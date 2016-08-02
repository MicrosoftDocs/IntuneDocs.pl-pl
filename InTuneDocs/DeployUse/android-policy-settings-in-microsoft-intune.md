---

title: Ustawienia zasad konfiguracji systemu Android i Samsung KNOX | Microsoft Intune
description: "Utwórz zasady określające ustawienia i funkcje na urządzeniach z systemem Android zarządzanych za pomocą usługi Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71cc39cf-e726-40fd-8d08-78776e099a4b
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6e3e81f37e677a016ac49240cc70602a568afcd5
ms.openlocfilehash: 9385ca0e5aa9dd8fc2daf79c57b47951bcd5c0cb


---

# Ustawienia zasad konfiguracji systemu Android i Samsung KNOX w usłudze Microsoft Intune

Usługa Intune udostępnia szereg wbudowanych ustawień ogólnych, które można skonfigurować na urządzeniach z systemem Android. Ponadto można określić wartości jednolitego identyfikatora zasobów organizacji Open Mobile Alliance (OMA-URI), aby utworzyć ustawienia niestandardowe, które nie są dostępne w usłudze Intune.

## Ogólne zasady konfiguracji

**Ogólne zasady konfiguracji systemu Android** w usłudze Intune umożliwiają konfigurację ustawień dla:

-   **Ustawienia zabezpieczeń urządzenia przenośnego** — Możliwość wyboru z listy wstępnie zdefiniowanych ustawień, które pozwalają na kontrolę szeregu funkcji i funkcjonalności urządzenia.

-   **Tryb kiosku** (tylko w przypadku urządzeń Samsung KNOX) — Możliwość blokowania urządzenia w celu zezwolenia na działanie tylko niektórych funkcji. Na przykład można zezwolić na uruchamianie na urządzeniu tylko określonej zarządzanej aplikacji albo można wyłączyć przyciski regulacji głośności na urządzeniu. Można użyć tych ustawień dla modeli pokazowych urządzenia lub dla urządzeń przeznaczonych do wykonywania tylko jednej funkcji — na przykład urządzeń w punkcie sprzedaży.

-   **Zgodne i niezgodne aplikacje** — Określanie listy zgodnych i niezgodnych aplikacji w firmie. Na urządzeniach z systemami Android i iOS można użyć **Raportu o niezgodnych aplikacjach**, aby porównać aplikacje zainstalowane przez użytkowników z listą zgodnych aplikacji. Raport nie może faktycznie zablokować instalacji aplikacji.

> [!TIP]
> Można skonfigurować warunki i postanowienia dla użytkowników, aby wiedzieli oni, że aplikacje na urządzeniu, w tym również aplikacje osobiste, będą podlegały ocenie, a aplikacje niezgodne będą blokowane lub zgłaszane. Przed rejestracją urządzenia i rozpoczęciem korzystania z Portalu firmy w celu pobrania aplikacji użytkownicy muszą zaakceptować przedstawione warunki i postanowienia. Aby uzyskać więcej informacji na temat korzystania z warunków i postanowień, zobacz [Ustawienia zasad dotyczących warunków i postanowień w usłudze Microsoft Intune](terms-and-condition-policy-settings-in-microsoft-intune.md).

