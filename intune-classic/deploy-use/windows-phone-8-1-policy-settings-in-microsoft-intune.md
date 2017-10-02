---
title: Ustawienia zasad systemu Windows Phone 8.1
description: "Usługa Intune udostępnia szereg wbudowanych ustawień ogólnych, które można skonfigurować na urządzeniach z systemem Windows Phone 8.1. Ponadto można określić wartości OMA-URI, aby utworzyć ustawienia niestandardowe, które nie są dostępne w usłudze Intune."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 83f7469c-272e-43f2-8139-b0d7bc34f43f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 95de34806ebd9faed761b0e64df8c4dc596083c8
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2017
---
# <a name="windows-phone-81-policy-settings-in-microsoft-intune"></a>Ustawienia zasad systemu Windows Phone 8.1 w usłudze Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Usługa Intune udostępnia szereg wbudowanych ustawień ogólnych, które można skonfigurować na urządzeniach z systemem Windows Phone 8.1. Ponadto można określić wartości jednolitego identyfikatora zasobów organizacji Open Mobile Alliance (OMA-URI), aby utworzyć ustawienia niestandardowe, które nie są dostępne w usłudze Intune.

## <a name="general-configuration-settings"></a>Ogólne ustawienia konfiguracji

**Ogólne zasady konfiguracji systemu Windows Phone w usłudze Intune (system Windows Phone 8.1 i nowsze)** umożliwiają konfigurowanie następujących ustawień urządzeń z systemem Windows Phone 8.1:

-   **Ustawienia zabezpieczeń urządzenia przenośnego** — Możliwość wyboru z listy wstępnie zdefiniowanych ustawień, które pozwalają na kontrolę szeregu funkcji i funkcjonalności urządzenia.

-   **Zgodne i niezgodne aplikacje** — określanie listy zgodnych lub niezgodnych aplikacji w firmie. Urządzenia z systemem Windows Phone mogą blokować instalację tych aplikacji lub zezwalać na nią.

### <a name="applicability-settings"></a>Ustawienia zastosowania

|Nazwa ustawienia|Szczegóły|
|----------------|----------------------------------|
|**Zastosuj wszystkie konfiguracje dla systemu Windows 10**|Umożliwia zastosowanie ustawień tych zasad również na urządzeniach z systemem Windows 10 Mobile, a nie tylko na urządzeniach z systemem Windows 8.1.|

### <a name="password-settings"></a>Ustawienia hasła

|Nazwa ustawienia|Szczegóły|
|----------------|------|
|**Wymagaj hasła do odblokowania urządzeń przenośnych**|Określa, czy użytkownicy muszą wprowadzić hasło, aby uzyskać dostęp do swoich urządzeń.|
|**Wymagany typ hasła**|Określa typ hasła, które będzie wymagane, na przykład alfanumeryczne lub tylko liczbowe.|
|**Wymagany typ hasła — Minimalna liczba zestawów znaków**|Określa, z ilu różnych zestawów znaków muszą pochodzić znaki zawarte w haśle. Istnieją cztery zestawy znaków: małe litery, wielkie litery, cyfry oraz symbole. Jednak w przypadku urządzeń z systemem iOS ustawienie określa liczbę symboli, które muszą być zawarte w haśle.|
|**Minimalna długość hasła**|Określa minimalną wymaganą liczbę znaków w haśle.|
|**Zezwalaj na proste hasła**|Określa, czy można używać prostych haseł, takich jak ciągi „0000” i „1234”.|
|**Liczba dopuszczalnych nieudanych logowań przed wyczyszczeniem danych z urządzenia**|Określa, ile razy może zostać podane nieprawidłowe hasło, zanim zawartość urządzenia zostanie wyczyszczona.|
|**Czas braku aktywności (w minutach) przed wyłączeniem ekranu**|Określa czas, przez jaki urządzenie musi pozostawać bezczynne, zanim ekran zostanie automatycznie zablokowany.|
|**Dni do wygaśnięcia hasła**|Określa liczbę dni, po której należy zmienić hasło urządzenia.|Tak|Tak|
|**Pamiętaj historię haseł**|Określa, czy wcześniej używane hasła są zapamiętywane, aby uniemożliwić użytkownikowi ich ponowne użycie.|
|**Pamiętaj historię haseł** — **Zapobiegaj ponownemu używaniu poprzednich haseł**|Określa liczbę poprzednich haseł, które są zapamiętywane.|

