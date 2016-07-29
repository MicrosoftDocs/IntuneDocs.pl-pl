---
title: Ustawienia zasad systemu Windows Phone 8.1 | Microsoft Intune
description: "Usługa Intune udostępnia szereg wbudowanych ustawień ogólnych, które można skonfigurować na urządzeniach z systemem Windows Phone 8.1. Ponadto można określić wartości OMA-URI, aby utworzyć ustawienia niestandardowe, które nie są dostępne w usłudze Intune."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 83f7469c-272e-43f2-8139-b0d7bc34f43f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: e11ca62eb242d7c530e8de2ad1e885315d220233


---

# Ustawienia zasad systemu Windows Phone 8.1 w usłudze Microsoft Intune

Usługa Intune udostępnia szereg wbudowanych ustawień ogólnych, które można skonfigurować na urządzeniach z systemem Windows Phone 8.1. Ponadto można określić wartości OMA-URI, aby utworzyć ustawienia niestandardowe, które nie są dostępne w usłudze Intune.

## Ogólne ustawienia konfiguracji

**Ogólne zasady konfiguracji systemu Windows Phone w usłudze Intune (system Windows Phone 8.1 i nowsze)** umożliwiają konfigurowanie następujących ustawień urządzeń z systemem Windows Phone 8.1:

-   **Ustawienia zabezpieczeń urządzenia przenośnego** — Możliwość wyboru z listy wstępnie zdefiniowanych ustawień, które pozwalają na kontrolę szeregu funkcji i funkcjonalności urządzenia.

-   **Zgodne i niezgodne aplikacje** — Określanie listy zgodnych i niezgodnych aplikacji w firmie. Urządzenia z systemem Windows Phone mogą blokować lub umożliwić instalację tych aplikacji.

### Ustawienia zastosowania

|Nazwa ustawienia|Szczegóły|
|----------------|----------------------------------|
|**Zastosuj wszystkie konfiguracje dla systemu Windows 10**|Umożliwia zastosowanie ustawień tych zasad na urządzeniach systemu Windows 10 Mobile oprócz urządzeń z systemami Windows 8.1.|

### Ustawienia hasła

|Nazwa ustawienia|Szczegóły|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Wymagaj hasła do odblokowania urządzeń przenośnych**|Określa, czy użytkownicy muszą wprowadzić hasło, aby uzyskać dostęp do swoich urządzeń.|Tak|Tak|
|**Wymagany typ hasła**|Określa typ hasła, które będzie wymagane, na przykład wyłącznie numeryczne lub alfanumeryczne.|Tak|Tak|
|**Wymagany typ hasła — Minimalna liczba zestawów znaków**|Istnieją cztery zestawów znaków: małe litery, wielkie litery, cyfry oraz symbole. To ustawienie określa, znaki z ilu zestawów znaków muszą być zawarte w haśle). Jednak w przypadku urządzeń z systemem iOS ustawienie określa liczbę znaków symbolicznych, które muszą być zawarte w haśle)|Tak|Tak|
|**Minimalna długość hasła**|Określa minimalną wymaganą liczbę znaków w haśle.|Tak|Tak|
|**Zezwalaj na proste hasła**|Proste hasła zawierają ciągi "0000" i "1234"|Tak|Tak|
|**Liczba dopuszczalnych nieudanych logowań przed wyczyszczeniem danych z urządzenia**|Określa, ile razy może zostać zapamiętane nieprawidłowe hasło, zanim zawartość urządzenia zostanie usunięta.|Tak|Tak|
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
|**Zezwalaj na przesłanie danych diagnostycznych**|Zezwala urządzeniu na przesyłanie danych diagnostycznych do firmy Microsoft.|Nie|Tak|

### Ustawienia chmury — konta i synchronizacja

|Nazwa ustawienia|Szczegóły|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Zezwalaj na konto Microsoft**|Zezwala na połączenie konta Microsoft z urządzeniem.|Nie|Tak|

### Ustawienia poczty e-mail

|Nazwa ustawienia|Szczegóły|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Zezwalaj na niestandardowe konta e-mail**|Zezwalaj urządzeniu na połączenia z kontami poczty e-mail innymi niż Microsoft.|Nie|Tak|

### Ustawienia aplikacji — przeglądarka

|Nazwa ustawienia|Szczegóły|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Zezwalaj na używanie przeglądarki sieci Web**|Zezwala na wbudowaną przeglądarkę sieci Web na urządzeniach lub blokuje ją.|Nie|Tak|

### Ustawienia aplikacji — aplikacje

|Nazwa ustawienia|Szczegóły|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Zezwalaj na korzystanie ze sklepu z aplikacjami**|Umożliwia użytkownikom łączenie się ze sklepem z aplikacjami z urządzenia.|Nie|Tak|

### Ustawienia możliwości urządzenia — sprzęt

