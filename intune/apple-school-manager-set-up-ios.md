---
title: "Konfigurowanie rejestrowania urządzeń z systemem iOS w programie Apple School Manager"
titleSuffix: Intune on Azure
description: "Informacje o sposobie konfigurowania rejestracji firmowych urządzeń z systemem iOS w programie Apple School Manager przy użyciu usługi Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 73556209c88759ffe0747d9927cbcbb49600e0c0
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="enable-ios-device-enrollment-with-apple-school-manager"></a>Włączanie rejestracji urządzeń z systemem iOS za pomocą usługi Apple School Manager

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ten temat ułatwia administratorom IT włączenie rejestracji urządzeń z systemem iOS zakupionych w ramach programu [Apple School Manager](https://school.apple.com/) (ASM). Usługa Microsoft Intune umożliwia wdrożenie „na odległość” profilu rejestracji, który pozwala zarejestrować urządzenia ASM w usłudze zarządzania. Administrator nie musi zbliżać się do żadnego z zarządzanych urządzeń. Profil ASM zawiera ustawienia zarządzania, w tym opcje Asystenta ustawień, które zostają zastosowane do urządzeń podczas rejestracji.

**Kroki rejestracji w programie ASM**
1. [Pobieranie tokenu ASM i przypisywanie urządzeń](#get-the-asm-token-and-assign-devices)
2. [Tworzenie profilu rejestracji](#create-an-apple-enrollment-profile)
3. [Łączenie się z usługą School Data Sync](#connect-school-data-sync) (opcjonalnie)
4. [Synchronizowanie urządzeń zarządzanych w ramach programu ASM](#sync-asm-managed-devices)
5. [Przypisywanie profilu ASM do urządzeń](#assign-an-asm-profile-to-devices)
6. [Przekazywanie urządzeń użytkownikom](#distribute-devices-to-users)

>[!NOTE]
>W przypadku użycia programu [Device Enrollment Program (DEP)](device-enrollment-program-enroll-ios.md) firmy Apple lub konta [menedżera rejestracji urządzeń](device-enrollment-manager-enroll.md) usługi Intune rejestracja w programie ASM nie jest możliwa.

## <a name="get-the-apple-asm-token-and-assign-devices"></a>Pobieranie tokenu ASM firmy Apple i przypisywanie urządzeń

Przed zarejestrowaniem firmowych urządzeń z systemem iOS z użyciem programu Apple School Manager (ASM) należy uzyskać od firmy Apple plik tokenu (.p7m). Token ten umożliwia usłudze Intune synchronizację informacji dotyczących urządzeń uczestniczących w programie ASM. Umożliwia on również usłudze Intune przekazywanie profilów rejestracji do firmy Apple i przypisywanie urządzeń do tych profilów. W portalu firmy Apple można także przypisywać numery seryjne urządzeń do zarządzania.

**Wymagania wstępne**
- [Certyfikat wypychania MDM firmy Apple](apple-mdm-push-certificate-get.md)
- Rejestracja w programie [Apple School Management](http://school.apple.com)

**Krok 1. Pobierz certyfikat klucza publicznego usługi Intune wymagany do utworzenia tokenu ASM firmy Apple.**<br>
1. W [portalu usługi Intune](https://aka.ms/intuneportal) na platformie Azure wybierz kolejno pozycje **Rejestracja urządzenia** i **Token programu Enrollment Program**.
2. W bloku **Token programu Enrollment Program** wybierz pozycję **Pobierz klucz publiczny**, aby pobrać i zapisać lokalnie plik klucza szyfrowania (.pem). Plik .pem jest używany na potrzeby żądania certyfikatu relacji zaufania z portalu Apple School Manager.

**Krok 2. Pobierz token ASM i przypisz urządzenia.**<br>
Wybierz pozycję **Utwórz token za pomocą usługi Apple School Manager** i zaloguj się przy użyciu identyfikatora Apple ID swojej firmy. Tego identyfikatora Apple ID można także użyć do odnowienia tokenu ASM.

   1.  W [portalu Apple School Manager](https://school.apple.com) wybierz pozycję **MDM Servers** (Serwery MDM), a następnie wybierz **Add MDM Server** (Dodaj serwer MDM) (w prawym górnym rogu).
   2.  Wypełnij pole **MDM Server Name** (Nazwa serwera MDM). Nazwa serwera służy użytkownikowi do identyfikowania serwera MDM. Nie jest to nazwa ani adres URL serwera usługi Microsoft Intune.
   3.  Wybierz pozycję **Upload File...** (Przekaż plik...) w portalu firmy Apple, przejdź do pliku .pem, a następnie wybierz pozycję **Save MDM Server** (Zapisz serwer MDM) (w lewym dolnym rogu).
   4.  Wybierz opcję **Get Token** (Pobierz token), a następnie pobierz na komputer plik tokenu serwera (.p7m).
   5. Przejdź do pozycji **Device Assignments** (Przypisania urządzeń) i **Choose Device** (Wybierz urządzenie). W tym celu wypełnij ręcznie pole **Serial Numbers** (Numery seryjne), **Order Number** (Numer zamówienia) lub **Upload CSV File** (Przekaż plik CSV).
   6.   Wybierz akcję **Assign to Server** (Przypisz do serwera) i wybierz utworzony serwer MDM (**MDM Server**).
   7. Określ sposób **wybierania urządzeń**, a następnie podaj informacje o urządzeniach i określ szczegóły według numeru seryjnego (**Serial Number**) urządzenia, numeru zamówienia (**Order Number**) lub przekaż plik CSV (**Upload CSV File**).
   8. Wybierz pozycję **Assign to Server** (Przypisz do serwera), wybierz nazwę serwera &lt;nazwa_serwera&gt; określoną dla usługi Microsoft Intune, a następnie kliknij przycisk **OK**.

**Krok 3. Wprowadź identyfikator Apple ID użyty do utworzenia tokenu ASM.**<br>Tego identyfikatora należy użyć do odnowienia tokenu Apple ASM. Należy zachować token do użytku w przyszłości.

**Krok 4. Zlokalizuj i przekaż token.**<br>
Przejdź do pliku certyfikatu (.p7m) i wybierz pozycję **Otwórz**, a następnie wybierz pozycję **Przekaż**. Usługa Intune przeprowadzi automatyczną synchronizację urządzeń firmy Apple należących do programu ASM.

## <a name="create-an-apple-enrollment-profile"></a>Tworzenie profilu rejestracji firmy Apple
Profil rejestracji urządzeń określa ustawienia stosowane do grupy urządzeń podczas rejestracji.

1. W portalu usługi Intune wybierz pozycję **Rejestracja urządzenia**, a następnie pozycję **Rejestracja Apple**.
2. W obszarze **Enrollment Program**, wybierz pozycję **Profile programu Enrollment Program**.
3. W bloku **Profile programu Enrollment Program** wybierz pozycję **Utwórz**.
4. W bloku **Utwórz profil rejestracji** wypełnij pola **Nazwa** i **Opis** odnoszące się do profilu wyświetlanego w portalu usługi Intune.
5. Dla pozycji **Koligacja użytkownika** wskaż, czy urządzenia z tym profilem będą rejestrowane z koligacją użytkownika, czy bez niej.

 - **Zarejestruj z koligacją użytkownika** — podczas początkowej konfiguracji należy określić przynależność urządzenia do użytkownika, a następnie zezwolić na dostęp tego urządzenia do firmowych danych i poczty e-mail. Wybierz opcję koligacji użytkownika dla urządzeń zarządzanych z użyciem usługi ASM, do których użytkownicy logują się za pomocą swoich zarządzanych identyfikator Apple ID.

 >[!NOTE]
 >Uwierzytelnianie wieloskładnikowe (MFA) nie działa podczas rejestracji urządzeń za pomocą programu ASM, gdy jest używana koligacja użytkownika. Po zarejestrowaniu tych urządzeń uwierzytelnianie wieloskładnikowe działa zgodnie z oczekiwaniami.

  Tryb udostępniania urządzenia iPad w usłudze Apple School Manager wymaga od użytkownika zarejestrowania urządzenia z koligacją użytkownika.

 >[!NOTE]
    >Program ASM z koligacją użytkownika wymaga włączenia [nazwy użytkownika protokołu WS-Trust 1.3/mieszanego punktu końcowego](https://technet.microsoft.com/library/adfs2-help-endpoints), aby możliwe było żądanie tokenu użytkownika. [Dowiedz się więcej na temat protokołu WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Zarejestruj bez koligacji użytkownika** — przynależność urządzenia do użytkownika nie jest określana. Tego typu przynależności należy użyć w przypadku urządzeń wykonujących zadania bez uzyskiwania dostępu do danych użytkowników lokalnych. Aplikacje wymagające koligacji użytkownika (w tym aplikacja Portal firmy używana do instalowania aplikacji biznesowych) nie będą działać.

6. Wybierz pozycję **Ustawienia zarządzania urządzeniami**. Te pozycje są konfigurowane podczas aktywacji i do ich zmiany wymagane jest zresetowanie do ustawień fabrycznych. Skonfiguruj następujące ustawienia profilu, a następnie wybierz pozycję **Zapisz**:

    - **Nadzorowane** — tryb zarządzania, w ramach którego następuje włączenie większej liczby opcji zarządzania i domyślne wyłączenie blokady aktywacji. Jeśli pole pozostanie puste, użytkownik będzie mieć ograniczone możliwości w zakresie zarządzania.

    - **Rejestracja zablokowana** — (wymaga zastosowania ustawienia Tryb zarządzania = Nadzorowane) wyłącza ustawienia systemu iOS, które umożliwiają usunięcie profilu zarządzania. W przypadku pozostawienia tego pola pustego istnieje możliwość usunięcia profilu zarządzania z poziomu menu Ustawienia.

  - **Udostępnione urządzenie iPad** — (wymaga ustawienia **Zarejestruj z koligacją użytkownika** i trybu **Nadzorowane**). Umożliwia wielu użytkownikom logowanie się do zarejestrowanych urządzeń iPad przy użyciu zarządzanego identyfikatora Apple ID. Zarządzane identyfikatory Apple ID tworzy się w portalu Apple School Manager.

  >[!NOTE]
  >Jeśli w profilu zostanie włączony tryb **Udostępnione urządzenie iPad**, a następnie dla trybu **Koligacja użytkownika** lub **Nadzorowane** zostanie wybrana opcja **Wyłączone**, tryb Udostępnione urządzenie iPad zostanie wyłączony dla profilu rejestracji.

  - **Maksymalna liczba zbuforowanych użytkowników** — (wymaga wyboru ustawienia **Udostępnione urządzenie iPad** = **Tak**) tworzy na urządzeniu partycję dla każdego użytkownika. Zalecaną wartością jest liczba uczniów mogących korzystać z urządzenia w wyznaczonym okresie. Np. jeśli w ciągu tygodnia z urządzenia regularnie korzysta sześciu uczniów, należy wybrać wartość 6.  

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
(Opcjonalnie) Usługa ASM obsługuje synchronizowanie danych listy uczniów z usługą Azure Active Directory (AD) przy użyciu aplikacji Microsoft School Data Sync (SDS). Wykonaj poniższe kroki, aby użyć aplikacji SDS w celu zsynchronizowania danych szkolnych.

1. W bloku **Token programu Enrollment Program** wybierz niebieski baner z informacjami lub opcję **Połącz z programem SDS**.
2. Wybierz pozycję **Zezwalaj aplikacji Microsoft School Data Sync na używanie tego tokenu** i ustaw wartość **Zezwalaj**. To ustawienie umożliwia usłudze Intune łączenie się z programem SDS w usłudze Office 365.
3. Aby włączyć połączenie między usługą ASM i usługą Azure AD, wybierz opcję **Skonfiguruj aplikację Microsoft School Data Sync**. Dowiedz się więcej o [sposobie konfigurowania aplikacji School Data Sync](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1).
4. Kliknij przycisk **OK**, aby zapisać zmiany i kontynuować.

## <a name="sync-asm-managed-devices"></a>Synchronizowanie urządzeń zarządzanych w ramach programu ASM
Teraz, gdy do usługi Intune zostało przypisane uprawnienie do zarządzania urządzeniami ASM, można zsynchronizować usługę Intune z usługą ASM, aby wyświetlić zarządzane urządzenia w portalu usługi Intune.

1. W portalu usługi Intune wybierz pozycję **Rejestracja urządzenia**, a następnie pozycję **Rejestracja Apple**.
2. W obszarze **Urządzenia programu Enrollment Program** wybierz pozycję **Synchronizacja**. Pasek postępu pokazuje, ile czasu minie przed ponownym przesłaniem żądania synchronizacji.

    Aby spełnić warunki ruchu usługi ASM firmy Apple, usługa Intune nakłada następujące ograniczenia:
     -  Pełną synchronizację usługi ASM można uruchamiać nie częściej niż co siedem dni. Podczas pełnej synchronizacji usługa Intune odświeża każdy numer seryjny Apple przypisany do usługi Intune, niezależnie od tego, czy numer seryjny był już wcześniej synchronizowany. W przypadku próby przeprowadzenia pełnej synchronizacji przed upływem siedmiu dni od poprzedniej pełnej synchronizacji usługa Intune odświeża tylko numery seryjne, które jeszcze nie zostały przypisane do usługi Intune.
     -  Każde żądanie synchronizacji ma przydzielone 15 minut na zakończenie. W tym czasie lub do momentu zakończenia żądania powodzeniem przycisk **synchronizacji** jest wyłączony.

>[!NOTE]
>Można także przypisać numery seryjne urządzeń ASM do profilów z bloku **Urządzenia programu Enrollment Program**.

## <a name="assign-an-asm-profile-to-devices"></a>Przypisywanie profilu usługi ASM do urządzeń
Przed zarejestrowaniem urządzeń ASM zarządzanych przez usługę Intune należy przypisać do nich profil usługi ASM.

1. W portalu usługi Intune wybierz kolejno pozycje **Rejestracja urządzenia** > **Rejestracja Apple**, a następnie wybierz pozycję **Profile programu Enrollment Program**.
2. Z listy **Profile programu Enrollment Program** wybierz profil, który ma zostać przypisany do urządzeń, a następnie wybierz pozycję **Przypisania urządzeń**
3. Wybierz pozycję **Przypisz**, a następnie wybierz urządzenia ASM, do których chcesz przypisać ten profil. Możesz zastosować filtr, aby wyświetlać dostępne urządzenia ASM:
  - **nieprzypisane**
  - **dowolne**
  - **&lt;nazwa profilu usługi ASM&gt;**
4. Wybierz urządzenia, które chcesz przypisać. Pole wyboru powyżej kolumny pozwala wybrać maksymalnie 1000 wyświetlanych urządzeń. Kliknij przycisk **Przypisz**. Aby zarejestrować więcej niż 1000 urządzeń, powtarzaj czynności przypisania, aż profil usługi ASM zostanie przypisany do wszystkich urządzeń.

## <a name="distribute-devices-to-users"></a>Przekazywanie urządzeń użytkownikom

Urządzenia firmowe mogą zostać teraz przekazane użytkownikom. Po włączeniu urządzenia ASM z systemem iOS zostanie ono zarejestrowane na potrzeby zarządzania przez usługę Intune. Jeśli urządzenie zostało aktywowane i jest używane, profilu nie można zastosować, dopóki urządzenie nie zostanie zresetowane do ustawień fabrycznych.

### <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Jak użytkownicy instalują aplikację Portal firmy i używają jej na urządzeniach

Na urządzeniach skonfigurowanych z koligacją użytkownika można zainstalować aplikację Portal firmy i używać jej do pobierania aplikacji i zarządzania urządzeniami. Po otrzymaniu urządzeń użytkownicy muszą uruchomić Asystenta ustawień i zainstalować aplikację Portal firmy.
