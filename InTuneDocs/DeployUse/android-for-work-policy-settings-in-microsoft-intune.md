---

title: Ustawienia zasad programu Android for Work | Microsoft Intune
description: "Utwórz zasady określające ustawienia i funkcje na urządzeniach z programem Android for Work zarządzanych za pomocą usługi Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 35a53076-74d6-486d-b201-e0da2e170008
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 32bded5047b1a08738418e3e36382eeae1a5f3b4
ms.openlocfilehash: f7c676b25f5dd5b7ee1d1d7c1b51b75a41b5c102


---

# Ustawienia zasad programu Android for Work w usłudze Microsoft Intune

Usługa Intune udostępnia szereg wbudowanych ustawień ogólnych, które można skonfigurować na urządzeniach z programem Android for Work.

## Ogólne zasady konfiguracji

Za pomocą **zasad ogólnych konfiguracji programu Android for Work** w usłudze Intune skonfiguruj ustawienia zabezpieczeń i profilu służbowego dla urządzeń z programem Android for Work.

Jeśli w tym temacie nie opisano ustawienia, którego szukasz, możesz mieć możliwość utworzenia go za pomocą niestandardowych zasad systemu Android, które pozwalają sterować urządzeniem za pomocą ustawień OMA-URI. Aby uzyskać więcej informacji, przejdź do sekcji [Ustawienia zasad niestandardowych](#custom-policy-settings) w dalszej części tego tematu.

> [!TIP]
> Urządzenia są automatycznie szyfrowane podczas aprowizacji profilu służbowego. Nie można zmienić tego ustawienia.

### Ustawienia hasła

|Nazwa ustawienia|Szczegóły|
|----------------|-|
|**Wymagaj hasła do odblokowania urządzeń przenośnych**|Określa, czy na zarządzanych urządzeniach wymagane jest hasło. Wybierz spośród opcji:<br><br>- **Złożone** — wymaga co najmniej jednej litery, jednej cyfry i jednego symbolu<br>- **Alfanumeryczne** — wymaga co najmniej jednej cyfry i jednego znaku alfabetycznego<br>- **Alfabetyczne** — wymaga co najmniej liter lub symboli<br>- **Złożone liczbowych** — wymaga znaków numerycznych, które się nie powtarzają ani nie są liczbami kolejnymi<br>- **Numeryczne**<br><br>Jeśli to ustawienie nie jest włączone, nie ma żadnych wymagań dotyczących złożoności.|
|**Minimalna długość hasła**|Określa minimalną liczbę znaków lub cyfr w haśle.|
|**Liczba minut nieaktywności przed zablokowaniem urządzenia**|Określa liczbę minut braku aktywności użytkownika przed automatycznym zablokowaniem urządzenia.|
|**Zezwalaj na użycie blokady inteligentnej i innych agentów zaufania**<br>(system Android 6 i nowsze)|Umożliwia sterowanie funkcją blokady inteligentnej na zgodnych urządzeniach z systemem Android. Ta funkcja telefonu, czasami znana jako funkcja agentów zaufania, umożliwia wyłączenie lub obejście hasła ekranu blokady urządzenia, jeśli urządzenie jest w zaufanej lokalizacji (np. gdy zostało podłączone do danego urządzenia Bluetooth lub znajduje się w pobliżu tagu NFC). Możesz użyć tego ustawienia, aby uniemożliwić użytkownikom konfigurowanie funkcji blokady inteligentnej.|
|**Liczba powtórzonych nieudanych logowań przed usunięciem profilu służbowego**|Określa liczbę dopuszczalnych nieudanych logowań przed usunięciem profilu służbowego z urządzenia. Ta operacja nie powoduje pełnego wyczyszczenia urządzenia.|
|**Pamiętaj historię haseł**|Zapobiega ponownemu użyciu wcześniej używanych haseł.|
|**Pamiętaj historię haseł** - **Zapobiegaj ponownemu używaniu poprzednich haseł**|Określa liczbę wcześniej używanych haseł do zapamiętania.|
|**Wygaśnięcie hasła (dni)**|Określa liczbę dni, po której należy zmienić hasło urządzenia.|
|**Zezwalaj na odblokowanie na podstawie linii papilarnych**<br>(system Android 6 i nowsze)|Pozawala odblokowywać odciskiem palca urządzenia obsługujące tę funkcję.|


### Ustawienia profilu służbowego

|Nazwa ustawienia|Szczegóły|
|----------------|-|
|**Zezwalaj na współużytkowanie danych między profilem służbowym i osobistym**|Pozwala aplikacjom w profilu służbowym udostępniać dane aplikacjom w profilu osobistym użytkownika. Wybierz spośród opcji:<br><br>- **Uniemożliwiaj wszelkie udostępnianie poza granice**<br>- **Aplikacje w profilu służbowym mogą obsługiwać żądania udostępniania z profilu osobistego**<br>- **Brak ograniczeń dotyczących udostępniania**|
|**Ukryj powiadomienia profilu służbowego, gdy urządzenie jest zablokowane**<br>(system Android 6 i nowsze)|Pozwala określić, czy mają być wyświetlane jakiekolwiek powiadomienia z profilu służbowego, gdy urządzenie jest zablokowane.|
|**Ustaw domyślne zasady uprawnień aplikacji**<br>(system Android 6 i nowsze)|Powoduje ustawienie domyślnych zasad uprawnień dla wszystkich aplikacji w profilu służbowym.|




## Ustawienia zasad niestandardowych
**Niestandardowe zasady konfiguracji programu Android for Work** w usłudze Microsoft Intune umożliwiają wdrożenie ustawień OMA-URI, których można użyć do sterowania funkcjami na urządzeniach z programem Android form Work. Są to ustawienia standardowe używane przez wielu producentów urządzeń przenośnych do sterowania funkcjami urządzeń.

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
    |**Nazwa ustawienia**|Wprowadź unikatową nazwę dla ustawienia OMA-URI, aby ułatwić jego identyfikację na liście ustawień.|
    |**Opis ustawienia**|Podaj opis, który zawiera omówienie ustawienia oraz inne istotne informacje, które ułatwią jego wyszukanie.|
    |**Typ danych**|Wybierz typ danych, zgodnie z którym określisz to ustawienie OMA-URI. Wybierz jedną z opcji: **Ciąg, Ciąg (XML), Data i godzina, Liczba całkowita, Liczba zmiennoprzecinkowa** lub **Wartość logiczna**.|
    |**OMA-URI (z uwzględnieniem wielkości liter)**|Określ identyfikator OMA-URI, dla którego chcesz podać ustawienie.|
    |**Wartość**|Określ wartość, która będzie kojarzona z określonym wcześniej identyfikatorem OMA-URI.|

### Przykłady

- [Tworzenie profilu sieci Wi-Fi z użyciem klucza wstępnego](pre-shared-key-wi-fi-profile.md)
- [Używanie zasad niestandardowych do tworzenia profilu sieci VPN dla aplikacji na urządzeniach z systemem Android](per-app-vpn-for-android-pulse-secure.md)

### Zobacz także
[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)


<!--HONumber=Oct16_HO2-->


