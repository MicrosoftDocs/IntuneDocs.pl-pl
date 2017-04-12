---
title: Poprzednie wersje | Microsoft Docs
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: noindex,nofollow
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 6bc3afe58d5e0f1f12c8b6c6fc62e37d01cd5132
ms.openlocfilehash: cab9833a1e1b92c156a2eb77411436289c70ad71


---

# <a name="previous-intune-releases"></a>Poprzednie wersje usługi Intune

Ta strona stanowi listę ogłoszeń opublikowanych w artykule [Co nowego w usłudze Microsoft Intune](whats-new-in-microsoft-intune.md).

[!INCLUDE[wit_nextref](../includes/whats-new-last-six-months.md)]

## <a name="july-2016"></a>Lipiec 2016

### <a name="app-management"></a>Zarządzanie aplikacjami

__Poprawa aktualizowania profilu aprowizacji aplikacji__ Biznesowe aplikacje mobilne systemu Apple iOS są tworzone za pomocą dołączonego profilu aprowizacji, a ich kod jest podpisywany przy użyciu certyfikatu. Gdy aplikacja jest uruchamiana na urządzeniu z systemem iOS, system iOS potwierdza integralność aplikacji systemu iOS i wymusza zasady zdefiniowane przez profil aprowizacji.

Certyfikat podpisywania przedsiębiorstwa używany do podpisywania aplikacji jest zwykle ważny przez 3 lata. Profil aprowizacji wygasa jednak po 1 roku. Dzięki tej aktualizacji usługa Intune udostępnia narzędzia umożliwiające aktywne wdrażanie nowych zasad profilu aprowizacji na urządzeniach, na których znajdują się aplikacje bliskie wygaśnięcia, ale certyfikat jest nadal ważny. Aby uzyskać więcej informacji, zobacz [Use iOS mobile provisioning profile policies to keep your line of business apps up to date](/intune/deploy-use/ios-mobile-app-provisioning-profiles) (Używanie zasad profilów aprowizacji aplikacji mobilnych systemu iOS, aby zapewnić aktualność aplikacji).
<!--- TFS 1280247--->

