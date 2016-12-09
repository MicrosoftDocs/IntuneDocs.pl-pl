---
title: "Przygotowywanie aplikacji do zarządzania aplikacjami mobilnymi | Microsoft Intune"
description: "Informacje przedstawione w tym temacie ułatwiają określenie, kiedy należy używać narzędzia opakowującego aplikację i zestawu SDK aplikacji w celu umożliwienia niestandardowym aplikacjom biznesowym użycia zasad zarządzania aplikacjami mobilnymi."
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ee7e0491c0635c45cbc0377a5de01d5eba851132
ms.openlocfilehash: 3d7b60862942742d663ff23c7b5f3fd135c72640


---

# <a name="decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune"></a>Wybieranie sposobu przygotowania aplikacji do zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune
W aplikacjach można włączyć opcję użycia zasad zarządzania aplikacjami mobilnymi (MAM, Mobile Application Management) za pomocą narzędzia opakowującego aplikacje usługi Intune lub zestawu SDK aplikacji usługi Intune. Poniżej przedstawiono informacje dotyczące tych dwóch metod oraz sytuacji, w których należy je stosować.

## <a name="intune-app-wrapping-tool"></a>Narzędzia opakowujące aplikacje usługi Intune
Narzędzia opakowujące aplikacje jest używane głównie dla wewnętrznych aplikacji biznesowych. To narzędzie jest aplikacją wiersza polecenia tworzącą otokę aplikacji, która następnie umożliwia zarządzanie aplikacją za pośrednictwem zasad MAM usługi Intune.

