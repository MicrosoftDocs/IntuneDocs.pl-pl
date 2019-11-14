---
title: Aktualizowanie funkcji systemu BIOS dla systemu Windows przy użyciu zasad rozwiązania do zarządzania urządzeniami mobilnymi w usłudze Microsoft Intune — platforma Azure | Microsoft Docs
description: Dodaj profil interfejsu DFCI (Device Firmware Configuration Interface) na potrzeby zarządzania ustawieniami interfejsu UEFI, takimi jak procesor, wbudowany sprzęt i opcje rozruchu, na urządzeniach z systemem Windows 10 w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/06/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e9fe2b2174252aa1081eb311d79b4b5ba37f96f2
ms.sourcegitcommit: 1a7f04c80548e035be82308d2618492f6542d3c0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/07/2019
ms.locfileid: "73755348"
---
# <a name="use-device-firmware-configuration-interface-profiles-on-windows-devices-in-microsoft-intune-public-preview"></a>Używanie profilów interfejsu DFCI (Device Firmware Configuration Interface) na urządzeniach z systemem Windows w usłudze Microsoft Intune (publiczna wersja zapoznawcza)

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

W przypadku korzystania z usługi Intune do zarządzania zarejestrowanymi urządzeniami rozwiązania Autopilot można zarządzać ustawieniami interfejsu UEFI (BIOS) przy użyciu interfejsu DFCI (Device Firmware Configuration Interface). Aby zapoznać się z korzyściami, scenariuszami i wymaganiami wstępnymi, zobacz [Overview of DFCI (Przegląd interfejsu DFCI)](https://microsoft.github.io/mu/dyn/mu_plus/DfciPkg/Docs/Dfci_Feature/).

Interfejs DFCI [umożliwia systemowi Windows](https://docs.microsoft.com/windows/client-management/mdm/uefi-csp) przekazywanie poleceń zarządzania z usługi Intune do interfejsu UEFI (Unified Extensible Firmware Interface).

W usłudze Intune można za pomocą tej funkcji kontrolować ustawienia systemu BIOS. Zazwyczaj oprogramowanie układowe jest bardziej odporne na złośliwe ataki. Ogranicza ono kontrolę użytkowników końcowych nad systemem BIOS, co działa na korzyść w przypadku naruszenia zabezpieczeń.

Na przykład używasz urządzenia z systemem Windows 10 w zabezpieczonym środowisku i chcesz wyłączyć kamerę. Kamerę możesz wyłączyć w warstwie oprogramowania układowego, dlatego nie ma znaczenia, co zrobi użytkownik końcowy. Ponowna instalacja systemu operacyjnego ani wyczyszczenie komputera nie spowoduje ponownego włączenia kamery. Inny przykład: zablokowanie opcji rozruchu, aby uniemożliwić użytkownikom rozruch innego systemu operacyjnego lub starszej wersji systemu Windows, która nie ma tych samych funkcji zabezpieczeń.

W przypadku ponownej instalacji starszej wersji systemu Windows, instalacji oddzielnego systemu operacyjnego ani formatowania dysku twardego nie można przesłonić funkcji zarządzania interfejsu DFCI. Ta funkcja może uniemożliwić komunikację złośliwego kodu z procesami systemu operacyjnego, w tym z procesami z podniesionym poziomem uprawnień. Łańcuch zaufania interfejsu DFCI korzysta z kryptografii klucza publicznego i nie zależy od zabezpieczeń hasła lokalnego interfejsu UEFI (BIOS). Ta warstwa zabezpieczeń blokuje użytkownikom lokalnym dostęp do ustawień zarządzanych z menu interfejsu UEFI (BIOS) urządzenia.

Ta funkcja ma zastosowanie do:

- systemu Windows 10 RS5 (1809) i nowszych opartych na obsługiwanym interfejsie UEFI

## <a name="before-you-begin"></a>Przed rozpoczęciem

- Producent urządzenia musi dodać interfejs DFCI do swojego oprogramowania układowego interfejsu UEFI w ramach procesu produkcji lub jako aktualizację oprogramowania układowego instalowaną przez użytkownika. Skontaktuj się z dostawcami urządzeń, aby określić [producentów, którzy obsługują interfejs DFCI](https://microsoft.github.io/mu/dyn/mu_plus/DfciPkg/Docs/Scenarios/DfciScenarios/#oems-that-support-dfci), lub wersję oprogramowania układowego wymaganą do korzystania z interfejsu DFCI.

- Urządzenie musi być zarejestrowane w rozwiązaniu Windows Autopilot przez [partnera programu Microsoft Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider) lub bezpośrednio przez producenta OEM. 

  Urządzenia zarejestrowane ręcznie w rozwiązaniu Autopilot, na przykład [zaimportowane z pliku csv](../enrollment/enrollment-autopilot.md#add-devices), nie mogą używać interfejsu DFCI. Zgodnie z projektem interfejsu DFCI, zarządzanie nim wymaga zewnętrznego zaświadczenia o komercyjnym pozyskaniu uzyskanym w ramach rejestracji producenta OEM lub partnera programu Microsoft CSP dla rozwiązania Windows Autopilot.

  Po zarejestrowaniu urządzenia jego numer seryjny jest wyświetlany na liście urządzeń rozwiązania Windows Autopilot.

  Aby uzyskać więcej informacji na temat rozwiązania Autopilot, w tym wszystkich wymagań, zobacz [Rejestrowanie urządzeń z systemem Windows w usłudze Intune za pomocą rozwiązania Windows Autopilot](../enrollment/enrollment-autopilot.md).

## <a name="create-your-azure-ad-security-groups"></a>Tworzenie grup zabezpieczeń usługi Azure AD

Profile wdrażania rozwiązania Autopilot są przypisane do grup zabezpieczeń usługi Azure AD. Należy pamiętać o utworzeniu grup obejmujących urządzenia obsługiwane przez interfejs DFCI. W przypadku urządzeń z interfejsem DFCI większość organizacji może utworzyć grupy urządzeń zamiast grup użytkowników. Rozważ następujące scenariusze:

- Dział zasobów ludzkich (HR) dysponuje różnymi urządzeniami z systemem Windows. Ze względów bezpieczeństwa nie chcesz, aby ktokolwiek z tej grupy mógł korzystać z kamery na urządzeniach. W tym scenariuszu możesz utworzyć grupę użytkowników zabezpieczeń dla działu HR, tak aby zasady były stosowane do użytkowników w tej grupie niezależnie od typu urządzenia.
- Na hali produkcyjnej masz 10 urządzeń. Na wszystkich urządzeniach chcesz uniemożliwić ich rozruch za pomocą urządzenia USB. W tym scenariuszu możesz utworzyć grupę urządzeń zabezpieczeń i dodać te 10 urządzeń do grupy.

Aby uzyskać więcej informacji na temat tworzenia grup w usłudze Intune, zobacz [Dodawanie grup w celu organizowania użytkowników i urządzeń](../fundamentals/groups-add.md).

## <a name="create-the-profiles"></a>Tworzenie profilów

Aby użyć interfejsu DFCI, utwórz następujące profile i przypisz je do grupy.

### <a name="create-an-autopilot-deployment-profile"></a>Tworzenie profilu wdrażania rozwiązania Autopilot

Ten profil umożliwia przygotowanie i wstępne skonfigurowanie nowych urządzeń. [Profil wdrażania rozwiązania Autopilot](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile) zawiera listę kroków umożliwiających utworzenie profilu.

### <a name="create-an-enrollment-state-page-profile"></a>Tworzenie profilu strony stanu rejestracji

Ten profil zapewnia, że urządzenia są weryfikowane i aktywowane pod kątem interfejsu DFCI podczas instalacji systemu Windows. Zdecydowanie zaleca się użycie tego profilu do zablokowania użycia urządzenia dopóki wszystkie aplikacje i profile nie zostaną zainstalowane. [Profil strony stanu rejestracji](../enrollment/windows-enrollment-status.md) zawiera kroki tworzenia profilu.

### <a name="create-the-dfci-profile"></a>Tworzenie profilu interfejsu DFCI

Ten profil zawiera konfigurowane ustawienia interfejsu DFCI.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz **Urządzenia** > **Profile konfiguracji** > **Utwórz profil**.
3. Wprowadź następujące właściwości:

    - **Nazwa**: Wprowadź opisową nazwę profilu. Nadaj nazwę zasadom, aby można było je później łatwo rozpoznać. Na przykład dobra nazwa profilu to **Windows: Konfigurowanie ustawień interfejsu DFCI na urządzeniach z systemem Windows**.
    - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: Wybierz **System Windows 10 lub nowszy**.
    - **Typ profilu**: Wybierz pozycję **Device Firmware Configuration Interface**.

4. Skonfiguruj ustawienia:

    - **Zezwalaj użytkownikom lokalnym na zmienianie ustawień interfejsu UEFI (BIOS)** : Dostępne opcje:
      - **Tylko nieskonfigurowane ustawienia**: użytkownik lokalny może zmienić dowolne ustawienie *z wyjątkiem* ustawień, dla których jawnie ustawiono opcję **Włączone** lub **Wyłączone** za pomocą usługi Intune.
      - **Brak**: użytkownik lokalny nie może zmieniać żadnych ustawień interfejsu UEFI (BIOS), w tym ustawień niewyświetlanych w profilu interfejsu DFCI.

    - **Wirtualizacja procesora CPU i operacji we/wy**: Dostępne opcje:
        - **Nieskonfigurowane**: usługa Intune nie modyfikuje tej funkcji i pozostawia wszystkie ustawienia bez zmian.
        - **Włączone**: system BIOS umożliwia korzystanie z możliwości wirtualizacji procesora i operacji we/wy platformy na potrzeby systemu operacyjnego. Włącza on technologie Zabezpieczenia na podstawie wirtualizacji i Device Guard systemu Windows.
        - **Wyłącz**: system BIOS wyłącza możliwości wirtualizacji procesora i operacji we/wy platformy oraz uniemożliwia ich użycie.
    - **Kamery**: Dostępne opcje:
        - **Nieskonfigurowane**: usługa Intune nie modyfikuje tej funkcji i pozostawia wszystkie ustawienia bez zmian.
        - **Włączone**: wszystkie wbudowane kamery zarządzane bezpośrednio przez interfejs UEFI (BIOS) są włączone. Nie dotyczy to urządzeń peryferyjnych, takich jak kamery podłączone przez złącze USB.
        - **Wyłączone**: wszystkie wbudowane kamery zarządzane bezpośrednio przez interfejs UEFI (BIOS) są wyłączone. Nie dotyczy to urządzeń peryferyjnych, takich jak kamery podłączone przez złącze USB.
    - **Mikrofony i głośniki**:  Dostępne opcje:
        - **Nieskonfigurowane**: usługa Intune nie modyfikuje tej funkcji i pozostawia wszystkie ustawienia bez zmian.
        - **Włączone**: wszystkie wbudowane mikrofony i głośniki zarządzane bezpośrednio przez interfejs UEFI (BIOS) są włączone. Nie dotyczy to urządzeń peryferyjnych, takich jak podłączone przez złącze USB.
        - **Wyłączone**: wszystkie wbudowane mikrofony i głośniki zarządzane bezpośrednio przez interfejs UEFI (BIOS) są wyłączone. Nie dotyczy to urządzeń peryferyjnych, takich jak podłączone przez złącze USB.
    - **Urządzenia radiowe (Bluetooth, Wi-Fi, NFC itp.)** : Dostępne opcje:
        - **Nieskonfigurowane**: usługa Intune nie modyfikuje tej funkcji i pozostawia wszystkie ustawienia bez zmian.
        - **Włączone**: wszystkie wbudowane urządzenia radiowe zarządzane bezpośrednio przez interfejs UEFI (BIOS) są włączone. Nie dotyczy to urządzeń peryferyjnych, takich jak podłączone przez złącze USB.
        - **Wyłączone**: wszystkie wbudowane urządzenia radiowe zarządzane bezpośrednio przez interfejs UEFI (BIOS) są wyłączone. Nie dotyczy to urządzeń peryferyjnych, takich jak podłączone przez złącze USB.

        > [!WARNING]
        > Jeśli wyłączysz ustawienie **Urządzenia radiowe**, urządzenie będzie wymagać połączenia sieci przewodowej. W przeciwnym przypadku zarządzanie urządzeniem może nie być możliwe.

    - **Rozruch z nośnika zewnętrznego (USB, SD)** : Dostępne opcje:
        - **Nieskonfigurowane**: usługa Intune nie modyfikuje tej funkcji i pozostawia wszystkie ustawienia bez zmian.
        - **Włączone**: interfejs UEFI (BIOS) zezwala na rozruch z magazynu innego niż dysk twardy.
        - **Wyłączone**: interfejs UEFI (BIOS) nie zezwala na rozruch z magazynu innego niż dysk twardy.
    - **Rozruch z kart sieciowych**:  Dostępne opcje:
        - **Nieskonfigurowane**: usługa Intune nie modyfikuje tej funkcji i pozostawia wszystkie ustawienia bez zmian.
        - **Włączone**: interfejs UEFI (BIOS) zezwala na rozruch z wbudowanych interfejsów sieciowych.
        - **Wyłączone**: interfejs UEFI (BIOS) nie zezwala na rozruch z wbudowanych interfejsów sieciowych.

5. Po zakończeniu wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany. Profil zostanie utworzony i wyświetlony na liście.

## <a name="assign-the-profiles-and-reboot"></a>Przypisywanie profili i ponowne uruchamianie

Po utworzeniu profilów są one [gotowe do przypisania](../configuration/device-profile-assign.md). Należy pamiętać o przypisaniu profilów do grup zabezpieczeń usługi Azure AD zawierających używane urządzenia interfejsu DFCI.

Jeśli na urządzeniu jest uruchomione rozwiązanie Windows Autopilot, na stronie Stan rejestracji interfejs DFCI może wymusić ponowne uruchomienie systemu. Podczas tego pierwszego ponownego uruchomienia interfejs UEFI jest rejestrowany w usłudze Intune. 

Jeśli chcesz potwierdzić, że urządzenie jest zarejestrowane, możesz je ponownie uruchomić, ale nie jest to wymagane. Użyj instrukcji dostarczonych przez producenta urządzenia, aby otworzyć menu interfejsu UEFI i potwierdzić, że jest on zarządzany.

Podczas następnego synchronizowania urządzenia z usługą Intune system Windows otrzyma ustawienia interfejsu DFCI. Uruchom ponownie urządzenie. Ten trzeci ponowny rozruch jest wymagany do odebrania ustawień interfejsu DFCI z systemu Windows.

## <a name="update-existing-dfci-settings"></a>Aktualizowanie istniejących ustawień interfejsu DFCI

Jeśli chcesz zmienić istniejące ustawienia interfejsu DFCI na używanych urządzeniach, jest to możliwe. W istniejącym profilu interfejsu DFCI zmień ustawienia i zapisz zmiany. Ponieważ profil jest już przypisany, nowe ustawienia interfejsu DFCI zaczną obowiązywać, gdy:

1. Urządzenie zostanie zaewidencjonowane w usłudze Intune w celu przejrzenia aktualizacji profilów. Ewidencjonowanie jest wykonywane w różnych godzinach. Aby uzyskać więcej informacji, zobacz [kiedy urządzenie pobiera aktualizacje zasad, profilów lub aplikacji](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

2. Aby wymusić nowe ustawienia, uruchom ponownie urządzenie [zdalnie](../remote-actions/device-restart.md) lub lokalnie.

Możesz też [przesłać do urządzeń sygnał ewidencjonowania](../remote-actions/device-sync.md). Po pomyślnym wykonaniu synchronizacji [prześlij sygnał ponownego uruchomienia](../remote-actions/device-restart.md).

>[!NOTE]
> Usunięcie profilu interfejsu DFCI ani usunięcie urządzenia z grupy przypisanej do profilu nie powoduje usunięcia ustawień interfejsu DFCI ani ponownego włączenia menu interfejsu UEFI (BIOS). Jeśli chcesz zakończyć korzystanie z interfejsu DFCI, zaktualizuj istniejący profil interfejsu DFCI. Aby uzyskać więcej informacji na temat kroków, zobacz sekcję [Wycofywanie urządzenia](#retire) w tym artykule.

## <a name="reuse-retire-or-recover-the-device"></a>Ponowne użycie, wycofanie lub odzyskanie urządzenia

### <a name="reuse"></a>Ponowne użycie

Jeśli planujesz zresetować system Windows w celu zmiany przeznaczenia urządzenia, [wyczyść urządzenie](../remote-actions/devices-wipe.md). **Nie** usuwaj rekordu urządzenia rozwiązania Autopilot.

Po wyczyszczeniu urządzenia przenieś je do grupy przypisanej do nowych profilów interfejsu DFCI i rozwiązania Autopilot. Upewnij się, że uruchomiono ponownie urządzenie, aby uruchomić ponownie instalatora systemu Windows.

### <a name="retire"></a>Wycofaj

Gdy wszystko będzie gotowe do wycofania urządzenia i zwolnienia go z zarządzania, zaktualizuj profil interfejsu DFCI za pomocą ustawień interfejsu UEFI (BIOS), które mają być aktywne po zakończeniu procesu. Zwykle wszystkie ustawienia są włączone. Przykład:

1. Otwórz profil interfejsu DFCI (**Urządzenia** > **Profile konfiguracji**).
2. Zmień ustawienie **Zezwalaj użytkownikom lokalnym na zmienianie ustawień interfejsu UEFI (BIOS)** na **Tylko nieskonfigurowane ustawienia**.
3. Ustaw wszystkie inne ustawienia na wartość **Nie skonfigurowano**.
4. Zapisz ustawienia.

Te kroki służą do odblokowania menu interfejsu UEFI (BIOS) urządzenia. Wartości pozostaną takie same jak w profilu (**Włączone** lub **Wyłączone**) i nie zostaną przywrócone do wartości domyślnych systemu operacyjnego.

Teraz można przystąpić do czyszczenia urządzenia. Po wyczyszczeniu urządzenia usuń rekord rozwiązania Autopilot. Usunięcie rekordu uniemożliwia automatyczne ponowne zarejestrowanie urządzenia po jego ponownym uruchomieniu.

### <a name="recover"></a>Odzyskiwanie

Jeśli wyczyścisz urządzenie i usuniesz rekord rozwiązania Autopilot przed odblokowaniem menu interfejsu UEFI (BIOS), menu pozostaną zablokowane. Usługa Intune nie może wysłać aktualizacji profilu, aby je odblokować.

Aby odblokować urządzenie, otwórz menu UEFI (BIOS) i odśwież zarządzanie z sieci. Odzyskiwanie odblokowuje menu, ale pozostawia wszystkie ustawienia UEFI (BIOS) skonfigurowane za pomocą wartości z poprzedniego profilu DFCI usługi Intune.

## <a name="end-user-impact"></a>Wpływ na użytkowników końcowych

Po zastosowaniu zasad interfejsu DFCI użytkownicy lokalni nie mogą zmieniać ustawień skonfigurowanych przy pomocy interfejsu DFCI, nawet jeśli menu interfejsu UEFI (BIOS) jest chronione hasłem. W zależności od skonfigurowanych ustawień, użytkownicy końcowi mogą otrzymywać błędy dotyczące niemożliwości znalezienia lub zdiagnozowania składników sprzętowych. Pamiętaj o dostarczeniu użytkownikom końcowym dokumentacji wyjaśniającej wyłączone opcje.  

## <a name="next-steps"></a>Następne kroki

Po przypisaniu profilu [monitoruj jego stan](../device-profile-monitor.md).
