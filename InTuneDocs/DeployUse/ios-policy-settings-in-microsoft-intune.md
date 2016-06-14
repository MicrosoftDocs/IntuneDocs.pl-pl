---
# required metadata

title: Ustawienia zasad systemu iOS w usłudze Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ab46be6c-ab73-4c99-8492-66d1dd418293

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Ustawienia zasad systemu iOS w usłudze Microsoft Intune

## Ustawienia ogólnych zasad konfiguracji

**Ogólne zasady konfiguracji systemu iOS** w usłudze Microsoft Intune umożliwiają konfigurację następujących ustawień:

-   **Ustawienia zabezpieczeń urządzenia przenośnego** — Możliwość wyboru z listy wstępnie zdefiniowanych ustawień, które pozwalają na kontrolę szeregu funkcji i funkcjonalności urządzenia.

-   **Tryb kiosku** — Blokowanie urządzenia w celu zezwolenia na działanie tylko niektórych funkcji. Na przykład można zezwolić na uruchamianie na urządzeniu tylko określonej zarządzanej aplikacji albo można wyłączyć przyciski regulacji głośności na urządzeniu. Można użyć tych ustawień dla modeli pokazowych urządzenia lub dla urządzeń przeznaczonych do wykonywania tylko jednej funkcji — na przykład urządzeń w punkcie sprzedaży.

-   **Zgodne i niezgodne aplikacje** — Określanie listy zgodnych i niezgodnych aplikacji w firmie. Na urządzeniach z systemami Android i iOS można użyć **Raportu o niezgodnych aplikacjach** , aby porównać aplikacje zainstalowane przez użytkowników z listą zgodnych aplikacji (ale nie można zablokować instalacji aplikacji).

> [!TIP]
> Można skonfigurować warunki i postanowienia dla użytkowników, aby wiedzieli oni, że aplikacje na urządzeniu, w tym również aplikacje osobiste, będą podlegały ocenie, a aplikacje niezgodne będą blokowane lub zgłaszane. Przed rejestracją urządzenia i rozpoczęciem korzystania z Portalu firmy w celu pobrania aplikacji użytkownicy muszą zaakceptować przedstawione warunki i postanowienia. Aby uzyskać więcej informacji na temat korzystania z warunków i postanowień, zobacz [Ustawienia zasad dotyczących warunków i postanowień w usłudze Microsoft Intune](terms-and-condition-policy-settings-in-microsoft-intune.md)..

Jeśli ustawienia, którego szukasz, nie ma w tym temacie, można je utworzyć za pomocą niestandardowych zasad systemu iOS, które umożliwiają importowanie ustawień utworzonych za pomocą narzędzia [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12). Aby uzyskać więcej informacji, zobacz **Ustawienia zasad niestandardowych** w dalszej części tego tematu.

### Ustawienia zabezpieczeń

