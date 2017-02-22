---
title: Wprowadzenie do grup w wersji zapoznawczej portalu Intune Azure | Dokumentacja firmy Microsoft
description: "Dowiedz się o nowych funkcjach grup w wersji zapoznawczej portalu Intune Azure"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angerobe
ms.date: 01/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 323f384d-8a76-4adc-999b-e508d641bfa1
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: 27a9c9d8269b302fa9735972056d38e7919f42b5


---

# <a name="get-started-with-groups"></a>Wprowadzenie do grup

[!INCLUDE[azure preview](../includes/azure_preview.md)]

Wysłuchaliśmy opinii użytkowników i wprowadziliśmy pewne zmiany sposobu pracy z grupami w usłudze Microsoft Intune.
Jeśli korzystasz z usługi Intune z witryny Azure Portal, Twoje grupy z usługi Intune zostały poddane migracji do grup zabezpieczeń usługi Azure Active Directory.

Korzyścią dla użytkownika będzie teraz możliwość pracy w tym samym środowisku obsługi grup we wszystkich aplikacjach rozwiązania Enterprise Mobility + Security i usługi Azure AD. Ponadto będzie można rozszerzać tę nową funkcjonalność za pomocą interfejsu API programu Graph i PowerShell.

Grupy zabezpieczeń usługi Azure AD obsługują wszystkie typy wdrożeń usługi Intune dla użytkowników i urządzeń. Ponadto można używać grup dynamicznych usługi Azure AD, które są automatycznie aktualizowane na podstawie podanych atrybutów. Można na przykład utworzyć grupę urządzeń z systemem iOS 9. Każde nowo rejestrowane urządzenie z systemem iOS 9 jest automatycznie dodawane do grupy dynamicznej.

## <a name="what-is-not-available"></a>Co jest niedostępne?

Niektóre funkcje, które były dostępne w przypadku grup Intune, są niedostępne w usłudze Azure AD:

- Nie są już dostępne grupy usługi Intune **Użytkownicy niezgrupowani** i **Urządzenia niezgrupowane**.
- Opcja **Wyklucz określonych członków** dla grupy nie istnieje w witrynie Azure Portal. W celu replikowania tego zachowania można jednak użyć grupy zabezpieczeń usługi Azure AD z regułami zaawansowanymi. Będzie można na przykład utworzyć zaawansowaną regułę, która dołącza wszystkie osoby w Twoim dziale sprzedaży do grupy zabezpieczeń, ale wyklucza te osoby, których stanowiska zawierają wyraz „Asystent”, przy użyciu tej zaawansowanej reguły: `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`.
- Grupa **Wszystkie urządzenia zarządzane za pośrednictwem programu Exchange ActiveSync** wbudowana w konsolę usługi Intune nie została poddana migracji do usługi Azure AD. Można jednak nadal uzyskiwać dostęp do informacji o zarządzanych urządzeniach EAS w witrynie Azure Portal.


## <a name="how-to-get-started"></a>Wprowadzenie

- Zapoznaj się z poniższymi tematami dotyczącymi usługi Azure AD, aby dowiedzieć się więcej o grupach zabezpieczeń usługi Azure AD i sposobie ich działania:
    -  [Zarządzanie dostępem do zasobów przy użyciu grup usługi Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/).
    -  [Zarządzanie grupami w usłudze Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/).
    -  [Tworzenie zaawansowanych reguł przy użyciu atrybutów](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).
-  Upewnij się, że wszyscy administratorzy, którzy muszą tworzyć grupy, zostali dodani do roli usługi Azure AD **Administrator usługi Intune**. Zauważ, że rola administratora usługi Azure AD nie ma uprawnienia **Zarządzanie grupą**.
-  Jeśli w przeszłości zdarzyło Ci się używać grup z opcją **Wyklucz określonych członków**, zastanów się, czy możesz ponownie zaprojektować te grupy tak, aby wykluczenia nie były konieczne, lub użyć reguł zaawansowanych w zapytaniu usługi Azure AD, aby osiągnąć ten sam efekt.


## <a name="what-happened-to-intune-groups"></a>Co stało się z grupami usługi Intune?

| Grupy w usłudze Intune|Grupa w usłudze Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Statyczna grupa użytkowników|Statyczna grupa zabezpieczeń usługi Azure AD|
|Dynamiczna grupa użytkowników|statycznymi grupami zabezpieczeń usługi Azure AD z hierarchią grup zabezpieczeń usługi Azure AD|
|Statyczna grupa urządzeń|Statyczna grupa zabezpieczeń usługi Azure AD|
|Dynamiczna grupa urządzeń|Dynamiczna grupa zabezpieczeń usługi Azure AD|
|Grupa z warunkiem dołączenia|Statyczna grupa zabezpieczeń usługi Azure AD zawierająca statyczne lub dynamiczne elementy członkowskie powiązane z warunkiem uwzględnienia w usłudze Intune|
|Grupa z warunkiem wykluczenia|Niemigrowana|
|Grupy wbudowane, **Wszyscy użytkownicy**, **Użytkownicy niezgrupowani**, **Wszystkie urządzenia**, **Urządzenia niezgrupowane**, **Wszystkie komputery**, **Wszystkie urządzenia przenośne**, **Wszystkie urządzenia zarządzane przez system MDM** i **Wszystkie urządzenia zarządzane przez program EAS**|Grupy zabezpieczeń usługi Azure AD|

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

## <a name="what-happens-to-policies-and-apps-you-previously-deployed"></a>Co się dzieje z wdrożonymi wcześniej zasadami i aplikacjami?

Zasady i aplikacje można nadal wdrażać do grup, tak jak wcześniej. Tymi grupami można będzie jednak teraz zarządzać w witrynie Azure Portal (zamiast przy użyciu klasycznej konsoli usługi Intune).



<!--HONumber=Feb17_HO1-->


