---
title: Wymagania wstępne dotyczące zasad zarządzania aplikacjami mobilnymi
description: W tym temacie opisano wymagania wstępne dotyczące konfigurowania użytkowników przed utworzeniem zasad zarządzania aplikacjami mobilnymi.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 11/29/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 52cba4de7d19744e1a011071ac6c9bbb168ffb30
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="get-ready-to-configure-app-protection-policies-in-the-azure-portal"></a>Przygotowywanie do konfigurowania zasad ochrony aplikacji w witrynie Azure Portal

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

W tym temacie opisano wymagania wstępne oraz czynności, które należy wykonać **przed** rozpoczęciem tworzenia zasad ochrony aplikacji w witrynie Azure Portal.

Aby dowiedzieć się, w jaki sposób zasady ochrony aplikacji usługi Intune mogą chronić dane firmy, zobacz [Protect apps and data using app protection policies](protect-apps-and-data-with-microsoft-intune.md) (Chronienie aplikacji i danych przy użyciu zasad ochrony aplikacji).

## <a name="what-is-the-azure-portal"></a>Co to jest portal Azure?

Witryna Azure Portal to nowa konsola administracyjna do tworzenia zasad ochrony aplikacji. Obsługuje ona następujące scenariusze zarządzania aplikacjami mobilnymi:
- Urządzenia, które zostały zarejestrowane w usłudze Intune
- Urządzenia zarządzane przy użyciu innego rozwiązania do zarządzania urządzeniami mobilnymi (MDM)
- Urządzenia niezarządzane przez żadne rozwiązanie MDM (BYOD)

Obecnie zarówno **konsola administratora usługi Intune**, jak i **witryna Azure Portal** umożliwiają konfigurowanie zasad ochrony aplikacji.  Rozważ następujące opcje:

* Zasady tworzone w witrynie **Azure Portal** są obsługiwane we **wszystkich scenariuszach zarządzania aplikacjami mobilnymi** wymienionych wcześniej. **Konsola administratora usługi Intune** obsługuje wyłącznie tworzenie zasad dla **urządzeń zarejestrowanych w usłudze Intune i zarządzanych przez nią**.

* Nie wszystkie ustawienia zasad ochrony aplikacji będą widoczne w konsoli administratora usługi Intune, ponieważ **nowe ustawienia** można dodawać tylko do witryny **Azure Portal**.

* Jeśli utworzysz zasady ochrony aplikacji **zarówno** za pomocą konsoli administracyjnej usługi Intune, jak i witryny Azure Portal, zasady utworzone w **witrynie Azure Portal zostaną zastosowane dla aplikacji i wdrożone dla użytkowników**.
    * Zasad ochrony aplikacji utworzonych w konsoli administracyjnej usługi Intune nie można zaimportować do witryny Azure Portal.  Zasady ochrony aplikacji należy ponownie utworzyć w witrynie Azure Portal.


* Inne **funkcje zarządzania aplikacjami**, takie jak wdrażanie aplikacji i zasady konfiguracji aplikacji, są obecnie dostępne tylko w **konsoli administracyjnej usługi Intune**.


Jeśli jesteś nowym użytkownikiem witryny Azure Portal, zobacz artykuł [Azure Portal — zasady ochrony aplikacji](azure-portal-for-microsoft-intune-mam-policies.md), aby zapoznać się z podstawowymi informacjami na temat witryny Azure Portal.

Aby uzyskać informacje o tworzeniu zasad aplikacji w konsoli administracyjnej usługi Intune, zobacz artykuł [Konfigurowanie i wdrażanie zasad ochrony aplikacji w konsoli usługi Microsoft Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).


##  <a name="supported-platforms"></a>Obsługiwane platformy
- System iOS 8.1 lub nowszy
- System Android 4 lub nowszy
- Windows 10

>[!NOTE]
>Począwszy od wersji 1703, zasady ochrony aplikacji można definiować dla urządzeń z systemem Windows 10 w scenariuszu zarządzania aplikacjami mobilnymi bez rejestracji. Aby uzyskać szczegółowe informacje, zobacz [Protect your enterprise data using Windows Information Protection](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip) (Chronienie danych przedsiębiorstwa przy użyciu rozwiązania Windows Information Protection).

##  <a name="supported-apps"></a>Obsługiwane aplikacje
* **Aplikacje firmy Microsoft:** te aplikacje mają wbudowany zestaw SDK aplikacji usługi Intune i nie wymagają dalszego przetwarzania przed zastosowaniem zasad ochrony aplikacji.
Pełna lista obsługiwanych aplikacji firmy Microsoft jest dostępna w [galerii aplikacji mobilnych usługi Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) na stronie partnerów aplikacji usługi Microsoft Intune. Kliknij aplikację, aby wyświetlić obsługiwane scenariusze i platformy, a także sprawdzić, czy aplikacja obsługuje wiele tożsamości.

