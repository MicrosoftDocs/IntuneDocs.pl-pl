---
title: W trakcie opracowywania — Microsoft Intune
titleSuffix: ''
description: Funkcje usługi Microsoft Intune w trakcie opracowywania
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/15/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: aa38a684a32756d4f2c3be3b750f8e79b66e98f6
ms.sourcegitcommit: 8c795b041cd39e3896595f64f53ace48be0ec84c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2019
ms.locfileid: "59587386"
---
# <a name="in-development-for-microsoft-intune---april-2019"></a>Funkcje usługi Microsoft Intune w trakcie opracowywania — kwiecień 2019 r.

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
 
## <a name="intune-in-the-azure-portal"></a>Usługa Intune w witrynie Azure Portal

<!-- 1904 start-->

### <a name="set-login-settings-and-control-restart-options-on-macos-devices----1210083---"></a>Określanie ustawień logowania i kontrolowanie opcji ponownego uruchamiania na urządzeniach z systemem macOS <!-- 1210083 -->
Na urządzeniach z systemem iOS można utworzyć profil konfiguracji urządzenia (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > wybierz **macOS** jako platformę > **Funkcje urządzenia** dla typu profilu). Nowe ustawienia okna logowania będą obejmowały między innymi wyświetlanie niestandardowego transparentu, wybór sposobu logowania użytkowników, czy pokazywanie lub ukrywanie ustawień zasilania.

Aby zapoznać się z bieżącymi ustawieniami, zobacz artykuł [Ustawienia funkcji urządzeń z systemem macOS](macos-device-features-settings.md).

Dotyczy: systemu macOS

### <a name="advanced-settings-for-windows-defender-firewall----1311949---"></a>Zaawansowane ustawienia zapory Windows Defender <!-- 1311949 -->
Wkrótce będzie można zarządzać niestandardowymi regułami zapory usługi Windows Defender na komputerach klienckich za pomocą usługi Intune. Reguły te mogą określać zachowanie dotyczące ruchu przychodzącego i wychodzącego na poziomie aplikacji, adresów sieciowych i portów. 

### <a name="require-app-protection-conditional-access----1634317---"></a>Wymaganie ochrony aplikacji za pomocą dostępu warunkowego  <!--1634317 -->
Będzie można korzystać z *zasady wymagania ochrony aplikacji*, sprawdzającej przed zakończeniem logowania, czy aplikacja użytkownika ma zastosowane zasady, co pozwoli zapobiec dostępowi użytkowników do danych chronionych za pomocą dostępu warunkowego. Choć weryfikacja zasad może spowolnić działanie przy pierwszym użyciu, zwiększa ochronę przed problemami z siecią, nieprawidłową konfiguracją administracyjną lub celowymi próbami obejścia zasad ochrony aplikacji. 

### <a name="retire-noncompliant-devices----1827291---"></a>Wycofywanie niezgodnych urządzeń <!-- 1827291 -->
Zostanie dodane nowe działanie zgodności, polegające na wycofaniu niezgodnego urządzenia. Wycofanie niezgodnego urządzenia spowoduje usunięcie z niego wszystkich danych firmowych, a następnie usunięcie urządzenia z listy urządzeń zarządzanych przez usługę Intune. Ta akcja będzie uruchamiana po osiągnięciu skonfigurowanej wartości w dniach. Wartość minimalna to 30 dni. 

### <a name="configure-settings-for-kernel-extensions-on-macos-devices----2043024---"></a>Konfigurowanie ustawień dotyczących rozszerzeń jądra na urządzeniach z systemem macOS <!-- 2043024 -->
Na urządzeniach z systemem iOS można utworzyć profil konfiguracji urządzenia (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > wybierz **macOS** jako platformę). Nowa grupa ustawień umożliwi konfigurowanie i używanie rozszerzeń jądra na urządzeniach.

