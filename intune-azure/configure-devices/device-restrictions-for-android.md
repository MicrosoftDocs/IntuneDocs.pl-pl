---
title: "Ustawienia ograniczeń urządzenia z systemem Android w usłudze Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje na temat ustawień usługi Intune służących do kontrolowania ustawień i funkcjonalności na urządzeniach z systemem Android."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 3ba986b624e602f05eb6ab25ec30e9d58173dbd8
ms.lasthandoff: 04/19/2017


---

# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-microsoft-intune"></a>Ustawienia ograniczeń urządzenia z systemami Android i Samsung KNOX Standard w usłudze Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Ogólne

|||||
|-|-|-|-|
|Nazwa ustawienia|Szczegóły|Android 4.0+|Samsung KNOX Standard|
|**Aparat fotograficzny**|Zezwala na korzystanie z aparatu fotograficznego urządzenia.|Tak|Tak|
|**Kopiowanie i wklejanie**|Umożliwia używanie funkcji kopiowania i wklejania na urządzeniu.|Nie|Tak|
|**Udostępnianie Schowka między aplikacjami**|Umożliwia wykorzystanie schowka do kopiowania i wklejania danych między aplikacjami.|Nie|Tak|
|**Przesłanie danych diagnostycznych**|Uniemożliwia użytkownikowi użycie funkcji przesyłania danych diagnostycznych z urządzenia.|Nie|Tak|
|**Resetuj do ustawień fabrycznych**|Umożliwia użytkownikowi przeprowadzenie resetowania urządzenia do ustawień fabrycznych.|Nie|Tak|
|**Geolokalizacja**|Umożliwia urządzeniu korzystanie z informacji o lokalizacji (tylko Samsung KNOX Standard).|Nie|Tak|
|**Wyłączanie**|Umożliwia użytkownikowi wyłączanie urządzenia.<br>Jeśli to ustawienie jest wyłączone, ustawienie **Liczba nieudanych logowań przed wyczyszczeniem danych z urządzenia** na urządzeniach z systemem Samsung KNOX Standard nie działa.|Nie|Tak|
|**Przechwytywanie ekranu**|Umożliwia użytkownikowi przechwytywanie zawartości ekranu w formie obrazu.|Nie|Tak|
|**Asystent głosowy**|Umożliwia korzystanie z oprogramowania asystenta głosowego na urządzeniu.|Nie|Tak|
|**YouTube**|Umożliwia korzystanie z aplikacji YouTube na urządzeniu.|Nie|Tak|
|**Urządzenia udostępnione**|Konfigurowanie zarządzanego urządzenia z rozwiązaniem Samsung KNOX Standard jako urządzenia udostępnionego. W tym trybie użytkownicy końcowi mogą zalogować się na urządzeniu lub wylogować się z niego przy użyciu poświadczeń usługi Azure AD, a urządzenie jest zarządzane centralnie niezależnie od tego, czy jest używane.<br>Użytkownicy końcowi po zalogowaniu otrzymują dostęp do aplikacji, a także są stosowane wobec nich zasady. Gdy użytkownicy się wylogują, wszystkie dane aplikacji są usuwane.|Nie|Tak|

## <a name="password"></a>Hasło

