---
title: Konfigurowanie aplikacji Microsoft Launcher dla systemu Android Enterprise przy użyciu usługi Intune
titleSuffix: ''
description: Użyj zasad konfiguracji usługi Intune w aplikacji Microsoft Launcher.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/26/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 55f76b0c5c71f7828fed17233c2b81d6b066cc3b
ms.sourcegitcommit: fab685b22a010fe231b27a0c5eda34a6f22f4c8d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2020
ms.locfileid: "78216104"
---
# <a name="configure-microsoft-launcher"></a>Konfigurowanie aplikacji Microsoft Launcher

Microsoft Launcher to aplikacja dla systemu Android, która umożliwia użytkownikom personalizowanie telefonu, organizację w podróży oraz przejście z pracy na telefonie na pracę na komputerze. 

Na w pełni zarządzanych urządzeniach z systemem Android Enterprise aplikacja Launcher umożliwia administratorom z działu informatycznego przedsiębiorstwa dostosowanie ekranów głównych urządzeń zarządzanych przez wybranie położeń tapety, aplikacji i ikony. Powoduje to standaryzację wyglądu i działania wszystkich zarządzanych urządzeń z systemem Android na różnych urządzeniach OEM i w różnych wersjach systemu. 

## <a name="how-to-configure-the-microsoft-launcher-app"></a>Jak skonfigurować aplikację Microsoft Launcher 

Przejdź do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) i wybierz kolejno pozycje **Aplikacje** > **Zasady konfiguracji aplikacji**. Dodaj zasady konfiguracji dla **urządzeń zarządzanych** z systemem **Android**, a następnie wybierz pozycję **Microsoft Launcher** jako skojarzoną aplikację. Kliknij pozycję **Ustawienia konfiguracji**, aby skonfigurować różne dostępne ustawienia aplikacji Microsoft Launcher. 

## <a name="choosing-a-configuration-settings-format"></a>Wybieranie formatu ustawień konfiguracji 

Istnieją dwie metody, których można użyć do definiowania ustawień konfiguracji dla aplikacji Microsoft Launcher: 

- **Projektant konfiguracji** pozwala na konfigurowanie ustawień za pomocą łatwego w użyciu interfejsu użytkownika umożliwiającego włączanie lub wyłączanie funkcji i ustawianie wartości. W przypadku tej metody istnieje kilka wyłączonych kluczy konfiguracji z typem wartości BundleArray. Te klucze konfiguracji można skonfigurować tylko przez wprowadzanie danych JSON. 

- **Dane JSON** pozwalają na zdefiniowanie wszystkich możliwych kluczy konfiguracji za pomocą skryptu JSON. 

Jeśli dodasz właściwości za pomocą **projektanta konfiguracji**, możesz automatycznie przekonwertować te właściwości do formatu JSON, wybierając pozycję **Wprowadź dane JSON** z listy rozwijanej **Format ustawień konfiguracji**, jak przedstawiono poniżej.

   ![Format ustawień konfiguracji — Użyj projektanta konfiguracji](./media/configure-microsoft-launcher/configure-microsoft-launcher-01.png)

## <a name="using-configuration-designer"></a>Korzystanie z projektanta konfiguracji

Projektant konfiguracji umożliwia wybieranie wstępnie wypełnionych ustawień i ich skojarzonych wartości.

   ![Format ustawień konfiguracji — Wprowadź dane JSON](./media/configure-microsoft-launcher/configure-microsoft-launcher-02.png)

Poniższa tabela zawiera listę dostępnych kluczy konfiguracji aplikacji Microsoft Launcher, typów wartości, wartości domyślnych i opisów. Opis zawiera oczekiwane zachowanie urządzenia w zależności od wybranych wartości. Klucze konfiguracji, które są wyłączone w projektancie konfiguracji, nie są wymienione w tabeli.

