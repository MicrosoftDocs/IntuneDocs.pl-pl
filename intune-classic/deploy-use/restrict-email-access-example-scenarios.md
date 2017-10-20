---
title: Scenariusze ochrony poczty e-mail
description: "Kilka przykładowych scenariuszy i sposoby ich implementacji przy użyciu dostępu warunkowego."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 454eab79-b620-42c9-b8e6-fada6e719fcd
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1ca486ca9eab1ebb8a446b560ff5e265eb4d2712
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2017
---
# <a name="protect-access-to-email-with-microsoft-intune-example-scenarios"></a>Ochrona dostępu do poczty e-mail przy użyciu usługi Microsoft Intune: przykładowe scenariusze

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="scenario-1-block-users-from-using-noncompliant-devices-to-access-exchange-online"></a>Scenariusz 1. Blokowanie użytkownikom możliwości używania niezgodnych urządzeń do uzyskiwania dostępu do usługi Exchange Online
### <a name="scenario-requirements"></a>Wymagania dotyczące scenariusza
- Dostęp do usługi Exchange Online musi być zablokowany dla wszystkich użytkowników w grupie zabezpieczeń **Księgowość** usługi Azure Active Directory, jeśli ich urządzenia są niezgodne z wdrożonymi zasadami zgodności.
- Jeśli w tej grupie znajduje się jakikolwiek użytkownik, którego urządzenia nie są obsługiwane przez usługę Intune, dostęp z tych urządzeń do usługi Exchange Online musi być zablokowany.
- Wszyscy użytkownicy w grupie zabezpieczeń **Finanse** usługi Azure Active Directory muszą być wykluczeni z zasad, nawet jeśli należą również do grupy zabezpieczeń **Księgowość**.

W tym celu należy skonfigurować zasady dostępu warunkowego dla usługi Exchange Online z następującymi ustawieniami:

- Wybierz pozycję **Włącz zasady dostępu warunkowego**.

- Wybierz platformy, dla których ma być dozwolony dostęp za pomocą aplikacji używających nowoczesnego uwierzytelniania.
- W przypadku aplikacji Exchange ActiveSync wybierz pozycje **Zablokuj niezgodne urządzenia na platformach obsługiwanych przez usługę Microsoft Intune** i **Zablokuj wszystkie inne urządzenia na platformach nieobsługiwanych przez usługę Microsoft Intune**.
-   W sekcji **Grupa docelowa** w obszarze **Wybrane grupy zabezpieczeń** wybierz grupę użytkowników **Księgowość**.

-   W sekcji **Wykluczona grupa** w obszarze **Wybrane grupy zabezpieczeń** wybierz grupę użytkowników **Finanse**.


Następujący przepływ w tym scenariuszu służy do określania, które urządzenia mogą uzyskiwać dostęp do usługi Exchange Online:

![Przepływ dostępu do urządzeń](./media/ConditionalAccess8-5.png)

## <a name="scenario-2-all-ios-devices-that-access-exchange-on-premises-must-be-managed-by-intune"></a>Scenariusz 2. Wszystkie urządzenia z systemem iOS, które uzyskują dostęp do lokalnego programu Exchange, muszą być zarządzane przy użyciu usługi Intune
### <a name="scenario-requirements"></a>Wymagania dotyczące scenariusza
- Dostęp do lokalnego programu Exchange powinny mieć tylko urządzenia z systemem iOS.
- Urządzenia muszą być również zarejestrowane w usłudze Intune i spełniać reguły zasad zgodności zanim będzie można ich użyć do uzyskania dostępu do programu Exchange.

W tym celu należy skonfigurować następujące zasady dostępu warunkowego dla lokalnego programu Exchange z następującymi ustawieniami:

-   Wybierz opcję **Zablokuj dostęp aplikacjom poczty e-mail do lokalnego programu Exchange, jeśli urządzenie jest niezgodne lub nie jest zarejestrowane w usłudze Microsoft Intune**. Wybór tej opcji powoduje włączenie zasad dostępu warunkowego, które wymagają, aby wszystkie urządzenia były zarejestrowane w usłudze Microsoft Intune i spełniały reguły zasad zgodności zanim będą mogły uzyskać dostęp do programu Exchange.

-   Aby użyć zaawansowanych ustawień programu Exchange Active Sync, utwórz:

  -   Wyjątek dla platformy umożliwiający urządzeniom z systemem iOS dostęp do programu Exchange.   

  -   Domyślną regułę określającą, że jeśli urządzenie nie jest objęte regułą wyjątku platformy, to jego dostęp do programu Exchange powinien zostać zablokowany. Ta reguła zapewnia, że urządzenia z systemami innymi niż iOS będą miały zablokowany dostęp do programu Exchange.

Następujący przepływ służy do określania, które urządzenia mogą uzyskiwać dostęp do programu Exchange:

![Przepływ dostępu do urządzeń](./media/ConditionalAccess8-3.png)

## <a name="scenario-3-no-android-devices-can-access-exchange-on-premises"></a>Scenariusz 3. Żadne urządzenia z systemem Android nie mogą uzyskiwać dostępu do lokalnego programu Exchange
### <a name="scenario-requirements"></a>Wymagania dotyczące scenariusza
- Wszystkie urządzenia z systemem Android powinny mieć zablokowany dostęp do programu Exchange.
- Wszystkie inne obsługiwane urządzenia mogą uzyskiwać dostęp do programu Exchange, o ile są zarządzane przy użyciu usługi Intune.

W tym celu należy skonfigurować zasady dostępu warunkowego dla lokalnego programu Exchange z następującymi ustawieniami:

-   Wybierz opcję **Zablokuj dostęp aplikacjom poczty e-mail do lokalnego programu Exchange, jeśli urządzenie jest niezgodne lub nie jest zarejestrowane w usłudze Microsoft Intune**. Wybór tej opcji oznacza, że wymagane jest, aby wszystkie urządzenia były zarejestrowane w usłudze Intune i spełniały reguły zasad zgodności.

- Aby użyć zaawansowanych ustawień programu Exchange Active Sync, utwórz:
  -   Wyjątek dla platformy blokujący dostęp urządzeń z systemem Android do programu Exchange. Ta reguła zapewnia, że urządzenia z systemem Android nie mogą być używane do uzyskiwania dostępu do programu Exchange.

  -   Domyślną regułę określającą, że jeśli urządzenie nie jest objęte innymi regułami, to powinno mieć dostęp do programu Exchange. Ta zasada domyślna zapewnia, że urządzenia z systemem innym niż Android, ale obsługiwane przez usługę Microsoft Intune, mogą być używane do uzyskiwania dostępu do programu Exchange. Takie urządzenia muszą być jednak zarejestrowane w usłudze Intune i spełniać reguły zasad zgodności.

Następujący przepływ służy do określania, które urządzenia mogą uzyskiwać dostęp do programu Exchange:

![Przepływ dostępu do urządzeń](./media/ConditionalAccess8-4.png)
