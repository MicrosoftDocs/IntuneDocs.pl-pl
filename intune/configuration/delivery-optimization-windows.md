---
title: Ustawienia optymalizacji dostarczania dla systemu Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Skonfiguruj sposób korzystania z optymalizacji dostarczania przez urządzenia z systemem Windows 10, którymi zarządzasz za pomocą usługi Intune. W usłudze Intune utwórz profil konfiguracji urządzenia na potrzeby instalowania aktualizacji z Internetu. Zobacz również, jak można zastąpić istniejące pierścienie aktualizacji profilem optymalizacji dostarczania.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/10/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: kerimh
ms.openlocfilehash: 9fb4aab6b02c6ad6a5d2f18ca9d15beafc12d58a
ms.sourcegitcommit: e1ff157f692983b49bdd6e20cc9d0f93c3b3733c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124813"
---
# <a name="delivery-optimization-settings-in-microsoft-intune"></a>Ustawienia optymalizacji dostarczania w usłudze Microsoft Intune

Za pomocą usługi Intune możesz użyć ustawień optymalizacji dostarczania dla urządzeń z systemem Windows 10, aby ograniczyć zużycie przepustowości podczas pobierania przez nie aplikacji i aktualizacji. Skonfiguruj optymalizację dostarczania w ramach profilów konfiguracji urządzenia.  

W tym artykule opisano sposób konfigurowania ustawień optymalizacji dostarczania jako części profilu konfiguracji urządzenia. Po utworzeniu profilu możesz go przypisać do urządzeń z systemem Windows 10 lub wdrożyć na nich. 

Aby wyświetlić listę ustawień optymalizacji dostarczania obsługiwanych przez usługę Intune, zobacz [Ustawienia optymalizacji dostarczania dla usługi Intune](../delivery-optimization-settings.md).  

Aby uzyskać informacje dotyczące optymalizacji dostarczania w systemie Windows 10, zobacz artykuł [Aktualizacje optymalizacji dostarczania](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) w dokumentacji systemu Windows.  

## <a name="create-the-profile"></a>Tworzenie profilu

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz pozycję **Urządzenia** > **Profile konfiguracji** > **Utwórz profil**.

3. Wprowadź następujące właściwości:

    - **Nazwa**: Wprowadź opisową nazwę nowego profilu.
    - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: Wybierz pozycję **Windows 10 i nowsze**.
    - **Typ profilu**: wybierz pozycję **Optymalizacja dostarczania**.

4. Wybierz pozycję **Ustawienia** > **Skonfiguruj** i zdefiniuj sposób pobierania aktualizacji i aplikacji. Aby uzyskać informacje na temat dostępnych ustawień, zobacz artykuł [Ustawienia optymalizacji dostarczania dla usługi Intune](../delivery-optimization-settings.md).

5. Po zakończeniu wybierz pozycję **OK** > **Utwórz**, aby zapisać zmiany.

Profil zostanie utworzony i wyświetlony na liście. Następnie [przypiszesz profil](device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).

<!-- ## Move existing update rings to delivery optimization

**Delivery optimization** settings replace **Software updates – Windows 10 Update Rings**. Your existing update rings can be easily changed to use the **Delivery optimization** settings. To maintain the same settings when you create a delivery optimization profile, use the same *Delivery optimization download mode* and then set the same settings as you already use. However, you can choose to reconfigure delivery optimization settings to take advantage of the full range of addition settings that the Delivery Optimization profile can manage. 
-->

## <a name="remove-delivery-optimization-from-windows-10-update-rings"></a>Usuwanie optymalizacji dostarczania z pierścieni aktualizacji systemu Windows 10

Optymalizacja dostarczania była wcześniej konfigurowana jako część pierścieni aktualizacji oprogramowania. Począwszy od lutego 2019, ustawienia optymalizacji dostarczania są konfigurowane jako część profilu konfiguracji urządzenia dotyczącego optymalizacji dostarczania, który obejmuje dodatkowe ustawienia mające wpływ nie tylko na dostarczanie aktualizacji oprogramowania do urządzeń. Jeśli nie zostało to jeszcze zrobione, usuń ustawienie optymalizacji dostarczania z pierścieni aktualizacji, określając wartość *Nie skonfigurowano*, a następnie użyj profilu optymalizacji dostarczania w celu zarządzania większym zakresem dostępnych opcji.

1. Utwórz profil konfiguracji urządzenia dotyczący optymalizacji dostarczania:

    1. W centrum administracyjnym programu Microsoft Endpoint Manager wybierz pozycję **Urządzenia** > **Profile konfiguracji** > **Utwórz profil**.
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

2. Przypisz ten nowy profil do tych samych urządzeń i użytkowników jako istniejący pierścień aktualizacji oprogramowania. Listę kroków można znaleźć w temacie [Przypisywanie profilu](device-profile-assign.md).

3. Usuń konfigurację istniejącego pierścienia oprogramowania:
    1. W centrum administracyjnym programu Microsoft Endpoint Manager przejdź do pozycji **Aktualizacje oprogramowania** > Pierścienie aktualizacji systemu Windows 10.
    2. Z listy wybierz pierścień aktualizacji.
    3. W obszarze ustawień ustaw **Tryb pobierania optymalizacji dostarczania** na wartość **Nieskonfigurowane**.
    4. **OK** > **Zapisz** zmiany.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).  
Wyświetl [ustawienia optymalizacji dostarczania](../delivery-optimization-settings.md) dla usługi Intune.
