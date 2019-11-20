---
title: Niestandardowy profil sieci VPN dla poszczególnych aplikacji dla systemu Android
titleSuffix: Microsoft Intune
description: Instrukcje dotyczące tworzenia profilu sieci VPN dla poszczególnych aplikacji dla urządzeń z systemem Android zarządzanych przez usługę Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3683d2aeada791c6ec827e915e02365a336e6045
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059676"
---
# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a>Korzystanie z niestandardowego profilu usługi Microsoft Intune w celu tworzenia profilu sieci VPN dla aplikacji dla urządzeń z systemem Android

[!INCLUDE[azure_portal](../includes/azure_portal.md)]

W przypadku urządzeń z systemem Android 5.0 i nowszymi zarządzanych przez usługę Intune można utworzyć profil sieci VPN dla aplikacji. Najpierw utwórz profil sieci VPN, który używa typu połączenia Pulse Secure lub Citrix. Następnie utwórz niestandardowe zasady konfiguracji, które kojarzą profil sieci VPN z określonymi aplikacjami.

Po przypisaniu zasad w grupach użytkowników lub na urządzeniu z systemem Android użytkownicy powinni uruchomić klienta sieci VPN Pulse Secure lub Citrix. Klient sieci VPN będzie wówczas zezwalać na używanie otwartego połączenia sieci VPN tylko dla ruchu z określonych aplikacji.

> [!NOTE]
>
> Dla tego profilu obsługiwane są tylko typy połączenia Pulse Secure i Citrix.

## <a name="step-1-create-a-vpn-profile"></a>Krok 1. Tworzenie profilu sieci VPN

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia** > **Profile konfiguracji** > **Utwórz profil**.
3. Wprowadź następujące właściwości:

    - **Nazwa**: Wprowadź opisową nazwę profilu. Nadaj nazwę profilom, aby można było je później łatwo rozpoznać. Na przykład dobra nazwa profilu to **Profil sieci VPN na aplikację dla systemu Android w całej firmie**.
    - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: — wybierz opcję **Android**.
    - **Typ profilu**: Wybierz pozycję **Sieć VPN**.

4. Wybierz kolejno pozycje **Ustawienia** > **Konfiguruj**, a następnie skonfiguruj profil sieci VPN zgodnie z ustawieniami przedstawionymi w artykułach [Konfigurowanie ustawień sieci VPN](vpn-settings-configure.md) i [Intune VPN settings for Android devices](vpn-settings-android.md) (Ustawienia sieci VPN usługi Intune dla urządzeń z systemem Android).

Zapisz **nazwę połączenia** — wartość określaną podczas tworzenia profilu sieci VPN. Będzie ona potrzebna w następnym kroku. Przykład: **mój_profil_VPN_aplikacji**.

## <a name="step-2-create-a-custom-configuration-policy"></a>Krok 2: Tworzenie niestandardowych zasad konfiguracji

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia** > **Profile konfiguracji** > **Utwórz profil**.
3. Wprowadź następujące właściwości:

    - **Nazwa**: Wprowadź opisową nazwę profilu niestandardowego. Nadaj nazwę profilom, aby można było je później łatwo rozpoznać. Na przykład dobra nazwa profilu to **Niestandardowy profil sieci VPN dla systemu Android i identyfikatora OMA-URI w całej firmie**.
    - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: — wybierz opcję **Android**.
    - **Typ profilu**: wybierz pozycję **Niestandardowy**.

4. Wybierz kolejno pozycje **Ustawienia** > **Konfiguruj**.
5. W okienku **Niestandardowe ustawienia OMA-URI** wybierz pozycję **Dodaj**.
    - **Nazwa**: wprowadź nazwę ustawienia.
    - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **OMA-URI**: wprowadź ciąg `./Vendor/MSFT/VPN/Profile/*Name*/PackageList`, w którym *Name* (Nazwa) jest nazwą połączenia zanotowaną w kroku 1. W tym przykładzie ciąg to `./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList`.
    - **Typ danych**: wprowadź wartość **Ciąg**.
    - **Wartość**: wprowadź listę pakietów rozdzielonych średnikami do skojarzenia z profilem. Jeśli na przykład chcesz, aby program Excel i przeglądarka Google Chrome używały połączenia sieci VPN, wprowadź ciąg `com.microsoft.office.excel;com.android.chrome`.

![Przykład niestandardowych zasad sieci VPN dla aplikacji systemu Android](./media/android-pulse-secure-per-app-vpn/android_per_app_vpn_oma_uri.png)

### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Ustawianie listy aplikacji jako listy zabronionych lub listy dozwolonych (opcjonalne)

Korzystając z wartości **BLACKLIST**, możesz wprowadzić listę aplikacji, które *nie* będą mogły korzystać z połączenia sieci VPN. Wszystkie pozostałe aplikacje nawiązują połączenia za pośrednictwem sieci VPN. Możesz również użyć wartości **WHITELIST**, aby wprowadzić listę aplikacji, które *mogą* korzystać z połączenia sieci VPN. Aplikacje, które nie znajdują się na liście, nie nawiązują połączeń za pośrednictwem sieci VPN.

1. W okienku **Niestandardowe ustawienia OMA-URI** wybierz pozycję **Dodaj**.
2. Podaj nazwę ustawienia.
3. W polu **OMA-URI** wprowadź ciąg `./Vendor/MSFT/VPN/Profile/*Name*/Mode`, gdzie *Name* (nazwa) jest nazwą profilu sieci VPN zanotowaną w kroku 1. W naszym przykładzie ciąg to `./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode`.
4. W polu **Typ danych** wprowadź wartość **Ciąg**.
5. W polu **Wartość** wprowadź wartość **BLACKLIST** lub **WHITELIST**.

## <a name="step-3-assign-both-policies"></a>Krok 3: Przypisywanie obu zasad

[Przypisz obydwa profile urządzeń](device-profile-assign.md) do wymaganych użytkowników lub urządzeń.
