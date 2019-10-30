---
title: Konfigurowanie aplikacji Microsoft Managed Home Screen
titleSuffix: Microsoft Intune
description: Dowiedz się, jak skonfigurować aplikację Microsoft Managed Home Screen.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 865c7f03-f525-4dfa-b3a8-d088a9106502
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e97e88ad78e1b914543b7fa283f47863dce185fc
ms.sourcegitcommit: 25acfc88b366d2da71c37d354a0238e4f1168325
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2019
ms.locfileid: "72813481"
---
# <a name="configure-the-microsoft-managed-home-screen-app-for-android-enterprise"></a>Konfigurowanie aplikacji Microsoft Managed Home Screen dla rozwiązania Android Enterprise

Managed Home Screen to aplikacja używana dla należących do firmy dedykowanych urządzeń z rozwiązaniem Android Enterprise zarejestrowanych za pomocą usługi Intune i działających w trybie kiosku z wieloma aplikacjami. Dla tych urządzeń aplikacja Managed Home Screen działa jako obszar, z którego można uruchamiać inne zatwierdzone aplikacje. Aplikacja Managed Home Screen umożliwia administratorom IT dostosowywanie urządzeń i ograniczanie funkcji, do których użytkownik końcowy może uzyskać dostęp. 

## <a name="when-to-configure-the-microsoft-managed-home-screen-app"></a>Kiedy należy skonfigurować aplikację Microsoft Managed Home Screen

Zazwyczaj, jeśli ustawienia są dostępne za pośrednictwem konfiguracji urządzenia, należy je konfigurować tam. W ten sposób oszczędza się czas, minimalizuje liczbę błędów i uzyskuje lepsze wsparcie ze strony usługi Intune. Jednak niektóre ustawienia aplikacji Managed Home Screen są obecnie dostępne wyłącznie za pośrednictwem bloku **Zasady konfiguracji aplikacji** w konsoli usługi Intune. Z tego dokumentu dowiesz się, jak skonfigurować różne ustawienia przy użyciu projektanta konfiguracji albo skryptu JSON. 

> [!NOTE]
> Obecnie jest możliwe (i zalecane) ustawianie dozwolonych aplikacji i przypiętych linków internetowych za pośrednictwem pozycji **Aplikacje klienckie** i **Konfiguracja urządzenia**. Aby uzyskać pełną listę ustawień dostępnych w pozycji **Konfiguracja urządzenia** i mających wpływ na aplikację Managed Home Screen, zobacz [Ustawienia dedykowanego urządzenia](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings).  

Po pierwsze przejdź do konsoli usługi Intune w witrynie Azure Portal, a następnie przejdź do pozycji **Aplikacje klienckie** > **Zasady konfiguracji aplikacji**. Dodaj zasady konfiguracji dla **urządzeń zarządzanych** z systemem **Android**, a następnie wybierz pozycję **Managed Home Screen** jako skojarzoną aplikację. Kliknij pozycję **Ustawienia konfiguracji**, aby skonfigurować różne dostępne ustawienia aplikacji Managed Home Screen. 

## <a name="choosing-a-configuration-settings-format"></a>Wybieranie formatu ustawień konfiguracji

Istnieją dwie metody, których można użyć do definiowania ustawień konfiguracji dla aplikacji Managed Home Screen:

- **Projektant konfiguracji** pozwala na konfigurowanie ustawień za pomocą łatwego w użyciu interfejsu użytkownika umożliwiającego włączanie lub wyłączanie funkcji i ustawianie wartości. W przypadku tej metody istnieje kilka wyłączonych kluczy konfiguracji z typem wartości `BundleArray`. Te klucze konfiguracji można skonfigurować tylko przez wprowadzanie danych JSON. 
- **Dane JSON** pozwalają na zdefiniowanie wszystkich możliwych kluczy konfiguracji za pomocą skryptu JSON. 

Jeśli dodasz właściwości za pomocą projektanta konfiguracji, możesz automatycznie przekonwertować te właściwości do formatu JSON, wybierając pozycję **Wprowadź dane JSON** z listy rozwijanej **Format ustawień konfiguracji**.

