---
title: W trakcie opracowywania — Microsoft Intune
titleSuffix: ''
description: Funkcje programu Microsoft Intune w trakcie opracowywania
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
# <a name="in-development-for-microsoft-intune---april-2019"></a>Podczas tworzenia usługi Microsoft Intune — kwiecień 2019 r

Aby pomóc w swojej gotowości i planowania, ta strona listy aktualizacji interfejsu użytkownika usługi Intune i funkcje są w fazie projektowania, ale nie została jeszcze ogólnie. Ponadto:

- Przewidujemy, należy podjąć działania przed zmianą, opublikujemy dodatkowe wpis w Centrum wiadomości usługi Office.
- Gdy funkcja jest uruchamiana w środowisku produkcyjnym, albo w wersji zapoznawczej lub ogólnie dostępna, opis funkcji przeniesie wyłączone na tej stronie i na [co to jest nowa strona](whats-new.md).
- Na tej stronie i [co to jest nowa strona](whats-new.md) są okresowo aktualizowane. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.
- Zapoznaj się [plan M365](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) strategiczne cele do zrealizowania i osi czasu.

> [!Note]
> Te elementy odzwierciedlają bieżących oczekiwań firmy Microsoft o możliwościach usługi Intune zostaną dodane w przyszłych wydaniach. Daty i poszczególne funkcje mogą ulec zmianie. Nie wszystkie elementy w rozwoju ma opis funkcji na tej stronie.

**Kanał informacyjny RSS**: otrzymuj powiadomienie, gdy ta strona zostanie zaktualizowana przez skopiowanie i wklejenie następującego adresu URL w czytniku kanałów informacyjnych: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Usługa Intune w witrynie Azure Portal

<!-- 1904 start-->

### <a name="set-login-settings-and-control-restart-options-on-macos-devices----1210083---"></a>Określanie ustawień logowania i kontroli ponowne uruchamianie urządzeń z systemem macOS <!-- 1210083 -->
Na urządzeniach z systemem macOS można utworzyć profil konfiguracji urządzeń (**konfiguracji urządzenia** > **profile** > **Utwórz profil** > Wybierz **macOS** platformy > **funkcje urządzenia** dla typu profilu). Nowe ustawienia okno logowania będzie obejmują elementy, takie jak wyświetlanie transparentu niestandardowe, wybierz, jak użytkownicy zalogować, Pokaż lub Ukryj ustawienia zasilania i inne.

Aby wyświetlić bieżące ustawienia, przejdź do [ustawień funkcji urządzenia z systemem macOS](macos-device-features-settings.md).

Dotyczy: system macOS

### <a name="advanced-settings-for-windows-defender-firewall----1311949---"></a>Zaawansowane ustawienia zapory Windows Defender <!-- 1311949 -->
Wkrótce będzie można zarządzać niestandardowych reguł zapory na komputerach klienckich programu Windows Defender za pomocą usługi Intune. Reguły można określić zachowanie dla ruchu przychodzącego i wychodzącego do aplikacji, adresów sieciowych i portów. 

### <a name="require-app-protection-conditional-access----1634317---"></a>Wymagają dostępu warunkowego ochrony aplikacji  <!--1634317 -->
Będzie można użyć *zasad ochrony aplikacji zarządzania wymagają*, potwierdzenie zasad jest stosowany do aplikacji przez użytkownika przed ukończeniem logowania, aby uniemożliwić użytkownikom uzyskiwanie dostępu do danych, możesz chronić przy użyciu dostępu warunkowego. Podczas gdy zasady assurance może spowolnić pierwsze doświadczenie użycia, pomaga chronić przed problemy z siecią, administracyjne błędów konfiguracji lub zamierzone działań mających na celu utrudniają zasad ochrony aplikacji. 

### <a name="retire-noncompliant-devices----1827291---"></a>Wycofywanie urządzeń niezgodnych <!-- 1827291 -->
Zamierzamy dodać nową akcję zgodności wycofywania urządzenia niezgodne. Wycofywanie niezgodne urządzenia powoduje usunięcie wszystkich danych firmowych z niego, a następnie spowoduje również usunięcie urządzenia z zarządzania przez usługę Intune. Ta akcja jest uruchamiany, gdy wartość skonfigurowana w dniach zostanie osiągnięty. Wartość minimalna to 30 dni. 

