---
title: Porzucanie rejestracji portalu firmy w usłudze Intune
titlesuffix: Microsoft Intune
description: Informacje o raporcie porzucania portalu firmy.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/20/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
ms.custom: intune-azure; get-started
ms.openlocfilehash: ba1ee5a6811457b8c6e7343de7355261a2fcecdb
ms.sourcegitcommit: 5c2a70180cb69049c73c9e55d36a51e9d6619049
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/30/2018
ms.locfileid: "50236758"
---
# <a name="company-portal-abandonment-report"></a>Raport porzucania portalu firmy

Ten raport informuje, w którym miejscu użytkownicy porzucają proces rejestracji Portalu firmy.

Aby wyświetlić raport, wybierz pozycję **Intune** > **Rejestrowanie urządzeń** > **Porzucanie Portalu firmy**.

Dzięki tym informacjom o porzucaniu możesz zaktualizować swoje dokumenty dotyczące dołączania, aby ułatwić użytkownikom ukończenie rejestracji. Jeśli na przykład wielu użytkowników porzuca rejestrację na etapie warunków użytkowania, możesz zbadać ten obszar i uczynić go bardziej intuicyjnym dla użytkowników.

## <a name="what-is-abandonment"></a>Co to jest porzucenie?

Porzucenie to sytuacja, w której użytkownik wykonuje jedną z następujących czynności:

-   Jawnie wybiera akcję zatrzymującą rejestrację.
-   Zamyka Portal firmy podczas rejestracji.
-   Spędza ponad 30 minut między sekcjami rejestracji.

Jeśli użytkownik decyduje się na wielokrotne zatrzymanie i ponowne rozpoczęcie rejestracji, jest to wyświetlane jako wiele prób i wiele porzuceń. Jeśli użytkownik czeka 30 minut między różnymi ekranami rejestracji, jest to uznawane za porzucenia.

## <a name="what-does-the-report-show"></a>Co jest wyświetlane w raporcie?

Raporty rejestracji zawierają dane dla urządzeń z systemami iOS i Android.

W raportach są wyświetlane dane z ostatnich dwóch tygodni, ale możesz filtrować raport, aby były wyświetlane dane z okresu do 30 dni w przeszłości.

Wybierając pozycję **Filtruj**, możesz filtrować według zakresu dat, systemu operacyjnego i sekcji rejestracji.

### <a name="number-and-percentage-tiles"></a>Kafelki liczby i wartości procentowych

W górnej części raportu znajduje się liczba i wartość procentowa porzuconych raportów w odniesieniu do wszystkich rejestracji.

-   Zainicjowane rejestracje: liczba prób rejestracji.
-   Porzucone rejestracje: liczba prób rejestracji, których rezultatem nie było w pełni zarejestrowane i zgodne urządzenie.
-   Współczynnik porzucania: wartość procentowa prób rejestracji, które zostały porzucone (porzucone rejestracje / zainicjowane rejestracje).

### <a name="line-graph"></a>Wykres liniowy

Wykres liniowy przedstawia codzienne porzucenia dla każdej z czterech podstawowych sekcji rejestracji:

-   Lista kontrolna ustawień
-   Ekrany platformy
-   Warunki użytkowania
-   Zgodność/aktywacja

### <a name="user-abandonment-actions"></a>Akcje porzucenia użytkownika

