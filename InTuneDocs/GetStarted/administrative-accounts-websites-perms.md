---
# required metadata

title: Konta administracyjne, witryny sieci Web i uprawnienia w usłudze Microsoft Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: db3075e7-38fd-4dfe-b266-26aed10ac8ea

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Konta administracyjne, witryny sieci Web i uprawnienia w usłudze Microsoft Intune

Przed skonfigurowaniem usługi Microsoft Intune przejrzyj ten temat i inne wymagania wymienione w artykule [Co należy wiedzieć przed rozpoczęciem korzystania z usługi Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md).

Do administrowania usługą Intune służą:
- Dwa typy kont administratora
- Konta użytkowników z dodatkowymi uprawnieniami
- Dwie konsole administracyjne/portale oparte na sieci Web, zapewniające administratorom dostęp do zarządzanych elementów.

Opis tych kont i portali znajduje się w następujących sekcjach.

## Konta administratorów i konta użytkowników z uprawnieniami specjalnymi

Poniżej przedstawiono konta i uprawnienia używane w usłudze Intune.

### Administrator dzierżawy
|Poziomy uprawnień|Więcej informacji|
|--------------------------|-------------------------|
|Administratorzy dzierżawy mają przypisaną jedną rolę określającą ich zakres administracyjny i zadania, którymi mogą zarządzać.<br /><br />Role administratorów są wspólne w różnych usługach firmy Microsoft w chmurze, chociaż niektóre role mogą nie być obsługiwane we wszystkich usługach.<br /><br /> Usługa Microsoft Intune używa następujących ról:<br /><br />- Administrator globalny<br />- Administrator rozliczeń<br />- Administrator haseł<br />- Administrator pomocy technicznej usługi<br />- Administrator zarządzania użytkownikami|Domyślnie do utworzenia subskrypcji usługi Microsoft Intune służy konto administratora dzierżawy z rolą administratora globalnego.<br /></br>  Administrator dzierżawy używa narzędzia [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)] do zarządzania subskrypcją usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] oraz do przypisywania administratorów dzierżaw z [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />Aby uzyskać dostęp do narzędzia [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] w celu przypisania pierwszego administratora usługi, należy użyć konta administratora dzierżawy z rolą administratora globalnego. Dobrą praktyką jest nieużywanie konta administratora dzierżawy na potrzeby wykonywania typowych zadań zarządzania. Administrator dzierżawy nie musi mieć licencji usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], aby uzyskiwać dostęp do [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />Administrator dzierżawy jest wspólnym pojęciem w usługach w chmurze firmy Microsoft. Subskrybowana usługa [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] jest dzierżawą usługi Microsoft Azure AD. Zobacz sekcję dotyczącą dzierżaw usługi Azure AD w temacie [Co to jest katalog usług Azure AD?](http://technet.microsoft.com/library/jj573650.aspx).|


### Administrator usługi
|Poziomy uprawnień|Więcej informacji|
|--------------------------|-------------------------|
|Administratorzy usługi mają jedne z poniższych uprawnień:<br /><br />**Pełny dostęp:** nieograniczony dostęp do wszystkich obszarów narzędzia [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]. W ramach tych uprawnień można również dodawać pozostałych administratorów usługi i zarządzać nimi.<br /><br />**Dostęp tylko do odczytu:** uprawnienia do odczytu wszystkich obszarów narzędzia [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]. Administrator usługi z takimi uprawnieniami nie może modyfikować danych, ale może uruchamiać raporty.<br /><br />**Pomoc techniczna — węzeł Grupy:** uprawnienia umożliwiające administratorowi usługi wykonywanie wyłącznie zestawu zadań zwykle powiązanych ze scenariuszami pracy działu pomocy technicznej. Aby uzyskać informacje o tym zestawie uprawnień, zobacz [Dostosowywanie widoków konsoli usługi Intune zgodnie z rolami administratorów](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console).|Domyślnie w usłudze [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] nie ma przypisanego administratora usługi. Z tego powodu w celu przypisania pierwszego administratora usługi dla subskrypcji należy użyć konta administratora dzierżawy z rolą administratora globalnego. </br></br> Administrator usługi zarządza typowymi zadaniami za pomocą narzędzia [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].<br /><br />Przypisywanie administratorów usługi odbywa się przy użyciu konsoli administratora. Aby móc uzyskać dostęp do konsoli administratora, administrator usługi musi dysponować licencją na korzystanie z usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].|



### Menedżerowie rejestracji urządzeń
|Poziomy uprawnień|Więcej informacji|
|--------------------------|-------------------------|
|Menedżerowie rejestracji urządzeń to standardowi użytkownicy z dodatkowymi uprawnieniami umożliwiającymi zarejestrowanie więcej niż pięciu urządzeń.|Domyślnie każdy użytkownik usługi [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] może zarejestrować maksymalnie pięć urządzeń. Można jednak przyznać użytkownikowi uprawnienia menedżera rejestracji urządzeń, a następnie użyć jego konta, aby zarejestrować wiele firmowych urządzeń. Jest to przydatne, gdy urządzenia są tymczasowo przypisane do użytkowników lub pracują w trybie kiosku, który nie wymaga takiego przypisania.|


## Witryny internetowe umożliwiające administrowanie usługą Intune
 Różne zadania administracyjne wymagają użycia jednej z następujących administracyjnych witryn sieci Web, do których można uzyskiwać dostęp za pomocą [obsługiwanej przeglądarki sieci Web](supported-web-browsers.md)..

- [Portal usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Konsola administratora usługi Microsoft Intune](https://admin.manage.microsoft.com/)

### [Portal usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)

**Administrator dzierżawy używa tego portalu do zarządzania subskrypcją**, co obejmuje wykonywanie następujących zadań, o ile jest to dozwolone przez rolę administratora:

- Zarządzanie kontami użytkowników w ramach subskrypcji i konfigurowanie synchronizacji katalogów z lokalnej usługi Active Directory.
- Zarządzanie grupami użytkowników zwanymi grupami zabezpieczeń.
- Przypisywanie użytkownikom licencji na korzystanie z usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].
- Konfigurowanie nazwy domeny używanej w ramach subskrypcji. Nazwa domeny określa konto używane przez użytkowników do logowania.
- Zarządzanie informacjami dotyczącymi rozliczeń i zakupów w ramach subskrypcji, w tym liczbą posiadanych licencji lub ilością dostępnego miejsca w magazynie w chmurze.
- Znajdowanie linków umożliwiających wyświetlenie kondycji usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].
- Administrator dzierżawy może zalogować się do portalu usługi Office 365 w celu zarządzania subskrypcją, nawet jeśli nie ma przypisanej licencji na korzystanie z [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].
- Dowolny użytkownik, który ma licencję na korzystanie z usługi Intune, ale nie jest administratorem, może za pomocą tego portalu resetować hasło swojego konta i edytować swój profil.
- Aby użytkownik mógł uzyskać dostęp do portalu usługi Office 365, jego konto musi mieć stan logowania **Dozwolone**. Ten stan nie oznacza posiadania licencji na korzystanie z subskrypcji. Domyślnie wszystkie konta użytkowników mają stan **Dozwolone**..


