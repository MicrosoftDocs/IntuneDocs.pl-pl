---
title: "Dostęp warunkowy do usługi O365 oparty na aplikacji"
description: "Poznaj sposób, w jaki dostęp warunkowy zarządzania aplikacjami mobilnymi może pomóc w kontrolowaniu tego, które aplikacje mogą mieć dostęp do usług O365."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7ad33ba7020f418f4894a689d5d66a74e4b8c10e
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2017
---
# <a name="allow-only-mobile-apps-that-support-intune-app-protection-policies-to-access-office-365-services"></a>Zezwalanie na dostęp do usług Office 365 wyłącznie aplikacjom mobilnym obsługującym zasady ochrony aplikacji usługi Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

[Zasady ochrony aplikacji usługi Intune](protect-apps-and-data-with-microsoft-intune.md) pomagają chronić dane firmy na urządzeniach zarejestrowanych na potrzeby zarządzania przez usługę Intune. Możesz również korzystać z zasad ochrony aplikacji na **urządzeniach należących do pracowników, które nie zostały zarejestrowane na potrzeby zarządzania przez usługę Intune**.  W takim przypadku, nawet jeśli nie zarządzasz danym urządzeniem, musisz upewnić się, że dane i zasoby firmy zostały odpowiednio zabezpieczone. Przy użyciu dostępu warunkowego na podstawie aplikacji do zarządzania aplikacjami mobilnymi możesz utworzyć zasady, które zezwalają na dostęp do usług O365, takich jak usługa Exchange Online, tylko tym aplikacjom mobilnym, które obsługują zasady ochrony aplikacji usługi Intune.

Na przykład zezwalając na dostęp do usługi Exchange Online wyłącznie **aplikacji Microsoft Outlook**, możesz **blokować wbudowane aplikacje poczty e-mail w systemach iOS i Android**, które nie zapewniają ochrony danych pochodzącej z zasad zarządzania aplikacjami mobilnymi usługi Intune, aby nie mogły odbierać wiadomości z usługi **Exchange Online**. Możesz także zablokować dostęp do usługi **SharePoint Online** aplikacjom mobilnym, które nie mają obsługi zarządzania aplikacjami mobilnymi w usłudze Intune.

Poniższy diagram ilustruje przepływ używany przez zasady dostępu warunkowego na podstawie aplikacji umożliwiający określenie, kiedy należy zezwolić na dostęp lub zablokować go: ![Diagram przedstawiający różne kryteria dodane w celu ustalenia, czy należy zezwolić na dostęp, czy zablokować go](../media/mam-ca-decision-flow_simple.png).

Opis skrótów używanych na diagramach:
* **CP**: aplikacja Portal firmy
* **AA**: aplikacja Azure Authenticator
* **AAD**: usługa Azure Active Directory
* **EAS**: aplikacja Exchange Active Sync

## <a name="prerequisites"></a>Wymagania wstępne
**Przed** utworzeniem zasad dostępu warunkowego na podstawie aplikacji musisz mieć **subskrypcję pakietu Enterprise Mobility + Security lub usługi Azure Active Directory w warstwie Premium**, a użytkownicy muszą mieć licencję usług EMS lub Azure AD. Aby uzyskać więcej szczegółowych informacji, zobacz [Cennik pakietu Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) lub [Cennik usługi Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).


## <a name="supported-apps"></a>Obsługiwane aplikacje
**Exchange Online**:
* **Microsoft Outlook** dla urządzeń z systemami iOS i Android.

**SharePoint Online**
* Microsoft Word dla urządzeń z systemami iOS i Android
* Microsoft Excel dla urządzeń z systemami iOS i Android
* Microsoft PowerPoint dla urządzeń z systemami iOS i Android
* Microsoft OneDrive dla Firm dla urządzeń z systemami iOS i Android
* Microsoft OneNote dla urządzeń z systemem iOS

>[!IMPORTANT]
>W przypadku urządzeń z systemem Android początkowa rejestracja urządzenia musi zostać przeprowadzona poprzez zalogowanie się do aplikacji OneDrive lub aplikacji Outlook. Aplikacja OneNote dla urządzeń z systemem Android nie obsługuje jeszcze zarządzania aplikacjami mobilnymi bez rejestracji.

Aby dowiedzieć się więcej o środowisku użytkownika korzystającego z aplikacji, która zawiera zasady dostępu warunkowego na podstawie aplikacji, zobacz [Oczekiwany przebieg korzystania z aplikacji z dostępem warunkowym do zarządzania aplikacjami mobilnymi](use-apps-with-mam-ca.md).


## <a name="next-steps"></a>Następne kroki
[Tworzenie zasad usługi Exchange Online dla aplikacji z obsługą zarządzania aplikacjami mobilnymi](mam-ca-for-exchange-online.md)

[Tworzenie zasad usługi SharePoint Online dla aplikacji z obsługą zarządzania aplikacjami mobilnymi](mam-ca-for-sharepoint-online.md)

[Blokowanie aplikacji, które nie obsługują nowoczesnego uwierzytelniania](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Zobacz także

[Ochrona danych aplikacji za pomocą zasad ochrony aplikacji](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
