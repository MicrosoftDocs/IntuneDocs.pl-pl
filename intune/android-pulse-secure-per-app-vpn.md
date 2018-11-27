---
title: Niestandardowy profil sieci VPN dla poszczególnych aplikacji dla systemu Android
titlesuffix: Microsoft Intune
description: Instrukcje dotyczące tworzenia profilu sieci VPN dla poszczególnych aplikacji dla urządzeń z systemem Android zarządzanych przez usługę Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 48f1227da6260217105120d31301f60b6e06110c
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52186022"
---
# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a>Korzystanie z niestandardowego profilu usługi Microsoft Intune w celu tworzenia profilu sieci VPN dla aplikacji dla urządzeń z systemem Android

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

W przypadku urządzeń z systemem Android 5.0 i nowszymi zarządzanych przez usługę Intune można utworzyć profil sieci VPN dla aplikacji. Najpierw utwórz profil sieci VPN, który używa typu połączenia Pulse Secure lub Citrix. Następnie utwórz niestandardowe zasady konfiguracji, które kojarzą profil sieci VPN z określonymi aplikacjami.

Po przypisaniu zasad w grupach użytkowników lub na urządzeniu z systemem Android użytkownicy powinni uruchomić klienta sieci VPN Pulse Secure lub Citrix. Klient sieci VPN będzie wówczas zezwalać na używanie otwartego połączenia sieci VPN tylko dla ruchu z określonych aplikacji.

> [!NOTE]
>
> Dla tego profilu obsługiwane są tylko typy połączenia Pulse Secure i Citrix.


## <a name="step-1-create-a-vpn-profile"></a>Krok 1. Tworzenie profilu sieci VPN


1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Konfiguracja urządzeń**.
2. W okienku **Konfiguracja urządzeń** w sekcji **Zarządzanie** wybierz pozycję **Profile**.
2. W okienku z listą profilów wybierz pozycję **Utwórz profil**.
3. W okienku **Tworzenie profilu** wprowadź wartość w polach **Nazwa** i **Opis** (opcjonalnie) dotyczących profilu sieci VPN.
4. Z listy rozwijanej **Platforma** wybierz pozycję **Android**.
5. Z listy rozwijanej **Typ profilu** wybierz pozycję **Sieć VPN**.
3. Wybierz kolejno pozycje **Ustawienia** > **Konfiguruj**, a następnie skonfiguruj profil sieci VPN zgodnie z ustawieniami przedstawionymi w artykułach [Konfigurowanie ustawień sieci VPN](vpn-settings-configure.md) i [Intune VPN settings for Android devices](vpn-settings-android.md) (Ustawienia sieci VPN usługi Intune dla urządzeń z systemem Android).

Zapisz **nazwę połączenia** — wartość określaną podczas tworzenia profilu sieci VPN. Będzie ona potrzebna w następnym kroku. Przykład: **mój_profil_VPN_aplikacji**.

## <a name="step-2-create-a-custom-configuration-policy"></a>Krok 2. Tworzenie niestandardowych zasad konfiguracji

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Konfiguracja urządzeń**.
2. W okienku **Konfiguracja urządzeń** w sekcji **Zarządzanie** wybierz pozycję **Profile**.
3. W okienku profilów kliknij pozycję **Utwórz profil**.
4. W okienku **Tworzenie profilu** wprowadź wartość w polach **Nazwa** i **Opis** dotyczących profilu niestandardowego.
5. Z listy rozwijanej **Platforma** wybierz pozycję **Android**.
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Niestandardowy**.
7. Wybierz kolejno pozycje **Ustawienia** > **Konfiguruj**.
3. W okienku **Niestandardowe ustawienia OMA-URI** wybierz pozycję **Dodaj**.
    - Podaj nazwę ustawienia.
    - Dla pozycji **OMA-URI** określ następujący ciąg: **./Vendor/MSFT/VPN/Profile/*Nazwa*/PackageList**, gdzie wartość *Nazwa* jest nazwą połączenia zanotowaną w kroku 1. W tym przykładzie byłby to ciąg **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList**.
    - Dla pozycji **Typ danych** określ wartość **Ciąg**.
    - W polu **Wartość** utwórz listę pakietów rozdzielonych średnikami do skojarzenia z profilem. Jeśli na przykład chcesz, aby program Excel i przeglądarka Google Chrome używały połączenia sieci VPN, podaj ciąg: **com.microsoft.office.excel;com.android.chrome**.

![Przykład niestandardowych zasad sieci VPN dla aplikacji systemu Android](./media/android_per_app_vpn_oma_uri.png)

### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Ustawianie listy aplikacji jako listy zabronionych lub listy dozwolonych (opcjonalne)
  Korzystając z wartości **BLACKLIST**, możesz określić listę aplikacji, które *nie* będą mogły korzystać z połączenia sieci VPN. Wszystkie pozostałe aplikacje nawiązują połączenia za pośrednictwem sieci VPN.
Alternatywnie możesz użyć wartości **WHITELIST**, aby określić listę aplikacji, które *mogą* korzystać z połączenia sieci VPN. Aplikacje, które nie znajdują się na liście, nie nawiązują połączeń za pośrednictwem sieci VPN.
  1.    W okienku **Niestandardowe ustawienia OMA-URI** wybierz pozycję **Dodaj**.
  2.    Podaj nazwę ustawienia.
  3.    Dla pozycji **OMA-URI** użyj ciągu ***./Vendor/MSFT/VPN/Profile/* Nazwa**/Mode, gdzie wartość *Nazwa* jest nazwą profilu sieci VPN zanotowaną w kroku 1. W tym przykładzie byłby to ciąg **./Vendor/MSFT/VPN/Profile/mój_profil_VPN_aplikacji/Mode**.
  4.    Dla pozycji **Typ danych** określ wartość **Ciąg**.
  5.    W polu **Wartość** podaj wartość **BLACKLIST** lub **WHITELIST**.



## <a name="step-3-assign-both-policies"></a>Krok 3: Przypisanie obu zasad

Postępuj zgodnie z instrukcjami zawartymi w artykule [How to assign device profiles](device-profile-assign.md) (Sposoby przypisywania profilów urządzeń), aby przypisać oba profile do wymaganych użytkowników lub urządzeń.
