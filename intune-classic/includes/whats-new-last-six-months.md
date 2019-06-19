---
ms.openlocfilehash: 984b78b271d130618ec0994f76e966f1dc338706
ms.sourcegitcommit: 4b83697de8add3b90675c576202ef2ecb49d80b2
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 06/13/2019
ms.locfileid: "67044713"
---
## <a name="april-2017"></a>Kwiecień 2017

### <a name="new-capabilities"></a>Nowe możliwości

#### <a name="myapps-available-for-managed-browser---822308-822303--"></a>Usługa MyApps dostępna dla przeglądarki Managed Browser <!--822308, 822303-->

Usługa Microsoft MyApps ma teraz lepsze wsparcie w ramach przeglądarki Managed Browser. Użytkownicy przeglądarki Managed Browser, którzy nie są przeznaczeni do zarządzania, zostaną przeniesieni bezpośrednio do usługi MyApps, w której będą mogli uzyskać dostęp do aprowizowanych przez administratora aplikacji SaaS. Użytkownicy, którzy są przeznaczeni do zarządzania w usłudze Intune, nadal będą mogli uzyskiwać dostęp do usługi MyApps z wbudowanej zakładki przeglądarki Managed Browser.

#### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431-971473--"></a>Nowe ikony przeglądarki Managed Browser i aplikacji Portal firmy <!--918433, 918431, 971473-->

Przeglądarka Managed Browser otrzymuje zaktualizowane ikony aplikacji dla systemów Android i iOS. Nowa ikona będzie zawierać zaktualizowany identyfikator Intune, dzięki czemu będzie bardziej spójna z innymi aplikacjami w rozwiązaniu Enterprise Mobility + Security (EM+S). Nowa ikona programu Managed Browser jest widoczna na [stronie dotyczącej nowości w interfejsie użytkownika aplikacji usługi Intune](/intune/whats-new-app-ui).

Portal firmy również otrzymuje zaktualizowane ikony aplikacji dla systemów Android, iOS i Windows, aby poprawić spójność z innymi aplikacjami w rozwiązaniu EM+S. Ikony te będą stopniowo wydawane na różnych platformach od kwietnia do końca maja.

#### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Wskaźnik postępu logowania w aplikacji Portal firmy dla systemu Android <!--953374-->

Aktualizacja aplikacji Portal firmy dla systemu Android pokazuje wskaźnik postępu logowania, gdy użytkownik uruchomi lub wznowi działanie aplikacji. Wskaźnik przechodzi przez nowe stany, od „Trwa łączenie...” przez „Trwa logowanie...” do „Trwa sprawdzanie wymagań dotyczących bezpieczeństwa...”, zanim zezwoli użytkownikowi na dostęp do aplikacji. Nowe ekrany aplikacji Portal firmy dla systemu Android są widoczne na [stronie dotyczącej nowości w interfejsie użytkownika aplikacji usługi Intune](/intune/whats-new-app-ui).

#### <a name="block-apps-from-accessing-sharepoint-online----679339---"></a>Blokowanie dostępu aplikacji do usługi SharePoint Online <!-- 679339 -->

Teraz możesz tworzyć zasady dostępu warunkowego na podstawie aplikacji, aby blokować dostęp do usługi [SharePoint Online](/intune-classic/deploy-use/mam-ca-for-sharepoint-online) aplikacjom, do których nie zastosowano zasad ochrony aplikacji. W tym scenariuszu dostępu warunkowego na podstawie aplikacji można określić aplikacje, które mają mieć dostęp do usługi SharePoint Online, za pomocą witryny Azure Portal.

#### <a name="single-sign-in-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>Obsługa logowania jednokrotnego z aplikacji Portal firmy dla systemu iOS do programu Outlook dla systemu iOS <!--834012-->
Użytkownicy nie muszą już logować się w aplikacji Outlook, jeśli zalogowali się na tym samym urządzeniu do aplikacji Portal firmy dla systemu iOS przy użyciu tego samego konta. Gdy użytkownicy uruchamiają aplikację Outlook, mogą wybrać swoje konto i zalogować się automatycznie. Ponadto pracujemy nad dodaniem tej funkcji do innych aplikacji firmy Microsoft.

#### <a name="improved-status-messaging-in-the-company-portal-app-for-ios---744866--"></a>Ulepszono komunikaty o stanie w aplikacji Portal firmy dla systemu iOS <!--744866-->
Nowe, bardziej szczegółowe komunikaty o błędach będą teraz wyświetlane w aplikacji Portal firmy dla systemu iOS, aby zapewnić bardziej dostępne informacje o tym, co dzieje się na urządzeniach. Poprzednio te przypadki błędów były uwzględniane w ogólnym komunikacie o błędzie o tytule „Portal firmy jest tymczasowo niedostępny”. Ponadto, jeśli użytkownik uruchamia aplikację Portal firmy w systemie iOS, gdy nie ma połączenia internetowego, zobaczy teraz stały pasek stanu na stronie głównej z komunikatem „Brak połączenia internetowego”.

#### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Ulepszono stan instalacji aplikacji Portal firmy dla systemu Windows 10 <!--676495-->

Nowe ulepszenia instalacji aplikacji uruchomionych w aplikacji Portal firmy systemu Windows 10 obejmują:
-   Szybsze raportowanie postępu instalacji pakietów MSI
-   Szybsze raportowanie postępu instalacji nowoczesnych aplikacji na urządzeniach z Rocznicową aktualizacją systemu Windows 10 lub nowszą wersją
-   Nowy pasek postępu dla instalacji nowoczesnych aplikacji na urządzeniach z Rocznicową aktualizacją systemu Windows 10 lub nowszą wersją

Nowy pasek postępu jest zaprezentowany na [stronie dotyczącej nowości w interfejsie użytkownika aplikacji usługi Intune](/intune/whats-new-app-ui).

#### <a name="bulk-enroll-windows-10-devices----747607---"></a>Rejestracja zbiorcza urządzeń z systemem Windows 10 <!-- 747607 -->

