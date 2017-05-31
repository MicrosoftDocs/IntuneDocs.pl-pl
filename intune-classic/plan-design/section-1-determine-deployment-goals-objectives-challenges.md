---
title: "Określanie celów, zamierzeń i wyzwań związanych z wdrożeniem usługi Intune | Microsoft Docs"
description: "Ten artykuł jest pomocny w przypadku identyfikowania celów, zamierzeń i wyzwań związanych z implementacją usługi Microsoft Intune tylko w chmurze."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 24cf9d97-db39-4b95-a664-4aa2e33edb87
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 6014527422ea3dae4d1333965ccd9e48e8216afb
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="determine-intune-deployment-goals-objectives-and-challenges"></a>Określanie celów, zamierzeń i wyzwań związanych z wdrożeniem usługi Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Tworzenie dobrego planu wdrożenia rozpoczyna się od zidentyfikowania celów i zamierzeń wdrożenia oraz potencjalnych wyzwań. Każda organizacja jest unikatowa i będzie mieć własne cele, zamierzenia i wyzwania związane z wdrożeniem. Omówmy dokładniej każdy z tych obszarów.

## <a name="deployment-goals"></a>Cele wdrożenia

Cele wdrażania to długoterminowe osiągnięcia, które organizacja chce realizować przez zaimplementowanie usługi Microsoft Intune. Poniżej przedstawiono przykłady celów wdrożenia usługi Intune w organizacji oraz podano opis i wartość biznesową każdego z nich.

-   **Integracja z usługą Office 365 i obsługa korzystania z aplikacji mobilnych pakietu Office**

    -   **Opis:** zapewnia ścisłą integrację z usługą Office 365 i umożliwia korzystanie z aplikacji mobilnych pakietu Office objętych ochroną aplikacji.

    -   **Wartość biznesowa:** bezpieczne i ulepszone środowisko pracy, w którym użytkownicy mogą korzystać ze znanych i preferowanych aplikacji.

-   **Zapewnianie dostępu do wewnętrznych usług firmy na urządzeniach przenośnych**

    -   **Opis:** jest to strategiczny kierunek rozwoju organizacji umożliwiający pracownikom produktywne działanie z każdego miejsca, z którego muszą wykonywać pracę, przy użyciu najodpowiedniejszego dla nich urządzenia. W ramach tego projektu wskazane jest umożliwienie produktywnej pracy na urządzeniach przenośnych i dostępu do danych firmowych w bezpieczny sposób.

    -   **Wartość biznesowa:** dzięki zapewnieniu pracownikom elastyczności i możliwości pracy z dowolnego miejsca firma jest bardziej konkurencyjna i oferuje atrakcyjniejsze środowisko pracy.

-   **Zapewnianie ochrony danych na urządzeniach przenośnych**

    -   **Opis:** w przypadku, gdy dane są przechowywane na urządzeniu przenośnym, powinny być chronione przed złośliwą lub przypadkową utratą bądź udostępnieniem.

    -   **Wartość biznesowa:** ochrona danych jest niezbędna do zapewnienia stałej konkurencyjności firmy. Sprawia również, że klienci i ich dane są traktowane z najwyższą starannością.

-   **Obniżenie kosztów**

    -   **Opis:** jeśli to możliwe, projekt zmniejsza koszty wdrożenia i operacyjne.

    -    **Wartość biznesowa:** dzięki efektywnemu użyciu zasobów firma może inwestować w innych obszarach, konkurować skuteczniej i oferować klientom lepszą obsługę.

## <a name="deployment-objectives"></a>Zamierzenia wdrożenia

Zamierzenia wdrożenia to akcje, które organizacja może podjąć w celu osiągnięcia celów wdrożenia usługi Microsoft Intune. Poniżej przedstawiono kilka przykładów zamierzeń wdrożenia w organizacji oraz sposoby ich realizacji.

