---
title: "Co nowego w usłudze Microsoft Intune"
titlesuffix: Azure portal
description: "Dowiedz się, co nowego w witrynie Azure Portal usługi Intune"
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 861d28b75d72a2784fc1c73a6f770d44cf1a21b3
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="whats-new-in-microsoft-intune"></a>Co nowego w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Dowiedz się co tydzień, co nowego w usłudze Microsoft Intune. Możesz również dowiedzieć się o [nadchodzących zmianach](#whats-coming), [ważnych powiadomieniach](#notices) o usłudze oraz uzyskać informacje o [poprzednich wersjach](whats-new-archive.md).

> [!Note]
> Aby uzyskać informacje na temat nowych funkcji w ramach hybrydowego zarządzania urządzeniami przenośnymi, odwiedź stronę [ Co nowego w funkcjach hybrydowych](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Role-based access control
  ### Intune apps
  ### Monitor and troubleshoot

-->   

## <a name="week-of-january-22-2018"></a>Tydzień od 22 stycznia 2018 r.

### <a name="intune-apps"></a>Aplikacje usługi Intune

#### <a name="remote-lock-available-in-company-portal-app-for-windows-10---676506--"></a>Zdalne blokowanie dostępne w aplikacji Portal firmy dla systemu Windows 10 <!--676506-->
Użytkownicy końcowi mogą teraz zdalnie blokować swoje urządzenia w aplikacji Portal firmy dla systemu Windows 10. Opcja nie będzie wyświetlana dla wybranego urządzenia lokalnego, którego aktywnie używają.

#### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546--"></a>Łatwiejsze rozwiązywanie problemów ze zgodnością aplikacji Portal firmy dla systemu Windows 10<!--676546-->
Użytkownicy końcowi mający urządzenia z systemem Windows będą mogli wybierać przyczynę niezgodności w aplikacji Portal firmy. Gdy będzie to możliwe, przeniesie to ich bezpośrednio do poprawnej lokalizacji w aplikacji ustawień, aby rozwiązać ten problem.

## <a name="week-of-december-11-2017"></a>Tydzień 11 grudnia 2017 r.

### <a name="device-configuration"></a>Konfiguracja urządzenia

#### <a name="new-automatic-redeployment-setting----1469168---"></a>Nowe ustawienie automatycznego ponownego wdrażania<!-- 1469168 -->
Ustawienie **Automatyczne ponowne wdrażanie** pozwala użytkownikom z uprawnieniami administracyjnymi usunąć wszystkie dane użytkownika i ustawienia za pomocą kombinacji klawiszy **CTRL+Win+R** na ekranie blokady urządzenia. Urządzenie jest automatycznie ponownie konfigurowane i rejestrowane do zarządzania. To ustawienie można znaleźć w obszarze Windows 10 > Ograniczenia dotyczące urządzeń > Ogólne > Automatyczne ponowne wdrażanie. Aby uzyskać szczegółowe informacje, zobacz [Ustawienia ograniczeń urządzenia z systemem Windows 10 w usłudze Intune](device-restrictions-windows-10.md#general).

#### <a name="support-for-additional-source-editions-in-the-windows-10-edition-upgrade-policy-----903672--1119689---"></a>Obsługa dodatkowych wersji źródła w zasadach uaktualniania wersji systemu Windows 10 <!-- 903672,  1119689 -->
Zasady uaktualniania wersji systemu Windows 10 umożliwiają teraz uaktualnianie dodatkowych wersji systemu Windows 10 (Windows 10 Pro, Windows 10 Pro for Education, Windows 10 Cloud itp.). Przed tą wersją obsługiwane ścieżki uaktualniania wersji były bardziej ograniczone. Więcej szczegółów znajduje się w temacie [Jak skonfigurować uaktualnienia wersji systemu Windows 10](edition-upgrade-configure-windows-10.md).

#### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Nowe ustawienia profilu konfiguracji urządzenia w aplikacji Windows Defender Security Center (WDSC)<!-- 1335507 -->

Usługa Intune została wzbogacona o nową sekcję ustawień profilu konfiguracji urządzenia w obszarze Ochrona punktu końcowego o nazwie **Windows Defender Security Center**. Administratorzy IT mogą skonfigurować, do których filarów aplikacji Windows Defender Security Center użytkownicy końcowi mogą uzyskać dostęp. Jeśli administrator IT ukrywa filar w aplikacji Windows Defender Security Center, wszystkie powiadomienia powiązane z ukrytym filarem nie będą wyświetlane na urządzeniu użytkownika.

Poniżej wymieniono filary, które administratorzy mogą ukryć w ustawieniach profilu konfiguracji urządzenia w aplikacji Windows Defender Security Center:
- Ochrona przed wirusami i zagrożeniami
- Wydajność i kondycja urządzenia
- Zapora i ochrona sieci
- Kontrola aplikacji i przeglądarki
- Opcje rodziny

Administratorzy IT mogą również dostosować to, które powiadomienia będą otrzymywać użytkownicy. Na przykład można określić, czy użytkownicy będą otrzymywać wszystkie powiadomienia generowane w ramach widocznych filarów w aplikacji WDSC, czy tylko powiadomienia krytyczne. Powiadomienia niekrytyczne obejmują okresowe podsumowania działania programu antywirusowego Windows Defender i powiadomienia po zakończeniu skanowania. Wszystkie pozostałe powiadomienia są traktowane jako krytyczne. Ponadto można również dostosować zawartość powiadomień, na przykład można podać informacje kontaktowe do działu IT do osadzenia w powiadomieniach wyświetlanych na rządzeniach użytkowników.

#### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling----1361755---"></a>Obsługa wielu łączników na potrzeby obsługi certyfikatów protokołu SCEP i PFX <!-- 1361755 -->

Klienci, którzy korzystają z lokalnego łącznika usługi NDES w celu dostarczania certyfikatów do urządzeń, mogą teraz skonfigurować wiele łączników w jednej dzierżawie.

Ta nowa możliwość obsługuje następujący scenariusz:

- **Wysoka dostępność**

Każdy łącznik usługi NDES ściąga żądania certyfikatu z usługi Intune.  Jeśli jeden łącznik usługi NDES przejdzie do trybu offline, inny łącznik może dalej przetwarzać żądania.

#### <a name="customer-subject-name-can-use-aaddeviceid-variable-----1468599---"></a>Nazwa podmiotu klienta może zawierać zmienną AAD_DEVICE_ID <!-- 1468599 -->

Tworząc profil certyfikatu SCEP w usłudze Intune, można teraz użyć zmiennej AAD_DEVICE_ID podczas kompilowania niestandardowej nazwy podmiotu.   Gdy żądanie certyfikatu jest przesyłane przy użyciu tego profilu SCEP, zmienna jest zastępowana identyfikatorem urządzenia usługi AAD należącym do urządzenia wysyłającego żądanie certyfikatu.


### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine----1592747---"></a>Zarządzanie urządzeniami z systemem macOS zarejestrowanymi w programie Jamf przy użyciu aparatu zgodności urządzenia usługi Intune <!-- 1592747 -->
Korzystając z programu Jamf, można teraz wysyłać informacje o stanie urządzenia z systemem macOS do usługi Intune, która następnie oceni je pod kątem zgodności z zasadami określonymi w konsoli usługi Intune. W oparciu o stan zgodności urządzenia, a także pozostałe warunki (takie jak lokalizacja, ryzyko związane z użytkownikiem itp.) dostęp warunkowy będzie wymuszać zgodność dla urządzeń z systemem macOS uzyskujących dostęp do chmury i lokalnych aplikacji połączonych z usługą Azure Active Directory oraz usługą Office 365. Dowiedz się więcej o [konfigurowaniu integracji programu Jamf](conditional-access-integrate-jamf.md) i [wymuszaniu zgodności dla urządzeń zarządzanych przez program Jamf](conditional-access-assign-jamf.md).

#### <a name="new-ios-device-action------1424701---"></a>Nowa akcja dotycząca urządzenia z systemem iOS <!-- 1424701 -->

Możliwe jest teraz zamykanie nadzorowanych urządzeń z systemem iOS 10.3. Ta akcja natychmiast wyłącza urządzenie bez ostrzeżenia dla użytkownika końcowego. Akcję **Wyłącz (tylko nadzorowane)** można znaleźć we właściwościach urządzenia po wybraniu urządzenia w obciążeniu **Urządzenie**.

#### <a name="disallow-datetime-changes-to-samsung-knox-devices----1468103---"></a>Blokowanie zmian daty/godziny na urządzeniach z systemem Samsung Knox<!-- 1468103 -->

Dodaliśmy nową funkcję, która pozwala na blokowanie zmian daty i godziny na urządzeniach z systemem Samsung Knox. Ta funkcja jest dostępna po wybraniu opcji **Profile konfiguracji urządzeń** > **Ograniczenia dotyczące urządzeń (Android)** > **Ogólne**.

#### <a name="surface-hub-resource-account-supported----1566442----"></a>Obsługa konta zasobu Surface Hub <!-- 1566442  -->

Dodano nową akcję urządzenia, która umożliwia administratorom określanie i aktualizowanie konta zasobu skojarzonego z rozwiązaniem Surface Hub.

Konto zasobu jest używane przez rozwiązanie Surface Hub do uwierzytelniania w programie Skype/Exchange, co pozwala przyłączyć je do spotkania. Można utworzyć unikatowe konto zasobu, aby rozwiązanie Surface Hub było wyświetlane w spotkaniu jako sala konferencyjna. Na przykład konto zasobu może być widoczne jako *Sala konferencyjna B41/6233*. Konto zasobu (nazywane kontem urządzenia) dla rozwiązania Surface Hub zwykle trzeba skonfigurować dla lokalizacji sali konferencyjnej i gdy trzeba zmienić inne parametry konta zasobu.

Gdy administratorzy chcą zaktualizować konto zasobu na urządzeniu, muszą podać bieżące poświadczenia usługi Active Directory/Azure Active Directory skojarzone z tym urządzeniem. Jeśli dla urządzenia jest włączona funkcja rotacji haseł, administratorzy muszą przejść do usługi Azure Active Directory, aby znaleźć hasło.

> [!NOTE]
> Wszystkie pola są wysyłane w pakiecie i zastępują wszystkie pola skonfigurowane wcześniej. Puste pola również zastępują pola istniejące.

Poniżej przedstawiono ustawienia, które mogą skonfigurować administratorzy:

- **Konto zasobu**
   - **Użytkownik Active Directory**

      Nazwa_domeny\nazwa_użytkownika lub główna nazwa użytkownika (UPN): user@domainname.com

   - **Hasło**

- **Opcjonalne parametry konta zasobu** (trzeba je ustawić przy użyciu określonego konta zasobu)

   - **Okres rotacji hasła**

     Ze względów bezpieczeństwa zapewnia co tydzień automatyczną aktualizację hasła konta przez rozwiązanie Surface Hub. Aby skonfigurować jakiekolwiek parametry po włączeniu tej opcji, należy najpierw zresetować hasło konta w usłudze Azure Active Directory.

   - **Adres SIP (Session Initiation Protocol)**

     Używany tylko wtedy, gdy wykrywanie automatyczne zakończy się niepowodzeniem.

   - **Poczta e-mail**

     Adres e-mail konta urządzenia/zasobu.

   - **Serwer Exchange**

     Wymagany tylko wtedy, gdy wykrywanie automatyczne zakończy się niepowodzeniem.

   - **Synchronizacja kalendarza**

     Określa, czy jest włączona synchronizacja kalendarza oraz pozostałe usługi serwera Exchange. Na przykład: synchronizacja spotkania.

#### <a name="install-office-apps-on-macos-devices----1494311---"></a>Instalacja aplikacji pakietu Office na urządzeniach z systemem macOS<!-- 1494311 -->
Można teraz instalować aplikacje pakietu Office na urządzeniach z systemem macOS. Ten nowy typ aplikacji umożliwi instalację programów Word, Excel, PowerPoint, Outlook i OneNote. Do aplikacji dołączony jest program Microsoft AutoUpdate (MAU), który pomaga zapewnić ich bezpieczeństwo i aktualność.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>Usuwanie tokenu programu zakupów zbiorczych dla systemu iOS <!-- 820879 -->
Istnieje możliwość usunięcia tokenu programu Volume Purchasing Program (VPP) systemu iOS przy użyciu konsoli. Może to być konieczne w przypadku występowania zduplikowanych wystąpień tokenu programu VPP.

### <a name="intune-apps"></a>Aplikacje usługi Intune

#### <a name="end-user-messaging-for-accounts---1573558-for-1712--"></a>Komunikaty dla użytkowników końcowych dotyczące kont <!--1573558 for 1712-->

Użytkownicy witryny Portal firmy będą mieć zablokowaną możliwość podejmowania działań, które wymagają prawa do zapisu w dzierżawie. Zostanie wyświetlony odpowiedni komunikat o błędzie z wyjaśnieniem, że konto podlega pracom konserwacyjnym. Podobne zmiany zostaną wkrótce wprowadzone w aplikacjach Portal firmy dla systemów Android, iOS, macOS i Windows. Informacje na temat tego błędu można znaleźć w temacie [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).



### <a name="role-based-access-control"></a>Kontrola dostępu oparta na rolach

#### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1667026---"></a>Nowa kolekcja jednostek o nazwie Bieżący użytkownik jest ograniczona do danych aktualnie aktywnych użytkowników <!-- 1667026 -->

Kolekcja jednostek **Users** zawiera listę wszystkich użytkowników usługi Azure Active Directory (Azure AD) w przedsiębiorstwie wraz z przypisanymi licencjami. Na przykład w ciągu ostatniego miesiąca użytkownik mógł zostać dodany do usługi Intune, a następnie z niej usunięty. Chociaż ten użytkownik nie występuje w chwili tworzenia raportu, on i jego stan znajdują się jednak w danych. Możesz utworzyć raport, który pokazuje okres historycznej obecności użytkownika w Twoich danych.

Z kolei nowa kolekcja jednostek **Bieżący użytkownik** zawiera tylko tych użytkowników, którzy nie zostali usunięci. Kolekcja jednostek **Bieżący użytkownik** zawiera tylko aktualnie aktywnych użytkowników. Aby uzyskać informacje o kolekcji jednostek **bieżącego użytkownika**, zobacz temat [Dokumentacja jednostki bieżącego użytkownika](reports-ref-current-user.md).


### <a name="updated-graph-apis----1736360---"></a>Zaktualizowane interfejsy API programu Graph <!-- 1736360 -->

W tej wersji zaktualizowaliśmy kilka interfejsów API programu Graph dla usługi Intune, które są dostępne w wersji beta. Aby uzyskać więcej informacji, sprawdź miesięczny [dziennik zmian interfejsu API programu Graph](https://developer.microsoft.com/graph/docs/concepts/changelog).


## <a name="week-of-december-4-2017"></a>Tydzień 4 grudnia 2017 r.

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="intune-supports-windows-information-protection-wip-denied-apps----1479103---"></a>Usługa Intune obsługuje niedozwolone aplikacje rozwiązania Windows Information Protection <!-- 1479103 -->
Niedozwolone aplikacje można określić w usłudze Intune. Jeśli aplikacja zostanie ustawiona jako niedozwolona, nie może uzyskiwać dostępu do informacji firmowych. Jest to sytuacja odwrotna, co w przypadku listy dozwolonych aplikacji. Aby uzyskać więcej informacji, zobacz [Zalecana lista niedozwolonych aplikacji na potrzeby rozwiązania Windows Information Protection](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp?f=255&MSPPError=-2147217396#recommended-deny-list-for-windows-information-protection).


## <a name="week-of-november-27-2017"></a>Tydzień 27 listopada 2017 r.

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="troubleshoot-enrollment-issues-----746324---"></a>Rozwiązywanie problemów z rejestracją <!-- 746324 -->

Problemy z rejestracją są teraz widoczne dla użytkownika w obszarze roboczym **Rozwiązywanie problemów**. Szczegółowe informacje o problemie i sugerowane kroki korygujące mogą ułatwić administratorom i operatorom pomocy technicznej rozwiązywanie problemów. Niektóre problemy z rejestracją nie są rejestrowane i dla niektórych błędów może nie być sugestii korekty.

#### <a name="group-assigned-enrollment-restrictions----747598---"></a>Ograniczenia rejestracji przypisane do grupy <!-- 747598 -->

Administratorzy usługi Intune będą mogli [tworzyć niestandardowe ograniczenia rejestracji dotyczące typu urządzeń i limitu urządzeń dla grup użytkowników](enrollment-restrictions-set.md).

Witryna Azure Portal usługi Intune pozwala utworzyć maksymalnie 25 wystąpień poszczególnych typów ograniczeń, które można przypisać do grup użytkowników. Ograniczenia przypisane do grupy zastępują ograniczenia domyślne.

Wszystkie wystąpienia typu ograniczenia są przechowywane na ściśle uporządkowanej liście. Porządek ten określa wartości priorytetów na potrzeby rozwiązywania konfliktów. Jeśli użytkownika dotyczy więcej niż jedno wystąpienie ograniczeń, pod uwagę brane jest tylko wystąpienie o najwyższej wartości priorytetu. Priorytet danego wystąpienia można zmienić, przeciągając je do innej pozycji na liście.

Funkcja ta zostanie udostępniona podczas migracji ustawień programu Android for Work z menu rejestracji programu Android for Work do menu ograniczeń rejestracji. Ponieważ ta migracja może zająć kilka dni, zanim zostanie włączone przypisanie grupy do ograniczeń rejestracji, konto może zostać uaktualnione o inne funkcje wprowadzane w wersji listopadowej.

#### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Obsługa wielu łączników usługi rejestracji urządzeń sieciowych (NDES) <!-- 1528104 -->

Usługa rejestracji urządzeń sieciowych (Network Device Enrollment Service, NDES) umożliwia urządzeniom przenośnym działającym bez poświadczeń domeny uzyskiwanie certyfikatów przy użyciu dodatku Prosty protokół rejestrowania certyfikatów (Simple Certificate Enrollment Protocol, SCEP).
Aktualizacja wprowadza obsługę wielu łączników usługi NDES.

#### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Zarządzanie urządzeniami programu Android for Work w sposób niezależny od urządzeń z systemem Android <!-- 1490731 EEready-->

**Uwaga:** następujące zmiany zostaną wprowadzone wraz z listopadową aktualizacją, ale ich wdrożenie na danym koncie może trochę potrwać. Gdy zmiany zostaną zastosowane na Twoim koncie, otrzymasz powiadomienie w portalu usługi Office 365. Po wprowadzeniu aktualizacji zyskasz dodatkowe możliwości zarządzania. Aktualizacja nie wprowadza zmian w środowisku użytkownika końcowego.

Usługa Intune obsługuje zarządzanie rejestracją urządzeń programu Android for Work w sposób niezależny od platformy Android. Opcje zarządzania tymi ustawieniami są dostępne w obszarze **Rejestrowanie urządzenia** > **Ograniczenia rejestracji** > **Ograniczenia typów urządzeń**. (Wcześniej znajdowały się one w obszarze **Rejestrowanie urządzeń** > **Rejestracja w programie Android for Work** > **Ustawienia rejestracji programu Android for Work**).

Domyślnie ustawienia urządzeń programu Android for Work są takie same jak ustawienia urządzeń z systemem Android. Nie będzie tak jednak w przypadku zmiany ustawień programu Android for Work.

Jeśli zablokujesz rejestrację urządzeń osobistych w programie Android for Work, będzie można rejestrować tylko firmowe urządzenia z systemem Android.

Podczas pracy z nowymi ustawieniami zwróć uwagę na następujące kwestie:

##### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Jeśli wcześniej nie dodano rejestracji w programie Android for Work

Nowa platforma Android for Work jest zablokowana w domyślnych ograniczeniach typów urządzeń. Po dodaniu tej funkcji możesz zezwolić urządzeniom na rejestrację w programie Android for Work. Aby to zrobić, zastąp domyślne ograniczenie typów urządzeń — zmień je lub utwórz nowe ograniczenie.

##### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Jeśli dodano rejestrację w programie Android for Work

Jeśli wcześniej dołączono do programu, sytuacja zależy od wybranego ustawienia:

| Ustawienie | Stan programu Android for Work w domyślnym ograniczeniu typów urządzeń | Uwagi |
| --- | --- | --- |
| **Zarządzaj wszystkimi urządzeniami jako urządzeniami z systemem Android** | Zablokowane | Wszystkie urządzenia z systemem Android należy zarejestrować bez programu Android for Work. |
| **Zarządzaj obsługiwanymi urządzeniami jako urządzeniami z programem Android for Work** | Dozwolone | Wszystkie urządzenia z systemem Android, które obsługują program Android for Work, należy zarejestrować w programie Android for Work. |
| **Zarządzaj obsługiwanymi urządzeniami jako urządzeniami z programem Android for Work tylko dla użytkowników w tych grupach** | Zablokowane | Utworzono oddzielne zasady ograniczeń typów urządzeń, które przesłaniają domyślne zasady. Zasady te definiują wcześniej wybrane grupy, zezwalając na rejestrację w programie Android for Work. Użytkownicy z wybranych grup zachowają możliwość rejestrowania urządzeń programu Android for Work. Pozostali użytkownicy nie mogą rejestrować się w programie Android for Work. |

We wszystkich przypadkach zamierzone zasady są zachowywane. Nie są wymagane żadne działania użytkownika w celu zachowania możliwości korzystania z programu Android for Work w środowisku — zarówno w skali ogólnej, jak i w odniesieniu do poszczególnych grup.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="app-install-report-updated-to-include-install-pending-status----1249446---"></a>Raport instalacji aplikacji został zaktualizowany, aby obejmować stan Oczekująca instalacja <!-- 1249446 -->  

Raport o **stanie instalacji aplikacji**, dostępny dla każdej aplikacji za pośrednictwem listy **Aplikacja** w obciążeniu **Aplikacje mobilne**, zawiera teraz licznik **Oczekująca instalacja** dla użytkowników i urządzeń.

#### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>Interfejs API spisu aplikacji dla systemu iOS 11 na potrzeby wykrywania zagrożeń mobilnych<!-- 1391759 -->

Usługa Intune zbiera informacje dotyczące spisu aplikacji zarówno z urządzeń osobistych, jak i firmowych i udostępnia je dostawcom usługi wykrywania zagrożeń mobilnych, na przykład aplikacji Lookout for Work. Możesz zbierać informacje o spisie aplikacji z urządzeń z systemem iOS 11 lub nowszym.

**Spis aplikacji**  
Spisy pochodzące zarówno z urządzeń osobistych, jak i urządzeń firmowych z systemem iOS 11 lub nowszym są wysyłane do dostawcy usługi MTD. Spis aplikacji zawiera następujące dane:

 - Identyfikator aplikacji
 - Wersja aplikacji
 - Krótki numer wersji
 - Nazwa aplikacji
 - Rozmiar pakietu aplikacji
 - Dynamiczny rozmiar aplikacji
 - Wskazanie, czy aplikacja została zweryfikowana
 - Wskazanie, czy aplikacja jest zarządzana


### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="migrate-hybrid-mdm-users-and-devices-to-intune-standalone----1463747-wnready---"></a>Migrowanie użytkowników i urządzeń hybrydowego zarządzania urządzeniami przenośnymi do autonomicznej usługi Intune <!-- 1463747 wnready -->
Istnieje nowy proces i narzędzia służące do przenoszenia użytkowników i ich urządzeń z hybrydowego zarządzania urządzeniami przenośnymi do usługi Intune w witrynie Azure Portal, co umożliwia wykonywanie następujących czynności:
- Kopiowanie zasad i profilów z konsoli programu Configuration Manager do usługi Intune w witrynie Azure Portal
- Przenoszenie podzbioru użytkowników do usługi Intune w witrynie Azure Portal przy zachowaniu pozostałych w ramach hybrydowego zarządzania urządzeniami przenośnymi
- Migrowanie urządzeń do usługi Intune w witrynie Azure Portal bez konieczności ich ponownego rejestrowania

Aby uzyskać więcej informacji, zobacz [Migrowanie użytkowników i urządzeń hybrydowego zarządzania urządzeniami przenośnymi do autonomicznej usługi Intune](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa).

#### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Obsługa wysokiej dostępności łącznika lokalnego programu Exchange <!-- 676614 -->
Gdy łącznik programu Exchange utworzy połączenie z programem Exchange za pomocą określonego zabezpieczenia dostępu kodu, będzie mieć możliwość odnajdywania innych zabezpieczeń dostępu kodu. Jeśli podstawowe zabezpieczenia dostępu kodu będą niedostępne, łącznik przejdzie w tryb failover, korzystając z innych zabezpieczeń dostępu kodu (jeśli będą dostępne) do momentu przywrócenia dostępności podstawowych zabezpieczeń dostępu kodu. Szczegółowe informacje znajdują się w temacie [Obsługa wysokiej dostępności łącznika lokalnego programu Exchange](exchange-connector-install.md#on-premises-exchange-connector-high-availability-support).

#### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>Zdalne ponowne uruchamianie urządzenia z systemem iOS (tylko tryb nadzorowany) <!-- 1424595 -->

Przy użyciu akcji urządzenia możesz teraz wyzwolić ponowne uruchomienie nadzorowanego urządzenia z systemem iOS 10.3 lub nowszym. Aby uzyskać więcej informacji na temat używania akcji ponownego uruchamiania urządzenia, zobacz [Zdalne ponowne uruchamianie urządzeń przy użyciu usługi Intune](device-restart.md).

> [!Note]
> To polecenie wymaga trybu nadzorowanego urządzenia i prawa dostępu do **blokady urządzenia**. Urządzenie jest natychmiast uruchamiane ponownie. Urządzenia z systemem iOS z blokadą opartą na kodzie dostępu nie połączą się z siecią Wi-Fi po ponownym uruchomieniu. Ponadto nawiązanie połączenia z serwerem może nie być możliwe.

#### <a name="single-sign-on-support-for-ios----1333645---"></a>Obsługa logowania jednokrotnego dla systemu iOS <!-- 1333645 -->  

Użytkownicy systemu iOS mogą korzystać z logowania jednokrotnego. Aplikacje dla systemu iOS, które poszukują poświadczeń użytkownika w ładunku logowania jednokrotnego, zachowują swoją funkcjonalność po zaktualizowaniu konfiguracji ładunku. Nazwę główną i obszar można również skonfigurować przy użyciu nazwy UPN i identyfikatora urządzenia w usłudze Intune. Aby uzyskać szczegółowe informacje, zobacz [Konfigurowanie logowania jednokrotnego w usłudze Intune dla urządzeń z systemem iOS](sso-ios.md).

#### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Dodanie aplikacji „Znajdź mój iPhone” dla urządzeń osobistych <!--1427287-->
Może teraz sprawdzić, czy urządzenia z systemem iOS mają włączoną blokadę aktywacji. Funkcja ta była wcześniej dostępna w klasycznym portalu usługi Intune.


#### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Zdalne blokowanie urządzeń zarządzanych z systemem macOS przy użyciu usługi Intune <!-- 1437691 -->

Zgubione urządzenie z systemem macOS można zablokować przez ustawienie 6-cyfrowego numeru PIN odzyskiwania. Gdy blokada jest aktywna, do momentu wysłania innej akcji urządzenia na ekranie jest widoczny blok **Przegląd urządzenia** z monitem o numer PIN.

Aby uzyskać więcej informacji, zobacz [Zdalne blokowanie urządzeń zarządzanych przy użyciu usługi Intune](device-remote-lock.md).

#### <a name="new-scep-profile-details-supported----1559808---"></a>Obsługa nowych szczegółów profilu SCEP <!-- 1559808 -->

Administratorzy mogą teraz określić dodatkowe ustawienia podczas tworzenia profilu SCEP na platformach Windows, iOS, macOS i Android.  Można na przykład ustawić kod IMEI, numer seryjny lub nazwę pospolitą obejmującą adres e-mail w formacie nazwy podmiotu.

<!-- #### Update to what device details your company may see -1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources. -->

#### <a name="retain-data-during-a-factory-reset----1588489---"></a>Zachowywanie danych podczas resetowania do ustawień fabrycznych <!--1588489 -->
W przypadku resetowania do ustawień fabrycznych systemu Windows 10 w wersji 1709 oraz nowszych dostępna jest nowa funkcja. Administratorzy mogą wskazać, czy informacje o rejestracji urządzenia i inne aprowizowane dane mają zostać zachowane podczas resetowania urządzenia do ustawień fabrycznych.

Podczas resetowania do ustawień fabrycznych są zachowywane następujące dane:
- Konta użytkowników skojarzone z urządzeniem
- Stan komputera (dołączenie do domeny, dołączenie do usługi Azure Active Directory)
- Rejestracja w usłudze zarządzania urządzeniami przenośnymi
- Aplikacje zainstalowane przez producenta OEM (aplikacje ze Sklepu i aplikacje Win32)
- Profil użytkownika
- Dane użytkownika przechowywane poza profilem użytkownika
- Informacje o logowaniu automatycznym użytkownika

Następujące dane nie są zachowywane:
- Pliki użytkownika
- Aplikacje zainstalowane przez użytkownika (aplikacje ze Sklepu i aplikacje Win32)
- Ustawienia urządzenia inne niż domyślne

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów
#### <a name="window-10-update-ring-assignments-are-displayed----1621837---"></a>Wyświetlanie przypisań pierścienia aktualizacji systemu Windows 10 <!-- 1621837 -->
Podczas **rozwiązywania problemów** są widoczne wszystkie przypisania pierścieni aktualizacji systemu Windows 10 dla aktualnie wybranego użytkownika.  

#### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings-----1455974----"></a>Ustawienia częstotliwości raportowania usługi Zaawansowana ochrona przed zagrożeniami usługi Windows Defender <!-- 1455974  -->
Usługa Zaawansowana ochrona przed zagrożeniami usługi Windows Defender (WDATP, Windows Defender Advanced Threat Protection) pozwala administratorom zmieniać częstotliwość raportowania dla zarządzanych urządzeń. Nowa opcja — **Usprawnij częstotliwość raportowania danych telemetrycznych** — umożliwia usłudze WDATP częstsze zbieranie danych i ocenianie ryzyka. Domyślne ustawienie raportowania pozwala zoptymalizować szybkość i wydajność. Zwiększenie częstotliwości raportowania może być przydatne w przypadku urządzeń narażonych na wysokie ryzyko. To ustawienie znajduje się w profilu usługi **Windows Defender ATP** w **konfiguracji urządzeń**.

#### <a name="audit-updates----1412961---"></a>Aktualizacje inspekcji <!-- 1412961 -->  
Inspekcje w usłudze Intune udostępniają rejestr operacji zmian dotyczących usługi Intune.  Wszystkie operacje tworzenia, aktualizowania, usuwania i zadań zdalnych są przechwytywane i przechowywane przez jeden rok.  Witryna Azure Portal udostępnia filtrowany widok danych inspekcji poszczególnych obciążeń z ostatnich 30 dni.  Dostępny jest odpowiedni interfejs API programu Graph, umożliwiający pobieranie danych inspekcji z ostatniego roku.

Inspekcje można znaleźć w grupie **MONITOR**. Dla każdego obciążenia dostępny jest element menu **Dzienniki inspekcji**.




## <a name="week-of-november-20-2017"></a>Tydzień 20 listopada 2017 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="google-play-protect-support-on-android----908720---"></a>Obsługa funkcji Google Play Protect w urządzeniach z systemem Android <!-- 908720 -->

Wraz z wydaniem systemu Android Oreo firma Google wprowadza zestaw funkcji zabezpieczających Google Play Protect, który umożliwia użytkownikom i organizacjom uruchamianie bezpiecznych aplikacji oraz bezpiecznych obrazów dla systemu Android. Usługa Intune obsługuje funkcje Google Play Protect, w tym funkcję zdalnego zaświadczania SafetyNet. Administratorzy mogą ustawić wymagania dotyczące zasad zgodności, które wymuszą konfigurację funkcji Google Play Protect oraz zapewnienie jej prawidłowego działania.
Ustawienie **zdalnego zaświadczania SafetyNet** wymaga połączenia się urządzenia z usługą Google w celu umożliwienia sprawdzenia, czy urządzenie jest w dobrej kondycji i czy jego zabezpieczenia nie zostały złamane. Administratorzy mogą również wybrać ustawienie profilu konfiguracji dla programu Android for Work, co spowoduje wprowadzenie wymogu, aby zainstalowane aplikacje były weryfikowane przez usługi Google Play. Dostęp warunkowy może uniemożliwić użytkownikom uzyskiwanie dostępu do zasobów firmy, jeśli urządzenie nie jest zgodne z wymaganiami funkcji Google Play Protect.

- Dowiedz się [Jak utworzyć zasady zgodności urządzenia w celu włączenia funkcji Google Play Protect](https://docs.microsoft.com/intune/compliance-policy-create-google-play-protect).

#### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Protokół tekstowy dostępny w aplikacjach zarządzanych <!-- 1414050  -->

Aplikacje zarządzane przez zestaw SDK aplikacji usługi Intune mogą wysyłać wiadomości SMS.

## <a name="week-of-november-13-2017"></a>Tydzień 13 listopada 2017 r.

### <a name="intune-apps"></a>Aplikacje usługi Intune
#### <a name="company-portal-app-for-macos-is-available---1541700--"></a>Aplikacja Portal firmy dla systemu macOS jest dostępna <!--1541700-->
Aplikacja Portal firmy w usłudze Intune dla systemu macOS została zaktualizowana i zoptymalizowana, aby prawidłowo wyświetlać wszystkie informacje i powiadomienia o zgodności potrzebne użytkownikom do wszystkich zarejestrowanych urządzeń. Po wdrożeniu aplikacji Portal firmy w usłudze Intune na urządzeniu usługa Microsoft AutoUpdate dla systemu macOS zapewni jej aktualizacje. Nową wersję aplikacji Portal firmy w usłudze Intune dla systemu macOS można pobrać, logując się do witryny sieci Web aplikacji Portal firmy w usłudze Intune przy użyciu urządzenia z systemem macOS.

#### <a name="microsoft-planner-is-now-part-of-the-mobile-app-management-mam-list-of-approved-apps-----1248473---"></a>Aplikacja Microsoft Planner znajduje się obecnie na liście zarządzania aplikacjami mobilnymi (MAM) zawierającej zatwierdzone aplikacje<!-- 1248473 -->
Aplikacja Microsoft Planner dla systemów iOS i Android należy obecnie do zatwierdzonych aplikacji funkcji zarządzania aplikacjami mobilnymi (MAM). Aplikację można skonfigurować za pomocą bloku Intune App Protection w witrynie Azure Portal na potrzeby wszystkich dzierżaw.
- Więcej informacji znajduje się na [liście zatwierdzonych aplikacji w funkcji zarządzania aplikacjami mobilnymi ](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

#### <a name="per-app-vpn-requirement-update-frequency-on-ios-devices------1547061---"></a>Częstotliwość aktualizacji wymagań dotyczących sieci VPN dla aplikacji na urządzeniach z systemem iOS <!-- 1547061 -->  
Administratorzy mogą obecnie usuwać wymagania dotyczące sieci VPN dla aplikacji na urządzeniach z systemem iOS; operacja obejmie urządzenia po kolejnym zaewidencjonowaniu w usłudze Intune, które zwykle następuje w ciągu 15 minut.  

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów
#### <a name="support-for-system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Obsługa pakietu administracyjnego programu System Center Operations Manager dla łącznika programu Exchange <!-- 885457 -->
Pakiet administracyjny programu System Center Operations Manager (SCOM) dla łącznika programu Exchange jest obecnie dostępny, aby ułatwić analizowanie dzienników łącznika programu Exchange. Dzięki temu dostępne są różne sposoby monitorowania usługi, jeśli trzeba rozwiązać problemy.

## <a name="week-of-november-6-2017"></a>Tydzień 6 listopada 2017 r.

### <a name="device-enrollment"></a>Rejestrowanie urządzeń
#### <a name="co-management-for-windows-10-devices-----1243445---"></a>Współzarządzanie dla urządzeń z systemem Windows 10 <!-- 1243445 -->
Współzarządzanie to rozwiązanie, które łączy zarządzanie tradycyjne z nowoczesnym i udostępnia ścieżkę umożliwiającą wprowadzanie zmian przy użyciu podejścia etapowego. Zasadniczo współzarządzanie jest rozwiązaniem, w którym urządzenia z systemem Windows 10 są jednocześnie zarządzane przez program Configuration Manager i usługę Microsoft Intune, a także połączone z usługami Active Directory (AD) i Azure Active Directory (Azure AD).  Taka konfiguracja umożliwia przyszłą modernizację w tempie odpowiednim dla organizacji, jeśli nie można przenieść wszystkiego naraz.  

#### <a name="new-enrollment-status-page-for-windows-10-enrollments---1063201--"></a>Nowa strona stanu rejestracji dla rejestracji systemu Windows 10 <!--1063201-->    
Teraz można skonfigurować powitanie, które jest wyświetlane, gdy użytkownicy rejestrują urządzenia z systemem Windows 10. Na **ekranie stanu rejestracji** można skonfigurować niestandardowy komunikat i hiperlink, które będą wyświetlane użytkownikom końcowym podczas rejestrowania ich urządzeń z systemem Windows 10.  **Ekran stanu rejestracji** zapewni również użytkownikom końcowym widok postępu ustawień zasad stosowanych do ich urządzeń.  

#### <a name="restrict-windows-enrollment-by-os-version----245498---"></a>Ograniczanie rejestracji systemu Windows na podstawie wersji systemu operacyjnego <!-- 245498 -->
Jako administrator usługi Intune możesz teraz określić minimalną i maksymalną wersję systemu Windows 10 na potrzeby rejestracji urządzeń. Ograniczenia te można ustawić w bloku **Konfiguracja platformy**.

Usługa Intune będzie nadal obsługiwała rejestrowanie komputerów i telefonów z systemem Windows 8.1. Jednak tylko wersje systemu Windows 10 można ustawić z limitami minimalnym i maksymalnym. Aby zezwolić na rejestrowanie urządzeń z systemem w wersji 8.1, minimalny limit należy pozostawić pusty.

#### <a name="alerts-for-windows-autopilot-unassigned-devices-----1631236---"></a>Alerty dla urządzeń nieprzypisanych w programie Windows AutoPilot <!-- 1631236 -->
Dostępny jest nowy alert dotyczący urządzeń nieprzypisanych w programie Windows AutoPilot na stronie **Microsoft Intune** > **Rejestracja urządzeń** > **Przegląd**. Ten alert pokazuje, ile urządzeń z programu AutoPilot nie ma przypisanych profilów wdrożenia programu AutoPilot. Skorzystaj z informacji w alercie, aby utworzyć profile i przypisać je do nieprzypisanych urządzeń. Po kliknięciu alertu zostanie wyświetlona pełna lista urządzeń w programie Windows AutoPilot. Aby uzyskać więcej informacji, zobacz [Rejestrowanie urządzeń z systemem Windows przy użyciu programu Windows AutoPilot Deployment](https://docs.microsoft.com/intune/enrollment-autopilot).

### <a name="device-management"></a>Zarządzanie urządzeniami

#### <a name="refresh-button-for-devices-list-------1333581---"></a>Przycisk Odśwież dla listy urządzeń <!-- 1333581 -->
Ponieważ lista urządzeń nie jest odświeżana automatycznie, można teraz używać nowego przycisku Odśwież, który służy do aktualizowania urządzeń wyświetlanych na liście.

#### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Obsługa urzędu certyfikacji (CA) Symantec Cloud <!-- 1333638 -->    
Usługa Intune obsługuje teraz urząd certyfikacji Symantec Cloud, co pozwala łącznikowi Intune Certificate Connector na wystawianie certyfikatów PKCS z urzędu certyfikacji Symantec Cloud dla urządzeń zarządzanych przez usługę Intune. Jeśli łącznik Intune Certificate Connector jest już używany z urzędem certyfikacji (CA) Microsoft, można wykorzystać istniejącą konfigurację łącznika Intune Certificate Connector w celu dodania obsługi urzędu certyfikacji Symantec.

#### <a name="new-items-added-to-device-inventory-----1404455---"></a>Nowe elementy dodane do spisu urządzeń <!--1404455 -->
W tej wersji dodano następujące nowe elementy do [spisu wykonywanego przez zarejestrowane urządzenia](device-inventory.md):

- Adres MAC sieci Wi-Fi
- Całkowita ilość miejsca
- Całkowita ilość wolnego miejsca
- MEID
- Nazwa operatora subskrybenta


### <a name="app-management"></a>Zarządzanie aplikacjami
#### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Ustawianie dostępu dla aplikacji według minimalnego poziomu poprawki zabezpieczeń systemu Android na urządzeniu<!-- 1278463 -->   
Administrator może zdefiniować minimalny poziom poprawki zabezpieczeń systemu Android, który musi być zainstalowany na urządzeniu, aby można było uzyskać dostęp do aplikacji zarządzanej na koncie zarządzanym.

> [!Note]  
> Ta funkcja ogranicza poprawki zabezpieczeń opublikowane przez firmę Google wyłącznie na urządzeniach z systemem Android 6.0 lub nowszym.

#### <a name="app-conditional-launch-support----1193313---"></a>Obsługa uruchamiania warunkowego aplikacji <!-- 1193313 -->
Administratorzy IT mogą teraz określić za pośrednictwem portalu administracyjnego platformy Azure wymaganie, aby podczas uruchamiania aplikacji było wymuszane wprowadzenie hasła, zamiast wprowadzania kodu liczbowego PIN za pośrednictwem funkcji zarządzania aplikacjami mobilnymi (MAM). W przypadku skonfigurowania tej opcji użytkownik musi określić hasło i użyć go po wyświetleniu monitu, zanim uzyska dostęp do aplikacji z obsługą funkcji zarządzania aplikacjami mobilnymi. Hasło jest zdefiniowane jako kod liczbowy PIN zawierający co najmniej jeden znak specjalny lub wielką/małą literę. W tej wersji usługi Intune ta funkcja jest dostępna **tylko w systemie iOS**. Usługa Intune obsługuje hasło w podobny sposób jak kod liczbowy PIN — określa minimalną długość, umożliwiając powtarzanie znaków i sekwencji. Funkcja ta wymaga udziału aplikacji (tj. WXP, Outlook, Managed Browser, Yammer) w celu integracji zestawu Intune App SDK przy użyciu kodu dla tej funkcji, dzięki czemu ustawienia kodu dostępu zostaną wymuszone w aplikacjach docelowych.

#### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>Numery wersji aplikacji biznesowych w raporcie o stanie instalacji urządzenia <!-- 1233999 -->
W tej wersji w raporcie o stanie instalacji urządzenia wyświetlane są numery wersji aplikacji biznesowych dla systemów iOS i Android. Korzystając z tych informacji, można rozwiązywać problemy z aplikacjami lub znajdować urządzenia z nieaktualnymi wersjami aplikacji.


### <a name="device-configuration"></a>Konfiguracja urządzenia
#### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Administratorzy mogą teraz konfigurować ustawienia zapory na urządzeniu za pomocą profilu konfiguracji urządzenia <!-- 951708 -->   
Administratorzy mogą włączać zaporę dla urządzeń, a także konfigurować różne protokoły dla domeny oraz sieci prywatnych i publicznych.  Ustawienia zapory można znaleźć w profilu „Ochrona punktów końcowych”.

#### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>Funkcja Windows Defender Application Guard ułatwia ochronę urządzeń przed niezaufanymi witrynami w sposób zdefiniowany przez Twoją organizację <!-- 958257 -->   
Używając przepływu pracy funkcji Windows Information Protection lub nowego profilu „Granica sieci” w konfiguracjach urządzeń, administratorzy mogą definiować witryny jako „zaufane” lub „firmowe”. Wszystkie witryny wyświetlane w przeglądarce Microsoft Edge, które nie znajdują się w granicach zaufanej sieci na urządzeniu z 64-bitowym systemem Windows 10, są otwierane w przeglądarce na komputerze wirtualnym funkcji Hyper-V.

Funkcję Application Guard można znaleźć w profilach konfiguracji urządzeń w profilu „Ochrona punktów końcowych”. W tym miejscu administratorzy mogą skonfigurować interakcję między zwirtualizowaną przeglądarką a komputerem hosta, zaufanymi i niezaufanymi witrynami oraz danymi magazynowania generowanymi w zwirtualizowanej przeglądarce. Aby można było używać funkcji Application Guard na urządzeniu, najpierw należy skonfigurować granicę sieci. Dla jednego urządzenia należy określić tylko jedną granicę sieci.  

#### <a name="windows-defender-application-control-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>Funkcja Windows Defender Application Control w systemie Windows 10 Enterprise udostępnia tryb ufania tylko autoryzowanym aplikacjom <!-- 1031096 -->    
Tysiące nowych, złośliwych plików tworzonych każdego dnia powodują, że walka ze złośliwym oprogramowaniem przy użyciu wykrywania wirusów w oparciu o ich sygnatury może nie zapewniać już odpowiedniej obrony przed nowymi atakami. Korzystając z funkcji Windows Defender Application Control w systemie Windows 10 Enterprise, można zmienić konfigurację urządzenia z trybu, w którym aplikacje są zaufane, dopóki nie zostaną zablokowane przez program antywirusowy lub inne rozwiązanie z zakresu zabezpieczeń, na tryb, w którym system operacyjny ufa tylko aplikacjom autoryzowanym przez przedsiębiorstwo. Zaufanie do aplikacji można przypisać za pomocą funkcji Windows Defender Application Control.

Korzystając z usługi Intune, można skonfigurować zasady kontroli aplikacji w trybie „tylko do inspekcji” lub w trybie wymuszania. Aplikacje działające w trybie „tylko do inspekcji” nie będą blokowane. Tryb „tylko do inspekcji” rejestruje wszystkie zdarzenia w lokalnych dziennikach klienta. Można również określić, czy mogą być uruchamiane wyłącznie składniki systemu Windows i aplikacje ze sklepu Microsoft Store, czy również inne aplikacje o dobrej reputacji zdefiniowane przez usługę Intelligent Security Graph.

#### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>Windows Defender Exploit Guard to nowy zestaw funkcji zapobiegania nieautoryzowanemu dostępowi do systemu Windows 10 <!-- 1063615 -->   
Windows Defender Exploit Guard zawiera reguły niestandardowe, które ograniczają podatność aplikacji na wykorzystanie luk w zabezpieczeniach, zapobiega zagrożeniom w makrach i skryptach, automatycznie blokuje połączenia sieciowe z adresami IP o niskiej reputacji, a także umożliwia zabezpieczenie danych przed oprogramowaniem wymuszającym okup i nieznanymi zagrożeniami. Windows Defender Exploit Guard obejmuje następujące składniki:

- **Attack Surface Reduction (ASR)** zawiera reguły, które pozwalają zapobiegać zagrożeniom występującym w makrach, skryptach i wiadomościach e-mail.
- **Controlled Folder Access** automatycznie blokuje dostęp do zawartości do folderów chronionych.
- **Network Filter** blokuje połączenie wychodzące z dowolnej aplikacji do adresu IP/domeny o niskiej reputacji.
- **Exploit Protection** zapewnia ograniczenia pamięci, przepływu sterowania i zasad, które umożliwiają ochronę aplikacji przed lukami w zabezpieczeniach.


#### <a name="manage-powershell-scripts-in-intune-for-windows-10-devices----790537---"></a>Zarządzanie skryptami programu PowerShell w usłudze Intune dla urządzeń z systemem Windows 10 <!-- 790537 -->

Rozszerzenie do zarządzania usługi Intune pozwala przekazywać skrypty programu PowerShell w usłudze Intune w celu uruchamiania ich na urządzeniach z systemem Windows 10. Rozszerzenie uzupełnia możliwości funkcji zarządzania urządzeniami mobilnymi (MDM, Mobile Device Management) z systemem Windows 10 i ułatwia migrację do nowoczesnego zarządzania. Aby uzyskać szczegółowe informacje, zobacz [Zarządzanie skryptami programu PowerShell w usłudze Intune dla urządzeń z systemem Windows 10](intune-management-extension.md).

#### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Nowe ustawienia ograniczeń urządzeń z systemem Windows 10      <!-- 1308850 -->
-    Wiadomości (tylko dla urządzeń przenośnych) — wyłączenie testowania lub wiadomości MMS
-    Hasło — ustawienia umożliwiające włączanie standardu FIPS i uwierzytelnianie za pomocą dodatkowych urządzeń z usługą Windows Hello 
-    Ekran — ustawienia umożliwiające włączanie i wyłączanie skalowania graficznego interfejsu użytkownika dla starszych aplikacji

#### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Ograniczenia urządzeń z systemem Windows 10 do trybu kiosku <!-- 1308872 -->   
Możesz ograniczyć użytkowników urządzeń z systemem Windows 10 do trybu kiosku, który ogranicza użytkownikom dostęp tylko do zestawu wstępnie zdefiniowanych aplikacji.  Aby to zrobić, należy utworzyć profil ograniczenia urządzenia z systemem Windows 10 i określić ustawienia kiosku.

Tryb kiosku obsługuje dwa tryby: **pojedynczej aplikacji** (pozwala użytkownikowi na uruchomienie tylko jednej aplikacji) lub **wielu aplikacji** (zezwala na dostęp do zestawu aplikacji).  Aby określić obsługiwane aplikacje, należy zdefiniować konto użytkownika i nazwę urządzenia.  Zalogowany użytkownik ma dostęp ograniczony do zdefiniowanych aplikacji.  Aby dowiedzieć się więcej, zobacz [AssignedAccess CSP (Dostawca usługi konfiguracji AssignedAccess)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp). 

Wymagania trybu kiosku:

- Usługa Intune musi być urzędem zarządzania urządzeniami przenośnymi.
- Aplikacje muszą być już zainstalowane na urządzeniu docelowym.
- Urządzenie musi być [poprawnie udostępniane](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions).

#### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Nowy profil konfiguracji urządzeń do tworzenia granic sieci <!-- 1311967 -->   
Utworzyliśmy profil konfiguracji urządzeń o nazwie **Granica sieci**, który można znaleźć wśród innych profilów konfiguracji urządzeń. Ten profil umożliwia zdefiniowanie zasobów online, które mają być uważane za firmowe i zaufane. Granicę sieci dla urządzenia należy zdefiniować *przed* użyciem na urządzeniu funkcji takich jak Windows Defender Application Guard i Windows Information Protection. Dla każdego urządzenia należy określić tylko jedną granicę sieci.

Jako zasoby, które mają zostać uznane za zaufane, można zdefiniować zasoby chmury przedsiębiorstwa, zakresy adresów IP i wewnętrzne serwery proxy. Zdefiniowana granica sieci może być używana przez inne funkcje, takie jak Windows Defender Application Guard i Windows Information Protection.

####  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Dwa dodatkowe ustawienia usługi Windows Defender Antivirus <!-- 1338409 -->  
**Poziom blokowania plików**

| | |
|---|---|
| Nieskonfigurowane | **Nieskonfigurowane** używa domyślnego poziomu blokowania usługi Windows Defender Antivirus i zapewnia silne wykrywanie bez zwiększania ryzyka wykrywania prawidłowych plików. |
| Wysoki | **Wysoki** stosuje silny poziom wykrywania.
| Wysoki +  | **Wysoki +** zapewnia wysoki poziom z dodatkowymi środkami ochronnymi, które mogą mieć wpływ na wydajność klienta.
| Zero tolerancji  | **Zero tolerancji** blokuje wszystkie nieznane pliki wykonywalne. |

Chociaż jest to mało prawdopodobne, ustawienie **Wysoki** może powodować wykrywanie niektórych prawidłowych plików.
Zalecamy ustawienie domyślnego poziomu blokowania plików **Nieskonfigurowane**.

**Zwiększenie limitu czasu dla skanowania plików w chmurze**  

| | |
|--|--|
| Liczba sekund (0–50) | Należy określić maksymalny czas, przez który usługa Windows Defender Antivirus powinna blokować plik podczas oczekiwania na wynik z chmury. Wartość domyślna wynosi 10 sekund: dodatkowy czas określony w tym miejscu (maksymalnie 50 sekund) jest dodawany do tych 10 sekund. W większości przypadków skanowanie trwa znacznie krócej niż wartość maksymalna. Wydłużenie czasu pozwala chmurze na staranne zbadanie podejrzanych plików. Zalecamy włączenie tego ustawienia i określenie co najmniej 20 dodatkowych sekund. |

#### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Dodano sieć VPN Citrix dla urządzeń z systemem Windows 10 <!-- 1512457 -->  
Można skonfigurować sieć VPN Citrix dla swoich urządzeń z systemem Windows 10. Sieć VPN Citrix można wybrać na liście *Wybierz typ połączenia* w bloku **Podstawowa sieć VPN** podczas konfigurowania sieci VPN dla systemu Windows 10 i nowszych.

> [!Note]
> Konfiguracja serwera Citrix istniała dla systemów iOS i Android.

#### <a name="wi-fi-connections-support-pre-shared-keys-on-ios----1550823---"></a>Połączenia sieci Wi-Fi obsługują klucze wstępne w systemie iOS<!-- 1550823 -->
Klienci mogą skonfigurować profile sieci Wi-Fi, aby używać kluczy wstępnych (PSK) dla połączeń WPA/WPA2 Personal na urządzeniach z systemem iOS. Te profile są wypychane na urządzenie użytkownika, kiedy urządzenie jest zarejestrowane w usłudze Intune.

Po wypchnięciu profilu do urządzenia następny krok zależy od konfiguracji profilu.  Jeśli ustawiono wartość Połącz automatycznie, połączenie z siecią jest nawiązywane automatycznie, kiedy jest potrzebne.  Jeśli w profilu ustawiono ręczne połączenie, użytkownik musi ręcznie uaktywnić połączenie.  

### <a name="intune-apps"></a>Aplikacje usługi Intune

#### <a name="access-to-managed-app-logs-for-ios----1469920---"></a>Dostęp do dzienników zarządzanych aplikacji dla systemu iOS <!-- 1469920 -->
Użytkownicy końcowi z zainstalowanym programem Managed Browser mogą teraz wyświetlać stan zarządzania wszystkich aplikacji opublikowanych przez firmę Microsoft i wysyłać dzienniki na potrzeby rozwiązywania problemów z ich zarządzanymi aplikacjami systemu iOS.

Dowiedz się, jak włączyć tryb rozwiązywania problemów w programie Managed Browser na urządzeniu z systemem iOS, zobacz [jak uzyskać dostęp do dzienników zarządzanych aplikacji przy użyciu programu Managed Browser w systemie iOS](app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios).

#### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290----1417174---"></a>Ulepszenia przepływu pracy konfiguracji urządzenia w aplikacji Portal firmy dla systemu iOS w wersji 2.9.0 <!-- 1417174 -->

Ulepszyliśmy przepływ pracy konfiguracji urządzenia w aplikacji Portal firmy dla systemu iOS. Używany język jest bardziej przyjazny dla użytkownika i tam, gdzie było to możliwe, ekrany zostały połączone. Ponadto język jest lepiej dostosowany do Twojej firmy, ponieważ w tekście instalatora używana jest jej nazwa. Ten zaktualizowany przepływ pracy można wyświetlić na [stronie dotyczącej nowości w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów

#### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>Jednostka użytkownika zawiera najnowsze dane użytkownika w modelu danych magazynu danych <!-- 1544273 -->
Pierwsza wersja modelu danych magazynu danych usługi Intune zawierała tylko ostatnie, historyczne dane usługi Intune. Podczas tworzenia raportu nie było możliwe uchwycenie bieżącego stanu użytkownika. Po wprowadzeniu tej aktualizacji **jednostka użytkownika** jest wypełniana najnowszymi danymi użytkownika.


## <a name="week-of-october-30-2017"></a>30 października, 2017 r.

### <a name="app-management"></a>Zarządzanie aplikacjami

#### <a name="ios-and-android-line-of-business-app-version-number-is-visible----1380712---"></a>Widoczny numer wersji aplikacji biznesowej dla systemu iOS lub Android <!-- 1380712 -->

W usłudze Intune są teraz wyświetlane numery wersji aplikacji biznesowych dla systemu iOS lub Android. W witrynie Azure Portal numer jest widoczny na liście aplikacji i w bloku przeglądu aplikacji. Użytkownicy końcowi widzą numer aplikacji w aplikacji Portal firmy i w portalu internetowym.

__Pełny numer wersji__ Pełny numer wersji identyfikuje określoną wersję aplikacji. Numer ma postać _wersja_(_kompilacja_), na przykład 2.2(2.2.17560800).

Pełny numer wersji ma dwa składniki:

 - **Wersja**  
   Numer wersji to zrozumiały dla użytkownika numer wydania aplikacji. Jest on używany przez użytkowników końcowych do identyfikowania różnych wydań aplikacji.

 - **Numer kompilacji**  
    Numer kompilacji to numer wewnętrzny, który może być używany do wykrywania aplikacji i programowego zarządzania nią. Numer kompilacji dotyczy iteracji aplikacji, która odnosi się do zmian w kodzie.

Temat [Wprowadzenie do zestawu SDK aplikacji usługi Microsoft Intune](app-sdk-get-started.md#line-of-business-app-version-numbers) zawiera więcej informacji o numerach wersji i tworzeniu aplikacji biznesowych.

#### <a name="device-and-app-management-integration----677972---"></a>Integracja zarządzania urządzeniami i aplikacjami <!-- 677972 -->   
Teraz, gdy funkcje zarządzania urządzeniami przenośnymi (MDM) i zarządzania aplikacjami mobilnymi (MAM) usługi Intune są już dostępne w witrynie Azure Portal, usługa Intune rozpoczęła integrowanie środowiska pracy administratora IT wokół zarządzania aplikacjami i urządzeniami. Zmiany mają na celu uproszczenie środowiska zarządzania urządzeniami i aplikacjami.

Dowiedz się więcej na temat zmian funkcji MDM i MAM ogłoszonych w [blogu zespołu pomocy technicznej usługi Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).

#### <a name="new-enrollment-alerts-for-apple-devices----1471790---"></a>Nowe alerty rejestracji dla urządzeń firmy Apple <!-- 1471790 -->
Na stronie przeglądu rejestracji będą wyświetlane przydatne alerty dotyczące zarządzania urządzeniami firmy Apple, przeznaczone dla administratorów IT. Alerty na stronie przeglądu pojawią się, jeśli certyfikat wypychania MDM firmy Apple wkrótce wygaśnie bądź już wygasł lub token programu Device Enrollment Program wkrótce wygaśnie bądź już wygasł albo w programie Device Enrollment Program występują nieprzypisane urządzenia.

#### <a name="support-token-replacement-for-app-configuration-without-device-enrollment----1080364---"></a>Obsługa zastępowania tokenu dla konfiguracji aplikacji bez rejestracji urządzeń <!-- 1080364 -->

Można używać tokenów dla wartości dynamicznych w konfiguracjach aplikacji na niezarejestrowanych urządzeniach. Aby uzyskać więcej informacji, zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych aplikacji bez rejestracji urządzeń](app-configuration-policies-managed-app.md).

### <a name="intune-apps"></a>Aplikacje usługi Intune

#### <a name="updates-to-the-company-portal-app-for-windows-10---1299474--"></a>Aktualizacje aplikacji Portal firmy dla systemu Windows 10 <!--1299474-->
Strona Ustawienia w aplikacji Portal firmy dla systemu Windows 10 została zaktualizowana, dzięki czemu ustawienia i spodziewane akcje użytkownika są bardziej spójne z pozostałymi ustawieniami. Zaktualizowany został również układ aplikacji, który teraz lepiej odpowiada układom innych aplikacji systemu Windows. Obrazy stanu przed i po aktualizacji znajdują się na stronie dotyczącej [nowości w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

#### <a name="inform-end-users-what-device-information-can-be-seen-for-windows-10-devices---1337920--"></a>Powiadamianie użytkowników końcowych o widocznych informacjach dotyczących urządzeń dla systemu Windows 10 <!--1337920-->
Dodaliśmy element **Typ własności** do ekranu Szczegóły urządzenia w aplikacji Portal firmy dla systemu Windows 10. Dzięki temu użytkownicy mogą dowiedzieć się więcej o ochronie prywatności bezpośrednio z tej strony w dokumentach użytkownika końcowego usługi Intune. Mogą oni również zlokalizować te informacje na ekranie **Informacje**.

#### <a name="feedback-prompts-for-the-company-portal-app-for-android---1165249--"></a>Monity o opinię użytkownika aplikacji Portal firmy dla systemu Android <!--1165249-->
Aplikacja Portal firmy dla systemu Android wyświetla teraz prośbę o opinię użytkownika końcowego. Opinia ta jest wysyłana bezpośrednio do firmy Microsoft i zapewni użytkownikom końcowym możliwość opublikowania recenzji aplikacji w publicznym sklepie Google Play. Opinia nie jest wymagana, więc prośbę można łatwo odrzucić i dalej używać aplikacji.

<!-- #### Update to what device details an organization can see 1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources.-->

#### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Ułatwianie użytkownikom samodzielnego rozwiązywania problemów przy użyciu aplikacji Portal firmy dla systemu Android <!-- 1573324, 1573150, 1558616, 1564878 -->

Do aplikacji Portal firmy dla systemu Android zostały dodane instrukcje dla użytkowników końcowych zawierające opisy problemów i umożliwiające — o ile to możliwe — samodzielne rozwiązywanie nowych przypadków użycia.
- W przypadku dodania maksymalnej dozwolonej liczby urządzeń użytkownicy końcowi zostaną przekierowani do [portalu usługi Azure Active Directory](https://account.activedirectory.windowsazure.com/r/#/profile) w celu usunięcia urządzenia.
- Użytkownicy otrzymają instrukcje ułatwiające [naprawienie błędów aktywacji na urządzeniach z systemem Samsung Knox](https://go.microsoft.com/fwlink/?linkid=859718) lub [wyłączenie trybu oszczędzania energii](/intune-user-help/power-saving-mode-android). Jeśli żadne z tych rozwiązań nie pozwoli rozwiązać problemu, udostępnimy wskazówki dotyczące [przesyłania dzienników do firmy Microsoft](/intune-user-help/send-logs-to-microsoft-android).

#### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Nowa akcja „Rozwiąż” dostępna dla urządzeń z systemem Android <!-- 1583480 -->

W aplikacji Portal firmy dla systemu Android zostanie wprowadzona akcja „Rozwiąż”, dostępna na stronie _aktualizacji ustawień urządzenia_. Wybranie tej opcji spowoduje przejście bezpośrednio do ustawienia powodującego niezgodność urządzenia z zasadami. Aktualnie aplikacja Portal firmy dla systemu Android obsługuje tę akcję dla ustawień dotyczących [kodu dostępu urządzenia](/intune-user-help/set-your-pin-or-password-android), [debugowania USB](/intune-user-help/you-need-to-turn-off-usb-debugging-android) i [nieznanych źródeł](/intune-user-help/you-need-to-turn-off-unknown-sources-android).

#### <a name="device-setup-progress-indicator-in-android-company-portal----1565657---"></a>Wskaźnik postępu konfiguracji urządzenia w aplikacji Portal firmy dla systemu Android <!-- 1565657 -->
Aplikacja Portal firmy dla systemu Android wyświetla wskaźnik postępu konfiguracji urządzenia, gdy użytkownik rejestruje swoje urządzenie. Wskaźnik przedstawia nowe stany, np. „Konfigurowanie urządzenia...”, następnie „Trwa rejestrowanie urządzenia...”, następnie „Kończenie rejestrowania urządzenia...”, następnie „Trwa kończenie konfigurowania urządzenia...”.

## <a name="week-of-october-23-2017"></a>Tydzień 23 października 2017 r.

### <a name="intune-apps"></a>Aplikacje usługi Intune
#### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Obsługa uwierzytelniania opartego na certyfikatach w Portalu firmy dla systemu iOS <!--1029830-->
W aplikacji Portal firmy dla systemu iOS dodaliśmy obsługę uwierzytelniania opartego na certyfikatach (CBA). Użytkownicy korzystający z uwierzytelniania CBA wprowadzają swoją nazwę użytkownika, a następnie wybierają link „Zaloguj się przy użyciu certyfikatu”. Uwierzytelnianie CBA jest już obsługiwane w aplikacji Portal firmy dla systemów Android i Windows. Więcej informacji na ten temat można znaleźć na stronie [logowania się w aplikacji Portal firmy](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal).

#### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Aplikacje dostępne z rejestracją lub bez rejestracji można teraz instalować bez monitów o rejestrację. <!-- 1334712 -->

Aplikacje firmowe, które udostępniono z rejestracją lub bez rejestracji w aplikacji Portal firmy dla systemu Android, można teraz zainstalować bez monitu o rejestrację.

## <a name="week-of-october-16-2017"></a>Tydzień 16 października 2017 r.
### <a name="device-enrollment"></a>Rejestrowanie urządzeń
#### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune-----747617----"></a>Obsługa programu Windows AutoPilot Deployment w usłudze Microsoft Intune <!-- 747617  -->
Przy użyciu programu usługi Microsoft Intune z programem Windows AutoPilot Deployment możesz umożliwiać użytkownikom aprowizację urządzeń firmowych bez angażowania w to działu IT. Możesz dostosować tryb OOBE i przeprowadzić użytkowników przez proces dołączania urządzenia do usługi Azure AD i jego rejestracji w usłudze Intune. Dzięki współdziałaniu usługi Microsoft Intune i programu Windows AutoPilot nie ma potrzeby wdrażania i utrzymywania obrazów systemu operacyjnego ani zarządzania nimi. Aby uzyskać szczegółowe informacje, zobacz [Rejestrowanie urządzeń z systemem Windows przy użyciu programu Windows AutoPilot Deployment](https://docs.microsoft.com/intune/enrollment-autopilot).

#### <a name="quick-start-for-device-enrollment-----1425655---"></a>Szybki start dla rejestracji urządzeń <!-- 1425655 --> 
Szybki start jest teraz dostępny w **rejestracji urządzeń** i zawiera tabelę odwołań dla zarządzania platformami i konfigurowania procesu rejestracji. Krótki opis każdego elementu i linki do dokumentacji z instrukcjami krok po kroku ułatwiają rozpoczęcie pracy.

#### <a name="device-categorization----1427491---"></a>Kategoryzacja urządzeń <!-- 1427491 -->
Zestawienie platform zarejestrowanych urządzeń w bloku **Urządzenia > Przegląd** organizuje urządzenia według platform, w tym systemów Android, iOS, macOS, Windows i Windows Mobile.  Urządzenia z innymi systemami operacyjnymi znajdują się w grupie „Inne”.  Są to urządzenia wyprodukowane przez firmy Blackberry, NOKIA i inne.  

Aby dowiedzieć się, których urządzeń w dzierżawie to dotyczy, wybierz pozycję **Zarządzaj > Wszystkie urządzenia**, a następnie przy użyciu funkcji **Filtruj** ogranicz pole **System operacyjny**.

### <a name="device-management"></a>Zarządzanie urządzeniami
#### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium — nowy partner usługi Mobile Threat Defense <!-- 954681 -->  
Dostęp urządzeń przenośnych do zasobów firmy można kontrolować przy użyciu dostępu warunkowego opartego na ocenie ryzyka przeprowadzanej przez usługę Zimperium. Jest to rozwiązanie chroniące przed zagrożeniami bezpieczeństwa urządzeń przenośnych zintegrowane z usługą Microsoft Intune.

##### <a name="how-integration-with-intune-works"></a>Jak działa integracja z usługą Intune
Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń z uruchomionym rozwiązaniem Zimperium. Zasady dostępu warunkowego usług EMS można skonfigurować w oparciu o ocenę ryzyka przeprowadzaną przez rozwiązanie Zimperium włączane przy użyciu zasad zgodności urządzeń usługi Intune, których w przypadku niezgodnego urządzenia można użyć do zezwalania na dostęp do zasobów firmy lub blokowania go w oparciu o wykryte zagrożenia.

#### <a name="new-settings-for-windows-10-device-restriction-profile------978575-1308849---"></a>Nowe ustawienia dla profilu ograniczeń urządzenia z systemem Windows 10 <!--- 978575, 1308849, -->  
Dodajemy nowe ustawienia do profilu ograniczeń urządzenia z systemem Windows 10 w kategorii Windows Defender SmartScreen.

Aby uzyskać szczegółowe informacje o profilu ograniczeń urządzenia z systemem Windows 10, zobacz [Ustawienia ograniczeń urządzenia z systemem Windows 10 lub nowszym]( device-restrictions-windows-10.md).

#### <a name="remote-support-for-windows-and-windows-mobile-devices------1070473---"></a>Zdalna pomoc techniczna dla urządzeń z systemem Windows i Windows Mobile <!-- 1070473 -->  
Usługa Intune umożliwia teraz korzystanie z zakupionego osobno oprogramowania [TeamViewer](https://www.teamviewer.com), aby umożliwić oferowanie pomocy zdalnej użytkownikom urządzeń z systemem Windows i Windows Mobile.

#### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Skanowanie urządzeń z użyciem usługi Windows Defender <!-- 1280988  1280990   -->
Na zarządzanych urządzeniach z systemem Windows 10 możliwe jest teraz uruchomienie **szybkiego skanowania** i **pełnego skanowania** oraz przeprowadzenie **aktualizacji sygnatur** z użyciem programu antywirusowego Windows Defender. W bloku przeglądu urządzenia wybierz akcję do przeprowadzenia na urządzeniu. Przed wysłaniem polecenia do urządzenia zostanie wyświetlony monit o potwierdzenie akcji. 

**Szybkie skanowanie**: szybkie skanowanie obejmuje lokalizacje, w których złośliwe oprogramowanie rejestruje się w celu umożliwienia jego uruchomienia, np. klucze rejestru i znane foldery uruchamiania systemu Windows. Szybkie skanowanie trwa średnio pięć minut. W połączeniu z ustawieniem **zawsze włączonej ochrony w czasie rzeczywistym**, które skanuje pliki, gdy są one otwierane i zamykane, a także za każdym razem, gdy użytkownik przejdzie do folderu, szybkie skanowanie pomaga chronić przed złośliwym oprogramowaniem, które może być obecne w systemie lub w jądrze. Po zakończeniu skanowania użytkownicy widzą jego wyniki na swoich urządzeniach. 

**Pełne skanowanie**: pełne skanowanie przydaje się w przypadku urządzeń, w których wystąpiło zagrożenie związane ze złośliwym oprogramowaniem, ponieważ pozwala określić, czy istnieją nieaktywne składniki, które wymagają dokładniejszego czyszczenia; funkcja umożliwia także uruchamianie skanowania na żądanie. Pełne skanowanie może trwać godzinę. Po zakończeniu skanowania użytkownicy widzą jego wyniki na swoich urządzeniach. 

**Zaktualizuj sygnatury**: polecenie aktualizacji sygnatur powoduje aktualizację definicji i sygnatur złośliwego oprogramowania programu antywirusowego Windows Defender. Można w ten sposób upewnić się, że program antywirusowy Windows Defender skutecznie wykrywa złośliwe oprogramowanie. Ta funkcja jest dostępna wyłącznie dla urządzeń z systemem Windows 10 i wymaga połączenia z Internetem. 

#### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal-----1400455---"></a>Przycisk Włącz/Wyłącz został usunięty ze strony urzędu certyfikacji usługi Intune w witrynie Azure Portal usługi Intune <!-- 1400455 -->
 Eliminujemy dodatkowy krok z konfiguracji łącznika certyfikatów w usłudze Intune. Obecnie należy pobrać łącznik certyfikatów, a następnie włączyć go w konsoli usługi Intune. Jeśli jednak wyłączysz łącznik w konsoli usługi Intune, łącznik wciąż wydaje certyfikaty.

##### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Począwszy od października przycisk Włącz/Wyłącz nie będzie już wyświetlany na stronie urzędu certyfikacji w witrynie Azure Portal. Funkcje łącznika pozostają bez zmian. Certyfikaty są wciąż wdrażane na urządzeniach zarejestrowanych w usłudze Intune. Nadal możesz pobrać i zainstalować łącznik certyfikatów. Aby zatrzymać wydawanie certyfikatów, zamiast wyłączać łącznik certyfikatów należy go teraz odinstalować.

##### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Jeśli łącznik certyfikatów jest obecnie wyłączony, należy go odinstalować.

### <a name="device-configuration"></a>Konfiguracja urządzenia
#### <a name="new-settings-for-windows-10-team-device-restriction-profile-------1308838---"></a>Nowe ustawienia dla profilu ograniczeń urządzenia z systemem Windows 10 Team <!--- 1308838 -->
W tym wydaniu dodaliśmy wiele nowych ustawień profilu ograniczeń urządzenia z systemem Windows 10 Team ułatwiających kontrolę urządzeń Surface Hub.

Aby uzyskać więcej informacji o tym profilu, zobacz artykuł [Windows 10 Team device restriction settings](device-restrictions-windows-10-teams.md) (Ustawienia ograniczeń urządzenia z systemem Windows 10 Team).

#### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Uniemożliwianie użytkownikom urządzeń z systemem Android zmiany daty i godziny ich urządzeń <!-- 1333292 -->
Można użyć [niestandardowych zasad urządzeń z systemem Android](custom-settings-android.md), aby uniemożliwić użytkownikom urządzeń z systemem Android zmianę daty i godziny urządzenia.

W tym celu należy skonfigurować niestandardowe zasady systemu Android, korzystając z identyfikatora URI ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange Dla powyższego identyfikatora URI należy wybrać wartość **TRUE**, a następnie przypisać go do wymaganych grup.

#### <a name="bitlocker-device-configuration----1397398---"></a>Konfiguracja urządzenia z użyciem funkcji BitLocker <!-- 1397398 -->
Wybierając pozycję **Szyfrowanie systemu Windows > Ustawienia podstawowe**, można uzyskać dostęp do nowego ustawienia **Ostrzeżenie dotyczące innego szyfrowania dysku** pozwalającego wyłączyć [monit ostrzegawczy](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) dotyczący innego szyfrowania, które mogło zostać użyte na urządzeniu użytkownika.  Przed rozpoczęciem konfiguracji funkcji BitLocker na urządzeniu zostanie wyświetlony monit ostrzegawczy wymagający zgody użytkownika końcowego; konfiguracja funkcji BitLocker będzie blokowana do czasu potwierdzenia przez użytkownika końcowego.  Nowe ustawienie wyłącza ostrzeżenie użytkownika końcowego.


### <a name="app-management"></a>Zarządzanie aplikacjami
#### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant----800882---"></a>Aplikacje programu Volume Purchase Program for Business będą się teraz synchronizowały z dzierżawą usługi Intune <!-- 800882 -->  
Deweloperzy innych firm mogą prywatnie dystrybuować aplikacje do autoryzowanych członków programu Volume Purchase Program (VPP) for Business określonych w usłudze iTunes Connect. Ci członkowie programu VPP for Business mogą zalogować się do sklepu Volume Purchase Program App Store i zakupić ich aplikacje.

W tej wersji aplikacje programu VPP for Business zakupione przez użytkownika końcowego będą się teraz synchronizowały z ich dzierżawami usługi Intune.

#### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Wybór krajowego sklepu Apple do synchronizacji aplikacji VPP <!-- 1332311 -->  
Podczas przekazywania tokenu programu VPP można skonfigurować krajowy sklep do obsługi programu zakupów zbiorczych (VPP, ang. Volume Purchase Program). Usługa Intune synchronizuje aplikacje VPP z określonego krajowego sklepu umożliwiającego korzystanie z programu zakupów zbiorczych zgodnie ze wszystkimi ustawieniami regionalnymi.

> [!NOTE]  
> Obecnie usługa Intune synchronizuje tylko aplikacje VPP z krajowego sklepu umożliwiającego korzystanie z programu zakupów zbiorczych zgodnego z ustawieniami regionalnymi usługi Intune dla lokalizacji, w której została utworzona dzierżawa usługi Intune.


### <a name="intune-apps"></a>Aplikacje usługi Intune
#### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Blokowanie kopiowania i wklejania między profilami służbowymi i osobistymi w aplikacji Android for Work <!-- 1098994 -->
W tej wersji można skonfigurować profil służbowy w programie Android for Work w taki sposób, aby kopiowanie i wklejanie danych między aplikacjami służbowymi i osobistymi było blokowane. To nowe ustawienie można znaleźć w profilu **Ograniczenia urządzenia** platformy **Android for Work** w obszarze **Ustawienia profilu służbowego**.

#### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Tworzenie aplikacji dla systemu iOS ograniczonych do określonych regionalnych sklepów Apple App Store <!-- 1281692 -->
Podczas tworzenia zarządzanej aplikacji przeznaczonej do sklepu Apple App Store można określić ustawienia regionalne dla kraju.

> [!Note]  
> Obecnie można tworzyć wyłącznie zarządzane aplikacje dla sklepu Apple App Store dostępne w amerykańskiej wersji strony sklepu.

####  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Aktualizacja aplikacji VPP dla systemu iOS z licencją użytkownika i urządzenia <!-- 1305564 -->  
Można skonfigurować token programu VPP systemu iOS pod kątem aktualizacji wszystkich aplikacji zakupionych dla danego tokenu za pośrednictwem usługi Intune. Usługa Intune wykryje aktualizacje aplikacji VPP w sklepie z aplikacjami i automatycznie wypchnie je do urządzenia po jego zaewidencjonowaniu.

Aby poznać procedurę ustawiania tokenu VPP i włączania automatycznych aktualizacji, zobacz [Jak w usłudze Microsoft Intune zarządzać aplikacjami dla systemu iOS, które zostały zakupione w ramach programu zakupów zbiorczych] (/intune/vpp-apps-ios).


### <a name="monitor-and-troubleshoot"></a>Monitorowanie i rozwiązywanie problemów
#### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Kolekcja jednostek skojarzenia urządzenia użytkownika dodana do modelu danych magazynu danych usługi Intune <!-- 1187917 -->
Można teraz tworzyć raporty i wizualizacje danych, korzystając z informacji skojarzenia urządzenia użytkownika, które odpowiadają za skojarzenie użytkownika i kolekcji jednostek urządzenia. Dostęp do modelu danych można uzyskać, korzystając z pliku usługi Power BI (PBIX) pobranego ze strony magazynu danych usługi Intune, za pośrednictwem punktu końcowego OData lub poprzez utworzenie niestandardowego klienta.

#### <a name="review-policy-compliance-for-windows-10-update-rings----1067886---"></a>Przegląd zasad zgodności pod kątem pierścieni aktualizacji systemu Windows 10 <!-- 1067886 -->
Można przejrzeć raport zasad odnoszący się do pierścieni aktualizacji systemu Windows 10, przechodząc do obszaru Aktualizacje oprogramowania > Stan wdrożenia według pierścienia aktualizacji. Raport zasad zawiera stan wdrożenia dla skonfigurowanych pierścieni aktualizacji. 

#### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Nowy raport, który zawiera listę urządzeń dla systemu iOS ze starszymi wersjami systemu iOS   <!-- 1352223 -->
Raport **Nieaktualne urządzenia z systemem iOS** jest dostępny z poziomu obszaru roboczego **Aktualizacje oprogramowania**. W raporcie można przejrzeć listę nadzorowanych urządzeń z systemem iOS, których dotyczyły zasady aktualizacji systemu iOS i które mają dostępne aktualizacje. Dla każdego urządzenia można wyświetlić stan z informacją, dlaczego urządzenie nie zostało zaktualizowane automatycznie. 

#### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Wyświetlanie przypisań zasad ochrony aplikacji w celu rozwiązywania problemów <!--  1475003 -->
W nadchodzącym wydaniu opcja **zasad ochrony aplikacji** zostanie dodana do listy rozwijanej **Przypisania** dostępnej w bloku rozwiązywania problemów. Teraz możesz wybrać zasady ochrony aplikacji, aby wyświetlić zasady ochrony aplikacji przypisane do wybranych użytkowników.



## <a name="week-of-october-2-2017"></a>Tydzień 2 października 2017 r.
### <a name="intune-apps"></a>Aplikacje usługi Intune
#### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>Ulepszenia przepływu pracy konfiguracji urządzenia w Portalu firmy <!--1490692-->
Ulepszyliśmy przepływ pracy konfiguracji urządzenia w aplikacji Portal firmy dla systemu Android. Język jest bardziej przyjazny dla użytkownika i specyficzny dla Twojej firmy, a w miarę możliwości ekrany zostały połączone. Możesz to zobaczyć na stronie [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md#week-of-october-2-2017).

#### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Ulepszone wskazówki dotyczące żądania dostępu do kontaktów na urządzeniach z systemem Android <!--1484985-->

Aplikacja Portal firmy dla systemu Android często wymaga od użytkownika końcowego zaakceptowania uprawnień do kontaktów. Jeśli użytkownik końcowy odmówi dostępu, zobaczy w aplikacji powiadomienie z alertem dotyczącym przyznania aplikacji dostępu warunkowego. 

#### <a name="secure-startup-remediation-for-android---1490712--"></a>Korygowanie bezpiecznego uruchamiania dla systemu Android <!--1490712-->

Użytkownicy końcowi mający urządzenia z systemem Android będą mogli wybierać przyczynę niezgodności w aplikacji Portal firmy. Gdy będzie to możliwe, przeniesie to ich bezpośrednio do poprawnej lokalizacji w aplikacji ustawień, aby rozwiązać ten problem. 

#### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo---1475932--"></a>Dodatkowe powiadomienia wypychane dla użytkowników końcowych w aplikacji Portal firmy dla systemu Android Oreo <!--1475932-->

Użytkownicy końcowi będą widzieli dodatkowe powiadomienia, gdy aplikacja Portal firmy dla systemu Android Oreo wykonuje zadania w tle, takie jak pobieranie zasad z usługi Intune. Powoduje to zwiększenie przejrzystości dla użytkowników końcowych przez informowanie ich, kiedy aplikacja Portal firmy wykonuje zadania administracyjne na ich urządzeniach. Jest to część ogólnej [optymalizacji interfejsu użytkownika aplikacji Portal firmy](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) dla aplikacji Portal firmy dla systemu Android Oreo. 

Istnieją dodatkowe optymalizacje dla nowych elementów interfejsu użytkownika, które są włączone w systemie Android Oreo.  Użytkownicy końcowi zobaczą dodatkowe powiadomienia, które będą wskazywać im, kiedy Portal firmy wykonuje zadania w tle, takie jak pobieranie zasad z usługi Intune.  Powoduje to zwiększenie przejrzystości dla użytkowników końcowych dzięki informowaniu ich, kiedy aplikacja Portal firmy wykonuje zadania administracyjne na urządzeniu.

#### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Nowe zachowanie aplikacji Portal firmy dla systemu Android z profilami służbowymi <!-- 1485783 -->

Po zarejestrowaniu urządzenia z programem Android for Work i z profilem służbowym to właśnie aplikacja Portal firmy w profilu służbowym wykonuje na urządzeniu zadania z zakresu zarządzania. 

Jeśli użytkownik nie korzysta w profilu osobistym z aplikacji z obsługą zasad zarządzania aplikacjami mobilnymi (MAM), aplikacja Portal firmy dla systemu Android nie pełni już żadnej roli. Aby ulepszyć środowisko pracy w profilu służbowym, po pomyślnej rejestracji profilu służbowego usługa Intune automatycznie ukrywa aplikację Portal firmy z profilu osobistego.

Aplikację Portal firmy dla systemu Android można w dowolnym momencie włączyć w profilu osobistym, wybierając [aplikację Portal firmy w Sklepie Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) i wybierając opcję **Włącz**.

#### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Utrzymanie aplikacji Portal firmy w systemach Windows 8.1 i Windows Phone 8.1 <!--1428681-->

Począwszy od października 2017 roku aplikacje Portal firmy zostaną utrzymane w systemach Windows 8.1 i Windows Phone 8.1. Oznacza to, że aplikacje i istniejące scenariusze, np. scenariusze rejestracji i zgodności, będą nadal obsługiwane przez te platformy. Aplikacje te będą nadal dostępne do pobrania za pośrednictwem istniejących kanałów, takich jak Sklep Microsoft. 

Po zatwierdzeniu utrzymania tych aplikacji będą dla nich udostępniane wyłącznie krytyczne aktualizacje zabezpieczeń. Nie będzie dla nich żadnych dodatkowych aktualizacji i nie będą w nich udostępniane żadne nowe funkcje. W celu skorzystania z nowych funkcji zalecamy aktualizację urządzenia do systemu Windows 10 lub Windows 10 Mobile. 


### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="block-unsupported-samsung-knox-device-enrollment-----1490695---"></a>Blokowanie nieobsługiwanej rejestracji urządzenia z systemem Samsung Knox <!-- 1490695 -->

Aplikacja Portal firmy tylko próbuje zarejestrować obsługiwane urządzenia z systemem Samsung Knox. Aby uniknąć błędów aktywacji systemu Knox, które uniemożliwiają rejestrację w usłudze MDM, próba rejestracji urządzenia nastąpi tylko wtedy, gdy urządzenie znajduje się na [liście urządzeń opublikowanej przez firmę Samsung](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Urządzenia firmy Samsung z określonymi numerami modelu mogą obsługiwać system Knox, podczas gdy inne go nie obsługują. Sprawdź zgodność systemu Knox u odsprzedawcy urządzenia przed zakupem i wdrożeniem. Pełną listę zweryfikowanych urządzeń można znaleźć w [ustawieniach zasad systemu Android i systemu Samsung Knox Standard](/intune/supported-devices-browsers.md#intune-supported-devices).

#### <a name="end-of-support-for-android-43-and-lower----1171126-1326920---"></a>Zakończenie obsługi dla systemu Android 4.3 i starszych <!-- 1171126, 1326920 -->
Aplikacje zarządzane i aplikacja Portal firmy dla systemu Android będą wymagać systemu Android 4.4 lub nowszego, aby można było uzyskiwać dostęp do zasobów firmy. Od grudnia zostanie wymuszone wycofanie wszystkich zarejestrowanych urządzeń, co spowoduje utratę dostępu do zasobów firmy. Jeśli używasz zasad ochrony aplikacji bez zarządzania urządzeniami przenośnymi, aplikacje nie będą otrzymywać aktualizacji, a jakość obsługi będzie się pogarszać wraz z upływem czasu.

#### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Powiadamianie użytkowników końcowych o informacjach o urządzeniu widocznych na zarejestrowanych urządzeniach <!--1165314-->
Dodajemy element **Typ własności** do ekranu Szczegóły urządzenia we wszystkich aplikacjach Portal firmy. Dzięki temu użytkownicy mogą dowiedzieć się więcej o ochronie prywatności bezpośrednio z artykułu [Jakie informacje może wyświetlać Twoja firma?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune). Zostanie to wdrożone we wszystkich aplikacjach Portal firmy w najbliższej przyszłości. Zapowiedzieliśmy to dla systemu iOS we [wrześniu](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017).


## <a name="week-of-september-25-2017"></a>Tydzień 25 września 2017 r.

### <a name="device-enrollment"></a>Rejestrowanie urządzeń

#### <a name="intune-supports-ios-11---1428975--"></a>Usługa Intune obsługuje system iOS 11 <!--1428975-->
Usługa Intune obsługuje system iOS 11. Zostało to wcześniej zapowiedziane na [blogu dotyczącym pomocy technicznej usługi Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/).

#### <a name="end-of-support-for-ios-80----1164477---"></a>Zakończenie obsługi dla systemu iOS 8.0 <!-- 1164477 -->
Aplikacje zarządzane i aplikacja Portal firmy dla systemu iOS będą wymagać systemu iOS 9.0 lub nowszego, aby można było uzyskiwać dostęp do zasobów firmy. Urządzenia, które nie zostaną zaktualizowane do września tego roku, nie będą już mogły uzyskiwać dostępu do aplikacji Portal firmy i tych aplikacji. 

### <a name="intune-apps"></a>Aplikacje usługi Intune

#### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Dodanie akcji odświeżenia do aplikacji Portal firmy dla systemu Windows 10 <!--1132468-->
Aplikacja Portal firmy dla systemu Windows 10 pozwala użytkownikom odświeżać dane w aplikacji poprzez przeciągnięcie ekranu lub — w przypadku komputerów — naciśnięcie klawisza F5.



## <a name="notices"></a>Uwagi

### <a name="plan-for-change-use-intune-on-azure-now-for-your-mdm-management----1227338---"></a>Planowanie zmian: już teraz zacznij zarządzać urządzeniami przenośnymi za pomocą usługi Intune na platformie Azure <!-- 1227338 -->
Ponad rok temu ogłosiliśmy [publiczną wersję zapoznawczą usługi Intune na platformie Azure](https://cloudblogs.microsoft.com/enterprisemobility/2016/12/07/public-preview-of-intune-on-azure/), a sześć miesięcy temu opublikowaliśmy [ogólnie dostępną wersję nowego środowiska pracy administratora](https://cloudblogs.microsoft.com/enterprisemobility/2017/06/08/the-new-intune-and-conditional-access-admin-consoles-are-ga/) dla usługi Intune. 2 kwietnia 2018 r. wyłączymy funkcję zarządzania urządzeniami przenośnymi w klasycznej konsoli programu Silverlight dla klientów korzystających z autonomicznej usługi Intune. Zamiast tego na potrzeby zarządzania urządzeniami przenośnymi można używać [usługi Intune na platformie Azure](https://aka.ms/Intune_on_Azure). Jeśli nadal używasz konsoli klasycznej do zarządzania urządzeniami przenośnymi, zapoznaj się z usługą Intune na platformie Azure. Ta zmiana nie powinna mieć żadnego wpływu na użytkowników końcowych. Program Silverlight będzie nadal umożliwiał zarządzanie komputerami klasycznymi. Więcej informacji na temat tej zmiany i jej wpływu na Ciebie znajduje się [tutaj](https://aka.ms/Intune_on_Azure_mdm).


### <a name="plan-for-change-easy-assist-end-of-life----1556480---"></a>Planowanie zmian: zakończenie obsługi funkcji Easy Assist <!-- 1556480 -->
Usługa Intune używa funkcji Microsoft Easy Assist do realizacji pomocy zdalnej w zakresie zarządzania komputerem. Nowością może być fakt, że funkcja Microsoft Easy Assist jest składnikiem usługi Office Live Meeting, której świadczenie zakończy się w dniu 31 grudnia 2017 r. W związku z tym funkcja Easy Assist w usłudze Intune również przestanie być dostępna w dniu 31 grudnia 2017 r.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Zarządzanie urządzeniami programu Android for Work w sposób niezależny od urządzeń z systemem Android <!-- 1490731 EEready-->    
**Uwaga:** następujące zmiany zostaną wprowadzone wraz z listopadową aktualizacją, ale ich wdrożenie na danym koncie może trochę potrwać. Gdy zmiany zostaną zastosowane na Twoim koncie, otrzymasz powiadomienie w portalu usługi Office 365. Po wprowadzeniu aktualizacji zyskasz dodatkowe możliwości zarządzania. Aktualizacja nie wprowadza zmian w środowisku użytkownika końcowego.

Usługa Intune obsługuje zarządzanie rejestracją urządzeń programu Android for Work w sposób niezależny od platformy Android. Opcje zarządzania tymi ustawieniami są dostępne w obszarze **Rejestrowanie urządzenia** > **Ograniczenia rejestracji** > **Ograniczenia typów urządzeń**. (Wcześniej znajdowały się one w obszarze **Rejestrowanie urządzeń** > **Rejestracja w programie Android for Work** > **Ustawienia rejestracji programu Android for Work**).

Domyślnie ustawienia urządzeń programu Android for Work będą takie same jak ustawienia urządzeń z systemem Android. Nie będzie tak jednak w przypadku zmiany ustawień programu Android for Work.

Jeśli zablokujesz rejestrację urządzeń osobistych w programie Android for Work, będzie można rejestrować tylko firmowe urządzenia z systemem Android.

Podczas pracy z nowymi ustawieniami zwróć uwagę na następujące kwestie:

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Jeśli wcześniej nie dodano rejestracji w programie Android for Work

Nowa platforma Android for Work jest zablokowana w domyślnych ograniczeniach typów urządzeń. Po dodaniu tej funkcji możesz zezwolić urządzeniom na rejestrację w programie Android for Work. Aby to zrobić, zastąp domyślne ograniczenie typów urządzeń — zmień je lub utwórz nowe ograniczenie.

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Jeśli dodano rejestrację w programie Android for Work

Jeśli wcześniej dołączono do programu, sytuacja zależy od wybranego ustawienia:

| Ustawienie | Stan programu Android for Work w domyślnym ograniczeniu typów urządzeń | Uwagi |
| --- | --- | --- |
| **Zarządzaj wszystkimi urządzeniami jako urządzeniami z systemem Android** | Zablokowane | Wszystkie urządzenia z systemem Android należy zarejestrować bez programu Android for Work. |
| **Zarządzaj obsługiwanymi urządzeniami jako urządzeniami z programem Android for Work** | Dozwolone | Wszystkie urządzenia z systemem Android, które obsługują program Android for Work, należy zarejestrować w programie Android for Work. |
| **Zarządzaj obsługiwanymi urządzeniami jako urządzeniami z programem Android for Work tylko dla użytkowników w tych grupach** | Zablokowane | Utworzono oddzielne zasady ograniczeń typów urządzeń, które przesłaniają domyślne zasady. Zasady te definiują wcześniej wybrane grupy, zezwalając na rejestrację w programie Android for Work. Użytkownicy z wybranych grup zachowają możliwość rejestrowania urządzeń programu Android for Work. Pozostali użytkownicy nie mogą rejestrować się w programie Android for Work. |

We wszystkich przypadkach zamierzone zasady są zachowywane. Nie są wymagane żadne działania użytkownika w celu zachowania możliwości korzystania z programu Android for Work w środowisku — zarówno w skali ogólnej, jak i w odniesieniu do poszczególnych grup.

### <a name="deprecating-support-for-os-x-mavericks-1010-and-previous-versions-of-macos---1489263-plan-for-change-for-1802--"></a>Wycofanie obsługi systemu OS X Mavericks 10.10 i wcześniejszych wersji systemu macOS <!--1489263, plan for change for 1802-->
Ogłaszamy, że w lutym 2018 roku rozpoczniemy wycofywanie obsługi rejestracji dla urządzeń z systemem OS X Yosemite 10.10 i wcześniejszymi wersjami systemu macOS. Usługa Intune w pełni obsługuje system OS X El Capitan 10.11 i jego nowsze wersje.

### <a name="new-path-for-managed-devices-in-graph-api----1586728---"></a>Nowa ścieżka dla urządzeń zarządzanych w interfejsie API programu Graph <!-- 1586728 -->
Zmieniamy ścieżkę dostępu do urządzeń zarządzanych w wersji beta interfejsu API programu Graph. 

| | |
|--|--|
| Bieżąca ścieżka |  https://graph.microsoft.com/beta/managedDevices |
| Nowa ścieżka | https://graph.microsoft.com/beta/deviceManagement/managedDevices |

Obie ścieżki będą działać przez cały październik. Po wydaniu październikowej wersji usługi będzie działać tylko nowa ścieżka.  Jeśli dostęp do urządzeń zarządzanych jest uzyskiwany za pomocą interfejsu API programu Graph, należy zaktualizować skrypty i aplikacje oraz sprawdzić, czy działają z nową ścieżką. Informacje na temat dodatkowych zmian zawiera comiesięczny [wykaz zmian interfejsu API programu Graph](https://developer.microsoft.com/graph/docs/concepts/changelog).


### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Bezpośredni dostęp do scenariuszy rejestracji firmy Apple <!--951869-->
Na kontach usługi Intune utworzonych po styczniu 2017 roku włączono bezpośredni dostęp do scenariuszy rejestracji firmy Apple przy użyciu obciążenia Rejestruj urządzenia w witrynie Azure Portal. Wcześniej podgląd rejestracji firmy Apple był dostępny tylko z poziomu linków w klasycznym portalu Intune. Konta usługi Intune utworzone przed styczniem 2017 roku wymagają przeprowadzenia jednorazowej migracji, zanim funkcje te będą dostępne w systemie Azure. Harmonogram migracji nie został jeszcze ogłoszony, ale szczegółowe informacje zostaną udostępnione najszybciej, jak będzie to możliwe. Zdecydowanie zalecamy utworzenie konta w wersji próbnej w celu przetestowania nowego środowiska pracy w przypadku, gdy istniejące konto nie ma dostępu do witryny Azure portal.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Zastąpienie ról administracyjnych w witrynie Azure Portal
Istniejące role administracyjne zarządzania aplikacjami mobilnymi (MAM) (współautor, właściciel, tylko do odczytu) używane w portalu klasycznym Intune (Silverlight) są zastępowane pełnym zestawem nowych kontroli administracyjnych opartych na rolach (RBAC) w witrynie Intune Azure Portal. Po migracji do witryny Azure Portal należy ponownie przypisać administratorów do nowych ról administracyjnych. Aby uzyskać więcej informacji na temat kontroli dostępu opartej na rolach (RBAC) i nowych ról, zobacz [Kontrola dostępu oparta na rolach w usłudze Microsoft Intune](/intune/role-based-access-control).

## <a name="whats-coming"></a>Wkrótce

### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866--"></a>Aktualizacja środowiska użytkownika aplikacji Portal firmy dla systemu iOS <!--1412866-->

Niedługo wydamy dużą aktualizację środowiska użytkownika w aplikacji Portal firmy dla systemu iOS. Aktualizacja obejmie całkowicie nowy projekt wizualny, w tym zmodernizowany wygląd i działanie oraz większą użyteczność i dostępność. Cała obecna funkcjonalność aplikacji Portal firmy dla systemu iOS zostanie zachowana.

Za pośrednictwem programu Apple TestFlight oferujemy wersję wstępną zaktualizowanej aplikacji Portal firmy dla systemu iOS, aby umożliwić korzystanie z niej i przesyłanie opinii na jej temat. Zarejestruj się pod adresem https://aka.ms/intune_ios_cp_testflight, aby uzyskać dostęp do programu TestFlight.

### <a name="conditional-access-policies-for-intune-will-only-be-available-from-the-azure-portal-----1737088---"></a>Zasady dostępu warunkowego dla usługi Intune będą teraz dostępne tylko z poziomu witryny Azure Portal <!-- 1737088 -->
Uproszczamy obszary, w których ma miejsce konfigurowanie i zarządzanie dostępem warunkowym. Obecnie dostępem warunkowym można zarządzać z poziomu bloku Ochrona aplikacji w usłudze Intune (MAM) i za pośrednictwem klasycznego środowiska usługi Azure AD w witrynie [Microsoft Azure Portal](https://manage.windowsazure.com). Począwszy od stycznia, konfigurowanie zasad i zarządzanie nimi będzie możliwe tylko z poziomu witryny [Azure Portal](https://portal.azure.com) w bloku **Azure Active Directory** > **Dostęp warunkowy**. Dla wygody możesz przejść do tego bloku z usługi Intune w witrynie Azure Portal w obszarze **Intune** > **Dostęp warunkowy**.

### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine---1592747--"></a>Zarządzanie urządzeniami z systemem macOS zarejestrowanymi w programie Jamf przy użyciu aparatu zgodności urządzenia usługi Intune <!--1592747-->
Od początku 2018 r. program Jamf będzie wysyłać informacje o stanie urządzenia z systemem macOS do usługi Intune, która następnie oceni je pod kątem zgodności z zasadami określonymi w konsoli usługi Intune. W oparciu o stan zgodności urządzenia, a także pozostałe warunki (takie jak lokalizacja, ryzyko związane z użytkownikiem itp.) dostęp warunkowy będzie wymuszać zgodność dla urządzeń z systemem macOS uzyskujących dostęp do chmury i lokalnych aplikacji połączonych z usługą Azure Active Directory oraz usługą Office 365.

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Zmiany w obsłudze aplikacji Portal firmy dla systemu iOS w usłudze Intune <!-- 1164474  -->
Wkrótce pojawi się nowa wersja aplikacji Portal firmy usługi Microsoft Intune dla systemu iOS, która obejmie tylko urządzenia z systemem iOS 9.0 lub nowszym. Wersja aplikacji Portal firmy obsługująca system iOS 8 będzie przez krótki okres nadal dostępna. Jeśli jednak są również używane aplikacje systemu iOS z obsługą funkcji MAM, obsługiwany jest system iOS 9.0 i nowsze wersje, więc należy zadbać o to, aby użytkownicy końcowi zaktualizowali system operacyjny do najnowszej wersji. 

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Informujemy o tym z wyprzedzeniem, mimo że nie podajemy konkretnych dat, aby zapewnić klientom czas na zaplanowanie działań. Zadbaj o to, aby użytkownicy zaktualizowali system do wersji iOS 9 lub nowszej, a po opublikowaniu aplikacji Portal firmy zwróć się do użytkowników końcowych o zaktualizowanie aplikacji Portal firmy.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Zalecamy powiadomienie użytkowników, aby przeprowadzili aktualizację do wersji iOS 9.0 lub nowszej w celu pełnego korzystania z nowych funkcji usługi Intune.  Zachęć użytkowników do zainstalowania nowej wersji aplikacji Portal firmy i korzystania z dostępnych w niej nowych funkcji.

Przejdź do usługi Intune w witrynie Azure Portal i wyświetl obszar Urządzenia > Wszystkie urządzenia. Przefiltruj widok według wersji systemu iOS, aby wyświetlić wszystkie bieżące urządzenia z systemami operacyjnymi wcześniejszym niż iOS 9.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Firma Apple będzie wymagać aktualizacji mechanizmu Application Transport Security <!--748318-->
Firma Apple ogłosiła, że będzie egzekwować pewne wymagania dotyczące mechanizmu Application Transport Security (ATS). Mechanizm ATS służy do wymuszania mocniejszych zabezpieczeń całej komunikacji aplikacji za pośrednictwem protokołu HTTPS. Ta zmiana wpływa na klientów usługi Intune korzystających z aplikacji Portalu firmy w systemie iOS.

Udostępniliśmy wersję aplikacji Portal firmy dla systemu iOS przy użyciu programu Apple TestFlight, który wymusza nowe wymagania ATS. Jeśli chcesz ją wypróbować, aby sprawdzić swoją zgodność z ATS, wyślij na adres e-mail <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> wiadomość ze swoim imieniem i nazwiskiem, adresem e-mail i nazwą firmy. Zapoznaj się z naszym [blogiem pomocy technicznej usługi Intune](https://aka.ms/compportalats), aby uzyskać więcej szczegółów.

## <a name="see-also"></a>Zobacz też
* [Blog usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plan platformy w chmurze](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Co nowego w interfejsie użytkownika aplikacji Portal firmy](whats-new-app-ui.md)
* [Nowości w poprzednich miesiącach](whats-new-archive.md)
