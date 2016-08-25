---
title: Ustawienia zasad systemu Windows Phone 8.1 | Microsoft Intune
description: "Usługa Intune udostępnia szereg wbudowanych ustawień ogólnych, które można skonfigurować na urządzeniach z systemem Windows Phone 8.1. Ponadto można określić wartości OMA-URI, aby utworzyć ustawienia niestandardowe, które nie są dostępne w usłudze Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 83f7469c-272e-43f2-8139-b0d7bc34f43f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4279ecd098ddaa6d6eb239ee71f9c3f7d450ab3f
ms.openlocfilehash: f2ccc52ceae6bbb63ea76ff4391922099c69f4dd


---

# Ustawienia zasad systemu Windows Phone 8.1 w usłudze Microsoft Intune

Usługa Intune udostępnia szereg wbudowanych ustawień ogólnych, które można skonfigurować na urządzeniach z systemem Windows Phone 8.1. Ponadto można określić wartości jednolitego identyfikatora zasobów organizacji Open Mobile Alliance (OMA-URI), aby utworzyć ustawienia niestandardowe, które nie są dostępne w usłudze Intune.

## Ogólne ustawienia konfiguracji

**Ogólne zasady konfiguracji systemu Windows Phone w usłudze Intune (system Windows Phone 8.1 i nowsze)** umożliwiają konfigurowanie następujących ustawień urządzeń z systemem Windows Phone 8.1:

-   **Ustawienia zabezpieczeń urządzenia przenośnego** — Możliwość wyboru z listy wstępnie zdefiniowanych ustawień, które pozwalają na kontrolę szeregu funkcji i funkcjonalności urządzenia.

-   **Zgodne i niezgodne aplikacje** — określanie listy zgodnych lub niezgodnych aplikacji w firmie. Urządzenia z systemem Windows Phone mogą blokować instalację tych aplikacji lub zezwalać na nią.

### Ustawienia zastosowania

|Nazwa ustawienia|Szczegóły|
|----------------|----------------------------------|
|**Zastosuj wszystkie konfiguracje dla systemu Windows 10**|Umożliwia zastosowanie ustawień tych zasad również na urządzeniach z systemem Windows 10 Mobile, a nie tylko na urządzeniach z systemem Windows 8.1.|

### Ustawienia hasła

|Nazwa ustawienia|Szczegóły|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Wymagaj hasła do odblokowania urządzeń przenośnych**|Określa, czy użytkownicy muszą wprowadzić hasło, aby uzyskać dostęp do swoich urządzeń.|Tak|Tak|
|**Wymagany typ hasła**|Określa typ hasła, które będzie wymagane, na przykład alfanumeryczne lub tylko liczbowe.|Tak|Tak|
|**Wymagany typ hasła — Minimalna liczba zestawów znaków**|Określa, z ilu różnych zestawów znaków muszą pochodzić znaki zawarte w haśle. Istnieją cztery zestawy znaków: małe litery, wielkie litery, cyfry oraz symbole. Jednak w przypadku urządzeń z systemem iOS ustawienie określa liczbę symboli, które muszą być zawarte w haśle.|Tak|Tak|
|**Minimalna długość hasła**|Określa minimalną wymaganą liczbę znaków w haśle.|Tak|Tak|
|**Zezwalaj na proste hasła**|Określa, czy można używać prostych haseł, takich jak ciągi „0000” i „1234”.|Tak|Tak|
|**Liczba dopuszczalnych nieudanych logowań przed wyczyszczeniem danych z urządzenia**|Określa, ile razy może zostać podane nieprawidłowe hasło, zanim zawartość urządzenia zostanie wyczyszczona.|Tak|Tak|
|**Czas braku aktywności (w minutach) przed wyłączeniem ekranu**|Określa czas, przez jaki urządzenie musi pozostawać bezczynne, zanim ekran zostanie automatycznie zablokowany.|Tak|Tak|
|**Wygaśnięcie hasła w dniach**|Określa liczbę dni, po której należy zmienić hasło urządzenia.|Tak|Tak|
|**Pamiętaj historię haseł**|Określa, czy wcześniej używane hasła są zapamiętywane, aby uniemożliwić użytkownikowi ich ponowne użycie.|Tak|Tak|
|**Pamiętaj historię haseł** — **Zapobiegaj ponownemu używaniu poprzednich haseł**|Określa liczbę poprzednich haseł, które są zapamiętywane.|Tak|Tak|

### Ustawienia szyfrowania

|Nazwa ustawienia|Szczegóły|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Wymagaj szyfrowania na urządzeniu przenośnym**|Wymaga szyfrowania danych na obsługiwanych urządzeniach przenośnych.<br>Dla urządzeń z systemem Windows Phone 8 trzeba ustawić wartość **Tak**.|Tak|Tak|

