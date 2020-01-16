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
ms.openlocfilehash: 01ea2f75d166e5cc6aef4b890dba5722a74c1f61
ms.sourcegitcommit: 8f56220e7cafc5bc43135940575a9acb5afde730
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 01/09/2020
ms.locfileid: "75827823"
---
# <a name="in-development-for-microsoft-intune---january-2020"></a>Funkcje usługi Microsoft Intune w trakcie opracowywania — styczeń 2020 r.

Aby ułatwić Ci przygotowanie i planowanie, na tej stronie udostępniamy listę aktualizacji interfejsu użytkownika i funkcji usługi Intune, które są obecnie opracowywane, a zostaną wydane w przyszłości. Oprócz informacji na tej stronie: 

- Jeśli przewidujemy, że przed wprowadzeniem zmiany będzie konieczne wykonanie określonych działań, publikujemy również dodatkowy wpis w centrum wiadomości usługi Office.
- Gdy funkcja przechodzi do środowiska produkcyjnego, niezależnie od tego, czy jest to wersja zapoznawcza, czy ogólnie dostępna, opis funkcji zostanie przeniesiony z tej strony, aby [co nowego](whats-new.md).
- Ta strona oraz strona [Co nowego](whats-new.md) są okresowo aktualizowane. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.
- Zobacz [harmonogram działania dla platformy Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS), aby poznać strategiczne cele i terminy.

> [!NOTE]
> Ta strona przedstawia nasze bieżące oczekiwania dotyczące możliwości usługi Intune w przyszłej wersji. Zarówno daty, jak i poszczególne funkcje mogą ulec zmianie. Ta strona nie zawiera opisu wszystkich funkcji programistycznych.

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

### <a name="display-notifications-for-the-company-portal-app-on-windows---1808082----"></a>Wyświetl powiadomienia dla aplikacji Portal firmy w systemie Windows<!-- 1808082  -->
Zaktualizujemy aplikację Portal firmy na urządzeniach z systemem Windows, aby wyświetlać wyskakujące powiadomienia użytkownikom nawet po zamknięciu aplikacji. Aktualizacja będzie zawierać powiadomienia dotyczące dostępnych aplikacji tylko wtedy, gdy stan instalacji zostanie ukończony lub zakończył się niepowodzeniem. Aplikacja Portal firmy nie będzie zawierać powiadomień dotyczących wymaganych aplikacji. 

### <a name="display-installation-status-messages-for-the-company-portal-app---2514416----"></a>Wyświetlanie komunikatów o stanie instalacji dla aplikacji Portal firmy<!-- 2514416  -->
Aplikacja Portal firmy będzie wyświetlać dodatkowe komunikaty o stanie instalacji aplikacji dla użytkowników końcowych. Poniższe warunki dotyczą nowych funkcji zależności Win32:
- Instalowanie aplikacji nie powiodło się. Zależności zdefiniowane przez administratora nie zostały spełnione.

### <a name="retarget-web-clips-to-microsoft-edge-on-ios-devices---5455276-idready---"></a>Przekieruj klipy internetowe do przeglądarki Microsoft Edge na urządzeniach z systemem iOS<!-- 5455276 idready -->
Klipy internetowe, które działają jako przypięte aplikacje sieci Web na urządzeniach z systemem iOS, będą musiały zostać zaktualizowane. Nowo wdrożone klipy internetowe będą otwierane w przeglądarce Microsoft Edge, a nie Intune Managed Browser, jeśli będzie to wymagane do otwarcia w chronionej sieci. Musisz przekierować wcześniej istniejące klipy internetowe, aby upewnić się, że są otwierane w przeglądarce Microsoft Edge, a nie Managed Browser. 

### <a name="user-experience-change-when-adding-apps-to-intune---4705829-idready---"></a>Zmiana czynności użytkownika podczas dodawania aplikacji do usługi Intune<!-- 4705829 idready -->
Po dodaniu aplikacji za pośrednictwem usługi Intune zobaczysz nowe środowisko użytkownika. To środowisko zapewnia te same ustawienia i szczegóły, które zostały wcześniej użyte, ale nowe środowisko jest zgodne z procesem podobnym do kreatora przed dodaniem aplikacji do usługi Intune. To nowe środowisko udostępnia również stronę przeglądu przed dodaniem aplikacji. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**. Aby uzyskać więcej informacji, zobacz [Dodawanie aplikacji do usługi Microsoft Intune](~/apps/apps-add.md).

#### <a name="require-win32-apps-to-restart----3136567--"></a>Wymagaj ponownego uruchomienia aplikacji Win32 <!-- 3136567-->
Po pomyślnej instalacji programu można wymagać ponownego uruchomienia aplikacji Win32. Ponadto można wybrać ilość czasu (okres prolongaty) przed ponownym uruchomieniem.

