---
title: "Dodawanie użytkowników i przyznawanie uprawnień"
description: "Synchronizowanie lokalnych użytkowników z usługą Azure AD i przyznawanie uprawnień administratora dla subskrypcji usługi Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/19/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7873481ccd33d2eaf4ec1a4c7fadf30c61b8d42e
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2017
---
# <a name="add-users-and-give-administrative-permission-to-intune"></a>Dodawanie użytkowników i przyznawanie uprawnień administracyjnych do usługi Intune

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Ten temat zawiera informacje dla administratorów dotyczące dodawania użytkowników do usługi Intune oraz uprawnień administracyjnych dostępnych w usłudze Intune.

Jako administrator możesz bezpośrednio dodawać użytkowników lub synchronizować użytkowników w lokalnej usłudze Active Directory. Po dodaniu użytkownicy mogą rejestrować urządzenia i uzyskiwać dostęp do zasobów firmy. Użytkownikom możesz też przyznawać dodatkowe uprawnienia, takie jak uprawnienia *administratora globalnego* i *administratora usługi*.

## <a name="add-users-to-intune"></a>Dodawanie użytkowników do usługi Intune
Można ręcznie dodawać użytkowników do subskrypcji usługi Intune za pośrednictwem [portalu usługi Office 365](https://www.office.com/signin) lub [portalu usługi Intune na platformie Azure](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview). Administrator może edytować konta użytkowników w celu przypisania licencji usługi Intune. Możesz przypisać licencje w portalu usługi Office 365 albo portalu usługi Intune na platformie Azure. Aby uzyskać więcej informacji dotyczących korzystania z portalu usługi Office 365, zobacz [Pojedyncze lub zbiorcze dodawanie użytkowników do portalu usługi Office 365](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="add-intune-users-in-the-office-365-admin-center"></a>Dodawanie użytkowników usługi Intune w centrum administracyjnym usługi Office 365
1. Zaloguj się do [portalu usługi Office 365](https://www.office.com/signin) za pomocą konta administratora globalnego lub administratora zarządzającego użytkownikami.
2. W menu usługi Office 365 wybierz pozycję **Administracja**.
3. W centrum administracyjnym wybierz pozycję **Dodaj użytkownika**.

  ![Zrzut ekranu centrum administracyjnego usługi Office 365](media/office-add-user.png)

4. Określ następujące dane użytkownika:
  - **Imię**
  - **Nazwisko**
  - **Nazwa wyświetlana**
  - **Nazwa użytkownika** — uniwersalna nazwa główna (nazwa UPN) przechowywana w usłudze Azure Active Directory używana do uzyskania dostępu do usługi
  - **Lokalizacja**
  - **Informacje kontaktowe** (opcjonalnie)
  - **Hasło** — generowane automatycznie lub określone

     ![Zrzut ekranu centrum administracyjnego usługi Office 365](media/office-add-user-details.png)

5. Przypisz licencję usługi Intune. Wybierz pozycję **Licencje produktów** i wybierz licencję produktu. Wymagana jest licencja obejmująca usługę Intune.
6. Wybierz pozycję **Dodaj**, aby utworzyć nowego użytkownika.

### <a name="add-intune-users-in-the-azure-intune-portal"></a>Dodawanie użytkowników usługi Intune w portalu usługi Intune na platformie Azure
1. Zaloguj się w witrynie [Azure Portal](https://portal.azure.com) i wybierz pozycje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**. Możesz również *wyszukać zasoby* i znaleźć usługę **Intune**.
2. Wybierz pozycję **Użytkownicy**.
3. W centrum administracyjnym wybierz pozycję **Nowy użytkownik**.
  ![Zrzut ekranu centrum administracyjnego usługi Office 365](media/intune-add-user.png)
4. Określ następujące dane użytkownika:
  - **Nazwa**
  - **Nazwa użytkownika** — nowa nazwa w portalu usługi Azure Active Directory ![Zrzut ekranu centrum administracyjnego usługi Office 365](media/intune-add-user-info.png) Wybierz przycisk **OK**, aby kontynuować.
5. Opcjonalnie możesz określić następujące właściwości użytkownika:
  - **Profil** — informacje służbowe, w tym **Stanowisko** i **Dział**
  -  **Grupy** — wybierz grupy do dodania dla użytkownika
  - **Rola katalogu** — przyznaj użytkownikowi uprawnienia administracyjne, w tym rolę administratora usługi Intune.

  Wybierz pozycję **Utwórz**, aby dodać nowego użytkownika do usługi Intune.
6. Wybierz pozycję **Profil**, a następnie wybierz pozycję **Lokalizacja użycia** dla nowego użytkownika. Lokalizacja użycia jest wymagana, zanim będzie można przypisać licencję usługi Intune do nowego użytkownika. Wybierz przycisk **Zapisz**, aby kontynuować.
    ![Zrzut ekranu centrum administracyjnego usługi Office 365](media/intune-add-user-loc.png)
7. Wybierz pozycję **Licencje**, a następnie wybierz pozycję **Przypisz**, aby przypisać licencję usługi Intune do tego użytkownika. Licencja usługi Intune jest wymagana, aby zarejestrować urządzenia lub uzyskać dostęp do zasobów firmy. Wybierz pozycję **Produkty**, wybierz typ licencji, wybierz pozycję **Wybierz**, a następnie wybierz pozycję **Przypisz**.

## <a name="grant-admin-permissions"></a>Przyznawanie uprawnień administracyjnych

Po dodaniu użytkowników do subskrypcji usługi Intune zaleca się przyznanie uprawnień administracyjnych kilku użytkownikom.  Aby przyznać uprawnienia administracyjne, wykonaj następujące kroki:

### <a name="give-admin-permissions-in-office-365"></a>Nadawanie uprawnień administratora w usłudze Office 365
1. Zaloguj się do [portalu usługi Office 365](https://www.office.com/signin) przy użyciu konta administratora globalnego.
2. W menu usługi Office 365 wybierz pozycję **Administracja**.
3. W centrum administracyjnym wybierz pozycję **Aktywni użytkownicy**, a następnie wybierz użytkownika, któremu chcesz przyznać uprawnienia administratora.
4. W kolumnie **Role** wybierz pozycję **Edytuj**.
  ![Zrzut ekranu przedstawiający ekran przypisywania ról w usłudze Office 365](./media/office-assign-roles-open.png)
5. Z listy dostępnych ról wybierz uprawnienia administratora, które mają zostać przyznane.
![Obraz przedstawiający przypisywanie ról w portalu usługi Office 365.](./media/office-assign-roles.png)
6. Wybierz polecenie **Zapisz**.

### <a name="give-admin-permissions-in-the-intune-portal"></a>Nadawanie uprawnień administratora w portalu usługi Intune
1. Zaloguj się do [portalu usługi Intune](https://www.office.com/signin) przy użyciu konta administratora globalnego.
2. W portalu usługi Intune wybierz pozycję **Użytkownik**, a następnie wybierz użytkownika, któremu chcesz nadać uprawnienia administratora.
3. Wybierz pozycję **Rola katalogu**, a następnie wybierz uprawnienie.
  ![Zrzut ekranu](./media/add-intune-directory-role.png)
4. Wybierz polecenie **Zapisz**.

### <a name="types-of-administrators"></a>Typy administratorów

Przypisz użytkownikom co najmniej jedne uprawnienia administratora. Uprawnienia te definiują zakres administracyjny użytkowników i zadania, którymi mogą zarządzać. Uprawnienia administratorów są wspólne w różnych usługach firmy Microsoft w chmurze, chociaż niektóre uprawnienia mogą nie być obsługiwane w pewnych usługach. W portalu usługi Intune i portalu usługi Office 365 jest wyświetlana lista ograniczonych ról administratora, które nie są używane przez usługę Intune. Uprawnienia administratora usługi Intune obejmują następujące opcje:

- **Administrator globalny** — (usługa Office 365 i Intune) ma dostęp do wszystkich funkcji administracyjnych w usłudze Intune. Domyślnie osoba, która zarejestruje się w usłudze Intune staje się administratorem globalnym. Administratorzy globalni są jedynymi administratorami, którzy mogą przypisywać pozostałe role administratora. W organizacji może być więcej niż jeden administrator globalny. Najlepszym rozwiązaniem jest przypisanie tej roli tylko kilku osobom w firmie, ponieważ pozwala to ograniczyć potencjalne zagrożenia.
- **Administrator haseł** — (usługa Office 365 i Intune) resetuje hasła, zarządza żądaniami obsługi i monitoruje kondycję usługi. Administratorzy haseł mogą jedynie resetować hasła użytkowników.
- **Administrator usługi** — (usługa Office 365 i Intune) otwiera żądania pomocy technicznej przesyłane do firmy Microsoft oraz przegląda pulpit nawigacyjny i centrum wiadomości usługi. Ma uprawnienia tylko do wyświetlania z wyjątkiem otwierania biletów pomocy technicznej oraz ich odczytywania.
- **Administrator rozliczeń** — (usługa Office 365 i Intune) dokonuje zakupów, zarządza subskrypcjami, zarządza biletami pomocy technicznej i monitoruje kondycję usługi.
- **Administrator użytkowników** — (usługa Office 365 i Intune) resetuje hasła, monitoruje kondycję usługi, dodaje i usuwa konta użytkowników oraz zarządza żądaniami obsługi. Administrator zarządzający użytkownikami nie może usunąć administratora globalnego, tworzyć innych ról administratora ani resetować haseł innych administratorów.
- **Administrator usługi Intune** — ma wszystkie uprawnienia administratora globalnego usługi Intune z wyjątkiem uprawnienia do tworzenia administratorów za pomocą opcji **Rola katalogu**.

Konto użyte do utworzenia subskrypcji usługi Microsoft Intune jest administratorem globalnym. Najlepszym rozwiązaniem jest nieużywanie konta administratora globalnego do wykonywania codziennych zadań zarządzania. Administrator nie musi dysponować licencją na korzystanie z usługi Intune, aby uzyskać dostęp do portalu usługi Intune. 

Aby uzyskać dostęp do portalu usługi Office 365, Twoje konto musi mieć ustawioną opcję **Logowanie dozwolone**. W portalu Intune w obszarze **Profil** ustaw wartość opcji **Blokuj logowanie** na **Nie**, aby zezwolić na dostęp. Ten stan nie oznacza posiadania licencji na korzystanie z subskrypcji. Domyślnie wszystkie konta użytkowników mają stan **Dozwolone**. Użytkownicy bez uprawnień administratora mogą używać portalu usługi Office 365 do resetowania haseł usługi Intune.

## <a name="sync-active-directory-and-add-users-to-intune"></a>Synchronizacja usługi Active Directory i dodawanie użytkowników do usługi Intune
Istnieje możliwość skonfigurowania synchronizacji katalogów w celu zaimportowania kont użytkowników z lokalnej usługi Active Directory do usługi Microsoft Azure Active Directory (Azure AD), co obejmuje użytkowników usługi Intune. Połączenie lokalnej usługi Active Directory z wszystkimi usługami opartymi na usłudze Azure Active Directory znacznie ułatwia zarządzanie tożsamościami użytkowników. Można także skonfigurować funkcje logowania jednokrotnego, aby znacznie ułatwić uwierzytelnianie użytkowników. Dzięki połączeniu tej samej [dzierżawy usługi Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) z wieloma usługami wcześniej zsynchronizowane konta użytkowników są dostępne dla wszystkich usług w chmurze.

### <a name="how-to-sync-on-premises-users-with-azure-ad"></a>Jak zsynchronizować użytkowników lokalnych z usługą Azure AD
Jedynym narzędziem potrzebnym do synchronizowania kont użytkowników z usługą Azure AD jest [Kreator Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594). Kreator Azure AD Connect zapewnia uproszczoną obsługę i przewodnik łączenia lokalnej infrastruktury tożsamości z chmurą.  Wybierz topologię i potrzeby (jeden lub wiele katalogów, synchronizacja haseł lub federacja). Kreator wdroży i skonfiguruje wszystkie składniki wymagane do uruchomienia połączenia. Dotyczy to następujących składników: usług synchronizacji, Usług federacyjne Active Directory (AD FS) i modułu Azure AD PowerShell.

> [!TIP]
> Kreator Azure AD Connect obejmuje funkcje, które były wcześniej dostępne w narzędziach Dirsync i Azure AD Sync. Dowiedz się więcej na temat [integracji katalogów](http://technet.microsoft.com/library/jj573653.aspx). Aby dowiedzieć się więcej o synchronizowaniu kont użytkowników z katalogu lokalnego do usługi Azure AD, zobacz [Podobieństwa między usługami Active Directory i Azure AD](http://technet.microsoft.com/library/dn518177.aspx).