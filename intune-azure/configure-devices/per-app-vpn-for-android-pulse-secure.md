---
title: "Profil sieci VPN dla aplikacji dla systemu Android — Pulse Secure | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: instrukcje dotyczące tworzenia profilu sieci VPN dla aplikacji dla urządzeń z systemem Android zarządzanych przez usługę Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: aeed271699656addce8f2bd8cde2a69ab8ede8f9
ms.lasthandoff: 02/16/2017


---

# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a>Korzystanie z niestandardowego profilu usługi Microsoft Intune w celu tworzenia profilu sieci VPN dla aplikacji dla urządzeń z systemem Android

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

W przypadku urządzeń z systemem Android 5.0 i nowszymi zarządzanych przez usługę Intune można utworzyć profil sieci VPN dla aplikacji. Najpierw utwórz profil sieci VPN, który używa typu połączenia Pulse Secure. Następnie utwórz niestandardowe zasady konfiguracji, które kojarzą profil sieci VPN z określonymi aplikacjami.

Po wdrożeniu zasad na urządzeniu z systemem Android lub w grupie użytkowników użytkownicy powinni uruchomić połączenie sieci VPN w programie PulseSecure. Program PulseSecure będzie wówczas zezwalać na używanie otwartego połączenia sieci VPN tylko dla ruchu z określonej aplikacji.

> [!NOTE]
>
> Dla tego profilu obsługiwany jest tylko typ połączenia Pulse Secure.


## <a name="step-1-create-a-vpn-profile"></a>Krok 1. Tworzenie profilu sieci VPN


1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno pozycje **Więcej usług** > **Inne** > **Intune**.
3. W bloku **Intune** wybierz pozycję **Konfiguruj urządzenia**.
2. W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
2. W bloku listy profilów wybierz pozycję **Utwórz profil**.
3. W bloku **Utwórz profil** uzupełnij pola **Nazwa** i **Opis** (opcjonalnie) odnoszące się do profilu sieci VPN.
4. Z listy rozwijanej **Platforma** wybierz pozycję **Android**.
5. Z listy rozwijanej **Typ profilu** wybierz pozycję **Sieć VPN**.
3. Wybierz kolejno pozycje **Ustawienia** > **Konfiguruj**, a następnie skonfiguruj profil sieci VPN zgodnie z ustawieniami przedstawionymi w artykułach [Konfigurowanie ustawień sieci VPN](how-to-configure-vpn-settings.md) i [Intune VPN settings for Android devices](vpn-for-android.md) (Ustawienia sieci VPN usługi Intune dla urządzeń z systemem Android).

Zanotuj nazwę profilu sieci VPN w celu użycia jej w następnym kroku. Przykład: **mój_profil_VPN_aplikacji**.

## <a name="step-2-create-a-custom-configuration-policy"></a>Krok 2. Tworzenie niestandardowych zasad konfiguracji

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno pozycje **Więcej usług** > **Inne** > **Intune**.
3. W bloku **Intune** wybierz pozycję **Konfiguruj urządzenia**.
2. W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
3. W bloku profilów kliknij pozycję **Utwórz profil**.
4. W bloku **Utwórz profil** uzupełnij pola **Nazwa** i **Opis** odnoszące się do profilu niestandardowego.
5. Z listy rozwijanej **Platforma** wybierz pozycję **Android**.
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Niestandardowy**.
7. Wybierz kolejno pozycje **Ustawienia** > **Konfiguruj**.
3. W bloku **Niestandardowe ustawienia OMA-URI** wybierz pozycję **Dodaj**.
    - Podaj nazwę ustawienia.
    - Dla pozycji **Typ danych** określ wartość **Ciąg**.
    - Dla pozycji **OMA-URI** określ następujący ciąg: **./Vendor/MSFT/VPN/Profile/*Nazwa*/PackageList**, gdzie wartość *Nazwa* jest nazwą profilu sieci VPN zanotowaną w kroku 1. W tym przykładzie byłby to ciąg **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList**.
    - W polu **Wartość** utwórz listę pakietów rozdzielonych średnikami do skojarzenia z profilem. Jeśli na przykład chcesz, aby program Excel i przeglądarka Google Chrome używały połączenia sieci VPN, podaj ciąg: **com.microsoft.office.excel;com.android.chrome**.

![Przykład niestandardowych zasad sieci VPN dla aplikacji systemu Android](./media/android_per_app_vpn_oma_uri.png)

### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Ustawianie listy aplikacji jako listy zabronionych lub listy dozwolonych (opcjonalne)
  Korzystając z wartości **BLACKLIST**, możesz określić listę aplikacji, które *nie* będą mogły korzystać z połączenia sieci VPN. Wszystkie pozostałe aplikacje będą nawiązywać połączenia za pośrednictwem sieci VPN.
Alternatywnie możesz użyć wartości **WHITELIST**, aby określić listę aplikacji, które *mogą* korzystać z połączenia sieci VPN. Aplikacje, które nie znajdują się na liście, nie będą nawiązywały połączeń za pośrednictwem sieci VPN.
  1.    W bloku **Niestandardowe ustawienia OMA-URI** wybierz pozycję **Dodaj**.
  2.    Podaj nazwę ustawienia.
  3.    Dla pozycji **Typ danych** określ wartość **Ciąg**.
  4.    Dla pozycji **OMA-URI** użyj ciągu **./Vendor/MSFT/VPN/Profile/*Nazwa*/Mode**, gdzie wartość *Nazwa* jest nazwą profilu sieci VPN zanotowaną w kroku 1. W tym przykładzie byłby to ciąg **./Vendor/MSFT/VPN/Profile/mój_profil_VPN_aplikacji/Mode**.
  5.    W polu **Wartość** podaj wartość **BLACKLIST** lub **WHITELIST**.



## <a name="step-3-assign-both-policies"></a>Krok 3: Przypisanie obu zasad

Postępuj zgodnie z instrukcjami zawartymi w artykule [How to assign device profiles](how-to-assign-device-profiles.md) (Sposoby przypisywania profilów urządzeń), aby przypisać oba profile do wymaganych użytkowników lub urządzeń.

