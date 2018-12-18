---
title: Ustawienia urządzeń z systemem Android Enterprise w usłudze Microsoft Intune — Azure | Microsoft Docs
description: W urządzeniach z systemem Android Enterprise lub Android for Work możesz ograniczyć ustawienia, w tym kopiowanie i wklejanie, pokazywanie powiadomień, uprawnienia aplikacji, udostępnianie danych, długość hasła, błędy logowania, używanie odcisku palca do odblokowywania, ponowne używanie haseł oraz włączanie udostępniania kontaktów służbowych za pomocą technologii Bluetooth. Konfiguruj urządzenia jako kiosk w celu uruchamiania jednej aplikacji lub wielu aplikacji.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seodec18
ms.openlocfilehash: c9e2e0df79625329310171c509327395989f3a7c
ms.sourcegitcommit: fff179f59bd542677cbd4bf3bacc24bb880e2cb6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/07/2018
ms.locfileid: "53032541"
---
# <a name="android-enterprise-device-settings-to-allow-or-restrict-features-using-intune"></a>Ustawienia urządzeń z systemem Android Enterprise w celu zezwolenia na funkcje lub ich ograniczenia przy użyciu usługi Intune

W tym artykule wymieniono i opisano różne ustawienia, którymi można sterować na urządzeniach z systemem Android Enterprise. Użyj tych ustawień w ramach swojego rozwiązania do zarządzania urządzeniami mobilnymi (MDM), aby zezwalać na działanie funkcji lub je wyłączać, uruchamiać aplikacje w trybie kiosku, kontrolować zabezpieczenia i nie tylko.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia](device-restrictions-configure.md).

## <a name="device-owner-only"></a>Tylko właściciel urządzenia

### <a name="general-settings"></a>Ustawienia ogólne

- **Przechwytywanie ekranu**: wybierz pozycję **Blokuj**, aby uniemożliwić tworzenie zrzutów ekranu i przechwytywanie ekranów w urządzeniu. Zapobiega również wyświetlaniu zawartości na urządzeniach wyświetlających, które nie mają zabezpieczonego wyjścia wideo. Pozycja **Nieskonfigurowane** umożliwia użytkownikowi przechwytywanie zawartości ekranu w formie obrazu.
- **Aparat fotograficzny**: wybierz pozycję **Blokuj**, aby uniemożliwić dostęp do aparatu na urządzeniu. Pozycja **Niewymagane** zezwala na dostęp do aparatu urządzenia.
- **Domyślne zasady uprawnień**: to ustawienie określa domyślne zasady uprawnień dla żądań uprawnień w środowisku uruchomieniowym. Dopuszczalne wartości to:
  - **Ustawienie domyślne urządzenia**: zostaną użyte ustawienia domyślne urządzenia.
  - **Monituj**: użytkownik jest monitowany o zatwierdzenie uprawnienia.
  - **Automatyczne udzielaj**: uprawnienia są automatycznie udzielane.
  - **Automatyczne odmawiaj**: następuje automatyczna odmowa udzielenia uprawnień.
