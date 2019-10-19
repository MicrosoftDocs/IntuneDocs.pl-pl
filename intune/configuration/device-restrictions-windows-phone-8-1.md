---
title: Ustawienia ograniczeń urządzeń z systemem Windows Phone 8.1 w usłudze Microsoft Intune
titleSuffix: ''
description: Dowiedz się więcej na temat ustawień usługi Intune służących do kontrolowania ustawień i funkcjonalności na urządzeniach z systemem Windows Phone 8.1.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: bc29a7a5026691371370b167a4445bfd70cc76bd
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72489806"
---
# <a name="microsoft-intune-windows-phone-81-device-restriction-settings"></a>Ustawienia ograniczeń urządzeń z systemem Windows Phone 8.1 w usłudze Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

W tym artykule opisano ustawienia ograniczeń urządzeń w usłudze Microsoft Intune, które można skonfigurować dla urządzeń z systemem Windows Phone 8.1.


## <a name="general"></a>Ogólne

- **Aparat fotograficzny** — umożliwia lub blokuje korzystanie z aparatu fotograficznego urządzenia.
- **Kopiowanie i wklejanie** — umożliwia lub blokuje kopiowanie i wklejanie na urządzeniach.
- **Magazyn wymienny** — umożliwia korzystanie z magazynu wymiennego (na przykład karty SD) na urządzeniu.
- **Geolokalizacja** — umożliwia urządzeniu korzystanie z informacji o lokalizacji.
- **Konto Microsoft** — umożliwia użytkownikowi łączenie konta Microsoft z urządzeniem lub blokuje tę możliwość.
- **Przechwytywanie ekranu** — umożliwia użytkownikowi przechwytywanie zawartości ekranu w formie pliku obrazu.
- **Przesyłanie danych diagnostycznych** — umożliwia urządzeniu przesyłanie danych diagnostycznych do firmy Microsoft.
- **Niestandardowe synchronizowanie kont e-mail** — umożliwia urządzeniu łączenie się z kontami poczty e-mail innymi niż konto Microsoft.

## <a name="password"></a>Hasło

- **Hasło** — wymaga od użytkownika końcowego wprowadzenia hasła w celu uzyskania dostępu do urządzenia.
  - **Wymagany typ hasła** — określa wymagany typ hasła, na przykład alfanumeryczne lub wyłącznie numeryczne.
  - **Minimalna długość hasła** — określa minimalną wymaganą liczbę znaków w haśle.
  - **Proste hasła** — określa, czy można używać prostych haseł, takich jak „0000” i „1234”.
  - **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia** — określa, ile razy może zostać podane nieprawidłowe hasło, zanim zawartość urządzenia zostanie wyczyszczona.
  - **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu** — określa, jak długo urządzenie musi pozostawać w stanie bezczynności, zanim ekran zostanie automatycznie zablokowany.
  - **Wygaśnięcie hasła (dni)** — określa liczbę dni, po której należy zmienić hasło urządzenia.
  - **Zapobiegaj ponownemu użyciu starych haseł** —określa liczbę poprzednio używanych haseł, które zostaną zapamiętane.
- **Szyfrowanie** — wymaga szyfrowania danych na obsługiwanych urządzeniach przenośnych.

## <a name="app-store"></a>App Store

- **App Store** — umożliwia użytkownikom łączenie się ze sklepem z aplikacjami przy użyciu urządzenia.

## <a name="restricted-apps"></a>Aplikacje z ograniczeniami

Na liście aplikacji z ograniczeniami można skonfigurować jedną z następujących list:

Lista **Zablokowane aplikacje** — lista aplikacji (niezarządzanych przez usługę Intune), których użytkownicy nie mogą instalować ani uruchamiać.
Lista **Dozwolone aplikacje** — lista aplikacji, które użytkownicy mogą instalować. Aplikacje zarządzane przez usługę Intune są automatycznie traktowane jako dozwolone.

Aby skonfigurować listę, kliknij przycisk **Dodaj**, a następnie wprowadź wybraną nazwę oraz opcjonalnie wydawcę aplikacji i adres URL aplikacji w sklepie z aplikacjami.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Jak określić adres URL aplikacji w sklepie

Aby określić adres URL aplikacji na liście aplikacji dozwolonych lub zablokowanych, użyj następującego formatu:

Na stronie [Sklep Windows Phone](https://www.microsoft.com/store/apps/windows-phone) wyszukaj aplikację, której chcesz użyć.

Otwórz stronę instalacji aplikacji i skopiuj adres URL do schowka. Możesz teraz użyć tego adresu URL na liście dozwolonych lub zablokowanych aplikacji.

Przykład: wyszukaj w sklepie aplikację Skype. Adres URL do użycia to `http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51`.



### <a name="additional-options"></a>Opcje dodatkowe

Możesz również kliknąć przycisk **Importuj**, aby wypełnić listę danymi z pliku CSV w formacie <*adres URL aplikacji*>, <*nazwa aplikacji*>, <*wydawca aplikacji*>, lub kliknąć przycisk **Eksportuj**, aby utworzyć plik CSV zawierający listę aplikacji z ograniczeniami w tym samym formacie.


## <a name="browser"></a>Przeglądarka

- **Przeglądarka sieci Web** — umożliwia lub blokuje korzystanie z wbudowanej przeglądarki sieci Web na urządzeniach.

## <a name="cellular-and-connectivity"></a>Sieć komórkowa i łączność

- **Wi-Fi** — włącza lub wyłącza funkcję obsługi sieci Wi-Fi na urządzeniu.
- **Tethering Wi-Fi** — umożliwia korzystanie z funkcji udostępniania połączenia internetowego przez Wi-Fi na urządzeniu.
- **Automatycznie łącz się z hotspotami Wi-Fi** — umożliwia automatyczne łączenie się przy użyciu urządzenia z bezpłatnymi hotspotami Wi-Fi oraz automatyczne akceptowanie wszelkich warunków użytkowania.
- **Raportowanie informacji o hotspotach Wi-Fi** — umożliwia wysyłanie informacji dotyczących połączeń Wi-Fi, aby ułatwić użytkownikowi odnajdywanie pobliskich połączeń.
- **NFC** — włącza lub wyłącza operacje korzystające z komunikacji zbliżeniowej na urządzeniach, które ją obsługują.
- **Bluetooth** — włącza lub wyłącza funkcję Bluetooth na urządzeniu.
