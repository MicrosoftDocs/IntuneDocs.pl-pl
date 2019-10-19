---
title: Portal pomocy technicznej służący do rozwiązywania problemów
titleSuffix: Microsoft Intune
description: Personel działu pomocy korzysta z tego portalu do rozwiązywania problemów technicznych użytkowników.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 03/11/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0094cdd12b2594cb60260d768daec8c5bed04c9c
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72510255"
---
# <a name="use-the-troubleshooting-portal-to-help-users-at-your-company"></a>Korzystanie z portalu rozwiązywania problemów, aby pomóc użytkownikom w firmie

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Portal służący do rozwiązywania problemów pozwala operatorom pomocy technicznej i administratorom usługi Intune wyświetlać informacje dotyczące użytkowników w celu rozwiązywania zgłoszonych przez nich problemów. Organizacje z działami pomocy technicznej mogą przypisać do grupy użytkowników rolę **operatora pomocy technicznej**. Rola operatora pomocy technicznej może używać okienka **Rozwiązywanie problemów**.

Problemy z rejestracją są widoczne dla użytkownika w okienku **Rozwiązywanie problemów**. Szczegółowe informacje o problemie i sugerowane kroki korygujące mogą ułatwić administratorom i operatorom pomocy technicznej rozwiązywanie problemów. Niektóre problemy z rejestracją nie są rejestrowane i dla niektórych błędów może nie być sugestii korekty.

Procedura dodawania roli operatora pomocy technicznej jest dostępna w artykule [Kontrola administracji opartej na rolach (RBAC) przy użyciu usługi Intune](/intune/role-based-access-control)

Jeśli użytkownik zgłasza do działu pomocy technicznej problem techniczny dotyczący usługi Intune, operator pomocy technicznej wprowadza imię i nazwisko użytkownika. W usłudze Intune wyświetlane są przydatne dane, które mogą ułatwić rozwiązanie wielu problemów warstwy 1, w tym:

- Stan użytkownika
- Przypisania
- Problemy ze zgodnością
- Urządzenie nie odpowiada
- Urządzenie nie pobiera ustawień sieci VPN lub Wi-Fi
- Nie można zainstalować aplikacji

## <a name="to-review-troubleshooting-details"></a>Przeglądanie szczegółów dotyczących rozwiązywania problemów

Aby wyświetlić informacje o użytkownikach, w okienku rozwiązywania problemów wybierz pozycję **Wybierz użytkownika**. Informacje o użytkowniku mogą ułatwić zrozumienie bieżącego stanu użytkowników i ich urządzeń.  

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. W okienku **Intune** wybierz pozycję **Rozwiązywanie problemów**.
4. Kliknij pozycję **Wybierz**, aby wybrać użytkownika do rozwiązywania problemów.
5. Wybierz użytkownika przez wpisanie jego nazwy lub adresu e-mail. Kliknij pozycję **Wybierz**. Informacje dotyczące rozwiązywania problemów użytkownika zostaną wyświetlone w okienku Rozwiązywanie problemów. Te informacje objaśniono w poniższej tabeli.

