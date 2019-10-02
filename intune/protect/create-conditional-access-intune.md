---
title: Konfigurowanie dostępu warunkowego opartego na urządzeniach przy użyciu usługi Intune
titleSuffix: Microsoft Intune
description: Dowiedz się, jak utworzyć zasady dostępu warunkowego opartego na urządzeniach na podstawie zgodności urządzeń usługi Microsoft Intune i zarządzania aplikacjami mobilnymi.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e27997b45f0a68f6eb9247c69fafc363787fb457
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71722595"
---
# <a name="create-a-device-based-conditional-access-policy"></a>Tworzenie zasad dostępu warunkowego opartego na urządzeniach

Usługa Intune umożliwia rozszerzenie dostępu warunkowego w usłudze Azure Active Directory przez dodanie zgodności urządzeń przenośnych do metod kontroli dostępu. Po utworzeniu zasad zgodności usługi Intune, które definiują wymagania dotyczące zgodności urządzeń, można użyć stanu zgodności urządzenia do zezwolenia na dostęp do aplikacji i usług lub do zablokowania tego dostępu. W tym celu można utworzyć zasady dostępu warunkowego, które używają ustawienia **Wymagaj, aby urządzenie było oznaczone jako zgodne**.  

Zasady dostępu warunkowego określają aplikację lub usługi, które chcesz chronić, warunki uzyskiwania dostępu do aplikacji lub usług oraz użytkowników, w przypadku których zasady mają zastosowanie. Dostęp warunkowy to funkcja usługi Azure AD w wersji Premium, którą można skonfigurować w usłudze Azure Active Directory. Te same zasady można jednak skonfigurować w portalu usługi Intune. Węzeł Dostęp warunkowy dostępny z usługi *Intune* jest tym samym węzłem, do którego dostęp jest uzyskiwany z usługi *Azure AD*.  

> [!IMPORTANT]
> Przed skonfigurowaniem dostępu warunkowego należy skonfigurować zasady zgodności urządzeń usługi Intune, które będą oceniać, czy urządzenia spełniają określone wymagania. Zobacz [Wprowadzenie do zasad zgodności urządzeń w usłudze Intune](device-compliance-get-started.md).

## <a name="create-conditional-access-policy"></a>Tworzenie zasad dostępu warunkowego

1. W portalu usługi Intune wybierz kolejno pozycje **Dostęp warunkowy** > **Zasady** > **Nowe zasady**.
   
    ![Tworzenie nowych zasad dostępu warunkowego](./media/create-conditional-access-intune/create-ca.png)
 
2. W obszarze **Przypisania** wybierz pozycję **Użytkownicy i grupy**. 
3. Na karcie **Dołączanie** wskaż użytkowników lub grupy, których mają dotyczyć zasady dostępu warunkowego. Po wybraniu osób można użyć karty **Wykluczanie**, jeśli istnieją użytkownicy, role lub grupy do wykluczenia z tych zasad.  
    - **Wszyscy użytkownicy**: wybierz tę opcję, aby zastosować zasady do wszystkich użytkowników i grup, w tym do użytkowników wewnętrznych i gości.
  
    - **Wybierz użytkowników i grupy**: wybierz tę opcję i określ co najmniej jedną z następujących opcji:
  
      a. **Wszyscy użytkownicy-goście**: wybierz tę opcję, aby dołączyć lub wykluczyć zewnętrznych użytkowników-gości (na przykład partnerów i współpracowników zewnętrznych).
       
      b. **Role katalogu**: wybierz co najmniej jedną rolę usługi Azure AD w celu dołączenia lub wykluczenia użytkowników, do których przypisano te role.
      
      c. **Użytkownicy i grupy**: wybierz tę opcję, aby wyszukać i wybrać konkretnych użytkowników lub konkretne grupy do dołączenia lub wykluczenia.
     
       > [!TIP]  
       > Przetestuj zasady w mniejszej grupie użytkowników, aby upewnić się, że działają zgodnie z oczekiwaniami.
4. Wybierz pozycję **Gotowe**.
5. W obszarze **Przypisania** wybierz pozycję **Aplikacje w chmurze**. 
6. Na karcie **Dołączanie** zidentyfikuj aplikacje i usługi, które chcesz chronić za pomocą zasad dostępu warunkowego. Następnie możesz użyć karty **Wykluczanie**, jeśli istnieją aplikacje lub usługi, które chcesz wykluczyć z tych zasad.
    - **Wszystkie aplikacje w chmurze**: wybierz tę opcję, aby zastosować zasady do wszystkich aplikacji.
      > [!IMPORTANT]  
      > Na tej liście znajduje się aplikacja Microsoft Azure Management służąca do uzyskiwania dostępu do witryny Azure Portal. Pamiętaj, aby użyć karty **Wykluczanie** w tym miejscu lub w obszarze opcji **Użytkownicy i grupy** w celu upewnienia się, że użytkownik (albo wyznaczeni użytkownicy lub grupy) będzie mógł zalogować się do witryny Azure Portal. 

    - **Wybierz aplikacje**: wybierz tę opcję, wybierz pozycję **Wybierz**, a następnie wyszukaj i wybierz aplikacje lub usługi do objęcia ochroną na liście aplikacji.
    
      ![Tworzenie nowych zasad dostępu warunkowego](./media/create-conditional-access-intune/create-ca-select-apps.png)