### <a name="encryption-settings"></a>Ustawienia szyfrowania

|Nazwa ustawienia|Szczegóły|
|----------------|------|
|**Wymagaj szyfrowania na urządzeniu przenośnym**|Wymaga szyfrowania danych na obsługiwanych urządzeniach przenośnych.|

### <a name="system-settings"></a>Ustawienia systemowe

|Nazwa ustawienia|Szczegóły|
|----------------|-----|
|**Zezwalaj na przechwytywanie ekranu**|Umożliwia użytkownikowi przechwytywanie zawartości ekranu w formie pliku obrazu.|
|**Zezwalaj na przesyłanie danych diagnostycznych**|Umożliwia urządzeniu przesyłanie danych diagnostycznych do firmy Microsoft.|

### <a name="cloud-settings--accounts-and-synchronization"></a>Ustawienia chmury — konta i synchronizacja

|Nazwa ustawienia|Szczegóły|
|----------------|------|
|**Zezwalaj na konto Microsoft**|Umożliwia połączenie konta Microsoft z urządzeniem.|

### <a name="email-settings"></a>Ustawienia poczty e-mail

|Nazwa ustawienia|Szczegóły|
|----------------|-----|
|**Zezwalaj na niestandardowe konta e-mail**|Umożliwia urządzeniu łączenie z kontami poczty e-mail innymi niż konto Microsoft.|

### <a name="application-settings---browser"></a>Ustawienia aplikacji — przeglądarka

|Nazwa ustawienia|Szczegóły|
|----------------|-----|
|**Zezwalaj na używanie przeglądarki sieci Web**|Umożliwia korzystanie z wbudowanej przeglądarki sieci Web na urządzeniach lub blokuje ją.|

### <a name="application-settings---apps"></a>Ustawienia aplikacji — aplikacje

|Nazwa ustawienia|Szczegóły|
|----------------|-----|
|**Zezwalaj na korzystanie ze sklepu z aplikacjami**|Umożliwia użytkownikom łączenie się ze sklepem z aplikacjami z urządzenia.|

### <a name="device-capabilities-settings---hardware"></a>Ustawienia możliwości urządzenia — sprzęt

|Nazwa ustawienia|Szczegóły|
|----------------|-----|
|**Zezwalaj na używanie aparatu**|Umożliwia korzystanie z aparatu urządzenia lub blokuje go.|
|**Zezwalaj na używanie magazynu wymiennego**|Umożliwia używanie na urządzeniu magazynu wymiennego, na przykład karty SD.|
|**Zezwalaj na połączenia Wi-Fi**|Włącza lub wyłącza funkcję obsługi sieci Wi-Fi urządzenia.|
|**Zezwalaj na tethering Wi-Fi**|Umożliwia korzystanie z funkcji tetheringu Wi-Fi urządzenia.|
|**Zezwalaj na automatyczne łączenie z bezpłatnymi punktami hotspot Wi-Fi**|Umożliwia urządzeniu automatyczne łączenie z bezpłatnymi hotspotami Wi-Fi i automatyczne akceptowanie wszelkich warunków użytkowania.|
|**Zezwalaj na raportowanie informacji o punktach hotspot Wi-Fi**|Wysyła informacje dotyczące połączeń Wi-Fi, aby ułatwić użytkownikowi odnajdywanie pobliskich połączeń.|
|**Zezwalaj na używanie funkcji geolokalizacji**|Umożliwia urządzeniu korzystanie z informacji o lokalizacji.|
|**Zezwalaj na komunikację NFC**|Umożliwia wykonywanie operacji korzystających z komunikacji NFC.|
|**Zezwalaj na połączenia Bluetooth**|Włącza lub wyłącza funkcję Bluetooth urządzenia.|

### <a name="device-capabilities-settings---features"></a>Ustawienia możliwości urządzenia — funkcje

