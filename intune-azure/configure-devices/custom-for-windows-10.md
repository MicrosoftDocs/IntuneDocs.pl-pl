---
title: "Niestandardowe ustawienia usługi Intune dla urządzeń z systemem Windows 10 | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące ustawień, których można używać w niestandardowym profilu systemu Windows 10."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7bcea136-7260-4042-b21b-c7dab86b380d
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0da8c0fe399f76f43439cc66eaecd12bb454f9a6
ms.openlocfilehash: 05856480f8bb76e561f2b459d4ab800f9909a40a


---

# <a name="custom-device-settings-for-windows-10-devices-in-intune-azure-preview"></a>Ustawienia niestandardowe dla urządzeń z systemem Windows 10 w wersji zapoznawczej usługi Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

 Profil **niestandardowy** usługi Microsoft Intune dla systemów Windows 10 i Windows 10 Mobile umożliwia wdrożenie ustawień OMA-URI (Open Mobile Alliance Uniform Resource Identifier), których można użyć do sterowania funkcjami na urządzeniach. System Windows 10 udostępnia wiele ustawień za pomocą [dostawcy usługi konfiguracji zasad](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).

1. Aby rozpocząć pracę, postępuj zgodnie z instrukcjami w artykule [How to configure custom device settings in Microsoft Intune](how-to-configure-custom-settings.md) (Jak skonfigurować niestandardowe ustawienia urządzenia w usłudze Microsoft Intune).
2. W bloku **Tworzenie profilu** wybierz pozycję **Ustawienia**, aby dodać co najmniej jedno ustawienie OMA-URI.
3. W bloku **Ustawienia niestandardowe OMA-URI** kliknij przycisk **Dodaj**, aby dodać nową wartość. Możesz również kliknąć przycisk **Eksportuj**, aby utworzyć listę wszystkich wartości skonfigurowanych w pliku wartości rozdzielanych przecinkami (.csv).
4. Dla każdego ustawienia OMA-URI, które chcesz dodać, wprowadź następujące informacje. Lista w tym temacie zawiera informacje dotyczące ustawień, których można użyć:
    - **Nazwa ustawienia** — Wprowadź unikatową nazwę dla ustawienia OMA-URI, aby ułatwić jego identyfikację na liście ustawień.
    - **Opis** — Opcjonalnie wprowadź opis ustawienia.
    - **Typ danych** — Wybierz spośród opcji:
        - **Ciąg**
        - **Ciąg (XML)**
        - **Data i godzina**
        - **Liczba całkowita**
        - **Liczba zmiennoprzecinkowa**
        - **Wartość logiczna**
    - **OMA-URI (z uwzględnieniem wielkości liter)** — Określ identyfikator OMA-URI, dla którego chcesz podać ustawienie.
    - **Wartość** — Określ wartość, która będzie kojarzona z określonym wcześniej identyfikatorem OMA-URI.
5. Gdy skończysz, wróć do bloku **Utwórz profil** i wybierz pozycję **Utwórz**.
Profil zostanie utworzony i wyświetlony w bloku listy profilów.

## <a name="example"></a>Przykład
Na poniższym zrzucie ekranu ustawienie **Connectivity/AllowVPNOverCellular** jest włączone. Pozwala to urządzeniu z systemem Windows 10 na otwarcie połączenia sieci VPN w sieci komórkowej.

> ![Przykład zasad niestandardowych zawierających ustawienia sieci VPN](./media/custom-policy-example.png)


## <a name="policy-settings"></a>Ustawienia zasad

