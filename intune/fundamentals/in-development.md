---
title: W trakcie opracowywania — Microsoft Intune
titleSuffix: ''
description: Funkcje usługi Microsoft Intune w trakcie opracowywania
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: ea5fae72f6e2057ef0b03a7bd295085ed1ac3bbd
ms.sourcegitcommit: 5807f4db4a45a093ce2fd6cb0c480bec384ec1ff
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/19/2019
ms.locfileid: "72601551"
---
# <a name="in-development-for-microsoft-intune---october-2019"></a>W trakcie opracowywania — Microsoft Intune — październik 2019 r.

Aby ułatwić Ci przygotowanie i planowanie, na tej stronie udostępniamy listę aktualizacji interfejsu użytkownika i funkcji usługi Intune, które są obecnie opracowywane, a zostaną wydane w przyszłości. Oprócz informacji na tej stronie:

- Jeśli przewidujemy, że przed wprowadzeniem zmiany będzie konieczne wykonanie określonych działań, publikujemy również dodatkowy wpis w centrum wiadomości usługi Office.
- Gdy funkcja przechodzi do środowiska produkcyjnego, niezależnie od tego, czy jest to wersja zapoznawcza, czy ogólnie dostępna, opis funkcji zostanie przeniesiony z tej strony do [nowości](whats-new.md).
- Ta strona oraz strona [Co nowego](whats-new.md) są okresowo aktualizowane. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.
- Zobacz [harmonogram działania dla platformy Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS), aby poznać strategiczne cele i terminy.

> [!NOTE]
> Ta strona przedstawia nasze bieżące oczekiwania dotyczące możliwości usługi Intune w przyszłej wersji. Zarówno daty, jak i poszczególne funkcje mogą ulec zmianie. Ta strona nie zawiera opisu wszystkich funkcji programistycznych.

**Kanał informacyjny RSS**: dowiaduj się o aktualizacjach tej strony dzięki skopiowaniu i wklejeniu następującego adresu URL w czytniku kanałów informacyjnych: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

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

### <a name="apply-dark-mode-in-ios-company-portal----4911422----"></a>Zastosuj tryb ciemny w Portal firmy systemu iOS <!-- 4911422  -->
Zaplanowano tryb ciemny dla Portal firmy systemu iOS. Będziesz w stanie pobrać aplikacje firmowe, zarządzać urządzeniami i uzyskać pomoc techniczną w wybranym przez siebie schemacie kolorów. Aby uzyskać więcej informacji na temat konfigurowania Portalu firmy dla systemu iOS, zobacz [Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune](../apps/company-portal-app.md).

### <a name="run-win32-apps-on-windows-10-s-mode-devices----3747604----"></a>Uruchamianie aplikacji Win32 na urządzeniach z systemem Windows 10 w trybie S <!-- 3747604  --> 
Będzie można instalować i uruchamiać aplikacje Win32 na urządzeniach zarządzanych w trybie systemu Windows 10 S. Utwórz co najmniej jedną uzupełniającą zasadę dla trybu S przy użyciu narzędzi programu PowerShell Windows Defender Application Control (WDAC). Użyj portalu podpisywania funkcji Device Guard, aby podpisywać dodatkowe zasady. Następnie Przekaż i Rozpowszechnij zasady za pomocą usługi Intune. 

W usłudze Intune znajdziesz tę możliwość, wybierając pozycję **aplikacje klienckie**  > **zasady uzupełniania systemu Windows 10 S**. 

### <a name="set-app-availability-based-on-a-date-and-time----3510685----"></a>Ustawianie dostępności aplikacji na podstawie daty i godziny <!-- 3510685  -->
Jako administrator możesz skonfigurować godzinę rozpoczęcia i termin ostateczny dla wymaganej aplikacji. Po uruchomieniu rozszerzenie zarządzania usługi Intune pobierze zawartość aplikacji i przeprowadzi ją w pamięci podręcznej. Aplikacja zostanie zainstalowana w ostatecznym terminie. W przypadku dostępnych aplikacji czas rozpoczęcia będzie określać, kiedy aplikacja jest widoczna w Portal firmy. 

Aby ustawić dostępność aplikacji na podstawie daty i godziny:

1. W usłudze Intune wybierz pozycję **Aplikacje klienckie** > **Aplikacje**. 
1. Wybierz aplikację z listy lub Dodaj nową, wybierając pozycję **Dodaj**. 
1. W bloku aplikacja wybierz pozycję **przypisania** > **Dodaj grupę**. 
1. Ustaw typu **Assignment** na **Required** a następnie wybierz pozycję **Included grupy**. 
1. Ustaw ustawienie Ustaw **tę aplikację jako wymaganą dla wszystkich użytkowników** na **wartość tak**. 
1. Wybierz pozycję **Edytuj** , aby zmodyfikować opcje **środowiska użytkownika końcowego** . 
1. W bloku **środowisko użytkownika końcowego** Ustaw **czas dostępności oprogramowania** zgodnie z wymaganiami. 

