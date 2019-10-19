---
title: Konfigurowanie urządzenia z systemem iOS do uzyskiwania dostępu do zasobów firmy | Microsoft Docs
description: Opisuje sposób udostępniania urządzenia z systemem iOS do zarządzania przez usługę Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 09/12/2019
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
ms.collection: M365-identity-device-management
ms.openlocfilehash: e468042ab81d563c9fa4b272661508a340d61aa9
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506237"
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

    ![Przykładowy zrzut ekranu logowania w aplikacji Portal firmy.](./media/ios-01-cp-enroll-1904.PNG)  

2. Po wyświetleniu monitu dotyczącego odbierania powiadomień z aplikacji Portal firmy naciśnij pozycję **Zezwalaj**. Powiadomienia z aplikacji Portal firmy mogą zawierać między innymi alerty dotyczące koniecznych zmian w ustawieniach urządzenia. 

    ![Przykładowy zrzut ekranu monitu o powiadomieniach na stronie głównej aplikacji Portal firmy.](./media/ios-02-cp-enroll-1904.PNG)  

3. Na ekranie **Konfigurowanie dostępu** wybierz pozycję **Rozpocznij**.  

     ![Przykładowy zrzut ekranu „Konfigurowanie dostępu” w aplikacji Portal firmy.](./media/ios-03-cp-enroll-1904.PNG)  

4. Zapoznaj się z listą informacji o urządzeniu, które będą widoczne i niewidoczne dla Twojej organizacji. Następnie naciśnij przycisk **Kontynuuj**.  

5. Zapoznaj się z instrukcjami na ekranie **Co dalej?** . Gdy wszystko będzie gotowe do pobrania i zainstalowania profilu zarządzania, naciśnij przycisk **Kontynuuj**.  

 > [!IMPORTANT]
> Kolejne ekrany i czynności do wykonania będą różnić się w zależności od używanej wersji systemu iOS. Postępuj zgodnie z instrukcjami dotyczącymi używanej wersji systemu iOS. 

6. W przeglądarce Safari na urządzeniu zostanie otwarta witryna internetowa Portal firmy. Po wyświetleniu monitu dotyczącego pobrania profilu konfiguracji naciśnij pozycję **Zezwalaj**. Jeśli używasz systemu:  
    * iOS 12.2 lub nowszego: po zakończeniu pobierania naciśnij pozycję **Gotowe**. Przejdź do kroku 7. w tym artykule.
    * iOS 12.1 lub starszego: nastąpi automatyczne przekierowanie do aplikacji Ustawienia. Przejdź do kroku 8. w tym artykule.  
 
    Jeśli przypadkowo naciśniesz pozycję **Ignoruj**, odśwież stronę. Zostanie wyświetlony monit o otwarcie aplikacji Portal firmy. W aplikacji możesz nacisnąć przycisk **Pobierz ponownie**.

  > [!NOTE]
  > Należy zainstalować profil zarządzania zgodnie z poniższymi instrukcjami przed upływem 8 minut od jego pobrania. W przeciwnym przypadku profil zostanie usunięty i będzie trzeba ponownie uruchomić rejestrację.  

7. Tylko w systemie iOS 12.2 lub nowszym: po wyświetleniu monitu o otwarcie aplikacji Portal firmy naciśnij przycisk **Otwórz**. Na ekranie **Trwa instalowanie profilu zarządzania** znajduje się lista kroków instalacji profilu.

    ![Przykładowy zrzut ekranu Trwa instalowanie profilu zarządzania w aplikacji Portal firmy.](./media/ios-07-cp-enroll-1904.PNG)  

8. Otwórz aplikację Ustawienia i naciśnij pozycję **Profil pobrany**.  

    Jeśli opcja **Profil pobrany** nie jest widoczna, wybierz pozycję **Ogólne** > **Profile**. Jeśli nadal nie widzisz profilu, może być konieczne ponowne pobranie go.  

    ![Przykładowy zrzut ekranu przedstawiający ustawienie Profil pobrany w aplikacji Ustawienia.](./media/ios-1904-settings-badge.PNG)  

9. Naciśnij przycisk **Zainstaluj**.  
    
