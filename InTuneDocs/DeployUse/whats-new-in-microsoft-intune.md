---
title: Co nowego | Microsoft Intune
description: "Sprawdź nowości w tym miesiącu i poprzednich wersjach usługi Microsoft Intune"
keywords: 
author: Lindavr
manager: angrobe
ms.date: 08/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0d70a46d9c13aad1bc0a940836d83a99b93bb95e
ms.openlocfilehash: a753ecfa08adcd27049c70889c50e10618ecddba


---

# Co nowego w usłudze Microsoft Intune
Poznaj nowości w tej wersji usługi Microsoft Intune. Dowiedz się o nadchodzących zmianach, na które należy się przygotować, jak również uzyskaj informacje o poprzednich wersjach.

Wszystkie te funkcje będą również w przyszłości obsługiwane dla hybrydowych wdrożeń klientów (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

## Sierpień 2016
## Zarządzanie aplikacjami
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

### Aplikacje ukrywane i wyświetlane dla systemu iOS 9.3
Dla urządzeń nadzorowanych z systemem iOS 9.3 lub nowszym w ogólnych zasadach konfiguracji systemu iOS można używać listy aplikacji ukrywanych i wyświetlanych, aby:
- Określić listę aplikacji, które będą ukryte dla użytkowników. Użytkownicy nie będą mogli wyświetlać ani uruchamiać tych aplikacji.
- Określić listę aplikacji, które użytkownicy mogą wyświetlać i uruchamiać. Użytkownicy nie będą mogli wyświetlać ani uruchamiać żadnych innych aplikacji.

Dla tych list można określić zarówno aplikacje wdrożone, jak i wbudowane aplikacje dla systemu iOS, takie jak Wiadomości i Notatki. Aby uzyskać więcej informacji, zobacz [Ustawienia zasad systemu iOS w usłudze Microsoft Intune]( https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune)
<!---TFS 1279009 checked--->
### Zasady aplikacji dozwolonych i zablokowanych dla urządzeń z systemem Samsung KNOX
Dla urządzeń z systemem Samsung KNOX można teraz skonfigurować zasady niestandardowe umożliwiające utworzenie jednej z następujących list:
- Lista aplikacji, których uruchamianie na urządzeniu jest zablokowane. Nawet po zainstalowaniu aplikacji zdefiniowanej na liście zablokowanych nie będzie jej można uaktywnić na urządzeniu.
- Lista aplikacji, które użytkownicy urządzenia mogą instalować ze sklepu klepu Google Play. Nie będzie można instalować żadnych innych aplikacji ze sklepu.

Tych ustawień można używać tylko w przypadku urządzeń z systemem Samsung KNOX.
Aby uzyskać więcej informacji, zobacz [Użycie niestandardowych zasad do zezwalania na aplikacje i blokowania ich na urządzeniach z systemem Samsung KNOX]( custom-policy-to-allow-and-block-samsung-knox-apps.md).
<!---TFS 1311629 checked --->
### Nowe aplikacje zgodne z zasadami zarządzania aplikacjami mobilnymi (MAM)
Aplikacja usługi Yammer dla systemów [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) i [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) jest teraz zgodna z [zasadami zarządzania aplikacjami mobilnymi (MAM, mobile application management) usługi Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) bez względu na to, czy urządzenie jest zarejestrowane.

Pełna lista aplikacji zgodnych z zasadami MAM jest dostępna w witrynie [partnerów aplikacji usługi Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners).
<!--- TFS 1252335 & 1252336 checked--->


<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

### Aplikacje Intune Viewer
Wraz z wydaniem nowej aplikacji RMS sharing zostaną usunięte następujące aplikacje Intune Viewer, począwszy od sierpnia 2016 roku:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer dla systemu Android ze sklepu Google Play

Zalecamy, aby zamiast korzystania z aplikacji Intune Viewer używać nowej [aplikacji do zarządzania prawami (RMS sharing) dla systemu Android](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), co pozwala na wdrożenie jednej aplikacji zamiast trzech osobnych aplikacji w celu bezpiecznego przeglądania plików firmy na urządzeniach z systemem Android. Gdy aplikacja Intune Viewer nie będzie już obsługiwana, zostanie usunięta ze sklepu Google i nie będzie dostępna do użycia w przyszłości.

## Zarządzanie urządzeniami
### Obsługa systemu Android 7.0
Usługa Intune zapewnia obsługę „od dnia 0” nadchodzącego systemu operacyjnego Android 7.0 dla urządzeń przenośnych.
<!---TFS 1262053--->
### Usunięcie przez Google możliwości zdalnego resetowania kodu dostępu na urządzeniach z systemem Android 7.0
Google usuwa możliwość zdalnego resetowania kodu dostępu urządzeń z systemem Android 7.0 przez administratorów IT i użytkowników końcowych. Wcześniej administratorzy IT mogli zdalnie zresetować kod dostępu użytkownika, a użytkownicy końcowi mogli resetować swoje kody dostępu z witryny sieci Web Portalu firmy.



## Aktualizacje Portalu firmy
### Witryna sieci Web Portal firmy
- **Link opinii z Portalu firmy do firmy Microsoft** <br/>
Witryna sieci Web Portalu firmy udostępnia użytkownikom końcowym nowy link „Opinia” u dołu strony, który użytkownicy mogą wybrać, aby wysłać do firmy Microsoft opinię dotyczącą ich wizyty w witrynie. Zebrane, anonimowe opinie pomogą firmie Microsoft w ulepszaniu środowiska witryny sieci Web Portalu firmy dla użytkowników.
<!--- TFS 1313657 checked--->

### iOS
- **Minimalna wersja systemu iOS dla przeglądarki Managed Browser została zaktualizowana do 8.0**<br/>
Aplikacja Microsoft Intune Managed Browser dla systemu iOS została zaktualizowana w celu obsługiwania urządzeń z systemem iOS 8.0 lub nowszym. Podczas gdy urządzenia z systemem iOS 7.1 wciąż mogą używać istniejącej aplikacji Managed Browser, należy zachęcać użytkowników do aktualizacji systemu iOS do wersji 8.0 lub nowszej, aby mogli w pełni skorzystać z najnowszych funkcji przeglądarki Managed Browser.  
<!---TFS 1313253 checked--->

## Wkrótce
### Przejście grup usługi Intune do grup usługi Azure Active Directory rozpocznie się we wrześniu 2016 r.
Usługa Intune wprowadza nową funkcjonalność zarządzania grupami, która używa grup zabezpieczeń usługi Azure Active Directory (AAD) jako grupy użytkowników i urządzeń w usłudze Intune. Te grupy będą używane do zarządzania grupami, wdrażania zasad i wdrażania profilów **po wprowadzeniu nowego portalu administracyjnego usługi Intune używającej platformy Azure**.

Nowe środowisko zlikwiduje konieczność duplikowania grup między usługami, **pozwoli na dostęp do nowych funkcji grup usługi Azure Active Directory Premium (AADP)** i zapewni możliwość rozszerzenia przy użyciu programów PowerShell i Graph. Ujednolici to również środowisko administrowania grupami w zarządzaniu mobilnością w przedsiębiorstwie.

W celu umożliwienia przejścia do grup zabezpieczeń środowisko **bieżącej konsoli administracyjnej** zostanie zmodyfikowane. **Te zmiany i sposób korzystania z grup zabezpieczeń usługi AAD zostaną zarejestrowane w dokumentacji usługi Intune**.

Nowi klienci usługi Intune zobaczą **zmiany grup zabezpieczeń przed bieżącymi dzierżawcami**.

Oprócz zmian w zarządzaniu grupami **zostaną wycofane następujące funkcje**:
- Wykluczanie członków lub grup podczas tworzenia nowej grupy
- Grupy **Użytkownicy niezgrupowani** i **Urządzenia niezgrupowane**
- **Zarządzanie grupami** w roli administratora usługi
- Niestandardowe alerty bazujące na grupach dla reguł powiadomień
- Przestawianie z grupami w raportach
<!--- TFS 1295329--->

### Dodanie obszaru „Powiadomienia” do Portalu firmy dla systemu Android
We wrześniu udostępnimy aktualizację Portalu firmy dla systemu Android, która wprowadzi nową ikonę **Powiadomienia** na stronie głównej. Naciśnięcie tej ikony spowoduje przejście na stronę **Powiadomienia**, która przedstawia użytkownikowi końcowemu wszystkie elementy, które wymagają uwagi w aplikacji Portal firmy, takie jak brak zgodności urządzeń, aktualizacja rejestracji i aktywacja rejestracji. Jeśli używasz również aplikacji Portal firmy dla systemu iOS, powiadomienia masz już widoczne. Wraz z wprowadzeniem strony **Powiadomienia** nie będzie widoczna strona **Konfigurowanie dostępu do zasobów firmy** po uruchomieniu lub wznowieniu pracy w Portalu firmy dla systemu Android, jeśli urządzenie zostało już zarejestrowane. Wiemy, że wiele osób utworzyło wskazówki dla użytkowników końcowych i doceniają wcześniejsze powiadomienie, gdy wskazówki lub zrzuty ekranu mogą wymagać aktualizacji. Prosimy więc o takie zaktualizowanie dokumentacji, aby odzwierciedlała ona nadchodzące zmiany w środowisku. Zaktualizowane zrzuty ekranu można znaleźć tutaj: https://aka.ms/androidcpupdate.  

### Ulepszenia w sposobie uzyskiwania aplikacji przez użytkowników końcowych systemu iOS
We wrześniu zostaną wprowadzone następujące zmiany w odniesieniu do kafelków aplikacji w aplikacji Portal firmy dla systemu iOS. Zmiany mają na celu umożliwienie przechodzenia do różnych widoków w obrębie jednej lokalizacji — witryny sieci Web Portal firmy — dla wszystkich swoich aplikacji. Obecnie ograniczenia firmy Apple uniemożliwiają wyświetlanie w aplikacji Portal firmy aplikacji biznesowych oraz zarządzanych ze sklepu z aplikacjami, w związku z czym użytkownicy muszą korzystać z różnych widoków, aby znaleźć wszystkie swoje aplikacje.

- Kafelek **Aplikacje firmowe** pozwala obecnie przejść do listy wszystkich aplikacji na karcie WSZYSTKIE w witrynie sieci Web Portal firmy. Jego działanie nie ulegnie zmianie. Nazwa kafelka zostanie zmieniona na **Wszystkie aplikacje**.
- Kafelek **Inne aplikacje** pozwala obecnie przejść do widoku aplikacji Portal firmy zawierającego wszystkie aplikacje, których wyświetlanie w aplikacji Portal firmy jest możliwe zgodnie z zasadami firmy Apple. Nazwa kafelka zostanie zmieniona na **Polecane aplikacje**, a jego dotknięcie spowoduje przejście na kartę POLECANE w witrynie sieci Web Portal firmy.
-  Kafelek **Kategorie** pozwala obecnie przejść do widoku aplikacji Portal firmy, w którym wyświetlana jest lista kategorii aplikacji. Nazwa kafelka nie ulegnie zmianie, ale jego dotknięcie będzie teraz powodować przejście na kartę KATEGORIE w witrynie sieci Web Portal firmy. Zaktualizowane zrzuty ekranu można znaleźć [tutaj](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
<!---TFS 1317133--->

### Plan chmury
Śledź na bieżąco rozwój usługi Intune, korzystając z [planu platformy w chmurze](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Wycofywanie usług
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **Zmiany w obsłudze aplikacji Portal firmy dla systemu iOS**<br/>
We wrześniu wszyscy użytkownicy aplikacji Portal firmy usługi Microsoft Intune dla systemu iOS będą musieli używać jej najnowszej wersji. Nowi użytkownicy będą mogli pobrać tylko najnowszą wersję, a bieżący użytkownicy będą musieli przeprowadzić aktualizację do najnowszej wersji. Najnowsza wersja aplikacji wymaga systemu iOS 8.0 lub nowszego, dlatego urządzenia ze starszymi wersjami systemu iOS nie będą mogły korzystać z portalu firmy ani rejestrować się do czasu ich zaktualizowania do systemu iOS 8.0 lub nowszego oraz zaktualizowania aplikacji Portal firmy do najnowszej wersji. Zarejestrowane urządzenia z wersjami systemu iOS poniżej 8.0 będą nadal zarządzane i wyświetlane w konsoli administracyjnej usługi Intune.  

- **Minimalna wersja systemu iOS dla przeglądarki Managed Browser została zaktualizowana do 8.0**<br/>
W sierpniu dział usługi Intune opublikuje zaktualizowaną aplikację Microsoft Intune Managed Browser dla systemu iOS, która będzie obsługiwana tylko na urządzeniach z systemem iOS 8.0 lub nowszym. Podczas gdy urządzenia z systemem iOS 7.1 wciąż będą mogły używać istniejącej aplikacji Managed Browser, należy zachęcać użytkowników do aktualizacji systemu iOS do wersji 8.0 lub nowszej, aby mogli w pełni skorzystać z najnowszych funkcji przeglądarki Managed Browser.  
<!---TFS 1313253--->

- **Aplikacje Portal firmy dla systemu Windows 8 i Windows Phone 8 zostaną wycofane we wrześniu 2016 r.** <br/>
Począwszy od września 2016 roku w usłudze Microsoft Intune zakończy się obsługa aplikacji Portal firmy Microsoft Intune dla platform Windows Phone 8 i Windows 8. Zaktualizuj urządzenia do systemów Windows 8.1 i Windows Phone 8.1 oraz skorzystaj z odpowiedniej aplikacji Portal firmy dla systemu Windows 8.1 lub Windows Phone 8.1, aby kontynuować dystrybucję aplikacji na tych urządzeniach.
<!---TFS 1255391--->

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



<!--HONumber=Aug16_HO4-->