W poniższych tabelach przedstawiono listę akcji użytkownika, które kwalifikują się jako porzucenie. Aby zobaczyć przykłady ekranów rejestracji, możesz obejrzeć klipy wideo dotyczące rejestracji w systemach [iOS](https://channel9.msdn.com/Series/IntuneEnrollment/iOS-Enrollment) i [Android](https://channel9.msdn.com/Series/IntuneEnrollment/Android-Enrollment). 


#### <a name="setup-checklist-section"></a>Lista kontrolna konfiguracji

| Nazwa porzucenia | Ekran lub przepływ | Platforma | Akcja |
| ---- |---- |---- |---- |
| EnrollmentWrapUp | Monit o otworzenie strony w Portalu firmy | iOS/Android | **Anuluj** |
| EnrollmentWrapUp | Ekran rejestracji urządzenia do chwili ukończenia **ładowania zasobów firmy** | iOS/Android | Czas trwania > 30 minut |
| DeviceCategory | Wybór kategorii urządzenia (jeśli skonfigurowano przez administratora) do chwili kliknięcia pozycji **Gotowe** | iOS/Android | Czas trwania > 30 minut |
| PreEnrollmentWizard | Ekran konfigurowania dostępu, gdy rozpoczęto rejestrację, ale wrócono do konfigurowania dostępu | iOS/Android| **Odłóż** |
| PreEnrollmentWizard | Ekran konfigurowania dostępu do chwili kliknięcia pozycji **Dalej** na ekranie **Co dalej** | iOS/Android | Czas trwania > 30 minut |

#### <a name="platform-screens-section"></a>Sekcja ekranów platformy

| Nazwa porzucenia | Ekran lub przepływ | Platforma | Akcja |
| ---- |---- |---- |---- |
| iOSProfileLaunch | Monit o pokazanie profilu konfiguracji | iOS | **Ignoruj** |
| iOSProfileLaunch | Ekran instalowania profilu | iOS | **Anuluj** |
| iOSProfileLaunch | Monit o zaufanie elementowi źródłowemu profilu w celu zarejestrowania urządzenia | iOS | **Anuluj** |
| iOSProfileLaunch | Ekran instalowania profilu do chwili zainstalowania profilu | iOS | Czas trwania > 30 minut |
| AndroidPermissions | Ekran aktywacji administratora urządzenia | Android | **Anuluj** |
| AndroidPermissions | Monit o zatwierdzenie w celu wykonywania połączeń telefonicznych i zarządzania nimi do chwili **aktywacji** administratora urządzenia | Android | Czas trwania > 30 minut |
| KnoxActivation | Aktywacja agenta KLMS (tylko rozwiązanie firmy Samsung) | Android| **Anuluj** |
| KnoxActivation | Aktywacja agenta KLMS do chwili **potwierdzenia** | Android | Czas trwania > 30 minut|

#### <a name="terms-of-use-section"></a>Sekcja warunków użytkowania

| Nazwa porzucenia | Ekran lub przepływ | Platforma | Akcja |
| ---- |---- |---- |---- |
| TermsofUse | Warunki użytkowania (jeśli skonfigurowano przez administratora) | iOS/Android | **Odrzuć wszystko** |
| TermsofUse | Warunki użytkowania do chwili **zaakceptowania wszystkiego** | iOS/Android | Czas trwania > 30 minut |

#### <a name="complianceactivation-section"></a>Sekcja zgodności/aktywacji

| Nazwa porzucenia | Ekran lub przepływ | Platforma | Akcja |
| ---- |---- |---- |---- |
| Zgodność | Zgodność urządzenia (jeśli skonfigurowano przez administratora) wyświetlana w kolorze innym niż zielony podczas konfigurowania dostępu po zarejestrowaniu| iOS/Android | **Odłóż** |
| Zgodność | Zgodność urządzenia wyświetlana w kolorze innym niż zielony do chwili zaktualizowania do wyświetlania w kolorze zielonym | iOS/Android | Czas trwania > 30 minut |
| Aktywacja | Aktywacja rejestracji (jeśli skonfigurowano przez administratora) wyświetlana w kolorze innym niż zielony podczas konfigurowania dostępu | iOS/Android | **Odłóż** |
| Zgodność | Aktywacja urządzenia wyświetlana w kolorze innym niż zielony do chwili zaktualizowania do wyświetlania w kolorze zielonym | iOS/Android | Czas trwania > 30 minut |

## <a name="next-steps"></a>Następne kroki

Po sprawdzeniu współczynników porzucania możesz przejrzeć [opcje rejestracji](enrollment-options.md), aby przekonać się, czy można wprowadzić jakieś zmiany w celu udoskonalenia rejestracji.