---
title: Co nowego w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Dowiedz się, co nowego w witrynie Azure Portal usługi Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/31/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 72b96714e8740fe4077583cfa5d9f148c2ee0908
ms.sourcegitcommit: f41b22f65286a64a8002e2cbe80debfdd6692278
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2019
ms.locfileid: "66469590"
---
# <a name="whats-new-in-microsoft-intune"></a>Co nowego w usłudze Microsoft Intune

Dowiedz się co tydzień, co nowego w usłudze Microsoft Intune. Możesz również sprawdzić informacje o [nadchodzących zmianach](in-development.md), [ważnych powiadomieniach](#notices) oraz [poprzednich wersjach](whats-new-archive.md). 

> [!Note]
> Niektóre funkcje mogą być wprowadzane przez kilka tygodni i nie być dostępne dla wszystkich klientów w pierwszym tygodniu.

**Kanał informacyjny RSS**: otrzymuj powiadomienie, gdy ta strona zostanie zaktualizowana przez skopiowanie i wklejenie następującego adresu URL w czytniku kanałów informacyjnych: `https://docs.microsoft.com/api/search/rss?search=%22What%27s+new+in+microsoft+intune%3F+-+Azure%22&locale=en-us`

<!-- Common categories:  
### App management
### Device configuration
### Device enrollment
### Device management
### Intune apps
### Monitor and troubleshoot
### Role-based access control

-->  

<!-- ########################## -->

## <a name="week-of-may-27-2019"></a>Tydzień od 27 maja 2019 r. 

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="reporting-for-potentially-harmful-apps-on-android-devices----4223162---"></a>Raporty dotyczące potencjalnie szkodliwych aplikacji na urządzeniach z systemem Android <!-- 4223162 -->
Usługa Intune udostępnia teraz dodatkowe raporty na temat potencjalnie szkodliwych aplikacji na urządzeniach z systemem Android. 

## <a name="week-of-may-20-2019"></a>Tydzień od 20 maja 2019 r. 

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="windows-company-portal-app----3316993---"></a>Aplikacja Portal firmy dla systemu Windows <!-- 3316993 -->
Aplikacja Portal firmy w systemie Windows będzie teraz mieć nową stronę z etykietą **Urządzenia**. Strona **Urządzenia** przedstawia użytkowników końcowych wszystkich zarejestrowanych urządzeń. Użytkownicy zobaczą tę zmianę w Portalu firmy, jeśli korzystają z wersji 10.3.4291.0 lub nowszej. Aby uzyskać informacje na temat konfigurowania Portalu firmy, zobacz [Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune](company-portal-app.md).

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="autopilot-device-orderid-attribute-name-changed-to-group-tag----4659453---"></a>Zmieniono nazwę atrybutu OrderID urządzenia rozwiązania Autopilot na tag grupy <!-- 4659453 -->

Aby zwiększyć intuicyjność, zmieniono nazwę atrybutu **OrderID** w urządzeniach rozwiązania Autopilot na **Tag grupy**. W przypadku przekazywania informacji o urządzeniu rozwiązania Autopilot za pomocą plików CSV jako nagłówka kolumny należy użyć tagu grupy, a nie atrybutu OrderID.  

## <a name="week-of-may-13-2019"></a>Tydzień od 13 maja 2019 r. 

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359-idready-wnready--"></a>Zasady usługi Intune aktualizują metodę uwierzytelniania i instalację aplikacji Portal firmy  <!-- 1927359 idready wnready-->
Na urządzeniach, które zostały już zarejestrowane za pomocą Asystenta ustawień przy użyciu jednej z metod rejestracji urządzeń firmowych firmy Apple, usługa Intune nie będzie już obsługiwać aplikacji Portal firmy po jej ręcznym zainstalowaniu ze sklepu z aplikacjami przez użytkowników końcowych. Ta zmiana ma zastosowanie tylko w sytuacji, w której uwierzytelnianie jest przeprowadzane przy użyciu asystenta ustawień firmy Apple podczas rejestracji. Ta zmiana dotyczy tylko urządzeń z systemem iOS zarejestrowanych przy użyciu następujących rozwiązań:  
* Apple Configurator

* Apple Business Manager

* Apple School Manager

* Apple Device Enrollment Program (DEP)

Jeśli użytkownicy zainstalują aplikację Portal firmy ze sklepu z aplikacjami, a następnie podejmą próbę zarejestrowania urządzeń przy jej użyciu, wystąpi błąd. Oczekuje się, że te urządzenia będą używać aplikacji Portal firmy tylko w sytuacji, gdy nastąpi automatyczne wypchnięcie przez usługę Intune podczas rejestracji. Profile rejestracji w usłudze Intune w witrynie Azure Portal zostaną zaktualizowane tak, aby określić sposób uwierzytelniania urządzeń oraz wskazać, czy otrzymują aplikację Portal firmy. Jeśli chcesz, aby użytkownicy urządzenia DEP mieli aplikację Portal firmy, musisz określić swoje preferencje w profilu rejestracji. 

Ponadto ekran **Identyfikowanie urządzenia** w aplikacji Portal firmy dla systemu iOS jest usuwany. W związku z tym administratorzy, którzy chcą włączyć dostęp warunkowy lub wdrażać aplikacje firmowe, muszą zaktualizować profil rejestracji w programie DEP. To wymaganie ma zastosowanie tylko, jeśli rejestracja w programie DEP jest uwierzytelniana przy użyciu Asystenta ustawień. W takim przypadku należy wypchnąć aplikację Portal firmy do urządzenia. W tym celu wybierz pozycję **Intune** > **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > wybierz token > **Profile** > wybierz profil > **Właściwości** > ustaw pozycję **Zainstaluj Portal firmy** na wartość **Tak**.

Aby zainstalować Portal firmy na już zarejestrowanych urządzeniach objętych programem DEP, należy przejść do usługi Intune > Aplikacje klienckie i wypchnąć ją jako aplikację zarządzaną przy użyciu zasad konfiguracji aplikacji. 

#### <a name="configure-how-end-users-update-a-line-of-business-lob-app-using-an-app-protection-policy----3568384---"></a>Konfigurowanie sposobu aktualizowania aplikacji biznesowej (LOB) przez użytkowników końcowych przy użyciu zasad ochrony aplikacji <!-- 3568384 -->
Teraz w konfiguracji można określić, gdzie użytkownicy końcowi mogą uzyskać zaktualizowaną wersję aplikacji biznesowych (LOB). Użytkownicy końcowi będą widzieli tę funkcję w oknie dialogowym warunkowego uruchamiania **minimalnej wersji aplikacji**, które wyświetli monit o aktualizację do minimalnej wersji aplikacji LOB przez użytkownika końcowego. Te szczegółowe informacje dotyczące aktualizacji należy podać w ramach zasad ochrony aplikacji LOB. Ta funkcja jest dostępna w systemie iOS i Android. W systemie iOS ta funkcja wymaga zintegrowania aplikacji (lub opakowania za pomocą narzędzia opakowującego) z zestawem SDK usługi Intune dla systemu iOS w wersji 10.0.7 lub nowszej. W systemie Android ta funkcja wymaga najnowszej wersji aplikacji Portal firmy. Aby skonfigurować sposób, w jaki użytkownik końcowy aktualizuje aplikację LOB, zasady konfiguracji aplikacji zarządzanej muszą zostać wysłane do aplikacji przy użyciu klucza, `com.microsoft.intune.myappstore`. Wysłana wartość określi, z którego sklepu użytkownik końcowy pobierze aplikację. Jeśli aplikacja jest wdrażana za pośrednictwem Portalu firmy, wartość musi być równa `CompanyPortal`. W przypadku każdego innego sklepu należy wprowadzić pełny adres URL.

#### <a name="intune-management-extension-powershell-scripts-----3734186-idready---"></a>Skrypty programu PowerShell rozszerzające zarządzanie w ramach usługi Intune  <!-- 3734186 idready -->
Skrypty programu PowerShell można skonfigurować do uruchamiania z uprawnieniami administratora na urządzeniu. Aby uzyskać więcej informacji, zobacz [Używanie skryptów programu PowerShell na urządzeniach z systemem Windows 10 w usłudze Intune](intune-management-extension.md) i [Zarządzanie aplikacjami Win32](apps-win32-app-management.md).

#### <a name="android-enterprise-app-management----4459905---"></a>Zarządzanie aplikacjami w usłudze Android Enterprise <!-- 4459905 -->
Aby ułatwić administratorom IT konfigurowanie i używanie zarządzania w usłudze Android Enterprise, cztery typowe aplikacje związane z usługą Android Enterprise zostaną automatycznie dodane do konsoli administracyjnej usługi Intune. Są to następujące cztery aplikacje w usłudze Android Enterprise:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)**  — używana w scenariuszach w pełni zarządzanych za pomocą Android Enterprise.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)**  — pomaga zalogować się do kont w przypadku używania weryfikacji dwuskładnikowej.
- **[Intune — Portal firmy](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)**  — używana w przypadku scenariuszy obejmujących zasady ochrony aplikacji i profil służbowy Android Enterprise.
- [Zarządzany ekran główny](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise) — używana w scenariuszach z użyciem Android Enterprise dla urządzeń dedykowanych/działających w trybie kiosku.

