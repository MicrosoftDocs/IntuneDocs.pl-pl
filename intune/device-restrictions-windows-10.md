---
title: Ustawienia ograniczeń urządzeń dla systemu Windows 10 w usłudze Microsoft Intune na platformie Azure | Microsoft Docs
description: Zapoznaj się z listą wszystkich ustawień dotyczących tworzenia ograniczeń dotyczących urządzeń z systemie Windows 10 lub nowszym oraz z ich opisami. Te ustawienia w profilu konfiguracji służą do kontrolowania zrzutów ekranu, wymagań dotyczących haseł, ustawień kiosku, aplikacji w sklepie, przeglądarki Microsoft Edge, usługi Windows Defender, dostępu do chmury, menu Start i innych elementów w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/18/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 30e869cbb0311e1855dd4dc09978505ad539970e
ms.sourcegitcommit: 256952cac44bc6289156489b6622fdc1a3c9c889
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2019
ms.locfileid: "67403090"
---
# <a name="windows-10-and-newer-device-settings-to-allow-or-restrict-features-using-intune"></a>Ustawienia urządzeń z systemem Windows 10 (i nowszym) w celu zezwolenia na funkcje lub ich ograniczenia przy użyciu usługi Intune

W tym artykule wymieniono i opisano wszystkie różne ustawienia, którymi można sterować na urządzeniach z systemem Windows 10 i nowszym. Użyj tych ustawień w ramach swojego rozwiązania do zarządzania urządzeniami mobilnymi (MDM), aby zezwalać na działanie funkcji lub je wyłączać, ustawiać reguły haseł, dostosowywać ekran blokady, korzystać z programu Windows Defender i nie tylko.

Te ustawienia są dodawane do profilu konfiguracji urządzenia w usłudze Intune, a następnie przypisywane lub wdrażane na urządzeniach z systemem Windows 10.

