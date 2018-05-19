---
title: Wczesna wersja
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/09/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f3cbfad85e4a7a97d9bbf98e2ad239fda7cc29e4
ms.sourcegitcommit: d40bfb6af66f2ce7026c0151ace98ec23f1cf76e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/10/2018
---
# <a name="the-early-edition-for-microsoft-intune---may-2018"></a>Wersja wczesna usługi Microsoft Intune — maj 2018

**Wczesna wersja** zawiera listę funkcji, które zostaną wprowadzone w przyszłych wersjach usługi Microsoft Intune. Te informacje są przekazywane w ograniczonym zakresie i mogą ulec zmianie. Nie należy udostępniać tych informacji poza firmą. Niektóre funkcje wymienione w tym miejscu mogą nie być wdrożone na czas i zostać opóźnione do przyszłych wersji. Inne funkcje są testowane w wersji pilotażowej, aby zapewnić przygotowanie ich do użytku przez klientów. W przypadku pytań lub wątpliwości skontaktuj się z osobą kontaktową ds. tej grupy produktów firmy Microsoft.

Ta strona jest okresowo aktualizowana. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.

> [!Note]
>Dla usługi Intune opracowywane są następujące zmiany. Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Usługa Intune w witrynie Azure Portal

<!-- 1805 start -->

### <a name="set-compliance-by-device-location----851881----"></a>Ustawianie zgodności według lokalizacji urządzenia <!-- 851881 ! -->
W niektórych sytuacjach możesz ograniczyć dostęp do zasobów firmy do określonej lokalizacji zdefiniowanej przez połączenie sieciowe. Zasady zgodności (**Zgodność urządzenia** > **Lokalizacje**) będzie można utworzyć na podstawie adresu IP urządzenia. Jeśli urządzenie zostanie przeniesione poza zakres adresów IP, nie będzie miało dostępu do zasobów firmy.

### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Ulepszone rozwiązywanie problemów z instalacją aplikacji <!-- 928990 -->
Na urządzeniach zarządzanych przez oprogramowanie MDM w usłudze Microsoft Intune czasami operacje instalacji aplikacji mogą zakończyć się niepowodzeniem. W takich sytuacjach zrozumienie przyczyny niepowodzenia lub rozwiązanie problemu może okazać się wyzwaniem. Udostępniamy publiczną wersję zapoznawczą naszej funkcji rozwiązywania problemów z aplikacjami. W obszarach poszczególnych urządzeń zauważysz nowy węzeł o nazwie **Aplikacje zarządzane**. Ta pozycja służy do wyświetlania listy aplikacji dostarczonych za pomocą oprogramowania MDM usługi Intune. Wewnątrz węzła znajduje się lista stanów instalacji aplikacji. Po wybraniu aplikacji zostanie wyświetlony widok rozwiązywania problemów związanych z tą aplikacją. W widoku rozwiązywania problemów zostanie przedstawiony cały cykl życia aplikacji, np. czas utworzenia i zmodyfikowania aplikacji, wybrania jej jako docelowej i dostarczenia do urządzenia. Ponadto jeśli instalacja aplikacji zakończyła się niepowodzeniem, zostanie wyświetlony kod błędu i użyteczny komunikat dotyczący przyczyny tego błędu. 

### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>Blokowanie dostępu do aplikacji dla niezatwierdzonych dostawców i modeli urządzeń <!-- 1425689 ! -->
Administrator IT usługi Intune będzie mógł wymuszać określoną listę producentów urządzeń z systemem Android i/lub modeli urządzeń z systemem iOS za pomocą zasad ochrony aplikacji w usłudze Intune. Administrator IT może przedstawić rozdzielaną średnikami listę producentów zgodnych z zasadami systemu Android oraz modeli urządzeń zgodnych z zasadami systemu iOS. Zasady ochrony aplikacji w usłudze Intune są przeznaczone tylko dla systemów Android i iOS. Dla podanej listy będzie można wykonać dwie oddzielne akcje:
- Blokowanie dostępu do aplikacji na urządzeniach, które nie zostały określone.
- Lub selektywne czyszczenie danych firmowych na urządzeniach, które nie zostały określone. 

Użytkownik nie będzie mógł uzyskiwać dostępu do aplikacji docelowej, jeśli wymagania zasad nie zostaną spełnione. Na podstawie ustawień użytkownik może zostać zablokowany albo jego dane firmowe mogą zostać selektywnie wyczyszczone z aplikacji. Na urządzeniach z systemem iOS ta funkcja wymaga udziału aplikacji (np. WXP, Outlook, Managed Browser, Yammer) w celu integracji zestawu SDK aplikacji Intune oraz ustawień wersji minimalnej, które mają być wymuszane w aplikacjach docelowych. Ta integracja jest przeprowadzana w sposób ciągły i zależy od zespołów zajmujących się określonymi aplikacjami. W systemie Android ta funkcja wymaga najnowszej wersji aplikacji Portal firmy.

