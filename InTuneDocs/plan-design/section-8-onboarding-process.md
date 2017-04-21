---
title: "Proces dołączania do usługi Intune | Microsoft Docs"
description: "Ten artykuł zawiera wszystkie szczegółowe informacje, które należy wziąć pod uwagę podczas dołączania opartego tylko na chmurze rozwiązania Intune do własnego środowiska."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac7bd764-5365-4920-8fd0-ea57d5ebe039
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 23d40a31c43a061e0f3b1fbb05827697ca7380ac
ms.lasthandoff: 04/14/2017


---

# <a name="intune-implementation"></a>Implementacja usługi Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Podczas fazy dołączania usługa Intune będzie implementowana w środowisku produkcyjnym. Proces wdrażania będzie obejmować instalowanie i konfigurowanie usługi Intune oraz zależności zewnętrznych (jeśli są wymagane) na podstawie [wymagań przypadków użycia](section-3-determine-use-case-requirements.md), których przegląd miał miejsce w poprzednich sekcjach tego przewodnika.

W poniższej sekcji znajduje się omówienie procesu implementacji usługi Intune, który obejmuje wymagania i zadania wysokiego poziomu.

>[!TIP]
> Aby uzyskać więcej informacji na temat procesu implementacji usługi Intune, zobacz [Dodatkowe zasoby](additional-resources.md).

## <a name="intune-requirements"></a>Wymagania usługi Intune

Główne wymagania autonomicznej usługi Intune są przedstawione poniżej:

-   Subskrypcja pakietu EMS/usługi Intune

-   Subskrypcja usługi Office 365 (w przypadku aplikacji pakietu Office i aplikacji zarządzanych przez zasady zarządzania aplikacjami mobilnymi)

-   Certyfikat Apple APNs (w celu włączenia zarządzanie platformą urządzeń z systemem iOS)

-   Program Azure AD Connect (do synchronizacji katalogów)

-   Łącznik On-Premises Connector programu Exchange (na potrzeby urzędu certyfikacji lokalnej instalacji programu Exchange, w razie potrzeby)

-   Łącznik certyfikatów usługi Intune (na potrzeby wdrożenia certyfikatu SCEP, w razie potrzeby)

