---
title: Włączanie trybu nadzorowanego dla systemu iOS/iPadOS przy użyciu usługi Microsoft Intune
titleSuffix: ''
description: Dowiedz się, jak włączyć tryb nadzorowany dla systemu iOS/iPadOS przy użyciu usługi Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/15/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 8190814-07f0-42d8-9b3a-87c67dd2b7ed
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0d266dbc9fa72b1579e05e7798315e2e718a9797
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2020
ms.locfileid: "77413660"
---
# <a name="turn-on-iosipados-supervised-mode"></a>Włączanie trybu nadzorowanego dla systemu iOS/iPadOS


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Tryb nadzorowany systemu iOS/iPadOS firmy Apple zapewnia administratorom więcej opcji podczas zarządzania urządzeniami firmy Apple, co jest przydatne w przypadku urządzeń należących do firmy wdrożonych na dużą skalę. Na przykład można ograniczyć funkcję AirDrop lub uniemożliwić użytkownikom zmienianie nazwy urządzenia. Aby uzyskać listę ustawień, które wymagają trybu nadzorowanego, zobacz [ustawienia ograniczeń urządzeń z systemem iOS w usłudze Intune](../configuration/device-restrictions-ios.md).

Usługa Intune obsługuje tryb nadzorowany w ramach [programu Device Enrollment Program (DEP)](../enrollment/device-enrollment-program-enroll-ios.md) firmy Apple.

Aby uzyskać listę kontrolek firmy Apple, które wymagają nadzoru, zobacz [dokumentację ustawień ładunku](http://help.apple.com/configurator/mac/2.4/#/cad5370d089) firmy Apple.

## <a name="turn-on-supervised-mode-during-enrollment"></a>Włączanie trybu nadzorowanego podczas rejestracji

W [centrum administracyjnym programy Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) możesz włączyć tryb nadzorowany dla urządzeń podczas [tworzenia profilu rejestracji firmy Apple w programie DEP](../enrollment/device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile). W obszarze **Ustawienia zarządzania urządzeniami**, zaznacz pole **Nadzorowane**.

## <a name="turn-on-supervised-mode-after-enrollment"></a>Włączanie trybu nadzorowanego po rejestracji

Po rejestracji jedynym sposobem włączenia trybu nadzorowanego jest podłączenie urządzenia z systemem iOS/iPadOS do komputera Mac i [użycie programu Apple Configurator](../enrollment/apple-configurator-enroll-ios.md) (który zresetuje urządzenie). Po rejestracji nie można skonfigurować urządzenia w trybie Nadzorowane w usłudze Intune.

## <a name="identify-a-supervised-device"></a>Identyfikowanie nadzorowanego urządzenia

Aby ustalić, czy urządzenie jest nadzorowane, sprawdź ekran blokady lub stronę **Informacje**:
- Na ekranie blokady urządzenia będzie wyświetlany tekst **Ten telefon iPhone jest zarządzany przez „nazwa firmy”.**
- Na stronie **Informacje** urządzenia będzie wyświetlany tekst **Ten telefon iPhone jest nadzorowany. „Nazwa firmy” może monitorować Twój ruch w Internecie i lokalizować to urządzenie”.**

## <a name="next-steps"></a>Następne kroki

Aby uzyskać inne opcje zarządzania urządzeniami, zobacz [Co to jest zarządzanie urządzeniami w usłudze Microsoft Intune?](device-management.md)
