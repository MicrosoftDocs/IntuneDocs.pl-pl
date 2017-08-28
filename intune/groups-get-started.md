---
title: "Klasyczne grupy usługi Intune w witrynie Azure Portal"
titleSuffix: Intune on Azure
description: "Poznaj nowe funkcje grup w portalu usługi Intune Azure"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angerobe
ms.date: 01/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 323f384d-8a76-4adc-999b-e508d641bfa1
ms.custom: intune-azure
ms.openlocfilehash: c51c3102cc78cf095e27da4ff199cb3fb5ae14a6
ms.sourcegitcommit: 45204e0fb8cb4cce449e65f2f1d7bb6f6ac4ccf5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2017
---
# <a name="intune-classic-groups-in-the-azure-portal"></a>Klasyczne grupy usługi Intune w witrynie Azure Portal

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Wysłuchaliśmy opinii użytkowników i wprowadziliśmy pewne zmiany sposobu pracy z grupami w usłudze Microsoft Intune.
Jeśli korzystasz z usługi Intune z witryny Azure Portal, Twoje grupy z usługi Intune zostały poddane migracji do grup zabezpieczeń usługi Azure Active Directory.

Korzyścią dla użytkownika jest teraz możliwość pracy w tym samym środowisku obsługi grup we wszystkich aplikacjach rozwiązania Enterprise Mobility + Security i usługi Azure AD. Ponadto będzie można rozszerzać tę nową funkcjonalność za pomocą interfejsu API programu Graph i programu PowerShell.

Grupy zabezpieczeń usługi Azure AD obsługują wszystkie typy wdrożeń usługi Intune dla użytkowników i urządzeń. Ponadto można używać grup dynamicznych usługi Azure AD, które są automatycznie aktualizowane na podstawie podanych atrybutów. Można na przykład utworzyć grupę urządzeń z systemem iOS 9. Zawsze, gdy rejestrowane jest urządzenie z systemem iOS 9, pojawia się ono automatycznie w grupie dynamicznej.

## <a name="what-is-not-available"></a>Co jest niedostępne?

Niektóre funkcje, które były dostępne w przypadku grup Intune, są niedostępne w usłudze Azure AD:

- Nie są już dostępne grupy usługi Intune **Użytkownicy niezgrupowani** i **Urządzenia niezgrupowane**.
- Opcja **Wyklucz określonych członków** dla grupy nie istnieje w witrynie Azure Portal. W celu replikowania tego zachowania można jednak użyć grupy zabezpieczeń usługi Azure AD z regułami zaawansowanymi. Będzie można na przykład utworzyć następującą zaawansowaną regułę, która dołącza wszystkie osoby w Twoim dziale sprzedaży do grupy zabezpieczeń, ale wyklucza te grupy, których tytuły zawierają wyraz „Assistant”:

  `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`.
- Grupa **Wszystkie urządzenia zarządzane za pośrednictwem programu Exchange ActiveSync** wbudowana w konsolę usługi Intune nie została poddana migracji do usługi Azure AD. Można jednak nadal uzyskiwać dostęp do informacji o zarządzanych urządzeniach EAS w witrynie Azure Portal.

## <a name="how-to-get-started"></a>Wprowadzenie

- Zapoznaj się z poniższymi tematami, aby dowiedzieć się więcej o grupach zabezpieczeń usługi Azure AD i sposobie ich działania:
    -  [Zarządzanie dostępem do zasobów przy użyciu grup usługi Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-manage-groups/).
    -  [Zarządzanie grupami w usłudze Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/).
    -  [Tworzenie zaawansowanych reguł przy użyciu atrybutów](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).
-  Upewnij się, że administratorzy, którzy muszą tworzyć grupy, zostali dodani do roli usługi Azure AD **Administrator usługi Intune**. Rola administratora usługi Azure AD nie ma uprawnienia **Zarządzanie grupą**.
-  Jeśli w grupach usługi Intune użyto opcji **Wyklucz określone elementy członkowskie**, zdecyduj, czy możesz przeprojektować te grupy bez wykluczeń, czy potrzebujesz użyć reguł zaawansowanych, aby spełnić potrzeby biznesowe.


## <a name="what-happened-to-intune-groups"></a>Co stało się z grupami usługi Intune?
Podczas migrowania grup z portalu klasycznego Intune do usługi Intune w witrynie Azure Portal stosowane są następujące reguły:

| Grupy w klasycznym portalu usługi Intune|Grupy w usłudze Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Statyczna grupa użytkowników|Statyczna grupa zabezpieczeń usługi Azure AD|
|Dynamiczna grupa użytkowników|statycznymi grupami zabezpieczeń usługi Azure AD z hierarchią grup zabezpieczeń usługi Azure AD|
|Statyczna grupa urządzeń|Statyczna grupa zabezpieczeń usługi Azure AD|
|Dynamiczna grupa urządzeń|Dynamiczna grupa zabezpieczeń usługi Azure AD|
|Grupa z warunkiem dołączenia|Statyczna grupa zabezpieczeń usługi Azure AD zawierająca statyczne lub dynamiczne elementy członkowskie powiązane z warunkiem uwzględnienia w usłudze Intune|
|Grupa z warunkiem wykluczenia|Niemigrowana|
|Grupy wbudowane:<br>- **Wszyscy użytkownicy**<br>- **Użytkownicy niezgrupowani**<br>- **Wszystkie urządzenia**<br>- **Urządzenia niezgrupowane**<br>- **Wszystkie komputery**<br>- **Wszystkie urządzenia przenośne**<br>- **Wszystkie urządzenia zarządzane w usłudze zarządzania urządzeniami przenośnymi**<br>- **Wszystkie urządzenia zarządzane w usłudze Exchange Active Sync (EAS)**|Grupy zabezpieczeń usługi Azure AD|

## <a name="group-hierarchy"></a>Hierarchia grup

W klasycznej konsoli usługi Intune wszystkie grupy mają grupę nadrzędną. Grupy mogą zawierać tylko elementy członkowskie ze swojej grupy nadrzędnej. W usłudze Azure AD grupy podrzędne mogą zawierać elementy członkowskie, których nie ma w grupie nadrzędnej.

## <a name="group-attributes"></a>Atrybuty grupy
Atrybuty to właściwości urządzeń, za pomocą których można definiować grupy. W tej tabeli opisano, jak te kryteria są migrowane do grup zabezpieczeń usługi Azure AD.

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

Zasady i aplikacje można nadal wdrażać do grup, tak jak wcześniej. Tymi grupami można jednak teraz zarządzać w witrynie Azure Portal (zamiast przy użyciu klasycznej konsoli usługi Intune).
