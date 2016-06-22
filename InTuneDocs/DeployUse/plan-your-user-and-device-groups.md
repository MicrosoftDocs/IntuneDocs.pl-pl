---
# required metadata

title: Planowanie grup użytkowników i urządzeń | Microsoft Intune
description:
keywords:
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f11bb256-1094-4f7e-b826-1314c57f3356

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Planowanie grup użytkowników i urządzeń
Grupy w usłudze Intune zapewniają dużą elastyczność w zakresie zarządzania urządzeniami i użytkownikami. Grupy można skonfigurować zgodnie z potrzebami organizacji na podstawie:

- położenia geograficznego,
- działu,
- właściwości sprzętu,
- systemu operacyjnego,
- przynależności urządzeń do użytkowników lub firmy.


## Jak działają grupy usługi Intune


Domyślny widok węzła Grupy w konsoli administracyjnej usługi Intune jest następujący:

![Zrzut ekranu przedstawiający widok domyślny węzła Grupy w konsoli usługi Intune](/intune/media/Intune_Planning_Groups_Default_small.png)

Zasady są wdrażane do grup, dlatego hierarchia grupy jest jednym z najważniejszych zagadnień projektowych. Należy również pamiętać, że po utworzeniu grupy nie można zmienić grupy nadrzędnej, więc projekt grup jest bardzo ważny od początku korzystania z usługi Intune. Niektóre zalecane praktyki projektowania hierarchii grup odpowiednio do potrzeb organizacji są opisane poniżej.

## Reguły członkostwa w grupach

1. Grupa może zawierać użytkowników lub urządzenia, ale nie oba te elementy jednocześnie.

    * **Grupy urządzeń:** dotyczy zarówno komputerów, jak i urządzeń przenośnych. Aby można było dodać komputer do grupy, musi być on zarejestrowany. Aby można było dodać urządzenie przenośne do grupy, środowisko musi być skonfigurowane do obsługi urządzeń przenośnych i urządzenia muszą być zarejestrowane lub wykryte za pomocą programu Exchange ActiveSync.

    * **Grupy użytkowników:** grupa może zawierać użytkowników z grup zabezpieczeń, które są synchronizowane z usługi Active Directory. Jeśli nie używasz synchronizacji usługi Active Directory, możesz utworzyć te grupy ręcznie.

2. Urządzenie lub użytkownik może należeć do więcej niż jednej grupy.

3. Elementy członkowskie mogą być dołączane do grupy lub wykluczane z niej na podstawie następujących reguł członkostwa:

    * **Kryteria członkostwa:** są to dynamiczne reguły, których usługa Intune używa do uwzględniania lub wykluczania członków. W tych kryteriach są używane **grupy zabezpieczeń** i inne informacje synchronizowane z lokalnej usługi Active Directory. Jeśli grupa zabezpieczeń lub dane zostaną zmienione, członkostwo w grupie ulega zmianie po synchronizacji z usługą Active Directory.

    * **Członkostwo bezpośrednie:** są to statyczne reguły, które jawnie dodają lub wykluczają elementy członkowskie. Lista członkostwa jest statyczna.

4. Usługi domenowe Active Directory (AD DS) nie są wymagane do utworzenia grup użytkowników lub grup urządzeń, które zawierają użytkowników lub komputery, jednak w przypadku urządzeń przenośnych środowisko musi być skonfigurowane pod kątem ich obsługi.

    Ponadto urządzenia muszą zostać wykryte i dodane do usługi Intune.

## Reguły relacji grup

1. Każda tworzona grupa musi mieć grupę nadrzędną, której nie można zmienić po utworzeniu grupy.

2. W przypadku dodawania użytkowników lub urządzeń do grupy podrzędnej:

    * Grupy podrzędne są zawsze podzbiorami grupy nadrzędnej.

    * Nowe elementy członkowskie dodane do grupy podrzędnej są automatycznie dodawane do jej grupy nadrzędnej.

    * Nie można dodać elementu członkowskiego do grupy podrzędnej, jeśli jest on wykluczony z grupy nadrzędnej.