- **Zmiany daty i godziny**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom ręczne ustawianie daty i godziny. Pozycja **Nieskonfigurowane** umożliwia użytkownikom ustawianie określonej daty i godziny na urządzeniu.
- **Zmiany głośności**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom zmienianie głośności urządzenia. Pozycja **Nieskonfigurowane** umożliwia korzystanie z ustawień głośności na urządzeniu.
- **Resetowanie do ustawień fabrycznych**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom używanie opcji resetowania do ustawień fabrycznych w ustawieniach urządzenia. Pozycja **Nieskonfigurowane** pozwala użytkownikom na używanie tego ustawienia na urządzeniu.
- **Bezpieczny rozruch**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom ponowne uruchamianie urządzenia w trybie awaryjnym. Pozycja **Nieskonfigurowane** pozwala użytkownikom na ponowne uruchamianie urządzenia w trybie awaryjnym.
- **Pasek stanu**: wybierz pozycję **Blokuj**, aby uniemożliwić dostęp do paska stanu, w tym do powiadomień i szybkich ustawień. Pozycja **Nieskonfigurowane** zezwala użytkownikom na dostęp do paska stanu.
- **Usługi roamingu danych**: wybierz pozycję **Blokuj**, aby uniemożliwić roaming danych w sieci komórkowej. Pozycja **Nieskonfigurowane** zezwala na roaming danych, gdy urządzenie jest w sieci komórkowej.
- **Zmiany ustawień sieci Wi-Fi**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom zmienianie ustawień sieci Wi-Fi utworzonych przez właściciela urządzenia. Użytkownicy mogą tworzyć własne konfiguracje sieci Wi-Fi. Pozycja **Nieskonfigurowane** umożliwia użytkownikom zmianę ustawień sieci Wi-Fi na urządzeniu.
- **Konfiguracja punktu dostępu sieci Wi-Fi**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom tworzenie lub zmienianie konfiguracji sieci Wi-Fi. Pozycja **Nieskonfigurowane** umożliwia użytkownikom zmianę ustawień sieci Wi-Fi na urządzeniu.
- **Konfiguracja połączenia Bluetooth**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom konfigurowanie połączenia Bluetooth na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia używanie połączenia Bluetooth na urządzeniu.
- **Udostępnianie kontaktów za pośrednictwem połączenia Bluetooth**: wybierz pozycję **Blokuj**, aby uniemożliwić dostęp do kontaktów służbowych z innego urządzenia, takiego jak system samochodowy, gdy urządzenie z systemem Android zostanie sparowane za pomocą połączenia Bluetooth. Pozycja **Nieskonfigurowane** zezwala na dostęp do kontaktów służbowych na innym urządzeniu Bluetooth, które zostało sparowane z urządzeniem z systemem Android.
- **Tethering i dostęp do hotspotów**: wybierz pozycję **Blokuj**, aby uniemożliwić tethering i uzyskiwanie dostępu do przenośnych hotspotów. Pozycja **Nieskonfigurowane** zezwala na tethering i dostęp do przenośnych hotspotów.
- **Pamięć USB**: wybierz pozycję **Zezwalaj**, aby uzyskiwać dostęp do pamięci USB na urządzeniu. Pozycja **Nieskonfigurowane** uniemożliwia dostęp do pamięci USB.
- **Transfer plików USB**: wybierz pozycję **Blokuj**, aby uniemożliwić przesyłanie plików za pośrednictwem USB. Pozycja **Nieskonfigurowane** pozwala na transfer plików.
- **Nośniki zewnętrzne**: wybierz pozycję **Blokuj**, aby uniemożliwić korzystanie z nośników zewnętrznych i łączenie się z nimi na urządzeniu. Pozycja **Nieskonfigurowane** zezwala na użycie nośników zewnętrznych na urządzeniu.
- **Przesyłaj dane za pomocą komunikacji NFC**: wybierz pozycję **Blokuj**, aby uniemożliwić używanie technologii NFC (Near Field Communication) do przesyłania danych z aplikacji. Pozycja **Nieskonfigurowane** umożliwia używanie technologii NFC do udostępniania danych między urządzeniami.
- **Funkcje debugowania**: wybierz pozycję **Zezwalaj**, aby umożliwić użytkownikom korzystanie z funkcji debugowania na urządzeniu. Pozycja **Nieskonfigurowane** uniemożliwia użytkownikom korzystanie z funkcji debugowania na urządzeniu.
- **Dostosowanie mikrofonu**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom wyłączanie wyciszania mikrofonu i dostosowywanie jego głośności. Pozycja **Nieskonfigurowane** umożliwia użytkownikom używanie i dostosowywanie głośności mikrofonu na urządzeniu.
- **Adresy e-mail ochrony dotyczącej resetowania do ustawień fabrycznych**: wybierz pozycję **Adresy e-mail konta Google**. Wprowadź adresy e-mail administratorów urządzenia, którzy mogą je odblokować po wyczyszczeniu zawartości. Pamiętaj, aby oddzielić adresy e-mail średnikami w następujący sposób: `admin1@gmail.com;admin2@gmail.com`. Jeśli nie wprowadzono adresu e-mail, każda osoba może odblokować urządzenie po przywróceniu go do ustawień fabrycznych.
- **Wyjście bezpieczeństwa sieci**: wybierz pozycję **Włącz**, aby umożliwić użytkownikom włączanie funkcji wyjścia bezpieczeństwa sieci. Jeśli podczas uruchamiania urządzenia nie nawiązano połączenia sieciowego, wyjście bezpieczeństwa wyświetli prośbę o tymczasowe połączenie z siecią i odświeżenie zasad urządzenia. Po zastosowaniu zasad sieć tymczasowa zostanie zapomniana, a urządzenie będzie kontynuować rozruch. Ta funkcja powoduje połączenie urządzeń z siecią, jeśli:
  - W ostatnich zasadach nie ma odpowiedniej sieci.
  - Urządzenie jest uruchamiane w aplikacji w trybie blokady zadania.
  - Użytkownik nie może używać ustawień urządzenia.

  Pozycja **Nieskonfigurowane** uniemożliwia użytkownikom włączanie funkcji wyjścia bezpieczeństwa sieci na urządzeniu.

