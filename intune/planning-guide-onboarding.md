---
title: Proces dołączania do usługi Intune
titlesuffix: Microsoft Intune
description: Ten artykuł zawiera wszystkie szczegółowe informacje, które należy wziąć pod uwagę podczas dołączania opartego tylko na chmurze rozwiązania Microsoft Intune do własnego środowiska.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ac7bd764-5365-4920-8fd0-ea57d5ebe039
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: d5c1fb2b6b20c9687418e14f8e35543c04833a25
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52186396"
---
# <a name="implement-your-microsoft-intune-plan"></a>Implementowanie planu dotyczącego usługi Microsoft Intune

Podczas fazy dołączania usługa Intune jest wdrażana w środowisku produkcyjnym. Proces wdrażania obejmuje instalowanie oraz konfigurowanie usługi Intune i zależności zewnętrznych (jeśli są wymagane) na podstawie [wymagań przypadków użycia](planning-guide-requirements.md).

W poniższej sekcji znajduje się omówienie procesu implementacji usługi Intune, który obejmuje wymagania i zadania wysokiego poziomu.

## <a name="intune-requirements"></a>Wymagania usługi Intune

Główne wymagania autonomicznej usługi Intune to:

-   Subskrypcja pakietu Enterprise Mobility + Security (EMS)/usługi Intune

-   Subskrypcja usługi Office 365 (w przypadku aplikacji pakietu Office i aplikacji zarządzanych za pomocą zasad ochrony aplikacji)

-   Certyfikat Apple APNs (w celu włączenia zarządzanie platformą urządzeń z systemem iOS)

-   Program Azure AD Connect (do synchronizacji katalogów)

-   Lokalny łącznik usługi Intune dla programu Exchange (na potrzeby dostępu warunkowego do lokalnego programu Exchange, w razie potrzeby)

-   Łącznik certyfikatów usługi Intune (na potrzeby wdrożenia certyfikatu SCEP, w razie potrzeby)

>[!TIP]
> Zobacz listę [obsługiwanych urządzeń](supported-devices-browsers.md), którymi można zarządzać w usłudze Intune.

## <a name="intune-implementation-process"></a>Proces implementacji usługi Intune

Określiliśmy 13 odrębnych zadań wykonywanych w celu wdrożenia usługi Intune. W zależności od wymagań biznesowych, istniejącej infrastruktury i strategii zarządzania urządzeniami niektóre z tych zadań mogą już być ukończone. Inne osoby nie mogą korzystać z Twojego planu.

### <a name="task-1-get-an-intune-subscription"></a>Zadanie 1. Uzyskiwanie subskrypcji usługi Intune

Jak wskazano w powyższej sekcji „Wymagania usługi Intune”, niezbędna jest subskrypcja pakietu EMS lub usługi Intune. Jeśli Twoja organizacja nie ma żadnej z tych subskrypcji, skontaktuj się z firmą Microsoft lub zespołem konta Microsoft, aby wyrazić zainteresowanie zakupem pakietu Enterprise Mobility + Security (EMS) lub usługi Intune.

-   Dowiedz się więcej na temat [zakupu usługi Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-pricing).

### <a name="task-2-add-office-365-subscription"></a>Zadanie 2. Dodawanie subskrypcji usługi Office 365

Ta czynność jest opcjonalna. Jeśli planujesz używanie usługi Exchange Online i chcesz zarządzać aplikacjami mobilnymi pakietu Office przy użyciu zasad ochrony aplikacji, niezbędna jest subskrypcja usługi Office 365. Jeśli Twoja organizacja nie ma subskrypcji usługi Office 365, skontaktuj się z firmą Microsoft lub zespołem konta Microsoft, aby wyrazić zainteresowanie zakupem usługi Office 365.

