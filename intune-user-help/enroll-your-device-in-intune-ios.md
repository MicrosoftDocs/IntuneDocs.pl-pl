---
title: Konfigurowanie urządzenia z systemem iOS do uzyskiwania dostępu do zasobów firmy | Microsoft Docs
description: Opisuje sposób udostępniania urządzenia z systemem iOS do zarządzania przez usługę Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 12/18/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: tisilv
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: 92d1ca850d8bb542f0b7fe027ab7af8c12089ef8
ms.sourcegitcommit: 9ee2401a2f01373a962749b0728c22385dbcba6d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/29/2020
ms.locfileid: "78181759"
---
# <a name="set-up-ios-device-access-to-your-company-resources"></a>Konfigurowanie urządzenia z systemem iOS do uzyskiwania dostępu do zasobów firmy  

Zarejestruj urządzenie z systemem iOS przy użyciu aplikacji Portal firmy w usłudze Intune, aby uzyskać bezpieczny dostęp do poczty e-mail, plików i aplikacji w organizacji.

Zarejestrowane urządzenie staje się urządzeniem *zarządzanym*. Organizacja może przypisywać zasady i aplikacje do urządzenia za pośrednictwem dostawcy zarządzania urządzeniami przenośnymi (MDM), takiego jak usługa Intune.  

> [!NOTE]
> Danych zebranych przez naszą usługę nie sprzedajemy z jakiegokolwiek powodu żadnym osobom trzecim.  