10. Wprowadź hasło urządzenia. Następnie naciśnij przycisk **Zainstaluj**.    

    ![Przykładowy zrzut ekranu instalacji profilu w aplikacji Ustawienia z kursorem na przycisku Zainstaluj.](./media/ios-10-cp-enroll-1904.PNG)  


11. Kolejny ekran zawiera standardowe ostrzeżenie systemowe dotyczące zarządzania urządzeniami. Aby kontynuować instalację, naciśnij przycisk **Zainstaluj**. Jeśli zostanie wyświetlony monit dotyczący zaufania na potrzeby zarządzania zdalnego, naciśnij pozycję **Ufaj**.  

    ![Przykładowy zrzut ekranu aplikacji Ustawienia ze standardowym ostrzeżeniem systemowym dotyczącym certyfikatu głównego i zarządzania urządzeniami mobilnymi.](./media/ios-11-cp-enroll-1904.PNG)  

12. Po zakończeniu instalacji naciśnij pozycję **Gotowe**. Aby zweryfikować instalację profilu, przejdź do obszaru ustawień **Profile i zarządzanie urządzeniami**. Profil powinien znajdować się na liście w obszarze **Zarządzanie urządzeniami mobilnymi**.   

    ![Przykładowy zrzut ekranu Profile i zarządzanie urządzeniami w aplikacji Ustawienia z widocznym profilem zarządzania.](./media/ios-12-cp-enroll-1904.PNG)  

13. Wróć do aplikacji Portal firmy. W aplikacji Portal firmy rozpocznie się synchronizowanie i konfigurowanie urządzenia. Może zostać wyświetlony monit o zaktualizowanie dodatkowych ustawień urządzenia. W takim przypadku naciśnij przycisk **Kontynuuj**.  

    ![Przykładowy zrzut ekranu „Konfigurowanie dostępu” w aplikacji Portal firmy z żółtym trójkątem obok wymagania dotyczącego ustawień.](./media/ios-13-cp-enroll-1904.PNG)  

14. Konfiguracja będzie zakończona, gdy obok wszystkich elementów na liście wyświetlona będzie ikona zielonego koła. Naciśnij pozycję **Gotowe**.   
    
    ![Przykładowy zrzut ekranu „Wszystko gotowe!” w aplikacji Portal firmy z ikoną zielonego koła przy wszystkich elementach.](./media/ios-14-cp-enroll-1904.PNG)  

> [!Note]
> Jeśli w Twojej organizacji są monitorowane limity danych i połączeń głosowych lub są udostępniane urządzenia należące do firmy, może być konieczne wykonanie kilku dodatkowych czynności. Jeśli zostanie wyświetlony monit o instalację aplikacji **Datalert**, zobacz [Rejestrowanie urządzenia w rozwiązaniu do zarządzania wydatkami telekomunikacyjnymi](enroll-your-device-with-telecom-expense-management-ios.md). Jeśli Twoja organizacja uczestniczy w programie Device Enrollment Program firmy Apple, zobacz [jak zarejestrować urządzenie należące do firmy](enroll-your-device-dep-ios.md).  

## <a name="it-administrator-support"></a>Pomoc techniczna dla administratora IT  
Jeśli jako administrator IT napotkasz problemy podczas rejestrowania urządzeń, zobacz [Troubleshooting iOS device enrollment problems in Microsoft Intune (Rozwiązywanie problemów z rejestrowaniem urządzeń z systemem iOS w usłudze Microsoft Intune)](https://support.microsoft.com/en-us/help/4039809). W tym artykule wymieniono typowe błędy, ich przyczyny i kroki prowadzące do ich usunięcia.  

## <a name="next-steps"></a>Następne kroki  
Znajdź aplikacje, które pomogą Ci w pracy lub szkole. Dowiedz się, [jak są udostępniane aplikacje](use-managed-apps-on-your-device-ios.md) za pośrednictwem aplikacji Portal firmy.  

Nadal potrzebujesz pomocy? Skontaktuj się z działem pomocy technicznej Twojej firmy. Odpowiednie informacje kontaktowe możesz znaleźć w [witrynie aplikacji Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).  
