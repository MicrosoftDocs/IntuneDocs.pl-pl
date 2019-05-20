---
title: Konfigurowanie aplikacji Microsoft Managed Home Screen
titleSuffix: Microsoft Intune
description: Dowiedz się, jak skonfigurować aplikację Microsoft Managed Home Screen.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/01/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 865c7f03-f525-4dfa-b3a8-d088a9106502
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b17ab1fb385bb1079a834f0a6fa690223ab64163
ms.sourcegitcommit: 01117021dfaebb5507aa146b7369447c3d5a403d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "65626506"
---
# <a name="configure-the-microsoft-managed-home-screen-app-for-android-enterprise"></a>Konfigurowanie aplikacji Microsoft Managed Home Screen dla rozwiązania Android Enterprise

Managed Home Screen to aplikacja używana dla należących do firmy dedykowanych urządzeń z rozwiązaniem Android Enterprise zarejestrowanych za pomocą usługi Intune i działających w trybie kiosku z wieloma aplikacjami. Dla tych urządzeń aplikacja Managed Home Screen działa jako obszar, z którego można uruchamiać inne zatwierdzone aplikacje. Aplikacja Managed Home Screen umożliwia administratorom IT dostosowywanie urządzeń i ograniczanie funkcji, do których użytkownik końcowy może uzyskać dostęp. 

## <a name="when-to-configure-the-microsoft-managed-home-screen-app"></a>Kiedy należy skonfigurować aplikację Microsoft Managed Home Screen

Zazwyczaj, jeśli ustawienia są dostępne za pośrednictwem konfiguracji urządzenia, należy je konfigurować tam. W ten sposób oszczędza się czas, minimalizuje liczbę błędów i uzyskuje lepsze wsparcie ze strony usługi Intune. Jednak niektóre ustawienia aplikacji Managed Home Screen są obecnie dostępne wyłącznie za pośrednictwem bloku **Zasady konfiguracji aplikacji** w konsoli usługi Intune. Z tego dokumentu dowiesz się, jak skonfigurować różne ustawienia przy użyciu projektanta konfiguracji albo skryptu JSON. 