![Zrzut ekranu przedstawiający opcje formatowania ustawień konfiguracji](./media/app-configuration-managed-home-screen-app/app-configuration-managed-home-screen-app_01.png)

## <a name="using-configuration-designer"></a>Korzystanie z projektanta konfiguracji

Projektant konfiguracji umożliwia wybieranie wstępnie wypełnionych ustawień i ich skojarzonych wartości. 

![Zrzut ekranu przedstawiający dodane ustawienia konfiguracji](./media/app-configuration-managed-home-screen-app/app-configuration-managed-home-screen-app_02.png)

Poniższa tabela zawiera listę dostępnych kluczy konfiguracji aplikacji Managed Home Screen, typów wartości, wartości domyślnych i opisów. Opis zawiera oczekiwane zachowanie urządzenia w zależności od wybranych wartości. Klucze konfiguracji, które są wyłączone w projektancie konfiguracji, nie są wymienione w tabeli.

| Klucz konfiguracji | Typ wartości | Wartość domyślna | Opis |
|---------------------------------------------------------------------------------------------------------------------------|-------------|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Set Grid Size (Ustaw rozmiar siatki) | ciąg | Automatycznie | Umożliwia ustawienie rozmiaru siatki dla aplikacji, które mają zostać umieszczone na zarządzanym ekranie głównym. Możesz ustawić liczbę wierszy i kolumn aplikacji, aby zdefiniować rozmiar siatki w następującym formacie: `columns;rows`. Jeśli zdefiniujesz rozmiar siatki, maksymalną liczbą aplikacji, które będą wyświetlane w wierszu na ekranie głównym, będzie liczba ustawionych wierszy, a maksymalną liczbą aplikacji, które będą wyświetlane w kolumnie ekranu głównego, będzie ustawiona liczba kolumn. |
| Enable notifications badge (Włącz wskaźnik powiadomień) | wartość logiczna | FAŁSZ | Włącza dla ikon aplikacji wskaźnik powiadomień z liczbą nowych powiadomień w aplikacji. Jeśli to ustawienie zostanie włączone, użytkownicy końcowi będą widzieli wskaźniki powiadomień dla aplikacji z nieprzeczytanymi powiadomieniami. Pozostawienie tego klucza konfiguracji wyłączonego spowoduje, że użytkownik końcowy nie zobaczy żadnych wskaźników powiadomień powiązanych z aplikacjami, w których mogą być nieprzeczytane powiadomienia. |
| Lock Home Screen (Blokuj ekran główny) | wartość logiczna | PRAWDA | Usuwa użytkownikowi końcowemu możliwość przechodzenia między ikonami aplikacji na ekranie głównym. Po włączeniu tego klucza konfiguracji ikony aplikacji na ekranie głównym zostaną zablokowane, a użytkownik końcowy nie będzie mógł ich przeciągać i upuszczać w innych miejscach siatki ekranu głównego. Jeśli zostanie ustawiona wartość `false`, użytkownicy końcowi będą mogli przechodzić między ikonami aplikacji i linków internetowych na zarządzanym ekranie głównym.  |
| Set device wall paper (Ustaw tapetę urządzenia) | ciąg | Domyślny | Umożliwia ustawienie tapety wybranej przez użytkownika poprzez wprowadzenie adresu URL obrazu, który chcesz ustawić jako tapetę. |
| Set app icon size (Ustaw rozmiar ikony aplikacji) | liczba całkowita | 2 | Umożliwia ustawienie rozmiaru ikony dla aplikacji wyświetlanych na ekranie głównym. Możesz wybrać następujące wartości w tej konfiguracji dla różnych rozmiarów: 0 (najmniejsza), 1 (mała), 2 (zwykła), 3 (duża) i 4 (największa). |
| Set app folder icon (Ustaw ikonę folderu aplikacji) | liczba całkowita | 0 | Pozwala zdefiniować wygląd folderów aplikacji na ekranie głównym. Wygląd można wybrać spośród następujących wartości: Ciemny kwadrat (0); ciemne koło (1); jasny kwadrat (2); jasne koło (3). |
| Set screen orientation (Ustaw orientację ekranu) | liczba całkowita | 1 | Pozwala ustawić orientację ekranu głównego jako poziomą lub pionową albo zezwolić na automatyczne obracanie. Możesz ustawić orientację, wprowadzając wartość 1 (tryb pionowy), 2 (tryb poziomy) lub 3 (automatyczne obracanie). |
| Enable device telemetry (Włącz telemetrię urządzenia) | wartość logiczna | FAŁSZ | Włącza wszystkie dane telemetryczne przechwytywane dla zarządzanego ekranu głównego. Jeśli to włączysz, firma Microsoft będzie mogła przechwytywać dane telemetryczne użycia urządzenia, takie jak liczba uruchomień konkretnej aplikacji na tym urządzeniu. |
| Set allow-listed applications (Ustaw dozwolone aplikacje) | bundleArray | FAŁSZ | Umożliwia wybranie zestawu aplikacji widocznych na ekranie głównym spośród aplikacji zainstalowanych na urządzeniu. Aplikacje możesz określić, wprowadzając nazwę pakietu dla aplikacji, którą chcesz wyświetlać — na przykład com.microsoft.emmx spowoduje udostępnienie ustawień na ekranie głównym. Aplikacje dozwolone w tej sekcji powinny już być zainstalowane na urządzeniu, aby były widoczne na ekranie głównym. |
| Set pinned web links (Ustaw przypięte linki internetowe) | bundleArray | FAŁSZ | Umożliwia przypięcie witryn internetowych jako ikon szybkiego uruchamiania na ekranie głównym. W przypadku tej konfiguracji możesz określić adres URL i dodać go do ekranu głównego, aby użytkownik końcowy mógł go uruchomić w przeglądarce jednym naciśnięciem. |
| Enable screen saver (Włącz wygaszacz ekranu) | wartość logiczna | FAŁSZ | Umożliwia włączenie lub wyłączenie trybu wygaszacza ekranu. Jeśli jest ustawiona wartość true, możesz skonfigurować wartości **screen_saver_image**, **screen_saver_show_time**, **inactive_time_to_show_screen_saver** i **media_detect_ screen_saver**. |
| Screen saver image (Obraz wygaszacza ekranu) | ciąg |   | Ustaw adres URL obrazu wygaszacza ekranu. Jeśli nie zostanie ustawiony żaden adres URL, po uaktywnieniu wygaszacza ekranu urządzenia będą wyświetlać domyślny obraz wygaszacza ekranu. Domyślny obraz pokazuje ikonę aplikacji Managed Home Screen.  |
| Screen saver show time (Czas wyświetlania wygaszacza ekranu) | liczba całkowita | 0 | Udostępnia opcję ustawiania czasu (w sekundach) wyświetlania przez urządzenie wygaszacza ekranu w trybie wygaszacza ekranu. Jeśli ustawisz wartość 0, wygaszacz ekranu będzie widoczny przez czas nieokreślony (do chwili aktywowania urządzenia).  |
| Inactive time to enable   screen saver (Czas nieaktywności umożliwiający włączenie wygaszacza ekranu) | liczba całkowita | 30 | Liczba sekund, przez które urządzenie jest nieaktywne przed wyzwoleniem wygaszacza ekranu. Jeśli ustawisz wartość 0, urządzenie nigdy nie przejdzie w tryb wygaszacza ekranu. |
| Media detect before showing screen saver (Wykrywanie multimediów przed pokazaniem wygaszacza ekranu) | wartość logiczna | PRAWDA | Wybierz, czy ekran urządzenia ma wyświetlać wygaszacz ekranu, jeśli na urządzeniu jest odtwarzane nagranie audio/wideo. Jeśli ustawisz wartość true, urządzenie nie będzie odtwarzać nagrania audio/wideo niezależnie od wartości **inactive_time_to_show_scree_saver**. Jeśli ustawisz wartość false, ekran urządzenia pokaże wygaszacz ekranu zgodnie z ustawioną wartością **inactive_time_to_show_screen_saver**.   |
| Enable virtual home button (Włącz wirtualny przycisk ekranu głównego) | wartość logiczna | FAŁSZ | Ustaw wartość `True` dla tego ustawienia, aby zezwolić użytkownikowi końcowemu na dostęp do przycisku ekranu głównego aplikacji Managed Home Screen, który przeniesie go z powrotem do zarządzanego ekranu głównego z bieżącego zadania, które wykonuje.  |
| Type of virtual home button (Typ wirtualnego przycisku ekranu głównego) | ciąg | swipe_up | Użyj wartości **swipe_up**, aby uzyskać dostęp do przycisku ekranu głównego przy użyciu gestu szybkiego przesunięcia w górę. Użyj wartości **float**, aby uzyskać dostęp do umocowanego, trwałego przycisku ekranu głównego, który użytkownik końcowy może przenosić po ekranie. |
| Battery and Signal Strength   indicator bar (Pasek wskaźnika naładowania baterii i siły sygnału) | wartość logiczna | Prawda  | Określenie wartości `True` dla tego ustawienia powoduje wyświetlenie paska wskaźnika naładowania baterii i siły sygnału. |
| Exit lock task mode password (Hasło wyjścia z trybu blokady zadania) | ciąg |   | Wprowadź 4-6-cyfrowy kod pozwalający na czasowe wyjście z trybu blokady zadania w celu rozwiązania problemu. |
| Show Wi-Fi setting (Pokaż ustawienia sieci Wi-Fi) | wartość logiczna | FAŁSZ | Ustawienie wartości `True` dla tego ustawienia umożliwia użytkownikowi końcowemu włączanie lub wyłączanie sieci Wi-Fi oraz nawiązywanie połączenia z innymi sieciami Wi-Fi.  |
| Show Bluetooth setting (Pokaż ustawienia funkcji Bluetooth) | wartość logiczna | FAŁSZ | Ustawienie wartości `True` dla tego ustawienia umożliwia użytkownikowi końcowemu włączanie lub wyłączanie funkcji Bluetooth oraz nawiązywanie połączenia z różnymi urządzeniami obsługującymi łączność Bluetooth.   |
| Applications in folder are ordered by name (Aplikacje w folderze są uporządkowane według nazwy) | wartość logiczna | PRAWDA | Ustawienie wartości `False` dla tego ustawienia powoduje, że elementy w folderze będą wyświetlane w kolejności, w której są określone. W przeciwnym razie będą one wyświetlane w kolejności alfabetycznej.   |
| Application order enabled (Kolejność aplikacji włączona) | wartość logiczna | FAŁSZ | Ustawienie wartości `True` dla tego ustawienia umożliwia włączenie funkcji określania kolejności aplikacji, linków internetowych i folderów w aplikacji Managed Home Screen. Po włączeniu tego ustawienia należy ustawić kolejność za pomocą ustawienia **app_order**.   |
| Application order (Kolejność aplikacji) | bundleArray | FAŁSZ | Umożliwia określenie kolejności aplikacji, linków internetowych i folderów w aplikacji Managed Home Screen. Aby można było korzystać z tego ustawienia, opcja **Lock Home Screen** (Blokuj ekran główny) musi być włączona, opcja **Set grid size** (Ustaw rozmiar siatki) musi być określona oraz opcja **Application order enabled** (Kolejność aplikacji włączona) musi być ustawiona na `True`.   |

