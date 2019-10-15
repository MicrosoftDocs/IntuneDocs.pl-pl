---
title: Dodawanie użytkowników i przyznawanie uprawnień
titleSuffix: Microsoft Intune
description: Synchronizuj lokalnych użytkowników z usługą Azure AD i przyznawaj uprawnienia administratora dla subskrypcji usługi Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/28/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5f0383bf889a955a72df278ae3f2b3b23925f233
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71726235"
---
# <a name="add-users-and-grant-administrative-permission-to-intune"></a>Dodawanie użytkowników i przyznawanie uprawnień administracyjnych do usługi Intune

[!INCLUDE [both-portals](../../intune-classic/includes/note-for-both-portals.md)]

Jako administrator możesz bezpośrednio dodawać użytkowników lub synchronizować użytkowników w lokalnej usłudze Active Directory. Po dodaniu użytkownicy mogą rejestrować urządzenia i uzyskiwać dostęp do zasobów firmy. Użytkownikom możesz też przyznawać dodatkowe uprawnienia, takie jak uprawnienia *administratora globalnego* i *administratora usługi*.

## <a name="add-users-to-intune"></a>Dodawanie użytkowników do usługi Intune
Można ręcznie dodawać użytkowników do subskrypcji usługi Intune za pośrednictwem [centrum administracyjnego platformy Microsoft 365](https://admin.microsoft.com) lub [witryny Azure Portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview). Administrator może edytować konta użytkowników w celu przypisania licencji usługi Intune. Możesz przypisać licencje w centrum administracyjnym platformy Microsoft 365 albo portalu usługi Intune na platformie Azure. Aby uzyskać więcej informacji dotyczących korzystania z centrum administracyjnego platformy Microsoft 365, zobacz [Pojedyncze lub zbiorcze dodawanie użytkowników do centrum administracyjnego platformy Microsoft 365](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="add-intune-users-in-the-microsoft-365-admin-center"></a>Dodawanie użytkowników usługi Intune w centrum administracyjnym platformy Microsoft 365
1. Zaloguj się do [centrum administracyjnego platformy Microsoft 365](https://admin.microsoft.com) za pomocą konta administratora globalnego lub administratora zarządzającego użytkownikami.
2. W menu usługi Office 365 wybierz pozycję **Administracja**.
3. W centrum administracyjnym wybierz pozycję **Dodaj użytkownika**.

   ![Zrzut ekranu przedstawiający sekcję Dodawanie użytkownika](./media/users-add/office-add-user.png)

4. Określ następujące dane użytkownika:
   - **Imię**
   - **Nazwisko**
   - **Nazwa wyświetlana**
   - **Nazwa użytkownika** — uniwersalna nazwa główna (nazwa UPN) przechowywana w usłudze Azure Active Directory używana do uzyskania dostępu do usługi
   - **Lokalizacja**
   - **Informacje kontaktowe** (opcjonalnie)
   - **Hasło** — generowane automatycznie lub określone

     ![Zrzut ekranu przedstawiający sekcję Nowy użytkownik](./media/users-add/office-add-user-details.png)

5. Przypisz licencję usługi Intune. Wybierz pozycję **Licencje produktów** i wybierz licencję produktu. Wymagana jest licencja obejmująca usługę Intune.
6. Wybierz pozycję **Dodaj**, aby utworzyć nowego użytkownika.

### <a name="add-intune-users-in-the-azure-portal"></a>Dodawanie użytkowników usługi Intune w witrynie Azure Portal
1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Użytkownicy** > **Wszyscy użytkownicy**.
3. W centrum administracyjnym wybierz pozycję **Nowy użytkownik**.
   ![Zrzut ekranu przedstawiający dodawanie nowego użytkownika](./media/users-add/intune-add-user.png)
4. Określ następujące dane użytkownika:
   - **Nazwa**
   - **Nazwa użytkownika** — nowa nazwa w portalu usługi Azure Active Directory ![Zrzut ekranu przedstawiający dodawanie nazwy i nazwy użytkownika](./media/users-add/intune-add-user-info.png). Wybierz przycisk **OK**, aby kontynuować.
5. Opcjonalnie możesz określić następujące właściwości użytkownika:
   - **Profil** — informacje służbowe, w tym **Stanowisko** i **Dział**
   - **Grupy** — wybierz grupy do dodania dla użytkownika
   - **Rola katalogu** — przyznaj użytkownikowi uprawnienia administracyjne, w tym rolę administratora usługi Intune.

   Wybierz pozycję **Utwórz**, aby dodać nowego użytkownika do usługi Intune.
6. Wybierz pozycję **Profil**, a następnie wybierz pozycję **Lokalizacja użycia** dla nowego użytkownika. Lokalizacja użycia jest wymagana, zanim będzie można przypisać licencję usługi Intune do nowego użytkownika. Wybierz przycisk **Zapisz**, aby kontynuować.
    ![Zrzut ekranu przedstawiający lokalizację użytkowania](./media/users-add/intune-add-user-loc.png)
7. Wybierz pozycję **Licencje**, a następnie wybierz pozycję **Przypisz**, aby przypisać licencję usługi Intune do tego użytkownika. Licencja usługi Intune jest wymagana, aby zarejestrować urządzenia lub uzyskać dostęp do zasobów firmy. Wybierz pozycję **Produkty**, wybierz typ licencji, wybierz pozycję **Wybierz**, a następnie wybierz pozycję **Przypisz**.

## <a name="grant-admin-permissions"></a>Przyznawanie uprawnień administracyjnych

Po dodaniu użytkowników do subskrypcji usługi Intune zaleca się przyznanie uprawnień administracyjnych kilku użytkownikom.  Aby przyznać uprawnienia administracyjne, wykonaj następujące kroki:

### <a name="give-admin-permissions-in-office-365"></a>Nadawanie uprawnień administratora w usłudze Office 365
1. Zaloguj się do [centrum administracyjnego platformy Microsoft 365](https://admin.microsoft.com) przy użyciu konta administratora globalnego.
2. W menu usługi Office 365 wybierz pozycję **Administracja**.
3. W centrum administracyjnym wybierz pozycję **Aktywni użytkownicy**, a następnie wybierz użytkownika, któremu chcesz przyznać uprawnienia administratora.

4. W kolumnie **Role** wybierz pozycję **Edytuj**.

    ![Zrzut ekranu przedstawiający administratora](./media/users-add/office-assign-roles-open.png)

5. Z listy dostępnych ról wybierz uprawnienia administratora, które mają zostać przyznane.
![Zrzut ekranu przedstawiający przypisywanie ról](./media/users-add/office-assign-roles.png)
6. Wybierz polecenie **Zapisz**.

### <a name="give-admin-permissions-in-the-azure-portal"></a>Nadawanie uprawnień administratora w witrynie Azure Portal
1. Zaloguj się do [witryny Azure Portal](https://portal.azure.com) przy użyciu konta administratora globalnego.
2. W witrynie Azure Portal wybierz pozycję **Użytkownik**, a następnie wybierz użytkownika, któremu chcesz nadać uprawnienia administratora.
3. Wybierz pozycję **Rola katalogu**, a następnie wybierz uprawnienie.
  ![Zrzut ekranu przedstawiający rolę katalogu](./media/users-add/add-intune-directory-role.png)
4. Wybierz polecenie **Zapisz**.

### <a name="types-of-administrators"></a>Typy administratorów

Przypisz użytkownikom co najmniej jedne uprawnienia administratora. Uprawnienia te definiują zakres administracyjny użytkowników i zadania, którymi mogą zarządzać. Uprawnienia administratorów są wspólne w różnych usługach firmy Microsoft w chmurze, chociaż niektóre uprawnienia mogą nie być obsługiwane w pewnych usługach. W witrynie Azure Portal i centrum administracyjnym platformy Microsoft 365 jest wyświetlana lista ograniczonych ról administratora, które nie są używane przez usługę Intune. Uprawnienia administratora usługi Intune obejmują następujące opcje:

- **Administrator globalny** — (usługa Office 365 i Intune) ma dostęp do wszystkich funkcji administracyjnych w usłudze Intune. Domyślnie osoba, która zarejestruje się w usłudze Intune staje się administratorem globalnym. Administratorzy globalni są jedynymi administratorami, którzy mogą przypisywać pozostałe role administratora. W organizacji może być więcej niż jeden administrator globalny. Najlepszym rozwiązaniem jest przypisanie tej roli tylko kilku osobom w firmie, ponieważ pozwala to ograniczyć potencjalne zagrożenia.
- **Administrator haseł** — (usługa Office 365 i Intune) resetuje hasła, zarządza żądaniami obsługi i monitoruje kondycję usługi. Administratorzy haseł mogą jedynie resetować hasła użytkowników.
- **Administrator usługi** — (usługa Office 365 i Intune) otwiera żądania pomocy technicznej przesyłane do firmy Microsoft oraz przegląda pulpit nawigacyjny i centrum wiadomości usługi. Ma uprawnienia tylko do wyświetlania z wyjątkiem otwierania biletów pomocy technicznej oraz ich odczytywania.
- **Administrator rozliczeń** — (usługa Office 365 i Intune) dokonuje zakupów, zarządza subskrypcjami, zarządza biletami pomocy technicznej i monitoruje kondycję usługi.
- **Administrator użytkowników** — (usługa Office 365 i Intune) resetuje hasła, monitoruje kondycję usługi, dodaje i usuwa konta użytkowników oraz zarządza żądaniami obsługi. Administrator zarządzający użytkownikami nie może usunąć administratora globalnego, tworzyć innych ról administratora ani resetować haseł innych administratorów.
- **Administrator usługi Intune** — ma wszystkie uprawnienia administratora globalnego usługi Intune z wyjątkiem uprawnienia do tworzenia administratorów za pomocą opcji **Rola katalogu**.

Konto użyte do utworzenia subskrypcji usługi Microsoft Intune jest administratorem globalnym. Najlepszym rozwiązaniem jest nieużywanie konta administratora globalnego do wykonywania codziennych zadań zarządzania. Mimo że administrator nie wymaga licencji usługi Intune na dostęp do usługi Intune w witrynie Azure Portal, to w celu wykonania pewnych zadań zarządzania, takich jak konfigurowanie konektora usługi Exchange, wymagana jest licencja usługi Intune.

Aby uzyskać dostęp do centrum administracyjnego platformy Microsoft 365, Twoje konto musi mieć ustawioną opcję **Logowanie dozwolone**. W witrynie Azure Portal w obszarze **Profil** ustaw wartość opcji **Blokuj logowanie** na **Nie**, aby zezwolić na dostęp. Ten stan nie oznacza posiadania licencji na korzystanie z subskrypcji. Domyślnie wszystkie konta użytkowników mają stan **Dozwolone**. Użytkownicy bez uprawnień administratora mogą używać centrum administracyjnego platformy Microsoft 365 do resetowania haseł usługi Intune.

## <a name="sync-active-directory-and-add-users-to-intune"></a>Synchronizacja usługi Active Directory i dodawanie użytkowników do usługi Intune
Istnieje możliwość skonfigurowania synchronizacji katalogów w celu zaimportowania kont użytkowników z lokalnej usługi Active Directory do usługi Microsoft Azure Active Directory (Azure AD), co obejmuje użytkowników usługi Intune. Połączenie lokalnej usługi Active Directory z wszystkimi usługami opartymi na usłudze Azure Active Directory znacznie ułatwia zarządzanie tożsamościami użytkowników. Można także skonfigurować funkcje logowania jednokrotnego, aby znacznie ułatwić uwierzytelnianie użytkowników. Dzięki połączeniu tej samej [dzierżawy usługi Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) z wieloma usługami wcześniej zsynchronizowane konta użytkowników są dostępne dla wszystkich usług w chmurze.

### <a name="how-to-sync-on-premises-users-with-azure-ad"></a>Jak zsynchronizować użytkowników lokalnych z usługą Azure AD
Jedynym narzędziem potrzebnym do synchronizowania kont użytkowników z usługą Azure AD jest [Kreator Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594). Kreator Azure AD Connect zapewnia uproszczoną obsługę i przewodnik łączenia lokalnej infrastruktury tożsamości z chmurą. Wybierz topologię i potrzeby (jeden lub wiele katalogów, synchronizację skrótów haseł, uwierzytelnianie przekazywane lub federację). Kreator wdroży i skonfiguruje wszystkie składniki wymagane do uruchomienia połączenia. Dotyczy to następujących składników: usług synchronizacji, Usług federacyjne Active Directory (AD FS) i modułu Azure AD PowerShell.

> [!TIP]
> Kreator Azure AD Connect obejmuje funkcje, które były wcześniej dostępne w narzędziach Dirsync i Azure AD Sync. Dowiedz się więcej na temat [integracji katalogów](https://technet.microsoft.com/library/jj573653.aspx). Aby dowiedzieć się więcej o synchronizowaniu kont użytkowników z katalogu lokalnego do usługi Azure AD, zobacz [Podobieństwa między usługami Active Directory i Azure AD](https://technet.microsoft.com/library/dn518177.aspx).