Dotyczy: macOS 10.13.2 i nowsze

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470---"></a>Konfigurowanie profilu pod kątem pominięcia niektórych ekranów asystenta ustawień <!-- 2276470 -->
Podczas tworzenia profilu rejestracji systemu macOS będzie można skonfigurować go tak, aby pominąć dowolny z następujących ekranów, gdy użytkownik będzie korzystać z asystenta ustawień:
- Migracja systemu Android
- Wyświetlanie sygnału
- Ochrona prywatności
- iCloudStorage Jeśli tworzysz nowy profil lub edytujesz profil, wybrane pomijane ekrany muszą być synchronizowane z serwerem MDM firmy Apple. Użytkownicy mogą wydać ręczną synchronizację urządzeń, aby nie było ma żadnego opóźnienia podczas pobierania zmian profilu.
Aby uzyskać więcej informacji, zobacz [Automatically enroll macOS devices with the Device Enrollment Program or Apple School Manager](device-enrollment-program-enroll-macos.md) (Automatyczne rejestrowanie urządzeń z systemem macOS w ramach programu Device Enrollment Program lub usługi Apple School Manager).

### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Użytkownicy urządzeń mogą wyświetlać wszystkie zarządzane aplikacje, które zainstalowali lub próbowali zainstalować <!-- 2352913 -->
W aplikacji Portal firmy dla systemu Windows będzie dostępna lista wszystkich zarządzanych aplikacji (zarówno wymaganych, jak i dostępnych), które zainstalowano na urządzeniu użytkownika. Użytkownicy będą mogli wyświetlać aplikacje, które próbowano zainstalować lub które oczekują na instalację, wraz z bieżącym stanem. Jeśli organizacja nie określa aplikacji jako wymagane lub dostępne, użytkownicy zobaczą komunikat z informacją, że nie zainstalowano żadnych aplikacji firmowych. Użytkownicy będą również mogli sortować lub filtrować swoje aplikacje według stanu instalacji.

### <a name="scope-tags-for-apple-vpp-tokens---2371886---"></a>Tagi zakresu dla tokenów VPP firmy Apple <!--2371886 -->
Będzie można dodawać tagi zakresu do tokenów programu VPP firmy Apple. Tylko użytkownicy z przypisanym tym samym tagiem zakresu będą mieli dostęp do tokenu VPP firmy Apple z tym tagiem. Aplikacje programu VPP i książki elektroniczne zakupione przy użyciu tego tokenu dziedziczą jego tagi zakresu. Aby uzyskać więcej informacji na temat tagów zakresu, zobacz [Use RBAC and scope tags](scope-tags.md) (Używanie kontroli RBAC i tagów zakresu).

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Używanie „reguł stosowania” podczas tworzenia profili konfiguracji urządzeń z systemem Windows 10 <!-- 2549910 -->
Obecnie możesz tworzyć profile konfiguracji urządzeń z systemem Windows 10 (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > **Windows 10** jako platforma). W przyszłości będzie możliwe również tworzenie **reguł stosowania**, aby profil był stosowany tylko do określonej edycji lub wersji. Możesz na przykład utworzyć profil włączający określone ustawienia funkcji BitLocker. Gdy dodasz ten profil, reguła stosowania umożliwi zastosowanie go tylko do urządzeń z systemem Windows 10 Enterprise.

Dotyczy: 
- System Windows 10 lub nowszy

### <a name="enable-win32-app-dependencies----2617348---"></a>Włączanie zależności aplikacji Win32 <!-- 2617348 -->
Publiczna wersja zapoznawcza — Jako administrator będziesz mieć możliwość wymagania instalacji innych aplikacji jako zależności przed zainstalowaniem aplikacji Win32. W szczególności na urządzeniu muszą zostać zainstalowane aplikacje zależne przed zainstalowaniem aplikacji Win32. Ta funkcja będzie dostępna dopiero wtedy, gdy agent zarządzania usługi Intune zostanie uaktualniony do wersji 1904 (nowszej niż 1.18.120.0), co może nastąpić tydzień lub dwa tygodnie po uaktualnieniu usługi do wersji 1904. W usłudze Intune wybierz pozycję **Aplikacje klienckie** > **Aplikacje** > **Dodaj**, aby wyświetlić blok **Dodaj aplikację**. Wybierz pozycję **Aplikacja systemu Windows (Win32)** jako **typ aplikacji**. Aby uzyskać więcej informacji, zobacz [Autonomiczna usługa Intune — zarządzanie aplikacjami Win32](apps-win32-app-management.md).

