---
# required metadata

title: Przykładowe scenariusze ograniczania dostępu do poczty e-mail | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 454eab79-b620-42c9-b8e6-fada6e719fcd

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Ograniczanie dostępu do poczty e-mail przy użyciu usługi Microsoft Intune: przykładowe scenariusze

## Zablokuj użytkownikom możliwość używania niezgodnych urządzeń do uzyskiwania dostępu do usługi Exchange Online.
### Wymagania dotyczące scenariusza
- Dostęp do usługi Exchange Online musi być zablokowany dla wszystkich użytkowników w grupie zabezpieczeń usługi Active Directory **Księgowość**, jeśli ich urządzenia nie są zgodne z wdrożonymi zasadami zgodności.
- Jeśli w tej grupie znajduje się jakikolwiek użytkownik, którego urządzenia nie są obsługiwane przez usługę [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], dostęp z tych urządzeń do usługi Exchange Online musi być zablokowany.
- Wszyscy użytkownicy w grupie zabezpieczeń usługi Active Directory **Finanse** muszą być wykluczeni z zasad, nawet jeśli należą również do grupy zabezpieczeń **Księgowość**.

W tym celu należy skonfigurować zasady dostępu warunkowego dla usługi Exchange Online z następującymi ustawieniami:

-   Wybierz pozycję **Włącz zasady dostępu warunkowego**.

- Wybierz platformy, dla których ma być dozwolony dostęp z aplikacji używających nowoczesnego uwierzytelniania.
- W przypadku aplikacji Exchange ActiveSync wybierz pozycje **Zablokuj niezgodne urządzenia na platformach obsługiwanych przez usługę Microsoft Intune** i **Zablokuj wszystkie inne urządzenia na platformach nieobsługiwanych przez usługę Microsoft Intune**.
-   W sekcji **Grupa docelowa** w obszarze **Wybrane grupy zabezpieczeń** wybierz grupę użytkowników **Księgowość**.

-   W sekcji **Wykluczona grupa** w obszarze **Wybrane grupy zabezpieczeń** wybierz grupę  użytkowników **Finanse**.


Następujący przepływ służy do określania, które urządzenia mogą uzyskać dostęp do usługi Exchange Online:

![Przepływ dostępu do urządzeń](./media/ConditionalAccess8-5.png)

## Wszystkie urządzenia z systemem iOS, które uzyskują dostęp do lokalnego programu Exchange, muszą być zarządzane przez usługę Intune
### Wymagania dotyczące scenariusza
- Dostęp do lokalnego programu Exchange powinny mieć tylko urządzenia z systemem iOS.
- Urządzenia muszą być również zarejestrowane w usłudze Intune i spełniać reguły zasad zgodności zanim będzie można ich użyć do uzyskania dostępu do programu Exchange.

W tym celu należy skonfigurować następujące zasady dostępu warunkowego dla lokalnego programu Exchange z następującymi ustawieniami:

-   Wybierz opcję **Zablokuj dostęp aplikacjom poczty e-mail do lokalnego programu Exchange, jeśli urządzenie jest niezgodne lub nie jest zarejestrowane w usłudze Microsoft Intune**. Po zaznaczeniu tej opcji włączane są zasady dostępu warunkowego, które wymagają, aby wszystkie urządzenia były zarejestrowane w usłudze Microsoft Intune i spełniały reguły zasad zgodności zanim będą mogły uzyskać dostęp do programu Exchange.

-   Aby uzyskać zaawansowane ustawienia programu Exchange ActiveSync, utwórz:

  -   Wyjątek dla platformy umożliwiający urządzeniom z systemem iOS dostęp do programu Exchange.   

  -   Domyślną regułę określającą, że jeśli urządzenie nie jest objęte regułą wyjątku platformy, to jego dostęp do programu Exchange powinien zostać zablokowany. Ta reguła zapewnia, że urządzenia z systemami innymi niż iOS będą miały zablokowany dostęp do programu Exchange.

Następujący przepływ służy do określania, które urządzenia mogą uzyskać dostęp do programu Exchange:

![Przepływ dostępu do urządzeń](./media/ConditionalAccess8-3.png)

## Żadne urządzenia z systemem Android nie mogą uzyskać dostępu do lokalnego programu Exchange.
### Wymagania dotyczące scenariusza
- Wszystkie urządzenia z systemem Android powinny mieć zablokowany dostęp do programu Exchange.
- Wszystkie inne obsługiwane urządzenia mogą uzyskać dostęp do programu Exchange, o ile są zarządzane przez usługę [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

W tym celu należy skonfigurować zasady dostępu warunkowego dla lokalnego programu Exchange z następującymi ustawieniami:

-   Wybierz opcję **Zablokuj dostęp aplikacjom poczty e-mail do lokalnego programu Exchange, jeśli urządzenie jest niezgodne lub nie jest zarejestrowane w usłudze Microsoft Intune**. Wybór tej opcji oznacza, że wymagane jest, aby wszystkie urządzenia były zarejestrowane w usłudze Intune i spełniały reguły zasad zgodności.

- Aby uzyskać zaawansowane ustawienia programu Exchange ActiveSync, utwórz:
  -   Wyjątek dla platformy blokujący dostęp urządzeń z systemem Android do programu Exchange. Ta reguła zapewnia, że urządzenia z systemem Android nie mogą być używane do uzyskania dostępu do programu Exchange.

  -   Domyślną regułę określającą, że jeśli urządzenie nie jest objęte innymi regułami, to powinno mieć dostęp do programu Exchange. Ta zasada domyślna służy do zapewnienia, że urządzenia z systemem innym niż Android, ale obsługiwane przez usługę Microsoft Intune, mogą być używane do uzyskania dostępu do programu Exchange. Takie urządzenia muszą być jednak zarejestrowane w usłudze Intune i spełniać reguły zasad zgodności.

Następujący przepływ służy do określania, które urządzenia mogą uzyskać dostęp do programu Exchange:

![Przepływ dostępu do urządzeń](./media/ConditionalAccess8-4.png)


<!--HONumber=Jun16_HO2-->


