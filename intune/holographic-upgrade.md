---
title: Uaktualnienie do systemu Windows Holographic for Business
titleSuffix: Microsoft Intune
description: Dowiedz się, jak uaktualnić urządzenia z systemem Windows Holographic do systemu Windows Holographic for Business
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: bfca0cb5b02fdf77fa9a0bab42af05fd04b5c140
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55838890"
---
# <a name="upgrade-devices-running-windows-holographic-to-windows-holographic-for-business"></a>Uaktualnianie urządzeń z systemem Windows Holographic do systemu Windows Holographic for Business

Usługa Microsoft Intune zawiera wiele ustawień pomocnych w przypadku zarządzania urządzeniami i ich ochrony. W tym artykule wymieniono i opisano ustawienia używane do uaktualniania urządzeń z systemem Windows Holographic do systemu Windows Holographic for Business. Te ustawienia są tworzone w profilu konfiguracji uaktualniania w usłudze Intune oraz są wypychane do urządzeń lub na nich wdrażane.

W ramach rozwiązania do zarządzania urządzeniami przenośnymi (MDM) użyj tych ustawień, aby uaktualnić urządzenia z systemem Windows Holographic. W przypadku urządzeń Microsoft HoloLens możesz kupić wersję Commercial Suite, aby uzyskać wymaganą licencję na uaktualnienie. Aby uzyskać więcej informacji, zobacz [Unlock Windows Holographic for Business features](https://docs.microsoft.com/hololens/hololens-upgrade-enterprise) (Odblokowanie funkcji systemu Windows Holographic for Business).

Aby uzyskać więcej informacji na temat tej funkcji, zobacz [Uaktualnianie wersji systemu Windows 10 lub włączanie trybu S](edition-upgrade-configure-windows-10.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia](edition-upgrade-configure-windows-10.md#create-the-profile).

## <a name="edition-upgrade"></a>Zasady uaktualniania wersji

- **Wersja, do której ma być uaktualniany system**: wybierz pozycję **Windows 10 Holographic for Business**.
- **Plik licencji**: wyszukaj i wybierz plik licencji XML, który został udostępniony.

  ![Wprowadzanie nazwy pliku XML, który zawiera informacje dotyczące licencji systemu Holographic for Business](media/Holographic-edition-upgrade.png)
 
## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale może jeszcze nie wykonywać żadnych czynności. Pamiętaj, aby [przypisać profil](device-profile-assign.md) i [monitorować jego stan](device-profile-monitor.md).

Można również utworzyć profile uaktualniania wersji dla urządzeń z [systemem Windows 10 i nowszym](edition-upgrade-windows-settings.md).
