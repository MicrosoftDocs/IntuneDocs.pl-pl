---
title: "Obsługiwane urządzenia — Microsoft Intune"
description: "Podaje listę obsługiwanych platform urządzeń i przeglądarki do zarządzania urządzeniami w usłudze Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f862129d73c83e078d8b29201f1d92b9b65aa609
ms.sourcegitcommit: ce8a1f0f4e95444949556600d1837937b6efd769
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/28/2017
---
# <a name="supported-devices-and-browsers"></a>Obsługiwane urządzenia i przeglądarki

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Ten artykuł jest przeznaczony dla administratorów systemów odpowiedzialnych za zarządzanie urządzeniami w przedsiębiorstwie. Aby uzyskać pomoc dotyczącą instalowania usługi Intune na telefonie, zobacz artykuł [Korzystanie z zarządzanych urządzeń do wykonania pracy](/intune-user-help/company-portal-frequently-asked-questions).

Przed rozpoczęciem konfigurowania usługi Microsoft Intune przejrzyj poniższe wymagania:

- [Obsługiwane urządzenia i komputery](#intune-supported-devices)
- [listę obsługiwanych przeglądarek sieci Web umożliwiających korzystanie z usługi Intune.](#intune-supported-web-browsers)

Zapoznaj się też z informacjami o [użyciu przepustowości sieci przez usługę Intune](network-bandwidth-use.md) ([konsola klasyczna](/intune-classic/get-started/network-bandwidth-use)).

## <a name="intune-supported-devices"></a>Urządzenia obsługiwane przez usługę Intune

Korzystając z funkcji zarządzania urządzeniami przenośnymi usługi Intune, możesz zarządzać następującymi urządzeniami:

[!INCLUDE[mdm-supported-devices](./includes/mdm-supported-devices.md)]

Usługi Intune nie można używać do zarządzania systemami operacyjnymi Windows Server.

### <a name="windows-pc-software-client"></a>Oprogramowanie klienckie dla komputerów z systemem Windows

[Oprogramowanie klienckie usługi Intune](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) można wdrożyć i zainstalować na komputerach z systemem Windows jako alternatywną metodę rejestracji. Ta funkcja jest dostępna tylko za pomocą klasycznej konsoli usługi Intune. Klient oprogramowania usługi Intune umożliwia zarządzanie komputerami z systemem Windows 7 lub nowszym, z wyjątkiem systemu Windows 10 Home Edition.

<!--  ### Exchange ActiveSync management

You can manage [Exchange ActiveSync devices](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) from the Intune console. This option provides a limited set of management capabilities when compared to the other methods. See [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) for a list of supported devices.  -->

## <a name="intune-supported-web-browsers"></a>Przeglądarki sieci Web obsługiwane przez usługę Intune

Różne zadania administracyjne wymagają użycia jednej z następujących witryn administracyjnych sieci Web.

- [Portal usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Portal usługi Intune](https://portal.azure.com/)

Dla tych portali obsługiwane są następujące przeglądarki:
- Microsoft Edge (najnowsza wersja)
- Microsoft Internet Explorer 11
- Safari (najnowsza wersja, tylko Mac)
- Chrome (najnowsza wersja)
- Firefox (najnowsza wersja)

### <a name="intune-classic-portal"></a>Klasyczny portal usługi Intune

Tylko klasyczne funkcje usługi Intune, takie jak oprogramowanie klienckie usługi Intune na komputery PC i integracja z partnerami usługi Mobile Threat Defense, są dostępne tylko w klasycznym portalu usługi Intune (https://manage.microsoft.com). Klasyczny portal usługi Intune wymaga obsługi przeglądarki programu Silverlight.

Następujące przeglądarki programu Silverlight obsługują klasyczną konsolę usługi Intune:
- Internet Explorer 10 lub nowsza wersja
- Google Chrome (wersje poprzedzające wersję 42)
- Mozilla Firefox z włączonym dodatkiem Silverlight [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=836872)

> [!Note]
> Przeglądarka Microsoft Edge i przeglądarki dla urządzeń mobilnych nie są obsługiwane przez klasyczną konsolę usługi Intune, ponieważ nie obsługują technologii [Microsoft Silverlight](https://msdn.microsoft.com/library/cc838158(v=vs.95).aspx).

Do tego portalu mogą logować się tylko użytkownicy z uprawnieniami administratora usługi lub administratorzy dzierżawy z rolą administratora globalnego. Aby można było uzyskać dostęp do konsoli administracyjnej, konto musi mieć licencję na korzystanie z usługi Intune i stan logowania **Dozwolone**.