### Ustawienia systemowe

|Nazwa ustawienia|Szczegóły|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Zezwalaj na przechwytywanie ekranu**|Umożliwia użytkownikowi przechwytywanie zawartości ekranu w formie pliku obrazu.|Nie|Tak|
|**Zezwalaj na przesłanie danych diagnostycznych**|Umożliwia urządzeniu przesyłanie danych diagnostycznych do firmy Microsoft.|Nie|Tak|

### Ustawienia chmury — konta i synchronizacja

|Nazwa ustawienia|Szczegóły|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Zezwalaj na konto Microsoft**|Umożliwia połączenie konta Microsoft z urządzeniem.|Nie|Tak|

### Ustawienia poczty e-mail

|Nazwa ustawienia|Szczegóły|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Zezwalaj na niestandardowe konta e-mail**|Umożliwia urządzeniu łączenie z kontami poczty e-mail innymi niż konto Microsoft.|Nie|Tak|

### Ustawienia aplikacji — przeglądarka

|Nazwa ustawienia|Szczegóły|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Zezwalaj na używanie przeglądarki sieci Web**|Umożliwia korzystanie z wbudowanej przeglądarki sieci Web na urządzeniach lub blokuje ją.|Nie|Tak|

### Ustawienia aplikacji — aplikacje

|Nazwa ustawienia|Szczegóły|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Zezwalaj na korzystanie ze sklepu z aplikacjami**|Umożliwia użytkownikom łączenie się ze sklepem z aplikacjami z urządzenia.|Nie|Tak|

### Ustawienia możliwości urządzenia — sprzęt

|Nazwa ustawienia|Szczegóły|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Zezwalaj na używanie aparatu**|Umożliwia korzystanie z aparatu urządzenia lub blokuje go.|Nie|Tak|
|**Zezwalaj na używanie magazynu wymiennego**|Umożliwia używanie na urządzeniu magazynu wymiennego, na przykład karty SD.|Tak|Tak|
|**Zezwalaj na połączenia Wi-Fi**|Włącza lub wyłącza funkcję obsługi sieci Wi-Fi urządzenia.|Nie|Tak|
|**Zezwalaj na tethering Wi-Fi**|Umożliwia korzystanie z funkcji tetheringu Wi-Fi urządzenia.|Nie|Tak
|**Zezwalaj na automatyczne łączenie z bezpłatnymi punktami hotspot Wi-Fi**|Umożliwia urządzeniu automatyczne łączenie z bezpłatnymi hotspotami Wi-Fi i automatyczne akceptowanie wszelkich warunków użytkowania.|Nie|Tak|
|**Zezwalaj na raportowanie informacji o punktach hotspot Wi-Fi**|Wysyła informacje dotyczące połączeń Wi-Fi, aby ułatwić użytkownikowi odnajdywanie pobliskich połączeń.|Nie|Tak|
|**Zezwalaj na używanie funkcji geolokalizacji**|Umożliwia urządzeniu korzystanie z informacji o lokalizacji.|Nie|Tak|
|**Zezwalaj na komunikację NFC**|Umożliwia wykonywanie operacji korzystających z komunikacji NFC.|Nie|Tak|
|**Zezwalaj na połączenia Bluetooth**|Włącza lub wyłącza funkcję Bluetooth urządzenia.|Nie|Tak|

### Ustawienia możliwości urządzenia — funkcje

|Nazwa ustawienia|Szczegóły|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Zezwalaj na kopiowanie i wklejanie**|Umożliwia kopiowanie i wklejanie na urządzeniach.|Nie|Tak|

### Ustawienia dotyczące aplikacji dozwolonych i zablokowanych
Na liście **Aplikacje dozwolone i zablokowane** określ aplikacje, które mają być dozwolone lub zablokowane, używając następujących informacji:

> [!NOTE]
> W ramach jednych zasad można określić wyłącznie listę dozwolonych lub zablokowanych aplikacji. Nie można wprowadzić obu list w ramach jednych zasad.

