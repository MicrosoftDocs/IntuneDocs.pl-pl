---
title: "Ustawienia ograniczeń urządzenia z systemem Windows Phone 8.1 w usłudze Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje na temat ustawień usługi Intune służących do kontrolowania ustawień i funkcji urządzeń z systemem Windows Phone 8.1."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d42714-49ca-43b3-b080-2e67a4268198
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 175401f05b10e7c8fdece996403832490e102a98
ms.lasthandoff: 02/18/2017


---

# <a name="windows-phone-81-device-restriction-settings-in-microsoft-intune"></a>Ustawienia ograniczeń urządzenia z systemem Windows Phone 8.1 w usłudze Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Ogólne
-     **Zastosuj wszystkie ustawienia tylko do systemu Windows Phone 8.1** — to ustawienie można skonfigurować w portalu klasycznym usługi Intune. W witrynie Azure Portal tego ustawienia nie można zmienić. Jeśli ma ono wartość **Skonfigurowano**, wszystkie ustawienia zostaną zastosowane tylko do urządzeń z systemem Windows Phone 8.1. Jeśli ma ono na wartość **Nie skonfigurowano**, te ustawienia zostaną również zastosowane do urządzeń z systemem Windows 10 Mobile.
-     **Aparat fotograficzny** — umożliwia lub blokuje korzystanie z aparatu fotograficznego urządzenia.
-     **Kopiowanie i wklejanie** — umożliwia lub blokuje kopiowanie i wklejanie na urządzeniach.
-     **Magazyn wymienny** — umożliwia korzystanie z magazynu wymiennego (na przykład karty SD) na urządzeniu.
-     **Geolokalizacja** — umożliwia urządzeniu korzystanie z informacji o lokalizacji.
-     **Konto Microsoft** — umożliwia użytkownikowi łączenie konta Microsoft z urządzeniem lub blokuje tę możliwość.
-     **Przechwytywanie ekranu** — umożliwia użytkownikowi przechwytywanie zawartości ekranu w formie pliku obrazu.
-     **Przesyłanie danych diagnostycznych** — umożliwia urządzeniu przesyłanie danych diagnostycznych do firmy Microsoft.
-     **Niestandardowe synchronizowanie kont e-mail** — umożliwia urządzeniu łączenie się z kontami poczty e-mail innymi niż konto Microsoft.

## <a name="password"></a>Hasło
-     **Zastosuj wszystkie ustawienia tylko do systemu Windows Phone 8.1** — to ustawienie można skonfigurować w portalu klasycznym usługi Intune. W witrynie Azure Portal tego ustawienia nie można zmienić. Jeśli ma ono wartość **Skonfigurowano**, wszystkie ustawienia zostaną zastosowane tylko do urządzeń z systemem Windows Phone 8.1. Jeśli ma ono na wartość **Nie skonfigurowano**, te ustawienia zostaną również zastosowane do urządzeń z systemem Windows 10 Mobile.
-     **Wymagane jest hasło** — wymaga od użytkownika końcowego wprowadzenia hasła w celu uzyskania dostępu do urządzenia.
    -     **Wymagany typ hasła** — określa wymagany typ hasła, na przykład alfanumeryczne lub wyłącznie numeryczne.
    -     **Minimalna długość hasła** — określa minimalną wymaganą liczbę znaków w haśle.
    -     **Proste hasła** — określa, czy można używać prostych haseł, takich jak „0000” i „1234”.
    -     **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia** — określa, ile razy może zostać podane nieprawidłowe hasło, zanim zawartość urządzenia zostanie wyczyszczona.
    -     **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu** — określa, jak długo urządzenie musi pozostawać w stanie bezczynności, zanim ekran zostanie automatycznie zablokowany.
    -     **Wygaśnięcie hasła (dni)** — określa liczbę dni, po której należy zmienić hasło urządzenia.
    -     **Zapobiegaj ponownemu użyciu starych haseł** —określa liczbę poprzednio używanych haseł, które zostaną zapamiętane.
-     **Szyfrowanie** — wymaga szyfrowania danych na obsługiwanych urządzeniach przenośnych.

## <a name="app-store"></a>App Store
-     **Zastosuj wszystkie ustawienia tylko do systemu Windows Phone 8.1** — to ustawienie można skonfigurować w portalu klasycznym usługi Intune. W witrynie Azure Portal tego ustawienia nie można zmienić. Jeśli ma ono wartość **Skonfigurowano**, wszystkie ustawienia zostaną zastosowane tylko do urządzeń z systemem Windows Phone 8.1. Jeśli ma ono na wartość **Nie skonfigurowano**, te ustawienia zostaną również zastosowane do urządzeń z systemem Windows 10 Mobile.
-     **App Store** — umożliwia użytkownikom łączenie się ze sklepem z aplikacjami przy użyciu urządzenia.

