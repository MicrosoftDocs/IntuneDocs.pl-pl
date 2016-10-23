---
title: "Migracja do grup usługi Azure Active Directory | Microsoft Intune"
description: "Przebieg procesu migracji grup z usługi Intune do usługi Azure AD"
keywords: 
author: nbigman
manager: angerobe
ms.date: 10/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 03b69afa-3548-4033-9039-191528f3fd99
translationtype: Human Translation
ms.sourcegitcommit: d92c9ffe42b36770a32c28941de3c402aec9dd68
ms.openlocfilehash: 08bcc258f64e6385ae6fa648ddb8f2b5fe68942e


---

## Nowe środowisko administratora dla grup
    
Na podstawie opinii użytkowników, aby istniało jedno środowisko grupowania i kierowania w pakiecie Enterprise Mobility & Security, konwertujemy grupy usługi Intune na grupy zabezpieczeń oparte na usłudze Azure Active Directory. Spowoduje to ujednolicenie zarządzania grupami w usłudze Intune i usłudze Azure Active Directory (Azure AD). Nowe środowisko zlikwiduje konieczność duplikowania grup między usługami i zapewni możliwość rozszerzenia przy użyciu programów PowerShell i Graph. 

### W jaki sposób i kiedy zostanie przeprowadzona migracja do nowego środowiska grup?
Bieżący klienci będą migrowani stopniowo, począwszy najwcześniej od grudnia 2016 roku. Przed migracją grup otrzymasz powiadomienie. Jeśli masz jakiekolwiek pytania dotyczące migracji, skontaktuj się z naszym zespołem migracji, wysyłając wiadomość e-mail na adres [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### Jakie nowe funkcje będą dla mnie dostępne?
Poniżej znajdują się nowe funkcje, które zostaną wprowadzone: 
 
-    Grupy zabezpieczeń usługi Azure AD będą obsługiwane w usłudze Intune dla wszystkich typów wdrożeń. 
-    Grupy zabezpieczeń usługi Azure AD będą obsługiwać grupowanie urządzeń wraz z użytkownikami.
-    Grupy zabezpieczeń usługi Azure AD będą obsługiwać grupy dynamiczne z atrybutami urządzeń usługi Intune. Na przykład możliwe będzie dynamiczne grupowanie urządzeń na podstawie platformy, takiej jak iOS. Dzięki temu podczas rejestrowania nowego urządzenia z systemem iOS w organizacji zostanie ono automatycznie dodane do dynamicznej grupy urządzeń z systemem iOS.
-    Współużytkowane środowiska pracy administratora na potrzeby zarządzania grupami w usłudze Azure AD i usłudze Intune.
- *Rola administratora usługi Intune* zostanie dodana do usługi Azure AD w celu umożliwienia administratorom w usłudze Intune wykonywania zadań zarządzania grupami w usłudze Azure AD.

 
### Jakie funkcje usługi Intune nie będą dostępne?
Chociaż środowisko grupy zostanie ulepszone, po migracji w usłudze Intune nie będą dostępne pewne funkcje.

#### Funkcja zarządzania grupami

-   Nie będzie możliwe wykluczenie członków ani grup podczas tworzenia nowej grupy. Grupy dynamiczne usługi Azure AD będą jednak umożliwiały tworzenie zaawansowanych reguł wykluczania elementów członkowskich na podstawie kryteriów przy użyciu atrybutów. Będzie można na przykład utworzyć następującą zaawansowaną regułę, która dołącza wszystkie osoby w Twoim dziale sprzedaży do grupy zabezpieczeń, ale wyklucza te osoby, których stanowiska zawierają wyraz „Asystent”: `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`. Aby uzyskać więcej informacji, zobacz [Tworzenie zaawansowanych reguł przy użyciu atrybutów](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).
-   Grupy **Użytkownicy niezgrupowani** i **Urządzenia niezgrupowane** nie będą obsługiwane. Te grupy nie będą migrowane.

#### Funkcja zależna od grupy

-   Rola administratora usługi nie będzie miała uprawnienia do **zarządzania grupami**.
-   Nie będzie możliwe grupowanie urządzeń programu Exchange ActiveSync.  Twoja grupa **Wszystkie urządzenia zarządzane przez program EAS** zostanie przekonwertowana z grupy na widok raportu.
-  Przestawianie z grupami w raportach nie będzie dostępne.
-  Określanie grup niestandardowych jako obiektów docelowych reguł powiadomień nie będzie dostępne.

### Co należy zrobić, aby przygotować się do tej zmiany?
 Mamy następujące zalecenia, które ułatwią to przejście:
 
- Wyczyść wszystkie niepożądane lub niepotrzebne grupy Intune przed migracją.
- Oceń swoje użycie wykluczeń w grupach i zastanów się, jak przeprojektować swoje grupy tak, aby nie było konieczne używanie wykluczeń lub aby można było zrealizować ten sam cel za pomocą zaawansowanych reguł.
-  Jeśli istnieją administratorzy, którzy nie mają uprawnień do tworzenia grup w usłudze Azure AD, skontaktuj się z administratorem usługi Azure AD, aby dodać ich do roli **administratora usługi Intune** w usłudze Azure AD.

Możesz także uzyskać więcej informacji o grupach zabezpieczeń usługi Azure AD:
-  Aby zapoznać się z omówieniem, przeczytaj temat [Zarządzanie dostępem do zasobów przy użyciu grup usługi Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/).
-  Aby uzyskać informacje dotyczące tworzenia grup usługi Azure AD i zarządzania nimi, zobacz [Zarządzanie grupami w usłudze Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/).
-  Aby uzyskać więcej informacji o zaawansowanych regułach dla grup zabezpieczeń, zobacz [Tworzenie zaawansowanych reguł przy użyciu atrybutów](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).

> [!NOTE]
Można zauważyć, że w dokumentacji grup zabezpieczeń usługi Azure AD nie opisano tworzenia grup urządzeń. Te funkcje zostaną włączone w usłudze Azure AD przed rozpoczęciem procesu migracji grup usługi Intune.

## Szczegóły dotyczące migracji
Poniżej przedstawiono szczegółowe informacje dotyczące procesu migracji Twoich grup usługi Intune do grup zabezpieczeń usługi Azure AD.

### Migracja istniejących grup

| Grupa usługi Intune stanie się...|...grupą zabezpieczeń usługi Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Statyczne grupy użytkowników objęte zasadami usługi Intune|statycznymi grupami zabezpieczeń usługi Azure AD zawierającymi tych samych użytkowników|
|Dynamiczne grupy użytkowników objęte zasadami usługi Intune|statycznymi grupami zabezpieczeń usługi Azure AD z hierarchią grup zabezpieczeń usługi Azure AD|
|Statyczne grupy urządzeń objęte zasadami usługi Intune|statycznymi grupami zabezpieczeń usługi Azure AD zawierającymi urządzenia|
|Dynamiczne grupy urządzeń z atrybutami urządzeń objęte zasadami usługi Intune|dynamicznymi grupami zabezpieczeń usługi Azure AD zawierającymi atrybuty urządzeń|
|Grupa z warunkiem dołączenia|oddzielną statyczną grupą zabezpieczeń usługi Azure AD, która będzie zawierać grupę oraz wszystkie statyczne/dynamiczne elementy członkowskie dozwolone w usłudze Intune przez warunek dołączenia|
|Grupa z warunkiem wykluczenia|...nie zostanie poddana migracji. Warunki wykluczenia nie są obsługiwane w trakcie procesu tworzenia grup statycznych w usłudze Azure AD. Warunek wykluczenia może zostać użyty podczas tworzenia grupy dynamicznej w usłudze Azure AD.|
|Grupy domyślne **Wszyscy użytkownicy**, **Użytkownicy niezgrupowani**, **Wszystkie urządzenia**, **Urządzenia niezgrupowane**, **Wszystkie komputery**, **Wszystkie urządzenia przenośne**, **Wszystkie urządzenia zarządzane przez system MDM** i **Wszystkie urządzenia zarządzane przez program EAS**, których używasz w zasadach usługi Intune  |grupami zabezpieczeń usługi Azure AD. Nieużywane grupy domyślne będą musiały w razie potrzeby zostać utworzone przez klienta za pomocą grup dynamicznych.|

### Zmiany w widokach hierarchicznych
Hierarchiczny widok grup w relacji typu nadrzędny/podrzędny usługi Intune w usłudze Intune był relacją typu nadzbiór/podzbiór. Nie jest tak w przypadku usługi Azure AD. Element podrzędny może mieć elementy członkowskie, których nie miał element nadrzędny. Ponadto grupy w usłudze Azure AD mogą mieć charakter cykliczny — grupa nadrzędna może być elementem podrzędnym grupy podrzędnej.

### Konwersja atrybutów w trakcie procesu migracji
Atrybuty to właściwości urządzeń, za pomocą których można definiować grupy. W tej tabeli opisano, jak te kryteria zostaną zmigrowane do grup zabezpieczeń usługi Azure AD.

| Atrybut usługi Intune|Atrybut usługi Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Atrybut jednostki organizacyjnej (OU) grup urządzeń|Atrybut OU grup dynamicznych. Wartości atrybutów udostępniane administratorowi dotyczące poszczególnych dzierżaw przez dodawanie ich jako poszczególnych składników dzierżawy do wyświetlania.|
|Atrybut nazwy domeny grup urządzeń|Atrybut nazwy domeny grup dynamicznych. Wartości atrybutów udostępniane administratorowi dotyczące poszczególnych dzierżaw przez dodawanie ich jako poszczególnych składników dzierżawy do wyświetlania|
|Grupa zabezpieczeń jako atrybut grup użytkowników|Grupy nie mogą być atrybutami w zapytaniach dynamicznych usługi Azure AD. Grupy dynamiczne mogą zawierać tylko atrybuty określone dla użytkowników lub urządzeń.|
|Atrybut menedżera grup użytkowników|Zaawansowana reguła atrybutu *menedżer* w grupach dynamicznych|
|Wszyscy użytkownicy z nadrzędnej grupy użytkowników|Grupa statyczna z tą grupą jako elementem członkowskim|
|Wszystkie urządzenia przenośne z nadrzędnej grupy urządzeń|Grupa statyczna z tą grupą jako elementem członkowskim|
|Wszystkie urządzenia przenośne zarządzane bezpośrednio przez usługę Microsoft Intune|Atrybut typu zarządzania z wartością „MDM” dla grupy dynamicznej|
|Wszystkie urządzenia przenośne zarządzane przez program EAS|Urządzenia korzystające z programu EAS nie mogą być grupowane w usłudze Azure AD. Twoja grupa **Wszystkie urządzenia zarządzane przez program EAS** zostanie przekonwertowana z grupy na widok raportu.|
|Grupy zagnieżdżone w grupach statycznych |Grupy zagnieżdżone w grupach statycznych|
|Grupy zagnieżdżone w grupach dynamicznych|Grupa dynamiczna z jednym poziomem zagnieżdżenia|


## Migracja zasad
W trakcie procesu migracji grup będzie można nadal zarządzać zasadami w konsoli usługi Intune. W konsoli usługi Intune będzie dostępny link do konsoli zarządzania platformy Azure, w której będziesz zarządzać swoimi grupami. Twoje zasady będą nadal wdrażane względem zmigrowanych grup zabezpieczeń usługi Azure AD odpowiadających Twoim starym grupom usługi Intune.

Po zmigrowaniu wszystkich funkcji usługi Intune do portalu zarządzania platformy Azure (około pierwszego kwartału 2017 roku) będziesz zarządzać zasadami i grupami w tym portalu.

     
### Zobacz także
[Zarządzanie dostępem do zasobów przy użyciu grup usługi Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/)

[Zarządzanie grupami w usłudze Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/)

[Tworzenie zaawansowanych reguł przy użyciu atrybutów](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/)



<!--HONumber=Oct16_HO2-->


