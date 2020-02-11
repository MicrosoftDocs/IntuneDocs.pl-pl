---
title: Rozwiązywanie problemów z dostarczaniem certyfikatów do urządzeń w przypadku korzystania z protokołu SCEP w usłudze Microsoft Intune | Microsoft Docs
description: Rozwiązywanie problemów z dostarczaniem certyfikatu do urządzenia z urzędu certyfikacji w przypadku używania profilów certyfikatów protokołu SCEP w usłudze Intune w celu wdrożenia certyfikatów.
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
ms.openlocfilehash: 77be59d126dc7e73bee468ca938938c6bb1b2e1a
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "76915879"
---
# <a name="troubleshoot-the-delivery-of-certificates-provisioned-by-scep-to-devices-in-microsoft-intune"></a>Rozwiązywanie problemów z dostarczaniem certyfikatów aprowizowanych przez protokół SCEP do urządzeń w usłudze Microsoft Intune

Informacje przedstawione w tym artykule ułatwiają badanie dostarczania certyfikatów do urządzeń w przypadku używania prostego protokołu rejestrowania certyfikatów (SCEP, Simple Certificate Enrollment Protocol) w celu aprowizowania certyfikatów w usłudze Intune. Gdy serwer usługi rejestracji urządzeń sieciowych (NDES, Network Device Enrollment Service) odbiera żądany certyfikat dla urządzenia z urzędu certyfikacji (CA), przekazuje ten certyfikat z powrotem do urządzenia.

Ten artykuł dotyczy kroku 5 [przepływu pracy komunikacji protokołu SCEP](troubleshoot-scep-certificate-profiles.md): dostarczanie certyfikatu do urządzenia, które przesłało żądanie certyfikatu.

## <a name="review-the-certification-authority"></a>Przeglądanie urzędu certyfikacji

Gdy urząd certyfikacji wystawi certyfikat, w urzędzie certyfikacji zobaczysz wpis podobny do następującego przykładu:

![Przykład wystawionych certyfikatów](../protect/media/troubleshoot-scep-certificate-delivery/certificate-authority.png)

## <a name="review-the-device"></a>Przeglądanie urządzenia

### <a name="android"></a>Android

W przypadku urządzeń zarejestrowanych przez administratora urządzenia zobaczysz powiadomienie podobne do przedstawionego na poniższym obrazie, które zawiera monit o zainstalowanie certyfikatu:

![Powiadomienie w systemie Android](../protect/media/troubleshoot-scep-certificate-delivery/android-notification.png)

W przypadku systemu Android Enterprise lub Samsung KNOX instalacja certyfikatu odbywa się automatycznie i dyskretnie.

Aby wyświetlić zainstalowany certyfikat w systemie Android, użyj aplikacji do wyświetlania certyfikatów innej firmy.

