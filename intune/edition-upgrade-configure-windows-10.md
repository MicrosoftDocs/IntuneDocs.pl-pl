---
title: "Uaktualnianie urządzeń z systemem Windows 10 za pomocą usługi Microsoft Intune — Azure | Microsoft Docs"
description: "Utwórz profil urządzenia w usłudze Microsoft Intune, aby uaktualnić urządzenia z systemem Windows 10 do nowszych wersji. Dowiedz się również o obsługiwanych ścieżkach uaktualniania dla systemu Windows 10 Pro, N Edition, Education, Cloud, Enterprise, Core, Holographic i Mobile."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8084f1b2fbd513de596bd97f4ffec995b6f7aac4
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/08/2018
---
# <a name="configure-windows-10-edition-upgrade-profile-in-intune"></a>Konfigurowanie profilu uaktualniania wersji systemu Windows 10 w usłudze Intune
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Skonfiguruj profil uaktualniania w usłudze Intune, aby automatycznie uaktualnić urządzenia z uruchomioną wersją systemu Windows 10 do innej wersji. Dowiedz się również o obsługiwanych ścieżkach uaktualniania.

## <a name="before-you-begin"></a>Przed rozpoczęciem
Przed uaktualnianiem urządzeń do najnowszej wersji potrzebujesz jednego z następujących elementów:

- Prawidłowego klucza produktu w celu zainstalowanie zaktualizowanej wersji systemu Windows na wszystkich docelowych urządzeniach zasad (w przypadku wersji Windows 10 Desktop). Możesz użyć kluczy aktywacji wielokrotnej (MAK), kluczy serwera zarządzania kluczami (KMS) lub pliku licencji firmy Microsoft, który zawiera informacje licencyjne umożliwiające zainstalowanie zaktualizowanej wersji systemu Windows na wszystkich docelowych urządzeniach zasad (w przypadku wersji Windows 10 Mobile i Windows 10 Holographic).
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

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Tworzenie profilu urządzenia zawierającego ustawienia ograniczeń dotyczących urządzeń
1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. W obszarze **Konfiguracja urządzeń** wybierz pozycję **Profile**, a następnie wybierz pozycję **Utwórz profil**.
4. Wprowadź wartość w polach **Nazwa** i **Opis** dotyczących profilu uaktualnienia wersji.
5. Z listy rozwijanej **Platforma** wybierz pozycję **Windows 10 lub nowszy**.
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Uaktualnienie wersji**.
7. W ramach właściwości **Uaktualnienie wersji** wprowadź następujące ustawienia:
  - **Wersja, do której chcesz uaktualnić** — z listy rozwijanej wybierz wersję systemu — Windows 10 Desktop, Windows 10 Holographic lub Windows 10 Mobile — do której zostaną uaktualnione docelowe urządzenia.
  - **Klucz produktu** — wprowadź otrzymany od firmy Microsoft klucz produktu, który może zostać użyty do uaktualnienia wszystkich docelowych urządzeń z systemem Windows 10 Desktop. 
    Po utworzeniu zasad zawierających klucz produktu nie jest możliwe zaktualizowanie takiego klucza i jest on ukryty ze względów bezpieczeństwa. Aby zmienić klucz produktu, ponownie wprowadź cały klucz.
  - **Plik licencji** — wybierz pozycję **Przeglądaj**, aby wybrać plik licencji otrzymany od firmy Microsoft. Ten plik licencji otrzymany od firmy Microsoft zawiera informacje o licencji dla wersji Windows Holographic lub Windows 10 Mobile, do której są uaktualniane docelowe urządzenia.
8. Po zakończeniu wybierz pozycję **Utwórz**, aby zapisać zmiany.

Profil zostanie utworzony i wyświetlony na liście profilów.

## <a name="next-steps"></a>Następne kroki

Aby przypisać ten profil do grup, zobacz [Jak przypisywać profile urządzeń](device-profile-assign.md).

>[!NOTE]
>Jeśli później usuniesz przypisanie zasad, wersja systemu Windows na urządzeniu nie zostanie przywrócona i będzie dalej działać normalnie.