* **Aplikacje biznesowe organizacji:** przed zastosowaniem zasad ochrony aplikacji należy przygotować te aplikacje do dołączenia do nich zestawu SDK aplikacji usługi Intune.

  * W przypadku urządzeń zarządzanych przez usługę Intune zobacz [Decide how to prepare apps for MAM](/intune/apps-prepare-mobile-application-management) (Wybieranie sposobu przygotowania aplikacji do zarządzania aplikacjami mobilnymi).

  * W przypadku urządzeń niezarządzanych (takich jak urządzenia należące do pracowników) lub urządzeń zarządzanych przy użyciu rozwiązania do zarządzania urządzeniami przenośnymi innej firmy, zobacz artykuł [Ochrona aplikacji biznesowych i danych na urządzeniach niezarejestrowanych w usłudze Microsoft Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

## <a name="prerequisites"></a>Wymagania wstępne

- **Subskrypcja usługi Microsoft Intune**. Użytkownicy potrzebują licencji usługi Intune w celu pobierania aplikacji z zasadami ochrony aplikacji.
  Jeśli aktualnie używasz usługi Intune do zarządzania urządzeniami, masz już subskrypcję usługi Intune. Masz również subskrypcję usługi Intune, jeśli masz kupioną licencję pakietu Enterprise Mobility Suite (EMS). Jeśli wypróbowujesz usługę Intune w celu zapoznania się z możliwościami w zakresie zarządzania aplikacjami mobilnymi, konto próbne możesz uzyskać na [stronie usługi Microsoft Intune](https://www.microsoft.com/server-cloud/products/microsoft-intune/).

  Aby sprawdzić, czy masz subskrypcję usługi Intune, przejdź do strony **Rozliczenia** w portalu usługi Office.  Jeśli masz subskrypcję, usługa Intune powinna być widoczna jako **Aktywna** w obszarze subskrypcji.

- **Subskrypcja usługi Office 365**, która jest wymagana do:

  - Stosowania zasad ochrony aplikacji do aplikacji z obsługą wielu tożsamości.

  - Tworzenia kont służbowych usług SharePoint Online i Exchange Online. Lokalna instalacja programu Exchange i lokalna instalacja programu SharePoint nie są obsługiwane.

- **Konfiguracja programu Skype dla firm Online do korzystania z nowoczesnego uwierzytelniania**. Aby uzyskać więcej informacji, zobacz [Włączanie nowoczesnego uwierzytelniania](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).


- Usługa Azure Active Directory (Azure AD) do tworzenia użytkowników. Usługa Azure AD uwierzytelnia użytkowników, gdy otworzą oni aplikację i wprowadzą poświadczenia robocze.

    > [!NOTE]
    > Grupy użytkowników muszą być skonfigurowane w usłudze Azure AD. Grupy użytkowników usługi Intune nie mogą służyć do wdrażania zasad ochrony aplikacji w witrynie Azure Portal.

### <a name="create-users-and-assign-microsoft-intune-licenses"></a>Tworzenie użytkowników i przypisywanie licencji usługi Microsoft Intune

1.  Zaloguj się do [portalu usługi Office](https://portal.office.com) przy użyciu poświadczeń administratora.

2.  Dodaj użytkowników, zgodnie z opisem w sekcji **Korzystanie z 30-dniowej wersji ewaluacyjnej usługi Intune** w [Przewodniku ewaluacji usługi Intune](/intune-classic/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune), a następnie przypisz licencje usługi Intune. Aby dać użytkownikowi możliwość dostępu do portalu usługi Office, portalu usługi Azure AD i portalu Azure, przypisz użytkownikowi **rolę administratora globalnego**.

5.  Zasady ochrony aplikacji są wdrażane dla grup użytkowników w usłudze Azure Active Directory. Aby utworzyć grupy użytkowników na potrzeby zasad ochrony aplikacji, utwórz grupę użytkowników w sposób opisany w sekcji **Tworzenie grupy użytkowników** w artykule [Tworzenie grup w celu organizowania użytkowników i urządzeń objętych subskrypcją ewaluacyjną](/intune-classic/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-3).

### <a name="assign-roles-to-non-global-admin-users"></a>Przypisywanie ról do użytkowników niebędących administratorami globalnymi

Administratorzy globalni mają dostęp do [portalu Azure](https://portal.azure.com).  Jeśli chcesz, aby użytkownicy inni niż administratorzy globalni mogli konfigurować zasady oraz wykonywać inne zadania związane z zarządzaniem aplikacjami mobilnymi, zapoznaj się z artykułem [Zarządzanie dostępem do zasobów subskrypcji platformy Azure za pomocą przypisań ról](https://azure.microsoft.com/documentation/articles/role-based-access-control-configure/).

## <a name="next-steps"></a>Następne kroki
[Tworzenie i wdrażanie zasad ochrony aplikacji przy użyciu usługi Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)
