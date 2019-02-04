---
title: Ustawienia optymalizacji dostarczania dla systemu Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Skonfiguruj sposób dostarczania aktualizacji oprogramowania do urządzeń przy użyciu usług optymalizacji dostarczania w chmurze, które są dostępne na urządzeniach z systemem Windows 10 i nowszych. W usłudze Intune utwórz profil konfiguracji urządzenia na potrzeby instalowania aktualizacji z Internetu. Zobacz również, jak można zastąpić istniejące pierścienie aktualizacji profilem optymalizacji dostarczania.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0a59cab5f709897e064b315193b292cb46dc2f2e
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54831551"
---
# <a name="windows-10-and-newer-delivery-optimization-settings-in-microsoft-intune"></a>Ustawienia optymalizacji dostarczania w systemie Windows 10 (i nowszych) w usłudze Microsoft Intune

> [!NOTE]
> **Aktualizacje oprogramowania — pierścienie aktualizacji systemu Windows 10** są zastępowane przez ustawienia **optymalizacji dostarczania**. Istniejące pierścienie aktualizacji można zmienić, tak aby używać ustawień **optymalizacji dostarczania**. Listę czynności można znaleźć w sekcji [Przenoszenie istniejących pierścieni aktualizacji do optymalizacji dostarczania](#move-existing-update-rings-to-delivery-optimization) (w tym artykule). 


Ta funkcja ma zastosowanie do następującej platformy:

- System Windows 10 lub nowszy

W tym artykule wymieniono i opisano wszystkie ustawienia optymalizacji dostarczania, które można skonfigurować dla urządzeń z systemem Windows 10. Te ustawienia są dodawane do profilu konfiguracji urządzenia, a następnie przypisywane do urządzeń lub wdrażane na nich przy użyciu usługi Microsoft Intune.

[Aktualizacje optymalizacji dostarczania](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) to świetny zasób, z którego dowiesz się więcej na temat optymalizacji dostarczania w systemie Windows 10.

## <a name="create-the-profile"></a>Tworzenie profilu

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, wpisz nazwę usługi **Intune** w filtrze, a następnie wybierz pozycję **Intune**.

2. Wybierz kolejno pozycje **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.

3. Wprowadź następujące właściwości:

    - **Nazwa**: Wprowadź opisową nazwę nowego profilu.
    - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: wybierz platformę:  

        - **Windows 10 lub nowszy**

    - **Typ profilu**: wybierz pozycję **Optymalizacja dostarczania**.
    - **Ustawienia**: wybierz sposób pobierania aktualizacji. Dostępne opcje: 

        - **Nieskonfigurowane**: użytkownicy końcowi aktualizują swoje urządzenia przy użyciu własnych metod, czyli na przykład stosując ustawienia **aktualizacji systemu Windows** lub **optymalizacji dostarczania** dostępne w systemie operacyjnym.
        - **Tylko protokół HTTP, bez komunikacji równorzędnej**: pobieranie aktualizacji tylko z Internetu. Aktualizacje nie są pobierane z innych komputerów w sieci (tzw. komunikacja równorzędnej lub sieć równorzędna).
        - **Protokół HTTP w połączeniu z komunikacją równorzędną za tym samym translatorem adresów sieciowych**: pobieranie aktualizacji z Internetu i innych komputerów w sieci. 
        - **Protokół HTTP w połączeniu z komunikacją równorzędną w grupie prywatnej**: Komunikacja równorzędna występuje na urządzeniach w tej samej lokacji usługi Active Directory (jeśli istnieje) lub w tej samej domenie. Po wybraniu tej opcji następuje przecięcie adresów IP translatora adresów sieciowych w ramach komunikacji równorzędnej.
        - **Protokół HTTP w połączeniu z internetową komunikacją równorzędną**: pobieranie aktualizacji z Internetu i innych komputerów w sieci.
        - **Prosty tryb pobierania bez komunikacji równorzędnej**: pobieranie aktualizacji z Internetu bezpośrednio od właściciela aktualizacji, takiego jak firma Microsoft. Podczas tego procesu nie ma kontaktu z usługami optymalizacji dostarczania w chmurze.
        - **Tryb obejścia**: pobieranie aktualizacji przez zastosowanie Usługi inteligentnego transferu w tle (BITS). Optymalizacja dostarczania nie jest używana.

4. Po zakończeniu wybierz pozycję **OK**  >  **Utwórz**, aby zapisać zmiany.

Profil zostanie utworzony i wyświetlony na liście. W dalszej części [przypiszesz profil](device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).

## <a name="move-existing-update-rings-to-delivery-optimization"></a>Przenoszenie istniejących pierścieni aktualizacji do optymalizacji dostarczania

**Aktualizacje oprogramowania — pierścienie aktualizacji systemu Windows 10** są zastępowane przez ustawienia **optymalizacji dostarczania**. Istniejące pierścienie aktualizacji można łatwo zmienić, tak aby używać ustawień **optymalizacji dostarczania**. Kroki:

1. Utwórz profil konfiguracji optymalizacji dostarczania:

    1. W usłudze Intune wybierz kolejno pozycje **Konfiguracja urządzenia** > **Profile** > **Utwórz profil**.
    2. Wprowadź następujące właściwości:

        - **Nazwa**: Wprowadź opisową nazwę nowego profilu.
        - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
        - **Platforma**: Wybierz pozycję **Windows 10 i nowsze**.
        - **Typ profilu**: wybierz pozycję **Optymalizacja dostarczania**.
        - **Ustawienia**: W obszarze **Tryb pobierania optymalizacji dostarczania** wybierz tryb używany już przez istniejący pierścień aktualizacji oprogramowania. Dostępne opcje:
            - **Nieskonfigurowany**
            - **Tylko protokół HTTP, bez komunikacji równorzędnej**
            - **Protokół HTTP w połączeniu z komunikacją równorzędną za tym samym translatorem adresów sieciowych**
            - **Protokół HTTP w połączeniu z komunikacją równorzędną w grupie prywatnej**
            - **Protokół HTTP w połączeniu z internetową komunikacją równorzędną**
            - **Prosty tryb pobierania bez komunikacji równorzędnej**
            - **Tryb obejścia**

2. Przypisz ten nowy profil do tych samych urządzeń i użytkowników jako istniejący pierścień aktualizacji oprogramowania. Listę kroków można znaleźć w temacie [Przypisywanie profilu](device-profile-assign.md).

3. Usuń konfigurację istniejącego pierścienia oprogramowania:
    1. W usłudze Intune przejdź do pozycji **Aktualizacje oprogramowania** > Pierścienie aktualizacji systemu Windows 10.
    2. Z listy wybierz pierścień aktualizacji.
    3. W obszarze ustawień ustaw **Tryb pobierania optymalizacji dostarczania** na wartość **Nieskonfigurowane**.
    4. **OK** > **Zapisz** zmiany.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).
