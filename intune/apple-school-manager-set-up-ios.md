---
title: Konfigurowanie rejestrowania urządzeń z systemem iOS w programie Apple School Manager
titleSuffix: Microsoft Intune
description: Dowiedz się, jak skonfigurować rejestrację firmowych urządzeń z systemem iOS w programie Apple School Manager przy użyciu usługi Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4c35a23e-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2d099d049892d71c36e4b01fb1a8af6f7ad25df1
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2018
ms.locfileid: "43313413"
---
# <a name="enable-ios-device-enrollment-with-apple-school-manager"></a>Włączanie rejestracji urządzeń z systemem iOS za pomocą usługi Apple School Manager

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W tym artykule przedstawiono informacje ułatwiające włączenie rejestracji urządzeń z systemem iOS zakupionych w ramach programu [Apple School Manager](https://school.apple.com/). Korzystając z usługi Intune z programem Apple School Manager, możesz zarejestrować wiele urządzeń z systemem iOS bez ich dotykania. Gdy uczeń lub nauczyciel włączy urządzenie, Asystent ustawień zostanie uruchomiony ze wstępnie skonfigurowanymi ustawieniami, a urządzenie zostanie zarejestrowane w funkcji zarządzania.

Aby włączyć rejestrację w programie Apple School Manager, należy użyć portalu usługi Intune i portalu programu Apple School Manager. Wymagana jest lista numerów seryjnych lub numerów zamówień zakupu, która pozwala przypisać urządzenia do funkcji zarządzania usługi Intune. Możliwe jest utworzenie profilów rejestracji w ramach programu DEP zawierających ustawienia stosowane względem urządzeń podczas rejestracji.

Rejestracji w programie Apple School Manager nie można używać wraz z [programem Device Enrollment Program firmy Apple](device-enrollment-program-enroll-ios.md) ani [menedżerem rejestracji urządzeń](device-enrollment-manager-enroll.md).

**Wymagania wstępne**
- [Certyfikat wypychania MDM firmy Apple](apple-mdm-push-certificate-get.md)
- [Urząd zarządzania urządzeniami przenośnymi](mdm-authority-set.md)
- [Certyfikat wypychania MDM firmy Apple](apple-mdm-push-certificate-get.md)
- W przypadku korzystania z usług ADFS koligacja użytkownika wymaga [nazwy użytkownika protokołu WS-Trust 1.3/mieszanego punktu końcowego](https://technet.microsoft.com/library/adfs2-help-endpoints). [Dowiedz się więcej](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
- Urządzenia zakupione w programie [Apple School Management](http://school.apple.com)

## <a name="get-an-apple-token-and-assign-devices"></a>Uzyskiwanie tokenu od firmy Apple i przypisywanie urządzeń

Przed zarejestrowaniem firmowych urządzeń z systemem iOS w programie Apple School Manager należy uzyskać od firmy Apple plik tokenu (p7m). Token ten umożliwia usłudze Intune synchronizację informacji dotyczących urządzeń korzystających z programu Apple School Manager. Umożliwia on również usłudze Intune przekazywanie profilów rejestracji do firmy Apple i przypisywanie urządzeń do tych profilów. W portalu firmy Apple można także przypisywać numery seryjne urządzeń do zarządzania.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-an-apple-token"></a>Krok 1. Pobierz certyfikat klucza publicznego usługi Intune wymagany do utworzenia tokenu firmy Apple

1. W usłudze [Intune](https://aka.ms/intuneportal) wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > **Dodaj**.

   ![Pobierz token programu rejestracji.](./media/device-enrollment-program-enroll-ios/image01.png)

2. W bloku **Token programu Enrollment Program** wybierz pozycję **Pobierz klucz publiczny**, aby pobrać i zapisać lokalnie plik klucza szyfrowania (pem). Plik .pem jest używany na potrzeby żądania certyfikatu relacji zaufania z portalu Apple School Manager.
     ![Blok Token programu rejestracji.](./media/device-enrollment-program-enroll-ios/image02.png)

### <a name="step-2-download-a-token-and-assign-devices"></a>Krok 2. Pobierz token i przypisz urządzenia
1. Wybierz pozycję **Utwórz token za pomocą usługi Apple School Manager** i zaloguj się do programu Apple School przy użyciu identyfikatora Apple ID swojej firmy. Tego identyfikatora Apple ID można także użyć do odnowienia tokenu programu Apple School Manager.
2.  W [portalu Apple School Manager](https://school.apple.com) wybierz pozycję **MDM Servers** (Serwery MDM), a następnie wybierz **Add MDM Server** (Dodaj serwer MDM) (w prawym górnym rogu).
3.  Wypełnij pole **MDM Server Name** (Nazwa serwera MDM). Nazwa serwera służy użytkownikowi do identyfikowania serwera MDM. Nie jest to nazwa ani adres URL serwera usługi Microsoft Intune.
   ![Zrzut ekranu portalu programu Apple School Manager z wybraną opcją Serial Number (Numer seryjny)](./media/asm-server-assignment.png)

4.  Wybierz pozycję **Upload File...** (Przekaż plik...) w portalu firmy Apple, przejdź do pliku pem, a następnie wybierz pozycję **Save MDM Server** (Zapisz serwer MDM) (w lewym dolnym rogu).
5.  Wybierz opcję **Get Token** (Pobierz token), a następnie pobierz na komputer plik tokenu serwera (p7m).
6. Przejdź do pozycji **Device Assignments** (Przypisania urządzeń) i **Choose Device** (Wybierz urządzenie). W tym celu wypełnij ręcznie pole **Serial Numbers** (Numery seryjne), **Order Number** (Numer zamówienia) lub **Upload CSV File** (Przekaż plik CSV).
     ![Zrzut ekranu portalu programu Apple School Manager z wybraną opcją Serial Number (Numer seryjny)](./media/asm-device-assignment.png)
7.  Wybierz akcję **Assign to Server** (Przypisz do serwera) i wybierz utworzony serwer MDM (**MDM Server**).
8. Określ sposób **wyboru urządzeń**, a następnie podaj informacje i szczegóły dotyczące urządzenia.
9. Wybierz pozycję **Assign to Server** (Przypisz do serwera), wybierz nazwę serwera &lt;nazwa_serwera&gt; określoną dla usługi Microsoft Intune, a następnie kliknij przycisk **OK**.

### <a name="step-3-save-the-apple-id-used-to-create-this-token"></a>Krok 3. Zapisz identyfikator Apple ID użyty do utworzenia tokenu

W usłudze Intune w witrynie Azure Portal podaj identyfikator Apple ID do użytku w przyszłości.

![Zrzut ekranu przedstawiający wprowadzanie identyfikatora Apple ID używanego do utworzenia tokenu programu rejestracji i przechodzenie do tokenu programu rejestracji.](./media/device-enrollment-program-enroll-ios/image03.png)

### <a name="step-4-upload-your-token"></a>Krok 4. Przekazywanie tokenu
W polu **Token Apple** przejdź do pliku certyfikatu (.pem), wybierz pozycję **Otwórz**, a następnie kliknij **Utwórz**. Dzięki certyfikatowi wypychania usługa Intune może rejestrować urządzenia z systemem iOS i zarządzać nimi, wypychając zasady do zarejestrowanych urządzeń przenośnych. Usługa Intune przeprowadzi automatyczną synchronizację urządzeń firmy Apple korzystających z programu Apple School Manager.

## <a name="create-an-apple-enrollment-profile"></a>Tworzenie profilu rejestracji firmy Apple
Gdy token jest zainstalowany, możesz utworzyć profil rejestracji dla urządzeń korzystających z programu Apple School. Profil rejestracji urządzeń określa ustawienia stosowane do grupy urządzeń podczas rejestracji.

1. W usłudze [Intune](https://aka.ms/intuneportal) wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji**.
2. Wybierz token, wybierz pozycję **Profile**, a następnie wybierz pozycję **Utwórz profil**.

3. W obszarze **Utwórz profil** wprowadź nazwę w polu **Nazwa** i opis w polu **Opis**. Informacje te będą używane do celów administracyjnych. Te szczegóły nie są widoczne dla użytkowników. Możesz użyć pola **Nazwa**, aby utworzyć grupę dynamiczną w usłudze Azure Active Directory. Nazwa profilu umożliwia zdefiniowanie parametru enrollmentProfileName w celu przypisania urządzeń z tym profilem rejestracji. Dowiedz się więcej o [grupach dynamicznych usługi Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects).

    ![Nazwa i opis profilu.](./media/device-enrollment-program-enroll-ios/image05.png)

4. Dla pozycji **Koligacja użytkownika** wybierz, czy urządzenia z tym profilem muszą być rejestrowane z przypisanym użytkownikiem, czy bez niego.
    - **Zarejestruj z koligacją użytkownika** — tę opcję należy wybrać w przypadku urządzeń należących do użytkowników, które chcą korzystać z Portalu firmy na potrzeby usług takich jak instalowanie aplikacji. Ta opcja umożliwia również uwierzytelnianie urządzeń przy użyciu aplikacji Portal firmy. W przypadku korzystania z usług ADFS koligacja użytkownika wymaga [nazwy użytkownika protokołu WS-Trust 1.3/mieszanego punktu końcowego](https://technet.microsoft.com/library/adfs2-help-endpoints). [Dowiedz się więcej](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).   Tryb udostępniania urządzenia iPad w programie Apple School Manager wymaga od użytkownika zarejestrowania urządzenia bez koligacji użytkownika.

    - **Zarejestruj bez koligacji użytkownika** — tę opcję należy wybrać dla urządzeń, dla których nie istnieje koligacja z żadnym użytkownikiem, np. dla urządzenia udostępnionego. Tej opcji można używać dla urządzeń, które wykonują zadania bez uzyskiwania dostępu do lokalnych danych użytkowników. Aplikacje, takie jak Portal firmy, nie działają.

5. Jeśli została wybrana opcja **Zarejestruj z użyciem koligacji użytkowników**, można zezwolić użytkownikom na uwierzytelnianie za pomocą aplikacji Portal firmy zamiast Asystenta ustawień firmy Apple.

    ![Uwierzytelnianie za pomocą aplikacji Portal firmy.](./media/device-enrollment-program-enroll-ios/authenticatewithcompanyportal.png)

    > [!NOTE]
    > Jeśli chcesz wykonać dowolną z następujących czynności, w pozycji **Uwierzytelnij za pomocą aplikacji Portal firmy zamiast Asystenta konfiguracji firmy Apple** ustaw wartość **Tak**.
    >    - Używanie uwierzytelniania wieloskładnikowego
    >    - wyświetlanie monitów dla użytkowników, w przypadku których wymagana jest zmiana hasła podczas pierwszego logowania.
    >    - Monitowanie użytkowników o zresetowanie ich wygasłych haseł podczas rejestracji
    >
    > Nie są one obsługiwane w przypadku uwierzytelniania przy użyciu asystenta ustawień firmy Apple.

6. Wybierz pozycję **Ustawienia zarządzania urządzeniami** i określ, czy chcesz, żeby urządzenia korzystające z tego profilu były nadzorowane.
    W przypadku urządzeń **nadzorowanych** dostępnych jest więcej opcji zarządzania, a blokada aktywacji jest domyślnie wyłączona. Firma Microsoft zaleca używanie programu DEP jako mechanizmu włączania trybu nadzorowanego, szczególnie w przypadku organizacji, które wdrażają dużą liczbę urządzeń z systemem iOS.

    Użytkownicy są powiadamiani o tym, że ich urządzenia są nadzorowane, na dwa sposoby:

   - Na ekranie blokady jest wyświetlany komunikat: „Ten iPhone jest zarządzany przez firmę Contoso”.
   - Na ekranie **Ustawienia** > **Ogólne** > **Informacje** jest wyświetlany komunikat: „Ten iPhone jest nadzorowany. Firma Contoso może monitorować Twój ruch w Internecie i lokalizować to urządzenie”

     > [!NOTE]
     > Urządzenie zarejestrowane bez nadzoru można zresetować do nadzorowanego tylko przy użyciu programu Apple Configurator. Zresetowanie urządzenia w ten sposób wymaga podłączenia urządzenia z systemem iOS do komputera Mac za pomocą kabla USB. Dowiedz się więcej na ten temat w [dokumentacji programu Apple Configurator](http://help.apple.com/configurator/mac/2.3).

7. Wybierz, czy chcesz ustawić rejestrację zablokowaną dla urządzeń używających tego profilu. **Rejestracja zablokowana** wyłącza ustawienia systemu iOS, które umożliwiają usunięcie profilu zarządzania w menu **Ustawienia**. Po rejestracji urządzenia nie można zmienić tego ustawienia bez wyczyszczenia danych z urządzenia. Takie urządzenia muszą mieć ustawiony tryb zarządzania **Nadzorowane** na *Tak*. 

8. Jeśli chcesz umożliwić wielu użytkownikom logowanie się na zarejestrowanych urządzeniach iPad za pomocą zarządzanego identyfikatora Apple Id, wybierz pozycję **Tak** w obszarze **Udostępnione urządzenie iPad** (ta opcja wymaga ustawienia pozycji **Zarejestruj bez koligacji użytkownika** i trybu **Nadzorowane** na **Tak**). Zarządzane identyfikatory Apple ID tworzy się w portalu Apple School Manager. Dowiedz się więcej na temat [udostępnionego urządzenia iPad](education-settings-configure-ios-shared.md) i [wymagań dotyczących udostępnionego urządzenia iPad firmy Apple](https://help.apple.com/classroom/ipad/2.0/#/cad7e2e0cf56).

9. Wybierz, czy chcesz, aby urządzenia korzystające z tego profilu mogły **synchronizować się z komputerami**. W przypadku wybrania pozycji **Zezwalaj programowi Apple Configurator według certyfikatów** należy wybrać certyfikat w obszarze **Certyfikaty programu Apple Configurator**.

10. W przypadku wybrania opcji **Zezwalaj programowi Apple Configurator według certyfikatów** w poprzednim kroku wybierz certyfikat programu Apple Configurator do zaimportowania.

11. Wybierz przycisk **OK**.

12. Wybierz pozycję **Ustawienia Asystenta ustawień**, aby skonfigurować następujące ustawienia profilu: ![Dostosowanie Asystenta ustawień.](./media/device-enrollment-program-enroll-ios/setupassistantcustom.png)


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


13. Wybierz przycisk **OK**.

14. Abu zapisać profil, wybierz pozycję **Utwórz**.

## <a name="connect-school-data-sync"></a>Łączenie się z usługą School Data Sync
Opcjonalnie: program Apple School Manager obsługuje synchronizowanie danych listy uczniów z usługą Azure Active Directory (AD) przy użyciu aplikacji Microsoft School Data Sync (SDS). Z aplikacją SDS można zsynchronizować tylko jeden token. Jeśli z programem School Data Sync skonfigurujesz inny token, SDS zostanie usunięty z tokenu, który wcześniej go obejmował. Nowe połączenie spowoduje zastąpienie bieżącego tokenu. Wykonaj poniższe kroki, aby użyć aplikacji SDS w celu zsynchronizowania danych szkolnych.

1. W usłudze [Intune](https://aka.ms/intuneportal) wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji**.
2. Wybierz token programu Apple School Manager, a następnie wybierz opcję **School Data Sync**.
3. W obszarze **School Data Sync** wybierz pozycję **Zezwalaj**. To ustawienie umożliwia usłudze Intune łączenie się z programem SDS w usłudze Office 365.
4. Aby włączyć połączenie między programem Apple School Manager i usługą Azure AD, wybierz opcję **Skonfiguruj aplikację Microsoft School Data Sync**. Dowiedz się więcej o [sposobie konfigurowania aplikacji School Data Sync](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1).
5. Kliknij kolejno **Zapisz** > **OK**.

## <a name="sync-managed-devices"></a>Synchronizowanie urządzeń zarządzanych

Gdy do usługi Intune zostało przypisane uprawnienie do zarządzania urządzeniami korzystającymi z programu Apple School Manager, zsynchronizuj usługę Intune z usługą firmy Apple, aby wyświetlić zarządzane urządzenia w usłudze Intune.

W usłudze [Intune](https://aka.ms/intuneportal) wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > wybierz token z listy > **Urządzenia** > **Synchronizuj**. ![Zrzut ekranu przedstawiający wybrany węzeł Urządzenia programu Enrollment Program i wybierany link Synchronizuj.](./media/device-enrollment-program-enroll-ios/image06.png)

  Aby spełnić warunki firmy Apple dotyczące ruchu w programie rejestracji, usługa Intune nakłada następujące ograniczenia:
  - Pełną synchronizację można uruchamiać nie częściej niż co siedem dni. Podczas pełnej synchronizacji usługa Intune odświeża każdy numer seryjny Apple przypisany do usługi Intune. W przypadku próby przeprowadzenia pełnej synchronizacji przed upływem siedmiu dni od poprzedniej pełnej synchronizacji usługa Intune odświeża tylko numery seryjne, które jeszcze nie zostały przypisane do usługi Intune.
  - Każde żądanie synchronizacji ma przydzielone 15 minut na zakończenie. W tym czasie lub do momentu zakończenia żądania powodzeniem przycisk **synchronizacji** jest wyłączony.
  - Usługa Intune co 24 godziny synchronizuje z firmą Apple urządzenia nowe i usunięte.

>[!NOTE]
>Można także przypisać numery seryjne urządzeń korzystających z programu Apple School Manager do profilów z poziomu bloku **Urządzenia programu Enrollment Program**.

## <a name="assign-a-profile-to-devices"></a>Przypisywanie profilu do urządzeń
Przed zarejestrowaniem urządzeń korzystających z programu Apple School Manager zarządzanych przez usługę Intune należy przypisać do nich profil rejestracji.

1. W usłudze [Intune](https://aka.ms/intuneportal) wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > wybierz token z listy.
2. Wybierz **Urządzenia** > wybierz urządzenia na liście > **Przypisz profil**.
3. W obszarze **Przypisz profil** wybierz profil dla urządzeń, a następnie wybierz pozycję **Przypisz**.

## <a name="distribute-devices-to-users"></a>Przekazywanie urządzeń użytkownikom

Włączono zarządzanie i synchronizację między danymi firmy Apple i usługą Intune oraz przypisano profil umożliwiający rejestrowanie urządzeń korzystających z programu Apple School. Możesz teraz przekazać urządzenia użytkownikom. Po włączeniu urządzenia z systemem iOS korzystającego z programu Apple School Manager zostanie ono zarejestrowane na potrzeby zarządzania przez usługę Intune. Jeśli urządzenie zostało aktywowane i jest używane, profilu nie można zastosować, dopóki urządzenie nie zostanie wyczyszczone.
