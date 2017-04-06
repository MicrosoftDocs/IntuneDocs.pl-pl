# <a name="february-2017"></a>Luty 2017

## <a name="new-capabilities"></a>Nowe możliwości

### <a name="modernizing-the-company-portal-website---753980--"></a>Modernizowanie witryny sieci Web Portal firmy <!--753980-->
Witryna internetowa Portal firmy będzie obsługiwać aplikacje przeznaczone dla użytkowników, którzy nie mają zarządzanych urządzeń. Witryna internetowa zostanie zmieniona tak, aby wyglądała jak witryny innych produktów i usług firmy Microsoft, przy użyciu nowego schematu kontrastujących kolorów, ilustracji dynamicznych i menu typu „hamburger” ![Mały obraz menu typu „hamburger” dodanego w lewym górnym rogu witryny internetowej Portal firmy,](/intune/whats-new/media/CP_hamburger_menu.png) które będzie zawierać szczegółowe dane kontaktowe działu pomocy technicznej i informacje o istniejących urządzeniach zarządzanych. Układ strony docelowej zostanie zmieniony tak, aby wyróżnić aplikacje dostępne dla użytkowników, a aplikacje polecane i ostatnio zaktualizowane zostaną oznaczone symbolem karuzeli. Obrazy przedstawiające poprzednią i nową wersję są dostępne na [stronie aktualizacji interfejsu użytkownika](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

## <a name="notices"></a>Uwagi

### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>Migracja grup nie wymaga żadnych aktualizacji grup ani zasad dotyczących urządzeń z systemem iOS <!--898837-->
W przypadku każdej grupy urządzeń w usłudze Intune, które są wstępnie przypisane przy użyciu profilu Rejestracja urządzeń firmowych, w usłudze AAD zostanie utworzona odpowiednia dynamiczna grupa urządzeń przy użyciu nazwy profilu Rejestracja urządzeń firmowych podczas migracji do grup urządzeń w usłudze Azure Active Directory. Dzięki temu rejestrowane urządzenia będą automatycznie grupowane i będą uzyskiwać te same zasady oraz aplikacje co grupa oryginalna w usłudze Intune.

Kiedy rozpocznie się proces migracji dzierżawy w zakresie grupowania i określania wartości docelowej, usługa Intune automatycznie utworzy dynamiczną grupę usługi AAD, która będzie odpowiadała grupie usługi Intune określonej jako docelowa przez profil Rejestracja urządzeń firmowych. Jeśli administrator usługi Intune usunie docelową grupę usługi Intune, odpowiadająca jej dynamiczna grupa usługi AAD nie zostanie usunięta. Członkowie tej grupy i zapytanie dynamiczne zostaną wyczyszczone, ale sama grupa jako całość zostanie pozostawiona do czasu, aż administrator IT usunie ją za pomocą portalu usługi AAD.

Podobnie — jeśli administrator IT zmieni docelową grupę usługi Intune dla profilu Rejestracja urządzeń firmowych, usługa Intune utworzy nową grupę dynamiczną odzwierciedlającą nowe przypisanie profilu, ale nie spowoduje usunięcia grupy dynamicznej utworzonej dla starego przypisania.

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Przyjmowanie wartości domyślnej zarządzania urządzeniami stacjonarnymi z systemem Windows za pomocą ustawień systemu Windows <!--663050-->
Domyślne zachowanie w przypadku rejestrowania komputerów z systemem Windows 10 ulega zmianie. W przypadku nowych rejestracji będzie stosowana typowa procedura rejestracji agenta MDM, a nie agenta komputerowego. Na witrynie sieci Web Portal firmy użytkownikom komputerów stacjonarnych z systemem Windows 10 zostaną udostępnione instrukcje dotyczące rejestrowania, które przeprowadzą ich przez proces dodawania komputerów stacjonarnych z systemem Windows 10 jako urządzeń przenośnych. Nie będzie to miało wpływu na obecnie zarejestrowane komputery, a organizacja nadal będzie mogła zarządzać komputerami stacjonarnymi z systemem Windows 10 przy użyciu agenta komputerowego, [jeśli zechcesz](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Ulepszona obsługa selektywnego czyszczenia danych przez zarządzanie aplikacjami mobilnymi <!--581242-->
Użytkownicy końcowi otrzymają dodatkowe wskazówki dotyczące odzyskiwania dostępu do danych służbowych w przypadku automatycznego usunięcia tych danych spowodowanego przez zasadę „Interwał offline przed wyczyszczeniem danych aplikacji”.<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Linki w aplikacji Portal dla systemu iOS są otwierane wewnątrz aplikacji <!--665954-->
Linki w aplikacji Portal firmy dla systemu iOS, w tym linki do dokumentacji i aplikacji, będą otwierane bezpośrednio w aplikacji Portal firmy przy użyciu widoku przeglądarki Safari w aplikacji. Ta aktualizacja zostanie udostępniona oddzielnie od aktualizacji usługi w styczniu.

### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Nowy adres serwera MDM dla urządzeń z systemem Windows <!--893007-->
Jeśli użytkownik wpisze ciąg __manage.microsoft.com__ jako adres serwera MDM (po wyświetleniu odpowiedniego monitu), próba zarejestrowania urządzenia z systemem Windows lub Windows Phone nie powiedzie się. Adres serwera MDM uległ zmianie z adresu __manage.microsoft.com__ na adres __enrollment.manage.microsoft.com__. Powiadom użytkownika, aby użył ciągu __enrollment.manage.microsoft.com__ jako adresu serwera MDM w przypadku wyświetlenia monitu podczas rejestrowania urządzenia z systemem Windows lub Windows Phone. Nie są wymagane żadne zmiany w konfiguracji CNAME. Aby uzyskać dodatkowe informacje o tej zmianie, odwiedź stronę [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange).

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nowe środowisko użytkownika aplikacji Portal firmy dla systemu Android <!--621622-->
Od marca aplikacja Portal firmy dla systemu Android będzie zgodna z [zaleceniami dotyczącymi projektowania materiałów](https://material.io/guidelines/material-design/introduction.html) w celu zapewnienia bardziej nowoczesnego wyglądu i działania. Udoskonalone środowisko użytkownika końcowego obejmuje między innymi następujące elementy:

* __Kolory__: nagłówkom kart można nadać kolory z palety kolorów niestandardowych.
* __Interfejs__: przyciski Polecane aplikacje i Wszystkie aplikacje na karcie Aplikacje zostały zaktualizowane. Przycisk Wyszukaj jest teraz przestawnym przyciskiem akcji.
* __Nawigacja__: na karcie Wszystkie aplikacje jest dostępny widok z kartami Polecane, Wszystkie i Kategorie w celu zapewnienia łatwiejszej nawigacji.
* __Usługa__: karty Moje urządzenia i Kontakt z działem IT są bardziej czytelne.

Obrazy przedstawiające poprzednią i nową wersję są dostępne na [stronie aktualizacji interfejsu użytkownika](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>Skojarzenie wielu narzędzi do zarządzania ze Sklepem Windows dla firm <!--926135-->
Wcześniej w przypadku wdrażania aplikacji ze Sklepu Windows dla firm za pomocą więcej niż jednego narzędzia do zarządzania można było skojarzyć ze Sklepem Windows dla firm tylko jedno z tych narzędzi. Teraz ze sklepem można skojarzyć wiele narzędzi do zarządzania (np. usługę Intune i program Configuration Manager). Aby uzyskać szczegółowe informacje, zobacz artykuł [Zarządzanie aplikacjami zakupionymi w Sklepie Windows dla firm za pomocą usługi Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune).

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Nowości w publicznej wersji zapoznawczej środowiska administracyjnego usługi Intune na platformie Azure <!--736542-->

Na początku roku 2017 r. będziemy migrować nasze pełne środowisko administracyjne na platformę Azure, co umożliwi zaawansowane i zintegrowane zarządzanie podstawowymi przepływami pracy EMS na nowoczesnej platformie usług, którą można rozszerzyć za pomocą interfejsów API programu Graph.

Publiczna wersja zapoznawcza nowego środowiska administracyjnego będzie widoczna w nowych dzierżawach w wersji próbnej w witrynie Azure Portal w tym miesiącu. W wersji zapoznawczej możliwości istniejącej konsoli usługi Intune i spójność z nią będą udostępniane w sposób iteracyjny.

W środowisku administracyjnym w witrynie Azure Portal będzie używana już zapowiadana nowa funkcja grupowania i określania celu. W przypadku migrowania istniejącej dzierżawy do nowego środowiska grupowania nastąpi również migracja do nowego środowiska administracyjnego w wersji zapoznawczej w dzierżawie. Jeśli przed zakończeniem migrowania dzierżawy chcesz przetestować lub poznać dowolną nową funkcję, utwórz nowe konto wersji próbnej usługi Intune lub zapoznaj się z [nową dokumentacją](https://docs.microsoft.com/intune-azure/introduction/whats-new).

Informacje na temat nowości w wersji zapoznawczej usługi Intune na platformie Azure znajdziesz [tutaj](https://docs.microsoft.com/intune-azure/introduction/whats-new).

## <a name="january-2017"></a>Styczeń 2017

### <a name="new-capabilities"></a>Nowe możliwości

#### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>Raporty w konsoli dotyczące zarządzania aplikacjami mobilnymi bez rejestracji <!--677961-->
Dodano nowe raporty ochrony aplikacji dla zarówno zarejestrowanych, jak i niezarejestrowanych urządzeń. Dowiedz się więcej na temat [monitorowania zasad zarządzania aplikacjami mobilnymi](https://docs.microsoft.com/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune).

#### <a name="android-711-support---694397--"></a>Obsługa systemu Android 7.1.1 <!--694397-->
Usługa Intune teraz w pełni obsługuje system Android 7.1.1 i zarządza nim.

#### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them---unknown--"></a>Rozwiązywanie problemów związanych z brakiem aktywności urządzeń z systemem iOS lub z brakiem możliwości komunikacji pomiędzy nimi a konsolą administracyjną <!--unknown-->
Gdy urządzenia użytkowników utracą połączenie z usługą Intune, można wykonać w odniesieniu do nich nowe kroki mające na celu rozwiązanie problemów w celu przywrócenia dostępu do zasobów firmy. Zobacz temat [Urządzenia są nieaktywne lub nie jest możliwe nawiązanie łączności między nimi a konsolą administracyjną](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

### <a name="notices"></a>Uwagi

#### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Przyjmowanie wartości domyślnej zarządzania urządzeniami stacjonarnymi z systemem Windows za pomocą ustawień systemu Windows <!--663050-->
Domyślne zachowanie w przypadku rejestrowania komputerów z systemem Windows 10 ulega zmianie. W przypadku nowych rejestracji będzie stosowana typowa procedura rejestracji agenta MDM, a nie agenta komputerowego.

Na witrynie sieci Web Portal firmy użytkownikom komputerów stacjonarnych z systemem Windows 10 zostaną udostępnione instrukcje dotyczące rejestrowania, które przeprowadzą ich przez proces dodawania komputerów stacjonarnych z systemem Windows 10 jako urządzeń przenośnych. Nie będzie to miało wpływu na obecnie zarejestrowane komputery, a organizacja nadal będzie mogła zarządzać komputerami stacjonarnymi z systemem Windows 10 przy użyciu agenta komputerowego, [jeśli zechcesz](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

#### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Ulepszona obsługa selektywnego czyszczenia danych przez zarządzanie aplikacjami mobilnymi <!--581242-->
Użytkownicy końcowi otrzymają dodatkowe wskazówki dotyczące odzyskiwania dostępu do danych służbowych w przypadku automatycznego usunięcia tych danych spowodowanego przez zasadę „Interwał offline przed wyczyszczeniem danych aplikacji”.<!--, or the removal of the Intune Company Portal on Android.-->

#### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Linki w aplikacji Portal dla systemu iOS są otwierane wewnątrz aplikacji <!--665954-->
Linki w aplikacji Portal firmy dla systemu iOS, w tym linki do dokumentacji i aplikacji, będą otwierane bezpośrednio w aplikacji Portal firmy przy użyciu widoku przeglądarki Safari w aplikacji. Ta aktualizacja zostanie udostępniona oddzielnie od aktualizacji usługi w styczniu.

#### <a name="modernizing-the-company-portal-website---753980--"></a>Modernizowanie witryny sieci Web Portal firmy <!--753980-->
Od lutego witryna sieci Web Portal firmy będzie obsługiwać aplikacje przeznaczone dla użytkowników, którzy nie mają zarządzanych urządzeń. Witryna sieci Web zostanie zmieniona tak, aby wyglądała jak witryny innych produktów i usług firmy Microsoft, przy użyciu nowego schematu kontrastujących kolorów, ilustracji dynamicznych i menu typu „hamburger” ![menu „hamburger” witryny sieci Web Portal firmy](/Intune/whats-new/media/CP_hamburger_menu.png) oraz będzie zawierać szczegółowe dane kontaktowe działu pomocy technicznej i informacje o istniejących urządzeniach zarządzanych. Układ strony docelowej zostanie zmieniony tak, aby wyróżnić aplikacje dostępne dla użytkowników, a aplikacje polecane i ostatnio zaktualizowane zostaną oznaczone symbolem karuzeli. Obrazy przedstawiające poprzednią i nową wersję są dostępne na stronie [Co nowego w interfejsie użytkownika aplikacji usługi Intune](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

#### <a name="new-documentation-for-app-protection-policies---583398--"></a>Nowa dokumentacja dla zasad ochrony aplikacji <!--583398-->
Zaktualizowaliśmy dokumentację dla administratorów i deweloperów aplikacji, którzy chcą włączyć zasady ochrony aplikacji (znane jako zasady zarządzania aplikacjami mobilnymi) w swoich aplikacjach dla systemów iOS i Android przy użyciu narzędzia opakowującego aplikacje usługi Intune lub zestawu SDK aplikacji usługi Intune.

Zaktualizowano następujące artykuły:

* [Wybieranie sposobu przygotowania aplikacji do zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
* [Przygotowanie aplikacji systemu iOS do zarządzania aplikacjami mobilnymi za pomocą narzędzia opakowującego aplikacje w usłudze Intune](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
* [Wprowadzenie do zestawu SDK aplikacji usługi Microsoft Intune](https://docs.microsoft.com/intune/develop/intune-app-sdk-get-started)
* [Przewodnik dewelopera po zestawie SDK aplikacji usługi Intune dla systemu iOS](https://docs.microsoft.com/intune/develop/intune-app-sdk-ios)

Następujące artykuły są nowościami w bibliotece dokumentacji:

* [Wtyczka Cordova zestawu SDK aplikacji usługi Intune](https://docs.microsoft.com/intune/develop/intune-app-sdk-cordova)
* [Składnik Xamarin zestawu SDK aplikacji usługi Intune](https://docs.microsoft.com/intune/develop/intune-app-sdk-xamarin)

#### <a name="progress-bar-when-launching-the-company-portal-on-ios---665978--"></a>Pasek postępu podczas uruchamiania aplikacji Portal firmy w systemie iOS <!--665978-->
W aplikacji Portal firmy dla systemu iOS wprowadzono pasek postępu na ekranie uruchamiania, aby przedstawić użytkownikowi informacje na temat procesów ładowania. Pasek postępu będzie wdrażany etapowo i zastąpi pokrętło. To oznacza, że niektórzy użytkownicy będą widzieć nowy pasek postępu, podczas gdy inni będą nadal widzieć pokrętło.

## <a name="december-2016"></a>Grudzień 2016

### <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Publiczna wersja zapoznawcza nowego środowiska administracyjnego usługi Intune na platformie Azure <!--736542-->
Na początku roku 2017 przeprowadzimy migrację pełnego środowiska administracyjnego na platformę Azure, co umożliwi zaawansowane i zintegrowane zarządzanie podstawowymi przepływami pracy EMS na nowoczesnej platformie usług, którą można rozszerzać za pomocą interfejsów API programu Graph. W związku z planami udostępnienia tego portalu wszystkim dzierżawcom usługi Intune z przyjemnością informujemy, że rozpoczynamy udostępnianie podglądu nowego środowiska administracyjnego jeszcze w tym miesiącu, aby wybrać dzierżawców.

W środowisku administracyjnym w witrynie Azure Portal będzie używana już zapowiadana nowa funkcja grupowania i określania celu. W przypadku migrowania istniejącej dzierżawy do nowego środowiska grupowania nastąpi również migracja do nowego środowiska administracyjnego w wersji zapoznawczej w dzierżawie. W międzyczasie możesz zapoznać się z naszą ofertą dotyczącą usługi Microsoft Intune w witrynie Azure Portal, korzystając z [nowej dokumentacji](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).

__Integracja z usługami zarządzania kosztami telekomunikacyjnymi w publicznej wersji zapoznawczej witryny Azure Portal__ <!--747605--> Obecnie rozpoczynamy pracę nad wersją zapoznawczą integracji z usługami zarządzania kosztami telekomunikacyjnymi innych firm w witrynie Azure Portal. Usługa Intune może być używana do wymuszania limitów użycia danych w kraju i w roamingu. Te operacje integracji rozpoczynamy od współpracy z firmą [Saaswedo](http://www.saaswedo.com). Aby włączyć tę funkcję w dzierżawie w wersji próbnej, [skontaktuj się z pomocą techniczną firmy Microsoft](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

### <a name="new-capabilities"></a>Nowe możliwości

__Uwierzytelnianie wieloskładnikowe na wszystkich platformach__ <!--747590--> Teraz można wymusić użycie usługi Multi-Factor Authentication (MFA) przez wybraną grupę użytkowników podczas rejestracji urządzeń z systemem iOS, Android, Windows 8.1+ lub Windows Phone 8.1+ w portalu zarządzania Azure. W tym celu należy skonfigurować usługę MFA w aplikacji rejestracji w usłudze Microsoft Intune w usłudze Azure Active Directory.

__Możliwość ograniczenia rejestracji urządzeń przenośnych__ <!--747596--> Usługa Intune dodaje nowe ograniczenia rejestracji, które pozwalają kontrolować, które platformy urządzeń przenośnych mogą być rejestrowane. Usługa Intune dzieli platformy urządzeń przenośnych na iOS, macOS, Android, Windows i Windows Mobile.
* Ograniczanie rejestracji urządzeń przenośnych nie ogranicza rejestracji klientów komputerów stacjonarnych.
* Tylko platforma iOS ma dodatkową opcję blokowania rejestracji urządzeń, które są własnością osobistą.

Intune oznacza wszystkie nowe urządzenia jako osobiste, chyba że administrator IT oznaczy je jako własność firmową, zgodnie z opisem [w tym artykule](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).

### <a name="notices"></a>Uwagi

__Uwierzytelnianie wieloskładnikowe przy rejestracji przeniesione do witryny Azure Portal__ <!--VSO 750545-->Wcześniej w celu skonfigurowania usługi MFA na potrzeby rejestracji w usłudze Intune administratorzy musieli przejść do konsoli usługi Intune lub konsoli programu Configuration Manager (wersje wydane przed październikiem 2016). Dzięki zaktualizowanej funkcji teraz należy zalogować się do witryny [Microsoft Azure Portal](https://manage.windowsazure.com) przy użyciu poświadczeń usługi Intune i skonfigurować ustawienia usługi MFA za pośrednictwem usługi Azure AD. Więcej informacji na ten temat można znaleźć [tutaj](https://aka.ms/mfa_ad).

__Aplikacja Portal firmy dla systemu Android teraz jest dostępna w Chinach__ <!--VSO 658093--> Obecnie publikujemy aplikację Portal firmy dla systemu Android możliwą do pobierania na terenie Chin. Z powodu braku sklepu Google Play w Chinach aplikacje dla urządzeń z systemem Android należy uzyskiwać z chińskich platform handlowych oferujących aplikacje. Aplikacja Portal firmy dla systemu Android będzie dostępna do pobrania w następujących sklepach:
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

__Firefox nie będzie obsługiwać technologii Silverlight__ <!--VSO TBA--> Mozilla rezygnuje z obsługi technologii Silverlight w wersji 52 [przeglądarki Firefox](https://www.mozilla.org/firefox), począwszy od marca 2017 r. W związku z tym nie będzie można zalogować się do istniejącej konsoli usługi Intune za pomocą przeglądarki Firefox w wersjach nowszych niż 51. W celu uzyskania dostępu do konsoli administracyjnej zaleca się korzystanie z programu Internet Explorer 10 i 11 lub [wersji przeglądarki Firefox niższej niż 52](https://ftp.mozilla.org/pub/firefox/releases/). Przejście usługi Intune do witryny Azure Portal umożliwi obsługę wielu [nowoczesnych przeglądarek](https://docs.microsoft.com/en-us/azure/azure-preview-portal-supported-browsers-devices) bez konieczności korzystania z technologii Silverlight.

__Usunięcie zasad dotyczących mobilnych skrzynek pocztowych usługi Exchange Online__ <!--770687--> Od grudnia administratorzy nie będą już mogli wyświetlać ani konfigurować zasad dotyczących mobilnych skrzynek pocztowych usługi Exchange Online (EAS) w konsoli usługi Intune. Ta zmiana zostanie wdrożona we wszystkich dzierżawach usługi Intune w grudniu i styczniu. Wszystkie istniejące skonfigurowane zasady pozostaną niezmienione; w przypadku konfigurowania nowych zasad trzeba będzie korzystać z powłoki zarządzania serwerem Exchange. Więcej informacji można znaleźć [tutaj](https://technet.microsoft.com/en-us/library/bb123783%28v=exchg.150%29.aspx).

__Aplikacje Intune AV Player, Image Viewer i PDF Viewer przestaną być obsługiwane w systemie Android__ <!--747553--> Od połowy grudnia 2016 r. użytkownicy nie będą już mogli korzystać z aplikacji Intune AV Player, Image Viewer i PDF Viewer. Te aplikacje zostały zastąpione przez aplikację Azure Information Protection. Więcej informacji na temat aplikacji Azure Information Protection można znaleźć [tutaj](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq).

## <a name="november-2016"></a>Listopad 2016

### <a name="new-capabilities"></a>Nowe możliwości

__Nowy Portal firmy w usłudze Microsoft Intune dostępny dla urządzeń z systemem Windows 10__ Firma Microsoft udostępniła nową [aplikację Portal firmy w usłudze Microsoft Intune dla urządzeń z systemem Windows 10](https://www.microsoft.com/store/apps/9wzdncrfj3pz). Ta aplikacja, korzystająca z nowego uniwersalnego formatu systemu Windows 10, będzie udostępniać użytkownikom zaktualizowane środowisko obsługi w aplikacji oraz zapewniać identyczne środowisko obsługi na wszystkich urządzeniach z systemem Windows 10 — komputerach osobistych i urządzeniach przenośnych — oferując ten sam zestaw funkcji, który jest dostępny dzisiaj.

Nowa aplikacja będzie również umożliwiać użytkownikom korzystanie z dodatkowych funkcji platformy, takich jak rejestracja jednokrotna (SSO) i uwierzytelnianie oparte na certyfikatach, na urządzeniach z systemem Windows 10. Aplikacja zostanie udostępniona jako uaktualnienie istniejących instalacji Portalu firmy w systemie Windows 8.1 i Portalu firmy w systemie Windows Phone 8.1 ze Sklepu Windows. Aby uzyskać szczegółowe informacje, przejdź do strony [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).

> [!IMPORTANT]
> __Aktualizacja dotycząca usługi Intune i systemu Android for Work__ Można wdrożyć aplikacje systemu Android for Work z akcją __Wymagane__, ale jeśli grupy usługi Intune zostały zmigrowane do nowego środowiska grup usługi Azure AD, będzie można wdrożyć aplikacje tylko jako __Dostępne__.

__Dodatek Cordova do zestawu SDK aplikacji usługi Intune obsługuje obecnie usługę MAM bez rejestracji__ Deweloperzy aplikacji mogą teraz używać dodatku Cordova do zestawu SDK aplikacji usługi Intune, aby w swoich aplikacjach opartych na oprogramowaniu Cordova dla systemów Android i iOS włączyć funkcje zarządzania aplikacjami mobilnymi bez rejestracji urządzeń. Zestaw SDK aplikacji usługi Intune dla wtyczki Cordova można znaleźć [tutaj](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam).

__Składnik Xamarin zestawu SDK aplikacji usługi Intune obsługuje obecnie usługę MAM bez rejestracji__ Deweloperzy aplikacji mogą teraz używać składnika Xamarin zestawu SDK aplikacji usługi Intune, aby w swoich aplikacjach opartych na platformie Xamarin dla systemów Android i iOS włączyć funkcje zarządzania aplikacjami mobilnymi bez rejestracji urządzeń. Składnik Xamarin zestawu SDK aplikacji usługi Intune można znaleźć [tutaj](https://github.com/msintuneappsdk/intune-app-sdk-xamarin).

### <a name="notices"></a>Uwagi

__Do pobrania certyfikatu podpisywania firmy Symantec nie jest już wymagana podpisana aplikacja Portal firmy dla systemu Windows Phone 8__ Pobieranie certyfikatu podpisywania firmy Symantec nie wiąże się już z koniecznością posiadania podpisanej aplikacji Portal firmy dla systemu Windows Phone 8. Certyfikat można przekazać niezależnie.

###<a name="deprecations"></a>Zakończenie obsługi

__Obsługa aplikacji Portal firmy dla systemu Windows Phone 8__ Pomoc techniczna dla aplikacji Portal firmy systemu Windows Phone 8 zostanie wycofana. Obsługa platform systemów Windows Phone 8 i WinRT została zakończona w październiku 2016 r. Obsługa Portalu firmy dla systemu Windows 8 została również zakończona w październiku 2016 r.

## <a name="october-2016"></a>Październik 2016

### <a name="conditional-access-for-mobile-application-management"></a>Dostęp warunkowy do zarządzania aplikacjami mobilnymi
Będzie możliwe ograniczanie dostępu do usług Exchange Online w taki sposób, aby można go było uzyskać tylko z poziomu aplikacji obsługujących zasady zarządzania aplikacjami mobilnymi usługi Intune, takich jak Outlook. [Ta nowa funkcja](/intune/deploy-use/allow-policy-managed-apps-access-to-o365) doskonale współgra z zasadami zarządzania aplikacjami mobilnymi w usłudze Intune, ponieważ umożliwia blokowanie dostępu do wbudowanych klientów poczty lub innych aplikacji, które nie zostały skonfigurowane za pomocą tych zasad. Dzięki temu użytkownicy mogą korzystać z danych organizacji za pośrednictwem aplikacji, które mogą być chronione przy użyciu funkcji zarządzania aplikacjami mobilnymi w usłudze Intune. Pracę z zasadami zarządzania aplikacjami mobilnymi w usłudze Intune można rozpocząć, korzystając z portalu Azure. Wystarczy znaleźć w bloku „Ustawienia” nową sekcję dotyczącą dostępu warunkowego.

### <a name="conditional-access-for-windows-pcs"></a>Dostęp warunkowy dla komputerów z systemem Windows
Przy użyciu konsoli administracyjnej usługi Intune można teraz tworzyć zasady dostępu warunkowego, uniemożliwiając komputerom z systemem Windows dostęp do usług [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) i [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune). Zasady dostępu warunkowego można też tworzyć w celu blokowania dostępu do aplikacji klasycznych pakietu Office oraz aplikacji uniwersalnych.

### <a name="android-for-work-support"></a>Pomoc techniczna dla programu Android for Work

> [!IMPORTANT]

> Można wdrożyć aplikacje systemu Android for Work z akcją __Wymagane__, ale jeśli grupy usługi Intune zostały zmigrowane do nowego środowiska grup usługi Azure AD, będzie można wdrożyć aplikacje tylko jako __Dostępne__.

Usługa Intune jest teraz częścią programu Android for Work (AfW). W tym miesiącu rozpoczniemy wdrażanie obsługi funkcji programu AfW i będziemy kontynuować te działania w ciągu następnych kilku miesięcy. Należy pamiętać, że wdrożenie dostępnych aplikacji programu AfW korzysta z nowego środowiska grupowania i kierowania. Użytkownicy nowo aprowizowanych kont usługi Intune będą w stanie korzystać z tej funkcji po udostępnieniu im programu AfW.

[Przeczytaj ogłoszenie firmy Microsoft dotyczące pomocy technicznej dla programu Android for Work w ramach usługi Intune](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

Poniższe tematy dotyczące usługi Intune są nowe lub zostały zaktualizowane o informacje o programie Android for Work:

Dla specjalistów IT:
- [Konfigurowanie programu Android for Work](/intune/deploy-use/set-up-android-for-work)
- [Ograniczanie dostępu poczty e-mail do usługi Exchange Online i nowej usługi Exchange Online w wersji dedykowanej przy użyciu usługi Intune](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
- [Ograniczanie dostępu poczty e-mail do lokalnego programu Exchange i starszej wersji usługi Exchange Online w wersji dedykowanej przy użyciu usługi Intune](/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
- [Ustawienia zasad zgodności programu Android for Work](/intune/deploy-use/afw-compliance-policy-settings-in-microsoft-intune)
- [Jak wdrażać aplikacje programu Android for Work](/intune/deploy-use/android-for-work-apps)
- [Konfigurowanie aplikacji programu Android for Work przy użyciu zasad konfiguracji aplikacji mobilnych](/intune/deploy-use/afw-app-configuration-policy)
- [Ustawienia zasad programu Android for Work](/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)

Dla użytkowników końcowych:
- [Co się dzieje w przypadku tworzenia profilu służbowego](/intune/enduser/what-happens-when-you-create-a-work-profile-android)
- [Tworzenie profilu służbowego i rejestrowanie urządzenia w usłudze Intune](/intune/enduser/create-a-work-profile-and-enroll-your-device-in-intune-android)

### <a name="lookout-integration-to-protect-ios-devices"></a>Integracja usługi Lookout w celu ochrony urządzeń z systemem iOS
W październiku firma Microsoft wprowadzi integrację z rozwiązaniem firmy Lookout do ochrony urządzeń przenośnych w celu zabezpieczenia urządzeń przenośnych z systemem iOS dzięki wykrywaniu złośliwego oprogramowania, ryzykownych aplikacji i innych zagrożeń na urządzeniach. Rozwiązanie firmy Lookout pomaga w określeniu poziomu zagrożenia, który można skonfigurować. W usłudze Intune można utworzyć regułę zasad zgodności w celu określania zgodności urządzeń na podstawie oceny ryzyka uzyskanej z rozwiązania firmy Lookout. Za pomocą zasad dostępu warunkowego można umożliwić lub zablokować dostęp do zasobów firmy w zależności od stanu zgodności danego urządzenia.

W przypadku użytkowników końcowych korzystających z niezgodnych urządzeń z systemem iOS zostanie wyświetlony monit o przeprowadzenie rejestracji. Aby uzyskać dostęp do zasobów firmy, użytkownicy będą musieli zainstalować aplikację Lookout for Work na swoich urządzeniach, uaktywnić ją i podjąć środki zaradcze dotyczące zagrożeń raportowanych przez aplikację Lookout for Work. Dowiedz się, jak [skonfigurować i wdrożyć aplikację Lookout for Work](/intune/deploy-use/configure-and-deploy-lookout-for-work-apps).
<!--TFS 1319493-->

### <a name="intune-app-wrapping-tool-for-android"></a>Narzędzie opakowujące aplikacje usługi Intune dla systemu Android
Przy użyciu narzędzia opakowującego aplikacje usługi Intune możesz włączyć stosowanie zasad zarządzania aplikacjami mobilnymi usługi Intune w używanych aplikacjach. Pomoc techniczna dotycząca zasad zarządzania aplikacjami mobilnymi usługi Intune bez konieczności rejestrowania urządzeń jest już dostępna.

### <a name="manage-printing-from-apps-managed-using-mam-policies"></a>Zarządzanie drukowaniem z aplikacji zarządzanych przy użyciu zasad zarządzania aplikacjami mobilnymi
Możesz teraz uniemożliwić drukowanie firmowych danych z aplikacji, dla których obowiązują zasady zarządzania aplikacjami mobilnymi. To ustawienie jest dostępne w [Portalu Azure](/Intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) i jest obsługiwane zarówno przez urządzenia z systemem [iOS](/Intune/deploy-use/ios-mam-policy-settings), jak i z systemem [Android](/Intune/deploy-use/android-mam-policy-settings).
<!--TFS 1014328-->

### <a name="support-for-fingerprints-on-android-devices"></a>Obsługa odcisków palców na urządzeniach z systemem Android
Zasady zarządzania aplikacjami mobilnymi systemu Android teraz umożliwiają użytkownikom uzyskanie dostępu do aplikacji za pomocą odcisku palca zamiast wpisywania kodu PIN. Zobacz to i inne [ustawienia zasad zarządzania aplikacjami mobilnymi systemu Android, klikając tutaj](/Intune/deploy-use/android-mam-policy-settings).

### <a name="notices"></a>Uwagi

__Zgodność systemów Android i Samsung KNOX z usługą Intune__ Niektóre modele telefonu Samsung Galaxy Ace nie mogą być zarządzane przez usługę Intune jako urządzenia Samsung KNOX. Zamiast tego po zarejestrowaniu tych urządzeń w usłudze Intune będą one zarządzane jako standardowe urządzenia z systemem Android.

Numery modeli, których dotyczy to zagadnienie:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

Ani Ty ani użytkownicy końcowi nie musicie wykonywać żadnych dalszych czynności. Aby uzyskać więcej informacji, odwiedź witrynę sieci Web [Samsung KNOX](https://www.samsungknox.com).

__Aplikacja Portal firmy dla systemu Windows 8 jest przestarzała; pomoc techniczna dla platform Windows Phone 8 i Windows RT zostanie wkrótce wycofana__ Począwszy od października 2016 r. usługa Microsoft Intune wstrzyma obsługę aplikacji Portal firmy dla systemu Windows 8. Z usługi Microsoft Intune zostanie również wycofana pomoc techniczna dla platform Windows Phone 8 i Windows RT. W rezultacie nie będzie można zarejestrować ani zaktualizować żadnych urządzeń z systemem Windows Phone 8 lub Windows RT.

Można będzie nadal zarządzać urządzeniami z systemami Windows Phone 8, Windows RT i Windows 8, które są już zarejestrowane. Zaktualizuj urządzenia z systemami Windows 8 i Windows Phone 8 do systemów Windows 8.1 i Windows Phone 8.1 oraz skorzystaj z odpowiedniej aplikacji Portal firmy dla systemu Windows 8.1 lub Windows Phone 8.1, aby kontynuować bez zakłóceń dystrybucję aplikacji na tych urządzeniach.

Począwszy od listopada 2016 roku firma Microsoft wycofa pomoc techniczną dla aplikacji Portal firmy systemu Windows Phone 8.
<!--TFS 1255391-->

### <a name="whats-coming"></a>Wkrótce

__Nowy Portal firmy w usłudze Microsoft Intune dostępny dla urządzeń z systemem Windows 10__ Firma Microsoft udostępnia nowy Portal firmy w usłudze Microsoft Intune dla urządzeń z systemem Windows 10. Ta aplikacja, korzystająca z nowego uniwersalnego formatu systemu Windows 10, będzie udostępniać użytkownikom zaktualizowane środowisko obsługi w aplikacji oraz zapewniać identyczne środowisko obsługi na wszystkich urządzeniach z systemem Windows 10 — komputerach osobistych i urządzeniach przenośnych — oferując ten sam zestaw funkcji, który jest dostępny dzisiaj.

Nowa aplikacja będzie również umożliwiać użytkownikom korzystanie z dodatkowych funkcji platformy, takich jak rejestracja jednokrotna (SSO) i uwierzytelnianie oparte na certyfikatach, na urządzeniach z systemem Windows 10. Aplikacja zostanie udostępniona jako uaktualnienie istniejących instalacji Portalu firmy w systemie Windows 8.1 i Portalu firmy w systemie Windows Phone 8.1 ze Sklepu Windows. Aby uzyskać szczegółowe informacje, przejdź do strony [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).
<!--TFS 1016502-->

## <a name="september-2016"></a>Wrzesień 2016
### <a name="new-features-announcements-and-information"></a>Nowe funkcje, anonsy i informacje
* [Dostęp warunkowy w systemie Windows](#windows-conditional-access)
* [Obsługa systemu iOS 10](#ios-10-support)
* [Narzędzie opakowujące aplikacje obsługuje zarządzanie aplikacjami mobilnymi bez rejestrowania urządzeń dla systemów Android i iOS](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [Rozpoczęte we wrześniu przejście grup usługi Intune do grup usługi Azure Active Directory](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Integracja aplikacji Lookout w celu ochrony urządzeń z systemem Android](#lookout-integration-to-protect-android-devices)
* [Aktualizacje aplikacji Portal firmy dla systemów Android, iOS i Windows](#company-portal-updates)
* [Słownik dotyczący usługi Intune](#intune-glossary)
* [Wkrótce](#whats-coming)

### <a name="windows-conditional-access"></a>Dostęp warunkowy w systemie Windows
Przy użyciu konsoli administracyjnej usługi Intune można teraz tworzyć zasady dostępu warunkowego, uniemożliwiając komputerom z systemem Windows dostęp do usług Exchange Online i SharePoint Online. Zasady dostępu warunkowego można też tworzyć w celu blokowania dostępu do aplikacji klasycznych pakietu Office oraz aplikacji uniwersalnych.

### <a name="ios-10-support"></a>Obsługa systemu iOS 10
Istniejące scenariusze dotyczące zarządzania urządzeniami przenośnymi i aplikacjami mobilnymi w usłudze Intune mają zastosowanie w systemie iOS 10. Aby uzyskać porady, zobacz [Blog zespołu pomocy technicznej usługi Intune](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/).

### <a name="app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios"></a>Narzędzie opakowujące aplikacje obsługuje zarządzanie aplikacjami mobilnymi bez rejestrowania urządzeń dla systemów Android i iOS
Narzędzie opakowujące aplikacje dostępne w ramach usługi Intune to narzędzie wiersza polecenia służące do obsługi aplikacji biznesowych do zarządzania aplikacjami mobilnymi w usłudze Intune dla systemów iOS i Android. Jest to najprostszy sposób uwzględnienia w swojej aplikacji zestawu SDK do zarządzania aplikacjami mobilnymi w usłudze Intune. Dzięki temu aplikacja może wymuszać stosowanie zasad zarządzania aplikacjami mobilnymi wdrożonych za pomocą usługi Intune. Za pomocą zasad zarządzania aplikacjami mobilnymi można:

1. Szyfrować dane aplikacji.
2. Wymagać wprowadzania numeru PIN podczas uruchamiania aplikacji przez pracownika przetwarzającego informacje.
3. Zezwalać aplikacji na przesyłanie danych tylko do innych aplikacji zarządzanych.
4. Uniemożliwić aplikacji tworzenie kopii zapasowej danych w systemie Android oraz usługach iTunes i iCloud.
5. Zezwalać na wycinanie, kopiowanie i wklejanie wyłącznie do oraz z innych aplikacji zarządzanych.

Publiczna wersja zapoznawcza zaktualizowanego narzędzia opakowującego aplikacje w usłudze Intune obsługuje teraz zarządzanie aplikacjami mobilnymi bez rejestrowania urządzeń w wewnętrznych aplikacjach biznesowych w systemach iOS i Android. To znaczy, że użytkownicy końcowi nie muszą rejestrować swoich urządzeń za pomocą usługi Intune w celu używania aplikacji biznesowych obsługujących zarządzanie aplikacjami mobilnymi.

Każdy może wypróbować publiczną wersję zapoznawczą i przeczytać pomocną dokumentację. Wystarczy skorzystać z materiałów udostępnionych na koncie msintuneappsdk w usłudze GitHub:

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Przed zainstalowaniem i użyciem wersji wstępnej narzędzia opakowującego aplikacje w usłudze Microsoft Intune dla systemów Android i iOS trzeba:

* Zapoznać się z postanowieniami licencyjnymi firmy Microsoft dotyczącymi wersji wstępnej narzędzia opakowującego aplikacje w usłudze Microsoft Intune dla systemów Android i iOS.
* Wydrukować i zachować kopię postanowień licencyjnych. Pobranie i używanie wersji wstępnej narzędzia opakowującego aplikacje w usłudze Microsoft Intune dla systemu Android jest równoznaczne z akceptacją postanowień licencyjnych. Jeśli użytkownik nie akceptuje niniejszych postanowień, nie może używać tego oprogramowania.
<!---TFS 1235607--->

### <a name="intune-groups-begin-transitioning-to-azure-active-directory-in-september"></a>Rozpoczęte we wrześniu przejście grup usługi Intune do grup usługi Azure Active Directory
W przypadku niektórych nowych kont usługi Intune będą używane grupy zabezpieczeń usługi Azure Active Directory, a nie grupy użytkowników usługi Intune. To, że praca odbywa się z grupami zabezpieczeń, jest sygnalizowane obecnością na stronie grup portalu Intune linku do portalu zarządzania Azure.

### <a name="lookout-integration-to-protect-android-devices"></a>Integracja aplikacji Lookout w celu ochrony urządzeń z systemem Android
Firma Microsoft przeprowadza integrację z rozwiązaniem firmy Lookout przeznaczonymi do ochrony urządzeń przenośnych w celu zabezpieczenia urządzeń przenośnych z systemem Android przez wykrywanie na urządzeniach złośliwego oprogramowania, ryzykownych aplikacji i innych zagrożeń. Rozwiązanie firmy Lookout pomaga w określeniu poziomu zagrożenia, który można skonfigurować. W usłudze Intune można utworzyć regułę zasad zgodności w celu określania zgodności urządzeń na podstawie oceny ryzyka uzyskanej z rozwiązania firmy Lookout. Za pomocą zasad dostępu warunkowego można umożliwić lub zablokować dostęp do zasobów firmy w zależności od stanu zgodności danego urządzenia.

W przypadku użytkowników końcowych korzystających z niezgodnych urządzeń zostanie wyświetlony monit o zarejestrowanie urządzeń. Aby uzyskać dostęp do zasobów firmy, użytkownicy będą musieli zainstalować aplikację Lookout for Work na urządzeniach z systemem Android, uaktywnić ją i podjąć środki zaradcze dotyczące zagrożeń zgłoszonych w aplikacji Lookout for Work. Aby uzyskać więcej informacji, zobacz [Ograniczanie dostępu do zasobów firmy oparte na ryzyku dotyczącym urządzeń, sieci i aplikacji](https://docs.microsoft.com/en-us/intune/deploy-use/device-threat-protection).


### <a name="company-portal-updates"></a>Aktualizacje Portalu firmy

__Android__

<p style="margin-left: 40px">**Dodanie obszaru „Powiadomienia” do Portalu firmy dla systemu Android**<br/>
<p style="margin-left: 40px">Na stronie głównej Portalu firmy dla systemu Android dodano nową ikonę Powiadomienia. Naciśnięcie tej ikony powoduje przejście na stronę Powiadomienia — przedstawia ona użytkownikowi końcowemu wszystkie elementy, które wymagają uwagi w aplikacji Portal firmy, takie jak brak zgodności urządzeń, aktualizacja rejestracji i aktywacja rejestracji. W aplikacji Portal firmy dla systemu iOS obszar powiadomień jest już dostępny. W wyniku wprowadzenia strony Powiadomienia nie będzie widoczna strona Konfigurowanie dostępu do zasobów firmy po uruchomieniu lub wznowieniu pracy w Portalu firmy, jeśli urządzenie zostało już zarejestrowane. W przypadku tworzenia własnych wskazówek dla użytkowników końcowych warto zaktualizować dokumentację, tak aby uwzględniała tę zmianę. Zaktualizowane zrzuty ekranu można znaleźć [tutaj](https://aka.ms/androidcpupdate).  

__iOS__
<p style="margin-left: 40px">**Zmiany w obsłudze aplikacji Portal firmy dla systemu iOS**<br/>
<p style="margin-left: 40px">Wszyscy użytkownicy aplikacji Portal firmy usługi Microsoft Intune dla systemu iOS muszą obecnie używać jej najnowszej wersji. Nowi użytkownicy mogą pobrać tylko najnowszą wersję, a bieżący użytkownicy muszą przeprowadzić aktualizację do najnowszej wersji. Najnowsza wersja aplikacji wymaga systemu iOS 8.0 lub nowszego, dlatego urządzenia ze starszymi wersjami systemu iOS nie mogą korzystać z portalu firmy ani rejestrować się do czasu ich zaktualizowania do systemu iOS 8.0 lub nowszego oraz zaktualizowania aplikacji Portal firmy do najnowszej wersji. Zarejestrowane urządzenia z wersjami systemu iOS poniżej 8.0 będą nadal zarządzane i wyświetlane w konsoli administracyjnej usługi Intune.
<!---TFS 1283165--->

<p style="margin-left: 40px">**Ulepszenia w sposobie uzyskiwania aplikacji przez użytkowników końcowych systemu iOS**<br/>
<p style="margin-left: 40px">Wprowadzono następujące zmiany w odniesieniu do kafelków aplikacji w aplikacji Portal firmy dla systemu iOS. Zmiany mają na celu umożliwienie przechodzenia do różnych widoków w obrębie jednej lokalizacji — witryny sieci Web Portal firmy — dla wszystkich swoich aplikacji. Ograniczenia firmy Apple uniemożliwiają wyświetlanie w aplikacji Portal firmy aplikacji biznesowych oraz zarządzanych ze sklepu z aplikacjami, w związku z czym użytkownicy muszą korzystać z różnych widoków, aby znaleźć wszystkie swoje aplikacje.

<p style="margin-left: 40px">Kafelek **Aplikacje firmowe** pozwalał poprzednio przejść do listy wszystkich aplikacji na karcie WSZYSTKIE w witrynie sieci Web Portal firmy. Jego działanie nie ulegnie zmianie. Nazwa kafelka została zmieniona na **Wszystkie aplikacje**.

<p style="margin-left: 40px">Kafelek **Inne aplikacje** pozwalał poprzednio przejść do widoku zawierającego wszystkie aplikacje, których wyświetlanie w aplikacji Portal firmy jest możliwe zgodnie z zasadami firmy Apple. Nazwa kafelka została zmieniona na **Polecane aplikacje**, a jego naciśnięcie spowoduje przejście na kartę POLECANE w witrynie sieci Web Portal firmy.

<p style="margin-left: 40px">Kafelek **Kategorie** pozwalał poprzednio przejść w ramach aplikacji Portal firmy do widoku zawierającego kategorie aplikacji. Nazwa kafelka nie uległa zmianie, ale jego naciśnięcie będzie teraz powodować przejście na kartę KATEGORIE w witrynie sieci Web Portal firmy. Zaktualizowane zrzuty ekranu można znaleźć [tutaj](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
  <!---TFS 1317133--->

<p style="margin-left: 40px">**Wyświetlanie monitu o instalację aplikacji Managed Browser dla systemu iOS, jeśli oprogramowanie IT Pro określiło taki wymóg dla aplikacji**<br/>
<p style="margin-left: 40px">Ustawienie składnika Web Clip w taki sposób, aby otwierał się tylko w zarządzanej przeglądarce w przypadku, gdy zarządzana przeglądarka nie została zainstalowana na urządzeniu, spowoduje, że aplikacja Portal firmy na urządzeniu wyświetli monit o zainstalowanie zarządzanej przeglądarki przed zainstalowaniem składnika Web Clip.
  <!---TFS 1228570--->

__Windows__
<p style="margin-left: 40px">**Dodanie przycisku wysyłania opinii do aplikacji Portal firmy dla systemu Windows Phone 8.1**<br/>
<p style="margin-left: 40px">Aplikacja Portal firmy dla systemu Windows Phone 8.1 umożliwia użytkownikom końcowym przesyłanie opinii o aplikacji przy użyciu nowego przycisku „wyślij opinię”. Aby znaleźć przycisk, użytkownicy muszą nacisnąć oznaczone wielokropkiem menu w prawej dolnej części ekranu aplikacji Portal firmy, a następnie nacisnąć pozycję **wyślij opinię**. Zebrane anonimowe opinie pomogą firmie Microsoft w ulepszaniu środowiska aplikacji Portal firmy dla użytkowników.
<!---TFS 1317806--->

### <a name="intune-glossarybr"></a>Słownik dotyczący usługi Intune</br>
Dodano nowy [temat w słowniku](https://docs.microsoft.com/intune/understand-explore/intune-glossary) do biblioteki, aby ułatwić zrozumienie niektórych pojęć używanych w produkcie Intune.

## <a name="august-2016"></a>Sierpień 2016
### <a name="app-management"></a>Zarządzanie aplikacjami

__Aplikacje ukrywane i wyświetlane dla systemu iOS 9.3__ Dla urządzeń z systemem iOS 9.3 lub nowszym w ogólnych zasadach konfiguracji systemu iOS można używać listy aplikacji ukrywanych i wyświetlanych, aby:
- Określić listę aplikacji, które będą ukryte dla użytkowników. Użytkownicy nie będą mogli wyświetlać ani uruchamiać tych aplikacji.
- Określić listę aplikacji, które użytkownicy mogą wyświetlać i uruchamiać. Użytkownicy nie będą mogli wyświetlać ani uruchamiać żadnych innych aplikacji.

Dla tych list można określić zarówno aplikacje wdrożone, jak i wbudowane aplikacje dla systemu iOS, takie jak Wiadomości i Notatki. Aby uzyskać więcej informacji, zobacz [Ustawienia zasad systemu iOS w usłudze Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune)
<!---TFS 1279009 checked--->
__Zasady aplikacji dozwolonych i zablokowanych dla urządzeń z systemem Samsung KNOX__ Dla urządzeń z systemem Samsung KNOX można teraz skonfigurować zasady niestandardowe umożliwiające utworzenie jednej z następujących list:
- Lista aplikacji, których uruchamianie na urządzeniu jest zablokowane. Nawet po zainstalowaniu aplikacji zdefiniowanej na liście zablokowanych nie będzie jej można uaktywnić na urządzeniu.
- Lista aplikacji, które użytkownicy urządzenia mogą instalować ze sklepu klepu Google Play. Nie będzie można instalować żadnych innych aplikacji ze sklepu.

Tych ustawień można używać tylko w przypadku urządzeń z systemem Samsung KNOX.
Aby uzyskać więcej informacji, zobacz [Użycie niestandardowych zasad do zezwalania na aplikacje i blokowania ich na urządzeniach z systemem Samsung KNOX](https://docs.microsoft.com/en-us/intune/deploy-use/custom-policy-to-allow-and-block-samsung-knox-apps).
<!---TFS 1311629 checked --->

__Nowe aplikacje zgodne z zasadami zarządzania aplikacjami mobilnymi__ Aplikacja usługi Yammer dla systemów [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) i [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) jest teraz zgodna z [zasadami zarządzania aplikacjami mobilnymi usługi Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), bez względu na to, czy urządzenie jest zarejestrowane.

Pełna lista aplikacji zgodnych z zasadami MAM jest dostępna w witrynie [partnerów aplikacji usługi Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners).
<!--- TFS 1252335 & 1252336 checked--->

__Aplikacje Intune Viewer__ Wraz z wydaniem nowej aplikacji RMS sharing zostaną usunięte następujące aplikacje Intune Viewer, począwszy od sierpnia 2016 roku:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer dla systemu Android ze sklepu Google Play

Zalecamy, aby zamiast korzystania z aplikacji Intune Viewer używać nowej [aplikacji do zarządzania prawami (RMS sharing) dla systemu Android](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), co pozwala na wdrożenie jednej aplikacji zamiast trzech osobnych aplikacji w celu bezpiecznego przeglądania plików firmy na urządzeniach z systemem Android. Gdy aplikacja Intune Viewer nie będzie już obsługiwana, zostanie usunięta ze sklepu Google i nie będzie dostępna do użycia w przyszłości.

### <a name="device-management"></a>Zarządzanie urządzeniami
__Obsługa systemu Android 7.0__ Usługa Intune zapewnia obsługę „od dnia 0” nadchodzącego systemu operacyjnego Android 7.0 dla urządzeń przenośnych.
<!---TFS 1262053--->
### <a name="google-removal-of-remote-passcode-reset-capability-on-android-70-devices"></a>Usunięcie przez Google możliwości zdalnego resetowania kodu dostępu na urządzeniach z systemem Android 7.0
Google usuwa możliwość zdalnego resetowania kodu dostępu urządzeń z systemem Android 7.0 przez administratorów IT i użytkowników końcowych. Wcześniej administratorzy IT mogli zdalnie zresetować kod dostępu użytkownika, a użytkownicy końcowi mogli resetować swoje kody dostępu z witryny sieci Web Portalu firmy.



### <a name="company-portal-updates"></a>Aktualizacje Portalu firmy
__Witryna sieci Web Portal firmy__
- **Link opinii z Portalu firmy do firmy Microsoft** <br/>
Witryna sieci Web Portalu firmy udostępnia użytkownikom końcowym nowy link „Opinia” u dołu strony, który użytkownicy mogą wybrać, aby wysłać do firmy Microsoft opinię dotyczącą ich wizyty w witrynie. Zebrane, anonimowe opinie pomogą firmie Microsoft w ulepszaniu środowiska witryny sieci Web Portalu firmy dla użytkowników.
<!--- TFS 1313657 checked--->

__iOS__
- **Minimalna wersja systemu iOS dla przeglądarki Managed Browser została zaktualizowana do 8.0**<br/>
Aplikacja Microsoft Intune Managed Browser dla systemu iOS została zaktualizowana w celu obsługiwania urządzeń z systemem iOS 8.0 lub nowszym. Podczas gdy urządzenia z systemem iOS 7.1 wciąż mogą używać istniejącej aplikacji Managed Browser, należy zachęcać użytkowników do aktualizacji systemu iOS do wersji 8.0 lub nowszej, aby mogli w pełni skorzystać z najnowszych funkcji przeglądarki Managed Browser.  
<!---TFS 1313253 checked--->

### <a name="whats-coming"></a>Wkrótce
__Przejście grup usługi Intune do grup usługi Azure Active Directory rozpocznie się we wrześniu 2016 r.__ Usługa Intune wprowadza nową funkcjonalność zarządzania grupami, która używa grup zabezpieczeń usługi Azure Active Directory (AAD) jako grupy użytkowników i urządzeń w usłudze Intune. Te grupy będą używane do zarządzania grupami, wdrażania zasad i wdrażania profilów **po wprowadzeniu nowego portalu administracyjnego usługi Intune używającej platformy Azure**.

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

__Dodanie obszaru „Powiadomienia” do Portalu firmy dla systemu Android__ We wrześniu udostępnimy aktualizację Portalu firmy dla systemu Android, która wprowadzi nową ikonę **Powiadomienia** na stronie głównej. Naciśnięcie tej ikony spowoduje przejście na stronę **Powiadomienia**, która przedstawia użytkownikowi końcowemu wszystkie elementy, które wymagają uwagi w aplikacji Portal firmy, takie jak brak zgodności urządzeń, aktualizacja rejestracji i aktywacja rejestracji. Jeśli używasz również aplikacji Portal firmy dla systemu iOS, powiadomienia masz już widoczne. Wraz z wprowadzeniem strony **Powiadomienia** nie będzie widoczna strona **Konfigurowanie dostępu do zasobów firmy** po uruchomieniu lub wznowieniu pracy w Portalu firmy dla systemu Android, jeśli urządzenie zostało już zarejestrowane. Wiemy, że wiele osób utworzyło wskazówki dla użytkowników końcowych i doceniają wcześniejsze powiadomienie, gdy wskazówki lub zrzuty ekranu mogą wymagać aktualizacji. Prosimy więc o takie zaktualizowanie dokumentacji, aby odzwierciedlała ona nadchodzące zmiany w środowisku. Zaktualizowane zrzuty ekranu można znaleźć tutaj: https://aka.ms/androidcpupdate.  

### <a name="service-deprecation"></a>Wycofywanie usług

- **Zmiany w obsłudze aplikacji Portal firmy dla systemu iOS**<br/>
We wrześniu wszyscy użytkownicy aplikacji Portal firmy usługi Microsoft Intune dla systemu iOS będą musieli używać jej najnowszej wersji. Nowi użytkownicy będą mogli pobrać tylko najnowszą wersję, a bieżący użytkownicy będą musieli przeprowadzić aktualizację do najnowszej wersji. Najnowsza wersja aplikacji wymaga systemu iOS 8.0 lub nowszego, dlatego urządzenia ze starszymi wersjami systemu iOS nie będą mogły korzystać z portalu firmy ani rejestrować się do czasu ich zaktualizowania do systemu iOS 8.0 lub nowszego oraz zaktualizowania aplikacji Portal firmy do najnowszej wersji. Zarejestrowane urządzenia z wersjami systemu iOS poniżej 8.0 będą nadal zarządzane i wyświetlane w konsoli administracyjnej usługi Intune.  

- **Minimalna wersja systemu iOS dla przeglądarki Managed Browser została zaktualizowana do 8.0**<br/>
W sierpniu dział usługi Intune opublikuje zaktualizowaną aplikację Microsoft Intune Managed Browser dla systemu iOS, która będzie obsługiwana tylko na urządzeniach z systemem iOS 8.0 lub nowszym. Podczas gdy urządzenia z systemem iOS 7.1 wciąż będą mogły używać istniejącej aplikacji Managed Browser, należy zachęcać użytkowników do aktualizacji systemu iOS do wersji 8.0 lub nowszej, aby mogli w pełni skorzystać z najnowszych funkcji przeglądarki Managed Browser.  
<!---TFS 1313253--->

- **Aplikacje Portal firmy dla systemu Windows 8 i Windows Phone 8 zostaną wycofane we wrześniu 2016 r.** <br/>
Począwszy od września 2016 roku w usłudze Microsoft Intune zakończy się obsługa aplikacji Portal firmy Microsoft Intune dla platform Windows Phone 8 i Windows 8. Zaktualizuj urządzenia do systemów Windows 8.1 i Windows Phone 8.1 oraz skorzystaj z odpowiedniej aplikacji Portal firmy dla systemu Windows 8.1 lub Windows Phone 8.1, aby kontynuować dystrybucję aplikacji na tych urządzeniach.
<!---TFS 1255391--->
