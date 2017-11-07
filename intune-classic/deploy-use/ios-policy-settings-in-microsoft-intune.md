---
title: Ustawienia zasad systemu iOS
description: "Utwórz zasady określające ustawienia i funkcje na urządzeniach z systemem iOS zarządzanych za pomocą usługi Intune."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab46be6c-ab73-4c99-8492-66d1dd418293
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 58be7ad24da7e4eadc1c67016979396114799bd8
ms.sourcegitcommit: 0f877251e6adf4e45b918cc8dc9193626727f2d9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2017
---
# <a name="ios-policy-settings-in-microsoft-intune"></a>Ustawienia zasad systemu iOS w usłudze Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Usługa Intune udostępnia szereg wbudowanych ustawień ogólnych, które można skonfigurować na urządzeniach z systemem iOS. Ponadto przy użyciu narzędzia Apple Configurator można utworzyć ustawienia niestandardowe, które nie są dostępne w usłudze Intune.

## <a name="general-configuration-policy-settings"></a>Ustawienia ogólnych zasad konfiguracji

**Ogólne zasady konfiguracji systemu iOS** w usłudze Microsoft Intune umożliwiają konfigurację następujących ustawień:

-   **Ustawienia ogólne urządzenia i ustawienia zabezpieczeń**. Możesz wybrać ustawienia z listy wstępnie zdefiniowanych ustawień, które pozwalają na kontrolowanie szeregu funkcji urządzenia.

-   **Tryb kiosku**. Blokowanie urządzenia w celu zezwolenia na działanie tylko niektórych funkcji. Na przykład można zezwolić na uruchamianie na urządzeniu tylko określonej zarządzanej aplikacji albo można wyłączyć przyciski regulacji głośności na urządzeniu. Można użyć tych ustawień dla modeli pokazowych urządzenia lub dla urządzeń przeznaczonych do wykonywania tylko jednej funkcji — na przykład urządzeń w punkcie sprzedaży.

-   **Zgodne i niezgodne aplikacje**. Określ listę zgodnych i niezgodnych aplikacji w firmie. Na urządzeniach z systemami Android i iOS można użyć **Raportu o niezgodnych aplikacjach** , aby porównać aplikacje zainstalowane przez użytkowników z listą zgodnych aplikacji (ale nie można zablokować instalacji aplikacji).

> [!TIP]
> Można skonfigurować warunki i postanowienia dla użytkowników, aby wiedzieli oni, że aplikacje na urządzeniu, w tym również aplikacje osobiste, będą podlegały ocenie, a aplikacje niezgodne będą blokowane lub zgłaszane. Przed rejestracją urządzenia i rozpoczęciem korzystania z Portalu firmy w celu pobrania aplikacji użytkownicy muszą zaakceptować przedstawione warunki i postanowienia. Aby uzyskać więcej informacji na temat korzystania z warunków i postanowień, zobacz [Ustawienia zasad dotyczących warunków i postanowień w usłudze Microsoft Intune](terms-and-condition-policy-settings-in-microsoft-intune.md).

Jeśli ustawienia, którego szukasz, nie ma w tym temacie, można je utworzyć za pomocą niestandardowych zasad systemu iOS, które umożliwiają importowanie ustawień utworzonych za pomocą narzędzia [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12). Aby uzyskać więcej informacji, zobacz „Ustawienia zasad niestandardowych” w dalszej części tego tematu.

### <a name="security-settings"></a>Ustawienia zabezpieczeń
Wszystkie ustawienia dotyczą systemu iOS 8.0 i nowszych.

