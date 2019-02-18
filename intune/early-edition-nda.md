---
title: Wczesna wersja — Microsoft Intune
titlesuffix: ''
description: Wczesna wersja usługi Microsoft Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/04/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 19994745a232a362d6bba0f09ed3934e492a17ed
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55837258"
---
# <a name="the-early-edition-for-microsoft-intune---february-2019"></a>Wczesna wersja usługi Microsoft Intune — luty 2019

> [!Note]
> Powiadomienie NDA: Dla usługi Intune opracowywane są następujące zmiany. Te informacje są udostępniane pod rygorem umowy o zachowaniu poufności w bardzo ograniczonym zakresie. Nie wolno publikować żadnych tych informacji w mediach społecznościowych ani w publicznych witrynach internetowych, takich jak Twitter, UserVoice, Reddit itd. 

**Wczesna wersja** zawiera listę funkcji udostępnianych w ramach umowy o zachowaniu poufności, które zostaną wprowadzone w przyszłych wydaniach usługi Microsoft Intune. Te informacje są przekazywane w ograniczonym zakresie i mogą ulec zmianie. Nie publikuj tweetów, wpisów na platformie UserVoice ani w inny sposób nie udostępniaj tych informacji poza swoją firmą. Niektóre funkcje wymienione w tym miejscu mogą nie być wdrożone na czas i zostać opóźnione do przyszłych wersji. Inne funkcje są testowane w wersji pilotażowej, aby zapewnić przygotowanie ich do użytku przez klientów. W przypadku pytań lub wątpliwości skontaktuj się z osobą kontaktową ds. tej grupy produktów firmy Microsoft.

Ta strona jest okresowo aktualizowana. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Usługa Intune w witrynie Azure Portal
<!-- 1902 start-->

### <a name="powershell-scripts-can-run-in-a-64-bit-host-on-64-bit-devices----1862675----"></a>Skrypty programu PowerShell można uruchomić w ramach 64-bitowego hosta na urządzeniach 64-bitowych <!-- 1862675  -->
Po dodaniu skryptu programu PowerShell do profilu konfiguracji urządzenia skrypt jest zawsze wykonywany jako 32-bitowy nawet w 64-bitowych systemach operacyjnych. Dzięki tej aktualizacji administrator może uruchomić skrypt w ramach 64-bitowego hosta programu PowerShell na urządzeniach 64-bitowych (**Konfiguracja urządzenia** > **Skrypty PowerShell** > **Dodaj** > **Konfiguruj** > **Uruchom skrypt w 64-bitowym hoście programu PowerShell**).
Aby uzyskać więcej informacji na temat korzystania z programu PowerShell, zobacz [Skrypty programu PowerShell w usłudze Intune](intune-management-extension.md).
Dotyczy: System Windows 10 lub nowszy

### <a name="rename-an-enrolled-windows-device----1911112----"></a>Zmiana nazwy zarejestrowanego urządzenia z systemem Windows <!-- 1911112  -->
Będzie można zmienić nazwę zarejestrowanego urządzenia z systemem Windows 10 (RS4 lub nowszym). Aby to zrobić, wybierz pozycje **Intune** > **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Zmień nazwę urządzenia**.