__Dostępny jest zestaw SDK platformy Xamarin dla aplikacji Intune__ Składnik Xamarin zestawu SDK aplikacji Intune umożliwia włączenie funkcji zarządzania aplikacjami mobilnymi usługi Intune w aplikacjach mobilnych dla systemów iOS i Android skompilowanych za pomocą platformy Xamarin. Składnik można znaleźć w [sklepie Xamarin](https://components.xamarin.com/view/Microsoft.Intune.MAM) lub na [stronie Microsoft Intune Github](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

### <a name="device-management"></a>Zarządzanie urządzeniami
__Zwiększenie limitów rejestracji urządzeń__ Usługa Intune zwiększyła maksymalny limit rejestracji konfigurowalnych urządzeń z 5 do 15 urządzeń dla każdego użytkownika.
<!---TFS 1289896 --->

__Integracja programu TeamViewer dla komputerów z systemem Windows z uruchomionym oprogramowaniem klienckim usługi Intune__
 Integracja oprogramowania [TeamViewer](https://www.teamviewer.com) dla komputerów z systemem Windows z uruchomionym oprogramowaniem klienckim usługi Intune umożliwia ustanawianie sesji pomocy zdalnej dla komputerów z systemem Windows w celu wsparcia działu pomocy technicznej użytkowników końcowych. Dotyczy to systemów Windows 7, 8, 8.1 i Windows 10. Aby uzyskać więcej informacji, zobacz [Typowe zadania związane z zarządzaniem komputerem z systemem Windows za pomocą klienta komputerowego usługi Microsoft Intune](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

### <a name="company-portal-updates"></a>Aktualizacje Portalu firmy

__Witryna sieci Web Portal firmy__
- **Poprawione środowisko użytkownika końcowego podczas rejestrowania urządzeń z systemem Windows**<br/>
Jeśli korzystasz z dostępu warunkowego, procedury rejestracji systemów Windows 8.1, Windows 10 Desktop i Windows 10 Mobile zostały uproszczone w witrynie internetowej Portalu firmy. Użytkownicy zobaczą teraz osobne kroki „Rejestrowanie urządzeń” i „Workplace Join”, co ułatwi sprawdzenie stanu urządzenia i ukończenie procesu po błędzie narzędzia Workplace Join (WPJ). Oddzielne kroki powinny również uprościć proces rozwiązywania problemów dla administratorów IT. Wcześniej, gdy użytkownik końcowy próbował zarejestrować urządzenie i wszystkie kroki rejestracji kończyły się pomyślnie z wyjątkiem użycia narzędzia WPJ, zarejestrowane urządzenie nie było wyświetlane na liście urządzeń do zidentyfikowania przez użytkowników, co było mylące.

__Android__
- **Aplikacja Portal firmy dla systemu Android**<br/>
Jeśli użytkownicy końcowi systemu Android widzą komunikat o błędzie stwierdzający brak wymaganego certyfikatu na urządzeniu, mogą nacisnąć przycisk „Jak rozwiązać ten problem”, aby uzyskać [kroki](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) wymagane do zainstalowania brakującego certyfikatu. Jeśli użytkownicy wykonają podane kroki, ale wciąż widzą komunikat o braku certyfikatu, proszeni są o kontakt z administratorem IT i podanie tego [linku](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), który zawiera kroki umożliwiające administratorom IT usunięcie problemu z certyfikatem.

- **Ograniczenie instalacji aplikacji ładowanych bezpośrednio do zarejestrowanych urządzeń**<br/>
Na urządzeniach z systemem Android nie można już instalować aplikacji za pośrednictwem witryny internetowej Portalu firmy, chyba że zostały zarejestrowane w usłudze Intune przy użyciu aplikacji Portal firmy usługi Intune dla systemu Android.
<!---TFS 1299082--->

__iOS__
- **Zmiany w kontach menedżerów rejestracji urządzeń w aplikacji Portal firmy dla systemu iOS**<br/>
Aby zwiększyć wydajność i skalę, usługa Intune nie pokazuje już wszystkich urządzeń menedżerów rejestracji urządzeń (DEM) w okienku **Moje urządzenia** aplikacji Portal firmy dla systemu iOS. Wyświetlane jest tylko urządzenie lokalne, na którym uruchomiono aplikację, o ile zostało zarejestrowane przez aplikację Portal firmy.

Użytkownik menedżera rejestracji urządzeń może wykonywać działania na urządzeniu lokalnym, ale zdalne zarządzanie innymi zarejestrowanymi urządzeniami można przeprowadzać tylko z konsoli administracyjnej usługi Intune. Dodatkowo w usłudze Intune wycofano używanie kont menedżera rejestracji urządzeń z programem Device Enrollment Program firmy Apple i narzędziem Apple Configurator. Obie te metody rejestracji obsługują już rejestrację bez użytkowników dla współużytkowanych urządzeń z systemem iOS.

Kont menedżera rejestracji urządzeń należy używać tylko w przypadku braku dostępności rejestracji bez użytkowników dla współużytkowanych urządzeń. Więcej informacji zawiera temat [Rejestrowanie urządzeń należących do firmy przy użyciu menedżera rejestracji urządzeń w usłudze Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### <a name="change-of-names-for-windows-features"></a>Zmiana nazw funkcji systemu Windows
- Usługa [Microsoft Passport for Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) ma teraz nazwę **Windows Hello dla firm**.
- [Ochrona danych przedsiębiorstwa](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) ma teraz nazwę **Windows Information Protection**.


## <a name="june-2016"></a>Czerwiec 2016
### <a name="intune-service-health"></a>Kondycja usługi Intune
Informacje o kondycji usługi Intune zostały przeniesione do centralnej lokalizacji z innymi usługami firmy Microsoft. Teraz znajdziesz te informacje w portalu zarządzania usługą Office 365 w obszarze Kondycja usługi. Aby uzyskać więcej informacji, zobacz [ten wpis w blogu](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### <a name="app-management"></a>Zarządzanie aplikacjami
- **Ulepszone funkcje konfiguracji zasad dotyczących danych przedsiębiorstwa w systemie Windows 10.** Wprowadzono ulepszenia funkcji konfiguracji zasad ochrony danych przedsiębiorstwa w systemie Windows 10 dotyczące tworzenia reguł aplikacji, określania definicji granic sieci i innych ustawień ochrony danych przedsiębiorstwa. Aby dowiedzieć się więcej, zobacz [Tworzenie zasad ochrony danych w przedsiębiorstwie (EDP) przy użyciu usługi Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune).


### <a name="device-management"></a>Zarządzanie urządzeniami
- **Ustawienie zasad programu Windows Defender umożliwiające ochronę przed potencjalnie niechcianymi aplikacjami.** W programie Windows Defender dodano nowe ustawienie o nazwie **Wykrywanie potencjalnie niechcianych aplikacji** do ogólnych zasad konfiguracji systemu Windows 10 Desktop i Mobile. Przy użyciu tego ustawienia możesz chronić zarejestrowane komputery stacjonarne z systemem Windows przed uruchamianiem oprogramowania sklasyfikowanego przez program Windows Defender jako potencjalnie niechciane. Można chronić komputery przed uruchamianiem tych aplikacji lub używać trybu inspekcji, aby zgłaszać zdarzenia instalowania potencjalnie niechcianych aplikacji. Aby uzyskać więcej informacji, zobacz [Ustawienia zasad systemu Windows 10 w usłudze Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).
<!---TFS 1244478--->

### <a name="conditional-access"></a>Dostęp warunkowy
- **Zasady kontroli dostępu do sieci dla usługi Intune w produkcie Cisco ISE.**  Klienci korzystający z platformy Cisco Identity Service Engine (ISE) 2.1 i usługi Microsoft Intune mogą ustawić zasady kontroli dostępu do sieci w produkcie ISE.

    W przypadku korzystania z tych zasad urządzenia, które łączą się z siecią przy użyciu sieci WiFi lub VPN, muszą spełniać następujące warunki przed udzieleniem im dostępu:

    * być zarządzane przez usługę Intune,
    * być zgodne z wdrożonymi zasadami zgodności usługi Intune.

 Użytkownicy końcowi niezgodnych urządzeń będą otrzymywali monit o zarejestrowanie się i skorygowanie wszystkich problemów ze zgodnością w celu uzyskania dostępu.
- **Dostęp warunkowy dla przeglądarki.** Możliwe jest ustawienie zasad dostępu warunkowego dla usług [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) i [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune), aby można było do nich uzyskać dostęp tylko z obsługiwanych przeglądarek internetowych i zgodnych urządzeń z systemem iOS lub Android. Użytkownicy końcowi, którzy podejmą próbę zalogowania się do witryn usługi Outlook Web Access (OWA) lub usługi SharePoint przy użyciu urządzeń z systemami iOS i Android, zostaną poproszeni o zarejestrowanie swoich urządzeń w usłudze Intune oraz rozwiązanie wszelkich problemów z niezgodnością przed ukończeniem logowania.
<!---TFS 1175844--->

- **Usługa Dynamics CRM Online obsługuje dostęp warunkowy.** Można ustawić zasady dostępu warunkowego dla usługi [Dynamics CRM Online](/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune), co umożliwia dostęp do niej tylko przez zarządzane i zgodne urządzenia z systemem iOS lub Android. Użytkownicy końcowi, którzy podejmą próbę zalogowania się do aplikacji mobilnej Dynamics CRM w systemie iOS lub Android, zostaną poproszeni o rejestrację w usłudze Intune oraz rozwiązanie wszelkich problemów z niezgodnością przed ukończeniem logowania.
<!---TFS1295358--->

### <a name="intune-company-portal-updates"></a>Aktualizacje Portalu firmy w usłudze Intune

__Aplikacja Portal firmy dla systemu Android__

- Gdy administratorzy IT zastosują nowe zasady „Wymagaj, aby urządzenia nie zezwalały na instalowanie aplikacji z nieznanych źródeł (Android 4.0+)”, użytkownikom końcowym urządzeń z systemem Android 4.0 lub nowszym zostanie wyświetlony komunikat „Instalacja z nieznanych źródeł musi zostać wyłączona”. Użytkownicy będą musieli przejść do pozycji **Ustawienia** > **Zabezpieczenia** i wyłączyć opcję **Nieznane źródła**. Link w komunikacie dotyczącym zgodności pozwala użytkownikom uzyskać więcej [informacji](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) o komunikacie i o tym, dlaczego wymagane jest wyłączenie tego ustawienia.

- Gdy administratorzy IT zastosują nowe zasady „Wymagaj, aby urządzenia miały włączone skanowanie aplikacji pod kątem zagrożeń zabezpieczeń (Android 4.0+)”, użytkownikom końcowym urządzeń z systemem Android 4.0 lub nowszym zostanie wyświetlony komunikat „Skanuj urządzenie pod kątem zagrożeń zabezpieczeń”. Użytkownicy będą musieli przejść do pozycji **Ustawienia** > **Google** > **Zabezpieczenia** i włączyć opcję **Skanuj urządzenie pod kątem zagrożeń zabezpieczeń**. Link w komunikacie dotyczącym zgodności pozwala użytkownikom uzyskać więcej [informacji](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) o komunikacie i o tym, dlaczego wymagane jest włączenie tego ustawienia.

- Gdy administratorzy IT zastosują nowe zasady „Wymagaj, aby debugowanie USB było wyłączone (Android 4.2 +)”, użytkownikom końcowym urządzeń z systemem Android 4.2 lub nowszym zostanie wyświetlony komunikat „Debugowanie USB musi zostać wyłączone”. Użytkownicy będą musieli przejść do pozycji **Ustawienia** > **Opcje dewelopera** i wyłączyć opcję **Debugowanie USB**. Link w komunikacie dotyczącym zgodności pozwala użytkownikom uzyskać więcej [informacji](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) o komunikacie i o tym, dlaczego wymagane jest wyłączenie tego ustawienia.

- Gdy administratorzy IT zastosują nową zasadę „Minimalny poziom poprawki zabezpieczeń (Android 6.0+)”, użytkownikom końcowym z urządzeniami z systemem Android 6.0 lub nowszym będzie wyświetlany komunikat „To urządzenie nie spełnia wymagań dotyczących minimalnego poziomu poprawki zabezpieczeń systemu Android”. Użytkownicy będą musieli zainstalować wymaganą poprawkę zabezpieczeń. Link w komunikacie dotyczącym zgodności pozwala użytkownikom uzyskać [informacje](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) o sposobie instalowania wymaganej poprawki zabezpieczeń i zobaczyć, która poprawka zabezpieczeń jest aktualnie zainstalowana.

__Aplikacja Portal firmy dla systemu iOS__

- Podczas instalacji aplikacji biznesowych przez użytkowników końcowych wyświetlane jest teraz usprawnione środowisko instalacyjne aplikacji. Jeśli instalacja aplikacji trwa długo, użytkownicy mogą synchronizować swoje urządzenia ręcznie, co wymusza wznowienie procesu synchronizacji. Aby przejrzeć instrukcje dla użytkowników końcowych, zobacz [Ręczne synchronizowanie urządzenia z systemem iOS](/Intune/EndUser/sync-your-device-manually-ios).

- Aplikacja Portal firmy usługi Microsoft Intune dla systemu iOS została zaktualizowana do obsługi systemu iOS w wersji 8.0 i nowszych. Ta aktualizacja oznacza, że użytkownicy końcowi mogą instalować aplikację Portal firmy i rejestrować w usłudze Intune nowe urządzenia tylko wtedy, gdy urządzenie ma zainstalowany system iOS w wersji 8.0 lub nowszej. Użytkownicy, którzy mają wcześniej zarejestrowane urządzenia z nieobsługiwaną wersją systemu iOS, mogą nadal używać aplikacji Portal firmy, która znajduje się na urządzeniu.

## <a name="may-2016"></a>Maj 2016
Wszystkie te funkcje są również obsługiwane dla wdrożeń hybrydowych (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](https://technet.microsoft.com/en-us/library/mt718155.aspx).

### <a name="documentation"></a>Dokumentacja
Zapraszamy do skorzystania z wersji zapoznawczej witryny [docs.microsoft.com](https://docs.microsoft.com/en-us/intune)!
Jest to zupełnie nowa, nowoczesna platforma zawartości zaprojektowana z myślą o tym, aby ułatwić naszym klientom zrozumienie usługi Intune oraz korzystanie z niej.
Aby przeczytać o wszystkich nowych funkcjach, zobacz [Wprowadzenie do witryny docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/)

### <a name="intune-service-health"></a>Kondycja usługi Intune
Informacje o kondycji usługi Intune zostały przeniesione do centralnej lokalizacji z innymi usługami firmy Microsoft. Teraz znajdziesz te informacje w [portalu zarządzania usługą Office 365](https://portal.office.com/Admin/Default.aspx) w obszarze **Kondycja usługi**.
Aby uzyskać więcej informacji, zobacz [ten wpis w blogu](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### <a name="app-management"></a>Zarządzanie aplikacjami
- **Zestaw SDK zarządzania aplikacjami mobilnymi: obsługa konfiguracji długości numeru PIN.** Będzie możliwe określenie długości numeru PIN dla aplikacji w ramach zarządzania aplikacjami mobilnymi, podobnie jak w przypadku numeru PIN urządzenia. Użytkownicy końcowi będą musieli zachować zgodność z określonymi nowymi ograniczeniami. Będzie wyświetlany nieco zmodyfikowany ekran numeru PIN, umożliwiający wprowadzanie dłuższych numerów. Aby uzyskać szczegółowe informacje, zobacz [Ustawienia zasad zarządzania aplikacjami mobilnymi dla systemu Android](/intune/deploy-use/android-mam-policy-settings) i [Ustawienia zasad zarządzania aplikacjami mobilnymi dla systemu iOS](/intune/deploy-use/ios-mam-policy-settings).

- **Aplikacja Skype dla firm dla systemów iOS i Android.** Aplikację Skype dla firm można teraz wskazać jako objętą [zarządzaniem aplikacjami mobilnymi bez stosowania zasad rejestracji](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). Gdy użytkownicy zalogują się, zostaną zastosowane zasady zarządzania aplikacjami mobilnymi.

- **Nowe aplikacje dostępne do zarządzania przy użyciu zasad zarządzania aplikacjami mobilnymi.** Aplikacje Microsoft Word, Excel i PowerPoint dla systemu Android teraz mogą być skojarzone z zasadami zarządzania aplikacjami mobilnymi na urządzeniach, które nie są zarejestrowane w usłudze Intune. Pełna lista obsługiwanych aplikacji jest dostępna w galerii aplikacji mobilnych usługi Microsoft Intune na stronie [partnerów aplikacji usługi Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).


### <a name="company-portal-updates"></a>Aktualizacje Portalu firmy

#### <a name="android-company-portal-app"></a>Aplikacja Portal firmy dla systemu Android
- **Wyskakujące powiadomienia dla użytkownika końcowego**: użytkownicy końcowi będą teraz otrzymywać wyskakujące powiadomienia z aplikacji Portal firmy dla systemu Android, gdy będą rejestrować lub usuwać swoje urządzenia w Portalu firmy.

- **Zmiany w kontach menedżerów rejestracji urządzeń w aplikacji Portal firmy dla systemu Android.** W celu poprawy wydajności i skalowania usługa Intune nie pokazuje już wszystkich urządzeń menedżerów rejestracji urządzeń (DEM) w okienku Moje urządzenia w aplikacji Portal firmy dla systemu Android. Wyświetlane jest tylko urządzenie lokalne, na którym uruchomiono aplikację, o ile zostało zarejestrowane przez aplikację Portal firmy. Użytkownik menedżera rejestracji urządzeń może wykonywać działania na urządzeniu lokalnym, ale zdalne zarządzanie innymi zarejestrowanymi urządzeniami można przeprowadzać tylko z konsoli administracyjnej usługi Intune.

#### <a name="company-portal-website"></a>Witryna sieci Web Portal firmy
- **Witryna sieci Web Portal firmy: transparent identyfikacji urządzenia będzie zapewniać więcej informacji użytkownikom końcowym.** Użytkownicy końcowi mogą teraz łatwiej identyfikować urządzenie, które wybrali, gdy korzystają z witryny sieci Web Portal firmy. W przypadku wybrania niewłaściwego urządzenia użytkownik będzie mógł wybrać poprawne urządzenie, naciskając link **Naciśnij tutaj** na transparencie na stronie głównej.

### <a name="service-deprecation"></a>Wycofywanie usług
- **Aplikacje Intune Viewer.** Wraz z wydaniem nowej aplikacji RMS sharing zostaną usunięte następujące aplikacje Intune Viewer, począwszy od sierpnia 2016 roku:
    - Intune AV Viewer
    - Intune PDF Viewer
    - Intune Image Viewer dla systemu Android ze sklepu Google Play

  Zalecamy, aby zamiast korzystania z aplikacji Intune Viewer używać nowej aplikacji do zarządzania prawami (RMS sharing) dla systemu Android, co pozwala na wdrożenie jednej aplikacji zamiast trzech osobnych aplikacji w celu bezpiecznego przeglądania plików firmy na urządzeniach z systemem Android. Dowiedz się więcej na temat aplikacji RMS sharing (za pomocą linku do dokumentacji).

- **Usunięcie określania grup niestandardowych jako obiektów docelowych reguł powiadomień.**
Reguły powiadomień usługi Intune definiują, do kogo będą wysyłane alerty e-mail z usługi Intune. Obecnie można konfigurować reguły powiadomień w celu wysyłania wiadomości e-mail do wszystkich użytkowników urządzeń należących do utworzonej grupy urządzeń usługi Intune. Około 1 czerwca 2016 roku określanie grup utworzonych przez użytkownika jako docelowych przestanie być obsługiwane.

    Obecnie w celu skierowania reguły powiadomień do grupy utworzonej z konsoli administracyjnej usługi Microsoft Intune można wykonać następujące czynności:

    W obszarze roboczym **Administracja** kliknij pozycję **Reguły powiadomień** > **Utwórz nową regułę**.

    W drugim kroku Kreatora tworzenia reguł powiadomień wybierz grupy urządzeń, których będzie dotyczyć dana reguła. Ten krok („Wybierz grupy urządzeń”) jest usuwany z konsoli usługi Intune.

    Wstępny plan dla tej zmiany jest następujący:
    - W czerwcu 2016 roku nowi dzierżawcy nie będą widzieć drugiego kroku Kreatora tworzenia reguł powiadomień. Nie dotyczy to jednak istniejących dzierżawców.
    - W okolicach sierpnia 2016 roku niektórzy istniejący dzierżawcy nie będą widzieć kroku „Wybierz grupy urządzeń” w kreatorze.
    - Przewidujemy, że krok „Wybierz grupy urządzeń” w kreatorze przestanie być widoczny dla wszystkich dzierżawców w okolicach października 2016 roku.


- **Zmiany w obsłudze aplikacji Portal firmy dla systemu iOS**. W najbliższych miesiącach odbędzie się aktualizacja aplikacji Portal firmy usługi Microsoft Intune dla systemu iOS, która obejmie tylko urządzenia z systemem iOS 8.0 lub nowszym. Użytkownicy nie będą mogli rejestrować nowych urządzeń z wersjami starszymi niż iOS 8.0. Zarejestrowane urządzenia z wersjami starszymi niż iOS 8.0 nadal będą zarządzane i przez ograniczony czas będzie można nadal korzystać z aplikacji Portal firmy. Jednak w celu uzyskania dostępu do najnowszych wersji aplikacji Portal firmy urządzenia muszą mieć system iOS 8.0 lub późniejszą wersję. Zalecamy powiadomienie użytkowników, aby przeprowadzili aktualizację do wersji iOS 8.0 lub nowszej w celu pełnego korzystania z nowych funkcji usługi Intune.  


## <a name="april-2016"></a>Kwiecień 2016
Wszystkie te funkcje są również obsługiwane dla klientów hybrydowych (program Configuration Manager zintegrowany z usługą Intune).

### <a name="app-management"></a>Zarządzanie aplikacjami
- **Zgodność użytkownika funkcji zarządzania aplikacjami mobilnymi.**
Teraz można wyświetlić [stan](/intune/deploy-use/monitor-mobile-app-management-policies-with-Microsoft-Intune) zasad zarządzania aplikacjami dla dowolnego użytkownika w dzierżawie usługi Azure Active Directory (AAD). Obejmuje to następujące działania:
   - Urządzenia
   - Aplikacje na urządzeniu

   Wartości stanu:

   **Zaewidencjonowano**: wskazuje, że zasady zostały wdrożone dla użytkownika, aplikacja była stosowana w kontekście pracy i pomyślnie odebrała zasady.

    **Nie zaewidencjonowano**: wskazuje, że zasady zostały wdrożone dla użytkownika, ale aplikacja nie była stosowana w kontekście pracy od tego momentu.


- **Kontrolki zarządzania aplikacjami mobilnymi zapobiegające synchronizacji kontaktów programu Outlook (Android).**
Dostępne jest nowe ustawienie do [zarządzania aplikacjami mobilnymi](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) bez rejestracji urządzeń. To ustawienie umożliwia zapobieganie synchronizacji przez aplikację kontaktów z natywną książką adresową na urządzeniach z systemem Android. Po włączeniu tego ustawienia wybrane aplikacje nie będą w stanie zapisywać kontaktów w natywnej książce adresowej. Po wyłączeniu tego ustawienia wybrane aplikacje będą w stanie zapisywać kontakty w natywnej książce adresowej. Po [zdalnym wyczyszczeniu urządzenia lub aplikacji](/intune/deploy-use/wipe-managed-company-app-data-with-Microsoft-Intune) zostaną usunięte wszystkie kontakty zapisane wcześniej w natywnej książce adresowej. To nowe ustawienie jest obsługiwane początkowo przez aplikację Outlook na urządzeniach z systemem Android.

### <a name="device-management"></a>Zarządzanie urządzeniami
- **Identyfikacja numeru telefonu dla urządzeń należących do firmy.** Telefony skategoryzowane jako firmowe są teraz identyfikowane przez pełny numer telefonu na przykład przy uruchomieniu raportu inwentaryzacyjnego urządzenia przenośnego. Numery telefonów BYOD są nadal maskowane symbolami **** i wyświetlane są tylko 4 ostatnie cyfry.


### <a name="company-portal-updates"></a>Aktualizacje Portalu firmy
**Aplikacja Portal firmy dla systemu Android** Użytkownicy, którzy nie zarejestrowali urządzeń w usłudze Intune i którzy nie mają zainstalowanych poprawnych certyfikatów, nie będą w stanie zalogować się do aplikacji Portal firmy systemu Android i zobaczą komunikat „Nie możesz się zalogować, ponieważ urządzenie nie ma wymaganego certyfikatu”. Komunikat zawiera link „Rozwiązanie problemu”, którego naciśnięcie powoduje wyświetlenie instrukcji instalacji certyfikatu. Aby zobaczyć kroki, które użytkownicy końcowi powinni wykonać w celu rozwiązania problemu, zobacz [Brak wymaganego certyfikatu urządzenia](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing).

**Aplikacja Portal firmy dla systemu iOS** Dodano obsługę akcji „pociągnij, aby odświeżyć”, umożliwiającej odświeżenie zawartości ekranu głównego, w tym aplikacji, urządzeń i danych kontaktowych działu IT. Akcja „pociągnij, aby odświeżyć” nie sprawdza informacji dotyczących zgodności i zasad. Można to zrobić, wybierając kafelek bieżącego urządzenia i naciskając przycisk **Synchronizuj**.

**Aplikacja Portal firmy w systemie Windows 10 Mobile i Windows Phone 8.1** Podczas instalacji aplikacji biznesowych przez użytkowników końcowych wyświetlane jest teraz usprawnione środowisko instalacyjne aplikacji. Jeśli instalacja aplikacji trwa długo, użytkownicy mogą synchronizować swoje urządzenia ręcznie, co wymusza wznowienie procesu synchronizacji. Aby przejrzeć instrukcje dla użytkowników końcowych, zobacz [Ręczne synchronizowanie urządzenia w celu przyspieszenia instalacji aplikacji](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually).

**Witryna sieci Web Portal firmy** Gdy użytkownicy systemów Windows 10 Mobile i Windows Phone 8.1 instalują aplikacje biznesowe, wyświetlane są następujące nowe stany zapewniające więcej informacji na temat stanu instalacji:

* **Oczekiwanie na synchronizację urządzenia** — użytkownik nacisnął pozycję „Instaluj” i urządzenie próbuje przeprowadzić synchronizację z infrastrukturą usługi Intune. Synchronizacja jest wymagana w celu ukończenia instalacji. Komunikat „Oczekiwanie na synchronizację urządzenia” to również link, który użytkownicy mogą nacisnąć w celu wyświetlenia [instrukcji](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) ręcznej synchronizacji urządzenia z usługą Intune, jeśli proces synchronizacji trwa długo lub zablokował się.
* **Pobieranie** — trwa przetwarzanie żądania pobierania użytkownika; urządzenie pobiera i instaluje aplikację.

Przed dodaniem tych stanów użytkownicy nie mieli wystarczających informacji na temat sytuacji w przypadku długich instalacji, ponieważ wyświetlany był tylko stan „Instalowanie”, który mógł pozostawać na ekranie godzinami. Dodanie nowych stanów oznacza, że zamiast kontaktować się z działem pomocy technicznej, użytkownicy mogą nacisnąć link „Oczekiwanie na synchronizację urządzenia” i wykonać instrukcje, aby wymusić wznowienie procesu synchronizacji.

>[!div class="step-by-step"]

>[&larr; **Co nowego w usłudze Intune**](whats-new-in-microsoft-intune.md)    



<!--HONumber=Feb17_HO3-->


