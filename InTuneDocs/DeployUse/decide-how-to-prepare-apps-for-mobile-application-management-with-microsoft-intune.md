---
title: "Przygotowywanie aplikacji do zarządzania aplikacjami mobilnymi | Microsoft Intune"
description: "Informacje przedstawione w tym temacie ułatwiają określenie, kiedy należy używać narzędzia opakowującego aplikację i zestawu SDK aplikacji w celu umożliwienia niestandardowym aplikacjom biznesowym użycia zasad zarządzania aplikacjami mobilnymi."
keywords: 
author: karthikaraman
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
ms.sourcegitcommit: df1b58d5ce94c985e71f3afbe228dba9438040dc
ms.openlocfilehash: d79c498fd775ee9b3d59761fec2fe6ebba116d6d


---

# Wybieranie sposobu przygotowania aplikacji do zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune
W aplikacjach można włączyć opcję użycia zasad zarządzania aplikacjami mobilnymi (MAM, Mobile Application Management) za pomocą narzędzia opakowującego aplikacje usługi Intune lub zestawu SDK aplikacji usługi Intune. Poniżej przedstawiono informacje dotyczące tych dwóch metod oraz sytuacji, w których należy je stosować.

## Narzędzia opakowujące aplikacje usługi Intune
Narzędzia opakowujące aplikacje jest używane głównie dla wewnętrznych aplikacji biznesowych. To narzędzie jest aplikacją wiersza polecenia tworzącą otoku aplikacji, która następnie umożliwia zarządzanie aplikacją za pośrednictwem zasad zarządzania aplikacjami mobilnymi usługi Intune. 

Do korzystania z narzędzia nie potrzeba kodu źródłowego, ale potrzebne będą poświadczenia podpisywania.  Aby uzyskać więcej informacji na temat poświadczeń podpisywania, zobacz [blog usługi Intune](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/). Aby uzyskać informacje na temat dokumentacji dotyczącej narzędzia opakowującego aplikacje, zobacz [Narzędzie opakowujące aplikacje systemu Android](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) i [Narzędzie opakowujące aplikacje systemu iOS](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

Narzędzie opakowujące aplikacje **nie obsługuje** aplikacji ze sklepu Apple App Store i sklepu Google Play ani niektórych opcji, które wymagają integracji deweloperów (skorzystaj z poniższej tabeli z porównaniem opcji).

Jeśli aplikacja została już napisana lub jeśli kod źródłowy jest niedostępny, należy użyć narzędzia opakowującego aplikacje, a nie zestawu SDK.

**Aby uzyskać więcej informacji dotyczących narzędzia opakowującego aplikacje do zarządzania aplikacjami mobilnymi na urządzeniach, które nie są zarejestrowane w usłudze Intune, zobacz temat [Chronienie aplikacji biznesowych i danych na niezarejestrowanych urządzeniach w usłudze Microsoft Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md)**.

### Obsługiwane platformy tworzenia aplikacji

|**Narzędzie opakowujące aplikacje** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |Tak|Tak|
|**Android**| Nie |Tak|

## Zestaw SDK aplikacji usługi Intune
Zestaw SDK aplikacji jest przeznaczony głównie dla klientów, których aplikacje znajdują się w sklepie Apple App Store lub sklepie Google Play i którzy chcą zarządzać aplikacjami za pomocą usługi Intune. Korzyści wynikające z integracji zestawu SDK są jednak dostępne dla wszystkich aplikacji, nawet aplikacji biznesowych.

Aby dowiedzieć się więcej o zestawie SDK, zobacz [Przegląd](/intune/develop/intune-app-sdk). Aby zacząć korzystać z zestawu SDK, zobacz [Wprowadzenie do zestawu SDK aplikacji usługi Microsoft Intune](/intune/develop/intune-app-sdk-get-started).

### Obsługiwane platformy tworzenia aplikacji

|**Zestaw SDK aplikacji usługi Intune** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|Tak — użyj składnika Xamarin zestawu SDK aplikacji usługi Intune|Tak — użyj wtyczki Cordova zestawu SDK aplikacji usługi Intune|
|**Android**| Tak — użyj składnika Xamarin zestawu SDK aplikacji usługi Intune|Tak — użyj wtyczki Cordova zestawu SDK aplikacji usługi Intune|

## Porównanie funkcji
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
|Wymagaj odcisku palca zamiast numeru PIN (tylko system iOS)<br></br>**Uwaga:** dostępne tylko w środowiskach obsługujących wyłącznie zarządzanie aplikacjami mobilnymi.|X||
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
### Zobacz także

[Narzędzie opakowujące aplikacje systemu Android](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Narzędzie opakowujące aplikacje systemu iOS](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Używanie zestawu SDK w celu przygotowania aplikacji do zarządzania aplikacjami mobilnymi](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Sep16_HO4-->