|Nazwa ustawienia|Szczegóły|
|----------------|-------|
|**Wymagaj hasła do odblokowania urządzeń przenośnych**|Określ, czy użytkownik musi wprowadzić hasło, aby uzyskać dostęp do urządzenia.|
|**Wymagany typ hasła**|Określ typ hasła, które będzie wymagane, na przykład wyłącznie numeryczne lub alfanumeryczne.|
|**Wymagana liczba znaków złożonych w haśle**|Określ liczbę znaków symbolicznych (takich jak **#** lub **@**), które muszą być zawarte w haśle.|
|**Minimalna długość hasła**|Określ minimalną liczbę znaków w haśle.|
|**Zezwalaj na proste hasła**|Zezwalaj na proste hasła, takie jak **0000** i **1234**.|
|**Liczba dopuszczalnych nieudanych logowań przed wyczyszczeniem danych z urządzenia**|Określ liczbę dopuszczalnych nieudanych logowań przed wyczyszczeniem danych z urządzenia.|
|**Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**<sup>1</sup>|Określ, jak długo urządzenie może pozostawać bezczynne, zanim użytkownik będzie musiał ponownie wprowadzić hasło.|
|**Dni do wygaśnięcia hasła**|Określ liczbę dni, po której należy zmienić hasło urządzenia.|
|**Pamiętaj historię haseł**|Określ, czy użytkownik może użyć poprzednio używanego hasła.|
|**Pamiętaj historię haseł** — **Zapobiegaj ponownemu używaniu poprzednich haseł**|Określ liczbę poprzednich haseł, które są zapamiętywane przez urządzenie.|
|**Liczba minut braku aktywności przed wyłączeniem ekranu**<sup>1</sup>|Określ liczbę minut przed wyłączeniem ekranu urządzenia.|
|**Zezwalaj na odblokowanie na podstawie linii papilarnych**|Zezwalaj na odblokowywanie urządzenia przy użyciu linii papilarnych.|
<sup>1</sup> W przypadku urządzeń z systemem iOS skonfigurowane ustawienia **Liczba minut braku aktywności przed wyłączeniem ekranu** i **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła** są stosowane jedno po drugim. Na przykład, jeśli wartość obu ustawień zostanie ustawiona na **5** minut, ekranie wyłączy się automatycznie po 5 minut, a urządzenie zostanie zablokowane po kolejnych 5 minutach. Jednak jeśli użytkownik wyłączy ekranie ręcznie, drugie ustawienie zostanie zastosowane natychmiast. W tym samym przykładzie, jeśli użytkownik wyłączy ekran, po 5 minutach urządzenie zostanie zablokowane.

### <a name="system-settings"></a>Ustawienia systemowe
Wszystkie ustawienia dotyczą systemu iOS 8.0 i nowszych.

|Nazwa ustawienia|Szczegóły|
|----------------|-------|
|**Zezwalaj na robienie zrzutów ekranu**|Zezwalaj użytkownikowi na przechwytywanie zawartości ekranu w formie obrazu.|
|**Zezwalaj na dostęp do centrum kontroli na ekranie blokady**|Zezwalaj użytkownikowi na dostęp do aplikacji centrum sterowania, gdy urządzenie jest zablokowane.|
|**Zezwalaj na dostęp do widoku powiadomień na ekranie blokady**|Zezwalaj użytkownikowi na dostęp do widoku powiadomień bez odblokowywania urządzenia.|
|**Zezwalaj na dostęp do widoku Dziś na ekranie blokady**|Zezwalaj użytkownikowi na wyświetlanie powiadomień, gdy urządzenie jest zablokowane.|
|**Zezwalaj na niezaufane certyfikaty TLS**|Zezwalaj na niezaufane certyfikaty protokołu TLS na urządzeniu.|
|**Zezwalaj na przesyłanie danych diagnostycznych**|Zezwala lub blokuje możliwość przesyłania danych diagnostycznych z urządzenia do firmy Apple.|
|**Zezwalaj na używanie aplikacji Passbook po zablokowaniu**|Zezwalaj użytkownikowi na dostęp do aplikacji Passbook, gdy urządzenie jest zablokowane.|

### <a name="cloud-settings-for-documents-and-data"></a>Ustawienia chmury dotyczące dokumentów i danych
Wszystkie ustawienia dotyczą systemu iOS 8.0 i nowszych.

|Nazwa ustawienia|Szczegóły|
|----------------|-------|
|**Zezwalaj na wykonywanie kopii zapasowych w usłudze iCloud**|Zezwalaj użytkownikowi na tworzenie kopii zapasowych urządzenia w usłudze iCloud.|
|**Zezwalaj na synchronizację dokumentów w usłudze iCloud**|Zezwalaj na synchronizowanie dokumentów i wartości kluczy do obszaru magazynu usługi iCloud.|
|**Zezwalaj na synchronizację strumienia zdjęć w usłudze iCloud**|Umożliwia użytkownikom włączanie funkcji **Mój strumień zdjęć** na ich urządzeniach, co pozwala synchronizować zdjęcia z usługą iCloud i udostępniać je na wszystkich urządzeniach użytkownika.|
|**Wymagaj szyfrowanej kopii zapasowej**|Wymagaj szyfrowania wszelkich kopii zapasowych urządzenia.|
|**Zezwalaj zarządzanym aplikacjom na synchronizowanie danych z usługą iCloud**|Zezwalaj aplikacjom zarządzanym za pomocą usługi Intune na synchronizowanie danych z kontem użytkownika w usłudze iCloud.|
|**Zezwalaj programowi Handoff na kontynuowanie działań na innym urządzeniu**|Zezwalaj użytkownikowi na kontynuowanie pracy rozpoczętej na urządzeniu z systemem iOS na innym urządzeniu z systemem iOS lub Mac OS X.|
|**Zezwalaj na udostępnianie zdjęć w usłudze iCloud**|Ustaw opcję **Nie**, aby wyłączyć funkcję **Udostępnianie zdjęć w usłudze iCloud** na urządzeniu.|
|**Zezwalaj na Bibliotekę zdjęć iCloud**|Ustawienie opcji **Nie** powoduje wyłączenie korzystania z biblioteki zdjęć iCloud, która pozwala użytkownikom przechowywać zdjęcia i klipy wideo w chmurze.   W przypadku ustawienia opcji **Nie** wszelkie zdjęcia, które nie zostały w pełni pobrane z biblioteki zdjęć iCloud na urządzenie, zostaną usunięte z urządzenia.|

### <a name="application-settings-for-the-browser"></a>Ustawienia aplikacji dotyczące przeglądarki
Wszystkie ustawienia dotyczą systemu iOS 8.0 i nowszych.

|Nazwa ustawienia|Szczegóły|
|----------------|-------|
|**Zezwalaj na używanie programu Safari**|Określ, czy na urządzeniu można użyć przeglądarki Safari.|
|**Zezwalaj na automatyczne uzupełnianie**|Zezwalaj użytkownikowi na zmianę ustawienia autowypełniania w przeglądarce.|
|**Zezwalaj na blokowanie wyskakujących okienek**|Włącz lub wyłącz blokowanie wyskakujących okienek w przeglądarce.|
|**Zezwalaj na pliki cookie**|Zezwalaj na używanie plików cookie przez przeglądarkę.|
|**Zezwalaj na używanie skryptów języka Java**|Zezwalaj na uruchamianie skryptów Java w przeglądarce.|
|**Zezwalaj na ostrzeganie o oszustwach**|Zezwalaj na ostrzeżenia o oszustwie w przeglądarce.|

### <a name="application-settings-for-apps"></a>Ustawienia aplikacji dotyczące aplikacji
Wszystkie ustawienia dotyczą systemu iOS 8.0 i nowszych.

|Nazwa ustawienia|Szczegóły|
|----------------|-------|
|**Zezwalaj na instalowanie aplikacji**|Zezwalaj urządzeniu na dostęp do sklepu z aplikacjami i instalowanie aplikacji.|
|**Wymagaj hasła w celu dostępu do sklepu z aplikacjami**|Wymagaj od użytkownika wprowadzenia hasła, zanim będzie on mógł odwiedzić sklep z aplikacjami.|
|**Zezwalaj na zakupy w aplikacji**|Zezwalaj na zakupy w sklepie dokonywane w uruchomionej aplikacji.|
|**Zezwalaj na zarządzane dokumenty w innych niezarządzanych aplikacjach**|Zezwalaj na wyświetlanie dokumentów firmowych w dowolnej aplikacji.<br>**Przykład:** chcesz uniemożliwić użytkownikom zapisywanie plików z aplikacji OneDrive w aplikacji Dropbox. Skonfiguruj to ustawienie jako „nie”. Gdy urządzenie otrzyma zasady (na przykład po ponownym uruchomieniu), nie będzie już miało możliwości zapisywania.|
|**Zezwalaj na niezarządzane dokumenty w innych zarządzanych aplikacjach**|Zezwalaj na wyświetlanie dowolnych dokumentów w zarządzanych aplikacjach firmowych.|
|**Zezwalaj na wideokonferencje**|Zezwalaj na użycie aplikacji do obsługi wideokonferencji, takiej jak FaceTime, w urządzeniu.|
|**Zezwalaj użytkownikowi na ufanie autorom nowych aplikacji dla przedsiębiorstw**|Umożliwia użytkownikowi wybranie ufania aplikacjom, które nie zostały pobrane ze sklepu z aplikacjami.|


### <a name="application-settings-for-games"></a>Ustawienia aplikacji dotyczące gier
Wszystkie ustawienia dotyczą systemu iOS 8.0 i nowszych.

|Nazwa ustawienia|Szczegóły|
|----------------|-------|
|**Zezwalaj na dodawanie znajomych do usługi Game Center**|Zezwalaj użytkownikowi na dodawanie przyjaciół w Centrum gier.|
|**Zezwalaj na gry dla wielu graczy**|Zezwalaj użytkownikowi na gry dla wielu graczy w urządzeniu.|

### <a name="application-settings-for-media-content"></a>Ustawienia aplikacji dotyczące zawartości multimedialnej
Wszystkie ustawienia dotyczą systemu iOS 8.0 i nowszych.

|Nazwa ustawienia|Szczegóły|
|----------------|-------|
|**Region klasyfikacji**|Wybierz region, a następnie wybierz maksymalną klasyfikację zawartości, którą użytkownicy mogą pobierać w przypadku **filmów**, **programów telewizyjnych** i **aplikacji**.|
|**Zezwalaj na dostęp do treści dla dorosłych w sklepie z multimediami**|Zezwalaj urządzeniu na dostęp do zawartości w sklepie sklasyfikowanej jako zawartość dla dorosłych.|
|**Zezwalaj użytkownikom na pobieranie ze sklepu iBook zawartości oznaczonej jako „Erotyka”**|Zezwalaj użytkownikom na pobieranie ze sklepu iBook książek z kategorii „Erotyka”.|


### <a name="device-capabilities-settings-for-hardware"></a>Ustawienia możliwości urządzenia dotyczące sprzętu
Wszystkie ustawienia dotyczą systemu iOS 8.0 i nowszych.

|Nazwa ustawienia|Szczegóły|
|----------------|-------|
|**Zezwalaj na używanie aparatu**|Określ, czy można używać aparatu w urządzeniu.|
|**Wymuszaj wykrywanie nadgarstka dla sparowanych zegarków Apple Watch**|Po włączeniu tego ustawienia Apple Watch nie będzie wyświetlać powiadomień, kiedy nie znajduje się na nadgarstku użytkownika.|
|**Wymagaj hasła parowania dla wychodzących żądań funkcji AirPlay**|Wymagaj hasła parowania, gdy użytkownik używa funkcji AirPlay do strumieniowego przesyłania zawartości do innych urządzeń firmy Apple.|

### <a name="device-capabilities-settings-for-cellular"></a>Ustawienia możliwości urządzenia dotyczące połączeń komórkowych
Wszystkie ustawienia dotyczą systemu iOS 8.0 i nowszych.

|Nazwa ustawienia|Szczegóły|
|----------------|-------|
|**Zezwalaj na roaming połączeń głosowych**|Zezwalaj na roaming połączeń głosowych, gdy urządzenie jest w sieci komórkowej.|
|**Zezwalaj na roaming danych**|Zezwalaj na roaming danych, gdy urządzenie korzysta z sieci komórkowej.|
|**Zezwalaj na pobieranie danych globalnych w tle po włączeniu roamingu**|Zezwalaj urządzeniu na pobieranie danych, np. wiadomości e-mail, w roamingu w sieci komórkowej.|

### <a name="device-capabilities-settings-for-features"></a>Ustawienia możliwości urządzenia dotyczące funkcji
Wszystkie ustawienia dotyczą systemu iOS 8.0 i nowszych.

|Nazwa ustawienia|Szczegóły|
|----------------|-------|
|**Zezwalaj na używanie programu Siri**|Zezwalaj na korzystanie z asystenta głosowego Siri w urządzeniu.|
|**Zezwalaj na używanie programu Siri po zablokowaniu urządzenia**|Zezwalaj na korzystanie z asystenta głosowego Siri w urządzeniu, gdy urządzenie jest zablokowane.|
|**Zezwalaj na wybieranie głosowe**|Zezwalaj na korzystanie z funkcji wybierania głosowego w urządzeniu.|
|**Nie zezwalaj na użycie funkcji Airdrop z zarządzanych aplikacji**|Uniemożliwia zarządzanym aplikacjom wysyłanie danych za pomocą funkcji Airdrop.|


### <a name="settings-for-compliant-and-noncompliant-apps"></a>Ustawienia dotyczące aplikacji zgodnych i niezgodnych
Na liście **Zgodne i niezgodne aplikacje** określ listę zgodnych i niezgodnych aplikacji, korzystając z poniższych informacji.

> [!NOTE]
> W ramach jednych zasad można określić wyłącznie listę zgodnych lub wyłącznie listę niezgodnych aplikacji. Nie można wprowadzić obu list w ramach jednych zasad.

|Nazwa ustawienia|Szczegóły|
|----------------|--------------------|
|**Zgłaszaj brak zgodności, jeśli użytkownicy będą instalować aplikacje z listy**|Utwórz listę aplikacji (niezarządzanych przez usługę Intune), których użytkownicy nie mogą instalować i uruchamiać.|
|**Zgłaszaj brak zgodności, jeśli użytkownicy będą instalować aplikacje spoza listy**|Utwórz listę aplikacji, które użytkownicy mogą instalować. Aby utrzymać zgodność, użytkownicy nie mogą instalować aplikacji, których nie ma na liście. Aplikacje zarządzane przez usługę Intune są automatycznie traktowane jako dozwolone.|
|**Dodaj**|Dodaje aplikację do wybranej listy. Wprowadź wybraną nazwę, opcjonalnie wydawcę aplikacji, a także adres URL aplikacji w sklepie z aplikacjami. Zobacz sekcję „Jak określać adresy URL sklepów z aplikacjami” w dalszej części tego tematu, aby uzyskać pomoc.|
|**Importuj aplikacje**|Importuje listę aplikacji w pliku w formacie wartości rozdzielanych przecinkami. W pliku użyj tego formatu: nazwa aplikacji, wydawca, adres URL aplikacji.|
|**Edytowanie**|Umożliwia edytowanie nazwy, wydawcy i adresu URL wybranej aplikacji.|
|**Usuwanie**|Usuwa wybraną aplikację z listy.|

Zasady zawierające ustawienia zgodnych i niezgodnych aplikacji należy wdrażać dla grup użytkowników.

### <a name="kiosk-mode-settings"></a>Ustawienia trybu kiosku

|Nazwa ustawienia|Szczegóły|
|----------------|--------------------|
|**Wybierz zarządzaną aplikację, która będzie mogła działać na urządzeniu w trybie kiosku**|Wybierz pozycję **Przeglądaj**, a następnie wskaż zarządzaną aplikację lub aplikację ze sklepu, która będzie mogła działać na urządzeniu w trybie kiosku. Na tym urządzeniu nie będzie można uruchamiać żadnych innych aplikacji. Aby uzyskać pomoc, zobacz sekcję „Jak określać adresy URL sklepów z aplikacjami” w dalszej części tego tematu.|
|**Zezwalaj na obsługę dotykową**|Włącza lub wyłącza ekran dotykowy na urządzeniu.|
|**Zezwalaj na obracanie ekranu**|Włącza lub wyłącza zmianę orientacji ekranu podczas obracania urządzenia.|
|**Zezwalaj na używanie przycisków regulacji głośności**|Włącza lub wyłącza przyciski regulacji głośności na urządzeniu.|
|**Zezwalaj na przełączanie dzwonka**|Włącza lub wyłącza przełączanie dzwonka (wyciszanie) na urządzeniu.|
|**Zezwalaj na używanie przycisku usypiania/budzenia ekranu**|Włącza lub wyłącza przycisk usypiania/budzenia ekranu na urządzeniu.|
|**Zezwalaj na automatyczne blokowanie**|Włącza lub wyłącza automatyczne blokowanie urządzenia.|
|**Włącz dźwięk mono**|Włącza lub wyłącza ustawienie ułatwień dostępu **Dźwięk mono**.|
|**Włącz lektora**|Włącza lub wyłącza funkcję ułatwień dostępu **VoiceOver** , która odczytuje na głos tekst wyświetlany na ekranie urządzenia.|
|**Włącz korektę lektora**|Włącza lub wyłącza możliwość dostosowania ustawień funkcji VoiceOver (na przykład tempa odczytywania tekstu z ekranu).|
|**Włącz powiększenie**|Włącza lub wyłącza funkcję ułatwień dostępu **Zoom** umożliwiającą użytkownikowi powiększenie fragmentu ekranu urządzenia za pomocą gestu.|
|**Włącz korektę powiększenia**|Włącza lub wyłącza ustawienia funkcji Zoom.|
|**Włącz odwrócone kolory**|Włącza lub wyłącza funkcję ułatwień dostępu **Odwróć kolory** dostosowującą wyświetlany obraz do potrzeb użytkowników niedowidzących.|
|**Włącz korektę odwróconych kolorów**|Włącza lub wyłącza ustawienia funkcji Odwróć kolory, która umożliwia użytkownikowi korektę odwróconych kolorów.|
|**Włącz obsługę dotykową z ułatwieniami**|Włącza lub wyłącza funkcję ułatwień dostępu **Assistive Touch**, która ułatwia użytkownikom wykonywanie trudnych dla nich gestów na ekranie.|
|**Włącz korektę obsługi dotykowej z ułatwieniami**|Włącza lub wyłącza ustawienia obsługi dotykowej z ułatwieniami, które umożliwiają użytkownikom dostosowanie funkcji obsługi dotykowej z ułatwieniami.|
|**Włącz wybór mowy**|Włącza lub wyłącza funkcję ułatwień dostępu **wyboru mowy**, dzięki której zaznaczony tekst może zostać odczytany użytkownikowi na głos przez urządzenie.|
> [!NOTE]
> Poniższe uwagi dotyczą ustawień trybu kiosku dla urządzeń z systemem iOS:
>
> -   Aby można było skonfigurować tryb kiosku dla urządzenia z systemem iOS, należy najpierw użyć [narzędzia Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) lub [programu Device Enrollment Program firmy Apple](ios-device-enrollment-program-in-microsoft-intune.md) w celu uruchomienia trybu nadzorowanego na tym urządzeniu. Aby uzyskać więcej informacji o narzędziu Apple Configurator, skorzystaj z dokumentacji firmy Apple.
> -   Jeśli określona aplikacja dla systemu iOS zostanie zainstalowana po wdrożeniu zasad konfiguracji, urządzenie przejdzie do trybu kiosku dopiero po ponownym uruchomieniu.

### <a name="reference-information-for-compliant-and-noncompliant-apps"></a>Informacje o odwołaniu dotyczące aplikacji zgodnych i niezgodnych

Użyj **Raportu o niezgodnych aplikacjach** , aby wyświetlić zgodność dozwolonych i blokowanych aplikacji.

##### <a name="to-run-the-noncompliant-apps-report"></a>Aby uruchomić raport o niezgodnych aplikacjach

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) kliknij pozycję **Raporty** &gt; **Raport o niezgodnych aplikacjach**.