-   Dowiedz się więcej na temat [zakupu usługi Office 365](https://products.office.com/business/compare-office-365-for-business-plans).

### <a name="task-3-add-users-groups-in-azure-ad"></a>Zadanie 3. Dodawanie grup użytkowników w usłudze Azure AD

Może być konieczne dodanie użytkowników lub grup zabezpieczeń w usłudze Active Directory lub usłudze Azure Active Directory na podstawie scenariuszy przypadków użycia dotyczących wdrożenia usługi Intune. Należy przejrzeć bieżących użytkowników i bieżące grupy zabezpieczeń w usłudze Active Directory lub Azure Active Directory i określić, czy w pełni spełniają one potrzeby. Firma Microsoft zaleca, aby nowych użytkowników i nowe grupy zabezpieczeń dodawać w usłudze Active Directory i synchronizować z usługą Azure Active Directory za pomocą programu Azure AD Connect.


-   Dowiedz się więcej na temat [dodawania użytkowników i grup w usłudze Intune](users-permissions-add.md).
<!---why not send them to the AAD connect topic? Question out to Andre: https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect--->



### <a name="task-4-assign-intune-and-office-365-user-licenses"></a>Zadanie 4. Przypisywanie licencji użytkowników usługi Intune i Office 365

Wszyscy użytkownicy objęci wdrożeniem pakietu EMS/usługi Intune i usługi Office 365 muszą mieć przypisaną licencję. Licencje pakietu EMS/usługi Intune i usługi Office 365 można przypisać w portalu Centrum administracyjnego usługi Office 365.

-   Dowiedz się więcej na temat [przypisywania licencji usługi Intune](licenses-assign.md).

### <a name="task-5-set-mobile-device-management-authority-to-intune"></a>Zadanie 5. Ustawianie usługi Intune jako urzędu zarządzania urządzeniami przenośnymi

Przed rozpoczęciem instalacji, konfigurowania i rejestrowania urządzeń oraz zarządzania nimi za pomocą usługi Intune należy ustawić usługę Intune jako urząd zarządzania urządzeniami.

-   Dowiedz się więcej na temat [ustawiania urzędu zarządzania urządzeniami](mdm-authority-set.md).

### <a name="task-6-enable-device-platforms"></a>Zadanie 6. Włączanie platformy urządzeń

Domyślnie większość platform urządzeń jest włączona — z wyjątkiem urządzeń firmy Apple (system iOS i komputery Mac). Zanim możliwe będzie zarejestrowanie urządzeń z systemem iOS w usłudze Intune i zarządzanie nimi należy włączyć platformę urządzenia. Aby to zrobić, należy utworzyć certyfikat wypychania MDM i dodać go do usługi Intune.

-   Dowiedz się więcej o [włączaniu urządzeń firmy Apple do rejestracji](apple-mdm-push-certificate-get.md).

### <a name="task-7-add-and-deploy-terms-and-conditions-policies"></a>Zadanie 7. Dodawanie i wdrażanie zasad dotyczących warunków i postanowień

Usługa Intune obsługuje zasady dotyczące warunków i postanowień. Dodaj odpowiednie zasady dotyczące warunków i postanowień i wdróż je w grupach docelowych na podstawie przypadków użycia i wymagań dotyczących wdrożenia.

-   Dowiedz się więcej na temat [dodawania i wdrażania zasad dotyczących warunków i postanowień](terms-and-conditions-create.md).

### <a name="task-8-add-and-deploy-configuration-policies"></a>Zadanie 8. Dodawanie i wdrażanie zasad konfiguracji

Usługa Intune obsługuje dwa typy zasad konfiguracji — ogólne i niestandardowe. Dodaj odpowiednie zasady konfiguracji i wdróż je w grupach docelowych na podstawie przypadków użycia i wymagań dotyczących wdrożenia.

-   Dowiedz się więcej na temat [dodawania i wdrażania zasad konfiguracji](device-profiles.md).

### <a name="task-9-add-and-deploy-resource-profiles"></a>Zadanie 9. Dodawanie i wdrażanie profilów zasobów

Usługa Intune obsługuje profile poczty e-mail, sieci Wi-Fi i sieci VPN. Dodaj odpowiednie profile i wdróż je w grupach docelowych na podstawie przypadków użycia i wymagań dotyczących wdrożenia.

-   Dowiedz się więcej na temat [sposobów zapewniania dostępu do zasobów firmy przy użyciu usługi Intune](device-profiles.md).

### <a name="task-10-add-and-deploy-apps"></a>Zadanie 10. Dodawanie i wdrażanie aplikacji

Usługa Intune obsługuje wdrażanie aplikacji internetowych, aplikacji biznesowych i publicznych aplikacji ze Sklepu. Dodatkowo możliwe jest zarządzanie aplikacjami, w których zintegrowano zestaw Intune SDK przez skojarzenie ich z zasadami ochrony aplikacji. Dodaj odpowiednie aplikacje i wdróż je w grupach docelowych na podstawie przypadków użycia i wymagań dotyczących wdrożenia.

-   Dowiedz się więcej o [dodawaniu i wdrażaniu aplikacji](app-management.md).

### <a name="task-11-add-and-deploy-compliance-policies"></a>Zadanie 11. Dodawanie i wdrażanie zasad zgodności

Usługa Intune obsługuje zasady zgodności. Dodaj odpowiednie zasady zgodności i wdróż je w grupach docelowych na podstawie przypadków użycia i wymagań dotyczących wdrożenia.

-   Dowiedz się więcej na temat [zasad zgodności](device-compliance.md).

### <a name="task-12-enable-conditional-access-policies"></a>Zadanie 12. Włączanie zasad dostępu warunkowego

Usługa Intune obsługuje dostęp warunkowy dla usługi Exchange Online, lokalnej instalacji programu Exchange, usługi SharePoint Online, usługi Skype dla firm Online i usługi Dynamics CRM Online. Włącz i skonfiguruj odpowiedni dostęp warunkowy na podstawie przypadków użycia i wymagań dotyczących wdrożenia usługi Intune.

-   Dowiedz się więcej na temat [dostępu warunkowego](conditional-access.md).

### <a name="task-13-enroll-devices"></a>Zadanie 13. Rejestrowanie urządzeń

Usługa Intune obsługuje platformy urządzeń przenośnych z systemem iOS, Mac OS, Android, Windows Desktop i Windows Mobile. Zarejestruj odpowiednie platformy urządzeń przenośnych na podstawie przypadków użycia i wymagań dotyczących wdrożenia usługi Intune.

-   Dowiedz się więcej na temat [rejestrowania urządzeń](device-enrollment.md).


## <a name="next-steps"></a>Następne kroki

Zapoznaj się z tym [modułem sesji dotyczącym usługi Intune w wirtualnej akademii firmy Microsoft](https://mva.microsoft.com/en-US/training-courses/deploying-microsoft-enterprise-mobility-suite-16408), aby uzyskać więcej informacji na temat procesu implementowania usługi Intune.


Zobacz wskazówki dotyczące [testowania i weryfikowania wdrożenia usługi Intune](planning-guide-test-validation.md).
