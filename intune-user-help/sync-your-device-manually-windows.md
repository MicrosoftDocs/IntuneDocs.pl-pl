---
title: "Ręczne synchronizowanie urządzenia z systemem Windows | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 443c6de7-5187-4dc4-b844-6085a0c659bd
searchScope: User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 05b290345c761372850fb501a3707dbd53a3ef07
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="sync-your-windows-device-manually"></a>Ręczne synchronizowanie urządzenia z systemem Windows

Czasami próba zainstalowania aplikacji na urządzeniu z systemem Windows może trwać dłużej niż się wydaje. W takim przypadku można spróbować ręcznie zsynchronizować urządzenie z systemem Windows. Synchronizacja może przyspieszyć instalację.

> [!Note]
> Instalowanie aplikacje może potrwać trochę czasu w przypadku pracy w wolniejszej sieci lub w sieci z większą ilością urządzeń pobierających zawartość w tym samym czasie.

Poniższe wersje systemu Windows można synchronizować ręcznie. Niestety, jeśli Twoje urządzenie używa innej wersji systemu Windows, nie jest możliwe uruchomienie synchronizacji ręcznej.

* [Synchronizuj system Windows 10 Desktop](#windows-10-desktop)
* [Synchronizuj system Windows 10 Mobile](#windows-10-mobile)
* [Synchronizuj system Windows Phone 8.1](#windows-phone-81)

## <a name="windows-10-desktop"></a>Windows 10 Desktop
Istnieje więcej niż jedna wersja systemu Windows 10, więc przygotowano dwie procedury. Aby wybrać odpowiednią procedurę, spójrz na zrzuty ekranu, a następnie wykonaj kroki, które odpowiadają temu, co widzisz na swoim urządzeniu.

1. Wybierz przycisk **Start**, a następnie wybierz pozycję **Ustawienia**.

    ![Przycisk Start](./media/win10pc-sync-1-start-button.png)

2. Na stronie **Ustawienia** wybierz pozycję **Konta**.

    ![Wybieranie kont na stronie Ustawienia](./media/win10pc-sync-2-settings-accounts.png)

3. Przyjrzyj się obu ekranom i zastanów się, który z nich przypomina zawartość ekranu urządzenia. Wykonaj kroki odnoszące się do ekranu przypominającego ekran urządzenia.

    Jeśli widzisz ten ekran („Uzyskaj dostęp do miejsca pracy lub nauki”), postępuj zgodnie z instrukcjami opisanymi w sekcji [Procedura w przypadku wyświetlenia ekranu Uzyskaj dostęp do miejsca pracy lub nauki](#steps-to-follow-if-you-see-access-work-or-school).

    ![Procedura synchronizacji w przypadku wyświetlenia ekranu Uzyskaj dostęp do miejsca pracy lub nauki](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    Jeśli widzisz ten ekran („Dostęp z miejsca pracy”), postępuj zgodnie z instrukcjami opisanymi w sekcji [Procedura w przypadku wyświetlenia ekranu Dostęp z miejsca pracy](#steps-to-follow-if-you-see-work-access).

    ![Wybieranie dostępu z miejsca pracy jako typu konta](./media/win10pc-sync-3-work-access.png)

### <a name="steps-to-follow-if-you-see-access-work-or-school"></a>Czynności w przypadku wyświetlenia ekranu Dostęp do zasobów służbowych

1. Na stronie **Konta** wybierz pozycję **Uzyskaj dostęp do miejsca pracy lub nauki**.

    ![Wybieranie pozycji Uzyskaj dostęp do miejsca pracy lub nauki](./media/w10-enroll-rs1-connect-to-work-or-school.png)

2. Wybierz swoje konto służbowe. W zależności od tego, jak administrator IT skonfigurował środowisko, mogą zostać wyświetlone dwa konta wyglądające podobnie jak na poniższym przykładzie. Obok jednego konta jest wyświetlona ikona aktówki, a obok drugiego — logo firmy Microsoft.

    - Jeśli widzisz konto z aktówką, wybierz je i poszukaj pod nim przycisku **Informacje**.
    - Jeśli widzisz tylko konto z logo firmy Microsoft, wybierz je i poszukaj pod nim przycisku **Informacje**.

    ![Wybieranie nazwy konta obok logo aktówki lub logo firmy Microsoft](./media/win10pc-rs1-sync-info-button.png)

3. Wybierz przycisk **Informacje**. Zostanie otwarte okno dialogowe przypominające poniższe.

    ![Wybieranie nazwy konta obok logo aktówki lub logo firmy Microsoft](./media/win10pc-rs1-sync-button.png)

4. Wybierz przycisk **Synchronizuj**. Urządzenie zostanie zsynchronizowane z usługą Intune.

### <a name="steps-to-follow-if-you-see-work-access"></a>Procedura w przypadku wyświetlenia ekranu Dostęp z miejsca pracy

1. Na stronie **Konta** wybierz pozycję **Dostęp z miejsca pracy**.

    ![Wybieranie dostępu z miejsca pracy jako typu konta](./media/win10pc-sync-3-work-access.png)

2. W sekcji **Rejestrowanie w celu zarządzania urządzeniami** wybierz nazwę swojej firmy.

    ![Wybieranie nazwy firmy w celu zarządzania urządzeniami](./media/win10pc-sync-4-tap-com-name.png)

3. Wybierz przycisk **Synchronizuj**.

    ![Wybieranie przycisku Synchronizuj](./media/win10pc-sync-5-tap-sync.png)

   Przycisk będzie szary aż do zakończenia synchronizacji.

### <a name="windows-10-mobile"></a>Windows 10 Mobile
Aby ręcznie zsynchronizować urządzenie z systemem Windows 10 Mobile w celu przyspieszenia powolnej instalacji aplikacji:

   1. Wybierz pozycje **Wszystkie aplikacje** > **Ustawienia** > **Konta**.

       ![Wybieranie kont na ekranie Ustawienia](./media/win10m-sync-1-settings-accounts.png)

   2. Wybierz pozycję **Dostęp z miejsca pracy**.

       ![Wybieranie dostępu z miejsca pracy jako typu konta](./media/win10m-sync-2-work-access.png)

   3. W obszarze **Rejestrowanie w celu zarządzania urządzeniami** wybierz nazwę firmy.

       ![Wybieranie nazwy firmy w celu zarządzania urządzeniami](./media/win10m-sync-3-tap-comp-name.png)

   4. Wybierz ikonę **Synchronizuj**.

       ![Wybieranie ikony Synchronizuj](./media/win10m-sync-4-tap-sync.png)

       W górnej części ekranu pojawi się komunikat „Synchronizujemy Twoje konto”. Przycisk **Synchronizuj** będzie szary, dopóki synchronizacja urządzenia nie zakończy się.

## <a name="windows-phone-81"></a>Windows Phone 8.1
Aby ręcznie zsynchronizować urządzenie z systemem Windows Phone 8.1 w celu przyspieszenia powolnej instalacji aplikacji:

1. Wybierz pozycje **Wszystkie aplikacje** > **Ustawienia** > **Miejsce pracy**.

    ![Lista ustawień](./media/wp81-1-sync-settings-workplace.png)

2. Wybierz nazwę firmy.

    ![Wybieranie nazwy firmy dla konta firmowego](./media/wp81-2-sync-tap-compname.png)

3. Wybierz ikonę **Synchronizuj**.

    ![Wybieranie ikony Synchronizuj](./media/wp81-3-sync-tap-sync-button.png)

   W górnej części ekranu pojawi się komunikat „Synchronizujemy Twoje konto”, który będzie widoczny aż do zakończenia synchronizowania urządzenia.

Nadal potrzebujesz pomocy? Skontaktuj się z administratorem IT. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](http://portal.manage.microsoft.com).
