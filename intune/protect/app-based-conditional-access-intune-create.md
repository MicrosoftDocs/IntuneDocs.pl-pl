---
title: Konfigurowanie zasad dostępu warunkowego opartego na aplikacji w usłudze Intune
titleSuffix: Microsoft Intune
description: Dowiedz się, jak utworzyć zasady dostępu warunkowego na podstawie aplikacji przy użyciu usługi Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/06/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 465f8b0001e5e2a049a3ffe12469bdb5057854ec
ms.sourcegitcommit: 28622c5455adfbce25a404de4d0437fa2b5370be
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/07/2019
ms.locfileid: "73712837"
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Konfigurowanie zasad dostępu warunkowego na podstawie aplikacji za pomocą usługi Intune

Skonfiguruj zasady dostępu warunkowego na podstawie aplikacji dla aplikacji znajdujących się na liście zatwierdzonych aplikacji. Lista zatwierdzonych aplikacji składa się z aplikacji, które zostały przetestowane przez firmę Microsoft.

Zanim zaczniesz korzystać z zasad dostępu warunkowego opartego na aplikacji, musisz zastosować do swoich aplikacji [zasady ochrony aplikacji usługi Intune](../apps/app-protection-policies.md).

> [!IMPORTANT]
> W tym artykule przedstawiono kroki dodawania zasad dostępu warunkowego opartego na aplikacji. Tych samych kroków można używać podczas dodawania aplikacji takich jak SharePoint Online, Microsoft Teams i Microsoft Exchange Online z listy zatwierdzonych aplikacji.

## <a name="create-app-based-conditional-access-policies"></a>Tworzenie zasad dostępu warunkowego opartego na aplikacji

Dostęp warunkowy to pojęcie z technologii używanej w usłudze Azure Active Directory (Azure AD). Węzeł Dostęp warunkowy dostępny z usługi *Intune* jest tym samym węzłem, do którego dostęp jest uzyskiwany z usługi *Azure AD*. Ponieważ jest to ten sam węzeł, nie trzeba przełączać się między usługami Intune i Azure AD, aby skonfigurować zasady.

Aby można było utworzyć zasady dostępu warunkowego z centrum administracyjnego programu Microsoft Endpoint Manager, musisz mieć licencję usługi Azure AD — wersja Premium.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Tworzenie zasad dostępu warunkowego opartego na aplikacji

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)

2. Wybierz pozycję **Zabezpieczenia punktu końcowego** > **Dostęp warunkowy** > **Nowe zasady**.

3. Wprowadź **nazwę** zasad, a następnie w obszarze *Przypisania* wybierz pozycję **Użytkownicy i grupy**. Użyj opcji Dołącz lub Wyklucz, aby dodać grupy do zasad, i wybierz opcję **Gotowe**.

4. Wybierz pozycję **Aplikacje w chmurze lub akcje**, a następnie aplikacje do objęcia ochroną. Na przykład wybierz pozycję **Wybierz aplikacje**, a następnie pozycje **Office 365 SharePoint Online** i **Office 365 Exchange Online**.

   Wybierz przycisk **Gotowe**, aby zapisać zmiany.

5. Wybierz pozycję **Warunki** > **Aplikacje klienckie**, aby zastosować zasady do aplikacji i przeglądarek. Na przykład wybierz przycisk **Tak**, a następnie włącz opcje **Przeglądarka** oraz **Aplikacje mobilne i klienci stacjonarni**.

   Wybierz przycisk **Gotowe**, aby zapisać zmiany.

6. W obszarze *Kontrole dostępu* wybierz pozycję **Udziel**, aby zastosować dostęp warunkowy w zależności od zgodności urządzeń. Na przykład wybierz pozycje **Udziel dostępu** > **Wymagaj, aby urządzenie było oznaczone jako zgodne**.

   Wybierz przycisk **Wybierz**, aby zapisać zmiany.

7. W obszarze **Włącz zasady** wybierz pozycję **Wł.** , a następnie wybierz pozycję **Utwórz** w celu zapisania zmian.





## <a name="next-steps"></a>Następne kroki
[Blokowanie aplikacji, które nie obsługują nowoczesnego uwierzytelniania](app-modern-authentication-block.md)

## <a name="see-also"></a>Zobacz także

[Ochrona danych aplikacji przy użyciu zasad ochrony aplikacji](../apps/app-protection-policies.md)
[Dostęp warunkowy w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
