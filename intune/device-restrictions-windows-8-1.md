---
title: Ustawienia ograniczeń urządzeń z systemem Windows 8.1 w usłudze Microsoft Intune
titleSuffix: ''
description: Dowiedz się więcej na temat ustawień usługi Intune służących do kontrolowania ustawień i funkcji na urządzeniach z systemem Windows 8.1.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 2e6d42edaa5cdef9a149f3232e1b150e0847e542
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52180633"
---
# <a name="microsoft-intune-windows-81-and-later-device-restriction-settings"></a>Ustawienia ograniczeń urządzeń z systemem Windows 8.1 lub nowszym w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W tym artykule opisano wszystkie ustawienia ograniczeń urządzeń, które można skonfigurować w usłudze Microsoft Intune dla urządzeń z systemem Windows 8.1 lub nowszym.


## <a name="general"></a>Ogólne

-   **Przesyłanie danych diagnostycznych** — umożliwia urządzeniu przesyłanie danych diagnostycznych do firmy Microsoft.
-   **Zapora** — wymaga włączenia Zapory systemu Windows.
-   **Kontrola konta użytkownika** — wymaga używania na urządzeniach usługi Kontrola konta użytkownika.

## <a name="password"></a>Hasło
-   **Wymagany typ hasła** — wymaga od użytkownika końcowego wprowadzenia hasła w celu uzyskania dostępu do urządzenia.
-   **Minimalna długość hasła** — określa minimalną wymaganą długość hasła (w znakach).
-   **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia** — powoduje wyczyszczenie urządzenia, jeśli podana liczba prób logowania zakończy się niepowodzeniem.
-   **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu** — określa liczbę minut, przez które urządzenie musi pozostawać w stanie bezczynności, zanim do jego odblokowania będzie wymagane hasło.
-   **Wygaśnięcie hasła (dni)** — określa liczbę dni, po której należy zmienić hasło urządzenia.
-   **Zapobiegaj ponownemu użyciu starych haseł** —określa, czy użytkownik może skonfigurować poprzednio używane hasła.
-   **Hasło obrazkowe i numer PIN** — umożliwia korzystanie z haseł obrazkowych i numerów PIN. Hasło obrazkowe umożliwia użytkownikowi logowanie za pomocą gestów na obrazie. Numer PIN umożliwia użytkownikowi szybkie logowanie za pomocą 4-cyfrowego kodu.
-   **Szyfrowanie** — wymaga szyfrowania plików na urządzeniu.<br>Aby wymusić szyfrowanie na urządzeniach z systemem Windows 8.1, trzeba zainstalować na wszystkich urządzeniach [aktualizację klienta MDM dla systemu Windows z grudnia 2014 r.](https://support.microsoft.com/kb/3013816) 
W przypadku włączenia tego ustawienia dla urządzeń z systemem Windows 8.1 wszyscy użytkownicy urządzeń muszą mieć konto Microsoft.
Aby szyfrowanie działało, urządzenie musi spełniać wymagania certyfikacji sprzętu [Microsoft InstantGo](https://blogs.windows.com/windowsexperience/2014/06/19/instantgo-a-better-way-to-sleep/#IBHULcTfI4PokO8X.97).
W przypadku wymuszania szyfrowania na urządzeniu klucz odzyskiwania jest dostępny tylko za pośrednictwem konta Microsoft użytkownika, do którego można uzyskać dostęp z konta usługi OneDrive. Nie można odzyskać tego klucza w imieniu użytkownika.     



## <a name="browser"></a>Przeglądarka
-   **Autowypełnianie** — umożliwia użytkownikom zmianę ustawień autouzupełniania w przeglądarce.
-   **Ostrzeżenia przed oszustwem** — włącza lub wyłącza wyświetlanie ostrzeżeń dotyczących potencjalnie oszukańczych witryn sieci Web.
-   **SmartScreen** — włącza lub wyłącza wyświetlanie ostrzeżeń dotyczących potencjalnie oszukańczych witryn sieci Web.
-   **JavaScript** — umożliwia uruchamianie skryptów (takich jak JavaScript) w przeglądarce.
-   **Wyskakujące okienka** — włącza lub wyłącza blokowanie wyskakujących okienek w przeglądarce.
-   **Wysyłaj nagłówki Nie śledź** — wysyła nagłówek Nie śledź do odwiedzanych witryn w przeglądarce Internet Explorer.
-   **Dodatki** — umożliwia użytkownikom dodawanie wtyczek do programu Internet Explorer.
-   **Przejście do witryny intranetowej po wpisaniu jednego słowa** —umożliwia przekierowanie programu Internet Explorer do witryny sieci Web za pomocą jednego słowa, np. Bing.
-   **Automatyczne wykrywanie witryny intranetowej** — ułatwia konfigurowanie zabezpieczeń witryn intranetowych w przeglądarce Internet Explorer.
-   **Poziom zabezpieczeń internetowych** — ustawia poziom zabezpieczeń przeglądarki Internet Explorer dla witryn internetowych.
-   **Poziom zabezpieczeń intranetowych** — ustawia poziom zabezpieczeń przeglądarki Internet Explorer dla witryn intranetowych.
-   **Poziom zabezpieczeń witryn zaufanych** — konfiguruje poziom zabezpieczeń strefy witryn zaufanych.
-   **Wysoki poziom zabezpieczeń dla witryn ograniczonych** — konfiguruje poziom zabezpieczeń strefy witryn ograniczonych.
-   **Dostęp do trybu przedsiębiorstwa w menu** — umożliwia użytkownikom dostęp do opcji menu trybu przedsiębiorstwa w programie Internet Explorer.
Jeśli to ustawienie jest wybrane, możesz również określić opcję **Lokalizacja raportu rejestrowania**, która zawiera adres URL do raportu przedstawiającego witryny sieci Web, dla których użytkownicy włączyli dostęp w trybie przedsiębiorstwa.
-   **Lokalizacja listy witryn trybu przedsiębiorstwa** — określa lokalizację listy witryn internetowych, które będą używać trybu przedsiębiorstwa, gdy będzie aktywny.

## <a name="cellular"></a>Komórkowe
-   **Roaming danych** — umożliwia roaming danych, gdy urządzenie korzysta z sieci komórkowej.

## <a name="cloud-and-storage"></a>Chmura i magazyn
-   **Adres URL folderów roboczych** — określa adres URL folderu roboczego, aby umożliwić synchronizację dokumentów między urządzeniami.
-   **Dostęp do aplikacji Poczta systemu Windows bez konta Microsoft** — umożliwia dostęp do aplikacji Poczta systemu Windows bez konta Microsoft.    
