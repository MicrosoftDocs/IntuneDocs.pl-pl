---
title: "Rozwiązywanie problemów z rejestrowaniem urządzeń"
titleSuffix: Intune on Azure
description: "Informacje o rozwiązywaniu problemów z rejestrowaniem urządzeń."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c324c74e-e225-40ad-88b7-72a6d9ea09b5
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9b7af9168164f1cccf3feae5bbdfd8014f8c7c1f
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2017
---
# <a name="troubleshoot-device-enrollment-in-intune"></a>Rozwiązywanie problemów dotyczących rejestrowania urządzeń w usłudze Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ten temat zawiera sugestie dotyczące rozwiązywania problemów z rejestracją urządzenia. Jeśli te informacje nie pomogą rozwiązać problemu, zobacz [How to get support for Microsoft Intune](https://docs.microsoft.com/intune-classic/troubleshoot/get-support) (Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune), aby znaleźć więcej sposobów uzyskania pomocy.


## <a name="initial-troubleshooting-steps"></a>Początkowe kroki rozwiązywania problemów

Przed rozpoczęciem rozwiązywania problemów upewnij się, że usługa Intune została prawidłowo skonfigurowana w celu umożliwienia rejestracji. Zobacz artykuł [Rejestrowanie urządzeń z systemem Android i Standard Knox](android-enroll.md), aby znaleźć linki do kroków rejestracji dotyczących poszczególnych platform.

Użytkownicy urządzenia zarządzanego mogą zbierać dzienniki rejestracji i dzienniki diagnostyczne, z którymi możesz się zapoznać. Instrukcje użytkownika dotyczące zbierania tych dzienników przedstawiono w następujących tematach:

- [Wysyłanie błędów rejestracji systemu Android do administratora IT](https://docs.microsoft.com/intune-user-help/send-enrollment-errors-to-your-it-admin-android)
- [Wysyłanie błędów systemu iOS do administratora IT](https://docs.microsoft.com/intune-user-help/send-errors-to-your-it-admin-ios)

## <a name="general-enrollment-issues"></a>Ogólne problemy dotyczące rejestrowania
Te problemy mogą wystąpić na wszystkich platformach urządzeń.

### <a name="device-cap-reached"></a>Osiągnięto limit urządzeń
**Problem:** podczas rejestracji urządzenia występuje błąd, na przykład **Portal firmy jest tymczasowo niedostępny** na urządzeniu z systemem iOS, a dziennik DMPdownloader.log programu Configuration Manager zawiera błąd **DeviceCapReached**.

**Rozwiązanie:**

#### <a name="check-number-of-devices-enrolled-and-allowed"></a>Sprawdzanie liczby zarejestrowanych i dozwolonych urządzeń

W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**. W bloku Intune portalu Azure Portal wybierz pozycje **Zarejestruj urządzenia** > **Ograniczenia rejestracji** i sprawdź, czy liczba urządzeń przypisanych do użytkownika nie przekroczyła dozwolonego limitu 15 urządzeń.

<!--- Mobile device users can delete devices at the following URL: [https://byodtestservice.azurewebsites.net/](https://byodtestservice.azurewebsites.net/). --->

Administratorzy mogą usuwać urządzenia w portalu usługi Azure Active Directory.

#### <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>Aby usunąć urządzenia w portalu usługi Azure Active Directory

1.  Przejdź do witryny [http://aka.ms/accessaad](http://aka.ms/accessaad) lub wybierz pozycję **Administrator** &gt; **Azure AD** w witrynie [https://portal.office.com](https://portal.office.com).

2.  Zaloguj się za pomocą identyfikatora organizacji, korzystając z linku w lewej części strony.

3.  Utwórz subskrypcję platformy Azure, jeśli jej nie masz. Jeśli masz płatne konto, ta operacja nie powinna wymagać uiszczenia płatności ani podania danych karty kredytowej (wybierz link do subskrypcji **Zarejestruj bezpłatny katalog Azure Active Directory**).

4.  Wybierz pozycję **Active Directory**, a następnie wybierz organizację.

5.  Wybierz kartę **Użytkownicy** .

6.  Wybierz użytkownika, którego urządzenia chcesz usunąć.

7.  Wybierz pozycję **Urządzenia**.

8.  Usuń urządzenia zgodnie z potrzebami, na przykład takie, które nie są już w użyciu lub zawierają niedokładne definicje.

> [!NOTE]

> Można uniknąć stosowania limitu rejestracji urządzeń, używając menedżerów rejestracji urządzeń zgodnie z opisem w temacie [Rejestrowanie urządzeń przy użyciu menedżera rejestracji urządzeń](device-enrollment-manager-enroll.md).
>
> W przypadku konta użytkownika dodanego do grupy Menedżerowie rejestracji urządzeń ukończenie procesu rejestracji będzie niemożliwe, jeśli w odniesieniu do danych logowania użytkownika zostaną wymuszone zasady dostępu warunkowego.

### <a name="company-portal-temporarily-unavailable"></a>Portal firmy jest tymczasowo niedostępny
**Problem:** na urządzeniu występuje błąd **Portal firmy jest tymczasowo niedostępny**.

**Rozwiązanie:**

1.  Usuń aplikację Portal firmy dla usługi Intune z urządzenia.

2.  Na urządzeniu otwórz przeglądarkę, przejdź do witryny [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com)i spróbuj zalogować użytkownika.

3.  Jeśli użytkownik nie może się zalogować, niech spróbuje skorzystać z innej sieci.

4.  Jeśli ten sposób również zawiedzie, sprawdź, czy poświadczenia użytkownika zostały prawidłowo zsynchronizowane z usługą Azure Active Directory.

5.  Jeśli logowanie użytkownika przebiegnie pomyślnie, na urządzeniu z systemem iOS zostanie wyświetlony monit o zainstalowanie aplikacji Portal firmy dla usługi Intune i zarejestrowanie. Na urządzeniu z systemem Android należy ręcznie zainstalować aplikację Portal firmy dla usługi Intune, po czym będzie można ponowić próbę rejestracji.

### <a name="mdm-authority-not-defined"></a>Niezdefiniowany urząd MDM
**Problem:** występuje błąd **Nie zdefiniowano urzędu MDM**.

**Rozwiązanie:**

1.  Sprawdź, czy urząd MDM został prawidłowo ustawiony dla używanego typu usługi Intune (usługi Intune, usługi Office 365 lub programu System Center Configuration Manager z usługą Intune). Zobacz artykuł [Konfigurowanie urzędu zarządzania urządzeniami przenośnymi](mdm-authority-set.md), aby znaleźć instrukcje.

    > [!NOTE]    
    > W programie Configuration Manager w wersji 1610 lub nowszej i w usłudze Microsoft Intune w wersji 1705 można zmienić urząd certyfikacji MDM bez konieczności kontaktowania się Pomocą techniczną firmy Microsoft oraz wyrejestrowywania i ponownego rejestrowania istniejących urządzeń zarządzanych. Szczegółowe informacje można znaleźć w sekcji [Co należy zrobić, jeśli wybrano błędne ustawienie urzędu MDM](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).

2.  Upewnij się, że poświadczenia użytkownika zostały prawidłowo zsynchronizowane z usługą Azure Active Directory. W tym celu sprawdź, czy ich nazwy UPN odpowiadają informacjom o usłudze Active Directory w portalu konta.
    Jeśli nazwa UPN jest niezgodna z informacjami z usługi Active Directory:

    1.  Wyłącz narzędzie DirSync na serwerze lokalnym.

    2.  Usuń niezgodnego użytkownika z listy użytkowników w **portalu konta usługi Intune** .

    3.  Poczekaj około jednej godziny, aby umożliwić usunięcie nieprawidłowych danych z usługi Azure.

    4.  Włącz ponownie narzędzie DirSync i sprawdź, czy użytkownik jest teraz prawidłowo synchronizowany.

3.  W przypadku gdy używasz usługi Intune z programem System Center Configuration Manager, sprawdź, czy użytkownik ma prawidłowy identyfikator użytkownika chmury:

    1.  Otwórz program SQL Management Studio.

    2.  Nawiąż połączenie z odpowiednią bazą danych.

    3.  Otwórz folder baz danych i znajdź, a następnie otwórz folder **CM_DBName**, gdzie DBName to nazwa bazy danych klienta.

    4.  U góry wybierz pozycję **Nowa kwerenda** i wykonaj następujące zapytania:

        -   Aby wyświetlić wszystkich użytkowników: `select * from [CM_ DBName].[dbo].[User_DISC]`

        -   Aby wyświetlić konkretnych użytkowników, użyj następującego zapytania, gdzie %testuser1% reprezentuje nazwę username@domain.com dla użytkownika, którego chcesz wyszukać: `select * from [CM_ DBName].[dbo].[User_DISC] where User_Principal_Name0 like '%testuser1%'`

        Po zapisaniu zapytania wybierz pozycję **!Wykonaj**.
        Po zwróceniu wyników poszukaj identyfikatora użytkownika chmury.  Jeśli identyfikator nie zostanie znaleziony, oznacza to, że użytkownik nie ma licencji na korzystanie z usługi Intune.

### <a name="unable-to-create-policy-or-enroll-devices-if-the-company-name-contains-special-characters"></a>Nie można utworzyć zasad lub zarejestrować urządzeń, jeśli nazwa firmy zawiera znaki specjalne.
**Problem:** Nie można utworzyć zasad lub zarejestrować urządzeń.

**Rozwiązanie:** W [centrum administracyjnym usługi Office 365](https://portal.office.com/) usuń znaki specjalne z nazwy firmy i zapisz informacje o firmie.

### <a name="unable-to-log-in-or-enroll-devices-when-you-have-multiple-verified-domains"></a>Nie można zalogować się lub zarejestrować urządzeń w przypadku posiadania wielu zweryfikowanych domen
**Problem:** Po dodaniu drugiej zweryfikowanej domeny do usług ADFS możliwe, że użytkownicy z sufiksem nazwy głównej użytkownika (UPN) drugiej domeny nie będą mogli zalogować się do portali lub rejestrować urządzeń.


**Rozwiązanie:** W przypadku klientów usługi Microsoft Office 365 korzystających z funkcji logowania jednokrotnego (SSO, single sign-on) przy użyciu usług AD FS 2.0 i mających wiele domen najwyższego poziomu dla sufiksów nazw głównych użytkowników w organizacji (na przykład @contoso.com lub @fabrikam.com) jest wymagane wdrożenie oddzielnego wystąpienia usługi federacyjnej AD FS 2.0 na każdy sufiks.  Obecnie dostępny jest [zbiorczy pakiet aktualizacji dla usług AD FS 2.0](http://support.microsoft.com/kb/2607496) działający w połączeniu z przełącznikiem **SupportMultipleDomain** w celu włączenia obsługi tego scenariusza przez serwer usług AD FS bez konieczności dodawania dodatkowych serwerów usługi AD FS 2.0. Aby uzyskać więcej informacji, zobacz [ten blog](https://blogs.technet.microsoft.com/abizerh/2013/02/05/supportmultipledomain-switch-when-managing-sso-to-office-365/).


## <a name="android-issues"></a>Problemy z systemem android
### <a name="devices-fail-to-check-in-with-the-intune-service-and-display-as-unhealthy-in-the-intune-admin-console"></a>Nie można zaewidencjonować urządzeń w usłudze Intune — w konsoli administracyjnej usługi Intune stan urządzeń jest wyświetlany jako „W niedobrej kondycji”
**Problem:** zaewidencjonowywanie niektórych urządzeń firmy Samsung z systemem Android w wersji 4.4.x i 5.x przy użyciu usługi Intune może zostać zatrzymane. Jeśli nie można zaewidencjonować urządzeń:

- Nie otrzymują one zasad, aplikacji ani poleceń zdalnych z usługi Intune.
- W konsoli administracyjnej ich stan jest wyświetlany jako **W niedobrej kondycji**.
- Użytkownicy chronieni przez zasady dostępu warunkowego mogą utracić dostęp do zasobów firmowych.

Firma Samsung potwierdziła, że oprogramowanie Samsung Smart Menedżer dostarczane na niektórych urządzeniach Samsung może powodować dezaktywowanie aplikacji Portal firmy w usłudze Intune oraz jej składników. Zdezaktywowanej aplikacji Portal firmy nie można uruchomić w tle, co uniemożliwia nawiązywanie kontaktu z usługą Intune.

**Rozwiązanie 1:**

Poproś użytkowników o ręczne uruchomienie aplikacji Portal firmy. Po ponownym uruchomieniu aplikacji urządzenie jest zaewidencjonowywane przy użyciu usługi Intune.

> [!IMPORTANT]
> Ręczne otwieranie aplikacji Portal firmy to rozwiązanie tymczasowe, ponieważ oprogramowanie Samsung Smart Menedżer może spowodować ponowne dezaktywowanie aplikacji Portal firmy.

**Rozwiązanie 2:**

Poproś użytkowników, aby spróbowali uaktualnić do systemu Android do wersji 6.0. Problem z dezaktywacją nie występuje na urządzeniach z systemem Android 6.0. Aby sprawdzić, czy aktualizacja jest dostępna, użytkownicy mogą przejść kolejno do pozycji **Ustawienia** > **Informacje o urządzeniu** > **Pobierz aktualizacje ręcznie** i postępować zgodnie z monitami wyświetlanymi w urządzeniu.

**Rozwiązanie 3:**

Jeśli rozwiązanie 2 nie działa, poproś użytkowników o wykonanie poniższych kroków w celu wykluczenia aplikacji Portal firmy z oprogramowania Smart Menedżer:

1. Uruchom aplikację Smart Menedżer w urządzeniu.

  ![Wybieranie ikony Smart Menedżer w urządzeniu](./media/smart-manager-app-icon.png)

2. Wybierz kafelek **Bateria**.

  ![Wybieranie kafelka Bateria](./media/smart-manager-battery-tile.png)

3. W obszarze **Oszczędzanie energii dla aplikacji** lub **Optymalizacja aplikacji** wybierz pozycję **Szczegóły**.

  ![Wybieranie pozycji Szczegóły w obszarze Oszczędzanie energii dla aplikacji lub Optymalizacja aplikacji](./media/smart-manager-app-power-saving-detail.png)

4. Z listy aplikacji wybierz pozycję **Portal firmy**.

  ![Wybieranie pozycji Portal firmy z listy aplikacji](./media/smart-manager-company-portal.png)

5. Wybierz pozycję **Wyłączono**.

  ![Wybieranie pozycji Wyłączono w oknie dialogowym Optymalizacja aplikacji](./media/smart-manager-app-optimization-turned-off.png)

6. W obszarze **Oszczędzanie energii dla aplikacji** lub **Optymalizacja aplikacji** sprawdź, czy aplikacja Portal firmy została wyłączona.

  ![Sprawdzanie, czy aplikacja Portal firmy została wyłączona](./media/smart-manager-verify-comp-portal-turned-off.png)


### <a name="profile-installation-failed"></a>Instalacja profilu nie powiodła się
**Problem:**  Na urządzeniu z systemem Android wystąpił błąd **Instalacja profilu nie powiodła się**.

**Rozwiązanie:**

1.  Upewnij się, że użytkownikowi przypisano odpowiednią licencję dla używanej wersji usługi Intune.

2.  Sprawdź, czy urządzenie nie zostało już zarejestrowane za pomocą innego dostawcy MDM lub czy nie zainstalowano już dla niego profilu zarządzania.

3.  Upewnij się, że domyślną przeglądarką w systemie jest program Chrome dla systemu Android oraz że pliki cookie są włączone.

### <a name="android-certificate-issues"></a>Problemy z certyfikatami systemu Android

**Problem**: użytkownicy otrzymują następujący komunikat na urządzeniu: *Nie możesz się zalogować, ponieważ urządzenie nie ma wymaganego certyfikatu.*

**Rozwiązanie 1**:

poproś użytkowników o wykonanie instrukcji zawartych w artykule [Brak wymaganego certyfikatu urządzenia](https://docs.microsoft.com/intune-user-help/your-device-is-missing-a-required-certificate-landing-android#your-device-is-missing-a-certificate-required-by-your-it-administrator). Jeśli po wykonaniu instrukcji błąd nadal występuje, spróbuj rozwiązania 2.

**Rozwiązanie 2**:

jeśli użytkownicy nadal widzą błąd braku certyfikatu po wprowadzeniu poświadczeń firmowych i przekierowaniu w celu obsługi logowania federacyjnego, być może brakuje pośredniego certyfikatu z serwera usług Active Directory Federation Services (AD FS).

Błąd certyfikatu występuje, ponieważ urządzenia z systemem Android wymagają certyfikatów pośrednich zawartych w [powitaniu serwera SSL](https://technet.microsoft.com/library/cc783349.aspx), ale obecnie instalacja serwera domyślnego usług AD FS lub serwera proxy usług AD FS w odpowiedzi serwera SSL na powitanie klienta SSL wysyła jedynie certyfikat SSL usług AD FS.

Aby rozwiązać ten problem, zaimportuj certyfikaty do certyfikatów osobistych komputerów na serwerze usług AD FS lub serwerach proxy w następujący sposób:

1.  Na serwerach usług AD FS i serwerach proxy uruchom konsolę zarządzania certyfikatami dla komputera lokalnego, klikając prawym przyciskiem myszy przycisk **Start**, a następnie wybierając polecenie **Uruchom** i wpisując ciąg **certlm.msc**.
2.  Rozwiń węzeł **Osobiste** i wybierz pozycję **Certyfikaty**.
3.  Znajdź certyfikat dla komunikacji usług AD FS (certyfikat z podpisem publicznym), a następnie kliknij go dwukrotnie, aby wyświetlić jego właściwości.
4.  Wybierz kartę **Ścieżka certyfikacji**, aby wyświetlić certyfikaty nadrzędne tego certyfikatu.
5.  Dla każdego certyfikatu nadrzędnego zaznacz opcję **Wyświetl certyfikat**.
6.  Wybierz kartę **Szczegóły** i wybierz pozycję **Kopiuj do pliku...**.
7.  Postępuj zgodnie z poleceniami kreatora, aby wyeksportować lub zapisać klucz publiczny certyfikatu do żądanej lokalizacji pliku.
8.  Zaimportuj certyfikaty nadrzędne wyeksportowane w kroku 3 do lokalizacji Local Computer\Personal\Certificates, klikając prawym przyciskiem myszy pozycję **Certyfikaty**, wybierając pozycję **Wszystkie zadania** > **Importowanie**, a następnie wykonując polecenia kreatora w celu zaimportowania certyfikatów.
9.  Uruchom ponownie serwery usług AD FS.
10. Powtórz powyższe kroki na wszystkich serwerach usług AD FS i serwerach proxy.
Zalogowanie się do aplikacji Portal firmy na urządzeniu z systemem Android powinno być teraz możliwe.

**Aby sprawdzić, czy certyfikat jest zainstalowany prawidłowo**:

Następujące kroki opisują jedną z wielu metod i narzędzi umożliwiających sprawdzenie poprawności instalacji certyfikatu.

1. Przejdź do [bezpłatnego narzędzia Digicert](ttps://www.digicert.com/help/).
2. Wprowadź w pełni kwalifikowaną nazwę domeny serwera usług AD FS (np. sts.contoso.com), a następnie wybierz pozycję **SPRAWDŹ SERWER**.

Jeśli certyfikat serwera jest zainstalowany poprawnie, w wynikach zostaną wyświetlone wszystkie znaczniki wyboru. Jeśli powyższy problem występuje nadal, zobaczysz czerwony symbol X w sekcjach raportu „Certificate Name Matches” (Zgodne nazwy certyfikatu) i „SSL Certificate is correctly Installed” (Certyfikat SSL jest zainstalowany poprawnie).


## <a name="ios-issues"></a>Problemy z systemem iOS

### <a name="devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Urządzenia są nieaktywne lub nie jest możliwe nawiązanie łączności między nimi a konsolą administracyjną
**Problem:** urządzenia z systemem iOS nie są ewidencjonowane przy użyciu usługi Intune. Urządzenia muszą być okresowo zaewidencjonowane w celu umożliwienia im dalszego dostępu do chronionych zasobów firmy. Jeśli nie można zaewidencjonować urządzeń:

- Nie otrzymują one zasad, aplikacji ani poleceń zdalnych z usługi Intune.
- W konsoli administracyjnej ich stan jest wyświetlany jako **W niedobrej kondycji**.
- Użytkownicy chronieni przez zasady dostępu warunkowego mogą utracić dostęp do zasobów firmowych.

**Rozwiązanie:** podaj użytkownikom końcowym następujące rozwiązania, aby pomóc im odzyskać dostęp do zasobów firmy.

Po uruchomieniu w systemie iOS aplikacja Portal firmy sprawdza, czy urządzenie użytkownika nie utraciło łączności z usługą Intune. Jeśli aplikacja wykryje brak połączenia, automatycznie podejmie próbę synchronizacji z usługą Intune w celu ponownego nawiązania połączenia, czemu będzie towarzyszyć powiadomienie **Trwa próba wykonania synchronizacji...** widoczne dla użytkowników.

  ![Powiadomienie o trwającej próbie wykonania synchronizacji](./media/ios_cp_app_trying_to_sync_notification.png)

Jeśli synchronizacja zakończy się pomyślnie, zobaczysz w aplikacji Portal firmy w systemie iOS powiadomienie **Synchronizacja powiodła się** wskazujące, że urządzenie jest w prawidłowym stanie.

  ![Powiadomienie informujące, że synchronizacja powiodła się](./media/ios_cp_app_sync_successful_notification.png)

Jeśli synchronizacja nie powiedzie się, użytkownicy zobaczą w aplikacji Portal firmy w systemie iOS powiadomienie o treści **Nie można zsynchronizować**.

  ![Powiadomienie o nieudanej próbie synchronizacji](./media/ios_cp_app_unable_to_sync_notification.png)

Aby rozwiązać ten problem, użytkownicy muszą użyć przycisku **Konfiguruj** znajdującego się na prawo od powiadomienia **Nie można zsynchronizować**. Przycisk Konfiguruj umożliwia przejście do ekranu przepływu Konfiguracja dostępu do zasobów firmy. Postępując zgodnie z monitami wyświetlanymi na tej stronie, można zarejestrować swoje urządzenie.

  ![Ekran Konfiguracja dostępu do zasobów firmy](./media/ios_cp_app_company_access_setup.png)

Po zarejestrowaniu urządzenie powraca do stanu prawidłowego i odzyskuje dostęp do zasobów firmy.

### <a name="profile-installation-failed"></a>Instalacja profilu nie powiodła się
**Problem:**  Na urządzeniu z systemem iOS wystąpił błąd **Instalacja profilu nie powiodła się**.

### <a name="troubleshooting-steps-for-failed-profile-installation"></a>Kroki rozwiązywania problemów dotyczących niepowodzenia instalacji profilu

1.  Upewnij się, że użytkownikowi przypisano odpowiednią licencję dla używanej wersji usługi Intune.

2.  Sprawdź, czy urządzenie nie zostało już zarejestrowane za pomocą innego dostawcy MDM lub czy nie zainstalowano już dla niego profilu zarządzania.

3.  Przejdź do witryny [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) i po wyświetleniu monitu spróbuj zainstalować profil.

4.  Upewnij się, że domyślną przeglądarką jest program Safari dla systemu iOS oraz że pliki cookie są włączone.

### <a name="enrolled-ios-device-doesnt-appear-in-console-when-using-system-center-configuration-manager-with-intune"></a>Zarejestrowane urządzenie z systemem iOS nie jest wyświetlane w konsoli podczas korzystania z programu System Center Configuration Manager z usługą Intune
**Problem:** Użytkownik rejestruje urządzenie z systemem iOS, ale nie jest ono wyświetlane w konsoli administracyjnej programu Configuration Manager. Urządzenie nie wskazuje, że zostało zarejestrowane. Możliwe przyczyny:

- Łącznik usługi Intune mógł zostać zarejestrowany na jednym koncie, a następnie zarejestrowany na innym koncie.
- Możliwe, że pobrano certyfikat zarządzania urządzeniami przenośnymi z jednego konta i użyto go na innym koncie.


**Rozwiązanie:** Wykonaj następujące kroki:

1. Wyłącz system iOS w łączniku usługi Windows Intune.
    1. Kliknij prawym przyciskiem myszy subskrypcję usługi Intune i wybierz pozycję **Właściwości**.
    1. Na karcie „iOS” usuń zaznaczenie pola wyboru „Włącz rejestrację systemu iOS”.



2. W programie SQL uruchom następujące kroki w bazie danych CAS:

    1. update SC_ClientComponent_Property set Value2 = '' where Name like '%APNS%'
    1. delete from MDMPolicy where PolicyType = 7
    1. delete from MDMPolicyAssignment where PolicyType = 7
    1. update SC_ClientComponent_Property set Value2 = '' where Name like '%APNS%'
    1. delete from MDMPolicy where PolicyType = 11
    1. delete from MDMPolicyAssignment where PolicyType = 11
    1. DELETE Drs_Signals
3. Uruchom ponownie usługę SMS Executive lub serwer CM.

4. Uzyskaj nowy certyfikat APN i przekaż go. W tym celu kliknij prawym przyciskiem myszy subskrypcję usługi Intune w lewym okienku programu Configuration Manager. Wybierz polecenie **Utwórz żądanie certyfikatu usług APN** i postępuj zgodnie z instrukcjami.
5.
## <a name="issues-when-using-system-center-configuration-manager-with-intune"></a>Problemy dotyczące korzystania z programu System Center Configuration Manager z usługą Intune

### <a name="mobile-devices-disappear"></a>Urządzenia przenośne znikają

**Problem:** po pomyślnym zarejestrowaniu urządzenia przenośnego w programie Configuration Manager urządzenie znika z kolekcji urządzeń przenośnych, ale nadal posiada profil zarządzania i znajduje się na liście w obszarze bramy CSS.

**Rozwiązanie:** taka sytuacja może wystąpić, jeśli istnieje niestandardowy proces usuwania urządzeń, które nie są przyłączone do domeny, lub użytkownik wycofał urządzenie z subskrypcji. Aby to zweryfikować i zidentyfikować proces lub konto użytkownika będące przyczyną usunięcia urządzenia z konsoli programu Configuration Manager, wykonaj następujące kroki. Pozwolą one sprawdzić, w jaki sposób urządzenie zostało usunięte.

1.  W konsoli administracyjnej programu Configuration Manager wybierz pozycje **Monitorowanie** &gt; **Stan systemu** &gt; **Kwerendy komunikatów o stanie**.

2.  Kliknij prawym przyciskiem myszy pozycję **Ręcznie usunięte zasoby członka kolekcji** i wybierz polecenie **Pokaż komunikaty**.

3.  Wybierz odpowiednią datę i godzinę lub ostatnie 12 godzin.

4.  Znajdź dane urządzenie i sprawdź, jak zostało ono usunięte. W poniższym przykładzie pokazano sytuację, w której konto SCCMInstall spowodowało usunięcie urządzenia za pomocą nieznanej aplikacji.

    ![Zrzut ekranu przedstawiający diagnostykę usuwania urządzeń](./media/cm-with-intune-unknown-app-deleted-device.png)

5.  Upewnij się, że program Configuration Manager nie ma zaplanowanego zadania, skryptu ani innego procesu, który mógłby automatycznie usuwać urządzenia nienależące do domeny bądź urządzenia przenośne lub pokrewne.




### <a name="other-ios-enrollment-errors"></a>Inne błędy rejestracji urządzeń z systemem iOS

Możesz wyświetlić listę [Błędy rejestracji urządzeń z systemem iOS](https://docs.microsoft.com/intune-user-help/you-see-errors-while-trying-to-enroll-your-device-in-intune-ios), która zawiera błędy widoczne dla użytkowników końcowych. Lista zawiera informacje dotyczące komunikatów o błędach, które użytkownicy końcowi mogą napotkać, oraz czynności, które należy wykonać w celu rozwiązania problemu.

## <a name="pc--issues"></a>Problemy z komputerem PC

### <a name="the-machine-is-already-enrolled---error-hr-0x8007064c"></a>Maszyna jest już zarejestrowana — błąd hr 0x8007064c
**Problem:** Rejestracja kończy się niepowodzeniem z powodu błędu **Maszyna jest już zarejestrowana**. Dziennik rejestracji zawiera błąd **hr 0x8007064c**.

Ten błąd może wystąpić, ponieważ komputer został już wcześniej zarejestrowany lub zawiera sklonowany obraz komputera, który został zarejestrowany. Certyfikat poprzedniego konta nadal istnieje na komputerze.

**Rozwiązanie:**

1. W menu **Start** wpisz polecenie **Uruchom** -> **MMC**.
1. Wybierz kolejno opcje **Plik** > **Dodawanie lub usuwanie przystawek**.
1. Kliknij dwukrotnie pozycję **Certyfikaty**, wybierz pozycję **Konto komputera** > **Dalej**, a następnie wybierz pozycję **Komputer lokalny**.
1. Kliknij dwukrotnie pozycję **Certyfikaty (komputer lokalny)** i wybierz pozycję **Osobiste/certyfikaty**.
1. Wyszukaj certyfikat usługi Intune wydany przez wydawcę Sc_Online_Issuing i usuń go, jeśli istnieje.
1. Jeśli istnieje następujący klucz rejestru, usuń go oraz wszystkie jego klucze podrzędne: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\OnlineManagement regkey**.
1. Spróbuj ponownie zarejestrować komputer.
1. Jeśli nadal nie można zarejestrować komputera, wyszukaj następujący klucz i usuń go, jeśli istnieje: **KEY_CLASSES_ROOT\Installer\Products\6985F0077D3EEB44AB6849B5D7913E95**.
1. Spróbuj ponownie zarejestrować komputer.

    > [!IMPORTANT]
    > Ta sekcja, metoda lub zadanie zawiera kroki dotyczące sposobu modyfikowania rejestru. Jednak nieprawidłowa modyfikacja rejestru może powodować poważne problemy. Dlatego należy ostrożnie wykonywać te czynności. W celu zapewnienia dodatkowej ochrony utwórz kopię zapasową rejestru przed rozpoczęciem wprowadzania zmian. Dzięki temu w razie problemów będzie można przywrócić rejestr.
    > Aby uzyskać więcej informacji na temat tworzenia kopii zapasowej i przywracania rejestru, przeczytaj artykuł [Jak wykonać kopię zapasową i przywrócić rejestr w systemie Windows](https://support.microsoft.com/kb/322756).

## <a name="general-enrollment-error-codes"></a>Ogólne kody błędów rejestracji

|Kod błędu|Możliwy problem|Sugerowane rozwiązanie|
|--------------|--------------------|----------------------------------------|
|0x80CF0437 |W zegarze na komputerze klienckim nie ustawiono prawidłowego czasu.|Upewnij się, że dla zegara i strefy czasowej na komputerze klienckim ustawiono prawidłową godzinę i strefę czasową.|
|0x80240438, 0x80CF0438, 0x80CF402C|Nie można nawiązać połączenia z usługą Intune. Sprawdź ustawienia serwera proxy klienta.|Sprawdź, czy konfiguracja serwera proxy na komputerze klienckim jest obsługiwana przez usługę Intune i czy komputer kliencki ma dostęp do Internetu.|
|0x80240438, 0x80CF0438|Nie skonfigurowano ustawień serwera proxy w programie Internet Explorer i w systemie lokalnym.|Nie można nawiązać połączenia z usługą Intune. Sprawdź ustawienia serwera proxy klienta i upewnij się, że konfiguracja serwera proxy na komputerze klienckim jest obsługiwana przez usługę Intune i że komputer kliencki ma dostęp do Internetu.|
|0x80043001, 0x80CF3001, 0x80043004, 0x80CF3004|Pakiet rejestracyjny jest nieaktualny.|Pobierz i zainstaluj bieżący pakiet oprogramowania klienckiego z poziomu obszaru roboczego Administrator.|
|0x80043002, 0x80CF3002|Konto jest w trybie konserwacji.|Nie można zarejestrować nowych komputerów klienckich, gdy konto jest w trybie konserwacji. Aby wyświetlić ustawienia Twojego konta, zaloguj się do niego.|
|0x80043003, 0x80CF3003|Konto zostało usunięte.|Sprawdź, czy Twoje konto i subskrypcja usługi Intune są nadal aktywne. Aby wyświetlić ustawienia Twojego konta, zaloguj się do niego.|
|0x80043005, 0x80CF3005|Komputer kliencki został wycofany.|Poczekaj kilka godzin, usuń wszelkie wcześniejsze wersje oprogramowania klienckiego z komputera, a następnie ponów próbę instalacji oprogramowania klienckiego.|
|0x80043006, 0x80CF3006|Osiągnięto maksymalną liczbę dozwolonych stanowisk dla konta.|Twoja organizacja musi zakupić dodatkowe licencje na stanowiska, aby można było zarejestrować więcej komputerów klienckich w usłudze.|
|0x80043007, 0x80CF3007|Nie można odnaleźć pliku certyfikatu w folderze programu instalacyjnego.|Wyodrębnij wszystkie pliki przed rozpoczęciem instalacji. Nie zmieniaj nazw wyodrębnionych plików ani ich nie przenoś: wszystkie pliki muszą znajdować się w tym samym folderze — w przeciwnym razie instalacja się nie powiedzie.|
|0x8024D015, 0x00240005, 0x80070BC2, 0x80070BC9, 0x80CFD015|Nie można zainstalować oprogramowania, ponieważ komputer kliencki oczekuje na ponowne uruchomienie.|Uruchom ponownie komputer, a następnie ponów próbę instalacji oprogramowania klienckiego.|
|0x80070032|Na komputerze klienckim nie odnaleziono co najmniej jednego wymagania wstępnego dotyczącego instalacji oprogramowania klienckiego.|Upewnij się, że na komputerze klienckim są zainstalowane wszystkie wymagane aktualizacje, a następnie ponów próbę instalacji oprogramowania klienckiego.|
|0x80043008, 0x80CF3008|Uruchomienie usługi Microsoft Online Management Updates nie powiodło się.|Skontaktuj się z pomocą techniczną zgodnie z opisem w temacie [How to get support for Microsoft Intune](https://docs.microsoft.com/intune-classic/troubleshoot/get-support) (Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune).|
|0x80043009, 0x80CF3009|Komputer kliencki jest już zarejestrowany w usłudze.|Aby móc ponownie zarejestrować komputer kliencki w usłudze, musisz go najpierw wycofać.|
|0x8004300B, 0x80CF300B|Nie można uruchomić pakietu instalacyjnego oprogramowania klienckiego, ponieważ wersja systemu Windows uruchomiona na kliencie jest nieobsługiwana.|Usługa Intune nie obsługuje wersji systemu Windows uruchomionej na komputerze klienckim.|
|0xAB2|Instalator Windows nie może uzyskać dostępu do środowiska wykonawczego VBScript w celu wykonania akcji niestandardowej.|Przyczyną tego błędu jest próba wykonania akcji niestandardowej opartej na dołączanych dynamicznie bibliotekach (DLL). Podczas rozwiązywania problemu z biblioteką DLL może być konieczne użycie narzędzi opisanych w artykule KB198038 z bazy wiedzy pomocy technicznej firmy Microsoft: [Useful Tools for Package and Deployment Issues](https://support.microsoft.com/kb/198038) (Przydatne narzędzia w przypadku problemów z tworzeniem pakietów i wdrażaniem).|
|0x80cf0440|Połączenie z punktem końcowym usługi zostało zakończone.|Konto próbne lub płatne zostało zawieszone. Utwórz nowe konto próbne lub płatne i zarejestruj je ponownie.|




### <a name="next-steps"></a>Następne kroki
Jeśli te informacje dotyczące rozwiązywania problemów nie pomogły, skontaktuj się z pomocą techniczną firmy Microsoft zgodnie z opisem w temacie [How to get support for Microsoft Intune](https://docs.microsoft.com/intune-classic/troubleshoot/get-support) (Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune).