2.  Wybierz grupy urządzeń, które chcesz sprawdzić, określ, czy sprawdzić aplikacje zgodne, niezgodne czy oba rodzaje, a następnie wybierz pozycję **Wyświetl raport**.

#### <a name="how-to-specify-urls-to-app-stores"></a>Jak określać adresy URL sklepów z aplikacjami
Aby określić adres URL na liście zgodnych i niezgodnych aplikacji lub w opcji **Wybierz zarządzaną aplikację, która będzie mogła działać na urządzeniu w trybie kiosku** (tylko iOS), użyj następującego formatu:

1. Korzystając z wyszukiwarki, znajdź w sklepie iTunes aplikację, której chcesz użyć, i otwórz jej stronę.

2. Skopiuj adres URL strony i użyj go jako adresu URL do skonfigurowania listy zgodnych lub niezgodnych aplikacji lub aplikacji, która będzie działać w trybie kiosku.

**Przykład:** Wyszukaj aplikację **Microsoft Word dla tabletu iPad**. Adres URL, którego użyjesz, to **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.

> [!NOTE]
> Możesz również znaleźć aplikację za pomocą programu iTunes, a następnie użyć polecenia **Kopiuj link** , aby uzyskać adres URL aplikacji.

### <a name="enrollment-settings"></a>Ustawienia rejestracji
Wszystkie ustawienia dotyczą systemu iOS 8.0 i nowszych.

