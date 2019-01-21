---
title: Dostosowywanie ekranu blokady w urządzeniach z systemem iOS przy użyciu usługi Microsoft Intune — Azure | Microsoft Docs
titlesuffix: ''
description: Informacje na temat ustawień usługi Microsoft Intune umożliwiających wyświetlanie informacji na ekranie blokady urządzeń z systemem iOS przy użyciu ustawień konfiguracji urządzenia udostępnionego dla systemu iOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/12/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 9f4d75d795421c761398f349c324b498fd21ca01
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203080"
---
# <a name="add-custom-messages-to-lock-screen-and-login-window-on-ios-devices-using-microsoft-intune"></a>Dodawanie niestandardowych komunikatów do ekranu blokady i okna logowania w urządzeniach z systemem iOS za pomocą usługi Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W tym artykule opisano ustawienia usługi Microsoft Intune umożliwiające wyświetlanie informacji na ekranie blokady i w oknie logowania urządzeń z systemem iOS. 

Te ustawienia pozwalają wyświetlać niestandardowe komunikaty lub tekst w oknie logowania i na ekranie blokady. Można na przykład wprowadzić komunikat „W razie zgubienia zwróć do” oraz informacje dotyczące tagu zasobu.

Te ustawienia obsługują nadzorowane urządzenia z systemem iOS w wersji 9.3 i nowszych.

## <a name="create-the-profile"></a>Tworzenie profilu

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, wpisz nazwę usługi **Intune** w filtrze, a następnie wybierz pozycję **Intune**.
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Wprowadź **nazwę** i **opis** profilu.
4. W polu **Platforma** wybierz opcję **iOS**. W polu **Typ profilu** wybierz pozycję **Funkcje urządzenia**.
5. W polu **Ustawienia** wybierz pozycję **Komunikat ekranu blokady (tylko tryb nadzorowany)**. Skonfiguruj następujące ustawienia:

    - **Informacje dotyczące tagu zasobu**: wprowadź informacje o tagu zasobu urządzenia. Na przykład wprowadź `123xyz`.

        Wprowadzony tekst zostanie wyświetlony w oknie logowania i na ekranie blokady w urządzeniu.

    - **Przypis dolny ekranu blokady**: wprowadź informację, która może ułatwić zwrot urządzenia w przypadku jego utraty lub kradzieży. Możesz wprowadzić w polu dowolny tekst. Na przykład wpisz coś takiego: `If found, call Contoso at ...`.

    Możesz też dodać w tych polach informacje dotyczące konkretnych urządzeń za pomocą tokenów urządzeń. Aby na przykład wyświetlić numer seryjny, wprowadź `Serial Number: {{serialnumber}}`. Na ekranie blokady zostanie wyświetlony tekst podobny do tego: `Serial Number 123456789ABC`. Podczas wprowadzania zmiennych użyj nawiasów klamrowych `{{ }}`. [Tokeny konfiguracji aplikacji](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) zawierają listę zmiennych, których można użyć. Możesz też użyć wartości `deviceName` lub innej wartości specyficznej dla urządzenia.

6. Po zakończeniu wybierz pozycję **OK**  >  **OK**  >  **Utwórz**. Twój profil zostanie wyświetlony na liście.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. W dalszej części [przypiszesz profil](device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).
