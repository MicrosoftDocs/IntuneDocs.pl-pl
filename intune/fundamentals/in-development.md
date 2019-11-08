---
title: W trakcie opracowywania — Microsoft Intune
titleSuffix: ''
description: Funkcje usługi Microsoft Intune w trakcie opracowywania
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/28/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3720b0b9a67f0c3462993feef4162ef35f7f3f92
ms.sourcegitcommit: d1b36501186e867355843ddd67c795ade800b76a
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2019
ms.locfileid: "73182928"
---
# <a name="in-development-for-microsoft-intune---november-2019"></a>W trakcie opracowywania — Microsoft Intune — listopad 2019 r.

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

### <a name="smime-support-for-microsoft-outlook-mobile----2669398----"></a>Obsługa protokołu S/MIME dla programu Microsoft Outlook Mobile <!-- 2669398  -->
Usługa Intune będzie obsługiwać dostarczanie certyfikatów podpisywania S/MIME i szyfrowania, które mogą być używane z programem Outlook Mobile w systemach iOS i Android. Aby uzyskać powiązane informacje, zobacz [Ustawienia poczty e-mail dla urządzeń z systemem iOS](~/configuration/email-settings-ios.md) i [Ustawienia poczty e-mail dla urządzeń z systemem Android](~/configuration/email-settings-android.md).

### <a name="custom-settings-support-for-macos-applications----4736278----"></a>Obsługa ustawień niestandardowych dla aplikacji macOS <!-- 4736278  -->
Usługa Intune będzie obsługiwać ustawienia niestandardowe, umożliwiając dodawanie określonych kluczy i wartości do istniejącego pliku listy właściwości preferencji (plist) w celu skonfigurowania aplikacji macOS i urządzenia. Nie wszystkie aplikacje obsługują preferencje zarządzane, a w niektórych przypadkach można zarządzać tylko określonymi ustawieniami. Ustawienia są wdrażane tylko za pośrednictwem kanału urządzenia. Należy przekazać tylko pliki listy właściwości lub pliki XML, które są przeznaczone dla ustawień kanału urządzenia.

### <a name="assignment-type-value-in-windows-company-portal----5459950----"></a>Wartość typu przypisania w systemie Windows Portal firmy <!-- 5459950  -->
Strona **zainstalowane aplikacje** w aplikacji Portal firmy systemu Windows zostanie zaktualizowana. Kolumna **Typ przypisania** na stronie **zainstalowane aplikacje** została zaktualizowana o nazwę wymaganą przez organizację. Możliwe wartości to **tak** lub **nie** , aby wyznaczyć wymagane aplikacje a. Ta zmiana jest wprowadzana w odpowiedzi na pewne pomyłki użytkowników końcowych. Aby uzyskać więcej informacji na temat konfigurowania Portalu firmy dla systemu Windows, zobacz [Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune](~/apps/company-portal-app.md).

### <a name="run-win32-apps-on-windows-10-s-mode-devices----3747604----"></a>Uruchamianie aplikacji Win32 na urządzeniach z systemem Windows 10 w trybie S <!-- 3747604  --> 
Będzie można instalować i uruchamiać aplikacje Win32 na urządzeniach zarządzanych w trybie systemu Windows 10 S. Utwórz co najmniej jedną uzupełniającą zasadę dla trybu S przy użyciu narzędzi programu PowerShell Windows Defender Application Control (WDAC). Użyj portalu podpisywania funkcji Device Guard, aby podpisywać dodatkowe zasady. Następnie Przekaż i Rozpowszechnij zasady za pomocą usługi Intune. 

W usłudze Intune znajdziesz tę możliwość, wybierając pozycję **aplikacje klienckie**  > **zasady uzupełniania systemu Windows 10 S**. 