- **Zezwalaj na instalację z nieznanych źródeł**: wybierz pozycję **Zezwalaj**, aby użytkownicy mogli włączać opcję **Nieznane źródła**. To ustawienie umożliwia instalowanie aplikacji z nieznanych źródeł. Pozycja **Nieskonfigurowane** uniemożliwia użytkownikom włączanie opcji **Nieznane źródła**.
- **Aktualizacja systemu**: wybierz opcję, aby określić sposób obsługi aktualizacji bezprzewodowych przez urządzenie:
  - **Ustawienie domyślne urządzenia**: zostaną użyte ustawienia domyślne urządzenia.
  - **Automatyczne**: aktualizacje są automatycznie instalowane bez interakcji z użytkownikiem. Ustawienie tych zasad powoduje natychmiastowe instalowanie wszystkich oczekujących aktualizacji.
  - **Odłożone**: instalowanie aktualizacji jest odkładane o 30 dni. Po upływie tych 30 dni system Android monituje użytkownika o zainstalowanie aktualizacji. Producenci urządzeń i operatorzy mogą uniemożliwiać (wykluczać) odkładanie ważnych aktualizacji zabezpieczeń. Aktualizacja podlegająca takiemu wykluczeniu powoduje wyświetlenie użytkownikowi powiadomienia systemowego na urządzeniu. 
  - **Okno obsługi**: aktualizacje są instalowane automatycznie w ramach codziennego okna obsługi skonfigurowanego w usłudze Intune. Próba instalacji jest podejmowana codziennie przez 30 dni i może zakończyć się niepowodzeniem ze względu na brak miejsca lub niski poziom baterii. Po upływie 30 dni system Android monituje użytkownika o instalację. To okno jest też używane do instalowania aktualizacji aplikacji ze sklepu Play. Tej opcji należy używać w przypadku urządzeń dedykowanych, takich jak kioski, ponieważ umożliwia ona aktualizowanie aplikacji na pierwszym planie kiosków z pojedynczymi aplikacjami.
- **Automatyczne aktualizacje aplikacji**: wybierz moment instalowania aktualizacji automatycznych. Dostępne opcje:
  - **Nieskonfigurowany**
  - **Wybór użytkownika**
  - **Nigdy**
  - **Tylko sieć Wi-Fi**
  - **Zawsze**

### <a name="system-security-settings"></a>Ustawienia zabezpieczeń systemu

- **Skanowanie aplikacji pod kątem zagrożeń**: pozycja **Wymagaj** wymusza włączenie ustawienia **Weryfikuj aplikacje** w profilach służbowych i osobistych.

### <a name="kiosk-settings"></a>Ustawienia kiosku

Urządzenie można skonfigurować do uruchamiania pojedynczej aplikacji lub wielu aplikacji. Gdy urządzenie jest w trybie kiosku, dostępne są tylko dodane aplikacje.

**Tryb kiosku**: wybierz, czy na urządzeniu będzie uruchamiana jedna, czy wiele aplikacji.

- **Kiosk z pojedynczą aplikacją**: użytkownicy mogą uzyskiwać dostęp tylko do jednej aplikacji na urządzeniu. Po uruchomieniu urządzenia zostanie uruchomiona tylko określona aplikacja. Użytkownicy nie mogą otwierać nowych aplikacji ani zmieniać uruchomionej aplikacji.

  **Kroki**
  1. Wybierz pozycję **Wybierz zarządzaną aplikację**, a następnie wybierz z listy zarządzaną aplikację ze sklepu Google Play. 

      Jeśli nie masz listy aplikacji, [dodaj wybrane aplikacje dla systemu Android](apps-add-android-for-work.md) do urządzenia. Pamiętaj, aby [przypisać aplikację do grupy urządzeń utworzonej na potrzeby urządzeń kiosku](apps-deploy.md).

  2. Wybierz przycisk **OK** > **OK**, aby dodać aplikację.

