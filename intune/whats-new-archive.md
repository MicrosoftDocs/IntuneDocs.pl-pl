---
title: Nowości w poprzednich miesiącach w usłudze Microsoft Intune — platforma Azure | Microsoft Docs
titlesuffix: ''
description: Przejrzyj starsze powiadomienia o nowościach w usłudze Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/19/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ea9f8662faad1f8ef70fbba4c3706930d31157ac
ms.sourcegitcommit: 2d1e89fa5fa721e79648e41fde147a035e7b047d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/31/2018
ms.locfileid: "43347716"
---
# <a name="whats-new-in-the-microsoft-intune---previous-months"></a>Nowości w usłudze Microsoft Intune — poprzednie miesiące

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="november-2017"></a>Listopad 2017

### <a name="troubleshoot-enrollment-issues-----746324---"></a>Rozwiązywanie problemów z rejestracją <!-- 746324 -->

Problemy z rejestracją są teraz widoczne dla użytkownika w obszarze roboczym **Rozwiązywanie problemów**. Szczegółowe informacje o problemie i sugerowane kroki korygujące mogą ułatwić administratorom i operatorom pomocy technicznej rozwiązywanie problemów. Niektóre problemy z rejestracją nie są rejestrowane i dla niektórych błędów może nie być sugestii korekty.

### <a name="group-assigned-enrollment-restrictions----747598---"></a>Ograniczenia rejestracji przypisane do grupy <!-- 747598 -->

Administratorzy usługi Intune będą mogli [tworzyć niestandardowe ograniczenia rejestracji dotyczące typu urządzeń i limitu urządzeń dla grup użytkowników](enrollment-restrictions-set.md).

Witryna Azure Portal usługi Intune pozwala utworzyć maksymalnie 25 wystąpień poszczególnych typów ograniczeń, które można przypisać do grup użytkowników. Ograniczenia przypisane do grupy zastępują ograniczenia domyślne.

Wszystkie wystąpienia typu ograniczenia są przechowywane na ściśle uporządkowanej liście. Porządek ten określa wartości priorytetów na potrzeby rozwiązywania konfliktów. Jeśli użytkownika dotyczy więcej niż jedno wystąpienie ograniczeń, pod uwagę brane jest tylko wystąpienie o najwyższej wartości priorytetu. Priorytet danego wystąpienia można zmienić, przeciągając je do innej pozycji na liście.

Funkcja ta zostanie udostępniona podczas migracji ustawień programu Android for Work z menu rejestracji programu Android for Work do menu ograniczeń rejestracji. Ponieważ ta migracja może zająć kilka dni, zanim zostanie włączone przypisanie grupy do ograniczeń rejestracji, konto może zostać uaktualnione o inne funkcje wprowadzane w wersji listopadowej.

### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Obsługa wielu łączników usługi rejestracji urządzeń sieciowych (NDES) <!-- 1528104 -->

Usługa rejestracji urządzeń sieciowych (Network Device Enrollment Service, NDES) umożliwia urządzeniom przenośnym działającym bez poświadczeń domeny uzyskiwanie certyfikatów przy użyciu dodatku Prosty protokół rejestrowania certyfikatów (Simple Certificate Enrollment Protocol, SCEP).
Aktualizacja wprowadza obsługę wielu łączników usługi NDES.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Zarządzanie urządzeniami programu Android for Work w sposób niezależny od urządzeń z systemem Android <!-- 1490731 EEready-->

Usługa Intune obsługuje zarządzanie rejestracją urządzeń programu Android for Work w sposób niezależny od platformy Android. Opcje zarządzania tymi ustawieniami są dostępne w obszarze **Rejestrowanie urządzenia** > **Ograniczenia rejestracji** > **Ograniczenia typów urządzeń**. (Wcześniej znajdowały się one w obszarze **Rejestrowanie urządzeń** > **Rejestracja w programie Android for Work** > **Ustawienia rejestracji programu Android for Work**).

Domyślnie ustawienia urządzeń programu Android for Work są takie same jak ustawienia urządzeń z systemem Android. Nie będzie tak jednak w przypadku zmiany ustawień programu Android for Work.

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

### <a name="google-play-protect-support-on-android----908720---"></a>Obsługa funkcji Google Play Protect w urządzeniach z systemem Android <!-- 908720 -->

Wraz z wydaniem systemu Android Oreo firma Google wprowadza zestaw funkcji zabezpieczających Google Play Protect, który umożliwia użytkownikom i organizacjom uruchamianie bezpiecznych aplikacji oraz bezpiecznych obrazów dla systemu Android. Usługa Intune obsługuje teraz funkcje Google Play Protect, w tym funkcję zdalnego zaświadczania SafetyNet. Administratorzy mogą ustawić wymagania dotyczące zasad zgodności, które wymuszą konfigurację funkcji Google Play Protect oraz zapewnienie jej prawidłowego działania.
Ustawienie **zdalnego zaświadczania SafetyNet** wymaga połączenia się urządzenia z usługą Google w celu umożliwienia sprawdzenia, czy urządzenie jest w dobrej kondycji i czy jego zabezpieczenia nie zostały złamane. Administratorzy mogą również wybrać ustawienie profilu konfiguracji dla programu Android for Work, co spowoduje wprowadzenie wymogu, aby zainstalowane aplikacje były weryfikowane przez usługi Google Play. Jeśli urządzenie nie jest zgodne z wymaganiami funkcji Google Play Protect, dostęp warunkowy może uniemożliwić użytkownikom uzyskiwanie dostępu do zasobów firmy.

