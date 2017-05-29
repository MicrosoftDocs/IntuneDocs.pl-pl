---
title: "Konfigurowanie zasad zgodności urządzeń i zasad zarządzania aplikacjami podczas migracji do usługi Intune | Microsoft Docs"
description: "Celem tego artykułu jest przedstawienie niezbędnych instrukcji dotyczących konfigurowania zasad zgodności urządzeń i zasad zarządzania aplikacjami podczas migracji do usługi Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0062d08e-e5b3-4f73-8b64-5ad95adbe945
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 50a8929ef31e0a322e9460f82af3ed821ade69cf
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="phase-1-configure-device-compliance-and-app-management-policies"></a>Faza 1: Konfigurowanie zasad zgodności urządzeń i zasad zarządzania aplikacjami

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Głównym celem migracji do usługi Intune jest zarejestrowanie wszystkich urządzeń i zapewnienie ich zgodności z zasadami tej usługi. Zasady dotyczące urządzeń ułatwiają zarządzanie nie tylko firmowymi urządzeniami, z których korzystają pojedynczy użytkownicy, ale także urządzeniami osobistymi (BYOD), współużytkowanymi urządzeniami, takimi jak kioski, urządzenia używane w punktach sprzedaży czy tablety używane przez wielu uczniów w klasie, oraz urządzeniami nienależącymi do żadnego użytkownika (tylko z systemem iOS).

Poszczególne platformy urządzeń oferują różne ustawienia, ale zasady dotyczące urządzeń w usłudze Intune udostępniają następujące możliwości zarządzania urządzeniami przenośnymi, które zapewniają obsługę wszystkich platform:

-   Określanie liczby urządzeń, które może zarejestrować każdy użytkownik.

-   Zarządzanie ustawieniami urządzeń (np. szyfrowaniem na poziomie urządzenia, długością hasła lub użyciem aparatu fotograficznego).

-   Dostarczanie aplikacji, profilów poczty e-mail, profilów sieci VPN itp.

-   Ocenianie na poziomie urządzenia kryteriów dotyczących zasad zgodności z zabezpieczeniami.

> [!IMPORTANT]
> Zasady zarządzania urządzeniami nie są przypisywane bezpośrednio do poszczególnych urządzeń lub użytkowników, ale do grup użytkowników. Zasady te mogą być stosowane bezpośrednio do grupy użytkowników, a tym samym do urządzeń używanych przez te osoby, lub do grupy urządzeń, a tym samym do członków grupy.

## <a name="task-list-for-device-compliance-policies"></a>Lista zadań dotyczących zasad zgodności urządzeń

### <a name="task-1-add-device-groups-optional"></a>Zadanie 1. Dodanie grup urządzeń (opcjonalnie)