Wcześniej administratorzy IT musieli ręcznie znajdować i zatwierdzać te aplikacje w [zarządzanym sklepie Google Play](https://play.google.com/store/apps) w ramach procesu konfigurowania. Ta zmiana eliminuje te wcześniej wykonywane ręcznie kroki, aby klienci mogli łatwiej i szybciej zacząć korzystać z zarządzania w ramach usługi Android Enterprise.

Administratorzy zobaczą te cztery aplikacje automatycznie dodane do listy aplikacji usługi Intune podczas pierwszego połączenia swojego dzierżawcy usługi Intune z zarządzanym sklepem Google Play. Aby uzyskać więcej informacji, zobacz [Łączenie konta usługi Intune z kontem zarządzanego sklepu Google Play](connect-intune-android-enterprise.md). W przypadku dzierżawców, dla których już nawiązano połączenie lub rozpoczęto korzystanie z usługi Android Enterprise, administratorzy nie muszą nic robić. Te cztery aplikacje automatycznie staną się widoczne w ciągu 7 dni od ukończenia wdrożenia usługi w maju 2019 r.

### <a name="device-configuration"></a>Konfiguracja urządzenia

####  <a name="intune-security-tasks-for-defender-atp-in-public-preview--------3208597---"></a>Zadania zabezpieczeń usługi Intune dotyczące zaawansowanej ochrony przed zagrożeniami usługi Defender (w publicznej wersji zapoznawczej)     <!-- 3208597 -->
W publicznej wersji zapoznawczej można używać usługi Intune do zarządzania zadaniami zabezpieczeń dla Zaawansowanej ochrony przed zagrożeniami w usłudze Microsoft Defender. Dzięki integracji z Zaawansowaną ochroną przed zagrożeniami jest dodawane oparte na ryzyku podejście do odnajdywania, priorytetyzowania oraz korygowania luk w zabezpieczeniach i błędów konfiguracji punktów końcowych przy jednoczesnym skróceniu czasu między odnalezieniem i ograniczeniem ryzyka.

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---idstaged--"></a>Sprawdzanie mikroukładu modułu TPM w zasadach zgodności urządzeń z systemem Windows 10 <!-- 3617671   idstaged-->
Wiele urządzeń z systemem Windows 10 lub nowszym zawiera mikroukład modułu TPM (Trusted Platform Module). Ta aktualizacja obejmuje nowe ustawienie zgodności, które sprawdza wersję mikroukładu modułu TPM na urządzeniu. 

To ustawienie jest opisane w artykule [Ustawienia zasad zgodności urządzeń z systemem Windows 10 lub nowszym](compliance-policy-create-windows.md#device-security).

Dotyczy: System Windows 10 lub nowszy

#### <a name="prevent-end-users-from-modifying-their-personal-hotspot-and-disable-siri-server-logging-on-ios-devices----4097904-----"></a>Uniemożliwianie użytkownikom końcowym modyfikowania ich osobistego hotspotu i wyłączanie rejestrowania programu Siri na urządzeniach z systemem iOS <!-- 4097904   --> 
Dla urządzenia z systemem iOS można utworzyć profil ograniczeń urządzenia (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > **iOS** dla platformy > **Ograniczenia urządzenia** dla typu profilu). Ta aktualizacja obejmuje nowe ustawienia, które można skonfigurować:

- **Aplikacje wbudowane**: rejestrowanie po stronie serwera na potrzeby poleceń programu Siri
- **Sieć bezprzewodowa**: modyfikowanie osobistego hotspotu przez użytkownika (tylko tryb nadzorowany)

Aby wyświetlić te ustawienia, przejdź do [wbudowanych ustawień aplikacji dla systemu iOS](device-restrictions-ios.md#built-in-apps) i [ustawień sieci bezprzewodowej dla systemu iOS](device-restrictions-ios.md#wireless).

Dotyczy: system iOS 12.2 i nowsze

#### <a name="new-classroom-app-device-restriction-settings-for-macos-devices----4097905-----"></a>Nowe ustawienia ograniczeń urządzeń w aplikacji Klasa dotyczące urządzeń z systemem macOS <!-- 4097905   --> 
Na urządzeniach z systemem macOS można utworzyć profile konfiguracji urządzenia (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > **macOS** dla platformy > **Ograniczenia urządzenia** dla typu profilu). Ta aktualizacja obejmuje nowe ustawienia aplikacji Klasa, opcję blokowania zrzutów ekranu oraz opcję wyłączania biblioteki zdjęć iCloud.

Aby zobaczyć bieżące ustawienia, przejdź do artykułu [Ustawienia urządzeń z systemem macOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](device-restrictions-macos.md).

Dotyczy: systemu macOS

#### <a name="the-ios-password-to-access-app-store-setting-is-renamed---4557891----"></a>Nazwa ustawienia Hasło dostępu do sklepu z aplikacjami w systemie iOS została zmieniona<!-- 4557891  -->
Nazwa ustawienia **Hasło dostępu do sklepu z aplikacjami** została zmieniona na **Wymagaj hasła sklepu iTunes dla wszystkich zakupów** (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** jako platforma > **Ograniczenia urządzeń** jako typ profilu > **Sklep App Store, wyświetlanie dokumentów i granie**).

Aby wyświetlić dostępne ustawienia, przejdź do sekcji [Ustawienia systemu iOS dla sklepu App Store, wyświetlanie dokumentów i granie](device-restrictions-ios.md#app-store-doc-viewing-gaming).

Dotyczy: iOS

####  <a name="microsoft-defender-advanced-threat-protection--baseline--preview------3754134---"></a>Punkty odniesienia usługi Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender (wersja zapoznawcza)  <!--  3754134 -->
Dodaliśmy wersję zapoznawczą punktów odniesienia zabezpieczeń dla ustawień usługi [Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender](security-baseline-settings-defender-atp.md). Ten punkt odniesienia jest dostępny, jeśli środowisko spełnia wymagania wstępne dotyczące korzystania z [Zaawansowanej ochrony przed zagrożeniami w usłudze Microsoft Defender](advanced-threat-protection.md#prerequisites).

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="windows-enrollment-status-page-esp-is-now-generally-available----3605348---"></a>Strona ze stanem rejestracji w systemie Windows jest teraz ogólnie dostępna <!-- 3605348 -->
Okres obowiązywania wersji zapoznawczej strony ze stanem rejestracji zakończył się. Aby uzyskać więcej informacji, zobacz [Konfigurowanie strony ze stanem rejestracji](windows-enrollment-status.md).


#### <a name="intune-user-interface-update---autopilot-enrollment-profile-creation-----4593669---"></a>Aktualizacja interfejsu użytkownika usługi Intune — tworzenie profilu rejestracji rozwiązania Autopilot  <!-- 4593669 -->
Interfejs użytkownika służący do tworzenia profilu rejestracji rozwiązania Autopilot został zaktualizowany w celu dostosowania do stylów interfejsu użytkownika platformy Azure. Aby uzyskać więcej informacji, zobacz [Create an Autopilot enrollment profile](https://docs.microsoft.com/intune/enrollment-autopilot#create-an-autopilot-deployment-profile) (Tworzenie profilu rejestracji rozwiązania Autopilot). W przyszłości dodatkowe scenariusze usługi Intune zostaną zaktualizowane do tego nowego stylu interfejsu użytkownika.

#### <a name="enable-autopilot-reset-for-all-windows-devices----4225665---"></a>Włączanie resetowania rozwiązania Autopilot dla wszystkich urządzeń z systemem Windows <!-- 4225665 -->
Resetowanie rozwiązania Autopilot działa teraz dla wszystkich urządzeń Windows, nawet tych, które nie zostały skonfigurowane do używania strony ze stanem rejestracji. Jeśli strona ze stanem rejestracji nie została skonfigurowana na tym urządzeniu podczas początkowej rejestracji urządzenia, po zalogowaniu do urządzenia nastąpi bezpośrednie przejście do pulpitu. Synchronizacja urządzenia i wyświetlenie go jako zgodnego w usłudze Intune może potrwać do ośmiu godzin. Aby uzyskać więcej informacji, zobacz [Reset devices with remote Windows Autopilot Reset](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-reset-remote) (Resetowanie urządzeń przy użyciu zdalnego resetowania rozwiązania Autopilot w systemie Windows).

#### <a name="exact-imei-format-not-required-when-searching-all-devices---30407680---"></a>Dokładny format numerów IMEI niewymagany w przypadku wyszukiwania wszystkich urządzeń <!--30407680 -->
W przypadku wyszukiwania **wszystkich urządzeń** nie trzeba uwzględniać spacji w numerach IMEI.

#### <a name="deleting-a-device-in-the-apple-portal-will-be-reflected-in-the-intune-portal---2489996---"></a>Usunięcie urządzenia w portalu firmy Apple zostanie odzwierciedlone w portalu usługi Intune <!--2489996 -->
Jeśli urządzenie zostanie usunięte z portalu usługi Device Enrollment Program firmy Apple lub portalu Apple Business Manager, to zostanie też automatycznie usunięte z usługi Intune podczas następnej synchronizacji.

### <a name="the-enrollment-status-page-now-tracks-win32-apps----2714451---"></a>Strona Stan rejestracji śledzi teraz aplikacje Win32 <!-- 2714451 -->
Dotyczy to tylko urządzeń z systemem Windows 10 w wersji 1903 lub nowszej. Aby uzyskać więcej informacji, zobacz [Konfigurowanie strony ze stanem rejestracji](windows-enrollment-status.md).

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api----3295288---"></a>Zbiorcze resetowanie i czyszczenie urządzeń za pomocą interfejsu API programu Graph <!-- 3295288 -->
Za pomocą interfejsu API programu Graph można teraz zbiorczo zresetować i wyczyścić do 100 urządzeń.


### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="the-encryption-report-is-out-of-public-preview------4587546--------"></a>Okres obowiązywania wersji zapoznawczej raportu szyfrowania zakończył się   <!-- 4587546      -->
[Raport dotyczący szyfrowania funkcją BitLocker i szyfrowania urządzenia](encryption-monitor.md) jest teraz ogólnie dostępny i nie jest już częścią publicznej wersji zapoznawczej. 

<!-- ########################## -->

#### <a name="outlook-signature-and-biometric-settings-for--ios-and-android-devices----4050557---"></a>Ustawienia biometryczne i ustawienia podpisu programu Outlook dla urządzeń z systemami iOS i Android <!-- 4050557 -->
Teraz można określić, czy podpis domyślny jest włączony w programie Outlook na urządzeniach z systemem iOS i Android. Ponadto można zezwolić użytkownikom na zmianę ustawienia biometrycznego w programie Outlook w systemie iOS.

## <a name="week-of-may-6-2019"></a>Tydzień od 6 maja 2019 r. 

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="network-access-control-nac-support-for-f5-access-for-ios-devices----4500808---"></a>Obsługa kontrolo dostępu do sieci (NAC) dla aplikacji F5 Access dla urządzeń z systemem iOS <!-- 4500808 -->

Firma F5 opublikowała aktualizację systemu BIG-IP 13 udostępniającą funkcje kontroli dostępu do sieci dla aplikacji F5 Access w systemie iOS w usłudze Intune. Aby użyć tej funkcji:

- Zaktualizuj system BIG-IP do odświeżonej wersji 13.1.1.5. System BIG-IP 14 nie jest obsługiwany.
- Zintegruj system BIG-IP z usługą Intune, aby móc korzystać z kontroli dostępu do sieci. Kroki opisano na stronie [Overview: Configuring APM for device posture checks with endpoint management systems](https://support.f5.com/kb/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html#guid-0bd12e12-8107-40ec-979d-c44779a8cc89) (Omówienie: Konfigurowania programu APM pod kątem kontroli stanu urządzenia za pomocą systemów zarządzania punktem końcowym).
- Sprawdź ustawienie **Włącz kontrolę dostępu do sieci (NAC)** w profilu sieci VPN w usłudze Intune.

Aby wyświetlić dostępne ustawienia, przejdź na stronę [Konfigurowanie ustawień sieci VPN w urządzeniach z systemem iOS](vpn-settings-ios.md).

Dotyczy: iOS

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune----doc-vso-1521237----"></a>Zaktualizowany łącznik certyfikatów PFX dla usługi Microsoft Intune <!-- doc-vso 1521237  -->  
Udostępniliśmy aktualizację [łącznika certyfikatów PFX dla usługi Microsoft Intune](certficates-pfx-configure.md#whats-new-for-connectors), która skraca odstęp czasu sondowania z 5 minut do 30 sekund.

## <a name="week-of-april-22-2019"></a>Tydzień od 22 kwietnia 2019 r.

### <a name="use-compliance-manager-to-create-assessments-for-microsoft-intune---4404750---"></a>Używanie Menedżera zgodności do tworzenia ocen usługi Microsoft Intune<!-- 4404750 -->

[Menedżer zgodności](https://servicetrust.microsoft.com/ComplianceManager) (powoduje otwarcie innej witryny firmy Microsoft) to oparte na przepływie pracy narzędzie do oceny ryzyka w portalu Service Trust Portal firmy Microsoft. Umożliwia ono śledzenie, przypisywanie i weryfikowanie działań Twojej organizacji związanych z zapewnianiem zgodności z przepisami dotyczących usług firmy Microsoft. Możesz utworzyć własną ocenę zgodności przy użyciu usługi Office 365, platformy Azure, systemu Dynamics, usług Professional Services i usługi Intune. W przypadku usługi Intune dostępne są dwie oceny — FFIEC i RODO.

Menedżer zgodności ułatwia odpowiednie ukierunkowanie podejmowanych wysiłków, dzieląc kontrole na zarządzane przez firmę Microsoft i zarządzane przez Twoją organizację. Możesz ukończyć oceny, a następnie wyeksportować je i wydrukować.

Zgodność z [Federal Financial Institutions Examination Council (FFIEC)](https://www.microsoft.com/trustcenter/compliance/FFIEC) (powoduje otwarcie innej witryny firmy Microsoft) to zbiór standardów dla bankowości internetowej wydany przez FFIEC. To najbardziej pożądana ocena dla instytucji finansowych, które korzystają z usługi Intune. Interpretuje ona, jak usługa Intune pomaga spełnić wytyczne FFIEC dotyczące cyberbezpieczeństwa związane z obciążeniami w chmurze publicznej. Ocena FFIEC usługi Intune jest drugą oceną FFIEC w Menedżerze zgodności.

W poniższym przykładzie można zobaczyć podział kontroli FFIEC. Firma Microsoft zarządza 64 kontrolami. Ty odpowiadasz za pozostałe 12 kontroli.

![Zobacz przykładową ocenę usługi Intune dla FFIEC, uwzględniającą działania klienta i działania firmy Microsoft](./media/intune-ffiec-assessment-status.png)

[Ogólne rozporządzenie o ochronie danych (RODO)](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-overview) (powoduje otwarcie innej witryny firmy Microsoft) to prawo Unii Europejskiej, które pomaga chronić prawa osób i ich dane. RODO jest najbardziej pożądaną oceną, aby zapewnić zgodność z przepisami dotyczącymi ochrony prywatności. 

W poniższym przykładzie zostanie wyświetlony podział kontroli RODO. Firma Microsoft obsługuje 49 kontroli. Ty odpowiadasz za pozostałe 66 kontroli.

![Zobacz przykładową ocenę usługi Intune dla RODO, uwzględniającą działania klienta i działania firmy Microsoft](./media/intune-assessment-status.png)

## <a name="week-of-april-15-2019"></a>Tydzień od 15 kwietnia 2019 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="openssl-encryption-for-android-app-protection-policies----3747362---"></a>Szyfrowanie OpenSSL dla zasad ochrony aplikacji systemu Android <!-- 3747362 -->
Zasady ochrony aplikacji usługi Intune na urządzeniach z systemem Android używają teraz biblioteki szyfrowania OpenSSL zgodnej ze standardem FIPS 140-2. Aby uzyskać więcej informacji, zobacz sekcję [szyfrowanie](app-protection-policy-settings-android.md#encryption) w artykule [Ustawienia zasad ochrony aplikacji systemu Android w usłudze Microsoft Intune](app-protection-policy-settings-android.md).

#### <a name="enable-win32-app-dependencies----2617348----"></a>Włączanie zależności aplikacji Win32 <!-- 2617348  -->
Jako administrator możesz wymagać zainstalowania innych aplikacji jako zależności przed zainstalowaniem aplikacji Win32. W szczególności na urządzeniu muszą zostać zainstalowane aplikacje zależne przed zainstalowaniem aplikacji Win32. W usłudze Intune wybierz pozycję **Aplikacje klienckie** > **Aplikacje** > **Dodaj**, aby wyświetlić blok **Dodaj aplikację**. Wybierz pozycję **Aplikacja systemu Windows (Win32)** jako **typ aplikacji**. Po dodaniu aplikacji możesz wybrać pozycję **Zależności**, aby dodać aplikacje zależne, które należy zainstalować przed zainstalowaniem aplikacji Win32. Aby uzyskać więcej informacji, zobacz [Autonomiczna usługa Intune — zarządzanie aplikacjami Win32](apps-win32-app-management.md). 

#### <a name="app-version-installation-information-for-microsoft-store-for-business-apps----3537391-----"></a>Informacje o instalacji wersji aplikacji dla aplikacji ze sklepu Microsoft Store dla Firm <!-- 3537391   -->
Raporty dotyczące instalacji aplikacji obejmują informacje o wersji aplikacji w przypadku aplikacji ze sklepu Microsoft Store dla Firm. W usłudze Intune wybierz pozycję **Aplikacje klienckie** > **Aplikacje**. Wybierz pozycję **Microsoft Store dla firm**, a następnie wybierz pozycję **Stan instalacji urządzenia** w sekcji **Monitorowanie**.

#### <a name="additions-to-win32-apps-requirement-rules----3676883-----"></a>Dodatki do reguł wymagań aplikacji Win32 <!-- 3676883   -->
Możesz utworzyć reguły wymagań na podstawie skryptów programu PowerShell, wartości rejestru i informacji o systemie plików. W usłudze Intune wystarczy wybrać pozycję **Aplikacje klienckie** > **Aplikacje** > **Dodaj**. Następnie wybierz pozycję **Aplikacja systemu Windows (Win32)** jako **typ aplikacji** w bloku **Dodaj aplikację**.  Wybierz pozycję **Wymagania** > **Dodaj**, aby skonfigurować dodatkowe reguły wymagań. Następnie wybierz opcję **Typ pliku**, **Rejestr** lub **Skrypt** jako **Typ wymagania**. Aby uzyskać więcej informacji, zobacz [Zarządzanie aplikacjami Win32](apps-win32-app-management.md).

 #### <a name="configure-your-win32-apps-to-be-installed-on-intune-enrolled-azure-ad-joined-devices----3695227----"></a>Konfigurowanie aplikacji Win32 pod kątem instalowania na urządzeniach dołączonych do usługi Azure AD zarejestrowanych w usłudze Intune <!-- 3695227  -->
Można przypisać aplikacje Win32, które mają być instalowane na urządzeniach dołączonych do usługi Azure AD zarejestrowanych w usłudze Intune. Aby uzyskać więcej informacji o aplikacjach Win32 w usłudze Intune, zobacz [Zarządzanie aplikacjami Win32](apps-win32-app-management.md).

#### <a name="device-overview-shows-primary-user---794259----"></a>Na stronie przeglądu urządzenia jest wyświetlany użytkownik podstawowy <!--794259  -->
Na stronie Przegląd urządzenia będzie wyświetlany użytkownik podstawowy, nazywany również użytkownikiem koligacji urządzenia użytkownika (UDA). Aby zobaczyć użytkownika podstawowego dla urządzenia, wybierz pozycję **Intune** > **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie. Użytkownik podstawowy będzie wyświetlany w górnej części strony **Przegląd**.

#### <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices----4105925----"></a>Dodatkowe raportowanie aplikacji z zarządzanego sklepu Google Play dla urządzeń z profilem służbowym rozwiązania Android Enterprise <!-- 4105925  -->
W przypadku aplikacji z zarządzanego sklepu Google Play wdrożonych na urządzeniach z profilem służbowym rozwiązania Android Enterprise można wyświetlić numer wersji aplikacji zainstalowanej na urządzeniu. Dotyczy to tylko wymaganych aplikacji.  

#### <a name="ios-third-party-keyboards----4111843-----"></a>Klawiatury innych firm dla systemu iOS <!-- 4111843   -->
Obsługa zasad ochrony aplikacji usługi Intune dla ustawienia **Klawiatury innych firm** dotyczącego systemu iOS zostanie zakończona z powodu zmiany na platformie iOS. Nie będzie można skonfigurować tego ustawienia w konsoli administracyjnej usługi Intune i nie będzie ono wymuszane na kliencie w zestawie SDK aplikacji usługi Intune.

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="set-login-settings-and-control-restart-options-on-macos-devices----1210083----"></a>Określanie ustawień logowania i kontrolowanie opcji ponownego uruchamiania na urządzeniach z systemem macOS <!-- 1210083  -->
Na urządzeniach z systemem iOS można utworzyć profil konfiguracji urządzenia (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > wybierz **macOS** jako platformę > **Funkcje urządzenia** dla typu profilu). Ta aktualizacja obejmuje nowe ustawienia okna logowania, takie jak wyświetlanie niestandardowego transparentu, wybór sposobu logowania użytkowników, pokazywanie lub ukrywanie ustawień zasilania i inne.

Aby zapoznać się z tymi ustawieniami, zobacz artykuł [Ustawienia funkcji urządzeń z systemem macOS](macos-device-features-settings.md).

#### <a name="configure-wifi-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode---3041940----"></a>Konfigurowanie sieci Wi-Fi na dedykowanych urządzeniach z rozwiązaniem Android Enterprise w trybie Właściciel urządzenia uruchamianych w trybie kiosku z wieloma aplikacjami <!--3041940  -->
Możesz włączyć ustawienia na urządzeniu z rozwiązaniem Android Enterprise w trybie Właściciel urządzenia, kiedy jest ono uruchamiane jako dedykowane urządzenie w trybie kiosku z wieloma aplikacjami. W ramach tej aktualizacji możesz umożliwić użytkownikom konfigurowanie i nawiązywanie połączenia z sieciami Wi-Fi (**Intune** > **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Android Enterprise** jako platforma > **Tylko właściciel urządzenia, Ograniczenia dotyczące urządzeń** dla typu profilu > **Urządzenia dedykowane** > **Tryb kiosku**: **Kiosk z wieloma aplikacjami** > **Konfiguracja sieci Wi-Fi**). 

Aby wyświetlić wszystkie ustawienia, które można skonfigurować, zobacz [Ustawienia urządzeń z systemem Android Enterprise w celu zezwolenia na funkcje lub ich ograniczenia](device-restrictions-android-for-work.md).

Dotyczy: Dedykowane urządzenia z rozwiązaniem Android Enterprise działające w trybie kiosku z wieloma aplikacjami


#### <a name="configure-bluetooth-and-pairing-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode----3041941----"></a>Konfigurowanie połączenia Bluetooth i parowanie na dedykowanych urządzeniach z rozwiązaniem Android Enterprise w trybie Właściciel urządzenia działających w trybie kiosku z wieloma aplikacjami <!-- 3041941  -->
Możesz włączyć ustawienia na urządzeniu z rozwiązaniem Android Enterprise w trybie Właściciel urządzenia, kiedy jest ono uruchamiane jako dedykowane urządzenie w trybie kiosku z wieloma aplikacjami. W ramach tej aktualizacji można zezwolić użytkownikom końcowym na włączenie funkcji Bluetooth i parowanie urządzeń za pośrednictwem połączenia Bluetooth (**Intune** > **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Android Enterprise** jako platforma > **Tylko właściciel urządzenia, Ograniczenia dotyczące urządzeń** dla typu profilu > **Urządzenia dedykowane** > **Tryb kiosku**: **Kiosk z wieloma aplikacjami** > **Konfiguracja połączenia Bluetooth**). 

Aby wyświetlić wszystkie ustawienia, które można skonfigurować, zobacz [Ustawienia urządzeń z systemem Android Enterprise w celu zezwolenia na funkcje lub ich ograniczenia](device-restrictions-android-for-work.md).

Dotyczy: Dedykowane urządzenia z rozwiązaniem Android Enterprise działające w trybie kiosku z wieloma aplikacjami

#### <a name="create-and-use-oemconfig-device-configuration-profiles-in-intune----3305883----"></a>Tworzenie i używanie profilów konfiguracji urządzeń za pomocą aplikacji OEMConfig w usłudze Intune <!-- 3305883  -->
W ramach tej aktualizacji usługa Intune obsługuje konfigurowanie urządzeń z rozwiązaniem Android Enterprise za pomocą aplikacji OEMConfig. Możesz utworzyć profil konfiguracji urządzenia i zastosować ustawienia do urządzeń z rozwiązaniem Android Enterprise przy użyciu aplikacji OEMConfig (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Android Enterprise** dla platformy).

Obsługa producentów OEM jest obecnie dostępna dla poszczególnych producentów OEM. Jeśli aplikacja OEMConfig nie jest dostępna na liście aplikacji OEMConfig, skontaktuj się z `IntuneOEMConfig@microsoft.com`.

Aby dowiedzieć się więcej na temat tej funkcji, zobacz artykuł [Use and manage Android Enterprise devices with OEMConfig in Microsoft Intune](android-oem-configuration-overview.md) (Korzystanie z urządzeń z rozwiązaniem Android Enterprise i zarządzanie nimi za pomocą aplikacji OEMConfig w usłudze Microsoft Intune).

Dotyczy: Android Enterprise

#### <a name="windows-update-notifications-----3316758-3316782----"></a>Powiadomienia usługi Windows Update  <!-- 3316758, 3316782  -->
Dodaliśmy dwa *ustawienia środowiska użytkownika* do konfiguracji pierścienia usługi Windows Update, którymi można zarządzać z poziomu konsoli usługi Intune. Teraz możesz:
- Blokować lub zezwalać użytkownikom na [skanowanie w poszukiwaniu aktualizacji systemu Windows](windows-update-settings.md#block-user-from-scanning-for-windows-updates).
- Zarządzać [poziomem powiadomień witryny Windows Update](windows-update-settings.md#windows-update-notification-level) widocznym dla użytkowników.

#### <a name="new-device-restriction-settings-for-android-enterprise-device-owner----3574254----"></a>Nowe ustawienia ograniczeń urządzeń dla rozwiązania Android Enterprise w trybie Właściciel urządzenia <!-- 3574254  -->
Na urządzeniach z rozwiązaniem Android Enterprise można utworzyć profil ograniczeń urządzenia, aby zezwolić na funkcje lub ograniczyć je, ustawić reguły haseł i nie tylko (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > wybierz **Android Enterprise** jako platformę > **Tylko właściciel urządzenia > Ograniczenia dotyczące urządzeń** dla typu profilu). 

Ta aktualizacja obejmuje nowe ustawienia hasła, umożliwia pełny dostęp do aplikacji w sklepie Google Play dla w pełni zarządzanych urządzeń i nie tylko. Aby wyświetlić aktualną listę ustawień, zobacz [Ustawienia urządzeń z systemem Android Enterprise w celu zezwolenia na funkcje lub ich ograniczenia](device-restrictions-android-for-work.md). 

Dotyczy: W pełni zarządzane urządzenia z rozwiązaniem Android Enterprise

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>Sprawdzanie mikroukładu modułu TPM w zasadach zgodności urządzeń z systemem Windows 10 <!-- 3617671 -->

Ta funkcja jest opóźniona, a jej wdrożenie zaplanowano na później.

#### <a name="updated-ui-changes-for-microsoft-edge-browser-on-windows-10-and-later-devices----3775833-----"></a>Zaktualizowano zmiany interfejsu użytkownika dla przeglądarki Microsoft Edge na urządzeniach z systemem Windows 10 lub nowszym <!-- 3775833   -->
Podczas tworzenia profilu konfiguracji urządzenia można umożliwić lub ograniczyć działanie funkcji przeglądarki Microsoft Edge na urządzeniach z systemem Windows 10 lub nowszym (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **System Windows 10 lub nowszy** dla platformy > **Ograniczenia dotyczące urządzeń** dla typu profilu > **Przeglądarka Microsoft Edge**). Po wprowadzeniu tej aktualizacji ustawienia przeglądarki Microsoft Edge są bardziej opisowe i łatwiejsze do zrozumienia. 

Aby wyświetlić te funkcje, przejdź do [ustawień ograniczeń dotyczących urządzeń w przeglądarce Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser).

Dotyczy: System Windows 10 lub nowszy

#### <a name="expanded-support-for-android-enterprise-fully-managed-devices--preview-------3903241-3903244-3903246-----"></a>Rozszerzona obsługa w pełni zarządzanych urządzeń z rozwiązaniem Android Enterprise (wersja zapoznawcza)  <!--   3903241, 3903244, 3903246   -->
Nadal w publicznej wersji zapoznawczej rozszerzyliśmy naszą obsługę w pełni zarządzanych urządzeń z rozwiązaniem Android Enterprise ([po raz pierwszy przedstawioną w styczniu 2019](whats-new.md#week-of-january-14-2019) w celu uwzględnienia następujących elementów: 

- Na w pełni zarządzanych i dedykowanych urządzeniach można utworzyć [zasady zgodności](compliance-policy-create-android-for-work.md), aby uwzględnić reguły dotyczące haseł i wymagania dotyczące systemu operacyjnego (**Zgodność urządzeń** > **Zasady** > **Utwórz zasady** > **Android Enterprise** dla platformy > **Właściciel urządzenia** dla typu profilu). 

  Na dedykowanych urządzeniach urządzenie może być wyświetlane jako **Niezgodne**. Dostęp warunkowy nie jest obsługiwany na dedykowanych urządzeniach. Pamiętaj, aby wykonać zadania lub akcje służące zapewnieniu zgodności dedykowanych urządzeń z przypisanymi zasadami.

- [Dostęp warunkowy](conditional-access.md) — zasady dostępu warunkowego, które mają zastosowanie do systemu Android, są stosowane również do w pełni zarządzanych urządzeń z rozwiązaniem Android Enterprise. Użytkownicy mogą teraz zarejestrować swoje w pełni zarządzane urządzenia w usłudze Azure Active Directory przy użyciu **aplikacji usługi Microsoft Intune**. Następnie można wyświetlić i rozwiązać wszelkie problemy ze zgodnością, aby uzyskać dostęp do zasobów organizacji.

- Nowa aplikacja użytkownika końcowego (aplikacja usługi Microsoft Intune) — istnieje nowa aplikacja użytkownika końcowego dla w pełni zarządzanych urządzeń z systemem Android o nazwie **Microsoft Intune**. Ta nowa aplikacja jest lekka, nowoczesna i zapewnia podobne funkcje jak aplikacja Portal firmy, ale dla w pełni zarządzanych urządzeń. Aby uzyskać więcej informacji, zobacz [aplikację Microsoft Intune w sklepie Google Play](https://play.google.com/store/apps/details?id=com.microsoft.intune).

W celu skonfigurowania w pełni zarządzanych urządzeń z systemem Android przejdź kolejno do pozycji **Rejestrowanie urządzenia** > **Rejestracja w systemie Android** > **Firmowe, w pełni zarządzane urządzenia użytkowników**. Obsługa w pełni zarządzanych urządzeń z systemem Android pozostaje w wersji zapoznawczej i niektóre funkcje usługi Intune mogą nie być w pełni funkcjonalne.  

Aby dowiedzieć się więcej na temat tej wersji zapoznawczej, zapoznaj się z naszym blogiem: [Usługa Microsoft Intune — wersja zapoznawcza 2 dla w pełni zarządzanych urządzeń z rozwiązaniem Android Enterprise](https://aka.ms/preview2_AE_fullymanaged).


### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470--wnstaged--"></a>Konfigurowanie profilu pod kątem pominięcia niektórych ekranów asystenta ustawień <!-- 2276470  wnstaged-->
Podczas tworzenia profilu rejestracji systemu macOS możesz skonfigurować go tak, aby pominąć dowolny z następujących ekranów, gdy użytkownik będzie korzystać z asystenta ustawień:
- Wygląd
- Wyświetlanie sygnału
- iCloudStorage Jeśli tworzysz nowy profil lub edytujesz profil, wybrane pomijane ekrany muszą być synchronizowane z serwerem MDM firmy Apple.  Użytkownicy mogą wydać ręczną synchronizację urządzeń, aby nie było ma żadnego opóźnienia podczas pobierania zmian profilu.
Aby uzyskać więcej informacji, zobacz [Automatically enroll macOS devices with the Device Enrollment Program or Apple School Manager](device-enrollment-program-enroll-macos.md) (Automatyczne rejestrowanie urządzeń z systemem macOS w ramach programu Device Enrollment Program lub usługi Apple School Manager).

#### <a name="bulk-device-naming-when-enrolling-corporate-ios-devices--3566569----"></a>Zbiorcze nadawanie nazw urządzeniom podczas rejestrowania urządzeń firmowych z systemem iOS<!--3566569  -->
Korzystając z jednej z metod rejestracji firmowej Apple (DEP/ABM/ASM), można ustawić format nazwy urządzenia w celu automatycznego nadawania nazw przychodzącym urządzeniom z systemem iOS. Możesz określić format, który zawiera typ urządzenia i numer seryjny w szablonie. Aby to zrobić, wybierz pozycję **Intune** > **Rejestrowanie urządzeń** > **Rejestracja Apple** > **Tokeny programu rejestracji** > **wybierz token** >**Utwórz profil** > **Format nazewnictwa urządzeń**. Można edytować istniejące profile, ale nazwa będzie stosowana tylko dla nowo synchronizowanych urządzeń.

#### <a name="updated-default-timeout-message-on-enrollment-status-page----3959331---"></a>Zaktualizowano domyślny komunikat limitu czasu na stronie ze stanem rejestracji <!-- 3959331 -->
Zaktualizowaliśmy domyślny komunikat limitu czasu wyświetlany dla użytkowników, gdy strona ze stanem rejestracji przekroczy wartość limitu czasu określoną w profilu strony ze stanem rejestracji. Nowy komunikat domyślny jest widoczny dla użytkowników i pomaga im zrozumieć następne akcje do wykonania w odniesieniu do ich wdrożenia strony ze stanem rejestracji.  

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="retire-noncompliant-devices-----1827291-----"></a>Wycofywanie niezgodnych urządzeń  <!-- 1827291   -->
Ta funkcja została odroczona, a jej wdrożenie jest planowane w przyszłej wersji.


### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="intune-data-warehouse-v10-changes-reflecting-back-to-beta----4403765---"></a>Zmiany magazynu danych usługi Intune w wersji 1.0 są odzwierciedlane wstecznie w wersji beta <!-- 4403765 -->
Gdy wersja 1.0 zadebiutowała w wydaniu 1808, różniła się pod pewnymi istotnymi względami od wersji beta interfejsu API. W wydaniu 1903 te zmiany zostaną odzwierciedlone z powrotem w wersji beta interfejsu API. Jeśli masz ważne raporty korzystające z wersji beta interfejsu API, zdecydowanie zalecamy przełączenie tych raportów do wersji 1.0 w celu uniknięcia zmian powodujących niezgodności. Aby uzyskać więcej informacji, zobacz [Dziennik zmian dla interfejsu API magazynu danych usługi Intune](reports-changelog.md#1903-part-2).

#### <a name="monitor-security-baseline-status-public-preview----3082047---"></a>Monitorowanie stanu punktów odniesienia zabezpieczeń (publiczna wersja zapoznawcza) <!-- 3082047 --> 
Dodaliśmy [widok według kategorii](security-baselines-monitor.md#per-category-view) do monitorowania punktów odniesienia zabezpieczeń. (Punkty odniesienia zabezpieczeń pozostają w wersji zapoznawczej). W widoku według kategorii wyświetlane są poszczególne kategorie z punktu odniesienia wraz z odsetkiem urządzeń należących do poszczególnych grup stanów dla danej kategorii. Teraz można zobaczyć, ile urządzeń nie pasuje do poszczególnych kategorii, jest nieprawidłowo skonfigurowanych lub nie ma zastosowania.

### <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach

#### <a name="scope-tags-for-apple-vpp-tokens---2371886----"></a>Tagi zakresu dla tokenów VPP firmy Apple <!--2371886  -->
Teraz możesz dodać tagi zakresu do tokenów VPP firmy Apple. Tylko użytkownicy z przypisanym tym samym tagiem zakresu będą mieli dostęp do tokenu VPP firmy Apple z tym tagiem. Aplikacje programu VPP i książki elektroniczne zakupione przy użyciu tego tokenu dziedziczą jego tagi zakresu. Aby uzyskać więcej informacji na temat tagów zakresu, zobacz [Use RBAC and scope tags](scope-tags.md) (Używanie kontroli RBAC i tagów zakresu).







## <a name="week-of-april-1-2019"></a>Tydzień od 1 kwietnia 2019 r.

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="updated-certificate-connectors-----icm-113304612---"></a>Zaktualizowane łączniki certyfikatów  <!-- ICM 113304612 -->
Wydaliśmy aktualizacje dla [łącznika certyfikatów usługi Intune i łącznika certyfikatów PFX dla usługi Microsoft Intune](certficates-pfx-configure.md#whats-new-for-connectors). Nowe wersje rozwiązują kilka znanych problemów.  

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="user-experience-update-for-the-company-portal-app-for-ios----2536024---"></a>Aktualizacja środowiska użytkownika aplikacji Portal firmy dla systemu iOS <!-- 2536024 -->
Strona główna aplikacji Portal firmy dla urządzeń z systemem iOS została przeprojektowana. Dzięki tej zmianie strona główna będzie bardziej zgodna z wzorcami interfejsu użytkownika systemu iOS, a także będzie zapewniać lepsze możliwości odnajdywania aplikacji i książek elektronicznych.

#### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users---3448635---"></a>Zmiany dotyczące rejestracji za pomocą aplikacji Portal firmy dla użytkowników urządzeń z systemem iOS 12 <!--3448635 -->  
Ekrany i kroki rejestracji urządzeń z systemem iOS za pomocą aplikacji Portal firmy zostały zaktualizowane, aby były zgodne ze zmianami rejestracji w rozwiązaniu MDM wydanymi w systemie iOS 12.2 firmy Apple. Zaktualizowany przepływ pracy monituje użytkowników o:  

* Zezwolenie przeglądarce Safari na otwarcie witryny internetowej Portal firmy i pobranie profilu zarządzania przed powrotem do aplikacji Portal firmy.  
* Otwarcie aplikacji Ustawienia w celu zainstalowania profilu zarządzania na urządzeniu użytkownika.
* Powrót do aplikacji Portal firmy w celu ukończenia procesu rejestracji.  

Aby zapoznać się ze zaktualizowanymi krokami i ekranami rejestracji, zobacz [Rejestrowanie urządzenia z systemem iOS w usłudze Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios).  

## <a name="week-of-march-25-2019"></a>Tydzień od 25 marca 2019 r.

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

### <a name="support-for-the-power-bi-compliance-app-from-the-data-warehouse-blade-in-microsoft-intune----4260871---"></a>Obsługa aplikacji Power BI Compliance z poziomu bloku Magazyn danych w usłudze Microsoft Intune <!-- 4260871 -->
Wcześniej link **Pobierz plik usługi Power BI** w bloku **Magazyn danych usługi Intune** umożliwiał pobranie raportu magazynu danych usługi Intune (pliku pbix). Ten raport został zastąpiony aplikacją Power BI Compliance. Aplikacja Power BI Compliance nie wymaga specjalnego ładowania ani konfiguracji. Będzie ona otwierana bezpośrednio w portalu usługi Power BI w trybie online i będzie wyświetlać dane dla Twojej dzierżawy usługi Intune na podstawie Twoich poświadczeń. W usłudze Intune wybierz link **Skonfiguruj magazyn danych usługi Intune** po prawej stronie bloku usługi Intune. Następnie kliknij pozycję **Pobierz aplikację Power BI**. Aby uzyskać więcej informacji, zobacz [Nawiązywanie połączenia z magazynem danych przy użyciu usługi Power BI](reports-proc-get-a-link-powerbi.md).

## <a name="week-of-march-18-2019"></a>Tydzień od 18 marca 2019 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="deploy-microsoft-visio-and-microsoft-project----3725386----"></a>Wdrażanie programu Microsoft Visio i programu Microsoft Project <!-- 3725386  -->
Teraz możesz wdrożyć klienta klasycznego usługi Microsoft Project Online i program Microsoft Visio Pro dla usługi Office 365 jako niezależne aplikacje na urządzeniach z systemem Windows 10 przy użyciu usługi Microsoft Intune, jeśli jesteś właścicielem licencji dla tych aplikacji. W usłudze Intune wybierz pozycję **Aplikacje klienckie** > **Aplikacje** > **Dodaj**, aby wyświetlić blok **Dodaj aplikację**. W bloku **Dodaj aplikację** wybierz **System Windows 10** jako **Typ aplikacji**. Następnie wybierz pozycję **Konfiguruj pakiet aplikacji**, aby wybrać aplikacje do zainstalowania. Aby uzyskać więcej informacji na temat aplikacji usługi Office 365 dla urządzeń z systemem Windows 10, zobacz [Przypisywanie aplikacji usługi Office 365 do urządzeń z systemem Windows 10 przy użyciu usługi Microsoft Intune](apps-add-office365.md).

#### <a name="microsoft-visio-pro-for-office-365-product-name-change----3593653----"></a>Zmiana nazwy produktu Microsoft Visio Pro dla usługi Office 365 <!-- 3593653  -->
Produkt **Microsoft Visio Pro dla usługi Office 365** teraz będzie nosił nazwę **Microsoft Visio Online Plan 2**.  Aby uzyskać więcej informacji na temat programu Microsoft Visio, zobacz [Visio Online Plan 2](https://products.office.com/visio/visio-online-plan-2). Aby uzyskać więcej informacji na temat aplikacji usługi Office 365 dla urządzeń z systemem Windows 10, zobacz [Przypisywanie aplikacji usługi Office 365 do urządzeń z systemem Windows 10 przy użyciu usługi Microsoft Intune](apps-add-office365.md).

#### <a name="intune-app-protection-policy-app-character-limit-setting----3291302----"></a>Ustawienie limitu znaków w zasadach ochrony aplikacji usługi Intune <!-- 3291302  -->
Administratorzy usługi Intune mogą określić wyjątek od ustawienia zasad **Ogranicz wycinanie, kopiowanie i wklejanie w innych aplikacjach** w zasadach ochrony aplikacji usługi Intune.  Jako administrator możesz określić liczbę znaków, które mogą być wycinane lub kopiowane z zarządzanej aplikacji. To ustawienie umożliwia udostępnienie określonej liczby znaków w dowolnej aplikacji niezależnie od ustawienia „Ogranicz wycinanie, kopiowanie i wklejanie w innych aplikacjach”. Pamiętaj, że wersja aplikacji Portal firmy usługi Intune dla systemu Android wymaga wersji 5.0.4364.0 lub nowszej. Aby uzyskać więcej informacji, zobacz [Ochrona danych w systemie iOS](app-protection-policy-settings-ios.md#data-protection), [Ochrona danych w systemie Android](app-protection-policy-settings-android.md#data-protection), i [Przeglądanie dzienników ochrony aplikacji klienta](app-protection-policy-settings-log.md#app-protection-policy-settings).

#### <a name="office-deployment-tool-odt-xml-for-office-proplus-deployment----3192477-----"></a>Plik XML narzędzia wdrażania pakietu Office dla wdrożenia pakietu Office ProPlus <!-- 3192477   -->
Można będzie udostępnić plik XML narzędzia wdrażania pakietu Office podczas tworzenia wystąpienia pakietu Office Pro Plus w konsoli administracyjnej usługi Intune. Zapewni to większe możliwości dostosowywania, jeśli istniejące opcje interfejsu użytkownika usługi Intune nie odpowiadają Twoim potrzebom. Aby uzyskać więcej informacji, zobacz [Przypisywanie aplikacji usługi Office 365 do urządzeń z systemem Windows 10 przy użyciu usługi Microsoft Intune](https://docs.microsoft.com/intune/apps-add-office365) i [Opcje konfiguracji narzędzia wdrażania pakietu Office](https://docs.microsoft.com/DeployOffice/configuration-options-for-the-office-2016-deployment-tool).

#### <a name="app-icons-will-now-be-displayed-with-an-automatically-generated-background----1429026----"></a>Ikony aplikacji będą teraz wyświetlane z automatycznie wygenerowanym tłem <!-- 1429026  -->
W aplikacji Portal firmy dla systemu Windows ikony aplikacji będą teraz wyświetlane z automatycznie wygenerowanym tłem określanym na podstawie dominującego koloru ikony (jeśli można będzie go wykryć). O ile będzie to miało zastosowanie, to tło zastąpi szare obramowanie, które było wcześniej widoczne na kafelkach aplikacji. Użytkownicy zobaczą tę zmianę w wersjach aplikacji Portal firmy późniejszych niż 10.3.3451.0.

#### <a name="install-available-apps-using-the-company-portal-app-after-windows-bulk-enrollment----2751523-----"></a>Instalowanie dostępnych aplikacji przy użyciu aplikacji Portal firmy po rejestracji zbiorczej urządzeń z systemem Windows <!-- 2751523   -->
Urządzenia z systemem Windows zarejestrowane w usłudze Intune przy użyciu [rejestracji zbiorczej systemu Windows](windows-bulk-enroll.md) (pakietów aprowizacji) będą mogły instalować dostępne aplikacje przy użyciu aplikacji Portal firmy. Aby uzyskać więcej informacji na temat aplikacji Portal firmy, zobacz [Ręczne dodawanie aplikacji Portal firmy dla systemu Windows 10](store-apps-company-portal-app.md) i [Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune](company-portal-app.md).

> [!Note]
> Ta funkcja nie została jeszcze w pełni wdrożona dla wszystkich klientów. Jeśli nie możesz korzystać z aplikacji Portal firmy na urządzeniach zarejestrowanych zbiorczo, być może musisz poczekać, aż ta zmiana zostanie wdrożona na Twoim koncie.

#### <a name="the-microsoft-teams-app-can-be-selected-as-part-of-the-office-app-suite----3828932----"></a>Aplikację Microsoft Teams można wybrać jako część pakietu aplikacji pakietu Office <!-- 3828932  -->
Aplikację Microsoft Teams można dołączyć lub wykluczyć w ramach instalacji pakietu aplikacji pakietu Office Pro Plus. Ta funkcja działa w przypadku pakietu Office Pro Plus o numerze kompilacji 16.0.11328.20116. W celu ukończenia instalacji użytkownik musi się wylogować, a następnie ponownie zalogować na urządzeniu. W usłudze Intune wystarczy wybrać pozycję **Aplikacje klienckie** > **Aplikacje** > **Dodaj**. Wybierz jeden z typów aplikacji **pakietu Office 365**, a następnie wybierz pozycję **Konfiguruj pakiet aplikacji**.

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="automatically-start-an-app-when-running-multiple-apps-in-kiosk-mode-on-windows-10-and-later-devices----2351390---"></a>Automatyczne uruchamianie aplikacji podczas uruchamiania wielu aplikacji w trybie kiosku na urządzeniach z systemem Windows 10 lub nowszym <!-- 2351390 -->

Na urządzeniach z systemem Windows 10 lub nowszym możesz uruchomić urządzenie w trybie kiosku i uruchamiać wiele aplikacji. W ramach tej aktualizacji dostępne jest ustawienie **Automatyczne uruchamianie** (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **System Windows 10 lub nowszy** dla platformy > **Kiosku** dla typu profilu > **Kiosk z wieloma aplikacjami**). To ustawienie służy do automatycznego uruchamiania aplikacji, gdy użytkownik zaloguje się do urządzenia.

Aby wyświetlić listę i opis wszystkich ustawień kiosku, zobacz [Ustawienia urządzenia z systemem Windows 10 lub nowszym, które ma działać jako kiosk w usłudze Intune](kiosk-settings-windows.md).

Dotyczy: System Windows 10 lub nowszy

#### <a name="operational-logs-also-show-details-on-non-compliant-devices----4063755----"></a>Dzienniki operacyjne pokazują również informacje dotyczące niezgodnych urządzeń <!-- 4063755  -->
Podczas przekierowywania dzienników do funkcji usługi Azure Monitor można kierować również dzienniki operacyjne. W ramach tej aktualizacji dzienniki operacyjne zawierają również informacje dotyczące niezgodnych urządzeń. 

Więcej informacji na temat tej funkcji zawiera artykuł [Send log data to storage, event hubs, or log analytics in Intune](review-logs-using-azure-monitor.md) (Wysyłanie danych dziennika do magazynu, centrów zdarzeń lub analizy dzienników w usłudze Intune).

#### <a name="route-logs-to-azure-monitor-in-more-intune-workloads----3804627---"></a>Przekierowywanie dzienników do usługi Azure Monitor dla dodatkowych obciążeń w usłudze Intune <!-- 3804627 -->
W usłudze Intune można przekierowywać dzienniki inspekcji i operacyjne do centrów zdarzeń, magazynu i analizy dzienników w usłudze Azure Monitor (**Intune** > **Monitorowanie** > **Ustawienia diagnostyki**). Dzięki tej aktualizacji można przekierowywać te dzienniki w dodatkowych obciążeniach usługi Intune, w tym obciążeniach zgodności, konfiguracji, aplikacji klienckich i innych. 

Aby dowiedzieć się więcej na temat przekierowywania dzienników do usługi Azure Monitor, zobacz [Wysyłanie danych dzienników do magazynu, centrów zdarzeń lub analizy dzienników](review-logs-using-azure-monitor.md).

#### <a name="create-and-use-mobility-extensions-on-android-zebra-devices-in-intune----3305880-----"></a>Tworzenie i używanie rozszerzeń dla mobilności na urządzeniach Zebra z systemem Android w usłudze Intune <!-- 3305880   -->
W ramach tej aktualizacji usługa Intune obsługuje konfigurowanie urządzeń Zebra z systemem Android. Ściślej mówiąc, możesz utworzyć profil konfiguracji urządzenia i zastosować ustawienia do urządzeń Zebra z systemem Android przy użyciu profilów rozszerzeń dla mobilności (MX) generowanych przez rozwiązanie StageNow (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Android** dla platformy > **Profil MX (tylko urządzenia Zebra)** dla typu profilu).

Aby uzyskać więcej informacji na temat tej funkcji, zobacz [Korzystanie z urządzeń Zebra i zarządzanie nimi za pomocą rozszerzeń dla mobilności w usłudze Intune](android-zebra-mx-overview.md).

Dotyczy: Android

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="encryption-report-for-windows-10-devices-in-public-preview---2351538---"></a>Raport szyfrowania urządzeń z systemem Windows 10 (w publicznej wersji zapoznawczej)<!-- 2351538 -->  
Nowy [raport szyfrowania (wersja zapoznawcza)](encryption-monitor.md) umożliwia wyświetlenie szczegółów dotyczących stanu szyfrowania urządzeń z systemem Windows 10. Dostępne szczegóły obejmują wersję modułu TPM urządzenia, gotowość szyfrowania i stan szyfrowania, raportowanie błędów i inne informacje.  

#### <a name="access-bitlocker-recovery-keys-from-the-intune-portal-in-public-preview----2351547-----"></a>Dostęp do kluczy odzyskiwania funkcji BitLocker z portalu usługi Intune (w publicznej wersji zapoznawczej) <!-- 2351547   -->  
Teraz możesz używać usługi Intune do [wyświetlania szczegółów](encryption-monitor.md) identyfikatora klucza funkcji BitLocker i kluczy odzyskiwania funkcji BitLocker z usługi Azure Active Directory.

#### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices----3411007---"></a>Obsługa przeglądarki Microsoft Edge dla scenariuszy usługi Intune na urządzeniach z systemem Android i iOS <!-- 3411007 -->
Przeglądarka Microsoft Edge będzie obsługiwać wszystkie te same scenariusze zarządzania co program Intune Managed Browser, dodając ulepszenia środowiska użytkownika końcowego. Funkcje dla przedsiębiorstw przeglądarki Microsoft Edge włączane przez zasady usługi Intune obejmują podwójną tożsamość, integrację zasad ochrony aplikacji, integrację serwera proxy aplikacji platformy Azure oraz zarządzane elementy ulubione i skróty do strony głównej. Aby uzyskać więcej informacji, zobacz [Obsługa przeglądarki Microsoft Edge](app-configuration-managed-browser.md#microsoft-edge-support).

#### <a name="exchange-onlineintune-connector-deprecate-support-for-eas-only-devices---3105122----"></a>Usługa Exchange Online/łącznik usługi Intune wycofują obsługę urządzeń tylko z programem EAS <!--3105122  -->
Konsola usługi Intune nie obsługuje już wyświetlania urządzeń typu „tylko EAS” podłączonych do usługi Exchange Online za pomocą łącznika usługi Intune ani zarządzania tymi urządzeniami. Zamiast tego do masz następujące opcje:
- Zarejestrowanie urządzeń w rozwiązaniu do zarządzania urządzeniami przenośnymi (MDM)
- Używanie zasad rozwiązania Intune App Protection do zarządzania urządzeniami
- Używanie kontrolek programu Exchange zgodnie z opisem w artykule [Clients and mobile in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/clients-and-mobile-in-exchange-online) (Klienci i urządzenia przenośne w usłudze Exchange Online)

### <a name="search-the-all-devices-page-for-an-exact-device-by-using-name---4254930---"></a>Wyszukiwanie dokładnej nazwy urządzenia na stronie Wszystkie urządzenia przy użyciu elementu [name] <!--4254930 -->
Możesz teraz wyszukać dokładną nazwę urządzenia. Przejdź do strony **Intune** > **Urządzenia** > **Wszystkie urządzenia** > w polu wyszukiwania wprowadź nazwę urządzenia ujętą w nawiasy {}, aby wyszukać dokładne dopasowanie. Na przykład **{Urządzenie12345}** .

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="support-for-additional-connectors-on-the-tenant-status-page----3617202----"></a>Obsługa dodatkowych łączników na stronie Stan dzierżawy <!-- 3617202  -->
Na [stronie Stan dzierżawy](tenant-status.md) są teraz wyświetlane informacje o stanie dodatkowych łączników, w tym *zaawansowanej ochrony przed zagrożeniami programu Windows Defender* (ATP) i innych łączników Mobile Threat Defense.

### <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach

#### <a name="granting-intune-read-only-access-to-some-azure-active-directory-roles----3637917----"></a>Udzielenie dostępu tylko do odczytu do usługi Intune niektórym rolom usługi Azure Active Directory <!-- 3637917  -->
Dostęp tylko do odczytu do usługi Intune został udzielony poniższym rolom usługi Azure AD. Uprawnienia przyznane przy użyciu ról usługi Azure AD zastępują uprawnienia przyznane przy użyciu kontroli dostępu na podstawie ról (RBAC) usługi Intune.

Dostęp tylko do odczytu do danych inspekcji usługi Intune:

- Administrator zgodności
- Administrator danych zgodności

Dostęp tylko do odczytu do wszystkich danych usługi Intune:

- Administrator zabezpieczeń
- Operator zabezpieczeń
- Czytelnik zabezpieczeń

Aby uzyskać więcej informacji, zobacz [Kontrola dostępu na podstawie ról](role-based-access-control.md).

#### <a name="scope-tags-for-ios-app-provisioning-profiles---2934430-----"></a>Tagi zakresu dla profilów aprowizacji aplikacji systemu iOS <!--2934430   -->
Możesz dodać tag zakresu do profilu aprowizacji aplikacji systemu iOS, tak aby tylko osoby z rolami przypisanymi do tego tagu zakresu miały dostęp do profilu aprowizacji aplikacji systemu iOS. Aby uzyskać więcej informacji, zobacz [Use RBAC and scope tags](scope-tags.md) (Używanie kontroli RBAC i tagów zakresu).

#### <a name="scope-tags-for-app-configuration-policies---2371891-----"></a>Tagi zakresu dla zasad konfiguracji aplikacji <!--2371891   -->
Możesz dodać tag zakresu do zasad konfiguracji aplikacji, tak aby tylko osoby z rolami przypisanymi do tego tagu zakresu miały dostęp do zasad konfiguracji aplikacji. Zasady konfiguracji aplikacji mogą być przeznaczone tylko dla lub skojarzone tylko z aplikacjami przypisanymi do tego samego tagu zakresu. Aby uzyskać więcej informacji, zobacz [Use RBAC and scope tags](scope-tags.md) (Używanie kontroli RBAC i tagów zakresu).

### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices----3411007---"></a>Obsługa przeglądarki Microsoft Edge dla scenariuszy usługi Intune na urządzeniach z systemem Android i iOS <!-- 3411007 -->
Przeglądarka Microsoft Edge będzie obsługiwać wszystkie te same scenariusze zarządzania, co program Intune Managed Browser, dodając ulepszenia środowiska użytkownika końcowego. Funkcje dla przedsiębiorstw przeglądarki Microsoft Edge włączane przez zasady usługi Intune obejmują podwójną tożsamość, integrację zasad ochrony aplikacji, integrację serwera proxy aplikacji platformy Azure oraz zarządzane elementy ulubione i skróty do strony głównej. Aby uzyskać więcej informacji, zobacz [Obsługa przeglądarki Microsoft Edge](app-configuration-managed-browser.md#microsoft-edge-support).

## <a name="week-of-february-25-2019"></a>Tydzień od 25 lutego 2019 r.

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="intune-powershell-module----951068----"></a>Moduł programu Intune PowerShell <!-- 951068  -->
Moduł programu Intune PowerShell, który zapewnia obsługę interfejsu API usługi Intune za pośrednictwem programu Microsoft Graph, jest teraz dostępny w [Galerii programu Microsoft PowerShell](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1902.1.10).

- [Szczegółowe informacje na temat sposobu korzystania z tego modułu](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/README.md)
- [Przykłady scenariuszy z użyciem tego modułu](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/Samples/README.md)

#### <a name="improved-support-for-delivery-optimization----3183757----"></a>Ulepszona obsługa optymalizacji dostarczania  <!--3183757  -->
Rozszerzyliśmy obsługę konfigurowania optymalizacji dostarczania w usłudze Intune. Teraz możesz skonfigurować rozszerzoną listę [ustawień optymalizacji dostarczania](delivery-optimization-settings.md) i zastosować ją do urządzeń z bezpośrednio z poziomu konsoli usługi Intune.


## <a name="week-of-february-18-2019"></a>Tydzień od 18 lutego 2019 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="intune-will-leverage-google-play-protect-apis-on-android-devices----2577355-----"></a>Usługa Intune będzie korzystać z interfejsów API usługi Google Play Protect na urządzeniach z systemem Android <!-- 2577355   -->
Niektórzy administratorzy IT muszą radzić sobie ze środowiskiem BYOD, w którym użytkownicy końcowi mogą rootować swoje telefony komórkowe lub wykonywać ich jailbreak. To zachowanie, choć czasem podejmowane bez złych zamiarów, powoduje obejście wielu zasad usługi Intune określonych w celu ochrony danych organizacji na urządzeniach użytkowników końcowych. W związku z tym usługa Intune udostępnia funkcję wykrywania rootingu i jailbreaku dla zarówno zarejestrowanych, jak i niezarejestrowanych urządzeń. W tej wersji usługa Intune wykorzysta interfejsy API usługi Google Play do dodania sprawdzeń dotyczących wykrywania rootingu dla urządzeń niezarejestrowanych. Mimo że firma Google nie udostępnia wszystkich wykonywanych sprawdzeń dotyczących rootingu, oczekujemy, że te interfejsy API wykrywają użytkowników, którzy wykonali rooting swojego urządzenia z dowolnej przyczyny — od dostosowania urządzenia do umożliwienia pobierania nowszych aktualizacji systemu operacyjnego na starszych urządzeniach. Następnie można zablokować dostęp tych użytkowników do danych firmowych lub wyczyścić ich konta firmowe z aplikacji obsługujących zasady. Dodatkowo administratorzy IT otrzymają kilka aktualizacji raportowania w bloku Intune App Protection — raport „Użytkownicy z flagą” pokazuje użytkowników wykrytych za pomocą skanowania przy użyciu interfejsu API SafetyNet usługi Google Play Protect, a raport „Potencjalnie szkodliwe aplikacje” pokazuje aplikacje wykryte za pomocą skanowania przy użyciu interfejsu API Verify Apps firmy Google. Ta funkcja jest dostępna w systemie Android.

#### <a name="win32-app-information-available-in-troubleshooting-blade----2617342-----"></a>Informacje o aplikacji Win32 dostępne w bloku Rozwiązywanie problemów <!-- 2617342   -->
Masz teraz możliwość zbierania plików dziennika błędów dla instalacji aplikacji Win32 w bloku **Rozwiązywanie problemów** aplikacji usługi Intune. Aby uzyskać więcej informacji na temat rozwiązywania problemów z instalacją aplikacji, zobacz [Rozwiązywanie problemów z instalacją aplikacji](troubleshoot-app-install.md) i [Rozwiązywanie problemów z aplikacjami Win32](apps-win32-app-management.md#troubleshoot-win32-app-issues).

#### <a name="app-status-details-for-ios-apps----3761235-----"></a>Szczegóły stanu aplikacji systemu iOS <!-- 3761235   -->
Wprowadzono nowe komunikaty o błędzie dla instalacji aplikacji związane z następującymi sytuacjami:
- Błąd aplikacji programu VPP podczas instalowania na współużytkowanym urządzeniu iPad
- Błąd, jeśli sklep App Store jest wyłączony
- Błąd szukania licencji programu VPP dla aplikacji
- Błąd instalacji aplikacji systemowych za pomocą dostawcy rozwiązania MDM
- Błąd instalacji aplikacji, gdy urządzenie jest w trybie zgubienia lub kiosku
- Błąd instalacji aplikacji, gdy użytkownik nie jest zalogowany do sklepu App Store

W usłudze Intune wybierz pozycję **Aplikacje klienckie** > **Aplikacje** > „Nazwa aplikacji” > **Stan instalacji urządzenia**. Nowe komunikaty o błędzie będą dostępne w kolumnie **Szczegóły stanu**.

#### <a name="new-app-categories-screen-in-the-company-portal-app-for-windows-10---3834780----"></a>Nowy ekran Kategorie aplikacji w aplikacji Portal firmy dla systemu Windows 10<!-- 3834780  -->
Dodano nowy ekran o nazwie **Kategorie aplikacji** w celu poprawy środowiska przeglądania i wyboru aplikacji w aplikacji Portal firmy dla systemu Windows 10. Użytkownicy będą teraz widzieli aplikacje posortowane w ramach kategorii, takich jak **Polecane**, **Edukacja** i **Produktywność**. Ta zmiana pojawia się w aplikacji Portal firmy w wersji 10.3.3451.0 i nowszych. Aby wyświetlić nowy ekran, zobacz [co nowego w interfejsie użytkownika aplikacji](https://docs.microsoft.com/intune/whats-new-app-ui). Aby uzyskać więcej informacji na temat aplikacji w Portalu firmy, zobacz [Instalowanie i udostępnianie aplikacji na urządzeniu](/intune-user-help/install-apps-cpapp-windows).  

#### <a name="power-bi-compliance-app----1455231-doc-work-item---"></a>Aplikacja Power BI Compliance <!-- 1455231 doc-work-item -->
Można uzyskiwać dostęp do magazynu danych usługi Intune w usłudze Power BI Online przy użyciu aplikacji [Intune Compliance (Data Warehouse)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp). Za pomocą tej aplikacji usługi Power BI możesz teraz uzyskiwać dostęp do wstępnie utworzonych raportów i udostępniać je bez żadnej konfiguracji i bez opuszczania przeglądarki internetowej. Aby uzyskać więcej informacji, zobacz [Dziennik zmian — aplikacja Power BI Compliance](reports-changelog.md#power-bi-compliance-app).


### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="powershell-scripts-can-run-in-a-64-bit-host-on-64-bit-devices----1862675-----"></a>Skrypty programu PowerShell można uruchomić w ramach 64-bitowego hosta na urządzeniach 64-bitowych <!-- 1862675   -->
Po dodaniu skryptu programu PowerShell do profilu konfiguracji urządzenia skrypt jest zawsze wykonywany jako 32-bitowy nawet w 64-bitowych systemach operacyjnych. Dzięki tej aktualizacji administrator może uruchomić skrypt w ramach 64-bitowego hosta programu PowerShell na urządzeniach 64-bitowych (**Konfiguracja urządzenia** > **Skrypty PowerShell** > **Dodaj** > **Konfiguruj** > **Uruchom skrypt w 64-bitowym hoście programu PowerShell**).

Aby uzyskać więcej informacji na temat korzystania z programu PowerShell, zobacz [Skrypty programu PowerShell w usłudze Intune](intune-management-extension.md).

Dotyczy: System Windows 10 lub nowszy

#### <a name="macos-users-are-prompted-to-update-their-password----1873216---"></a>Użytkownicy systemu macOS otrzymują monit o zaktualizowanie swojego hasła <!-- 1873216 -->
Usługa Intune wymusza ustawienie **ChangeAtNextAuth** na urządzeniach z systemem macOS. To ustawienie ma wpływ na użytkowników końcowych i urządzenia, które mają zasady zgodności haseł lub profile haseł w ograniczeniach dotyczących urządzenia. Użytkownicy końcowi są monitowani raz o zaktualizowanie swojego hasła. Ten monit jest wyświetlany zawsze, gdy użytkownik po raz pierwszy uruchamia zadanie, które wymaga uwierzytelniania, na przykład logowanie się na urządzeniu. Użytkownicy mogą również otrzymywać monit o zaktualizowanie swojego hasła podczas wykonywania czegokolwiek, co wymaga uprawnień administracyjnych, na przykład podczas żądania dostępu do pęku kluczy. 

Wszelkie zmiany nowych lub istniejących zasad haseł przez administratora powodują ponowne monitowanie użytkowników końcowych o zaktualizowanie swojego hasła.

Dotyczy:  
macOS

#### <a name="assign-scep-certificates-to-a-userless-macos-device-----2340521----"></a>Przypisywanie certyfikatów SCEP do urządzenia z systemem macOS bez użytkowników  <!-- 2340521  -->
Możesz przypisać certyfikaty protokołu Simple Certificate Enrollment Protocol (SCEP) przy użyciu atrybutów urządzenia do urządzeń z systemem macOS, w tym urządzeń bez koligacji użytkownika, i skojarzyć profil certyfikatu z profilami sieci Wi-Fi lub sieci VPN. Powoduje rozszerzenie obsługi [przypisywania certyfikatów protokołu SCEP na urządzeniach z lub bez koligacji użytkownika](certificates-scep-configure.md#create-a-scep-certificate-profile) z systemem Windows, iOS i Android.  Ta aktualizacja dodaje opcję wyboru typu certyfikatu *Urządzenie* podczas konfigurowania profilu certyfikatu protokołu SCEP dla systemu macOS.

Dotyczy: 
- macOS

#### <a name="intune-conditional-access-ui-update------2432313-----"></a>Aktualizacja interfejsu użytkownika dostępu warunkowego usługi Intune   <!-- 2432313   -->
Wprowadziliśmy ulepszenia interfejsu użytkownika dla dostępu warunkowego w konsoli usługi Intune. Należą do nich następujące elementy:
-  Zastąpienie bloku *Dostęp warunkowy* usługi Intune blokiem z usługi Azure Active Directory. Dzięki temu będziesz mieć dostęp do pełnego zakresu ustawień i konfiguracji dotyczących [dostępu warunkowego](conditional-access.md) (który pozostaje technologią usługi Azure AD) z poziomu konsoli usługi Intune. 
- Nazwa bloku *Dostęp lokalny* została zmieniona na *Dostęp do programu Exchange* i przenieśliśmy konfigurację *łącznika usługi Exchange* do tego bloku.  Ta zmiana umieszcza w jednym miejscu [konfigurowanie i monitorowanie szczegółów dotyczących usługi Exchange online i lokalnej](exchange-connector-install.md).  

#### <a name="kiosk-browser-and-microsoft-edge-browser-apps-can-run-on-windows-10-devices-in-kiosk-mode----2935135-----"></a>Aplikacje Kiosk Browser i Microsoft Edge mogą pracować na urządzeniach z systemem Windows 10 w trybie kiosku <!-- 2935135   -->
Urządzenia z systemem Windows 10 pracujące w trybie kiosku umożliwiają uruchamianie jednej lub wielu aplikacji. Ta aktualizacja obejmuje kilka zmian dotyczących korzystania z aplikacji w trybie kiosku, w tym:

- Możliwość uruchamiania przeglądarek Microsoft Edge i Kiosk Browser jako aplikacji na urządzeniu kiosku (**Konfiguracja urządzenia** > **Profile** > **Nowy profil** >  **System Windows 10 i nowsze** dla platformy > **Kiosk** dla typu profilu).
- Dostępne są nowe funkcje i ustawienia służące do zezwalania na nie lub ich ograniczania (**Konfiguracja urządzenia** > **Profile** > **Nowy profil**  > **System Windows 10 i nowsze**dla platformy > **Ograniczenia dotyczące urządzeń** dla typu profilu), w tym:

  - Przeglądarka Microsoft Edge:
  - Użyj trybu kiosku przeglądarki Microsoft Edge
  - Odśwież przeglądarkę po czasie bezczynności

 - Ulubione i wyszukiwanie:
  - Zezwalaj na zmiany aparatu wyszukiwania

Aby uzyskać listę tych ustawień zobacz:

- [Ustawienia urządzenia z systemem Windows 10 lub nowszym, które ma działać jako kiosk](kiosk-settings-windows.md)
- [Ograniczenia urządzeń z przeglądarką Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser)
- [Ograniczenia urządzeń dotyczące ulubionych i wyszukiwania](device-restrictions-windows-10.md##favorites-and-search)

Dotyczy: System Windows 10 lub nowszy

#### <a name="new-device-restriction-settings-for-ios-and-macos-devices----3448774-----"></a>Nowe ustawienia ograniczeń urządzeń z systemami iOS i macOS <!-- 3448774   -->
Istnieje możliwość ograniczenia niektórych ustawień i funkcji na urządzeniach z systemami iOS i macOS (**Konfiguracja urządzenia** > **Profile** > **Nowy profil** >  **iOS** lub **macOS** dla platformy > **Ograniczenia urządzenia** dla typu profilu). Ta aktualizacja dodaje kolejne funkcje i ustawienia, które można kontrolować, w tym ustawianie czasu korzystania z urządzenia, zmienianie ustawień karty eSIM, planów komórkowych i nie tylko na urządzeniach z systemem iOS. Ponadto umożliwia opóźnianie widoczności aktualizacji oprogramowania dla użytkownika i blokowanie buforowania zawartości na urządzeniach z systemem macOS. 

Aby wyświetlić funkcje i ustawienia, które można ograniczyć, zobacz:

- [Ustawienia ograniczeń dotyczących urządzeń z systemem iOS](device-restrictions-ios.md)
- [Ustawienia ograniczeń dotyczących urządzeń z systemem macOS](device-restrictions-macos.md)

Dotyczy:

- iOS
- macOS

#### <a name="kiosk-devices-are-now-called-dedicated-devices-on-android-enterprise-devices----3598402-----"></a>Urządzenia typu „kiosk” są teraz nazywane „urządzeniami dedykowanymi” na urządzeniach z rozwiązaniem Android Enterprise <!-- 3598402   -->
W celu dopasowania do terminologii systemu Android określenie **kiosk** zostało zmienione na **urządzenia dedykowane** dla urządzeń z rozwiązaniem Android Enterprise (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > ** Android Enterprise jako platforma > **Tylko właściciel urządzenia** > **Ograniczenia dotyczące urządzeń** > **Urządzenia dedykowane**).

Aby zobaczyć dostępne ustawienia, przejdź do artykułu [Ustawienia urządzeń w celu zezwolenia na funkcje lub ich ograniczenie](device-restrictions-android-for-work.md#dedicated-device-settings).

Dotyczy:  
Android Enterprise

#### <a name="safari-and-delaying-user-software-update-visibility-ios-settings-are-moving-in-the-intune-ui----3640850-3803313-----"></a>Ustawienia systemu iOS dotyczące przeglądarki Safari i opóźniania widoczności aktualizacji oprogramowania użytkownika są przenoszone w interfejsie użytkownika usługi Intune <!-- 3640850, 3803313   -->
W przypadku urządzeń z systemem iOS można skonfigurować ustawienia przeglądarki Safari i aktualizacje oprogramowania. W ramach tej aktualizacji wymienione ustawienia są przenoszone do różnych części interfejsu użytkownika usługi Intune:

- Ustawienia przeglądarki Safari zostały przeniesione z pozycji **Safari**(**Konfiguracja urządzenia** > **Profile** > **Nowy profil** > **iOS** dla platformy > **Ograniczenia urządzenia** dla typu profilu) do pozycji **[Aplikacje wbudowane](device-restrictions-ios.md#built-in-apps)** .
- Ustawienie **Opóźnianie widoczności aktualizacji oprogramowania użytkownika dla urządzeń z systemem iOS w trybie nadzorowanym** (**Aktualizacje oprogramowania** > **Aktualizuj zasady dla systemu iOS**) jest przenoszone do obszaru **Ograniczenia urządzeń** >  **[Ogólne](device-restrictions-ios.md#general)** .  Aby uzyskać szczegółowe informacje o wpływie na istniejące zasady, zobacz [aktualizacje oprogramowania systemu iOS](software-updates-ios.md#configure-the-policy). 

Aby uzyskać listę ustawień, zobacz:

- [Ograniczenia dotyczące urządzeń z systemem iOS](device-restrictions-ios.md) 
- [Aktualizacje oprogramowania systemu iOS](software-updates-ios.md)

Ta funkcja ma zastosowanie do: 

- iOS

#### <a name="enabling-restrictions-in-the-device-settings-is-renamed-to-screen-time-on-ios-devices----3699164-----"></a>Nazwa opcji Włączanie ograniczeń w ustawieniach urządzenia zostanie zmieniona na Czas korzystania z urządzenia na urządzeniach z systemem iOS <!-- 3699164   -->
Istnieje możliwość skonfigurowania pozycji **Włączanie ograniczeń w ustawieniach urządzenia** na urządzeniach nadzorowanych z systemem iOS (**Konfiguracja urządzenia** > **Profile** > **Nowy profil** > **iOS** dla platformy > **Ograniczenia urządzenia** dla typu profilu > **Ogólne**). W ramach tej aktualizacji nazwa tego ustawienia zostanie zmieniona na **Czas korzystania z urządzenia (tylko nadzorowane)** . 

Zachowanie jest takie samo. W szczególności: 

- System iOS 11.4.1 i starsze: opcja **Blokuj** uniemożliwia użytkownikom końcowym ustawianie własnych ograniczeń w ustawieniach urządzenia. 
- System iOS 12.0 i nowsze: opcja **Blokuj** uniemożliwia użytkownikom końcowym ustawianie pozycji **Czas korzystania z urządzenia** w ustawieniach urządzenia, w tym ograniczeń dotyczących zawartości i prywatności. Na urządzeniach uaktualnionych do systemu iOS 12.0 karta ograniczeń nie będzie już widoczna w ustawieniach urządzenia. Te ustawienia znajdują się teraz w obszarze **Czas korzystania z urządzenia**. 

Aby uzyskać listę ustawień, zobacz [Ograniczenia urządzeń z systemem iOS](device-restrictions-ios.md#general).

Dotyczy: 
- iOS


### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="rename-an-enrolled-windows-device----1911112----"></a>Zmiana nazwy zarejestrowanego urządzenia z systemem Windows <!-- 1911112  -->
Teraz można zmienić nazwę zarejestrowanego urządzenia z systemem Windows 10 (RS4 lub nowszym). Aby to zrobić, wybierz pozycje **Intune** > **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Zmień nazwę urządzenia**. Ta funkcja nie obsługuje obecnie zmiany nazw urządzeń z systemem Windows dołączonych hybrydowo do usługi Azure AD.

#### <a name="auto-assign-scope-tags-to-resources-created-by-an-admin-with-that-scope----3173823----"></a>Automatyczne przypisywanie tagów zakresu do zasobów utworzonych przez administratora przy użyciu danego zakresu <!-- 3173823  -->
Gdy administrator utworzy zasób, wszelkie tagi zakresu przypisane do administratora zostaną automatycznie przypisane do nowych zasobów.

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="failed-enrollment-report-moves-to-the-device-enrollment-blade----3560202----"></a>Raport rejestracji zakończonych niepowodzeniem został przeniesiony do bloku Rejestrowanie urządzeń <!-- 3560202  -->
Raport **Rejestracje zakończone niepowodzeniem** został przeniesiony do sekcji **Monitorowanie** bloku **Rejestrowanie urządzeń**. Dodano również dwie nowe kolumny (Metoda rejestracji i Wersja systemu operacyjnego).

#### <a name="company-portal-abandonment-report-renamed-to-incomplete-user-enrollments---3815076-eemiss---"></a>Nazwa raportu porzucania portalu firmy została zmieniona na Niekompletne rejestracje użytkownika <!--3815076 eemiss -->
Nazwa raportu **Porzucanie portalu firmy** została zmieniona na **Niekompletne rejestracje użytkownika**.


<!-- ########################## -->
## <a name="week-of-february-4-2019"></a>Tydzień od 4 lutego 2019 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="intune-macos-company-portal-dark-mode----3300524----"></a>Tryb ciemny Portalu firmy usługi Intune w systemie macOS <!-- 3300524  -->
Portal firmy usługi Intune w systemie macOS obsługuje teraz tryb ciemny systemu macOS. Po włączeniu trybu ciemnego na urządzeniu z systemem macOS w wersji 10.14 lub nowszej aplikacja Portal firmy dostosuje swój wygląd do kolorów używanych w tym trybie.

<!-- ########################## -->
## <a name="week-of-january-21-2019"></a>Tydzień od 21 stycznia 2019 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="toast-notifications-for-win32-apps----3136566-----"></a>Wyskakujące powiadomienia dla aplikacji Win32 <!-- 3136566   -->
Można pominąć wyświetlanie wyskakujących powiadomień dla użytkownika końcowego podczas przypisywania aplikacji. W usłudze Intune wybierz kolejno pozycje **Aplikacje klienckie** > **Aplikacje** > wybierz aplikację > **Przypisania** > **Uwzględnij grupy**. 

#### <a name="intune-app-protection-policies-ui-update----3251427----"></a>Aktualizacja interfejsu użytkownika zasad ochrony aplikacji usługi Intune <!-- 3251427  -->
Zmieniliśmy etykiety ustawień i przycisków funkcji ochrony aplikacji usługi Intune, aby ułatwić ich zrozumienie. Oto niektóre zmiany:  
- Kontrolki **tak** / **nie** zostały zmienione głównie na kontrolki **blokuj** / **zezwalaj** oraz  **wyłącz** / **włącz**. Etykiety również zostały aktualizowane.  
- Format ustawień został zmieniony, dzięki czemu ustawienie i jego etykieta znajdują się obok siebie w kontrolce, umożliwiając lepszą nawigację.   

Ustawienia domyślne i liczba ustawień pozostają takie same, lecz ta zmiana pozwala użytkownikowi lepiej zrozumieć i wykorzystać ustawienia w celu stosowania wybranych zasad ochrony aplikacji, a także łatwiej nawigować po nich. Aby uzyskać informacje, zobacz [Ustawienia systemu iOS](app-protection-policy-settings-ios.md) i [Ustawienia systemu Android](app-protection-policy-settings-android.md).

### <a name="additional-settings-for-outlook----3301182----"></a>Dodatkowe ustawienia dla programu Outlook <!-- 3301182  -->
Teraz za pomocą usługi Intune można skonfigurować następujące dodatkowe ustawienia dla programu Outlook w systemach iOS i Android:

- Zezwalanie na użycie wyłącznie kont służbowych w programie Outlook dla systemów iOS i Android
- Wdrażanie nowoczesnego uwierzytelniania dla usługi Office 365 oraz kont lokalnych nowoczesnego uwierzytelniania hybrydowego
- Używanie wartości `SAMAccountName` dla pola nazwy użytkownika w profilu poczty e-mail, gdy jest wybrane uwierzytelnianie podstawowe
- Zezwalanie na zapisywanie kontaktów
- Konfigurowanie porad dotyczących poczty adresatów zewnętrznych
- Konfigurowanie **priorytetowej skrzynki odbiorczej**
- Wymaganie danych biometrycznych w celu uzyskania dostępu do programu Outlook dla systemu iOS
- Blokowanie obrazów zewnętrznych

> [!NOTE]
> Jeśli do zarządzania dostępem do tożsamości firmowych są używane zasady rozwiązania Intune App Protection, warto rozważyć wyłączenie **wymagania danych biometrycznych**. Aby uzyskać więcej informacji, zobacz **Wymagaj poświadczeń firmowych w celu udzielenia dostępu** dla [ustawień dotyczących dostępu systemu iOS](app-protection-policy-settings-ios.md#access-requirements) i [ustawień dotyczących dostępu systemu Android](app-protection-policy-settings-android.md#access-requirements).

Aby uzyskać więcej informacji, zobacz [ustawienia konfiguracji programu Microsoft Outlook](app-configuration-policies-outlook.md).

#### <a name="delete-android-enterprise-apps----1352553---"></a>Usuwanie aplikacji systemu Android Enterprise <!-- 1352553 -->
Możesz usuwać aplikacje z zarządzanego sklepu Google Play z poziomu usługi Microsoft Intune. Aby usunąć aplikację z zarządzanego sklepu Google Play, otwórz usługę Microsoft Intune w witrynie Azure Portal i wybierz kolejno pozycje **Aplikacje klienckie** > **Aplikacje**. Na liście aplikacji wybierz wielokropek (...) po prawej stronie aplikacji z zarządzanego sklepu Google Play, a następnie wybierz pozycję **Usuń** z wyświetlonej listy. Po usunięciu aplikacji zarządzanej ze sklepu Google Play z listy aplikacji ta aplikacja zarządzana stanie się automatycznie aplikacją niezatwierdzoną.

#### <a name="managed-google-play-app-type----1352580---"></a>Typ aplikacji zarządzanej ze sklepu Google Play <!-- 1352580 -->
Dzięki zastosowaniu typów aplikacji **zarządzanych ze sklepu Google Play** będzie można wybiórczo dodawać [aplikacje zarządzane ze sklepu Google Play](https://play.google.com/work/search?q=microsoft&c=apps) do usługi Intune. Administratorzy usługi Intune mogą przeglądać, wyszukiwać, zatwierdzać, synchronizować i przypisywać zatwierdzone aplikacje zarządzane ze sklepu Google Play z poziomu usługi Intune.  Nie jest już konieczne przechodzenie do zarządzanej konsoli Google Play i dokonywanie ponownego uwierzytelniania.  W usłudze Intune wystarczy wybrać pozycję **Aplikacje klienckie** > **Aplikacje** > **Dodaj**. Natomiast na liście **Typ aplikacji** będzie trzeba wybrać pozycję **Zarządzany sklep Google Play**.

### <a name="default-android-pin-keyboard----3802457---"></a>Domyślna klawiatura systemu Android dla numeru PIN <!-- 3802457 -->
Użytkownicy końcowi, którzy ustawili numer PIN dla zasad ochrony aplikacji usługi Intune na swoich urządzeniach z systemem Android przy użyciu typu „Numeryczne”, będą teraz widzieć domyślną klawiaturę systemu Android zamiast stałego interfejsu użytkownika klawiatury systemu Android zaprojektowanego wcześniej. Tę zmianę wprowadzono w celu wprowadzenia spójności podczas korzystania z klawiatur domyślnych w systemach Android i iOS dla typów numeru PIN „Numeryczne” i/lub „Kod dostępu”. Aby uzyskać więcej informacji na temat ustawień dostępu użytkownika końcowego w systemie Android, takich dotyczących numeru PIN zasad ochrony aplikacji, zobacz [Wymagania dostępu dla systemu Android](app-protection-policy-settings-android.md#access-requirements).

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="use-microsoft-recommended-settings-with-security-baselines-public-preview----2055484-----"></a>Używanie ustawień zalecanych przez firmę Microsoft z punktami odniesienia zabezpieczeń (publiczna wersja zapoznawcza) <!-- 2055484   -->

Usługa Intune umożliwia integrację z innymi usługami koncentrującymi się na zabezpieczeniach, w tym z usługą Windows Defender ATP i usługą Office 365 ATP. Klienci pytają o typową strategię i spójny zestaw kompleksowych przepływów pracy zabezpieczeń w usługach Microsoft 365. Naszym celem jest dopasowanie strategii w celu utworzenia rozwiązań, które łączą operacje zabezpieczeń i typowe zadania administratora. W usłudze Intune staramy się osiągnąć ten cel, publikując zestaw „punktów odniesienia zabezpieczeń” zalecanych przez firmę Microsoft (**Intune** > **Punkty odniesienia zabezpieczeń**).  Administrator może tworzyć zasady zabezpieczeń bezpośrednio z tych punktów odniesienia, a następnie wdrażać je dla użytkowników. Możesz również dostosować rekomendacje dotyczące najlepszych rozwiązań do potrzeb organizacji. Usługa Intune zapewnia, że urządzenia pozostają w zgodności z tymi punktami odniesienia, i powiadamia administratorów użytkowników lub urządzeń, które nie są zgodne.

Ta funkcja jest dostępna w publicznej wersji zapoznawczej, więc wszystkie profile utworzone teraz nie zostaną przeniesione do ogólnie dostępnych szablonów punktów odniesienia zabezpieczeń. Nie należy planować używania szablonów dostępnych w wersji zapoznawczej w środowisku produkcyjnym.

Aby dowiedzieć się więcej na temat punktów odniesienia zabezpieczeń, zobacz temat [Create a Windows 10 security baseline in Intune](security-baselines-monitor.md) (Tworzenie punktu odniesienia zabezpieczeń systemu Windows 10 w usłudze Intune).

Ta funkcja ma zastosowanie do: System Windows 10 lub nowszy

#### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379-----"></a>Użytkownicy inni niż administratorzy mogą włączyć funkcję BitLocker na urządzeniach z systemem Windows 10 dołączonych do usługi Azure AD<!-- 2147379   -->
Włączenie ustawień funkcji BitLocker na urządzeniach z systemem Windows 10 (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** jako platforma > **Endpoint Protection** jako typ profilu > **Szyfrowanie systemu Windows**) oznacza dodanie ustawień funkcji BitLocker. 

Ta aktualizacja obejmuje nowe ustawienie funkcji BitLocker, które zezwala użytkownikom standardowym (innym niż administratorzy) na włączanie szyfrowania. 

Aby wyświetlić te ustawienia, zobacz [Ustawienia programu Endpoint Protection dla systemu Windows 10](endpoint-protection-windows-10.md#windows-encryption).

#### <a name="check-for-configuration-manager-compliance----2192052--eepublished----"></a>Sprawdzanie zgodności w programie Configuration Manager <!-- 2192052  eepublished  -->
Ta aktualizacja zawiera nowe ustawienie zgodności programu System Center Configuration Manager (**Zgodność urządzenia** > **Zasady** > **Utwórz zasady** > **System Windows 10 i nowsze** > **Zgodność z programem Configuration Manager**). Program Configuration Manager wysyła sygnały zgodności do usługi Intune. Przy użyciu tego ustawienia można wymagać, aby wszystkie sygnały programu Configuration Manager zwracały stan „zgodne”.

Na przykład można wymagać, aby na urządzeniach były zainstalowane wszystkie aktualizacje oprogramowania. W programie Configuration Manager to wymaganie ma stan „Zainstalowano”. Jeśli jakiekolwiek programy na urządzeniu mają nieznany stan, to urządzenie jest niezgodne w usłudze Intune.

To ustawienie opisano w sekcji [Zgodność z programem Configuration Manager](compliance-policy-create-windows.md#configuration-manager-compliance).

Dotyczy: System Windows 10 lub nowszy

#### <a name="customize-wallpaper-on-supervised-ios-devices-using-a-device-configuration-profile----2809324-----"></a>Dostosowywanie tapety na urządzeniach nadzorowanych z systemem iOS przy użyciu profilu konfiguracji urządzenia <!-- 2809324   -->
Podczas tworzenia profilu konfiguracji urządzenia dla urządzeń z systemem iOS można dostosowywać niektóre funkcje (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > **iOS** dla platformy > **Funkcje urządzenia** dla typu profilu). Ta aktualizacja obejmuje nowe ustawienia obszaru **Tapeta**, które umożliwiają administratorowi użycie obrazu PNG, JPG lub JPEG na ekranie głównym lub ekranie blokady. Te ustawienia dotyczące tapety mają zastosowanie tylko na urządzeniach nadzorowanych. 

Listę tych ustawień można znaleźć w temacie [iOS device feature settings](ios-device-features-settings.md) (Ustawienia funkcji urządzeń z systemem iOS).

#### <a name="windows-10-kiosk-is-generally-available----3594661----"></a>Kiosk systemu Windows 10 jest ogólnie dostępny <!-- 3594661  -->
W tej aktualizacji funkcja kiosku jest udostępniana ogólnie na urządzeniach z systemem Windows 10 i nowszych. Aby zapoznać się ze wszystkimi ustawieniami, które można dodać i skonfigurować, zobacz temat [Ustawienia kiosku dla systemu Windows 10 (i nowszego)](kiosk-settings.md).

#### <a name="contact-sharing-via-bluetooth-is-removed-in-device-restrictions--device-owner-for-android-enterprise----3598396-----"></a>Udostępnianie kontaktów za pośrednictwem połączenia Bluetooth zostało usunięte z obszaru Ograniczenia dotyczące urządzeń > Właściciel urządzenia w systemie Android Enterprise <!-- 3598396   -->
Podczas tworzenia profilu ograniczeń dotyczących urządzeń z systemem Android Enterprise widoczne jest ustawienie **Udostępnianie kontaktów za pośrednictwem połączenia Bluetooth**. W ramach tej aktualizacji ustawienie **Udostępnianie kontaktów za pośrednictwem połączenia Bluetooth** zostało usunięte (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > **Android Enterprise** dla platformy > **Ograniczenia dotyczące urządzeń > Właściciel urządzenia** dla typu profilu > **Ogólne**). 

Ustawienie **Udostępnianie kontaktów za pośrednictwem połączenia Bluetooth** nie jest obsługiwane w przypadku zarządzania właścicielami urządzeń w systemie Android Enterprise. Po usunięciu tego ustawienia nie będzie ono miało wpływu na jakiekolwiek urządzenia czy dzierżawy, nawet jeśli to ustawienie zostało włączone i skonfigurowane w środowisku.

Aby wyświetlić aktualną listę ustawień, zobacz [Ustawienia urządzeń z systemem Android Enterprise w celu zezwolenia na funkcje lub ich ograniczenia](device-restrictions-android-for-work.md).

Dotyczy: właściciel urządzenia z systemem Android Enterprise

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="selective-wipe-support-for-wip-without-enrollment-devices----1434452---"></a>Obsługa selektywnego czyszczenia danych dla urządzeń usługi WIP bez rejestracji <!-- 1434452 -->
Usługa Windows Information Protection Without Enrollment (WIP-WE) umożliwia klientom ochronę danych firmowych na urządzeniach z systemem Windows 10 bez konieczności pełnej rejestracji w rozwiązaniu MDM. Gdy dokumenty są chronione za pomocą zasad funkcji WIP-WE, chronione dane mogą być selektywnie czyszczone przez administratora usługi Intune. Wybierając użytkownika i urządzenie oraz wysyłając żądanie czyszczenia, wszystkie dane chronione za pomocą zasad funkcji WIP-WE staną się bezużyteczne. Z usługi Intune w witrynie Azure Portal wybierz pozycję **Aplikacja mobilna** > **Selektywne czyszczenie aplikacji**.

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="new-operational-logs-and-ability-to-send-logs-to-azure-monitor-services----3762211----"></a>Nowe dzienniki operacyjne i możliwość wysyłania dzienników do usług Azure Monitor <!-- 3762211  -->
Usługa Intune ma wbudowaną funkcję rejestrowania inspekcji, która śledzi zdarzenia w miarę wprowadzania zmian. Ta aktualizacja obejmuje nowe funkcje rejestrowania, w tym: 
- Dzienniki operacyjne (wersja zapoznawcza), które pokazują szczegóły użytkowników i zarejestrowanych urządzeń, łącznie z próbami udanymi i nieudanymi.
- Dzienniki inspekcji i dzienniki operacyjne można wysyłać do usługi Azure Monitor, łącznie z informacjami na temat kont magazynu, centrów zdarzeń i analizy dzienników. Usługi te pozwalają na przechowywanie danych rejestrowania, korzystanie z analiz, takich jak Splunk i QRadar, oraz uzyskiwanie wizualizacji danych rejestrowania.

Więcej informacji na temat tej funkcji zawiera artykuł [Send log data to storage, event hubs, or log analytics in Intune](review-logs-using-azure-monitor.md) (Wysyłanie danych dziennika do magazynu, centrów zdarzeń lub analizy dzienników w usłudze Intune).

### <a name="skip-more-setup-assistant-screens-on-an-ios-dep-device----2687509----"></a>Pomijanie większej liczby ekranów Asystenta ustawień na urządzeniu DEP z systemem iOS <!-- 2687509  -->
Oprócz ekranów, które obecnie możesz pominąć, możesz skonfigurować urządzenia z systemem iOS objęte programem DEP tak, aby następujące ekrany Asystenta ustawień były pomijane podczas rejestracji urządzenia przez użytkownika: Ton wyświetlacza, Prywatność, Migracja systemu Android, Przycisk Strona główna, iMessage i FaceTime, Przechodzenie do usługi, Migracja urządzenia Watch, Wygląd, Czas korzystania z urządzenia, Aktualizacja oprogramowania, Instalator SIM.
Aby wybrać ekrany do pominięcia, przejdź kolejno do pozycji **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > wybierz token > **Profile** > wybierz profil > **Właściwości** > **Dostosowywanie Asystenta ustawień** > wybierz pozycję **Ukryj**  dla ekranów do pominięcia > **OK**.
Jeśli tworzysz nowy profil lub edytujesz profil, wybrane pomijane ekrany muszą być synchronizowane z serwerem MDM firmy Apple. Użytkownicy mogą wydać ręczną synchronizację urządzeń, aby nie było ma żadnego opóźnienia podczas pobierania zmian profilu.

#### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Wdrażanie aplikacji APP-WE dla systemu Android Enterprise <!-- 1171203 -->
Dla urządzeń z systemem Android w scenariuszu wdrażania zasad ochrony aplikacji bez rejestracji (APP-WE) możesz teraz używać zarządzanego sklepu Google Play w celu wdrażania aplikacji ze sklepu i aplikacji biznesowych dla użytkowników. Mówiąc ściślej, możesz udostępnić użytkownikom końcowym środowisko katalogu i instalacji aplikacji, które nie wymaga już od użytkowników końcowych obniżenia poziomu zabezpieczeń urządzeń przez umożliwienie instalacji z nieznanych źródeł. Ponadto ten scenariusz wdrażania zapewni ulepszone środowisko pracy użytkownika końcowego.

<!-- ########################## -->
## <a name="week-of-january-14-2019"></a>Tydzień od 14 stycznia 2019 r.

### <a name="preview-of-support-for-android-corporate-owned-fully-managed-devices----1574342----"></a>Obsługa należących do firmy, w pełni zarządzanych urządzeń z systemem Android — wersja zapoznawcza <!-- 1574342  -->
Usługa Intune obsługuje teraz w pełni zarządzane, należące do firmy urządzenia z systemem Android w scenariuszu „właściciel urządzenia”, w którym urządzenia są ściśle zarządzane przez dział IT i są powiązane z poszczególnymi użytkownikami. Pozwala to administratorom na zarządzanie całym urządzeniem, wymuszanie rozszerzonej gamy opcji kontroli zasad niedostępnych dla profilów służbowych oraz ograniczanie możliwości instalowania aplikacji przez użytkowników tylko do aplikacji z zarządzanego sklepu Google Play. Aby uzyskać więcej informacji, zobacz [Konfigurowanie rejestracji w usłudze Intune dla w pełni zarządzanych urządzeń z systemem Android](android-fully-managed-enroll.md) i [Rejestracja urządzeń dedykowanych i w pełni zarządzanych](android-dedicated-devices-fully-managed-enroll.md).  Należy pamiętać, że ta funkcja jest dostępna w wersji zapoznawczej. Niektóre funkcje usługi Intune, takie jak certyfikaty, zgodność i dostęp warunkowy, nie są obecnie dostępne dla w pełni zarządzanych urządzeń użytkowników z systemem Android.

<!-- ########################## -->
## <a name="week-of-january-7-2019"></a>Tydzień od 7 stycznia 2019 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="intune-app-pin----2298397---"></a>Numer PIN aplikacji usługi Intune <!-- 2298397 -->
Jako administrator IT masz teraz możliwość skonfigurowania, ile dni użytkownik końcowy może czekać, aż będzie musiał zmienić numer PIN aplikacji usługi Intune. Nowe ustawienie, czyli *resetowanie numeru PIN po określonej liczbie dni*, jest dostępne w witrynie Azure Portal w obszarze **Intune** > **Aplikacje klienckie** > **Zasady ochrony aplikacji** > **Utwórz zasady** > **Ustawienia** > **Wymagania dotyczące dostępu**. Ta funkcja jest dostępne dla urządzeń z systemami [iOS](app-protection-policy-settings-ios.md) i [Android](app-protection-policy-settings-android.md) i obsługuje dodatnie liczby całkowite.


#### <a name="intune-device-reporting-fields----2748738---"></a>Pola raportów dotyczących urządzeń w usłudze Intune <!-- 2748738 -->
Usługa Intune udostępnia dodatkowe pola raportów dotyczących urządzeń, takie jak na przykład identyfikator rejestracji aplikacji, producent systemu Android, model i wersja poprawki zabezpieczeń, a także model urządzenia z systemem iOS. W usłudze Intune te pola są dostępne po wybraniu opcji **Aplikacje klienckie** > **Stan ochrony aplikacji** i wybraniu pozycji **Raport ochrony aplikacji: iOS, Android**. Ponadto te parametry będą pomocne w przypadku konfigurowania listy **dozwolonych** dla producenta urządzenia (Android), listy **dozwolonych** dla modelu urządzenia (Android i iOS) oraz ustawienia minimalnej wersji poprawki zabezpieczeń systemu Android. 


### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Szablony administracyjne są dostępne w publicznej wersji zapoznawczej i zostały przeniesione do własnego profilu konfiguracji <!-- 3322847 -->

Szablony administracyjne w usłudze Intune (**Konfiguracja urządzenia** > **Szablony administracyjne**) są obecnie dostępne w publicznej wersji zapoznawczej. Dzięki tej aktualizacji

- Szablony administracyjne obejmują około 300 ustawień, którymi można zarządzać w usłudze Intune. Wcześniej ustawienia te istniały tylko w edytorze zasad grupy.
- Szablony administracyjne są dostępne w publicznej wersji zapoznawczej.
- Szablony administracyjne są przenoszone z obszaru **Konfiguracja urządzenia** > **Szablony administracyjne** do obszaru **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > w polu **Platforma** wybierz pozycję  **Windows 10 i nowsze** > w polu **Typ profilu** wybierz pozycję **Szablony administracyjne**.
- Funkcja Raportowanie jest włączona

Aby dowiedzieć się więcej na temat tej funkcji, zobacz [szablony systemu Windows 10 służące do konfigurowania ustawień zasad grupy](administrative-templates-windows.md).

Dotyczy: System Windows 10 lub nowszy

#### <a name="use-smime-to-encrypt-and-sign-multiple-devices-for-a-user-----1333642---"></a>Używanie protokołu S/MIME do szyfrowania i rejestrowania wielu urządzeń użytkownika  <!-- 1333642 -->
Ta aktualizacja obejmuje szyfrowanie poczty e-mail za pomocą protokołu S/MIME z użyciem profilu nowo zaimportowanego certyfikatu (**Konfiguracja urządzenia** > **Profil** > **Utwórz profil** > wybierz platformę > typ profilu **Zaimportowany certyfikat PKCS**). W usłudze Intune można importować certyfikaty w formacie PFX. Usługa Intune może następnie dostarczać te same certyfikaty do wielu urządzeń zarejestrowanych przez jednego użytkownika. Obejmuje to również:
- Profil natywnej poczty e-mail systemu iOS obsługuje włączanie szyfrowania S/MIME przy użyciu importowanych certyfikatów w formacie PFX.
- Natywna aplikacja poczty na urządzeniach z systemem Windows Phone 10 automatycznie używa certyfikatu szyfrowania S/MIME.
- Certyfikaty prywatne mogą być dostarczane na wielu platformach. Jednak nie wszystkie aplikacje poczty e-mail obsługują szyfrowanie S/MIME.
- Na innych platformach może być konieczne ręczne skonfigurowanie aplikacji poczty, aby włączyć szyfrowanie S/MIME.  
- Aplikacje poczty e-mail, które obsługuje szyfrowanie S/MIME może obsługiwać pobieranie certyfikatów dla protokołu S/MIME szyfrowania wiadomości e-mail w sposób, który nie obsługuje zarządzania urządzeniami Przenośnymi, takie jak odczytywanie ich z magazynu certyfikatów ich wydawcy.
Aby uzyskać więcej informacji na temat tej funkcji, zapoznaj się z [omówieniem protokołu S/MIME do podpisywania i szyfrowania wiadomości e-mail](certificates-s-mime-encryption-sign.md).
Obsługiwane na: Windows, Windows Phone 10, macOS, iOS, Android

#### <a name="new-options-to-automatically-connect-and-persist-rules-when-using-dns-settings-on-windows-10-and-later-devices----1333665-2999078---"></a>Nowe opcje automatycznego łączenia i utrzymywania reguł w przypadku korzystania z ustawień systemu DNS w systemie Windows 10 lub nowszym <!-- 1333665, 2999078 -->
Na urządzeniach z systemem Windows 10 lub nowszym możesz utworzyć profil konfiguracji sieci VPN z listą serwerów DNS, która pozwala na rozpoznawanie domen, np. contoso.com. Ta aktualizacja obejmuje nowe ustawienia funkcji rozpoznawania nazw (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > wybierz platformę **Windows 10 i nowsze** > wybierz typ profilu **VPN** > **Ustawienia DNS** >**Dodaj**): 
- **Połącz automatycznie**: po wybraniu pozycji **Włączone** urządzenie automatycznie łączy się z siecią VPN po nawiązaniu kontaktu z wprowadzoną domeną, np. contoso.com.
- **Trwałe**: domyślnie wszystkie reguły tabeli zasad rozpoznawania nazw (NRPT) są aktywne reguły tak długo, jak długo urządzenie jest połączone za pomocą tego profilu sieci VPN. Gdy to ustawienie jest **włączone** dla reguły tabeli NRPT, reguła pozostanie aktywna na urządzeniu, nawet wtedy gdy połączenie sieci VPN zostanie rozłączone. Reguła pozostaje aktywna do momentu usunięcia profilu sieci VPN lub ręcznego usunięcia reguły, co można wykonać w programie PowerShell.
W temacie [Ustawienia sieci VPN systemu Windows 10](vpn-settings-windows-10.md) opisano te ustawienia. 

#### <a name="use-trusted-network-detection-for-vpn-profiles-on-windows-10-devices----1500165---"></a>Korzystanie z wykrywania zaufanych sieci na użytek profilów sieci VPN na urządzeniach z systemem Windows 10 <!-- 1500165 -->
W przypadku korzystania z wykrywania zaufanych sieci możesz wyłączyć automatyczne tworzenie połączenia sieci VPN w profilach sieci VPN, gdy użytkownik będzie już w zaufanej sieci. Dzięki tej aktualizacji masz możliwość dodawania sufiksów DNS w celu włączenia wykrywania zaufanych sieci na urządzeniach z systemem Windows 10 i nowszych (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** jako platforma > **VPN** jako typ profilu).
Aktualną listę ustawień sieci VPN można znaleźć w temacie [Windows 10 VPN settings](vpn-settings-windows-10.md) (Ustawienia sieci VPN w systemie Windows 10).

#### <a name="manage-windows-holographic-for-business-devices-used-by-multiple-users----1907917-1063203---"></a>Zarządzanie urządzeniami z systemem Windows Holographic for Business używanymi przez wielu użytkowników <!-- 1907917, 1063203 -->
Obecnie można konfigurować ustawienia komputera udostępnionego na urządzeniach z systemem Windows 10 i Windows Holographic for Business przy użyciu niestandardowego ustawienia OMA-URI. W ramach tej aktualizacji dodawany jest nowy profil służący do konfigurowania ustawień komputera udostępnionego (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** > **Urządzenie udostępnione wielu użytkownikom**).
Aby dowiedzieć się więcej na temat tej funkcji, zobacz [ustawienia usługi Intune do zarządzania urządzeniami udostępnionymi](shared-user-device-settings.md).
Dotyczy: system Windows 10 lub nowsze oraz system Windows Holographic for Business

#### <a name="new-windows-10-update-settings---2626030--2512994----"></a>Nowe ustawienia aktualizacji systemu Windows 10 <!--2626030  2512994  -->
W przypadku [pierścieni aktualizacji systemu Windows 10](windows-update-for-business-configure.md) możesz skonfigurować:
- **Zachowanie automatycznych aktualizacji**: użyj nowej opcji *Resetuj do domyślnych* w celu przywrócenia oryginalnych ustawień automatycznych aktualizacji na maszynie z systemem Windows 10 z *aktualizacją z października 2018 r.*
- **Blokowanie wstrzymywania aktualizacji systemu Windows przez użytkownika**: skonfiguruj nowe ustawienie aktualizacji oprogramowania, które umożliwia zezwalanie użytkownikom na wstrzymywanie instalacji aktualizacji lub blokowanie tej możliwości w obszarze *Ustawienia* ich komputerów. 

#### <a name="ios-email-profiles-can-use-smime-signing-and-encryption----2662949---"></a>Profile poczty e-mail w systemie iOS mogą używać szyfrowania i podpisywania protokołu S/MIME <!-- 2662949 -->
Masz możliwość tworzenia profilu poczty e-mail z różnymi ustawieniami. Ta aktualizacja obejmuje między innymi ustawienia protokołu S/MIME, których można używać do podpisywania i szyfrowania wiadomości e-mail na urządzeniach z systemem iOS (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > wybierz platformę **iOS** > wybierz typ profilu **E-mail**).
Lista ustawień znajduje się w obszarze [ustawień konfiguracji poczty e-mail systemu iOS](email-settings-ios.md).

#### <a name="some-bitlocker-settings-support-windows-10-pro-edition---2727036---"></a>Niektóre ustawienia funkcji BitLocker obsługują wersję systemu Windows 10 Pro<!-- 2727036 -->
Możesz utworzyć profil konfiguracji, który definiuje ustawienia programu Endpoint Protection na urządzeniach z systemem Windows 10, w tym ustawienia funkcji BitLocker. W tej aktualizacji dodano obsługę systemu Windows 10 Professional dla niektórych ustawień funkcji BitLocker. Aby wyświetlić te ustawienia ochrony, zobacz [Ustawienia programu Endpoint Protection dla systemu Windows 10](endpoint-protection-windows-10.md#windows-encryption).

#### <a name="shared-device-configuration-is-renamed-to-lock-screen-message-for-ios-devices-in-the-azure-portal---2809362---"></a>Nazwa konfiguracji urządzenia udostępnionego została zmieniona na Komunikat ekranu blokady dla urządzeń z systemem iOS w witrynie Azure Portal<!-- 2809362 -->
W przypadku tworzenia profilu konfiguracji dla urządzeń z systemem iOS możesz dodać ustawienia obszaru **Konfiguracja urządzenia udostępnianego** w celu wyświetlania określonego tekstu na ekranie blokady. Ta aktualizacja obejmuje następujące zmiany: 
- Ustawienia **Konfiguracja urządzenia udostępnianego** w witrynie Azure Portal są zmieniane na „Komunikat ekranu blokady (tylko tryb nadzorowany)” (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > wybierz platformę **iOS** > wybierz typ profilu **Funkcje urządzenia** > **Komunikat ekranu blokady**).
- Podczas dodawania wiadomości ekranu blokady można wstawić numer seryjny, nazwę urządzenia lub inną wartość specyficzną dla urządzenia w obszarze **Informacje dotyczące tagu zasobu** i **Przypis dolny ekranu blokady**. Na przykład można wprowadzić wartości `Device name: {{devicename}}` lub `Serial number is {{serialnumber}}`, używając nawiasów klamrowych. Listę dostępnych tokenów do użycia można znaleźć w sekcje [iOS tokens](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) (Tokeny systemu iOS).
Listę ustawień można znaleźć w temacie dotyczącym [ustawień wyświetlania komunikatów na ekranie blokady](shared-device-settings-ios.md).

#### <a name="new-app-store-doc-viewing-gaming-device-restriction-settings-added-to-ios-devices----2827760--"></a>Do urządzeń z systemem iOS dodano nowe ustawienia ograniczeń urządzenia obejmujące sklep App Store, wyświetlanie dokumentów i gry <!-- 2827760-->
W obszarze **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** >  **iOS** dla platformy > **Ograniczenia dotyczące urządzeń** dla typu profilu > **App Store, wyświetlanie dokumentów, gry** dodano następujące ustawienia: Zezwalanie aplikacjom zarządzanym na zapisywanie kontaktów na kontach niezarządzanych kontaktów. Zezwalanie niezarządzanym aplikacjom na odczytywanie z kont kontaktów zarządzanych. Aby wyświetlić te ustawienia, zobacz [ograniczenia urządzeń z systemem iOS](device-restrictions-ios.md#app-store-doc-viewing-gaming).

#### <a name="new-notification-hints-and-keyguard-settings-to-android-enterprise-device-owner-devices----3201839-3201843---"></a>Nowe ustawienia powiadomień, wskazówek i funkcji blokowania klawiatury na urządzeniach właściciela urządzenia z systemem Android Enterprise <!-- 3201839 3201843 -->
Ta aktualizacja obejmuje kilka nowych funkcji dotyczących urządzeń z systemem Android Enterprise uruchamianych jako właściciel urządzenia. Aby korzystać z tych funkcji, przejdź do pozycji **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > w polu **Platforma** wybierz wartość **Android Enterprise** > w polu **Typ profilu** wybierz wartość **Tylko właściciel urządzenia** > **Ograniczenia urządzenia**.

Nowe funkcje obejmują: 

- Wyłączanie wyświetlania powiadomień systemowych, w tym połączeń przychodzących, alertów systemowych, błędów systemu i innych.
- Sugerowanie pomijania samouczków i wskazówek dotyczących aplikacji otwieranych po raz pierwszy.
- Wyłączanie zaawansowanych ustawień funkcji blokady klawiatury, takich jak aparat, powiadomienia, odblokowywanie odciskiem palca i inne.


Aby zapoznać się z tymi ustawieniami, zobacz [ustawienia ograniczeń urządzeń z systemem Android Enterprise](device-restrictions-android-for-work.md).

#### <a name="android-enterprise-device-owner-devices-can-use-always-on-vpn-connections----3202194---"></a>Urządzenia właściciela urządzenia z systemem Android Enterprise mogą używać zawsze włączonych połączeń VPN <!-- 3202194 -->
Dzięki tej aktualizacji będziesz mieć możliwość używania zawsze włączonych połączeń sieci VPN na urządzeniach właściciela urządzenia z systemem Android Enterprise. Zawsze włączone połączenia sieci VPN pozostają aktywne lub są natychmiast przywracane, gdy użytkownik odblokuje urządzenie, gdy urządzenie uruchomi się ponownie lub gdy zmieni się sieć bezprzewodowa. Połączenie można również przenieść do trybu „blokady”, który powoduje zablokowanie całego ruchu sieciowego do momentu uaktywnienia połączenia sieci VPN.
Zawsze włączoną sieć VPN możesz włączyć za pomocą ustawień **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Android Enterprise** jako platforma > **Ograniczenia dotyczące urządzeń** dla opcji Tylko właściciel urządzenia > **Łączność**. Aby zapoznać się z tymi ustawieniami, zobacz [ustawienia ograniczeń urządzeń z systemem Android Enterprise](device-restrictions-android-for-work.md).

#### <a name="new-setting-to-end-processes-in-task-manager-on-windows-10-devices----3285177---"></a>Nowe ustawienie służące do kończenia procesów w Menedżerze zadań na urządzeniach z systemem Windows 10 <!-- 3285177 --> 
Ta aktualizacja obejmuje nowe ustawienie służące do kończenia procesów w Menedżerze zadań na urządzeniach z systemem Windows 10. Używając profilu konfiguracji urządzenia (ustawienia w obszarze **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > w polu **Platforma** wybierz wartość **Windows 10** > w polu **Typ profilu** wybierz wartość **Ograniczenia dotyczące urządzeń** > **Ogólne**), możesz zezwolić na to ustawienie lub je zablokować.
Aby zapoznać się z bieżącymi ustawieniami, zobacz [ustawienia ograniczeń urządzeń z systemem Windows 10](device-restrictions-windows-10.md).
Dotyczy: System Windows 10 lub nowszy


### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="more-detailed-enrollment-restriction-failure-messaging----3111564---"></a>Bardziej szczegółowe komunikaty dotyczące błędów ograniczeń rejestracji <!-- 3111564 -->
Bardziej szczegółowe komunikaty o błędach będą dostępne, gdy ograniczenia rejestracji nie zostaną spełnione. Aby wyświetlić te komunikaty, przejdź do obszaru **Intune** > **Rozwiązywanie problemów** i zapoznaj się z tabelą błędów rejestracji. Aby uzyskać więcej informacji, zobacz [listę błędów rejestracji](help-desk-operators.md#enrollment-failure-reference).

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="tenant-status-dashboard-----1124854---"></a>Pulpit nawigacyjny stanu dzierżawy  <!-- 1124854 -->
Nowa [strona stanu dzierżawy](tenant-status.md) to jedna lokalizacja, w której można wyświetlać stan i powiązane szczegóły dzierżawy.  Pulpit nawigacyjny jest podzielony na cztery obszary:
- **Szczegóły dzierżawy**: zawiera informacje takie jak nazwa i lokalizacja dzierżawy, urząd zarządzania urządzeniami przenośnymi, łączna liczba zarejestrowanych urządzeń w Twojej dzierżawie i liczba licencji. Ta sekcja zawiera także bieżącą wersję usługi dla Twojej dzierżawy.
- **Stan łącznika**: zawiera informacje na temat dostępnych skonfigurowanych łączników, może również zawierać te, które nie zostały jeszcze włączone.  
   Na podstawie bieżącego stanu łączniki są oznaczane flagami Dobra kondycja, Ostrzeżenie lub Zła kondycja. Wybierz łącznik, aby przejść do szczegółów lub skonfigurować dla niego dodatkowe informacje.
-  **Kondycja usługi Intune**: zawiera szczegółowe informacje dotyczące aktywnych zdarzeń lub awarii w dzierżawie. Informacje przedstawione w tej sekcji są pobierane bezpośrednio z Centrum wiadomości usługi Office.
-  **Wiadomości w usłudze Intune**: zawiera aktywne wiadomości dla Twojej dzierżawy. Wiadomości obejmują takie elementy jak na przykład powiadomienia o tym, że dzierżawa otrzymała najnowsze funkcje usługi Intune.  Informacje przedstawione w tej sekcji są pobierane bezpośrednio z Centrum wiadomości usługi Office.

#### <a name="new-help-and-support-experience-in-company-portal-for-windows-10----1488939--"></a>Nowe środowisko pomocy i obsługi technicznej w aplikacji Portal firmy w systemie Windows 10 <!-- 1488939-->
Nowa strona pomocy i obsługi technicznej w aplikacji Portal firmy umożliwia użytkownikom rozwiązywanie problemów i zwracanie się o pomoc w zakresie aplikacji i problemów z dostępem. Na nowej stronie użytkownicy mogą wysłać wiadomość e-mail zawierającą szczegóły błędu oraz informacje z dziennika diagnostycznego, a także znaleźć kontakt do pomocy technicznej organizacji. Mają również dostęp do sekcji z często zadawanymi pytaniami i linkami do odpowiedniej dokumentacji usługi Intune. 

#### <a name="new-help-and-support-experience-for-intune------3307080---"></a>Nowe środowisko pomocy i obsługi technicznej dla usługi Intune   <!-- #3307080 -->
W ciągu kilku najbliższych dni wprowadzimy nowe środowisko pomocy i obsługi technicznej dla wszystkich dzierżaw. Nowe środowisko jest dostępne dla usługi Intune i można uzyskać do niego dostęp, korzystając z bloków usługi Intune w witrynie [Azure Portal](https://portal.azure.com/).
Nowe środowisko pozwala opisać problem własnymi słowami i uzyskać szczegóły dotyczące rozwiązywania problemu oraz zawartość internetową dotyczącą korygowania. Te rozwiązania są oferowane za pośrednictwem algorytmu uczenia maszynowego opartego na regułach i sterowanego przez zapytania użytkownika. Oprócz korzystania ze wskazówek specyficznych dla problemu możesz użyć nowego przepływu pracy tworzenia sprawy do otwarcia zgłoszenia do pomocy technicznej za pomocą poczty e-mail lub telefonu. To nowe środowisko zastępuje poprzednie środowisko Pomocy i obsługi technicznej w postaci statycznego zestawu wstępnie wybranych opcji określonych na podstawie obszaru konsoli aktywnego podczas otwierania środowiska Pomoc i obsługa techniczna. Aby uzyskać więcej informacji, zobacz [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](get-support.md).

### <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach

#### <a name="scope-tags-for-apps----1081941---"></a>Tagi zakresu dla aplikacji <!-- 1081941 -->
Możesz tworzyć tagi zakresu w celu ograniczenia dostępu do ról i aplikacji. Możesz dodać tag zakresu do aplikacji, tak aby tylko osoby z rolą przypisaną do tego tagu zakresu miały dostęp do aplikacji. Obecnie do aplikacji dodanych do usługi Intune z zarządzanego sklepu Google Play lub aplikacji kupionych w ramach programu Apple Volume Purchase Program (VPP) nie można przypisywać tagów zakresu. Planowane jest wprowadzenie tej funkcji w przyszłości. Aby uzyskać więcej informacji, zobacz [Używanie tagów zakresu do filtrowania zasad](scope-tags.md).

<!-- ########################## -->
## <a name="week-of-december-10-2018"></a>Tydzień 10 grudnia 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="updates-for-application-transport-security----748318---"></a>Aktualizacje mechanizmu Application Transport Security <!-- 748318 -->

Usługa Microsoft Intune obsługuje protokół TLS (Transport Layer Security) 1.2+, aby zapewnić najlepsze w swojej klasie szyfrowanie i zagwarantować, że nasza usługa będzie domyślnie bezpieczniejsza, a także dopasować ją do innych usług firmy Microsoft, takich jak Microsoft Office 365. Aby spełnić to wymaganie, portale firmy dla systemu iOS i macOS będą wymuszać wymagania zaktualizowanego mechanizmu Application Transport Security (ATS) firmy Apple, które obejmują również protokół TLS 1.2+. Mechanizm ATS służy do wymuszania mocniejszych zabezpieczeń całej komunikacji aplikacji za pośrednictwem protokołu HTTPS. Ta zmiana dotyczy klientów usługi Intune korzystających z aplikacji Portal firmy dla systemu iOS i macOS. Aby uzyskać więcej informacji, zobacz [blog dotyczący pomocy technicznej usługi Intune](https://aka.ms/compportalats).

#### <a name="the-intune-app-sdk-will-support-256-bit-encryption-keys----1832174---"></a>Zestaw SDK aplikacji usługi Intune będzie obsługiwać 256-bitowe klucze szyfrowania <!-- 1832174 -->
Zestaw SDK aplikacji usługi Intune dla systemu Android korzysta z 256-bitowych kluczy szyfrowania po włączeniu szyfrowania przy użyciu zasad ochrony aplikacji. Zestaw SDK będzie nadal obsługiwać 128-bitowe klucze w celu zachowania zgodności z zawartością i aplikacjami, które używają starszych wersji zestawu SDK.

### <a name="microsoft-auto-update-version-450-required-for-macos-devices----3503442---"></a>Funkcja Microsoft Auto Update w wersji 4.5.0 wymagana dla urządzeń z systemem macOS <!-- 3503442 -->
Aby nadal otrzymywać aktualizacje aplikacji Portal firmy i innych aplikacjach pakietu Office, należy uaktualnić urządzenia z systemem macOS zarządzane przez usługę Intune do funkcji Microsoft Auto Update w wersji 4.5.0. Użytkownicy mogą już mieć tę wersję dla swoich aplikacji pakietu Office.

### <a name="intune-requires-macos-1012-or-later----2827778---"></a>Usługa Intune wymaga systemu macOS 10.12 lub nowszego <!-- 2827778 -->
Usługa Intune wymaga teraz systemu macOS w wersji 10.12 lub nowszego. Urządzenia z wcześniejszymi wersjami systemu macOS nie mogą używać aplikacji Portal firmy w celu rejestracji do usługi Intune. Aby nadal otrzymywać pomoc techniczną i nowe funkcje, użytkownicy muszą uaktualnić swoje urządzenia do systemu macOS 10.12 lub nowszego i uaktualnić aplikację Portal firmy do najnowszej wersji.

<!-- ########################## -->
## <a name="week-of-november-26-2018"></a>Tydzień 26 listopada 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="uninstalling-apps-on-corporate-owned-supervised-ios-devices----1281677---"></a>Odinstalowywanie aplikacji na nadzorowanych urządzeniach z systemem iOS należących do firmy <!-- 1281677 -->

Można usunąć dowolną aplikację na nadzorowanych urządzeniach z systemem iOS należących do firmy. Dowolną aplikację można usunąć, określając jako cel grupę użytkowników lub urządzeń za pomocą typu przypisania **Odinstaluj**. W przypadku osobistych lub nienadzorowanych urządzeń z systemem iOS będzie można w dalszym ciągu usunąć tylko aplikacje zainstalowane przy użyciu usługi Intune.

#### <a name="downloading-intune-win32-app-content----2617320---"></a>Pobieranie zawartości aplikacji usługi Intune Win32 <!-- 2617320 -->
System Windows 10 RS3 i nowsi klienci będą pobierać zawartość aplikacji Win32 w usłudze Intune przy użyciu składnika Optymalizacja dostarczania w obrębie klienta systemu Windows 10. Optymalizacja dostarczania udostępnia funkcję Sieć równorzędna, która jest włączana domyślnie. Optymalizację dostarczania można obecnie skonfigurować przy użyciu zasad grupy. Aby uzyskać więcej informacji, zobacz [Delivery Optimization for Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) (Optymalizacja dostarczania w systemie Windows 10). 

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Menu kontekstowe na urządzeniach użytkowników końcowych i w aplikacjach <!-- 2771453 -->
Użytkownicy końcowi mogą teraz korzystać z menu kontekstowego na urządzeniach i aplikacjach w celu wyzwolenia typowych akcji, takich jak zmiana nazwy urządzenia lub sprawdzenie zgodności.

#### <a name="set-custom-background-in-managed-home-screen-app-----3041945---"></a>Ustawianie niestandardowego tła w aplikacji Managed Home Screen  <!-- 3041945 -->
Dodajemy ustawienie, które umożliwia dostosowanie wyglądu tła aplikacji Managed Home Screen na urządzeniach z rozwiązaniem Android Enterprise pracujących w trybie kiosku z wieloma aplikacjami.  Aby skonfigurować **adres URL niestandardowego tła**, przejdź do usługi Intune za pomocą pozycji Konfiguracja urządzenia w witrynie Azure Portal. Wybierz bieżący profil konfiguracji urządzenia lub utwórz nowy profil, aby edytować ustawienia kiosku.
Aby zapoznać się z ustawieniami kiosku, zobacz temat [Ograniczeń urządzeń z systemem Android Enterprise](device-restrictions-android-for-work.md).

#### <a name="app-protection-policy-assignment-save-and-apply----3104570---"></a>Zapisywanie i stosowanie przypisania zasad ochrony aplikacji <!-- 3104570 -->
Będziesz mieć lepszą kontrolę nad [przypisaniami zasad ochrony aplikacji](app-protection-policies.md#deploy-a-policy-to-users). Jeśli wybierzesz pozycję *Przypisania* w celu ustawiania lub edytowania przypisań zasad, musisz najpierw **zapisać** konfigurację, aby zmiana została zastosowana. Użyj pozycji **Odrzuć**, aby wyczyścić wszystkie wprowadzone zmiany bez ich zapisywania na listach uwzględniania lub wykluczania.  Dzięki możliwości wymagania zapisania lub odrzucenia zasady ochrony aplikacji są przypisywane tylko do wybranych przez Ciebie użytkowników.

#### <a name="new-microsoft-edge-browser-settings-for-windows-10-and-later----3174639---"></a>Nowe ustawienia przeglądarki Microsoft Edge dla systemu Windows 10 i nowszych <!-- 3174639 -->
Ta aktualizacja obejmuje nowe ustawienia ułatwiające kontrolowanie przeglądarki Microsoft Edge na urządzeniach i zarządzanie nią. Aby uzyskać listę tych ustawień, zobacz [Ograniczenia urządzeń dla systemu Windows 10 (i nowszych)](device-restrictions-windows-10.md#microsoft-edge-browser).

#### <a name="new-apps-support-with-app-protection-policies----3330037---"></a>Obsługa nowych aplikacji przy użyciu zasad ochrony aplikacji <!-- 3330037 -->
Teraz można zarządzać następującymi aplikacjami za pomocą [zasad ochrony aplikacji usługi Intune](app-protection-policies.md):
- Stream (iOS)
- To DO (Android, iOS)
- PowerApps (Android, iOS)
- Flow (Android, iOS)

Zasady ochrony aplikacji umożliwiają ochronę danych firmowych i kontrolowanie transferu danych dla tych aplikacji, podobnie jak w przypadku innych aplikacji zarządzanych przez zasady usługi Intune. Uwaga: jeśli usługa Flow nie jest jeszcze widoczna w konsoli, należy ją dodać podczas tworzenia lub edytowania zasad ochrony aplikacji. W tym celu należy użyć opcji **+ Więcej aplikacji** i podać *identyfikator aplikacji* dla usługi Flow w polu danych wejściowych. W przypadku systemu Android należy użyć wartości *com.microsoft.flow*, a w przypadku systemu iOS — wartości *com.microsoft.procsimo*.


### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="ios-and-macos-version-numbers-and-build-numbers-are-shown----1892471---"></a>Są wyświetlane numery wersji i numery kompilacji systemów iOS i macOS <!-- 1892471 -->
W polu **Zgodność urządzenia** > **Zgodność urządzenia** są wyświetlane wersje systemów operacyjnych iOS oraz macOS i można ich używać w zasadach zgodności. Ta aktualizacja uwzględnia numer kompilacji, który można konfigurować na obydwu platformach.
Po wydaniu aktualizacji zabezpieczeń firma Apple zwykle pozostawia numer wersji bez zmian, lecz aktualizuje numer kompilacji. Na podstawie numeru kompilacji w zasadach zgodności można łatwo sprawdzić, czy została zainstalowana aktualizacja eliminująca luki w zabezpieczeniach.
Aby korzystać z tej funkcji, zapoznaj się z zasadami zgodności dla systemów [iOS](compliance-policy-create-ios.md#device-health) i [macOS](compliance-policy-create-mac-os.md#device-properties).

#### <a name="update-rings-are-being-replaced-with-delivery-optimization-settings-for-windows-10-and-later----2753807---"></a>Pierścienie aktualizacji są zastępowane ustawieniami optymalizacji dostarczania dla systemu Windows 10 i nowszych wersji <!-- 2753807 -->
Optymalizacja dostarczania to nowy profil konfiguracji dla systemu Windows 10 i nowszych wersji. Ta funkcja oferuje bardziej usprawnione środowisko dostarczania aktualizacji oprogramowania do urządzeń w organizacji. Ta aktualizacja pomaga też dostarczać ustawienia w nowych i istniejących pierścieniach aktualizacji przy użyciu profilu konfiguracji.
Aby skonfigurować profil konfiguracji optymalizacji dostarczania, zobacz [Windows 10 (and newer) delivery optimization settings](delivery-optimization-windows.md) (Ustawienia optymalizacji w systemie Windows 10 (i nowszych)).

#### <a name="new-device-restriction-settings-added-to-ios-and-macos-devices----2827760---"></a>Nowe ustawienia ograniczeń urządzeń dodane do urządzeń z systemem iOS i macOS <!-- 2827760 -->
Ta aktualizacja obejmuje nowe ustawienia dla urządzeń z systemem iOS i macOS, które zostały wydane z systemem iOS 12:

**Ustawienia systemu iOS**: 
- Ogólne: Blokuj usuwanie aplikacji (tylko tryb nadzorowany)
- Ogólne: Blokuj tryb ograniczony USB (tylko tryb nadzorowany)
- Ogólne: Wymuszaj automatyczne ustawianie daty i godziny (tylko tryb nadzorowany)
- Hasło: Blokuj automatyczne wypełnianie haseł (tylko tryb nadzorowany)
- Hasło: Blokuj zbliżeniowe żądania haseł (tylko tryb nadzorowany)
- Hasło: Blokuj udostępnianie haseł (tylko tryb nadzorowany)

**Ustawienia systemu macOS**: 
- Hasło: Blokuj automatyczne wypełnianie haseł
- Hasło: Blokuj zbliżeniowe żądania haseł
- Hasło: Blokuj udostępnianie haseł

Aby dowiedzieć się więcej o tych ustawieniach, zobacz ustawienia ograniczeń urządzeń z systemem [iOS](device-restrictions-ios.md) i [macOS](device-restrictions-macos.md).

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="select-apps-tracked-on-the-enrollment-status-page---2531007---"></a>Wybieranie śledzonych aplikacji na stronie stanu rejestracji<!-- 2531007 -->
Można wybrać śledzone aplikacje na stronie stanu rejestracji. Do momentu zainstalowania tych aplikacji użytkownik nie może korzystać z urządzenia. Aby uzyskać więcej informacji, zobacz [Konfigurowanie strony ze stanem rejestracji](windows-enrollment-status.md).

#### <a name="search-for-autopilot-device-by-serial-number---2595788---"></a>Wyszukiwanie urządzenia rozwiązania Autopilot według numeru seryjnego <!--2595788 -->
Teraz można wyszukiwać urządzenia rozwiązania Autopilot według numeru seryjnego. W tym celu należy wybrać pozycję **Rejestrowanie urządzenia** > **Rejestracja w systemie Windows** > **Urządzenia** > wpisz numer seryjny w polu **Wyszukiwanie według numeru seryjnego** > naciśnij klawisz Enter.

#### <a name="track-installation-of-office-proplus---2620217---"></a>Śledzenie instalacji pakietu Office ProPlus <!--2620217 -->
Użytkownicy mogą śledzić postęp instalacji pakietu [Office ProPlus](apps-add-office365.md) przy użyciu [strony stanu rejestracji](windows-enrollment-status.md). Aby uzyskać więcej informacji, zobacz [Konfigurowanie strony ze stanem rejestracji](windows-enrollment-status.md).

#### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Alerty dotyczące wygasającego tokenu VPP lub zbyt małej liczby licencji aplikacji Portal firmy <!-- 2237572 -->
Jeśli do wstępnej aprowizacji aplikacji Portal firmy podczas rejestracji programu DEP używasz tokenu programu Volume Purchase Program (VPP), usługa Intune powiadomi Cię, jeśli token VPP niedługo wygaśnie lub zaczyna brakować licencji aplikacji Portal firmy.

### <a name="macos-device-enrollment-program-support-for-apple-school-manager-accounts---3006133---"></a>Obsługa programu Device Enrollment Program dla systemu macOS w przypadku kont usługi Apple School Manager <!--3006133 -->
Usługa Intune obsługuje teraz program Device Enrollment Program dla urządzeń z systemem macOS w przypadku kont usługi Apple School Manager.  Aby uzyskać więcej informacji, zobacz [Automatically enroll macOS devices with Apple School Manager or Device Enrollment Program](device-enrollment-program-enroll-macos.md) (Automatyczne rejestrowanie urządzeń z systemem macOS w ramach usługi Apple School Manager lub programu Device Enrollment Program).

### <a name="new-intune-device-subscription-sku---3312071--"></a>Nowa wersja SKU subskrypcji usługi Intune dla urządzeń <!--3312071-->
W celu ułatwienia obniżania kosztów zarządzania urządzeniami w przedsiębiorstwach udostępniono nową wersję SKU subskrypcji opartej na urządzeniach. Ta wersja SKU subskrypcji usługi Intune dla urządzeń jest licencjonowana na urządzenie i jest subskrypcją miesięczną. Cena zależy od programu licencjonowania. Jest ona dostępna bezpośrednio w centrum administracyjnym rozwiązania Microsoft 365, a także za pośrednictwem umów [Enterprise Agreement](https://www.microsoft.com/licensing/licensing-programs/enterprise?activetab=enterprise-tab:primaryr2) (EA), [Microsoft Products and Services Agreement](https://www.microsoft.com/licensing/mpsa/default) (MPSA), [umów Microsoft Open](https://partner.microsoft.com/licensing/licensing-agreements) oraz [dostawcy rozwiązań w chmurze](https://www.microsoftpartnercommunity.com/t5/Partnership-101/What-is-the-Cloud-Solution-Provider-CSP-program/td-p/2453) (CSP, Cloud Solution Provider).

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="temporarily-pause-kiosk-mode-on-android-devices-to-make-changes----3041935---"></a>Tymczasowe wstrzymanie trybu kiosku na urządzeniach z systemem Android w celu wprowadzenia zmian <!-- 3041935 -->
W przypadku urządzeń z systemem Android pracujących w trybie kiosku z wieloma aplikacjami administrator IT może potrzebować wprowadzić zmiany na urządzeniu. Ta aktualizacja obejmuje nowe ustawienia dla kiosku z wieloma aplikacjami, które pozwalają administratorowi IT na tymczasowe wstrzymanie trybu kiosku za pomocą numeru PIN i uzyskanie dostępu do całego urządzenia.
Aby zapoznać się z ustawieniami kiosku, zobacz temat [Ograniczeń urządzeń z systemem Android Enterprise](device-restrictions-android-for-work.md).

#### <a name="enable-virtual-home-button-on-android-enterprise-kiosk-devices-----3042021---"></a>Dostępność wirtualnego przycisku strony głównej na urządzeniach z rozwiązaniem Android Enterprise pracujących w trybie kiosku  <!-- 3042021 -->
Nowe ustawienie umożliwi użytkownikom przełączanie się między aplikacją Managed Home Screen a innymi przypisanymi aplikacjami na urządzeniu kiosku z wieloma aplikacjami przez naciśnięcie przycisku programowego. To ustawienie jest szczególnie przydatne w sytuacjach, gdy aplikacja kiosku nie reaguje odpowiednio na przycisk „wstecz”. To ustawienie będzie można skonfigurować dla pojedynczych urządzeń z systemem Android należących do firmy. Aby włączyć lub wyłączyć **wirtualny przycisk strony głównej**, przejdź do usługi Intune za pomocą pozycji Konfiguracja urządzenia w witrynie Azure Portal. Wybierz bieżący profil konfiguracji urządzenia lub utwórz nowy profil, aby edytować ustawienia kiosku.
Aby zapoznać się z ustawieniami kiosku, zobacz temat [Ograniczeń urządzeń z systemem Android Enterprise](device-restrictions-android-for-work.md).

<!-- ########################## -->
## <a name="week-of-november-12-2018"></a>Tydzień 12 listopada 2018 r.

### <a name="network-access-control-nac-support-for-citrix-sso-for-ios----3259404---"></a>Obsługa kontroli dostępu do sieci (NAC) dla aplikacji Citrix SSO w systemie iOS <!-- 3259404 -->

Firma Citrix opublikowała aktualizację aplikacji Citrix Gateway, aby umożliwić kontrolę dostępu do sieci w aplikacji Citrix dla systemu iOS w usłudze Intune. Można wyrazić zgodę na uwzględnienie identyfikatora urządzenia w profilu sieci VPN w usłudze Intune, a następnie wypchnąć ten profil do urządzeń z systemem iOS. Aby używać tej funkcji, trzeba będzie zainstalować najnowszą aktualizację aplikacji Citrix Gateway.

Temat [Konfigurowanie ustawień sieci VPN na urządzeniach z systemem iOS](vpn-settings-ios.md#base-vpn-settings) zawiera dalsze informacje na temat używania kontroli dostępu do sieci, w tym opis niektórych dodatkowych wymagań. 

<!-- ########################## -->
## <a name="week-of-november-5-2018"></a>Tydzień 5 listopada 2018 r.

### <a name="support-for-ios-12-oauth-in-ios-email-profiles---2155106---"></a>Obsługa uwierzytelniania OAuth z systemu iOS 12 w profilach poczty e-mail systemu iOS <!--2155106 -->

Profile poczty e-mail systemu iOS w usłudze Intune obsługują uwierzytelnianie OAuth (Open Authorization) z systemu iOS 12. Aby wyświetlić tę funkcję, utwórz nowy profil (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **iOS** dla platformy > **E-mail** dla typu profilu) lub zaktualizuj istniejący profil poczty e-mail systemu iOS. Po włączeniu uwierzytelniania OAuth w profilu, który jest już wdrożony u użytkowników, użytkownicy ci są monitowani o ponowne uwierzytelnienie, a następnie o ponowne pobranie poczty e-mail.

Więcej informacji na temat korzystania z protokołu OAuth w profilu poczty e-mail podano w [artykule poświęconym profilom poczty e-mail systemu iOS](email-settings-ios.md).

### <a name="autopilot-support-for-hybrid-azure-active-directory-joined-devices-preview----1048100--"></a>Obsługa rozwiązania Autopilot w przypadku urządzeń przyłączonych hybrydowo do usługi Azure Active Directory (wersja zapoznawcza) <!-- 1048100-->
Za pomocą rozwiązania Autopilot możesz teraz skonfigurować urządzenia przyłączone hybrydowo do usługi Azure Active Directory. Aby używać hybrydowego rozwiązania Autopilot, urządzenia muszą być przyłączone do sieci w organizacji. Aby uzyskać więcej informacji, zobacz [Wdrażanie hybrydowych urządzeń przyłączonych do usługi Active Directory przy użyciu usługi Intune i programu Windows Autopilot](windows-autopilot-hybrid.md).
Ta funkcja będzie stopniowo wprowadzana dla użytkowników w ciągu kilku następnych dni. W związku z tym wykonanie tych kroków może nie być możliwe do momentu wdrożenia jej na Twoim koncie.

<!-- ########################## -->
## <a name="week-of-october-29-2018"></a>Tydzień 29 października 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="require-non-biometric-pin-after-a-specified-timeout----1506985---"></a>Niebiometryczny numer PIN jest wymagany po upłynięciu określonego limitu czasu <!-- 1506985 -->
Wymagając niebiometrycznego numeru PIN po upłynięciu limitu czasu określonego przez administratora, usługa Intune zapewnia lepsze zabezpieczenia dla aplikacji z obsługą funkcji zarządzania aplikacjami mobilnymi (MAM) przez ograniczenie użycia identyfikacji biometrycznej na potrzeby dostępu do danych firmowych. Ustawienia dotyczą użytkowników, którzy korzystają z funkcji Touch ID (iOS), Face ID (iOS), Android Biometric lub innych przyszłych metod uwierzytelniania biometrycznego w celu uzyskiwania dostępu do swoich aplikacji z obsługą zasad ochrony aplikacji/funkcji MAM. Ustawienia umożliwiają administratorom usługi Intune uzyskanie większej kontroli nad dostępem użytkowników, eliminując przypadki, gdy urządzenie z wieloma odciskami palców lub innymi biometrycznymi metodami dostępu może ujawnić dane firmowe niewłaściwemu użytkownikowi. W witrynie Azure Portal otwórz usługę **Microsoft Intune**. Wybierz pozycję **Aplikacje klienckie** > **Zasady ochrony aplikacji** > **Dodaj zasady** > **Ustawienia**. Znajdź sekcję **Dostęp** dla konkretnych ustawień. Aby uzyskać informacje dotyczące ustawień dostępu, zobacz [Ustawienia systemu iOS](app-protection-policy-settings-ios.md#access-requirements) i [Ustawienia systemu Android](app-protection-policy-settings-android.md#access-requirements).

#### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices----2244713---"></a>Ustawienia transferu danych aplikacji usługi Intune w urządzeniach z systemem iOS zarejestrowanych w oprogramowaniu MDM <!-- 2244713 -->
Możesz oddzielić kontrolę ustawień transferu danych aplikacji usługi Intune na urządzeniach z systemem iOS zarejestrowanych w rozwiązaniu MDM od określania tożsamości zarejestrowanego użytkownika nazywanej także główną nazwa użytkownika (UPN). Administratorzy nieużywający narzędzia IntuneMAMUPN nie zaobserwują zmiany zachowania. Jeśli ta funkcja jest dostępna, administratorzy używający narzędzia IntuneMAMUPN do kontrolowania zachowania transferu danych na zarejestrowanych urządzeniach powinni przejrzeć nowe ustawienia i odpowiednio zaktualizować ustawienia aplikacji.

#### <a name="windows-10-win32-apps----2617325---"></a>Aplikacje Win32 systemu Windows 10 <!-- 2617325 -->
Aplikacje Win32 można skonfigurować pod kątem instalowania w kontekście poszczególnych użytkowników w przeciwieństwie do instalowania aplikacji dla wszystkich użytkowników urządzenia.

#### <a name="windows-win32-apps-and-powershell-scripts----2617330---"></a>Aplikacje Win32 systemu Windows i skrypty programu PowerShell <!-- 2617330 -->
Użytkownicy końcowi nie muszą już być zalogowani na urządzeniu, aby instalować aplikacje Win32 lub wykonywać skrypty programu PowerShell. 

#### <a name="troubleshooting-client-app-installation----1363711---"></a>Rozwiązywanie problemów z instalacją aplikacji klienckiej <!-- 1363711 -->
Rozwiązywanie problemów z instalacją aplikacji klienckich można rozpocząć od zapoznania się z kolumną **Instalacja aplikacji** w bloku **Rozwiązywanie problemów**. Aby wyświetlić blok **Rozwiązywanie problemów**, w portalu usługi Intune wybierz pozycję **Rozwiązywanie problemów** w obszarze **Pomoc i obsługa techniczna**.

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="network-access-control-support-on-ios-vpn-clients----1333693---"></a>Obsługa kontroli dostępu do sieci na klientach sieci VPN z systemem iOS <!-- 1333693 -->
W tej aktualizacji udostępniono nowe ustawienie umożliwiające włączenie kontroli dostępu do sieci (NAC) po utworzeniu profilu konfiguracji sieci VPN dla oprogramowania Cisco AnyConnect, F5 Access i Citrix SSO for iOS. To ustawienie umożliwia dołączenie identyfikatora NAC urządzenia do profilu sieci VPN. Obecnie nie ma żadnych klientów sieci VPN ani rozwiązań partnerskich NAC obsługujących ten nowy identyfikator NAC, lecz gdy takie pojawią się, poinformujemy Cię za pośrednictwem [wpisów w naszym blogu obsługi technicznej](ttps://aka.ms/iOS12_and_vpn).

Aby korzystać z kontroli dostępu do sieci, należy:
1. Udzielić zgody, aby umożliwić usłudze Intune dołączanie identyfikatorów urządzeń do profilów sieci VPN
2. Zaktualizować oprogramowanie dostawcy NAC lub oprogramowanie układowe, korzystając ze wskazówek udostępnionych bezpośrednio przez dostawcę NAC

Aby uzyskać informacje na temat tego ustawienia dla profilu sieci VPN systemu iOS, zobacz [Dodawanie ustawień sieci VPN na urządzeniach z systemem iOS w usłudze Microsoft Intune](vpn-settings-ios.md). Aby uzyskać więcej informacji na temat kontroli dostępu do sieci, zobacz [Integracja kontroli dostępu do sieci z usługą Intune](network-access-control-integrate.md). 

Dotyczy: iOS

#### <a name="remove-an-email-profile-from-a-device-even-when-theres-only-one-email-profile----1818139---"></a>Usuwanie profilu poczty e-mail z urządzenia, nawet wtedy, gdy istnieje tylko jeden profil poczty e-mail <!-- 1818139 -->
Wcześniej nie można było usunąć profilu poczty e-mail z urządzenia, *jeśli* był to jedyny profil poczty e-mail. Dzięki tej aktualizacji to zachowanie zmieniło się. Teraz można usunąć profil poczty e-mail, nawet jeśli jest to jedyny profil poczty e-mail w urządzeniu. Zobacz [Add email settings to devices using Intune (Dodawanie ustawień poczty e-mail do urządzeń przy użyciu usługi Intune)](email-settings-configure.md), aby uzyskać szczegółowe informacje.

#### <a name="powershell-scripts-and-aad----2309469---"></a>Skrypty programu PowerShell i usługa AAD <!-- 2309469 -->
Skrypty programu PowerShell w usłudze Intune mogą być przeznaczone dla grup zabezpieczeń urządzeń usługi AAD.

#### <a name="new-required-password-type-default-setting-for-android-android-enterprise---2649963---"></a>Nowe ustawienie domyślne „Wymagany typ hasła” dla systemów Android, Android Enterprise<!-- 2649963 -->
Podczas tworzenia nowych zasad zgodności (**Intune** > **Zgodność urządzenia** > **Zasady** > **Utwórz zasady** > **Android** lub **Android enterprise** dla platformy > Zabezpieczenia systemu) wartość domyślna dla ustawienia **Wymagany typ hasła** ulega zmianie:

Od: Ustawienie domyślne urządzenia Do: Co najmniej numeryczne

Dotyczy: Android, Android Enterprise

Aby wyświetlić te ustawienia, przejdź do pozycji [Android](compliance-policy-create-android.md) i [Android Enterprise](compliance-policy-create-android-for-work.md).

#### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile----2662938---"></a>Używanie klucza wstępnego w profilu sieci Wi-Fi systemu Windows 10 <!-- 2662938 -->
Dzięki tej aktualizacji będziesz mieć możliwość użycia klucza wstępnego (PSK) z protokołem zabezpieczeń WPA/WPA2-Personal do uwierzytelniania profilu konfiguracji sieci Wi-Fi dla systemu Windows 10. Będzie także możliwe określenie konfiguracji kosztów dla sieci taryfowej na potrzeby urządzeń z systemem Windows 10 z aktualizacją z października 2018 r.

Obecnie trzeba zaimportować profil sieci Wi-Fi lub utworzyć profil niestandardowy, aby korzystać z klucza wstępnego. Obszar [Ustawienia sieci Wi-Fi dla systemu Windows 10](wi-fi-settings-windows.md) zawiera listę bieżących ustawień. 

#### <a name="remove-pkcs-and-scep-certificates-from-your-devices----3218390---"></a>Usuwanie certyfikatów PKCS i SCEP z urządzeń <!-- 3218390 -->
W niektórych scenariuszach certyfikaty PKCS i SCEP pozostawały w urządzeniach nawet po usunięciu zasad z grupy, usunięciu wdrożenia konfiguracji lub zgodności albo zaktualizowania istniejącego profilu certyfikatu SCEP lub PKCS. Ta aktualizacja zmienia to zachowanie. W pewnych scenariuszach certyfikaty PKCS i SCEP są usuwane z urządzeń, a w innych — pozostają w urządzeniu. Opis tych scenariuszy można znaleźć w temacie [Usuwanie certyfikatów SCEP i PKCS w usłudze Microsoft Intune](remove-certificates.md).

#### <a name="use-gatekeeper-on-macos-devices-for-compliance----2504381---"></a>Użycie programu Gatekeeper na urządzeniach z systemem macOS na potrzeby zachowania zgodności <!-- 2504381 -->
Ta aktualizacja obejmuje program Gatekeeper dla systemu macOS umożliwiający ocenę urządzenia pod kątem zgodności. Aby ustawić właściwość programu Gatekeeper, zobacz [Dodawanie zasad zgodności dla urządzeń z systemem macOS](compliance-policy-create-mac-os.md).


### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="enrollment-abandonment-report----1382924---"></a>Raport porzucania rejestracji <!-- 1382924 -->
Nowy raport zawierający szczegółowe informacje dotyczące porzuconych rejestracji jest dostępny w obszarze **Rejestrowanie urządzeń** > **Monitorowanie**. Aby uzyskać więcej informacji, zobacz [Raport porzucania portalu firmy](enrollment-report-company-portal-abandon.md).

#### <a name="new-azure-active-directory-terms-of-use-feature----2870393---"></a>Nowa funkcja warunków użytkowania usługi Azure Active Directory <!-- 2870393 -->
Usługa Azure Active Directory udostępnia funkcję warunków użytkowania, której można użyć zamiast istniejących warunków i postanowień usługi Intune. Funkcja warunków użytkowania usługi Azure AD zapewnia większą elastyczność w związku z tym, które warunki wyświetlić i kiedy, lepszą obsługę lokalizacji, większą kontrolę sposobu renderowania i ulepszone raportowanie. Funkcja warunków użytkowania usługi Azure AD wymaga usługi Azure Active Directory Premium P1, która jest również częścią pakietu Enterprise Mobility + Security E3. Aby dowiedzieć się więcej, zobacz artykuł [Zarządzanie warunkami i postanowieniami obowiązującymi w firmie na potrzeby dostępu użytkowników](terms-and-conditions-create.md).

#### <a name="android-device-owner-mode-support---3188762--"></a>Obsługa trybu Właściciel urządzenia z systemem Android <!--3188762-->
W przypadku rejestracji w rozwiązaniu Samsung Knox Mobile Enrollment usługa Intune obsługuje teraz rejestrowanie urządzeń w trybie zarządzania Właściciel urządzenia z systemem Android. Użytkownicy korzystający z sieci komórkowej lub Wi-Fi mogą za pomocą kilku naciśnięć zarejestrować urządzenie przy jego pierwszym włączeniu. Aby uzyskać więcej informacji, zobacz temat [Automatically enroll Android devices by using Samsung's Knox Mobile Enrollment](android-samsung-knox-mobile-enroll.md) (Automatyczne rejestrowanie urządzeń z systemem Android za pomocą rozwiązania Knox Mobile Enrollment firmy Samsung).

### <a name="device-management"></a>Zarządzanie urządzeniami
#### <a name="new-settings-for-software-updates------1907869---"></a>Nowe ustawienia aktualizacji oprogramowania   <!-- 1907869 -->  
- Teraz można skonfigurować niektóre powiadomienia, aby wysyłać do użytkowników końcowych alerty dotyczące operacji ponownego uruchamiania, które są wymagane do zakończenia instalacji najnowszych aktualizacji oprogramowania.   
- Teraz można skonfigurować monit ostrzegawczy dotyczący ponownych uruchomień, które odbywają się poza godzinami pracy. Ta opcja jest obsługiwana w przypadku scenariuszy BYOD.

#### <a name="group-windows-autopilot-enrolled-devices-by-correlator-id----2075110---"></a>Grupowanie urządzeń zarejestrowanych w programie Windows Autopilot według identyfikatora korelatora <!-- 2075110 -->
Usługa Intune teraz obsługuje grupowanie urządzeń z systemem Windows według identyfikatora korelatora, jeśli urządzenia są zarejestrowane przy użyciu [rozwiązania Autopilot dla istniejących urządzeń](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) za pośrednictwem programu Configuration Manager. Identyfikator korelatora jest parametrem pliku konfiguracji rozwiązania Autopilot. Usługa Intune automatycznie ustawi [atrybut enrollmentProfileName urządzenia w usłudze Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#using-attributes-to-create-rules-for-device-objects) na wartość „OfflineAutopilotprofile-<correlator ID>”. Dzięki temu można utworzyć dowolne grupy dynamiczne usługi Azure AD na podstawie identyfikatora korelatora za pomocą atrybutu enrollmentprofileName dla rejestracji rozwiązania Autopilot w trybie offline. Aby uzyskać więcej informacji, zobacz [Rozwiązanie Windows Autopilot dla istniejących urządzeń](enrollment-autopilot.md#windows-autopilot-for-existing-devices).

#### <a name="intune-app-protection-policies----2984657---"></a>Zasady ochrony aplikacji usługi Intune <!-- 2984657 -->
Zasady ochrony aplikacji usługi Intune pozwalają skonfigurować różne ustawienia ochrony danych dla chronionych aplikacji usługi Intune, takich jak Outlook i Word. Zmieniliśmy wygląd i działanie tych ustawień dla systemów [iOS](app-protection-policy-settings-ios.md) i [Android](app-protection-policy-settings-android.md), aby umożliwić łatwiejsze znalezienie poszczególnych ustawień. Istnieją trzy kategorie ustawień zasad:
- **Relokacja danych** — ta grupa obejmuje kontrolki ochrony przed utratą danych ograniczające działania takie jak wycinanie, kopiowanie, wklejanie i zapisywanie pod nową nazwą. Te ustawienia określają, jak użytkownicy używają danych w aplikacjach.
- **Wymagania dotyczące dostępu** — ta grupa zawiera opcje numeru PIN dla poszczególnych aplikacji, które określają, w jaki sposób użytkownik uzyskuje dostęp do aplikacji w kontekście służbowym.  
- **Uruchamianie warunkowe** — ta grupa zawiera ustawienia takie jak minimalna wersja systemu operacyjnego, wykrywanie urządzeń ze zdjętymi zabezpieczeniami systemu i z dostępem do konta root oraz okresy prolongaty trybu offline.  
  
Działanie ustawień nie ulega zmianie, ale będzie można je łatwiej znaleźć podczas pracy z przepływem tworzenia zasad.

### <a name="intune-apps"></a>Aplikacje usługi Intune

#### <a name="intune-will-support-a-maximum-package-size-of-8-gb-for-lob-apps----1727158---"></a>Usługa Intune będzie obsługiwać pakiety o maksymalnym rozmiarze 8 GB w przypadku aplikacji biznesowych <!-- 1727158 -->
Usługa Intune zwiększyła maksymalny rozmiar pakietu do 8 GB dla aplikacji biznesowych. Aby uzyskać więcej informacji, zobacz [Dodawanie aplikacji do usługi Microsoft Intune](apps-add.md).

#### <a name="add-custom-brand-image-for-company-portal-app----1916266---"></a>Dodawanie obrazu niestandardowego marki dla aplikacji Portal firmy <!-- 1916266 -->
Jako administrator usługi Microsoft Intune masz możliwość przekazania obrazu niestandardowego marki, który będzie wyświetlany jako obraz tła na stronie profilu użytkownika w aplikacji Portal firmy dla systemu iOS. Aby uzyskać więcej informacji na temat konfigurowania aplikacji Portal firmy, zobacz artykuł [Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune](company-portal-app.md).

#### <a name="intune-will-maintain-the-office-localized-language-when-updating-office-on-end-users-machines----2971030---"></a>Zachowanie lokalnego języka pakietu Office przez usługę Intune podczas aktualizowania pakietu Office na komputerach użytkowników końcowych <!-- 2971030 -->
Podczas instalowania pakietu Office na komputerach użytkowników końcowych przez usługę Intune użytkownicy końcowi automatycznie uzyskają te same pakiety językowe, z których korzystali w przypadku poprzednich instalacji pakietu Office opartych na instalatorze MSI. Aby uzyskać więcej informacji, zobacz [Jak przypisać aplikacje usługi Office 365 do urządzeń z systemem Windows 10 przy użyciu usługi Microsoft Intune](apps-add-office365.md).

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="new-intune-support-experience-in-the-microsoft-365-device-management-portal----3076965---"></a>Nowe środowisko pomocy technicznej usługi Intune w portalu zarządzania urządzeniami na platformie Microsoft 365 <!-- 3076965 -->
Wprowadzamy nowe środowisko Pomoc i obsługa techniczna dla usługi Intune w [portalu zarządzania urządzeniami na platformie Microsoft 365]( http://devicemanagement.microsoft.com). Nowe środowisko pozwala opisać problem własnymi słowami i uzyskać szczegóły dotyczące rozwiązywania problemu oraz zawartość internetową dotyczącą korygowania. Te rozwiązania są oferowane za pośrednictwem algorytmu uczenia maszynowego opartego na regułach i sterowanego przez zapytania użytkownika.  

Oprócz korzystania ze wskazówek specyficznych dla problemu można także użyć nowego przepływu pracy tworzenia sprawy do otwarcia zgłoszenia do pomocy technicznej za pomocą poczty e-mail lub telefonu.  

Dla klientów objętych wdrożeniem to nowe środowisko zastępuje bieżące środowisko Pomoc i obsługa techniczna w postaci statycznego zestawu wstępnie wybranych opcji określonych na podstawie obszaru konsoli aktywnego podczas otwierania środowiska Pomoc i obsługa techniczna.  

*Nowe środowisko Pomoc i obsługa techniczna jest wdrażane dla niektórych, lecz nie wszystkich, dzierżaw i jest dostępne w portalu Zarządzanie urządzeniami. Użytkownicy nowego środowiska zostali wybrani losowo z dostępnych dzierżaw usługi Intune. Nowe dzierżawy będą dodawane w miarę postępów wdrażania.*  

Aby uzyskać więcej informacji, zobacz [Środowisko Pomoc i obsługa techniczna](get-support.md#help-and-support-experience) na stronie Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune.  

### <a name="powershell-module-for-intune--preview-available----951068---"></a>Moduł programu PowerShell dla usługi Intune w wersji zapoznawczej dostępny <!-- 951068 -->
Nowy moduł programu PowerShell, który zapewnia obsługę interfejsu API usługi Intune za pośrednictwem programu Microsoft Graph, jest teraz dostępny w wersji zapoznawczej w serwisie [GitHub]( https://aka.ms/intunepowershell). Aby uzyskać szczegółowe informacje na temat korzystania z tego modułu, zobacz plik README w tej lokalizacji. 


<!-- ########################## -->
## <a name="week-of-october-15-2018"></a>Tydzień 15 października 2018 r.

### <a name="pin-prompt-when-you-change-fingerprints-or-face-id-on-an-ios-device-----2637704----"></a>Monit o podanie numeru PIN podczas zmieniania odcisków palców lub twarzy w funkcji Face ID na urządzeniu z systemem iOS  <!-- 2637704  -->
Użytkownicy są teraz monitowani o podanie numeru PIN po wprowadzeniu zmian biometrycznych na urządzeniu z systemem iOS. Obejmuje to zmiany zarejestrowanych odcisków palców lub twarzy w funkcji Face ID. Chronometraż monitu zależy od konfiguracji limitu czasu *Ponownie sprawdź wymagania dostępu po (minuty)* .  Jeśli numer PIN nie jest ustawiony, użytkownik jest monitowany o ustawienie go. 
 
Ta funkcja jest dostępna tylko dla systemów iOS i wymaga udziału aplikacji, w których zintegrowany jest zestaw SDK zasad ochrony aplikacji usługi Intune dla systemu iOS w wersji 9.0.1 lub nowszej. Integracja zestawu SDK jest konieczna, aby można było wymusić to zachowanie w aplikacjach docelowych. Ta integracja jest przeprowadzana w sposób ciągły i zależy od zespołów zajmujących się określonymi aplikacjami. Dotyczy to między innymi aplikacji WXP, Outlook, Managed Browser i Yammer.


<!-- ########################## -->
## <a name="week-of-october-1-2018"></a>Tydzień 1 października 2018 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="access-to-key-profile-properties-using-the-company-portal-app----772203---"></a>Dostęp do kluczowych właściwości profilu za pomocą aplikacji Portal firmy <!-- 772203 -->
Użytkownicy końcowi mogą teraz uzyskiwać dostęp do kluczowych właściwości konta i akcji takich jak resetowanie hasła z aplikacji Portal firmy. 

#### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Klawiatury innych firm mogą zostać zablokowane przez ustawienia aplikacji w systemie iOS <!-- 1248481 -->
Na urządzeniach z systemem iOS administratorzy usługi Intune mogą zablokować możliwość korzystania z klawiatur innych firm podczas uzyskiwania dostępu do danych organizacji w aplikacjach chronionych przez zasady. Gdy zasady ochrony aplikacji (APP) są ustawione na blokowanie klawiatur innych firm, użytkownik urządzenia otrzymuje komunikat podczas pierwszej próby interakcji z danymi firmowymi przy użyciu klawiatury innej firmy. Wszystkie opcje inne niż klawiatura macierzysta są zablokowane, a użytkownicy urządzenia nie będą ich widzieć. Użytkownicy urządzenia zobaczą tylko raz komunikat w oknie dialogowym. 

#### <a name="user-account-access-of-intune-apps-on-managed-android-and-ios-devices----1248496---"></a>Dostęp do konta użytkownika w przypadku aplikacji usługi Intune na zarządzanych urządzeniach z systemami Android i iOS <!-- 1248496 -->
Jako administrator usługi Microsoft Intune masz możliwość kontrolowania kont użytkownika dodawanych do aplikacji pakietu Microsoft Office na urządzeniach zarządzanych. Istnieje możliwość ograniczenia dostępu tylko do dozwolonych kont użytkowników w organizacji oraz blokowania kont osobistych na zarejestrowanych urządzeniach. 

#### <a name="outlook-ios-and-android-app-configuration-policy---1828527---"></a>Zasady konfiguracji aplikacji Outlook dla systemów iOS i Android <!--1828527 -->
Można teraz utworzyć zasady konfiguracji aplikacji Outlook dla systemów iOS i Android przeznaczone dla użytkowników lokalnych, którzy korzystają z uwierzytelniania podstawowego przy użyciu protokołu ActiveSync. Dodatkowe ustawienia konfiguracji będą dodawane w miarę ich włączania w aplikacji Outlook dla systemów iOS i Android.

#### <a name="office-365-pro-plus-language-packs----1833450---"></a>Pakiety językowe usługi Office 365 Pro Plus <!-- 1833450 -->
Jako administrator usługi Intune możesz wdrożyć dodatkowe języki dla aplikacji pakietu Office 365 Pro Plus zarządzanych przez usługę Intune. Lista dostępnych języków uwzględnia **Typ** pakietu językowego (podstawowy, częściowy i weryfikujący). W witrynie Azure Portal wybierz pozycję **Microsoft Intune** > **Aplikacje klienckie** > **Aplikacje** > **Dodaj**. Na liście **Typ aplikacji** w bloku **Dodaj aplikację** wybierz pozycję **Windows 10** w obszarze **Pakiet Office 365**. Wybierz pozycję **Języki** w bloku **Ustawienia pakietu aplikacji**.

####  <a name="windows-line-of-business-lob-apps-file-extensions----1884873---"></a>Rozszerzenia plików aplikacji biznesowych (LOB) dla systemu Windows <!-- 1884873 -->
Rozszerzenia plików aplikacji LOB dla systemu Windows obejmują teraz rozszerzenia *msi*, *appx*, *appxbundle*, *msix* i *msixbundle*. Aby dodać aplikację w usłudze Microsoft Intune, wybierz kolejno pozycje **Aplikacje klienckie** > **Aplikacje** > **Dodaj**. Zostanie wyświetlone okienko **Dodaj aplikację**, w którym możesz wybrać **Typ aplikacji**. Dla aplikacji LOB dla systemu Windows wybierz aplikację **Biznesowa** jako typ aplikacji, wybierz pozycję **Plik pakietu aplikacji**, a następnie wprowadź plik instalacyjny z odpowiednim rozszerzeniem.

#### <a name="windows-10-app-deployment-using-intune----2309001---"></a>Wdrażanie aplikacji systemu Windows 10 przy użyciu usługi Intune <!-- 2309001 -->
Korzystając z istniejącej obsługi aplikacji biznesowych i aplikacji z portalu Microsoft Store dla Firm, administratorzy mogą użyć usługi Intune do wdrożenia większości aplikacji używanych w organizacji dla użytkowników końcowych na urządzeniach z systemem Windows 10. Administratorzy mogą dodawać, instalować i deinstalować aplikacje dla użytkowników systemu Windows 10 w różnych formatach, takich jak MSI, Setup.exe lub MSP. Usługa Intune oceni reguły wymagań przed pobraniem i zainstalowaniem, powiadamiając użytkowników końcowych o stanie wymagań dotyczących ponownego uruchomienia za pomocą Centrum akcji systemu Windows 10. Ta funkcja skutecznie umożliwia zainteresowanym organizacjom przeniesienie obciążenia do usługi Intune i chmury. Jest ona obecnie dostępna w publicznej wersji zapoznawczej i planujemy dodanie do niej znaczących nowych możliwości w ciągu kilku następnych miesięcy. 

#### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Ustawienia zasad ochrony aplikacji dla danych internetowych <!-- 2662995 -->
Ustawienia zasad ochrony aplikacji dla zawartości internetowej na urządzeniach z systemami Android i iOS zostaną zaktualizowane w celu ulepszenia obsługi linków internetowych http i https, a także przesyłania danych za pośrednictwem linków uniwersalnych systemu iOS i linków między aplikacjami systemu Android. 

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Menu kontekstowe na urządzeniach użytkowników końcowych i w aplikacjach <!-- 2771453 -->
Użytkownicy końcowi mogą teraz korzystać z menu kontekstowego na urządzeniach i aplikacjach w celu wyzwolenia typowych akcji, takich jak zmiana nazwy urządzenia lub sprawdzenie zgodności. 

#### <a name="windows-company-portal-keyboard-shortcuts----2771518---"></a>Skróty klawiaturowe w aplikacji Portal firmy dla systemu Windows <!-- 2771518 -->
Użytkownicy końcowi będą teraz mogli wyzwalać akcje aplikacji i urządzeń w aplikacji Portal firmy dla systemu Windows za pomocą skrótów klawiaturowych (akceleratorów).

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="create-dns-suffixes-in-vpn-configuration-profiles-on-devices-running-windows-10---1333668---"></a>Tworzenie sufiksów DNS w profilach konfiguracji sieci VPN na urządzeniach z systemem Windows 10<!-- 1333668 -->
Podczas tworzenia profilu konfiguracji urządzenia sieci VPN (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** (platforma) > **VPN** (typ profilu)) wprowadzasz pewne ustawienia systemu DNS. Dzięki tej aktualizacji można również podać wiele **sufiksów DNS** w usłudze Intune. Korzystając z sufiksów DNS, możesz wyszukać zasób sieciowy za pomocą jego krótkiej nazwy, zamiast w pełni kwalifikowanej nazwy domeny (FQDN). Ta aktualizacja umożliwia również zmianę kolejności sufiksów DNS w usłudze Intune.
Pole [Ustawienia sieci VPN systemu Windows 10](vpn-settings-windows-10.md#dns-settings) zawiera aktualnie ustawienia systemu DNS.
Dotyczy: Urządzenia z systemem Windows 10

#### <a name="support-for-always-on-vpn-for-android-enterprise-work-profiles----1333705---"></a>Obsługa zawsze włączonej sieci VPN dla profilów roboczych systemu Android dla firm <!-- 1333705 -->
Dzięki tej aktualizacji będziesz mieć możliwość używania zawsze włączonych połączeń sieci VPN na urządzeniach z systemem Android dla firm dzięki zarządzanym profilom służbowym. Zawsze włączone połączenia sieci VPN pozostają aktywne lub są natychmiast przywracane, gdy użytkownik odblokuje urządzenie, gdy urządzenie uruchomi się ponownie lub gdy zmieni się sieć bezprzewodowa. Połączenie można również przenieść do trybu „blokady”, który powoduje zablokowanie całego ruchu sieciowego do momentu uaktywnienia połączenia sieci VPN.
Zawsze włączoną sieć VPN możesz włączyć za pomocą ustawień **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **System Android dla firm** platforma > **Ograniczenia dotyczące urządzeń** > **Łączność**.

#### <a name="issue-scep-certificates-to-user-less-devices----1744554---"></a>Wystawianie certyfikatów protokołu SCEP dla urządzeń bez użytkowników <!-- 1744554 -->
Obecnie certyfikaty są wystawiane dla użytkowników. Dzięki tej aktualizacji certyfikaty protokołu SCEP można wystawiać dla urządzeń, w tym urządzeń bez użytkowników, takich jak kioski (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** platforma > **Certyfikat SCEP** dla profilu). Inne aktualizacje obejmują:
- Właściwość **Podmiot** w profilu SCEP jest teraz niestandardowym polem tekstowym i może zawierać nowe zmienne. 
- Właściwość **Alternatywna nazwa podmiotu (SAN)** w profilu SCEP ma teraz format tabeli i może zawierać nowe zmienne. W tabeli administrator może dodać atrybut i wypełnić wartość w niestandardowym polu tekstowym. Nazwa SAN będzie obsługiwać następujące atrybuty: 
  - systemem DNS,
  - Adres e-mail
  - UPN

  Te nowe zmienne można dodawać z tekstem statycznym w polu tekstowym wartości niestandardowej. Na przykład atrybut systemu DNS można dodać jako `DNS = {{AzureADDeviceId}}.domain.com`.

  > [!NOTE]
  > Nawiasy klamrowe, średniki i symbole potoku „{}; |” nie będą działać w tekście statycznym nazwy SAN. W nawiasy klamrowe należy ująć tylko jedną z nowych zmiennych certyfikatu urządzenia do zaakceptowania: `Subject` lub `Subject alternative name`. 

Nowe zmienne certyfikatu urządzenia:  

```
"{{AAD_Device_ID}}",
"{{Device_Serial}}",
"{{Device_IMEI}}",
"{{SerialNumber}}",
"{{IMEINumber}}",
"{{AzureADDeviceId}}",
"{{WiFiMacAddress}}",
"{{IMEI}}",
"{{DeviceName}}",
"{{FullyQualifiedDomainName}}",
"{{MEID}}",
```

> [!NOTE]
>  - Zmienna `{{FullyQualifiedDomainName}}` działa tylko w przypadku urządzeń z systemem Windows i urządzeń przyłączonych do domeny. 
>  -  Podczas określania właściwości urządzenia, takich jak numer IMEI, numer seryjny i w pełni kwalifikowana nazwa domeny w obrębie podmiotu lub nazwy SAN dla certyfikatu urządzenia, należy pamiętać, że te właściwości mogą zostać sfałszowane przez osobę z dostępem do urządzenia. 

Podczas tworzenia profilu konfiguracji protokołu w obszarze [Tworzenie profilu certyfikatu protokołu SCEP](certificates-scep-configure.md#create-a-scep-certificate-profile) będą znajdować się bieżące zmienne. 

Dotyczy: system Windows 10 i nowsze oraz system iOS, obsługiwane w sieci Wi-Fi

#### <a name="remotely-lock-uncompliant-devices----2064495---"></a>Zdalne blokowanie niezgodnych urządzeń <!-- 2064495 -->
Gdy urządzenie jest niezgodne, możesz utworzyć akcję dotyczącą zasad zgodności, która zdalnie zablokuje urządzenie. W obszarze Intune > **Zgodność urządzenia** utwórz nowe zasady lub wybierz istniejące zasady, a następnie wybierz pozycję **Właściwości**. Wybierz kolejno pozycje **Akcje dotyczące niezgodności** > **Dodaj** i wybierz opcję zdalnego blokowania urządzenia.
Obsługiwane na: 
- Android
- iOS
- macOS
- Windows 10 Mobile 
- System Windows Phone 8.1 lub nowszy 

#### <a name="windows-10-and-later-kiosk-profile-improvements-in-the-azure-portal----2748224---"></a>System Windows 10 i nowsze Ulepszenia profilu kiosku w witrynie Azure Portal <!-- 2748224 -->
Ta aktualizacja obejmuje następujące ulepszenia profilu konfiguracji urządzenia kiosku z systemem Windows 10 (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** platforma > **Kiosk (wersja zapoznawcza)** dla typu profilu): 
- Obecnie w jednym urządzeniu można utworzyć wiele profilów kiosku. Dzięki tej aktualizacji usługa Intune będzie obsługiwać tylko jeden profil kiosku na urządzenie. Jeśli nadal potrzebujesz wielu profilów kiosku w jednym urządzeniu, możesz użyć niestandardowego identyfikatora URI.
- W profilu **Kiosk z wieloma aplikacjami** można wybrać rozmiar kafelka aplikacji oraz porządek **układu menu Start** w siatce aplikacji. Jeśli wolisz szersze możliwości dostosowywania, możesz kontynuować przekazywanie pliku XML.
- Ustawienia przeglądarki kiosku są przenoszone do ustawień **kiosku**. Obecnie ustawienia **przeglądarki internetowej kiosku** mają własną kategorię w witrynie Azure Portal.
Dotyczy: System Windows 10 lub nowszy




### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="apply-autopilot-profile-to-enrolled-win-10-devices-not-already-registered-for-autopilot----1558983---"></a>Stosowanie profilu rozwiązania Autopilot do zarejestrowanych urządzeń z systemem Windows 10, które nie zostały jeszcze zarejestrowane w rozwiązaniu Autopilot <!-- 1558983 -->
Profil rozwiązania Autopilot możesz zastosować do zarejestrowanych urządzeń z systemem Windows 10, które nie zostały jeszcze zarejestrowane w rozwiązaniu Autopilot. W profilu rozwiązania Autopilot wybierz opcję **Convert all targeted devices to Autopilot** (Konwertuj wszystkie wybrane urządzenia na potrzeby rozwiązania Autopilot), aby automatycznie rejestrować urządzenia bez rozwiązania Autopilot w usłudze wdrażania rozwiązania Autopilot. Przetwarzanie rejestracji może potrwać do 48 godzin. Jeśli urządzenie nie zostało zarejestrowane i je zresetowano, rozwiązanie Autopilot przeprowadzi jego aprowizację.

#### <a name="create-and-assign-multiple-enrollment-status--page-profiles-to-azure-ad-groups----2526564---"></a>Tworzenie i przypisywanie wielu profilów strony ze stanem rejestracji do grup usługi Azure AD <!-- 2526564 -->
Teraz możesz [utworzyć i przypisać](windows-enrollment-status.md) wiele profilów strony stanu rejestracji dla grup usługi Azure ADD.

#### <a name="migration-from-device-enrollment-program-to-apple-business-manager-in-intune---2748613--"></a>Migracja z programu Device Enrollment Program do usługi Apple Business Manager w usłudze Intune <!--2748613-->
Usługa Apple Business Manager (ABM) działa w usłudze Intune i można uaktualnić konto z programu Device Enrollment Program (DEP) do usługi ABM. Proces w usłudze Intune jest taki sam. Aby uaktualnić swoje konto Apple z programu DEP do usługi ABM, przejdź na stronę [ https://support.apple.com/HT208817 ]( https://support.apple.com/HT208817).

### <a name="alert-and-enrollment-status-tabs-on-the-device-enrollment-overview-page---2748656--"></a>Karty alertów i stanu rejestracji na stronie przeglądu rejestracji urządzenia <!--2748656-->
Alerty i błędy rejestracji pojawiają się teraz na osobnych kartach na stronie przeglądu rejestracji urządzenia.

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="restricts-apps-and-block-access-to-company-resources-on-android-devices----2451462----"></a>Ograniczanie aplikacji i blokowanie dostępu do zasobów firmy na urządzeniach z systemem Android <!-- 2451462  -->  
W obszarze **Zgodność urządzenia** > **Zasady** > **Utwórz zasady** > **Android** > **Zabezpieczenia systemu** w sekcji *Bezpieczeństwo urządzenia* znajduje się nowe ustawienie o nazwie **Aplikacje z ograniczeniami**. Ustawienie **Aplikacje z ograniczeniami** używa zasad zgodności, aby zablokować dostęp do zasobów firmy, jeśli pewne aplikacje są zainstalowane na urządzeniu. Urządzenie jest uznawane za niezgodne, dopóki aplikacje z ograniczeniami nie zostaną usunięte z urządzenia.
Dotyczy: 
- Android

<!-- ########################### -->
## <a name="notices"></a>Uwagi

[!INCLUDE [Intune notices](./includes/intune-notices.md)]
