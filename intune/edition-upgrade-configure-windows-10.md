---
title: Uaktualnianie lub używanie trybu S na urządzeniach z systemem Windows 10 — Microsoft Intune — Azure | Microsoft Docs
description: Użyj usługi Microsoft Intune, aby uaktualnić urządzenia z systemem Windows 10 do innych wersji lub aby włączyć tryb S. Administratorzy mogą używać profilu konfiguracji urządzenia, aby uaktualniać system Windows 10 Professional do wersji Windows 10 Enterprise oraz aby włączać lub wyłączać tryb S. Dowiedz się więcej o obsługiwanych ścieżkach uaktualniania dla systemu Windows 10 Pro, N Edition, Education, Cloud, Enterprise, Core, Holographic i Mobile.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 3eea1d1f100515b29dfda3b2297005f61e05ea23
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54831619"
---
# <a name="upgrade-windows-10-editions-or-enable-s-mode-on-devices-using-microsoft-intune"></a>Uaktualnianie wersji systemu Windows 10 lub włączanie trybu S na urządzeniach przy użyciu usługi Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W ramach rozwiązania do zarządzania urządzeniami przenośnymi (MDM) można uaktualnić urządzenia z systemem Windows 10. Możesz na przykład chcieć uaktualnić urządzenia z systemem Windows 10 Professional do systemu Windows 10 Enterprise. Możesz również włączyć tryb mobilny S, aby urządzenia uruchamiały tylko aplikacje ze sklepu Microsoft Store.

[Tryb S systemu Windows 10](https://support.microsoft.com/help/4456067/windows-10-switch-out-of-s-mode) zaprojektowano z myślą o bezpieczeństwie i wydajności. Jeśli na urządzeniach uruchamiane są tylko aplikacje ze sklepu Microsoft Store, używanie trybu S ułatwia zadbanie o bezpieczeństwo urządzeń. Jeśli urządzenia używają aplikacji, które nie są dostępne w sklepie Microsoft Store, tryb S zostaje wyłączony. Wyłączenie trybu S to działanie jednokierunkowe. Po wyłączeniu trybu S systemu Windows 10 nie można już do niego wrócić.

Ta funkcja ma zastosowanie do:

- System Windows 10 lub nowszy
- System Windows 10 1809 lub nowszy dla trybu S
- Windows Holographic for Business

Te funkcje są dostępne w usłudze Intune i są konfigurowane przez administratora. „Profile konfiguracji” są używane w usłudze Intune do tworzenia i dostosowywania tych ustawień na potrzeby organizacji. Po dodaniu tych funkcji w profilu można następnie wypychać lub wdrażać profil na urządzeniach z systemem Windows 10 w organizacji. Podczas wdrażania profilu usługa Intune automatycznie uaktualnia urządzenia lub włącza tryb S.

Ten artykuł zawiera listę obsługiwanych ścieżek uaktualniania i pokazuje, jak utworzyć profil konfiguracji urządzenia. Można również zapoznać się z dostępnymi ustawieniami uaktualnień i trybu S dla systemu [Windows 10](edition-upgrade-windows-settings.md).

> [!NOTE]
> Jeśli później usuniesz przypisanie zasad, wersja systemu Windows na urządzeniu nie zostanie przywrócona. Urządzenie będzie w dalszym ciągu działać normalnie.

## <a name="prerequisites"></a>Wymagania wstępne

Przed uaktualnianiem urządzeń upewnij się, że spełniono następujące wymagania wstępne:

- Prawidłowego klucza produktu w celu zainstalowanie zaktualizowanej wersji systemu Windows na wszystkich docelowych urządzeniach zasad (w przypadku wersji Windows 10 Desktop). Można użyć kluczy aktywacji wielokrotnej (MAK), kluczy usługi serwera zarządzania kluczami (KMS)
- W przypadku wersji Windows 10 Mobile i Windows 10 Holographic można użyć pliku licencji firmy Microsoft. Plik licencji zawiera informacje o licencjonowaniu, które umożliwiają zainstalowanie zaktualizowanej wersji na wszystkich urządzeniach docelowych zasad.
- Urządzenia z systemem Windows 10, którym przypisywane są zasady, zostały zarejestrowane w usłudze Microsoft Intune. Z zasad uaktualniania wersji nie można korzystać w przypadku komputerów z oprogramowaniem klienckim Intune.

## <a name="supported-upgrade-paths"></a>Obsługiwane ścieżki uaktualnienia

Poniższa tabela zawiera listę obsługiwanych ścieżek uaktualnienia dla profilu uaktualnienia wersji systemu Windows 10.

| Uaktualnienie z | Uaktualnienie do |
|---|---|
| Windows 10 Pro | Windows 10 Education <br/>Windows 10 Enterprise <br/>Windows 10 Pro Education |
| Windows 10 Pro N edition | Wersja N systemu Windows 10 Education <br/>Windows 10 Enterprise N edition <br/>Windows 10 Pro Education N edition | 
| Windows 10 Pro Education | Windows 10 Education | 
| Windows 10 Pro Education N edition | Wersja N systemu Windows 10 Education |
| Windows 10 Cloud | Windows 10 Education <br/>Windows 10 Enterprise <br/>Windows 10 Pro <br/>Windows 10 Pro Education | 
| Windows 10 Cloud N edition | Wersja N systemu Windows 10 Education <br/>Windows 10 Enterprise N edition <br/>Windows 10 Pro N edition <br/>Windows 10 Pro Education N edition | 
| Windows 10 Enterprise | Windows 10 Education | 
| Windows 10 Enterprise N edition | Wersja N systemu Windows 10 Education | 
| Windows 10 Core | Windows 10 Education <br/>Windows 10 Enterprise <br/>Windows 10 Pro Education | 
| Windows 10 Core N edition | Wersja N systemu Windows 10 Education <br/>Windows 10 Enterprise N edition <br/>Windows 10 Pro Education N edition | 
| Windows 10 Holographic | Windows 10 Holographic for Business |
| Windows 10 Mobile | Windows 10 Mobile Enterprise |

<!--The following table provides information about the supported upgrade paths for Windows 10 editions in this policy:

![supported](./media/check_grn.png)  (X) = not supported    
![unsupported](./media/x_blk.png)    (green checkmark) = supported    

|Upgrade from edition\Upgrade to edition|Education|Education N|Pro Education|Pro Education N|Enterprise|Enterprise N|Professional|Professional N|Mobile Enterprise|Holographic for Business|
|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|
|Pro|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro Education|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro Education N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Cloud|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Cloud N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Enterprise|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Enterprise N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Core|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)   |![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Core N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Mobile|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|
|Holographic|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png) -->

