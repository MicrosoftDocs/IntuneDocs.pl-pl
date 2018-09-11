---
title: Rejestrowanie urządzenia z systemem macOS w usłudze Intune za pomocą aplikacji Portal firmy | Microsoft Docs
description: Opis sposobu rejestrowania urządzenia z systemem macOS w usłudze Intune za pomocą aplikacji Portal firmy
keywords: Mac OS X, macOS, OS X
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3bb659cc-9b57-4d19-8631-2c26749fa71c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: af5c7492563c8df0168eff3250ae1bbad2cc323e
ms.sourcegitcommit: 490365fb8b5405f323b4358fb1ec9dfdd9ff2d58
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/29/2018
ms.locfileid: "43147721"
---
# <a name="enroll-your-macos-device-in-intune-with-the-company-portal-app"></a>Rejestrowanie urządzenia z systemem macOS w usłudze Intune przy użyciu aplikacji Portal firmy

Zarejestruj urządzenie z systemem macOS przy użyciu aplikacji Portal firmy w usłudze Intune, aby uzyskać bezpieczny dostęp do poczty e-mail, plików i aplikacji w organizacji.

Organizacje często wymagają przekazania urządzenia do zarządzania przed uzyskaniem dostępu do danych własnościowych. Po przekazaniu urządzenia do zarządzania organizacje mogą wypychać zasady i aplikacje do urządzenia za pośrednictwem dostawcy zarządzania urządzeniami przenośnymi. Aby uzyskać ciągły dostęp do danych służbowych z urządzenia, musisz skonfigurować urządzenie, aby dopasować je do ustawień zasad.  

W tym artykule opisano, jak aplikacja Portal firmy w usłudze Intune dla systemu macOS pomaga w rejestrowaniu, konfigurowaniu i utrzymywaniu urządzenia zgodnie z wymaganiami organizacji.

## <a name="what-to-expect-from-the-company-portal-app"></a>Czego można oczekiwać od aplikacji Portal firmy

Podczas początkowej konfiguracji aplikacja wymaga uwierzytelnienia użytkownika w organizacji. Następnie informuje użytkownika o wszelkich wymaganych ustawieniach urządzenia. Na przykład organizacje często ustawiają wymagania dotyczące minimalnej i maksymalnej długości haseł, które trzeba spełnić.    

Po zarejestrowaniu urządzenia aplikacja Portal firmy będzie nadal upewniać się, że urządzenie jest chronione. Jeśli przykładowo zainstalujesz aplikację z niezaufanego źródła, aplikacja będzie wysyłać alerty i czasami odwoływać dostęp do danych firmowych. Zasady ochrony aplikacji, takie jak powyższa, są typowe w organizacjach i często wymagają odinstalowania niezaufanych aplikacji przed odzyskaniem dostępu.

Jeśli po zarejestrowaniu organizacja wymusi nowe wymagania dotyczące zabezpieczeń, np. uwierzytelnianie wieloskładnikowe, aplikacja Portal firmy powiadomi użytkownika. Będziesz mieć szansę na dostosowanie ustawień, aby nadal kontynuować pracę z urządzenia.  

Aby uzyskać więcej informacji o rejestracji, zobacz [Co się stanie, jeśli zainstaluję aplikację Portal firmy i zarejestruję swoje urządzenie?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-macos.md).  

## <a name="get-your-device-managed"></a>Przekazywanie urządzenia do zarządzania  
Wykonaj poniższe kroki, aby zarejestrować urządzenia z systemem operacyjnym macOS w wersji X El Capitan 10.11 lub nowszym.   


1. Aby uzyskać dostęp do witryny internetowej Portal firmy, otwórz nowe okno w przeglądarce __Safari__ i przejdź do sekcji https://portal.manage.microsoft.com.  

2. Zaloguj się do witryny aplikacji Portal firmy przy użyciu konta służbowego.

   [!INCLUDE [wit_nextref](includes/end-user-password-guidance.md)]


3. Przejdź do lewego górnego rogu strony i kliknij opcję **Menu** > **Urządzenia**.  

