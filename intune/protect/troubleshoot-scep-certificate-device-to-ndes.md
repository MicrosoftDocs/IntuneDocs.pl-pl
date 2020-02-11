---
title: Rozwiązywanie problemów z komunikacją urządzenia zarządzanego z usługą NDES w usłudze Microsoft Intune | Microsoft Docs
description: Rozwiązywanie problemów z komunikacją urządzenia zarządzanego z serwerem usługi NDES w przypadku używania profilów certyfikatów protokołu SCEP w celu wdrażania certyfikatów za pomocą usługi Intune.
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
ms.openlocfilehash: 8c81fa9b521b0d950fb69c29f7625981e709863d
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "76916113"
---
# <a name="troubleshoot-device-to-ndes-server-communication-for-scep-certificate-profiles-in-microsoft-intune"></a>Rozwiązywanie problemów z komunikacją urządzenia z serwerem usługi NDES dla profilów certyfikatów protokołu SCEP w usłudze Microsoft Intune

Poniższe informacje umożliwiają określenie, czy urządzenie, które otrzymało i przetworzyło profil certyfikatu prostego protokołu rejestrowania certyfikatów (SCEP, Simple Certificate Enrollment Protocol) usługi Intune, może pomyślnie skontaktować się z usługą rejestrowania urządzeń sieciowych (NDES, Network Device Enrollment Service) w celu przedstawienia wyzwania. Na urządzeniu generowany jest klucz prywatny, a żądanie podpisania certyfikatu (CSR, Certificate Signing Request) i wyzwanie są przekazywane z urządzenia do serwera usługi NDES. Aby skontaktować się z serwerem usługi NDES, urządzenie używa identyfikatora URI z profilu certyfikatu protokołu SCEP.

Ten artykuł dotyczy kroku 2 z [omówienia przepływu komunikacji protokołu SCEP](troubleshoot-scep-certificate-profiles.md).

## <a name="review-iis-logs-for-a-connection-from-the-device"></a>Przeglądanie dzienników usług IIS pod kątem połączenia z urządzenia

Dzienniki usług IIS zawierają ten sam typ wpisów dla wszystkich platform.


1. Na serwerze usługi NDES otwórz najnowszy plik dziennika usług IIS, który znajduje się w następującym folderze: *%SystemDrive%\inetpub\logs\logfiles\w3svc1*

2. Wyszukaj w dzienniku wpisy podobne do poniższych przykładów. Oba przykłady zawierają stan **200**, który znajduje się w końcowej części:

   `fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll/pkiclient.exe operation=GetCACaps&message=default 80 - fe80::f53d:89b8:c3e8:5fec%13 Mozilla/4.0+(compatible;+Win32;+NDES+client) - 200 0 0 186 0.`

   oraz

   `fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll/pkiclient.exe operation=GetCACert&message=default 80 - fe80::f53d:89b8:c3e8:5fec%13 Mozilla/4.0+(compatible;+Win32;+NDES+client) - 200 0 0 3567 0`

