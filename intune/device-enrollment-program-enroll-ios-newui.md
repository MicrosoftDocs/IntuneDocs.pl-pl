---
title: Rejestrowanie urządzeń z systemem iOS — program Device Enrollment Program
titleSuffix: Microsoft Intune
description: Informacje dotyczące rejestrowania firmowych urządzeń z systemem iOS przy użyciu programu Device Enrollment Program (nowy interfejs użytkownika).
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7ddbf360-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b7925b09a8f5978319fc76d899f954190dc9df4e
ms.sourcegitcommit: 4c18352d5b3b30080f7c7257fa63d852b1894850
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2018
---
# <a name="automatically-enroll-ios-devices-with-apples-device-enrollment-program"></a>Automatyczne rejestrowanie urządzeń z systemem iOS w ramach programu Device Enrollment Program

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

> [!NOTE]
> ### <a name="temporary-user-interface-differences"></a>Tymczasowe różnice dotyczące interfejsu użytkownika
> Interfejsy funkcji opisanych na tej stronie są w trakcie aktualizacji. Aktualizacje te zostaną stopniowo wprowadzone na wszystkich kontach użytkowników do końca kwietnia.
>
> Jeśli Twoja strona **Rejestrowanie urządzenia** wygląda jak poniżej, masz zaktualizowane interfejsy użytkownika i możesz skorzystać z tej strony pomocy.
>
> ![Nowy interfejs użytkownika](./media/appleenroll-newui.png)
>
> Jeśli Twoja strona **Rejestrowanie urządzenia** wygląda jak poniżej, Twoje konto nie zostało jeszcze zaktualizowane do nowego interfejsu użytkownika. Przejdź do [tej strony pomocy](device-enrollment-program-enroll-ios.md).
>
> ![Stary interfejs użytkownika](./media/appleenroll-oldui.png)

