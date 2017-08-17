---
title: "Nowości w poprzednich miesiącach w usłudze Microsoft Intune"
titleSuffix: Intune on Azure
description: "Przejrzyj starsze powiadomienia o nowościach w usłudze Intune"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 8/02/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 31617fb9992937f43f5bfc3b882f09d4be7de7b6
ms.sourcegitcommit: 1c71fff769ca0097faf46fc2b58b953ff28386e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/08/2017
---
# <a name="whats-new-in-the-microsoft-intune---previous-months"></a>Nowości w usłudze Microsoft Intune — poprzednie miesiące

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="june-2017"></a>Czerwiec 2017

### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a>Nowy dostęp administracji opartej na rolach dla administratorów usługi Intune <!-- 1099990 -->  
Nowa rola administratora dostępu warunkowego jest dodawana w celu wyświetlania, tworzenia, modyfikowania i usuwania zasad dostępu warunkowego usługi Azure AD. Wcześniej uprawnienie to mieli tylko administratorzy globalni i administratorzy zabezpieczeń. Te uprawnienia roli mogą być nadane administratorom usługi Intune, aby mieli oni dostęp do zasad dostępu warunkowego.


### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a>Oznaczanie urządzeń należących do firmy przy użyciu numeru seryjnego<!-- 1215070 -->  
Usługa Intune obsługuje teraz przekazywanie numerów seryjnych systemów iOS, macOS i Android jako identyfikatorów urządzeń firmowych. Nie można używać numerów seryjnych do blokowania rejestracji urządzeń osobistych, ponieważ numery seryjne nie są weryfikowane podczas rejestracji. Blokowanie urządzeń osobistych za pomocą numerów seryjnych będzie obsługiwane w najbliższej przyszłości.


### <a name="new-remote-actions-for-ios-devices----854689---"></a>Nowe akcje zdalne dla urządzeń z systemem iOS <!-- 854689 -->
W tej wersji dodano dwie nowe akcje zdalnego urządzenia dla udostępnionych urządzeń iPad, które zarządzają aplikacją Apple Classroom:

-   [Wyloguj bieżącego użytkownika](device-logout-user.md) — powoduje wylogowanie bieżącego użytkownika z wybranego urządzenia z systemem iOS.
-   [Usuń użytkownika](device-remove-user.md) — powoduje usunięcie wybranego użytkownika z lokalnej pamięci podręcznej na urządzeniu z systemem iOS.


### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a>Obsługa udostępnionych urządzeń iPad przy użyciu aplikacji iOS Classroom <!-- 1044681 -->
W tej wersji rozszerzono obsługę funkcji zarządzania aplikacją Classroom dla systemu iOS w celu uwzględnienia uczniów logujących się na współużytkowanych tabletach iPad za pomocą zarządzanych identyfikatorów Apple ID.


### <a name="changes-to-intune-built-in-apps----1332306---"></a>Zmiany do wbudowanych aplikacji usługi Intune <!-- 1332306 -->
Wcześniej usługa Intune zawierała kilka wbudowanych aplikacji, które można było szybko przypisać. Na podstawie Twojej opinii usunęliśmy tę listę, a wbudowane aplikacje nie będą już dla Ciebie widoczne.
Jeśli jednak przypisano już jakiekolwiek wbudowane aplikacje, będą one nadal widoczne na liście aplikacji. W razie potrzeby te aplikacje mogą pozostać przypisane.
W nowszej wersji planujemy dodać łatwiejszy sposób wybierania i przypisywania wbudowanych aplikacji z portalu usługi Intune.

### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Łatwiejsza instalacja aplikacji usługi Office 365 <!--- 1121362 --->
Nowy typ aplikacji usługi **Office 365 ProPlus** ułatwia przypisywanie aplikacji usługi Office 365 ProPlus 2016 do zarządzanych przez Ciebie urządzeń z najnowszą wersją systemu Windows 10. Ponadto jeśli masz licencje na programy Microsoft Project i Microsoft Visio, masz możliwość ich zainstalowania. Potrzebne aplikacje są ze sobą powiązane i wyświetlane jako jedna aplikacja na liście aplikacji w konsoli usługi Intune.
Aby uzyskać więcej informacji, zobacz [How to add Office 365 apps for Windows 10](apps-add-office365.md) (Jak dodawać aplikacje usługi Office 365 dla systemu Windows 10).


### <a name="support-for-offline-apps-from-the-microsoft-store-for-business-----777044----"></a>Obsługa aplikacji offline ze Sklepu Microsoft dla Firm <!--- 777044 --->
Aplikacje offline zakupione ze Sklepu Microsoft dla Firm będą teraz synchronizowane z portalem usługi Intune. Następnie można wdrożyć te aplikacje w grupach urządzeń lub w grupach użytkowników. Aplikacje offline są instalowane przez usługę Intune, a nie przez sklep.

### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a>Aplikacja Microsoft Teams znajduje się obecnie na zawierającej zatwierdzone aplikacje liście dostępu warunkowego na podstawie aplikacji <!-- 1257019 -->
Aplikacja Microsoft Teams dla systemów iOS i Android stanowi teraz część zatwierdzonych aplikacji dla zasad dostępu warunkowego na podstawie aplikacji dla programów Exchange i SharePoint Online. Można skonfigurować tę aplikację za pomocą bloku Intune App Protection w witrynie Azure Portal do wszystkich dzierżawców używających obecnie dostępu warunkowego na podstawie aplikacji.

### <a name="managed-browser-and-app-proxy-integration----1287310---"></a>Integracja aplikacji Managed Browser i serwera proxy aplikacji <!-- 1287310 -->
Aplikację Intune Managed Browser można teraz zintegrować z usługą serwera proxy aplikacji usługi Azure AD, aby umożliwić użytkownikom dostęp do wewnętrznych witryn internetowych nawet wtedy, gdy pracują zdalnie. Użytkownicy przeglądarki wprowadzają adres URL witryny w normalny sposób, a aplikacja Managed Browser kieruje żądanie za pośrednictwem bramy internetowej serwera proxy aplikacji. Aby uzyskać więcej informacji, zobacz [Zarządzanie dostępem do Internetu za pomocą zasad programu Managed Browser](app-configuration-managed-browser.md).

### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a>Nowe ustawienia konfiguracji aplikacji dla Intune Managed Browser<!-- 682951 -->
W tej wersji dodano dodatkowe konfiguracje dla aplikacji Intune Managed Browser dla systemów iOS i Android. Można teraz skonfigurować domyślną stronę główną i zakładki do przeglądarki przy użyciu zasad konfiguracji aplikacji.
Aby uzyskać więcej informacji, zobacz [Zarządzanie dostępem do Internetu za pomocą zasad programu Managed Browser](app-configuration-managed-browser.md).

### <a name="bitlocker-settings-for-windows-10-----951707---"></a>Ustawienia funkcji BitLocker dla systemu Windows 10 <!-- 951707 -->
Teraz można skonfigurować ustawienia funkcji BitLocker dla urządzeń z systemem Windows 10 przy użyciu nowego profilu urządzeń usługi Intune. Można na przykład wymagać szyfrowania urządzeń, a także skonfigurować dodatkowe ustawienia, które są stosowane po włączeniu funkcji BitLocker.
Aby uzyskać więcej informacji, zobacz [Ustawienia programu Endpoint Protection dla systemu Windows 10 i nowszych wersji](endpoint-protection-windows-10.md).

