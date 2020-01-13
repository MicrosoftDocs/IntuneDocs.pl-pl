---
title: Monitorowanie zasad zgodności urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Pulpit nawigacyjny zgodności urządzeń służy do monitorowania ogólnej zgodności urządzeń, wyświetlania raportów i wyświetlania zgodności urządzeń z poszczególnymi zasadami i ustawieniami.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 89b4516017d7ac8bf1e27134db6a67a0a86b17cb
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206078"
---
# <a name="monitor-intune-device-compliance-policies"></a>Monitorowanie zasad zgodności urządzeń Intune

Raporty zgodności pomagają w weryfikowaniu zgodności urządzeń oraz rozwiązywaniu problemów związanych ze zgodnością w organizacji. Korzystanie z tych raportów zapewnia następujące informacje:

- Ogólny stan zgodności urządzeń
- Stan zgodności poszczególnych ustawień
- Stan zgodności poszczególnych zasad
- Przechodzenie do szczegółów dotyczących poszczególnych urządzeń w celu wyświetlenia konkretnych ustawień i zasad wpływających na te urządzenia

## <a name="open-the-compliance-dashboard"></a>Otwieranie pulpitu nawigacyjnego zgodności

Otwórz **pulpit nawigacyjny zgodności urządzeń w usłudze Intune**:

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz kartę **Urządzenia** > **Omówienie** > **Stan zgodności**.

> [!IMPORTANT]
> Aby otrzymać zasady zgodności urządzeń, urządzenia muszą być zarejestrowane w usłudze Intune.

## <a name="dashboard-overview"></a>Pulpit nawigacyjny — omówienie

Po otwarciu pulpitu nawigacyjnego możesz uzyskać omówienie zawierające wszystkie raporty zgodności. W tych raportach możesz zobaczyć i sprawdzić następujące elementy:

- Ogólna zgodność urządzenia
- Zgodność urządzeń wg zasady
- Zgodność urządzeń wg ustawienia
- Stan agenta zagrożeń
- Stan ochrony urządzenia

![Obraz pulpitu nawigacyjnego przedstawiający pulpit nawigacyjny zgodności urządzeń oraz różne raporty](./media/compliance-policy-monitor/idc-1.png)

Podczas przechodzenia do szczegółów raportów możesz też zobaczyć konkretne zasady zgodności i ustawienia mające zastosowanie do określonego urządzenia, w tym stan zgodności dla każdego ustawienia.

### <a name="device-compliance-status"></a>Stan zgodności urządzenia

Wykres **Stan zgodności urządzenia** przedstawia stany zgodności dla wszystkich urządzeń zarejestrowanych w usłudze Intune. Stany zgodności urządzeń są przechowywane w dwóch różnych bazach danych: Intune i Azure Active Directory.