### <a name="new-device-restriction-setting-for-android-enterprise-device-owner-let-users-connect-to-wi-fi-networks-on-android-enterprise-dedicated-devices-running-multi-app-kiosk-mode---3041940---"></a>Nowe ustawienie ograniczeń urządzenia z rozwiązaniem Android Enterprise w trybie Właściciel urządzenia: umożliwianie użytkownikom łączenia się z sieciami Wi-Fi na dedykowanych urządzeniach z rozwiązaniem Android Enterprise w trybie kiosku z wieloma aplikacjami <!--3041940 -->
Administratorzy będą mogli włączyć nowe ustawienie umożliwiające użytkownikom konfigurowanie połączeń Bluetooth na dedykowanych urządzeniach z rozwiązaniem Android Enterprise działających w trybie kiosku z wieloma aplikacjami. Aby zobaczyć to ustawienie w konsoli usługi Intune, wybierz kolejno pozycje **Intune** > **Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > platforma **Android Enterprise** > typ profilu **Tylko właściciel urządzenia, Ograniczenia urządzenia** > **Ustawienia** > **Dedykowane urządzenia**, a następnie wybierz pozycję **Wiele aplikacji** z listy rozwijanej ustawienia **Tryb kiosku**. Pojawi się wówczas dostępna do włączenia opcja o nazwie **Konfiguracja sieci Wi-Fi**. 

Dotyczy: dedykowanych urządzeń z rozwiązaniem Android Enterprise działających w trybie kiosku z wieloma aplikacjami. 

### <a name="new-device-restriction-setting-for-android-enterprise-device-owner-let-users-configure-bluetooth-and-pairing-on-android-enterprise-dedicated-devices---3041941---"></a>Nowe ustawienie ograniczeń urządzenia z rozwiązaniem Android Enterprise w trybie Właściciel urządzenia: umożliwianie użytkownikom konfigurowania połączeń Bluetooth i parowania na dedykowanych urządzeniach z rozwiązaniem Android Enterprise <!--3041941 -->
Administratorzy będą mogli włączyć nowe ustawienie umożliwiające użytkownikom konfigurowanie połączeń Bluetooth na dedykowanych urządzeniach z rozwiązaniem Android Enterprise działających w trybie kiosku z wieloma aplikacjami. Aby zobaczyć to ustawienie w konsoli usługi Intune, wybierz kolejno pozycje **Intune** > **Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > platforma **Android Enterprise** > typ profilu **Tylko właściciel urządzenia, Ograniczenia urządzenia** > **Ustawienia** > **Dedykowane urządzenia**, a następnie wybierz pozycję **Wiele aplikacji** z listy rozwijanej ustawienia **Tryb kiosku**. Pojawi się wówczas dostępna do włączenia opcja o nazwie **Konfiguracja połączenia Bluetooth**. 

Dotyczy: dedykowanych urządzeń z rozwiązaniem Android Enterprise działających w trybie kiosku z wieloma aplikacjami. 

### <a name="monitor-security-baseline-status-public-preview----3082047---"></a>Monitorowanie stanu punktów odniesienia zabezpieczeń (publiczna wersja zapoznawcza) <!-- 3082047 --> 
Podczas monitorowania wartości *Stan urządzenia* pod kątem punktów odniesienia zabezpieczeń ten widok uporządkuje stan według kategorii punktów odniesienia, takich jak *Dostęp przy włączonej blokadzie*, *BitLocker*, czy *Przeglądarka*. Przedstawione zostaną wszystkie dostępne kategorie punktów odniesienia. W każdej kategorii zobaczysz, ile urządzeń nie pasuje do określonego punktu odniesienia, ma nieprawidłową konfigurację lub nie ma zastosowania.

###  <a name="intune-security-tasks-for-defender-atp-in-public-preview----3208597---"></a>Zadania zabezpieczeń usługi Intune dotyczące zaawansowanej ochrony przed zagrożeniami usługi Defender (w publicznej wersji zapoznawczej) <!-- 3208597 -->
Wkrótce w usłudze Intune zostanie udostępniona publiczna wersja zapoznawcza zadań zabezpieczeń związanych z nowo przedstawioną funkcją zarządzania zagrożeniami i lukami w zabezpieczeniach usługi Microsoft Defender.  Dzięki tej integracji administratorzy zabezpieczeń zaawansowanej ochrony przed zagrożeniami w usłudze Windows Defender będą mogli bardziej efektywnie informować administratorów usługi Intune o zalecanych środkach zaradczych w odniesieniu do pojawiających się zagrożeń. Dodanie tych zadań zabezpieczeń umożliwia zastosowanie opartego na ryzyku podejścia do wykrywania, określania priorytetów i korygowania luk w zabezpieczeniach i błędów w konfiguracji punktów końcowych.

