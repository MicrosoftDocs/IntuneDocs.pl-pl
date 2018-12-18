---
title: Wczesna wersja — Microsoft Intune
titlesuffix: ''
description: Wczesna wersja usługi Microsoft Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/3/2018
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
ms.openlocfilehash: 35298713738c666ca19d57e647412729a85bbc4a
ms.sourcegitcommit: 5058dbfb0e224207dd4e7ca49712c6ad3434c83c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2018
ms.locfileid: "53112837"
---
# <a name="the-early-edition-for-microsoft-intune---december-2018"></a>Wczesna wersja usługi Microsoft Intune — grudzień 2018

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

<!-- 1812 start -->

### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Wdrażanie aplikacji APP-WE dla systemu Android Enterprise <!-- 1171203 -->
Dla urządzeń z systemem Android w scenariuszu wdrażania zasad ochrony aplikacji bez rejestracji (APP-WE) będzie można używać zarządzanego sklepu Google Play w celu wdrażania aplikacji ze sklepu i aplikacji biznesowych dla użytkowników. Mówiąc ściślej, dział IT może udostępnić użytkownikom końcowym środowisko instalacji i wykazu aplikacji, które nie wymaga już od użytkowników końcowych rozluźnienia stanu zabezpieczeń urządzeń przez umożliwienie instalacji z nieznanych źródeł. Ponadto ten scenariusz wdrażania zapewni ulepszone środowisko pracy użytkownika końcowego.

### <a name="new-options-to-automatically-connect-and-persist-rules-when-using-dns-settings-on-windows-10-and-later-devices----1333665-2999078---"></a>Nowe opcje automatycznego łączenia i utrzymywania reguł w przypadku korzystania z ustawień systemu DNS w systemie Windows 10 lub nowszym <!-- 1333665, 2999078 -->
Na urządzeniach z systemem Windows 10 lub nowszym będzie można utworzyć profil konfiguracji sieci VPN z listą serwerów DNS, która pozwala na rozpoznawanie domen, np. contoso.com. Obejmuje to nowe ustawienia funkcji rozpoznawania nazw (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > wybierz platformę **Windows 10 i nowsze** > wybierz typ profilu **VPN** > **Ustawienia DNS** >**Dodaj**): 

- **Połącz automatycznie**: po wybraniu pozycji **Włączone** urządzenie automatycznie łączy się z siecią VPN po nawiązaniu kontaktu z wprowadzoną domeną, np. contoso.com.
- **Trwałe**: domyślnie wszystkie reguły tabeli zasad rozpoznawania nazw (NRPT) są aktywne reguły tak długo, jak długo urządzenie jest połączone za pomocą tego profilu sieci VPN. Gdy to ustawienie jest **włączone** dla reguły tabeli NRPT, reguła pozostaje aktywna na urządzeniu, nawet wtedy gdy połączenie sieci VPN zostanie rozłączone lub gdy profil sieci VPN zostanie usunięty. Reguła pozostaje aktywna do momentu ręcznego usunięcia, co można zrobić w programie PowerShell.

Aktualną listę ustawień można znaleźć w temacie [Windows 10 VPN settings](vpn-settings-windows-10.md) (Ustawienia sieci VPN w systemie Windows 10). 

### <a name="use-smime-to-encrypt-and-sign-a-users-multiple-devices-----1333642-eeready---"></a>Używanie szyfrowania S/MIME do szyfrowania i rejestrowania wielu urządzeń użytkownika <!-- 1333642 eeready -->
Szyfrowanie poczty e-mail za pomocą protokołu S/MIME z użyciem profilu nowo zaimportowanego certyfikatu będzie teraz obsługiwane (**Konfiguracja urządzenia** > **Profil** > **Utwórz profil** > wybierz platformę > typ profilu **Zaimportowany certyfikat PKCS**). W usłudze Intune można importować certyfikaty w formacie PFX. Usługa Intune może następnie dostarczać te same certyfikaty do wielu urządzeń zarejestrowanych przez jednego użytkownika. Obejmuje to również:

