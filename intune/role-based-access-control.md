---
title: Kontrola RBAC w usłudze Microsoft Intune
description: Dowiedz się, jak kontrola dostępu na podstawie ról (RBAC) umożliwia kontrolowanie, kto może wykonywać akcje i wprowadzać zmiany w usłudze Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 02/27/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: edf17d98bb733f7567a615eec856fb7122ba251b
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/17/2018
---
# <a name="role-based-administration-control-rbac-with-microsoft-intune"></a>Kontrola dostępu na podstawie ról (kontrola RBAC) w usłudze Microsoft Intune

Kontrola RBAC ułatwia kontrolowanie, kto może wykonywać różne zadania usługi Intune w organizacji i kogo te zadania dotyczą. Możesz użyć wbudowanych ról, które obejmują kilka typowych scenariuszy usługi Intune, lub utworzyć własne. Rolę definiują następujące właściwości:

- **Definicja roli**: nazwa roli, zarządzane przez nią zasoby oraz uprawnienia nadane dla każdego zasobu.
- **Elementy członkowskie**: grupy użytkowników, którym nadano uprawnienia.
- **Zakres**: grupy użytkowników lub urządzeń, którymi mogą zarządzać elementy członkowskie.
- **Przypisanie**: po skonfigurowaniu definicji, elementów członkowskich i zakresu jest przypisywana rola.

![Przykład kontroli RBAC przy użyciu usługi Intune](./media/intune-rbac-1.PNG)

Od momentu udostępnienia nowej witryny Azure Portal usługa **Azure Active Directory (Azure AD)** zapewnia dwie role katalogu, których można użyć z usługą Intune. Tym rolom nadaje się pełne uprawnienia do wykonywania wszystkich działań w usłudze Intune:

- **Administrator globalny:** użytkownicy posiadający tę rolę mają dostęp do wszystkich funkcji administracyjnych w usłudze Azure AD oraz usług, które federują do usługi Azure AD, np. Exchange Online, SharePoint Online oraz Skype dla firm Online. Osoba, która zarejestruje się dla dzierżawcy usługi Azure AD staje się administratorem globalnym. Tylko administratorzy globalni mogą przypisywać pozostałe role administratorów usługi Azure AD. Dana organizacja może mieć więcej niż jednego administratora globalnego. Administratorzy globalni mogą resetować hasła dla wszystkich użytkowników oraz wszystkich pozostałych administratorów.

- **Administrator usługi Intune:** użytkownicy posiadający tę rolę mają globalne uprawnienia w ramach usługi Intune, gdy usługa ta jest dostępna. Ponadto oprócz zastępowanych ograniczeń platformy Azure ta rola zapewnia możliwość zarządzania użytkownikami, urządzeniami oraz tworzenia grup usługi Intune i zarządzania nimi.

- **Administrator dostępu warunkowego:** użytkownicy posiadający tę rolę mają uprawnienia tylko do wyświetlania, tworzenia, modyfikowania i usuwania zasad dostępu warunkowego.

    > [!IMPORTANT]
    > Rola administratora usługi Intune nie zapewnia możliwości zarządzania ustawieniami dostępu warunkowego usługi Azure AD.

    > [!TIP]
    > Usługa Intune wyświetla również trzy rozszerzenia usługi Azure AD: **Użytkownicy**, **Grupy** oraz **Dostęp warunkowy**, które są kontrolowane za pomocą usługi Azure AD RBAC. Ponadto **Administrator konta użytkownika** wykonuje tylko działania użytkownika/grupy usługi AAD i nie ma pełnych uprawnień do wykonywania wszystkich działań w usłudze Intune. Aby uzyskać więcej szczegółowych informacji, zobacz temat [RBAC with Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles) (Kontrola RBAC przy użyciu usługi Azure AD).

## <a name="roles-created-in-the-intune-classic-portal"></a>Role utworzone w portalu klasycznym usługi Intune

Tylko użytkownicy usługi Intune **Administratorzy usługi** z pełnymi uprawnieniami są migrowani z portalu klasycznego usługi Intune do usługi Intune w witrynie Azure Portal. Musisz ponownie przypisać użytkowników usługi Intune **Administratorów usługi** z dostępem „Tylko do odczytu” lub „Pomoc techniczna” do ról usługi Intune w witrynie Azure Portal i usunąć ich z portalu klasycznego.

> [!IMPORTANT]
> Może być konieczne zachowanie dostępu Administratora usługi Intune w portalu klasycznym, jeśli administratorzy będą nadal potrzebować dostępu do zarządzania komputerami przy użyciu usługi Intune.

## <a name="built-in-roles"></a>Wbudowane role

Poniższe role są wbudowane w usługę Intune i można je przypisać do grup bez dalszej konfiguracji:

- **Pracownik punktu pomocy**: wykonuje zadania zdalne na użytkownikach i urządzeniach i może przypisywać aplikacje lub zasady do użytkowników lub urządzeń.
- **Menedżer zasad i profilów**: zarządza zasadami zgodności, profilami konfiguracji i rejestracją Apple oraz identyfikatorami urządzeń firmowych.
- **Operator tylko do odczytu**: wyświetla informacje o użytkownikach, urządzeniach, rejestracji, konfiguracji i aplikacji. Nie może wprowadzać zmian w usłudze Intune.
- **Menedżer aplikacji**: zarządza aplikacjami mobilnymi i zarządzanymi i może odczytywać informacje o urządzeniu.
- **Administrator szkoły**: zarządza urządzeniami z systemem Windows 10 w usłudze [Intune for Education](introduction-intune-education.md) i może wykonywać następujące akcje: 

