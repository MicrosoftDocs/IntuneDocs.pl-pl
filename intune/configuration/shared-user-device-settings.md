---
title: Ustawienia urządzeń udostępnionych obsługujących wielu użytkowników w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodaj urządzenia z systemem Windows 10 i Windows Holographic for Business, które są udostępnione, czyli używane przez wielu użytkowników, i korzystaj z nich w usłudze Microsoft Intune. Wyświetl listę wszystkich ustawień i przekonaj się, jak działają na urządzeniach, na przykład urządzeniu Microsoft HoloLens. Profil konfiguracji urządzenia umożliwia kontrolowanie kont gości, zarządzanie kontami, usuwanie kont nieaktywnych, zezwalanie na zapisywanie w magazynie lokalnym lub blokowanie tej możliwości, konfigurowanie opcji zasilania i uśpienia, wybieranie, kiedy mają zostać zainstalowane aktualizacje, oraz korzystanie z urządzeń w środowiskach edukacyjnych.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/09/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: b8dfab31d770c012acf88eb3775313634c3c14cc
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72492304"
---
# <a name="control-access-accounts-and-power-features-on-shared-pc-or-multi-user-devices-using-intune"></a>Kontrola dostępu, konta i funkcje zasilania na udostępnianych komputerach lub urządzeniach obsługujących wielu użytkowników w usłudze Intune

Urządzenia, które mają wielu użytkowników, to tak zwane urządzenia udostępnione. Są często spotykanym elementem rozwiązań do zarządzania urządzeniami mobilnymi. Dzięki usłudze Microsoft Intune można dostosowywać urządzenia udostępnione z następującymi systemami:

- Windows 10 Professional i nowsze wersje
- Windows 10 Enterprise i nowsze wersje
- Windows Holographic for Business, na przykład HoloLens

Na przykład szkoły są zwykle wyposażone w urządzenia używane przez wielu uczniów. Dzięki temu ustawieniu szkolny administrator usługi Intune może włączyć funkcję komputera udostępnionego, aby zezwolić na jednoczesne korzystanie z usługi przez jednego użytkownika. Uczniowie nie mogą przełączać się pomiędzy różnymi zalogowanymi kontami na tym urządzeniu. Po wylogowaniu ucznia możesz również zdecydować się na usunięcie wszystkich ustawień tego użytkownika.

Użytkownicy końcowi mogą logować się na tych urządzeniach udostępnionych za pomocą konta gościa. Po zalogowaniu poświadczenia użytkowników są zapisywane w pamięci podręcznej. Podczas korzystania z urządzenia użytkownicy końcowi mają dostęp tylko do tych funkcji, które im udostępnisz. Możesz na przykład zdecydować, kiedy urządzenie przechodzi w stan uśpienia, czy użytkownicy mogą wyświetlać i zapisywać pliki lokalnie, włączyć lub wyłączyć ustawienia zarządzania zasilaniem i nie tylko. Możesz również kontrolować, czy konto gościa ma zostać usunięte po wylogowaniu się użytkownika, czy też nieaktywne konta mają być usuwane po osiągnięciu określonego progu.

W tym artykule pokazano, jak utworzyć profil konfiguracji, oraz podano linki do dostępnych ustawień wraz z ich opisem.

Po utworzeniu profilu w usłudze Intune możesz wdrożyć lub przypisać profil do grup urządzeń w swojej organizacji. Możesz również przypisać ten profil do grup urządzeń składających się z różnych typów urządzeń i wersji systemu operacyjnego.

## <a name="create-the-profile"></a>Tworzenie profilu

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz kolejno pozycje **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Wprowadź następujące właściwości:

   - **Nazwa**: Wprowadź opisową nazwę nowego profilu.
   - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
   - **Platforma**: Wybierz pozycję **Windows 10 i nowsze**.
   - **Typ profilu**: Wybierz pozycję **Udostępnione urządzenie obsługujące wielu użytkowników**.

4. Skonfiguruj ustawienia dla systemu [Windows 10 lub nowszego](shared-user-device-settings-windows.md) lub systemu [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md).

5. Wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany.

Twój profil został utworzony i jest wyświetlany na liście, ale nie wykonuje jeszcze żadnych działań. Pamiętaj, aby [przypisać profil](device-profile-assign.md) do grupy urządzeń w organizacji.

## <a name="next-steps"></a>Następne kroki

- Zapoznaj się z wszystkimi ustawieniami dla systemu [Windows 10 i nowszych](shared-user-device-settings-windows.md) oraz [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md).
- [Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).
