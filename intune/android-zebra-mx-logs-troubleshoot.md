---
title: Użyj StageNow rejestruje na urządzeniach z systemem Android zebry w Microsoft Intune — Azure | Dokumentacja firmy Microsoft
description: Zobacz typowe problemy i rozwiązania, używając StageNow na urządzeniach z systemem Android z usługą Microsoft Intune. Poznasz również sposób pobieranie dzienników i zapoznaj się z przykładami sposobu odczytywania dzienników sukcesów lub błędów.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 36476820805c00cefafcd9f64dd2f08a014762c0
ms.sourcegitcommit: 44095bbd1502b02201a01604531f4105401fbb92
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/27/2019
ms.locfileid: "58490545"
---
# <a name="troubleshoot-and-see-potential-issues-on-android-zebra-devices-in-microsoft-intune"></a>Rozwiązywanie problemów i zobacz potencjalnych problemów na urządzeniach z systemem Android zebry w Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune, można użyć [zebry mobilności rozszerzenia (MX) do zarządzania urządzeniami z systemem Android zebry](android-zebra-mx-overview.md). Podczas korzystania z urządzeń zebry, tworzyć profile w StageNow umożliwia zarządzanie ustawieniami i przekazać je do usługi Intune. Usługa Intune używa aplikacji StageNow stosowania ustawień na urządzeniach. Aplikacja StageNow również tworzy szczegółowy plik dziennika na urządzeniu, które służy do rozwiązywania.

Ta funkcja ma zastosowanie do:

- Android

Na przykład możesz utworzyć profil w StageNow, aby skonfigurować urządzenie. Podczas tworzenia profilu StageNow, ostatnim krokiem generuje plik dla testów profilu. Możesz wykorzystywać ten plik za pomocą aplikacji StageNow na urządzeniu.

W kolejnym przykładzie możesz utworzyć profil w StageNow i przetestować go. W usłudze Intune Dodaj profil StageNow, a następnie przypisać go do urządzeń z systemem zebry. Podczas sprawdzania stanu przypisanego profilu, profil, który przedstawia stan wysokiego poziomu.

W obu przypadkach możesz uzyskać więcej szczegółowych informacji z pliku dziennika StageNow, który jest zapisywany na urządzeniu, za każdym razem, gdy profil StageNow dotyczy.

Niektóre problemy, nie są powiązane z zawartością profilu StageNow i nie są widoczne w dziennikach.

W tym artykule pokazano, jak odczytywać dzienniki StageNow i zawiera listę potencjalnych problemów z urządzeniami zebry, które nie zostaną odzwierciedlone w dziennikach.

[Użyj urządzenia i zarządzać nimi zebry z rozszerzeniami mobilności zebry](android-zebra-mx-overview.md) zawiera więcej informacji na temat tej funkcji.

## <a name="get-the-logs"></a>Pobierz dzienniki

