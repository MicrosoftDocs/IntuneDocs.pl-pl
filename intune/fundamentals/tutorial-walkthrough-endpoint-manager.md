---
title: Samouczek — Prezentacja usługi Intune w usłudze Microsoft Endpoint Manager
titleSuffix: Microsoft Intune
description: W tym samouczku poznasz usługę Microsoft Intune za pomocą centrum administracyjnego usługi Microsoft Endpoint Manager i dowiesz się, jak wykonywać zadania.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/06/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
Customer intent: As an Intune admin, I want to learn where to find the different features in Intune from the Microsoft Endpoint Manager admin center.
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1d8950e57c2427c522d337807d315ed5c399c0d5
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514085"
---
# <a name="tutorial-walkthrough-intune-in-microsoft-endpoint-manager"></a>Samouczek: Prezentacja usługi Intune w usłudze Microsoft Endpoint Manager

Platforma [Azure](https://docs.microsoft.com/learn/modules/welcome-to-azure) zawiera ponad 100 usług, które ułatwiają pracę dzięki różnym możliwościom i scenariuszom przetwarzania w chmurze. Microsoft Intune jest jedną z kilku usług dostępnych na platformie Azure. Usługa Intune pomaga zapewnić, że urządzenia, aplikacje i dane firmowe spełniają wymagania dotyczące zabezpieczeń. Możesz kontrolować, które wymagania mają być sprawdzane, i co ma się stać, gdy te wymagania nie zostaną spełnione. W [centrum administracyjnym usługi Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) możesz znaleźć usługę Microsoft Intune, a także inne ustawienia związane z zarządzaniem urządzeniami. Zrozumienie funkcji dostępnych w usłudze Intune pomoże Ci w wykonywaniu różnych zadań dotyczących zarządzania urządzeniami mobilnymi (MDM) i zarządzania aplikacjami mobilnymi (MAM).

> [!NOTE]
> Microsoft Endpoint Manager to pojedyncza, zintegrowana platforma zarządzania punktami końcowymi służąca do zarządzania wszystkimi punktami końcowymi. To centrum administracyjne programu Microsoft Endpoint Manager integruje program ConfigMgr i usługę Microsoft Intune.

W tym samouczku wykonasz następujące czynności:
> [!div class="checklist"]
> * Przewodnik po centrum administracyjnym usługi Microsoft Endpoint Manager
> * Dostosuj widok centrum administracyjnego usługi Microsoft Endpoint Manager

Jeśli nie masz subskrypcji usługi Intune, [utwórz konto bezpłatnej wersji próbnej](free-trial-sign-up.md).

## <a name="prerequisites"></a>Wymagania wstępne
Przed skonfigurowaniem usługi Microsoft Intune przejrzyj poniższe wymagania:

- [Obsługiwane systemy operacyjne i przeglądarki](../supported-devices-browsers.md) 
- [Przepustowość i wymagania dotyczące konfiguracji sieci](../network-bandwidth-use.md)

## <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Rejestrowanie w celu skorzystania z bezpłatnej wersji próbnej usługi Microsoft Intune

Usługę Intune można bezpłatnie testować przez 30 dni. Jeśli masz już konto firmowe, **zaloguj się** przy użyciu tego konta i dodaj usługę Intune do swojej subskrypcji. W przeciwnym razie [utwórz konto bezpłatnej wersji próbnej](free-trial-sign-up.md), aby móc korzystać z usługi Intune w swojej organizacji.

> [!IMPORTANT]
> Nie można połączyć istniejącego konta służbowego lub edukacyjnego po zarejestrowaniu nowego konta.

## <a name="tour-microsoft-intune-in-the-microsoft-endpoint-manager-admin-center"></a>Przewodnik dla usługi Microsoft Intune w centrum administracyjnym usługi Microsoft Endpoint Manager

Postępuj zgodnie z poniższymi instrukcjami, aby lepiej zrozumieć usługę Intune dostępną w centrum administracyjnym usługi Microsoft Endpoint Manager. Po ukończeniu prezentacji będziesz mieć lepsze zrozumienie niektórych głównych obszarów usługi Intune.

1. Otwórz przeglądarkę i zaloguj się do [centrum administracyjnego usługi Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431). Jeśli jesteś nowym użytkownikiem usługi Intune, użyj subskrypcji bezpłatnej wersji próbnej.

    ![Zrzut ekranu przedstawiający centrum administracyjne usługi Microsoft Endpoint Manager — Strona główna](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-01.png)

    Gdy otworzysz usługę Microsoft Endpoint Manager lub inną usługę na platformie Azure, usługa zostanie wyświetlona w okienku. Niektóre z pierwszych obciążeń, których możesz użyć w usłudze Intune, to **Urządzenia**, **Aplikacje**, **Użytkownicy** i **Grupy**. Obciążenie to po prostu podobszar usługi. Po wybraniu obciążenia odpowiednie okienko zostanie otwarte jako pełna strona. Inne okienka wysuwają się z prawej strony okienka, gdy zostaną otwarte, i zamykają się, aby odsłonić poprzednie okienko. 

    Domyślnie po otwarciu usługi Microsoft Endpoint Manager zostanie wyświetlone okienko **Strona główna**. To okienko zawiera ogólną wizualną migawkę stanu dzierżawy i stanu zgodności, a także inne przydatne linki pokrewne.

2. W okienku nawigacji wybierz pozycję **Pulpit nawigacyjny**, aby wyświetlić ogólne informacje dotyczące urządzeń i aplikacji klienckich w dzierżawie usługi Intune. Jeśli rozpoczynasz od nowej dzierżawy usługi Intune, nie masz jeszcze żadnych zarejestrowanych urządzeń. 

    ![Zrzut ekranu centrum administracyjnego usługi Microsoft Endpoint Manager — Pulpit nawigacyjny](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-02.png)
    
    Usługa Intune umożliwia zarządzanie urządzeniami i aplikacjami pracowników, w tym także sposobem uzyskiwania przez nich dostępu do danych firmy. Aby można było użyć tego rozwiązania do zarządzania urządzeniami mobilnymi (MDM, mobile device management), urządzenia muszą być zarejestrowane w usłudze Intune. Dla zarejestrowanego urządzenia jest wystawiany certyfikat MDM. Ten certyfikat jest używany do komunikacji z usługą Intune. 

    Istnieje kilka metod rejestrowania urządzeń pracowników w usłudze Intune. Każda metoda zależy od własności urządzenia (osobiste lub firmowe), typu urządzenia (system iOS/iPadOS, Windows lub Android) i wymagań dotyczących zarządzania (resetowanie, koligacja i blokowanie). Jednak zanim będzie możliwe włączenie rejestrowania urządzeń, najpierw należy skonfigurować infrastrukturę usługi Intune. W szczególności rejestracja urządzeń wymaga [ustawienia urzędu zarządzania urządzeniami przenośnymi](mdm-authority-set.md). Aby uzyskać więcej informacji na temat przygotowania środowiska usługi Intune (dzierżawy), zobacz [Konfigurowanie usługi Intune](setup-steps.md). Po przygotowaniu dzierżawy usługi Intune możesz rejestrować urządzenia. Aby uzyskać informacje na temat rejestrowania urządzenia, zobacz [Co to jest rejestrowanie urządzenia?](../enrollment/device-enrollment.md)

3. W okienku nawigacyjnym wybierz pozycję **Urządzenia**, aby wyświetlić szczegółowe informacje o urządzeniach zarejestrowanych w dzierżawie usługi Intune. 

    > [!TIP]
    > Jeśli wcześniej usługa Intune była używana w witrynie Azure Portal, powyższe informacje można znaleźć w witrynie Azure Portal, logując się do [usługi Intune](https://go.microsoft.com/fwlink/?linkid=2090973) i wybierając pozycję **Urządzenia**.

    Okienko **Urządzenia — przegląd** zawiera kilka kart, które umożliwiają wyświetlenie podsumowania następujących stanów i alertów:
    - **Stan rejestracji** — zapoznaj się ze szczegółami dotyczącymi urządzeń zarejestrowanych w usłudze Intune według platformy i błędów rejestracji.
    - **Alerty dotyczące rejestracji** — więcej szczegółów dotyczących nieprzypisanych urządzeń według platformy. 
    - **Stan zgodności** — przegląd stanu zgodności na podstawie urządzenia, zasad, ustawienia, zagrożeń i ochrony. Ponadto to okienko zawiera listę urządzeń bez zasad zgodności.
    - **Stan konfiguracji** — przegląd stanu konfiguracji profilów urządzeń, a także wdrożenia profilu. 
    - **Stan aktualizacji oprogramowania** — wizualizacja stanu wdrożenia dla wszystkich urządzeń i wszystkich użytkowników.

    ![Zrzut ekranu centrum administracyjnego usługi Microsoft Endpoint Manager — Urządzenia](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-03.png)

4. W okienku **Urządzenia — przegląd** wybierz pozycję **Zasady zgodności**, aby wyświetlić szczegółowe informacje dotyczące zgodności urządzeń zarządzanych przez usługę Intune. Zostaną wyświetlone szczegóły jak na poniższej ilustracji.

    ![Zrzut ekranu przedstawiający centrum administracyjne usługi Microsoft Endpoint Manager — Zasady zgodności](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-04.png)
    
    > [!TIP]
    > Jeśli wcześniej usługa Intune była używana w witrynie Azure Portal, powyższe informacje można znaleźć w witrynie Azure Portal, logując się do [usługi Intune](https://go.microsoft.com/fwlink/?linkid=2090973) i wybierając pozycję **Zgodność urządzenia**.

    Wymagania dotyczące zgodności to zasadniczo reguły, takie jak wymóg stosowania numeru PIN urządzenia lub stosowania szyfrowania urządzenia. Zasady zgodności urządzeń służą do definiowania reguł i ustawień, które muszą zostać zastosowane na urządzeniu, aby było uważane za zgodne. Aby korzystać z zasad zgodności urządzeń, należy mieć następujące elementy:
    - Subskrypcja usług Intune i Azure Active Directory (Azure AD) Premium
    - Urządzenia z obsługiwaną platformą
    - Urządzenia muszą być zarejestrowane w usłudze Intune
    - Urządzenia, które są zarejestrowane dla jednego użytkownika lub bez użytkownika podstawowego.
    
    Aby uzyskać więcej informacji, zobacz [Wprowadzenie do zasad zgodności urządzeń w usłudze Intune](../protect/device-compliance-get-started.md).

5. W okienku **Urządzenia — przegląd** wybierz pozycję **Dostęp warunkowy**,aby wyświetlić szczegółowe informacje na temat zasad dostępu.

    ![Zrzut ekranu Centrum administracyjnego usługi Microsoft Endpoint Manager — Dostęp warunkowy](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-05.png)

    > [!TIP]
    > Jeśli wcześniej usługa Intune była używana w witrynie Azure Portal, powyższe informacje można znaleźć w witrynie Azure Portal, logując się do [usługi Intune](https://go.microsoft.com/fwlink/?linkid=2090973) i wybierając pozycję **Dostęp warunkowy**.

    Dostęp warunkowy dotyczy sposobów kontrolowania urządzeń i aplikacji, które mogą nawiązywać połączenie z pocztą e-mail i zasobami firmy. Aby uzyskać informacje dotyczące dostępu warunkowego opartego na urządzeniach i aplikacjach, a także poznać typowe scenariusze dotyczące używania dostępu warunkowego za pomocą usługi Intune, zobacz [Co to jest dostęp warunkowy?](../protect/conditional-access.md)

6. W okienku nawigacji wybierz pozycję **Urządzenia** > **Profile konfiguracji**, aby wyświetlić szczegółowe informacje o profilach urządzeń w usłudze Intune.

    ![Zrzut ekranu centrum administracyjnego usługi Microsoft Endpoint Manager — Profile konfiguracji](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-06.png)
    
    > [!TIP]
    > Jeśli wcześniej usługa Intune była używana w witrynie Azure Portal, powyższe informacje można znaleźć w witrynie Azure Portal, logując się do [usługi Intune](https://go.microsoft.com/fwlink/?linkid=2090973) i wybierając pozycję **Konfiguracja urządzeń**.

    Usługa Intune obejmuje ustawienia i funkcje, które można włączać lub wyłączać na różnych urządzeniach w organizacji. Te ustawienia i funkcje są dodawane do „profili konfiguracji”. Możesz utworzyć profile dla różnych urządzeń i różnych platform, w tym systemów iOS/iPadOS, Android, macOS i Windows. Następnie możesz przy użyciu usługi Intune zastosować profil do urządzeń w organizacji.   

    Aby uzyskać więcej informacji o konfiguracji urządzeń, zobacz [Stosowanie ustawień funkcji w urządzeniach przy użyciu profili urządzeń w usłudze Microsoft Intune](../configuration/device-profiles.md).

7. W okienku nawigacji wybierz pozycję **Urządzenia** > **Wszystkie urządzenia**, aby wyświetlić szczegółowe informacje o urządzeniach zarejestrowanych w dzierżawie usługi Intune. Jeśli rozpoczynasz od nowej rejestracji w usłudze Intune, nie masz jeszcze żadnych zarejestrowanych urządzeń.

    ![Zrzut ekranu centrum administracyjnego usługi Microsoft Endpoint Manager — Wszystkie urządzenia](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-07.png)

    Ta lista urządzeń pokazuje najważniejsze szczegóły dotyczące zgodności, wersji systemu operacyjnego i daty ostatniego zaewidencjonowania.

    > [!TIP]
    > Jeśli wcześniej usługa Intune była używana w witrynie Azure Portal, powyższe informacje można znaleźć w witrynie Azure Portal, logując się do [usługi Intune](https://go.microsoft.com/fwlink/?linkid=2090973) i wybierając pozycję **Urządzenia** > **Wszystkie urządzenia**.
 
8. W okienku nawigacji wybierz pozycję **Aplikacje**, aby wyświetlić przegląd stanu aplikacji. To okienko zawiera informacje o stanie instalacji aplikacji oparte na danych w następujących kartach:

    > [!TIP]
    > Jeśli wcześniej usługa Intune była używana w witrynie Azure Portal, powyższe informacje można znaleźć w witrynie Azure Portal, logując się do [usługi Intune](https://go.microsoft.com/fwlink/?linkid=2090973) i wybierając pozycję **Aplikacje klienckie**.

    Okienko **Aplikacje — przegląd** zawiera dwie karty, które umożliwiają wyświetlenie podsumowania następujących stanów:
    - **Stan instalacji** — najważniejsze błędy instalacji według urządzenia, a także aplikacje z błędami instalacji.  
    - **Stan zasad ochrony aplikacji** — szczegóły dotyczące użytkowników przypisanych do zasad ochrony aplikacji, a także oflagowanych użytkowników.

    ![Zrzut ekranu centrum administracyjnego usługi Microsoft Endpoint Manager — Aplikacje](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-08.png)

    Jako administrator informatyczny możesz używać usługi Microsoft Intune do zarządzania aplikacjami klienckimi używanymi przez pracowników firmy. Ta funkcja jest dodatkiem do funkcji zarządzania urządzeniami oraz ochrony danych. Jednym z priorytetów administratora jest zapewnienie, że użytkownicy końcowi mają dostęp do aplikacji, których potrzebują do pracy. Dodatkowo możesz przypisywać aplikacje na urządzeniach niezarejestrowanych w usłudze Intune i zarządzać nimi. Usługa Intune oferuje szeroką gamę możliwości, które pomogą Ci uzyskać dostęp do potrzebnych aplikacji na wybranych urządzeniach. 

    > [!NOTE]
    > Okienko **Aplikacje — przegląd** zawiera także szczegóły stanu dzierżawy i konta.

    Aby uzyskać więcej informacji na temat dodawania i przypisywania aplikacji, zobacz [Dodawanie aplikacji do usługi Microsoft Intune](../apps/apps-add.md) i [Przypisywanie aplikacji do grup przy użyciu usługi Microsoft Intune](../apps/apps-deploy.md).

9. W okienku **Aplikacje — przegląd** wybierz pozycję **Wszystkie aplikacje**, aby wyświetlić listę aplikacji, które zostały dodane do usługi Intune.

    > [!TIP]
    > Jeśli wcześniej usługa Intune była używana w witrynie Azure Portal, powyższe informacje można znaleźć w witrynie Azure Portal, logując się do [usługi Intune](https://go.microsoft.com/fwlink/?linkid=2090973) i wybierając pozycję **Aplikacje klienckie** > **Aplikacje**.

    Możesz dodać do usługi Intune różne typy aplikacji na podstawie platformy. Po dodaniu aplikacji można przypisać ją do grup użytkowników. 

    ![Zrzut ekranu centrum administracyjnego usługi Microsoft Endpoint Manager — Wszystkie aplikacje](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-09.png)

    Aby uzyskać więcej informacji, zobacz [Dodawanie aplikacji do usługi Microsoft Intune](~/apps/apps-add.md). 

10. W okienku nawigacji wybierz pozycję **Użytkownicy**, aby wyświetlić szczegółowe informacje o użytkownikach w usłudze Intune. Ci użytkownicy są pracownikami firmy.

    ![Zrzut ekranu centrum administracyjnego usługi Microsoft Endpoint Manager — Użytkownicy](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-10.png)

    > [!TIP]
    > Jeśli wcześniej usługa Intune była używana w witrynie Azure Portal, powyższe informacje można znaleźć w witrynie Azure Portal, logując się do [usługi Intune](https://go.microsoft.com/fwlink/?linkid=2090973) i wybierając pozycję **Użytkownicy**.

    Możesz bezpośrednio dodawać użytkowników do usługi Intune lub synchronizować użytkowników z lokalnej usługi Active Directory. Po dodaniu użytkownicy mogą rejestrować urządzenia i uzyskiwać dostęp do zasobów firmy. Możesz także przyznawać użytkownikom dodatkowe uprawnienia dostępu do usługi Intune. Aby uzyskać więcej informacji, zobacz [Dodawanie użytkowników i przyznawanie uprawnień administracyjnych do usługi Intune](users-add.md).

11. W okienku nawigacyjnym wybierz pozycję **Grupy**, aby wyświetlić szczegółowe informacje o grupach usługi Azure Active Directory (Azure AD) w usłudze Intune. Jako administrator usługi Intune używasz grup do zarządzania urządzeniami i użytkownikami.

    ![Zrzut ekranu centrum administracyjnego usługi Microsoft Endpoint Manager — Grupy](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-11.png)

    > [!TIP]
    > Jeśli wcześniej usługa Intune była używana w witrynie Azure Portal, powyższe informacje można znaleźć w witrynie Azure Portal, logując się do [usługi Intune](https://go.microsoft.com/fwlink/?linkid=2090973) i wybierając pozycję **Grupy**.

    Grupy możesz skonfigurować zgodnie z potrzebami organizacji. Utwórz grupy w celu zorganizowania użytkowników i urządzeń według lokalizacji geograficznej, działu lub parametrów sprzętowych. Użyj grup, aby zarządzać zadaniami na dużą skalę. Możesz na przykład ustawić zasady dla wielu użytkowników lub wdrożyć aplikacje na zestawie urządzeń. Aby uzyskać więcej informacji na temat grup, zobacz [Dodawanie grup w celu zorganizowania użytkowników i urządzeń](../groups-add.md).

12. W okienku nawigacji wybierz pozycję **Administracja dzierżawą**, aby wyświetlić szczegółowe informacje o dzierżawie usługi Intune.

    > [!TIP]
    > Jeśli wcześniej usługa Intune była używana w witrynie Azure Portal, powyższe informacje można znaleźć w witrynie Azure Portal, logując się do [usługi Intune](https://go.microsoft.com/fwlink/?linkid=2090973) i wybierając pozycję **Stan dzierżawy**.

    W okienku **Administracja dzierżawą — stan dzierżawy** znajdują się karty **Szczegóły dzierżawy**, **Stan łącznika** i **Pulpit nawigacyjny kondycji usługi**. Jeśli wystąpią problemy z dzierżawą lub samą usługą Intune, szczegółowe informacje znajdziesz w tym okienku. 

    ![Zrzut ekranu centrum administracyjnego usługi Microsoft Endpoint Manager — Stan dzierżawy](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-12.png)

    Aby uzyskać więcej informacji, zobacz [Stan dzierżawy w usłudze Intune](../tenant-status.md).

13. W okienku nawigacji wybierz pozycję **Rozwiązywanie problemów i pomoc techniczna** > **Rozwiązywanie problemów**, aby sprawdzić szczegóły stanu określonego użytkownika. 

    > [!TIP]
    > Jeśli wcześniej usługa Intune była używana w witrynie Azure Portal, powyższe informacje można znaleźć w witrynie Azure Portal, logując się do [usługi Intune](https://go.microsoft.com/fwlink/?linkid=2090973) i wybierając pozycję **Rozwiązywanie problemów**.

    Z listy rozwijanej **Przypisania** możesz wybrać opcję wyświetlenia wybranych przypisań aplikacji klienckich, zasad, pierścieni aktualizacji i ograniczeń rejestracji. Ponadto to okienko zawiera szczegóły urządzenia, stan ochrony aplikacji i błędy rejestracji dla określonego użytkownika.

    ![Zrzut ekranu centrum administracyjnego usługi Microsoft Endpoint Manager — Rozwiązywanie problemów](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-13.png)

    Aby uzyskać dodatkowe informacje dotyczące rozwiązywania problemów w usłudze Intune, zobacz [Korzystanie z portalu rozwiązywania problemów, aby pomóc użytkownikom w firmie](../help-desk-operators.md).

14. W okienku nawigacji wybierz pozycję **Rozwiązywanie problemów i obsługa techniczna** > **Pomoc i obsługa techniczna**, aby zwrócić się o pomoc. 

    > [!TIP]
    > Jeśli wcześniej usługa Intune była używana w witrynie Azure Portal, powyższe informacje można znaleźć w witrynie Azure Portal, logując się do [usługi Intune](https://go.microsoft.com/fwlink/?linkid=2090973) i wybierając pozycję **Pomoc i obsługa techniczna**.

    Jako administrator IT możesz za pomocą opcji **Pomoc i obsługa techniczna** wyszukiwać i wyświetlać rozwiązania oraz zgłaszać bilety pomocy technicznej online dla usługi Intune. 

    ![Zrzut ekranu przedstawiający centrum administracyjne usługi Microsoft Endpoint Manager — Pomoc i obsługa techniczna](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-14.png)

    Aby utworzyć bilet pomocy technicznej, musisz mieć konto z przypisaną rolą administratora w usłudze Azure Active Directory. Role administratora obejmują **administratora usługi Intune**, **administratora globalnego** i **administratora usługi**. 

    Aby uzyskać więcej informacji, zobacz [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](../get-support.md).

15. W okienku nawigacji wybierz pozycję **Rozwiązywanie problemów i obsługa techniczna** > **Scenariusze z przewodnikiem**, aby wyświetlić dostępne scenariusze z przewodnikiem usługi Intune. 

    Scenariusz z przewodnikiem przedstawia serię dostosowanych kroków, które należy wykonać w jednym konkretnym przypadku użycia. Typowe scenariusze są opisane na podstawie na roli, jaką w Twojej organizacji odgrywa administrator, użytkownik lub urządzenie. Te role zwykle wymagają starannego zsynchronizowania profilów, ustawień, aplikacji i opcji zabezpieczeń, aby zapewnić jak najlepsze środowisko użytkownika i skuteczne zabezpieczenia.

    Jeśli nie znasz wszystkich kroków i zasobów potrzebnych do wdrożenia konkretnego scenariusza usługi Intune, możesz zacząć od skorzystania ze scenariusza z przewodnikiem. 

    ![Zrzut ekranu centrum administracyjnego usługi Microsoft Endpoint Manager — Scenariusze z przewodnikiem](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-15.png)

    Aby uzyskać więcej informacji na temat scenariuszy z przewodnikiem, zobacz [Scenariusze z przewodnikiem — omówienie](~/fundamentals/guided-scenarios-overview.md).

## <a name="configure-the-microsoft-endpoint-manager-admin-center"></a>Konfigurowanie centrum administracyjnego usługi Microsoft Endpoint Manager

Platforma Azure umożliwia dostosowywanie i konfigurowanie widoku portalu.

### <a name="change-the-dashboard"></a>Modyfikowanie pulpitu nawigacyjnego

**Pulpit nawigacyjny** umożliwia wyświetlenie ogólnych informacji dotyczących urządzeń i aplikacji klienckich w dzierżawie usługi Intune. Pulpity nawigacyjne to sposób na tworzenie spójnych tematycznie i zorganizowanych widoków w centrum administracyjnym usługi Microsoft Endpoint Manager. Używaj pulpitów nawigacyjnych jako obszaru roboczego, w którym można szybko uruchamiać zadania na potrzeby codziennych operacji i monitorować zasoby. Na przykład możesz tworzyć niestandardowe pulpity nawigacyjne na podstawie projektów, zadań lub ról użytkownika. Centrum administracyjne usługi Microsoft Endpoint Manager udostępnia domyślny pulpit nawigacyjny jako punkt startowy. Możesz zmodyfikować domyślny pulpit nawigacyjny, utworzyć i dostosować dodatkowe pulpity nawigacyjne oraz opublikować pulpity nawigacyjne i udostępnić je innym użytkownikom. 

   ![Zrzut ekranu centrum administracyjnego usługi Microsoft Endpoint Manager — Pulpit nawigacyjny](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-16.png)

Aby zmodyfikować bieżący pulpit nawigacyjny, wybierz pozycję **Edytuj**. Jeśli nie chcesz zmieniać domyślnego pulpitu nawigacyjnego, możesz również utworzyć **Nowy pulpit nawigacyjny**. Utworzenie nowego pulpitu nawigacyjnego powoduje udostępnienie pustego, prywatnego pulpitu nawigacyjnego z pozycją **Galeria kafelków**, umożliwiającą dodawanie kafelków i zmienianie ich rozmieszczenia. Kafelki można wyszukiwać według kategorii lub typu zasobu. Możesz także wyszukać konkretne kafelki. Wybierz pozycję **Mój pulpit nawigacyjny**, aby wybrać dowolny z istniejących niestandardowych pulpitów nawigacyjnych.

### <a name="change-the-portal-settings"></a>Zmienianie ustawień portalu

Możesz dostosować centrum administracyjne usługi Microsoft Endpoint Manager, wybierając widok domyślny, motyw, limit czasu dla poświadczeń, a także ustawienia języka i regionu.

   <img alt="Screenshot of the Microsoft Endpoint Manager admin center - Portal settings" src="./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-17.png" width="250">

## <a name="next-steps"></a>Następne kroki

Aby szybko rozpocząć pracę z usługą Microsoft Intune, utwórz bezpłatne konto usługi Intune, a następnie zapoznaj się z przewodnikami Szybki start.

> [!div class="nextstepaction"]
> [Szybki start: bezpłatna wersja próbna usługi Microsoft Intune](free-trial-sign-up.md)
