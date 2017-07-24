---
title: "Łącznik programu Skycure w usłudze Intune"
titleSuffix: Intune on Azure
description: "Integracja łącznika programu Skycure w usłudze Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: df4ce3f6-a093-432c-ab86-7a83865e389e
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2a7c15cf695fd88ba5961611c78ecc28a29238af
ms.sourcegitcommit: 3b21f20108e2bf1cf47c141b36a7bdae609c4ec3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/10/2017
---
# <a name="skycure-mobile-threat-defense-connector"></a>Łącznik Skycure Mobile Threat Defense

Dostęp urządzeń przenośnych do zasobów firmy można kontrolować za pomocą dostępu warunkowego opartego na ocenie ryzyka przeprowadzanej przez usługę Skycure — rozwiązaniu usługi Mobile Threat Defense zintegrowanemu z usługą Microsoft Intune. Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń z uruchomioną usługą Skycure. Są to na przykład:

-   Ochrona fizyczna

-   Ochrona sieciowa

-   Ochrona aplikacji

-   Ochrona przed lukami w zabezpieczeniach

Można skonfigurować zasady dostępu warunkowego oparte na ocenie ryzyka Skycure włączone za pomocą zasad zgodności urządzeń usługi Intune, których w przypadku niezgodnego urządzenia można użyć do zezwalania na dostęp do zasobów firmy lub blokowania go w oparciu o wykryte zagrożenia.

## <a name="how-do-intune-and-skycure-help-protect-your-company-resources"></a>W jaki sposób usługa Intune i program Skycure ułatwiają ochronę zasobów firmy?

Aplikacja mobilna Skycure dla systemu Android lub iOS przechwytuje dane telemetryczne z systemu plików, stosu sieci oraz urządzenia i aplikacji (wszędzie, gdzie są dostępne), a następnie wysyła je do usługi Skycure w chmurze w celu dokonania oceny ryzyka dotyczącego urządzenia pod kątem zagrożeń mobilnych.

Zasady zgodności urządzeń w usłudze Intune zawierają regułę dotyczącą usługi Skycure Mobile Threat Defense, która jest oparta na ocenie ryzyka Skycure. Gdy ta reguła jest włączona, usługa Intune ocenia zgodność urządzenia z zasadami, które zostały włączone.

Jeśli okaże się, że urządzenie nie jest zgodne, może zostać zablokowany dostęp do takich zasobów, jak usługa Exchange Online lub SharePoint Online. Użytkownicy zablokowanych urządzeń otrzymają wskazówki z aplikacji mobilnej Skycure dotyczące rozwiązania problemu i odzyskania dostępu do zasobów firmy.

Usługa Intune obsługuje dwa tryby integracji z programem Skycure:

-   **Konfiguracja podstawowa**, który jest trybem tylko do odczytu, umożliwiającym widoczność Skycure dla urządzeń w usłudze Intune.

-   **Pełna integracja**, który umożliwia programowi Skycure raportowanie do usługi Intune ryzyka urządzeń i szczegółowych informacji dotyczących incydentów zabezpieczeń.

## <a name="sample-scenarios"></a>Przykładowe scenariusze

Poniżej przedstawiono kilka typowych scenariuszy:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kontrola dostępu oparta na zagrożeniach ze strony złośliwych aplikacji

Po wykryciu na urządzeniach złośliwego oprogramowania możesz zablokować na nich następujące funkcje do czasu usunięcia zagrożenia:

-   Łączenie z firmową pocztą e-mail

-   Synchronizowanie plików firmowych za pomocą aplikacji OneDrive do pracy

-   Uzyskiwanie dostępu do aplikacji firmowych

**Blokowanie po wykryciu złośliwych aplikacji:**

![Wykryto złośliwe aplikacje](./media/skycure-arch-1.png)

**Dostęp udzielany po skorygowaniu:**

![Udzielono dostępu po wykryciu złośliwych aplikacji](./media/skycure-arch-2.png)

### <a name="control-access-based-on-threat-to-network"></a>Kontrola dostępu oparta na zagrożeniu dla sieci

Wykrywanie w sieci zagrożeń, takich jak ataki typu **Man-in-the-middle**, i ochrona dostępu do sieci Wi-Fi w oparciu o ryzyko dotyczące urządzenia.

**Blokowanie dostępu do sieci za pośrednictwem sieci Wi-Fi:**

![Blokowanie dostępu do sieci za pośrednictwem sieci Wi-Fi](./media/skycure-arch-3.png)

**Dostęp udzielany po skorygowaniu:**

![Dostęp udzielany po skorygowaniu](./media/skycure-arch-4.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Kontrola dostępu do usługi SharePoint Online oparta na zagrożeniu dla sieci

Wykrywanie w sieci zagrożeń, takich jak ataki typu **Man-in-the-middle**, i blokowanie synchronizacji plików firmowych w oparciu o ryzyko dotyczące urządzenia.

**Blokowanie usługi SharePoint Online po wykryciu zagrożeń sieciowych:**

![Blokowanie usługi SharePoint Online po wykryciu zagrożeń sieciowych](./media/skycure-arch-5.png)

**Dostęp udzielany po skorygowaniu:**

![Dostęp udzielany po skorygowaniu — przykład dla programu Sharepoint](./media/skycure-arch-6.png)

## <a name="supported-platforms"></a>Obsługiwane platformy

-   **Android 4.1 i nowsze**

-   **iOS 8 i nowsze**

## <a name="pre-requisites"></a>Wymagania wstępne

-   Azure Active Directory Premium

-   Subskrypcja usługi Microsoft Intune

-   Subskrypcja usługi Skycure Mobile Threat Defense

Więcej informacji można znaleźć w [witrynie sieci Web Skycure](https://www.skycure.com/skycure-microsoft-integration/).

## <a name="next-steps"></a>Następne kroki

Poniżej przedstawiono kroki, które należy wykonać w celu zintegrowania usługi Intune z programem Skycure:

1.  [Dodawanie i przypisywanie aplikacji Skycure, aplikacji Microsoft Authenticator i zasad konfiguracji aplikacji systemu iOS](mtd-apps-ios-app-configuration-policy-add-assign.md)

2.  [Konfiguracja integracji z programem Skycure w usłudze Intune](skycure-mtd-connector-integration.md)

3.  [Włączenie programu Skycure MTD w usłudze Intune](mtd-connector-enable.md)

4.  [Tworzenie zasad zgodności urządzeń w programie Skycure przy użyciu usługi Intune](mtd-device-compliance-policy-create.md)