- **Kiosk z wieloma aplikacjami**: użytkownicy mogą uzyskiwać dostęp do ograniczonego zestawu aplikacji na urządzeniu. Po uruchomieniu urządzenia zostaną uruchomione tylko dodane aplikacje. Można również dodać linki internetowe, które użytkownicy będą mogli otwierać. Po zastosowaniu zasad użytkownicy widzą ikony dozwolonych aplikacji na ekranie głównym.

  > [WAŻNE] W przypadku urządzeń kiosku z wieloma aplikacjami [aplikacja Zarządzany ekran główny](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise) ze sklepu Google Play **musi zostać**:
  >   - [Dodana jako aplikacja kliencka](apps-add-android-for-work.md) w usłudze Intune
  >   - [Przypisana do grupy urządzeń](apps-deploy.md) utworzonej na potrzeby urządzeń kiosku
  > 
  > Aplikacja **Zarządzany ekran główny** nie musi znajdować się w profilu konfiguracji, ale trzeba ją dodać jako aplikację kliencką. Gdy aplikacja **Zarządzany ekran główny** zostanie dodana jako aplikacja kliencka, wszystkie inne aplikacje dodane w profilu konfiguracji będą wyświetlane jako ikony w aplikacji **Zarządzany ekran główny**. 

  - Wybierz pozycję **Dodaj** i wybierz aplikacje z listy.

    Jeśli na liście nie ma aplikacji **Zarządzany ekran główny**, [dodaj ją ze sklepu Google Play](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise). Pamiętaj, aby [przypisać aplikację](apps-deploy.md) do grupy urządzeń utworzonej na potrzeby urządzeń kiosku.

    Na urządzeniu możesz również dodać inne [aplikacje dla systemu Android](apps-add-android-for-work.md) i [aplikacje internetowe](web-app.md) utworzone przez organizację. Pamiętaj, aby [przypisać aplikację do grupy urządzeń utworzonej na potrzeby urządzeń kiosku](apps-deploy.md).

  - **Wirtualny przycisk ekranu głównego**: wybierz pozycję **Włącz**, aby przycisk ekranu głównego był wyświetlany na urządzeniach kiosku. Po wybraniu tego przycisku użytkownik wróci na ekran główny urządzenia. Ułatwia to użytkownikom przełączanie między aplikacjami. Na niektórych urządzeniach z systemem Android użytkownicy będą musieli przesunąć ekran w górę, aby przycisk ekranu głównego został wyświetlony. Pozycja **Wyłącz** powoduje, że przycisk ekranu głównego nie pojawia się, a użytkownicy muszą używać przycisku Wstecz do przełączania się między aplikacjami.
  - **Wyjdź z trybu kiosku**: wybierz pozycję **Włącz**, aby umożliwić administratorom tymczasowe wstrzymywanie trybu kiosku w celu zaktualizowania urządzenia. Aby skorzystać z tej funkcji, administrator wykonuje następujące czynności: 
  
    1. Wybiera przycisk Wstecz do momentu wyświetlenia przycisku „Wyjdź z kiosku”. 
    2. Wybiera przycisk, a następnie wprowadza numer PIN dla opcji **Kod wychodzenia z trybu kiosku**.
    3. Po zakończeniu wprowadzania zmian wybiera aplikację **Zarządzany ekran główny**. Ten krok powoduje ponowne zablokowanie urządzenia w trybie kiosku z wieloma aplikacjami. 
    
    Pozycja **Wyłącz** nie oferuje możliwości wstrzymywania trybu kiosku. Jeśli administrator wybiera przycisk Wstecz, a następnie przycisk „Wyjdź z kiosku”, pojawia się komunikat z informacją o tym, że kod dostępu jest wymagany.
    
    - **Kod wychodzenia z trybu kiosku**: wprowadź liczbowy kod PIN zawierający 4–6 cyfr. Administrator używa tego numeru PIN do tymczasowego wstrzymywania trybu kiosku.
 
  - **Ustaw tło przy użyciu niestandardowego adresu URL**: wprowadź adres URL, aby dostosować ekran tła na urządzeniu kiosku.

### <a name="device-password-settings"></a>Ustawienia haseł urządzeń

- **Blokada klawiatury**: wybierz pozycję **Wyłącz**, aby uniemożliwić użytkownikom używanie funkcji blokady ekranu Blokada klawiatury na urządzeniu. Pozycja **Nieskonfigurowane** zezwala użytkownikowi na korzystanie z funkcji blokady klawiatury.
- **Wymagany typ hasła**: określ typ hasła wymagany dla urządzenia. Dostępne opcje:
  - **Co najmniej numeryczne**
  - **Złożona wartość liczbowa**: powtarzające się lub kolejne cyfry, np. „1111” lub „1234”, są niedozwolone.
  - **Co najmniej alfabetyczne**
  - **Co najmniej alfanumeryczne**
  - **Co najmniej alfanumeryczne z symbolami**
