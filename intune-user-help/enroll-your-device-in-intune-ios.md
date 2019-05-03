---
title: Konfigurowanie urządzenia z systemem iOS do uzyskiwania dostępu do zasobów firmy | Microsoft Docs
description: Opisuje sposób udostępniania urządzenia z systemem iOS do zarządzania przez usługę Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/05/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: tisilv
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: d0c7ac239a67a51ba7165771206883f3c46f5f55
ms.sourcegitcommit: 364a7dbc7eaa414c7a9c39cf53eb4250e1ad3151
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59292428"
---
# <a name="set-up-ios-device-access-to-your-company-resources"></a>Konfigurowanie urządzenia z systemem iOS do uzyskiwania dostępu do zasobów firmy  

Zarejestruj urządzenie z systemem iOS przy użyciu aplikacji Portal firmy w usłudze Intune, aby uzyskać bezpieczny dostęp do poczty e-mail, plików i aplikacji w organizacji.

Po zarejestrowaniu urządzenia, staje się *zarządzane*. Twoja organizacja można przypisać zasady i aplikacje na urządzeniu za pośrednictwem dostawcy zarządzania (urządzeniami przenośnymi MDM) urządzeń przenośnych, takich jak usługi Intune.  

Aby utrzymywać dostęp do informacji służbowych z urządzenia, musisz skonfigurować urządzenie, aby dopasować je do preferowanych ustawień organizacji. W tym artykule opisano, jak za pomocą portalu firmy zarejestrować urządzenia i Obsługa wymagań ustawienie Twojej organizacji. 

> [!NOTE]
> Jeśli nastąpiła próba dostępu do firmowej poczty e-mail w aplikacji poczty, a następnie został wyświetlony monit o przekazanie urządzenia do zarządzania, jesteś w odpowiednim miejscu. Aby uzyskać dostęp do poczty e-mail i innych zasobów firmy na swoim urządzeniu z systemem iOS, postępuj zgodnie z poniższymi instrukcjami.  

## <a name="what-to-expect-from-the-company-portal-app"></a>Czego można oczekiwać od aplikacji Portal firmy  

### <a name="security"></a>Zabezpieczenia  
Podczas początkowej konfiguracji aplikacja wymaga uwierzytelnienia użytkownika w organizacji. Następnie informuje użytkownika o wszelkich wymaganych aktualizacjach ustawieniach urządzenia. Na przykład organizacje często ustawiają wymagania dotyczące minimalnej i maksymalnej długości haseł, które trzeba spełnić.     

### <a name="protection"></a>Protection  
Po zarejestrowaniu urządzenia aplikacja Portal firmy będzie nadal upewniać się, że urządzenie jest chronione. Jeśli przykładowo zainstalujesz aplikację z niezaufanego źródła, aplikacja będzie wysyłać alerty i czasami odwoływać dostęp do danych firmowych. Tego rodzaju zasady jest często używany w organizacji, a często, musisz odinstalować niezaufanych aplikację, zanim można go odzyskać.  

### <a name="setting-notifications"></a>Ustawianie powiadomień  
Jeśli po zarejestrowaniu organizacja wymusi nowe wymagania dotyczące zabezpieczeń, np. uwierzytelnianie wieloskładnikowe, aplikacja Portal firmy powiadomi użytkownika. Będziesz mieć szansę na dostosowanie ustawień, aby nadal kontynuować pracę z urządzenia.  

