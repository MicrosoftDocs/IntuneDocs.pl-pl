---
# required metadata

title: Przygotowywanie się do skonfigurowania zasad zarządzania aplikacjami mobilnymi | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Przygotowywanie się do skonfigurowania zasad zarządzania aplikacjami mobilnymi przy użyciu usługi Microsoft Intune
W tym temacie opisano, co należy zrobić przed rozpoczęciem tworzenia zasad zarządzania aplikacjami mobilnymi w portalu Azure.
Jeśli obecnie korzystasz z **konsoli administracyjnej usługi Intune** do zarządzania urządzeniami, możesz utworzyć zasady zarządzania aplikacjami mobilnym obsługujące aplikacje dla urządzeń zarejestrowanych w usłudze Intune przy użyciu [konsoli administracyjnej usługi Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).
>[!IMPORTANT]
> W konsoli administracyjnej usługi Intune mogą nie być wyświetlane wszystkie ustawienia zasad zarządzania aplikacjami mobilnymi. Portal Azure to nowa konsola administracyjna do tworzenia zasad zarządzania aplikacjami mobilnymi.

##  Obsługiwane platformy
- System iOS 8.1 lub nowszy

- System Android 4 lub nowszy

##  Obsługiwane aplikacje
Pełna lista obsługiwanych aplikacji jest dostępna w [galerii aplikacji mobilnych usługi Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) na stronie partnerów aplikacji usługi Microsoft Intune.
Kliknij aplikację, aby wyświetlić obsługiwane scenariusze i platformy, a także sprawdzić, czy aplikacja obsługuje wiele tożsamości.

**Przed** rozpoczęciem konfigurowania zasad zarządzania aplikacjami mobilnymi potrzebne będą:

-   **Subskrypcja usługi Microsoft Intune**.    Użytkownicy końcowi potrzebują licencji usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] w celu pobierania aplikacji z zasadami zarządzania aplikacjami mobilnymi.

-   Należy ustawić usługę Intune lub program Configuration Manager jako **urząd zarządzania urządzeniami przenośnymi**, zależnie od tego, czy używana jest tylko usługa **Intune**, czy program **Configuration manager** jest zintegrowany z usługą Intune w celu zarządzania urządzeniami. Jeśli używana jest wbudowana funkcja zarządzania urządzeniami przenośnymi w usłudze O365, należy zakupić subskrypcję usługi Intune i [ustawić usługę Intune jako urząd zarządzania urządzeniami przenośnymi](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority)..
-   Subskrypcja **usługi Office 365 (O365)** jest wymagana do:
  - Stosowania zasad zarządzania aplikacjami mobilnymi do aplikacji z obsługą wielu tożsamości.
  - Tworzenia kont służbowych usług SharePoint Online i Exchange Online. Lokalna instalacja programu Exchange i lokalna instalacja programu SharePoint nie są obsługiwane.


- **Usługa Azure Active Directory (Azure AD)** do tworzenia użytkowników. Usługa Azure AD uwierzytelnia użytkownika końcowego w momencie uruchomienia przez niego aplikacji i wprowadzenia poświadczeń służbowych.

    > [!NOTE]
    > Jeśli konfigurujesz użytkowników przy użyciu konsoli usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], pamiętaj, że konfiguracja zasad zarządzania aplikacjami mobilnymi będzie prowadzona od teraz w portalu Azure. Korzystanie z tego portalu wymaga skonfigurowania grup użytkowników usługi Azure AD przy użyciu portalu usługi Office 365.


## Tworzenie użytkowników i przypisywanie licencji usługi Microsoft Intune

1. Potrzebna jest subskrypcja usługi Intune: jeśli aktualnie używasz usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] do zarządzania urządzeniami, masz już subskrypcję usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] .  Masz również subskrypcję usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], jeśli masz kupioną licencję pakietu EMS. Jeśli wypróbowujesz usługę [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] w celu zapoznania się z możliwościami w zakresie zarządzania aplikacjami mobilnymi, konto próbne możesz uzyskać [tutaj](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/).

    Aby sprawdzić, czy masz subskrypcję usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], przejdź do strony rozliczeń w portalu usługi Office.  Usługa [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] powinna być widoczna jako **Aktywna** w obszarze subskrypcji.