> [!Note]
> Nie wszystkie opcje są dostępne we wszystkich wersjach systemu Windows. Aby poznać obsługiwane wersje, zobacz [Policy CSPs (Dostawcy usługi konfiguracji zasad](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) — link otwiera inną witrynę internetową firmy Microsoft).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia](device-restrictions-configure.md#create-the-profile).

## <a name="app-store"></a>App Store

Te ustawienia korzystają z [dostawcy usługi konfiguracji zasad ApplicationManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement), który zawiera również listę obsługiwanych wersji systemu Windows.

- **Sklep z aplikacjami** (tylko urządzenia przenośne): ustawienie **Nie skonfigurowano** (domyślne) umożliwia użytkownikom końcowym uzyskiwanie dostępu do sklepu z aplikacjami na urządzeniach przenośnych. Ustawienie **Blokuj** uniemożliwia korzystanie ze sklepu z aplikacjami.
- **Automatycznie aktualizuj aplikacje ze sklepu**: ustawienie **Nie skonfigurowano** (domyślne) umożliwia automatyczne aktualizowanie zainstalowanych aplikacji pochodzących ze Sklepu Microsoft Store. Ustawienie **Blokuj** uniemożliwia automatyczne instalowanie aktualizacji.
- **Instalacja aplikacji zaufanej**: wybierz, jeśli chcesz zezwolić na instalowanie aplikacji spoza Sklepu Microsoft Store, zwane także pobieraniem lokalnym. Pobieranie lokalne to instalowanie, a następnie uruchamianie lub testowanie aplikacji, która nie jest certyfikowana przez sklep Microsoft Store. Na przykład aplikacja, która jest aplikacją wewnętrzną wyłącznie w Twojej firmie. Dostępne opcje:
  - **Nie skonfigurowano** (ustawienie domyślne): używa domyślnych ustawień systemu operacyjnego.
  - **Blokuj**: uniemożliwia pobieranie lokalne. Nie można zainstalować aplikacji spoza sklepu Microsoft Store.
  - **Zezwalaj**: umożliwia pobieranie lokalne. Można instalować aplikacje spoza sklepu Microsoft Store.
- **Odblokowanie trybu deweloperskiego**: umożliwia korzystanie z ustawień trybu deweloperskiego systemu Windows, np. z ustawienia umożliwiającego użytkownikowi końcowemu modyfikację aplikacji pobranych lokalnie. Dostępne opcje:
  - **Nie skonfigurowano** (ustawienie domyślne): używa domyślnych ustawień systemu operacyjnego.
  - **Blokuj**: uniemożliwia korzystanie z trybu dewelopera i pobieranie lokalne aplikacji.
  - **Zezwalaj**: umożliwia korzystanie z trybu dewelopera i pobieranie lokalne aplikacji.

  Więcej informacji na temat tej funkcji znajdziesz w artykule [Konfigurowanie urządzenia pod kątem programowania](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development).

- **Udostępnione dane aplikacji użytkownika**: wybierz ustawienie **Zezwalaj**, aby udostępniać dane aplikacji różnym użytkownikom na tym samym urządzeniu oraz innym wystąpieniom tej aplikacji. Ustawienie **Nie skonfigurowano** (domyślne) uniemożliwia udostępnianie danych innym użytkownikom oraz innym wystąpieniom tej samej aplikacji.
- **Używaj tylko sklepu prywatnego**: ustawienie **Zezwalaj** zezwala tylko na pobieranie aplikacji ze sklepu prywatnego i nie zezwala na pobieranie aplikacji ze sklepu publicznego, w tym z katalogu sieci sprzedaży. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia pobieranie aplikacji ze sklepu prywatnego i sklepu publicznego.
- **Uruchamianie aplikacji pochodzącej ze sklepu**: ustawienie **Blokuj** wyłącza wszystkie aplikacje preinstalowane na urządzeniu lub pobrane ze sklepu Microsoft Store. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na otwieranie tych aplikacji.
- **Instaluj dane aplikacji na woluminie systemowym**: ustawienie **Blokuj** uniemożliwia aplikacjom przechowywanie danych na woluminie systemowym urządzenia. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia aplikacjom przechowywanie danych na woluminie dysku systemowego.
- **Instaluj aplikacje na dysku systemowym**: ustawienie **Blokuj** uniemożliwia instalowanie aplikacji na dysku systemowym urządzenia. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia instalowanie aplikacji na dysku systemowym.
- **DVR z gry** (tylko komputery): ustawienie **Blokuj** wyłącza nagrywanie i transmitowanie gier w systemie Windows. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia nagrywanie i transmitowanie gier.
- **Tylko aplikacje ze sklepu**: to ustawienie określa środowisko użytkownika, gdy użytkownicy instalują aplikacje z miejsc innych niż Microsoft Store. Dostępne opcje:

  - **Nieskonfigurowane** (ustawienie domyślne): umożliwia użytkownikom końcowym i instalować aplikacje z miejsc innych niż Microsoft Store, w tym aplikacje określone w innych ustawień zasad.  
  - **Gdziekolwiek**: wyłącza zalecenia dotyczące aplikacji, a użytkownicy mogą instalować aplikacji z dowolnego miejsca.  
  - **Tylko Store**: wymusza użytkownikom końcowym instalować tylko aplikacje z Microsoft Store.
  - **Zalecenia dotyczące**: podczas instalowania aplikacji z sieci web, która jest dostępna w Microsoft Store, użytkownikom zostanie wyświetlony komunikat zalecania, będą oni mogli pobrać ze sklepu.  
  - **Preferuj Store**: ostrzega użytkowników po ich instalować aplikacje z miejsc innych niż Microsoft Store.

  [Filtr SmartScreen/EnableAppInstallControl dostawcy usług Kryptograficznych](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen#smartscreen-enableappinstallcontrol)

- **Wymuś ponowne uruchamianie aplikacji w przypadku niepowodzenia aktualizacji**: aplikacja może się nie zaktualizować, jeśli jest właśnie używana. To ustawienie pozwala wymusić jej ponowne uruchomienie. **Nieskonfigurowane**: (domyślne) to ustawienie nie wymusza ponownego uruchomienia aplikacji. **Wymagaj**: pozwala administratorom na wymuszenie ponownego uruchomienia w określonym dniu i o podanej godzinie lub zgodnie z cyklicznym harmonogramem. Ustawienie **Wymagaj** powoduje też konieczność skonfigurowania następujących opcji:

  - **Data/godzina rozpoczęcia**: wybierz datę i godzinę ponownego uruchamiania aplikacji.
  - **Cykl**: wybierz powtarzanie codziennie, co tydzień lub co miesiąc.

  [Dostawca usługi konfiguracji ApplicationManagement/ScheduleForceRestartForUpdateFailures](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)

- **Kontrola użytkownika nad instalacjami**: po wybraniu ustawienia **Nieskonfigurowane** (domyślnie) Instalator Windows uniemożliwia użytkownikom zmianę opcji instalacji, które są zwykle zastrzeżone dla administratorów systemu. Dotyczy to np. wejścia do katalogu w celu zainstalowania plików. **Zablokuj**: pozwala użytkownikom na zmianę tych opcji instalacji. Niektóre funkcje zabezpieczeń Instalatora Windows są pomijane.

  [Dostawca usługi konfiguracji ApplicationManagement/MSIAllowUserControlOverInstall](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-msiallowusercontroloverinstall)

- **Instalowanie aplikacji z podniesionymi uprawnieniami**: po wybraniu ustawienia **Nieskonfigurowane** (domyślnie) podczas instalowania programów, których nie wdraża ani nie udostępnia administrator systemu, system stosuje uprawnienia bieżącego użytkownika. **Zablokuj**: zezwala Instalatorowi Windows na użycie podniesionych uprawnień podczas instalowania dowolnego programu w systemie. Uprawnienia te są rozszerzone na wszystkie programy.

  [Dostawca usługi konfiguracji ApplicationManagement/MSIAlwaysInstallWithElevatedPrivileges](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-msialwaysinstallwithelevatedprivileges)

- **Aplikacje autostartu**: wprowadź listę aplikacji, które będą otwierane, gdy użytkownik zaloguje się na urządzeniu. Lista musi zawierać aplikacje systemu Windows wymienione jako nazwy rodzin pakietów (PFN) rozdzielone średnikami. Aby ta zasada działała, manifest aplikacji systemu Windows musi zawierać zadanie startowe.

  [Dostawca usługi konfiguracji ApplicationManagement/LaunchAppAfterLogOn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-launchappafterlogon)

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="cellular-and-connectivity"></a>Sieć komórkowa i łączność

Te ustawienia korzystają z dostawców usługi konfiguracji [zasad łączności](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity) i [zasad sieci Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi) zawierających także listę obsługiwanych wersji systemu Windows.

- [Dostawcy usługi konfiguracji zasad sieci Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi)

- **Kanał danych komórkowych**: wybierz, jeśli chcesz, aby użytkownicy końcowi mogli korzystać z sieci komórkowej w celu np. przeglądania Internetu. Dostępne opcje:
  - **Nie skonfigurowano** (ustawienie domyślne): używa domyślnych ustawień systemu operacyjnego, które mogą zezwalać na używanie kanału danych komórkowych. Użytkownicy końcowi mogą wyłączyć tę opcję.
  - **Blokuj**: nie zezwala na używanie kanału danych komórkowych. Użytkownicy końcowi nie mogą włączyć tej opcji.
  - **Zezwalaj (nieedytowalne)** : umożliwia korzystanie z kanału danych komórkowych. Użytkownicy końcowi nie mogą wyłączyć tej opcji.

- **Roaming danych**: ustawienie **Blokuj** uniemożliwia włączenie roamingu danych na urządzeniu. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na roaming między sieciami w przypadku uzyskiwania dostępu do danych.
- **Sieć VPN przez sieć komórkową**: ustawienie **Blokuj** uniemożliwia urządzeniu uzyskiwanie dostępu do sieci VPN, gdy korzysta z sieci komórkowej. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia sieci VPN na korzystanie z dowolnego połączenia, w tym także komórkowego.
- **Roaming sieci VPN przez sieć komórkową**: ustawienie **Blokuj** uniemożliwia urządzeniu uzyskiwanie dostępu do połączeń sieci VPN, gdy jest włączony roaming w sieci komórkowej. Ustawienie**Nie skonfigurowano** (domyślne) zezwala na połączenia sieci VPN podczas roamingu.
- **Usługa podłączonych urządzeń**: ustawienie **Blokuj** powoduje wyłączenie składnika platformy podłączonych urządzeń (CDP). Platforma CDP umożliwia odnajdywanie innych urządzeń i nawiązywanie z nimi połączenia (za pośrednictwem połączenia Bluetooth/LAN lub chmury) w celu umożliwienia zdalnego uruchamiania aplikacji, zdalnej obsługi komunikatów, tworzenia sesji zdalnych aplikacji oraz korzystania z innych środowisk obsługi wielu urządzeń. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na używanie usługi podłączonych urządzeń, która umożliwia odnajdywanie i nawiązywanie połączenia z innymi urządzeniami Bluetooth.
- **NFC**: ustawienie **Blokuj** uniemożliwia korzystanie z funkcji komunikacji zbliżeniowej (NFC). Ustawienie **Nie skonfigurowano** (domyślne) umożliwia użytkownikom włączanie i konfigurowanie funkcji NFC na urządzeniu.
- **Wi-Fi**: ustawienie **Blokuj** uniemożliwia użytkownikom włączanie i konfigurowanie połączeń Wi-Fi na urządzeniu i korzystanie z nich. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na połączenia Wi-Fi.
- **Automatycznie łącz się z hotspotami Wi-Fi**: ustawienie **Blokuj** uniemożliwia urządzeniom automatyczne łączenie się z hotspotami Wi-Fi. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia urządzeniom automatyczne łączenie się z bezpłatnymi hotspotami Wi-Fi oraz automatyczne akceptowanie wszelkich warunków i postanowień związanych z połączeniem.
- **Ręczna konfiguracja sieci Wi-Fi**: ustawienie **Blokuj** uniemożliwia urządzeniom łączenie się z sieciami Wi-Fi poza sieciami z zainstalowanymi serwerami MDM. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia użytkownikom końcowym dodawanie i konfigurowanie własnych -Fi identyfikatorów SSID sieci połączeń Wi-Fi.
- **Interwał skanowania sieci Wi-Fi**: wprowadź wartość określającą, jak często urządzenie ma wyszukiwać sieci Wi-Fi. Wprowadź wartość z zakresu od 1 (najczęściej) do 500 (najrzadziej). Wartość domyślna to `0` (zero).

### <a name="bluetooth"></a>Bluetooth

Te ustawienia korzystają z [dostawcy usługi konfiguracji zasad komunikacji Bluetooth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth), który zawiera również listę obsługiwanych wersji systemu Windows.

- **Bluetooth**: ustawienie **Blokuj** uniemożliwia użytkownikom włączanie komunikacji Bluetooth. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na korzystanie z komunikacji Bluetooth na urządzeniu.
- **Odnajdowanie Bluetooth**: ustawienie **Blokuj** uniemożliwia wykrycie urządzenia przez inne urządzenia z włączoną komunikacją Bluetooth. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia wykrywanie urządzenia przez inne urządzenia z włączoną komunikacją Bluetooth, takie jak np. zestaw słuchawkowy.
- **Wstępne parowanie przy użyciu połączenia Bluetooth**: ustawienie **Blokuj** uniemożliwia automatyczne parowanie określonych urządzeń Bluetooth z urządzeniem hosta. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na automatyczne parowanie z urządzeniem hosta.
- **Reklamy przez sieć Bluetooth**: ustawienie **Blokuj** uniemożliwia urządzeniu wysyłanie reklam przez sieć Bluetooth. Ustawienie **Nie skonfigurowano** (domyślne) zezwala urządzeniu na wysłanie reklam przez sieć Bluetooth.
- **Dozwolone usługi Bluetooth**: **Dodaj** listę dozwolonych usług i profilów Bluetooth w postaci ciągów szesnastkowych, np. `{782AFCFC-7CAA-436C-8BF0-78CD0FFBD4AF}`.

  Więcej informacji o liście usług znajdziesz w artykule [Podręcznik użycia elementu ServicesAllowedList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#servicesallowedlist-usage-guide).

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="cloud-and-storage"></a>Chmura i magazyn

Te ustawienia korzystają z [dostawcy usługi konfiguracji zasad kont](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-accounts), który zawiera również listę obsługiwanych wersji systemu Windows.

- **Konto Microsoft**: ustawienie **Blokuj** uniemożliwia użytkownikom końcowym skojarzenie konta Microsoft z urządzeniem. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na dodawanie konta Microsoft i korzystanie z niego.
- **Konto inne niż Microsoft**: ustawienie **Blokuj** uniemożliwia użytkownikom końcowym dodawanie kont innych niż Microsoft przy użyciu interfejsu użytkownika. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia użytkownikom dodawanie kont e-mail, które nie są skojarzone z kontem Microsoft.
- **Synchronizacja ustawień dla konta Microsoft**: ustawienie **Nie skonfigurowano** (domyślne) zezwala na synchronizację ustawień urządzenia i aplikacji, które są skojarzone z kontem Microsoft, między różnymi urządzeniami. Ustawienie **Blokuj** uniemożliwia wykonanie synchronizacji.
- **Asystent logowania za pomocą konta Microsoft**: ustawienie **Nie skonfigurowano** (domyślne) umożliwia użytkownikom końcowym na uruchamiania i zatrzymywanie usługi **Asystent logowania za pomocą konta Microsoft** (wlidsvc). Ta usługa systemu operacyjnego pozwala użytkownikom logować się do swoich kont Microsoft. Ustawienie **Wyłącz** uniemożliwia użytkownikom końcowym sterowanie usługą Asystent logowania za pomocą konta Microsoft (wlidsvc).

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="cloud-printer"></a>Drukarka w chmurze

Te ustawienia korzystają z [dostawcy usługi konfiguracji zasad EnterpriseCloudPrint](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-enterprisecloudprint), który zawiera również listę obsługiwanych wersji systemu Windows.

- **Adres URL na potrzeby wykrywania drukarek**: wprowadź adres URL służący do wyszukiwania drukarek w chmurze. Na przykład wprowadź `https://cloudprinterdiscovery.contoso.com`.
- **Adres URL urzędu dostępu do drukarek**: wprowadź adres URL punktu końcowego uwierzytelniania na potrzeby pobierania tokenów OAuth. Na przykład wprowadź `https://azuretenant.contoso.com/adfs`.
- **Identyfikator GUID aplikacji klienta natywnego platformy Azure**: wprowadź identyfikator GUID aplikacji klienckiej upoważnionej do pobierania tokenów OAuth z urzędu OAuthAuthority. Na przykład wprowadź `E1CF1107-FF90-4228-93BF-26052DD2C714`.
- **Identyfikator URI zasobu usługi drukowania**: wprowadź identyfikator URI zasobu OAuth dla usługi drukowania skonfigurowanej w witrynie Azure Portal. Na przykład wprowadź `http://MicrosoftEnterpriseCloudPrint/CloudPrint`.
- **Maksymalna liczba drukarek do uwzględnienia w zapytaniu**: wprowadź maksymalną liczbę drukarek, która powinna zostać uwzględniona w zapytaniu. Wartość domyślna to `20`.
- **Identyfikator URI zasobu usługi wykrywania drukarek**: wprowadź identyfikator URI zasobu OAuth dla usługi wykrywania drukarek skonfigurowany w witrynie Azure Portal. Na przykład wprowadź `http://MopriaDiscoveryService/CloudPrint`.

> [!TIP]
> Po skonfigurowaniu [hybrydowego drukowania w chmurze systemu Windows Server](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-overview) można skonfigurować te ustawienia, a następnie wdrożyć je na urządzeniach z systemem Windows.

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="control-panel-and-settings"></a>Panel sterowania i Ustawienia

- **Aplikacja ustawień**: ustawienie **Blokuj** uniemożliwia użytkownikom końcowym uzyskiwanie dostępu do aplikacji ustawień systemu Windows. Ustawienie **Nie skonfigurowano** (domyślne) zezwala użytkownikom na otwieranie aplikacji Ustawienia na urządzeniu.
  - **System**: ustawienie **Blokuj** uniemożliwia dostęp do obszaru System w aplikacji Ustawienia. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na dostęp.
    - **Modyfikowanie ustawień zasilania i uśpienia** (tylko komputery stacjonarnych): ustawienie **Blokuj** uniemożliwia użytkownikom końcowym zmienianie ustawień zasilania i uśpienia na urządzeniu. Ustawienie **Nie skonfigurowano** (domyślne) zezwala użytkownikom na zmianę tych ustawień.
  - **Urządzenia**: ustawienie **Blokuj** uniemożliwia dostęp do obszaru Urządzenia w aplikacji Ustawienia na urządzeniu. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na dostęp.
  - **Sieć i Internet**: ustawienie **Blokuj** uniemożliwia dostęp do obszaru Sieć i Internet w aplikacji Ustawienia na urządzeniu. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na dostęp.
  - **Personalizacja**: ustawienie **Blokuj** uniemożliwia dostęp do obszaru Personalizacja w aplikacji Ustawienia na urządzeniu. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na dostęp.
  - **Aplikacje**: ustawienie **Blokuj** uniemożliwia dostęp do obszaru Aplikacje w aplikacji Ustawienia na urządzeniu. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na dostęp.
  - **Konta**: ustawienie **Blokuj** uniemożliwia dostęp do obszaru Konta w aplikacji Ustawienia na urządzeniu. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na dostęp.
  - **Czas i język**: ustawienie **Blokuj** uniemożliwia dostęp do obszaru Czas i język w aplikacji Ustawienia na urządzeniu. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na dostęp.
    - **Modyfikowanie czasu systemowego**: ustawienie **Blokuj** uniemożliwia użytkownikom końcowym zmienianie ustawień daty i godziny na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia użytkownikom zmianę tych ustawień.
    - **Modyfikowanie ustawień regionu** (tylko komputery): ustawienie **Blokuj** uniemożliwia użytkownikom końcowym zmianę ustawień regionu na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia użytkownikom zmianę tych ustawień.
    - **Modyfikowanie ustawień języka (tylko komputery)** : ustawienie **Blokuj** uniemożliwia użytkownikom końcowym zmianę ustawień języka na urządzeniu. Pozycja **Nieskonfigurowane** umożliwia użytkownikom zmianę tych ustawień.

      [Dostawca usługi konfiguracji zasad ustawień](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings)

  - **Granie**: ustawienie **Blokuj** uniemożliwia dostęp do obszaru Granie w aplikacji Ustawienia na urządzeniu. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na dostęp.
  - **Ułatwienia dostępu**: ustawienie **Blokuj** uniemożliwia dostęp do obszaru Ułatwienia dostępu w aplikacji Ustawienia na urządzeniu. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na dostęp.
  - **Prywatność**: ustawienie **Blokuj** uniemożliwia dostęp do obszaru Prywatność w aplikacji Ustawienia na urządzeniu. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na dostęp.
  - **Aktualizacja i zabezpieczenia**: ustawienie **Blokuj** uniemożliwia dostęp do obszaru Aktualizacja i zabezpieczenia w aplikacji Ustawienia na urządzeniu. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na dostęp.

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="display"></a>Wyświetlanie

Te ustawienia korzystają z [dostawcy usługi konfiguracji zasad wyświetlania](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-display), który zawiera również listę obsługiwanych wersji systemu Windows.

Skalowanie DPI z użyciem interfejsu GDI umożliwia rozpoznawanie wartości DPI monitora tym aplikacjom, które jej nie rozpoznają.

- **Włącz skalowanie z użyciem interfejsu GDI dla aplikacji**: **dodaj** starsze aplikacje, dla których chcesz włączyć skalowanie DPI z użyciem interfejsu GDI. Na przykład wprowadź adres `filename.exe` lub `%ProgramFiles%\Path\Filename.exe`.

  Skalowanie DPI z użyciem interfejsu GDI jest włączone dla wszystkich starszych aplikacji na liście.

- **Wyłącz skalowanie z użyciem interfejsu GDI dla aplikacji**: **dodaj** starsze aplikacje, dla których chcesz wyłączyć skalowanie DPI z użyciem interfejsu GDI. Na przykład wprowadź adres `filename.exe` lub `%ProgramFiles%\Path\Filename.exe`.

  Skalowanie DPI z użyciem interfejsu GDI jest wyłączone dla wszystkich starszych aplikacji na liście.

Możesz również **zaimportować** plik CSV zawierający listę aplikacji.

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="general"></a>Ogólne

Te ustawienia korzystają z [dostawcy usługi konfiguracji zasad środowiska](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience), który zawiera również listę obsługiwanych wersji systemu Windows. 

- **Przechwytywanie ekranu** (tylko urządzenia przenośne): ustawienie **Blokuj** uniemożliwia użytkownikom końcowym wykonywanie zrzutów ekranu na urządzeniu. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na korzystanie z tej funkcji.
- **Kopiowanie i wklejanie (tylko urządzenia przenośne)** : ustawienie **Blokuj** uniemożliwia użytkownikom końcowym kopiowanie i wklejanie danych między aplikacjami na urządzeniu. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na korzystanie z tej funkcji.
- **Ręczne wyrejestrowanie**: ustawienie **Blokuj** uniemożliwia użytkownikom końcowym usunięcie konta firmowego za pomocą panelu sterowania na urządzeniu. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na korzystanie z tej funkcji.

  To ustawienie zasad nie jest stosowane, jeśli komputer jest przyłączony do usługi Azure AD i włączono automatyczne rejestrowanie.

- **Ręczne instalowanie certyfikatu głównego (tylko urządzenia przenośne)** : ustawienie **Blokuj** uniemożliwia użytkownikom końcowym ręczne instalowanie certyfikatów głównych i certyfikatów pośrednich urzędów certyfikacji. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na korzystanie z tej funkcji.
- **Kamera**: ustawienie **Blokuj** uniemożliwia użytkownikom końcowym korzystanie z kamery urządzenia. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na korzystanie z tej funkcji.
- **Synchronizacja plików w usłudze OneDrive**: ustawienie **Blokuj** uniemożliwia użytkownikom końcowym synchronizowanie plików z urządzenia z usługą OneDrive. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na korzystanie z tej funkcji.
- **Magazyn wymienny**: ustawienie **Blokuj** uniemożliwia użytkownikom końcowym używanie urządzeń magazynu wymiennego, takich jak karty SD, z urządzeniem. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na korzystanie z tej funkcji.
- **Geolokalizacja**: ustawienie **Blokuj** uniemożliwia użytkownikom końcowym włączanie usług lokalizacyjnych na urządzeniu. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na korzystanie z tej funkcji.
- **Udostępnianie Internetu**: ustawienie **Blokuj** uniemożliwia udostępnianie połączenia internetowego na urządzeniu. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na korzystanie z tej funkcji.
- **Resetowanie telefonu**: ustawienie **Blokuj** uniemożliwia użytkownikom końcowym wyczyszczenie lub zresetowanie urządzenia do ustawień fabrycznych. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na korzystanie z tej funkcji.
- **Połączenie USB**: ustawienie **Blokuj** uniemożliwia dostęp do zewnętrznych urządzeń pamięci masowej przez połączenie USB na urządzeniu. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na korzystanie z tej funkcji. To ustawienie nie ma wpływu na ładowanie przy użyciu portu USB.
- **Tryb przeciwkradzieżowy** (tylko urządzenia przenośne): ustawienie **Blokuj** uniemożliwia użytkownikom końcowym wybranie preferencji trybu przeciwkradzieżowego na urządzeniu. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na korzystanie z tej funkcji.
- **Cortana**: ustawienie **Blokuj** powoduje wyłączenie asystenta głosowego Cortana na urządzeniu. Gdy Cortana jest wyłączona, użytkownicy mogą nadal wyszukiwać elementy na urządzeniu. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia korzystanie z Cortany.
- **Nagrywanie głosu** (tylko urządzenia przenośne): ustawienie **Blokuj** uniemożliwia użytkownikom końcowym korzystanie z rejestratora głosu na urządzeniu. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia rejestrowanie głosu przez aplikacje.
- **Modyfikacja nazwy urządzenia** (tylko urządzenia przenośne): ustawienie **Blokuj** uniemożliwia użytkownikom końcowym zmianę nazwy urządzenia. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na korzystanie z tej funkcji.
- **Dodaj pakiety aprowizacji**: ustawienie **Blokuj** uniemożliwia uruchamianie agenta konfiguracji środowiska uruchomieniowego, który instaluje pakiety aprowizacji na urządzeniu. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na korzystanie z tej funkcji.
- **Usuń pakiety aprowizacji**: ustawienie **Blokuj** uniemożliwia uruchamianie agenta konfiguracji środowiska uruchomieniowego, który usuwa pakiety aprowizacji z urządzenia. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na korzystanie z tej funkcji.
- **Odnajdywanie urządzeń**: ustawienie **Blokuj** uniemożliwia wykrywanie urządzenia przez inne urządzenia. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na korzystanie z tej funkcji.
- **Przełącznik zadań** (tylko urządzenia przenośne): ustawienie **Blokuj** uniemożliwia przełączanie zadań na urządzeniu. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na korzystanie z tej funkcji.
- **Okno dialogowe błędu karty SIM** (tylko urządzenia przenośne): ustawienie **Blokuj** powoduje, że na urządzeniu nie będą wyświetlane komunikaty o błędach, gdy karta SIM nie zostanie wykryta. Wybranie ustawienia **Nie skonfigurowano** (domyślne) spowoduje wyświetlanie komunikatów o błędach.
- **Obszar roboczy pisma odręcznego**: wybierz, czy i jak użytkownicy uzyskują dostęp do obszaru roboczego pisma odręcznego. Dostępne opcje:
  - **Nie skonfigurowano** (domyślna): włącza obszar roboczy pisma odręcznego, a użytkownik może używać go na ekranie blokady urządzenia.
  - **Wyłączone na ekranie blokady**: obszar roboczy pisma odręcznego i funkcja są włączone. Jednak użytkownik nie może uzyskać do nich dostępu na ekranie blokady urządzenia.
  - **Wyłączone**: dostęp do obszaru roboczego pisma odręcznego jest wyłączony. Funkcja jest wyłączona.

  [Dostawca usługi konfiguracji zasad WindowsInkWorkspace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace)

- **Automatyczne ponowne wdrażanie**: wybierz ustawienie **Zezwalaj**, aby użytkownicy z uprawnieniami administracyjnymi mogli usuwać wszystkie dane użytkownika i ustawienia za pomocą kombinacji klawiszy **CTRL + Win + R** na ekranie blokady urządzenia. Urządzenie jest automatycznie ponownie konfigurowane i rejestrowane do zarządzania. Pozycja **Nie skonfigurowano** (ustawienie domyślne) blokuje tę funkcję.
- **Wymagaj od użytkowników połączenia z siecią podczas konfiguracji urządzenia**: wybierz ustawienie **Wymagane**, aby urządzenia łączyły się z siecią przed wyjściem poza stronę Sieć podczas instalacji systemu Windows. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia użytkownikom przejście przez stronę Sieć nawet w przypadku braku połączenia z siecią.

  Ustawienie zostanie zastosowane po kolejnym wyczyszczeniu lub zresetowaniu urządzenia. Podobnie jak w przypadku wszelkich innych konfiguracji usługi Intune, urządzenie musi być zarejestrowane i zarządzane w usłudze Intune, aby otrzymać ustawienia konfiguracji. Jeśli urządzenie jest zarejestrowane i otrzymuje zasady, zresetowanie go wymusi zastosowanie ustawienia podczas kolejnej instalacji systemu Windows.

- **Bezpośredni dostęp do pamięci**: opcja **Blokuj** uniemożliwia bezpośredni dostęp do pamięci dla wszystkich podrzędnych portów PCI z możliwością podłączenia podczas pracy, dopóki użytkownik nie zaloguje się do systemu Windows. Pozycja **Włączone** (wartość domyślna) zezwala na bezpośredni dostęp do pamięci nawet wtedy, gdy użytkownik nie jest zalogowany.

  Dostawca usług kryptograficznych: [DataProtection/AllowDirectMemoryAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess)

- **Kończ procesy z Menedżera zadań**: to ustawienie określa, czy użytkownicy niebędący administratorami mogą używać Menedżera zadań do kończenia zadań. Pozycja **Blokuj** uniemożliwia użytkownikom standardowym (niebędącym administratorami) używanie Menedżera zadań do zakończenia procesu lub zadania na urządzeniu. **Nieskonfigurowane** (wartość domyślna) umożliwia użytkownikom standardowym zakończenie procesu lub zadania za pomocą Menedżera zadań.

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="locked-screen-experience"></a>Środowisko ekranu blokady

- **Powiadomienia Centrum akcji (tylko urządzenia przenośne)** : ustawienie **Blokuj** zapobiega wyświetlaniu powiadomień Centrum akcji na ekranie blokady urządzenia. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia użytkownikom wybranie, które aplikacje mogą wyświetlać powiadomienia na ekranie blokady.

  [Dostawca usługi konfiguracji AboveLock/AllowActionCenterNotifications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock#abovelock-allowactioncenternotifications)

- **Adres URL obrazu ekranu blokady (tylko komputery)** : wprowadź adres URL obrazu w formacie JPG, JPEG lub PNG używany jako tapeta ekranu blokady systemu Windows. Na przykład wprowadź `https://contoso.com/image.png`. To ustawienie powoduje zablokowanie obrazu bez możliwości późniejszej zmiany.
- **Konfigurowany przez użytkownika limit czasu ekranu (tylko urządzenia przenośne)** : ustawienie **Zezwalaj** pozwala użytkownikowi na ustawianie czasu. Ustawienie **Nie skonfigurowano** (domyślne) nie zapewnia użytkownikom tej opcji.

  [Dostawca usługi konfiguracji DeviceLock/AllowScreenTimeoutWhileLockedUserConfig](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-allowscreentimeoutwhilelockeduserconfig)

- **Cortana na zablokowanym ekranie** (tylko komputery): ustawienie **Blokuj** uniemożliwia użytkownikom interakcję z Cortana, gdy jest wyświetlany ekran blokady. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia interakcję z Cortaną.

  [Dostawca usługi konfiguracji AboveLock/AllowCortanaAboveLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock#abovelock-allowcortanaabovelock)

- **Wyskakujące powiadomienia na zablokowanym ekranie**: ustawienie **Blokuj** zapobiega wyświetlaniu wyskakujących powiadomień na ekranie blokady urządzenia. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na wyświetlanie tych powiadomień.

  [Dostawca usługi konfiguracji AboveLock/AllowToasts](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock#abovelock-allowtoasts)

- **Limit czasu ekranu (tylko urządzenia przenośne)** : ustaw czas trwania (w sekundach) od momentu zablokowania ekranu do momentu wyłączenia ekranu. Obsługiwane wartości to 11 – 1800. Na przykład wprowadź wartość `300`, aby ustawić limit czasu na 5 minut.

  [Dostawca usługi konfiguracji DeviceLock/ScreenTimeoutWhileLocked](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-screentimeoutwhilelocked)

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="messaging"></a>Obsługa wiadomości

Te ustawienia korzystają z [dostawcy usługi konfiguracji zasad obsługi wiadomości](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-messaging), który zawiera również listę obsługiwanych wersji systemu Windows.

- **Synchronizowanie wiadomości (tylko urządzenia przenośne)** : ustawienie **Blokuj** powoduje wyłączenie tworzenia kopii zapasowych i przywracania SMS-ów oraz synchronizowania SMS-ów między urządzeniami z systemem Windows. Wyłączenie tej funkcji pomaga uniknąć przechowywania informacji na serwerach poza kontrolą organizacji. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia użytkownikom zmianę tych ustawień i synchronizowanie SMS-ów.
- **MMS (tylko urządzenia przenośne)** : ustawienie **Blokuj** powoduje wyłączenie funkcji wysyłania i odbierania MMS-ów na urządzeniu. W przypadku przedsiębiorstw przy użyciu tych zasad możesz wyłączyć MMS-y na urządzeniach w ramach wymagań dotyczących zarządzania lub inspekcji. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na wysyłanie i odbieranie MMS-ów.
- **RCS (tylko urządzenia przenośne)** : ustawienie **Blokuj** powoduje wyłączenie funkcji wysyłania i odbierania wiadomości Rich Communication Services na urządzeniu. W przypadku przedsiębiorstw przy użyciu tych zasad możesz wyłączyć wiadomości RCS na urządzeniach w ramach wymagań dotyczących zarządzania lub inspekcji. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na wysyłanie i odbieranie wiadomości RCS.

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="microsoft-edge-browser"></a>Przeglądarka Microsoft Edge

Te ustawienia korzystają z [dostawcy usługi konfiguracji zasad przeglądarki](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser), który zawiera również listę obsługiwanych wersji systemu Windows.

### <a name="use-microsoft-edge-kiosk-mode"></a>Użyj trybu kiosku przeglądarki Microsoft Edge

Dostępne ustawienia zmieniają się w zależności od wybranej opcji. Dostępne opcje:

- **Nie** (ustawienie domyślne): przeglądarka Microsoft Edge nie jest uruchamiana w trybie kiosku. Możesz zmieniać i konfigurować wszystkie ustawienia przeglądarki Microsoft Edge.
- **Oznakowanie cyfrowe/interakcyjne (kiosk z jedną aplikacją)** : ta opcja filtruje ustawienia przeglądarki Microsoft Edge, które dotyczą trybu kiosku z oznakowaniem cyfrowym/interacyjnym w tej przeglądarce, używane wyłącznie w przypadku kiosków systemu Windows 10 z jedną aplikacją. Wybierz to ustawienie, aby otworzyć adres URL na pełnym ekranie i pokazać wyłącznie zawartość docelowej witryny internetowej. Artykuł [Set up digital signs (Konfigurowanie oznakowania cyfrowego)](https://docs.microsoft.com/windows/configuration/setup-digital-signage) zawiera więcej informacji na temat tej funkcji.
- **Przeglądanie publiczne w trybie InPrivate (kiosk z jedną aplikacją)** : ta opcja filtruje ustawienia przeglądarki Microsoft Edge, które dotyczą trybu kiosku z przeglądaniem publicznym w trybie InPrivate w tej przeglądarce, używane w przypadku kiosków systemu Windows 10 z jedną aplikacją. Umożliwia uruchomienie wersji przeglądarki Microsoft Edge z wieloma kartami.
- **Tryb normalny (kiosk z wieloma aplikacjami)** : ta opcja filtruje ustawienia przeglądarki Microsoft Edge, które dotyczą normalnego trybu kiosku w tej przeglądarce. Umożliwia uruchomienie pełnej wersji przeglądarki Microsoft Edge z wszystkimi funkcjami przeglądania.
- **Przeglądanie publiczne (kiosk z wieloma aplikacjami)** : ta opcja filtruje ustawienia przeglądarki Microsoft Edge, które dotyczą trybu przeglądania publicznego w kiosku systemu Windows 10 z wieloma aplikacjami.  Umożliwia uruchomienie wersji przeglądarki Microsoft Edge z wieloma kartami w trybie InPrivate.

> [!TIP]
> Aby uzyskać więcej informacji na temat działania tych opcji, zobacz [Microsoft Edge kiosk mode configuration types (Typy konfiguracji trybu kiosku przeglądarki Microsoft Edge)](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

Ten profil ograniczeń urządzenia jest bezpośrednio związany z profilem kiosku utworzonym za pomocą [ustawień kiosku w systemie Windows](kiosk-settings-windows.md). Podsumowując:

1. Utwórz profil [ustawień kiosku systemu Windows](kiosk-settings-windows.md), aby uruchomić urządzenie w trybie kiosku. Wybierz aplikację Microsoft Edge i ustaw tryb kiosku przeglądarki Microsoft Edge w profilu kiosku.
2. Utwórz profil ograniczeń urządzenia zgodnie z opisem w tym artykule i skonfiguruj dozwolone funkcje i ustawienia przeglądarki Microsoft Edge. Pamiętaj, aby wybrać ten sam typ trybu kiosku przeglądarki Microsoft Edge, który określono w profilu kiosku (w [ustawieniach kiosku systemu Windows](kiosk-settings-windows.md)). 

    Artykuł [Supported kiosk mode settings (Obsługiwane ustawienia trybu kiosku)](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-policies-for-kiosk-mode) to doskonałe źródło informacji.

> [!IMPORTANT] 
> Pamiętaj, aby przypisać utworzony profil przeglądarki Microsoft Edge do tych samych urządzeń, do których przypisano profil kiosku ([ustawienia kiosku systemu Windows](kiosk-settings-windows.md)).

[ConfigureKioskMode CSP (Dostawca usługi konfiguracji ConfigureKioskMode)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-configurekioskmode)

### <a name="start-experience"></a>Środowisko rozpoczynania pracy

- **Uruchom przeglądarkę Microsoft Edge przy użyciu**: wybierz strony otwierane po uruchomieniu przeglądarki Microsoft Edge. Dostępne opcje:
  - **Niestandardowe strony początkowe**: wprowadź strony początkowe, na przykład `http://www.contoso.com`. Przeglądarka Microsoft Edge załaduje wprowadzone przez Ciebie strony początkowe.
  - **Strona nowej karty**: przeglądarka Microsoft Edge ładuje adres wprowadzony w obszarze **Adres URL nowej karty**.
  - **Strona ostatniej sesji**: przeglądarka Microsoft Edge ładuje stronę ostatniej sesji.
  - **Strony początkowe w ustawieniach aplikacji lokalnych**: przeglądarka Microsoft Edge jest uruchamiana z domyślną stroną początkową zdefiniowaną przez system operacyjny.

- **Zezwalaj użytkownikowi na zmienianie stron początkowych**: ustawienie **Tak** (domyślne) zezwala użytkownikom na zmienianie stron początkowych. Administratorzy mogą używać elementu `EdgeHomepageUrls` do wprowadzania stron początkowych, które są widoczne domyślnie dla użytkowników po otwarciu przeglądarki Microsoft Edge. Ustawienie **Nie** uniemożliwia użytkownikom zmienianie stron początkowych.
- **Zezwalaj na zawartość internetową na nowej karcie**: po wybraniu ustawienia **Tak** (domyślnego) przeglądarka Microsoft Edge otwiera adres URL wprowadzony w ustawieniu **Adres URL nowej karty**. Jeśli ustawienie **Adres URL nowej karty** jest puste, przeglądarka Microsoft Edge otworzy nową kartę zdefiniowaną w ustawieniach przeglądarki. Użytkownicy mogą zmienić to ustawienie. Po wybraniu ustawienia **Nie** przeglądarka Microsoft Edge otworzy nową kartę z pustą stroną. Użytkownicy nie mogą zmienić tego ustawienia.
- **Adres URL nowej karty**: wprowadź adres URL do otwarcia na stronie nowej karty. Na przykład wprowadź adres `https://www.bing.com` lub `https://www.contoso.com`.

- **Przycisk Strona główna**: wybierz, co się stanie po wybraniu przycisku Strona główna. Dostępne opcje:
  - **Strony początkowe**: otwiera stronę wybraną w ustawieniu **Uruchom przeglądarkę Microsoft Edge przy użyciu**.
  - **Strona nowej karty**: otwiera adres URL wprowadzony w ustawieniu **Adres URL nowej karty**.
  - **Adres URL przycisku Strona główna**: wprowadź adres URL do otwarcia. Na przykład wprowadź adres `https://www.bing.com` lub `https://www.contoso.com`.
  - **Ukryj przycisk Strona główna**: ukrywa przycisk Strona główna
- **Zezwalaj użytkownikom na zmienianie przycisku Strona główna**: ustawienie **Tak** zezwala użytkownikom na zmienianie przycisku Strona główna. Zmiany wprowadzone przez użytkownika zastępują wszelkie ustawienia administratora, które dotyczą przycisku strony głównej. Ustawienie **Nie** (domyślne) uniemożliwia użytkownikom zmienianie sposobu, w jaki administrator skonfigurował przycisk Strona główna.
- **Pokaż stronę pierwszego uruchomienia (tylko urządzenia przenośne)** : ustawienie **Tak** (domyślne) powoduje wyświetlanie strony wprowadzenia przy pierwszym użyciu w przeglądarce Microsoft Edge. Ustawienie **Nie** blokuje wyświetlanie strony wprowadzenia przy pierwszym uruchomieniu przeglądarki Microsoft Edge. Ta funkcja umożliwia przedsiębiorstwom, takim jak organizacje zarejestrowane w konfiguracjach zeroemisyjnych, na blokowanie tej strony.
- **Lokalizacja listy adresów URL na potrzeby pierwszego uruchomienia** (tylko system Windows 10 Mobile): wprowadź adres URL pliku XML zawierającego adresy URL strony pierwszego uruchomienia. Na przykład wprowadź `https://www.contoso.com/sites.xml`.

- **Odśwież przeglądarkę po czasie bezczynności**: wprowadź czas bezczynności w minutach, od 0 do 1440, po którym przeglądarka zostanie odświeżona. Wartość domyślna to `5` minut. Wartość `0` (zero) oznacza, że przeglądarka nie będzie odświeżana w czasie bezczynności.

  To ustawienie jest dostępne tylko w trybie [Przeglądanie publiczne InPrivate (kiosk z jedną aplikacją)](#use-microsoft-edge-kiosk-mode).

- **Zezwalaj na wyskakujące okienka** (tylko komputery): ustawienie **Tak** (domyślne) zezwala na wyskakujące okienka w przeglądarce internetowej. Ustawienie **Nie** zapobiega wyświetlaniu wyskakujących okienek przeglądarce.
- **Wysyłaj ruch intranetowy do programu Internet Explorer** (tylko komputery): ustawienie **Zezwalaj** umożliwia użytkownikom otwieranie intranetowych witryn internetowych w programie Internet Explorer zamiast w przeglądarce Microsoft Edge. To ustawienie dotyczy kompatybilności wstecznej. Ustawienie **Nie** (domyślne) pozwala użytkownikom na używanie przeglądarki Microsoft Edge.
- **Lokalizacja listy witryn trybu przedsiębiorstwa** (tylko komputery): wprowadź adres URL pliku XML zawierającego lokalizację listy witryn internetowych, które można otwierać w trybie przedsiębiorstwa. Użytkownicy nie mogą zmieniać tej listy. Na przykład wprowadź `https://www.contoso.com/sites.xml`.
- **Komunikat podczas otwierania witryn w programie Internet Explorer**: to ustawienie służy do konfigurowania przeglądarki Microsoft Edge w celu wyświetlania powiadomienia przed otwarciem witryny w programie Internet Explorer 11. Dostępne opcje:
  - **Nie pokazuj komunikatu**: jest stosowane domyślne zachowanie systemu operacyjnego, co może sprawiać, że komunikat nie będzie wyświetlany.
  - **Pokaż komunikat o otworzeniu witryny w programie Internet Explorer 11**: wyświetlaj komunikat podczas otwierania witryn w programie Internet Explorer. Witryny są otwierane w programie IE. 
  - **Pokaż komunikat z opcją otwarcia witryn w przeglądarce Microsoft Edge**: wyświetlaj komunikat podczas otwierania witryn w przeglądarce Edge. Komunikat zawiera link **Kontynuuj pracę w przeglądarce Microsoft Edge**, dzięki któremu użytkownicy mogą wybrać przeglądarkę Microsoft Edge zamiast programu Internet Explorer.

  > [!IMPORTANT]
  > To ustawienie wymaga użycia ustawienia **Lokalizacja listy witryn trybu przedsiębiorstwa**, ustawienia **Wysyłaj ruch intranetowy do programu Internet Explorer** lub obydwu tych ustawień.

- **Zezwalaj na używanie listy zgodności firmy Microsoft**: ustawienie **Tak** (domyślne) zezwala na używanie listy zgodności firmy Microsoft. Ustawienie **Nie** uniemożliwia używanie listy zgodności firmy Microsoft w przeglądarce Microsoft Edge. Ta lista firmy Microsoft pomaga przeglądarce Microsoft Edge prawidłowo wyświetlać witryny ze znanymi problemami dotyczącymi zgodności.
- **Załaduj wstępnie strony początkowe i nową kartę**: ustawienie **Tak** (domyślne) używa domyślnego zachowania systemu operacyjnego, które może powodować wstępne ładowanie tych stron. Wstępne ładowanie minimalizuje czas uruchamiania przeglądarki Microsoft Edge i ładowania nowej karty. Ustawienie **Nie** uniemożliwia wstępne ładowanie stron startowych i strony nowej karty w przeglądarce Microsoft Edge.
- **Uruchom wstępnie strony początkowe i nową kartę**: ustawienie **Tak** (domyślne) używa domyślnego zachowania systemu operacyjnego, które może powodować wstępne uruchamianie tych stron. Wstępne uruchomienie zwiększa wydajność przeglądarki Microsoft Edge i minimalizuje czas wymagany do uruchomienia tej przeglądarki. Ustawienie **Nie** uniemożliwia wstępne ładowanie stron początkowych i nowej karty w przeglądarce Microsoft Edge.

Wybierz przycisk **OK**, aby zapisać zmiany.

### <a name="favorites-and-search"></a>Ulubione i wyszukiwanie

- **Pokaż pasek Ulubione**: wybierz, co się stanie z paskiem ulubionych na dowolnej stronie przeglądarki Microsoft Edge. Dostępne opcje:
  - **Na stronach początkowych i nowej karcie**: pokazuje pasek ulubionych po uruchomieniu przeglądarki Microsoft Edge i na wszystkich kartach. Użytkownicy końcowi mogą zmienić to ustawienie.
  - **Na wszystkich stronach**: pokazuje pasek ulubionych na wszystkich stronach. Użytkownicy końcowi nie mogą zmienić tego ustawienia.
  - **Ukryty**: ukrywa pasek ulubionych na wszystkich stronach. Użytkownicy końcowi nie mogą zmienić tego ustawienia.
- **Zezwalaj na zmiany w ulubionych**: ustawienie **Tak** (domyślne) używa domyślnego zachowania systemu operacyjnego, które zezwala użytkownikom na zmienianie listy. Ustawienie **Nie** uniemożliwia użytkownikom końcowym dodawanie, importowanie, sortowanie lub edytowanie listy Ulubione.
  - **Lista Ulubione**: dodaj listę adresów URL do pliku ulubionych. Na przykład dodaj `http://contoso.com/favorites.html`.
- **Synchronizuj ulubione między przeglądarkami firmy Microsoft (tylko komputery)** : ustawienie **Tak** wymusza synchronizowanie ulubionych między przeglądarkami Internet Explorer i Microsoft Edge w systemie Windows. Operacje dodawania, usuwania, modyfikacji i zmian kolejności w obszarze ulubionych będą udostępniane między przeglądarkami.  Ustawienie **Nie** (domyślne) używa domyślnego zachowania systemu operacyjnego, które może dać użytkownikom możliwość synchronizowania między przeglądarkami.
- **Domyślna wyszukiwarka**: wybierz domyślną wyszukiwarkę na urządzeniu. Użytkownicy końcowi mogą w dowolnym momencie zmienić tę wartość. Dostępne opcje:
  - Wyszukiwarka w ustawieniach przeglądarki Microsoft Edge klienta
  - Bing
  - Google
  - Yahoo
  - Wartość niestandardowa: w obszarze **Adres URL pliku XML w technologii OpenSearch** wprowadź adres URL protokołu HTTPS wraz z plikiem XML zawierającym co najmniej krótką nazwę i adres URL wyszukiwarki. Na przykład wprowadź `https://www.contoso.com/opensearch.xml`.
- **Pokaż sugestie dotyczące wyszukiwania**: ustawienie **Tak** (domyślne) umożliwia sugerowanie witryn przez wyszukiwarkę podczas wpisywania wyszukiwanych fraz na pasku adresu. Ustawienie **Nie** uniemożliwia użycie tej funkcji.
- **Zezwalaj na zmiany w wyszukiwarce**: opcja **Tak** (ustawienie domyślne) umożliwia użytkownikom dodawanie nowych wyszukiwarek lub zmianę domyślnej wyszukiwarki w przeglądarce Microsoft Edge. Wybierz opcję **Nie**, aby uniemożliwić użytkownikom dostosowywanie ustawień wyszukiwarki.

  To ustawienie jest dostępne tylko w [trybie normalnym (kiosk z wieloma aplikacjami) ](#use-microsoft-edge-kiosk-mode).

Wybierz przycisk **OK**, aby zapisać zmiany.

### <a name="privacy-and-security"></a>Prywatność i zabezpieczenia

- **Zezwalaj na przeglądanie InPrivate**: ustawienie **Tak** (domyślne) zezwala na przeglądanie InPrivate w przeglądarce Microsoft Edge. Po zamknięciu wszystkich kart InPrivate przeglądarka Microsoft Edge usuwa dane przeglądania z urządzenia. Ustawienie **Nie** uniemożliwia użytkownikom końcowym otwieranie sesji przeglądania InPrivate.
- **Zapisywanie historii przeglądania**: ustawienie **Tak** (domyślne) umożliwia zapisywanie historii przeglądania w przeglądarce Microsoft Edge. Ustawienie **Nie** uniemożliwia zapisywanie historii przeglądania.
- **Wyczyść dane przeglądania przy zamykaniu** (tylko komputery): ustawienie **Tak** włącza czyszczenie historii i danych przeglądania przy zamykaniu przeglądarki Microsoft Edge. Ustawienie **Nie** (domyślne) używa domyślnego zachowania systemu operacyjnego, które może powodować buforowanie danych przeglądania.
- **Synchronizuj ustawienia przeglądarki między urządzeniami użytkownika**: wybierz sposób synchronizowania ustawień przeglądarki między urządzeniami. Dostępne opcje:
  - **Zezwalaj**: zezwala na synchronizację ustawień przeglądarki Microsoft Edge między urządzeniami użytkownika.
  - **Blokuj i włącz nadpisywanie użytkownika**: blokuje synchronizację ustawień przeglądarki Microsoft Edge między urządzeniami użytkownika. Użytkownicy mogą przesłaniać to ustawienie.
  - **Blokuj**: blokuj synchronizację ustawień przeglądarki Microsoft Edge między urządzeniami użytkowników. Użytkownicy nie mogą przesłaniać tego ustawienia.

Po wybraniu opcji „Zablokuj i włącz przesłanianie przez użytkownika” użytkownik może przesłonić wartość wyznaczoną przez administratora.

- **Zezwalaj na menedżera haseł**: ustawienie **Tak** (domyślne) zezwala przeglądarce Microsoft Edge na automatyczne używanie menedżera haseł, co umożliwia użytkownikom zapisywanie haseł na urządzeniu i zarządzanie nimi. Ustawienie **Nie** uniemożliwia przeglądarce Microsoft Edge używanie menedżera haseł.
- **Pliki cookie**: wybierz sposób obsługi plików cookie w przeglądarce internetowej. Dostępne opcje:
  - **Zezwalaj**: pliki cookie są przechowywane na urządzeniu.
  - **Blokuj wszystkie pliki cookie**: pliki cookie nie są przechowywane na urządzeniu.
  - **Blokuj tylko pliki cookie innych firm**: pliki cookie innych firm lub partnerów nie są przechowywane na urządzeniu.
- **Zezwalaj na autowypełnianie w formularzach**: ustawienie **Tak** (domyślne) zezwala użytkownikom na zmianę ustawień autowypełniania w przeglądarce i automatyczne wypełnianie pól formularzy. Ustawienie **Nie** powoduje wyłączenie funkcji autowypełniania w przeglądarce Microsoft Edge.
- **Wysyłaj nagłówki Nie śledź**: ustawienie **Tak** powoduje wysyłanie nagłówków Nie śledź do witryn internetowych żądających informacji dotyczących śledzenia (zalecane). Ustawienie **Nie** (domyślne) powoduje, że nagłówki Nie śledź nie są wysyłane, co umożliwia witrynom internetowym śledzenie użytkownika. Użytkownik może konfigurować to ustawienie.
- **Pokaż adres IP hosta localhost dla protokołu WebRTC**: ustawienie **Tak** (domyślne) umożliwia wyświetlanie adresu IP lokalnego hosta użytkowników podczas nawiązywania połączeń telefonicznych przy użyciu tego protokołu. Ustawienie **Nie** zapobiega wyświetlaniu adresu IP hosta lokalnego użytkowników. 
- **Zezwalaj na zbieranie danych dynamicznych kafelków**: ustawienie **Tak** (domyślne) zezwala przeglądarce Microsoft Edge na zbieranie informacji z dynamicznych kafelków przypiętych do menu Start. Ustawienie **Nie** uniemożliwia zbieranie tych informacji, co może spowodować ograniczenie środowiska użytkowników.
- **Użytkownik może przesłonić błędy certyfikatów**: ustawienie **Tak** (domyślne) zezwala użytkownikom na uzyskiwanie dostępu do witryn internetowych, w przypadku których występują błędy certyfikatu Secure Sockets Layer / Transport Layer Security (SSL/TLS). Ustawienie **Nie** (zalecane w celu zwiększenia bezpieczeństwa) uniemożliwia użytkownikom uzyskiwanie dostępu do witryn internetowych z błędami certyfikatu SSL lub TLS.

Wybierz przycisk **OK**, aby zapisać zmiany.

### <a name="additional"></a>Dodatkowe

- **Zezwalaj na korzystanie z przeglądarki Microsoft Edge** (tylko urządzenia przenośne): ustawienie **Tak** (domyślne) umożliwia korzystanie z przeglądarki internetowej Microsoft Edge na urządzeniu przenośnym. Ustawienie **Nie** uniemożliwia korzystanie z przeglądarki Microsoft Edge na urządzeniu. Jeśli wybierzesz ustawienie **Nie**, pozostałe poszczególne ustawienia będą dotyczyć tylko komputerów.
- **Zezwalaj na listę rozwijaną paska adresu**: ustawienie **Tak** (domyślne) zezwala przeglądarce Microsoft Edge na wyświetlanie sugestii na liście rozwijanej paska adresu. Ustawienie **Nie** uniemożliwia przeglądarce Microsoft Edge wyświetlanie sugestii na liście rozwijanej podczas wpisywania tekstu. Gdy wybierzesz ustawienie **Nie**:
  - zmniejszasz przepustowość sieci w ramach komunikacji między przeglądarką Microsoft Edge a usługami firmy Microsoft.
  - wyłączasz funkcję **Pokazuj sugestie wyszukiwania i sugerowane witryny podczas wpisywania** w obszarze Microsoft Edge > Ustawienia.
- **Zezwalaj na tryb pełnoekranowy**: ustawienie **Tak** (domyślne) zezwala na korzystanie z trybu pełnoekranowego w przeglądarce Microsoft Edge. W trybie pełnoekranowym wyświetlana jest tylko zawartość internetowa, a interfejs użytkownika przeglądarki Microsoft Edge pozostaje ukryty. Ustawienie **Nie** uniemożliwia korzystanie z trybu pełnoekranowego w przeglądarce Microsoft Edge.
- **Zezwalaj na stronę z informacjami o flagach**: ustawienie **Tak** (domyślne) używa domyślnego zachowania systemu operacyjnego, które może zezwolić na dostęp do strony `about:flags`. Strona `about:flags` umożliwia użytkownikom zmianę ustawień dla deweloperów i korzystanie z funkcji eksperymentalnych. Ustawienie **Nie** uniemożliwia użytkownikom końcowym uzyskiwanie dostępu do strony `about:flags` w przeglądarce Microsoft Edge.
- **Zezwalaj na narzędzia programistyczne**: ustawienie **Tak** (domyślne) zezwala użytkownikom na korzystanie z narzędzi programistycznych F12 w celu tworzenia i debugowania stron internetowych. Ustawienie **Nie** uniemożliwia użytkownikom końcowym korzystanie z narzędzi programistycznych F12.
- **Zezwalaj na język JavaScript**: ustawienie **Tak** (domyślne) umożliwia uruchamianie skryptów (takich jak JavaScript) w przeglądarce Microsoft Edge. Ustawienie **Nie** uniemożliwia uruchamianie skryptów języka Java w przeglądarce.
- **Użytkownik może instalować rozszerzenia**: ustawienie **Tak** (domyślne) umożliwia użytkownikom końcowym instalowanie rozszerzeń przeglądarki Microsoft Edge na urządzeniu. Ustawienie **Nie** uniemożliwia instalację.
- **Zezwalaj na pobieranie lokalne rozszerzeń dla deweloperów**: ustawienie **Tak** (domyślne) używa domyślnego zachowania systemu operacyjnego, które może zezwalać na pobieranie lokalne. Pobieranie lokalne umożliwia instalowanie i uruchamianie niezweryfikowanych rozszerzeń. Ustawienie **Nie** uniemożliwia przeglądarce Microsoft Edge pobieranie lokalne przy użyciu funkcji **Ładuj rozszerzenia**. Nie uniemożliwia jednak pobierania lokalnego rozszerzeń przy użyciu innych sposobów, np. za pomocą programu PowerShell.
- **Wymagane rozszerzenia**: wybierz rozszerzenia, których użytkownicy końcowi nie mogą wyłączać w przeglądarce Microsoft Edge. Wprowadź nazwy rodzin pakietów, a następnie wybierz pozycję **Dodaj**. Wskazówki można znaleźć w temacie [Znajdowanie nazwy rodziny pakietów (PFN)](https://docs.microsoft.com/sccm/protect/deploy-use/find-a-pfn-for-per-app-vpn).

  Możesz również **zaimportować** plik CSV, który zawiera nazwy rodzin pakietów. Lub możesz **wyeksportować** wprowadzone nazwy rodzin pakietów.

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="network-proxy"></a>Serwer proxy sieci

Te ustawienia korzystają z [dostawcy usługi konfiguracji zasad NetworkProxy](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp), który zawiera również listę obsługiwanych wersji systemu Windows.

- **Automatycznie wykrywaj ustawienia serwera proxy**: ustawienie **Blokuj** wyłącza na urządzeniu funkcję automatycznego wykrywania skryptu automatycznej konfiguracji serwera proxy (PAC). Ustawienie **Nie skonfigurowano** (domyślne) włącza tę funkcję. Po włączeniu tego ustawienia urządzenie spróbuje znaleźć ścieżkę do skryptu PAC.
- **Użyj skryptu serwera proxy**: wybierz ustawienie **Zezwalaj**, aby wprowadzić ścieżkę do skryptu PAC i skonfigurować serwer proxy. Ustawienie **Nie skonfigurowano** (domyślne) nie umożliwia wprowadzenia adresu URL skryptu PAC.
  - **Adres URL skryptu konfiguracji**: wprowadź adres URL skryptu PAC, którego chcesz użyć do skonfigurowania serwera proxy.
- **Użyj ręcznego serwera proxy**: wybierz ustawienie **Zezwalaj**, aby ręcznie wprowadzić nazwę lub adres IP oraz numer portu TCP serwera proxy. Ustawienie **Nie skonfigurowano** (domyślne) nie umożliwia ręcznego wprowadzenia szczegółów serwera proxy.
  - **Adres**: wprowadź nazwę lub adres IP serwera proxy.
  - **Numer portu**: wprowadź numer portu serwera proxy.
  - **Wyjątki serwera proxy**: wprowadź wszystkie adresy URL, w przypadku których korzystanie z serwera proxy będzie zabronione. Rozdziel kolejne elementy średnikiem.
  - **Pomiń serwer proxy dla adresów lokalnych**: ustawienie **Nie skonfigurowano** (domyślne) uniemożliwia używanie serwera proxy dla adresów lokalnych w intranecie. Ustawienie **Zezwalaj** używa serwera proxy dla adresów lokalnych.

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="password"></a>Hasło

Te ustawienia korzystają z [dostawcy usługi konfiguracji zasad DeviceLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock), który zawiera również listę obsługiwanych wersji systemu Windows.

- **Hasło**: pozycja **Wymagaj** wymusza wprowadzanie hasła przez użytkownika końcowego w celu uzyskania dostępu do urządzenia. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na dostęp do urządzenia bez hasła. Dotyczy tylko kont lokalnych. Hasła do kont domeny pozostaną skonfigurowane przez Active Directory (AD) i Azure AD.

  - **Wymagany typ hasła**: wybierz typ hasła. Dostępne opcje:
    - **Nie skonfigurowano**: hasło może zawierać cyfry i litery.
    - **Numeryczne**: hasło może się składać tylko z cyfr.
    - **Alfanumeryczne**: hasło musi zawierać kombinację liter i cyfr.
  - **Minimalna długość hasła**: wprowadź minimalną liczbą wymaganych znaków z zakresu 4–16. Na przykład wprowadź `6`, aby wymagać hasła o długości co najmniej 6 znaków.
  
    > [!IMPORTANT]
    > Kiedy wymóg dotyczący hasła zostanie zmieniony na komputerze z systemem Windows, użytkownicy będą musieli się do niego dostosować przy następnym logowaniu, ponieważ to właśnie wtedy urządzenie przechodzi ze stanu bezczynności w stan aktywności. Użytkownicy, których hasła spełniają wymagania, także zostaną poproszeniu o zmianę hasła.
    
  - **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia**: wprowadź liczbę nieudanych prób uwierzytelniania dopuszczalnych, zanim zawartość urządzenia może zostać wyczyszczona (maksymalnie 11). Prawidłową liczbę, którą można wprowadzić zależy od wersji. [Dostawcy usług Kryptograficznych DeviceLock/MaxDevicePasswordFailedAttempts](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-maxdevicepasswordfailedattempts) zawiera listę obsługiwanych wartości. `0` (zero) może spowodować wyłączenie funkcji czyszczenia urządzenia.

    Wpływ tego ustawienia zależy również od wersji. Aby uzyskać szczegółowe informacje, zobacz artykuł [Dostawca usługi konfiguracji DeviceLock/MaxDevicePasswordFailedAttempts](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-maxdevicepasswordfailedattempts).

  - **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu**: określ, jak długo urządzenie musi pozostawać w stanie bezczynności, zanim ekran zostanie automatycznie zablokowany.
  - **Wygaśnięcie hasła (dni)** : określ liczbę dni, po której należy zmienić hasło urządzenia, z zakresu 1–365. Na przykład wprowadź liczbę `90`, aby hasło wygasało po 90 dniach.
  - **Zapobiegaj ponownemu użyciu starych haseł**: wprowadź liczbę poprzednio używanych haseł, których ponowne użycie nie jest możliwe, z zakresu 1–24. Na przykład wprowadź liczbę `5`, aby użytkownicy nie mogli ustawić nowego hasła, które jest takie samo jak bieżące hasło i 4 poprzednie hasła.
  - **Wymagaj hasła przy powrocie urządzenia ze stanu bezczynności** (urządzenia przenośne i holograficzne): wybierz ustawienie **Wymagaj**, aby użytkownicy musieli wprowadzić hasło w celu odblokowania urządzenia po stanie bezczynności. Ustawienie **Nie skonfigurowano** (domyślne) nie wymaga kodu PIN ani hasła, gdy urządzenie wznawia pracę po stanie bezczynności.
  - **Proste hasła**: wybierz ustawienie **Blokuj**, aby uniemożliwić użytkownikom tworzenie prostych haseł takich jak `1234` lub `1111`. Wybierz ustawienie **Nie skonfigurowano** (domyślne), aby umożliwić użytkownikom tworzenie haseł takich jak `1234` lub `1111`. To ustawienie zezwala również na używanie haseł obrazkowych systemu Windows lub blokuje tę możliwość.
- **Automatyczne szyfrowanie podczas AADJ**: opcja **Blokuj** uniemożliwia automatyczne szyfrowanie urządzenia za pomocą funkcji BitLocker podczas przygotowywania do pierwszego użycia, jeśli to urządzenie jest dołączone do usługi Azure AD. W przypadku wybrania opcji **Nieskonfigurowane** (ustawienie domyślnie) jest używane domyślne ustawienie systemu operacyjnego, które może zezwalać na szyfrowanie. Więcej informacji na temat [szyfrowania urządzenia za pomocą funkcji BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption).

  [Security/PreventAutomaticDeviceEncryptionForAzureADJoinedDevices CSP (Dostawca usługi konfiguracji Security/PreventAutomaticDeviceEncryptionForAzureADJoinedDevices)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-preventautomaticdeviceencryptionforazureadjoineddevices)

- **Zasady FIPS (Federal Information Processing Standard)** : po wybraniu opcji **Zezwalaj** są używane zasady FIPS, czyli opracowane przez rząd Stanów Zjednoczonych normy szyfrowania, wyznaczania wartości skrótu i podpisywania. W przypadku wybrania opcji **Nieskonfigurowane** (ustawienie domyślnie) jest używane domyślne ustawienie systemu operacyjnego, niekorzystające z zasad FIPS.

  [Cryptography/AllowFipsAlgorithmPolicy CSP (Dostawca usługi konfiguracji Cryptography/AllowFipsAlgorithmPolicy)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-cryptography#cryptography-allowfipsalgorithmpolicy)

- **Uwierzytelnianie urządzeń przy użyciu funkcji Windows Hello**: opcja **Zezwalaj** umożliwia użytkownikom logowanie się na komputerze z systemem Windows 10 za pomocą urządzenia towarzyszącego funkcji Windows Hello, na przykład telefonu, opaski treningowej lub urządzenia Internetu rzeczy (IoT). W przypadku wybrania opcji **Nieskonfigurowane** (ustawienie domyślnie) jest używane domyślne ustawienie systemu operacyjnego, które nie musi umożliwiać uwierzytelniania w systemie Windows za pomocą urządzeń towarzyszących funkcji Windows Hello.

  [Authentication/AllowSecondaryAuthenticationDevice CSP (Dostawca usługi konfiguracji Authentication/AllowSecondaryAuthenticationDevice)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowsecondaryauthenticationdevice)

- **Logowanie internetowe**: włącza obsługę logowania w systemie Windows dla dostawców innych niż dostawcy sfederowani usług ADFS (Active Directory Federation Services), na przykład SAML. Funkcja SAML obsługuje logowanie jednokrotne w przeglądarkach internetowych za pomocą bezpiecznych tokenów. Dostępne opcje:

  - **Nieskonfigurowane** (ustawienie domyślne): używa domyślnego ustawienia systemu operacyjnego na urządzeniu.
  - **Włączone**: włącza logowanie za pomocą internetowego dostawcy poświadczeń.
  - **Wyłączone**: wyłącza logowanie za pomocą internetowego dostawcy poświadczeń.

  [Authentication/EnableWebSignIn CSP (Dostawca usługi konfiguracji Authentication/EnableWebSignIn)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-enablewebsignin)

- **Preferowana domena dzierżawy usługi Azure AD**: wprowadź nazwę domeny, która istnieje w Twojej organizacji usługi Azure AD. Użytkownicy z tej domeny nie muszą podczas logowania wpisywać nazwy domeny. Na przykład wprowadź `contoso.com`. Użytkownicy w domenie `contoso.com` będą mogli zalogować się za pomocą samej nazwy użytkownika, na przykład `abby` zamiast `abby@contoso.com`.

  [Authentication/PreferredAadTenantDomainName CSP (Dostawca usługi konfiguracji Authentication/PreferredAadTenantDomainName)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-preferredaadtenantdomainname)

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="per-app-privacy-exceptions"></a>Wyjątki prywatności dla aplikacji

Możesz dodawać aplikacje, dla których chcesz określić inne zachowanie dotyczące prywatności niż zachowanie zdefiniowane w domyślnym ustawieniu prywatności.

- **Nazwa pakietu**: nazwa rodziny pakietów aplikacji.
- **Nazwa aplikacji**: nazwa aplikacji.

### <a name="exceptions"></a>Wyjątki

- **Informacje o koncie**: określ, czy ta aplikacja może uzyskiwać dostęp do nazwy użytkownika, zdjęcia oraz innych informacji kontaktowych.
- **Aplikacje w tle**: określ, czy ta aplikacja może działać w tle.
- **Kalendarz**: określ, czy ta aplikacja może uzyskiwać dostęp do kalendarza.
- **Historia połączeń**: określ, czy ta aplikacja może uzyskiwać dostęp do historii połączeń.
- **Aparat fotograficzny**: określ, czy ta aplikacja może uzyskiwać dostęp do aparatu fotograficznego.
- **Kontakty**: określ, czy ta aplikacja może uzyskiwać dostęp do kontaktów.
- **E-mail**: określ, czy ta aplikacja może uzyskiwać dostęp do wiadomości e-mail i je wysyłać.
- **Lokalizacja**: określ, czy ta aplikacja może uzyskiwać dostęp do informacji o lokalizacji.
- **Obsługa wiadomości**: określ, czy ta aplikacja może odczytywać lub wysyłać wiadomości tekstowe lub MMS.
- **Mikrofon**: określ, czy ta aplikacja może korzystać z mikrofonu.
- **Ruch**: określ, czy ta aplikacja może uzyskiwać dostęp do informacji o ruchu urządzenia.
- **Powiadomienia**: określ, czy ta aplikacja może uzyskiwać dostęp do powiadomień.
- **Telefon**: określ, czy ta aplikacja może uzyskiwać dostęp do telefonu.
- **Urządzenia radiowe**: niektóre aplikacje używają urządzeń radiowych (np. Bluetooth) w urządzeniu do wysyłania lub odbierania danych i muszą te urządzenia radiowe włączać lub wyłączać. Określ, czy ta aplikacja będzie mogła sterować tymi urządzeniami radiowymi.
- **Zadania**: określ, czy ta aplikacja może uzyskiwać dostęp do zadań.
- **Zaufane urządzenia**: określ, czy ta aplikacja może używać zaufanych urządzeń. Zaufane urządzenia to sprzęt, z którym już nawiązano połączenie, lub sprzęt dołączony do urządzenia. Jako zaufanych urządzeń można na przykład użyć telewizorów, projektorów itd.
- **Opinie i diagnostyka**: określ, czy ta aplikacja może uzyskiwać dostęp do informacji diagnostycznych.
- **Synchronizacja z urządzeniami**: wybierz, czy ta aplikacja może automatycznie udostępniać informacje i synchronizować je z urządzeniami bezprzewodowymi, które nie są jawnie sparowane z tym urządzeniem.

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="personalization"></a>Personalizacja

Te ustawienia korzystają z [dostawcy usługi konfiguracji zasad personalizacji](https://docs.microsoft.com/windows/client-management/mdm/personalization-csp), który zawiera również listę obsługiwanych wersji systemu Windows.

- **Adres URL obrazu tła pulpitu (tylko komputery)** : wprowadź adres URL obrazu w formacie jpg, jpeg lub png, który będzie używany jako tapeta pulpitu systemu Windows. Użytkownicy nie mogą zmieniać obrazu. Na przykład wprowadź `https://contoso.com/logo.png`.

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="printer"></a>Drukarka

- **Drukarki**: lista dodanych drukarek lokalnych.
- **Drukarka lokalna**: ustaw tę drukarkę jako domyślną.
- **Dostęp użytkownika pozwalający na dodanie nowych drukarek**: zezwala na korzystanie z drukarek lokalnych lub je blokuje.

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="privacy"></a>Ochrona prywatności

Te ustawienia korzystają z [dostawcy usługi konfiguracji zasad prywatności](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy), który zawiera również listę obsługiwanych wersji systemu Windows.

- **Personalizacja danych wejściowych**: ustawienie **Blokuj** uniemożliwia używanie poleceń głosowych w celu dyktowania i komunikowania się z Cortaną i innymi aplikacjami korzystającymi z rozpoznawania mowy opartego na chmurze firmy Microsoft. Ta funkcja jest wyłączona, a użytkownicy nie mogą włączyć rozpoznawania mowy online przy użyciu ustawień. Ustawienie **Nie skonfigurowano** (domyślne) daje użytkownikom wybór. Jeśli zezwolisz na te usługi, firma Microsoft może zbierać dane głosowe w celu usprawnienia świadczonej usługi.
- **Automatyczne akceptowanie w przypadku monitów o wyrażenie zgody przez użytkownika dotyczących parowania i prywatności**: wybierz ustawienie **Zezwalaj**, aby system Windows mógł automatycznie akceptować komunikaty dotyczące parowania i prywatności wyświetlane w uruchamianych aplikacjach. Ustawienie **Nie skonfigurowano** (domyślne) zapobiega automatycznemu akceptowaniu okna dotyczącego parowania i prywatności wyświetlanego w otwieranych aplikacjach.
- **Publikuj działania użytkownika**: ustawienie **Blokuj** uniemożliwia udostępnianie środowisk i odnajdywanie ostatnio używanych zasobów w kanale aktywności. Ustawienie **Nie skonfigurowano** (domyślne) włącza tę funkcję, aby aplikacje mogły publikować działania użytkownika końcowego.
- **Tylko działania lokalne**: pozycja **Blokuj** uniemożliwia udostępnianie środowisk i odnajdywanie ostatnio używanych zasobów w przełączniku zadań jedynie na podstawie działań lokalnych. Ustawienie **Nie skonfigurowano** (domyślne) włącza tę funkcję.

Można skonfigurować informacje, do których mogą uzyskiwać dostęp wszystkie aplikacje na urządzeniu. Ponadto należy zdefiniować wyjątki dla poszczególnych aplikacji, korzystając z opcji **Wyjątki prywatności dla aplikacji**.

Wybierz przycisk **OK**, aby zapisać zmiany.

### <a name="exceptions"></a>Wyjątki

- **Informacje o koncie**: określ, czy ta aplikacja może uzyskiwać dostęp do nazwy użytkownika, zdjęcia oraz innych informacji kontaktowych.
- **Aplikacje w tle**: określ, czy ta aplikacja może działać w tle.
- **Kalendarz**: określ, czy ta aplikacja może uzyskiwać dostęp do kalendarza.
- **Historia połączeń**: określ, czy ta aplikacja może uzyskiwać dostęp do historii połączeń.
- **Aparat fotograficzny**: określ, czy ta aplikacja może uzyskiwać dostęp do aparatu fotograficznego.
- **Kontakty**: określ, czy ta aplikacja może uzyskiwać dostęp do kontaktów.
- **E-mail**: określ, czy ta aplikacja może uzyskiwać dostęp do wiadomości e-mail i je wysyłać.
- **Lokalizacja**: określ, czy ta aplikacja może uzyskiwać dostęp do informacji o lokalizacji.
- **Obsługa wiadomości**: określ, czy ta aplikacja może odczytywać lub wysyłać wiadomości tekstowe lub MMS.
- **Mikrofon**: określ, czy ta aplikacja może korzystać z mikrofonu.
- **Ruch**: określ, czy ta aplikacja może uzyskiwać dostęp do informacji o ruchu urządzenia.
- **Powiadomienia**: określ, czy ta aplikacja może uzyskiwać dostęp do powiadomień.
- **Telefon**: określ, czy ta aplikacja może uzyskiwać dostęp do telefonu.
- **Urządzenia radiowe**: niektóre aplikacje używają urządzeń radiowych (np. Bluetooth) w urządzeniu do wysyłania lub odbierania danych i muszą te urządzenia radiowe włączać lub wyłączać. Określ, czy ta aplikacja będzie mogła sterować tymi urządzeniami radiowymi.
- **Zadania**: określ, czy ta aplikacja może uzyskiwać dostęp do zadań.
- **Zaufane urządzenia**: określ, czy ta aplikacja może używać zaufanych urządzeń. Zaufane urządzenia to sprzęt, z którym już nawiązano połączenie, lub sprzęt dołączony do urządzenia. Jako zaufanych urządzeń można na przykład użyć telewizorów, projektorów itd.
- **Opinie i diagnostyka**: określ, czy ta aplikacja może uzyskiwać dostęp do informacji diagnostycznych.
- **Synchronizacja z urządzeniami** — określ, czy ta aplikacja może automatycznie udostępniać informacje i synchronizować je z urządzeniami bezprzewodowymi, które nie są jawnie sparowane z tym komputerem, tabletem lub telefonem.

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="projection"></a>Projekcja

Te ustawienia korzystają z [dostawcy usługi konfiguracji zasad WirelessDisplay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wirelessdisplay), który zawiera również listę obsługiwanych wersji systemu Windows.

- **Dane wejściowe użytkownika z odbiorników ekranów bezprzewodowych**: ustawienie **Blokuj** blokuje dane wejściowe użytkownika z odbiorników ekranów bezprzewodowych. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia ekranowi bezprzewodowemu na wysyłanie danych wejściowych klawiatury, myszy, pióra i dotyku z powrotem do urządzenia źródłowego.
- **Projekcja na tym komputerze**: ustawienie **Blokuj** uniemożliwia innym urządzeniom odnajdywanie tego komputera dla celów projekcji. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia odnajdywanie urządzenia oraz projekcję na urządzeniu na ekranie blokady.
- **Wymagaj kodu PIN do parowania**: wybierz ustawienie **Wymagaj**, aby zawsze wyświetlać monit o kod PIN podczas nawiązywania połączenia z urządzeniem do projekcji. Ustawienie **Nie skonfigurowano** (domyślne) nie wymaga kodu PIN do parowania urządzenia z urządzeniem do projekcji.

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="reporting-and-telemetry"></a>Raportowanie i telemetria

- **Udostępnij dane użycia**: wybierz poziom przesyłanych danych diagnostycznych. Dostępne opcje:
  - **Nie skonfigurowano**: dane nie zostaną udostępnione.
  - **Bezpieczeństwo**: informacje wymagane do zwiększenia bezpieczeństwa systemu Windows, łącznie z danymi dotyczącymi ustawień składnika środowiska i telemetrii połączonego użytkownika, narzędzia do usuwania złośliwego oprogramowania i usługi Windows Defender.
  - **Podstawowy**: podstawowe informacje o urządzeniu, w tym dane dotyczące jakości, zgodność aplikacji, dane dotyczące użycia aplikacji i dane z poziomu Bezpieczeństwo.
  - **Ulepszony**: dodatkowe informacje szczegółowe, w tym: sposób używania systemów Windows i Windows Server, programu System Center i aplikacji oraz ich wydajność, zaawansowane dane dotyczące niezawodności oraz dane z poziomów Podstawowy i Bezpieczeństwo.
  - **Pełny**: wszystkie dane potrzebne do identyfikowania i rozwiązywania problemów oraz dane z poziomów Bezpieczeństwo, Podstawowy i Ulepszony.

  [Dostawca usługi konfiguracji System/AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry)

- **Wysyłanie danych przeglądania przeglądarki Microsoft Edge do usługi Microsoft 365 Analytics**: aby użyć tej funkcji, należy zdefiniować ustawienie **Udostępnij dane użycia** jako **Rozszerzone** lub **Pełne**. Ta funkcja kontroluje dane, które przeglądarka Microsoft Edge wysyła do usługi Microsoft 365 Analytics dla urządzeń firmowych przy użyciu skonfigurowanego identyfikatora komercyjnego. Dostępne opcje:
  - **Nieskonfigurowane**: używa domyślnego zachowania systemu operacyjnego, które może powodować, że żadne dane historii przeglądania nie będą wysyłane
  - **Wysyłaj tylko dane intranetowe**: umożliwia administratorowi wysyłanie historii danych intranetowych
  - **Wysyłaj tylko dane internetowe**: umożliwia administratorowi wysyłanie historii danych internetowych
  - **Wysyłaj dane intranetowe i internetowe**: umożliwia administratorowi wysyłanie historii danych intranetowych i internetowych

  [Dostawca usługi konfiguracji Browser/ConfigureTelemetryForMicrosoft365Analytics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-configuretelemetryformicrosoft365analytics)

- **Serwer proxy telemetrii**: wprowadź w pełni kwalifikowaną nazwę domeny (FQDN) lub adres IP serwera proxy do przekazywania żądań środowisk i telemetrii połączonego użytkownika przy użyciu połączenia SSL (Secure Sockets Layer). Format dla tego ustawienia to: *serwer*:*port*. Jeśli nazwany serwer proxy ulegnie awarii lub jeśli serwer proxy nie zostanie wprowadzony w momencie włączenia tych zasad, dane środowisk i telemetrii połączonego użytkownika nie zostaną wysłane i pozostaną na urządzeniu lokalnym.

  Przykładowe formaty:

  ```
  IPv4: 192.246.246.106:100
  IPv6: [2001:4898:4010:4013:95c1:a8b2:953c:c633]:100
  FQDN: www.contoso.com:345
  ```

  [Dostawca usługi konfiguracji System/TelemetryProxy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-telemetryproxy)

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="search"></a>Wyszukaj

Te ustawienia korzystają z [dostawcy usługi konfiguracji zasad wyszukiwania](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-search), który zawiera również listę obsługiwanych wersji systemu Windows. 

- **Bezpieczne wyszukiwanie (tylko urządzenia przenośne)** : pozwala określić sposób, w jaki Cortana filtruje treści dla dorosłych w wynikach wyszukiwania. Dostępne opcje:
  - **Zdefiniowane przez użytkownika**: zezwól użytkownikom końcowym na wybranie własnych ustawień.
  - **Ścisłe**: najwyższy poziom filtrowania pod kątem blokowania treści dla dorosłych.
  - **Umiarkowany**: umiarkowany poziom filtrowania pod kątem blokowania treści dla dorosłych. Prawidłowe wyniki wyszukiwania nie są filtrowane.
- **Wyświetl wyniki z Internetu w wyszukiwaniu**: po wybraniu ustawienia **Blokuj** użytkownicy nie będą mogli wykonywać wyszukiwania, a wyniki z Internetu nie będą wyświetlane. Ustawienie **Nie skonfigurowano** (domyślne) zezwala użytkownikom na wyszukiwanie w Internecie, a wyniki są wyświetlane na urządzeniu.

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="start"></a>Początek

Te ustawienia korzystają z [dostawcy usługi konfiguracji zasad uruchamiania](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-start), który zawiera również listę obsługiwanych wersji systemu Windows.  

- **Układ menu Start**: zastąp domyślny układ menu Start i dostosuj menu Start na komputerach. Przekaż plik XML zawierający dostosowania, w tym kolejność wyświetlania aplikacji i nie tylko. Użytkownicy nie mogą zmieniać wprowadzonego w ten sposób układu menu Start.
- **Przypinaj witryny internetowe do kafelków w menu Start**: zaimportuj obrazy z przeglądarki Microsoft Edge, które będą wyświetlane jako linki w menu Start systemu Windows dla urządzeń stacjonarnych.
- **Odpinanie aplikacji od paska zadań**: ustawienie **Blokuj** uniemożliwia użytkownikom odpinanie aplikacji od paska zadań. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia użytkownikom odpinanie aplikacji od paska zadań.
- **Szybkie przełączanie użytkowników**: ustawienie **Blokuj** uniemożliwia przełączanie się między zalogowanymi jednocześnie użytkownikami bez wylogowywania się. Ustawienie **Nie skonfigurowano** (domyślne) powoduje wyświetlanie pozycji **Przełącz użytkownika** na kafelku użytkownika.
- **Najczęściej używane aplikacje**: ustawienie **Blokuj** ukrywa najczęściej używane aplikacje w menu Start. Powoduje też wyłączenie odpowiedniego przełącznika w aplikacji Ustawienia. Ustawienie **Nie skonfigurowano** (domyślne) wyświetla najczęściej używane aplikacje.
- **Ostatnio dodane aplikacje**: ustawienie **Blokuj** ukrywa ostatnio dodane aplikacje w menu Start. Powoduje też wyłączenie odpowiedniego przełącznika w aplikacji Ustawienia. Ustawienie **Nie skonfigurowano** (domyślne) pokazuje ostatnio dodane aplikacje w menu Start.
- **Tryb ekranu startowego**: wybierz sposób wyświetlania ekranu startowego. Dostępne opcje:
  - **Zdefiniowane przez użytkownika**: nie wymusza rozmiaru ekranu startowego. Użytkownicy mogą ustawić rozmiar.
  - **Pełny ekran**: wymusza rozmiar pełnoekranowy ekranu startowego.
  - **Niepełny ekran**: wymuś rozmiar niepełnoekranowy ekranu startowego.
- **Ostatnio otwierane elementy list szybkiego dostępu**: ustawienie **Blokuj** ukrywa listy szybkiego dostępu do ostatnich elementów w menu Start i na pasku zadań. Powoduje też wyłączenie odpowiedniego przełącznika w aplikacji Ustawienia. Ustawienie **Nie skonfigurowano** (domyślne) pokazuje ostatnio otwierane elementy z listy szybkiego dostępu.
- **Lista aplikacji**: wybierz sposób wyświetlania list wszystkich aplikacji. Dostępne opcje:
  - **Zdefiniowane przez użytkownika**: nie jest wymuszane żadne ustawienie. Użytkownicy decydują o tym, jak lista aplikacji jest wyświetlana na urządzeniu.
  - **Zwiń**: ukryj listę wszystkich aplikacji.
  - **Zwiń i wyłącz aplikację Ustawienia**: ukryj listę wszystkich aplikacji i wyłącz opcję **Pokaż listę aplikacji w menu Start**  w aplikacji Ustawienia.
  - **Usuwa i wyłącza aplikację Ustawienia**: ukryj listę wszystkich aplikacji, usuń przycisk wszystkich aplikacji i wyłącz opcję **Pokaż listę aplikacji w menu Start**  w aplikacji Ustawienia.
- **Przycisk zasilania**: ustawienie **Blokuj** ukrywa przycisk zasilania w menu Start. Ustawienie **Nie skonfigurowano** (domyślne) powoduje wyświetlenie przycisku usypiania.
- **Kafelek użytkownika**: ustawienie **Blokuj** powoduje ukrycie kafelka użytkownika w menu Start. Ustawienie **Nie skonfigurowano** (domyślne) powoduje wyświetlenie kafelka użytkownika, a także ustawia następujące ustawienia:
  - **Blokada**: stawienie **Blokuj** powoduje ukrycie opcji **Blokada** na kafelku użytkownika w menu Start. Ustawienie **Nie skonfigurowano** (domyślne) powoduje wyświetlanie opcji **Blokada**.
  - **Wylogowanie**: stawienie **Blokuj** powoduje ukrycie opcji **Wylogowanie** na kafelku użytkownika w menu Start. Ustawienie **Nie skonfigurowano** (domyślne) powoduje wyświetlanie opcji **Wylogowanie**.
- **Zamknij**: ustawienie **Blokuj** powoduje ukrycie opcji **Zaktualizuj i zamknij** oraz **Zamknij** na przycisku zasilania w menu Start. Ustawienie **Nie skonfigurowano** (domyślne) powoduje wyświetlanie tych opcji.
- **Uśpij**: ustawienie **Blokuj** powoduje ukrycie opcji **Uśpij** na przycisku zasilania w menu Start. Ustawienie **Nie skonfigurowano** (domyślne) powoduje wyświetlanie tej opcji.
- **Hibernacja**: ustawienie **Blokuj** powoduje ukrycie opcji **Hibernacja** na przycisku zasilania w menu Start. Ustawienie **Nie skonfigurowano** (domyślne) powoduje wyświetlanie tej opcji.
- **Przełącz konto**: ustawienie **Blokuj** powoduje ukrycie opcji **Przełącz konto** na kafelku użytkownika w menu Start. Ustawienie **Nie skonfigurowano** (domyślne) powoduje wyświetlanie tej opcji.
- **Opcje ponownego uruchamiania**: ustawienie **Blokuj** powoduje ukrycie opcji **Zaktualizuj i uruchom ponownie** oraz **Uruchom ponownie** na przycisku zasilania w menu Start. Ustawienie **Nie skonfigurowano** (domyślne) powoduje wyświetlanie tych opcji.
- **Folder Dokumenty w menu Start**: pozwala ukryć lub pokazać folder Dokumenty w menu Start systemu Windows. Dostępne opcje:
  - **Nie skonfigurowano** (domyślne): żadne ustawienie nie jest wymuszane. Użytkownicy mogą wybrać, czy skrót ma być wyświetlany, czy ukrywany.
  - **Ukryj**: skrót jest ukryty, a ustawienie w aplikacji Ustawienia jest wyłączone.
  - **Pokaż**: skrót jest wyświetlany, a ustawienie w aplikacji Ustawienia jest wyłączone.
- **Folder Pliki do pobrania w menu Start**: pozwala ukryć lub pokazać folder pobranych plików w menu Start systemu Windows. Dostępne opcje:
  - **Nie skonfigurowano** (domyślne): żadne ustawienie nie jest wymuszane. Użytkownicy mogą wybrać, czy skrót ma być wyświetlany, czy ukrywany.
  - **Ukryj**: skrót jest ukryty, a ustawienie w aplikacji Ustawienia jest wyłączone.
  - **Pokaż**: skrót jest wyświetlany, a ustawienie w aplikacji Ustawienia jest wyłączone.
- **Eksplorator plików w menu Start**: pozwala ukryć lub pokazać Eksploratora plików w menu Start systemu Windows. Dostępne opcje:
  - **Nie skonfigurowano** (domyślne): żadne ustawienie nie jest wymuszane. Użytkownicy mogą wybrać, czy skrót ma być wyświetlany, czy ukrywany.
  - **Ukryj**: skrót jest ukryty, a ustawienie w aplikacji Ustawienia jest wyłączone.
  - **Pokaż**: skrót jest wyświetlany, a ustawienie w aplikacji Ustawienia jest wyłączone.
- **Grupa domowa w menu Start**: pozwala ukryć lub pokazać skrót Grupa domowa w menu Start systemu Windows. Dostępne opcje:
  - **Nie skonfigurowano** (domyślne): żadne ustawienie nie jest wymuszane. Użytkownicy mogą wybrać, czy skrót ma być wyświetlany, czy ukrywany.
  - **Ukryj**: skrót jest ukryty, a ustawienie w aplikacji Ustawienia jest wyłączone.
  - **Pokaż**: skrót jest wyświetlany, a ustawienie w aplikacji Ustawienia jest wyłączone.
- **Folder Muzyka w menu Start**: pozwala ukryć lub pokazać folder Muzyka w menu Start systemu Windows. Dostępne opcje:
  - **Nie skonfigurowano** (domyślne): żadne ustawienie nie jest wymuszane. Użytkownicy mogą wybrać, czy skrót ma być wyświetlany, czy ukrywany.
  - **Ukryj**: skrót jest ukryty, a ustawienie w aplikacji Ustawienia jest wyłączone.
  - **Pokaż**: skrót jest wyświetlany, a ustawienie w aplikacji Ustawienia jest wyłączone.
- **Sieć w menu Start**: pozwala ukryć lub pokazać skrót Sieć w menu Start systemu Windows. Dostępne opcje:
  - **Nie skonfigurowano** (domyślne): żadne ustawienie nie jest wymuszane. Użytkownicy mogą wybrać, czy skrót ma być wyświetlany, czy ukrywany.
  - **Ukryj**: skrót jest ukryty, a ustawienie w aplikacji Ustawienia jest wyłączone.
  - **Pokaż**: skrót jest wyświetlany, a ustawienie w aplikacji Ustawienia jest wyłączone.
- **Folder Osobiste w menu Start**: pozwala ukryć lub pokazać folder Osobiste w menu Start systemu Windows. Dostępne opcje:
  - **Nie skonfigurowano** (domyślne): żadne ustawienie nie jest wymuszane. Użytkownicy mogą wybrać, czy skrót ma być wyświetlany, czy ukrywany.
  - **Ukryj**: skrót jest ukryty, a ustawienie w aplikacji Ustawienia jest wyłączone.
  - **Pokaż**: skrót jest wyświetlany, a ustawienie w aplikacji Ustawienia jest wyłączone.
- **Folder Obrazy w menu Start**: pozwala ukryć lub pokazać folder obrazów w menu Start systemu Windows. Dostępne opcje:
  - **Nie skonfigurowano** (domyślne): żadne ustawienie nie jest wymuszane. Użytkownicy mogą wybrać, czy skrót ma być wyświetlany, czy ukrywany.
  - **Ukryj**: skrót jest ukryty, a ustawienie w aplikacji Ustawienia jest wyłączone.
  - **Pokaż**: skrót jest wyświetlany, a ustawienie w aplikacji Ustawienia jest wyłączone.
- **Ustawienia w menu Start**: pozwala ukryć lub pokazać skrót Ustawienia w menu Start systemu Windows. Dostępne opcje:
  - **Nie skonfigurowano** (domyślne): żadne ustawienie nie jest wymuszane. Użytkownicy mogą wybrać, czy skrót ma być wyświetlany, czy ukrywany.
  - **Ukryj**: skrót jest ukryty, a ustawienie w aplikacji Ustawienia jest wyłączone.
  - **Pokaż**: skrót jest wyświetlany, a ustawienie w aplikacji Ustawienia jest wyłączone.
- **Folder Wideo w menu Start**: pozwala ukryć lub pokazać folder Wideo w menu Start systemu Windows. Dostępne opcje:
  - **Nie skonfigurowano** (domyślne): żadne ustawienie nie jest wymuszane. Użytkownicy mogą wybrać, czy skrót ma być wyświetlany, czy ukrywany.
  - **Ukryj**: skrót jest ukryty, a ustawienie w aplikacji Ustawienia jest wyłączone.
  - **Pokaż**: skrót jest wyświetlany, a ustawienie w aplikacji Ustawienia jest wyłączone.

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="windows-defender-smart-screen"></a>Windows Defender SmartScreen

- **Filtr SmartScreen dla przeglądarki Microsoft Edge**: ustawienie **Wymagaj** powoduje wyłączenie filtra SmartScreen w usłudze Windows Defender i uniemożliwia użytkownikom włączenie go. Ustawienie **Nie skonfigurowano** (domyślne) powoduje włączenie filtru SmartScreen. Pomaga chronić użytkowników przed potencjalnymi zagrożeniami i uniemożliwia użytkownikom wyłączenie go.

  Przeglądarka Microsoft Edge używa filtra SmartScreen w usłudze Windows Defender, aby chronić użytkowników przed potencjalnym wyłudzeniem informacji i złośliwym oprogramowaniem.

  [Dostawca usługi konfiguracji Browser/AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen)

- **Dostęp do złośliwych witryn**: ustawienie **Blokuj** uniemożliwia użytkownikom ignorowanie ostrzeżeń filtru SmartScreen w usłudze Windows Defender oraz przechodzenia do witryny. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia użytkownikom zignorowanie ostrzeżeń i przejście do witryny.

  [Dostawca usługi konfiguracji Browser/PreventSmartScreenPromptOverride](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverride)

- **Pobieranie niezweryfikowanych plików**: ustawienie **Blokuj** uniemożliwia użytkownikom ignorowanie ostrzeżeń filtru SmartScreen w usłudze Windows Defender oraz pobieranie niezweryfikowanych plików. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia użytkownikom zignorowanie ostrzeżeń i pobranie niezweryfikowanych plików.

  [Dostawca usługi konfiguracji Browser/PreventSmartScreenPromptOverrideForFiles](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverrideforfiles)

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="windows-spotlight"></a>W centrum uwagi Windows

Te ustawienia korzystają z [dostawcy usługi konfiguracji zasad środowiska](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience), który zawiera również listę obsługiwanych wersji systemu Windows.

- **W centrum uwagi Windows** ustawienie **Blokuj** powoduje wyłączenie wszystkich funkcji W centrum uwagi Windows na ekranie blokady, wskazówek dotyczących systemu Windows, funkcji firmy Microsoft dla konsumentów i innych powiązanych funkcji. Jeśli Twoim celem jest zminimalizowanie ruchu sieciowego z urządzeń, wybierz ustawienie **Blokuj**. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na funkcje W centrum uwagi Windows i kontrolowanie przez użytkowników końcowych. Po włączeniu możesz również zablokować lub zezwolić na następujące ustawienia:

  - **Funkcja W centrum uwagi Windows na ekranie blokady**: ustawienie **Blokuj** wyłącza wyświetlania informacji funkcji W centrum uwagi Windows na ekranie blokady urządzenia. Ustawienie **Nie skonfigurowano** (domyślne) włącza tę funkcję.
  - **Sugestie innych firm w funkcji W centrum uwagi Windows**: ustawienie **Blokuj** wyłącza sugerowanie zawartości niepochodzącej od firmy Microsoft przez funkcję W centrum uwagi Windows. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na sugestie dotyczące aplikacji i zawartości pochodzące od innych wydawców oprogramowania w funkcjach W centrum uwagi Windows, takich jak W centrum uwagi na ekranie blokady, sugerowane aplikacje w menu Start i porady dotyczące systemu Windows.
  - **Funkcje dla konsumentów**: ustawienie **Blokuj** wyłącza funkcje przeznaczone zwykle tylko dla konsumentów, takie jak sugestie w menu Start, powiadomienia dotyczące członkostwa, instalacja aplikacji po uruchomieniu środowiska OOBE i kafelki przekierowania. Pozycja **Nieskonfigurowane** (wartość domyślna) zezwala na te funkcje.
  - **Wskazówki dotyczące systemu Windows**: ustawienie **Blokuj** wyłącza wyskakujące wskazówki dotyczące Windows. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na wyświetlanie wskazówek.
  - **Funkcja W centrum uwagi Windows w Centrum akcji**: ustawienie **Blokuj** zapobiega wyświetlaniu powiadomień funkcji W centrum uwagi Windows w Centrum akcji. Po wybraniu ustawienia **Nie skonfigurowano** (domyślnego) mogą być wyświetlane powiadomienia w Centrum akcji, które sugerują aplikacje lub funkcje pozwalające zwiększyć produktywność użytkowników w systemie Windows.
  - **Personalizacja funkcji W centrum uwagi Windows**: ustawienie **Bloku** uniemożliwia systemowi Windows używanie danych diagnostycznych w celu zapewniania dostosowanych środowisk dla użytkownika. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia firmie Microsoft używanie danych diagnostycznych w celu zapewnienia spersonalizowanych zaleceń, wskazówek i ofert dostosowanych do potrzeb użytkownika systemu Windows.
  - **Środowisko powitalne systemu Windows**: ustawienie **Blokuj** powoduje wyłączenie środowiska powitalnego systemu Windows w funkcji W centrum uwagi Windows. Środowisko powitalne systemu Windows nie będzie wyświetlane, gdy są dostępne aktualizacje i zmiany systemu Windows i jego aplikacji. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na wyświetlanie środowiska powitalnego systemu Windows, w którym są widoczne informacje o nowych lub zaktualizowanych funkcjach.

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="windows-defender-antivirus"></a>Program antywirusowy Windows Defender

Te ustawienia korzystają z [dostawcy usługi konfiguracji zasad usługi Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender), który zawiera również listę obsługiwanych wersji systemu Windows.

- **Monitorowanie w czasie rzeczywistym**: ustawienie **Włącz** uniemożliwia skanowanie w czasie rzeczywistym w poszukiwaniu złośliwego oprogramowania, programów szpiegujących i innego niepożądanego oprogramowania. Ustawienie **Nie skonfigurowano** (domyślne) zezwala na korzystanie z tej funkcji.
- **Monitorowanie zachowania**: ustawienie **Włącz** uniemożliwia usłudze Defender sprawdzanie urządzeń pod kątem określonych wzorców podejrzanej aktywności. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia usłudze Windows Defender monitorowanie zachowania.
- **Network Inspection System (NIS)** : pomaga w ochronie urządzeń przed sieciowymi atakami wykorzystującymi luki w zabezpieczeniach. System NIS korzysta z sygnatur znanych luk w zabezpieczeniach z centrum programu Microsoft Endpoint Protection, co pomaga wykrywać i blokować złośliwy ruch.
- **Skanuj wszystkie pobrane pliki**: określa, czy usługa Defender ma skanować wszystkie pliki pobierane z Internetu.
- **Skanuj skrypty ładowane w przeglądarkach internetowych firmy Microsoft**: ustawienie **Nie skonfigurowano** (domyślne) umożliwia usłudze Defender skanowanie skryptów używanych przez przeglądarkę Internet Explorer. Ustawienie **Włącz** uniemożliwia przeprowadzenie tego skanowania.
- **Dostęp użytkownika końcowego do usługi Defender**: ustawienie **Blokuj** ukrywa interfejs użytkownika usługi Windows Defender przed użytkownikami końcowymi. Wszystkie powiadomienia usługi Windows Defender również są pomijane. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia użytkownikom uzyskiwanie dostępu do interfejsu użytkownika usługi Windows Defender. Zmiany tego ustawienia zostaną wprowadzone po następnym ponownym uruchomieniu komputera użytkownika.
- **Interwał aktualizacji sygnatur (w godzinach)** : wprowadź interwał sprawdzania dostępności nowych plików sygnatur przez usługę Defender z zakresu 0–24. Dostępne opcje:

  - **Nie skonfigurowano** (wartość domyślna)
  - **Nie sprawdzaj**: usługa Defender nie sprawdza dostępności nowych plików sygnatur.
  - **1–24**: `1` — sprawdza co godzinę `2` — sprawdza co dwie godziny `24` — sprawdza, czy każdy dzień i tak dalej.
- **Monitoruj działanie plików i programów**: zezwala usłudze Defender na monitorowanie działania plików i programów na urządzeniach.
- **Dni przed usunięciem złośliwego oprogramowania poddanego kwarantannie**: umożliwia kontynuowanie śledzenia wykrytego złośliwego oprogramowania przez wprowadzoną liczbę dni, co pozwala ręcznie sprawdzać urządzenia, które wcześniej zostały zainfekowane. Jeśli liczba dni zostanie ustawiona na **0**, złośliwe oprogramowanie pozostanie w folderze kwarantanny i nie będzie automatycznie usuwane. Po ustawieniu wartości `90` elementy poddane kwarantannie są przechowywane w systemie przez 90 dni, po czym są usuwane.
- **Limit wykorzystania procesora CPU podczas skanowania**: ogranicz użycie procesora dozwolone dla procesów skanowania w skali od **1** do **100**.
- **Skanuj pliki archiwów**: ustawienie **Włącz** uniemożliwia usłudze Defender skanowanie plików zarchiwizowanych, na przykład plików zip i cab. Ustawienie **Nie skonfigurowano** (domyślne) umożliwia to skanowanie.
- **Skanuj przychodzące wiadomości e-mail**: ustawienie **Włącz** umożliwia usłudze Defender skanowanie wiadomości e-mail dostarczanych do urządzenia. Ustawienie **Nie skonfigurowano** (domyślne) uniemożliwia skanowanie wiadomości e-mail.
- **Skanuj dyski wymienne podczas pełnego skanowania**: ustawienie **Włącz** uniemożliwia pełne skanowanie dysków wymiennych. Ustawienie **Nie skonfigurowane** (domyślne) umożliwia usłudze Defender skanowanie dysków wymiennych, na przykład dysków USB.
- **Skanuj zamapowane dyski sieciowe podczas pełnego skanowania**: ustawienie **Włącz** umożliwia usłudze Defender skanowanie plików na zamapowanych dyskach sieciowych. Ustawienie **Nie skonfigurowano** (domyślne) uniemożliwia pełne skanowanie. Jeśli pliki na dysku są plikami tylko do odczytu, usługa Defender nie będzie mogła usunąć z nich wykrytego złośliwego oprogramowania.
- **Skanuj pliki otwierane z folderów sieciowych**: ustawienie **Nie skonfigurowano** (domyślne) umożliwia usłudze Defender skanowanie plików na udostępnionych dyskach sieciowych takich jak dyski dostępne za pośrednictwem ścieżki UNC. Ustawienie **Włącz** uniemożliwia przeprowadzenie tego skanowania. Jeśli pliki na dysku są plikami tylko do odczytu, usługa Defender nie będzie mogła usunąć z nich wykrytego złośliwego oprogramowania.
- **Ochrona w chmurze**: ustawienie **Nie skonfigurowano** (domyślne) umożliwia usłudze Microsoft Active Protection odbieranie informacji o działaniu złośliwego oprogramowania z zarządzanych urządzeń. Ustawienie **Włącz** blokuje tę funkcję.
- **Monituj użytkowników przed przesłaniem próbki**: określa, czy do firmy Microsoft są automatycznie wysyłane potencjalnie złośliwe pliki, które mogą wymagać dalszej analizy. Dostępne opcje:
  - **Nieskonfigurowany**
  - **Zawsze pytaj**
  - **Pytaj przed wysłaniem danych osobistych**
  - **Nigdy nie wysyłaj danych**
  - **Wyślij wszystkie dane bez pytania**: dane są wysyłane automatycznie

- **Godzina przeprowadzania codziennego szybkiego skanowania**: wybierz godzinę uruchomienia codziennego szybkiego skanowania. W przypadku wybrania opcji **Nieskonfigurowane** codzienne skanowanie nie będzie uruchamiane. Jeśli chcesz bardziej szczegółowo dostosować ustawienia, skonfiguruj ustawienie **Typ skanowania systemu do wykonania**.

  [Defender/ScheduleQuickScanTime CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime) (Zasady zabezpieczeń zawartości Defender/ScheduleQuickScanTime)

  > [!WARNING]
  > To ustawienie w usłudze Intune w witrynie Azure Portal może pokazywać stan niepowodzenia. Jest to błąd funkcji raportowania. Po odtworzeniu tego zachowania i rozwiązaniu problemu grupa produktów usługi Intune potwierdziła, że rzeczywisty stan to Powodzenie. Błąd dotyczący raportowania zostanie naprawiony w kolejnej wersji. Szacowany czas udostępnienia nowej wersji nie jest znany, ponieważ terminy ulegają zmianom. Wszelkie aktualizacje dla tej funkcji są ogłaszane na stronie [Funkcje usługi Microsoft Intune w trakcie opracowywania](in-development.md).

- **Typ skanowania systemu do wykonania**: umożliwia zaplanowanie skanowania systemu, w tym poziomu skanowania oraz dnia i godziny uruchomienia skanowania. Dostępne opcje:
  - **Nieskonfigurowane**: skanowanie systemu na urządzeniu nie jest zaplanowane. Użytkownicy końcowi mogą ręcznie uruchamiać skanowanie na urządzeniu stosownie do potrzeb lub oczekiwań.
  - **Wyłącz**: wyłącza wszelkie skanowanie systemu na urządzeniu. Wybierz tę opcję, jeśli korzystasz z partnerskiego rozwiązania antywirusowego, które skanuje urządzenia.
  - **Szybkie skanowanie**: obejmuje lokalizacje, w których najczęściej rejestruje się złośliwe oprogramowanie, na przykład klucze rejestru i znane foldery uruchamiania systemu Windows.
    - **Zaplanowany dzień**: wybierz dzień uruchomienia skanowania.
    - **Zaplanowana godzina**: wybierz godzinę uruchomienia skanowania.
  - **Pełne skanowanie**: obejmuje lokalizacje, w których najczęściej rejestruje się złośliwe oprogramowanie, oraz wszystkie pliki i foldery na urządzeniu.
    - **Zaplanowany dzień**: wybierz dzień uruchomienia skanowania.
    - **Zaplanowana godzina**: wybierz godzinę uruchomienia skanowania.

  To ustawienie może spowodować konflikt z ustawieniem **Godzina przeprowadzania codziennego szybkiego skanowania**. Niektóre rekomendacje:

  - Aby uruchomić codzienne szybkie skanowanie, skonfiguruj ustawienie **Godzina przeprowadzania codziennego szybkiego skanowania**.
  - Aby uruchomić codzienne szybkie skanowanie i pełne skanowanie co tydzień, skonfiguruj ustawienie **Godzina przeprowadzania codziennego szybkiego skanowania**. W obszarze **Typ skanowania systemu do wykonania** wybierz Pełne skanowanie wraz z datą i godziną.
  - Nie należy konfigurować ustawienia **Godzina przeprowadzania codziennego szybkiego skanowania** jednocześnie z opcją **Szybkie skanowanie** w ustawieniu **Typ skanowania systemu do wykonania**. Może to powodować konflikt ustawień i nieuruchomienie skanowania.
  - Aby uruchamiać szybkie skanowanie co wtorek o 6 rano, skonfiguruj tylko ustawienie **Typ skanowania systemu do wykonania**.

  [Defender/ScanParameter CSP (Dostawca usługi konfiguracji Defender/ScanParameter)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-scanparameter)  
  [Defender/ScheduleScanDay CSP (Dostawca usługi konfiguracji Defender/ScheduleScanDay)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescanday)  
  [Defender/ScheduleScanTime CSP (Dostawca usługi konfiguracji Defender/ScheduleScanTime)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescantime)

  > [!WARNING]
  > To ustawienie w usłudze Intune w witrynie Azure Portal może pokazywać stan niepowodzenia. Jest to błąd funkcji raportowania. Po odtworzeniu tego zachowania i rozwiązaniu problemu grupa produktów usługi Intune potwierdziła, że rzeczywisty stan to Powodzenie. Błąd dotyczący raportowania zostanie naprawiony w kolejnej wersji. Szacowany czas udostępnienia nowej wersji nie jest znany, ponieważ terminy ulegają zmianom. Wszelkie aktualizacje dla tej funkcji są ogłaszane na stronie [Funkcje usługi Microsoft Intune w trakcie opracowywania](in-development.md).

- **Wykrywaj potencjalnie niepożądane aplikacje**: pozwala wybrać poziom ochrony w przypadku wykrycia potencjalnie niechcianych aplikacji przez system Windows. Dostępne opcje:
  - **Nie skonfigurowano** (ustawienie domyślne): ochrona usługi Windows Defender przed potencjalnie niepożądanymi aplikacjami jest wyłączona.
  - **Blokuj**: usługa Windows Defender wykrywa potencjalnie niepożądane aplikacje, a wykryte elementy są blokowane. Te elementy są wyświetlane w historii wraz z innymi zagrożeniami.
  - **Inspekcja**: usługa Windows Defender wykrywa potencjalnie niepożądane aplikacje, ale nie podejmuje żadnych działań. Możesz przejrzeć informacje o aplikacjach, wobec których usługa Windows Defender podjęłaby działanie. Możesz na przykład wyszukać zdarzenia utworzone przez usługę Windows Defender w Podglądzie zdarzeń.

  Aby uzyskać więcej informacji dotyczących potencjalnie niepożądanych aplikacji, zobacz temat [Wykrywanie i blokowanie potencjalnie niepożądanych aplikacji](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus).

- **Akcje do podjęcia wobec wykrytych zagrożeń związanych ze złośliwym oprogramowaniem**: wybierz akcje, które ma podejmować usługa Defender po wykryciu zagrożenia określonego poziomu, takiego jak: niski, umiarkowany, wysoki i poważny. Jeśli nie będzie to możliwe, usługa Windows Defender wybierze najlepszą opcję pozwalającą na wyeliminowanie zagrożenia. Dostępne opcje:
  - **Wyczyść**
  - **Kwarantanna**
  - **Usuń**
  - **Zezwalaj**
  - **Zdefiniowane przez użytkownika**
  - **Zablokuj**

Wybierz przycisk **OK**, aby zapisać zmiany.

### <a name="windows-defender-antivirus-exclusions"></a>Wyjątki programu antywirusowego Windows Defender

- **Pliki i foldery do wyłączenia ze skanów i ochrony w czasie rzeczywistym**: umożliwia dodanie do listy wykluczeń pojedynczych plików lub folderów lub większej ich liczby, na przykład **C:\ścieżka** lub **%ProgramFiles%\ścieżka\nazwa_pliku.exe**. Te pliki i foldery nie są uwzględniane podczas skanowania w czasie rzeczywistym ani zaplanowanego skanowania.
- **Rozszerzenia plików do wyłączenia ze skanów i ochrony w czasie rzeczywistym**: umożliwia dodanie do listy wykluczeń pojedynczych rozszerzeń plików lub większej ich liczby, np. **JPG** lub **TXT**. Żadne pliki z tymi rozszerzeniami nie będą uwzględniane podczas skanowania w czasie rzeczywistym lub skanowania planowanego.
- **Procesy do wyłączenia ze skanów i ochrony w czasie rzeczywistym**: umożliwia dodanie do listy wykluczeń pojedynczych procesów typu **EXE**, **COM** lub **SCR** lub większej ich liczby. Te procesy nie są uwzględniane podczas skanowania w czasie rzeczywistym ani podczas zaplanowanego skanowania.

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="next-steps"></a>Następne kroki

Dodatkowe szczegóły techniczne poszczególnych ustawień oraz obsługiwanych wersji systemu Windows można znaleźć w [dokumentacji dotyczącej dostawcy usługi konfiguracji dla zasad systemu Windows 10](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)
