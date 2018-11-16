---
title: Rozwiązywanie problemów z rejestrowaniem urządzeń
description: Sugestie dotyczące rozwiązywania problemów z rejestracją urządzenia.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/09/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6982ba0e-90ff-4fc4-9594-55797e504b62
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 87f49c9aafa8b6f9f281a00e4d7bd297c354f90b
ms.sourcegitcommit: 4c4e87cb0d8906085fcb7cdd170bd6b0cfeb23ff
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2018
ms.locfileid: "51511042"
---
# <a name="troubleshoot-device-enrollment-in-intune"></a>Rozwiązywanie problemów dotyczących rejestrowania urządzeń w usłudze Intune

Ten artykuł zawiera sugestie dotyczące rozwiązywania problemów z rejestracją urządzenia. Jeśli te informacje nie pomogą rozwiązać problemu, zobacz [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](get-support.md), aby znaleźć więcej sposobów uzyskania pomocy.


## <a name="initial-troubleshooting-steps"></a>Początkowe kroki rozwiązywania problemów

Przed rozpoczęciem rozwiązywania problemów sprawdź, czy usługa Intune została prawidłowo skonfigurowana w celu umożliwienia rejestracji. O tych wymaganiach dotyczących konfiguracji można przeczytać w następujących tematach:

-   [Przygotowanie do rejestracji urządzeń w usłudze Microsoft Intune](setup-steps.md)
-   [Konfigurowanie zarządzania systemem iOS i komputerami Mac](ios-enroll.md)
-   [Konfigurowanie zarządzania urządzeniami z systemem Windows](windows-enroll.md)
-   [Konfigurowanie zarządzania urządzeniami z systemem Android](android-enroll.md) — nie są wymagane dodatkowe kroki

Można również upewnić się, czy data i godzina są prawidłowo ustawione na urządzeniu użytkownika:

1. Uruchom urządzenie ponownie.
2. Upewnij się, że data i godzina są w przybliżeniu ustawione zgodnie ze standardami GMT (+ lub - 12 godzin) dla strefy czasowej użytkownika końcowego.
3. Odinstaluj i zainstaluj ponownie Portal firmy w usłudze Intune (jeśli dotyczy).

Użytkownicy urządzenia zarządzanego mogą zbierać dzienniki rejestracji i dzienniki diagnostyczne, z którymi możesz się zapoznać. Instrukcje użytkownika dotyczące zbierania tych dzienników przedstawiono w następujących tematach:

