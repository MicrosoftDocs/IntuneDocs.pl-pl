---
title: Blokowanie aplikacji, które nie obsługują nowoczesnego uwierzytelniania, przy użyciu usługi Intune
titleSuffix: Microsoft Intune
description: Dowiedz się więcej o uwierzytelnianiu aplikacji i nowoczesnym uwierzytelnianiu (ADAL) przy użyciu usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/06/2020
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.topic: conceptual
ms.technology: ''
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cd6925e85fdaa7dfddf69153f5fbcfe9cef0852f
ms.sourcegitcommit: a66b5916eaab9cb537e483064efc584a6a63a390
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/07/2020
ms.locfileid: "75692271"
---
# <a name="block-apps-that-dont-use-modern-authentication-adal"></a>Blokowanie aplikacji, które nie korzystają z nowoczesnego uwierzytelniania (ADAL)

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Dostęp warunkowy na podstawie aplikacji z zasadami ochrony aplikacji bazuje na aplikacjach korzystających z [nowoczesnego uwierzytelniania](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), które jest implementacją protokołu OAuth2. Większość obecnych mobilnych i klasycznych aplikacji pakietu Office korzysta z nowoczesnego uwierzytelniania. Istnieją jednak aplikacje innych firm oraz starsze aplikacje pakietu Office, które korzystają z innych metod uwierzytelniania, takich jak uwierzytelnianie podstawowe i uwierzytelnianie za pomocą formularzy.

## <a name="block-access-to-apps"></a>Blokowanie dostępu do aplikacji

Aby zablokować dostęp do aplikacji, które nie korzystają z nowoczesnego uwierzytelniania, użyj zasad ochrony aplikacji usługi Intune w celu zaimplementowania dostępu opartego na warunkach. Aby uzyskać więcej informacji, zobacz temat [Dostęp warunkowy oparty na aplikacji z użyciem usługi Intune](app-based-conditional-access-intune.md).

## <a name="additional-information"></a>Dodatkowe informacje

Aby uzyskać więcej informacji na temat dostępu warunkowego w usłudze Azure AD, zobacz następujące tematy:
- [Co to jest dostęp warunkowy w usłudze Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)
- [Sposób działania dostępu warunkowego opartego na aplikacji](app-based-conditional-access-intune.md#how-app-based-conditional-access-works)
- [Konfigurowanie usług SharePoint Online i Exchange Online na potrzeby dostępu warunkowego w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/conditional-access-for-exo-and-spo)

## <a name="next-steps"></a>Następne kroki

- [Dostęp warunkowy oparty na aplikacji z użyciem usługi Intune](app-based-conditional-access-intune.md)
