---
title: Usuwanie urządzenia z systemem Windows z usługi Intune
description: Opis sposobu usunięcia urządzenia z systemem Windows z usługi Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/01/2018
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
ms.openlocfilehash: 980b7d9f221fd1a1ae12f27743757d5b3bd53492
ms.sourcegitcommit: 5f6117b83f96f7d93dde3685c2ff2b67ae53740b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2018
ms.locfileid: "39481193"
---
# <a name="remove-your-windows-device-from-intune-management"></a>Usuwanie urządzenia z systemem Windows z zarządzania za pomocą usługi Intune

Usuń zarejestrowane urządzenie z systemem Windows z usługi Intune, gdy już nie chcesz lub nie musisz:  
* Korzystać z urządzenia do pracy lub nauki. 
* Uzyskiwać dostępu do służbowych aplikacji, poczty e-mail lub innych zasobów.

Po usunięciu urządzenia nie będziesz mieć możliwości uzyskania za jego pomocą dostępu do służbowych zasobów. Urządzenia z systemem Windows, które można usunąć z usługi Intune:  
* Urządzenia z systemem Windows 10 
* Komputer z systemem Windows 8.1
* Urządzenie mobilne z systemem Windows 8.1
 
Aby uzyskać więcej informacji o tym, co się stanie po usunięciu urządzenia z zarządzania za pomocą usługi Intune, zobacz temat [Co się stanie w przypadku usunięcia urządzenia z usługi Intune](what-happens-if-you-unenroll-your-device-from-intune-windows.md).

## <a name="remove-your-windows-10-device"></a>Usuwanie urządzenia z systemem Windows 10
Aby usunąć urządzenie z systemem Windows 10 z usługi Intune, wykonaj poniższe kroki.

### <a name="via-the-company-portal-app"></a>Za pomocą aplikacji Portal firmy

1. Otwórz aplikację Portal firmy.
2. Zaloguj się przy użyciu poświadczeń konta służbowego.
3. W obszarze **Moje urządzenia** wybierz urządzenie, które chcesz usunąć.
4. W górnym prawym rogu aplikacji, wybierz ikonę **Zobacz więcej**.
5. Wybierz pozycję **Usuń**. 
6. Aby potwierdzić zamiar usunięcia urządzenia, wybierz opcję **Usuń urządzenie**.

### <a name="via-device-settings-app"></a>Za pomocą aplikacji urządzenia Ustawienia
1. Otwórz aplikację Ustawienia. 
2. Przejdź kolejno do pozycji **Konta** > **Uzyskaj dostęp do miejsca pracy lub nauki**.
3. Wybierz podłączone konto, które chcesz usunąć > **Rozłącz**.
4. Aby potwierdzić zamiar usunięcia urządzenia, wybierz opcję **Tak**.

## <a name="remove-your-windows-81-computer"></a>Usuwanie komputera z systemem Windows 8.1
Aby usunąć komputer z systemem Windows 8.1 z usługi Intune, wykonaj poniższe kroki.

1.  Przejdź kolejno do pozycji **Ustawienia komputera** > **Sieć** > **Miejsce pracy**.
2.  W obszarze **Dołącz do miejsca pracy** wybierz pozycję **Opuść**.
3.  W obszarze **Włączanie zarządzania urządzeniami** wybierz pozycję **Wyłącz**.
4.  W otwartym oknie podręcznym wybierz pozycję **Wyłącz**.

## <a name="remove-your-windows-81-mobile-device"></a>Usuwanie urządzenia przenośnego z systemem Windows 8.1
Aby usunąć urządzenie przenośne z systemem Windows 8.1 z usługi Intune, wykonaj poniższe kroki.

1.  Przejdź do pozycji **Ustawienia** > **Miejsce pracy**.
2.  Naciśnij konto firmowe, które chcesz wyrejestrować.
3.  W dolnej części ekranu naciśnij pozycję **Usuń**.
4.  W oknie dialogowym **Usuń konto** naciśnij opcję **Usuń**.  
## <a name="removing-your-personal-information-after-removing-the-company-portal"></a>Usuwanie danych osobowych po usunięciu aplikacji Portal firmy
Istnieją dwa rodzaje danych, które aplikacja Portal firmy przechowuje na urządzeniu z systemem Windows:

-   **Dzienniki diagnostyczne**: dane o aktywności standardowej aplikacji gromadzone przez firmę Microsoft. Są one automatycznie usuwane po odinstalowaniu aplikacji Portal firmy. Do danych o aktywności aplikacji należą na przykład dane informujące o tym, jak długo aplikacja była otwarta lub czy miała miejsce awaria aplikacji.
-   **Pamięć podręczna aplikacji**: wybrane pliki pomocnicze wymagane do działania aplikacji, np. ikony i ustawienia.

Aby usunąć przechowywane dzienniki i pamięć podręczna, wykonaj jeden z następujących kroków:

* [Odinstalowywanie aplikacji Portal firmy](https://support.microsoft.com/help/4028003/windows-10-uninstall-apps-and-programs) 

* Zresetuj aplikację Portal firmy. Otwórz aplikację **Ustawienia** i wybierz pozycję > **Aplikacje** > **Portal firmy** > **Opcje zaawansowane** > **Resetuj**. 

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://portal.manage.microsoft.com#HelpDeskDialog).
