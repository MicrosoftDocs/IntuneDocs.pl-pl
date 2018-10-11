---
title: Migracja dostępu warunkowego do witryny Azure Portal
titlesuffix: Microsoft Intune
description: Ponowne przypisywanie zasad dostępu warunkowego utworzonych wcześniej w klasycznym portalu usługi Intune do witryny Azure Portal.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 301159ad-5f7e-4fcc-86c7-f72a71701ff4
ms.reviewer: chrisgree
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 00c657700cd8c27e4758b9cc94292ba83b2db3cd
ms.sourcegitcommit: fffa64f28278573dc83a846b647315def2108781
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2018
ms.locfileid: "48231716"
---
# <a name="reassign-conditional-access-policies-from-intune-classic-portal-to-the-azure-portal"></a>Ponowne przypisywanie zasad dostępu warunkowego z klasycznego portalu usługi Intune do witryny Azure Portal

W nowej witrynie Azure Portal dostęp warunkowy zapewnia obsługę wielu zasad na aplikację. Możliwe jest także dostosowywanie w szerszym zakresie. Jeśli wcześniej utworzono zasady dostępu warunkowego w klasycznym portalu usługi Intune, można migrować je do witryny Azure Portal. 

## <a name="before-you-begin"></a>Przed rozpoczęciem

Jeśli wszystko jest już gotowe do przejścia na witrynę Azure Portal, wykonaj czynności przedstawione w tym temacie, aby ponownie przypisać zasady dostępu warunkowego utworzone wcześniej w klasycznym portalu usługi Intune:

- Zgromadź wcześniej utworzone zasady dostępu warunkowego, aby wiedzieć, które ustawienia trzeba będzie później ponownie przypisać.

- Wykonaj kroki opisane w tym temacie, aby ponownie utworzyć te zasady w witrynie Azure Portal.

- Po sprawdzeniu, czy nowe zasady w witrynie Azure Portal działają prawidłowo, wyłącz zasady dostępu warunkowego w portalu klasycznym usługi Intune.
<br /><br />
    - **Przed wyłączeniem** zasad dostępu warunkowego w portalu klasycznym usługi Intune zaplanuj przeniesienie użytkowników, aby mogli korzystać z nowych zasad. Dostępne są dwie opcje:
<br /><br />
        - **Użyj tej samej grupy użytkowników uwzględnionych, która będzie objęta zasadami utworzonymi w witrynie Azure Portal, i utwórz grupę użytkowników wykluczonych, która będzie używana z zasadami stosowanymi przez klasyczny portal usługi Intune**.
            - Stopniowo przenoś użytkowników do grupy wykluczonych określonej w portalu klasycznym. Zapobiega to stosowaniu zasad przez klasyczny portal usługi Intune. Oprócz zasad stosowanych w klasycznym portalu usługi Intune stosowane są także zasady utworzone i przeznaczone dla tej samej grupy użytkowników w witrynie Azure Portal. 
<br /><br />
        - **Utwórz nową grupę docelową dla zasad dostępu warunkowego w witrynie Azure Portal**. Jeśli wybierzesz tę opcję, musisz wykonać następujące czynności:
            - Stopniowo usuwaj użytkowników z grup zabezpieczeń, które mają przypisane zasady dostępu warunkowego w portalu klasycznym usługi Intune.
            - Po sprawdzeniu, czy nowe zasady dla tych użytkowników działają, można je wyłączyć w portalu klasycznym usługi Intune. 
