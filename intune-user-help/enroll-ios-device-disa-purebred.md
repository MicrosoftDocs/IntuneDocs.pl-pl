---
title: Zarejestrowanie urządzenia z systemem iOS lub iPadOS przy użyciu Intune — Portal firmy i DISA purebred
description: Dowiedz się, jak zarejestrować urządzenie z systemem iOS lub iPadOS i skonfigurować pochodne uwierzytelnianie poświadczeń za pomocą DISA purebred.
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
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5c484b98466c1418016f4ebc6cc805e412d7891e
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "73415792"
---
# <a name="set-up-ios-or-ipados-device-with-company-portal-and-disa-purebred"></a>Konfigurowanie urządzenia z systemem iOS lub iPadOS przy użyciu Portal firmy i DISA purebred  

Zarejestruj urządzenie przy użyciu aplikacji Portal firmy w usłudze Intune, aby uzyskać bezpieczny dostęp mobilny do poczty e-mail, plików i aplikacji w organizacji. Zarejestrowane urządzenie staje się urządzeniem *zarządzanym*. Organizacja może przypisywać zasady i aplikacje do urządzenia za pośrednictwem dostawcy zarządzania urządzeniami przenośnymi (MDM), takiego jak usługa Intune.  

Podczas rejestracji na urządzeniu zostanie również zainstalowana poświadczenie pochodne. W przypadku uzyskiwania dostępu do zasobów lub podpisywania i szyfrowania wiadomości e-mail w organizacji może być wymagane użycie poświadczenie pochodne jako metody uwierzytelniania. 

Istnieje konieczność skonfigurowania poświadczenie pochodne w przypadku używania karty inteligentnej w celu:

* Zaloguj się do aplikacji szkolnych lub służbowych, Wi-Fi i wirtualnych sieci prywatnych (VPN)
* Podpisywanie i szyfrowanie służbowych wiadomości e-mail przy użyciu certyfikatów S/MIME  

W tym artykule opisano:  

   * Zarejestrowanie urządzenia przenośnego z systemem iOS lub iPadOS za pomocą Intune — Portal firmy.  
   * Uzyskaj poświadczenie pochodne od dostawcy poświadczeń pochodnych organizacji, [DISA purebred](https://cyber.mil/pki-pke/purebred/).  

## <a name="what-are-derived-credentials"></a>Co to są poświadczenia pochodne?  
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

Podczas instalacji należy również skontaktować się z agentem lub przedstawicielem purebred.      

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
8. Na ekranie **Konfiguracja mobilnego dostępu do kart inteligentnych** :  
    a. Naciśnij link do instrukcji dotyczących konfigurowania swojej organizacji. Jeśli Twoja organizacja nie poda dodatkowych instrukcji, zostanie on wysłany do tego artykułu.  
    b. Kliknij przycisk **Otwórz** , aby otworzyć aplikację purebred.  

    ![Przykładowy zrzut ekranu przedstawiający ekran Portal firmy konfigurowania mobilnego dostępu do kart inteligentnych.](./media/smart-card-open-disa-purebred.png)  
9. Po wyświetleniu monitu o zezwolenie Portal firmy otworzyć aplikację rejestracji purebred wybierz pozycję **Otwórz**.   

    ![Przykładowy zrzut ekranu przedstawiający monit Portal firmy, aby otworzyć aplikację DISA purebred.](./media/open-app-prompt-disa-purbred.png)  
10. Gdy aplikacja działa, należy skontaktować się z agentem purebred w organizacji w celu skonfigurowania i pobrania profilu konfiguracji przed rejestracją purebred.   
11. Przejdź do pozycji Ustawienia Aplikacja > **Ogólne** **Profile > & Zarządzanie urządzeniami** > **Zainstaluj profil** i naciśnij pozycję **Zainstaluj**.  
12. Wprowadź kod dostępu do urządzenia.  
13. Zainstaluj profil. Może być konieczne naciśnięcie przycisku **Zainstaluj** więcej niż jeden raz, aby rozpocząć instalację. 
14. Wróć do aplikacji do rejestracji purebred. Postępuj zgodnie z instrukcjami agenta purebred, aby kontynuować.  
 
15. Po pobraniu profilu konfiguracji przejdź do pozycji Ustawienia Aplikacja > **ogólne** > **Profile & Zarządzanie urządzeniami** > **Zainstaluj profil** i naciśnij pozycję **Zainstaluj**.   
16.  Wprowadź kod dostępu do urządzenia.
17. Zainstaluj profil. Może być konieczne naciśnięcie przycisku **Zainstaluj** więcej niż jeden raz, aby rozpocząć instalację. 
18. Po zakończeniu instalacji Wróć do aplikacji Portal firmy.  
19.  Na ekranie **Konfiguracja mobilnego dostępu do karty inteligentnej** naciśnij pozycję **Kontynuuj**.  

20. Na ekranie **Importowanie certyfikatów** zostanie pobrane i zaimportowane poświadczenie pochodne otrzymane z DISA purebred.  

    a. Naciśnij przycisk **Kontynuuj**.   

    Przykład ![zrzut ekranu przedstawiający ekran Portal firmy ustawienia importowania certyfikatów.](./media/import-certificate-disa-purebred.png)  
    b. Przejdź do obszaru usługi iCloud **przeglądaj** > **lokalizacje**i naciśnij pozycję **więcej lokalizacji**.  

    Przykład ![zrzut ekranu przedstawiający dysk iCloud, menu Przeglądaj wyróżnianie opcji więcej lokalizacji.](./media/icloud-drive-more-locations.png)  
    c. Naciśnij przełącznik, aby włączyć **łańcuch kluczy purebred**.  

    ![Przykładowy zrzut ekranu przedstawiający dysk usługi iCloud, widok przeglądania, wyróżnianie, że przełącznik łańcucha kluczy purebred jest włączony.](./media/icloud-drive-enable-purebred-keychain.png)   

    d. Naciśnij pozycję **pakiet poświadczeń purebred**.  

    Przykład ![zrzut ekranu przedstawiający ekran systemu iOS z opcją możliwego do wybrania pakietem poświadczeń purebred.](./media/purebred-credential-package.png)  
    f. Zostanie wyświetlona lista certyfikatów. Wybierz jeden z nich, a następnie naciśnij pozycję **Importuj klucz**.  

    ![Przykładowy zrzut ekranu przedstawiający listę wybranych certyfikatów z jednym już wybranym.](./media/import-purebred-keychain.png) 
21. Wróć do aplikacji Portal firmy i poczekaj na zakończenie konfigurowania urządzenia przez Portal firmy.   

## <a name="next-steps"></a>Następne kroki  
Po zakończeniu rejestracji będziesz mieć dostęp do zasobów służbowych, takich jak poczta e-mail, Sieć Wi-Fi i wszystkie aplikacje udostępniane przez organizację. Aby uzyskać więcej informacji na temat pobierania, wyszukiwania, instalowania i odinstalowywania aplikacji w Portal firmy, zobacz:

* [Zarządzanie aplikacjami z witryny internetowej Portalu firmy](manage-apps-cpweb.md)  
* [Korzystanie z aplikacji zarządzanych na urządzeniu](use-managed-apps-on-your-device-ios.md)  

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).
