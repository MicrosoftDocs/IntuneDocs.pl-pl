---
title: Zarejestrowanie urządzenia z systemem iOS lub iPadOS przy użyciu Intune — Portal firmy i Entrust Datacard
description: Zarejestruj urządzenie z systemem iOS lub iPadOS i skonfiguruj pochodne uwierzytelnianie poświadczeń przy użyciu Entrust Datacard.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: tisilver
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: b976e9a47a56c7af1e754f5b5b0162410e278025
ms.sourcegitcommit: caee3c3fa77586314aa8040b0caf32a0527b669e
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 01/10/2020
ms.locfileid: "75856396"
---
# <a name="set-up-ios-or-ipados-device-with-company-portal-and-entrust-datacard"></a>Konfigurowanie urządzenia z systemem iOS lub iPadOS przy użyciu Portal firmy i Entrust Datacard

Zarejestruj urządzenie przy użyciu aplikacji Portal firmy w usłudze Intune, aby uzyskać bezpieczny dostęp mobilny do poczty e-mail, plików i aplikacji w organizacji. Zarejestrowane urządzenie staje się urządzeniem *zarządzanym*. Organizacja może przypisywać zasady i aplikacje do urządzenia za pośrednictwem dostawcy zarządzania urządzeniami przenośnymi (MDM), takiego jak usługa Intune.  

Podczas rejestracji na urządzeniu zostanie również zainstalowana poświadczenie pochodne. W przypadku uzyskiwania dostępu do zasobów lub podpisywania i szyfrowania wiadomości e-mail w organizacji może być wymagane użycie poświadczenie pochodne jako metody uwierzytelniania. 

Istnieje konieczność skonfigurowania poświadczenie pochodne w przypadku używania karty inteligentnej w celu:  

* Zaloguj się do aplikacji szkolnych lub służbowych, Wi-Fi i wirtualnych sieci prywatnych (VPN)
* Podpisywanie i szyfrowanie służbowych wiadomości e-mail przy użyciu certyfikatów S/MIME  

