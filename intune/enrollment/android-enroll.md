---
title: Rejestrowanie urządzeń z systemem Android w usłudze Intune
titleSuffix: Microsoft Intune
description: Informacje o sposobie rejestrowania urządzeń z systemem Android w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 7/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4a9de31ce7a08edcb7dddc6a65a061c1883021e4
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71723596"
---
# <a name="enroll-android-devices"></a>Rejestrowanie urządzeń z systemem Android

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Jako administrator usługi Intune możesz rejestrować urządzenia z systemem Android w następujący sposób:
- System Android Enterprise (oferuje zestaw opcji rejestracji, które zapewniają użytkownikom najbardziej aktualne i bezpieczne funkcje):
    - [**Android Enterprise — profil służbowy**](android-work-profile-enroll.md): Dla urządzeń osobistych z uprawnieniami dostępu do danych firmowych. Administratorzy mogą zarządzać kontami służbowymi, aplikacjami i danymi. Dane osobiste na urządzeniu są oddzielone od danych służbowych, a administratorzy nie kontrolują ustawień ani danych osobistych. 
    - [**Android Enterprise (dedykowane)**](android-kiosk-enroll.md): Dla urządzeń należących do firmy przeznaczonych do użytku w jednym celu, takim jak znakowanie cyfrowe, drukowanie biletów czy zarządzanie zapasami. Administratorzy ograniczają użycie urządzenia do zdefiniowanego zestawu aplikacji i linków internetowych. Uniemożliwia to również użytkownikom dodawanie innych aplikacji i wykonywanie innych akcji na urządzeniu.
    - [**Urządzenia w pełni zarządzane w rozwiązaniu Android Enterprise**](android-fully-managed-enroll.md): w przypadku urządzeń należących do firmy wykorzystywanych przez jednego użytkownika w celach wyłącznie służbowych, a nie osobistych. Administratorzy mogą zarządzać całym urządzeniem i wymuszać kontrolki zasad niedostępne dla profilów służbowych. 
- [**Administrator urządzeń z systemem Android**](android-enroll-device-administrator.md), w tym z systemem Samsung Knox Standard oraz [urządzeń Zebra](../configuration/android-zebra-mx-overview.md). 

## <a name="prerequisites"></a>Wymagania wstępne

Aby przygotować się do zarządzania urządzeniami przenośnymi, należy ustawić urząd zarządzania urządzeniami przenośnymi (MDM) na wartość **Microsoft Intune**. Instrukcje znajdują się w artykule [Set the MDM authority](../fundamentals/mdm-authority-set.md) (Ustawianie urzędu MDM). Element ten ustawia się tylko raz podczas pierwszej konfiguracji usługi Intune do zarządzania urządzeniami przenośnymi.

W przypadku urządzeń wyprodukowanych przez firmę Zebra Technologies może być konieczne przyznanie dodatkowych uprawnień aplikacji Portal firmy w zależności od możliwości określonego urządzenia. Więcej szczegółowych informacji zawiera temat [Rozszerzenia dla mobilności w urządzeniach Zebra](../configuration/android-zebra-mx-overview.md).

W przypadku urządzeń z systemem Samsung Knox Standard istnieje [więcej wymagań wstępnych](android-samsung-knox-mobile-enroll.md).

## <a name="next-steps"></a>Następne kroki

- [Set up Android Enterprise work profile enrollments](android-work-profile-enroll.md) (Konfigurowanie rejestracji profilów służbowych systemu Android Enterprise)
- [Set up Android Enterprise dedicated device enrollments](android-kiosk-enroll.md) (Konfigurowanie rejestracji dedykowanych urządzeń systemu Android Enterprise)
- [Set up Android Enterprise fully managed enrollments](android-fully-managed-enroll.md) (Konfigurowanie w pełni zarządzanych rejestracji systemu Android Enterprise)
- [Rejestracja administratora urządzeń z systemem Android](android-enroll-device-administrator.md)

