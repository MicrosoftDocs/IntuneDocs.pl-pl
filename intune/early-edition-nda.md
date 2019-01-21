---
title: Wczesna wersja — Microsoft Intune
titlesuffix: ''
description: Wczesna wersja usługi Microsoft Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/09/2019
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
ms.openlocfilehash: 0efc84da6a9efb594600b9ca33aa5eb7622c8101
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203437"
---
# <a name="the-early-edition-for-microsoft-intune---january-2019"></a>Wczesna wersja usługi Microsoft Intune — styczeń 2019

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

<!-- 1901 start -->

### <a name="android-enterprise-apps----1352553----"></a>Aplikacje systemu Android Enterprise <!-- 1352553  -->
Za pomocą usługi Microsoft Intune będzie można usuwać aplikacje zarządzane ze sklepu Google Play. Aby usunąć aplikację zarządzaną ze sklepu Google Play, konieczne będzie otwarcie usługi Microsoft Intune w witrynie Azure Portal i wybranie pozycji **Aplikacje klienckie** > **Aplikacje**. Na liście aplikacji będzie trzeba wybrać wielokropek (...) po prawej stronie aplikacji zarządzanej ze sklepu Google Play, a następnie wybrać pozycję **Usuń** z wyświetlonej listy poleceń. Po usunięciu aplikacji zarządzanej ze sklepu Google Play z listy aplikacji ta aplikacja zarządzana stanie się automatycznie aplikacją niezatwierdzoną.

