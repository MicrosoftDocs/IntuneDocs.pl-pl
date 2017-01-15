---
title: "Zarządzanie programem DEP firmy Apple dla urządzeń z systemem iOS | Microsoft Docs"
description: "Aby zarządzać urządzeniami firmy Apple, wdróż profil rejestracji służący do bezprzewodowego rejestrowania urządzeń z systemem iOS zakupionych w ramach programu Device Enrollment Program (DEP)."
keywords: 
author: staciebarker
ms.author: stabar
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8ff9d9e7-eed8-416c-8508-efc20fca8578
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: f8f5c1e5d69cf91413ebc4a71f1f9f8f8e1c8231


---

# <a name="enroll-corporate-owned-device-enrollment-program-ios-devices"></a>Rejestrowanie firmowych urządzeń z systemem iOS przy użyciu Device Enrollment Program
Usługa Microsoft Intune może wdrożyć profil rejestracji, który będzie bezprzewodowo rejestrować urządzenia z systemem iOS zakupione w ramach programu Device Enrollment Program (DEP). Pakiet rejestracyjny może obejmować opcje Asystenta ustawień dla urządzenia. Użytkownicy nie mogą wyrejestrowywać urządzeń zarejestrowanych w programie DEP.

## <a name="apple-dep-management-for-ios-devices-with-microsoft-intune"></a>Zarządzanie programem DEP firmy Apple dla systemu iOS przy użyciu usługi Microsoft Intune
W celu zarządzania firmowymi urządzeniami z systemem iOS przy użyciu programu Device Enrollment Program (DEP) firmy Apple organizacja musi dołączyć do programu DEP firmy Apple i zakupić urządzenia w ramach tego programu. Szczegóły tego procesu są dostępne pod adresem:  [https://deploy.apple.com](https://deploy.apple.com). Zalety programu obejmują funkcje bezobsługowego konfigurowania urządzeń bez konieczności podłączania poszczególnych urządzeń do komputera przy użyciu kabla USB.

Aby zarejestrować firmowe urządzenia z systemem iOS w programie DEP, należy uzyskać token programu DEP od firmy Apple. Token umożliwia usłudze Intune synchronizację informacji dotyczących urządzeń uczestniczących w programie DEP należących do firmy. Umożliwia on również usłudze Intune przekazywanie profilów rejestracji do firmy Apple i przypisywanie urządzeń do tych profilów.

1.  **Rozpocznij zarządzanie urządzeniami z systemem iOS przy użyciu usługi Microsoft Intune**</br>
    Aby móc rejestrować urządzenia z systemem iOS w programie Device Enrollment Program (DEP), musisz zakończyć włączanie zarządzania systemem iOS dla usługi Intune.

2.  **Pobierz klucz szyfrowania**</br>
    Jako użytkownik administracyjny otwórz [konsolę administracyjną usługi Microsoft Intune](http://manage.microsoft.com), kliknij pozycję **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **iOS** &gt; **Device Enrollment Program**, a następnie wybierz pozycję **Pobierz klucz szyfrowania**. Zapisz lokalnie plik klucza szyfrowania (PEM) Plik PEM jest używany na potrzeby żądania certyfikatu relacji zaufania z portalu programu Device Enrollment Program firmy Apple.

      ![Aktualizacja tokenu programu Device Enrollment Program](../media/dev-sa-ios-dep.png)

3.  **Pobierz token programu Device Enrollment Program**</br>
    Przejdź do [portalu Device Enrollment Program](https://deploy.apple.com) (https://deploy.apple.com) i zaloguj się przy użyciu identyfikatora Apple ID swojej firmy. Tego identyfikatora firmy Apple należy używać w przyszłości do odnawiania tokenu programu DEP.

    1.  W [portalu Device Enrollment Program](https://deploy.apple.com) wybierz pozycje **Device Enrollment Program** &gt; **Manage Servers** (Zarządzanie serwerami), a następnie wybierz pozycję **Add MDM Server** (Dodaj serwer MDM).

    2.  Wprowadź nazwę serwera w polu **MDM Server Name** (Nazwa serwera MDM), a następnie wybierz przycisk **Next**(Dalej). Nazwa serwera służy użytkownikowi do identyfikowania serwera MDM. Nie jest to nazwa ani adres URL serwera usługi Microsoft Intune.

    3.  Zostanie otwarte okno dialogowe **Add &lt;nazwa_serwera&gt;** (Dodawanie serwera <nazwa_serwera>). Kliknij pozycję **Choose File…** (Wybierz plik...) w celu przekazania pliku PEM, a następnie kliknij przycisk **Next** (Dalej).

    4.  W oknie dialogowym **Add&lt; <nazwa_serwera>&gt;** (Dodawanie serwera <nazwa_serwera>) zostanie wyświetlony link **Your Server Token** (Token serwera). Pobierz plik tokenu serwera (p7m) na komputer, a następnie wybierz pozycję **Done**(Gotowe).

    Ten plik certyfikatu (p7m) służy do ustanawiania relacji zaufania między serwerami usługi Intune i programu Device Enrollment Program firmy Apple.

4.  **Dodaj token programu DEP do usługi Intune**</br>
    W [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) wybierz pozycję **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **iOS** &gt; **Device Enrollment Program**, a następnie kliknij pozycję **Przekaż token DEP**. **Przejdź** do pliku certyfikatu (p7m), wprowadź swój identyfikator **Apple ID** i wybierz pozycję **Przekaż**.

5.  **Dodaj zasady rejestracji urządzeń firmowych**</br>
    W [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) wybierz pozycję **Zasady** &gt; **Rejestracja urządzeń firmowych**, a następnie wybierz pozycję **Dodaj**.

    Podaj **ogólne** informacje, takie jak **Nazwa** i **Opis**, oraz określ, czy urządzenia przypisane do tego profilu pozostają w koligacji z użytkownikiem, czy też należą do grupy.
      - **Monituj o koligację użytkownika** — podczas początkowej konfiguracji należy określić przynależność urządzenia do użytkownika przed udzieleniem zezwolenia na dostęp tego urządzenia do danych firmowych i poczty e-mail jako ten użytkownik. **Koligację użytkownika** należy skonfigurować dla urządzeń zarządzanych w programie DEP, które należą do użytkowników i muszą korzystać z portalu firmy (tj. w celu instalowania aplikacji). Uwierzytelnianie wieloskładnikowe (MFA) nie działa podczas rejestracji urządzeń za pomocą programu DEP, gdy jest używana koligacja użytkownika. Po zarejestrowaniu tych urządzeń uwierzytelnianie wieloskładnikowe działa zgodnie z oczekiwaniami. 

      > [!NOTE]
      > Program DEP z koligacją użytkownika wymaga nazwy użytkownika protokołu WS-Trust 1.3/mieszanego punktu końcowego, aby móc żądać tokenu użytkownika.

      - **Brak koligacji użytkownika:** urządzenie nie zostało powiązane z użytkownikiem. Tego typu przynależności należy użyć w przypadku urządzeń wykonujących zadania bez uzyskiwania dostępu do danych użytkowników lokalnych. Aplikacje wymagające koligacji użytkownika, w tym aplikacja Portal firmy użyta do zainstalowania aplikacji biznesowych, nie będą działać.

    Możesz także **przypisać urządzenia do następującej grupy**. Kliknij pozycję **Wybierz...**, aby wybrać grupę.

    [!INCLUDE[groups deprecated](../includes/group-deprecation.md)]

    Następnie włącz opcję **Skonfiguruj ustawienia programu rejestracji urządzeń dla tych zasad** w celu obsługi programu DEP.

      ![Okienko Asystenta ustawień](../media/pol-sa-corp-enroll.png)

     Dla urządzeń zarządzanych w programie DEP dostępne są następujące ustawienia:

     - **Dział** — wyświetlane, gdy użytkownicy nacisną pozycję **Informacje o konfiguracji** podczas aktywacji
     - **Numer telefonu pomocy technicznej** — wyświetlane, gdy użytkownik kliknie przycisk **Potrzebna pomoc** podczas aktywacji
     - **Tryb przygotowania** — stan ustawiany podczas aktywacji bez możliwości jego zmiany bez zresetowania urządzenia do ustawień fabrycznych:
        - **Nienadzorowane** — ograniczone możliwości zarządzania
        - **Nadzorowane** — włącza więcej opcji zarządzania i domyślnie wyłącza blokadę aktywacji
     - **Zablokuj profil rejestracji dla urządzenia** — stan ustawiany podczas aktywacji bez możliwości jego zmiany bez zresetowania urządzenia do ustawień fabrycznych
        - **Wyłącz** — umożliwia usunięcie profilu zarządzania z poziomu menu **Ustawienia**
        - **Włącz** — (wymaga, aby ustawienie **Tryb przygotowania** = **Nadzorowane**) — wyłącza ustawienia systemu iOS, które umożliwiają usunięcie profilu zarządzania
     - **Opcje Asystenta ustawień** — te opcjonalne ustawienia mogą być później konfigurowane z poziomu menu **Ustawienia** systemu iOS.
        - **Kod dostępu** — wyświetla monit o podanie kodu dostępu podczas aktywacji. Zawsze należy wymagać kodu dostępu, chyba że urządzenie zostanie zabezpieczone lub dostęp do niego będzie kontrolowany w inny sposób (tj. tryb kiosku, który ogranicza możliwość użycia urządzenia do jednej aplikacji).
        - **Usługi lokalizacji** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący usługi podczas aktywacji
        - **Przywracanie** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit o kopię zapasową w programie iCloud podczas aktywacji
        - **Apple ID** — jeśli to ustawienie zostało włączone, system iOS wyświetla monit o podanie identyfikatora Apple ID, gdy usługa Intune będzie podejmowała próbę zainstalowania aplikacji bez tego identyfikatora. Identyfikator Apple ID jest wymagany do pobierania aplikacji ze sklepu iOS App Store, w tym aplikacji zainstalowanych przez usługę Intune.
        - **Warunki i postanowienia** — jeśli to ustawienie zostało włączone, Asystent ustawień monituje użytkowników o zaakceptowanie warunków i postanowień firmy Apple podczas aktywacji
        - **Touch ID** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji
        - **Apple Pay** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji
        - **Zoom** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji
        - **Siri** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji
        - **Wyślij dane diagnostyczne do firmy Apple** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji
     -  **Zezwalaj na dodatkowe zarządzanie przy użyciu programu Apple Configurator** —ustawienie wartości **Nie zezwalaj** zapobiega synchronizowaniu plików za pomocą programu iTunes lub zarządzaniu przy użyciu programu Apple Configurator. Zalecane jest ustawienie na wartość **Nie zezwalaj**, wyeksportowanie dalszej konfiguracji z programu Apple Configurator, a następnie wdrożenie jako niestandardowego profilu konfiguracji systemu iOS za pomocą usługi Intune, a nie używanie tego ustawienia w celu zezwolenia na ręczne wdrożenie z użyciem lub bez użycia certyfikatu.
        - **Nie zezwalaj** — uniemożliwia urządzeniu komunikację za pomocą połączenia USB (wyłącza parowanie)
        - **Zezwalaj** — umożliwia urządzeniu komunikację za pomocą połączenia USB z dowolnym komputerem PC lub Mac
        - **Wymagaj certyfikatu** — umożliwia parowanie z komputerem Mac przy użyciu certyfikatu zaimportowanego do profilu rejestracji

6.  **Przypisz urządzenia DEP do zarządzania**. Przejdź do [portalu Device Enrollment Program](https://deploy.apple.com) (https://deploy.apple.com) i zaloguj się przy użyciu identyfikatora Apple ID Twojej firmy. Wybierz kolejno pozycje **Deployment Program** (Program wdrażania) &gt; **Device Enrollment Program** (Program rejestracji urządzeń) &gt; **Manage Devices** (Zarządzanie urządzeniami). Określ sposób **wyboru urządzeń**, podaj informacje o urządzeniach i określ szczegóły według numeru seryjnego (**Serial Number**) urządzenia, numeru zamówienia (**Order Number**) lub przekaż plik CSV (**Upload CSV File**). Następnie wybierz pozycję **Assign to Server** (Przypisz do serwera), wybierz nazwę serwera &lt;nazwa_serwera&gt; określoną dla usługi Microsoft Intune, a następnie kliknij przycisk **OK**.

7.  **Synchronizuj urządzenia zarządzane w programie DEP**. Jako użytkownik administracyjny otwórz [konsolę administracyjną usługi Microsoft Intune](http://manage.microsoft.com), przejdź do pozycji **Administracja** &gt; **Zarządzanie urządzeniami przenośnymi** &gt; **iOS** &gt; **Device Enrollment Program**, a następnie kliknij pozycję **Synchronizuj teraz**. Żądanie synchronizacji zostanie wysłane do firmy Apple. Aby wyświetlić urządzenia zarządzane przez program DEP po synchronizacji, w [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) wybierz pozycję **Grupy** &gt; **Wszystkie urządzenia** &gt; **Wstępnie zarejestrowane urządzenia należące do firmy** &gt; **Według numeru seryjnego systemu iOS**. W obszarze roboczym **Według numeru seryjnego systemu iOS** dla zarządzanych urządzeń wyświetlany jest **stan** „Nie nawiązano komunikacji”, dopóki urządzenie nie zostanie włączone i Asystent ustawień nie zostanie uruchomiony w celu zarejestrowania urządzenia.

    Aby spełnić warunki ruchu programu DEP firmy Apple, usługa Intune nakłada następujące ograniczenia:
     -  Pełną synchronizację programu DEP można uruchamiać nie częściej niż co siedem dni. Podczas pełnej synchronizacji usługa Intune odświeża każdy numer seryjny Apple przypisany do usługi Intune, niezależnie od tego, czy numer seryjny był już wcześniej synchronizowany. W przypadku próby przeprowadzenia pełnej synchronizacji przed upływem siedmiu dni od poprzedniej pełnej synchronizacji usługa Intune odświeża tylko numery seryjne, które jeszcze nie zostały przypisane do usługi Intune.
     -  Każde żądanie synchronizacji ma przydzielone 10 minut na zakończenie. W tym czasie lub do momentu zakończenia żądania powodzeniem przycisk **synchronizacji** jest wyłączony.

8.  **Dystrybuuj urządzenia do użytkowników**. Urządzenia firmowe mogą zostać teraz przekazane użytkownikom. Po włączeniu urządzenia z systemem iOS zostanie ono zarejestrowane na potrzeby zarządzania przez usługę Intune.

## <a name="changes-to-intune-group-assignments"></a>Zmiany przypisań grup usługi Intune

Od listopada zarządzanie grupami urządzeń zostanie przeniesione do usługi Azure Active Directory. Po przejściu do grup usługi Azure Active Directory przypisanie do grupy nie będzie wyświetlane w opcjach **profilu rejestracji w firmie**. Ponieważ ta zmiana będzie wprowadzana przez szereg miesięcy, może nie być widoczna od razu. Po przejściu do nowego portalu dynamiczne przypisania grup urządzeń będzie można definiować na podstawie nazw profili rejestracji w firmie. Ten proces zapewnia, że urządzenia przypisane do grupy urządzeń zostaną automatycznie zarejestrowane w grupie z wdrożonymi zasadami i aplikacjami. [Dowiedz się więcej o grupach usługi Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/)

### <a name="see-also"></a>Zobacz także
[Wymagania wstępne dotyczące rejestrowania urządzeń](prerequisites-for-enrollment.md)



<!--HONumber=Dec16_HO2-->


