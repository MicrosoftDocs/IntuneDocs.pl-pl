---
title: Zmienianie nazwy urządzenia za pomocą usługi Microsoft Intune — Azure | Microsoft Docs
description: Zmienianie nazwy urządzenia za pomocą usługi Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 35fae5ea1b3294772db4f4db51179892e08ed5d1
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728510"
---
# <a name="rename-a-device-in-intune"></a>Zmienianie nazwy urządzenia w usłudze Intune


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Akcja **Zmienianie nazwy urządzenia** pozwala zmienić nazwę urządzenia, które zostało zarejestrowane w usłudze Intune. Nazwa urządzenia jest zmieniana w usłudze Intune i na urządzeniu.

Można zmieniać nazwy następujących typów urządzeń:
- należących do firmy z systemem Windows 
- nadzorowanych z systemem iOS
- należących do firmy z systemem MacOS 10

Ta funkcja nie obsługuje obecnie zmiany nazw urządzeń z systemem Windows dołączonych hybrydowo do usługi Azure AD.

## <a name="rename-a-device"></a>Zmienianie nazwy urządzenia

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Wybierz kolejno pozycje **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Więcej** > **Zmień nazwę urządzenia**.
4. W bloku **Zmienianie nazwy urządzenia** wpisz nową nazwę w polu tekstowym. Możesz użyć liter, cyfr i łączników. Nazwa musi zawierać co najmniej jedną literę lub łącznik.
5. Jeśli chcesz ponownie uruchomić urządzenie po zmianie jego nazwy, wybierz pozycję **Tak** obok pozycji **Uruchom ponownie po zmianie nazwy**.
6. Wybierz pozycję **Zmień nazwę**.



## <a name="next-steps"></a>Następne kroki

Aby wyświetlić stan akcji **Zmienianie nazwy** dotyczącej urządzenia, przejdź na stronę **Omówienie** urządzenia.
