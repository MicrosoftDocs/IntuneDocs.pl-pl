---
title: Konfigurowanie zgodności urządzeń i aplikacji podczas migracji do usługi Intune
titlesuffix: Microsoft Intune
description: Ten artykuł zawiera niezbędne instrukcje dotyczące konfigurowania zasad zgodności urządzeń i zasad zarządzania aplikacjami podczas migracji do usługi Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0062d08e-e5b3-4f73-8b64-5ad95adbe945
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 99f8f1eb297ac1530f9379dd4f033b72eee0b0f4
ms.sourcegitcommit: fff179f59bd542677cbd4bf3bacc24bb880e2cb6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/07/2018
ms.locfileid: "53031827"
---
# <a name="configure-device-compliance-and-app-management-policies-when-migrating-to-microsoft-intune"></a>Konfigurowanie zasad zgodności urządzeń i zasad zarządzania aplikacjami podczas migracji do usługi Microsoft Intune

Głównym celem migracji do usługi Intune jest zarejestrowanie wszystkich urządzeń w usłudze Intune i zapewnienie ich zgodności z zasadami tej usługi. Zasady dotyczące urządzeń ułatwiają zarządzanie nie tylko firmowymi urządzeniami, z których korzystają pojedynczy użytkownicy, ale także urządzeniami osobistymi (BYOD) i urządzeniami udostępnianymi, takimi jak kioski, urządzenia używane w punktach sprzedaży czy tablety używane przez wielu uczniów w klasie, oraz urządzeniami nienależącymi do żadnego użytkownika (tylko z systemem iOS).

Poszczególne platformy urządzeń oferują różne ustawienia, ale zasady dotyczące urządzeń w usłudze Intune udostępniają następujące możliwości zarządzania urządzeniami przenośnymi, które zapewniają obsługę wszystkich platform:

-   Określanie liczby urządzeń, które może zarejestrować każdy użytkownik.

-   Zarządzanie ustawieniami urządzeń (na przykład szyfrowaniem na poziomie urządzenia, długością hasła czy użyciem aparatu fotograficznego).

-   Dostarczanie aplikacji, profilów poczty e-mail, profilów sieci VPN itp.

-   Ocenianie na poziomie urządzenia kryteriów dotyczących zasad zgodności z zabezpieczeniami.

> [!IMPORTANT]
> Zasady zarządzania urządzeniami nie są przypisywane bezpośrednio do poszczególnych urządzeń lub użytkowników, ale do grup użytkowników. Zasady te mogą być stosowane bezpośrednio do grupy użytkowników, a tym samym do urządzeń używanych przez te osoby, lub do grupy urządzeń, a tym samym do elementów członkowskich grupy.

## <a name="task-list-for-device-compliance-policies"></a>Lista zadań dotyczących zasad zgodności urządzeń

### <a name="task-1-add-device-groups-optional"></a>Zadanie 1. Dodanie grup urządzeń (opcjonalnie)

Możliwe jest tworzenie grup urządzeń, co jest przydatne, gdy trzeba wykonywać zadania administracyjne na podstawie tożsamości urządzenia, a nie tożsamości użytkownika.

Grupy urządzeń ułatwiają zarządzanie urządzeniami, które nie mają dedykowanych użytkowników, takimi jak kioski lub urządzenia współużytkowane przez personel pracujący w systemie zmianowym, albo urządzeniami przypisanymi do konkretnej lokalizacji.

Dzięki skonfigurowaniu grup urządzeń przed rozpoczęciem rejestracji urządzeń można użyć kategorii urządzeń w celu automatycznego dołączania urządzeń do grup podczas rejestracji. Następnie automatycznie otrzymają one odpowiednie zasady grupy dotyczące urządzeń. [Wprowadzenie do grup](groups-get-started.md).

### <a name="task-2-use-resource-access-profiles-wi-fi-vpn-and-email-certificates"></a>Zadanie 2: Użycie profilów dostępu do zasobów (certyfikatów sieci Wi-Fi i VPN oraz poczty e-mail)

Profile dostępu do zasobów dostarczają certyfikaty i konfiguracje dostępu zarejestrowanym urządzeniom. Jeśli używasz uwierzytelniania opartego na certyfikatach, [skonfiguruj certyfikaty](certificates-configure.md).

### <a name="task-3-create-and-deploy-device-configuration-profiles"></a>Zadanie 3: Tworzenie i wdrażanie profilów konfiguracji urządzeń

Musisz utworzyć profil konfiguracji urządzeń, aby wymusić stosowanie ustawień na poziomie urządzenia, na przykład wyłączyć aparat i sklep z aplikacjami, skonfigurować ekran główny i tryb pojedynczej aplikacji itd. Dowiedz się więcej o [profilach urządzeń](device-profiles.md).

####  <a name="directly-import-ios-configuration-profiles-optional"></a>Bezpośrednie importowanie profilów konfiguracji systemu iOS (opcjonalnie)

-   **Profile programu Apple Configurator dla systemu iOS (system iOS 7.1 lub nowszy):** jeśli istniejące rozwiązanie MDM używa profilów programu Apple Configurator (plików mobileconfig), można je bezpośrednio zaimportować do usługi Intune jako niestandardowe zasady konfiguracji.

-   **Zasady konfiguracji aplikacji mobilnych dla systemu iOS:** jeśli istniejące rozwiązanie MDM używa zasad konfiguracji aplikacji mobilnych dla systemu iOS, można je bezpośrednio zaimportować do usługi Intune, o ile są one zgodne z formatem XML list właściwości określonym przez firmę Apple.

- Dowiedz się, jak dodać niestandardowe zasady dla systemu [iOS](custom-settings-ios.md).

### <a name="task-4-create-and-deploy-device-compliance-policies-optional"></a>Zadanie 4: Tworzenie i wdrażanie zasad zgodności urządzeń (opcjonalnie)

Zasady zgodności urządzeń umożliwiają ocenę ustawień związanych z zabezpieczeniami i udostępniają raporty na temat zgodności urządzeń ze standardami firmowymi. Te ustawienia obejmują:

-   Długość numeru PIN

-   Stan zabezpieczeń systemowych

-   Wersja systemu operacyjnego

Zapoznaj się z dodatkowymi materiałami dotyczącymi ustawień zgodności urządzeń:

-   Dowiedz się więcej o [zasadach zgodności urządzeń](device-compliance.md).

-   Dowiedz się, [jak utworzyć zasady zgodności urządzeń](device-compliance-get-started.md).

### <a name="task-5-publish-and-deploy-apps"></a>Zadanie 5: Publikowanie i wdrażanie aplikacji

Funkcje MDM usługi Intune umożliwiają dostarczanie aplikacji przez wymaganie ich automatycznej instalacji lub ich udostępnienie w Portalu firmy.

-   [Jak dodawać aplikacje](apps-add.md).

-   [Jak wdrażać aplikacje](apps-deploy.md).

### <a name="task-6-enable-device-enrollment"></a>Zadanie 6: Włączanie rejestracji urządzeń

Zarejestrowanie urządzenia jest niezbędne do zarządzania urządzeniem. Dowiedz się, [jak przygotować rejestrację firmowych urządzeń i osobistych urządzeń użytkowników](device-enrollment.md).

## <a name="next-steps"></a>Następne kroki

[Konfigurowanie zasad ochrony aplikacji (opcjonalnie)](migration-guide-app-protection-policies.md).
