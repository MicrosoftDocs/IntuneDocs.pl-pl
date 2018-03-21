---
title: "Portal pomocy technicznej służący do rozwiązywania problemów"
titlesuffix: Microsoft Intune
description: "Personel działu pomocy korzysta z tego portalu do rozwiązywania problemów technicznych użytkowników."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.openlocfilehash: 9582b53c4f992b5f788f10a262bb802e80580144
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/08/2018
---
# <a name="use-the-troubleshooting-portal-to-help-users-at-your-company"></a>Korzystanie z portalu rozwiązywania problemów, aby pomóc użytkownikom w firmie

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Portal służący do rozwiązywania problemów pozwala operatorom pomocy technicznej i administratorom usługi Intune wyświetlać informacje dotyczące użytkowników w celu rozwiązywania zgłoszonych przez nich problemów. Organizacje z działami pomocy technicznej mogą przypisać do grupy użytkowników rolę **operatora pomocy technicznej**. Rola operatora pomocy technicznej może używać okienka **Rozwiązywanie problemów**.

Problemy z rejestracją są widoczne dla użytkownika w okienku **Rozwiązywanie problemów**. Szczegółowe informacje o problemie i sugerowane kroki korygujące mogą ułatwić administratorom i operatorom pomocy technicznej rozwiązywanie problemów. Niektóre problemy z rejestracją nie są rejestrowane i dla niektórych błędów może nie być sugestii korekty.

Procedura dodawania roli operatora pomocy technicznej jest dostępna w artykule [Kontrola administracji opartej na rolach (RBAC) przy użyciu usługi Intune](/intune/role-based-access-control)

Jeśli użytkownik zgłasza do działu pomocy technicznej problem techniczny dotyczący usługi Intune, operator pomocy technicznej wprowadza imię i nazwisko użytkownika. W usłudze Intune wyświetlane są przydatne dane, które mogą ułatwić rozwiązanie wielu problemów warstwy 1, w tym:

- Stan użytkownika
- Przypisania
- Problemy ze zgodnością
- Urządzenie nie
- Urządzenie nie pobiera ustawień sieci VPN lub Wi-Fi
- Nie można zainstalować aplikacji

## <a name="to-review-troubleshooting-details"></a>Przeglądanie szczegółów dotyczących rozwiązywania problemów

Aby wyświetlić informacje o użytkownikach, w okienku rozwiązywania problemów wybierz pozycję **Wybierz użytkownika**. Informacje o użytkowniku mogą ułatwić zrozumienie bieżącego stanu użytkowników i ich urządzeń.  

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie + zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Rozwiązywanie problemów**.
4. Kliknij pozycję **Wybierz**, aby wybrać użytkownika do rozwiązywania problemów.
5. Wybierz użytkownika przez wpisanie jego nazwy lub adresu e-mail. Kliknij pozycję **Wybierz**. Informacje dotyczące rozwiązywania problemów użytkownika zostaną wyświetlone w okienku Rozwiązywanie problemów. Te informacje objaśniono w poniższych tabelach.

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
| 4.   | Informacje o użytkowniku  | Użyj listy, aby wybrać szczegóły do przejrzenia w okienku. <br>Dostępne są następujące opcje: <ul><li>Aplikacje mobilne<li>Zasady ochrony aplikacji<li>Zasady zgodności<li> Zasady konfiguracji</ul>      |
| 5.   | Członkostwo w grupach  | Yadda       |

## <a name="mobile-apps-reference"></a>Odwołanie do aplikacji mobilnych

Aplikacje na urządzeniach lub urządzenia należące do użytkowników zarządzanych przez usługi Intune i Azure Active Directory (AD).

### <a name="properties"></a>Właściwości

Właściwości aplikacji mobilnych.

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
| Własność          | Typ własności urządzenia. Może to być typ **Firma**, **Osobiste** lub **Nieznany**.                                               |
| Zgodne z usługą Intune   | Nazwa typu urządzenia.                                                                                                     |
| Zgodne z usługą Azure AD | Stan każdej aplikacji użytkowników objętej ochroną aplikacji. Możliwe stany aplikacji to **Zaewidencjonowano** i **Nie zaewidencjonowano**. |
| System operacyjny                 | System operacyjny zainstalowany na urządzeniu.                                                                                       |
| Wersja systemu operacyjnego         | Numer wersji systemu operacyjnego urządzenia.                                                                                  |
| Ostatnie zaewidencjonowanie      | Nazwa typu urządzenia.                                                                                                     |

