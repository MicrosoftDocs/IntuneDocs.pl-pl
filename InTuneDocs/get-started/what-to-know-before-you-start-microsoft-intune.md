---
title: "Obsługiwane urządzenia — Microsoft Intune | Dokumentacja firmy Microsoft"
description: "Podaje listę obsługiwanych platform urządzeń i przeglądarki do zarządzania urządzeniami w usłudze Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 271459e3faf886a45bcd673d2450f36a4a33a5db
ms.openlocfilehash: 7171dab36ace4915b51def2dd717e63df8438135
ms.contentlocale: pl-pl
ms.lasthandoff: 04/28/2017


---

# <a name="supported-devices-and-browsers"></a>Obsługiwane urządzenia i przeglądarki

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ten artykuł jest przeznaczony dla administratorów systemów odpowiedzialnych za zarządzanie urządzeniami w przedsiębiorstwie. Aby uzyskać pomoc dotyczącą instalowania usługi Intune na telefonie, zobacz artykuł [Korzystanie z zarządzanych urządzeń do wykonania pracy](https://docs.microsoft.com/intune/enduser/company-portal-frequently-asked-questions).

Przed rozpoczęciem konfigurowania usługi Microsoft Intune przejrzyj poniższe wymagania:

- [Obsługiwane urządzenia i komputery](#intune-supported-devices)
- [listę obsługiwanych przeglądarek sieci Web umożliwiających korzystanie z usługi Intune.](#intune-supported-web-browsers)

Zapoznaj się też z informacjami o [użyciu przepustowości sieci przez usługę Intune](network-bandwidth-use.md).

## <a name="intune-supported-devices"></a>Urządzenia obsługiwane przez usługę Intune

Korzystając z funkcji zarządzania urządzeniami przenośnymi usługi Intune, możesz zarządzać następującymi urządzeniami:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Usługi Intune nie można używać do zarządzania systemami operacyjnymi Windows Server.

Zarządzanie urządzeniami w usłudze Intune zapewnia [następujące możliwości](mobile-device-management-capabilities-in-microsoft-intune.md).

### <a name="windows-pc-software-client"></a>Oprogramowanie klienckie dla komputerów z systemem Windows

[Oprogramowanie klienckie usługi Intune](/intune/deploy-use/manage-windows-pcs-with-microsoft-intune) można wdrożyć i zainstalować na komputerach z systemem Windows jako alternatywną metodę rejestracji. Klient oprogramowania usługi Intune umożliwia zarządzanie komputerami z systemem Windows 7 lub nowszym, z wyjątkiem systemu Windows 10 Home Edition.

### <a name="exchange-activesync-management"></a>Zarządzanie przy użyciu programu Exchange ActiveSync

Możesz zarządzać [urządzeniami z zainstalowanym programem Exchange ActiveSync](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) przy użyciu konsoli usługi Intune. Ta opcja zapewnia ograniczony zestaw funkcji zarządzania w porównaniu z innymi metodami. W artykule [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) (Możliwości wbudowanego zarządzania urządzeniami przenośnymi w usłudze Office 365) znajduje się lista obsługiwanych urządzeń.

## <a name="intune-supported-web-browsers"></a>Przeglądarki sieci Web obsługiwane przez usługę Intune

Różne zadania administracyjne wymagają użycia jednej z następujących witryn administracyjnych sieci Web.

- [Portal usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Konsola administratora usługi Microsoft Intune](https://admin.manage.microsoft.com/)

|Funkcja usługi Intune |Obsługiwane przeglądarki|
|---------|---------|
|**Konsola administratora usługi Intune**     |  Internet Explorer 10 lub nowsza wersja<br /><br />Google Chrome (wersje poprzedzające wersję 42)<br /><br />Mozilla Firefox z włączonym dodatkiem Silverlight<br />**Uwaga:** w marcu 2017 roku Mozilla zakończy obsługę dodatku Silverlight. [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=836872). |
|**Portal administratorów usługi Office 365**     |Wszystkie przeglądarki, w tym przeglądarki dla urządzeń przenośnych i zarządzane przeglądarki  |
|**Witryna sieci Web Portal firmy**     |**Urządzenia przenośne:** należy używać domyślnej przeglądarki sieci Web dla każdej z obsługiwanych platform   <br /><br />**Komputery z systemem Windows:** Internet Explorer 10 lub nowsza wersja albo Microsoft Edge<br /><br />**System Mac OS X 10.9 lub nowszy:** Apple Safari    |

> [!Note]
> Przeglądarka Microsoft Edge i przeglądarki dla urządzeń przenośnych nie są obsługiwane przez konsolę administracyjną, ponieważ nie obsługują technologii [Microsoft Silverlight](https://msdn.microsoft.com/library/cc838158(v=vs.95).aspx). Konsola usługi Intune stopniowo odchodzi od technologii Silverlight. Docelowo wszystkie funkcje usługi Intune z zakresu zarządzania urządzeniami przenośnymi i aplikacjami zostaną [udostępnione w nowym portalu Microsoft Azure](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).


Do tego portalu mogą logować się tylko użytkownicy z uprawnieniami administratora usługi lub administratorzy dzierżawy z rolą administratora globalnego. Aby można było uzyskać dostęp do konsoli administracyjnej, konto musi mieć licencję na korzystanie z usługi Intune i stan logowania **Dozwolone**.

>[!div class="step-by-step"]

>[**Obsługa sieci** &rarr;](network-bandwidth-use.md)  