> [!NOTE]
> Obecnie jest możliwe (i zalecane) ustawianie dozwolonych aplikacji i przypiętych linków internetowych za pośrednictwem pozycji **Aplikacje klienckie** i **Konfiguracja urządzenia**. Aby uzyskać pełną listę ustawień dostępnych w pozycji **Konfiguracja urządzenia** i mających wpływ na aplikację Managed Home Screen, zobacz [Ustawienia dedykowanego urządzenia](device-restrictions-android-for-work.md#dedicated-device-settings).  

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
| Set Grid Size (Ustaw rozmiar siatki) | ciąg | Automatycznie | Umożliwia ustawienie rozmiaru siatki dla aplikacji, które mają zostać umieszczone na zarządzanym ekranie głównym. Możesz ustawić liczbę wierszy i kolumn aplikacji, aby zdefiniować rozmiar siatki w następującym formacie (`rows;column`). Jeśli zdefiniujesz rozmiar siatki, maksymalną liczbą aplikacji, które będą wyświetlane w wierszu na ekranie głównym, będzie liczba ustawionych wierszy, a maksymalną liczbą aplikacji, które będą wyświetlane w kolumnie ekranu głównego, będzie ustawiona liczba kolumn. |
| Enable Screen Header (Włącz nagłówek ekranu) | wartość logiczna | PRAWDA | Włącza górny nagłówek dla różnych widoków, które oferuje zarządzany ekran główny, takich jak źródło danych lub karty źródeł danych. Jeśli to ustawienie zostanie włączone, użytkownicy urządzeń zobaczą nagłówek. |
| Enable device status bar (Włącz pasek stanu urządzenia) | wartość logiczna | PRAWDA | Włącza pasek stanu na ekranie głównym (górny pasek wyświetlający bieżące połączenia, takie jak sieci Wi-Fi itd.). Po włączeniu tego klucza konfiguracji użytkownik końcowy będzie mógł zobaczyć ikony wyświetlane na paskach stanu, które reprezentują połączenia i aktywne aplikacje. |
| Enable notifications badge (Włącz wskaźnik powiadomień) | wartość logiczna | FAŁSZ | Włącza dla ikon aplikacji wskaźnik powiadomień z liczbą nowych powiadomień w aplikacji. Jeśli to ustawienie zostanie włączone, użytkownicy końcowi będą widzieli wskaźniki powiadomień dla aplikacji z nieprzeczytanymi powiadomieniami. Pozostawienie tego klucza konfiguracji wyłączonego spowoduje, że użytkownik końcowy nie zobaczy żadnych wskaźników powiadomień powiązanych z aplikacjami, w których mogą być nieprzeczytane powiadomienia. |
| Lock Home Screen (Blokuj ekran główny) | wartość logiczna | PRAWDA | Usuwa użytkownikowi końcowemu możliwość przechodzenia między ikonami aplikacji na ekranie głównym. Po włączeniu tego klucza konfiguracji ikony aplikacji na ekranie głównym zostaną zablokowane, a użytkownik końcowy nie będzie mógł ich przeciągać i upuszczać w innych miejscach siatki ekranu głównego. Jeśli zostanie ustawiona wartość `false`, użytkownicy końcowi będą mogli przechodzić między ikonami aplikacji i linków internetowych na zarządzanym ekranie głównym.  |
| Set device wall paper (Ustaw tapetę urządzenia) | ciąg | Domyślny | Umożliwia ustawienie tapety wybranej przez użytkownika poprzez wprowadzenie adresu URL obrazu, który chcesz ustawić jako tapetę. |
| Set app icon size (Ustaw rozmiar ikony aplikacji) | liczba całkowita | 2 | Umożliwia ustawienie rozmiaru ikony dla aplikacji wyświetlanych na ekranie głównym. Możesz wybrać następujące wartości w tej konfiguracji dla różnych rozmiarów: 0 (najmniejsza), 1 (mała), 2 (zwykła), 3 (duża) i 4 (największa). |
| Set app folder icon (Ustaw ikonę folderu aplikacji) | liczba całkowita | 0 | Pozwala zdefiniować wygląd folderów aplikacji na ekranie głównym. Wygląd można wybrać spośród następujących wartości: Ciemny kwadrat (0); ciemne koło (1); jasny kwadrat (2); jasne koło (3). |
| Enable gestures (Włącz gesty) | wartość logiczna | FAŁSZ | Włącza użytkownikowi końcowemu możliwość przypisywania akcji do różnych gestów, takich jak szybkie przesunięcie w górę i w dół. Jeśli ten klucz konfiguracji zostanie wyłączony, użytkownicy końcowi będą mogli tylko szybko przesuwać w prawo, jeśli istnieje druga strona, i powracać do strony głównej. |
| Enable vertical scrolling (Włącz przewijanie w pionie) | wartość logiczna | FAŁSZ | Włącza przewijanie w pionie na zarządzanym ekranie głównym. Jeśli włączysz ten klucz konfiguracji, użytkownik końcowy będzie mógł przechodzić do różnych stron tylko w pionie, a nie szybko przesuwając w poziomie. |
| Set home screen theme (Ustaw motyw ekranu głównego) | ciąg | Theme.Light.Blue | Umożliwia wybranie motywu dla ekranu głównego z zestawu wstępnie zdefiniowanych motywów w różnych kolorach. Możesz wybrać następujące motywy, wprowadzając wartość ciągu w następującym formacie.   Theme.Light.Green. Gdzie Light (jasny) można zastąpić przez Dark (ciemny) dla ciemnego motywu, a Green (zielony) można zastąpić przez Blue (niebieski), Yellow (żółty), Pink (różowy), Red (czerwony), Orange (pomarańczowy) i Purple (purpurowy). |
| Enable dock (Włącz dokowanie) | wartość logiczna | FAŁSZ | Włącza sekcję dokowania aplikacji w dolnej części ekranu głównego z wyświetlonymi trwałymi aplikacjami i punktem wejścia dla wszystkich zainstalowanych aplikacji. Jeśli włączysz ten klucz konfiguracji, użytkownik końcowy będzie mógł uzyskiwać dostęp do aplikacji w sekcji dokowania, a także przechodzić do sekcji wszystkich aplikacji z listą wszystkich aplikacji zainstalowanych na urządzeniach bez względu na to, czy są one dozwolone, czy też nie. |
| Set screen orientation (Ustaw orientację ekranu) | liczba całkowita | 1 | Pozwala ustawić orientację ekranu głównego jako poziomą lub pionową albo zezwolić na automatyczne obracanie. Możesz ustawić orientację, wprowadzając wartość 1 (tryb pionowy), 2 (tryb poziomy) lub 3 (automatyczne obracanie). |
| Enable home screen feed (Włącz źródło danych ekranu głównego) | wartość logiczna | FAŁSZ | Włącza źródło danych ekranu głównego, które można zobaczyć po szybkim przesunięciu w lewo ekranu głównego. To źródło danych wyświetla zróżnicowaną zawartość, taką jak wiadomości, kalendarz, często używane aplikacje użytkownika, karta asystenta głosowego Cortana itd. Jeśli zostanie to włączone, użytkownik końcowy będzie mógł przejść do kanału informacyjnego, szybko przesuwając palcem w lewo ekran główny. |
| Enable overview mode (Włącz tryb omówienia) | wartość logiczna | FAŁSZ | Umożliwia użytkownikom końcowym dodawanie lub usuwanie różnych stron na ekranie głównym, do których dostęp jest możliwy po szybkim przesunięciu w prawo bezpośrednio z domyślnego ekranu. Jeśli to włączysz, użytkownik końcowy będzie mógł dodać strony z prawej strony domyślnej strony ekranu głównego, będzie miał możliwość zmiany domyślnej strony, jak również będzie mógł uzyskać dostęp do ustawień na zarządzanym ekranie głównym. |
| Enable device telemetry (Włącz telemetrię urządzenia) | wartość logiczna | FAŁSZ | Włącza wszystkie dane telemetryczne przechwytywane dla zarządzanego ekranu głównego. Jeśli to włączysz, firma Microsoft będzie mogła przechwytywać dane telemetryczne użycia urządzenia, takie jak liczba uruchomień konkretnej aplikacji na tym urządzeniu. |
| Set whitelisted applications (Ustaw dozwolone aplikacje) | bundleArray | FAŁSZ | Umożliwia zdefiniowanie zestawu aplikacji widocznych na ekranie głównym spośród aplikacji zainstalowanych na urządzeniu. Aplikacje możesz określić, wprowadzając nazwę pakietu dla aplikacji, którą chcesz wyświetlać, na przykład com.android.settings spowoduje udostępnienie ustawień na ekranie głównym. Aplikacje dozwolone w tej sekcji powinny być już zainstalowane na urządzeniu, aby były widoczne na ekranie głównym. |
| Set pinned web links (Ustaw przypięte linki internetowe) | bundleArray | FAŁSZ | Umożliwia przypięcie witryn internetowych jako ikon szybkiego uruchamiania na ekranie głównym. W przypadku tej konfiguracji możesz określić adres URL i dodać go do ekranu głównego, aby użytkownik końcowy mógł go uruchomić w przeglądarce jednym naciśnięciem. |
| Enable search bar (Włącz pasek wyszukiwania) | wartość logiczna | FAŁSZ | Włącza pasek wyszukiwania na ekranie głównym. Jeśli zostanie to włączone, użytkownicy urządzenia zobaczą pasek wyszukiwania na ekranie głównym, gdzie będą mieć możliwość wprowadzania tego, co chcą wyszukać w Internecie. |
| Disable settings app (Wyłącz aplikację ustawień) | wartość logiczna | FAŁSZ | Wyłącza stronę ustawień dla aplikacji Managed Home Screen. Jeśli to wyłączysz, użytkownik końcowy urządzenia nie będzie mieć możliwości przejścia do ustawień aplikacji Managed Home Screen. |
| Enable screen saver (Włącz wygaszacz ekranu) | wartość logiczna | FAŁSZ | Umożliwia włączenie lub wyłączenie trybu wygaszacza ekranu. Jeśli jest ustawiona wartość true, możesz skonfigurować wartości **screen_saver_image**, **screen_saver_show_time**, **inactive_time_to_show_screen_saver** i **media_detect_ screen_saver**. |
| Screen saver image (Obraz wygaszacza ekranu) | ciąg |   | Ustaw adres URL obrazu wygaszacza ekranu. Jeśli nie zostanie ustawiony żaden adres URL, po uaktywnieniu wygaszacza ekranu urządzenia będą wyświetlać domyślny ekran.  |
| Screen saver show time (Czas wyświetlania wygaszacza ekranu) | liczba całkowita | 0 | Udostępnia opcję ustawiania czasu (w sekundach) wyświetlania przez urządzenie wygaszacza ekranu w trybie wygaszacza ekranu. Jeśli ustawisz wartość 0, wygaszacz ekranu będzie widoczny przez czas nieokreślony (do chwili aktywowania urządzenia).  |
| Inactive time to enable   screen saver (Czas nieaktywności umożliwiający włączenie wygaszacza ekranu) | liczba całkowita | 30 | Liczba sekund, przez które urządzenie jest nieaktywne przed wyzwoleniem wygaszacza ekranu. Jeśli ustawisz wartość 0, urządzenie nigdy nie przejdzie w tryb wygaszacza ekranu. |
| Media detect before showing screen saver (Wykrywanie multimediów przed pokazaniem wygaszacza ekranu) | wartość logiczna | PRAWDA | Wybierz, czy ekran urządzenia ma wyświetlać wygaszacz ekranu, jeśli na urządzeniu jest odtwarzane nagranie audio/wideo. Jeśli ustawisz wartość true, urządzenie nie będzie odtwarzać nagrania audio/wideo niezależnie od wartości **inactive_time_to_show_scree_saver**. Jeśli ustawisz wartość false, ekran urządzenia pokaże wygaszacz ekranu zgodnie z ustawioną wartością **inactive_time_to_show_screen_saver**.   |
| Enable virtual home button (Włącz wirtualny przycisk ekranu głównego) | wartość logiczna | FAŁSZ | Ustaw wartość `True` dla tego ustawienia, aby zezwolić użytkownikowi końcowemu na dostęp do przycisku ekranu głównego aplikacji Managed Home Screen, który przeniesie go z powrotem do zarządzanego ekranu głównego z bieżącego zadania, które wykonuje.  |
| Type of virtual home button (Typ wirtualnego przycisku ekranu głównego) | ciąg | Swipe_up | Użyj wartości **swipe_up**, aby uzyskać dostęp do przycisku ekranu głównego przy użyciu gestu szybkiego przesunięcia w górę. Użyj wartości **float**, aby uzyskać dostęp do umocowanego, trwałego przycisku ekranu głównego, który użytkownik końcowy może przenosić po ekranie. |
| Battery and Signal Strength   indicator bar (Pasek wskaźnika naładowania baterii i siły sygnału) | wartość logiczna | Prawda  | Określenie wartości `True` dla tego ustawienia powoduje wyświetlenie paska wskaźnika naładowania baterii i siły sygnału. |
| Exit lock task mode password (Hasło wyjścia z trybu blokady zadania) | ciąg |   | Wprowadź 4-6-cyfrowy kod pozwalający na czasowe wyjście z trybu blokady zadania w celu rozwiązania problemu. |
| Show Wi-Fi setting (Pokaż ustawienia sieci Wi-Fi) | wartość logiczna | FAŁSZ | Ustawienie wartości `True` dla tego ustawienia umożliwia użytkownikowi końcowemu włączanie lub wyłączanie sieci Wi-Fi oraz nawiązywanie połączenia z innymi sieciami Wi-Fi.  |
| Show Bluetooth setting (Pokaż ustawienia funkcji Bluetooth) | wartość logiczna | FAŁSZ | Ustawienie wartości `True` dla tego ustawienia umożliwia użytkownikowi końcowemu włączanie lub wyłączanie funkcji Bluetooth oraz nawiązywanie połączenia z różnymi urządzeniami obsługującymi łączność Bluetooth.   |

## <a name="enter-json-data"></a>Wprowadzanie danych JSON

Wprowadź dane JSON, aby skonfigurować wszystkie dostępne ustawienia aplikacji Managed Home Screen oraz ustawienia wyłączone w tabeli **Projektant konfiguracji**.

![Zrzut ekranu przedstawiający dodane dane JSON](./media/app-configuration-managed-home-screen-app/app-configuration-managed-home-screen-app_03.png)

Oprócz listy konfigurowalnych ustawień wyświetlonej w tabeli **Projektant konfiguracji** (powyżej), następująca tabela zawiera klucze konfiguracji, które można skonfigurować tylko za pośrednictwem danych JSON.

|    Klucz konfiguracji    |    Typ wartości    |    Wartość domyślna    |    Opis    |
|-------------------------------------------------|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Set whitelisted applications (Ustaw dozwolone aplikacje)    |    bundleArray    | ``` json   {        "key":   "applications",        "valueBundleArray": [        {                                    "managedProperty": [   {         "key": "package",         "valueString":   STRING_VALUE   }   ]        }        ]   },   ``` |    Umożliwia wybranie zestawu aplikacji widocznych na ekranie głównym spośród aplikacji zainstalowanych na urządzeniu. Aplikacje możesz określić, wprowadzając nazwę pakietu dla aplikacji, którą chcesz wyświetlać, na przykład com.android.settings spowoduje udostępnienie ustawień na ekranie głównym. Aplikacje dozwolone w tej sekcji powinny już być zainstalowane na urządzeniu, aby były widoczne na ekranie głównym.    |
|    Set pinned web links (Ustaw przypięte linki internetowe)    |    bundleArray    | ``` json   {        "key": "weblinks",        "valueBundleArray": [         {               "managedProperty": [     {          "key": "link",          "valueString":   STRING_VALUE      },      {           "key": "label",           "valueString": STRING_VALUE      }      ]         }         ]   },   ``` |    Umożliwia przypięcie witryn internetowych jako ikon szybkiego uruchamiania na ekranie głównym. W przypadku tej konfiguracji możesz określić adres URL i dodać go do ekranu głównego, aby użytkownik końcowy mógł go uruchomić w przeglądarce jednym naciśnięciem.    |
|    Create Managed Folder for grouping   apps (Utwórz zarządzany folder do grupowania aplikacji)    |    bundleArray    | ``` json   {        "key": “managed_folders",        "valueBundleArray": [         {               "managedProperty": [     {            "key": "folder_name",            "valueString": STRING_VALUE      },      {             "key": "content",                      "valueBundleArray":   [                        {                             "managedProperty": [                    {                              “key”: “type”,                             “valueString”: STRING_VALUE                    },                    {                              “key”: “label”,                             “valueString”: STRING_VALUE                    },                    {                              “key”: “package”,                             “valueString”: STRING_VALUE                    },                    {                              “key”: “class”,                             “valueString”: STRING_VALUE                    },                    {                              “key”: “link”,                             “valueString”: STRING_VALUE                    }                 ]              }          ]      }              ]          }      ]   },   ``` |    Umożliwia tworzenie folderów i nadawanie im nazw, a następnie grupowanie aplikacji w tych folderach. Użytkownicy końcowi nie będą mogli przenosić folderów, zmieniać ich nazw ani przenosić aplikacji między folderami.   Foldery będą wyświetlane w kolejności utworzenia, zaś aplikacje w ramach folderów będą wyświetlane w kolejności alfabetycznej.         Uwaga: wszystkie aplikacje, które chcesz grupować w folderach, muszą być przypisane jako wymagane dla urządzenia i muszą zostać dodane do aplikacji Managed Home Screen.     |

Poniżej przedstawiono przykładowy skrypt JSON zawierający wszystkie dostępne klucze konfiguracji:

```json
{
    "kind": "androidenterprise#managedConfiguration",
    "productId": "com.microsoft.launcher.enterprise",
    "managedProperty": [
        {
            "key": "grid_size",
            "valueString": "Auto"
        },
        {
            "key": "keep_page_header",
            "valueBool": true
        },
        {
            "key": "keep_status_bar",
            "valueBool": true
        },
        {
            "key": "show_notification_badge",
            "valueBool": false
        },
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
            "key": "gesture_on",
            "valueBool": false
        },
        {
            "key": "vertical_scrolling",
            "valueBool": false
        },
        {
            "key": "theme",
            "valueString": "Theme.Light.Blue"
        },
        {
            "key": "dock_enable",
            "valueBool": false
        },
        {
            "key": "screen_orientation",
            "valueInteger": 1
        },
        {
            "key": "feed_enable",
            "valueBool": false
        },
        {
            "key": "allow_overview_mode",
            "valueBool": false
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
            "key": "search_bar",
            "valueBool": false
        },
        {
            "key": "hide_settings",
            "valueBool": false
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
## <a name="next-steps"></a>Następne kroki

- Aby uzyskać więcej informacji o urządzeniach dedykowanych dla rozwiązania Android Enterprise, zobacz [Konfigurowanie rejestracji urządzeń dedykowanych dla rozwiązania Android Enterprise w usłudze Intune](android-kiosk-enroll.md).