### <a name="new-settings-for-windows-10-device-restriction-profile-----978527--978550-978569-1050031-1058611-----"></a>Nowe ustawienia dla profilu ograniczeń urządzenia z systemem Windows 10 <!--- 978527,  978550, 978569, 1050031, 1058611,  --->
W tej wersji dodano nowe ustawienia profilu ograniczeń urządzenia z systemem Windows 10 w następujących kategoriach:

-  Usługa Windows Defender
-  Sieć komórkowa i łączność
-  Środowisko ekranu blokady
-  Ochrona prywatności
-  Wyszukaj
-  W centrum uwagi Windows
-  Przeglądarka Edge

Aby uzyskać więcej informacji o ustawieniach systemu Windows 10, zobacz [Ustawienia ograniczeń urządzenia z systemem Windows 10 i nowszym](device-restrictions-windows-10.md).


### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>Aplikacja Portal firmy dla systemu Android ma teraz nowe środowisko użytkownika końcowego dla zasad ochrony aplikacji <!--1305217-->
Na podstawie opinii klientów zmodyfikowaliśmy aplikację Portal firmy dla systemu Android w celu wyświetlania przycisku **Dostęp do zawartości firmowej**. Ma to na celu zapobieganie niepotrzebnemu przechodzeniu przez użytkowników końcowych przez proces rejestracji, gdy potrzebują tylko dostępu do aplikacji obsługujących zasady ochrony aplikacji, czyli funkcję zarządzania aplikacjami mobilnymi usługi Intune. Zmiany te są widoczne na stronie [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Nowa akcja menu do łatwego usuwania Portalu firmy <!--1164569-->
W odpowiedzi na opinie użytkowników w aplikacji Portal firmy dla systemu Android została dodana nowa akcja menu do inicjowania usunięcia Portalu firmy z urządzenia. Powoduje ona usunięcie urządzenia z zarządzania w usłudze Intune, dzięki czemu użytkownik może samodzielnie usunąć aplikację z urządzenia. Zmiany te są widoczne na stronie [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md) oraz w [dokumentacji użytkownika końcowego systemu Android](/intune-user-help/unenroll-your-device-from-intune-android).

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Ulepszenia synchronizacji aplikacji w wersji Aktualizacja systemu Windows 10 dla twórców <!--676505-->
Aplikacja Portal firmy dla systemu Windows 10 będzie teraz automatycznie inicjować synchronizację żądań instalacji aplikacji dla urządzeń z systemem w wersji Aktualizacja systemu Windows 10 dla twórców (wersja 1703). Pozwoli to ograniczyć problem związany z zatrzymywaniem się instalacji aplikacji w stanie „Oczekiwanie na synchronizację”. Ponadto użytkownicy będą mogli ręcznie zainicjować synchronizację z poziomu aplikacji. Zmiany te są widoczne na stronie [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Nowe środowisko z przewodnikiem dla Portalu firmy systemu Windows 10 <!---1058938--->
Aplikacja Portal firmy dla systemu Windows 10 będzie zawierać wskazówki przewodnika usługi Intune dla urządzeń, które nie zostały zidentyfikowane ani zarejestrowane. Nowe środowisko obejmuje instrukcje krok po kroku, które prowadzą użytkownika przez proces rejestracji w usłudze Azure Active Directory (wymaganej dla funkcji dostępu warunkowego) oraz rejestracji MDM (wymaganej dla funkcji zarządzania urządzeniami). Przewodnik obsługi będzie dostępny na stronie głównej Portalu firmy. Użytkownicy mogą nadal używać aplikacji, jeśli nie ukończą rejestracji, ale może wystąpić ograniczenie funkcjonalności.

Ta aktualizacja jest widoczna tylko na urządzeniach z Rocznicową aktualizacją systemu Windows 10 (kompilacją 1607) i nowszymi wersjami. Zmiany te są widoczne na stronie [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).


### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Konsole administracyjne usługi Microsoft Intune i dostępu warunkowego są ogólnie dostępne
Firma Microsoft informuje o ogólnej dostępności nowej usługi Intune w konsoli administracyjnej platformy Azure i konsoli administracyjnej dostępu warunkowego. Za pomocą usługi Intune na platformie Azure można teraz zarządzać wszystkimi możliwościami MAM i MDM usługi Intune w jednym skonsolidowanym środowisku administratora i korzystać z funkcji grupowania i określania odbiorców docelowych w usłudze Azure AD. Dostęp warunkowy na platformie Azure oferuje zaawansowane możliwości w usługach Azure AD i Intune w jednej ujednoliconej konsoli. W środowisku administracyjnym przeniesienie na platformę Azure umożliwia korzystanie z nowoczesnych przeglądarek.

Usługa Intune jest teraz widoczna bez etykiety **wersji zapoznawczej** w konsoli platformy Azure pod adresem portal.azure.com.

Obecnie istniejący klienci nie muszą podejmować żadnych działań, chyba że użytkownik otrzyma jeden z serii komunikatów z centrum wiadomości z żądaniem podjęcia działania, dzięki któremu będziemy mogli migrować jego grupy. Użytkownik mógł również otrzymać powiadomienie z centrum wiadomości informujące o tym, że migracja trwa dłużej z powodu błędów występujących po naszej stronie. Firma Microsoft nadal usilnie pracuje nad tym, by przeprowadzić migrację wszystkich klientów, na których to miało wpływ.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>Ulepszone kafelki aplikacji w Portalu firmy dla systemu iOS
Zaktualizowaliśmy wygląd kafelków aplikacji na stronie głównej, aby odpowiadał on kolorowi ustawionemu dla Portalu firmy. Aby uzyskać więcej informacji, zobacz temat [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Selektor konta już dostępny w aplikacji Portal firmy dla systemu iOS
Dla użytkowników urządzeń z systemem iOS nasz nowy selektor konta może być widoczny po zalogowaniu się do Portalu firmy, jeśli użyją konta służbowego do zalogowania się do innych aplikacji firmy Microsoft. Aby uzyskać więcej informacji, zobacz temat [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

## <a name="may-2017"></a>Maj 2017 r.

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Zmiana urzędu MDM bez wyrejestrowania zarządzanych urządzeń <!--1103950-->
Teraz będzie można zmienić urząd MDM bez konieczności kontaktowania się z działem pomocy technicznej firmy Microsoft oraz wyrejestrowywania i ponownego rejestrowania istniejących urządzeń zarządzanych. W konsoli programu Configuration Manager można [zmienić urząd MDM](/sccm/mdm/deploy-use/change-mdm-authority), wybierając opcję Ustaw Menedżera konfiguracji (hybrydowe) zamiast opcji Microsoft Intune (autonomiczne) lub odwrotnie.


### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Ulepszone powiadomienia dotyczące numerów PIN wymaganych do uruchomiania urządzeń z obsługą platformy Samsung KNOX <!--1087143-->
W przypadku gdy użytkownicy końcowi muszą skonfigurować numer PIN wpisywany po uruchomieniu urządzenia z obsługą platformy Samsung KNOX w celu zapewnienia zgodności z szyfrowaniem, dotknięcie wyświetlonego powiadomienia umożliwi przejście bezpośrednio do odpowiedniego ustawienia.  Wcześniej dotknięcie powiadomienia na urządzeniu użytkownika końcowego powodowało przejście do ekranu zmiany hasła.

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="apple-school-manager-asm-support-with-shared-ipad----748864-770395--"></a>Obsługa usługi Apple School Manager (ASM) w przypadku udostępnionego urządzenia iPad <!-- 748864, 770395-->

Usługa Intune obsługuje obecnie korzystanie z usługi Apple School Manager (ASM) zamiast z programu Device Enrollment Program firmy Apple w celu umożliwienia rejestracji urządzeń z systemem iOS przy pierwszym uruchomieniu. Dołączenie do usługi ASM jest wymagane w celu umożliwienia korzystania z aplikacji Classroom na udostępnionych urządzeniach iPad oraz włączenia synchronizacji danych pomiędzy usługą ASM i usługą Azure Active Directory za pośrednictwem usługi School Data Sync (SDS) firmy Microsoft. Aby uzyskać więcej informacji, zobacz [Włączanie rejestracji urządzeń z systemem iOS za pomocą usługi Apple School Manager](apple-school-manager-set-up-ios.md).

> [!NOTE]
> Konfigurowanie udostępnionych urządzeń iPad do pracy z aplikacją Classroom wymaga konfiguracji programu Education dla systemu iOS na platformie Azure, które nie są jeszcze dostępne.  Ta funkcja zostanie wkrótce dodana.

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="provide-remote-assistance-to-android-devices-using-teamviewer----675418---"></a>Zapewnienie pomocy zdalnej na urządzeniach z systemem Android przy użyciu programu TeamViewer<!-- 675418 -->

Usługa Intune może teraz korzystać z zakupionego osobno oprogramowania [TeamViewer](https://www.teamviewer.com), aby umożliwić oferowanie pomocy zdalnej użytkownikom urządzeń z systemem Android. Więcej informacji można znaleźć w temacie [Zapewnienie pomocy zdalnej dla urządzeń z systemem Android zarządzanych przy użyciu usługi Intune](device-profile-android-teamviewer.md).

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="new-app-protection-policies-conditions-for-mam----679864---"></a>Nowe warunki zasad ochrony aplikacji dla funkcji zarządzania aplikacjami mobilnymi (MAM) <!-- 679864 -->

Teraz można ustawić wymóg dotyczący funkcji MAM bez użytkowników rejestracji, co wymusza następujące zasady:

- Minimalna wersja aplikacji
- Minimalna wersja systemu operacyjnego
- Minimalna wersja zestawu SDK aplikacji usługi Intune dla docelowych aplikacji (tylko system iOS)

Funkcja ta jest dostępna w systemach Android i iOS. Usługa Intune obsługuje wymuszenie wersji minimalnej dla wersji platformy systemu operacyjnego, wersji aplikacji i zestawu SDK aplikacji usługi Intune. W systemie iOS dla aplikacji ze zintegrowanym zestawem SDK można również ustawić wymóg minimalnej wersji na poziomie zestawu SDK. Użytkownik nie będzie mógł uzyskać dostępu do docelowej aplikacji w przypadku, gdy nie zostaną spełnione wymogi dotyczące minimalnej wersji w ramach zasad ochrony aplikacji na trzech różnych poziomach wymienionych powyżej. W tym momencie użytkownik będzie mógł usunąć swoje konto (w przypadku aplikacji z obsługą wielu tożsamości), zamknąć aplikację lub zaktualizować wersję systemu operacyjnego lub aplikacji.

Można również skonfigurować dodatkowe ustawienia, aby wyświetlić na urządzeniu użytkownika powiadomienie z zaleceniem uaktualnienia systemu operacyjnego lub aplikacji niepowodujące blokady urządzenia. Takie powiadomienie można zamknąć, aby następnie korzystać z aplikacji w zwykły sposób.

Więcej informacji można znaleźć w tematach [Ustawienia zasad ochrony aplikacji dla systemu iOS](app-protection-policy-settings-ios.md) oraz [Ustawienia zasad ochrony aplikacji dla systemu Android](app-protection-policy-settings-android.md).

#### <a name="configure-app-configurations-for-android-for-work----621621---"></a>Konfigurowanie ustawień aplikacji dla programu Android for Work <!-- 621621 -->
Niektóre aplikacje dla systemu Android ze sklepu obsługują opcje konfiguracji zarządzanych, które umożliwiają administratorowi IT kontrolowanie działania aplikacji w profilu służbowym. Przy użyciu usługi Intune można teraz wyświetlić konfiguracje obsługiwane przez aplikację i skonfigurować je w portalu usługi Intune za pomocą projektanta konfiguracji lub edytora JSON. Aby uzyskać więcej informacji, zobacz artykuł [Use app configurations for Android for Work](app-configuration-policies-use-android.md) (Używanie konfiguracji aplikacji dla programu Android for Work).

#### <a name="new-app-configuration-capability-for-mam-without-enrollment----677969---"></a>Nowe możliwości konfiguracji aplikacji dla funkcji MAM bez rejestracji<!-- 677969 -->
Teraz można tworzyć zasady konfiguracji aplikacji za pomocą funkcji MAM bez użycia kanału rejestracji. Ta funkcja jest odpowiednikiem zasad konfiguracji aplikacji dostępnych w konfiguracji aplikacji funkcji zarządzania urządzeniami mobilnymi (MDM). Przykład konfiguracji aplikacji przy użyciu funkcji MAM bez rejestracji znajduje się w temacie [Zarządzanie dostępem do Internetu za pomocą zasad programu Managed Browser w usłudze Microsoft Intune](app-configuration-managed-browser.md).

#### <a name="configure-allowed-and-blocked-url-lists-for-the-managed-browser----682960---"></a>Konfigurowanie list dozwolonych i zablokowanych adresów URL dla programu Managed Browser <!-- 682960 -->
Teraz można skonfigurować listę dozwolonych i zablokowanych domen oraz adresów URL dla programu Managed Browser w usłudze Intune przy użyciu ustawień konfiguracji aplikacji w witrynie Azure Portal. Ustawienia te można skonfigurować niezależnie od tego, czy są one używane na urządzeniu zarządzanym, czy niezarządzanym. Aby uzyskać więcej informacji, zobacz temat [Zarządzanie dostępem do Internetu za pomocą zasad programu Managed Browser w usłudze Microsoft Intune](app-configuration-managed-browser.md).

#### <a name="app-protection-policy-helpdesk-view----1069473---"></a>Widok pomocy technicznej zasad ochrony aplikacji <!-- 1069473 -->
Użytkownicy pomocy technicznej z działu IT mogą teraz sprawdzić stan licencji użytkownika i stan aplikacji zasad ochrony aplikacji przypisane do użytkowników w bloku Rozwiązywanie problemów. Aby uzyskać szczegółowe informacje, zobacz temat [Rozwiązywanie problemów](./help-desk-operators.md).

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="control-website-visits-on-ios-devices----723832---"></a>Kontrola odwiedzin w witrynach internetowych na urządzeniach z systemem iOS <!-- 723832 -->
Teraz przy użyciu jednej z następujących dwóch metod można kontrolować, które witryny internetowe mogą odwiedzać użytkownicy urządzeń z systemem iOS:

- Dodaj dozwolone i zablokowane adresy URL przy użyciu wbudowanych filtrów zawartości sieci Web w urządzeniach firmy Apple.

- Zezwalaj tylko na dostęp do określonych witryn sieci Web za pośrednictwem przeglądarki Safari. Dla każdej określonej witryny jest tworzona zakładka w przeglądarce Safari.

Aby uzyskać więcej informacji, zobacz temat [Ustawienia filtru zawartości sieci Web dla urządzeń z systemem iOS](web-content-filter-settings-ios.md).

#### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Wstępna konfiguracja uprawnień urządzenia dla aplikacji Android for Work <!-- 621614 -->
W przypadku aplikacji wdrożonych w ramach profilów służbowych urządzenia z programem Android for Work można teraz skonfigurować stan uprawnień dla poszczególnych aplikacji.  Domyślnie aplikacje systemu Android, które wymagają uprawnień urządzenia, takich jak dostęp do lokalizacji lub aparatu urządzenia, wyświetlają monit o zaakceptowanie lub odrzucenie uprawnień przez użytkownika.  Na przykład jeśli aplikacja używa mikrofonu urządzenia, użytkownik końcowy otrzyma monit o przyznanie aplikacji uprawnienia do użycia mikrofonu. Ta funkcja pozwala zdefiniować uprawnienia w imieniu użytkownika końcowego.  Można skonfigurować uprawnienia, aby a) automatycznie odmawiać bez powiadomienia użytkownika, b) automatycznie zatwierdzać bez powiadomienia użytkownika lub c) monitować użytkownika o zaakceptowanie lub odmówienie. Aby uzyskać więcej informacji, zobacz temat [Ustawienia ograniczeń urządzenia z programem Android for Work w usłudze Microsoft Intune](device-restrictions-android-for-work.md).

#### <a name="define-app-specific-pin-for-android-for-work-devices----728976-1102534---"></a>Ustawienie numeru PIN dla aplikacji na urządzeniach z programem Android for Work <!-- 728976, 1102534 -->
Na urządzeniach z systemem Android w wersji 7.0 lub nowszej z profilem służbowym zarządzanym jako urządzenie z programem Android for Work możliwe będzie zdefiniowanie zasad kodu dostępu, które będą dotyczyć tylko aplikacji w profilu służbowym.  Dostępne opcje:

- Zdefiniowanie zasad kodu dostępu obejmujących całe urządzenie — jest to kod dostępu, którego użytkownik musi użyć w celu odblokowania całego urządzenia.
- Zdefiniowanie zasad kodu dostępu obejmujących wyłącznie profil służbowy — użytkownicy otrzymają monit o podanie kodu dostępu przy każdym otwarciu dowolnej aplikacji w profilu służbowym.
- Zdefiniowanie zasad kodu dostępu obejmujących zarówno urządzenie, jak i profil służbowy — administrator IT ma możliwość zdefiniowania zarówno zasad kodu dostępu dla urządzenia, jak i zasad kodu dostępu dotyczących profilu służbowego o różnej sile (np. 4-cyfrowy numer PIN do odblokowywania urządzenia i 6-cyfrowy numer PIN do otwierania dowolnej aplikacji w profilu służbowym).

Aby uzyskać więcej informacji, zobacz temat [Ustawienia ograniczeń urządzenia z programem Android for Work w usłudze Microsoft Intune](device-restrictions-android-for-work.md).

> [!NOTE]
> Ta opcja jest dostępna wyłącznie w systemie Android w wersji 7.0 i nowszych.  Domyślnie użytkownik końcowy może używać dwóch różnych numerów PIN lub wybrać opcję połączenia dwóch zdefiniowanych numerów PIN w celu uzyskania numeru PIN o większej sile.

#### <a name="new-settings-for-windows-10-devices----978585---"></a>Nowe ustawienia dla urządzeń z systemem Windows 10<!-- 978585 -->
Dodaliśmy nowe [ustawienia ograniczeń dla urządzenia z systemem Windows](device-restrictions-windows-10.md), które kontrolują takie funkcje, jak ekrany bezprzewodowe, odnajdywanie urządzeń, przełączanie zadań i komunikaty o błędach karty SIM.

#### <a name="updates-to-certificate-configuration----918991-and-823198---"></a>Aktualizacje konfiguracji certyfikatu <!-- 918991 and 823198 -->
Podczas tworzenia profilu certyfikatu SCEP dla pozycji **Format nazwy podmiotu**, opcja **Niestandardowy** jest dostępna dla urządzeń z systemami iOS, Android i Windows. Przed tą aktualizacją pole **Niestandardowy** było dostępne tylko dla urządzeń z systemem iOS. Aby uzyskać więcej informacji, zobacz temat [ Tworzenie profilu certyfikatu protokołu SCEP] (certificates-scep-configure.md#how-to-create-a-scep-certificate-profile).

Podczas tworzenia profilu certyfikatu PKCS dla pozycji **Alternatywna nazwa podmiotu** dostępna jest opcja **Atrybut niestandardowy usługi Azure AD**. Opcja **Dział** jest dostępna po wybraniu opcji **Atrybut niestandardowy usługi Azure AD**. Aby uzyskać więcej informacji, zobacz temat [Tworzenie profilu certyfikatu PKCS] (certficates-pfx-configure.md#how-to-create-a-pkcs-certificate-profile).

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode----662059---"></a>Konfigurowanie wielu aplikacji, które można uruchomić, gdy urządzenie z systemem Android jest w trybie kiosku<!-- 662059 -->
Wcześniej można było skonfigurować tylko jedną aplikację możliwą do uruchomienia, gdy urządzenie z systemem Android jest w trybie kiosku. Teraz można skonfigurować wiele aplikacji przy użyciu identyfikatora aplikacji, adres URL sklepu lub wybierając zarządzaną już aplikację systemu Android. Aby uzyskać więcej informacji, zobacz [Ustawienia trybu kiosku](device-restrictions-android.md#kiosk).



## <a name="april-2017"></a>Kwiecień 2017

### <a name="support-for-managing-the-apple-classroom-app"></a>Obsługa zarządzania aplikacji Classroom firmy Apple
Teraz można zarządzać aplikacją Classroom dla systemu iOS na urządzeniach iPad. Skonfiguruj aplikację Classroom na tablecie iPad dla nauczycieli, podając poprawne dane dotyczące klasy i uczniów, następnie skonfiguruj tablety iPad dla uczniów zarejestrowane dla danej klasy, aby mieć możliwość sterowania nimi przy użyciu aplikacji.
Aby uzyskać szczegółowe informacje, zobacz temat [Konfigurowanie ustawień usług edukacyjnych dla urządzeń z systemem iOS](education-settings-configure-ios.md).

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Obsługa opcji zarządzanych konfiguracji dla aplikacji systemu Android <!-- 621621 -->
Za pośrednictwem usługi Intune można teraz skonfigurować przeznaczone dla systemu Android aplikacje ze sklepu Play, które obsługują zarządzane opcje konfiguracji.  Ta funkcja umożliwia pracownikom działu IT wyświetlanie listy wartości konfiguracji obsługiwanych przez aplikację oraz zapewnia najwyższej klasy interfejs użytkownika z przewodnikiem, dzięki któremu można skonfigurować te wartości.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Nowe zasady dla systemu Android dotyczące złożonych numerów PIN <!-- 722069 -->
W przypadku urządzeń z systemem Android 5.0 lub nowszym można teraz ustawić w profilu urządzenia wymagany typ [hasła](device-restrictions-android.md#password) na „Złożona wartość liczbowa”.  Użyj tego ustawienia, aby uniemożliwić użytkownikom tworzenie numerów PIN zawierających powtarzające się lub kolejne liczby, np. 1111 lub 1234.

### <a name="additional-support-for-android-for-work-devices"></a>Dodatkowa obsługa urządzeń z programem Android for Work
- **Zarządzaj ustawieniami hasła i profilu służbowego** <!-- 612808 -->

  Te nowe zasady ograniczeń dla urządzeń z programem Android for Work umożliwiają teraz zarządzanie ustawieniami hasła i profilu służbowego na zarządzanych urządzeniach z programem Android for Work.

- **Zezwalaj na współużytkowanie danych między profilem służbowym i osobistym** <!-- 1045102 -->

Ten profil ograniczeń urządzenia z programem Android for Work oferuje teraz nowe opcje pozwalające skonfigurować udostępnianie danych między profilami służbowym i osobistym.

- **Ogranicz kopiowanie i wklejanie między profilami służbowymi i osobistymi** <!-- 1046094 -->

  Nowy niestandardowy profil urządzenia dla urządzeń z programem Android for Work umożliwia obecnie określenie, czy akcje kopiowania i wklejania między aplikacjami służbowymi i osobistymi mają być dozwolone.

Aby uzyskać więcej informacji, zobacz artykuł [Ograniczenia urządzenia z programem Android for Work](device-restrictions-android-for-work.md).

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>Przypisuj aplikacje LOB do urządzeń z systemem iOS lub Android <!-- 1057568 -->
Możesz teraz przypisywać różne aplikacje biznesowe (LOB) dla systemu [iOS](lob-apps-ios.md) (pliki ipa) lub [Android](lob-apps-android.md) (pliki apk) do użytkowników lub urządzeń.


###  <a name="new-device-policies-for-ios----723774-723815-723826-723830---"></a>Nowe zasady dotyczące urządzeń dla systemu iOS <!-- 723774, 723815, 723826, 723830 -->
- **Aplikacje na ekranie głównym** — pozwala określić, które aplikacje użytkownik może zobaczyć na [ekranie głównym swojego urządzenia z systemem iOS](home-screen-settings-ios.md). Zasady te zmieniają układ ekranu głównego, ale nie wdrażają żadnych aplikacji.

- **Połączenia z urządzeniami AirPrint** — pozwala określić, z którymi [urządzeniami AirPrint](air-print-settings-ios-macos.md) (drukarkami sieciowymi) użytkownicy końcowi urządzeń z systemem iOS będą mogli nawiązywać połączenie.

- **Połączenia z urządzeniami AirPlay** — pozwala określić, z którymi [urządzeniami AirPlay](airplay-settings-ios.md) (np. urządzeniami Apple TV) użytkownicy końcowi urządzeń z systemem iOS będą mogli nawiązywać połączenie.

- **Niestandardowy komunikat ekranu blokady** — pozwala skonfigurować niestandardowy komunikat, który użytkownicy zobaczą na ekranie blokady urządzenia z systemem iOS zamiast domyślnego komunikatu ekranu blokady. Aby uzyskać więcej informacji, zobacz [Aktywowanie trybu zgubienia na urządzeniach z systemem iOS](device-lost-mode.md).

### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>Ogranicz powiadomienia wypychane dla aplikacji systemu iOS <!-- 723767 -->
W profilu ograniczeń urządzenia w usłudze Intune możesz teraz skonfigurować następujące [ustawienia powiadomień](app-notification-settings-ios.md) dla urządzeń z systemem iOS:

- W pełni włączyć lub wyłączyć powiadomienia dla określonej aplikacji.
- Włączyć lub wyłączyć powiadomienia w centrum powiadomień dla określonej aplikacji.
- Określić typ alertu: **Brak**, **Transparent** lub **Alert modalny**.
- Określić, czy identyfikatory są dozwolone dla tej aplikacji.
- Określić, czy dźwięki powiadomień są dozwolone.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>Skonfiguruj aplikacje systemu iOS do autonomicznego uruchamiania w trybie pojedynczej aplikacji <!-- 737837 -->
Możesz teraz użyć profilu urządzenia w usłudze Intune do skonfigurowania urządzeń z systemem iOS, aby uruchamiać określone aplikacje w [autonomicznym trybie pojedynczej aplikacji](device-restrictions-ios.md#autonomous-single-app-mode-supervised-only). Jeśli skonfigurowano ten tryb, a aplikacja zostanie uruchomiona, urządzenie zostanie zablokowane, aby mogło uruchamiać wyłącznie tę aplikację. Opcję tę można przykładowo wykorzystać w przypadku konfigurowania aplikacji, która umożliwia użytkownikom wykonywanie testów na urządzeniu. Po zakończeniu działań aplikacji lub usunięciu tych zasad urządzenie powraca do normalnego stanu.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>Skonfiguruj zaufane domeny dla poczty e-mail i przeglądania sieci Web na urządzeniach z systemem iOS <!-- 723765 -->
W profilu ograniczeń urządzenia z systemem iOS możesz teraz skonfigurować następujące [ustawienia domen](device-restrictions-ios.md#domains):

- **Nieoznaczone domeny poczty e-mail** — wiadomości e-mail wysyłane lub odbierane przez użytkownika, które nie pasują do domen określonych w tym miejscu, będą oznaczone jako niezaufane.

- **Zarządzane domeny sieci Web** — dokumenty pobierane z adresów URL określonych w tym miejscu będą uznawane za zarządzane (tylko przeglądarka Safari).  

- **Domeny automatycznego uzupełniania haseł przeglądarki Safari** — użytkownicy mogą zapisywać hasła w przeglądarce Safari tylko w przypadku adresów URL spełniających wzorce określone w tym miejscu. Aby użyć tego ustawienia, urządzenie musi być w trybie nadzorowanym i nie może być skonfigurowane dla wielu użytkowników. (iOS 9.3+)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>Aplikacje VPP dostępne w aplikacji Portal firmy dla systemu iOS <!-- 748782 -->
Możesz teraz przypisać aplikacje dla systemu iOS zakupione zbiorczo (VPP) jako **Dostępne** instalacje do użytkowników końcowych. Użytkownicy końcowi potrzebują konta sklepu Apple Store, aby zainstalować aplikację.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>Synchronizuj książki elektroniczne ze sklepu Apple VPP Store <!-- 800878 -->
Możesz teraz [synchronizować książki](vpp-apps-ios.md) zakupione w sklepie programu zakupów zbiorczych Apple przy użyciu usługi Intune i przypisywać je do użytkowników.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Zarządzanie wieloma użytkownikami w przypadku urządzeń Samsung KNOX Standard <!-- 971988 -->
Urządzenia z systemem Samsung KNOX Standard są teraz obsługiwane w przypadku [zarządzania wieloma użytkownikami](android-enroll.md) przez usługę Intune. Oznacza to, że użytkownicy końcowi mogą zalogować się na urządzeniu przy użyciu poświadczeń usługi Azure Active Directory lub wylogować się z niego, a urządzenie jest zarządzane centralnie niezależnie od tego, czy jest używane.  Po zalogowaniu się użytkownicy końcowi otrzymują dostęp do aplikacji oraz zostają wobec nich zastosowane zasady. Gdy użytkownicy się wylogują, wszystkie dane aplikacji są usuwane.

### <a name="additional-windows-device-restriction-settings----818566---"></a>Dodatkowe ustawienia ograniczeń urządzeń z systemem Windows <!-- 818566 -->
Dodaliśmy obsługę dodatkowych [ustawień ograniczeń urządzeń z systemem Windows](device-restrictions-windows-10.md), np. dodatkową obsługę przeglądarki Edge, dostosowywanie ekranu blokady na urządzeniu, dostosowywanie menu Start, tapetę zestawu wyszukiwania W centrum uwagi Windows oraz ustawienia serwera proxy.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Obsługa wielu użytkowników w aktualizacji Windows 10 Creators Update <!-- 822547 -->
Dodaliśmy obsługę [zarządzania wieloma użytkownikami](windows-enroll.md) na urządzeniach z aktualizacją systemu Windows 10 dla twórców, które zostały dołączone do domeny usługi Azure Active Directory. Oznacza to, że różni użytkownicy standardowi po zalogowaniu się do urządzenia przy użyciu poświadczeń usługi Azure AD otrzymują wszelkie aplikacje i zasady, które zostały przypisane do ich nazw użytkowników. Obecnie użytkownicy nie mogą używać witryny internetowej Portal firmy na potrzeby samoobsługowych scenariuszy, takich jak instalowanie aplikacji.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Świeży początek dla komputerów z systemem Windows 10<!-- 1004830 -->
Dla komputerów z systemem Windows 10 dostępna jest nowa [akcja odświeżonego uruchomienia urządzenia](device-fresh-start.md).  Po wykonaniu tej akcji wszelkie aplikacje zainstalowane na komputerze zostaną usunięte, a komputer zostanie automatycznie zaktualizowany do najnowszej wersji systemu Windows. Funkcja może być przydatna do usuwania wstępnie zainstalowanych aplikacji OEM, które są często dostarczane z nowymi komputerami. Możesz zdecydować, czy dane użytkownika zostaną zachowane w przypadku wykonania tej akcji dla urządzenia.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>Dodatkowe ścieżki uaktualniania systemu Windows 10 <!-- 903672 -->
Można teraz tworzyć [zasady uaktualniania wersji umożliwiające uaktualnienie urządzeń](edition-upgrade-configure-windows-10.md) do następujących dodatkowych wersji systemu Windows 10:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Rejestracja zbiorcza urządzeń z systemem Windows 10 <!-- 747607 -->
Teraz możesz łączyć dużą liczbę urządzeń z aktualizacją systemu Windows 10 dla twórców z usługami Azure Active Directory oraz Intune, korzystając z aplikacji Windows Configuration Designer (WCD). Aby włączyć [zbiorcze rejestrowanie w usłudze MDM](windows-bulk-enroll.md) dla dzierżawy usługi Azure AD, utwórz pakiet aprowizacyjny, który dołącza urządzenia do dzierżawy usługi Azure AD, przy użyciu aplikacji Windows Configuration Designer, i zastosuj pakiet do firmowych urządzeń, które chcesz zarejestrować i którymi chcesz zarządzać w sposób zbiorczy. Po zastosowaniu pakietu urządzenia dołączają do usługi Azure AD, rejestrują się w usłudze Intune i umożliwiają logowanie użytkownikom usługi Azure AD.  Użytkownicy usługi Azure AD są standardowymi użytkownikami tych urządzeń i otrzymują przypisane zasady oraz wymagane aplikacje. Scenariusze samoobsługowe i scenariusze użycia aplikacji Portal firmy nie są obecnie obsługiwane.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----581122-736644---"></a>Nowe ustawienia MAM dla numerów PIN i zarządzanych lokalizacji przechowywania <!-- 581122, 736644 -->
Obecnie są dostępne dwa nowe ustawienia aplikacji, które pomagają w zarządzaniu aplikacjami mobilnymi (MAM):

- **Wyłącz numer PIN aplikacji, jeśli numer PIN urządzenia jest zarządzany** — wykrywa, czy numer PIN urządzenia jest obecny na zarejestrowanym urządzeniu; jeśli tak jest, pomija numer PIN aplikacji wyzwalany przez zasady ochrony aplikacji. Ustawienie to umożliwia zredukowanie liczby monitów o numer PIN wyświetlanych dla użytkowników podczas otwierania na zarejestrowanym urządzeniu aplikacji z włączonym zarządzaniem aplikacjami mobilnymi. Funkcja ta jest dostępna dla systemów Android i iOS.

- **Wybierz, w których usługach magazynu można zapisywać dane firmowe** — umożliwia określenie lokalizacji przechowywania, w której należy zapisywać dane firmowe. Użytkownicy mogą zapisywać w wybranych usługach służących do zarządzania lokalizacjami przechowywania. Oznacza to, że wszystkie inne usługi zarządzające lokalizacjami przechowywania, które nie znajdą się na liście, zostaną zablokowane.

  Lista obsługiwanych usług zarządzających lokalizacjami przechowywania:

  - OneDrive
  - Business SharePoint Online
  - Magazyn lokalny

### <a name="help-desk-troubleshooting-portal----907448---"></a>Portal pomocy technicznej służący do rozwiązywania problemów <!-- 907448 -->
Nowy [portal służący do rozwiązywania problemów](help-desk-operators.md) umożliwia operatorom pomocy technicznej i administratorom usługi Intune wyświetlać użytkowników i ich urządzenia oraz wykonywać zadania mające na celu rozwiązywanie problemów technicznych związanych z usługą Intune.

## <a name="march-2017"></a>Marzec 2017

### <a name="support-for-ios-lost-mode---431695--"></a>Obsługa trybu utraty w systemie iOS<!--431695-->
Dla urządzeń z systemem iOS w wersji 9.3 i późniejszych w usłudze Intune dodano obsługę **trybu utraty**. Teraz możesz zablokować urządzenie, aby uniemożliwić jego użycie w jakikolwiek sposób, oraz wyświetlić komunikat i numer telefonu kontaktowego na ekranie blokady urządzenia.

Użytkownik końcowy nie będzie mógł odblokować urządzenia aż do chwili, gdy administrator wyłączy tryb utraty. Po włączeniu trybu utraty można skorzystać z akcji **Zlokalizuj urządzenie**, aby wyświetlić w konsoli usługi Intune lokalizację geograficzną urządzenia na mapie.

Urządzenie musi być urządzeniem z systemem iOS, należącym do firmy, zarejestrowanym w usłudze DEP i objętym trybem nadzorowanym.

Aby uzyskać więcej informacji, zobacz artykuł [Co to jest zarządzanie urządzeniami w usłudze Microsoft Intune?](device-management.md)

### <a name="improvements-to-device-actions-report---677150--"></a>Ulepszenia w zakresie raportu dotyczącego akcji związanych z urządzeniami <!--677150-->
Wprowadziliśmy ulepszenia w zakresie raportu dotyczącego akcji związanych z urządzeniami w celu zwiększenia wydajności. Ponadto raport można teraz filtrować według stanu. Można na przykład filtrować raport w taki sposób, aby wyświetlić tylko te akcje związane z urządzeniem, które zostały zakończone.

### <a name="custom-app-categories---748805--"></a>Niestandardowe kategorie aplikacji <!--748805-->
Możesz teraz tworzyć, edytować i przypisywać kategorie dla aplikacji dodawanych do usługi Intune. Obecnie kategorie można określać tylko w języku angielskim.
Zobacz [Jak dodać aplikację do usługi Intune](apps-add.md).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>Przypisywanie aplikacji biznesowych do użytkowników z wyrejestrowanymi urządzeniami <!--748823-->
Użytkownikom można teraz przypisywać aplikacje biznesowe ze sklepu niezależnie od tego, czy ich urządzenia są zarejestrowane w usłudze Intune. Jeśli urządzenie użytkownika nie jest zarejestrowane w usłudze Intune, w celu jej zainstalowania użytkownik musi przejść do witryny sieci Web Portal firmy zamiast do aplikacji Portal firmy.

### <a name="new-compliance-reports---846671--"></a>Nowe raporty dotyczące zgodności <!--846671-->
Można teraz korzystać z raportów zgodności, które dostarczają informacje na temat stanu zgodności urządzeń w Twojej firmie i pozwalają na szybkie rozwiązywanie problemów ze zgodnością napotykanych przez użytkowników. Możliwe jest wyświetlanie informacji dotyczących następujących kwestii:

- ogólny stan zgodności urządzeń,
- stan zgodności poszczególnych ustawień,
- stan zgodności poszczególnych zasad.

Raportów można także użyć do przechodzenia do informacji szczegółowych dotyczących poszczególnych urządzeń, aby wyświetlić konkretne ustawienia i zasady, które mają wpływ na to urządzenie.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Bezpośredni dostęp do scenariuszy rejestracji firmy Apple <!--951869-->
Na kontach usługi Intune utworzonych po styczniu 2017 roku włączono bezpośredni dostęp do scenariuszy rejestracji firmy Apple przy użyciu obciążenia Rejestruj urządzenia w witrynie Azure Portal. Wcześniej podgląd rejestracji firmy Apple był dostępny tylko z poziomu linków w klasycznym portalu Intune. Konta usługi Intune utworzone przed styczniem 2017 będą wymagać przeprowadzenia jednorazowej migracji, zanim funkcje te będą dostępne w systemie Azure. Harmonogram migracji nie został jeszcze ogłoszony, ale szczegółowe informacje zostaną udostępnione najszybciej, jak będzie to możliwe. Zdecydowanie zalecamy utworzenie konta w wersji próbnej w celu przetestowania nowego środowiska pracy w przypadku, gdy istniejące konto nie ma dostępu do podglądu.


## <a name="february-2017"></a>Luty 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Możliwość ograniczenia rejestracji urządzeń przenośnych <!--747600, 795782-->
Usługa Intune dodaje nowe ograniczenia rejestracji, które pozwalają kontrolować, które platformy urządzeń przenośnych mogą być rejestrowane. Usługa Intune dzieli platformy urządzeń przenośnych na iOS, macOS, Android, Windows i Windows Mobile.

* Ograniczanie rejestracji urządzeń przenośnych nie ogranicza rejestracji klientów komputerów stacjonarnych.  
* Tylko w przypadku systemu iOS i Android istnieje dodatkowa opcja blokowania rejestracji urządzeń, które są własnością osobistą.

Intune oznacza wszystkie nowe urządzenia jako osobiste, chyba że administrator IT oznaczy je jako własność firmową, zgodnie z opisem [w tym artykule](https://docs.microsoft.com/intune-classic/deploy-use/manage-corporate-owned-devices).

### <a name="view-all-actions-on-managed-devices---677150--"></a>Wyświetlanie wszystkich akcji na urządzeniach zarządzanych <!--677150-->
Nowy raport __Akcje urządzenia__ pokazuje, kto wykonał akcje zdalne, takie jak przywrócenie stanu fabrycznego na urządzeniach, a ponadto wyświetla stan takich akcji. Zobacz [Co to jest zarządzanie urządzeniami?](device-management.md).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Urządzenia niezarządzane mają dostęp do przypisanych aplikacji <!--664691-->
W ramach zmian wyglądu witryny internetowej Portal firmy użytkownicy systemów iOS i Android będą mogli instalować na swoich urządzeniach niezarządzanych aplikacje przypisane im jako „dostępne bez rejestracji”. Przy użyciu poświadczeń usługi Intune użytkownicy mogą zalogować się do witryny internetowej Portal firmy i wyświetlić listę przypisanych im aplikacji. Pakiety aplikacji oznaczonych jako „dostępne bez rejestracji” są udostępniane do pobrania za pośrednictwem witryny internetowej Portal firmy. Ta zmiana nie ma wpływu na aplikacje, które wymagają rejestracji na potrzeby instalacji, ponieważ użytkownicy, którzy zechcą zainstalować te aplikacje, zobaczą monit o zarejestrowanie ich urządzenia.

### <a name="custom-app-categories---748805--"></a>Niestandardowe kategorie aplikacji <!--748805-->
Możesz teraz tworzyć, edytować i przypisywać kategorie dla aplikacji dodawanych do usługi Intune. Obecnie kategorie można określać tylko w języku angielskim.
Zobacz [Jak dodać aplikację do usługi Intune](apps-add.md).

### <a name="display-device-categories---814654--"></a>Wyświetlanie kategorii urządzeń <!--814654-->
Kategorię urządzenia można teraz wyświetlić jako kolumnę na liście urządzeń. Można także edytować kategorię z poziomu sekcji właściwości w bloku właściwości urządzenia. Zobacz [Jak dodać aplikację do usługi Intune](apps-add.md).

### <a name="configure-windows-update-for-business-settings---776716--"></a>Konfigurowanie ustawień usługi Windows Update dla firm<!--776716-->

Windows jako usługa to nowy sposób udostępniania aktualizacji dla systemu Windows 10. Począwszy od systemu Windows 10, wszystkie nowe funkcjonalne i jakościowe aktualizacje będą obejmować zawartość wszystkich poprzednich aktualizacji. Oznacza to, że po zainstalowaniu najnowszej aktualizacji masz pewność, iż urządzenia systemu Windows 10 są całkowicie aktualne. W odróżnieniu od wcześniejszych wersji systemu Windows teraz musisz zainstalować całą aktualizację, a nie tylko jej część.

Za pomocą usługi Windows Update dla firm można uprościć zarządzanie aktualizacjami, dzięki czemu nie trzeba zatwierdzać poszczególnych aktualizacji dla grup urządzeń. Nadal możesz zarządzać ryzykiem w swoich środowiskach, konfigurując strategię wdrażania aktualizacji, dzięki czemu usługa Windows Update zagwarantuje zainstalowanie aktualizacji w odpowiednim czasie. Usługa Microsoft Intune zapewnia możliwość konfigurowania ustawień aktualizacji na urządzeniach oraz odroczenia instalacji aktualizacji. Usługa Intune nie przechowuje aktualizacji, a jedynie przypisanie zasad aktualizacji. W celu aktualizacji urządzenia uzyskują dostęp bezpośrednio do witryny Windows Update. Użyj usługi Intune do konfigurowania **pierścieni aktualizacji systemu Windows 10** i zarządzania nimi. Pierścień aktualizacji zawiera grupę ustawień, które konfigurują, kiedy i w jaki sposób aktualizacje systemu Windows 10 mają zostać zainstalowane. Aby uzyskać szczegółowe informacje, zobacz sekcję [Konfigurowanie ustawień usługi Windows Update dla firm](windows-update-for-business-configure.md).

## <a name="january-2017"></a>Styczeń 2017

### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--"></a>Przypisywanie aplikacji biznesowych niezależnie od tego, czy urządzenia są zarejestrowane <!--748823-->
Możesz teraz przypisywać użytkownikom aplikacje biznesowe ze sklepu niezależnie od tego, czy ich urządzenia są zarejestrowane w usłudze Intune. Jeśli urządzenie użytkownika nie jest zarejestrowane w usłudze Intune, aby ją zainstalować, użytkownik musi przejść do witryny sieci Web Portal firmy, a nie do aplikacji Portal firmy. Zobacz [Co to jest zarządzanie aplikacjami](app-management.md).

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Rozwiązywanie problemów związanych z brakiem aktywności urządzeń z systemem iOS lub z brakiem możliwości komunikacji pomiędzy nimi a konsolą administracyjną
Gdy urządzenia użytkowników utracą połączenie z usługą Intune, można wykonać w odniesieniu do nich nowe kroki mające na celu rozwiązanie problemów w celu przywrócenia dostępu do zasobów firmy. Zobacz temat [Urządzenia są nieaktywne lub nie jest możliwe nawiązanie łączności między nimi a konsolą administracyjną](enrollment-troubleshoot.md#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="december-2016-initial-release"></a>Grudzień 2016 (wersja początkowa)

### <a name="telecom-expense-management-integration-in-azure-portal--747605--"></a>Integracja zarządzania kosztami telekomunikacyjnymi w witrynie Azure Portal<!--747605-->
Obecnie rozpoczynamy pracę nad wersją zapoznawczą integracji z usługami zarządzania kosztami telekomunikacyjnymi innych firm w witrynie Azure Portal. Usługa Intune może być używana do wymuszania limitów użycia danych w kraju i w roamingu. Te operacje integracji rozpoczynamy od współpracy z firmą [Saaswedo](http://www.saaswedo.com). Aby włączyć tę funkcję w dzierżawie w wersji próbnej, [skontaktuj się z pomocą techniczną firmy Microsoft](https://docs.microsoft.com/intune-classic/troubleshoot/get-support).

- Wdrażanie aplikacji ze sklepu na urządzeniach z systemami iOS, Android i Windows i zarządzanie nimi
- Wdrażanie aplikacji biznesowych (LOB, line of business) na urządzeniach z systemami iOS, Android i Windows i zarządzanie nimi
- Wdrażanie aplikacji kupionych w ramach zakupów zbiorczych na urządzeniach z systemami iOS, Android i Windows i zarządzanie nimi
- Wdrażanie aplikacji sieci Web na urządzeniach z systemami iOS, Android i Windows i zarządzanie nimi
- Profile konfiguracji aplikacji zarządzanych w systemie iOS
- Konfigurowanie zasad ochrony aplikacji i wdrażanie aplikacji biznesowych na urządzeniach niezarejestrowanych w usłudze Intune
- Profile sieci VPN, sieci VPN dla aplikacji, sieci Wi-Fi, poczta e-mail i profile certyfikatów
- Zasady zgodności
- Dostęp warunkowy do usługi Azure AD
- Dostęp warunkowy do lokalnego programu Exchange
- Rejestrowanie urządzeń
- Kontrola dostępu oparta na rolach

## <a name="deprecated-features-in-the-azure-portal"></a>Funkcje przestarzałe w portalu Azure

### <a name="support-for-row-by-row-review-of-hardware-identifiers"></a>Obsługa przeglądu wiersz po wierszu identyfikatorów sprzętu
Portal Azure nie obsługuje przeglądu wiersz po wierszu identyfikatorów sprzętu dla numerów IMEI i numerów seryjnych firmy Apple. W klasycznej konsoli usługi Intune można zaimportować szczegółowe informacje z pliku CSV i zastąpić nimi istniejące szczegółowe informacje dotyczące indywidualnych identyfikatorów sprzętu. Portal Azure udostępnia pojedynczą, zoptymalizowaną opcję, która automatycznie zastępuje szczegóły dotyczące wszystkich identyfikatorów sprzętu lub ignoruje nowe szczegóły dotyczące istniejących identyfikatorów.

#### <a name="how-this-affects-you"></a>Jaki to ma wpływ na Ciebie
W portalu Azure nie będziesz mieć możliwości ustalenia wiersz po wierszu, które urządzenia z numerem InternationaI Mobile Equipment (IMEI) należy zaktualizować. W klasycznej konsoli usługi Intune ta funkcja będzie nadal obsługiwana.

#### <a name="how-to-get-ready-for-this-change"></a>Jak przygotować się do tej zmiany
Ponieważ informujemy o tym z wyprzedzeniem, to jeśli ta zmiana dotyczy Ciebie, masz możliwość zwrócenia na nią uwagi administratorom. Ta zmiana zbiega się z przeniesieniem do portalu Azure przewidywanym w pierwszej połowie 2017 roku.


### <a name="support-for-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Obsługa domyślnych profilów rejestracji urządzeń firmowych usługi Apple DEP
Portal Azure nie obsługuje „domyślnego” profilu rejestracji urządzeń firmowych w odniesieniu do numerów seryjnych urządzeń programu Apple DEP (Device Enrollment Program) Ta dostępna w klasycznej konsoli usługi Intune funkcja przestaje być obsługiwana, aby zapobiec przypadkowo przypisanym profilom. W portalu Azure numery seryjne synchronizowane z kontem usługi Apple DEP nie będą początkowo miały przypisanego profilu rejestracji urządzeń firmowych.

#### <a name="how-this-affects-you"></a>Jaki to ma wpływ na Ciebie
W portalu Azure nie będziesz mieć możliwości ustawienia domyślnych zasad profilu wszystkich urządzeń firmy Apple. W klasycznej konsoli usługi Intune ta funkcja będzie nadal obsługiwana.

#### <a name="how-to-get-ready-for-this-change"></a>Jak przygotować się do tej zmiany
Ponieważ informujemy o tym z wyprzedzeniem, to jeśli ta zmiana dotyczy Ciebie, masz możliwość zwrócenia na nią uwagi administratorom. Ta zmiana zbiega się z przeniesieniem do portalu Azure przewidywanym w pierwszej połowie 2017 roku.

### <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).
