---
title: "Ustawienia ograniczeń urządzenia z systemem Android w usłudze Intune"
titlesuffix: Azure portal
description: "Informacje na temat ustawień usługi Intune służących do kontrolowania ustawień i funkcjonalności na urządzeniach z systemem Android."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 09/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 97e125d768ca7b0cf58a2892d78675dfa42ef7ce
ms.sourcegitcommit: fa0f0402dfd25ec56a0df08c23708c7e2ad41120
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/29/2017
---
# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-microsoft-intune"></a>Ustawienia ograniczeń urządzenia z systemami Android i Samsung KNOX Standard w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Te ustawienia wraz z zasadami ograniczeń urządzenia z systemem Android są pomocne w konfigurowaniu urządzeń w Twojej organizacji.

>[!TIP]
>Jeśli żądane ustawienia nie są dostępne, możesz skonfigurować urządzenia przy użyciu [profilu niestandardowego](custom-settings-android.md). 

## <a name="general"></a>Ogólne

- **Aparat fotograficzny** — umożliwia korzystanie z aparatu fotograficznego urządzenia.
- **Kopiuj i wklej (tylko system Samsung KNOX)** — umożliwia używanie funkcji kopiowania i wklejania na urządzeniu.
- **Udostępnianie schowka między aplikacjami (tylko system Samsung KNOX)** — umożliwia korzystanie ze schowka w celu kopiowania i wklejania między aplikacjami.
- **Przesyłanie danych diagnostycznych (tylko system Samsung KNOX)** — uniemożliwia użytkownikowi przesyłanie danych diagnostycznych z urządzenia.
- **Resetowanie do ustawień fabrycznych (tylko system Samsung KNOX)** — umożliwia użytkownikowi zresetowanie urządzenia do ustawień fabrycznych.
- **Geolokalizacja (tylko system Samsung KNOX)** — umożliwia korzystanie z informacji o lokalizacji na urządzeniu.
- **Wyłączanie (tylko system Samsung KNOX)** — umożliwia użytkownikowi wyłączanie urządzenia.<br>Po wyłączeniu nie można ustawić opcji **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia**.
- **Przechwytywanie ekranu (tylko system Samsung KNOX)** — umożliwia użytkownikowi przechwytywanie zawartości ekranu w formie obrazu.
- **Asystent głosowy (tylko system Samsung KNOX)** — umożliwia korzystanie z oprogramowania Asystenta głosowego na urządzeniu.
- **YouTube (tylko system Samsung KNOX)** — umożliwia korzystanie z aplikacji YouTube na urządzeniu.
- **Urządzenia udostępnione (tylko system Samsung KNOX)** — umożliwia skonfigurowanie zarządzanego urządzenia z systemem Samsung KNOX Standard jako urządzenia udostępnionego. W tym trybie użytkownicy końcowi mogą zalogować się na urządzeniu i wylogować się z niego przy użyciu swoich poświadczeń usługi Azure AD. Urządzenie nadal będzie zarządzane, niezależnie od tego, czy jest używane.<br>Gdy jest używana w połączeniu z profilem certyfikatu SCEP, funkcja ta umożliwia użytkownikom końcowym udostępnianie urządzenia z tym samym zestawem aplikacji wszystkim użytkownikom, ale przy użyciu ich własnych certyfikatów użytkownika SCEP.  Gdy użytkownicy się wylogują, wszystkie dane aplikacji są usuwane.  Funkcja ta jest ograniczona tylko do aplikacji LOB.

## <a name="password"></a>Hasło

- **Hasło** — wymaga od użytkownika końcowego wprowadzenia hasła w celu uzyskania dostępu do urządzenia.|Tak|Tak|
- **Minimalna długość hasła** — określa minimalną długość hasła, które musi skonfigurować użytkownik (od 4 do 16 znaków).
- **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu** — określa liczbę minut braku aktywności przed automatycznym zablokowaniem urządzenia.
- **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia** — określa liczbę dopuszczalnych nieudanych logowań przed wyczyszczeniem zawartości urządzenia.
- **Wygaśnięcie hasła (dni)** — określa liczbę dni, po której należy zmienić hasło urządzenia.
-  **Wymagany typ hasła** — określa wymagany poziom złożoności hasła oraz możliwość stosowania urządzeń biometrycznych. Wybierz spośród opcji:
    - **Ustawienie domyślne urządzenia**
    - **Zabezpieczenia biometryczne na niskim poziomie**
    - **Co najmniej numeryczne**
    - **Złożona wartość liczbowa** — powtarzające się lub kolejne cyfry, np. „1111” lub „1234”, są niedozwolone<sup>1</sup>
    - **Co najmniej alfabetyczne**
    - **Co najmniej alfanumeryczne**
    - **Co najmniej alfanumeryczne z symbolami**
