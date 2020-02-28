---
title: Dodawanie ustawień niestandardowych do urządzeń z systemem iOS/iPadOS w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Wyeksportuj ustawienia systemu iOS i iPadOS z narzędzi Apple Configurator lub Apple Profile Manager, a następnie zaimportuj te ustawienia do usługi Microsoft Intune. Za pomocą tych ustawień można tworzyć, wykorzystywać i kontrolować niestandardowe funkcje i ustawienia na urządzeniach z systemem iOS/iPadOS. Następnie ten profil niestandardowy można przypisać lub rozpowszechnić do urządzeń z systemem iOS/iPadOS w organizacji, aby utworzyć punkt odniesienia lub standard.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8a5dbb56a20d778a0fffc9abde1bc6ce80eb0add
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77513116"
---
# <a name="use-custom-settings-for-ios-and-ipados-devices-in-microsoft-intune"></a>Używanie ustawień niestandardowych dla urządzeń z systemem iOS i iPadOS w usłudze Microsoft Intune

Za pomocą usługi Microsoft Intune można dodawać lub tworzyć ustawienia niestandardowe dla urządzeń z systemem iOS/iPadOS przy użyciu „profilów niestandardowych”. Profile niestandardowe to funkcja w usłudze Intune. Służą one do dodawania ustawień i funkcji urządzeń, które nie są wbudowane w usłudze Intune.

W przypadku korzystania z urządzeń z systemem iOS/iPadOS istnieją dwa sposoby pobrania ustawień niestandardowych do usługi Intune:

- [Program Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12)
- [Program Apple Profile Manager](https://support.apple.com/profile-manager)

Przy użyciu tych narzędzi można wyeksportować ustawienia do profilu konfiguracji. W usłudze Intune można zaimportować ten plik, a następnie przypisać profil do użytkowników systemu iOS/iPadOS i odpowiednich urządzeń. Po przypisaniu ustawienia są dystrybuowane. Tworzą one również punkt odniesienia lub standard dla systemu iOS/iPadOS w organizacji.

W tym artykule przedstawiono wskazówki dotyczące korzystania z programów Apple Configurator i Apple Profile Manager oraz opisano właściwości, które można skonfigurować.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil](device-profile-create.md).

## <a name="what-you-need-to-know"></a>Co musisz wiedzieć

- Jeśli tworzysz profil konfiguracji za pomocą programu **Apple Configurator**, upewnij się, że eksportowane ustawienia są zgodne z wersją systemu iOS/iPadOS na urządzeniach. Aby uzyskać informacje o rozwiązywaniu problemów z niezgodnymi ustawieniami, wyszukaj dokumenty **Configuration Profile Reference** i **Mobile Device Management Protocol Reference** w witrynie internetowej [Apple Developer](https://developer.apple.com/).

- W przypadku używania programu **Apple Profile Manager** wykonaj następujące czynności:

  - Włącz [zarządzania urządzeniami mobilnymi](https://help.apple.com/serverapp/mac/5.7/#/apd05B9B761-D390-4A75-9251-E9AD29A61D0C) w programie Profile Manager.
  - Dodaj [urządzenia z systemem iOS/iPadOS](https://help.apple.com/profilemanager/mac/5.7/#/pm9onzap1984) w programie Profile Manager.
  - Po dodaniu urządzenia w programie Profile Manager przejdź do obszaru **Biblioteka** > **Urządzenia** > wybierz swoje urządzenie > **Ustawienia**. Wprowadź ustawienia ogólne dla tego urządzenia.

    Pobierz i zapisz ten plik. Ten plik zostanie wprowadzony w profilu usługi Intune.

  - Upewnij się, że ustawienia wyeksportowane z programu Apple Profile Manager są zgodne z wersją systemu iOS/iPadOS na urządzeniach. Aby uzyskać informacje o rozwiązywaniu problemów z niezgodnymi ustawieniami, wyszukaj dokumenty **Configuration Profile Reference** i **Mobile Device Management Protocol Reference** w witrynie internetowej [Apple Developer](https://developer.apple.com/).

## <a name="custom-configuration-profile-settings"></a>Ustawienia niestandardowego profilu konfiguracji

- **Niestandardowa nazwa profilu konfiguracji**: Podaj nazwę zasad. Ta nazwa jest wyświetlana na urządzeniu i w stanie usługi Intune.
- **Plik profilu konfiguracji**: przejdź do profilu konfiguracji utworzonego przy użyciu programu Apple Configurator lub Apple Profile Manager. Maksymalny rozmiar pliku to 1 000 000 bajtów (niewiele poniżej 1 MB). Zaimportowany plik jest wyświetlany w obszarze **Zawartość pliku**.

  Możesz również dodać tokeny urządzeń do niestandardowych plików konfiguracji. Tokeny urządzeń służą do dodawania informacji specyficznych dla urządzenia. Aby na przykład wyświetlić numer seryjny, wprowadź `{{serialnumber}}`. Na urządzeniu tekst będzie wyglądać podobnie do następującego: `123456789ABC` (jest on unikatowy dla każdego urządzenia). Podczas wprowadzania zmiennych użyj nawiasów klamrowych `{{ }}`. [Tokeny konfiguracji aplikacji](../apps/app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) zawierają listę zmiennych, których można użyć. Możesz też użyć wartości `deviceid` lub innej wartości specyficznej dla urządzenia.

  > [!NOTE]
  > Zmienne nie są weryfikowane w interfejsie użytkownika i uwzględniają wielkość liter. Dlatego mogą pojawić się profile zapisane z niepoprawnymi danymi wejściowymi. Na przykład jeśli podano wartość `{{DeviceID}}` zamiast `{{deviceid}}`, zostanie wyświetlony literał ciągu zamiast unikatowego identyfikatora urządzenia. Upewnij się, że wprowadzasz odpowiednie informacje.

Wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany. Profil zostanie utworzony i wyświetlony na liście profilów.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. Teraz należy [przypisać profil](device-profile-assign.md).

Zobacz jak [utworzyć profil na urządzeniach z systemem macOS](custom-settings-macos.md). 
