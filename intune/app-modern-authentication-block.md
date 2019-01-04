---
title: Blokowanie aplikacji, które nie obsługują nowoczesnego uwierzytelniania, przy użyciu usługi Intune
titleSuffix: Microsoft Intune
description: Dowiedz się więcej o blokowaniu aplikacji, które nie korzystają z nowoczesnego uwierzytelniania (ADAL), przy użyciu usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: dc9318d46892eab21e81c7eb2992f3476720abd1
ms.sourcegitcommit: 4e69a8664c289263490daa4c02bc6b81c33196e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2018
ms.locfileid: "53642459"
---
# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Blokowanie aplikacji, które nie korzystają z nowoczesnego uwierzytelniania (ADAL)

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Dostęp warunkowy na podstawie aplikacji z zasadami ochrony aplikacji bazuje na aplikacjach korzystających z [nowoczesnego uwierzytelniania](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), które jest implementacją protokołu OAuth2. Większość obecnych mobilnych i klasycznych aplikacji pakietu Office korzysta z nowoczesnego uwierzytelniania. Istnieją jednak aplikacje innych firm oraz starsze aplikacje pakietu Office, które korzystają z innych metod uwierzytelniania, takich jak uwierzytelnianie podstawowe i uwierzytelnianie za pomocą formularzy.

## <a name="block-apps"></a>Blokowanie aplikacji

Aby zablokować dostęp do aplikacji, które nie korzystają z nowoczesnego uwierzytelniania, zaleca się następujące metody:

- Skonfiguruj reguły oświadczeń ADFS, aby zablokować nienowoczesne protokoły uwierzytelniania. Szczegółowe instrukcje zostały przedstawione w scenariuszu 3 — [całkowite blokowanie dostępu do usługi O365 z wyjątkiem aplikacji opartych na przeglądarce](https://technet.microsoft.com/library/dn592182.aspx).
- W przypadku **programu Exchange i usługi SharePoint Online** użyj dostępu warunkowego w usłudze Azure Active Directory. Dla usługi SharePoint Online użyj polecenia cmdlet Set-SPOTenant programu PowerShell. Aby uzyskać szczegółowe instrukcje, zobacz [Konfigurowanie usług SharePoint Online i Exchange Online na potrzeby dostępu warunkowego w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-no-modern-authentication#legacy-authentication-protocols).


>[!IMPORTANT]
>Dostęp warunkowy na podstawie aplikacji nie może być używany z uwierzytelnianiem na podstawie certyfikatu usługi Azure Active Directory (Azure AD). Użytkownik może mieć skonfigurowaną tylko jedną z tych opcji.

## <a name="next-steps"></a>Następne kroki

- [Dostęp warunkowy oparty na aplikacji z użyciem usługi Intune](app-based-conditional-access-intune.md)
