---
title: Ręczne synchronizowanie urządzenia z systemem Windows | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 07/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 289d99603314be7c1097d54d59d4a0e90cae0bed
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72508334"
---
# <a name="sync-your-windows-device-manually"></a>Ręczne synchronizowanie urządzenia z systemem Windows

W przypadku niezadowalającej prędkości instalacji aplikacji należy zainicjować ręczną synchronizację urządzenia. Ręczna synchronizacja wymusza połączenie urządzenia z usługą Intune w celu pobrania najnowszych aktualizacji i wiadomości. Po ukończeniu synchronizacji urządzenia prędkość instalacji może wzrosnąć.

Usługa Intune obsługuje ręczną synchronizację z aplikacji Portal firmy, paska zadań na pulpicie i aplikacji Ustawienia na urządzeniu. Funkcje aplikacji Portal firmy są obsługiwane na urządzeniach z systemem Windows 10 z aktualizacją Creator’s Update (1703) lub nowszą. 

Za pomocą aplikacji Ustawienia na urządzeniu można synchronizować wszystkie urządzenia z systemem Windows, w tym:

* [Windows 10 Desktop](#windows-10-desktop)  
* [Microsoft HoloLens](#microsoft-hololens)   
* [Windows 10 Mobile](#windows-10-mobile)  
* [Windows Phone 8.1](#windows-phone-81)    

## <a name="sync-directly-from-company-portal-app-for-windows"></a>Synchronizacja bezpośrednio z aplikacji Portal firmy dla systemu Windows
Wykonaj następujące kroki, aby ręcznie zsynchronizować wszystkie urządzenia z systemem Windows 10 zawierającym aktualizację Creator’s Update (wersja 1703) lub nowszą.

1. Otwórz aplikację Portal firmy na urządzeniu.

2. Wybierz **Ustawienia** > **Synchronizacja**.

    ![Zrzut ekranu strony głównej aplikacji Portal firmy, wyróżnione Ustawienia](./media/RS1_homePage_settings_04.png)  
    
    ![Zrzut ekranu strony ustawień aplikacji Portal firmy, wyróżniony przycisk Synchronizuj](./media/RS1_settingspage_sync05.png)  

## <a name="sync-from-device-taskbar-or-start-menu"></a>Synchronizacja z paska zadań urządzenia lub menu Start   

Sterowanie synchronizacją jest także dostępne spoza aplikacji — z pulpitu urządzenia. Jeśli aplikacja została przypięta bezpośrednio do paska zadań lub menu Start, można szybko wykonać synchronizację.  

1. Znajdź ikonę aplikacji Portal firmy na pasku zadań lub w menu Start.  
2. Kliknij prawym przyciskiem myszy ikonę aplikacji, aby wyświetlić jej menu (tzw. listę szybkiego dostępu).  

    ![Zrzut ekranu paska zadań systemu Windows na pulpicie urządzenia. Ikona aplikacji Portal firmy została kliknięta, aby wyświetlić menu z opcjami „Przypnij do paska zadań” i „Zamknij okno” oraz akcją „Synchronizuj to urządzenie”.](./media/sync-device-from-start-menu-1807.png)  

3. Wybierz pozycję **Synchronizuj to urządzenie**. Spowoduje to otwarcie aplikacji Portal firmy na stronie **Ustawienia** i zainicjowanie synchronizacji.  

## <a name="sync-from-settings-app"></a>Synchronizacja z ustawień aplikacji 
Wykonaj następujące kroki, aby ręcznie zsynchronizować urządzenia Microsoft HoloLens, Windows 10 Desktop, Windows 10 Mobile lub Windows Phone 8.1 przy użyciu aplikacji Ustawienia.  

### <a name="windows-10-desktop"></a>Windows 10 Desktop
1. Na urządzeniu wybierz opcje **Start** > **Ustawienia**.

2. Wybierz pozycję **Konta**.

    ![Wybieranie kont na stronie Ustawienia](./media/win10pc-sync-2-settings-accounts.png)  

3. Istnieje wiele wersji systemu Windows 10 na komputery stacjonarne. Porównaj swój ekran z przedstawionymi poniżej zrzutami, aby określić czynności do wykonania. 

    * Jeśli na ekranie jest wyświetlany napis**Uzyskaj dostęp do miejsca pracy lub nauki**, przejdź do procedury w sekcji [Uzyskaj dostęp do miejsca pracy lub nauki](#access-work-or-school-steps).

    ![Opcja Uzyskaj dostęp do miejsca pracy lub nauki w ustawieniach aplikacji](./media/w10-enroll-rs1-connect-to-work-or-school.png)  

    * W przypadku napisu **Dostęp z miejsca pracy** przejdź do procedury w sekcji [Dostęp z miejsca pracy](#work-access-steps).  

    ![Wybieranie dostępu z miejsca pracy jako typu konta](./media/win10pc-sync-3-work-access.png)

#### <a name="access-work-or-school-steps"></a>Czynności dla opcji Uzyskaj dostęp do miejsca pracy lub nauki

1. Wybierz **Uzyskaj dostęp do miejsca pracy lub nauki**.

    ![Zrzut ekranu przedstawiający opcję Uzyskaj dostęp do miejsca pracy lub nauki](./media/w10-enroll-rs1-connect-to-work-or-school.png)  

2. Wybierz konto, obok którego znajduje się ikona aktówki. Jeśli nie widzisz takiego konta, może to oznaczać, że firma skonfigurowała ustawienia w inny sposób. Zamiast tego kliknij konto, obok którego znajduje się logo firmy Microsoft.

     ![Wybieranie nazwy konta obok logo aktówki lub logo firmy Microsoft](./media/win10pc-rs1-sync-info-button.png)

3. Kliknij **Informacje**. 

4. Kliknij **Synchronizuj**. 

#### <a name="work-access-steps"></a>Czynności dla opcji Dostęp z miejsca pracy

1. Kliknij **Dostęp z miejsca pracy**.

    ![Wybieranie dostępu z miejsca pracy jako typu konta](./media/win10pc-sync-3-work-access.png)

2. W obszarze **Rejestrowanie w celu zarządzania urządzeniami** wybierz nazwę firmy.

    ![Wybieranie nazwy firmy w celu zarządzania urządzeniami](./media/win10pc-sync-4-tap-com-name.png)

3. Kliknij **Synchronizuj**. Przycisk pozostaje wyłączony do zakończenia synchronizacji.

    ![Wybieranie przycisku Synchronizuj](./media/win10pc-sync-5-tap-sync.png)  


### <a name="windows-10-mobile"></a>Windows 10 Mobile

   1. Na swoim urządzeniu wybierz pozycje **Wszystkie aplikacje** > **Ustawienia** > **Konta**.

       ![Wybieranie kont na ekranie Ustawienia](./media/win10m-sync-1-settings-accounts.png)

   2. Wybierz pozycję **Dostęp z miejsca pracy**.

       ![Wybieranie dostępu z miejsca pracy jako typu konta](./media/win10m-sync-2-work-access.png)

   3. W obszarze **Rejestrowanie w celu zarządzania urządzeniami** wybierz nazwę firmy.

       ![Wybieranie nazwy firmy w celu zarządzania urządzeniami](./media/win10m-sync-3-tap-comp-name.png)

   4. Wybierz ikonę **Synchronizacja**. Przycisk pozostaje wyłączony do zakończenia synchronizacji.

       ![Wybieranie ikony Synchronizuj](./media/win10m-sync-4-tap-sync.png)  
### <a name="microsoft-hololens"></a>Microsoft HoloLens  
Te instrukcje dotyczą urządzeń HoloLens z systemem Windows 10 z aktualizacją Anniversary Update (znanej także jako RS1). 
1. Otwórz na urządzeniu aplikację Ustawienia.  

2. Wybierz **Konta** > **Dostęp z miejsca pracy**.  
    ![Zrzut ekranu aplikacji Ustawienia na urządzeniu HoloLens, wyróżniony link kont](./media/RS1_holoLens_SettingsRS1_Accounts_06.png)  

3. Wybierz swoje połączone konto > **Synchronizacja**.  ![Zrzut ekranu aplikacji Ustawienia na urządzeniu HoloLens, wyróżniony przycisk synchronizacji](./media/RS1_holoLens_SyncRS1_Sync_08.png)  

### <a name="windows-phone-81"></a>Windows Phone 8,1

1. Wybierz pozycje **Wszystkie aplikacje** > **Ustawienia** > **Miejsce pracy**.

    ![Lista ustawień](./media/wp81-1-sync-settings-workplace.png)

2. Wybierz nazwę firmy.

    ![Wybieranie nazwy firmy dla konta firmowego](./media/wp81-2-sync-tap-compname.png)

3. Wybierz ikonę **Synchronizacja**.

    ![Wybieranie ikony Synchronizuj](./media/wp81-3-sync-tap-sync-button.png)

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).
