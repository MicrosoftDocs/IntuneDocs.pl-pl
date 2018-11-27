---
title: Uaktualnianie lub używanie trybu S na urządzeniach z systemem Windows 10 za pomocą usługi Microsoft Intune — Azure | Microsoft Docs
description: Utwórz profil urządzenia w usłudze Microsoft Intune, aby uaktualnić urządzenia z systemem Windows 10 do innych wersji. Możesz na przykład uaktualnić system Windows 10 Professional do systemu Windows 10 Enterprise. Możesz również włączyć lub wyłączyć tryb S na urządzeniu przy użyciu profilu konfiguracji. Dowiedz się również o obsługiwanych ścieżkach uaktualniania dla systemu Windows 10 Pro, N Edition, Education, Cloud, Enterprise, Core, Holographic i Mobile.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: eb44647e50e406b9ef5052c576660c9b7eebf6dd
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52189762"
---
# <a name="use-a-configuration-profile-to-upgrade-windows-10-or-switch-from-s-mode-in-intune"></a>Uaktualnianie systemu Windows 10 lub wyłączanie trybu S w usłudze Intune przy użyciu profilu konfiguracji
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Skonfiguruj profil uaktualniania w usłudze Intune, aby automatycznie uaktualnić urządzenia z uruchomioną wersją systemu Windows 10 do innej wersji. Dowiedz się również o obsługiwanych ścieżkach uaktualniania.

## <a name="before-you-begin"></a>Przed rozpoczęciem
Przed uaktualnieniem urządzeń do najnowszej wersji potrzebujesz następujących elementów:

- Prawidłowego klucza produktu w celu zainstalowanie zaktualizowanej wersji systemu Windows na wszystkich docelowych urządzeniach zasad (w przypadku wersji Windows 10 Desktop). Można użyć kluczy aktywacji wielokrotnej (MAK), kluczy usługi serwera zarządzania kluczami (KMS) lub też pliku licencji od firmy Microsoft, który zawiera informacje licencyjne umożliwiające zainstalowanie zaktualizowanej wersji systemu Windows na wszystkich docelowych urządzeniach zasad (w przypadku wersji Windows 10 Mobile i Windows 10 Holographic).
- Urządzenia z systemem Windows 10, którym przypisywane są zasady, zostały zarejestrowane w usłudze Microsoft Intune. Z zasad uaktualniania wersji nie można korzystać w przypadku komputerów z oprogramowaniem klienckim Intune.

## <a name="supported-upgrade-paths"></a>Obsługiwane ścieżki uaktualniania
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


<!-- Testing a new table on 3/5/18 

The following lists provide the supported upgrade paths for the Windows 10 edition upgrade profile. The Windows 10 edition to upgrade to is in bold followed by the list of supported editions that you can upgrade from:

**Windows 10 Education**
- Windows 10 Pro
- Windows 10 Pro Education
- Windows 10 Cloud
- Windows 10 Enterprise
- Windows 10 Core
    
**Windows 10 Education N edition**    
- Windows 10 Pro N edition
- Windows 10 Pro Education N edition
- Windows 10 Cloud N edition
- Windows 10 Enterprise N edition
- Windows 10 Core N edition
    
**Windows 10 Enterprise**
- Windows 10 Pro
- Windows 10 Cloud
- Windows 10 Core
    
**Windows 10 Enterprise N edition**
- Windows 10 Pro N edition
- Windows 10 Cloud N edition
- Windows 10 Core N edition
    
**Windows 10 Pro**
- Windows 10 Cloud
    
**Windows 10 Pro N edition**
- Windows 10 Cloud N edition
    
**Windows 10 Pro Education**
- Windows 10 Pro
- Windows 10 Cloud
- Windows 10 Core
    
**Windows 10 Pro Education N edition**
- Windows 10 Pro N edition
- Windows 10 Cloud N edition
- Windows 10 Core N edition

**Windows 10 Holographic for Business**
- Windows 10 Holographic

**Windows 10 Mobile Enterprise**
- Windows 10 Mobile -->

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

