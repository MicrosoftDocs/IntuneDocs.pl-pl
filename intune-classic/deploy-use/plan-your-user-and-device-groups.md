---
title: "Planowanie grup użytkowników i urządzeń | Microsoft Docs"
description: Planowanie grup na potrzeby organizacji.
keywords: 
author: sanchusa
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f11bb256-1094-4f7e-b826-1314c57f3356
ms.reviewer: lpatha
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 1e6727f633d2f74e1f1b018fad5f6765dfa4936b
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="plan-your-user-and-device-groups"></a>Planowanie grup użytkowników i urządzeń

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Grupy w usłudze Intune zapewniają dużą elastyczność zarządzania urządzeniami i użytkownikami. Grupy można skonfigurować zgodnie z potrzebami organizacji na podstawie:

- położenia geograficznego,
- działu,
- właściwości sprzętu,
- systemu operacyjnego,
- przynależności urządzeń do użytkowników lub firmy.


## <a name="how-intune-groups-work"></a>Jak działają grupy usługi Intune


To jest domyślny widok węzła **Grupy** w konsoli administracyjnej usługi Intune:

![Zrzut ekranu przedstawiający widok domyślny węzła Grupy w konsoli usługi Intune](../media/Intune_Planning_Groups_Default_small.png)

Zasady są wdrażane w grupach, dlatego hierarchia grup jest jednym z najważniejszych zagadnień projektowych. Należy zwrócić uwagę na to, że nie można zmienić grupy nadrzędnej danej grupy po jej utworzeniu. Projektowanie grup ma zasadnicze znaczenie od momentu rozpoczęcia korzystania z usługi Intune. Niektóre zalecane praktyki projektowania hierarchii grup odpowiednio do potrzeb organizacji są opisane poniżej.

## <a name="group-membership-rules"></a>Reguły członkostwa w grupach

- Grupa może zawierać użytkowników lub urządzenia, ale nie oba te elementy jednocześnie.

    * **Grupy urządzeń**. Dotyczy zarówno komputerów, jak i urządzeń przenośnych. Aby można było dodać komputer do grupy, musi być on zarejestrowany. Aby można było dodać urządzenie przenośne do grupy, środowisko musi być skonfigurowane do obsługi urządzeń przenośnych i urządzenie musi być zarejestrowane lub odnalezione za pomocą programu Exchange ActiveSync.

    * **Grupy użytkowników**. Grupa może zawierać użytkowników z grup zabezpieczeń. Grupy zabezpieczeń są synchronizowane z wystąpieniem usługi Active Directory. Jeśli nie używasz do synchronizacji usługi Active Directory, możesz utworzyć te grupy ręcznie.

- Urządzenie lub użytkownik może należeć do więcej niż jednej grupy.

- Elementy członkowskie mogą być dołączane do grupy lub wykluczane z niej na podstawie następujących reguł członkostwa:

    * **Kryteria członkostwa**. Są to dynamiczne reguły, których usługa Intune używa do dołączania lub wykluczania elementów członkowskich. W tych kryteriach są używane grupy zabezpieczeń i inne informacje synchronizowane z lokalnym wystąpieniem usługi Active Directory. Jeśli grupa zabezpieczeń lub dane zostaną zmienione, członkostwo w grupie ulega zmianie po synchronizacji z usługą Active Directory.

    * **Członkostwo bezpośrednie**. Są to statyczne reguły, które jawnie dodają lub wykluczają elementy członkowskie. Lista członkostwa jest statyczna.

-   Podczas tworzenia grup użytkowników lub grup urządzeń, które zawierają użytkowników lub komputery, nie są wymagane usługi domenowe Active Directory (AD DS). Jednak aby umożliwić dołączenie do grup urządzeń przenośnych, środowisko musi być skonfigurowane pod kątem obsługi urządzeń przenośnych.

    Ponadto urządzenia muszą zostać wykryte i dodane do usługi Intune.

## <a name="group-relationship-rules"></a>Reguły relacji grup

- Każda utworzona grupa musi mieć grupę nadrzędną. Nie można zmienić grupy nadrzędnej danej grupy po jej utworzeniu.

- W przypadku dodawania użytkowników lub urządzeń do grupy podrzędnej:

    * Grupa podrzędna jest zawsze podzbiorem grupy nadrzędnej.

    * Nowe elementy członkowskie dodane do grupy podrzędnej są automatycznie dodawane do jej grupy nadrzędnej.

    * Nie można dodać elementu członkowskiego do grupy podrzędnej, jeśli jest on wykluczony z grupy nadrzędnej.

