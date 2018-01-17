---
title: "Konfigurowanie uaktualnień wersji systemu Windows 10 w usłudze Intune"
titlesuffix: Azure portal
description: "Informacje o korzystaniu z usługi Intune do uaktualniania zarządzanych urządzeń z systemem Windows 10 do innych wersji."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b4e1fc203633a9624ce748ab1f36374c5322e3f7
ms.sourcegitcommit: 061dab899e3fbc59b0128e2b4fbdf8ebf80afddd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-configure-windows-10-edition-upgrades-in-microsoft-intune"></a>Jak skonfigurować uaktualnienia wersji systemu Windows 10 w usłudze Microsoft Intune
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zapoznaj się z informacjami zawartymi w tym artykule, aby dowiedzieć się, jak skonfigurować profil uaktualnienia systemu Windows 10. Profil ten umożliwia automatyczne uaktualnianie urządzeń z uruchomioną wersją systemu Windows 10 do innej wersji. 

## <a name="before-you-start"></a>Przed rozpoczęciem
Przed rozpoczęciem uaktualniania urządzeń do najnowszej wersji potrzebujesz jednego z następujących elementów:

- Klucza produktu umożliwiającego zainstalowanie nowej wersji systemu Windows na wszystkich docelowych urządzeniach zasad (w przypadku wersji Windows 10 Desktop). Można użyć kluczy aktywacji wielokrotnej (MAK), kluczy usługi serwera zarządzania kluczami (KMS) lub też pliku licencji od firmy Microsoft, który zawiera informacje licencyjne umożliwiające zainstalowanie nowej wersji systemu Windows na wszystkich docelowych urządzeniach zasad (w przypadku wersji Windows 10 Mobile i Windows 10 Holographic).
- Urządzenia z systemem Windows 10, do których są przypisywane zasady, muszą zostać zarejestrowane w usłudze Microsoft Intune. Z zasad uaktualniania wersji nie można korzystać w przypadku komputerów z oprogramowaniem klienckim Intune.

## <a name="supported-upgrade-paths-for-the-windows-10-edition-upgrade-profile"></a>Obsługiwane ścieżki uaktualnienia profilu uaktualnienia wersji systemu Windows 10
Następujące listy zawierają obsługiwane ścieżki uaktualnienia dla profilu uaktualnienia wersji systemu Windows 10. Wersja systemu Windows 10, do której jest wykonywane uaktualnienie, jest oznaczona pogrubioną czcionką. Po niej następuje lista obsługiwanych wersji, które można uaktualnić:

**Windows 10 Education**
- Windows 10 Pro
- Windows 10 Pro Education
- Windows 10 Cloud
- Windows 10 Enterprise
- Windows 10 Core
    
**Wersja N systemu Windows 10 Education**    
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
- Windows 10 Mobile

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
1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Konfiguracja urządzeń**.
2. W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
3. W bloku profilów wybierz pozycję **Utwórz profil**.
4. W bloku **Utwórz profil** uzupełnij pola **Nazwa** i **Opis** odnoszące się do profilu uaktualnienia wersji.
5. Z listy rozwijanej **Platforma** wybierz pozycję **Windows 10 lub nowszy**.
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Uaktualnienie wersji**.
7. W bloku **Uaktualnienie wersji** skonfiguruj następujące ustawienia:
    - **Wersja, do której chcesz uaktualnić** — z listy rozwijanej wybierz wersję systemu — Windows 10 Desktop, Windows 10 Holographic lub Windows 10 Mobile — do której mają zostać uaktualnione docelowe urządzenia.
    - **Klucz produktu** — podaj uzyskany od firmy Microsoft klucz produktu, który może zostać użyty do uaktualnienia wszystkich docelowych urządzeń z systemem Windows 10 Desktop.<br>Nie można edytować klucza produktu po utworzeniu zasad, które go zawierają. Jest to spowodowane zasłonięciem klucza ze względów bezpieczeństwa. Aby zmienić klucz produktu, musisz wprowadzić ponownie cały klucz.
    - **Plik licencji** — wybierz pozycję **Przeglądaj**, aby znaleźć plik licencji uzyskany od firmy Microsoft zawierający informacje o licencji dla wersji Windows Holographic lub Windows 10 Mobile, do której chcesz uaktualnić docelowe urządzenia.
8. Gdy skończysz, wróć do bloku **Utwórz profil** i wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony w bloku listy profilów.

## <a name="next-steps"></a>Następne kroki

Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](device-profile-assign.md) (Sposoby przypisywania profilów urządzeń).

>[!NOTE]
>Jeśli później usuniesz przypisanie zasad, wersja systemu Windows na urządzeniu nie zostanie przywrócona i będzie dalej działać normalnie.