-   **Zmniejszenie liczby rozwiązań do zarządzania urządzeniami**
<br>
    -   **Wykonanie:** konsolidacja do pojedynczego rozwiązania do zarządzania urządzeniami przenośnymi, usługi Microsoft Intune, w celu objęcia ochroną danych firmowych aplikacji i urządzeń.
<br></br>
-   **Zapewnianie bezpiecznego dostępu do programu Exchange i usługi SharePoint Online**
<br>
    -   **Wykonanie:** zaimplementowanie dostępu warunkowego usługi Microsoft Intune dla programu Exchange i usługi SharePoint Online.
<br></br>
-   **Zapobieganie przechowywaniu danych firmowych w usługach innych niż firmowe na urządzeniu przenośnym oraz przekazywaniu danych do tych usług**
<br>
    -   **Wykonanie:** zaimplementowanie zasad ochrony usługi Microsoft Intune dla aplikacji pakietu Microsoft Office i biznesowych.
<br></br>
-   **Oferowanie możliwości czyszczenia danych firmowych z urządzenia**
<br>
    -   **Wykonanie:** zarejestrowanie urządzeń oraz zarządzanie nimi w usłudze Microsoft Intune, co zapewnia możliwość zdalnego czyszczenia firmowych danych i zasobów w odpowiednim momencie.

## <a name="deployment-challenges"></a>Wyzwania związane z wdrożeniem

Wyzwania związane z wdrożeniem to najważniejsze dla organizacji problemy, które mogą mieć negatywny wpływ na to wdrożenie. Czasami wyzwania mogą dotyczyć problemów, które wystąpiły w przeszłych projektach i których organizacja chce uniknąć, lub nowych problemów powstających podczas pracy nad bieżącym wdrożeniem. Poniżej przedstawiono kilka przykładów wyzwań związanych z wdrożeniem usługi Microsoft Intune w firmie oraz potencjalne środki zaradcze.

-   Przygotowanie do udzielania pomocy technicznej oraz środowisko pracy użytkownika końcowego nie są uwzględnione w początkowym zakresie projektu.  W rezultacie wdrażanie użytkownika końcowego jest nieskuteczne oraz występują wyzwania związane z udzielaniem pomocy technicznej dotyczącej rozwiązania.
<br>
    -   **Środki zaradcze:** zorganizowanie szkoleń z zakresu pomocy technicznej oraz zweryfikowanie środowiska użytkownika końcowego z użyciem metryk sukcesu w planie wdrożenia.
<br></br>
-   Brak jasno określonych celów i metryk sukcesu ma niemierzalne wyniki oraz powoduje reagowanie po wystąpieniu problemów.
<br>
    -   **Środki zaradcze:** zdefiniuj cele i metryki sukcesu na wczesnym etapie określania zakresu projektu i skorzystaj z tych danych podczas opracowywania pozostałych faz wdrażania. Upewnij się, że cele są zgodne ze strategią SMART (określone, wymierne, możliwe do osiągnięcia, realistyczne i terminowe), zaplanuj pomiar względem celów w poszczególnych fazach i upewnij się, że projekt wdrożenia jest realizowany zgodnie z planem.
<br></br>
-   Pominięcie tworzenia, weryfikacji i agresywnego przekazywania zrozumiałych informacji o korzyściach odpowiadających potrzebom organizacji często skutkuje ograniczonym przyjęciem i brakiem zwrotu z inwestycji (ROI, return on investment).
<br>
    -   **Środki zaradcze:** choć możesz chcieć od razu rozpocząć realizowanie projektu, upewnij się, że masz jasno zdefiniowane cele i zamierzenia. Uwzględnij te informacje we wszystkich działaniach związanych ze zwiększaniem świadomości i szkoleniach, aby ułatwić użytkownikom zrozumienie, dlaczego organizacja wybrała usługę Intune.

## <a name="next-steps"></a>Następne kroki

Teraz, gdy zidentyfikowano cele, zamierzenia i potencjalne wyzwania związane z wdrożeniem, przejdźmy do kolejnej sekcji: [Identyfikowanie scenariuszy przypadków użycia](section-2-identify-use-case-scenarios.md).

