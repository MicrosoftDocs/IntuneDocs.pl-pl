---
title: Konfigurowanie ustawień programu Endpoint Protection w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Utwórz ustawienia programu Endpoint Protection podczas tworzenia profilu urządzenia z systemem macOS lub Windows 10 w usłudze Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 3/27/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8cda293fb337730c936a7fab9b7eadf4816beb67
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57237966"
---
# <a name="add-endpoint-protection-settings-in-intune"></a>Dodawanie ustawień programu Endpoint Protection w usłudze Intune

Program Endpoint Protection umożliwia kontrolowanie różnych funkcji zabezpieczeń na urządzeniach, w tym zapory, funkcji BitLocker, zezwalania i blokowania aplikacji, usługi Windows Defender, szyfrowania i innych. Ustawienia te możesz skonfigurować w usłudze Microsoft Intune przy użyciu profilów urządzeń.

Na przykład możesz utworzyć profil programu Endpoint Protection, który umożliwia użytkownikom systemu macOS instalowanie aplikacji wyłącznie ze sklepu Mac App Store. Możesz też włączyć funkcję Windows SmartScreen w przypadku uruchamiania aplikacji na urządzeniach z systemem Windows 10.

W tym artykule przedstawiono sposób tworzenia profilu. Następnie wybierz platformę urządzeń, aby uzyskać więcej szczegółów o dostępnych ustawieniach.

## <a name="create-a-device-profile-containing-endpoint-protection-settings"></a>Tworzenie profilu urządzenia zawierającego ustawienia programu Endpoint Protection

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
4. Wprowadź **Nazwę** i **Opis** dla profilu programu Endpoint Protection.
5. Z listy rozwijanej **Platforma** wybierz platformę urządzenia, do której chcesz zastosować ustawienia niestandardowe. Obecnie dla ustawień ograniczeń dotyczących urządzeń można wybrać jedną z następujących platform:
   - **macOS**
   - **Windows 10 lub nowszy**
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Endpoint Protection**. 
7. Ustawienia, które można skonfigurować, różnią się w zależności od wybranej platformy. Szczegółowe informacje na temat ustawień każdej z platform podano w następujących tematach:
   - [macOS settings](endpoint-protection-macos.md) (Ustawienia systemu macOS)
   - [Windows 10 settings](endpoint-protection-windows-10.md) (Ustawienia systemu Windows 10)
8. Po zakończeniu wróć na stronę **Utwórz profil** i kliknij pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony na stronie listy profilów. Aby przypisać ten profil do grup, zobacz [przypisywanie profilów urządzeń](device-profile-assign.md).

## <a name="next-steps"></a>Następne kroki
Aby przypisać profil do grup, zobacz [przypisywanie profilów urządzeń](device-profile-assign.md).
