---
title: Konfigurowanie ustawień programu Endpoint Protection w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Utwórz ustawienia programu Endpoint Protection podczas tworzenia profilu urządzenia z systemem macOS lub Windows 10 w usłudze Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 5/17/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
mr.reviewer: karthib
ms.openlocfilehash: c13c5d71d1ff631d7a3c84cd3f62037569757917
ms.sourcegitcommit: bc5e4dff18f5f9b79077a888f8a58dcc490708c0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/21/2019
ms.locfileid: "65975776"
---
# <a name="add-endpoint-protection-settings-in-intune"></a>Dodawanie ustawień programu Endpoint Protection w usłudze Intune

W usłudze Intune można używać profilów konfiguracji urządzeń do zarządzania typowymi funkcjami zabezpieczeń programu Endpoint Protection na urządzeniach, takimi jak:
- Zapora 
- Funkcja BitLocker
- Zezwalanie na aplikacje i ich blokowanie  
- Usługa Windows Defender i szyfrowanie

Na przykład możesz utworzyć profil programu Endpoint Protection, który umożliwia użytkownikom systemu macOS instalowanie aplikacji wyłącznie ze sklepu Mac App Store. Możesz też włączyć funkcję Windows SmartScreen w przypadku uruchamiania aplikacji na urządzeniach z systemem Windows 10.

Przed utworzeniem profilu zapoznaj się z następującymi artykułami ze szczegółami ustawień programu Endpoint Protection, którymi usługa Intune może zarządzać dla każdej z obsługiwanych platform: 
   - [macOS settings](endpoint-protection-macos.md) (Ustawienia systemu macOS)
   - [Windows 10 settings](endpoint-protection-windows-10.md) (Ustawienia systemu Windows 10)

## <a name="create-a-device-profile-containing-endpoint-protection-settings"></a>Tworzenie profilu urządzenia zawierającego ustawienia programu Endpoint Protection

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=20909).
3. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
4. Wprowadź **Nazwę** i **Opis** dla profilu programu Endpoint Protection.
5. Z listy rozwijanej **Platforma** wybierz platformę urządzenia, do której chcesz zastosować ustawienia niestandardowe. Obecnie dla ustawień ograniczeń dotyczących urządzeń można wybrać jedną z następujących platform:
   - **macOS**
   - **Windows 10 lub nowszy**
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Endpoint Protection**. 
7. Ustawienia, które można skonfigurować, różnią się w zależności od wybranej platformy. Zobacz:
   - [macOS settings](endpoint-protection-macos.md) (Ustawienia systemu macOS)
   - [Windows 10 settings](endpoint-protection-windows-10.md) (Ustawienia systemu Windows 10)  

8. Po skonfigurowaniu odpowiednich ustawień wybierz pozycję **Utwórz** na stronie **Tworzenie profilu**.

   Profil zostanie utworzony i wyświetlony na stronie listy profilów. Aby przypisać ten profil do grup, zobacz [przypisywanie profilów urządzeń](device-profile-assign.md).


## <a name="next-steps"></a>Następne kroki  

Aby przypisać profil do grup, zobacz [przypisywanie profilów urządzeń](device-profile-assign.md).
