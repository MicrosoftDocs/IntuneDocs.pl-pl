---
title: W trakcie opracowywania — Microsoft Intune
titleSuffix: ''
description: Funkcje usługi Microsoft Intune w trakcie opracowywania
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/03/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7113552e09a7c7fa145a452e56575bfaf5297c3e
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514572"
---
# <a name="in-development-for-microsoft-intune---february-2020"></a>Funkcje usługi Microsoft Intune w trakcie opracowywania — luty 2020 r.

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

### <a name="retarget-web-clips-to-microsoft-edge-on-iosipados-devices---5455276---"></a>Przekierowywanie klipów internetowych do przeglądarki Microsoft Edge na urządzeniach z systemem iOS/iPadOS<!-- 5455276 -->
Klipy internetowe, które działają jako przypięte aplikacje internetowe na urządzeniach z systemem iOS/iPadOS, będą musiały zostać zaktualizowane. Nowo wdrożone klipy internetowe będą otwierane w przeglądarce Microsoft Edge, a nie w programie Intune Managed Browser, jeśli będzie to wymagane do otwarcia w chronionej przeglądarce. Istniejące klipy internetowe trzeba będzie skierować tak, aby były otwierane w przeglądarce Microsoft Edge, a nie Managed Browser.

### <a name="macos-company-portal-user-experience-improvements---5568987---"></a>Ulepszenia środowiska użytkownika w aplikacji Portal firmy dla systemu macOS<!-- 5568987 -->
Ulepszamy obsługę rejestracji urządzeń z systemem macOS i aplikację Portal firmy dla komputerów Mac. Można oczekiwać następujących zmian:
- Lepsza obsługa **aktualizacji automatycznych** firmy Microsoft podczas rejestracji, co zapewni, że użytkownicy będą mieć najnowszą wersję aplikacji Portal firmy.
- Ulepszony krok sprawdzania zgodności podczas rejestracji.
- Obsługa kopiowanych identyfikatorów zdarzeń, aby użytkownicy mogli szybciej wysyłać błędy z urządzeń do zespołu pomocy technicznej w firmie.

Aby uzyskać więcej informacji o rejestracji i aplikacji Portal firmy dla komputerów Mac, zobacz Rejestrowanie urządzenia z systemem macOS za pomocą aplikacji Portal firmy (https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos-cp). 