|Nazwa ustawienia|Szczegóły|
|----------------|--------------------|
|**Zezwalaj na blokadę aktywacji, gdy urządzenie jest w trybie nadzorowanym**|Umożliwia blokadę aktywacji na nadzorowanych urządzeniach z systemem iOS.|

### <a name="supervised-mode-settings"></a>Ustawienia trybu nadzorowanego
Następujące ustawienia można skonfigurować na urządzeniach z systemem iOS 8.0 lub nowszym, które są w trybie nadzorowanym.

### <a name="supervised-mode-settings-for-device-restrictions"></a>Ustawienia trybu nadzorowanego dla ograniczeń urządzenia

|Nazwa ustawienia|Szczegóły|
|----------------|--------------------|
|**Zezwalaj na modyfikowanie konta**|Umożliwia użytkownikowi zmianę ustawień konta, takich jak konfiguracja poczty e-mail.|
|**Zezwalaj na zmienianie ustawień użycia komórkowego połączenia do transmisji danych w aplikacji**|Umożliwia użytkownikowi kontrolowanie, które aplikacje mogą korzystać z danych komórkowych.|
|**Zezwalaj na korzystanie z opcji wymazywania z urządzenia całej zawartości i wszystkich ustawień**|Zezwala użytkownikowi na korzystanie z opcji wymazywania z urządzenia całej zawartości i wszystkich ustawień na urządzeniu.|
|**Zezwalaj użytkownikom na włączanie ograniczeń w ustawieniach urządzenia**|Zezwala użytkownikowi na konfigurowanie ograniczeń urządzenia (kontroli rodzicielskiej) na urządzeniu.|
|**Zezwalaj na parowanie hostów w celu sterowania tym, z którymi urządzeniami może łączyć się urządzenie z systemem iOS**|Zezwala na parowanie hostów w celu umożliwienia administratorowi kontrolowania tego, z którymi urządzeniami może być sparowane urządzenie iOS.|
|**Zezwala użytkownikowi na instalowanie profilów konfiguracji i certyfikatów**|Zezwala użytkownikowi na instalowanie profilów konfiguracji i certyfikatów.|
|**Zezwalaj na modyfikację nazwy urządzenia**|Zezwala użytkownikowi na zmianę nazwy urządzenia.|
|**Zezwalaj na modyfikację kodu dostępu**|Zezwala na dodawanie, zmianę lub usunięcie hasła urządzenia.|
|**Zezwalaj na parowanie zegarków Apple Watch**|Zezwala na parowanie urządzenia z zegarkiem Apple Watch.|
|**Zezwalaj na modyfikowanie ustawień powiadomień**|Zezwala użytkownikowi na zmianę ustawień powiadomień urządzenia.|
|**Zezwalaj na modyfikowanie tapety**|Zezwala użytkownikowi na zmianę tapety urządzenia.|

