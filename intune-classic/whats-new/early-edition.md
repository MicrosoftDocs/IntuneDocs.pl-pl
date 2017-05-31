---
title: Wersja wczesna | Microsoft Docs
description: 
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 249a902e6e10f799dcff4e1c46da90cd62f2c125
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="the-early-edition-for-microsoft-intune---may-2017"></a>Wersja wczesna usługi Microsoft Intune — maj 2017

**Wersja wczesna** zawiera listę funkcji, które zostaną wprowadzone w przyszłych wersjach usługi Microsoft Intune. Te informacje są przekazywane pod rygorem umowy NDA w bardzo ograniczonym zakresie i mogą ulec zmianie. Niektóre funkcje wymienione w tym miejscu mogą nie być wdrożone na czas i zostać opóźnione do przyszłych wersji. Inne funkcje są testowane w wersji pilotażowej, aby zapewnić przygotowanie ich do użytku przez klientów. W przypadku pytań lub wątpliwości skontaktuj się ze swoim partnerem ds. usługi Intune/PM.

Ta strona jest okresowo aktualizowana. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.

> [!Note]
> Dla usługi Intune opracowywane są następujące zmiany. Wszystkie te funkcje będą również w przyszłości obsługiwane dla hybrydowych wdrożeń klientów (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nowe możliwości

### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>Obsługa logowania jednokrotnego z aplikacji Portal firmy dla systemu iOS do programu Outlook dla systemu iOS <!--834012-->

Użytkownicy nie będą już musieli logować się w aplikacji Outlook, jeśli zalogowali się do aplikacji Portal firmy dla systemu iOS na tym samym urządzeniu przy użyciu tego samego konta. Gdy użytkownicy uruchamiają aplikację Outlook, mogą wybrać swoje konto i zalogować się automatycznie. Ponadto pracujemy nad dodaniem tej funkcji do innych aplikacji firmy Microsoft.

### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Ulepszone powiadomienia dotyczące numerów PIN wymaganych do uruchomiania urządzeń z obsługą platformy Samsung KNOX <!--1087143-->

W przypadku gdy użytkownicy końcowi muszą skonfigurować numer PIN wpisywany po uruchomieniu urządzenia z obsługą platformy Samsung KNOX w celu zapewnienia zgodności z szyfrowaniem, dotknięcie wyświetlonego powiadomienia umożliwi przejście bezpośrednio do odpowiedniego ustawienia.  Wcześniej dotknięcie powiadomienia na urządzeniu użytkownika końcowego powodowało przejście do ekranu zmiany hasła.

### <a name="promoting-the-most-current-version-of-the-company-portal-for-android---1098661--"></a>Promowanie najnowszej wersji aplikacji Portal firmy dla systemu Android <!--1098661-->

Po udostępnieniu nowej zalecanej wersji aplikacji Portal firmy dla systemu Android zostanie wyświetlone powiadomienie na ekranie powiadomień aplikacji. Treść powiadomienia będzie informować użytkowników, że „jest dostępna aktualizacja aplikacji Portal firmy”. Dotknięcie powiadomienia spowoduje otwarcie strony sieci Web z listą dostępnych sklepów z aplikacjami, z których można pobrać zaktualizowaną wersję. 

### <a name="improvements-to-app-syncing-with-windows-10-creators-update----676505---"></a>Ulepszenia synchronizacji aplikacji w wersji Aktualizacja systemu Windows 10 dla twórców <!-- 676505 -->

Aplikacja Portal firmy dla systemu Windows 10 będzie automatycznie inicjować synchronizację żądań instalacji aplikacji dla urządzeń z systemem w wersji Aktualizacja systemu Windows 10 dla twórców (1704). Pozwoli to ograniczyć problem związany z zatrzymywaniem się instalacji aplikacji w stanie „Oczekiwanie na synchronizację”. Ponadto użytkownicy będą mogli ręcznie zainicjować synchronizację z poziomu aplikacji. 

W aplikacji Portal firmy dla systemu Windows 10 zostanie również udostępniony przycisk odświeżania umożliwiający użytkownikowi odświeżenie zawartości aplikacji w dowolnym momencie. 

## <a name="notices"></a>Uwagi

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Firma Apple będzie wymagać aktualizacji mechanizmu Application Transport Security <!--748318-->

Firma Apple ogłosiła, że począwszy od wiosny 2017 roku będzie egzekwować pewne wymagania dotyczące mechanizmu Application Transport Security (ATS). Mechanizm ATS służy do wymuszania mocniejszych zabezpieczeń całej komunikacji aplikacji za pośrednictwem protokołu HTTPS. Ta zmiana wpływa na klientów usługi Intune korzystających z aplikacji Portalu firmy w systemie iOS. Zapoznaj się z naszym [blogiem pomocy technicznej usługi Intune](https://aka.ms/compportalats), aby uzyskać więcej szczegółów.

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Bezpośredni dostęp do scenariuszy rejestracji firmy Apple <!--951869-->

Na kontach usługi Intune utworzonych po styczniu 2017 roku włączono bezpośredni dostęp do scenariuszy rejestracji firmy Apple przy użyciu obciążenia Rejestruj urządzenia w portalu Azure w wersji zapoznawczej. Wcześniej podgląd rejestracji firmy Apple był dostępny tylko z poziomu linków w klasycznym portalu Intune. Konta usługi Intune utworzone przed styczniem 2017 będą wymagać przeprowadzenia jednorazowej migracji, zanim funkcje te będą dostępne w systemie Azure. Harmonogram migracji nie został jeszcze ogłoszony, ale szczegółowe informacje zostaną udostępnione najszybciej, jak będzie to możliwe. Zdecydowanie zalecamy utworzenie konta w wersji próbnej w celu przetestowania nowego środowiska pracy w przypadku, gdy istniejące konto nie ma dostępu do podglądu.

### <a name="whats-coming-for-appx-in-intune-on-azure----1000270---"></a>Elementy dostępne wkrótce dla pakietu AppX w usłudze Intune na platformie Azure <!-- 1000270 -->

W ramach migracji do usługi Intune na platformie Azure wprowadzamy następujące zmiany w pakiecie AppX:

1. Dodanie nowego typu aplikacji pakietu AppX w klasycznej konsoli usługi Intune, który można wdrożyć tylko do urządzeń zarejestrowanych w usłudze MDM.
2. Zmiana przeznaczenia istniejącego typu aplikacji pakietu AppX celem nakierowania wyłącznie na komputery zarządzanie za pośrednictwem komputerowego agenta usługi Intune.
3. Skonwertowanie wszystkich istniejących pakietów AppX do pakietów AppX usługi MDM w ramach migracji.

Zmiany nie wpływają na żadne istniejące wdrożenia w urządzeniach zarządzanych za pośrednictwem komputerowego agenta usługi Intune. Niemniej po migracji nie będzie można wdrażać tych migrowanych pakietów AppX na żadnych nowych urządzeniach zarządzanych za pośrednictwem komputerowego agenta usługi Intune, które nie zostały wcześniej ustawione jako urządzenia docelowe.

Po migracji należy ponownie przekazać pakiet AppX jako komputerowy pakiet AppX, jeśli chcesz przeprowadzać nowe wdrożenia na komputerach. Aby dowiedzieć się więcej, zobacz [Appx changes in Intune on Azure](https://aka.ms/appxchange) (Zmiany w pakietach AppX w usłudze Intune na platformie Azure) na blogu zespołu pomocy technicznej usługi Intune.  


## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Publiczna wersja zapoznawcza nowego środowiska administracyjnego usługi Intune na platformie Azure <!--736542-->

Na początku roku 2017 r. będziemy migrować nasze pełne środowisko administracyjne na platformę Azure, co umożliwi zaawansowane i zintegrowane zarządzanie podstawowymi przepływami pracy EMS na nowoczesnej platformie usług, którą można rozszerzyć za pomocą interfejsów API programu Graph.

Publiczna wersja zapoznawcza nowego środowiska administracyjnego będzie widoczna w nowych dzierżawach w wersji próbnej w witrynie Azure Portal w tym miesiącu. W wersji zapoznawczej możliwości istniejącej konsoli usługi Intune i spójność z nią będą udostępniane w sposób iteracyjny.

W środowisku administracyjnym w witrynie Azure Portal będzie używana już zapowiadana nowa funkcja grupowania i określania celu. W przypadku migrowania istniejącej dzierżawy do nowego środowiska grupowania nastąpi również migracja do nowego środowiska administracyjnego w wersji zapoznawczej w dzierżawie. Jeśli przed zakończeniem migrowania dzierżawy chcesz przetestować lub poznać dowolną nową funkcję, utwórz nowe konto wersji próbnej usługi Intune lub zapoznaj się z [nową dokumentacją](https://docs.microsoft.com/intune/what-is-intune).

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Obsługa opcji zarządzanych konfiguracji dla aplikacji systemu Android <!-- 621621 -->

Możliwe będzie konfigurowanie przeznaczonych dla systemu Android aplikacji ze sklepu Play, które obsługują zarządzane opcje konfiguracji.  Ta funkcja umożliwia wyświetlenie listy wartości konfiguracji obsługiwanych przez aplikację oraz zapewnia najwyższej klasy interfejs użytkownika z przewodnikiem, dzięki któremu można skonfigurować te wartości.

### <a name="remote-assistance-for-android-devices----675418---"></a>Pomoc zdalna dla urządzeń z systemem Android <!-- 675418 -->

Usługa Intune będzie korzystać z zakupionego osobno oprogramowania [TeamViewer](https://www.teamviewer.com), aby umożliwić oferowanie pomocy zdalnej użytkownikom urządzeń z systemem Android.

### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Wstępna konfiguracja uprawnień urządzenia dla aplikacji Android for Work <!-- 621614 -->

W przypadku aplikacji wdrożonych w ramach profilów służbowych urządzenia z programem Android for Work można będzie skonfigurować stan uprawnień dla poszczególnych aplikacji. Domyślnie aplikacje systemu Android, które wymagają uprawnień urządzenia, takich jak dostęp do lokalizacji lub aparatu urządzenia, wyświetlają monit o zaakceptowanie lub odrzucenie uprawnień przez użytkownika.  Na przykład jeśli aplikacja używa mikrofonu urządzenia, użytkownik końcowy otrzyma monit o przyznanie aplikacji uprawnienia do użycia mikrofonu. Ta funkcja pozwoli zdefiniować uprawnienia w imieniu użytkownika końcowego.  Administrator może skonfigurować uprawnienia, aby umożliwić następujące operacje:

- Automatyczna odmowa bez powiadomienia użytkownika
- Automatyczne zatwierdzenie bez powiadomienia użytkownika
- Wyświetlenie monitu o zaakceptowanie lub odrzucenie przez użytkownika.

### <a name="define-app-specific-pin-for-android-for-work-devices---728976--"></a>Ustawienie numeru PIN dla aplikacji na urządzeniach z programem Android for Work <!--728976-->

Możliwe będzie zdefiniowanie zasad kodu dostępu, które będą dotyczyć tylko aplikacji w profilu służbowym na urządzeniach z systemem Android w wersji 7.0 lub nowszej zarządzanych jako urządzenie z programem Android for Work.  Dostępne opcje:

- Zdefiniowanie zasad kodu dostępu obejmujących wyłącznie urządzenie — jest to kod dostępu, którego użytkownik musi użyć w celu odblokowania całego urządzenia.
- Zdefiniowanie zasad kodu dostępu obejmujących wyłącznie profil służbowy – użytkownicy końcowi otrzymają monit o podanie kodu dostępu przy każdym otwarciu dowolnej aplikacji w profilu służbowym.
- Zdefiniowanie zasad kodu dostępu obejmujących zarówno urządzenie, jak i profil służbowy — pracownik działu IT ma możliwość zdefiniowania zarówno zasad kodu dostępu dla urządzenia, jak i zasad kodu dostępu dotyczących profilu służbowego o różnej sile (np. 4-cyfrowy numer PIN do odblokowywania urządzenia i 6-cyfrowy numer PIN do otwierania dowolnej aplikacji w profilu służbowym).

>[!NOTE]
> Ta opcja jest dostępna wyłącznie w systemie Android w wersji 7.0 i nowszych.  Domyślnie użytkownik końcowy może użyć dwóch różnych numerów PIN lub wybrać opcję połączenia dwóch zdefiniowanych numerów PIN w celu uzyskania numeru PIN o większej sile.

### <a name="manage-password-and-other-android-for-work-settings---1102534--"></a>Zarządzanie hasłem i innymi ustawieniami programu Android for Work <!--1102534-->

Dodajemy nowe zasady ograniczeń urządzeń z programem Android for Work, które umożliwiają zarządzanie ustawieniami hasła i profilu służbowego na urządzeniach z programem Android for Work.

###  <a name="new-web-content-filter-policy-for-ios-devices----723832---"></a>Nowe zasady filtru zawartości sieci Web dla urządzeń z systemem iOS <!-- 723832 -->

Możliwe będzie kontrolowanie witryn sieci Web odwiedzanych przez użytkowników urządzeń z systemem iOS przy użyciu jednej z następujących dwóch metod:

  - Dodaj dozwolone i zablokowane adresy URL przy użyciu wbudowanych filtrów zawartości sieci Web w urządzeniach firmy Apple.
  - Zezwalaj tylko na dostęp do określonych witryn sieci Web za pośrednictwem przeglądarki Safari. Dla każdej określonej witryny zostanie utworzona zakładka w przeglądarce Safari.

### <a name="apple-school-manager-asm-support---748864--"></a>Obsługa usługi Apple School Manager (ASM) <!--748864-->

Usługa Intune będzie obsługiwać korzystanie z usługi Apple School Manager (ASM) zamiast z programu Device Enrollment Program firmy Apple w celu umożliwienia rejestracji urządzeń z systemem iOS przy pierwszym uruchomieniu. Dołączenie do usługi ASM jest wymagane w celu umożliwienia korzystania z aplikacji Classroom na udostępnionych urządzeniach iPad oraz włączenia synchronizacji danych pomiędzy usługą ASM i usługą Azure Active Directory za pośrednictwem usługi School Data Sync (SDS) firmy Microsoft.  

### <a name="shared-ipad-support---770395-1044681---"></a>Obsługa udostępnionego urządzenia iPad <!--770395, 1044681 -->

Usługa Intune będzie obsługiwać konfigurację trybu udostępnionego urządzenia iPad w profilu rejestracji dla programu Device Enrollment Program firmy Apple lub usługi Apple School Manager. To ustawienie umożliwia logowanie się przy użyciu wielu zarządzanych identyfikatorów Apple ID na tym samym urządzeniu.

Firma Microsoft będzie także rozszerzać obsługę funkcji zarządzania aplikacją Classroom dla urządzeń z systemem iOS w celu uwzględnienia studentów logujących się na udostępnionych urządzeniach iPad za pomocą zarządzanych identyfikatorów Apple ID.

### <a name="new-windows-device-restriction-settings---978585--"></a>Nowe ustawienia ograniczeń urządzeń z systemem Windows <!--978585-->

Dodajemy do profilu ograniczeń urządzenia z systemem Windows ustawienia, które kontrolują takie funkcje, jak ekrany bezprzewodowe, odnajdywanie urządzeń, przełączanie zadań i komunikaty o błędach karty SIM.

### <a name="office-365-proplus-app-available-for-windows-10-devices---1121362--"></a>Aplikacja Office 365 ProPlus dostępna dla urządzeń z systemem Windows 10 <!--1121362-->

Dodajemy nowy typ aplikacji Office 365 ProPlus, który ułatwi przypisywanie aplikacji usługi Office 365 ProPlus do urządzeń z systemem Windows 10. Ponadto użytkownicy posiadający licencje na programy Microsoft Project i Microsoft Visio będą mogli je zainstalować. Aplikacje będą ze sobą powiązane i będą wyświetlane jako jedna aplikacja na liście aplikacji w konsoli usługi Intune.

### <a name="new-allowblock-list-for-the-managed-browser---682960--"></a>Nowa lista dozwolonych/zablokowanych dla programu Managed Browser <!--682960-->

Możliwe będzie skonfigurowanie listy dozwolonych/zablokowanych domen i adresów URL dla programu Managed Browser przy użyciu ustawień konfiguracji aplikacji usługi Intune w portalu Azure Portal. Konfigurowanie listy dla programu Managed Browser będzie niezależnie od tego, czy jest on używany na urządzeniu zarządzanym, czy niezarządzanym.

### <a name="new-app-configuration-capabilities----677969---"></a>Nowe możliwości konfiguracji aplikacji <!-- 677969 -->

Ta funkcja będzie odpowiednikiem konfiguracji aplikacji do zarządzania urządzeniami mobilnymi (MDM). Umożliwia ona administratorom zastosowanie większej liczby wartości konfiguracji aplikacji niż tylko wartości konfiguracji aplikacji dostępne za pośrednictwem zasad ochrony aplikacji w usłudze MAM bez kanału rejestracji.

### <a name="new-app-protection-policies-conditions-for-mam---679864--"></a>Nowe warunki zasad ochrony aplikacji dla funkcji zarządzania aplikacjami mobilnymi (MAM) <!--679864-->

Możliwe będzie ustawienie za pośrednictwem konsoli administracyjnej wymogu dotyczącego funkcji MAM bez użytkowników rejestracji, który pozwoli na wymuszanie następujących parametrów:

- Minimalna wersja aplikacji
- Minimalna wersja systemu operacyjnego
- Minimalna wersja zestawu SDK aplikacji usługi Intune dla docelowych aplikacji (tylko system iOS)

Ta funkcja będzie dostępna zarówno dla systemu Android, jak i iOS. Usługa Intune obsługuje wymuszenie wersji minimalnej dla wersji platformy systemu operacyjnego, wersji aplikacji i zestawu SDK aplikacji usługi Intune. W systemie iOS dla aplikacji ze zintegrowanym zestawem SDK można również ustawić wymóg minimalnej wersji na poziomie zestawu SDK.

Użytkownik nie będzie mógł uzyskać dostępu do docelowej aplikacji w przypadku, gdy nie zostaną spełnione wymogi dotyczące minimalnej wersji w ramach zasad ochrony aplikacji na 3 różnych poziomach wymienionych powyżej. W tym momencie użytkownik będzie mógł usunąć swoje konto (w przypadku aplikacji z obsługą wielu tożsamości), zamknąć aplikację i/lub zaktualizować system operacyjny lub wersję aplikacji, aby spełnić wymagania.

Ponadto możliwe będzie również skonfigurowanie dodatkowych ustawień za pomocą konsoli administracyjnej, aby wyświetlić na urządzeniu użytkownika powiadomienie z zaleceniem uaktualnienia systemu operacyjnego lub aplikacji niepowodujące blokady urządzenia. Takie powiadomienie można zamknąć, aby następnie korzystać z aplikacji w zwykły sposób.

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Zmiana urzędu MDM bez wyrejestrowania zarządzanych urządzeń <!--1103950-->

Możliwa będzie zmiana urzędu certyfikacji MDM bez konieczności kontaktowania się z działem pomocy technicznej firmy Microsoft oraz wyrejestrowywania i ponownego rejestrowania istniejących zarządzanych urządzeń. W konsoli programu Configuration Manager możesz zmienić urząd MDM, wybierając opcję Ustaw Menedżera konfiguracji (hybrydowe) zamiast opcji Microsoft Intune (autonomiczne) lub odwrotnie.


### <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new-in-microsoft-intune.md).

