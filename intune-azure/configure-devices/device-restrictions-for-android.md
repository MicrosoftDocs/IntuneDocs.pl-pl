---
title: "Ustawienia ograniczeń urządzenia w usłudze Intune dla systemu Android | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: informacje na temat ustawień usługi Intune służących do kontrolowania ustawień i funkcjonalności na urządzeniach z systemem Android."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: a003b2b16e05c2d071bb7dbaaf564e24d0cf5823
ms.lasthandoff: 02/16/2017


---

# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-microsoft-intune"></a>Ustawienia ograniczeń urządzenia z systemami Android i Samsung KNOX Standard w usłudze Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Ogólne
-     **Aparat fotograficzny** — umożliwia korzystanie z aparatu fotograficznego urządzenia.
-     **Kopiuj i wklej** — umożliwia używanie funkcji kopiowania i wklejania na urządzeniu.
-     **Udostępnianie schowka między aplikacjami** — umożliwia korzystanie ze schowka w celu kopiowania i wklejania między aplikacjami (tylko Samsung KNOX Standard).
-     **Przesyłanie danych diagnostycznych** — blokuje użytkownikowi funkcję przesyłania danych diagnostycznych z urządzenia.    
-     **Resetowanie do ustawień fabrycznych** — umożliwia użytkownikowi zresetowanie urządzenia do ustawień fabrycznych.
-     **Geolokalizacja** — umożliwia urządzeniu korzystanie z informacji o lokalizacji (tylko Samsung KNOX Standard).
-     **Wyłączanie** — umożliwia użytkownikowi wyłączanie urządzenia.<br>Jeśli to ustawienie jest wyłączone, ustawienie **Liczba nieudanych logowań przed wyczyszczeniem danych z urządzenia** na urządzeniach z systemem Samsung KNOX Standard nie działa.
-     **Przechwytywanie ekranu** — umożliwia użytkownikowi przechwytywanie zawartości ekranu w formie obrazu.
-     **Asystent głosowy** — umożliwia korzystanie z oprogramowania Asystenta głosowego na urządzeniu (tylko Samsung KNOX Standard).
-     **YouTube** — umożliwia korzystanie z aplikacji YouTube na urządzeniu (tylko Samsung KNOX Standard).

## <a name="password"></a>Hasło
-     **Wymagane jest hasło** — wymaga od użytkownika końcowego wprowadzenia hasła w celu uzyskania dostępu do urządzenia.
-     **Minimalna długość hasła** — określa minimalną długość hasła, które musi skonfigurować użytkownik (od 4 do 16 znaków).
-     **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu** — określa liczbę minut braku aktywności przed automatycznym zablokowaniem urządzenia.
-     **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia** — określa liczbę dopuszczalnych nieudanych logowań przed wyczyszczeniem zawartości urządzenia.
-     **Wygaśnięcie hasła (dni)** — określa liczbę dni, po której należy zmienić hasło urządzenia.
-     **Wymagany typ hasła** — określa wymagany poziom złożoności hasła oraz możliwość stosowania urządzeń biometrycznych.
-     **Zapobiegaj ponownemu używaniu poprzednich haseł** —nie dopuszcza do tego, by użytkownik końcowy utworzył hasło, które było wcześniej używane.
-     **Odblokowywanie za pomocą odcisku palca** — umożliwia korzystanie z odcisku palca do odblokowania obsługiwanych urządzeń.
-     **Blokada Smart Lock i inni agenci zaufania** — umożliwia sterowanie funkcją Smart Lock na niezgodnych urządzeniach z systemem Android (tylko Samsung KNOX Standard 5.0 lub nowszy). Ta funkcja telefonu, czasami znana jako funkcja agentów zaufania, umożliwia wyłączenie lub obejście hasła ekranu blokady urządzenia, jeśli urządzenie jest w zaufanej lokalizacji (np. gdy zostało podłączone do danego urządzenia Bluetooth lub znajduje się w pobliżu tagu NFC). Możesz użyć tego ustawienia, aby uniemożliwić użytkownikom konfigurowanie funkcji blokady inteligentnej.
-     **Szyfrowanie** — wymaga szyfrowania plików na urządzeniu.

## <a name="google-play-store"></a>Sklep Google Play

-     **Sklep Google Play** — umożliwia użytkownikowi dostęp do sklepu Google Play na urządzeniu (tylko Samsung KNOX Standard).

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
-     **Przeglądarka sieci Web** — określa, czy na urządzeniu można używać domyślnej przeglądarki sieci Web.
-     **Autowypełnianie** — umożliwia korzystanie z funkcji autowypełniania w przeglądarce sieci Web.
-     **Pliki cookie** — umożliwia używanie plików cookie przez przeglądarkę sieci Web urządzenia.
-     **JavaScript** — umożliwia przeglądarce sieci Web urządzenia uruchamianie skryptów Java.
-     **Wyskakujące okienka** — umożliwia blokowanie wyskakujących okienek w przeglądarce sieci Web.

## <a name="cloud-and-storage"></a>Chmura i magazyn
-     **Kopie zapasowe w usłudze Google** — umożliwia korzystanie z kopii zapasowych w usłudze Google.
-     **Automatyczna synchronizacja konta Google** — umożliwia automatyczną synchronizację ustawień konta Google.
-     **Magazyn wymienny** — umożliwia korzystanie z magazynu wymiennego, np. karty SD, przez urządzenie (tylko Samsung KNOX Standard).
-     **Szyfrowanie na kartach pamięci** — określa, czy karta pamięci urządzenia musi być szyfrowana.

## <a name="cellular-and-connectivity"></a>Sieć komórkowa i łączność
-     **Roaming danych** — umożliwia roaming danych, gdy urządzenie korzysta z sieci komórkowej (tylko Samsung KNOX Standard).
-     **Wiadomości SMS i MMS** — umożliwia korzystanie z wiadomości SMS i MMS na urządzeniu (tylko Samsung KNOX Standard).
-     **Wybieranie głosowe** — włącza lub wyłącza funkcję wybierania głosowego na urządzeniu (tylko Samsung KNOX Standard).
-     **Roaming połączeń głosowych** — umożliwia roaming połączeń głosowych, gdy urządzenie korzysta z sieci komórkowej (tylko Samsung KNOX Standard).
-     **Bluetooth** — umożliwia korzystanie z funkcji Bluetooth na urządzeniu (tylko Samsung KNOX Standard).
-     **NFC** — umożliwia wykonywanie operacji korzystających z komunikacji zbliżeniowej (NFC), jeśli urządzenie ją obsługuje (tylko Samsung KNOX Standard).
-     **Wi-Fi** — umożliwia korzystanie z funkcji Wi-Fi na urządzeniu (tylko Samsung KNOX Standard).
-     **Tethering Wi-Fi** — umożliwia korzystanie z funkcji tetheringu Wi-Fi na urządzeniu (tylko Samsung KNOX Standard).

## <a name="kiosk"></a>Kiosk
-     **Wybierz aplikację zarządzaną** — przejdź do odpowiedniej lokalizacji i wybierz aplikację zarządzaną, która może działać na urządzeniu w trybie kiosku (aplikacje określone jako link do sklepu nie są aktualnie obsługiwane). Na tym urządzeniu nie będzie można uruchamiać żadnych innych aplikacji.
-     **Przycisk usypiania ekranu** — włącza lub wyłącza przycisk usypiania/budzenia ekranu na urządzeniu.
-     **Przyciski regulacji głośności** — włącza lub wyłącza przyciski regulacji głośności na urządzeniu.