>[!TIP]
> Więcej informacji o wymaganiach autonomicznej usługi Intune można znaleźć [tutaj](https://docs.microsoft.com/intune/get-started/what-to-know-before-you-start-microsoft-intune).

## <a name="intune-implementation-process"></a>Proces implementacji usługi Intune

### <a name="overview-of-implementation-tasks"></a>Przegląd zadań implementacji

Poniżej przedstawiono omówienie poszczególnych zadań podczas implementowania usługi Intune.

#### <a name="task-1-add-intune-subscription"></a>Zadanie 1. Dodawanie subskrypcji usługi Intune

Zgodnie z tym, co określono w poprzedniej sekcji, subskrypcja pakietu EMS lub usługi Intune jest wymagana. Jeśli Twoja organizacja nie ma subskrypcji pakietu EMS lub usługi Intune, skontaktuj się z firmą Microsoft lub zespołem konta Microsoft w celu wyrażenia zainteresowania zakupem pakietu Enterprise Mobility + Security (EMS) lub usługi Intune.

-   Dowiedz się więcej na temat [zakupu usługi Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-pricing).

#### <a name="task-2-add-office-365-subscription"></a>Zadanie 2. Dodawanie subskrypcji usługi Office 365

Ta czynność jest opcjonalna. Zgodnie z tym, co określono w poprzedniej sekcji dotyczącej wymagań, subskrypcja usługi Office 365 jest wymagana, jeśli planowane jest używanie usługi Exchange Online i zarządzanie aplikacjami mobilnymi pakietu Office za pomocą zasad zarządzania aplikacjami mobilnymi. Jeśli Twoja organizacja nie ma subskrypcji usługi Office 365, skontaktuj się z firmą Microsoft lub zespołem konta Microsoft w celu wyrażenia zainteresowania zakupem usługi Office 365.

-   Dowiedz się więcej na temat [zakupu usługi Office 365](https://products.office.com/business/compare-office-365-for-business-plans).

#### <a name="task-3-add-users-groups-in-azure-ad"></a>Zadanie 3. Dodawanie grup użytkowników w usłudze Azure AD

Może być konieczne dodanie użytkowników lub grup zabezpieczeń w usłudze AD lub AAD na podstawie scenariuszy przypadków użycia dotyczących wdrożenia usługi Intune. Należy przejrzeć bieżących użytkowników i bieżące grupy zabezpieczeń w usłudze Active Directory lub Azure Active Directory i określić, czy w pełni spełniają one potrzeby. Najczęściej ma miejsce dodawanie nowych użytkowników i grup zabezpieczeń w usłudze Active Directory, a następnie synchronizowanie ich w usłudze Azure Active Directory za pomocą programu Azure AD Directory Connect.

-   Dowiedz się więcej na temat [dodawania użytkowników i grup w usłudze Intune](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3).

#### <a name="task-4-assign-intune-and-office-365-user-licenses"></a>Zadanie 4. Przypisywanie licencji użytkowników usługi Intune i Office 365

Wszyscy użytkownicy, które będą objęci wdrożeniem pakietu EMS/usługi Intune i usługi Office 365 muszą mieć przypisaną licencję. Przypisanie licencji pakietu EMS/Intune i usługi Office 365 może mieć miejsce w portalu Centrum administracyjnego usługi Office 365.

-   Dowiedz się więcej na temat [przypisywania licencji usługi Intune](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4).

#### <a name="task-5-set-mobile-device-management-authority-to-intune"></a>Zadanie 5. Ustawianie usługi Intune jako urzędu zarządzania urządzeniami przenośnymi

Przed rozpoczęciem instalacji, konfigurowania i rejestrowania urządzeń oraz zarządzania nimi za pomocą usługi Intune należy ustawić usługę Intune jako urząd zarządzania urządzeniami. Zadanie ustawiania urzędu zarządzania urządzeniami jest wykonywane w portalu administracyjnym usługi Intune w obszarze roboczym Administracja.

-   Dowiedz się więcej na temat [ustawiania urzędu zarządzania urządzeniami](https://docs.microsoft.com/intune/deploy-use/prerequisites-for-enrollment#step-2-set-mdm-authority).

#### <a name="task-6-enable-device-platforms"></a>Zadanie 6. Włączanie platformy urządzeń

Domyślnie w konsoli administracyjnej usługi Intune większość platform urządzeń jest włączona, z wyjątkiem urządzeń firmy Apple (system iOS i komputery Mac). Zanim możliwe będzie zarejestrowanie urządzeń z systemem iOS w usłudze Intune i zarządzanie nimi należy włączyć platformę urządzenia. Proces włączenia platformy urządzenia z systemem iOS składa się z trzech kroków: utworzenia i pobrania certyfikatu APNs oraz przekazania tego certyfikatu do usługi Intune.

-   Dowiedz się więcej na temat [konfiguracji zarządzania systemem iOS i komputerami Mac](https://docs.microsoft.com/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).

#### <a name="task-7-add-and-deploy-terms-and-conditions-policies"></a>Zadanie 7. Dodawanie i wdrażanie zasad dotyczących warunków i postanowień

Usługa Microsoft Intune obsługuje dodawanie i wdrażanie zasad dotyczących warunków i postanowień. Dodawanie i wdrażanie zasad dotyczących warunków i postanowień odbywa się w portalu administracyjnym usługi Intune w obszarze Zasady. Dodaj odpowiednie zasady dotyczące warunków i postanowień i wdróż je w grupach docelowych na podstawie przypadków użycia i wymagań dotyczących wdrożenia.

-   Dowiedz się więcej na temat [dodawania i wdrażania zasad dotyczących warunków i postanowień](https://docs.microsoft.com/intune/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune).

#### <a name="task-8-add-and-deploy-configuration-policies"></a>Zadanie 8. Dodawanie i wdrażanie zasad konfiguracji

Usługa Microsoft Intune obsługuje dodawanie i wdrażanie dwóch typów zasad konfiguracji — ogólnych i niestandardowych. Dodawanie i wdrażanie zasad konfiguracji odbywa się w portalu administracyjnym usługi Intune w obszarze Zasady. Dodaj odpowiednie zasady konfiguracji i wdróż je w grupach docelowych na podstawie przypadków użycia i wymagań dotyczących wdrożenia.

-   Dowiedz się więcej na temat [dodawania i wdrażania zasad konfiguracji](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).

#### <a name="task-9-add-and-deploy-resource-profiles"></a>Zadanie 9. Dodawanie i wdrażanie profilów zasobów

Usługa Microsoft Intune obsługuje profile poczty E-mail, sieci Wi-Fi i sieci VPN. Dodawanie i wdrażanie profilów odbywa się w portalu administracyjnym usługi Intune w obszarze Zasady. Dodaj odpowiednie profile poczty E-mail, sieci Wi-Fi lub sieci VPN i wdróż je w grupach docelowych na podstawie przypadków użycia i wymagań dotyczących wdrożenia.

-   Dowiedz się więcej na temat [zapewniania dostępu do zasobów firmy przy użyciu usługi Intune](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune).

#### <a name="task-10-add-and-deploy-apps"></a>Zadanie 10. Dodawanie i wdrażanie aplikacji

Usługa Microsoft Intune obsługuje wdrażanie aplikacji sieci Web, aplikacji biznesowych i publicznych aplikacji ze Sklepu. Dodatkowo obsługiwane jest zarządzanie aplikacjami, w których zintegrowano zestaw SDK usługi Intune przez skojarzenie ich z zasadami zarządzania aplikacjami mobilnymi. Dodawanie i wdrażanie aplikacji odbywa się w portalu administracyjnym usługi Intune w obszarze Zasady. Dodawanie zasad zarządzania aplikacjami mobilnymi odbywa się w portalu administracyjnym usługi Intune w obszarze Zasady. Dodaj odpowiednie aplikacje i wdróż je w grupach docelowych na podstawie przypadków użycia i wymagań dotyczących wdrożenia.

-   Dowiedz się więcej na temat [dodawania i wdrażania aplikacji](https://docs.microsoft.com/intune/deploy-use/deploy-apps).

#### <a name="task-11-add-and-deploy-compliance-policies"></a>Zadanie 11. Dodawanie i wdrażanie zasad zgodności

Usługa Microsoft Intune obsługuje zasady zgodności. Dodawanie i wdrażanie zasad zgodności odbywa się w portalu administracyjnym usługi Intune w obszarze Zasady. Dodaj odpowiednie zasady zgodności i wdróż je w grupach docelowych na podstawie przypadków użycia i wymagań dotyczących wdrożenia.

-   Dowiedz się więcej na temat [zasad zgodności](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).

#### <a name="task-12-enable-conditional-access-policies"></a>Zadanie 12. Włączanie zasad dostępu warunkowego

Usługa Microsoft Intune obsługuje dostęp warunkowy dla usługi Exchange Online i lokalnej instalacji programu Exchange, usługi SharePoint Online, usługi Skype dla firm Online i usługi Dynamics CRM Online. Zasady dostępu warunkowego można włączyć w portalu administracyjnym usługi Intune w obszarze roboczym Zasady. Włącz i skonfiguruj odpowiedni dostęp warunkowy na podstawie [przypadków użycia i wymagań dotyczących wdrożenia usługi Intune](section-3-determine-use-case-requirements.md).

-   Dowiedz się więcej na temat [dostępu warunkowego](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

#### <a name="task-13-enroll-devices"></a>Zadanie 13. Rejestrowanie urządzeń

Usługa Intune obsługuje platformy urządzeń przenośnych z systemem iOS, Mac OS, Android, Windows Desktop i Windows Mobile. Zarejestruj odpowiednie platformy urządzeń przenośnych na podstawie przypadków użycia i wymagań dotyczących wdrożenia usługi Intune.

-   Dowiedz się więcej na temat [rejestrowania urządzeń](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune).

>[!TIP]
> Zapoznaj się z tym [modułem sesji dotyczącym usługi Intune w wirtualnej akademii firmy Microsoft](https://mva.microsoft.com/training-courses/deploying-microsoft-enterprise-mobility-suite-16408?l=PPWNoZxvD_1404778676), aby uzyskać więcej informacji na temat procesu implementowania usługi Intune.

## <a name="next-section"></a>Następna sekcja

Następna sekcja zawiera wskazówki dotyczące [testowania i sprawdzania poprawności wdrożenia usługi Intune](section-9-test-and-validation.md).

