---
title: Ustawienia urządzeń udostępnianych z systemem Windows Holographic for Business — Microsoft Intune — Azure | Microsoft Docs
description: Dodaj system Windows Holographic for Business i używaj go w celu skonfigurowania urządzeń udostępnionych lub używanych przez wielu użytkowników w usłudze Microsoft Intune. Wyświetl listę ustawień Zarządzania kontami i przekonaj się, jak działają na urządzeniach, na przykład urządzeniu Microsoft HoloLens.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/09/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 428025e5e56450fd859f6bf2c9a990cbdca4f263
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55835116"
---
# <a name="windows-holographic-for-business-settings-to-manage-shared-devices-using-intune"></a>Ustawienia systemu Windows Holographic for Business służące do zarządzenia urządzeniami udostępnionymi przy użyciu usługi Intune

Urządzenia z systemem Windows Holographic for Business, takie jak Microsoft HoloLens, mogą być używane przez wielu użytkowników. Urządzenia, które mają wielu użytkowników, to tak zwane urządzenia udostępnione. Jest to element rozwiązań do zarządzania urządzeniami mobilnymi.

Dzięki usłudze Microsoft Intune użytkownicy mogą zalogować się na tych urządzeniach udostępnionych na kontach gości. Podczas korzystania z urządzenia mają dostęp tylko do tych funkcji, które im udostępnisz.

W tym artykule wymieniono i opisano ustawienia używane w profilu konfiguracji urządzenia z systemem Windows Holographic for Business. Po utworzeniu profilu w usłudze Intune możesz go następnie wdrożyć lub przypisać do grupy urządzeń w swojej organizacji. Możesz również przypisać ten profil do grup urządzeń składających się z różnych typów urządzeń i wersji systemu operacyjnego.

Aby uzyskać więcej informacji na temat tej funkcji w usłudze Intune, zobacz [Control access, accounts, and power features on shared PC or multi-user devices (Kontrola dostępu, konta i funkcje zasilania na komputerze udostępnionym lub urządzeniach obsługujących wielu użytkowników)](shared-user-device-settings.md). Aby uzyskać więcej informacji na temat dostawcy CSP w systemie Windows, zobacz [AccountManagement CSP](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp).

## <a name="before-your-begin"></a>Zanim rozpoczniesz

[Utwórz profil](shared-user-device-settings.md).

## <a name="shared-multi-user-device-settings"></a>Ustawienia urządzenia udostępnionego obsługującego wielu użytkowników

> [!NOTE]
> Urządzenia z systemem Windows Holographic for Business, w tym Microsoft HoloLens, obsługują wyłącznie ustawienia **Zarządzania kontami**. Jeśli skonfigurujesz jakiekolwiek inne ustawienia pokazane w usłudze Intune, na przykład **Tryb komputera udostępnionego**, nie ma to wpływu na te urządzenia.

- **Zarządzanie kontami**: Ustaw w pozycji **Włącz**, aby automatycznie usuwać konta lokalne utworzone przez gości oraz konta w usługach AD i Azure AD. Gdy użytkownik wyloguje się z urządzenia lub gdy zostanie uruchomiona konserwacja systemu, te konta zostaną usunięte. Gdy to ustawienie jest włączone, należy również skonfigurować:
  - **Usuwanie kont**: Wybierz, kiedy konta są usuwane: **Po przekroczeniu progu przestrzeni dyskowej**, **Po przekroczeniu progu przestrzeni dyskowej i czasu nieaktywności** lub **Natychmiast po wylogowaniu**. Wprowadź też następujące ustawienia:
    - **Próg rozpoczęcia usuwania (%)**: Wprowadź wartość procentową miejsca na dysku (od 0 do 100). Gdy łączna ilość miejsca na dysku/w pamięci urządzenia spadnie poniżej wprowadzonej wartości, konta zostaną usunięte z pamięci podręcznej. Konta są usuwane w trybie ciągłym w celu odzyskiwania miejsca dyskowego. Konta, które są nieaktywne najdłużej, są usuwane w pierwszej kolejności.
    - **Próg zatrzymania usuwania (%)**: Wprowadź wartość procentową miejsca na dysku (od 0 do 100). Gdy łączna ilość miejsca na dysku/w pamięci urządzenia będzie odpowiadać wprowadzonej wartości, proces usuwania zostanie zatrzymany.

  Ustaw w pozycji **Wyłącz**, aby zachować konta lokalne, konta usługi AD oraz Azure AD utworzone przez gości.

  > [!NOTE]
  > Urządzenia Microsoft HoloLens obsługują tylko ustawienia **Zarządzania kontami**.

## <a name="next-steps"></a>Następne kroki

- [Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).
- Zobacz ustawienia dla systemu [Windows 10 i nowszego](shared-user-device-settings-windows.md).