<!-- ***********************************************-->
## <a name="device-configuration"></a>Konfiguracja urządzenia

### <a name="add-automatic-proxy-settings-to-wi-fi-profiles-for-android-enterprise-work-profiles---4490822-idready---"></a>Dodawanie automatycznych ustawień serwera proxy do profilów sieci Wi-Fi dla profilów służbowych systemu Android Enterprise<!-- 4490822 idready -->
Na urządzeniach profilu służbowego systemu Android Enterprise można tworzyć profile sieci Wi-Fi. Po wybraniu typu przedsiębiorstwa Wi-Fi można także wprowadzić typ protokołu uwierzytelniania rozszerzonego (EAP) używanego w sieci Wi-Fi.

W przyszłej aktualizacji, po wybraniu typu przedsiębiorstwa, będziesz mieć możliwość wprowadzenia automatycznych ustawień serwera proxy, w tym adresu URL serwera proxy, takiego jak `proxy.contoso.com`.

Aby wyświetlić bieżące ustawienia sieci Wi-Fi, które można skonfigurować, przejdź do [dodawania ustawień sieci Wi-Fi dla urządzeń z systemem Android Enterprise i kiosku systemu Android w](../configuration/wi-fi-settings-android-enterprise.md)Microsoft Intune.

Dotyczy:
- Android Enterprise — profil służbowy

### <a name="wired-network-device-configuration-profiles-for-macos-devices---3508686----"></a>Profile konfiguracji urządzeń sieci przewodowej dla urządzeń z systemem macOS<!-- 3508686  -->
Zostanie udostępniony nowy profil konfiguracji urządzenia z systemem macOS, który konfiguruje sieci przewodowe (**konfigurację urządzenia** > **profile** > **Utwórz profil** > **macOS** dla platformy > **sieci przewodowej dla typu profilu). Użyj tej funkcji, aby utworzyć profile 802.1 x w celu zarządzania sieciami przewodowymi i wdrożyć te sieci przewodowe na urządzeniach macOS.

Dotyczy:
- macOS

### <a name="vpn-profiles-with-ikev2-vpn-connections-can-use-always-on-with-ios-devices----1947932-idready---"></a>Profile sieci VPN z połączeniami sieci VPN z protokołem IKEv2 mogą używać zawsze na urządzeniach z systemem iOS <!-- 1947932 idready -->
Na urządzeniach z systemem iOS można utworzyć profil sieci VPN, który używa połączenia IKEv2 (**Konfiguracja urządzenia** > **profile** > **tworzenia profilu** > **iOS/iPadOS** > **sieci VPN dla typu profilu). W przyszłej aktualizacji można skonfigurować protokół zawsze włączony przy użyciu protokołu IKEv2. Po skonfigurowaniu, profile sieci VPN IKEv2 łączą się automatycznie i pozostają połączone (lub szybko ponownie nawiązuje połączenie) z siecią VPN. Pozostaje połączony nawet podczas przechodzenia między sieciami lub ponownego uruchamiania urządzeń.

W systemie iOS zawsze włączona jest sieć VPN ograniczona do profilów IKEv2.