> [!IMPORTANT]
> Usługa Intune wykonuje wszystkie oceny zgodności na urządzeniu zgodnie z jego harmonogramem ewidencjonowania. [Dowiedz się więcej o harmonogramie ewidencjonowania urządzenia](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

Opisy różnych stanów zasad zgodności urządzeń:

- **Zgodne**: urządzenie pomyślnie zastosowało co najmniej jedno ustawienie zasady zgodności urządzenia.

- **Okres prolongaty:** urządzenie jest urządzeniem docelowym dla co najmniej jednego ustawienia zasad zgodności urządzeń. Jednak użytkownik jeszcze nie zastosował zasad. Oznacza to, że urządzenie nie jest zgodne, ale jest w okresie prolongaty zdefiniowanym przez administratora.

  - Dowiedz się więcej o [akcjach dla niezgodnych urządzeń](actions-for-noncompliance.md).

- **Nie oceniono**: wstępny stan dla nowo zarejestrowanych urządzeń. Inne możliwe przyczyny tego stanu to między innymi:

  - Urządzenia, którym nie przypisano zasad zgodności i które nie mają wyzwalacza umożliwiającego sprawdzenie zgodności
  - Urządzenia, które nie zostały zaewidencjonowane od momentu ostatniej aktualizacji zasad zgodności
  - Urządzenia nieskojarzone z określonym użytkownikiem, takie jak:
    - Urządzenia z systemem iOS zakupione w ramach programu Device Enrollment Program (DEP) firmy Apple bez koligacji użytkownika
    - Urządzenia kiosku systemu Android lub dedykowane urządzenia z systemem Android Enterprise
  - Urządzenia zarejestrowane przy użyciu konta menedżera rejestracji urządzeń (DEM)

- **Niezgodne:** urządzenie nie zastosowało pomyślnie co najmniej jednego ustawienia zasad zgodności urządzenia. Lub użytkownik nie zapewnił zgodności z zasadami.

- **Urządzenie nie jest zsynchronizowane:** urządzenie nie zgłosiło stanu zasad zgodności urządzenia z jednej z następujących przyczyn:

  - **Nieznane**: urządzenie jest w trybie offline lub nie nawiązało łączności z usługą Intune lub Azure AD z innych przyczyn.

  - **Błąd**: urządzenie nie skomunikowało się z usługami Intune i Azure AD i otrzymało komunikat o błędzie wraz z powodem.

> [!IMPORTANT]
> Urządzenia, które są zarejestrowane w usłudze Intune, ale nie są objęte żadnymi zasadami zgodności urządzeń, są uwzględnione w raporcie w obszarze **Zgodne**.

#### <a name="drill-down-for-more-details"></a>Przechodzenie do szczegółów

Na wykresie **Stan zgodności urządzenia** wybierz stan. Na przykład wybierz stan **Niezgodne**:

![Wybieranie stanu braku zgodności](./media/compliance-policy-monitor/select-not-compliant-status.png)

Ta akcja powoduje otwarcie okna **Zgodność urządzenia** i wyświetlenie urządzeń na wykresie **Stan urządzenia**. Wykres przedstawia bardziej szczegółowe informacje dotyczące urządzeń w danym stanie, w tym platformy systemu operacyjnego, daty ostatniego zaewidencjonowania i innych danych.
![Obraz pulpitu nawigacyjnego przedstawiający bardziej szczegółowe informacje dotyczące urządzenia w określonym stanie](./media/compliance-policy-monitor/drill-down-details.png)

Jeśli chcesz zobaczyć wszystkie urządzenia stanowiące własność konkretnego użytkownika, możesz też filtrować raport z wykresem poprzez wpisanie adresu e-mail użytkownika.

#### <a name="filter-and-columns"></a>Filtr i kolumny

![Wybierz opcje Filtr i Kolumna, aby zmienić wyniki na wykresie](./media/compliance-policy-monitor/filter-columns.png)

Po wybraniu przycisku **Filtr** zostanie otworzone okno z większą liczbą opcji, w tym stanem **zgodności**, urządzeniami ze **zdjętymi zabezpieczeniami systemu** i innymi. **Zastosuj** filtr, aby zaktualizować wyniki.

Użyj właściwości **Kolumny**, aby dodać lub usunąć kolumny z danych wyjściowych wykresu. Przykładowo **Główna nazwa użytkownika** może pokazywać adres e-mail zarejestrowany na urządzeniu. **Zastosuj** kolumny, aby zaktualizować wyniki.

#### <a name="device-details"></a>Szczegóły urządzenia

Na wykresie **Szczegóły urządzenia** wybierz konkretne urządzenie, a następnie wybierz pozycję **Zgodność urządzenia**:

![Wybierz konkretne urządzenie, a następnie wybierz opcję Zgodność urządzenia, aby zobaczyć zastosowane zasady zgodności](./media/compliance-policy-monitor/see-policies-applied-specific-device.png)

Usługa Intune wyświetla więcej szczegółów dotyczących ustawień zasad zgodności urządzenia zastosowanych na danym urządzeniu. Po wybraniu określonych zasad zostaną wyświetlone wszystkie ustawienia w zasadach.

### <a name="devices-without-compliance"></a>Urządzenia bez zgodności

Na stronie *Stan zgodności* obok wykresu *Zgodność z zasadami* możesz wybrać kafelek **Urządzenia bez zasad zgodności**, aby wyświetlić informacje o urządzeniach, które nie mają przypisanych zasad zgodności:

![Wyświetlanie urządzeń bez żadnych zasad zgodności](./media/compliance-policy-monitor/devices-without-policies.png)

Po wybraniu kafelka zostaną wyświetlone wszystkie urządzenia bez zasad zgodności. Ponadto opcja pokazuje użytkownika urządzenia, stan wdrożenia zasad oraz model urządzenia.

#### <a name="what-you-need-to-know"></a>Co musisz wiedzieć

- W przypadku ustawienia zabezpieczeń **Oznaczaj urządzenia bez przypisanych zasad zgodności jako** należy zidentyfikować urządzenia bez zasad zgodności. Następnie możesz im przypisać co najmniej jedne zasady zgodności.

  Ustawienie zabezpieczeń można skonfigurować w portalu usługi Intune. Przejdź do pozycji **Urządzenia** > **Zasady zgodności** > **Ustawienia zasad zgodności**. Następnie ustaw opcję **Oznaczaj urządzenia bez przypisanych zasad zgodności jako** na wartość **Zgodne** lub **Niezgodne**.

  Dowiedz się więcej o tym [ulepszeniu zabezpieczeń w usłudze Intune](https://blogs.technet.microsoft.com/intunesupport/2018/02/09/updated-upcoming-security-enhancements-in-the-intune-service/).

- Użytkownicy z przypisanymi zasadami zgodności dowolnego typu nie są wyświetlani w raporcie, niezależnie od platformy urządzeń. Jeśli na przykład przypiszesz zasady zgodności systemu Windows do użytkownika z systemem Android, urządzenie nie zostanie ujęte w raporcie. Jednak usługa Intune uzna urządzenie z systemem Android za niezgodne. Aby uniknąć problemów, firma Microsoft zaleca utworzenie zasad dla każdej platformy urządzeń i wdrożenie ich do wszystkich użytkowników.

### <a name="per-policy-device-compliance"></a>Zgodność urządzeń wg zasady

Raport **Zgodność z zasadami** przedstawia zasady oraz liczbę urządzeń zgodnych i niezgodnych.

![Wyświetlanie listy zasad oraz liczby urządzeń zgodnych i niezgodnych z tymi zasadami](./media/compliance-policy-monitor/idc-8.png)

### <a name="setting-compliance"></a>Zgodność ustawienia

Wykres **Zgodność ustawień** przedstawia wszystkie ustawienia zasad zgodności urządzeń ze wszystkich zasad zgodności, platformy, dla których zastosowano ustawienia zasad, a także liczbę niezgodnych urządzeń.

![Wyświetlanie listy wszystkich urządzeń w różnych zasadach](./media/compliance-policy-monitor/idc-10.png)

## <a name="view-compliance-reports"></a>Wyświetlanie raportów zgodności

Oprócz używania wykresów w obszarze *Stan zgodności* możesz przejść do pozycji **Raporty** > **Zgodność urządzenia**.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz pozycję **Urządzenia** > **Monitoruj**, a następnie poniżej pozycji **Zgodność** wybierz raport, który chcesz wyświetlić. Niektóre z dostępnych raportów zgodności są następujace:

   - Zgodność urządzeń
   - Niezgodne urządzenia
   - Urządzenia bez zasad zgodności
   - Zgodność ustawienia
   - Zgodność z zasadami
   - Raport dotyczący zaświadczania o kondycji systemu Windows
   - Stan agenta zagrożeń

Aby uzyskać więcej informacji o raportach, zobacz [Raporty usługi Intune](../fundamentals/reports.md)

## <a name="view-status-of-device-policies"></a>Wyświetlanie stanu zasad dotyczących urządzenia

Różne stany zasad można sprawdzać według platformy. Na przykład masz zasady zgodności systemu macOS. Chcesz wyświetlić urządzenia, na które wpływają te zasady, i dowiedzieć się, czy występują konflikty lub błędy.

Ta funkcja jest uwzględniana w obszarze raportowania stanu urządzenia:

1. Wybierz pozycję **Urządzenia** > **Zasady zgodności** > **Zasady**. Zostanie wyświetlona lista zasad, w tym platforma, informacja o przypisaniu zasad i dalsze szczegóły.
2. Wybierz zasadę > **Omówienie**. W tym widoku przypisanie zasad uwzględnia następujące stany:

    - **Powodzenie**: zasady zostały zastosowane.
    - **Błąd**: nie można zastosować zasad. Ten komunikat jest przeważnie wyświetlany z kodem błędu stanowiącym link do wyjaśnienia.
    - **Konflikt**: na tym samym urządzeniu zostały zastosowane dwa ustawienia, a usługa Intune nie może rozwiązać konfliktu. Administrator powinien zapoznać się z tą sytuacją.
    - **Oczekujące**: urządzenie nie zostało jeszcze zaewidencjonowane w usłudze Intune w celu odebrania zasad.
    - **Nie dotyczy**: urządzenie nie może odebrać zasad. Na przykład zasady aktualizują ustawienie specyficzne dla systemu iOS 11.1, ale urządzenie używa systemu iOS 10.

3. Aby wyświetlić szczegóły urządzeń używających danych zasad, wybierz jeden z stanów. Na przykład wybierz pozycję **Powodzenie**. W następnym oknie jest wyświetlana lista szczegółów określonego urządzenia, w tym nazwa i stan jego wdrażania.

## <a name="how-intune-resolves-policy-conflicts"></a>Jak są rozwiązywane konflikty zasad usługi Intune

Konflikty zasad mogą wystąpić, gdy na urządzeniu stosuje się wiele zasad usługi Intune. Jeśli ustawienia zasad nakładają się na siebie, usługa Intune rozwiązuje konflikty, używając następujących reguł:

- Jeżeli sprzeczne ustawienia pochodzą z zasad konfiguracji usługi Intune i zasad zgodności, ustawienia w zasadach zgodności mają pierwszeństwo względem ustawień w zasadach konfiguracji. Dzieje się tak nawet wtedy, gdy ustawienia w zasadach konfiguracji są bardziej bezpieczne.

- Jeśli wdrożono wiele zasad zgodności, usługa Intune używa najbezpieczniejszych z nich.

## <a name="next-steps"></a>Następne kroki

[Omówienie zasad zgodności](device-compliance-get-started.md)