Aby dowiedzieć się więcej na temat zadań zabezpieczeń w usłudze Intune, zobacz wpis w blogu dotyczący [rozszerzania funkcji zarządzania zagrożeniami i lukami w zabezpieczeniach w ramach zaawansowanej ochrony przed zagrożeniami w usłudze Microsoft Defender za pomocą zadań zabezpieczeń w usłudze Intune](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Microsoft-Intune-security-tasks-extend-Microsoft-Defender-ATP-s/ba-p/369857). 

### <a name="create-and-use-oemconfig-device-configuration-profiles-in-intune----3305883---"></a>Tworzenie i używanie profilów konfiguracji urządzeń za pomocą aplikacji OEMConfig w usłudze Intune <!-- 3305883 -->
Usługa Intune będzie obsługiwać konfigurowanie urządzeń z rozwiązaniem Android Enterprise za pomocą aplikacji OEMConfig. Możesz utworzyć profil konfiguracji urządzenia i zastosować ustawienia do urządzeń z rozwiązaniem Android Enterprise przy użyciu aplikacji OEMConfig (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Android Enterprise** dla platformy).

Obsługa producentów OEM jest obecnie dostępna dla poszczególnych producentów OEM. Jeśli aplikacja OEMConfig nie jest dostępna na liście aplikacji OEMConfig, skontaktuj się z `IntuneOEMConfig@microsoft.com`.

Dotyczy: 
- Android Enterprise

### <a name="new-device-restriction-settings-for-android-enterprise-device-owner----3574254---"></a>Nowe ustawienia ograniczeń urządzeń dla rozwiązania Android Enterprise w trybie Właściciel urządzenia <!-- 3574254 -->
Na urządzeniach z rozwiązaniem Android Enterprise można utworzyć profil ograniczeń urządzenia, aby zezwolić na funkcje lub ograniczyć je, ustawić reguły haseł i nie tylko (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > wybierz **Android Enterprise** jako platformę > **Tylko właściciel urządzenia > Ograniczenia dotyczące urządzeń** dla typu profilu). 

Zostaną udostępnione nowe ustawienia, w tym między innymi ustawienia hasła oraz umożliwianie pełnego dostępu do aplikacji w sklepie Google Play w pełni zarządzanym urządzeniom. 

Aby wyświetlić aktualną listę ustawień, zobacz [Ustawienia urządzeń z systemem Android Enterprise w celu zezwolenia na funkcje lub ich ograniczenia](device-restrictions-android-for-work.md). 

Dotyczy: w pełni zarządzanych urządzeń z rozwiązaniem Android Enterprise

### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>Sprawdzanie mikroukładu modułu TPM w zasadach zgodności urządzeń z systemem Windows 10 <!-- 3617671 -->
Wiele urządzeń z systemem Windows 10 lub nowszym zawiera mikroukład modułu TPM (Trusted Platform Module). Nowe ustawienie zgodności umożliwi sprawdzenie, czy urządzenie ma moduł TPM.

Obecnie dostępne ustawienia są wymienione w artykule [Ustawienia zasad zgodności urządzeń z systemem Windows 10 lub nowszym](compliance-policy-create-windows.md).

Dotyczy: 
- System Windows 10 lub nowszy

### <a name="configure-your-win32-apps-to-be-installed-on-intune-enrolled-azure-ad-joined-devices----3695227---"></a>Konfigurowanie aplikacji Win32 pod kątem instalowania na urządzeniach dołączonych do usługi Azure AD zarejestrowanych w usłudze Intune <!-- 3695227 -->
Można będzie przypisać aplikacje Win32, które mają być instalowane na urządzeniach dołączonych do usługi Azure AD zarejestrowanych w usłudze Intune. Aby uzyskać więcej informacji o aplikacjach Win32 w usłudze Intune, zobacz [Zarządzanie aplikacjami Win32](apps-win32-app-management.md).

### <a name="windows-defender-advanced-threat-protection-baseline----3754134---"></a>Punkt odniesienia dla zaawansowanej ochrony przed zagrożeniami w usłudze Windows Defender <!-- 3754134 -->
Planujemy dodać nowy punkt odniesienia ułatwiający konfigurowanie ustawień zaawansowanej ochrony przed zagrożeniami w usłudze Windows Defender.

