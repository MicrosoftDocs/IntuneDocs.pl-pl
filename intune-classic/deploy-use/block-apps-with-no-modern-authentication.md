---
title: "Blokowanie aplikacji, które nie obsługują nowoczesnego uwierzytelniania"
description: 
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 098b652c-01e0-45d1-a731-620b0d3dc7c1
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 848178ecdd5580ca6dcb0b8f853e80abd2959d24
ms.sourcegitcommit: 82088d297eef629e3da6011681ead442ae7e25f7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Blokowanie aplikacji, które nie korzystają z nowoczesnego uwierzytelniania (ADAL)

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Dostęp warunkowy na podstawie aplikacji z zasadami ochrony aplikacji bazuje na aplikacjach korzystających z [nowoczesnego uwierzytelniania](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), które jest implementacją protokołu OAuth2. Większość obecnych mobilnych i klasycznych aplikacji pakietu Office korzysta z nowoczesnego uwierzytelniania. Istnieją jednak aplikacje innych firm oraz starsze aplikacje pakietu Office, które korzystają z innych metod uwierzytelniania, takich jak uwierzytelnianie podstawowe i uwierzytelnianie za pomocą formularzy.

Aby zablokować dostęp do tych aplikacji zalecamy wykonanie poniższych czynności:

* Skonfiguruj reguły oświadczeń ADFS, aby zablokować nienowoczesne protokoły uwierzytelniania. Szczegółowe instrukcje zostały przedstawione w scenariuszu 3 — [całkowite blokowanie dostępu do usługi O365 z wyjątkiem aplikacji opartych na przeglądarce](https://technet.microsoft.com/library/dn592182.aspx).
* W przypadku usługi **SharePoint Online** należy wyłączyć nienowoczesne uwierzytelnianie w usłudze SharePoint Online, korzystając z polecenia cmdlet [Set-SPOTenant](https://technet.microsoft.com/library/fp161390.aspx) programu PowerShell, aby ustawić dla starszych protokołów uwierzytelniania właściwość „fałsz”:

```
 Set-SPOTenant -LegacyAuthProtocolsEnabled $false

```


>[!IMPORTANT]
>Dostęp warunkowy na podstawie aplikacji nie może być używany z uwierzytelnianiem na podstawie certyfikatu usługi Azure Active Directory (Azure AD). Użytkownik może mieć skonfigurowaną tylko jedną z tych opcji.

### <a name="see-also"></a>Zobacz także
[Zezwalanie na dostęp do usług Office 365 tylko aplikacjom obsługiwanym przez usługę Intune](allow-policy-managed-apps-access-to-o365.md)