3. Członkostwo grupy nadrzędnej definiuje dostępne członkostwa dla grupy podrzędnej.

4. Usunięcie grupy nadrzędnej spowoduje usunięcie wszystkich grup podrzędnych.

5. Możesz wdrożyć zawartość i zasady w grupie nadrzędnej bez jednoczesnego wdrażania ich w grupach podrzędnych.

6. Do grupy podrzędnej możesz dodać określonego użytkownika lub urządzenie, które nie jest elementem członkowskim grupy nadrzędnej. W takim przypadku nowy element członkowski zostanie dodany do grupy nadrzędnej.

    Jednak nie można dodać do grupy podrzędnej takiego elementu członkowskiego, który jest wykluczony z grupy nadrzędnej.

7. Członkostwo w grupie jest rekursywne. Na przykład:

    * **Paweł** jest elementem członkowskim tylko jednej grupy — grupy zabezpieczeń **Użytkownicy laptopów** .

    * Grupa **Użytkownicy laptopów** jest elementem członkowskim grupy zabezpieczeń **Zatwierdzeni użytkownicy** .

    * Tworzysz grupę w usłudze Intune używającą dynamicznego zapytania o członkostwo, które obejmuje członków grupy **Zatwierdzeni użytkownicy**. W rezultacie grupa użytkowników usługi Intune będzie zawierać użytkownika **Paweł**.

> [!TIP]
> Podczas tworzenia grup należy wziąć pod uwagę, jak będą stosowane zasady. Na przykład są zasady właściwe dla systemów operacyjnych urządzeń i zasady właściwe dla różnych ról w organizacji lub jednostek organizacyjnych zdefiniowanych już w usłudze Active Directory. Niektórzy uważają, że warto mieć grupy urządzeń właściwe dla systemu iOS, Android i Windows, a także grupy użytkowników dla poszczególnych ról organizacyjnych.

<!--- should we just link to a policies topic at this point and remove this? Ask Rob
 You'll probably want to create a default policy that applies to all groups and devices, to establish the basic compliance requirements of your company. Then create more specific policies for the broadest categories of users and devices, for example, email policies for each of the device operating systems.

 Be careful naming your policies so that you can easily identify them later. For example, a good, descriptive policy name is **WP Email Policy for Entire Company**.

 Each time you create a restrictive policy you'll want to communicate it to your users, so after you create the more general groups and policies pay attention to how you create smaller groups so that you can reduce unnecessary communication.--->

## Grupy wbudowane
Usługa Intune udostępnia dziewięć grup wbudowanych, których nie można edytować ani usunąć: <!--maybe a screen shot would be best?-->

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
> Kieruj się zasadą: *należy zachować prostotę*. Jeśli Twoja organizacja nie ma określonych potrzeb, takich jak opisane poniżej, wówczas zachowanie prostoty oraz pozostawienie domyślnej struktury i zasad grup ułatwi zarządzanie usługą w długoterminowej perspektywie. Konserwacja będzie łatwiejsza, jeśli użytkowników można traktować jednakowo, przy niewielkim zróżnicowaniu zależnie od grup — zmniejszy to liczbę zasad do obsługi.


### Wszyscy użytkownicy i wszystkie urządzenia w Twojej organizacji
Dla wszystkich użytkowników i urządzeń w Twojej organizacji zdefiniuj grupę nadrzędną, ponieważ prawdopodobnie będą istnieć zasady dotyczące ich wszystkich. W tym celu możesz użyć grup domyślnych **Wszyscy użytkownicy** i **Wszystkie urządzenia** w usłudze Intune. Podgrupy pozwalające organizować urządzenia według określonych kryteriów, takie jak grupa „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) i grupa urządzeń należących do firmy, mogą być elementami podrzędnymi grup nadrzędnych **Wszyscy użytkownicy ** i **Wszystkie urządzenia**.

## Dostosowywanie grup na potrzeby organizacji

### Urządzenia „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) i urządzenia należące do firmy
Jeśli Twoja organizacja pozwala pracownikom korzystać w pracy z własnych urządzeń (model BYOD), zapewnia urządzenia należące do firmy albo stosuje oba te modele, zalecamy stosowanie zasad na podstawie obu tych kategorii urządzeń.

