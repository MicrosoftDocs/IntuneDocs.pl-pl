---
title: Samouczek — przewodnik po usłudze Intune w witrynie Azure Portal
titleSuffix: Microsoft Intune
description: W tym samouczku poznasz usługę Microsoft Intune i dowiesz się, jak wykonywać zadania.
keywords: ''
author: ErikRe
ms.author: erikre
manager: dougeby
ms.date: 03/28/2019
ms.topic: tutorial
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: e892d8a3-7f74-498c-98d5-e968a8fbb049
Customer intent: As an Intune admin, I want to learn where to find the different features in Intune.
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c601af8c2b73ac68ec88f45d3684fcfd41f1c87f
ms.sourcegitcommit: 1144247aa7f042eb1b99d8fd8dd17b909eae38c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/28/2019
ms.locfileid: "58567592"
---
# <a name="tutorial-walkthrough-of-microsoft-intune-in-the-azure-portal"></a>Samouczek: przewodnik po usłudze Microsoft Intune w witrynie Azure Portal

Platforma [Azure](https://docs.microsoft.com/learn/modules/welcome-to-azure) zawiera ponad 100 usług, które ułatwiają pracę dzięki różnym możliwościom i scenariuszom przetwarzania w chmurze. Microsoft Intune jest jedną z kilku usług dostępnych na platformie Azure. Usługa Intune pomaga zapewnić, że urządzenia, aplikacje i dane firmowe spełniają wymagania dotyczące zabezpieczeń. Możesz kontrolować, które wymagania mają być sprawdzane, i co ma się stać, gdy te wymagania nie zostaną spełnione. Usługę Microsoft Intune można znaleźć w witrynie [Azure Portal](https://portal.azure.com). Zrozumienie funkcji dostępnych w usłudze Intune pomoże Ci w wykonywaniu różnych zadań dotyczących zarządzania urządzeniami mobilnymi (MDM) i zarządzania aplikacjami mobilnymi (MAM).

W tym samouczku wykonasz następujące czynności:
> [!div class="checklist"]
> * Zapoznanie się z usługą Microsoft Intune
> * Konfigurowanie witryny Azure portal

Jeśli nie masz subskrypcji usługi Intune, [utwórz konto bezpłatnej wersji próbnej](free-trial-sign-up.md).

## <a name="prerequisites"></a>Wymagania wstępne
Przed skonfigurowaniem usługi Microsoft Intune przejrzyj poniższe wymagania:

   - [Obsługiwane systemy operacyjne i przeglądarki](supported-devices-browsers.md) 
   - [Przepustowość i wymagania dotyczące konfiguracji sieci](network-bandwidth-use.md)

## <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Rejestrowanie w celu skorzystania z bezpłatnej wersji próbnej usługi Microsoft Intune

Usługę Intune można bezpłatnie testować przez 30 dni. Jeśli masz już konto firmowe, **zaloguj się** przy użyciu tego konta i dodaj usługę Intune do swojej subskrypcji. W przeciwnym razie [utwórz konto bezpłatnej wersji próbnej](free-trial-sign-up.md), aby móc korzystać z usługi Intune w swojej organizacji.

> [!IMPORTANT]
> Nie można połączyć istniejącego konta służbowego lub edukacyjnego po zarejestrowaniu nowego konta.

## <a name="tour-microsoft-intune"></a>Zapoznanie się z usługą Microsoft Intune

Wykonaj poniższe czynności, aby lepiej poznać usługę Intune w witrynie Azure portal. Po ukończeniu prezentacji będziesz mieć lepsze zrozumienie niektórych głównych obszarów usługi Intune.

1. Otwórz przeglądarkę i zaloguj się do [portalu usługi Intune](https://aka.ms/intuneportal). Jeśli jesteś nowym użytkownikiem usługi Intune, użyj subskrypcji bezpłatnej wersji próbnej.

    ![Zrzut ekranu przedstawiający portal usługi Microsoft Intune](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-01.png)

    Otwarcie usługi Intune lub dowolnej innej usługi platformy Azure spowoduje wyświetlenie tej usługi w okienku. Niektóre z pierwszych obciążeń, których możesz użyć w usłudze Intune, to **Urządzenia**, **Aplikacje klienckie**, **Użytkownicy** i **Grupy**. Obciążenie to po prostu podobszar usługi. Po wybraniu obciążenia odpowiednie okienko zostanie otwarte jako pełna strona. Inne okienka wysuwają się z prawej strony okienka, gdy zostaną otwarte, i zamykają się, aby odsłonić poprzednie okienko. Okienko jest również nazywane blokiem. 

    Domyślnie po otwarciu usługi Intune wyświetlane jest okienko **Przegląd**. To okienko zawiera ogólną wizualną migawkę przypisania urządzeń i stanu zgodności, a także stan instalacji aplikacji.

2. W usłudze [Intune](https://aka.ms/intuneportal) wybierz pozycję **Rejestrowanie urządzeń**, aby wyświetlić szczegółowe informacje o zarejestrowanych urządzeniach w dzierżawie usługi Intune. Jeśli rozpoczynasz od nowej dzierżawy usługi Intune, nie masz jeszcze żadnych zarejestrowanych urządzeń. 

    ![Zrzut ekranu przedstawiający okienko Rejestrowanie urządzeń](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-02.png)
    
    Usługa Intune umożliwia zarządzanie urządzeniami i aplikacjami pracowników, w tym także sposobem uzyskiwania przez nich dostępu do danych firmy. Aby można było użyć tego rozwiązania do zarządzania urządzeniami mobilnymi (MDM, mobile device management), urządzenia muszą być zarejestrowane w usłudze Intune. Dla zarejestrowanego urządzenia jest wystawiany certyfikat MDM. Ten certyfikat jest używany do komunikacji z usługą Intune. 

    Istnieje kilka metod rejestrowania urządzeń pracowników w usłudze Intune. Każda metoda zależy od własności urządzenia (osobiste lub firmowe), typu urządzenia (system iOS, Windows lub Android) i wymagań dotyczących zarządzania (resetowanie, koligacja i blokowanie). Jednak zanim będzie możliwe włączenie rejestrowania urządzeń, najpierw należy skonfigurować infrastrukturę usługi Intune. W szczególności rejestracja urządzeń wymaga [ustawienia urzędu zarządzania urządzeniami przenośnymi](mdm-authority-set.md). Aby uzyskać więcej informacji na temat przygotowania środowiska usługi Intune (dzierżawy), zobacz [Konfigurowanie usługi Intune](setup-steps.md). Po przygotowaniu dzierżawy usługi Intune możesz rejestrować urządzenia. Aby uzyskać informacje na temat rejestrowania urządzenia, zobacz [Co to jest rejestrowanie urządzenia?](device-enrollment.md)

3. W usłudze [Intune](https://aka.ms/intuneportal) wybierz pozycję **Zgodność urządzenia**, aby wyświetlić szczegóły dotyczące zgodności urządzeń zarządzanych przez usługę Intune. Zostaną wyświetlone szczegóły jak na poniższej ilustracji.

    ![Zrzut ekranu przedstawiający okienko Zgodność urządzenia](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-03.png)
    
    Wymagania dotyczące zgodności to zasadniczo reguły, takie jak wymóg stosowania numeru PIN urządzenia lub stosowania szyfrowania urządzenia. Zasady zgodności urządzeń służą do definiowania reguł i ustawień, które muszą zostać zastosowane na urządzeniu, aby było uważane za zgodne. Aby korzystać z zasad zgodności urządzeń, należy mieć następujące elementy:
    - Subskrypcja usług Intune i Azure Active Directory (Azure AD) Premium
    - Urządzenia z obsługiwaną platformą
    - Urządzenia muszą być zarejestrowane w usłudze Intune
    - Urządzenia, które są zarejestrowane dla jednego użytkownika lub bez użytkownika podstawowego.
    
    Aby uzyskać więcej informacji, zobacz [Wprowadzenie do zasad zgodności urządzeń w usłudze Intune](device-compliance-get-started.md).

4. W usłudze [Intune](https://aka.ms/intuneportal) wybierz pozycję **Konfiguracja urządzenia**, aby wyświetlić szczegółowe informacje dotyczące profilów urządzeń w usłudze Intune. 

    ![Zrzut ekranu przedstawiający okienko Konfiguracja urządzenia](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-04.png)
    
    Usługa Intune obejmuje ustawienia i funkcje, które można włączać lub wyłączać na różnych urządzeniach w organizacji. Te ustawienia i funkcje są dodawane do „profili konfiguracji”. Możesz utworzyć profile dla różnych urządzeń i różnych platform, w tym systemów iOS, Android i Windows. Następnie możesz przy użyciu usługi Intune zastosować profil do urządzeń w organizacji.   

    Aby uzyskać więcej informacji o konfiguracji urządzeń, zobacz [Stosowanie ustawień funkcji w urządzeniach przy użyciu profili urządzeń w usłudze Microsoft Intune](device-profiles.md).

5. W usłudze [Intune](https://aka.ms/intuneportal) wybierz pozycję **Urządzenia**, aby wyświetlić szczegółowe informacje o zarejestrowanych urządzeniach w dzierżawie usługi Intune. Jeśli rozpoczynasz od nowej rejestracji w usłudze Intune, nie masz jeszcze żadnych zarejestrowanych urządzeń. 

    ![Zrzut ekranu przedstawiający okienko Rejestrowanie urządzeń](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-05.png)
    
    Okienko **Urządzenia** zawiera szczegółowe informacje o zarejestrowanych urządzeniach w dzierżawie. Możesz kliknąć pozycję **Wszystkie urządzenia**, aby wyświetlić listę urządzeń dla dzierżawy usługi Intune. 

6. W usłudze [Intune](https://aka.ms/intuneportal) wybierz pozycję **Aplikacje klienckie**, aby wyświetlić stan instalacji aplikacji.

    ![Zrzut ekranu przedstawiający okienko Aplikacje klienckie](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-06.png)
    
    Jako administrator informatyczny możesz używać usługi Microsoft Intune do zarządzania aplikacjami klienckimi używanymi przez pracowników firmy. Ta funkcja jest dodatkiem do funkcji zarządzania urządzeniami oraz ochrony danych. Jednym z priorytetów administratora jest zapewnienie, że użytkownicy końcowi mają dostęp do aplikacji, których potrzebują do pracy. Dodatkowo możesz przypisywać aplikacje na urządzeniach niezarejestrowanych w usłudze Intune i zarządzać nimi. Usługa Intune oferuje szeroką gamę możliwości, które pomogą Ci uzyskać dostęp do potrzebnych aplikacji na wybranych urządzeniach. Aby uzyskać więcej informacji na temat dodawania i przypisywania aplikacji, zobacz [Dodawanie aplikacji do usługi Microsoft Intune](apps-add.md) i [Przypisywanie aplikacji do grup przy użyciu usługi Microsoft Intune](apps-deploy.md).

7. W usłudze [Intune](https://aka.ms/intuneportal) wybierz pozycję **Dostęp warunkowy**,aby wyświetlić szczegółowe informacje na temat zasad dostępu.

    ![Zrzut ekranu przedstawiający okienko dostępu warunkowego](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-07.png)

    Dostęp warunkowy dotyczy sposobów kontrolowania urządzeń i aplikacji, które mogą nawiązywać połączenie z pocztą e-mail i zasobami firmy. Aby uzyskać informacje dotyczące dostępu warunkowego opartego na urządzeniach i aplikacjach, a także poznać typowe scenariusze dotyczące używania dostępu warunkowego za pomocą usługi Intune, zobacz [Co to jest dostęp warunkowy?](conditional-access.md).

8. W usłudze [Intune](https://aka.ms/intuneportal) wybierz pozycję **Użytkownicy**, aby wyświetlić szczegółowe informacje o użytkownikach w usłudze Intune. Ci użytkownicy są pracownikami firmy. 
 
    ![Zrzut ekranu przedstawiający okienko Użytkownicy](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-08.png)

    Możesz bezpośrednio dodawać użytkowników do usługi Intune lub synchronizować użytkowników z lokalnej usługi Active Directory. Po dodaniu użytkownicy mogą rejestrować urządzenia i uzyskiwać dostęp do zasobów firmy. Możesz także przyznawać użytkownikom dodatkowe uprawnienia dostępu do usługi Intune. Aby uzyskać więcej informacji, zobacz [Dodawanie użytkowników i przyznawanie uprawnień administracyjnych do usługi Intune](users-add.md).

9. W usłudze [Intune](https://aka.ms/intuneportal) wybierz pozycję **Grupy**, aby wyświetlić szczegółowe informacje o grupach usługi Azure Active Directory (Azure AD) w usłudze Intune. Jako administrator usługi Intune używasz grup do zarządzania urządzeniami i użytkownikami. 

    ![Zrzut ekranu przedstawiający okienko Grupy](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-09.png)

    Grupy możesz skonfigurować zgodnie z potrzebami organizacji. Utwórz grupy w celu zorganizowania użytkowników i urządzeń według lokalizacji geograficznej, działu lub parametrów sprzętowych. Użyj grup, aby zarządzać zadaniami na dużą skalę. Możesz na przykład ustawić zasady dla wielu użytkowników lub wdrożyć aplikacje na zestawie urządzeń. Aby uzyskać więcej informacji na temat grup, zobacz [Dodawanie grup w celu zorganizowania użytkowników i urządzeń](groups-add.md).

10. W usłudze [Intune](https://aka.ms/intuneportal) wybierz pozycję **Pomoc i obsługa techniczna**, aby poprosić o pomoc. Jako administrator IT możesz za pomocą opcji **Pomoc i obsługa techniczna** wyszukiwać i wyświetlać rozwiązania oraz zgłaszać bilety pomocy technicznej online dla usługi Intune. 

    ![Zrzut ekranu przedstawiający okienko Pomoc i obsługa techniczna](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-10.png)

    Aby utworzyć bilet pomocy technicznej, musisz mieć konto z przypisaną rolą administratora w usłudze Azure Active Directory. Role administratora obejmują **administratora usługi Intune**, **administratora globalnego** i **administratora usługi**. Aby uzyskać więcej informacji, zobacz [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](get-support.md).

11. W usłudze [Intune](https://aka.ms/intuneportal) wybierz pozycję **Stan dzierżawy**, aby wyświetlić szczegółowe informacje o dzierżawie usługi Intune.

    ![Zrzut ekranu przedstawiający okienko Stan dzierżawy](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-11.png)

    Szczegółowe informacje o stanie dzierżawy obejmują stan łącznika, kondycję usługi Intune i wiadomości w usłudze Intune. Jeśli wystąpią problemy z dzierżawą lub samą usługą Intune, szczegółowe informacje znajdziesz w okienku **Stan dzierżawy**. Aby uzyskać więcej informacji, zobacz [Stan dzierżawy w usłudze Intune](tenant-status.md).

12. W usłudze [Intune](https://aka.ms/intuneportal) wybierz pozycję **Rozwiązywanie problemów**, aby uzyskać skrót do wskazówek związanych z rozwiązywaniem problemów, żądania pomocy technicznej oraz sprawdzania stanu usługi Intune. Te informacje dotyczą określonego, wybranego przez Ciebie użytkownika.

    ![Zrzut ekranu przedstawiający okienko Rozwiązywanie problemów](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-12.png)

Aby uzyskać dodatkowe informacje dotyczące rozwiązywania problemów w usłudze Intune, zobacz [Korzystanie z portalu rozwiązywania problemów, aby pomóc użytkownikom w firmie](help-desk-operators.md).

## <a name="configure-the-azure-portal"></a>Konfigurowanie witryny Azure portal

Platforma Azure umożliwia dostosowywanie i konfigurowanie widoku portalu.

### <a name="change-the-sidebar"></a>Zmienianie paska bocznego

Na **pasku bocznym** po lewej stronie witryny Azure Portal znajduje się lista wszystkich dostępnych usług platformy Azure. Domyślny wygląd tej kompleksowej listy można zmienić, aby najważniejsze usługi były zawsze widoczne. W poniższym opisie przykładową usługą dodawaną na górze listy jest usługa Intune.

![Użytkownik wyszukuje usługę Microsoft Intune na liście „Więcej usług”.](./media/azure-add-intune1.png)

1. Wybierz pozycję **Wszystkie usługi** z paska bocznego w lewej części strony.
2. Wpisz ciąg **Intune** w polu filtru.
3. Wybierz ikonę **gwiazdki**, aby dodać usługę Intune na koniec listy ulubionych usług.
4. Umieść wskaźnik myszy nad usługą Intune. Wybierz, a następnie przeciągnij usługę Intune przy użyciu **trzech pionowo ułożonych kropek** po prawej stronie nazwy usługi.

### <a name="change-the-dashboard"></a>Zmienianie pulpitu nawigacyjnego

Domyślna strona docelowa to **pulpit nawigacyjny**. Na tej stronie możesz zmodyfikować kafelki, aby przedstawiały informacje najważniejsze dla Ciebie.

![Obraz standardowego nowego pulpitu nawigacyjnego. Pasek boczny ze wszystkimi usługami znajduje się po lewej stronie, a główny pulpit nawigacyjny jest na środku. Przyciski służące do modyfikowania pulpitu nawigacyjnego są umieszczone u góry wraz z kafelkami umożliwiającymi dostęp do wszystkich zasobów, samouczków Szybki start, kondycji usług i witryny Azure Marketplace.](./media/azure-default-dashboard.png)

Aby zmodyfikować bieżący pulpit nawigacyjny, wybierz przycisk **Edytuj pulpit nawigacyjny**. Jeśli nie chcesz zmieniać domyślnego pulpitu nawigacyjnego, możesz również utworzyć **Nowy pulpit nawigacyjny**. Utworzenie nowego pulpitu nawigacyjnego powoduje udostępnienie pustego, prywatnego pulpitu nawigacyjnego z pozycją **Galeria kafelków**, umożliwiającą dodawanie kafelków i zmienianie ich rozmieszczenia. Kafelki możesz znajdować za pomocą następujących metod: **Kategoria ogólna**, **Typ**, **Wyszukiwanie**, **Grupa zasobów** lub **Tag**.

Oprócz tego kafelki można dodawać do pulpitu nawigacyjnego bezpośrednio za pomocą dowolnego przycisku **wielokropka**, wybierając pozycję **Przypnij do pulpitu nawigacyjnego**.

![Zbliżenie lokalizacji Użytkownicy i grupy > Wszystkie grupy w usłudze Intune z opcją „Przypnij do pulpitu nawigacyjnego” widoczną po prawej stronie grupy.](./media/azure-pin-to-dashboard.png)

Ta możliwość będzie bardziej przydatna po dodaniu większej ilości zawartości do usługi Intune, takiej jak grupy i użytkownicy.

## <a name="next-steps"></a>Następne kroki

Aby szybko rozpocząć pracę z usługą Microsoft Intune, utwórz bezpłatne konto usługi Intune, a następnie zapoznaj się z przewodnikami Szybki start.

> [!div class="nextstepaction"]
> [Szybki start: bezpłatna wersja próbna usługi Microsoft Intune](free-trial-sign-up.md)