### <a name="supervised-mode-settings-for-feature-restrictions"></a>Ustawienia trybu nadzorowanego dla ograniczeń funkcji

|Nazwa ustawienia|Szczegóły|
|----------------|--------------------|
|**Zezwalaj na korzystanie z funkcji AirDrop**|Umożliwia używanie funkcji AirDrop do wymiany zawartości z pobliskimi urządzeniami.|
|**Zezwalaj programowi Siri na wykonywanie zapytań o zawartość wygenerowaną przez użytkowników w Internecie**|Zezwala programowi Siri na dostęp do witryn sieci Web w celu udzielania odpowiedzi na pytania.|
|**Użyj filtra wulgaryzmów programu Siri**|Uniemożliwia programowi Siri dyktowanie i mówienie wulgaryzmów.|
|**Zezwalaj na zwracanie przez wyszukiwanie Spotlight wyników z Internetu**|Pozwala, aby wyszukiwanie Spotlight łączyło się z Internetem w celu udostępniania dodatkowych wyników.|
|**Zezwalaj na wyszukiwanie definicji słowa**|Zezwala na używanie funkcji systemu iOS umożliwiającej wyróżnienie wyrazu i wyszukanie jego definicji.|
|**Zezwalaj na klawiatury predykcyjne**|Zezwala na używanie klawiatur predykcyjnych, które sugerują wyrazy, które użytkownik może chcieć wpisać.|
|**Zezwalaj na autokorektę**|Pozwala urządzeniu na automatyczne poprawianie błędnie napisanych wyrazów.|
|**Zezwalaj na sprawdzanie pisowni dla klawiatury**|Pozwala na korzystanie z modułu sprawdzania pisowni urządzenia.|
|**Zezwalaj na skróty klawiaturowe**|Zezwala na używanie skrótów klawiaturowych.|