## <a name="enter-json-data"></a>Wprowadzanie danych JSON

Wprowadź dane JSON, aby skonfigurować wszystkie dostępne ustawienia aplikacji Managed Home Screen oraz ustawienia wyłączone w tabeli **Projektant konfiguracji**.

![Zrzut ekranu przedstawiający dodane dane JSON](./media/app-configuration-managed-home-screen-app/app-configuration-managed-home-screen-app_03.png)

Oprócz listy konfigurowalnych ustawień wyświetlonej w tabeli **Projektant konfiguracji** (powyżej), następująca tabela zawiera klucze konfiguracji, które można skonfigurować tylko za pośrednictwem danych JSON.

|    Klucz konfiguracji    |    Typ wartości    |    Wartość domyślna    |    Opis    |
|-------------------------------------------------|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Set allow-listed applications (Ustaw dozwolone aplikacje)    |    bundleArray    | <img alt="JSON - Example 1" src="./media/app-configuration-managed-home-screen-app/defaultvaluejson01.png" width="300"> |    Umożliwia wybranie zestawu aplikacji widocznych na ekranie głównym spośród aplikacji zainstalowanych na urządzeniu. Aplikacje możesz określić, wprowadzając nazwę pakietu dla aplikacji, którą chcesz wyświetlać, na przykład com.android.settings spowoduje udostępnienie ustawień na ekranie głównym. Aplikacje dozwolone w tej sekcji powinny już być zainstalowane na urządzeniu, aby były widoczne na ekranie głównym.    |
|    Set pinned web links (Ustaw przypięte linki internetowe)    |    bundleArray    | <img alt="JSON - Example 2" src="./media/app-configuration-managed-home-screen-app/defaultvaluejson02.png" width="300"> |    Umożliwia przypięcie witryn internetowych jako ikon szybkiego uruchamiania na ekranie głównym. W przypadku tej konfiguracji możesz określić adres URL i dodać go do ekranu głównego, aby użytkownik końcowy mógł go uruchomić w przeglądarce jednym naciśnięciem.    |
|    Create Managed Folder for grouping   apps (Utwórz zarządzany folder do grupowania aplikacji)    |    bundleArray    | <img alt="JSON - Example 3" src="./media/app-configuration-managed-home-screen-app/defaultvaluejson03.png" width="300"> |    Umożliwia tworzenie folderów i nadawanie im nazw, a następnie grupowanie aplikacji w tych folderach. Użytkownicy końcowi nie będą mogli przenosić folderów, zmieniać ich nazw ani przenosić aplikacji między folderami.   Foldery będą wyświetlane w kolejności utworzenia, zaś aplikacje w ramach folderów będą wyświetlane w kolejności alfabetycznej.         Uwaga: wszystkie aplikacje, które chcesz grupować w folderach, muszą być przypisane jako wymagane dla urządzenia i muszą zostać dodane do aplikacji Managed Home Screen.     |

