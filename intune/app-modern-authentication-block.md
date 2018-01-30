---
title: "Blokowanie aplikacji, które nie obsługują nowoczesnego uwierzytelniania, przy użyciu usługi Intune"
description: 
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1ab83b5fc6c7e87210ad7df387151ebf4b80b445
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Blokowanie aplikacji, które nie korzystają z nowoczesnego uwierzytelniania (ADAL)

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Dostęp warunkowy na podstawie aplikacji z zasadami ochrony aplikacji bazuje na aplikacjach korzystających z [nowoczesnego uwierzytelniania](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), które jest implementacją protokołu OAuth2. Większość obecnych mobilnych i klasycznych aplikacji pakietu Office korzysta z nowoczesnego uwierzytelniania. Istnieją jednak aplikacje innych firm oraz starsze aplikacje pakietu Office, które korzystają z innych metod uwierzytelniania, takich jak uwierzytelnianie podstawowe i uwierzytelnianie za pomocą formularzy.

Aby zablokować dostęp do tych aplikacji zalecamy wykonanie poniższych czynności:

* Skonfiguruj reguły oświadczeń ADFS, aby zablokować nienowoczesne protokoły uwierzytelniania. Szczegółowe instrukcje zostały przedstawione w scenariuszu 3 — [całkowite blokowanie dostępu do usługi O365 z wyjątkiem aplikacji opartych na przeglądarce](https://technet.microsoft.com/library/dn592182.aspx).
* W przypadku usługi **SharePoint Online** należy wyłączyć nienowoczesne uwierzytelnianie w usłudze SharePoint Online, korzystając z polecenia cmdlet [Set-SPOTenant](https://technet.microsoft.com/library/fp161390.aspx) programu PowerShell, aby ustawić dla starszych protokołów uwierzytelniania właściwość „fałsz”:

```
 Set-SPOTenant -LegacyAuthProtocolsEnabled $false

```


>[!IMPORTANT]
>Dostęp warunkowy na podstawie aplikacji nie może być używany z uwierzytelnianiem na podstawie certyfikatu usługi Azure Active Directory (Azure AD). Użytkownik może mieć skonfigurowaną tylko jedną z tych opcji.

### <a name="see-also"></a>Zobacz też
[Dostęp warunkowy oparty na aplikacji z użyciem usługi Intune](app-based-conditional-access-intune.md)
