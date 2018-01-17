---
title: "Obsługiwane urządzenia — Microsoft Intune"
description: "Podaje listę obsługiwanych platform urządzeń i przeglądarki do zarządzania urządzeniami w usłudze Intune"
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 01/03/2018
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 56516562b9a7510020475d226c74bf719bdd33a3
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/04/2018
---
# <a name="supported-devices-and-browsers"></a>Obsługiwane urządzenia i przeglądarki

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Ten artykuł jest przeznaczony dla administratorów systemów odpowiedzialnych za zarządzanie urządzeniami w przedsiębiorstwie. Aby uzyskać pomoc dotyczącą instalowania usługi Intune na telefonie, zobacz artykuł [Korzystanie z zarządzanych urządzeń do wykonania pracy](/intune-user-help/company-portal-frequently-asked-questions).

Przed rozpoczęciem konfigurowania usługi Microsoft Intune przejrzyj poniższe wymagania:

- [Obsługiwane urządzenia i komputery](#intune-supported-devices)
- [listę obsługiwanych przeglądarek sieci Web umożliwiających korzystanie z usługi Intune.](#intune-supported-web-browsers)

Zapoznaj się też z informacjami o [użyciu przepustowości sieci przez usługę Intune](network-bandwidth-use.md) ([portal klasyczny](/intune-classic/get-started/network-bandwidth-use)).

## <a name="intune-supported-devices"></a>Urządzenia obsługiwane przez usługę Intune

Korzystając z funkcji zarządzania urządzeniami przenośnymi usługi Intune, możesz zarządzać następującymi urządzeniami:

[!INCLUDE[mdm-supported-devices](./includes/mdm-supported-devices.md)]

### <a name="supported-samsung-knox-standard-devices"></a>Obsługiwane urządzenia z systemem Samsung Knox Standard

Aplikacja Portal firmy podejmuje próbę aktywacji systemu Samsung Knox podczas rejestracji w usłudze MDM tylko w przypadku, gdy urządzenie znajduje się na [liście obsługiwanych urządzeń z systemem Knox](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Pozwala to uniknąć błędów aktywacji systemu Knox, które uniemożliwiają rejestrację w usłudze MDM. Urządzenia, które nie obsługują aktywacji systemu Samsung Knox, są rejestrowane jako standardowe urządzenia z systemem Android. Urządzenia firmy Samsung z określonymi numerami modelu mogą obsługiwać system Knox, podczas gdy inne go nie obsługują. Przed zakupem i wdrożeniem urządzeń firmy Samsung należy sprawdzić zgodność systemu Knox u odsprzedawcy urządzenia.

> [!NOTE]
> Rejestrowanie urządzeń z systemem Samsung Knox może wiązać się z koniecznością [włączenia dostępu do serwerów firmy Samsung](https://support.samsungknox.com/hc/articles/115013833108-Our-corporate-devices-are-behind-a-firewall-How-do-I-enable-Knox-Workspace-devices-to-contact-Samsung-servers). 

Poniższa lista obejmuje modele urządzeń firmy Samsung, które nie obsługują systemu Knox i są rejestrowane jako urządzenia z natywnym systemem Android przez aplikację Portal firmy dla systemu Android:

| **Nazwa urządzenia** | **Numery modelu urządzenia** |
| --- | --- |
| Galaxy Avant | SM-G386T |
| Galaxy Core 2/Core 2 Duos | SM-G355H<br>SM-G355M |
| Galaxy Core Lite | SM-G3588V |
| Galaxy Core Prime | SM-G360H |
| Galaxy Core LTE | SM-G386F<br>SM-G386W |
| Galaxy Grand | GT-I9082L<br>GT-I9082<br>GT-I9080L |
| Galaxy Grand 3 | SM-G7200 |
| Galaxy Grand Neo | GT-I9060I |
| Galaxy Grand Prime Value Edition | SM-G531H |
| Galaxy J Max | SM-T285YD |
| Galaxy J1 | SM-J100H<br>SM-J100M<br>SM-J100ML |
| Galaxy J1 Ace | SM-J110F<br>SM-J110H |
| Galaxy J1 Mini | SM-J105M |
| Galaxy J2/J2 Pro | SM-J200H<br>SM-J210F |
| Galaxy J3 | SM-J320F<br>SM-J320FN<br>SM-J320H<br>SM-J320M |
| Galaxy K Zoom | SM-C115 |
| Galaxy Light | SGH-T399N |
| Galaxy Note 3 | SM-N9002<br>SM-N9009 |
| Galaxy Note 7/Note 7 Duos | SM-N930S<br>SM-N9300<br>SM-N930F<br>SM-N930T<br>SM-N9300<br>SM-N930F<br>SM-N930S<br>SM-N930T |
| Galaxy Note 10.1 3G | SM-P602 |
| Galaxy S2 Plus | GT-I9105P |
| Galaxy S3 Mini | SM-G730A<br>SM-G730V |
| Galaxy S3 Neo | GT-I9300<br>GT-I9300I |
| Galaxy S4 | SM-S975L |
| Galaxy S4 Neo | SM-G318ML |
| Galaxy S5 | SM-G9006W |
| Galaxy S6 Edge | 404SC |
| Galaxy Tab A 7.0&quot; | SM-T280<br>SM-T285 |
| Galaxy Tab 3 7&quot;/Tab 3 Lite 7&quot; | SM-T116<br>SM-T210<br>SM-T211 |
| Galaxy Tab 3 8.0&quot; | SM-T311 |
| Galaxy Tab 3 10.1&quot; | GT-P5200<br>GT-P5210<br>GT-P5220 |
| Galaxy Trend 2 Lite | SM-G318H |
| Galaxy V Plus | SM-G318HZ |
| Galaxy Young 2 Duos | SM-G130BU |

Usługi Intune nie można używać do zarządzania systemami operacyjnymi Windows Server.

### <a name="windows-pc-software-client"></a>Oprogramowanie klienckie dla komputerów z systemem Windows

[Oprogramowanie klienckie usługi Intune](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) można wdrożyć i zainstalować na komputerach z systemem Windows jako alternatywną metodę rejestracji. Ta funkcja jest dostępna tylko za pomocą portalu klasycznego usługi Intune. Klient oprogramowania usługi Intune umożliwia zarządzanie komputerami z systemem Windows 7 lub nowszym, z wyjątkiem systemu Windows 10 Home Edition.

<!--  ### Exchange ActiveSync management

You can manage [Exchange ActiveSync devices](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) from the Intune console. This option provides a limited set of management capabilities when compared to the other methods. See [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) for a list of supported devices.  -->

## <a name="intune-supported-web-browsers"></a>Przeglądarki sieci Web obsługiwane przez usługę Intune

Różne zadania administracyjne wymagają użycia jednej z następujących witryn administracyjnych sieci Web.

- [Portal usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Portal Azure](https://portal.azure.com/)

Dla tych portali obsługiwane są następujące przeglądarki:
- Microsoft Edge (najnowsza wersja)
- Microsoft Internet Explorer 11
- Safari (najnowsza wersja, tylko Mac)
- Chrome (najnowsza wersja)
- Firefox (najnowsza wersja)

### <a name="intune-classic-portal"></a>Klasyczny portal usługi Intune

Tylko klasyczne funkcje usługi Intune, takie jak oprogramowanie klienckie usługi Intune na komputery PC i integracja z partnerami usługi Mobile Threat Defense, są dostępne tylko w klasycznym portalu usługi Intune (https://manage.microsoft.com). Klasyczny portal usługi Intune wymaga obsługi przeglądarki programu Silverlight.

Następujące przeglądarki programu Silverlight obsługują konsolę usługi Intune:
- Internet Explorer 10 lub nowsza wersja
- Google Chrome (wersje poprzedzające wersję 42)
- Mozilla Firefox z włączonym dodatkiem Silverlight [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=836872)

> [!Note]
> Przeglądarka Microsoft Edge i przeglądarki dla urządzeń przenośnych nie są obsługiwane przez portal klasyczny usługi Intune, ponieważ nie obsługują technologii [Microsoft Silverlight](https://msdn.microsoft.com/library/cc838158(v=vs.95).aspx).

Do tego portalu mogą logować się tylko użytkownicy z uprawnieniami administratora usługi lub administratorzy dzierżawy z rolą administratora globalnego. Aby można było uzyskać dostęp do konsoli administracyjnej, konto musi mieć licencję na korzystanie z usługi Intune i stan logowania **Dozwolone**.