### <a name="screen-removed-from-company-portal-android-work-profile-enrollment--6103987---"></a>Ekran usunięty z aplikacji Portal firmy, rejestracja profilu służbowego systemu Android<!--6103987 -->
Ekran **Co dalej?** zostanie usunięty z przepływu rejestracji profilu służbowego systemu Android w aplikacji Portal firmy, aby usprawnić obsługę użytkowników. Przejdź do tematu [Rejestracja przy użyciu profilu służbowego systemu Android]( https://docs.microsoft.com/intune-user-help/enroll-device-android-work-profile), aby zobaczyć bieżący przepływ rejestracji profilu służbowego systemu Android.

### <a name="microsoft-defender-advanced-threat-protection-atp-app-for-macos---5424518-idready---"></a>Aplikacja Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender dla systemu macOS<!-- 5424518 idready -->
Usługa Intune zapewnia łatwe wdrażanie aplikacji Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender dla systemu macOS na zarządzanych urządzeniach Mac. Aby uzyskać więcej informacji, zobacz [Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender dla komputerów Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac). 

<!-- ***********************************************-->
## <a name="device-configuration"></a>Konfiguracja urządzenia

### <a name="wired-network-device-configuration-profiles-for-macos-devices---3508686----"></a>Profile konfiguracji urządzeń sieci przewodowej dla urządzeń z systemem macOS<!-- 3508686  -->
Zostanie udostępniony nowy profil konfiguracji urządzenia z systemem macOS, który konfiguruje sieci przewodowe (**Konfiguracja urządzenia**  >  **Profile**  >  **Utwórz profil**  >  **macOS** dla platformy > **Sieć przewodowa** dla typu profilu). Użyj tej funkcji, aby utworzyć profile 802.1x w celu zarządzania sieciami przewodowymi, i wdróż te sieci przewodowe na urządzeniach z systemem macOS.

Dotyczy:
- macOS

### <a name="vpn-profiles-with-ikev2-vpn-connections-can-use-always-on-with-iosipados-devices----1947932-idready---"></a>Profile sieci VPN z połączeniami sieci VPN z protokołem IKEv2 mogą używać funkcji Zawsze włączone na urządzeniach z systemem iOS/iPadOS <!-- 1947932 idready -->
Na urządzeniach z systemem iOS/iPadOS można utworzyć profil sieci VPN, który używa połączenia IKEv2 (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS/iPadOS** jako platforma > **VPN** jako typ profilu). W przyszłej aktualizacji będzie można skonfigurować funkcję Zawsze włączone przy użyciu protokołu IKEv2. Po skonfigurowaniu profile sieci VPN IKEv2 łączą się automatycznie i pozostają połączone (lub szybko ponownie nawiązują połączenie) z siecią VPN. Pozostają one połączone nawet podczas przechodzenia między sieciami lub ponownego uruchamiania urządzeń.

W systemie iOS/iPadOS zawsze włączona sieć VPN jest ograniczona do profilów IKEv2.

Aby wyświetlić bieżące ustawienia profilów IKEv2, które możesz skonfigurować, przejdź do tematu [Dodawanie ustawień sieci VPN na urządzeniach z systemem iOS/iPadOS w usłudze Microsoft Intune](../configuration/vpn-settings-ios.md#ikev2-settings).

Dotyczy:
- iOS

### <a name="improved-user-interface-experience-when-creating-configuration-profiles-on-iosipados-and-macos-devices---5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984-idready---"></a>Ulepszony interfejs użytkownika podczas tworzenia profilów konfiguracji na urządzeniach z systemami iOS/iPadOS i macOS<!-- 5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984 idready -->
Środowisko tworzenia profilu dla urządzeń z systemem iOS/iPadOS lub macOS w centrum administracyjnym zarządzania punktem końcowym zostanie zaktualizowane. Ta zmiana ma wpływ na następujące profile konfiguracji urządzeń (**Urządzenia**  >  **Profile konfiguracji**  >  **Utwórz profil**  >  **iOS** lub **macOS** dla platformy):

- Niestandardowe: iOS/iPadOS, macOS
- Funkcje urządzenia: iOS/iPadOS, macOS
- Ograniczenia urządzeń: iOS/iPadOS, macOS
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
## <a name="device-management"></a>Zarządzanie urządzeniami

### <a name="change-primary-user-for-windows-devices----3794742---"></a>Zmienianie użytkownika podstawowego dla urządzeń z systemem Windows <!-- 3794742 -->
Będzie można zmieniać użytkownika podstawowego dla urządzeń hybrydowych z systemem Windows i urządzeń przyłączonych do usługi Azure AD. Aby to zrobić, przejdź do pozycji **Intune** > **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Właściwości** > **Użytkownik podstawowy**. 

### <a name="serial-number-on-the-apple-mdm-push-certificate-page--5947765---"></a>Numer seryjny na stronie certyfikatu wypychania Apple MDM<!--5947765 -->
Na stronie certyfikatu wypychania Apple MDM będzie wyświetlany numer seryjny. Numer seryjny jest wymagany do odzyskania dostępu do certyfikatu wypychania Apple MDM, jeśli zostanie utracony dostęp do identyfikatora Apple, za pomocą którego utworzono certyfikat. Aby wyświetlić numer seryjny, przejdź do pozycji **Urządzenia** > **iOS** > **Rejestracja w systemie iOS** > **Certyfikat wypychania Apple MDM**.

### <a name="choose-which-iosipados-updates-to-push-to-enrolled-devices--5879689---"></a>Wybieranie aktualizacji systemu iOS/iPadOS w celu wypychania do zarejestrowanych urządzeń<!--5879689 -->
Będzie można wybrać konkretną aktualizację systemu iOS/iPadOS w celu wypychania do urządzeń, które zarejestrowano przy użyciu programu Apple Business Manager lub Apple School Manager. Takie urządzenia muszą mieć ustawione zasady konfiguracji urządzeń w celu opóźniania widoczności aktualizacji oprogramowania przez pewną liczbę dni. Aby wyświetlić tę funkcję, przejdź do pozycji MEM > **Urządzenia** > **iOS** > **Zasady aktualizacji dla systemu iOS/iPadOS** > **Utwórz profil**.

### <a name="new-update-schedule-options-for-pushing-os-updates-to-enrolled-iosipados-devices--5879689--"></a>Nowe opcje harmonogramu aktualizacji dla wypychania aktualizacji systemu operacyjnego do zarejestrowanych urządzeń z systemem iOS/iPadOS<!--5879689-->
Podczas planowania aktualizacji systemu operacyjnego dla urządzeń z systemem iOS/iPadOS będą dostępne następujące opcje. Dotyczy to urządzeń, w przypadku których użyto typów rejestracji programu Apple Business Manager lub Apple School Manager.
- Aktualizuj przy następnym meldowaniu
- Aktualizuj w zaplanowanym czasie
- Aktualizuj poza zaplanowanym czasem

W przypadku dwóch ostatnich opcji można utworzyć wiele okien czasu.

Aby wyświetlić nowe opcje, przejdź do pozycji MEM > **Urządzenia** > **iOS** > **Zasady aktualizacji dla systemu iOS/iPadOS** > **Utwórz profil**.


<!-- ***********************************************-->
<!--## Intune apps-->
 

<!-- ***********************************************-->
## <a name="monitoring-and-troubleshooting"></a>Monitorowanie i rozwiązywanie problemów

### <a name="improved-intune-reporting-experience---3791418-idready---"></a>Udoskonalone środowisko raportowania usługi Intune<!-- 3791418 idready -->
Usługa Intune oferuje teraz udoskonalone środowisko raportowania, w tym nowe typy raportów, lepszą organizację raportów, bardziej ukierunkowane widoki, ulepszone funkcje raportów, a także spójniejsze i aktualniejsze dane. Środowisko raportowania zostanie przekształcone z publicznej wersji zapoznawczej w wersję ogólnie dostępną. Ponadto wersja ogólnie dostępna zapewni obsługę lokalizacji, poprawki błędów, udoskonalenia projektu i zagregowane dane zgodności urządzeń na kafelkach w [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

Nowe typy raportów koncentrują się na następujących kwestiach:
- **Operacyjne** — oferują nowe rekordy skoncentrowane na złej kondycji. 
- **Organizacyjne** — zawierają szersze podsumowanie ogólnego stanu.
- **Historyczne** — przedstawiają wzorce i trendy w wybranym okresie.
- **Specjalistyczne** — umożliwiają tworzenie własnych niestandardowych raportów przy użyciu danych pierwotnych.

Pierwszy zestaw nowych raportów koncentruje się na zgodności urządzeń. Aby uzyskać więcej informacji, zobacz tematy [Blog - Microsoft Intune reporting framework](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/New-Reporting-Framework-Coming-to-Intune/ba-p/1009553) (Blog — platforma raportowania w usłudze Microsoft Intune) i [Intune reports](~/fundamentals/reports.md) (Raporty usługi Intune).



<!-- ***********************************************-->
## <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach

### <a name="intune-roles-user-interface-changes-coming--5801612-idready--"></a>Nadchodzące zmiany interfejsu użytkownika ról usługi Intune<!--5801612 idready-->
Interfejs użytkownika dla [centrum administracyjnego usługi Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)  >  **Administracja dzierżawy**  >  **Role** zostanie zmieniony na bardziej przyjazny dla użytkownika i intuicyjny. To środowisko zawiera te same ustawienia i szczegółowe informacje, które są obecnie używane, ale nowe środowisko korzysta z procesu przypominającego kreatora.


<!-- ***********************************************-->
## <a name="security"></a>Zabezpieczenia

### <a name="derived-credentials-support-on-android-cobo-devices--4839592--"></a>Obsługa poświadczeń pochodnych na urządzeniach z systemem Android COBO<!--4839592-->
W pełni zarządzane urządzenia z systemem Android Enterprise będą mogły korzystać z poświadczeń pochodnych. Obsługa zostanie uwzględniona w przypadku pobierania poświadczeń pochodnych dla firm Entrust Datacard, Intercede i DISA Purebred. Będzie można użyć poświadczeń pochodnych na potrzeby uwierzytelniania aplikacji, sieci Wi-Fi, sieci VPN lub podpisywania S/MIME i/lub szyfrowania przy użyciu aplikacji, które je obsługują.

### <a name="use-antivirus-policy-to-manage-settings-for-microsoft-defender-antivirus-and-the-windows-security-experience--6131401---"></a>Używanie zasad ochrony antywirusowej do zarządzania ustawieniami programu Microsoft Defender Antivirus i środowiskiem zabezpieczeń systemu Windows<!--6131401 -->
W węźle *Zabezpieczenia punktu końcowego* będzie można skonfigurować ustawienia **Ochrona antywirusowa**. Konfigurując zasady ochrony antywirusowej, można zdefiniować ustawienia dla urządzeń z systemem Windows 10 przy użyciu dwóch typów profilów:

- Program antywirusowy Microsoft Defender: zarządzanie ustawieniami ochrony chmury, wykluczeń ochrony antywirusowej, korygowania, opcji skanowania i innymi.
- Środowisko zabezpieczeń systemu Windows: zarządzanie sposobem korzystania przez użytkowników z ustawień zabezpieczeń systemu Windows na urządzeniach. Będzie można skonfigurować elementy, które użytkownicy końcowi mogą wyświetlać w Centrum zabezpieczeń usługi Microsoft Defender, i otrzymywane przez nich powiadomienia. 

<!-- ***********************************************-->
## <a name="notices"></a>Uwagi

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).


