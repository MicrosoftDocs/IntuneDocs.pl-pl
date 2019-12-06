---
title: Rozwiązywanie problemów z dziennikami profilów urządzeń Wi-Fi i ich przeglądanie w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Informacje o problemach z profilami konfiguracji urządzeń Wi-Fi oraz ich rozwiązywaniu na urządzeniach z systemami Android, iOS i Windows w usłudze Microsoft Intune. Przejrzyj dzienniki, aby zapoznać się z niektórymi typowymi problemami i możliwymi rozwiązaniami.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: tycast
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 77f5787509438ec3280f29be8449d78979806042
ms.sourcegitcommit: 16a9109b4028589c17695d41271ca4fee8b1d697
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2019
ms.locfileid: "74542666"
---
# <a name="troubleshoot-wi-fi-device-configuration-profiles-in-microsoft-intune"></a>Rozwiązywanie problemów z profilami konfiguracji urządzeń w usłudze Microsoft Intune

W usłudze Intune można tworzyć profile konfiguracji urządzeń, które obejmują ustawienia połączeń sieci Wi-Fi. Te ustawienia służą do łączenia urządzeń użytkowników z systemami Android, iOS i Windows z siecią organizacji.

W tym artykule pokazano, jak wygląda profil sieci Wi-Fi po pomyślnym zastosowaniu na urządzeniach. Zawiera on również informacje dziennika, typowe problemy i wiele innych. Artykuł ten ułatwi Ci rozwiązywanie problemów z profilami sieci Wi-Fi.