## <a name="create-the-profile"></a>Tworzenie profilu

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, wpisz nazwę usługi **Intune** w filtrze, a następnie wybierz pozycję **Intune**.
2. Wybierz kolejno pozycje **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Wprowadź następujące właściwości:

    - **Nazwa**: Wprowadź opisową nazwę nowego profilu. Na przykład wpisz coś takiego: `Windows 10 edition upgrade profile` lub `Windows 10 switch off S mode`.
    - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: wybierz platformę:  

        - **Windows 10 lub nowszy**

    - **Typ profilu**: wybierz pozycję **Uaktualnienie wersji**.
    - **Ustawienia**: wprowadź ustawienia, które chcesz skonfigurować. Listę wszystkich ustawień i ich zadań można znaleźć w temacie:

        - [Windows 10 upgrade and S mode](edition-upgrade-windows-settings.md) (Uaktualnianie systemu Windows 10 i tryb S)
        - [Windows Holographic for Business](holographic-upgrade.md)

4. Wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany. 

Profil zostanie utworzony i wyświetlony na liście. Pamiętaj, aby [przypisać profil](device-profile-assign.md) i [monitorować jego stan](device-profile-monitor.md).

## <a name="next-steps"></a>Następne kroki

Po utworzeniu profil jest gotowy do przypisania. W dalszej części [przypiszesz profil](device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).

Wyświetl ustawienia uaktualniania i trybu S dla urządzeń z systemem [Windows 10](edition-upgrade-windows-settings.md) oraz [Windows Holographic for Business](holographic-upgrade.md).
