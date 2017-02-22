---
title: "Podstawowe ustawienia zarządzania danymi w aplikacjach usługi Office 365 — usługa Intune Azure w wersji zapoznawczej | Dokumentacja firmy Microsoft"
description: "Usługa Intune Azure w wersji zapoznawczej: dokumentacja uzupełniająca kreatora Zarządzaj aplikacjami usługi Office 365."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 01/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 852612ac-f146-4372-a900-3f6fdebd05ad
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: ayesham
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4c45b7fc8a520d869f21717fea36e27b242cf39
ms.openlocfilehash: 7cff88f0365cff1de133fdafdce2bd45b36d551e


---


# <a name="how-your-users-will-experience-basic-protection-on-managed-office-365-apps"></a>Na czym polega podstawowa ochrona użytkowników zarządzanych aplikacji usługi Office 365

Kreator **Zarządzaj aplikacjami usługi Office 365** tworzy zasady ochrony aplikacji dla każdej platformy urządzeń.

Kreator włącza następujące zasady:

**iOS**
* Szyfruj dane aplikacji

**Android**
* Szyfruj dane aplikacji
* Wymagaj prostego numeru PIN w celu udzielenia dostępu

Zasady te gwarantują możliwość zarządzania aplikacjami usługi Office 365, zapewniając możliwość czyszczenia danych służbowych z aplikacji pakietu Office odpowiednio do potrzeb. Zapewniają one także podstawową ochronę w przypadku, gdy urządzenie zostanie zagubione lub skradzione, szyfrując dane służbowe i wymagając wprowadzenia numeru PIN w celu wyświetlenia danych w aplikacjach pakietu Office 365.


W tym artykule posłużono się przykładem usługi OneDrive dla Firm w celu zademonstrowania sposobu korzystania przez użytkownika z aplikacji zarządzanych przez usługę Intune.


>[!NOTE]
>Na urządzeniu prywatnym aplikacja jest zazwyczaj pobierana przez użytkownika końcowego. Jeśli urządzenie jest zarządzane przez rozwiązanie do zarządzania urządzeniami przenośnymi (MDM), możesz wdrożyć tę aplikację na urządzeniu.

## <a name="user-experience-on-an-ios-device"></a>Środowisko użytkownika urządzenia z systemem iOS

1. Uruchom aplikację OneDrive dla Firm, aby otworzyć stronę logowania.  <br/> ![Ilustracja przedstawiająca ekran logowania programu OneDrive dla urządzeń z systemem iOS](./media/onedrive-ios-sign-in.png)
2. Wpisz nazwę użytkownika konta służbowego. Nastąpi przekierowanie do strony uwierzytelniania usługi Office 365, gdzie wprowadzisz swoje poświadczenia służbowe. <br/> ![Ilustracja przedstawiająca stronę logowania usługi Office 365](./media/o365-sign-in-ios.png)
3. Po pomyślnym uwierzytelnieniu poświadczeń przez usługę Azure Active Directory zostaną zastosowane zasady zarządzania aplikacjami mobilnymi (MAM) i pojawi się prośba o ponowne uruchomienie aplikacji OneDrive dla Firm.  <br/>![Ilustracja przedstawiająca monit o ponowne uruchomienie w systemie iOS](./media/ios-restart-prompt.png)
>[!NOTE]
>Komunikat informujący o konieczności ponownego uruchomienia aplikacji jest wyświetlany tylko na urządzeniach, które nie zostały zarejestrowane w usłudze Intune.


4. Uruchom ponownie aplikację OneDrive dla Firm. Aplikacja zostanie uruchomiona z włączonymi zasadami MAM, po czym zostanie wyświetlony monit o ustawienie kodu PIN dla urządzenia (o ile nie skonfigurowano w nim jeszcze kodu PIN). <br/> ![Ilustracja przedstawiająca monit o utworzenie kodu PIN](./media/pin-prompt-ios.png)

>[!NOTE]
>Większość użytkowników nie otrzyma tego monitu. Zobaczą go tylko ci użytkownicy, którzy nie włączyli kodu PIN na swoim urządzeniu z systemem iOS.


5. Po ustawieniu kodu PIN i jego zatwierdzeniu powróć do aplikacji OneDrive dla Firm. Zostanie wyświetlona jednorazowa informacja, że dane służbowe w usłudze OneDrive są teraz objęte ochroną administratora IT. <br/> ![Ilustracja przedstawiająca jednorazowe powiadomienie od administratora IT](./media/one-time-notice.png)
6. Zamknij powiadomienie, aby uzyskać dostęp do plików w aplikacji OneDrive dla Firm. <br/> ![Ilustracja przedstawiająca pliki w aplikacji OneDrive na urządzeniu z systemem iOS](./media/onedrive-files-ios.png) <br/>

