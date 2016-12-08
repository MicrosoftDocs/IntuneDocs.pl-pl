---
title: "Ręczne synchronizowanie urządzenia z systemem Windows | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 443c6de7-5187-4dc4-b844-6085a0c659bd
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9ddbcde20fac83289c4622f69538ff00fa0cb65b
ms.openlocfilehash: 2fad0ea18485290a513d175fecf0a4947786e5eb


---


# <a name="sync-your-windows-device-manually"></a>Ręczne synchronizowanie urządzenia z systemem Windows
Jeśli instalowanie aplikacji trwa zbyt długo, możesz spróbować ręcznie zsynchronizować urządzenie z systemem Windows. Ręczna synchronizacja może przyspieszyć instalację.

Obsługiwane są wyłącznie następujące wersje. Jeśli urządzenia nie ma na liście, synchronizacja nie jest obsługiwana. Skorzystaj z instrukcji odpowiednich dla typu używanego urządzenia.

* [Windows 10 Mobile](#windows-10-mobile)
* [Windows 10 Desktop](#windows-10-desktop)
* [Windows Phone 8.1](#windows-phone-8-1)


## <a name="windows-10-mobile"></a>Windows 10 Mobile
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

## <a name="windows-10-desktop"></a>Windows 10 Desktop
Istnieje więcej niż jedna wersja systemu Windows 10, więc przygotowano dwie procedury. Aby wybrać odpowiednią procedurę, spójrz na zrzuty ekranu, a następnie wykonaj kroki, które odpowiadają temu, co widzisz na swoim urządzeniu. 

1. Wybierz przycisk **Start**, a następnie wybierz pozycję **Ustawienia**.

    ![Przycisk Start](./media/win10pc-sync-1-start-button.png)

2. Na stronie **Ustawienia** wybierz pozycję **Konta**.

    ![Wybieranie kont na stronie Ustawienia](./media/win10pc-sync-2-settings-accounts.png)

3. Przyjrzyj się obu ekranom i zastanów się, który z nich przypomina zawartość ekranu urządzenia. Wykonaj kroki odnoszące się do ekranu przypominającego ekran urządzenia.

    Jeśli widzisz ten ekran („Uzyskaj dostęp do miejsca pracy lub nauki”), postępuj zgodnie z instrukcjami opisanymi w sekcji [Procedura w przypadku wyświetlenia ekranu Uzyskaj dostęp do miejsca pracy lub nauki](#steps-to-follow-if-you-see-access-work-or-school).

    ![Procedura synchronizacji w przypadku wyświetlenia ekranu Uzyskaj dostęp do miejsca pracy lub nauki](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    Jeśli widzisz ten ekran („Dostęp z miejsca pracy”), postępuj zgodnie z instrukcjami opisanymi w sekcji [Procedura w przypadku wyświetlenia ekranu Dostęp z miejsca pracy](#steps-to-follow-if-you-see-your-account).

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



<!--HONumber=Nov16_HO1-->


