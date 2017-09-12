---
title: "Konfigurowanie uaktualnień wersji systemu Windows 10 w usłudze Intune"
titlesuffix: Azure portal
description: "Informacje o korzystaniu z usługi Intune do uaktualniania zarządzanych urządzeń z systemem Windows 10 do innych wersji."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f6bd4c4af168bc64acabc05fdaad93558ddd10a
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-configure-windows-10-edition-upgrades-in-microsoft-intune"></a>Jak skonfigurować uaktualnienia wersji systemu Windows 10 w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zapoznaj się z informacjami zawartymi w tym temacie, aby dowiedzieć się, jak skonfigurować profil uaktualnienia systemu Windows 10. Profil ten umożliwia automatyczne uaktualnianie urządzeń z uruchomioną jedną z następujących wersji systemu Windows 10 do innej wersji:

- Windows 10 Home
- Windows 10 Holographic
- Windows 10 Mobile


Obsługiwane są następujące ścieżki uaktualniania:

- Z systemu Windows 10 Pro do systemu Windows 10 Enterprise
- Z systemu Windows 10 Home do systemu Windows 10 Education
- Z systemu Windows 10 Mobile do systemu Windows 10 Mobile Enterprise
- Z systemu Windows 10 Holographic Pro do systemu Windows 10 Holographic Enterprise


## <a name="before-you-start"></a>Przed rozpoczęciem
Przed rozpoczęciem uaktualniania urządzeń do najnowszej wersji potrzebujesz jednego z następujących elementów:

- Klucza produktu umożliwiającego zainstalowanie nowej wersji systemu Windows na wszystkich docelowych urządzeniach zasad (w przypadku wersji Windows 10 Desktop). Można użyć kluczy aktywacji wielokrotnej (MAK), kluczy usługi serwera zarządzania kluczami (KMS) lub też pliku licencji od firmy Microsoft, który zawiera informacje licencyjne umożliwiające zainstalowanie nowej wersji systemu Windows na wszystkich docelowych urządzeniach zasad (w przypadku wersji Windows 10 Mobile i Windows 10 Holographic).
- Urządzenia z systemem Windows 10, do których są przypisywane zasady, muszą zostać zarejestrowane w usłudze Microsoft Intune. Z zasad uaktualniania wersji nie można korzystać w przypadku komputerów z oprogramowaniem klienckim Intune.

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
    - **Wersja, z której chcesz aktualizować** — z listy rozwijanej wybierz wersję systemu Windows 10, która ma zostać uaktualniona na urządzeniach.
    - **Wersja, do której chcesz uaktualnić** — z listy rozwijanej wybierz wersję systemu — Windows 10 Desktop, Windows 10 Holographic lub Windows 10 Mobile — do której mają zostać uaktualnione docelowe urządzenia.
    - **Klucz produktu** — podaj uzyskany od firmy Microsoft klucz produktu, który może zostać użyty do uaktualnienia wszystkich docelowych urządzeń z systemem Windows 10 Desktop.<br>Nie można edytować klucza produktu po utworzeniu zasad, które go zawierają. Jest to spowodowane zasłonięciem klucza ze względów bezpieczeństwa. Aby zmienić klucz produktu, musisz wprowadzić ponownie cały klucz.
    - **Plik licencji** — wybierz pozycję **Przeglądaj**, aby znaleźć plik licencji uzyskany od firmy Microsoft zawierający informacje o licencji dla wersji Windows Holographic lub Windows 10 Mobile, do której chcesz uaktualnić docelowe urządzenia.
8. Gdy skończysz, wróć do bloku **Utwórz profil** i wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony w bloku listy profilów.

## <a name="next-steps"></a>Następne kroki

Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](device-profile-assign.md) (Sposoby przypisywania profilów urządzeń).

>[!NOTE]
>Jeśli później usuniesz przypisanie zasad, wersja systemu Windows na urządzeniu nie zostanie przywrócona i będzie dalej działać normalnie.

