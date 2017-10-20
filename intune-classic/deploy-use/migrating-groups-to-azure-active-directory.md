---
title: "Migracja do grup usługi Azure Active Directory"
description: "Przebieg procesu migracji grup z usługi Intune do usługi Azure AD"
keywords: 
author: arob98
ms.author: angrobe
manager: angerobe
ms.date: 12/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 03b69afa-3548-4033-9039-191528f3fd99
ROBOTS: NOINDEX,NOFOLLOW
ms.custom: intune-classic
ms.openlocfilehash: 5eb6a72abd28b566b7588e56647787dc669706bc
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2017
---
# <a name="a-new-way-of-using-groups-in-intune"></a>Nowy sposób korzystania z grup w usłudze Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Wysłuchaliśmy opinii użytkowników i wprowadzamy pewne zmiany sposobu pracy z grupami w usłudze Microsoft Intune.
Obecnie migrujemy wszystkie grupy usługi Intune naszych klientów do grup zabezpieczeń usługi Azure Active Directory.

Korzyścią dla użytkownika będzie teraz możliwość pracy w tym samym środowisku obsługi grup we wszystkich aplikacjach rozwiązania Enterprise Mobility + Security i usługi Azure AD. Ponadto będzie można rozszerzać tę nową funkcjonalność za pomocą interfejsu API programu Graph i PowerShell.

Grupy zabezpieczeń usługi Azure AD obsługują wszystkie typy wdrożeń usługi Intune dla użytkowników i urządzeń. Ponadto można używać grup dynamicznych usługi Azure AD, które są automatycznie aktualizowane na podstawie podanych atrybutów. Można na przykład utworzyć grupę urządzeń z systemem iOS 9. Każde nowo rejestrowane urządzenie z systemem iOS 9 jest automatycznie dodawane do grupy dynamicznej.

## <a name="when-is-this-happening"></a>Kiedy te zmiany zostaną wprowadzone?

Proces migracji obecnie trwa. Przed przeprowadzeniem migracji Twoich danych otrzymasz odpowiednie powiadomienie.
Jeśli migracja Twoich danych już się odbyła, po podjęciu próby uzyskania dostępu do grup z poziomu klasycznej konsoli usługi Intune zobaczysz komunikat podobny do następującego:

