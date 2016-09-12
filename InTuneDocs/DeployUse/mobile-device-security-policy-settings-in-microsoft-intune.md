---
title: "Ustawienia zasad zabezpieczeń urządzeń przenośnych | Microsoft Intune"
description: "Usługa Intune umożliwia skonfigurowanie wielu ustawień, które możesz wdrożyć na urządzeniach zarządzanych w Twojej organizacji."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e5ab3b76-08af-4893-b294-fb6627fdc4c6
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 388426657c5fa96289f5e14a85e8c299e4b50037
ms.openlocfilehash: ac19128499f078b4fe7d16713f18c78b248d38db



---

# Ustawienia zasad zabezpieczeń urządzeń przenośnych w usłudze Microsoft Intune
> [!IMPORTANT]
> Usługa Microsoft Intune obsługuje teraz oddzielne zasady konfiguracji dla każdej platformy urządzeń. Te zasady zawierają najbardziej aktualne ustawienia, których można użyć. Zasady zabezpieczeń urządzenia przenośnego można stosować w dalszym ciągu, a wszystkie istniejące wdrożenia będą nadal działać. Należy jednak możliwie jak najszybciej zaplanować migrację do nowych zasad konfiguracji, ponieważ zasady zabezpieczeń urządzenia przenośnego zostaną w przyszłości usunięte.

Zasady zabezpieczeń urządzenia przenośnego usługi Intune umożliwiają skonfigurowanie wielu ustawień, które można wdrożyć na urządzeniach zarządzanych w ramach organizacji. Za pomocą tych ustawień możesz kontrolować funkcjonalność i zabezpieczenia urządzeń.

Możesz tworzyć i wdrażać zasady zabezpieczeń urządzeń przenośnych dla następujących typów urządzeń:

-   Windows RT 8.1 i zarejestrowane urządzenia z systemem Windows 8.1

-   Windows RT

-   Windows Phone 8 i Windows Phone 8.1

-   iOS

-   Android i Samsung KNOX

> [!NOTE]
> Niektóre ustawienia nie mają zastosowania do niektórych urządzeń. Poniższe tabele zawierają pełną listę ustawień, które można skonfigurować.

## Ustawienia zabezpieczeń

|Nazwa ustawienia|Windows 8.1 i Windows RT 8.1|Windows RT|Windows Phone 8 i Windows Phone 8.1|iOS|Android i Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Wymagaj hasła do odblokowania urządzeń przenośnych**|Nie|Nie|Tak|Tak|Tak|
|**Wymagany typ hasła**<br /><br />To ustawienie określa typ hasła, które będzie wymagane, na przykład alfanumeryczne lub wyłącznie liczbowe.|Tak|Tak|Tak|Tak|Nie|
|**Wymagany typ hasła — Minimalna liczba zestawów znaków**<br /><br />Istnieją cztery zestawy znaków: małe litery, wielkie litery, cyfry oraz symbole. To ustawienie określa, z ilu różnych zestawów znaków muszą pochodzić znaki zawarte w haśle. Jednak w przypadku urządzeń z systemem iOS ustawienie określa liczbę znaków symbolicznych, które muszą być zawarte w haśle.|Tak|Tak|Tak|Tak|Nie|
|**Minimalna długość hasła**|Tak|Tak|Tak|Tak|Tak|
|**Zezwalaj na proste hasła**<br /><br />Proste hasła zawierają ciągi „0000” i „1234”.|Nie|Nie|Tak|Tak|Nie|
|**Liczba dopuszczalnych nieudanych logowań przed wyczyszczeniem danych z urządzenia**|Tak|Tak|Tak|Tak|Tak|
|**Czas braku aktywności (w minutach) przed wyłączeniem ekranu**<sup>1</sup>|Tak|Tak|Tak|Tak|Tak|
|**Wygaśnięcie hasła w dniach**|Tak|Tak|Tak|Tak|Tak|
|**Pamiętaj historię haseł**|Tak|Tak|Tak|Tak|Tak|
|**Pamiętaj historię haseł** — **Zapobiegaj ponownemu używaniu poprzednich haseł**|Tak|Tak|Tak|Tak|Tak|
|**Jakość hasła**|Nie|Nie|Nie|Nie|Tak|
|**Zezwalaj na hasło obrazkowe i numer PIN**|Tak|Tak|Nie|Nie|Nie|
|**Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła**|Nie|Nie|Nie|Tak|Nie|
|**Zezwalaj na odblokowanie na podstawie linii papilarnych**|Nie|Nie|Nie|iOS 7 i nowsze|Nie|
<sup>1</sup> W przypadku urządzeń z systemem iOS skonfigurowane ustawienia **Czas braku aktywności (w minutach) przed wyłączeniem ekranu** i **Czas braku aktywności (w minutach), zanim będzie wymagane podanie hasła** są stosowane jedno po drugim. Na przykład, jeśli wartość obu ustawień zostanie ustawiona na **5** minut, ekranie wyłączy się automatycznie po 5 minut, a urządzenie zostanie zablokowane po kolejnych 5 minutach. Jednak jeśli użytkownik wyłączy ekranie ręcznie, drugie ustawienie zostanie zastosowane natychmiast. W tym samym przykładzie, jeśli użytkownik wyłączy ekran, po 5 minutach urządzenie zostanie zablokowane.