Teraz możesz łączyć dużą liczbę urządzeń z aktualizacją systemu Windows 10 dla twórców z usługami Azure Active Directory oraz Intune, korzystając z aplikacji Windows Configuration Designer (WCD). Aby włączyć [zbiorcze rejestrowanie w usłudze MDM](/intune-classic/deploy-use/bulk-enroll-windows) dla dzierżawy usługi Azure AD, utwórz pakiet aprowizacyjny, który dołącza urządzenia do dzierżawy usługi Azure AD, przy użyciu aplikacji Windows Configuration Designer, i zastosuj pakiet do firmowych urządzeń, które chcesz zarejestrować i którymi chcesz zarządzać w sposób zbiorczy. Po zastosowaniu pakietu urządzenia dołączają do usługi Azure AD, rejestrują się w usłudze Intune i umożliwiają logowanie użytkownikom usługi Azure AD.  Użytkownicy usługi Azure AD są standardowymi użytkownikami tych urządzeń i otrzymują przypisane zasady oraz wymagane aplikacje. Scenariusze samoobsługowe i scenariusze użycia witryny internetowej Portal firmy nie są w tej chwili obsługiwane.

### <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Nowości w publicznej wersji zapoznawczej środowiska administracyjnego usługi Intune na platformie Azure <!--736542-->

Na początku roku 2017 r. będziemy migrować nasze pełne środowisko administracyjne na platformę Azure, co umożliwi zaawansowane i zintegrowane zarządzanie podstawowymi przepływami pracy EMS na nowoczesnej platformie usług, którą można rozszerzyć za pomocą interfejsów API programu Graph.

Publiczna wersja zapoznawcza nowego środowiska administracyjnego będzie widoczna w nowych dzierżawach w wersji próbnej w witrynie Azure Portal w tym miesiącu. W wersji zapoznawczej możliwości istniejącej konsoli usługi Intune i spójność z nią będą udostępniane w sposób iteracyjny.

W środowisku administracyjnym w witrynie Azure Portal będzie używana już zapowiadana nowa funkcja grupowania i określania celu. W przypadku migrowania istniejącej dzierżawy do nowego środowiska grupowania nastąpi również migracja do nowego środowiska administracyjnego w wersji zapoznawczej w dzierżawie. Jeśli przed zakończeniem migrowania dzierżawy chcesz przetestować lub poznać dowolną nową funkcję, utwórz nowe konto wersji próbnej usługi Intune lub zapoznaj się z [nową dokumentacją](/intune/whats-new).

Informacje na temat nowości w wersji zapoznawczej usługi Intune na platformie Azure znajdziesz [tutaj](/intune/whats-new).

### <a name="notices"></a>Uwagi

#### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Bezpośredni dostęp do scenariuszy rejestracji firmy Apple <!--951869-->

Na kontach usługi Intune utworzonych po styczniu 2017 roku włączono bezpośredni dostęp do scenariuszy rejestracji firmy Apple przy użyciu obciążenia Rejestruj urządzenia w portalu Azure w wersji zapoznawczej. Wcześniej podgląd rejestracji firmy Apple był dostępny tylko z poziomu linków w klasycznym portalu Intune. Konta usługi Intune utworzone przed styczniem 2017 będą wymagać przeprowadzenia jednorazowej migracji, zanim funkcje te będą dostępne w systemie Azure. Harmonogram migracji nie został jeszcze ogłoszony, ale szczegółowe informacje zostaną udostępnione najszybciej, jak będzie to możliwe. Zdecydowanie zalecamy utworzenie konta w wersji próbnej w celu przetestowania nowego środowiska pracy w przypadku, gdy istniejące konto nie ma dostępu do podglądu.

#### <a name="whats-coming-for-appx-in-intune-in-the-azure-portal----1000270---"></a>Elementy dostępne wkrótce dla pakietu Appx w usłudze Intune w witrynie Azure Portal <!-- 1000270 -->

W ramach migracji do usługi Intune w witrynie Azure Portal wprowadzamy następujące zmiany w pakiecie AppX:

1. Dodanie nowego typu aplikacji pakietu AppX w klasycznej konsoli usługi Intune, który można wdrożyć tylko do urządzeń zarejestrowanych w usłudze MDM.
2. Zmiana przeznaczenia istniejącego typu aplikacji pakietu AppX celem nakierowania wyłącznie na komputery zarządzanie za pośrednictwem komputerowego agenta usługi Intune.
3. Skonwertowanie wszystkich istniejących pakietów AppX do pakietów AppX usługi MDM w ramach migracji.

##### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?

Zmiany nie wpływają na żadne istniejące wdrożenia w urządzeniach zarządzanych za pośrednictwem komputerowego agenta usługi Intune. Niemniej po migracji nie będzie można wdrażać tych migrowanych pakietów AppX na żadnych nowych urządzeniach zarządzanych za pośrednictwem komputerowego agenta usługi Intune, które nie zostały wcześniej ustawione jako urządzenia docelowe.

##### <a name="what-action-do-i-need-to-take"></a>Jakie działania muszę podjąć?

