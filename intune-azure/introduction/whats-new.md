---
title: "Co nowego w wersji zapoznawczej usługi Microsoft Intune"
titleSuffix: Intune Azure preview
description: "Dowiedz się, co nowego w wersji zapoznawczej usługi Intune platformy Azure"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 04/20/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 62dcb40ad5a7921c514a9d41da14b991e39f3bcd
ms.openlocfilehash: 9554a431859665312daf414f2c6cdfb47baf8547
ms.lasthandoff: 04/20/2017

---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>Co nowego w wersji zapoznawczej usługi Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

W miarę rozwoju wersji zapoznawczej i dodawania kolejnych funkcji będziemy Cię o nich tutaj powiadamiać.

> [!Note]
> Stopniowo wprowadzamy zmiany wymienione na tej stronie wersji zapoznawczej portalu Azure. Jednak zmiany mogą nie być dostępne od razu ze względu na sposób aktualizacji usługi Intune.  Zanim nowe funkcje staną się dostępne, niektóre składniki usługi muszą zostać zaktualizowane sekwencyjnie. Szukaj tych zmian w miarę ich sukcesywnego wdrażania w tym miesiącu.

## <a name="april-2017"></a>Kwiecień 2017

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Obsługa opcji zarządzanych konfiguracji dla aplikacji systemu Android <!-- 621621 -->

Za pośrednictwem usługi Intune można teraz skonfigurować przeznaczone dla systemu Android aplikacje ze sklepu Play, które obsługują zarządzane opcje konfiguracji.  Ta funkcja umożliwia pracownikom działu IT wyświetlanie listy wartości konfiguracji obsługiwanych przez aplikację oraz zapewnia najwyższej klasy interfejs użytkownika z przewodnikiem, dzięki któremu można skonfigurować te wartości.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Nowe zasady dla systemu Android dotyczące złożonych numerów PIN <!-- 722069 -->

