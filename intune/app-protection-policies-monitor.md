---
title: Monitorowanie zasad ochrony aplikacji
titleSuffix: Intune on Azure
description: "Zobacz, jak wielu użytkowników korzysta z zasad, i poznaj więcej szczegółów."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 978e32476069183865f7e729de9791e13bc81ebc
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2017
---
# <a name="how-to-monitor-app-protection-policies"></a>Monitorowanie zasad ochrony aplikacji
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Jeśli nie korzystasz z portalu Azure Portal**, w tym temacie znajdziesz opis sposobu [tworzenia zasad ochrony aplikacji](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) w klasycznej konsoli usługi Intune.


Możesz monitorować stan zgodności zasad zarządzania aplikacjami mobilnymi (MAM, ang. Mobile Application Management), które zostały zastosowane do użytkowników w bloku ochrony aplikacji usługi Intune w [witrynie Azure Portal](https://portal.azure.com). Dostępne są informacje o użytkownikach, których dotyczą zasady zarządzania aplikacjami mobilnymi, o ich stanie zgodności, a także o wszelkich problemach, które mogą napotykać użytkownicy.

Monitorowanie stanu zgodności jest możliwe w trzech miejscach:

-   Widok podsumowania

-   Widok szczegółowy

-   Widok raportowania

## <a name="summary-view"></a>Widok podsumowania

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz pozycję **Aplikacje mobilne**.
4. W obciążeniu **Aplikacje mobilne** wybierz kolejno pozycje **Monitor** > **Stan użytkownika ochrony aplikacji**, aby wyświetlić widok podsumowania:

![Kafelek podsumowania w bloku zarządzania aplikacjami mobilnymi usługi Intune](./media/app-protection-user-status-summary.png)

-   **Użytkownicy**: całkowita liczba użytkowników w firmie, którzy korzystają z aplikacji skojarzonej z zasadami w kontekście służbowym.

-   **ZARZĄDZANE PRZEZ ZASADY**: liczba użytkowników, którzy korzystali z aplikacji i mają zasady przypisane do nich w kontekście służbowym.

-   **BRAK ZASAD**: liczba użytkowników, którzy korzystają z aplikacji, ale nie są objęci żadnymi zasadami w kontekście służbowym. Można rozważyć dodanie tych użytkowników do zasad.
    > [!NOTE]
    > Jeśli istnieje wiele zasad dla platformy, użytkownik będzie traktowany jako zarządzany przez zasady, jeśli ma przypisaną co najmniej jedną zasadę.

- **Oflagowani użytkownicy:** liczba użytkowników, którzy napotykają problemy. Obecnie tylko użytkownicy z urządzeniami ze zdjętymi zabezpieczeniami systemu są zgłaszani w sekcji **Oflagowani użytkownicy**.


## <a name="detailed-view"></a>Widok szczegółowy
Aby uzyskać szczegółowy widok podsumowania, wybierz kafelek **Stan użytkownika** (odpowiednio do platformy systemu operacyjnego urządzenia) i kafelek **Oflagowani użytkownicy**.

### <a name="user-status"></a>Stan użytkownika
Możesz wyszukać pojedynczego użytkownika i sprawdzić jego stan zgodności. Blok **Raportowanie aplikacji** pokazuje następujące informacje dotyczące wybranego użytkownika:
- Urządzenia, które są skojarzone z kontem użytkownika

- Aplikacje z zasadami zarządzania aplikacjami mobilnymi na urządzeniu

- Stan:

  - **Zaewidencjonowano:** zasady zostały wdrożone względem użytkownika, a aplikacja została co najmniej raz użyta w kontekście służbowym.

  - **Nie zaewidencjonowano:** zasady zostały wdrożone względem użytkownika, ale od tego momentu aplikacja nie była używana w kontekście służbowym.

>[!NOTE]
> Jeśli poszukiwany użytkownik nie ma wdrożonych zasad zarządzania aplikacjami mobilnymi, pojawi się komunikat z informacją, że użytkownik nie jest objęty przez żadne zasady dotyczące zarządzania aplikacjami mobilnymi.

Aby wyświetlić raportowanie dla użytkownika, wykonaj następujące kroki:

1.  Aby wybrać użytkownika, wybierz kafelek **Podsumowanie**.

    ![Zrzut ekranu nr 3](./media/MAM-reporting-6.png)

2. W bloku **Raportowanie aplikacji**, który się otworzy, wybierz opcję **Wybierz użytkownika**, aby wyszukać użytkownika w usłudze Azure Active Directory.

    ![Opcja Wybierz użytkownika w bloku Raportowanie aplikacji](./media/MAM-reporting-2.png)

3. Wybierz użytkownika z listy. Zostaną wyświetlone szczegółowe informacje o stanie zgodności tego użytkownika.

### <a name="flagged-users"></a>Oflagowani użytkownicy
W widoku szczegółowym wyświetlane są: komunikat o błędzie, aplikacja używana w momencie wystąpienia błędu, platforma systemu operacyjnego urządzenia, której dotyczy błąd, oraz sygnatura czasowa.

## <a name="reporting-view"></a>Widok raportowania

Możesz uzyskać dostęp do tych samych raportów, które są wyświetlane w widoku szczegółowym, a także do dodatkowych raportów ułatwiających sprawdzenie stanu zgodności zasad zarządzania aplikacjami mobilnymi:

![Zrzut ekranu nr 4](./media/MAM-reporting-7.png)

-   **Raport użytkownika dotyczący ochrony aplikacji:** zawiera te same informacje, które znajdują się w raporcie **Stan użytkownika** w sekcji widoku szczegółowego opisanej powyżej.

-   **Raport aplikacji dotyczący ochrony aplikacji:** zawiera dwa różne stany ochrony aplikacji, które administratorzy mogą wybrać przed wygenerowaniem raportu. Te stany to: chronione lub niechronione.

    -   Stan użytkownika odnoszący się do zarządzanych działań z zakresu zarządzania aplikacjami mobilnymi (chroniony): ten raport podsumowuje działanie każdej zarządzanej aplikacji objętej zarządzaniem aplikacjami mobilnymi, przy czym dane odnoszą się do poszczególnych użytkowników.

        -   Raport uwzględnia wszystkie aplikacje objęte zasadami zarządzania aplikacjami mobilnymi dla każdego z użytkowników i określa stan każdej aplikacji, który może sygnalizować, że aplikacja została zaewidencjonowana z użyciem zasad zarządzania aplikacjami mobilnymi lub że podlegała im, ale nie została nigdy zaewidencjonowana.
<br></br>
    -   Stan użytkownika dla niezarządzanego działania z zakresu zarządzania aplikacjami mobilnymi (niechroniony): ten raport podsumowuje działanie aplikacji z włączonym zarządzaniem aplikacjami mobilnymi, które nie są obecnie zarządzane, przy czym dane odnoszą się do poszczególnych użytkowników. Przyczyny takiej sytuacji mogą być następujące:

        -   Aplikacje te są używane przez użytkownika lub przez aplikację, w odniesieniu do których nie mają obecnie zastosowania żadne zasady zarządzania aplikacjami mobilnymi.

        -   Wszystkie aplikacje są zaewidencjonowane, nie są jednak objęte żadnymi zasadami zarządzania aplikacjami mobilnymi.

![Zrzut ekranu nr 2](./media/MAM-reporting-4.png)

## <a name="table-grouping"></a>Grupowanie tabel

Gdy zostanie wyświetlony **Raport użytkownika dotyczący ochrony aplikacji**, możesz zagregować dane według następujących właściwości:

- **Wynik weryfikacji:** wyświetlane dane są pogrupowane według stanu ochrony aplikacji; możliwe stany to niepowodzenie, ostrzeżenie lub powodzenie.
- **Nazwa aplikacji:** wyświetlane dane są pogrupowane według rzeczywistych nazw aplikacji, dla których jest także określony stan: niepowodzenie, ostrzeżenie lub powodzenie.

## <a name="export-app-protection-activities-to-csv"></a>Eksportowanie działań z zakresu ochrony aplikacji do formatu CSV

Możesz wyeksportować wszystkie działania z zakresu zasad ochrony aplikacji do jednego pliku o rozszerzeniu .csv. Tego rodzaju plik może okazać się przydatny podczas analizy wszystkich stanów ochrony aplikacji zgłaszanych przez użytkowników.

Wykonaj następujące kroki, aby wygenerować raport dotyczący ochrony aplikacji:

1. W bloku zarządzania aplikacjami mobilnymi usługi Intune wybierz raport dotyczący ochrony aplikacji.

    ![Zrzut ekranu nr 6](./media/app-protection-report-csv-2.png)

2. Wybierz opcję Tak, aby zapisać raport, a następnie wybierz polecenie Zapisz jako i wybierz folder, w którym chcesz zapisać raport.

    ![Zrzut ekranu nr 7](./media/app-protection-report-csv-1.png)

## <a name="see-also"></a>Zobacz także
[Zarządzanie przesyłaniem danych między aplikacjami systemu iOS](data-transfer-between-apps-manage-ios.md)

* [Czego można oczekiwać, gdy aplikacja dla systemu Android jest zarządzana przy użyciu zasad ochrony aplikacji](app-protection-enabled-apps-android.md)
* [Czego można oczekiwać, gdy aplikacja systemu iOS jest zarządzana przy użyciu zasad ochrony aplikacji](app-protection-enabled-apps-ios.md)
