---
title: "Używanie grup do zarządzania użytkownikami i urządzeniami | Microsoft Intune"
description: "Utwórz grupy i zarządzaj nimi za pomocą obszaru roboczego Grupy."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 06/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb9b01ce-9b9b-4c2a-bf99-3879c0bdaba5
ms.reviewer: lpatha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 300df17fd5844589a1e81552d2d590aee5615897
ms.openlocfilehash: 53a7bda5dd5adcac512c413c7069723ae638f279


---

# Tworzenie grup do zarządzania użytkownikami i urządzeniami w usłudze Microsoft Intune

Aby utworzyć grupy i zarządzać nimi, użyj obszaru roboczego **Grupy** w konsoli administracyjnej usługi Microsoft Intune. Strona **Przegląd grup** zawiera podsumowania stanów, które ułatwiają zidentyfikowanie i ustalenie priorytetów dla problemów wymagających uwagi, które dotyczą następujących zagadnień:

-   Alerty
-   Aktualizacje oprogramowania
-   Program Endpoint Protection
-   Zasady
-   Zarządzanie oprogramowaniem

Ponadto wyświetlana jest hierarchia grup z podsumowaniami stanów ułatwiającymi identyfikację i rozwiązywanie problemów dotyczących elementów członkowskich wybranej grupy.


> [!TIP]
> Podczas tworzenia grup należy wziąć pod uwagę, jak będą stosowane zasady. Na przykład są zasady właściwe dla systemów operacyjnych urządzeń i zasady właściwe dla różnych ról w organizacji lub jednostek organizacyjnych zdefiniowanych już w usłudze Active Directory. Niektórzy uważają, że warto mieć grupy urządzeń właściwe dla systemu iOS, Android i Windows, a także grupy użytkowników dla poszczególnych ról organizacyjnych.
>
> Prawdopodobnie należy utworzyć zasady domyślne odnoszące się do wszystkich grup i urządzeń w celu ustalenia podstawowych wymagań zgodności w firmie. Następnie można utworzyć bardziej szczegółowe zasady dla najszerszych kategorii użytkowników i urządzeń, na przykład zasady poczty e-mail dla poszczególnych systemów operacyjnych urządzeń.
>
> Należy nadawać zasadom odpowiednie nazwy, aby można je było później łatwo rozpoznać. Na przykład, właściwą opisową nazwą zasad może być **Zasady poczty e-mail WP dla całej firmy**.
>
> Za każdym razem, gdy tworzy się zasady ograniczające, należy o nich poinformować użytkowników, więc po utworzeniu bardziej ogólnych grup i zasad należy zwrócić uwagę na sposób tworzenia mniejszych grup, aby ograniczyć zbędny przepływ informacji.


## Tworzenie grupy urządzeń

1.  W konsoli administracyjnej usługi Intune wybierz pozycje **Grupy** &gt; **Przegląd** &gt; **Utwórz grupę**.

2.  Podaj nazwę i opcjonalny opis grupy oraz wybierz grupę urządzeń jako grupę nadrzędną. Wybierz pozycję **Next** (Dalej).

3.  Na stronie **Zdefiniuj kryteria członkostwa** wybierz typ urządzeń, które będą znajdować się w grupie. Dodatkowe opcje umożliwiające skonfigurowanie grupy są dostępne w zależności od typu wybranych urządzeń:

    -   **Komputer:** określ, czy mają zostać dołączone wszystkie elementy członkowskie grupy nadrzędnej, a także podaj jednostki organizacyjne (OU) i domeny, które mają zostać dołączone lub wykluczone. Informacje o jednostce organizacyjnej i domenie komputera są uzyskiwane ze spisu.

    -   **Urządzenia przenośne:** określ, czy mają zostać dołączone tylko urządzenia przenośne zarządzane przez usługę Intune, tylko urządzenia zarządzane przez program Exchange ActiveSync, czy oba typy urządzeń.

    -   **Wszystkie urządzenia:** ta opcja powoduje dołączenie wszystkich urządzeń bez wykluczeń na podstawie kryteriów.

4.  Na stronie **Zdefiniuj członkostwo bezpośrednie** dołącz lub wyklucz poszczególne urządzenia, klikając polecenie **Przeglądaj**. Jeśli za pomocą tej opcji wybierzesz urządzenia, które nie znajdują się w podanej grupie nadrzędnej, zostaną one automatycznie dodane do grupy nadrzędnej.


