---
title: "Ochrona usługi Skype dla firm Online | Microsoft Docs"
description: "Ochrona i kontrola dostępu do usługi Skype dla firm Online przy użyciu dostępu warunkowego."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1b2d7125-f63f-43cf-ac1e-94fbedf2a7e8
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 312a3ae8a74b0a8460f969f96bee14077c6c7161
ms.lasthandoff: 04/14/2017


---

# <a name="protect-access-to-skype-for-business-online-with-microsoft-intune"></a>Ochrona dostępu do usługi Skype dla firm Online przy użyciu usługi Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Możesz użyć zasad dostępu warunkowego dla usługi **Skype dla firm Online** w celu kontroli dostępu do usługi Skype dla firm Online.
Dostęp warunkowy ma dwa składniki:
- Zasady zgodności urządzenia, które urządzenie musi spełniać, aby zostało uznane za zgodne.
- Zasady dostępu warunkowego, w ramach których określane są warunki, które urządzenie musi spełniać w celu uzyskania dostępu do usługi.
Aby dowiedzieć się więcej o sposobie działania dostępu warunkowego, przeczytaj artykuł [Ochrona dostępu do poczty e-mail i usług O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).

Jeśli wybrany użytkownik próbuje użyć usługi Skype dla firm Online na swoim urządzeniu, sprawdzane są następujące kwestie:

![Diagram przedstawiający punkty decyzyjne służące do określenia, czy urządzenie ma mieć dostęp do usługi Skype dla firm Online, czy ma być blokowane](../media/ConditionalAccess_SkypeforBusiness.png)

**Przed** skonfigurowaniem zasad dostępu warunkowego dla usługi Skype fla firm Online, konieczne jest:
- Posiadanie **subskrypcji usługi Skype dla firm Online** i przypisanie licencji usługi Skype dla firm Online użytkownikom.
- Posiadanie **subskrypcji pakietu Enterprise Mobility + Security (EMS)** lub **subskrypcji usługi Azure Active Directory (Azure AD) Premium** oraz posiadanie licencji użytkowników na usługi EMS lub Azure AD. Aby uzyskać więcej szczegółowych informacji, zobacz [Cennik pakietu Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) lub [Cennik usługi Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).

-   [Włączenie nowoczesnego uwierzytelniania](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune) dla usługi Skype dla firm Online.
-  Wszyscy użytkownicy powinni używać usługi **Skype dla firm Online**. Jeśli wdrożenie obejmuje zarówno usługę Skype dla firm Online, jak i lokalną aplikację Skype dla firm, zasady dostępu warunkowego nie będą stosowane do użytkowników.

Urządzenie, dla którego wymagany jest dostęp do usługi Skype dla firm Online, powinno:

-   Być urządzeniem z system **Android** lub **iOS**.

-   Być **zarejestrowane** w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

-   Być **zgodne** ze wszystkimi wdrożonymi zasadami zgodności usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].


Stan urządzenia jest przechowywany w usłudze Azure Active Directory, która na podstawie wybranych warunków przydziela prawo dostępu lub je blokuje.

Jeśli warunek nie jest spełniony, użytkownik zobaczy podczas logowania jeden z następujących komunikatów:

-   Jeśli urządzenie nie zostało zarejestrowane w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] lub Azure Active Directory, zostanie wyświetlony komunikat z instrukcjami dotyczącymi sposobu instalowania aplikacji Portal firmy i rejestrowania.

-   Jeśli urządzenie nie jest zgodne, zostanie wyświetlony komunikat kierujący użytkownika do witryny Portal firmy usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] lub aplikacji Portal firmy, gdzie można znaleźć informacje o problemie i sposobie jego rozwiązania.

## <a name="configure-conditional-access-for-skype-for-business-online"></a>Konfigurowanie dostępu warunkowego dla usługi Skype dla firm Online

