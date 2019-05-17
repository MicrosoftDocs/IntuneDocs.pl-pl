---
title: Tworzenie profilów urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodaj lub skonfiguruj profil konfiguracji urządzenia w usłudze Microsoft Intune. Wybierz typ platformy, skonfiguruj ustawienia i dodaj tag zakresu.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/03/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 08c6ece37a4ff6eceaa4df735f365453a4bc7d88
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59570406"
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Tworzenie profilu urządzenia w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Profile urządzeń umożliwiają dodawanie i konfigurowanie ustawień, a następnie wypychanie tych ustawień do urządzeń w organizacji. Dalsze szczegóły, w tym opis możliwych do wykonania czynności, można znaleźć w temacie [Apply features and settings on your devices using device profiles](device-profiles.md) (Stosowanie funkcji i ustawień na urządzeniach przy użyciu profilów urządzeń).

W tym artykule:

- Znajduje się lista czynności wymaganych do utworzenia profilu.
- Przedstawiono sposób dodawania tagu zakresu w celu „filtrowania” profilu.
- Znajduje się lista czasów cykli odświeżania zaewidencjonowania, gdy urządzenia otrzymują profile i wszelkie aktualizacje profilów.

## <a name="create-the-profile"></a>Tworzenie profilu

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, wpisz nazwę usługi **Intune** w filtrze, a następnie wybierz pozycję **Intune**.

2. Wybierz pozycję **Konfiguracja urządzenia**. Do wyboru są następujące opcje:

    - **Omówienie**: lista stanów profilów oraz dodatkowe szczegółowe informacje o profilach przypisanych do użytkowników i urządzeń.
    - **Zarządzanie**: tworzenie profili urządzeń, przekazywanie niestandardowych [skryptów programu PowerShell](intune-management-extension.md) do uruchamiania w profilu i dodawanie planów danych do urządzeń korzystających z karty [eSIM](esim-device-configuration.md).
    - **Monitorowanie**: sprawdzanie stanu profilu (powodzenie lub niepowodzenie) oraz wyświetlanie dzienników dotyczących profili.
    - **Instalator**: dodawanie urzędu certyfikacji SCEP lub PFX albo włączanie [zarządzania wydatkami telekomunikacyjnymi](telecom-expenses-monitor.md) w profilu.

3. Wybierz pozycję **Profile**  >  **Utwórz profil**. Wprowadź następujące właściwości:

   - **Nazwa**: Wprowadź opisową nazwę profilu. Nadaj nazwę profilom, aby można było je później łatwo rozpoznać. Na przykład dobra nazwa profilu to **Profil poczty e-mail WP dla całej firmy**.
   - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
   - **Platforma**: Wybierz platformę urządzeń. Dostępne opcje:  

       - **Android**
       - **Android enterprise**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 lub nowszy**
       - **Windows 10 lub nowszy**

   - **Typ profilu**: Wybierz typ ustawień, który chcesz utworzyć. Wyświetlana lista zależy od wybranej **platformy**.
   - **Ustawienia**: Ustawienia poszczególnych typów profilów opisano w następujących artykułach:

       - [Szablony administracyjne](administrative-templates-windows.md)
       - [Niestandardowe](custom-settings-configure.md)
       - [Optymalizacja dostarczania](delivery-optimization-windows.md)
       - [Funkcje urządzenia](device-features-configure.md)
       - [Ograniczenia dotyczące urządzeń](device-restrictions-configure.md)
       - [Uaktualnianie wersji i przełącznik trybów](edition-upgrade-configure-windows-10.md)
       - [Edukacja](education-settings-configure.md)
       - [Poczta e-mail](email-settings-configure.md)
       - [Program Endpoint Protection](endpoint-protection-configure.md)
       - [Identity Protection](identity-protection-configure.md)  
       - [Kiosk](kiosk-settings.md)
       - [Certyfikat PKCS](certficates-pfx-configure.md)
       - [Certyfikat SCEP](certificates-scep-configure.md)
       - [Zaufany certyfikat](certificates-configure.md)
       - [Zasady aktualizacji](software-updates-ios.md)
       - [VPN](vpn-settings-configure.md)
       - [Wi-Fi](wi-fi-settings-configure.md)
       - [Zaawansowana ochrona przed zagrożeniami w usłudze Windows Defender](advanced-threat-protection.md)
       - [Rozwiązanie Windows Information Protection](windows-information-protection-configure.md)

     Jeśli na przykład wybierzesz platformę **iOS**, opcje typu profilu będą wyglądać podobnie do następującego profilu:

     ![Tworzenie profilu systemu iOS w usłudze Intune](./media/create-device-profile.png)

4. Po zakończeniu wybierz pozycję **OK**  >  **Utwórz**, aby zapisać zmiany. Profil zostanie utworzony i wyświetlony na liście.

## <a name="scope-tags"></a>Tagi zakresu

Po dodaniu ustawień możesz również dodać tag zakresu do profilu. Tagi zakresu umożliwiają przypisywanie i filtrowanie zasad do określonych grup, takich jak pracownicy działu kadr lub wszyscy pracownicy w stanie Północna Karolina w USA.

Więcej informacji na temat tagów zakresu i czynności możliwych do wykonania można znaleźć w artykule [Use RBAC and scope tags for distributed IT](scope-tags.md) (Używanie kontroli RBAC i tagów zakresu w rozproszonej infrastrukturze informatycznej).

### <a name="add-a-scope-tag"></a>Dodawanie tagu zakresu

1. Wybierz pozycję **Zakres (tagi)**.
2. Wybierz pozycję **Dodaj**, aby utworzyć nowy tag zakresu. Możesz również wybrać istniejący tag zakresu z listy.
3. Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="refresh-cycle-times"></a>Czasy cyklu odświeżania

Usługa Intune używa następujących cykli odświeżania, aby wyszukiwać aktualizacje profilów konfiguracji:

| Platforma | Cykl odświeżania|
| --- | --- |
| iOS | Co 6 godzin |
| macOS | Co 6 godzin |
| Android | Co 8 godzin |
| Komputery z systemem Windows 10 zarejestrowane jako urządzenia | Co 8 godzin |
| Windows Phone | Co 8 godzin |
| Windows 8.1 | Co 8 godzin |

Jeśli urządzenie zostało ostatnio zarejestrowane, ewidencjonowanie jest uruchamiane częściej:

| Platforma | Częstotliwość |
| --- | --- |
| iOS | Co 15 minut przez 6 godzin, a następnie co 6 godzin |  
| macOS | Co 15 minut przez 6 godzin, a następnie co 6 godzin | 
| Android | Co 3 minuty przez 15 minut, następnie co 15 minut przez 2 godziny, a następnie co 8 godzin | 
| Komputery z systemem Windows 10 zarejestrowane jako urządzenia | Co 3 minuty przez 30 minut, a następnie co 8 godzin | 
| Windows Phone | Co 5 minut przez 15 minut, następnie co 15 minut przez 2 godziny, a następnie co 8 godzin | 
| Windows 8.1 | Co 5 minut przez 15 minut, następnie co 15 minut przez 2 godziny, a następnie co 8 godzin | 

W dowolnym momencie użytkownicy mogą otwierać aplikację Portal firmy i synchronizować urządzenie, aby natychmiast wyszukiwać aktualizacje profilów.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).
