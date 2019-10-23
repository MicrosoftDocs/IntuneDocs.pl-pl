---
title: Rejestrowanie urządzeń z systemem iOS — program Device Enrollment Program
titleSuffix: Microsoft Intune
description: Informacje dotyczące rejestrowania firmowych urządzeń z systemem iOS przy użyciu programu Device Enrollment Program.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7ddbf360-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 339f6b9476dae438d898b97abcaf3c1759fe9cfc
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503332"
---
# <a name="automatically-enroll-ios-devices-with-apples-device-enrollment-program"></a>Automatyczne rejestrowanie urządzeń z systemem iOS w ramach programu Device Enrollment Program

Możesz skonfigurować usługę Intune do rejestracji urządzeń z systemem iOS zakupionych w ramach programu [Device Enrollment Program (DEP)](https://deploy.apple.com) firmy Apple. Program DEP umożliwia rejestrację dużej liczby urządzeń nawet bez ich dotykania. Urządzenia, na przykład iPhone i iPad, można dostarczyć bezpośrednio do użytkowników. Gdy użytkownik włączy urządzenie, Asystent ustawień zostanie uruchomiony ze wstępnie skonfigurowanymi ustawieniami, a urządzenie zostanie zarejestrowane w funkcji zarządzania.

Włączenie rejestracji w programie DEP wymaga użycia zarówno portalu usługi Intune, jak i portalu DEP firmy Apple. Wymagana jest lista numerów seryjnych lub numerów zamówień zakupu, która pozwala przypisać urządzenia do funkcji zarządzania usługi Intune. Możliwe jest utworzenie profilów rejestracji w ramach programu DEP zawierających ustawienia stosowane względem urządzeń podczas rejestracji.

Należy zwrócić uwagę, że rejestracja w ramach programu DEP nie działa z [menedżerem rejestracji urządzeń](device-enrollment-manager-enroll.md).

> [!NOTE]
> Program DEP ustawia konfiguracje urządzeń, które nie mogą zostać usunięte przez użytkownika końcowego. Dlatego przed [migracją do programu DEP](../fundamentals/migration-guide-considerations.md) urządzenie musi zostać wyczyszczone, aby przywrócić je do stanu przed pierwszym użyciem.

## <a name="dep-and-the-company-portal"></a>Program DEP i aplikacja Portal firmy

Rejestracje programu DEP nie są zgodne z wersją aplikacji Portal firmy ze sklepu z aplikacjami. Możesz przyznać użytkownikom prawa dostępu do aplikacji Portal firmy na urządzeniu DEP. Aby przydzielić prawa dostępu, należy wypchnąć aplikację na urządzenie, korzystając z opcji **Zainstaluj Portal firmy za pomocą programu VPP** (programu zakupów zbiorczych) w profilu programu DEP. Aby uzyskać więcej informacji, zobacz [Automatyczne rejestrowanie urządzeń z systemem iOS w ramach programu Device Enrollment Program firmy Apple](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile).

 Aplikację Portal firmy można zainstalować na urządzeniach już zarejestrowanych przy użyciu programu DEP. W tym celu wdróż aplikację Portal firmy za pomocą usługi Intune z zastosowanymi [zasadami konfiguracji aplikacji](../apps/app-configuration-policies-use-ios.md).

## <a name="what-is-supervised-mode"></a>Co to jest tryb nadzorowany?

Firma Apple wprowadziła tryb nadzorowany w systemie iOS 5. Urządzeniem z systemem iOS w trybie nadzorowanym można zarządzać za pomocą większej liczby kontrolek. W efekcie jest szczególnie przydatne w przypadku urządzeń należących do firmy. Usługa Intune obsługuje konfigurowanie urządzeń dla trybu nadzorowanego w ramach programu Device Enrollment Program (DEP) firmy Apple.

Obsługa nienadzorowanych urządzeń objętych programem DEP została uznana za przestarzałą w systemie iOS 11. W systemie iOS 11 i nowszych urządzenia skonfigurowane w ramach programu DEP zawsze powinny być nadzorowane. W przyszłych wersjach systemu iOS flaga is_supervised programu DEP zostanie zignorowana.

<!--
**Steps to enable enrollment programs from Apple**
1. [Get an Apple DEP token and assign devices](#get-the-apple-dep-token)
2. [Create an enrollment profile](#create-an-apple-enrollment-profile)
3. [Synchronize DEP-managed devices](#sync-managed-device)
4. [Assign DEP profile to devices](#assign-an-enrollment-profile-to-devices)
5. [Distribute devices to users](#end-user-experience-with-managed-devices)
-->
## <a name="prerequisites"></a>Wymagania wstępne
- Urządzenia zakupione za pośrednictwem [programu Device Enrollment firmy Apple](http://deploy.apple.com)
- [Urząd zarządzania urządzeniami przenośnymi (MDM)](../fundamentals/mdm-authority-set.md)
- [Certyfikat wypychania MDM firmy Apple](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Uzyskiwanie tokenu DEP od firmy Apple

Aby zarejestrować urządzenia z systemem iOS w ramach programu DEP, należy uzyskać token programu DEP (plik p7m) od firmy Apple. Ten token umożliwia usłudze Intune synchronizację informacji dotyczących urządzeń korzystających z programu DEP należących do firmy. Umożliwia on również usłudze Intune przekazywanie profilów rejestracji do firmy Apple i przypisywanie urządzeń do tych profilów.

W portalu Apple DEP Portal można utworzyć token programu DEP. W tym portalu można również przypisać urządzenia do funkcji zarządzania usługi Intune.

> [!NOTE]
> Jeśli usuniesz token z portalu klasycznego usługi Intune przed migracją do usługi Azure, usługa Intune może przywrócić usunięty token DEP firmy Apple. Możesz ponownie usunąć token programu DEP z poziomu witryny Azure Portal.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-the-token"></a>Krok 1. Pobierz certyfikat klucza publicznego usługi Intune wymagany do utworzenia tokenu.

1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > **Dodaj**.

    ![Pobierz token programu rejestracji.](./media/device-enrollment-program-enroll-ios/image01.png)

2. Udziel firmie Microsoft uprawnień do wysyłania informacji o użytkowniku i urządzeniu do firmy Apple, wybierając pozycję **Zgadzam się**.

   ![Zrzut ekranu przedstawiający okienko tokenu programu Enrollment Program w obszarze roboczym certyfikatów firmy Apple umożliwiające pobranie klucza publicznego.](./media/device-enrollment-program-enroll-ios/add-enrollment-program-token-pane.png)

3. Wybierz pozycję **Pobierz klucz publiczny**, aby pobrać i zapisać lokalnie plik klucza szyfrowania (PEM). Plik PEM jest używany na potrzeby żądania certyfikatu relacji zaufania z portalu programu Device Enrollment Program firmy Apple.


### <a name="step-2-use-your-key-to-download-a-token-from-apple"></a>Krok 2. Aby pobrać token Apple, należy użyć swojego klucza.

1. Wybierz pozycję **Utwórz token programu Device Enrollment Program firmy Apple**, aby otworzyć portal programu wdrażania firmy Apple i zalogować się przy użyciu firmowego konta Apple ID. Tego identyfikatora firmy Apple możesz użyć do odnowienia tokenu DEP.
2. W [portalu programów wdrażania](https://deploy.apple.com) firmy Apple wybierz pozycję **Get Started** (Rozpocznij) dla opcji **Device Enrollment Program**.

3. Na stronie **Manage Servers** (Zarządzanie serwerami) wybierz pozycję **Add MDM Server** (Dodaj serwer MDM).
4. Wprowadź nazwę serwera w polu **MDM Server Name** (Nazwa serwera MDM), a następnie wybierz przycisk **Next**(Dalej). Nazwa serwera służy użytkownikowi do identyfikowania serwera MDM. Nie jest to nazwa ani adres URL serwera usługi Microsoft Intune.

5. Zostanie otwarte okno dialogowe **Add &lt;nazwa_serwera&gt;** (Dodawanie serwera <nazwa_serwera>) z widocznym komunikatem **Upload Your Public Key** (Przekaż klucz publiczny). Wybierz pozycję **Choose File…** (Wybierz plik...) w celu przekazania pliku PEM, a następnie kliknij przycisk **Next** (Dalej).

6. Wybierz kolejno pozycje **Deployment Programs** (Programy wdrażania)&gt; **Device Enrollment Program** (Program rejestracji urządzeń) &gt; **Manage Devices** (Zarządzaj urządzeniami).
7. W obszarze **Choose Devices By** (Sposób wybierania urządzeń) określ sposób identyfikowania urządzeń:
    - **Serial Number** (Numer seryjny)
    - **Order Number** (Numer zamówienia)
    - **Upload CSV File** (Przekaż plik CSV).

   ![Zrzut ekranu przedstawiający wybraną opcję wybierania urządzeń według numerów seryjnych, akcję po wybraniu ustawioną jako przypisywanie do serwera oraz wybraną nazwę serwera.](./media/device-enrollment-program-enroll-ios/enrollment-program-token-specify-serial.png)

8. W kroku **Choose Action** (Wybierz akcję) wybierz pozycję **Assign to Server** (Przypisz do serwera), wybierz &lt;nazwę serwera&gt; określoną dla usługi Microsoft Intune, a następnie kliknij przycisk **OK**. Portal firmy Apple przypisze wskazane urządzenia do funkcji zarządzania na serwerze Intune, a następnie wyświetli komunikat **Assignment Complete** (Przypisanie zostało ukończone).

   W portalu firmy Apple wybierz pozycję **Deployment Programs** (Programy wdrażania) &gt; **Device Enrollment Program** &gt; **View Assignment History** (Wyświetl historię przypisania), aby wyświetlić listę urządzeń i ich przypisania do serwera MDM.

### <a name="step-3-save-the-apple-id-used-to-create-this-token"></a>Krok 3. Zapisz identyfikator Apple ID użyty do utworzenia tokenu.

W usłudze Intune w witrynie Azure Portal podaj identyfikator Apple ID do użytku w przyszłości.

![Zrzut ekranu przedstawiający wprowadzanie identyfikatora Apple ID używanego do utworzenia tokenu programu rejestracji i przechodzenie do tokenu programu rejestracji.](./media/device-enrollment-program-enroll-ios/image03.png)

### <a name="step-4-upload-your-token-and-choose-scope-tags"></a>Krok 4. Przekaż token i wybierz tagi zakresu.

1. W polu **Token Apple** przejdź do pliku certyfikatu (pem) i wybierz pozycję **Otwórz**.
2. Jeśli chcesz zastosować [tagi zakresu](../fundamentals/scope-tags.md) do tego tokenu DEP, wybierz pozycję **Zakres (tagi)** i wybierz tagi zakresu. Tagi zakresu stosowane do tokenu będą dziedziczone przez profile i urządzenia dodawane do tego tokenu.
3. Wybierz pozycję **Utwórz**.

Dzięki certyfikatowi wypychania usługa Intune może rejestrować urządzenia z systemem iOS i zarządzać nimi, wypychając zasady do zarejestrowanych urządzeń przenośnych. Usługa Intune automatycznie synchronizuje dane z firmą Apple, co pozwala wyświetlić konto programu rejestracji.

## <a name="create-an-apple-enrollment-profile"></a>Tworzenie profilu rejestracji firmy Apple

Teraz, po zainstalowaniu tokenu, możesz utworzyć profil rejestracji dla urządzeń korzystających z programu DEP. Profil rejestracji urządzeń określa ustawienia stosowane do grupy urządzeń podczas rejestracji. Istnieje limit 100 profilów rejestracji na token DEP.

> [!NOTE]
> Urządzenia będą blokowane, jeśli nie ma wystarczającej liczby licencji aplikacji Portal firmy dla tokenu VPP lub jeśli token wygasł. Usługa Intune wyświetli alert, gdy token wkrótce wygaśnie lub licencja kończy się.
 

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu Enrollment Program**.
2. Wybierz token, wybierz pozycję **Profile** > **Utwórz profil** > **iOS**.

    ![Utwórz zrzut ekranu profilu.](./media/device-enrollment-program-enroll-ios/image04.png)

3. Na stronie **Podstawy** wprowadź nazwę w polu **Nazwa** i opis w polu **Opis** dla profilu. Informacje te będą używane do celów administracyjnych. Te szczegóły nie są widoczne dla użytkowników. Możesz użyć pola **Nazwa**, aby utworzyć grupę dynamiczną w usłudze Azure Active Directory. Nazwa profilu umożliwia zdefiniowanie parametru enrollmentProfileName w celu przypisania urządzeń z tym profilem rejestracji. Dowiedz się więcej o [grupach dynamicznych usługi Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices).

    ![Nazwa i opis profilu.](./media/device-enrollment-program-enroll-ios/image05.png)

4. Wybierz pozycję **Dalej: Ustawienia zarządzania urządzeniami**.

5. Dla pozycji **Koligacja użytkownika** wybierz, czy urządzenia z tym profilem muszą być rejestrowane z przypisanym użytkownikiem, czy bez niego.
    - **Zarejestruj z koligacją użytkownika** — tę opcję należy wybrać w przypadku urządzeń należących do użytkowników, którzy chcą korzystać z aplikacji Portal firmy w celu używania usług takich, jak instalowanie aplikacji. Gdy w przypadku korzystania z usług ADFS profil rejestracji ma w pozycji **Uwierzytelnij za pomocą aplikacji Portal firmy zamiast Asystenta konfiguracji** wartość **Nie**, wymagana jest opcja [Nazwa użytkownika protokołu WS-Trust 1.3/mieszanego punktu końcowego](https://technet.microsoft.com/library/adfs2-help-endpoints) [ Dowiedz się więcej](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

    - **Zarejestruj bez koligacji użytkownika** — tę opcję należy wybrać w przypadku urządzeń, dla których nie istnieje koligacja z żadnym użytkownikiem. Użyj tej opcji w przypadku urządzeń, które nie mają dostępu do danych użytkownika lokalnego. Aplikacje, takie jak Portal firmy, nie działają.

5. Jeśli została wybrana opcja **Zarejestruj z użyciem koligacji użytkowników**, można zezwolić użytkownikom na uwierzytelnianie za pomocą aplikacji Portal firmy zamiast Asystenta ustawień firmy Apple.

    ![Uwierzytelnianie za pomocą aplikacji Portal firmy.](./media/device-enrollment-program-enroll-ios/authenticatewithcompanyportal.png)

    > [!NOTE]
    > Jeśli chcesz wykonać dowolne z poniższych czynności, ustaw opcję **Wybierz miejsce, w którym użytkownicy muszą się uwierzytelniać** na **Portal firmy**.
    >    - Używanie uwierzytelniania wieloskładnikowego
    >    - wyświetlanie monitów dla użytkowników, w przypadku których wymagana jest zmiana hasła podczas pierwszego logowania.
    >    - Monitowanie użytkowników o zresetowanie ich wygasłych haseł podczas rejestracji
    >
    > Nie są one obsługiwane w przypadku uwierzytelniania przy użyciu asystenta ustawień firmy Apple.

6. W przypadku wybrania aplikacji **Portal firmy** dla ustawienia **Wybierz miejsce, w którym użytkownicy muszą się uwierzytelniać** możesz używać tokenu programu VPP w celu automatycznego instalowania aplikacji Portal firmy na urządzeniu. W takim przypadku użytkownik nie musi podawać identyfikatora Apple ID. Aby zainstalować aplikację Portal firmy przy użyciu tokenu programu VPP, wybierz token w obszarze **Instalowanie aplikacji Portal firmy przy użyciu programu VPP**. Wymaga, aby Portal firmy został dodany do tokenu programu VPP. Nie należy konfigurować zasad wymagających aplikacji dla użytkowników. Usługa Intune automatycznie zainstaluje aplikację Portal firmy na urządzeniach z zastosowanym tym profilem rejestracji. Upewnij się, że token nie wygasł, i że masz wystarczającą liczbę licencji urządzeń dla aplikacji Portal firmy. Jeśli token wygaśnie lub zabraknie dla niego licencji, usługa Intune zainstaluje aplikację Portal firmy ze sklepu App Store (powoduje to wyświetlenie monitu o podanie identyfikatora Apple ID). 

    > [!NOTE]
    > Po ustawieniu opcji **Wybierz miejsce, w którym użytkownicy muszą się uwierzytelniać** na **Portal firmy** upewnij się, że proces rejestracji urządzenia zostanie wykonany w ciągu pierwszych 24 godzin od pobrania portalu firmy na urządzenie programu DEP. W przeciwnym razie rejestracja może zakończyć się niepowodzeniem, a w celu zarejestrowania urządzenia będzie konieczne zresetowanie do ustawień fabrycznych.
    
    ![Zrzut ekranu przedstawiający instalowanie aplikacji Portal firmy przy użyciu programu VPP.](./media/device-enrollment-program-enroll-ios/install-cp-with-vpp.png)

7. Jeśli ustawisz wartość **Asystent ustawień** dla opcji **Wybierz miejsce, w którym użytkownicy muszą się uwierzytelniać**, ale chcesz również korzystać z dostępu warunkowego lub wdrażać aplikacje firmowe na urządzeniach, musisz zainstalować aplikację Portal firmy na urządzeniach. W tym celu wybierz pozycję **Tak** w obszarze **Zainstaluj Portal firmy**.  Jeśli chcesz, aby użytkownicy otrzymywali aplikację Portal firmy bez konieczności uwierzytelniania w sklepie z aplikacjami, wybierz opcję **Zainstaluj Portal firmy za pomocą programu VPP** i wybierz token programu VPP. Upewnij się, że token nie wygasł, i że masz wystarczającą liczbę licencji urządzeń dla aplikacji Portal firmy do przeprowadzenia prawidłowego wdrożenia.

8. Jeśli wybierzesz token dla opcji **Instaluj aplikację Portal firmy przy użyciu programu VPP**, możesz zablokować urządzenie w trybie pojedynczej aplikacji (aplikacji Portal firmy) natychmiast po zakończeniu pracy Asystenta konfiguracji. Wybierz opcję **Tak** w pozycji **Uruchom aplikację Portal firmy w trybie pojedynczej aplikacji do momentu uwierzytelnienia**, aby ustawić tę opcję. Aby użyć urządzenia, użytkownik musi najpierw uwierzytelnić się poprzez zalogowanie w aplikacji Portal firmy.

    Uwierzytelnianie wieloskładnikowe nie jest obsługiwane na pojedynczym urządzeniu zablokowanym w trybie pojedynczej aplikacji. To ograniczenie istnieje, ponieważ urządzenie nie może przełączyć się do innej aplikacji w celu ukończenia drugiego składnika uwierzytelniania. W związku z tym, jeśli chcesz przeprowadzać uwierzytelnianie wieloskładnikowe na urządzeniu w trybie pojedynczej aplikacji, drugi składnik musi znajdować się na innym urządzeniu.

    Ta funkcja jest tylko obsługiwana w systemie iOS 11.3.1 i jego nowszych wersjach.

   ![Zrzut ekranu przedstawiający tryb pojedynczej aplikacji.](./media/device-enrollment-program-enroll-ios/single-app-mode.png)

9. Jeśli chcesz, aby urządzenia korzystające z tego profilu były nadzorowane, wybierz pozycję **Tak** w obszarze **Nadzorowane**.

    ![Zrzut ekranu pozycji Ustawienia zarządzania urządzeniami.](./media/device-enrollment-program-enroll-ios/supervisedmode.png)

    W przypadku urządzeń **nadzorowanych** dostępnych jest więcej opcji zarządzania, a blokada aktywacji jest domyślnie wyłączona. Firma Microsoft zaleca używanie programu DEP jako mechanizmu włączania trybu nadzorowanego, szczególnie w przypadku wdrażania dużej liczby urządzeń z systemem iOS.

    Użytkownicy są powiadamiani o tym, że ich urządzenia są nadzorowane, na dwa sposoby:

   - Na ekranie blokady wyświetlany jest komunikat: „To urządzenie iPhone jest zarządzane przez firmę Contoso”.
   - Na ekranie **Ustawienia** > **Ogólne** > **Informacje** wyświetlany jest komunikat: „To urządzenie iPhone jest nadzorowane. Firma Contoso może monitorować Twój ruch w Internecie i lokalizować to urządzenie”

     > [!NOTE]
     > Urządzenie zarejestrowane bez nadzoru można zresetować do nadzorowanego tylko przy użyciu programu Apple Configurator. Zresetowanie urządzenia w ten sposób wymaga podłączenia urządzenia z systemem iOS do komputera Mac za pomocą kabla USB. Dowiedz się więcej na ten temat w [dokumentacji programu Apple Configurator](http://help.apple.com/configurator/mac/2.3).

10. Wybierz, czy chcesz ustawić rejestrację zablokowaną dla urządzeń używających tego profilu. **Rejestracja zablokowana** wyłącza ustawienia systemu iOS, które umożliwiają usunięcie profilu zarządzania w menu **Ustawienia**. Po rejestracji urządzenia nie można zmienić tego ustawienia bez wyczyszczenia danych z urządzenia. Takie urządzenia muszą mieć ustawiony tryb zarządzania **Nadzorowane** na *Tak*. 

11. Wybierz, czy chcesz, aby urządzenia korzystające z tego profilu mogły **synchronizować się z komputerami**. W przypadku wybrania pozycji **Zezwalaj programowi Apple Configurator według certyfikatów** należy wybrać certyfikat w obszarze **Certyfikaty programu Apple Configurator**.

12. W przypadku wybrania opcji **Zezwalaj programowi Apple Configurator według certyfikatów** w poprzednim kroku wybierz certyfikat programu Apple Configurator do zaimportowania.

13. Można określić format nazewnictwa dla urządzeń, który będzie automatycznie stosowany podczas rejestrowania i po każdym kolejnym zaewidencjonowaniu. Aby utworzyć szablon nazewnictwa, wybierz pozycję **Tak** w obszarze **Zastosuj szablon nazwy urządzenia**. Następnie w polu **Szablon nazwy urządzenia** wprowadź szablon, który ma być używany dla nazw korzystających z tego profilu. Możesz określić format szablonu, który zawiera typ urządzenia i numer seryjny. 

14. Wybierz pozycję **Dalej: Dostosowanie Asystenta ustawień**.

15. Na stronie **Dostosowywanie Asystenta ustawień** skonfiguruj następujące ustawienia profilu: ![Dostosowanie Asystenta ustawień.](./media/device-enrollment-program-enroll-ios/setupassistantcustom.png)


    | Ustawienia działu | Opis |
    |---|---|
    | <strong>Nazwa działu</strong> | Wyświetlane, gdy użytkownicy klikną pozycję <strong>Informacje o konfiguracji</strong> podczas aktywacji. |
    |    <strong>Telefon działu</strong>     | Jest wyświetlany, gdy użytkownik kliknie podczas aktywacji przycisk <strong>Potrzebna pomoc</strong>. |

    Podczas konfigurowania użytkownika można ukryć ekrany Asystenta ustawień na urządzeniu.
    - Jeśli wybierzesz pozycję **Ukryj**, ekran nie będzie wyświetlany podczas konfigurowania. Po skonfigurowaniu urządzenia użytkownik może nadal przejść do menu **Ustawienia**, aby skonfigurować tę funkcję.
    - Jeśli wybierzesz pozycję **Pokaż**, ekran będzie wyświetlany podczas konfigurowania. Użytkownik może czasami pominąć ekran bez podejmowania akcji. Później jednak może przejść do menu **Ustawienia** urządzenia, aby skonfigurować tę funkcję. 


    | Ustawienia ekranu Asystent ustawień | Jeśli wybierzesz pozycję **Pokaż**, podczas konfigurowania urządzenie będzie... |
    |------------------------------------------|------------------------------------------|
    | <strong>Kod dostępu</strong> | Monitować o wprowadzenie hasła. Zawsze należy wymagać kodu dostępu dla urządzeń niezabezpieczonych, chyba że dostęp do niego będzie kontrolowany w inny sposób (np. zostanie zastosowany tryb kiosku, który ogranicza możliwość użycia urządzenia do jednej aplikacji). |
    | <strong>Usługi lokalizacyjne</strong> | Monitować użytkownika o określenie lokalizacji. |
    | <strong>Przywróć</strong> | Wyświetlać ekran Aplikacje i dane. Ten ekran oferuje użytkownikowi opcję przywracania lub przenoszenia danych z kopii zapasowej w usłudze iCloud podczas konfigurowania urządzenia. |
    | <strong>Identyfikator Apple ID i usługa iCloud</strong> | Oferować użytkownikowi opcję logowania za pomocą identyfikatora Apple ID i używania usługi iCloud.                         |
    | <strong>Warunki i postanowienia</strong> | Wymagać od użytkownika akceptacji warunków i postanowień firmy Apple. |
    | <strong>Touch ID</strong> | Oferować użytkownikowi możliwość konfigurowania identyfikacji za pomocą odcisku palca w urządzeniu. |
    | <strong>Apple Pay</strong> | Oferować użytkownikowi opcję skonfigurowania usługi Apple Pay na urządzeniu. |
    | <strong>Powiększenie</strong> | Oferować użytkownikowi opcję powiększania ekranu podczas konfigurowania urządzenia. |
    | <strong>Siri</strong> | Oferować użytkownikowi opcję konfigurowania programu Siri. |
    | <strong>Dane diagnostyczne</strong> | Wyświetlać ekran Diagnostyka dla użytkownika. Na tym ekranie użytkownik może wybrać opcję wysyłania danych diagnostycznych do firmy Apple. |
    | <strong>Wyświetlanie sygnału</strong> | Umożliwiać użytkownikowi włączenie funkcji wyświetlania sygnału. |
    | <strong>Ochrona prywatności</strong> | Wyświetlać użytkownikowi ekran ochrony prywatności. |
    | <strong>Migracja systemu Android</strong> | Umożliwiać użytkownikowi migrację danych z urządzenia z systemem Android. |
    | <strong>iMessage i FaceTime</strong> | Umożliwiać użytkownikowi skonfigurowanie aplikacji iMessage i FaceTime. |
    | <strong>Dołączanie</strong> | Wyświetlać ekrany informacyjne dotyczące dołączania na potrzeby edukacji użytkowników, takie jak Arkusz okładki, Wybór aplikacji i Centrum sterowania. |
    | <strong>Migracja urządzenia Watch</strong> | Umożliwiać użytkownikowi migrowanie danych z urządzenia Watch. |
    | <strong>Czas przed ekranem</strong> | Wyświetlać ekran Czas przed ekranem. |
    | <strong>Aktualizacja oprogramowania</strong> | Wyświetlać ekranu obowiązkowych aktualizacji oprogramowania. |
    | <strong>Instalator SIM</strong> | Umożliwiać użytkownikowi dodawanie planu sieci komórkowej. |
    | <strong>Wygląd</strong> | Wyświetlać ekran Wygląd dla użytkownika. |
    | <strong>Język ekspresowy</strong>| Wyświetlać ekran Język ekspresowy dla użytkownika. |
    | <strong>Preferowany język</strong> | Dawać użytkownikowi możliwość wyboru **preferowanego języka**. |
    | <strong>Migracja między urządzeniami</strong> | Umożliwiać użytkownikowi migrowanie danych ze starego urządzenia na to urządzenie.|
    

16. Wybierz pozycję **Dalej**, aby przejść do strony **Recenzja i tworzenie**.

17. Abu zapisać profil, wybierz pozycję **Utwórz**.

## <a name="sync-managed-devices"></a>Synchronizowanie urządzeń zarządzanych
Gdy usługa Intune ma uprawnienia do zarządzania urządzeniami, można ją zsynchronizować z danymi firmy Apple, aby wyświetlić zarządzane urządzenia w usłudze Intune w witrynie Azure Portal.

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > wybierz token z listy > **Urządzenia** > **Synchronizuj**. ![Zrzut ekranu przedstawiający węzeł Urządzenia programu Enrollment Program i link Synchronizuj.](./media/device-enrollment-program-enroll-ios/image06.png)

   Aby spełnić warunki firmy Apple dotyczące ruchu w programie rejestracji, usługa Intune nakłada następujące ograniczenia:
   - Pełną synchronizację można uruchamiać nie częściej niż co siedem dni. Podczas pełnej synchronizacji usługa Intune pobiera pełną zaktualizowaną listę numerów seryjnych przypisanych do serwera MDM firmy Apple połączonego z usługą Intune. Jeśli urządzenie programu DEP zostanie usunięte z portalu usługi Intune, powinno zostać cofnięte jego przypisanie do serwera MDM firmy Apple w portalu programu DEP. W przeciwnym razie nie zostanie ono ponownie zaimportowane do usługi Intune do momentu uruchomienia pełnej synchronizacji.   
   - Synchronizacja jest uruchamiana automatycznie co 24 godziny. Można też przeprowadzić synchronizację, klikając przycisk **Synchronizuj** (nie częściej niż raz na 15 minut). Każde żądanie synchronizacji ma przydzielone 15 minut na ukończenie. Przycisk **Synchronizuj** pozostaje wyłączony do ukończenia synchronizacji. Synchronizacja spowoduje odświeżenie stanu bieżącego urządzenia oraz zaimportowanie nowych urządzeń przypisanych do serwera MDM firmy Apple.   


## <a name="assign-an-enrollment-profile-to-devices"></a>Przypisywanie profilu rejestracji do urządzeń
Zanim możliwe będzie rejestrowanie urządzeń, należy przypisać profil programu rejestracji.

>[!NOTE]
>Możesz także przypisać numery seryjne do profilów w bloku **Numery seryjne Apple**.

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > wybierz token z listy.
2. Wybierz **Urządzenia** > wybierz urządzenia na liście > **Przypisz profil**.
3. W obszarze **Przypisz profil** wybierz profil dla urządzeń > **Przypisz**.

### <a name="assign-a-default-profile"></a>Przypisywanie profilu domyślnego

Można wybrać profil domyślny, który zostanie zastosowany do wszystkich urządzeń rejestrowanych przy użyciu określonego tokenu.

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > wybierz token z listy.
2. Kliknij pozycję **Ustaw profil domyślny**, wybierz profil z listy rozwijanej, a następnie kliknij pozycję **Zapisz**. Ten profil zostanie zastosowany do wszystkich urządzeń rejestrowanych przy użyciu tokenu.

## <a name="distribute-devices"></a>Dystrybuowanie urządzeń
Włączono zarządzanie i synchronizację między danymi firmy Apple i usługą Intune oraz przypisano profil umożliwiający rejestrowanie urządzeń korzystających z programu DEP. Możesz teraz przekazać urządzenia użytkownikom. W przypadku urządzeń z koligacją użytkownika wymagane jest, aby poszczególni użytkownicy mieli przypisane licencje na korzystanie z usługi Intune. Urządzenia bez koligacji użytkownika wymagają licencji urządzenia. Aktywowane urządzenie nie może stosować profilu rejestracji, dopóki nie zostaną wyczyszczone dane urządzenia.

Zobacz [Rejestracja urządzenia z systemem iOS przy użyciu programu Device Enrollment Program](/intune-user-help/enroll-your-device-dep-ios).

## <a name="renew-a-dep-token"></a>Odnawianie tokenu DEP  
1. Przejdź do witryny deploy.apple.com.  
2. W obszarze **Zarządzanie serwerami** wybierz serwer MDM skojarzony z plikiem tokenu, który chcesz odnowić.
3. Wybierz pozycję **Wygeneruj nowy token**.

    ![Zrzut ekranu przedstawiający generowanie nowego tokenu.](./media/device-enrollment-program-enroll-ios/generatenewtoken.png)

4. Wybierz pozycję **Token Twojego serwera**.  
5. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji**, a następnie wybierz token.
    ![Zrzut ekranu przedstawiający tokeny programu rejestracji.](./media/device-enrollment-program-enroll-ios/enrollmentprogramtokens.png)

6. Wybierz pozycję **Odnów token** i wprowadź identyfikator Apple ID użyty do utworzenia pierwotnego tokenu.  
    ![Zrzut ekranu przedstawiający generowanie nowego tokenu.](./media/device-enrollment-program-enroll-ios/renewtoken.png)

8. Przekaż nowo pobrany token.  
9. Wybierz pozycję **Odnów token**. Wyświetli się potwierdzenie, że token został odnowiony.   
    ![Zrzut ekranu przedstawiający potwierdzenie.](./media/device-enrollment-program-enroll-ios/confirmation.png)