### <a name="set-app-availability-based-on-a-date-and-time----3510685----"></a>Ustawianie dostępności aplikacji na podstawie daty i godziny <!-- 3510685  -->
Jako administrator możesz skonfigurować godzinę rozpoczęcia i termin ostateczny dla wymaganej aplikacji. Po uruchomieniu rozszerzenie zarządzania usługi Intune pobierze zawartość aplikacji i przeprowadzi ją w pamięci podręcznej. Aplikacja zostanie zainstalowana w ostatecznym terminie. W przypadku dostępnych aplikacji czas rozpoczęcia będzie określać, kiedy aplikacja jest widoczna w Portal firmy. 

Aby ustawić dostępność aplikacji na podstawie daty i godziny:

1. W usłudze Intune wybierz pozycję **Aplikacje klienckie** > **Aplikacje**. 
1. Wybierz aplikację z listy lub Dodaj nową, wybierając pozycję **Dodaj**. 
1. W bloku aplikacja wybierz pozycję **przypisania** > **Dodaj grupę**. 
1. Ustaw **Typ przypisania** na **Wymagane** a następnie wybierz pozycję **uwzględnione grupy**. 
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

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Skonfiguruj zawartość powiadomienia aplikacji dla kont organizacji <!-- 2576686 -->
Aplikacja usługi Intune na urządzeniach z systemem Android i iOS umożliwi kontrolowanie zawartości powiadomień aplikacji dla kont organizacji. Ta funkcja będzie wymagała obsługi aplikacji i może być niedostępna dla wszystkich aplikacji korzystających z aplikacji. Aby uzyskać więcej informacji na temat zasad ochrony aplikacji (APP), zobacz [Co to są zasady ochrony aplikacji?](../apps/app-protection-policy.md)


<!-- ***********************************************-->
## <a name="device-configuration"></a>Konfiguracja urządzenia

### <a name="use-pkcs-certificates-with-wi-fi-profiles-on-windows-10-and-later-devices----3246388----"></a>Używanie certyfikatów PKCS z profilami sieci Wi-Fi na urządzeniach z systemem Windows 10 i nowszym <!-- 3246388  -->
Obecnie można uwierzytelniać profile sieci Wi-Fi systemu Windows przy użyciu certyfikatów protokołu SCEP (**Konfiguracja urządzenia** > **Profile** > **tworzenia profilu** > **Windows 10 i nowszych** dla platformy > **Wi-Fi** dla Typ profilu > typ > **protokołu EAP** **przedsiębiorstwa** ). Będziesz mieć możliwość używania certyfikatów PKCS z profilami sieci Wi-Fi systemu Windows. Ta funkcja umożliwia użytkownikom uwierzytelnianie profilów sieci Wi-Fi przy użyciu nowych lub istniejących profilów certyfikatów PKCS w dzierżawie. 

Aby uzyskać więcej informacji o profilach sieci Wi-Fi, zobacz [Dodawanie ustawień Wi-Fi dla urządzeń z systemem Windows 10 lub nowszym w usłudze Intune](../configuration/wi-fi-settings-windows.md).

Dotyczy:
- System Windows 10 lub nowszy

### <a name="new-exchangeactivesync-settings-when-creating-an-email-device-configuration-profile-on-ios-devices----4892824----"></a>Nowe ustawienia ExchangeActiveSync podczas tworzenia profilu konfiguracji urządzenia poczty E-mail na urządzeniach z systemem iOS <!-- 4892824  --> 
Na urządzeniach z systemem iOS/iPadOS można skonfigurować łączność poczty e-mail w profilu konfiguracji urządzenia (**Konfiguracja urządzenia** > **Profile** > **tworzenia profilu** > **iOS/iPadOS** dla platformy > **poczty e-mail** dla typu profilu). 

Dostępne będą nowe ustawienia ExchangeActiveSync, w tym:
- Wybierz usługi, które mają zostać zsynchronizowane (lub Zablokuj synchronizację), takie jak poczta e-mail, kalendarz i kontakty.
- Zezwalaj (lub Blokuj) użytkownikom na zmienianie ustawień synchronizacji dla tych usług na ich urządzeniach. 