|Nazwa ustawienia|Szczegóły|iOS|
|----------------|-------|
|**Wymagaj hasła do odblokowania urządzeń przenośnych**|Określ, czy użytkownicy muszą wprowadzić hasło, aby uzyskać dostęp do urządzenia.|Tak|
|**Wymagany typ hasła**|Określa typ hasła, które będzie wymagane, na przykład wyłącznie numeryczne lub alfanumeryczne.|Tak|
|**Wymagany typ hasła — Minimalna liczba zestawów znaków**|Istnieją cztery zestawów znaków: małe litery, wielkie litery, cyfry oraz symbole. To ustawienie określa, znaki z ilu zestawów znaków muszą być zawarte w haśle). Jednak w przypadku urządzeń z systemem iOS ustawienie określa liczbę znaków symbolicznych, które muszą być zawarte w haśle)|Tak|
|**Minimalna długość hasła**|Określa minimalną liczbę znaków w haśle.|Tak|
|**Zezwalaj na proste hasła**|Zezwalaj na proste hasła, takie jak „0000” i „1234”.|Tak|
|**Liczba dopuszczalnych nieudanych logowań przed wyczyszczeniem danych z urządzenia**|Czyści urządzenie po określonej liczbie prób logowania zakończonych niepowodzeniem.|Tak|
|**Czas braku aktywności (w minutach) przed wyłączeniem ekranu**<sup>1</sup>|Określ liczbę minut przed wyłączeniem ekranu urządzenia.|Tak|
|**Wygaśnięcie hasła w dniach**|Określa liczbę dni, po której należy zmienić hasło urządzenia.|Tak|
|**Pamiętaj historię haseł**|Określa, czy użytkownik może użyć poprzednio używanego hasła.|Tak|
|**Pamiętaj historię haseł** — **Zapobiegaj ponownemu używaniu poprzednich haseł**|Określa liczbę poprzednich haseł, które są zapamiętywane przez urządzenie.|Tak|
|**Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**<sup>1</sup>|Określa, jak długo urządzenie może pozostawać bezczynne, zanim użytkownik będzie musiał ponownie wprowadzić hasło.|Tak|
|**Zezwalaj na odblokowanie na podstawie linii papilarnych**|Zezwalaj na odblokowywanie urządzenia przy użyciu linii papilarnych.|System iOS 7.1 lub nowszy|
<sup>1</sup> W przypadku urządzeń z systemem iOS skonfigurowane ustawienia **Czas braku aktywności (w minutach) przed wyłączeniem ekranu** i **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**są stosowane jedno po drugim. Na przykład, jeśli wartość obu ustawień zostanie ustawiona na **5** minut, ekranie wyłączy się automatycznie po 5 minut, a urządzenie zostanie zablokowane po kolejnych 5 minutach. Jednak jeśli użytkownik wyłączy ekranie ręcznie, drugie ustawienie zostanie zastosowane natychmiast. W tym samym przykładzie, jeśli użytkownik wyłączy ekran, po 5 minutach urządzenie zostanie zablokowane.

### Ustawienia systemowe

|Nazwa ustawienia|Szczegóły|iOS|
|----------------|-------|
|**Zezwalaj na zrzut ekranu**|Zezwala użytkownikowi na przechwytywanie zawartości ekranu w formie obrazu.|Tak|
|**Zezwalaj na centrum sterowania na ekranie blokady**|Określa, czy aplikacja Centrum sterowania jest dostępna, gdy urządzenie jest zablokowane.|System iOS 7.1 lub nowszy|
|**Zezwalaj na widok powiadomienia na ekranie blokady**|Zezwalaj użytkownikowi na dostęp do widoku powiadomień bez odblokowywania urządzenia.|System iOS 7.1 lub nowszy|
|**Zezwalaj na widok dzisiejszy na ekranie blokady**|Określa, czy można wyświetlać powiadomienia, gdy urządzenie jest zablokowane.|System iOS 7.1 lub nowszy|
|**Zezwalaj na przesłanie danych diagnostycznych**|Zezwala lub blokuje możliwość przesyłania danych diagnostycznych z urządzenia do firmy Apple.|Tak|
|**Zezwalaj na niezaufane certyfikaty TLS**|Zezwalaj na niezaufane certyfikaty protokołu TLS na urządzeniu.|Tak|
|**Zezwalaj na aplikację Passbook podczas blokady**|Zezwalaj użytkownikowi na dostęp do aplikacji Passbook, gdy urządzenie jest zablokowane.|Tak|

### Ustawienia chmury — dokumenty i dane