Po migracji należy ponownie przekazać pakiet AppX jako komputerowy pakiet AppX, jeśli chcesz przeprowadzać nowe wdrożenia na komputerach. Aby dowiedzieć się więcej, zobacz wpis [Appx changes in Intune in the Azure portal](https://aka.ms/appxchange) (Zmiany w pakietach AppX w usłudze Intune w witrynie Azure Portal) na blogu zespołu pomocy technicznej usługi Intune.  

#### <a name="administration-roles-being-replaced-in-azure-portal"></a>Zastąpienie ról administracyjnych w witrynie Azure Portal

Istniejące role administracyjne zarządzania aplikacjami mobilnymi (MAM) (współautor, właściciel, tylko do odczytu) używane w portalu klasycznym Intune (Silverlight) są zastępowane pełnym zestawem nowych kontroli administracyjnych opartych na rolach (RBAC) w witrynie Intune Azure Portal. Po migracji do witryny Azure Portal należy ponownie przypisać administratorów do nowych ról administracyjnych. Aby uzyskać więcej informacji na temat kontroli dostępu opartej na rolach (RBAC) i nowych ról, zobacz [Kontrola dostępu oparta na rolach w usłudze Microsoft Intune](/intune/role-based-access-control).

### <a name="whats-coming"></a>Wkrótce

#### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Ulepszone środowisko logowania w aplikacjach Portalu firmy dla wszystkich platform <!--User Story 1132123-->

Informujemy o zmianie, która zostanie wprowadzona w ciągu następnych kilku miesięcy i ułatwi logowanie w aplikacjach Portalu firmy w usłudze Intune dla systemów Android, iOS i Windows. Nowe środowisko użytkownika zostanie udostępnione automatycznie na wszystkich platformach aplikacji Portal firmy, gdy zmiana ta zostanie wprowadzona w usłudze Azure AD. Ponadto użytkownicy mogą teraz logować się do Portalu firmy za pomocą innego urządzenia, korzystając z wygenerowanego kodu jednorazowego. Ta opcja jest szczególnie przydatna w sytuacji, gdy niezbędne jest zalogowanie się bez użycia poświadczeń.

Zrzuty ekranu przedstawiające poprzednie środowisko logowania, nowe środowisko logowania z poświadczeniami oraz nowe środowisko logowania za pomocą innego urządzenia można znaleźć na stronie [Co nowego w interfejsie aplikacji](/intune/whats-new-app-ui).

#### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Planowane zmiany: zmiany w usłudze Intune dotyczące witryny Intune Partner Portal <!-- 1050016 -->

Wraz z aktualizacją usługi w połowie maja 2017 r. strona Intune Partner zostanie usunięta z witryny manage.microsoft.com.  

Administratorzy partnerów nie będą już mogli wyświetlać strony Intune Partner ani podejmować na niej działań w imieniu swoich klientów. Zamiast tego konieczne będzie zalogowanie się w jednym z dwóch innych portali firmy Microsoft dla partnerów.

Logowanie się na zarządzane konta klientów będzie możliwe zarówno w [Centrum partnerskim firmy Microsoft](https://partnercenter.microsoft.com/), jak i w [Centrum administracyjnym usługi Microsoft 365](https://admin.microsoft.com/). Aby kontynuować czynności partnerskie, należy korzystać z dowolnej z tych witryn do zarządzania klientami.


#### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Firma Apple będzie wymagać aktualizacji mechanizmu Application Transport Security <!--748318-->

Firma Apple ogłosiła, że będzie egzekwować pewne wymagania dotyczące mechanizmu Application Transport Security (ATS). Mechanizm ATS służy do wymuszania mocniejszych zabezpieczeń całej komunikacji aplikacji za pośrednictwem protokołu HTTPS. Ta zmiana wpływa na klientów usługi Intune korzystających z aplikacji Portalu firmy w systemie iOS.

Udostępniliśmy wersję aplikacji Portal firmy dla systemu iOS przy użyciu programu Apple TestFlight, który wymusza nowe wymagania ATS. Jeśli chcesz ją wypróbować, aby sprawdzić swoją zgodność z ATS, wyślij na adres e-mail <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> wiadomość ze swoim imieniem i nazwiskiem, adresem e-mail i nazwą firmy. Zapoznaj się z naszym [blogiem pomocy technicznej usługi Intune](https://aka.ms/compportalats), aby uzyskać więcej szczegółów.

## <a name="march-2017"></a>Marzec 2017

### <a name="new-capabilities"></a>Nowe możliwości

#### <a name="support-for-skycure"></a>Obsługa aplikacji Skycure

Dostęp urządzeń mobilnych do zasobów firmy można obecnie kontrolować z użyciem dostępu warunkowego na podstawie ocenie ryzyka przeprowadzanej przez aplikację Skycure. Jest to rozwiązanie chroniące przed zagrożeniami bezpieczeństwa urządzeń mobilnych zintegrowane z usługą Microsoft Intune. Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń z uruchomioną usługą Skycure. Są to na przykład:

- Ochrona fizyczna
- Ochrona sieciowa
- Ochrona aplikacji
- Ochrona przed lukami w zabezpieczeniach

Zasady dostępu warunkowego usług EMS można skonfigurować na podstawie oceny ryzyka przeprowadzonej przez aplikację Skycure włączaną przy użyciu zasad zgodności urządzeń usługi Intune. Przy użyciu tych zasad można zezwalać na dostęp do zasobów firmowych lub blokować go niezgodnym urządzeniom w oparciu o wykryte zagrożenia. Aby uzyskać więcej informacji, zobacz [Łącznik Skycure Mobile Threat Defense](/intune-classic/deploy-use/skycure-mobile-threat-defense-connector).

#### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nowe środowisko użytkownika aplikacji Portal firmy dla systemu Android <!--621622-->

Interfejs użytkownika aplikacji Portal firmy dla systemu Android zostanie zaktualizowany w celu zapewnienia bardziej nowoczesnego wyglądu i działania oraz udoskonalenia środowiska pracy. Znaczące zmiany:

- Kolory: nagłówki kart w aplikacji Portal firmy mają kolor wybrany przez zespół IT.
- Aplikacje: na karcie **Aplikacje** zaktualizowano przyciski **Polecane aplikacje** i **Wszystkie aplikacje**.
- Wyszukiwanie: przycisk **Wyszukaj** na karcie **Aplikacje** jest teraz przestawnym przyciskiem akcji.
- Poruszanie się w obrębie aplikacji: w widoku **Wszystkie aplikacje** jest dostępny widok z kartami **Polecane**, **Wszystkie** i **Kategorie**, które ułatwiają nawigację.
- Pomoc techniczna: zaktualizowano karty **Moje urządzenia** i **Kontakt z działem IT** w celu poprawy czytelności.

Aby uzyskać więcej informacji o tych zmianach, zobacz artykuł [Aktualizacje interfejsu użytkownika dla aplikacji użytkownika końcowego usługi Intune](/intune/whats-new-app-ui).

#### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Urządzenia niezarządzane mają dostęp do przypisanych aplikacji <!--664691-->

W ramach zmian wyglądu witryny internetowej Portal firmy użytkownicy systemów iOS i Android będą mogli instalować na swoich urządzeniach niezarządzanych aplikacje przypisane im jako „dostępne bez rejestracji”. Przy użyciu poświadczeń usługi Intune użytkownicy mogą zalogować się do witryny internetowej Portal firmy i wyświetlić listę przypisanych im aplikacji. Pakiety aplikacji oznaczonych jako „dostępne bez rejestracji” są udostępniane do pobrania za pośrednictwem witryny internetowej Portal firmy. Ta zmiana nie ma wpływu na aplikacje, które wymagają rejestracji na potrzeby instalacji, ponieważ użytkownicy, którzy zechcą zainstalować te aplikacje, zobaczą monit o zarejestrowanie ich urządzenia.

#### <a name="signing-script-for-windows-10-company-portal---941642--"></a>Podpisywanie skryptu dla aplikacji Portal firmy systemu Windows 10 <!--941642-->

Jeśli musisz pobrać i ładować bezpośrednio aplikację Portal firmy dla systemu Windows 10, możesz teraz korzystać ze skryptu upraszczającego i usprawniającego proces podpisywania aplikacji w organizacji.   Aby pobrać skrypt i instrukcje dotyczące korzystania z niego, zobacz temat [Microsoft Intune Signing Script](https://aka.ms/win10cpscript) (Microsoft Intune – skrypt podpisywania) dla aplikacji Portal firmy systemu Windows 10 w galerii TechNet. Więcej szczegółów dotyczących tego powiadomienia można znaleźć w artykule [Updating your Windows 10 Company Portal app](https://blogs.technet.microsoft.com/intunesupport/2017/03/13/updating-your-windows-10-company-portal-app/) (Aktualizowanie aplikacji Portal firmy dla systemu Windows 10) na blogu zespołu pomocy technicznej usługi Intune.


### <a name="notices"></a>Uwagi

#### <a name="support-for-ios-103"></a>Obsługa systemu iOS 10.3

Wersja systemu iOS 10.3 została udostępniona użytkownikom 27 marca 2017 r. Wszystkie istniejące scenariusze dotyczące zarządzania urządzeniami przenośnymi i aplikacjami mobilnymi w usłudze Intune mają zastosowanie do najnowszej wersji systemu operacyjnego firmy Apple. Przewidujemy, że wszystkie obecnie dostępne funkcje usługi Intune do zarządzania urządzeniami z systemem iOS będą nadal działać po uaktualnieniu urządzeń i aplikacji do systemu iOS 10.3 przez użytkowników.

Obecnie nie występują żadne znane problemy. W przypadku wystąpienia jakichkolwiek problemów związanych z systemem operacyjnym iOS w wersji 10.3 zachęcamy do kontaktu z [zespołem pomocy technicznej usługi Intune](/intune-classic/troubleshoot/contact-assisted-phone-support-for-microsoft-intune).

#### <a name="improved-support-for-android-users-based-in-china---720444--"></a>Ulepszona obsługa systemu Android dla użytkowników w Chinach <!--720444-->

Ponieważ Sklep Google Play jest niedostępny w Chinach, aplikacje na urządzenia z systemem Android należy uzyskiwać z chińskich platform oferujących aplikacje. Aplikacja Portal firmy będzie obsługiwać ten przepływ pracy, przekierowując użytkowników systemu Android w Chinach na strony umożliwiające pobranie aplikacji Portal firmy i Outlook z lokalnych sklepów z aplikacjami. Pozwoli to udoskonalić środowisko pracy w przypadku włączenia zasad dostępu warunkowego — zarówno dla zarządzania urządzeniami przenośnymi, jak i zarządzania aplikacjami mobilnymi. Aplikacje Portal firmy i Outlook dla systemu Android są dostępne w następujących chińskich sklepach z aplikacjami:

- [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
- [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)
- [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
- [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
- [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)

#### <a name="best-practice-make-sure-your-company-portal-apps-are-up-to-date---879465--"></a>Najlepsze rozwiązanie: upewnij się, że aplikacje Portalu firmy są aktualne <!--879465-->

W grudniu 2016 roku opublikowaliśmy aktualizację włączającą wymuszanie uwierzytelniania wieloskładnikowego (MFA, multi-factor authentication) dla grupy użytkowników rejestrujących urządzenie z systemem iOS, Android, Windows 8.1 i nowszym lub Windows Phone 8.1 i nowszym. Ta funkcja nie może działać bez niektórych podstawowych wersji aplikacji Portal firmy dla systemów Android (w wersji 5.0.3419.0 lub nowszej) i iOS (w wersji 2.1.17 lub nowszej).

Firma Microsoft nieustannie ulepsza usługę Intune poprzez dodawanie nowych funkcji do konsoli i aplikacji Portal firmy na wszystkich obsługiwanych platformach. W rezultacie firma Microsoft wydaje tylko poprawki dotyczące problemów znalezionych w bieżącej wersji aplikacji Portal firmy. Dlatego zaleca się używanie najnowszych wersji aplikacji Portal firmy w celu uzyskania możliwie najwygodniejszego sposobu pracy użytkownika.

>[!Tip]
> Użytkownicy powinni skonfigurować swoje urządzenia do automatycznego aktualizowania aplikacji z właściwego sklepu z aplikacjami. Jeśli aplikacja Portal firmy systemu Android została udostępniona w udziale sieciowym, jej najnowszą wersję możesz pobrać z [Centrum pobierania firmy Microsoft](https://www.microsoft.com/download/details.aspx?id=49140).

#### <a name="microsoft-teams-is-now-enabled-for-mam-on-ios-and-android"></a>Obszar roboczy Microsoft Teams jest teraz włączony dla usługi MAM w systemach iOS i Android

Firma Microsoft poinformowała o ogólnej dostępności obszaru roboczego Microsoft Teams. Zaktualizowane aplikacje Microsoft Teams dla systemów iOS i Android są teraz włączone wraz z funkcjami zarządzania aplikacjami mobilnymi (MAM) w usłudze Intune, możesz więc zaoferować swoim zespołom możliwość swobodnej pracy na różnych urządzeniach przy jednoczesnym stałym zapewnieniu ochrony konwersacji i danych firmowych. Aby uzyskać więcej informacji, zobacz [Anons Microsoft Teams](https://blogs.technet.microsoft.com/enterprisemobility/2017/03/14/microsoft-teams-is-now-generally-available-and-mam-enabled-on-ios-and-android/) na blogu rozwiązania Enterprise Mobility and Security.


## <a name="february-2017"></a>Luty 2017

### <a name="new-capabilities"></a>Nowe możliwości

### <a name="modernizing-the-company-portal-website---753980--"></a>Modernizowanie witryny internetowej Portal firmy <!--753980-->
Witryna internetowa Portal firmy będzie obsługiwać aplikacje przeznaczone dla użytkowników, którzy nie mają zarządzanych urządzeń. Witryna internetowa zostanie zmieniona tak, aby wyglądała jak witryny innych produktów i usług firmy Microsoft, przy użyciu nowego schematu kontrastujących kolorów, ilustracji dynamicznych i menu typu „hamburger”. ![Mały obraz menu typu „hamburger” dodanego w lewym górnym rogu witryny internetowej Portal firmy,](/intune/whats-new-app-ui).

### <a name="notices"></a>Uwagi

#### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>Migracja grup nie wymaga żadnych aktualizacji grup ani zasad dotyczących urządzeń z systemem iOS <!--898837-->
W przypadku każdej grupy urządzeń w usłudze Intune, które są wstępnie przypisane przy użyciu profilu Rejestracja urządzeń firmowych, w usłudze AAD zostanie utworzona odpowiednia dynamiczna grupa urządzeń przy użyciu nazwy profilu Rejestracja urządzeń firmowych podczas migracji do grup urządzeń w usłudze Azure Active Directory. Dzięki temu rejestrowane urządzenia będą automatycznie grupowane i będą uzyskiwać te same zasady oraz aplikacje co grupa oryginalna w usłudze Intune.

Kiedy rozpocznie się proces migracji dzierżawy w zakresie grupowania i określania wartości docelowej, usługa Intune automatycznie utworzy dynamiczną grupę usługi AAD, która będzie odpowiadała grupie usługi Intune określonej jako docelowa przez profil Rejestracja urządzeń firmowych. Jeśli administrator usługi Intune usunie docelową grupę usługi Intune, odpowiadająca jej dynamiczna grupa usługi AAD nie zostanie usunięta. Członkowie tej grupy i zapytanie dynamiczne zostaną wyczyszczone, ale sama grupa jako całość zostanie pozostawiona do czasu, aż administrator IT usunie ją za pomocą portalu usługi AAD.

Podobnie — jeśli administrator IT zmieni docelową grupę usługi Intune dla profilu Rejestracja urządzeń firmowych, usługa Intune utworzy nową grupę dynamiczną odzwierciedlającą nowe przypisanie profilu, ale nie spowoduje usunięcia grupy dynamicznej utworzonej dla starego przypisania.

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Przyjmowanie wartości domyślnej zarządzania urządzeniami stacjonarnymi z systemem Windows za pomocą ustawień systemu Windows <!--663050-->
Domyślne zachowanie w przypadku rejestrowania komputerów z systemem Windows 10 ulega zmianie. W przypadku nowych rejestracji będzie stosowana typowa procedura rejestracji agenta MDM, a nie agenta komputerowego. Na witrynie sieci Web Portal firmy użytkownikom komputerów stacjonarnych z systemem Windows 10 zostaną udostępnione instrukcje dotyczące rejestrowania, które przeprowadzą ich przez proces dodawania komputerów stacjonarnych z systemem Windows 10 jako urządzeń przenośnych. Nie będzie to miało wpływu na obecnie zarejestrowane komputery, a organizacja nadal będzie mogła zarządzać komputerami stacjonarnymi z systemem Windows 10 przy użyciu agenta komputerowego, [jeśli zechcesz](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune).

#### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Ulepszona obsługa selektywnego czyszczenia danych przez zarządzanie aplikacjami mobilnymi <!--581242-->
Użytkownicy końcowi otrzymają dodatkowe wskazówki dotyczące odzyskiwania dostępu do danych służbowych w przypadku automatycznego usunięcia tych danych spowodowanego przez zasadę „Interwał offline przed wyczyszczeniem danych aplikacji”.<!--, or the removal of the Intune Company Portal on Android.-->

#### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Linki w aplikacji Portal firmy dla systemu iOS są otwierane wewnątrz aplikacji <!--665954-->
Linki w aplikacji Portal firmy dla systemu iOS, w tym linki do dokumentacji i aplikacji, będą otwierane bezpośrednio w aplikacji Portal firmy przy użyciu widoku przeglądarki Safari w aplikacji. Ta aktualizacja zostanie udostępniona oddzielnie od aktualizacji usługi w styczniu.

#### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Nowy adres serwera MDM dla urządzeń z systemem Windows <!--893007-->
Jeśli użytkownik wpisze ciąg __manage.microsoft.com__ jako adres serwera MDM (po wyświetleniu odpowiedniego monitu), próba zarejestrowania urządzenia z systemem Windows lub Windows Phone nie powiedzie się. Adres serwera MDM uległ zmianie z adresu __manage.microsoft.com__ na adres __enrollment.manage.microsoft.com__. Powiadom użytkownika, aby użył ciągu __enrollment.manage.microsoft.com__ jako adresu serwera MDM w przypadku wyświetlenia monitu podczas rejestrowania urządzenia z systemem Windows lub Windows Phone. Nie są wymagane żadne zmiany w konfiguracji CNAME. Aby uzyskać dodatkowe informacje o tej zmianie, odwiedź stronę [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange).

#### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nowe środowisko użytkownika aplikacji Portal firmy dla systemu Android <!--621622-->
Od marca aplikacja Portal firmy dla systemu Android będzie zgodna z [zaleceniami dotyczącymi projektowania materiałów](https://material.io/guidelines/material-design/introduction.html) w celu zapewnienia bardziej nowoczesnego wyglądu i działania. Udoskonalone środowisko użytkownika końcowego obejmuje między innymi następujące elementy:

* __Kolory__: nagłówkom kart można nadać kolory z palety kolorów niestandardowych.
* __Interfejs__: przyciski Polecane aplikacje i Wszystkie aplikacje na karcie Aplikacje zostały zaktualizowane. Przycisk Wyszukaj jest teraz przestawnym przyciskiem akcji.
* __Nawigacja__: na karcie Wszystkie aplikacje jest dostępny widok z kartami Polecane, Wszystkie i Kategorie w celu zapewnienia łatwiejszej nawigacji.
* __Usługa__: karty Moje urządzenia i Kontakt z działem IT są bardziej czytelne.

Obrazy przedstawiające poprzednią i nową wersję są dostępne na [stronie aktualizacji interfejsu użytkownika](/intune/whats-new-app-ui).

### <a name="associate-multiple-management-tools-with-the-microsoft-store-for-business---926135--"></a>Kojarzenie wielu narzędzi do zarządzania ze sklepie Microsoft Store dla Firm <!--926135-->
Wcześniej w przypadku wdrażania aplikacji ze Sklepu Microsoft dla Firm za pomocą więcej niż jednego narzędzia do zarządzania można było skojarzyć ze Sklepem Microsoft dla Firm tylko jedno z tych narzędzi. Teraz ze sklepem można skojarzyć wiele narzędzi do zarządzania (np. usługę Intune i program Configuration Manager). Aby uzyskać szczegółowe informacje, zobacz artykuł [Zarządzanie aplikacjami zakupionymi w Sklepie Microsoft dla Firm za pomocą usługi Microsoft Intune](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune).

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Nowości w publicznej wersji zapoznawczej środowiska administracyjnego usługi Intune na platformie Azure <!--736542-->

Na początku roku 2017 r. będziemy migrować nasze pełne środowisko administracyjne na platformę Azure, co umożliwi zaawansowane i zintegrowane zarządzanie podstawowymi przepływami pracy EMS na nowoczesnej platformie usług, którą można rozszerzyć za pomocą interfejsów API programu Graph.

Publiczna wersja zapoznawcza nowego środowiska administracyjnego będzie widoczna w nowych dzierżawach w wersji próbnej w witrynie Azure Portal w tym miesiącu. W wersji zapoznawczej możliwości istniejącej konsoli usługi Intune i spójność z nią będą udostępniane w sposób iteracyjny.

W środowisku administracyjnym w witrynie Azure Portal będzie używana już zapowiadana nowa funkcja grupowania i określania celu. W przypadku migrowania istniejącej dzierżawy do nowego środowiska grupowania nastąpi również migracja do nowego środowiska administracyjnego w wersji zapoznawczej w dzierżawie. Jeśli przed zakończeniem migrowania dzierżawy chcesz przetestować lub poznać dowolną nową funkcję, utwórz nowe konto wersji próbnej usługi Intune lub zapoznaj się z [nową dokumentacją](/intune/whats-new).

Informacje na temat nowości w wersji zapoznawczej usługi Intune na platformie Azure znajdziesz [tutaj](/intune/whats-new).

## <a name="january-2017"></a>Styczeń 2017

### <a name="new-capabilities"></a>Nowe możliwości

#### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>Raporty w konsoli dotyczące zarządzania aplikacjami mobilnymi bez rejestracji <!--677961-->
Dodano nowe raporty ochrony aplikacji dla zarówno zarejestrowanych, jak i niezarejestrowanych urządzeń. Dowiedz się więcej na temat [monitorowania zasad zarządzania aplikacjami mobilnymi](/intune-classic/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune).

#### <a name="android-711-support---694397--"></a>Obsługa systemu Android 7.1.1 <!--694397-->
Usługa Intune teraz w pełni obsługuje system Android 7.1.1 i zarządza nim.

#### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them---unknown--"></a>Rozwiązywanie problemów związanych z brakiem aktywności urządzeń z systemem iOS lub z brakiem możliwości komunikacji pomiędzy nimi a konsolą administracyjną <!--unknown-->
Gdy urządzenia użytkowników utracą połączenie z usługą Intune, można wykonać w odniesieniu do nich nowe kroki mające na celu rozwiązanie problemów w celu przywrócenia dostępu do zasobów firmy. Zobacz temat [Urządzenia są nieaktywne lub nie jest możliwe nawiązanie łączności między nimi a konsolą administracyjną](/intune-classic/troubleshoot/troubleshoot-device-enrollment-in-intune#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

### <a name="notices"></a>Uwagi

#### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Przyjmowanie wartości domyślnej zarządzania urządzeniami stacjonarnymi z systemem Windows za pomocą ustawień systemu Windows <!--663050-->
Domyślne zachowanie w przypadku rejestrowania komputerów z systemem Windows 10 ulega zmianie. W przypadku nowych rejestracji będzie stosowana typowa procedura rejestracji agenta MDM, a nie agenta komputerowego.

Na witrynie sieci Web Portal firmy użytkownikom komputerów stacjonarnych z systemem Windows 10 zostaną udostępnione instrukcje dotyczące rejestrowania, które przeprowadzą ich przez proces dodawania komputerów stacjonarnych z systemem Windows 10 jako urządzeń przenośnych. Nie będzie to miało wpływu na obecnie zarejestrowane komputery, a organizacja nadal będzie mogła zarządzać komputerami stacjonarnymi z systemem Windows 10 przy użyciu agenta komputerowego, [jeśli zechcesz](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune).

#### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Ulepszona obsługa selektywnego czyszczenia danych przez zarządzanie aplikacjami mobilnymi <!--581242-->
Użytkownicy końcowi otrzymają dodatkowe wskazówki dotyczące odzyskiwania dostępu do danych służbowych w przypadku automatycznego usunięcia tych danych spowodowanego przez zasadę „Interwał offline przed wyczyszczeniem danych aplikacji”.<!--, or the removal of the Intune Company Portal on Android.-->

#### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Linki w aplikacji Portal firmy dla systemu iOS są otwierane wewnątrz aplikacji <!--665954-->
Linki w aplikacji Portal firmy dla systemu iOS, w tym linki do dokumentacji i aplikacji, będą otwierane bezpośrednio w aplikacji Portal firmy przy użyciu widoku przeglądarki Safari w aplikacji. Ta aktualizacja zostanie udostępniona oddzielnie od aktualizacji usługi w styczniu.

#### <a name="modernizing-the-company-portal-website---753980--"></a>Modernizowanie witryny internetowej Portal firmy <!--753980-->
Od lutego witryna sieci Web Portal firmy będzie obsługiwać aplikacje przeznaczone dla użytkowników, którzy nie mają zarządzanych urządzeń. Witryna internetowa zostanie zmieniona tak, aby wyglądała jak witryny innych produktów i usług firmy Microsoft, przy użyciu nowego schematu kontrastujących kolorów, ilustracji dynamicznych i menu typu „hamburger”. ![Menu typu „hamburger” witryny internetowej Portal firmy](/intune/whats-new-app-ui).

#### <a name="new-documentation-for-app-protection-policies---583398--"></a>Nowa dokumentacja dotycząca zasad ochrony aplikacji <!--583398-->
Zaktualizowaliśmy dokumentację dla administratorów i deweloperów aplikacji, którzy chcą włączyć zasady ochrony aplikacji (znane jako zasady zarządzania aplikacjami mobilnymi) w swoich aplikacjach dla systemów iOS i Android przy użyciu narzędzia opakowującego aplikacje usługi Intune lub zestawu SDK aplikacji usługi Intune.

Zaktualizowano następujące artykuły:

* [Wybieranie sposobu przygotowania aplikacji do zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](/intune/apps-prepare-mobile-application-management)
* [Przygotowanie aplikacji systemu iOS do zarządzania aplikacjami mobilnymi za pomocą narzędzia opakowującego aplikacje w usłudze Intune](/intune/app-wrapper-prepare-ios)
* [Wprowadzenie do zestawu SDK aplikacji usługi Microsoft Intune](/intune/app-sdk-get-started)
* [Przewodnik dewelopera po zestawie SDK aplikacji usługi Intune dla systemu iOS](/intune/app-sdk-ios)

Następujące artykuły są nowościami w bibliotece dokumentacji:

* [Wtyczka Cordova zestawu SDK aplikacji usługi Intune](/intune/app-sdk-cordova)
* [Składnik Xamarin zestawu SDK aplikacji usługi Intune](/intune/app-sdk-xamarin)

#### <a name="progress-bar-when-launching-the-company-portal-on-ios---665978--"></a>Pasek postępu podczas uruchamiania aplikacji Portal firmy w systemie iOS <!--665978-->
W aplikacji Portal firmy dla systemu iOS wprowadzono pasek postępu na ekranie uruchamiania, aby przedstawić użytkownikowi informacje na temat procesów ładowania. Pasek postępu będzie wdrażany etapowo i zastąpi pokrętło. To oznacza, że niektórzy użytkownicy będą widzieć nowy pasek postępu, podczas gdy inni będą nadal widzieć pokrętło.

## <a name="december-2016"></a>Grudzień 2016

### <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Publiczna wersja zapoznawcza nowego środowiska administracyjnego usługi Intune na platformie Azure <!--736542-->
Na początku roku 2017 przeprowadzimy migrację pełnego środowiska administracyjnego na platformę Azure, co umożliwi zaawansowane i zintegrowane zarządzanie podstawowymi przepływami pracy EMS na nowoczesnej platformie usług, którą można rozszerzać za pomocą interfejsów API programu Graph. W związku z planami udostępnienia tego portalu wszystkim dzierżawcom usługi Intune z przyjemnością informujemy, że rozpoczynamy udostępnianie podglądu nowego środowiska administracyjnego jeszcze w tym miesiącu, aby wybrać dzierżawców.

W środowisku administracyjnym w witrynie Azure Portal będzie używana już zapowiadana nowa funkcja grupowania i określania celu. W przypadku migrowania istniejącej dzierżawy do nowego środowiska grupowania nastąpi również migracja do nowego środowiska administracyjnego w wersji zapoznawczej w dzierżawie. W międzyczasie możesz zapoznać się z naszą ofertą dotyczącą usługi Microsoft Intune w witrynie Azure Portal, korzystając z [nowej dokumentacji](/intune/what-is-intune).

__Integracja zarządzania kosztami telekomunikacyjnymi w publicznej wersji zapoznawczej witryny Azure Portal__ <!--747605-->
Obecnie rozpoczynamy pracę nad wersją zapoznawczą integracji z usługami zarządzania kosztami telekomunikacyjnymi innych firm w witrynie Azure Portal. Usługa Intune może być używana do wymuszania limitów użycia danych w kraju i w roamingu. Te operacje integracji rozpoczynamy od współpracy z firmą [Saaswedo](http://www.saaswedo.com/). Aby włączyć tę funkcję w dzierżawie w wersji próbnej, [skontaktuj się z pomocą techniczną firmy Microsoft](/intune-classic/troubleshoot/how-to-get-support-for-microsoft-intune).

### <a name="new-capabilities"></a>Nowe możliwości

__Usługa Multi-Factor Authentication na wszystkich platformach__ <!--747590-->
Teraz można wymusić użycie usługi Multi-Factor Authentication (MFA) przez wybraną grupę użytkowników podczas rejestracji urządzeń z systemem iOS, Android, Windows 8.1+ lub Windows Phone 8.1+ w portalu zarządzania Azure. W tym celu należy skonfigurować usługę MFA w aplikacji rejestracji w usłudze Microsoft Intune w usłudze Azure Active Directory.

__Możliwość ograniczenia rejestracji urządzeń przenośnych__ <!--747596-->
Usługa Intune dodaje nowe ograniczenia rejestracji, które pozwalają kontrolować, które platformy urządzeń przenośnych mogą być rejestrowane. Usługa Intune dzieli platformy urządzeń przenośnych na iOS, macOS, Android, Windows i Windows Mobile.
* Ograniczanie rejestracji urządzeń przenośnych nie ogranicza rejestracji klientów komputerów stacjonarnych.
* Tylko platforma iOS ma dodatkową opcję blokowania rejestracji urządzeń, które są własnością osobistą.

Intune oznacza wszystkie nowe urządzenia jako osobiste, chyba że administrator IT oznaczy je jako własność firmową, zgodnie z opisem [w tym artykule](/intune-classic/deploy-use/manage-corporate-owned-devices).

### <a name="notices"></a>Uwagi

__Użycie usługi Multi-Factor Authentication podczas rejestracji przeniesione do witryny Azure Portal__ <!--VSO 750545-->
Wcześniej w celu skonfigurowania usługi MFA na potrzeby rejestracji w usłudze Intune administratorzy musieli przejść do konsoli usług Intune lub konsoli programu Configuration Manager (wersje wydane przed październikiem 2016). Dzięki zaktualizowanej funkcji teraz należy zalogować się do witryny [Microsoft Azure Portal](https://manage.windowsazure.com) przy użyciu poświadczeń usługi Intune i skonfigurować ustawienia usługi MFA za pośrednictwem usługi Azure AD. Więcej informacji na ten temat można znaleźć [tutaj](https://aka.ms/mfa_ad).

__Aplikacja Portal firmy dla systemu Android jest teraz dostępna w Chinach__ <!--VSO 658093-->
Obecnie publikujemy aplikację Portal firmy dla systemu Android możliwą do pobierania na terenie Chin. Z powodu braku sklepu Google Play w Chinach aplikacje dla urządzeń z systemem Android należy uzyskiwać z chińskich platform handlowych oferujących aplikacje. Aplikacja Portal firmy dla systemu Android będzie dostępna do pobrania w następujących sklepach:
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

Aplikacja Portal firmy dla systemu Android używa usług Google Play do komunikowania się z usługą Microsoft Intune. Ponieważ usługi Google Play nie są jeszcze dostępne w Chinach, wykonanie dowolnego z wymienionych poniżej zadań może potrwać do 8 godzin. 

|Konsola administracyjna usługi Intune| Aplikacja Portal firmy w usłudze Intune dla systemu Android |Witryna aplikacji Portal firmy w usłudze Intune|   
|---|---|---|
|Pełne czyszczenie danych| Usuwanie urządzenia zdalnego| Usuwanie urządzenia (lokalnego i zdalnego)|
|Selektywne czyszczenie danych| Resetowanie urządzenia| Resetowanie urządzenia|
|Wdrażanie nowych lub zaktualizowanych aplikacji| Instalowanie dostępnych aplikacji biznesowych| Resetowanie kodu dostępu urządzenia|
|Zdalne blokowanie|||
|Resetowanie kodu dostępu|||

### <a name="deprecations"></a>Zakończenie obsługi

__Przeglądarka Firefox nie obsługuje już programu Silverlight__ <!--VSO TBA-->
Mozilla rezygnuje z obsługi technologii Silverlight w wersji 52 [przeglądarki Firefox](https://www.mozilla.org/firefox), począwszy od marca 2017 r. W związku z tym nie będzie można zalogować się do istniejącej konsoli usługi Intune za pomocą przeglądarki Firefox w wersjach nowszych niż 51. W celu uzyskania dostępu do konsoli administracyjnej zaleca się korzystanie z programu Internet Explorer 10 i 11 lub [wersji przeglądarki Firefox niższej niż 52](https://ftp.mozilla.org/pub/firefox/releases/). Przejście usługi Intune do witryny Azure Portal umożliwi obsługę wielu [nowoczesnych przeglądarek](/azure/azure-preview-portal-supported-browsers-devices) bez konieczności korzystania z technologii Silverlight.

__Usuwanie zasad mobilnej skrzynki odbiorczej usługi Exchange Online__ <!--770687-->
Od grudnia administratorzy nie będą już mogli wyświetlać ani konfigurować zasad dotyczących mobilnych skrzynek pocztowych usługi Exchange Online (EAS) w konsoli usługi Intune. Ta zmiana zostanie wdrożona we wszystkich dzierżawach usługi Intune w grudniu i styczniu. Wszystkie istniejące skonfigurowane zasady pozostaną niezmienione; w przypadku konfigurowania nowych zasad trzeba będzie korzystać z powłoki zarządzania serwerem Exchange. Więcej informacji można znaleźć [tutaj](https://technet.microsoft.com/library/bb123783%28v=exchg.150%29.aspx).

__Aplikacje Intune AV Player, Image Viewer i PDF Viewer nie są już obsługiwane w systemie Android__ <!--747553-->
Od połowy grudnia 2016 r. użytkownicy nie będą już mogli korzystać z aplikacji Intune AV Player, Image Viewer i PDF Viewer. Te aplikacje zostały zastąpione przez aplikację Azure Information Protection. Więcej informacji na temat aplikacji Azure Information Protection można znaleźć [tutaj](/information-protection/rms-client/mobile-app-faq).

## <a name="november-2016"></a>Listopad 2016

### <a name="new-capabilities"></a>Nowe możliwości

__Nowy Portal firmy w usłudze Microsoft Intune dostępny dla urządzeń z systemem Windows 10__ Firma Microsoft udostępniła nową [aplikację Portal firmy w usłudze Microsoft Intune dla urządzeń z systemem Windows 10](https://www.microsoft.com/store/apps/9wzdncrfj3pz). Ta aplikacja, korzystająca z nowego uniwersalnego formatu systemu Windows 10, będzie udostępniać użytkownikom zaktualizowane środowisko obsługi w aplikacji oraz zapewniać identyczne środowisko obsługi na wszystkich urządzeniach z systemem Windows 10 — komputerach osobistych i urządzeniach przenośnych — oferując ten sam zestaw funkcji, który jest dostępny dzisiaj.

Nowa aplikacja będzie również umożliwiać użytkownikom korzystanie z dodatkowych funkcji platformy, takich jak rejestracja jednokrotna (SSO) i uwierzytelnianie oparte na certyfikatach, na urządzeniach z systemem Windows 10. Aplikacja zostanie udostępniona jako uaktualnienie istniejących instalacji Portalu firmy w systemie Windows 8.1 i Portalu firmy w systemie Windows Phone 8.1 ze Sklepu Microsoft. Aby uzyskać szczegółowe informacje, przejdź do strony [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).

> [!IMPORTANT]
> __Aktualizacja dotycząca usługi Intune i systemu Android for Work__ Można wdrożyć aplikacje systemu Android for Work z akcją __Wymagane__, ale jeśli grupy usługi Intune zostały zmigrowane do nowego środowiska grup usługi Azure AD, będzie można wdrożyć aplikacje tylko jako __Dostępne__.

__Dodatek Cordova do zestawu SDK aplikacji usługi Intune obsługuje obecnie usługę MAM bez rejestracji__ Deweloperzy aplikacji mogą teraz używać dodatku Cordova do zestawu SDK aplikacji usługi Intune, aby w swoich aplikacjach opartych na oprogramowaniu Cordova dla systemów Android i iOS włączyć funkcje zarządzania aplikacjami mobilnymi bez rejestracji urządzeń. Zestaw SDK aplikacji usługi Intune dla wtyczki Cordova można znaleźć [tutaj](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam).

__Składnik Xamarin zestawu SDK aplikacji usługi Intune obsługuje obecnie usługę MAM bez rejestracji__ Deweloperzy aplikacji mogą teraz używać składnika Xamarin zestawu SDK aplikacji usługi Intune, aby w swoich aplikacjach opartych na platformie Xamarin dla systemów Android i iOS włączyć funkcje zarządzania aplikacjami mobilnymi bez rejestracji urządzeń. Składnik Xamarin zestawu SDK aplikacji usługi Intune można znaleźć [tutaj](https://github.com/msintuneappsdk/intune-app-sdk-xamarin).

### <a name="notices"></a>Uwagi

__Do pobrania certyfikatu podpisywania firmy Symantec nie jest już wymagana podpisana aplikacja Portal firmy dla systemu Windows Phone 8__ Pobieranie certyfikatu podpisywania firmy Symantec nie wiąże się już z koniecznością posiadania podpisanej aplikacji Portal firmy dla systemu Windows Phone 8. Certyfikat można przekazać niezależnie.

### <a name="deprecations"></a>Zakończenie obsługi

__Obsługa aplikacji Portal firmy dla systemu Windows Phone 8__ Pomoc techniczna dla aplikacji Portal firmy systemu Windows Phone 8 zostanie wycofana. Obsługa platform systemów Windows Phone 8 i WinRT została zakończona w październiku 2016 r. Obsługa Portalu firmy dla systemu Windows 8 została również zakończona w październiku 2016 r.