### <a name="step-1-configure-azure-active-directory-security-groups"></a>Krok 1. Konfigurowanie grup zabezpieczeń usługi Azure Active Directory
Przed rozpoczęciem skonfiguruj grupy zabezpieczeń usługi Azure Active Directory dla zasad dostępu warunkowego. Możesz skonfigurować te grupy w **centrum administracyjnym usługi Office 365**. Grupy te zostaną użyte do objęcia użytkowników zasadami lub wykluczenia użytkowników z zasad. Jeśli zasady obejmują użytkownika, każde używane przez niego urządzenie musi być zgodne, aby mógł uzyskać dostęp do zasobów.

Można określić dwa typy grup dla zasad programu Skype dla firm:

-   **Grupy docelowe**: grupy użytkowników, do których zasady mają zastosowanie.

-   **Wykluczone grupy**: grupy użytkowników, którzy są wykluczeni z zasad.

Jeśli użytkownik należy do obu grup, będzie wykluczony z zasad.

### <a name="step-2-configure-and-deploy-a-compliance-policy"></a>Krok 2. Konfigurowanie i wdrażanie zasad zgodności
[Utwórz](create-a-device-compliance-policy-in-microsoft-intune.md) i [wdróż](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) zasady zgodności na wszystkich urządzeniach, które będą objęte zasadami. Będą to wszystkie urządzenia, które są używane przez użytkowników z **grup docelowych**.

> [!NOTE]
> Jeśli zasady zgodności są wdrażane w grupach usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], zasady dostępu warunkowego są stosowane dla grup zabezpieczeń usługi Azure Active Directory.


> [!IMPORTANT]
> Jeśli zasady zgodności nie zostały wdrożone, urządzenia będą traktowane jako zgodne.

Gdy wszystko będzie gotowe, przejdź do **kroku 3**.

### <a name="step-3-configure-the-skype-for-business-online-policy"></a>Krok 3. Konfigurowanie zasad usługi Skype dla firm Online
Skonfiguruj zasady wymagające, aby tylko urządzenia zarządzane i zgodne miały dostęp do usługi Skype dla firm Online. Te zasady będą przechowywane w usłudze Azure Active Directory.

1.  W [konsoli administratora usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycje **Zasady** > **Dostęp warunkowy** > **Skype dla firm Online — zasady**.

  ![Zrzut ekranu przedstawiający stronę zasad dostępu warunkowego usługi Skype dla firm Online](./media/conditional_access_SFBPolicy.png)

2.  Wybierz pozycję **Włącz zasady dostępu warunkowego**.

3.  W obszarze **Dostęp do aplikacji** możesz wybrać platformy, do których zostaną zastosowane zasady dostępu warunkowego:

    -   **iOS**

    -   **Android**

4.  W obszarze **Grupy docelowe** wybierz pozycję **Modyfikuj**, aby wybrać grupy zabezpieczeń usługi Azure Active Directory, do których zostaną zastosowane zasady. Możesz objąć zasadami wszystkich użytkowników lub ich wybrane grupy.

5.  W obszarze **Wykluczone grupy** możesz wybrać pozycję **Modyfikuj**, jeśli chcesz, aby zasady nie były stosowane dla wskazanych grup zabezpieczeń usługi Azure Active Directory.

6.  Po zakończeniu tych czynności wybierz pozycję **Zapisz**.

Dostęp warunkowy dla usługi Skype dla firm Online został skonfigurowany. Nie musisz wdrażać zasad dostępu warunkowego, ponieważ zostają one natychmiast zastosowane.


## <a name="monitor-the-compliance-and-conditional-access-policies"></a>Monitorowanie zgodności i zasad dostępu warunkowego
W obszarze roboczym **Grupy** można przeglądać informacje o stanie warunkowego dostępu do urządzeń.

Wybierz dowolną grupę urządzeń przenośnych. Następnie na karcie **Urządzenia**, w obszarze **Filtry** wybierz jedną z następujących opcji:

* **Urządzenia, które nie są zarejestrowane w usłudze AAD**: dostęp tych urządzeń do usługi Skype dla firm Online jest zablokowany.

* **Urządzenia, które nie są zgodne**: dostęp tych urządzeń do usługi Skype dla firm Online jest zablokowany.

* **Urządzenia, które są zarejestrowane w usłudze AAD i są zgodne**: te urządzenia mogą uzyskiwać dostęp do usługi Skype dla firm Online.

