---
title: Systemy operacyjne i przeglądarki obsługiwane przez usługę Microsoft Intune
titleSuffix: ''
description: Podaje listę obsługiwanych platform urządzeń i przeglądarki do zarządzania urządzeniami w usłudze Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 536f689a009f3e7e0128c350bafd3bf1340aeaaa
ms.sourcegitcommit: 6608dc70d01376e0cd90aa620a2fe01337f6a2f1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/04/2020
ms.locfileid: "78260218"
---
# <a name="supported-operating-systems-and-browsers-in-intune"></a>Systemy operacyjne i przeglądarki obsługiwane w usłudze Intune

Przed skonfigurowaniem usługi Microsoft Intune sprawdź obsługiwane systemy operacyjne i przeglądarki.

Aby uzyskać pomoc dotyczącą instalowania usługi Intune na urządzeniu, zobacz [Wykonywanie pracy przy użyciu urządzeń zarządzanych](https://docs.microsoft.com/intune-user-help/company-portal-frequently-asked-questions) i [Przepustowość i wymagania dotyczące konfiguracji sieci usługi Intune](network-bandwidth-use.md).

Aby uzyskać więcej informacji na temat obsługi dostawcy usługi konfiguracji, odwiedź stronę [Configuration service provider reference](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) (Informacje dotyczące dostawcy usługi konfiguracji).

> [!NOTE]
> Usługa Intune aktualnie wymaga systemu Android 5.x (Lollipop) lub nowszego, aby aplikacje i urządzenia mogły uzyskiwać dostęp do zasobów firmy za pomocą aplikacji Portal firmy dla systemu Android oraz zestawu Intune App SDK dla systemu Android. To wymaganie NIE dotyczy urządzeń usługi Teams bazujących na systemie Polycom Android 4.4. Te urządzenia będą nadal obsługiwane. 

## <a name="intune-supported-operating-systems"></a>Systemy operacyjne obsługiwane przez usługę Intune

Zarządzać możesz urządzeniami z następującymi systemami operacyjnymi:

[!INCLUDE [mdm-supported-devices](../includes/mdm-supported-devices.md)]

### <a name="supported-samsung-knox-standard-devices"></a>Obsługiwane urządzenia z systemem Samsung Knox Standard

W celu uniknięcia błędów aktywacji, które uniemożliwiają rejestrację w usłudze zarządzania urządzeniami przenośnymi, aplikacja Portal firmy podejmuje próbę aktywacji systemu Samsung Knox podczas rejestracji w usłudze MDM tylko w przypadku, gdy urządzenie znajduje się na [liście obsługiwanych urządzeń z systemem Knox](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Urządzenia, które nie obsługują aktywacji systemu Samsung Knox, są rejestrowane jako standardowe urządzenia z systemem Android. Urządzenia firmy Samsung z określonymi numerami modelu mogą obsługiwać system Knox, podczas gdy inne go nie obsługują. Przed zakupem i wdrożeniem urządzeń firmy Samsung należy sprawdzić zgodność systemu Knox u odsprzedawcy urządzenia.

> [!NOTE]
> Rejestrowanie urządzeń z systemem Samsung Knox może wiązać się z koniecznością [włączenia dostępu do serwerów firmy Samsung](https://support.samsungknox.com/hc/articles/115013833108-Our-corporate-devices-are-behind-a-firewall-How-do-I-enable-Knox-Workspace-devices-to-contact-Samsung-servers).

Modele urządzeń firmy Samsung z poniższej listy nie obsługują systemu Knox. Zostaną one zarejestrowane jako natywne urządzenia z systemem Android przez aplikację Portal firmy dla systemu Android:

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

### <a name="windows-pc-software-client"></a>Oprogramowanie klienckie dla komputerów z systemem Windows

[Oprogramowanie klienckie usługi Intune](manage-windows-pcs-with-microsoft-intune.md) można wdrożyć i zainstalować na komputerach z systemem Windows jako alternatywną metodę rejestracji. Ta funkcja jest dostępna tylko za pomocą portalu klasycznego usługi Intune. Klient oprogramowania usługi Intune umożliwia zarządzanie komputerami z systemem w wersji 10 lub nowszym, z wyjątkiem systemu Windows 10 Home Edition.

> [!Note]
> Firma Microsoft ogłosiła, że świadczenie pomocy technicznej dla systemu Windows 7 zakończy się 14 stycznia 2020 r. W tym dniu zostanie też wycofana obsługa urządzeń z systemem Windows 7 w usłudze Intune.
>
> Aby uzyskać więcej informacji, zobacz [Planowanie zmian w usłudze Intune: koniec wsparcia dla systemu Windows 7](https://docs.microsoft.com/intune/fundamentals/whats-new#windows-7-ends-extended-support-).
>
> Obsługa konsoli usługi Intune opartej na technologii Silverlight zostanie wycofana w usłudze Microsoft Intune w dniu 15 października 2020 r. To wycofanie obejmuje zakończenie pomocy technicznej dla klienta oprogramowania konfigurowanego przez konsolę Silverlight (znanego również jako agent komputera).
>
> Aby uzyskać więcej informacji, zobacz [Microsoft Intune ending support for the Silverlight-based admin console](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Take-Action-Microsoft-Intune-ending-support-for-the-Silverlight/ba-p/916249) (W usłudze Microsoft Intune kończy się obsługa konsoli administracyjnej opartej na technologii Silverlight).

<!--  ### Exchange ActiveSync management

You can manage [Exchange ActiveSync devices](../enrollment/device-enrollment.md#mobile-device-management-with-exchange-activesync-and-intune) from the Intune console. This option provides a limited set of management capabilities when compared to the other methods. See [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) for a list of supported devices.  -->

## <a name="intune-supported-web-browsers"></a>Przeglądarki sieci Web obsługiwane przez usługę Intune

Różne zadania administracyjne wymagają użycia jednej z następujących witryn administracyjnych sieci Web.

- [Centrum administracyjne platformy Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Portal Azure](https://portal.azure.com/)

Dla tych portali obsługiwane są następujące przeglądarki:

- Microsoft Edge (najnowsza wersja)
- Microsoft Internet Explorer 11
- Safari (najnowsza wersja, tylko Mac)
- Chrome (najnowsza wersja)
- Firefox (najnowsza wersja)

### <a name="intune-classic-portal"></a>Klasyczny portal usługi Intune

Klasyczny portal usługi Intune służy tylko do zarządzania urządzeniami zarejestrowanymi przy użyciu oprogramowania klienckiego usługi Intune (https://manage.microsoft.com). Klasyczny portal usługi Intune wymaga obsługi przeglądarki programu Silverlight.

Następujące przeglądarki programu Silverlight obsługują konsolę usługi Intune:

- Internet Explorer 10 lub nowsza wersja
- Google Chrome (wersje poprzedzające wersję 42)
- Mozilla Firefox z włączonym dodatkiem Silverlight (wersje wcześniejsze niż wersja 56)

> [!Note]
> Przeglądarka Microsoft Edge i przeglądarki dla urządzeń przenośnych nie są obsługiwane przez portal klasyczny usługi Intune, ponieważ nie obsługują technologii [Microsoft Silverlight](https://msdn.microsoft.com/library/cc838158(v=vs.95).aspx).

Do tego portalu mogą logować się tylko użytkownicy z uprawnieniami administratora usługi lub administratorzy dzierżawy z rolą administratora globalnego. Aby można było uzyskać dostęp do konsoli administracyjnej, konto musi mieć licencję na korzystanie z usługi Intune i stan logowania **Dozwolone**.