|||||
|-|-|-|-|
|Nazwa ustawienia|Szczegóły|Android 4.0+|Samsung KNOX Standard|
|**Hasło**|Wymaga od użytkownika końcowego wprowadzenia hasła w celu uzyskania dostępu do urządzenia.|Tak|Tak|
|**Minimalna długość hasła**|Określa minimalną długość hasła, które musi skonfigurować użytkownik (od 4 do 16 znaków).|Tak|Tak|
|**Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu**|Określa liczbę minut braku aktywności przed automatycznym zablokowaniem urządzenia.|Tak|Tak|
|**Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia**|Określa liczbę dopuszczalnych nieudanych logowań przed wyczyszczeniem danych z urządzenia.|Tak|Tak|
|**Dni do wygaśnięcia hasła**|Określa liczbę dni, po której należy zmienić hasło urządzenia.|Tak|Tak|
|**Wymagany typ hasła**|Określa wymagany poziom złożoności hasła oraz możliwość stosowania urządzeń biometrycznych. Wybierz spośród opcji:<br><br>    -     **Ustawienie domyślne urządzenia**<br>-     **Zabezpieczenia biometryczne na niskim poziomie**<br>    -     **Co najmniej numeryczne**<br>    -     **Złożona wartość liczbowa** (powtarzające się lub kolejne cyfry, np. „1111” lub „1234”, są niedozwolone)<sup>1</sup><br>    -     **Co najmniej alfabetyczne**<br>    -     **Co najmniej alfanumeryczne**<br>    -     **Co najmniej alfanumeryczne z symbolami**|Tak|Tak|
|**Zapobiegaj ponownemu używaniu poprzednich haseł**|Uniemożliwia użytkownikowi końcowemu utworzenie hasła, które było wcześniej używane.|Tak|Tak|
|**Odblokowywanie za pomocą odcisku palca**|Umożliwia korzystanie z odcisku palca do odblokowania obsługiwanych urządzeń.|Nie|Tak|
|**Blokada Smart Lock i inni agenci zaufania**|Umożliwia sterowanie funkcją Smart Lock na zgodnych urządzeniach z systemem Android (tylko Samsung KNOX Standard 5.0 lub nowszy). Ta funkcja telefonu, czasami znana jako funkcja agentów zaufania, umożliwia wyłączenie lub obejście hasła ekranu blokady urządzenia, jeśli urządzenie jest w zaufanej lokalizacji (np. gdy zostało podłączone do danego urządzenia Bluetooth lub znajduje się w pobliżu tagu NFC). Możesz użyć tego ustawienia, aby uniemożliwić użytkownikom konfigurowanie funkcji blokady inteligentnej.|Tak (wersja 5.0 i nowsze)|Nie|
|**Szyfrowanie**|Wymaga szyfrowania plików na urządzeniu.|Tak|Tak|

<sup>1</sup>Przed przypisaniem tego ustawienia do urządzeń upewnij się, że aplikacja Portal firmy została zaktualizowana na urządzeniach docelowych do najnowszej wersji.

W przypadku skonfigurowania ustawienia **Złożona wartość liczbowa** i jego przypisania do urządzenia z systemem Android w wersji starszej niż 5.0 wystąpią opisane poniżej konsekwencje.
- Jeśli w urządzeniu uruchomiona jest aplikacja Portal firmy w wersji wcześniejszej niż 1704, do urządzenia nie będą mieć zastosowania żadne zasady dotyczące numeru PIN, a w portalu usługi Intune będzie wyświetlany błąd.
- Jeśli aplikacja Portal firmy została zaktualizowana do wersji 1704, w urządzeniu zostanie zastosowany tylko prosty numer PIN. To ustawienie nie jest obsługiwane w wersjach systemu Android wcześniejszych niż 5.0. W portalu usługi Intune nie jest wyświetlany błąd.


## <a name="google-play-store"></a>Sklep Google Play

|||||
|-|-|-|-|
|Nazwa ustawienia|Szczegóły|Android 4.0+|Samsung KNOX Standard|
|**Sklep Google Play**|Umożliwia użytkownikowi uzyskiwanie dostępu do sklepu Google Play na urządzeniu.|Nie|Tak|

## <a name="restricted-apps"></a>Aplikacje z ograniczeniami

Na liście aplikacji z ograniczeniami można skonfigurować jedną z następujących list:

Lista **Aplikacje zabronione** — lista aplikacji (niezarządzanych przez usługę Intune), których użytkownicy nie mogą instalować ani uruchamiać.
Lista **Zatwierdzone aplikacje** — lista aplikacji, które użytkownicy mogą instalować. Aby utrzymać zgodność, użytkownicy nie mogą instalować aplikacji, których nie ma na liście. Aplikacje zarządzane przez usługę Intune są automatycznie traktowane jako dozwolone.
Profile urządzeń zawierające ustawienia aplikacji z ograniczeniami należy wdrożyć dla grup użytkowników.

Aby skonfigurować listę, kliknij przycisk **Dodaj**, a następnie wprowadź wybraną nazwę oraz opcjonalnie wydawcę aplikacji i adres URL aplikacji w sklepie z aplikacjami.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Jak określić adres URL aplikacji w sklepie

Aby określić adres URL aplikacji na liście aplikacji zgodnych i niezgodnych, wykonaj następujące działania:

W sekcji [Aplikacje w sklepie Google Play](https://play.google.com/store/apps) wyszukaj aplikację, której chcesz użyć.

Otwórz stronę instalacji aplikacji i skopiuj jej adres URL do schowka. Możesz teraz użyć tego adresu URL na liście zgodnych lub niezgodnych aplikacji.

Przykład: wyszukaj w sklepie Google Play aplikację Microsoft Office Mobile. Adres URL, którego użyjesz, to **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

### <a name="additional-options"></a>Opcje dodatkowe

Możesz również kliknąć przycisk **Importuj**, aby wypełnić listę danymi z pliku CSV w formacie <*adres url aplikacji*>, <*nazwa aplikacji*>, <*wydawca aplikacji*>, lub kliknąć przycisk **Eksportuj**, aby utworzyć plik CSV zawierający listę aplikacji z ograniczeniami w tym samym formacie.        

## <a name="browser"></a>Przeglądarka
|||||
|-|-|-|-|
|Nazwa ustawienia|Szczegóły|Android 4.0+|Samsung KNOX Standard|
|**Przeglądarka internetowa**|Określa, czy można używać domyślnej przeglądarki sieci Web na urządzeniu.|Nie|Tak|
|**Autowypełnianie**|Umożliwia korzystanie z funkcji automatycznego uzupełniania w przeglądarce sieci Web.|Nie|Tak|
|**Plik cookie**|Zezwala na używanie plików cookie przez przeglądarkę sieci Web urządzenia.|Nie|Tak|
|**JavaScript**|Umożliwia uruchamianie skryptów Java w przeglądarce sieci Web na urządzeniu.|Nie|Tak|
|**Okna podręczne**|Umożliwia blokowanie wyskakujących okienek w przeglądarce sieci Web.|Nie|Tak|

## <a name="cloud-and-storage"></a>Chmura i magazyn
|||||
|-|-|-|-|
|Nazwa ustawienia|Szczegóły|Android 4.0+|Samsung KNOX Standard|
|**Kopia zapasowa w usłudze Google**|Zezwala na korzystanie z kopii zapasowej Google.|Nie|Tak|
|**Automatyczna synchronizacja konta Google**|Zezwala na automatyczną synchronizację ustawień konta Google.|Nie|Tak|
|**Magazyn wymienny**|Umożliwia używanie na urządzeniu magazynu wymiennego, takiego jak karta SD.|Nie|Tak|
|**Szyfrowanie kart pamięci**|Określa, czy karta pamięci urządzenia musi być szyfrowana.|Nie|Tak|

## <a name="cellular-and-connectivity"></a>Sieć komórkowa i łączność
|||||
|-|-|-|-|
|Nazwa ustawienia|Szczegóły|Android 4.0+|Samsung KNOX Standard|
|**Roaming danych**|Zezwala na roaming danych, gdy urządzenie znajduje się w sieci komórkowej.|Nie|Tak|
|**Wiadomości SMS/MMS**|Umożliwia korzystanie z wiadomości SMS i MMS na urządzeniu.|Nie|Tak|
|**Wybieranie głosowe**|Włącza lub wyłącza funkcję wybierania głosowego na urządzeniu.|Nie|Tak|
|**Roaming połączeń głosowych**|Zezwala na roaming połączeń głosowych, gdy urządzenie jest w sieci komórkowej.|Nie|Tak|
|**Bluetooth**|Umożliwia używanie połączeń Bluetooth na urządzeniu.|Nie|Tak|
|**NFC**|Umożliwia wykonywanie operacji korzystających z komunikacji zbliżeniowej (NFC), jeśli urządzenie ją obsługuje.|Nie|Tak|
|**Wi-Fi**|Umożliwia korzystanie z funkcji Wi-Fi urządzenia.|Nie|Tak|
|**Tethering Wi-Fi**|Umożliwia korzystanie z funkcji tetheringu Wi-Fi urządzenia.|Nie|Tak|

## <a name="kiosk"></a>Kiosk
|||||
|-|-|-|-|
|Nazwa ustawienia|Szczegóły|Android 4.0+|Samsung KNOX Standard|
|**Wybierz zarządzaną aplikację**|Przejdź do odpowiedniej lokalizacji i wybierz zarządzaną aplikację, która może działać na urządzeniu pozostającym w trybie kiosku (aplikacje wskazane za pomocą linku do sklepu nie są aktualnie obsługiwane). Na tym urządzeniu nie będzie można uruchamiać żadnych innych aplikacji.|Nie|Tak|
|**Przycisk usypiania ekranu**|Włącza lub wyłącza przycisk usypiania/budzenia ekranu na urządzeniu.|Nie|Tak|
|**Przyciski regulacji głośności**|Włącza lub wyłącza przyciski regulacji głośności na urządzeniu.|Nie|Tak|

