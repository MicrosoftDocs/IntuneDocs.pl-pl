---
title: "Określanie celów, zamierzeń i wyzwań związanych z wdrożeniem"
description: "Ten artykuł jest pomocny w przypadku identyfikowania celów, zamierzeń i wyzwań związanych z implementacją usługi Microsoft Intune tylko w chmurze."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 24cf9d97-db39-4b95-a664-4aa2e33edb87
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6c81ba2f40500ff58fb1e828cf629b4dcc8ac9d1
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2017
---
# <a name="determine-deployment-goals-objectives-and-challenges"></a>Określanie celów, zamierzeń i wyzwań związanych z wdrożeniem

Tworzenie dobrego planu wdrożenia rozpoczyna się od zidentyfikowania celów i zamierzeń wdrożenia oraz potencjalnych wyzwań. Omówmy dokładniej każdy z tych obszarów.

## <a name="deployment-goals"></a>Cele wdrożenia

Cele wdrożenia to długoterminowe osiągnięcia, jakie mają być uzyskane poprzez wdrożenie usługi Intune w organizacji. Poniżej przedstawiono przykłady takich celów oraz podano opis i wartość biznesową każdego z nich.

-   **Integracja z usługą Office 365 i obsługa korzystania z aplikacji mobilnych pakietu Office**

    -   **Opis:** zapewnia ścisłą integrację z usługą Office 365 i umożliwia korzystanie z aplikacji mobilnych pakietu Office objętych ochroną aplikacji.

    -   **Wartość biznesowa:** bezpieczne i ulepszone środowisko pracy, w którym użytkownicy mogą korzystać ze znanych i preferowanych aplikacji.

-   **Zapewnianie dostępu do wewnętrznych usług firmy na urządzeniach przenośnych**

    -   **Opis:** umożliwienie pracownikom produktywnego działania z każdego miejsca, z którego muszą wykonywać pracę, przy użyciu najodpowiedniejszego dla nich urządzenia. W ramach tego projektu wskazane jest umożliwienie produktywnej pracy na urządzeniach przenośnych i dostępu do danych firmowych w bezpieczny sposób.

    -   **Wartość biznesowa:** dzięki zapewnieniu pracownikom elastyczności i możliwości pracy z dowolnego miejsca firma jest bardziej konkurencyjna i oferuje atrakcyjniejsze środowisko pracy.

-   **Zapewnianie ochrony danych na urządzeniach przenośnych**

    -   **Opis:** w przypadku, gdy dane są przechowywane na urządzeniu mobilnym, powinny być chronione przed złośliwą lub przypadkową utratą bądź udostępnieniem.

    -   **Wartość biznesowa:** ochrona danych jest niezbędna do zapewnienia stałej konkurencyjności firmy. Sprawia również, że klienci i ich dane są traktowane z najwyższą starannością.

-   **Obniżenie kosztów**

    -   **Opis:** jeśli to możliwe, projekt zmniejsza koszty wdrożenia i operacyjne.

    -    **Wartość biznesowa:** dzięki efektywnemu użyciu zasobów firma może inwestować w innych obszarach, konkurować skuteczniej i oferować klientom lepszą obsługę.

## <a name="deployment-objectives"></a>Zamierzenia wdrożenia

Zamierzenia wdrożenia to akcje, które organizacja może podjąć w celu osiągnięcia celów wdrożenia usługi Intune. Poniżej przedstawiono kilka przykładów zamierzeń wdrożenia oraz sposoby ich realizacji.

-   **Zmniejszenie liczby rozwiązań do zarządzania urządzeniami**

    -   **Implementacja:** konsolidacja do pojedynczego rozwiązania do zarządzania urządzeniami mobilnymi, usługi Microsoft Intune, w celu objęcia ochroną danych firmowych aplikacji i urządzeń.

-   **Zapewnianie bezpiecznego dostępu do programu Exchange i usługi SharePoint Online**

    -   **Implementacja:** zastosowanie dostępu warunkowego dla programu Exchange i usługi SharePoint Online.

-   **Zapobieganie przechowywaniu danych firmowych w usługach innych niż firmowe na urządzeniu mobilnym oraz przekazywaniu danych do tych usług**

    -   **Implementacja:** zastosowanie zasad ochrony aplikacji w usłudze Intune dla aplikacji pakietu Microsoft Office i biznesowych.

-   **Oferowanie możliwości czyszczenia danych firmowych z urządzenia**

    -   **Implementacja:** rejestrowanie urządzeń w usłudze Intune. Daje to możliwość wykonywania zdalnego czyszczenia danych firmowych i zasobów, gdy jest to konieczne.

## <a name="deployment-challenges"></a>Wyzwania związane z wdrożeniem

Wyzwania związane z wdrożeniem to najważniejsze dla organizacji problemy, które mogą mieć negatywny wpływ na to wdrożenie. Czasami wyzwania mogą dotyczyć problemów, które wystąpiły w przeszłych projektach i których organizacja chce uniknąć, lub nowych problemów powstających podczas pracy nad bieżącym wdrożeniem. Poniżej przedstawiono kilka przykładów wyzwań związanych z wdrożeniem usługi Intune oraz potencjalne środki zaradcze.

-   Przygotowanie do udzielania pomocy technicznej oraz środowisko użytkownika końcowego nie są uwzględnione w początkowym zakresie projektu. Prowadzi to do niechętnego przyjęcia rozwiązania przez użytkowników końcowych i stwarza wyzwania dla organizacji udzielającej pomocy technicznej.

    -   **Środki zaradcze:** Wprowadzenie szkolenia w zakresie pomocy technicznej. Sprawdzenie środowiska użytkownika końcowego z użyciem metryk sukcesu określonych w planie wdrożenia.

-   Brak jasno określonych celów i metryk sukcesu skutkuje brakiem konkretnych wyników. Może także spowodować działanie organizacji w trybie reaktywnym w momencie wystąpienia problemów.

    -   **Środki zaradcze:** zdefiniuj cele i metryki sukcesu na wczesnym etapie określania zakresu projektu i skorzystaj z tych danych podczas opracowywania pozostałych faz wdrażania. Upewnij się, że cele są zgodne z zasadą SMART (są skonkretyzowane, mierzalne, osiągalne, realne i określone w czasie). Zaplanuj pomiar wyników względem celów w każdej fazie i upewnij się, że projekt wdrożenia jest realizowany zgodnie z planem.

-   Pominięcie tworzenia, weryfikacji i intensywnego przekazywania zrozumiałych informacji o korzyściach odpowiadających potrzebom organizacji. Często skutkuje to ograniczonym przyjęciem rozwiązania i brakiem zwrotu z inwestycji.

    -   **Środki zaradcze:** Choć możesz chcieć od razu rozpocząć realizowanie projektu, upewnij się, że masz jasno zdefiniowane cele i zamierzenia. Uwzględnij te informacje we wszystkich działaniach związanych ze zwiększaniem świadomości i szkoleniach, aby ułatwić użytkownikom zrozumienie, dlaczego organizacja wybrała usługę Intune.

## <a name="next-steps"></a>Następne kroki

Teraz, gdy zidentyfikowano cele, zamierzenia i potencjalne wyzwania związane z wdrożeniem, przejdźmy do kolejnej sekcji: [Identyfikowanie scenariuszy przypadków użycia](planning-guide-scenarios.md).