|Nazwa ustawienia|Szczegóły|iOS|
|----------------|-------|
|**Zezwalaj na tworzenie kopii zapasowych w ramach usługi iCloud**|Zezwala użytkownikowi na tworzenie kopii zapasowych urządzenia w usłudze iCloud.|Tak|
|**Zezwalaj na synchronizowanie dokumentów w ramach usługi iCloud**|Zezwalaj na synchronizowanie dokumentów i wartości kluczy do obszaru magazynu usługi iCloud. Tak|
|**Zezwalaj na synchronizowanie strumienia zdjęć w ramach usługi iCloud**|Zezwalaj na synchronizowanie zdjęć na urządzeniu do usługi iCloud.|Tak|
|**Wymagaj zaszyfrowanej kopii zapasowej**|Wymagaj szyfrowania wszelkich kopii zapasowych urządzenia.|Tak|

### Ustawienia aplikacji — przeglądarka

|Nazwa ustawienia|Szczegóły|iOS|
|----------------|-------|
|**Zezwalaj na Safari**|Określ, czy na urządzeniu można użyć przeglądarki Safari.|Tak|
|**Zezwalaj na automatyczne uzupełnianie**|Użytkownik może zmienić ustawienia autowypełniania w przeglądarce.|Tak|
|**Zezwalaj na blokowanie wyskakujących okienek**|Włącz lub wyłącz blokowanie wyskakujących okienek w przeglądarce.|Tak|
|**Zezwalaj na pliki cookie**|Zezwalaj na używanie plików cookie przez przeglądarkę sieci Web urządzenia.|Tak|
|**Zezwalaj na wykonywanie skryptów Java**|Zezwalaj na uruchamianie skryptów Java w przeglądarce.|Tak|
|**Zezwalaj na ostrzeżenia o oszustwie**|Zezwalaj na ostrzeżenia o oszustwie w przeglądarce urządzenia.|Tak|

### Ustawienia aplikacji — aplikacje

|Nazwa ustawienia|Szczegóły|iOS|
|----------------|-------|
|**Zezwalaj na korzystanie ze sklepu z aplikacjami**|Umożliwia dostęp do sklepu z aplikacjami z poziomu urządzenia.|Tak|
|**Wymagaj hasła w celu dostępu do sklepu z aplikacjami**|Tak|
|**Zezwalaj na zakupy w aplikacji**|Zezwalaj na zakupy w sklepie dokonywane w uruchomionej aplikacji.|Tak|
|**Zezwalaj na zarządzane dokumenty w innych niezarządzanych aplikacjach**|Zezwala na wyświetlanie dokumentów firmowych w dowolnej aplikacji.|System iOS 7.1 lub nowszy|
|**Zezwalaj na niezarządzane dokumenty w innych zarządzanych aplikacjach**|Zezwalaj na wyświetlanie dowolnych dokumentów w zarządzanych aplikacjach firmowych.|System iOS 7.1 lub nowszy|
|**Zezwalaj na wideokonferencje**|Zezwalaj na użycie aplikacji do obsługi wideokonferencji, takiej jak Facetime, w urządzeniu.|Tak|
|**Zezwala na zawartość dla dorosłych w sklepie z multimediami**|Zezwalaj urządzeniu na dostęp do zawartości w sklepie sklasyfikowanej jako zawartość dla dorosłych.|Tak|

### Ustawienia aplikacji — gry

|Nazwa ustawienia|Szczegóły|iOS|
|----------------|-------|
|**Zezwalaj na dodawanie przyjaciół z programu Game Center**|Zezwalaj użytkownikowi na dodawanie przyjaciół w Centrum gier.|Tak|
|**Zezwalaj na gry dla wielu graczy**|Zezwalaj użytkownikowi na gry dla wielu graczy w urządzeniu.|Tak|

### Ustawienia możliwości urządzenia — sprzęt

|Nazwa ustawienia|Szczegóły|iOS|
|----------------|-------|
|**Zezwalaj na używanie aparatu**|Określa, czy można używać aparatu w urządzeniu.|Tak|

### Ustawienia możliwości urządzenia — połączenie komórkowe

