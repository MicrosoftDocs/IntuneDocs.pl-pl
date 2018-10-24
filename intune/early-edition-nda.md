---
title: Wczesna wersja
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 72585982cd27962981f581a99f0ea361642df0ee
ms.sourcegitcommit: ba0699cc351954960b222223c60c4ecd50edc829
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49652142"
---
# <a name="the-early-edition-for-microsoft-intune---october-2018"></a>Wersja wczesna usługi Microsoft Intune — październik 2018

> [!Note]
> Powiadomienie dotyczące umowy o zachowaniu poufności: dla usługi Intune opracowywane są następujące zmiany. Te informacje są udostępniane pod rygorem umowy o zachowaniu poufności w bardzo ograniczonym zakresie. Nie wolno publikować żadnych tych informacji w mediach społecznościowych ani w publicznych witrynach internetowych, takich jak Twitter, UserVoice, Reddit itd. 

**Wczesna wersja** zawiera listę funkcji udostępnianych w ramach umowy o zachowaniu poufności, które zostaną wprowadzone w przyszłych wydaniach usługi Microsoft Intune. Te informacje są przekazywane w ograniczonym zakresie i mogą ulec zmianie. Nie publikuj tweetów, wpisów na platformie UserVoice ani w inny sposób nie udostępniaj tych informacji poza swoją firmą. Niektóre funkcje wymienione w tym miejscu mogą nie być wdrożone na czas i zostać opóźnione do przyszłych wersji. Inne funkcje są testowane w wersji pilotażowej, aby zapewnić przygotowanie ich do użytku przez klientów. W przypadku pytań lub wątpliwości skontaktuj się z osobą kontaktową ds. tej grupy produktów firmy Microsoft.

Ta strona jest okresowo aktualizowana. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Usługa Intune w witrynie Azure Portal

<!-- 1810 start -->

### <a name="use-microsoft-recommended-settings-with-security-baselines----2055484---"></a>Używanie ustawień zalecanych przez firmę Microsoft z punktami odniesienia zabezpieczeń <!-- 2055484 -->
Usługa Intune umożliwia integrację z innymi usługami koncentrującymi się na zabezpieczeniach, w tym z usługą Windows Defender ATP i usługą Office 365 ATP. Klienci pytają o typową strategię i spójny zestaw kompleksowych przepływów pracy zabezpieczeń w usługach Microsoft 365. Naszym celem jest dopasowanie strategii w celu utworzenia rozwiązań, które łączą operacje zabezpieczeń i typowe zadania administratora. W usłudze Intune staramy się osiągnąć ten cel, publikując zestaw „punktów odniesienia zabezpieczeń” zalecanych przez firmę Microsoft (**Intune** > **Punkty odniesienia zabezpieczeń**).  Administrator będzie mógł tworzyć zasady zabezpieczeń bezpośrednio z tych punktów odniesienia, a następnie wdrożyć je dla użytkowników. Można również dostosować rekomendacje dotyczące najlepszych rozwiązań do potrzeb swojej organizacji. Usługa Intune zapewnia, że urządzenia pozostają w zgodności z tymi punktami odniesienia, i powiadamia administratorów użytkowników lub urządzeń, które nie są zgodne.

### <a name="autopilot-support-for-hybrid-azure-active-directory-joined-devices----1048100---"></a>Obsługa rozwiązania Autopilot w przypadku hybrydowych urządzeń przyłączonych do usługi Azure Active Directory <!-- 1048100 -->
Za pomocą rozwiązania Autopilot będzie można skonfigurować hybrydowe urządzenia przyłączone do usługi Azure Active Directory. Aby używać hybrydowego rozwiązania Autopilot, urządzenia muszą być przyłączone do sieci w organizacji.

