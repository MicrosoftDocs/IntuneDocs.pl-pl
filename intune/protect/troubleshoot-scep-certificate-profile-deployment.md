---
title: Rozwiązywanie problemów z wdrażaniem profilów certyfikatów protokołu SCEP na urządzeniach za pomocą usługi Microsoft Intune | Microsoft Docs
description: Rozwiązywanie problemów z wysyłaniem profilu certyfikatu protokołu SCEP do urządzenia za pomocą usługi Intune.
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
ms.openlocfilehash: 3dae74321b6825a1b94551addfd7621450fd8ae4
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "76916048"
---
# <a name="troubleshoot-deployment-of-a-scep-certificate-profile-to-devices-in-microsoft-intune"></a>Rozwiązywanie problemów z wdrażaniem profilu certyfikatu protokołu SCEP na urządzeniach w usłudze Microsoft Intune

Poniższe informacje pomagają w rozwiązywaniu problemów z wdrażaniem profilów certyfikatów prostego protokołu rejestrowania certyfikatów (SCEP, Simple Certificate Enrollment Protocol) za pomocą usługi Intune.

Ten artykuł dotyczy kroku 1 [omówienia przepływu komunikacji protokołu SCEP](troubleshoot-scep-certificate-profiles.md).


## <a name="android"></a>Android