W tym temacie przedstawiono informacje przydatne podczas włączania rejestracji urządzeń z systemem iOS zakupionych w ramach programu [Device Enrollment Program (DEP)](https://deploy.apple.com) firmy Apple. Rejestrację w ramach programu DEP można włączyć dla dużej liczby urządzeń bez konieczności używania ich. Urządzenia, na przykład iPhone i iPad, można dostarczyć bezpośrednio do użytkowników. Gdy użytkownik włączy urządzenie, Asystent ustawień zostanie uruchomiony ze wstępnie skonfigurowanymi ustawieniami, a urządzenie zostanie zarejestrowane w funkcji zarządzania.

Włączenie rejestracji w programie DEP wymaga użycia zarówno portalu usługi Intune, jak i portalu DEP firmy Apple. Wymagana jest lista numerów seryjnych lub numerów zamówień zakupu, która pozwala przypisać urządzenia do funkcji zarządzania usługi Intune. Możliwe jest utworzenie profilów rejestracji w ramach programu DEP zawierających ustawienia stosowane względem urządzeń podczas rejestracji.

Należy zwrócić uwagę, że rejestracja w ramach programu DEP nie działa z [menedżerem rejestracji urządzeń](device-enrollment-manager-enroll.md).

## <a name="what-is-supervised-mode"></a>Co to jest tryb nadzorowany?
Firma Apple wprowadziła tryb nadzorowany w systemie iOS 5. Urządzeniem z systemem iOS w trybie nadzorowanym można zarządzać za pomocą większej liczby kontrolek. W efekcie jest szczególnie przydatne w przypadku urządzeń należących do firmy. Usługa Intune obsługuje konfigurowanie urządzeń dla trybu nadzorowanego w ramach programu Device Enrollment Program (DEP) firmy Apple. 

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
- [Urząd zarządzania urządzeniami przenośnymi](mdm-authority-set.md)
- [Certyfikat wypychania MDM firmy Apple](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Uzyskiwanie tokenu DEP od firmy Apple

Aby zarejestrować urządzenia z systemem iOS w ramach programu DEP, należy uzyskać token programu DEP (plik p7m) od firmy Apple. Ten token umożliwia usłudze Intune synchronizację informacji dotyczących urządzeń korzystających z programu DEP należących do firmy. Umożliwia on również usłudze Intune przekazywanie profilów rejestracji do firmy Apple i przypisywanie urządzeń do tych profilów.

W portalu Apple DEP Portal można utworzyć token programu DEP. W tym portalu można również przypisać urządzenia do funkcji zarządzania usługi Intune.

> [!NOTE]
> Jeśli usuniesz token z portalu klasycznego usługi Intune przed migracją do usługi Azure, usługa Intune może przywrócić usunięty token DEP firmy Apple. Możesz ponownie usunąć token programu DEP z poziomu witryny Azure Portal. Możesz ponownie usunąć token programu DEP z poziomu witryny Azure Portal.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-the-token"></a>Krok 1. Pobierz certyfikat klucza publicznego usługi Intune wymagany do utworzenia tokenu.

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > **Dodaj**.

    ![Pobierz token programu rejestracji.](./media/device-enrollment-program-enroll-ios/image01.png)

2. Udziel firmie Microsoft uprawnień do wysyłania informacji o użytkowniku i urządzeniu do firmy Apple, wybierając pozycję **Zgadzam się**.

   ![Zrzut ekranu przedstawiający okienko tokenu programu Enrollment Program w obszarze roboczym certyfikatów firmy Apple umożliwiające pobranie klucza publicznego.](./media/device-enrollment-program-enroll-ios-newui/add-enrollment-program-token-pane.png)

3. Wybierz pozycję **Pobierz klucz publiczny**, aby pobrać i zapisać lokalnie plik klucza szyfrowania (PEM). Plik PEM jest używany na potrzeby żądania certyfikatu relacji zaufania z portalu programu Device Enrollment Program firmy Apple.


### <a name="step-2-use-your-key-to-download-a-token-from-apple"></a>Krok 2. Aby pobrać token Apple, należy użyć swojego klucza.

1. Wybierz pozycję **Utwórz token programu Device Enrollment Program firmy Apple**, aby otworzyć portal programu wdrażania firmy Apple i zalogować się przy użyciu firmowego konta Apple ID. Tego identyfikatora firmy Apple możesz użyć do odnowienia tokenu DEP.
2.  W [portalu programów wdrażania](https://deploy.apple.com) firmy Apple wybierz pozycję **Get Started** (Rozpocznij) dla opcji **Device Enrollment Program**.

3. Na stronie **Manage Servers** (Zarządzanie serwerami) wybierz pozycję **Add MDM Server** (Dodaj serwer MDM).
4. Wprowadź nazwę serwera w polu **MDM Server Name** (Nazwa serwera MDM), a następnie wybierz przycisk **Next**(Dalej). Nazwa serwera służy użytkownikowi do identyfikowania serwera MDM. Nie jest to nazwa ani adres URL serwera usługi Microsoft Intune.

5. Zostanie otwarte okno dialogowe **Add &lt;nazwa_serwera&gt;** (Dodawanie serwera <nazwa_serwera>) z widocznym komunikatem **Upload Your Public Key** (Przekaż klucz publiczny). Kliknij pozycję **Choose File…** (Wybierz plik...) w celu przekazania pliku PEM, a następnie kliknij przycisk **Next** (Dalej).

6. Wybierz kolejno pozycje **Deployment Programs** (Programy wdrażania)&gt; **Device Enrollment Program** (Program rejestracji urządzeń) &gt; **Manage Devices** (Zarządzaj urządzeniami).
7. W obszarze **Choose Devices By** (Sposób wybierania urządzeń) określ sposób identyfikowania urządzeń:
    - **Serial Number** (Numer seryjny)
    - **Order Number** (Numer zamówienia)
    - **Upload CSV File** (Przekaż plik CSV).

   ![Zrzut ekranu przedstawiający wybraną opcję wybierania urządzeń według numerów seryjnych, akcję po wybraniu ustawioną jako przypisywanie do serwera oraz wybraną nazwę serwera.](./media/enrollment-program-token-specify-serial.png)

8. W kroku **Choose Action** (Wybierz akcję) wybierz pozycję **Assign to Server** (Przypisz do serwera), wybierz &lt;nazwę serwera&gt; określoną dla usługi Microsoft Intune, a następnie kliknij przycisk **OK**. Portal firmy Apple przypisze wskazane urządzenia do funkcji zarządzania na serwerze Intune, a następnie wyświetli komunikat **Assignment Complete** (Przypisanie zostało ukończone).

   W portalu firmy Apple wybierz pozycję **Deployment Programs** (Programy wdrażania) &gt; **Device Enrollment Program** &gt; **View Assignment History** (Wyświetl historię przypisania), aby wyświetlić listę urządzeń i ich przypisania do serwera MDM.

### <a name="step-3-save-the-apple-id-used-to-create-this-token"></a>Krok 3. Zapisz identyfikator Apple ID użyty do utworzenia tokenu.

W usłudze Intune w witrynie Azure Portal podaj identyfikator Apple ID do użytku w przyszłości.

![Zrzut ekranu przedstawiający wprowadzanie identyfikatora Apple ID używanego do utworzenia tokenu programu rejestracji i przechodzenie do tokenu programu rejestracji.](./media/device-enrollment-program-enroll-ios/image03.png)

### <a name="step-4-upload-your-token"></a>Krok 4. Przekaż token.
W polu **Token Apple** przejdź do pliku certyfikatu (.pem), wybierz pozycję **Otwórz**, a następnie kliknij **Utwórz**. Dzięki certyfikatowi wypychania usługa Intune może rejestrować urządzenia z systemem iOS i zarządzać nimi, wypychając zasady do zarejestrowanych urządzeń przenośnych. Usługa Intune automatycznie synchronizuje dane z firmą Apple, co pozwala wyświetlić konto programu rejestracji.

## <a name="create-an-apple-enrollment-profile"></a>Tworzenie profilu rejestracji firmy Apple

Teraz, po zainstalowaniu tokenu, możesz utworzyć profil rejestracji dla urządzeń korzystających z programu DEP. Profil rejestracji urządzeń określa ustawienia stosowane do grupy urządzeń podczas rejestracji.

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu Enrollment Program**.
2. Wybierz token, wybierz pozycję **Profile**, a następnie wybierz pozycję **Utwórz profil**.
    ![Utwórz zrzut ekranu profilu.](./media/device-enrollment-program-enroll-ios/image04.png)
3. W obszarze **Utwórz profil** wprowadź nazwę w polu **Nazwa** i opis w polu **Opis**. Informacje te będą używane do celów administracyjnych. Te szczegóły nie są widoczne dla użytkowników. Możesz użyć pola **Nazwa**, aby utworzyć grupę dynamiczną w usłudze Azure Active Directory. Nazwa profilu umożliwia zdefiniowanie parametru enrollmentProfileName w celu przypisania urządzeń z tym profilem rejestracji. Dowiedz się więcej o [grupach dynamicznych usługi Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects).
    ![Nazwa i opis profilu.](./media/device-enrollment-program-enroll-ios/image05.png)

4. Dla pozycji **Koligacja użytkownika** wybierz, czy urządzenia z tym profilem muszą być rejestrowane z przypisanym użytkownikiem, czy bez niego.
    - **Zarejestruj z koligacją użytkownika** — tę opcję należy wybrać w przypadku urządzeń należących do użytkowników, które chcą korzystać z Portalu firmy na potrzeby usług takich jak instalowanie aplikacji. Ta opcja umożliwia również uwierzytelnianie urządzeń przy użyciu aplikacji Portal firmy. Koligacja użytkownika wymaga [nazwy użytkownika protokołu WS-Trust 1.3/mieszanego punktu końcowego](https://technet.microsoft.com/library/adfs2-help-endpoints). [Dowiedz się więcej](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

    - **Zarejestruj bez koligacji użytkownika** — tę opcję należy wybrać w przypadku urządzeń, dla których nie istnieje koligacja z żadnym użytkownikiem. Można jej używać dla urządzeń, które wykonują zadania bez uzyskiwania dostępu do lokalnych danych użytkowników. Aplikacje, takie jak Portal firmy, nie działają.

5. Jeśli została wybrana opcja **Zarejestruj z użyciem koligacji użytkowników**, można zezwolić użytkownikom na uwierzytelnianie za pomocą aplikacji Portal firmy zamiast Asystenta ustawień firmy Apple.

    ![Uwierzytelnianie za pomocą aplikacji Portal firmy.](./media/device-enrollment-program-enroll-ios/authenticatewithcompanyportal.png)

    > [!NOTE]
    > Uwierzytelnianie wieloskładnikowe (MFA) nie działa podczas rejestrowania w programie DEP, jeśli właściwości profilu zostały ustawione na wartość **Zarejestruj z koligacją użytkownika**. Po zarejestrowaniu usługa MFA działa zgodnie z oczekiwaniami na tych urządzeniach. Na urządzeniach nie mogą być wyświetlane monity dla użytkowników, w przypadku których wymagana jest zmiana hasła podczas pierwszego logowania. Ponadto dla użytkowników, których hasła wygasły, nie zostanie wyświetlony monit o zresetowanie hasła podczas rejestracji. Muszą oni zresetować hasło za pomocą innego urządzenia.

6. Wybierz pozycję **Ustawienia zarządzania urządzeniami** i określ, czy chcesz, żeby urządzenia korzystające z tego profilu były nadzorowane.
    W przypadku urządzeń **nadzorowanych** dostępnych jest więcej opcji zarządzania, a blokada aktywacji jest domyślnie wyłączona. Firma Microsoft zaleca używanie programu DEP jako mechanizmu włączania trybu nadzorowanego, szczególnie w przypadku organizacji, które wdrażają dużą liczbę urządzeń z systemem iOS.

    Użytkownicy są powiadamiani o tym, że ich urządzenia są nadzorowane, na dwa sposoby:

   - Na ekranie blokady jest wyświetlany komunikat: „Ten iPhone jest zarządzany przez firmę Contoso”.
   - Na ekranie **Ustawienia** > **Ogólne** > **Informacje** jest wyświetlany komunikat: „Ten iPhone jest nadzorowany. Firma Contoso może monitorować Twój ruch w Internecie i lokalizować to urządzenie”

     > [!NOTE]
     > Urządzenie zarejestrowane bez nadzoru można zresetować do nadzorowanego tylko przy użyciu programu Apple Configurator. Zresetowanie urządzenia w ten sposób wymaga podłączenia urządzenia z systemem iOS do komputera Mac za pomocą kabla USB. Dowiedz się więcej na ten temat w [dokumentacji programu Apple Configurator](http://help.apple.com/configurator/mac/2.3).

7. Wybierz, czy chcesz ustawić rejestrację zablokowaną dla urządzeń używających tego profilu. **Rejestracja zablokowana** wyłącza ustawienia systemu iOS, które umożliwiają usunięcie profilu zarządzania w menu **Ustawienia**. Po rejestracji urządzenia nie można zmienić tego ustawienia bez resetowania urządzenia do ustawień fabrycznych. Takie urządzenia muszą mieć ustawiony tryb zarządzania **Nadzorowane** na *Tak*. 

8. Wybierz, czy chcesz, aby urządzenia korzystające z tego profilu mogły **synchronizować się z komputerami**. W przypadku wybrania pozycji **Zezwalaj programowi Apple Configurator według certyfikatów** należy wybrać certyfikat w obszarze **Certyfikaty programu Apple Configurator**.

9. W przypadku wybrania opcji **Zezwalaj programowi Apple Configurator według certyfikatów** w poprzednim kroku wybierz certyfikat programu Apple Configurator do zaimportowania.

10. Wybierz przycisk **OK**.

11. Wybierz pozycję **Ustawienia Asystenta ustawień**, aby skonfigurować następujące ustawienia profilu: ![Dostosowanie Asystenta ustawień.](./media/device-enrollment-program-enroll-ios/setupassistantcustom.png)


    |                 Ustawienie                  |                                                                                               Opis                                                                                               |
    |------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    |     <strong>Nazwa działu</strong>     |                                                             Wyświetlane, gdy użytkownicy klikną pozycję <strong>Informacje o konfiguracji</strong> podczas aktywacji.                                                              |
    |    <strong>Telefon działu</strong>     |                                                          Jest wyświetlany, gdy użytkownik kliknie podczas aktywacji przycisk <strong>Potrzebna pomoc</strong>.                                                          |
    | <strong>Opcje Asystenta ustawień</strong> |                                                     Następujące opcjonalne ustawienia mogą być później konfigurowane w menu <strong>Ustawienia</strong> systemu iOS.                                                      |
    |        <strong>Kod dostępu</strong>         | Wyświetla monit o podanie kodu dostępu podczas aktywacji. Zawsze należy wymagać kodu dostępu, chyba że urządzenie zostanie zabezpieczone lub dostęp do niego będzie kontrolowany w inny sposób (tj. zostanie zastosowany tryb kiosku, który ogranicza możliwość użycia urządzenia do jednej aplikacji). |
    |    <strong>Usługi lokalizacyjne</strong>    |                                                                 Jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji.                                                                  |
    |         <strong>Przywróć</strong>         |                                                                Jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit o kopię zapasową w programie iCloud podczas aktywacji.                                                                 |
    |   <strong>Identyfikator Apple ID i usługa iCloud</strong>   |                         Jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit o zalogowanie przy użyciu identyfikatora Apple ID, a ekran Aplikacje i dane umożliwi przywrócenie urządzenia z kopii zapasowej usługi iCloud.                         |
    |  <strong>Warunki i postanowienia</strong>   |                                                   Jeśli to ustawienie zostało włączone, Asystent ustawień monituje użytkowników o zaakceptowanie warunków i postanowień firmy Apple podczas aktywacji.                                                   |
    |        <strong>Touch ID</strong>         |                                                                 Jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji.                                                                 |
    |        <strong>Apple Pay</strong>        |                                                                 Jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji.                                                                 |
    |          <strong>Powiększenie</strong>           |                                                                 Jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji.                                                                 |
    |          <strong>Siri</strong>           |                                                                 Jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji.                                                                 |
    |     <strong>Dane diagnostyczne</strong>     |                                                                 Jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji.                                                                 |


12. Wybierz przycisk **OK**.

13. Abu zapisać profil, wybierz pozycję **Utwórz**.

## <a name="sync-managed-devices"></a>Synchronizowanie urządzeń zarządzanych
Gdy usługa Intune ma uprawnienia do zarządzania urządzeniami, można ją zsynchronizować z danymi firmy Apple, aby wyświetlić zarządzane urządzenia w usłudze Intune w witrynie Azure Portal.

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > wybierz token z listy > **Urządzenia** > **Synchronizuj**. ![Zrzut ekranu przedstawiający wybrany węzeł Urządzenia programu Enrollment Program i wybierany link Synchronizuj.](./media/device-enrollment-program-enroll-ios/image06.png)

   Aby spełnić warunki firmy Apple dotyczące ruchu w programie rejestracji, usługa Intune nakłada następujące ograniczenia:
   - Pełną synchronizację można uruchamiać nie częściej niż co siedem dni. Podczas pełnej synchronizacji usługa Intune odświeża każdy numer seryjny Apple przypisany do usługi Intune. W przypadku próby przeprowadzenia pełnej synchronizacji przed upływem siedmiu dni od poprzedniej pełnej synchronizacji usługa Intune odświeża tylko numery seryjne, które jeszcze nie zostały przypisane do usługi Intune.
   - Każde żądanie synchronizacji ma przydzielone 15 minut na zakończenie. W tym czasie lub do momentu zakończenia żądania powodzeniem przycisk **synchronizacji** jest wyłączony.
   - Usługa Intune co 24 godziny synchronizuje z firmą Apple urządzenia nowe i usunięte.

## <a name="assign-an-enrollment-profile-to-devices"></a>Przypisywanie profilu rejestracji do urządzeń
Zanim możliwe będzie rejestrowanie urządzeń, należy przypisać profil programu rejestracji.

>[!NOTE]
>Możesz także przypisać numery seryjne do profilów w bloku **Numery seryjne Apple**.

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > wybierz token z listy.
2. Wybierz **Urządzenia** > wybierz urządzenia na liście > **Przypisz profil**.
3. W obszarze **Przypisz profil** wybierz profil dla urządzeń, a następnie wybierz pozycję **Przypisz**.

### <a name="assign-a-default-profile"></a>Przypisywanie profilu domyślnego

Można wybrać profil domyślny, który zostanie zastosowany do wszystkich urządzeń rejestrowanych przy użyciu określonego tokenu.

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > wybierz token z listy.
2. Kliknij pozycję **Ustaw profil domyślny**, wybierz profil z listy rozwijanej, a następnie kliknij pozycję **Zapisz**. Ten profil zostanie zastosowany do wszystkich urządzeń rejestrowanych przy użyciu tokenu.

## <a name="distribute-devices"></a>Dystrybuowanie urządzeń
Włączono zarządzanie i synchronizację między danymi firmy Apple i usługą Intune oraz przypisano profil umożliwiający rejestrowanie urządzeń korzystających z programu DEP. Możesz teraz przekazać urządzenia użytkownikom. W przypadku urządzeń z koligacją użytkownika wymagane jest, aby poszczególni użytkownicy mieli przypisane licencje na korzystanie z usługi Intune. Urządzenia bez koligacji użytkownika wymagają licencji urządzenia. Aktywowane urządzenie nie może stosować profilu rejestracji, dopóki urządzenie nie zostanie zresetowane do ustawień fabrycznych.

Zobacz [Rejestracja urządzenia z systemem iOS przy użyciu programu Device Enrollment Program](/intune-user-help/enroll-your-device-dep-ios).


