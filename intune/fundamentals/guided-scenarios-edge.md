---
title: Scenariusz z przewodnikiem — wdrażanie przeglądarki Microsoft Edge dla urządzeń przenośnych
titleSuffix: Microsoft Intune
description: Zapoznaj się ze scenariuszem z przewodnikiem dotyczącym wdrażania przeglądarki Microsoft Edge dla urządzeń przenośnych w portalu zarządzania urządzeniami na platformie Microsoft 365.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e86f3a469169e7a805cb3f56e570ba4d3a90e925
ms.sourcegitcommit: 0be25b59c8e386f972a855712fc6ec3deccede86
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2019
ms.locfileid: "72585699"
---
# <a name="guided-scenario---deploy-microsoft-edge-for-mobile"></a>Scenariusz z przewodnikiem — wdrażanie przeglądarki Microsoft Edge dla urządzeń przenośnych 

Wykonując czynności opisane w tym [przewodniku ze scenariuszem](~/fundamentals/guided-scenarios-overview.md), możesz przypisać aplikację Microsoft Edge do użytkowników urządzeń z systemem iOS lub Android w swojej organizacji. Przypisanie tej aplikacji umożliwi użytkownikom bezproblemowe przeglądanie zawartości przy użyciu urządzeń firmowych. 

Przeglądarka Microsoft Edge umożliwia użytkownikom łatwiejsze korzystanie z Internetu dzięki wbudowanym funkcjom, które pomagają im konsolidować i porządkować zawartość związaną z pracą oraz nią zarządzać. Użytkownicy urządzeń z systemami iOS i Android, którzy logują się przy użyciu kont firmowych usługi Azure AD w aplikacji Microsoft Edge, zobaczą wstępnie załadowaną przeglądarkę z służbowymi **ulubionymi** oraz zdefiniowanymi przez Ciebie filtrami witryn internetowych.

> [!NOTE]
> Jeśli zablokowano możliwość rejestrowania urządzeń z systemem iOS lub Android przez użytkowników, ten scenariusz nie umożliwi rejestracji, a użytkownicy będą musieli zainstalować przeglądarkę Microsoft Edge samodzielnie.
Dostępne są następujące funkcje przeglądarki Microsoft Edge dla przedsiębiorstw włączane przy użyciu zasad usługi Intune: 

- **Podwójna tożsamość** — użytkownicy mogą dodawać konta służbowe i osobiste na potrzeby przeglądania. Te dwie tożsamości są całkowicie oddzielone, co przypomina architekturę i środowisko usługi Office 365 oraz programu Outlook. Administratorzy usługi Intune będą mogli ustawić żądane zasady dla chronionego środowiska przeglądania w ramach konta służbowego. 
- **Integracja zasad ochrony aplikacji usługi Intune** — administratorzy mogą teraz używać zasad ochrony w przeglądarce Microsoft Edge, w tym kontrolować funkcje wycinania, kopiowania i wklejania, zapobiegać tworzeniu zrzutów ekranu oraz zapewniać, że linki wybrane przez użytkownika będzie można otwierać tylko w innych aplikacjach zarządzanych.
- **Integracja serwera proxy aplikacji platformy Azure** — administratorzy mogą kontrolować dostęp do aplikacji SaaS i aplikacji internetowych, co pomaga zagwarantować, że tylko aplikacje oparte na przeglądarce będą uruchamiane w bezpiecznej przeglądarce Microsoft Edge, bez względu na to, czy użytkownicy końcowi nawiązują połączenie z sieci firmowej, czy też z Internetu. 
- **Skróty do zarządzanych ulubionych i strony głównej** — w celu ułatwienia dostępu administratorzy mogą ustawić adresy URL tak, aby były wyświetlane w obszarze Ulubione, gdy użytkownicy końcowi będą pracować w kontekście firmy. Administratorzy mogą ustawić skrót do strony głównej, który będzie wyświetlany jako skrót podstawowy, gdy użytkownik firmowy otworzy nową stronę lub nową kartę w przeglądarce Microsoft Edge.

## <a name="prerequisites"></a>Wymagania wstępne

