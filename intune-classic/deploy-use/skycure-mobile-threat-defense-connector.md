---
title: Łącznik Skycure Mobile Threat Defense
description: Chroń dostęp do zasobów firmy na podstawie ryzyka dotyczącego urządzeń, sieci i aplikacji przy użyciu łącznika usługi Skycure Mobile Threat Defense i usługi Intune.
keywords: ''
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7a004e6c-604a-448c-bfb8-cfda63749f5b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f79e793ec6931d6497c6b66eee98aea39786e962
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="skycure-mobile-threat-defense-connector"></a>Łącznik Skycure Mobile Threat Defense

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Dostęp urządzeń przenośnych do zasobów firmy można kontrolować za pomocą dostępu warunkowego opartego na ocenie ryzyka przeprowadzanej przez usługę Skycure — rozwiązaniu usługi Mobile Threat Defense zintegrowanemu z usługą Microsoft Intune. Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń z uruchomioną usługą Skycure. Są to na przykład:

-   Ochrona fizyczna

-   Ochrona sieciowa

-   Ochrona aplikacji

-   Ochrona przed lukami w zabezpieczeniach

Można skonfigurować zasady dostępu warunkowego oparte na ocenie ryzyka Skycure włączone za pomocą zasad zgodności urządzeń usługi Intune, których w przypadku niezgodnego urządzenia można użyć do zezwalania na dostęp do zasobów firmy lub blokowania go w oparciu o wykryte zagrożenia.

## <a name="how-do-intune-and-skycure-help-protect-your-company-resources"></a>W jaki sposób usługa Intune i program Skycure ułatwiają ochronę zasobów firmy?

Aplikacja mobilna Skycure dla systemu Android lub iOS przechwytuje dane telemetryczne z systemu plików, stosu sieci oraz urządzenia i aplikacji (wszędzie, gdzie są dostępne), a następnie wysyła je do usługi Skycure w chmurze w celu dokonania oceny ryzyka dotyczącego urządzenia pod kątem zagrożeń mobilnych.

Zasady zgodności urządzeń w usłudze Intune zawierają regułę dotyczącą usługi Skycure Mobile Threat Defense, która jest oparta na ocenie ryzyka Skycure. Gdy ta reguła jest włączona, usługa Intune ocenia zgodność urządzenia z zasadami, które zostały włączone.

Jeśli okaże się, że urządzenie nie jest zgodne, może zostać zablokowany dostęp do zasobów, takich jak usługa Exchange Online lub SharePoint Online. Użytkownicy zablokowanych urządzeń otrzymają wskazówki z aplikacji mobilnej Skycure dotyczące rozwiązania problemu i odzyskania dostępu do zasobów firmy.

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

![Wykryto złośliwe aplikacje](../media/mtp/skycure-arch-1.png)

**Dostęp udzielany po skorygowaniu:**

![Udzielono dostępu po wykryciu złośliwych aplikacji](../media/mtp/skycure-arch-2.png)

### <a name="control-access-based-on-threat-to-network"></a>Kontrola dostępu oparta na zagrożeniu dla sieci

Wykrywanie w sieci zagrożeń, takich jak ataki typu **Man-in-the-middle**, i ochrona dostępu do sieci Wi-Fi w oparciu o ryzyko dotyczące urządzenia.

**Blokowanie dostępu do sieci za pośrednictwem sieci Wi-Fi:**

![Blokowanie dostępu do sieci za pośrednictwem sieci Wi-Fi](../media/mtp/skycure-arch-3.png)

**Dostęp udzielany po skorygowaniu:**

![Dostęp udzielany po skorygowaniu](../media/mtp/skycure-arch-4.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Kontrola dostępu do usługi SharePoint Online oparta na zagrożeniu dla sieci

Wykrywanie w sieci zagrożeń, takich jak ataki typu **Man-in-the-middle**, i blokowanie synchronizacji plików firmowych w oparciu o ryzyko dotyczące urządzenia.

**Blokowanie usługi SharePoint Online po wykryciu zagrożeń sieciowych:**

![Blokowanie usługi SharePoint Online po wykryciu zagrożeń sieciowych](../media/mtp/skycure-arch-5.png)

**Dostęp udzielany po skorygowaniu:**

![Dostęp udzielany po skorygowaniu — przykład dla programu Sharepoint](../media/mtp/skycure-arch-6.png)

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

1.  [Konfigurowanie programu Skycure do użycia z funkcją logowania jednokrotnego (SSO) usługi Azure Active Directory](/intune-classic/deploy-use/configure-skycure-to-use-azure-active-directory-single-sign-on)

2.  [Pobieranie zasad konfiguracji aplikacji Skycure dla systemu iOS](/intune-classic/deploy-use/download-skycure-ios-app-configuration-policy)

3.  [Dodanie aplikacji Skycure, aplikacji Microsoft Authenticator i zasad konfiguracji aplikacji systemu iOS](/intune-classic/deploy-use/add-skycure-apps-microsoft-authenticator-and-ios-app-configuration-policy)

4.  [Wdrożenie aplikacji Skycure, aplikacji Microsoft Authenticator i zasad konfiguracji aplikacji systemu iOS](/intune-classic/deploy-use/deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy)

5.  [Konfiguracja integracji z programem Skycure w usłudze Intune](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)

6.  [Włączenie usługi Skycure Mobile Threat Defense w usłudze Intune](/intune-classic/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

7.  [Utworzenie zasad zgodności usługi Skycure Mobile Threat Defense w usłudze Intune](/intune-classic/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)
