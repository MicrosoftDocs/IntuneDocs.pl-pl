---
title: Wersja wczesna | Microsoft Docs
description: 
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 04/25/2017
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
ms.sourcegitcommit: 5f172290d493717308446c4f9e2313a03ba8f3aa
ms.openlocfilehash: d7f25657fc7cfb9298809f76f198810718e58c39
ms.contentlocale: pl-pl
ms.lasthandoff: 04/27/2017


---


# <a name="the-early-edition-for-microsoft-intune---april-2017"></a>Wersja wczesna usługi Microsoft Intune — kwiecień 2017

**Wersja wczesna** zawiera listę funkcji, które zostaną wprowadzone w przyszłych wersjach usługi Microsoft Intune. Te informacje są przekazywane pod rygorem umowy NDA w bardzo ograniczonym zakresie i mogą ulec zmianie. Niektóre funkcje wymienione w tym miejscu mogą nie być wdrożone na czas i zostać opóźnione do przyszłych wersji. Inne funkcje są testowane w wersji pilotażowej, aby zapewnić przygotowanie ich do użytku przez klientów. W przypadku pytań lub wątpliwości skontaktuj się ze swoim partnerem ds. usługi Intune/PM.

Ta strona jest okresowo aktualizowana. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.

> [!Note]
> Dla usługi Intune opracowywane są następujące zmiany. Wszystkie te funkcje będą również w przyszłości obsługiwane dla hybrydowych wdrożeń klientów (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nowe możliwości

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Ulepszono stan instalacji aplikacji Portal firmy dla systemu Windows 10 <!--676495-->

Aplikacja Portal firmy systemu Windows 10 będzie teraz zapewniać pasek postępu instalacji dla wszystkich instalacji nowoczesnych aplikacji rozpoczętych z witryny Portal firmy. Nowe komunikaty o stanie pokazywane w aplikacji Portal firmy dla systemu Windows 10 można znaleźć na [stronie dotyczącej nowości w interfejsie użytkownika aplikacji usługi Intune](whats-new-in-intune-app-ui.md).

### <a name="improved-status-messaging-in-the-company-portal-app-for-ios---744866--"></a>Ulepszono komunikaty o stanie w aplikacji Portal firmy dla systemu iOS <!--744866-->

Nowe, bardziej szczegółowe komunikaty o błędach będą teraz wyświetlane w aplikacji Portal firmy dla systemu iOS, aby zapewnić bardziej dostępne informacje o tym, co dzieje się na urządzeniach. Poprzednio te przypadki błędów były uwzględniane w ogólnym komunikacie o błędzie o tytule „Portal firmy jest tymczasowo niedostępny”. Ponadto, jeśli użytkownik uruchamia aplikację Portal firmy w systemie iOS, gdy nie ma połączenia internetowego, zobaczy teraz stały pasek stanu na stronie głównej z komunikatem „Brak połączenia internetowego”.

### <a name="myapps-available-for-managed-browser---822308-822303--"></a>Usługa MyApps dostępna dla przeglądarki Managed Browser <!--822308, 822303-->

Usługa Microsoft MyApps ma teraz lepsze wsparcie w ramach przeglądarki Managed Browser. Użytkownicy przeglądarki Managed Browser, którzy nie są przeznaczeni do zarządzania, zostaną przeniesieni bezpośrednio do usługi MyApps, w której będą mogli uzyskać dostęp do aprowizowanych przez administratora aplikacji SaaS. Użytkownicy, którzy są przeznaczeni do zarządzania w usłudze Intune, nadal będą mogli uzyskiwać dostęp do usługi MyApps z wbudowanej zakładki przeglądarki Managed Browser.

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Nowe ikony przeglądarki Managed Browser i aplikacji Portal firmy <!--918433, 918431-->

Przeglądarka Managed Browser otrzymuje zaktualizowane ikony aplikacji dla systemów Android i iOS. Nowa ikona będzie zawierać zaktualizowany identyfikator Intune, dzięki czemu będzie bardziej spójna z innymi aplikacjami w rozwiązaniu Enterprise Mobility + Security (EM+S). Nowa ikona programu Managed Browser jest widoczna na [stronie dotyczącej nowości w interfejsie użytkownika aplikacji usługi Intune](whats-new-in-intune-app-ui.md).

Portal firmy również otrzymuje zaktualizowane ikony aplikacji dla systemów Android, iOS i Windows, aby poprawić spójność z innymi aplikacjami w rozwiązaniu EM+S. Ikony te będą stopniowo wydawane na różnych platformach od kwietnia do końca maja.

### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>Obsługa logowania jednokrotnego z aplikacji Portal firmy dla systemu iOS do programu Outlook dla systemu iOS <!--834012-->

Użytkownicy nie muszą już logować się w aplikacji Outlook, jeśli zalogowali się na tym samym urządzeniu do aplikacji Portal firmy dla systemu iOS przy użyciu tego samego konta. Gdy użytkownicy uruchamiają aplikację Outlook, mogą wybrać swoje konto i zalogować się automatycznie. Ponadto pracujemy nad dodaniem tej funkcji do innych aplikacji firmy Microsoft.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Wskaźnik postępu logowania w aplikacji Portal firmy dla systemu Android <!--953374-->

Aktualizacja aplikacji Portal firmy dla systemu Android pokazuje wskaźnik postępu logowania, gdy użytkownik uruchomi lub wznowi działanie aplikacji. Wskaźnik przechodzi przez nowe stany, od „Trwa łączenie...” przez „Trwa logowanie...” do „Trwa sprawdzanie wymagań dotyczących bezpieczeństwa...”, zanim zezwoli użytkownikowi na dostęp do aplikacji. Nowe ekrany aplikacji Portal firmy dla systemu Android są widoczne na [stronie dotyczącej nowości w interfejsie użytkownika aplikacji usługi Intune](whats-new-in-intune-app-ui.md).


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

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?

Zmiany nie wpływają na żadne istniejące wdrożenia w urządzeniach zarządzanych za pośrednictwem komputerowego agenta usługi Intune. Niemniej po migracji nie będzie można wdrażać tych migrowanych pakietów AppX na żadnych nowych urządzeniach zarządzanych za pośrednictwem komputerowego agenta usługi Intune, które nie zostały wcześniej ustawione jako urządzenia docelowe.

#### <a name="what-action-do-i-need-to-take"></a>Jakie działania muszę podjąć?

Po migracji należy ponownie przekazać pakiet AppX jako komputerowy pakiet AppX, jeśli chcesz przeprowadzać nowe wdrożenia na komputerach. Aby dowiedzieć się więcej, zobacz [Appx changes in Intune on Azure](https://aka.ms/appxchange) (Zmiany w pakietach AppX w usłudze Intune na platformie Azure) na blogu zespołu pomocy technicznej usługi Intune.  


## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Publiczna wersja zapoznawcza nowego środowiska administracyjnego usługi Intune na platformie Azure <!--736542-->

Na początku roku 2017 r. będziemy migrować nasze pełne środowisko administracyjne na platformę Azure, co umożliwi zaawansowane i zintegrowane zarządzanie podstawowymi przepływami pracy EMS na nowoczesnej platformie usług, którą można rozszerzyć za pomocą interfejsów API programu Graph.

Publiczna wersja zapoznawcza nowego środowiska administracyjnego będzie widoczna w nowych dzierżawach w wersji próbnej w witrynie Azure Portal w tym miesiącu. W wersji zapoznawczej możliwości istniejącej konsoli usługi Intune i spójność z nią będą udostępniane w sposób iteracyjny.

W środowisku administracyjnym w witrynie Azure Portal będzie używana już zapowiadana nowa funkcja grupowania i określania celu. W przypadku migrowania istniejącej dzierżawy do nowego środowiska grupowania nastąpi również migracja do nowego środowiska administracyjnego w wersji zapoznawczej w dzierżawie. Jeśli przed zakończeniem migrowania dzierżawy chcesz przetestować lub poznać dowolną nową funkcję, utwórz nowe konto wersji próbnej usługi Intune lub zapoznaj się z [nową dokumentacją](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Obsługa opcji zarządzanych konfiguracji dla aplikacji systemu Android <!-- 621621 -->

Za pośrednictwem usługi Intune można skonfigurować aplikacje dla systemu Android w sklepie Play, które obsługują opcje zarządzanych konfiguracji.  Ta funkcja umożliwia pracownikom działu IT wyświetlanie listy wartości konfiguracji obsługiwanych przez aplikację oraz zapewnia najwyższej klasy interfejs użytkownika z przewodnikiem, dzięki któremu można skonfigurować te wartości.

### <a name="remote-assistance-for-android-devices----675418---"></a>Pomoc zdalna dla urządzeń z systemem Android <!-- 675418 -->

Usługa Intune będzie korzystać z zakupionego osobno oprogramowania [TeamViewer](https://www.teamviewer.com), aby umożliwić oferowanie pomocy zdalnej użytkownikom urządzeń z systemem Android.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Nowe zasady dla systemu Android dotyczące złożonych numerów PIN <!-- 722069 -->

Możesz ustawić wymagany typ hasła na „złożony numeryczny” w profilu urządzenia z systemem Android w przypadku urządzeń z systemem Android 5.0 lub nowszym.  Użyj tego ustawienia, aby uniemożliwić użytkownikom tworzenie numerów PIN zawierających powtarzające się lub kolejne liczby, np. 1111 lub 1234.

### <a name="additional-support-for-android-for-work-devices"></a>Dodatkowa obsługa urządzeń z programem Android for Work

- **Zarządzaj ustawieniami hasła i profilu służbowego** <!-- 612808 -->

  Dodaliśmy nowe zasady ograniczeń dla urządzeń z programem Android for Work, które umożliwiają zarządzanie ustawieniami hasła i profilu służbowego na zarządzanych urządzeniach z programem Android for Work.

- **Zezwalaj na współużytkowanie danych między profilem służbowym i osobistym** <!-- 1045102 -->

  Zaktualizowaliśmy ustawienie **Udostępnianie danych między profilami służbowym i osobistym** w profilu ograniczeń dla urządzeń z programem Android for Work o nowe opcje, które pomagają w konfigurowaniu udostępniania danych między profilami służbowymi i osobistymi.

- **Ogranicz kopiowanie i wklejanie między profilami służbowymi i osobistymi** <!-- 1046094 -->

  W przypadku zarządzania urządzeniami z programem Android for Work za pomocą usługi Intune kopiowanie i wklejanie między aplikacjami służbowymi i osobistymi jest dozwolone. Teraz dodaliśmy niestandardowy profil urządzenia dla urządzeń z programem Android for Work, który umożliwia ograniczenie kopiowania i wklejania między aplikacjami służbowymi i osobistymi.

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>Przypisuj aplikacje LOB do urządzeń z systemem iOS lub Android <!-- 1057568 -->

Możesz przypisywać różne aplikacje biznesowe dla systemu iOS (pliki ipa) lub Android (pliki apk) do użytkowników lub urządzeń.

###  <a name="new-policies-for-ios-devices----723774-723815-723826-723830-723832---"></a>Nowe zasady dla urządzeń z systemem iOS <!-- 723774, 723815, 723826, 723830, 723832 -->

- **Aplikacje na ekranie głównym** — możesz użyć zasad urządzenia do kontrolowania aplikacji, które użytkownik może zobaczyć na ekranie głównym swojego urządzenia z systemem iOS. Zasady te zmieniają układ ekranu głównego, ale nie wdrażają żadnych określonych aplikacji, które nie zostały zainstalowane.

- **Połączenia z urządzeniami AirPrint** — możesz użyć zasad urządzenia usługi Intune do kontrolowania urządzeń AirPrint (drukarek sieciowych), z którymi użytkownicy końcowi urządzeń z systemem iOS będą mogli nawiązywać połączenie.

- **Połączenia z urządzeniami AirPlay** — możesz użyć zasad urządzenia usługi Intune do kontrolowania urządzeń AirPlay (np. Apple TV), z którymi użytkownicy końcowi urządzeń z systemem iOS będą mogli nawiązywać połączenie.

- **Niestandardowy komunikat ekranu blokady** — możesz skonfigurować niestandardowy komunikat, który użytkownicy zobaczą na ekranie blokady urządzenia z systemem iOS, zastępując domyślny komunikat ekranu blokady.

- **Filtr zawartości sieci Web** — możesz kontrolować witryny sieci Web, które użytkownicy urządzeń z systemem iOS mogą odwiedzać, korzystając z jednej z następujących dwóch metod:

  - Dodaj dozwolone i zablokowane adresy URL przy użyciu wbudowanych filtrów zawartości sieci Web w urządzeniach firmy Apple.
  - Zezwalaj tylko na dostęp do określonych witryn sieci Web za pośrednictwem przeglądarki Safari. Dla każdej określonej witryny zostanie utworzona zakładka w przeglądarce Safari.


### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>Ogranicz powiadomienia wypychane dla aplikacji systemu iOS <!-- 723767 -->

W profilu ograniczeń urządzenia w usłudze Intune możesz skonfigurować następujące ustawienia powiadomień dla urządzeń z systemem iOS:

- W pełni włączyć lub wyłączyć powiadomienia dla określonej aplikacji.
- Włączyć lub wyłączyć powiadomienia w centrum powiadomień dla określonej aplikacji.
- Określić typ alertu: **Brak**, **Transparent** lub **Alert modalny**.
- Określić, czy identyfikatory są dozwolone dla tej aplikacji.
- Określić, czy dźwięki powiadomień są dozwolone.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>Skonfiguruj aplikacje systemu iOS do autonomicznego uruchamiania w trybie pojedynczej aplikacji <!-- 737837 -->

Możesz użyć profilu urządzenia w usłudze Intune do skonfigurowania urządzeń z systemem iOS, aby uruchamiać określone aplikacje w autonomicznym trybie pojedynczej aplikacji. Jeśli skonfigurowano ten tryb, a aplikacja zostanie uruchomiona, urządzenie zostanie zablokowane, aby mogło uruchamiać wyłącznie tę aplikację. Opcję tę można przykładowo wykorzystać w przypadku konfigurowania aplikacji, która umożliwia użytkownikom wykonywanie testów na urządzeniu. Po zakończeniu działań aplikacji lub usunięciu tych zasad urządzenie powraca do normalnego stanu.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>Skonfiguruj zaufane domeny dla poczty e-mail i przeglądania sieci Web na urządzeniach z systemem iOS <!-- 723765 -->

W profilu ograniczeń urządzenia z systemem iOS możesz skonfigurować następujące ustawienia domeny:

- **Nieoznaczone domeny poczty e-mail** — wiadomości e-mail wysyłane lub odbierane przez użytkownika, które nie pasują do domen określonych w tym miejscu, będą oznaczone jako niezaufane.

- **Zarządzane domeny sieci Web** — dokumenty pobierane z adresów URL określonych w tym miejscu będą uznawane za zarządzane (tylko przeglądarka Safari).  

- **Domeny automatycznego uzupełniania haseł przeglądarki Safari** — użytkownicy mogą zapisywać hasła w przeglądarce Safari tylko w przypadku adresów URL spełniających wzorce określone w tym miejscu. Aby użyć tego ustawienia, urządzenie musi być w trybie nadzorowanym i nie może być skonfigurowane dla wielu użytkowników. (iOS 9.3+)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>Aplikacje VPP dostępne w aplikacji Portal firmy dla systemu iOS <!-- 748782 -->

Możesz przypisać aplikacje dla systemu iOS zakupione zbiorczo (VPP) jako **Dostępne** instalacje do użytkowników końcowych. Użytkownicy końcowi potrzebują konta sklepu Apple Store, aby zainstalować aplikację.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>Synchronizuj książki elektroniczne ze sklepu Apple VPP Store <!-- 800878 -->

Możesz synchronizować książki zakupione w sklepie programu zakupów zbiorczych Apple przy użyciu usługi Intune i przypisywać je do użytkowników.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Zarządzanie wieloma użytkownikami w przypadku urządzeń Samsung KNOX Standard <!-- 971988 -->

Urządzenia z systemem Samsung KNOX Standard są teraz obsługiwane w przypadku zarządzania wieloma użytkownikami przez usługę Intune. Oznacza to, że użytkownicy końcowi mogą zalogować się na urządzeniu przy użyciu poświadczeń usługi Azure Active Directory lub wylogować się z niego, a urządzenie jest zarządzane centralnie niezależnie od tego, czy jest używane.  Użytkownicy końcowi po zalogowaniu otrzymują dostęp do aplikacji, a także są stosowane wobec nich zasady. Gdy użytkownicy się wylogują, wszystkie dane aplikacji są usuwane.

### <a name="additional-windows-device-restriction-settings----818566---"></a>Dodatkowe ustawienia ograniczeń urządzeń z systemem Windows <!-- 818566 -->

Dodaliśmy obsługę dodatkowych ustawień ograniczeń urządzeń z systemem Windows, np. dodatkową obsługę przeglądarki Edge, dostosowywanie ekranu blokady na urządzeniu, dostosowanie menu Start, tapetę zestawu wyszukiwania W centrum uwagi Windows oraz ustawienia serwera proxy.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Obsługa wielu użytkowników w aktualizacji Windows 10 Creators Update <!-- 822547 -->

Dodaliśmy obsługę zarządzania wieloma użytkownikami na urządzeniach z aktualizacją systemu Windows 10 dla twórców, które zostały dołączone do domeny usługi Azure Active Directory. Oznacza to, że różni użytkownicy standardowi po zalogowaniu się do urządzenia przy użyciu poświadczeń usługi Azure AD otrzymują wszelkie aplikacje i zasady, które zostały przypisane do ich nazw użytkowników. Obecnie użytkownicy nie mogą używać witryny internetowej Portal firmy na potrzeby samoobsługowych scenariuszy, takich jak instalowanie aplikacji.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Świeży początek dla komputerów z systemem Windows 10<!-- 1004830 -->

W tej wersji dodaliśmy nową akcję odświeżonego uruchomienia dla komputerów z systemem Windows 10.  Po wykonaniu tej akcji wszelkie aplikacje zainstalowane na komputerze zostaną usunięte, a komputer zostanie automatycznie zaktualizowany do najnowszej wersji systemu Windows. Funkcja może być przydatna do usuwania wstępnie zainstalowanych aplikacji OEM, które są często dostarczane z nowymi komputerami. Możesz zdecydować, czy dane użytkownika zostaną zachowane w przypadku wykonania tej akcji dla urządzenia.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>Dodatkowe ścieżki uaktualniania systemu Windows 10 <!-- 903672 -->

Można teraz tworzyć zasady uaktualniania wersji umożliwiające uaktualnienie urządzeń do następujących dodatkowych wersji systemu Windows 10:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Rejestracja zbiorcza urządzeń z systemem Windows 10 <!-- 747607 -->

Możesz łączyć dużą liczbę urządzeń z aktualizacją systemu Windows 10 dla twórców z usługami Azure Active Directory oraz Intune, korzystając z aplikacji Windows Configuration Designer (WCD). Aby włączyć automatyczne rejestrowanie w usłudze MDM dla dzierżawy usługi Azure AD, utwórz pakiet aprowizacyjny, który dołącza urządzenia do dzierżawy usługi Azure AD, przy użyciu aplikacji Windows Configuration Designer, i zastosuj pakiet do firmowych urządzeń, które chcesz zarejestrować i którymi chcesz zarządzać w sposób zbiorczy. Po zastosowaniu pakietu urządzenia dołączają do usługi Azure AD, rejestrują się w usłudze Intune i umożliwiają logowanie użytkownikom usługi Azure AD.  Użytkownicy usługi Azure AD są standardowymi użytkownikami tych urządzeń i otrzymują przypisane zasady oraz wymagane aplikacje. Scenariusze samoobsługowe i scenariusze użycia witryny internetowej Portal firmy nie są w tej chwili obsługiwane.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----58112-736644---"></a>Nowe ustawienia MAM dla numerów PIN i zarządzanych lokalizacji przechowywania <!-- 58112, 736644 -->

Są dostępne dwa nowe ustawienia aplikacji, które pomagają w zarządzaniu aplikacjami mobilnymi (MAM):

- **Wyłącz numer PIN aplikacji, jeśli numer PIN urządzenia jest zarządzany** — wykrywa, czy numer PIN urządzenia jest obecny na zarejestrowanym urządzeniu; jeśli tak jest, pomija numer PIN aplikacji wyzwalany przez zasady ochrony aplikacji. Ustawienie to umożliwia zredukowanie liczby monitów o numer PIN wyświetlanych dla użytkowników podczas otwierania na zarejestrowanym urządzeniu aplikacji z włączonym zarządzaniem aplikacjami mobilnymi. Funkcja ta jest dostępna dla systemów Android i iOS.

- **Wybierz, w których usługach magazynu można zapisywać dane firmowe** — umożliwia określenie lokalizacji przechowywania, w której należy zapisywać dane firmowe. Użytkownicy mogą zapisywać w wybranych usługach służących do zarządzania lokalizacjami przechowywania. Oznacza to, że wszystkie inne usługi zarządzające lokalizacjami przechowywania, które nie znajdą się na liście, zostaną zablokowane.

  Lista obsługiwanych usług zarządzających lokalizacjami przechowywania:

  - OneDrive
  - Business SharePoint Online
  - Magazyn lokalny


### <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new-in-microsoft-intune.md).