- Członkostwo grupy nadrzędnej definiuje dostępne członkostwa dla grupy podrzędnej.

- Usunięcie grupy nadrzędnej spowoduje usunięcie wszystkich grup podrzędnych.

- Zawartość i zasady możesz wdrożyć w grupie nadrzędnej bez jednoczesnego wdrażania ich w grupach podrzędnych.

- Określonego użytkownika lub urządzenie możesz dodać do grupy podrzędnej, jeśli dodawany element nie jest już elementem członkowskim grupy nadrzędnej. W takim przypadku nowy element członkowski grupy podrzędnej zostanie dodany do grupy nadrzędnej.

    Jednak nie można dodać do grupy podrzędnej takiego elementu członkowskiego, który jest wykluczony z grupy nadrzędnej.

- Członkostwo w grupie jest rekursywne. Na przykład:

    * **Paweł** jest elementem członkowskim tylko jednej grupy — grupy zabezpieczeń **Użytkownicy laptopów** .

    * Grupa **Użytkownicy laptopów** jest elementem członkowskim grupy zabezpieczeń **Zatwierdzeni użytkownicy** .

    * Tworzysz grupę w usłudze Intune używającą dynamicznego zapytania o członkostwo, które obejmuje członków grupy **Zatwierdzeni użytkownicy**. W rezultacie grupa użytkowników usługi Intune będzie zawierać użytkownika **Paweł**.

> [!TIP]
> Podczas tworzenia grup należy wziąć pod uwagę, jak będą stosowane zasady. Na przykład mogą istnieć zasady przeznaczone dla systemów operacyjnych urządzeń i zasady przeznaczone dla różnych ról w organizacji lub jednostek organizacyjnych zdefiniowanych już w usłudze Active Directory. Niektórzy administratorzy uważają za przydatne tworzenie grup urządzeń specyficznych dla systemów iOS, Android i Windows. Ten proces jest uzupełnieniem procesu tworzenia grup użytkowników dla każdej roli organizacyjnej.

<!--- should we just link to a policies topic at this point and remove this? Ask Rob
 You'll probably want to create a default policy that applies to all groups and devices, to establish the basic compliance requirements of your organization. Then, you create more specific policies for the broadest categories of users and devices, for example, email policies for each of the device operating systems.

 Be careful when you name your policies, so that you can easily identify them later. For example, a good, descriptive policy name is **WP Email Policy for Entire Company**.

 Each time you create a restrictive policy, you'll want to communicate it to your users. After you create the more general groups and policies, pay attention to how you create smaller groups so that you can reduce unnecessary communication.--->

## <a name="built-in-groups"></a>Grupy wbudowane
Usługa Intune udostępnia dziewięć wbudowanych grup, których nie można edytować ani usunąć: <!--maybe a screen shot would be best?-->

-   **Wszyscy użytkownicy**
    -   Użytkownicy niezgrupowani
-   **Wszystkie urządzenia**
    -   Wszystkie komputery
    -   Wszystkie urządzenia przenośne
        -   Wszystkie urządzenia zarządzane bezpośrednio
        -   Wszystkie urządzenia zarządzane za pośrednictwem programu Exchange ActiveSync
    -   Wszystkie urządzenia należące do firmy
    -   Urządzenia niezgrupowane

> [!NOTE]
> Kieruj się zasadą: *należy zachować prostotę*. Jeśli Twoja organizacja nie ma specyficznych potrzeb, takich jak opisane w kolejnych sekcjach, użyj domyślnej struktury i zasad grup. Ułatwi to zarządzanie usługą w długoterminowej perspektywie. Konserwacja będzie łatwiejsza, jeśli możesz traktować użytkowników jednolicie. Przy małym zróżnicowaniu grup będzie trzeba utrzymywać mniejszą liczbę zasad.


### <a name="all-users-and-devices-in-your-organization"></a>Wszyscy użytkownicy i wszystkie urządzenia w Twojej organizacji
Zdefiniuj grupę nadrzędną dla wszystkich użytkowników i urządzeń w Twojej organizacji. Prawdopodobnie będziesz używać zasad dotyczących wszystkich elementów. Do tego celu możesz użyć grup domyślnych usługi Intune **Wszyscy użytkownicy** i **Wszystkie urządzenia**. Podgrupy pozwalające organizować urządzenia według określonych kryteriów, takie jak grupa „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) i grupa urządzeń należących do firmy, mogą być grupami podrzędnymi grup nadrzędnych **Wszyscy użytkownicy**  i **Wszystkie urządzenia**.

