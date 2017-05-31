---
title: "Wspieranie przyjęcia rozwiązania przez użytkowników końcowych przy użyciu dostępu warunkowego | Microsoft Docs"
description: "Celem tego artykułu jest przybliżenie szczegółowych informacji na temat sposobu wykorzystania dostępu warunkowego w celu przyspieszenia rejestracji w usłudze Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 55e437fa33af9d27223798cbac9f541b0bc1be2d
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="phase-2-drive-end-user-adoption-with-conditional-access"></a>Faza 2: Wspieranie przyjęcia rozwiązania przez użytkowników końcowych przy użyciu dostępu warunkowego

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

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

-   Dowiedz się więcej na temat [dostępu warunkowego](https://docs.microsoft.com/intune/conditional-access).

## <a name="task-list-for-conditional-access"></a>Lista zadań związanych z konfiguracją dostępu warunkowego

### <a name="task-1-get-ready-for-intune-conditional-access"></a>Zadanie 1. Przygotowanie do wprowadzenia dostępu warunkowego w usłudze Intune

-   Dowiedz się, [jak skonfigurować dostęp warunkowy](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

### <a name="task-2-set-up-intune-conditional-access"></a>Zadanie 2. Konfiguracja dostępu warunkowego w usłudze Intune

Wybierz jeden z poniższych typów zasad dostępu warunkowego, aby dowiedzieć się więcej:

-   [Usługa Exchange Online i nowa usługa Exchange Online w wersji dedykowanej](/intune-classic/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)

-   [Lokalna instalacja programu Exchange i starsza usługa Exchange Online w wersji dedykowanej](/intune-classic/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)

-   [SharePoint Online](/intune-classic/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)

-   [Skype dla firm Online](/intune-classic/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)

-   [Dynamics CRM Online](/intune-classic/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)

-   [Przykładowe scenariusze dostępu do poczty e-mail](/intune-classic/deploy-use/restrict-email-access-example-scenarios)

## <a name="next-steps"></a>Następne kroki

[Faza 2: Typowy cykl migracji](/intune-classic/plan-design/migration-phase2-typical-migration-cycle)