2.  Zaloguj się do   [portalu usługi Office](http://portal.office.com) przy użyciu poświadczeń administratora.

3.  Przejdź do strony **Aktywni użytkownicy**, aby dodać użytkowników i przypisać licencje usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    ![Strona dodawania użytkowników do portalu usługi Office](../media/AppManagement/OfficePortal_AddUsers.png)

4.  Aby dać użytkownikowi możliwość dostępu do portalu usługi Office, portalu usługi Azure AD i portalu Azure, przypisz użytkownikowi **rolę administratora globalnego**.

    ![Zrzut ekranu przedstawiający stronę aktywnych użytkowników portalu Office ](../media/AppManagement/OfficePortal_AddRoletoUser.png)

5.  Zasady zarządzania aplikacjami mobilnymi są wdrażane dla grup użytkowników w usłudze Azure Active Directory. Aby utworzyć grupy użytkowników, które będą stosowane dla zasad zarządzania aplikacjami mobilnymi, przejdź do strony **Grupy** w **portalu usługi Office** i kliknij ikonę **+**, aby utworzyć nową grupę zabezpieczeń.  Wpisz nazwę i opis, a następnie kliknij pozycję **Utwórz**. Po utworzeniu grupy możesz dodać do niej użytkownika, klikając pozycję **Edytuj członków** dla nowo utworzonej grupy zabezpieczeń. W usłudze Azure Active Directory zostanie utworzona grupa zabezpieczeń.

    ![Zrzut ekranu przedstawiający wybór roli Administrator globalny na stronie edycji ról użytkownika](../media/AppManagement/OfficePortal_CreateGroups.png)

W poniższej tabeli zamieszczono role i uprawnienia, które można przypisać administratorom.

|||
|--|----|
|**Rola**|**Uprawnienia**|
|Administrator globalny (portal usługi O365)|Dostęp do portalu usługi O365 i portalu usługi Azure AD<br /><br />Dostęp do portalu Azure (możliwość zarządzania rolami i aplikacjami mobilnymi).|
|Rola właściciela (portal Azure)|Dostęp do portalu Azure (możliwość zarządzania rolami i aplikacjami mobilnymi).|
|Rola współautora (portal Azure)|Dostęp do portalu Azure (tylko możliwość zarządzania aplikacjami mobilnymi).|

## Przypisywanie użytkownikowi roli współautora

**Administratorzy globalni** mają dostęp do portalu Azure.  Jeśli chcesz, aby inni administratorzy mogli konfigurować zasady oraz wykonywać inne zadania związane z zarządzaniem aplikacjami mobilnymi, możesz przypisać użytkownikom **rolę współautora** zgodnie z poniższym opisem:


1.  W bloku **Ustawienia** w sekcji **Zarządzanie zasobami** kliknij pozycję **Użytkownicy**.

    ![Zrzut ekranu przedstawiający blok Użytkownicy w portalu Azure](../media/AppManagement/AzurePortal_MAM_AddUsers.png)

2.  Kliknij pozycję **Dodaj** , aby otworzyć blok **Dodawanie dostępu** .

3.  Kliknij pozycję **Wybierz rolę**, a następnie pozycję **Rola współautora**.

    ![Zrzut ekranu przedstawiający blok Wybieranie roli w portalu Azure](../media/AppManagement/AzurePortal_MAM_AddRole.png)

4.  Po wybraniu roli kliknij pozycję **Dodaj użytkownika**i wyszukaj użytkownika według jego nazwy lub adresu e-mail. Użytkownicy widoczni na tej liście to pierwszych 1000 użytkowników utworzonych wcześniej w usłudze Azure AD za pomocą portalu usługi Office. Kliknij pozycję **OK** w bloku **Dodawanie dostępu** , aby zapisać i przypisać rolę użytkownikowi.

    ![Zrzut ekranu przedstawiający blok Dodawanie użytkowników w portalu Azure](../media/AppManagement/AzurePortal_MAM_AddusertoRole.png)

    > [!IMPORTANT]
    > Jeśli zostanie wybrany użytkownik bez przypisanej licencji usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] , nie będzie on w stanie uzyskiwać dostępu do portalu.

## Następne kroki
[Tworzenie i wdrażanie zasad zarządzania aplikacjami mobilnymi przy użyciu usługi Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


