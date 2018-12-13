---
title: Ustawienia ograniczeń urządzeń z systemem macOS w usłudze Microsoft Intune
titlesuffix: ''
description: Informacje na temat ustawień usługi Intune służących do kontrolowania ustawień i funkcji na urządzeniach z systemem macOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 0a2a096bfb4b5fafd895425a775abc13afc643e2
ms.sourcegitcommit: ecd6aebe50b1440a282dfdda771e37fbb8750d42
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/01/2018
ms.locfileid: "52728540"
---
# <a name="microsoft-intune-macos-device-restriction-settings"></a>Ustawienia ograniczeń urządzeń z systemem macOS w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W tym artykule opisano ustawienia ograniczeń urządzeń, które można skonfigurować dla urządzeń z systemem macOS.

## <a name="password"></a>Hasło
- **Hasło** — wymaga od użytkownika końcowego wprowadzenia hasła w celu uzyskania dostępu do urządzenia.
  - **Wymagany typ hasła** — określa, czy hasło może być wyłącznie numeryczne (zawierać tylko cyfry), czy też musi być alfanumeryczne (zawierać litery i cyfry). To ustawienie jest obsługiwane tylko w systemie Mac OS X w wersji 10.10.3 lub nowszej.
  - **Liczba znaków innych niż alfanumeryczne w haśle** — określa liczbę znaków złożonych, którą musi zawierać hasło (od **0** do **4**).<br>Znak złożony to symbol, na przykład „**?**”.
  - **Minimalna długość hasła** — określa minimalną długość hasła, które musi skonfigurować użytkownik (od **4** do **16** znaków).
  - **Proste hasła** — umożliwia korzystanie z prostych haseł, takich jak **0000** lub **1234**.
  - **Maksymalna liczba minut po zablokowaniu ekranu, po których jest wymagane wprowadzenie hasła** — określa czas braku aktywności komputera, po upływie którego do jego odblokowania będzie wymagane hasło.
  - **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu** — określa, jak długo komputer musi pozostawać w stanie bezczynności, zanim ekran zostanie zablokowany.
  - **Wygaśnięcie hasła (dni)** — określa liczbę dni, po upływie których użytkownik musi zmienić hasło (od **1** do **255** dni).
  - **Zapobiegaj ponownemu użyciu starych haseł** — określa liczbę poprzednio używanych haseł, których nie można użyć ponownie (od **1** do **24**).

- **Blokuj automatyczne wypełnianie haseł**: wybierz pozycję **Blokuj**, aby uniemożliwić użycie funkcji automatycznego wypełniania haseł w systemie macOS. Wybranie pozycji **Blokuj** ma również następujące skutki:

  - Użytkownicy nie są monitowani o użycie zapisanego hasła w przeglądarce Safari ani innych aplikacjach.
  - Automatyczne silne hasła są wyłączone i silne hasła nie są zalecane dla użytkowników.

  Pozycja **Nieskonfigurowane** zezwala na te funkcje.

- **Blokuj zbliżeniowe żądania haseł**: wybierz pozycję **Blokuj**, aby urządzenie użytkownika nie żądało haseł od urządzeń znajdujących się w pobliżu. Pozycja **Nieskonfigurowane** zezwala na te żądania haseł.

- **Blokowanie udostępniania haseł**: pozycja **Blokuj** uniemożliwia udostępnianie haseł między urządzeniami przy użyciu funkcji AirDrop. Pozycja **Nieskonfigurowane** umożliwia udostępnianie haseł.


## <a name="restricted-apps"></a>Aplikacje z ograniczeniami

Na liście aplikacji z ograniczeniami można skonfigurować jedną z następujących list:

- Lista **Aplikacje zabronione** — lista aplikacji (niezarządzanych przez usługę Intune), których użytkownicy nie mogą instalować ani uruchamiać. Nie można zapobiec zainstalowaniu zabronionej aplikacji przez użytkowników, lecz jeśli to zrobią, ten fakt zostanie Tobie zgłoszony.
- Lista **Zatwierdzone aplikacje** — lista aplikacji, które użytkownicy mogą instalować. Użytkownicy nie mogą instalować aplikacji, których nie ma na liście. Aplikacje zarządzane przez usługę Intune są automatycznie traktowane jako dozwolone. Nie można zapobiec zainstalowaniu przez użytkowników aplikacji spoza listy aplikacji zatwierdzonych, lecz jeśli to zrobią, ten fakt zostanie Ci zgłoszony.

Aby skonfigurować listę, kliknij przycisk **Dodaj**, a następnie wprowadź wybraną nazwę oraz opcjonalnie wydawcę aplikacji i identyfikator pakietu aplikacji (np. *com.apple.calculator*).

## <a name="domains"></a>Domains

### <a name="unmarked-email-domains"></a>Nieoznaczone domeny poczty e-mail

W polu **Adres URL domeny poczty e-mail** dodaj do listy co najmniej jeden adres URL. Gdy użytkownicy otrzymają wiadomość e-mail z domeny innej niż skonfigurowana, wiadomość e-mail zostanie oznaczona w aplikacji Mail dla systemu MacOS jako niezaufana.