### <a name="assign-scep-certificates-to-a-userless-macos-device-------2340521-----"></a>Przypisywanie certyfikatów SCEP do urządzenia z systemem macOS bez użytkowników    <!-- 2340521   -->
Będzie można przypisać certyfikaty prostego protokołu rejestrowania certyfikatów (SCEP) do urządzenia z systemem macOS bez użytkowników i skojarzyć certyfikat z profilem sieci Wi-Fi lub VPN. Rozszerza to istniejącą obsługę [przypisywania certyfikatów do urządzeń bez użytkowników z systemem Windows, iOS i Android](certificates-scep-configure.md#create-a-scep-certificate-profile).

### <a name="intune-conditional-access-ui-update------2432313----"></a>Aktualizacja interfejsu użytkownika dostępu warunkowego usługi Intune   <!-- 2432313  -->
Wprowadzamy ulepszenia interfejsu użytkownika dla dostępu warunkowego w konsoli usługi Intune. Należą do nich następujące elementy:
- Zastąpienie bloku *Dostęp warunkowy* usługi Intune blokiem z usługi Azure Active Directory. Dzięki temu będziesz mieć dostęp do pełnego zakresu ustawień i konfiguracji dotyczących dostępu warunkowego, który pozostaje technologią usługi Azure AD.
- Przeniesienie konfiguracji *łącznika usługi Exchange* do obecnego bloku *Dostęp lokalny*. Nazwa bloku jest także zmieniana na *Dostęp do programu Exchange*. Ta zmiana umieszcza w jednym miejscu konfigurowanie i monitorowanie szczegółów dotyczących usługi Exchange online i lokalnej.

### <a name="intune-will-leverage-google-play-protect-apis-on-android-devices----2577355----"></a>Usługa Intune będzie korzystać z interfejsów API usługi Google Play Protect na urządzeniach z systemem Android <!-- 2577355  -->
Niektórzy administratorzy IT muszą radzić sobie ze środowiskiem BYOD, w którym użytkownicy końcowi mogą rootować swoje telefony komórkowe lub wykonywać ich jailbreak. To zachowanie, choć czasem podejmowane bez złych zamiarów, powoduje obejście wielu zasad usługi Intune określonych w celu ochrony danych organizacji na urządzeniach użytkowników końcowych. W związku z tym usługa Intune udostępnia funkcję wykrywania rootingu i jailbreaku dla zarówno zarejestrowanych, jak i niezarejestrowanych urządzeń. W tej wersji usługa Intune wykorzysta interfejsy API usługi Google Play do dodania sprawdzeń dotyczących wykrywania rootingu dla urządzeń niezarejestrowanych. Mimo że firma Google nie udostępnia wszystkich wykonywanych sprawdzeń dotyczących rootingu, oczekujemy, że te interfejsy API wykrywają użytkowników, którzy wykonali rooting swojego urządzenia z dowolnej przyczyny — od dostosowania urządzenia do umożliwienia pobierania nowszych aktualizacji systemu operacyjnego na starszych urządzeniach. Następnie można zablokować dostęp tych użytkowników do danych firmowych lub wyczyścić ich konta firmowe z aplikacji obsługujących zasady. Dodatkowo administratorzy IT otrzymają kilka aktualizacji raportowania w bloku Intune App Protection — raport „Użytkownicy z flagą” pokazuje użytkowników wykrytych za pomocą skanowania przy użyciu interfejsu API SafetyNet usługi Google Play Protect, a raport „Potencjalnie szkodliwe aplikacje” pokazuje aplikacje wykryte za pomocą skanowania przy użyciu interfejsu API Verify Apps firmy Google. Ta funkcja jest dostępna w systemie Android. 

### <a name="win32-app-information-available-in-troubleshooting-blade----2617342------"></a>Informacje o aplikacji Win32 dostępne w bloku Rozwiązywanie problemów <!-- 2617342    -->
Będzie dostępna możliwość zbierania plików dziennika błędów dla instalacji aplikacji Win32 w bloku **Rozwiązywanie problemów** aplikacji usługi Intune. Aby uzyskać więcej informacji na temat rozwiązywania problemów z instalacją aplikacji, zobacz [Rozwiązywanie problemów z instalacją aplikacji](troubleshoot-app-install.md).

### <a name="kiosk-browser-and-microsoft-edge-browser-apps-can-run-on-windows-10-devices-in-kiosk-mode----2935135----"></a>Aplikacje Kiosk Browser i Microsoft Edge mogą pracować na urządzeniach z systemem Windows 10 w trybie kiosku <!-- 2935135  -->
Urządzenia z systemem Windows 10 pracujące w trybie kiosku umożliwiają uruchamianie jednej lub wielu aplikacji. Ta aktualizacja obejmuje kilka zmian dotyczących korzystania z aplikacji w trybie kiosku, w tym:

- Możliwość uruchamiania przeglądarek Microsoft Edge i Kiosk Browser jako aplikacji na urządzeniu kiosku (**Konfiguracja urządzenia** > **Profile** > **Nowy profil** >  **System Windows 10 i nowsze** dla platformy > **Kiosk** dla typu profilu).
- Zablokowanie lub dopuszczenie możliwości uruchamiania przeglądarki Microsoft Edge w trybie kiosku (**Konfiguracja urządzenia** > **Profile** > **Nowy profil** >  **System Windows 10 i nowsze** dla platformy > **Ograniczenia urządzenia** dla typu profilu > **Przeglądarka Microsoft Edge**). Gdy przeglądarka Microsoft Edge nie działa w trybie kiosku, użytkownicy końcowi mogą zmienić jej ustawienia.

Aby uzyskać listę bieżących ustawień, zobacz:

- [Ustawienia urządzenia z systemem Windows 10 lub nowszym, które ma działać jako kiosk](kiosk-settings-windows.md)
- [Ograniczenia urządzeń z przeglądarką Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser)

Dotyczy: System Windows 10 lub nowszy

### <a name="auto-assign-scope-tags-to-resources-created-by-an-admin-with-that-scope----3173823----"></a>Automatyczne przypisywanie tagów zakresu do zasobów utworzonych przez administratora przy użyciu danego zakresu <!-- 3173823  -->
Gdy administrator utworzy zasób, wszelkie tagi zakresu przypisane do administratora zostaną automatycznie przypisane do nowych zasobów.

### <a name="new-device-restriction-settings-for-ios-and-macos-devices----3448774---"></a>Nowe ustawienia ograniczeń urządzeń z systemami iOS i macOS <!-- 3448774 -->
Istnieje możliwość ograniczenia niektórych ustawień i funkcji na urządzeniach z systemami iOS i macOS (**Konfiguracja urządzenia** > **Profile** > **Nowy profil** >  **iOS** lub **macOS** dla platformy > **Ograniczenia urządzenia** dla typu profilu). Ta aktualizacja dodaje kolejne funkcje i ustawienia, które można kontrolować, w tym ustawianie czasu korzystania z urządzenia, zmienianie ustawień karty eSIM i planów komórkowych, opóźnianie widoczności aktualizacji oprogramowania dla użytkownika, blokowanie buforowania zawartości i nie tylko.
Aby wyświetlić bieżące funkcje i ustawienia, które można ograniczyć, zobacz:
- [Ustawienia ograniczeń dotyczących urządzeń z systemem iOS](device-restrictions-ios.md)
- [Ustawienia ograniczeń dotyczących urządzeń z systemem macOS](device-restrictions-macos.md)

Dotyczy:
- iOS
- macOS

### <a name="failed-enrollment-report-moves-to-the-device-enrollment-blade----3560202---"></a>Raport niepowodzenia rejestracji zostanie przeniesiony do bloku Rejestrowanie urządzenia <!-- 3560202 -->
Raport **Rejestracje zakończone niepowodzeniem** zostanie przeniesiony do sekcji **Monitor** bloku **Rejestracja urządzenia**. Dodane zostaną również dwie nowe kolumny (Metoda rejestracji i Wersja systemu operacyjnego).

### <a name="change-kiosk-to-dedicated-devices----3598402----"></a>Zmiana pozycji „Kiosk” na „Urządzenia dedykowane” <!-- 3598402  -->
W ramach ujednolicania terminologii dla systemu Android pozycja **Kiosk** zostanie zmieniona na **Urządzenia dedykowane** w ramach pozycji Profile konfiguracji urządzeń, **System Android dla firm** > **Właściciel urządzenia** > **Ograniczenia urządzenia**.

### <a name="safari-and-delaying-user-software-update-visibility-ios-settings-are-moving-in-the-intune-ui----3640850--3803313----"></a>Ustawienia systemu iOS dotyczące przeglądarki Safari i opóźniania widoczności aktualizacji oprogramowania użytkownika są przenoszone w interfejsie użytkownika usługi Intune <!-- 3640850, , 3803313  -->
W przypadku urządzeń z systemem iOS można skonfigurować ustawienia przeglądarki Safari i aktualizacje oprogramowania. W ramach tej aktualizacji wymienione ustawienia są przenoszone do różnych części interfejsu użytkownika usługi Intune:

- Ustawienia przeglądarki Safari są przenoszone z pozycji **Safari**(**Konfiguracji urządzenia** > **Profile** > **Nowy profil** > **iOS** dla platformy > **Ograniczenia urządzenia** dla typu profilu) do pozycji **Aplikacje wbudowane**. 
- Ustawienie **Opóźnianie widoczności aktualizacji oprogramowania użytkownika dla urządzeń z systemem iOS w trybie nadzorowanym** (**Aktualizacje oprogramowania** > **Aktualizuj zasady dla systemu iOS**) jest przenoszone do obszaru **Ograniczenia urządzeń** > **Ogólne**.

Aby uzyskać listę bieżących ustawień, zobacz [Ograniczenia urządzeń z systemem iOS](device-restrictions-ios.md) i [Aktualizacje oprogramowania dla systemu iOS](software-updates-ios.md).

Dotyczy: 
- iOS

### <a name="enabling-restrictions-in-the-device-settings-is-renamed-to-screen-time-on-ios-devices----3699164----"></a>Nazwa opcji Włączanie ograniczeń w ustawieniach urządzenia zostanie zmieniona na Czas korzystania z urządzenia na urządzeniach z systemem iOS <!-- 3699164  -->
Istnieje możliwość skonfigurowania pozycji **Włączanie ograniczeń w ustawieniach urządzenia** na urządzeniach nadzorowanych z systemem iOS (**Konfiguracja urządzenia** > **Profile** > **Nowy profil** > **iOS** dla platformy > **Ograniczenia urządzenia** dla typu profilu > **Ogólne**). W ramach tej aktualizacji nazwa tego ustawienia zostanie zmieniona na **Czas korzystania z urządzenia (tylko nadzorowane)**. Zachowanie jest takie samo. W szczególności: 

- System iOS 11.4.1 i starsze: opcja **Blokuj** uniemożliwia użytkownikom końcowym ustawianie własnych ograniczeń w ustawieniach urządzenia. 
- System iOS 12.0 i nowsze: opcja **Blokuj** uniemożliwia użytkownikom końcowym ustawianie pozycji **Czas korzystania z urządzenia** w ustawieniach urządzenia, w tym ograniczeń dotyczących zawartości i prywatności. Na urządzeniach uaktualnionych do systemu iOS 12.0 karta ograniczeń nie będzie już widoczna w ustawieniach urządzenia. Te ustawienia znajdują się teraz w obszarze **Czas korzystania z urządzenia**. 

Aby uzyskać listę bieżących ustawień, zobacz [Ustawienia ograniczenia urządzenia z systemem iOS](device-restrictions-ios.md).

Dotyczy: 
- iOS

### <a name="app-status-details-for-ios-apps----3761235----"></a>Szczegóły stanu aplikacji systemu iOS <!-- 3761235  -->
Zostaną wprowadzone nowe komunikaty o błędzie dla instalacji aplikacji związane z następującymi sytuacjami:
- Błąd aplikacji programu VPP podczas instalowania na współużytkowanym urządzeniu iPad
- Błąd, jeśli sklep App Store jest wyłączony
- Błąd szukania licencji programu VPP dla aplikacji
- Błąd instalacji aplikacji systemowych za pomocą dostawcy rozwiązania MDM
- Błąd instalacji aplikacji, gdy urządzenie jest w trybie zgubienia lub kiosku
- Błąd instalacji aplikacji, gdy użytkownik nie jest zalogowany do sklepu App Store

W usłudze Intune wybierz pozycję **Aplikacje klienckie** > **Aplikacje** > „Nazwa aplikacji” > **Stan instalacji urządzenia**. Nowe komunikaty o błędzie będą dostępne w kolumnie **Szczegóły stanu**.

<!-- 1901 start -->

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----1672660----"></a>Wdrażanie licencjonowanych w trybie online aplikacji ze sklepu Microsoft Store dla Firm <!-- 1672660  -->
Będzie możliwe przypisywanie w kontekście urządzenia wymaganych, licencjonowanych w trybie online aplikacji ze sklepu Microsoft Store dla Firm. Wdrożona w ten sposób aplikacja ze sklepu Microsoft Store dla Firm będzie mogła być zainstalowana dla wszystkich użytkowników urządzenia. Dotyczy to tylko urządzeń stacjonarnych z systemem Windows 10 w wersji RS4 lub nowszej. Możliwość instalacji w kontekście urządzenia jest dostępna na stronie przypisywania aplikacji klienckich dla aplikacji MSFB licencjonowanych w trybie online.

<!-- 1812 start -->

### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Wdrażanie aplikacji APP-WE dla systemu Android Enterprise <!-- 1171203 -->
Dla urządzeń z systemem Android w scenariuszu wdrażania zasad ochrony aplikacji bez rejestracji (APP-WE) będzie można używać zarządzanego sklepu Google Play w celu wdrażania aplikacji ze sklepu i aplikacji biznesowych dla użytkowników. Mówiąc ściślej, dział IT może udostępnić użytkownikom końcowym środowisko instalacji i wykazu aplikacji, które nie wymaga już od użytkowników końcowych rozluźnienia stanu zabezpieczeń urządzeń przez umożliwienie instalacji z nieznanych źródeł. Ponadto ten scenariusz wdrażania zapewni ulepszone środowisko pracy użytkownika końcowego.

### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359---"></a>Zasady usługi Intune aktualizują metodę uwierzytelniania i instalację aplikacji Portal firmy <!-- 1927359 -->
Na urządzeniach, które zostały już zarejestrowane za pomocą Asystenta ustawień przy użyciu jednej z metod rejestracji urządzeń firmowych firmy Apple, usługa Intune nie będzie już obsługiwać aplikacji Portal firmy po jej ręcznym zainstalowaniu ze sklepu z aplikacjami przez użytkowników końcowych. Ta zmiana ma zastosowanie tylko w sytuacji, w której uwierzytelnianie jest przeprowadzane przy użyciu asystenta ustawień firmy Apple podczas rejestracji. Ta zmiana dotyczy tylko urządzeń z systemem iOS zarejestrowanych przy użyciu następujących rozwiązań:  
* Apple Configurator
* Apple Business Manager
* Apple School Manager
* Apple Device Enrollment Program (DEP)

Jeśli użytkownicy zainstalują aplikację Portal firmy ze sklepu z aplikacjami, a następnie podejmą próbę zarejestrowania urządzeń przy jej użyciu, wystąpi błąd. Oczekuje się, że te urządzenia będą używać aplikacji Portal firmy tylko w sytuacji, gdy nastąpi automatyczne wypchnięcie przez usługę Intune podczas rejestracji. Profile rejestracji w usłudze Intune w witrynie Azure Portal zostaną zaktualizowane tak, aby określić sposób uwierzytelniania urządzeń oraz wskazać, czy otrzymują aplikację Portal firmy. Jeśli chcesz, aby użytkownicy urządzenia DEP mieli aplikację Portal firmy, musisz określić swoje preferencje w profilu rejestracji. Ponadto ekran **Identyfikowanie urządzenia** w aplikacji Portal firmy wkrótce będzie przestarzały.  
Aby zainstalować Portal firmy na już zarejestrowanych urządzeniach objętych programem DEP, należy przejść do usługi Intune > Aplikacje klienckie i wypchnąć ją jako aplikację zarządzaną przy użyciu zasad konfiguracji aplikacji. Szczegółowe informacje na temat tych czynności zostaną przedstawione w przyszłej dokumentacji.

### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Szablony administracyjne są dostępne w publicznej wersji zapoznawczej i zostały przeniesione do własnego profilu konfiguracji <!-- 3322847 -->
Szablony administracyjne w usłudze Intune (**Konfiguracja urządzenia** > **Szablony administracyjne**) są obecnie dostępne w prywatnej wersji zapoznawczej. Dzięki tej aktualizacji szablony administracyjne obejmują około 300 ustawień, którymi można zarządzać w usłudze Intune. Wcześniej ustawienia te istniały tylko w edytorze zasad grupy.
Szablony administracyjne są dostępne w publicznej wersji zapoznawczej Szablony administracyjne są przenoszone z obszaru **Konfiguracja urządzenia** > **Szablony administracyjne** do obszaru **Konfiguracja urządzenia** > **Profile** >**Utwórz profil** > w polu **Platforma** wybierz  **Windows 10 i nowsze**, w polu **Typ profilu** wybierz **Szablony administracyjne**.
Włączone raportowanie Dotyczy: System Windows 10 lub nowszy

### <a name="intune-macos-company-portal-dark-mode----3300524---"></a>Tryb ciemny Portalu firmy usługi Intune w systemie macOS <!-- 3300524 -->
Portal firmy usługi Intune w systemie macOS obsługuje teraz tryb ciemny systemu macOS. Po włączeniu trybu ciemnego na urządzeniu z systemem macOS w wersji 10.14 lub nowszej aplikacja Portal firmy dostosuje swój wygląd do kolorów używanych w tym trybie.

<!-- 1809 start -->  

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Ustawienia zasad ochrony aplikacji dla danych internetowych <!-- 2662995 -->
Ustawienia zasad ochrony aplikacji dla zawartości internetowej na urządzeniach z systemami Android i iOS zostaną zaktualizowane w celu ulepszenia obsługi linków internetowych http i https, a także przesyłania danych za pośrednictwem linków uniwersalnych systemu iOS i linków między aplikacjami systemu Android.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Token VPP firmy Apple używany przez inne rozwiązanie MDM <!-- 1488946 -->
Usługa Intune wykryje i wyświetli szczegółowe informacje, jeśli token programu VPP (Volume Purchase Program) jest używany zarówno przez usługę Intune, jak i inne rozwiązanie MDM.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Wycofane urządzenia na pulpicie nawigacyjnym zgodności urządzeń <!-- 1981119 -->
W ramach przyszłej aktualizacji wycofane urządzenia zostaną usunięte z pulpitu nawigacyjnego zgodności urządzeń. Spowoduje to zmianę liczb dotyczących zgodności.

## <a name="notices"></a>Uwagi

Aktualnie nie ma aktywnych powiadomień.

### <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).
