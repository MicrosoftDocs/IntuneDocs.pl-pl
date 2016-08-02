---
title: "Przygotowanie do konfigurowania zasad zarządzania aplikacjami mobilnymi | Microsoft Intune"
description: "W tym temacie opisano wymagania wstępne i konfigurowanie użytkowników przed przystąpieniem do tworzenia zasad zarządzania aplikacjami mobilnymi."
keywords: 
author: karthikaraman
manager: arob98
ms.date: 07/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2038ed6219a94dc4285891d71ce00fd51310f3e3
ms.openlocfilehash: 39af738fe83ec6ea2e963d857cc233332063c80b


---

# Przygotowywanie się do skonfigurowania zasad zarządzania aplikacjami mobilnymi przy użyciu usługi Microsoft Intune
W tym temacie opisano, co należy zrobić przed rozpoczęciem tworzenia zasad zarządzania aplikacjami mobilnymi w portalu Azure.

Portal Azure to nowa konsola administracyjna do tworzenia zasad zarządzania aplikacjami mobilnymi. Zaleca się używanie tego portalu do tworzenia zasad zarządzania aplikacjami mobilnymi. Portal Azure obsługuje następujące scenariusze zarządzania aplikacjami mobilnymi:
- Urządzenia, które zostały zarejestrowane w usłudze Intune
- Urządzenia zarządzane przez rozwiązanie MDM innej firmy
- Urządzenia niezarządzane przez żadne rozwiązanie MDM (BYOD)

Jeśli używasz portalu Azure po raz pierwszy, przeczytaj temat [Portal Azure — zasady zarządzania aplikacjami mobilnymi](azure-portal-for-microsoft-intune-mam-policies.md), aby szybko zapoznać się z portalem.

>[!IMPORTANT]

> Jeśli obecnie używasz konsoli administracyjnej usługi Intune do zarządzania urządzeniami, możesz utworzyć zasady zarządzania aplikacjami mobilnymi obsługujące aplikacje dla urządzeń zarejestrowanych w usłudze Intune przy użyciu konsoli administracyjnej usługi Intune. Jednak zaleca się korzystanie z portalu Azure, nawet w przypadku urządzeń, które są zarejestrowane w usłudze Intune. Aby uzyskać informacje o tworzeniu zasad zarządzania aplikacjami mobilnymi przy użyciu konsoli administracyjnej usługi Intune, zobacz [Konfigurowanie i wdrażanie zasad zarządzania aplikacjami mobilnymi w konsoli usługi Microsoft Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).

> W konsoli administracyjnej usługi Intune mogą nie być wyświetlane wszystkie ustawienia zasad zarządzania aplikacjami mobilnymi. Jeśli utworzysz zasady zarządzania aplikacjami mobilnymi zarówno za pomocą konsoli administracyjnej usługi Intune, jak i portalu Azure, zasady utworzone w portalu Azure zostaną zastosowane dla aplikacji i wdrożone dla użytkowników.
> Zasady zarządzania aplikacjami mobilnymi utworzone w konsoli administracyjnej usługi Intune nie mogą być importowane do portalu Azure.  Zasady zarządzania aplikacjami mobilnymi muszą zostać ponownie utworzone w portalu Azure.


##  Obsługiwane platformy
- System iOS 8.1 lub nowszy

- System Android 4 lub nowszy

Urządzenia z systemem Windows nie są obecne obsługiwane.
##  Obsługiwane aplikacje
* **Aplikacje firmy Microsoft:** te aplikacje mają wbudowany zestaw SDK aplikacji usługi Intune i nie wymagają dalszego przetwarzania przed zastosowaniem zasad zarządzania aplikacjami mobilnymi.
Pełna lista obsługiwanych aplikacji firmy Microsoft jest dostępna w [galerii aplikacji mobilnych usługi Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) na stronie partnerów aplikacji usługi Microsoft Intune. Kliknij aplikację, aby wyświetlić obsługiwane scenariusze i platformy, a także sprawdzić, czy aplikacja obsługuje wiele tożsamości.
* **Aplikacje biznesowe Twojej organizacji:** wymagają przygotowania aplikacji do dołączenia do nich zestawu SDK aplikacji usługi Intune, zanim będzie możliwe zastosowanie zasad zarządzania aplikacjami mobilnymi.

  * W przypadku urządzeń zarządzanych przez usługę Intune zobacz [Decide how to prepare apps for MAM](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md) (Wybieranie sposobu przygotowania aplikacji do zarządzania aplikacjami mobilnymi).
  * W przypadku urządzeń niezarządzanych (takich jak urządzenia należące do pracowników) lub urządzeń zarządzanych przez rozwiązanie do zarządzania urządzeniami przenośnymi oferowane przez inną firmę, zobacz [Protect line-of-business apps and data on devices not enrolled in Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md) (Chronienie aplikacji biznesowych i danych na niezarejestrowanych urządzeniach w usłudze Intune).

*Przed* rozpoczęciem konfigurowania zasad zarządzania aplikacjami mobilnymi potrzebne będą:

-   Subskrypcja usługi Microsoft Intune.    Użytkownicy potrzebują licencji usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] w celu pobierania aplikacji z zasadami zarządzania aplikacjami mobilnymi.

-   Subskrypcja usługi Office 365, która jest wymagana do:
  - Stosowania zasad zarządzania aplikacjami mobilnymi do aplikacji z obsługą wielu tożsamości.
  - Tworzenia kont służbowych usług SharePoint Online i Exchange Online. Lokalna instalacja programu Exchange i lokalna instalacja programu SharePoint nie są obsługiwane.
