---
title: Rozwiązywanie problemów z modułem zasad łącznika certyfikatów usługi Microsoft Intune | Microsoft Docs
description: Rozwiązywanie problemów z działaniem modułu zasad usługi NDES, gdy moduł przetwarza żądanie certyfikatu, w przypadku używania profilów certyfikatów protokołu SCEP do wdrażania certyfikatów w usłudze Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/30/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: be53f6102226b004cab2bd953357e8c360a00f67
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "76915840"
---
# <a name="troubleshoot-the-ndes-policy-module-in-microsoft-intune"></a>Rozwiązywanie problemów z modułem zasad usługi NDES w usłudze Microsoft Intune

Informacje przedstawione w tym artykule pomagają w weryfikowaniu działania modułu zasad usługi rejestracji urządzeń sieciowych (NDES, Network Device Enrollment Service), który jest instalowany przy użyciu łącznika certyfikatów usługi Microsoft Intune. Gdy usługa NDES odbiera żądanie dotyczące certyfikatu, przekazuje to żądanie do modułu zasad, który sprawdza, czy żądanie jest prawidłowe dla urządzenia. Po walidacji usługa NDES kontaktuje się z urzędem certyfikacji, aby zażądać certyfikatu w imieniu urządzenia.

Ten artykuł dotyczy kroku 3 i kroku 4 [przepływu pracy komunikacji protokołu SCEP](troubleshoot-scep-certificate-profiles.md).

## <a name="ndes-communication-to-the-policy-module"></a>Komunikacja usługi NDES z modułem zasad

Po otrzymaniu żądania certyfikatu z urządzenia usługa NDES weryfikuje to żądanie w usłudze Intune za pośrednictwem modułu zasad, który jest instalowany za pomocą łącznika certyfikatów usługi Microsoft Intune. Te wpisy dotyczą *punktu rejestracji certyfikatów*.

**Wpisy dziennika wskazujące powodzenie**:

Aby potwierdzić, że żądanie weryfikacji zostało przesłane do modułu, wyszukaj wpis podobny do następującego przykładu w dziennikach na serwerze usługi NDES:

- **Dzienniki usług IIS**:

  ```
  fe80::f53d:89b8:c3e8:5fec%13 POST /CertificateRegistrationSvc/Certificate/VerifyRequest - 443 - 
  fe80::f53d:89b8:c3e8:5fec%13 NDES_Plugin - 201 0 0 341 875
  ```

- **Dziennik programu NDESPlugin**:

  ```
  Calling VerifyRequest ...  
  Sending request to certificate registration point.
  ```

  Poniższy przykład wskazuje pomyślną weryfikację żądania wezwania urządzenia i pokazuje, że usługa NDES może teraz kontaktować się z urzędem certyfikacji:

  ```
  Verify challenge returns true
  Exiting VerifyRequest with 0x0
  ```

- **Plik CertificateRegistrationPoint.svclog**:

  `Validation Phase 1 finished with status True.`  
  `Validation Phase 3 finished with status True.`  
  `VerifyRequest Finished with status True`


**Gdy brakuje wskaźników sukcesu**:

Jeśli nie znajdziesz tych wpisów, zacznij od przejrzenia wskazówek dotyczących rozwiązywania problemów dla [komunikacji urządzeń z serwerem usługi NDES](troubleshoot-scep-certificate-device-to-ndes.md#troubleshoot-common-errors).

Jeśli informacje zawarte w tym artykule nie pomogą rozwiązać problemu, poniżej przedstawiono dodatkowe wpisy, które mogą wskazywać problemy.

### <a name="ndespluginlog-contains-an-error-12175"></a>Plik NDESPlugin.log zawiera błąd 12175

Jeśli dziennik zawiera błąd 12175, który wygląda podobnie do poniższego, może występować problem z certyfikatem SSL:

```
WINHTTP_CALLBACK_STATUS_FLAG_CERT_CN_INVALID
Failed to send http request /CertificateRegistrationSvc/Certificate/VerifyRequest. Error 12175
```

Nowoczesne przeglądarki i przeglądarki na urządzeniach przenośnych ignorują *nazwę pospolitą* w certyfikacie SSL, jeśli istnieją *alternatywne nazwy podmiotów*.

**Rozwiązanie**:  Wydaj certyfikat SSL serwera internetowego z następującymi atrybutami dla *nazwy pospolitej* i *alternatywnej nazwy podmiotu*, a następnie powiąż go z portem 443 w usługach IIS:

  - **Nazwa podmiotu**  
    CN = nazwa serwera zewnętrznego
  - **Alternatywna nazwa podmiotu**  
     Nazwa = nazwa serwera zewnętrznego  
     Nazwa DNS = nazwa serwera wewnętrznego

### <a name="ndespluginlog-contains-an-error-403--forbidden-access-is-denied"></a>Plik NDESPlugin.log zawiera błąd 403 — Zabronione: Odmowa dostępu”

Jeśli następujące dzienniki zawierają błąd 403 podobny do poniższego, certyfikat klienta może być niezaufany lub nieprawidłowy:

**Plik NDESPlugin.log**:

```
Sending request to certificate registration point.
Verify challenge returns <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd"> <html xmlns="http://www.w3.org/1999/xhtml"> <head><meta http-equiv="Content-Type" content="text/html; charset=iso-8859-1"/>
<title>403 - Forbidden: Access is denied.</title>
```

**Dziennik usług IIS**:

```
POST /CertificateRegistrationSvc/Certificate/VerifyRequest - 443 -<IP_address>
NDES_Plugin - 403 16 2148204809 453  
```

Ten błąd występuje, jeśli w magazynie certyfikatów zaufanych głównych urzędów certyfikacji serwera usługi NDES istnieją certyfikaty z pośredniego urzędu certyfikacji.

Jeśli certyfikat ma tę samą wartość w polach *Wystawiono dla* i *Wystawiony przez*, to jest certyfikatem głównym. W przeciwnym razie jest to certyfikat pośredni.

**Rozwiązanie**: Aby rozwiązać ten problem, zidentyfikuj i usuń certyfikaty pośredniego urzędu certyfikacji z magazynu certyfikatów zaufanych głównych urzędów certyfikacji.

### <a name="ndespluginlog-indicates-the-challenge-returns-false"></a>Plik NDESPlugin.log wskazuje, że wyzwanie zwraca wartość false

Gdy wynik wyzwania zwraca wartość **false**, sprawdź, czy w pliku *CertificateRegistrationPoint.svclog* występują błędy. Możesz na przykład zauważyć komunikat o błędzie „Nie można pobrać certyfikatu podpisywania”, który przypomina następujący wpis:

```
Signing certificate could not be retrieved. System.Security.Cryptography.CryptographicException: m_safeCertContext is an invalid handle. at System.Security.Cryptography.X509Certificates.X509Certificate.ThrowIfContextInvalid() at System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHashString() at Microsoft.ConfigurationManager.CertRegPoint.CRPCertificate.RetrieveSigningCert(String certThumbprint
```

**Rozwiązanie**: Na serwerze, na którym jest zainstalowany łącznik, otwórz Edytor rejestru, znajdź klucz rejestru `HKLM\SOFTWARE\Microsoft\MicrosoftIntune\NDESConnector`, a następnie sprawdź, czy istnieje wartość SigningCertificate.

Jeśli ta wartość nie istnieje, ponownie uruchom usługę łącznika usługi Intune w programie services.msc, a następnie sprawdź, czy ta wartość pojawi się w rejestrze. Jeśli wartości nadal nie ma, często jest to spowodowane problemami z łącznością sieciową między serwerem usługi NDES i usługą Intune.

## <a name="ndes-passes-the-request-to-issue-the-certificate"></a>Usługa NDES przekazuje żądanie wystawienia certyfikatu

Po pomyślnej weryfikacji przez punkt rejestracji certyfikatu (moduł zasad) usługa NDES przekazuje żądanie certyfikatu do urzędu certyfikacji w imieniu urządzenia.

**Wpisy dziennika wskazujące powodzenie**:

- **Dziennik programu NDESPlugin**:

  ```
  Verify challenge returns true
  Exiting VerifyRequest with 0x0
  ```

- **Dzienniki usług IIS**:

  ```
  fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll/pkiclient.exe ... 80 - 
  fe80::f53d:89b8:c3e8:5fec%13 Mozilla/4.0+(compatible;+Win32;+NDES+client) - 200 0 0 2713 1296
  ```

- **Plik CertificateRegistrationPoint.svclog**:

  `Validation Phase 1 finished with status True.`  
  `Validation Phase 3 finished with status True.`  
  `VerifyRequest Finished with status True`

**Gdy brakuje wskaźników sukcesu**:

Jeśli nie widzisz wpisów wskazujących powodzenie, wykonaj następujące kroki:

1. Wyszukaj problemy, które są rejestrowane w pliku *CertificateRegistrationPoint.svclog*, gdy punkt rejestracji certyfikatu weryfikuje wyzwanie. Wyszukaj wpisy między następującymi wierszami:

   - VerifyRequest Started.
   - VerifyRequest Finished with status False

2. Otwórz przystawkę MMC urzędu certyfikacji na stronie urzędu certyfikacji, a następnie wybierz pozycję **Żądania zakończone niepowodzeniem**, aby wyszukać błędy pomocne w zidentyfikowaniu problemu. Poniższy obraz przedstawia przykład:

   ![Przykład żądania zakończonego niepowodzeniem](../protect/media/troubleshoot-scep-certificate-ndes-policy-module/failed-requests.png)

3. Przejrzyj dziennik zdarzeń aplikacji w urzędzie certyfikacji pod kątem błędów. Zazwyczaj można znaleźć błędy, które są zgodne błędami widocznymi w obszarze **Żądania zakończone niepowodzeniem** z poprzedniego kroku. Poniższy obraz przedstawia przykład:

   ![Przeglądanie dziennika aplikacji](../protect/media/troubleshoot-scep-certificate-ndes-policy-module/application-log-errors.png)

## <a name="next-steps"></a>Następne kroki

Jeśli moduł zasad usługi NDES zweryfikuje żądanie i żądanie zostanie przekazane do urzędu certyfikacji, następnym krokiem jest zapoznanie się z [dostarczaniem certyfikatu do urządzenia](troubleshoot-scep-certificate-delivery.md).