## <a name="customize-groups-for-your-organization"></a>Dostosowywanie grup na potrzeby organizacji

### <a name="byod-and-corporate-owned-devices"></a>Urządzenia BYOD i należące do firmy
Jeśli Twoja organizacja pozwala pracownikom korzystać w pracy z własnych urządzeń lub dostarcza urządzenia należące do firmy bądź stosuje oba te modele, zalecamy stosowanie odrębnych zasad dla wymienionych kategorii urządzeń.

W przypadku modelu BYOD lub stosowania obu modeli należy dokładnie zaplanować zasady, tak aby nie naruszały lokalnych przepisów dotyczących zachowania poufności. Utwórz grupę nadrzędną dla wszystkich użytkowników, którzy będą przynosili własne urządzenia. Tej grupy możesz użyć do stosowania zasad dotyczących wszystkich użytkowników należących do tej kategorii.

![Tworzenie grupy nadrzędnej BYOD](../media/Intune_Planning_Groups_BYOD_small.png)

Podobnie można utworzyć w organizacji grupę dla użytkowników urządzeń należących do firmy:

![Równorzędne grupy użytkowników (grupa BYOD i grupa dla urządzeń należących do firmy)](../media/Intune_Planning_Groups_BYOD_Hierachy_View_small.png)

<!---START HERE--->

### <a name="groups-for-geographic-regions"></a>Grupy dla regionów geograficznych
Jeśli Twoja organizacja potrzebuje zasad dla konkretnych regionów geograficznych, istnieje możliwość utworzenia grup na podstawie tego kryterium. Możesz oprzeć je na grupach regionalnych, które być może już utworzono w ramach Twojego wystąpienia usługi Active Directory, i synchronizować za pomocą usługi Azure Active Directory. Możesz również utworzyć grupy regionalne bezpośrednio w usłudze Azure Active Directory.

Kolejne zrzuty ekranu pokazują tworzenie grup usługi Intune opartych na grupach zsynchronizowanych z lokalnym wystąpieniem usługi Active Directory. Na potrzeby tych przykładów przyjęto, że istnieje grupa zabezpieczeń usługi Active Directory o nazwie **US Users Group**.

Najpierw podaj informacje ogólne.

![Zrzut ekranu przedstawiający obszar Edytowanie grupy](../media/Intune_Planning_Groups_AD_General_small.png)

W obszarze **Kryteria członkostwa** wybierz grupę **US Users Group** zsynchronizowaną z usługą Active Directory jako grupę zabezpieczeń do użycia w ramach reguł członkostwa.

![Zrzut ekranu przedstawiający okno dialogowe Edytowanie grupy](../media/Intune_Planning_Groups_AD_Criteria_small.png)

Przejrzyj wpisy, a następnie wybierz pozycję **Zakończ**, aby utworzyć grupę.

![Zrzut ekranu przedstawiający okno dialogowe Edytowanie grupy](../media/Intune_Planning_Groups_AD_Summary_small.png)

W przykładzie utworzono również grupę o nazwie **MEA** (Środkowy Wschód i Azja).

> [!NOTE]
> Jeśli członkostwo w grupie nie zostanie wypełnione na podstawie przynależności do grupy zabezpieczeń, upewnij się, że do tych elementów członkowskich grupy zostały przypisane licencje usługi Intune.

### <a name="groups-for-specific-hardware"></a>Grupy dla konkretnego sprzętu
Jeśli w Twojej organizacji są wymagane zasady dotyczące konkretnych typów sprzętu, możesz tworzyć grupy na podstawie tego kryterium. Zasady możesz oprzeć na konkretnych grupach, które już utworzono w ramach lokalnego wystąpienia usługi Active Directory, a następnie synchronizować je za pomocą usługi Azure Active Directory. Możesz również utworzyć grupy bezpośrednio w usłudze Azure Active Directory. W tym przykładzie użyto grupy **US Users Group** jako grupy nadrzędnej względem grupy **Laptop Users**.

![Okno dialogowe Wybieranie grupy zabezpieczeń](../media/Intune_Planning_Groups_Laptop_small.png)

W tym momencie hierarchia grupy powinna wyglądać podobnie do przedstawionej na następnym zrzucie ekranu. Jak widać, grupa **Laptop Users** usługi Intune ma teraz członków. Wszystkie zasady zastosowane dla tej grupy będą dotyczyć użytkowników laptopów BYOD z regionu Stanów Zjednoczonych.

