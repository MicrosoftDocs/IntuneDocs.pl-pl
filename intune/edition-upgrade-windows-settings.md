---
title: Ustawienia uaktualniania systemu Windows 10 i trybu S w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z listą wszystkich ustawień i ich zadań wykonywanych podczas uaktualniania wersji systemu Windows 10 na urządzeniu lub włączania trybu S na urządzeniu przy użyciu profilu konfiguracji urządzenia w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 24f763cf3231bd76a01870d889cb7637f2f36532
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55849679"
---
# <a name="windows-10-and-newer-device-settings-to-upgrade-editions-or-enable-s-mode-in-intune"></a>Ustawienia urządzeń z systemem Windows 10 (lub nowszym) służące do uaktualniania wersji lub włączenia trybu S w usłudze Intune

Usługa Microsoft Intune zawiera wiele ustawień pomocnych w przypadku zarządzania urządzeniami i ich ochrony. W tym artykule wymieniono i opisano ustawienia służące do uaktualniania wersji lub włączania trybu S na urządzeniach z systemem Windows 10. Te ustawienia są tworzone w profilu konfiguracji uaktualniania w usłudze Intune oraz są wypychane do urządzeń lub na nich wdrażane.

W ramach rozwiązania do zarządzania urządzeniami przenośnymi (MDM) użyj tych ustawień, aby kontrolować opcje wersji i trybu S dla urządzeń z systemem Windows 10.

Aby uzyskać więcej informacji na temat tej funkcji, zobacz [Uaktualnianie wersji systemu Windows 10 lub włączanie trybu S](edition-upgrade-configure-windows-10.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil](edition-upgrade-configure-windows-10.md#create-the-profile).

## <a name="edition-upgrade"></a>Zasady uaktualniania wersji

- **Wersja, do której ma być uaktualniany system**: wybierz wersję systemu Windows 10, do której chcesz uaktualnić system. Urządzenia objęte tymi zasadami zostaną uaktualnione do wybranej wersji.
- **Klucz produktu**: wprowadź otrzymany od firmy Microsoft klucz produktu. Po utworzeniu zasad zawierających klucz produktu nie jest możliwe zaktualizowanie takiego klucza i jest on ukryty ze względów bezpieczeństwa. Aby zmienić klucz produktu, ponownie wprowadź cały klucz.
- **Plik licencji**: w przypadku systemu **Windows 10 Holographic for Business** lub **Windows 10 Mobile** wybierz pozycję **Przeglądaj**, aby wybrać plik licencji otrzymany od firmy Microsoft. Ten plik licencji zawiera informacje o licencjach dla wersji, do których są uaktualniane urządzenia.

## <a name="mode-switch"></a>Przełączanie trybu

- **Brak konfiguracji**: urządzenie w trybie S pozostaje w trybie S. Użytkownik końcowy może wyłączyć tryb S na urządzeniu.
- **Zachowaj w trybie S**: uniemożliwia użytkownikowi końcowemu wyłączenie trybu S na urządzeniu.
- **Wyłącz**: wyłącza tryb S na urządzeniu.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale może jeszcze nie wykonywać żadnych czynności. Pamiętaj, aby [przypisać profil](device-profile-assign.md) i [monitorować jego stan](device-profile-monitor.md).

Można również utworzyć profile uaktualniania wersji dla urządzeń z [systemem Windows Holographic for Business](holographic-upgrade.md).