|Nazwa ustawienia|Szczegóły|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Zezwalaj na używanie aparatu**|Zezwala na używanie aparatu urządzenia lub blokuje je.|Nie|Tak|
|**Zezwalaj na używanie magazynu wymiennego**|Umożliwia używanie na urządzeniu magazynu wymiennego, na przykład karty SD.|Tak|Tak|
|**Zezwalaj na połączenia Wi-Fi**|Włącza lub wyłącza funkcję obsługi sieci Wi-Fi urządzenia.|Nie|Tak|
|**Zezwalaj na tethering Wi-Fi**|Umożliwia korzystanie z funkcji tetheringu Wi-Fi urządzenia.|Nie|Tak
|**Zezwalaj na automatyczne łączenie z bezpłatnymi punktami hotspot Wi-Fi**|Zezwala urządzeniu na automatyczne łączenie z bezpłatnymi punktami hotspot Wi-Fi i automatycznie akceptuje wszelkie warunki użytkowania.|Nie|Tak|
|**Zezwalaj na raportowanie informacji o punktach hotspot Wi-Fi**|Wysyłaj informacje dotyczące połączeń Wi-Fi, aby ułatwić wykrywanie pobliskich połączeń.|Nie|Tak|
|**Zezwalaj na używanie funkcji geolokalizacji**|Umożliwia urządzeniu korzystanie z informacji o lokalizacji.|Nie|Tak|
|**Zezwalaj na komunikację NFC**|Umożliwia wykonywanie operacji korzystających z komunikacji NFC.|Nie|Tak|
|**Zezwalaj na połączenia Bluetooth**|Włącza lub wyłącza funkcję Bluetooth urządzenia.|Nie|Tak|

### Ustawienia możliwości urządzenia — funkcje

|Nazwa ustawienia|Szczegóły|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Zezwalaj na kopiowanie i wklejanie**|Zezwalaj na kopiowanie i wklejanie na urządzeniach.|Nie|Tak|

### Ustawienia dotyczące aplikacji zgodnych i niezgodnych
Na liście **Zgodne i niezgodne aplikacje** określ listę zgodnych i niezgodnych aplikacji, korzystając z poniższych informacji:

> [!NOTE]
> W ramach jednych zasad można określić wyłącznie listę zgodnych lub wyłącznie listę niezgodnych aplikacji. Nie można wprowadzić obu list w ramach jednych zasad.

|Nazwa ustawienia|Szczegóły|
|----------------|--------------------|
|**Blokuj otwieranie aplikacji z listy przez urządzenia**|Tworzy listę aplikacji niezarządzanych przez usługę Intune, których użytkownicy nie mogą instalować i uruchamiać.|
|**Zezwalaj urządzeniom na instalowanie tylko aplikacji z listy**|Tworzy listę aplikacji, które użytkownicy mogą instalować. Użytkownicy nie będą mogli instalować żadnych innych aplikacji. Aplikacje zarządzane przez usługę Intune są automatycznie traktowane jako dozwolone.|
|**Dodaj**|Dodaje aplikację do wybranej listy. Wprowadź wybraną nazwę, opcjonalnie wydawcę aplikacji, a także adres URL aplikacji w sklepie z aplikacjami. Aby uzyskać pomoc, zobacz sekcję „Jak określać adresy URL sklepów z aplikacjami” w dalszej części tego tematu.
|**Importuj aplikacje**|Importuje listę aplikacji wprowadzoną w pliku w formacie wartości rozdzielanych przecinkami. W pliku użyj formatu: nazwa aplikacji, wydawca, adres URL.|
|**Edytowanie**|Umożliwia edytowanie nazwy, wydawcy i adresu URL wybranej aplikacji.|
|**Usuwanie**|Usuwa wybraną aplikację z listy.|
> [!IMPORTANT]
> Podczas określania listy dozwolonych aplikacji dla urządzeń z systemem Windows Phone 8.1 należy dodać do tej listy aplikację Portal firmy — w przeciwnym razie zostanie ona zablokowana.


### Informacje o odwołaniu dotyczące aplikacji zgodnych i niezgodnych

#### Jak określać adresy URL sklepów z aplikacjami
Aby określić adres URL aplikacji na liście aplikacji zgodnych i niezgodnych, użyj następującego formatu:

Na stronie [Aplikacje+Gry systemu Windows Phone](http://www.windowsphone.com/en-us/store/overview) wyszukaj aplikację, której chcesz użyć.

Otwórz stronę instalacji aplikacji i skopiuj adres URL do schowka. Możesz teraz użyć tego adresu URL na liście zgodnych lub niezgodnych aplikacji.

**Przykład:** Wyszukaj aplikację Skype w sklepie. Adres URL, którego użyjesz, to **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**.

## Ustawienia zasad niestandardowych 
**Niestandardowe zasady konfiguracji systemu Windows Phone** w usłudze Intune umożliwiają wdrożenie ustawień OMA-URI (Open Mobile Alliance Uniform Resource Identifier), za pomocą których można kontrolować funkcje na **urządzeniach z systemem Windows Phone 8.1**. Są to ustawienia standardowe używane przez wielu producentów urządzeń przenośnych do sterowania funkcjami urządzeń.

Ta funkcja ma umożliwić wdrażanie ustawień systemu Windows Phone, których nie można skonfigurować przy użyciu zasad ogólnych konfiguracji usługi Intune. Aby uzyskać informacje o ustawieniach, które można skonfigurować za pomocą tych zasad, zobacz [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

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




<!--HONumber=Jul16_HO3-->