- **Minimalna długość hasła**: wprowadź minimalną długość hasła, które musi podać użytkownik (od 4 do 16 znaków).
- **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia**: wprowadź liczbę dopuszczalnych nieudanych logowań przed wyczyszczeniem urządzenia (od 1 do 11).

### <a name="power-settings"></a>Ustawienia zasilania

- **Czas do zablokowania ekranu**: ustaw okres bezczynności przed zablokowaniem urządzenia.
- **Włączony ekran, gdy urządzenie jest podłączone**: wybierz źródła zasilania. Jeśli urządzenie będzie podłączone do jednego z nich, ekran urządzenia będzie włączony.

### <a name="users-and-accounts-settings"></a>Ustawienia użytkowników i kont

- **Dodawanie nowych użytkowników**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom dodawanie nowych użytkowników. Każdy użytkownik ma na urządzeniu obszar osobisty, który zawiera niestandardowe ekrany główne, konta, aplikacje i ustawienia. Pozycja **Nieskonfigurowane** umożliwia użytkownikom dodawanie innych użytkowników do urządzenia.
- **Usuwanie użytkownika**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom usuwanie użytkowników. Pozycja **Nieskonfigurowane** umożliwia użytkownikom usuwanie innych użytkowników z urządzenia.
- **Zmiany dotyczące konta**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom modyfikowanie kont. Pozycja **Nieskonfigurowane** umożliwia użytkownikom aktualizowanie kont użytkowników na urządzeniu.

## <a name="work-profile-only"></a>Tylko profil służbowy 

### <a name="work-profile-settings"></a>Ustawienia profilu służbowego

#### <a name="general"></a>Ogólne

- **Ogranicz kopiowanie i wklejanie między profilami służbowymi i osobistymi**: wybierz pozycję **Blokuj**, aby uniemożliwić kopiowanie i wklejanie między aplikacjami służbowymi i osobistymi. Pozycja **Nieskonfigurowane** umożliwia użytkownikom udostępnianie danych aplikacjom w profilu osobistym przy użyciu kopiowania i wklejania. 
- **Udostępnianie danych między profilami służbowym i osobistym**: wybierz, czy aplikacje w profilu służbowym mogą udostępniać dane aplikacjom w profilu osobistym. Możesz na przykład sterować akcjami udostępniania, takimi jak opcja **Udostępnij…**, w aplikacjach. w przeglądarce Chrome. To ustawienie nie ma zastosowania do zachowania schowka w zakresie kopiowania/wklejania. Opcje udostępniania:
  - **Domyślne ograniczenia udostępniania**: domyślne zachowanie urządzenia w zakresie udostępniania, które różni się w zależności od wersji systemu Android. Udostępnianie danych z profilu osobistego w profilu służbowym jest domyślnie dozwolone. Udostępnianie danych z profilu służbowego w profilu osobistym jest domyślnie zablokowane. To ustawienie zapobiega udostępnianiu danych z profilu służbowego w profilu osobistym. Firma Google nie blokuje udostępniania z profilu osobistego do profilu służbowego na urządzeniach z systemem w wersji 6.0 lub nowszej.
  - **Aplikacje w profilu służbowym mogą obsługiwać żądania udostępniania z profilu osobistego**: włącza wbudowaną funkcję systemu Android, która umożliwia udostępnianie danych z profilu osobistego w profilu służbowym. Gdy ta opcja jest włączona, żądanie udostępnienia z aplikacji w profilu osobistym umożliwi udostępnianie danych aplikacjom w profilu służbowym. Jest to domyślne ustawienie w przypadku urządzeń z systemem Android w wersji wcześniejszej niż 6.0.
  - **Zezwalaj na udostępnianie przez granice**: umożliwia udostępnianie przez granicę profilu służbowego w obu kierunkach. Po wybraniu tego ustawienia aplikacje w profilu służbowym mogą udostępniać dane niewskazanym aplikacjom w profilu osobistym. To ustawienie pozwala zarządzanym aplikacjom z profilu służbowego udostępniać dane aplikacjom w niezarządzanym obszarze urządzenia. Dlatego należy go używać ostrożnie.

