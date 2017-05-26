---
title: Ustawienia zasad uaktualniania wersji systemu Windows | Microsoft Docs
description: "Dowiedz się, jak automatycznie uaktualniać urządzenia z systemem Windows 10 do innej wersji za pomocą usługi Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8589866a-3f13-489b-a5cd-cee017d16d54
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 66be6716df38d868e8247131b49ffb50fc48e60b
ms.openlocfilehash: 81061f032ef2079695f45e54e99cbb6479252bed
ms.lasthandoff: 04/15/2017


---

# <a name="windows-edition-upgrade-policy-settings-in-microsoft-intune"></a>Ustawienia zasad uaktualniania wersji systemu Windows w usłudze Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

**Zasady uaktualniania wersji** w usłudze Microsoft Intune umożliwiają automatyczne uaktualnianie urządzeń z uruchomioną jedną z następujących wersji systemu Windows 10 do innej wersji:
* Windows 10 Desktop
* Windows 10 Holographic
* Windows 10 Mobile

Obsługiwane są następujące ścieżki uaktualniania:
- Z systemu Windows 10 Pro do systemu Windows 10 Enterprise
- Z systemu Windows 10 Home do systemu Windows 10 Education
- Z systemu Windows 10 Mobile do systemu Windows 10 Mobile Enterprise
- Z systemu Windows 10 Holographic Pro do systemu Windows 10 Holographic Enterprise

## <a name="before-you-start"></a>Przed rozpoczęciem
Przed rozpoczęciem uaktualniania urządzeń do najnowszej wersji potrzebujesz jednego z następujących elementów:
* Klucza produktu umożliwiającego zainstalowanie nowej wersji systemu Windows na wszystkich docelowych urządzeniach zasad (w przypadku wersji Windows 10 Desktop). Można użyć kluczy aktywacji wielokrotnej (MAK) lub kluczy usługi serwera zarządzania kluczami (KMS)
**lub też** pliku licencji od firmy Microsoft, który zawiera informacje licencyjne umożliwiające zainstalowanie nowej wersji systemu Windows na wszystkich docelowych urządzeniach zasad (w przypadku wersji Windows 10 Mobile i Windows 10 Holographic).
* Docelowe urządzenia z systemem Windows 10 muszą być zarejestrowane w usłudze Microsoft Intune. Z zasad uaktualniania wersji nie można korzystać w przypadku komputerów z oprogramowaniem klienckim Intune.

## <a name="edition-upgrade-policy-settings"></a>Ustawienia zasad uaktualniania wersji

|Nazwa ustawienia|Szczegóły|
|-|-|
|**Nazwa**|Podaj nazwę dla zasad uaktualniania wersji.|
|**Opis**|Opcjonalnie podaj opis zasad, który ułatwia ich identyfikację w konsoli usługi Intune.
|**Wersja, do której ma być uaktualniany system**|Z listy rozwijanej wybierz wersję systemu: Windows 10 Desktop, Windows 10 Holographic lub Windows 10 Mobile, do której mają zostać uaktualnione docelowe urządzenia.
|**Klucz produktu**|Podaj klucz produktu uzyskany od firmy Microsoft, który może być używany do uaktualnienia wszystkich docelowych urządzeń z systemem Windows 10 Desktop.<br>Po utworzeniu zasad zawierających klucz produktu nie można go edytować. Jest to spowodowane zasłonięciem klucza ze względów bezpieczeństwa. Aby zmienić klucz produktu, musisz wprowadzić ponownie cały klucz.
|**Plik licencji**|Wybierz pozycję **Przeglądaj**, aby znaleźć plik licencji uzyskany od firmy Microsoft zawierający informacje o licencji dla wersji Windows Holographic lub Windows 10 Mobile, do której chcesz uaktualnić docelowe urządzenia.

### <a name="see-also"></a>Zobacz także
[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