### <a name="configure-settings-for-kernel-extensions-on-macos-devices----2043024---"></a>Konfigurowanie ustawień rozszerzenia jądra dla urządzeń z systemem macOS <!-- 2043024 -->
Na urządzeniach z systemem macOS można utworzyć profil konfiguracji urządzeń (**konfiguracji urządzenia** > **profile** > **Utwórz profil** > Wybierz **macOS** platformy). Nową grupę ustawień umożliwi Konfigurowanie i używanie rozszerzeń jądra na swoich urządzeniach.

Dotyczy: macOS 10.13.2 i nowsze

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470---"></a>Konfigurowanie profilu pod kątem pominięcia niektórych ekranów asystenta ustawień <!-- 2276470 -->
Podczas tworzenia profilu rejestracji systemu macOS będzie można skonfigurować go tak, aby pominąć dowolny z następujących ekranów, gdy użytkownik będzie korzystać z asystenta ustawień:
- Migracja systemu Android
- Wyświetlanie sygnału
- Ochrona prywatności
- iCloudStorage Jeśli tworzysz nowy profil lub edytujesz profil, wybrane pomijane ekrany muszą być synchronizowane z serwerem MDM firmy Apple. Użytkownicy mogą wydać ręczną synchronizację urządzeń, aby nie było ma żadnego opóźnienia podczas pobierania zmian profilu.
Aby uzyskać więcej informacji, zobacz [Automatically enroll macOS devices with the Device Enrollment Program or Apple School Manager](device-enrollment-program-enroll-macos.md) (Automatyczne rejestrowanie urządzeń z systemem macOS w ramach programu Device Enrollment Program lub usługi Apple School Manager).

### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Urządzenia, użytkownicy mogą wyświetlać wszystkie aplikacje zarządzane są już zainstalowane lub wykonały próby instalacji <!-- 2352913 -->
Portal firmy dla Windows spowoduje wyświetlenie listy wszystkich zarządzanych aplikacji&ndash; wymagana i dostępna&ndash; są instalowane na urządzeniu użytkownika. Użytkownicy będą mogli, do widoku podjęto próbę i oczekujące instalacje aplikacji oraz ich bieżący stan. Jeśli Twoja organizacja nie twórz aplikacje, wymagane, czy dostępne, użytkownicy zobaczą komunikat wyjaśniający, czy zostały zainstalowane nie aplikacje firmowe. Użytkownicy będą również mogli sortowania lub filtrowania swoje aplikacje, stan instalacji.

### <a name="scope-tags-for-apple-vpp-tokens---2371886---"></a>Tagi zakresu tokenów programu VPP firmy Apple <!--2371886 -->
Będzie można dodawać tagi zakresu do tokenów programu VPP firmy Apple. Tylko użytkownicy są przypisywane przy użyciu tego samego tagu zakresu mają dostęp do tokenu VPP firmy Apple z tym tagiem. Aplikacje programu VPP i książki elektroniczne zakupić przy użyciu tokenu dziedziczą jego tagi zakresu. Aby uzyskać więcej informacji na temat tagi zakresu zobacz [tagi RBAC użycia i zakres](scope-tags.md).

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Użyj "zasady stosowania" podczas tworzenia profilów konfiguracji urządzeń z systemem Windows 10 <!-- 2549910 -->
Tworzenie profilów konfiguracji urządzeń z systemem Windows 10 (**konfiguracji urządzenia** > **profile** > **Utwórz profil**  >  **Systemu Windows 10** platformy). Będziesz mieć możliwość tworzenia **reguły stosowania** tak profil, który ma zastosowanie tylko do określonej wersji lub określonej wersji. Na przykład możesz utworzyć profil, który umożliwia pewne ustawienia funkcji BitLocker. Po dodaniu profilu, użycie reguły stosowania, więc profil, który ma zastosowanie tylko do urządzeń z systemem Windows 10 Enterprise.

Dotyczy: 
- System Windows 10 lub nowszy

### <a name="enable-win32-app-dependencies----2617348---"></a>Włącz zależności aplikacji systemu Win32 <!-- 2617348 -->
Publiczna wersja zapoznawcza — jako administrator możesz będziesz mieć możliwość wymagają, że inne aplikacje są instalowane jako zależności, przed zainstalowaniem aplikacji Win32. W szczególności urządzenia należy zainstalować aplikacje zależne, przed instalacją aplikacji Win32. Ta funkcja będzie dostępna tylko wtedy, gdy agent zarządzania usługi Intune został uaktualniony do wersji 1904 (większe niż 1.18.120.0), która może potrwać 1 lub 2 tygodnie dodatkowe po uaktualnieniu usługi na 1904. W usłudze Intune, wybierz **aplikacje klienckie** > **aplikacje** > **Dodaj** do wyświetlenia **Dodaj aplikację** bloku. Wybierz **aplikacji Windows (Win32)** jako **typ aplikacji**. Aby uzyskać więcej informacji, zobacz [autonomicznej usługi Intune — Zarządzanie aplikacjami Win32](apps-win32-app-management.md).