Do korzystania z narzędzia nie potrzeba kodu źródłowego, ale potrzebne będą poświadczenia podpisywania.  Aby uzyskać więcej informacji na temat poświadczeń podpisywania, zobacz [blog usługi Intune](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/). Aby uzyskać informacje na temat dokumentacji dotyczącej narzędzia opakowującego aplikacje, zobacz [Narzędzie opakowujące aplikacje systemu Android](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) i [Narzędzie opakowujące aplikacje systemu iOS](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

Narzędzie opakowujące aplikacje **nie** obsługuje aplikacji w sklepie Apple App Store ani w sklepie Google Play. Ponadto nie obsługuje niektórych funkcji wymagających integracji deweloperskiej (zobacz poniższą tabelę zawierającą porównanie funkcji).


Aby uzyskać więcej informacji dotyczących narzędzia opakowującego aplikacje do zarządzania aplikacjami mobilnymi na urządzeniach, które nie są zarejestrowane w usłudze Intune, zobacz temat [Chronienie aplikacji biznesowych i danych na niezarejestrowanych urządzeniach w usłudze Microsoft Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

### <a name="reasons-to-use-the-app-wrapping-tool"></a>Powody korzystania z narzędzia opakowującego aplikacje:
* Aplikacja nie ma wbudowanych funkcji ochrony danych.
* Aplikacja jest prosta.
* Aplikacja jest wdrażana wewnętrznie.
* Nie masz dostępu do kodu źródłowego aplikacji.
* Aplikacja nie została utworzona przez Ciebie.
* Aplikacja ma minimalne środowisko uwierzytelniania użytkownika.


### <a name="supported-app-development-platforms"></a>Obsługiwane platformy tworzenia aplikacji

|**Narzędzie opakowujące aplikacje** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |Tak|Tak|
|**Android**| Nie |Tak|

## <a name="intune-app-sdk"></a>Zestaw SDK aplikacji usługi Intune
Zestaw SDK aplikacji jest przeznaczony głównie dla klientów, których aplikacje znajdują się w sklepie Apple App Store lub sklepie Google Play i którzy chcą zarządzać aplikacjami za pomocą usługi Intune. Korzyści wynikające z integracji zestawu SDK są jednak dostępne dla wszystkich aplikacji, nawet aplikacji biznesowych.

Aby dowiedzieć się więcej o zestawie SDK, zobacz [Przegląd](/intune/develop/intune-app-sdk). Aby zacząć korzystać z zestawu SDK, zobacz [Wprowadzenie do zestawu SDK aplikacji usługi Microsoft Intune](/intune/develop/intune-app-sdk-get-started).

### <a name="reasons-to-use-the-sdk"></a>Powody korzystania z zestawu SDK
* Aplikacja nie ma wbudowanych funkcji ochrony danych.
* Aplikacja jest złożona i zawiera wiele środowisk.
* Aplikacja jest wdrażana do publicznego magazynu aplikacji, takiego jak Google Play lub App Store firmy Apple.
* Jesteś twórcą aplikacji i umiesz korzystać z zestawu SDK.
* Aplikacja jest zintegrowana z innymi zestawami SDK.
* Aplikacja jest często aktualizowana.

### <a name="supported-app-development-platforms"></a>Obsługiwane platformy tworzenia aplikacji

|**Zestaw SDK aplikacji usługi Intune** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|Tak — użyj [składnika Xamarin zestawu SDK aplikacji usługi Intune](/../develop/intune-app-sdk-xamarin).|Tak — użyj [wtyczki Cordova zestawu SDK aplikacji usługi Intune](/../develop/intune-app-sdk-cordova).|
|**Android**| Tak — użyj [składnika Xamarin zestawu SDK aplikacji usługi Intune](/../develop/intune-app-sdk-xamarin).|Tak — użyj [wtyczki Cordova zestawu SDK aplikacji usługi Intune](/../develop/intune-app-sdk-cordova).|

## <a name="feature-comparison"></a>Porównanie funkcji
W tej tabeli przedstawiono ustawienia do użycia w przypadku zestawu SDK aplikacji i narzędzia opakowującego aplikacje.

> [!NOTE]
> Narzędzie opakowujące aplikacje może być stosowane z autonomiczną usługą Intune lub usługą Intune z programem Configuration Manager.

|Funkcja|Zestaw SDK aplikacji|Narzędzie opakowujące aplikacje|
|-----------|---------------------|-----------|
|Ogranicz zawartość sieci Web wyświetlaną w zarządzanej przeglądarce firmowej|X|X|
|Nie zezwalaj na kopie zapasowe systemu Android, programu iTunes i usługi iCloud|X|X|
|Zezwalaj aplikacji na transfer danych do innych aplikacji|X|X|
|Zezwalaj aplikacji na odbieranie danych z innych aplikacji|X|X|
|Ogranicz wycinanie, kopiowanie i wklejanie w innych aplikacjach|X|X|
|Wymagaj prostego numeru PIN w celu udzielenia dostępu|X|X|
|Zastąp numer PIN wbudowanej aplikacji numerem PIN usługi Intune|X||
|Określ liczbę prób przed zresetowaniem numeru PIN|X|X|
|Zezwalaj na odcisk palca zamiast numeru PIN |X|X|
|Wymagaj poświadczeń firmowych w celu udzielenia dostępu|X|X|
|Blokuj uruchamianie aplikacji zarządzanych na urządzeniach, na których zdjęto zabezpieczenia systemu lub uzyskano dostęp do konta root|X|X|
|Szyfruj dane aplikacji|X|X|
|Ponownie sprawdź wymagania dostępu po upływie określonej liczby minut|X|X|
|Wybierz okres karencji w trybie offline|X|X|
|Zablokuj przechwytywanie ekranu (tylko system Android)|X|X|
|Pełne czyszczenie|X|X|
|Selektywne czyszczenie <br></br>**Uwaga:** w systemie iOS usunięcie profilu zarządzania spowoduje również usunięcie aplikacji.|X||
|Nie zezwalaj na używanie polecenia „Zapisz jako” |X||
|Obsługa wielu tożsamości|X||
|Obsługa zarządzania aplikacjami mobilnymi bez rejestracji urządzenia|X|X|
|Możliwość dostosowywania stylów |X|||
### <a name="see-also"></a>Zobacz także

[Narzędzie opakowujące aplikacje systemu Android](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Narzędzie opakowujące aplikacje systemu iOS](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Używanie zestawu SDK w celu przygotowania aplikacji do zarządzania aplikacjami mobilnymi](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Dec16_HO2-->


