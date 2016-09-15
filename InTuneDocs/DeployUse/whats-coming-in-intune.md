---
title: "Wkrótce | Microsoft Intune"
description: 
keywords: 
author: Lindavr
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 500cc93b595e04cea987bda699abf94ae010443a
ms.openlocfilehash: f45fc02003c6b40cc15fabeffff35cf0cde1a830


---

# Wkrótce w usłudze Microsoft Intune — sierpień
Te informacje są przekazywane pod rygorem umowy NDA w bardzo ograniczonym zakresie i mogą ulec zmianie. Niektóre funkcje wymienione w tym miejscu mogą nie być wdrożone na czas i zostać opóźnione do przyszłych wersji. Inne funkcje są testowane w wersji pilotażowej, aby zapewnić przygotowanie ich do użytku przez klientów. W przypadku pytań lub wątpliwości skontaktuj się ze swoim partnerem ds. usługi Intune/PM.

Ta strona jest okresowo aktualizowana. Odwiedź ją ponownie, aby sprawdzić informacje na temat nadchodzących aktualizacji.

Dla usługi Intune opracowywane są następujące zmiany. Wszystkie te funkcje będą również w przyszłości obsługiwane dla hybrydowych wdrożeń klientów (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).


## Zarządzanie aplikacjami
### Aplikacje ukrywane i wyświetlane dla systemu iOS 9.3
Dla urządzeń z systemem iOS 9.3 lub nowszym w ogólnych zasadach konfiguracji systemu iOS można będzie użyć listy aplikacji ukrywanych i wyświetlanych, aby:
- Określić listę aplikacji, które będą ukryte dla użytkowników. Użytkownicy nie będą mogli wyświetlać ani uruchamiać tych aplikacji.
- Określić listę aplikacji, które użytkownicy mogą wyświetlać i uruchamiać. Użytkownicy nie będą mogli wyświetlać ani uruchamiać żadnych innych aplikacji.

Dla tych list można określić zarówno aplikacje wdrożone, jak i wbudowane aplikacje dla systemu iOS, takie jak Wiadomości i Notatki.
<!---TFS 1279009--->

### Zasady aplikacji dozwolonych i zablokowanych dla urządzeń z systemem Samsung KNOX

Dla urządzeń z systemem Samsung KNOX można teraz skonfigurować zasady niestandardowe umożliwiające utworzenie jednej z następujących list:
- Lista aplikacji, których uruchamianie na urządzeniu jest zablokowane. Nawet po zainstalowaniu aplikacji zdefiniowanej na liście zablokowanych nie będzie jej można uaktywnić na urządzeniu.
- Lista aplikacji, które użytkownicy urządzenia mogą instalować ze sklepu klepu Google Play. Nie będzie można instalować żadnych innych aplikacji ze sklepu.

Tych ustawień można używać tylko w przypadku urządzeń z systemem Samsung KNOX.
<!--- For details, see [Use custom policies to allow and block apps for Samsung KNOX devices]( custom-policy-to-allow-and-block-samsung-knox-apps.md)--->
<!---TFS 1311629 --->

### Nowe aplikacje zgodne z zasadami zarządzania aplikacjami mobilnymi (MAM)
Aplikacja usługi Yammer dla systemów [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) i [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) będzie zgodna z [zasadami zarządzania aplikacjami mobilnymi (MAM) usługi Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) bez względu na to, czy urządzenie jest zarejestrowane.

Pełna lista aplikacji zgodnych z zasadami MAM jest dostępna w witrynie [partnerów aplikacji usługi Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners).
<!--- TFS 1252335 & 1252336--->

## Zarządzanie urządzeniami
### Obsługa systemu Android 7.0
W sierpniu usługa Intune zapewni obsługę „od dnia 0” nadchodzącego systemu operacyjnego Android 7.0 dla urządzeń przenośnych.
<!---TFS 1262053--->
### Usunięcie przez Google możliwości zdalnego resetowania kodu dostępu na urządzeniach z systemem Android 7.0
Google usuwa możliwość zdalnego resetowania kodu dostępu urządzeń z systemem Android 7.0 przez administratorów IT i użytkowników końcowych. Wcześniej administratorzy IT mogli zdalnie zresetować kod dostępu użytkownika, a użytkownicy końcowi mogli resetować swoje kody dostępu z witryny sieci Web Portalu firmy.

## Zarządzanie grupami
### Przejście grup usługi Intune do grup usługi Azure Active Directory rozpocznie się we wrześniu 2016 r.
Usługa Intune wprowadza nową funkcjonalność zarządzania grupami, która używa grup zabezpieczeń usługi Azure Active Directory (AAD) jako grupy użytkowników i urządzeń w usłudze Intune. Te grupy będą używane do zarządzania grupami, wdrażania zasad i wdrażania profilów **po wprowadzeniu nowego portalu administracyjnego usługi Intune używającej platformy Azure**.

