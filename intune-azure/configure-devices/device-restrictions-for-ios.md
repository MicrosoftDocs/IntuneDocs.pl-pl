---
title: "Ustawienia ograniczeń urządzenia w usłudze Intune dla systemu iOS | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: informacje na temat ustawień usługi Intune służących do kontrolowania ustawień i funkcji urządzeń z systemem iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 73590192-54ca-4833-9f1d-83e1b654399f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 2b8bf6d3944f9968d0f4020fbb5c57ef8180062c
ms.lasthandoff: 02/16/2017


---

# <a name="ios-device-restriction-settings-in-microsoft-intune"></a>Ustawienia ograniczeń urządzenia z systemem iOS w usłudze Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Ogólne
-     **Aparat fotograficzny** — określa, czy można używać aparatu fotograficznego urządzenia.     
-     **Przesyłanie danych diagnostycznych** — umożliwia lub blokuje przesyłanie danych diagnostycznych z urządzenia do firmy Apple.
-     **FaceTime** — umożliwia korzystanie z aplikacji FaceTime na urządzeniu.
-     **Przechwytywanie ekranu** — umożliwia użytkownikowi przechwytywanie zawartości ekranu w formie obrazu.
-     **Siri** — umożliwia korzystanie z asystenta głosowego Siri na urządzeniu.
    -     **Program Siri, gdy urządzenie jest zablokowane** — umożliwia korzystanie z asystenta głosowego Siri na zablokowanym urządzeniu.
    -     **Filtr wulgaryzmów Siri (tylko nadzorowane)** — uniemożliwia dyktowanie lub wypowiadanie wulgaryzmów przez Siri.
    -     **Wyszukiwanie zawartości wygenerowanej przez użytkowników z sieci Internet przez Siri (tylko nadzorowane)** —umożliwia programowi Siri dostęp do witryn sieci Web w celu udzielania odpowiedzi na pytania.
