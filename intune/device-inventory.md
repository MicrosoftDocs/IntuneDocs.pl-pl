---
title: Wyświetlanie szczegółów urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Wyświetl szczegóły urządzeń, w tym system operacyjny, miejsce do magazynowania, producenta i model. Pobierz listę zainstalowanych aplikacji, sprawdź zasady zgodności i skonfiguruj program TeamViewer za pomocą usługi Microsoft Intune na platformie Azure. Podobnie jak w przypadku wyświetlania spisu urządzeń, którymi zarządzasz.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a658182800f480f27097e078f28adc95c35aa3ea
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2018
ms.locfileid: "43313182"
---
# <a name="see-device-details-in-intune"></a>Wyświetlanie szczegółów urządzenia w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Funkcja **Urządzenia** udostępnia dodatkowe szczegóły dotyczące zarządzanych urządzeń, w tym informacje o ich sprzęcie i zainstalowanych aplikacjach.

W tym artykule przedstawiono sposób wyświetlania wszystkich urządzeń i ich właściwości w witrynie Azure Portal.

## <a name="view-the-device-details"></a>Wyświetlanie szczegółów urządzenia

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Urządzenia** > **Wszystkie urządzenia**, a następnie wybierz jedno z wymienionych na liście urządzeń, aby otworzyć jego szczegóły:

   - **Omówienie** zawiera nazwę urządzenia oraz listę niektórych kluczowych właściwości urządzenia, w tym informację o tym, czy jest to urządzenie BYOD, kiedy zostało zaewidencjonowane itp. Możesz wykonać następujące akcje na urządzeniu:
      - [Wycofaj](devices-wipe.md#retire)
        - [Czyszczenie danych](devices-wipe.md#wipe)
        - [Zdalne blokowanie](device-remote-lock.md)
        - [Synchronizowanie urządzenia](device-sync.md)
        - [Zresetuj kod dostępu](device-passcode-reset.md)
        - [Ponowne uruchamianie](device-restart.md) (tylko system Windows)
        - [Zaczynanie od początku](device-fresh-start.md) (tylko system Windows)
     - Uruchamianie sesji pomocy zdalnej
   - Za pomocą opcji **Właściwości** możesz przypisać [utworzoną kategorię urządzeń](device-group-mapping.md) i zmienić własność urządzenia na urządzenie osobiste lub urządzenie firmowe.
   - **Sprzęt** — zawiera wiele szczegółów dotyczących urządzenia, w tym identyfikator urządzenia, system operacyjny wraz z wersją, miejsce do magazynowania, model i producenta, ustawienia dostępu warunkowego oraz inne informacje.
   - **Odnalezione aplikacje** — wyświetla listę wszystkich aplikacji, które zostały odnalezione jako zainstalowane na urządzeniu przez usługę Intune, wraz z wersjami aplikacji. Możesz też **wyeksportować** listę aplikacji do pliku CSV.
   - **Zgodność urządzenia** — wyświetla wszystkie przypisane zasady zgodności oraz informację o tym, czy urządzenie jest zgodne.
   - **Konfiguracja urządzenia** — zawiera wszystkie zasady konfiguracji urządzeń przypisane do urządzenia oraz informację o tym, czy wdrożenie zasad powiodło się.

Usługa Intune zbiera listę aplikacji tylko na urządzeniach należących do firmy. Aplikacje nie są sprawdzane na urządzeniach osobistych. W przypadku komputerów z systemem Windows 10 wyszczególniane są tylko aplikacje nowoczesne na urządzeniach należących do firmy. Usługa Intune nie zbiera informacji o aplikacjach Win32 na urządzeniu. W zależności od operatora danego urządzenia mogą nie zostać zebrane wszystkie aplikacje.

|Platforma|Urządzenia osobiste|Urządzenia należące do firmy|  
|--------------|---------------------------------|--------------------------------|  
|Windows 10 (bez klienta programu Configuration Manager)|Tylko aplikacje zarządzane|Tylko aplikacje zarządzane|
|Windows 8.1 (bez klienta programu Configuration Manager)|Tylko aplikacje zarządzane|Tylko aplikacje zarządzane|  
|Windows Phone 8|Tylko aplikacje zarządzane|Tylko aplikacje zarządzane|  
|Windows RT|Tylko aplikacje zarządzane|Tylko aplikacje zarządzane|  
|iOS|Tylko aplikacje zarządzane|Wszystkie aplikacje zainstalowane na urządzeniu|
|macOS|Wszystkie aplikacje zainstalowane na urządzeniu|Wszystkie aplikacje zainstalowane na urządzeniu|  
|Android|Tylko aplikacje zarządzane|Wszystkie aplikacje zainstalowane na urządzeniu|  

## <a name="hardware-device-details"></a>Szczegóły urządzeń

### <a name="windows-and-ios-device-details"></a>Szczegóły urządzeń z systemami Windows i iOS:
|Szczegóły|Opis|  
|--------------|----------------------|  
|Nazwa|Nazwa urządzenia.|
|Nazwa zarządzania|Nazwa urządzenia używana tylko w konsoli. Zmiana tej nazwy nie spowoduje zmiany nazwy na urządzeniu.|
|Identyfikator UDID|Unikatowy identyfikator urządzenia.|
|Identyfikator urządzenia usługi Intune|Identyfikator GUID, który unikatowo identyfikuje urządzenie.|
|Numer seryjny|Numer seryjny urządzenia od producenta.|
|Udostępnione urządzenie|Jeśli wybrano pozycję **Tak**, urządzenie jest współużytkowane przez więcej niż jednego użytkownika.|
|Rejestracja zatwierdzona przez użytkownika|Jeśli wybrano pozycję **Tak**, rejestracja urządzenia jest zatwierdzona przez użytkownika, co pozwala administratorom zarządzać pewnymi ustawieniami zabezpieczeń w urządzeniu.|
|System operacyjny|System operacyjny używany w urządzeniu.|
|Wersja systemu operacyjnego|Wersja systemu operacyjnego działającego na urządzeniu.|
|Język systemu operacyjnego|Język ustawiony dla systemu operacyjnego w urządzeniu.|
|Całkowita ilość miejsca|Całkowita ilość miejsca w urządzeniu (w gigabajtach).|
|Wolne miejsce w magazynie|Nieużywane miejsce w urządzeniu (w gigabajtach).|


### <a name="windows-ios-and-macos-device-details"></a>Szczegóły urządzeń z systemami Windows, iOS i macOS
|Szczegóły|Opis|  
|--------------|----------------------|  
|IMEI|Numer IMEI (International Mobile Equipment Identity) urządzenia.|
|MEID|Identyfikator sprzętu przenośnego urządzenia.|
|Producent|Producent urządzenia.|
|Model|Model urządzenia.|
|Numer telefonu|Numer telefonu przypisany do urządzenia.|
|Operator subskrybenta|Operator sieci bezprzewodowej urządzenia.|
|Technologia sieci komórkowej|System radiowy używany przez urządzenie.|
|Wi-Fi MAC|Adres MAC (Media Access Control) urządzenia.|
|Identyfikator ICCID|Identyfikator ICCID (Integrated Circuit Card Identifier), który jest unikatowym numerem identyfikacyjnym karty SIM.|
|Data rejestracji|Data i godzina rejestracji urządzenia w usłudze Intune.|
|Ostatni kontakt|Data i godzina ostatniego połączenia urządzenia z usługą Intune.|
|Kod obejścia blokady aktywacji|Kod umożliwiający obejście blokady aktywacji.|
|Zarejestrowane w usłudze Azure AD|Jeśli wybrano pozycję **Tak**, urządzenie jest zarejestrowane w usłudze Azure Active Directory.|
|Zgodność|Stan zgodności urządzenia.|
|Aktywowano program EAS|Jeśli wybrano pozycję **Tak**, urządzenie jest zsynchronizowane ze skrzynką pocztową programu Exchange.|
|Identyfikator aktywacji programu EAS|Identyfikator programu Exchange ActiveSync urządzenia.|
|Nadzorowane|Jeśli wybrano pozycję **Tak**, administratorzy mają rozszerzoną kontrolę nad urządzeniem.|
|Zaszyfrowane|Jeśli wybrano pozycję **Tak**, dane przechowywane w urządzeniu są zaszyfrowane.|



## <a name="next-steps"></a>Następne kroki
Zobacz, co jeszcze możesz zrobić, aby [zarządzać urządzeniami](device-management.md) przy użyciu usługi Intune.