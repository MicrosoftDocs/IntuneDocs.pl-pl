---
title: Zarządzanie aplikacjami z witryny Portal firmy usługi Intune
description: Zarządzanie i wyświetlanie dostępnych i zainstalowanych aplikacji
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 06/27/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: edc45fb3ddab43ef77a3f072c5a1a31f8f88c957
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72506112"
---
# <a name="manage-apps-from-the-company-portal-website"></a>Pobieranie aplikacji firmowych z witryny internetowej Portalu firmy 
Odwiedź witrynę [Portal firmy](https://portal.manage.microsoft.com) , aby wyświetlić aplikacje w organizacji i zarządzać nimi. 

## <a name="view-all-apps"></a>Wyświetl wszystkie aplikacje  
Z menu wybierz pozycję **aplikacje** , aby wyświetlić wszystkie aplikacje udostępnione przez Twoją organizację. 

   ![Zrzut ekranu przedstawiający Portal firmy witryny sieci Web, na stronie aplikacje, z uwzględnieniem opcji uściślania.](./media/intune-view-apps-1907.png)  

Na tej stronie przedstawiono następujące szczegóły dotyczące poszczególnych aplikacji:  

* Nazwa: Nazwa aplikacji z linkiem do strony szczegółów aplikacji.
* Wydawca: Nazwa dewelopera lub firmy, która rozproszona aplikację. Wydawca jest zazwyczaj dostawcą oprogramowania lub Twoją organizacją.  
* Data publikacji: Data, z której aplikacja została udostępniona do pobrania. Data publikacji może zawierać wersję początkową aplikacji lub ostatnią aktualizację aplikacji.
* Stan: bieżący stan aplikacji na urządzeniu, w tym dostępne, zainstalowane i instalowane. 
* Kategoria: funkcja lub cel aplikacji, na przykład Polecane, inżynieria, edukacja i produktywność.  

### <a name="search-and-refine"></a>Wyszukaj i Uściślij   

Użyj paska wyszukiwania, aby znaleźć aplikacje. Wyniki wyszukiwania są sortowane automatycznie według istotności.  

   ![Zrzut ekranu przedstawiający Portal firmy witryny sieci Web, na stronie aplikacje, z uwzględnieniem opcji uściślania.](./media/intune-refine-all-apps-1907.png)  

Wybierz pozycję **Uściślij** , aby wyświetlić opcje filtrowania i sortowania. Przefiltruj listę, aby wyświetlić aplikacje z określonymi kryteriami, w tym **typu**, **dostępności**i **wydawców**. Wybierz pozycję **Sortuj** , aby ponownie rozmieścić aplikacje według:

* Nazwa aplikacji, rosnąco lub malejąco alfabetycznie 
* Nazwa wydawcy, rosnąco lub malejąco alfabetycznie 
* Data publikacji, najstarsza lub Najnowsza  

## <a name="view-installed-apps"></a>Wyświetlanie zainstalowanych aplikacji  
Z menu wybierz pozycję **zainstalowane aplikacje** , aby wyświetlić listę wszystkich aplikacji zainstalowanych na urządzeniu.  

   ![Zrzut ekranu przedstawiający stronę Zainstalowane aplikacje w witrynie Portal firmy.](./media/intune-installed-apps-1907.png)  


Na tej stronie przedstawiono następujące szczegóły dotyczące poszczególnych aplikacji:  

* Nazwa: Nazwa aplikacji z linkiem do strony szczegółów aplikacji.
* Typ przypisania: sposób przypisywania i udostępniania aplikacji. Aby uzyskać więcej informacji, zobacz dostępne i wymagane aplikacje. Twoja organizacja może udostępnić aplikację, aby można było ją zainstalować samodzielnie, lub będzie ona mogła automatycznie wymagać i instalować aplikację na urządzeniu.  
* Wydawca: Nazwa dewelopera lub firmy, która rozproszona aplikację. Wydawca jest zazwyczaj dostawcą oprogramowania lub Twoją organizacją.  
* Data publikacji: Data, z której aplikacja została udostępniona do pobrania. Data publikacji może zawierać wersję początkową aplikacji lub ostatnią aktualizację aplikacji.
* Stan: bieżący stan instalacji aplikacji na urządzeniu. Aplikacje mogą pokazać, że instalacja, instalacja i instalacja nie powiodły się. Aby można było wyświetlić aktualny stan, wymagane aplikacje mogą potrwać do 10 minut.  

### <a name="search-and-refine"></a>Wyszukaj i Uściślij  

Użyj paska wyszukiwania, aby znaleźć aplikacje. Wyniki wyszukiwania są sortowane automatycznie według istotności.  

   ![Zrzut ekranu przedstawiający witrynę Portal firmy, zainstalowane aplikacje oraz opcje uściślania.](./media/intune-installed-refine-1907.png)  

Wybierz pozycję **Uściślij** , aby wyświetlić opcje filtrowania i sortowania. Przefiltruj listę, aby wyświetlić aplikacje z określonymi kryteriami, takimi jak **typy**, **wydawcy**i **Stany**. Wybierz pozycję **Sortuj** , aby ponownie rozmieścić aplikacje według:

* Nazwa aplikacji, rosnąco lub malejąco alfabetycznie  
* Nazwa wydawcy, rosnąco lub malejąco alfabetycznie  
* Data publikacji, najstarsza lub Najnowsza  

Potrzebujesz dodatkowej pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).  

### <a name="available-and-required-apps"></a>Aplikacje dostępne i wymagane
Aplikacje są przypisane do Ciebie przez organizację i oznaczone jako dostępne lub wymagane. Na stronie **zainstalowane aplikacje** są wyświetlane aplikacje, które znajdują się w kolumnie **Typ przypisania** . 


* Dostępne aplikacje: te aplikacje są wybierane przez organizację i są odpowiednie i przydatne w przypadku pracy lub szkoły. Są one opcjonalne do zainstalowania i są jedynymi aplikacjami, które znajdują się w Portal firmy do zainstalowania. 

* Aplikacje wymagane: Twoja organizacja może wdrażać niezbędne aplikacje służbowe bezpośrednio na urządzeniu. Te aplikacje są automatycznie instalowane bez interwencji. 

Aplikacje są również udostępniane na podstawie typu używanego urządzenia. Jeśli na przykład używasz witryny internetowej Portalu firmy na urządzeniu z systemem Windows, będziesz mieć dostęp do aplikacji dla systemu Windows, ale nie dla systemu iOS.  

## <a name="view-app-details"></a>Wyświetl szczegóły aplikacji  
Wybierz aplikację na stronie **aplikacje** lub **zainstalowane aplikacje** , aby wyświetlić jej szczegóły. Nastąpi przekierowanie do **szczegółów aplikacji**, w której znajdziesz opis i wymagania aplikacji. Jeśli aplikacja nie jest już zainstalowana na urządzeniu, możesz ją zainstalować z tej strony. 


   ![Zrzut ekranu przedstawiający witrynę sieci Web Portal firmy, Strona szczegółów aplikacji.](./media/intune-app-details-1907.png)  

## <a name="next-steps"></a>Następne kroki
Potrzebujesz dodatkowej pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).  
