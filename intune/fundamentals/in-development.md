---
title: W trakcie opracowywania — Microsoft Intune
titleSuffix: ''
description: Funkcje usługi Microsoft Intune w trakcie opracowywania
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/07/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: d71ae3c15dddedd5d9ebfaf06fcae25af89f6b82
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "76912639"
---
# <a name="in-development-for-microsoft-intune---january-2020"></a>Funkcje usługi Microsoft Intune w trakcie opracowywania — styczeń 2020 r.

Aby ułatwić Ci przygotowanie i planowanie, na tej stronie udostępniamy listę aktualizacji interfejsu użytkownika i funkcji usługi Intune, które są obecnie opracowywane, a zostaną wydane w przyszłości. Oprócz informacji na tej stronie: 

- Jeśli przewidujemy, że przed wprowadzeniem zmiany będzie konieczne wykonanie określonych działań, publikujemy również dodatkowy wpis w centrum wiadomości usługi Office.
- Po wprowadzeniu funkcji w środowisku produkcyjnym — w wersji zapoznawczej lub ogólnie dostępnej — opis tej funkcji zostanie przeniesiony z tej strony na stronę [Co nowego](whats-new.md).
- Ta strona oraz strona [Co nowego](whats-new.md) są okresowo aktualizowane. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.
- Zobacz [harmonogram działania dla platformy Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS), aby poznać strategiczne cele i terminy.

> [!NOTE]
> Ta strona odzwierciedla nasze aktualne plany dotyczące funkcji usługi Intune, które zostaną wprowadzone w przyszłych wydaniach. Zarówno daty, jak i poszczególne funkcje mogą ulec zmianie. Ta strona nie zawiera opisu wszystkich funkcji będących w trakcie opracowywania.

**Kanał informacyjny RSS**: Dowiaduj się o aktualizacjach tej strony dzięki skopiowaniu i wklejeniu następującego adresu URL w czytniku kanałów informacyjnych: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->

<!-- Common categories:  
## App management
## Device configuration
## Device enrollment
## Device management
## Intune apps
## Monitor and troubleshoot
## Role-based access control
## Security

-->
 
<!-- ***********************************************-->
## <a name="app-management"></a>Zarządzanie aplikacjami

### <a name="display-notifications-for-the-company-portal-app-on-windows---1808082----"></a>Wyświetlanie powiadomień aplikacji Portal firmy w systemie Windows<!-- 1808082  -->
Zaktualizujemy aplikację Portal firmy na urządzeniach z systemem Windows, aby wyświetlać wyskakujące powiadomienia użytkownikom nawet po zamknięciu aplikacji. W wyniku aktualizacji powiadomienia dotyczące dostępnych aplikacji będą wyświetlane tylko wtedy, gdy instalacja zostanie ukończona lub się nie powiedzie. Aplikacja Portal firmy nie będzie wyświetlać powiadomień dotyczących wymaganych aplikacji. 

### <a name="display-installation-status-messages-for-the-company-portal-app---2514416----"></a>Wyświetlanie komunikatów o stanie instalacji aplikacji Portal firmy<!-- 2514416  -->
Aplikacja Portal firmy będzie wyświetlać dodatkowe komunikaty o stanie instalacji aplikacji dla użytkowników końcowych. Poniższe warunki dotyczą nowych funkcji zależności Win32:
- Instalowanie aplikacji nie powiodło się. Zależności zdefiniowane przez administratora nie zostały spełnione.

### <a name="retarget-web-clips-to-microsoft-edge-on-ios-devices---5455276---"></a>Przekierowywanie klipów internetowych do przeglądarki Microsoft Edge na urządzeniach z systemem iOS<!-- 5455276 -->
Klipy internetowe, które działają jako przypięte aplikacje internetowe na urządzeniach z systemem iOS, będą musiały zostać zaktualizowane. Nowo wdrożone klipy internetowe będą otwierane w przeglądarce Microsoft Edge, a nie w programie Intune Managed Browser, jeśli będzie to wymagane do otwarcia w chronionej przeglądarce. Istniejące klipy internetowe trzeba będzie skierować tak, aby były otwierane w przeglądarce Microsoft Edge, a nie Managed Browser. 


<!-- ***********************************************-->
## <a name="device-configuration"></a>Konfiguracja urządzenia

### <a name="wired-network-device-configuration-profiles-for-macos-devices---3508686----"></a>Profile konfiguracji urządzeń sieci przewodowej dla urządzeń z systemem macOS<!-- 3508686  -->
Zostanie udostępniony nowy profil konfiguracji urządzenia z systemem macOS, który konfiguruje sieci przewodowe (**Konfiguracja urządzenia**  >  **Profile**  >  **Utwórz profil**  >  **macOS** dla platformy > **Sieć przewodowa** dla typu profilu). Użyj tej funkcji, aby utworzyć profile 802.1x w celu zarządzania sieciami przewodowymi, i wdróż te sieci przewodowe na urządzeniach z systemem macOS.

Dotyczy:
- macOS

