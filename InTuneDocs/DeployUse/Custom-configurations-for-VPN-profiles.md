---
# required metadata

title: Konfiguracje niestandardowe dla profilów sieci VPN | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Konfiguracje niestandardowe dla profilów sieci VPN

## Tworzenie konfiguracji niestandardowej
Konfiguracje niestandardowe umożliwiają tworzenie profilów sieci VPN w usłudze Intune. Aby utworzyć konfigurację niestandardową:

   1. W konsoli administracyjnej usługi Intune wybierz pozycje **Zasady** -> **Dodaj zasadę** -> *<Expand platform>* -> **Konfiguracja niestandardowa** -> **Utwórz zasady**.
   2. Podaj nazwę zasad.
   3. Dla każdego ustawienia identyfikatora URI kliknij pozycję **Dodaj** i podaj wymagane informacje. Przykład:

   ![Okno dialogowe konfiguracji niestandardowej profilu VPN](intune/media/Intune_Add_VPN_URI.png)

   4.  Po wprowadzeniu wszystkich ustawień identyfikatora URI kliknij pozycję **Zapisz zasady**, a następnie wdróż zasady.

## Wdrażanie zasad konfiguracji

1.  W obszarze roboczym **Zasady** wybierz zasady do wdrożenia, a następnie kliknij pozycję **Zarządzaj wdrożeniem**.

2.  W oknie dialogowym **Zarządzanie wdrażaniem** :

    -   **Aby wdrożyć zasady** — wybierz co najmniej jedną grupę, w której chcesz wdrożyć zasady, a następnie kliknij pozycje **Dodaj** &gt; **OK**.

    -   **Aby zamknąć okno dialogowe bez wdrażania** — kliknij przycisk **Anuluj**.

Po wybraniu wdrożonych zasad można wyświetlić więcej informacji dotyczących wdrożenia w dolnej części listy zasad.

##Przykład ustawień identyfikatora URI dla konfiguracji niestandardowej profilu sieci VPN
Poniżej przedstawiono przykładowe wpisy wartości identyfikatora URI umożliwiające utworzenie konfiguracji niestandardowej dla sieci VPN w fikcyjnej firmie o nazwie Contoso. Aby uzyskać więcej informacji, takich jak typ danych dla każdego wpisu, zobacz [VPNv2 CSP](https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776.aspx)

Native Contoso VPN (IKEv2):
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

vpn.contoso.com
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType

Ikev2
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType

SplitTunnel
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod

Eap
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration
&lt;EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;EapMethod&gt;&lt;Type xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;13&lt;/Type&gt;&lt;VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorId&gt;&lt;VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorType&gt;&lt;AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/AuthorId&gt;&lt;/EapMethod&gt;&lt;Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"&gt;&lt;Type&gt;13&lt;/Type&gt;&lt;EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"&gt;&lt;CredentialsSource&gt;&lt;CertificateStore&gt;&lt;SimpleCertSelection&gt;true&lt;/SimpleCertSelection&gt;&lt;/CertificateStore&gt;&lt;/CredentialsSource&gt;&lt;ServerValidation&gt;&lt;DisableUserPromptForServerValidation&gt;false&lt;/DisableUserPromptForServerValidation&gt;&lt;ServerNames&gt;&lt;/ServerNames&gt;&lt;/ServerValidation&gt;&lt;DifferentUsername&gt;false&lt;/DifferentUsername&gt;&lt;PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/PerformServerValidation&gt;&lt;AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/AcceptServerName&gt;&lt;/EapType&gt;&lt;/Eap&gt;&lt;/Config&gt;&lt;/EapHostConfig&gt;

**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal**
Prawda

**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials**
1

**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName**
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix**
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection**
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address**
10.0.0.0

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize**
8

**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn**
true

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id**
%PROGRAMFILES%\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id**
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id**
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id**
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id**
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

Aby uzyskać odpowiedzi na pytania dotyczące używania tych ustawień lub więcej szczegółów na temat ich działania, klienci powinni zapoznać się z dokumentacją CSP:
https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776(v=vs.85).aspx

## Ustawienia identyfikatora URI połączeń sieci VPN dla aplikacji systemu Android w programie PulseSecure
### NIESTANDARDOWY IDENTYFIKATOR URI DLA LISTY PAKIETÓW 
-  Typ danych = ciąg
-  OMA-URI = ./Vendor/MSFT/VPN/Profile/<Name>/PackageList 
-  Wartość = lista pakietów rozdzielonych ogranicznikami.
   - Ograniczniki: średnik (;), dwukropek (:), przecinek (,), pionowa kreska (|)

Przykłady: 
- com.android.chrome
- com.android.chrome;com.android.browser

### NIESTANDARDOWY IDENTYFIKATOR URI DLA TRYBU (OPCJONALNIE)
- Typ danych = ciąg
- OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode 

> Uwagi
> - Używaj tej samej *nazwy*, która została przypisana do niestandardowego profilu
> - Dopuszczalne wartości: *GLOBAL*, *WHITELIST*, *BLACKLIST*
> - Jeśli nie podano parametru PackageList (zgodność z poprzednimi wersjami profilów systemowych), wartość domyślna to *GLOBAL*
> - Jeśli podano parametr PackageList, wartość domyślna to *WHITELIST*


### Zobacz także
(Połączenia sieci VPN w usłudze Microsoft Intune)[vpn-connections-in-microsoft-intune.md]


<!--HONumber=May16_HO1-->