### <a name="supervised-mode-settings-for-app-restrictions"></a>Ustawienia trybu nadzorowanego dla ograniczeń aplikacji

|Nazwa ustawienia|Szczegóły|
|----------------|--------------------|
|**Zezwalaj na modyfikowanie ustawień zaufania aplikacji dla przedsiębiorstw**|Umożliwia użytkownikom zmienianie ustawień zaufania dla aplikacji dla przedsiębiorstw.|
|**Zezwalaj na instalowanie aplikacji tylko za pomocą programów Apple Configurator i iTunes**|Włącza lub wyłącza sklep App Store na ekranie głównym urządzenia. Użytkownicy nadal mogą instalować i aktualizować aplikacje przy użyciu programu iTunes lub narzędzia Apple Configurator.|
|**Zezwalaj na automatyczne pobieranie aplikacji**|Zezwalaj na automatyczne pobieranie na to urządzenie aplikacji kupionych na innych urządzeniach. To ustawienie nie wpływa na aktualizacje aplikacji.|
|**Zezwalaj na zmienianie ustawień aplikacji Find My Friends**|Umożliwia użytkownikowi zmienianie ustawień aplikacji Znajdź moich znajomych.|
|**Zezwalaj na dostęp do sklepu iBooks**|Umożliwia użytkownikowi przeglądanie i kupowanie książek w sklepie iBooks.|
|**Zezwalaj na korzystanie z aplikacji Messages na urządzeniu**|Zezwala na korzystanie z aplikacji Messages do wysyłania wiadomości SMS.|
|**Zezwalaj na użycie aplikacji Podcasty**|Zezwala na używanie aplikacji Podcasty.|
|**Zezwalaj na użycie usługi Music**|Zezwala na używanie aplikacji Apple Music.|
|**Zezwalaj na usługę iTunes Radio**|Zezwala na używanie aplikacji iTunes Radio.|
|**Zezwalaj na usługę Apple News**|Zezwala na używanie aplikacji Apple News.|
|**Zezwalaj na aplikację Game Center**|Zezwala na używanie aplikacji Game Center.|