|    Klucz konfiguracji    |    Typ wartości    |    Wartość domyślna    |    Opis     |
|---------------------------------------------------|------------------|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Typ rejestracji    |    String     |    Domyślny    |    Pozwala ustawić typ rejestracji, do którego te zasady mają być stosowane. Obecnie wartość **Domyślny** odnosi się do typu **CorporateOwnedBusinessOnly**. Obecnie nie istnieją żadne inne obsługiwane typy rejestracji.        Nazwa klucza JSON: management_mode_key        |
|    Dopuszczalna zmiana przez użytkownika kolejności aplikacji na ekranie głównym    |    Boolean    |    Prawda    |    Umożliwia określenie, czy ustawienie **Kolejność aplikacji na ekranie głównym** może zostać zmienione przez użytkownika końcowego.<ul><li>W przypadku ustawienia wartości **Prawda** kolejność aplikacji zdefiniowana w zasadach będzie wymuszana tylko dla początkowego wdrożenia. Następnie zasady nie zostaną wymuszone w celu uwzględnienia zmian wprowadzonych przez użytkownika.</li><li>W przypadku ustawienia wartości **Fałsz** kolejność aplikacji będzie wymuszana przy każdej synchronizacji.</li></ul><br>**Uwaga:** Kolejność aplikacji na ekranie głównym można skonfigurować tylko za pomocą edytora JSON.<br><br>Nazwa klucza JSON:<br>`com.microsoft.launcher.HomeScreen.AppOrder.UserChangeAllowed`    |
|    Set Grid Size (Ustaw rozmiar siatki)    |    String    |    Auto    |    Umożliwia ustawienie rozmiaru siatki dla aplikacji, które mają zostać umieszczone na ekranie głównym. Możesz ustawić liczbę wierszy i kolumn aplikacji, aby zdefiniować rozmiar siatki w następującym formacie: `columns;rows`. Jeśli zdefiniujesz rozmiar siatki, maksymalną liczbą aplikacji, które będą wyświetlane w wierszu na ekranie głównym, będzie liczba ustawionych wierszy, a maksymalną liczbą aplikacji, które będą wyświetlane w kolumnie ekranu głównego, będzie ustawiona liczba kolumn.<br><br>        Nazwa klucza JSON:<br>`com.microsoft.launcher.HomeScreen.GridSize`    |
|    Ustaw tapetę urządzenia    |    String    |    Zero    |    Umożliwia ustawienie tapety wybranej przez użytkownika poprzez wprowadzenie adresu URL obrazu, który chcesz ustawić jako tapetę.<br><br>Nazwa klucza JSON:<br>`com.microsoft.launcher.Wallpaper.URL`    |
|    Dozwolona zmiana ustawienia Ustaw tapetę urządzenia przez użytkownika    |    Wartość logiczna    |    Prawda    |    Umożliwia określenie, czy ustawienie Ustaw tapetę urządzenia może zostać zmienione przez użytkownika końcowego.<ul><li>W przypadku ustawienia wartości **Prawda** tapeta w zasadach będzie wymuszana tylko w przypadku początkowego wdrożenia. Następnie zasady nie zostaną wymuszone w celu uwzględnienia zmian wprowadzonych przez użytkownika.</li><li>W przypadku ustawienia wartości **Fałsz** tapeta będzie wymuszana przy każdej synchronizacji.</li></ul><br>Nazwa klucza JSON:<br>`com.microsoft.launcher.Wallpaper.URL.UserChangeAllowed`        |
|    Włącz kanał informacyjny    |    Boolean    |    Prawda    |    Umożliwia włączenie kanału informacyjnego uruchamiania na urządzeniu, gdy użytkownik szybko przesunie w prawo na ekranie głównym.<ul><li>W przypadku ustawienia wartości **Prawda** kanał informacyjny zostanie włączony.</li><li>W przypadku ustawienia wartości **Fałsz** kanał informacyjny zostanie wyłączony.</li></ul><br>Nazwa klucza JSON:<br>`com.microsoft.launcher.Feed.Enabled`    |
|    Dozwolona zmiana ustawienia Włącz kanał informacyjny przez użytkownika    |    Boolean    |    Prawda    |     Umożliwia określenie, czy ustawienie **Włącz kanał informacyjny** może zostać zmienione przez użytkownika końcowego.<ul><li>W przypadku ustawienia wartości **Prawda** kanał informacyjny zostanie wymuszony tylko dla początkowego wdrożenia. Następnie zasady nie zostaną wymuszone w celu uwzględnienia zmian wprowadzonych przez użytkownika.</li><li>W przypadku ustawienia wartości **Fałsz** kanał informacyjny zostanie wymuszony przy każdej synchronizacji.</li></ul><br>Nazwa klucza JSON:`com.microsoft.launcher.Feed.Enabled.UserChangeAllowed`    |