W tym artykule opisano następujące czynności:  

   * Zarejestrowanie urządzenia przenośnego z systemem iOS lub iPadOS za pomocą Intune — Portal firmy.  
   * Uzyskaj poświadczenie pochodne od dostawcy poświadczeń pochodnych organizacji, [Entrust Datacard](https://www.entrustdatacard.com/).  

### <a name="what-are-derived-credentials"></a>Co to są poświadczenia pochodne?  
Poświadczenie pochodne to certyfikat pochodzący z poświadczeń karty inteligentnej i zainstalowany na urządzeniu. Umożliwia dostęp zdalny do zasobów służbowych, jednocześnie uniemożliwiając nieautoryzowanym użytkownikom dostęp do poufnych informacji.  

Poświadczenia pochodne są używane do: 
* Uwierzytelniaj uczniów i pracowników, którzy logują się do aplikacji szkolnych lub służbowych, Wi-Fi i sieci VPN
* Podpisywanie i szyfrowanie służbowych wiadomości e-mail przy użyciu certyfikatów S/MIME

Pochodne poświadczenia są implementacją wytycznych National Institute of Standards and Technology (NIST) dla pochodnych poświadczeń weryfikacji tożsamości osobistej (PIV) w ramach publikacji specjalnej (SP) 800-157.  

## <a name="prerequisites"></a>Wymagania wstępne

 Aby ukończyć rejestrację, musisz mieć:

* Twoja szkoła lub karta inteligentna udostępniana przez służbę
* Dostęp do komputera lub kiosku, w którym można się zalogować za pomocą karty inteligentnej
* Urządzenie przenośne
* Aplikacja Intune — Portal firmy dla systemów iOS i iPadOS zainstalowana na urządzeniu  


## <a name="enroll-device"></a>Rejestrowanie urządzenia  
1. Otwórz aplikację Portal firmy dla systemu iOS/iPadOS na urządzeniu przenośnym i zaloguj się przy użyciu konta służbowego.  

2. Zapisz kod na ekranie.  

    ![Przykładowy obraz aplikacji Portal firmy z komunikatem na ekranie i kodem.](./media/copy-code-intercede.png)   

3. Przełącz się na urządzenie z obsługą kart inteligentnych i przejdź do https://microsoft.com/devicelogin. 
4. Wprowadź kod, który został wcześniej zapisany.  

    ![Przykładowy zrzut ekranu przedstawiający wiersz Portal firmy witryny sieci Web "Wprowadź kod".](./media/enter-code-intercede.png)   

5. Włóż kartę inteligentną, aby się zalogować.   
6. Wróć do aplikacji Portal firmy na swoim urządzeniu przenośnym i postępuj zgodnie z instrukcjami wyświetlanymi na ekranie, aby zarejestrować urządzenie.  
7. Po zakończeniu rejestracji Portal firmy zostanie powiadomiona o skonfigurowaniu karty inteligentnej. Wybierz powiadomienie. Jeśli nie otrzymasz powiadomienia, Sprawdź swój adres e-mail.   

    ![Przykładowy zrzut ekranu przedstawiający Powiadomienie wypychane Portal firmy na ekranie głównym urządzenia.](./media/action-required-in-app-intercede.png)  

8. Na ekranie **Setup Mobile dostęp do kart inteligentnych** ekran:   
    a. Naciśnij link do instrukcji konfiguracji organizacji. Jeśli Twoja organizacja nie poda dodatkowych instrukcji, zostanie on wysłany do tego artykułu.  
    b. Naciśnij pozycję **Rozpocznij**.  

    ![Przykładowy zrzut ekranu przedstawiający ekran Portal firmy konfigurowania mobilnego dostępu do kart inteligentnych.](./media/smart-card-info-intercede.png)

9. Przejdź do urządzenia z obsługą kart inteligentnych i Otwórz IdentityGuard. 
10. Znajdź obszar Logowanie przy użyciu poświadczeń inteligentnych i wybierz przycisk Zaloguj.  
11. Po wyświetleniu monitu o wybranie certyfikatu wybierz swoje poświadczenia karty inteligentnej. Następnie wybierz pozycję **OK**. 
12. Wprowadź numer PIN karty inteligentnej.  
13. Zostanie wyświetlony monit o wybranie z listy akcji. Wybierz ten, który umożliwia zarejestrowanie w ramach pochodnego mobilnego urządzenia przenośnego. Link lub przycisk mogą powiedzieć, **chcę zarejestrować się na potrzeby poświadczenie pochodnej karty inteligentnej dla urządzeń przenośnych.**  
14. Wybierz, czy aplikacja obsługująca funkcję Smart Credential została pomyślnie pobrana i zainstalowana. Wszystko gotowe. Przejdź do następnego ekranu.   
15. Wprowadź informacje o pochodnym poświadczeniu karty inteligentnej.  
    a. W polu Nazwa tożsamości wprowadź dowolną nazwę, na przykład *powierzać pochodną*poświadczeń.  
    b. Z menu rozwijanego wybierz pozycję **powierzyć IdentityGudard Mobile Credential**.  
    c. Przejdź do następnego kroku. Zostanie wyświetlony kod QR z hasłem numerycznym.  

16. Wróć do urządzenia przenośnego. Na ekranie Portal firmy > **uzyskać** kod QR naciśnij pozycję **Kontynuuj**. 

    ![Przykładowy zrzut ekranu przedstawiający ekran Portal firmy Pobierz kod QR.](./media/get-qr-code-intercede.png)  
17. Naciśnij pozycję **używać aparatu** > **OK**.  

    ![Przykładowy zrzut ekranu przedstawiający monit Portal firmy, z prośbą o zezwolenie na dostęp do aparatu.](./media/allow-cp-camera-access-intercede.png)  
18. Zeskanuj obraz kodu QR, który znajduje się na urządzeniu z obsługą kart inteligentnych.  
19. Wprowadź hasło liczbowe, które pojawia się w obszarze kodu QR.  

    ![Przykładowy zrzut ekranu przedstawiający ekran Portal firmy hasło wymagane, wprowadź pole hasło.](./media/enter-password-derived-credentials.png)   

20. Zaczekaj, aż Portal firmy zakończy Konfigurowanie urządzenia.  


## <a name="next-steps"></a>Następne kroki  
Po zakończeniu rejestracji będziesz mieć dostęp do zasobów służbowych, takich jak poczta e-mail, Sieć Wi-Fi i wszystkie aplikacje udostępniane przez organizację. Aby uzyskać więcej informacji na temat pobierania, wyszukiwania, instalowania i odinstalowywania aplikacji w Portal firmy, zobacz:

* [Zarządzanie aplikacjami z witryny internetowej Portalu firmy](manage-apps-cpweb.md)  
* [Korzystanie z aplikacji zarządzanych na urządzeniu](use-managed-apps-on-your-device-ios.md)  

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).  
