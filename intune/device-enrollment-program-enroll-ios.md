---
title: "Rejestrowanie urządzeń z systemem iOS — program Device Enrollment Program"
titlesuffix: Azure portal
description: "Informacje dotyczące rejestrowania firmowych urządzeń z systemem iOS przy użyciu programu Device Enrollment Program."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a10d158816f17c7fbe07fd14172d1a9abb9ed9b9
ms.sourcegitcommit: 520eb7712625e129b781e2f2b9fe16f9b9f3d08a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/01/2017
---
# <a name="automatically-enroll-ios-devices-with-apples-device-enrollment-program"></a>Automatyczne rejestrowanie urządzeń z systemem iOS w ramach programu Device Enrollment Program

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

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

> [!NOTE]
> Usługa Multi-Factor Authentication (MFA) nie działa podczas rejestracji urządzeń w ramach programu DEP skonfigurowanej na potrzeby koligacji użytkownika. Po zarejestrowaniu usługa MFA działa zgodnie z oczekiwaniami na tych urządzeniach. Na urządzeniach nie mogą być wyświetlane monity dla użytkowników, w przypadku których wymagana jest zmiana hasła podczas pierwszego logowania. Ponadto dla użytkowników, których hasła wygasły, nie zostanie wyświetlony monit o zresetowanie hasła podczas rejestracji. Muszą oni zresetować hasło za pomocą innego urządzenia.

## <a name="get-the-apple-dep-token"></a>Pobieranie tokenu DEP firmy Apple

Aby zarejestrować urządzenia z systemem iOS w ramach programu DEP, należy uzyskać token programu DEP (plik p7m) od firmy Apple. Ten token umożliwia usłudze Intune synchronizację informacji dotyczących urządzeń korzystających z programu DEP należących do firmy. Umożliwia on również usłudze Intune przekazywanie profilów rejestracji do firmy Apple i przypisywanie urządzeń do tych profilów.

W portalu Apple DEP Portal można utworzyć token programu DEP. W tym portalu można również przypisać urządzenia do funkcji zarządzania usługi Intune.

> [!NOTE]
> Jeśli usuniesz token z portalu klasycznego usługi Intune przed migracją do usługi Azure, usługa Intune może przywrócić usunięty token DEP firmy Apple. Możesz ponownie usunąć token programu DEP z poziomu witryny Azure Portal. Możesz ponownie usunąć token programu DEP z poziomu witryny Azure Portal.

**Krok 1. Pobierz certyfikat klucza publicznego usługi Intune wymagany do utworzenia tokenu DEP firmy Apple.**<br>

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Token programu Enrollment Program**.

  ![Zrzut ekranu przedstawiający okienko tokenu programu Enrollment Program w obszarze roboczym certyfikatów firmy Apple.](./media/enrollment-program-token-add.png)

2. Wybierz pozycję **Pobierz klucz publiczny**, aby pobrać i zapisać lokalnie plik klucza szyfrowania (PEM). Plik PEM jest używany na potrzeby żądania certyfikatu relacji zaufania z portalu programu Device Enrollment Program firmy Apple.

  ![Zrzut ekranu przedstawiający okienko tokenu programu Enrollment Program w obszarze roboczym certyfikatów firmy Apple umożliwiające pobranie klucza publicznego.](./media/enrollment-program-token-download.png)