## <a name="enter-json-data"></a>Wprowadzanie danych JSON

Wprowadź dane JSON, aby skonfigurować wszystkie dostępne ustawienia aplikacji Microsoft Launcher oraz ustawienia wyłączone w tabeli **Projektant konfiguracji**, jak przedstawiono poniżej.

   ![Projektant konfiguracji — dane JSON](./media/configure-microsoft-launcher/configure-microsoft-launcher-03.png)

Oprócz listy konfigurowalnych ustawień wyświetlonej w tabeli Projektant konfiguracji (powyżej) następująca tabela zawiera klucze konfiguracji, które można skonfigurować tylko za pośrednictwem danych JSON.

|    Klucz konfiguracji    |    Typ wartości    |    Wartość domyślna    |    Opis     |
|----------------------------------------------------------------------------------------------------|-------------------|-------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Ustaw dozwolone aplikacje<br>Klucz JSON:`com.microsoft.launcher.HomeScreen.Applications`    |    BundleArray    | Zobacz: [Ustaw dozwolone aplikacje](configure-microsoft-launcher.md#set-allow-listed-applications)</sup>    |    Umożliwia wybranie zestawu aplikacji widocznych na ekranie głównym spośród aplikacji zainstalowanych na urządzeniu. Aplikacje możesz zdefiniować, wprowadzając nazwę pakietu dla aplikacji, którą chcesz wyświetlać — na przykład `com.android.settings` spowoduje udostępnienie ustawień na ekranie głównym. Aplikacje dozwolone w tej sekcji powinny już być zainstalowane na urządzeniu, aby były widoczne na ekranie głównym.<p>Właściwości:<ul><li>**Pakiet:** Nazwa pakietu aplikacji</li><li>**Klasa:** Działanie aplikacji, które jest specyficzne dla określonej strony aplikacji. Jeśli ta wartość jest pusta, zostanie użyta domyślna strona aplikacji.</li></ul>      |
|    Kolejność aplikacji na ekranie głównym<br>Klucz JSON: `com.microsoft.launcher.HomeScreen.AppOrder`    |    BundleArray    |    Zobacz: [Kolejność aplikacji na ekranie głównym](configure-microsoft-launcher.md#home-screen-app-order)      |    Umożliwia określenie kolejności aplikacji na ekranie głównym.<p>Właściwości:<br><ul><li>**Typ:** Jedynym obsługiwanym typem jest `application`.</li><li>**Pozycja:** Gniazdo ikony aplikacji na ekranie głównym. Zaczyna się od pozycji 1 w lewym górnym rogu i przechodzi od lewej do prawej, od góry do dołu.</li><li>**Pakiet:** Nazwa pakietu aplikacji.</li><li>**Klasa:** Działanie aplikacji, które jest specyficzne dla określonej strony aplikacji. Jeśli ta wartość jest pusta, zostanie użyta domyślna strona aplikacji.</li></ul>    |

### <a name="set-allow-listed-applications"></a>Set allow-listed applications (Ustaw dozwolone aplikacje)

```JSON
{
    "key": "com.microsoft.launcher.HomeScreen.Applications",
    "valueBundleArray": 
    [
        {
            "managedProperty": [
                {
                    "key": "package",
                    "valueString": ""
                },
                {
                    "key": "class",
                    "valueString": ""
                }
            ]
        }
    ]
}
```

### <a name="home-screen-app-order"></a>Kolejność aplikacji na ekranie głównym

```JSON
{
    "key": "com.microsoft.launcher.HomeScreen.AppOrder",
    "valueBundleArray": 
    [
        {
            "managedProperty": [
                {
                    "key": "type",
                    "valueString": "application"
                },
                {
                    "key": "position",
                    "valueInteger": 0
                },
                {
                    "key": "package",
                    "valueString": ""
                },
                {
                    "key": "class",
                    "valueString": ""
                }
            ]
        }
    ]
}
```

Poniżej przedstawiono przykładowy skrypt JSON zawierający wszystkie dostępne klucze konfiguracji:

```JSON
{
    "kind": "androidenterprise#managedConfiguration", 
    "productId": "app:com.microsoft.launcher", 
    "managedProperty": [
        {
            "key": "management_mode_key", 
            "valueString": "Default"
        }, 
        {
            "key": "com.microsoft.launcher.Feed.Enable.UserChangeAllowed", 
            "valueBool": false
        }, 
        {
            "key": "com.microsoft.launcher.Feed.Enable", 
            "valueBool": true
        }, 
        {
            "key": "com.microsoft.launcher.Wallpaper.Url.UserChangeAllowed", 
            "valueBool": false
        }, 
        {
            "key": "com.microsoft.launcher.Wallpaper.Url", 
            "valueBool": "http://www.contoso.com/wallpaper.png"
        }, 
        {
            "key": "com.microsoft.launcher.HomeScreen.GridSize", 
            "valueString": "5;5"
        }, 
        {
            "key": "com.microsoft.launcher.HomeScreen.Applications", 
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "package", 
                            "valueString": "com.ups.mobile.android"
                        }, 
                        {
                            "key": "class", 
                            "valueString": ""
                        }
                    ]
                }, 
                {
                    "managedProperty": [
                        {
                            "key": "package", 
                            "valueString": "com.microsoft.teams"
                        }, 
                        {
                            "key": "class", 
                            "valueString": ""
                        }
                    ]
                }, 
                {
                    "managedProperty": [
                        {
                            "key": "package", 
                            "valueString": "com.microsoft.bing"
                        }, 
                        {
                            "key": "class", 
                            "valueString": ""
                        }
                    ]
                }
            ]
        }, 
        {
            "key": "com.microsoft.launcher.HomeScreen.AppOrder.UserChangeAllowed", 
            "valueBool": false
        }, 
        {
            "key": "com.microsoft.launcher.HomeScreen.AppOrder", 
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "type", 
                            "valueString": "application"
                        }, 
                        {
                            "key": "position", 
                            "valueInteger": 17
                        }, 
                        {
                            "key": "package", 
                            "valueString": "com.ups.mobile.android"
                        }, 
                        {
                            "key": "class", 
                            "valueString": ""
                        }
                    ]
                }, 
                {
                    "managedProperty": [
                        {
                            "key": "type", 
                            "valueString": "application"
                        }, 
                        {
                            "key": "position", 
                            "valueInteger": 18
                        }, 
                        {
                            "key": "package", 
                            "valueString": "com.microsoft.teams"
                        }, 
                        {
                            "key": "class", 
                            "valueString": ""
                        }
                    ]
                }, 
                {
                    "managedProperty": [
                        {
                            "key": "type", 
                            "valueString": "application"
                        }, 
                        {
                            "key": "position", 
                            "valueInteger": 19
                        }, 
                        {
                            "key": "package", 
                            "valueString": "com.microsoft.bing"
                        }, 
                        {
                            "key": "class", 
                            "valueString": ""
                        }
                    ]
                }
            ]
        }
    ]
}
```

## <a name="next-steps"></a>Następne kroki

- Aby uzyskać więcej informacji o w pełni zarządzanych urządzeniach dla rozwiązania Android Enterprise, zobacz temat [Konfiguracja rejestracji w usłudze Intune dla w pełni zarządzanych urządzeń z systemem Android Enterprise (wersja zapoznawcza)](../enrollment/android-fully-managed-enroll.md).
