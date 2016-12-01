---
title: "Synchronizacja usługi Active Directory i dodawanie użytkowników do usługi Intune | Microsoft Intune"
description: "Synchronizowanie lokalnych użytkowników z usługą Azure AD i przyznawanie uprawnień administratora dla subskrypcji usługi Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 29b6e5a3d319c741482fcc2b600842e2e42b96e2
ms.openlocfilehash: 33534c685ad3a4ddfd4b605e088132f2b8ff2c36


---


# <a name="sync-active-directory-and-add-users-to-intune"></a>Synchronizacja usługi Active Directory i dodawanie użytkowników do usługi Intune
Istnieje możliwość skonfigurowania synchronizacji katalogów w celu zaimportowania kont użytkowników z lokalnej usługi Active Directory do usługi Microsoft Azure Active Directory (Azure AD). Połączenie lokalnej usługi Active Directory z wszystkimi usługami opartymi na usłudze Azure Active Directory znacznie ułatwia zarządzanie tożsamościami użytkowników. Można także skonfigurować funkcje logowania jednokrotnego, aby znacznie ułatwić uwierzytelnianie użytkowników.

Ponadto w przypadku korzystania z wielu usług za pomocą tej samej [dzierżawy usługi Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) zsynchronizowane konta użytkowników są dostępne dla wszystkich usług w chmurze, które współużytkują tę samą subskrypcję dzierżawy usługi Azure AD.

## <a name="synchronize-on-premises-users-with-azure-ad"></a>Synchronizowanie lokalnych użytkowników z usługą Azure AD
Jedynym narzędziem potrzebnym do synchronizowania kont użytkowników z usługą Azure AD jest [Kreator Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594). Kreator Azure AD Connect zapewnia uproszczoną obsługę i przewodnik łączenia lokalnej infrastruktury tożsamości z chmurą.  Określ topologię i potrzeby (jeden lub wiele katalogów, synchronizacja haseł lub federacja), a kreator wdroży i skonfiguruje wszystkie elementy wymagane do uruchomienia połączenia. Dotyczy to następujących składników: usług synchronizacji, Usług federacyjne Active Directory (AD FS) i modułu Azure AD PowerShell.

