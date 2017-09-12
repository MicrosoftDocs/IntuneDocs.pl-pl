---
title: "Monitorowanie zgodności z dostępem warunkowym dla lokalnego programu Exchange i usługi Exchange Online"
titlesuffix: Azure portal
description: "Monitorowanie zgodności z dostępem warunkowym dla lokalnego programu Exchange i usługi Exchange Online za pośrednictwem portalu Intune Azure"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5712682d-285b-43fd-9978-3dcfd95ec5f9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: be0c1cef0dd6562feb54724edbf8ae22072e3d95
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2017
---
# <a name="monitor-conditional-access-compliance-for-on-premises-exchange-and-exchange-online-in-intune"></a>Monitorowanie zgodności z dostępem warunkowym dla lokalnego programu Exchange i usługi Exchange Online w usłudze Intune

Począwszy od usługi Intune w wersji 1704 administratorzy mogą zobaczyć informacje dotyczące raportowania powiązane z rekordami urządzeń w programie Exchange ActiveSync, które są synchronizowane z usługą Intune za pośrednictwem lokalnego programu Exchange Connector lub łącznika Service To Service Connector usługi Intune (łącznika usługi Exchange Online). Raportowanie zgodności z dostępem warunkowym zawiera podsumowanie informacji o urządzeniach o różnych stanach synchronizacji:

-   **Zezwalaj**

-   **Zablokuj**

-   **Kwarantanna**

## <a name="to-monitor-conditional-access-compliance"></a>Aby monitorować zgodność z dostępem warunkowym

1.  Przejdź do witryny [Azure Portal](https://portal.azure.com/) i zaloguj się przy użyciu swoich poświadczeń usługi Intune.

2.  Po pomyślnym zalogowaniu zostanie wyświetlona strona **Pulpit nawigacyjny Azure**.

3.  W menu po lewej stronie wybierz pozycję **Więcej usług**, a następnie w filtrze pola tekstowego wpisz **Intune**.

4.  Wybierz pozycję **Intune**, aby wyświetlić **Pulpit nawigacyjny Intune**.

5.  Wybierz pozycję **Dostęp warunkowy**, a następnie wybierz pozycję **Przegląd**.

6.  Na wykresie wybierz jeden z trzech obszarów (**Zablokowane**, **Kwarantanna** lub **Dozwolone**), aby wyświetlić raport dotyczący zgodności z dostępem warunkowym.

    ![Pulpit nawigacyjny dostępu warunkowego](./media/CA-reporting-intune-1.png)

Po wybraniu jednego z trzech obszarów można zobaczyć bardziej szczegółowe informacje o urządzeniach dozwolonych, zablokowanych lub poddanych kwarantannie.

Można również przejść do informacji o określonych urządzeniach i wyświetlić więcej szczegółów. Na przykład urządzenie wybrane na ilustracji poniżej jest zablokowane. Usługa Intune zapewnia możliwość usunięcia danych firmowych z poziomu bloku raportu dotyczącego zgodności z dostępem warunkowym.

![Raportowanie szczegółów urządzenia z dostępem warunkowym](./media/CA-reporting-intune-3.png)

W bloku szczegółów urządzenia można zobaczyć więcej informacji:

-   **Przegląd:** można wyświetlić właściwości urządzenia, takie jak: wersja systemu operacyjnego, model urządzenia, własność, numer seryjny, producent urządzenia, numer telefonu oraz godzina ostatniego zameldowania.

-   **Właściwości:** można ustawić własność urządzenia (osobista lub firmowa).

-   **Sprzęt:** udostępnia informacje widoczne w obszarze Przegląd, a także szczegóły magazynu (całkowita ilość miejsca i wolne miejsce), załącznik systemowy, szczegóły sieci, usługę sieciową i więcej szczegółów dotyczących blokowania dostępu warunkowego.

-   **Odnalezione aplikacje:** wyświetla wszystkie aplikacje zainstalowane na urządzeniu. Można także eksportować listę zainstalowanych aplikacji do formatu CSV.

-   **Zgodność:** przedstawia wszystkie szczegóły zasad zgodności urządzenia.

-   **Konfiguracja urządzenia:** zawiera wszystkie szczegóły konfiguracji urządzenia.

-   **Dostęp do programu Exchange:** tutaj można dowiedzieć się więcej o stanie urządzenia po zastosowaniu zasad dostępu warunkowego.