Aby uzyskać więcej informacji o profilach sieci Wi-Fi w usłudze Intune, zobacz temat [Dodawanie i używanie ustawień sieci Wi-Fi dla urządzeń](wi-fi-settings-configure.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

W przykładach w tym artykule użyto uwierzytelniania certyfikatu protokołu SCEP dla profilów usługi Intune. Przyjęto również założenie, że zaufane profile główne i SCEP działają poprawnie na urządzeniu.

## <a name="android"></a>Android

W tej sekcji przeprowadzimy Cię przez środowisko użytkownika końcowego podczas instalacji profilów konfiguracji na urządzeniu z systemem Android.

### <a name="end-user-experience-example"></a>Przykład środowiska użytkownika końcowego

W tym scenariuszu jest stosowane urządzenie Nokia 6.1. Przed zainstalowaniem profilu sieci Wi-Fi na urządzeniu należy zainstalować zaufane profile główne i SCEP.

1. Użytkownicy końcowi otrzymają powiadomienie dotyczące konieczności instalacji profilu zaufanego certyfikatu głównego:

    > [!div class="mx-imgBorder"]
    > ![Przykładowe powiadomienie aplikacji Portal firmy w systemie Android dotyczące konieczności zainstalowania profilu zaufanego certyfikatu głównego](./media/troubleshoot-wi-fi-profiles/android-end-user-company-portal-trusted-root.png)

2. Następne powiadomienie zawiera monit dotyczący konieczności instalacji profilu certyfikatu protokołu SCEP:

    > [!div class="mx-imgBorder"]
    > ![Przykładowe powiadomienie aplikacji Portal firmy w systemie Android dotyczące konieczności zainstalowania profilu certyfikatu SCEP](./media/troubleshoot-wi-fi-profiles/android-end-user-company-portal-scep-certificate.png)

    > [!TIP]
    > W przypadku korzystania z urządzenia z systemem Android zarządzanego przez administratora urządzenia lista może zawierać wiele certyfikatów. Po odwołaniu lub usunięciu profilu certyfikatu certyfikat pozostaje na urządzeniu. W tym scenariuszu wybierz najnowszy certyfikat. Zwykle jest to ostatni certyfikat wyświetlany na liście.
    >
    > Ta sytuacja nie występuje w przypadku urządzeń z systemem Android Enterprise ani Samsung Knox. Aby uzyskać więcej informacji, zobacz tematy [Zarządzanie urządzeniami z profilem służbowym systemu Android](../enrollment/android-enterprise-overview.md) i [Usuwanie certyfikatów SCEP i PKCS](../protect/remove-certificates.md#android-knox-devices).

3. Następnie użytkownicy otrzymają powiadomienie dotyczące instalacji profilu sieci Wi-Fi:

    > [!div class="mx-imgBorder"]
    > ![Przykładowe powiadomienie aplikacji Portal firmy w systemie Android dotyczące konieczności zainstalowania profilu certyfikatu SCEP](./media/troubleshoot-wi-fi-profiles/android-end-user-install-wifi-profile.png)

4. Po zakończeniu połączenie Wi-Fi jest wyświetlane jako zapisana sieć:

    > [!div class="mx-imgBorder"]
    > ![Połączenie Wi-Fi wyświetlane jako zapisana sieć](./media/troubleshoot-wi-fi-profiles/android-end-user-saved-networks.png)

### <a name="review-company-portal-app-logs"></a>Przeglądanie dzienników aplikacji Portal firmy

W systemie Android plik **Omadmlog.log** zawiera szczegóły działań profilu sieci Wi-Fi zainstalowanego na urządzeniu. Może istnieć maksymalnie pięć plików dziennika Omadmlog. Pamiętaj, aby pobrać znacznik czasu ostatniej synchronizacji, ponieważ ułatwi to znalezienie powiązanych wpisów dziennika.

W poniższym przykładzie użyj narzędzia [CMTrace](https://docs.microsoft.com/configmgr/core/support/cmtrace), aby odczytać dzienniki, a następnie wyszukaj ciąg „wifimgr”:

> [!div class="mx-imgBorder"]
> ![Połączenie Wi-Fi wyświetlane jako zapisana sieć](./media/troubleshoot-wi-fi-profiles/android-cmtrace-filter-wifimgr.png)

Poniższy dziennik przedstawia wyniki wyszukiwania i pokazuje, że profil sieci Wi-Fi został pomyślnie zastosowany:

```log
2019-08-01T19:22:46.7340000    VERB    com.microsoft.omadm.platforms.android.wifimgr.WifiProfile    15118    04142    Starting to parse Wifi Profile XML with name '<profile ID>'.
2019-08-01T19:22:46.7490000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Starting to parse OneX from Wifi XML.
2019-08-01T19:22:46.8100000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Completed parsing OneX from Wifi XML.
2019-08-01T19:22:46.8209999    VERB    com.microsoft.omadm.platforms.android.wifimgr.WifiProfile    15118    04142    Completed parsing Wifi Profile XML with name '<profile ID>'.
2019-08-01T19:22:46.8240000    INFO    com.microsoft.omadm.utils.CertificateSelector    15118    04142    Selected ca certificate with alias: 'user:205xxxxx.0' and thumbprint '<thumbprint>'.
2019-08-01T19:22:47.0990000    VERB    com.microsoft.omadm.platforms.android.certmgr.CertificateChainBuilder    15118    04142    Complete certificate chain built with Complete certs.
2019-08-01T19:22:47.1010000    VERB    com.microsoft.omadm.utils.CertUtils    15118    04142    1 cert(s) matched criteria: User<ID>[i:<ID>,17CECEA1D337FAA7D167AD83A8CC7A8FCBF9xxxx;eku:1.3.6.1.5.5.7.3.1,1.3.6.1.5.5.7.3.2]
2019-08-01T19:22:47.1090000    VERB    com.microsoft.omadm.utils.CertUtils    15118    04142    0 cert(s) excluded by criteria:
2019-08-01T19:22:47.1110000    INFO    com.microsoft.omadm.utils.CertificateSelector    15118    04142    Selected client cert with alias 'User<ID>' and requestId 'ModelName=<ModelName>%2FLogicalName_<LogicalName>;Hash=-912418295'.
2019-08-01T19:22:47.4120000    VERB    com.microsoft.omadm.Services    15118    04142    Successfully applied, enabled and saved wifi profile '<profile ID>'
2019-08-01T19:22:47.4240000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Starting to parse OneX from Wifi XML.
2019-08-01T19:22:47.4910000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Completed parsing OneX from Wifi XML.
2019-08-01T19:22:47.4970000    VERB    com.microsoft.omadm.platforms.android.wifimgr.WifiProfile    15118    04142    Starting to parse Wifi Profile XML with name '<profile ID>'.
2019-08-01T19:22:47.5080000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Starting to parse OneX from Wifi XML.
2019-08-01T19:22:47.5820000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Completed parsing OneX from Wifi XML.
2019-08-01T19:22:47.5900000    VERB    com.microsoft.omadm.platforms.android.wifimgr.WifiProfile    15118    04142    Completed parsing Wifi Profile XML with name '<profile ID>'.
2019-08-01T19:22:47.5910000    INFO    com.microsoft.omadm.platforms.android.wifimgr.WifiProfileManager    15118    04142    Applied profile <profile ID>

```

## <a name="ios"></a>iOS

Po zainstalowaniu na urządzeniu profilu sieci Wi-Fi zostanie on wyświetlony w obszarze **Profil zarządzania**:

> [!div class="mx-imgBorder"]
> ![Profil zarządzania na urządzeniu z systemem iOS](./media/troubleshoot-wi-fi-profiles/ios-management-profile.png)

> [!div class="mx-imgBorder"]
> ![Połączenie Wi-Fi wyświetlane jako sieć Wi-Fi na urządzeniu z systemem iOS](./media/troubleshoot-wi-fi-profiles/ios-wifi-connection-in-management-profile.png)

### <a name="review-the-ios-console-and-device-logs"></a>Przeglądanie dzienników konsoli i urządzeń systemu iOS

Na urządzeniach z systemem iOS dziennik aplikacji Portal firmy nie zawiera informacji o profilach sieci Wi-Fi. Aby wyświetlić szczegóły instalacji profilów sieci Wi-Fi, użyj dzienników konsoli/urządzenia:

1. Podłącz urządzenie z systemem iOS do komputera Mac. Przejdź do pozycji **Aplikacje** > **Narzędzia** i otwórz aplikację Konsola.
2. W obszarze **akcji** wybierz opcje **uwzględniania komunikatów informacyjnych** i **uwzględniania komunikatów debugowania**:

    > [!div class="mx-imgBorder"]
    > ![Opcje uwzględniania komunikatów informacyjnych i uwzględniania komunikatów debugowania w aplikacji konsolowej systemu iOS](./media/troubleshoot-wi-fi-profiles/ios-console-app-include-info-messages-debug-messages.png)

3. Odtwórz scenariusz i zapisz dzienniki w pliku tekstowym:

    1. Zaznacz wszystkie komunikaty na bieżącym ekranie: **Edytuj** > **Zaznacz wszystkie**.
    2. Skopiuj komunikaty: **Edytuj** > **Kopiuj**.
    3. Wklej dane dziennika w edytorze tekstów i zapisz plik.

4. Wyszukaj zapisany plik dziennika, aby wyświetlić szczegółowe informacje. Po pomyślnym zainstalowaniu profilu dane wyjściowe wyglądają podobnie do następującego dziennika:

    ```log
    Line 390870: debug    11:19:58.994815 -0400    profiled    Adding dependent www.windowsintune.com.wifi.Contoso to parent Microsoft.Profiles.MDM in domain ManagingProfileToManagedProfile to system\
    Line 390872: debug    11:19:58.995210 -0400    profiled    Adding dependent Microsoft.Profiles.MDM to parent www.windowsintune.com.wifi.Contoso in domain ManagedProfileToManagingProfile to system\
    Line 392346: default    11:19:59.360460 -0400    profiled    Profile \'93www.windowsintune.com.wifi.Contoso\'94 installed.\
    ```

## <a name="windows"></a>Windows

Po zainstalowaniu profilu sieci Wi-Fi na urządzeniu przejdź kolejno do pozycji **Ustawienia** > **Konta** > **Dostęp do zasobów służbowych**. Wybierz konto > **Informacje**:

> [!div class="mx-imgBorder"]
> ![Obszar Dostęp do zasobów służbowych i wybieranie pozycji Informacje na urządzeniu z systemem Windows](./media/troubleshoot-wi-fi-profiles/windows-access-work-school-info.png)

W oknie **obszarów zarządzanych przez firmę Microsoft** jest wyświetlana pozycja **Wi-Fi**:

> [!div class="mx-imgBorder"]
> ![Pozycja Wi-Fi dla systemu Windows wyświetlana w oknie obszarów zarządzanych przez firmę Microsoft](./media/troubleshoot-wi-fi-profiles/windows-wifi-areas-managed-by-microsoft.png)

Aby wyświetlić połączenie Wi-Fi, przejdź do pozycji **Ustawienia** > **Sieć i Internet**  > **Wi-Fi**:

> [!div class="mx-imgBorder"]
> ![Połączenie Wi-Fi wyświetlane jako znana sieć w ustawieniach systemu Windows](./media/troubleshoot-wi-fi-profiles/windows-wifi-connection-known-networks.png)

### <a name="review-event-viewer-logs"></a>Przeglądanie dzienników podglądu zdarzeń

Na urządzeniach z systemem Windows szczegółowe informacje o profilach sieci Wi-Fi są rejestrowane w Podglądzie zdarzeń:

1. Otwórz aplikację **Podgląd zdarzeń**.
2. W menu **Widok** wybierz pozycję **Pokaż dzienniki analityczne i debugowania**.
3. Rozwiń pozycję **Dzienniki aplikacji i usług** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostic-Provider** > **Administrator**

Dane wyjściowe będą podobne do następujących dzienników:

```log
Log Name:      Microsoft-Windows-DeviceManagement-Enterprise-Diagnostics-Provider/Admin
Source:        Microsoft-Windows-DeviceManagement-Enterprise-Diagnostics-Provider
Date:          8/7/2019 8:01:41 PM
Event ID:      1506
Task Category: (1)
Level:         Information
Keywords:      (2)
User:          SYSTEM
Computer:      <Computer Name>
Description:
WiFiConfigurationServiceProvider: Node set value, type: (0x4), Result: (The operation completed successfully.).
```

## <a name="common-issues"></a>Typowe problemy

### <a name="issue-1-the-wi-fi-profile-isnt-deployed-to-the-device"></a>Problem 1. Profil sieci Wi-Fi nie został wdrożony na urządzeniu

- Potwierdź, że profil sieci Wi-Fi został przypisany do prawidłowej grupy:

    1. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję **Urządzenia** > **Profile konfiguracji**.
    2. Wybierz profil > **Przypisania**. Potwierdź, że wybrane grupy są prawidłowe.
    3. W programie Endpoint Manager wybierz pozycję **Rozwiązywanie problemów i pomoc techniczna**. Przejrzyj informacje dotyczące **przypisań**.

- W programie Endpoint Manager wybierz pozycję **Rozwiązywanie problemów i pomoc techniczna**. Potwierdź, że urządzenie można zsynchronizowane z usługą Intune, sprawdzając **czas ostatniego zaewidencjonowania**.

- Jeśli profil sieci Wi-Fi został połączony z zaufanymi profilami głównymi i SCEP, upewnij się, że oba profile zostały wdrożone na urządzeniu. Profil sieci Wi-Fi jest zależny od tych profilów.

- Na urządzeniach z systemem Windows 10 lub nowszym przejrzyj dzienniki informacji diagnostycznych oprogramowania MDM:

  1. Przejdź kolejno do pozycji **Ustawienia** > **Konta** > **Uzyskaj dostęp do miejsca pracy lub nauki**.
  2. Wybierz konto służbowe > **Informacje**.
  3. W dolnej części strony **Ustawienia** wybierz pozycję **Utwórz raport**.
  4. Zostanie otwarte okno pokazujące ścieżkę do plików dziennika. Wybierz pozycję **Eksportuj**.
  5. Przejdź do ścieżki `\Users\Public\Documents\MDMDiagnostics` i wyświetl raport:

      > [!div class="mx-imgBorder"]
      > ![Przykładowe informacje diagnostyczne oprogramowania MDM przedstawiające konfigurację profilu sieci Wi-Fi na urządzeniach z systemem Windows 10](./media/troubleshoot-wi-fi-profiles/windows-mdm-diagnostic-info.png)

  > [!TIP]
  > Aby uzyskać więcej informacji, zobacz temat [Diagnose MDM failures in Windows 10](https://docs.microsoft.com/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10) (Diagnozowanie błędów oprogramowania MDM w systemie Windows 10).

- Jeśli na urządzeniu z systemem Android nie zainstalowano zaufanych profilów głównych ani profilów SCEP, zobaczysz następujący wpis w pliku Omadmlog aplikacji Portal firmy:

  ``` log
  2019-08-01T19:18:13.5120000    INFO    com.microsoft.omadm.platforms.android.wifimgr.WifiProfileManager    15118    04105    Skipping Wifi profile <profile ID> because it is pending certificates.
  ```

  - Jeśli zaufane profile główne i profile SCEP znajdują się na urządzeniu z systemem Android i są zgodne, profil sieci Wi-Fi może nie znajdować się na urządzeniu. Ten problem występuje, gdy dostawca **CertificateSelector** z aplikacji Portal firmy nie odnajdzie certyfikatu zgodnego z określonymi kryteriami. Określone kryteria mogą znajdować się w szablonie certyfikatu lub w profilu certyfikatu SCEP.

    Jeśli odpowiedni certyfikat nie zostanie znaleziony, certyfikaty nie będą instalowane na urządzeniu. Profil sieci Wi-Fi nie jest stosowany, ponieważ nie ma poprawnego certyfikatu. W tym scenariuszu w pliku Omadmlog aplikacji Portal firmy zobaczysz następujący wpis:

    ` Skipping Wifi profile <profile ID> because it is pending certificates.`

    Poniższy przykładowy dziennik przedstawia certyfikaty wykluczane, ponieważ wybrano kryterium rozszerzonego użycia klucza (EKU, Extended Key Usage) **Dowolne przeznaczenie**. Ale certyfikaty przypisane do urządzenia nie mają takiego rozszerzonego użycia klucza:

    ```log
    2018-11-27T21:10:37.6390000    VERB     com.microsoft.omadm.utils.CertUtils      14210    00948    Excluding cert with alias User<ID1> and requestId <requestID1> as it does not have any purpose EKU.
    2018-11-27T21:10:37.6400000    VERB     com.microsoft.omadm.utils.CertUtils      14210    00948    Excluding cert with alias User<ID2> and requestId <requestID2> as it does not have any purpose EKU.
    2018-11-27T21:10:37.6400000    VERB     com.microsoft.omadm.utils.CertUtils      14210    00948    0 cert(s) matched criteria:
    2018-11-27T21:10:37.6400000    VERB     com.microsoft.omadm.utils.CertUtils      14210    00948    2 cert(s) excluded by criteria:
    2018-11-27T21:10:37.6400000    INFO       com.microsoft.omadm.platforms.android.wifimgr.WifiProfileManager       14210                00948     Skipping Wifi profile <profile ID> because it is pending certificates.
    ```

    Poniższy przykład pokazuje profil certyfikatu SCEP wprowadzonym w rozszerzonym użyciu klucza **Dowolne przeznaczenie**. Nie został on jednak wprowadzony w szablonie certyfikatu w urzędzie certyfikacji. Aby rozwiązać ten problem, dodaj opcję **Dowolne przeznaczenie** do szablonu certyfikatu. Możesz również usunąć opcję **Dowolne przeznaczenie** z profilu certyfikatu SCEP.

    > [!div class="mx-imgBorder"]
    > ![Dodawanie opcji Dowolne przeznaczenie do szablonu certyfikatu w urzędzie certyfikacji (system Android)](./media/troubleshoot-wi-fi-profiles/android-add-any-purpose-eku.png)

    > [!div class="mx-imgBorder"]
    > ![Dodawanie opcji Dowolne przeznaczenie profilu konfiguracji certyfikatu SCEP w usłudze Intune (system Android)](./media/troubleshoot-wi-fi-profiles/android-any-purpose-scep-device-config-profile.png)

  - Upewnij się, że wszystkie wymagane certyfikaty w kompletnym łańcuchu certyfikatów znajdują się na urządzeniu z systemem Android. W przeciwnym razie nie można zainstalować profilu sieci Wi-Fi na urządzeniu. Aby uzyskać więcej informacji, zobacz artykuł [Missing intermediate certificate authority](https://developer.android.com/training/articles/security-ssl#MissingCa) (Brakujący pośredni urząd certyfikacji) (otwiera witrynę internetową systemu Android).
  - Odfiltruj plik Omadmlog przy użyciu słów kluczowych, aby wyszukać informacje, takie jak certyfikat używany w profilu sieci Wi-Fi oraz potwierdzenie pomyślnego zastosowania certyfikatu.

    Na przykład użyj narzędzia [CMTrace](https://docs.microsoft.com/sccm/core/support/cmtrace) do odczytania dzienników. Użyj ciągu wyszukiwania w celu odfiltrowania ciągu „wifimgr”:

    > [!div class="mx-imgBorder"]
    > ![Filtrowanie przy użyciu narzędzia CMTrace w celu wyszukiwania profilów konfiguracji WiFiMgr na urządzeniach z systemem Android](./media/troubleshoot-wi-fi-profiles/cmtrace-filter-wifimgr.png)

    Dane wyjściowe będą podobne do poniższego dziennika:

    > [!div class="mx-imgBorder"]
    > ![Przykładowe dane wyjściowe dziennika narzędzia CMTrace, które pokazują profil konfiguracji usługi Intune dla sieci WiFi pomyślnie zastosowany na urządzeniach](./media/troubleshoot-wi-fi-profiles/cmtrace-sample-log-output.png)

    Jeśli zobaczysz w dzienniku błąd, skopiuj znacznik czasu tego błędu i usuń filtrowanie dziennika. Następnie użyj opcji „find” (znajdź) ze znacznikiem czasu, aby zobaczyć, co się stało przed błędem.

### <a name="issue-2-the-wi-fi-profile-is-deployed-to-the-device-but-the-device-cant-connect-to-the-network"></a>Problem 2. Profil sieci Wi-Fi został wdrożony na urządzeniu, ale urządzenie nie może nawiązać połączenia z siecią

Zazwyczaj ten problem jest spowodowany przez elementy spoza usługi Intune. Następujące zadania mogą pomóc w zrozumieniu i rozwiązywaniu problemów z łącznością:

- Połącz się ręcznie z siecią przy użyciu certyfikatu z tymi samymi kryteriami, które znajdują się w profilu sieci Wi-Fi.

  Jeśli możesz nawiązać połączenie, przyjrzyj się właściwościom certyfikatu w połączeniu ręcznym. Następnie zaktualizuj profil sieci Wi-Fi usługi Intune przy użyciu tych samych właściwości certyfikatu.
- Błędy łączności są zwykle rejestrowane w dzienniku serwera usługi RADIUS. Na przykład powinien on zawierać informacje o tym, że urządzenie próbowało nawiązać połączenie z profilem sieci Wi-Fi.

## <a name="need-more-help"></a>Dodatkowa pomoc

- Skorzystaj z [forów użytkowników usługi Intune](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc) lub [uzyskać pomoc techniczną od firmy Microsoft](../fundamentals/get-support.md).

- Aby uzyskać więcej informacji o profilach sieci Wi-Fi w usłudze Microsoft Intune, zobacz następujące artykuły:

  - Dodawanie ustawień sieci Wi-Fi dla urządzeń z systemem [Android](wi-fi-settings-android.md), [iOS](wi-fi-settings-ios.md) oraz [Windows 10 i nowszym](wi-fi-settings-windows.md).
  - [Support Tip - How to configure NDES for SCEP certificate deployments in Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-How-to-configure-NDES-for-SCEP-certificate/ba-p/455125) (Porady dotyczące pomocy technicznej — jak skonfigurować usługę NDES dla wdrożeń certyfikatów SCEP w usłudze Intune)
  - Rozwiązywanie problemów z [wdrożeniem profilu certyfikatu protokołu SCEP](https://support.microsoft.com/help/4526725/troubleshooting-scep-profile-deployment-to-android-devices-in-intune) i [konfiguracją usługi NDES](https://support.microsoft.com/help/4459540/troubleshoot-ndes-configuration-for-use-with-intune).

- Najnowsze wiadomości, informacje i porady techniczne można znaleźć w oficjalnych blogach:
  - [Blog zespołu pomocy technicznej usługi Microsoft Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
  - [Blog dotyczący pakietu Microsoft Enterprise Mobility and Security](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/bg-p/enterprisemobilityandsecurity)

## <a name="next-steps"></a>Następne kroki

[Monitoruj profile](device-profile-monitor.md).