### <a name="new-device-restriction-setting-for-android-enterprise-device-owner-let-users-connect-to-wi-fi-networks-on-android-enterprise-dedicated-devices-running-multi-app-kiosk-mode---3041940---"></a>Nowe ustawienia ograniczeń urządzenia dla przedsiębiorstwa z systemem Android, właściciel urządzenia: zezwolić użytkownikom na łączenie się z sieciami Wi-Fi na urządzeniach przedsiębiorstwa z systemem Android w wersji dedykowanej z trybu kiosku z wieloma aplikacjami <!--3041940 -->
Administratorzy będą mogli przełączyć nowe ustawienie, która umożliwia użytkownikom konfigurować funkcję Bluetooth na urządzeniach przedsiębiorstwa z systemem Android w wersji dedykowanej, uruchomiony w trybie kiosku z wieloma aplikacjami. Aby wyświetlić tego ustawienia w konsoli usługi Intune, wybierz **Intune** > **konfiguracji urządzenia** > **profile**  >  **Utwórz profil** > Wybierz **przedsiębiorstwa z systemem Android** platformy > **tylko właściciel urządzenia, ograniczeń dotyczących urządzeń** dla typu profilu > **ustawienia**   >  **Urządzenia dedykowane** > Wybierz **wieloma aplikacjami** z **trybu kiosku** ustawienie listy rozwijanej. Opcja o nazwie **konfiguracji sieci Wi-Fi** będą dostępne, aby umożliwić. 

Dotyczy: urządzeń z systemem trybu kiosku z wieloma aplikacjami przedsiębiorstwa z systemem Android w wersji dedykowanej. 

### <a name="new-device-restriction-setting-for-android-enterprise-device-owner-let-users-configure-bluetooth-and-pairing-on-android-enterprise-dedicated-devices---3041941---"></a>Nowe ustawienia ograniczeń urządzenia dla przedsiębiorstwa z systemem Android, właściciel urządzenia: zezwalać użytkownikom na konfigurowanie Bluetooth i Dobieranie w pary na urządzeniach przedsiębiorstwa z systemem Android w wersji dedykowanej <!--3041941 -->
Administratorzy będą mogli przełączyć nowe ustawienie, która umożliwia użytkownikom konfigurować funkcję Bluetooth na urządzeniach przedsiębiorstwa z systemem Android w wersji dedykowanej, uruchomiony w trybie kiosku z wieloma aplikacjami. Aby wyświetlić tego ustawienia w konsoli usługi Intune, wybierz **Intune** > **konfiguracji urządzenia** > **profile**  >  **Utwórz profil** > Wybierz **przedsiębiorstwa z systemem Android** platformy > **tylko właściciel urządzenia, ograniczeń dotyczących urządzeń** dla typu profilu > **ustawienia**   >  **Urządzenia dedykowane** > Wybierz **wieloma aplikacjami** z **trybu kiosku** ustawienie listy rozwijanej. Opcja o nazwie **konfiguracji Bluetooth** będą dostępne, aby umożliwić. 

Dotyczy: urządzeń z systemem trybu kiosku z wieloma aplikacjami przedsiębiorstwa z systemem Android w wersji dedykowanej. 

### <a name="monitor-security-baseline-status-public-preview----3082047---"></a>Monitorowanie stanu linii bazowej zabezpieczeń (publiczna wersja zapoznawcza) <!-- 3082047 --> 
Podczas monitorowania *stan urządzenia* dla swojej wartości bazowych zabezpieczeń widoku zorganizuje stan według kategorii linii bazowej, takie jak *blokadzie*, *funkcji BitLocker*i  *Przeglądarka*. Wszystkie kategorie z bazowego dostępne będzie reprezentowany. Dla każdej kategorii zobaczysz, ile urządzeń nie są zgodne z kategorią określonej linii bazowej, są niepoprawnie skonfigurowane lub nie mają zastosowania.