|Nazwa ustawienia|Szczegóły|iOS|
|----------------|-------|
|**Zezwalaj na roaming połączeń głosowych**|Zezwalaj na roaming połączeń głosowych, gdy urządzenie jest w sieci komórkowej.|Tak|
|**Zezwalaj na roaming danych**|Zezwalaj na roaming danych, gdy urządzenie korzysta z sieci komórkowej.|Tak|
|**Zezwalaj na globalne pobieranie w tle podczas roamingu**|Zezwalaj urządzeniu na pobieranie danych, np. wiadomości e-mail, w roamingu w sieci komórkowej.|Tak|

### Ustawienia możliwości urządzenia — funkcje

|Nazwa ustawienia|Szczegóły|iOS|
|----------------|-------|
|**Zezwalaj na Siri**|Zezwalaj na korzystanie z asystenta głosowego Siri w urządzeniu.|Tak|
|**Zezwalaj na Siri, gdy urządzenie jest zablokowane**|Zezwalaj na korzystanie z asystenta głosowego Siri w urządzeniu, gdy urządzenie jest zablokowane.|Tak|
|**Zezwalaj na wybieranie głosowe**|Zezwalaj na korzystanie z funkcji wybierania głosowego w urządzeniu.|Tak|


### Ustawienia dotyczące aplikacji zgodnych i niezgodnych
Na liście **Zgodne i niezgodne aplikacje** określ listę zgodnych i niezgodnych aplikacji, korzystając z poniższych informacji:

> [!NOTE]
> W ramach jednych zasad można określić wyłącznie listę zgodnych lub wyłącznie listę niezgodnych aplikacji. Nie można wprowadzić obu list w ramach jednych zasad.

|Nazwa ustawienia|Szczegóły|
|----------------|--------------------|
|**Zgłaszaj niezgodność, gdy użytkownicy instalują aplikacje z listy**|Tworzy listę aplikacji niezarządzanych przez usługę Intune, których użytkownicy nie mogą instalować i uruchamiać.|
|**Nie zgłaszaj niezgodności, gdy użytkownicy instalują aplikacje z listy**|Tworzy listę aplikacji, które użytkownicy mogą instalować. Aby utrzymać zgodność, użytkownicy nie mogą instalować aplikacji, których nie ma na liście. Aplikacje zarządzane przez usługę Intune są automatycznie traktowane jako dozwolone.|
|**Dodaj**|Dodaje aplikację do wybranej listy. Wprowadź wybraną nazwę, opcjonalnie wydawcę aplikacji, a także adres URL aplikacji w sklepie z aplikacjami. Zobacz sekcję **Jak określać adresy URL sklepów z aplikacjami** w dalszej części tego tematu, aby uzyskać pomoc.|
|**Importuj aplikacje**|Importuje listę aplikacji wprowadzoną w pliku w formacie wartości rozdzielanych przecinkami. W pliku użyj formatu: nazwa aplikacji, wydawca, adres URL.|
|**Edytowanie**|Umożliwia edytowanie nazwy, wydawcy i adresu URL wybranej aplikacji.|
|**Usuwanie**|Usuwa wybraną aplikację z listy.|

### Ustawienia trybu kiosku