Aby uzyskać więcej informacji o rejestracji, zobacz [Co się stanie, jeśli zainstaluję aplikację Portal firmy i zarejestruję swoje urządzenie?](https://docs.microsoft.com//intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios).  

## <a name="enroll-your-ios-device"></a>Rejestrowanie urządzenia z systemem iOS  

Przejdź do sklepu App store, aby pobrać i zainstalować [aplikacji Portal firmy Intune](install-and-sign-in-to-the-intune-company-portal-app-ios.md) na urządzeniu. Należy również utrzymania połączenia Wi-Fi i mają dostęp do programu Safari podczas rejestracji. 

Wstrzymywanie przez okres dłuższy niż kilka minut, podczas rejestracji może spowodować, że aplikacja zamknąć lub zakończyć instalację. Jeśli tak się stanie, Otwórz aplikację Portal firmy i spróbuj ponownie.  

1. Otwórz aplikację Portal firmy i zaloguj się za pomocą konta służbowego. 

    ![Zrzut ekranu aplikacji Portal firmy i logowanie.](./media/ios-01-cp-enroll-1903.PNG)  

2. Po wyświetleniu monitu, aby otrzymywać powiadomienia z aplikacji Portal firmy, naciśnij **Zezwalaj.** Portal firmy używa powiadomienia do wyzwalania alertu, jeśli na przykład, należy zaktualizować ustawienia urządzenia. 

    ![Zrzut ekranu strony głównej portalu firmy, "Powiadomienia" w wierszu polecenia.](./media/ios-04-cp-enroll-1903.PNG)  

3. Na **Konfigurowanie dostępu** ekranu, wybierz opcję **rozpocząć.**  

     ![Zrzut ekranu aplikacji Portal firmy, ekran "Konfigurowanie dostępu".](./media/ios-05-cp-enroll-1903.PNG)  

4. Zapoznaj się z artykułem listy informacje o urządzeniach w organizacji może zobaczyć. Następnie wybierz przycisk **Kontynuuj**.  

5. Zapoznaj się z artykułem z instrukcjami wyświetlanymi na **co przyniesie przyszłość?** ekranu. Kiedy wszystko będzie gotowe do pobrania i zainstalowanie profilu zarządzania naciśnij pozycję **Kontynuuj**.  

 > [!IMPORTANT]
> Te czynności dalej i ekrany będą się różnić w zależności od używanej wersji systemu iOS. Postępuj zgodnie z instrukcjami dla używanej wersji systemu iOS. 

6. Safari powoduje otwarcie witryny internetowej Portal firmy na urządzeniu. Po wyświetleniu monitu, aby pobrać profil konfiguracji, naciśnij **Zezwalaj**. Jeśli na urządzeniu z systemem:  
    * System iOS 12.2 lub nowszy: po zakończeniu pobierania wybierz **gotowe.** Przejdź do kroku 7, w tym artykule.
    * System iOS 12.1 i wcześniejszych: nastąpi automatyczne przekierowanie do aplikacji ustawienia. Przejdź do kroku 8, w tym artykule.  
 
    Jeśli przypadkowo naciśnij **Ignoruj**, Odśwież stronę. Zostanie wyświetlony monit, aby otworzyć aplikację Portal firmy. Z poziomu aplikacji, możesz nacisnąć pozycję **ponownie pobrać**.

  > [!NOTE]
  > Należy zainstalować profil zarządzania, zgodnie z opisem w następnych krokach 8 minut ją pobrać. Jeśli nie istnieje profil, który zostanie usunięty i będzie trzeba ponownie uruchamiać rejestracji.  

7. iOS 12.2 i późniejsze: po wyświetleniu monitu, aby otworzyć Portal firmy, naciśnij **Otwórz**. **Instalowanie profilu zarządzania** ekranu przedstawiono kroki, aby zainstalować profil.

    ![Zrzut ekranu aplikacji Portal firmy, instalowanie profilu zarządzania ekranu.](./media/ios-1904-settings-icon.PNG)  

8. Przejdź do aplikacji ustawienia i naciśnij **pobrany profil**.  

    Jeśli **pobrany profil** nie są wyświetlane jako opcja, przejdź do **ogólne** > **profile**. Jeśli nadal nie widzisz tego profilu, może być konieczne ponowne pobranie.  

    ![Przykład zrzucie ekranu pokazano aplikację ustawienia w profilu pobrane, ustawienie.](./media/ios-1904-settings-badge.PNG)  

9. Naciśnij przycisk **Zainstaluj**.  
    
10. Zmień hasło urządzenia Następnie wybierz przycisk **zainstalować**.    

    ![Zrzut ekranu w aplikacji ustawienia ekranie instalacji profilu, z kursorem na ** Zainstaluj ** przycisku.](./media/ios-1904-password-install.PNG)  


11. Następny ekran jest ostrzeżenie standardowego systemu do zarządzania urządzeniami. Aby kontynuować instalację, naciśnij **zainstalować**. Jeśli zostanie wyświetlony monit, aby zaufać zdalnego zarządzania, naciśnij przycisk **zaufania**.  

    ![Zrzut ekranu ustawień aplikacji, ekran ostrzegawczy standardowych systemowych dla certyfikatu głównego i zarządzania urządzeniami przenośnymi.](./media/ios-15-cp-enroll-1903.PNG)  

12. Po zakończeniu instalacji wybierz **gotowe**. Aby zweryfikować, że profil został zainstalowany, przejdź do **Zarządzanie profilami i urządzeniami** ustawienia. Powinien zostać wyświetlony profil wymieniony w obszarze **zarządzanie urządzeniami przenośnymi**.   

    ![Zrzut ekranu ustawień aplikacji, Zarządzanie profilami i urządzeniami ustawień przedstawiający profil zarządzania.](./media/ios-00-cp-enroll-1903.PNG)  

13. Wróć do aplikacji Portal firmy. Portal firmy rozpocznie się synchronizowanie i skonfigurować urządzenie. Portal firmy może spowodować wyświetlenie monitu można zaktualizować dodatkowe ustawienia urządzeń. Jeśli naciśnij przycisk **Kontynuuj**.  

    ![Zrzut ekranu aplikacji Portal firmy, "Konfiguracja dostępu do" ekran, żółtego trójkąta obok ustawienia wymagań.](./media/ios-12-cp-enroll-1903.PNG)  

14. Będziesz wiedzieć, że czy konfiguracja została ukończona w przypadku, gdy wszystkie elementy na liście Pokaż zielone koło. Naciśnij pozycję **Gotowe**.   
    
    ![Zrzut ekranu aplikacji Portal firmy, "wszystko jest gotowe!" ekran przedstawiający wszystkie okręgów.](./media/ios-13-cp-enroll-1903.PNG)  

> [!Note]
> Jeśli Twoja organizacja monitoruje limity danych i głosu lub dostarcza urządzenia należące do firmy, może być kilka kroków do wykonania. Jeśli zostanie wyświetlony monit, aby zainstalować **Datalert** aplikacji, zobacz [zarejestrowanie urządzenia w rozwiązaniu do zarządzania wydatkami](enroll-your-device-with-telecom-expense-management-ios.md). Jeśli Twoja organizacja jest częścią Device Enrollment Program firmy Apple, Dowiedz się, [sposobu rejestrowania urządzenia należące do firmy](enroll-your-device-dep-ios.md).  

## <a name="next-steps"></a>Następne kroki  
Znajdź aplikacje, które pomogą Ci w pracy lub nauki. Dowiedz się, [jak aplikacje stają się dostępne](use-managed-apps-on-your-device-ios.md) użytkownikowi za pośrednictwem portalu firmy.  

Nadal potrzebujesz pomocy? Skontaktuj się z działem pomocy technicznej Twojej firmy. Odpowiednie informacje kontaktowe możesz znaleźć w [witrynie aplikacji Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).  