### <a name="use-the-stagenow-app-on-the-device"></a>Za pomocą aplikacji StageNow na urządzeniu
Podczas testowania profilu bezpośrednio na komputerze, zamiast przy użyciu StageNow [usługi Intune na wdrożenie profilu](android-zebra-mx-overview.md#step-4-create-a-device-management-profile-in-stagenow), aplikacja StageNow na urządzeniu zapisuje dzienniki z testu. Aby uzyskać plik dziennika, użyj **więcej (...)**  opcja w aplikacji StageNow na urządzeniu.

### <a name="get-logs-using-android-debug-bridge"></a>Pobieranie dzienników za pomocą mostka debugowania systemu Android
Aby pobieranie dzienników po profil, który jest już wdrożony za pomocą usługi Intune, podłącz urządzenie do komputera przy użyciu [mostka debugowania systemu Android (adb)](https://developer.android.com/studio/command-line/adb) (otwiera witrynę sieci web systemu Android).

Na urządzeniu dzienniki są zapisywane w `/sdcard/Android/data/com.microsoft.windowsintune.companyportal/files`

### <a name="get-logs-from-email"></a>Pobierz dzienniki z wiadomości e-mail
Można pobrać dzienników po profil, który jest już wdrożony za pomocą usługi Intune, użytkownicy końcowi mogą e-mail dzienników przy użyciu aplikacji poczty e-mail na urządzeniu. Na urządzeniu zebry, Otwórz aplikację Portal firmy i [wysyłania dzienników](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android). Za pomocą funkcji Wyślij dzienniki wzrasta, powstaje PowerLift zdarzenia identyfikator, który można odwoływać się jeśli kontaktując się z pomocą techniczną firmy Microsoft.

## <a name="read-the-logs"></a>Odczyt dzienników

Podczas wyszukiwania w dziennikach, występuje błąd, gdy zostanie wyświetlony `<characteristic-error>` tagu. Szczegóły błędu są zapisywane w `<parm-error>` tagu > `desc` właściwości.

## <a name="error-types"></a>Typy błędów

Zebry urządzenia obejmują błąd różne poziomy raportowania:

- Dostawca usług Kryptograficznych nie jest obsługiwane na urządzeniu. Na przykład urządzenie nie komórkowej urządzenia i nie ma Menedżera sieci komórkowej.
- MX lub OS x w wersji jest niezgodny. Każdy dostawca usług Kryptograficznych jest wersjonowany. Dla macierzy pełną pomoc techniczną, zobacz [dokumentacji firmy zebry](http://techdocs.zebra.com/mx/) (otwiera witrynę sieci web firmy zebry).
- Urządzenie raportuje inny problem lub błąd.

## <a name="examples"></a>Przykłady

Na przykład masz poniższy profil danych wejściowych:

```xml
<wap-provisioningdoc>
    <characteristic type="Clock">
        <parm name="AutoTime" value="false"/>
        <parm name="TimeZone" value="GMT-5"/>
        <parm name="Date" value="2014-12-03"/>
        <parm name="Time" value="11:11:11"/>
    </characteristic>
</wap-provisioningdoc>
```

W dzienniku kod XML jest taka sama jak dane wejściowe. Zgodne dane wyjściowe oznacza, że profil pomyślnie zastosowane do urządzeń bez błędów:

```xml
<wap-provisioningdoc>
    <characteristic type="Clock" version="6.0">
        <parm name="AutoTime" value="false"/>
        <parm name="TimeZone" value="GMT-5"/>
        <parm name="Date" value="2014-12-03"/>
        <parm name="Time" value="11:11:11"/>
    </characteristic>
</wap-provisioningdoc>
```

W kolejnym przykładzie masz następujące dane wejściowe:

```xml
<wap-provisioningdoc>
    <characteristic type="XmlMgr" version="4.2" >
        <parm name="ProcessingMode" value="1"/>
    </characteristic>
    <characteristic type="AppMgr" version="4.2" >
        <parm name="Action" value="Install"/>
        <parm name="APK" value="/sdcard/test.apk"/>
    </characteristic>
</wap-provisioningdoc>
```

Dziennik pokazuje błąd, ponieważ zawiera on `<characteristic-error>` tagu. W tym scenariuszu profil, który próbowano zainstalować pakiet dla systemu Android (APK), który nie istnieje w podanej ścieżce:

```xml
<wap-provisioningdoc>
    <characteristic type="XmlMgr" version="4.2">
        <parm name="ProcessingMode" value="1"/>
    </characteristic>
    <characteristic-error type="AppMgr" version="5.1" desc="missing">
        <parm-error name="Action" value="Install" desc="apk doesnot exist in the path"/>
        <parm name="APK" value="/sdcard/test.apk"/>
    </characteristic-error>
</wap-provisioningdoc>
```

## <a name="other-potential-issues-with-zebra-devices"></a>Inne potencjalne problemy z urządzeniami zebry

W tej sekcji przedstawiono inne możliwe problemy, które mogą być widoczne podczas korzystania z urządzeń zebry przy użyciu administratora urządzenia. Problemy te nie są zgłaszane w dziennikach StageNow.

### <a name="android-system-webview-is-out-of-date"></a>Aplikację android System WebView jest nieaktualna

W przypadku starszych urządzeń Zaloguj się przy użyciu aplikacji Portal firmy, użytkownicy mogą zobaczyć komunikat, składnika System WebView jest nieaktualna i musi uaktualnić. Jeśli urządzenie ma zainstalowany sklepu Google Play, połącz go z Internetem i sprawdzenie aktualizacji. Jeśli urządzenie nie ma zainstalowane sklepu Google Play uzyskać zaktualizowaną wersję składnika i zastosować je do urządzeń. Lub aktualizacji do najnowszej urządzenia wystawiony przez zebry systemu operacyjnego.

### <a name="management-actions-take-a-long-time"></a>Akcje z zakresu zarządzania zająć dużo czasu

Jeśli usługi Google Play nie są dostępne, niektóre zadania zająć maksymalnie 8 godzin. [Aplikacja Portal firmy ograniczenia usługi Intune dla systemu Android](https://support.microsoft.com/help/3211588/limitations-of-intune-company-portal-app-for-android-in-china) (otwiera inną witrynę sieci web) mogą być dobry zasobem.

### <a name="device-spoofing-suspected-shows-in-intune"></a>"Urządzenie fałszowania podejrzanych" jest wyświetlane w usłudze Intune

Ten błąd oznacza, że usługa Intune podejrzenia, że inne niż - zebry dla systemu Android urządzenie raportuje jej modelu i producenta urządzenia zebry jako.

### <a name="company-portal-app-is-older-than-minimum-required-version"></a>Aplikacja Portal firmy jest starsza niż minimalna wymagana wersja

Usługa Intune może być aktualizowana minimalną wymaganą wersję aplikacji Portal firmy. Jeśli sklepu Google Play nie jest zainstalowany na urządzeniu, aplikacja Portal firmy nie automatycznie zaktualizowani. Jeśli minimalna wymagana wersja jest nowsza niż wersja zainstalowana, aplikacja Portal firmy przestaje działać. Aktualizacja do najnowszej aplikacji Portal firmy aplikacji przy użyciu [ładowania bezpośredniego na urządzeniach zebry](android-zebra-mx-overview.md#sideload-the-company-portal-app).

## <a name="next-steps"></a>Następne kroki

[Zebry dyskusyjnymi](https://developer.zebra.com/community/home/discussions) (otwiera witrynę sieci web firmy zebry)

[Użyj urządzenia i zarządzać nimi zebry zebry mobilności rozszerzenia w usłudze Intune](android-zebra-mx-overview.md)