- **Powiadomienia profilu służbowego przy zablokowanym urządzeniu**: pozwala określić, czy aplikacje z profilu służbowego mogą pokazywać dane w powiadomieniach, gdy urządzenie jest zablokowane. Pozycja **Blokuj** powoduje, że dane nie są wyświetlane. Pozycja **Nieskonfigurowane** powoduje wyświetlanie danych.
- **Domyślne uprawnienia aplikacji**: Powoduje ustawienie domyślnych zasad uprawnień dla wszystkich aplikacji w profilu służbowym. Począwszy od systemu Android 6, użytkownik jest monitowany o udzielenie określonych uprawnień wymaganych przez aplikacje, gdy aplikacja jest uruchamiana. To ustawienie zasad pozwala określić, czy użytkownicy są monitowani o nadanie uprawnień wszystkim aplikacjom w profilu służbowym. Można na przykład przypisać aplikację do profilu służbowego, który wymaga dostępu do lokalizacji. Standardowo aplikacja monituje użytkownika o zatwierdzenie lub odrzucenie dostępu aplikacji do lokalizacji. Należy użyć tych zasad, aby automatycznie udzielić uprawnień bez wyświetlania monitu, automatycznie odmówić uprawnień bez wyświetlania monitu lub pozwolić użytkownikowi końcowemu zdecydować. Wybierz spośród opcji:
  - **Ustawienie domyślne urządzenia**
  - **Monit**
  - **Automatyczne udzielaj**
  - **Automatyczne odmawiaj**

  Zasad konfiguracji aplikacji można także użyć do nadania uprawnień dla poszczególnych aplikacji (**Aplikacje klienckie** > **Zasady konfiguracji aplikacji**).

- **Dodawanie i usuwanie kont**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom końcowym ręczne dodawanie lub usuwanie kont w profilu służbowym. Na przykład w przypadku wdrożenia aplikacji Gmail w profilu służbowym systemu Android można uniemożliwić użytkownikom końcowym dodawanie i usuwanie kont w tym profilu służbowym. Pozycja **Nieskonfigurowane** zezwala na dodawanie kont w profilu służbowym.  

- **Udostępnianie kontaktów za pośrednictwem połączenia Bluetooth**: umożliwia dostęp do kontaktów służbowych z innego urządzenia, takiego jak samochód, sparowanego za pomocą połączenia Bluetooth. Domyślnie to ustawienie nie jest skonfigurowane i kontakty służbowe nie są wyświetlane. Wybierz pozycję **Włącz**, aby zezwolić na udostępnianie i wyświetlić kontakty z profilu służbowego. To ustawienie dotyczy urządzeń z systemem Android w wersji 6.0 i nowszych oraz profilem służbowym. Włączenie tego ustawienia może umożliwić niektórym urządzeniom Bluetooth zapisanie w pamięci podręcznej kontaktów służbowych przy pierwszym połączeniu. Wyłączenie tych zasad po przeprowadzeniu początkowego parowania/synchronizacji może nie spowodować usunięcia kontaktów służbowych z urządzenia Bluetooth.

- **Przechwytywanie ekranu**: wybierz pozycję **Blokuj**, aby uniemożliwić tworzenie zrzutów ekranu i przechwytywanie ekranów na urządzeniu w profilu służbowym. Zapobiega również wyświetlaniu zawartości na urządzeniach wyświetlających, które nie mają zabezpieczonego wyjścia wideo. Pozycja **Nieskonfigurowane** umożliwia tworzenie zrzutów ekranu.

- **Wyświetlanie identyfikatora rozmówcy dla kontaktu służbowego w profilu osobistym**: po włączeniu (pozycja **Nieskonfigurowane**) szczegóły rozmówcy dla kontaktu służbowego są wyświetlane w profilu osobistym. Po wybraniu pozycji **Blokuj** numer rozmówcy dla kontaktu służbowego nie jest wyświetlany w profilu osobistym. Dotyczy systemu operacyjnego Android w wersji 6.0 i nowszych wersji.

- **Wyszukiwanie kontaktów służbowych w profilu osobistym**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom wyszukiwanie kontaktów służbowych w aplikacjach w profilu osobistym. Pozycja **Niewymagane** umożliwia wyszukiwanie kontaktów służbowych w profilu osobistym.

- **Aparat fotograficzny**: wybierz pozycję **Blokuj**, aby uniemożliwić dostęp do aparatu na urządzeniu w profilu służbowym. To ustawienie nie wpływa na aparat w profilu osobistym. Pozycja **Niewymagane** zezwala na dostęp do aparatu w profilu służbowym.

#### <a name="work-profile-password"></a>Hasło profilu służbowego

