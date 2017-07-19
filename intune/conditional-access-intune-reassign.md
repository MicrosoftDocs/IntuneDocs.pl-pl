---
title: "Przeprowadź migrację zasad dostępu warunkowego z portalu klasycznego usługi Intune do nowej witryny Azure Portal."
titleSuffix: Intune on Azure
description: "Przeprowadź migrację zasad dostępu warunkowego z portalu klasycznego usługi Intune do nowej witryny Azure Portal."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 301159ad-5f7e-4fcc-86c7-f72a71701ff4
ms.reviewer: chrisgree
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2450a878424d8c992a43e8028ba59b7136e1d530
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2017
---
# <a name="reassign-conditional-access-policies-from-intune-classic-portal-to-the-new-azure-portal"></a>Ponowne przypisywanie zasad dostępu warunkowego z portalu klasycznego usługi Intune do nowej witryny Azure Portal

W nowej witrynie Azure Portal dostęp warunkowy zapewnia obsługę wielu zasad na aplikację. Możliwe jest także dostosowywanie w szerszym zakresie.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Jeśli wszystko jest już gotowe do przejścia na nową witrynę Azure Portal, za pomocą poniższej procedury przypisz ponownie zasady dostępu warunkowego utworzone wcześniej w portalu klasycznym usługi Intune:

- Zgromadź zasady dostępu warunkowego utworzone wcześniej w portalu klasycznym usługi Intune, aby wiedzieć, które ustawienia trzeba będzie ponownie przypisać.

- Wykonaj kroki opisane w tym temacie, aby odtworzyć te zasady w nowej witrynie Azure Portal.

- Po sprawdzeniu, czy nowe zasady w nowej witrynie Azure Portal działają prawidłowo, wyłącz zasady dostępu warunkowego w konsoli klasycznej usługi Intune.
<br /><br />
    - **Przed wyłączeniem** zasad dostępu warunkowego w portalu klasycznym usługi Intune zaplanuj przeniesienie użytkowników, aby mogli korzystać z nowych zasad. Dostępne są dwie opcje:
<br /><br />
        - **Użyj tej samej grupy użytkowników uwzględnionych, która będzie objęta zasadami utworzonymi w nowej witrynie Azure Portal, i utwórz grupę użytkowników wykluczonych, która będzie używana z zasadami stosowanymi przez portal klasyczny usługi Intune**.
            - Stopniowo przenoś użytkowników do grupy wykluczonych określonej w portalu klasycznym.  Zapobiega to stosowaniu zasad przez portal klasyczny usługi Intune. Oprócz zasad stosowanych w portalu klasycznym usługi Intune stosowane są także zasady utworzone i przeznaczone dla tej samej grupy użytkowników w nowej witrynie Azure Portal. 
<br /><br />
        - **Utwórz nową grupę docelową dla zasad dostępu warunkowego w nowej witrynie Azure Portal**. Jeśli wybierzesz tę opcję, musisz wykonać następujące czynności:
            - Stopniowo usuwaj użytkowników z grup zabezpieczeń, które mają przypisane zasady dostępu warunkowego w portalu klasycznym usługi Intune.
            - Po sprawdzeniu, czy nowe zasady dla tych użytkowników działają, można je wyłączyć w portalu klasycznym usługi Intune. 