|Nazwa ustawienia|Szczegóły|
|----------------|--------------------|
|**Wybierz zarządzaną aplikację, która będzie mogła działać na urządzeniu w trybie kiosku**|Kliknij pozycję **Przeglądaj**, a następnie wskaż zarządzaną aplikację lub aplikację ze sklepu, która będzie mogła działać na urządzeniu w trybie kiosku. Na tym urządzeniu nie będzie można uruchamiać żadnych innych aplikacji. Aby uzyskać pomoc, zobacz **Jak określać adresy URL sklepów z aplikacjami** w dalszej części tego tematu.|
|**Zezwalaj na obsługę dotykową**|Włącza lub wyłącza ekran dotykowy na urządzeniu.|
|**Zezwalaj na obracanie ekranu**|Włącza lub wyłącza zmianę orientacji ekranu podczas obracania urządzenia.|
|**Zezwalaj na używanie przycisków regulacji głośności**|Włącza lub wyłącza przyciski regulacji głośności na urządzeniu.|
|**Zezwalaj na przełączanie dzwonka**|Włącza lub wyłącza przełączanie dzwonka (wyciszanie) na urządzeniu.|
|**Zezwalaj na używanie przycisku usypiania/budzenia ekranu**|Włącza lub wyłącza przycisk usypiania/budzenia ekranu na urządzeniu.|
|**Zezwalaj na automatyczne blokowanie**|Włącza lub wyłącza automatyczne blokowanie urządzenia.|
|**Włącz dźwięk mono**|Włącza lub wyłącza ustawienie ułatwień dostępu **Dźwięk mono**..|
|**Włącz lektora**|Włącza lub wyłącza funkcję ułatwień dostępu **VoiceOver** , która odczytuje na głos tekst wyświetlany na ekranie urządzenia.|
|**Włącz korektę lektora**|Włącza lub wyłącza ustawienia funkcji VoiceOver (na przykład możliwość ustawienia tempa odczytywania tekstu z ekranu).|
|**Włącz powiększenie**|Włącza lub wyłącza funkcję ułatwień dostępu **Zoom** umożliwiającą powiększenie fragmentu ekranu urządzenia za pomocą gestu.|
|**Włącz korektę powiększenia**|Włącza lub wyłącza ustawienia funkcji Zoom.|
|**Włącz odwrócone kolory**|Włącza lub wyłącza funkcję ułatwień dostępu **Odwróć kolory** dostosowującą wyświetlany obraz do potrzeb użytkowników niedowidzących.|
|**Włącz korektę odwróconych kolorów**|Włącza lub wyłącza ustawienia funkcji Odwróć kolory.|
|**Włącz obsługę dotykową z ułatwieniami**|Włącza lub wyłącza funkcję ułatwień dostępu **Assistive Touch** , która umożliwia użytkownikom wykonywanie trudnych dla nich gestów na ekranie.|
|**Włącz korektę obsługi dotykowej z ułatwieniami**|Włącza lub wyłącza ustawienia funkcji Assistive Touch.|
|**Włącz wybór mowy**|Włącza lub wyłącza funkcję ułatwień dostępu **wyboru mowy** , dzięki której zaznaczony tekst może zostać odczytany na głos przez urządzenie.|
> [!NOTE]
> Poniższe uwagi dotyczą ustawień trybu kiosku dla urządzeń z systemem iOS:
> 
> -   Aby można było skonfigurować tryb kiosku dla urządzenia z systemem iOS, należy najpierw użyć [narzędzia Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) lub menedżera rejestracji urządzeń w celu uruchomienia trybu nadzorowanego na tym urządzeniu. Aby uzyskać więcej informacji o narzędziu Apple Configurator, skorzystaj z dokumentacji firmy Apple.
> -   Jeśli wskazana aplikacja dla systemu iOS zostanie zainstalowana po wdrożeniu zasad konfiguracji, urządzenie przejdzie do trybu kiosku dopiero po ponownym uruchomieniu.

### Informacje o odwołaniu dotyczące aplikacji zgodnych i niezgodnych

#### Monitoruj aplikacje zgodne i niezgodne
Użyj **Raportu o niezgodnych aplikacjach** , aby wyświetlić zgodność dozwolonych i blokowanych aplikacji.

##### Aby uruchomić raport o niezgodnych aplikacjach

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) kliknij pozycję **Raporty** &gt; **Raport o niezgodnych aplikacjach**.

2.  Wybierz grupy urządzeń, które chcesz sprawdzić, określ, czy sprawdzić aplikacje zgodne, niezgodne czy oba rodzaje, a następnie kliknij pozycję **Wyświetl raport**..

