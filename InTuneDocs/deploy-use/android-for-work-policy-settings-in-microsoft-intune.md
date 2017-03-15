---

title: Ustawienia zasad programu Android for Work | Microsoft Docs
description: "Utwórz zasady określające ustawienia i funkcje na urządzeniach z programem Android for Work zarządzanych za pomocą usługi Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 35a53076-74d6-486d-b201-e0da2e170008
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 02c844a5b38023a6dfc6c4ef1de81e1416601fba
ms.openlocfilehash: b0c3520c7c1fd29a631587fe1a69d4c411099cb4
ms.lasthandoff: 03/07/2017


---

# <a name="android-for-work-policy-settings-in-microsoft-intune"></a>Ustawienia zasad programu Android for Work w usłudze Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Usługa Intune udostępnia szereg wbudowanych ustawień ogólnych, które można skonfigurować na [urządzeniach z programem Android for Work](android-for-work.md).

## <a name="general-configuration-policy"></a>Ogólne zasady konfiguracji

Za pomocą **zasad ogólnych konfiguracji programu Android for Work** w usłudze Intune skonfiguruj ustawienia zabezpieczeń i profilu służbowego dla urządzeń z programem Android for Work.

Jeśli w tym temacie nie opisano ustawienia, którego szukasz, możesz mieć możliwość utworzenia go za pomocą niestandardowych zasad systemu Android, które pozwalają sterować urządzeniem za pomocą ustawień OMA-URI. Aby uzyskać więcej informacji, przejdź do sekcji [Ustawienia zasad niestandardowych](#custom-policy-settings) w dalszej części tego tematu.

> [!TIP]
> Urządzenia są automatycznie szyfrowane podczas aprowizacji profilu służbowego. Nie można zmienić tego ustawienia.

### <a name="password-settings"></a>Ustawienia hasła

|Nazwa ustawienia|Szczegóły|
|----------------|-|
|**Wymagaj hasła do odblokowania urządzeń przenośnych**|Określa, czy na zarządzanych urządzeniach wymagane jest hasło. Wybierz spośród opcji:<br><br>- **Złożone** — wymaga co najmniej jednej litery, jednej cyfry i jednego symbolu<br>- **Alfanumeryczne** — wymaga co najmniej jednej cyfry i jednego znaku alfabetycznego<br>- **Alfabetyczne** — wymaga co najmniej liter lub symboli<br>- **Złożone liczbowe** — wymaga znaków numerycznych, które się nie powtarzają ani nie są liczbami kolejnymi<br>- **Numeryczne**<br><br>Jeśli to ustawienie nie jest włączone, nie ma żadnych wymagań dotyczących złożoności.|
|**Minimalna długość hasła**|Określa minimalną liczbę znaków lub cyfr w haśle.|
|**Liczba minut nieaktywności przed zablokowaniem urządzenia**|Określa liczbę minut braku aktywności użytkownika przed automatycznym zablokowaniem urządzenia.|
|**Zezwalaj na użycie blokady inteligentnej i innych agentów zaufania**<br>(system Android 6 i nowsze)|Umożliwia sterowanie funkcją blokady inteligentnej na zgodnych urządzeniach z systemem Android. Ta funkcja telefonu, czasami znana jako funkcja agentów zaufania, umożliwia wyłączenie lub obejście hasła ekranu blokady urządzenia, jeśli urządzenie jest w zaufanej lokalizacji (np. gdy zostało podłączone do danego urządzenia Bluetooth lub znajduje się w pobliżu tagu NFC). Możesz użyć tego ustawienia, aby uniemożliwić użytkownikom konfigurowanie funkcji blokady inteligentnej.|
|**Liczba powtórzonych nieudanych logowań przed usunięciem profilu służbowego**|Określa liczbę dopuszczalnych nieudanych logowań przed usunięciem profilu służbowego z urządzenia. Ta operacja nie powoduje pełnego wyczyszczenia urządzenia.|
|**Pamiętaj historię haseł**|Zapobiega ponownemu użyciu wcześniej używanych haseł.|
|**Pamiętaj historię haseł** - **Zapobiegaj ponownemu używaniu poprzednich haseł**|Określa liczbę wcześniej używanych haseł do zapamiętania.|
|**Dni do wygaśnięcia hasła**|Określa liczbę dni, po której należy zmienić hasło urządzenia.|
|**Zezwalaj na odblokowanie na podstawie linii papilarnych**<br>(system Android 6 i nowsze)|Pozawala odblokowywać odciskiem palca urządzenia obsługujące tę funkcję.|


### <a name="work-profile-settings"></a>Ustawienia profilu służbowego

|Nazwa ustawienia|Szczegóły|
|----------------|-|
|**Zezwalaj na współużytkowanie danych między profilem służbowym i osobistym**|Pozwala aplikacjom w profilu służbowym udostępniać dane aplikacjom w profilu osobistym użytkownika. Wybierz spośród opcji:<br><br>- **Uniemożliwiaj wszelkie udostępnianie poza granice**<br>- **Aplikacje w profilu służbowym mogą obsługiwać żądania udostępniania z profilu osobistego**<br>- **Brak ograniczeń dotyczących udostępniania**|
|**Ukryj powiadomienia profilu służbowego, gdy urządzenie jest zablokowane**<br>(system Android 6 i nowsze)|Pozwala określić, czy mają być wyświetlane jakiekolwiek powiadomienia z profilu służbowego, gdy urządzenie jest zablokowane.|
|**Ustaw domyślne zasady uprawnień aplikacji**<br>(system Android 6 i nowsze)|Powoduje ustawienie domyślnych zasad uprawnień dla wszystkich aplikacji w profilu służbowym. Począwszy od systemu Android 6, podczas uruchamiania aplikacji użytkownikom końcowym są wyświetlane monity o zaakceptowanie wymaganych uprawnień.  To ustawienie zasad umożliwia zespołowi IT określenie, czy i w jaki sposób użytkownicy otrzymują monit o przyznanie uprawnień aplikacji w profilu służbowym. <br/><br/>Przykładowo — zespół IT może wypchnąć do profilu służbowego aplikację, która wymaga dostępu do lokalizacji.  W przypadku zastosowania standardowej konfiguracji w aplikacji zostałoby wyświetlone wyskakujące okno dialogowe z pytaniem, czy użytkownik chce udzielić aplikacji dostępu do lokalizacji. Użytkownik mógłby zezwolić na dostęp lub wybrać opcję odmowy dostępu.  Ta zasada pozwala zespołowi IT zdecydować, czy wszystkie uprawnienia powinny być przyznawane automatycznie bez wyświetlania monitu, czy ma być automatycznie wybierana opcja odmowy dostępu bez wyświetlania monitu, czy też decyzja ma zostać pozostawiona użytkownikowi końcowemu.|


## <a name="custom-policy-settings"></a>Ustawienia zasad niestandardowych
**Niestandardowe zasady konfiguracji programu Android for Work** w usłudze Microsoft Intune umożliwiają wdrożenie ustawień OMA-URI, których można użyć do sterowania funkcjami na urządzeniach z programem Android form Work. Są to ustawienia standardowe używane przez wielu producentów urządzeń przenośnych do sterowania funkcjami urządzeń.

Ta funkcja ma umożliwić wdrażanie ustawień systemu Android, których nie można skonfigurować przy użyciu zasad usługi Intune.
Obecnie usługa Intune obsługuje tylko ograniczoną liczbę zasad niestandardowych systemu Android. Zobacz przykłady w tym temacie, aby dowiedzieć się, które zasady możesz skonfigurować.

### <a name="general-settings"></a>Ustawienia ogólne

|Nazwa ustawienia|Szczegóły|
    |----------------|--------------------|
    |**Nazwa**|Wprowadź unikatową nazwę niestandardowych zasad systemu Android, która pomoże je zidentyfikować w konsoli usługi Intune.|
    |**Opis**|Podaj opis zawierający omówienie zasad niestandardowych systemu Android oraz inne istotne informacje ułatwiające ich wyszukanie.|

### <a name="oma-uri-settings"></a>Ustawienia OMA-URI

   |Nazwa ustawienia|Szczegóły|
    |--------|--------------------|
    |**Nazwa ustawienia**|Wprowadź unikatową nazwę dla ustawienia OMA-URI, aby ułatwić jego identyfikację na liście ustawień.|
    |**Opis ustawienia**|Podaj opis, który zawiera omówienie ustawienia oraz inne istotne informacje, które ułatwią jego wyszukanie.|
    |**Typ danych**|Wybierz typ danych, zgodnie z którym określisz to ustawienie OMA-URI. Wybierz jedną z opcji: **Ciąg, Ciąg (XML), Data i godzina, Liczba całkowita, Liczba zmiennoprzecinkowa** lub **Wartość logiczna**.|
    |**OMA-URI (z uwzględnieniem wielkości liter)**|Określ identyfikator OMA-URI, dla którego chcesz podać ustawienie.|
    |**Wartość**|Określ wartość, która będzie kojarzona z określonym wcześniej identyfikatorem OMA-URI.|

### <a name="examples"></a>Przykłady

- [Tworzenie profilu sieci Wi-Fi z użyciem klucza wstępnego](pre-shared-key-wi-fi-profile.md)
- [Tworzenie profilu sieci VPN dla aplikacji na urządzeniach z systemem Android za pomocą zasad niestandardowych](per-app-vpn-for-android-pulse-secure.md)

### <a name="see-also"></a>Zobacz też
[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