### <a name="app-protection-status"></a>Stan ochrony aplikacji

Dostępne są zasady ochrony aplikacji dla aplikacji mobilnych zintegrowanych z technologiami Enterprise Mobility Solution (EMS). Zapewniają one podstawową ochronę danych firmowych pobieranych przez aplikacje mobilne, w tym aplikacje mobilne pakietu Office. 

| Właściwość    | Opis                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Stan      | Typ własności urządzenia. Może to być typ **Firma**, **Osobiste** lub **Nieznany**. |
| Nazwa aplikacji    | Nazwa aplikacji                                                           |
| Nazwa urządzenia | Nazwa typu urządzenia.                                                       |
| Typ urządzenia | Nazwa typu urządzenia.                                                       |
| Zasady    | Typ własności urządzenia. Może to być typ **Firma**, **Osobiste** lub **Nieznany**. |
| Ostatnia synchronizacja   | Sygnatura czasowa ostatniej synchronizacji urządzenia z usługą Intune.                   |

## <a name="app-protection-policies-reference"></a>Odwołanie do zasad ochrony aplikacji

Dostępne są zasady ochrony aplikacji dla aplikacji mobilnych zintegrowanych z technologiami EMS. Zapewniają one podstawową ochronę danych firmowych pobieranych przez aplikacje mobilne, w tym aplikacje mobilne pakietu Office. 

### <a name="properties"></a>Właściwości

Tabela zawiera podsumowanie stanu zasad ochrony aplikacji dla urządzeń zarządzanych przez usługę Intune.

| Właściwość    | Opis                                                                                                                                |
|-------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Nazwa        | Nazwa aplikacji.                                                                                                        |
| Wdrożony    | Stan każdej aplikacji użytkowników objętej ochroną aplikacji. Możliwe stany aplikacji to **Zaewidencjonowano** i **Nie zaewidencjonowano**. |
| Platforma    | Typ własności urządzenia. Może to być typ **Firma**, **Osobiste** lub **Nieznany**.                                               |
| Rejestrowanie  | Nazwa typu urządzenia.                                                                                                     |
| Ostatnia aktualizacja | Sygnatura czasowa modyfikacji zasad.                                                                                              |

### <a name="devices"></a>Devices

Urządzenia zarządzane przez usługę Intune albo użytkowników zarządzanych przez usługę Intune lub Azure AD.

| Właściwość           | Tekst                                                                                                                                |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Nazwa urządzenia        | Nazwa typu urządzenia.                                                                                                     |
| Zarządzany przez         | Sygnatura czasowa modyfikacji zasad.                                                                                              |
| Typ dołączenia do usługi Azure AD | Stan każdej aplikacji użytkowników objętej ochroną aplikacji. Możliwe stany aplikacji to **Zaewidencjonowano** i **Nie zaewidencjonowano**. |
| Własność          | Typ własności urządzenia. Może to być typ **Firma**, **Osobiste** lub **Nieznany**.                                               |
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
| Typ zasad   | Typ własności urządzenia. Może to być typ **Firma**, **Osobiste** lub **Nieznany**.                                               |
| Data ostatniej modyfikacji | Nazwa typu urządzenia.                                                                                                     |

### <a name="devices"></a>Devices

Urządzenia zarządzane przez usługę Intune albo użytkowników zarządzanych przez usługę Intune lub Azure AD.

| Właściwość           | Opis                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Nazwa urządzenia        | Nazwa typu urządzenia.                                                                                                     |
| Zarządzany przez         | Sygnatura czasowa modyfikacji zasad.                                                                                              |
| Typ dołączenia do usługi Azure AD | Stan każdej aplikacji użytkowników objętej ochroną aplikacji. Możliwe stany aplikacji to **Zaewidencjonowano** i **Nie zaewidencjonowano**. |
| Własność          | Typ własności urządzenia. Może to być typ **Firma**, **Osobiste** lub **Nieznany**.                                               |
| Zgodne z usługą Intune   | Nazwa typu urządzenia.                                                                                                     |
| Zgodne z usługą Azure AD | Stan każdej aplikacji użytkowników objętej ochroną aplikacji. Możliwe stany aplikacji to **Zaewidencjonowano** i **Nie zaewidencjonowano**. |
| System operacyjny                 | System operacyjny zainstalowany na urządzeniu.                                                                                       |
| Wersja systemu operacyjnego         | Numer wersji systemu operacyjnego urządzenia.                                                                                  |
| Ostatnie zaewidencjonowanie      | Nazwa typu urządzenia.                                                                                                     |