### <a name="show-or-hide-apps"></a>Pokaż lub ukryj aplikacje

Użyj **listy ukrytych i pokazanych aplikacji**, aby wykonać następujące działania na nadzorowanych urządzeniach z systemem iOS 9.3 lub nowszym:

- Określić listę aplikacji, które będą ukryte dla użytkowników. Użytkownicy nie będą mogli wyświetlać ani uruchamiać tych aplikacji.
- Określić listę aplikacji, które użytkownicy mogą wyświetlać i uruchamiać. Użytkownicy nie będą mogli wyświetlać ani uruchamiać żadnych innych aplikacji.


#### <a name="how-to-create-a-hidden-or-shown-app-list"></a>Jak utworzyć listę pokazanych lub ukrytych aplikacji

Określ następujące ustawienia:

|Nazwa ustawienia|Szczegóły|
|-|-|
|**Lista ukrytych i wyświetlanych aplikacji**|Włącz to ustawienie, jeśli chcesz utworzyć listę ukrytych lub pokazanych aplikacji.|
|**Ukryj aplikacje na liście przed użytkownikami**|Wybierz tę opcję, jeśli chcesz utworzyć listę aplikacji, które będą ukryte przed użytkownikami.<br>Po utworzeniu listy tego typu wszystkie aplikacje, z wyjątkiem aplikacji systemu iOS **Ustawienia** i **Telefon** (w przypadku telefonu iPhone), będą ukryte.|
|**Pokaż użytkownikom tylko aplikacje na liście**|Wybierz tę opcję, jeśli chcesz utworzyć listę aplikacji, które będą wyświetlane dla użytkowników.<br>Po utworzeniu listy tego typu wszystkie pozostałe aplikacje systemu iOS, z wyjątkiem aplikacji **Ustawienia** i **Telefon** (w przypadku telefonu iPhone), będą ukryte.<br>Ponadto należy dodać do listy aplikację Portal firmy i wszystkie aplikacje wdrożone i zarządzane za pomocą usługi Intune.|
|**Dodaj**|Dodaje aplikację do wybranej listy.<br>W przypadku listy ukrytych należy określić **nazwę**, **wydawcę** i **adres URL aplikacji lub identyfikator pakietu** każdej aplikacji, która ma być ukryta.<br>W przypadku listy pokazanych możesz użyć polecenia **Wybierz zarządzaną aplikację**, aby wyświetlić listę aplikacji do wyboru zarządzanych przez usługę Intune. Możesz także użyć polecenia Wybierz aplikację ze sklepu i określić **nazwę**, **wydawcę** i **adres URL aplikacji lub identyfikator pakietu** każdej aplikacji, która ma być wyświetlana.|
|**Importuj aplikacje**|Importuje listę aplikacji wprowadzoną w pliku w formacie wartości rozdzielanych przecinkami. W pliku użyj formatu: nazwa aplikacji, wydawca, adres URL.|
|**Edytowanie**|Umożliwia edytowanie nazwy, wydawcy i adresu URL wybranej aplikacji.|
|**Usuwanie**|Usuwa wybraną aplikację z listy.|

#### <a name="app-information-for-built-in-ios-apps"></a>Informacje o aplikacji dla wbudowanych aplikacji systemu iOS

Użyj informacji na tej liście, aby określić nazwę, wydawcę i identyfikator pakietu dla wbudowanych aplikacji systemu iOS, które można pokazać lub ukryć. Jeśli chcesz pokazać lub ukryć wszystkie aplikacje na liście, możesz skopiować dane poniżej do pliku tekstowego z rozszerzeniem **csv**, a następnie użyć opcji **Importuj aplikacje**, aby zaimportować wszystkie aplikacje jednocześnie.

