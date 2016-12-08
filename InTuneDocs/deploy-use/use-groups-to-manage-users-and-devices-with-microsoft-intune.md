---
title: "Używanie grup do zarządzania użytkownikami i urządzeniami | Microsoft Intune"
description: "Twórz grupy i zarządzaj nimi za pomocą obszaru roboczego Grupy."
keywords: 
author: Mtillman
ms.author: mtillman
manager: angrobe
ms.date: 10/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb9b01ce-9b9b-4c2a-bf99-3879c0bdaba5
ms.reviewer: lpatha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 46fd83ac8048a313b0fe4f15e01563698bf7995c


---
# <a name="use-groups-to-manage-users-and-devices-in-microsoft-intune"></a>Używanie grup do zarządzania użytkownikami i urządzeniami w usłudze Microsoft Intune

W tym temacie opisano sposób tworzenia grup w usłudze Intune. Temat zawiera także informacje o tym, w jaki sposób zarządzanie grupami może zmienić się na przestrzeni nadchodzących miesięcy. 

>[!IMPORTANT]
>
>Jeśli otworzysz obszar roboczy Grupy w portalu Intune i będzie widoczny link do portalu usługi Azure Active Directory (Azure AD), oznacza to, że używane jest już *nowe* podejście do grup zabezpieczeń usługi Azure AD służące do zarządzania grupami w usłudze Intune opisane w sekcji [Informacja o nadchodzących ulepszeniach środowiska pracy administratora dla grup](#notice-of-upcoming-improvements-to-the-admin-experience-for-groups). Kliknij link do portalu usługi Azure AD, aby utworzyć grupy i zarządzać nimi.
>
>![Zrzut ekranu przedstawiający link do grupy zarządzania platformy Azure](../media/groups-link-azure.png) 
>
>Jeśli nie jest widoczny link do portalu usługi Azure AD, oznacza to, że nadal używane jest *bieżące* podejście do zarządzania grupami opisane w sekcji [Tworzenie grup do zarządzania użytkownikami i urządzeniami w usłudze Microsoft Intune](#Create-groups-to-manage-users-and-devices-with-Microsoft-Intune) w tym temacie.


## <a name="notice-of-upcoming-improvements-to-the-admin-experience-for-groups"></a>Informacja o nadchodzących ulepszeniach środowiska pracy administratora dla grup

Otrzymaliśmy opinie użytkowników z sugestiami, aby istniało jedno środowisko grupowania i kierowania w pakiecie Enterprise Mobility + Security. Wzięliśmy to pod uwagę. Na podstawie tych opinii wkrótce będzie miało miejsce konwertowanie grup usługi Intune do grup zabezpieczeń opartych na usłudze Azure Active Directory. Ta zmiana spowoduje ujednolicenie zarządzania grupami w usłudze Intune i usłudze Azure Active Directory (Azure AD). Nowe środowisko oznacza, że nie będzie już potrzeby duplikowania grup między usługami. Zostanie również rozszerzona funkcjonalność dzięki możliwości użycia programu Windows PowerShell i Microsoft Graph.

### <a name="how-does-this-affect-me-right-now"></a>Jak to wpłynie na moją bieżącą pracę?
Jeśli korzystasz już z usługi Intune, ta zmiana nie ma teraz na Ciebie wpływu. Możemy natomiast określić, co będzie miało miejsce wkrótce:

-   Nowe konta będą używać grup zabezpieczeń usługi Azure AD zamiast grup *użytkowników* usługi Intune.   
-   W listopadzie 2016 r. nowe konta aprowizowane po comiesięcznym wydaniu usługi będą zarządzać grupami opartymi na użytkownikach i zasobach w portalu usługi Azure AD. Nie będzie miało to żadnego wpływu na istniejących klientów.
-   W grudniu 2016 r. zespół produktu Intune rozpocznie migrowanie istniejących klientów do nowego środowiska zarządzania grupami opartego na usłudze Azure AD. Wszystkie grupy użytkowników i urządzeń istniejące teraz w usłudze Intune zostaną zmigrowane do grup zabezpieczeń usługi Azure AD. Migracje zostaną rozpoczęte dopiero wtedy, gdy nie będą miały wpływu na Twoją codzienną pracę i pracę użytkowników. Przed migracją Twojego konta otrzymasz powiadomienie.


### <a name="how-and-when-will-i-migrate-to-the-new-groups-experience"></a>W jaki sposób i kiedy zostanie przeprowadzona migracja do nowego środowiska grup?
Bieżący klienci usługi Intune będą migrowani przez pewien czas. Teraz ma miejsce finalizowanie harmonogramu dla tej migracji. Ten temat zostanie zaktualizowany w ciągu kilku tygodni i będzie zawierał więcej szczegółów. Przed migracją otrzymasz powiadomienie. Jeśli masz jakiekolwiek wątpliwości dotyczące migracji, skontaktuj się z naszym zespołem ds. migracji, wysyłając wiadomość e-mail na adres [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com). Zobacz [Migrowanie grup do usługi Azure Active Directory](migrating-groups-to-azure-active-directory.md), aby uzyskać szczegółowe informacje na temat sposobu migrowania grup.

### <a name="what-happens-to-my-existing-user-and-device-groups"></a>Co się stanie z moimi istniejącymi grupami użytkowników i urządzeń?
 Grupy użytkowników i grupy urządzeń utworzone w usłudze Intune zostaną zmigrowane do grup zabezpieczeń usługi Azure AD. Domyślne grupy usługi Intune, takie jak grupa Wszyscy użytkownicy, zostaną zmigrowane tylko wtedy, jeśli będą używane we wdrożeniach w czasie migracji. Migracje niektórych grup mogą być bardziej skomplikowane. Powiadomimy Cię, jeśli na potrzeby migracji będzie wymagane wykonanie dodatkowych czynności w Twojej organizacji.

### <a name="what-new-features-will-be-available-to-me"></a>Jakie nowe funkcje będą dla mnie dostępne?
Poniżej przedstawiono nowe funkcje, które zostaną wprowadzone w ramach tej migracji z usługi Intune do usługi Azure Active Directory:

-    Grupy zabezpieczeń usługi Azure AD będą obsługiwane w usłudze Intune dla wszystkich typów wdrożeń.
-    Grupy zabezpieczeń usługi Azure AD będą obsługiwać grupowanie urządzeń i użytkowników.
-    Grupy zabezpieczeń usługi Azure AD będą obsługiwać grupy dynamiczne z atrybutami urządzeń usługi Intune. Na przykład możliwe będzie dynamiczne grupowanie urządzeń według platformy, takiej jak iOS. Podczas rejestrowania nowego urządzenia z systemem iOS w organizacji zostanie ono automatycznie dodane do dynamicznej grupy urządzeń z systemem iOS.
-    Dzięki temu będzie istnieć współużytkowane środowiska pracy administratora na potrzeby zarządzania grupami w usłudze Azure AD i usłudze Intune.
- Rola administratora usługi Intune zostanie dodana do usługi Azure AD w celu umożliwienia administratorom w usłudze Intune wykonywania zadań zarządzania grupami w usłudze Azure AD.

### <a name="what-intune-functionality-wont-be-available"></a>Jakie funkcje usługi Intune nie będą dostępne?
Chociaż środowisko grupy zostanie ulepszone, po migracji z grup usługi Intune do grup zabezpieczeń usługi Azure AD w usłudze Intune nie będą dostępne pewne funkcje.

#### <a name="group-management-functionality"></a>Funkcja zarządzania grupami

-   Po migracji nie będzie możliwe wykluczanie członków ani grup podczas tworzenia nowej grupy. Grupy dynamiczne usługi Azure AD będą jednak umożliwiały używanie atrybutów do tworzenia zaawansowanych reguł mogących służyć do wykluczania członków na podstawie ustawionych kryteriów.
-   Grupy Użytkownicy niezgrupowani i Urządzenia niezgrupowane nie będą obsługiwane. Te grupy nie zostaną zmigrowane z usługi Intune do usługi Azure AD.


#### <a name="group-dependent-functionality"></a>Funkcja zależna od grupy

-   Rola administratora usługi nie będzie miała uprawnienia do **zarządzania grupami**.
-   Nie będzie możliwe grupowanie urządzeń programu Exchange ActiveSync. Twoja grupa Wszystkie urządzenia zarządzane przez program EAS zostanie przekonwertowana z grupy na widok raportu.
-  Przestawianie z grupami w raportach nie będzie dostępne.
-  Określanie grup niestandardowych jako obiektów docelowych reguł powiadomień nie będzie dostępne.

### <a name="what-should-i-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
 Mamy następujące zalecenia, które ułatwią to przejście:

- Wyczyść wszystkie niepożądane lub niepotrzebne grupy Intune przed migracją.
- Oceń zastosowanie wykluczeń w grupach i rozważ zmianę projektu grup, dzięki czemu nie będzie konieczne używanie wykluczeń.
-  Jeśli istnieją administratorzy, którzy nie mają uprawnień do tworzenia grup w usłudze Azure AD, skontaktuj się z administratorem usługi Azure AD, aby dodać ich do roli administratora usługi Intune w usłudze Azure AD.


## <a name="create-groups-to-manage-users-and-devices-with-microsoft-intune"></a>Tworzenie grup do zarządzania użytkownikami i urządzeniami w usłudze Microsoft Intune

W tej sekcji opisano sposób tworzenia grup w usłudze Intune w konsoli administracyjnej Intune.

Za pomocą obszaru roboczego **Grupy** w konsoli administracyjnej usługi Microsoft Intune można tworzyć grupy i zarządzać nimi. Strona **Przegląd grup** zawiera podsumowania stanów, które ułatwiają zidentyfikowanie i ustalenie priorytetów dla problemów wymagających uwagi. Podsumowania stanów dotyczą następujących zagadnień:

-   Alerty
-   Aktualizacje oprogramowania
-   Program Endpoint Protection
-   Zasady
-   Zarządzanie oprogramowaniem

Ponadto w hierarchii grup wyświetlane są podsumowania stanów ułatwiające identyfikację i rozwiązywanie problemów dotyczących członków wybranej grupy.

## <a name="create-groups"></a>Tworzenie grup

> [!TIP]
> Podczas tworzenia grup należy wziąć pod uwagę sposób stosowania zasad. Na przykład mogą istnieć zasady przeznaczone dla systemów operacyjnych urządzeń i zasady przeznaczone dla różnych ról w organizacji lub jednostek organizacyjnych zdefiniowanych już w usłudze Active Directory. Przydatne może być posiadanie oddzielnych grup urządzeń dla systemu iOS, Android i Windows, a także grupy użytkowników dla poszczególnych ról organizacyjnych.
>
> Prawdopodobnie warto również utworzyć zasady domyślne dotyczące wszystkich grup i urządzeń w celu ustalenia podstawowych wymagań zgodności w firmie. Następnie można utworzyć bardziej szczegółowe zasady dla najszerszych kategorii użytkowników i urządzeń. Można na przykład utworzyć zasady poczty e-mail dla każdego systemu operacyjnego urządzenia.
>
> Należy nadawać zasadom odpowiednie nazwy, aby można je było później łatwo rozpoznać. Na przykład, właściwą opisową nazwą zasad może być **Zasady poczty e-mail WP dla całej firmy**.
>
> Za każdym razem, gdy tworzy się zasady ograniczające, należy o nich poinformować użytkowników. W związku z tym po utworzeniu bardziej ogólnych grup i zasad należy zwrócić uwagę na sposób tworzenia mniejszych grup, aby ograniczyć zbędny przepływ informacji.

### <a name="to-create-a-device-group"></a>Aby utworzyć grupę urządzeń

1.  W konsoli administracyjnej usługi Intune wybierz pozycję **Grupy** &gt; **Przegląd** &gt; **Utwórz grupę**.

2.  Wprowadź nazwę i opcjonalny opis grupy, a następnie wybierz grupę urządzeń jako grupę nadrzędną. Wybierz pozycję **Next** (Dalej).

3.  Na stronie **Zdefiniuj kryteria członkostwa** wybierz typ urządzeń, które mają zostać dołączone do grupy. Istnieją dodatkowe opcje konfiguracji grupy na podstawie typów urządzeń, które zostaną dołączone:

    -   **Komputer**. Wybierz, czy mają zostać dołączone wszystkie elementy członkowskie grupy nadrzędnej, a także podaj jednostki organizacyjne i domeny, które mają zostać dołączone lub wykluczone. Informacje dotyczące jednostki organizacyjnej i domeny komputera można uzyskać ze spisu.

    -   **Urządzenia przenośne**. Wybierz, czy mają zostać dołączone urządzenia przenośne zarządzane przez usługę Intune, urządzenia przenośne zarządzane przez program Exchange ActiveSync, czy oba typy urządzeń.

    -   **Wszystkie urządzenia**. Ta opcja powoduje dołączenie wszystkich urządzeń bez wykluczeń na podstawie wszystkich kryteriów.

4.  Na stronie **Zdefiniuj członkostwo bezpośrednie** dołącz lub wyklucz poszczególne urządzenia, klikając pozycję **Przeglądaj**. Jeśli wybierzesz urządzenia, które nie znajdują się w podanej grupie nadrzędnej, zostaną one automatycznie dodane do grupy nadrzędnej za pomocą usługi Intune.

5.  Na stronie **Podsumowanie** przejrzyj wybrane opcje, a następnie kliknij pozycję **Zakończ**.

Nowo utworzona grupa zostanie wyświetlona na liście **Grupy** w obszarze roboczym **Grupy** w ramach grupy nadrzędnej. W tym miejscu możesz także edytować lub usunąć grupę.

### <a name="to-create-a-user-group"></a>Aby utworzyć grupę użytkowników

1.  W konsoli administracyjnej usługi Intune wybierz pozycję **Grupy** &gt; **Przegląd** &gt; **Utwórz grupę**.

2.  Wprowadź nazwę i opcjonalny opis grupy, a następnie wybierz grupę użytkowników jako grupę nadrzędną. Wybierz pozycję **Next** (Dalej).

3.  Na stronie **Zdefiniuj kryteria członkostwa** wybierz, czy mają zostać dołączeni wszyscy członkowie grupy nadrzędnej, czy też chcesz rozpocząć od pustej grupy. Następnie dołącz lub wyklucz członków na podstawie grup zabezpieczeń użytkowników skonfigurowanych ręcznie w [centrum administracyjnym usługi Office 365](http://go.microsoft.com/fwlink/?LinkId=698854) lub przeprowadź synchronizację z poziomu usługi Active Directory. Jeśli nastąpi zmiana członkostwa grupy zabezpieczeń, członkostwo grup użytkowników opartych na tej grupie zabezpieczeń może także ulec zmianie.

    > [!IMPORTANT]
    > Obecnie w przypadku grupy zawierającej członków z określonych grup zabezpieczeń lub grup kierowników oraz wykluczenia członków z określonych grup początkowo dołączeni członkowie zostaną usunięci. Aby utworzyć grupę, w której będą znajdować się dołączeni i wykluczeni członkowie, zaleca się utworzenie najpierw grupy nadrzędnej, do której będą należeć dołączeni członkowie. Następnie należy utworzyć grupę podrzędną dla tej grupy nadrzędnej. W nowej grupie podrzędnej należy utworzyć listę wykluczonych członków. Następnie należy użyć tej grupy podrzędnej do zarządzania zasadami usługi Intune, profilami i dystrybucją aplikacji.

    > [!NOTE]
    > W usłudze Azure Portal możesz utworzyć grupy oparte na kierownikach będących przełożonymi użytkowników. Jest to grupa typu dynamicznego, której członkowie zmieniają się wraz z dodawaniem lub usuwaniem pracowników w zespole danego kierownika w usłudze Azure Active Directory. Sposób tworzenia grupy kierownika na platformie Azure opisano w artykule [Using attributes to create advanced rules](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/) (Tworzenie zaawansowanych reguł przy użyciu atrybutów) w sekcji **To configure a group as a “Manager” group** (Aby skonfigurować grupę jako grupę kierownika).

4.  Na stronie **Zdefiniuj członkostwo bezpośrednie** dołącz lub wyklucz poszczególnych użytkowników, klikając pozycję **Przeglądaj**. Jeśli wybierzesz użytkowników, którzy nie znajdują się w podanej grupie nadrzędnej, zostaną oni automatycznie dodani do grupy nadrzędnej. W dolnej części okna dialogowego **Wybieranie członków** znajduje się opcja ręcznego dodawania użytkownika. Jest to przydatne, jeśli chcesz dodać użytkownika, który nie ma jeszcze zarejestrowanego urządzenia.

5.  Na stronie **Podsumowanie** przejrzyj wybrane opcje, a następnie kliknij pozycję **Zakończ**.

Nowo utworzona grupa zostanie wyświetlona na liście **Grupy** w obszarze roboczym **Grupy** w ramach grupy nadrzędnej. W tym miejscu możesz także edytować lub usunąć grupę.

> [!TIP]
> Grupy zabezpieczeń to odpowiedni zasób do użycia podczas wypełniania grup użytkowników. Grupy zabezpieczeń określają, kto ma dostęp do określonych zasobów, dlatego można je łatwo przekształcić w grupy użytkowników usługi Intune. Wszystkie grupy zabezpieczeń, które są synchronizowane z usługi Active Directory do usługi Azure Active Directory albo które są tworzone bezpośrednio w usłudze Azure Active Directory za pośrednictwem centrum administracyjnego usługi Office 365 lub usługi Azure Portal, są dostępne w momencie tworzenia grup użytkowników w usłudze Intune.

## <a name="filter-admin-views-by-role"></a>Filtrowanie widoków administratora według roli
Filtrowane widoki grup umożliwiają dostosowanie elementów, które będą widoczne dla administratora IT na podstawie jego roli. Można również ograniczyć grupy, którymi mogą zarządzać poszczególni administratorzy IT. Może to być przydatne w następujących przypadkach:

-   Administratorzy IT mają mieć możliwość wdrażania elementów tylko dla konkretnych użytkowników i urządzeń
-   Dla administratorów IT mają być wyświetlane tylko grupy z nimi związane

Filtrowane widoki grup można skonfigurować dla administratorów usługi w konsoli administracyjnej usługi Intune. Aby uzyskać szczegółowe informacje, zobacz [Co należy wiedzieć przed rozpoczęciem korzystania z usługi Microsoft Intune](/intune/get-started/what-to-know-before-you-start-microsoft-intune).

Po skonfigurowaniu filtrowanych widoków grup dla administratorów usługi podczas wdrażania przez nich oprogramowania lub zasad bądź uruchamiania raportów mogą oni wyświetlać i wybierać tylko określone grupy. Dla administratorów nie są również widoczne informacje o stanie na tych stronach konsoli administracyjnej:

-   **Przegląd systemu**
-   **Przegląd grup**
-   **Przegląd programu Endpoint Protection**
-   **Przegląd alertów**
-   **Przegląd oprogramowania**
-   **Przegląd zasad**

### <a name="to-create-a-filtered-group-view"></a>Aby utworzyć filtrowany widok grupy

1.  W konsoli administracyjnej usługi Intune wybierz pozycję **Administracja** &gt; **Zarządzanie administratorami** &gt; **Administratorzy usługi**.

2.  Wybierz administratora usługi, dla którego ma zostać utworzony filtrowany widok grupy, a następnie wybierz pozycję **Zarządzaj grupami**.

3.  W oknie dialogowym **Wybierz grupy, które będą widoczne dla administratora usługi** dodaj grupy, do których ma mieć dostęp administrator usługi, a następnie kliknij przycisk **OK**.

Po skonfigurowaniu filtrowanych widoków grup administrator IT będzie mógł wyświetlać i wybierać tylko wskazane grupy.

## <a name="manage-your-groups"></a>Zarządzanie grupami
Po utworzeniu grup można nimi zarządzać odpowiednio do potrzeb organizacji.

Można edytować grupę, zmieniając jej nazwę, opis lub należących do niej członków.

Grupę, która nie spełnia już wymagań organizacji, można usunąć. Usunięcie grupy nie powoduje usunięcia użytkowników, którzy do niej należą.

## <a name="next-steps"></a>Następne kroki
Po skonfigurowaniu grup i zasad sprawdź praktyczne efekty projektu, przeglądając informacje **Wartość zamierzona** i **Stan**.

### <a name="to-check-your-design"></a>Aby sprawdzić projekt

1. Wybierz dowolne urządzenie z grupy urządzeń i przeglądaj kategorie informacji w górnej części strony.
2. Wybierz pozycję **Zasady**. Zobaczysz ekran podobny do tego zrzutu ekranu przedstawiającego ustawienia zasad dotyczących urządzeń z systemem Android.

![Przykład zasad ustawień systemu Android](../media/Intune-Device-Policy-v.2.jpg)

Wszystkie zasady mają parametry **Wartość zamierzona** i **Stan**. Wartość zamierzona to wartość, która miała zostać osiągnięta w momencie przypisywania zasad. Stanem jest to, co się uzyskuje, gdy weźmie się pod uwagę wszystkie zasady dotyczące urządzenia, a także ograniczenia i wymagania sprzętowe oraz system operacyjny. Ten zrzut ekranu zawiera dwa proste przykłady:

-   Ustawienie **Zezwalaj na proste hasła** ma wartość **Tak**, jak pokazano w kolumnie **Wartość zamierzona**, ale jego ustawienie **Stan** ma wartość **Nie dotyczy**. Dzieje się tak, gdyż proste hasła nie są obsługiwane w przypadku urządzeń z systemem Android.
-   Podobnie, rozwinięty element zasad **Ustawienia poczty e-mail dla urządzeń z systemem iOS** nie ma zastosowania do tego urządzenia, ponieważ jest to urządzenie z systemem Android.

> [!NOTE]
> Należy pamiętać, że jeśli dwie zasady z różnymi poziomami ograniczeń dotyczą tego samego urządzenia lub użytkownika, w praktyce zostaną zastosowane zasady bardziej restrykcyjne.



<!--HONumber=Nov16_HO1-->


