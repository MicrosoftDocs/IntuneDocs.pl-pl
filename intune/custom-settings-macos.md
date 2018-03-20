---
title: "Ustawienia niestandardowe w usłudze Microsoft Intune dla urządzeń z systemem macOS"
titleSuffix: 
description: "Dowiedz się więcej na temat ustawień, których można używać w niestandardowym profilu systemu macOS."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5ccc9d48eb16ce155bbed2bbdf38793b8f3bdfda
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/08/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-macos"></a>Niestandardowe ustawienia urządzeń w usłudze Microsoft Intune dla urządzeń z systemem macOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Profil niestandardowy systemu macOS w usłudze Microsoft Intune umożliwia przypisywanie ustawień utworzonych przy użyciu [narzędzia Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) do urządzeń z systemem macOS. To narzędzie umożliwia tworzenie wielu ustawień do kontroli działania tych urządzeń oraz eksportowanie ich do profilu konfiguracji. Następnie można zaimportować ten profil konfiguracji do profilu niestandardowego systemu macOS w usłudze Intune i przypisać ustawienia użytkownikom oraz urządzeniom w swojej organizacji.

Ta funkcja umożliwia przypisywanie ustawień systemu macOS, których nie można skonfigurować przy użyciu innych typów profilów usługi Intune.


1. Aby rozpocząć pracę, postępuj zgodnie z instrukcjami w artykule [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) (Jak skonfigurować niestandardowe ustawienia urządzenia w usłudze Microsoft Intune).
2. W okienku **Niestandardowy profil konfiguracji** skonfiguruj każde z następujących ustawień:

- **Nazwa niestandardowego profilu konfiguracji** — podaj nazwę zasad, która jest wyświetlana na urządzeniu i w ramach stanu usługi Intune.
- **Plik profilu konfiguracji** — przejdź do profilu konfiguracji utworzonego przy użyciu programu Apple Configurator.
Upewnij się, że ustawienia wyeksportowane z programu Apple Configurator są zgodne z wersją systemu macOS na urządzeniach, do których są przypisywane niestandardowe zasady systemu macOS. Aby uzyskać informacje o sposobie postępowania w przypadku niezgodnych ustawień, wyszukaj dokumenty **Configuration Profile Reference** i **Mobile Device Management Protocol Reference** w witrynie sieci Web programu [Apple Developer](https://developer.apple.com/).

Zaimportowany plik jest wyświetlany w obszarze **Zawartość pliku** okienka.