#### Jak określać adresy URL sklepów z aplikacjami
Aby określić adres URL na liście zgodnych i niezgodnych aplikacji lub w opcji **Wybierz zarządzaną aplikację, która będzie mogła działać na urządzeniu w trybie kiosku** (tylko iOS), użyj następującego formatu:

Korzystając z wyszukiwarki, znajdź w sklepie iTunes aplikację, której chcesz użyć, i otwórz jej stronę.

Skopiuj adres URL strony i użyj go jako adresu URL do skonfigurowania listy zgodnych lub niezgodnych aplikacji lub aplikacji, która będzie działać w trybie kiosku.

**Przykład:** Wyszukaj aplikację **Microsoft Word dla tabletu iPad**. Adres URL, którego użyjesz, to **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**..

> [!NOTE]
> Możesz również znaleźć aplikację za pomocą programu iTunes, a następnie użyć polecenia **Kopiuj link** , aby uzyskać adres URL aplikacji.


## Ustawienia zasad niestandardowych

**Zasady niestandardowe systemu iOS** w usłudze Microsoft Intune umożliwiają wdrażanie ustawień utworzonych przy użyciu [narzędzia Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) na urządzeniach z systemem iOS. To narzędzie umożliwia tworzenie wielu ustawień do kontroli działania tych urządzeń oraz eksportowanie ich do profilu konfiguracji. Następnie można zaimportować ten profil konfiguracji do zasad niestandardowych systemu iOS w usłudze Intune i wdrożyć ustawienia dla użytkowników oraz urządzeń w swojej organizacji.

Ta funkcja ma umożliwić wdrażanie ustawień systemu iOS, których nie można skonfigurować przy użyciu zasad ogólnych konfiguracji usługi Intune.

### Wymagania wstępne
Przed rozpoczęciem trzeba mieć zainstalowany program Apple Configurator i utworzony plik konfiguracji zawierający ustawienia, które mają zostać wdrożone dla użytkowników lub urządzeń. Program Apple Configurator można pobrać ze sklepu [Mac App Store](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12), można tam także znaleźć więcej informacji na jego temat.

> [!NOTE]
> Usługa Intune nie raportuje zgodności poszczególnych ustawień w zasadach niestandardowych systemu iOS. Jednak ogólna zgodność z zasadami jest raportowana.

### Ustawienia ogólne

|Nazwa ustawienia|Szczegóły|
    |----------------|--------------------|
    |**Nazwa**|Wprowadź unikatową nazwę zasad niestandardowych systemu iOS, co pomoże zidentyfikować je w konsoli usługi Intune.|
    |**Opis**|Podaj opis zawierający omówienie zasad niestandardowych systemu iOS oraz inne istotne informacje ułatwiające ich wyszukanie.|

### Ustawienia niestandardowe

|Nazwa ustawienia|Szczegóły|
    |----------------|--------------------|
|**Nazwa niestandardowego profilu konfiguracji (wyświetlana dla użytkowników)**|Podaj nazwę zasad, która będzie wyświetlana w urządzeniu i w raportach zasad usługi Intune.|
|**Plik profilu konfiguracji**|Kliknij przycisk **Importuj**, następnie przejdź do profilu konfiguracji utworzonego przy użyciu programu Apple Configurator. **Uwaga:** upewnij się, że ustawienia wyeksportowane z narzędzia Apple Configurator są zgodne z wersją systemu iOS na urządzeniach, na których są wdrażane niestandardowe zasady systemu iOS. Aby uzyskać informacje o sposobie postępowania w przypadku niezgodnych ustawień, wyszukaj dokumenty **Configuration Profile Reference** i **Mobile Device Management Protocol Reference** w witrynie sieci Web [Apple Developer](https://developer.apple.com/).|
    |**Szczegóły profilu konfiguracji**|Wyświetla kod XML zaimportowanego profilu konfiguracji.|

### Zobacz także
[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->


