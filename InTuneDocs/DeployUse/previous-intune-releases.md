---
# required metadata

title: Poprzednie wersje | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Poprzednie wersje usługi Intune
## Marzec 2016
### Co nowego w wersji z 29 marca 2016 r.
Z wyjątkiem aktualizacji ogólnych zasad konfiguracji systemu Windows 10, wszystkie funkcje w wersji opublikowanej 29 marca 2016 r. są również obsługiwane dla klientów hybrydowych (program Configuration Manager zintegrowany z usługą Intune). Hybrydowa obsługa dla aktualizacji ogólnych zasad konfiguracji systemu Windows 10 będzie dostępna wkrótce. Należy pamiętać, że niektóre z tych funkcji mogą wymagać najnowszej wersji programu Configuration Manager.

### Zarządzanie aplikacjami
- **Kontrolki zarządzania aplikacjami mobilnymi zapobiegające synchronizacji kontaktów programu Outlook (iOS).** Dostępne jest nowe ustawienie do zarządzania aplikacjami mobilnymi bez rejestracji urządzeń. To ustawienie umożliwia zapobieganie synchronizacji przez aplikację kontaktów z natywną książką adresową na urządzeniach z systemem iOS. Po włączeniu tego ustawienia aplikacja nie będzie w stanie zapisywać kontaktów w natywnej książce adresowej. Po wyłączeniu tego ustawienia aplikacja będzie w stanie zapisywać kontakty w natywnej książce adresowej. Po selektywnym wyczyszczeniu urządzenia zostaną usunięte wszystkie kontakty zapisane wcześniej w natywnej książce adresowej. To nowe ustawienie jest obsługiwane przez aplikację Outlook na urządzeniach z systemem iOS. Aby uzyskać więcej informacji dotyczących tego i innych ustawień, zobacz [Tworzenie i wdrażanie zasad MAM](https://technet.microsoft.com/en-us/library/dn292747.aspx).

### Kontrola dostępu
- **Usługa Skype dla firm Online obsługuje dostęp warunkowy.** Możesz określić zasady dostępu warunkowego dla usługi Skype dla firm Online, co umożliwia dostęp do niej tylko przez zarządzane i zgodne urządzenia z systemem iOS lub Android. Użytkownicy końcowi, którzy podejmą próbę zalogowania się do aplikacji mobilnej Skype dla firm w systemie iOS lub Android, zostaną poproszeni o rejestrację w usłudze Intune oraz rozwiązanie wszystkich problemów z niezgodnością przed zakończeniem logowania. Aby uzyskać szczegółowe informacje, zobacz [Zarządzanie dostępem do usługi Skype dla firm Online](https://technet.microsoft.com/en-us/library/mt695297.aspx).

### Zarządzanie urządzeniami
- **Obsługa usługi Intune dla systemu iOS 9.3.** W poniedziałek 21 marca firma Apple ogłosiła dostępność systemu iOS 9.3. Firma Microsoft intensywnie pracowała nad zapewnieniem zgodności usługi Microsoft Intune z najnowszym systemem operacyjnym firmy Apple dla urządzeń przenośnych. [Z przyjemnością ogłaszamy, że usługa Intune obsługuje już zarządzanie urządzeniami z systemem iOS 9.3](https://blogs.technet.microsoft.com/microsoftintune/2016/03/23/microsoft-intune-provides-support-for-ios-9-3/).

  Wszystkie obecnie dostępne funkcje usługi Intune do zarządzania urządzeniami z systemem iOS będą nadal działać bezproblemowo po uaktualnieniu urządzeń do systemu iOS 9.3 przez użytkowników. Ponadto system iOS 9.3 jest teraz obsługiwany również dla klientów hybrydowych (program Configuration Manager zintegrowany z usługą Intune).

- **Ogólne zasady konfiguracji systemu Windows 10 zawierają teraz ustawienia służące do zarządzania usługą Windows Defender na zarejestrowanych komputerach z systemem Windows 10.** Aby uzyskać więcej informacji, zobacz [Ustawienia zasad konfiguracji systemu Windows 10 w usłudze Microsoft Intune](https://technet.microsoft.com/en-us/library/mt404697.aspx).


### Portal firmy

- **Pakiety aplikacji systemu Windows dostępne bezpośrednio z witryny sieci Web portalu firmy.** Użytkownicy komputerów z systemami Windows 8, Windows 8.1 i Windows RT mogą teraz instalować pakiety aplikacji systemu Windows (z rozszerzeniem appx) bezpośrednio z witryny Portalu firmy. Poprzednio konieczne było wdrożenie aplikacji lub użytkownicy musieli instalować aplikację Portal firmy na urządzeniach w celu instalacji aplikacji.

- **Użytkownicy mogą zdalnie blokować swoje urządzenie z poziomu witryny sieci Web portalu firmy.** Do witryny sieci Web Portalu firmy dodano opcję blokady zdalnej, która umożliwia użytkownikom zdalne blokowanie urządzenia z Portalu w przypadku jego utraty lub kradzieży. Zobacz [instrukcje dla użytkowników końcowych](https://technet.microsoft.com/library/mt590895.aspx/?wt.mc_id=ui#BKMK_iwp_remote_lock). Poniższa tabela zawiera platformy obsługiwane przez funkcję blokady zdalnej autonomicznej usługi Intune oraz usługi Intune z programem Configuration Manager.

|Platforma | Szczegóły dotyczące obsługi|
|---------|----------------|
|Android |Obsługiwane|
|iOS |Obsługiwane|
|Windows 10 Mobile |Obsługiwane tylko wtedy, gdy na telefonie ustawiono kod dostępu|
|Windows 10 Desktop |Nieobsługiwane|
|Windows Phone 8,1 |Obsługiwane tylko wtedy, gdy na telefonie ustawiono kod dostępu|
|Windows Phone 8.0 |Nieobsługiwane|
|Komputer (Windows 8.0 i starsze) |Nieobsługiwane|
|Komputer (Windows 8.1) |Nieobsługiwane|

### Co nowego w wersji z 10 marca 2016 r.

### Zarządzanie aplikacjami

- **W systemie iOS warto korzystać z funkcji „Otwórz w” dla urządzeń, które są zarejestrowane w rozwiązaniu MDM innej firmy**
W celu korzystania w systemie iOS z funkcji „Otwórz w” możesz używać dowolnego dostawcy rozwiązania do zarządzania urządzeniami przenośnymi (MDM, ang. Mobile Device Management) innej firmy. Możesz konfigurować ograniczenia w ustawieniach profilu konfiguracji i wdrażać aplikacje przy użyciu funkcji [zarządzania przesyłaniem danych między aplikacjami systemu iOS](manage-data-transfer-between-ios-apps-with-microsoft-intune.md).

     Takie podejście charakteryzuje się dwoma korzyściami:

     1. Użytkownicy muszą logować się, korzystając z poświadczeń konta służbowego, zanim uzyskają dostęp do dowolnych danych korporacyjnych z usług w chmurze albo do innych aplikacji. Takie rozwiązanie zapewnia przestrzeganie zasad zarządzania aplikacjami mobilnymi (MAM, ang. Mobile App Management) podczas uzyskiwania dostępu do danych.

     2. Zarządzane profile poczty e-mail i inne aplikacje zarządzane wdrożone za pośrednictwem rozwiązania MDM innej firmy mogą udostępniać pliki i dane aplikacjom, które działają zgodnie z zasadami MAM usługi Intune.

- **Zarządzanie aplikacją Microsoft Outlook przy użyciu zasad zarządzania aplikacjami mobilnymi na urządzeniach, które nie są zarejestrowane w usłudze Intune**
Możesz teraz zarządzać aplikacją Microsoft Outlook na urządzeniach, które nie są zarejestrowane w usłudze Intune, korzystając z zasad zarządzania aplikacjami mobilnymi z usługi Intune. Zaktualizowana aplikacja Microsoft Outlook obsługująca zasady zarządzania aplikacjami mobilnymi jest dostępna dla urządzeń z systemem [iOS](https://itunes.apple.com/us/app/microsoft-outlook-email-calendar/id951937596?mt=8) oraz urządzeń z systemem [Android](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook). W celu tworzenia zasad zarządzania aplikacjami mobilnymi postępuj zgodnie z instrukcjami w temacie [Tworzenie i wdrażanie zasad zarządzania aplikacjami mobilnymi](https://technet.microsoft.com/library/mt627829.aspx).  


- **Zasady konfiguracji aplikacji mobilnych zapewniają większą elastyczność i możliwość określania szczegółów użytkowników dla aplikacji systemu iOS**
Możesz podawać ustawienia użytkowników, których może potrzebować aplikacja systemu iOS, gdy zostanie otwarta. Na przykład można podać port sieci lub nazwę użytkownika. Aby uzyskać więcej informacji, zobacz [Konfigurowanie aplikacji systemu iOS przy użyciu zasad konfiguracji aplikacji mobilnych w usłudze Microsoft Intune](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md).


- **Wdrażanie w przedsiębiorstwie programu Adobe Reader dla usługi Microsoft Intune na urządzeniach zarządzanych przez usługę Intune w systemie iOS**
Teraz można zarządzać aplikacją Adobe Reader dla systemu iOS na zarejestrowanych urządzeniach, stosując zasady zarządzania aplikacjami mobilnymi usługi Intune.

- **Zapewnienie, że wdrożone klipy internetowe będą otwierane w programie Managed Browser**
Możesz wdrażać klipy internetowe przeznaczone dla konkretnych grup odbiorców, które można otwierać tylko przy użyciu programu Managed Browser na urządzeniach z systemem iOS i z systemem Android. Na przykład wdrażasz linki do zasobów firmowych za pośrednictwem Portalu firmy, a gdy użytkownicy przejdą do tych linków, zostaną one otwarte bezpośrednio w programie Managed Browser, gdzie mogą być chronione przez zasady zarządzania aplikacjami mobilnymi. Aby uzyskać szczegółowe informacje, zobacz [Wdrażanie aplikacji](deploy-apps.md).


- **Wyszukiwanie i dystrybucja aplikacji ze Sklepu Windows dla firm oraz zarządzanie nimi dla urządzeń z systemem Windows 10 z konsoli administratora usługi Intune**
Usługa Intune obsługuje Sklep Windows dla firm, aby ułatwiać znajdowanie aplikacji i zarządzanie nimi, a także przeprowadzanie dystrybucji aplikacji na zarządzanych przez Ciebie urządzeniach z systemem Windows 10. Sklep Windows dla firm umożliwia zarządzanie procesem wdrażania i monitorowania tych aplikacji z konsoli administratora usługi Intune — tej samej konsoli, która służy do zarządzania innymi aplikacjami. W szczególności Sklep Windows dla firm zarządza zawartością i licencjonowaniem „aplikacji licencjonowanych online”. Aby uzyskać szczegółowe informacje, zobacz [Zarządzanie aplikacjami zakupionymi w Sklepie Windows dla firm](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md).


### Zarządzanie urządzeniami
- **Dystrybucja certyfikatów PFX dla urządzeń z systemem iOS**
Administratorzy usługi Intune mogą tworzyć i wdrażać certyfikaty PFX systemu iOS dla sieci Wi-Fi, poczty e-mail i uwierzytelniania sieci VPN na urządzeniach z systemem iOS. Ta funkcja jest już dostępna dla urządzeń z systemami Android i Windows 10. Szczegółowe informacje zawiera temat [Zapewnianie dostępu do zasobów firmy przy użyciu profilów certyfikatów](secure-resource-access-with-certificate-profiles.md).


- **Stosowanie aplikacji i zasad do różnych grup urządzeń w oparciu o wybór kategorii użytkownika**
Administratorzy usługi Intune mogą definiować niestandardowe kategorie urządzeń dla użytkowników, które można wybierać podczas rejestracji. Na przykład administratorzy mogą wymagać, aby użytkownicy określali, czy rejestrują urządzenie, którego przeznaczenie to „Kasa”, „Samochód dostawczy” czy „Pomieszczenie magazynowe”. Wybór kategorii spowoduje, że urządzenie stanie się elementem grupy urządzeń usługi Intune, z której można korzystać w celu wdrażania różnych aplikacji i zasad do zarejestrowanych urządzeń. Aby uzyskać szczegółowe informacje, zobacz temat [Kategoryzowanie urządzeń za pomocą mapowania grup urządzeń](categorize-devices-with-device-group-mapping-in-microsoft-intune.md).

### Zmiany i aktualizacje Portalu firmy oferowanego przez firmę Microsoft
W Portalu firmy w tej wersji wprowadzono następujące zmiany:

**Aplikacja Portal firmy dla systemu Android**

* Gdy użytkownicy uruchomią aplikację, która jest zarządzana przez zarządzanie aplikacjami mobilnymi, zobaczą komunikat z informacją, że aplikacja jest zarządzana przez ich firmę. W tym komunikacie można teraz wybrać link „Dowiedz się więcej”, aby uzyskać [więcej informacji](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_use_mgd_apps) o tym, co oznacza określenie „aplikacje zarządzane”. Można również nacisnąć polecenie „Nie pokazuj ponownie”, aby komunikat nie był już wyświetlany w trakcie uruchamiania aplikacji.
* Zostały dodane nowe ekrany, które prowadzą użytkowników przez proces rejestracji i udostępniają więcej informacji na temat tego, dlaczego użytkownicy powinni się rejestrować i tego, co jest i nie jest wyświetlane na zarejestrowanych urządzeniach administratorów IT. Szczegółowe informacje zawierają [instrukcje dotyczące rejestrowania](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc).
* W aplikacji Portal firmy są teraz wyświetlane komunikaty o błędach rejestracji. Wcześniej te komunikaty pojawiały się w witrynie Portal firmy. Wprowadzenie tej zmiany oznacza, że wszystkie komunikaty o błędach pojawiają się teraz tylko w jednym miejscu zamiast w kilku.


**Aplikacja Portal firmy dla systemu iOS**
* Gdy użytkownicy uruchomią aplikację, która jest zarządzana przez zarządzanie aplikacjami mobilnymi, zobaczą komunikat z informacją, że aplikacja jest zarządzana przez ich firmę. W tym komunikacie można teraz wybrać link „Dowiedz się więcej”, aby uzyskać [więcej informacji](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_use_mgd_apps) o tym, co oznacza określenie „aplikacje zarządzane”. Można również nacisnąć polecenie „Nie pokazuj ponownie”, aby komunikat nie był już wyświetlany w trakcie uruchamiania aplikacji.
* Zostały dodane nowe ekrany, które prowadzą użytkowników przez proces rejestracji i udostępniają więcej informacji na temat tego, dlaczego użytkownicy powinni się rejestrować i tego, co jest i nie jest wyświetlane na zarejestrowanych urządzeniach administratorów IT. Szczegółowe informacje zawierają [instrukcje dotyczące rejestrowania](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device).
* W aplikacji Portal firmy są teraz wyświetlane komunikaty o błędach rejestracji. Wcześniej te komunikaty pojawiały się w witrynie Portal firmy. Wprowadzenie tej zmiany oznacza, że wszystkie komunikaty o błędach pojawiają się teraz tylko w jednym miejscu zamiast w kilku.




## Luty 2016
### Zmiany i aktualizacje Portalu firmy oferowanego przez firmę Microsoft

W Portalu firmy w tej wersji wprowadzono następujące zmiany:

#### Aplikacja Portal firmy dla systemu Android
- Zostały dodane nowe ekrany, które prowadzą użytkowników przez proces rejestracji i udostępniają więcej informacji na temat tego, dlaczego użytkownicy powinni się rejestrować i tego, co jest i nie jest wyświetlane na zarejestrowanych urządzeniach administratorów IT. Szczegółowe informacje zawierają [instrukcje dotyczące rejestrowania](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc).
- W aplikacji Portal firmy są teraz wyświetlane komunikaty o błędach rejestracji. Wcześniej te komunikaty pojawiały się w witrynie Portal firmy. Wprowadzenie tej zmiany oznacza, że wszystkie komunikaty o błędach pojawiają się teraz tylko w jednym miejscu zamiast w kilku.

#### Aplikacja Portal firmy dla systemu iOS
 - Zostały dodane nowe ekrany, które prowadzą użytkowników przez proces rejestracji i udostępniają więcej informacji na temat tego, dlaczego użytkownicy powinni się rejestrować i tego, co jest i nie jest wyświetlane na zarejestrowanych urządzeniach administratorów IT. Szczegółowe informacje zawierają [instrukcje dotyczące rejestrowania](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device).

 - W aplikacji Portal firmy są teraz wyświetlane komunikaty o błędach rejestracji. Wcześniej te komunikaty pojawiały się w witrynie Portal firmy. Wprowadzenie tej zmiany oznacza, że wszystkie komunikaty o błędach pojawiają się teraz tylko w jednym miejscu zamiast w kilku.


## Styczeń 2016

### Korzystanie z zalet funkcji systemu Windows 10
* **Dostęp warunkowy i usługa zaświadczania o kondycji**
Administratorzy usługi Intune mogą teraz wyświetlać stan usługi zaświadczania o kondycji systemu Windows 10 w konsoli administracyjnej usługi Intune. Zaświadczenie o kondycji urządzenia umożliwia administratorowi upewnienie się, że komputery klienckie dysponują godnymi zaufania konfiguracjami systemu BIOS, modułu TPM i oprogramowania rozruchowego. W celu obsługi zaświadczania o kondycji na urządzeniach klienckich musi działać system Windows 10 z włączonym modułem TPM 2. Zaświadczenie o kondycji urządzeń zawiera liczbę urządzeń obsługujących następujące funkcje:
    * Usługa wczesnej ochrony przed złośliwym kodem
    * Funkcja BitLocker
    * Bezpieczny rozruch
    * Integralność kodu

    Więcej szczegółów na temat ustawień dotyczących kondycji urządzeń, zebranych punktów danych i raportu zaświadczającego o kondycji zawiera temat [Wprowadzenie do zasad zgodności urządzeń w usłudze Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md). W temacie [Szczegóły usługi HAS](https://msdn.microsoft.com/en-us/library/dn934876.aspx) ta usługa została opisana szczegółowo.

* **Zarządzanie zasadami i certyfikatem usługi Windows 10 Passport dla miejsca pracy**
Usługa Intune [umożliwia integrację z usługą Microsoft Passport dla miejsca pracy](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md), czyli alternatywną metodą logowania dla systemu Windows 10 korzystającą z usługi Active Directory lub konta usługi Azure Active Directory w celu zastąpienia hasła, karty inteligentnej lub wirtualnej karty inteligentnej. Usługa Passport pozwala używać do logowania gestu użytkownika zamiast hasła. Gestem użytkownika może być prosty numer PIN, uwierzytelnianie biometryczne, takie jak Windows Hello, lub urządzenie zewnętrzne, np. czytnik linii papilarnych.

* **Sieć VPN dla określonych aplikacji**
Możesz wybierać aplikacje, które będą automatycznie łączyć się z siecią firmową za pośrednictwem połączenia VPN. Utwórz listę aplikacji podczas konfigurowania profilu sieci VPN zgodnie z opisem w temacie „Pomaganie użytkownikom w nawiązywaniu połączenia z siecią firmową za pomocą profilów sieci VPN w usłudze Microsoft Intune”.

* **Obsługa pełnego czyszczenia w systemie Windows 10**
Obecnie można przeprowadzić pełne zdalne czyszczenie danych urządzeń komputerowych z systemem Windows 10 zarejestrowanych w usłudze Intune, korzystając z konsoli administracyjnej usługi Intune. Pełne czyszczenie danych systemu Windows 10 powoduje przywrócenie fabrycznych ustawień urządzenia.


### Aktualizacja programu zakupów zbiorczych VPP (ang. Volume Purchase Program) firmy Apple
Usługa Intune ułatwia [zarządzanie aplikacjami zakupionymi za pośrednictwem programu Apple Volume Purchase Program (VPP) dla firm](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md). Dotyczy to synchronizowania informacji o licencjach między firmą Apple i usługą Intune, a także śledzenia liczby wdrożonych kopii poszczególnych aplikacji.

### Korzystanie z numerów IMEI w celu identyfikowania urządzeń firmowych
Możesz teraz [importować międzynarodowe numery identyfikujące urządzenia przenośne (IMEI, International Mobile Equipment Identity)](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) dla platform urządzeń przenośnych, które mają numer IMEI, co ułatwia identyfikację firmowych urządzeń przenośnych. Zarejestrowane w usłudze Intune urządzenia z numerami IMEI oznakowane jako firmowe, co jest użyteczne w przypadku stosowania strategii innych niż względem urządzeń prywatnych.

### Więcej aplikacji jest teraz zgodnych z zasadami zarządzania aplikacjami mobilnymi usługi Intune
Dodatkowe aplikacje od partnerów firmy Microsoft są teraz zgodne z zasadami zarządzania aplikacjami mobilnymi (MAM) usługi Intune (dla urządzeń zarządzanych przez usługę Intune):
* Box for EMM (od firmy Box Inc) — tylko dla urządzeń z systemem iOS
* Adobe Reader (firmy Adobe) — tylko dla urządzeń z systemem Android
* Foxit PDF Reader (firmy Foxit Corporation) — dla urządzeń z systemem iOS lub Android


### Obsługa programu IE9 kończy się w styczniu
Począwszy od lutego 2016 roku program Internet Explorer 9 nie będzie już obsługiwany jako oficjalna przeglądarka do uzyskiwania dostępu do witryny sieci Web portalu firmy w usłudze Microsoft Intune, portalu konta usługi Intune i konsoli administracyjnej usługi Intune. Należy przeprowadzić migrację do programu Internet Explorer 10 lub nowszego.

## Grudzień 2015
### Zmiany i aktualizacje Portalu firmy oferowanego przez firmę Microsoft
W Portalu firmy w tej wersji wprowadzono następujące zmiany:

**Aplikacja Portal firmy dla systemu Android**

Następujące zmiany wprowadzono w celu zapewnienia zgodności z nowymi wymaganiami firmy Google. Na urządzeniach z systemem Android w wersji 6.0 lub nowszym zostaną wyświetlone dwa następujące komunikaty:
* Zezwolić aplikacji Portal firmy na połączenia telefoniczne i zarządzanie nimi?
* Zezwolić aplikacji Portal firmy na dostęp do zdjęć, multimediów i plików na Twoim urządzeniu?

Następująca tabela zawiera szczegółowe informacje dotyczące tych dwóch komunikatów.



Tekst komunikatu  |Zezwolić aplikacji Portal firmy na połączenia telefoniczne i zarządzanie nimi?  
---------|---------
Znaczenie komunikatu     |  Umożliwia wysłanie numeru telefonu i kodu IMEI urządzenia użytkownika do usługi Intune, gdzie są następnie wyświetlane w konsoli administracyjnej na stronie Sprzęt.   </br></br>**UWAGA: Aplikacja Portal firmy nigdy nie wykonuje połączeń telefonicznych ani nie zarządza nimi.** Tekst komunikatu jest kontrolowany przez firmę Google i nie można go zmienić. </br></br>Aby wyświetlić stronę **Sprzęt**, wybierz pozycję **Grupy** > **Wszystkie urządzenia przenośne** > **Urządzenia**. Wybierz urządzenie użytkownika, a następnie wybierz pozycję **Wyświetl właściwości** > **Sprzęt**.    
Gdzie i kiedy pojawi się komunikat  | Komunikat jest wyświetlany, gdy użytkownik zaloguje się do aplikacji Portal firmy po raz pierwszy w celu rozpoczęcia rejestrowania urządzenia.|         
Co się stanie, gdy użytkownik zezwoli na dostęp  |  Numer telefonu i kod IMEI urządzenia będą wyświetlane na stronie Sprzęt w konsoli administracyjnej. |         
Co się stanie, gdy użytkownik nie zezwoli na dostęp     | Może nadal używać aplikacji Portal firmy i zarejestrować urządzenie, lecz pola numeru telefonu i kodu IMEI urządzenia użytkownika na stronie Sprzęt konsoli administracyjnej będą puste.       </br></br> Podczas drugiego logowania użytkownika do aplikacji Portal firmy po odmowie dostępu w komunikacie zostanie wyświetlone pole wyboru **Nigdy nie pytaj ponownie**. Jego zaznaczenie spowoduje, że komunikat nigdy nie zostanie wyświetlony ponownie.</br></br>Jeśli użytkownik zezwoli na dostęp, lecz potem go odmówi, komunikat zostanie wyświetlony podczas następnego logowania użytkownika do aplikacji Portal firmy po rejestracji.</br></br>Jeśli później użytkownik zdecyduje się zezwolić na dostęp, może wybrać pozycję **Ustawienia** > **Aplikacje** > **Portal firmy** > **Uprawnienia** > **Telefon** i włączyć uprawnienie.
Więcej informacji     |  Dla użytkowników: [Logowanie do aplikacji Portal firmy](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_signin_cp)  </br></br>Dla profesjonalistów IT: informacje w poniższej tabeli znajdują się również w sekcji [Pomaganie użytkownikom w zrozumieniu komunikatów aplikacji Portal firmy](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   

Tekst komunikatu  |Zezwolić aplikacji Portal firmy na dostęp do zdjęć, multimediów i plików na Twoim urządzeniu?  
---------|---------
Znaczenie komunikatu     |  Umożliwia urządzeniu zapisywanie dzienników danych na karcie SD urządzenia, co umożliwia przenoszenie dzienników przy użyciu kabla USB.   </br></br>**UWAGA: Aplikacja Portal firmy nigdy nie uzyskuje dostępu do zdjęć, multimediów ani plików użytkownika.** Tekst komunikatu jest kontrolowany przez firmę Google i nie można go zmienić.     
Gdzie i kiedy pojawi się komunikat  | Komunikat jest wyświetlany, gdy użytkownik naciśnie polecenie **Wyślij dane** w celu wysłania dzienników danych do administratora IT.|         
Co się stanie, gdy użytkownik zezwoli na dostęp  |  Dzienniki będą kopiowane na kartę SD. |         
Co się stanie, gdy użytkownik nie zezwoli na dostęp     | Nadal może wysyłać dzienniki danych, ale dzienniki nie będą kopiowane na kartę SD urządzenia.       </br></br> Podczas drugiego logowania użytkownika do aplikacji Portal firmy po odmowie dostępu w komunikacie zostanie wyświetlone pole wyboru **Nigdy nie pytaj ponownie**. Jego zaznaczenie spowoduje, że komunikat nigdy nie zostanie wyświetlony ponownie.</br></br>Jeśli użytkownik zezwoli na dostęp, lecz potem go odmówi, komunikat zostanie wyświetlony podczas następnej próby wysłania dzienników przez użytkownika.</br></br>Jeśli później użytkownik zdecyduje się zezwolić na dostęp, może wybrać pozycję **Ustawienia** > **Aplikacje** > **Portal firmy** > **Uprawnienia** > **Pamięć** i włączyć uprawnienie.
Więcej informacji     |  Dla użytkowników: [wysyłanie diagnostycznych dzienników danych do administratora IT przy użyciu poczty e-mail](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_send_diag_logs)  </br></br>Dla profesjonalistów IT: informacje w poniższej tabeli znajdują się również w sekcji [Pomaganie użytkownikom w zrozumieniu komunikatów aplikacji Portal firmy](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   


**Aplikacja Portal firmy dla systemu iOS**
* Użytkownicy mogą teraz używać programu Microsoft Outlook lub innych aplikacji do obsługi poczty e-mail na potrzeby wysyłania dzienników diagnostycznych do administratora IT. Wcześniej można było używać tylko aplikacji natywnej.
* Udoskonalono obsługę programu Device Enrollment Program (DEP) firmy Apple i urządzeń rejestrowanych przez firmę. Aby uzyskać szczegółowe informacje, zobacz [Prośba o identyfikację urządzenia przy próbie jego zarejestrowania](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_id_your_device).
* Lista zarejestrowanych urządzeń użytkownika zawiera zielony znacznik obok urządzenia, które jest aktualnie używane przez użytkownika. Przed dodaniem tego znacznika użytkownik nie mógł stwierdzić, którego urządzenia używa.

**Aplikacja Portal firmy dla systemu Windows**

Firma Microsoft automatycznie zbiera anonimowe dane dotyczące wydajności i korzystania z portalu firmy w celu ulepszania swoich produktów i usług. Użytkownicy końcowi mogą wyłączyć zbieranie danych za pomocą ustawienia Użycie danych na urządzeniu, lecz administratorzy nie kontrolują gromadzenia danych i nie mogą zmienić tego ustawienia określonego przez użytkownika końcowego.



## Listopad 2015
### Zarządzanie aplikacjami
Usługa Intune obsługuje zasady zarządzania aplikacjami mobilnymi, które uniemożliwiają wyciek danych firmowych do aplikacji lub usług konsumenckich. W przeszłości te zasady były wymuszane tylko względem aplikacji mobilnych uruchomionych na urządzeniach, które zostały zarejestrowane również do zarządzania urządzeniami przenośnymi (MDM) w usłudze Intune.

Aktualizacja z tego miesiąca powoduje rozszerzenie funkcji zarządzania aplikacjami mobilnymi w usłudze Intune na nowe klasy urządzeń. Obok urządzeń, które są już zarejestrowane w usłudze Intune, zasady zarządzania aplikacjami mobilnymi można również wymuszać względem:
* urządzeń zarządzanych przez inne rozwiązanie do zarządzania urządzeniami przenośnymi;
* urządzeń, które nie są rejestrowane w żadnym systemie zarządzania urządzeniami — zwykle są to urządzenia BYOD (ang. Bring Your Own Device, „przynieś własne urządzenie”).

Więcej informacji na temat nowych funkcji zarządzania aplikacjami mobilnymi można znaleźć w następujących wpisach w blogu:
* [Zwiększanie wydajności przenośnych urządzeń zarządzanych](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)
* [Przedstawiamy nowe funkcje rozwiązań Enterprise Mobility firmy Microsoft](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)

Oto niektóre najważniejsze funkcje i dodatkowe informacje na temat funkcji zarządzania aplikacjami mobilnymi usługi Intune:
* Dane firmowe są odizolowane od danych konsumentów w ramach aplikacji obsługujących usługę Intune, do których należą aplikacje pakietu Office Mobile, aplikacje innych firm, które obsługują pakiet SDK usługi Intune, a także aplikacje biznesowe opakowane w usłudze Intune.
* Dane firmowe można udostępniać (**wycinanie/kopiowanie/wklejanie**) w aplikacjach firmowych, a jednocześnie można zapobiegać udostępnianiu danych firmowych do aplikacji osobistych. Aby uzyskać więcej informacji, przeczytaj temat [Jak zasady MAM chronią dane aplikacji](https://technet.microsoft.com/library/mt627825.aspx). Ten przykładowy scenariusz — [Korzystanie z programu Microsoft Word w pracy i do wykonywania zadań osobistych](https://technet.microsoft.com/library/mt627827.aspx)— pokazuje, jak zapobiegać udostępnianiu danych firmowych aplikacjom osobistym.
* Zasady zapobiegania utracie kluczowych danych, takich jak numery PIN do poszczególnych aplikacji, kontrolki „zapisz jako”, a także dane zarządzane udostępniane między aplikacjami. Listę wszystkich zasad zawiera temat [Tworzenie i wdrażanie zasad zarządzania aplikacjami mobilnymi przy użyciu usługi Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx).
* Wszystkie nowe możliwości są dostępne w programach i usługach Word, Excel, PowerPoint, Outlook, OneNote oraz OneDrive dla Firm, które mogą być zarządzane zarówno po zarejestrowaniu urządzenia, jak i bez jego rejestracji. Funkcje ochrony przed utratą danych są natywnie wbudowane w standardowe aplikacje pakietu Office w sklepie Apple Store oraz sklepie Google Play i nie wymagają opakowywania aplikacji ani pobierania lokalnego.
* Aby dowiedzieć się, jak rozpocząć, zapoznaj się z tematem [Rozpoczynanie pracy z zasadami zarządzania aplikacjami mobilnymi w portalu Azure](https://technet.microsoft.com/library/mt627830.aspx). Aby dowiedzieć się, jak skonfigurować i wdrożyć zasady zarządzania aplikacjami mobilnymi, zobacz [Tworzenie i wdrażanie zasad zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx).
* Podczas uwierzytelniania użytkowników końcowych w aplikacji przy użyciu poświadczeń firmowych następuje automatyczne skonfigurowanie funkcji ochrony przed utratą danych. Temat [Środowisko pracy użytkownika końcowego w przypadku aplikacji skojarzonych z zasadami zarządzania aplikacjami mobilnymi usługi Microsoft Intune](https://technet.microsoft.com/library/mt627827.aspx) zawiera przykładowe scenariusze dostępu do usługi OneDrive na urządzeniach z systemem iOS i urządzeniach z systemem Android.
* Funkcje te działają na urządzeniach z systemem Android i urządzeniach z systemem iOS.

Lista [Aplikacje firmy Microsoft, których można używać z zasadami zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](https://technet.microsoft.com/library/dn708489.aspx) została zaktualizowana i zawiera teraz najnowsze aplikacje.

### Zarządzanie urządzeniami
 **Zarządzanie urządzeniami z systemem Mac OS X**
Za pomocą usługi Intune można rejestrować urządzenia z systemem Mac OS X i zarządzać nimi. Możesz wykonywać następujące operacje dotyczące urządzeń z systemem Mac OS X:
* Rejestrować urządzenia przeznaczone do zarządzania przez usługę Intune. Zobacz [Konfigurowanie zarządzania systemem iOS i komputerami Mac przez usługę Microsoft Intune](https://technet.microsoft.com/library/dn408185.aspx).
* Kontrolować ustawienia urządzenia za pomocą zasad konfiguracji ogólnej. Zobacz [Ustawienia zasad konfiguracji systemu Mac OS X w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx).
* Wdrażać ustawienia systemu Mac OS X utworzone za pomocą programu Apple Configurator. Zobacz [Ustawienia zasad niestandardowych systemu Mac OS X w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx).
* Gromadzić spisy oprogramowania i sprzętu z urządzeń z systemem Mac OS X. Zobacz [Zrozumienie informacji o urządzeniach dzięki spisowi w usłudze Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx).
* Uruchamiać nowe raporty zawierające szczegółowe informacje o urządzeniach z systemem Mac OS X, którymi zarządzasz. Zobacz [Informacje o operacjach usługi Microsoft Intune — korzystanie z raportów](https://technet.microsoft.com/library/dn646977.aspx).

**Nowe ustawienia przeglądarki Edge dla urządzeń z systemem Windows 10**
Do ogólnych zasad konfiguracji systemu Windows 10 zostały dodane nowe ustawienia, które umożliwiają zarządzanie ustawieniami i funkcjami przeglądarki Microsoft Edge. Zobacz [Ustawienia zasad konfiguracji systemu Windows 10 w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx).

**Profile poczty e-mail**
Do urządzeń z systemem Windows 10 Desktop i systemem Windows 10 Mobile została dodana nowa zasada dotycząca profilów poczty e-mail. Zobacz [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](https://technet.microsoft.com/library/dn646984.aspx).

**Nowe ustawienia zasad zachowania zgodności**
Do listy zasad zachowania zgodności zostały dodane następujące nowe ustawienia zasad bezpieczeństwa i systemu:
* Aby upewnić się, że urządzenia z systemem Windows 8.1 lub z nowszymi wersjami, które uzyskują dostęp do zasobów firmy, mają zainstalowane najnowsze aktualizacje, należy użyć ustawienia **Wymagaj automatycznych aktualizacji**. Można również określić typ aktualizacji, które będą instalowane automatycznie — mogą to być wszystkie aktualizacje oznaczone jako ważne albo wszystkie aktualizacje oznaczone jako ważne lub zalecane. Pełną listę ustawień zasad zachowania zgodności zawiera temat [Zarządzanie zasadami zgodności urządzeń w usłudze Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx).
* Nowe ustawienie **Wymagaj hasła, gdy urządzenie powraca ze stanu bezczynności** w połączeniu z istniejącym ustawieniem **Liczba minut braku aktywności, zanim będzie wymagane hasło** umożliwia utworzenie ustawienia zgodności, które wymaga, aby użytkownik końcowy wprowadził hasło w celu korzystania z urządzenia, które było nieaktywne przez pewien czas.

**Nowe opcje zasad dostępu warunkowego**
Zasady dostępu warunkowego można stosować względem **wszystkich użytkowników** w ramach nowych albo istniejących zasad dostępu warunkowego. Wszyscy użytkownicy mający licencje na usługę Intune i usługę Office 365 będzie musieli zarejestrować swoje urządzenia, a jeśli platforma urządzenia nie jest obsługiwana przez usługę Intune, wówczas dostęp będzie zablokowany dla aplikacji klienckich, które korzystają z [logowania opartego na uwierzytelnianiu w usłudze Active Directory (nowoczesnego uwierzytelniania)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/).

Można również określić, że zasady dostępu warunkowego będą obowiązywać dla **wszystkich platform**.  Każda aplikacja kliencka korzystająca z [logowania opartego na uwierzytelnianiu w usłudze Active Directory (nowoczesne uwierzytelnianie)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/) będzie podlegała zasadom dostępu warunkowego, a jeśli dana platforma nie jest aktualnie obsługiwana w usłudze Intune, wówczas będzie ona zablokowana.

### Zmiany i aktualizacje Portalu firmy oferowanego przez firmę Microsoft
W aplikacjach Portalu firmy w tej wersji wprowadzono następujące zmiany:

* **Android**: do aplikacji Portal firmy dla systemu Android został dodany ekran powitalny, aby ułatwić użytkownikom zrozumienie przeznaczenia aplikacji Portal firmy. Ten ekran ma na celu zmniejszenie liczby pobrań aplikacji przez użytkowników, których przedsiębiorstwa nie są subskrybentami usługi Intune.

* **iOS**: usługa Intune obsługuje teraz rejestrowanie urządzeń z systemem Mac OS X przy użyciu [witryny sieci Web portalu firmy](https://portal.manage.microsoft.com). Instrukcje zawiera temat [Rejestrowanie urządzenia z systemem Mac OS X w usłudze Intune](https://technet.microsoft.com/library/mt598622.aspx).

* **Witryna sieci Web portalu firmy**: użytkownicy, którzy zarejestrowali urządzenie w usłudze Intune, mogą teraz zresetować kod dostępu za pomocą opcji **Resetuj kod dostępu** w witrynie sieci Web Portal firmy. Wcześniej tylko administratorzy IT mogli resetować kody dostępu użytkowników. Opcja Resetuj kod dostępu nie jest obsługiwana na urządzeniach z systemami Windows 8.1 i Windows RT i jest dostępna tylko wtedy, gdy urządzenia zostały zarejestrowane za pomocą oprogramowania do zarządzania urządzeniami przenośnymi (MDM) lub oprogramowania MDM programu Exchange ActiveSync. Instrukcje użytkownika zawiera temat [Resetowanie kodu dostępu](https://technet.microsoft.com/library/mt590895.aspx).

### Zmiany dotyczące licencjonowania administratorów globalnych
W październiku poinformowaliśmy, że administratorzy globalni (nazywani także administratorami dzierżawy) mogą nadal wykonywać administracyjne zadania bieżące bez oddzielnej licencji na usługę Intune ani pakiet Enterprise Mobility Suite (EMS). Jeśli jednak administratorzy globalni zechcą korzystać z tej usługi na przykład w celu zarejestrowania swoich własnych urządzeń lub urządzeń firmowych albo zechcą korzystać z Portalu firmy w usłudze Intune, wówczas będą potrzebować licencji na usługę Intune lub pakiet EMS, podobnie jak każdy inny użytkownik. Poniżej przedstawiono kilka dodatkowych informacji.
* Portal firmy w usłudze Intune to miejsce, w którym użytkownicy mogą:
    * rejestrować swoje urządzenia,
    * wyświetlać stan swoich urządzeń,
    * pobierać oprogramowanie wdrożone przez administratora globalnego w organizacji,
    * znajdować linki opublikowane przez administratora globalnego dotyczące sposobu kontaktu z działem IT w organizacji.

    [Dowiedz się więcej o Portalu firmy](https://technet.microsoft.com/library/dn646966.aspx#BKMK_CompanyPortal) i o sposobach [dostosowywania Portalu firmy](https://technet.microsoft.com/library/dn646983.aspx#BKMK_ConfigureCompanyPortal).
* Osoba, która zarejestruje się w celu zakupu usługi Intune lub pakietu EMS w imieniu organizacji automatycznie staje się pierwszym administratorem globalnym w danej dzierżawie. Minionej jesieni usługa Intune rozpoczęła automatyczne przypisywanie licencji na usługę Intune lub pakiet EMS temu pierwszemu administratorowi globalnemu w ramach przejścia na [Portal usługi Office 365](http://portal.office.com/) i wycofania [Portalu konta usługi Microsoft Intune](http://account.manage.microsoft.com/). Każdy dodatkowo dodany administrator globalny może nadal wykonywać codzienne zadania administracyjne bez osobnej licencji na usługę Intune i pakiet EMS. Jeśli taki administrator zachowa się jako użytkownik końcowy i zarejestruje własne (albo firmowe) urządzenie lub pobierze oprogramowanie z portalu firmy, wówczas będzie potrzebował licencji, tak jak każdy inny użytkownik.
* Ta zmiana będzie wprowadzana fazami i zacznie obowiązywać od stycznia 2016 r.
* Dla partnerów firmy Microsoft ta zmiana nie powinna wpłynąć na możliwość administrowania usługą w imieniu klientów. W celu wykonywania zadań użytkownika końcowego użytkownik będzie potrzebował licencji na usługę Intune lub pakiet EMS, która pozwoli na zarejestrowanie urządzenia oraz dostęp do oprogramowania lub pobranie oprogramowania z Portalu firmy.

Jeśli masz pytania dotyczące tej zmiany, możesz skontaktować się z zespołem pomocy technicznej usługi Intune:
* [Kanały pomocy technicznej dla usługi Microsoft Intune](https://technet.microsoft.com/library/jj839713.aspx)
* [Pomoc techniczna ze strony społeczności](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

W celu przekazania ogólnej opinii dotyczącej usługi Microsoft Intune, co może obejmować składanie wniosków o zmianę projektu (DCR) i zgłaszanie usterek, odwiedź [witrynę UserVoice dotyczącą usługi Intune](https://microsoftintune.uservoice.com/).


### Co nowego w dokumentacji usługi Intune — listopad 2015 r.
**Nowa zawartość**
* [Ustawienia zasad konfiguracji systemu Mac OS X w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx): kontrola ustawień i funkcji urządzenia dla urządzeń z systemem Mac OS X.
* [Ustawienia zasad niestandardowych systemu Mac OS X w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx): sposób wdrażania ustawień urządzenia z systemem Mac OS X, które zostały utworzone przy użyciu narzędzia Apple Configurator.
* [Konfigurowanie zasad aplikacji związanych z zapobieganiem utracie danych w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt627825.aspx): zawiera informacje o scenariuszach obsługiwanych przez zasady zarządzania aplikacjami mobilnymi, a także informacje o tym, w jaki sposób zasady chronią dane.
* [Rozpoczynanie pracy z zasadami zarządzania aplikacjami mobilnymi w portalu Azure](https://technet.microsoft.com/library/mt627830.aspx): czego potrzeba, aby rozpocząć korzystanie z portalu Azure w wersji zapoznawczej na potrzeby zasad zarządzania aplikacjami mobilnymi.
* [Tworzenie i wdrażanie zasad zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx): zawiera przewodnik krok po kroku na temat sposobu tworzenia zasad zarządzania aplikacjami mobilnymi w portalu Azure w wersji zapoznawczej.
* [Monitorowanie zasad zarządzania aplikacjami mobilnymi przy użyciu usługi Microsoft Intune](https://technet.microsoft.com/library/mt627824.aspx): informacje dotyczące sposobów monitorowania zasad zarządzania aplikacjami mobilnymi za pomocą portalu Azure w wersji zapoznawczej.
* [Zasady zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune i funkcja „Otwórz w” w systemie iOS](https://technet.microsoft.com/library/mt627821.aspx): informacje o tym, jak zasady zarządzania aplikacjami mobilnymi działają z funkcją „Otwórz w” w systemie iOS.
* [Środowisko pracy użytkownika końcowego w przypadku aplikacji skojarzonych z zasadami zarządzania aplikacjami mobilnymi usługi Microsoft Intune](https://technet.microsoft.com/library/mt627827.aspx): poznaj środowisko pracy użytkownika końcowego, który korzysta z aplikacji powiązanych z zasadami zarządzania aplikacjami mobilnymi.
* [Czyszczenie danych zarządzanych aplikacji firmowych za pomocą usługi Microsoft Intune](https://technet.microsoft.com/library/mt627826.aspx): jak usunąć dane aplikacji firmowych.

**Zawartość zaktualizowana**
* [Ustawienia zasad konfiguracji systemu Windows 10 w usłudze Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx): dodano nowe ustawienia przeglądarki Edge.
* [Konfigurowanie zarządzania systemem iOS i komputerami Mac za pomocą usługi Microsoft Intune](http://technet.microsoft.com/library/dn408185.aspx): dodano informacje o sposobie rejestrowania urządzeń z systemem Mac OS X.
* [Zrozumienie informacji o urządzeniach dzięki spisowi w usłudze Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx): dodano informacje o spisie gromadzonym z urządzeń z systemem Mac OS X. Ponadto zaktualizowano temat o najnowsze informacje dla wszystkich platform urządzeń.
* [Informacje o operacjach usługi Microsoft Intune — korzystanie z raportów](https://technet.microsoft.com/library/dn646977.aspx): dodano informacje dotyczące dwóch nowych raportów, które służą do wyświetlania informacji o zarządzanych urządzeniach z systemem Mac OS X.
* [Zarządzanie zasadami zgodności urządzeń w usłudze Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx): dodano informacje o nowych zasadach zgodności wymagających aktualizacji automatycznych i podania hasła, gdy urządzenie powraca ze stanu bezczynności.
* [Zarządzanie dostępem do poczty e-mail za pomocą usługi Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx): dodano informacje o możliwość stosowania zasad dostępu warunkowego dla wszystkich platform i wszystkich użytkowników.
* [Zarządzanie dostępem do usługi SharePoint Online w usłudze Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx): dodano informacje o możliwość stosowania zasad dostępu warunkowego dla wszystkich platform i wszystkich użytkowników.

## Październik 2015

### Aktualizacje dostępu warunkowego dla lokalnego programu Exchange
**Teraz można zezwolić na dostęp do poczty e-mail w programie Exchange Active Sync zgodnym urządzeniom zarejestrowanym w usłudze Intune, gdy ustawiono globalną regułę programu Exchange na wartość Blokuj lub Kwarantanna** — do chwili obecnej, aby umożliwić dostęp do poczty e-mail na urządzeniach zarejestrowanych i zgodnych, trzeba było ustawić wartość domyślną globalnej reguły programu Exchange na wartość **Zezwalaj**.

Ta aktualizacja usługi usuwa wymóg stosowania wymienionego ustawienia na potrzeby dostępu warunkowego. Jeśli środowisko programu Exchange wymaga, aby domyślna reguła globalna miała wartość **Blokuj/Kwarantanna**, po prostu zaznacz pole wyboru **Przesłoń regułę domyślną** na stronie zasad dostępu warunkowego lokalnego programu Exchange. Temat [Zarządzanie dostępem do poczty e-mail za pomocą usługi Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx) zawiera dodatkowe informacje na temat reguł i wynikających z nich powiadomień dla użytkownika końcowego.

**Nowa obsługa kwarantanny za pomocą jednego kliknięcia** — uprościliśmy obsługę wiadomości e-mail kwarantanny, umożliwiając rejestrowanie za pomocą jednego kliknięcia. Dzięki tej aktualizacji usługi użytkownicy końcowi mogą kliknąć pojedynczy link w wiadomości e-mail kwarantanny, aby zakończyć proces rejestracji w aplikacji Portal firmy.
### Aktualizacje zarządzania urządzeniami przenośnymi i aplikacjami
**Android** — wszystkie funkcje zarządzania usługi Intune obsługują teraz system Android 6.0 (Marshmallow) w sposób przedstawiony w następującym wpisie w blogu: [Microsoft Intune Provides Day 0 Support for Android Marshmallow](http://blogs.technet.com/b/microsoftintune/archive/2015/10/09/microsoft-intune-to-provide-day-0-support-for-android-marshmallow.aspx) (Usługa Microsoft Intune świadczy pomoc techniczną „Day 0” dla systemu Android Marshmallow)

**iOS** — nie możesz już tworzyć nowych wdrożeń aplikacji dla urządzeń z systemem iOS w wersji starszej niż iOS 7.1. Wszystkie istniejące wdrożenia aplikacji na urządzeniach z systemem w wersji starszej niż iOS 7.1 będą w dalszym ciągu działać i będą dostępne do zarządzania za pomocą usługi Intune.

**Windows 10** — usługa Intune teraz obsługuje wdrażanie aplikacji uniwersalnych systemu Windows 10 za pomocą instalatora oprogramowania typu **Pakiet aplikacji systemu Windows**. Informacje o szczegółach i wymaganiach zawiera temat [Wprowadzenie do wdrażania aplikacji w usłudze Microsoft Intune](http://technet.microsoft.com/en-US/library/dn646955.aspx).


### Zmiany i aktualizacje aplikacji Portalu firmy oferowanych przez firmę Microsoft
W aplikacjach Portalu firmy w tej wersji wprowadzono następujące zmiany:
**iOS**
Dodano nowe przyciski do aplikacji Portal firmy, aby ułatwić użytkownikom wysyłanie dzienników diagnostycznych do administratorów IT:

|Nazwa przycisku|Gdzie jest dostępny|
|------------|---------------|
|Raport|Komunikaty alertów o błędzie|
|Wyślij raport diagnostyczny|Ekran Informacje aplikacji Portal firmy|


>[!div class="step-by-step"]

>[&larr; **Co nowego w usłudze Intune**](whats-new-in-microsoft-intune.md)    


<!--HONumber=May16_HO1-->