Na urządzeniach użytkowników końcowych klient usługi Intune wykonuje akcję w oparciu o proste dopasowywanie ciągów określonych w bloku usługi Intune dla zasad ochrony aplikacji. Zależy to całkowicie od wartości zgłaszanej przez urządzenie. W takiej sytuacji administrator IT jest zachęcany do zapewniania, że założone zachowanie jest prawidłowe. Ten cel można osiągnąć, testując to ustawienie w oparciu o różnych producentów i modele urządzeń przeznaczone dla małej grupy użytkowników. W usłudze Microsoft Intune wybierz pozycję **Aplikacje mobilne** > **Zasady ochrony aplikacji**, aby wyświetlić i dodać zasady ochrony aplikacji. Aby uzyskać więcej informacji na temat zasad ochrony aplikacji, zobacz [Co to są zasady ochrony aplikacji](app-protection-policy.md).

### <a name="enable-kiosk-mode-on-windows-10-devices----1560072----"></a>Włączanie trybu kiosku na urządzeniach z systemem Windows 10 <!-- 1560072 ! -->
Na urządzeniach z systemem Windows 10 można utworzyć profil konfiguracji i włączyć tryb kiosku (**Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **Windows 10** > **Ograniczenia urządzenia** > **Kiosk**). W ramach tej aktualizacji nazwa ustawienia **Kiosk (wersja zapoznawcza)** została zmieniona na **Kiosk (przestarzałe)**. Używanie ustawienia **Kiosk (przestarzałe)** nie jest już zalecane, ale będzie ono działać do momentu wydania aktualizacji w lipcu. Ustawienie **Kiosk (przestarzałe)** zostało zastąpione przez nowy typ profilu **Kiosk** (**Utwórz profil** > **Windows 10** > **Kiosk (wersja zapoznawcza)**), który będzie zawierać ustawienia służące do konfigurowania kiosków w systemie Windows 10 RS4 lub nowszym.

Dotyczy systemu Windows 10 lub nowszych.

### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode----1560077----"></a>Pobieranie skojarzonego identyfikatora modelu użytkownika aplikacji (AUMID) dla aplikacji ze sklepu Microsoft Store dla Firm w trybie kiosku <!-- 1560077 ! -->
Usługa Intune będzie mogła pobrać identyfikatory modelu użytkownika aplikacji (AUMID) dla aplikacji ze sklepu Microsoft Store dla Firm (WSfB) w celu udostępniania ulepszonej konfiguracji profilu kiosku.

Aby uzyskać więcej informacji na temat aplikacji ze sklepu Microsoft Store dla Firm, zobacz [Manage apps from Microsoft Store for Business](windows-store-for-business.md) (Zarządzanie aplikacjami ze sklepu Microsoft Store dla Firm).

### <a name="access-actions-for-app-protection-policies----1483510-eeready---"></a>Akcje dotyczące uzyskiwania dostępu dla zasad ochrony aplikacji <!-- 1483510 EEready -->
Wkrótce będzie można konfigurować zasady ochrony aplikacji w celu jawnego czyszczenia lub blokowania niezgodnych urządzeń albo ostrzegania o nich. Najnowsza akcja *czyszczenia* powoduje usunięcie danych firmowych z urządzenia. W przypadku czyszczenia użytkownik urządzenia jest powiadamiany o przyczynie uruchomienia tego procesu oraz czynnościach korygujących. W przypadku niektórych ustawień, takich jak minimalna wersja systemu operacyjnego, można zastosować wiele akcji, takich jak blokowanie i czyszczenie.

### <a name="new-inventory-information-for-windows-devices----1333569-eeready---"></a>Nowe informacje ze spisu urządzeń z systemem Windows <!-- 1333569 eeready -->

W przypadku urządzeń z systemem Windows w spisie będą dostępne następujące informacje o poszczególnych urządzeniach na karcie **Sprzęt** (**Grupy** > **Wszystkie urządzenia przenośne** > **Urządzenia** > wybierz urządzenie użytkownika > **Wyświetl właściwości** > **Sprzęt**):
- Moduł TPM
- Oprogramowanie antywirusowe
- Program antyszpiegowski
- Zapora
- UAC
- Bateria
- Nazwa domeny

