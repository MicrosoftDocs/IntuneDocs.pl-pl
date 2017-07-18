---
title: "Wspieranie przyjęcia rozwiązania przez użytkowników końcowych przy użyciu dostępu warunkowego"
description: "Celem tego artykułu jest przybliżenie szczegółowych informacji na temat sposobu wykorzystania dostępu warunkowego w celu przyspieszenia rejestracji w usłudze Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0b2fbcc1d63f229e1b63873841bc300bdde92fa3
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2017
---
# <a name="drive-end-user-adoption-with-conditional-access"></a>Wspieranie przyjęcia rozwiązania przez użytkowników końcowych przy użyciu dostępu warunkowego

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Włączenie w usłudze Intune funkcji dostępu warunkowego, w tym np. blokowania wiadomości e-mail dla urządzeń, które nie są zarejestrowane, może zachęcić użytkowników do rejestracji urządzeń i sprzyjać zgodności, nie jest jednak niezbędne dla pomyślnego przeprowadzenia migracji. O sukcesie powinny decydować cele wdrażania technologii w ramach migracji oraz wymagania dotyczące zabezpieczeń.

## <a name="migration-campaign-with-conditional-access"></a>Kampania migracji uwzględniająca dostęp warunkowy

Poniżej przedstawiono typowe podejście do zwiększenia liczby rejestrowanych urządzeń w ramach kampanii migracji poprzez zastosowanie dostępu warunkowego:

1.  Ustaw zasady dostępu warunkowego, które zostaną wymuszone dla wszystkich użytkowników, ale wyklucz konkretnie użytkowników, w przypadku których jest wymagana migracja ze starego rozwiązania MDM. Możesz utworzyć grupę użytkowników usługi Azure AD, do której należeć będą wszyscy użytkownicy wykluczeni z dostępu warunkowego.

2.  Po przeprowadzeniu migracji przez danego użytkownika możesz go usunąć z grupy wykluczenia dostępu warunkowego.

3.  Po zakończeniu migracji skonfiguruj wszystkie zasady dostępu warunkowego pod kątem domyślnego blokowania z wyjątkiem sytuacji, gdy usługa Intune zezwala na dostęp.

### <a name="advantages"></a>Zalety

-   Zapewnia kontrolę dostępu dla nowych kont użytkowników oraz kont użytkowników, które nie były zarządzane z użyciem poprzedniego rozwiązania.

-   Uwzględnia okres prolongaty, w którym użytkownicy korzystający z poprzedniego rozwiązania mogą dokonać migracji.

-   Minimalizuje spadek produktywności

### <a name="disadvantages"></a>Wady

-   Użytkownicy korzystający z poprzedniego rozwiązania mogą potencjalnie uzyskać dostęp do zasobów za pomocą niezarządzanych urządzeń do czasu włączenia dla nich dostępu warunkowego.

> [!TIP]
> Jest to jedno z wielu możliwych podejść. Można wybrać prostszy proces, który odracza wszelki dostęp warunkowy do czasu przekazania instrukcji dotyczących rejestracji uczestnikom wszystkich faz, lub bardziej rygorystyczny proces, który będzie od samego początku wymuszał dostęp warunkowy i wymagał zachowania pełnej zgodności w celu uzyskania dostępu.

-   Dowiedz się więcej na temat [dostępu warunkowego](/intune/conditional-access).

## <a name="task-list-for-conditional-access"></a>Lista zadań związanych z konfiguracją dostępu warunkowego

### <a name="task-1-decide-how-you-are-going-to-implement-conditional-access"></a>Zadanie 1: Podjęcie decyzji o sposobie wdrożenia dostępu warunkowego

[Typowe sposoby korzystania z dostępu warunkowego](/intune/conditional-access-intune-common-ways-use).

### <a name="task-2-set-up-intune-conditional-access"></a>Zadanie 2. Konfiguracja dostępu warunkowego w usłudze Intune

Wybierz jedną z następujących opcji:

-   [Konfigurowanie dostępu warunkowego w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

-   [Instalowanie łącznika lokalnego programu Exchange w usłudze Intune](/intune/exchange-connector-install)

-   [Konfigurowanie zasad dostępu warunkowego opartego na aplikacji dla usługi Exchange Online](/intune/app-based-conditional-access-intune-exchange-online-create)

-   [Konfigurowanie zasad dostępu warunkowego opartego na aplikacji dla usługi SharePoint Online](/intune/app-based-conditional-access-intune-sharepoint-online-create)

-   [Blokowanie aplikacji, które nie korzystają z nowoczesnego uwierzytelniania (ADAL)](/intune/app-modern-authentication-block)

## <a name="next-steps"></a>Następne kroki

[Typowy cykl migracji](migration-guide-cycle.md)