Aby uzyskać więcej informacji, zobacz [Dodawanie aplikacji do usługi Microsoft Intune](../apps/apps-add.md).

### <a name="require-win32-apps-to-restart----3136567----"></a>Wymagaj ponownego uruchomienia aplikacji Win32 <!-- 3136567  -->
Po pomyślnej instalacji będzie można wymagać ponownego uruchomienia aplikacji Win32. Można wybrać ilość czasu (okres prolongaty) przed ponownym uruchomieniem.

### <a name="display-notifications-for-the-company-portal-app-on-windows----1808082----"></a>Wyświetl powiadomienia dla aplikacji Portal firmy w systemie Windows <!-- 1808082  -->
Zaktualizujemy aplikację Portal firmy na urządzeniach z systemem Windows, aby wyświetlać wyskakujące powiadomienia użytkownikom nawet po zamknięciu aplikacji. Aktualizacja będzie zawierać powiadomienia dotyczące dostępnych aplikacji tylko wtedy, gdy stan instalacji zostanie ukończony lub zakończył się niepowodzeniem. Aplikacja Portal firmy nie będzie zawierać powiadomień dotyczących wymaganych aplikacji.

### <a name="display-installation-status-messages-for-the-company-portal-app----2514416----"></a>Wyświetlanie komunikatów o stanie instalacji dla aplikacji Portal firmy <!-- 2514416  -->
Aplikacja Portal firmy będzie wyświetlać dodatkowe komunikaty o stanie instalacji aplikacji dla użytkowników końcowych. Poniższe warunki dotyczą nowych funkcji zależności Win32:
- Instalowanie aplikacji nie powiodło się. Zależności zdefiniowane przez administratora nie zostały spełnione.
- Aplikacja została zainstalowana pomyślnie, ale wymaga ponownego uruchomienia.
- Aplikacja jest w trakcie instalacji, ale wymaga ponownego uruchomienia, aby kontynuować.

### <a name="assign-the-microsoft-edge-beta-for-macos----4678761----"></a>Przypisywanie programu Microsoft Edge beta do macOS <!-- 4678761  -->
Można dodać i przypisać najnowszą wersję programu Microsoft Edge beta do usługi Intune dla urządzeń macOS. 

Aby przypisać program Microsoft Edge beta dla urządzeń macOS:
1. W usłudze Intune wybierz pozycję **aplikacje klienckie**  > **aplikacje**  > **Dodaj aplikację**  > **Microsoft Edge-macOS**. 
1. Przypisz program Microsoft Edge beta do odpowiednich grup. Program Microsoft AutoUpdate (MAU) zachowuje aktualność programu Microsoft Edge. 
 
Aby uzyskać więcej informacji na temat przeglądarki Microsoft Edge, zobacz [Zarządzanie dostępem do sieci Web za pomocą przeglądarki Microsoft Edge z Microsoft Intune](../apps/manage-microsoft-edge.md).

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Skonfiguruj zawartość powiadomienia aplikacji dla kont organizacji <!-- 2576686 -->
Aplikacja usługi Intune na urządzeniach z systemem Android i iOS umożliwi kontrolowanie zawartości powiadomień aplikacji dla kont organizacji. Ta funkcja będzie wymagała obsługi aplikacji i może być niedostępna dla wszystkich aplikacji korzystających z aplikacji. Aby uzyskać więcej informacji na temat zasad ochrony aplikacji (APP), zobacz [Co to są zasady ochrony aplikacji?](../apps/app-protection-policy.md)


<!-- ***********************************************-->
## <a name="device-configuration"></a>Konfiguracja urządzenia

### <a name="new-device-firmware-configuration-interface-profile-for-devices-that-run-windows-10-and-later----2266073----"></a>Nowy profil interfejsu konfiguracji oprogramowania układowego urządzenia dla urządzeń z systemem Windows 10 lub nowszym <!-- 2266073  -->
W systemie Windows 10 i nowszych można utworzyć profil konfiguracji urządzenia w celu kontrolowania ustawień i funkcji: 

1. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
1. Jako platformę wybierz pozycję **Windows 10 i nowsze**. 
 
Nowy typ profilu interfejsu konfiguracji oprogramowania układowego urządzenia umożliwi usłudze Intune zarządzanie ustawieniami interfejsu UEFI (BIOS).

Aby uzyskać informacje na temat bieżących ustawień, które można skonfigurować, zobacz [stosowanie funkcji i ustawień na urządzeniach przy użyciu profilów urządzeń w Microsoft Intune](../configuration/device-profiles.md).

