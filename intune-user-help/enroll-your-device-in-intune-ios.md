---
title: Konfigurowanie urządzenia z systemem iOS do uzyskiwania dostępu do zasobów firmy | Microsoft Docs
description: Opisuje sposób udostępniania urządzenia z systemem iOS do zarządzania przez usługę Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/26/2019
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
ms.openlocfilehash: ee0f438d929abd6b5b90acbaeeddc41e3ce11f98
ms.sourcegitcommit: 44095bbd1502b02201a01604531f4105401fbb92
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/27/2019
ms.locfileid: "58490646"
---
# <a name="set-up-ios-device-access-to-your-company-resources"></a>Konfigurowanie urządzenia z systemem iOS do uzyskiwania dostępu do zasobów firmy  

Zarejestruj urządzenie z systemem iOS przy użyciu aplikacji Portal firmy w usłudze Intune, aby uzyskać bezpieczny dostęp do poczty e-mail, plików i aplikacji w organizacji.

Aby uzyskiwać dostęp do własnościowych danych z urządzenia firmowego lub osobistego, musisz dodać urządzenie do zarządzania. Po przekazaniu urządzenia do zarządzania organizacja przypisze zasady i aplikacje do urządzenia za pośrednictwem dostawcy zarządzania urządzeniami przenośnymi (MDM), takiego jak usługa Intune. 

Aby utrzymywać dostęp do informacji służbowych z urządzenia, musisz skonfigurować urządzenie, aby dopasować je do preferowanych ustawień organizacji. W tym artykule opisano, jak za pomocą portalu firmy zarejestrować urządzenia i Obsługa wymagań ustawienie Twojej organizacji. 

> [!NOTE]
> Jeśli nastąpiła próba dostępu do firmowej poczty e-mail w aplikacji poczty, a następnie został wyświetlony monit o przekazanie urządzenia do zarządzania, jesteś w odpowiednim miejscu. Aby uzyskać dostęp do poczty e-mail i innych zasobów firmy na swoim urządzeniu z systemem iOS, postępuj zgodnie z poniższymi instrukcjami.  

## <a name="what-to-expect-from-the-company-portal-app"></a>Czego można oczekiwać od aplikacji Portal firmy  

### <a name="security"></a>Zabezpieczenia  
Podczas początkowej konfiguracji aplikacja wymaga uwierzytelnienia użytkownika w organizacji. Następnie informuje użytkownika o wszelkich wymaganych aktualizacjach ustawieniach urządzenia. Na przykład organizacje często ustawiają wymagania dotyczące minimalnej i maksymalnej długości haseł, które trzeba spełnić.     

### <a name="protection"></a>Protection  
Po zarejestrowaniu urządzenia aplikacja Portal firmy będzie nadal upewniać się, że urządzenie jest chronione. Jeśli przykładowo zainstalujesz aplikację z niezaufanego źródła, aplikacja będzie wysyłać alerty i czasami odwoływać dostęp do danych firmowych. Takie zasady jest często używany w organizacji, a często, musisz odinstalować niezaufanych aplikację, zanim można go odzyskać.  

### <a name="setting-notifications"></a>Ustawianie powiadomień  
Jeśli po zarejestrowaniu organizacja wymusi nowe wymagania dotyczące zabezpieczeń, np. uwierzytelnianie wieloskładnikowe, aplikacja Portal firmy powiadomi użytkownika. Będziesz mieć szansę na dostosowanie ustawień, aby nadal kontynuować pracę z urządzenia.  