Po wdrożeniu zasad długości hasła na urządzeniach z systemem Windows RT użytkownicy będą zmuszeni do zresetowania swojego hasła nawet wtedy, gdy ich bieżące hasło spełnia wymagania zasad.

## Ustawienia szyfrowania

|Nazwa ustawienia|Windows 8.1 i Windows RT 8.1|Windows RT|Windows Phone 8 i Windows Phone 8.1|iOS|Android i Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Wymagaj szyfrowania na urządzeniu przenośnym**<sup>1</sup><br /><br />Dla urządzeń z systemem Windows Phone 8 trzeba ustawić wartość **Tak**.<br /><br />Aby włączyć szyfrowanie na urządzeniach z systemem iOS, włącz ustawienie **Wymagaj hasła do odblokowania urządzeń przenośnych**.|Tak|Nie|Tak|Nie|Tak|
|**Wymagaj szyfrowania kart pamięci**<br /><br />To ustawienie dotyczy urządzeń, które są także zarządzane przez program Exchange ActiveSync.|n/d|n/d|n/d <br />Aplikacje i skojarzone dane są automatycznie szyfrowane.|n/d|Tak|
<sup>1</sup> Dodatkowe informacje dotyczące urządzeń z systemem Windows 8.1:

-   Aby wymusić szyfrowanie na urządzeniach z systemem Windows 8.1, trzeba zainstalować na wszystkich urządzeniach [aktualizację klienta MDM dla systemu Windows z grudnia 2014 r.](http://support.microsoft.com/kb/3013816) 

-   W przypadku włączenia tego ustawienia dla urządzeń z systemem Windows 8.1 wszyscy użytkownicy urządzeń muszą mieć konto Microsoft.

-   Aby szyfrowanie działało, urządzenie musi spełniać wymagania dotyczące certyfikacji sprzętu [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) firmy Microsoft.

-   W przypadku wymuszania szyfrowania na urządzeniu klucz odzyskiwania jest dostępny tylko za pośrednictwem konta Microsoft użytkownika, do którego można uzyskać dostęp z konta usługi OneDrive. Nie można odzyskać tego klucza w imieniu użytkownika.

## Ustawienia złośliwego oprogramowania

|Nazwa ustawienia|Windows 8.1 i Windows RT 8.1|Windows RT|Windows Phone 8 i Windows Phone 8.1|iOS|Android i Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Wymagaj zapory sieciowej**|Tak|Nie|Nie|Nie|Nie|
|**Włącz filtr SmartScreen**|Tak|Nie|Nie|Nie|Nie|

## Ustawienia systemowe

|Nazwa ustawienia|Windows 8.1 i Windows RT 8.1|Windows RT|Windows Phone 8 i Windows Phone 8.1|iOS|Android i Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Wymagaj aktualizacji automatycznych**|Tak|Nie|Nie|Nie|Nie|
|**Wymagaj aktualizacji automatycznych — minimalna klasyfikacja aktualizacji do instalacji automatycznej**<br /><br />Wybierz klasyfikację aktualizacji, które zostaną zainstalowane automatycznie:<br /><br />- **Ważne**. Instaluje wszystkie aktualizacje sklasyfikowane jako ważne.<br /><br />- **Zalecane**. Instaluje wszystkie aktualizacje sklasyfikowane jako ważne lub zalecane.|Tak|Nie|Nie|Nie|Nie|
|**Zezwalaj na przechwytywanie ekranu**|Nie|Nie|Tylko Windows Phone 8.1|Tak|Tak (tylko Samsung KNOX)|
|**Zezwalaj na centrum sterowania na ekranie blokady**|Nie|Nie|Nie|iOS 7 i nowsze|Nie|
|**Zezwalaj na widok powiadomienia na ekranie blokady**|Nie|Nie|Nie|iOS 7 i nowsze|Nie|
|**Zezwalaj na widok dzisiejszy na ekranie blokady**|Nie|Nie|Nie|iOS 7 i nowsze|Nie|
|**Kontrola konta użytkownika**|Tak|Nie|Nie|Nie|Nie|
|**Zezwalaj na przesłanie danych diagnostycznych**|Tak|Nie|Tylko Windows Phone 8.1|Tak|Tak (tylko Samsung KNOX)|
|**Zezwalaj na niezaufane certyfikaty TLS**|Nie|Nie|Nie|Tak|Nie|
|**Zezwalaj na oprogramowanie osobistego portfela w trybie blokady**|Nie|Nie|Nie|Tak|Nie|
|**Zezwalaj na resetowanie do ustawień fabrycznych**|Nie|Nie|Nie|Nie|Tak (tylko Samsung KNOX)|


## Ustawienia chmury — dokumenty i dane

|Nazwa ustawienia|Windows 8.1 i Windows RT 8.1|Windows RT|Windows Phone 8 i Windows Phone 8.1|iOS|Android i Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Zezwalaj na tworzenie kopii zapasowych w ramach usługi iCloud**|Nie|Nie|Nie|Tak|Nie|
|**Zezwalaj na synchronizowanie dokumentów w ramach usługi iCloud**|Nie|Nie|Nie|Tak|Nie|
|**Zezwalaj na synchronizowanie strumienia zdjęć w ramach usługi iCloud**|Nie|Nie|Nie|Tak|Nie|
|**Wymagaj zaszyfrowanej kopii zapasowej**|Nie|Nie|Nie|Tak|Nie|
|**Adres URL folderów roboczych**<br /><br />To ustawienie określa adres URL folderu roboczego, aby umożliwić synchronizację dokumentów między urządzeniami.|Tak|Nie|Nie|Nie|Nie|
|**Zezwalaj na kopie zapasowe w usłudze Google**|Nie|Nie|Nie|Nie|Tak (tylko Samsung KNOX)|

## Ustawienia chmury — konta i synchronizacja

|Nazwa ustawienia|Windows 8.1 i Windows RT 8.1|Windows RT|Windows Phone 8 i Windows Phone 8.1|iOS|Android i Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Zezwalaj na konto Microsoft**|Nie|Nie|Tylko Windows Phone 8.1|Nie|Nie|
|**Zezwalaj na automatyczną synchronizację konta Google**|Nie|Nie|Nie|Nie|Tak (tylko Samsung KNOX)|

## Ustawienia poczty e-mail

|Nazwa ustawienia|Windows 8.1 i Windows RT 8.1|Windows RT|Windows Phone 8 i Windows Phone 8.1|iOS|Android i Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Zezwalaj użytkownikom na pobieranie załączników wiadomości e-mail**<sup>1</sup>|n/d|n/d|n/d|n/d|n/d|
|**Okres synchronizacji wiadomości e-mail** <br /><br />To ustawienie dotyczy urządzeń, które są także zarządzane przez program Exchange ActiveSync.|n/d|n/d|n/d|n/d|n/d|
|**Zezwalaj urządzeniom przenośnym, które nie obsługują w pełni tych ustawień, na synchronizowanie z programem Exchange (Exchange ActiveSync)** <br /><br />To ustawienie dotyczy urządzeń, które są także zarządzane przez program Exchange ActiveSync.|n/d|n/d|n/d|n/d|n/d|
|**Ustaw konto Microsoft jako opcjonalne w aplikacji Windows Mail**|Tak|Nie|Nie|Nie|Nie|
|**Zezwalaj na niestandardowe konta e-mail**|Nie|Nie|Tylko Windows Phone 8.1|Nie|Nie|

## Ustawienia aplikacji — przeglądarka

|Nazwa ustawienia|Windows 8.1 i Windows RT 8.1|Windows RT|Windows Phone 8 i Windows Phone 8.1|iOS|Android i Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Zezwalaj na używanie przeglądarki sieci Web**|Nie|Nie|Tylko Windows Phone 8.1|Tak|Tak (tylko Samsung KNOX)|
|**Zezwalaj na automatyczne uzupełnianie**|Tak|Nie|Nie|Tak|Tak (tylko Samsung KNOX)|
|**Zezwalaj na blokowanie wyskakujących okienek**|Tak|Nie|Nie|Tak|Tak (tylko Samsung KNOX)|
|**Zezwalaj na pliki cookie**|Nie|Nie|Nie|Tak|Tak (tylko Samsung KNOX)|
|**Zezwalaj na używanie dodatków**|Tak|Nie|Nie|Nie|Nie|
|**Zezwalaj na wykonywanie aktywnych skryptów**|Tak|Nie|Nie|Tak|Tak (tylko Samsung KNOX)|
|**Zezwalaj na ostrzeżenia o oszustwie**|Tak|Nie|Nie|Tak|Nie|
|**Zezwalaj na przejście do witryny intranetowej po wpisaniu jednego słowa**<br /><br />(To ustawienie umożliwia użycie pojedynczego słowa do przekierowania programu Internet Explorer do witryny sieci Web — na przykład „Bing”).|Tak|Nie|Nie|Nie|Nie|
|**Zezwalaj na automatyczne wykrywanie sieci intranet**|Tak|Nie|Nie|Nie|Nie|
|**Poziom zabezpieczeń Internetu**|Tak|Nie|Nie|Nie|Nie|
|**Poziom zabezpieczeń sieci intranet**|Tak|Nie|Nie|Nie|Nie|
|**Poziom zabezpieczeń zaufanych witryn**|Tak|Nie|Nie|Nie|Nie|
|**Poziom zabezpieczeń witryn z ograniczeniami**|Tak|Nie|Nie|Nie|Nie|
|**Wysyłaj nagłówek Nie śledź**|Tak|Nie|Nie|Nie|Nie|
|**Zezwalaj na dostęp do menu trybu przedsiębiorstwa**|Tak|Nie|Nie|Nie|Nie|
|**Lokalizacja listy witryn trybu przedsiębiorstwa**|Tak|Nie|Nie|Nie|Nie|

## Ustawienia aplikacji — aplikacje

|Nazwa ustawienia|Windows 8.1 i Windows RT 8.1|Windows RT|Windows Phone 8 i Windows Phone 8.1|iOS|Android i Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Zezwalaj na korzystanie ze sklepu z aplikacjami**|Nie|Nie|Tylko Windows Phone 8.1|Tak|Tak (tylko Samsung KNOX)|
|**Wymagaj hasła w celu dostępu do sklepu z aplikacjami**|Nie|Nie|Nie|Tak|Nie|
|**Zezwalaj na zakupy w aplikacji**|Nie|Nie|Nie|Tak|Nie|
|**Zezwalaj na zarządzane dokumenty w innych niezarządzanych aplikacjach**|Nie|Nie|Nie|iOS 7 i nowsze|Nie|
|**Zezwalaj na niezarządzane dokumenty w innych zarządzanych aplikacjach**|Nie|Nie|Nie|iOS 7 i nowsze|Nie|
|**Zezwalaj na wideokonferencje**|Nie|Nie|Nie|Tak|Nie|
|**Zezwala na zawartość dla dorosłych w sklepie z multimediami**|Nie|Nie|Nie|Tak|Nie|
|**Zezwalaj na instalacje aplikacji**|Nie|Nie|Nie|iOS 6 i nowsze|Nie|

## Ustawienia aplikacji — gry

|Nazwa ustawienia|Windows 8.1 i Windows RT 8.1|Windows RT|Windows Phone 8 i Windows Phone 8.1|iOS|Android i Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Zezwalaj na dodawanie znajomych w aplikacji Game Center**|Nie|Nie|Nie|Tak|Nie|
|**Zezwalaj na gry dla wielu graczy**|Nie|Nie|Nie|Tak|Nie|

## Ustawienia możliwości urządzenia — sprzęt

|Nazwa ustawienia|Windows 8.1 i Windows RT 8.1|Windows RT|Windows Phone 8 i Windows Phone 8.1|iOS|Android i Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Zezwalaj na używanie aparatu**|Nie|Nie|Tylko Windows Phone 8.1|Tak|Tak|
|**Zezwalaj na używanie magazynu wymiennego**|Nie|Nie|Tak|Nie|Tak (tylko Samsung KNOX)|
|**Zezwalaj na połączenia Wi-Fi**|Nie|Nie|Tylko Windows Phone 8.1|Nie|Tak (tylko Samsung KNOX)|
|**Zezwalaj na tethering Wi-Fi**|Nie|Nie|Tylko Windows Phone 8.1|Nie|Tak (tylko Samsung KNOX)|
|**Zezwalaj na automatyczne łączenie z bezpłatnymi punktami hotspot Wi-Fi**|Nie|Nie|Tylko Windows Phone 8.1|Nie|Nie|
|**Zezwalaj na raportowanie informacji o punktach hotspot Wi-Fi**<br /><br />To ustawienie umożliwia wysyłanie informacji dotyczących połączeń Wi-Fi, aby ułatwić odnajdywanie połączeń w pobliżu.|Nie|Nie|Tylko Windows Phone 8.1|Nie|Nie|
|**Zezwalaj na używanie funkcji geolokalizacji**<br /><br />To ustawienie umożliwia urządzeniu korzystanie z informacji o lokalizacji.|Nie|Nie|Tylko Windows Phone 8.1|Nie|Tak (tylko Samsung KNOX)|
|**Zezwalaj na komunikację NFC**<br /><br />To ustawienie umożliwia wykonywanie operacji korzystających z komunikacji NFC.|Nie|Nie|Tylko Windows Phone 8.1|Nie|Tak (tylko Samsung KNOX)|
|**Zezwalaj na połączenia Bluetooth**|Nie|Nie|Tylko Windows Phone 8.1|Nie|Tak (tylko Samsung KNOX)|
|**Zezwalaj na wyłączenie urządzenia**<br>Jeśli to ustawienie jest wyłączone, ustawienie **Liczba dopuszczalnych nieudanych logowań przed wyczyszczeniem danych z urządzenia** dla urządzeń z systemem Samsung KNOX nie działa.|Nie|Nie|Nie|Nie|Tak (tylko Samsung KNOX)|

## Ustawienia możliwości urządzenia — połączenie komórkowe

|Nazwa ustawienia|Windows 8.1 i Windows RT 8.1|Windows RT|Windows Phone 8 i Windows Phone 8.1|iOS|Android i Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Zezwalaj na roaming połączeń głosowych**|Nie|Nie|Nie|Tak|Tak (tylko Samsung KNOX)|
|**Zezwalaj na roaming danych**|Tak|Nie|Nie|Tak|Tak (tylko Samsung KNOX)|
|**Zezwalaj na automatyczną synchronizację podczas roamingu**|Nie|Nie|Nie|Tak|Nie|
|**Zezwalaj na obsługę wiadomości SMS/MMS**|Nie|Nie|Nie|Nie|Tak (tylko Samsung KNOX)|

## Ustawienia możliwości urządzenia — funkcje

|Nazwa ustawienia|Windows 8.1 i Windows RT 8.1|Windows RT|Windows Phone 8 i Windows Phone 8.1|iOS|Android i Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Zezwalaj na asystenta głosowego**|Nie|Nie|Nie|Tak|Tak (tylko Samsung KNOX)|
|**Zezwalaj na asystenta głosowego, gdy urządzenie jest zablokowane**|Nie|Nie|Nie|Tak|Nie|
|**Zezwalaj na wybieranie głosowe**|Nie|Nie|Nie|Tak|Tak (tylko Samsung KNOX)|
|**Zezwalaj na kopiowanie i wklejanie**|Nie|Nie|Tylko Windows Phone 8.1|Nie|Tak (tylko Samsung KNOX)|
|**Zezwalaj na udostępnianie Schowka między aplikacjami**|Nie|Nie|Nie|Nie|Tak (tylko Samsung KNOX)|
|**Zezwalaj na YouTube**|Nie|Nie|Nie|Nie|Tak (tylko Samsung KNOX)|

### Zobacz także
[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Aug16_HO3-->