Profile certyfikatów protokołu SCEP dla systemu Android przychodzą na urządzenie jako element SyncML i są rejestrowane w dzienniku [OMADM](troubleshoot-scep-certificate-profiles.md#logs-for-android-devices).

### <a name="validate-that-the-android-device-was-sent-the-policy"></a>Weryfikowanie, czy na urządzenie z systemem Android wysłano zasady

Aby sprawdzić, czy profil został wysłany na odpowiednie urządzenie, w [Centrum administracyjnym usługi Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję **Rozwiązywania problemów i pomoc techniczna** > **Rozwiązywanie problemów**.  W oknie *Rozwiązywanie problemów* dla pozycji **Przypisania** ustaw opcję **Profile konfiguracji**, a następnie zweryfikuj następujące konfiguracje:

1. Określ użytkownika, który powinien otrzymać profil certyfikatu protokołu SCEP.

2. Przejrzyj członkostwo w grupach użytkowników, aby upewnić się, że znajdują się oni w grupie zabezpieczeń użytej z profilem certyfikatu protokołu SCEP.

3. Przejrzyj czas ostatniego zaewidencjonowania urządzenia w usłudze Intune.

![Weryfikowanie zasad](../protect/media/troubleshoot-scep-certificate-profile-deployment/validate-policy-android.png)

### <a name="validate-the-policy-reached-the-android-device"></a>Weryfikowanie, czy zasady dotarły na urządzenie z systemem Android

Przejrzyj [dziennik programu OMADM urządzeń](troubleshoot-scep-certificate-profiles.md#logs-for-android-devices). Wyszukaj wpisy podobne do następujących, które są rejestrowane, gdy urządzenie otrzymuje profil z usługi Intune:

```
Time    VERB    Event     com.microsoft.omadm.syncml.SyncmlSession     9595        9    <?xml version="1.0" encoding="utf-8"?><SyncML xmlns="SYNCML:SYNCML1.2"><SyncHdr><VerDTD>1.2</VerDTD><VerProto>DM/1.2</VerProto><SessionID>1</SessionID><MsgID>6</MsgID><Target><LocURI>urn:uuid:UUID</LocURI></Target><Source><LocURI>https://a.manage.microsoft.com/devicegatewayproxy/AndroidHandler.ashx</LocURI></Source><Meta><MaxMsgSize xmlns="syncml:metinf">524288</MaxMsgSize></Meta></SyncHdr><SyncBody><Status><CmdID>1</CmdID><MsgRef>6</MsgRef><CmdRef>0</CmdRef><Cmd>SyncHdr</Cmd><Data>200</Data></Status><Replace><CmdID>2</CmdID><Item><Target><LocURI>./Vendor/MSFT/Scheduler/IntervalDurationSeconds</LocURI></Target><Meta><Format xmlns="syncml:metinf">int</Format><Type xmlns="syncml:metinf">text/plain</Type></Meta><Data>28800</Data></Item></Replace><Replace><CmdID>3</CmdID><Item><Target><LocURI>./Vendor/MSFT/EnterpriseAppManagement/EnterpriseIDs</LocURI></Target><Data>contoso.onmicrosoft.com</Data></Item></Replace><Exec><CmdID>4</CmdID><Item><Target><LocURI>./Vendor/MSFT/EnterpriseAppManagement/EnterpriseApps/ClearNotifications</LocURI></Target></Item></Exec><Add><CmdID>5</CmdID><Item><Target><LocURI>./Vendor/MSFT/CertificateStore/Root/{GUID}/EncodedCertificate</LocURI></Target><Data>Data</Data></Item></Add><Add><CmdID>6</CmdID><Item><Target><LocURI>./Vendor/MSFT/CertificateStore/Enroll/ModelName=AC_51…%2FLogicalName_39907…%3BHash=-1518303401/Install</LocURI></Target><Meta><Format xmlns="syncml:metinf">xml</Format><Type xmlns="syncml:metinf">text/plain</Type></Meta><Data>&lt;CertificateRequest&gt;&lt;ConfigurationParametersDocument&gt;&amp;lt;ConfigurationParameters xmlns="http://schemas.microsoft.com/SystemCenterConfigurationManager/2012/03/07/CertificateEnrollment/ConfigurationParameters"&amp;gt;&amp;lt;ExpirationThreshold&amp;gt;20&amp;lt;/ExpirationThreshold&amp;gt;&amp;lt;RetryCount&amp;gt;3&amp;lt;/RetryCount&amp;gt;&amp;lt;RetryDelay&amp;gt;1&amp;lt;/RetryDelay&amp;gt;&amp;lt;TemplateName /&amp;gt;&amp;lt;SubjectNameFormat&amp;gt;{ID}&amp;lt;/SubjectNameFormat&amp;gt;&amp;lt;SubjectAlternativeNameFormat&amp;gt;{ID}&amp;lt;/SubjectAlternativeNameFormat&amp;gt;&amp;lt;KeyStorageProviderSetting&amp;gt;0&amp;lt;/KeyStorageProviderSetting&amp;gt;&amp;lt;KeyUsage&amp;gt;32&amp;lt;/KeyUsage&amp;gt;&amp;lt;KeyLength&amp;gt;2048&amp;lt;/KeyLength&amp;gt;&amp;lt;HashAlgorithms&amp;gt;&amp;lt;HashAlgorithm&amp;gt;SHA-1&amp;lt;/HashAlgorithm&amp;gt;&amp;lt;HashAlgorithm&amp;gt;SHA-2&amp;lt;/HashAlgorithm&amp;gt;&amp;lt;/HashAlgorithms&amp;gt;&amp;lt;NDESUrls&amp;gt;&amp;lt;NDESUrl&amp;gt;https://breezeappproxy-contoso.msappproxy.net/certsrv/mscep/mscep.dll&amp;lt;/NDESUrl&amp;gt;&amp;lt;/NDESUrls&amp;gt;&amp;lt;CAThumbprint&amp;gt;{GUID}&amp;lt;/CAThumbprint&amp;gt;&amp;lt;ValidityPeriod&amp;gt;2&amp;lt;/ValidityPeriod&amp;gt;&amp;lt;ValidityPeriodUnit&amp;gt;Years&amp;lt;/ValidityPeriodUnit&amp;gt;&amp;lt;EKUMapping&amp;gt;&amp;lt;EKUMap&amp;gt;&amp;lt;EKUName&amp;gt;Client Authentication&amp;lt;/EKUName&amp;gt;&amp;lt;EKUOID&amp;gt;1.3.6.1.5.5.7.3.2&amp;lt;/EKUOID&amp;gt;&amp;lt;/EKUMap&amp;gt;&amp;lt;/EKUMapping&amp;gt;&amp;lt;/ConfigurationParameters&amp;gt;&lt;/ConfigurationParametersDocument&gt;&lt;RequestParameters&gt;&lt;CertificateRequestToken&gt;PENlcnRFbn... Hash: 1,010,143,298&lt;/CertificateRequestToken&gt;&lt;SubjectName&gt;CN=name&lt;/SubjectName&gt;&lt;Issuers&gt;CN=FourthCoffee CA; DC=fourthcoffee; DC=local&lt;/Issuers&gt;&lt;SubjectAlternativeName&gt;&lt;SANs&gt;&lt;SAN NameFormat="ID" AltNameType="2" OID="{OID}"&gt;&lt;/SAN&gt;&lt;SAN NameFormat="ID" AltNameType="11" OID="{OID}"&gt;john@contoso.onmicrosoft.com&lt;/SAN&gt;&lt;/SANs&gt;&lt;/SubjectAlternativeName&gt;&lt;NDESUrl&gt;https://breezeappproxy-contoso.msappproxy.net/certsrv/mscep/mscep.dll&lt;/NDESUrl&gt;&lt;/RequestParameters&gt;&lt;/CertificateRequest&gt;</Data></Item></Add><Get><CmdID>7</CmdID><Item><Target><LocURI>./Vendor/MSFT/CertificateStore/SCEP</LocURI></Target></Item></Get><Add><CmdID>8</CmdID><Item><Target><LocURI>./Vendor/MSFT/GCM</LocURI></Target><Data>Data</Data></Item></Add><Replace><CmdID>9</CmdID><Item><Target><LocURI>./Vendor/MSFT/GCM</LocURI></Target><Data>Data</Data></Item></Replace><Get><CmdID>10</CmdID><Item><Target><LocURI>./Vendor/MSFT/NodeCache/SCConfigMgr</LocURI></Target></Item></Get><Get><CmdID>11</CmdID><Item><Target><LocURI>./Vendor/MSFT/NodeCache/SCConfigMgr/CacheVersion</LocURI></Target></Item></Get><Get><CmdID>12</CmdID><Item><Target><LocURI>./Vendor/MSFT/NodeCache/SCConfigMgr/ChangedNodes</LocURI></Target></Item></Get><Get><CmdID>13</CmdID><Item><Target><LocURI>./DevDetail/Ext/Microsoft/LocalTime</LocURI></Target></Item></Get><Get><CmdID>14</CmdID><Item><Target><LocURI>./Vendor/MSFT/DeviceLock/DevicePolicyManager/IsActivePasswordSufficient</LocURI></Target></Item></Get><Get><CmdID>15</CmdID><Item><Target><LocURI>./Vendor/MSFT/WorkProfileLock/DevicePolicyManager/IsActivePasswordSufficient</LocURI></Target></Item></Get><Final /></SyncBody></SyncML>
```

Przykłady wpisów kluczy:

- `ModelName=AC_51bad41f-3854-4eb5-a2f2-0f7a94034ee8%2FLogicalName_39907e78_e61b_4730_b9fa_d44a53e4111c%3BHash=-1518303401`
- `NDESUrls&amp;gt;&amp;lt;NDESUrl&amp;gt;https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll&amp;lt;/NDESUrl&amp;gt;&amp;lt;/NDESUrls`

## <a name="ios-and-ipados"></a>Systemy iOS i iPadOS

### <a name="validate-that-the-ios-or-ipados-device-was-sent-the-policy"></a>Weryfikowanie, czy na urządzenie z systemem iOS lub iPadOS wysłano zasady

Aby sprawdzić, czy profil został wysłany na odpowiednie urządzenie, w [Centrum administracyjnym usługi Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję **Rozwiązywania problemów i pomoc techniczna** > **Rozwiązywanie problemów**.  W oknie *Rozwiązywanie problemów* dla pozycji **Przypisania** ustaw opcję **Profile konfiguracji**, a następnie zweryfikuj następujące konfiguracje:

1. Określ użytkownika, który powinien otrzymać profil certyfikatu protokołu SCEP.

2. Przejrzyj członkostwo w grupach użytkowników, aby upewnić się, że znajdują się oni w grupie zabezpieczeń użytej z profilem certyfikatu protokołu SCEP.

3. Przejrzyj czas ostatniego zaewidencjonowania urządzenia w usłudze Intune.

![Weryfikowanie zasad](../protect/media/troubleshoot-scep-certificate-profile-deployment/validate-policy-ios.png)

### <a name="validate-the-policy-reached-the-ios-or-ipados-device"></a>Weryfikowanie, czy zasady dotarły na urządzenie z systemem iOS lub iPadOS

Przejrzyj [dziennik debugowania urządzeń](troubleshoot-scep-certificate-profiles.md#logs-for-ios-and-ipados-devices). Wyszukaj wpisy podobne do następujących, które są rejestrowane, gdy urządzenie otrzymuje profil z usługi Intune:

```
debug    18:30:54.638009 -0500    profiled    Adding dependent ModelName=AC_51bad41f.../LogicalName_1892fe4c...;Hash=-912418295 to parent 636572740000000000000012 in domain PayloadDependencyDomainCertificate to system\
```

Przykłady wpisów kluczy:

- `ModelName=AC_51bad41f.../LogicalName_1892fe4c...;Hash=-912418295`
- `PayloadDependencyDomainCertificate`

## <a name="windows"></a>Windows

### <a name="validate-that-the-windows-device-was-sent-the-policy"></a>Weryfikowanie, czy na urządzenie z systemem Windows wysłano zasady

Aby sprawdzić, czy profil został wysłany na odpowiednie urządzenie, w [Centrum administracyjnym usługi Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)[Centrum administracyjnym usługi Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję **Rozwiązywania problemów i pomoc techniczna** > **Rozwiązywanie problemów**.  W oknie *Rozwiązywanie problemów* dla pozycji **Przypisania** ustaw opcję **Profile konfiguracji**, a następnie zweryfikuj następujące konfiguracje:

1. Określ użytkownika, który powinien otrzymać profil certyfikatu protokołu SCEP.

2. Przejrzyj członkostwo w grupach użytkowników, aby upewnić się, że znajdują się oni w grupie zabezpieczeń użytej z profilem certyfikatu protokołu SCEP.

3. Przejrzyj czas ostatniego zaewidencjonowania urządzenia w usłudze Intune.

![Weryfikowanie zasad](../protect/media/troubleshoot-scep-certificate-profile-deployment/validate-policy-windows.png)

### <a name="validate-the-policy-reached-the-windows-device"></a>Weryfikowanie, czy zasady dotarły na urządzenie z systemem Windows

Dostarczenie zasad dla profilu jest rejestrowane na urządzeniu z systemem Windows w dzienniku *DeviceManagement-Enterprise-Diagnostics-Provider* > **Administrator** z identyfikatorem zdarzenia **306**. 

Aby otworzyć dziennik:

1. Na urządzeniu uruchom plik **eventvwr.msc**, aby otworzyć Podgląd zdarzeń systemu Windows.

2. Rozwiń pozycję **Dzienniki aplikacji i usług** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostic-Provider** > **Administrator**.

3. Wyszukaj zdarzenie **306**, które przypomina poniższy przykład:

   ```
   Event ID:      306
   Task Category: None
   Level:         Information
   User:          SYSTEM
   Computer:      <Computer Name>
   Description:
   SCEP: CspExecute for UniqueId : (ModelName_<ModelName>_LogicalName_<LogicalName>_Hash_<Hash>) InstallUserSid : (<UserSid>) InstallLocation : (user) NodePath : (clientinstall)  KeyProtection: (0x2) Result : (Unknown Win32 Error code: 0x2ab0003).
   ```

   Kod błędu **0x2ab0003** oznacza **DM_S_ACCEPTED_FOR_PROCESSING**.

   Kod błędu niepowodzenia może wskazywać, o jaki problem chodzi.

## <a name="next-steps"></a>Następne kroki

Jeśli profil zostanie dostarczony na urządzenie, następnym krokiem jest przejrzenie [komunikacji urządzenia z serwerem usługi NDES](troubleshoot-scep-certificate-device-to-ndes.md).
