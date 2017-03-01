---
title: "Tworzenie niestandardowych profilów sieci VPN w usłudze Microsoft Intune"
titleSuffix: Intune Azure preview
description: "Konfiguracje niestandardowe umożliwiają tworzenie profilów sieci VPN w usłudze Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 132844bb1d1119390b7f55cca58cecbd5b8ee90a
ms.lasthandoff: 02/18/2017


---

# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a>Jak tworzyć niestandardowe profile sieci VPN w usłudze Microsoft Intune

## <a name="create-a-custom-configuration"></a>Tworzenie konfiguracji niestandardowej
Zasady konfiguracji niestandardowych usługi Intune umożliwiają tworzenie profilów sieci VPN dla następujących urządzeń:

* Urządzenia z systemem Android 4 i nowszym
* Zarejestrowane urządzenia z systemem Windows 8.1 lub nowszym
* Urządzenia z systemem Windows Phone 8.1 lub nowszym
* Zarejestrowane urządzenia z systemem Windows 10 Desktop 
* Urządzenia z systemem Windows 10 Mobile

Ten typ zasad może być przydatny, gdy standardowe zasady sieci VPN usługi Intune nie zawierają odpowiednich ustawień.

## <a name="to-create-a-custom-configuration-policy"></a>Aby utworzyć niestandardowe zasady konfiguracji:

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno pozycje **Więcej usług** > **Inne** > **Intune**.
3. W bloku **Intune** wybierz pozycję **Konfiguruj urządzenia**.
4. W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
5. W bloku profilów wybierz pozycję **Utwórz profil**.
6. W bloku **Utwórz profil** uzupełnij pola **Nazwa** i **Opis** odnoszące się do profilu sieci VPN.
7. Z listy rozwijanej **Platforma** wybierz platformę urządzenia, do której chcesz zastosować ustawienia sieci VPN. Obecnie dla ustawień niestandardowych urządzenia można wybrać jedną z następujących platform:
    - **Android**
    - **iOS** (konfiguracja przy użyciu pliku wyeksportowanego z narzędzia Apple Configurator).
    - **macOS** (konfiguracja przy użyciu pliku wyeksportowanego z narzędzia Apple Configurator).
    - **Windows Phone 8.1**
    - **Windows 10 lub nowszy**
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Niestandardowy**.
7. W bloku **Ustawienia niestandardowe OMA-URI** dla każdego ustawienia identyfikatora URI, które chcesz określić, wybierz przycisk **Dodaj**, podaj wymagane informacje, a następnie wybierz przycisk **OK**. Przykład:

   ![Okno dialogowe konfiguracji niestandardowej profilu VPN](./media/Intune_Add_VPN_URI.png)

4.  Po wprowadzeniu wszystkich potrzebnych ustawień identyfikatora URI wybierz przycisk **OK**, a następnie w bloku **Utwórz profil** wybierz przycisk **Utwórz**.

Profil zostanie utworzony i wyświetlony w bloku listy profilów.
Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](how-to-assign-device-profiles.md) (Sposoby przypisywania profilów urządzeń).

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




