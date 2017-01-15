---
title: "Konfiguracje niestandardowe dla profilów sieci VPN usługi Microsoft Intune | Microsoft Docs"
description: "Konfiguracje niestandardowe umożliwiają tworzenie profilów sieci VPN w usłudze Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f2b364b2c57adab33df2a8e6b34c1f30c02988d3
ms.openlocfilehash: 9dbb44981c1525e6137dd8a469b1582731ee9719


---

# <a name="custom-configurations-for-microsoft-intune-vpn-profiles"></a>Konfiguracje niestandardowe dla profilów sieci VPN usługi Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="create-a-custom-configuration"></a>Tworzenie konfiguracji niestandardowej
Zasady konfiguracji niestandardowych usługi Intune umożliwiają tworzenie profilów sieci VPN dla następujących urządzeń:

* Urządzenia z systemem Android 4 i nowszym
* Urządzenia z programem Android for Work
* Zarejestrowane urządzenia z systemem Windows 8.1 lub nowszym
* Urządzenia z systemem Windows Phone 8.1 lub nowszym
* Zarejestrowane urządzenia z systemem Windows 10 Desktop 
* Urządzenia z systemem Windows 10 Mobile

Ten typ zasad może być przydatny, gdy standardowe zasady sieci VPN usługi Intune nie zawierają odpowiednich ustawień.

## <a name="to-create-a-custom-configuration-policy"></a>Aby utworzyć niestandardowe zasady konfiguracji:

   1. W [konsoli administracyjnej usługi Intune](https://manage.microsoft.com) wybierz pozycję **Zasady** > **Dodaj zasady** > *Rozwiń platformę* > **Konfiguracja niestandardowa** > **Utwórz zasady**.
   2. Podaj nazwę zasad.
   3. Dla każdego ustawienia identyfikatora URI, które chcesz określić, wybierz pozycję **Dodaj** i podaj wymagane informacje. Przykład:

   ![Okno dialogowe konfiguracji niestandardowej profilu VPN](./media/Intune_Add_VPN_URI.png)

   4.  Po wprowadzeniu wszystkich ustawień identyfikatora URI wybierz pozycję **Zapisz zasady**, a następnie wdróż zasady.

Następnie [wdróż zasady](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy) w zwykły sposób.

## <a name="example-uri-settings"></a>Przykładowe ustawienia identyfikatorów URI

Te ustawienia umożliwiają utworzenie konfiguracji niestandardowej dla sieci VPN w fikcyjnej firmie o nazwie Contoso.
Aby uzyskać kompletne, szczegółowe informacje o wszystkich ustawieniach, których można użyć, zobacz [VPNv2 CSP](https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776.aspx).

Native Contoso VPN (IKEv2): ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

vpn.contoso.com ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType

Ikev2 ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType

SplitTunnel ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod

Eap ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration &lt;EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;EapMethod&gt;&lt;Type xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;13&lt;/Type&gt;&lt;VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorId&gt;&lt;VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorType&gt;&lt;AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/AuthorId&gt;&lt;/EapMethod&gt;&lt;Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"&gt;&lt;Type&gt;13&lt;/Type&gt;&lt;EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"&gt;&lt;CredentialsSource&gt;&lt;CertificateStore&gt;&lt;SimpleCertSelection&gt;true&lt;/SimpleCertSelection&gt;&lt;/CertificateStore&gt;&lt;/CredentialsSource&gt;&lt;ServerValidation&gt;&lt;DisableUserPromptForServerValidation&gt;false&lt;/DisableUserPromptForServerValidation&gt;&lt;ServerNames&gt;&lt;/ServerNames&gt;&lt;/ServerValidation&gt;&lt;DifferentUsername&gt;false&lt;/DifferentUsername&gt;&lt;PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/PerformServerValidation&gt;&lt;AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/AcceptServerName&gt;&lt;/EapType&gt;&lt;/Eap&gt;&lt;/Config&gt;&lt;/EapHostConfig&gt;

**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal** True

**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials** 1

**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address** 10.0.0.0

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize** 8

**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn** true

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id** %PROGRAMFILES%\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id** %PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id** Microsoft.MicrosoftEdge_8wekyb3d8bbwe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id** %PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id** Microsoft.MicrosoftEdge_8wekyb3d8bbwe

Aby uzyskać odpowiedzi na pytania dotyczące używania tych ustawień lub więcej szczegółów na temat ich działania, klienci powinni zapoznać się z dokumentacją dostawcy usług konfiguracji: https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776(v=vs.85).aspx.

## <a name="uri-settings-for-android-per-app-vpn-on-pulsesecure"></a>Ustawienia identyfikatora URI połączeń sieci VPN dla aplikacji systemu Android w programie PulseSecure
### <a name="custom-uri-for-package-list"></a>NIESTANDARDOWY IDENTYFIKATOR URI DLA LISTY PAKIETÓW
-  Typ danych = ciąg
-  OMA-URI = ./Vendor/MSFT/VPN/Profile/Name/PackageList
-  Wartość = lista pakietów rozdzielonych ogranicznikami.
   - Ograniczniki: średnik (;), dwukropek (:), przecinek (,), pionowa kreska (|)

Przykłady:
- com.android.chrome
- com.android.chrome;com.android.browser

### <a name="custom-uri-for-mode-optional"></a>NIESTANDARDOWY IDENTYFIKATOR URI DLA TRYBU (OPCJONALNIE)
- Typ danych = ciąg
- OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode

> Uwagi
> - Używaj tej samej *nazwy*, która została przypisana do niestandardowego profilu
> - Dopuszczalne wartości: *GLOBAL*, *WHITELIST*, *BLACKLIST*
> - Jeśli nie podano parametru PackageList (zgodność z poprzednimi wersjami profilów systemowych), wartość domyślna to *GLOBAL*
> - Jeśli podano parametr PackageList, wartość domyślna to *WHITELIST*


### <a name="see-also"></a>Zobacz także
[Połączenia VPN w usłudze Microsoft Intune](vpn-connections-in-microsoft-intune.md)



<!--HONumber=Dec16_HO3-->


