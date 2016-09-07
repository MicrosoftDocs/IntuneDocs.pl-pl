---
title: Ustawienia zasad uaktualniania wersji systemu Windows | Microsoft Intune
description: "Dowiedz się, jak automatycznie uaktualniać urządzenia z systemem Windows 10 do najnowszej wersji za pomocą usługi Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8589866a-3f13-489b-a5cd-cee017d16d54
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4bed62ebe07d5470414183626b34e68dd91f2d01
ms.openlocfilehash: 17933e41a646f305f9fb765e790c0de36a5036ba


---

# Ustawienia zasad uaktualniania wersji systemu Windows w usłudze Microsoft Intune
**Zasady uaktualniania wersji** w usłudze Microsoft Intune umożliwiają automatyczne uaktualnianie urządzeń z uruchomioną jedną z następujących wersji systemu Windows 10 do nowszej wersji:
* Windows 10 Desktop
* Windows 10 Holographic

## Przed rozpoczęciem
Przed rozpoczęciem uaktualniania urządzeń do najnowszej wersji potrzebujesz jednego z następujących elementów:
* Klucza produktu umożliwiającego zainstalowanie nowej wersji systemu Windows na wszystkich docelowych urządzeniach zasad (w przypadku wersji Windows 10 Desktop). Można użyć kluczy aktywacji wielokrotnej (MAK) lub kluczy usługi serwera zarządzania kluczami (KMS)
**lub też** pliku licencji od firmy Microsoft, który zawiera informacje licencyjne umożliwiające zainstalowanie nowej wersji systemu Windows na wszystkich docelowych urządzeniach zasad (w przypadku wersji Windows 10 Mobile i Windows 10 Holographic).
* Docelowe urządzenia z systemem Windows 10 muszą być zarejestrowane w usłudze Microsoft Intune. Z zasad uaktualniania wersji nie można korzystać w przypadku komputerów z oprogramowaniem klienckim Intune.

## Ustawienia zasad uaktualniania wersji

|Nazwa ustawienia|Szczegóły|
|-|-|
|**Nazwa**|Podaj nazwę dla zasad uaktualniania wersji.|
|**Opis**|Opcjonalnie podaj opis zasad, który ułatwia ich identyfikację w konsoli usługi Intune.
|**Wersja, do której ma być uaktualniany system**|Z listy rozwijanej wybierz wersję systemu: Windows 10 Desktop, Windows 10 Holographic lub Windows 10 Mobile, do której mają zostać uaktualnione docelowe urządzenia.
|**Klucz produktu**|Podaj klucz produktu uzyskany od firmy Microsoft, który może być używany do uaktualnienia wszystkich docelowych urządzeń z systemem Windows 10 Desktop.<br>Po utworzeniu zasad zawierających klucz produktu nie można go edytować. Jest to spowodowane zasłonięciem klucza ze względów bezpieczeństwa. Aby zmienić klucz produktu, musisz wprowadzić ponownie cały klucz.
|**Plik licencji**|Wybierz pozycję **Przeglądaj**, aby znaleźć plik licencji uzyskany od firmy Microsoft zawierający informacje o licencji dla wersji Windows Holographic lub Windows 10 Mobile, do której chcesz uaktualnić docelowe urządzenia.

### Zobacz także
[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Aug16_HO4-->


