---
title: Ustawienia kiosku dla systemu Windows Holographic for Business w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Skonfiguruj urządzenia z systemem Windows Holographic for Business jako kioski z pojedynczą aplikacją oraz z wieloma aplikacjami, dostosuj menu Start, dodaj aplikacje i pasek zadań oraz skonfiguruj przeglądarkę internetową w usłudze Microsoft Intune.
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
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8c5fd9998a4816775b3fc1d7803dc26e223b1e39
ms.sourcegitcommit: e5f501b396cb8743a8a9dea33381a16caadc51a9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/23/2019
ms.locfileid: "56742443"
---
# <a name="windows-holographic-for-business-device-settings-to-run-as-a-kiosk-in-intune"></a>Ustawienia urządzeń z systemem Windows Holographic for Business na potrzeby uruchamiania jako kiosku w usłudze Intune

Urządzenia platformy Windows Holographic for Business można skonfigurować tak, aby były uruchamiane w trybie kiosku z jedną aplikacją lub wieloma aplikacjami. Niektóre funkcje nie są obsługiwane na platformie Windows Holographic for Business.

W tym artykule wymieniono i opisano różne ustawienia, które można kontrolować na urządzeniach z systemem Windows Holographic for Business. W ramach rozwiązania do zarządzania urządzeniami przenośnymi (MDM) użyj tych ustawień, aby skonfigurować urządzenia z systemem Windows Holographic for Business do uruchamiania w trybie kiosku.

Jako administrator usługi Intune możesz tworzyć i przypisywać te ustawienia do urządzeń.

Aby dowiedzieć się więcej na temat funkcji kiosku systemu Windows w usłudze Intune, zobacz temat dotyczący [konfigurowania ustawień kiosku](kiosk-settings.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil](kiosk-settings.md#create-the-profile).

## <a name="single-full-screen-app-kiosks"></a>Kioski z pojedynczą aplikacją w trybie pełnoekranowym

W przypadku wybrania trybu kiosku z pojedynczą aplikacją wprowadź następujące ustawienia:

- **Typ logowania użytkownika**: Wybierz pozycję **Konto użytkownika lokalnego**, aby wprowadzić konto użytkownika lokalnego (na urządzenie) lub konto Microsoft skojarzone z aplikacją kiosku. Konta użytkowników typu **Logowanie automatyczne** nie są obsługiwane na platformie Windows Holographic for Business.

- **Typ aplikacji**: Wybierz pozycję **Aplikacja ze Sklepu**.

- **Aplikacja do uruchamiania w trybie kiosku**: Wybierz pozycję **Dodaj aplikację ze sklepu**, a następnie wybierz aplikację z listy.

    Lista nie zawiera żadnych aplikacji? Dodaj aplikacje, wykonując czynności opisane w temacie [Aplikacje klienckie](apps-add.md).

    Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="multi-app-kiosks"></a>Kioski z wieloma aplikacjami

Aplikacje w tym trybie są dostępne w menu Start. Te aplikacje to jedyne aplikacje, które użytkownik może otwierać. W przypadku wybrania trybu kiosku z wieloma aplikacjami wprowadź następujące ustawienia:

- **Określ urządzenia w trybie S z systemem Windows 10 jako docelowe**: Wybierz pozycję **Nie**. Tryb S nie jest obsługiwany na platformie Windows Holographic for Business.

- **Typ logowania użytkownika**: Dodaj co najmniej jedno konta użytkownika, które może używać dodanych aplikacji. Dostępne opcje: 

  - **Logowanie automatyczne**: Ta opcja nie jest obsługiwana na platformie Windows Holographic for Business.
  - **Konta użytkowników lokalnych**: **Dodaj** konto użytkownika lokalnego (w urządzeniu). Wprowadzone konto jest używane do logowania się do kiosku.
  - **Użytkownik lub grupa usługi Azure AD (system Windows 10 w wersji 1803 lub nowszej)**: Wymaga poświadczeń użytkownika w celu zalogowania się na urządzeniu. Wybierz pozycję **Dodaj**, aby wybrać użytkowników lub grupy usługi Azure AD z listy. Można wybrać wielu użytkowników lub wiele grup. Wybierz przycisk **Wybierz**, aby zapisać zmiany.
  - **Odwiedzający platformę HoloLens**: Konto gościa, które nie wymaga żadnych poświadczeń użytkownika ani uwierzytelniania, zgodnie z opisem w sekcji [Pojęcia związane z trybem komputera udostępnionego](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Aplikacje**: Dodaj aplikacje do uruchamiania w urządzeniu kiosku. Pamiętaj, że możesz dodać kilka aplikacji.

  - **Dodaj aplikacje ze Sklepu**: Wybierz istniejącą aplikację, którą dodano za pomocą funkcji [Aplikacje klienckie](apps-add.md). Jeśli lista nie zawiera żadnych aplikacji, możesz pobrać aplikacje i [dodać je do usługi Intune](store-apps-windows.md).
  - **Dodaj aplikację systemu Win32**: Ta opcja nie jest obsługiwana na platformie Windows Holographic for Business.
  - **Dodaj przy użyciu identyfikatora AUMID**: Użyj tej opcji, aby dodać aplikacje skrzynki odbiorczej systemu Windows. Wprowadź następujące właściwości: 

    - **Nazwa aplikacji**: Element wymagany. Wprowadź nazwę aplikacji.
    - **Identyfikator modelu użytkownika aplikacji (AUMID)**: Element wymagany. Wprowadź identyfikator modelu użytkownika aplikacji (AUMID) dla aplikacji systemu Windows. Aby uzyskać ten identyfikator, zobacz [Znajdowanie identyfikatora modelu użytkownika aplikacji zainstalowanej aplikacji](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).
    - **Rozmiar kafelka**: Element wymagany. Wybierz mały, średni, szeroki lub duży rozmiar kafelka aplikacji.

- **Ustawienia przeglądarki kiosku**: Ta opcja nie jest obsługiwana na platformie Windows Holographic for Business.

- **Użyj alternatywnego układu ekranu startowego**: Wybierz pozycję **Tak**, aby wprowadzić plik XML, który opisuje sposób wyświetlania aplikacji w menu Start, w tym ich kolejność. Użyj tej opcji, jeśli potrzebujesz większej liczby dostosowań w menu Start. Artykuł [Customize and export Start layout (Dostosowywanie i eksportowanie układu menu Start)](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-for-hololens) zawiera wskazówki i oraz plik XML przygotowany dla urządzeń platformy Windows Holographic for Business.

- **Pasek zadań systemu Windows**: Ta opcja nie jest obsługiwana na platformie Windows Holographic for Business.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).

Można również utworzyć profile kiosku dla urządzeń z systemem [Android](device-restrictions-android.md#kiosk), [Android Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings) oraz [Windows 10 i nowszymi wersjami](kiosk-settings-windows.md).