<br /><br />
- Jeśli ustawienia zasad dostępu warunkowego zostały skonfigurowane w portalu klasycznym usługi Intune do używania protokołu EAS (Exchange ActiveSync), za pomocą [instrukcji w tym temacie](#to-reassign-intune-device-based-conditional-access-policies-for-eas-clients) **przypisz ponownie ustawienia zasad dostępu warunkowego EAS w witrynie Azure Portal**.

### <a name="to-verify-your-device-based-conditional-access-policies-in-the-intune-classic-portal"></a>Aby zweryfikować w portalu klasycznym usługi Intune zasady dostępu warunkowego opartego na urządzeniach

1.  Przejdź do [portalu klasycznego usługi Intune](https://manage.microsoft.com) i zaloguj się przy użyciu swoich poświadczeń.

2.  Z menu po lewej stronie wybierz pozycję **Zasady**.

3.  Wybierz pozycję **Dostęp warunkowy**, a następnie wybierz usługi w chmurze firmy Microsoft (na przykład Exchange Online lub SharePoint Online), dla których zostały utworzone zasady dostępu warunkowego.

4.  Zanotuj ustawienia dostępu warunkowego i użyj ich podczas tworzenia tych samych zasad dostępu warunkowego w witrynie Azure Portal.

### <a name="app-and-device-based-conditional-access-policies-working-together"></a>Współdziałanie zasad dostępu warunkowego opartego na aplikacji i na urządzeniach

Blok **Intune App Protection** w witrynie Azure Portal umożliwia administratorom konfigurowanie reguł warunkowych opartych na aplikacji. Umożliwia to udostępnienie zasobów firmowych tylko aplikacjom obsługującym zasady ochrony aplikacji w usłudze Intune. Można zdecydować, ze zasady dostępu warunkowego opartego na aplikacji mają być używane w połączeniu z zasadami dostępu warunkowego opartego na urządzeniach. Zasady dostępu warunkowego opartego na aplikacji i opartego na urządzeniach można połączyć (operator logiczny ORAZ) lub udostępnić jako opcje (operator logiczny LUB). Jeśli Twoje wymagania dotyczące zasad dostępu warunkowego:

- Wymagają zgodnego urządzenia **ORAZ** korzystają z zatwierdzonej aplikacji.
    - Należy skonfigurować zasady dostępu warunkowego za pomocą [bloku dostępu warunkowego usługi Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) i [bloku Intune App Protection](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).
<br /><br />
- Wymagają zgodnego urządzenia **LUB** korzystają z zatwierdzonej aplikacji.
    - Należy skonfigurować zasady dostępu warunkowego za pomocą [portalu klasycznego usługi Intune](https://manage.microsoft.com) i [bloku Intune App Protection](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).

> [!TIP] 
> W tym temacie przedstawiono zrzuty ekranu umożliwiające porównanie środowiska użytkownika w portalu klasycznym usługi Intune i witrynie Azure Portal.

## <a name="reassign-intune-device-based-conditional-access-policies"></a>Ponowne przypisywanie zdefiniowanych w usłudze Intune zasad dostępu warunkowego opartego na urządzeniach

1. Przejdź do obszaru [Dostęp warunkowy w witrynie Azure Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) i zaloguj się przy użyciu swoich poświadczeń.

2. Wybierz pozycję **Nowe zasady**.

3. Podaj nazwę zasad.

4. W sekcji **Przypisania** wybierz pozycję **Użytkownicy i grupy**, aby wybrać użytkowników i grupy docelowe dla nowych zasad dostępu warunkowego.
    
    ![Obraz przedstawiający porównanie interfejsu użytkownika grup użytkowników w portalu usługi Intune i witrynie Azure Portal](./media/reassign-ca-1.png)

    > [!IMPORTANT] 
    > Wybór w witrynie Azure Portal powinien odpowiadać wyborowi w portalu klasycznym. Na przykład jeśli w portalu klasycznym usługi Intune masz wybranych wszystkich użytkowników, wybierz pozycję **Wszyscy użytkownicy** w witrynie Azure Portal. Oprócz tego, jeśli w portalu klasycznym usługi Intune była zaznaczona opcja **Wykluczone grupy**, musisz także wykluczyć te grupy w witrynie Azure Portal.

5. Po wybraniu grupy kliknij pozycję **Wybierz**, a następnie kliknij pozycję **Gotowe**.

6. W sekcji **Przypisania** wybierz pozycję **Aplikacje w chmurze**.

7. W bloku **Aplikacje w chmurze** wybierz pozycję **Wybierz aplikacje**.

8. Wybierz aplikację, do której chcesz zastosować nowe zasady dostępu warunkowego, a następnie kliknij pozycję **Wybierz**.

9. Kliknij pozycję **Gotowe**.

    ![Obraz przedstawiający porównanie interfejsu użytkownika aplikacji w chmurze w portalu usługi Intune i witrynie Azure Portal](./media/reassign-ca-3.png)

    > [!TIP] 
    > Jeśli masz wiele aplikacji objętych tymi samymi zasadami, rozważ połączenie ich w jeden zestaw zasad w witrynie Azure Portal.

10. W sekcji **Przypisania** wybierz pozycję **Warunki**.

11. W bloku **Warunki** wybierz pozycję **Platformy urządzeń**, a następnie wybierz odpowiednie platformy urządzeń.

12. Po wybraniu platform urządzeń dwa razy kliknij pozycję **Gotowe**.

    ![Obraz przedstawiający porównanie interfejsu użytkownika platform urządzeń w portalu usługi Intune i witrynie Azure Portal](./media/reassign-ca-4.png)

    > [!TIP] 
    > Jeśli w portalu klasycznym usługi Intune wybrano poszczególne platformy, należy wybrać te poszczególne platformy w witrynie Azure Portal.

    > [!NOTE] 
    > Później można określić opcję przyłączenia do domeny lub zgodności w systemie Windows.

13. W sekcji **Przypisania** wybierz pozycję **Warunki**.

14. W bloku **Warunki** wybierz pozycję **Aplikacje klienckie**, a następnie wybierz odpowiednią aplikację kliencką.

15. Po wybraniu aplikacji klienckiej kliknij dwa razy pozycję **Gotowe**.

    ![Obraz przedstawiający porównanie interfejsu użytkownika aplikacji klienckiej w portalu usługi Intune i witrynie Azure Portal](./media/reassign-ca-6.png)

16. Jeśli w portalu klasycznym usługi Intune zostały wybrane ustawienia przeglądarki, zaznacz zarówno pozycję **Przeglądarka**, jak i pozycję **Aplikacje mobilne i klienci stacjonarni** w witrynie Azure Portal. Jeśli w portalu klasycznym usługi Intune nie zostały wybrane ustawienia przeglądarki, zaznacz tylko pozycję **Aplikacje mobilne i klienci stacjonarni**. 

17. W sekcji **Kontrole dostępu** wybierz pozycję **Udziel**.

18. W sekcji **Udziel kontroli dostępu** wybierz pozycję **Wymagaj, aby urządzenie było oznaczone jako zgodne**, a następnie kliknij pozycję **Wybierz**.

19. Jeśli masz zasady, które wymagają przyłączonych do domeny urządzeń z systemem Windows, a oprócz tego obsługiwane są zgodne i zarejestrowane w usłudze Intune urządzenia z systemem Windows, wybierz pozycje **Wymagaj urządzenia połączonego z domeną** i **Wymagaj, aby urządzenie było oznaczone jako zgodne** oraz pozycję **Wymagaj jednej z wybranych kontrolek**.

20. Jeśli zgodne i zarejestrowane w usłudze Intune urządzenia z systemem Windows nie są dozwolone, wyklucz zasady dotyczące systemu Windows z obecnych zasad. Następnie utwórz osobne zasady, ustawiając dla pozycji **Platformy urządzeń** wartość **Windows**, uwzględnij inne warunki zgodnie z powyższymi informacjami i wybierz pozycję **Wymagaj urządzenia połączonego z domeną** dostępną w obszarze **Udziel kontroli dostępu**.

21. W bloku **Nowy** zasad dostępu warunkowego włącz przełącznik **Włącz zasady**, a następnie kliknij pozycję **Utwórz**.

    ![Obraz przedstawiający porównanie interfejsu użytkownika dla włączania zasad dostępu warunkowego w portalu usługi Intune i w witrynie Azure Portal](./media/reassign-ca-11.png)

## <a name="reassign-intune-device-based-conditional-access-policies-for-eas-clients"></a>Ponowne przypisywanie zdefiniowanych w usłudze Intune zasad dostępu warunkowego opartego na urządzeniach dla klientów programu EAS

Jeśli w ramach zasad dotyczących usługi Exchange Online skonfigurowano w portalu klasycznym usługi Intune ustawienia programu Exchange ActiveSync, trzeba utworzyć drugi zestaw zasad dostępu warunkowego w witrynie Azure Portal.

1. Przejdź do obszaru [Dostęp warunkowy w witrynie Azure Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) i zaloguj się przy użyciu swoich poświadczeń.

2. Wybierz pozycję **Nowe zasady**.

3. Podaj nazwę zasad.

4. W sekcji **Przypisania** wybierz pozycję **Użytkownicy i grupy**, aby wybrać użytkowników i grupy docelowe dla nowych zasad dostępu warunkowego.

    ![Obraz przedstawiający porównanie interfejsu użytkownika grup użytkowników w portalu usługi Intune i witrynie Azure Portal](./media/reassign-ca-12.png)

    > [!IMPORTANT] 
    > Wybór dokonany dla witryny Azure Portal powinien odpowiadać wyborowi dokonanemu dla witryny Azure Portal. Na przykład jeśli w portalu klasycznym usługi Intune masz wybranych wszystkich użytkowników, wybierz pozycję **Wszyscy użytkownicy** w witrynie Azure Portal. Oprócz tego, jeśli w portalu klasycznym usługi Intune była zaznaczona opcja **Wykluczone grupy**, musisz także wykluczyć te grupy w witrynie Azure Portal.

5. Po wybraniu grupy kliknij pozycję **Wybierz**, a następnie kliknij pozycję **Gotowe**.

6. W sekcji **Przypisania** wybierz pozycję **Aplikacje w chmurze**.

7. W bloku **Aplikacje w chmurze** kliknij pozycję **Wybierz aplikacje**, a następnie wybierz pozycję **Exchange Online**. Następnie kliknij pozycję **Wybierz** i pozycję **Gotowe**.

    ![Obraz przedstawiający porównanie interfejsu użytkownika aplikacji w chmurze w portalu usługi Intune i witrynie Azure Portal](./media/reassign-ca-14.png)

    > [!IMPORTANT] 
    > Zasady dostępu warunkowego dla klientów programu EAS nie mogą obejmować żadnej innej aplikacji w chmurze.

8. W bloku **Warunki** wybierz pozycję **Aplikacje klienckie**, a następnie wybierz odpowiednią aplikację kliencką. Jeśli wybrano blokowanie klientów nieobsługiwanych przez usługę Intune, użyj opcji **Zastosuj zasady tylko do obsługiwanych platform**.

    ![Obraz przedstawiający porównanie interfejsu użytkownika aplikacji klienckiej w portalu usługi Intune i witrynie Azure Portal](./media/reassign-ca-15.png)

9. Po wybraniu aplikacji klienckiej kliknij dwa razy pozycję **Gotowe**.

10. W sekcji **Kontrole dostępu** wybierz pozycję **Udziel**.

11. W sekcji **Udziel kontroli dostępu** wybierz pozycję **Wymagaj, aby urządzenie było oznaczone jako zgodne**, a następnie kliknij pozycję **Wybierz**.

    ![Obraz przedstawiający porównanie interfejsu użytkownika udzielania dostępu w portalu usługi Intune i witrynie Azure Portal](./media/reassign-ca-16.png)

12. W bloku **Nowy** zasad dostępu warunkowego włącz przełącznik **Włącz zasady**, a następnie kliknij pozycję **Utwórz**.

    ![Obraz przedstawiający porównanie interfejsu użytkownika dla włączania zasad dostępu warunkowego w portalu usługi Intune i w witrynie Azure Portal](./media/reassign-ca-17.png)

> [!NOTE]
> Jeśli skonfigurujesz opcję **Platformy urządzeń**, próba zapisania zasad zakończy się niepowodzeniem z powodu błędu „Konfiguracja zasad nie jest obsługiwana”. Program Exchange ActiveSync nie może zidentyfikować platformy używanej przez łączące się urządzenie. W związku z tym w przypadku tworzenia zasad dla urządzeń z programem Exchange ActiveSync konfigurowanie konkretnych platform urządzeń nie jest obsługiwane.

## <a name="disable-conditional-access-policies-in-the-intune-classic-portal"></a>Wyłączanie zasad dostępu warunkowego w portalu klasycznym usługi Intune

Po ponownym przypisaniu zasad dostępu warunkowego w witrynie Azure Portal należy stopniowo wyłączać zasady dostępu warunkowego utworzone wcześniej w portalu klasycznym usługi Intune. Ponadto może być konieczne użycie tej samej grupy zabezpieczeń w celu zastosowania zasad dostępu warunkowego utworzonych w witrynie Azure Portal.

> [!NOTE]
> Przed wyłączeniem zasad dostępu warunkowego w portalu klasycznym usługi Intune zobacz sekcję [Przed rozpoczęciem](#before-you-begin) dostępną na początku tego tematu.

### <a name="to-disable-the-conditional-access-policies"></a>Aby wyłączyć zasady dostępu warunkowego

1.  Przejdź do [portalu klasycznego usługi Intune](https://manage.microsoft.com) i zaloguj się przy użyciu swoich poświadczeń.

2.  Z menu po lewej stronie wybierz pozycję **Zasady**.

3.  Wybierz pozycję **Dostęp warunkowy**, a następnie wybierz usługi w chmurze firmy Microsoft (na przykład Exchange Online lub SharePoint Online), dla których zostały utworzone zasady dostępu warunkowego.

4.  Usuń zaznaczenie opcji **Włącz zasady dostępu warunkowego**, a następnie kliknij pozycję **Zapisz**.

    ![Obraz przedstawiający wyłączanie zasad dostępu warunkowego w portalu klasycznym usługi Intune](./media/reassign-ca-18.png)

## <a name="see-also"></a>Zobacz też

- [Typowe sposoby korzystania z dostępu warunkowego przy użyciu usługi Intune](conditional-access-intune-common-ways-use.md)
- [Dostęp warunkowy oparty na aplikacji z użyciem usługi Intune](app-based-conditional-access-intune.md)
- [Dostęp warunkowy w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