> [!TIP]
> Kreator Azure AD Connect obejmuje funkcje, które były wcześniej dostępne w narzędziach Dirsync i Azure AD Sync. Dowiedz się więcej na temat [integracji katalogów](http://technet.microsoft.com/library/jj573653.aspx). Aby poznać zalety synchronizowania kont użytkowników z katalogu lokalnego do usługi Azure AD, zobacz [Podobieństwa między usługami Active Directory i Azure AD](http://technet.microsoft.com/library/dn518177.aspx).

## <a name="grant-administrator-permissions"></a>Udzielanie uprawnień administratora

Do administrowania usługą Intune służą:
- Dwa typy kont administratora
- Konta użytkowników z dodatkowymi uprawnieniami
- Dwie konsole administracyjne/portale oparte na sieci Web, zapewniające administratorom dostęp do zarządzanych elementów.

Po dodaniu użytkowników do subskrypcji usługi Intune zalecane jest przyznanie poświadczeń administracyjnych kilku kontom użytkowników. Konsola, której należy użyć do przypisania poświadczeń administracyjnych, zależy od typu administratora, który chcesz przypisać:

-   **Administrator dzierżawy**: użyj **portalu konta usługi Microsoft Intune**, aby przypisać ten typ administratora umożliwiający zarządzanie subskrypcją, w tym rozliczeniami, magazynem w chmurze oraz użytkownikami, którzy mogą korzystać z usługi Intune.

-   **Administrator usługi**: użyj **konsoli administracyjnej usługi Microsoft Intune**, aby przypisać ten typ administratora umożliwiający wykonywanie codziennych zadań, w tym zarządzanie urządzeniami przenośnymi lub komputerami, wdrażanie zasad lub oprogramowania i uruchamianie raportów.

Opis tych kont i portali znajduje się w następujących sekcjach.

## <a name="administrator-accounts-and-user-accounts-with-special-permissions"></a>Konta administratorów i konta użytkowników z uprawnieniami specjalnymi

Poniżej przedstawiono konta i uprawnienia używane w usłudze Intune.

### <a name="tenant-administrator"></a>Administrator dzierżawy
|Poziomy uprawnień|Więcej informacji|
|--------------------------|-------------------------|
|Administratorzy dzierżawy mają przypisaną jedną rolę określającą ich zakres administracyjny i zadania, którymi mogą zarządzać.<br /><br />Role administratorów są wspólne w różnych usługach firmy Microsoft w chmurze, chociaż niektóre role mogą nie być obsługiwane we wszystkich usługach.<br /><br /> Usługa Microsoft Intune używa następujących ról:<br /><br />- Administrator globalny<br />- Administrator rozliczeń<br />- Administrator haseł<br />- Administrator pomocy technicznej usługi<br />- Administrator zarządzania użytkownikami|Domyślnie do utworzenia subskrypcji usługi Microsoft Intune służy konto administratora dzierżawy z rolą administratora globalnego.<br /></br>  Administrator dzierżawy używa narzędzia [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)] do zarządzania subskrypcją usługi Intune oraz do przypisywania administratorów dzierżaw z usługi [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />Aby uzyskać dostęp do narzędzia [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] w celu przypisania pierwszego administratora usługi, należy użyć konta administratora dzierżawy z rolą administratora globalnego. Dobrą praktyką jest nieużywanie konta administratora dzierżawy na potrzeby wykonywania typowych zadań zarządzania. Administrator dzierżawy nie musi dysponować licencją na korzystanie z usługi Intune, aby uzyskać dostęp do narzędzia [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />Administrator dzierżawy jest wspólnym pojęciem w usługach w chmurze firmy Microsoft. Subskrybowana usługa Intune jest dzierżawą usługi Microsoft Azure AD. Zobacz sekcję dotyczącą dzierżaw usługi Azure AD w temacie [Co to jest katalog usług Azure AD?](http://technet.microsoft.com/library/jj573650.aspx).|


### <a name="service-administrator"></a>Administrator usługi
|Poziomy uprawnień|Więcej informacji|
|--------------------------|-------------------------|
|Administratorzy usługi mają jedne z poniższych uprawnień:<br /><br />**Pełny dostęp:** nieograniczony dostęp do wszystkich obszarów narzędzia [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]. W ramach tych uprawnień można również dodawać pozostałych administratorów usługi i zarządzać nimi.<br /><br />**Dostęp tylko do odczytu:** uprawnienia do odczytu wszystkich obszarów narzędzia [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]. Administrator usługi z takimi uprawnieniami nie może modyfikować danych, ale może uruchamiać raporty.<br /><br />**Pomoc techniczna — węzeł Grupy:** uprawnienia umożliwiające administratorowi usługi wykonywanie wyłącznie zestawu zadań zwykle powiązanych ze scenariuszami pracy działu pomocy technicznej. Aby uzyskać informacje o tym zestawie uprawnień, zobacz [Dostosowywanie widoków konsoli usługi Intune zgodnie z rolami administratorów](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console).|Domyślnie w usłudze Intune nie ma przypisanego administratora usługi. Z tego powodu w celu przypisania pierwszego administratora usługi dla subskrypcji należy użyć konta administratora dzierżawy z rolą administratora globalnego. </br></br> Administrator usługi zarządza typowymi zadaniami usługi Intune za pomocą narzędzia [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)].<br /><br />Przypisywanie administratorów usługi odbywa się przy użyciu konsoli administratora. Aby uzyskać dostęp do konsoli administracyjnej z poziomu konta, administrator usługi musi dysponować licencją na korzystanie z usługi Intune.|



### <a name="device-enrollment-managers"></a>Menedżerowie rejestracji urządzeń
|Poziomy uprawnień|Więcej informacji|
|--------------------------|-------------------------|
|Menedżerowie rejestracji urządzeń to standardowi użytkownicy z dodatkowymi uprawnieniami umożliwiającymi zarejestrowanie więcej niż pięciu urządzeń.|Domyślnie każdy użytkownik usługi [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] może zarejestrować maksymalnie pięć urządzeń. Można jednak przyznać użytkownikowi uprawnienia menedżera rejestracji urządzeń, a następnie użyć jego konta, aby zarejestrować wiele firmowych urządzeń. Jest to przydatne, gdy urządzenia są tymczasowo przypisane do użytkowników lub pracują w trybie kiosku, który nie wymaga takiego przypisania.|




>[!div class="step-by-step"]

>[&larr;**Ustawienia domeny**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Zarządzanie licencjami usługi Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  



<!--HONumber=Nov16_HO4-->