Aby zachować możliwość dostępu do informacji służbowych lub szkolnych za pomocą urządzenia, należy skonfigurować to urządzenie tak, aby dopasować je do preferowanych ustawień organizacji. W tym artykule opisano, jak za pomocą aplikacji Portal firmy zarejestrować urządzenie i dostosować się do ustawień wymaganych przez organizację.  
</br>
> [!VIDEO https://www.youtube.com/embed/mJyv6YcHi7c?rel=0]

> [!NOTE]
> Jeśli nastąpiła próba dostępu do firmowej poczty e-mail w aplikacji poczty, a następnie został wyświetlony monit o przekazanie urządzenia do zarządzania, jesteś w odpowiednim miejscu. Aby uzyskać dostęp do poczty e-mail i innych zasobów firmy na swoim urządzeniu z systemem iOS, postępuj zgodnie z poniższymi instrukcjami.  


## <a name="what-to-expect-from-the-company-portal-app"></a>Czego można oczekiwać od aplikacji Portal firmy  

### <a name="security"></a>Zabezpieczenia  
Podczas początkowej konfiguracji aplikacja wymaga uwierzytelnienia użytkownika w organizacji. Następnie informuje użytkownika o wszelkich wymaganych aktualizacjach ustawieniach urządzenia. Na przykład organizacje często ustawiają wymagania dotyczące minimalnej i maksymalnej długości haseł, które trzeba spełnić.

### <a name="protection"></a>Protection  
Po zarejestrowaniu urządzenia aplikacja Portal firmy będzie nadal upewniać się, że urządzenie jest chronione. Jeśli przykładowo zainstalujesz aplikację z niezaufanego źródła, aplikacja będzie wysyłać alerty i czasami odwoływać dostęp do danych firmowych. Tego typu zasady są często stosowane w organizacjach i często wymagają odinstalowania niezaufanych aplikacji w celu odzyskania dostępu.  

### <a name="setting-notifications"></a>Ustawianie powiadomień  
Jeśli po zarejestrowaniu organizacja wymusi nowe wymagania dotyczące zabezpieczeń, np. uwierzytelnianie wieloskładnikowe, aplikacja Portal firmy powiadomi użytkownika. Będziesz mieć szansę na dostosowanie ustawień, aby nadal kontynuować pracę z urządzenia.  

Aby uzyskać więcej informacji o rejestracji, zobacz [Co się stanie, jeśli zainstaluję aplikację Portal firmy i zarejestruję swoje urządzenie?](https://docs.microsoft.com//intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios).  

## <a name="enroll-your-ios-device"></a>Rejestrowanie urządzenia z systemem iOS  

Przejdź do sklepu App Store, aby pobrać i zainstalować [aplikację Portal firmy usługi Intune](install-and-sign-in-to-the-intune-company-portal-app-ios.md) na urządzeniu. Podczas rejestracji potrzebne będzie również połączenie Wi-Fi oraz dostęp do przeglądarki Safari. 

Wstrzymanie rejestracji na więcej niż kilka minut może spowodować zamknięcie aplikacji lub zakończenie konfiguracji. W takim przypadku otwórz aplikację Portal firmy i spróbuj ponownie.  

1. Otwórz aplikację Portal firmy i zaloguj się za pomocą konta służbowego.  

2. Po wyświetleniu monitu dotyczącego odbierania powiadomień z aplikacji Portal firmy naciśnij pozycję **Zezwalaj**. Powiadomienia z aplikacji Portal firmy mogą zawierać między innymi alerty dotyczące koniecznych zmian w ustawieniach urządzenia.  

3. Na ekranie **Konfigurowanie dostępu** wybierz pozycję **Rozpocznij**.   

    ![Przykładowy zrzut ekranu „Konfigurowanie dostępu” w aplikacji Portal firmy.](./media/ios-enrollment-checklist-1909.PNG)  

4. Zostanie wyświetlony ekran **Wybór typu urządzenia i rejestracji** z pytaniem o typ urządzenia.  
    * Jeśli swoje urządzenie masz od organizacji, naciśnij pozycję **Firma (nazwa organizacji) jest właścicielem tego urządzenia**. Następnie przejdź do sekcji [Zabezpieczanie całego urządzenia](#secure-entire-device) w tym artykule, aby zakończyć instalację.  
    * Naciśnij pozycję **To urządzenie należy do mnie**, jeśli używasz urządzenia osobistego przyniesionego z domu. Następnie przejdź do następnego kroku.  

    Jeśli nie widzisz tego ekranu, przejdź do sekcji [Zabezpieczanie całego urządzenia](#secure-entire-device), aby zakończyć instalację.  
    
    ![Przykładowy zrzut ekranu przedstawiający Portal firmy, ekran „Wybór typu urządzenia i rejestracji”, opcje typu urządzenia.](./media/ios-device-type-1909.PNG)  


5. Wybierz sposób ochrony danych na urządzeniu po jego zarejestrowaniu.  
    * Naciśnij pozycję **Zabezpieczanie całego urządzenia**, aby zabezpieczyć wszystkie aplikacje i dane na urządzeniu. Następnie przejdź do sekcji [Zabezpieczanie całego urządzenia](enroll-your-device-in-intune-ios.md#secure-entire-device), aby zakończyć instalację.
    * Naciśnij pozycję **Zabezpieczanie tylko aplikacji i danych służbowych**, aby zabezpieczyć tylko aplikacje i dane, do których uzyskujesz dostęp za pomocą konta służbowego. Następnie przejdź do sekcji [Zabezpieczanie tylko aplikacji i danych służbowych](enroll-your-device-in-intune-ios.md#secure-work-related-apps-and-data).  

    ![Przykładowy zrzut ekranu przedstawiający Portal firmy, ekran „Wybór typu urządzenia i rejestracji”, opcje typu rejestracji.](./media/ios-enrollment-type-1909.PNG)  


### <a name="secure-entire-device"></a>Zabezpieczanie całego urządzenia  

1. Na ekranie **Zarządzanie urządzeniami i prywatność** zapoznaj się z listą informacji o urządzeniu widocznych i niewidocznych dla Twojej organizacji. Następnie naciśnij przycisk **Kontynuuj**.  


 > [!IMPORTANT]
> Kolejne ekrany i czynności do wykonania będą różnić się w zależności od używanej wersji systemu iOS. Postępuj zgodnie z instrukcjami dotyczącymi używanej wersji systemu iOS. 

2. W przeglądarce Safari na urządzeniu zostanie otwarta witryna internetowa Portal firmy. Po wyświetleniu monitu dotyczącego pobrania profilu konfiguracji naciśnij pozycję **Zezwalaj**. Jeśli używasz systemu:  
    * iOS 12.2 lub nowszego: Po zakończeniu pobierania naciśnij pozycję **Zamknij**. Następnie przejdź do kroku 3.  
    * System iOS 12.1 i starsze: Po zakończeniu pobierania nastąpi automatyczne przekierowanie do aplikacji Ustawienia. Przejdź do kroku 4.  
 
    Jeśli przypadkowo naciśniesz pozycję **Ignoruj**, odśwież stronę. Zostanie wyświetlony monit o otwarcie aplikacji Portal firmy. Gdy tam będziesz, naciśnij pozycję **Pobierz ponownie**.

  > [!NOTE]
  > Należy zainstalować profil zarządzania zgodnie z poniższymi instrukcjami przed upływem 8 minut od jego pobrania. W przeciwnym przypadku profil zostanie usunięty i będzie trzeba ponownie uruchomić rejestrację.  

3. Po wyświetleniu monitu o otwarcie Portalu firmy naciśnij pozycję **Otwórz**. Zapoznaj się z informacjami na ekranie **Jak zainstalować profil zarządzania**.  

4. Przejdź do aplikacji Ustawienia, a następnie naciśnij pozycję **Zarejestruj w firmie < nazwa organizacji >** lub **Pobrano profil**.  

    ![Przykładowy zrzut ekranu przedstawiający aplikację Ustawienia, opcja rejestrowania w organizacji.](./media/enroll-in-organization-ios-1909.PNG)  

   Jeśli żadna z tych opcji nie zostanie wyświetlona, przejdź do pozycji **Ogólne** > **Profile i zarządzanie urządzeniami**> **Profil zarządzania**. Jeśli nadal nie widzisz profilu zarządzania, może być konieczne jego ponowne pobranie.  

5. Naciśnij przycisk **Zainstaluj**.  
    
6. Wprowadź hasło urządzenia. Następnie naciśnij przycisk **Zainstaluj**.    

7. Kolejny ekran zawiera standardowe ostrzeżenie systemowe dotyczące zarządzania urządzeniami. Aby kontynuować instalację, naciśnij przycisk **Zainstaluj**. Jeśli zostanie wyświetlony monit dotyczący zaufania na potrzeby zarządzania zdalnego, naciśnij pozycję **Ufaj**.  

8. Po zakończeniu instalacji naciśnij pozycję **Gotowe**. Aby zweryfikować instalację profilu, przejdź do obszaru ustawień **Profile i zarządzanie urządzeniami**. Profil powinien znajdować się na liście w obszarze **Zarządzanie urządzeniami mobilnymi**.   

    ![Przykładowy zrzut ekranu Profile i zarządzanie urządzeniami w aplikacji Ustawienia z widocznym profilem zarządzania.](./media/ios-12-cp-enroll-1904.PNG)  

9. Wróć do aplikacji Portal firmy. W aplikacji Portal firmy rozpocznie się synchronizowanie i konfigurowanie urządzenia. Może zostać wyświetlony monit o zaktualizowanie dodatkowych ustawień urządzenia. W takim przypadku naciśnij przycisk **Kontynuuj**.  

10. Konfiguracja będzie zakończona, gdy obok wszystkich elementów na liście wyświetlona będzie ikona zielonego znacznika wyboru. Naciśnij pozycję **Gotowe**.   

> [!Note]
> Jeśli w Twojej organizacji są monitorowane limity danych i połączeń głosowych lub są udostępniane urządzenia należące do firmy, może być konieczne wykonanie kilku dodatkowych czynności. Jeśli zostanie wyświetlony monit o instalację aplikacji **Datalert**, zobacz [Rejestrowanie urządzenia w rozwiązaniu do zarządzania wydatkami telekomunikacyjnymi](enroll-your-device-with-telecom-expense-management-ios.md). Jeśli Twoja organizacja uczestniczy w programie Device Enrollment Program firmy Apple, zobacz [jak zarejestrować urządzenie należące do firmy](enroll-your-device-dep-ios.md).  

### <a name="secure-work-related-apps-and-data"></a>Zabezpieczanie aplikacji i danych służbowych  
1. Zostanie wyświetlony ekran **Pobieranie aplikacji Microsoft Authenticator** (jeśli masz już aplikację Authenticator, nie zobaczysz tego ekranu, dlatego przejdź od razu do kroku 2).  
    1. Naciśnij pozycję **Pobierz ze sklepu App Store**.
    2. Po otwarciu sklepu App Store zainstaluj aplikację. 
    3. Wróć do Portalu firmy i naciśnij pozycję **Kontynuuj**.    
    
   Po zainstalowaniu aplikacji Microsoft Authenticator nie trzeba już niczego robić w związku z tą aplikacją. Wystarczy, że będzie obecna na urządzeniu. 

   ![Przykładowy zrzut ekranu przedstawiający Portal firmy, ekran „Pobieranie aplikacji Microsoft Authenticator”.](./media/download-ms-authenticator-1909.PNG)  

2. Na ekranie **Zarządzanie urządzeniami i prywatność** zapoznaj się z listą informacji o urządzeniu widocznych i niewidocznych dla Twojej organizacji. Następnie naciśnij przycisk **Kontynuuj**.  


 > [!IMPORTANT]
> Kolejne ekrany i czynności do wykonania będą różnić się w zależności od używanej wersji systemu iOS. Postępuj zgodnie z instrukcjami dotyczącymi używanej wersji systemu iOS. 

3. W przeglądarce Safari na urządzeniu zostanie otwarta witryna internetowa Portal firmy. Po wyświetleniu monitu dotyczącego pobrania profilu konfiguracji naciśnij pozycję **Zezwalaj**. Jeśli używasz systemu:  
    * iOS 12.2 lub nowszego: Po zakończeniu pobierania naciśnij pozycję **Zamknij**. Następnie przejdź do kroku 4.  
    * System iOS 12.1 i starsze: Po zakończeniu pobierania nastąpi automatyczne przekierowanie do aplikacji Ustawienia. Przejdź do kroku 5.  
 
    Jeśli przypadkowo naciśniesz pozycję **Ignoruj**, odśwież stronę. Zostanie wyświetlony monit o otwarcie aplikacji Portal firmy. W aplikacji możesz nacisnąć przycisk **Pobierz ponownie**.

  > [!NOTE]
  > Należy zainstalować profil zarządzania zgodnie z poniższymi instrukcjami przed upływem 8 minut od jego pobrania. W przeciwnym przypadku profil zostanie usunięty i będzie trzeba ponownie uruchomić rejestrację.  

4. Po wyświetleniu monitu o otwarcie Portalu firmy naciśnij pozycję **Otwórz**. Zapoznaj się z informacjami na ekranie **Jak zainstalować profil zarządzania**. 

5. Przejdź do aplikacji Ustawienia, a następnie naciśnij pozycję **Zarejestruj w firmie < nazwa organizacji >** lub **Pobrano profil**.  

    ![Przykładowy zrzut ekranu przedstawiający aplikację Ustawienia, opcja rejestrowania w organizacji.](./media/enroll-in-organization-ios-1909.PNG)  

   Jeśli żadna z tych opcji nie zostanie wyświetlona, przejdź do pozycji **Ogólne** > **Profile i zarządzanie urządzeniami**> **Profil zarządzania**. Jeśli nadal nie widzisz profilu zarządzania, może być konieczne jego ponowne pobranie.   


6. Na ekranie **Rejestracja użytkownika** naciśnij pozycję **Zarejestruj moje urządzenie iPhone**.  

    ![Przykładowy zrzut ekranu przedstawiający aplikację Ustawienia, ekran Rejestracja użytkownika, wyróżnienie przycisku rejestracji.](./media/user-enrollment-information-1909.PNG)  

7. Wprowadź hasło urządzenia. Następnie naciśnij przycisk **Zainstaluj**.  

8. Na ekranie **Logowanie** wprowadź hasło dla zarządzanego identyfikatora Apple ID. W większości przypadków te poświadczenia będą takie same jak te, które są używane do logowania się do konta służbowego, chyba że Twoja organizacja udostępni Ci inny zestaw poświadczeń. 
9. Naciśnij pozycję **Zaloguj się**.  
10. Komunikat o powodzeniu zostanie wyświetlony na ekranie krótko po zainstalowaniu profilu. Aby zweryfikować instalację profilu, przejdź do ustawień  **Profile i zarządzanie urządzeniami** . Profil powinien znajdować się na liście w obszarze  **Mobile Device Management**.  

    ![Przykładowy zrzut ekranu Profile i zarządzanie urządzeniami w aplikacji Ustawienia z widocznym profilem zarządzania.](./media/ios-12-cp-enroll-1904.PNG)  

11. Wróć do aplikacji Portal firmy. W aplikacji Portal firmy rozpocznie się synchronizowanie i konfigurowanie urządzenia. Może zostać wyświetlony monit o zaktualizowanie dodatkowych ustawień urządzenia. W takim przypadku naciśnij przycisk **Kontynuuj**.    

12. Konfiguracja będzie zakończona, gdy obok wszystkich elementów na liście wyświetlona będzie ikona zielonego znacznika wyboru. Naciśnij pozycję  **Gotowe**.  

## <a name="it-administrator-support"></a>Pomoc techniczna dla administratora IT  
Jeśli jako administrator IT napotkasz problemy podczas rejestrowania urządzeń, zobacz [Troubleshooting iOS device enrollment problems in Microsoft Intune (Rozwiązywanie problemów z rejestrowaniem urządzeń z systemem iOS w usłudze Microsoft Intune)](https://support.microsoft.com/en-us/help/4039809). W tym artykule wymieniono typowe błędy, ich przyczyny i kroki prowadzące do ich usunięcia.  

## <a name="next-steps"></a>Następne kroki  
Znajdź aplikacje, które pomogą Ci w pracy lub szkole. Dowiedz się, [jak są udostępniane aplikacje](use-managed-apps-on-your-device-ios.md) za pośrednictwem aplikacji Portal firmy.  

Nadal potrzebujesz pomocy? Skontaktuj się z działem pomocy technicznej Twojej firmy. Odpowiednie informacje kontaktowe możesz znaleźć w [witrynie aplikacji Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).  