Nowe środowisko zlikwiduje konieczność duplikowania grup między usługami, **pozwoli na dostęp do nowych funkcji grup usługi Azure Active Directory — wersja Premium (AADP)** i zapewni możliwość rozszerzenia przy użyciu programów PowerShell i Graph. Ujednolici to również środowisko administrowania grupami w zarządzaniu mobilnością w przedsiębiorstwie.

W celu umożliwienia przejścia do grup zabezpieczeń środowisko **bieżącej konsoli administracyjnej** zostanie zmodyfikowane. **Te zmiany i sposób korzystania z grup zabezpieczeń usługi AAD zostaną zarejestrowane w dokumentacji usługi Intune**.

Nowi klienci usługi Intune zobaczą **zmiany grup zabezpieczeń przed bieżącymi dzierżawcami**.

Oprócz zmian w zarządzaniu grupami **zostaną wycofane następujące funkcje**:
- Wykluczanie członków lub grup podczas tworzenia nowej grupy
- Grupy **Użytkownicy niezgrupowani** i **Urządzenia niezgrupowane**
- **Zarządzanie grupami** w roli administratora usługi
- Niestandardowe alerty bazujące na grupach dla reguł powiadomień
- Przestawianie z grupami w raportach
<!--- TFS 1295329--->

## Portal firmy

### Link opinii z Portalu firmy do firmy Microsoft
Witryna sieci Web Portalu firmy udostępni użytkownikom końcowym nowy link „Opinia” u dołu strony, który użytkownicy mogą wybrać, aby wysłać do firmy Microsoft opinię dotyczącą ich obsługi w witrynie. Zebrane, anonimowe opinie pomogą firmie Microsoft w ulepszaniu środowiska witryny sieci Web Portalu firmy dla użytkowników.
<!--- TFS 1313657--->

### Dodanie obszaru „Powiadomienia” do Portalu firmy dla systemu Android
We wrześniu udostępnimy aktualizację Portalu firmy dla systemu Android, która wprowadzi nową ikonę **Powiadomienia** na stronie głównej. Naciśnięcie tej ikony spowoduje przejście na stronę **Powiadomienia**, która przedstawia użytkownikowi końcowemu wszystkie elementy, które wymagają uwagi w aplikacji Portal firmy, takie jak brak zgodności urządzeń, aktualizacja rejestracji i aktywacja rejestracji. Jeśli używasz również aplikacji Portal firmy dla systemu iOS, powiadomienia masz już widoczne. Wraz z wprowadzeniem strony **Powiadomienia** nie będzie widoczna strona **Konfigurowanie dostępu do zasobów firmy** po uruchomieniu lub wznowieniu pracy w Portalu firmy dla systemu Android, jeśli urządzenie zostało już zarejestrowane. Wiemy, że wiele osób utworzyło wskazówki dla użytkowników końcowych i doceniają wcześniejsze powiadomienie, gdy wskazówki lub zrzuty ekranu mogą wymagać aktualizacji. Prosimy więc o takie zaktualizowanie dokumentacji, aby odzwierciedlała ona nadchodzące zmiany w środowisku. Zaktualizowane zrzuty ekranu można znaleźć tutaj: https://aka.ms/androidcpupdate.  

### Ulepszenia w sposobie uzyskiwania aplikacji przez użytkowników końcowych systemu iOS
We wrześniu zostaną wprowadzone następujące zmiany w odniesieniu do kafelków aplikacji w aplikacji Portal firmy dla systemu iOS. Zmiany mają na celu umożliwienie przechodzenia do różnych widoków w obrębie jednej lokalizacji — witryny sieci Web Portal firmy — dla wszystkich swoich aplikacji. Obecnie ograniczenia firmy Apple uniemożliwiają wyświetlanie w aplikacji Portal firmy aplikacji biznesowych oraz zarządzanych ze sklepu z aplikacjami, w związku z czym użytkownicy muszą korzystać z różnych widoków, aby znaleźć wszystkie swoje aplikacje.