- [Ustawianie usługi Intune jako urzędu MDM](mdm-authority-set.md#set-mdm-authority-to-intune) — ustawienie urzędu zarządzania urządzeniami przenośnymi (MDM) określa metodę zarządzania urządzeniami. Jako administrator systemów informatycznych, musisz ustawić urząd MDM, aby użytkownicy mogli zarejestrować urządzenia do zarządzania.
- Wymagane uprawnienia administratora usługi Intune:
    - Uprawnienia do odczytu, tworzenia, usuwania i przypisywania aplikacji zarządzanych
    - Uprawnienia do odczytu, tworzenia i przypisywania aplikacji mobilnych
    - Uprawnienia do odczytu, tworzenia i przypisywania zestawów zasad
    - Uprawnienia do odczytu i aktualizacji w organizacji

## <a name="step-1---introduction"></a>Krok 1. Wprowadzenie

Scenariusz z przewodnikiem **Wdrażanie przeglądarki Microsoft Edge dla urządzeń przenośnych** opisuje konfigurowanie podstawowych wdrożeń przeglądarki Microsoft Edge dla wybranej grupy użytkowników urządzeń z systemami iOS i Android. Obejmuje wdrożenie **podwójnej tożsamości** oraz **skrótów do zarządzanych ulubionych i strony głównej**. Ponadto na urządzeniach zarejestrowanych przez wybranych użytkowników aplikacja Microsoft Edge zostanie automatycznie zainstalowana przez usługę Intune. Ta automatyczna instalacja będzie miała miejsce w przypadku wszystkich typów rejestracji sterowanych przez użytkownika, takich jak: 
- Rejestracja urządzeń z systemem iOS za pośrednictwem aplikacji Portal firmy 
- Rejestracja koligacji urządzenia z systemem iOS użytkownika za pośrednictwem usługi Apple Business Manager 
- Rejestracja starszych urządzeń z systemem Android za pośrednictwem aplikacji Portal firmy 

Ten scenariusz z przewodnikiem obejmuje automatyczne włączenie wyświetlania usługi **MyApps** w Ulubionych w przeglądarce Microsoft Edge i zastosowanie w przeglądarce oznaczeń marki skonfigurowanych dla aplikacji Portal firmy w usłudze Intune. 

### <a name="what-you-will-need-to-continue"></a>Co jest konieczne, aby przejść dalej
Będą potrzebne informacje o stronach służbowych, które mają zostać dodane do Ulubionych dla użytkowników, oraz o filtrach wymaganych podczas przeglądania Internetu. Zanim przejdziesz dalej, upewnij się, że zakończono wykonywanie następujących zadań:

- Dodawanie użytkowników do grup usługi Azure AD. Aby uzyskać więcej informacji, zobacz [Tworzenie podstawowej grupy i dodawanie członków w usłudze Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=2102458).
- Rejestrowanie urządzeń z systemami iOS i Android w usłudze Intune. Aby uzyskać więcej informacji, zobacz temat [Rejestrowanie urządzeń](https://go.microsoft.com/fwlink/?linkid=2102547).
- Przygotowanie listy stron służbowych do dodania do Ulubionych w przeglądarce Microsoft Edge.
- Przygotowanie listy filtrów witryn internetowych, które chcesz zastosować w przeglądarce Microsoft Edge.

## <a name="step-2---basics"></a>Krok 2. Podstawowe informacje

W tym kroku należy wprowadzić nazwę i opis nowych zasad przeglądarki Microsoft Edge. Możesz sprawdzić te zasady później, jeśli konieczna będzie zmiana przypisań i konfiguracji. W scenariuszu z przewodnikiem zostanie dodana aplikacja Microsoft Edge iOS dla urządzeń z systemem iOS oraz aplikacja Microsoft Edge Android dla urządzeń z systemem Android. W tym kroku zostaną również utworzone zasady konfiguracji dla tych aplikacji.

## <a name="step-3---configuration"></a>Krok 3. Konfiguracja

Ten krok scenariusza z przewodnikiem pokazuje, jak skonfigurować przeglądarkę Microsoft Edge, aby były w niej wyświetlane wszystkie inne aplikacje przypisane użytkownikom za pomocą usługi Intune oraz takie same oznaczenia marki, jak w aplikacji Portal firmy w usłudze Microsoft Intune. Możesz dodatkowo skonfigurować w przeglądarce Microsoft Edge **adres URL skrótu do strony głównej**, listę **zakładek zarządzanych** i listę **zablokowanych adresów URL**. **Adres URL skrótu do strony głównej** wyświetli się użytkownikom jako pierwsza ikona poniżej paska wyszukiwania po otwarciu nowej karty w przeglądarce Microsoft Edge na urządzeniu. **Zakładki zarządzane** to lista ulubionych adresów URL dostępnych dla użytkowników podczas korzystania z przeglądarki Microsoft Edge w celach służbowych. **Zablokowane adresy URL** określają witryny, które są zablokowane dla użytkowników podczas korzystania z przeglądarki w celach służbowych. Wszystkie pozostałe witryny będą dozwolone. 

## <a name="step-4---assignments"></a>Krok 4. Przypisania

W tym kroku możesz wybrać grupy użytkowników, które mają mieć skonfigurowaną przeglądarkę Microsoft Edge dla urządzeń przenośnych do celów służbowych. Przeglądarka Microsoft Edge będzie również zainstalowana na wszystkich urządzeniach z systemami iOS i Android zarejestrowanych przez tych użytkowników.

## <a name="step-5---review--create"></a>Krok 5. Przegląd + tworzenie

W ostatnim kroku możesz zapoznać się podsumowaniem skonfigurowanych ustawień. Po sprawdzeniu swoich wyborów kliknij opcję **Utwórz**, aby ukończyć scenariusz z przewodnikiem. 

> [!NOTE]
> Może upłynąć do 12 godzin, zanim konfiguracja zostanie wprowadzona w przeglądarce Edge. Aby uzyskać więcej informacji, zobacz [Zasady konfiguracji aplikacji usługi Microsoft Intune](~/apps/app-configuration-policies-overview.md).

> [!IMPORTANT]
> Po zakończeniu scenariusza z przewodnikiem zostanie wyświetlone podsumowanie. Możesz zmodyfikować zasoby wymienione w podsumowaniu później, ale tabela z tymi zasobami nie zostanie zapisana.

## <a name="next-steps"></a>Następne kroki

- Zwiększ bezpieczeństwo korzystania z przeglądarki Microsoft Edge, konfigurując integrację zasad ochrony aplikacji w usłudze Intune. Aby uzyskać więcej informacji, zobacz [Zasady ochrony aplikacji dla przeglądarki Microsoft Edge](~/apps/manage-microsoft-edge.md#application-protection-policies-for-microsoft-edge).
- Jeśli chcesz dodać witryny intranetowe, dowiedz się więcej na temat ochrony dostępu za pomocą integracji serwera proxy aplikacji platformy Azure. Aby uzyskać więcej informacji, zobacz [Konfigurowanie ustawień serwera proxy aplikacji dla przeglądarki Microsoft Edge](~/apps/manage-microsoft-edge.md#configure-application-proxy-settings-for-microsoft-edge).