### <a name="managed-google-play-app-type----1352580---"></a>Typ aplikacji zarządzanej ze sklepu Google Play <!-- 1352580 -->
Dzięki zastosowaniu typów aplikacji **zarządzanych ze sklepu Google Play** będzie można wybiórczo dodawać [aplikacje zarządzane ze sklepu Google Play](https://play.google.com/work/search?q=microsoft&c=apps) do usługi Intune. Administratorzy usługi Intune będą mogli przeglądać, wyszukiwać, zatwierdzać, synchronizować i przypisywać zatwierdzone aplikacje zarządzane ze sklepu Google Play z poziomu usługi Intune. Nie będzie już konieczne przechodzenie do zarządzanej konsoli Google Play i dokonywanie ponownego uwierzytelniania. W usłudze Intune wystarczy wybrać pozycję **Aplikacje klienckie** > **Aplikacje** > **Dodaj**. Natomiast na liście **Typ aplikacji** będzie trzeba wybrać pozycję **Zarządzany sklep Google Play**.

### <a name="preview-of-support-for-android-corporate-owned-fully-managed-devices----1574342----"></a>Obsługa należących do firmy, w pełni zarządzanych urządzeń z systemem Android — wersja zapoznawcza <!-- 1574342  -->
Usługa Intune będzie obsługiwać w pełni zarządzane, należące do firmy urządzenia z systemem Android w scenariuszu „właściciel urządzenia”, w którym urządzenia są ściśle zarządzane przez dział IT i są powiązane z poszczególnymi użytkownikami. Pozwala to administratorom na zarządzanie całym urządzeniem, wymuszanie rozszerzonej gamy opcji kontroli zasad niedostępnych dla profilów służbowych oraz ograniczanie możliwości instalowania aplikacji przez użytkowników tylko do aplikacji z zarządzanego sklepu Google Play. W celu skonfigurowania w pełni zarządzanych urządzeń z systemem Android będzie trzeba przejść kolejno do pozycji **Rejestrowanie urządzenia** > **Rejestracja systemu Android** > **Firmowe, w pełni zarządzane urządzenia użytkowników**. Należy pamiętać, że ta funkcja jest dostępna w wersji zapoznawczej. Niektóre funkcje usługi Intune, takie jak certyfikaty, zgodność i dostęp warunkowy, nie są obecnie dostępne dla w pełni zarządzanych urządzeń użytkowników z systemem Android.

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----1672660----"></a>Wdrażanie licencjonowanych w trybie online aplikacji ze sklepu Microsoft Store dla Firm <!-- 1672660  -->
Będzie możliwe przypisywanie w kontekście urządzenia wymaganych, licencjonowanych w trybie online aplikacji ze sklepu Microsoft Store dla Firm. Wdrożona w ten sposób aplikacja ze sklepu Microsoft Store dla Firm będzie mogła być zainstalowana dla wszystkich użytkowników urządzenia. Dotyczy to tylko urządzeń stacjonarnych z systemem Windows 10 w wersji RS4 lub nowszej. Możliwość instalacji w kontekście urządzenia jest dostępna na stronie przypisywania aplikacji klienckich dla aplikacji MSFB licencjonowanych w trybie online.

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470----"></a>Konfigurowanie profilu pod kątem pominięcia niektórych ekranów asystenta ustawień <!-- 2276470  -->
Podczas tworzenia profilu rejestracji systemu macOS będzie można skonfigurować go tak, aby pominąć dowolny z następujących ekranów, gdy użytkownik będzie korzystać z asystenta ustawień:
- Migracja systemu Android
- Wyświetlanie sygnału
- Ochrona prywatności
- iCloudStorage

### <a name="assign-autopilot-profiles-to-the-all-devices-virtual-group---2715522----"></a>Przypisywanie profilów rozwiązania Autopilot do wirtualnej grupy wszystkich urządzeń <!--2715522  -->
Będzie można przypisać profile rozwiązania Autopilot do wirtualnej grupy wszystkich urządzeń. Aby to zrobić, wybierz pozycję **Rejestrowanie urządzeń** > **Rejestracja w systemie Windows** > **Profile wdrażania** > wybierz profil > **Przypisania** > w obszarze **Przypisz do** wybierz pozycję **Wszystkie urządzenia**. Aby uzyskać więcej informacji na temat profilów rozwiązania Autopilot, zobacz [Rejestrowanie urządzeń z systemem Windows przy użyciu rozwiązania Windows Autopilot](enrollment-autopilot.md).

### <a name="customize-wallpaper-on-supervised-ios-devices-using-a-device-configuration-profile----2809324----"></a>Dostosowywanie tapety na urządzeniach nadzorowanych z systemem iOS przy użyciu profilu konfiguracji urządzenia <!-- 2809324  -->
Podczas tworzenia profilu konfiguracji urządzenia dla urządzeń z systemem iOS będzie można włączać lub ograniczać niektóre ustawienia w obszarze **Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > **iOS** dla platformy > **Ograniczenia dotyczące urządzeń** dla typu profilu. Ta aktualizacja zawiera nowe ustawienia **Tapeta**, które pozwalają administratorowi na użycie obrazu w formacie png, jpg lub jpeg jako tapety, wyświetlenie podglądu takiego obrazu i zablokowanie możliwości zmiany tapety przez użytkowników. Ustawienia dotyczące tapety mają zastosowanie tylko na urządzeniach nadzorowanych. Aby uzyskać listę bieżących ustawień, zobacz [iOS device restriction settings](device-restrictions-ios.md) (Ustawienia dotyczące ograniczania urządzeń z systemem iOS).

### <a name="toast-notifications-for-win32-apps----3136566-----"></a>Wyskakujące powiadomienia dla aplikacji Win32 <!-- 3136566   -->
Będzie można pominąć wyświetlanie wyskakujących powiadomień dla użytkownika końcowego podczas przypisywania aplikacji. W usłudze Intune wybierz kolejno pozycje **Aplikacje klienckie** > **Aplikacje** > wybierz aplikację > **Przypisania** > **Uwzględnij grupy**. 

### <a name="contact-sharing-via-bluetooth-is-removed-in-device-restrictions--device-owner-for-android-enterprise----3598396---"></a>Udostępnianie kontaktów za pośrednictwem połączenia Bluetooth zostało usunięte z obszaru Ograniczenia dotyczące urządzeń > Właściciel urządzenia w systemie Android Enterprise <!-- 3598396 -->
Podczas tworzenia profilu ograniczeń dotyczących urządzeń z systemem Android Enterprise widoczne jest ustawienie **Udostępnianie kontaktów za pośrednictwem połączenia Bluetooth**. W ramach tej aktualizacji ustawienie **Udostępnianie kontaktów za pośrednictwem połączenia Bluetooth** zostanie usunięte (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > **Android Enterprise** dla platformy > **Ograniczenia dotyczące urządzeń > Właściciel urządzenia** dla typu profilu > **Ogólne**). 

Ustawienie **Udostępnianie kontaktów za pośrednictwem połączenia Bluetooth** nie jest obsługiwane w przypadku zarządzania właścicielami urządzeń w systemie Android Enterprise. Po usunięciu tego ustawienia nie będzie ono miało wpływu na jakiekolwiek urządzenia czy dzierżawy, nawet jeśli to ustawienie zostało włączone i skonfigurowane w środowisku.

Aby wyświetlić aktualną listę ustawień, zobacz [Ustawienia urządzeń z systemem Android Enterprise w celu zezwolenia na funkcje lub ich ograniczenia](device-restrictions-android-for-work.md).

Dotyczy: właściciel urządzenia z systemem Android Enterprise

<!-- 1812 start -->

### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Wdrażanie aplikacji APP-WE dla systemu Android Enterprise <!-- 1171203 -->
Dla urządzeń z systemem Android w scenariuszu wdrażania zasad ochrony aplikacji bez rejestracji (APP-WE) będzie można używać zarządzanego sklepu Google Play w celu wdrażania aplikacji ze sklepu i aplikacji biznesowych dla użytkowników. Mówiąc ściślej, dział IT może udostępnić użytkownikom końcowym środowisko instalacji i wykazu aplikacji, które nie wymaga już od użytkowników końcowych rozluźnienia stanu zabezpieczeń urządzeń przez umożliwienie instalacji z nieznanych źródeł. Ponadto ten scenariusz wdrażania zapewni ulepszone środowisko pracy użytkownika końcowego.

### <a name="the-intune-app-sdk-will-support-256-bit-encryption-keys----1832174---"></a>Zestaw SDK aplikacji usługi Intune będzie obsługiwać 256-bitowe klucze szyfrowania <!-- 1832174 -->
Zestaw SDK aplikacji usługi Intune dla systemu Android będzie używać 256-bitowych kluczy szyfrowania po włączeniu szyfrowania przy użyciu zasad ochrony aplikacji. Zestaw SDK będzie nadal obsługiwać 128-bitowe klucze w celu zachowania zgodności z zawartością i aplikacjami, które używają starszych wersji zestawu SDK.


### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359---"></a>Zasady usługi Intune aktualizują metodę uwierzytelniania i instalację aplikacji Portal firmy <!-- 1927359 -->
Na urządzeniach, które zostały już zarejestrowane za pomocą Asystenta ustawień przy użyciu jednej z metod rejestracji urządzeń firmowych firmy Apple, usługa Intune nie będzie już obsługiwać aplikacji Portal firmy po jej ręcznym zainstalowaniu ze sklepu z aplikacjami przez użytkowników końcowych. Ta zmiana ma zastosowanie tylko w sytuacji, w której uwierzytelnianie jest przeprowadzane przy użyciu asystenta ustawień firmy Apple podczas rejestracji. Ta zmiana dotyczy tylko urządzeń z systemem iOS zarejestrowanych przy użyciu następujących rozwiązań:  
* Apple Configurator
* Apple Business Manager
* Apple School Manager
* Apple Device Enrollment Program (DEP)

Jeśli użytkownicy zainstalują aplikację Portal firmy ze sklepu z aplikacjami, a następnie podejmą próbę zarejestrowania urządzeń przy jej użyciu, wystąpi błąd. Oczekuje się, że te urządzenia będą używać aplikacji Portal firmy tylko w sytuacji, gdy nastąpi automatyczne wypchnięcie przez usługę Intune podczas rejestracji. Profile rejestracji w usłudze Intune w witrynie Azure Portal zostaną zaktualizowane tak, aby określić sposób uwierzytelniania urządzeń oraz wskazać, czy otrzymują aplikację Portal firmy. Jeśli chcesz, aby użytkownicy urządzenia DEP mieli aplikację Portal firmy, musisz określić swoje preferencje w profilu rejestracji. Ponadto ekran **Identyfikowanie urządzenia** w aplikacji Portal firmy wkrótce będzie przestarzały.  
Aby zainstalować Portal firmy na już zarejestrowanych urządzeniach objętych programem DEP, należy przejść do usługi Intune > Aplikacje klienckie i wypchnąć ją jako aplikację zarządzaną przy użyciu zasad konfiguracji aplikacji. Szczegółowe informacje na temat tych czynności zostaną przedstawione w przyszłej dokumentacji.

### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379---"></a>Użytkownicy inni niż administratorzy mogą włączyć funkcję BitLocker na urządzeniach z systemem Windows 10 dołączonych do usługi Azure AD<!-- 2147379 -->
Włączenie ustawień funkcji BitLocker na urządzeniach z systemem Windows 10 (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10 i nowsze** jako platforma > **Endpoint Protection** jako typ profilu > **Szyfrowanie systemu Windows**) oznacza dodanie ustawień funkcji BitLocker. Ta aktualizacja obejmuje nowe ustawienie funkcji BitLocker, które zezwala użytkownikom standardowym (innym niż administratorzy) na włączanie szyfrowania. Aby wyświetlić bieżące ustawienia, zobacz [Endpoint protection settings for Windows 10](endpoint-protection-windows-10.md#windows-encryption) (Ustawienia programu Endpoint Protection dla systemu Windows 10).


### <a name="additional-settings-for-outlook----3301182---"></a>Dodatkowe ustawienia dla programu Outlook <!-- 3301182 -->
Teraz, używając usługi Intune, można skonfigurować dodatkowe ustawienia dla programu Outlook dla systemów iOS i Android.  Te ustawienia są następujące:
- Zezwalanie na użycie wyłącznie kont służbowych w programie Outlook dla systemów iOS i Android
- Wdrażanie nowoczesnego uwierzytelniania dla usługi Office 365 oraz kont lokalnych nowoczesnego uwierzytelniania hybrydowego
- Używanie wartości `SAMAccountName` dla pola nazwy użytkownika w profilu poczty e-mail, gdy jest wybrane uwierzytelnianie podstawowe
- Zezwalanie na zapisywanie kontaktów
- Konfigurowanie porad dotyczących poczty adresatów zewnętrznych
- Konfigurowanie **priorytetowej skrzynki odbiorczej**
- Wymaganie danych biometrycznych w celu uzyskania dostępu do programu Outlook dla systemu iOS 
- Blokowanie obrazów zewnętrznych

> [!NOTE]
> Jeśli do zarządzania dostępem do tożsamości firmowych są używane zasady rozwiązania Intune App Protection, warto rozważyć wyłączenie **wymagania danych biometrycznych**. Aby uzyskać więcej informacji, zobacz **Wymagaj poświadczeń firmowych w celu udzielenia dostępu** dla [wymagań dotyczących dostępu systemu iOS](app-protection-policy-settings-ios.md#access-settings) i [wymagań dotyczących dostępu systemu Android](app-protection-policy-settings-android.md#access-settings).

### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Szablony administracyjne są dostępne w publicznej wersji zapoznawczej i zostały przeniesione do własnego profilu konfiguracji <!-- 3322847 -->
Szablony administracyjne w usłudze Intune (**Konfiguracja urządzenia** > **Szablony administracyjne**) są obecnie dostępne w prywatnej wersji zapoznawczej. Dzięki tej aktualizacji szablony administracyjne obejmują około 300 ustawień, którymi można zarządzać w usłudze Intune. Wcześniej ustawienia te istniały tylko w edytorze zasad grupy.
Szablony administracyjne są dostępne w publicznej wersji zapoznawczej Szablony administracyjne są przenoszone z obszaru **Konfiguracja urządzenia** > **Szablony administracyjne** do obszaru **Konfiguracja urządzenia** > **Profile** >**Utwórz profil** > w polu **Platforma** wybierz  **Windows 10 i nowsze**, w polu **Typ profilu** wybierz **Szablony administracyjne**.
Włączone raportowanie Dotyczy: System Windows 10 lub nowszy

### <a name="intune-macos-company-portal-dark-mode----3300524---"></a>Tryb ciemny Portalu firmy usługi Intune w systemie macOS <!-- 3300524 -->
Portal firmy usługi Intune w systemie macOS obsługuje teraz tryb ciemny systemu macOS. Po włączeniu trybu ciemnego na urządzeniu z systemem macOS w wersji 10.14 lub nowszej Portal firmy dostosuje swój wygląd do kolorów obecnych w tym trybie.

<!-- 1810 start -->

### <a name="use-microsoft-recommended-settings-with-security-baselines----2055484---"></a>Używanie ustawień zalecanych przez firmę Microsoft z punktami odniesienia zabezpieczeń <!-- 2055484 -->
Usługa Intune umożliwia integrację z innymi usługami koncentrującymi się na zabezpieczeniach, w tym z usługą Windows Defender ATP i usługą Office 365 ATP. Klienci pytają o typową strategię i spójny zestaw kompleksowych przepływów pracy zabezpieczeń w usługach Microsoft 365. Naszym celem jest dopasowanie strategii w celu utworzenia rozwiązań, które łączą operacje zabezpieczeń i typowe zadania administratora. W usłudze Intune staramy się osiągnąć ten cel, publikując zestaw „punktów odniesienia zabezpieczeń” zalecanych przez firmę Microsoft (**Intune** > **Punkty odniesienia zabezpieczeń**).  Administrator będzie mógł tworzyć zasady zabezpieczeń bezpośrednio z tych punktów odniesienia, a następnie wdrożyć je dla użytkowników. Można również dostosować rekomendacje dotyczące najlepszych rozwiązań do potrzeb swojej organizacji. Usługa Intune zapewnia, że urządzenia pozostają w zgodności z tymi punktami odniesienia, i powiadamia administratorów użytkowników lub urządzeń, które nie są zgodne.

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



<!-- 1807 start -->

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Sprawdzanie zgodności w programie Configuration Manager <!-- 2192052 -->
Przyszła aktualizacja będzie zawierać nowe ustawienie zgodności programu System Center Configuration Manager (**Zgodność urządzeń** > **Zasady** > **Tworzenie zasad** > **System Windows 10**). Program Configuration Manager wysyła sygnały zgodności do usługi Intune. Przy użyciu ustawienia usługi Intune można wymagać, aby wszystkie sygnały programu Configuration Manager zwracały stan „zgodne”.

Na przykład można wymagać, aby na urządzeniach były zainstalowane wszystkie aktualizacje oprogramowania. W programie Configuration Manager to wymaganie ma stan „Zainstalowano”. Jeśli jakiekolwiek programy na urządzeniu mają nieznany stan, to urządzenie będzie niezgodne w usłudze Intune.

Dotyczy: system Windows 10 lub nowszy



## <a name="notices"></a>Uwagi

Aktualnie nie ma aktywnych powiadomień.

### <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).