![Komunikat oznaczający, że migracja grup została już przeprowadzona.](http://i.imgur.com/72KRaXj.png)

## <a name="what-wont-be-available"></a>Które elementy nie będą dostępne?

Niektóre istniejące możliwości grup w usłudze Intune nie są dostępne w usłudze Azure AD:

- Grupy usługi Intune **Użytkownicy niezgrupowani** i **Urządzenia niezgrupowane** nie będą migrowane.
- Opcja **Wyklucz określonych członków** dla grupy, która jest obecnie dostępna w konsoli usługi Intune, nie istnieje w witrynie Azure Portal. W celu replikowania tego zachowania można jednak użyć grupy zabezpieczeń usługi Azure AD z regułami zaawansowanymi. Będzie można na przykład utworzyć zaawansowaną regułę, która dołącza wszystkie osoby w Twoim dziale sprzedaży do grupy zabezpieczeń, ale wyklucza te osoby, których stanowiska zawierają wyraz „Asystent”, przy użyciu tej zaawansowanej reguły: `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`.
- Grupa **Wszystkie urządzenia zarządzane za pośrednictwem programu Exchange ActiveSync** wbudowana w konsoli usługi Intune nie będzie migrowana do usługi Azure AD. Można jednak nadal uzyskiwać dostęp do informacji o zarządzanych urządzeniach EAS w witrynie Azure Portal.
- W klasycznej konsoli usługi Intune nie będzie można filtrować raportów według grup.
<!--- - Custom group targeting of notification rules will not be available. ROB I took this out as I couldn't replicate the behavior. --->

## <a name="how-to-get-ready"></a>Jak się przygotować

- Zapoznaj się z poniższymi tematami dotyczącymi usługi Azure AD, aby dowiedzieć się więcej o grupach zabezpieczeń usługi Azure AD i sposobie ich działania:
    -  [Zarządzanie dostępem do zasobów przy użyciu grup usługi Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-manage-groups/).
    -  [Zarządzanie grupami w usłudze Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/).
    -  [Tworzenie zaawansowanych reguł przy użyciu atrybutów](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).
- Rozważ usunięcie przed migracją wszystkich grup usługi Intune, których już nie używasz.
-  Upewnij się, że wszyscy administratorzy, którzy muszą tworzyć grupy, zostali dodani do roli usługi Azure AD **Administrator usługi Intune**. Zauważ, że rola administratora usługi Azure AD nie ma uprawnienia **Zarządzanie grupą**.
-  Jeśli używasz grup z opcją **Wyklucz określonych członków**, zastanów się, czy możesz ponownie zaprojektować te grupy, tak aby wykluczenia nie były konieczne, lub czy możesz użyć reguł zaawansowanych w zapytaniu usługi Azure AD, aby osiągnąć ten sam efekt.


## <a name="what-happens-to-intune-groups"></a>Co się dzieje z grupami usługi Intune?

| Grupy w usłudze Intune|Grupa w usłudze Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Statyczna grupa użytkowników|Statyczna grupa zabezpieczeń usługi Azure AD|
|Dynamiczna grupa użytkowników|statycznymi grupami zabezpieczeń usługi Azure AD z hierarchią grup zabezpieczeń usługi Azure AD|
|Statyczna grupa urządzeń|Statyczna grupa zabezpieczeń usługi Azure AD|
|Dynamiczna grupa urządzeń|Dynamiczna grupa zabezpieczeń usługi Azure AD|
|Grupa z warunkiem dołączenia|Statyczna grupa zabezpieczeń usługi Azure AD zawierająca wszystkie statyczne lub dynamiczne elementy członkowskie powiązane z warunkiem uwzględnienia w usłudze Intune.|
|Grupa z warunkiem wykluczenia|Niemigrowana|
|Grupy wbudowane, **Wszyscy użytkownicy**, **Użytkownicy niezgrupowani**, **Wszystkie urządzenia**, **Urządzenia niezgrupowane**, **Wszystkie komputery**, **Wszystkie urządzenia przenośne**, **Wszystkie urządzenia zarządzane przez system MDM** i **Wszystkie urządzenia zarządzane przez program EAS**|grupami zabezpieczeń usługi Azure AD.|

W usłudze Intune wszystkie grupy muszą mieć grupę nadrzędną. Grupy mogą zawierać tylko elementy członkowskie ze swojej grupy nadrzędnej. W usłudze Azure AD grupy podrzędne mogą zawierać elementy członkowskie, których nie ma grupa nadrzędna.

Atrybuty to właściwości urządzeń, za pomocą których można definiować grupy. W tej tabeli opisano, jak te kryteria zostaną zmigrowane do grup zabezpieczeń usługi Azure AD.

| Atrybut w usłudze Intune|Atrybut w usłudze Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Atrybut jednostki organizacyjnej (OU) grup urządzeń|Atrybut OU grup dynamicznych.|
|Atrybut nazwy domeny grup urządzeń|Atrybut nazwy domeny grup dynamicznych.|
|Grupa zabezpieczeń jako atrybut grup użytkowników|Grupy nie mogą być atrybutami w zapytaniach dynamicznych usługi Azure AD. Grupy dynamiczne mogą zawierać tylko atrybuty określone dla użytkowników lub urządzeń.|
|Atrybut menedżera grup użytkowników|Zaawansowana reguła atrybutu *menedżer* w grupach dynamicznych|
|Wszyscy użytkownicy z nadrzędnej grupy użytkowników|Grupa statyczna z tą grupą jako elementem członkowskim|
|Wszystkie urządzenia przenośne z nadrzędnej grupy urządzeń|Grupa statyczna z tą grupą jako elementem członkowskim|
|Wszystkie urządzenia przenośne zarządzane przez usługę Intune|Atrybut typu zarządzania z wartością „MDM” dla grupy dynamicznej|
|Grupy zagnieżdżone w grupach statycznych |Grupy zagnieżdżone w grupach statycznych|
|Grupy zagnieżdżone w grupach dynamicznych|Grupa dynamiczna z jednym poziomem zagnieżdżenia|

## <a name="what-happens-to-policies-and-apps-youve-already-deployed"></a>Co się dzieje z już wdrożonymi już zasadami i aplikacjami?

Zasady i aplikacje można nadal wdrażać do grup, tak jak wcześniej. Tymi grupami można będzie jednak teraz zarządzać w witrynie Azure Portal (zamiast przy użyciu klasycznej konsoli usługi Intune).
 
