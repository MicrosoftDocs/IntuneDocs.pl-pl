---
title: Ustawienia niestandardowe w usłudze Microsoft Intune dla urządzeń z systemem iOS
titleSuffix: ''
description: Informacje dotyczące ustawień, których można używać w niestandardowym profilu systemu iOS w usłudze Microsoft Intune.
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
ms.custom: intune-azure
ms.openlocfilehash: e0ae4e757264465043ee6992033710c5a81d7157
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
ms.locfileid: "31831304"
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-ios"></a>Niestandardowe ustawienia urządzeń w usłudze Microsoft Intune dla urządzeń z systemem iOS

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Profil niestandardowy systemu iOS w usłudze Microsoft Intune umożliwia przypisywanie ustawień utworzonych przy użyciu [narzędzia Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) do urządzeń z systemem iOS. To narzędzie umożliwia tworzenie wielu ustawień do kontroli działania tych urządzeń oraz eksportowanie ich do profilu konfiguracji. Następnie można zaimportować ten profil konfiguracji do profilu niestandardowego systemu iOS w usłudze Intune i przypisać ustawienia użytkownikom oraz urządzeniom w swojej organizacji.

Ta funkcja umożliwia przypisywanie ustawień systemu iOS, których nie można skonfigurować przy użyciu innych typów profilów usługi Intune.


1. Aby rozpocząć pracę, postępuj zgodnie z instrukcjami w artykule [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) (Jak skonfigurować niestandardowe ustawienia urządzenia w usłudze Microsoft Intune).
2. W okienku **Niestandardowy profil konfiguracji** skonfiguruj każde z następujących ustawień:

- **Nazwa niestandardowego profilu konfiguracji** — podaj nazwę zasad, która jest wyświetlana na urządzeniu i w ramach stanu usługi Intune.
- **Plik profilu konfiguracji** — przejdź do profilu konfiguracji utworzonego przy użyciu programu Apple Configurator.
Upewnij się, że ustawienia wyeksportowane z programu Apple Configurator są zgodne z wersją systemu iOS na urządzeniach, do których są przypisywane niestandardowe zasady systemu iOS. Aby uzyskać informacje o sposobie postępowania w przypadku niezgodnych ustawień, wyszukaj dokumenty **Configuration Profile Reference** i **Mobile Device Management Protocol Reference** w witrynie sieci Web programu [Apple Developer](https://developer.apple.com/).

Zaimportowany plik jest wyświetlany w obszarze **Zawartość pliku** okienka.
