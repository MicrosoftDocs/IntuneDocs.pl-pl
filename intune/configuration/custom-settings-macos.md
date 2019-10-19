---
title: Dodawanie ustawień niestandardowych do urządzeń z systemem macOS w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Wyeksportuj ustawienia systemu macOS z narzędzi Apple Configurator lub Apple Profile Manager, a następnie zaimportuj te ustawienia do usługi Microsoft Intune. Za pomocą tych ustawień można tworzyć, wykorzystywać i kontrolować niestandardowe funkcje i ustawienia na urządzeniach z systemem macOS. Następnie ten profil niestandardowy można przypisać lub rozpowszechnić do urządzeń z systemem macOS w organizacji, aby utworzyć plan bazowy lub standard.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/26/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5c24c120b033a4db0162e985ef185932dd931eda
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506926"
---
# <a name="use-custom-settings-for-macos-devices-in-microsoft-intune"></a>Używanie ustawień niestandardowych dla urządzeń z systemem macOS w usłudze Microsoft Intune

Za pomocą usługi Microsoft Intune można dodawać lub tworzyć ustawienia niestandardowe dla urządzeń z systemem macOS przy użyciu „profilu niestandardowego”. Profile niestandardowe to funkcja w usłudze Intune. Służą one do dodawania ustawień i funkcji urządzeń, które nie są wbudowane w usłudze Intune.

W przypadku korzystania z urządzeń z systemem macOS istnieją dwa sposoby pobrania ustawień niestandardowych do usługi Intune:

- [Program Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12)
- [Program Apple Profile Manager](https://support.apple.com/profile-manager)

Przy użyciu tych narzędzi można wyeksportować ustawienia do profilu konfiguracji. W usłudze Intune można zaimportować ten plik, a następnie przypisać profil do użytkowników systemu macOS i odpowiednich urządzeń. Po przypisaniu ustawienia są dystrybuowane. Tworzą one również linię bazową lub standard dla macOS w organizacji.

W tym artykule przedstawiono wskazówki dotyczące korzystania z programu Apple Configurator i Menedżera profilów firmy Apple oraz opisano właściwości, które można skonfigurować.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil](device-profile-create.md).

## <a name="what-you-need-to-know"></a>Co musisz wiedzieć

- Jeśli tworzysz profil konfiguracji za pomocą programu **Apple Configurator**, upewnij się, że eksportowane ustawienia są zgodne z wersją systemu macOS na urządzeniach. Aby uzyskać informacje o rozwiązywaniu problemów z niezgodnymi ustawieniami, wyszukaj dokumenty **Configuration Profile Reference** i **Mobile Device Management Protocol Reference** w witrynie internetowej [Apple Developer](https://developer.apple.com/).

- W przypadku używania programu **Apple Profile Manager** wykonaj następujące czynności:

  - Włącz [zarządzania urządzeniami mobilnymi](https://help.apple.com/serverapp/mac/5.7/#/apd05B9B761-D390-4A75-9251-E9AD29A61D0C) w programie Profile Manager.
  - Dodaj [urządzenia z systemem macOS](https://help.apple.com/profilemanager/mac/5.7/#/pm9onzap1984) w programie Profile Manager.
  - Po dodaniu urządzenia w programie Profile Manager przejdź do obszaru **Biblioteka** > **Urządzenia** > wybierz swoje urządzenie > **Ustawienia**. Wprowadź ustawienia ogólne, zabezpieczeń, prywatności, katalogu i certyfikatu dla urządzenia.

    Pobierz i zapisz ten plik. Ten plik zostanie wprowadzony w profilu usługi Intune. 

  - Upewnij się, że ustawienia wyeksportowane z programu Apple Profile Manager są zgodne z wersją systemu macOS na urządzeniach. Aby uzyskać informacje o rozwiązywaniu problemów z niezgodnymi ustawieniami, wyszukaj dokumenty **Configuration Profile Reference** i **Mobile Device Management Protocol Reference** w witrynie internetowej [Apple Developer](https://developer.apple.com/).

## <a name="custom-configuration-profile-settings"></a>Ustawienia niestandardowego profilu konfiguracji

- **Nazwa niestandardowego profilu konfiguracji**: wprowadź nazwę zasad. Ta nazwa jest wyświetlana na urządzeniu i w stanie usługi Intune.
- **Plik profilu konfiguracji**: przejdź do profilu konfiguracji utworzonego przy użyciu programu Apple Configurator lub Apple Profile Manager. Zaimportowany plik jest wyświetlany w obszarze **Zawartość pliku**.

  Możesz również dodać tokeny urządzeń do plików `.mobileconfig`. Tokeny urządzeń służą do dodawania informacji specyficznych dla urządzenia. Aby na przykład wyświetlić numer seryjny, wprowadź `{{serialnumber}}`. Na urządzeniu tekst będzie wyglądać podobnie do `123456789ABC`, który jest unikatowy dla każdego urządzenia. Podczas wprowadzania zmiennych użyj nawiasów klamrowych `{{ }}`. [Tokeny konfiguracji aplikacji](../apps/app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) zawierają listę zmiennych, których można użyć. Możesz też użyć wartości `deviceid` lub innej wartości specyficznej dla urządzenia.

  > [!NOTE]
  > Zmienne nie są weryfikowane w interfejsie użytkownika i uwzględniają wielkość liter. Dlatego mogą pojawić się profile zapisane z niepoprawnymi danymi wejściowymi. Na przykład jeśli podano wartość `{{DeviceID}}` zamiast `{{deviceid}}`, zostanie wyświetlony literał ciągu zamiast unikatowego identyfikatora urządzenia. Upewnij się, że wprowadzono prawidłowe informacje.

Wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany. Profil zostanie utworzony i wyświetlony na liście profilów.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. Teraz należy [przypisać profil](device-profile-assign.md).

Zobacz jak [utworzyć profil na urządzeniach z systemem iOS](../custom-settings-ios.md).
