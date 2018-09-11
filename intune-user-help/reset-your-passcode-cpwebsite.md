---
title: Jak zresetować kod dostępu z poziomu witryny sieci Web Portal firmy | Dokumentacja firmy Microsoft
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 8ce71a14f9bb7e877fb31e78afdf64d5e492f4a8
ms.sourcegitcommit: 490365fb8b5405f323b4358fb1ec9dfdd9ff2d58
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/29/2018
ms.locfileid: "43146693"
---
# <a name="how-to-reset-your-device-passcode-from-the-company-portal-website"></a>Jak zresetować kod dostępu urządzenia z poziomu witryny sieci Web Portal firmy

Jeśli utracisz numer PIN lub hasło, możesz zresetować je przy użyciu [witryny internetowej Portal firmy](https://portal.manage.microsoft.com).  

Jeśli używasz urządzenia zarejestrowanego przez firmę, możesz nie widzieć opcji umożliwiającej zresetowanie kodu dostępu do urządzenia. Skontaktuj się z działem pomocy technicznej Twojej firmy w celu uzyskania kodu dostępu.

   > [!NOTE]
   > Nie można zresetować kodu dostępu w przypadku urządzeń z systemem Android 7.0 lub nowszym. Jeśli zapomnisz, jaki jest kod dostępu, musisz zresetować urządzenie, przywracając ustawienia fabryczne. 

## <a name="reset-your-passcode"></a>Resetowanie kodu dostępu

1.  Otwórz [witrynę internetową Portal firmy](https://portal.manage.microsoft.com), wybierz przycisk __Menu__, a następnie wybierz pozycję __Urządzenia__.  

2. Wybierz urządzenie, które wymaga zresetowania kodu dostępu.  

    ![Zrzut ekranu przedstawiający stronę Urządzenia z dwoma kafelkami, które przedstawiają niezidentyfikowane urządzenia z ogólną nazwą. Bezpośrednio pod urządzeniami wyświetlany jest szary baner zawierający monit dla użytkownika z prośbą o identyfikację używanego urządzenia lub dodanie nowego.](./media/rename-reset-device-step2-1808.png) 

3. Wybierz pozycję **Zresetuj kod dostępu**. Jeśli opcja resetowania kodu dostępu nie jest widoczna w górnej części strony, wybierz opcję **Więcej (...)** > **Zresetuj kod dostępu**.   

   ![Strona szczegółów urządzenia dla wybranego urządzenia w witrynie Portal firmy, z listą linków w górnej części z opcjami Zmień nazwę, Usuń, Resetuj urządzenie, Resetuj kod dostępu oraz Zdalne blokowanie. ](./media/rename-reset-device-1808.png)   

    ![Powiększony widok ikony Więcej wyróżnionej czerwoną strzałką.](./media/rename-reset-device-step3-more-1808.png)  

4. Po wyświetleniu monitu kliknij przycisk **Wyloguj się**. Po wyświetleniu monitu zaloguj się ponownie. Musisz zalogować się ponownie w witrynie internetowej Portal firmy w ciągu pięciu minut; w przeciwnym wypadku aplikacja Portal firmy nie zresetuje kodu dostępu urządzenia.  

   > [!NOTE]
   > Musisz zalogować się ponownie, aby potwierdzić swoją tożsamość. Ma to na celu zapobieganie złośliwym próbom zresetowania kodu dostępu urządzenia.

   ![Przykładowe zrzuty ekranu przedstawiające monit o wylogowanie się z witryny Portal firmy. Przyciskami aktywności użytkownika są Wyloguj i Anuluj.](./media/iwp-reset-passcode-popup-1808.png)

5. Pojawi się komunikat z ostrzeżeniem o usunięciu istniejącego kodu dostępu urządzenia. Kliknij przycisk **Zresetuj kod dostępu**, aby potwierdzić.  
    > [!WARNING]
    > Po zresetowaniu kodu dostępu każda osoba, która ma fizyczny dostęp do urządzenia, będzie w stanie uzyskać dostęp do większości informacji osobistych i firmowych na urządzeniu. Jeśli nie masz urządzenia przy sobie, nie resetuj kodu dostępu.  

   ![Zrzut ekranu przedstawiający drugi komunikat o resetowaniu kodu dostępu. Zawiera link prowadzący do dodatkowych informacji o ustawianiu nowego kodu dostępu w dokumentacji, a także poszczególne przyciski umożliwiające zresetowanie kodu dostępu lub anulowanie operacji.](./media/iwp-reset-passcode-popup2-1808.png) 

6. Jeśli resetujesz kod dostępu dla urządzenia z systemem iOS, istniejący kod dostępu zostanie usunięty. W przypadku urządzeń z systemem Windows lub Android otrzymasz tymczasowy kod dostępu umożliwiający odblokowanie urządzenia i ustawienie nowego kodu dostępu. 

   > [!NOTE]
   > Hasło tymczasowe dla urządzeń z systemem Windows lub Android możesz znaleźć w witrynie Portal firmy, na stronie szczegółów urządzenia. Zobacz sekcję [Konfigurowanie nowego kodu dostępu](reset-your-passcode-cpwebsite.md#set-up-a-new-passcode), aby uzyskać więcej opisów kodów dostępu właściwych dla danego systemu operacyjnego.  
   
7. Na urządzeniu przejdź do sekcji **Ustawienia** i zmień tymczasowy kod dostępu. 

8. W prawym górnym rogu witryny internetowej Portal firmy pojawi się flaga. Kliknij, aby odczytać powiadomienie i potwierdzić pomyślne zresetowanie kodu dostępu.  

## <a name="set-up-a-new-passcode"></a>Konfigurowanie nowego kodu dostępu  

W tej sekcji opisano resetowanie kodu dostępu oraz zachowanie związane z hasłem tymczasowym dla każdej platformy urządzeń.  

**Android**: usuwa istniejący kodu dostępu i tworzy tymczasowy kod dostępu składający się z liter i cyfr.

**iOS**: usuwa istniejący kod dostępu i nie tworzy tymczasowego kodu dostępu. Jeśli używasz czytnika linii papilarnych Touch ID do otwierania urządzenia lub dokonywania zakupów, musisz ponownie go skonfigurować.  

**Windows 10 Mobile**: usuwa istniejący kod dostępu i tworzy tymczasowy kod dostępu składający się z liter i cyfr. Po skonfigurowaniu rozpoznawanie twarzy Windows Hello nadal będzie działać na urządzeniu.
    
**Windows Phone 8.1**: usuwa istniejący kod dostępu i powoduje utworzenie tymczasowego kodu dostępu składającego się z cyfr.  

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).  