4. Na stronie __Urządzenia__ zostanie wyświetlona lista zarządzanych urządzeń lub transparent. Wyświetlone elementy zależą od tego, czy masz już zarządzane urządzenie. 
    * Aby dodać urządzenie, którego nie ma na liście, wybierz transparent z tekstem **Naciśnij tutaj, aby poinformować nas o używanym urządzeniu lub dodać nowe urządzenie**.
    * Jeśli nie masz żadnych urządzeń, transparent wyświetla tekst: **Nie masz żadnych zarządzanych urządzeń. Dodaj urządzenie, naciskając tutaj.** Kliknij transparent, aby dodać urządzenie.  

     ![Zrzut ekranu przedstawiający stronę Urządzenia z czerwonym kwadratem wokół opcji transparentu wyróżniającym miejsce, w którym należy kliknąć.](./media/CP-enroll-MACOS-1808.png)  
5.  Wykonaj poniższy krok dopasowany do obecnie wyświetlanej wiadomości w aplikacji Portal firmy.  
    * Jeśli dodajesz urządzenie po raz pierwszy, zostanie wyświetlony monit o pobranie aplikacji Portal firmy na urządzenie. Kliknij przycisk **Pobierz**, aby kontynuować.  

         ![Zrzut ekranu przedstawiający monit o pobranie aplikacji Portal firmy dla systemu macOS. Użytkownik ma możliwość kliknięcia niebieskiego przycisku Pobierz w lewym dolnym rogu monitu lub szarego przycisku Anuluj w prawym dolnym rogu.](./media/CP-enroll-download-macOS-1808.png)  

    * Jeśli masz już urządzenie zarządzane z systemem macOS, otrzymasz monit z listą obecnie zarządzanych urządzeń z systemem macOS. Wybierz opcję **Mojego urządzenia nie ma na liście** > **Pobierz**, aby pobrać aplikację Portal firmy na dodawane urządzenie.  

         ![Zrzut ekranu przedstawiający monit o pobranie aplikacji Portal firmy dla systemu macOS. Użytkownik może wybrać opcję „Mojego urządzenia nie ma na liście” lub konkretne urządzenie w środkowej części strony. Niebieski przycisk Pobierz zostanie wyświetlony w lewym dolnym rogu monitu, a szary przycisk Anuluj w prawym dolnym rogu](./media/cp-mac-os-device-isnt-here-1808.png)  

6. Urządzenie sprawdzi, czy pobrany plik instalacyjny **CompanyPortal.pkg** można bezpiecznie otworzyć. Po zakończeniu otwórz instalatora i ukończ instalację.  

7. Jeśli instalator zakończył pracę, przejdź do aplikacji **Launchpad** i otwórz aplikację **Portal firmy**.  

8. Urządzenie z systemem macOS wyświetli monit o potwierdzenie otworzenia aplikacji Portal firmy. Kliknij pozycję **Otwórz**.  

   > [!TIP]
   > Usługa Intune musi mieć dostęp do komputera, aby sprawdzić, czy urządzenie jest wystarczająco bezpieczne, aby mogło uzyskiwać dostęp do zasobów organizacji. Jeśli Twój komputer odmawia otwarcia aplikacji Portal firmy, [wyłącz funkcję Gatekeeper](https://support.apple.com/HT202491). Następnie otwórz aplikację.

9. Pierwszy wyświetlony ekran w aplikacji Portal firmy zawiera monit o **zalogowanie**. Użyj tego samego konta służbowego, którego użyto do zalogowania się w witrynie internetowej Portal firmy.

10. Portal firmy potwierdzi informacje o Twoim koncie, a następnie wyświetli stan **rejestracji urządzenia** i **zgodności urządzenia**. Żółtymi trójkątami oznaczono akcje, które należy wykonać, aby zabezpieczyć urządzenie z systemem macOS na potrzeby zadań związanych ze szkołą lub pracą. Kliknij przycisk **Rozpocznij**, aby rozpocząć rejestrację. Dowiedz się, [jakie dane może wyświetlać Twoja organizacja](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md) podczas rejestrowania urządzenia.

11. Może zostać wyświetlony monit o podanie informacji logowania na komputerze. Rejestracja urządzenia w zarządzaniu może potrwać kilka minut. W tym czasie można robić inne rzeczy na urządzeniu. Gdy konfigurowanie dostępu do zasobów firmy zostanie zakończone, pojawi się odpowiedni komunikat.  

Nadal potrzebujesz pomocy? Skontaktuj się z działem pomocy technicznej Twojej firmy. Odpowiednie informacje kontaktowe możesz znaleźć w [witrynie aplikacji Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).  
