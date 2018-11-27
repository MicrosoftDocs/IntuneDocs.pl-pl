---
title: Dodawanie ustawień niestandardowych do urządzeń z systemem iOS w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Wyeksportuj ustawienia systemu iOS z narzędzi Apple Configurator lub Apple Profile Manager, a następnie zaimportuj te ustawienia do usługi Microsoft Intune. Za pomocą tych ustawień można tworzyć, używać i kontrolować funkcje i ustawienia niestandardowe na urządzeniach z systemem iOS. Następnie ten profil niestandardowy można przypisać lub rozpowszechnić do urządzeń z systemem iOS w organizacji, aby utworzyć plan bazowy lub standard.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 4c65b381afaad4b3ba65fa3d8eb49ba8f52b95d1
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52183353"
---
# <a name="use-custom-settings-for-ios-devices-in-microsoft-intune"></a>Używanie ustawień niestandardowych dla urządzeń z systemem iOS w usłudze Microsoft Intune

Za pomocą usługi Microsoft Intune można dodawać lub tworzyć ustawienia niestandardowe dla urządzeń z systemem iOS przy użyciu „profili niestandardowych”. Profile niestandardowe to funkcja w usłudze Intune. Służą one do dodawania ustawień i funkcji urządzeń, które nie są wbudowane w usłudze Intune.

W przypadku korzystania z urządzeń z systemem iOS istnieją dwa sposoby pobrania ustawień niestandardowych do usługi Intune:

- [Program Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12)
- [Program Apple Profile Manager](https://support.apple.com/profile-manager)

Przy użyciu tych narzędzi można wyeksportować ustawienia do profilu konfiguracji. W usłudze Intune można zaimportować ten plik, a następnie przypisać profil do użytkowników systemu iOS i odpowiednich urządzeń. Po przypisaniu ustawienia są rozpowszechniane i tworzą plan bazowy lub standard dla systemu iOS w Twojej organizacji.

W tym artykule pokazano, jak utworzyć profil niestandardowy dla urządzeń z systemem iOS. Zawiera on również pewne wskazówki na temat korzystania z programów Apple Configurator i Apple Profile Manager.

## <a name="before-you-begin"></a>Przed rozpoczęciem

- Jeśli tworzysz profil konfiguracji za pomocą programu **Apple Configurator**, upewnij się, że eksportowane ustawienia są zgodne z wersją systemu iOS na używanych urządzeniach. Aby uzyskać informacje o rozwiązywaniu problemów z niezgodnymi ustawieniami, wyszukaj dokumenty **Configuration Profile Reference** i **Mobile Device Management Protocol Reference** w witrynie internetowej [Apple Developer](https://developer.apple.com/).

- W przypadku używania programu **Apple Profile Manager** wykonaj następujące czynności:

  - Włącz [zarządzania urządzeniami mobilnymi](https://help.apple.com/serverapp/mac/5.7/#/apd05B9B761-D390-4A75-9251-E9AD29A61D0C) w programie Profile Manager.
  - Dodaj [urządzenia z systemem iOS](https://help.apple.com/profilemanager/mac/5.7/#/pm9onzap1984) w programie Profile Manager.
  - Po dodaniu urządzenia w programie Profile Manager przejdź do obszaru **Biblioteka** > **Urządzenia** > wybierz swoje urządzenie > **Ustawienia**. Wprowadź ustawienia ogólne dla tego urządzenia.

    Pobierz i zapisz ten plik. Ten plik zostanie wprowadzony w profilu usługi Intune.

  - Upewnij się, że ustawienia wyeksportowane z programu Apple Profile Manager są zgodne z wersją systemu iOS na używanych urządzeniach. Aby uzyskać informacje o rozwiązywaniu problemów z niezgodnymi ustawieniami, wyszukaj dokumenty **Configuration Profile Reference** i **Mobile Device Management Protocol Reference** w witrynie internetowej [Apple Developer](https://developer.apple.com/).

## <a name="create-the-profile"></a>Tworzenie profilu

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Podaj następujące ustawienia:

    - **Nazwa**: wprowadź nazwę profilu, na przykład `ios custom profile`.
    - **Opis:** wprowadź opis profilu.
    - **Platforma**: wybierz pozycję **iOS**.
    - **Typ profilu**: wybierz pozycję **Niestandardowy**.

4. W polu **Konfiguracja niestandardowa** wprowadź następujące ustawienia:

    - **Nazwa niestandardowego profilu konfiguracji**: wprowadź nazwę zasad. Ta nazwa jest wyświetlana na urządzeniu i w stanie usługi Intune.
    - **Plik profilu konfiguracji**: przejdź do profilu konfiguracji utworzonego przy użyciu programu Apple Configurator lub Apple Profile Manager. Zaimportowany plik jest wyświetlany w obszarze **Zawartość pliku**.

5. Wybierz pozycję **OK** > **Utwórz**, aby utworzyć profil usługi Intune. Po utworzeniu profil będzie widoczny na liście **Konfiguracja urządzenia — profile**.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. Teraz należy [przypisać profil](device-profile-assign.md).

Zobacz jak [utworzyć profil na urządzeniach z systemem macOS](custom-settings-macos.md). 