---
title: "Ustawienia niestandardowe usługi Intune dla urządzeń z systemem macOS | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące ustawień, których można używać w niestandardowym profilu systemu macOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 68100ea5-7d9b-4c0b-8df7-b9a24b2442c8
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5ab494a3dd1e1bdea9703ab314574b192c5208ee
ms.openlocfilehash: 113572430f0ef82c9a6fa533e3d6fc17b86119cb


---

# <a name="custom-settings-for-macos-devices-in-intune-azure-preview"></a>Ustawienia niestandardowe dla urządzeń z systemem macOS w wersji zapoznawczej usługi Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Profil niestandardowy systemu macOS w usłudze Microsoft Intune umożliwia wdrażanie ustawień utworzonych przy użyciu [narzędzia Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) na urządzeniach z systemem macOS. To narzędzie umożliwia tworzenie wielu ustawień do kontroli działania tych urządzeń oraz eksportowanie ich do profilu konfiguracji. Następnie można zaimportować ten profil konfiguracji do profilu niestandardowego systemu macOS w usłudze Intune i przypisać ustawienia użytkownikom oraz urządzeniom w swojej organizacji.

Ta funkcja umożliwia wdrażanie ustawień systemu macOS, których nie można skonfigurować przy użyciu innych typów profilów usługi Intune.


1. Aby rozpocząć pracę, postępuj zgodnie z instrukcjami w artykule [How to configure custom device settings in Microsoft Intune](how-to-configure-custom-settings.md) (Jak skonfigurować niestandardowe ustawienia urządzenia w usłudze Microsoft Intune).
2. W bloku **Utwórz profil** określ następujące pozycje:

- **Nazwa niestandardowego profilu konfiguracji** — podaj nazwę zasad, która będzie wyświetlana na urządzeniu i w stanie usługi Intune.
- **Plik profilu konfiguracji** — przejdź do profilu konfiguracji utworzonego przy użyciu programu Apple Configurator.
Upewnij się, że ustawienia wyeksportowane z programu Apple Configurator są zgodne z wersją systemu macOS na urządzeniach, na których są wdrażane niestandardowe zasady systemu macOS. Aby uzyskać informacje o sposobie postępowania w przypadku niezgodnych ustawień, wyszukaj dokumenty **Configuration Profile Reference** i **Mobile Device Management Protocol Reference** w witrynie sieci Web programu [Apple Developer](https://developer.apple.com/).

Zaimportowany plik będzie wyświetlany w obszarze bloku **Zawartość pliku**.



<!--HONumber=Feb17_HO1-->