7. Wybierz pozycję **Gotowe**.
8. W obszarze **Przypisania** wybierz pozycję **Warunki**.
    - **Ryzyko logowania**: wybierz pozycję Tak, aby wraz z tym zasadami używać funkcji wykrywania ryzyka logowania usługi Azure AD Identity Protection, a następnie wybierz poziomy ryzyka logowania, do których będą stosowane zasady.
    - **Platformy urządzeń**: Na karcie **Dołączanie** zidentyfikuj platformy urządzeń, do których mają zostać zastosowane te zasady dostępu warunkowego. Użyj karty **Wykluczanie**, aby wykluczyć platformy z tych zasad.
    - **Lokalizacje**: Na karcie **Dołączanie** określ, czy zasady mają zastosowanie do dowolnej lokalizacji, zaufanych lokalizacji sieciowych kontrolowanych przez dział IT lub określonych lokalizacji sieciowych. Użyj karty **Wykluczanie**, aby wykluczyć lokalizacje sieciowe z tych zasad. 
    - **Aplikacje klienckie**: wybierz pozycję **Tak**, aby określić, czy zasady powinny być stosowane względem aplikacji przeglądarki, aplikacji mobilnych i klientów stacjonarnych. Możesz również wybrać pozycję **Nowocześni klienci uwierzytelniania** (np. program Outlook dla systemu iOS lub program Outlook dla systemu Android) oraz pozycję **Klienci programu Exchange ActiveSync**.
    - **Stan urządzenia**: zasady dostępu warunkowego będą stosowane do wszystkich stanów urządzeń, chyba że wybierzesz pozycję Tak i wykluczysz stany Urządzenie dołączone do hybrydowej usługi Azure AD albo Urządzenie oznaczone jako zgodne (lub obydwa).
    
      ![Tworzenie nowych zasad dostępu warunkowego](./media/create-conditional-access-intune/create-ca-device-platforms.png)

      > [!TIP]  
      > Jeśli chcesz chronić **nowoczesnych klientów uwierzytelniania** i **klientów programu Exchange ActiveSync**, utwórz dwie oddzielne zasady dostępu warunkowego, jedną dla każdego typu klienta. Mimo że program Exchange ActiveSync obsługuje nowoczesne uwierzytelnianie, jedynym warunkiem obsługiwanym przez program Exchange ActiveSync jest platforma. Inne warunki, w tym uwierzytelnianie wieloskładnikowe, nie są obsługiwane. Aby skutecznie chronić dostęp do usługi Exchange Online z programu Exchange ActiveSync, utwórz zasady dostępu warunkowego określające aplikację w chmurze Office 365 Exchange Online i aplikację kliencką programu Exchange ActiveSync z wybraną opcją Zastosuj zasady tylko do obsługiwanych platform.

9. Wybierz pozycję **Gotowe**.
10. W obszarze **Kontrole dostępu** wybierz pozycję **Udziel**. Skonfiguruj zachowanie w zależności od skonfigurowanych warunków.  Możesz wybrać jedną z następujących opcji:
    - **Blokuj dostęp**: w przypadku użytkowników określonych w zasadach nastąpi odmowa dostępu do aplikacji zgodnie z określonymi przez Ciebie warunkami.
    - **Udziel dostępu**: użytkownicy określeni w ramach tych zasad otrzymują prawa dostępu, ale możesz wymagać wykonania dowolnych spośród następujących dodatkowych czynności:
      - **Wymagaj uwierzytelniania wieloskładnikowego**: użytkownik musi spełnić dodatkowe wymagania dotyczące zabezpieczeń, takie jak rozmowa telefoniczna lub wiadomość tekstowa.
      - **Wymagaj, aby urządzenie było oznaczone jako zgodne**: urządzenie musi być zgodne z usługą Intune. Jeśli urządzenie jest niezgodne, użytkownik będzie mieć możliwość zarejestrowania go w usłudze Intune. 
      - **Wymagaj urządzenia dołączonego do hybrydowej usługi Azure AD**: urządzenia muszą być dołączone do hybrydowej usługi Azure AD.
      - **Wymagaj zatwierdzonej aplikacji klienckiej**: urządzenie musi używać tych zatwierdzonych aplikacji klienckich. 
      - **W przypadku wielu opcji kontroli**: wybierz pozycję **Wymagaj wszystkich wybranych opcji kontroli** tak, aby wszystkie powyższe wymagania były wymuszane, gdy urządzenie spróbuje uzyskać dostęp do aplikacji.
    
      ![Kontrole dostępu — ustawienia udzielania dostępu](./media/create-conditional-access-intune/create-ca-grant-access-settings.png)
 
11. W obszarze **Włącz zasady** wybierz pozycję **na**.
     
     ![Włączanie zasad](./media/create-conditional-access-intune/enable-policy.png)

12. Wybierz przycisk **Utwórz**.

## <a name="see-also"></a>Zobacz także
[Dostęp warunkowy oparty na aplikacji z użyciem usługi Intune](app-based-conditional-access-intune.md)

[Troubleshooting Intune conditional access](https://support.microsoft.com/help/4456106) (Rozwiązywanie problemów z dostępem warunkowym w usłudze Intune)
