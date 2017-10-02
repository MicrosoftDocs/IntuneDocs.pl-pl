---
title: "Ustawienia ograniczeń urządzenia z systemem macOS w usłudze Intune"
titlesuffix: Azure portal
description: "Informacje na temat ustawień usługi Intune służących do kontrolowania ustawień i funkcjonalności na urządzeniach z systemem macOS."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3129cbaf-96c2-4837-8907-ca87a605a496
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ee6a9428bd06a01676fd9ff92653bef26ca03ce4
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2017
---
# <a name="macos-device-restriction-settings-in-microsoft-intune"></a>Ustawienia ograniczeń urządzenia z systemem macOS w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ustawienia te umożliwiają zarządzanie urządzeniami z systemem macOS w profilu ograniczeń urządzenia.

## <a name="password"></a>Hasło
-   **Hasło** — wymaga od użytkownika końcowego wprowadzenia hasła w celu uzyskania dostępu do urządzenia.
    -   **Wymagany typ hasła** — określa, czy hasło może być wyłącznie numeryczne (zawierać tylko cyfry), czy też musi być alfanumeryczne (zawierać litery i cyfry). To ustawienie jest obsługiwane tylko w systemie Mac OS X w wersji 10.10.3 lub nowszej.
    -   **Liczba znaków innych niż alfanumeryczne w haśle** — określa liczbę znaków złożonych, którą musi zawierać hasło (od **0** do **4**).<br>Znak złożony to symbol taki jak **?**.
    -   **Minimalna długość hasła** — określa minimalną długość hasła, które musi skonfigurować użytkownik (od **4** do **16** znaków).
    -   **Proste hasła** — umożliwia korzystanie z prostych haseł, takich jak **0000** lub **1234**.
    -   **Maksymalna liczba minut po zablokowaniu ekranu, po których jest wymagane wprowadzenie hasła** — określa czas braku aktywności komputera, po upływie którego do jego odblokowania będzie wymagane hasło.
    -   **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu** — określa, jak długo komputer musi pozostawać w stanie bezczynności, zanim ekran zostanie zablokowany.
    -   **Wygaśnięcie hasła (dni)** — określa liczbę dni, po upływie których użytkownik musi zmienić hasło (od **1** do **255** dni).
    -   **Zapobiegaj ponownemu użyciu starych haseł** — określa liczbę poprzednio używanych haseł, których nie można użyć ponownie (od **1** do **24**).

## <a name="restricted-apps"></a>Aplikacje z ograniczeniami

Na liście aplikacji z ograniczeniami można skonfigurować jedną z następujących list:

Lista **Aplikacje zabronione** — lista aplikacji (niezarządzanych przez usługę Intune), których użytkownicy nie mogą instalować ani uruchamiać.
Lista **Zatwierdzone aplikacje** — lista aplikacji, które użytkownicy mogą instalować. Aby utrzymać zgodność, użytkownicy nie mogą instalować aplikacji, których nie ma na liście. Aplikacje zarządzane przez usługę Intune są automatycznie traktowane jako dozwolone.

Aby skonfigurować listę, kliknij przycisk **Dodaj**, a następnie wprowadź wybraną nazwę oraz opcjonalnie wydawcę aplikacji i identyfikator pakietu aplikacji (np. *com.apple.calculator*).

## <a name="domains"></a>Domains

### <a name="unmarked-email-domains"></a>Nieoznaczone domeny poczty e-mail

W polu **Adres URL domeny poczty e-mail** dodaj do listy co najmniej jeden adres URL. Gdy użytkownicy końcowi otrzymają wiadomość e-mail z domeny innej niż skonfigurowana, wiadomość e-mail zostanie oznaczona w aplikacji Mail dla systemu iOS jako niezaufana.