Ta funkcja ma zastosowanie do systemu Windows 10 RS5 (1809) lub nowszego na wybranych urządzeniach.
 

<!-- ***********************************************-->
## <a name="device-enrollment"></a>Rejestrowanie urządzeń

### <a name="for-ios-devices-customize-the-enrollment-privacy-window-of-company-portal----4394993----"></a>W przypadku urządzeń z systemem iOS Dostosuj okno prywatności rejestracji Portal firmy <!-- 4394993  -->
Przy użyciu języka Markdown będzie można dostosować okno z informacjami o ochronie prywatności w aplikacji Portal firmy, które użytkownicy końcowi widzą podczas rejestracji systemu iOS. W tym celu można dostosować listę elementów i działań, których Twoja organizacja nie może zobaczyć ani wykonać na urządzeniu.

<!-- ***********************************************-->
## <a name="device-management"></a>Zarządzanie urządzeniami


### <a name="edit-the-group-tag-value-for-autopilot-devices---4816775---"></a>Edytuj wartość tagu grupy dla urządzeń z autopilotażem<!-- 4816775 -->
Będziesz w stanie edytować wartość **tagu grupy** dla urządzeń z autopilotażem:

1. Wybierz pozycję Usługa **Intune**  > **rejestracja urządzeń**  > **rejestracja w systemie Windows**  >   > **urządzeń**z**systemem Windows** .
1. Wybierz urządzenie.
1. W okienku po prawej stronie Zmień wartość **tagu grupy** .
1. Wybierz pozycję **Zapisz**.

### <a name="target-macos-user-groups-to-require-jamf-management----4061739---"></a>Docelowa Grupa użytkowników macOS do wymagania zarządzania Jamf <!-- 4061739 -->
Będziesz mieć możliwość nawiązywania określonych grup użytkowników, aby wymagały zarządzania urządzeniami macOS przez Jamf. Ten element docelowy umożliwi zastosowanie integracji zgodności Jamf z podzbiorem urządzeń macOS, podczas gdy inne urządzenia będą nadal zarządzane przez usługę Intune. Określanie wartości docelowej umożliwia również stopniowe Migrowanie urządzeń użytkowników z jednego systemu zarządzania urządzeniami przenośnymi do drugiego.

### <a name="deploy-software-updates-to-macos-devices----3194876---"></a>Wdrażanie aktualizacji oprogramowania na urządzeniach macOS <!-- 3194876 -->
Będziesz w stanie wdrożyć aktualizacje oprogramowania w grupach urządzeń macOS. Ta funkcja obejmuje krytyczne, oprogramowanie układowe, plik konfiguracji i inne aktualizacje. Można wysyłać aktualizacje przy następnym zaewidencjonowaniu urządzenia. Możesz też wybrać Harmonogram tygodniowy, aby wdrożyć aktualizacje w określonym lub wyznaczonym okresie. 

Ta funkcja ułatwia aktualizowanie urządzeń poza standardowymi godzinami pracy lub godzinami zewnętrznymi, gdy dział pomocy technicznej jest w pełni zatrudniony. Zostanie również wyświetlony szczegółowy raport dotyczący wszystkich urządzeń macOS, które mają wdrożone aktualizacje. Możesz przejść do szczegółów raportu według urządzenia, aby zobaczyć stan konkretnej aktualizacji.

<!-- ***********************************************-->
## <a name="monitoring-and-troubleshooting"></a>Monitorowanie i rozwiązywanie problemów

### <a name="android-report-on-the-devices-overview-page----2984353----"></a>Raport systemu Android na stronie przegląd urządzeń <!-- 2984353  -->
Na stronie **przegląd urządzeń** zostanie dodany nowy raport. Raport zawiera informacje o liczbie urządzeń z systemem Android zarejestrowanych w poszczególnych rozwiązaniach do zarządzania urządzeniami. Na wykresie przedstawiono liczbę urządzeń dla zarejestrowanego profilu służbowego, w pełni zarządzane, dedykowane i administratora urządzenia. 

Aby wyświetlić raport, wybierz pozycję **Intune** > **Devices** > **Przegląd**.

### <a name="updated-support-experience-------5012398------"></a>Zaktualizowane środowisko pomocy technicznej   <!--  5012398    -->
W ramach dalszych ulepszeń będziemy aktualizować środowisko pomocy technicznej w konsoli usługi Intune.  Zajmiemy się wyszukiwaniem w konsoli i opiniami dotyczącymi typowych problemów. usprawniamy przepływ pracy, aby skontaktować się z pomocą techniczną.     

<!-- ***********************************************-->
<!--## Security-->


<!-- ***********************************************-->
## <a name="notices"></a>Uwagi

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).