- Profil natywnej poczty e-mail systemu iOS obsługuje włączanie szyfrowania S/MIME przy użyciu importowanych certyfikatów w formacie PFX.
- Natywna aplikacja poczty na urządzeniach z systemem Windows Phone 10 automatycznie używa certyfikatu szyfrowania S/MIME.
- Certyfikaty prywatne mogą być dostarczane na wielu platformach. Jednak nie wszystkie aplikacje poczty e-mail obsługują szyfrowanie S/MIME.
- Na innych platformach może być konieczne ręczne skonfigurowanie aplikacji poczty, aby włączyć szyfrowanie S/MIME.  
- Aplikacje poczty e-mail, które obsługuje szyfrowanie S/MIME może obsługiwać pobieranie certyfikatów dla protokołu S/MIME szyfrowania wiadomości e-mail w sposób, który nie obsługuje zarządzania urządzeniami Przenośnymi, takie jak odczytywanie ich z magazynu certyfikatów ich wydawcy.

Obsługiwane na: Windows, Windows Phone 10, macOS, iOS, Android

### <a name="help-and-support-page-in-the-windows-company-portal-app----1488939---"></a>Strona pomocy i obsługi technicznej w aplikacji Portal w systemie Windows <!-- 1488939 -->
Do aplikacji Portal firmy w systemie Windows zostanie dodana nowa strona. Na stronie pomocy i obsługi technicznej będzie można znaleźć informacje kontaktowe działu pomocy technicznej. Ponadto użytkownicy końcowi będą mogli wysyłać dzienniki aplikacji Portal firmy, jeśli napotkają problemy. Strona będzie również zawierać sekcję często zadawanych pytań, aby pomóc użytkownikom końcowym.

### <a name="use-trusted-network-detection-for-vpn-profiles-on-windows-10-devices----1500165---"></a>Korzystanie z wykrywania zaufanych sieci na użytek profilów sieci VPN na urządzeniach z systemem Windows 10 <!-- 1500165 -->
W przypadku korzystania z wykrywania zaufanych sieci będzie można wyłączyć automatyczne tworzenie połączenia sieci VPN w profilach sieci VPN, gdy użytkownik będzie już w zaufanej sieci. Będziesz mieć możliwość dodawania sufiksów DNS w celu włączenia wykrywania zaufanych sieci na urządzeniach z systemem Windows 10 i nowszych (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** jako platforma > **VPN** jako typ profilu).
Aktualną listę ustawień sieci VPN można znaleźć w temacie [Windows 10 VPN settings](vpn-settings-windows-10.md) (Ustawienia sieci VPN w systemie Windows 10).

### <a name="the-intune-app-sdk-will-support-256-bit-encryption-keys----1832174---"></a>Zestaw SDK aplikacji usługi Intune będzie obsługiwać 256-bitowe klucze szyfrowania <!-- 1832174 -->
Zestaw SDK aplikacji usługi Intune dla systemu iOS będzie używać 256-bitowych kluczy szyfrowania po włączeniu szyfrowania przy użyciu zasad ochrony aplikacji. Zestaw SDK będzie nadal obsługiwać 128-bitowe klucze w celu zachowania zgodności z zawartością i aplikacjami, które używają starszych wersji zestawu SDK.

### <a name="enabled-shared-pc-settings-in-intune-profile----1907917---"></a>Włączone ustawienia komputera udostępnionego w profilu usługi Intune <!-- 1907917 -->
Obecnie można konfigurować ustawienia komputera udostępnionego na urządzeniach z systemem Windows 10 Desktop przy użyciu niestandardowego ustawienia OMA-URI. Zostanie dodany nowy profil służący do konfigurowania ustawień komputera udostępnionego (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** > **Urządzenie udostępnione wielu użytkownikom**).
Dotyczy: system Windows 10 lub nowsze oraz system Windows Holographic for Business

### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359---"></a>Zasady usługi Intune aktualizują metodę uwierzytelniania i instalację aplikacji Portal firmy <!-- 1927359 -->
Usługa Intune nie będzie już obsługiwać aplikacji Portal firmy po jej zainstalowaniu ze sklepu z aplikacjami na niektórych urządzeniach. Ta zmiana ma zastosowanie tylko w sytuacji, w której uwierzytelnianie jest przeprowadzane przy użyciu asystenta ustawień firmy Apple podczas rejestracji. Ta zmiana dotyczy tylko urządzeń z systemem iOS zarejestrowanych przy użyciu następujących rozwiązań:  
* Apple Configurator
* Apple Business Manager
* Apple School Manager
* Apple Device Enrollment Program (DEP)

Jeśli użytkownicy zainstalują aplikację Portal firmy ze sklepu z aplikacjami, a następnie podejmą próbę zarejestrowania urządzeń przy jej użyciu, wystąpi błąd. Oczekuje się, że te urządzenia będą używać aplikacji Portal firmy tylko w sytuacji, gdy nastąpi automatyczne wypchnięcie przez usługę Intune podczas rejestracji. Profile rejestracji w usłudze Intune w witrynie Azure Portal zostaną zaktualizowane tak, aby określić sposób uwierzytelniania urządzeń oraz wskazać, czy otrzymują aplikację Portal firmy. Jeśli chcesz, aby użytkownicy urządzenia DEP mieli aplikację Portal firmy, musisz określić swoje preferencje w profilu rejestracji. Ponadto ekran **Identyfikowanie urządzenia** w aplikacji Portal firmy wkrótce będzie przestarzały.  
Aby zainstalować Portal firmy na już zarejestrowanych urządzeniach objętych programem DEP, należy przejść do usługi Intune > Aplikacje klienckie i wypchnąć ją jako aplikację zarządzaną przy użyciu zasad konfiguracji aplikacji. Szczegółowe informacje na temat tych czynności zostaną przedstawione w przyszłej dokumentacji.

### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379---"></a>Użytkownicy inni niż administratorzy mogą włączyć funkcję BitLocker na urządzeniach z systemem Windows 10 dołączonych do usługi Azure AD<!-- 2147379 -->
Włączenie ustawień funkcji BitLocker na urządzeniach z systemem Windows 10 (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** jako platforma > **Endpoint Protection** jako typ profilu > **Szyfrowanie systemu Windows**) oznacza dodanie ustawień funkcji BitLocker. Ta aktualizacja obejmuje nowe ustawienie funkcji BitLocker, które zezwala użytkownikom standardowym (innym niż administratorzy) na włączanie szyfrowania. Aby wyświetlić bieżące ustawienia, zobacz [Endpoint protection settings for Windows 10](endpoint-protection-windows-10.md#windows-encryption) (Ustawienia programu Endpoint Protection dla systemu Windows 10).

### <a name="intune-app-pin----2298397---"></a>Numer PIN aplikacji usługi Intune <!-- 2298397 -->
Jako administrator IT będziesz mieć możliwość skonfigurowania liczby dni, przez które użytkownik końcowy może czekać, aż będzie musiał zmienić numer PIN aplikacji usługi Intune. Nowe ustawienie będzie dostępne w witrynie Azure Portal w obszarze **Intune** > **Aplikacje klienckie** > **zasad ochrony aplikacji** > **Utwórz zasady** > **Ustawienia** > **Wymagania dotyczące dostępu**. Ta funkcja będzie dostępna na urządzeniach z systemem Android i iOS. To ustawienie obsługuje dodatnie liczby całkowite.

### <a name="new-windows-10-update-settings----2626030-2512994---"></a>Nowe ustawienia aktualizacji systemu Windows 10 <!-- 2626030 2512994 -->
W przypadku pierścieni aktualizacji systemu Windows 10 będziesz mieć możliwość:
- przywracania oryginalnych ustawień automatycznych aktualizacji na maszynie z systemem Windows 10 z *aktualizacją z października 2018 r.*
- konfigurowania nowego ustawienia aktualizacji oprogramowania, które umożliwia zezwalanie użytkownikom na wstrzymywanie instalacji aktualizacji lub blokowanie tej możliwości z obszaru *Ustawienia* ich komputerów. 



### <a name="ios-email-profiles-can-use-smime-signing-and-encryption----2662949---"></a>Profile poczty e-mail w systemie iOS mogą używać szyfrowania i podpisywania protokołu S/MIME <!-- 2662949 -->
Będziesz mieć możliwość tworzenia profilu poczty e-mail z różnymi ustawieniami. Są to m.in. ustawienia protokołu S/MIME, których można używać do podpisywania i szyfrowania wiadomości e-mail na urządzeniach z systemem iOS (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > wybierz platformę **iOS** > wybierz typ profilu **E-mail**).

Lista bieżących ustawień znajduje się w obszarze [ustawień konfiguracji poczty e-mail systemu iOS](email-settings-ios.md).

### <a name="skip-more-setup-assistant-screens-on-an-ios-dep-device----2687509---"></a>Pomijanie większej liczby ekranów Asystenta ustawień na urządzeniu DEP z systemem iOS <!-- 2687509 -->
Oprócz ekranów, które obecnie możesz pominąć, będziesz mieć możliwość skonfigurowania urządzeń z systemem iOS objętych programem DEP tak, aby następujące ekrany Asystenta ustawień były pomijane podczas rejestracji urządzenia przez użytkownika: Ton wyświetlacza, Prywatność, Migracja systemu Android, Przycisk Strona główna, iMessage i FaceTime, Przechodzenie do usługi, Migracja urządzenia Watch, Wygląd, Czas korzystania z urządzenia, Aktualizacja oprogramowania, Instalator SIM.
Aby wybrać ekrany do pominięcia, przejdź kolejno do pozycji **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > wybierz token > **Profile** > wybierz profil > **Właściwości** > **Dostosowywanie Asystenta ustawień** > wybierz pozycję **Ukryj**  dla ekranów do pominięcia > **OK**.

### <a name="some-bitlocker-settings-support-windows-10-pro-edition---2727036---"></a>Niektóre ustawienia funkcji BitLocker obsługują wersję systemu Windows 10 Pro<!-- 2727036 -->
Będzie można utworzyć profil konfiguracji, który definiuje ustawienia programu Endpoint Protection na urządzeniach z systemem Windows 10, w tym funkcji BitLocker. Spowoduje to dodanie obsługi systemu Windows 10 Professional dla niektórych ustawień funkcji BitLocker. Aby wyświetlić bieżące ustawienia wersji systemu Windows 10, zobacz [Endpoint protection settings for Windows 10](endpoint-protection-windows-10.md#windows-encryption) (Ustawienia programu Endpoint Protection dla systemu Windows 10).
Usługa Intune będzie udostępniać dodatkowe pola raportów dotyczących urządzeń, takie jak na przykład producent systemu Android, model i wersja poprawki zabezpieczeń, a także model z systemem iOS. W usłudze Intune te pola będą dostępne po wybraniu opcji **Aplikacje klienckie** > **Stan ochrony aplikacji** i wybraniu pozycji **Raport ochrony aplikacji: iOS, Android**. Ponadto te parametry będą pomocne w przypadku konfigurowania listy **dozwolonych** dla producenta urządzenia (Android), listy **dozwolonych** dla modelu urządzenia (Android i iOS) oraz ustawienia minimalnej wersji poprawki zabezpieczeń systemu Android. 

### <a name="intune-device-reporting-fields----2748738---"></a>Pola raportów dotyczących urządzeń w usłudze Intune <!-- 2748738 -->
Usługa Intune będzie udostępniać dodatkowe pola raportów dotyczących urządzeń, takie jak na przykład producent systemu Android, model i wersja poprawki zabezpieczeń, a także model z systemem iOS. W usłudze Intune te pola będą dostępne po wybraniu opcji **Aplikacje klienckie** > **Stan ochrony aplikacji** i wybraniu pozycji **Raport ochrony aplikacji: iOS, Android**. Ponadto te parametry będą pomocne w przypadku konfigurowania listy **dozwolonych** dla producenta urządzenia (Android), listy **dozwolonych** dla modelu urządzenia (Android i iOS) oraz ustawienia minimalnej wersji poprawki zabezpieczeń systemu Android. 

### <a name="shared-device-configuration-is-renamed-to-lock-screen-message-for-ios-devices-in-the-azure-portal----2809362---"></a>Nazwa konfiguracji urządzenia udostępnionego została zmieniona na Komunikat ekranu blokady dla urządzeń z systemem iOS w witrynie Azure Portal <!-- 2809362 -->
W przypadku tworzenia profilu konfiguracji dla urządzeń z systemem iOS będziesz mieć możliwość dodawania ustawień obszaru **Konfiguracja urządzenia udostępnianego** w celu wyświetlania określonego tekstu na ekranie blokady. Obejmuje to następujące zmiany: 

- Ustawienia **Konfiguracja urządzenia udostępnianego** w witrynie Azure Portal są zmieniane na „Komunikat ekranu blokady (tylko tryb nadzorowany)” (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > wybierz platformę **iOS** > wybierz typ profilu **Funkcje urządzenia** > **Komunikat ekranu blokady**).
- Podczas dodawania wiadomości ekranu blokady można wstawić numer seryjny, nazwę urządzenia lub inną wartość specyficzną dla urządzenia w obszarze **informacji dotyczących tagu zasobu**. Na przykład można wprowadzić wartości `Device name: {{device name}}` lub `Serial number is {{serial number}}`, używając nawiasów klamrowych. Listę dostępnych tokenów do użycia można znaleźć w sekcje [iOS tokens](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) (Tokeny systemu iOS).

Listę aktualnych ustawień można znaleźć w temacie [Settings to display messages on the lock screen](shared-device-settings-ios.md) (Ustawienia służące do wyświetlania komunikatów na ekranie blokady).

### <a name="more-detailed-enrollment-restriction-failure-messaging----3111564--"></a>Bardziej szczegółowe komunikaty dotyczące błędów ograniczeń rejestracji <!-- 3111564-->
Bardziej szczegółowe komunikaty o błędach będą dostępne, gdy ograniczenia rejestracji nie zostaną spełnione. Aby wyświetlić te komunikaty, przejdź do obszaru **Intune** > **Rozwiązywanie problemów** i zapoznaj się z tabelą błędów rejestracji.

### <a name="new-notification-hints-and-keyguard-settings-to-android-enterprise-device-owner-devices----3201839-3201843---"></a>Nowe ustawienia powiadomień, wskazówek i funkcji blokowania klawiatury na urządzeniach właściciela urządzenia z systemem Android Enterprise<!-- 3201839 3201843 -->
Ta aktualizacja obejmuje kilka nowych funkcji dotyczących urządzeń z systemem Android Enterprise uruchamianych jako właściciel urządzenia. Aby korzystać z tych funkcji, przejdź do pozycji **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > w polu **Platforma** wybierz wartość **Android Enterprise** > w polu **Typ profilu** wybierz wartość **Tylko właściciel urządzenia** > **Ograniczenia urządzenia**.
Nowe funkcje obejmują: 
- Wyłączanie wyświetlania powiadomień systemowych, w tym połączeń przychodzących, alertów systemowych, błędy systemu i innych
- Sugerowanie pomijania samouczków i wskazówek dotyczących aplikacji otwieranych po raz pierwszy
- Wyłączanie zaawansowanych ustawień funkcji blokady klawiatury, takich jak aparat, powiadomienia, odblokowywanie odciskiem palca i inne

Aby zapoznać się z bieżącymi ustawieniami, przejdź do tematu [Android Enterprise device restriction settings](device-restrictions-android-for-work.md) (Ustawienia ograniczeń urządzeń z systemem Android Enterprise).

### <a name="android-enterprise-device-owner-devices-can-use-always-on-vpn-connections----3202194---"></a>Urządzenia właściciela urządzenia z systemem Android Enterprise mogą używać zawsze włączonych połączeń VPN <!-- 3202194 -->
Dzięki tej aktualizacji będziesz mieć możliwość używania zawsze włączonych połączeń sieci VPN na urządzeniach właściciela urządzenia z systemem Android Enterprise. Zawsze włączone połączenia sieci VPN pozostają aktywne lub są natychmiast przywracane, gdy użytkownik odblokuje urządzenie, gdy urządzenie uruchomi się ponownie lub gdy zmieni się sieć bezprzewodowa. Połączenie można również przenieść do trybu „blokady”, który powoduje zablokowanie całego ruchu sieciowego do momentu uaktywnienia połączenia sieci VPN.
Zawsze włączoną sieć VPN możesz włączyć za pomocą ustawień **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Android Enterprise** jako platforma > **Ograniczenia dotyczące urządzeń** dla opcji Tylko właściciel urządzenia > **Łączność**. Aby zapoznać się z bieżącymi ustawieniami, przejdź do tematu [Android Enterprise device restriction settings](device-restrictions-android-for-work.md) (Ustawienia ograniczeń urządzeń z systemem Android Enterprise).

### <a name="new-setting-to-end-processes-in-task-manager-on-windows-10-devices----3285177---"></a>Nowe ustawienie służące do kończenia procesów w Menedżerze zadań na urządzeniach z systemem Windows 10 <!-- 3285177 --> 
Ta aktualizacja obejmuje nowe ustawienie służące do kończenia procesów w Menedżerze zadań na urządzeniach z systemem Windows 10. Używając profilu konfiguracji urządzenia (ustawienia w obszarze **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > w polu **Platforma** wybierz wartość **Windows 10** > w polu **Typ profilu** wybierz wartość **Ograniczenia dotyczące urządzeń** > **Ogólne**), możesz zezwolić na to ustawienie lub je zablokować.
Aby zapoznać się z bieżącymi ustawieniami, przejdź do tematu [Windows 10 device restriction settings](device-restrictions-windows-10.md) (Ustawienia ograniczeń urządzeń z systemem Windows 10).
Dotyczy: System Windows 10 lub nowszy

### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Szablony administracyjne są dostępne w publicznej wersji zapoznawczej i zostały przeniesione do własnego profilu konfiguracji <!-- 3322847 -->
Szablony administracyjne w usłudze Intune (**Konfiguracja urządzenia** > **Szablony administracyjne**) są obecnie dostępne w prywatnej wersji zapoznawczej. Dzięki tej aktualizacji szablony administracyjne obejmują około 300 ustawień, którymi można zarządzać w usłudze Intune. Wcześniej ustawienia te istniały tylko w edytorze zasad grupy.
Szablony administracyjne są dostępne w publicznej wersji zapoznawczej Szablony administracyjne są przenoszone z obszaru **Konfiguracja urządzenia** > **Szablony administracyjne** do obszaru **Konfiguracja urządzenia** > **Profile** >**Utwórz profil** > w polu **Platforma** wybierz  **Windows 10 i nowsze**, w polu **Typ profilu** wybierz **Szablony administracyjne**.
Włączone raportowanie Dotyczy: System Windows 10 lub nowszy


<!-- 1810 start -->

### <a name="use-microsoft-recommended-settings-with-security-baselines----2055484---"></a>Używanie ustawień zalecanych przez firmę Microsoft z punktami odniesienia zabezpieczeń <!-- 2055484 -->
Usługa Intune umożliwia integrację z innymi usługami koncentrującymi się na zabezpieczeniach, w tym z usługą Windows Defender ATP i usługą Office 365 ATP. Klienci pytają o typową strategię i spójny zestaw kompleksowych przepływów pracy zabezpieczeń w usługach Microsoft 365. Naszym celem jest dopasowanie strategii w celu utworzenia rozwiązań, które łączą operacje zabezpieczeń i typowe zadania administratora. W usłudze Intune staramy się osiągnąć ten cel, publikując zestaw „punktów odniesienia zabezpieczeń” zalecanych przez firmę Microsoft (**Intune** > **Punkty odniesienia zabezpieczeń**).  Administrator będzie mógł tworzyć zasady zabezpieczeń bezpośrednio z tych punktów odniesienia, a następnie wdrożyć je dla użytkowników. Można również dostosować rekomendacje dotyczące najlepszych rozwiązań do potrzeb swojej organizacji. Usługa Intune zapewnia, że urządzenia pozostają w zgodności z tymi punktami odniesienia, i powiadamia administratorów użytkowników lub urządzeń, które nie są zgodne.

### <a name="scope-tags-for-apps---1081941---"></a>Tagi zakresu dla aplikacji <!--1081941 -->
Będzie możliwe tworzenie tagów zakresu w celu ograniczenia dostępu do zasobów usługi Intune. Dodaj tag zakresu do przypisania roli, a następnie dodaj tag zakresu do profilu konfiguracji. Rola będzie miała wtedy dostęp tylko do zasobów z profilami konfiguracji ze zgodnymi tagami zakresu (lub bez tagów zakresu).
Aby utworzyć tag zakresu, wybierz pozycję **Role usługi Intune** > **Zakres (tagi)** > **Utwórz**.
Aby dodać tag zakresu do przypisania roli, wybierz pozycję **Role usługi Intune** > **Wszystkie role** > **Menedżer zasad i profilów** > **Przypisania** > **Zakres (tagi)**.
Aby dodać tag zakresu do profilu konfiguracji, wybierz pozycję **Konfiguracja urządzenia** > **Profile** > wybierz profil > **Właściwości** > **Zakres (tagi)**.

### <a name="tenant-health-dashboard----1124854---"></a>Pulpit nawigacyjny kondycji dzierżawy <!-- 1124854 -->
Na stronie Stan dzierżawy w usłudze Intune znajdziesz informacje o stanie dzierżawy w jednym miejscu. Strona jest podzielona na 4 sekcje:  
- **Szczegóły dzierżawy**: zawiera informacje, takie jak urząd zarządzania urządzeniami przenośnymi, łączna liczba zarejestrowanych urządzeń w dzierżawie i liczba licencji. Ta sekcja zawiera także bieżącą wersję usługi dla Twojej dzierżawy.
- **Stan łącznika**: zawiera informacje dla skonfigurowanych łączników, takich jak program VPP firmy Apple, Sklep Windows dla Firm i łączniki certyfikatów. Na podstawie ich bieżącego stanu łączniki są oznaczane flagami *Dobra kondycja*, *Ostrzeżenie* lub *Zła kondycja*.
- **Kondycja usługi Intune**: zawiera aktywne zdarzenia lub awarie dotyczące Twojej dzierżawy. Informacje przedstawione w tej sekcji są pobierane bezpośrednio z Centrum wiadomości usługi Office ([https://portal.office.com](https://portal.office.com)).
- **Wiadomości w usłudze Intune**: zawiera aktywne wiadomości dla dzierżawy obejmujące takie elementy jak powiadomienia o tym, że dzierżawa otrzymała najnowsze funkcje usługi Intune. Informacje przedstawione w tej sekcji są pobierane bezpośrednio z Centrum wiadomości usługi Office ([https://portal.office.com](https://portal.office.com)).


### <a name="deployed-wip-policies-without-user-enrollment----1434452---"></a>Wdrożone zasady funkcji WIP bez rejestracji użytkownika <!-- 1434452 -->
Zasady funkcji Windows Information Protection (WIP) będzie można wdrożyć bez konieczności rejestracji urządzeń z systemem Windows 10 przez użytkowników zarządzania urządzeniami przenośnymi. Ta konfiguracja pozwala firmom na ochronę firmowych dokumentów na podstawie konfiguracji funkcji WIP, jednocześnie umożliwiając użytkownikom zarządzanie własnymi urządzeniami z systemem Windows. Gdy dokumenty są chronione za pomocą zasad funkcji WIP, chronione dane mogą być selektywnie czyszczone przez administratora usługi Intune. Wybierając użytkownika i urządzenie oraz wysyłając żądanie czyszczenia, wszystkie dane chronione za pomocą zasad funkcji WIP staną się bezużyteczne. Z usługi Intune w witrynie Azure Portal wybierz pozycję **Aplikacja mobilna** > **Selektywne czyszczenie aplikacji**.


<!-- 1809 start -->  

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Ustawienia zasad ochrony aplikacji dla danych internetowych <!-- 2662995 -->
Ustawienia zasad ochrony aplikacji dla zawartości internetowej na urządzeniach z systemami Android i iOS zostaną zaktualizowane w celu ulepszenia obsługi linków internetowych http i https, a także przesyłania danych za pośrednictwem linków uniwersalnych systemu iOS i linków między aplikacjami systemu Android.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Token VPP firmy Apple używany przez inne rozwiązanie MDM <!-- 1488946 -->
Usługa Intune wykryje i wyświetli szczegółowe informacje, jeśli token programu VPP (Volume Purchase Program) jest używany zarówno przez usługę Intune, jak i inne rozwiązanie MDM.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Wycofane urządzenia na pulpicie nawigacyjnym zgodności urządzeń <!-- 1981119 -->
W ramach przyszłej aktualizacji wycofane urządzenia zostaną usunięte z pulpitu nawigacyjnego zgodności urządzeń. Spowoduje to zmianę liczb dotyczących zgodności.


### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Zmiana w procesie aktualizacji łączników lokalnych <!-- 2277554 -->
Na podstawie opinii klientów zmienimy sposób aktualizacji łączników lokalnych. Po początkowej instalacji łącznika lokalnego aktualizacje będą wykonywane automatycznie. Ta zmiana rozpocznie się od nowego łącznika certyfikatów PFX usługi Microsoft Intune, a następnie będzie wdrażana dla innych typów łączników lokalnych. 

<!-- 1807 start -->

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Sprawdzanie zgodności w programie Configuration Manager <!-- 2192052 -->
Przyszła aktualizacja będzie zawierać nowe ustawienie zgodności programu System Center Configuration Manager (**Zgodność urządzeń** > **Zasady** > **Tworzenie zasad** > **System Windows 10**). Program Configuration Manager wysyła sygnały zgodności do usługi Intune. Przy użyciu ustawienia usługi Intune można wymagać, aby wszystkie sygnały programu Configuration Manager zwracały stan „zgodne”.

Na przykład można wymagać, aby na urządzeniach były zainstalowane wszystkie aktualizacje oprogramowania. W programie Configuration Manager to wymaganie ma stan „Zainstalowano”. Jeśli jakiekolwiek programy na urządzeniu mają nieznany stan, to urządzenie będzie niezgodne w usłudze Intune.

Dotyczy: system Windows 10 lub nowszy



## <a name="notices"></a>Uwagi

Aktualnie nie ma aktywnych powiadomień.

### <a name="see-also"></a>Zobacz też
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).



