---
title: "Ustawienia ograniczeń urządzenia z systemem macOS w usłudze Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje na temat ustawień usługi Intune służących do kontrolowania ustawień i funkcji urządzeń z systemem macOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3129cbaf-96c2-4837-8907-ca87a605a496
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: e6b308547331e20a8373aca56f9a0781dcd210a2
ms.lasthandoff: 02/18/2017


---

# <a name="macos-device-restriction-settings-in-microsoft-intune"></a>Ustawienia ograniczeń urządzenia z systemem macOS w usłudze Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="password"></a>Hasło
-     **Wymagane jest hasło** — wymaga od użytkownika końcowego wprowadzenia hasła w celu uzyskania dostępu do urządzenia.
    -     **Wymagany typ hasła** — określa, czy hasło może być wyłącznie numeryczne (zawierać tylko cyfry), czy też musi być alfanumeryczne (zawierać litery i cyfry). To ustawienie jest obsługiwane tylko w systemie Mac OS X w wersji 10.10.3 lub nowszej.
    -     **Liczba znaków innych niż alfanumeryczne w haśle** — określa liczbę znaków złożonych, którą musi zawierać hasło (od **0** do **4**).<br>Znak złożony to symbol, taki jak **?**.
    -     **Minimalna długość hasła** — określa minimalną długość hasła, które musi skonfigurować użytkownik (od **4** do **16** znaków).
    -     **Proste hasła** — umożliwia korzystanie z prostych haseł, takich jak **0000** lub **1234**.
    -     **Maksymalna liczba minut po zablokowaniu ekranu, po których jest wymagane wprowadzenie hasła** — określa czas braku aktywności komputera, po upływie którego do jego odblokowania będzie wymagane hasło.
    -     **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu** — określa, jak długo komputer musi pozostawać w stanie bezczynności, zanim ekran zostanie zablokowany.
    -     **Wygaśnięcie hasła (dni)** — określa liczbę dni, po upływie których użytkownik musi zmienić hasło (od **1** do **255** dni).
    -     **Zapobiegaj ponownemu użyciu starych haseł** — określa liczbę poprzednio używanych haseł, których nie można użyć ponownie (od **1** do **24**).

## <a name="restricted-apps"></a>Aplikacje z ograniczeniami

Na liście aplikacji z ograniczeniami można skonfigurować jedną z następujących list:

Lista **Aplikacje zabronione** — lista aplikacji (niezarządzanych przez usługę Intune), których użytkownicy nie mogą instalować ani uruchamiać.
Lista **Zatwierdzone aplikacje** — lista aplikacji, które użytkownicy mogą instalować. Aby utrzymać zgodność, użytkownicy nie mogą instalować aplikacji, których nie ma na liście. Aplikacje zarządzane przez usługę Intune są automatycznie traktowane jako dozwolone.

Aby skonfigurować listę, kliknij przycisk **Dodaj**, a następnie wprowadź wybraną nazwę oraz opcjonalnie wydawcę aplikacji i identyfikator pakietu aplikacji (np. *com.apple.calculator*).



