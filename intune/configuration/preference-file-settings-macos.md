---
title: Dodawanie ustawień pliku preferencji do urządzeń z systemem macOS w usłudze Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Dodaj plik XML lub plist zawierający najważniejsze informacje o aplikacji. Profil konfiguracji urządzenia pliku preferencji służy do zmieniania informacji o kluczach w pliku listy właściwości i przypisywania go do urządzeń z systemem macOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/09/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d226a5b8ee448b7b168a03fe6b8a1c63bc1be432
ms.sourcegitcommit: 8f56220e7cafc5bc43135940575a9acb5afde730
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 01/09/2020
ms.locfileid: "75827789"
---
# <a name="add-a-property-list-file-to-macos-devices-using-microsoft-intune"></a>Dodaj plik listy właściwości do urządzeń macOS za pomocą Microsoft Intune

Za pomocą Microsoft Intune można dodać plik listy właściwości (. plist) dla urządzeń macOS lub aplikacji na urządzeniach macOS.

Ta funkcja ma zastosowanie do:

- Urządzenia z systemem macOS 10.7 i nowszym

Pliki listy właściwości zazwyczaj zawierają informacje o aplikacjach macOS. Aby uzyskać więcej informacji, zobacz [informacji o plikach listy właściwości](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) (witryna firmy Apple) i [ustawieniach niestandardowych ładunku](https://support.apple.com/guide/mdm/custom-mdm9abbdbe7/1/web/1).

W tym artykule wymieniono i opisano różne ustawienia plików listy właściwości, które można dodać do urządzeń macOS. W ramach rozwiązania do zarządzania urządzeniami przenośnymi (MDM) Użyj tych ustawień, aby dodać identyfikator pakietu aplikacji (`com.company.application`), a następnie Dodaj plik. plist.

Te ustawienia są dodawane do profilu konfiguracji urządzenia w usłudze Intune, a następnie przypisywane lub wdrażane na urządzeniach z systemem macOS.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil](device-profile-create.md).

## <a name="what-you-need-to-know"></a>Co musisz wiedzieć

- Te ustawienia nie są weryfikowane. Pamiętaj o przetestowaniu zmian przed przypisaniem profilu do urządzeń.
- Jeśli nie masz pewności, jak wprowadzić klucz aplikacji, Zmień ustawienie w aplikacji. Następnie przejrzyj plik preferencji aplikacji przy użyciu [Xcode](https://developer.apple.com/xcode/), aby zobaczyć, jak to ustawienie jest skonfigurowane. Firma Apple zaleca usunięcie niezarządzanych ustawień przy użyciu Xcode przed zaimportowaniem pliku.
- Tylko niektóre aplikacje obsługują preferencje zarządzane. Aplikacje te mogą nie zezwalać na zarządzanie wszystkimi ustawieniami.
- Upewnij się, że przekazano pliki listy właściwości, które są docelowymi ustawieniami kanału urządzenia, a nie z ustawieniami kanału użytkownika. Pliki listy właściwości są przeznaczone dla całego urządzenia.

## <a name="preference-file"></a>Plik preferencji

- **Nazwa domeny preferencji**: pliki list właściwości są zwykle używane w przeglądarkach sieci Web (Microsoft Edge), [usługi Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac)i aplikacjach niestandardowych. Podczas tworzenia domeny preferencji tworzony jest również identyfikator pakietu. Wprowadź identyfikator pakietu, taki jak `com.company.application`. Na przykład wpisz `com.Contoso.applicationName`, `com.Microsoft.Edge` lub `com.microsoft.wdav`.
- **Pliku listy właściwości**: Wybierz plik listy właściwości skojarzony z Twoją aplikacją. Upewnij się, że jest to plik `.plist` lub `.xml`. Na przykład Przekaż plik `YourApp-Manifest.plist` lub `YourApp-Manifest.xml`.
- **Zawartość pliku**: wyświetlane są informacje o kluczu z pliku listy właściwości. Jeśli potrzebujesz zmienić informacje o kluczu, Otwórz plik listy w innym edytorze, a następnie Przekaż go ponownie w usłudze Intune.

Upewnij się, że plik jest poprawnie sformatowany. Plik powinien zawierać tylko pary klucz-wartość i nie powinien być opakowany w `<dict>`, `<plist>`ani tagów `<xml>`. Na przykład plik listy właściwości powinien wyglądać podobnie do następującego pliku:

```xml
<key>SomeKey</key>
<string>someString</string>
<key>AnotherKey</key>
<false/>
...
```

Wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany. Profil zostanie utworzony i wyświetlony na liście profilów.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. W dalszej części [przypiszesz profil](device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).

Aby uzyskać więcej informacji na temat plików preferencji dla przeglądarki Microsoft Edge, zobacz [konfigurowania ustawień zasad programu Microsoft Edge w](https://docs.microsoft.com/deployedge/configure-microsoft-edge-on-mac)macOS.
