---
title: Portal pomocy technicznej służący do rozwiązywania problemów
titlesuffix: Microsoft Intune
description: Personel działu pomocy korzysta z tego portalu do rozwiązywania problemów technicznych użytkowników.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 10/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 37483f0fa33db109510ee537772a7bdead79e4f3
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203556"
---
# <a name="use-the-troubleshooting-portal-to-help-users-at-your-company"></a>Korzystanie z portalu rozwiązywania problemów, aby pomóc użytkownikom w firmie

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

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

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Rozwiązywanie problemów**.
4. Kliknij pozycję **Wybierz**, aby wybrać użytkownika do rozwiązywania problemów.
5. Wybierz użytkownika przez wpisanie jego nazwy lub adresu e-mail. Kliknij pozycję **Wybierz**. Informacje dotyczące rozwiązywania problemów użytkownika zostaną wyświetlone w okienku Rozwiązywanie problemów. Te informacje objaśniono w poniższej tabeli.

> [!Note]  
> Dostęp do okienka **Rozwiązywanie problemów** można też uzyskać przez przejście w przeglądarce do strony [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## <a name="areas-of-troubleshooting-dashboard"></a>Obszary pulpitu nawigacyjnego rozwiązywania problemów

Okienko **Rozwiązywanie problemów** umożliwia przeglądanie informacji o użytkownikach.

![](/intune/media/troubleshooting-dash.png)

| Obszar | Nazwa | Opis |
| ---  | ---  | ---         |
| 1.   | Stan konta  | Pokazuje stan bieżącej dzierżawy usługi Intune (**Aktywny** lub **Nieaktywny**).       |
| 2.   | Wybrany użytkownik  | Nazwa obecnie wybranego użytkownika. Kliknij pozycję **Zmień użytkownika**, aby wybrać nowego użytkownika.       |
| 3.   | Stan użytkownika  | Wyświetla stan licencji usługi Intune użytkownika, liczbę urządzeń, informacje o zgodności poszczególnych urządzeń, liczbę aplikacji i informacje o zgodności aplikacji.       |
| 4.   | Informacje o użytkowniku  | Użyj listy, aby wybrać szczegóły do przejrzenia w okienku. <br>Dostępne są następujące opcje: <ul><li>Aplikacje klienckie<li>Zasady zgodności<li> Zasady konfiguracji<li>Zasady ochrony aplikacji <li>Ograniczenia rejestracji</ul>      |
| 5.   | Członkostwo w grupach  | Pokazuje grupy, których wybrany użytkownik jest obecnie członkiem.       |

## <a name="client-apps-reference"></a>Odwołanie do aplikacji klienckich

Aplikacje działające na urządzeniach
- zarządzanych przez usługi Intune i Azure Active Directory (AD) 
- należących do użytkowników zarządzanych przez usługi Intune i Azure Active Directory (AD).

### <a name="properties"></a>Właściwości

Właściwości aplikacji klienckich.

| Właściwość      | Opis                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nazwa          | Nazwa aplikacji.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| System operacyjny            | System operacyjny zainstalowany na urządzeniu.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Typ          | Możesz wybrać typ przypisania dla każdej aplikacji.  <br> **Dostępne** — użytkownicy instalują aplikację z aplikacji Portal firmy lub witryny sieci Web.  <br> **Nie dotyczy** — aplikacja nie jest instalowana ani wyświetlana w Portalu firmy. <br> **Odinstaluj** — aplikacja jest odinstalowywana z urządzeń w wybranych grupach.  <br> **Dostępne z rejestracją lub bez** — przypisz tę aplikację do grup użytkowników, których urządzenia nie są zarejestrowane w usłudze Intune. |
| Data ostatniej modyfikacji | Nazwa typu urządzenia.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

### <a name="devices"></a>Devices

Urządzenia zarządzane przez usługę Intune albo użytkowników zarządzanych przez usługę Intune lub Azure AD.

| Właściwość           | Opis                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Nazwa urządzenia        | Nazwa typu urządzenia.                                                                                                     |
| Zarządzany przez         | Sygnatura czasowa modyfikacji zasad.                                                                                              |
| Typ dołączenia do usługi Azure AD | Stan każdej aplikacji użytkowników objętej ochroną aplikacji. Możliwe stany aplikacji to **Zaewidencjonowano** i **Nie zaewidencjonowano**. |
| Własność          | Typ własności urządzenia (**Firmowe**, **Osobiste** lub **Nieznany**).                                               |
| Zgodne z usługą Intune   | Nazwa typu urządzenia.                                                                                                     |
| Zgodne z usługą Azure AD | Stan każdej aplikacji użytkowników objętej ochroną aplikacji. Możliwe stany aplikacji to **Zaewidencjonowano** i **Nie zaewidencjonowano**. |
| Instalacja aplikacji | Wskazuje, czy instalacja aplikacji na poszczególnych urządzeniach zakończyła się powodzeniem lub niepowodzeniem. |
| System operacyjny                 | System operacyjny zainstalowany na urządzeniu.                                                                                       |
| Wersja systemu operacyjnego         | Numer wersji systemu operacyjnego urządzenia.                                                                                  |
| Ostatnie zaewidencjonowanie      | Nazwa typu urządzenia.                                                                                                     |

### <a name="app-protection-status"></a>Stan ochrony aplikacji

Dostępne są zasady ochrony aplikacji dla aplikacji mobilnych zintegrowanych z technologiami Enterprise Mobility Solution (EMS). Te zasady zapewniają podstawową ochronę danych firmowych pobieranych przez aplikacje mobilne, w tym aplikacje mobilne pakietu Office. 

| Właściwość    | Opis                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Stan      | Typ własności urządzenia (**Firmowe**, **Osobiste** lub **Nieznany**). |
| Nazwa aplikacji    | Nazwa aplikacji                                                           |
| Nazwa urządzenia | Nazwa typu urządzenia.                                                       |
| Typ urządzenia | Nazwa typu urządzenia.                                                       |
| Zasady    | Typ własności urządzenia (**Firmowe**, **Osobiste** lub **Nieznany**). |
| Ostatnia synchronizacja   | Sygnatura czasowa ostatniej synchronizacji urządzenia z usługą Intune.                   |

## <a name="app-protection-policies-reference"></a>Odwołanie do zasad ochrony aplikacji

Dostępne są zasady ochrony aplikacji dla aplikacji mobilnych zintegrowanych z technologiami EMS. Te zasady zapewniają podstawową ochronę danych firmowych pobieranych przez aplikacje mobilne, w tym aplikacje mobilne pakietu Office. 

### <a name="properties"></a>Właściwości

Tabela zawiera podsumowanie stanu zasad ochrony aplikacji dla urządzeń zarządzanych przez usługę Intune.

| Właściwość    | Opis                                                                                                                                |
|-------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Nazwa        | Nazwa aplikacji.                                                                                                        |
| Wdrożony    | Stan każdej aplikacji użytkowników objętej ochroną aplikacji. Możliwe stany aplikacji to **Zaewidencjonowano** i **Nie zaewidencjonowano**. |
| Platforma    | Typ własności urządzenia (**Firmowe**, **Osobiste** lub **Nieznany**).                                               |
| Rejestrowanie  | Nazwa typu urządzenia.                                                                                                     |
| Ostatnia aktualizacja | Sygnatura czasowa modyfikacji zasad.                                                                                              |

### <a name="devices"></a>Devices

Urządzenia zarządzane przez usługę Intune albo użytkowników zarządzanych przez usługę Intune lub Azure AD.

| Właściwość           | Tekst                                                                                                                                |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Nazwa urządzenia        | Nazwa typu urządzenia.                                                                                                     |
| Zarządzany przez         | Sygnatura czasowa modyfikacji zasad.                                                                                              |
| Typ dołączenia do usługi Azure AD | Stan każdej aplikacji użytkowników objętej ochroną aplikacji. Możliwe stany aplikacji to **Zaewidencjonowano** i **Nie zaewidencjonowano**. |
| Własność          | Typ własności urządzenia (**Firmowe**, **Osobiste** lub **Nieznany**).                                               |
| Zgodne z usługą Intune   | Nazwa typu urządzenia.                                                                                                     |
| Zgodne z usługą Azure AD | Stan każdej aplikacji użytkowników objętej ochroną aplikacji. Możliwe stany aplikacji to **Zaewidencjonowano** i **Nie zaewidencjonowano**. |
| Zgodne z usługą Azure AD | Stan każdej aplikacji użytkowników objętej ochroną aplikacji. Możliwe stany aplikacji to **Zaewidencjonowano** i **Nie zaewidencjonowano**. |
| System operacyjny                 | System operacyjny zainstalowany na urządzeniu.                                                                                       |
| Wersja systemu operacyjnego         | Numer wersji systemu operacyjnego urządzenia.                                                                                  |
| Ostatnie zaewidencjonowanie      | Nazwa typu urządzenia.                                                                                                     |

## <a name="compliance-policies-reference"></a>Odwołanie do zasad zgodności

Pozwala zagwarantować, że urządzenia używane do uzyskiwania dostępu do aplikacji oraz danych firmowych są zgodne z pewnymi regułami, takimi jak wymaganie użycia numeru PIN w celu uzyskania dostępu do urządzenia oraz szyfrowanie danych przechowywanych na urządzeniu.

### <a name="properties"></a>Właściwości

Właściwości zasad zgodności.

| Właściwość      | Opis                                                                                                                         |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Przypisania    | Stan każdej aplikacji użytkowników objętej ochroną aplikacji. Możliwe stany aplikacji to **Zaewidencjonowano** i **Nie zaewidencjonowano**. |
| Nazwa          | Nazwa aplikacji.                                                                                                        |
| System operacyjny            | System operacyjny zainstalowany na urządzeniu.                                                                                       |
| Typ zasad   | Typ własności urządzenia (**Firmowe**, **Osobiste** lub **Nieznany**).                                               |
| Data ostatniej modyfikacji | Nazwa typu urządzenia.                                                                                                     |

### <a name="devices"></a>Devices

Urządzenia zarządzane przez usługę Intune albo użytkowników zarządzanych przez usługę Intune lub Azure AD.

| Właściwość           | Opis                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Nazwa urządzenia        | Nazwa typu urządzenia.                                                                                                     |
| Zarządzany przez         | Sygnatura czasowa modyfikacji zasad.                                                                                              |
| Typ dołączenia do usługi Azure AD | Stan każdej aplikacji użytkowników objętej ochroną aplikacji. Możliwe stany aplikacji to **Zaewidencjonowano** i **Nie zaewidencjonowano**. |
| Własność          | Typ własności urządzenia (**Firmowe**, **Osobiste** lub **Nieznany**).                                               |
| Zgodne z usługą Intune   | Nazwa typu urządzenia.                                                                                                     |
| Zgodne z usługą Azure AD | Stan każdej aplikacji użytkowników objętej ochroną aplikacji. Możliwe stany aplikacji to **Zaewidencjonowano** i **Nie zaewidencjonowano**. |
| System operacyjny                 | System operacyjny zainstalowany na urządzeniu.                                                                                       |
| Wersja systemu operacyjnego         | Numer wersji systemu operacyjnego urządzenia.                                                                                  |
| Ostatnie zaewidencjonowanie      | Nazwa typu urządzenia.                                                                                                     |

### <a name="app-protection-policies"></a>Zasady ochrony aplikacji

Dostępne są zasady ochrony aplikacji dla aplikacji mobilnych zintegrowanych z technologiami EMS. Te zasady zapewniają podstawową ochronę danych firmowych pobieranych przez aplikacje mobilne, w tym aplikacje mobilne pakietu Office. 

| Właściwość    | Opis                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Stan      | Typ własności urządzenia (**Firmowe**, **Osobiste** lub **Nieznany**). |
| Nazwa aplikacji    | Nazwa aplikacji                                                           |
| Nazwa urządzenia | Nazwa typu urządzenia.                                                       |
| Typ urządzenia | Nazwa typu urządzenia.                                                       |
| Zasady    | Typ własności urządzenia (**Firmowe**, **Osobiste** lub **Nieznany**). |
| Ostatnia synchronizacja   | Sygnatura czasowa ostatniej synchronizacji urządzenia z usługą Intune.                   |

## <a name="configuration-policies-reference"></a>Informacje o zasadach konfiguracji

Dostępne są zasady konfiguracji aplikacji dla aplikacji mobilnych z konfiguracją specyficzną dla dostawcy. 

### <a name="properties"></a>Właściwości

Właściwości zasad konfiguracji.

| Właściwość      | Opis                                                                                                                         |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Przypisania    | Stan każdej aplikacji użytkowników objętej ochroną aplikacji. Możliwe stany aplikacji to **Zaewidencjonowano** i **Nie zaewidencjonowano**. |
| Nazwa          | Nazwa aplikacji.                                                                                                        |
| System operacyjny            | System operacyjny zainstalowany na urządzeniu.                                                                                       |
| Typ zasad   | Typ własności urządzenia (**Firmowe**, **Osobiste** lub **Nieznany**).                                               |
| Data ostatniej modyfikacji | Nazwa typu urządzenia.                                                                                                     |

### <a name="devices"></a>Devices

Urządzenia zarządzane przez usługę Intune albo użytkowników zarządzanych przez usługę Intune lub Azure AD.

| Właściwość           | Opis                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Nazwa urządzenia        | Nazwa typu urządzenia.                                                                                                     |
| Zarządzany przez         | Sygnatura czasowa modyfikacji zasad.                                                                                              |
| Typ dołączenia do usługi Azure AD | Stan każdej aplikacji użytkowników objętej ochroną aplikacji. Możliwe stany aplikacji to **Zaewidencjonowano** i **Nie zaewidencjonowano**. |
| Własność          | Typ własności urządzenia (**Firmowe**, **Osobiste** lub **Nieznany**).                                               |
| Zgodne z usługą Intune   | Nazwa typu urządzenia.                                                                                                     |
| Zgodne z usługą Azure AD | Stan każdej aplikacji użytkowników objętej ochroną aplikacji. Możliwe stany aplikacji to **Zaewidencjonowano** i **Nie zaewidencjonowano**. |
| System operacyjny                 | System operacyjny zainstalowany na urządzeniu.                                                                                       |
| Wersja systemu operacyjnego         | Numer wersji systemu operacyjnego urządzenia.                                                                                  |
| Ostatnie zaewidencjonowanie      | Nazwa typu urządzenia.                                                                                                     |


### <a name="app-protection-policies"></a>Zasady ochrony aplikacji

Dostępne są zasady ochrony aplikacji dla aplikacji mobilnych zintegrowanych z technologiami EMS. Te zasady zapewniają podstawową ochronę danych firmowych pobieranych przez aplikacje mobilne, w tym aplikacje mobilne pakietu Office. 

| Właściwość    | Opis                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Stan      | Typ własności urządzenia (**Firmowe**, **Osobiste** lub **Nieznany**). |
| Nazwa aplikacji    | Nazwa aplikacji                                                           |
| Nazwa urządzenia | Nazwa typu urządzenia.                                                       |
| Typ urządzenia | Nazwa typu urządzenia.                                                       |
| Zasady    | Typ własności urządzenia (**Firmowe**, **Osobiste** lub **Nieznany**). |
| Ostatnia synchronizacja   | Sygnatura czasowa ostatniej synchronizacji urządzenia z usługą Intune.                   |

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