Poniżej przedstawiono przykładowy skrypt JSON zawierający wszystkie dostępne klucze konfiguracji:

```json
{
    "kind": "androidenterprise#managedConfiguration",
    "productId": "com.microsoft.launcher.enterprise",
    "managedProperty": [
        {
            "key": "lock_home_screen",
            "valueBool": true
        },
        {
            "key": "wallpaper",
            "valueString": "default"
        },
        {
            "key": "icon_size",
            "valueInteger": 2
        },
        {
            "key": "app_folder_icon",
            "valueInteger": 0
        },
        {
            "key": "screen_orientation",
            "valueInteger": 1
        },
        {
            "key": "enable_telemetry",
            "valueBool": false
        },
        {
            "key": "applications",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "package",
                            "valueString": “app package name here”
                        }
                    ]
                }
            ]
        },
        {
            "key": "weblinks",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "link",
                            "valueString": “link here”
                        },
                        {
                            "key": "label",
                            "valueString": “weblink label here”
                        }
                    ]
                }
            ]
        },
        {
            "key": "show_virtual_home",
            "valueBool": false
        },
        {
            "key": "virtual_home_type",
            "valueString": "swipe_up"
        },
        {
            "key": "show_virtual_status_bar",
            "valueBool": true
        },
        {
            "key": "exit_lock_task_mode_code",
            "valueString": ""
        },
        {
            "key": "show_wifi_setting",
            "valueBool": false
        },
        {
            "key": "show_bluetooth_setting",
            "valueBool": false
        },
        {
            "key": "grid_size",
            "valueString": "4;5"
        },
        {
            "key": "app_order_enabled",
            "valueBool": true
        },
        {
            "key": "apps_in_folder_ordered_by_name",
            "valueBool": true
        },
        {
            "key": "app_orders",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "package",
                            "valueString": "com.Microsoft.emmx"
                        },
                        {
                            "key": "type",
                            "valueString": "application"
                        },
                        {
                            "key": "container",
                            "valueInteger": 1
                        },
                        {
                            "key": "position",
                            "valueInteger": 1
                        }
                    ]
                },
                {
                    "managedProperty": [
                        {
                            "key": "folder_name",
                            "valueString": "Work"
                        },
                        {
                            "key": "type",
                            "valueString": "managed_folder"
                        },
                        {
                            "key": "container",
                            "valueInteger": 1
                        },
                        {
                            "key": "position",
                            "valueInteger": 2
                        }
                    ]
                },
                {
                    "managedProperty": [
                        {
                            "key": "package",
                            "valueString": "com.microsoft.launcher.enterprise"
                        },
                        {
                            "key": "type",
                            "valueString": "application"
                        },
                        {
                            "key": "class",
                            "valueString": "com.microsoft.launcher.launcher"
                        },
                        {
                            "key": "container",
                            "valueInteger": 1
                        },
                        {
                            "key": "position",
                            "valueInteger": 3
                        }
                    ]
                }
            ]
        },
        {
            "key": "managed_folders",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "folder_name",
                            "valueString": "Folder name here"
                        },
                        {
                            "key": "applications",
                            "valueBundleArray": [
                                {
                                    "managedProperty": [
                                        {
                                            "key": "package",
                                            "valueString": "com.microsoft.emmx"
                                        }
                                    ]
                                },
                                {
                                    "managedProperty": [
                                        {
                                            "key": "package",
                                            "valueString": "com.microsoft.bing"
                                        }
                                    ]
                                },
                                {
                                    "managedProperty": [
                                        {
                                            "key": "link",
                                            "valueString": "https://microsoft.com/"
                                        }
                                    ]
                                }
                            ]
                        }
                    ]
                },
                {
                    "managedProperty": [
                        {
                            "key": "folder_name",
                            "valueString": "Example folder name 2"
                        },
                        {
                            "key": "applications",
                            "valueBundleArray": [
                                {
                                    "managedProperty": [
                                        {
                                            "key": "package",
                                            "valueString": "com.microsoft.office.word"
                                        }
                                    ]
                                }
                            ]
                        }
                    ]
                }
            ]
        }
    ]
}
```