- [Wysyłanie błędów rejestracji systemu Android do administratora IT](https://docs.microsoft.com/intune-user-help/send-enrollment-errors-to-your-it-admin-android)
- [Wysyłanie błędów systemu iOS do administratora IT](https://docs.microsoft.com/intune-user-help/send-errors-to-your-it-admin-ios)


## <a name="general-enrollment-issues"></a>Ogólne problemy dotyczące rejestrowania
Te problemy mogą wystąpić na wszystkich platformach urządzeń.

### <a name="device-cap-reached"></a>Osiągnięto limit urządzeń
**Problem:** podczas rejestracji urządzenia przez użytkownika występuje błąd (na przykład **Portal firmy jest tymczasowo niedostępny**), a dziennik DMPdownloader.log programu Configuration Manager zawiera błąd **DeviceCapReached**.

**Rozwiązanie:**

#### <a name="check-number-of-devices-enrolled-and-allowed"></a>Sprawdzanie liczby zarejestrowanych i dozwolonych urządzeń

Sprawdź, czy użytkownik nie jest przypisany do większej niż maksymalna liczby urządzeń, wykonując poniższe kroki:

1. W usłudze Intune wybierz pozycję **Rejestrowanie urządzeń** > **Ograniczenia rejestracji** > **Ograniczenia limitu urządzeń**. Zanotuj wartość w kolumnie **Limit urządzeń**.

2. W usłudze Intune wybierz pozycję **Użytkownicy** > **Wszyscy użytkownicy**, wybierz użytkownika i wybierz pozycję **Urządzenia**. Zanotuj liczbę urządzeń.

3. Jeśli liczba zarejestrowanych urządzeń użytkownika jest już równa limitowi urządzeń, nie będzie można zarejestrować kolejnych urządzeń, dopóki nie zostanie wykonana jedna z następujących czynności:
    - [Usunięcie istniejących urządzeń](devices-wipe.md)
    - Zwiększenie limitu urządzeń przez [ustawienie ograniczeń urządzeń](enrollment-restrictions-set.md#set-device-limit-restrictions)

Aby uniknąć osiągania górnych limitów urządzeń, pamiętaj o usuwaniu nieaktualnych rekordów urządzeń.

> [!NOTE]
> 
> Stosowania limitu rejestracji urządzeń można uniknąć, używając konta menedżera rejestracji urządzeń zgodnie z opisem w temacie [Rejestrowanie urządzeń należących do firmy przy użyciu menedżera rejestracji urządzeń w usłudze Microsoft Intune](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
> 
> Konto użytkownika, które jest dodawane do konta Menedżerowie rejestracji urządzeń, nie będzie mogło zostać użyte do ukończenia procesu rejestrowania, jeśli dla danych logowania tego użytkownika zostaną wymuszone zasady dostępu warunkowego.

### <a name="company-portal-temporarily-unavailable"></a>Portal firmy jest tymczasowo niedostępny
**Problem:** na urządzeniu występuje błąd **Portal firmy jest tymczasowo niedostępny**.

**Rozwiązanie:**

1.  Usuń aplikację Portal firmy dla usługi Intune z urządzenia.

2.  Na urządzeniu otwórz przeglądarkę, przejdź do witryny [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) i spróbuj zalogować użytkownika.

3.  Jeśli użytkownik nie może się zalogować, powinien spróbować skorzystać z innej sieci.

4.  Jeśli ten sposób również zawiedzie, sprawdź, czy poświadczenia użytkownika zostały prawidłowo zsynchronizowane z usługą Azure Active Directory.

5.  Jeśli logowanie użytkownika przebiegnie pomyślnie, na urządzeniu z systemem iOS zostanie wyświetlony monit o zainstalowanie aplikacji Portal firmy dla usługi Intune i zarejestrowanie. Na urządzeniu z systemem Android należy ręcznie zainstalować aplikację Portal firmy dla usługi Intune, po czym będzie można ponowić próbę rejestracji.

### <a name="mdm-authority-not-defined"></a>Niezdefiniowany urząd MDM
**Problem:** występuje błąd **Nie zdefiniowano urzędu MDM**.

**Rozwiązanie:**

1.  Sprawdź, czy urząd MDM został [odpowiednio ustawiony](mdm-authority-set.md).
    
2.  Sprawdź, czy poświadczenia użytkownika zostały prawidłowo zsynchronizowane z usługą Azure Active Directory. W portalu usługi Office 365 możesz sprawdzić, czy nazwa UPN użytkownika jest zgodna z informacjami usługi Active Directory.
    Jeśli nazwa UPN jest niezgodna z informacjami z usługi Active Directory:

    1.  Wyłącz narzędzie DirSync na serwerze lokalnym.

    2.  Usuń niezgodnego użytkownika z listy użytkowników w **portalu konta usługi Intune** .

    3.  Poczekaj około jednej godziny, aby umożliwić usunięcie nieprawidłowych danych z usługi Azure.

    4.  Włącz ponownie narzędzie DirSync i sprawdź, czy użytkownik jest teraz prawidłowo synchronizowany.

3.  W przypadku, gdy używasz usługi Intune z programem System Center Configuration Manager, sprawdź, czy użytkownik ma prawidłowy identyfikator użytkownika chmury:

    1.  Otwórz program SQL Management Studio.

    2.  Nawiąż połączenie z odpowiednią bazą danych.

    3.  Otwórz folder baz danych i znajdź, a następnie otwórz folder **CM_DBName**, gdzie DBName to nazwa bazy danych klienta.

    4.  U góry wybierz pozycję **Nowa kwerenda** i wykonaj następujące zapytania:

        -   Aby wyświetlić wszystkich użytkowników: `select * from [CM_ DBName].[dbo].[User_DISC]`

        -   Aby wyświetlić konkretnych użytkowników, użyj następującego zapytania, gdzie %testuser1% jest symbolem zastępczy wartości username@domain.com dla użytkownika, którego chcesz wyszukać: `select * from [CM_ DBName].[dbo].[User_DISC] where User_Principal_Name0 like '%testuser1%'`

        Po zapisaniu zapytania wybierz pozycję **!Wykonaj**.
        Po zwróceniu wyników poszukaj identyfikatora użytkownika chmury.  Jeśli identyfikator nie zostanie znaleziony, oznacza to, że użytkownik nie ma licencji na korzystanie z usługi Intune.

### <a name="unable-to-create-policy-or-enroll-devices-if-the-company-name-contains-special-characters"></a>Nie można utworzyć zasad lub zarejestrować urządzeń, jeśli nazwa firmy zawiera znaki specjalne.
**Problem:** Nie można utworzyć zasad lub zarejestrować urządzeń.

**Rozwiązanie:** W [centrum administracyjnym usługi Office 365](https://portal.office.com/) usuń znaki specjalne z nazwy firmy i zapisz informacje o firmie.

### <a name="unable-to-sign-in-or-enroll-devices-when-you-have-multiple-verified-domains"></a>Nie można się zalogować lub zarejestrować urządzeń w przypadku korzystania z wielu zweryfikowanych domen
**Problem:** ten problem może wystąpić po dodaniu drugiej zweryfikowanej domeny do usługi AD FS. Możliwe, że użytkownicy z sufiksem głównej nazwy użytkownika (nazwy UPN) drugiej domeny nie będą mogli zalogować się do portali lub rejestrować urządzeń.


<strong>Rozwiązanie:</strong> klienci usługi Microsoft Office 365 muszą wdrożyć oddzielne wystąpienie usługi federacyjnej AD FS 2.0 na każdy sufiks, jeśli:
- korzystają z logowania jednokrotnego (SSO) za pośrednictwem usług AD FS 2.0 i
- mają wiele domen najwyższego poziomu dla sufiksów nazw głównych użytkowników w organizacji (na przykład @contoso.com lub @fabrikam.com).


[Zbiorczy pakiet aktualizacji dla usług AD FS 2.0](http://support.microsoft.com/kb/2607496) działa w połączeniu z przełącznikiem <strong>SupportMultipleDomain</strong> w celu włączenia obsługi tego scenariusza przez serwer usług AD FS bez konieczności stosowania dodatkowych serwerów usługi AD FS 2.0. Aby uzyskać więcej informacji, zobacz [ten blog](https://blogs.technet.microsoft.uucom/abizerh/2013/02/05/supportmultipledomain-switch-when-managing-sso-to-office-365/).


## <a name="android-issues"></a>Problemy z systemem android

### <a name="android-enrollment-errors"></a>Błędy rejestracji w systemie Android

Poniższa tabela zawiera listę błędów, które użytkownicy końcowi mogą napotkać podczas rejestrowania urządzeń z systemem Android w usłudze Intune.

|Komunikat o błędzie|Problem|Rozwiązanie|
|---|---|---|
|**Administrator IT musi przypisać licencję w celu udzielenia praw dostępu**<br>Administrator IT nie nadał Ci praw dostępu do korzystania z tej aplikacji. Uzyskaj pomoc od administratora IT lub spróbuj ponownie później.|Nie można zarejestrować urządzenia, ponieważ konto użytkownika nie ma potrzebnej licencji.|Aby umożliwić użytkownikom rejestrowanie urządzeń, należy przypisać im wymaganą licencję. Ten komunikat oznacza, że użytkownicy mają niewłaściwy typ licencji dla urzędu zarządzania urządzeniami mobilnymi. Na przykład użytkownicy zobaczą ten błąd, gdy spełnione są oba z następujących warunków:<ol><li>usługa Intune została ustawiona jako urząd zarządzania urządzeniami mobilnymi</li><li>używana jest licencja programu System Center 2012 R2 Configuration Manager.</li></ol>Aby uzyskać więcej informacji, zobacz [Przypisywanie licencji usługi Intune do kont użytkowników](/intune/licenses-assign).|
|**Administrator IT musi ustawić urząd MDM**<br>Wygląda na to, że administrator IT nie ustawił urzędu zarządzania urządzeniami mobilnymi. Uzyskaj pomoc od administratora IT lub spróbuj ponownie później.|Nie określono urzędu zarządzania urządzeniami mobilnymi.|Urząd zarządzania urządzeniami mobilnymi nie został ustawiony w usłudze Intune. Zobacz informacje na temat [ustawiania urzędu zarządzania urządzeniami mobilnymi](/intune/mdm-authority-set).|


### <a name="devices-fail-to-check-in-with-the-intune-service-and-display-as-unhealthy-in-the-intune-admin-console"></a>Nie można zaewidencjonować urządzeń w usłudze Intune — w konsoli administracyjnej usługi Intune stan urządzeń jest wyświetlany jako „W niedobrej kondycji”
**Problem:** zaewidencjonowywanie niektórych urządzeń firmy Samsung z systemem Android w wersji 4.4.x i 5.x przy użyciu usługi Intune może zostać zatrzymane. Jeśli nie można zaewidencjonować urządzeń:

- Nie otrzymują one zasad, aplikacji ani poleceń zdalnych z usługi Intune.
- W konsoli administracyjnej ich stan jest wyświetlany jako **W niedobrej kondycji**.
- Użytkownicy chronieni przez zasady dostępu warunkowego mogą utracić dostęp do zasobów firmowych.

Oprogramowanie Samsung Smart Menedżer dostarczane na niektórych urządzeniach Samsung może powodować dezaktywowanie aplikacji Portal firmy w usłudze Intune oraz jej składników. Zdezaktywowanej aplikacji Portal firmy nie można uruchomić w tle, co uniemożliwia nawiązywanie kontaktu z usługą Intune.

**Rozwiązanie 1:**

Poproś użytkowników o ręczne uruchomienie aplikacji Portal firmy. Po ponownym uruchomieniu aplikacji urządzenie jest zaewidencjonowywane przy użyciu usługi Intune.

> [!IMPORTANT]
> Ręczne otwieranie aplikacji Portal firmy to rozwiązanie tymczasowe, ponieważ oprogramowanie Samsung Smart Menedżer może spowodować ponowne dezaktywowanie aplikacji Portal firmy.

**Rozwiązanie 2:**

Poproś użytkowników, aby spróbowali uaktualnić do systemu Android do wersji 6.0. Problem z dezaktywacją nie występuje na urządzeniach z systemem Android 6.0. Aby sprawdzić, czy aktualizacja jest dostępna, przejdź do pozycji **Ustawienia** > **Informacje o urządzeniu** > **Pobierz aktualizacje ręcznie** i postępuj zgodnie z wyświetlanymi instrukcjami.

**Rozwiązanie 3:**

Jeśli rozwiązanie 2 nie działa, poproś użytkowników o wykonanie poniższych kroków w celu wykluczenia aplikacji Portal firmy z oprogramowania Smart Menedżer:

1. Uruchom aplikację Smart Menedżer w urządzeniu.

   ![Wybieranie ikony Smart Menedżer w urządzeniu](./media/troubleshoot-device-enrollment-in-intune/smart-manager-app-icon.png)

2. Wybierz kafelek **Bateria**.

   ![Wybieranie kafelka Bateria](./media/troubleshoot-device-enrollment-in-intune/smart-manager-battery-tile.png)

3. W obszarze **Oszczędzanie energii dla aplikacji** lub **Optymalizacja aplikacji** wybierz pozycję **Szczegóły**.

   ![Wybieranie pozycji Szczegóły w obszarze Oszczędzanie energii dla aplikacji lub Optymalizacja aplikacji](./media/troubleshoot-device-enrollment-in-intune/smart-manager-app-power-saving-detail.png)

4. Z listy aplikacji wybierz pozycję **Portal firmy**.

   ![Wybieranie pozycji Portal firmy z listy aplikacji](./media/troubleshoot-device-enrollment-in-intune/smart-manager-company-portal.png)

5. Wybierz pozycję **Wyłączono**.

   ![Wybieranie pozycji Wyłączono w oknie dialogowym Optymalizacja aplikacji](./media/troubleshoot-device-enrollment-in-intune/smart-manager-app-optimization-turned-off.png)

6. W obszarze **Oszczędzanie energii dla aplikacji** lub **Optymalizacja aplikacji** sprawdź, czy aplikacja Portal firmy została wyłączona.

   ![Sprawdzanie, czy aplikacja Portal firmy została wyłączona](./media/troubleshoot-device-enrollment-in-intune/smart-manager-verify-comp-portal-turned-off.png)


### <a name="profile-installation-failed"></a>Instalacja profilu nie powiodła się
**Problem:**  Na urządzeniu z systemem Android wystąpił błąd **Instalacja profilu nie powiodła się**.

**Rozwiązanie:**

1.  Upewnij się, że użytkownik ma przypisaną odpowiednią licencję dla używanej wersji usługi Intune.

2.  Sprawdź, czy urządzenie nie zostało już zarejestrowane za pomocą innego dostawcy MDM.

3. Upewnij się, że urządzenie nie ma jeszcze zainstalowanego profilu zarządzania.

4.  Upewnij się, że domyślną przeglądarką w systemie jest program Chrome dla systemu Android oraz że pliki cookie są włączone.

### <a name="android-certificate-issues"></a>Problemy z certyfikatami systemu Android

**Problem**: użytkownicy otrzymują następujący komunikat na urządzeniu: *Nie możesz się zalogować, ponieważ urządzenie nie ma wymaganego certyfikatu.*

**Rozwiązanie 1**:

Użytkownik może mieć możliwość pobrania brakującego certyfikatu przez wykonanie instrukcji podanych w temacie [Brak wymaganego certyfikatu urządzenia](/intune-user-help/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator). Jeśli błąd będzie się powtarzać, spróbuj zastosować rozwiązanie 2.

**Rozwiązanie 2**:

Po wprowadzeniu poświadczeń firmowych i przekierowaniu w celu obsługi logowania federacyjnego użytkownicy mogą nadal widzieć błąd braku certyfikatu. W takim przypadku ten błąd może oznaczać, że brakuje pośredniego certyfikatu z serwera usług Active Directory Federation Services (AD FS).

Błąd certyfikatu występuje, ponieważ urządzenia z systemem Android wymagają, by do [powitania serwera SSL](https://technet.microsoft.com/library/cc783349.aspx) były dołączone certyfikaty pośrednie. Obecnie domyślna instalacja serwera usług AD FS lub serwera proxy WAP usług AD FS powoduje wysłanie tylko certyfikatu SSL usług AD FS w odpowiedzi na powitanie klienta SSL.

Aby rozwiązać ten problem, zaimportuj certyfikaty do certyfikatów osobistych komputerów na serwerze usług AD FS lub serwerach proxy w następujący sposób:

1.  Na serwerach usług AD FS i serwerach proxy kliknij prawym przyciskiem myszy pozycję **Start** > **Uruchom** > **certlm.msc** w celu uruchomienia konsoli zarządzania certyfikatami komputera lokalnego.
2.  Rozwiń węzeł **Osobiste** i wybierz pozycję **Certyfikaty**.
3.  Znajdź certyfikat dla komunikacji usług AD FS (certyfikat z podpisem publicznym), a następnie kliknij go dwukrotnie, aby wyświetlić jego właściwości.
4.  Wybierz kartę **Ścieżka certyfikacji**, aby wyświetlić certyfikaty nadrzędne tego certyfikatu.
5.  Dla każdego certyfikatu nadrzędnego zaznacz opcję **Wyświetl certyfikat**.
6.  Wybierz pozycję **Szczegóły** > **Kopiuj do pliku...**.
7.  Postępuj zgodnie z instrukcjami kreatora, aby wyeksportować lub zapisać klucz publiczny certyfikatu nadrzędnego do wybranej lokalizacji pliku.
8.  Kliknij prawym przyciskiem myszy pozycje **Certyfikaty** > **Wszystkie zadania** > **Importuj**.
9.  Postępuj zgodnie z instrukcjami kreatora, aby zaimportować certyfikaty nadrzędne do katalogu **Komputer lokalny\Osobiste\Certyfikaty**.
10. Uruchom ponownie serwery usług AD FS.
11. Powtórz powyższe kroki na wszystkich serwerach usług AD FS i serwerach proxy.

Możesz sprawdzić, czy zainstalowano odpowiedni certyfikat, używając narzędzia diagnostycznego dostępnego w witrynie [https://www.digicert.com/help/](https://www.digicert.com/help/). W polu **Adres serwera** wprowadź w pełni kwalifikowaną nazwę domeny serwera usług AD FS (IE: sts.contoso.com) i kliknij przycisk **Sprawdź serwer**.

**Aby sprawdzić, czy certyfikat jest zainstalowany prawidłowo**:

Następujące kroki opisują jedną z wielu metod i narzędzi umożliwiających sprawdzenie poprawności instalacji certyfikatu.

1. Przejdź do [bezpłatnego narzędzia Digicert](ttps://www.digicert.com/help/).
2. Wprowadź w pełni kwalifikowaną nazwę domeny serwera usług AD FS (np. sts.contoso.com), a następnie wybierz pozycję **SPRAWDŹ SERWER**.

Jeśli certyfikat serwera jest zainstalowany poprawnie, w wynikach zostaną wyświetlone wszystkie znaczniki wyboru. Jeśli powyższy problem występuje nadal, zobaczysz czerwony symbol X w sekcjach raportu „Certificate Name Matches” (Zgodne nazwy certyfikatu) i „SSL Certificate is correctly Installed” (Certyfikat SSL jest zainstalowany poprawnie).


## <a name="ios-issues"></a>Problemy z systemem iOS

### <a name="ios-enrollment-errors"></a>Błędy rejestracji urządzeń z systemem iOS
Poniższa tabela zawiera listę błędów, które użytkownicy końcowi mogą napotkać podczas rejestrowania urządzeń z systemem iOS w usłudze Intune.

|Komunikat o błędzie|Problem|Rozwiązanie|
|-------------|-----|----------|
|NoEnrollmentPolicy|Nie znaleziono zasad rejestracji|Sprawdź, czy skonfigurowane zostały wszystkie wymagania wstępne rejestracji, takie jak certyfikat usługi Apple Push Notification Service (APNs), i czy opcja „iOS jako platforma” jest włączona. Aby uzyskać instrukcje, zobacz [Konfigurowanie zarządzania systemem iOS i komputerami Mac](ios-enroll.md).|
|DeviceCapReached|Zarejestrowano już zbyt wiele urządzeń przenośnych.|Aby można było zarejestrować kolejne urządzenie przenośne, użytkownik musi usunąć jedno z obecnie zarejestrowanych urządzeń przenośnych z Portalu firmy. Zapoznaj się z instrukcjami dotyczącymi odpowiedniego typu urządzenia: [Android](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-android), [iOS](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-ios) lub [Windows](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows).|
|APNSCertificateNotValid|Występuje problem z certyfikatem umożliwiającym komunikację urządzenia przenośnego z siecią firmową.<br /><br />|Usługa Apple Push Notification Service (APNs) udostępnia kanał na potrzeby kontaktu zarejestrowanych urządzeń z systemem iOS. Rejestracja zakończy się niepowodzeniem i zostanie wyświetlony ten komunikat, jeśli:<ul><li>kroki uzyskiwania certyfikatu APNs nie zostały ukończone lub</li><li>certyfikat APNs wygasł.</li></ul>Przejrzyj informacje na temat sposobu konfigurowania użytkowników w sekcjach [Synchronizacja usługi Active Directory i dodawanie użytkowników do usługi Intune](users-add.md) oraz [Organizowanie użytkowników i urządzeń](groups-add.md).|
|AccountNotOnboarded|Występuje problem z certyfikatem umożliwiającym komunikację urządzenia przenośnego z siecią firmową.<br /><br />|Usługa Apple Push Notification Service (APNs) udostępnia kanał na potrzeby kontaktu zarejestrowanych urządzeń z systemem iOS. Rejestracja zakończy się niepowodzeniem i zostanie wyświetlony ten komunikat, jeśli:<ul><li>kroki uzyskiwania certyfikatu APNs nie zostały ukończone lub</li><li>certyfikat APNs wygasł.</li></ul>Aby uzyskać więcej informacji, zobacz [Konfigurowanie zarządzania systemem iOS i komputerami Mac przez usługę Microsoft Intune](ios-enroll.md).|
|DeviceTypeNotSupported|Prawdopodobnie użytkownik wykonał próbę zarejestrowania urządzenia z systemem innymi niż iOS. Typ urządzenia przenośnego, które próbujesz zarejestrować, nie jest obsługiwany.<br /><br />Upewnij się, że na urządzeniu działa system iOS w wersji 8.0 lub nowszej.<br /><br />|Upewnij się, że na urządzeniu użytkownika działa system iOS w wersji 8.0 lub nowszej.|
|UserLicenseTypeInvalid|Nie można zarejestrować urządzenia, ponieważ konto użytkownika nie jest jeszcze członkiem wymaganej grupy użytkowników.<br /><br />|Aby użytkownicy mogli rejestrować urządzenia, muszą należeć do odpowiedniej grupy użytkowników. Ten komunikat oznacza, że użytkownicy mają niewłaściwy typ licencji dla urzędu zarządzania urządzeniami mobilnymi. Na przykład użytkownicy zobaczą ten błąd, gdy spełnione są oba z następujących warunków:<ol><li>usługa Intune została ustawiona jako urząd zarządzania urządzeniami mobilnymi</li><li>używana jest licencja programu System Center 2012 R2 Configuration Manager.</li></ol>Przejrzyj poniższe artykuły, aby uzyskać więcej informacji:<br /><br />Zobacz [Konfigurowanie zarządzania systemem iOS i komputerami Mac przez usługę Microsoft Intune](ios-enroll.md), a także informacje o sposobie konfigurowania użytkowników w temacie [Synchronizacja usługi Active Directory i dodawanie użytkowników do usługi Intune](users-add.md) oraz [Organizowanie użytkowników i urządzeń](groups-add.md).|
|MdmAuthorityNotDefined|Nie określono urzędu zarządzania urządzeniami mobilnymi.<br /><br />|Urząd zarządzania urządzeniami mobilnymi nie został ustawiony w usłudze Intune.<br /><br />Zapoznaj się z pozycją 1 w sekcji „Krok 6. Rejestrowanie urządzeń przenośnych i instalowanie aplikacji” w temacie [Rozpoczynanie pracy z 30-dniową wersją próbną usługi Microsoft Intune](free-trial-sign-up.md).|

### <a name="devices-are-inactive-or-the-admin-console-cant-communicate-with-them"></a>Urządzenia są nieaktywne lub nie jest możliwe nawiązanie łączności między nimi a konsolą administracyjną
**Problem:** urządzenia z systemem iOS nie są ewidencjonowane przy użyciu usługi Intune. Urządzenia muszą być okresowo zaewidencjonowane w celu umożliwienia im dalszego dostępu do chronionych zasobów firmy. Jeśli nie można zaewidencjonować urządzeń:

- Nie otrzymują one zasad, aplikacji ani poleceń zdalnych z usługi Intune.
- W konsoli administracyjnej ich stan jest wyświetlany jako **W niedobrej kondycji**.
- Użytkownicy chronieni przez zasady dostępu warunkowego mogą utracić dostęp do zasobów firmowych.

**Rozwiązanie:** podaj użytkownikom końcowym następujące rozwiązania, aby pomóc im odzyskać dostęp do zasobów firmy.

Po uruchomieniu w systemie iOS aplikacja Portal firmy sprawdza, czy urządzenie użytkownika nie utraciło łączności z usługą Intune. Jeśli aplikacja wykryje brak połączenia, automatycznie podejmie próbę synchronizacji z usługą Intune w celu ponownego nawiązania połączenia (użytkownicy zobaczą komunikat **Trwa próba wykonania synchronizacji...** ).

  ![Powiadomienie o trwającej próbie wykonania synchronizacji](./media/troubleshoot-device-enrollment-in-intune/ios_cp_app_trying_to_sync_notification.png)

Jeśli synchronizacja zakończy się pomyślnie, zobaczysz w aplikacji Portal firmy w systemie iOS powiadomienie **Synchronizacja powiodła się** wskazujące, że urządzenie jest w prawidłowym stanie.

  ![Powiadomienie informujące, że synchronizacja powiodła się](./media/troubleshoot-device-enrollment-in-intune/ios_cp_app_sync_successful_notification.png)

Jeśli synchronizacja nie powiedzie się, użytkownicy zobaczą w aplikacji Portal firmy w systemie iOS powiadomienie o treści **Nie można zsynchronizować**.

  ![Powiadomienie o nieudanej próbie synchronizacji](./media/troubleshoot-device-enrollment-in-intune/ios_cp_app_unable_to_sync_notification.png)

Aby rozwiązać ten problem, użytkownicy muszą użyć przycisku **Konfiguruj** znajdującego się na prawo od powiadomienia **Nie można zsynchronizować**. Przycisk Konfiguruj umożliwia przejście do ekranu przepływu Konfiguracja dostępu do zasobów firmy. Postępując zgodnie z monitami wyświetlanymi na tej stronie, można zarejestrować swoje urządzenie.

  ![Ekran Konfiguracja dostępu do zasobów firmy](./media/troubleshoot-device-enrollment-in-intune/ios_cp_app_company_access_setup.png)

Po zarejestrowaniu urządzenie powraca do stanu prawidłowego i odzyskuje dostęp do zasobów firmy.

### <a name="verify-ws-trust-13-is-enabled"></a>Sprawdzanie, czy usługa WS-Trust 1.3 jest włączona
**Problem** Nie można zarejestrować urządzeń z systemem iOS objętych programem Device Enrollment Program (DEP)

Rejestrowanie urządzeń objętych programem DEP z koligacją użytkownika wymaga włączenia punktu końcowego WS-Trust 1.3 Username/Mixed, aby móc żądać tokenów użytkowników. Usługa Active Directory domyślnie włącza ten punkt końcowy. Punktu końcowego trust/13/UsernameMixed należy szukać na liście włączonych punktów końcowych dostępnej za pośrednictwem polecenia cmdlet programu PowerShell Get-AdfsEndpoint. Przykład:

      Get-AdfsEndpoint -AddressPath “/adfs/services/trust/13/UsernameMixed”

Więcej informacji można znaleźć w [dokumentacji polecenia Get-AdfsEndpoint](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

Aby uzyskać więcej informacji, zobacz artykuł [Najlepsze rozwiązania dotyczące zabezpieczania Usług federacyjnych Active Directory](https://technet.microsoft.com/windows-server-docs/identity/ad-fs/operations/best-practices-securing-ad-fs). Jeśli potrzebujesz dodatkowej pomocy w określeniu, czy punkt końcowy WS-Trust 1.3 Username/Mixed jest włączony u Twojego dostawcy federacyjnego tożsamości:
- skontaktuj się z pomocą techniczną firmy Microsoft, jeśli korzystasz z usługi AD FS, lub
- skontaktuj się z dostawcą tożsamości innej firmy.


### <a name="profile-installation-failed"></a>Instalacja profilu nie powiodła się
**Problem:**  Na urządzeniu z systemem iOS wystąpił błąd **Instalacja profilu nie powiodła się**.

### <a name="troubleshooting-steps-for-failed-profile-installation"></a>Kroki rozwiązywania problemów dotyczących niepowodzenia instalacji profilu

1.  Upewnij się, że użytkownik ma przypisaną odpowiednią licencję dla używanej wersji usługi Intune.

2.  Sprawdź, czy urządzenie nie zostało już zarejestrowane za pomocą innego dostawcy MDM.

3. Upewnij się, że urządzenie jeszcze nie ma zainstalowanego profilu zarządzania.

4.  Gdy zostanie wyświetlony monit, przejdź do witryny [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) i spróbuj zainstalować profil.

5.  Upewnij się, że domyślną przeglądarką jest program Safari dla systemu iOS oraz że pliki cookie są włączone.

### <a name="enrolled-ios-device-doesnt-appear-in-console-when-using-system-center-configuration-manager-with-intune"></a>Zarejestrowane urządzenie z systemem iOS nie jest wyświetlane w konsoli podczas korzystania z programu System Center Configuration Manager z usługą Intune
**Problem:** Użytkownik rejestruje urządzenie z systemem iOS, ale nie jest ono wyświetlane w konsoli administracyjnej programu Configuration Manager. Urządzenie nie wskazuje, że zostało zarejestrowane. Możliwe przyczyny:

- Łącznik usługi Microsoft Intune w lokacji programu Configuration Manager nie łączy się z usługą Intune.
- Składnik Menedżera danych odnajdywania (ddm) lub składnik Menedżera stanu (statmgr) nie przetwarza komunikatów z usługi Intune.
- Możliwe, że pobrano certyfikat zarządzania urządzeniami przenośnymi z jednego konta i użyto go na innym koncie.


**Rozwiązanie:** Przejrzyj następujące pliki dziennika pod kątem możliwych błędów:

- dmpdownloader.log
- ddm.log
- statmgr.log

Przykłady zawartości, pod kątem obecności której należy sprawdzić pliki dziennika, zostaną dodane wkrótce.


### <a name="users-ios-device-is-stuck-on-an-enrollment-screen-for-more-than-10-minutes"></a>Urządzenie użytkownika z systemem iOS jest zablokowane na ekranie rejestracji przez więcej niż 10 minut

**Problem**: Rejestrowane urządzenie może zostać zablokowane na jednym z dwóch ekranów:
- Awaiting final configuration from “Microsoft” (Oczekiwanie na konfigurację końcową od firmy Microsoft)
- Guided Access app unavailable (Aplikacja Guided Access jest niedostępna). Skontaktuj się z administratorem.

Ten problem może wystąpić w następujących sytuacjach:
- wystąpiła tymczasowa awaria usług firmy Apple lub
- rejestrowanie urządzeń z systemem iOS jest skonfigurowane do używania tokenów programu VPP, jak pokazano w tabeli, ale coś jest nie tak z tokenem VPP.

| Ustawienia rejestracji | Wartość |
| ---- | ---- |
| Platforma | iOS |
| Koligacja użytkownika | Zarejestruj z użyciem koligacji użytkowników |
|Uwierzytelnij za pomocą aplikacji Portal firmy zamiast Asystenta konfiguracji firmy Apple | Tak |
| Instalowanie aplikacji Portal firmy przy użyciu programu VPP | Użyj tokenu: adres tokenu |
| Uruchom aplikację Portal firmy w trybie pojedynczej aplikacji do momentu uwierzytelnienia | Tak |

**Rozwiązanie**: Aby rozwiązać problem, musisz:
1. Określić, czy wystąpił problem z tokenem VPP i naprawić go.
2. Zidentyfikować urządzenia, które są blokowane.
3. Wyczyścić urządzenia, których dotyczy problem.
4. Poprosić użytkowników o ponowne uruchomienie procesu rejestracji.

#### <a name="determine-if-theres-something-wrong-with-the-vpp-token"></a>Określanie, czy wystąpił problem z tokenem VPP
1. Przejdź do pozycji **Intune** > **Rejestrowanie urządzeń** > **Rejestracja Apple** > **Tokeny programu rejestracji** > nazwa tokenu > **Profile** > nazwa profilu > **Zarządzaj** > **Właściwości**.
2. Przejrzyj właściwości, aby zobaczyć, czy są wyświetlane jakiekolwiek błędy podobne do następujących:
    - Ten token wygasł.
    - Ten token nie ma licencji aplikacji Portal firmy.
    - Ten token jest używany przez inną usługę.
    - Ten token jest używany przez inną dzierżawę.
    - Ten token został usunięty.
3. Rozwiąż problemy dotyczące tokenu.

#### <a name="identify-which-devices-are-blocked-by-the-vpp-token"></a>Identyfikowanie urządzeń, które są blokowane przez token programu VPP
1. Przejdź do pozycji **Intune** > **Rejestrowanie urządzeń** > **Rejestracja Apple** > **Tokeny programu rejestracji** > nazwa tokenu > **Urządzenia**.
2. Filtruj kolumnę **Stan profilu** według wartości **Zablokowane**.
3. Zanotuj numery seryjne wszystkich urządzeń, które są **Zablokowane**.

#### <a name="remotely-wipe-the-blocked-devices"></a>Zdalne czyszczenie zablokowanych urządzeń
Po rozwiązaniu problemów z tokenem VPP należy wyczyścić urządzenia, które są blokowane.
1. Wybierz kolejno pozycje **Intune** > **Urządzenia** > **Wszystkie urządzenia** > **Kolumny**  >  **Numer seryjny** > **Zastosuj**. 
2. W przypadku każdego zablokowanego urządzenia wybierz je na liście **Wszystkie urządzenia**, a następnie wybierz pozycje **Czyszczenie danych** > **Tak**.

#### <a name="tell-the-users-to-restart-the-enrollment-process"></a>Informowanie użytkowników, aby ponownie uruchomili proces rejestracji
Po wyczyszczeniu zablokowanych urządzeń możesz poprosić użytkowników o ponowne uruchomienie procesu rejestracji.

## <a name="macos-issues"></a>Problemy z systemem macOS

### <a name="macos-enrollment-errors"></a>Błędy rejestracji systemu macOS
**Komunikat o błędzie 1:** *Prawdopodobnie używasz maszyny wirtualnej. Upewnij się, że została ona w pełni skonfigurowana, łącznie z numerem seryjnym i modelem sprzętu. Jeśli to nie jest maszyna wirtualna, skontaktuj się z pomocą techniczną.*  

**Komunikat o błędzie 2:** *Mamy problem z objęciem urządzenia zarządzaniem. Ten problem może być spowodowany tym, że używasz maszyny wirtualnej, masz zastrzeżony numer seryjny albo to urządzenie jest już przypisane do kogoś innego. Dowiedz się, jak rozwiązać te problemy, lub skontaktuj się z pomocą techniczną w swojej firmie.*

**Problem:** Przyczyny tego komunikatu mogą być następujące:  
* Maszyna wirtualna z systemem macOS nie jest skonfigurowana poprawnie  
* Włączono ograniczenia dotyczące urządzeń, w myśl których urządzenie musi należeć do firmy lub mieć numer seryjny zarejestrowany w usłudze Intune  
* Urządzenie zostało już zarejestrowane i ciągle jest przypisane w usłudze Intune do kogoś innego  

**Rozwiązanie:** Najpierw skontaktuj się z użytkownikiem i dowiedz się, jakie problemy ma ze swoim urządzeniem. Następnie zastosuj najtrafniejsze z następujących rozwiązań:
* Jeśli użytkownik rejestruje maszynę wirtualną do testowania, upewnij się, że została w pełni skonfigurowana, aby usługa Intune mogła rozpoznać jej numer seryjny i model sprzętu. Dowiedz się więcej na temat tego, jak [konfigurować maszyny wirtualne](macos-enroll.md#enroll-virtual-macos-machines-for-testing) w usłudze Intune.  
* Jeśli w organizacji masz włączone ograniczenia rejestracji, które blokują urządzenia osobiste z systemem macOS, musisz ręcznie [dodać numer seryjny urządzenia osobistego](corporate-identifiers-add.md#manually-enter-corporate-identifiers) do usługi Intune.  
* Jeśli urządzenie jest nadal przypisane do innego użytkownika w usłudze Intune, jego poprzedni właściciel nie użył aplikacji Portal firmy do usunięcia lub zresetowania go. Aby wyczyścić nieaktualny rekord urządzenia z usługi Intune:  

    1. Przejdź do [usługi Intune w witrynie Azure Portal](https://portal.manage.microsoft.com) i zaloguj się przy użyciu poświadczeń administracyjnych.
    2. Przejdź do pozycji Intune > **Urządzenia** > **Wszystkie urządzenia**.  
    3. Znajdź urządzenie, dla którego występuje problem z rejestracją. Ogranicz liczbę wyników, wyszukując według nazwy urządzenia lub adresu MAC/sprzętu.
    4. Wybierz urządzenie, a następnie pozycję **Usuń**. Usuń wszystkie inne wpisy skojarzone z urządzeniem.  

## <a name="issues-when-using-system-center-configuration-manager-with-intune"></a>Problemy dotyczące korzystania z programu System Center Configuration Manager z usługą Intune
### <a name="mobile-devices-disappear"></a>Urządzenia przenośne znikają
**Problem:** Po pomyślnym zarejestrowaniu urządzenia przenośnego w programie Configuration Manager znika ono z kolekcji urządzeń przenośnych, ale nadal posiada profil zarządzania i znajduje się na liście w obszarze Brama CSS.

**Rozwiązanie:** Możliwe przyczyny wystąpienia tego problemu:
- istnieje niestandardowy proces usuwania urządzeń, które nie są przyłączone do domeny, lub 
- użytkownik wycofał urządzenie z subskrypcji.
Aby to zweryfikować i sprawdzić, który proces lub które konto użytkownika usunęło urządzenie z konsoli programu Configuration Manager, wykonaj następujące kroki.

#### <a name="check-how-device-was-removed"></a>Sprawdzanie sposobu usunięcia urządzenia

1.  W konsoli administracyjnej programu Configuration Manager wybierz pozycje **Monitorowanie** &gt; **Stan systemu** &gt; **Kwerendy komunikatów o stanie**.

2.  Kliknij prawym przyciskiem myszy pozycję **Ręcznie usunięte zasoby członka kolekcji** i wybierz polecenie **Pokaż komunikaty**.

3.  Wybierz odpowiednią datę i godzinę lub ostatnie 12 godzin.

4.  Znajdź dane urządzenie i sprawdź, jak zostało ono usunięte. W poniższym przykładzie pokazano sytuację, w której konto SCCMInstall usunęło urządzenie za pomocą nieznanej aplikacji.

    ![Zrzut ekranu przedstawiający diagnostykę usuwania urządzeń](./media/troubleshoot-device-enrollment-in-intune/CM_With_Intune_Unknown_App_Deleted_Device.jpg)

5.  Upewnij się, że program Configuration Manager nie ma zaplanowanego zadania, skryptu ani innego procesu, który mógłby automatycznie usuwać urządzenia nienależące do domeny, urządzenia przenośne lub pokrewne.

### <a name="other-ios-enrollment-errors"></a>Inne błędy rejestracji urządzeń z systemem iOS
Lista błędów rejestracji urządzeń z systemem iOS znajduje się w naszej dokumentacji w artykule [Rozwiązywanie problemów z rejestracją urządzeń z systemem iOS w usłudze Microsoft Intune](https://support.microsoft.com/help/4039809/troubleshooting-ios-device-enrollment-in-intune).

## <a name="pc-issues"></a>Problemy z komputerem PC

|Komunikat o błędzie|Problem|Rozwiązanie|
|---|---|---|
|**Administrator IT musi przypisać licencję w celu udzielenia praw dostępu**<br>Administrator IT nie nadał Ci praw dostępu do korzystania z tej aplikacji. Uzyskaj pomoc od administratora IT lub spróbuj ponownie później.|Nie można zarejestrować urządzenia, ponieważ konto użytkownika nie ma potrzebnej licencji.|Aby umożliwić użytkownikom rejestrowanie urządzeń, należy przypisać im wymaganą licencję. Ten komunikat oznacza, że użytkownicy mają niewłaściwy typ licencji dla urzędu zarządzania urządzeniami mobilnymi. Na przykład użytkownicy zobaczą ten błąd, gdy spełnione są oba z następujących warunków: <ol><li>usługa Intune została ustawiona jako urząd zarządzania urządzeniami mobilnymi</li><li>używana jest licencja programu System Center 2012 R2 Configuration Manager.</li></ol>Zobacz informacje na temat [przypisywania licencji usługi Intune do kont użytkowników](https://docs.microsoft.com/intune/licenses-assign).|



### <a name="the-machine-is-already-enrolled---error-hr-0x8007064c"></a>Maszyna jest już zarejestrowana — błąd hr 0x8007064c
**Problem:** Rejestracja kończy się niepowodzeniem z powodu błędu **Maszyna jest już zarejestrowana**. Dziennik rejestracji zawiera błąd **hr 0x8007064c**.

Ten błąd może wystąpić, ponieważ komputer:
- został już wcześniej zarejestrowany lub
- zawiera sklonowany obraz komputera, który został już zarejestrowany.
Certyfikat poprzedniego konta nadal istnieje na komputerze.

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
    > Aby uzyskać więcej informacji na temat tworzenia kopii zapasowej i przywracania rejestru, przeczytaj temat [Jak wykonać kopię zapasową i przywrócić rejestr w systemie Windows XP](https://support.microsoft.com/kb/322756).

## <a name="general-enrollment-error-codes"></a>Ogólne kody błędów rejestracji

|Kod błędu|Możliwy problem|Sugerowane rozwiązanie|
|--------------|--------------------|----------------------------------------|
|0x80CF0437 |W zegarze na komputerze klienckim nie ustawiono prawidłowego czasu.|Upewnij się, że dla zegara i strefy czasowej na komputerze klienckim ustawiono prawidłową godzinę i strefę czasową.|
|0x80240438, 0x80CF0438, 0x80CF402C|Nie można nawiązać połączenia z usługą Intune. Sprawdź ustawienia serwera proxy klienta.|Sprawdź, czy usługa Intune obsługuje konfigurację serwera proxy na komputerze klienckim. Sprawdź, czy komputer kliencki ma dostęp do Internetu.|
|0x80240438, 0x80CF0438|Nie skonfigurowano ustawień serwera proxy w programie Internet Explorer i w systemie lokalnym.|Nie można nawiązać połączenia z usługą Intune. Sprawdź ustawienia serwera proxy klienta. Sprawdź, czy usługa Intune obsługuje konfigurację serwera proxy na komputerze klienckim. Sprawdź, czy komputer kliencki ma dostęp do Internetu.|
|0x80043001, 0x80CF3001, 0x80043004, 0x80CF3004|Pakiet rejestracyjny jest nieaktualny.|Pobierz i zainstaluj bieżący pakiet oprogramowania klienckiego z poziomu obszaru roboczego Administrator.|
|0x80043002, 0x80CF3002|Konto jest w trybie konserwacji.|Nie można zarejestrować nowych komputerów klienckich, gdy konto jest w trybie konserwacji. Aby wyświetlić ustawienia Twojego konta, zaloguj się do niego.|
|0x80043003, 0x80CF3003|Konto zostało usunięte.|Sprawdź, czy Twoje konto i subskrypcja usługi Intune są nadal aktywne. Aby wyświetlić ustawienia Twojego konta, zaloguj się do niego.|
|0x80043005, 0x80CF3005|Komputer kliencki został wycofany.|Poczekaj kilka godzin, usuń wszelkie wcześniejsze wersje oprogramowania klienckiego z komputera, a następnie ponów próbę instalacji oprogramowania klienckiego.|
|0x80043006, 0x80CF3006|Osiągnięto maksymalną liczbę dozwolonych stanowisk dla konta.|Twoja organizacja musi zakupić dodatkowe licencje na stanowiska, aby można było zarejestrować więcej komputerów klienckich w usłudze.|
|0x80043007, 0x80CF3007|Nie można odnaleźć pliku certyfikatu w folderze programu instalacyjnego.|Wyodrębnij wszystkie pliki przed rozpoczęciem instalacji. Nie zmieniaj nazw wyodrębnionych plików ani ich nie przenoś: wszystkie pliki muszą znajdować się w tym samym folderze — w przeciwnym razie instalacja się nie powiedzie.|
|0x8024D015, 0x00240005, 0x80070BC2, 0x80070BC9, 0x80CFD015|Nie można zainstalować oprogramowania, ponieważ komputer kliencki oczekuje na ponowne uruchomienie.|Uruchom ponownie komputer, a następnie ponów próbę instalacji oprogramowania klienckiego.|
|0x80070032|Na komputerze klienckim nie odnaleziono co najmniej jednego wymagania wstępnego dotyczącego instalacji oprogramowania klienckiego.|Upewnij się, że na komputerze klienckim są zainstalowane wszystkie wymagane aktualizacje, a następnie ponów próbę instalacji oprogramowania klienckiego.|
|0x80043008, 0x80CF3008|Uruchomienie usługi Microsoft Online Management Updates nie powiodło się.|Skontaktuj się z pomocą techniczną zgodnie z opisem w temacie [How to get support for Microsoft Intune](get-support.md) (Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune).|
|0x80043009, 0x80CF3009|Komputer kliencki jest już zarejestrowany w usłudze.|Aby móc ponownie zarejestrować komputer kliencki w usłudze, musisz go najpierw wycofać.|
|0x8004300B, 0x80CF300B|Nie można uruchomić pakietu instalacyjnego oprogramowania klienckiego, ponieważ wersja systemu Windows uruchomiona na kliencie jest nieobsługiwana.|Usługa Intune nie obsługuje wersji systemu Windows uruchomionej na komputerze klienckim.|
|0xAB2|Instalator Windows nie może uzyskać dostępu do środowiska wykonawczego VBScript w celu wykonania akcji niestandardowej.|Przyczyną tego błędu jest próba wykonania akcji niestandardowej opartej na dołączanych dynamicznie bibliotekach (DLL). Podczas rozwiązywania problemu z biblioteką DLL może być konieczne użycie narzędzi opisanych w artykule KB198038 z bazy wiedzy pomocy technicznej firmy Microsoft: [Useful Tools for Package and Deployment Issues](https://support.microsoft.com/kb/198038) (Przydatne narzędzia w przypadku problemów z tworzeniem pakietów i wdrażaniem).|
|0x80cf0440|Połączenie z punktem końcowym usługi zostało zakończone.|Konto próbne lub płatne zostało zawieszone. Utwórz nowe konto próbne lub płatne i zarejestruj je ponownie.|




### <a name="next-steps"></a>Następne kroki
Jeśli te informacje dotyczące rozwiązywania problemów nie pomogły, skontaktuj się z pomocą techniczną firmy Microsoft zgodnie z opisem w temacie [How to get support for Microsoft Intune](get-support.md) (Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune).