Aby uzyskać więcej informacji na temat sposobu uzyskiwania tych danych przez dostawcę usługi konfiguracji, zobacz wpisy DeviceGuard w artykule [DeviceStatus CSP](https://docs.microsoft.com/en-us/windows/client-management/mdm/devicestatus-csp) (Dostawca usługi konfiguracji DeviceGuard).

### <a name="intune-and-the-microsoft-edge-browser----1818969---"></a>Usługa Intune i przeglądarka Microsoft Edge <!-- 1818969 -->
Przeglądarka Microsoft Edge dla urządzeń przenośnych (iOS i Android) obsługuje teraz zasady ochrony aplikacji w usłudze Intune. Użytkownicy, którzy logują się przy użyciu kont firmowych usługi Azure AD w aplikacji przeglądarki Edge, będą chronieni przez usługę Intune. 

### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot----1821766---"></a>Nowe ustawienie języka/regionu podczas konfigurowania OOBE dla rozwiązania Autopilot <!-- 1821766 -->
Zostanie udostępnione nowe ustawienie konfiguracji umożliwiające ustawianie języka i regionu dla profilów rozwiązania Autopilot podczas uruchamiania typu Out of Box Experience.

### <a name="new-setting-for-configuring-device-keyboard----1821768---"></a>Nowe ustawienie służące do konfigurowania klawiatury urządzenia <!-- 1821768 -->
Zostanie udostępnione nowe ustawienie umożliwiające konfigurowanie klawiatury dla profilów rozwiązania Autopilot podczas uruchamiania typu Out of Box Experience.

### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices----1985547---"></a>Używanie programu TeamViewer do udostępniania ekranów urządzeń z systemami iOS i MacOS<!-- 1985547 -->
Obecnie można używać programu TeamViewer do zdalnego administrowania [zarządzanymi przez usługę Intune urządzeniami z systemem Android i Windows](device-profile-android-teamviewer.md).

Administratorzy będą mogli łączyć się z programem TeamViewer, a następnie uruchamiać sesję udostępniania ekranu na urządzeniach z systemem iOS i macOS. Użytkownicy urządzeń iPhone i iPad oraz urządzeń z systemem macOS mogą na żywo udostępniać ekrany innemu urządzeniu stacjonarnemu lub przenośnemu. 

### <a name="device-profile-graphical-user-chart-is-back----2160133---"></a>Graficzny wykres użytkowników profilu urządzeń jest ponownie dostępny <!-- 2160133 -->
W trakcie ulepszania sposobu wyświetlania liczb na graficznym wykresie profilu urządzenia (**Konfiguracja urządzenia** > **Profile** > wybierz istniejący profil > **Omówienie**) tymczasowo usunięto graficzny wykres użytkowników.

W ramach tej aktualizacji graficzny wykres użytkowników został ponownie udostępniony i jest wyświetlany w witrynie Azure Portal.

### <a name="assign-all-users-and-all-devices-as-scope-groups----2196803---"></a>Przypisywanie wszystkich użytkowników i wszystkich urządzeń jako grup zakresu <!-- 2196803 -->
W grupach zakresu będzie można przypisywać wszystkich użytkowników, wszystkie urządzenia oraz wszystkich użytkowników i wszystkie urządzenia.

### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Profile rozwiązania AutoPilot będą stosowane dla grup <!-- 1877935 -->
Obecnie profile wdrażania rozwiązania AutoPilot można przypisać do wybranych urządzeń. Poniżej przedstawiono czynności, które będzie można wykonywać po wydaniu tej funkcji:
- Utwórz grupy usługi Azure AD, zawierające urządzenia z rozwiązaniem AutoPilot.
- Przypisz wybrane profile do grupy usługi Azure AD. Profil rozwiązania AutoPilot będzie teraz przypisany do urządzeń rozwiązania AutoPilot w tej grupie.

### <a name="management-name-field-will-be-editable----1875989---"></a>Będzie można edytować pole Nazwa zarządzania <!-- 1875989 -->
Będzie można edytować pole Nazwa zarządzania w bloku **Właściwości** urządzenia. Aby edytować to pole, wybierz pozycję **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenie > **Właściwości**. Pola nazwy zarządzania można używać do unikatowego identyfikowania urządzenia.

<!-- 1804 start -->


### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Dodatki dla ustawień opcji zabezpieczeń urządzenia lokalnego <!-- 1403702 -->
Będzie można skonfigurować dodatkowe ustawienia opcji zabezpieczeń urządzenia lokalnego dla urządzeń z systemem Windows 10. Dodatkowe ustawienia będą dostępne w następujących obszarach: klient sieci Microsoft, serwer sieci Microsoft, dostęp do sieci i zabezpieczenia oraz logowanie interakcyjne. Te ustawienia można znaleźć w kategorii Endpoint Protection podczas tworzenia zasad konfiguracji urządzeń z systemem Windows 10.

### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>Wymagana instalacja zasad, aplikacji oraz profilów certyfikatów i sieciowych <!-- 1553555 -->
Administratorzy będą mogli zablokować dostęp użytkowników końcowych do pulpitu systemu Windows 10 RS4 do momentu zainstalowania zasad, aplikacji oraz profilów certyfikatów i sieciowych przez usługę Intune podczas aprowizowania urządzeń z rozwiązaniem AutoPilot.

### <a name="rules-for-removing-devices----1609459---"></a>Reguły usuwania urządzeń <!-- 1609459 -->
Będą dostępne nowe reguły umożliwiające automatyczne usuwanie urządzeń, które nie zostały zaewidencjonowane przez ustawioną liczbę dni. Aby wyświetlić nową regułę, przejdź do okienka **Intune**, wybierz pozycję **Urządzenia**, a następnie pozycję **Reguły usuwania urządzeń**.

### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Blokowanie aplikacji i środowisk konsumenckich na urządzeniach z rozwiązaniem AutoPilot w systemie Windows 10 Enterprise RS4<!-- 1621980 -->
Będzie można zablokować instalację aplikacji i środowisk konsumenckich na urządzeniach z systemem Windows 10 Enterprise RS4 i rozwiązaniem AutoPilot. Aby wyświetlić tę funkcję, przejdź do pozycji **Intune** > **Rejestrowanie urządzenia** > **Rejestrowanie systemu Windows** > **Profile AutoPilot systemu Windows** > **Utwórz nowy** > **Ustawienia rejestracji**. 

<!-- 1803 start -->

#### <a name="multiple-exchange-connector-support----2070451---"></a>Obsługa wielu programów Exchange Connector <!-- 2070451 -->

Nie będzie już ograniczenia do jednego programu Microsoft Intune Exchange Connector na dzierżawę. Usługa Intune będzie obsługiwać wiele programów Microsoft Intune Exchange Connector, dzięki czemu możliwe będzie skonfigurowanie dostępu warunkowego w usłudze Intune przy użyciu wielu lokalnych organizacji programu Exchange.

Dzięki lokalnemu łącznikowi programu Exchange w usłudze Intune możesz zarządzać dostępem urządzeń do lokalnych skrzynek pocztowych programu Exchange na podstawie tego, czy urządzenie jest zarejestrowane w usłudze Intune i jest zgodne z zasadami zgodności urządzeń usługi Intune. Aby skonfigurować łącznik, pobierz lokalny łącznik programu Exchange z witryny Azure Portal i zainstaluj go na serwerze w organizacji programu Exchange. Na pulpicie nawigacyjnym usługi Microsoft Intune wybierz pozycję **Dostęp lokalny**, a następnie w obszarze **Konfiguracja** wybierz pozycję **Łącznik Exchange ActiveSync**. Pobierz lokalny łącznik programu Exchange i zainstaluj go na serwerze w organizacji programu Exchange. Ponieważ nie ma już ograniczenia do jednego łącznika programu Exchange na dzierżawę, jeśli masz dodatkowe organizacje programu Exchange, możesz wykonać te same czynności, aby pobrać i zainstalować łącznik dla każdej dodatkowej organizacji programu Exchange.

### <a name="support-coming-for-new-cisco-anyconnect-client-for-ios----1333708---"></a>Nadchodząca obsługa klienta oprogramowania Cisco AnyConnect dla systemu iOS <!-- 1333708 -->

Nowe profile sieci VPN utworzone dla oprogramowania Cisco AnyConnect będą działały z wersją oprogramowania Cisco AnyConnect 4.0.7x i wyższymi. Istniejące profile sieci VPN oprogramowania Cisco AnyConnect dla systemu iOS zostaną oznaczone etykietą **Cisco Legacy AnyConnect** i będą nadal działały z oprogramowaniem AnyConnect 4.0.5x, jak ma to miejsce obecnie.

> [!NOTE]
> Ta zmiana dotyczy tylko systemu iOS; w przypadku systemów Android i macOS oraz programu Android for Work nadal będzie dostępna tylko jedna opcja oprogramowania Cisco AnyConnect.

#### <a name="more-information"></a>Więcej informacji

Aby włączyć obsługę nowej aplikacji, musisz utworzyć nowy profil sieci VPN oprogramowania Cisco AnyConnect dla systemu iOS, ponieważ nowa aplikacja Cisco AnyConnect oraz aplikacja Cisco Legacy AnyConnect to oddzielne aplikacje. Jeśli zarządzasz klientem oprogramowania AnyConnect w danym środowisku, musisz wdrożyć także nową aplikację Cisco AnyConnect. Aby wykonać uaktualnienie musisz także usunąć profil sieci VPN oprogramowania Cisco Legacy AnyConnect oraz aplikację Cisco Legacy AnyConnect.

W początkowym wydaniu integracja kontroli dostępu do sieci (NAC) nie będzie działać w przypadku nowego klienta oprogramowania AnyConnect. Wraz z firmą Cisco pracujemy nad umożliwieniem integracji NAC w przyszłym wydaniu usługi Intune.

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Możliwość wdrożenia wymaganych aplikacji biznesowych (LOB) dla wszystkich użytkowników urządzeń z systemem Windows 10 Desktop <!-- 1627835 RS4 -->
Klienci będą mogli wdrażać wymagane aplikacje biznesowe systemu Windows 10 oraz instalować je w kontekstach urządzeń. Umożliwi to udostępnienie tych aplikacji wszystkim użytkownikom urządzenia. Dotyczy to tylko urządzeń z systemem Windows 10 Desktop.

### <a name="company-portal-enrollment-improved----1874230--"></a>Ulepszona rejestracja za pomocą aplikacji Portal firmy <!-- 1874230-->
Użytkownicy rejestrujący urządzenia za pomocą aplikacji Portal firmy w systemie Windows 10 w wersji 1703 i wyższej będą mogli wykonać pierwszy krok rejestracji bez wychodzenia z aplikacji.

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Aktualizowanie środowiska Pomoc i opinie w aplikacji Portal firmy dla systemu Android <!--1631531 -->

Zaktualizujemy środowisko Pomoc i opinie w aplikacji Portal firmy dla systemu Android, aby było zgodne z najlepszymi rozwiązaniami dla aplikacji systemu Android. W ciągu kilku następnych miesięcy wprowadzimy aktualizację aplikacji Portal firmy dla systemu Android dzielącą element menu **Pomoc i opinie** na oddzielne elementy **Pomoc** i **Prześlij opinię**. Strona **Pomoc** będzie zawierała sekcję **Często zadawane pytania** oraz przycisk **Pomoc techniczna pocztą e-mail**, który umożliwi użytkownikom końcowym przekazanie dzienników firmie Microsoft i wysłanie wiadomości e-mail do pomocy technicznej firmy wraz z opisem problemu. Funkcja **Prześlij opinię** przeprowadzi użytkownika przez standardowy proces przesyłania opinii, podczas którego użytkownik będzie mógł wybrać opcje takie jak „Coś mi się podoba”, „Coś mi się nie podoba”, „Mam pomysł”.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Zasady usługi App Protection <!-- 679615 -->
Zasady usługi Intune App Protection umożliwiają tworzenie globalnych, domyślnych zasad, które pozwalają na szybkie włączenie ochrony dla wszystkich użytkowników w całej dzierżawie.

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Witryny internetowe usługi Azure Active Directory mogą wymagać aplikacji Intune Managed Browser i obsługiwać rejestrację jednokrotną w aplikacji Managed Browser (publiczna wersja zapoznawcza) <!-- 710595 -->   
Korzystając z usługi Azure Active Directory (Azure AD), można ograniczyć dostęp do witryn internetowych na urządzeniach przenośnych tylko do aplikacji Intune Managed Browser. W aplikacji Managed Browser dane witryn internetowych będą bezpieczne i odseparowane od osobistych danych użytkowników końcowych. Ponadto w przypadku witryn chronionych przez usługę Azure AD aplikacja Managed Browser będzie obsługiwać funkcje logowania jednokrotnego. Zarejestrowanie się w aplikacji Managed Browser lub korzystanie z aplikacji Managed Browser na urządzeniu z inną aplikacją zarządzaną przez usługę Intune umożliwia aplikacji Managed Browser dostęp do witryn firmowych chronionych przez usługę Azure AD bez konieczności wprowadzania poświadczeń użytkownika. Ta funkcja ma zastosowanie do witryn takich jak Outlook Web Access (OWA) i SharePoint Online, a także innych witryn firmowych, takich jak zasoby intranetowe dostępne za pośrednictwem serwera proxy aplikacji platformy Azure.


## <a name="notices"></a>Uwagi

Aktualnie nie ma aktywnych powiadomień.

### <a name="see-also"></a>Zobacz też
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).
