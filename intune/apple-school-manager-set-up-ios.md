---
title: "Konfigurowanie rejestrowania urządzeń z systemem iOS w programie Apple School Manager"
titlesuffix: Microsoft Intune
description: "Dowiedz się, jak skonfigurować rejestrację firmowych urządzeń z systemem iOS w programie Apple School Manager przy użyciu usługi Intune."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/08/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f639a61c4d481a891156383c3a23e0e1511a5fbe
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2018
---
# <a name="set-up-ios-device-enrollment-with-apple-school-manager"></a>Konfigurowanie rejestracji urządzeń z systemem iOS za pomocą usługi Apple School Manager

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

> [!NOTE]
> ### <a name="temporary-user-interface-differences"></a>Tymczasowe różnice dotyczące interfejsu użytkownika
>
>Interfejsy funkcji opisanych na tej stronie są w trakcie aktualizacji. Aktualizacje te zostaną stopniowo wprowadzone na wszystkich kontach użytkowników do końca kwietnia.
>
>Jeśli Twoja strona **Rejestracja urządzeń** wygląda jak obraz poniżej, Twoje konto nie zostało jeszcze zaktualizowane do nowego interfejsu użytkownika i można użyć tej strony pomocy.
>
>![Stary interfejs użytkownika usługi Intune](./media/appleenroll-oldui.png)
>
>Jeśli Twoja strona **Rejestracja urządzeń** wygląda jak obraz poniżej, masz zaktualizowane interfejsy użytkownika.  Przejdź do [tej strony pomocy](apple-school-manager-set-up-ios-newui.md).
>
>![Nowy interfejs użytkownika usługi Intune](./media/appleenroll-newui.png)