3. Gdy urządzenie kontaktuje się z usługami IIS, rejestrowane jest żądanie HTTP GET dla biblioteki mscep.dll.

   Sprawdź kod stanu w końcowej części tego żądania:
   - **Kod stanu równy 200**: Ten stan wskazuje, że połączenie z serwerem usługi NDES zostało nawiązane pomyślnie.
   - **Kod stanu równy 500**: Grupa IIS_IURS może nie mieć prawidłowych uprawnień. Zobacz [Kod stanu 500](#status-code-500) w dalszej części tego artykułu.
   - Jeśli kod stanu nie wynosi 200 ani 500:

     - Zobacz [Testowanie adresu URL serwera SCEP](#test-the-scep-server-url) w dalszej części tego artykułu w celu zweryfikowania konfiguracji.

     - Zobacz [Kody stanów HTTP w programach IIS 7 i późniejszych wersjach](https://support.microsoft.com/help/943891), aby uzyskać informacje o rzadziej występujących kodach błędów.

   Jeśli żądanie połączenia nie zostało w ogóle zarejestrowane, kontakt z urządzenia może być blokowany w sieci między urządzeniem a serwerem usługi NDES.

## <a name="review-device-logs-for-connections-to-ndes"></a>Przeglądanie dzienników urządzenia pod kątem połączeń z usługą NDES

### <a name="android-devices"></a>Urządzenia z systemem Android

Przejrzyj [dziennik programu OMADM urządzeń](troubleshoot-scep-certificate-profiles.md#logs-for-android-devices). Wyszukaj wpisy podobne do następujących, które są rejestrowane, gdy urządzenie łączy się z usługą NDES:

```
2018-02-27T05:16:08.2500000  VERB  Event  com.microsoft.omadm.platforms.android.certmgr.CertificateEnrollmentManager  18327    10  There are 1 requests
2018-02-27T05:16:08.2500000  VERB  Event  com.microsoft.omadm.platforms.android.certmgr.CertificateEnrollmentManager  18327    10  Trying to enroll certificate request: ModelName=AC_51bad41f-3854-4eb5-a2f2-0f7a94034ee8%2FLogicalName_39907e78_e61b_4730_b9fa_d44a53e4111c;Hash=1677525787
2018-02-27T05:16:09.5530000  VERB  Event  org.jscep.transport.UrlConnectionGetTransport  18327    10  Sending GetCACaps(ca) to https://<server>.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=ca
2018-02-27T05:16:14.6440000  VERB  Event  org.jscep.transport.UrlConnectionGetTransport  18327    10  Received '200 OK' when sending GetCACaps(ca) to https://<server>.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=ca
2018-02-27T05:16:21.8220000  VERB  Event  org.jscep.message.PkiMessageEncoder  18327     10 Encoding message: org.jscep.message.PkcsReq@2b06f45f[messageData=org.<server>.pkcs.PKCS10CertificationRequest@699b3cd,messageType=PKCS_REQ,senderNonce=Nonce [D447AE9955E624A56A09D64E2B3AE76E],transId=251E592A777C82996C7CF96F3AAADCF996FC31FF]
2018-02-27T05:16:21.8790000  VERB  Event  org.jscep.message.PkiMessageEncoder  18327     10  Signing pkiMessage using key belonging to [dn=CN=<uesrname>; serial=1]
2018-02-27T05:16:21.9580000  VERB  Event  org.jscep.transaction.EnrollmentTransaction  18327     10  Sending org.<server>.cms.CMSSignedData@ad57775
```

Kluczowe wpisy zawierają następujące przykładowe ciągi tekstowe:

- There are 1 requests
- Received '200 OK' when sending GetCACaps(ca) to https://\<server>.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=ca
- Signing pkiMessage using key belonging to [dn=CN=\<username>; serial=1]


Połączenie jest również rejestrowane przez usługi IIS w folderze %SystemDrive%\inetpub\logs\LogFiles\W3SVC1\ serwera usług NDES. Poniżej przedstawiono przykład:

```
fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll operation=GetCACert&message=ca 443 - 
fe80::f53d:89b8:c3e8:5fec%13 Dalvik/2.1.0+(Linux;+U;+Android+5.0;+P01M+Build/LRX21V) - 200 0 0 3909 0
fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll operation=GetCACaps&message=ca 443 - 
fe80::f53d:89b8:c3e8:5fec%13 Dalvik/2.1.0+(Linux;+U;+Android+5.0;+P01M+Build/LRX21V) - 200 0 0 421 
```

### <a name="ios-and-ipados-devices"></a>Urządzenia z systemami iOS i iPadOS

Przejrzyj [dziennik debugowania urządzeń](troubleshoot-scep-certificate-profiles.md#logs-for-ios-and-ipados-devices). Wyszukaj wpisy podobne do następujących, które są rejestrowane, gdy urządzenie łączy się z usługą NDES:

```
debug    18:30:53.691033 -0500    profiled    Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACert&message=SCEP%20Authority\ 
debug    18:30:54.640644 -0500    profiled    Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=SCEP%20Authority\ 
default    18:30:55.483977 -0500    profiled    Attempting to retrieve issued certificate...\ 
debug    18:30:55.487798 -0500    profiled    Sending CSR via GET.\  
debug    18:30:55.487908 -0500    profiled    Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=PKIOperation&message=MIAGCSqGSIb3DQEHAqCAMIACAQExDzANBglghkgBZQMEAgMFADCABgkqhkiG9w0BBwGggCSABIIZfzCABgkqhkiG9w0BBwOggDCAAgEAMYIBgjCCAX4CAQAwZjBPMRUwEwYKCZImiZPyLGQBGRYFbG9jYWwxHDAaBgoJkiaJk/IsZAEZFgxmb3VydGhjb2ZmZWUxGDAWBgNVBAMTD0ZvdXJ0aENvZmZlZSBDQQITaAAAAAmaneVjEPlcTwAAAAAACTANBgkqhkiG9w0BAQEFAASCAQCqfsOYpuBToerQLkw/tl4tH9E+97TBTjGQN9NCjSgb78fF6edY0pNDU+PH4RB356wv3rfZi5IiNrVu5Od4k6uK4w0582ZM2n8NJFRY7KWSNHsmTIWlo/Vcr4laAtq5rw+CygaYcefptcaamkjdLj07e/Uk4KsetGo7ztPVjSEFwfRIfKv474dLDmPqp0ZwEWRQGZwmPoqFMbX3g85CJT8khPaqFW05yGDTPSX9YpuEE0Bmtht9EwOpOZe6O7sd77IhfFZVmHmwy5mIYN7K6mpx/4Cb5zcNmY3wmTBlKEkDQpZDRf5PpVQ3bmQ3we9XxeK1S4UsAXHVdYGD+bg/bCafMIAGCSqGSIb3DQEHATAUBggqhkiG9w0DBwQI5D5J2lwZS5OggASCF6jSG9iZA/EJ93fEvZYLV0v7GVo3JAsR11O7DlmkIqvkAg5iC6DQvXO1j88T/MS3wV+rqUbEhktr8Xyf4sAAPI4M6HMfVENCJTStJw1PzaGwUJHEasq39793nw4k268UV5XHXvzZoF3Os2OxUHSfHECOj
```

Kluczowe wpisy zawierają następujące przykładowe ciągi tekstowe:

- operation=GetCACert
- Attempting to retrieve issued certificate
- Sending CSR via GET
- operation=PKIOperation

### <a name="windows-devices"></a>Urządzenia z systemem Windows

Na urządzeniu z systemem Windows, które nawiązuje połączenie z usługą NDES, można wyświetlić Podgląd zdarzeń systemu Windows i poszukać oznak pomyślnego połączenia. Połączenia są rejestrowane jako zdarzenia o identyfikatorze **36** w dzienniku *DeviceManagement-Enterprise-Diagnostics-Provide* > **Administrator** urządzenia.

Aby otworzyć dziennik:

1. Na urządzeniu uruchom polecenie **eventvwr.msc**, aby otworzyć Podgląd zdarzeń systemu Windows.

2. Rozwiń pozycję **Dzienniki aplikacji i usług** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostic-Provider** > **Administrator**.

3. Wyszukaj zdarzenie **36**, które przypomina poniższy przykład z kluczowym wierszem **SCEP: Certificate request generated successfully**:

   ```
   Event ID:      36
   Task Category: None
   Level:         Information
   Keywords:
   User:          <UserSid>
   Computer:      <Computer Name>
   Description:
   SCEP: Certificate request generated successfully. Enhanced Key Usage: (1.3.6.1.5.5.7.3.2), NDES URL: (https://<server>/certsrv/mscep/mscep.dll/pkiclient.exe), Container Name: (), KSP Setting: (0x2), Store Location: (0x1).
   ```

## <a name="troubleshoot-common-errors"></a>Rozwiązywanie typowych problemów

Poniższe sekcje mogą pomóc w rozwiązywaniu typowych problemów z połączeniami ze wszystkich platform urządzeń do usługi NDES.

### <a name="status-code-500"></a>Kod stanu 500

Połączenia podobne do poniższego przykładu, z kodem stanu równym 500, wskazują, że uprawnienie użytkownika *Personifikuj klienta po uwierzytelnieniu* nie jest przypisane do grupy IIS_IURS na serwerze usługi NDES. Wartość stanu **500** jest widoczna na końcu:

```
2017-08-08 20:22:16 IP_address GET /certsrv/mscep/mscep.dll operation=GetCACert&message=SCEP%20Authority 443 - 10.5.14.22 profiled/1.0+CFNetwork/811.5.4+Darwin/16.6.0 - 500 0 1346 31
```

**Aby rozwiązać ten problem**:

1. Na serwerze usługi NDES uruchom polecenie **secpol.msc**, aby otworzyć zasady zabezpieczeń lokalnych.

2. Rozwiń węzeł **Zasady lokalne**, a następnie kliknij pozycję **Przypisywanie praw użytkownika**.

3. Kliknij dwukrotnie pozycję **Personifikuj klienta po uwierzytelnieniu** w okienku po prawej stronie.

4. Kliknij pozycję **Dodaj użytkownika lub grupę...** , wprowadź ciąg **IIS_IURS** w polu **Wprowadź nazwy obiektów do wybrania**, a następnie kliknij przycisk **OK**.

5. Kliknij przycisk **OK**.

6. Uruchom ponownie komputer, a następnie spróbuj ponownie nawiązać połączenie z urządzenia.

### <a name="test-the-scep-server-url"></a>Testowanie adresu URL serwera SCEP

Wykonaj następujące kroki, aby przetestować adres URL określony w profilu certyfikatu protokołu SCEP.

1. W usłudze Intune edytuj profil certyfikatu protokołu SCEP i skopiuj adres URL serwera. Adres URL powinien być podobny do następującego: *https://contoso.com/certsrv/mscep/msecp.dll* .

2. Otwórz przeglądarkę internetową, a następnie przejdź do tego adresu URL serwera SCEP. Wynik powinien być następujący: **Błąd HTTP 403.0 — Dostęp zabroniony**. Ten wynik wskazuje, że adres URL działa prawidłowo.

   Jeśli ten błąd nie zostanie wyświetlony, wybierz link przypominający błąd, który widzisz, aby wyświetlić wskazówki dotyczące konkretnego problemu:
   - [Otrzymuję ogólny komunikat dotyczący usługi rejestracji urządzeń sieciowych](#general-ndes-message)
   - [Otrzymuję komunikat „Błąd HTTP 503. Usługa jest niedostępna”](#http-error-503)
   - [Otrzymuję komunikat o błędzie „Limit czasu bramy”](#gatewaytimeout)
   - [Otrzymuję komunikat „HTTP 414 Identyfikator URI żądania jest za długi”](#http-414-request-uri-too-long)
   - [Otrzymuję komunikat „Nie można wyświetlić tej strony”](#this-page-cant-be-displayed)
   - [Otrzymuję komunikat „500 — Wewnętrzny błąd serwera”](#internal-server-error)

#### <a name="general-ndes-message"></a>Ogólny komunikat dotyczący usługi NDES

Po przejściu do adresu URL serwera SCEP jest wyświetlany następujący komunikat usługi rejestracji urządzeń sieciowych:

![Adres URL serwera SCEP](../protect/media/troubleshoot-scep-certificate-device-to-ndes/ndes-server-url-message.png)

- **Przyczyna**: Ten problem jest zazwyczaj związany z instalacją łącznika usługi Microsoft Intune.

  Biblioteka mscep.dll to rozszerzenie ISAPI, które przechwytuje żądanie przychodzące i wyświetla błąd HTTP 403, jeśli instalacja przebiegła poprawnie.
  
  **Rozwiązanie**: Sprawdź plik *SetupMsi.log*, aby określić, czy łącznik usługi Microsoft Intune został zainstalowany poprawnie. W poniższym przykładzie komunikaty *Instalacja została zakończona pomyślnie* i *Stan powodzenia lub błędu instalacji: 0* wskazują pomyślną instalację:

  ```
  MSI (c) (28:54) [16:13:11:905]: Product: Microsoft Intune Connector -- Installation completed successfully.
  MSI (c) (28:54) [16:13:11:999]: Windows Installer installed the product. Product Name: Microsoft Intune Connector. Product Version: 6.1711.4.0. Product Language: 1033. Manufacturer: Microsoft Corporation. Installation success or error status: 0.
  ```

  Jeśli instalacja nie powiedzie się, usuń łącznik usługi Microsoft Intune, a następnie zainstaluj go ponownie.

#### <a name="http-error-503"></a>Błąd HTTP 503

Po przejściu do adresu URL serwera SCEP jest wyświetlany następujący komunikat o błędzie:

![Błąd HTTP 503. Usługa jest niedostępna](../protect/media/troubleshoot-scep-certificate-device-to-ndes/service-unavailable.png)

Ten problem jest zwykle spowodowany tym, że nie uruchomiono puli aplikacji protokołu **SCEP** w usługach IIS. Na serwerze usługi NDES otwórz **Menedżera usług IIS** i przejdź do obszaru **Pule aplikacji**. Znajdź pulę aplikacji protokołu **SCEP** i potwierdź, że została uruchomiona.

Jeśli pula aplikacji protokołu SCEP nie została uruchomiona, sprawdź dziennik zdarzeń aplikacji na serwerze:

1. Na urządzeniu uruchom polecenie **eventvwr.msc**, aby otworzyć **Podgląd zdarzeń** i wybierz pozycję **Dzienniki systemu Windows** > **Aplikacja**.

2. Poszukaj zdarzenia podobnego do poniższego przykładu, które oznacza, że pula aplikacji ulega awarii po odebraniu żądania:

   ```
   Log Name:      Application
   Source:        Application Error
   Event ID:      1000
   Task Category: Application Crashing Events
   Level:         Error
   Keywords:      Classic
   Description: Faulting application name: w3wp.exe, version: 8.5.9600.16384, time stamp: 0x5215df96
   Faulting module name: ntdll.dll, version: 6.3.9600.18821, time stamp: 0x59ba86db
   Exception code: 0xc0000005
   ```

**Najczęstsze przyczyny awarii puli aplikacji**:

- **Przyczyna 1**: W magazynie certyfikatów zaufanych głównych urzędów certyfikacji serwera usługi NDES istnieją certyfikaty z pośredniego urzędu certyfikacji (bez podpisu własnego).

  **Rozwiązanie**: Usuń certyfikaty pośrednie z magazynu certyfikatów zaufanych głównych urzędów certyfikacji, a następnie ponownie uruchom serwer usługi NDES.
  
  Aby zidentyfikować wszystkie certyfikaty pośrednie w magazynie certyfikatów zaufanych głównych urzędów certyfikacji, uruchom następujące polecenie cmdlet programu PowerShell: `Get-Childitem -Path cert:\LocalMachine\root -Recurse | Where-Object {$_.Issuer -ne $_.Subject}`

  Certyfikat, który ma tę samą wartość w polach **Wystawiono dla** i **Wystawiony przez**, jest certyfikatem głównym. W przeciwnym razie jest to certyfikat pośredni.

  Po usunięciu certyfikatów i ponownym uruchomieniu serwera ponownie uruchom polecenie cmdlet programu PowerShell, aby upewnić się, że nie ma certyfikatów pośrednich. Jeśli są, sprawdź, czy zasady grupy wypychają certyfikaty pośrednie do serwera usługi NDES. Jeśli tak, wyklucz serwer usługi NDES z zasad grupy i ponownie usuń certyfikaty pośrednie.

- **Przyczyna 2**: Adresy URL na liście odwołania certyfikatów (CRL, Certificate Revocation List) są blokowane lub nieosiągalne dla certyfikatów używanych przez łącznik certyfikatów usługi Intune.

  **Rozwiązanie**: Włącz dodatkowe rejestrowanie, aby zebrać więcej informacji:
  1. Otwórz Podgląd zdarzeń, kliknij pozycję **Widok**, upewnij się, że opcja **Pokaż dzienniki analityczne i debugowania** jest zaznaczona.
  2. Przejdź do obszaru **Dzienniki aplikacji i usług** > **Microsoft** > **Windows** > **CAPI2** > **Operacyjne**, kliknij prawym przyciskiem myszy pozycję **Operacyjne**, a następnie kliknij pozycję **Włącz dziennik**.
  3. Po włączeniu rejestrowania CAPI2 odtwórz problem i przejrzyj dziennik zdarzeń w celu rozwiązania problemu.

- **Przyczyna 3**: Uprawnienie usługi IIS do usługi **CertificateRegistrationSvc** ma włączoną opcję **Uwierzytelnianie systemu Windows**.

  **Rozwiązanie**: Włącz opcję **Uwierzytelnianie anonimowe** i wyłącz opcję **Uwierzytelnianie systemu Windows**, a następnie ponownie uruchom serwer usługi NDES.

  ![Uprawnienia usługi IIS](../protect/media/troubleshoot-scep-certificate-device-to-ndes/iis-permissions.png)

#### <a name="gatewaytimeout"></a>Limit czasu bramy

Po przejściu do adresu URL serwera SCEP jest wyświetlany następujący komunikat o błędzie:

![Błąd limitu czasu bramy](../protect/media/troubleshoot-scep-certificate-device-to-ndes/gateway-timeout.png)

- **Przyczyna**: Usługa **łącznika serwera proxy aplikacji usługi Microsoft AAD** nie jest uruchomiona.

  **Rozwiązanie**:  Uruchom polecenie **services.msc**, a następnie upewnij się, że usługa **łącznika serwera proxy aplikacji usługi Microsoft AAD** jest uruchomiona i że dla właściwości **Typ uruchamiania** ustawiono wartość **Automatyczne**.

#### <a name="http-414-request-uri-too-long"></a>HTTP 414 Identyfikator URI żądania jest za długi

Po przejściu do adresu URL serwera SCEP jest wyświetlany następujący komunikat o błędzie: `HTTP 414 Request-URI Too Long`

- **Przyczyna**: Filtrowanie żądań usług IIS nie jest skonfigurowane w celu obsługi długich adresów URL (zapytań) odbieranych przez usługę NDES. Ta obsługa jest konfigurowana podczas [konfigurowania usługi NDES](certificates-scep-configure.md#configure-the-ndes-service) pod kątem użycia z infrastrukturą dla protokołu SCEP.

- **Rozwiązanie**: Skonfiguruj obsługę długich adresów URL.

  1. Na serwerze usługi NDES otwórz menedżera usług IIS, wybierz pozycję **Domyślna witryna internetowa** > **Filtrowanie żądań** > **Edytuj ustawienia funkcji**, aby otworzyć stronę **Edytowanie ustawień filtrowania żądań**.

  2. Skonfiguruj następujące ustawienia:
     - **Maksymalna długość adresu URL (w bajtach)** = 65534
     - **Maksymalna długość ciągu zapytania (w bajtach)** = 65534

  3. Wybierz przycisk **OK**, aby zapisać tę konfigurację i zamknąć menedżera usług IIS.

  4. Zweryfikuj tę konfigurację, znajdując następujący klucz rejestru w celu potwierdzenia, że ma on wskazane wartości:

     HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters

     Następujące wartości są ustawione jako wpisy typu DWORD:
     - Nazwa: **MaxFieldLength** o wartości dziesiętnej **65534**
     - Nazwa: **MaxRequestBytes** o wartości dziesiętnej **65534**

  5. Uruchom ponownie serwer usługi NDES.

#### <a name="this-page-cant-be-displayed"></a>Nie można wyświetlić tej strony

Masz skonfigurowany serwer proxy aplikacji usługi Azure AD. Po przejściu do adresu URL serwera SCEP jest wyświetlany następujący komunikat o błędzie:

`This page can't be displayed`

- **Przyczyna**: Ten problem występuje, gdy zewnętrzny adres URL protokołu SCEP jest niepoprawny w konfiguracji serwera proxy aplikacji. Przykład tego adresu URL: https://contoso.com/certsrv/mscep/mscep.dll.

  **Rozwiązanie**: Użyj domeny domyślnej *yourtenant.msappproxy.net* na potrzeby zewnętrznego adresu URL protokołu SCEP w konfiguracji serwera proxy aplikacji.

#### <a name="internal-server-error"></a>500 — Wewnętrzny błąd serwera

Po przejściu do adresu URL serwera SCEP jest wyświetlany następujący komunikat o błędzie:

![500 — Wewnętrzny błąd serwera](../protect/media/troubleshoot-scep-certificate-device-to-ndes/500-internal-server-error.png)

- **Przyczyna 1**: Konto usługi NDES jest zablokowane lub jego hasło wygasło.

  **Rozwiązanie**: Odblokuj konto lub zresetuj hasło.

- **Przyczyna 2**: Certyfikaty MSCEP-RA wygasły.

  **Rozwiązanie**: W przypadku wygaśnięcia certyfikatów MSCEP-RA zainstaluj ponownie rolę usługi NDES lub zażądaj nowych certyfikatów szyfrowania protokołu CEP i agenta rejestracji programu Exchange (żądanie offline).

  Aby zażądać nowych certyfikatów, wykonaj następujące kroki:

  1. W urzędzie certyfikacji lub w urzędzie wystawiającym certyfikaty otwórz konsolę MMC szablonów certyfikatów. Upewnij się, że zalogowany użytkownik i serwer usługi NDES mają uprawnienia **odczytu** i **rejestrowania** do szablonów certyfikatów szyfrowania protokołu CEP i agenta rejestracji programu Exchange (żądanie offline).

  2. Sprawdź wygasłe certyfikaty na serwerze usługi NDES, skopiuj informacje **podmiotu** z certyfikatu.

  3. Otwórz konsolę MMC certyfikatów na stronie **Konto komputera**.

  4. Rozwiń węzeł **Osobiste**, kliknij prawym przyciskiem myszy pozycję **Certyfikaty**, a następnie wybierz pozycję **Wszystkie zadania** > **Żądaj nowego certyfikatu**.

  5. Na stronie **Żądanie certyfikatu** wybierz pozycję **Szyfrowanie protokołu CEP**, a następnie kliknij pozycję **Do zarejestrowania tego certyfikatu jest wymaganych więcej informacji. Kliknij tutaj, aby skonfigurować ustawienia**.

     ![Wybieranie szyfrowania protokołu CEP](../protect/media/troubleshoot-scep-certificate-device-to-ndes/select-scep-encryption.png)

  6. W obszarze **Właściwości certyfikatu** kliknij kartę **Podmiot**, wypełnij pole **Nazwa podmiotu** za pomocą informacji zebranych w kroku 2, a następnie kliknij pozycję **Dodaj** i przycisk **OK**.

  7. Ukończ rejestrację certyfikatu.

  8. Otwórz konsolę MMC certyfikatów na stronie **Moje konto użytkownika**.

     Rejestrowanie certyfikatu agenta rejestracji programu Exchange (żądanie offline) należy wykonać w kontekście użytkownika. **Typ podmiotu** tego szablonu certyfikatu ma ustawioną wartość **Użytkownik**.

  9. Rozwiń węzeł **Osobiste**, kliknij prawym przyciskiem myszy pozycję **Certyfikaty**, a następnie wybierz pozycję **Wszystkie zadania** > **Żądaj nowego certyfikatu**.

  10. Na stronie **Żądanie certyfikatu** wybierz pozycję **Agent rejestracji programu Exchange (żądanie offline)** , a następnie kliknij pozycję **Do zarejestrowania tego certyfikatu jest wymaganych więcej informacji. Kliknij tutaj, aby skonfigurować ustawienia**.

      ![Wybieranie agenta rejestracji programu Exchange](../protect/media/troubleshoot-scep-certificate-device-to-ndes/select-exchange-enrollment-agent.png)

  11. W obszarze **Właściwości certyfikatu** kliknij kartę **Podmiot**, wypełnij pole **Nazwa podmiotu** za pomocą informacji zebranych w kroku 2, a następnie kliknij pozycję **Dodaj**.

      ![Właściwości certyfikatu](../protect/media/troubleshoot-scep-certificate-device-to-ndes/certificate-properties.png)

      Wybierz kartę **Klucz prywatny**, wybierz pozycję **Klucz prywatny można eksportować**, a następnie kliknij przycisk **OK**.

      ![Klucz prywatny](../protect/media/troubleshoot-scep-certificate-device-to-ndes/private-key.png)

  12. Ukończ rejestrację certyfikatu.

  13. Wyeksportuj certyfikat agenta rejestracji programu Exchange (żądanie offline) z magazynu certyfikatów bieżącego użytkownika. W Kreatorze eksportu certyfikatów wybierz opcję **Tak, eksportuj klucz prywatny**.

  14. Zaimportuj certyfikat do magazynu certyfikatów komputera lokalnego.

  15. W konsoli MMC certyfikatów wykonaj następujące czynności dla każdego z nowych certyfikatów:

      Kliknij prawym przyciskiem myszy certyfikat, kliknij pozycję **Wszystkie zadania** > **Zarządzaj kluczami prywatnymi** i dodaj uprawnienie do **odczytu** dla konta usługi NDES.

  16. Uruchom polecenie **iisreset**, aby ponownie uruchomić usługi IIS.

## <a name="next-steps"></a>Następne kroki

Jeśli urządzenie pomyślnie połączy się z serwerem usługi NDES w celu zaprezentowania żądania certyfikatu, następnym krokiem jest zapoznanie się z [modułem Zasady łączników certyfikatów usługi Intune](troubleshoot-scep-certificate-ndes-policy-module.md).