Aby wyświetlić bieżące ustawienia, przejdź do [ustawień profilu poczty e-mail dla urządzeń z systemem iOS w usłudze Intune](../configuration/email-settings-ios.md).

Dotyczy:
- System iOS 13.0 i nowsze
- System iPadOS 13.0 i nowsze

### <a name="prevent-users-from-adding-personal-google-accounts-to-android-enterprise-device-owner-and-dedicated-devices----5353228----"></a>Uniemożliwiaj użytkownikom dodawanie osobistych kont Google do właściciela urządzenia z systemem Android Enterprise i urządzeń dedykowanych <!-- 5353228  -->
Będziesz mieć możliwość uniemożliwienia użytkownikom tworzenia osobistych kont Google na właścicielu urządzenia i dedykowanych urządzeniach z systemem Android (**Konfiguracja urządzeń** > **Profile** > **tworzenia profilu** > systemie **Android Enterprise** dla > **właściciel urządzenia tylko > ograniczenia dotyczące urządzeń** dla typu profilu > **Ustawienia użytkowników i kont**).

Aby wyświetlić bieżące ustawienia, które można skonfigurować, zobacz [Ustawienia urządzeń z systemem Android Enterprise w celu zezwolenia na funkcje lub ich ograniczenia przy użyciu usługi Intune](../configuration/device-restrictions-android-for-work.md).

Dotyczy:
- Właściciel urządzenia z systemem Android Enterprise
- Dedykowane urządzenia z rozwiązaniem Android Enterprise

### <a name="server-side-logging-for-siri-commands-setting-is-removed-in-ios-device-restrictions-profile----5468501----"></a>Funkcja rejestrowania po stronie serwera dla poleceń Siri jest usuwana w profilu ograniczeń urządzenia z systemem iOS <!-- 5468501  -->
Na urządzeniach z systemem iOS można utworzyć profile ograniczeń dla urządzeń, które konfigurują rejestrowanie po stronie serwera dla poleceń Siri (**Konfiguracja urządzenia** > **Profile** > **tworzenia profilu** > **iOS/iPadOS** dla platformy **Ograniczenia > urządzeń** dla typu profilu > **aplikacje wbudowane**). Ustawienie **Siri polecenia rejestrowania po stronie serwera** zostanie usunięte.

To ustawienie zostanie usunięte z konsoli administracyjnej usługi Intune. To ustawienie nie ma wpływu na urządzenie, mimo że istniejące zasady, które mają skonfigurowane to ustawienie, będą nadal wyświetlać ustawienie. Jeśli chcesz usunąć ustawienie z istniejących zasad, przejdź do zasad, wprowadź drobną edycję, Zapisz ją i zasady zostaną zaktualizowane.

Aby wyświetlić ustawienia, które można skonfigurować, zobacz [Ustawienia urządzeń z systemem iOS i iPadOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](../configuration/device-restrictions-ios.md).

Dotyczy:
- iOS


<!-- ***********************************************-->
<!--## Device enrollment-->

<!-- ***********************************************-->
## <a name="device-management"></a>Zarządzanie urządzeniami

### <a name="edit-device-name-value-for-autopilot-devices---2640074----"></a>Edytuj wartość nazwy urządzenia dla urządzeń z autopilotażem<!-- 2640074  -->
Będziesz w stanie edytować wartość nazwy urządzenia dla urządzeń z urządzeniami niewidocznymi w usłudze Azure AD. W tym celu przejdź do usługi **Intune** > **rejestracja urządzeń** > **rejestracja w systemie Windows** >  > **urządzeń** z **systemem Windows autopilotaż** > Wybierz urządzenie > zmienić wartość **nazwy urządzenia** w prawym okienku > **Zapisz**.


### <a name="edit-the-group-tag-value-for-autopilot-devices---4816775---"></a>Edytuj wartość tagu grupy dla urządzeń z autopilotażem<!-- 4816775 -->
Będziesz w stanie edytować wartość **tagu grupy** dla urządzeń z autopilotażem:

1. Wybierz pozycję Usługa **Intune**  > **rejestracja urządzeń**  > **rejestracja w systemie Windows**  >   > **urządzeń**z**systemem Windows** .
1. Wybierz urządzenie.
1. W okienku po prawej stronie Zmień wartość **tagu grupy** .
1. Wybierz pozycję **Zapisz**.

### <a name="target-macos-user-groups-to-require-jamf-management----4061739---"></a>Docelowa Grupa użytkowników macOS do wymagania zarządzania Jamf <!-- 4061739 -->
Będziesz mieć możliwość nawiązywania określonych grup użytkowników, aby wymagały zarządzania urządzeniami macOS przez Jamf. Ten element docelowy umożliwi zastosowanie integracji zgodności Jamf z podzbiorem urządzeń macOS, podczas gdy inne urządzenia będą nadal zarządzane przez usługę Intune. Określanie wartości docelowej umożliwia również stopniowe Migrowanie urządzeń użytkowników z jednego systemu zarządzania urządzeniami przenośnymi do drugiego.

<!-- ***********************************************-->
## <a name="intune-apps"></a>Aplikacje usługi Intune

### <a name="improved-macos-enrollment-experience-in-company-portal----5074349----"></a>Ulepszona obsługa rejestracji macOS w Portal firmy <!-- 5074349  -->
Portal firmy dla środowiska rejestracji macOS będzie prostszy proces rejestracji, który będzie bardziej ściśle dopasowywany do Portal firmy środowiska rejestracji systemu iOS. Użytkownicy urządzeń będą widzieli następujące:  

* Elegancki interfejs użytkownika.  
* Ulepszona Lista kontrolna rejestracji.  
* Wyraźniejsze instrukcje dotyczące rejestrowania urządzeń.  
* Udoskonalone opcje rozwiązywania problemów.  

### <a name="improved-checklist-design-in-company-portal-app-for-android---5550857----"></a>Ulepszony projekt listy kontrolnej w aplikacji Portal firmy dla systemu Android<!-- 5550857  -->
Lista kontrolna konfiguracji w aplikacji Portal firmy dla systemu Android zostanie zaktualizowana o lekkie projektowanie i nowe ikony. Zmiany zostaną wyrównane wraz z najnowszymi aktualizacjami wprowadzonymi do aplikacji Portal firmy dla systemu iOS.

<!-- ***********************************************-->
## <a name="monitoring-and-troubleshooting"></a>Monitorowanie i rozwiązywanie problemów

### <a name="updated-support-experience-------5012398------"></a>Zaktualizowane środowisko pomocy technicznej   <!--  5012398    -->
W ramach dalszych ulepszeń będziemy aktualizować środowisko pomocy technicznej w konsoli usługi Intune.  Zajmiemy się wyszukiwaniem w konsoli i opiniami dotyczącymi typowych problemów. usprawniamy przepływ pracy, aby skontaktować się z pomocą techniczną.     

<!-- ***********************************************-->
## <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach

### <a name="duplicate-custom-or-built-in-roles----1081938---"></a>Zduplikowane role niestandardowe lub wbudowane <!-- 1081938 -->
Będziesz mieć możliwość kopiowania ról wbudowanych i niestandardowych. W tym celu przejdź do **ról** > usługi **Intune** > **wszystkie role** > wybierz rolę z listy > **Duplikuj**. Upewnij się, że wprowadzono nową nazwę, która jest unikatowa.

<!-- ***********************************************-->

## <a name="security"></a>Zabezpieczenia

### <a name="bitlocker-key-rotation--------2564951--------"></a>Rotacja kluczy funkcji BitLocker     <!-- 2564951      -->
Za pomocą usługi Intune można obrócić klucze odzyskiwania funkcji BitLocker dla zarządzanych urządzeń z systemem Windows w wersji 1909 lub nowszej. 

<!-- ***********************************************-->
## <a name="notices"></a>Uwagi

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).