Jeśli w tym temacie nie opisano ustawienia, którego szukasz, możesz mieć możliwość utworzenia go za pomocą niestandardowych zasad systemu Android, które pozwalają sterować urządzeniem za pomocą ustawień OMA-URI. Aby uzyskać więcej informacji, przejdź do sekcji [Ustawienia zasad niestandardowych](#custom-policy-settings) w dalszej części tego tematu.

### Ustawienia hasła

|Nazwa ustawienia|Szczegóły|Android 4.0+|Samsung KNOX|
|----------------|-|----------------|----------------|
|**Wymagaj hasła do odblokowania urządzeń przenośnych**|Określa, czy należy wymagać hasła na obsługiwanych urządzeniach.|Tak|Tak|
|**Minimalna długość hasła**|Określa minimalną długość hasła.|Tak|Tak|
|**Liczba dopuszczalnych nieudanych logowań przed wyczyszczeniem danych z urządzenia**|Określa liczbę dopuszczalnych nieudanych logowań przed wyczyszczeniem danych z urządzenia.|Tak|Tak|
|**Czas braku aktywności (w minutach) przed wyłączeniem ekranu**|Określa liczbę minut braku aktywności przed automatycznym zablokowaniem urządzenia.|Tak|Tak|
|**Wygaśnięcie hasła (dni)**|Określa liczbę dni, po której należy zmienić hasło.|Tak|Tak|
|**Pamiętaj historię haseł**|Określa liczbę wcześniej używanych haseł do zapamiętania.|Tak|Tak|
|**Pamiętaj historię haseł** - **Zapobiegaj ponownemu używaniu poprzednich haseł**|Zapobiega ponownemu używaniu poprzednich haseł.|Tak|Tak|
|**Jakość hasła**|Określa wymagany poziom złożoności hasła oraz możliwość stosowania urządzeń biometrycznych.|Tak|Tak|
|**Zezwalaj na odblokowanie na podstawie linii papilarnych**|Umożliwia odblokowywanie urządzenia przy użyciu linii papilarnych.|Nie|Tak|
|**Zezwalaj na użycie blokady inteligentnej i innych agentów zaufania**<br>(system Android 5 i nowsze)|Umożliwia sterowanie funkcją blokady inteligentnej na zgodnych urządzeniach z systemem Android. Ta funkcja telefonu, czasami znana jako funkcja agentów zaufania, umożliwia wyłączenie lub obejście hasła ekranu blokady urządzenia, jeśli urządzenie jest w zaufanej lokalizacji (np. gdy zostało podłączone do danego urządzenia Bluetooth lub znajduje się w pobliżu tagu NFC). Możesz użyć tego ustawienia, aby uniemożliwić użytkownikom konfigurowanie funkcji blokady inteligentnej.|Tak|Nie|

### Ustawienia szyfrowania

|Nazwa ustawienia|Szczegóły|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Wymagaj szyfrowania na urządzeniu przenośnym**|Wymaga szyfrowania plików na urządzeniu przenośnym.|Tak|Tak|
|**Wymagaj szyfrowania kart pamięci**|Określa, czy karta pamięci urządzenia musi być szyfrowana.|Nie|Tak|

### Ustawienia systemowe

|Nazwa ustawienia|Szczegóły|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Zezwalaj na przechwytywanie ekranu**|Umożliwia użytkownikowi przechwytywanie zawartości ekranu w formie obrazu.|Nie|Tak|
|**Zezwalaj na przesłanie danych diagnostycznych**|Umożliwia urządzeniu przesyłanie danych diagnostycznych do firmy Google.|Nie|Tak|
|**Zezwalaj na resetowanie do ustawień fabrycznych**|Umożliwia użytkownikowi przeprowadzenie resetowania urządzenia do ustawień fabrycznych.|Nie|Tak|

### Ustawienia chmury — dokumenty i dane

|Nazwa ustawienia|Szczegóły|Android 4.0+|Samsung KNOX|
|----------------|----------------------------|----------------|
|**Zezwalaj na kopie zapasowe w usłudze Google**|Zezwala na korzystanie z kopii zapasowej Google.|Nie|Tak|

### Ustawienia chmury — konta i synchronizacja

|Nazwa ustawienia|Szczegóły|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Zezwalaj na automatyczną synchronizację konta Google**|Zezwala na automatyczną synchronizację ustawień konta Google.|Nie|Tak|

### Ustawienia aplikacji — przeglądarka

|Nazwa ustawienia|Szczegóły|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Zezwalaj na używanie przeglądarki sieci Web**|Określa, czy można używać domyślnej przeglądarki sieci Web na urządzeniu.|Nie|Tak|
|**Zezwalaj na automatyczne uzupełnianie**|Umożliwia korzystanie z funkcji automatycznego uzupełniania w przeglądarce sieci Web.|Nie|Tak|
|**Zezwalaj na blokowanie wyskakujących okienek**|Umożliwia blokowanie wyskakujących okienek w przeglądarce sieci Web.|Nie|Tak|
|**Zezwalaj na pliki cookie**|Zezwala na używanie plików cookie przez przeglądarkę sieci Web urządzenia.|Nie|Tak|
|**Zezwalaj na wykonywanie aktywnych skryptów**|Umożliwia używanie aktywnych skryptów przez przeglądarkę sieci Web urządzenia.|Nie|Tak|

### Ustawienia aplikacji — aplikacje

|Nazwa ustawienia|Szczegóły|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Zezwalaj na sklep Google Play**|Umożliwia użytkownikowi uzyskiwanie dostępu do sklepu Google Play na urządzeniu.|Nie|Tak|

### Ustawienia możliwości urządzenia — sprzęt

|Nazwa ustawienia|Szczegóły|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Zezwalaj na używanie aparatu**|Zezwala na korzystanie z aparatu fotograficznego urządzenia.|Tak|Tak|
|**Zezwalaj na używanie magazynu wymiennego**|Umożliwia używanie na urządzeniu magazynu wymiennego, takiego jak karta SD.|Nie|Tak|
|**Zezwalaj na połączenia Wi-Fi**|Umożliwia korzystanie z funkcji Wi-Fi urządzenia.|Nie|Tak|
|**Zezwalaj na tethering Wi-Fi**|Umożliwia korzystanie z funkcji tetheringu Wi-Fi urządzenia.|Nie|Tak|
|**Zezwalaj na używanie funkcji geolokalizacji**|Umożliwia urządzeniu korzystanie z informacji o lokalizacji.|Nie|Tak|
|**Zezwalaj na komunikację NFC**|Umożliwia wykonywanie operacji korzystających z komunikacji zbliżeniowej (NFC), jeśli urządzenie ją obsługuje.|Nie|Tak|
|**Zezwalaj na połączenia Bluetooth**|Umożliwia używanie połączeń Bluetooth na urządzeniu.|Nie|Tak|
|**Zezwalaj na wyłączenie urządzenia**|Umożliwia użytkownikowi wyłączanie urządzenia.<br /><br />Jeśli to ustawienie jest wyłączone, ustawienie **Liczba dopuszczalnych nieudanych logowań przed wyczyszczeniem danych z urządzenia** dla urządzeń z systemem Samsung KNOX nie działa.|Nie|Tak|

### Ustawienia możliwości urządzenia — połączenie komórkowe

|Nazwa ustawienia|Szczegóły|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Zezwalaj na roaming połączeń głosowych**|Zezwala na roaming połączeń głosowych, gdy urządzenie jest w sieci komórkowej.|Nie|Tak|
|**Zezwalaj na roaming danych**|Zezwala na roaming danych, gdy urządzenie jest w sieci komórkowej.|Nie|Tak|
|**Zezwalaj na obsługę wiadomości SMS/MMS**|Umożliwia korzystanie z wiadomości SMS i MMS na urządzeniu.|Nie|Tak|

### Ustawienia możliwości urządzenia — funkcje

|Nazwa ustawienia|Szczegóły|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Zezwalaj na asystenta głosowego**|Umożliwia korzystanie z oprogramowania asystenta głosowego na urządzeniu.|Nie|Tak|
|**Zezwalaj na wybieranie głosowe**|Włącza lub wyłącza funkcję wybierania głosowego na urządzeniu.|Nie|Tak|
|**Zezwalaj na kopiowanie i wklejanie**|Umożliwia używanie funkcji kopiowania i wklejania na urządzeniu.|Nie|Tak|
|**Zezwalaj na udostępnianie Schowka między aplikacjami**|Umożliwia wykorzystanie schowka do kopiowania i wklejania danych między aplikacjami.|Nie|Tak|
|**Zezwalaj na YouTube**|Umożliwia korzystanie z serwisu YouTube na urządzeniu.|Nie|Tak|

### Ustawienia dotyczące aplikacji zgodnych i niezgodnych
Na liście **Zgodne i niezgodne aplikacje** określ listę zgodnych i niezgodnych aplikacji, korzystając z poniższych informacji:

> [!NOTE]
> W ramach jednych zasad można określić wyłącznie listę zgodnych lub wyłącznie listę niezgodnych aplikacji. Nie można wprowadzić obu list w ramach jednych zasad.

|Nazwa ustawienia|Szczegóły|
|----------------|--------------------|
|**Zgłaszaj niezgodność, gdy użytkownicy instalują aplikacje z listy**|Tworzy listę aplikacji niezarządzanych przez usługę Intune, które nie mają być instalowane i uruchamiane przez użytkowników. Jeśli użytkownicy zainstalują dowolną z tych aplikacji, taka informacja znajdzie się w raporcie o niezgodnych aplikacjach.|
|**Nie zgłaszaj niezgodności, gdy użytkownicy instalują aplikacje z listy**|Wyświetla listę aplikacji, na których używanie chcesz zezwolić. Aby utrzymać zgodność, użytkownicy nie mogą instalować aplikacji, których nie ma na tej liście. Aplikacje zarządzane przez usługę Intune są automatycznie traktowane jako dozwolone.|
|**Dodaj**|Dodaje aplikację do wybranej listy. Wprowadź nazwę aplikacji, opcjonalnie wydawcę aplikacji, a także adres URL aplikacji w sklepie z aplikacjami.<br /><br />Aby uzyskać więcej informacji, zobacz sekcję [Jak określać adresy URL sklepów z aplikacjami](#specify-urls-to-app-stores) w dalszej części tego tematu.|
|**Importuj aplikacje**|Importuje listę aplikacji wprowadzoną w pliku w formacie wartości rozdzielanych przecinkami. W pliku użyj formatu: nazwa aplikacji, wydawca, adres URL.|
|**Edytowanie**|Umożliwia edytowanie nazwy, wydawcy i adresu URL wybranej aplikacji.|
|**Usuwanie**|Usuwa wybraną aplikację z listy.|

### Ustawienia trybu kiosku
Określ następujące ustawienia dla **urządzeń z systemem Samsung KNOX**:

|Nazwa ustawienia|Szczegóły|
|----------------|--------------------|
|**Wybierz zarządzaną aplikację, która może działać na urządzeniu w trybie kiosku**|Wybierz pozycję **Przeglądaj**, a następnie wybierz zarządzaną aplikację, która może działać na urządzeniu w trybie kiosku. Aplikacje określone jako link do sklepu nie są aktualnie obsługiwane. Na tym urządzeniu nie będzie można uruchamiać żadnych innych aplikacji.|
|**Zezwalaj na używanie przycisków regulacji głośności**|Włącza lub wyłącza przyciski regulacji głośności na urządzeniu.|
|**Zezwalaj na używanie przycisku usypiania/budzenia ekranu**|Włącza lub wyłącza przycisk usypiania/budzenia ekranu na urządzeniu.|

### Informacje o odwołaniu dotyczące aplikacji zgodnych i niezgodnych

#### Monitoruj aplikacje zgodne i niezgodne
Użyj **Raportu o niezgodnych aplikacjach**, aby wyświetlić zgodność dozwolonych i blokowanych aplikacji.

###### Aby uruchomić raport o niezgodnych aplikacjach

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) kliknij pozycję **Raporty** &gt; **Raport o niezgodnych aplikacjach**.

2.  Wybierz grupy urządzeń, które chcesz sprawdzić. Następnie wybierz, czy chcesz sprawdzić aplikacje zgodne, aplikacje niezgodne, czy oba typy aplikacji. Na końcu wybierz opcję **Wyświetl raport**.

#### Jak określać adresy URL sklepów z aplikacjami
Aby określić adres URL aplikacji na liście aplikacji zgodnych i niezgodnych, wykonaj następujące działania:

W sekcji [Aplikacje w sklepie Google Play](https://play.google.com/store/apps) wyszukaj aplikację, której chcesz użyć.

Otwórz stronę instalacji aplikacji i skopiuj jej adres URL do schowka. Możesz teraz użyć tego adresu URL na liście zgodnych lub niezgodnych aplikacji.

Przykład: wyszukaj w sklepie Google Play aplikację Microsoft Office Mobile. Adres URL, którego użyjesz, to **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

## Ustawienia zasad niestandardowych
**Niestandardowe zasady konfiguracji systemu Android** w usłudze Microsoft Intune umożliwiają wdrożenie ustawień OMA-URI, których można użyć do sterowania funkcjami na urządzeniach z systemem Android. Są to ustawienia standardowe używane przez wielu producentów urządzeń przenośnych do sterowania funkcjami urządzeń.

Ta funkcja ma umożliwić wdrażanie ustawień systemu Android, których nie można skonfigurować przy użyciu zasad usługi Intune.

> [!NOTE]
> Obecnie zasady niestandardowe systemu Android obsługują tylko konfigurowanie ustawień Wi-Fi dla urządzeń z systemem Android, które obejmują klucz wstępny.

### Ustawienia ogólne

|Nazwa ustawienia|Szczegóły|
    |----------------|--------------------|
    |**Nazwa**|Wprowadź unikatową nazwę niestandardowych zasad systemu Android, która pomoże je zidentyfikować w konsoli usługi Intune.|
    |**Opis**|Podaj opis zawierający omówienie zasad niestandardowych systemu Android oraz inne istotne informacje ułatwiające ich wyszukanie.|

### Ustawienia OMA-URI

   |Nazwa ustawienia|Szczegóły|
    |--------|--------------------|
    |**Nazwa ustawienia**|Wprowadź unikatową nazwę dla ustawienia OMA-URI, aby ułatwić jego identyfikację  na liście ustawień.|
    |**Opis ustawienia**|Podaj opis, który zawiera omówienie ustawienia oraz inne istotne informacje, które ułatwią jego wyszukanie.|
    |**Typ danych**|Wybierz typ danych, zgodnie z którym określisz to ustawienie OMA-URI. Wybierz jedną z opcji: **Ciąg, Ciąg (XML), Data i godzina, Liczba całkowita, Liczba zmiennoprzecinkowa** lub **Wartość logiczna**.|
    |**OMA-URI (z uwzględnieniem wielkości liter)**|Określ identyfikator OMA-URI, dla którego chcesz podać ustawienie.|
    |**Wartość**|Określ wartość, która będzie kojarzona z określonym wcześniej identyfikatorem OMA-URI.|

### Przykład: konfigurowanie niestandardowego profilu Wi-Fi z użyciem klucza wstępnego
Chociaż usługa Intune obsługuje profile Wi-Fi dla urządzeń z systemem Android, funkcja ta nie obsługuje obecnie uwzględniania klucza wstępnego w konfiguracji. W tym przykładzie dowiesz się, jak utworzyć zasady niestandardowe systemu Android umożliwiające tworzenie profilu Wi-Fi z użyciem klucza wstępnego na urządzeniu Android.

#### Aby utworzyć profil Wi-Fi z użyciem klucza wstępnego

1.  Upewnij się, że użytkownicy korzystają z najnowszej wersji aplikacji [Portal firmy w usłudze Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) dla systemu Android.

2.  Utwórz niestandardowe zasady systemu Android i dodaj następujące ustawienia:

|Nazwa ustawienia|Szczegóły|
|----------------|--------------------|
|**Nazwa ustawienia**|Określ nazwę ustawienia.|
|**Opis ustawienia**|Określ opis ustawienia.|
|**Typ danych**|Wybierz pozycję **Ciąg (XML)**.|
|**OMA-URI**|Wpisz następujący ciąg: ./Vendor/MSFT/WiFi/Profile/*&lt;Twój profil Wi-Fi&gt;*/Settings|

3.  W polu **Wartość** skopiuj i wklej następujący kod XML:

    ```
    <!--
    WEP Wifi Profile
                    <Name of wifi profile> = Name of profile
                    <SSID of wifi profile> = Plain text version of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
                    <WEP password> = Password to connect to the network
    -->
    <WLANProfile
    xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
      <name><Name of wifi profile></name>
      <SSIDConfig>
        <SSID>
          <name><SSID of wifi profile></name>
        </SSID>
      </SSIDConfig>
      <connectionType>ESS</connectionType>
      <MSM>
        <security>
          <authEncryption>
            <authentication>open</authentication>
            <encryption>WEP</encryption>
            <useOneX>false</useOneX>
          </authEncryption>
          <sharedKey>
            <keyType>networkKey</keyType>
            <protected>false</protected>
            <keyMaterial><WEP password></keyMaterial>
          </sharedKey>
          <keyIndex>0</keyIndex>
        </security>
      </MSM>
    </WLANProfile>
    ```

4.  Po zakończeniu zapisz zasady, a następnie wdróż je na wybranych urządzeniach z systemem Android. Nowy profil Wi-Fi pojawi się na liście połączeń na urządzeniu.

### Zobacz także
[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Jul16_HO4-->