## <a name="googles-android-device-policy-app"></a>Aplikacja Android Device Policy firmy Google
Aplikacja Managed Home Screen umożliwia teraz dostęp do aplikacji Android Device Policy firmy Google. Aplikacja Managed Home Screen jest niestandardowym modułem uruchamiania używanym w przypadku urządzeń zarejestrowanych w usłudze Intune jako urządzenia dedykowane z systemem Android Enterprise (AE) w trybie kiosku z wieloma aplikacjami. Aplikacja Android Device Policy może być przydatna zarówno dla Ciebie, jak i Twoich użytkowników w celu uzyskania pomocy technicznej lub przeprowadzenia debugowania. Ta funkcja uruchamiania jest dostępna, gdy urządzenie zostanie zarejestrowane i zablokowane w aplikacji Managed Home Screen. Do korzystania z tej funkcji nie są konieczne żadne dodatkowe instalacje.

## <a name="managed-home-screen-debug-screen"></a>Ekran debugowania w aplikacji Managed Home Screen
Dostęp do ekranu debugowania w aplikacji Managed Home Screen możesz uzyskać, klikając przycisk **Wstecz** do momentu wyświetlenia ekranu debugowania (kliknij przycisk **Wstecz** co najmniej 15 razy). Na tym ekranie debugowania można uruchomić aplikację Android Device Policy, wyświetlić i przekazać dzienniki lub tymczasowo wstrzymać tryb kiosku w celu zaktualizowania urządzenia. Aby uzyskać więcej informacji na temat wstrzymywania trybu kiosku, zobacz pozycję **Opuszczanie trybu kiosku** w [ustawieniach urządzeń dedykowanych](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings) dla rozwiązania Android Enterprise.

## <a name="next-steps"></a>Następne kroki

- Aby uzyskać więcej informacji o urządzeniach dedykowanych dla rozwiązania Android Enterprise, zobacz [Konfigurowanie rejestracji urządzeń dedykowanych dla rozwiązania Android Enterprise w usłudze Intune](../enrollment/android-kiosk-enroll.md).
