---
title: W trakcie opracowywania — Microsoft Intune
titleSuffix: ''
description: Funkcje usługi Microsoft Intune w trakcie opracowywania
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3c2b9429bf5b50ac5e416c4a7b356627e9cc9fb1
ms.sourcegitcommit: f75386986d24e7d5dd63a3f1a0a014cb52056063
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2019
ms.locfileid: "69560102"
---
# <a name="in-development-for-microsoft-intune---august-2019"></a>W trakcie opracowywania — Microsoft Intune — sierpień 2019 r.

Aby ułatwić Ci planowanie, na tej stronie udostępniamy listę aktualizacji interfejsu użytkownika i funkcji usługi Intune, które są obecnie opracowywane, a zostaną wydane w przyszłości. Ponadto:

- Jeśli przewidujemy, że przed wprowadzeniem zmiany będzie konieczne wykonanie określonych działań, opublikujemy również dodatkowy wpis w Centrum wiadomości usługi Office.
- Po wprowadzeniu funkcji w środowisku produkcyjnym — w wersji zapoznawczej lub ogólnie dostępnej — opis tej funkcji zostanie przeniesiony z tej strony na stronę [Co nowego](whats-new.md).
- Ta strona oraz strona [Co nowego](whats-new.md) są okresowo aktualizowane. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.
- Zobacz [harmonogram działania dla platformy M365](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS), aby poznać strategiczne cele i terminy.

> [!Note]
> Te elementy odzwierciedlają aktualne plany firmy Microsoft dotyczące funkcji usługi Intune, które zostaną wprowadzone w przyszłych wydaniach. Zarówno daty, jak i poszczególne funkcje mogą ulec zmianie. Nie wszystkie elementy będące w trakcie opracowywania zostały opisane na tej stronie.

**Kanał informacyjny RSS**: otrzymuj powiadomienie, gdy ta strona zostanie zaktualizowana przez skopiowanie i wklejenie następującego adresu URL w czytniku kanałów informacyjnych: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->

<!-- Common categories:  
#### App management
#### Device configuration
#### Device enrollment
#### Device management
#### Intune apps
#### Monitor and troubleshoot
#### Role-based access control
#### Security

-->
 
<!-- ***********************************************-->
## <a name="app-management"></a>Zarządzanie aplikacjami

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Skonfiguruj zawartość powiadomienia aplikacji dla kont organizacji <!-- 2576686 -->
Zasady ochrony aplikacji usługi Intune (aplikacje) na urządzeniach z systemem Android i iOS umożliwiają kontrolowanie zawartości powiadomień aplikacji dla kont organizacji. Ta funkcja będzie wymagała obsługi aplikacji i może być niedostępna dla wszystkich aplikacji z obsługą aplikacji. Aby uzyskać więcej informacji na temat zasad ochrony aplikacji, zobacz [Co to są zasady ochrony aplikacji?](app-protection-policy.md)

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Raportowanie aplikacji ze sklepu Google Play dostępne dla profilów służbowych systemu Android <!-- 3041956  -->
W przypadku dostępnych instalacji aplikacji na urządzeniach z profilem służbowym systemu Android można wyświetlić stan instalacji aplikacji oraz zainstalowaną wersję aplikacji z zarządzanego sklepu Google Play. Aby uzyskać więcej informacji, zobacz artykuły [Jak monitorować zasady ochrony aplikacji](app-protection-policies-monitor.md), [Zarządzanie urządzeniami z profilem służbowym systemu Android za pomocą usługi Intune](android-enterprise-overview.md) i [Typ aplikacji zarządzanej ze sklepu Google Play](apps-add-android-for-work.md#managed-google-play-app-type).

<!-- ***********************************************-->
## <a name="device-configuration"></a>Konfiguracja urządzenia

### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>Obsługa profilów sieci VPN protokołu IKEv2 dla systemu iOS <!-- 1943438 -->
Będzie można tworzyć profile sieci VPN dla natywnego klienta sieci VPN systemu iOS za pomocą protokołu IKEv2. Protokół IKEv2 to nowy typ połączenia w obszarze **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** jako platforma > **VPN** jako typ profilu > **Ustawienia**.

Te profile sieci VPN konfigurują natywnego klienta sieci VPN. Dlatego żadne aplikacje klienta sieci VPN nie są instalowane ani wypychane do urządzeń zarządzanych. Ta funkcja wymaga zarejestrowania urządzeń w usłudze Intune (rejestracji w oprogramowaniu MDM).

Aby wyświetlić bieżące ustawienia sieci VPN, które możesz skonfigurować, przejdź do tematu [Konfigurowanie ustawień sieci VPN dla urządzeń z systemem iOS w usłudze Microsoft Intune](vpn-settings-ios.md).

Dotyczy: iOS

<!-- ***********************************************-->
## <a name="device-enrollment"></a>Rejestrowanie urządzeń

### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal----4394993----"></a>W przypadku urządzeń z systemem iOS Dostosuj ekran prywatność procesu rejestracji Portal firmy <!-- 4394993  -->
Korzystając z promocji, będziesz mieć możliwość dostosowania ekranu prywatności Portal firmy, który użytkownicy końcowi zobaczą podczas rejestracji systemu iOS. W tym celu można dostosować listę rzeczy, które Twoja organizacja nie może zobaczyć ani wykonać na urządzeniu.

<!-- ***********************************************-->
## <a name="security"></a>Zabezpieczenia

### <a name="import-and-export-security-baselines------3408610------------"></a>Importuj i Eksportuj linie bazowe zabezpieczeń    <!--3408610          -->  
Dodawana jest możliwość eksportowania i importowania linii bazowych zabezpieczeń. Ta funkcja umożliwi Ci dostosowanie własnych dostosowań i udostępnienie ich między środowiskami usługi Intune.

<!-- ***********************************************-->
## <a name="notices"></a>Uwagi

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).




