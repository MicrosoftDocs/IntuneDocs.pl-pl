---
title: Przygotowywanie aplikacji do zarządzania aplikacjami mobilnymi za pomocą usługi Microsoft Intune
description: Informacje przedstawione w tym temacie ułatwiają określenie, kiedy należy używać narzędzia opakowującego aplikację i zestawu SDK aplikacji w celu umożliwienia niestandardowym aplikacjom biznesowym użycia zasad zarządzania aplikacjami mobilnymi.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/19/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: f3addd79b20c685c5643a2b99fb7120e958cdecb
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2019
ms.locfileid: "58394885"
---
# <a name="prepare-line-of-business-apps-for-app-protection-policies"></a>Przygotowanie aplikacji biznesowych pod kątem zasad ochrony aplikacji

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

W swoich aplikacjach możesz umożliwić korzystanie z zasad ochrony aplikacji przez użycie narzędzia opakowującego aplikacje usługi Intune lub zestawu Intune App SDK. Poniżej przedstawiono informacje dotyczące tych dwóch metod oraz sytuacji, w których należy je stosować.

## <a name="intune-app-wrapping-tool"></a>Narzędzia opakowujące aplikacje usługi Intune
Narzędzia opakowujące aplikacje jest używane głównie dla **wewnętrznych** aplikacji biznesowych. Narzędzie to jest aplikacją wiersza polecenia tworzącą otokę wokół aplikacji, która następnie umożliwia zarządzanie aplikacją przez zasady ochrony aplikacji usługi Intune. Jeśli ochronę aplikacji zapewnia niezależny dostawca oprogramowania (ISV, independent software vendor), ważne jest, aby wyjaśnić, czy dostawca ISV będzie nadal obsługiwać opakowaną aplikację.

Do korzystania z narzędzia nie potrzeba kodu źródłowego, ale potrzebne będą poświadczenia podpisywania. Aby uzyskać więcej informacji na temat poświadczeń podpisywania, zobacz [blog usługi Intune](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/). Aby uzyskać informacje na temat dokumentacji dotyczącej narzędzia opakowującego aplikacje, zobacz [Narzędzie opakowujące aplikacje systemu Android](app-wrapper-prepare-android.md) i [Narzędzie opakowujące aplikacje systemu iOS](app-wrapper-prepare-ios.md).

Narzędzie opakowujące aplikacje **nie** obsługuje aplikacji w sklepie Apple App Store ani w sklepie Google Play. Ponadto nie obsługuje niektórych funkcji wymagających integracji deweloperskiej (zobacz poniższą tabelę zawierającą porównanie funkcji).

Aby uzyskać więcej informacji o narzędziu opakowującym aplikacje na potrzeby zasad ochrony aplikacji na urządzeniach niezarejestrowanych w usłudze Intune, zobacz [Ochrona aplikacji biznesowych i danych na urządzeniach niezarejestrowanych w usłudze Microsoft Intune](apps-add.md).

### <a name="reasons-to-use-the-app-wrapping-tool"></a>Powody do korzystania z narzędzia opakowującego aplikacje
* Twoja aplikacja nie ma wbudowanych funkcji ochrony danych
* Twoja aplikacja jest prosta
* Twoja aplikacja jest wdrażana wewnętrznie
* Nie masz dostępu do kodu źródłowego aplikacji.
* Aplikacja nie jest Twojego autorstwa
* Twoja aplikacja ma minimalne możliwości w zakresie uwierzytelniania użytkowników

### <a name="supported-app-development-platforms"></a>Obsługiwane platformy tworzenia aplikacji

|**Narzędzie opakowujące aplikacje** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |Tak|Tak|
|**Android**|Nie — użyj [powiązań platformy Xamarin dla zestawu Intune App SDK](app-sdk-xamarin.md).|Tak|

## <a name="intune-app-sdk"></a>Zestaw SDK aplikacji usługi Intune
Zestaw SDK aplikacji jest przeznaczony głównie dla klientów, których aplikacje znajdują się w sklepie Apple App Store lub sklepie Google Play i którzy chcą zarządzać aplikacjami za pomocą usługi Intune. Korzyści wynikające z integracji zestawu SDK są jednak dostępne dla wszystkich aplikacji, nawet aplikacji biznesowych.

Aby dowiedzieć się więcej o zestawie SDK, zobacz [Przegląd](app-sdk.md). Aby zacząć korzystać z zestawu SDK, zobacz [Wprowadzenie do zestawu SDK aplikacji usługi Microsoft Intune](app-sdk-get-started.md).

