---
title: "Ustawienia niestandardowe dla urządzeń z systemem macOS w usłudze Intune"
titleSuffix: Intune on Azure
description: "Informacje dotyczące ustawień, których można używać w niestandardowym profilu systemu macOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 68100ea5-7d9b-4c0b-8df7-b9a24b2442c8
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 57c4ec3621ffaef5c1aaffd55c87baac91e50154
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="custom-settings-for-macos-devices-in-microsoft-intune"></a>Ustawienia niestandardowe dla urządzeń z systemem macOS w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Profil niestandardowy systemu macOS w usłudze Microsoft Intune umożliwia przypisywanie ustawień utworzonych przy użyciu [narzędzia Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) do urządzeń z systemem macOS. To narzędzie umożliwia tworzenie wielu ustawień do kontroli działania tych urządzeń oraz eksportowanie ich do profilu konfiguracji. Następnie można zaimportować ten profil konfiguracji do profilu niestandardowego systemu macOS w usłudze Intune i przypisać ustawienia użytkownikom oraz urządzeniom w swojej organizacji.

Ta funkcja umożliwia przypisywanie ustawień systemu macOS, których nie można skonfigurować przy użyciu innych typów profilów usługi Intune.


1. Aby rozpocząć pracę, postępuj zgodnie z instrukcjami w artykule [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) (Jak skonfigurować niestandardowe ustawienia urządzenia w usłudze Microsoft Intune).
2. W bloku **Utwórz profil** określ następujące pozycje:

- **Nazwa niestandardowego profilu konfiguracji** — podaj nazwę zasad, która będzie wyświetlana na urządzeniu i w stanie usługi Intune.
- **Plik profilu konfiguracji** — przejdź do profilu konfiguracji utworzonego przy użyciu programu Apple Configurator.
Upewnij się, że ustawienia wyeksportowane z programu Apple Configurator są zgodne z wersją systemu macOS na urządzeniach, do których są przypisywane niestandardowe zasady systemu macOS. Aby uzyskać informacje o sposobie postępowania w przypadku niezgodnych ustawień, wyszukaj dokumenty **Configuration Profile Reference** i **Mobile Device Management Protocol Reference** w witrynie sieci Web programu [Apple Developer](https://developer.apple.com/).

Zaimportowany plik będzie wyświetlany w obszarze bloku **Zawartość pliku**.