5.  Na stronie **Podsumowanie** przejrzyj akcje, które zostaną wykonane. Wybierz pozycję **Zakończ**.

Nowo utworzona grupa będzie umieszczona na liście **Grupy** w obszarze roboczym **Grupy** w obszarze grupy nadrzędnej. W tym miejscu możesz także edytować lub usunąć grupę.

## Tworzenie grupy użytkowników

1.  W konsoli administracyjnej usługi Intune wybierz pozycje **Grupy** &gt; **Przegląd** &gt; **Utwórz grupę**.

2.  Podaj nazwę i opcjonalny opis grupy oraz wybierz grupę użytkowników jako grupę nadrzędną. Wybierz pozycję **Next** (Dalej).

3.  Na stronie **Zdefiniuj kryteria członkostwa** określ, czy mają zostać dołączeni wszyscy członkowie grupy nadrzędnej, czy też chcesz rozpocząć od pustej grupy.  Możesz dołączyć lub wykluczyć członków na podstawie **grup zabezpieczeń** użytkowników skonfigurowanych ręcznie w [centrum administracyjnym usługi Office 365](http://go.microsoft.com/fwlink/?LinkId=698854) lub synchronizowanych z lokalnej usługi Active Directory. Jeśli nastąpi zmiana członkostwa grupy zabezpieczeń, członkostwo grup użytkowników opartych na tej grupie zabezpieczeń może także ulec zmianie.

    > [!IMPORTANT]
    > Obecnie w przypadku grupy zawierającej członków z określonych grup zabezpieczeń lub grup kierowników oraz wykluczenia członków z określonych grup początkowo dołączeni członkowie zostaną usunięci. Przed utworzeniem grupy zawierającej dołączonych i wykluczonych członków zalecamy utworzenie grupy nadrzędnej z dołączonymi członkami, a następnie utworzenie grupy podrzędnej zawierającej wykluczonych członków. Grupy podrzędnej będzie można używać na potrzeby zasad usługi Intune, profili i dystrybucji aplikacji.

    > [!NOTE]
    > W Portalu zarządzania Azure można utworzyć grupę kierownika, któremu podlegają użytkownicy. Jest to grupa dynamiczna, której członkowie zmieniają się wraz z dodawaniem lub usuwaniem pracowników w zespole danego kierownika w usłudze Azure Active Directory. Procedurę tworzenia grupy kierownika na platformie Azure opisano w artykule [Using attributes to create advanced rules](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/) (Tworzenie zaawansowanych reguł przy użyciu atrybutów) w sekcji **To configure a group as a “Manager” group** (Aby skonfigurować grupę jako grupę kierownika).


4.  Na stronie **Zdefiniuj członkostwo bezpośrednie** dołącz lub wyklucz poszczególnych użytkowników, klikając polecenie **Przeglądaj**. Jeśli za pomocą tej opcji wybierzesz użytkowników, którzy nie znajdują się w podanej grupie nadrzędnej, zostaną oni automatycznie dodani do grupy nadrzędnej. W dolnej części okna dialogowego **Wybieranie członków** znajduje się opcja ręcznego dodawania użytkownika. Jest to przydatne, jeśli chcesz dodać użytkownika, który nie ma jeszcze zarejestrowanego urządzenia.


5.  Na stronie **Podsumowanie** przejrzyj akcje, które zostaną wykonane. Wybierz pozycję **Zakończ**.

Nowo utworzona grupa będzie umieszczona na liście **Grupy** w obszarze roboczym **Grupy** w obszarze grupy nadrzędnej. W tym miejscu możesz także edytować lub usunąć grupę.

> [!TIP]
> Grupy zabezpieczeń są doskonałą pomocą podczas wypełniania grup użytkowników. Grupy zabezpieczeń określają, kto ma dostęp do określonych zasobów, dlatego można je łatwo przekształcić w grupy użytkowników usługi Intune. Wszystkie grupy zabezpieczeń, które są synchronizowane z usługi Active Directory do usługi Azure Active Directory albo które są tworzone bezpośrednio w usłudze Azure Active Directory za pośrednictwem centrum administracyjnego usługi Office 365 lub portalu administracyjnego platformy Azure, są dostępne i umożliwiają tworzenie grup użytkowników w usłudze Intune.

## Dostosowywanie widoków do ról administratora
Korzystając z filtrowanych widoków grup, można dostosowywać widoki dostępne dla administratorów na podstawie ich ról oraz ograniczać grupy, którymi mogą zarządzać poszczególni administratorzy IT. Może to być przydatne w następujących przypadkach:

-   Administratorzy IT powinni mieć możliwość wdrażania elementów tylko dla konkretnych użytkowników i urządzeń.

-   Poszczególni administratorzy IT powinni widzieć tylko istotne dla nich grupy.

Filtrowane widoki grup można skonfigurować dla administratorów usługi za pomocą konsoli administracyjnej usługi Intune. Aby uzyskać szczegółowe informacje, zobacz [Co należy wiedzieć przed rozpoczęciem korzystania z usługi Microsoft Intune](/intune/get-started/what-to-know-before-you-start-microsoft-intune).

Gdy filtrowane widoki grup zostaną skonfigurowane dla administratora usługi, administrator:

-   może wyświetlać i wybierać tylko określone grupy podczas wdrażania oprogramowania lub w przypadku używania raportów,

-   nie otrzymuje informacji o stanie na następujących stronach konsoli administracyjnej:

    -   **Omówienie systemu**

    -   **Przegląd grup**

    -   **Przegląd programu Endpoint Protection**

    -   **Przegląd alertów**

    -   **Przegląd oprogramowania**

    -   **Przegląd zasad**

### Konfigurowanie filtrowanych widoków grup

1.  W konsoli administracyjnej usługi Intune wybierz pozycje **Administracja** &gt; **Zarządzanie administratorami** &gt; **Administratorzy usługi**.

2.  Wybierz administratora usługi, dla którego grupy mają być filtrowane, a następnie kliknij polecenie **Zarządzaj grupami**.

3.  W oknie dialogowym **Wybierz grupy, które będą widoczne dla administratora usługi** dodaj grupy, do których ma mieć dostęp wybrany administrator usługi, a następnie kliknij przycisk **OK**.

Po skonfigurowaniu filtrowanych widoków grup administrator IT będzie mógł wyświetlać i wybierać tylko określone grupy.

## Zarządzanie grupami
Po utworzeniu grup można nimi zarządzać odpowiednio do potrzeb organizacji.

Można edytować grupę, zmieniając jej nazwę, opis i należących do niej członków.

Grupę, która nie spełnia już wymagań organizacji, można usunąć. Usunięcie grupy nie powoduje usunięcia użytkowników, którzy do niej należą.

## Następne kroki

### Sprawdzanie projektu
Po skonfigurowaniu grup i zasad sprawdź praktyczne efekty projektu, przeglądając informacje **Wartość zamierzona** i **Stan**.

1. Wybierz dowolne urządzenie z grupy urządzeń i przeglądaj kategorie informacji w górnej części ekranu.
2. Wybierz pozycję **Zasady** . Zobaczysz ekran podobny do tego zrzutu ekranu przedstawiającego ustawienia zasad dotyczących urządzeń z systemem Android.

![Przykład zasad ustawień systemu iOS](../media/Intune-Device-Policy-v.2.jpg)

Wszystkie zasady mają parametry **Wartość zamierzona** i **Stan**. Wartość zamierzona to wartość, która miała być osiągnięta w momencie przypisywania zasad. Stanem jest to, co faktycznie się uzyskuje, gdy weźmie się pod uwagę wszystkie zasady dotyczące urządzenia, a także ograniczenia i wymagania sprzętowe oraz system operacyjny.  Zrzut ekranu zawiera dwa proste przykłady:

-   Ustawienie **Zezwalaj na proste hasła** ma wartość **Tak**, jak pokazano w kolumnie **Wartość zamierzona**, ale jego ustawienie **Stan** ma wartość **Nie dotyczy**. Dzieje się tak, gdyż proste hasła nie są obsługiwane w przypadku urządzeń z systemem Android.

-   Podobnie, rozwinięty element zasad **Ustawienia poczty e-mail dla urządzeń z systemem iOS** nie ma zastosowania do tego urządzenia, ponieważ jest to urządzenie z systemem Android.

> [!NOTE]
> Należy pamiętać, że jeśli dwie zasady z różnymi poziomami ograniczeń dotyczą tego samego urządzenia lub użytkownika, w praktyce zostaną zastosowane zasady bardziej restrykcyjne.



<!--HONumber=Jul16_HO4-->


