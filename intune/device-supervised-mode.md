---
title: Włączanie trybu nadzorowanego dla systemu iOS przy użyciu usługi Microsoft Intune
titleSuffix: ''
description: Dowiedz się, jak włączyć tryb nadzorowany dla systemu iOS przy użyciu usługi Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8190814-07f0-42d8-9b3a-87c67dd2b7ed
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 09b94ad2109c41ad02e8da7267690c31ba296bae
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="turn-on-ios-supervised-mode"></a>Włączanie trybu nadzorowanego dla systemu iOS


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tryb nadzorowany systemu iOS firmy Apple zapewnia administratorom więcej opcji podczas zarządzania urządzeniami firmy Apple, co jest przydatne w przypadku urządzeń należących do firmy wdrożonych na dużą skalę. Na przykład można ograniczyć funkcję AirDrop lub uniemożliwić użytkownikom zmienianie nazwy urządzenia. Aby uzyskać listę ustawień, które wymagają trybu nadzorowanego, zobacz [ustawienia ograniczeń urządzeń z systemem iOS w usłudze Intune](device-restrictions-ios.md).

Usługa Intune obsługuje tryb nadzorowany w ramach [programu Device Enrollment Program (DEP)](device-enrollment-program-enroll-ios.md) firmy Apple.

Aby uzyskać listę kontrolek firmy Apple, które wymagają nadzoru, zobacz [dokumentację ustawień ładunku](http://help.apple.com/configurator/mac/2.4/#/cad5370d089) firmy Apple.

## <a name="turn-on-supervised-mode-during-enrollment"></a>Włączanie trybu nadzorowanego podczas rejestracji

W usłudze Intune możesz włączyć tryb nadzorowany dla urządzeń podczas [tworzenia profilu rejestracji firmy Apple w programie DEP](https://docs.microsoft.com/en-us/intune/device-enrollment-program-enroll-ios#create-an-apple-enrollment-profile). W obszarze **Ustawienia zarządzania urządzeniami**, zaznacz pole **Nadzorowane**.

## <a name="turn-on-supervised-mode-after-enrollment"></a>Włączanie trybu nadzorowanego po rejestracji

Po rejestracji jedynym sposobem włączenia trybu nadzorowanego jest podłączenie urządzenia z systemem iOS do komputera Mac i [użycie programu Apple Configurator](apple-configurator-enroll-ios.md) (który zresetuje urządzenie). Po rejestracji nie można skonfigurować urządzenia w trybie Nadzorowane w usłudze Intune.

## <a name="identify-a-supervised-device"></a>Identyfikowanie nadzorowanego urządzenia

Aby ustalić, czy urządzenie jest nadzorowane, sprawdź ekran blokady lub stronę **Informacje**:
- Na ekranie blokady urządzenia będzie wyświetlany tekst **Ten telefon iPhone jest zarządzany przez „nazwa firmy”.**
- Na stronie **Informacje** urządzenia będzie wyświetlany tekst **Ten telefon iPhone jest nadzorowany. „Nazwa firmy” może monitorować Twój ruch w Internecie i lokalizować to urządzenie”.**

## <a name="next-steps"></a>Następne kroki

Aby uzyskać inne opcje zarządzania urządzeniami, zobacz [Co to jest zarządzanie urządzeniami w usłudze Microsoft Intune?](device-management.md)