-   Konfiguracja programu Skype dla firm Online dla nowoczesnego uwierzytelniania. Aby uzyskać więcej informacji, zobacz [Włączanie nowoczesnego uwierzytelniania](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx.md).


- Usługa Azure Active Directory (Azure AD) do tworzenia użytkowników. Usługa Azure AD uwierzytelnia użytkowników, gdy otworzą oni aplikację i wprowadzą poświadczenia robocze.

    > [!NOTE]
    > Jeśli konfigurujesz użytkowników przy użyciu konsoli usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], pamiętaj, że konfiguracja zasad zarządzania aplikacjami mobilnymi jest przenoszona do portalu Azure. Aby korzystać z tego portalu, musisz skonfigurować grupy użytkowników usługi Azure AD za pomocą portalu usługi Office 365.


## Tworzenie użytkowników i przypisywanie licencji usługi Microsoft Intune

1. Upewnij się, że masz subskrypcję usługi Intune. Jeśli aktualnie używasz usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] do zarządzania urządzeniami, masz już subskrypcję usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].  Masz również subskrypcję usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], jeśli masz kupioną licencję pakietu Enterprise Mobility Suite (EMS). Jeśli wypróbowujesz usługę [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] w celu zapoznania się z możliwościami w zakresie zarządzania aplikacjami mobilnymi, konto próbne możesz uzyskać [na stronie usługi Microsoft Intune](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/).

    Aby sprawdzić, czy masz subskrypcję usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], przejdź do strony **Rozliczenia** w portalu usługi Office.  Usługa [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] powinna być widoczna jako **Aktywna** w obszarze subskrypcji.

2.  Zaloguj się do [portalu usługi Office](http://portal.office.com) przy użyciu poświadczeń administratora.

3.  Przejdź do strony **Aktywni użytkownicy**, aby dodać użytkowników i przypisać licencje usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    ![Strona Aktywni użytkownicy w portalu usługi Office](../media/AppManagement/OfficePortal_AddUsers.png)

    ![Strona Edytowanie użytkownika w portalu usługi Office](../media/AppManagement/OfficePortal_AssignLicenses.png)

4.  Aby dać użytkownikowi możliwość dostępu do portalu usługi Office, portalu usługi Azure AD i portalu Azure, przypisz użytkownikowi **rolę administratora globalnego**.

    ![Strona do edycji ról użytkowników w portalu usługi Office](../media/AppManagement/OfficePortal_AddRoletoUser.png)

5.  Zasady zarządzania aplikacjami mobilnymi są wdrażane dla grup użytkowników w usłudze Azure Active Directory. Aby utworzyć grupy użytkowników dla zasad zarządzania aplikacjami mobilnymi, przejdź do strony **Grupy** w portalu usługi Office i wybierz opcję **Dodaj grupę** w menu górnym, aby utworzyć nową grupę zabezpieczeń.  Wpisz nazwę i opis, a następnie kliknij pozycję **Utwórz**. Po utworzeniu grupy możesz dodać do niej użytkowników, klikając pozycję **Edytuj członków**. W usłudze Azure Active Directory zostanie utworzona grupa zabezpieczeń.

    ![Strona dla grup zabezpieczeń w portalu usługi Office](../media/AppManagement/OfficePortal_CreateGroups.png)

W poniższej tabeli zamieszczono role i uprawnienia, które można przypisać administratorom.

|||
|--|----|
|**Rola**|**Uprawnienia**|
|Administrator globalny (portal usługi Office 365)|Dostęp do portalu usługi Office 365 i portalu usługi Azure AD.<br /><br />Dostęp do portalu Azure (możliwość zarządzania rolami i aplikacjami mobilnymi).|
|Właściciel (portal Azure)|Dostęp do portalu Azure (możliwość zarządzania rolami i aplikacjami mobilnymi).|
|Współautor (portal Azure)|Dostęp do portalu Azure (tylko możliwość zarządzania aplikacjami mobilnymi).|

## Przypisywanie użytkownikowi roli współautora

Administratorzy globalni mają dostęp do [portalu Azure](https://portal.azure.com).  Jeśli chcesz, aby inni administratorzy mogli konfigurować zasady oraz wykonywać inne zadania związane z zarządzaniem aplikacjami mobilnymi, możesz przypisać użytkownikom rolę współautora:


1.  W bloku **Ustawienia** w sekcji **Zarządzanie zasobami** kliknij pozycję **Użytkownicy**.

    ![Blok użytkowników w portalu Azure](../media/AppManagement/AzurePortal_MAM_AddUsers.png)

2.  Kliknij pozycję **Dodaj** , aby otworzyć blok **Dodawanie dostępu** .

3.  Kliknij pozycję **Wybierz rolę**, a następnie pozycję **Współautor**.

    ![Blok wyboru roli w portalu Azure](../media/AppManagement/AzurePortal_MAM_AddRole.png)

4.  Kliknij przycisk **Dodaj użytkownika** i wyszukaj użytkownika według nazwy lub adresu e-mail. Użytkownicy widoczni na tej liście to pierwszych 1000 użytkowników utworzonych wcześniej w usłudze Azure AD za pomocą portalu usługi Office. Kliknij przycisk **OK** w bloku **Dodawanie dostępu**, aby zapisać i przypisać rolę użytkownikowi.

    ![Blok dodawania użytkowników w portalu Azure](../media/AppManagement/AzurePortal_MAM_AddusertoRole.png)

    > [!IMPORTANT]
    > Jeśli zostanie wybrany użytkownik bez przypisanej licencji usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] , nie będzie on w stanie uzyskiwać dostępu do portalu.

## Następne kroki
[Tworzenie i wdrażanie zasad zarządzania aplikacjami mobilnymi przy użyciu usługi Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


