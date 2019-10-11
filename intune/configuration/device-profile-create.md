---
title: Tworzenie profilów urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodaj lub skonfiguruj profil konfiguracji urządzenia w usłudze Microsoft Intune. Wybierz typ platformy, skonfiguruj ustawienia i dodaj tag zakresu.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0858eefede678615e5b856fa0e40e48a791e4cce
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71724103"
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Tworzenie profilu urządzenia w usłudze Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Profile urządzeń umożliwiają dodawanie i konfigurowanie ustawień, a następnie wypychanie tych ustawień do urządzeń w organizacji. Dalsze szczegóły, w tym opis możliwych do wykonania czynności, można znaleźć w temacie [Apply features and settings on your devices using device profiles](device-profiles.md) (Stosowanie funkcji i ustawień na urządzeniach przy użyciu profilów urządzeń).

W tym artykule:

- Znajduje się lista czynności wymaganych do utworzenia profilu.
- Przedstawiono sposób dodawania tagu zakresu w celu „filtrowania” profilu.
- Opisano reguły stosowania na urządzeniach z systemem Windows 10 i pokazano, jak utworzyć regułę.
- Znajduje się lista czasów cykli odświeżania zaewidencjonowania, gdy urządzenia otrzymują profile i wszelkie aktualizacje profilów.

## <a name="create-the-profile"></a>Tworzenie profilu

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

2. Wybierz pozycję **Konfiguracja urządzenia**. Do wyboru są następujące opcje:

    - **Omówienie**: lista stanów profilów oraz dodatkowe szczegółowe informacje o profilach przypisanych do użytkowników i urządzeń.
    - **Zarządzanie**: tworzenie profili urządzeń, przekazywanie niestandardowych [skryptów programu PowerShell](../apps/intune-management-extension.md) do uruchamiania w profilu i dodawanie planów danych do urządzeń korzystających z karty [eSIM](esim-device-configuration.md).
    - **Monitorowanie**: sprawdzanie stanu profilu (powodzenie lub niepowodzenie) oraz wyświetlanie dzienników dotyczących profili.
    - **Instalator**: dodawanie urzędu certyfikacji SCEP lub PFX albo włączanie [zarządzania wydatkami telekomunikacyjnymi](telecom-expenses-monitor.md) w profilu.

3. Wybierz pozycję **Profile**  >  **Utwórz profil**. Wprowadź następujące właściwości:

   - **Nazwa**: Wprowadź opisową nazwę profilu. Nadaj nazwę profilom, aby można było je później łatwo rozpoznać. Na przykład dobra nazwa profilu to **Profil poczty e-mail WP dla całej firmy**.
   - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
   - **Platforma**: Wybierz platformę urządzeń. Dostępne opcje:  

       - **Android**
       - **Android enterprise**
       - **iOS/iPadOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 lub nowszy**
       - **Windows 10 lub nowszy**

   - **Typ profilu**: Wybierz typ ustawień, który chcesz utworzyć. Wyświetlana lista zależy od wybranej **platformy**.
   - **Ustawienia**: Ustawienia poszczególnych typów profilów opisano w następujących artykułach:

       - [Szablony administracyjne](administrative-templates-windows.md)
       - [Niestandardowe](../custom-settings-configure.md)
       - [Optymalizacja dostarczania](../delivery-optimization-windows.md)
       - [Funkcje urządzenia](../device-features-configure.md)
       - [Ograniczenia dotyczące urządzeń](device-restrictions-configure.md)
       - [Uaktualnianie wersji i przełącznik trybów](edition-upgrade-configure-windows-10.md)
       - [Edukacja](education-settings-configure.md)
       - [Poczta e-mail](email-settings-configure.md)
       - [Program Endpoint Protection](../protect/endpoint-protection-configure.md)
       - [Identity Protection](../protect/identity-protection-configure.md)  
       - [Kiosk](kiosk-settings.md)
       - [Certyfikat PKCS](../protect/certficates-pfx-configure.md)
       - [Certyfikat SCEP](../protect/certificates-scep-configure.md)
       - [Zaufany certyfikat](../protect/certificates-configure.md)
       - [Zasady aktualizacji](../software-updates-ios.md)
       - [VPN](vpn-settings-configure.md)
       - [Wi-Fi](wi-fi-settings-configure.md)
       - [Zaawansowana ochrona przed zagrożeniami w usłudze Windows Defender](../protect/advanced-threat-protection.md)
       - [Rozwiązanie Windows Information Protection](../protect/windows-information-protection-configure.md)

     Jeśli na przykład wybierzesz platformę **iOS/iPadOS**, opcje typu profilu będą wyglądać podobnie do następującego profilu:

     ![Tworzenie profilu systemu iOS w usłudze Intune](./media/device-profile-create/create-device-profile.png)

4. Po zakończeniu wybierz pozycję **OK**  >  **Utwórz**, aby zapisać zmiany. Profil zostanie utworzony i wyświetlony na liście.

## <a name="scope-tags"></a>Tagi zakresu

Po dodaniu ustawień możesz również dodać tag zakresu do profilu. Tagi zakresu umożliwiają przypisywanie i filtrowanie zasad do określonych grup, takich jak pracownicy działu kadr lub wszyscy pracownicy w stanie Północna Karolina w USA.

Więcej informacji na temat tagów zakresu i czynności możliwych do wykonania można znaleźć w artykule [Use RBAC and scope tags for distributed IT](../fundamentals/scope-tags.md) (Używanie kontroli RBAC i tagów zakresu w rozproszonej infrastrukturze informatycznej).