>[!NOTE]
>Jeśli zmienisz wdrożone zasady, zmiany te zostaną zastosowane przy następnym otwarciu aplikacji.


## <a name="user-experience-on-an-android-device"></a>Środowisko użytkownika urządzenia z systemem Android

1. Uruchom aplikację OneDrive dla Firm, aby otworzyć stronę logowania.  <br/> ![Ilustracja przedstawiająca ekran powitalny aplikacji OneDrive](./media/onedrive-android-welcome.png)
2. Wpisz nazwę użytkownika konta służbowego. Nastąpi przekierowanie do strony uwierzytelniania usługi Office 365, gdzie wprowadzisz swoje poświadczenia służbowe. <br/> ![Ilustracja przedstawiająca logowanie do usługi O365 w systemie Android](./media/o365-sign-in-android.png)
3. Jeśli na urządzeniu nie została wcześniej zainstalowana aplikacja Portal firmy, po pomyślnym uwierzytelnieniu poświadczeń przez usługę Azure Active Directory zostanie wyświetlony komunikat z instrukcją dotyczącą instalacji tej aplikacji. Aby kontynuować, wybierz pozycję **Przejdź do sklepu**. <br/> ![Ilustracja przedstawiająca komunikat z informacją o konieczności pobrania aplikacji Portal firmy](./media/get-company-portal-android.png) <br/>Jeśli na telefonie została wcześniej zainstalowana aplikacja Portal firmy, nastąpi automatyczne uruchomienie usługi OneDrive dla Firm. Możesz przejść do uwagi końcowej.
>[!IMPORTANT]
>Choć użytkownik końcowy nie musi w praktyce otwierać aplikacji Portal firmy ani logować się do niej, aby odczytać wiadomości e-mail i dokumenty, to w systemie Android po skonfigurowaniu aplikacji pakietu Office pod kątem zarządzania przy użyciu zasady zarządzania aplikacjami mobilnymi (MAM) użytkownik urządzenia **musi** zainstalować aplikację Portal firmy w celu uzyskania dostępu do służbowych wiadomości e-mail i dokumentów.

4. Nastąpi przekierowanie do sklepu Google Play, z którego można pobrać aplikację Portal firmy, którą następnie należy zainstalować. Aplikacja pomaga w zabezpieczeniu i ochronie danych. <br/> ![Ilustracja przedstawiająca aplikację w sklepie Google Play](./media/google-play-get-app-android.png)
5. Po zakończeniu instalacji aplikacji wybierz pozycję **Akceptuj**, aby zaakceptować warunki. Nastąpi automatyczne uruchomienie aplikacji OneDrive dla Firm.


>[!NOTE]
>Zależnie od wymogów działu IT podczas kolejnej próby otwarcia aplikacji OneDrive dla Firm może zostać wyświetlony monit o ustawienie kodu PIN. Po ustawieniu i potwierdzeniu kodu PIN można przejść do aplikacji OneDrive dla Firm.

![Ilustracja przedstawiająca monit o podanie kodu PIN](./media/pin-prompt-android.png)


<!--- Original steps: 6. The next time you open OneDrive for Business, you may be asked to set a PIN, if your IT requires one to use the OneDrive for Business app. ART 7. After you set and confirm the PIN, you can continue on to OneDrive for Business. -->

