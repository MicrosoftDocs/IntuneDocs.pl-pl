---
title: "Jak zresetować kod dostępu z poziomu witryny sieci Web Portal firmy | Dokumentacja firmy Microsoft"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
searchScope: User help
ROBOTS: 
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: ae85e523a2c5b87e172a2bfc01254f87093c71b1
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-reset-your-device-passcode-from-the-company-portal-website"></a>Jak zresetować kod dostępu urządzenia z poziomu witryny sieci Web Portal firmy

Jeśli utracisz numer PIN lub kod dostępu urządzenia zarejestrowanego w usłudze Intune, możesz zresetować go przy użyciu [witryny sieci Web Portal firmy](http://portal.manage.microsoft.com). Witryna sieci Web Portal firmy może umożliwiać zarządzanie komputerami i urządzeniami zarejestrowanymi w usłudze Intune oraz wykonywanie większości zadań, które można wykonać przy użyciu aplikacji Portal firmy.

> [!NOTE]
> W przypadku korzystania z zarejestrowanego urządzenia firmowego istnieje możliwość, że przycisk Resetuj kod dostępu nie będzie widoczny w witrynie internetowej Portal firmy. W takim przypadku należy skontaktować się z administratorem IT w celu uzyskania kodu dostępu.

Aby zresetować kod dostępu:

1.  W [witrynie sieci Web Portal firmy](http://portal.manage.microsoft.com) naciśnij przycisk __menu__ ![Mały obrazek przycisku menu, trzy poziome paski ułożone równolegle do siebie.](/intune/media/CP_hamburger_menu.png), a następnie wybierz pozycję __Moje urządzenia__.

2. Na stronie __Moje urządzenia__ wybierz nazwę urządzenia, którego kod dostępu chcesz zresetować.

  ![Zrzut ekranu strony Moje urządzenia przedstawiający kilka niezidentyfikowanych urządzeń oraz znajdujący się poniżej transparent z monitem o zarejestrowanie urządzeń nieznajdujących się na liście lub zidentyfikowanie tych niezidentyfikowanych.](./media/macOS_enroll_002_tap_here_banner.png)

3.  Urządzenie wyświetli się w oknie podręcznym. Naciśnij przycisk **Resetuj kod dostępu**.

    ![Wszystkie opcje dla wybranego urządzenia w witrynie sieci Web Portal firmy, w tym Zmień nazwę, Usuń, Resetuj urządzenie, Resetuj kod dostępu i Zdalne blokowanie. ](./media/iwp-screen-with-all-options.png)

4.  Zostanie wyświetlony transparent z prośbą o potwierdzenie zresetowania kodu dostępu i informacją o wylogowaniu urządzenia po wykonaniu tej czynności. Aby zalogować się ponownie, konieczne będzie odczekanie 5 minut.

  ![Transparent z ostrzeżeniem dotyczącym resetowania kodu dostępu urządzenia i wylogowania użytkownika. Przyciskami aktywności użytkownika są Wyloguj i Anuluj.](./media/iwp-reset-passcode-popup.png)

5.  Po wybraniu polecenia **Wyloguj** wyświetli się jeden komunikat końcowy informujący o usunięciu kodu dostępu z urządzenia. Jeśli nie masz urządzenia przy sobie, nie usuwaj kodu dostępu, ponieważ osoba mająca fizyczny dostęp do urządzenia będzie mogła uzyskać wgląd w większość zawartych na nim informacji — osobistych lub firmowych. 

  ![Drugi transparent z ostrzeżeniem dotyczącym resetowania kodu dostępu urządzenia i jego usunięcia z urządzenia. Informuje również, że aby ustawić nowy kod dostępu, należy przejść do ustawień urządzenia.](./media/iwp-reset-passcode-2nd-popup.png)

  Różne urządzenia mają różne typy kodów dostępu.

  **Android**: usuwa istniejący kodu dostępu i tworzy tymczasowy kod dostępu składający się z liter i cyfr. 
  
  > [!NOTE]
  > Nie można zresetować kodu dostępu w przypadku urządzeń z systemem Android 7.0 lub nowszym. Jeśli zapomnisz, jaki jest kod dostępu, musisz zresetować te urządzenia, przywracając ich ustawienia fabryczne.

  **iOS**: usuwa istniejący kod dostępu i nie tworzy tymczasowego kodu dostępu. Jeśli do otwierania urządzenia lub dokonywania zakupów używasz czytnika linii papilarnych Touch ID, musisz ponownie go skonfigurować.

  **Windows 10 Mobile**: usuwa istniejący kod dostępu i tworzy tymczasowy kod dostępu składający się z liter i cyfr. Jeśli podczas logowania używasz funkcji rozpoznawania twarzy Windows Hello, funkcja ta w dalszym ciągu będzie obsługiwana.
    
  **Windows Phone 8.1**: usuwa istniejący kod dostępu i powoduje utworzenie tymczasowego kodu dostępu składającego się z cyfr.

  W przypadku urządzeń z systemem Android i Windows hasło tymczasowe zostanie wyświetlone w polu **Szczegóły urządzenia**. 

6.  Odblokuj urządzenie, a następnie ustaw nowy kod dostępu lub zmień tymczasowy kod dostępu, przechodząc w urządzeniu do menu **Ustawienia**.

Aby wyświetlić powiadomienie potwierdzające pomyślne zresetowanie hasła, kliknij flagę powiadomienia u góry po prawej stronie w witrynie sieci Web Portal firmy.

Nadal potrzebujesz pomocy? Skontaktuj się z administratorem IT. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](http://portal.manage.microsoft.com).
