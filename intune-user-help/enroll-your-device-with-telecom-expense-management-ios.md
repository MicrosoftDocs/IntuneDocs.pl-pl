---
title: Rejestrowanie urządzenia z systemem iOS w rozwiązaniu do zarządzania wydatkami telekomunikacyjnymi za pomocą usługi Intune
description: Dowiedz się, jak zarejestrować urządzenie z systemem iOS w rozwiązaniu do zarządzania wydatkami telekomunikacyjnymi.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6d8c6372-f2ce-4558-8886-1d7c1966699c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: sumitp
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: ff51405ee48851b5a48c4d6142c33bc16ed6218e
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31031808"
---
# <a name="enroll-your-ios-device-in-telecom-expense-management"></a>Rejestrowanie urządzenia z systemem iOS w rozwiązaniu do zarządzania wydatkami telekomunikacyjnymi

Organizacja może używać oprogramowania do zarządzania wydatkami telekomunikacyjnymi, aby mieć pewność, że jej dane i plany taryfowe obejmujące usługi połączeń głosowych są wykorzystywane we właściwy sposób. Po zakończeniu rejestracji urządzenia otrzymasz monit o wybranie najlepszej kategorii dla danego urządzenia.

  ![Zrzut ekranu „wybór najlepszej kategorii dla urządzenia” na urządzeniu z systemem iOS. Na zrzucie widoczna jest opcja wyboru rejestracji firmowej lub osobistej.](./media/ios-enroll-10-tem-select-best-category.png)

Po wybraniu odpowiedniej opcji otrzymasz powiadomienie z informacją o konieczności instalacji aplikacji [__Datalert__](https://itunes.apple.com/app/datalert/id771029268?mt=8) ze sklepu App Store. Aplikacja Datalert pozwala organizacji dokonywać pomiaru stopnia wykorzystania danych. Jeśli dla organizacji została skonfigurowana opcja rejestracji urządzeń z kontami służbowymi firmy Microsoft, konieczne będzie zalogowanie się przy użyciu danych konta służbowego. Jeśli opcja ta nie została włączona, w celu zarejestrowania w usłudze Datalert konieczne będzie podanie informacji takich jak numer telefonu oraz zweryfikowanie urządzenia przy użyciu kodu uzyskanego z aplikacji.

  ![Zrzut ekranu przedstawiający ekran powitalny aplikacji Datalert, z którego można przejść do następnego ekranu po wpisaniu krótkiego sposobu, w jaki aplikacja Datalert może pomóc organizacji optymalnie wykorzystać plan taryfowy obejmujący usługi transmisji danych.](./media/ios-enroll-11-tem-datalert-setup.png)

## <a name="enroll-into-datalert-using-your-microsoft-work-or-school-account"></a>Rejestrowanie w usłudze Datalert przy użyciu służbowego konta Microsoft

> [!NOTE]
> Aby zarejestrować urządzenie w ten sposób, musisz mieć w swoim telefonie zainstalowaną i aktywną aplikację [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to).

1. Wybierz pozycję __Enroll with Microsoft account__ (Rejestracja za pomocą konta Microsoft).

   ![Zrzut ekranu ustawień aplikacji Datalert dla użytkowników posiadających konto w usłudze Microsoft Office 365 i subskrypcję usługi Intune: u góry pole numeru telefonu pozwalające zarejestrować urządzenie, u dołu opcja rejestracji przy użyciu konta Microsoft.](./media/ios-enroll-11a-tem-datalert-enroll-msft-account.png)

2. Otrzymasz powiadomienie, że aplikacja __„Datalert” chce otworzyć aplikację „Authenticator”__. Wybierz pozycję __Open__ (Otwórz).

   ![Zrzut ekranu przedstawiający wyskakujące okienko z monitem o otwarcie aplikacji Authenticator na żądanie aplikacji Datalert.](./media/ios-enroll-11b-tem-datalert-open-authenticator.png)

3. Zaloguj się przy użyciu __służbowego konta Microsoft__. Poczekaj chwilę na zakończenie konfigurowania usługi Datalert. Gdy proces się zakończy się, wybierz opcję __Finish__ (Zakończ).

## <a name="enroll-into-datalert-using-your-phone-number"></a>Rejestrowanie w usłudze Datalert przy użyciu numeru telefonu

1. Podaj numer telefonu urządzenia.

   ![Zrzut ekranu aplikacji Datalert z żądaniem podania numeru telefonu.](./media/ios-enroll-12-tem-datalert-phone-number.png)

2. Następnie otrzymasz kod weryfikacyjny za pośrednictwem wiadomości SMS. Wpisz kod i naciśnij przycisk __OK__.

   ![Zrzut ekranu aplikacji Datalert z żądaniem wpisania kodu weryfikacyjnego z wiadomości SMS.](./media/ios-enroll-13-tem-datalert-sms.png)

3. Wpisanie kodu weryfikacyjnego stanowi zakończenie procesu instalacji aplikacji Datalert. Po wybraniu opcji __Zakończ__ możesz monitorować użycie danych w aplikacji Datalert.

   ![Zrzut ekranu przedstawiający proces monitorowania dziennego użycia danych w aplikacji Datalert.](./media/ios-enroll-14-tem-datalert-monitoring-active.png)

Po zakończeniu rejestracji zobaczysz swoje użycie danych w aplikacji Datalert.

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://portal.manage.microsoft.com#HelpDeskDialog).