```
,com.apple.AppStore,App Store,Apple
,com.apple.calculator,Calculator,Apple
,com.apple.mobilecal,Calendar,Apple
,com.apple.camera,Camera,Apple
,com.apple.mobiletimer,Clock,Apple
,com.apple.compass,Compass,Apple
,com.apple.MobileAddressBook,Contacts,Apple
,com.apple.facetime,FaceTime,Apple
,com.apple.mobileme.fmf1,Find Friends,Apple
,com.apple.mobileme.fmip1,Find iPhone,Apple
,com.apple.gamecenter,Game Center,Apple
,com.apple.mobilegarageband,GarageBand,Apple
,com.apple.Health,Health,Apple
,com.apple.iBooks,iBooks,Apple
,com.apple.MobileStore,iTunes Store,Apple
,com.apple.itunesu,iTunes U,Apple
,com.apple.Keynote,Keynote,Apple
,com.apple.mobilemail,Mail,Apple
,com.apple.MapsMaps,Apple
,com.apple.MobileSMS,Messages,Apple
,com.apple.Music,Music,Apple
,com.apple.news,News,Apple
,com.apple.mobilenotes,Notes,Apple
,com.apple.Numbers,Numbers,Apple
,com.apple.Pages,Pages,Apple
,com.apple.Photo-Booth,Photo Booth,Apple
,com.apple.mobileslideshow,Photos,Apple
,com.apple.podcasts,Podcasts,Apple
,com.apple.reminders,Reminders,Apple
,com.apple.MobileSafari,Safari,Apple
,com.apple.Preferences,Settings,Apple
,com.apple.stocks,Stocks,Apple
,com.apple.tips,Tips,Apple
,com.apple.videos,Videos,Apple
,com.apple.VoiceMemos,VoiceMemos,Apple
,com.apple.Passbook,Wallet,Apple
,com.apple.Bridge,Watch,Apple
,com.apple.weather,Weather,Apple


```




## <a name="custom-policy-settings"></a>Ustawienia zasad niestandardowych

**Zasady niestandardowe systemu iOS** w usłudze Microsoft Intune umożliwiają wdrażanie ustawień utworzonych przy użyciu [narzędzia Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) na urządzeniach z systemem iOS. To narzędzie umożliwia tworzenie wielu ustawień do kontroli działania tych urządzeń oraz eksportowanie ich do profilu konfiguracji. Następnie można zaimportować ten profil konfiguracji do zasad niestandardowych systemu iOS w usłudze Intune i wdrożyć ustawienia dla użytkowników oraz urządzeń w swojej organizacji.

Ta funkcja umożliwia wdrażanie ustawień systemu iOS, których nie można skonfigurować przy użyciu ogólnych zasad konfiguracji usługi Intune.

### <a name="prerequisites"></a>Wymagania wstępne
Przed rozpoczęciem trzeba mieć zainstalowany program Apple Configurator i utworzony plik konfiguracji zawierający ustawienia, które mają zostać wdrożone dla użytkowników lub urządzeń. Program Apple Configurator można pobrać ze sklepu [Mac App Store](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12); można tam także znaleźć więcej informacji na jego temat.

> [!NOTE]
> Usługa Intune nie raportuje zgodności poszczególnych ustawień w zasadach niestandardowych systemu iOS. Jednak ogólna zgodność z zasadami jest raportowana.

### <a name="general-settings"></a>Ustawienia ogólne

|Nazwa ustawienia|Szczegóły|
    |----------------|--------------------|
    |**Nazwa**|Wprowadź unikatową nazwę zasad niestandardowych systemu iOS, co pomoże zidentyfikować je w konsoli usługi Intune.|
    |**Opis**|Podaj opis zawierający omówienie zasad niestandardowych systemu iOS oraz inne istotne informacje ułatwiające ich wyszukanie.|

### <a name="custom-settings"></a>Ustawienia niestandardowe

|Nazwa ustawienia|Szczegóły|
    |----------------|--------------------|
|**Nazwa niestandardowego profilu konfiguracji (wyświetlana dla użytkowników)**|Podaj nazwę zasad, która będzie wyświetlana w urządzeniu i w raportach zasad usługi Intune.|
|**Plik profilu konfiguracji**|Wybierz pozycję **Importuj**, a następnie przejdź do profilu konfiguracji utworzonego przy użyciu programu Apple Configurator. **Uwaga:** upewnij się, że ustawienia wyeksportowane z narzędzia Apple Configurator są zgodne z wersją systemu iOS na urządzeniach, na których są wdrażane niestandardowe zasady systemu iOS. Aby uzyskać informacje o sposobie postępowania w przypadku niezgodnych ustawień, wyszukaj dokumenty **Configuration Profile Reference** i **Mobile Device Management Protocol Reference** w witrynie sieci Web programu [Apple Developer](https://developer.apple.com/).|
    |**Szczegóły profilu konfiguracji**|Wyświetla kod XML zaimportowanego profilu konfiguracji.|

### <a name="see-also"></a>Zobacz także
[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
