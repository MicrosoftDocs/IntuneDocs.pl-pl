---
title: Dodawanie lub konfigurowanie ustawień usług edukacyjnych w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Użyj aplikacji Take a Test w profilu konfiguracji urządzenia na urządzeniach z systemem Windows 10 lub nowszym w usłudze Microsoft Intune. Utwórz profil konfiguracji, używając ustawień usług edukacyjnych, i wprowadź adres URL aplikacji obsługującej testy, wybierz sposób logowania użytkowników, monitoruj ekran podczas testu oraz zezwalaj na sugestie tekstowe podczas testu lub blokuj je.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/10/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3fc42193b461b8a0364e4ef2a2c34fe3e446ada3
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71724012"
---
# <a name="use-the-take-a-test-app-on-windows-10-devices-in-microsoft-intune"></a>Używanie aplikacji Take a Test na urządzeniach z systemem Windows 10 w usłudze Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Profile edukacyjne w usłudze Intune są przeznaczone dla uczniów, którzy biorą udział w teście lub egzaminie na urządzeniach. Ta funkcja obejmuje aplikację **Take a Test** i ustawienia, które służą do dodawania adresu URL testu, wybierania sposobu logowania użytkowników końcowych do testu i wykonywania innych czynności. Ta funkcja obsługuje następującą platformę:

- System Windows 10 lub nowszy

Gdy użytkownik się zaloguje, w aplikacji Take a Test zostanie automatycznie otwarty test, w którym bierze on udział. W trakcie trwania testu na urządzeniu nie można uruchamiać żadnych innych aplikacji. Dalsze szczegółowe informacje na temat aplikacji Take a Test można znaleźć w temacie [Take tests in Windows 10](https://docs.microsoft.com/education/windows/take-tests-in-windows-10) (Branie udziału w testach w systemie Windows 10).

Ten artykuł zawiera listę kroków tworzenia profilu konfiguracji urządzenia w usłudze Microsoft Intune. Przedstawiono w nim także warte przeczytania i zapamiętania informacje dotyczące dostępnych ustawień usług edukacyjnych dla urządzeń z systemem Windows 10.

## <a name="create-a-device-profile"></a>Tworzenie profilu urządzenia

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Wprowadź następujące właściwości:

    - **Nazwa**: Wprowadź opisową nazwę nowego profilu.
    - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: Wybierz **System Windows 10 lub nowszy**.
    - **Profil**: Wybierz pozycję **Profil edukacji**.

4. Wprowadź ustawienia, które chcesz skonfigurować:

    - [Windows 10 lub nowszy](education-settings-windows.md)

5. Wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany.

Gdy wprowadzisz ustawienia i utworzysz profil, profil będzie wyświetlany na liście profilów. Następnie [przypisz ten profil do grup](device-profile-assign.md).

## <a name="next-steps"></a>Następne kroki

Zapoznaj się z listą [ustawień usług edukacyjnych w systemie Windows 10](education-settings-windows.md) i ich opisami.

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).