W tym temacie przedstawiono informacje ułatwiające skonfigurowanie rejestracji urządzeń z systemem iOS zakupionych w ramach programu [Apple School Manager](https://school.apple.com/). Korzystając z usługi Intune z programem Apple School Manager, możesz zarejestrować wiele urządzeń z systemem iOS bez ich dotykania. Gdy uczeń lub nauczyciel włączy urządzenie, Asystent ustawień zostanie uruchomiony ze wstępnie skonfigurowanymi ustawieniami, a urządzenie zostanie zarejestrowane w funkcji zarządzania.

Aby włączyć rejestrację w programie Apple School Manager, należy użyć portalu usługi Intune i portalu programu Apple School Manager. Wymagana jest lista numerów seryjnych lub numerów zamówień zakupu, która pozwala przypisać urządzenia do funkcji zarządzania usługi Intune. Możliwe jest utworzenie profilów rejestracji w ramach programu DEP zawierających ustawienia stosowane względem urządzeń podczas rejestracji.

Ponadto rejestracji w programie Apple School Manager nie można używać wraz z [programem Device Enrollment Program firmy Apple](device-enrollment-program-enroll-ios.md) ani [menedżerem rejestracji urządzeń](device-enrollment-manager-enroll.md).

**Wymagania wstępne**
- [Certyfikat wypychania MDM firmy Apple](apple-mdm-push-certificate-get.md)
- [Urząd zarządzania urządzeniami przenośnymi](mdm-authority-set.md)
- [Certyfikat wypychania MDM firmy Apple](apple-mdm-push-certificate-get.md)
- Koligacja użytkownika wymaga [nazwy użytkownika protokołu WS-Trust 1.3/mieszanego punktu końcowego](https://technet.microsoft.com/library/adfs2-help-endpoints). [Dowiedz się więcej](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
- Urządzenia zakupione w programie [Apple School Management](http://school.apple.com)

>[!NOTE]
>Uwierzytelnianie wieloskładnikowe (MFA) nie działa podczas rejestracji urządzeń korzystających z programu Apple School Manager, gdy jest używana koligacja użytkownika. Po zarejestrowaniu tych urządzeń uwierzytelnianie wieloskładnikowe działa zgodnie z oczekiwaniami. Po zarejestrowaniu usługa MFA działa zgodnie z oczekiwaniami na tych urządzeniach. Na urządzeniach nie mogą być wyświetlane monity dla użytkowników, w przypadku których wymagana jest zmiana hasła podczas pierwszego logowania. Ponadto dla użytkowników, których hasła wygasły, nie zostanie wyświetlony monit o zresetowanie hasła podczas rejestracji. Muszą oni zresetować hasło za pomocą innego urządzenia.

## <a name="get-the-apple-token-and-assign-devices"></a>Pobieranie tokenu firmy Apple i przypisywanie urządzeń

Przed zarejestrowaniem firmowych urządzeń z systemem iOS w programie Apple School Manager należy uzyskać od firmy Apple plik tokenu (p7m). Token ten umożliwia usłudze Intune synchronizację informacji dotyczących urządzeń korzystających z programu Apple School Manager. Umożliwia on również usłudze Intune przekazywanie profilów rejestracji do firmy Apple i przypisywanie urządzeń do tych profilów. W portalu firmy Apple można także przypisywać numery seryjne urządzeń do zarządzania.

**Krok 1. Pobierz certyfikat klucza publicznego usługi Intune wymagany do utworzenia tokenu firmy Apple.**<br>
1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz pozycję **Rejestrowanie urządzenia**, a następnie wybierz pozycję **Token programu Enrollment Program**.

  ![Okienko tokenu programu Enrollment Program w obszarze roboczym certyfikatów firmy Apple umożliwiające pobranie klucza publicznego](./media/enrollment-program-token-download.png)

2. W bloku **Token programu Enrollment Program** wybierz pozycję **Pobierz klucz publiczny**, aby pobrać i zapisać lokalnie plik klucza szyfrowania (pem). Plik .pem jest używany na potrzeby żądania certyfikatu relacji zaufania z portalu Apple School Manager.

**Krok 2. Pobierz token i przypisz urządzenia.**<br>
1. Wybierz pozycję **Utwórz token za pomocą usługi Apple School Manager** i zaloguj się przy użyciu identyfikatora Apple ID swojej firmy. Tego identyfikatora Apple ID można także użyć do odnowienia tokenu programu Apple School Manager.
2.  W [portalu Apple School Manager](https://school.apple.com) wybierz pozycję **MDM Servers** (Serwery MDM), a następnie wybierz **Add MDM Server** (Dodaj serwer MDM) (w prawym górnym rogu).
3.  Wypełnij pole **MDM Server Name** (Nazwa serwera MDM). Nazwa serwera służy użytkownikowi do identyfikowania serwera MDM. Nie jest to nazwa ani adres URL serwera usługi Microsoft Intune.
   ![Portal programu Apple School Manager z wybraną opcją Serial Number (Numer seryjny)](./media/asm-server-assignment.png)

4.  Wybierz pozycję **Upload File...** (Przekaż plik...) w portalu firmy Apple, przejdź do pliku pem, a następnie wybierz pozycję **Save MDM Server** (Zapisz serwer MDM) (w lewym dolnym rogu).
5.  Wybierz opcję **Get Token** (Pobierz token), a następnie pobierz na komputer plik tokenu serwera (p7m).
6. Przejdź do pozycji **Device Assignments** (Przypisania urządzeń) i **Choose Device** (Wybierz urządzenie). W tym celu wypełnij ręcznie pole **Serial Numbers** (Numery seryjne), **Order Number** (Numer zamówienia) lub **Upload CSV File** (Przekaż plik CSV).
     ![Portal programu Apple School Manager z wybraną opcją Serial Number (Numer seryjny)](./media/asm-device-assignment.png)
7.  Wybierz akcję **Assign to Server** (Przypisz do serwera) i wybierz utworzony serwer MDM (**MDM Server**).
8. Określ sposób **wyboru urządzeń**, a następnie podaj informacje i szczegóły dotyczące urządzenia.
9. Wybierz pozycję **Assign to Server** (Przypisz do serwera), wybierz nazwę serwera &lt;nazwa_serwera&gt; określoną dla usługi Microsoft Intune, a następnie kliknij przycisk **OK**.

**Krok 3. Wprowadź identyfikator Apple ID użyty do utworzenia tokenu programu Apple School Manager.**<br>Tego identyfikatora należy użyć do odnowienia tokenu programu Apple School Manager. Jest on przechowywany do użytku w przyszłości.

![Wprowadzanie identyfikatora Apple ID używanego do utworzenia tokenu programu rejestracji i przechodzenie do tokenu programu rejestracji](./media/enrollment-program-token-apple-id.png)

**Krok 4. Zlokalizuj i przekaż token.**<br>
Przejdź do pliku certyfikatu (.p7m) i wybierz pozycję **Otwórz**, a następnie wybierz pozycję **Przekaż**. Usługa Intune przeprowadzi automatyczną synchronizację urządzeń firmy Apple korzystających z programu Apple School Manager.

## <a name="create-an-apple-enrollment-profile"></a>Tworzenie profilu rejestracji firmy Apple
Profil rejestracji urządzeń określa ustawienia stosowane do grupy urządzeń podczas rejestracji.

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia**, a następnie pozycję **Rejestracja Apple**.
2. W obszarze **Enrollment Program**, wybierz pozycję **Profile programu Enrollment Program**.
3. W bloku **Profile programu Enrollment Program** wybierz pozycję **Utwórz**.
4. W bloku **Utwórz profil rejestracji** wypełnij pola **Nazwa** i **Opis** odnoszące się do profilu wyświetlanego w usłudze Intune.
5. Dla pozycji **Koligacja użytkownika** wskaż, czy urządzenia z tym profilem będą rejestrowane z koligacją użytkownika, czy bez niej.

 - **Zarejestruj z koligacją użytkownika** — tworzy koligację urządzenia z użytkownikiem podczas instalacji.

  Tryb udostępniania urządzenia iPad w programie Apple School Manager wymaga od użytkownika zarejestrowania urządzenia bez koligacji użytkownika.

 - **Zarejestruj bez koligacji użytkownika** — to ustawienie należy wybrać dla urządzenia, dla którego nie istnieje koligacja z żadnym użytkownikiem, np. dla urządzenia udostępnionego. Ma to zastosowanie w przypadku urządzeń wykonujących zadania bez uzyskiwania dostępu do danych użytkowników lokalnych. Aplikacje, takie jak Portal firmy, nie działają.

6. Wybierz pozycję **Ustawienia zarządzania urządzeniami**. Te pozycje są konfigurowane podczas aktywacji i do ich zmiany wymagane jest zresetowanie do ustawień fabrycznych. Skonfiguruj następujące ustawienia profilu, a następnie wybierz pozycję **Zapisz**:

  ![Wybieranie trybu zarządzania](./media/enrollment-program-profile-mode.png)

    - **Nadzorowane** — tryb zarządzania, w ramach którego następuje włączenie większej liczby opcji zarządzania i domyślne wyłączenie blokady aktywacji. Jeśli pole pozostanie puste, użytkownik będzie mieć ograniczone możliwości w zakresie zarządzania.

     - **Rejestracja zablokowana** — (wymaga zastosowania ustawienia Tryb zarządzania = Nadzorowane) wyłącza ustawienia systemu iOS, które umożliwiają usunięcie profilu zarządzania. W przypadku pozostawienia tego pola pustego istnieje możliwość usunięcia profilu zarządzania z poziomu menu Ustawienia.
   - **Udostępnione urządzenie iPad** — (wymaga ustawienia **Zarejestruj z koligacją użytkownika** i trybu nadzorowanego). Umożliwia wielu użytkownikom logowanie się do zarejestrowanych urządzeń iPad przy użyciu zarządzanego identyfikatora Apple ID. Zarządzane identyfikatory Apple ID tworzy się w portalu Apple School Manager. Dowiedz się więcej na temat [udostępnionego urządzenia iPad](education-settings-configure-ios-shared.md). Należy także przejrzeć [wymagania firmy Apple dotyczące udostępnionych urządzeń iPad](https://help.apple.com/classroom/ipad/2.0/#/cad7e2e0cf56).

   >[!NOTE]
   >Jeśli opcja **Koligacja użytkownika** jest ustawiona na wartość **Z koligacją użytkownika** lub tryb **Nadzorowane** jest ustawiony na wartość **Wyłączone**, tryb Udostępnione urządzenie iPad zostanie wyłączony dla profilu rejestracji.

        - **Maximum Cached Users** - (Requires **Shared iPad** = **Yes**) Creates a partition on the device for each user. The recommended value is the number of students likely to use the device over a period of time. For example, if six students use the device regularly during the week, set this number to six.  

    - **Zezwalaj na parowanie** — określa, czy urządzenia z systemem iOS można synchronizować z komputerami. W przypadku wybrania pozycji **Zezwalaj programowi Apple Configurator według certyfikatów** należy wybrać certyfikat w obszarze **Certyfikaty programu Apple Configurator**.

      - **Certyfikaty programu Apple Configurator** — w przypadku wyboru pozycji **Zezwalaj programowi Apple Configurator według certyfikatów** w obszarze **Zezwalaj na parowanie** należy wybrać certyfikat programu Apple Configurator do zaimportowania.

7. Wybierz pozycję **Ustawienia Asystenta ustawień**, skonfiguruj następujące ustawienia profilu, a następnie wybierz pozycję **Zapisz**:

    - **Nazwa działu** — jest wyświetlana, gdy użytkownik dotknie pozycji **Informacje o konfiguracji** podczas aktywacji.

    - **Telefon działu** — jest wyświetlany, gdy użytkownik kliknie podczas aktywacji przycisk Potrzebna pomoc.
    - **Opcje Asystenta ustawień** — jeśli te opcje zostaną wykluczone z obszaru opcji Asystenta ustawień, można je później skonfigurować z poziomu menu **Ustawienia** systemu iOS.
        - **Kod dostępu** — wyświetla monit o podanie kodu dostępu podczas aktywacji. Zawsze należy wymagać kodu dostępu, chyba że urządzenie zostanie zabezpieczone lub dostęp do niego będzie kontrolowany w inny sposób (tj. zostanie zastosowany tryb kiosku, który ogranicza możliwość użycia urządzenia do jednej aplikacji).
        - **Usługi lokalizacji** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący usługi podczas aktywacji
        - **Przywracanie** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit o kopię zapasową w programie iCloud podczas aktywacji
        - **Apple ID** — jeśli to ustawienie zostało włączone, system iOS wyświetli monit o podanie identyfikatora Apple ID, gdy usługa Intune będzie podejmowała próbę zainstalowania aplikacji bez tego identyfikatora. Identyfikator Apple ID jest wymagany do pobierania aplikacji ze sklepu iOS App Store, w tym aplikacji instalowanych przez usługę Intune.
        - **Warunki i postanowienia** — jeśli to ustawienie zostało włączone, Asystent ustawień monituje użytkowników o zaakceptowanie warunków i postanowień firmy Apple podczas aktywacji
        - **Touch ID** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji
        - **Apple Pay** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji
        - **Zoom** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji
        - **Siri** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji
        - **Dane diagnostyczne** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji

8. Aby zapisać ustawienia profilu, wybierz pozycję **Utwórz** w bloku **Utwórz profil rejestracji**.

## <a name="connect-school-data-sync"></a>Łączenie się z usługą School Data Sync
Opcjonalnie: program Apple School Manager obsługuje synchronizowanie danych listy uczniów z usługą Azure Active Directory (AD) przy użyciu aplikacji Microsoft School Data Sync (SDS). Wykonaj poniższe kroki, aby użyć aplikacji SDS w celu zsynchronizowania danych szkolnych.

1. W bloku **Token programu Enrollment Program** wybierz niebieski baner z informacjami lub opcję **Połącz z programem SDS**.
2. Wybierz pozycję **Zezwalaj aplikacji Microsoft School Data Sync na używanie tego tokenu** i ustaw wartość **Zezwalaj**. To ustawienie umożliwia usłudze Intune łączenie się z programem SDS w usłudze Office 365.
3. Aby włączyć połączenie między programem Apple School Manager i usługą Azure AD, wybierz opcję **Skonfiguruj aplikację Microsoft School Data Sync**. Dowiedz się więcej o [sposobie konfigurowania aplikacji School Data Sync](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1).
4. Kliknij przycisk **OK**, aby zapisać zmiany i kontynuować.

## <a name="sync-managed-devices"></a>Synchronizowanie urządzeń zarządzanych
Teraz, gdy do usługi Intune zostało przypisane uprawnienie do zarządzania urządzeniami korzystającymi z programu Apple School Manager, możliwe jest zsynchronizowanie usługi Intune z usługą firmy Apple, aby wyświetlić zarządzane urządzenia w usłudze Intune.

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Urządzenia programu Enrollment Program** > **Synchronizacja**. Pasek postępu pokazuje, ile czasu minie przed ponownym przesłaniem żądania synchronizacji.

  ![Wybrany węzeł Urządzenia programu Enrollment Program i wybierany link Synchronizuj](./media/enrollment-program-device-sync.png)
2. W bloku **synchronizacji** wybierz pozycję **Żądaj synchronizacji**. Pasek postępu pokazuje, ile czasu minie przed ponownym przesłaniem żądania synchronizacji.

  ![Blok Synchronizuj z wybranym linkiem Żądaj synchronizacji](./media/enrollment-program-device-request-sync.png)

  Aby spełnić warunki dopuszczalnego ruchu firmy Apple, usługa Intune nakłada następujące ograniczenia:
   -    Pełną synchronizację można uruchamiać nie częściej niż co siedem dni. Podczas pełnej synchronizacji usługa Intune odświeża każdy numer seryjny Apple przypisany do usługi Intune, niezależnie od tego, czy numer seryjny był już wcześniej synchronizowany. W przypadku próby przeprowadzenia pełnej synchronizacji przed upływem siedmiu dni od poprzedniej pełnej synchronizacji usługa Intune odświeża tylko numery seryjne, które jeszcze nie zostały przypisane do usługi Intune.
   -    Każde żądanie synchronizacji ma przydzielone 15 minut na zakończenie. W tym czasie lub do momentu zakończenia żądania powodzeniem przycisk **synchronizacji** jest wyłączony.

>[!NOTE]
>Można także przypisać numery seryjne urządzeń korzystających z programu Apple School Manager do profilów z poziomu bloku **Urządzenia programu Enrollment Program**.

## <a name="assign-a-profile-to-devices"></a>Przypisywanie profilu do urządzeń
Przed zarejestrowaniem urządzeń korzystających z programu Apple School Manager zarządzanych przez usługę Intune należy przypisać do nich profil rejestracji.

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple**, a następnie wybierz pozycję **Profile programu Enrollment Program**.
2. Z listy **Profile programu Enrollment Program** wybierz profil, który ma zostać przypisany do urządzeń, a następnie wybierz pozycję **Przypisania urządzeń**.

 ![Przypisania urządzeń z wybranym przyciskiem Przypisz.](./media/enrollment-program-device-assign.png)

3. Wybierz pozycję **Przypisz**, a następnie wybierz urządzenia korzystające z programu Apple School Manager, do których chcesz przypisać ten profil. Możesz zastosować filtr, aby wyświetlić dostępne urządzenia:
  - **nieprzypisane**
  - **dowolne**
  - **&lt;nazwa profilu&gt;**
4. Wybierz urządzenia, które chcesz przypisać. Pole wyboru powyżej kolumny pozwala wybrać maksymalnie 1000 wyświetlanych urządzeń. Kliknij przycisk **Przypisz**. Aby zarejestrować więcej niż 1000 urządzeń, powtarzaj procedurę przypisania, aż profil rejestracji zostanie przypisany do wszystkich urządzeń.

  ![Przycisk Przypisz służący do przypisywania profilu programu Enrollment Program w usłudze Intune](media/dep-profile-assignment.png)

## <a name="distribute-devices-to-users"></a>Przekazywanie urządzeń użytkownikom

Urządzenia firmowe mogą zostać teraz przekazane użytkownikom. Po włączeniu urządzenia z systemem iOS korzystającego z programu Apple School Manager zostanie ono zarejestrowane na potrzeby zarządzania przez usługę Intune. Jeśli urządzenie zostało aktywowane i jest używane, profilu nie można zastosować, dopóki urządzenie nie zostanie zresetowane do ustawień fabrycznych.