W przypadku modelu BYOD lub stosowania obu modeli należy dokładnie zaplanować zasady, tak aby nie naruszały lokalnych przepisów dotyczących zachowania poufności. Utwórz grupę nadrzędną dla wszystkich użytkowników, którzy będą przynosili własne urządzenia. Tej grupy będzie można używać do stosowania zasad dotyczących wszystkich użytkowników należących do tej kategorii.

![Zrzut ekranu przedstawiający tworzenie grupy nadrzędnej BYOD](/intune/media/Intune_Planning_Groups_BYOD_small.png)

Podobnie można utworzyć w organizacji grupę dla użytkowników urządzeń należących do firmy:

![Zrzut ekranu przedstawiający równorzędne grupy użytkowników (grupa BYOD i grupa dla urządzeń należących do firmy)](/intune/media/Intune_Planning_Groups_BYOD_Hierachy_View_small.png)

<!---START HERE--->

### Grupy dla regionów geograficznych
Jeśli w Twojej organizacji są potrzebne zasady dla konkretnych regionów, możesz tworzyć grupy na podstawie tego kryterium. Można je utworzyć na podstawie grup regionalnych, które mogły już zostać utworzone w usłudze Active Directory (AD), a następnie zsynchronizować je z usługą Azure AD. Można je również utworzyć bezpośrednio w usłudze Azure AD.

Te zrzuty ekranu pokazują, jak tworzyć grupy w usłudze Intune w oparciu o grupy synchronizowane z lokalnej usługi AD. W tym przykładzie obowiązuje założenie, że istnieje grupa zabezpieczeń usługi AD o nazwie **US Users Group**.

1. Najpierw podaj informacje ogólne.

![Zrzut ekranu przedstawiający obszar Edytowanie grupy](/intune/media/Intune_Planning_Groups_AD_General_small.png)

W obszarze Kryteria członkostwa wybierz grupę **US Users Group** zsynchronizowaną z usługi AD jako grupę zabezpieczeń do użycia w ramach reguł członkostwa.

![Okno dialogowe Edytowanie grupy](/intune/media/Intune_Planning_Groups_AD_Criteria_small.png)

Przejrzyj informacje i wybierz pozycję **Zakończ**, aby zakończyć tworzenie grupy.

![Okno dialogowe Edytowanie grupy](/intune/media/Intune_Planning_Groups_AD_Summary_small.png)

W naszym przykładzie utworzona również została grupa MEA (Middle East and Asia).

> [!NOTE] Jeśli członkostwo w grupie nie zostanie wypełnione na podstawie przynależności do grupy zabezpieczeń, upewnij się, że do tych członków została przypisana licencja na usługę Intune.

### Grupy dla konkretnego sprzętu
Jeśli w Twojej organizacji są wymagane zasady dotyczące konkretnych typów sprzętu, możesz tworzyć grupy na podstawie tego kryterium. Można je utworzyć na podstawie określonych grup utworzonych już w lokalnej usłudze AD, a następnie zsynchronizować je z usługą Azure AD. Można je również utworzyć bezpośrednio w usłudze Azure AD. W tym przykładzie użyto grupy **US Users Group** jako nadrzędnej względem grupy **Laptop Users**.

![Okno dialogowe Wybieranie grupy zabezpieczeń](/intune/media/Intune_Planning_Groups_Laptop_small.png)

W takim przypadku hierarchia grup powinna być taka jak pokazano poniżej. Jak widać, w grupie Intune **Laptop Users** istnieją teraz członkowie. Wszystkie zasady zastosowane do tej grupy będą teraz dotyczyć użytkowników laptopów BYOD z regionu Stanów Zjednoczonych.

![Reprezentacja graficzna grupy użytkowników laptopów](/intune/media/Intune_Planning_Groups_Laptop_Hierarchy_small.png)