- Dowiedz się [Jak utworzyć zasady zgodności urządzenia w celu włączenia funkcji Google Play Protect](https://docs.microsoft.com/intune/compliance-policy-create-google-play-protect).

### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Protokół tekstowy dostępny w aplikacjach zarządzanych <!-- 1414050  -->

Aplikacje zarządzane przez zestaw SDK aplikacji usługi Intune mogą wysyłać wiadomości SMS.


### <a name="app-install-report-updated-to-include-install-pending-status----1249446---"></a>Raport instalacji aplikacji został zaktualizowany, aby obejmować stan Oczekująca instalacja <!-- 1249446 -->  

Raport **Stan instalacji aplikacji**, dostępny dla każdej aplikacji za pośrednictwem listy **Aplikacja** w obciążeniu **Aplikacje klienckie**, zawiera teraz licznik **Oczekująca instalacja** dla użytkowników i urządzeń.

### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>Interfejs API spisu aplikacji dla systemu iOS 11 na potrzeby wykrywania zagrożeń mobilnych<!-- 1391759 -->

Usługa Intune zbiera informacje dotyczące spisu aplikacji z urządzeń osobistych i firmowych i udostępnia je dostawcom usługi wykrywania zagrożeń mobilnych, na przykład aplikacji Lookout for Work. Możesz zbierać informacje o spisie aplikacji z urządzeń z systemem iOS 11 lub nowszym.

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

### <a name="migrate-hybrid-mdm-users-and-devices-to-intune-standalone----1463747-wnready---"></a>Migrowanie użytkowników i urządzeń hybrydowego zarządzania urządzeniami przenośnymi do autonomicznej usługi Intune <!-- 1463747 wnready -->
Dostępne są teraz nowe procesy i narzędzia służące do przenoszenia użytkowników i ich urządzeń z hybrydowego zarządzania urządzeniami przenośnymi do usługi Intune w witrynie Azure Portal, co umożliwia wykonywanie następujących zadań:
- Kopiowanie zasad i profilów z konsoli programu Configuration Manager do usługi Intune w witrynie Azure Portal
- Przenoszenie podzbioru użytkowników do usługi Intune w witrynie Azure Portal przy zachowaniu pozostałych w ramach hybrydowego zarządzania urządzeniami przenośnymi
- Migrowanie urządzeń do usługi Intune w witrynie Azure Portal bez konieczności ich ponownego rejestrowania

Aby uzyskać więcej informacji, zobacz [Migrowanie użytkowników i urządzeń hybrydowego zarządzania urządzeniami przenośnymi do autonomicznej usługi Intune](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa).

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Obsługa wysokiej dostępności łącznika lokalnego programu Exchange <!-- 676614 -->
Gdy łącznik programu Exchange utworzy połączenie z programem Exchange za pomocą określonego zabezpieczenia dostępu kodu, będzie mieć możliwość odnajdywania innych zabezpieczeń dostępu kodu. Jeśli podstawowe zabezpieczenia dostępu kodu będą niedostępne, łącznik przejdzie w tryb failover, korzystając z innych zabezpieczeń dostępu kodu (jeśli będą dostępne) do momentu przywrócenia dostępności podstawowych zabezpieczeń dostępu kodu. Szczegółowe informacje znajdują się w temacie [Obsługa wysokiej dostępności łącznika lokalnego programu Exchange](exchange-connector-install.md#on-premises-exchange-connector-high-availability-support).

### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>Zdalne ponowne uruchamianie urządzenia z systemem iOS (tylko tryb nadzorowany) <!-- 1424595 -->

Przy użyciu akcji urządzenia możesz teraz wyzwolić ponowne uruchomienie nadzorowanego urządzenia z systemem iOS 10.3 lub nowszym. Aby uzyskać więcej informacji na temat używania akcji ponownego uruchamiania urządzenia, zobacz [Zdalne ponowne uruchamianie urządzeń przy użyciu usługi Intune](device-restart.md).

> [!Note]
> To polecenie wymaga trybu nadzorowanego urządzenia i prawa dostępu do **blokady urządzenia**. Urządzenie jest natychmiast uruchamiane ponownie. Urządzenia z systemem iOS z blokadą opartą na kodzie dostępu nie połączą się z siecią Wi-Fi po ponownym uruchomieniu. Ponadto nawiązanie połączenia z serwerem może nie być możliwe.

### <a name="single-sign-on-support-for-ios----1333645---"></a>Obsługa logowania jednokrotnego dla systemu iOS <!-- 1333645 -->  

Użytkownicy systemu iOS mogą korzystać z logowania jednokrotnego. Aplikacje dla systemu iOS, które poszukują poświadczeń użytkownika w ładunku logowania jednokrotnego, zachowują swoją funkcjonalność po zaktualizowaniu konfiguracji ładunku. Nazwę główną i obszar można również skonfigurować przy użyciu nazwy UPN i identyfikatora urządzenia w usłudze Intune. Aby uzyskać szczegółowe informacje, zobacz [Konfigurowanie logowania jednokrotnego w usłudze Intune dla urządzeń z systemem iOS](sso-ios.md).

### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Dodanie aplikacji „Znajdź mój iPhone” dla urządzeń osobistych <!--1427287-->
Może teraz sprawdzić, czy urządzenia z systemem iOS mają włączoną blokadę aktywacji. Funkcja ta była wcześniej dostępna w klasycznym portalu usługi Intune.

### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Zdalne blokowanie urządzeń zarządzanych z systemem macOS przy użyciu usługi Intune <!-- 1437691 -->

Zgubione urządzenie z systemem macOS można zablokować przez ustawienie 6-cyfrowego numeru PIN odzyskiwania. Gdy blokada jest aktywna, do momentu wysłania innej akcji urządzenia na ekranie jest widoczny blok **Przegląd urządzenia** z monitem o numer PIN.

Aby uzyskać więcej informacji, zobacz [Zdalne blokowanie urządzeń zarządzanych przy użyciu usługi Intune](device-remote-lock.md).

### <a name="new-scep-profile-details-supported----1559808---"></a>Obsługa nowych szczegółów profilu SCEP <!-- 1559808 -->

Administratorzy mogą teraz określić dodatkowe ustawienia podczas tworzenia profilu SCEP na platformach Windows, iOS, macOS i Android.  Można na przykład ustawić kod IMEI, numer seryjny lub nazwę pospolitą obejmującą adres e-mail w formacie nazwy podmiotu.

<!-- #### Update to what device details your company may see -1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources. -->

### <a name="retain-data-during-a-factory-reset----1588489---"></a>Zachowywanie danych podczas resetowania do ustawień fabrycznych <!--1588489 -->
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


### <a name="window-10-update-ring-assignments-are-displayed----1621837---"></a>Wyświetlanie przypisań pierścienia aktualizacji systemu Windows 10 <!-- 1621837 -->
Podczas **rozwiązywania problemów** są widoczne wszystkie przypisania pierścieni aktualizacji systemu Windows 10 dla aktualnie wybranego użytkownika.  

### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings-----1455974----"></a>Ustawienia częstotliwości raportowania usługi Zaawansowana ochrona przed zagrożeniami usługi Windows Defender <!-- 1455974  -->
Usługa Zaawansowana ochrona przed zagrożeniami usługi Windows Defender (WDATP, Windows Defender Advanced Threat Protection) pozwala administratorom zmieniać częstotliwość raportowania dla zarządzanych urządzeń. Nowa opcja — **Usprawnij częstotliwość raportowania danych telemetrycznych** — umożliwia usłudze WDATP częstsze zbieranie danych i ocenianie ryzyka. Domyślne ustawienie raportowania pozwala zoptymalizować szybkość i wydajność. Zwiększenie częstotliwości raportowania może być przydatne w przypadku urządzeń narażonych na wysokie ryzyko. To ustawienie znajduje się w profilu usługi **Windows Defender ATP** w **konfiguracji urządzeń**.

### <a name="audit-updates----1412961---"></a>Aktualizacje inspekcji <!-- 1412961 -->  
Inspekcje w usłudze Intune udostępniają rejestr operacji zmian dotyczących usługi Intune.  Wszystkie operacje tworzenia, aktualizowania, usuwania i zadań zdalnych są przechwytywane i przechowywane przez jeden rok.  Witryna Azure Portal udostępnia filtrowany widok danych inspekcji poszczególnych obciążeń z ostatnich 30 dni.  Dostępny jest odpowiedni interfejs API programu Graph, umożliwiający pobieranie danych inspekcji z ostatniego roku.

Inspekcje można znaleźć w grupie **MONITOR**. Dla każdego obciążenia dostępny jest element menu **Dzienniki inspekcji**.

### <a name="company-portal-app-for-macos-is-available---1541700--"></a>Aplikacja Portal firmy dla systemu macOS jest dostępna <!--1541700-->
Aplikacja Portal firmy w usłudze Intune dla systemu macOS została zaktualizowana i zoptymalizowana, aby prawidłowo wyświetlać wszystkie informacje i powiadomienia o zgodności potrzebne użytkownikom do wszystkich zarejestrowanych urządzeń. Po wdrożeniu aplikacji Portal firmy w usłudze Intune na urządzeniu usługa Microsoft AutoUpdate dla systemu macOS zapewni jej aktualizacje. Nową wersję aplikacji Portal firmy w usłudze Intune dla systemu macOS można pobrać, logując się do witryny sieci Web aplikacji Portal firmy w usłudze Intune przy użyciu urządzenia z systemem macOS.

### <a name="microsoft-planner-is-now-part-of-the-mobile-app-management-mam-list-of-approved-apps-----1248473---"></a>Aplikacja Microsoft Planner znajduje się obecnie na liście zarządzania aplikacjami mobilnymi (MAM) zawierającej zatwierdzone aplikacje<!-- 1248473 -->
Aplikacja Microsoft Planner dla systemów iOS i Android należy obecnie do zatwierdzonych aplikacji funkcji zarządzania aplikacjami mobilnymi (MAM). Aplikację można skonfigurować za pomocą bloku Intune App Protection w witrynie Azure Portal na potrzeby wszystkich dzierżaw.
- Więcej informacji znajduje się na [liście zatwierdzonych aplikacji w funkcji zarządzania aplikacjami mobilnymi ](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

### <a name="per-app-vpn-requirement-update-frequency-on-ios-devices------1547061---"></a>Częstotliwość aktualizacji wymagań dotyczących sieci VPN dla aplikacji na urządzeniach z systemem iOS <!-- 1547061 -->  
Administratorzy mogą obecnie usuwać wymagania dotyczące sieci VPN dla aplikacji na urządzeniach z systemem iOS; operacja obejmie urządzenia po kolejnym zaewidencjonowaniu w usłudze Intune, które zwykle następuje w ciągu 15 minut.  

### <a name="support-for-system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Obsługa pakietu administracyjnego programu System Center Operations Manager dla łącznika programu Exchange <!-- 885457 -->
Pakiet administracyjny programu System Center Operations Manager (SCOM) dla łącznika programu Exchange jest obecnie dostępny, aby ułatwić analizowanie dzienników łącznika programu Exchange. Dzięki tej funkcji dostępne są różne sposoby monitorowania usługi, jeśli trzeba rozwiązać problemy.

### <a name="co-management-for-windows-10-devices-----1243445---"></a>Współzarządzanie dla urządzeń z systemem Windows 10 <!-- 1243445 -->
Współzarządzanie to rozwiązanie, które łączy zarządzanie tradycyjne z nowoczesnym i udostępnia ścieżkę umożliwiającą wprowadzanie zmian przy użyciu podejścia etapowego. Zasadniczo współzarządzanie jest rozwiązaniem, w którym urządzenia z systemem Windows 10 są jednocześnie zarządzane przez program Configuration Manager i usługę Microsoft Intune, a także połączone z usługami Active Directory (AD) i Azure Active Directory (Azure AD).  Taka konfiguracja umożliwia przyszłą modernizację w tempie odpowiednim dla organizacji, jeśli nie można przenieść wszystkiego naraz.  

### <a name="restrict-windows-enrollment-by-os-version----245498---"></a>Ograniczanie rejestracji systemu Windows na podstawie wersji systemu operacyjnego <!-- 245498 -->
Jako administrator usługi Intune możesz teraz określić minimalną i maksymalną wersję systemu Windows 10 na potrzeby rejestracji urządzeń. Ograniczenia te można ustawić w bloku **Konfiguracja platformy**.

Usługa Intune będzie nadal obsługiwała rejestrowanie komputerów i telefonów z systemem Windows 8.1. Jednak tylko wersje systemu Windows 10 można ustawić z limitami minimalnym i maksymalnym. Aby zezwolić na rejestrowanie urządzeń z systemem w wersji 8.1, minimalny limit należy pozostawić pusty.

### <a name="alerts-for-windows-autopilot-unassigned-devices-----1631236---"></a>Alerty dla urządzeń nieprzypisanych w programie Windows AutoPilot <!-- 1631236 -->
Dostępny jest nowy alert dotyczący urządzeń nieprzypisanych w programie Windows AutoPilot na stronie **Microsoft Intune** > **Rejestracja urządzeń** > **Przegląd**. Ten alert pokazuje, ile urządzeń z programu AutoPilot nie ma przypisanych profilów wdrożenia programu AutoPilot. Skorzystaj z informacji w alercie, aby utworzyć profile i przypisać je do nieprzypisanych urządzeń. Po kliknięciu alertu zostanie wyświetlona pełna lista urządzeń w programie Windows AutoPilot. Aby uzyskać więcej informacji, zobacz [Rejestrowanie urządzeń z systemem Windows przy użyciu programu Windows AutoPilot Deployment](https://docs.microsoft.com/intune/enrollment-autopilot).


### <a name="refresh-button-for-devices-list-------1333581---"></a>Przycisk Odśwież dla listy urządzeń <!-- 1333581 -->
Ponieważ lista urządzeń nie jest odświeżana automatycznie, można teraz używać nowego przycisku Odśwież, który służy do aktualizowania urządzeń wyświetlanych na liście.

### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Obsługa urzędu certyfikacji (CA) Symantec Cloud <!-- 1333638 -->    
Usługa Intune obsługuje teraz urząd certyfikacji Symantec Cloud, co pozwala łącznikowi Intune Certificate Connector na wystawianie certyfikatów PKCS z urzędu certyfikacji Symantec Cloud dla urządzeń zarządzanych przez usługę Intune. Jeśli łącznik certyfikatów usługi Intune jest już używany z urzędem certyfikacji (CA) firmy Microsoft, można wykorzystać istniejącą konfigurację łącznika certyfikatów usługi Intune w celu dodania obsługi urzędu certyfikacji firmy Symantec.

### <a name="new-items-added-to-device-inventory-----1404455---"></a>Nowe elementy dodane do spisu urządzeń <!--1404455 -->
Na potrzeby [spisu wykonywanego przez zarejestrowane urządzenia](device-inventory.md) są teraz dostępne następujące nowe elementy:

- Adres MAC sieci Wi-Fi
- Całkowita ilość miejsca
- Całkowita ilość wolnego miejsca
- MEID
- Nazwa operatora subskrybenta

### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Ustawianie dostępu dla aplikacji według minimalnego poziomu poprawki zabezpieczeń systemu Android na urządzeniu<!-- 1278463 -->   
Administrator może zdefiniować minimalny poziom poprawki zabezpieczeń systemu Android, który musi być zainstalowany na urządzeniu, aby można było uzyskać dostęp do aplikacji zarządzanej na koncie zarządzanym.

> [!Note]  
> Ta funkcja ogranicza poprawki zabezpieczeń opublikowane przez firmę Google wyłącznie na urządzeniach z systemem Android 6.0 lub nowszym.

### <a name="app-conditional-launch-support----1193313---"></a>Obsługa uruchamiania warunkowego aplikacji <!-- 1193313 -->
Administratorzy IT mogą teraz określić za pośrednictwem portalu administracyjnego platformy Azure wymaganie, aby podczas uruchamiania aplikacji było wymuszane wprowadzenie hasła, zamiast wprowadzania kodu liczbowego PIN za pośrednictwem funkcji zarządzania aplikacjami mobilnymi (MAM). W przypadku skonfigurowania tej opcji użytkownik musi określić hasło i użyć go po wyświetleniu monitu, zanim uzyska dostęp do aplikacji z obsługą funkcji zarządzania aplikacjami mobilnymi. Hasło jest zdefiniowane jako kod liczbowy PIN zawierający co najmniej jeden znak specjalny lub wielką/małą literę. W tej wersji usługi Intune ta funkcja jest dostępna **tylko w systemie iOS**. Usługa Intune obsługuje hasło w podobny sposób jak kod liczbowy PIN — określa minimalną długość, umożliwiając powtarzanie znaków i sekwencji. Funkcja ta wymaga udziału aplikacji (tj. WXP, Outlook, Managed Browser, Yammer) w celu integracji zestawu Intune App SDK przy użyciu kodu dla tej funkcji, dzięki czemu ustawienia kodu dostępu zostaną wymuszone w aplikacjach docelowych.

### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>Numery wersji aplikacji biznesowych w raporcie o stanie instalacji urządzenia <!-- 1233999 -->
W tej wersji w raporcie o stanie instalacji urządzenia wyświetlane są numery wersji aplikacji biznesowych dla systemów iOS i Android. Korzystając z tych informacji, można rozwiązywać problemy z aplikacjami lub znajdować urządzenia z nieaktualnymi wersjami aplikacji.

### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Administratorzy mogą teraz konfigurować ustawienia zapory na urządzeniu za pomocą profilu konfiguracji urządzenia <!-- 951708 -->   
Administratorzy mogą włączać zaporę dla urządzeń, a także konfigurować różne protokoły dla domeny oraz sieci prywatnych i publicznych.  Ustawienia zapory można znaleźć w profilu „Ochrona punktów końcowych”.

### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>Funkcja Windows Defender Application Guard ułatwia ochronę urządzeń przed niezaufanymi witrynami w sposób zdefiniowany przez Twoją organizację <!-- 958257 -->   
Używając przepływu pracy funkcji Windows Information Protection lub nowego profilu „Granica sieci” w konfiguracjach urządzeń, administratorzy mogą definiować witryny jako „zaufane” lub „firmowe”. Wszystkie witryny wyświetlane w przeglądarce Microsoft Edge, które nie znajdują się w granicach zaufanej sieci na urządzeniu z 64-bitowym systemem Windows 10, są otwierane w przeglądarce na komputerze wirtualnym funkcji Hyper-V.

Funkcję Application Guard można znaleźć w profilach konfiguracji urządzeń w profilu „Ochrona punktów końcowych”. W tym miejscu administratorzy mogą skonfigurować interakcję między zwirtualizowaną przeglądarką a komputerem hosta, zaufanymi i niezaufanymi witrynami oraz danymi magazynowania generowanymi w zwirtualizowanej przeglądarce. Aby można było używać funkcji Application Guard na urządzeniu, najpierw należy skonfigurować granicę sieci. Dla jednego urządzenia należy określić tylko jedną granicę sieci.  

### <a name="windows-defender-application-control-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>Funkcja Windows Defender Application Control w systemie Windows 10 Enterprise udostępnia tryb ufania tylko autoryzowanym aplikacjom <!-- 1031096 -->    
Tysiące nowych, złośliwych plików tworzonych każdego dnia powodują, że walka ze złośliwym oprogramowaniem przy użyciu wykrywania wirusów w oparciu o ich sygnatury może nie zapewniać już odpowiedniej obrony przed nowymi atakami. Korzystając z funkcji Windows Defender Application Control w systemie Windows 10 Enterprise, można zmienić konfigurację urządzenia z trybu, w którym aplikacje są zaufane, dopóki nie zostaną zablokowane przez program antywirusowy lub inne rozwiązanie z zakresu zabezpieczeń, na tryb, w którym system operacyjny ufa tylko aplikacjom autoryzowanym przez przedsiębiorstwo. Zaufanie do aplikacji można przypisać za pomocą funkcji Windows Defender Application Control.

Korzystając z usługi Intune, można skonfigurować zasady kontroli aplikacji w trybie „tylko do inspekcji” lub w trybie wymuszania. Aplikacje działające w trybie „tylko do inspekcji” nie są blokowane. Tryb „tylko do inspekcji” rejestruje wszystkie zdarzenia w lokalnych dziennikach klienta. Można również określić, czy mogą być uruchamiane wyłącznie składniki systemu Windows i aplikacje ze sklepu Microsoft Store, czy również inne aplikacje o dobrej reputacji zdefiniowane przez usługę Intelligent Security Graph.

### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>Windows Defender Exploit Guard to nowy zestaw funkcji zapobiegania nieautoryzowanemu dostępowi do systemu Windows 10 <!-- 1063615 -->   
Windows Defender Exploit Guard zawiera reguły niestandardowe, które ograniczają podatność aplikacji na wykorzystanie luk w zabezpieczeniach, zapobiega zagrożeniom w makrach i skryptach, automatycznie blokuje połączenia sieciowe z adresami IP o niskiej reputacji, a także umożliwia zabezpieczenie danych przed oprogramowaniem wymuszającym okup i nieznanymi zagrożeniami. Windows Defender Exploit Guard obejmuje następujące składniki:

- **Attack Surface Reduction (ASR)** zawiera reguły, które pozwalają zapobiegać zagrożeniom występującym w makrach, skryptach i wiadomościach e-mail.
- **Controlled Folder Access** automatycznie blokuje dostęp do zawartości do folderów chronionych.
- **Network Filter** blokuje połączenie wychodzące z dowolnej aplikacji do adresu IP/domeny o niskiej reputacji.
- **Exploit Protection** zapewnia ograniczenia pamięci, przepływu sterowania i zasad, które umożliwiają ochronę aplikacji przed lukami w zabezpieczeniach.

### <a name="manage-powershell-scripts-in-intune-for-windows-10-devices----790537---"></a>Zarządzanie skryptami programu PowerShell w usłudze Intune dla urządzeń z systemem Windows 10 <!-- 790537 -->

Rozszerzenie do zarządzania usługi Intune pozwala przekazywać skrypty programu PowerShell w usłudze Intune w celu uruchamiania ich na urządzeniach z systemem Windows 10. Rozszerzenie uzupełnia możliwości funkcji zarządzania urządzeniami mobilnymi (MDM, Mobile Device Management) z systemem Windows 10 i ułatwia migrację do nowoczesnego zarządzania. Aby uzyskać szczegółowe informacje, zobacz [Zarządzanie skryptami programu PowerShell w usłudze Intune dla urządzeń z systemem Windows 10](intune-management-extension.md).

### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Nowe ustawienia ograniczeń urządzeń z systemem Windows 10      <!-- 1308850 -->
-    Wiadomości (tylko dla urządzeń przenośnych) — wyłączenie testowania lub wiadomości MMS
-    Hasło — ustawienia umożliwiające włączanie standardu FIPS i uwierzytelnianie za pomocą dodatkowych urządzeń z usługą Windows Hello 
-    Ekran — ustawienia umożliwiające włączanie i wyłączanie skalowania graficznego interfejsu użytkownika dla starszych aplikacji

### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Ograniczenia urządzeń z systemem Windows 10 do trybu kiosku <!-- 1308872 -->   
Możesz ograniczyć użytkowników urządzeń z systemem Windows 10 do trybu kiosku, który ogranicza użytkownikom dostęp tylko do zestawu wstępnie zdefiniowanych aplikacji.  Aby to zrobić, należy utworzyć profil ograniczenia urządzenia z systemem Windows 10 i określić ustawienia kiosku.

Tryb kiosku obsługuje dwa tryby: **pojedynczej aplikacji** (pozwala użytkownikowi na uruchomienie tylko jednej aplikacji) lub **wielu aplikacji** (zezwala na dostęp do zestawu aplikacji).  Aby określić obsługiwane aplikacje, należy zdefiniować konto użytkownika i nazwę urządzenia.  Zalogowany użytkownik ma dostęp ograniczony do zdefiniowanych aplikacji.  Aby dowiedzieć się więcej, zobacz [AssignedAccess CSP (Dostawca usługi konfiguracji AssignedAccess)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp). 

Wymagania trybu kiosku:

- Usługa Intune musi być urzędem zarządzania urządzeniami przenośnymi.
- Aplikacje muszą być już zainstalowane na urządzeniu docelowym.
- Urządzenie musi być [poprawnie udostępniane](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions).

### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Nowy profil konfiguracji urządzeń do tworzenia granic sieci <!-- 1311967 -->   
Wśród profilów konfiguracji urządzeń można znaleźć nowy profil konfiguracji urządzeń o nazwie **Granica sieci**. Ten profil umożliwia zdefiniowanie zasobów online, które mają być uważane za firmowe i zaufane. Granicę sieci dla urządzenia należy zdefiniować *przed* użyciem na urządzeniu funkcji takich jak Windows Defender Application Guard i Windows Information Protection. Dla każdego urządzenia należy określić tylko jedną granicę sieci.

Jako zasoby, które mają zostać uznane za zaufane, można zdefiniować zasoby chmury przedsiębiorstwa, zakresy adresów IP i wewnętrzne serwery proxy. Zdefiniowana granica sieci może być używana przez inne funkcje, takie jak Windows Defender Application Guard i Windows Information Protection.

###  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Dwa dodatkowe ustawienia usługi Windows Defender Antivirus <!-- 1338409 -->  
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

### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Dodano sieć VPN Citrix dla urządzeń z systemem Windows 10 <!-- 1512457 -->  
Można skonfigurować sieć VPN Citrix dla swoich urządzeń z systemem Windows 10. Sieć VPN Citrix można wybrać na liście *Wybierz typ połączenia* w bloku **Podstawowa sieć VPN** podczas konfigurowania sieci VPN dla systemu Windows 10 i nowszych.

> [!Note]
> Konfiguracja serwera Citrix istniała dla systemów iOS i Android.

### <a name="wi-fi-connections-support-pre-shared-keys-on-ios----1550823---"></a>Połączenia sieci Wi-Fi obsługują klucze wstępne w systemie iOS<!-- 1550823 -->
Klienci mogą skonfigurować profile sieci Wi-Fi, aby używać kluczy wstępnych (PSK) dla połączeń WPA/WPA2 Personal na urządzeniach z systemem iOS. Te profile są wypychane na urządzenie użytkownika, kiedy urządzenie jest zarejestrowane w usłudze Intune.

Po wypchnięciu profilu do urządzenia następny krok zależy od konfiguracji profilu.  Jeśli ustawiono wartość Połącz automatycznie, połączenie z siecią jest nawiązywane automatycznie, kiedy jest potrzebne.  Jeśli w profilu ustawiono ręczne połączenie, użytkownik musi ręcznie uaktywnić połączenie.  

### <a name="access-to-managed-app-logs-for-ios----1469920---"></a>Dostęp do dzienników zarządzanych aplikacji dla systemu iOS <!-- 1469920 -->
Użytkownicy końcowi z zainstalowanym programem Managed Browser mogą teraz wyświetlać stan zarządzania wszystkich aplikacji opublikowanych przez firmę Microsoft i wysyłać dzienniki na potrzeby rozwiązywania problemów z ich zarządzanymi aplikacjami systemu iOS.

Dowiedz się, jak włączyć tryb rozwiązywania problemów w programie Managed Browser na urządzeniu z systemem iOS, zobacz [jak uzyskać dostęp do dzienników zarządzanych aplikacji przy użyciu programu Managed Browser w systemie iOS](app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios).

### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290----1417174---"></a>Ulepszenia przepływu pracy konfiguracji urządzenia w aplikacji Portal firmy dla systemu iOS w wersji 2.9.0 <!-- 1417174 -->

Ulepszono przepływ pracy konfiguracji urządzenia w aplikacji Portal firmy dla systemu iOS. Używany język jest bardziej przyjazny dla użytkownika i tam, gdzie było to możliwe, ekrany zostały połączone. Język jest lepiej dostosowany do Twojej firmy, ponieważ w tekście instalatora używana jest jej nazwa. Ten zaktualizowany przepływ pracy można wyświetlić na [stronie dotyczącej nowości w interfejsie użytkownika aplikacji](whats-new-app-ui.md).


### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>Jednostka użytkownika zawiera najnowsze dane użytkownika w modelu danych magazynu danych <!-- 1544273 -->
Pierwsza wersja modelu danych magazynu danych usługi Intune zawierała tylko ostatnie, historyczne dane usługi Intune. Podczas tworzenia raportu nie było możliwe uchwycenie bieżącego stanu użytkownika. Po wprowadzeniu tej aktualizacji **jednostka użytkownika** jest wypełniana najnowszymi danymi użytkownika.


## <a name="october-2017"></a>Październik 2017

### <a name="ios-and-android-line-of-business-app-version-number-is-visible----1380712---"></a>Widoczny numer wersji aplikacji biznesowej dla systemu iOS lub Android <!-- 1380712 -->

W usłudze Intune są teraz wyświetlane numery wersji aplikacji biznesowych dla systemu iOS lub Android. W witrynie Azure Portal numer jest widoczny na liście aplikacji i w bloku przeglądu aplikacji. Użytkownicy końcowi widzą numer aplikacji w aplikacji Portal firmy i w portalu internetowym.

__Pełny numer wersji__ Pełny numer wersji identyfikuje określoną wersję aplikacji. Numer ma postać _wersja_(_kompilacja_), na przykład 2.2(2.2.17560800).

Pełny numer wersji ma dwa składniki:

 - **Wersja**  
   Numer wersji to zrozumiały dla użytkownika numer wydania aplikacji. Jest on używany przez użytkowników końcowych do identyfikowania różnych wydań aplikacji.

 - **Numer kompilacji**  
    Numer kompilacji to numer wewnętrzny, który może być używany do wykrywania aplikacji i programowego zarządzania nią. Numer kompilacji dotyczy iteracji aplikacji, która odnosi się do zmian w kodzie.

Temat [Wprowadzenie do zestawu SDK aplikacji usługi Microsoft Intune](app-sdk-get-started.md#line-of-business-app-version-numbers) zawiera więcej informacji o numerach wersji i tworzeniu aplikacji biznesowych.

### <a name="device-and-app-management-integration----677972---"></a>Integracja zarządzania urządzeniami i aplikacjami <!-- 677972 -->   
Teraz, gdy funkcje zarządzania urządzeniami przenośnymi (MDM) i zarządzania aplikacjami mobilnymi (MAM) usługi Intune są już dostępne w witrynie Azure Portal, usługa Intune rozpoczęła integrowanie środowiska pracy administratora IT wokół zarządzania aplikacjami i urządzeniami. Zmiany mają na celu uproszczenie środowiska zarządzania urządzeniami i aplikacjami.

Dowiedz się więcej na temat zmian funkcji MDM i MAM ogłoszonych w [blogu zespołu pomocy technicznej usługi Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).

### <a name="new-enrollment-alerts-for-apple-devices----1471790---"></a>Nowe alerty rejestracji dla urządzeń firmy Apple <!-- 1471790 -->
Na stronie przeglądu rejestracji będą wyświetlane przydatne alerty dotyczące zarządzania urządzeniami firmy Apple, przeznaczone dla administratorów IT. Alerty na stronie przeglądu pojawią się, jeśli certyfikat wypychania MDM firmy Apple wkrótce wygaśnie bądź już wygasł lub token programu Device Enrollment Program wkrótce wygaśnie bądź już wygasł albo w programie Device Enrollment Program występują nieprzypisane urządzenia.

### <a name="support-token-replacement-for-app-configuration-without-device-enrollment----1080364---"></a>Obsługa zastępowania tokenu dla konfiguracji aplikacji bez rejestracji urządzeń <!-- 1080364 -->

Można używać tokenów dla wartości dynamicznych w konfiguracjach aplikacji na niezarejestrowanych urządzeniach. Aby uzyskać więcej informacji, zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych aplikacji bez rejestracji urządzeń](app-configuration-policies-managed-app.md).

### <a name="updates-to-the-company-portal-app-for-windows-10---1299474--"></a>Aktualizacje aplikacji Portal firmy dla systemu Windows 10 <!--1299474-->
Strona Ustawienia w aplikacji Portal firmy dla systemu Windows 10 została zaktualizowana, dzięki czemu ustawienia i spodziewane akcje użytkownika są bardziej spójne z pozostałymi ustawieniami. Zaktualizowany został również układ aplikacji, który teraz lepiej odpowiada układom innych aplikacji systemu Windows. Obrazy stanu przed i po aktualizacji znajdują się na stronie dotyczącej [nowości w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

### <a name="inform-end-users-what-device-information-can-be-seen-for-windows-10-devices---1337920--"></a>Powiadamianie użytkowników końcowych o widocznych informacjach dotyczących urządzeń dla systemu Windows 10 <!--1337920-->
Dodaliśmy element **Typ własności** do ekranu Szczegóły urządzenia w aplikacji Portal firmy dla systemu Windows 10. Dzięki temu użytkownicy mogą dowiedzieć się więcej o ochronie prywatności bezpośrednio z tej strony w dokumentach użytkownika końcowego usługi Intune. Mogą oni również zlokalizować te informacje na ekranie **Informacje**.

### <a name="feedback-prompts-for-the-company-portal-app-for-android---1165249--"></a>Monity o opinię użytkownika aplikacji Portal firmy dla systemu Android <!--1165249-->
Aplikacja Portal firmy dla systemu Android wyświetla teraz prośbę o opinię użytkownika końcowego. Opinia ta jest wysyłana bezpośrednio do firmy Microsoft i zapewnia użytkownikom końcowym możliwość opublikowania recenzji aplikacji w publicznym sklepie Google Play. Opinia nie jest wymagana, więc prośbę można łatwo odrzucić i dalej używać aplikacji.

<!-- #### Update to what device details an organization can see 1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources.-->

### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Ułatwianie użytkownikom samodzielnego rozwiązywania problemów przy użyciu aplikacji Portal firmy dla systemu Android <!-- 1573324, 1573150, 1558616, 1564878 -->

Do aplikacji Portal firmy dla systemu Android zostały dodane instrukcje dla użytkowników końcowych zawierające opisy problemów i umożliwiające — o ile to możliwe — samodzielne rozwiązywanie nowych przypadków użycia.
- W przypadku dodania maksymalnej dozwolonej liczby urządzeń użytkownicy końcowi zostaną przekierowani do [portalu usługi Azure Active Directory](https://account.activedirectory.windowsazure.com/r/#/profile) w celu usunięcia urządzenia.
- Użytkownicy otrzymają instrukcje ułatwiające [naprawienie błędów aktywacji na urządzeniach z systemem Samsung Knox](https://go.microsoft.com/fwlink/?linkid=859718) lub [wyłączenie trybu oszczędzania energii](/intune-user-help/power-saving-mode-android). Jeśli żadne z tych rozwiązań nie pozwoli rozwiązać problemu, udostępnimy wskazówki dotyczące [przesyłania dzienników do firmy Microsoft](/intune-user-help/send-logs-to-microsoft-android).

### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Nowa akcja „Rozwiąż” dostępna dla urządzeń z systemem Android <!-- 1583480 -->

W aplikacji Portal firmy dla systemu Android zostanie wprowadzona akcja „Rozwiąż”, dostępna na stronie _aktualizacji ustawień urządzenia_. Wybranie tej opcji spowoduje przejście bezpośrednio do ustawienia powodującego niezgodność urządzenia z zasadami. Aktualnie aplikacja Portal firmy dla systemu Android obsługuje tę akcję dla ustawień dotyczących [kodu dostępu urządzenia](/intune-user-help/set-your-pin-or-password-android), [debugowania USB](/intune-user-help/you-need-to-turn-off-usb-debugging-android) i [nieznanych źródeł](/intune-user-help/you-need-to-turn-off-unknown-sources-android).

### <a name="device-setup-progress-indicator-in-android-company-portal----1565657---"></a>Wskaźnik postępu konfiguracji urządzenia w aplikacji Portal firmy dla systemu Android <!-- 1565657 -->
Aplikacja Portal firmy dla systemu Android wyświetla wskaźnik postępu konfiguracji urządzenia, gdy użytkownik rejestruje swoje urządzenie. Wskaźnik przedstawia nowe stany, np. „Konfigurowanie urządzenia...”, następnie „Trwa rejestrowanie urządzenia...”, następnie „Kończenie rejestrowania urządzenia...”, następnie „Trwa kończenie konfigurowania urządzenia...”.

### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Obsługa uwierzytelniania opartego na certyfikatach w Portalu firmy dla systemu iOS <!--1029830-->
W aplikacji Portal firmy dla systemu iOS dodaliśmy obsługę uwierzytelniania opartego na certyfikatach (CBA). Użytkownicy korzystający z uwierzytelniania CBA wprowadzają swoją nazwę użytkownika, a następnie wybierają link „Zaloguj się przy użyciu certyfikatu”. Uwierzytelnianie CBA jest już obsługiwane w aplikacji Portal firmy dla systemów Android i Windows. Więcej informacji na ten temat można znaleźć na stronie [logowania się w aplikacji Portal firmy](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal).

### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Aplikacje dostępne z rejestracją lub bez rejestracji można teraz instalować bez monitów o rejestrację. <!-- 1334712 -->

Aplikacje firmowe, które udostępniono z rejestracją lub bez rejestracji w aplikacji Portal firmy dla systemu Android, można teraz zainstalować bez monitu o rejestrację.

### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune-----747617----"></a>Obsługa programu Windows AutoPilot Deployment w usłudze Microsoft Intune <!-- 747617  -->
Przy użyciu programu usługi Microsoft Intune z programem Windows AutoPilot Deployment możesz umożliwiać użytkownikom aprowizację urządzeń firmowych bez angażowania w to działu IT. Możesz dostosować tryb OOBE i przeprowadzić użytkowników przez proces dołączania urządzenia do usługi Azure AD i jego rejestracji w usłudze Intune. Dzięki współdziałaniu usługi Microsoft Intune i programu Windows AutoPilot nie ma potrzeby wdrażania i utrzymywania obrazów systemu operacyjnego ani zarządzania nimi. Aby uzyskać szczegółowe informacje, zobacz [Rejestrowanie urządzeń z systemem Windows przy użyciu programu Windows AutoPilot Deployment](https://docs.microsoft.com/intune/enrollment-autopilot).

### <a name="quick-start-for-device-enrollment-----1425655---"></a>Szybki start dla rejestracji urządzeń <!-- 1425655 --> 
Szybki start jest teraz dostępny w **rejestracji urządzeń** i zawiera tabelę odwołań dla zarządzania platformami i konfigurowania procesu rejestracji. Krótki opis każdego elementu i linki do dokumentacji z instrukcjami krok po kroku ułatwiają rozpoczęcie pracy.

### <a name="device-categorization----1427491---"></a>Kategoryzacja urządzeń <!-- 1427491 -->
Zestawienie platform zarejestrowanych urządzeń w bloku **Urządzenia > Przegląd** organizuje urządzenia według platform, w tym systemów Android, iOS, macOS, Windows i Windows Mobile.  Urządzenia z innymi systemami operacyjnymi znajdują się w grupie „Inne”.  Są to urządzenia wyprodukowane przez firmy Blackberry, NOKIA i inne.  

Aby dowiedzieć się, których urządzeń w dzierżawie to dotyczy, wybierz pozycję **Zarządzaj > Wszystkie urządzenia**, a następnie przy użyciu funkcji **Filtruj** ogranicz pole **System operacyjny**.

### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium — nowy partner usługi Mobile Threat Defense <!-- 954681 -->  
Dostęp urządzeń przenośnych do zasobów firmy można kontrolować przy użyciu dostępu warunkowego opartego na ocenie ryzyka przeprowadzanej przez usługę Zimperium. Jest to rozwiązanie chroniące przed zagrożeniami bezpieczeństwa urządzeń przenośnych zintegrowane z usługą Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Jak działa integracja z usługą Intune
Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń z uruchomionym rozwiązaniem Zimperium. Zasady dostępu warunkowego usług EMS można skonfigurować w oparciu o ocenę ryzyka przeprowadzaną przez rozwiązanie Zimperium włączane przy użyciu zasad zgodności urządzeń usługi Intune, których w przypadku niezgodnego urządzenia można użyć do zezwalania na dostęp do zasobów firmy lub blokowania go w oparciu o wykryte zagrożenia.

### <a name="new-settings-for-windows-10-device-restriction-profile------978575-1308849---"></a>Nowe ustawienia dla profilu ograniczeń urządzenia z systemem Windows 10 <!--- 978575, 1308849, -->  
Dodajemy nowe ustawienia do profilu ograniczeń urządzenia z systemem Windows 10 w kategorii Windows Defender SmartScreen.

Aby uzyskać szczegółowe informacje o profilu ograniczeń urządzenia z systemem Windows 10, zobacz [Ustawienia ograniczeń urządzenia z systemem Windows 10 lub nowszym]( device-restrictions-windows-10.md).

### <a name="remote-support-for-windows-and-windows-mobile-devices------1070473---"></a>Zdalna pomoc techniczna dla urządzeń z systemem Windows i Windows Mobile <!-- 1070473 -->  
Usługa Intune umożliwia teraz korzystanie z zakupionego osobno oprogramowania [TeamViewer](https://www.teamviewer.com), aby umożliwić oferowanie pomocy zdalnej użytkownikom urządzeń z systemem Windows i Windows Mobile.

### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Skanowanie urządzeń z użyciem usługi Windows Defender <!-- 1280988  1280990   -->
Na zarządzanych urządzeniach z systemem Windows 10 możliwe jest teraz uruchomienie **szybkiego skanowania** i **pełnego skanowania** oraz przeprowadzenie **aktualizacji sygnatur** z użyciem programu antywirusowego Windows Defender. W bloku przeglądu urządzenia wybierz akcję do przeprowadzenia na urządzeniu. Przed wysłaniem polecenia do urządzenia zostanie wyświetlony monit o potwierdzenie akcji. 

**Szybkie skanowanie**: szybkie skanowanie obejmuje lokalizacje, w których złośliwe oprogramowanie rejestruje się w celu umożliwienia jego uruchomienia, np. klucze rejestru i znane foldery uruchamiania systemu Windows. Szybkie skanowanie trwa średnio pięć minut. W połączeniu z ustawieniem **zawsze włączonej ochrony w czasie rzeczywistym**, które skanuje pliki, gdy są one otwierane i zamykane, a także za każdym razem, gdy użytkownik przejdzie do folderu, szybkie skanowanie pomaga chronić przed złośliwym oprogramowaniem, które może być obecne w systemie lub w jądrze. Po zakończeniu skanowania użytkownicy widzą jego wyniki na swoich urządzeniach. 

**Pełne skanowanie**: pełne skanowanie przydaje się w przypadku urządzeń, w których wystąpiło zagrożenie związane ze złośliwym oprogramowaniem, ponieważ pozwala określić, czy istnieją nieaktywne składniki, które wymagają dokładniejszego czyszczenia; funkcja umożliwia także uruchamianie skanowania na żądanie. Pełne skanowanie może trwać godzinę. Po zakończeniu skanowania użytkownicy widzą jego wyniki na swoich urządzeniach. 

**Zaktualizuj sygnatury**: polecenie aktualizacji sygnatur powoduje aktualizację definicji i sygnatur złośliwego oprogramowania programu antywirusowego Windows Defender. Można w ten sposób upewnić się, że program antywirusowy Windows Defender skutecznie wykrywa złośliwe oprogramowanie. Ta funkcja jest dostępna wyłącznie dla urządzeń z systemem Windows 10 i wymaga połączenia z Internetem. 

### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal-----1400455---"></a>Przycisk Włącz/Wyłącz został usunięty ze strony urzędu certyfikacji usługi Intune w witrynie Azure Portal usługi Intune <!-- 1400455 -->
 Eliminujemy dodatkowy krok z konfiguracji łącznika certyfikatów w usłudze Intune. Obecnie należy pobrać łącznik certyfikatów, a następnie włączyć go w konsoli usługi Intune. Jeśli jednak wyłączysz łącznik w konsoli usługi Intune, łącznik wciąż wydaje certyfikaty.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Począwszy od października przycisk Włącz/Wyłącz nie będzie już wyświetlany na stronie urzędu certyfikacji w witrynie Azure Portal. Funkcje łącznika pozostają bez zmian. Certyfikaty są wciąż wdrażane na urządzeniach zarejestrowanych w usłudze Intune. Nadal możesz pobrać i zainstalować łącznik certyfikatów. Aby zatrzymać wydawanie certyfikatów, zamiast wyłączać łącznik certyfikatów należy go teraz odinstalować.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Jeśli łącznik certyfikatów jest obecnie wyłączony, należy go odinstalować.

### <a name="new-settings-for-windows-10-team-device-restriction-profile-------1308838---"></a>Nowe ustawienia dla profilu ograniczeń urządzenia z systemem Windows 10 Team <!--- 1308838 -->
W tym wydaniu dodaliśmy wiele nowych ustawień profilu ograniczeń urządzenia z systemem Windows 10 Team ułatwiających kontrolę urządzeń Surface Hub.

Aby uzyskać więcej informacji o tym profilu, zobacz artykuł [Windows 10 Team device restriction settings](device-restrictions-windows-10-teams.md) (Ustawienia ograniczeń urządzenia z systemem Windows 10 Team).

### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Uniemożliwianie użytkownikom urządzeń z systemem Android zmiany daty i godziny ich urządzeń <!-- 1333292 -->
Można użyć [niestandardowych zasad urządzeń z systemem Android](custom-settings-android.md), aby uniemożliwić użytkownikom urządzeń z systemem Android zmianę daty i godziny urządzenia.

W tym celu należy skonfigurować niestandardowe zasady systemu Android, korzystając z identyfikatora URI ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange Dla powyższego identyfikatora URI należy wybrać wartość **TRUE**, a następnie przypisać go do wymaganych grup.

### <a name="bitlocker-device-configuration----1397398---"></a>Konfiguracja urządzenia z użyciem funkcji BitLocker <!-- 1397398 -->
Wybierając pozycję **Szyfrowanie systemu Windows > Ustawienia podstawowe**, można uzyskać dostęp do nowego ustawienia **Ostrzeżenie dotyczące innego szyfrowania dysku** pozwalającego wyłączyć [monit ostrzegawczy](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) dotyczący innego szyfrowania, które mogło zostać użyte na urządzeniu użytkownika.  Przed rozpoczęciem konfiguracji funkcji BitLocker na urządzeniu zostanie wyświetlony monit ostrzegawczy wymagający zgody użytkownika końcowego; konfiguracja funkcji BitLocker będzie blokowana do czasu potwierdzenia przez użytkownika końcowego.  Nowe ustawienie wyłącza ostrzeżenie użytkownika końcowego.


### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant----800882---"></a>Aplikacje programu Volume Purchase Program for Business będą się teraz synchronizowały z dzierżawą usługi Intune <!-- 800882 -->  
Deweloperzy innych firm mogą prywatnie dystrybuować aplikacje do autoryzowanych członków programu Volume Purchase Program (VPP) for Business określonych w usłudze iTunes Connect. Ci członkowie programu VPP for Business mogą zalogować się do sklepu Volume Purchase Program App Store i zakupić ich aplikacje.

W tej wersji aplikacje programu VPP for Business zakupione przez użytkownika końcowego będą się teraz synchronizowały z ich dzierżawami usługi Intune.

### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Wybór krajowego sklepu Apple do synchronizacji aplikacji VPP <!-- 1332311 -->  
Podczas przekazywania tokenu programu VPP można skonfigurować krajowy sklep do obsługi programu zakupów zbiorczych (VPP, ang. Volume Purchase Program). Usługa Intune synchronizuje aplikacje VPP z określonego krajowego sklepu umożliwiającego korzystanie z programu zakupów zbiorczych zgodnie ze wszystkimi ustawieniami regionalnymi.

> [!NOTE]  
> Obecnie usługa Intune synchronizuje tylko aplikacje VPP z krajowego sklepu umożliwiającego korzystanie z programu zakupów zbiorczych zgodnego z ustawieniami regionalnymi usługi Intune dla lokalizacji, w której została utworzona dzierżawa usługi Intune.


### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Blokowanie kopiowania i wklejania między profilami służbowymi i osobistymi w aplikacji Android for Work <!-- 1098994 -->
W tej wersji można skonfigurować profil służbowy w programie Android for Work w taki sposób, aby kopiowanie i wklejanie danych między aplikacjami służbowymi i osobistymi było blokowane. To nowe ustawienie można znaleźć w profilu **Ograniczenia urządzenia** platformy **Android for Work** w obszarze **Ustawienia profilu służbowego**.

### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Tworzenie aplikacji dla systemu iOS ograniczonych do określonych regionalnych sklepów Apple App Store <!-- 1281692 -->
Podczas tworzenia zarządzanej aplikacji przeznaczonej do sklepu Apple App Store można określić ustawienia regionalne dla kraju.

> [!Note]  
> Obecnie można tworzyć wyłącznie zarządzane aplikacje dla sklepu Apple App Store dostępne w amerykańskiej wersji strony sklepu.

###  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Aktualizacja aplikacji VPP dla systemu iOS z licencją użytkownika i urządzenia <!-- 1305564 -->  
Można skonfigurować token programu VPP systemu iOS pod kątem aktualizacji wszystkich aplikacji zakupionych dla danego tokenu za pośrednictwem usługi Intune. Usługa Intune wykryje aktualizacje aplikacji VPP w sklepie z aplikacjami i automatycznie wypchnie je do urządzenia po jego zaewidencjonowaniu.

Aby poznać procedurę ustawiania tokenu VPP i włączania automatycznych aktualizacji, zobacz [Jak w usłudze Microsoft Intune zarządzać aplikacjami dla systemu iOS, które zostały zakupione w ramach programu zakupów zbiorczych] (/intune/vpp-apps-ios).


### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Kolekcja jednostek skojarzenia urządzenia użytkownika dodana do modelu danych magazynu danych usługi Intune <!-- 1187917 -->
Można teraz tworzyć raporty i wizualizacje danych, korzystając z informacji skojarzenia urządzenia użytkownika, które odpowiadają za skojarzenie użytkownika i kolekcji jednostek urządzenia. Dostęp do modelu danych można uzyskać, korzystając z pliku usługi Power BI (PBIX) pobranego ze strony magazynu danych usługi Intune, za pośrednictwem punktu końcowego OData lub poprzez utworzenie niestandardowego klienta.

### <a name="review-policy-compliance-for-windows-10-update-rings----1067886---"></a>Przegląd zasad zgodności pod kątem pierścieni aktualizacji systemu Windows 10 <!-- 1067886 -->
Można przejrzeć raport zasad odnoszący się do pierścieni aktualizacji systemu Windows 10, przechodząc do obszaru Aktualizacje oprogramowania > Stan wdrożenia według pierścienia aktualizacji. Raport zasad zawiera stan wdrożenia dla skonfigurowanych pierścieni aktualizacji. 

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Nowy raport, który zawiera listę urządzeń dla systemu iOS ze starszymi wersjami systemu iOS   <!-- 1352223 -->
Raport **Nieaktualne urządzenia z systemem iOS** jest dostępny z poziomu obszaru roboczego **Aktualizacje oprogramowania**. W raporcie można przejrzeć listę nadzorowanych urządzeń z systemem iOS, których dotyczyły zasady aktualizacji systemu iOS i które mają dostępne aktualizacje. Dla każdego urządzenia można wyświetlić stan z informacją, dlaczego urządzenie nie zostało zaktualizowane automatycznie. 

### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Wyświetlanie przypisań zasad ochrony aplikacji w celu rozwiązywania problemów <!--  1475003 -->
W nadchodzącym wydaniu opcja **zasad ochrony aplikacji** zostanie dodana do listy rozwijanej **Przypisania** dostępnej w bloku rozwiązywania problemów. Teraz możesz wybrać zasady ochrony aplikacji, aby wyświetlić zasady ochrony aplikacji przypisane do wybranych użytkowników.



### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>Ulepszenia przepływu pracy konfiguracji urządzenia w Portalu firmy <!--1490692-->
Ulepszyliśmy przepływ pracy konfiguracji urządzenia w aplikacji Portal firmy dla systemu Android. Język jest bardziej przyjazny dla użytkownika i specyficzny dla Twojej firmy, a w miarę możliwości ekrany zostały połączone. Możesz to zobaczyć na stronie [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md#week-of-october-2-2017).

### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Ulepszone wskazówki dotyczące żądania dostępu do kontaktów na urządzeniach z systemem Android <!--1484985-->

Aplikacja Portal firmy dla systemu Android często wymaga od użytkownika końcowego zaakceptowania uprawnień do kontaktów. Jeśli użytkownik końcowy odmówi dostępu, zobaczy w aplikacji powiadomienie z alertem dotyczącym przyznania aplikacji dostępu warunkowego. 

### <a name="secure-startup-remediation-for-android---1490712--"></a>Korygowanie bezpiecznego uruchamiania dla systemu Android <!--1490712-->

Użytkownicy końcowi mający urządzenia z systemem Android będą mogli wybierać przyczynę niezgodności w aplikacji Portal firmy. Gdy będzie to możliwe, przeniesie to ich bezpośrednio do poprawnej lokalizacji w aplikacji ustawień, aby rozwiązać ten problem. 

### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo---1475932--"></a>Dodatkowe powiadomienia wypychane dla użytkowników końcowych w aplikacji Portal firmy dla systemu Android Oreo <!--1475932-->

Użytkownicy końcowi będą widzieli dodatkowe powiadomienia, gdy aplikacja Portal firmy dla systemu Android Oreo wykonuje zadania w tle, takie jak pobieranie zasad z usługi Intune. Powoduje to zwiększenie przejrzystości dla użytkowników końcowych przez informowanie ich, kiedy aplikacja Portal firmy wykonuje zadania administracyjne na ich urządzeniach. Jest to część ogólnej [optymalizacji interfejsu użytkownika aplikacji Portal firmy](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) dla aplikacji Portal firmy dla systemu Android Oreo. 

Istnieją dodatkowe optymalizacje dla nowych elementów interfejsu użytkownika, które są włączone w systemie Android Oreo.  Użytkownicy końcowi zobaczą dodatkowe powiadomienia, które będą wskazywać im, kiedy Portal firmy wykonuje zadania w tle, takie jak pobieranie zasad z usługi Intune.  Powoduje to zwiększenie przejrzystości dla użytkowników końcowych dzięki informowaniu ich, kiedy aplikacja Portal firmy wykonuje zadania administracyjne na urządzeniu.

### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Nowe zachowanie aplikacji Portal firmy dla systemu Android z profilami służbowymi <!-- 1485783 -->

Po zarejestrowaniu urządzenia z programem Android for Work i z profilem służbowym to właśnie aplikacja Portal firmy w profilu służbowym wykonuje na urządzeniu zadania z zakresu zarządzania. 

Jeśli użytkownik nie korzysta w profilu osobistym z aplikacji z obsługą zasad zarządzania aplikacjami mobilnymi (MAM), aplikacja Portal firmy dla systemu Android nie pełni już żadnej roli. Aby ulepszyć środowisko pracy w profilu służbowym, po pomyślnej rejestracji profilu służbowego usługa Intune automatycznie ukrywa aplikację Portal firmy z profilu osobistego.

Aplikację Portal firmy dla systemu Android można w dowolnym momencie włączyć w profilu osobistym, wybierając [aplikację Portal firmy w Sklepie Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) i wybierając opcję **Włącz**.

### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Utrzymanie aplikacji Portal firmy w systemach Windows 8.1 i Windows Phone 8.1 <!--1428681-->

Począwszy od października 2017 roku aplikacje Portal firmy zostaną utrzymane w systemach Windows 8.1 i Windows Phone 8.1. Oznacza to, że aplikacje i istniejące scenariusze, np. scenariusze rejestracji i zgodności, będą nadal obsługiwane przez te platformy. Aplikacje te będą nadal dostępne do pobrania za pośrednictwem istniejących kanałów, takich jak Sklep Microsoft. 

Po zatwierdzeniu utrzymania tych aplikacji będą dla nich udostępniane wyłącznie krytyczne aktualizacje zabezpieczeń. Nie będzie dla nich żadnych dodatkowych aktualizacji i nie będą w nich udostępniane żadne nowe funkcje. W celu skorzystania z nowych funkcji zalecamy aktualizację urządzenia do systemu Windows 10 lub Windows 10 Mobile. 


### <a name="block-unsupported-samsung-knox-device-enrollment-----1490695---"></a>Blokowanie nieobsługiwanej rejestracji urządzenia z systemem Samsung Knox <!-- 1490695 -->

Aplikacja Portal firmy tylko próbuje zarejestrować obsługiwane urządzenia z systemem Samsung Knox. Aby uniknąć błędów aktywacji systemu Knox, które uniemożliwiają rejestrację w usłudze MDM, próba rejestracji urządzenia nastąpi tylko wtedy, gdy urządzenie znajduje się na [liście urządzeń opublikowanej przez firmę Samsung](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Urządzenia firmy Samsung z określonymi numerami modelu mogą obsługiwać system Knox, podczas gdy inne go nie obsługują. Sprawdź zgodność systemu Knox u odsprzedawcy urządzenia przed zakupem i wdrożeniem. Pełną listę zweryfikowanych urządzeń można znaleźć w [ustawieniach zasad systemu Android i systemu Samsung Knox Standard](/intune/supported-devices-browsers.md#intune-supported-web-browsers).

### <a name="end-of-support-for-android-43-and-lower----1171126-1326920---"></a>Zakończenie obsługi dla systemu Android 4.3 i starszych <!-- 1171126, 1326920 -->
Aplikacje zarządzane i aplikacja Portal firmy dla systemu Android będą wymagać systemu Android 4.4 lub nowszego, aby można było uzyskiwać dostęp do zasobów firmy. Od grudnia zostanie wymuszone wycofanie wszystkich zarejestrowanych urządzeń, co spowoduje utratę dostępu do zasobów firmy. Jeśli używasz zasad ochrony aplikacji bez zarządzania urządzeniami przenośnymi, aplikacje nie będą otrzymywać aktualizacji, a jakość obsługi będzie się pogarszać wraz z upływem czasu.

### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Powiadamianie użytkowników końcowych o informacjach o urządzeniu widocznych na zarejestrowanych urządzeniach <!--1165314-->
Dodajemy element **Typ własności** do ekranu Szczegóły urządzenia we wszystkich aplikacjach Portal firmy. Dzięki temu użytkownicy mogą dowiedzieć się więcej o ochronie prywatności bezpośrednio z artykułu [Jakie informacje może wyświetlać Twoja firma?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune). Zostanie to wdrożone we wszystkich aplikacjach Portal firmy w najbliższej przyszłości. Zapowiedzieliśmy to dla systemu iOS we [wrześniu](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017).

## <a name="september-2017"></a>Wrzesień 2017

### <a name="intune-supports-ios-11---1428975--"></a>Usługa Intune obsługuje system iOS 11 <!--1428975-->
Usługa Intune obsługuje system iOS 11. Zostało to wcześniej zapowiedziane na [blogu dotyczącym pomocy technicznej usługi Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/).

### <a name="end-of-support-for-ios-80----1164477---"></a>Zakończenie obsługi dla systemu iOS 8.0 <!-- 1164477 -->
Aplikacje zarządzane i aplikacja Portal firmy dla systemu iOS będą wymagać systemu iOS 9.0 lub nowszego, aby można było uzyskiwać dostęp do zasobów firmy. Urządzenia, które nie zostaną zaktualizowane do września tego roku, nie będą już mogły uzyskiwać dostępu do aplikacji Portal firmy i tych aplikacji. 

### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Dodanie akcji odświeżenia do aplikacji Portal firmy dla systemu Windows 10 <!--1132468-->
Aplikacja Portal firmy dla systemu Windows 10 pozwala użytkownikom odświeżać dane w aplikacji poprzez przeciągnięcie ekranu lub — w przypadku komputerów — naciśnięcie klawisza F5.

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Powiadamianie użytkowników końcowych, o widocznych w systemie iOS informacjach o urządzeniu <!--739894-->

Dodaliśmy element **Typ własności** do ekranu Szczegóły urządzenia w aplikacji Portal firmy dla systemu iOS. Dzięki temu użytkownicy mogą dowiedzieć się więcej o ochronie prywatności bezpośrednio z tej strony w dokumentach użytkownika końcowego usługi Intune. Mogą oni również zlokalizować te informacje na ekranie Informacje.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Zezwalanie użytkownikom na dostęp do aplikacji Portal firmy dla systemu Android bez rejestracji <!---1169910--->

Wkrótce użytkownicy końcowi nie będą musieli rejestrować urządzeń, aby uzyskać dostęp do aplikacji Portal firmy dla systemu Android. Użytkownicy końcowi w organizacjach używających zasad ochrony aplikacji nie będą już otrzymywać monitów o zarejestrowanie swoich urządzeń po otwarciu aplikacji Portal firmy. Ponadto użytkownicy końcowi będą mogli instalować aplikacje z poziomu aplikacji Portal firmy bez konieczności rejestrowania urządzeń. 


### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android----1396349---"></a>Bardziej zrozumiałe komunikaty w aplikacji Portal firmy dla systemu Android <!---1396349--->  

Proces rejestracji w aplikacji Portal firmy dla systemu Android został uproszczony poprzez dodanie nowego tekstu w celu ułatwienia użytkownikom końcowym przeprowadzenia procesu rejestracji. Jeśli masz dokumentację rejestracji niestandardowej, możesz ją zaktualizować, aby odzwierciedlić nowe ekrany. Przykładowe obrazy można znaleźć na naszej stronie [aktualizacji interfejsu użytkownika dla aplikacji użytkownika końcowego usługi Intune](whats-new-app-ui.md#week-of-september-11-2017).

### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Dodanie aplikacji Portal firmy dla systemu Windows 10 do zasad zezwoleń funkcji Windows Information Protection <!-- 677129 -->

Aplikacja Portal firmy dla systemu Windows 10 została zaktualizowana w celu umożliwienia obsługi funkcji Windows Information Protection (WIP). Aplikację można dodać do zasad zezwoleń funkcji WIP. Dzięki tej zmianie nie trzeba dodawać żadnych aplikacji do listy **Wyklucz**.


## <a name="august-2017"></a>Sierpień 2017

### <a name="improvements-to-device-overview----1404453---"></a>Ulepszenia w zakresie przeglądu urządzeń <!-- 1404453 -->  
Dzięki ulepszeniom przegląd urządzeń wyświetla teraz zarejestrowane urządzenia, ale pomija urządzenia zarządzane przez program Exchange ActiveSync. Urządzenia programu Exchange ActiveSync nie mają tych samych opcji zarządzania co zarejestrowane urządzenia. Aby wyświetlić liczbę zarejestrowanych urządzeń i liczbę zarejestrowanych urządzeń według platformy, w usłudze Intune w witrynie Azure Portal przejdź do pozycji **Urządzenia** > **Przegląd**.

### <a name="improvements-to-device-inventory-collected-by-intune"></a>Ulepszenia dotyczące spisu urządzeń zebranego przez usługę Intune
<!-- 961134, 1104426, 1281327, 1333543 --> W tej wersji wprowadziliśmy następujące ulepszenia dotyczące informacji o spisie zbieranych przez zarządzane urządzenia:
 
-   W przypadku urządzeń z systemem Android możesz teraz dodać do spisu urządzeń kolumnę wyświetlającą poziom ostatniej poprawki dla każdego urządzenia. Dodaj kolumnę **Poziom poprawek bezpieczeństwa** do listy urządzeń, aby to zobaczyć.
-   Podczas filtrowania widoku urządzeń możesz teraz filtrować urządzenia według daty ich zarejestrowania. Możesz na przykład wyświetlić tylko urządzenia, które zostały zarejestrowane po określonej dacie.
-   Wprowadziliśmy ulepszenia dotyczące filtra używanego przez element **Data ostatniego zaewidencjonowania**.
-   Na liście urządzeń możesz teraz wyświetlić numery telefonów urządzeń będących własnością firmy.
Ponadto przy użyciu okienka filtru możesz wyszukiwać urządzenia według numeru telefonu.
 
Aby uzyskać więcej informacji na temat spisu urządzeń, zobacz [Jak wyświetlać spis urządzeń usługi Intune](device-inventory.md).

### <a name="conditional-access-support-for-macos-devices"></a>Obsługa dostępu warunkowego w przypadku urządzeń z systemem macOS 
<!-- 720172 --> Możesz teraz ustawić zasady dostępu warunkowego, które wymagają zarejestrowania urządzeń Mac w usłudze Intune i ich zgodności z zasadami zgodności urządzeń usługi Intune. Na przykład użytkownicy mogą pobrać aplikację Portal firmy w usłudze Intune dla systemu macOS i zarejestrować swoje urządzenia Mac w usłudze Intune. Usługa Intune ocenia, czy urządzenie Mac jest zgodne z wymaganiami, między innymi przez sprawdzenie numeru PIN, szyfrowania, wersji systemu operacyjnego i integralności systemu.

- Dowiedz się więcej o [obsłudze dostępu warunkowego w przypadku urządzeń z systemem macOS](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

### <a name="company-portal-app-for-macos-is-in-public-preview----1484796---"></a>Aplikacja Portal firmy dla urządzeń z systemem macOS jest dostępna w publicznej wersji zapoznawczej <!---1484796--->
Aplikacja Portal firmy dla urządzeń z systemem macOS jest teraz dostępna w ramach publicznej wersji zapoznawczej dostępu warunkowego pakietu Enterprise Mobility + Security. Ta wersja obsługuje system macOS w wersji 10.11 i nowszych. Pobierz ją ze strony [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal). 


### <a name="new-device-restriction-settings-for-windows-10"></a>Nowe ustawienia ograniczeń urządzenia z systemem Windows 10    
<!--1063965, 1308850  --> W tej wersji dodano nowe ustawienia [profilu ograniczeń urządzenia z systemem Windows 10](/intune/device-restrictions-windows-10) w następujących kategoriach:

-   Windows Defender SmartScreen
-   App Store

### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>Aktualizacje profilu urządzenia usługi Endpoint Protection dla systemu Windows 10 dla ustawień funkcji BitLocker
<!--1459533 -->    
W tej wersji wprowadziliśmy następujące ulepszenia dotyczące sposobu działania ustawień funkcji BitLocker w profilu urządzenia usługi Endpoint Protection dla systemu Windows 10:
 
W obszarze **Ustawienia funkcji BitLocker dla dysku systemu operacyjnego** wybranie wartości **Blokuj** dla ustawienia **Funkcja BitLocker z niezgodnym modułem TPM** w rzeczywistości zezwalało na używanie funkcji BitLocker. Ten błąd został rozwiązany i funkcja BitLocker jest blokowana, gdy zostanie wybrane odpowiednie ustawienie.
W obszarze **Ustawienia funkcji BitLocker dla dysku systemu operacyjnego** w przypadku ustawienia **Agent odzyskiwania danych oparty na certyfikatach** możesz teraz jawnie blokować agenta odzyskiwania danych opartego na certyfikatach. Jednak domyślnie agent nie jest blokowany.
W obszarze **Ustawienia stałych dysków danych w funkcji BitLocker** w przypadku ustawienia **Agent odzyskiwania danych**  możesz teraz jawnie blokować agenta odzyskiwania danych.
Aby uzyskać więcej informacji, zobacz [Ustawienia programu Endpoint Protection dla systemu Windows 10 i nowszych wersji](endpoint-protection-windows-10.md).


### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Nowe środowisko logowania dla użytkowników aplikacji Portal firmy w systemie Android i użytkowników zasady ochrony aplikacji <!-- 621669 -->
Użytkownicy końcowi mogą teraz przeglądać aplikacje, zarządzać urządzeniami i wyświetlać informacje kontaktowe dla działu IT przy użyciu aplikacji Portal firmy dla systemu Android bez rejestrowania urządzeń z systemem Android. Ponadto jeśli użytkownik końcowy używa aplikacji chronionej przez zasady usługi Intune App Protection i uruchamia Portal firmy dla systemu Android, nie otrzymuje już monitu o zarejestrowanie urządzenia.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Nowe ustawienie w aplikacji Portal firmy dla systemu Android umożliwiające przełączanie optymalizacji baterii <!--1405990-->
Strona **Ustawienia** w aplikacji Portal firmy dla systemu Android zawiera nowe ustawienie, które umożliwia użytkownikom proste wyłączanie optymalizacji baterii dla aplikacji Portal firmy i Microsoft Authenticator. Nazwa aplikacji wyświetlana w ustawieniu będzie różnić się w zależności od aplikacji, która zarządza kontem służbowym. Zalecamy, aby użytkownicy wyłączali optymalizację baterii w celu poprawy wydajności aplikacji służbowych, które synchronizują pocztę e-mail i dane. 

### <a name="multi-identity-support-for-onenote-for-ios---------1234281---"></a>Obsługa wielu tożsamości w programie OneNote dla systemu iOS      <!-- 1234281 -->
Użytkownicy końcowi mogą teraz używać w programie OneNote dla systemu iOS różnych kont (służbowych i osobistych). Zasady ochrony aplikacji można stosować do danych firmowych w notesach służbowych bez wpływu na notesy osobiste. Zasady mogą na przykład zezwalać użytkownikowi na wyszukiwanie informacji w notesie służbowym, ale uniemożliwią kopiowanie i wklejanie danych firmowych z notesu służbowego do notesu osobistego.
 
- Dowiedz się więcej o aplikacjach, które obsługują [ochronę aplikacji i wiele tożsamości](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) za pomocą usługi Intune.

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Nowe ustawienia umożliwiające zezwalanie na działanie aplikacji i blokowanie ich na urządzeniach z systemem Samsung Knox Standard
<!-- 1305423 822899-->  
W tej wersji dodajemy nowe [ustawienia ograniczeń urządzeń](device-restrictions-android.md) pozwalające określić następujące listy aplikacji:
 
- Aplikacje, które użytkownicy mogą instalować
- Aplikacje, których użytkownicy nie mogą uruchamiać
- Aplikacje ukryte przed użytkownikiem na urządzeniu
 
Możesz określić aplikacji przy użyciu adresu URL, nazwy pakietu lub zarządzanej przez Ciebie listy aplikacji.

### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Link do nowego opartego na aplikacji interfejsu użytkownika zasad dostępu warunkowego usługi Azure AD z usługi Intune
<!-- 1016201 --> Administratorzy IT mogą teraz ustawiać zasady dostępu warunkowego opartego na aplikacji za pomocą nowego interfejsu użytkownika zasad dostępu warunkowego w obciążeniu usługi Azure AD. Dostęp warunkowy oparty na aplikacji, który znajduje się w sekcji usługi Intune App Protection w witrynie Azure Portal, pozostanie w tym miejscu i będzie wymuszany równolegle. Wygodny link do nowego interfejsu użytkownika zasad dostępu warunkowego jest dostępny z poziomu obciążenia usługi Intune.

- Dowiedz się więcej o [dostępie warunkowym opartym na aplikacji w usłudze Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference).



## <a name="july-2017"></a>Lipiec 2017

### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Wprowadzanie ograniczeń rejestracji urządzeń z systemem Android lub iOS na podstawie wersji systemu operacyjnego <!--- 1333256,  1245463 --->
Usługa Intune obsługuje teraz ograniczanie rejestracji urządzeń z systemem Android lub iOS na podstawie numeru wersji systemu operacyjnego. W obszarze **Ograniczenie typu urządzenia** administrator IT może teraz ustawić konfigurację platformy w taki sposób, aby ograniczyć rejestrację, podając minimalną i maksymalną dopuszczalną wartość systemu operacyjnego. Wersje systemu operacyjnego Android muszą być określone jako wersja_główna.wersja_pomocnicza.kompilacja.wydanie, gdzie wersja_pomocnicza, kompilacja i wydanie są opcjonalne. Wersje systemu operacyjnego iOS muszą być określone jako wersja_główna.wersja_pomocnicza.kompilacja, gdzie wersja_pomocnicza i kompilacja są opcjonalne. Dowiedz się więcej o [ograniczeniach rejestracji urządzenia](enrollment-restrictions-set.md).

>[!NOTE]
>Nie ograniczaj rejestracji za pomocą programów rejestracji firmy Apple lub narzędzia Apple Configurator.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Ograniczanie rejestracji urządzeń osobistych z systemem Android, iOS lub macOS <!--- 1333272,  1333275, 1245709 --->
Usługa Intune może ograniczać rejestrację urządzenia osobistego, stosując białą listę numerów IMEI urządzeń firmowych. Ta funkcjonalność usługi Intune została teraz rozszerzona na systemy iOS, Android i macOS przy użyciu numerów seryjnych urządzeń. Przekazanie numerów seryjnych do usługi Intune pozwala wstępnie zadeklarować urządzenia jako firmowe. Ograniczenia rejestracji umożliwiają blokowanie urządzeń osobistych („Przynieś własne urządzenie” — BYOD), aby umożliwić rejestrację tylko dla urządzeń należących do firmy. Dowiedz się więcej o [ograniczeniach rejestracji urządzenia](enrollment-restrictions-set.md).

Aby zaimportować numery seryjne, przejdź do pozycji **Rejestrowanie urządzenia** > **Identyfikatory urządzeń firmowych** i kliknij pozycję **Dodaj**, a następnie przekaż plik CSV (bez nagłówka, dwie kolumny numeru seryjnego i szczegóły, takie jak numery IMEI).  Aby ograniczyć urządzenia osobiste, przejdź do lokalizacji **Rejestracja urządzeń**  >  **Ograniczenia rejestracji**. W obszarze **Ograniczenia typu urządzeń** wybierz pozycję **Domyślne**, a następnie wybierz pozycję **Konfiguracje platform**. Możesz wybrać pozycję **Zezwalaj** lub **Blokuj** dla urządzeń osobistych z systemem iOS, Android lub macOS. 


### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Nowa akcja urządzenia wymuszająca synchronizację urządzeń z usługą Intune <!-- 711369 -->
W tym wydaniu dodaliśmy nową akcję urządzenia, która wymusza natychmiastowe zaewidencjonowanie wybranego urządzenia w usłudze Intune. Zaewidencjonowane urządzenie natychmiast odbiera wszelkie przypisane do niego oczekujące akcje lub zasady.  Ta akcja ułatwia natychmiastowe weryfikowanie przypisanych zasad i rozwiązywanie dotyczących ich problemów bez konieczności czekania na następne zaplanowane ewidencjonowanie.
Aby uzyskać więcej informacji, zobacz [Synchronize device (Synchronizowanie urządzenia)](device-sync.md)

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Wymuszanie automatycznej instalacji najnowszej dostępnej aktualizacji oprogramowania na urządzeniach nadzorowanych z systemem iOS <!-- 777100 -->
W obszarze roboczym aktualizacji oprogramowania są dostępne nowe zasady, które umożliwiają wymuszanie automatycznej instalacji najnowszej dostępnej aktualizacji oprogramowania na urządzeniach nadzorowanych z systemem iOS. Aby uzyskać więcej informacji, zobacz [Configure iOS update policies (Konfigurowanie zasad aktualizacji systemu iOS)](/intune/software-updates-ios)

### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651-1172027---"></a>Check Point SandBlast Mobile — nowy partner usługi Mobile Threat Defense <!-- 954651, 1172027 -->
Dostęp urządzeń przenośnych do zasobów firmy można kontrolować z użyciem dostępu warunkowego opartego na ocenie ryzyka przeprowadzanej przez produkt Checkpoint SandBlast Mobile. Jest to rozwiązanie chroniące przed zagrożeniami bezpieczeństwa urządzenia przenośne zintegrowane z usługą Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Jak działa integracja z usługą Intune?
Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń z uruchomionym rozwiązaniem Checkpoint SandBlast Mobile. Zasady dostępu warunkowego usług EMS możesz skonfigurować w oparciu o ocenę ryzyka przeprowadzaną przez rozwiązanie Checkpoint SandBlast Mobile włączane przy użyciu zasad zgodności urządzeń usługi Intune. Możesz zezwalać na dostęp do zasobów firmowych lub blokować go niezgodnym urządzeniom w oparciu o wykryte zagrożenia.


### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business----748101---"></a>Wdrażanie aplikacji jako dostępnych w Sklepie Microsoft dla Firm <!-- 748101 -->
W tej wersji administratorzy mogą teraz przypisać Sklep Microsoft dla Firm jako dostępny. W przypadku ustawienia jako dostępny użytkownicy końcowi mogą zainstalować aplikację z aplikacji Portal firmy lub witryny internetowej bez przekierowania do sklepu Microsoft.

### <a name="ui-updates-to-the-company-portal-website---1313244-part-1--"></a>Aktualizacje interfejsu użytkownika witryny internetowej Portal firmy <!--1313244 part 1-->
Wprowadziliśmy kilka aktualizacji interfejsu użytkownika [witryny internetowej Portal firmy](https://portal.manage.microsoft.com) w celu ulepszenia środowiska użytkownika końcowego.

- __Ulepszenia kafelków aplikacji__ — ikony aplikacji będą teraz wyświetlane z automatycznie wygenerowanym tłem określanym na podstawie dominującego koloru ikony (jeśli można będzie go wykryć). O ile będzie to miało zastosowanie, to tło zastąpi szare obramowanie, które było wcześniej widoczne na kafelkach aplikacji.

    Witryna internetowa Portal firmy wyświetla w nadchodzącej wersji duże ikony, jeśli tylko to możliwe. Zalecamy, aby administratorzy IT podczas publikowania aplikacji korzystali z ikon o wysokiej rozdzielczości o rozmiarze co najmniej 120 x 120 pikseli. 

- __Zmiany nawigacji__ — elementy paska nawigacji zostały przeniesione do menu typu „hamburger” znajdującego się w lewym górnym rogu. Strona Kategorie została usunięta. Użytkownicy mogą teraz filtrować zawartość według kategorii podczas przeglądania.

- __Aktualizacje sekcji Polecane aplikacje__ — do witryny dodaliśmy dedykowaną stronę, na której użytkownicy mogą przeglądać aplikacje wybrane przez Ciebie do polecania. Dostosowaliśmy również interfejs użytkownika w sekcji Polecane na stronie głównej.

### <a name="ibooks-support-for-the-company-portal-website---1231841--"></a>Obsługa aplikacji iBooks w witrynie internetowej Portal firmy <!--1231841-->
Dodaliśmy dedykowaną stronę do witryny internetowej Portal firmy, która umożliwia użytkownikom przeglądanie i pobieranie plików iBooks. 


### <a name="additional-help-desk-troubleshooting-details------applies-to-1263399-1326964-1341642----"></a>Dodatkowe szczegóły rozwiązywania problemów dla działu pomocy technicznej <!---  Applies to 1263399, 1326964, 1341642 --->
W usłudze Intune zaktualizowano sposób wyświetlania procesu rozwiązywania problemów i uzupełniono informacje widoczne dla administratorów i personelu pomocy technicznej. Można teraz przeglądać tabelę **Przypisania**, która zawiera podsumowanie wszystkich przypisań dla użytkownika na podstawie członkostwa w grupie. Lista zawiera następujące pozycje:
- Aplikacje mobilne
- Zasady zgodności
- Profile konfiguracji
 
Ponadto tabela **Urządzenia** zawiera teraz kolumny **Typ dołączenia do usługi Azure AD** i **Zgodne z usługą Azure AD**. Aby uzyskać więcej informacji, zobacz [Help users troubleshoot problems (Pomaganie użytkownikom w rozwiązywaniu problemów)](help-desk-operators.md).



### <a name="intune-data-warehouse-public-preview"></a>Magazyn danych usługi Intune (publiczna wersja zapoznawcza)
Magazyn danych usługi Intune każdego dnia próbkuje dane, aby przedstawić widok historyczny Twojej dzierżawy. Możesz uzyskać dostęp do danych za pomocą pliku usługi Power BI (PBIX), linku usługi OData, która jest zgodna z wieloma narzędziami analitycznymi, lub interakcji z interfejsem API REST. Aby uzyskać więcej informacji, zobacz [Korzystanie z magazynu danych usługi Intune](reports-nav-create-intune-reports.md).


### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Tryb jasny i ciemny dostępne dla aplikacji Portal firmy dla systemu Windows 10 <!---676547--->
Użytkownicy końcowi będą mogli dostosować tryb kolorów aplikacji Portal firmy dla systemu Windows 10. Użytkownik będzie mógł wprowadzić zmiany w sekcji Ustawienia w aplikacji Portal firmy. Zmiana zostanie zastosowana po ponownym uruchomieniu aplikacji przez użytkownika. W przypadku systemu Windows 10 w wersji 1607 lub nowszej domyślnie będzie używany tryb aplikacji określony w ustawieniach systemowych. W przypadku systemu Windows 10 w wersji 1511 lub wcześniejszej domyślnie będzie używany jasny tryb aplikacji.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>Umożliwianie użytkownikom tagowania grupy urządzeń w aplikacji Portal firmy dla systemu Windows 10 <!---807046-->
Użytkownicy końcowi mogą teraz wybrać grupę, do której ma należeć ich urządzenie, przez otagowanie jej bezpośrednio z poziomu aplikacji Portal firmy dla systemu Windows 10.



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
W nowszej wersji planujemy dodać łatwiejszy sposób wybierania i przypisywania wbudowanych aplikacji z witryny Azure Portal.

### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Łatwiejsza instalacja aplikacji usługi Office 365 <!--- 1121362 --->
Nowy typ aplikacji usługi **Office 365 ProPlus** ułatwia przypisywanie aplikacji usługi Office 365 ProPlus 2016 do zarządzanych przez Ciebie urządzeń z najnowszą wersją systemu Windows 10. Ponadto jeśli masz licencje na programy Microsoft Project i Microsoft Visio, masz możliwość ich zainstalowania. Potrzebne aplikacje są ze sobą powiązane i wyświetlane jako jedna aplikacja na liście aplikacji w konsoli usługi Intune.
Aby uzyskać więcej informacji, zobacz [How to add Office 365 apps for Windows 10](apps-add-office365.md) (Jak dodawać aplikacje usługi Office 365 dla systemu Windows 10).


### <a name="support-for-offline-apps-from-the-microsoft-store-for-business-----777044----"></a>Obsługa aplikacji offline ze Sklepu Microsoft dla Firm <!--- 777044 --->
Aplikacje offline zakupione w Sklepie Microsoft dla Firm będą teraz synchronizowane z witryną Azure Portal. Następnie można wdrożyć te aplikacje w grupach urządzeń lub w grupach użytkowników. Aplikacje offline są instalowane przez usługę Intune, a nie przez sklep.

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
-  Przeglądarka Microsoft Edge

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
Firma Microsoft informuje o ogólnej dostępności nowej usługi Intune w konsoli administracyjnej witryny Azure Portal i konsoli administracyjnej dostępu warunkowego. Za pomocą usługi Intune w witrynie Azure Portal można teraz zarządzać wszystkimi możliwościami MAM i MDM usługi Intune w jednym skonsolidowanym środowisku administratora oraz korzystać z funkcji grupowania i określania odbiorców docelowych w usłudze Azure AD. Dostęp warunkowy na platformie Azure oferuje zaawansowane możliwości w usługach Azure AD i Intune w jednej ujednoliconej konsoli. W środowisku administracyjnym przeniesienie na platformę Azure umożliwia korzystanie z nowoczesnych przeglądarek.

Usługa Intune jest teraz widoczna bez etykiety **wersji zapoznawczej** w witrynie Azure Portal pod adresem portal.azure.com.

Obecnie istniejący klienci nie muszą podejmować żadnych działań, chyba że użytkownik otrzyma jeden z serii komunikatów z centrum wiadomości z żądaniem podjęcia działania, dzięki któremu będziemy mogli migrować jego grupy. Użytkownik mógł również otrzymać powiadomienie z centrum wiadomości informujące o tym, że migracja trwa dłużej z powodu błędów występujących po naszej stronie. Firma Microsoft nadal usilnie pracuje nad tym, by przeprowadzić migrację wszystkich klientów, na których to miało wpływ.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>Ulepszone kafelki aplikacji w Portalu firmy dla systemu iOS
Zaktualizowaliśmy wygląd kafelków aplikacji na stronie głównej, aby odpowiadał on kolorowi ustawionemu dla Portalu firmy. Aby uzyskać więcej informacji, zobacz temat [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Selektor konta już dostępny w aplikacji Portal firmy dla systemu iOS
Dla użytkowników urządzeń z systemem iOS nasz nowy selektor konta może być widoczny po zalogowaniu się do Portalu firmy, jeśli użyją konta służbowego do zalogowania się do innych aplikacji firmy Microsoft. Aby uzyskać więcej informacji, zobacz temat [Co nowego w interfejsie użytkownika aplikacji](whats-new-app-ui.md).

## <a name="may-2017"></a>Maj 2017 r.

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Zmiana urzędu MDM bez wyrejestrowania zarządzanych urządzeń <!--1103950-->
Teraz będzie można zmienić urząd MDM bez konieczności kontaktowania się z działem pomocy technicznej firmy Microsoft oraz wyrejestrowywania i ponownego rejestrowania istniejących urządzeń zarządzanych. W konsoli programu Configuration Manager można [zmienić urząd MDM](/sccm/mdm/deploy-use/change-mdm-authority), wybierając opcję Ustaw Menedżera konfiguracji (hybrydowe) zamiast opcji Microsoft Intune (autonomiczne) lub odwrotnie.


### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Ulepszone powiadomienia dotyczące numerów PIN wymaganych do uruchomiania urządzeń z systemem Samsung Knox <!--1087143-->
W przypadku gdy użytkownicy końcowi muszą skonfigurować numer PIN wpisywany po uruchomieniu urządzenia z systemem Samsung Knox w celu zapewnienia zgodności z szyfrowaniem, dotknięcie wyświetlonego powiadomienia umożliwi przejście bezpośrednio do odpowiedniego ustawienia.  Wcześniej dotknięcie powiadomienia na urządzeniu użytkownika końcowego powodowało przejście do ekranu zmiany hasła.

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
Niektóre aplikacje dla systemu Android ze sklepu obsługują opcje konfiguracji zarządzanych, które umożliwiają administratorowi IT kontrolowanie działania aplikacji w profilu służbowym. Przy użyciu usługi Intune można teraz wyświetlić konfiguracje obsługiwane przez aplikację i skonfigurować je w witrynie Azure Portal za pomocą projektanta konfiguracji lub edytora JSON. Aby uzyskać więcej informacji, zobacz artykuł [Use app configurations for Android for Work](app-configuration-policies-use-android.md) (Używanie konfiguracji aplikacji dla programu Android for Work).

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
Podczas tworzenia profilu certyfikatu SCEP dla pozycji <strong>Format nazwy podmiotu</strong>, opcja <strong>Niestandardowy</strong> jest dostępna dla urządzeń z systemami iOS, Android i Windows. Przed tą aktualizacją pole <strong>Niestandardowy</strong> było dostępne tylko dla urządzeń z systemem iOS. Aby uzyskać więcej informacji, zobacz [Tworzenie profilu certyfikatu protokołu SCEP](certificates-scep-configure.md#create-a-scep-certificate-profile).

Podczas tworzenia profilu certyfikatu PKCS dla pozycji **Alternatywna nazwa podmiotu** dostępna jest opcja **Atrybut niestandardowy usługi Azure AD**. Opcja **Dział** jest dostępna po wybraniu opcji **Atrybut niestandardowy usługi Azure AD**. Aby uzyskać więcej informacji, zobacz [Tworzenie profilu certyfikatu protokołu PKCS](certficates-pfx-configure.md#create-a-pkcs-certificate-profile).

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

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Zarządzanie wieloma użytkownikami na urządzeniach z systemem Samsung Knox Standard <!-- 971988 -->
Urządzenia z systemem Samsung Knox Standard obsługują teraz funkcję [zarządzania wieloma użytkownikami](android-enroll.md) przez usługę Intune. Oznacza to, że użytkownicy końcowi mogą zalogować się na urządzeniu przy użyciu poświadczeń usługi Azure Active Directory lub wylogować się z niego, a urządzenie jest zarządzane centralnie niezależnie od tego, czy jest używane.  Po zalogowaniu się użytkownicy końcowi otrzymują dostęp do aplikacji oraz zostają wobec nich zastosowane zasady. Gdy użytkownicy się wylogują, wszystkie dane aplikacji są usuwane.

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
Na kontach usługi Intune utworzonych po styczniu 2017 roku włączono bezpośredni dostęp do scenariuszy rejestracji firmy Apple przy użyciu obciążenia Rejestruj urządzenia w witrynie Azure Portal. Wcześniej podgląd rejestracji firmy Apple był dostępny tylko z poziomu linków w witrynie Azure Portal. Konta usługi Intune utworzone przed styczniem 2017 będą wymagać przeprowadzenia jednorazowej migracji, zanim funkcje te będą dostępne w systemie Azure. Harmonogram migracji nie został jeszcze ogłoszony, ale szczegółowe informacje zostaną udostępnione najszybciej, jak będzie to możliwe. Zdecydowanie zalecamy utworzenie konta w wersji próbnej w celu przetestowania nowego środowiska pracy w przypadku, gdy istniejące konto nie ma dostępu do podglądu.


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
