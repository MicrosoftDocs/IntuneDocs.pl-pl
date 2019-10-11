---
title: Rejestrowanie urządzeń z profilem służbowym systemu Android Enterprise w usłudze Intune
titleSuffix: Microsoft Intune
description: Dowiedz się, jak rejestrować urządzenia z profilem służbowym systemu Android Enterprise w usłudze Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 5/13/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8c447b6b21021573d95a5ece3297e548f216b7a0
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71723531"
---
# <a name="set-up-enrollment-of-android-enterprise-work-profile-devices"></a>Konfigurowanie rejestracji urządzeń z profilem służbowym systemu Android Enterprise

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Usługa Intune ułatwia wdrażanie aplikacji i ustawień na urządzeniach z profilem służbowym systemu Android Enterprise, co zapewnia oddzielenie informacji osobistych od służbowych. Aby uzyskać szczegółowe informacje na temat rozwiązania Android Enterprise, zobacz [wymagania dotyczące rozwiązania Android Enterprise](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Aby skonfigurować zarządzanie profilami służbowymi systemu Android Enterprise, wykonaj następujące kroki:

1. [Połącz swoje konto dzierżawy usługi Intune z kontem rozwiązania Android Enterprise](connect-intune-android-enterprise.md).
2. Określ ustawienia rejestracji profilu służbowego systemu Android Enterprise. Profile służbowe systemu Android Enterprise są [obsługiwane tylko na niektórych urządzeniach z systemem Android](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012%20style=%22target=new_window%22). Każde urządzenie, które obsługuje profile służbowe systemu Android Enterprise, obsługuje także zarządzanie przez administratora urządzeń z systemem Android. Usługa Intune pozwala określić, jak w ramach [ograniczeń rejestracji](enrollment-restrictions-set.md) powinny być zarządzane urządzenia, które obsługują profile służbowe systemu Android Enterprise.
    - **Blokuj**:  Wszystkie urządzenia z systemem Android, w tym urządzenia obsługujące profile służbowe systemu Android Enterprise, zostaną zarejestrowane jako urządzenia administratora urządzeń z systemem Android, o ile rejestracja administratora urządzeń z systemem Android również nie została zablokowana. 
    - **Zezwalaj (ustawienie domyślne)** : wszystkie urządzenia, które obsługują profile służbowe systemu Android Enterprise, są rejestrowane jako urządzenia z profilami służbowymi systemu Android Enterprise. Wszystkie urządzenia z systemem Android, które nie obsługują profilów służbowych systemu Android Enterprise, zostaną zarejestrowane jako urządzenia administratora urządzeń z systemem Android, o ile rejestracja administratora urządzeń z systemem Android nie została zablokowana. 
> [!NOTE]
> Od lipca 2019 r. domyślnym ustawieniem dla nowych dzierżaw jest **Zezwalaj**. Wszystkie wcześniejsze dzierżawy nie będą miały żadnych zmian w ograniczeniach rejestracji i będą widzieć wszystkie zasady, które zostały ustawione w ograniczeniach rejestracji. W przypadku wcześniejszych dzierżaw, które nigdy nie miały żadnych zmian w ograniczeniach rejestracji, domyślnym ustawieniem dla profilów służbowych usługi Android Enterprise będzie nadal **Zablokuj**.

3. [Poinformuj użytkowników, jak mogą zarejestrować swoje urządzenia](/intune-user-help/create-a-work-profile-and-enroll-your-device-in-intune-android).  

Jeśli chcesz zarejestrować urządzenia przy użyciu profilów służbowych systemu Android Enterprise, ale zostały one już zarejestrowane za pomocą administratora urządzeń z systemem Android, należy najpierw wyrejestrować te urządzenia, a następnie ponownie je zarejestrować.
> [!NOTE]
> Jako administrator możesz to zrobić zdalnie, korzystając z funkcji **Wycofaj**. Tę funkcję można znaleźć w menu Akcje po wybraniu urządzenia z bloku **Wszystkie urządzenia**.

W przypadku rejestrowania urządzeń z profilami służbowymi systemu Android Enterprise za pomocą konta [menedżera rejestracji urządzeń](device-enrollment-manager-enroll.md) na jednym koncie można zarejestrować maksymalnie 10 urządzeń.

Aby uzyskać więcej informacji, zobacz artykuł [Data Intune sends to Google (Dane wysyłane przez usługę Intune do firmy Google)](../protect/data-intune-sends-to-google.md).

## <a name="next-steps-for-android-enterprise-work-profiles"></a>Kolejne kroki dotyczące profilów służbowych systemu Android Enterprise
- [Deploy Android Enterprise work profile apps](../apps/apps-add-android-for-work.md) (Wdrażanie aplikacji z profilami służbowymi systemu Android Enterprise)
- [Add Android Enterprise work profile configuration policies](../configuration/device-profiles.md) (Dodawanie zasad konfiguracji profilów służbowych systemu Android Enterprise)

## <a name="see-also"></a>Zobacz także

[Configuring and troubleshooting Android enterprise devices in Microsoft Intune](https://support.microsoft.com/help/4476974) (Konfigurowanie urządzeń z systemem Android Enterprise i rozwiązywanie problemów z nimi w usłudze Microsoft Intune)
