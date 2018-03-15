---
title: "Monitorowanie zasad zgodności urządzeń Intune"
titlesuffix: Azure portal
description: "Informacje na temat monitorowania zasad zgodności urządzeń"
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 2/27/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2f80d46e3e7c25c2b2e7a7c1af9604de1257a21e
ms.sourcegitcommit: a55c009a2ab223f79dc7439539937b284aee0626
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2018
---
# <a name="monitor-intune-device-compliance-policies"></a>Monitorowanie zasad zgodności urządzeń Intune

Raporty zgodności umożliwiają administratorom analizowanie stanu zgodności urządzeń w organizacji i szybkie rozwiązywanie problemów ze zgodnością napotykanych przez użytkowników w organizacji. Można wyświetlić informacje o ogólnym stanie zgodności urządzeń, stanie zgodności poszczególnych ustawień, stanie zgodności dla poszczególnych zasad, a także przejść do poszczególnych urządzeń, aby wyświetlić konkretne ustawienia i zasady, które wpływają na urządzenie.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Wykonaj następujące kroki, aby znaleźć **pulpit nawigacyjny zgodności urządzeń Intune** w witrynie Azure Portal:

1.  Przejdź do witryny [Azure Portal](https://portal.azure.com) i zaloguj się przy użyciu swoich poświadczeń usługi Intune.

2.  W menu po lewej stronie wybierz pozycję **Więcej usług**, a następnie w filtrze pola tekstowego wpisz **Intune**.

3.  Wybierz kolejno opcje **Intune** &gt; **Zgodność urządzenia** &gt; **Przegląd**. Zostanie otwarty **pulpit nawigacyjny zgodności urządzeń**.

> [!IMPORTANT] 
> Aby otrzymać zasady zgodności urządzeń, urządzenia muszą być zarejestrowane w usłudze Intune.

## <a name="device-compliance-dashboard"></a>Pulpit nawigacyjny zgodności urządzeń

Na **pulpicie nawigacyjnym zgodności urządzeń** można monitorować stany zasad zgodności urządzeń i otrzymywać różne raporty dla poszczególnych kafelków, co pozwala na ocenę stanu zgodności urządzeń w Twojej organizacji. Istnieje możliwość wyświetlenia następujących raportów:

-   Ogólna zagregowana zgodność urządzeń

-   Zgodność urządzeń wg zasady

-   Zgodność urządzeń wg ustawienia

![Pulpit nawigacyjny zgodności urządzeń](./media/idc-1.png)

Można także wyświetlić określone zasady i ustawienia zgodności, które mają zastosowanie do poszczególnych urządzeń, oraz końcowy stan zgodności dla każdego z tych ustawień na urządzeniu.

### <a name="overall-device-compliance-aggregate-report"></a>Raport ogólnej zagregowanej zgodności urządzeń

Jest to wykres pierścieniowy przedstawiający zagregowany stan zgodności dla wszystkich urządzeń zarejestrowanych w usłudze Intune. Stany zgodności urządzeń są przechowywane w dwóch różnych bazach danych, Intune i Azure Active Directory. Poniżej przedstawiono szczegółowe informacje o stanach zasad zgodności urządzeń:

-   **Zgodne**: urządzenie pomyślnie zastosowało co najmniej jedno ustawienie zasady zgodności urządzenia przepisane przez administratora.

-   **Niezgodne**: nie udało się zastosować co najmniej jednego ustawienia zasady zgodności urządzenia przepisanego przez administratora lub też użytkownik nie spełnił zasad zgodności przepisanych przez administratora.

-   **Okres prolongaty**: administrator przepisał do urządzenia co najmniej jedno ustawienie zasady zgodności, ale użytkownik nie zastosował tych zasad, co oznacza, że urządzenie nie jest zgodne ze specyfikacją, ale trwa okres prolongaty zdefiniowany przez administratora.

    -   Dowiedz się więcej o akcjach dla niezgodnych urządzeń.

-   **Urządzenie nie jest zsynchronizowane**: urządzenie nie zgłosiło stanu zasady zgodności urządzenia z jednej z przyczyn:

    -   **Nieznany**: urządzenie jest w trybie offline lub nie nawiązało łączności z usługą Intune lub Azure AD z innych przyczyn.

    -   **Błąd**: urządzenie nie skomunikowało się z usługą Intune i Azure AD i otrzymało komunikat o błędzie z podanym powodem.

> [!IMPORTANT] 
> Urządzenia, które są zarejestrowane w usłudze Intune, ale nie są objęte żadnymi zasadami zgodności urządzeń, są uwzględnione w raporcie w obszarze **Zgodne**.

#### <a name="drill-down-option"></a>Opcja przechodzenia do informacji szczegółowych

Jeśli na **pulpicie nawigacyjnym zgodności urządzeń** klikniesz kafelek zgodności urządzenia, możesz przejść do określonego **stanu zgodności**, **aliasu adresu e-mail użytkownika**, **modelu urządzenia** i **lokalizacji** dla każdego urządzenia, które było objęte zasadami zgodności urządzeń.

![Przechodzenie do informacji szczegółowych na pulpicie nawigacyjnym zgodności urządzeń](./media/idc-2.png)

Aby uzyskać więcej szczegółów na temat określonego użytkownika, można filtrować raport wykresu zgodności urządzeń, wpisując alias adresu e-mail użytkownika.

![Konkretny użytkownik pulpitu nawigacyjnego zgodności urządzeń](./media/idc-3.png)

Możesz również kliknąć inny stan zgodności na wykresie zgodności urządzeń, aby zobaczyć bardziej szczegółowe informacje o stanach zasady zgodności urządzeń użytkownika.

![Różne stany pulpitu nawigacyjnego zgodności urządzeń](./media/idc-4.png)

#### <a name="filter"></a>Filtr

Po kliknięciu przycisku **Filtr** staną się dostępne następujące opcje:

-   Model

    -   Pole tekstowe, w którym można wpisać dowolny wyszukiwany ciąg
<br></br>
-   Platforma

    -   Android

    -   iOS

    -   Mac OS

    -   Windows

    -   Windows Phone

-   Stan

    -   Zgodny

    -   Niezgodny

    -   Okres prolongaty

    -   Nieznane

    -   Error

Po kliknięciu przycisku **Aktualizuj** powinny zostać zamknięte wyświetlane elementy, zaś wyniki powinny zostać zaktualizowane zgodnie z wybranymi kryteriami filtrowania.

##### <a name="device-details"></a>Szczegóły urządzenia

Kliknięcie urządzenie powoduje otwarcie **bloku Urządzenia** z zaznaczonym urządzeniem. Dzięki temu jest dostępnych więcej szczegółów dotyczących ustawienia zasad zgodności urządzenia zastosowanego do danego urządzenia.

![Pulpit nawigacyjny zgodności urządzeń](./media/idc-6.png)

Po kliknięciu samego ustawienia zasad urządzenia zostanie wyświetlona nazwa zasady zgodności urządzenia wskazująca, że ustawienie zgodności urządzenia zostało zalecone przez administratora.

![Nazwa ustawienia zgodności urządzenia](./media/idc-7.png)

## <a name="policy-compliance-report"></a>Raport o zgodności z zasadami

Ten raport zawiera widok wg zasady zgodności oraz łączną liczbę urządzeń znajdujących się w poszczególnych stanach zgodności. Kafelek **Zgodność z zasadami** jest dostępny na **pulpicie nawigacyjnym zgodności urządzenia** i zawiera wszystkie zasady wcześniej utworzone przez administratora, platformy, na których zasady są stosowane, liczbę zgodnych urządzeń oraz liczbę urządzeń niezgodnych.

![Raport zgodności urządzeń wg zasady](./media/idc-8.png)

Kliknięcie na pulpicie nawigacyjnym zgodności urządzeń kafelka Zgodność z zasadami umożliwia przejście do określonego **stanu zgodności**, **aliasu adresu e-mail użytkownika**, **modelu urządzenia** i **lokalizacji** dla każdego urządzenia, które było objęte daną zasadą zgodności urządzeń.

![Kafelek Zgodność z zasadami](./media/idc-9.png)

## <a name="setting-compliance-report"></a>Raport o zgodności ustawień

Ten raport umożliwia zapoznanie się z łączną liczbą urządzeń znajdujących się w poszczególnych stanach zgodności dla każdego ustawienia zgodności. Kafelek **Zgodność ustawień** jest dostępny na **pulpicie nawigacyjnym zgodności urządzenia** i pokazuje wszystkie ustawienia zasad zgodności urządzeń dla wszystkich zasad zgodności urządzeń utworzonych przez administratora, platformy, na których zastosowano ustawienia zasad, oraz liczbę niezgodnych urządzeń.

![Raport zgodności urządzeń wg ustawienia](./media/idc-10.png)

Kliknięcie na pulpicie nawigacyjnym zgodności urządzeń kafelka Zgodność ustawień umożliwia przejście do określonego **stanu zgodności**, **aliasu adresu e-mail użytkownika**, **modelu urządzenia** i **lokalizacji** dla każdego urządzenia, które było objęte daną zasadą zgodności urządzeń.

![Kafelek Zgodność ustawień](./media/idc-11.png)

## <a name="threat-agent-status-report"></a>Raport o stanie agenta zagrożeń

Ten raport umożliwia wyświetlenie stanu i kondycji agenta programu Windows Defender. Za pomocą zbiorczego raportu stanu w obszarze **Zgodność urządzenia** można wyświetlić urządzenia, dla których trzeba wykonać jedną z następujących czynności:
- Aktualizacja sygnatur
- Uruchom ponownie
- Ręczna interwencja
- Pełne skanowanie
- Inne stany agentów, które wymagają interwencji

Raport szczegółowy dla każdej kategorii stanu zawiera listę poszczególnych komputerów osobistych, które wymagają uwagi, lub komputerów osobistych, których stan jest zgłaszany jako **Czysty**.
