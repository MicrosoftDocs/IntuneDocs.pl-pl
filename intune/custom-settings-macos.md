---
title: Dodawanie ustawień niestandardowych do urządzeń z systemem macOS w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Wyeksportuj ustawienia systemu macOS z narzędzi Apple Configurator lub Apple Profile Manager, a następnie zaimportuj te ustawienia do usługi Microsoft Intune. Za pomocą tych ustawień można tworzyć, używać i kontrolować funkcje i ustawienia niestandardowe na urządzeniach z systemem macOS. Następnie ten profil niestandardowy można przypisać lub rozpowszechnić do urządzeń z systemem macOS w organizacji, aby utworzyć plan bazowy lub standard.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/23/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b8ce3317bf44e70a64851a0d325e8032d33bab8a
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57566288"
---
# <a name="use-custom-settings-for-macos-devices-in-microsoft-intune"></a>Używanie ustawień niestandardowych dla urządzeń z systemem macOS w usłudze Microsoft Intune

Za pomocą usługi Microsoft Intune można dodawać lub tworzyć ustawienia niestandardowe dla urządzeń z systemem macOS przy użyciu „profilu niestandardowego”. Profile niestandardowe to funkcja w usłudze Intune. Służą one do dodawania ustawień i funkcji urządzeń, które nie są wbudowane w usłudze Intune.

W przypadku korzystania z urządzeń z systemem macOS istnieją dwa sposoby pobrania ustawień niestandardowych do usługi Intune:

- [Program Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12)
- [Program Apple Profile Manager](https://support.apple.com/profile-manager)

Przy użyciu tych narzędzi można wyeksportować ustawienia do profilu konfiguracji. W usłudze Intune można zaimportować ten plik, a następnie przypisać profil do użytkowników systemu macOS i odpowiednich urządzeń. Po przypisaniu ustawienia są rozpowszechniane i tworzą plan bazowy lub standard dla systemu macOS w Twojej organizacji.

W tym artykule pokazano, jak utworzyć profil niestandardowy dla urządzeń z systemem macOS. Zawiera on również pewne wskazówki na temat korzystania z programów Apple Configurator i Apple Profile Manager.

## <a name="before-you-begin"></a>Przed rozpoczęciem

- Jeśli tworzysz profil konfiguracji za pomocą programu **Apple Configurator**, upewnij się, że eksportowane ustawienia są zgodne z wersją systemu macOS na używanych urządzeniach. Aby uzyskać informacje o rozwiązywaniu problemów z niezgodnymi ustawieniami, wyszukaj dokumenty **Configuration Profile Reference** i **Mobile Device Management Protocol Reference** w witrynie internetowej [Apple Developer](https://developer.apple.com/).

- W przypadku używania programu **Apple Profile Manager** wykonaj następujące czynności:

  - Włącz [zarządzania urządzeniami mobilnymi](https://help.apple.com/serverapp/mac/5.7/#/apd05B9B761-D390-4A75-9251-E9AD29A61D0C) w programie Profile Manager.
  - Dodaj [urządzenia z systemem macOS](https://help.apple.com/profilemanager/mac/5.7/#/pm9onzap1984) w programie Profile Manager.
  - Po dodaniu urządzenia w programie Profile Manager przejdź do obszaru **Biblioteka** > **Urządzenia** > wybierz swoje urządzenie > **Ustawienia**. Wprowadź ustawienia ogólne, zabezpieczeń, prywatności, katalogu i certyfikatu dla urządzenia.

    Pobierz i zapisz ten plik. Ten plik zostanie wprowadzony w profilu usługi Intune. 

  - Upewnij się, że ustawienia wyeksportowane z programu Apple Profile Manager są zgodne z wersją systemu macOS na używanych urządzeniach. Aby uzyskać informacje o rozwiązywaniu problemów z niezgodnymi ustawieniami, wyszukaj dokumenty **Configuration Profile Reference** i **Mobile Device Management Protocol Reference** w witrynie internetowej [Apple Developer](https://developer.apple.com/).

## <a name="create-the-profile"></a>Tworzenie profilu

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Podaj następujące ustawienia:

    - **Nazwa**: wprowadź nazwę profilu, na przykład `macos custom profile`.
    - **Opis:** wprowadź opis profilu.
    - **Platforma** wybierz pozycję **macOS**.
    - **Typ profilu**: wybierz pozycję **Niestandardowy**.

4. W polu **Konfiguracja niestandardowa** wprowadź następujące ustawienia:

    - **Nazwa niestandardowego profilu konfiguracji**: wprowadź nazwę zasad. Ta nazwa jest wyświetlana na urządzeniu i w stanie usługi Intune.
    - **Plik profilu konfiguracji**: przejdź do profilu konfiguracji utworzonego przy użyciu programu Apple Configurator lub Apple Profile Manager. Zaimportowany plik jest wyświetlany w obszarze **Zawartość pliku**.

5. Wybierz pozycję **OK** > **Utwórz**, aby utworzyć profil usługi Intune. Po utworzeniu profil będzie widoczny na liście **Konfiguracja urządzenia — profile**.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. Teraz należy [przypisać profil](device-profile-assign.md).

Zobacz jak [utworzyć profil na urządzeniach z systemem iOS](custom-settings-ios.md).
