---
title: "Ochrona poczty e-mail i usługi Office 365"
description: "W tym temacie opisano, jak można wykorzystać dostęp warunkowy do umożliwienia dostępu do firmowej poczty e-mail i danych firmowych w usłudze SharePoint Online i innych usługach tylko ze zgodnych urządzeń."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c564d292-b83b-440d-bf08-3f5b299b7a5e
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ab45292734c39d3eaf4a5f0403cbff6e77d9d7e6
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2017
---
# <a name="protect-access-to-email-office-365-and-other-services-with-microsoft-intune"></a>Ochrona dostępu do poczty e-mail, usług Office 365 i innych usług przy użyciu usługi Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Za pomocą dostępu warunkowego pakietu Enterprise Mobility + Security (EMS) można zabezpieczyć dostęp do firmowej poczty e-mail, usług Office 365, takich jak **lokalna instalacja programu Exchange**, **usługa Exchange Online**, **usługa Exchange Online w wersji dedykowanej**, **usługa SharePoint Online**, **usługa Skype dla firm Online** i innych. Ta funkcja pozwala na zapewnienie, że dostęp do poczty e-mail i usług Office 365 w Twojej firmie jest ograniczony do urządzeń zgodnych z zasadami ustawionymi w konsoli administracyjnej usługi Intune lub w klasycznym portalu Azure.
## <a name="how-does-conditional-access-work"></a>W jaki sposób działa dostęp warunkowy?
Do oceny zgodności urządzenia można wykorzystać ustawienia zasad zgodności. Zasady dostępu warunkowego używają tej oceny do ograniczenia dostępu do określonej usługi lub zezwolenia na taki dostęp. Jeśli zasady dostępu warunkowego są stosowane w połączeniu z zasadami zgodności urządzeń, tylko zgodne urządzenia będą miały dostęp do usługi. Zasady zgodności i zasady dostępu warunkowego są wdrażane dla użytkownika. Wszystkie urządzenia, których użytkownik używa do uzyskiwania dostępu do usług, są sprawdzane pod kątem zgodności z zasadami.

> [!IMPORTANT]
> Należy pamiętać, że użytkownik korzystający z urządzenia musi mieć na nim wdrożone zasady zgodności, aby urządzenie mogło zostać ocenione pod kątem zgodności.
> Jeśli na urządzeniu nie wdrożono żadnych zasad zgodności dla użytkownika, będzie ono traktowane jako zgodne i nie będą stosowane żadne ograniczenia dostępu.

Gdy urządzenia nie spełniają warunków ustawionych w zasadach, użytkownik końcowy jest przeprowadzany przez procedurę rejestracji urządzenia i rozwiązywania problemu, w związku z którym urządzenie nie może być zgodne.

Typowy przepływ dostępu warunkowego:

![Diagram przedstawiający punkty decyzyjne używane do określenia, czy urządzenie ma mieć dostęp do usługi, czy ma być blokowane](../media/ConditionalAccess4.png)

## <a name="setup-considerations"></a>Zagadnienia dotyczące instalacji

### <a name="licensing"></a>Licencjonowanie

Usługa Microsoft Intune i Azure Active Directory (Azure AD) Premium działają bezproblemowo razem w celu zapewnienia wielu warstw kontroli za pośrednictwem dostępu warunkowego pakietu EMS. Jeśli chcesz wdrożyć zasady dostępu warunkowego za pomocą usługi Intune, musisz mieć licencję dla obu tych produktów.

**Licencje usługi Azure AD Premium** można kupić jako autonomiczną usługę lub wraz z usługą Intune w ramach umowy Enterprise Agreement. Jeśli zasady dostępu warunkowego wdrożono za pomocą usługi Intune, upewnij się, że masz odpowiednie licencje usługi Azure AD Premium lub pakietu **EMS**.

- Dowiedz się więcej na temat [Cennika pakietu Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) lub [Cennika usługi Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).

Ponadto upewnij się, że użytkownicy, dla których planowane jest zastosowanie zasad dostępu warunkowego, są [przypisani za pomocą licencji usługi Azure AD Premium lub pakietu EMS](/intune/licenses-assign).

### <a name="device-compliance-settings"></a>Ustawienia zgodności urządzeń

Aby skonfigurować dostęp warunkowy, skonfiguruj zasady zgodności urządzeń i zasady dostępu warunkowego. Zasady zgodności zawierają ustawienia, takie jak kod dostępu i szyfrowanie, oraz określają, czy urządzenie nie ma zdjętych zabezpieczeń. Urządzenie musi spełniać te reguły, aby można je było uważać za zgodne.

- Dowiedz się więcej o [zasadach zgodności urządzeń i ich działaniu](introduction-to-device-compliance-policies-in-microsoft-intune.md).

### <a name="conditional-access-policy"></a>Zasady dostępu warunkowego

Możliwe jest ustawienie zasad dostępu warunkowego w celu ochrony dostępu w oparciu o:
- Stan zgodności urządzenia.
- Platformę, na której działa urządzenie.
- Typ aplikacji używanych do uzyskiwania dostępu do usług.

W odróżnieniu od innych zasad usługi Intune zasady dostępu warunkowego nie są wdrażane. Zamiast tego po skonfigurowaniu zasad i wybraniu użytkowników, którzy powinni je posiadać, zasady są stosowane do wszystkich użytkowników docelowych. Jeśli zasady obejmują użytkownika, możliwość uzyskania przez niego dostępu do zasobów wymaga zgodności każdego używanego przez niego urządzenia.


## <a name="next-steps"></a>Następne kroki


2. [Tworzenie zasad zgodności urządzenia](create-a-device-compliance-policy-in-microsoft-intune.md).

2.  Utwórz zasady dostępu warunkowego dla jednej z wybranych usług lub jednego z wybranych produktów firmy Microsoft w chmurze:

  - [Tworzenie zasad dostępu warunkowego dla usługi Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Tworzenie zasad dostępu warunkowego dla lokalnego programu Exchange](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Tworzenie zasad dostępu warunkowego dla nowej usługi Exchange Online w wersji dedykowanej](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Tworzenie zasad dostępu warunkowego dla starszej usługi Exchange Online w wersji dedykowanej](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Tworzenie zasad dostępu warunkowego dla usługi SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  - [Tworzenie zasad dostępu warunkowego dla usługi Skype dla firm Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  - [Tworzenie zasad dostępu warunkowego dla usługi Dynamics CRM Online](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)