### <a name="vpn-profiles-with-ikev2-vpn-connections-can-use-always-on-with-ios-devices----1947932-idready---"></a>Profile sieci VPN z połączeniami sieci VPN z protokołem IKEv2 mogą używać funkcji Zawsze włączone na urządzeniach z systemem iOS <!-- 1947932 idready -->
Na urządzeniach z systemem iOS można utworzyć profil sieci VPN, który używa połączenia IKEv2 (**Konfiguracja urządzenia**  >  **Profile**  >  **Utwórz profil**  >  **iOS/iPadOS** dla platformy > **VPN** dla typu profilu). W przyszłej aktualizacji będzie można skonfigurować funkcję Zawsze włączone przy użyciu protokołu IKEv2. Po skonfigurowaniu profile sieci VPN IKEv2 łączą się automatycznie i pozostają połączone (lub szybko ponownie nawiązują połączenie) z siecią VPN. Pozostają one połączone nawet podczas przechodzenia między sieciami lub ponownego uruchamiania urządzeń.

W systemie iOS zawsze włączona sieć VPN jest ograniczona do profilów IKEv2.

Aby wyświetlić bieżące ustawienia profilów IKEv2, które możesz skonfigurować, przejdź do tematu [Dodawanie ustawień sieci VPN na urządzeniach z systemem iOS w usłudze Microsoft Intune](../configuration/vpn-settings-ios.md#ikev2-settings).

Dotyczy:
- iOS

### <a name="improved-user-interface-experience-when-creating-configuration-profiles-on-ios-and-macos-devices---5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984-idready---"></a>Ulepszony interfejs użytkownika podczas tworzenia profilów konfiguracji na urządzeniach z systemami iOS i macOS<!-- 5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984 idready -->
Środowisko tworzenia profilu dla urządzeń z systemem iOS lub macOS w centrum administracyjnym zarządzania punktem końcowym zostanie zaktualizowane. Ta zmiana ma wpływ na następujące profile konfiguracji urządzeń (**Urządzenia**  >  **Profile konfiguracji**  >  **Utwórz profil**  >  **iOS** lub **macOS** dla platformy):

- Niestandardowe: iOS, macOS
- Funkcje urządzeń: iOS, macOS
- Ograniczenia urządzeń: iOS, macOS
- Ochrona punktu końcowego: macOS
- Rozszerzenia: macOS
- Plik preferencji: macOS

### <a name="improved-user-interface-experience-when-creating-oemconfig-configuration-profiles-on-android-enterprise-devices---5568645-idready----"></a>Ulepszony interfejs użytkownika podczas tworzenia profilów konfiguracji OEMConfig na urządzeniach z systemem Android Enterprise<!-- 5568645 idready  -->
Zaktualizowano środowisko tworzenia i edytowania profilu OEMConfig dla urządzeń z systemem Android Enterprise w centrum administracyjnym zarządzania punktami końcowymi. Zaktualizowane środowisko zawiera podsumowanie ustawień, które zostały skonfigurowane. Ta zmiana ma wpływ na profil konfiguracji urządzenia OEMConfig (**Urządzenia**  >  **Profile konfiguracji**  >  **Utwórz profil**  >  **Android Enterprise** dla platformy > **OEMConfig** dla typu profilu).

Ta funkcja ma zastosowanie do:
- Android Enterprise 

<!-- ***********************************************-->
<!--## Device enrollment-->



<!-- ***********************************************-->
<!--## Device management-->



<!-- ***********************************************-->
<!--## Intune apps-->
 

<!-- ***********************************************-->

<!--
## Monitoring and troubleshooting
-->


<!-- ***********************************************-->
## <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach

### <a name="intune-roles-user-interface-changes-coming--5801612-idready--"></a>Nadchodzące zmiany interfejsu użytkownika ról usługi Intune<!--5801612 idready-->
Interfejs użytkownika dla [centrum administracyjnego usługi Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)  >  **Administracja dzierżawy**  >  **Role** zostanie zmieniony na bardziej przyjazny dla użytkownika i intuicyjny. To środowisko zawiera te same ustawienia i szczegółowe informacje, które są obecnie używane, ale nowe środowisko korzysta z procesu przypominającego kreatora.


<!-- ***********************************************-->
## <a name="security"></a>Zabezpieczenia

### <a name="derived-credentials-support-on-android-cobo-devices--4839592--"></a>Obsługa poświadczeń pochodnych na urządzeniach z systemem Android COBO<!--4839592-->
W pełni zarządzane urządzenia z systemem Android Enterprise będą mogły korzystać z poświadczeń pochodnych. Obsługa zostanie uwzględniona w przypadku pobierania poświadczeń pochodnych dla firm Entrust Datacard, Intercede i DISA Purebred. Będzie można użyć poświadczeń pochodnych na potrzeby uwierzytelniania aplikacji, sieci Wi-Fi, sieci VPN lub podpisywania S/MIME i/lub szyfrowania przy użyciu aplikacji, które je obsługują. 

<!-- ***********************************************-->
## <a name="notices"></a>Uwagi

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).


