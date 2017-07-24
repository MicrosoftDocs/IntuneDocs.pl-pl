---
title: "Rejestrowanie urządzeń z systemem iOS — program Device Enrollment Program"
titleSuffix: Intune on Azure
description: "Informacje dotyczące rejestrowania firmowych urządzeń z systemem iOS przy użyciu programu Device Enrollment Program."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 654a19dd6f1e5f4fd2bda771b0df95b87944db75
ms.sourcegitcommit: 2a6ad3c233d15a9fb441362105f64b2bdd550c34
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/13/2017
---
# <a name="set-up-ios-device-enrollment-with-device-enrollment-program"></a>Konfigurowanie rejestracji urządzeń z systemem iOS przy użyciu programu Device Enrollment Program

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ten temat ułatwia administratorom IT włączenie rejestracji urządzeń z systemem iOS dla urządzeń zakupionych w ramach programu [Device Enrollment Program (DEP)](https://deploy.apple.com) firmy Apple. Usługa Microsoft Intune pozwala bezprzewodowo wdrożyć profil rejestracji na urządzeniach zakupionych w ramach programu DEP. Administrator nie musi zbliżać się do żadnego z zarządzanych urządzeń. Profil DEP zawiera ustawienia zarządzania, w tym opcje Asystenta ustawień, które są stosowane do urządzeń podczas rejestracji.

Włączenie rejestracji w programie DEP wymaga użycia zarówno portalu usługi Intune, jak i portalu DEP firmy Apple. Wymagana jest również lista identyfikatorów lub numerów zamówień zakupu, która pozwala przypisać te urządzenia do funkcji zarządzania usługi Intune w portalu firmy Apple.

>[!NOTE]
>Rejestracji DEP nie można używać razem z [menedżerem rejestracji urządzeń](device-enrollment-manager-enroll.md).

**Instrukcje włączania programów rejestracji firmy Apple**
1. [Pobieranie tokenu DEP firmy Apple i przypisywanie urządzeń](#get-the-apple-dep-token)
2. [Tworzenie profilu rejestracji](#create-an-apple-enrollment-profile)
3. [Synchronizowanie urządzeń zarządzanych w programie DEP](#sync-managed-device)
4. [Przypisywanie profilu usługi DEP do urządzeń](#assign-an-enrollment-profile-to-devices)
5. [Przekazywanie urządzeń użytkownikom](#end-user-experience-with-managed-devices)

## <a name="get-the-apple-dep-token"></a>Pobieranie tokenu DEP firmy Apple

Aby zarejestrować firmowe urządzenia z systemem iOS w programie Device Enrollment Program (DEP) firmy Apple, należy uzyskać token programu DEP (.p7m) od firmy Apple. Token umożliwia usłudze Intune synchronizację informacji dotyczących urządzeń uczestniczących w programie DEP należących do firmy. Umożliwia on również usłudze Intune przekazywanie profilów rejestracji do firmy Apple i przypisywanie urządzeń do tych profilów.

> [!NOTE]
> Jeśli usuniesz token z klasycznej konsoli usługi Intune przed migracją do usługi Azure, usługa Intune może przywrócić usunięty token DEP firmy Apple. Możesz ponownie usunąć token programu DEP z poziomu witryny Azure Portal. Możesz ponownie usunąć token programu DEP z poziomu witryny Azure Portal.

**Wymagania wstępne**
- [Certyfikat wypychania MDM firmy Apple](apple-mdm-push-certificate-get.md)
- Zarejestrowanie w [programie Device Enrollment Program firmy Apple](http://deploy.apple.com)

**Krok 1. Pobierz certyfikat klucza publicznego usługi Intune wymagany do utworzenia tokenu DEP firmy Apple.**<br>
1. W portalu usługi Intune wybierz pozycję **Rejestracja urządzenia**, a następnie **Rejestracja Apple** i **Token programu Enrollment Program**.

  ![Zrzut ekranu przedstawiający okienko tokenu programu Enrollment Program w obszarze roboczym certyfikatów firmy Apple.](./media/enrollment-program-token-add.png)

2. Wybierz pozycję **Pobierz klucz publiczny**, aby pobrać i zapisać lokalnie plik klucza szyfrowania (.pem). Plik PEM jest używany na potrzeby żądania certyfikatu relacji zaufania z portalu programu Device Enrollment Program firmy Apple.

  ![Zrzut ekranu przedstawiający okienko tokenu programu Enrollment Program w obszarze roboczym certyfikatów firmy Apple umożliwiające pobranie klucza publicznego.](./media/enrollment-program-token-download.png)

**Krok 2. Utwórz i pobierz token DEP firmy Apple.**<br>
1. Wybierz pozycję **Utwórz token za pomocą programu Device Enrollment Program firmy Apple**, aby otworzyć portal programu wdrażania firmy Apple i zalogować się przy użyciu firmowego identyfikatora Apple ID. Tego identyfikatora firmy Apple możesz użyć do odnowienia tokenu DEP.

  ![Zrzut ekranu przedstawiający okienko tokenu programu Enrollment Program w obszarze roboczym certyfikatów firmy Apple.](./media/enrollment-program-token-create.png)

  ![Zrzut ekranu przedstawiający okienko tokenu programu Enrollment Program w obszarze roboczym certyfikatów firmy Apple umożliwiające pobranie klucza publicznego.](./media/enrollment-program-token-sign.png)
2.  W [portalu programów wdrażania](https://deploy.apple.com) firmy Apple wybierz pozycję **Get Started** (Rozpocznij) dla opcji **Device Enrollment Program**.

   ![Zrzut ekranu przedstawiający kliknięcie pozycji Get Started (Rozpocznij) dla opcji Device Enrollment Program.](./media/enrollment-program-token-started.png)

3. Na stronie **Manage Servers** (Zarządzanie serwerami) wybierz pozycję **Add MDM Server** (Dodaj serwer MDM).
4. Wprowadź nazwę serwera w polu **MDM Server Name** (Nazwa serwera MDM), a następnie wybierz przycisk **Next**(Dalej). Nazwa serwera służy użytkownikowi do identyfikowania serwera MDM. Nie jest to nazwa ani adres URL serwera usługi Microsoft Intune.

   ![Zrzut ekranu przedstawiający dodawanie nazwy serwera MDM dla programu DEP, a następnie klikanie przycisku Next (Dalej).](./media/enrollment-program-token-add-server.png)

5. Zostanie otwarte okno dialogowe **Add &lt;nazwa_serwera&gt;** (Dodawanie serwera <nazwa_serwera>) z widocznym komunikatem **Upload Your Public Key** (Przekaż klucz publiczny). Kliknij pozycję **Choose File…** (Wybierz plik...) w celu przekazania pliku PEM, a następnie kliknij przycisk **Next** (Dalej).

   ![Zrzut ekranu przedstawiający przycisk umożliwiający wybranie pliku klucza publicznego, a następnie kliknięcie przycisku Next (Dalej).](./media/enrollment-program-token-choose-file.png)
6.  W oknie dialogowym **Add&lt; <nazwa_serwera>&gt;** (Dodawanie serwera <nazwa_serwera>) zostanie wyświetlony link **Your Server Token** (Token serwera). Pobierz plik tokenu serwera (p7m) na komputer, a następnie wybierz pozycję **Done**(Gotowe).
   ![Zrzut ekranu przedstawiający przycisk umożliwiający wybranie pliku klucza publicznego, a następnie kliknięcie przycisku Next (Dalej).](./media/enrollment-program-token-your-token.png)
7. Wybierz kolejno pozycje **Deployment Programs** (Programy wdrażania)&gt; **Device Enrollment Program** (Program rejestracji urządzeń) &gt; **Manage Devices** (Zarządzaj urządzeniami).
8. W obszarze **Choose Devices By** (Sposób wybierania urządzeń) określ sposób identyfikowania urządzeń:
    - **Serial Number** (Numer seryjny)
    - **Order Number** (Numer zamówienia)
    - **Upload CSV File** (Przekaż plik CSV).

   ![Zrzut ekranu przedstawiający wybraną opcję wybierania urządzeń według numerów seryjnych, akcję po wybraniu ustawioną jako przypisywanie do serwera oraz wybraną nazwę serwera.](./media/enrollment-program-token-specify-serial.png)

9. W kroku **Choose Action** (Wybierz akcję) wybierz pozycję **Assign to Server** (Przypisz do serwera), wybierz nazwę serwera &lt;nazwa_serwera&gt; określoną dla usługi Microsoft Intune, a następnie wybierz przycisk **OK**. Portal firmy Apple przypisze wskazane urządzenia do funkcji zarządzania na serwerze Intune, a następnie wyświetli komunikat **Assignment Complete** (Przypisanie zostało ukończone).

   W portalu firmy Apple wybierz pozycję **Deployment Programs** (Programy wdrażania) &gt; **Device Enrollment Program** &gt; **View Assignment History** (Wyświetl historię przypisania), aby wyświetlić listę urządzeń i ich przypisania do serwera MDM.

**Krok 3. Wprowadź identyfikator Apple ID użyty do utworzenia tokenu programu rejestracji.**<br>W portalu usługi Intune podaj identyfikator Apple ID do przyszłego wykorzystania. Identyfikator ten umożliwia odnowienie tokenu programu rejestracji bez potrzeby ponownego rejestrowania wszystkich urządzeń.

![Zrzut ekranu przedstawiający wprowadzanie identyfikatora Apple ID używanego do utworzenia tokenu programu rejestracji i przechodzenie do tokenu programu rejestracji.](./media/enrollment-program-token-apple-id.png)

**Krok 4. Przechodzenie do tokenu programu rejestracji w celu jego przekazania.**<br>
Przejdź do pliku certyfikatu (.pem) i wybierz pozycję **Otwórz**, a następnie wybierz pozycję **Przekaż**. Dzięki certyfikatowi wypychania usługa Intune może rejestrować urządzenia z systemem iOS i zarządzać nimi, wypychając zasady do zarejestrowanych urządzeń przenośnych. Usługa Intune automatycznie synchronizuje dane z firmą Apple, co pozwala wyświetlić konto programu rejestracji.

## <a name="create-an-apple-enrollment-profile"></a>Tworzenie profilu rejestracji firmy Apple

Profil rejestracji urządzeń określa ustawienia stosowane do grupy urządzeń podczas rejestracji.

1. W portalu usługi Intune wybierz pozycję **Rejestracja urządzenia**, a następnie pozycję **Rejestracja Apple**.
2. W obszarze **Program Enrollment Program dla firmy apple** wybierz pozycję **Profile programu Enrollment Program**, a następnie wybierz pozycję **Utwórz** w bloku **Profile programu Enrollment Program**.

  ![Zrzut ekranu przedstawiający wybieranie linku umożliwiającego utworzenie nowego profilu programu rejestracji.](./media/enrollment-program-profile-create.png)

3. W bloku **Utwórz profil rejestracji** wprowadź nazwę w polu **Nazwa** i opis w polu **Opis** dotyczące profilu do celów administracyjnych. Te szczegóły nie są widoczne dla użytkowników.

  ![Zrzut ekranu przedstawiający wprowadzanie nazwy i opisu oraz wybieranie pozycji Zarejestruj z koligacją użytkownika dla nowego profilu programu rejestracji.](./media/enrollment-program-profile-name.png)
Dla pozycji **Koligacja użytkownika** wskaż, czy urządzenia z tym profilem będą rejestrowane z koligacją użytkownika, czy bez niej.

 - **Zarejestruj z koligacją użytkownika** — podczas konfiguracji jest określana przynależność urządzenia do użytkownika, któremu można następnie przyznać dostęp do firmowych danych i poczty e-mail. Ustawienie **Koligacja użytkownika** należy wybrać w przypadku urządzeń należących do użytkowników, które muszą korzystać z portalu firmy na potrzeby usług takich jak instalowanie aplikacji.

 > [!NOTE]
 > Uwierzytelnianie wieloskładnikowe (MFA) nie działa podczas rejestrowania urządzeń objętych programem rejestracji, gdy jest używana koligacja użytkownika. Po zarejestrowaniu tych urządzeń uwierzytelnianie wieloskładnikowe działa zgodnie z oczekiwaniami. W przypadku nowych użytkowników, dla których wymagana jest zmiana hasła podczas pierwszego logowania, nie można wyświetlić monitu podczas rejestrowania urządzeń. Ponadto w przypadku użytkowników, których hasła wygasły, nie zostanie wyświetlony monit o zresetowanie hasła podczas rejestracji i muszą oni zresetować hasło za pomocą innego urządzenia.

 >[!NOTE]
 >Zarządzanie programem rejestracji z koligacją użytkownika wymaga włączenia nazwy użytkownika protokołu [WS-Trust 1.3/mieszanego punktu końcowego](https://technet.microsoft.com/library/adfs2-help-endpoints) w celu umożliwienia wysyłania żądań dotyczących tokenu użytkownika. [Dowiedz się więcej na temat protokołu WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Zarejestruj bez koligacji użytkownika** — przynależność urządzenia do użytkownika nie jest określana. Tego typu przynależności należy użyć w przypadku urządzeń wykonujących zadania bez uzyskiwania dostępu do danych użytkowników lokalnych. Aplikacje wymagające koligacji użytkownika (w tym aplikacja Portal firmy używana do instalowania aplikacji biznesowych) nie mogą działać.

4. Wybierz pozycję **Ustawienia zarządzania urządzeniami**, aby skonfigurować następujące ustawienia profilu:

  ![Zrzut ekranu przedstawiający wybór trybu zarządzania. Urządzenie ma następujące ustawienia: nadzorowane, zablokowana rejestracja, opcja zezwalania parowania ustawiona na odrzucanie wszystkich. Pozycja certyfikatów programu Apple Configurator jest wyszarzona dla nowego profilu rejestracji programu.](./media/enrollment-program-profile-mode.png)
    - **Nadzorowane** — tryb zarządzania, w ramach którego następuje włączenie większej liczby opcji zarządzania i domyślne wyłączenie blokady aktywacji. Jeśli pole pozostanie puste, użytkownik będzie mieć ograniczone możliwości w zakresie zarządzania.

    - **Rejestracja zablokowana** — (wymaga zastosowania ustawienia Tryb zarządzania = Nadzorowane) wyłącza ustawienia systemu iOS, które umożliwiają usunięcie profilu zarządzania. W przypadku pozostawienia tego pola pustego istnieje możliwość usunięcia profilu zarządzania z poziomu menu Ustawienia. Po rejestracji urządzenia nie można zmienić tego ustawienia bez resetowania urządzenia do ustawień fabrycznych.

    - **Zezwalaj na parowanie** — określa, czy urządzenia z systemem iOS można synchronizować z komputerami. W przypadku wybrania pozycji **Zezwalaj programowi Apple Configurator według certyfikatów** należy wybrać certyfikat w obszarze **Certyfikaty programu Apple Configurator**.

    - **Certyfikaty programu Apple Configurator** — w przypadku wyboru pozycji **Zezwalaj programowi Apple Configurator według certyfikatów** w obszarze **Zezwalaj na parowanie** należy wybrać certyfikat programu Apple Configurator do zaimportowania.

  Wybierz polecenie **Zapisz**.

5. Wybierz pozycję **Ustawienia Asystenta ustawień** i skonfiguruj następujące ustawienia profilu:

  ![Zrzut ekranu przedstawiający wybór ustawień konfiguracji z dostępnymi ustawieniami dla nowego profilu rejestracji programu.](./media/enrollment-program-profile-settings.png)
    - **Nazwa działu** — jest wyświetlana, gdy użytkownik dotknie pozycji **Informacje o konfiguracji** podczas aktywacji.

    - **Telefon działu** — jest wyświetlany, gdy użytkownik kliknie podczas aktywacji przycisk **Potrzebna pomoc**.
    - **Opcje Asystenta ustawień** — te opcjonalne ustawienia mogą być później konfigurowane z poziomu menu **Ustawienia** systemu iOS.
        - **Kod dostępu** — wyświetla monit o podanie kodu dostępu podczas aktywacji. Zawsze należy wymagać kodu dostępu, chyba że urządzenie zostanie zabezpieczone lub dostęp do niego będzie kontrolowany w inny sposób. Na przykład zostanie zastosowany tryb kiosku, który ogranicza możliwość użycia urządzenia do jednej aplikacji.
        - **Usługi lokalizacji** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący usługi podczas aktywacji
        - **Przywracanie** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit o kopię zapasową w programie iCloud podczas aktywacji
        - **Apple ID** — jeśli to ustawienie zostało włączone, system iOS wyświetli monit o podanie identyfikatora Apple ID, gdy usługa Intune będzie podejmowała próbę zainstalowania aplikacji bez tego identyfikatora. Identyfikator Apple ID jest wymagany do pobierania aplikacji ze sklepu iOS App Store, w tym aplikacji zainstalowanych przez usługę Intune.
        - **Warunki i postanowienia** — jeśli to ustawienie zostało włączone, Asystent ustawień monituje użytkowników o zaakceptowanie warunków i postanowień firmy Apple podczas aktywacji
        - **Touch ID** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji
        - **Apple Pay** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji
        - **Zoom** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji
        - **Siri** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji
        - **Dane diagnostyczne** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji

    Wybierz polecenie **Zapisz**.
9. Aby zapisać ustawienia profilu, wybierz pozycję **Utwórz** w bloku **Utwórz profil rejestracji**. Profil rejestracji zostanie wyświetlony na liście Profile rejestracji programu Enrollment Program firmy Apple.

## <a name="sync-managed-devices"></a>Synchronizowanie urządzeń zarządzanych
Gdy usługa Intune ma uprawnienia do zarządzania urządzeniami, można ją zsynchronizować z danymi firmy Apple, aby wyświetlić zarządzane urządzenia w portalu usługi Intune.

1. W portalu usługi Intune wybierz pozycję **Rejestracja urządzenia** &gt; **Rejestracja Apple** &gt; **Urządzenia programu Enrollment Program**.
2. W obszarze **Urządzenia programu Enrollment Program** wybierz pozycję **Synchronizacja**. Zostanie wyświetlony blok **Synchronizacja**.

  ![Zrzut ekranu przedstawiający wybrany węzeł Urządzenia programu Enrollment Program i wybierany link Synchronizuj.](./media/enrollment-program-device-sync.png)
3. W bloku **Synchronizuj** wybierz pozycję **Żądaj synchronizacji**. Pasek postępu pokazuje, ile czasu minie przed ponownym przesłaniem żądania synchronizacji.

  ![Zrzut ekranu przedstawiający blok Synchronizuj i wybierany link Żądaj synchronizacji.](./media/enrollment-program-device-request-sync.png)

  Aby spełnić warunki firmy Apple dotyczące ruchu w programie rejestracji, usługa Intune nakłada następujące ograniczenia:
     -  Pełną synchronizację można uruchamiać nie częściej niż co siedem dni. Podczas pełnej synchronizacji usługa Intune odświeża każdy numer seryjny Apple przypisany do usługi Intune. W przypadku próby przeprowadzenia pełnej synchronizacji przed upływem siedmiu dni od poprzedniej pełnej synchronizacji usługa Intune odświeża tylko numery seryjne, które jeszcze nie zostały przypisane do usługi Intune.
     -  Każde żądanie synchronizacji ma przydzielone 15 minut na zakończenie. W tym czasie lub do momentu zakończenia żądania powodzeniem przycisk **synchronizacji** jest wyłączony.
     - Usługa Intune co 24 godziny synchronizuje z firmą Apple urządzenia nowe i usunięte.
     
4. W obszarze roboczym Urządzenia programu Enrollment Program wybierz pozycję **Odśwież**, aby wyświetlić urządzenia.

## <a name="assign-an-enrollment-profile-to-devices"></a>Przypisywanie profilu rejestracji do urządzeń
Zanim możliwe będzie rejestrowanie urządzeń, należy przypisać profil programu rejestracji.

>[!NOTE]
>Możesz także przypisać numery seryjne do profilów w bloku **Numery seryjne Apple**.

1. W portalu usługi Intune wybierz kolejno pozycje **Rejestracja urządzenia** > **Rejestracja Apple**, a następnie wybierz pozycję **Profile programu Enrollment Program**.
2. Z listy **Profile programu Enrollment Program** wybierz profil, który ma zostać przypisany do urządzeń, a następnie wybierz pozycję **Przypisz urządzenia**.

 ![Zrzut ekranu przedstawiający blok Synchronizuj i wybierany link Żądaj synchronizacji.](./media/enrollment-program-device-assign.png)

3. Wybierz pozycję **Przypisz**, a następnie wybierz urządzenia, do których chcesz przypisać ten profil. Możesz zastosować filtr, aby wyświetlić dostępne urządzenia:
  - **nieprzypisane**
  - **dowolne**
  - **&lt;nazwa profilu&gt;**
4. Wybierz urządzenia, które chcesz przypisać. Pole wyboru nad kolumną pozwala na wybranie z listy maksymalnie 1000 urządzeń. Po wybraniu urządzeń kliknij przycisk **Przypisz**. Aby zarejestrować więcej niż 1000 urządzeń, powtarzaj procedurę przypisania, aż profil rejestracji zostanie przypisany do wszystkich urządzeń.

  ![Zrzut ekranu przedstawiający przycisk Przypisz służący do przypisywania profilu programu rejestracji w portalu usługi Intune](media/dep-profile-assignment.png)

## <a name="end-user-experience-with-managed-devices"></a>Środowisko użytkownika końcowego z zarządzanymi urządzeniami

Możesz teraz przekazać urządzenia użytkownikom. W przypadku urządzeń z koligacją użytkownika wymagane jest, aby poszczególni użytkownicy mieli przypisane licencje na korzystanie z usługi Intune. Aktywowane urządzenie nie może stosować profilu rejestracji, dopóki urządzenie nie zostanie zresetowane do ustawień fabrycznych. Po włączeniu urządzenia z systemem iOS zarządzanego przez program rejestracji użytkownik zobaczy na swoim urządzeniu następujące opcje:  

1. **Konfiguruj urządzenie z systemem iOS** — użytkownicy mogą wybrać następujące opcje:
  - **Konfiguruj jako nowe urządzenie**
  - **Przywróć z kopii zapasowej w usłudze iCloud**
  - **Przywróć z kopii zapasowej w usłudze iTunes**
2. Użytkownicy widzą komunikat: **&lt;Twoja organizacja&gt; automatycznie skonfiguruje urządzenie.** Dostępne są również następujące szczegółowe informacje dotyczące konfiguracji:

  **Konfiguracja umożliwia &lt;Twojej organizacji&gt; zarządzanie tym urządzeniem bez udziału użytkownika.**

  **Administrator może pomóc Ci w konfigurowaniu kont poczty e-mail i kont sieciowych, instalowaniu i konfigurowaniu aplikacji oraz zdalnym zarządzaniu ustawieniami.**

  **Administrator może wyłączać funkcje, instalować i usuwać aplikacje, monitorować i ograniczać ruch internetowy oraz zdalnie wymazać to urządzenie.**

  **Konfiguracja jest dostarczana przez:<br> &lt;Address&gt; zespołu ds. iOS<br> &lt;Twojej organizacji&gt;** 

3. Użytkownicy są monitowani o podanie nazwy użytkownika i hasła do konta służbowego.
4. Użytkownicy są monitowani o podanie identyfikatora Apple ID. Identyfikator Apple ID jest wymagany do zainstalowania aplikacji Intune — portal firmy i innych aplikacji. Po podaniu poświadczeń na urządzeniu jest instalowany profil zarządzania, którego nie można usunąć. Aby wyświetlić profil zarządzania usługą Intune, należy wybrać pozycję **Ustawienia** > **Ogólne** > **Zarządzanie urządzeniami** na urządzeniu.

Użytkownicy mogą dokończyć konfigurowanie firmowego urządzenia przy użyciu aplikacji Intune — portal firmy lub Asystenta ustawień firmy Apple.