## <a name="restricted-apps"></a>Aplikacje z ograniczeniami

-     **Zastosuj wszystkie ustawienia tylko do systemu Windows Phone 8.1** — to ustawienie można skonfigurować w portalu klasycznym usługi Intune. W witrynie Azure Portal tego ustawienia nie można zmienić. Jeśli ma ono wartość **Skonfigurowano**, wszystkie ustawienia zostaną zastosowane tylko do urządzeń z systemem Windows Phone 8.1. Jeśli ma ono na wartość **Nie skonfigurowano**, te ustawienia zostaną również zastosowane do urządzeń z systemem Windows 10 Mobile.

Na liście aplikacji z ograniczeniami można skonfigurować jedną z następujących list:

Lista **Zablokowane aplikacje** — lista aplikacji (niezarządzanych przez usługę Intune), których użytkownicy nie mogą instalować ani uruchamiać.
Lista **Dozwolone aplikacje** — lista aplikacji, które użytkownicy mogą instalować. Aplikacje zarządzane przez usługę Intune są automatycznie traktowane jako dozwolone.

Aby skonfigurować listę, kliknij przycisk **Dodaj**, a następnie wprowadź wybraną nazwę oraz opcjonalnie wydawcę aplikacji i adres URL aplikacji w sklepie z aplikacjami.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Jak określić adres URL aplikacji w sklepie

Aby określić adres URL aplikacji na liście aplikacji dozwolonych lub zablokowanych, użyj następującego formatu:

Na stronie [Sklep Windows Phone](https://www.microsoft.com/store/apps/windows-phone) wyszukaj aplikację, której chcesz użyć.

Otwórz stronę instalacji aplikacji i skopiuj adres URL do schowka. Możesz teraz użyć tego adresu URL na liście dozwolonych lub zablokowanych aplikacji.

Przykład: wyszukaj w sklepie aplikację Skype. Adres URL, którego użyjesz, to **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**.



### <a name="additional-options"></a>Opcje dodatkowe

Możesz również kliknąć przycisk **Importuj**, aby wypełnić listę danymi z pliku CSV w formacie <*adres url aplikacji*>, <*nazwa aplikacji*>, <*wydawca aplikacji*>, lub kliknąć przycisk **Eksportuj**, aby utworzyć plik CSV zawierający listę aplikacji z ograniczeniami w tym samym formacie.


## <a name="browser"></a>Przeglądarka
-     **Zastosuj wszystkie ustawienia tylko do systemu Windows Phone 8.1** — to ustawienie można skonfigurować w portalu klasycznym usługi Intune. W witrynie Azure Portal tego ustawienia nie można zmienić. Jeśli ma ono wartość **Skonfigurowano**, wszystkie ustawienia zostaną zastosowane tylko do urządzeń z systemem Windows Phone 8.1. Jeśli ma ono na wartość **Nie skonfigurowano**, te ustawienia zostaną również zastosowane do urządzeń z systemem Windows 10 Mobile.
-     **Przeglądarka sieci Web** — umożliwia lub blokuje korzystanie z wbudowanej przeglądarki sieci Web na urządzeniach.

## <a name="cellular-and-connectivity"></a>Sieć komórkowa i łączność
-     **Zastosuj wszystkie ustawienia tylko do systemu Windows Phone 8.1** — to ustawienie można skonfigurować w portalu klasycznym usługi Intune. W witrynie Azure Portal tego ustawienia nie można zmienić. Jeśli ma ono wartość **Skonfigurowano**, wszystkie ustawienia zostaną zastosowane tylko do urządzeń z systemem Windows Phone 8.1. Jeśli ma ono na wartość **Nie skonfigurowano**, te ustawienia zostaną również zastosowane do urządzeń z systemem Windows 10 Mobile.
-     **Wi-Fi** — włącza lub wyłącza funkcję obsługi sieci Wi-Fi na urządzeniu.
-     **Tethering Wi-Fi** — umożliwia korzystanie z funkcji udostępniania połączenia internetowego przez Wi-Fi na urządzeniu.
-     **Automatycznie łącz się z hotspotami Wi-Fi** — umożliwia automatyczne łączenie się przy użyciu urządzenia z bezpłatnymi hotspotami Wi-Fi oraz automatyczne akceptowanie wszelkich warunków użytkowania.
-     **Raportowanie informacji o hotspotach Wi-Fi** — umożliwia wysyłanie informacji dotyczących połączeń Wi-Fi, aby ułatwić użytkownikowi odnajdywanie pobliskich połączeń.
-     **NFC** — włącza lub wyłącza operacje korzystające z komunikacji zbliżeniowej na urządzeniach, które ją obsługują.
-     **Bluetooth** — włącza lub wyłącza funkcję Bluetooth na urządzeniu.