### Grupy dla poszczególnych systemów operacyjnych
Jeśli w Twojej organizacji są wymagane zasady dotyczące konkretnych systemów operacyjnych, takich jak Android, iOS i Windows, możesz tworzyć grupy na podstawie tego wymagania. Tak samo jak w poprzednich przykładach, można je utworzyć na podstawie grup, które dotyczą określonych systemów operacyjnych i zostały już utworzone w lokalnej usłudze AD, a następnie zsynchronizować je z usługą Azure AD. Można je również utworzyć bezpośrednio w usłudze Azure AD.

Stosując taką samą metodę jak w poprzednich przykładach, można utworzyć grupy na podstawie użytkowników <!--devices?--> przy użyciu określonych platform systemu operacyjnego.

> [!NOTE] Jeśli istnieją użytkownicy używający różnych platform mobilnych/systemów operacyjnych, a nie istnieje sposób automatycznej klasyfikacji użytkowników jako użytkowników systemu Android, iOS albo Windows, należy rozważyć stosowanie zasad na poziomie urządzeń, co zapewni większą elastyczność stosowania zasad dla konkretnych systemów operacyjnych.
>
> Na podstawie systemu operacyjnego urządzenia nie można dynamicznie udostępniać grup. Można to zrobić przy użyciu grup zabezpieczeń usługi AD lub usługi AAD.

![Reprezentacja graficzna grupy użytkowników laptopów](/intune/media/Intune_Planning_Groups_OS_Hierachy_small.png)

Gdy wszystkie grupy użytkowników zostaną wypełnione na podstawie tych wymagań organizacyjnych, hierarchia grup powinna przypominać następującą:

![Widok hierarchii grup](/intune/media/Intune_Planning_Groups_Midpoint_Hierachy_small.png)

Ta hierarchia może służyć do odpowiedniego stosowania zasad organizacji.

### Grupy urządzeń
Możesz również tworzyć podobne grupy urządzeń na potrzeby scenariusza BYOD w sposób przedstawiony poniżej, rozpoczynając od szerokiej grupy, która obejmuje wszystkie urządzenia należące do pracowników:

![Okno dialogowe Tworzenie grupy](/intune/media/Intune_Planning_Groups_Device_General_small.png)

Upewnij się, że wybrana jest opcja **Wszystkie urządzenia (komputery i urządzenia przenośne)**, aby grupa zawierała wszystkie urządzenia typu „Przynieś własne urządzenie”:

![Strona Definiowanie kryteriów członkostwa](/intune/media/Intune_Planning_Groups_Device_Criteria_small.png)

Przejrzyj informacje i wybierz pozycję **Zakończ**, aby utworzyć grupę BYOD.

![Okno dialogowe Tworzenie grupy](/intune/media/Intune_Planning_Groups_Device_Summary_small.png)

Kontynuuj tworzenie grup urządzeń aż do uzyskania hierarchii grup urządzeń podobnej do hierarchii grupy użytkownika. Wtedy Twój węzeł grupy w konsoli usługi Intune powinien wyglądać podobnie do poniższego:

![Widok hierarchii grup usługi Intune](/intune/media/Intune_Groups_Hierarchy_Final_Small.png)

## Hierarchie grup i konwencje nazewnictwa
Aby ułatwić zarządzanie zasadami, zalecamy nadanie każdej zasadzie nazwy zgodnie z przeznaczeniem, platformą i zakresem, do którego jest stosowana. Ten standard nazewnictwa powinien być zgodny ze strukturą grup utworzoną podczas przygotowania do stosowania zasad.

Na przykład w przypadku zasad systemu Android, które są stosowane do wszystkich firmowych urządzeń przenośnych z systemem Android na poziomie regionalnym USA, zasady mogą mieć nazwę: **CO_US_Mob_Android_General**.

![Tworzenie zasad dla systemu Android](/intune/media/Intune_planning_policy_android_small.png)

Nadawanie zasadom nazw w ten sposób umożliwi szybkie identyfikowanie zasad, ich przeznaczenia i zakresu z poziomu węzła zasad konsoli, co przedstawiono poniżej:

![Lista zasad usługi Intune](/intune/media/Intune_planning_policy_view_small.png)

## Następne kroki
[Tworzenie grup](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)


<!--HONumber=Jun16_HO3-->


