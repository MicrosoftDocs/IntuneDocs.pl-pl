---
title: "Dodawanie użytkowników i przyznawanie uprawnień | Microsoft Docs"
description: "Synchronizowanie lokalnych użytkowników z usługą Azure AD i przyznawanie uprawnień administratora dla subskrypcji usługi Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ad13897fe7bbe4fe13167bb4ce7f558b436a7a90
ms.openlocfilehash: b1f16df329c01aeb45885f3981e2d9d7ef854e8b


---

# <a name="add-users-and-give-administrative-permission-to-intune"></a>Dodawanie użytkowników i przyznawanie uprawnień administracyjnych do usługi Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ten temat zawiera informacje dla administratorów dotyczące dodawania użytkowników do usługi Intune oraz uprawnień administracyjnych dostępnych w usłudze Intune.

Jako administrator możesz bezpośrednio dodawać użytkowników lub synchronizować użytkowników w lokalnej usłudze Active Directory. Po dodaniu użytkownicy mogą rejestrować urządzenia i uzyskiwać dostęp do zasobów firmy. Możesz również przyznawać użytkownikom dodatkowe uprawnienia, takie jak uprawnienia *administratora dzierżawy*, *administratora usługi* i *menedżera rejestracji urządzeń*.

Ten temat zawiera informacje przydatne podczas takich działań, jak:

