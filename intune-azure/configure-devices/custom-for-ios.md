---
title: "Ustawienia niestandardowe usługi Intune dla urządzeń z systemem iOS | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące ustawień, których można używać w niestandardowym profilu systemu iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6da8caa8-65c2-4f47-842f-9570dcb1ac22
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5ab494a3dd1e1bdea9703ab314574b192c5208ee
ms.openlocfilehash: cfccdbf34437c5ab23cefba5307c53c60573ddb0


---

# <a name="intune-custom-settings-for-ios-devices-in-intune-azure-preview"></a>Ustawienia niestandardowe usługi Intune dla urządzeń z systemem iOS w wersji zapoznawczej usługi Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Profil niestandardowy systemu iOS w usłudze Microsoft Intune umożliwia wdrażanie ustawień utworzonych przy użyciu [narzędzia Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) na urządzeniach z systemem iOS. To narzędzie umożliwia tworzenie wielu ustawień do kontroli działania tych urządzeń oraz eksportowanie ich do profilu konfiguracji. Następnie można zaimportować ten profil konfiguracji do profilu niestandardowego systemu iOS w usłudze Intune i przypisać ustawienia użytkownikom oraz urządzeniom w swojej organizacji.

Ta funkcja umożliwia wdrażanie ustawień systemu iOS, których nie można skonfigurować przy użyciu innych typów profilów usługi Intune.


1. Aby rozpocząć pracę, postępuj zgodnie z instrukcjami w artykule [How to configure custom device settings in Microsoft Intune](how-to-configure-custom-settings.md) (Jak skonfigurować niestandardowe ustawienia urządzenia w usłudze Microsoft Intune).
2. W bloku **Utwórz profil** określ następujące pozycje:

- **Nazwa niestandardowego profilu konfiguracji** — podaj nazwę zasad, która będzie wyświetlana na urządzeniu i w stanie usługi Intune.
- **Plik profilu konfiguracji** — przejdź do profilu konfiguracji utworzonego przy użyciu programu Apple Configurator.
Upewnij się, że ustawienia wyeksportowane z programu Apple Configurator są zgodne z wersją systemu iOS na urządzeniach, na których są wdrażane niestandardowe zasady systemu iOS. Aby uzyskać informacje o sposobie postępowania w przypadku niezgodnych ustawień, wyszukaj dokumenty **Configuration Profile Reference** i **Mobile Device Management Protocol Reference** w witrynie sieci Web programu [Apple Developer](https://developer.apple.com/).

Zaimportowany plik będzie wyświetlany w obszarze bloku **Zawartość pliku**.



<!--HONumber=Feb17_HO1-->