- Kafelek **Aplikacje firmowe** pozwala obecnie przejść do listy wszystkich aplikacji na karcie WSZYSTKIE w witrynie sieci Web Portal firmy. Jego działanie nie ulegnie zmianie. Nazwa kafelka zostanie zmieniona na **Wszystkie aplikacje**.
- Kafelek **Inne aplikacje** pozwala obecnie przejść do widoku aplikacji Portal firmy zawierającego wszystkie aplikacje, których wyświetlanie w aplikacji Portal firmy jest możliwe zgodnie z zasadami firmy Apple. Nazwa kafelka zostanie zmieniona na **Polecane aplikacje**, a jego dotknięcie spowoduje przejście na kartę POLECANE w witrynie sieci Web Portal firmy.
-  Kafelek **Kategorie** pozwala obecnie przejść do widoku aplikacji Portal firmy, w którym wyświetlana jest lista kategorii aplikacji. Nazwa kafelka nie ulegnie zmianie, ale jego dotknięcie będzie teraz powodować przejście na kartę KATEGORIE w witrynie sieci Web Portal firmy.
Zaktualizowane zrzuty ekranu można znaleźć [tutaj](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
<!---TFS 1317133--->

### Wyświetlaj monit o instalację aplikacji Managed Browser dla systemu iOS, jeśli oprogramowanie IT Pro określiło taki wymóg dla aplikacji
We wrześniowej wersji aplikacji Portalu firmy dla systemu iOS ustawienie składnika Web Clip w taki sposób, aby otwierał się tylko w zarządzanej przeglądarce w przypadku, gdy zarządzana przeglądarka nie została zainstalowana na urządzeniu, spowoduje, że aplikacja Portal firmy na urządzeniu wyświetli monit o zainstalowanie zarządzanej przeglądarki przed zainstalowaniem składnika Web Clip. 
<!---TFS 1228570--->

## Wycofywanie usług
### Aplikacje Portal firmy dla systemu Windows 8 i Windows Phone 8 są przestarzałe i zostaną wycofane we wrześniu 2016 r.
Począwszy od października 2016, usługa Microsoft Intune wycofa obsługę aplikacji Portal firmy dla systemów Windows Phone 8 i Windows 8. Usługa Microsoft Intune wycofa również obsługę platformy Windows Phone 8. W rezultacie nie będzie można zarejestrować ani zaktualizować żadnych urządzeń z systemem Windows Phone 8. Można będzie nadal zarządzać urządzeniami z systemami Windows Phone 8 i Windows 8, które są już zarejestrowane. Zaktualizuj urządzenia z systemami Windows 8 i Windows Phone 8 do systemów Windows 8.1 i Windows Phone 8.1 oraz skorzystaj z odpowiedniej aplikacji Portal firmy dla systemu Windows 8.1 lub Windows Phone 8.1, aby kontynuować bez zakłóceń dystrybucję aplikacji na tych urządzeniach.
<!---TFS 1255391--->

### Usunięcie określania grup niestandardowych jako obiektów docelowych reguł powiadomień
Reguły powiadomień usługi Intune definiują, do kogo będą wysyłane alerty e-mail z usługi Intune. Obecnie można konfigurować reguły powiadomień w celu wysyłania wiadomości e-mail do wszystkich użytkowników urządzeń należących do utworzonej grupy urządzeń usługi Intune. Począwszy od czerwca 2016 wskazywanie grup utworzonych przez użytkownika jako obiektów docelowych nie będzie już obsługiwanie.

Wstępny plan dla tej zmiany jest następujący:
- We wrześniu 2016 roku nowi dzierżawcy nie będą widzieć drugiego kroku Kreatora tworzenia reguł powiadomień. Nie dotyczy to jednak istniejących dzierżawców.
- W okolicach października 2016 roku niektórzy istniejący dzierżawcy nie będą widzieć kroku „Wybierz grupy urządzeń” w kreatorze.
- Przewidujemy, że w późniejszym terminie krok „Wybierz grupy urządzeń” w kreatorze przestanie być widoczny dla wszystkich dzierżawców.

<!---   TFS 1278864--->
### Zmiany w obsłudze aplikacji Portal firmy dla systemu iOS
We wrześniu wszyscy użytkownicy aplikacji Portal firmy usługi Microsoft Intune dla systemu iOS będą musieli używać jej najnowszej wersji. Nowi użytkownicy będą mogli pobrać tylko najnowszą wersję, a bieżący użytkownicy będą musieli przeprowadzić aktualizację do najnowszej wersji. Najnowsza wersja aplikacji wymaga systemu iOS 8.0 lub nowszego, dlatego urządzenia ze starszymi wersjami systemu iOS nie będą mogły korzystać z portalu firmy ani rejestrować się do czasu ich zaktualizowania do systemu iOS 8.0 lub nowszego oraz zaktualizowania aplikacji Portal firmy do najnowszej wersji. Zarejestrowane urządzenia z wersjami systemu iOS poniżej 8.0 będą nadal zarządzane i wyświetlane w konsoli administracyjnej usługi Intune.

<!---TFS 1283165--->


### Aplikacje Intune Viewer
Wraz z wydaniem nowej aplikacji RMS we wrześniu 2016 roku zostaną usunięte następujące aplikacje Intune Viewer:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer dla systemu Android ze sklepu Google Play

Zalecamy, aby zamiast korzystania z aplikacji Intune Viewer używać nowej aplikacji do zarządzania prawami (RMS sharing) dla systemu Android, co pozwala na wdrożenie jednej aplikacji zamiast trzech osobnych aplikacji w celu bezpiecznego przeglądania plików firmy na urządzeniach z systemem Android. Dowiedz się więcej o [aplikacji RMS sharing](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app).
<!--- goes in 1608 What's New--->


### Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new-in-microsoft-intune.md).



<!--HONumber=Aug16_HO5-->


