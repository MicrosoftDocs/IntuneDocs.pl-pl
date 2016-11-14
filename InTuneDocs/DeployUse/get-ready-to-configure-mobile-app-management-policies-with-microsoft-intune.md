---
title: "Wymagania wstępne dotyczące zasad zarządzania aplikacjami mobilnymi | Microsoft Intune"
description: "W tym temacie opisano wymagania wstępne i konfigurowanie użytkowników przed przystąpieniem do tworzenia zasad zarządzania aplikacjami mobilnymi."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5778ccc632b72b3cca2593febeccbf7149591275
ms.openlocfilehash: 6d7843286369e2371ea204ac70d2e85e4c086d76


---

# Przygotowywanie się do skonfigurowania zasad zarządzania aplikacjami mobilnymi w portalu Azure
W tym temacie opisano wymagania wstępne oraz czynności, które należy wykonać **przed** rozpoczęciem tworzenia zasad zarządzania aplikacjami mobilnymi w portalu Azure.

Aby dowiedzieć się, w jaki sposób zasady zarządzania aplikacjami mobilnymi usługi Intune mogą chronić dane firmy, zobacz [Protect apps and data using mobile app management policies](protect-apps-and-data-with-microsoft-intune.md) (Chronienie aplikacji i danych przy użyciu zasad zarządzania aplikacjami mobilnymi).

## Co to jest portal Azure?
Portal Azure to nowa konsola administracyjna do tworzenia zasad zarządzania aplikacjami mobilnymi, która obsługuje następujące scenariusze zarządzania aplikacjami mobilnymi:
- **Urządzenia, które zostały zarejestrowane w usłudze Intune**
- **Urządzenia zarządzane przez rozwiązanie MDM innej firmy**
- **Urządzenia niezarządzane przez żadne rozwiązanie MDM (BYOD)**


Obecnie zarówno **konsola administratora usługi Intune**, jak i **portal Azure** umożliwiają skonfigurowanie zasad zarządzania aplikacjami mobilnymi.  Rozważ następujące opcje:

* Zasady utworzone w **portalu Azure** są obsługiwane we **wszystkich wymienionych powyżej scenariuszach zarządzania aplikacjami mobilnymi**. **Konsola administratora usługi Intune** obsługuje wyłącznie tworzenie zasad dla **urządzeń zarejestrowanych w usłudze Intune i zarządzanych przez nią**.
* Nie wszystkie ustawienia zasad zarządzania aplikacjami mobilnymi będą widoczne w konsoli administratora usługi Intune, ponieważ **nowe ustawienia** mogą być dodawane tylko do **portalu Azure**.
* Jeśli utworzysz zasady zarządzania aplikacjami mobilnymi **zarówno** za pomocą konsoli administracyjnej usługi Intune, jak i portalu Azure, zasady utworzone w **portalu Azure zostaną zastosowane dla aplikacji i wdrożone dla użytkowników**.
    * Zasady zarządzania aplikacjami mobilnymi utworzone w konsoli administracyjnej usługi Intune nie mogą być importowane do portalu Azure.  Zasady zarządzania aplikacjami mobilnymi muszą zostać ponownie utworzone w portalu Azure.
* Inne **funkcje zarządzania aplikacjami**, takie jak wdrażanie aplikacji i zasady konfiguracji aplikacji, są obecnie dostępne tylko w **konsoli administratora usługi Intune**.


Jeśli jesteś nowym użytkownikiem portalu Azure, zobacz [Portal Azure — zasady zarządzania aplikacjami mobilnymi](azure-portal-for-microsoft-intune-mam-policies.md), aby szybko zapoznać się z podstawowymi informacjami na temat portalu Azure.

Aby uzyskać informacje o tworzeniu zasad zarządzania aplikacjami mobilnymi w konsoli administratora usługi Intune, zobacz [Konfigurowanie i wdrażanie zasad zarządzania aplikacjami mobilnymi w konsoli usługi Microsoft Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).


##  Obsługiwane platformy
- System iOS 8.1 lub nowszy

- System Android 4 lub nowszy

