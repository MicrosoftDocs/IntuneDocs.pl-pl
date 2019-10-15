---
title: Zarządzanie wersjami systemu operacyjnego w usłudze Microsoft Intune
titleSuffix: Microsoft Intune
description: Dowiedz się, jak w usłudze Microsoft Intune zarządzać wersjami systemów operacyjnych na różnych platformach.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 361ef17b-1ee0-4879-b7b1-d678b0787f5a
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3be329e5b84f307c2683bc3799ff9cd6deafe729
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71726014"
---
# <a name="manage-operating-system-versions-with-intune"></a>Zarządzanie wersjami systemu operacyjnego w usłudze Intune
Na nowoczesnych platformach urządzeń przenośnych i komputerów ważne aktualizacje, poprawki i nowe wersje pojawiają się bardzo często. Aktualizacjami i poprawkami dla systemu Windows możesz zarządzać w pełni, ale w przypadku systemów iOS i Android wymagane jest uczestnictwo użytkowników końcowych w tym procesie.  Usługa Microsoft Intune ma funkcje pomagające uporządkować zarządzanie wersjami systemów operacyjnych na różnych platformach.

Usługa Intune sprawdzi się w następujących typowych scenariuszach: 
- Określanie, które wersje systemów operacyjnych są zainstalowane na urządzeniach użytkowników końcowych
- Kontrolowanie dostępu do danych organizacji na urządzeniach w trakcie weryfikowania nowego wydania systemu operacyjnego
- Zachęcanie użytkowników końcowych do przeprowadzenia uaktualnienia do najnowszej wersji systemu operacyjnego zatwierdzonej przez organizację lub wymaganie tego od użytkowników końcowych
- Zarządzanie wdrażaniem nowej wersji systemu operacyjnego w całej organizacji
  
## <a name="operating-system-version-control-using-intune-mobile-device-management-mdm-enrollment-restrictions"></a>Kontrolowanie wersji systemu operacyjnego za pomocą ograniczeń rejestracji w systemie zarządzania urządzeniami przenośnymi (MDM) usługi Intune
Ograniczenia rejestracji systemu MDM usługi Intune pozwalają zdefiniować wymagania co do urządzenia klienckiego zanim zezwolisz na rejestrację urządzenia. Celem jest wymaganie, aby użytkownicy końcowi rejestrowali tylko zgodne urządzenia przed uzyskaniem dostępu do zasobów organizacji. Wymagania dotyczące urządzeń obejmują minimalną i maksymalną dozwoloną wersję systemu operacyjnego dla obsługiwanych platform.

![Blok ograniczeń konfiguracji platformy](./media/manage-os-versions/os-version-platform-configurations.png)

### <a name="in-practice"></a>W praktyce

Organizacje używają ograniczeń typu urządzeń, aby kontrolować dostęp do zasobów organizacji, używając następujących ustawień:

1. Użyj minimalnej wersji systemu operacyjnego, aby użytkownicy końcowi korzystali z aktualnych platform obsługiwanych w Twojej organizacji.
2. Nie określaj maksymalnej wersji systemu operacyjnego (brak ograniczenia) albo ustaw ją na ostatnią wersję zweryfikowaną przez Twoją organizację, aby był czas na wewnętrzne testy nowych wersji systemu operacyjnego.