-     **Niezaufane certyfikaty protokołu TLS** — zezwala na niezaufane certyfikaty protokołu Transport Layer Security na urządzeniu.
-     **Dostęp do centrum kontroli, gdy urządzenie jest zablokowane** — umożliwia użytkownikowi dostęp do aplikacji centrum sterowania, gdy urządzenie jest zablokowane.
-     **Powiadomienia, gdy urządzenie jest zablokowane** — umożliwia użytkownikowi dostęp do widoku powiadomień bez odblokowywania urządzenia.
-     **Aplikacja Passbook, gdy urządzenie jest zablokowane** — umożliwia użytkownikowi dostęp do aplikacji Passbook, gdy urządzenie jest zablokowane.
-     **Widok Dziś, gdy urządzenie jest zablokowane** — umożliwia użytkownikowi wyświetlanie widoku Dzisiaj, gdy urządzenie jest zablokowane.
-     **Zaufanie do aplikacji dla przedsiębiorstw** — umożliwia użytkownikowi wybranie zaufania do aplikacji, które nie zostały pobrane ze sklepu z aplikacjami.
-     **AirDrop (tylko nadzorowane)** — umożliwia używanie funkcji AirDrop do wymiany zawartości z pobliskimi urządzeniami.
-     **Wyniki z sieci Internet w wyszukiwaniach funkcji Spotlight (tylko nadzorowane)** — umożliwia łączenie się funkcji wyszukiwania Spotlight z Internetem w celu dostarczania dodatkowych wyników.
-     **Wyszukiwanie definicji słów (tylko nadzorowane)** — umożliwia używanie funkcji systemu iOS pozwalającej na wyróżnienie wyrazu i wyszukanie jego definicji.
-     **Klawiatury predykcyjne (tylko nadzorowane)** — umożliwia korzystanie z klawiatur predykcyjnych sugerujących wyrazy, które użytkownik może chcieć wpisać.
-     **Korekta automatyczna (tylko nadzorowane)** — pozwala na automatyczne poprawianie błędnie napisanych wyrazów przez urządzenie.
-     **Funkcja sprawdzania pisowni klawiatury (tylko nadzorowane)** — pozwala na korzystanie z modułu sprawdzania pisowni na urządzeniu.
-     **Skróty klawiaturowe (tylko nadzorowane)** — umożliwia używanie skrótów klawiaturowych.
-     **Wykrywanie nadgarstka przez sparowane urządzenie Apple Watch** — po włączeniu tego ustawienia urządzenie Apple Watch nie będzie wyświetlać powiadomień, jeśli nie znajduje się na nadgarstku użytkownika.
- **Wymagaj hasła parowania dla wychodzących żądań AirPlay** — umożliwia wymaganie hasła parowania, gdy użytkownik używa funkcji AirPlay do strumieniowego przesyłania zawartości do innych urządzeń firmy Apple.
- **Modyfikacja konta (tylko nadzorowany)** — umożliwia użytkownikowi zmianę ustawień konta, takich jak konfiguracja poczty e-mail.
- **Parowanie z urządzeniem Apple Watch (tylko nadzorowany)** — umożliwia parowanie urządzenia z urządzeniem Apple Watch.
- **Modyfikacja protokołu Bluetooth (tylko nadzorowany)** — blokuje zmianę ustawień protokołu Bluetooth na urządzeniu przez użytkownika końcowego.
- **Zdalny podgląd ekranu za pomocą aplikacji Classroom (tylko nadzorowany)** — blokuje lub zezwala na podgląd ekranu na urządzeniach zdalnych za pomocą aplikacji Classroom.
- **Włączenie ograniczeń w ustawieniach urządzenia (tylko nadzorowany)** — umożliwia użytkownikowi konfigurowanie ograniczeń dotyczących urządzenia (kontroli rodzicielskiej) na urządzeniu.
- **Użyj funkcji wymazania całej zawartości i wszystkich ustawień z urządzenia (tylko nadzorowany)** — umożliwia użytkownikowi korzystanie z opcji wymazywania całej zawartości i wszystkich ustawień z urządzenia.
- **Modyfikacja nazwy urządzenia (tylko nadzorowany)** — umożliwia użytkownikowi zmianę nazwy urządzenia.
- **Modyfikacja ustawień przesyłania danych diagnostycznych (tylko nadzorowany)** — blokuje lub zezwala na przesyłanie danych diagnostycznych z urządzenia do firmy Apple.
- **Parowanie hosta na potrzeby kontrolowania urządzeń, z którymi można parować urządzenie z systemem iOS (tylko nadzorowany)** — zezwala na parowanie hostów w celu umożliwienia administratorowi kontrolowania tego, z którymi urządzeniami może być sparowane urządzenie z systemem iOS.
- **Modyfikacja ustawień powiadamiania (tylko nadzorowany)** — umożliwia użytkownikowi zmianę ustawień powiadamiania na urządzeniu.
- **Modyfikacja kodu dostępu (tylko nadzorowany)** — umożliwia dodawanie, modyfikowanie lub usuwanie hasła urządzenia.
- **Modyfikacja tapety (tylko nadzorowany)** — umożliwia użytkownikowi zmianę tapety urządzenia.
- **Modyfikacja ustawień zaufania dla aplikacji firmy (tylko nadzorowany)** — umożliwia użytkownikowi wybranie zaufania do aplikacji, które nie zostały pobrane ze sklepu z aplikacjami.
- **Instalowanie aplikacji ze sklepu App Store (tylko nadzorowany)** — zezwala urządzeniu na dostęp do sklepu z aplikacjami i instalowanie aplikacji.
- **Zmiany ustawień aplikacji Find My Friends (tylko nadzorowany)** — umożliwia użytkownikowi zmianę ustawień aplikacji Find My Friends.
- **Sklep iBooks (tylko nadzorowany)** — umożliwia użytkownikowi przeglądanie i kupowanie książek w sklepie iBooks.
- **Aplikacja Messages na urządzeniu (tylko nadzorowany)** — umożliwia wysyłanie i odbieranie wiadomości tekstowych przy użyciu aplikacji Messages.
- **Podcasts (tylko nadzorowany)** — umożliwia korzystanie z aplikacji Podcasts.
- **Usługa Music (tylko nadzorowany)** — umożliwia korzystanie z aplikacji Apple Music.
- **Usługa iTunes Radio (tylko nadzorowany)** — umożliwia korzystanie z aplikacji iTunes Radio.
- **Apple News (tylko nadzorowany)** — umożliwia korzystanie z aplikacji Apple News.
- **Zmiany profilu konfiguracji** — umożliwia użytkownikowi instalowanie profilów konfiguracji.