###  <a name="intune-security-tasks-for-defender-atp-in-public-preview----3208597---"></a>Zadania zabezpieczeń usługi Intune dla Defender ATP (w publicznej wersji zapoznawczej) <!-- 3208597 -->
Dostępne w publicznej wersji zapoznawczej, usługa Intune wkrótce doda zadań związanych z zabezpieczeniami dla nowo ogłoszone Zarządzanie luk w zabezpieczeniach i zagrożeń Defender firmy Microsoft.  Dzięki tej integracji Administratorzy operacji zabezpieczeń w systemie Windows Defender ATP Windows Defender (WDATP) bardziej efektywne może komunikować się zalecane korygowania funkcję dla pojawiających się zagrożeń dla administratorów usługi Intune. Dodawanie zadań zabezpieczeń dodaje opartych na ryzykach sposobem odnajdywanie, kategoryzowania i korygowanie luk w zabezpieczeniach punktu końcowego i błędów konfiguracji.

Aby dowiedzieć się więcej o zadaniach zabezpieczeń w usłudze Intune, zobacz wpis w blogu dotyczący [rozszerzenie Microsoft Defender ATP zagrożeń i zarządzanie lukami w zabezpieczeniach przy użyciu zadań zabezpieczeń w usłudze Intune](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Microsoft-Intune-security-tasks-extend-Microsoft-Defender-ATP-s/ba-p/369857). 

### <a name="create-and-use-oemconfig-device-configuration-profiles-in-intune----3305883---"></a>Tworzenie i używanie profilów konfiguracji urządzeń OEMConfig w usłudze Intune <!-- 3305883 -->
Usługa Intune będzie obsługiwać konfigurowanie urządzeniami przedsiębiorstwa z systemem Android za pomocą OEMConfig. W szczególności można utworzyć profil konfiguracji urządzenia i Zastosuj ustawienia do urządzeń przedsiębiorstwa z systemem Android przy użyciu OEMConfig (**konfiguracji urządzenia** > **profile**  >  **Utwórz profil** > **przedsiębiorstwa z systemem Android** platformy).

Pomoc dla producentów OEM jest obecnie na zasadzie na OEM. Jeśli aplikacja OEMConfig nie jest dostępna na liście aplikacji OEMConfig, skontaktuj się z `IntuneOEMConfig@microsoft.com`.

Dotyczy: 
- Android Enterprise

### <a name="new-device-restriction-settings-for-android-enterprise-device-owner----3574254---"></a>Nowe ustawienia ograniczeń urządzeń dla programu Android Enterprise, właściciel urządzenia <!-- 3574254 -->
Na urządzeniach z systemami przedsiębiorstwa z systemem Android można utworzyć profil ograniczenia dotyczącego urządzeń, aby ograniczyć funkcje, ustaw reguły hasła i inne (**konfiguracji urządzenia** > **profile**  >  **Utwórz profil** > Wybierz **przedsiębiorstwa z systemem Android** platformy > **tylko właściciel urządzenia > ograniczenia dotyczące urządzeń** dla typu profilu). 

Nowe ustawienia, w tym ustawienia hasła, umożliwiając pełny dostęp do aplikacji w Google Play Store dla w pełni zarządzanych urządzeń, a więcej będą dostępne. 

Aby wyświetlić aktualną listę ustawień, zobacz [Ustawienia urządzeń z systemem Android Enterprise w celu zezwolenia na funkcje lub ich ograniczenia](device-restrictions-android-for-work.md). 

Dotyczy: system android dla firm w pełni zarządzane urządzenia

### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>Sprawdź, czy mikroukład modułu TPM, w zasadach zgodności urządzenia systemu Windows 10 <!-- 3617671 -->
Wiele systemów Windows 10 i nowszym mają mikroukładami Trusted Platform Module (TPM). Nowym ustawieniem zgodności sprawdzi, czy modułu TPM na urządzeniu.

[Windows 10 i nowszych ustawienia zasad zgodności](compliance-policy-create-windows.md) Wyświetla listę bieżących ustawień.

Dotyczy: 
- System Windows 10 lub nowszy

### <a name="configure-your-win32-apps-to-be-installed-on-intune-enrolled-azure-ad-joined-devices----3695227---"></a>Konfigurowanie aplikacji Win32, należy zainstalować na zarejestrowane w usłudze Intune urządzeń przyłączonych do usługi Azure AD <!-- 3695227 -->
Będziesz mieć możliwość urządzeń przyłączonych do przypisania, można zainstalować w usłudze Intune w używanych aplikacjach Win32 zarejestrowane w usłudze Azure AD. Aby uzyskać więcej informacji o aplikacjach Win32 w usłudze Intune, zobacz [Zarządzanie aplikacjami Win32](apps-win32-app-management.md).