|Uprawnienie|Operacja|
|---|---|
|Inspekcja danych|Odczyt|
|DeviceConfigurations|Przypisywanie, tworzenie, usuwanie, odczyt, aktualizowanie|
|Menedżerowie rejestracji urządzeń|Odczyt, aktualizowanie|
|Urządzenia zarządzane|Odczyt, aktualizowanie<!--, Delete [To be added in 1803]-->|
|Aplikacje mobilne|Przypisywanie, tworzenie, usuwanie, odczyt, aktualizowanie|
|Reports|Odczyt|
|Zdalne działania|Czyszczenie komputera, ponowny rozruch, zdalne blokowanie, wycofywanie, synchronizowanie urządzeń, czyszczenie|
|Organizacja|Odczyt|

### <a name="to-assign-a-built-in-role"></a>Aby przypisać rolę wbudowaną

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Role usługi Intune**, a następnie wybierz pozycję **Wszystkie role**.
1. W okienku **Role usługi Intune — Wszystkie role** wybierz rolę wbudowaną, którą chcesz przypisać.

2. W okienku <*nazwa roli*> — **Omówienie** wybierz pozycję **Zarządzaj**, a następnie wybierz pozycję **Przypisania**.

    > [!NOTE]
    > Nie można usunąć ani edytować ról wbudowanych

3. W okienku roli niestandardowej wybierz pozycję **Przypisz**.

4. W okienku **Przypisania ról** uzupełnij pole **Nazwa** i opcjonalne pole **Opis** odnoszące się do przypisania, po czym wybierz następujące właściwości:
    - **Członkowie** — wybierz grupę, do której należy użytkownik, któremu chcesz nadać uprawnienia.
    - **Zakres** — wybierz grupę, do której należą użytkownicy, którymi będzie mógł zarządzać wskazany wcześniej członek.
<br></br>
5. Gdy wszystko będzie gotowe, kliknij przycisk **OK**. Nowe przypisanie zostanie wyświetlone na liście przypisań.

### <a name="intune-rbac-table"></a>Tabela kontroli RBAC przy użyciu usługi Intune

- Pobierz [tabelę kontroli RBAC przy użyciu usługi Intune](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a), aby poznać więcej szczegółów na temat możliwości każdej roli.

## <a name="custom-roles"></a>Role niestandardowe

Można utworzyć rolę niestandardową, która zawiera wszystkie uprawnienia wymagane dla funkcji określonego zadania. Na przykład jeśli grupa działu IT zarządza aplikacjami, zasadami i profilami konfiguracji, można dodać wszystkie te uprawnienia razem do jednej roli niestandardowej.

> [!IMPORTANT]
> Aby możliwe było tworzenie, edytowanie i przypisywanie ról, konto musi mieć w usłudze Azure AD jedno z następujących uprawnień:
> - **Administrator globalny**
> - **Administrator usługi Intune**

### <a name="to-create-a-custom-role"></a>Aby utworzyć rolę niestandardową

1. Zaloguj się do [witryny Azure Portal](https://portal.azure.com) przy użyciu poświadczeń usługi Intune.

2. W menu po lewej stronie wybierz pozycję **Wszystkie usługi**, a następnie w filtrze pola tekstowego wpisz **Intune**.

3. Wybierz pozycję **Intune**, a kiedy zostanie otwarty Pulpit nawigacyjny usługi Intune, wybierz pozycję **Role usługi Intune**.

4. W okienku **Role usługi Intune** wybierz pozycję **Wszystkie role** i wybierz pozycję **Dodaj niestandardowe**.

5. W okienku **Dodaj rolę niestandardową** wprowadź nazwę i opis nowej roli, a następnie kliknij pozycję **Uprawnienia**.

3. W okienku **Uprawnienia** wybierz uprawnienia do użycia w ramach tej roli. Użyj [tabeli Intune RBAC](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) aby określić uprawnienia, które chcesz zastosować.

4. Gdy wszystko będzie gotowe, wybierz pozycję **OK**.

5. W okienku **Dodaj rolę niestandardową** kliknij pozycję **Utwórz**. Nowa rola zostanie wyświetlona na liście w okienku **Role usługi Intune — Wszystkie role**.

### <a name="to-assign-a-custom-role"></a>Aby przypisać rolę niestandardową

1. W okienku **Role usługi Intune — Wszystkie role** wybierz rolę niestandardową, którą chcesz przypisać.

2. W okienku <*nazwa roli*> — **Omówienie** wybierz pozycję **Zarządzaj**, a następnie wybierz pozycję **Przypisania**. W tym okienku możesz również edytować i usuwać istniejące role.

3. W okienku roli niestandardowej wybierz pozycję **Przypisz**.

4. W okienku **Przypisania ról** uzupełnij pole **Nazwa** i opcjonalne pole **Opis** odnoszące się do przypisania, po czym wybierz następujące właściwości:
    - **Członkowie** — wybierz grupę, do której należy użytkownik, któremu chcesz nadać uprawnienia.
    - **Zakres** — wybierz grupę, do której należą użytkownicy, którymi będzie mógł zarządzać wskazany wcześniej członek.
<br></br>
5. Gdy wszystko będzie gotowe, kliknij przycisk **OK**. Nowe przypisanie zostanie wyświetlone na liście przypisań.

## <a name="next-steps"></a>Następne kroki

[Użyj roli operatora pomocy technicznej usługi Intune w portalu do rozwiązywania problemów](help-desk-operators.md)

## <a name="see-also"></a>Zobacz też

[Przypisz role przy użyciu usługi Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal)
