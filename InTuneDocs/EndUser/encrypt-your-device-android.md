---
title: "Szyfrowanie urządzenia | Microsoft Intune"
description: "Opis sposobu szyfrowania urządzenia z systemem Android"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/7/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d4430e92-04cc-48e9-a77a-81b95a90b6b3
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 81c0c29e1b874a7f5c7faa1c1216dbaa99ec4543
ms.openlocfilehash: b8214506ae4609cb5316c66b854fbd572fbac94f


---


# <a name="encrypt-your-device"></a>Szyfrowanie urządzenia

Jeśli firma lub organizacja prosi o zaszyfrowanie urządzenia z systemem Android przed uzyskaniem dostępu do firmowych plików, poczty e-mail lub danych, wykonaj następujące kroki, aby zaszyfrować urządzenie. Może zostać wyświetlony monit o ustawienie numeru PIN lub hasła przed szyfrowaniem, jeśli administrator IT wymaga takiego zabezpieczenia.

Jeśli wyrejestrujesz telefon, pozostanie on zaszyfrowany.

1.  Upewnij się, że urządzenie wymaga numeru PIN lub hasła w celu odblokowania ekranu.

2.  W sekcji **Ustawienia** wybierz pozycję **Zabezpieczenia** &gt; **Zaszyfruj telefon**.
    Na niektórych telefonach należy kliknąć pozycję **Magazyn** &gt; **Szyfrowanie pamięci** lub **Magazyn** &gt; **Blokada ekranu i zabezpieczenia** &gt; **Inne ustawienia zabezpieczeń**, aby uzyskać dostęp do opcji „Szyfruj”.

3.  Wykonaj instrukcje wyświetlane na ekranie. Podczas szyfrowania urządzenie może być kilka razy ponownie uruchamiane.

### <a name="what-to-do-if-you-have-issues"></a>Co zrobić, jeśli masz problemy
**Problem**: urządzenie jest już zaszyfrowane i wystąpiła jedna z następujących sytuacji:

- Przycisk szyfrowania jest wyłączony.
- Został wyświetlony komunikat informujący o tym, że szyfrowanie jest w dalszym ciągu wymagane.
- Wystąpiły błędy podczas próby użycia aplikacji Portal firmy.

**Co należy zrobić**

- Upewnij się, że urządzenie jest naładowane i podłączone do zasilania.
- Upewnij się, że ustawiono numer PIN lub hasło na urządzeniu.
- Jeśli ustawiono już numer PIN lub hasło na urządzeniu, spróbuj wykonać następujące kroki, których administrator IT może wymagać, aby zwiększyć bezpieczeństwo urządzenia. Wyświetlane nazwy menu mogą być nieco inne niż podane w poniższych krokach, w zależności od typu urządzenia z systemem Android.

    1. Przejdź do pozycji **Ustawienia** > **Zabezpieczenia** > **Blokada ekranu**. Potwierdź swój bieżący numer PIN lub hasło.

    2. Na ekranie **wyboru blokady ekranu** wybierz typ blokady ekranu, której chcesz użyć.

    3. Na ekranie **bezpiecznego uruchamiania** naciśnij pozycję **Wymagaj numeru PIN do uruchomienia urządzenia** i naciśnij przycisk **Kontynuuj**.

    4. Wybierz numer PIN (możesz wprowadzić ten sam, co wprowadzony wcześniej), a następnie naciśnij przycisk **Potwierdź numer PIN**.

    5. Otwórz aplikację Portal firmy, wybierz swoje urządzenie i naciśnij pozycję **Sprawdź zgodność**.

Nadal potrzebujesz pomocy? Skontaktuj się z administratorem IT (sprawdź [witrynę sieci Web Portal firmy](http://portal.manage.microsoft.com), aby uzyskać informacje kontaktowe) lub napisz do [zespołu ds. systemu Android firmy Microsoft](mailto:wintunedroidfbk@microsoft.com).



<!--HONumber=Nov16_HO2-->