W przypadku urządzeń z systemem Android 5.0 lub nowszym można teraz ustawić w profilu urządzenia wymagany typ [hasła](/intune-azure/configure-devices/device-restrictions-for-android#password) na „Złożona wartość liczbowa”.  Użyj tego ustawienia, aby uniemożliwić użytkownikom tworzenie numerów PIN zawierających powtarzające się lub kolejne liczby, np. 1111 lub 1234.

### <a name="additional-support-for-android-for-work-devices"></a>Dodatkowa obsługa urządzeń z programem Android for Work

- **Zarządzaj ustawieniami hasła i profilu służbowego** <!-- 612808 -->

  Te nowe zasady ograniczeń dla urządzeń z programem Android for Work umożliwiają teraz zarządzanie ustawieniami hasła i profilu służbowego na zarządzanych urządzeniach z programem Android for Work.

- **Zezwalaj na współużytkowanie danych między profilem służbowym i osobistym** <!-- 1045102 -->

Ten profil ograniczeń urządzenia z programem Android for Work oferuje teraz nowe opcje pozwalające skonfigurować udostępnianie danych między profilami służbowym i osobistym.

- **Ogranicz kopiowanie i wklejanie między profilami służbowymi i osobistymi** <!-- 1046094 -->

  Nowy niestandardowy profil urządzenia dla urządzeń z programem Android for Work umożliwia obecnie określenie, czy akcje kopiowania i wklejania między aplikacjami służbowymi i osobistymi mają być dozwolone.

Aby uzyskać więcej informacji, zobacz artykuł [Ograniczenia urządzenia z programem Android for Work](/intune-azure/configure-devices/device-restrictions-for-afw).

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>Przypisuj aplikacje LOB do urządzeń z systemem iOS lub Android <!-- 1057568 -->

Możesz teraz przypisywać różne aplikacje biznesowe (LOB) dla systemu [iOS](/intune-azure/manage-apps/ios-lob-app) (pliki ipa) lub [Android](/intune-azure/manage-apps/android-lob-app) (pliki apk) do użytkowników lub urządzeń.

###  <a name="new-device-policies-for-ios----723774-723815-723826-723830---"></a>Nowe zasady dotyczące urządzeń dla systemu iOS <!-- 723774, 723815, 723826, 723830 -->

- **Aplikacje na ekranie głównym** — pozwala określić, które aplikacje użytkownik może zobaczyć na [ekranie głównym swojego urządzenia z systemem iOS](/intune-azure/configure-devices/home-screen-settings-for-ios). Zasady te zmieniają układ ekranu głównego, ale nie wdrażają żadnych określonych aplikacji, które nie zostały zainstalowane.

- **Połączenia z urządzeniami AirPrint** — pozwala określić, z którymi [urządzeniami AirPrint](/intune-azure/configure-devices/air-print-settings-for-ios-and-macos) (drukarkami sieciowymi) użytkownicy końcowi urządzeń z systemem iOS będą mogli nawiązywać połączenie.

- **Połączenia z urządzeniami AirPlay** — pozwala określić, z którymi [urządzeniami AirPlay](/intune-azure/configure-devices/airplay-settings-for-ios-devices) (np. urządzeniami Apple TV) użytkownicy końcowi urządzeń z systemem iOS będą mogli nawiązywać połączenie.

- **Niestandardowy komunikat ekranu blokady** — pozwala skonfigurować niestandardowy komunikat, który użytkownicy zobaczą na ekranie blokady urządzenia z systemem iOS zamiast domyślnego komunikatu ekranu blokady. Aby uzyskać więcej informacji, zobacz temat [Dostępne akcje urządzenia](/intune-azure/manage-devices/what-is#available-device-actions).


### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>Ogranicz powiadomienia wypychane dla aplikacji systemu iOS <!-- 723767 -->

W profilu ograniczeń urządzenia w usłudze Intune możesz teraz skonfigurować następujące [ustawienia powiadomień](/intune-azure/configure-devices/app-notification-settings-for-ios) dla urządzeń z systemem iOS:

- W pełni włączyć lub wyłączyć powiadomienia dla określonej aplikacji.
- Włączyć lub wyłączyć powiadomienia w centrum powiadomień dla określonej aplikacji.
- Określić typ alertu: **Brak**, **Transparent** lub **Alert modalny**.
- Określić, czy identyfikatory są dozwolone dla tej aplikacji.
- Określić, czy dźwięki powiadomień są dozwolone.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>Skonfiguruj aplikacje systemu iOS do autonomicznego uruchamiania w trybie pojedynczej aplikacji <!-- 737837 -->

Możesz teraz użyć profilu urządzenia w usłudze Intune do skonfigurowania urządzeń z systemem iOS, aby uruchamiać określone aplikacje w [autonomicznym trybie pojedynczej aplikacji](/intune-azure/configure-devices/device-restrictions-for-ios#autonomous-single-app-mode-supervised-only). Jeśli skonfigurowano ten tryb, a aplikacja zostanie uruchomiona, urządzenie zostanie zablokowane, aby mogło uruchamiać wyłącznie tę aplikację. Opcję tę można przykładowo wykorzystać w przypadku konfigurowania aplikacji, która umożliwia użytkownikom wykonywanie testów na urządzeniu. Po zakończeniu działań aplikacji lub usunięciu tych zasad urządzenie powraca do normalnego stanu.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>Skonfiguruj zaufane domeny dla poczty e-mail i przeglądania sieci Web na urządzeniach z systemem iOS <!-- 723765 -->

W profilu ograniczeń urządzenia z systemem iOS możesz teraz skonfigurować następujące [ustawienia domen](/intune-azure/configure-devices/device-restrictions-for-ios#domains):

- **Nieoznaczone domeny poczty e-mail** — wiadomości e-mail wysyłane lub odbierane przez użytkownika, które nie pasują do domen określonych w tym miejscu, będą oznaczone jako niezaufane.

- **Zarządzane domeny sieci Web** — dokumenty pobierane z adresów URL określonych w tym miejscu będą uznawane za zarządzane (tylko przeglądarka Safari).  

- **Domeny automatycznego uzupełniania haseł przeglądarki Safari** — użytkownicy mogą zapisywać hasła w przeglądarce Safari tylko w przypadku adresów URL spełniających wzorce określone w tym miejscu. Aby użyć tego ustawienia, urządzenie musi być w trybie nadzorowanym i nie może być skonfigurowane dla wielu użytkowników. (iOS 9.3+)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>Aplikacje VPP dostępne w aplikacji Portal firmy dla systemu iOS <!-- 748782 -->

Możesz teraz przypisać aplikacje dla systemu iOS zakupione zbiorczo (VPP) jako **Dostępne** instalacje do użytkowników końcowych. Użytkownicy końcowi potrzebują konta sklepu Apple Store, aby zainstalować aplikację.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>Synchronizuj książki elektroniczne ze sklepu Apple VPP Store <!-- 800878 -->

Możesz teraz [synchronizować książki](/intune-azure/manage-apps/ios-vpp-apps) zakupione w sklepie programu zakupów zbiorczych Apple przy użyciu usługi Intune i przypisywać je do użytkowników.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Zarządzanie wieloma użytkownikami w przypadku urządzeń Samsung KNOX Standard <!-- 971988 -->

Urządzenia z systemem Samsung KNOX Standard są teraz obsługiwane w przypadku [zarządzania wieloma użytkownikami](/intune-azure/enroll-devices/enroll-android-and-knox-standard-devices) przez usługę Intune. Oznacza to, że użytkownicy końcowi mogą zalogować się na urządzeniu przy użyciu poświadczeń usługi Azure Active Directory lub wylogować się z niego, a urządzenie jest zarządzane centralnie niezależnie od tego, czy jest używane.  Użytkownicy końcowi po zalogowaniu otrzymują dostęp do aplikacji, a także są stosowane wobec nich zasady. Gdy użytkownicy się wylogują, wszystkie dane aplikacji są usuwane.

### <a name="additional-windows-device-restriction-settings----818566---"></a>Dodatkowe ustawienia ograniczeń urządzeń z systemem Windows <!-- 818566 -->

Dodaliśmy obsługę dodatkowych [ustawień ograniczeń urządzeń z systemem Windows](/intune-azure/configure-devices/device-restrictions-for-windows-10), np. dodatkową obsługę przeglądarki Edge, dostosowywanie ekranu blokady na urządzeniu, dostosowywanie menu Start, tapetę zestawu wyszukiwania W centrum uwagi Windows oraz ustawienia serwera proxy.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Obsługa wielu użytkowników w aktualizacji Windows 10 Creators Update <!-- 822547 -->

Dodaliśmy obsługę [zarządzania wieloma użytkownikami](/intune-azure/enroll-devices/enroll-windows-devices) na urządzeniach z aktualizacją systemu Windows 10 dla twórców, które zostały dołączone do domeny usługi Azure Active Directory. Oznacza to, że różni użytkownicy standardowi po zalogowaniu się do urządzenia przy użyciu poświadczeń usługi Azure AD otrzymują wszelkie aplikacje i zasady, które zostały przypisane do ich nazw użytkowników. Obecnie użytkownicy nie mogą używać witryny internetowej Portal firmy na potrzeby samoobsługowych scenariuszy, takich jak instalowanie aplikacji.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Świeży początek dla komputerów z systemem Windows 10<!-- 1004830 -->

Dla komputerów z systemem Windows 10 dostępna jest nowa [akcja odświeżonego uruchomienia urządzenia](/intune-azure/manage-devices/what-is#available-device-actions).  Po wykonaniu tej akcji wszelkie aplikacje zainstalowane na komputerze zostaną usunięte, a komputer zostanie automatycznie zaktualizowany do najnowszej wersji systemu Windows. Funkcja może być przydatna do usuwania wstępnie zainstalowanych aplikacji OEM, które są często dostarczane z nowymi komputerami. Możesz zdecydować, czy dane użytkownika zostaną zachowane w przypadku wykonania tej akcji dla urządzenia.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>Dodatkowe ścieżki uaktualniania systemu Windows 10 <!-- 903672 -->

Można teraz tworzyć [zasady uaktualniania wersji umożliwiające uaktualnienie urządzeń](/intune-azure/configure-devices/how-to-configure-windows-10-edition-upgrade) do następujących dodatkowych wersji systemu Windows 10:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Rejestracja zbiorcza urządzeń z systemem Windows 10 <!-- 747607 -->

Teraz możesz łączyć dużą liczbę urządzeń z aktualizacją systemu Windows 10 dla twórców z usługami Azure Active Directory oraz Intune, korzystając z aplikacji Windows Configuration Designer (WCD). Aby włączyć [zbiorcze rejestrowanie w usłudze MDM](/intune-azure/enroll-devices/bulk-enroll-windows) dla dzierżawy usługi Azure AD, utwórz pakiet aprowizacyjny, który dołącza urządzenia do dzierżawy usługi Azure AD, przy użyciu aplikacji Windows Configuration Designer, i zastosuj pakiet do firmowych urządzeń, które chcesz zarejestrować i którymi chcesz zarządzać w sposób zbiorczy. Po zastosowaniu pakietu urządzenia dołączają do usługi Azure AD, rejestrują się w usłudze Intune i umożliwiają logowanie użytkownikom usługi Azure AD.  Użytkownicy usługi Azure AD są standardowymi użytkownikami tych urządzeń i otrzymują przypisane zasady oraz wymagane aplikacje. Scenariusze samoobsługowe i scenariusze użycia witryny internetowej Portal firmy nie są w tej chwili obsługiwane.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----581122-736644---"></a>Nowe ustawienia MAM dla numerów PIN i zarządzanych lokalizacji przechowywania <!-- 581122, 736644 -->

Obecnie są dostępne dwa nowe ustawienia aplikacji, które pomagają w zarządzaniu aplikacjami mobilnymi (MAM):

- **Wyłącz numer PIN aplikacji, jeśli numer PIN urządzenia jest zarządzany** — wykrywa, czy numer PIN urządzenia jest obecny na zarejestrowanym urządzeniu; jeśli tak jest, pomija numer PIN aplikacji wyzwalany przez zasady ochrony aplikacji. Ustawienie to umożliwia zredukowanie liczby monitów o numer PIN wyświetlanych dla użytkowników podczas otwierania na zarejestrowanym urządzeniu aplikacji z włączonym zarządzaniem aplikacjami mobilnymi. Funkcja ta jest dostępna dla systemów Android i iOS.

- **Wybierz, w których usługach magazynu można zapisywać dane firmowe** — umożliwia określenie lokalizacji przechowywania, w której należy zapisywać dane firmowe. Użytkownicy mogą zapisywać w wybranych usługach służących do zarządzania lokalizacjami przechowywania. Oznacza to, że wszystkie inne usługi zarządzające lokalizacjami przechowywania, które nie znajdą się na liście, zostaną zablokowane.

  Lista obsługiwanych usług zarządzających lokalizacjami przechowywania:

  - OneDrive
  - Business SharePoint Online
  - Magazyn lokalny

### <a name="help-desk-troubleshooting-portal----907448---"></a>Portal pomocy technicznej służący do rozwiązywania problemów <!-- 907448 -->

Nowy [portal służący do rozwiązywania problemów](/intune-azure/manage-users/help-desk) umożliwia operatorom pomocy technicznej i administratorom usługi Intune wyświetlać użytkowników i ich urządzenia oraz wykonywać zadania mające na celu rozwiązywanie problemów technicznych związanych z usługą Intune.

## <a name="march-2017"></a>Marzec 2017

### <a name="support-for-ios-lost-mode---431695--"></a>Obsługa trybu utraty w systemie iOS<!--431695-->

Dla urządzeń z systemem iOS w wersji 9.3 i późniejszych w usłudze Intune dodano obsługę **trybu utraty**. Teraz możesz zablokować urządzenie, aby uniemożliwić jego użycie w jakikolwiek sposób, oraz wyświetlić komunikat i numer telefonu kontaktowego na ekranie blokady urządzenia.

Użytkownik końcowy nie będzie mógł odblokować urządzenia aż do chwili, gdy administrator wyłączy tryb utraty. Po włączeniu trybu utraty można skorzystać z akcji **Zlokalizuj urządzenie**, aby wyświetlić w konsoli usługi Intune lokalizację geograficzną urządzenia na mapie.

Urządzenie musi być urządzeniem z systemem iOS, należącym do firmy, zarejestrowanym w usłudze DEP i objętym trybem nadzorowanym.

Aby uzyskać więcej informacji, zobacz artykuł [Co to jest zarządzanie urządzeniami w usłudze Microsoft Intune?](/intune-azure/manage-devices/what-is)

### <a name="improvements-to-device-actions-report---677150--"></a>Ulepszenia w zakresie raportu dotyczącego akcji związanych z urządzeniami <!--677150-->

Wprowadziliśmy ulepszenia w zakresie raportu dotyczącego akcji związanych z urządzeniami w celu zwiększenia wydajności. Ponadto raport można teraz filtrować według stanu. Można na przykład filtrować raport w taki sposób, aby wyświetlić tylko te akcje związane z urządzeniem, które zostały zakończone.

### <a name="actions-for-non-compliance---730266--"></a>Akcje w przypadku niezgodności <!--730266-->

**Akcje w przypadku niezgodności** to nowa funkcja zasad zgodności, która umożliwia podejmowanie akcji na urządzeniach, które są niezgodne. Możesz określić jedną lub wiele akcji oraz przedział czasu, w którym te akcje muszą zostać wykonane. Na przykład możesz za pomocą poczty e-mail powiadomić użytkowników niezgodnych urządzeń, gdy tylko ich urządzenia staną się niezgodne, lub za pośrednictwem dostępu warunkowego zablokować niezgodnym urządzeniom dostęp do zasobów firmowych po 3-dniowym okresie karencji.

### <a name="custom-app-categories---748805--"></a>Niestandardowe kategorie aplikacji <!--748805-->

Możesz teraz tworzyć, edytować i przypisywać kategorie dla aplikacji dodawanych do usługi Intune. Obecnie kategorie można określać tylko w języku angielskim.
Zobacz [Jak dodać aplikację do usługi Intune](/intune-azure/manage-apps/add-apps).

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

Na kontach usługi Intune utworzonych po styczniu 2017 roku włączono bezpośredni dostęp do scenariuszy rejestracji firmy Apple przy użyciu obciążenia Rejestruj urządzenia w portalu Azure w wersji zapoznawczej. Wcześniej podgląd rejestracji firmy Apple był dostępny tylko z poziomu linków w klasycznym portalu Intune. Konta usługi Intune utworzone przed styczniem 2017 będą wymagać przeprowadzenia jednorazowej migracji, zanim funkcje te będą dostępne w systemie Azure. Harmonogram migracji nie został jeszcze ogłoszony, ale szczegółowe informacje zostaną udostępnione najszybciej, jak będzie to możliwe. Zdecydowanie zalecamy utworzenie konta w wersji próbnej w celu przetestowania nowego środowiska pracy w przypadku, gdy istniejące konto nie ma dostępu do podglądu.


## <a name="february-2017"></a>Luty 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Możliwość ograniczenia rejestracji urządzeń przenośnych <!--747600, 795782-->
Usługa Intune dodaje nowe ograniczenia rejestracji, które pozwalają kontrolować, które platformy urządzeń przenośnych mogą być rejestrowane. Usługa Intune dzieli platformy urządzeń przenośnych na iOS, macOS, Android, Windows i Windows Mobile.

* Ograniczanie rejestracji urządzeń przenośnych nie ogranicza rejestracji klientów komputerów stacjonarnych.  
* Tylko w przypadku systemu iOS i Android istnieje dodatkowa opcja blokowania rejestracji urządzeń, które są własnością osobistą.

Intune oznacza wszystkie nowe urządzenia jako osobiste, chyba że administrator IT oznaczy je jako własność firmową, zgodnie z opisem [w tym artykule](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).

### <a name="view-all-actions-on-managed-devices---677150--"></a>Wyświetlanie wszystkich akcji na urządzeniach zarządzanych <!--677150-->
Nowy raport __Akcje urządzenia__ pokazuje, kto wykonał akcje zdalne, takie jak przywrócenie stanu fabrycznego na urządzeniach, a ponadto wyświetla stan takich akcji. Zobacz [Co to jest zarządzanie urządzeniami?](https://docs.microsoft.com/intune-azure/manage-devices/what-is).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Urządzenia niezarządzane mają dostęp do przypisanych aplikacji <!--664691-->
W ramach zmian wyglądu witryny internetowej Portal firmy użytkownicy systemów iOS i Android będą mogli instalować na swoich urządzeniach niezarządzanych aplikacje przypisane im jako „dostępne bez rejestracji”. Przy użyciu poświadczeń usługi Intune użytkownicy mogą zalogować się do witryny internetowej Portal firmy i wyświetlić listę przypisanych im aplikacji. Pakiety aplikacji oznaczonych jako „dostępne bez rejestracji” są udostępniane do pobrania za pośrednictwem witryny internetowej Portal firmy. Ta zmiana nie ma wpływu na aplikacje, które wymagają rejestracji na potrzeby instalacji, ponieważ użytkownicy, którzy zechcą zainstalować te aplikacje, zobaczą monit o zarejestrowanie ich urządzenia.

### <a name="custom-app-categories---748805--"></a>Niestandardowe kategorie aplikacji <!--748805-->
Możesz teraz tworzyć, edytować i przypisywać kategorie dla aplikacji dodawanych do usługi Intune. Obecnie kategorie można określać tylko w języku angielskim.
Zobacz [Jak dodać aplikację do usługi Intune](/intune-azure/manage-apps/add-apps).

### <a name="display-device-categories---814654--"></a>Wyświetlanie kategorii urządzeń <!--814654-->
Kategorię urządzenia można teraz wyświetlić jako kolumnę na liście urządzeń. Można także edytować kategorię z poziomu sekcji właściwości w bloku właściwości urządzenia. Zobacz [Jak dodać aplikację do usługi Intune](/intune-azure/manage-apps/add-apps).

### <a name="configure-windows-update-for-business-settings---776716--"></a>Konfigurowanie ustawień usługi Windows Update dla firm<!--776716-->

Windows jako usługa to nowy sposób udostępniania aktualizacji dla systemu Windows 10. Począwszy od systemu Windows 10, wszystkie nowe funkcjonalne i jakościowe aktualizacje będą obejmować zawartość wszystkich poprzednich aktualizacji. Oznacza to, że po zainstalowaniu najnowszej aktualizacji masz pewność, iż urządzenia systemu Windows 10 są całkowicie aktualne. W odróżnieniu od wcześniejszych wersji systemu Windows teraz musisz zainstalować całą aktualizację, a nie tylko jej część.

Za pomocą usługi Windows Update dla firm można uprościć zarządzanie aktualizacjami, dzięki czemu nie trzeba zatwierdzać poszczególnych aktualizacji dla grup urządzeń. Nadal możesz zarządzać ryzykiem w swoich środowiskach, konfigurując strategię wdrażania aktualizacji, dzięki czemu usługa Windows Update zagwarantuje zainstalowanie aktualizacji w odpowiednim czasie. Usługa Microsoft Intune zapewnia możliwość konfigurowania ustawień aktualizacji na urządzeniach oraz odroczenia instalacji aktualizacji. Usługa Intune nie przechowuje aktualizacji, a jedynie przypisanie zasad aktualizacji. W celu aktualizacji urządzenia uzyskują dostęp bezpośrednio do witryny Windows Update. Użyj usługi Intune do konfigurowania **pierścieni aktualizacji systemu Windows 10** i zarządzania nimi. Pierścień aktualizacji zawiera grupę ustawień, które konfigurują, kiedy i w jaki sposób aktualizacje systemu Windows 10 mają zostać zainstalowane. Aby uzyskać szczegółowe informacje, zobacz sekcję [Konfigurowanie ustawień usługi Windows Update dla firm](/intune-azure/configure-devices/how-to-configure-windows-update-for-business).

## <a name="january-2017"></a>Styczeń 2017

### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--"></a>Przypisywanie aplikacji biznesowych niezależnie od tego, czy urządzenia są zarejestrowane <!--748823-->
Możesz teraz przypisywać użytkownikom aplikacje biznesowe ze sklepu niezależnie od tego, czy ich urządzenia są zarejestrowane w usłudze Intune. Jeśli urządzenie użytkownika nie jest zarejestrowane w usłudze Intune, aby ją zainstalować, użytkownik musi przejść do witryny sieci Web Portal firmy, a nie do aplikacji Portal firmy. Zobacz [Co to jest zarządzanie aplikacjami](/intune-azure/manage-apps/what-is-app-management).

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Rozwiązywanie problemów związanych z brakiem aktywności urządzeń z systemem iOS lub z brakiem możliwości komunikacji pomiędzy nimi a konsolą administracyjną
Gdy urządzenia użytkowników utracą połączenie z usługą Intune, można wykonać w odniesieniu do nich nowe kroki mające na celu rozwiązanie problemów w celu przywrócenia dostępu do zasobów firmy. Zobacz temat [Urządzenia są nieaktywne lub nie jest możliwe nawiązanie łączności między nimi a konsolą administracyjną](/intune-azure/enroll-devices/troubleshoot-device-enrollment#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="december-2016-initial-release"></a>Grudzień 2016 (wersja początkowa)

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integracja zarządzania kosztami telekomunikacyjnymi w publicznej wersji zapoznawczej witryny Azure Portal<!--747605-->
Obecnie rozpoczynamy pracę nad wersją zapoznawczą integracji z usługami zarządzania kosztami telekomunikacyjnymi innych firm w witrynie Azure Portal. Usługa Intune może być używana do wymuszania limitów użycia danych w kraju i w roamingu. Te operacje integracji rozpoczynamy od współpracy z firmą [Saaswedo](http://www.saaswedo.com). Aby włączyć tę funkcję w dzierżawie w wersji próbnej, [skontaktuj się z pomocą techniczną firmy Microsoft](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

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