Aby uzyskać szczegółowe informacje, zobacz [Ustawianie ograniczeń typu urządzenia](../enrollment/enrollment-restrictions-set.md#create-a-device-type-restriction).

## <a name="operating-system-version-reporting-and-compliance-with-intune-mdm-device-compliance-policies"></a>Raportowanie wersji systemu operacyjnego i zgodność z zasadami zgodności urządzeń w systemie MDM usługi Intune

Zasady zgodności urządzeń systemu MDM usługi Intune zapewniają następujące narzędzia:

- Określanie reguł zgodności
- Wyświetlanie stanu zgodności za pośrednictwem raportowania
- Stosowanie kwarantanny lub dostępu warunkowego dla urządzeń w przypadku braku zgodności

Podobnie jak w przypadku ograniczeń rejestracji, zasady zgodności urządzeń zawierają minimalną i maksymalną wersję systemu operacyjnego. Zasady mają również oś czasu zgodności, dzięki której można dać użytkownikom czas na osiągnięcie zgodności. Zasady zgodności urządzeń sprawiają, że zarejestrowane urządzenia użytkowników końcowych pozostają zgodne z zasadami organizacji.

![Zgodność urządzenia — akcje podejmowane względem niezgodnych urządzeń](./media/manage-os-versions/os-version-actions-noncompliance.png)

### <a name="in-practice"></a>W praktyce
Organizacje stosują zasady zgodności urządzeń dla tych samych scenariuszy co ograniczenia rejestracji. Te zasady powodują, że użytkownicy korzystają z aktualnych wersji systemów operacyjnych zweryfikowanych w Twojej organizacji. Gdy urządzenia użytkowników końcowych utracą zgodność, dostęp do zasobów organizacji może zostać zablokowany przez zastosowanie dostępu warunkowego, który zostanie wycofany, gdy użytkownicy znów będą mieć systemy operacyjne z zakresu obsługiwanego przez organizację. Użytkownicy końcowi są powiadamiani, że ich urządzenia są niezgodne, i przedstawiane im są kroki, które muszą wykonać, aby odzyskać dostęp do zasobów.   

Aby uzyskać szczegółowe informacje, zobacz [Get started with device compliance (Wprowadzenie do zgodności urządzeń)](../protect/device-compliance-get-started.md).
 
## <a name="operating-system-version-controls-using-intune-app-protection-policies"></a>Kontrolowanie wersji systemu operacyjnego za pomocą zasad ochrony aplikacji usługi Intune    
Zasady ochrony aplikacji usługi Intune i ustawienia dostępu w systemie zarządzania aplikacjami mobilnymi (MAM) pozwalają określać minimalną wersję systemu operacyjnego w warstwie aplikacji. Dzięki temu można informować użytkowników o konieczności zaktualizowania ich systemów operacyjnych do określonej minimalnej wersji, zachęcać ich do tego, a nawet tego wymagać.
 
Dostępne są dwie opcje: 
- **Ostrzeżenie** — informuje użytkownika końcowego o konieczności uaktualnienia, gdy otworzy aplikację z zasadami ochrony aplikacji lub ustawieniami dostępu systemu MAM na urządzeniu z systemem operacyjnym w wersji starszej niż minimalna. Dostęp do aplikacji i danych organizacji jest dozwolony.
  ![Obraz przedstawiający okno dialogowe z ostrzeżeniem dotyczącym aktualizacji w systemie Android](./media/manage-os-versions/os-version-update-warning.png) 

- **Zablokowanie** — informuje użytkownika końcowego o obowiązku uaktualnienia, gdy otworzy aplikację z zasadami ochrony aplikacji lub ustawieniami dostępu systemu MAM na urządzeniu z systemem operacyjnym w wersji starszej niż określona. Dostęp do aplikacji i danych organizacji jest zabroniony.
  ![Obraz przedstawiający okno dialogowe z informacją o zablokowaniu dostępu do aplikacji](./media/manage-os-versions/os-version-access-blocked.png)

### <a name="in-practice"></a>W praktyce
Obecnie organizacje używają ustawień zasad ochrony aplikacji, gdy aplikacje są otwierane lub gdy ich działanie jest wznawiane, aby informować użytkowników końcowych o konieczności dbania o ich aktualność. Przykładowa konfiguracja może być następująca: użytkownicy są ostrzegani, gdy używana przez nich wersja jest o jedną starsza od aktualnej, a blokowani, gdy jest starsza o dwie od aktualnej.
 
Aby uzyskać szczegółowe informacje, zobacz [Tworzenie i przypisywanie zasad ochrony aplikacji](../apps/app-protection-policies.md).

## <a name="managing-a-new-operating-system-version-rollout"></a>Zarządzanie wdrażaniem nowej wersji systemu operacyjnego
Z funkcji usługi Intune opisanych w tym artykule można korzystać, aby przejść w organizacji na nową wersję systemu operacyjnego w założonym czasie. Następujące kroki stanowią przykładowy model wdrażania, w ramach którego użytkownicy przejdą w ciągu 7 dni z systemu operacyjnego v1 na system operacyjny v2.
- **Krok 1**. Użyj ograniczeń rejestrowania, aby wymagać systemu operacyjnego v2 jako minimalnej wersji koniecznej do zarejestrowania urządzenia. Zagwarantuje to, że nowe urządzenia użytkowników końcowych będą zgodne w chwili rejestracji.
- **Krok 2a**. Użyj zasad ochrony aplikacji usługi Intune, aby po otwarciu aplikacji lub wznowieniu jej działania ostrzegać użytkowników, że wymagany jest system operacyjny v2.
- **Krok 2b**. Użyj zasad zgodności urządzeń, aby wymagać systemu operacyjnego v2 jako minimalnej wersji do zgodności urządzenia. Użyj **akcji** dotyczących braku zgodności, aby zezwolić na 7-dniowy okres prolongaty i wysłać do użytkowników końcowych powiadomienie e-mail z osią czasu i wymaganiami.
  - Te zasady będą informować użytkowników końcowych o konieczności zaktualizowania istniejących urządzeń za pośrednictwem poczty e-mail, w Portalu firmy usługi Intune i podczas otwierania aplikacji z obsługą zasad ochrony aplikacji.
  - Aby zobaczyć, którzy użytkownicy są niezgodni, można uruchomić raport zgodności. 
- **Krok 3a**. Użyj zasad ochrony aplikacji usługi Intune, aby zablokować użytkowników urządzeń bez systemu operacyjnego v2 po uruchomieniu aplikacji lub wznowieniu jej działania.
- **Krok 3b**. Użyj zasad zgodności urządzeń, aby wymagać systemu operacyjnego v2 jako minimalnej wersji do zgodności urządzenia.
  - Te zasady wymagają zaktualizowania urządzeń, aby możliwy był dalszy dostęp do danych organizacji. Gdy urządzenie działa w trybie dostępu warunkowego, chronione usługi są blokowane. Aplikacje z obsługą zasad ochrony aplikacji są blokowane po otwarciu lub przy próbie uzyskania dostępu do danych organizacji.

## <a name="next-steps"></a>Następne kroki

Użyj następujących zasobów, aby zarządzać wersjami systemów operacyjnych w swojej organizacji:

- [Ustawianie ograniczeń typu urządzeń](../enrollment/enrollment-restrictions-set.md#create-a-device-type-restriction)
- [Wprowadzenie do zasad zgodności urządzeń](../protect/device-compliance-get-started.md)
- [Tworzenie i przypisywanie zasad ochrony aplikacji](../apps/app-protection-policies.md)