---
title: "Resetowanie kodu dostępu urządzenia z poziomu witryny sieci Web Portal firmy | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
ms.author: stabar
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2aea845bc00c153f070e04abb67582a5d5a726ca
ms.openlocfilehash: 47b36616f7a8ee23d4d47b41a1db2c41c185c6f5


---


# Resetowanie kodu dostępu urządzenia z poziomu witryny sieci Web Portal firmy

Jeśli utracisz numer PIN lub kod dostępu urządzenia zarejestrowanego w usłudze Intune, możesz zresetować go przy użyciu [witryny sieci Web Portal firmy](http://portal.manage.microsoft.com). Witryna sieci Web Portal firmy może umożliwiać zarządzanie komputerami i urządzeniami zarejestrowanymi w usłudze Intune oraz wykonywanie większości zadań, które można wykonać przy użyciu aplikacji Portal firmy.

> [!NOTE]
> Przycisk **Resetuj kod dostępu** w witrynie sieci Web Portal firmy jest wyświetlany w zależności od tego, jak administrator IT skonfigurował usługę Intune. Resetowanie kodu dostępu nie jest obsługiwane na urządzeniach z systemem Windows 8.1.

Aby zresetować kod dostępu:

1.  Otwórz [witrynę sieci Web Portal firmy](http://portal.manage.microsoft.com) i wybierz urządzenie, którego kod dostępu chcesz zresetować.

2.  Wybierz polecenie **Resetuj kod dostępu**.

    ![Szczegóły urządzenia wraz z przyciskiem Resetuj kod dostępu](./media/iwp-screen-with-all-options.png)

3.  Wybierz pozycję **Wyloguj**, a następnie zaloguj się ponownie przy użyciu poświadczeń służbowych. Musisz zalogować się ponownie w ciągu pięciu minut.

    ![Wiadomość dotycząca resetowania z przyciskiem Wyloguj](./media/iwp-2-sign-out.png)

4.  Wybierz polecenie **Resetuj kod dostępu**.

    ![Komunikat wyjaśniający, co się dzieje, gdy kodu dostępu zostaje zresetowany](./media/iwp-3-tap-reset-passcode-after-signin.png)

    Sprawdź w tabeli, jak funkcja **resetowania kodu dostępu** działa na Twoim urządzeniu.

    |Platforma|Support|
    |------------|-----------|
    |Android|Utworzenie tymczasowego, alfanumerycznego kodu dostępu.|
    |iOS|Usunięcie kodu dostępu z urządzenia bez utworzenia tymczasowego kodu dostępu. Jeśli używasz funkcji Touch ID, musisz skonfigurować ją ponownie dla urządzenia, ponieważ jest ona usuwana podczas resetowania kodu dostępu.|
    |Windows 10 (tylko urządzenia przenośne)|Utworzenie tymczasowego, alfanumerycznego kodu dostępu. Funkcja Windows Hello jest obsługiwana.|
    |Windows Phone 8.1|Utworzenie tymczasowego, numerycznego kodu dostępu.|
    Po odblokowaniu urządzenia można ustawić nowy kod dostępu, przechodząc do pozycji **Ustawienia** na urządzeniu.

5.  Odblokuj urządzenie, a następnie ustaw nowy kod dostępu lub zmień tymczasowy kod dostępu, przechodząc do pozycji **Ustawienia** na urządzeniu.

    Aby wyświetlić powiadomienie potwierdzające pomyślne zresetowanie hasła, kliknij flagę powiadomienia u góry po prawej stronie w witrynie sieci Web Portal firmy.

Nadal potrzebujesz pomocy? Skontaktuj się z administratorem IT. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](http://portal.manage.microsoft.com).



<!--HONumber=Oct16_HO3-->