### [Konsola administratora usługi Microsoft Intune](https://admin.manage.microsoft.com/)

**Administrator usługi korzysta z tego portalu do zarządzania typowymi operacjami**, które obejmują:

- Ustawianie zasad dla komputerów i urządzeń przenośnych.
- Przekazywanie i wdrażania oprogramowania, na przykład aktualizacji i aplikacji.
- Zarządzanie programem Endpoint Protection usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] na komputerach.
- Wyświetlanie stanu urządzeń i uruchamianie raportów.
- Zaloguj się do tego portalu. Aby zalogować się do tego portalu, musisz mieć uprawnienia administratora usługi lub być administratorem dzierżawy z rolą administratora globalnego.


Do tego portalu mogą logować się tylko użytkownicy z uprawnieniami administratora usługi lub administratorzy dzierżawy z rolą administratora globalnego. Aby można było uzyskać dostęp do konsoli administracyjnej, Twoje konto musi mieć licencję na korzystanie z usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] i stan logowania **Dozwolone**..

Dowiedz się więcej o [dodawaniu użytkowników do subskrypcji](start-with-a-paid-subscription-to-microsoft-intune-step-3.md) i [przypisywaniu licencji na korzystanie z subskrypcji](start-with-a-paid-subscription-to-microsoft-intune-step-4.md)..

 ### Zobacz także
 [Co należy wiedzieć przed rozpoczęciem korzystania z usługi Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)


<!--HONumber=May16_HO1-->


