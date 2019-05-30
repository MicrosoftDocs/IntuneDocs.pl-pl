---
title: Ustawienia optymalizacji dostarczania dla systemu Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Skonfiguruj sposób korzystania z optymalizacji dostarczania przez urządzenia z systemem Windows 10, którymi zarządzasz za pomocą usługi Intune. W usłudze Intune utwórz profil konfiguracji urządzenia na potrzeby instalowania aktualizacji z Internetu. Zobacz również, jak można zastąpić istniejące pierścienie aktualizacji profilem optymalizacji dostarczania.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/12/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: kerimh
ms.openlocfilehash: d927c886bbb3f82c18d5873a86fc427d00d96337
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/23/2019
ms.locfileid: "66042634"
---
# <a name="delivery-optimization-settings-in-microsoft-intune"></a>Ustawienia optymalizacji dostarczania w usłudze Microsoft Intune

Za pomocą usługi Intune możesz użyć ustawień optymalizacji dostarczania dla urządzeń z systemem Windows 10, aby ograniczyć zużycie przepustowości podczas pobierania przez nie aplikacji i aktualizacji. Optymalizacja dostarczania jest skonfigurowana jako część profilów konfiguracji urządzenia.  

W tym artykule opisano sposób konfigurowania ustawień optymalizacji dostarczania jako części profilu konfiguracji urządzenia. Po utworzeniu profilu możesz go przypisać do urządzeń z systemem Windows 10 lub wdrożyć na nich. 

Aby uzyskać listę ustawień optymalizacji dostarczania obsługiwanych przez usługę Intune, zobacz artykuł [Ustawienia optymalizacji dostarczania dla usługi Intune](delivery-optimization-settings.md).  

Aby uzyskać informacje dotyczące optymalizacji dostarczania w systemie Windows 10, zobacz artykuł [Aktualizacje optymalizacji dostarczania](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) w dokumentacji systemu Windows.  


> [!NOTE]
> **Aktualizacje oprogramowania — pierścienie aktualizacji systemu Windows 10** są zastępowane przez ustawienia **optymalizacji dostarczania**. Istniejące pierścienie aktualizacji można zmienić, tak aby używać ustawień **optymalizacji dostarczania**. [Przenoszenie istniejących pierścieni aktualizacji do optymalizacji dostarczania](#move-existing-update-rings-to-delivery-optimization) (w tym artykule) 
## <a name="create-the-profile"></a>Tworzenie profilu

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, wpisz nazwę usługi **Intune** w filtrze, a następnie wybierz pozycję **Intune**.

2. Wybierz kolejno pozycje **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.

3. Wprowadź następujące właściwości:

    - **Nazwa**: Wprowadź opisową nazwę nowego profilu.
    - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: wybierz platformę:  

        - **Windows 10 lub nowszy**

    - **Typ profilu**: wybierz pozycję **Optymalizacja dostarczania**.
    - **Ustawienia**: Skonfiguruj ustawienia definiujące sposób pobierania aktualizacji i aplikacji. Aby uzyskać informacje na temat dostępnych ustawień, zobacz artykuł [Ustawienia optymalizacji dostarczania dla usługi Intune](delivery-optimization-settings.md).

4. Po zakończeniu wybierz pozycję **OK**  >  **Utwórz**, aby zapisać zmiany.

Profil zostanie utworzony i wyświetlony na liście. Następnie [przypiszesz profil](device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).

## <a name="move-existing-update-rings-to-delivery-optimization"></a>Przenoszenie istniejących pierścieni aktualizacji do optymalizacji dostarczania

Ustawienia **optymalizacji dostarczania** zastępują pozycję **Aktualizacje oprogramowania — pierścienie aktualizacji systemu Windows 10**. Istniejące pierścienie aktualizacji można łatwo zmienić, tak aby używać ustawień **optymalizacji dostarczania**. Aby zachować te same ustawienia po utworzeniu profilu optymalizacji dostarczania, użyj tego samego *trybu pobierania optymalizacji dostarczania* i podaj te same ustawienia co już używane. Jednak możesz też ponownie skonfigurować ustawienia optymalizacji dostarczania, aby wykorzystać pełny zakres dodatkowych ustawień, którymi można zarządzać za pomocą profilu optymalizacji dostarczania.

1. Utwórz profil konfiguracji optymalizacji dostarczania:

    1. W usłudze Intune wybierz kolejno pozycje **Konfiguracja urządzenia** > **Profile** > **Utwórz profil**.
    2. Wprowadź następujące właściwości:

        - **Nazwa**: Wprowadź opisową nazwę nowego profilu.
        - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
        - **Platforma**: Wybierz pozycję **Windows 10 i nowsze**.
        - **Typ profilu**: wybierz pozycję **Optymalizacja dostarczania**.
        - **Ustawienia**: Dla **trybu pobierania optymalizacji dostarczania** wybierz ten sam tryb co używany przez istniejący pierścień aktualizacji oprogramowania, chyba że chcesz zmienić ustawienia stosowane dla urządzeń. Dostępne opcje:
            - **Nieskonfigurowany**
            - **Tylko protokół HTTP, bez komunikacji równorzędnej**
            - **Protokół HTTP w połączeniu z komunikacją równorzędną za tym samym translatorem adresów sieciowych**
            - **Protokół HTTP w połączeniu z komunikacją równorzędną w grupie prywatnej**
            - **Protokół HTTP w połączeniu z internetową komunikacją równorzędną**
            - **Prosty tryb pobierania bez komunikacji równorzędnej**
            - **Tryb obejścia**
    3. Skonfiguruj dodatkowe ustawienia, którymi chcesz zarządzać.
1. Przypisz ten nowy profil do tych samych urządzeń i użytkowników jako istniejący pierścień aktualizacji oprogramowania. Listę kroków można znaleźć w temacie [Przypisywanie profilu](device-profile-assign.md).

3. Usuń konfigurację istniejącego pierścienia oprogramowania:
    1. W usłudze Intune przejdź do pozycji **Aktualizacje oprogramowania** > Pierścienie aktualizacji systemu Windows 10.
    2. Z listy wybierz pierścień aktualizacji.
    3. W obszarze ustawień ustaw **Tryb pobierania optymalizacji dostarczania** na wartość **Nieskonfigurowane**.
    4. **OK** > **Zapisz** zmiany.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).  
Wyświetl [ustawienia optymalizacji dostarczania](delivery-optimization-settings.md) dla usługi Intune.