Aby wyświetlić bieżące ustawienia profilów IKEv2, które możesz skonfigurować, przejdź do tematu [Dodawanie ustawień sieci VPN na urządzeniach z systemem iOS w usłudze Microsoft Intune](../configuration/vpn-settings-ios.md#ikev2-settings).

Dotyczy:
- iOS

### <a name="improved-user-interface-experience-when-creating-configuration-profiles-on-ios-and-macos-devices---5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984-idready---"></a>Ulepszone środowisko interfejsu użytkownika podczas tworzenia profilów konfiguracji na urządzeniach z systemem iOS i macOS<!-- 5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984 idready -->
Po utworzeniu profilu dla urządzeń z systemem iOS lub macOS środowisko w centrum administracyjnym zarządzania punktem końcowym zostanie zaktualizowane. Ta zmiana ma wpływ na następujące profile konfiguracji urządzeń (**urządzenia** > **profile konfiguracji** > **Tworzenie profilu** > **iOS** lub **macOS** dla platformy):

- Niestandardowe: iOS, macOS
- Funkcje urządzeń (systemy iOS i MacOS)
- Ograniczenia dotyczące urządzeń: iOS, macOS
- Ochrona punktu końcowego: macOS
- Rozszerzenia: macOS
- Plik preferencji

### <a name="improved-user-interface-experience-when-creating-oemconfig-configuration-profiles-on-android-enterprise-devices---5568645-idready----"></a>Ulepszone środowisko interfejsu użytkownika podczas tworzenia profilów konfiguracji OEMConfig na urządzeniach z systemem Android Enterprise<!-- 5568645 idready  -->
Podczas tworzenia lub edytowania profilu OEMConfig dla urządzeń z systemem Android Enterprise zostaje zaktualizowane środowisko centrum administracyjnego zarządzania punktami końcowymi. Zaktualizowane środowisko zawiera podsumowanie ustawień, które zostały skonfigurowane w skrócie. Ta zmiana ma wpływ na profil konfiguracji urządzenia OEMConfig (**urządzenia** > **profile konfiguracji** > **tworzenia profilu** > **Android Enterprise** dla platformy > **OEMConfig** dla typu profilu).

Ta funkcja ma zastosowanie do:
- Android Enterprise 

<!-- ***********************************************-->
## <a name="device-enrollment"></a>Rejestrowanie urządzeń

### <a name="block-android-enrollments-by-device-manufacturer--5197392-idready--"></a>Blokuj rejestracje systemu Android według producenta urządzenia<!--5197392 idready-->
Można zablokować możliwość rejestrowania urządzeń na podstawie producenta urządzenia. Dotyczy to urządzeń z systemem Android i profilem roboczym systemu Android Enterprise. Aby wyświetlić ograniczenia rejestracji, przejdź do [centrum administracyjne programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)> **urządzeń** > **ograniczenia rejestracji**.



<!-- ***********************************************-->
## <a name="device-management"></a>Zarządzanie urządzeniami


### <a name="new-information-in-device-details---4471759-5604099----"></a>Nowe informacje w obszarze Szczegóły urządzenia<!-- 4471759 5604099  -->
Następujące informacje zostaną dodane do **przegląd** stronie dla urządzeń:
- Pojemność pamięci (ilość pamięci fizycznej w urządzeniu)
- Pojemność magazynu (ilość pamięci fizycznej na urządzeniu) 
- Typ i szybkość procesora CPU
- Pamięć RAM i dane procesora

<!-- ***********************************************-->
<!--## Intune apps-->
 

<!-- ***********************************************-->

<!--
## Monitoring and troubleshooting
-->


<!-- ***********************************************-->
## <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach

### <a name="new-intune-built-in-role-endpoint-security-manager--4253397-idready--"></a>Nowa wbudowana rola usługi Intune — Menedżer zabezpieczeń punktu końcowego<!--4253397 idready-->
Zostanie udostępniona nowa wbudowana rola usługi Intune: Menedżer zabezpieczeń punktu końcowego. Ta nowa rola zapewnia administratorom pełen dostęp do węzła Menedżera punktów końcowych w usłudze Intune i tylko dostęp do innych obszarów. Rola to rozszerzenie roli "administrator zabezpieczeń" z usługi Azure AD. Jeśli obecnie używasz tylko ról administratorów globalnych, nie musisz wprowadzać żadnych zmian. Jeśli używasz ról i chcesz korzystać ze stopnia szczegółowości, który zapewnia rola Menedżer zabezpieczeń punktu końcowego, przypisz tę rolę, gdy zostanie udostępniona. Aby uzyskać więcej informacji na temat ról wbudowanych, zobacz [kontroli dostępu opartej na rolach](role-based-access-control.md).

### <a name="intune-roles-user-interface-changes-coming--5801612-idready--"></a>Zmiany interfejsu użytkownika ról usługi Intune<!--5801612 idready-->
Interfejs użytkownika dla [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) > **Administracja dzierżaw** > **ról** zostanie zmieniony na bardziej przyjazny dla użytkownika i intuicyjny projekt. To środowisko zawiera te same ustawienia i szczegółowe informacje, które są obecnie używane, ale nowe środowisko wykorzystuje proces przypominający kreatora.


<!-- ***********************************************-->
## <a name="security"></a>Zabezpieczenia

### <a name="derived-credentials-support-on-android-cobo-devices--4839592--"></a>Obsługa poświadczeń pochodnych na urządzeniach z systemem Android COBO<!--4839592-->
W pełni zarządzane urządzenia z systemem Android Enterprise będą mogły korzystać z poświadczeń pochodnych. Pomoc techniczna zostanie uwzględniona podczas pobierania poświadczenie pochodne dla Entrust Datacard, intercede i DISA purebred. Będziesz mieć możliwość użycia poświadczenie pochodne do uwierzytelniania aplikacji, sieci Wi-Fi, VPN lub podpisywania S/MIME i/lub szyfrowania przy użyciu aplikacji, które je obsługują. 

<!-- ***********************************************-->
## <a name="notices"></a>Uwagi

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).


