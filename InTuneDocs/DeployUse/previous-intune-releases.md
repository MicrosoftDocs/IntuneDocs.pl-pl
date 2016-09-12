---
title: Poprzednie wersje | Microsoft Intune
description: 
keywords: 
author: Lindavr
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 57570fcf2f738b68a01bb1c5fc8962c7ef117920
ms.openlocfilehash: 43546721245f92309d86c496dbcde7900a598ed0


---

# Poprzednie wersje usługi Intune
## Lipiec 2016
### Zarządzanie aplikacjami
#### Poprawa aktualizowania profilu aprowizacji aplikacji
Biznesowe aplikacje mobilne systemu Apple iOS są tworzone za pomocą dołączonego profilu aprowizacji, a ich kod jest podpisywany przy użyciu certyfikatu. Gdy aplikacja jest uruchamiana na urządzeniu z systemem iOS, system iOS potwierdza integralność aplikacji systemu iOS i wymusza zasady zdefiniowane przez profil aprowizacji.

Certyfikat podpisywania przedsiębiorstwa używany do podpisywania aplikacji jest zwykle ważny przez 3 lata. Profil aprowizacji wygasa jednak po 1 roku. Dzięki tej aktualizacji usługa Intune udostępnia narzędzia umożliwiające aktywne wdrażanie nowych zasad profilu aprowizacji na urządzeniach, na których znajdują się aplikacje bliskie wygaśnięcia, ale certyfikat jest nadal ważny. Aby uzyskać więcej informacji, zobacz [Use iOS mobile provisioning profile policies to keep your line of business apps up to date](/intune/deploy-use/ios-mobile-app-provisioning-profiles) (Używanie zasad profilów aprowizacji aplikacji mobilnych systemu iOS, aby zapewnić aktualność aplikacji).
<!--- TFS 1280247--->
#### Dostępny jest zestaw SDK platformy Xamarin dla aplikacji Intune
Składnik Xamarin zestawu SDK aplikacji Intune umożliwia włączenie funkcji zarządzania aplikacją mobilną Intune na urządzeniach przenośnych z systemem iOS i Android skompilowanych za pomocą platformy Xamarin. Składnik można znaleźć w [sklepie Xamarin](https://components.xamarin.com/view/Microsoft.Intune.MAM) lub na [stronie Microsoft Intune Github](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

### Zarządzanie urządzeniami
#### Zwiększenie limitów rejestracji urządzeń
Usługa Intune zwiększyła maksymalny limit rejestracji konfigurowalnych urządzeń z 5 na 15 urządzeń dla każdego użytkownika.
<!---TFS 1289896 --->

#### Integracja programu TeamViewer dla komputerów z systemem Windows z uruchomionym oprogramowaniem klienckim usługi Intune
Integracja oprogramowania [TeamViewer](https://www.teamviewer.com) dla komputerów z systemem Windows z uruchomionym oprogramowaniem klienckim usługi Intune umożliwia ustanawianie sesji pomocy zdalnej dla komputerów z systemem Windows w celu wsparcia działu pomocy technicznej użytkowników końcowych. Dotyczy to systemów Windows 7, 8, 8.1 i Windows 10. Aby uzyskać więcej informacji, zobacz [Typowe zadania związane z zarządzaniem komputerem z systemem Windows za pomocą klienta komputerowego usługi Microsoft Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).
<!---TFS 1284856--->

### Aktualizacje Portalu firmy
#### Witryna sieci Web Portal firmy
- **Poprawione środowisko użytkownika końcowego podczas rejestrowania urządzeń z systemem Windows**<br/>
Jeśli korzystasz z dostępu warunkowego, procedury rejestracji systemów Windows 8.1, Windows 10 Desktop i Windows 10 Mobile zostały uproszczone w witrynie internetowej Portalu firmy. Użytkownicy zobaczą teraz osobne kroki „Rejestrowanie urządzeń” i „Workplace Join”, co ułatwi sprawdzenie stanu urządzenia i ukończenie procesu po błędzie narzędzia Workplace Join (WPJ). Oddzielne kroki powinny również uprościć proces rozwiązywania problemów dla administratorów IT. Wcześniej, gdy użytkownik końcowy próbował zarejestrować urządzenie i wszystkie kroki rejestracji kończyły się pomyślnie z wyjątkiem użycia narzędzia WPJ, zarejestrowane urządzenie nie było wyświetlane na liście urządzeń do zidentyfikowania przez użytkowników, co było mylące.

#### Android
- **Aplikacja Portal firmy dla systemu Android**<br/>
Jeśli użytkownicy końcowi systemu Android widzą komunikat o błędzie stwierdzający brak wymaganego certyfikatu na urządzeniu, mogą nacisnąć przycisk „Jak rozwiązać ten problem”, aby uzyskać [kroki](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) wymagane do zainstalowania brakującego certyfikatu. Jeśli użytkownicy wykonają podane kroki, ale wciąż widzą komunikat o braku certyfikatu, proszeni są o kontakt z administratorem IT i podanie tego [linku](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), który zawiera kroki umożliwiające administratorom IT usunięcie problemu z certyfikatem.

- **Ograniczenie instalacji aplikacji ładowanych bezpośrednio do zarejestrowanych urządzeń**<br/>
Na urządzeniach z systemem Android nie można już instalować aplikacji za pośrednictwem witryny internetowej Portalu firmy, chyba że zostały zarejestrowane w usłudze Intune przy użyciu aplikacji Portal firmy usługi Intune dla systemu Android.
<!---TFS 1299082--->

#### iOS
- **Zmiany w kontach menedżerów rejestracji urządzeń w aplikacji Portal firmy dla systemu iOS**<br/>
Aby zwiększyć wydajność i skalę, usługa Intune nie pokazuje już wszystkich urządzeń menedżerów rejestracji urządzeń (DEM) w okienku **Moje urządzenia** aplikacji Portal firmy dla systemu iOS. Wyświetlane jest tylko urządzenie lokalne, na którym uruchomiono aplikację, o ile zostało zarejestrowane przez aplikację Portal firmy.

Użytkownik menedżera rejestracji urządzeń może wykonywać działania na urządzeniu lokalnym, ale zdalne zarządzanie innymi zarejestrowanymi urządzeniami można przeprowadzać tylko z konsoli administracyjnej usługi Intune. Dodatkowo w usłudze Intune wycofano używanie kont menedżera rejestracji urządzeń z programem Device Enrollment Program firmy Apple i narzędziem Apple Configurator. Obie te metody rejestracji obsługują już rejestrację bez użytkowników dla współużytkowanych urządzeń z systemem iOS.

Kont menedżera rejestracji urządzeń należy używać tylko w przypadku braku dostępności rejestracji bez użytkowników dla współużytkowanych urządzeń. Więcej informacji zawiera temat [Rejestrowanie urządzeń należących do firmy przy użyciu menedżera rejestracji urządzeń w usłudze Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### Zmiana nazw funkcji systemu Windows
- Usługa [Microsoft Passport for Windows](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) ma teraz nazwę **Windows Hello dla firm**.
- [Ochrona danych przedsiębiorstwa](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) ma teraz nazwę **Windows Information Protection**.

## Czerwiec 2016
### Kondycja usługi Intune
Informacje o kondycji usługi Intune zostały przeniesione do centralnej lokalizacji z innymi usługami firmy Microsoft. Teraz znajdziesz te informacje w portalu zarządzania usługą Office 365 w obszarze Kondycja usługi. Aby uzyskać więcej informacji, zobacz [ten wpis w blogu](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### Zarządzanie aplikacjami
- **Ulepszone funkcje konfiguracji zasad dotyczących danych przedsiębiorstwa w systemie Windows 10.** Wprowadzono ulepszenia funkcji konfiguracji zasad ochrony danych przedsiębiorstwa w systemie Windows 10 dotyczące tworzenia reguł aplikacji, określania definicji granic sieci i innych ustawień ochrony danych przedsiębiorstwa. Aby dowiedzieć się więcej, zobacz [Tworzenie zasad ochrony danych w przedsiębiorstwie (EDP) przy użyciu usługi Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune).


### Zarządzanie urządzeniami
- **Ustawienie zasad programu Windows Defender umożliwiające ochronę przed potencjalnie niechcianymi aplikacjami.** W programie Windows Defender dodano nowe ustawienie o nazwie **Wykrywanie potencjalnie niechcianych aplikacji** do ogólnych zasad konfiguracji systemu Windows 10 Desktop i Mobile. Przy użyciu tego ustawienia możesz chronić zarejestrowane komputery stacjonarne z systemem Windows przed uruchamianiem oprogramowania sklasyfikowanego przez program Windows Defender jako potencjalnie niechciane. Można chronić komputery przed uruchamianiem tych aplikacji lub używać trybu inspekcji, aby zgłaszać zdarzenia instalowania potencjalnie niechcianych aplikacji. Aby uzyskać więcej informacji, zobacz [Ustawienia zasad systemu Windows 10 w usłudze Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).
<!---TFS 1244478--->

### Dostęp warunkowy
- **Zasady kontroli dostępu do sieci dla usługi Intune w produkcie Cisco ISE.**  Klienci korzystający z platformy Cisco Identity Service Engine (ISE) 2.1 i usługi Microsoft Intune mogą ustawić zasady kontroli dostępu do sieci w produkcie ISE.

    W przypadku korzystania z tych zasad urządzenia, które łączą się z siecią przy użyciu sieci WiFi lub VPN, muszą spełniać następujące warunki przed udzieleniem im dostępu:

    * być zarządzane przez usługę Intune,
    * być zgodne z wdrożonymi zasadami zgodności usługi Intune.

 Użytkownicy końcowi niezgodnych urządzeń będą otrzymywali monit o zarejestrowanie się i skorygowanie wszystkich problemów ze zgodnością w celu uzyskania dostępu.
- **Dostęp warunkowy dla przeglądarki.** Możliwe jest ustawienie zasad dostępu warunkowego dla usług [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md) i [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md), aby można było do nich uzyskać dostęp tylko z obsługiwanych przeglądarek internetowych i zgodnych urządzeń z systemem iOS lub Android. Użytkownicy końcowi, którzy podejmą próbę zalogowania się do witryn usługi Outlook Web Access (OWA) lub usługi SharePoint przy użyciu urządzeń z systemami iOS i Android, zostaną poproszeni o zarejestrowanie swoich urządzeń w usłudze Intune oraz rozwiązanie wszelkich problemów z niezgodnością przed ukończeniem logowania.
<!---TFS 1175844--->

- **Usługa Dynamics CRM Online obsługuje dostęp warunkowy.** Można ustawić zasady dostępu warunkowego dla usługi [Dynamics CRM Online](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md), co umożliwia dostęp do niej tylko przez zarządzane i zgodne urządzenia z systemem iOS lub Android. Użytkownicy końcowi, którzy podejmą próbę zalogowania się do aplikacji mobilnej Dynamics CRM w systemie iOS lub Android, zostaną poproszeni o rejestrację w usłudze Intune oraz rozwiązanie wszelkich problemów z niezgodnością przed ukończeniem logowania.
<!---TFS1295358--->

##Aktualizacje Portalu firmy

#### Aplikacja Portal firmy dla systemu Android

- Gdy administratorzy IT zastosują nowe zasady „Wymagaj, aby urządzenia nie zezwalały na instalowanie aplikacji z nieznanych źródeł (Android 4.0+)”, użytkownikom końcowym urządzeń z systemem Android 4.0 lub nowszym zostanie wyświetlony komunikat „Instalacja z nieznanych źródeł musi zostać wyłączona”. Użytkownicy będą musieli przejść do pozycji **Ustawienia** > **Zabezpieczenia** i wyłączyć opcję **Nieznane źródła**. Link w komunikacie dotyczącym zgodności pozwala użytkownikom uzyskać więcej [informacji](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) o komunikacie i o tym, dlaczego wymagane jest wyłączenie tego ustawienia.

- Gdy administratorzy IT zastosują nowe zasady „Wymagaj, aby urządzenia miały włączone skanowanie aplikacji pod kątem zagrożeń zabezpieczeń (Android 4.0+)”, użytkownikom końcowym urządzeń z systemem Android 4.0 lub nowszym zostanie wyświetlony komunikat „Skanuj urządzenie pod kątem zagrożeń zabezpieczeń”. Użytkownicy będą musieli przejść do pozycji **Ustawienia** > **Google** > **Zabezpieczenia** i włączyć opcję **Skanuj urządzenie pod kątem zagrożeń zabezpieczeń**. Link w komunikacie dotyczącym zgodności pozwala użytkownikom uzyskać więcej [informacji](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) o komunikacie i o tym, dlaczego wymagane jest włączenie tego ustawienia.

- Gdy administratorzy IT zastosują nowe zasady „Wymagaj, aby debugowanie USB było wyłączone (Android 4.2 +)”, użytkownikom końcowym urządzeń z systemem Android 4.2 lub nowszym zostanie wyświetlony komunikat „Debugowanie USB musi zostać wyłączone”. Użytkownicy będą musieli przejść do pozycji **Ustawienia** > **Opcje dewelopera** i wyłączyć opcję **Debugowanie USB**. Link w komunikacie dotyczącym zgodności pozwala użytkownikom uzyskać więcej [informacji](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) o komunikacie i o tym, dlaczego wymagane jest wyłączenie tego ustawienia.

- Gdy administratorzy IT zastosują nową zasadę „Minimalny poziom poprawki zabezpieczeń (Android 6.0+)”, użytkownikom końcowym z urządzeniami z systemem Android 6.0 lub nowszym będzie wyświetlany komunikat „To urządzenie nie spełnia wymagań dotyczących minimalnego poziomu poprawki zabezpieczeń systemu Android”. Użytkownicy będą musieli zainstalować wymaganą poprawkę zabezpieczeń. Link w komunikacie dotyczącym zgodności pozwala użytkownikom uzyskać [informacje](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) o sposobie instalowania wymaganej poprawki zabezpieczeń i zobaczyć, która poprawka zabezpieczeń jest aktualnie zainstalowana.

#### Aplikacja Portal firmy dla systemu iOS

- Podczas instalacji aplikacji biznesowych przez użytkowników końcowych wyświetlane jest teraz usprawnione środowisko instalacyjne aplikacji. Jeśli instalacja aplikacji trwa długo, użytkownicy mogą synchronizować swoje urządzenia ręcznie, co wymusza wznowienie procesu synchronizacji. Aby przejrzeć instrukcje dla użytkowników końcowych, zobacz [Ręczne synchronizowanie urządzenia z systemem iOS](/Intune/EndUser/sync-your-device-manually-ios).

- Aplikacja Portal firmy usługi Microsoft Intune dla systemu iOS została zaktualizowana do obsługi systemu iOS w wersji 8.0 i nowszych. Ta aktualizacja oznacza, że użytkownicy końcowi mogą instalować aplikację Portal firmy i rejestrować w usłudze Intune nowe urządzenia tylko wtedy, gdy urządzenie ma zainstalowany system iOS w wersji 8.0 lub nowszej. Użytkownicy, którzy mają wcześniej zarejestrowane urządzenia z nieobsługiwaną wersją systemu iOS, mogą nadal używać aplikacji Portal firmy, która znajduje się na urządzeniu.


## Maj 2016

Wszystkie te funkcje są również obsługiwane dla wdrożeń hybrydowych (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](https://technet.microsoft.com/en-us/library/mt718155.aspx).

### Dokumentacja
Zapraszamy do skorzystania z wersji zapoznawczej witryny [docs.microsoft.com](https://docs.microsoft.com/en-us/intune)!
Jest to zupełnie nowa, nowoczesna platforma zawartości zaprojektowana z myślą o tym, aby ułatwić naszym klientom zrozumienie usługi Intune oraz korzystanie z niej.
Aby przeczytać o wszystkich nowych funkcjach, zobacz [Wprowadzenie do witryny docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/)

### Kondycja usługi Intune
Informacje o kondycji usługi Intune zostały przeniesione do centralnej lokalizacji z innymi usługami firmy Microsoft. Teraz znajdziesz te informacje w [portalu zarządzania usługą Office 365](https://portal.office.com/Admin/Default.aspx) w obszarze **Kondycja usługi**.
Aby uzyskać więcej informacji, zobacz [ten wpis w blogu](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).


### Zarządzanie aplikacjami
- **Zestaw SDK zarządzania aplikacjami mobilnymi: obsługa konfiguracji długości numeru PIN.** Będzie możliwe określenie długości numeru PIN dla aplikacji w ramach zarządzania aplikacjami mobilnymi, podobnie jak w przypadku numeru PIN urządzenia. Użytkownicy końcowi będą musieli zachować zgodność z określonymi nowymi ograniczeniami. Będzie wyświetlany nieco zmodyfikowany ekran numeru PIN, umożliwiający wprowadzanie dłuższych numerów. Aby uzyskać szczegółowe informacje, zobacz [Ustawienia zasad zarządzania aplikacjami mobilnymi dla systemu Android](android-mam-policy-settings.md) i [Ustawienia zasad zarządzania aplikacjami mobilnymi dla systemu iOS](ios-mam-policy-settings.md).

- **Aplikacja Skype dla firm dla systemów iOS i Android.** Aplikację Skype dla firm można teraz wskazać jako objętą [zarządzaniem aplikacjami mobilnymi bez stosowania zasad rejestracji](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md). Gdy użytkownicy zalogują się, zostaną zastosowane zasady zarządzania aplikacjami mobilnymi.

- **Nowe aplikacje dostępne do zarządzania przy użyciu zasad zarządzania aplikacjami mobilnymi.** Aplikacje Microsoft Word, Excel i PowerPoint dla systemu Android teraz mogą być skojarzone z zasadami zarządzania aplikacjami mobilnymi na urządzeniach, które nie są zarejestrowane w usłudze Intune. Pełna lista obsługiwanych aplikacji jest dostępna w galerii aplikacji mobilnych usługi Microsoft Intune na stronie [partnerów aplikacji usługi Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).


### Aktualizacje Portalu firmy

#### Aplikacja Portal firmy dla systemu Android
- **Wyskakujące powiadomienia dla użytkownika końcowego**: użytkownicy końcowi będą teraz otrzymywać wyskakujące powiadomienia z aplikacji Portal firmy dla systemu Android, gdy będą rejestrować lub usuwać swoje urządzenia w Portalu firmy.

- **Zmiany w kontach menedżerów rejestracji urządzeń w aplikacji Portal firmy dla systemu Android.** W celu poprawy wydajności i skalowania usługa Intune nie pokazuje już wszystkich urządzeń menedżerów rejestracji urządzeń (DEM) w okienku Moje urządzenia w aplikacji Portal firmy dla systemu Android. Wyświetlane jest tylko urządzenie lokalne, na którym uruchomiono aplikację, o ile zostało zarejestrowane przez aplikację Portal firmy. Użytkownik menedżera rejestracji urządzeń może wykonywać działania na urządzeniu lokalnym, ale zdalne zarządzanie innymi zarejestrowanymi urządzeniami można przeprowadzać tylko z konsoli administracyjnej usługi Intune.

#### Witryna sieci Web Portal firmy
- **Witryna sieci Web Portal firmy: transparent identyfikacji urządzenia będzie zapewniać więcej informacji użytkownikom końcowym.** Użytkownicy końcowi mogą teraz łatwiej identyfikować urządzenie, które wybrali, gdy korzystają z witryny sieci Web Portal firmy. W przypadku wybrania niewłaściwego urządzenia użytkownik będzie mógł wybrać poprawne urządzenie, naciskając link **Naciśnij tutaj** na transparencie na stronie głównej.

## Wkrótce
- **Dołączanie w interfejsie użytkownika Centrum wiadomości**. W ramach migracji usługi Intune do [portalu zarządzania usługą Office 365](https://portal.office.com/) rozpoczniemy korzystanie z Centrum wiadomości portalu w celu informowania o nowych funkcjach i przesyłania innych powiadomień. Ponadto po zainstalowaniu towarzyszącej administracyjnej aplikacji mobilnej usługi Office 365 możesz otrzymywać powiadomienia na telefonie komórkowym oraz łatwo przekazywać wszelkie komunikaty użytkownikom i aliasom dystrybucyjnym.
Od majowej wersji zaczniemy używać Centrum wiadomości w celu powiadamiania o ukończeniu aktualizacji oraz dołączymy informacje o nowych i ulepszonych funkcjach usługi Intune. Sprawdź Centrum wiadomości już dzisiaj, logując się do [portalu zarządzania usługi Office 365](https://portal.office.com/) i wybierając opcję CENTRUM WIADOMOŚCI w lewym okienku nawigacji.

- **Zmiany dotyczące kont menedżerów rejestracji urządzeń**. W celu poprawy wydajności i skalowania usługa Intune nie pokazuje już **wszystkich** urządzeń menedżerów rejestracji urządzeń (DEM) w okienku **Moje urządzenia** aplikacji Portal firmy dla systemu iOS. Wyświetlane jest tylko urządzenie lokalne, na którym uruchomiono aplikację, o ile zostało zarejestrowane przez aplikację Portal firmy. Użytkownik menedżera rejestracji urządzeń może wykonywać działania na urządzeniu lokalnym, ale zdalne zarządzanie innymi zarejestrowanymi urządzeniami można przeprowadzać tylko z konsoli administracyjnej usługi Intune. Dodatkowo w usłudze Intune wycofano używanie kont menedżera rejestracji urządzeń z programem Device Enrollment Program firmy Apple i narzędziem Apple Configurator. Obie te metody rejestracji obsługują już rejestrację bez użytkowników dla współużytkowanych urządzeń z systemem iOS. Kont menedżera rejestracji urządzeń należy używać tylko w przypadku braku dostępności rejestracji bez użytkowników dla współużytkowanych urządzeń.

### Plan chmury
Śledź na bieżąco rozwój usługi Intune, korzystając z [planu platformy w chmurze](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Wycofywanie usług
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


## Kwiecień 2016
Wszystkie te funkcje są również obsługiwane dla klientów hybrydowych (program Configuration Manager zintegrowany z usługą Intune).
### Zarządzanie aplikacjami
- **Zgodność użytkownika funkcji zarządzania aplikacjami mobilnymi.**
Teraz można wyświetlić [stan](monitor-mobile-app-management-policies-with-Microsoft-Intune.md) zasad zarządzania aplikacjami dla dowolnego użytkownika w dzierżawie usługi Azure Active Directory (AAD). Obejmuje to następujące działania:
   - Urządzenia
   - Aplikacje na urządzeniu

   Wartości stanu:

   **Zaewidencjonowano**: wskazuje, że zasady zostały wdrożone dla użytkownika, aplikacja była stosowana w kontekście pracy i pomyślnie odebrała zasady.

    **Nie zaewidencjonowano**: wskazuje, że zasady zostały wdrożone dla użytkownika, ale aplikacja nie była stosowana w kontekście pracy od tego momentu.


- **Kontrolki zarządzania aplikacjami mobilnymi zapobiegające synchronizacji kontaktów programu Outlook (Android).**
Dostępne jest nowe ustawienie do [zarządzania aplikacjami mobilnymi](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) bez rejestracji urządzeń. To ustawienie umożliwia zapobieganie synchronizacji przez aplikację kontaktów z natywną książką adresową na urządzeniach z systemem Android. Po włączeniu tego ustawienia wybrane aplikacje nie będą w stanie zapisywać kontaktów w natywnej książce adresowej. Po wyłączeniu tego ustawienia wybrane aplikacje będą w stanie zapisywać kontakty w natywnej książce adresowej. Po [zdalnym wyczyszczeniu urządzenia lub aplikacji](wipe-managed-company-app-data-with-Microsoft-Intune.md) zostaną usunięte wszystkie kontakty zapisane wcześniej w natywnej książce adresowej. To nowe ustawienie jest obsługiwane początkowo przez aplikację Outlook na urządzeniach z systemem Android.

### Zarządzanie urządzeniami
- **Identyfikacja numeru telefonu dla urządzeń należących do firmy.** Telefony skategoryzowane jako firmowe są teraz identyfikowane przez pełny numer telefonu na przykład przy uruchomieniu raportu inwentaryzacyjnego urządzenia przenośnego. Numery telefonów BYOD są nadal maskowane symbolami **** i wyświetlane są tylko 4 ostatnie cyfry.


### Aktualizacje Portalu firmy
**Aplikacja Portal firmy dla systemu Android** Użytkownicy, którzy nie zarejestrowali urządzeń w usłudze Intune i którzy nie mają zainstalowanych poprawnych certyfikatów, nie będą w stanie zalogować się do aplikacji Portal firmy systemu Android i zobaczą komunikat „Nie możesz się zalogować, ponieważ urządzenie nie ma wymaganego certyfikatu”. Komunikat zawiera link „Rozwiązanie problemu”, którego naciśnięcie powoduje wyświetlenie instrukcji instalacji certyfikatu. Aby zobaczyć kroki, które użytkownicy końcowi powinni wykonać w celu rozwiązania problemu, zobacz [Brak wymaganego certyfikatu urządzenia](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing).

**Aplikacja Portal firmy dla systemu iOS** Dodano obsługę akcji „pociągnij, aby odświeżyć”, umożliwiającej odświeżenie zawartości ekranu głównego, w tym aplikacji, urządzeń i danych kontaktowych działu IT. Akcja „pociągnij, aby odświeżyć” nie sprawdza informacji dotyczących zgodności i zasad. Można to zrobić, wybierając kafelek bieżącego urządzenia i naciskając przycisk **Synchronizuj**.

**Aplikacja Portal firmy w systemie Windows 10 Mobile i Windows Phone 8.1** Podczas instalacji aplikacji biznesowych przez użytkowników końcowych wyświetlane jest teraz usprawnione środowisko instalacyjne aplikacji. Jeśli instalacja aplikacji trwa długo, użytkownicy mogą synchronizować swoje urządzenia ręcznie, co wymusza wznowienie procesu synchronizacji. Aby przejrzeć instrukcje dla użytkowników końcowych, zobacz [Ręczne synchronizowanie urządzenia w celu przyspieszenia instalacji aplikacji](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually).

**Witryna sieci Web Portal firmy** Gdy użytkownicy systemów Windows 10 Mobile i Windows Phone 8.1 instalują aplikacje biznesowe, wyświetlane są następujące nowe stany zapewniające więcej informacji na temat stanu instalacji:

* **Oczekiwanie na synchronizację urządzenia** — użytkownik nacisnął pozycję „Instaluj” i urządzenie próbuje przeprowadzić synchronizację z infrastrukturą usługi Intune. Synchronizacja jest wymagana w celu ukończenia instalacji. Komunikat „Oczekiwanie na synchronizację urządzenia” to również link, który użytkownicy mogą nacisnąć w celu wyświetlenia [instrukcji](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) ręcznej synchronizacji urządzenia z usługą Intune, jeśli proces synchronizacji trwa długo lub zablokował się.
* **Pobieranie** — trwa przetwarzanie żądania pobierania użytkownika; urządzenie pobiera i instaluje aplikację.

Przed dodaniem tych stanów użytkownicy nie mieli wystarczających informacji na temat sytuacji w przypadku długich instalacji, ponieważ wyświetlany był tylko stan „Instalowanie”, który mógł pozostawać na ekranie godzinami. Dodanie nowych stanów oznacza, że zamiast kontaktować się z działem pomocy technicznej, użytkownicy mogą nacisnąć link „Oczekiwanie na synchronizację urządzenia” i wykonać instrukcje, aby wymusić wznowienie procesu synchronizacji.


## Marzec 2016
### Co nowego w wersji z 29 marca 2016 r.
Z wyjątkiem aktualizacji ogólnych zasad konfiguracji systemu Windows 10, wszystkie funkcje w wersji opublikowanej 29 marca 2016 r. są również obsługiwane dla klientów hybrydowych (program Configuration Manager zintegrowany z usługą Intune). Hybrydowa obsługa dla aktualizacji ogólnych zasad konfiguracji systemu Windows 10 będzie dostępna wkrótce. Należy pamiętać, że niektóre z tych funkcji mogą wymagać najnowszej wersji programu Configuration Manager.

### Zarządzanie aplikacjami
- **Kontrolki zarządzania aplikacjami mobilnymi zapobiegające synchronizacji kontaktów programu Outlook (iOS).** Dostępne jest nowe ustawienie do zarządzania aplikacjami mobilnymi bez rejestracji urządzeń. To ustawienie umożliwia zapobieganie synchronizacji przez aplikację kontaktów z natywną książką adresową na urządzeniach z systemem iOS. Po włączeniu tego ustawienia aplikacja nie będzie w stanie zapisywać kontaktów w natywnej książce adresowej. Po wyłączeniu tego ustawienia aplikacja będzie w stanie zapisywać kontakty w natywnej książce adresowej. Po selektywnym wyczyszczeniu urządzenia zostaną usunięte wszystkie kontakty zapisane wcześniej w natywnej książce adresowej. To nowe ustawienie jest obsługiwane przez aplikację Outlook na urządzeniach z systemem iOS. Aby uzyskać więcej informacji dotyczących tego i innych ustawień, zobacz [Tworzenie i wdrażanie zasad MAM](https://technet.microsoft.com/en-us/library/dn292747.aspx).

### Kontrola dostępu
- **Usługa Skype dla firm Online obsługuje dostęp warunkowy.** Możesz określić zasady dostępu warunkowego dla usługi Skype dla firm Online, co umożliwia dostęp do niej tylko przez zarządzane i zgodne urządzenia z systemem iOS lub Android. Użytkownicy końcowi, którzy podejmą próbę zalogowania się do aplikacji mobilnej Skype dla firm w systemie iOS lub Android, zostaną poproszeni o rejestrację w usłudze Intune oraz rozwiązanie wszystkich problemów z niezgodnością przed zakończeniem logowania. Aby uzyskać szczegółowe informacje, zobacz [Zarządzanie dostępem do usługi Skype dla firm Online](https://technet.microsoft.com/en-us/library/mt695297.aspx).

### Zarządzanie urządzeniami
- **Obsługa usługi Intune dla systemu iOS 9.3.** W poniedziałek 21 marca firma Apple ogłosiła dostępność systemu iOS 9.3. Firma Microsoft intensywnie pracowała nad zapewnieniem zgodności usługi Microsoft Intune z najnowszym systemem operacyjnym firmy Apple dla urządzeń przenośnych. [Z przyjemnością ogłaszamy, że usługa Intune obsługuje już zarządzanie urządzeniami z systemem iOS 9.3](https://blogs.technet.microsoft.com/microsoftintune/2016/03/23/microsoft-intune-provides-support-for-ios-9-3/).

  Wszystkie obecnie dostępne funkcje usługi Intune do zarządzania urządzeniami z systemem iOS będą nadal działać bezproblemowo po uaktualnieniu urządzeń do systemu iOS 9.3 przez użytkowników. Ponadto system iOS 9.3 jest teraz obsługiwany również dla klientów hybrydowych (program Configuration Manager zintegrowany z usługą Intune).

- **Ogólne zasady konfiguracji systemu Windows 10 zawierają teraz ustawienia służące do zarządzania usługą Windows Defender na zarejestrowanych komputerach z systemem Windows 10.** Aby uzyskać więcej informacji, zobacz [Ustawienia zasad konfiguracji systemu Windows 10 w usłudze Microsoft Intune](https://technet.microsoft.com/en-us/library/mt404697.aspx).


### Portal firmy

- **Pakiety aplikacji systemu Windows dostępne bezpośrednio z witryny sieci Web portalu firmy.** Użytkownicy komputerów z systemami Windows 8, Windows 8.1 i Windows RT mogą teraz instalować pakiety aplikacji systemu Windows (z rozszerzeniem appx) bezpośrednio z witryny Portalu firmy. Poprzednio konieczne było wdrożenie aplikacji lub użytkownicy musieli instalować aplikację Portal firmy na urządzeniach w celu instalacji aplikacji.

- **Użytkownicy mogą zdalnie blokować swoje urządzenie z poziomu witryny sieci Web portalu firmy.** Do witryny sieci Web Portalu firmy dodano opcję blokady zdalnej, która umożliwia użytkownikom zdalne blokowanie urządzenia z Portalu w przypadku jego utraty lub kradzieży. Zobacz [instrukcje dla użytkowników końcowych](https://technet.microsoft.com/library/mt590895.aspx/?wt.mc_id=ui#BKMK_iwp_remote_lock). Poniższa tabela zawiera platformy obsługiwane przez funkcję blokady zdalnej autonomicznej usługi Intune oraz usługi Intune z programem Configuration Manager.

|Platforma | Szczegóły dotyczące obsługi|
|---------|----------------|
|Android |Obsługiwane|
|iOS |Obsługiwane|
|Windows 10 Mobile |Obsługiwane tylko wtedy, gdy na telefonie ustawiono kod dostępu|
|Windows 10 Desktop |Nieobsługiwane|
|Windows Phone 8.1 |Obsługiwane tylko wtedy, gdy na telefonie ustawiono kod dostępu|
|Windows Phone 8.0 |Nieobsługiwane|
|Komputer (Windows 8.0 i starsze) |Nieobsługiwane|
|Komputer (Windows 8.1) |Nieobsługiwane|

### Co nowego w wersji z 10 marca 2016 r.

### Zarządzanie aplikacjami

- ** W systemie iOS warto korzystać z funkcji „Otwórz w” dla urządzeń, które są zarejestrowane w rozwiązaniu MDM innej firmy** W celu korzystania w systemie iOS z funkcji „Otwórz w” możesz używać dowolnego dostawcy rozwiązania do zarządzania urządzeniami przenośnymi (MDM, ang. Mobile Device Management) innej firmy. Możesz konfigurować ograniczenia w ustawieniach profilu konfiguracji i wdrażać aplikacje przy użyciu funkcji [zarządzania przesyłaniem danych między aplikacjami systemu iOS](manage-data-transfer-between-ios-apps-with-microsoft-intune.md).

     Takie podejście charakteryzuje się dwoma korzyściami:

     1. Użytkownicy muszą logować się, korzystając z poświadczeń konta służbowego, zanim uzyskają dostęp do dowolnych danych korporacyjnych z usług w chmurze albo do innych aplikacji. Takie rozwiązanie zapewnia przestrzeganie zasad zarządzania aplikacjami mobilnymi (MAM, ang. Mobile App Management) podczas uzyskiwania dostępu do danych.

     2. Zarządzane profile poczty e-mail i inne aplikacje zarządzane wdrożone za pośrednictwem rozwiązania MDM innej firmy mogą udostępniać pliki i dane aplikacjom, które działają zgodnie z zasadami MAM usługi Intune.

- **Zarządzanie aplikacją Microsoft Outlook przy użyciu zasad zarządzania aplikacjami mobilnymi na urządzeniach, które nie są zarejestrowane w usłudze Intune** Możesz teraz zarządzać aplikacją Microsoft Outlook na urządzeniach, które nie są zarejestrowane w usłudze Intune, korzystając z zasad zarządzania aplikacjami mobilnymi z usługi Intune. Zaktualizowana aplikacja Microsoft Outlook obsługująca zasady zarządzania aplikacjami mobilnymi jest dostępna dla urządzeń z systemem [iOS](https://itunes.apple.com/us/app/microsoft-outlook-email-calendar/id951937596?mt=8) oraz urządzeń z systemem [Android](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook). W celu tworzenia zasad zarządzania aplikacjami mobilnymi postępuj zgodnie z instrukcjami w temacie [Tworzenie i wdrażanie zasad zarządzania aplikacjami mobilnymi](https://technet.microsoft.com/library/mt627829.aspx).  


- ** Zasady konfiguracji aplikacji mobilnych zapewniają większą elastyczność i możliwość określania szczegółów użytkowników dla aplikacji systemu iOS** Możesz podawać ustawienia użytkowników, których może potrzebować aplikacja systemu iOS, gdy zostanie otwarta. Na przykład można podać port sieci lub nazwę użytkownika. Aby uzyskać więcej informacji, zobacz [Konfigurowanie aplikacji systemu iOS przy użyciu zasad konfiguracji aplikacji mobilnych w usłudze Microsoft Intune](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md).


- **Wdrażanie w przedsiębiorstwie programu Adobe Reader dla usługi Microsoft Intune na urządzeniach zarządzanych przez usługę Intune w systemie iOS** Teraz można zarządzać aplikacją Adobe Reader dla systemu iOS na zarejestrowanych urządzeniach, stosując zasady zarządzania aplikacjami mobilnymi usługi Intune.

- **Zapewnienie, że wdrożone klipy internetowe będą otwierane w programie Managed Browser** Możesz wdrażać klipy internetowe przeznaczone dla konkretnych grup odbiorców, które można otwierać tylko przy użyciu programu Managed Browser na urządzeniach z systemem iOS i z systemem Android. Na przykład wdrażasz linki do zasobów firmowych za pośrednictwem Portalu firmy, a gdy użytkownicy przejdą do tych linków, zostaną one otwarte bezpośrednio w programie Managed Browser, gdzie mogą być chronione przez zasady zarządzania aplikacjami mobilnymi. Aby uzyskać szczegółowe informacje, zobacz [Wdrażanie aplikacji](deploy-apps.md).


- **Wyszukiwanie i dystrybucja aplikacji ze Sklepu Windows dla firm oraz zarządzanie nimi dla urządzeń z systemem Windows 10 z konsoli administratora usługi Intune** Usługa Intune obsługuje Sklep Windows dla firm, aby ułatwiać znajdowanie aplikacji i zarządzanie nimi, a także przeprowadzanie dystrybucji aplikacji na zarządzanych przez Ciebie urządzeniach z systemem Windows 10. Sklep Windows dla firm umożliwia zarządzanie procesem wdrażania i monitorowania tych aplikacji z konsoli administratora usługi Intune — tej samej konsoli, która służy do zarządzania innymi aplikacjami. W szczególności Sklep Windows dla firm zarządza zawartością i licencjonowaniem „aplikacji licencjonowanych online”. Aby uzyskać szczegółowe informacje, zobacz [Zarządzanie aplikacjami zakupionymi w Sklepie Windows dla firm](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md).


### Zarządzanie urządzeniami
- **Dystrybucja certyfikatów PFX dla urządzeń z systemem iOS** Administratorzy usługi Intune mogą tworzyć i wdrażać certyfikaty PFX systemu iOS dla sieci Wi-Fi, poczty e-mail i uwierzytelniania sieci VPN na urządzeniach z systemem iOS. Ta funkcja jest już dostępna dla urządzeń z systemami Android i Windows 10. Szczegółowe informacje zawiera temat [Zapewnianie dostępu do zasobów firmy przy użyciu profilów certyfikatów](secure-resource-access-with-certificate-profiles.md).


- **Stosowanie aplikacji i zasad do różnych grup urządzeń w oparciu o wybór kategorii użytkownika** Administratorzy usługi Intune mogą definiować niestandardowe kategorie urządzeń dla użytkowników, które można wybierać podczas rejestracji. Na przykład administratorzy mogą wymagać, aby użytkownicy określali, czy rejestrują urządzenie, którego przeznaczenie to „Kasa”, „Samochód dostawczy” czy „Pomieszczenie magazynowe”. Wybór kategorii spowoduje, że urządzenie stanie się elementem grupy urządzeń usługi Intune, z której można korzystać w celu wdrażania różnych aplikacji i zasad do zarejestrowanych urządzeń. Aby uzyskać szczegółowe informacje, zobacz temat [Kategoryzowanie urządzeń za pomocą mapowania grup urządzeń](categorize-devices-with-device-group-mapping-in-microsoft-intune.md).

### Zmiany i aktualizacje Portalu firmy oferowanego przez firmę Microsoft
W Portalu firmy w tej wersji wprowadzono następujące zmiany:

**Aplikacja Portal firmy dla systemu Android**

* Gdy użytkownicy uruchomią aplikację, która jest zarządzana przez zarządzanie aplikacjami mobilnymi, zobaczą komunikat z informacją, że aplikacja jest zarządzana przez ich firmę. W tym komunikacie można teraz wybrać link „Dowiedz się więcej”, aby uzyskać [więcej informacji](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_use_mgd_apps) o tym, co oznacza określenie „aplikacje zarządzane”. Można również nacisnąć polecenie „Nie pokazuj ponownie”, aby komunikat nie był już wyświetlany w trakcie uruchamiania aplikacji.
* Zostały dodane nowe ekrany, które prowadzą użytkowników przez proces rejestracji i udostępniają więcej informacji na temat tego, dlaczego użytkownicy powinni się rejestrować i tego, co jest i nie jest wyświetlane na zarejestrowanych urządzeniach administratorów IT. Szczegółowe informacje zawierają [instrukcje dotyczące rejestrowania](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc).
* W aplikacji Portal firmy są teraz wyświetlane komunikaty o błędach rejestracji. Wcześniej te komunikaty pojawiały się w witrynie Portal firmy. Wprowadzenie tej zmiany oznacza, że wszystkie komunikaty o błędach pojawiają się teraz tylko w jednym miejscu zamiast w kilku.


**Aplikacja Portal firmy dla systemu iOS**
* Gdy użytkownicy uruchomią aplikację, która jest zarządzana przez zarządzanie aplikacjami mobilnymi, zobaczą komunikat z informacją, że aplikacja jest zarządzana przez ich firmę. W tym komunikacie można teraz wybrać link „Dowiedz się więcej”, aby uzyskać [więcej informacji](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_use_mgd_apps) o tym, co oznacza określenie „aplikacje zarządzane”. Można również nacisnąć polecenie „Nie pokazuj ponownie”, aby komunikat nie był już wyświetlany w trakcie uruchamiania aplikacji.
* Zostały dodane nowe ekrany, które prowadzą użytkowników przez proces rejestracji i udostępniają więcej informacji na temat tego, dlaczego użytkownicy powinni się rejestrować i tego, co jest i nie jest wyświetlane na zarejestrowanych urządzeniach administratorów IT. Szczegółowe informacje zawierają [instrukcje dotyczące rejestrowania](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device).
* W aplikacji Portal firmy są teraz wyświetlane komunikaty o błędach rejestracji. Wcześniej te komunikaty pojawiały się w witrynie Portal firmy. Wprowadzenie tej zmiany oznacza, że wszystkie komunikaty o błędach pojawiają się teraz tylko w jednym miejscu zamiast w kilku.




## Luty 2016
### Zmiany i aktualizacje Portalu firmy oferowanego przez firmę Microsoft

W Portalu firmy w tej wersji wprowadzono następujące zmiany:

#### Aplikacja Portal firmy dla systemu Android
- Zostały dodane nowe ekrany, które prowadzą użytkowników przez proces rejestracji i udostępniają więcej informacji na temat tego, dlaczego użytkownicy powinni się rejestrować i tego, co jest i nie jest wyświetlane na zarejestrowanych urządzeniach administratorów IT. Szczegółowe informacje zawierają [instrukcje dotyczące rejestrowania](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc).
- W aplikacji Portal firmy są teraz wyświetlane komunikaty o błędach rejestracji. Wcześniej te komunikaty pojawiały się w witrynie Portal firmy. Wprowadzenie tej zmiany oznacza, że wszystkie komunikaty o błędach pojawiają się teraz tylko w jednym miejscu zamiast w kilku.

#### Aplikacja Portal firmy dla systemu iOS
 - Zostały dodane nowe ekrany, które prowadzą użytkowników przez proces rejestracji i udostępniają więcej informacji na temat tego, dlaczego użytkownicy powinni się rejestrować i tego, co jest i nie jest wyświetlane na zarejestrowanych urządzeniach administratorów IT. Szczegółowe informacje zawierają [instrukcje dotyczące rejestrowania](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device).

 - W aplikacji Portal firmy są teraz wyświetlane komunikaty o błędach rejestracji. Wcześniej te komunikaty pojawiały się w witrynie Portal firmy. Wprowadzenie tej zmiany oznacza, że wszystkie komunikaty o błędach pojawiają się teraz tylko w jednym miejscu zamiast w kilku.


## Styczeń 2016

### Korzystanie z zalet funkcji systemu Windows 10
* **Dostęp warunkowy i usługa zaświadczania o kondycji** Administratorzy usługi Intune mogą teraz wyświetlać stan usługi zaświadczania o kondycji systemu Windows 10 w konsoli administracyjnej usługi Intune. Zaświadczenie o kondycji urządzenia umożliwia administratorowi upewnienie się, że komputery klienckie dysponują godnymi zaufania konfiguracjami systemu BIOS, modułu TPM i oprogramowania rozruchowego. W celu obsługi zaświadczania o kondycji na urządzeniach klienckich musi działać system Windows 10 z włączonym modułem TPM 2. Zaświadczenie o kondycji urządzeń zawiera liczbę urządzeń obsługujących następujące funkcje:
    * Usługa wczesnej ochrony przed złośliwym kodem
    * Funkcja BitLocker
    * Bezpieczny rozruch
    * Integralność kodu

    Więcej szczegółów na temat ustawień dotyczących kondycji urządzeń, zebranych punktów danych i raportu zaświadczającego o kondycji zawiera temat [Wprowadzenie do zasad zgodności urządzeń w usłudze Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md). W temacie [Szczegóły usługi HAS](https://msdn.microsoft.com/en-us/library/dn934876.aspx) ta usługa została opisana szczegółowo.

* **Zarządzanie zasadami i certyfikatem usługi Windows 10 Passport dla miejsca pracy** Usługa Intune umożliwia [integrację z usługą Microsoft Passport dla miejsca pracy](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md), czyli alternatywną metodą logowania dla systemu Windows 10 korzystającą z usługi Active Directory lub konta usługi Azure Active Directory w celu zastąpienia hasła, karty inteligentnej lub wirtualnej karty inteligentnej. Usługa Passport pozwala używać do logowania gestu użytkownika zamiast hasła. Gestem użytkownika może być prosty numer PIN, uwierzytelnianie biometryczne, takie jak Windows Hello, lub urządzenie zewnętrzne, np. czytnik linii papilarnych.

* **Sieć VPN dla określonych aplikacji** Możesz wybierać aplikacje, które będą automatycznie łączyć się z siecią firmową za pośrednictwem połączenia VPN. Utwórz listę aplikacji podczas konfigurowania profilu sieci VPN zgodnie z opisem w temacie „Pomaganie użytkownikom w nawiązywaniu połączenia z siecią firmową za pomocą profilów sieci VPN w usłudze Microsoft Intune”.

* **Obsługa pełnego czyszczenia w systemie Windows 10** Obecnie można przeprowadzić pełne zdalne czyszczenie danych urządzeń komputerowych z systemem Windows 10 zarejestrowanych w usłudze Intune, korzystając z konsoli administracyjnej usługi Intune. Pełne czyszczenie danych systemu Windows 10 powoduje przywrócenie fabrycznych ustawień urządzenia.


### Aktualizacja programu zakupów zbiorczych VPP (ang. Volume Purchase Program) firmy Apple
Usługa Intune ułatwia [zarządzanie aplikacjami zakupionymi za pośrednictwem programu Apple Volume Purchase Program (VPP) dla firm](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md). Dotyczy to synchronizowania informacji o licencjach między firmą Apple i usługą Intune, a także śledzenia liczby wdrożonych kopii poszczególnych aplikacji.

### Korzystanie z numerów IMEI w celu identyfikowania urządzeń firmowych
Możesz teraz [importować międzynarodowe numery identyfikujące urządzenia przenośne (IMEI, International Mobile Equipment Identity)](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) dla platform urządzeń przenośnych, które mają numer IMEI, co ułatwia identyfikację firmowych urządzeń przenośnych. Zarejestrowane w usłudze Intune urządzenia z numerami IMEI oznakowane jako firmowe, co jest użyteczne w przypadku stosowania strategii innych niż względem urządzeń prywatnych.

### Więcej aplikacji jest teraz zgodnych z zasadami zarządzania aplikacjami mobilnymi usługi Intune
Dodatkowe aplikacje od partnerów firmy Microsoft są teraz zgodne z zasadami zarządzania aplikacjami mobilnymi (MAM) usługi Intune (dla urządzeń zarządzanych przez usługę Intune):
* Box for EMM (od firmy Box Inc) — tylko dla urządzeń z systemem iOS
* Adobe Reader (firmy Adobe) — tylko dla urządzeń z systemem Android
* Foxit PDF Reader (firmy Foxit Corporation) — dla urządzeń z systemem iOS lub Android


### Obsługa programu IE9 kończy się w styczniu
Począwszy od lutego 2016 roku program Internet Explorer 9 nie będzie już obsługiwany jako oficjalna przeglądarka do uzyskiwania dostępu do witryny sieci Web portalu firmy w usłudze Microsoft Intune, portalu konta usługi Intune i konsoli administracyjnej usługi Intune. Należy przeprowadzić migrację do programu Internet Explorer 10 lub nowszego.


>[!div class="step-by-step"]

>[&larr; **Co nowego w usłudze Intune**](whats-new-in-microsoft-intune.md)    



<!--HONumber=Aug16_HO3-->