> [!Note]  
> Dostęp do okienka **Rozwiązywanie problemów** można też uzyskać przez przejście w przeglądarce do strony [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## <a name="areas-of-troubleshooting-dashboard"></a>Obszary pulpitu nawigacyjnego rozwiązywania problemów

Okienko **Rozwiązywanie problemów** umożliwia przeglądanie informacji o użytkownikach.

![Rozwiązywanie problemów z pulpitem nawigacyjnym z numerowanymi obszarami opisanymi w poniższej tabeli](./media/help-desk-operators/troubleshooting-dash.png)

| Obszar | Nazwa | Opis |
| ---  | ---  | ---         |
| 1.   | Stan konta  | Pokazuje stan bieżącej dzierżawy usługi Intune (**Aktywny** lub **Nieaktywny**).       |
| 2.   | Wybrany użytkownik  | Nazwa obecnie wybranego użytkownika. Kliknij pozycję **Zmień użytkownika**, aby wybrać nowego użytkownika.       |
| 3.   | Stan użytkownika  | Wyświetla stan licencji usługi Intune użytkownika, liczbę urządzeń, informacje o zgodności poszczególnych urządzeń, liczbę aplikacji i informacje o zgodności aplikacji.       |
| 4.   | Informacje o użytkowniku  | Użyj listy, aby wybrać szczegóły do przejrzenia w okienku. <br>Dostępne są następujące opcje: <ul><li>Aplikacje klienckie<li>Zasady zgodności<li> Zasady konfiguracji<li>Zasady ochrony aplikacji <li>Ograniczenia rejestracji</ul>      |
| 5.   | Członkostwo w grupach  | Pokazuje grupy, których wybrany użytkownik jest obecnie członkiem.       |

<!-- this section needs to be updated

## Client apps reference

The apps that are running devices
- managed by Intune and Azure Active Directory (AD) 
- owned by users managed by Intune and Azure Active Directory (AD).

### Properties

The properties of client apps.

| Property      | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Name          | The name of the application.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| OS            | The operating system installed on the device.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Type          | You can choose an assignment type for each app.  <br> **Available** - Users install the app from the Company Portal app or website.  <br> **Not Applicable** - The app is not installed or shown in the Company Portal. <br> **Uninstall** - The app is uninstalled from devices in the selected groups.  <br> **Available with or without enrollment** - Assign this app to groups of users whose devices are not enrolled with Intune. |
| Last Modified | The name of the type of device.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

### Devices

Devices managed by Intune or by users managed by Intune or Azure AD.

| Property           | Description                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Device name        | The name of the type of device.                                                                                                     |
| Managed by         | The timestamp the policy was modified.                                                                                              |
| Azure AD join type | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Ownership          | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Intune compliant   | The name of the type of device.                                                                                                     |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| App install | Denotes whether an app install failure or success has occurred on the individual device. |
| OS                 | The operating system installed on the device.                                                                                       |
| OS version         | The Operating System version number of the device.                                                                                  |
| Last check-in      | The name of the type of device.                                                                                                     |

### App protection status

An app protection policy is available to mobile apps that integrate with Enterprise Mobility Solution (EMS) technologies. These policies give a baseline of protection for your corporate data when it is downloaded to mobile apps, including the Office mobile apps. 

| Property    | Description                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Status      | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| App name    | The name of the application                                                           |
| Device name | The name of the type of device.                                                       |
| Device type | The name of the type of device.                                                       |
| Policies    | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| Last sync   | The timestamp of the last time the device synchronized with Intune.                   |

## App protection policies reference

An app protection policy is available to mobile apps that integrate with EMS technologies.These policies give a baseline of protection for your corporate data when it is downloaded to mobile apps, including the Office mobile apps. 

### Properties

The table summarizes app protection policies status for devices managed by Intune.

| Property    | Description                                                                                                                                |
|-------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Name        | The name of the application.                                                                                                        |
| Deployed    | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Platform    | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Enrollment  | The name of the type of device.                                                                                                     |
| Last Update | The timestamp the policy was modified.                                                                                              |

### Devices

Devices managed by Intune or by users managed by Intune or Azure AD.

| Property           | Text                                                                                                                                |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Device Name        | The name of the type of device.                                                                                                     |
| Managed By         | The timestamp the policy was modified.                                                                                              |
| Azure AD join type | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Ownership          | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Intune compliant   | The name of the type of device.                                                                                                     |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| OS                 | The operating system installed on the device.                                                                                       |
| OS version         | The Operating System version number of the device.                                                                                  |
| Last Check in      | The name of the type of device.                                                                                                     |

## Compliance policies reference

Makes sure that the devices used to access company apps and data, comply with certain rules like using a PIN to access the device, and encryption of data stored on the device.

### Properties

The properties of the compliance policies.

| Property      | Description                                                                                                                         |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Assignment    | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Name          | The name of the application.                                                                                                        |
| OS            | The operating system installed on the device.                                                                                       |
| Policy Type   | The type of device ownership (**Company**, **Personal**, and **Unknown**).                                               |
| Last Modified | The name of the type of device.                                                                                                     |

### Devices

Devices managed by Intune or by users managed by Intune or Azure AD.

| Property           | Description                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Device name        | The name of the type of device.                                                                                                     |
| Managed by         | The timestamp the policy was modified.                                                                                              |
| Azure AD join type | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Ownership          | The type of device ownership (**Company**, **Personal**, and **Unknown**).                                               |
| Intune compliant   | The name of the type of device.                                                                                                     |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| OS                 | The operating system installed on the device.                                                                                       |
| OS version         | The Operating System version number of the device.                                                                                  |
| Last check-in      | The name of the type of device.                                                                                                     |

### App protection policies

An app protection policy is available to mobile apps that integrate with EMS technologies. These policies give a baseline of protection for your corporate data when it is downloaded to mobile apps, including the Office mobile apps. 

| Property    | Description                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Status      | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| App name    | The name of the application                                                           |
| Device name | The name of the type of device.                                                       |
| Device type | The name of the type of device.                                                       |
| Policies    | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| Last sync   | The timestamp of the last time the device synchronized with Intune.                   |

## Configuration policies reference

An app configuration policy is available to mobile apps with vendor-specific configuration. 

### Properties

The properties of the configuration policies.

| Property      | Description                                                                                                                         |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Assignment    | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Name          | The name of the application.                                                                                                        |
| OS            | The operating system installed on the device.                                                                                       |
| Policy Type   | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Last Modified | The name of the type of device.                                                                                                     |

### Devices

Devices managed by Intune or by users managed by Intune or Azure AD.

| Property           | Description                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Device name        | The name of the type of device.                                                                                                     |
| Managed by         | The timestamp the policy was modified.                                                                                              |
| Azure AD join type | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Ownership          | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Intune compliant   | The name of the type of device.                                                                                                     |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| OS                 | The operating system installed on the device.                                                                                       |
| OS version         | The Operating System version number of the device.                                                                                  |
| Last check-in      | The name of the type of device.                                                                                                     |


### App protection policies

An app protection policy is available to mobile apps that integrate with EMS technologies. These policies give a baseline of protection for your corporate data when it is downloaded to mobile apps, including the Office mobile apps. 

| Property    | Description                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Status      | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| App name    | The name of the application                                                           |
| Device name | The name of the type of device.                                                       |
| Device type | The name of the type of device.                                                       |
| Policies    | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| Last sync   | The timestamp of the last time the device synchronized with Intune.                   |

-->

## <a name="enrollment-failure-reference"></a>Odwołanie do błędów rejestracji

Tabela błędów rejestracji zawiera listę prób rejestracji zakończonych niepowodzeniem. Urządzenie uwzględnione w poniższej tabeli mogło zostać później pomyślnie zarejestrowane podczas innej próby. Niektóre nieudane próby mogą nie być wyświetlane. Informacje o środkach zaradczych nie są dostępne dla wszystkich niepowodzeń.

| Kolumna tabeli | Opis |
|-------------|----------|
| Rozpoczęcie rejestracji | Godzina rozpoczęcia rejestrowania przez użytkownika. |
| System operacyjny | System operacyjny urządzenia. |
| Wersja systemu operacyjnego | Wersja systemu operacyjnego urządzenia. |
| Niepowodzenie | Przyczyna niepowodzenia. |

### <a name="failure-details"></a>Szczegóły błędu

Po wybraniu wiersza błędu zostaną wyświetlone bardziej szczegółowe informacje.

| Sekcja | Opis |
|-------------|----------|
| Szczegóły błędu | Bardziej szczegółowe wyjaśnienie błędu. |
| Potencjalne działania korygujące | Zalecane kroki w celu rozwiązania problemu. Niektóre błędy mogą nie mieć działań korygujących. |
| Zasoby (opcjonalnie) | Linki do dalszych informacji lub obszarów w portalu umożliwiających podjęcie działań. |

### <a name="enrollment-errors"></a>Błędy rejestracji

| Error | Szczegóły |
|-------------|----------|
| Limit czasu lub błąd systemu iOS | Przekroczenie limitu czasu między urządzeniem a usługą Intune z powodu zbyt długiego oczekiwania na ukończenie procesu rejestracji przez użytkownika. |
| Nie znaleziono użytkownika lub licencji | Użytkownik nie ma licencji lub został usunięty z usługi. |
| Urządzenie jest już zarejestrowane | Ktoś próbował zarejestrować urządzenie, korzystając z aplikacji Portal firmy na urządzeniu, które nadal jest zarejestrowane przez innego użytkownika. |
| Nie dołączono do usługi Intune | Podjęto próbę rejestracji, podczas gdy urząd zarządzania urządzeniami mobilnymi (MDM) usługi Intune nie został skonfigurowany. |
| Autoryzacja rejestracji nie powiodła się | Podjęto próbę rejestracji przy użyciu starszej wersji aplikacji Portal firmy. |
| Urządzenie nie jest obsługiwane | Urządzenie nie spełnia minimalnych wymagań na potrzeby rejestracji w usłudze Intune. |
| Nie spełniono ograniczeń rejestracji | Ta rejestracja została zablokowana ze względu na ograniczenie rejestracji skonfigurowane przez administratora. |
| Wersja urządzenia jest zbyt niska | Administrator skonfigurował ograniczenie rejestracji polegające na wymaganiu nowszej wersji urządzenia. |
| Wersja urządzenia jest zbyt wysoka | Administrator skonfigurował ograniczenie rejestracji polegające na wymaganiu starszej wersji urządzenia. |
| Urządzenia nie można zarejestrować jako osobistego | Administrator skonfigurował ograniczenie rejestracji polegające na blokowaniu rejestracji osobistych, a urządzenie, którego rejestracja nie powiodła się, nie zostało wstępnie zdefiniowane jako firmowe. |
| Platforma urządzenia jest zablokowana | Administrator skonfigurował ograniczenie rejestracji, które blokuje platformę tego urządzenia. |
| Token masowy wygasł | Token masowy w pakiecie aprowizacyjnym wygasł. |
| Nie znaleziono urządzenia rozwiązania Autopilot lub szczegółów | Podczas próby rejestracji nie znaleziono urządzenia rozwiązania Autopilot. |
| Nie znaleziono lub nie przypisano profilu rozwiązania Autopilot | Urządzenie nie ma aktywnego profilu rozwiązania Autopilot. |
| Nieoczekiwana metoda rejestracji rozwiązania Autopilot | Podjęto próbę zarejestrowania urządzenia przy użyciu niedozwolonej metody. |
| Usunięto urządzenie rozwiązania Autopilot | Urządzenie, dla którego podjęto próbę rejestracji, zostało usunięte z rozwiązania Autopilot dla tego konta. |
| Osiągnięto limit urządzeń | Ta rejestracja została zablokowana ze względu na limit urządzeń skonfigurowany przez administratora. |
| Dołączanie urządzenia firmy Apple | W przypadku wszystkich urządzeń z systemem iOS możliwość rejestracji została w tej chwili zablokowana z powodu braku lub wygaśnięcia certyfikatu wypychania MDM firmy Apple w usłudze Intune. |
| Urządzenie nie jest wstępnie zarejestrowane | Urządzenie nie zostało wstępnie zarejestrowane jako firmowe, a wszystkie rejestracje osobiste zostały zablokowane przez administratora. |
| Funkcja nie jest obsługiwana | Prawdopodobnie użytkownik próbował przeprowadzić rejestrację za pomocą metody niezgodnej z konfiguracją usługi Intune. |

## <a name="collect-available-data-from-mobile-device"></a>Zbieranie dostępnych danych z urządzenia przenośnego

Następujące zasoby ułatwiają zbieranie danych urządzenia podczas rozwiązywania problemów z urządzeniem użytkownika:
- [Wysyłanie błędów rejestracji systemu iOS do administratora IT](/intune-user-help/send-errors-to-your-it-admin-ios)
- [Ułatwianie działowi pomocy technicznej Twojej firmy rozwiązywania problemów z urządzeniami przez używanie pełnego rejestrowania](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android)
- [Wysyłanie dzienników systemu Android do działu pomocy technicznej Twojej firmy za pomocą kabla USB](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
- [Wysyłanie dzienników danych diagnostycznych systemu Android do administratora IT za pomocą poczty e-mail](/intune-user-help/send-logs-to-your-it-admin-by-email-android)
- [Wysyłanie błędów rejestracji systemu Android do administratora IT](/intune-user-help/send-enrollment-errors-to-your-it-administrator-android)

## <a name="next-steps"></a>Następne kroki

Dowiedz się więcej na temat kontroli administracji opartej na rolach (RBAC), aby definiować role na urządzeniu organizacji, zarządzanie aplikacjami mobilnymi i zadania ochrony danych. Aby uzyskać więcej informacji, zobacz [Kontrola administracji opartej na rolach (RBAC) przy użyciu usługi Intune](/intune/role-based-access-control).

Dowiedz się więcej o wszelkich znanych problemach w usłudze Microsoft Intune. Aby uzyskać więcej informacji, zobacz [Znane problemy w usłudze Microsoft Intune](/intune/known-issues).

Dowiedz się, jak utworzyć bilet pomocy technicznej i uzyskać pomoc. [Uzyskaj pomoc techniczną](/intune/get-support).