## <a name="password"></a>Hasło
-     **Wymagane jest hasło** — wymaga od użytkownika końcowego wprowadzenia hasła w celu uzyskania dostępu do urządzenia.
-     **Proste hasła** — zezwala na proste hasła, takie jak „0000” i „1234”.
-     **Wymagany typ hasła** — określa wymagany typ hasła, na przykład alfanumeryczne lub wyłącznie numeryczne.
-     **Liczba znaków innych niż alfanumeryczne w haśle** — określa liczbę znaków symboli (takich jak **#** lub **@**), którą musi zawierać hasło.
-     **Minimalna długość hasła** — określa minimalną liczbę znaków w haśle.
-     **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia** — określa dozwoloną liczbę nieudanych logowań przed wyczyszczeniem urządzenia.
-     **Maksymalna liczba minut po zablokowaniu ekranu, po których jest wymagane wprowadzenie hasła**<sup>1</sup> — określa, jak długo urządzenie może pozostawać bezczynne, zanim użytkownik będzie musiał ponownie wprowadzić hasło.
-     **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu**<sup>1</sup> — określa liczbę minut przed wyłączeniem ekranu urządzenia.
-     **Wygaśnięcie hasła (dni)** — określa liczbę dni, po której należy zmienić hasło urządzenia.
-     **Zapobiegaj ponownemu użyciu starych haseł** — określa liczbę poprzednich haseł zapamiętywanych przez urządzenie.
-     **Odblokowywanie za pomocą odcisku palca** — umożliwia użycie odcisku palca do odblokowania zgodnych urządzeń.

<sup>1</sup>W przypadku skonfigurowania ustawień **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu** i **Maksymalna liczba minut po zablokowaniu ekranu, po których jest wymagane wprowadzenie hasła** są one stosowane jedno po drugim. Na przykład, jeśli wartość obu ustawień zostanie ustawiona na **5** minut, ekranie wyłączy się automatycznie po 5 minut, a urządzenie zostanie zablokowane po kolejnych 5 minutach. Jednak jeśli użytkownik wyłączy ekranie ręcznie, drugie ustawienie zostanie zastosowane natychmiast. W tym samym przykładzie, jeśli użytkownik wyłączy ekran, po 5 minutach urządzenie zostanie zablokowane.

## <a name="app-store-doc-viewing-gaming"></a>Sklep App Store, wyświetlanie dokumentów, granie


-   **App Store (tylko w trybie nadzorowanym)** — blokuje dostęp do sklepu z aplikacjami na urządzeniach nadzorowanych.
-     **Hasło dostępu do sklepu z aplikacjami** — wymaga od użytkownika wprowadzenia hasła przed odwiedzeniem sklepu z aplikacjami.
-     **Zakupy w aplikacji** — umożliwia dokonywanie zakupów w sklepie bezpośrednio z uruchomionej aplikacji.
-     **Automatyczne pobieranie aplikacji (tylko nadzorowany)** -
-     **Jawna zawartość programu iTunes — muzyka, podkasty lub wiadomości (tylko w trybie nadzorowanym)** — zezwala urządzeniu na dostęp do zawartości w sklepie sklasyfikowanej jako zawartość dla dorosłych.
-     **Pobieranie zawartości oznaczonej jako „Erotyka” ze sklepu iBooks** — zezwalaj użytkownikom na pobieranie ze sklepu iBooks książek z kategorii „Erotyka”.
-     **Wyświetlanie dokumentów firmowych w niezarządzanych aplikacjach** — umożliwia wyświetlanie dokumentów firmowych w dowolnej aplikacji.<br>**Przykład:** chcesz uniemożliwić użytkownikom zapisywanie plików z aplikacji OneDrive w aplikacji Dropbox. Skonfiguruj to ustawienie jako „nie”. Gdy urządzenie otrzyma zasady (na przykład po ponownym uruchomieniu), nie będzie już miało możliwości zapisywania.
-     **Wyświetlanie dokumentów innych niż firmowe w aplikacjach firmowych** — umożliwia wyświetlanie dowolnych dokumentów w zarządzanych aplikacjach firmowych.
-     **Traktuj usługę AirDrop jako niezarządzane miejsce docelowe** — uniemożliwia zarządzanym aplikacjom wysyłanie danych za pomocą funkcji. Airdrop.
-     **Dodawanie znajomych do usługi Game Center (tylko w trybie nadzorowanym)** — umożliwia użytkownikowi dodawanie przyjaciół do usługi Game Center.
-     **Game Center (tylko nadzorowany)** — blokuje lub umożliwia korzystanie z aplikacji Game Center.
-     **Gry dla wielu graczy (tylko w trybie nadzorowanym)** — umożliwia użytkownikowi granie na urządzeniu w gry dla wielu graczy.
-     **Region klasyfikacji** — wybierz region klasyfikacji, dla którego chcesz skonfigurować dozwolone pliki do pobrania, a następnie wybierz dozwoloną klasyfikację dla opcji **Filmy** i **Programy telewizyjne**.
-     **Aplikacje** — wybierz dozwoloną klasyfikację wiekową dla aplikacji, które użytkownicy będą mogli pobierać, lub wybierz opcję **Zezwalaj na wszystkie aplikacje**.

## <a name="restricted-apps"></a>Aplikacje z ograniczeniami

Na liście aplikacji z ograniczeniami można skonfigurować jedną z następujących list:

Lista **Aplikacje zabronione** — lista aplikacji (niezarządzanych przez usługę Intune), których użytkownicy nie mogą instalować ani uruchamiać.
Lista **Zatwierdzone aplikacje** — lista aplikacji, które użytkownicy mogą instalować. Aby utrzymać zgodność, użytkownicy nie mogą instalować aplikacji, których nie ma na liście. Aplikacje zarządzane przez usługę Intune są automatycznie traktowane jako dozwolone.

Aby skonfigurować listę, kliknij przycisk **Dodaj**, a następnie wprowadź wybraną nazwę oraz opcjonalnie wydawcę aplikacji i adres URL aplikacji w sklepie z aplikacjami.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Jak określić adres URL aplikacji w sklepie

Aby określić adres URL aplikacji na liście aplikacji, użyj następującego formatu:

Korzystając z wyszukiwarki, znajdź w sklepie iTunes aplikację, której chcesz użyć, i otwórz jej stronę.
Skopiuj adres URL strony i użyj go jako adresu URL do skonfigurowania listy aplikacji zatwierdzonych lub zabronionych bądź aplikacji działających w trybie kiosku.
Profile urządzeń zawierające ustawienia aplikacji z ograniczeniami należy wdrożyć dla grup użytkowników.

Przykład: wyszukaj aplikację Microsoft Word dla tabletu iPad. Adres URL, którego należy użyć, to https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.

> [!Note]
> Możesz również znaleźć aplikację za pomocą programu iTunes, a następnie użyć polecenia **Kopiuj link**, aby uzyskać adres URL aplikacji.



### <a name="additional-options"></a>Opcje dodatkowe

Możesz również kliknąć przycisk **Importuj**, aby wypełnić listę danymi z pliku CSV w formacie <*adres url aplikacji*>, <*nazwa aplikacji*>, <*wydawca aplikacji*>, lub kliknąć przycisk **Eksportuj**, aby utworzyć plik CSV zawierający listę aplikacji z ograniczeniami w tym samym formacie.

## <a name="show-or-hide-apps"></a>Pokaż lub ukryj aplikacje

Na liście Pokaż lub ukryj aplikacje możesz skonfigurować jedną z następujących list (wymagane są urządzenia nadzorowane z systemem iOS 9.3 lub nowszym).

Lista **Ukryte aplikacje** — określ listę aplikacji, które będą ukryte dla użytkowników. Użytkownicy nie będą mogli wyświetlać ani uruchamiać tych aplikacji.
Lista **Widoczne aplikacje** — określ listę aplikacji, które użytkownicy będą mogli wyświetlać i uruchamiać. Użytkownicy nie będą mogli wyświetlać ani uruchamiać żadnych innych aplikacji.

Aby skonfigurować listę, kliknij przycisk **Dodaj**, a następnie wprowadź wybraną nazwę oraz opcjonalnie wydawcę aplikacji i adres URL aplikacji w sklepie z aplikacjami.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Jak określić adres URL aplikacji w sklepie

Aby określić adres URL aplikacji na liście aplikacji, użyj następującego formatu:

Korzystając z wyszukiwarki, znajdź w sklepie iTunes aplikację, której chcesz użyć, i otwórz jej stronę.
Skopiuj adres URL strony i użyj go jako adresu URL do skonfigurowania listy aplikacji zatwierdzonych lub zabronionych bądź aplikacji działających w trybie kiosku.

Przykład: wyszukaj aplikację Microsoft Word dla tabletu iPad. Adres URL, którego należy użyć, to https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.

> [!Note]
> Możesz również znaleźć aplikację za pomocą programu iTunes, a następnie użyć polecenia **Kopiuj link**, aby uzyskać adres URL aplikacji.

### <a name="additional-options"></a>Opcje dodatkowe

Możesz również kliknąć przycisk **Importuj**, aby wypełnić listę danymi z pliku CSV w formacie <*adres url aplikacji*>, <*nazwa aplikacji*>, <*wydawca aplikacji*>, lub kliknąć przycisk **Eksportuj**, aby utworzyć plik CSV zawierający listę ukrytych lub widocznych aplikacji w tym samym formacie.

### <a name="app-information-for-built-in-ios-apps"></a>Informacje o aplikacji dla wbudowanych aplikacji systemu iOS
Użyj informacji na tej liście, aby określić nazwę, wydawcę i identyfikator pakietu dla wbudowanych aplikacji systemu iOS, które można pokazać lub ukryć. Jeśli chcesz pokazać lub ukryć wszystkie aplikacje na liście, możesz skopiować dane poniżej do pliku tekstowego z rozszerzeniem **CSV**, a następnie użyć opcji **Importuj**, aby zaimportować wszystkie aplikacje jednocześnie.


    App Store,Apple,com.apple.AppStore
    Calculator,Apple,com.apple.calculator
    Calendar,Apple,com.apple.mobilecal
    Camera,Apple,com.apple.camera
    Clock,Apple,com.apple.mobiletimer
    Compass,Apple,com.apple.compass
    Contacts,Apple,com.apple.MobileAddressBook
    FaceTime,Apple,com.apple.facetime
    Find Friends,Apple,com.apple.mobileme.fmf1
    Find iPhone,Apple,com.apple.mobileme.fmip1
    Game Center,Apple,com.apple.gamecenter
    GarageBand,Apple,com.apple.mobilegarageband
    Health,Apple,com.apple.Health
    iBooks,Apple,com.apple.iBooks
    iTunes Store,Apple,com.apple.MobileStore
    iTunes U,Apple,com.apple.itunesu
    Keynote,Apple,com.apple.Keynote
    Mail,Apple,com.apple.mobilemail
    Maps,Apple,com.apple.Maps
    Messages,Apple,com.apple.MobileSMS
    Music,Apple,com.apple.Music
    News,Apple,com.apple.news
    Notes,Apple,com.apple.mobilenotes
    Numbers,Apple,com.apple.Numbers
    Pages,Apple,com.apple.Pages
    Photo Booth,Apple,com.apple.Photo-Booth
    Photos,Apple,com.apple.mobileslideshow
    Podcasts,Apple,com.apple.podcasts
    Reminders,Apple,com.apple.reminders
    Safari,Apple,com.apple.mobilesafari
    Settings,Apple,com.apple.Preferences
    Stocks,Apple,com.apple.stocks
    Tips,Apple,com.apple.tips
    Videos,Apple,com.apple.videos
    VoiceMemos,Apple,com.apple.VoiceMemos
    Wallet,Apple,com.apple.Passbook
    Watch,Apple,com.apple.Bridge
    Weather,Apple,com.apple.weather





## <a name="cellular"></a>Komórkowe
-     **Roaming danych** — zezwala na roaming danych, gdy urządzenie korzysta z sieci komórkowej.
-     **Globalne pobieranie w tle podczas roamingu** — umożliwia pobieranie danych, np. wiadomości e-mail, przez urządzenie korzystające z roamingu w sieci komórkowej.
-     **Wybieranie głosowe** — umożliwia korzystanie z funkcji wybierania głosowego na urządzeniu.
-     **Roaming połączeń głosowych** — zezwala na roaming połączeń głosowych, gdy urządzenie znajduje się w sieci komórkowej.
-     **Zmiany ustawień użycia danych komórkowych aplikacji (tylko nadzorowany)** — umożliwia użytkownikowi kontrolowanie, które aplikacje mogą korzystać z danych komórkowych.

## <a name="cloud-and-storage"></a>Chmura i magazyn
-     **Tworzenie kopii zapasowych w usłudze iCloud** — umożliwia użytkownikowi tworzenie kopii zapasowych urządzenia w usłudze iCloud.
-     **Synchronizowanie dokumentów z usługą iCloud (tylko w trybie nadzorowanym)** — umożliwia synchronizowanie dokumentów i wartości kluczy w obszarze magazynu usługi iCloud.
-     **Synchronizowanie strumienia zdjęć z usługą iCloud** — umożliwia użytkownikom włączanie funkcji **Mój strumień zdjęć** na urządzeniach, co pozwala synchronizować zdjęcia z usługą iCloud i udostępniać je na wszystkich urządzeniach użytkownika.
-     **Szyfrowana kopia zapasowa** — wymaga szyfrowania wszystkich kopii zapasowych urządzenia.
-     **Biblioteka zdjęć usługi iCloud** — wybór ustawienia **Nie** powoduje wyłączenie możliwości korzystania z biblioteki zdjęć iCloud, która pozwala użytkownikom przechowywać zdjęcia i klipy wideo w chmurze.    W przypadku ustawienia opcji **Nie** wszelkie zdjęcia, które nie zostały w pełni pobrane z biblioteki zdjęć iCloud na urządzenie, zostaną usunięte z urządzenia.
-     **Zarządzane aplikacje są synchronizowane z chmurą** — zezwala aplikacjom zarządzanym za pomocą usługi Intune na synchronizowanie danych z kontem użytkownika w usłudze iCloud.
-     **Udostępniony strumień zdjęć** — wybór ustawienia **Nie** powoduje wyłączenie funkcji **Udostępnianie zdjęć w usłudze iCloud** na urządzeniu.
-     **Kontynuacja aktywności** — umożliwia użytkownikowi kontynuowanie pracy rozpoczętej na urządzeniu z systemem iOS na innym urządzeniu z systemem iOS lub Mac OS X (program Handoff).

## <a name="kiosk"></a>Kiosk
-     **Blokada aktywacji** — umożliwia blokadę aktywacji na nadzorowanych urządzeniach z systemem iOS.
-     **Aplikacja pracująca w trybie kiosku** — wybierz opcję **Aplikacja zarządzana**, aby wybrać aplikację dodaną do usługi Intune, lub wybierz opcję **Aplikacja ze Sklepu**, aby określić adres URL aplikacji w sklepie. Na tym urządzeniu nie będzie można uruchamiać żadnych innych aplikacji. Aby uzyskać pomoc, zobacz sekcję „Jak określać adresy URL sklepów z aplikacjami” w dalszej części tego tematu.
-     **Dotyk wspomagający** — włącza lub wyłącza funkcję ułatwień dostępu **Dotyk wspomagający**, która ułatwia użytkownikom wykonywanie trudnych dla nich gestów na ekranie.
-     **Odwróć kolory** — włącza lub wyłącza funkcję ułatwień dostępu Odwróć kolory, która umożliwia dostosowanie wyświetlanego obrazu do potrzeb użytkowników niedowidzących.
-     **Dźwięk mono** — włącza lub wyłącza ustawienie ułatwień dostępu Dźwięk mono.
-     **VoiceOver** — włącza lub wyłącza funkcję ułatwień dostępu **VoiceOver**, która odczytuje na głos tekst wyświetlany na ekranie urządzenia.
-     **Powiększenie** — włącza lub wyłącza funkcję ułatwień dostępu **Powiększenie** umożliwiającą użytkownikowi powiększenie obrazu wyświetlanego na ekranie urządzenia za pomocą dotyku.
-     **Blokada automatyczna** — włącza lub wyłącza automatyczną blokadę urządzenia.
-     **Przełącznik dzwonka** — włącza lub wyłącza przełącznik dzwonka (wyciszenie) na urządzeniu.
-     **Obrót ekranu** — włącza lub wyłącza zmianę orientacji ekranu przy obrocie urządzenia.
-     **Przycisk usypiania ekranu** — włącza lub wyłącza przycisk usypiania/budzenia ekranu na urządzeniu.
-     **Dotyk** — włącza lub wyłącza ekran dotykowy na urządzeniu.
-     **Przyciski głośności** — włącza lub wyłącza przyciski regulacji głośności na urządzeniu.
-     **Wspomagająca kontrola dotykowa** — włącza lub wyłącza ustawienia obsługi dotykowej z ułatwieniami, które umożliwiają użytkownikowi dostosowanie funkcji dotyku wspomagającego.
-     **Odwróć kontrolę kolorów** — włącza lub wyłącza ustawienia funkcji Odwróć kolory, które umożliwiają użytkownikowi dostosowanie jej do swoich potrzeb.
-     **Mów przy wybranym tekście** — włącza lub wyłącza ustawienia funkcji ułatwień dostępu Czytaj zaznaczenie, która umożliwia odczytanie na głos tekstu zaznaczonego przez użytkownika.
-     **Kontrola VoiceOver** — włącza lub wyłącza ustawienia funkcji VoiceOver, które umożliwiają dostosowanie jej do swoich potrzeb (na przykład określenie tempa odczytywania tekstu na ekranie).
-     **Ustawianie powiększenia** — włącza lub wyłącza ustawienia funkcji powiększenia, które umożliwiają użytkownikowi dostosowanie jej do swoich potrzeb.

>[!NOTE]
> Aby można było skonfigurować urządzenie z systemem iOS do obsługi trybu kiosku, należy najpierw użyć narzędzia Apple Configurator lub programu Apple Device Enrollment Program w przełączenia go do trybu nadzorowanego. Aby uzyskać więcej informacji o narzędziu Apple Configurator, skorzystaj z dokumentacji firmy Apple.
>Jeśli określona aplikacja dla systemu iOS zostanie zainstalowana po wdrożeniu zasad konfiguracji, urządzenie przejdzie do trybu kiosku dopiero po ponownym uruchomieniu.

## <a name="safari"></a>Safari
-     **Safari (tylko w trybie nadzorowanym)** — określa, czy na urządzeniu można używać przeglądarki Safari.
-     **Autowypełnianie** — umożliwia użytkownikowi zmianę ustawień autouzupełniania w przeglądarce.
-     **Pliki cookie** — umożliwia używanie plików cookie przez przeglądarkę.
-     **JavaScript** — umożliwia uruchamianie skryptów Java w przeglądarce.
-     **Ostrzeżenia przed oszustwem** — umożliwia wyświetlanie ostrzeżeń przed oszustwem w przeglądarce.
-     **Wyskakujące okienka** — włącza lub wyłącza blokowanie wyskakujących okienek w przeglądarce.

