---
title: Rozwiązywanie problemów z raportowaniem pomyślnego wdrożenia certyfikatu na urządzeniach w przypadku używania protokołu SCEP w usłudze Microsoft Intune | Microsoft Docs
description: Rozwiązywanie problemów z raportowaniem usługi NDES i łącznika do usługi Intune o pomyślnym wdrożeniu certyfikatów, które były aprowizowane za pomocą profilów certyfikatów protokołu SCEP.
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
ms.openlocfilehash: 2ccc738626efc140efca46d1b997164ed36dd37f
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "76916022"
---
# <a name="troubleshoot-ndes-reporting-of-certificate-deployments-in-microsoft-intune"></a>Rozwiązywanie problemów z raportowaniem wdrożeń certyfikatów za pomocą usługi NDES w usłudze Microsoft Intune

Skorzystaj z poniższych informacji, aby potwierdzić, że usługa NDES i łącznik certyfikatów usługi Microsoft Intune pomyślnie raportują do usługi Intune, że certyfikat został dostarczony do urządzenia. Raportowanie do usługi Intune to ostatnia faza aprowizowania certyfikatu na urządzeniach z systemem Windows przy użyciu profilów certyfikatów protokołu SCEP.

Ten artykuł dotyczy kroku 6 [przepływu pracy komunikacji protokołu SCEP](troubleshoot-scep-certificate-profiles.md).

## <a name="review-for-signs-of-successful-reporting"></a>Przeglądanie pod kątem oznak pomyślnego raportowania

Jeśli raportowanie zakończyło się pomyślnie, na serwerze usługi NDES znajdziesz wpisy podobne do następujących przykładów:

- **Dziennik usług IIS**:

  `fe80::f53d:89b8:c3e8:5fec%13 POST /CertificateRegistrationSvc/Certificate/Notify - 443 - fe80::f53d:89b8:c3e8:5fec%13 NDES_Plugin - 204 0 0 277 62`

- **Plik NDESPlugin.log**

  ```
  Calling Notifyrequest ...
  Sending request to certificate registration point.
  Exiting Notify with 0x0
  ```

- **Plik CertificateRegistrationPoint.svclog**:

  ![Dziennik łącznika certyfikatów usługi Intune](../protect/media/troubleshoot-scep-certificate-reporting/certificate-registration-point-log.png)

- **Plik NDESConnector.svclog**:

  ![Dziennik łącznika certyfikatów usługi Intune](../protect/media/troubleshoot-scep-certificate-reporting/ndesconnector-log.png)

- **Folder CertificateRequestStatus**:

  Przejdź do folderu *%ProgramFiles%\Microsoft Intune\CertificateRequestStatus*, w którym znajdują się foldery **Failed** (Niepowodzenie), **Processing** (Przetwarzanie) i **Succeed** (Powodzenie) zawierające pliki stanu żądania certyfikatu.

  Jeśli żądanie certyfikatu zostało pomyślnie przetworzone, w folderze **Succeed** (Powodzenie) pojawią się nowe pliki. Możesz użyć programu *Notepad.exe*, aby otworzyć te pliki i wyświetlić dane przekazane do usługi Intune przez łącznik certyfikatów usługi Intune. Przekazane dane zawierają szczegóły, takie jak **CertificateSerialNumber** (Numer seryjny certyfikatu), **UserID** (Identyfikator użytkownika), **DeviceID** (Identyfikator urządzenia) i **Thumbprint** (Odcisk palca).

### <a name="troubleshoot-stuck-files"></a>Rozwiązywanie problemów z zablokowanymi plikami

Jeśli nie widzisz żadnych nowych plików tworzonych w folderze *Succeed* (Powodzenie), sprawdź, czy pliki nie utknęły w folderze *Processing* (Przetwarzanie).

Upewnij się, że usługa łącznika usługi Intune została uruchomiona na serwerze usługi NDES i że w pliku Ndesconnector.svclog nie ma żadnych błędów.

## <a name="next-steps"></a>Następne kroki

[Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](../fundamentals/get-support.md)