## <a name="what-policies-does-this-wizard-set"></a>Jakie zasady można ustawić, korzystając z tego kreatora?
|     |       | |
|----|--------|-|
|**Nazwa**|Zarządzaj aplikacjami usługi Office 365| |
| **Opis**|Utworzona z użyciem kreatora Zarządzaj aplikacjami usługi Office 365| |
| |  | |
| **Nazwa ustawienia** |**Wartość zasady dla systemu iOS** | **Wartość zasady dla systemu Android** |
|Zapobiegaj tworzeniu kopii zapasowych w programach iTunes i iCloud| Nie | Brak |
|Blokuj kopie zapasowe systemu Android |Brak | Nie|
|Zezwalaj aplikacji na transfer danych do innych aplikacji | Wszystkie aplikacje | Wszystkie aplikacje|
|Zezwalaj aplikacji na odbieranie danych z innych aplikacji| Wszystkie aplikacje | Wszystkie aplikacje|
|Nie zezwalaj na używanie polecenia „Zapisz jako” | Nie | Nie|
|Ogranicz wycinanie, kopiowanie i wklejanie w innych aplikacjach | Dowolna aplikacja | Dowolna aplikacja |
|Ogranicz zawartość sieci Web wyświetlaną w zarządzanej przeglądarce firmowej | Nie| Nie|
|Szyfruj dane aplikacji | Gdy urządzenie jest zablokowane | Tak|
|Wyłącz synchronizowanie kontaktów | Nie| Nie|
|Wyłącz drukowanie | Nie | Nie|
|Wymagaj numeru PIN w celu udzielenia dostępu | Nie | Tak|
|Liczba prób przed zresetowaniem numeru PIN | Brak |5|
|Zezwalaj na prosty numer PIN | Brak |Tak|
|Długość numeru PIN | Brak | 4|
|Zezwalaj na odcisk palca zamiast numeru PIN | Brak | Tak |
|Wymagaj poświadczeń firmowych w celu udzielenia dostępu | Nie | Nie|
|Blokuj uruchamianie aplikacji zarządzanych na urządzeniach, na których zdjęto zabezpieczenia systemu lub uzyskano dostęp do konta root | Nie | Nie|
|Ponownie sprawdź wymagania dostępu po (w minutach) — limit czasu | 30 | 30|
|Ponownie sprawdź wymagania dostępu po (w minutach) — okres karencji w trybie offline | 720 |720|
|Interwał przebywania w trybie offline (w dniach) przed wyczyszczeniem danych aplikacji | 90 | 90|
|Zablokuj przechwytywanie ekranu (tylko urządzenia z systemem Android) | Brak | Nie |

### <a name="why-is-an-app-pin-policy-only-configured-for-android-devices"></a>Dlaczego zasada aplikacji dotycząca numeru PIN jest skonfigurowana tylko dla urządzeń z systemem Android?
Szyfrowanie przebiega inaczej w systemach iOS i Android.

W systemie iOS w przypadku aplikacji, które zostały skojarzone z zasadami zarządzania aplikacjami mobilnymi usługi Intune, nieużywane dane są szyfrowane za pomocą funkcji szyfrowania na poziomie urządzenia udostępnianej przez system operacyjny. Po włączeniu zasady szyfrowania aplikacji zostaje więc automatycznie ustawiony także wymóg posiadania i wprowadzenia przez użytkownika numeru PIN w celu uzyskiwania dostępu do danych służbowych. Użytkownicy, którzy nie skonfigurowali jeszcze numeru PIN na urządzeniu, otrzymają monit o utworzenie numeru PIN urządzenia.

W systemie Android w przypadku aplikacji, które zostały skojarzone z zasadami zarządzania aplikacjami mobilnymi usługi Intune, dane są szyfrowane synchronicznie podczas zadań wejścia/wyjścia na plikach. Zawartość w pamięci urządzenia jest zawsze zaszyfrowana. Na urządzeniach, które nie są zarządzane przez system MDM, zasada zarządzania aplikacjami mobilnymi nie może narzucić wymogu użycia numeru PIN urządzenia. Aby zagwarantować, że użytkownicy muszą użyć jakiegoś kodu PIN w celu uzyskania dostępu do danych służbowych, kreator umożliwia zastosowanie zasady numeru PIN aplikacji.

Ustawienia zasady można w dowolnym momencie edytować w celu jej dostosowania do wymagań organizacji.

### <a name="how-can-i-view-and-edit-the-policies-created-by-the-wizard"></a>Jak wyświetlić i edytować zasady utworzone przez kreatora?
Aby wyświetlić lub zaktualizować powyższe zasady lub dowolne inne zasady utworzone w wersji zapoznawczej usługi Intune Azure, z poziomu pulpitu nawigacyjnego wybierz kolejno pozycje **Zarządzaj aplikacjami** > **Zasady ochrony aplikacji**. Po prawej stronie zostanie otwarta lista zasad. Wybierz zasadę, którą chcesz wyświetlić, aby sprawdzić i edytować ustawienia. <br/>
![Ilustracja przedstawiająca ścieżkę interfejsu użytkownika umożliwiającą wyświetlenie zasad](./media/image-for-faq.png)

## <a name="next-steps"></a>Następne kroki
Dowiedz się więcej o [zasadach ochrony aplikacji](https://docs.microsoft.com/intune-azure/manage-apps/what-is-app-protection-policy).



<!--HONumber=Feb17_HO1-->