- [Dodawanie użytkowników do usługi Intune](#add-users-to-intune)
- [Przyznawanie dodatkowych uprawnień dotyczących usługi Intune](#grant-intune-permissions), w tym następujących ról:
  - [Administrator dzierżawy](#tenant-administrator)
  - [Administrator usługi](#service-administrator)
  - [Menedżerowie rejestracji urządzeń](#device-enrollment-managers)

## <a name="add-users-to-intune"></a>Dodawanie użytkowników do usługi Intune
Możesz ręcznie dodawać użytkowników do subskrypcji usługi Intune za pośrednictwem [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854), ale licencja usługi Intune nie jest do nich przypisywana automatycznie. Zamiast tego administrator dzierżawy usługi Intune musi później edytować konto użytkownika w portalu usługi Office 365 w celu przypisania licencji do użytkownika. Aby uzyskać instrukcje, zobacz temat [Pojedyncze lub zbiorcze dodawanie użytkowników do usługi Office 365](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="sync-active-directory-and-add-users-to-intune"></a>Synchronizacja usługi Active Directory i dodawanie użytkowników do usługi Intune
Istnieje możliwość skonfigurowania synchronizacji katalogów w celu zaimportowania kont użytkowników z lokalnej usługi Active Directory do usługi Microsoft Azure Active Directory (Azure AD), co obejmuje użytkowników usługi Intune. Połączenie lokalnej usługi Active Directory z wszystkimi usługami opartymi na usłudze Azure Active Directory znacznie ułatwia zarządzanie tożsamościami użytkowników. Można także skonfigurować funkcje logowania jednokrotnego, aby znacznie ułatwić uwierzytelnianie użytkowników. Dzięki połączeniu tej samej [dzierżawy usługi Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) z wieloma usługami wcześniej zsynchronizowane konta użytkowników są dostępne dla wszystkich usług w chmurze.

### <a name="how-to-sync-on-premises-users-with-azure-ad"></a>Jak zsynchronizować użytkowników lokalnych z usługą Azure AD
Jedynym narzędziem potrzebnym do synchronizowania kont użytkowników z usługą Azure AD jest [Kreator Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594). Kreator Azure AD Connect zapewnia uproszczoną obsługę i przewodnik łączenia lokalnej infrastruktury tożsamości z chmurą.  Określ topologię i potrzeby (jeden lub wiele katalogów, synchronizacja haseł lub federacja), a kreator wdroży i skonfiguruje wszystkie elementy wymagane do uruchomienia połączenia. Dotyczy to następujących składników: usług synchronizacji, Usług federacyjne Active Directory (AD FS) i modułu Azure AD PowerShell.

> [!TIP]
> Kreator Azure AD Connect obejmuje funkcje, które były wcześniej dostępne w narzędziach Dirsync i Azure AD Sync. Dowiedz się więcej na temat [integracji katalogów](http://technet.microsoft.com/library/jj573653.aspx). Aby poznać zalety synchronizowania kont użytkowników z katalogu lokalnego do usługi Azure AD, zobacz [Podobieństwa między usługami Active Directory i Azure AD](http://technet.microsoft.com/library/dn518177.aspx).

## <a name="grant-intune-permissions"></a>Przyznawanie uprawnień dotyczących usługi Intune

Po dodaniu użytkowników do subskrypcji usługi Intune zaleca się przyznanie uprawnień administracyjnych kilku kontom użytkowników. Do celów administrowania usługą Intune można nadać użytkownikom trzy typy uprawnień
-   **Administrator dzierżawy**: skorzystaj z portalu usługi Office 365, aby przypisać ten typ administratora umożliwiający zarządzanie subskrypcją, w tym rozliczeniami, magazynem w chmurze oraz użytkownikami, którzy mogą korzystać z usługi Intune.
-   **Administrator usługi**: użyj konsoli administratora usługi Microsoft Intune, aby przypisać ten typ administratora umożliwiający wykonywanie typowych zadań, takich jak zarządzanie urządzeniami i komputerami, wdrażanie zasad i aplikacji oraz uruchamianie raportów.
-   **Menedżer rejestracji urządzeń**: użyj konsoli administratora usługi Microsoft Intune, aby przypisać ten typ administratora umożliwiający wykonywanie typowych zadań, takich jak zarządzanie urządzeniami i komputerami, wdrażanie zasad i aplikacji oraz uruchamianie raportów.


### <a name="tenant-administrator"></a>Administrator dzierżawy


Administratorzy dzierżawy mają przypisaną jedną rolę określającą ich zakres administracyjny i zadania, którymi mogą zarządzać. Role administratorów są wspólne w różnych usługach firmy Microsoft w chmurze, chociaż niektóre role mogą nie być obsługiwane we wszystkich usługach. W usłudze Intune są używane następujące role:
- **Administrator globalny** — ma dostęp do wszystkich funkcji administracyjnych w usłudze Intune. Domyślnie osoba, która zarejestruje się w usłudze Intune staje się administratorem globalnym. Administratorzy globalni są jedynymi administratorami, którzy mogą przypisywać pozostałe role administratora. W organizacji może być więcej niż jeden administrator globalny. Najlepszym rozwiązaniem jest przypisanie tej roli tylko kilku osobom w firmie, ponieważ pozwala to ograniczyć potencjalne zagrożenia.
- **Administrator rozliczeń** — dokonuje zakupów, zarządza subskrypcjami, zarządza biletami pomocy technicznej i monitoruje kondycję usługi.
- **Administrator haseł** — resetuje hasła, zarządza żądaniami obsługi i monitoruje kondycję usługi. Administratorzy haseł mogą jedynie resetować hasła użytkowników.
- **Administrator pomocy technicznej dotyczącej usług** — otwiera żądania pomocy technicznej przesyłane do firmy Microsoft oraz przegląda pulpit nawigacyjny usług i centrum wiadomości. Ma uprawnienia tylko do wyświetlania z wyjątkiem otwierania biletów pomocy technicznej oraz ich odczytywania.
- **Administrator zarządzający użytkownikami** — resetuje hasła, monitoruje kondycję usługi, dodaje i usuwa konta użytkowników oraz zarządza żądaniami obsługi. Administrator zarządzający użytkownikami nie może usunąć administratora globalnego, tworzyć innych ról administratora ani resetować haseł administratorów rozliczeń, administratorów globalnych i administratorów pomocy technicznej dotyczącej usług.

Domyślnie do utworzenia subskrypcji usługi Microsoft Intune służy konto administratora dzierżawy z rolą administratora globalnego. Administrator dzierżawy używa konsoli administratora usługi Intune do zarządzania subskrypcją usługi Intune oraz do przypisywania administratorów dzierżaw z [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854). Aby uzyskać dostęp do portalu w celu przypisania pierwszego administratora usługi, należy użyć konta administratora dzierżawy z rolą administratora globalnego. Dobrą praktyką jest nieużywanie konta administratora dzierżawy na potrzeby wykonywania typowych zadań zarządzania. Administrator dzierżawy nie musi dysponować licencją na korzystanie z usługi Intune, aby uzyskać dostęp do konsoli administratora usługi Intune. Administrator dzierżawy jest wspólnym pojęciem w usługach w chmurze firmy Microsoft. Subskrybowana usługa Intune jest dzierżawą usługi Azure AD. Aby uzyskać więcej informacji, zobacz sekcję dotyczącą dzierżaw usługi Azure AD w temacie [Co to jest katalog usługi Azure AD?](http://technet.microsoft.com/library/jj573650.aspx).

Administrator dzierżawy używa [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) do zarządzania subskrypcją, co obejmuje wykonywanie następujących zadań, o ile jest to dozwolone przez rolę administratora:

- Zarządzanie kontami użytkowników i konfigurowanie synchronizacji katalogów z lokalnej usługi Active Directory
- Zarządzanie grupami użytkowników zwanymi grupami zabezpieczeń
- Przypisywanie licencji użytkowników usługi Intune
- Konfigurowanie nazwy domeny dla subskrypcji używanej do logowania przez użytkowników (np. contoso.com)
- Zarządzanie rozliczeniami i zakupami, w tym licencjami i miejscem do magazynowania w chmurze
- Znajdowanie linków umożliwiających wyświetlenie kondycji usługi Intune

Aby użytkownik mógł uzyskać dostęp do portalu usługi Office 365, jego konto musi mieć stan logowania **Dozwolone**. Ten stan nie oznacza posiadania licencji na korzystanie z subskrypcji. Domyślnie wszystkie konta użytkowników mają stan **Dozwolone**. Użytkownicy bez uprawnień administratora mogą używać portalu usługi Office 365 do resetowania haseł usługi Intune.

### <a name="service-administrator"></a>Administrator usługi

Domyślnie w usłudze Intune nie ma przypisanego administratora usługi. Z tego powodu w celu przypisania pierwszego administratora usługi dla subskrypcji należy użyć konta administratora dzierżawy z rolą administratora globalnego. Administrator usługi zarządza typowymi zadaniami usługi Intune za pomocą [konsoli administratora usługi Intune](https://manage.microsoft.com/). Przypisywanie administratorów usługi odbywa się przy użyciu konsoli administratora. Aby uzyskać dostęp do konsoli administratora, administrator usługi musi dysponować licencją na usługę Intune.

Administratorzy usługi mają jedne z poniższych uprawnień:
- **Pełny dostęp**: nieograniczony dostęp do wszystkich obszarów konsoli administratora usługi Intune, dodawanie innych administratorów usługi oraz zarządzanie nimi
- **Dostęp tylko do odczytu**: uprawnienia do odczytu wszystkich obszarów konsoli administratora usługi Intune, brak możliwości modyfikowania danych, ale możliwe jest uruchamianie raportów
- **Pomoc techniczna — węzeł Grupy**: umożliwia administratorowi usługi wykonywanie tylko zadań skojarzonych ze scenariuszami pomocy technicznej. Zobacz temat [Dostosowywanie widoków konsoli usługi Intune zgodnie z rolami administratora](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console)

Administrator usługi korzysta z tego portalu do zarządzania typowymi operacjami, które obejmują:

- Tworzenie zasad dla komputerów i urządzeń przenośnych oraz zarządzanie nimi
- Przekazywanie i wdrażanie aktualizacji oprogramowania i aplikacji
- Zarządzanie programem Endpoint Protection na komputerach
- Wyświetlanie stanu urządzeń i uruchamianie raportów

### <a name="device-enrollment-managers"></a>Menedżerowie rejestracji urządzeń

Menedżerowie rejestracji urządzeń to standardowi użytkownicy z dodatkowymi uprawnieniami do rejestrowania wielu urządzeń bez użytkowników. Domyślnie każdy użytkownik usługi Intune może zarejestrować maksymalnie piętnaście urządzeń. Administrator może przypisać do konta użytkownika uprawnienia menedżera rejestracji urządzeń. To konto może zarejestrować dużą liczbę urządzeń firmowych. Jest to przydatne, gdy urządzenia są tymczasowo przypisane do użytkowników lub pracują w trybie kiosku, który nie wymaga takiego przypisania. Aby uzyskać więcej informacji, zobacz temat [Menedżer rejestracji urządzeń](https://docs.microsoft.com/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

>[!div class="step-by-step"]

>[&larr;**Ustawienia domeny**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Zarządzanie licencjami usługi Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  



<!--HONumber=Feb17_HO3-->


