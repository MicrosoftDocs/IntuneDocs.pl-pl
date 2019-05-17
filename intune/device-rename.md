---
title: Zmienianie nazwy urządzenia z systemem Windows za pomocą usługi Microsoft Intune — Azure | Microsoft Docs
description: Zmienianie nazwy urządzenia z systemem Windows za pomocą usługi Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8dfdc3641d583fc045346034ee8543feff1e7cbf
ms.sourcegitcommit: 1144247aa7f042eb1b99d8fd8dd17b909eae38c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/28/2019
ms.locfileid: "59567104"
---
# <a name="rename-a-windows-device-in-intune"></a>Zmienianie nazwy urządzenia z systemem Windows w usłudze Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Akcja **Zmienianie nazwy urządzenia** pozwala zmienić nazwę należącego do firmy urządzenia z systemem Windows, które zostało zarejestrowane w usłudze Intune. Nazwa urządzenia jest zmieniana w usłudze Intune i na urządzeniu. 

Ta funkcja nie obsługuje obecnie zmiany nazw urządzeń z systemem Windows dołączonych hybrydowo do usługi Azure AD.

## <a name="rename-a-device"></a>Zmienianie nazwy urządzenia

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie z systemem Windows > **Więcej** > **Zmień nazwę urządzenia**.
4. W bloku **Zmienianie nazwy urządzenia** wpisz nową nazwę w polu tekstowym. Możesz użyć liter, cyfr i łączników. Nazwa musi zawierać co najmniej jedną literę lub łącznik.
5. Jeśli chcesz ponownie uruchomić urządzenie po zmianie jego nazwy, wybierz pozycję **Tak** obok pozycji **Uruchom ponownie po zmianie nazwy**.
6. Wybierz pozycję **Zmień nazwę**.



## <a name="next-steps"></a>Następne kroki

Aby wyświetlić stan akcji **Zmienianie nazwy** dotyczącej urządzenia, przejdź na stronę **Omówienie** urządzenia.
