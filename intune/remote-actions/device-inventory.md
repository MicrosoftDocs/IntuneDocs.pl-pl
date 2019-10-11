---
title: Wyświetlanie szczegółów urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Wyświetl szczegóły urządzeń, w tym system operacyjny, miejsce do magazynowania, producenta i model. Pobierz listę zainstalowanych aplikacji, sprawdź zasady zgodności i skonfiguruj program TeamViewer za pomocą usługi Microsoft Intune na platformie Azure. Podobnie jak w przypadku wyświetlania spisu urządzeń, którymi zarządzasz.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e88371ac1ab51340f0f897d835f78562bed7d252
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71727977"
---
# <a name="see-device-details-in-intune"></a>Wyświetlanie szczegółów urządzenia w usłudze Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Funkcja **Urządzenia** udostępnia dodatkowe szczegóły dotyczące zarządzanych urządzeń, w tym informacje o ich sprzęcie i zainstalowanych aplikacjach.

W tym artykule przedstawiono sposób wyświetlania wszystkich urządzeń i ich właściwości w witrynie Azure Portal.

## <a name="view-the-device-details"></a>Wyświetlanie szczegółów urządzenia

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Wybierz pozycję **Urządzenia** > **Wszystkie urządzenia**, a następnie wybierz jedno z wymienionych na liście urządzeń, aby otworzyć jego szczegóły:

   - Strona **Omówienie** zawiera nazwę urządzenia oraz listę niektórych kluczowych właściwości urządzenia, w tym informację o tym, czy jest to urządzenie BYOD, kiedy zostało zaewidencjonowane i nie tylko. Na urządzeniu można wykonywać następujące akcje:
      - [Wycofaj](devices-wipe.md#retire)
      - [Czyszczenie danych](devices-wipe.md#wipe)
      - [Zdalne blokowanie](device-remote-lock.md)
      - [Synchronizowanie urządzenia](device-sync.md)
      - [Zresetuj kod dostępu](device-passcode-reset.md)
      - [Ponowne uruchamianie](device-restart.md) (tylko system Windows)
      - [Zaczynanie od początku](device-fresh-start.md) (tylko system Windows)
      - Uruchamianie sesji pomocy zdalnej
   - Za pomocą opcji **Właściwości** możesz przypisać [utworzoną kategorię urządzeń](../enrollment/device-group-mapping.md) i zmienić własność urządzenia na urządzenie osobiste lub urządzenie firmowe.
   - **Sprzęt** — zawiera wiele szczegółowych informacji o urządzeniu, takich jak identyfikator urządzenia, system operacyjny i jego wersja, dostępne miejsce do magazynowania i inne szczegóły.
   - **Odnalezione aplikacje** — wyświetla listę wszystkich aplikacji, które zostały odnalezione jako zainstalowane na urządzeniu przez usługę Intune, wraz z wersjami aplikacji. Aby uzyskać więcej informacji, zobacz temat [Intune discovered apps](../apps/app-discovered-apps.md) (Aplikacje odnalezione w usłudze Intune).
   - **Zgodność urządzenia** — wyświetla wszystkie przypisane zasady zgodności oraz informację o tym, czy urządzenie jest zgodne.
   - **Konfiguracja urządzenia** — zawiera wszystkie zasady konfiguracji urządzeń przypisane do urządzenia oraz informację o tym, czy wdrożenie zasad powiodło się.

## <a name="hardware-device-details"></a>Szczegóły urządzeń
W zależności od operatora danego urządzenia mogą nie zostać zebrane wszystkie szczegóły

> [!Note]  
> Spis sprzętu i oprogramowania jest odświeżany w usłudze Intune co 7 dni.

|Szczegóły|Opis|Platforma| 
|--------------|----------------------|----|  
|Nazwa|Nazwa urządzenia.|Windows, iOS|
|Nazwa zarządzania|Nazwa urządzenia używana tylko w konsoli. Zmiana tej nazwy nie spowoduje zmiany nazwy na urządzeniu.|Windows, iOS|
|Identyfikator UDID|Unikatowy identyfikator urządzenia.|Windows, iOS|
|Identyfikator urządzenia usługi Intune|Identyfikator GUID, który unikatowo identyfikuje urządzenie.|Windows, iOS|
|Numer seryjny|Numer seryjny urządzenia od producenta.|Windows, iOS|
|Udostępnione urządzenie|Jeśli wybrano pozycję **Tak**, urządzenie jest współużytkowane przez więcej niż jednego użytkownika.|Windows, iOS|
|Rejestracja zatwierdzona przez użytkownika|Jeśli wybrano pozycję **Tak**, rejestracja urządzenia jest zatwierdzona przez użytkownika, co pozwala administratorom zarządzać pewnymi ustawieniami zabezpieczeń w urządzeniu.|Windows, iOS|
|System operacyjny|System operacyjny używany w urządzeniu.|Windows, iOS|
|Wersja systemu operacyjnego|Wersja systemu operacyjnego działającego na urządzeniu.|Windows, iOS|
|Język systemu operacyjnego|Język ustawiony dla systemu operacyjnego w urządzeniu.|Windows, iOS|
|Numer kompilacji|Numer kompilacji systemu operacyjnego.|Android|
|Poziom poprawki zabezpieczeń|Poziom poprawki zabezpieczeń dla urządzenia.|Android|
|Całkowita ilość miejsca|Całkowita ilość miejsca w urządzeniu (w gigabajtach).|Windows, iOS|
|Wolne miejsce w magazynie|Nieużywane miejsce w urządzeniu (w gigabajtach).|Windows, iOS|
|IMEI|Numer IMEI (International Mobile Equipment Identity) urządzenia.|Windows, iOS, Android|
|MEID|Identyfikator sprzętu przenośnego urządzenia.|Windows, iOS, Android|
|Producent|Producent urządzenia.|Windows, iOS, Android|
|Model|Model urządzenia.|Windows, iOS, Android|
|Numer telefonu|Numer telefonu przypisany do urządzenia.|Windows, iOS, Android|
|Operator subskrybenta|Operator sieci bezprzewodowej urządzenia.|Windows, iOS, Android|
|Technologia sieci komórkowej|System radiowy używany przez urządzenie.|Windows, iOS, Android|
|Wi-Fi MAC|Adres MAC (Media Access Control) urządzenia.|Windows, iOS, Android|
|Identyfikator ICCID|Identyfikator ICCID (Integrated Circuit Card Identifier), który jest unikatowym numerem identyfikacyjnym karty SIM.|Windows, iOS, Android|
|Data rejestracji|Data i godzina rejestracji urządzenia w usłudze Intune.|Windows, iOS, Android|
|Ostatni kontakt|Data i godzina ostatniego połączenia urządzenia z usługą Intune.|Windows, iOS, Android|
|Kod obejścia blokady aktywacji|Kod umożliwiający obejście blokady aktywacji.|Windows, iOS, Android|
|Zarejestrowane w usłudze Azure AD|Jeśli wybrano pozycję **Tak**, urządzenie jest zarejestrowane w usłudze Azure Active Directory.|Windows, iOS, Android|
|Zarejestrowane w usłudze Intune|Jeśli wybrano pozycję **Tak**, urządzenie jest zarejestrowane w usłudze Intune|Windows, iOS, Android|
|Zgodność|Stan zgodności urządzenia.|Windows, iOS, Android|
|Aktywowano program EAS|Jeśli wybrano pozycję **Tak**, urządzenie jest zsynchronizowane ze skrzynką pocztową programu Exchange.|Windows, iOS, Android|
|Identyfikator aktywacji programu EAS|Identyfikator programu Exchange ActiveSync urządzenia.|Windows, iOS, Android|
|Nadzorowane|Jeśli wybrano pozycję **Tak**, administratorzy mają rozszerzoną kontrolę nad urządzeniem.|Windows, iOS, Android|
|Zaszyfrowane|Jeśli wybrano pozycję **Tak**, dane przechowywane w urządzeniu są zaszyfrowane.|Windows, iOS, Android|



## <a name="next-steps"></a>Następne kroki
Zobacz, co jeszcze możesz zrobić, aby [zarządzać urządzeniami](device-management.md) przy użyciu usługi Intune.
