---
title: "Rejestrowanie urządzenia z systemem macOS w usłudze Intune za pomocą aplikacji Portal firmy | Microsoft Docs"
description: "Opis sposobu rejestrowania urządzenia z systemem macOS w usłudze Intune za pomocą aplikacji Portal firmy"
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3bb659cc-9b57-4d19-8631-2c26749fa71c
searchScope: User help
ROBOTS: 
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 1559692de1a8c9c356a3f5b30e80d1abd31853d2
ms.sourcegitcommit: f2f147a1177d1cf5bbc8001701eb8f44dd833b7d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/12/2017
---
# <a name="enroll-your-macos-device-in-intune-with-the-company-portal-app"></a>Rejestrowanie urządzenia z systemem macOS w usłudze Intune przy użyciu aplikacji Portal firmy

Uzyskiwanie dostępu do aplikacji, danych i zasobów organizacji ułatwia wykonywanie pracy. Twoja organizacja używa usługi Intune do [zarządzania dostępem do tych zasobów](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-macos.md), co wymaga pobrania aplikacji Portal firmy dla systemu macOS. Te instrukcje będą działać w przypadku urządzeń z systemem macOS w wersji OS X El Capitan 10.11 i nowszych.

> [!NOTE]
> Instrukcje dotyczące rejestrowania urządzeń z systemem macOS dla wcześniejszych wersji systemu macOS można znaleźć [tutaj](enroll-your-device-in-intune-macos-legacy.md).

1. Na __Docku__ znajdź pozycję __Safari__ i otwórz nowe okno, a następnie otwórz [witrynę aplikacji Portal firmy](https://portal.manage.microsoft.com#HelpDeskDialog).

2. Zaloguj się do witryny aplikacji Portal firmy przy użyciu konta służbowego.

[!INCLUDE[wit_nextref](includes/end-user-password-guidance.md)]

3. Po zalogowaniu się kliknij pozycję **Menu** w lewym górnym rogu strony i wybierz pozycję **Moje urządzenia**.

   ![Zrzut ekranu strony początkowej portalu sieci Web z informacją, że nie można jeszcze zainstalować żadnych aplikacji, oraz przyciskiem Moje urządzenia poniżej.](./media/macOS_enroll_001_landing_page.png)

4. Na stronie __Moje urządzenia__ zostanie wyświetlona lista zarejestrowanych urządzeń lub transparent. Jest to zależne od tego, czy masz już zarejestrowane urządzenia z systemem macOS lub inne. Aby zarejestrować urządzenie, którego nie ma na liście, wybierz transparent z informacją __Jeśli urządzenie jest na liście, naciśnij tutaj, aby je zidentyfikować. Możesz również nacisnąć tutaj, aby zarejestrować urządzenie, jeśli nie ma go na liście__. Jeśli nie masz żadnych zarejestrowanych urządzeń, na banerze będzie wyświetlany komunikat **Nie masz żadnych zarejestrowanych urządzeń. Zarejestruj urządzenie, naciskając tutaj.**

    ![Zrzut ekranu strony Moje urządzenia przedstawiający kilka niezidentyfikowanych urządzeń oraz znajdujący się poniżej transparent z monitem o zarejestrowanie urządzeń nieznajdujących się na liście lub zidentyfikowanie tych niezidentyfikowanych.](./media/macOS_enroll_002_tap_here_banner.png)

5. Pobierz aplikację Portal firmy na urządzenie z systemem macOS, aby kontynuować rejestrowanie.

    ![Komunikat monitujący użytkownika o pobranie aplikacji aplikację Portal firmy dla systemu macOS. Ten komunikat wyświetla tekst podany w kroku powyżej przycisku „Pobierz” w prawym dolnym rogu.](./media/macOS_enroll_IWP_CP_app_notice.png)

6. Komputer Mac sprawdzi, czy pobrany plik **CompanyPortal.pkg** można bezpiecznie otworzyć. Otwórz instalator i przejdź przez proces instalacji.

7. Po zakończeniu działania instalatora otwórz folder **Aplikacje** lub **Launchpad**, a następnie otwórz aplikację **Portal firmy**.

8. Komputer Mac wyświetli komunikat **„CompanyPortal” to aplikacja pobrana z Internetu. Czy na pewno chcesz ją otworzyć?** Kliknij przycisk **Otwórz**.

  > [!NOTE]
  > Usługa Intune musi mieć dostęp do komputera, aby sprawdzić, czy urządzenie jest wystarczająco bezpieczne, aby mogło uzyskiwać dostęp do zasobów organizacji. Jeśli Twój komputer odmawia otwarcia aplikacji Portal firmy, spróbuj [wyłączyć funkcję Gatekeeper](https://support.apple.com/HT202491) i wtedy otworzyć aplikację.

9. Pierwszy ekran wyświetlony w aplikacji Portal firmy poprosi Cię o **zalogowanie się** za pomocą tego samego konta służbowego, które zostało użyte do zalogowania się do witryny internetowej Portal firmy.

10. Portal firmy potwierdzi informacje o Twoim koncie, a następnie wyświetli stan **rejestracji urządzenia** i **zgodności urządzenia**. Żółte trójkąty będą informować o akcjach, które trzeba wykonać, aby zagwarantować, że komputera Mac można bezpiecznie używać do pracy. Kliknij przycisk **Rozpocznij**, aby zacząć [rejestrowanie urządzenia w systemie zarządzania](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).

11. Komputer Mac zacznie rejestrację w systemie zarządzania. Może wtedy zostać wyświetlony monit o podanie informacji logowania na komputerze. Rejestracja może zająć kilka minut. W tym czasie można robić inne rzeczy na komputerze. Gdy konfigurowanie dostępu do zasobów firmy zostanie zakończone, pojawi się odpowiedni komunikat.

Nadal potrzebujesz pomocy? Skontaktuj się z działem pomocy technicznej Twojej firmy. Odpowiednie informacje kontaktowe możesz znaleźć w [witrynie aplikacji Portal firmy](https://portal.manage.microsoft.com#HelpDeskDialog).
