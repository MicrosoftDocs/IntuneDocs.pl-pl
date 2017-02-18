---
title: "Jak zresetować kod dostępu z poziomu witryny sieci Web Portal firmy | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
searchScope:
- Company Portal
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: a87fe0cf9591040f1455d71b1f40cd0705ba8abf
ms.openlocfilehash: a8ce59755a74199eda6865feda68c0613d10c2a7


---

# <a name="how-to-reset-your-device-passcode-from-the-company-portal-website"></a>Jak zresetować kod dostępu urządzenia z poziomu witryny sieci Web Portal firmy

Jeśli utracisz numer PIN lub kod dostępu urządzenia zarejestrowanego w usłudze Intune, możesz zresetować go przy użyciu [witryny sieci Web Portal firmy](http://portal.manage.microsoft.com). Witryna sieci Web Portal firmy może umożliwiać zarządzanie komputerami i urządzeniami zarejestrowanymi w usłudze Intune oraz wykonywanie większości zadań, które można wykonać przy użyciu aplikacji Portal firmy.

> [!NOTE]
> Istnieje możliwość, że przycisk **Resetuj kod dostępu** nie będzie widoczny w witrynie sieci Web Portal firmy. W takim przypadku należy skontaktować się za pośrednictwem witryny sieci Web Portal firmy z administratorem IT w celu uzyskania pomocy.

Aby zresetować kod dostępu:

1.  Otwórz [witrynę sieci Web Portal firmy](http://portal.manage.microsoft.com) i wybierz urządzenie, którego kod dostępu chcesz zresetować.

2.  Wybierz polecenie **Resetuj kod dostępu**.

    ![Szczegóły urządzenia wraz z przyciskiem Resetuj kod dostępu](./media/iwp-screen-with-all-options.png)

3.  Wybierz pozycję **Wyloguj**, a następnie zaloguj się ponownie przy użyciu poświadczeń służbowych. Musisz zalogować się ponownie w ciągu pięciu minut.

    ![Wiadomość dotycząca resetowania z przyciskiem Wyloguj](./media/iwp-2-sign-out.png)

4.  Wybierz polecenie **Resetuj kod dostępu**.

    ![Komunikat wyjaśniający, co się dzieje, gdy kodu dostępu zostaje zresetowany](./media/iwp-3-tap-reset-passcode-after-signin.png)

    Sprawdź w tabeli, jak funkcja **resetowania kodu dostępu** działa na Twoim urządzeniu.

    |Typ urządzenia|Co dzieje się po zresetowaniu|
    |------------|-----------|
    |Android|Usunięcie istniejącego kodu dostępu i utworzenie tymczasowego kodu dostępu składającego się z liter i cyfr.|
    |iOS|Usunięcie istniejącego kodu dostępu bez utworzenia tymczasowego kodu dostępu. Jeśli do otwierania urządzenia lub dokonywania zakupów używasz czytnika linii papilarnych Touch ID, musisz ponownie go skonfigurować.|
    |Windows 10 Mobile|Usunięcie istniejącego kodu dostępu i utworzenie tymczasowego kodu dostępu składającego się z liter i cyfr. Jeśli podczas logowania się używasz rozpoznawania twarzy przez funkcję Windows Hello, to funkcja ta w dalszym ciągu będzie obsługiwana.|
    |Windows Phone 8.1|Usunięcie istniejącego kodu dostępu i utworzenie tymczasowego kodu dostępu składającego się z cyfr.|

    5.  Odblokuj urządzenie, a następnie ustaw nowy kod dostępu lub zmień tymczasowy kod dostępu, przechodząc w urządzeniu do menu **Ustawienia**.

    Aby wyświetlić powiadomienie potwierdzające pomyślne zresetowanie hasła, kliknij flagę powiadomienia u góry po prawej stronie w witrynie sieci Web Portal firmy.

Nadal potrzebujesz pomocy? Skontaktuj się z administratorem IT. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](http://portal.manage.microsoft.com).



<!--HONumber=Jan17_HO4-->


