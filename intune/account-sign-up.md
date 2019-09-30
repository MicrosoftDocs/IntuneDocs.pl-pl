---
title: Utworzenie konta usługi Microsoft Intune lub zalogowanie się do niego
description: Informacje na temat rejestrowania się w celu uzyskania subskrypcji usługi Microsoft Intune lub logowania się w celu rozpoczęcia pracy z istniejącą subskrypcją.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0f3ce07a-b718-42a9-bace-f99a8b8abd94
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 22e5c38be9dc5a8a09888651e471f64bf6739c72
ms.sourcegitcommit: 1494ff4b33c13a87f20e0f3315da79a3567db96e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/20/2019
ms.locfileid: "71238903"
---
# <a name="sign-up-or-sign-in-to-microsoft-intune"></a>Utworzenie konta usługi Microsoft Intune lub zalogowanie się do niego

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Ten temat zawiera informacje dla administratorów dotyczące tworzenia konta w usłudze Intune.

Przed zarejestrowaniem się w usłudze Intune określ, czy masz już konto usług Microsoft Online Services, umowę Enterprise Agreement lub równoważną umowę licencjonowania zbiorowego. Umowy licencjonowania zbiorowego firmy Microsoft lub subskrypcje innych usług firmy Microsoft w chmurze, takich jak Office 365, obejmują zazwyczaj konta firmowe.

Jeśli masz już konto firmowe, **zaloguj się** przy użyciu tego konta i dodaj usługę Intune do swojej subskrypcji. W przeciwnym razie **zarejestruj** nowe konto, aby korzystać z usługi Intune w swojej organizacji.

>[!WARNING]
>Nie można połączyć istniejącego konta służbowego lub edukacyjnego po zarejestrowaniu nowego konta.

## <a name="how-to-sign-up-for-intune"></a>Jak zarejestrować się w usłudze Intune

1. Odwiedź stronę [Tworzenie konta w usłudze Intune](https://admin.microsoft.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20).

   ![Zrzut ekranu strony internetowej tworzenia konta próbnego usługi Microsoft Intune](./media/account-sign-up-site.png)

2. Na stronie tworzenia konta utwórz konto lub zaloguj się na nie, aby zarządzać nową subskrypcją usługi Intune.

## <a name="post-sign-up-considerations"></a>Kwestie do rozważenia po utworzeniu konta
Po utworzeniu konta w celu uzyskania nowej subskrypcji wiadomość e-mail zawierająca informacje o koncie zostanie wysłana na adres e-mail podany w procesie rejestracji. Stanowi ona potwierdzenie, że Twoja subskrypcja jest aktywna.

Po ukończeniu procesu rejestracji nastąpi przekierowanie do centrum administracyjnego platformy Microsoft 365 używanego do dodawania użytkowników i przypisywania im licencji. Jeśli będziesz korzystać tylko z kont w chmurze korzystających z Twojej domyślnej nazwy domeny onmicrosoft.com, możesz rozpocząć dodawanie użytkowników i przypisywanie licencji na tym etapie. Jednak jeśli chcesz używać [niestandardowej nazwy domeny](custom-domain-name-configure.md) organizacji lub [synchronizować informacje dotyczące kont użytkowników](users-add.md#sync-active-directory-and-add-users-to-intune) z lokalnej usługi Active Directory, możesz zamknąć to okno przeglądarki.

## <a name="sign-in-to-microsoft-intune"></a>Logowanie się do konta usługi Microsoft Intune
Po zarejestrowaniu się w usłudze Intune możesz użyć dowolnego urządzenia, na którym zainstalowano [obsługiwaną przeglądarkę](supported-devices-browsers.md#intune-supported-web-browsers), aby zalogować się do konta usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) w celu administrowania usługą.

Domyślnie konto musi mieć w usłudze Azure Active Directory jedno z następujących uprawnień:
- Administrator globalny
- Administrator usługi Intune (znany także jako administrator Intune)

Aby udzielić dostępu do administrowania usługą dla użytkowników z innymi uprawnieniami, zobacz temat [Kontrola dostępu oparta na rolach (RBAC) w usłudze Microsoft Intune](role-based-access-control.md)

### <a name="intune-admin-portal-url"></a>Adres URL portalu administracyjnego usługi Intune

Centrum administracyjne platformy Microsoft 365: https://devicemanagement.microsoft.com

Witryna Intune Azure Portal: https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade

Intune for Education: https://intuneeducation.portal.azure.com

Klasyczny portal usługi Intune: https://manage.microsoft.com Klasyczny portal usługi Intune służy tylko do zarządzania urządzeniami zarejestrowanymi przy użyciu oprogramowania klienckiego usługi Intune

### <a name="urls-for-intune-services-provided-by-office-365"></a>Adresy URL dla usług Intune oferowanych w ramach usługi Office 365

Microsoft 365 Business: https://portal.microsoft.com/adminportal

Zarządzanie urządzeniami mobilnymi w usłudze Office 365: https://portal.office.com/adminportal/home#/MifoDevices

## <a name="see-also"></a>Zobacz także
[You can't sign in to Office 365, Azure, or Intune](https://support.microsoft.com/help/2412085) (Nie można zalogować się w usłudze Office 365, Azure lub Intune)
