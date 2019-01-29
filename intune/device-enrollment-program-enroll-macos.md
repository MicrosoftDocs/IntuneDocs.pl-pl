---
title: Rejestrowanie urządzeń z systemem macOS — program Device Enrollment Program lub usługa Apple School Manager
titleSuffix: ''
description: Informacje dotyczące rejestrowania firmowych urządzeń z systemem macOS przy użyciu programu Device Enrollment Program.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 91d85182ccb51968915511d6d1941a350e3a9695
ms.sourcegitcommit: 06f62ae989da6c60bac4a52ccd41b429f7367d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2019
ms.locfileid: "55068292"
---
# <a name="automatically-enroll-macos-devices-with-the-device-enrollment-program-or-apple-school-manager"></a>Automatyczne rejestrowanie urządzeń z systemem macOS w ramach programu Device Enrollment Program lub usługi Apple School Manager

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Możesz skonfigurować rejestrację w usłudze Intune urządzeń z systemem macOS zakupionych w ramach programu [Device Enrollment Program (DEP) ](https://deploy.apple.com) lub usługi [Apple School Manager](https://school.apple.com/) firmy Apple. Każdej z tych rejestracji można używać dla dużej liczby urządzeń, nawet ich nie dotykając. Urządzenia z systemem macOS można wysłać bezpośrednio do użytkowników. Gdy użytkownik włączy urządzenie, zostanie uruchomiony Asystent konfiguracji ze wstępnie skonfigurowanymi ustawieniami, a urządzenie zostanie zarejestrowane w funkcji zarządzania usługi Intune.

Do konfigurowania rejestracji są wymagane portale usługi Intune oraz programu DEP firmy Apple. Możliwe jest utworzenie profilów rejestracji zawierających ustawienia stosowane względem urządzeń podczas rejestracji.

Rejestracja w ramach programu DEP ani usługi Apple School Manager nie działa z [menedżerem rejestracji urządzeń](device-enrollment-manager-enroll.md).

<!--
**Steps to enable enrollment programs from Apple**
1. [Get an Apple DEP token and assign devices](#get-the-apple-dep-token)
2. [Create an enrollment profile](#create-an-apple-enrollment-profile)
3. [Synchronize DEP-managed devices](#sync-managed-device)
4. [Assign DEP profile to devices](#assign-an-enrollment-profile-to-devices)
5. [Distribute devices to users](#end-user-experience-with-managed-devices)
-->
## <a name="prerequisites"></a>Wymagania wstępne
- Urządzenia zakupione za pośrednictwem usługi [Apple School Manager](https://school.apple.com/) lub programu [Device Enrollment Program firmy Apple](http://deploy.apple.com)
- Lista numerów seryjnych lub numerów zamówień zakupu. 
- [Urząd zarządzania urządzeniami przenośnymi](mdm-authority-set.md)
- [Certyfikat wypychania MDM firmy Apple](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Uzyskiwanie tokenu DEP od firmy Apple

Aby zarejestrować urządzenia z systemem macOS w ramach programu DEP lub usługi Apple School Manager, należy uzyskać token programu DEP (plik p7m) od firmy Apple. Ten token umożliwia usłudze Intune synchronizację informacji dotyczących urządzeń należących do firmy. Ponadto pozwala on usłudze Intune na przekazywanie profili rejestracji do firmy Apple i do tych profili w urządzeniach.

Do tworzenia tokenu służy witryna Azure Portal. W portalu firmy Apple można również przypisać urządzenia do funkcji zarządzania usługi Intune.

> [!NOTE]
> Jeśli usuniesz token z portalu klasycznego usługi Intune przed migracją na platformę Azure, usługa Intune może przywrócić usunięty token firmy Apple. Możesz ponownie usunąć token z poziomu witryny Azure Portal.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-the-token"></a>Krok 1. Pobierz certyfikat klucza publicznego usługi Intune wymagany do utworzenia tokenu.

1. W usłudze [Intune w witrynie Azure Portal](https://aka.ms/intuneportal) wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > **Dodaj**.

    ![Pobierz token programu rejestracji.](./media/device-enrollment-program-enroll-ios/image01.png)

2. Udziel firmie Microsoft uprawnień do wysyłania informacji o użytkowniku i urządzeniu do firmy Apple, wybierając pozycję **Zgadzam się**.

   ![Zrzut ekranu przedstawiający okienko tokenu programu Enrollment Program w obszarze roboczym certyfikatów firmy Apple umożliwiające pobranie klucza publicznego.](./media/device-enrollment-program-enroll-ios-newui/add-enrollment-program-token-pane.png)

3. Wybierz pozycję **Pobierz klucz publiczny**, aby pobrać i zapisać lokalnie plik klucza szyfrowania (PEM). Plik pem jest używany na potrzeby żądania certyfikatu relacji zaufania z portalu firmy Apple.


### <a name="step-2-use-your-key-to-download-a-token-from-apple"></a>Krok 2. Aby pobrać token Apple, należy użyć swojego klucza.

1. Wybierz pozycję **Utwórz token programu Device Enrollment Program firmy Apple** lub **Utwórz token w usłudze Apple School Manager**, aby otworzyć portal programu wdrażania firmy Apple i zalogować się przy użyciu firmowego konta Apple ID. Tego identyfikatora firmy Apple możesz użyć do odnowienia tokenu.
2.  W przypadku programu DEP w portalu firmy Apple wybierz pozycję **Get Started** (Wprowadzenie) dla obszaru **Device Enrollment Program** > **Manage Servers** > **Add MDM Server** (Device Enrollment Program > Zarządzanie serwerami > Dodaj serwer MDM).
3.  W przypadku usługi Apple School Manager w portalu firmy Apple wybierz kolejno pozycje **MDM Servers** > **Add MDM Server** (Serwery MDM > Dodaj serwer MDM).
4. Wprowadź nazwę serwera w polu **MDM Server Name** (Nazwa serwera MDM), a następnie wybierz przycisk **Next**(Dalej). Nazwa serwera służy użytkownikowi do identyfikowania serwera MDM. Nie jest to nazwa ani adres URL serwera usługi Microsoft Intune.

5. Zostanie otwarte okno dialogowe **Add &lt;nazwa_serwera&gt;** (Dodawanie serwera <nazwa_serwera>) z widocznym komunikatem **Upload Your Public Key** (Przekaż klucz publiczny). Kliknij pozycję **Choose File…** (Wybierz plik...) w celu przekazania pliku PEM, a następnie kliknij przycisk **Next** (Dalej).

6. Wybierz kolejno pozycje **Deployment Programs** (Programy wdrażania)&gt; **Device Enrollment Program** (Program rejestracji urządzeń) &gt; **Manage Devices** (Zarządzaj urządzeniami).
7. W obszarze **Choose Devices By** (Sposób wybierania urządzeń) określ sposób identyfikowania urządzeń:
    - **Serial Number** (Numer seryjny)
    - **Order Number** (Numer zamówienia)
    - **Upload CSV File** (Przekaż plik CSV).

   ![Zrzut ekranu przedstawiający wybraną opcję wybierania urządzeń według numerów seryjnych, akcję po wybraniu ustawioną jako przypisywanie do serwera oraz wybraną nazwę serwera.](./media/enrollment-program-token-specify-serial.png)

8. W kroku **Choose Action** (Wybierz akcję) wybierz pozycję **Assign to Server** (Przypisz do serwera), wybierz &lt;nazwę serwera&gt; określoną dla usługi Microsoft Intune, a następnie kliknij przycisk **OK**. Portal firmy Apple przypisze wskazane urządzenia do funkcji zarządzania na serwerze Intune, a następnie wyświetli komunikat **Assignment Complete** (Przypisanie zostało ukończone).

### <a name="step-3-save-the-apple-id-used-to-create-this-token"></a>Krok 3. Zapisz identyfikator Apple ID użyty do utworzenia tokenu

W usłudze Intune w witrynie Azure Portal podaj identyfikator Apple ID do użytku w przyszłości.

![Zrzut ekranu przedstawiający wprowadzanie identyfikatora Apple ID używanego do utworzenia tokenu programu rejestracji i przechodzenie do tokenu programu rejestracji.](./media/device-enrollment-program-enroll-ios/image03.png)

### <a name="step-4-upload-your-token"></a>Krok 4. Przekaż token.
W polu **Token Apple** przejdź do pliku certyfikatu (.pem), wybierz pozycję **Otwórz**, a następnie kliknij **Utwórz**. Dzięki certyfikatowi wypychania usługa Intune może rejestrować urządzenia z systemem macOS i zarządzać nimi, wypychając zasady do zarejestrowanych urządzeń. Usługa Intune automatycznie synchronizuje dane z firmą Apple, co pozwala wyświetlić konto programu rejestracji.

## <a name="create-an-apple-enrollment-profile"></a>Tworzenie profilu rejestracji firmy Apple

Teraz, po zainstalowaniu tokenu, możesz utworzyć profil rejestracji dla urządzeń. Profil rejestracji urządzeń określa ustawienia stosowane do grupy urządzeń podczas rejestracji.

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu Enrollment Program**.
2. Wybierz token, wybierz pozycję **Profile**, a następnie wybierz pozycję **Utwórz profil**.

    ![Utwórz zrzut ekranu profilu.](./media/device-enrollment-program-enroll-ios/image04.png)

3. W obszarze **Utwórz profil** wprowadź nazwę w polu **Nazwa** i opis w polu **Opis**. Informacje te będą używane do celów administracyjnych. Te szczegóły nie są widoczne dla użytkowników. Możesz użyć pola **Nazwa**, aby utworzyć grupę dynamiczną w usłudze Azure Active Directory. Nazwa profilu umożliwia zdefiniowanie parametru enrollmentProfileName w celu przypisania urządzeń z tym profilem rejestracji. Dowiedz się więcej o [grupach dynamicznych usługi Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects).

    ![Nazwa i opis profilu.](./media/device-enrollment-program-enroll-macos/createprofile.png)

4. W opcji **Platforma** wybierz pozycję **macOS**.

5. Dla pozycji **Koligacja użytkownika** wybierz, czy urządzenia z tym profilem muszą być rejestrowane z przypisanym użytkownikiem, czy bez niego.
    - **Zarejestruj z koligacją użytkownika** — tę opcję należy wybrać w przypadku urządzeń należących do użytkowników, którzy chcą korzystać z aplikacji Portal firmy w celu korzystania z usług takich, jak instalowanie aplikacji. W przypadku korzystania z usług ADFS koligacja użytkownika wymaga [nazwy użytkownika protokołu WS-Trust 1.3/mieszanego punktu końcowego](https://technet.microsoft.com/library/adfs2-help-endpoints). [Dowiedz się więcej](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint). Uwierzytelnianie wieloskładnikowe nie jest obsługiwane przez urządzenia DEP z systemem macOS z koligacją użytkownika.

    - **Zarejestruj bez koligacji użytkownika** — tę opcję należy wybrać w przypadku urządzeń, dla których nie istnieje koligacja z żadnym użytkownikiem. Można jej używać dla urządzeń, które wykonują zadania bez uzyskiwania dostępu do lokalnych danych użytkowników. Aplikacje, takie jak Portal firmy, nie działają.

6. Wybierz pozycję **Ustawienia zarządzania urządzeniami** i zdecyduj, czy chcesz rejestracji zablokowanej dla urządzeń korzystających z tego profilu. **Rejestracja zablokowana** wyłącza ustawienia systemu macOS, które umożliwiają usunięcie profilu zarządzania za pośrednictwem menu **Preferencje systemowe** lub **Terminal**. Po rejestracji urządzenia nie można zmienić tego ustawienia bez wyczyszczenia danych z urządzenia.

    ![Zrzut ekranu pozycji Ustawienia zarządzania urządzeniami.](./media/device-enrollment-program-enroll-macos/devicemanagementsettingsblade-macos.png)
 
7. Wybierz przycisk **OK**.

8. Wybierz pozycję **Ustawienia Asystenta ustawień**, aby skonfigurować następujące ustawienia profilu:  ![Dostosowanie Asystenta ustawień.](./media/device-enrollment-program-enroll-macos/setupassistantcustom-macos.png)

    | Ustawienia działu | Opis |
    |---|---|
    | <strong>Nazwa działu</strong> | Wyświetlane, gdy użytkownicy klikną pozycję <strong>Informacje o konfiguracji</strong> podczas aktywacji. |
    | <strong>Telefon działu</strong> | Jest wyświetlany, gdy użytkownik kliknie podczas aktywacji przycisk <strong>Potrzebna pomoc</strong>. |

  Można wybrać opcję pokazywania lub ukrywania różnych ekranów Asystenta ustawień na urządzeniu podczas jego konfigurowania.
  - Jeśli wybierzesz pozycję **Ukryj**, ekran nie będzie wyświetlany podczas konfigurowania. Po skonfigurowaniu urządzenia użytkownik może nadal przejść do menu **Ustawienia**, aby skonfigurować tę funkcję.
  - Jeśli wybierzesz pozycję **Pokaż**, ekran będzie wyświetlany podczas konfigurowania. Użytkownik może czasami pominąć ekran bez podejmowania akcji. Później jednak może przejść do menu **Ustawienia** urządzenia, aby skonfigurować tę funkcję. 


    | Ustawienia ekranu Asystent ustawień | Jeśli wybierzesz pozycję **Pokaż**, podczas konfigurowania urządzenie będzie... |
    |------------------------------------------|------------------------------------------|
    | <strong>Kod dostępu</strong> | Monitować o wprowadzenie hasła. Zawsze należy wymagać kodu dostępu, chyba że urządzenie zostanie zabezpieczone lub dostęp do niego będzie kontrolowany w inny sposób (tj. zostanie zastosowany tryb kiosku, który ogranicza możliwość użycia urządzenia do jednej aplikacji). |
    | <strong>Usługi lokalizacyjne</strong> | Monitować użytkownika o określenie lokalizacji. |
    | <strong>Przywróć</strong> | Wyświetlać ekran **Aplikacje i dane**. Ten ekran oferuje użytkownikowi opcję przywracania lub przenoszenia danych z kopii zapasowej w usłudze iCloud podczas konfigurowania urządzenia. |
    | <strong>Identyfikator Apple ID i usługa iCloud</strong> | Oferować użytkownikowi opcję logowania za pomocą **identyfikatora Apple ID** i używania usługi **iCloud**.                         |
    | <strong>Warunki i postanowienia</strong> | Wymagać od użytkownika akceptacji warunków i postanowień firmy Apple. |
    | <strong>Touch ID</strong> | Oferować użytkownikowi możliwość konfigurowania identyfikacji za pomocą odcisku palca w urządzeniu. |
    | <strong>Apple Pay</strong> | Oferować użytkownikowi opcję skonfigurowania usługi Apple Pay na urządzeniu. |
    | <strong>Powiększenie</strong> | Oferować użytkownikowi opcję powiększania ekranu podczas konfigurowania urządzenia. |
    | <strong>Siri</strong> | Oferować użytkownikowi opcję konfigurowania programu Siri. |
    | <strong>Dane diagnostyczne</strong> | Wyświetlać ekran **Diagnostyka** dla użytkownika. Na tym ekranie użytkownik może wybrać opcję wysyłania danych diagnostycznych do firmy Apple. |
    | <strong>FileVault</strong> | Oferować użytkownikowi opcję konfigurowania szyfrowania FileVault. |
    | <strong>Diagnostyka w usłudze iCloud</strong> | Oferować użytkownikowi opcję wysyłania danych diagnostycznych usługi iCloud do firmy Apple. |
    | <strong>Rejestracja</strong>| Wymagać od użytkownika zarejestrowania urządzenia. |
    
   

10. Wybierz przycisk **OK**.

11. Abu zapisać profil, wybierz pozycję **Utwórz**.

## <a name="sync-managed-devices"></a>Synchronizowanie urządzeń zarządzanych
Gdy usługa Intune ma uprawnienia do zarządzania urządzeniami, można ją zsynchronizować z danymi firmy Apple, aby wyświetlić zarządzane urządzenia w usłudze Intune w witrynie Azure Portal.

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > wybierz token z listy > **Urządzenia** > **Synchronizuj**. ![Zrzut ekranu przedstawiający wybrany węzeł Urządzenia programu Enrollment Program i wybierany link Synchronizuj.](./media/device-enrollment-program-enroll-ios/image06.png)

   Aby spełnić warunki firmy Apple dotyczące ruchu w programie rejestracji, usługa Intune nakłada następujące ograniczenia:
   - Pełną synchronizację można uruchamiać nie częściej niż co siedem dni. Podczas pełnej synchronizacji usługa Intune pobiera pełną zaktualizowaną listę numerów seryjnych przypisanych do serwera MDM firmy Apple połączonego z usługą Intune. Gdy urządzenie uczestniczące w programie rejestracji zostanie usunięte z portalu usługi Intune bez usuwania przypisania z serwera MDM firmy Apple w portalu programu DEP, zostanie ponownie zaimportowane do usługi Intune dopiero po uruchomieniu pełnej synchronizacji.   
   - Synchronizacja jest uruchamiana automatycznie co 24 godziny. Można też przeprowadzić synchronizację, klikając przycisk **Synchronizuj** (nie częściej niż raz na 15 minut). Każde żądanie synchronizacji ma przydzielone 15 minut na ukończenie. Przycisk **Synchronizuj** pozostaje wyłączony do ukończenia synchronizacji. Synchronizacja spowoduje odświeżenie stanu bieżącego urządzenia oraz zaimportowanie nowych urządzeń przypisanych do serwera MDM firmy Apple.   


## <a name="assign-an-enrollment-profile-to-devices"></a>Przypisywanie profilu rejestracji do urządzeń
Zanim możliwe będzie rejestrowanie urządzeń, należy przypisać profil programu rejestracji.

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > wybierz token z listy.
2. Wybierz **Urządzenia** > wybierz urządzenia na liście > **Przypisz profil**.
3. W obszarze **Przypisz profil** wybierz profil dla urządzeń > **Przypisz**.

### <a name="assign-a-default-profile"></a>Przypisywanie profilu domyślnego

Można wybrać profil domyślny w systemie macOS lub iOS, który zostanie zastosowany do wszystkich urządzeń rejestrowanych przy użyciu określonego tokenu. 

1. W usłudze Intune w witrynie Azure Portal wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja Apple** > **Tokeny programu rejestracji** > wybierz token z listy.
2. Kliknij pozycję **Ustaw profil domyślny**, wybierz profil z listy rozwijanej, a następnie kliknij pozycję **Zapisz**. Ten profil zostanie zastosowany do wszystkich urządzeń rejestrowanych przy użyciu tokenu.

## <a name="distribute-devices"></a>Dystrybuowanie urządzeń
Włączono zarządzanie i synchronizację między danymi firmy Apple i usługą Intune oraz przypisano profil umożliwiający rejestrowanie urządzeń. Możesz teraz przekazać urządzenia użytkownikom. W przypadku urządzeń z koligacją użytkownika wymagane jest, aby poszczególni użytkownicy mieli przypisane licencje na korzystanie z usługi Intune. Urządzenia bez koligacji użytkownika wymagają licencji urządzenia. Aktywowane urządzenie nie może stosować profilu rejestracji, dopóki nie zostaną wyczyszczone dane urządzenia.

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

## <a name="next-steps"></a>Następne kroki

Po zarejestrowaniu urządzeń z systemem macOS można rozpocząć [zarządzanie nimi](device-management.md).