### <a name="windows-defender-advanced-threat-protection-baseline----3754134---"></a>Punkt odniesienia dla zaawansowanej ochrony przed zagrożeniami w usłudze Windows Defender <!-- 3754134 -->
Zamierzamy dodać nową linię bazową, aby pomóc Ci w skonfigurowaniu ustawień zaawansowanej ochrony przed zagrożeniami programu Windows Defender.

### <a name="device-overview-shows-primary-user---794259---"></a>Przegląd urządzenia są widoczne dla użytkownika podstawowego <!--794259 -->
Na stronie Przegląd urządzenia będą widoczne dla użytkownika podstawowego, nazywany również użytkowników koligację urządzenia użytkownika (UDA). Aby wyświetlić głównego użytkownika dla urządzenia, wybierz **Intune** > **urządzeń** > **urządzeniom** > Wybierz urządzenie. Podstawowy użytkownik pojawi się w górnej części **Przegląd** strony.

### <a name="expanded-support-for-android-enterprise-fully-managed-devices----3903241-3903244-3903246---"></a>Rozszerzonej pomocy technicznej dla przedsiębiorstwa z systemem Android w pełni zarządzane urządzenia <!-- 3903241, 3903244, 3903246 -->
Będziemy rozszerzać obsługę urządzeń i w pełni zarządzana przedsiębiorstwa z systemem Android ([po raz pierwszy w styczniu 2019](whats-new.md#week-of-january-14-2019) do obejmują następujące elementy:
- Zgodność
- Dostęp warunkowy
- Nowy użytkownik końcowy aplikacji

W celu skonfigurowania w pełni zarządzanych urządzeń z systemem Android przejdź kolejno do pozycji **Rejestrowanie urządzenia** > **Rejestracja w systemie Android** > **Firmowe, w pełni zarządzane urządzenia użytkowników**. Obsługa nadal w pełni zarządzane urządzenia z systemem Android w wersji zapoznawczej, a niektóre funkcje usługi Intune może nie być w pełni funkcjonalne. 

### <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices----4105925---"></a>Dodatkowe zarządzany sklep Google Play aplikację, raportowanie dla urządzenia z profilem służbowym przedsiębiorstwa z systemem Android <!-- 4105925 -->
Zarządzany sklep Google Play aplikacji wdrożone do urządzenia przedsiębiorstwa z systemem Android z profilem służbowym będzie można wyświetlić numer wersji określonej aplikacji zainstalowane na urządzeniu. Dotyczy to tylko wymagane aplikacje. Te same funkcje dla aplikacji dostępnych dla zostaną włączone w przyszłej wersji.

### <a name="ios-third-party-keyboards----4111843---"></a>Klawiatury innych firm dla systemu iOS <!-- 4111843 -->
Obsługa zasad ochrony aplikacji usługi Intune (aplikacja) dla **klawiatury firm** ustawienie zakończy się z powodu zmiany platformy iOS. Nie można skonfigurować tego ustawienia w konsoli administracyjnej usługi Intune i nie są wymuszane na kliencie w zestawie SDK aplikacji usługi Intune.

<!-- 1903 start-->

### <a name="block-users-from-scanning-for-windows-updates----3316758---"></a>Zablokuj użytkownikom możliwość skanowania w poszukiwaniu aktualizacji Windows <!-- 3316758 -->
Dodajemy nowe ustawienie do pierścienia aktualizacji Windows, który można użyć, aby uniemożliwić użytkownikom skanowanie pod kątem aktualizacji Windows. To ustawienie nie będzie dostępny z poziomu portalu, ale można skonfigurować przy użyciu interfejsu API programu Graph usługi Intune.

### <a name="windows-update-notifications----3316782---"></a>Powiadomienia o aktualizacji Windows <!-- 3316782 -->
Dodajemy obsługę konfiguracje pierścienia aktualizacji Windows, dzięki czemu będzie można skonfigurować powiadomienia Windows Update, które widzą użytkownicy. To ustawienie nie będzie dostępny z poziomu portalu, ale można skonfigurować przy użyciu interfejsu API programu Graph usługi Intune.

### <a name="easier-access-to-diagnostic-settings----3804627---"></a>Ułatwienia dostępu do ustawień diagnostycznych <!-- 3804627 -->
Dodajemy nową opcję **dzienniki inspekcji** bloku w każdym obciążeniu dziennika inspekcji, w konsoli usługi Intune, które można użyć, aby otworzyć bezpośrednio *ustawień diagnostycznych* strony.

## <a name="notices"></a>Uwagi

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).


