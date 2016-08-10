---
title: Co nowego | Microsoft Intune
description: "Sprawdź nowości w tym miesiącu i poprzednich wersjach usługi Microsoft Intune"
keywords: 
author: Lindavr
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b93c6fe16e598c6f4b0d87981de8655f3de9c8d3
ms.openlocfilehash: 051f2994c59b2886a81a50d7c72f51627064bc6a


---

# Co nowego w usłudze Microsoft Intune
Poznaj nowości w tej wersji usługi Microsoft Intune. Dowiedz się o nadchodzących zmianach, na które należy się przygotować, jak również uzyskaj informacje o poprzednich wersjach.

Wszystkie te funkcje będą również w przyszłości obsługiwane dla hybrydowych wdrożeń klientów (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

## Sierpień 2016
## Aktualizacje Portalu firmy

### Android
- **Aplikacja Portal firmy dla systemu Android**<br/>
Aplikacja Portal firmy usługi Intune dla systemu Android zapewnia obsługę „od dnia 0” nadchodzącego systemu operacyjnego Android 7.0 dla urządzeń przenośnych.  

- **Usunięcie przez Google możliwości zdalnego resetowania kodu dostępu na urządzeniach z systemem Android 7.0**<br/>
Na urządzeniach z systemem Android 7.0 administratorzy IT usługi Intune i użytkownicy końcowi nie będą mogli zdalnie zresetować kodu dostępu urządzenia, ponieważ firma Google usunęła tę możliwość dla urządzeń z systemem Android 7.0. W wersjach wcześniejszych niż Android 7.0 administratorzy IT będą nadal mogli zdalnie zresetować kod dostępu użytkownika, a użytkownicy końcowi będą nadal mogli resetować swoje kody dostępu z poziomu witryny sieci Web Portalu firmy.

## Lipiec 2016
## Zarządzanie aplikacjami
### Poprawa aktualizowania profilu aprowizacji aplikacji
Biznesowe aplikacje mobilne systemu Apple iOS są tworzone za pomocą dołączonego profilu aprowizacji, a ich kod jest podpisywany przy użyciu certyfikatu. Gdy aplikacja jest uruchamiana na urządzeniu z systemem iOS, system iOS potwierdza integralność aplikacji systemu iOS i wymusza zasady zdefiniowane przez profil aprowizacji.

Certyfikat podpisywania przedsiębiorstwa używany do podpisywania aplikacji jest zwykle ważny przez 3 lata. Profil aprowizacji wygasa jednak po 1 roku. Dzięki tej aktualizacji usługa Intune udostępnia narzędzia umożliwiające aktywne wdrażanie nowych zasad profilu aprowizacji na urządzeniach, na których znajdują się aplikacje bliskie wygaśnięcia, ale certyfikat jest nadal ważny. Aby uzyskać więcej informacji, zobacz [Use iOS mobile provisioning profile policies to keep your line of business apps up to date](/intune/deploy-use/ios-mobile-app-provisioning-profiles) (Używanie zasad profilów aprowizacji aplikacji mobilnych systemu iOS, aby zapewnić aktualność aplikacji).
<!--- TFS 1280247--->
### Dostępny jest zestaw SDK platformy Xamarin dla aplikacji Intune
Składnik Xamarin zestawu SDK aplikacji Intune umożliwia włączenie funkcji zarządzania aplikacją mobilną Intune na urządzeniach przenośnych z systemem iOS i Android skompilowanych za pomocą platformy Xamarin. Składnik można znaleźć w [sklepie Xamarin](https://components.xamarin.com/view/Microsoft.Intune.MAM) lub na [stronie Microsoft Intune Github](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

## Zarządzanie urządzeniami
### Zwiększenie limitów rejestracji urządzeń
Usługa Intune zwiększyła maksymalny limit rejestracji konfigurowalnych urządzeń z 5 na 15 urządzeń dla każdego użytkownika.
<!---TFS 1289896 --->

### Integracja programu TeamViewer dla komputerów z systemem Windows z uruchomionym oprogramowaniem klienckim usługi Intune
Integracja oprogramowania [TeamViewer](https://www.teamviewer.com) dla komputerów z systemem Windows z uruchomionym oprogramowaniem klienckim usługi Intune umożliwia ustanawianie sesji pomocy zdalnej dla komputerów z systemem Windows w celu wsparcia działu pomocy technicznej użytkowników końcowych. Dotyczy to systemów Windows 7, 8, 8.1 i Windows 10. Aby uzyskać więcej informacji, zobacz [Typowe zadania związane z zarządzaniem komputerem z systemem Windows za pomocą klienta komputerowego usługi Microsoft Intune](intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

## Aktualizacje Portalu firmy
### Witryna sieci Web Portal firmy
- **Poprawione środowisko użytkownika końcowego podczas rejestrowania urządzeń z systemem Windows**<br/>
Jeśli korzystasz z dostępu warunkowego, procedury rejestracji systemów Windows 8.1, Windows 10 Desktop i Windows 10 Mobile zostały uproszczone w witrynie internetowej Portalu firmy. Użytkownicy zobaczą teraz osobne kroki „Rejestrowanie urządzeń” i „Workplace Join”, co ułatwi sprawdzenie stanu urządzenia i ukończenie procesu po błędzie narzędzia Workplace Join (WPJ). Oddzielne kroki powinny również uprościć proces rozwiązywania problemów dla administratorów IT. Wcześniej, gdy użytkownik końcowy próbował zarejestrować urządzenie i wszystkie kroki rejestracji kończyły się pomyślnie z wyjątkiem użycia narzędzia WPJ, zarejestrowane urządzenie nie było wyświetlane na liście urządzeń do zidentyfikowania przez użytkowników, co było mylące.

### Android
- **Aplikacja Portal firmy dla systemu Android**<br/>
Jeśli użytkownicy końcowi systemu Android widzą komunikat o błędzie stwierdzający brak wymaganego certyfikatu na urządzeniu, mogą nacisnąć przycisk „Jak rozwiązać ten problem”, aby uzyskać [kroki](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) wymagane do zainstalowania brakującego certyfikatu. Jeśli użytkownicy wykonają podane kroki, ale wciąż widzą komunikat o braku certyfikatu, proszeni są o kontakt z administratorem IT i podanie tego [linku](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), który zawiera kroki umożliwiające administratorom IT usunięcie problemu z certyfikatem.

- **Ograniczenie instalacji aplikacji ładowanych bezpośrednio do zarejestrowanych urządzeń**<br/>
Na urządzeniach z systemem Android nie można już instalować aplikacji za pośrednictwem witryny internetowej Portalu firmy, chyba że zostały zarejestrowane w usłudze Intune przy użyciu aplikacji Portal firmy usługi Intune dla systemu Android.
<!---TFS 1299082--->

### iOS
- **Zmiany w kontach menedżerów rejestracji urządzeń w aplikacji Portal firmy dla systemu iOS**<br/>
Aby zwiększyć wydajność i skalę, usługa Intune nie pokazuje już wszystkich urządzeń menedżerów rejestracji urządzeń (DEM) w okienku **Moje urządzenia** aplikacji Portal firmy dla systemu iOS. Wyświetlane jest tylko urządzenie lokalne, na którym uruchomiono aplikację, o ile zostało zarejestrowane przez aplikację Portal firmy.

    Użytkownik menedżera rejestracji urządzeń może wykonywać działania na urządzeniu lokalnym, ale zdalne zarządzanie innymi zarejestrowanymi urządzeniami można przeprowadzać tylko z konsoli administracyjnej usługi Intune. Dodatkowo w usłudze Intune wycofano używanie kont menedżera rejestracji urządzeń z programem Device Enrollment Program firmy Apple i narzędziem Apple Configurator. Obie te metody rejestracji obsługują już rejestrację bez użytkowników dla współużytkowanych urządzeń z systemem iOS.

    Kont menedżera rejestracji urządzeń należy używać tylko w przypadku braku dostępności rejestracji bez użytkowników dla współużytkowanych urządzeń. Więcej informacji zawiera temat [Rejestrowanie urządzeń należących do firmy przy użyciu menedżera rejestracji urządzeń w usłudze Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

## Zmiana nazw funkcji systemu Windows
- Usługa [Microsoft Passport for Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) ma teraz nazwę **Windows Hello for Business**.
- [Ochrona danych przedsiębiorstwa](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) ma teraz nazwę **Windows Information Protection**.

## Wkrótce
### Przejście grup usługi Intune do grup usługi Azure Active Directory rozpocznie się w sierpniu 2016
Usługa Intune wprowadza nową funkcjonalność zarządzania grupami, która używa grup zabezpieczeń usługi Azure Active Directory (AAD). Te grupy zabezpieczeń usługi Azure AD mogą zawierać zarówno użytkowników, jak i urządzenia, i będą używane do zarządzania wszystkimi grupami, wdrażania zasad i wdrażania profilów po wprowadzeniu nowego portalu administracyjnego usługi Intune bazującej na platformie Azure.

Nowe środowisko to:
- Brak konieczności duplikowania grup między usługami.
- Możliwość dostępu do nowych funkcji grup Azure Active Directory Premium (AADP).
- Rozszerzalność przy użyciu programów PowerShell i Graph.
- Ujednolicenie środowiska administrowania grupami w zarządzaniu mobilnością w przedsiębiorstwie.

W celu umożliwienia przejścia do grup zabezpieczeń środowisko bieżącej konsoli administracyjnej zostanie zmodyfikowane. Te zmiany i sposób korzystania z grup zabezpieczeń usługi Azure AD zostaną zarejestrowane w dokumentacji usługi Intune.

Nowi klienci usługi Intune zobaczą zmiany grup zabezpieczeń przed bieżącymi dzierżawcami.

Oprócz zmian w zarządzaniu grupami zostaną wycofane następujące funkcje:
- Wykluczanie członków lub grup podczas tworzenia nowej grupy
- Grupy **Użytkownicy niezgrupowani** i **Urządzenia niezgrupowane**
- **Zarządzanie grupami** w roli administratora usługi
- Niestandardowe alerty bazujące na grupach dla reguł powiadomień
- Przestawianie z grupami w raportach

Więcej informacji na temat sposobu rozwiązywania problemów z usuniętymi funkcjami zostanie opublikowanych w sierpniu.

### Dodanie obszaru „Powiadomienia” do Portalu firmy dla systemu Android
We wrześniu udostępnimy aktualizację Portalu firmy dla systemu Android, która wprowadzi nową ikonę **Powiadomienia** na stronie głównej. Naciśnięcie tej ikony spowoduje przejście na stronę **Powiadomienia**, która przedstawia użytkownikowi końcowemu wszystkie elementy, które wymagają uwagi w aplikacji Portal firmy, takie jak brak zgodności urządzeń, aktualizacja rejestracji i aktywacja rejestracji. Jeśli używasz również aplikacji Portal firmy dla systemu iOS, powiadomienia masz już widoczne. Wraz z wprowadzeniem strony **Powiadomienia** nie będzie widoczna strona **Konfigurowanie dostępu do zasobów firmy** po uruchomieniu lub wznowieniu pracy w Portalu firmy dla systemu Android, jeśli urządzenie zostało już zarejestrowane. Wiemy, że wiele osób utworzyło wskazówki dla użytkowników końcowych i doceniają wcześniejsze powiadomienie, gdy wskazówki lub zrzuty ekranu mogą wymagać aktualizacji. Prosimy więc o takie zaktualizowanie dokumentacji, aby odzwierciedlała ona nadchodzące zmiany w środowisku. Zaktualizowane zrzuty ekranu można znaleźć tutaj: https://aka.ms/androidcpupdate.  



### Plan chmury
Śledź na bieżąco rozwój usługi Intune, korzystając z [planu platformy w chmurze](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Wycofywanie usług
- **Zmiany w obsłudze aplikacji Portal firmy dla systemu iOS**<br/>
W lipcu wszyscy użytkownicy aplikacji Portal firmy usługi Microsoft Intune dla systemu iOS będą musieli używać jej najnowszej wersji. Nowi użytkownicy będą mogli pobrać tylko najnowszą wersję, a bieżący użytkownicy będą musieli przeprowadzić aktualizację do najnowszej wersji. Najnowsza wersja aplikacji wymaga systemu iOS 8.0 lub nowszego, dlatego urządzenia ze starszymi wersjami systemu iOS nie będą mogły korzystać z portalu firmy ani rejestrować się do czasu ich zaktualizowania do systemu iOS 8.0 lub nowszego oraz zaktualizowania aplikacji Portal firmy do najnowszej wersji. Zarejestrowane urządzenia z wersjami systemu iOS poniżej 8.0 będą nadal zarządzane i wyświetlane w konsoli administracyjnej usługi Intune.  

- **Minimalna wersja systemu iOS dla przeglądarki Managed Browser została zaktualizowana do 8.0**<br/>
W sierpniu dział usługi Intune opublikuje zaktualizowaną aplikację Microsoft Intune Managed Browser dla systemu iOS, która będzie obsługiwana tylko na urządzeniach z systemem iOS 8.0 lub nowszym. Podczas gdy urządzenia z systemem iOS 7.1 wciąż będą mogły używać istniejącej aplikacji Managed Browser, należy zachęcać użytkowników do aktualizacji systemu iOS do wersji 8.0 lub nowszej, aby mogli w pełni skorzystać z najnowszych funkcji przeglądarki Managed Browser.  
<!---TFS 1313253--->

- **Aplikacje Portal firma dla systemu Windows 8 i Windows Phone 8 zostaną wycofane we wrześniu 2016 r.** <br/>
Począwszy od września 2016 roku w usłudze Microsoft Intune zakończy się obsługa aplikacji Portal firmy Microsoft Intune dla platform Windows Phone 8 i Windows 8. Zaktualizuj urządzenia do systemów Windows 8.1 i Windows Phone 8.1 oraz skorzystaj z odpowiedniej aplikacji Portal firmy dla systemu Windows 8.1 lub Windows Phone 8.1, aby kontynuować dystrybucję aplikacji na tych urządzeniach.
<!---TFS 1255391--->

- **Aplikacje Intune Viewer** <br/>
Wraz z wydaniem nowej aplikacji RMS sharing zostaną usunięte następujące aplikacje Intune Viewer, począwszy od sierpnia 2016 roku:
    - Intune AV Viewer
    - Intune PDF Viewer
    - Intune Image Viewer dla systemu Android ze sklepu Google Play

  Zalecamy, aby zamiast korzystania z aplikacji Intune Viewer używać nowej [aplikacji do zarządzania prawami (RMS sharing) dla systemu Android](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), co pozwala na wdrożenie jednej aplikacji zamiast trzech osobnych aplikacji w celu bezpiecznego przeglądania plików firmy na urządzeniach z systemem Android. Gdy aplikacja Intune Viewer nie będzie już obsługiwana, zostanie usunięta ze sklepu Google i nie będzie dostępna do użycia w przyszłości.

<!--- - **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

    Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

    In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

    In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

    The preliminary timeline for this change is as follows:
    - In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
    - Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
    - Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

--->



## Poprzednie wersje usługi Intune
Aby zobaczyć funkcje wprowadzone w usłudze Intune w ostatnich sześciu miesiącach, zobacz artykuł [Poprzednie wersje usługi Intune](previous-intune-releases.md).

### Zobacz także
* [Blog usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plan platformy w chmurze](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)



<!--HONumber=Aug16_HO1-->