|Nazwa ustawienia|Szczegóły|
|----------------|--------------------|
|**Blokuj otwieranie aplikacji z listy przez urządzenia**|Tworzy listę aplikacji niezarządzanych przez usługę Intune, których użytkownicy nie mogą instalować ani uruchamiać.|
|**Zezwalaj urządzeniom na instalowanie tylko aplikacji z listy**|Tworzy listę aplikacji, które użytkownicy mogą instalować. Użytkownicy nie będą mogli instalować żadnych innych aplikacji. Aplikacje zarządzane przez usługę Intune są automatycznie traktowane jako dozwolone.|
|**Dodaj**|Dodaje aplikację do wybranej listy. Podaj wybraną nazwę, adres URL aplikacji w sklepie z aplikacjami, a także, opcjonalnie, wydawcę aplikacji. Aby uzyskać pomoc, zobacz sekcję „Jak określać adresy URL sklepów z aplikacjami” w dalszej części tego tematu.
|**Importuj aplikacje**|Importuje listę aplikacji wprowadzoną w pliku w formacie wartości rozdzielanych przecinkami. W pliku użyj formatu: nazwa aplikacji, wydawca, adres URL.|
|**Edytowanie**|Umożliwia edytowanie nazwy, wydawcy i adresu URL wybranej aplikacji.|
|**Usuwanie**|Usuwa wybraną aplikację z listy.|
> [!IMPORTANT]
> Jeśli określono listę dozwolonych aplikacji dla urządzeń z systemem Windows Phone 8.1, należy dodać do tej listy aplikację Portal firmy — w przeciwnym razie zostanie ona zablokowana.


### Informacje referencyjne dotyczące dozwolonych i zablokowanych aplikacji

#### Jak określać adresy URL sklepów z aplikacjami
Aby określić adres URL aplikacji na liście aplikacji dozwolonych lub zablokowanych, użyj następującego formatu:

Na stronie [Aplikacje+Gry systemu Windows Phone](http://www.windowsphone.com/en-us/store/overview) wyszukaj aplikację, której chcesz użyć.

Otwórz stronę instalacji aplikacji i skopiuj adres URL do schowka. Możesz teraz użyć tego adresu URL na liście dozwolonych lub zablokowanych aplikacji.

**Przykład:** Wyszukaj aplikację Skype w sklepie. Adres URL, którego użyjesz, to **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**.

## Ustawienia zasad niestandardowych
**Niestandardowe zasady konfiguracji systemu Windows Phone** w usłudze Microsoft Intune umożliwiają wdrożenie ustawień OMA-URI, których można użyć do sterowania funkcjami na **urządzeniach z systemem Windows Phone 8.1**. Są to ustawienia standardowe używane przez wielu producentów urządzeń przenośnych do sterowania funkcjami urządzeń.

Ta funkcja umożliwia wdrażanie ustawień systemu Windows Phone, których nie można skonfigurować przy użyciu ogólnych zasad konfiguracji usługi Intune. Aby uzyskać informacje o ustawieniach, które można skonfigurować za pomocą tych zasad, zobacz [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

Aby uzyskać pomoc przy tworzeniu ustawień OMA-URI dla urządzeń z systemem Windows Phone, skorzystaj z [dokumentacji protokołu MDM systemu Windows Phone 8.1](http://technet.microsoft.com/library/dn499787.aspx).

### Ustawienia ogólne

|Nazwa ustawienia|Szczegóły|
|----------------|--------------------|
|**Nazwa**|Wprowadź unikatową nazwę zasad, która ułatwi ich identyfikację w konsoli usługi Intune.|
|**Opis**|Podaj opis zawierający omówienie zasad oraz inne istotne informacje ułatwiające ich wyszukanie.|

### Ustawienia OMA-URI

W sekcji **Ustawienia OMA-URI** kliknij przycisk **Dodaj**, aby dodać ustawienie. Możesz również edytować i usuwać istniejące ustawienie.

W oknie dialogowym **Dodawanie lub edytowanie ustawienia OMA-URI** określ następujące informacje:

|Nazwa ustawienia|Szczegóły|
    |--------|--------------------|
    |**Nazwa ustawienia**|Wprowadź unikatową nazwę dla ustawienia OMA-URI, aby ułatwić jego identyfikację  na liście ustawień.|
    |**Opis ustawienia**|Podaj opis, który zawiera omówienie ustawienia oraz inne istotne informacje, które ułatwią jego wyszukanie.|
    |**Typ danych**|Wybierz typ danych, zgodnie z którym określisz to ustawienie OMA-URI. Wybierz spośród opcji:<br /><br />-   **String**<br />-   **Ciąg (XML)**<br />-   **Data i godzina**<br />-   **Integer**<br />-   **Liczba zmiennoprzecinkowa**<br />-   **Boolean**|
    |**OMA-URI (z uwzględnieniem wielkości liter)**|Określ identyfikator OMA-URI, dla którego chcesz podać ustawienie.|
    |**Wartość**|Określ wartość, która będzie kojarzona z określonym wcześniej identyfikatorem OMA-URI.|

### Zobacz także
[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Aug16_HO3-->


