---
title: Korzystanie z dzienników StageNow na urządzeniach z systemem Android zebry w Microsoft Intune na platformie Azure | Microsoft Docs
description: Zobacz typowe problemy i rozwiązania dotyczące korzystania z usługi StageNow na urządzeniach z systemem Android przy użyciu Microsoft Intune. Dowiedz się również, jak uzyskać dzienniki, i zapoznać się z przykładami dotyczącymi sposobu odczytywania dzienników pod kątem sukcesu lub błędów.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/26/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e7ed93c86d3fbe7ed7a6ac5d4b1a3494fb55f2bc
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506990"
---
# <a name="troubleshoot-and-see-potential-issues-on-android-zebra-devices-in-microsoft-intune"></a>Rozwiązywanie problemów i wyświetlanie potencjalnych problemów na urządzeniach z systemem Android zebry w Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

W Microsoft Intune można używać [rozszerzeń zebry Mobility (MX) do zarządzania urządzeniami z systemem Android zebry](android-zebra-mx-overview.md). W przypadku korzystania z urządzeń zebry profile można tworzyć w usłudze StageNow, aby zarządzać ustawieniami i przekazywać je do usługi Intune. Usługa Intune używa aplikacji StageNow do zastosowania ustawień na urządzeniach. Aplikacja StageNow tworzy również szczegółowy plik dziennika na urządzeniu używanym do rozwiązywania problemów.

Ta funkcja ma zastosowanie do:

- Android

Na przykład utworzysz profil w usłudze StageNow, aby skonfigurować urządzenie. Po utworzeniu profilu StageNow ostatni krok generuje plik do przetestowania profilu. Ten plik jest zużywany z aplikacją StageNow na urządzeniu.

W innym przykładzie utworzysz profil w StageNow i przetestujesz go. W usłudze Intune Dodaj profil StageNow, a następnie przypisz go do urządzeń zebry. Podczas sprawdzania stanu przypisanego profilu profil pokazuje stan wysokiego poziomu.

W obu tych przypadkach można uzyskać więcej szczegółów z pliku dziennika StageNow, który jest zapisywany na urządzeniu za każdym razem, gdy zostanie zastosowany profil StageNow.

Niektóre problemy nie są związane z zawartością profilu StageNow i nie są uwzględniane w dziennikach.

W tym artykule opisano sposób odczytywania dzienników StageNow oraz inne potencjalne problemy związane z urządzeniami zebry, które mogą nie być odzwierciedlone w dziennikach.

Aby uzyskać więcej informacji na temat tej funkcji [, należy używać urządzeń zebry i zarządzać nimi za pomocą rozszerzeń zebry Mobility](android-zebra-mx-overview.md) .

## <a name="get-the-logs"></a>Pobierz dzienniki