[Klasyczny portal usługi Intune](https://manage.microsoft.com/) umożliwia tworzenie grup urządzeń, co jest przydatne, gdy trzeba wykonywać różne zadania administracyjne na podstawie tożsamości urządzenia, a nie tożsamości użytkownika.

Grupy urządzeń ułatwiają zarządzanie urządzeniami bez wyznaczonych użytkowników, takimi jak kioski lub urządzenia współużytkowane przez personel pracujący w systemie zmianowym albo przypisane do określonej lokalizacji.

Konfigurując grupy urządzeń przed rozpoczęciem rejestracji urządzeń, można automatycznie pogrupować urządzenia przy użyciu ich kategorii. Dzięki temu podczas rejestracji automatycznie otrzymają one odpowiednie zasady grupy dotyczące urządzeń.

-   Dowiedz się, [jak dodać grupy urządzeń](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5).

-   Dowiedz się, [jak skonfigurować kategorie urządzeń](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune).

### <a name="task-2-use-resource-access-profiles-wi-fi-vpn-and-email-certificates"></a>Zadanie 2. Użycie profilów dostępu do zasobów (certyfikatów sieci Wi-Fi i VPN oraz poczty e-mail)

Profile dostępu do zasobów udostępniają certyfikaty i konfiguracje dostępu zarejestrowanym urządzeniom.

Jak już wspomniano w sekcji dotyczącej określania wymagań w zakresie zarządzania urządzeniami przenośnymi (MDM), jeśli korzystasz z uwierzytelniania opartego na certyfikatach, musisz mieć [działającą infrastrukturę PKI](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles), która umożliwia wdrożenie certyfikatów sieci VPN i Wi-Fi oraz poczty e-mail.

#### <a name="direct-import-of-resource-access-profiles-optional"></a>Bezpośrednie importowanie profilów dostępu do zasobów (opcjonalnie)

Jeśli istniejące rozwiązanie MDM udostępnia mechanizm eksportu profilów poczty e-mail oraz sieci Wi-Fi i VPN w formacie XML, spróbuj wykorzystać plik XML i zaimportować go do usługi Intune przy użyciu identyfikatora OMA-URI w celu utworzenia niestandardowych profilów dla urządzeń z systemami iOS, Android i Windows.

-   Dowiedz się, jak dodać niestandardowe zasady dla urządzeń z systemem [iOS](/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).

### <a name="task-3-create-and-deploy-device-configuration-profiles"></a>Zadanie 3. Tworzenie i wdrażanie profilów konfiguracji urządzeń

Musisz utworzyć profil konfiguracji urządzeń, aby wymusić stosowanie ustawień na poziomie urządzenia, na przykład wyłączyć aparat i sklep z aplikacjami lub skonfigurować ekran główny i tryb pojedynczej aplikacji.

- Dowiedz się więcej o [profilach konfiguracji urządzeń](https://docs.microsoft.com/intune/device-profile-create).

####  <a name="direct-import-of-ios-configuration-profiles-optional"></a>Bezpośrednie importowanie profilów konfiguracji systemu iOS (opcjonalnie)

-   **Profile narzędzia Apple Configurator dla systemu iOS (system iOS w wersji 7.1 i nowszych):** jeśli istniejące rozwiązanie MDM używa profilów narzędzia Apple Configurator (plików .mobileconfig), można je bezpośrednio zaimportować do usługi Intune jako niestandardowe zasady konfiguracji.

-   **Zasady konfiguracji aplikacji mobilnych dla systemu iOS:** jeśli istniejące rozwiązanie MDM używa zasad konfiguracji aplikacji mobilnych dla systemu iOS, można je bezpośrednio zaimportować do usługi Intune, o ile są one zgodne z formatem XML list właściwości określonym przez firmę Apple.

- Dowiedz się, jak dodać niestandardowe zasady dla systemu [iOS](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune#custom-policy-settings).

### <a name="task-4-create-and-deploy-device-compliance-policies-optional"></a>Zadanie 4. Tworzenie i wdrażanie zasad zgodności urządzeń (opcjonalnie)

Zasady zgodności urządzeń umożliwiają ocenę ustawień związanych z zabezpieczeniami i udostępniają raporty na temat zgodności urządzeń ze standardami firmowymi. Zasady zgodności urządzeń pozwalają ocenić czynniki związane z zabezpieczeniami, takie jak:

-   Długość numeru PIN

-   Stan zabezpieczeń systemowych

-   Wersja systemu operacyjnego

Zapoznaj się z dodatkowymi materiałami dotyczącymi ustawień zgodności urządzeń:

-   Dowiedz się więcej o [zasadach zgodności urządzeń](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).

-   Dowiedz się, [jak utworzyć zasady zgodności urządzeń](/intune-classic/deploy-use/create-a-device-compliance-policy-in-microsoft-intune).

### <a name="task-5-publish-and-deploy-apps"></a>Zadanie 5. Publikowanie i wdrażanie aplikacji

Funkcje MDM usługi Intune umożliwiają aprowizowanie aplikacji przez wymaganie ich automatycznej instalacji lub ich udostępnienie w Portalu firmy.

-   Dowiedz się, [jak dodawać aplikacje](/intune-classic/deploy-use/add-apps).

-   Dowiedz się, [jak wdrażać aplikacje](/intune-classic/deploy-use/deploy-apps).

### <a name="task-6-enable-device-enrollment"></a>Zadanie 6. Włączanie rejestracji urządzeń

Rejestracja umożliwia kontrolę nad urządzeniami, co pozwala nimi zarządzać.

-   Dowiedz się, [jak przygotować rejestrację firmowych urządzeń i osobistych urządzeń użytkowników](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune).

-   Dowiedz się, [jak zarejestrować firmowe urządzenia](/intune-classic/deploy-use/manage-corporate-owned-devices).

Jeśli musisz zarejestrować urządzenia udostępnione lub nieprzynależące do żadnego użytkownika, użyj [menedżera rejestracji urządzeń /intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

## <a name="next-steps"></a>Następne kroki 

[Faza 1: Konfiguracja zasad ochrony aplikacji /intune-classic/plan-design/migration-phase1-configure-app-protection-policies)