### <a name="scope-tags-for-apps---1081941---"></a>Tagi zakresu dla aplikacji <!--1081941 -->
Będzie możliwe tworzenie tagów zakresu w celu ograniczenia dostępu do zasobów usługi Intune. Dodaj tag zakresu do przypisania roli, a następnie dodaj tag zakresu do profilu konfiguracji. Rola będzie miała wtedy dostęp tylko do zasobów z profilami konfiguracji ze zgodnymi tagami zakresu (lub bez tagów zakresu).
Aby utworzyć tag zakresu, wybierz pozycję **Role usługi Intune** > **Zakres (tagi)** > **Utwórz**.
Aby dodać tag zakresu do przypisania roli, wybierz pozycję **Role usługi Intune** > **Wszystkie role** > **Menedżer zasad i profilów** > **Przypisania** > **Zakres (tagi)**.
Aby dodać tag zakresu do profilu konfiguracji, wybierz pozycję **Konfiguracja urządzenia** > **Profile** > wybierz profil > **Właściwości** > **Zakres (tagi)**.

### <a name="tenant-health-dashboard----1124854---"></a>Pulpit nawigacyjny kondycji dzierżawy <!-- 1124854 -->
Na stronie Stan dzierżawy w usłudze Intune znajdziesz informacje o stanie dzierżawy w jednym miejscu. Strona jest podzielona na 4 sekcje:  
- **Szczegóły dzierżawy**: zawiera informacje takie jak urząd zarządzania urządzeniami przenośnymi, suma zarejestrowanych urządzeń w Twojej dzierżawie i liczba licencji. Ta sekcja zawiera także bieżącą wersję usługi dla Twojej dzierżawy.
- **Stan łącznika**: zawiera informacje dla skonfigurowanych łączników, takich jak program VPP firmy Apple, Sklep Windows dla Firm i łączniki certyfikatów. Na podstawie ich bieżącego stanu łączniki są oznaczane flagami *Dobra kondycja*, *Ostrzeżenie* lub *Zła kondycja*.
- **Kondycja usługi Intune**: zawiera aktywne zdarzenia lub awarie dotyczące Twojej dzierżawy. Informacje przedstawione w tej sekcji są pobierane bezpośrednio z Centrum wiadomości usługi Office ([https://portal.office.com](https://portal.office.com)).
- **Wiadomości w usłudze Intune**: zawiera aktywne wiadomości dla dzierżawy obejmujące takie elementy jak powiadomienia o tym, że dzierżawa otrzymała najnowsze funkcje usługi Intune. Informacje przedstawione w tej sekcji są pobierane bezpośrednio z Centrum wiadomości usługi Office ([https://portal.office.com](https://portal.office.com)).

### <a name="enrollment-abandonment-report----1382924---"></a>Raport porzucań rejestracji <!-- 1382924 -->
Nowy raport zawierający szczegółowe informacje dotyczące porzuconych rejestracji będzie dostępny w obszarze **Rejestrowanie urządzeń** > **Monitorowanie**.

### <a name="deployed-wip-policies-without-user-enrollment----1434452---"></a>Wdrożone zasady funkcji WIP bez rejestracji użytkownika <!-- 1434452 -->
Zasady funkcji Windows Information Protection (WIP) będzie można wdrożyć bez konieczności rejestracji urządzeń z systemem Windows 10 przez użytkowników zarządzania urządzeniami przenośnymi. Ta konfiguracja pozwala firmom na ochronę firmowych dokumentów na podstawie konfiguracji funkcji WIP, jednocześnie umożliwiając użytkownikom zarządzanie własnymi urządzeniami z systemem Windows. Gdy dokumenty są chronione za pomocą zasad funkcji WIP, chronione dane mogą być selektywnie czyszczone przez administratora usługi Intune. Wybierając użytkownika i urządzenie oraz wysyłając żądanie czyszczenia, wszystkie dane chronione za pomocą zasad funkcji WIP staną się bezużyteczne. Z usługi Intune w witrynie Azure Portal wybierz pozycję **Aplikacja mobilna** > **Selektywne czyszczenie aplikacji**.


### <a name="add-custom-brand-image-for-company-portal-app----1916266---"></a>Dodawanie obrazu niestandardowego marki dla aplikacji Portal firmy <!-- 1916266 -->
Jako administrator usługi Microsoft Intune będziesz mieć możliwość przekazania obrazu niestandardowego marki, który będzie wyświetlany jako obraz tła na stronie profilu użytkownika w aplikacji Portal firmy. Aby uzyskać więcej informacji na temat konfigurowania aplikacji Portal firmy, zobacz artykuł [Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune](company-portal-app.md).

### <a name="group-windows-autopilot-enrolled-devices-by-correlator-id----2075110---"></a>Grupowanie urządzeń zarejestrowanych w programie Windows Autopilot według identyfikatora korelatora <!-- 2075110 -->
Usługa Intune będzie obsługiwać grupowanie urządzeń z systemem Windows według identyfikatora korelatora, jeśli są zarejestrowane przy użyciu [rozwiązania Autopilot dla istniejących urządzeń](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) za pośrednictwem programu Configuration Manager. Identyfikator korelatora jest parametrem pliku konfiguracji rozwiązania Autopilot. Usługa Intune automatycznie ustawi [atrybut urządzenia w usłudze Azure AD enrollmentProfileName](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#using-attributes-to-create-rules-for-device-objects) na wartość „OfflineAutopilotprofile-\<correlator ID\>”. Dzięki temu można utworzyć dowolne grupy dynamiczne usługi Azure AD na podstawie identyfikatora korelatora za pomocą atrybutu enrollmentprofileName dla rejestracji rozwiązania Autopilot w trybie offline. 


### <a name="support-for-ios-12-oauth-in-ios-email-profiles---2155106---"></a>Obsługa uwierzytelniania OAuth z systemu iOS 12 w profilach poczty e-mail systemu iOS <!--2155106 -->
Profile poczty e-mail systemu iOS w usłudze Intune będą obsługiwać uwierzytelnianie OAuth z systemu iOS 12. Aby wyświetlić tę funkcję, wybierz pozycje **Intune** > **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **OAuth**. Jeśli to ustawienie zostanie włączone, zdarzą się dwie rzeczy:
1. Urządzenia, które są już wybrane, otrzymają nowy profil.
2. Użytkownicy końcowi zostaną poproszeni o ponowne podanie poświadczeń.

### <a name="new-required-password-type-default-setting-for-android-android-enterprise---2649963---"></a>Nowe ustawienie domyślne „Wymagany typ hasła” dla systemów Android, Android Enterprise<!-- 2649963 -->
Podczas tworzenia nowej zasady zgodności (**Intune** > **Zgodność urządzenia** > **Zasady** > **Utwórz zasady** > **Android** lub **Android enterprise** dla platformy > Zabezpieczenia systemu) wartość domyślna dla ustawienia **Wymagany typ hasła** ulegnie zmianie: Aktualny, Domyślny: Ustawienie domyślne urządzenia; Nowy, Domyślny: Co najmniej numeryczne; Dotyczy: System Android, Android Enterprise.

### <a name="assign-autopilot-profiles-to-the-all-devices-virtual-group---2715522---"></a>Przypisywanie profilów rozwiązania Autopilot do wirtualnej grupy wszystkich urządzeń <!--2715522 -->
Będzie można przypisać profile rozwiązania Autopilot do wirtualnej grupy wszystkich urządzeń. Aby to zrobić, wybierz pozycję **Rejestrowanie urządzeń** > **Rejestracja w systemie Windows** > **Profile wdrażania** > wybierz profil > **Przypisania** > w obszarze **Przypisz do** wybierz pozycję **Wszystkie urządzenia**.

### <a name="new-azure-active-directory-terms-of-use-feature----2870393---"></a>Nowa funkcja warunków użytkowania usługi Azure Active Directory <!-- 2870393 -->
Usługa Azure Active Directory będzie miała funkcję warunków użytkowania, której będzie można użyć zamiast istniejących warunków i postanowień usługi Intune. Funkcja warunków użytkowania usługi Azure AD zapewnia większą elastyczność w związku z tym, które warunki wyświetlić i kiedy, lepszą obsługę lokalizacji, większą kontrolę sposobu renderowania i ulepszone raportowanie. Funkcja warunków użytkowania usługi Azure AD wymaga usługi Azure Active Directory Premium P1, która jest również częścią pakietu Enterprise Mobility + Security E3.


### <a name="intune-will-maintain-the-office-localized-language-when-updating-office-on-end-users-machines----2971030---"></a>Zachowanie lokalnego języka pakietu Office przez usługę Intune podczas aktualizowania pakietu Office na komputerach użytkowników końcowych <!-- 2971030 -->
Podczas instalowania pakietu Office na komputerach użytkowników końcowych przez usługę Intune użytkownicy końcowi automatycznie uzyskają te same pakiety językowe, które mieli z poprzednimi instalacjami pakietu Office MSI. 

<!-- 1809 start -->  

### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices----2244713---"></a>Ustawienia transferu danych aplikacji usługi Intune w urządzeniach z systemem iOS zarejestrowanych w oprogramowaniu MDM <!-- 2244713 -->
Będziesz mieć możliwość oddzielenia kontroli ustawień transferu danych aplikacji usługi Intune na urządzeniach z systemem iOS zarejestrowanych w oprogramowaniu MDM od określania tożsamości zarejestrowanego użytkownika. Administratorzy nieużywający narzędzia IntuneMAMUPN nie zaobserwują zmiany zachowania. Jeśli ta funkcja jest dostępna, administratorzy używający narzędzia IntuneMAMUPN do kontrolowania zachowania transferu danych na zarejestrowanych urządzeniach powinni przejrzeć nowe ustawienia i odpowiednio zaktualizować ustawienia aplikacji.

### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile----2662938---"></a>Używanie klucza wstępnego w profilu sieci Wi-Fi systemu Windows 10 <!-- 2662938 -->
Będziesz mieć możliwość użycia klucza wstępnego (PSK) z protokołem zabezpieczeń WPA/WPA2-Personal do uwierzytelniania profilu konfiguracji sieci Wi-Fi dla systemu Windows 10.
Obecnie trzeba zaimportować profil sieci Wi-Fi lub utworzyć profil niestandardowy, aby korzystać z klucza wstępnego. Obszar [Ustawienia sieci Wi-Fi dla systemu Windows 10](wi-fi-settings-windows.md) zawiera listę bieżących ustawień. 

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Ustawienia zasad ochrony aplikacji dla danych internetowych <!-- 2662995 -->
Ustawienia zasad ochrony aplikacji dla zawartości internetowej na urządzeniach z systemami Android i iOS zostaną zaktualizowane w celu ulepszenia obsługi linków internetowych http i https, a także przesyłania danych za pośrednictwem linków uniwersalnych systemu iOS i linków między aplikacjami systemu Android.  

### <a name="autopilot-device-sync-frequency-increasing-to-every-12-hours----2753673---"></a>Częstotliwość synchronizacji urządzeń rozwiązania Autopilot zwiększona do 12 godzin <!-- 2753673 -->
Urządzenia rozwiązania Autopilot będą synchronizowane co 12 godzin, zamiast co 24 godziny.

### <a name="intune-landing-page-updates-and-node-rename---2867309---"></a>Zmienianie nazwy węzła i aktualizacje strony docelowej usługi Intune <!--2867309 -->
Aktualizacje strony docelowej usługi Intune będą obejmować nowe i zmienione kafelki i wykresy służące do monitorowania, które poprawią jakość wizualizacji danych. Nazwa węzła **Aplikacje mobilne** zostanie zmieniona na **Aplikacje klienckie**.

### <a name="increased-end-user-access-using-the-company-portal-app----772203---"></a>Zwiększony dostęp użytkowników końcowych przy użyciu aplikacji Portal firmy <!-- 772203 -->
Użytkownicy końcowi będą mogli uzyskiwać dostęp do kluczowych akcji dotyczących kont, takich jak resetowanie haseł oraz profil usługi AAD, z aplikacji Portal firmy.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Token VPP firmy Apple używany przez inne rozwiązanie MDM <!-- 1488946 -->
Usługa Intune wykryje i wyświetli szczegółowe informacje, jeśli token programu VPP (Volume Purchase Program) jest używany zarówno przez usługę Intune, jak i inne rozwiązanie MDM.

### <a name="ios-version-number-and-build-number-are-shown----1892471---"></a>Numer wersji i numer kompilacji systemu iOS są wyświetlane <!-- 1892471 -->
W polu **Zgodność urządzenia** > **Zgodność urządzenia** jest wyświetlana wersja systemu operacyjnego iOS. W ramach przyszłej aktualizacji będzie także wyświetlany numer kompilacji.
Po wydaniu aktualizacji zabezpieczeń firma Apple zwykle pozostawia numer wersji bez zmian, lecz aktualizuje numer kompilacji. Wyświetlając numer kompilacji, można łatwo sprawdzić, czy aktualizacja luk w zabezpieczeniach została zainstalowana.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Wycofane urządzenia na pulpicie nawigacyjnym zgodności urządzeń <!-- 1981119 -->
W ramach przyszłej aktualizacji wycofane urządzenia zostaną usunięte z pulpitu nawigacyjnego zgodności urządzeń. Spowoduje to zmianę liczb dotyczących zgodności.


### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Zmiana w procesie aktualizacji łączników lokalnych <!-- 2277554 -->
Na podstawie opinii klientów zmienimy sposób aktualizacji łączników lokalnych. Po początkowej instalacji łącznika lokalnego aktualizacje będą wykonywane automatycznie. Ta zmiana rozpocznie się od nowego łącznika certyfikatów PFX usługi Microsoft Intune, a następnie będzie wdrażana dla innych typów łączników lokalnych. 

<!-- 1807 start -->

### <a name="improved-company-portal-app-experience-for-device-enrollment-manager-users----675800---"></a>Ulepszone środowisko aplikacji Portal firmy dla użytkowników menedżera rejestracji urządzeń <!-- 675800 -->
Gdy menedżer rejestracji urządzeń loguje się do aplikacji Portal firmy dla systemu Windows, w aplikacji będzie wyświetlane tylko bieżące, uruchomione urządzenie menedżera rejestracji urządzeń. To ulepszenie ograniczy występowanie przekroczeń limitu czasu, które wcześniej miały miejsce, gdy aplikacja podejmowała próbę załadowania wszystkich urządzeń zarejestrowanych w menedżerze rejestracji urządzeń.  

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Sprawdzanie zgodności w programie Configuration Manager <!-- 2192052 -->
Przyszła aktualizacja będzie zawierać nowe ustawienie zgodności programu System Center Configuration Manager (**Zgodność urządzeń** > **Zasady** > **Tworzenie zasad** > **System Windows 10**). Program Configuration Manager wysyła sygnały zgodności do usługi Intune. Przy użyciu ustawienia usługi Intune można wymagać, aby wszystkie sygnały programu Configuration Manager zwracały stan „zgodne”.

Na przykład można wymagać, aby na urządzeniach były zainstalowane wszystkie aktualizacje oprogramowania. W programie Configuration Manager to wymaganie ma stan „Zainstalowano”. Jeśli jakiekolwiek programy na urządzeniu mają nieznany stan, to urządzenie będzie niezgodne w usłudze Intune.

Dotyczy: system Windows 10 lub nowszy

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Alerty dotyczące wygasającego tokenu VPP lub zbyt małej liczby licencji aplikacji Portal firmy <!-- 2237572 -->
Jeśli do wstępnej aprowizacji aplikacji Portal firmy podczas rejestracji programu DEP jest używany token programu Volume Purchase Program (VPP), usługa Intune powiadomi Cię, jeśli token VPP niedługo wygaśnie lub zaczyna brakować licencji aplikacji Portal firmy.

<!-- 1806 start -->

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Klawiatury innych firm mogą zostać zablokowane przez ustawienia aplikacji w systemie iOS <!-- 1248481 -->
Na urządzeniach z systemem iOS administratorzy usługi Intune będą mogli zablokować możliwość korzystania z klawiatur innych firm podczas uzyskiwania dostępu do danych organizacji w aplikacjach chronionych przez zasady. Gdy zasady ochrony aplikacji są ustawione na blokowanie klawiatur innych firm, użytkownik urządzenia otrzyma komunikat podczas pierwszej próby interakcji z danymi firmowymi przy użyciu klawiatury innej firmy. Wszystkie opcje inne niż klawiatura macierzysta zostaną zablokowane, a użytkownicy urządzenia nie będą ich widzieć. Użytkownicy urządzenia zobaczą tylko raz komunikat w oknie dialogowym. 

<!-- 1805 start -->

### <a name="require-non-biometric-after-specified-timeout----1506985---"></a>Wymaganie danych niebiometrycznych po upłynięciu określonego limitu czasu <!-- 1506985 --> 

Wymagając niebiometrycznego kodu PIN po upłynięciu limitu czasu określonego przez administratora, usługa Intune zapewnia lepsze zabezpieczenia dla aplikacji z obsługą funkcji zarządzania aplikacjami mobilnymi (MAM) przez ograniczenie użycia identyfikacji biometrycznej na potrzeby dostępu do danych firmowych. Ustawienia będą miały wpływ na użytkowników, którzy korzystają z funkcji Touch ID (iOS), Face ID (iOS), Android Biometric lub innych przyszłych metod uwierzytelniania biometrycznego w celu uzyskiwania dostępu do swoich aplikacji z obsługą zasad ochrony aplikacji/funkcji MAM. Ustawienia te umożliwią administratorom usługi Intune uzyskanie większej kontroli nad dostępem użytkowników, eliminując przypadki, gdy urządzenie z wieloma odciskami palców lub innymi biometrycznymi metodami dostępu może ujawnić dane firmowe niewłaściwemu użytkownikowi. W witrynie Azure Portal otwórz usługę **Microsoft Intune**. Wybierz pozycję **Aplikacje mobilne** > **Zasady ochrony aplikacji** > **Dodaj zasadę** > **Ustawienia**. Znajdź sekcję **Dostęp** dla konkretnych ustawień.

<!-- 1803 start -->

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Aktualizowanie środowiska Pomoc i opinie w aplikacji Portal firmy dla systemu Android <!--1631531 -->

Środowisko Pomoc i opinie w aplikacji Portal firmy dla systemu Android zostanie zaktualizowane, aby było zgodne z najlepszymi rozwiązaniami dla aplikacji systemu Android. W ciągu kilku następnych miesięcy aplikacja Portal firmy dla systemu Android zostanie zaktualizowana, aby podzielić element menu **Pomoc i opinie** na oddzielne elementy **Pomoc** i **Prześlij opinię**. Strona **Pomoc** będzie zawierała sekcję **Często zadawane pytania** oraz przycisk **Pomoc techniczna pocztą e-mail**, który umożliwi użytkownikom końcowym przekazanie dzienników firmie Microsoft i wysłanie wiadomości e-mail do pomocy technicznej firmy wraz z opisem problemu. Funkcja **Prześlij opinię** przeprowadzi użytkownika przez standardowy proces przesyłania opinii, podczas którego użytkownik będzie mógł wybrać opcje takie jak „Coś mi się podoba”, „Coś mi się nie podoba”, „Mam pomysł”.



<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Uwagi

Aktualnie nie ma aktywnych powiadomień.

### <a name="see-also"></a>Zobacz też
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).



