---
title: Jak zapewnić ochronę urządzenia z systemem Android za pomocą szyfrowania | Microsoft Docs
description: Ochrona urządzenia z systemem Android
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 11/14/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d4430e92-04cc-48e9-a77a-81b95a90b6b3
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: cea43f2bf3b13bf0463e1dedd6c20a1587336d5b
ms.sourcegitcommit: 7f46e9990797bdfa669ccba2077721f1bc70c07e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/04/2018
ms.locfileid: "30754998"
---
# <a name="how-to-protect-your-android-device-using-encryption"></a>Jak zapewnić ochronę urządzenia z systemem Android za pomocą szyfrowania

Zaszyfrowanie urządzenia polega na opakowaniu zawartych na nim informacji w warstwie kodu ochronnego, który uniemożliwia dostęp do niego przez osoby bez autoryzacji. W ramach zabezpieczania informacji użytkowników organizacja wymaga szyfrowania urządzenia z systemem Android w celu uzyskania dostępu do firmowych plików, poczty e-mail lub danych.

> [!Note]
> Niektóre urządzenia z systemem Android, w tym niektóre urządzenia Huawei oraz urządzenia Vivo i OPPO, nie mogą być szyfrowane. Dowiedz się więcej [tutaj](your-device-appears-encrypted-but-cp-says-otherwise-android.md).

Jeśli wyrejestrujesz telefon, pozostanie on zaszyfrowany.

1.  Upewnij się, że urządzenie wymaga numeru PIN lub hasła w celu odblokowania ekranu.

2.  W sekcji **Ustawienia** wybierz kolejno pozycje **Zabezpieczenia** > **Zaszyfruj urządzenie**.
    (W niektórych telefonach należy kliknąć pozycję **Pamięć** > **Szyfrowanie pamięci** lub **Pamięć** > **Blokada ekranu i zabezpieczenia** > **Inne ustawienia zabezpieczeń**, aby uzyskać dostęp do opcji „Szyfruj”).

3.  Wykonaj instrukcje wyświetlane na ekranie. Podczas szyfrowania urządzenie może być kilka razy ponownie uruchamiane.

### <a name="what-to-do-if-you-have-issues"></a>Co zrobić, jeśli masz problemy
**Problem**: urządzenie jest już zaszyfrowane i wystąpiła jedna z następujących sytuacji:

- Przycisk szyfrowania jest wyłączony.
- Został wyświetlony komunikat informujący o tym, że szyfrowanie jest w dalszym ciągu wymagane.
- Wystąpiły błędy podczas próby użycia aplikacji Portal firmy.

**Co należy zrobić**

- Upewnij się, że urządzenie jest naładowane i podłączone do zasilania.
- Upewnij się, że ustawiono numer PIN lub hasło na urządzeniu.
- Jeśli ustawiono już numer PIN lub hasło na urządzeniu, spróbuj wykonać następujące kroki, których dział pomocy technicznej Twojej firmy może wymagać, aby zwiększyć bezpieczeństwo urządzenia. Wyświetlane nazwy menu mogą być nieco inne niż podane w poniższych krokach, w zależności od typu urządzenia z systemem Android.

    1. Przejdź kolejno do pozycji **Ustawienia** > **Ekran blokady i zabezpieczenia** > **Blokada ekranu**. Potwierdź swój bieżący numer PIN lub hasło.

    2. Na ekranie **wyboru blokady ekranu** wybierz typ blokady ekranu, której chcesz użyć. 

    3. Po wybraniu blokady ekranu wróć do ekranu **Ekran blokady i zabezpieczenia** i wybierz pozycję opcję **bezpiecznego uruchamiania**. 
    
    4. Na ekranie **bezpiecznego uruchamiania** naciśnij pozycję **Wymagaj numeru PIN do uruchomienia urządzenia** i naciśnij przycisk **Kontynuuj**.

    5. Wybierz numer PIN (możesz wprowadzić ten sam, co wprowadzony wcześniej), a następnie naciśnij przycisk **Potwierdź numer PIN**.

    6. Otwórz aplikację Portal firmy, wybierz swoje urządzenie i naciśnij pozycję **Sprawdź zgodność**.

Nadal potrzebujesz pomocy? Skontaktuj się z działem pomocy technicznej Twojej firmy (sprawdź [witrynę internetową Portal firmy](https://portal.manage.microsoft.com#HelpDeskDialog), aby uzyskać informacje kontaktowe) lub napisz do <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with encryption on my Android device&body=Describe the issue you're experiencing here.">zespołu ds. systemu Android w firmie Microsoft</a>.
