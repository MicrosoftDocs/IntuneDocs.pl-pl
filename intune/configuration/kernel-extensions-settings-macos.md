---
title: macOS ustawień rozszerzenia jądra w Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Dodaj, skonfiguruj lub Utwórz ustawienia na urządzeniach macOS, aby używać rozszerzeń jądra. Ponadto zezwól użytkownikom na przesłanianie zatwierdzonych rozszerzeń, zezwalanie na wszystkie rozszerzenia z identyfikatora zespołu lub zezwalanie na określone rozszerzenia lub aplikacje w Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/10/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8632f5b8df0f483de3bb4d06a6823639ba52c604
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506693"
---
# <a name="macos-device-settings-to-configure-and-use-kernel-extensions-in-intune"></a>macOS ustawień urządzenia w celu konfigurowania i używania rozszerzeń jądra w usłudze Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

W tym artykule wyszczególniono i opisano różne ustawienia rozszerzenia jądra, którymi można zarządzać na urządzeniach z systemem macOS. W ramach rozwiązania do zarządzania urządzeniami przenośnymi (MDM) Użyj tych ustawień, aby dodać rozszerzenia jądra na urządzeniach i zarządzać nimi.

Aby dowiedzieć się więcej o rozszerzeniach jądra w usłudze Intune i wymaganiach wstępnych, zobacz [Dodawanie rozszerzeń jądra macOS](../kernel-extensions-overview-macos.md).

Te ustawienia są dodawane do profilu konfiguracji urządzenia w usłudze Intune, a następnie przypisywane lub wdrażane na urządzeniach z systemem macOS.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji rozszerzeń jądra urządzenia](../kernel-extensions-overview-macos.md).

> [!NOTE]
> Te ustawienia mają zastosowanie do różnych typów rejestracji. Aby uzyskać więcej informacji na temat różnych typów rejestracji, zobacz [Rejestrowanie macOS](../macos-enroll.md).

## <a name="kernel-extensions"></a>Rozszerzenia jądra

### <a name="settings-apply-to-user-approved-automated-device-enrollment"></a>Ustawienia dotyczą: zatwierdzone przez użytkownika, automatyczna rejestracja urządzeń

- **Zezwalaj na zastępowanie użytkowników**: **Zezwalaj użytkownikom na** zatwierdzanie rozszerzeń jądra, które nie znajdują się w profilu konfiguracji. **Nieskonfigurowane** (domyślnie) uniemożliwia użytkownikom Zezwalanie na rozszerzenia, które nie znajdują się w profilu konfiguracji. Oznacza to, że dozwolone są tylko rozszerzenia zawarte w profilu konfiguracji.

  Zobacz [ładowanie rozszerzeń jądra zatwierdzone przez użytkownika](https://developer.apple.com/library/archive/technotes/tn2459/_index.html) (otwiera witrynę sieci Web firmy Apple), aby uzyskać więcej informacji na temat tej funkcji.

- **Dozwolone identyfikatory zespołu**: Użyj tego ustawienia, aby zezwolić na jeden lub wiele identyfikatorów zespołu. Wszystkie rozszerzenia jądra podpisane przy użyciu wprowadzonych identyfikatorów zespołu są dozwolone i zaufane. Inaczej mówiąc, Użyj tej opcji, aby zezwolić na wszystkie rozszerzenia jądra w ramach tego samego identyfikatora zespołu, który może być konkretnym deweloperem lub partnerem.

  **Dodaj** identyfikator zespołu prawidłowych i podpisanych rozszerzeń jądra, które chcesz załadować. Można dodać wiele identyfikatorów zespołu. Identyfikator zespołu musi być alfanumeryczny (litery i cyfry) i może składać się z 10 znaków. Na przykład wprowadź `ABCDE12345`.

  Po dodaniu identyfikatora zespołu można go również usunąć.

  [Znajdź swój identyfikator zespołu](https://help.apple.com/developer-account/#/dev55c3c710c) (otwiera witrynę sieci Web firmy Apple), aby uzyskać więcej informacji.

- **Dozwolone rozszerzenia jądra**: Użyj tego ustawienia, aby zezwolić na określone rozszerzenia jądra. Tylko rozszerzenia jądra są dozwolone lub zaufane. 

  **Dodaj** identyfikator pakietu i identyfikator zespołu rozszerzenia jądra, które chcesz załadować. W przypadku niepodpisanych starszych rozszerzeń jądra użyj pustego identyfikatora zespołu. Można dodać wiele rozszerzeń jądra. Identyfikator zespołu musi być alfanumeryczny (litery i cyfry) i może składać się z 10 znaków. Na przykład wprowadź `com.contoso.appname.macos` dla **identyfikatora pakietu**i `ABCDE12345` dla **identyfikatora zespołu**.

  > [!TIP]
  > Aby uzyskać identyfikator pakietu rozszerzenia jądra (KEXT) na urządzeniu macOS, możesz:
  >
  > 1. W terminalu uruchom `kextstat | grep -v com.apple` i zanotuj dane wyjściowe. Zainstaluj wymagane oprogramowanie lub KEXT. Uruchom ponownie `kextstat | grep -v com.apple` i poszukaj zmian.
  >
  >    W terminalu `kextstat` zawiera listę wszystkich rozszerzeń jądra w systemie operacyjnym. 
  >
  > 2. Na urządzeniu Otwórz plik listy właściwości informacji (info. plist) dla KEXT. Identyfikator pakietu jest wyświetlany. Każdy KEXT ma plik info. plist przechowywany wewnątrz. 

> [!NOTE]
> Nie musisz dodawać identyfikatorów zespołu i rozszerzeń jądra. Można skonfigurować jedną lub drugą.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](../device-profile-assign.md) i [monitorowanie jego stanu](../device-profile-monitor.md).