<br /><br />
- Jeśli ustawienia zasad dostępu warunkowego zostały skonfigurowane w portalu klasycznym usługi Intune do używania protokołu EAS (Exchange Active Sync), za pomocą [instrukcji w tym temacie](#to-reassign-intune-device-based-conditional-access-policies-for-eas-clients) **przypisz ponownie ustawienia zasad dostępu warunkowego EAS w nowej witrynie Azure Portal**.

### <a name="to-verify-your-device-based-conditional-access-policies-in-the-intune-classic-portal"></a>Aby zweryfikować w portalu klasycznym usługi Intune zasady dostępu warunkowego opartego na urządzeniach

1.  Przejdź do [portalu klasycznego usługi Intune](https://manage.microsoft.com) i zaloguj się przy użyciu swoich poświadczeń.

2.  Z menu po lewej stronie wybierz pozycję **Zasady**.

3.  Wybierz pozycję **Dostęp warunkowy**, a następnie wybierz usługi w chmurze firmy Microsoft (Exchange Online, SharePoint Online itp.), dla których zostały utworzone zasady dostępu warunkowego.

4.  Zanotuj ustawienia dostępu warunkowego i użyj tych notatek podczas tworzenia tych samych zasad dostępu warunkowego w nowej witrynie Azure Portal.

### <a name="app-and-device-based-conditional-access-policies-working-together"></a>Współdziałanie zasad dostępu warunkowego opartego na aplikacji i na urządzeniach

Blok **Intune App Protection** w nowej witrynie Azure Portal umożliwia administratorom konfigurowanie reguł warunkowych opartych na aplikacji. Umożliwia to udostępnienie zasobów firmowych tylko aplikacjom obsługującym zasady ochrony aplikacji w usłudze Intune. Można zdecydować, ze zasady dostępu warunkowego opartego na aplikacji mają być używane w połączeniu z zasadami dostępu warunkowego opartego na urządzeniach. Zasady dostępu warunkowego opartego na aplikacji i opartego na urządzeniach można połączyć (operator logiczny ORAZ) lub udostępnić jako opcje (operator logiczny LUB). Jeśli Twoje wymagania dotyczące zasad dostępu warunkowego:

- Wymagają zgodnego urządzenia **ORAZ** korzystają z zatwierdzonej aplikacji.
    - Należy skonfigurować zasady dostępu warunkowego za pomocą [bloku Dostęp warunkowy usługi Azure AD](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) i [bloku Intune App Protection](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).
<br /><br />
- Wymagają zgodnego urządzenia **LUB** korzystają z zatwierdzonej aplikacji.
    - Należy skonfigurować zasady dostępu warunkowego za pomocą [portalu klasycznego usługi Intune](https://manage.microsoft.com) i [bloku Intune App Protection](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).

> [!TIP] 
> W tym temacie przedstawiono zrzuty ekranu umożliwiające porównanie środowisko użytkownika w portalu klasycznym usługi Intune i nowej witrynie Azure Portal.

## <a name="to-re-assign-intune-device-based-conditional-access-policies"></a>Aby ponownie przypisać zdefiniowane w usłudze Intune zasady dostępu warunkowego opartego na urządzeniach

1. Przejdź do obszaru [Dostęp warunkowy w nowej witrynie Azure Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) i zaloguj się przy użyciu swoich poświadczeń.

2. Wybierz pozycję **Nowe zasady**.

3. Podaj nazwę zasad.

4. Wybierz pozycję **Użytkownicy i grupy** w sekcji **Przypisania**, aby wybrać użytkowników i grupy docelowe dla nowych zasad dostępu warunkowego.
    
    ![Porównanie interfejsu użytkownika przedstawiającego grupy użytkowników w portalu klasycznym usługi Intune i w nowej witrynie Azure Portal](./media/reassign-ca-1.png)

    > [!IMPORTANT] 
    > Jeśli w portalu klasycznym usługi Intune masz wybranych wszystkich użytkowników, wybierz pozycję Wszyscy użytkownicy. To samo dotyczy grup. Jeśli masz wybrane grupy, musisz **wybrać poszczególnych użytkowników i grupy**, aby uwzględnić te grupy. Oprócz tego, jeśli w portalu klasycznym usługi Intune była zaznaczona opcja **Wykluczone grupy**, musisz wykluczyć te grupy w nowej witrynie Azure Portal.

5. Po wybraniu grupy kliknij pozycję **Wybierz**, a następnie pozycję **Gotowe**.

6. Wybierz pozycję **Aplikacje w chmurze** dostępną w sekcji **Przypisania**.

7. W bloku **Aplikacje w chmurze** wybierz pozycję **Wybierz aplikacje**.

8. Wybierz aplikację, do której chcesz zastosować nowe zasady dostępu warunkowego, a następnie kliknij pozycję **Wybierz**.

9. Kliknij pozycję **Gotowe**.

    ![Porównanie interfejsu użytkownika przedstawiającego aplikacje w chmurze w portalu klasycznym usługi Intune i w nowej witrynie Azure Portal](./media/reassign-ca-3.png)

    > [!TIP] 
    > Jeśli masz wiele aplikacji objętych tymi samymi zasadami, rozważ połączenie ich w ramach jednego zestawu zasad w nowej witrynie Azure Portal.

10. Wybierz pozycję **Warunki** dostępną w sekcji **Przypisania**.

11. W bloku **Warunki** wybierz pozycję **Platformy urządzeń**, a następnie wybierz odpowiednie platformy urządzeń.

12. Po wybraniu platform urządzeń dwa razy kliknij pozycję **Gotowe**.

    ![Porównanie interfejsu użytkownika przedstawiającego platformy urządzeń w portalu klasycznym usługi Intune i w nowej witrynie Azure Portal](./media/reassign-ca-4.png)

    > [!TIP] 
    > Jeśli w portalu klasycznym usługi Intune wybrano poszczególne platformy, należy wybrać te poszczególne platformy w nowej witrynie Azure Portal.

    > [!NOTE] 
    > Później można określić opcję przyłączenia do domeny lub zgodności w systemie Windows.

13. Wybierz pozycję **Warunki** dostępną w sekcji **Przypisania**.

14. W bloku **Warunki** wybierz pozycję **Aplikacje klienckie**, a następnie wybierz odpowiednią aplikację kliencką.

15. Po wybraniu aplikacji klienckiej dwa razy kliknij pozycję **Gotowe**.

    ![Porównanie interfejsu użytkownika przedstawiającego aplikacje klienckie w portalu klasycznym usługi Intune i w nowej witrynie Azure Portal](./media/reassign-ca-6.png)

16. Jeśli w portalu klasycznym usługi Intune zostały wybrane ustawienia przeglądarki, zaznacz zarówno pozycję **Przeglądarka**, jak i pozycję **Aplikacje mobilne i klienci stacjonarni** w nowej witrynie Azure Portal. Jeśli w portalu klasycznym usługi Intune nie zostały wybrane ustawienia przeglądarki, zaznacz tylko pozycję **Aplikacje mobilne i klienci stacjonarni**. 

17. Wybierz pozycję **Udziel** dostępną w sekcji **Kontrole dostępu**.

18. Wybierz pozycję **Wymagaj, aby urządzenie było oznaczone jako zgodne** dostępną w sekcji **Udziel kontroli dostępu**, a następnie kliknij pozycję **Wybierz**.

19. Jeśli masz zasady, które wymagają przyłączonych do domeny urządzeń z systemem Windows, a oprócz tego obsługiwane są zgodne i zarejestrowane w usłudze Intune urządzenia z systemem Windows, wybierz pozycje **Wymagaj urządzenia połączonego z domeną** i **Wymagaj, aby urządzenie było oznaczone jako zgodne** oraz pozycję **Wymagaj jednej z wybranych kontrolek**.

20. Jeśli nie są dozwolone zgodne i zarejestrowane w usłudze Intune urządzenia z systemem Windows, wyklucz zasady dotyczące systemu Windows z obecnych zasad, a następnie utwórz osobne zasady, ustawiając dla pozycji **Platforma urządzeń** wartość **Windows**, uwzględnij inne warunki zgodnie z powyższymi informacjami i wybierz pozycję **Wymagaj urządzenia połączonego z domeną** dostępną w obszarze **Udziel kontroli dostępu**.

21. Włącz przełącznik **Włącz zasady** w bloku **Nowy** zasad dostępu warunkowego, a następnie kliknij pozycję **Utwórz**.

    ![Porównanie interfejsu użytkownika przedstawiającego włączanie dostępu warunkowego w portalu klasycznym usługi Intune i w nowej witrynie Azure Portal](./media/reassign-ca-11.png)

## <a name="to-reassign-intune-device-based-conditional-access-policies-for-eas-clients"></a>Aby ponownie przypisać dla klientów programu EAS zdefiniowane w usłudze Intune zasady dostępu warunkowego opartego na urządzeniach

Jeśli w ramach zasad dotyczących usługi Exchange Online skonfigurowano w portalu klasycznym usługi Intune ustawienia programu Exchange Active Sync (EAS), trzeba utworzyć drugi zestaw zasad dostępu warunkowego w nowej witrynie Azure Portal.

1. Przejdź do obszaru [Dostęp warunkowy w nowej witrynie Azure Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) i zaloguj się przy użyciu swoich poświadczeń.

2. Wybierz pozycję **Nowe zasady**.

3. Podaj nazwę zasad.

4. Wybierz pozycję **Użytkownicy i grupy** w sekcji **Przypisania**, aby wybrać użytkowników i grupy docelowe dla nowych zasad dostępu warunkowego.

    ![Porównanie interfejsu użytkownika przedstawiającego grupy użytkowników w portalu klasycznym usługi Intune i w nowej witrynie Azure Portal](./media/reassign-ca-12.png)

    > [!IMPORTANT] 
    > Jeśli w portalu klasycznym usługi Intune masz wybranych wszystkich użytkowników, wybierz pozycję Wszyscy użytkownicy. To samo dotyczy grup. Jeśli masz wybrane grupy, musisz **wybrać poszczególnych użytkowników i grupy**, aby uwzględnić te grupy. Oprócz tego, jeśli w portalu klasycznym usługi Intune była zaznaczona opcja **Wykluczone grupy**, musisz wykluczyć te grupy w nowej witrynie Azure Portal.

5. Po wybraniu grupy kliknij pozycję **Wybierz**, a następnie pozycję **Gotowe**.

6. Wybierz pozycję **Aplikacje w chmurze** dostępną w sekcji **Przypisania**.

7. W bloku **Aplikacje w chmurze** kliknij pozycję **Wybrane aplikacje**, wybierz pozycję **Exchange Online**, kliknij pozycję **Wybierz**, a następnie kliknij pozycję **Gotowe**.

    ![Porównanie interfejsu użytkownika przedstawiającego aplikacje w chmurze w portalu klasycznym usługi Intune i w nowej witrynie Azure Portal](./media/reassign-ca-14.png)

    > [!IMPORTANT] 
    > Zasady dostępu warunkowego dla klientów programu EAS nie mogą obejmować żadnej innej aplikacji w chmurze.

8. W bloku **Warunki** wybierz pozycję **Aplikacje klienckie**, a następnie wybierz odpowiednią aplikację kliencką. Jeśli wybrano blokowanie klientów nieobsługiwanych przez usługę Intune, użyj opcji **Zastosuj zasady tylko do obsługiwanych platform**.

    ![Porównanie interfejsu użytkownika przedstawiającego aplikacje klienckie w portalu klasycznym usługi Intune i w nowej witrynie Azure Portal](./media/reassign-ca-15.png)

9. Po wybraniu aplikacji klienckiej dwa razy kliknij pozycję **Gotowe**.

10. Wybierz pozycję **Udziel** dostępną w sekcji **Kontrole dostępu**.

11. Wybierz pozycję **Wymagaj, aby urządzenie było oznaczone jako zgodne** dostępną w sekcji **Udziel kontroli dostępu**, a następnie kliknij pozycję **Wybierz**.

    ![Porównanie interfejsu użytkownika przedstawiającego udzielanie dostępu w portalu klasycznym usługi Intune i w nowej witrynie Azure Portal](./media/reassign-ca-16.png)

12. Włącz przełącznik **Włącz zasady** w bloku **Nowy** zasad dostępu warunkowego, a następnie kliknij pozycję **Utwórz**.

    ![Porównanie interfejsu użytkownika przedstawiającego włączanie dostępu warunkowego w portalu klasycznym usługi Intune i w nowej witrynie Azure Portal](./media/reassign-ca-17.png)

## <a name="disable-conditional-access-policies-in-the-intune-classic-portal"></a>Wyłączanie zasad dostępu warunkowego w portalu klasycznym usługi Intune
### <a name="before-you-start"></a>Przed rozpoczęciem

Jeśli zasady dostępu warunkowego zostały już ponownie przypisane w nowej witrynie Azure Portal, należy stopniowo wyłączać zasady dostępu warunkowego utworzone wcześniej w portalu klasycznym usługi Intune. Ponadto może być konieczne użycie tej samej grupy zabezpieczeń w celu zastosowania zasad dostępu warunkowego utworzonych w nowej witrynie Azure Portal.

- Przed wyłączeniem zasad dostępu warunkowego w portalu klasycznym usługi Intune zobacz sekcję [Przed rozpoczęciem](#before-you-begin) dostępną na początku tego tematu.

### <a name="to-disable-the-conditional-access-policies"></a>Aby wyłączyć zasady dostępu warunkowego

1.  Przejdź do [portalu klasycznego usługi Intune](https://manage.microsoft.com) i zaloguj się przy użyciu swoich poświadczeń.

2.  Z menu po lewej stronie wybierz pozycję **Zasady**.

3.  Wybierz pozycję **Dostęp warunkowy**, a następnie wybierz usługi w chmurze firmy Microsoft (Exchange Online, SharePoint Online itp.), dla których zostały utworzone zasady dostępu warunkowego.

4.  Usuń zaznaczenie opcji **Włącz zasady dostępu warunkowego**, a następnie kliknij pozycję **Zapisz**.

    ![Wyłączanie zasad dostępu warunkowego w portalu klasycznym usługi Intune](./media/reassign-ca-18.png)

## <a name="see-also"></a>Zobacz także

- [Typowe sposoby korzystania z dostępu warunkowego przy użyciu usługi Intune](conditional-access-intune-common-ways-use.md)
- [Dostęp warunkowy oparty na aplikacji z użyciem usługi Intune](app-based-conditional-access-intune.md)
- [Dostęp warunkowy w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)