### <a name="reasons-to-use-the-sdk"></a>Powody korzystania z zestawu SDK
* Twoja aplikacja nie ma wbudowanych funkcji ochrony danych
* Twoja aplikacja jest złożona i zawiera wiele środowisk
* Twoja aplikacja jest dostępna w publicznym sklepie z aplikacjami, takim jak Google Play lub App Store firmy Apple
* Jesteś deweloperem aplikacji i masz wiedzę techniczną do korzystania z zestawu SDK
* Twoja aplikacja jest zintegrowana z innymi zestawami SDK
* Twoja aplikacja jest często aktualizowana

### <a name="supported-app-development-platforms"></a>Obsługiwane platformy tworzenia aplikacji

|**Zestaw SDK aplikacji usługi Intune** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|Tak — użyj [powiązań platformy Xamarin dla zestawu Intune App SDK](app-sdk-xamarin.md).|Nie|
|**Android**| Tak — użyj [powiązań platformy Xamarin dla zestawu Intune App SDK](app-sdk-xamarin.md).|Nie|

## <a name="feature-comparison"></a>Porównanie funkcji
W tej tabeli przedstawiono ustawienia do użycia w przypadku zestawu SDK aplikacji i narzędzia opakowującego aplikacje.

> [!NOTE]
> Narzędzie opakowujące aplikacje może być stosowane z autonomiczną usługą Intune lub usługą Intune z programem Configuration Manager.

|Funkcja|Zestaw SDK aplikacji|Narzędzie opakowujące aplikacje|
|-----------|---------------------|-----------|
|Ogranicz zawartość sieci Web wyświetlaną w zarządzanej przeglądarce firmowej|X|X|
|Uniemożliwiaj tworzenie kopii zapasowych dla systemu Android, programu iTunes i usługi iCloud|X|X|
|Zezwalaj aplikacji na transfer danych do innych aplikacji|X|X|
|Zezwalaj aplikacji na odbieranie danych z innych aplikacji|X|X|
|Ogranicz wycinanie, kopiowanie i wklejanie w innych aplikacjach|X|X|
|Określ liczbę znaków, które mogą być wycięte lub skopiowane z aplikacji zarządzanej|X|X|
|Wymagaj prostego numeru PIN w celu udzielenia dostępu|X|X|
|Określ liczbę prób przed zresetowaniem numeru PIN|X|X|
|Zezwalaj na odcisk palca zamiast numeru PIN|X|X|
|Zezwalaj na rozpoznawanie twarzy zamiast numeru PIN (tylko system iOS)|X|X|
|Wymagaj poświadczeń firmowych w celu udzielenia dostępu|X|X|
|Blokuj uruchamianie aplikacji zarządzanych na urządzeniach, na których zdjęto zabezpieczenia systemu lub uzyskano dostęp do konta root|X|X|
|Szyfruj dane aplikacji|X|X|
|Ponownie sprawdź wymagania dostępu po upływie określonej liczby minut|X|X|
|Wybierz okres karencji w trybie offline|X|X|
|Zablokuj przechwytywanie ekranu (tylko system Android)|X|X|
|Obsługa zarządzania aplikacjami mobilnymi bez rejestracji urządzenia|X|X|
|Pełne czyszczenie danych aplikacji|X|X|
|Selektywne czyszczenie danych służbowych w scenariuszach obejmujących wiele tożsamości <br><br>**Uwaga:** w systemie iOS usunięcie profilu zarządzania spowoduje również usunięcie aplikacji.|X||
|Nie zezwalaj na używanie polecenia „Zapisz jako”|X||
|Docelowa konfiguracja aplikacji|X||
|Obsługa wielu tożsamości|X||
|Możliwość dostosowywania stylów |X|||
|Połączenia sieci VPN na żądanie aplikacji z użyciem technologii Citrix mVPN|X|X| 
|Wyłącz synchronizację kontaktów|X|X|
|Wyłącz drukowanie|X|X|
|Wymagaj minimalnej wersji aplikacji|X|X|
|Wymagaj minimalnej wersji systemu operacyjnego (systemy iOS i Android)|X|X|
|Wymagaj minimalnej wersji poprawki zabezpieczeń systemu Android (tylko system Android)|X|X|
|Wymagaj minimalnego zestawu SDK usługi Intune dla systemu iOS (tylko system iOS)|X|X|

## <a name="next-steps"></a>Następne kroki

Aby dowiedzieć się więcej na temat zasad ochrony aplikacji i usługi Intune, zobacz następujące tematy:

  - [Narzędzie opakowujące aplikacje systemu Android](app-wrapper-prepare-android.md)<br>
  - [Narzędzie opakowujące aplikacje systemu iOS](app-wrapper-prepare-ios.md)<br>
  - [Używanie zestawu SDK w celu przygotowania aplikacji do zarządzania aplikacjami mobilnymi](app-sdk.md)