### <a name="app-protection-policies"></a>Zasady ochrony aplikacji

Dostępne są zasady ochrony aplikacji dla aplikacji mobilnych zintegrowanych z technologiami EMS. Zapewniają one podstawową ochronę danych firmowych pobieranych przez aplikacje mobilne, w tym aplikacje mobilne pakietu Office. 

| Właściwość    | Opis                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Stan      | Typ własności urządzenia. Może to być typ **Firma**, **Osobiste** lub **Nieznany**. |
| Nazwa aplikacji    | Nazwa aplikacji                                                           |
| Nazwa urządzenia | Nazwa typu urządzenia.                                                       |
| Typ urządzenia | Nazwa typu urządzenia.                                                       |
| Zasady    | Typ własności urządzenia. Może to być typ **Firma**, **Osobiste** lub **Nieznany**. |
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
| Typ zasad   | Typ własności urządzenia. Może to być typ **Firma**, **Osobiste** lub **Nieznany**.                                               |
| Data ostatniej modyfikacji | Nazwa typu urządzenia.                                                                                                     |

### <a name="devices"></a>Devices

Urządzenia zarządzane przez usługę Intune albo użytkowników zarządzanych przez usługę Intune lub Azure AD.

| Właściwość           | Opis                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Nazwa urządzenia        | Nazwa typu urządzenia.                                                                                                     |
| Zarządzany przez         | Sygnatura czasowa modyfikacji zasad.                                                                                              |
| Typ dołączenia do usługi Azure AD | Stan każdej aplikacji użytkowników objętej ochroną aplikacji. Możliwe stany aplikacji to **Zaewidencjonowano** i **Nie zaewidencjonowano**. |
| Własność          | Typ własności urządzenia. Może to być typ **Firma**, **Osobiste** lub **Nieznany**.                                               |
| Zgodne z usługą Intune   | Nazwa typu urządzenia.                                                                                                     |
| Zgodne z usługą Azure AD | Stan każdej aplikacji użytkowników objętej ochroną aplikacji. Możliwe stany aplikacji to **Zaewidencjonowano** i **Nie zaewidencjonowano**. |
| System operacyjny                 | System operacyjny zainstalowany na urządzeniu.                                                                                       |
| Wersja systemu operacyjnego         | Numer wersji systemu operacyjnego urządzenia.                                                                                  |
| Ostatnie zaewidencjonowanie      | Nazwa typu urządzenia.                                                                                                     |


### <a name="app-protection-policies"></a>Zasady ochrony aplikacji

Dostępne są zasady ochrony aplikacji dla aplikacji mobilnych zintegrowanych z technologiami EMS. Zapewniają one podstawową ochronę danych firmowych pobieranych przez aplikacje mobilne, w tym aplikacje mobilne pakietu Office. 

| Właściwość    | Opis                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Stan      | Typ własności urządzenia. Może to być typ **Firma**, **Osobiste** lub **Nieznany**. |
| Nazwa aplikacji    | Nazwa aplikacji                                                           |
| Nazwa urządzenia | Nazwa typu urządzenia.                                                       |
| Typ urządzenia | Nazwa typu urządzenia.                                                       |
| Zasady    | Typ własności urządzenia. Może to być typ **Firma**, **Osobiste** lub **Nieznany**. |
| Ostatnia synchronizacja   | Sygnatura czasowa ostatniej synchronizacji urządzenia z usługą Intune.                   |

## <a name="next-steps"></a>Następne kroki

Dowiedz się więcej na temat kontroli administracji opartej na rolach (RBAC), aby definiować role na urządzeniu organizacji, zarządzanie aplikacjami mobilnymi i zadania ochrony danych. Aby uzyskać więcej informacji, zobacz [Kontrola administracji opartej na rolach (RBAC) przy użyciu usługi Intune](/intune/role-based-access-control).

Dowiedz się więcej o wszelkich znanych problemach w usłudze Microsoft Intune. Aby uzyskać więcej informacji, zobacz [Znane problemy w usłudze Microsoft Intune](/intune/known-issues).

Dowiedz się, jak utworzyć bilet pomocy technicznej i uzyskać pomoc. [Uzyskaj pomoc techniczną](/intune/get-support).