- **Zapobiegaj ponownemu używaniu poprzednich haseł** —nie dopuszcza do tego, by użytkownik końcowy utworzył hasło, które było wcześniej używane.
- **Odblokowywanie za pomocą odcisku palca (tylko system Samsung KNOX)** — umożliwia korzystanie z odcisku palca do odblokowania obsługiwanych urządzeń.
- **Blokada Smart Lock i inni agenci zaufania** — umożliwia sterowanie funkcją Smart Lock na niezgodnych urządzeniach z systemem Android (tylko Samsung KNOX Standard 5.0 lub nowszy). Ta funkcja telefonu, czasami znana jako funkcja agentów zaufania, umożliwia wyłączenie lub obejście hasła ekranu blokady urządzenia, jeśli urządzenie jest w zaufanej lokalizacji. Na przykład można z tego skorzystać, gdy urządzenie jest połączone z konkretnym urządzeniem Bluetooth lub znajduje się w pobliżu tagu NFC. Możesz użyć tego ustawienia, aby uniemożliwić użytkownikom konfigurowanie funkcji blokady inteligentnej.
- **Szyfrowanie** — wymaga szyfrowania plików na urządzeniu.

<sup>1</sup> Przed przypisaniem tego ustawienia do urządzeń upewnij się, że aplikacja Portal firmy została zaktualizowana na tych urządzeniach do najnowszej wersji.

W przypadku skonfigurowania ustawienia **Złożona wartość liczbowa** i jego przypisania do urządzenia z systemem Android w wersji starszej niż 5.0 wystąpią opisane poniżej konsekwencje.
- Jeśli na urządzeniu jest uruchomiona aplikacja Portal firmy w wersji wcześniejszej niż 1704, do urządzenia nie będą mieć zastosowania żadne zasady dotyczące numeru PIN, a w witrynie Azure Portal będzie wyświetlany błąd.
- Jeśli uruchomiona jest aplikacja Portal firmy w wersji 1704 lub nowszej, można stosować tylko prosty numer PIN. To ustawienie nie jest obsługiwane w wersjach systemu Android wcześniejszych niż 5.0. W witrynie Azure Portal nie jest wyświetlany błąd.


## <a name="google-play-store"></a>Sklep Google Play

- **Sklep Google Play (tylko system Samsung KNOX)** — umożliwia użytkownikowi dostęp do sklepu Google Play na urządzeniu.

## <a name="restricted-apps"></a>Aplikacje z ograniczeniami

Na liście aplikacji z ograniczeniami można skonfigurować jedną z poniższych list dla urządzeń z systemem Android i funkcją Samsung KNOX Standard:

Lista **Aplikacje zabronione** — lista aplikacji (niezarządzanych przez usługę Intune), których instalacja i uruchomienie przez użytkowników zostaną zgłoszone.
Lista **Zatwierdzone aplikacje** — lista aplikacji, które użytkownicy mogą instalować. Aby utrzymać zgodność, użytkownicy nie mogą instalować aplikacji, których nie ma na liście. Aplikacje zarządzane przez usługę Intune są automatycznie traktowane jako dozwolone.
Profile urządzeń zawierające ustawienia aplikacji z ograniczeniami należy przypisać do grup użytkowników.

Aby skonfigurować listę, kliknij przycisk **Dodaj**, a następnie wprowadź wybraną nazwę oraz opcjonalnie wydawcę aplikacji i adres URL aplikacji w sklepie z aplikacjami.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Jak określić adres URL aplikacji w sklepie

Aby określić adres URL aplikacji na liście aplikacji zgodnych i niezgodnych, wykonaj następujące działania:

W sekcji [Aplikacje w sklepie Google Play](https://play.google.com/store/apps) wyszukaj aplikację, której chcesz użyć.

Otwórz stronę instalacji aplikacji i skopiuj jej adres URL do schowka. Możesz teraz użyć tego adresu URL na listach zgodnych lub niezgodnych aplikacji.

Przykład: wyszukaj w sklepie Google Play aplikację Microsoft Office Mobile. Użyj następującego adresu URL: **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

### <a name="additional-options"></a>Opcje dodatkowe

Możesz również kliknąć opcję **Importuj**, aby pobrać listę z pliku CSV. Użyj formatu <*adres url aplikacji*>, <*nazwa aplikacji*>, <*wydawca aplikacji*> lub kliknij przycisk **Eksportuj**, aby utworzyć plik CSV zawierający listę aplikacji z ograniczeniami w tym samym formacie.      

## <a name="browser"></a>Przeglądarka

- **Przeglądarka internetowa (tylko system Samsung KNOX)** — określa, czy na urządzeniu można używać domyślnej przeglądarki internetowej.
- **Autowypełnianie (tylko system Samsung KNOX)** — umożliwia korzystanie z funkcji autowypełniania w przeglądarce internetowej.
- **Pliki cookie (tylko system Samsung KNOX)** — umożliwia używanie plików cookie przez przeglądarkę internetową na urządzeniu.
- **JavaScript (tylko system Samsung KNOX)** — umożliwia uruchamianie skryptów Java w przeglądarce internetowej na urządzeniu.
- **Wyskakujące okienka (tylko system Samsung KNOX)** — umożliwia blokowanie wyskakujących okienek w przeglądarce internetowej.

## <a name="allow-or-block-apps"></a>Zezwalanie na aplikacje lub ich blokowanie

Te ustawienia pozwalają wskazać aplikacje, które mogą być instalowane lub uruchamiane wyłącznie na urządzeniach z rozwiązaniem Samsung KNOX Standard.
Ponadto można również wskazać zainstalowane aplikacje, które będą ukryte dla użytkownika urządzenia. Użytkownicy nie mogą uruchamiać tych aplikacji.

- **Aplikacje, które mogą być instalowane (tylko rozwiązanie Samsung KNOX Standard)**
- **Aplikacje, których uruchamianie jest blokowane (tylko rozwiązanie Samsung KNOX Standard)**
- **Aplikacje ukryte przed użytkownikiem (tylko rozwiązanie Samsung KNOX Standard)**

Dla każdego ustawienia skonfiguruj listę aplikacji, wykonując jedną z następujących czynności:

- **Dodaj aplikacje według nazwy pakietu** — opcja używana głównie w odniesieniu do aplikacji LOB. Wprowadź nazwę aplikacji i nazwę pakietu aplikacji. 
- **Dodaj aplikacje według adresu URL** — wprowadź nazwę aplikacji i jej adres URL w sklepie Google Play.
- **Dodaj aplikacje zarządzane** — wybierz odpowiednią aplikację z listy aplikacji zarządzanych przy użyciu usługi Intune.

## <a name="cloud-and-storage"></a>Chmura i magazyn

- **Kopie zapasowe w usłudze Google (tylko system Samsung KNOX)** — umożliwia korzystanie z kopii zapasowych w usłudze Google.
- **Automatyczna synchronizacja konta Google (tylko system Samsung KNOX)** — umożliwia automatyczną synchronizację ustawień konta Google.
- **Magazyn wymienny (tylko system Samsung KNOX)** — umożliwia korzystanie na urządzeniu z magazynu wymiennego, np. karty SD.
- **Szyfrowanie na kartach pamięci (tylko system Samsung KNOX)** — określa, czy karta pamięci urządzenia musi być szyfrowana.

## <a name="cellular-and-connectivity"></a>Sieć komórkowa i łączność

- **Roaming danych (tylko system Samsung KNOX)** — umożliwia roaming danych, gdy urządzenie korzysta z sieci komórkowej.
- **Wiadomości SMS i MMS (tylko system Samsung KNOX)** — umożliwia korzystanie z wiadomości SMS i MMS na urządzeniu.
- **Wybieranie głosowe (tylko system Samsung KNOX)** — włącza lub wyłącza funkcję wybierania głosowego na urządzeniu.
- **Roaming połączeń głosowych (tylko system Samsung KNOX)** — umożliwia roaming połączeń głosowych, gdy urządzenie korzysta z sieci komórkowej.
- **Bluetooth (tylko system Samsung KNOX)** — umożliwia korzystanie z funkcji Bluetooth na urządzeniu.
- **NFC (tylko system Samsung KNOX)** — umożliwia wykonywanie operacji korzystających z komunikacji zbliżeniowej na obsługiwanych urządzeniach.
- **Wi-Fi (tylko system Samsung KNOX)** — umożliwia korzystanie z funkcji Wi-Fi na urządzeniu.
- **Tethering Wi-Fi (tylko system Samsung KNOX)** — umożliwia korzystanie z funkcji tetheringu Wi-Fi na urządzeniu.

## <a name="kiosk"></a>Kiosk

Ustawienia kiosku dotyczą tylko urządzeń z rozwiązaniem Samsung KNOX Standard i odnoszą się wyłącznie do aplikacji zarządzanych za pomocą usługi Intune.

- **Wybierz zarządzaną aplikację** — wybierz jedną z poniższych opcji, aby dodać co najmniej jedną zarządzaną aplikację, którą można uruchomić, gdy urządzenie jest w trybie kiosku. Na tym urządzeniu nie można uruchamiać żadnych innych aplikacji.
    - **Dodaj aplikacje według nazwy pakietu**
    - **Dodaj aplikacje przez adres URL**
    - **Dodaj aplikacje zarządzane**.
- **Przycisk usypiania ekranu** — włącza lub wyłącza przycisk usypiania/budzenia ekranu na urządzeniu.
- **Przyciski regulacji głośności** — włącza lub wyłącza przyciski regulacji głośności na urządzeniu.


## <a name="next-steps"></a>Następne kroki

Nadal korzystając z instrukcji opisanych w temacie [Jak skonfigurować ustawienia ograniczeń urządzeń](device-restrictions-configure.md) utwórz, a następnie przypisz profil ograniczeń urządzenia.
