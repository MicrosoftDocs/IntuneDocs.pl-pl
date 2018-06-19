---
title: Monitorowanie dostępu warunkowego programu Exchange w usłudze Microsoft Intune
titlesuffix: ''
description: Monitorowanie zgodności z dostępem warunkowym dla lokalnego programu Exchange i usługi Exchange Online za pośrednictwem witryny Azure Portal usługi Intune.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5712682d-285b-43fd-9978-3dcfd95ec5f9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 932dfe32c6df5741615d9db9f303aaee7785d3a3
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/08/2018
ms.locfileid: "29775362"
---
# <a name="monitor-conditional-access-compliance-for-on-premises-exchange-and-exchange-online-in-intune"></a>Monitorowanie zgodności z dostępem warunkowym dla lokalnego programu Exchange i usługi Exchange Online w usłudze Intune

Począwszy od usługi Intune w wersji 1704 administratorzy mogą zobaczyć informacje dotyczące raportowania powiązane z rekordami urządzeń w programie Exchange ActiveSync, które są synchronizowane z usługą Intune za pośrednictwem lokalnego programu Exchange Connector lub łącznika Service To Service Connector usługi Intune (łącznika usługi Exchange Online). Raportowanie zgodności z dostępem warunkowym zawiera podsumowanie informacji o urządzeniach o różnych stanach synchronizacji:

-   **Zezwalaj**

-   **Zablokuj**

-   **Kwarantanna**

## <a name="to-monitor-conditional-access-compliance"></a>Aby monitorować zgodność z dostępem warunkowym

1.  Przejdź do witryny [Azure Portal](https://portal.azure.com/) i zaloguj się przy użyciu swoich poświadczeń usługi Intune.

2.  Po pomyślnym zalogowaniu zostanie wyświetlona strona **Pulpit nawigacyjny Azure**.

3.  W menu po lewej stronie wybierz pozycję **Wszystkie usługi**, a następnie w filtrze pola tekstowego wpisz **Intune**.

4.  Wybierz pozycję **Intune**, aby wyświetlić **Pulpit nawigacyjny Intune**.

5.  Wybierz pozycję **Dostęp warunkowy**, a następnie wybierz pozycję **Przegląd**.

6.  Na wykresie wybierz jeden z trzech obszarów (**Dozwolone**, **Zablokowane** lub **Kwarantanna**), aby wyświetlić raport dotyczący zgodności z dostępem warunkowym.

    ![Obraz przedstawiający pulpit nawigacyjny dostępu warunkowego](./media/CA-reporting-intune-1.png)

Po wybraniu jednego z trzech obszarów wyświetlane są bardziej szczegółowe informacje o urządzeniach dozwolonych, zablokowanych lub poddanych kwarantannie.

Można również przejść do informacji o określonych urządzeniach i wyświetlić więcej szczegółów. Na przykład urządzenie wybrane na poniższym obrazie jest zablokowane. Usługa Intune zapewnia możliwość usunięcia danych firmowych z poziomu okienka raportu dotyczącego zgodności z dostępem warunkowym.

![Obraz przedstawiający raportowanie szczegółów urządzenia z dostępem warunkowym](./media/CA-reporting-intune-3.png)

W okienku szczegółów urządzenia można wyświetlić więcej informacji:

-   **Przegląd:** można wyświetlić właściwości urządzenia, takie jak wersja systemu operacyjnego, model urządzenia, własność, numer seryjny, producent urządzenia, numer telefonu oraz godzina ostatniego zaewidencjonowania.

-   **Właściwości:** można ustawić własność urządzenia (osobista lub firmowa).

-   **Sprzęt:** udostępnia informacje widoczne w obszarze Przegląd, a także szczegóły magazynu (całkowita ilość miejsca i wolne miejsce), załącznik systemowy, szczegóły sieci, usługę sieciową i więcej szczegółów dotyczących blokowania dostępu warunkowego.

-   **Odnalezione aplikacje:** wyświetla wszystkie aplikacje zainstalowane na urządzeniu. Można także eksportować listę zainstalowanych aplikacji do formatu CSV.

-   **Zgodność:** przedstawia wszystkie szczegóły zasad zgodności urządzenia.

-   **Konfiguracja urządzenia:** zawiera wszystkie szczegóły konfiguracji urządzenia.

-   **Dostęp do programu Exchange:** tutaj można dowiedzieć się więcej o stanie urządzenia po zastosowaniu zasad dostępu warunkowego.