Możesz także przejrzeć [dziennik programu OMADM urządzeń](troubleshoot-scep-certificate-profiles.md#logs-for-android-devices). Wyszukaj wpisy podobne do następujących, które są rejestrowane, gdy certyfikat jest instalowany:

**Certyfikat główny**:

```
2018-02-27T04:50:52.1890000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeRootCertInstallStateMachine     9595        9    Root cert '17…' state changed from CERT_INSTALL_REQUESTED to CERT_INSTALL_REQUESTED
2018-02-27T04:53:31.1300000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeRootCertInstallStateMachine     9595        0    Root cert '17…' state changed from CERT_INSTALL_REQUESTED to CERT_INSTALLING
2018-02-27T04:53:32.0390000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeRootCertInstallStateMachine     9595       14    Root cert '17…' state changed from CERT_INSTALLING to CERT_INSTALL_SUCCESS
```

**Certyfikat aprowizowany za pośrednictwem protokołu SCEP**

```
2018-02-27T05:16:08.2500000    VERB    Event     com.microsoft.omadm.platforms.android.certmgr.CertificateEnrollmentManager    18327       10    There are 1 requests
2018-02-27T05:16:08.2500000    VERB    Event     com.microsoft.omadm.platforms.android.certmgr.CertificateEnrollmentManager    18327       10    Trying to enroll certificate request: ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787
2018-02-27T05:16:20.6150000    VERB    Event     org.jscep.transport.UrlConnectionGetTransport    18327       10    Sending GetCACert(ca) to https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACert&message=ca
2018-02-27T05:16:20.6530000    VERB    Event     org.jscep.transport.UrlConnectionGetTransport    18327       10    Received '200 OK' when sending GetCACert(ca) to https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACert&message=ca
2018-02-27T05:16:21.7460000    VERB    Event     org.jscep.transport.UrlConnectionGetTransport    18327       10    Sending GetCACaps(ca) to https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=ca
2018-02-27T05:16:21.7890000    VERB    Event     org.jscep.transport.UrlConnectionGetTransport    18327       10    Received '200 OK' when sending GetCACaps(ca) to https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=ca
2018-02-27T05:16:28.0340000    VERB    Event     org.jscep.transaction.EnrollmentTransaction    18327       10    Response: org.jscep.message.CertRep@3150777b[failInfo=<null>,pkiStatus=SUCCESS,recipientNonce=Nonce [GUID],messageData=org.spongycastle.cms.CMSSignedData@27cc8998,messageType=CERT_REP,senderNonce=Nonce [GUID],transId=TRANSID]
2018-02-27T05:16:28.2440000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeScepCertInstallStateMachine    18327       10    SCEP cert 'ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787' state changed from CERT_ENROLLED to CERT_INSTALL_REQUESTED
2018-02-27T05:18:44.9820000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeScepCertInstallStateMachine    18327        0    SCEP cert 'ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787' state changed from CERT_INSTALL_REQUESTED to CERT_INSTALLING
2018-02-27T05:18:45.3460000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeScepCertInstallStateMachine    18327       14    SCEP cert 'ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787' state changed from CERT_INSTALLING to CERT_ACCESS_REQUESTED
2018-02-27T05:20:15.3520000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeScepCertInstallStateMachine    18327       21    SCEP cert 'ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787' state changed from CERT_ACCESS_REQUESTED to CERT_ACCESS_GRANTED
```

### <a name="ios-and-ipados"></a>Systemy iOS i iPadOS

Na urządzeniu z systemem iOS lub iPadOS certyfikat można wyświetlić w obszarze Profil zarządzania urządzeniami. Aby wyświetlić szczegółowe informacje o zainstalowanych certyfikatach, przejdź do szczegółów.

![Certyfikat systemu iOS](../protect/media/troubleshoot-scep-certificate-delivery/ios-certificate.png)

W [dzienniku debugowania systemu iOS](troubleshoot-scep-certificate-profiles.md#logs-for-ios-and-ipados-devices) można również znaleźć wpisy podobne do następujących:

```
Debug 18:30:53.691033 -0500 profiled Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACert&message=SCEP%20Authority\  
Debug 18:30:54.640644 -0500 profiled Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=SCEP%20Authority\ 
Debug 18:30:55.487908 -0500 profiled Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=PKIOperation&message=MIAGCSqGSIb3DQEHAqCAMIACAQExDzANBglghkgBZQMEAgMFADCABgkqhkiG9w0BBwGggCSABIIZfzCABgkqhkiG9w0BBwOggDCAAgEAMYIBgjCCAX4CAQAwZjBPMRUwEwYKCZImiZPyLGQBGRYFbG9jYWwxHDAaBgoJkiaJk/IsZAEZFgxmb3VydGhjb2ZmZWUxGDAWBgNVBAMTD0ZvdXJ0aENvZmZlZSBDQQITaAAAAAmaneVjEPlcTwAAAAAACTANBgkqhkiG9w0BAQEFAASCAQCqfsOYpuBToerQLkw/tl4tH9E+97TBTjGQN9NCjSgb78fF6edY0pNDU+PH4RB356wv3rfZi5IiNrVu5Od4k6uK4w0582ZM2n8NJFRY7KWSNHsmTIWlo/Vcr4laAtq5rw+CygaYcefptcaamkjdLj07e/Uk4KsetGo7ztPVjSEFwfRIfKv474dLDmPqp0ZwEWRQG 
Debug 18:30:57.285730 -0500 profiled Adding dependent Microsoft.Profiles.MDM to parent www.windowsintune.com.SCEP.ModelName=AC_51bad41f.../LogicalName_1892fe4c...;Hash=-912418295 in domain ManagedProfileToManagingProfile to system\ 
Default 18:30:57.320616 -0500 profiled Profile \'93www.windowsintune.com.SCEP.ModelName=AC_51bad41f.../LogicalName_1892fe4c...;Hash=-912418295\'94 installed.\ 
```

### <a name="windows"></a>Windows

Na urządzeniu z systemem Windows sprawdź, czy certyfikat został dostarczony:

- Uruchom plik **eventvwr.msc**, aby otworzyć Podgląd zdarzeń. Przejdź do obszaru **Dzienniki aplikacji i usług** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostic-Provider** > **Administrator** i poszukaj **zdarzenia 39**. To zdarzenie powinno mieć następujący opis ogólny: **SCEP: Certyfikat został zainstalowany pomyślnie.**

   ![Zdarzenie 39 w dzienniku aplikacji systemu Windows](../protect/media/troubleshoot-scep-certificate-delivery/device-app-log.png)

Aby wyświetlić certyfikat na urządzeniu, uruchom plik **certmgr.msc**, aby otworzyć konsolę MMC certyfikatów i sprawdzić, czy certyfikat główny i certyfikat protokołu SCEP zostały poprawnie zainstalowane na urządzeniu w magazynie osobistym:

   1. Wybierz pozycję **Certyfikaty (komputer lokalny)**  > **Zaufane główne urzędy certyfikacji** > **Certyfikaty** i sprawdź, czy obecny jest certyfikat główny z urzędu certyfikacji. Wartości w polach *Wystawione dla* i *Wystawiony przez* będą takie same.
   2. W konsoli MMC certyfikatów wybierz pozycję **Certyfikaty — bieżący użytkownik** > **Osobiste** > **Certyfikaty** i sprawdź, czy żądany certyfikat jest obecny i czy w polu *Wystawiony przez* znajduje się nazwa urzędu certyfikacji.

## <a name="troubleshoot-failures"></a>Rozwiązywanie problemów

### <a name="android"></a>Android

Aby rozwiązać problemy dotyczące tego kroku, przejrzyj błędy zarejestrowane w dzienniku OMA DM.

### <a name="ios-and-ipados"></a>Systemy iOS i iPadOS

Aby rozwiązać problemy dotyczące tego kroku, przejrzyj błędy zarejestrowane w dzienniku debugowania urządzeń.

### <a name="windows"></a>Windows

Aby rozwiązać problemy z certyfikatem, który nie został zainstalowany na urządzeniu, przejrzyj dziennik zdarzeń systemu Windows i poszukaj błędów, które sugerują problemy:

- Na urządzeniu uruchom plik **eventvwr.msc**, aby otworzyć Podgląd zdarzeń, a następnie wybierz pozycję **Dzienniki aplikacji i usług** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostic-Provider** > **Administrator**.

Błędy dotyczące dostarczania i instalowania certyfikatu na urządzeniu są zwykle powiązane z operacjami systemu Windows, a nie z usługą Intune.

## <a name="next-steps"></a>Następne kroki

Gdy certyfikat zostanie pomyślnie wdrożony na urządzeniu, ale usługa Intune nie zgłosi powodzenia, zobacz [Raportowanie usługi NDES w usłudze Intune](troubleshoot-scep-certificate-reporting.md) w celu rozwiązania problemów z raportowaniem.