### <a name="add-a-scope-tag"></a>Dodawanie tagu zakresu

1. Wybierz pozycję **Zakres (tagi)**.
2. Wybierz pozycję **Dodaj**, aby utworzyć nowy tag zakresu. Możesz również wybrać istniejący tag zakresu z listy.
3. Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="applicability-rules"></a>Zasady stosowania

Dotyczy:

- System Windows 10 lub nowszy

Reguły stosowania umożliwiają administratorom kierowanie urządzeń do grup spełniających określone kryteria. Można na przykład utworzyć profil ograniczenia dotyczącego urządzeń, który ma zastosowanie do grupy **Wszystkie urządzenia systemu Windows 10**. Ponadto profil ma być przypisany tylko do urządzeń z systemem Windows 10 Enterprise.

Aby wykonać to zadanie, utwórz **regułę stosowania**. Te reguły są doskonałe dla następujących scenariuszy:

- Używasz systemu Windows 10 Education (EDU). W Bellows College chcesz wybrać wszystkie urządzenia z systemem Windows 10 EDU w wersjach od RS3 do RS4 jako urządzenia docelowe.
- Chcesz dotrzeć do wszystkich użytkowników w dziale zasobów ludzkich firmy Contoso, ale tylko do urządzeń z systemem Windows 10 Professional lub Enterprise.

Aby obsłużyć te scenariusze:

- Utwórz grupę urządzeń, która obejmuje wszystkie urządzenia w Bellows College. W profilu dodaj regułę stosowania, która ma zastosowanie, jeśli minimalna wersja systemu operacyjnego to `16299`, a maksymalna wersja to `17134`. Przypisz ten profil do grupy urządzeń Bellows College.

  Po przypisaniu profil dotyczy urządzeń między wprowadzanymi wersjami: minimalną i maksymalną. W przypadku urządzeń, które nie znajdują się w przedziale od wersji minimalnej do maksymalnej, zostanie wyświetlony stan **Nie dotyczy**.

- Utwórz grupę użytkowników obejmującą wszystkich użytkowników w dziale zasobów ludzkich (HR) w firmie Contoso. W profilu dodaj regułę stosowania, która ma zastosowanie do urządzeń z systemem Windows 10 Professional lub Enterprise. Przypisz ten profil do grupy użytkowników działu HR.

  Po przypisaniu profil dotyczy urządzeń z systemem Windows 10 Professional lub Enterprise. W przypadku urządzeń, na których nie są uruchomione te wersje, ich stan jest wyświetlany jako **Nie dotyczy**.

- Jeśli istnieją dwa profile z dokładnie tymi samymi ustawieniami, zostanie zastosowany profil bez reguły stosowania. 

  Na przykład profil A jest przeznaczony dla grupy urządzeń z systemem Windows 10, włącza funkcję BitLocker i nie ma reguły stosowania. Profil B jest przeznaczony dla tej samej grupy urządzeń z systemem Windows 10, włącza funkcję BitLocker i ma regułę stosowania tylko do systemu Windows 10 Enterprise.

  Po przypisaniu obu profili stosowany jest profil A, ponieważ nie ma on reguły stosowania. 

Po przypisaniu profilu do grup reguły stosowania działają jako filtr i są przeznaczone tylko dla urządzeń spełniających określone kryteria.

### <a name="add-a-rule"></a>Dodaj regułę

1. Wybierz opcję **Reguły stosowania**. Można wybrać **regułę**, **Właściwość** i **edycję systemu operacyjnego**:

    ![Dodaj regułę stosowania do profilu konfiguracji urządzenia w usłudze Microsoft Intune](./media/device-profile-create/applicability-rules.png)

2. W polu **Reguła** wybierz, czy chcesz uwzględnić, czy wykluczyć użytkowników lub grupy. Dostępne opcje:

    - **Przypisz profil, jeśli**: Obejmuje użytkowników lub grupy spełniające wprowadzone kryteria.
    - **Nie przypisuj profilu, jeśli**: Wyklucza użytkowników lub grupy spełniające wprowadzone kryteria.

3. W polu **Właściwość** wybierz filtr. Dostępne opcje: 

    - **Edycja systemu operacyjnego**: Na liście sprawdź edycje systemu Windows 10, które mają zostać uwzględnione (lub wykluczone) w regule.
    - **Wersja systemu operacyjnego**: Wprowadź **minimalny** i **maksymalny** numer wersji systemu Windows 10, który ma zostać uwzględniony (lub wykluczony) w regule. Obie wartości są wymagane.

      Można na przykład wprowadzić wartość `10.0.16299.0` (RS3 lub 1709) dla wersji minimalnej i `10.0.17134.0` (RS4 lub 1803) dla wersji maksymalnej. Można też określić wersje bardziej szczegółowo, wprowadzając wartość `10.0.16299.001` dla wersji minimalnej i `10.0.17134.319` dla wersji maksymalnej.

4. Wybierz opcję **Dodaj**, aby zapisać zmiany.

## <a name="refresh-cycle-times"></a>Czasy cyklu odświeżania

Usługa Intune używa różnych cykli odświeżania w celu sprawdzania dostępności aktualizacji profilów konfiguracji. Jeśli urządzenie zostało zarejestrowane ostatnio, sprawdzanie odbywa się częściej. Szacowane czasy odświeżania znajdują się w sekcji dotyczącej [cyklów odświeżania zasad i profilów](device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

W dowolnym momencie użytkownicy mogą otwierać aplikację Portal firmy i synchronizować urządzenie, aby natychmiast wyszukiwać aktualizacje profilów.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](../device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).
