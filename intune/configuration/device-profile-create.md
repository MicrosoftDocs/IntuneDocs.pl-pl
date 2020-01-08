---
title: Tworzenie profilów urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodaj lub skonfiguruj profil konfiguracji urządzenia w usłudze Microsoft Intune. Wybierz typ platformy, skonfiguruj ustawienia i dodaj tag zakresu.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c8748639f0407de7b1bb83f646b7decf8c838766
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206673"
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Tworzenie profilu urządzenia w usłudze Microsoft Intune

Profile urządzeń umożliwiają dodawanie i konfigurowanie ustawień, a następnie wypychanie tych ustawień do urządzeń w organizacji. Dalsze szczegóły, w tym opis możliwych do wykonania czynności, można znaleźć w temacie [Apply features and settings on your devices using device profiles](device-profiles.md) (Stosowanie funkcji i ustawień na urządzeniach przy użyciu profilów urządzeń).

W tym artykule:

- Znajduje się lista czynności wymaganych do utworzenia profilu.
- Przedstawiono sposób dodawania tagu zakresu w celu „filtrowania” profilu.
- Opisano reguły stosowania na urządzeniach z systemem Windows 10 i pokazano, jak utworzyć regułę.
- Znajduje się lista czasów cykli odświeżania zaewidencjonowania, gdy urządzenia otrzymują profile i wszelkie aktualizacje profilów.

## <a name="create-the-profile"></a>Tworzenie profilu

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz pozycję **Urządzenia** > **Profile konfiguracji**. Do wyboru są następujące opcje:

    - **Omówienie**: lista stanów profilów oraz dodatkowe szczegółowe informacje o profilach przypisanych do użytkowników i urządzeń.
    - **Zarządzanie**: tworzenie profili urządzeń, przekazywanie niestandardowych [skryptów programu PowerShell](../apps/intune-management-extension.md) do uruchamiania w profilu i dodawanie planów danych do urządzeń korzystających z karty [eSIM](esim-device-configuration.md).
    - **Monitorowanie**: sprawdzanie stanu profilu (powodzenie lub niepowodzenie) oraz wyświetlanie dzienników dotyczących profili.
    - **Instalator**: dodawanie urzędu certyfikacji SCEP lub PFX albo włączanie [zarządzania wydatkami telekomunikacyjnymi](telecom-expenses-monitor.md) w profilu.

3. Wybierz pozycję **Utwórz profil**. Wprowadź następujące właściwości:

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
       - [Zaimportowany certyfikat PKCS](../protect/certificates-imported-pfx-configure.md)
       - [Plik preferencji](preference-file-settings-macos.md)
       - [Certyfikat SCEP](../protect/certificates-scep-configure.md)
       - [Zaufany certyfikat](../protect/certificates-configure.md)
       - [Zasady aktualizacji](../software-updates-ios.md)
       - [VPN](vpn-settings-configure.md)
       - [Wi-Fi](wi-fi-settings-configure.md)
       - [Microsoft Defender ATP](../protect/advanced-threat-protection.md)
       - [Rozwiązanie Windows Information Protection](../protect/windows-information-protection-configure.md)

     Jeśli na przykład wybierzesz platformę **iOS/iPadOS**, opcje typu profilu będą wyglądać podobnie do następującego profilu:

     ![Tworzenie profilu systemu iOS w usłudze Intune](./media/device-profile-create/create-device-profile.png)

4. Po zakończeniu wybierz pozycję **OK** > **Utwórz**, aby zapisać zmiany. Profil zostanie utworzony i wyświetlony na liście.

## <a name="scope-tags"></a>Tagi zakresu

Po dodaniu ustawień możesz również dodać tag zakresu do profilu. Tagi zakresu umożliwiają filtrowanie profilów w celu zdefiniowania grup IT, takich jak `US-NC IT Team` lub `JohnGlenn_ITDepartment`.

Więcej informacji na temat tagów zakresu i czynności możliwych do wykonania można znaleźć w artykule [Use RBAC and scope tags for distributed IT](../fundamentals/scope-tags.md) (Używanie kontroli RBAC i tagów zakresu w rozproszonej infrastrukturze informatycznej).

### <a name="add-a-scope-tag"></a>Dodawanie tagu zakresu

1. Wybierz pozycję **Zakres (tagi)** .
2. Wybierz pozycję **Dodaj**, aby utworzyć nowy tag zakresu. Możesz również wybrać istniejący tag zakresu z listy.
3. Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="applicability-rules"></a>Zasady stosowania

Dotyczy:

- Windows 10 lub nowszym

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

## <a name="recommendations"></a>Zalecenia

Podczas tworzenia profilów należy wziąć pod uwagę następujące zalecenia:

- Nazwij swoje zasady, aby znać ich znaczenie i działanie. Wszystkie [zasady zgodności](../protect/create-compliance-policy.md) i [profile konfiguracji](../configuration/device-profile-create.md) mają opcjonalną właściwość **Opis**. W polu **Opis** należy zamieścić szczegółowe informacje, aby również inni znali działanie zasady.

  Niektóre przykłady profilów konfiguracji obejmują:

  **Nazwa profilu**: Szablon administratora — profil konfiguracji usługi OneDrive dla wszystkich użytkowników systemu Windows 10  
  **Opis profilu**: Profil szablonu administratora usługi OneDrive obejmujący minimalne i podstawowe ustawienia dla wszystkich użytkowników systemu Windows 10. Utworzony przez użytkownika user@contoso.com, aby uniemożliwić użytkownikom udostępnianie danych organizacji na kontach osobistych w usłudze OneDrive.

  **Nazwa profilu**: Profil sieci VPN dla wszystkich użytkowników systemu iOS  
  **Opis profilu**: Profil sieci VPN, który obejmuje minimalne i podstawowe ustawienia łączenia się z siecią VPN firmy Contoso dla wszystkich użytkowników systemu iOS. Utworzony przez użytkownika user@contoso.com, aby użytkownicy automatycznie uwierzytelniali się w sieci VPN, a nie otrzymywali monity o podanie nazwy użytkownika i hasła.

- Utwórz profil związany z konkretnym zadaniem, takim jak konfiguracja ustawień przeglądarki Microsoft Edge, włączanie ustawienia antywirusowego programu Microsoft Defender, blokowanie urządzeń z systemem iOS ze zdjętymi zabezpieczeniami itd.

- Utwórz profile, które mają zastosowanie do określonych grup, takich jak marketing, sprzedaż, administratorzy IT, lub do określonej lokalizacji bądź szkoły.

- Oddziel zasady użytkownika od zasad urządzeń.

  Na przykład [szablony administracyjne w usłudze Intune](administrative-templates-windows.md) mają setki ustawień ADMX. Te szablony pokazują, czy ustawienia dotyczą użytkowników, czy urządzeń. Podczas tworzenia szablonów administracyjnych przypisuj ustawienia użytkownika do grupy użytkowników, a ustawienia urządzenia do grupy urządzeń.

  Na poniższej ilustracji przedstawiono przykład ustawienia, które można zastosować do użytkowników lub do urządzeń:

  ![Szablon administracyjny w usłudze Intune, który można zastosować do użytkowników i do urządzeń](./media/device-profile-create/setting-applies-to-user-and-device.png)

- Za każdym razem, gdy tworzysz restrykcyjne zasady, poinformuj o tym użytkowników. Jeśli na przykład zmieniasz wymagania dotyczące kodu dostępu z 4 znaków na 6 znaków, powiadom użytkowników przed przypisaniem zasad.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](../device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).