### <a name="use-the-stagenow-app-on-the-device"></a>Korzystanie z aplikacji StageNow na urządzeniu
W przypadku przetestowania profilu bezpośrednio przy użyciu StageNow na komputerze w programie, a nie przy użyciu usługi [Intune w celu wdrożenia profilu](android-zebra-mx-overview.md#step-4-create-a-device-management-profile-in-stagenow), aplikacja StageNow na urządzeniu zapisuje dzienniki z testu. Aby uzyskać plik dziennika, użyj opcji **więcej (...)** w aplikacji StageNow na urządzeniu.

### <a name="get-logs-using-android-debug-bridge"></a>Pobieranie dzienników przy użyciu Android Debug Bridge
Aby pobrać dzienniki po wdrożeniu profilu za pomocą usługi Intune, podłącz urządzenie do komputera z [Android Debug Bridge (ADB)](https://developer.android.com/studio/command-line/adb) (otwiera witrynę sieci Web systemu Android).

Na urządzeniu dzienniki są zapisywane w `/sdcard/Android/data/com.microsoft.windowsintune.companyportal/files`

### <a name="get-logs-from-email"></a>Pobierz dzienniki z poczty e-mail
Aby pobrać dzienniki po wdrożeniu profilu w usłudze Intune, użytkownicy końcowi mogą wysłać dzienniki pocztą e-mail za pomocą aplikacji poczty e-mail na urządzeniu. Na urządzeniu zebry Otwórz aplikację Portal firmy i [Wyślij dzienniki](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android). Za pomocą funkcji Wyślij dzienniki tworzony jest również identyfikator zdarzenia PowerLift, do którego można się odwoływać w przypadku kontaktowania się z pomocą techniczną firmy Microsoft.

## <a name="read-the-logs"></a>Przeczytaj dzienniki

Gdy przeglądasz dzienniki, wystąpi błąd za każdym razem, gdy zobaczysz tag `<characteristic-error>`. Szczegóły błędu są zapisywane w tagu `<parm-error>` > Właściwości `desc`.

## <a name="error-types"></a>Typy błędów

Urządzenia zebry obejmują różne poziomy raportowania błędów:

- Dostawca CSP nie jest obsługiwany na urządzeniu. Na przykład urządzenie nie jest urządzeniem komórkowym i nie ma Menedżera sieci komórkowej.
- Wersja MX lub OSX jest niezgodna. Każdy dostawca usług kryptograficznych jest w wersji. Aby uzyskać pełną matrycę pomocy technicznej, zobacz [dokumentację programu zebry](http://techdocs.zebra.com/mx/) (otwiera witrynę sieci Web zebry).
- Urządzenie zgłasza inny problem lub błąd.

## <a name="examples"></a>Przykłady

Na przykład masz następujący profil wejściowy:

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

W dzienniku plik XML jest identyczny z danymi wejściowymi. To zgodne wyjście oznacza, że profil został pomyślnie zastosowany do urządzenia bez błędów:

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

W innym przykładzie masz następujące dane wejściowe:

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

W dzienniku zostanie wyświetlony komunikat o błędzie, ponieważ zawiera on tag `<characteristic-error>`. W tym scenariuszu w profilu podjęto próbę zainstalowania pakietu systemu Android (APK), który nie istnieje w danej ścieżce:

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

## <a name="other-potential-issues-with-zebra-devices"></a>Inne potencjalne problemy związane z urządzeniami zebry

W tej sekcji wymieniono inne możliwe problemy, które mogą wystąpić podczas korzystania z urządzeń zebry z uprawnieniami administratora urządzenia. Te problemy nie są raportowane w dziennikach StageNow.

### <a name="android-system-webview-is-out-of-date"></a>Android System WebView jest nieaktualna

Gdy starsze urządzenia logują się przy użyciu aplikacji Portal firmy, użytkownicy mogą zobaczyć komunikat informujący, że składnik System WebView jest nieaktualny i wymaga uaktualnienia. Jeśli na urządzeniu zainstalowano Google Play, połącz je z Internetem i Sprawdź aktualizacje. Jeśli na urządzeniu nie zainstalowano Google Play, uzyskaj zaktualizowaną wersję składnika i zastosuj go do urządzeń. Można też zaktualizować do najnowszej wersji systemu operacyjnego urządzenia wydanej przez zebry.

### <a name="management-actions-take-a-long-time"></a>Akcje zarządzania zajmuje dużo czasu

Jeśli usługi Google Play nie są dostępne, wykonanie niektórych zadań trwa dopiero po 8 godzinach. [Ograniczenia Intune — portal firmy aplikacji dla systemu Android](https://support.microsoft.com/help/3211588/limitations-of-intune-company-portal-app-for-android-in-china) (otwiera kolejną witrynę sieci Web firmy Microsoft) mogą być dobrym zasobem.

### <a name="device-spoofing-suspected-shows-in-intune"></a>"Wystąpiło" sfałszowanie urządzenia "w usłudze Intune

Ten błąd oznacza, że usługa Intune podejrzewa, że urządzenie z systemem Android inne niż zebry jest raportowane przez model i producenta jako urządzenie zebry.

### <a name="company-portal-app-is-older-than-minimum-required-version"></a>Aplikacja Portal firmy jest starsza niż minimalna wymagana wersja

Usługa Intune może zaktualizować minimalną wymaganą wersję aplikacji Portal firmy. Jeśli na urządzeniu nie zainstalowano Google Play, aplikacja Portal firmy nie zostanie automatycznie zaktualizowana. Jeśli minimalna wymagana wersja jest nowsza niż zainstalowana wersja, aplikacja Portal firmy przestanie działać. Zaktualizuj do najnowszej aplikacji Portal firmy przy użyciu funkcji [ładowania bezpośredniego na urządzeniach zebry](android-zebra-mx-overview.md#sideload-the-company-portal-app).

## <a name="next-steps"></a>Następne kroki

Tablice [dyskusyjne zebry](https://developer.zebra.com/community/home/discussions) (otwiera witrynę sieci Web zebry)

[Używanie urządzeń Zebra i zarządzanie nimi za pomocą funkcji Zebra Mobility Extensions w usłudze Intune](android-zebra-mx-overview.md)