Aby uzyskać więcej informacji o rejestracji, zobacz [Co się stanie, jeśli zainstaluję aplikację Portal firmy i zarejestruję swoje urządzenie?](https://docs.microsoft.com//intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios).  

## <a name="enroll-your-ios-device"></a>Rejestrowanie urządzenia z systemem iOS   

> [!IMPORTANT]
> Zrzuty ekranu w tej sekcji pokazano środowisko dla urządzeń z systemem iOS w wersji 12.1 i starszych. Gdy to stosowne, uwzględniliśmy instrukcje specyficzne dla systemu iOS w wersji 12.2 lub nowszy. Jeśli zauważysz, że środowisko różni się od zrzutach ekranu przedstawiono, zapoznaj się z instrukcjami 12.2.      

Przejdź do sklepu App store, aby pobrać i zainstalować [aplikacji Portal firmy Intune](install-and-sign-in-to-the-intune-company-portal-app-ios.md) do Twojego urządzenia. Podczas rejestracji należy także połączenia Wi-Fi i dostęp do programu Safari. 

Jeśli zatrzymasz się przez więcej niż kilka minut, podczas rejestrowania aplikacji mogą zamknąć lub zakończyć instalację. Jeśli tak się stanie, Otwórz aplikację Portal firmy i spróbuj ponownie.  

1. Otwórz aplikację Portal firmy i zaloguj się za pomocą konta służbowego. 

    ![Zrzut ekranu aplikacji Portal firmy i logowanie.](./media/ios-01-cp-enroll-1903.PNG)  

2. Po wyświetleniu monitu, aby otrzymywać powiadomienia z aplikacji Portal firmy, naciśnij **Zezwalaj.** Portal firmy używa powiadomienia do wyzwalania alertu, jeśli na przykład, należy zaktualizować ustawienia urządzenia. 

    ![Zrzut ekranu strony głównej portalu firmy, "Powiadomienia" w wierszu polecenia.](./media/ios-04-cp-enroll-1903.PNG)  

3. Na **Konfigurowanie dostępu** ekranu, wybierz opcję **rozpocząć.**  

     ![Zrzut ekranu aplikacji Portal firmy, ekran "Konfigurowanie dostępu".](./media/ios-05-cp-enroll-1903.PNG)  

4. Zapoznaj się z artykułem listy informacje o urządzeniach w organizacji może zobaczyć. [Dodatkowe informacje na ten temat](what-info-can-your-company-see-when-you-enroll-your-device-in-Intune.md) znajduje się za pośrednictwem **więcej** łącza. Gdy skończysz, naciśnij **Kontynuuj**.  

    ![Zrzut ekranu aplikacji Portal firmy "Moja organizacja widocznej", za pomocą przycisku Kontynuuj.](./media/ios-06-cp-enroll-1903.PNG)  
 
5. **Co przyniesie przyszłość?** ekranu znajduje się podsumowanie pozostałe kroki. Te kroki mogą być inne w zależności od używanej wersji systemu iOS. 
    * **System iOS 12.2 nowszy**: środowisko zamiast tego konieczne będzie:  

        a. **Zezwalaj na pobieranie profilu zarządzania**: przeglądarce otwórz witrynę sieci Web Portal firmy oraz monit o pozwolenie na pobieranie. Pobieranie zostaną zapisane w aplikacji ustawienia.  

        b. **Otwórz w aplikacji ustawienia i zainstalować profil**: musisz przejść do aplikacji ustawienia i zainstalowanie profilu zarządzania.  

        c. **Wróć do aplikacji Portal firmy**: musisz powrócić do aplikacji Portal firmy, aby ukończyć konfigurację.  

    Gdy wszystko będzie gotowe do pobrania profilu zarządzania, wybierz przycisk **Kontynuuj**.  

6. Safari powoduje otwarcie witryny internetowej Portal firmy. Po wyświetleniu monitu, aby pobrać profil konfiguracji, naciśnij **Zezwalaj**.  
    * **System iOS 12.2 nowszy**: Poczekaj, aż profil pobierania w przeglądarce Safari i naciśnij pozycję **gotowe**. Następnie otwórz aplikację **Ustawienia** na urządzeniu.  

    > [!IMPORTANT]
    > Należy przejść do **ustawienia** aplikację i zainstaluj ten profil 8 minut ją pobrać. Jeśli nie istnieje profil, który zostanie usunięty i będzie trzeba ponownie uruchamiać rejestracji. 

7. W **ustawienia** aplikacji, naciśnij pozycję **Zainstaluj pobrany profil** > **zainstalować**. Jeśli **Zainstaluj pobrany profil** nie są wyświetlane jako opcja, przejdź do **ogólne** > **profile**. Jeśli nadal nie widzisz tego profilu, może być konieczne ponowne pobranie.  

    ![Zrzut ekranu w aplikacji ustawienia ustawienia Instalowanie profilu pobrane ze wskaźnikiem red, który wskazuje ostatnio pobrany profil.](./media/ios-10-cp-enroll-1903.PNG)  
    
8. Po wyświetleniu monitu wprowadź hasło urządzenia. Następnie wybierz przycisk **zainstalować**.      

9. Następny ekran jest ostrzeżenie standardowego systemu do zarządzania urządzeniami. Aby dowiedzieć się więcej na temat co Twoja organizacja może zobaczyć na twoim urządzeniu, zobacz odpowiednią [artykułu witryny docs Intune](what-info-can-your-company-see-when-you-enroll-your-device-in-Intune.md). Aby kontynuować instalację, naciśnij **zainstalować**. Po wyświetleniu monitu o zaufanie zarządzania zdalnego, naciśnij **zaufania**.  

    ![Zrzut ekranu ustawień aplikacji, ekran ostrzegawczy standardowych systemowych dla certyfikatu głównego i zarządzania urządzeniami przenośnymi.](./media/ios-15-cp-enroll-1903.PNG)  

10. Po zakończeniu instalacji wybierz **gotowe**. Aby zweryfikować, że profil został zainstalowany, przejdź do **Zarządzanie profilami i urządzeniami** ustawienia. Powinien zostać wyświetlony profil wymieniony w obszarze **zarządzanie urządzeniami przenośnymi**.   

    ![Zrzut ekranu ustawień aplikacji, Zarządzanie profilami i urządzeniami ustawień przedstawiający profil zarządzania.](./media/ios-00-cp-enroll-1903.PNG)  


11. Wróć do aplikacji **Portal firmy**. Portal firmy rozpocznie się synchronizowanie i skonfigurować urządzenie. Portal firmy może spowodować wyświetlenie monitu można zaktualizować dodatkowe ustawienia urządzeń. Jeśli naciśnij przycisk **Kontynuuj**.

    ![Zrzut ekranu aplikacji Portal firmy, "Konfiguracja dostępu do" ekran, żółtego trójkąta obok ustawienia wymagań.](./media/ios-12-cp-enroll-1903.PNG)  

12. Będziesz wiedzieć, że czy konfiguracja została ukończona w przypadku, gdy wszystkie elementy na liście Pokaż zielone koło. Naciśnij pozycję **Gotowe**.  
    
    ![Zrzut ekranu aplikacji Portal firmy, "wszystko jest gotowe!" ekran przedstawiający wszystkie okręgów.](./media/ios-13-cp-enroll-1903.PNG)  

> [!Note]
> Jeśli Twoja organizacja monitoruje limity danych i głosu lub dostarcza urządzenia należące do firmy, może być kilka kroków do wykonania. Jeśli zostanie wyświetlony monit, aby zainstalować **Datalert** aplikacji, zobacz [zarejestrowanie urządzenia w rozwiązaniu do zarządzania wydatkami](enroll-your-device-with-telecom-expense-management-ios.md). Jeśli Twoja organizacja jest częścią Device Enrollment Program firmy Apple, Dowiedz się, [sposobu rejestrowania urządzenia należące do firmy](enroll-your-device-dep-ios.md).  

## <a name="next-steps"></a>Następne kroki  
Znajdź aplikacje, które pomogą Ci w pracy lub nauki. Dowiedz się, [jak aplikacje stają się dostępne](use-managed-apps-on-your-device-ios.md) użytkownikowi za pośrednictwem portalu firmy.  

Nadal potrzebujesz pomocy? Skontaktuj się z działem pomocy technicznej Twojej firmy. Odpowiednie informacje kontaktowe możesz znaleźć w [witrynie aplikacji Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).  