|Nazwa zasad i identyfikator URI|Szczegóły|
|---------------|------------|-----------|
|**Zezwalaj na automatyczne aktualizacje**<br>./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate|(tylko wersja Desktop)<br>**Typ danych:** liczba całkowita<br />**Wartości:** **0** - **5** (domyślnie: **1**)|
|**Planowany dzień instalacji**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay|(tylko wersja Mobile)<br>**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0** — codziennie (ustawienie domyślne)<br>**1** — niedziela<br>**2** — poniedziałek<br>**3** — wtorek<br>**4** — środa<br>**5** — czwartek<br>**6** — piątek<br>**7** — sobota|
|**Planowana godzina instalacji**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0**–**23** godz. (**0** oznacza północ) (domyślnie: **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword|(tylko wersja Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0** — użytkownik nie może ustawić czasomierza okresu karencji hasła, a wartość jest ustawiana jako „za każdym razem”<br>**1** — użytkownik może ustawić czasomierz okresu karencji hasła (ustawienie domyślne)|
|**WiFi/AllowWiFi**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi|(tylko wersja Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0** — nie zezwalaj na **używanie połączenia Wi-Fi**<br>**1** — **zezwalaj na używanie połączenia Wi-Fi** (ustawienie domyślne)|
|**WiFi/AllowInternetSharing**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing|(wersje Desktop i Mobile)<br>**Typ danych:** liczba całkowita<br />**Wartości:** **0** — nie zezwalaj na udostępnianie Internetu, **1** — zezwalaj na udostępnianie Internetu (wartość domyślna)|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**WiFi/AllowManualWiFiConfiguration**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration|(tylko wersja Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0** — nie jest dozwolone żadne połączenie Wi-Fi poza aprowizowanym przez rozwiązanie MDM.<br>**1** — dodawanie nowych identyfikatorów SSID sieci poza już aprowizowanymi przez rozwiązanie MDM jest dozwolone (ustawienie domyślne)|
|**System/AllowLocation**<br>./Vendor/MSFT/Policy/Config/System/AllowLocation|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**System/AllowTelemetry**<br>./Vendor/MSFT/Policy/Config/System/AllowTelemetry|(wersje Desktop i Mobile)<br>**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0** — niedozwolone (ustawienie tylko dla wersji Enterprise)<br>**1** — ograniczone<br>**2** — pełne (ustawienie domyślne)<br>**3** — pełne i informacje diagnostyczne|
|**System/AllowExperimentation**<br>./Vendor/MSFT/Policy/Config/System/AllowExperimentation|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0** — niedozwolone<br>**1** — tylko ustawienia (ustawienie domyślne)<br>**2** — ustawienia i eksperymenty|
|**Security/AntiTheftMode**<br>./Vendor/MSFT/Policy/Config/Security/AntiTheftMode|(tylko wersja Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0** — nie zezwalaj na tryb antykradzieżowy<br>**1** — preferencja użytkownika (ustawienie domyślne)|
|**Connectivity/AllowUSBConnection**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection|(tylko wersja Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**System/AllowUserToResetPhone**<br>./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone|(tylko wersja Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Connectivity/AllowCellularDataRoaming**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Connectivity/AllowVPNOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0** — używanie sieci VPN z połączeniem komórkowym jest niedozwolone<br>**1** — sieć VPN może używać dowolnego połączenia, w tym komórkowego (ustawienie domyślne)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|(tylko wersja Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|(tylko wersja Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Connectivity/AllowBluetooth**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0** — nie zezwalaj użytkownikowi na włączanie funkcji Bluetooth.<br>**1** — zastrzeżone. Użytkownik może włączać i konfigurować funkcję Bluetooth (nieobsługiwane w przypadku protokołu EAS oraz systemów Windows Phone 8.1 dla rozwiązania MDM, Windows 10 Desktop i Windows 10 Mobile).<br>**2** — dozwolone. Użytkownik może włączać i konfigurować funkcję Bluetooth (ustawienie domyślne)|
|**Experience/AllowScreenCapture**<br>./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture|(tylko wersja Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Experience/AllowTaskSwitcher**<br>./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher|(tylko wersja Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Experience/AllowVoiceRecording**<br>./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording|(tylko wersja Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Experience/AllowSyncMySettings**<br>./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings|(tylko wersja Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — nie zezwalaj na roaming, **1** — zezwalaj na roaming (wartość domyślna)|
|**Experience/AllowManualMDMUnenrollment**<br>./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Accounts/AllowMicrosoftAccountConnection**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Security/AllowManualRootCertificateInstallation**<br>./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation|(tylko wersja Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Security/AllowAddProvisioningPackages**<br>./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Search/DisableBackoff**<br>./Vendor/MSFT/Policy/Config/Search/DisableBackoff|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** (wartość domyślna), **1**|
|**Search/PreventRemoteQueries**<br>./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0**, **1** (wartość domyślna)|
|**Search/AllowUsingDiacritics**<br>./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** (wartość domyślna), **1**|
|**Search/AlwaysUseAutoLangDetection**<br>./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** (wartość domyślna), **1**|
|**Search/DisableRemovableDriveIndexing**<br>./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** (wartość domyślna), **1**|
|**Search/PreventIndexingLowDiskSpaceMB**<br>./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0**, **1** (wartość domyślna)|
|**Search/AllowIndexingEncryptedStoresOrItems**<br>./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** (wartość domyślna), **1**|
|**Security/AllowRemoveProvisioningPackage**<br>./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Security/RequireProvisioningPackageSignature**<br>./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** (wartość domyślna), **1**|
|**AboveLock/AllowActionCenterNotifications**<br>./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**TextInput/AllowIMENetworkAccess**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0** — nie zezwalaj<br>Otwarty słownik rozszerzony jest wyłączony.<br>Użytkownik nie może:<br>— dodać nowego otwartego słownika rozszerzonego,<br />— dodać nowego pliku konfiguracji integracji wyszukiwania,<br>— używać funkcji kandydata z chmury,<br>— wysłać zastrzeżonego słowa użytkownika.<br>**1** — zezwalaj<br>Otwarty słownik rozszerzony może być dodany i używany domyślnie. Domyślnie można również używać funkcji integracji wyszukiwania.<br>Użytkownik może:<br>używać funkcji kandydata z chmury.|
|**TextInput/AllowIMELogging**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0** — rejestrowanie błędów konwersji jest wyłączone.<br>**1** — rejestrowanie błędów konwersji jest włączone (ustawienie domyślne)|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**TextInput/AllowJapaneseIVSCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**TextInput/AllowJapaneseUserDictionary**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0** — żadne znaki nie są filtrowane (ustawienie domyślne)<br>**1** — wszystkie znaki oprócz znaków Shift JIS są filtrowane|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br />**0** — żadne znaki nie są filtrowane (ustawienie domyślne)<br>**1** — wszystkie znaki oprócz znaków JIS0208 są filtrowane|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0** — żadne znaki nie są filtrowane (ustawienie domyślne)<br>**1** — wszystkie znaki oprócz znaków JIS0208 lub EUDC są filtrowane|
|**TextInput/AllowInputPanel**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Bluetooth/AllowDiscoverableMode**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Bluetooth/AllowAdvertising**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Settings/AllowDataSense**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDataSense|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Settings/AllowVPN**<br>./Vendor/MSFT/Policy/Config/Settings/AllowVPN|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Settings/AllowWorkplace**<br>./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Settings/AllowDateTime**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDateTime|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Settings/AllowLanguage**<br>./Vendor/MSFT/Policy/Config/Settings/AllowLanguage|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Settings/AllowRegion**<br>./Vendor/MSFT/Policy/Config/Settings/AllowRegion|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Settings/AllowSignInOptions**<br>./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Settings/AllowYourAccount**<br>./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Settings/AllowPowerSleep**<br>./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Settings/AllowAutoPlay**<br>./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Experience/AllowCortana**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCortana|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Search/SafeSearchPermissions**<br>./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions|(tylko wersja Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0** — ścisłe, najwyższy poziom filtrowania pod kątem blokowania treści dla dorosłych<br>**1** — umiarkowane, średni poziom filtrowania pod kątem blokowania treści dla dorosłych (prawidłowe wyniki wyszukiwania nie będą filtrowane — ustawienie domyślne)|
|**Experience/AllowCopyPaste**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**Wymuś początkowy rozmiar**<br>./Vendor/MSFT/Policy/Config/Start/ForceStartSize|(tylko wersja Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0** — zezwalaj na zmianę rozmiaru przez użytkownika (ustawienie domyślne)<br>**1** — wymuś niepełny ekran<br>**2** — wymuś pełny ekran|
|**Update/RequireDeferUpgrade**<br>./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0**: nie odraczaj uaktualnienia (pozostań w wersji Current Branch — ustawienie domyślne)<br>**1**: zezwalaj na odraczanie aktualizacji i uaktualnień (urządzenie pozostaje zgodne z regułami wersji Current Branch dla firm)<br />Aby uzyskać szczegółowe informacje, zobacz:<br>[Wprowadzenie do obsługi systemu Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Planowanie wdrożenia systemu Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod|(wersje Desktop i Mobile)<br>**Opis:** zasady umożliwiające odroczenie aktualizacji oprogramowania na maksymalnie 4 tygodnie<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br> **0**: zastosuj aktualizacje od razu (ustawienie domyślne)<br>**1**-**4**: liczba tygodni, przez które mają być odroczone aktualizacje oprogramowania<br />Aby uzyskać szczegółowe informacje, zobacz:<br>[Wprowadzenie do obsługi systemu Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Planowanie wdrożenia systemu Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod|(wersje Desktop i Mobile)<br>**Opis:** zasady umożliwiające odroczenie uaktualnień funkcji na maksymalnie 8 miesięcy<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0**: zastosuj aktualizacje od razu (ustawienie domyślne)<br>**1**-**8**: liczba miesięcy, przez które mają być odroczone uaktualnienia funkcji<br />Aby uzyskać szczegółowe informacje, zobacz:<br>[Wprowadzenie do obsługi systemu Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Planowanie wdrożenia systemu Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>./Vendor/MSFT/Policy/Config/Update/PauseDeferrals|(wersje Desktop i Mobile)<br>**Opis:** zezwala na zatrzymanie otrzymywania aktualizacji i uaktualnień przez urządzenie na okres maksymalnie 5 tygodni.<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0**: zastosuj aktualizacje od razu (ustawienie domyślne)<br>**1**: wstrzymaj aktualizacje i uaktualnienia (wygasa po 5 tygodniach)|

## <a name="windows-defender-settings"></a>Ustawienia usługi Windows Defender

|Nazwa zasad i identyfikator URI|Szczegóły|
|---------------|-----------|
|**AllowRealtimeMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**AllowBehaviorMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**AllowIntrusionPreventionSystem**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**AllowIOAVProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**AllowScriptScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**AllowOnAccessProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**RealTimeScanDirection**<br>./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0** — monitoruj wszystkie pliki (wartość domyślna)<br>**1** — monitoruj pliki przychodzące<br>**2** — monitoruj pliki wychodzące|
|**DaysToRetainCleanedMalware**<br>./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0** - **90** — reprezentuje czas zachowywania złośliwego oprogramowania<br>**Wartość domyślna:** **0** — elementy w folderze kwarantanny będą przechowywane w nieskończoność i nie będą usuwane automatycznie|
|**AllowUserUIAccess**<br>./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**ScanParameter**<br>./Vendor/MSFT/Policy/Config/Defender/ScanParameter|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**1** — szybkie skanowanie (ustawienie domyślne)<br>**2** — pełne skanowanie|
|**ScheduleScanDay**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0** — codziennie (ustawienie domyślne)<br>**1** — poniedziałek<br>**2** — wtorek<br>**3** — środa<br>**4** — czwartek<br>**5** — piątek<br>**6** — sobota<br>**7** — niedziela<br>**8** — brak zaplanowanego skanowania|
|**ScheduleScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0** — 0:00<br>**60** — 1:00<br>**120** — 2:00 (ustawienie domyślne)<br>**180** — 3:00<br>**240** — 4:00<br>**300** — 5:00<br>**360** — 6:00<br>**420** — 7:00<br>**480** — 8:00<br>**540** — 9:00<br>**600** — 10:00<br>**660** — 11:00<br>**720** — 12:00<br>**780** — 13:00<br>**840** — 14:00<br>**900** — 15:00<br>**960** — 16:00<br>**1020** — 17:00<br>**1080** — 18:00<br>**1140** — 19:00<br>**1200** — 20:00<br>**1260** — 21:00<br>**1320** — 22:00<br>**1381** — okno obsługi|
|**ScheduleQuickScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime|(tylko wersja Desktop)<br>**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0** — 0:00<br>**60** — 1:00<br>**120** — 2:00 (ustawienie domyślne)<br>**180** — 3:00<br>**240** — 4:00<br>**300** — 5:00<br>**360** — 6:00<br>**420** — 7:00<br>**480** — 8:00<br>**540** — 9:00<br>**600** — 10:00<br>**660** — 11:00<br>**720** — 12:00<br>**780** — 13:00<br>**840** — 14:00<br>**900** — 15:00<br>**960** — 16:00<br>**1020** — 17:00<br>**1080** — 18:00<br>**1140** — 19:00<br>**1200** — 20:00<br>**1260** — 21:00<br>**1320** — 22:00<br>**1380** — 23:00|
|**AVGCPULoadFactor**<br>./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0**–**100** (wartość domyślna: **50**)|
|**AllowArchiveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**AllowEmailScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br>**Wartości:** **0** — niedozwolone (wartość domyślna), **1** — dozwolone|
|**AllowFullScanRemovableDriveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone (wartość domyślna), **1** — dozwolone|
|**AllowFullScanOnMappedNetworkDrives**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**AllowScanningNetworkFiles**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** – niedozwolone, **1** — dozwolone (wartość domyślna) — jeśli dozwolone, jest również uruchamiane przy włączonej ochronie czasu rzeczywistego|
|**SignatureUpdateInterval**<br>./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0** — bez sprawdzania podpisów co określony czas<br>**1** — sprawdzaj sygnatury co godzinę<br>**2** — sprawdzaj co 2 godziny itd.<br>**24** — sprawdzaj codziennie<br>**Wartość domyślna:** 8 — sprawdzaj co 8 godzin|
|**AllowCloudProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — niedozwolone, **1** — dozwolone (wartość domyślna)|
|**SubmitSamplesConsent**<br>./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0** — zawsze pytaj (ustawienie domyślne)<br>**1** — automatycznie wyślij bezpieczne próbki<br>**2** — nigdy nie wysyłaj<br>**3** — wyślij wszystkie próbki automatycznie|
|**ExcludedExtensions**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions|(tylko wersja Desktop)<br />**Typ danych:** ciąg<br />**Wartości:**<br>*&lt;lista rozszerzeń rozdzielonych średnikami&gt;*, na przykład **obj;lib**<br>**Ustawienie domyślne:** brak wykluczonych rozszerzeń|
|**ExcludedPaths**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths|(tylko wersja Desktop)<br />**Typ danych:** ciąg<br />**Wartości:**<br />*&lt;lista ścieżek rozdzielonych średnikami&gt;*<br />Przykład: **c:\test;c:\test1.exe**<br />**Wartość domyślna:** brak wykluczonych ścieżek|
|**ExcludedProcesses**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses|(tylko wersja Desktop)<br />**Typ danych:** ciąg<br />**Wartości:**<br>*&lt;lista ścieżek rozdzielonych średnikami&gt;*<br>Przykład: **c:\test.exe;c:\test1.exe**<br>**Wartość domyślna:** brak wykluczonych procesów|

## <a name="edge-browser-settings"></a>Ustawienia przeglądarki Edge

|Nazwa zasad i identyfikator URI|Szczegóły|
|---------------|------------|-----------|
|**Zezwalaj na przeglądarkę**<br>./Vendor/MSFT/Policy/Config/Browser/AllowBrowser|(tylko wersja Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0**: przeglądanie wyłączone, **1**: przeglądanie włączone (wartość domyślna)|
|**AllowSearchSuggestionsinAddressBar**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0**: nie pokazuj sugestii, **1**: pokaż sugestie (wartość domyślna)|
|**SendIntranetTraffictoInternetExplorer**<br>./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0**: wyłączone (otwieraj witryny intranetowe w przeglądarce Microsoft Edge — ustawienie domyślne)<br>**1**: włączone (otwieraj witryny intranetowe w programie Internet Explorer)|
|**Zezwalaj na żądania Nie śledź**<br>./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — wyłączone (identyfikator DNT nie jest wysyłany — ustawienie domyślne), **1** — włączone (wysyłaj identyfikator DNT)|
|**Skonfiguruj funkcję SmartScreen**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — nie zezwalaj, **1** — zezwalaj (wartość domyślna)|
|**Zezwalaj na wyskakujące okienka**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPopups|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — blokuj wyskakujące okienka (ustawienie domyślne), **1** — zezwalaj na wyskakujące okienka|
|**Zezwalaj na pliki cookie**<br>./Vendor/MSFT/Policy/Config/Browser/AllowCookies|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0** — zezwalaj na pliki cookie z wszystkich witryn sieci Web (wartość domyślna)<br>**1** — blokuj tylko pliki cookie innych firm<br>**2** — blokuj wszystkie pliki cookie|
|**Zezwalaj na zapisywanie haseł**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager|(wersje Desktop i Mobile)<br />**Typ danych:** liczba całkowita<br />**Wartości:**<br>**0** — menedżer haseł jest wyłączony; <br>**1** — menedżer haseł jest włączony (ustawienie domyślne)|
|**Zezwalaj na automatyczne uzupełnianie**<br>./Vendor/MSFT/Policy/Config/Browser/AllowAutofill|(tylko wersja Desktop)<br />**Typ danych:** liczba całkowita<br />**Wartości:** **0** — wyłączone (wartość domyślna), **1** — włączone|
|**Skonfiguruj listę witryn przedsiębiorstwa**<br>./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList|(tylko wersja Desktop)<br />**Typ danych:** ciąg<br />**Wartości:<br>**0** — nieskonfigurowane<br>**1** — użyj listy witryn trybu przedsiębiorstwa IE, jeśli jest skonfigurowana (ustawienie domyślne)<br>**2** — określ lokalizację listy witryn przedsiębiorstwa|



<!--HONumber=Feb17_HO1-->