- **Wymagaj hasła profilu służbowego**: ma zastosowanie do systemu Android 7.0 lub nowszego z włączonym profilem służbowym. Wybierz pozycję **Wymagaj**, aby wprowadzić zasady kodu dostępu, które będą mieć zastosowanie wyłącznie do aplikacji w profilu służbowym. Domyślnie użytkownik końcowy może używać dwóch różnych kodów PIN lub wybrać opcję połączenia zdefiniowanych kodów PIN w celu uzyskania kodu PIN o większej sile. Pozycja **Nieskonfigurowane** umożliwia użytkownikowi używanie aplikacji służbowych bez wprowadzania hasła.
- **Minimalna długość hasła**: określ minimalną liczbę znaków, które musi zawierać hasło użytkownika, **4**-**16**.
- **Maksymalna liczba minut braku aktywności przed zablokowaniem profilu służbowego**: wybierz długość czasu przed zablokowaniem profilu służbowego. Użytkownik musi następnie wprowadzić swoje poświadczenia, aby odzyskać dostęp.
- **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia**: określ, ile razy może zostać podane nieprawidłowe hasło, zanim profil służbowy zostanie wyczyszczony z urządzenia.
- **Wygaśnięcie hasła (dni)**: określ liczbę dni, po których użytkownik końcowy musi zmienić hasło (**1**-**255**).
- **Wymagany typ hasła**: wybierz typ hasła, które musi zostać ustawione na urządzeniu. Wybierz spośród opcji:
  - **Ustawienie domyślne urządzenia**
  - **Zabezpieczenia biometryczne na niskim poziomie**
  - **Wymagane**
  - **Co najmniej numeryczne**
  - **Złożona wartość liczbowa**: powtarzające się lub kolejne cyfry, np. „1111” lub „1234”, są niedozwolone
  - **Co najmniej alfabetyczne**
  - **Co najmniej alfanumeryczne**
  - **Co najmniej alfanumeryczne z symbolami**
- **Zapobiegaj ponownemu używaniu poprzednich haseł**: wprowadź liczbę nowych haseł, których należy użyć, zanim będzie możliwe ponowne użycie starego hasła (**1**-**24**).
- **Odblokowywanie za pomocą odcisku palca**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikom końcowym użycie skanera linii papilarnych w celu odblokowania urządzenia. Pozycja **Nieskonfigurowane** zezwala użytkownikom na odblokowywanie urządzeń przy użyciu odcisku palca w profilu służbowym.
- **Blokada Smart Lock i inni agenci zaufania**: wybierz pozycję **Blokuj**, aby uniemożliwić funkcji Smart Lock lub innym agentom zaufania dostosowywanie ustawień blokady ekranu na zgodnych urządzeniach. Ta funkcja, zwana również czasami agentem zaufania, umożliwia wyłączenie lub obejście hasła ekranu blokady urządzenia, jeśli urządzenie znajduje się w zaufanej lokalizacji. Na przykład można obejść hasło profilu służbowego, gdy urządzenie jest połączone z konkretnym urządzeniem Bluetooth lub znajduje się w pobliżu tagu NFC. Za pomocą tego ustawienia można uniemożliwić użytkownikom konfigurowanie funkcji Smart Lock.

### <a name="device-password"></a>Hasło urządzenia

Te ustawienia hasła są stosowane w profilach osobistych na urządzeniach korzystających z profilu służbowego.

- **Minimalna długość hasła**: określ minimalną liczbę znaków, które musi zawierać hasło użytkownika, **4**-**14**.
- **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu**: wybierz długość czasu przed automatycznym zablokowaniem nieaktywnego urządzenia.
- **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia**: określ, ile razy może zostać podane nieprawidłowe hasło, zanim wszystkie dane zostaną wyczyszczone z urządzenia.
- **Wygaśnięcie hasła (dni)**: określ liczbę dni, po których użytkownik końcowy musi zmienić hasło (**1**-**255**).
- **Wymagany typ hasła**: wybierz typ hasła, które musi zostać ustawione na urządzeniu. Wybierz spośród opcji:
  - **Ustawienie domyślne urządzenia**
  - **Zabezpieczenia biometryczne na niskim poziomie**
  - **Wymagane**
  - **Co najmniej numeryczne**
  - **Złożona wartość liczbowa**: powtarzające się lub kolejne cyfry, np. „1111” lub „1234”, są niedozwolone
  - **Co najmniej alfabetyczne**
  - **Co najmniej alfanumeryczne**
  - **Co najmniej alfanumeryczne z symbolami**