## <a name="upgrade-the-edition"></a>Uaktualnianie wersji

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
2. Wybierz kolejno pozycje **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Wprowadź **nazwę** i **opis** profilu. Na przykład wpisz coś takiego: `Windows 10 edition upgrade`
4. W polu **Platforma** wybierz pozycję **Windows 10 i nowsze**.
5. W polu **Typ profilu** wybierz opcję **Uaktualnienie wersji**.
6. W ramach właściwości **Uaktualnienie wersji** wprowadź następujące ustawienia:

   - **Docelowa wersja uaktualnienia**: wybierz wersję systemu Windows 10, do której chcesz uaktualnić system. Urządzenia objęte tymi zasadami zostaną uaktualnione do wybranej wersji.
   - **Klucz produktu**: wprowadź otrzymany od firmy Microsoft klucz produktu. Po utworzeniu zasad zawierających klucz produktu nie jest możliwe zaktualizowanie takiego klucza i jest on ukryty ze względów bezpieczeństwa. Aby zmienić klucz produktu, ponownie wprowadź cały klucz.
   - **Plik licencji**: w przypadku systemu **Windows 10 Holographic for Business** lub **Windows 10 Mobile** wybierz pozycję **Przeglądaj**, aby wybrać plik licencji otrzymany od firmy Microsoft. Ten plik licencji zawiera informacje o licencjach dla wersji, do których są uaktualniane docelowe urządzenia.

7. Wybierz przycisk **OK**, aby zapisać zmiany. Wybierz pozycję **Utwórz**, aby utworzyć profil.

## <a name="switch-out-of-s-mode"></a>Wyłączanie trybu S

[Tryb S systemu Windows 10](https://support.microsoft.com/help/4456067/windows-10-switch-out-of-s-mode) zaprojektowano z myślą o bezpieczeństwie i wydajności. Jeśli na urządzeniach uruchamiane są tylko aplikacje ze sklepu Microsoft Store, używanie trybu S ułatwia zadbanie o bezpieczeństwo urządzeń. Jeśli urządzenia wymagają aplikacji, które nie są dostępne w sklepie Microsoft Store, tryb S zostaje wyłączony. Wyłączenie trybu S to działanie jednokierunkowe. Po wyłączeniu trybu S systemu Windows 10 nie można już do niego wrócić.

W poniższych krokach pokazano, jak utworzyć profil sterujący trybem S na urządzeniach z systemem Windows 10 (w wersji 1809 lub nowszej).

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
2. Wybierz kolejno pozycje **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Wprowadź **nazwę** i **opis** profilu. Na przykład wpisz coś takiego: `Windows 10 switch off S mode`
4. W polu **Platforma** wybierz pozycję **Windows 10 i nowsze**.
5. W polu **Typ profilu** wybierz opcję **Uaktualnienie wersji**.
6. Wybierz pozycję **Mode switch (Windows Insider only)** (Przełącznik trybów — tylko niejawny program testów systemu Windows) i ustaw właściwość **Switch out of S mode** (Wyłączanie trybu S). Dostępne opcje:

    - **Brak konfiguracji**: urządzenie trybu S pozostaje w tym trybie. Użytkownik końcowy może wyłączyć tryb S na urządzeniu.
    - **Keep in S mode** (Pozostaw w trybie S): uniemożliwia użytkownikowi końcowemu wyłączenie trybu S na urządzeniu.
    - **Switch** (Wyłącz): wyłącza tryb S na urządzeniu.

7. Wybierz przycisk **OK**, aby zapisać zmiany. Wybierz pozycję **Utwórz**, aby utworzyć profil.

Profil zostanie utworzony i wyświetlony na liście profilów.

## <a name="next-steps"></a>Następne kroki

[Przypisz ten profil](device-profile-assign.md) do grup.

>[!NOTE]
>Jeśli później usuniesz przypisanie zasad, wersja systemu Windows na urządzeniu nie zostanie przywrócona i będzie dalej działać normalnie.
