---
title: Usuwanie urządzenia z systemem Windows z zarządzania za pomocą usługi Intune
description: Opis sposobu usuwania urządzenia z systemem Windows z zarządzania w usłudze Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 018bda65-7238-41f5-b92a-e5f67b7fe085
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 50833b33583dcc1b49eb9009995b8ccd6c79e1f0
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2019
ms.locfileid: "67546645"
---
# <a name="remove-your-windows-device-from-management"></a>Usuwanie urządzenia z systemem Windows z zarządzania

Usuń zarejestrowane urządzenie z systemem Windows z zarządzania w usłudze Intune, gdy już nie chcesz lub nie musisz:  
* Korzystać z urządzenia do pracy lub nauki. 
* Uzyskiwać dostępu do służbowych aplikacji, poczty e-mail lub innych zasobów.

Po wyrejestrowaniu urządzenia utracisz dostęp urządzenia do zasobów służbowych. Poniższe urządzenia z systemem Windows można usunąć z zarządzania.  
* Urządzenia z systemem Windows 10 
* Komputer z systemem Windows 8.1
* Telefon z systemem Windows 8.1
 
Aby uzyskać więcej informacji o tym, co się stanie po usunięciu urządzenia z zarządzania, zobacz temat [Co się stanie w przypadku usunięcia urządzenia z usługi Intune](what-happens-if-you-unenroll-your-device-from-intune-windows.md).  

## <a name="remove-your-windows-10-device"></a>Usuwanie urządzenia z systemem Windows 10
Aby usunąć urządzenie z systemem Windows 10 z zarządzania, wykonaj poniższe kroki.

### <a name="remove-in-company-portal-app-home-page"></a>Usuwanie w aplikacji Portal firmy, **strona główna**  

1. Otwórz aplikację Portal firmy.
2. Na **stronie głównej** przejdź w dół do sekcji **Moje urządzenia**.
3. Wybierz urządzenie, które chcesz usunąć.
3. W górnym prawym rogu aplikacji, wybierz ikonę **Zobacz więcej**.
4. Wybierz pozycję **Usuń**. 
5. Aby potwierdzić zamiar usunięcia urządzenia, wybierz pozycję **Usuń**.  

### <a name="remove-in-company-portal-app-device-context-menu"></a>Usuwanie w aplikacji Portal firmy, menu kontekstowe urządzenia  

1. Otwórz aplikację Portal firmy i przejdź do pozycji **Moje urządzenia**.

    ![Przykładowy zrzut ekranu przedstawiający aplikację Portal firmy dla systemu Windows, strona główna z wyróżnieniem sekcji Moje urządzenia.](./media/1809_CheckAccess_Context_Select_Device.png)

2. Kliknij prawym przyciskiem myszy lub naciśnij i przytrzymaj urządzenie, aby otworzyć jego [menu kontekstowe](https://docs.microsoft.com//windows/uwp/design/controls-and-patterns/menus).  

3. Wybierz pozycję **Usuń**.  

    ![Przykładowy zrzut ekranu aplikacji Portal firmy dla systemu Windows, strona główna. Menu kontekstowe urządzenia jest widoczne w sekcji **Moje urządzenia** strony i przedstawia akcje „Zmień nazwę”, „Usuń” oraz „Sprawdź dostęp”.](./media/1809_DeviceContextMenu_Windows_CP.png)  

5. W potwierdzeniu kliknij pozycję **Dowiedz się więcej**, aby przeczytać dalsze informacje na temat możliwych zmian dostępu do zasobów służbowych. Aby potwierdzić zamiar usunięcia urządzenia, wybierz pozycję **Usuń**.   

     ![Przykładowy zrzut ekranu aplikacji Portal firmy dla systemu Windows, strona główna. Nad urządzeniem pojawi się pole zmiany nazwy, w którym użytkownik może wpisać nową nazwę i kliknąć opcję Zmień nazwę lub Anuluj.](./media/1808_RemoveDevice_Popup.png)  


### <a name="remove-in-device-settings-app"></a>Usuwanie w aplikacji urządzenia Ustawienia
1. Otwórz aplikację Ustawienia. 
2. Przejdź kolejno do pozycji **Konta** > **Uzyskaj dostęp do miejsca pracy lub nauki**.
3. Wybierz podłączone konto, które chcesz usunąć > **Rozłącz**.
4. Aby potwierdzić zamiar usunięcia urządzenia, wybierz opcję **Tak**.

## <a name="remove-your-windows-81-computer"></a>Usuwanie komputera z systemem Windows 8.1
Aby usunąć komputer z systemem Windows 8.1 z usługi Intune, wykonaj poniższe kroki.

1. Przejdź kolejno do pozycji **Ustawienia komputera** > **Sieć** > **Miejsce pracy**.
2. W obszarze **Dołącz do miejsca pracy** wybierz pozycję **Opuść**.
3. W obszarze **Włączanie zarządzania urządzeniami** wybierz pozycję **Wyłącz**.
4. W otwartym oknie podręcznym wybierz pozycję **Wyłącz**.

## <a name="remove-your-windows-81-phone"></a>Usuwanie telefonu z systemem Windows 8.1
Aby usunąć telefon z systemem Windows 8.1 z usługi Intune, wykonaj poniższe kroki.

1. Przejdź do pozycji **Ustawienia** > **Miejsce pracy**.
2. Naciśnij konto firmowe, które chcesz wyrejestrować.
3. W dolnej części ekranu naciśnij pozycję **Usuń**.
4. W oknie dialogowym **Usuń konto** naciśnij opcję **Usuń**.  
## <a name="removing-your-personal-information-after-removing-the-company-portal"></a>Usuwanie danych osobowych po usunięciu aplikacji Portal firmy  

Istnieją dwa rodzaje danych, które aplikacja Portal firmy przechowuje na urządzeniu z systemem Windows:

- **Dzienniki diagnostyczne**: dane o aktywności standardowej aplikacji gromadzone przez firmę Microsoft. Są one automatycznie usuwane po odinstalowaniu aplikacji Portal firmy. Do danych o aktywności aplikacji należą na przykład dane informujące o tym, jak długo aplikacja była otwarta lub czy miała miejsce awaria aplikacji.
- **Pamięć podręczna aplikacji**: wybrane pliki pomocnicze wymagane do działania aplikacji, np. ikony i ustawienia.

Aby usunąć przechowywane dzienniki i pamięć podręczna, wykonaj jeden z następujących kroków:

* [Odinstalowywanie aplikacji Portal firmy](https://support.microsoft.com/help/4028003/windows-10-uninstall-apps-and-programs) 

* Zresetuj aplikację Portal firmy. Otwórz aplikację **Ustawienia** i wybierz pozycję > **Aplikacje** > **Portal firmy** > **Opcje zaawansowane** > **Resetuj**. 

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).
