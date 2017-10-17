---
title: "Konfiguracje niestandardowe dla profilów sieci VPN usługi Microsoft Intune"
description: "Konfiguracje niestandardowe umożliwiają tworzenie profilów sieci VPN w usłudze Intune."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 634a2b72f2f4ae1b3164b0f063aba4b73f05f1fb
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2017
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

Następnie [wdróż zasady](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy) w zwykły sposób.

## <a name="example-uri-settings"></a>Przykładowe ustawienia identyfikatorów URI

Te ustawienia umożliwiają utworzenie konfiguracji niestandardowej dla sieci VPN w fikcyjnej firmie o nazwie Contoso.
Aby uzyskać kompletne, szczegółowe informacje o wszystkich ustawieniach, których można użyć, zobacz [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776.aspx).

**Native Contoso VPN (IKEv2):**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

**vpn.contoso.com**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType

**Ikev2<br />** ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType

**SplitTunnel**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod

**Eap**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration
``` xml
<EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
   <EapMethod>
      <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type>
      <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId>
      <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType>
      <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId>
   </EapMethod>
   <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
      <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1">
         <Type>13</Type>
         <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1">
            <CredentialsSource>
               <CertificateStore>
                  <SimpleCertSelection>true</SimpleCertSelection>
               </CertificateStore>
            </CredentialsSource>
            <ServerValidation>
               <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation>
               <ServerNames></ServerNames>
            </ServerValidation>
            <DifferentUsername>false</DifferentUsername>
            <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
               false
            </PerformServerValidation>
            <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
               false
            </AcceptServerName>
         </EapType>
      </Eap>
   </Config>
</EapHostConfig>
```
**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal**<br />
Prawda

**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials**<br />
1

**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName**<br />
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix**<br />
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection**<br />
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address**<br />
10.0.0.0

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize**<br />
8

**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn**<br />
true

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id**<br />
%PROGRAMFILES%\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id**<br />
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id**<br />
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id**<br />
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id**<br />
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

Aby uzyskać odpowiedzi na pytania dotyczące używania tych ustawień lub więcej szczegółów na temat ich działania, klienci powinni zapoznać się z [dokumentacją dostawcy usług konfiguracji (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx).

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
