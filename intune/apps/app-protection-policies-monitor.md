---
title: Monitorowanie zasad ochrony aplikacji
titleSuffix: Microsoft Intune
description: W tym temacie opisano sposób monitorowania zasad ochrony aplikacji w usłudze Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/09/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9d82813f1292c99cf248c56a102503413d2cb8fb
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72507456"
---
# <a name="how-to-monitor-app-protection-policies"></a>Monitorowanie zasad ochrony aplikacji
[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Możesz monitorować stan zgodności zasad zarządzania aplikacjami mobilnymi (MAM), które zostały zastosowane do użytkowników w okienku ochrony aplikacji usługi Intune w witrynie [Azure Portal](https://portal.azure.com). Ponadto możesz wyszukiwać informacje o użytkownikach, których dotyczą zasady zarządzania aplikacjami mobilnymi, o stanie zgodności tych zasad, a także o wszelkich problemach, które mogą napotykać użytkownicy.

Zasady ochrony aplikacji można monitorować w trzech różnych miejscach:
- Widok podsumowania
- Widok szczegółowy
- Widok raportowania

> [!NOTE]
> Aby uzyskać szczegółowe informacje, zobacz [Tworzenie i przypisywanie zasad ochrony aplikacji](app-protection-policies.md).

Okres przechowywania danych ochrony aplikacji to 90 dni. Wszystkie wystąpienia aplikacji, które zostały zaewidencjonowane do usługi zarządzania aplikacjami mobilnymi w ciągu ostatnich 90 dni, są uwzględniane w raporcie o stanie ochrony aplikacji. *Wystąpienie aplikacji* to unikatowa kombinacja użytkownika, aplikacji i urządzenia. 

## <a name="summary-view"></a>Widok podsumowania

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. W okienku **Intune** wybierz pozycję **Aplikacje klienckie**.
4. Aby wyświetlić widok podsumowania, w obciążeniu **Aplikacje klienckie** w obszarze **Monitor** wybierz pozycję **Stan ochrony aplikacji**.

   ![Zrzut ekranu przedstawiający kafelek podsumowania w okienku zarządzania aplikacjami mobilnymi usługi Intune](./media/app-protection-policies-monitor/app-protection-user-status-summary.png)

- **Przypisani użytkownicy**: Całkowita liczba przypisanych użytkowników w firmie korzystających z aplikacji, którzy są powiązani z zasadami w kontekście służbowym oraz są chronieni i licencjonowani, jak również przypisanych użytkowników, którzy są niechronieni i nielicencjonowani.
- **Oflagowani użytkownicy:** Liczba użytkowników, którzy napotykają problemy ze swoimi urządzeniami. Urządzenia ze zdjętymi zabezpieczeniami systemu (iOS) i z dostępem do konta root (Android) są zgłaszane w sekcji **Oflagowani użytkownicy**. Ponadto w tym miejscu są zgłaszani użytkownicy urządzeń oflagowanych podczas sprawdzania zaświadczania urządzenia rozwiązania Google SafetyNet (jeśli zostało włączone przez administratora IT). 
- **Użytkownicy z potencjalnie szkodliwymi aplikacjami**: Liczba użytkowników, którzy mogą mieć na urządzeniu z systemem Android szkodliwą aplikację wykrytą przez funkcję Google Play Protect. 
- **Stan użytkownika dla systemu iOS** i **Stan użytkownika dla systemu Android**: Liczba użytkowników, którzy korzystali z aplikacji i mają przypisane zasady w kontekście służbowym dla powiązanej platformy. Zawiera liczbę użytkowników zarządzanych przez zasady, jak również liczbę użytkowników, którzy korzystają z aplikacji, ale nie są objęci żadnymi zasadami w kontekście służbowym. Można rozważyć dodanie tych użytkowników do zasad.
- **Najlepsze chronione aplikacje systemu iOS**: ta informacja to liczba chronionych i niechronionych aplikacji systemu iOS określana w oparciu o najczęściej częściej używane aplikacje systemu iOS.
- **Najlepsze chronione aplikacje systemu Android**: ta informacja to liczba chronionych i niechronionych aplikacji systemu Android określana w oparciu o najczęściej częściej używane aplikacje systemu Android.
- **Najważniejsze skonfigurowane aplikacje systemu iOS bez rejestracji**: ta informacja to liczba skonfigurowanych aplikacji systemu iOS określana w oparciu o najczęściej częściej używane aplikacje systemu iOS dla niezarejestrowanych urządzeń.
- **Najważniejsze skonfigurowane aplikacje systemu Android bez rejestracji**: ta informacja to liczba skonfigurowanych aplikacji systemu Android określana w oparciu o najczęściej używane aplikacje systemu Android dla niezarejestrowanych urządzeń.

    > [!NOTE]
    > Jeśli istnieje wiele zasad dla platformy, użytkownik jest traktowany jako zarządzany przez zasady, gdy ma przypisane co najmniej jedne zasady.

## <a name="detailed-view"></a>Widok szczegółowy
Aby uzyskać szczegółowy widok podsumowania, wybierz kafelek **Stan użytkownika** (odpowiednio do platformy systemu operacyjnego urządzenia), kafelek **Użytkownicy z potencjalnie szkodliwymi aplikacjami** oraz kafelek **Oflagowani użytkownicy**.

### <a name="user-status"></a>Stan użytkownika
Możesz wyszukać pojedynczego użytkownika i sprawdzić jego stan zgodności. Okienko **Raportowanie aplikacji** pokazuje następujące informacje dotyczące wybranego użytkownika:
- **Ikona**: Wskazuje, czy stan aplikacji jest aktualny.
- **Nazwa aplikacji**: Nazwa aplikacji.
- **Nazwa urządzenia**: urządzenia skojarzone z kontem użytkownika.
- **Typ urządzenia**: typ urządzenia lub system operacyjny uruchomiony na urządzeniu.
- **Zasady**: zasady skojarzone z aplikacją.
- **Stan**:
  - **Zaewidencjonowano:** zasady zostały wdrożone względem użytkownika, a aplikacja została co najmniej raz użyta w kontekście służbowym.
  - **Nie zaewidencjonowano:** zasady zostały wdrożone względem użytkownika, ale od tego momentu aplikacja nie była używana w kontekście służbowym.
- **Ostatnia synchronizacja**: kiedy aplikacja była ostatnio synchronizowana z usługą Intune. 

>[!NOTE]
> Kolumna **Ostatnia synchronizacja** przedstawia tę samą wartość zarówno w raporcie o stanie użytkownika w konsoli, jak i w [możliwym do wyeksportowania raporcie csv](https://docs.microsoft.com/intune/app-protection-policies-monitor#export-app-protection-activities-to-csv) zasad ochrony aplikacji. Różnica polega na małym opóźnieniu synchronizacji między tą wartością w tych dwóch raportach. 
>
> Czas podawany w kolumnie „Ostatnia synchronizacja” to czas, gdy usługa Intune po raz ostatni widziała wystąpienie aplikacji. Kiedy użytkownik uruchamia aplikację, może ona powiadomić usługę Intune App Protection w momencie uruchomienia, w zależności od czasu ostatniego zaewidencjonowania. Zobacz artykuł dotyczący [czasów interwałów ponowień dla ewidencjonowania zasad ochrony aplikacji](https://docs.microsoft.com/en-us/intune/app-protection-policy-delivery). Jeśli użytkownik końcowy nie używał tej konkretnej aplikacji w ostatnim interwale ewidencjonowania (który zazwyczaj wynosi 30 minut dla aktywnego użycia), a następnie uruchomił aplikację, to:
>
> - Możliwy do wyeksportowania raport csv zasad ochrony aplikacji będzie zawierać najnowszy czas w zakresie od 1 minuty (wartość minimalna) do 30 minut (wartość maksymalna).
> - Raport stanu użytkownika będzie od razu zawierał najnowszy czas.
>
> Rozważmy na przykład docelowego i licencjonowanego użytkownika, który uruchamia chronioną aplikację o godzinie 12:00:
> - Jeśli jest to pierwsze logowanie, oznacza to, że wcześniej ten użytkownik był wylogowany i nie ma rejestracji wystąpienia aplikacji w usłudze Intune. Po zalogowaniu się użytkownik uzyskuje nową rejestrację wystąpienia aplikacji i może zostać natychmiast zaewidencjonowany (z tymi samymi opóźnieniami, które zostały wymienione wcześniej, dla przyszłych operacji ewidencjonowania). Dlatego czas ostatniej synchronizacji w raporcie stanu użytkownika ma wartość 12:00, a w raporcie zasad ochrony aplikacji 12:01 (lub w najgorszym przypadku 12:30). 
> - Jeśli użytkownik tylko uruchamia aplikację, zaraportowany czas ostatniej synchronizacji zależy od czasu ostatniego zaewidencjonowania użytkownika.


Aby wyświetlić raportowanie dla użytkownika, wykonaj następujące kroki:

1. Aby wybrać użytkownika, wybierz kafelek podsumowania **Stan użytkownika**.

    ![Zrzut ekranu przedstawiający kafelek Podsumowanie bloku zarządzania aplikacjami mobilnymi usługi Intune](./media/app-protection-policies-monitor/MAM-reporting-6.png)

2. W okienku **Raportowanie aplikacji** wybierz pozycję **Wybierz użytkownika**, aby wyszukać użytkownika usługi Azure Active Directory.

    ![Zrzut ekranu przedstawiający opcję Wybierz użytkownika w okienku Raportowanie aplikacji](./media/app-protection-policies-monitor/MAM-reporting-2.png)

3. Wybierz użytkownika z listy. Zostaną wyświetlone szczegółowe informacje o stanie zgodności tego użytkownika.

>[!NOTE]
> Jeśli poszukiwany użytkownik nie ma wdrożonych zasad zarządzania aplikacjami mobilnymi, pojawi się komunikat z informacją, że użytkownik nie jest objęty przez żadne zasady dotyczące zarządzania aplikacjami mobilnymi.

### <a name="flagged-users"></a>Oflagowani użytkownicy
W widoku szczegółowym wyświetlane są: komunikat o błędzie, aplikacja używana w momencie wystąpienia błędu, platforma systemu operacyjnego urządzenia, której dotyczy błąd, oraz sygnatura czasowa. Ten błąd zazwyczaj występuje w przypadku urządzeń ze zdjętymi zabezpieczeniami systemu (iOS) lub z odblokowanym dostępem (Android). W tym miejscu są także zgłaszani użytkownicy urządzeń oflagowanych podczas sprawdzania uruchomienia warunkowego „zaświadczania urządzenia rozwiązania SafetyNet” z przyczyną zgłoszoną przez firmę Google. Aby użytkownik został usunięty z raportu, musi zmienić się stan samego urządzenia. Ma to miejsce po następnym sprawdzeniu odblokowania dostępu (lub sprawdzeniu zdjęcia zabezpieczeń systemu/SafetyNet) ze zgłoszonym pozytywnym wynikiem. Jeśli urządzenie zostanie naprawdę skorygowane, odświeżenie raportu Oflagowani użytkownicy nastąpi po ponownym załadowaniu bloku.

### <a name="users-with-potentially-harmful-apps"></a>Użytkownicy z potencjalnie szkodliwymi aplikacjami
Widok szczegółowy pokazuje następujące dane:

- Użytkownik.
- Identyfikator pakietu aplikacji.
- Czy aplikacja jest objęta zarządzaniem aplikacjami mobilnymi.
- Kategoria zagrożenia.
- Adres e-mail.
- Nazwa urządzenia.
- Sygnatura czasowa.

W tym miejscu są zgłaszani użytkownicy urządzeń oflagowanych podczas sprawdzania uruchomienia warunkowego **wymagania skanowania zagrożeń w aplikacjach** z kategorią zagrożenia zgłoszoną przez firmę Google. Jeśli w tym raporcie znajdują się aplikacje, które są wdrażane za pośrednictwem usługi Intune, skontaktuj się z deweloperem aplikacji lub usuń aplikację z przypisywania do użytkowników. 

## <a name="reporting-view"></a>Widok raportowania

Te same raporty możesz znaleźć w górnej części bloku **Stan ochrony aplikacji**.

> [!NOTE]
> Usługa Intune udostępnia dodatkowe pola raportów dotyczących urządzeń, takie jak na przykład identyfikator rejestracji aplikacji, producent systemu Android, model i wersja poprawki zabezpieczeń, a także model urządzenia z systemem iOS. W usłudze Intune te pola są dostępne po wybraniu pozycji **Aplikacje klienckie** > **Stan ochrony aplikacji** > **Raport ochrony aplikacji: iOS, Android**. Ponadto te parametry są pomocne w konfigurowaniu listy **dozwolonych** dla producenta urządzenia (Android), listy **dozwolonych** dla modelu urządzenia (Android i iOS) oraz ustawienia minimalnej wersji poprawki zabezpieczeń systemu Android. 

Są dostępne dodatkowe raporty, które ułatwiają sprawdzanie stanu zgodności zasad zarządzania aplikacjami mobilnymi. Aby wyświetlić te raporty, wybierz pozycję **Aplikacje klienckie** > **Stan ochrony aplikacji** > **Raporty**. 

Blok **Raporty** zawiera kilka raportów utworzonych na podstawie użytkownika i aplikacji, w tym między innymi:

- **Raport użytkownika**: ten raport zawiera te same informacje, które znajdują się w raporcie **Stan użytkownika** w sekcji [Widok szczegółowy](app-protection-policies-monitor.md#detailed-view) opisanej powyżej.

- **Raport aplikacji**: oprócz opcji wybrania platformy i aplikacji ten raport zawiera dwa różne stany ochrony aplikacji, które administratorzy mogą wybrać przed wygenerowaniem raportu. Te stany to **Chronione** lub **Niechronione**.

  - Stan użytkownika odnoszący się do zarządzanych działań z zakresu zarządzania aplikacjami mobilnymi (**Chronione**): Ten raport podsumowuje działanie każdej zarządzanej aplikacji objętej zarządzaniem aplikacjami mobilnymi, przy czym dane odnoszą się do poszczególnych użytkowników. Raport uwzględnia wszystkie aplikacje objęte zasadami zarządzania aplikacjami mobilnymi dla każdego z użytkowników i określa stan każdej aplikacji jako zaewidencjonowany z użyciem zasad zarządzania aplikacjami mobilnymi. Raport zawiera również stan każdej aplikacji, która podlegała zasadom zarządzania aplikacjami mobilnymi, ale nie została nigdy zaewidencjonowana.
  - Stan użytkownika dla niezarządzanego działania z zakresu zarządzania aplikacjami mobilnymi (**Niechronione**): Ten raport podsumowuje działanie aplikacji z włączonym zarządzaniem aplikacjami mobilnymi, które nie są obecnie zarządzane, przy czym dane odnoszą się do poszczególnych użytkowników. Może się tak zdarzyć, ponieważ:
    - Aplikacje te są używane przez użytkownika lub przez aplikację, w odniesieniu do których nie mają obecnie zastosowania żadne zasady zarządzania aplikacjami mobilnymi.
    - Wszystkie aplikacje są zaewidencjonowane, nie są jednak objęte żadnymi zasadami zarządzania aplikacjami mobilnymi.

    ![Zrzut ekranu przedstawiający blok raportowania aplikacji użytkownika ze szczegółami dla trzech aplikacji](./media/app-protection-policies-monitor/MAM-reporting-4.png)

- **Raport dotyczący konfiguracji użytkownika**: w oparciu o wybranego użytkownika ten raport zawiera szczegółowe informacje o konfiguracjach aplikacji odebranych przez użytkownika.
- **Raport dotyczący konfiguracji aplikacji**: o oparciu o wybraną platformę i aplikację ten raport zawiera szczegółowe informacje o użytkownikach, którzy otrzymali konfiguracje wybranej aplikacji.
- **Raport dotyczący uczenia aplikacji na potrzeby rozwiązania Windows Information Protection**: ten raport przedstawia aplikacje, które próbują przekroczyć granice między zasadami.
- **Uczenie dotyczące witryn internetowych na potrzeby rozwiązania Windows Information Protection**: ten raport przedstawia witryny internetowe, które próbują przekroczyć granice między zasadami.

## <a name="table-grouping"></a>Grupowanie tabel

Gdy zostaną wyświetlone dane z **Raportu użytkownika dotyczącego ochrony aplikacji**, możesz zagregować je według następujących właściwości:

- **Wynik weryfikacji**: Dane są pogrupowane według stanu ochrony aplikacji; możliwe stany to „niepowodzenie”, „ostrzeżenie” lub „powodzenie”.
- **Nazwa aplikacji**: Dane są pogrupowane według rzeczywistej nazwy aplikacji. Możliwe stany to „niepowodzenie”, „ostrzeżenie” lub „powodzenie”.

## <a name="export-app-protection-activities"></a>Eksportowanie działań z zakresu ochrony aplikacji

Możesz wyeksportować wszystkie działania z zakresu zasad ochrony aplikacji do jednego pliku o rozszerzeniu .csv. Tego rodzaju plik może okazać się przydatny podczas analizy wszystkich stanów ochrony aplikacji zgłaszanych przez użytkowników.

Wykonaj następujące kroki, aby wygenerować raport dotyczący ochrony aplikacji:

1. W okienku zarządzania aplikacjami mobilnymi usługi Intune wybierz **raport dotyczący ochrony aplikacji**.

    ![Zrzut ekranu przedstawiający link pobierania raportu dotyczącego ochrony aplikacji](./media/app-protection-policies-monitor/app-protection-report-csv-2.png)

2. Wybierz pozycję **Tak**, aby zapisać raport, a następnie wybierz pozycję **Zapisz jako**. Wybierz folder, w którym chcesz zapisać raport.

    ![Zrzut ekranu przedstawiający okno dialogowe z potwierdzeniem opcji Zapisz raport](./media/app-protection-policies-monitor/app-protection-report-csv-1.png)

## <a name="see-also"></a>Zobacz także
- [Zarządzanie przesyłaniem danych między aplikacjami systemu iOS](data-transfer-between-apps-manage-ios.md)
- [Czego można oczekiwać, gdy aplikacja dla systemu Android jest zarządzana przy użyciu zasad ochrony aplikacji](../fundamentals/end-user-mam-apps-android.md)
- [Czego można oczekiwać, gdy aplikacja systemu iOS jest zarządzana przy użyciu zasad ochrony aplikacji](../fundamentals/end-user-mam-apps-ios.md)