>[!NOTE]
>Urządzenia z systemem Windows nie obsługują tych zasad zarządzania aplikacjami mobilnymi. Jednak podczas rejestrowania urządzeń z systemem Windows 10 w usłudze Intune możesz użyć rozwiązania Windows Information Protection, które oferuje podobne funkcje. Aby uzyskać szczegółowe informacje, zobacz [Protect your enterprise data using Windows Information Protection](https://technet.microsoft.com/en-us/itpro/windows/keep-secure/protect-enterprise-data-using-wip) (Chronienie danych przedsiębiorstwa przy użyciu rozwiązania Windows Information Protection).

##  Obsługiwane aplikacje
* **Aplikacje firmy Microsoft:** te aplikacje mają wbudowany zestaw SDK aplikacji usługi Intune i nie wymagają dalszego przetwarzania przed zastosowaniem zasad zarządzania aplikacjami mobilnymi.
Pełna lista obsługiwanych aplikacji firmy Microsoft jest dostępna w [galerii aplikacji mobilnych usługi Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) na stronie partnerów aplikacji usługi Microsoft Intune. Kliknij aplikację, aby wyświetlić obsługiwane scenariusze i platformy, a także sprawdzić, czy aplikacja obsługuje wiele tożsamości.
* **Aplikacje biznesowe Twojej organizacji:** wymagają przygotowania aplikacji do dołączenia do nich zestawu SDK aplikacji usługi Intune, zanim będzie możliwe zastosowanie zasad zarządzania aplikacjami mobilnymi.

  * W przypadku urządzeń zarządzanych przez usługę Intune zobacz [Decide how to prepare apps for MAM](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md) (Wybieranie sposobu przygotowania aplikacji do zarządzania aplikacjami mobilnymi).
  * W przypadku urządzeń niezarządzanych (takich jak urządzenia należące do pracowników) lub urządzeń zarządzanych przez rozwiązanie do zarządzania urządzeniami przenośnymi oferowane przez inną firmę, zobacz [Chronienie aplikacji biznesowych i danych na niezarejestrowanych urządzeniach w usłudze Microsoft Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

## Wymagania wstępne

-   Subskrypcja usługi Microsoft Intune.    Użytkownicy potrzebują licencji usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] w celu pobierania aplikacji z zasadami zarządzania aplikacjami mobilnymi.
Jeśli aktualnie używasz usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] do zarządzania urządzeniami, masz już subskrypcję usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].  Masz również subskrypcję usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], jeśli masz kupioną licencję pakietu Enterprise Mobility Suite (EMS). Jeśli wypróbowujesz usługę [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] w celu zapoznania się z możliwościami w zakresie zarządzania aplikacjami mobilnymi, konto próbne możesz uzyskać [na stronie usługi Microsoft Intune](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/).

    Aby sprawdzić, czy masz subskrypcję usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], przejdź do strony **Rozliczenia** w portalu usługi Office.  Usługa [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] powinna być widoczna jako **Aktywna** w obszarze subskrypcji.

-   Subskrypcja usługi Office 365, która jest wymagana do:
  - Stosowania zasad zarządzania aplikacjami mobilnymi do aplikacji z obsługą wielu tożsamości.
  - Tworzenia kont służbowych usług SharePoint Online i Exchange Online. Lokalna instalacja programu Exchange i lokalna instalacja programu SharePoint nie są obsługiwane.
-   Konfiguracja programu Skype dla firm Online dla nowoczesnego uwierzytelniania. Aby uzyskać więcej informacji, zobacz [Włączanie nowoczesnego uwierzytelniania](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).


- Usługa Azure Active Directory (Azure AD) do tworzenia użytkowników. Usługa Azure AD uwierzytelnia użytkowników, gdy otworzą oni aplikację i wprowadzą poświadczenia robocze.

    > [!NOTE]
    > Grupy użytkowników muszą być skonfigurowane w usłudze Azure AD. Grupy użytkowników usługi Intune nie mogą służyć do wdrażania zasad zarządzania aplikacjami mobilnymi w portalu Azure.

### Tworzenie użytkowników i przypisywanie licencji usługi Microsoft Intune

1.  Zaloguj się do [portalu usługi Office](http://portal.office.com) przy użyciu poświadczeń administratora.

2.  Postępując zgodnie z instrukcją w sekcji **Dodawanie użytkowników** w [tym](https://docs.microsoft.com/en-us/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-2) temacie, dodaj użytkowników i przypisz licencje usługi Intune. Aby dać użytkownikowi możliwość dostępu do portalu usługi Office, portalu usługi Azure AD i portalu Azure, przypisz użytkownikowi **rolę administratora globalnego**.

5.  Zasady zarządzania aplikacjami mobilnymi są wdrażane dla grup użytkowników w usłudze Azure Active Directory. Aby utworzyć grupy użytkowników dla zasad zarządzania aplikacjami mobilnymi, utwórz grupę użytkowników, postępując zgodnie z instrukcją w sekcji **Tworzenie grupy użytkowników** w [tym](https://docs.microsoft.com/en-us/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-3) temacie.

### Użytkownicy inni niż administratorzy globalni

Administratorzy globalni mają dostęp do [portalu Azure](https://portal.azure.com).  Jeśli chcesz, aby użytkownicy inni niż administratorzy globalni mogli konfigurować zasady oraz wykonywać inne zadania związane z zarządzaniem aplikacjami mobilnymi, możesz przypisać użytkownikom rolę współautora. Szczegółowa instrukcja znajduje się w temacie [Zarządzanie dostępem do zasobów subskrypcji platformy Azure za pomocą przypisań ról](https://azure.microsoft.com/en-us/documentation/articles/role-based-access-control-configure/).

---------------------------------

W poniższej tabeli zamieszczono role i uprawnienia, które można przypisać administratorom.

|||
|--|----|
|**Rola**|**Uprawnienia**|
|Administrator globalny (portal usługi Office 365)|Dostęp do portalu usługi Office 365 i portalu usługi Azure AD.<br /><br />Dostęp do portalu Azure (możliwość zarządzania rolami i aplikacjami mobilnymi).|
|Właściciel (portal Azure)|Dostęp do portalu Azure (możliwość zarządzania rolami i aplikacjami mobilnymi).|
|Współautor (portal Azure)|Dostęp do portalu Azure (tylko możliwość zarządzania aplikacjami mobilnymi).|




## Następne kroki
[Tworzenie i wdrażanie zasad zarządzania aplikacjami mobilnymi przy użyciu usługi Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