![Reprezentacja graficzna grupy użytkowników laptopów](../media/Intune_Planning_Groups_Laptop_Hierarchy_small.png)

### <a name="groups-for-specific-operating-systems"></a>Grupy dla poszczególnych systemów operacyjnych
Jeśli w Twojej organizacji są wymagane zasady dotyczące konkretnych systemów operacyjnych, takich jak Android, iOS i Windows, możesz utworzyć grupy na podstawie tego wymagania. Podobnie jak w przypadku wcześniejszych przykładów, możesz oprzeć grupy na konkretnych grupach przeznaczonych dla systemów operacyjnych, które już utworzono w ramach lokalnego wystąpienia usługi Active Directory, i synchronizować je za pomocą usługi Azure Active Directory. Możesz także utworzyć je bezpośrednio w używanym wystąpieniu usługi Azure Active Directory.

Za pomocą tej samej metody co we wcześniejszych przykładach można utworzyć grupy na podstawie użytkowników<!--devices?-->, którzy używają konkretnych platform systemu operacyjnego.

> [!NOTE]
> Jeśli istnieją użytkownicy używający wielu platform mobilnych lub systemów operacyjnych, a nie istnieje sposób automatycznej klasyfikacji użytkowników jako użytkowników systemu Android, iOS lub Windows, należy rozważyć stosowanie zasad na poziomie urządzeń. Zapewni to większą elastyczność stosowania zasad dla konkretnych systemów operacyjnych.
>
> Nie można dynamicznie aprowizować grup na podstawie systemu operacyjnego urządzenia. Zamiast tego należy to zrobić przy użyciu grup zabezpieczeń usługi Active Directory lub Azure Active Directory.

![Grupa użytkowników laptopów](../media/Intune_Planning_Groups_OS_Hierachy_small.png)

Gdy wszystkie grupy użytkowników zostaną wypełnione na podstawie wymagań organizacyjnych, hierarchia grup powinna przypominać następującą:

![Widok hierarchii grup](../media/Intune_Planning_Groups_Midpoint_Hierachy_small.png)

Ta hierarchia może służyć do stosowania zasad organizacji.

### <a name="device-groups"></a>Grupy urządzeń
Możesz również tworzyć podobne grupy urządzeń na potrzeby scenariusza BYOD w sposób przedstawiony tutaj, rozpoczynając od szerokiej grupy, która obejmuje wszystkie urządzenia należące do pracowników.

![Okno dialogowe Tworzenie grupy](../media/Intune_Planning_Groups_Device_General_small.png)

Upewnij się, że wybrano opcję **Wszystkie urządzenia (komputery i urządzenia przenośne)**, aby grupa zawierała wszystkie urządzenia typu „Przynieś własne urządzenie”:

![Strona Definiowanie kryteriów członkostwa](../media/Intune_Planning_Groups_Device_Criteria_small.png)

Przejrzyj wpisy, a następnie wybierz pozycję **Zakończ**, aby utworzyć grupę BYOD.

![Okno dialogowe Tworzenie grupy](../media/Intune_Planning_Groups_Device_Summary_small.png)

Kontynuuj tworzenie grup urządzeń aż do uzyskania hierarchii grup urządzeń podobnej do hierarchii grup użytkowników. Węzeł grup w konsoli usługi Intune będzie wyglądać podobnie do następującego:

![Widok hierarchii grup usługi Intune](../media/Intune_Groups_Hierarchy_Final_Small.png)

## <a name="group-hierarchies-and-naming-conventions"></a>Hierarchie grup i konwencje nazewnictwa
Aby ułatwić zarządzanie zasadami, zalecamy nadanie każdej zasadzie nazwy zgodnie z przeznaczeniem, platformą i zakresem, których dotyczy. Użyj standardu nazewnictwa odpowiadającego strukturze grup utworzonej podczas przygotowań do zastosowania zasad.

Na przykład w przypadku zasad systemu Android, które są stosowane do wszystkich firmowych urządzeń przenośnych z systemem Android na poziomie regionalnym Stany Zjednoczone, zasady mogą mieć nazwę **CO_US_Mob_Android_General**.

![Tworzenie zasad dla systemu Android](../media/Intune_planning_policy_android_small.png)

Nadawanie zasadom nazw w ten sposób umożliwi szybkie identyfikowanie zasad, ich przeznaczenia i zakresu z poziomu węzła **Zasady**, co przedstawiono poniżej:

![Lista zasad usługi Intune](../media/Intune_planning_policy_view_small.png)

## <a name="next-steps"></a>Następne kroki
[Tworzenie grup](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)