|Nazwa ustawienia|Szczegóły|
|----------------|----|
|**Zezwalaj na kopiowanie i wklejanie**|Umożliwia kopiowanie i wklejanie na urządzeniach.|

### <a name="settings-for-allowed-and-blocked-apps"></a>Ustawienia dotyczące aplikacji dozwolonych i zablokowanych
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


### <a name="reference-information-for-allowed-and-blocked-apps"></a>Informacje referencyjne dotyczące dozwolonych i zablokowanych aplikacji

#### <a name="how-to-specify-urls-to-app-stores"></a>Jak określać adresy URL sklepów z aplikacjami
Aby określić adres URL aplikacji na liście aplikacji dozwolonych lub zablokowanych, użyj następującego formatu:

Na stronie [Aplikacje+Gry systemu Windows Phone](http://www.windowsphone.com/store/overview) wyszukaj aplikację, której chcesz użyć.

Otwórz stronę instalacji aplikacji i skopiuj adres URL do schowka. Możesz teraz użyć tego adresu URL na liście dozwolonych lub zablokowanych aplikacji.

**Przykład:** Wyszukaj aplikację Skype w sklepie. Adres URL, którego użyjesz, to **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**.

## <a name="custom-policy-settings"></a>Ustawienia zasad niestandardowych
**Niestandardowe zasady konfiguracji systemu Windows Phone** w usłudze Microsoft Intune umożliwiają wdrożenie ustawień OMA-URI, których można użyć do sterowania funkcjami na **urządzeniach z systemem Windows Phone 8.1**. Są to ustawienia standardowe używane przez wielu producentów urządzeń przenośnych do sterowania funkcjami urządzeń.

Ta funkcja umożliwia wdrażanie ustawień systemu Windows Phone, których nie można skonfigurować przy użyciu ogólnych zasad konfiguracji usługi Intune. Aby uzyskać informacje o ustawieniach, które można skonfigurować za pomocą tych zasad, zobacz [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

Aby uzyskać pomoc przy tworzeniu ustawień OMA-URI dla urządzeń z systemem Windows Phone, skorzystaj z [dokumentacji protokołu MDM systemu Windows Phone 8.1](http://technet.microsoft.com/library/dn499787.aspx).

### <a name="general-settings"></a>Ustawienia ogólne

|Nazwa ustawienia|Szczegóły|
|----------------|--------------------|
|**Nazwa**|Wprowadź unikatową nazwę zasad, która ułatwi ich identyfikację w konsoli usługi Intune.|
|**Opis**|Podaj opis zawierający omówienie zasad oraz inne istotne informacje ułatwiające ich wyszukanie.|

### <a name="oma-uri-settings"></a>Ustawienia OMA-URI

W sekcji **Ustawienia OMA-URI** kliknij przycisk **Dodaj**, aby dodać ustawienie. Możesz również edytować i usuwać istniejące ustawienie.

W oknie dialogowym **Dodawanie lub edytowanie ustawienia OMA-URI** określ następujące informacje:

|Nazwa ustawienia|Szczegóły|
    |--------|--------------------|
    |**Nazwa ustawienia**|Wprowadź unikatową nazwę dla ustawienia OMA-URI, aby ułatwić jego identyfikację na liście ustawień.|
    |**Opis ustawienia**|Podaj opis, który zawiera omówienie ustawienia oraz inne istotne informacje, które ułatwią jego wyszukanie.|
    |**Typ danych**|Wybierz typ danych, zgodnie z którym określisz to ustawienie OMA-URI. Wybierz spośród opcji:<br /><br />-   **Ciąg**<br />-   **Ciąg (XML)**<br />-   **Data i godzina**<br />-   **Liczba całkowita**<br />-   **Liczba zmiennoprzecinkowa**<br />-   **Wartość logiczna**|
    |**OMA-URI (z uwzględnieniem wielkości liter)**|Określ identyfikator OMA-URI, dla którego chcesz podać ustawienie.|
    |**Wartość**|Określ wartość, która będzie kojarzona z określonym wcześniej identyfikatorem OMA-URI.|

### <a name="see-also"></a>Zobacz także
[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
