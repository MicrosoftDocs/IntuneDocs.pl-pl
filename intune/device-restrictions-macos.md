---
title: "Ustawienia ograniczeń urządzenia z systemem macOS w usłudze Intune"
titlesuffix: Azure portal
description: "Informacje na temat ustawień usługi Intune służących do kontrolowania ustawień i funkcjonalności na urządzeniach z systemem macOS."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 1/31/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a88cf11209726a622863339c3a6c117f7b83be1e
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2018
---
# <a name="macos-device-restriction-settings-in-microsoft-intune"></a>Ustawienia ograniczeń urządzenia z systemem macOS w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ustawienia te umożliwiają zarządzanie urządzeniami z systemem macOS w profilu ograniczeń urządzenia.

## <a name="password"></a>Hasło
-   **Hasło** — wymaga od użytkownika końcowego wprowadzenia hasła w celu uzyskania dostępu do urządzenia.
    -   **Wymagany typ hasła** — określa, czy hasło może być wyłącznie numeryczne (zawierać tylko cyfry), czy też musi być alfanumeryczne (zawierać litery i cyfry). To ustawienie jest obsługiwane tylko w systemie Mac OS X w wersji 10.10.3 lub nowszej.
    -   **Liczba znaków innych niż alfanumeryczne w haśle** — określa liczbę znaków złożonych, którą musi zawierać hasło (od **0** do **4**).<br>Znak złożony to symbol, na przykład „**?**”.
    -   **Minimalna długość hasła** — określa minimalną długość hasła, które musi skonfigurować użytkownik (od **4** do **16** znaków).
    -   **Proste hasła** — umożliwia korzystanie z prostych haseł, takich jak **0000** lub **1234**.
    -   **Maksymalna liczba minut po zablokowaniu ekranu, po których jest wymagane wprowadzenie hasła** — określa czas braku aktywności komputera, po upływie którego do jego odblokowania będzie wymagane hasło.
    -   **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu** — określa, jak długo komputer musi pozostawać w stanie bezczynności, zanim ekran zostanie zablokowany.
    -   **Wygaśnięcie hasła (dni)** — określa liczbę dni, po upływie których użytkownik musi zmienić hasło (od **1** do **255** dni).
    -   **Zapobiegaj ponownemu użyciu starych haseł** — określa liczbę poprzednio używanych haseł, których nie można użyć ponownie (od **1** do **24**).

## <a name="restricted-apps"></a>Aplikacje z ograniczeniami

Na liście aplikacji z ograniczeniami można skonfigurować jedną z następujących list:

- Lista **Aplikacje zabronione** — lista aplikacji (niezarządzanych przez usługę Intune), których użytkownicy nie mogą instalować ani uruchamiać. Nie można zapobiec zainstalowaniu zabronionej aplikacji przez użytkowników, lecz jeśli to zrobią, ten fakt zostanie Tobie zgłoszony.
- Lista **Zatwierdzone aplikacje** — lista aplikacji, które użytkownicy mogą instalować. Użytkownicy nie mogą instalować aplikacji, których nie ma na liście. Aplikacje zarządzane przez usługę Intune są automatycznie traktowane jako dozwolone. Nie można zapobiec zainstalowaniu przez użytkowników aplikacji spoza listy aplikacji zatwierdzonych, lecz jeśli to zrobią, ten fakt zostanie Ci zgłoszony.

Aby skonfigurować listę, kliknij przycisk **Dodaj**, a następnie wprowadź wybraną nazwę oraz opcjonalnie wydawcę aplikacji i identyfikator pakietu aplikacji (np. *com.apple.calculator*).

## <a name="domains"></a>Domains

### <a name="unmarked-email-domains"></a>Nieoznaczone domeny poczty e-mail

W polu **Adres URL domeny poczty e-mail** dodaj do listy co najmniej jeden adres URL. Gdy użytkownicy końcowi otrzymają wiadomość e-mail z domeny innej niż skonfigurowana, wiadomość e-mail zostanie oznaczona w aplikacji Mail dla systemu iOS jako niezaufana.