**Krok 2. Utwórz i pobierz token DEP firmy Apple.**<br>
1. Wybierz pozycję **Utwórz token za pomocą programu Device Enrollment Program firmy Apple**, aby otworzyć portal programu wdrażania firmy Apple i zalogować się przy użyciu firmowego identyfikatora Apple ID. Tego identyfikatora firmy Apple możesz użyć do odnowienia tokenu DEP.
2.  W [portalu programów wdrażania](https://deploy.apple.com) firmy Apple wybierz pozycję **Get Started** (Rozpocznij) dla opcji **Device Enrollment Program**.

3. Na stronie **Manage Servers** (Zarządzanie serwerami) wybierz pozycję **Add MDM Server** (Dodaj serwer MDM).
4. Wprowadź nazwę serwera w polu **MDM Server Name** (Nazwa serwera MDM), a następnie wybierz przycisk **Next**(Dalej). Nazwa serwera służy użytkownikowi do identyfikowania serwera MDM. Nie jest to nazwa ani adres URL serwera usługi Microsoft Intune.

   ![Zrzut ekranu przedstawiający dodawanie nazwy serwera MDM dla programu DEP, a następnie klikanie przycisku Next (Dalej).](./media/enrollment-program-token-add-server.png)

5. Zostanie otwarte okno dialogowe **Add &lt;nazwa_serwera&gt;** (Dodawanie serwera <nazwa_serwera>) z widocznym komunikatem **Upload Your Public Key** (Przekaż klucz publiczny). Kliknij pozycję **Choose File…** (Wybierz plik...) w celu przekazania pliku PEM, a następnie kliknij przycisk **Next** (Dalej).


7. Wybierz kolejno pozycje **Deployment Programs** (Programy wdrażania)&gt; **Device Enrollment Program** (Program rejestracji urządzeń) &gt; **Manage Devices** (Zarządzaj urządzeniami).
8. W obszarze **Choose Devices By** (Sposób wybierania urządzeń) określ sposób identyfikowania urządzeń:
    - **Serial Number** (Numer seryjny)
    - **Order Number** (Numer zamówienia)
    - **Upload CSV File** (Przekaż plik CSV).

   ![Zrzut ekranu przedstawiający wybraną opcję wybierania urządzeń według numerów seryjnych, akcję po wybraniu ustawioną jako przypisywanie do serwera oraz wybraną nazwę serwera.](./media/enrollment-program-token-specify-serial.png)

9. W kroku **Choose Action** (Wybierz akcję) wybierz pozycję **Assign to Server** (Przypisz do serwera), wybierz &lt;nazwę serwera&gt; określoną dla usługi Microsoft Intune, a następnie kliknij przycisk **OK**. Portal firmy Apple przypisze wskazane urządzenia do funkcji zarządzania na serwerze Intune, a następnie wyświetli komunikat **Assignment Complete** (Przypisanie zostało ukończone).

   W portalu firmy Apple wybierz pozycję **Deployment Programs** (Programy wdrażania) &gt; **Device Enrollment Program** &gt; **View Assignment History** (Wyświetl historię przypisania), aby wyświetlić listę urządzeń i ich przypisania do serwera MDM.

**Krok 3. Wprowadź identyfikator Apple ID użyty do utworzenia tokenu programu rejestracji.**<br>W usłudze Intune w witrynie Azure Portal podaj identyfikator Apple ID do użytku w przyszłości. Ten identyfikator umożliwia odnowienie tokenu programu rejestracji w przyszłości bez potrzeby ponownego rejestrowania wszystkich urządzeń.

![Zrzut ekranu przedstawiający wprowadzanie identyfikatora Apple ID używanego do utworzenia tokenu programu rejestracji i przechodzenie do tokenu programu rejestracji.](./media/enrollment-program-token-apple-id.png)

**Krok 4. Przechodzenie do tokenu programu rejestracji w celu jego przekazania.**<br>
Przejdź do pliku certyfikatu (.pem) i wybierz pozycję **Otwórz**, a następnie wybierz pozycję **Przekaż**. Dzięki certyfikatowi wypychania usługa Intune może rejestrować urządzenia z systemem iOS i zarządzać nimi, wypychając zasady do zarejestrowanych urządzeń przenośnych. Usługa Intune automatycznie synchronizuje dane z firmą Apple, co pozwala wyświetlić konto programu rejestracji.

## <a name="create-an-apple-enrollment-profile"></a>Tworzenie profilu rejestracji firmy Apple

Teraz, po zainstalowaniu tokenu, możesz utworzyć profil rejestracji dla urządzeń korzystających z programu DEP. Profil rejestracji urządzeń określa ustawienia stosowane do grupy urządzeń podczas rejestracji.

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple**.
2. W obszarze **Program Enrollment Program dla firmy Apple** wybierz pozycję **Profile programu Enrollment Program** > **Utwórz**.
3. W obszarze **Utwórz profil rejestracji** wprowadź nazwę w polu **Nazwa** i opis w polu **Opis** dotyczące profilu do celów administracyjnych. Te szczegóły nie są widoczne dla użytkowników. Możesz użyć pola **Nazwa**, aby utworzyć grupę dynamiczną w usłudze Azure Active Directory. Nazwa profilu umożliwia zdefiniowanie parametru enrollmentProfileName w celu przypisania urządzeń z tym profilem rejestracji. Dowiedz się więcej o [grupach dynamicznych usługi Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects).

  Dla pozycji **Koligacja użytkownika** wybierz, czy urządzenia z tym profilem będą rejestrowane z przypisanym użytkownikiem, czy bez niego.

 - **Zarejestruj z koligacją użytkownika** — to ustawienie należy wybrać w przypadku urządzeń należących do użytkowników, które muszą korzystać z Portalu firmy na potrzeby usług, takich jak instalowanie aplikacji. Koligacja użytkownika wymaga [nazwy użytkownika protokołu WS-Trust 1.3/mieszanego punktu końcowego](https://technet.microsoft.com/library/adfs2-help-endpoints). [Dowiedz się więcej](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Zarejestruj bez koligacji użytkownika** — to ustawienie należy wybrać dla urządzenia, dla którego nie istnieje koligacja z żadnym użytkownikiem. Ma to zastosowanie w przypadku urządzeń wykonujących zadania bez uzyskiwania dostępu do danych użytkowników lokalnych. Aplikacje, takie jak Portal firmy, nie działają.

4. Wybierz pozycję **Ustawienia zarządzania urządzeniami**, aby skonfigurować następujące ustawienia profilu:

  ![Zrzut ekranu przedstawiający wybór trybu zarządzania. Urządzenie ma następujące ustawienia: nadzorowane, zablokowana rejestracja, zezwalanie na parowanie ustawione na odrzucanie wszystkiego. Pozycja certyfikatów programu Apple Configurator jest wyszarzona dla nowego profilu rejestracji programu.](./media/enrollment-program-profile-mode.png)
    - **Nadzorowane** — tryb zarządzania, w ramach którego następuje włączenie większej liczby opcji zarządzania i domyślne wyłączenie blokady aktywacji. Jeśli pole pozostanie puste, użytkownik będzie mieć ograniczone możliwości w zakresie zarządzania. Firma Microsoft zaleca używanie programu DEP jako mechanizmu włączania trybu nadzorowanego, szczególnie w przypadku organizacji, które wdrażają dużą liczbę urządzeń z systemem iOS.

 > [!NOTE]
 > Konfigurowania urządzenia dla trybu nadzorowanego nie można wykonać przy użyciu usługi Intune po zarejestrowaniu urządzenia. Po rejestracji jedynym sposobem włączenia trybu nadzorowanego jest podłączenie urządzenia z systemem iOS do komputera Mac za pomocą kabla USB i użycie narzędzia Apple Configurator. Spowoduje to zresetowanie urządzenia i skonfigurowanie go w trybie nadzorowanym. Dowiedz się więcej na ten temat w [dokumentacji programu Apple Configurator](http://help.apple.com/configurator/mac/2.3). Nadzorowane urządzenie wyświetli komunikat „Ten telefon iPhone jest zarządzany przez firmę Contoso” na ekranie blokady oraz „Ten telefon iPhone jest nadzorowany. Firma Contoso może monitorować Twój ruch w Internecie i lokalizować to urządzenie” w pozycji **Ustawienia** > **Ogólne** > **Informacje**.

    - **Rejestracja zablokowana** — (wymaga zastosowania ustawienia Tryb zarządzania = Nadzorowane) wyłącza ustawienia systemu iOS, które umożliwiają usunięcie profilu zarządzania. W przypadku pozostawienia tego pola pustego istnieje możliwość usunięcia profilu zarządzania z poziomu menu Ustawienia. Po rejestracji urządzenia nie można zmienić tego ustawienia bez resetowania urządzenia do ustawień fabrycznych.

  - **Włącz udostępnione urządzenie iPad** — program Device Enrollment Program firmy Apple nie obsługuje udostępnionego urządzenia iPad.

    - **Zezwalaj na parowanie** — określa, czy urządzenia z systemem iOS można synchronizować z komputerami. W przypadku wybrania pozycji **Zezwalaj programowi Apple Configurator według certyfikatów** należy wybrać certyfikat w obszarze **Certyfikaty programu Apple Configurator**.

    - **Certyfikaty programu Apple Configurator** — w przypadku wyboru pozycji **Zezwalaj programowi Apple Configurator według certyfikatów** w obszarze **Zezwalaj na parowanie** należy wybrać certyfikat programu Apple Configurator do zaimportowania.

  Wybierz polecenie **Zapisz**.

5. Wybierz pozycję **Ustawienia Asystenta ustawień**, aby skonfigurować następujące ustawienia profilu:

  ![Zrzut ekranu przedstawiający wybór ustawień konfiguracji z dostępnymi ustawieniami dla nowego profilu rejestracji programu.](./media/enrollment-program-profile-settings.png)
    - **Nazwa działu** — jest wyświetlana, gdy użytkownik dotknie pozycji **Informacje o konfiguracji** podczas aktywacji.

    - **Telefon działu** — jest wyświetlany, gdy użytkownik kliknie podczas aktywacji przycisk **Potrzebna pomoc**.
    - **Opcje Asystenta ustawień** — te opcjonalne ustawienia mogą być później konfigurowane z poziomu menu **Ustawienia** systemu iOS.
        - **Kod dostępu**
        - **Usługi lokalizacyjne**
        - **Przywróć**
        - **Identyfikator firmy Apple**
        - **Warunki i postanowienia**
        - **Touch ID**
        - **Apple Pay**
        - **Powiększenie**
        - **Siri**
        - **Dane diagnostyczne**

    Wybierz polecenie **Zapisz**.

9. Aby zapisać ustawienia profilu, wybierz pozycję **Utwórz** w bloku **Utwórz profil rejestracji**. Profil rejestracji zostanie wyświetlony na liście Profile rejestracji programu Enrollment Program firmy Apple.

## <a name="sync-managed-devices"></a>Synchronizowanie urządzeń zarządzanych
Gdy usługa Intune ma uprawnienia do zarządzania urządzeniami, można ją zsynchronizować z danymi firmy Apple, aby wyświetlić zarządzane urządzenia w usłudze Intune w witrynie Azure Portal.

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Urządzenia programu Enrollment Program** > **Synchronizacja**. Pasek postępu pokazuje, ile czasu minie przed ponownym przesłaniem żądania synchronizacji.

  ![Zrzut ekranu przedstawiający wybrany węzeł Urządzenia programu Enrollment Program i wybierany link Synchronizuj.](./media/enrollment-program-device-sync.png)
  
2. W bloku **synchronizacji** wybierz pozycję **Żądaj synchronizacji**. Pasek postępu pokazuje, ile czasu minie przed ponownym przesłaniem żądania synchronizacji.

  ![Zrzut ekranu przedstawiający blok Synchronizuj i wybierany link Żądaj synchronizacji.](./media/enrollment-program-device-request-sync.png)

  Aby spełnić warunki firmy Apple dotyczące ruchu w programie rejestracji, usługa Intune nakłada następujące ograniczenia:
     -  Pełną synchronizację można uruchamiać nie częściej niż co siedem dni. Podczas pełnej synchronizacji usługa Intune odświeża każdy numer seryjny Apple przypisany do usługi Intune. W przypadku próby przeprowadzenia pełnej synchronizacji przed upływem siedmiu dni od poprzedniej pełnej synchronizacji usługa Intune odświeża tylko numery seryjne, które jeszcze nie zostały przypisane do usługi Intune.
     -  Każde żądanie synchronizacji ma przydzielone 15 minut na zakończenie. W tym czasie lub do momentu zakończenia żądania powodzeniem przycisk **synchronizacji** jest wyłączony.
     - Usługa Intune co 24 godziny synchronizuje z firmą Apple urządzenia nowe i usunięte.

3. W obszarze roboczym Urządzenia programu Enrollment Program wybierz pozycję **Odśwież**, aby wyświetlić urządzenia.

## <a name="assign-an-enrollment-profile-to-devices"></a>Przypisywanie profilu rejestracji do urządzeń
Zanim możliwe będzie rejestrowanie urządzeń, należy przypisać profil programu rejestracji.

>[!NOTE]
>Możesz także przypisać numery seryjne do profilów w bloku **Numery seryjne Apple**.

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple**, a następnie wybierz pozycję **Profile programu Enrollment Program**.
2. Z listy **Profile programu Enrollment Program** wybierz profil, który ma zostać przypisany do urządzeń, a następnie wybierz pozycję **Przypisz urządzenia**.

 ![Zrzut ekranu z przypisaniami urządzeń z wybranym przyciskiem Przypisz.](./media/enrollment-program-device-assign.png)

3. Wybierz przycisk **Przypisz**, a następnie wybierz urządzenia, do których chcesz przypisać ten profil. Możesz zastosować filtr, aby wyświetlić dostępne urządzenia:
  - **nieprzypisane**
  - **dowolne**
  - **&lt;nazwa profilu&gt;**
4. Wybierz urządzenia, które chcesz przypisać. Pole wyboru nad kolumną pozwala na wybranie z listy maksymalnie 1000 urządzeń. Po wybraniu urządzeń kliknij przycisk **Przypisz**. Aby zarejestrować więcej niż 1000 urządzeń, powtarzaj procedurę przypisania, aż profil rejestracji zostanie przypisany do wszystkich urządzeń.

  ![Zrzut ekranu przedstawiający przycisk Przypisz służący do przypisywania profilu programu Enrollment Program w usłudze Intune](media/dep-profile-assignment.png)

## <a name="distribute-devices"></a>Dystrybuowanie urządzeń
Włączono zarządzanie i synchronizację między danymi firmy Apple i usługą Intune oraz przypisano profil umożliwiający rejestrowanie urządzeń korzystających z programu DEP. Możesz teraz przekazać urządzenia użytkownikom. W przypadku urządzeń z koligacją użytkownika wymagane jest, aby poszczególni użytkownicy mieli przypisane licencje na korzystanie z usługi Intune. Urządzenia bez koligacji użytkownika wymagają licencji urządzenia. Aktywowane urządzenie nie może stosować profilu rejestracji, dopóki urządzenie nie zostanie zresetowane do ustawień fabrycznych.

Zobacz [Rejestracja urządzenia z systemem iOS przy użyciu programu Device Enrollment Program](/intune-user-help/enroll-your-device-dep-ios).