### <a name="device-overview-shows-primary-user---794259---"></a>Na stronie przeglądu urządzenia jest wyświetlany użytkownik podstawowy <!--794259 -->
Na stronie Przegląd urządzenia będzie wyświetlany użytkownik podstawowy, nazywany również użytkownikiem koligacji urządzenia użytkownika (UDA). Aby zobaczyć użytkownika podstawowego dla urządzenia, wybierz pozycję **Intune** > **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie. Użytkownik podstawowy będzie wyświetlany w górnej części strony **Przegląd**.

### <a name="expanded-support-for-android-enterprise-fully-managed-devices----3903241-3903244-3903246---"></a>Rozszerzona obsługa w pełni zarządzanych urządzeń z rozwiązaniem Android Enterprise <!-- 3903241, 3903244, 3903246 -->
Planujemy rozszerzyć obsługę w pełni zarządzanych urządzeń z rozwiązaniem Android Enterprise ([po raz pierwszy przedstawioną w styczniu 2019](whats-new.md#week-of-january-14-2019) w celu uwzględnienia następujących elementów:
- Zgodność
- Dostęp warunkowy
- Nowa aplikacja dla użytkowników końcowych

W celu skonfigurowania w pełni zarządzanych urządzeń z systemem Android przejdź kolejno do pozycji **Rejestrowanie urządzenia** > **Rejestracja w systemie Android** > **Firmowe, w pełni zarządzane urządzenia użytkowników**. Obsługa w pełni zarządzanych urządzeń z systemem Android pozostaje w wersji zapoznawczej i niektóre funkcje usługi Intune mogą nie być w pełni funkcjonalne. 

### <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices----4105925---"></a>Dodatkowe raportowanie aplikacji z zarządzanego sklepu Google Play dla urządzeń z profilem służbowym rozwiązania Android Enterprise <!-- 4105925 -->
W przypadku aplikacji z zarządzanego sklepu Google Play wdrożonych na urządzeniach z profilem służbowym rozwiązania Android Enterprise można będzie wyświetlić numer wersji aplikacji zainstalowanej na urządzeniu. Dotyczy to tylko wymaganych aplikacji. Ta sama funkcja dla dostępnych aplikacji zostanie włączona w przyszłej wersji.

### <a name="ios-third-party-keyboards----4111843---"></a>Klawiatury innych firm dla systemu iOS <!-- 4111843 -->
Obsługa zasad ochrony aplikacji usługi Intune dla ustawienia **Klawiatury innych firm** zostanie zakończona z powodu zmiany na platformie iOS. Nie będzie można skonfigurować tego ustawienia w konsoli administracyjnej usługi Intune i nie będzie ono wymuszane na kliencie w zestawie SDK aplikacji usługi Intune.

<!-- 1903 start-->

### <a name="block-users-from-scanning-for-windows-updates----3316758---"></a>Blokowanie użytkownikom możliwości skanowania w poszukiwaniu aktualizacji systemu Windows <!-- 3316758 -->
Dodajemy nowe ustawienie pierścienia aktualizacji systemu Windows, które umożliwi zablokowanie użytkownikom możliwości skanowania w poszukiwaniu aktualizacji systemu Windows. To ustawienie nie będzie dostępne w portalu, ale można je będzie skonfigurować za pomocą interfejsu API programu Graph w usłudze Intune.

### <a name="windows-update-notifications----3316782---"></a>Powiadomienia usługi Windows Update <!-- 3316782 -->
Dodajemy obsługę konfiguracji pierścienia usługi Windows Update, która umożliwi konfigurowanie powiadomień usługi Windows Update wyświetlanych użytkownikom. To ustawienie nie będzie dostępne w portalu, ale można je będzie skonfigurować za pomocą interfejsu API programu Graph w usłudze Intune.

### <a name="easier-access-to-diagnostic-settings----3804627---"></a>Ułatwienie dostępu do ustawień diagnostycznych <!-- 3804627 -->
Dodajemy nową opcję do bloku **Dzienniki inspekcji** w każdym obciążeniu Dziennik inspekcji w konsoli usługi Intune, która umożliwi bezpośrednie otwarcie strony *Ustawienia diagnostyczne*.

## <a name="notices"></a>Uwagi

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).


