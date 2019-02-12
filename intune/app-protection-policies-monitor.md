---
title: Monitorowanie zasad ochrony aplikacji
titleSuffix: Microsoft Intune
description: Monitorowanie stanu zgodności zasad zarządzania aplikacjami mobilnymi w usłudze Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/08/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7efa888344b91c74672563730bbdea6c7424214b
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55835099"
---
# <a name="how-to-monitor-app-protection-policies"></a>Monitorowanie zasad ochrony aplikacji
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Możesz monitorować stan zgodności zasad zarządzania aplikacjami mobilnymi (MAM, Mobile Application Management), które zostały zastosowane do użytkowników w okienku ochrony aplikacji usługi Intune w [witrynie Azure Portal](https://portal.azure.com). Dostępne są informacje o użytkownikach, których dotyczą zasady zarządzania aplikacjami mobilnymi, o ich stanie zgodności, a także o wszelkich problemach, które mogą napotykać użytkownicy.

Monitorowanie stanu zgodności jest możliwe w trzech miejscach:

-   Widok podsumowania

-   Widok szczegółowy

-   Widok raportowania

> [!NOTE]
> Aby uzyskać więcej informacji na temat tworzenia zasad ochrony aplikacji, zobacz [How to create and assign app protection policies](app-protection-policies.md) (Jak tworzyć i przypisywać zasady ochrony aplikacji).

## <a name="summary-view"></a>Widok podsumowania

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Aplikacje klienckie**.
4. W obciążeniu **Aplikacje klienckie** wybierz pozycję **Stan ochrony aplikacji** w sekcji **Monitor**, aby wyświetlić widok podsumowania:

![Kafelek podsumowania w okienku zarządzania aplikacjami mobilnymi usługi Intune](./media/app-protection-user-status-summary.png)

-   **Przypisani użytkownicy**: Całkowita liczba przypisanych użytkowników w firmie korzystających z aplikacji, którzy są powiązani z zasadami w kontekście służbowym oraz są chronieni i licencjonowani, jak również przypisanych użytkowników, którzy są niechronieni i nielicencjonowani.
-   **Oflagowani użytkownicy:** liczba użytkowników, którzy napotykają problemy. Urządzenia ze zdjętymi zabezpieczeniami systemu są zgłaszane w sekcji **Oflagowani użytkownicy**.
-   **Stan użytkownika dla systemu iOS** i **Stan użytkownika dla systemu Android**: Liczba użytkowników, którzy korzystali z aplikacji i mają przypisane zasady w kontekście służbowym dla powiązanej platformy. Zawiera liczbę użytkowników zarządzanych przez zasady, jak również liczbę użytkowników, którzy korzystają z aplikacji, ale nie są objęci żadnymi zasadami w kontekście służbowym. Można rozważyć dodanie tych użytkowników do zasad.

    > [!NOTE]
    > Jeśli istnieje wiele zasad dla platformy, użytkownik jest traktowany jako zarządzany przez zasady, gdy ma przypisane co najmniej jedne zasady.

## <a name="detailed-view"></a>Widok szczegółowy
Aby uzyskać szczegółowy widok podsumowania, wybierz kafelek **Stan użytkownika** (odpowiednio do platformy systemu operacyjnego urządzenia) i kafelek **Oflagowani użytkownicy**.

### <a name="user-status"></a>Stan użytkownika
Możesz wyszukać pojedynczego użytkownika i sprawdzić jego stan zgodności. Okienko **Raportowanie aplikacji** pokazuje następujące informacje dotyczące wybranego użytkownika:
- Urządzenia, które są skojarzone z kontem użytkownika

- Aplikacje z zasadami zarządzania aplikacjami mobilnymi na urządzeniu

- Stan:

  - **Zaewidencjonowano:** zasady zostały wdrożone względem użytkownika, a aplikacja została co najmniej raz użyta w kontekście służbowym.

  - **Nie zaewidencjonowano:** zasady zostały wdrożone względem użytkownika, ale od tego momentu aplikacja nie była używana w kontekście służbowym.

>[!NOTE]
> Jeśli poszukiwany użytkownik nie ma wdrożonych zasad zarządzania aplikacjami mobilnymi, pojawi się komunikat z informacją, że użytkownik nie jest objęty przez żadne zasady dotyczące zarządzania aplikacjami mobilnymi.

Aby wyświetlić raportowanie dla użytkownika, wykonaj następujące kroki:

1.  Aby wybrać użytkownika, wybierz kafelek podsumowania **Stan użytkownika**.

    ![Zrzut ekranu przedstawiający kafelek Podsumowanie bloku zarządzania aplikacjami mobilnymi usługi Intune](./media/MAM-reporting-6.png)

2. W okienku **Raportowanie aplikacji**, które się otworzy, wybierz opcję **Wybierz użytkownika**, aby wyszukać użytkownika w usłudze Azure Active Directory.

    ![Zrzut ekranu przedstawiający opcję Wybierz użytkownika w okienku Raportowanie aplikacji](./media/MAM-reporting-2.png)

3. Wybierz użytkownika z listy. Zostaną wyświetlone szczegółowe informacje o stanie zgodności tego użytkownika.

### <a name="flagged-users"></a>Oflagowani użytkownicy
W widoku szczegółowym wyświetlane są: komunikat o błędzie, aplikacja używana w momencie wystąpienia błędu, platforma systemu operacyjnego urządzenia, której dotyczy błąd, oraz sygnatura czasowa.

## <a name="reporting-view"></a>Widok raportowania

Możesz znaleźć te same raporty w bloku **Stan ochrony aplikacji**.

> [!NOTE]
> Usługa Intune udostępnia dodatkowe pola raportów dotyczących urządzeń, takie jak na przykład identyfikator rejestracji aplikacji, producent systemu Android, model i wersja poprawki zabezpieczeń, a także model urządzenia z systemem iOS. W usłudze Intune te pola są dostępne po wybraniu opcji **Aplikacje klienckie** > **Stan ochrony aplikacji** i wybraniu pozycji **Raport ochrony aplikacji: iOS, Android**. Ponadto te parametry będą pomocne w przypadku konfigurowania listy **dozwolonych** dla producenta urządzenia (Android), listy **dozwolonych** dla modelu urządzenia (Android i iOS) oraz ustawienia minimalnej wersji poprawki zabezpieczeń systemu Android. 

Są dostępne dodatkowe raporty, które ułatwiają sprawdzanie stanu zgodności zasad zarządzania aplikacjami mobilnymi. Aby wyświetlić te raporty, wybierz pozycję **Aplikacje klienckie** > **Stan ochrony aplikacji** > **Raporty**. 

Blok **Raporty** zawiera kilka raportów utworzonych na podstawie użytkownika i aplikacji, w tym między innymi:


-   **Raport użytkownika**: Ten raport zawiera te same informacje, które znajdują się w raporcie **Stan użytkownika** w sekcji widoku szczegółowego opisanej powyżej.

-   **Raport aplikacji**: Ten raport zawiera dwa różne stany ochrony aplikacji, które administratorzy mogą wybrać przed wygenerowaniem raportu. Te stany to: chronione lub niechronione.

    -   Stan użytkownika odnoszący się do zarządzanych działań z zakresu zarządzania aplikacjami mobilnymi (chroniony): ten raport podsumowuje działanie każdej zarządzanej aplikacji objętej zarządzaniem aplikacjami mobilnymi, przy czym dane odnoszą się do poszczególnych użytkowników.

        -   Raport uwzględnia wszystkie aplikacje objęte zasadami zarządzania aplikacjami mobilnymi dla każdego z użytkowników i określa stan każdej aplikacji, który może sygnalizować, że aplikacja została zaewidencjonowana z użyciem zasad zarządzania aplikacjami mobilnymi lub że podlegała im, ale nie została nigdy zaewidencjonowana.
<br><br>
    -   Stan użytkownika dla niezarządzanego działania z zakresu zarządzania aplikacjami mobilnymi (niechroniony): ten raport podsumowuje działanie aplikacji z włączonym zarządzaniem aplikacjami mobilnymi, które nie są obecnie zarządzane, przy czym dane odnoszą się do poszczególnych użytkowników. Przyczyny takiej sytuacji mogą być następujące:

        -   Aplikacje te są używane przez użytkownika lub przez aplikację, w odniesieniu do których nie mają obecnie zastosowania żadne zasady zarządzania aplikacjami mobilnymi.

        -   Wszystkie aplikacje są zaewidencjonowane, nie są jednak objęte żadnymi zasadami zarządzania aplikacjami mobilnymi.

![Zrzut ekranu przedstawiający blok raportowania aplikacji użytkownika ze szczegółami dla 3 aplikacji](./media/MAM-reporting-4.png)

## <a name="table-grouping"></a>Grupowanie tabel

Gdy zostanie wyświetlony **Raport użytkownika dotyczący ochrony aplikacji**, możesz zagregować dane według następujących właściwości:

- **Wynik weryfikacji:** wyświetlane dane są pogrupowane według stanu ochrony aplikacji; możliwe stany to niepowodzenie, ostrzeżenie lub powodzenie.
- **Nazwa aplikacji:** Wyświetlane dane są pogrupowane według rzeczywistych nazw aplikacji, dla których jest także określony stan: niepowodzenie, ostrzeżenie lub powodzenie.

## <a name="export-app-protection-activities-to-csv"></a>Eksportowanie działań z zakresu ochrony aplikacji do formatu CSV

Możesz wyeksportować wszystkie działania z zakresu zasad ochrony aplikacji do jednego pliku o rozszerzeniu .csv. Tego rodzaju plik może okazać się przydatny podczas analizy wszystkich stanów ochrony aplikacji zgłaszanych przez użytkowników.

Wykonaj następujące kroki, aby wygenerować raport dotyczący ochrony aplikacji:

1. W okienku zarządzania aplikacjami mobilnymi usługi Intune wybierz **raport dotyczący ochrony aplikacji**.

    ![Zrzut ekranu przedstawiający link pobierania raportu dotyczącego ochrony aplikacji](./media/app-protection-report-csv-2.png)

2. Wybierz opcję Tak, aby zapisać raport, a następnie wybierz polecenie Zapisz jako i wybierz folder, w którym chcesz zapisać raport.

    ![Zrzut ekranu przedstawiający okno dialogowe z potwierdzeniem opcji Zapisz raport](./media/app-protection-report-csv-1.png)

## <a name="see-also"></a>Zobacz także
[Zarządzanie przesyłaniem danych między aplikacjami systemu iOS](data-transfer-between-apps-manage-ios.md)

* [Czego można oczekiwać, gdy aplikacja dla systemu Android jest zarządzana przy użyciu zasad ochrony aplikacji](app-protection-enabled-apps-android.md)
* [Czego można oczekiwać, gdy aplikacja systemu iOS jest zarządzana przy użyciu zasad ochrony aplikacji](app-protection-enabled-apps-ios.md)