- **Zapobiegaj ponownemu używaniu poprzednich haseł**: wprowadź liczbę nowych haseł, których należy użyć, zanim będzie możliwe ponowne użycie starego hasła (**1**-**24**).
- **Odblokowywanie za pomocą odcisku palca**: wybierz pozycję **Blokuj**, aby uniemożliwić użytkownikowi końcowemu użycie skanera linii papilarnych w celu odblokowania urządzenia. Pozycja **Nieskonfigurowane** zezwala użytkownikowi na odblokowywanie urządzenia przy użyciu odcisku palca.
- **Blokada Smart Lock i inni agenci zaufania**: wybierz pozycję **Blokuj**, aby uniemożliwić funkcji Smart Lock lub innym agentom zaufania dostosowywanie ustawień blokady ekranu na zgodnych urządzeniach. Ta funkcja, zwana również czasami agentem zaufania, umożliwia wyłączenie lub obejście hasła ekranu blokady urządzenia, jeśli urządzenie znajduje się w zaufanej lokalizacji. Na przykład można obejść hasło profilu służbowego, gdy urządzenie jest połączone z konkretnym urządzeniem Bluetooth lub znajduje się w pobliżu tagu NFC. Za pomocą tego ustawienia można uniemożliwić użytkownikom konfigurowanie funkcji Smart Lock.

### <a name="system-security"></a>Zabezpieczenia systemu

- **Skanowanie aplikacji pod kątem zagrożeń**: pozycja **Wymagaj** wymusza włączenie ustawienia **Weryfikuj aplikacje** w profilach służbowych i osobistych.

   > [!Note]
   > To ustawienie działa tylko w przypadku urządzeń z systemem Android O lub nowszym.

### <a name="connectivity"></a>Łączność

- **Zawsze włączona sieć VPN**: wybierz pozycję **Włącz**, aby ustawić klienta sieci VPN tak, aby automatycznie łączył się i przywracał połączenie z siecią VPN. Zawsze włączone połączenia sieci VPN pozostają aktywne lub natychmiast łączą się, gdy użytkownik zablokuje urządzenie, urządzenie uruchomi się ponownie lub zmieni się sieć bezprzewodowa. 

  Wybierz pozycję **Nieskonfigurowane**, aby wyłączyć zawsze włączoną sieć VPN dla wszystkich klientów sieci VPN.

  > [!IMPORTANT]
  > Należy pamiętać, aby dla jednego urządzenia wdrożyć tylko jedne zasady zawsze włączonej sieci VPN. Wdrażanie wielu zasad zawsze włączonej sieci VPN dla jednego urządzenia nie jest obsługiwane.

- **Klient sieci VPN**: wybierz klienta sieci VPN, który obsługuje opcję Zawsze włączone. Dostępne opcje:
  - Cisco AnyConnect
  - F5 Access
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Niestandardowy
    - **Identyfikator pakietu**: wprowadź identyfikator pakietu aplikacji w sklepie Google Play. Jeśli na przykład adresem URL aplikacji w sklepie Play jest `https://play.google.com/store/details?id=com.contosovpn.android.prod`, to identyfikatorem pakietu jest `com.contosovpn.android.prod`.

  > [!IMPORTANT]
  >  - Wybrany klient sieci VPN musi być zainstalowany na urządzeniu i musi obsługiwać sieć VPN dla aplikacji w profilach służbowych. W przeciwnym razie wystąpi błąd. 
  >  - Należy zatwierdzić aplikację klienta sieci VPN w **zarządzanymi sklepie Google Play**, zsynchronizować aplikację z usługą Intune i wdrożyć aplikację na urządzeniu. Po wykonaniu tej czynności aplikacja jest zainstalowana w profilu służbowym użytkownika.
  >  - Mogą wystąpić znane problemy podczas korzystania z sieci VPN dla aplikacji z programem F5 Access dla systemu Android 3.0.4. Aby uzyskać więcej informacji, zobacz [opublikowane przez firmę F5 informacje o wersji programu F5 Access dla systemu Android 3.0.4](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android).

- **Tryb blokady**: wybierz pozycję **Włącz**, aby wymusić korzystanie z tunelu sieci VPN przez cały ruch sieciowy. Jeśli nie nawiązano połączenia z siecią VPN, urządzenie nie będzie mieć dostępu do sieci.

  Wybierz pozycję **Nieskonfigurowane**, aby zezwolić ruchowi na przepływ przez tunel VPN lub sieć komórkową.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).

Można również utworzyć profile kiosku dla urządzeń z systemem [Android](device-restrictions-android.md#kiosk) i [Windows 10](kiosk-settings.md).
