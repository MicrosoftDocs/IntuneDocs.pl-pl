---
title: "Rejestrowanie urządzeń z systemem iOS — program Device Enrollment Program"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje na temat rejestrowania firmowych urządzeń z systemem iOS przy użyciu programu Device Enrollment Program."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 53f1c688aad2f810d8a887435dd8d122d4f471ae
ms.openlocfilehash: d8fa3a19915076f1a603449dd426172fbc5a613a
ms.lasthandoff: 04/27/2017


---

# <a name="enroll-ios-devices-using-device-enrollment-program"></a>Rejestrowanie urządzeń z systemem iOS przy użyciu programu Device Enrollment Program

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Ten temat ułatwia administratorom IT rejestrowanie firmowych urządzeń z systemem iOS zakupionych za pośrednictwem [programu Device Enrollment Program (DEP) firmy Apple](https://deploy.apple.com). Usługa Microsoft Intune umożliwia wdrożenie profilu rejestracji, który rejestruje program DEP bezprzewodowo, dzięki czemu administrator nie musi mieć fizycznego dostępu do każdego zarządzanego urządzenia. Profil DEP zawiera ustawienia zarządzania, które chcesz zastosować do urządzeń podczas rejestrowania. Pakiet rejestracyjny może obejmować opcje Asystenta ustawień dla urządzenia.

>[!NOTE]
>Rejestracji DEP nie można używać razem z [menedżerem rejestracji urządzeń](enroll-devices-using-device-enrollment-manager.md).
>Ponadto jeśli użytkownicy zarejestrują swoje urządzenia z systemem iOS za pomocą aplikacji Portal firmy, a następnie numery seryjne tych urządzeń zostaną zaimportowane i przypisane do profilu DEP, urządzenia te zostaną wyrejestrowane z usługi Intune.

**Kroki rejestracji DEP**
1. [Pobieranie tokenu DEP firmy Apple](#get-the-apple-dep-certificate)
2. [Tworzenie profilu DEP](#create-anapple-dep-profile)
3. [Przypisywanie numerów seryjnych programu DEP firmy Apple do serwera usługi Intune](#assign-apple-dep-serial-numbers-to-your-mdm-server)
4. [Synchronizowanie urządzeń zarządzanych w programie DEP](#synchronize-dep-managed-devices)
5. [Przypisywanie profilu usługi DEP do urządzeń](#assign-a-dep-profile-to-devices)
6. [Przekazywanie urządzeń użytkownikom](#distribute-devices-to-users)

## <a name="get-the-apple-dep-certificate"></a>Pobieranie certyfikatu programu DEP firmy Apple
Aby zarejestrować firmowe urządzenia z systemem iOS w programie Device Enrollment Program (DEP) firmy Apple, musisz uzyskać plik certyfikatu (p7m) programu DEP od firmy Apple. Token umożliwia usłudze Intune synchronizację informacji dotyczących urządzeń uczestniczących w programie DEP należących do firmy. Umożliwia on również usłudze Intune przekazywanie profilów rejestracji do firmy Apple i przypisywanie urządzeń do tych profilów.

W celu zarządzania firmowymi urządzeniami z systemem iOS przy użyciu programu DEP organizacja musi dołączyć do programu DEP firmy Apple i zakupić urządzenia w ramach tego programu. Szczegóły tego procesu są dostępne pod adresem https://deploy.apple.com. Zalety programu obejmują funkcje bezobsługowego konfigurowania urządzeń bez konieczności podłączania poszczególnych urządzeń do komputera przy użyciu kabla USB.

> [!NOTE]
> Jeśli dzierżawca usługi Intune został przeniesiony z konsoli klasycznej usługi Intune do witryny Azure Portal, a token programu DEP firmy Apple podczas migracji został usunięty z konsoli administracyjnej usługi Intune, ten token programu DEP mógł zostać przywrócony na koncie usługi Intune. Możesz ponownie usunąć token programu DEP z poziomu witryny Azure Portal.

**Krok 1. Pobierz certyfikat klucza publicznego usługi Intune wymagany do utworzenia tokenu DEP firmy Apple.**<br>
1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**. W bloku Intune wybierz pozycję **Rejestrowanie urządzeń** > **Token programu DEP firmy Apple**.
2. Wybierz pozycję **Pobierz klucz publiczny**, aby pobrać i zapisać lokalnie plik klucza szyfrowania (.pem). Plik PEM jest używany na potrzeby żądania certyfikatu relacji zaufania z portalu programu Device Enrollment Program firmy Apple.

**Krok 2. Pobierz token DEP firmy Apple z odpowiedniej witryny internetowej firmy Apple.**<br>
Wybierz pozycję [Utwórz token DEP za pomocą programów wdrażania firmy Apple](https://deploy.apple.com) (https://deploy.apple.com) i zaloguj się przy użyciu identyfikatora Apple swojej firmy. Tego identyfikatora firmy Apple możesz użyć do odnowienia tokenu DEP.

   1.  W [portalu Device Enrollment Program](https://deploy.apple.com) firmy Apple wybierz pozycję **Device Enrollment Program** &gt; **Zarządzanie serwerami**, a następnie wybierz pozycję **Dodaj serwer MDM**.
   2.  Wprowadź nazwę serwera w polu **MDM Server Name** (Nazwa serwera MDM), a następnie wybierz przycisk **Next**(Dalej). Nazwa serwera służy użytkownikowi do identyfikowania serwera MDM. Nie jest to nazwa ani adres URL serwera usługi Microsoft Intune.
   3.  Zostanie otwarte okno dialogowe **Add &lt;nazwa_serwera&gt;** (Dodawanie serwera <nazwa_serwera>). Kliknij pozycję **Choose File…** (Wybierz plik...) w celu przekazania pliku PEM, a następnie kliknij przycisk **Next** (Dalej).
   4.  W oknie dialogowym **Add&lt; <nazwa_serwera>&gt;** (Dodawanie serwera <nazwa_serwera>) zostanie wyświetlony link **Your Server Token** (Token serwera). Pobierz plik tokenu serwera (p7m) na komputer, a następnie wybierz pozycję **Done**(Gotowe).

**Krok 3. Wprowadź identyfikator firmy Apple użyty do utworzenia tokenu DEP firmy Apple. Tego identyfikatora można użyć do odnowienia tokenu DEP firmy Apple.**

**Krok 4. Przejdź do lokalizacji tokenu DEP firmy Apple do przekazania. Usługa Intune przeprowadzi automatyczną synchronizację z kontem DEP.**<br>
Przejdź do pliku certyfikatu (.pem) i wybierz pozycję **Otwórz**, a następnie wybierz pozycję **Przekaż**. Dzięki certyfikatowi wypychania usługa Intune może rejestrować urządzenia z systemem iOS i zarządzać nimi, wypychając zasady do zarejestrowanych urządzeń przenośnych.

## <a name="create-an-apple-dep-profile"></a>Tworzenie profilu programu DEP firmy Apple

Profil rejestracji urządzeń określa ustawienia stosowane do grupy urządzeń. Poniższe kroki pokazują, jak utworzyć profil rejestracji dla urządzeń z systemem iOS rejestrowanych przy użyciu programu DEP.

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
2. W bloku Intune wybierz pozycję **Rejestracja urządzenia**, a następnie wybierz pozycję **Rejestracja Apple**.
3. W obszarze **Zarządzaj ustawieniami rejestracji programu DEP (Device Enrollment Program) firmy Apple** wybierz pozycję **Profile usługi DEP**.
4. W bloku **Profile usługi DEP firmy Apple** wybierz pozycję **Utwórz**.
5. W bloku **Utwórz profil rejestracji** wprowadź nazwę i opis profilu.
6. Dla pozycji **Koligacja użytkownika** wskaż, czy urządzenia z tym profilem będą rejestrowane z koligacją użytkownika, czy bez niej.

 - **Zarejestruj z koligacją użytkownika** — podczas początkowej konfiguracji należy określić przynależność urządzenia do użytkownika, a następnie zezwolić na dostęp tego urządzenia do firmowych danych i poczty e-mail. Określ koligację użytkownika dla urządzeń zarządzanych w programie DEP, które należą do użytkowników i muszą korzystać z portalu firmy na potrzeby usług takich jak instalowanie aplikacji. Uwaga: uwierzytelnianie wieloskładnikowe (MFA) nie działa podczas rejestracji urządzeń za pomocą programu DEP, gdy jest używana koligacja użytkownika. Po zarejestrowaniu tych urządzeń uwierzytelnianie wieloskładnikowe działa zgodnie z oczekiwaniami. W przypadku nowych użytkowników, dla których wymagana jest zmiana hasła podczas pierwszego logowania, nie można wyświetlić monitu podczas rejestracji na urządzeniach objętych programem DEP. Ponadto w przypadku użytkowników, których hasła wygasły, nie zostanie wyświetlony monit o zresetowanie hasła podczas rejestracji w programie DEP i muszą oni zresetować hasło za pomocą innego urządzenia.

    >[!NOTE]
    >Program DEP z koligacją użytkownika wymaga nazwy użytkownika protokołu [WS-Trust 1.3/mieszanego punktu końcowego](https://technet.microsoft.com/en-us/library/adfs2-help-endpoints), aby móc żądać tokenu użytkownika. [Dowiedz się więcej na temat protokołu WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Zarejestruj bez koligacji użytkownika** — przynależność urządzenia do użytkownika nie jest określana. Tego typu przynależności należy użyć w przypadku urządzeń wykonujących zadania bez uzyskiwania dostępu do danych użytkowników lokalnych. Aplikacje wymagające koligacji użytkownika (w tym aplikacja Portal firmy używana do instalowania aplikacji biznesowych) nie będą działać.

7. Wybierz pozycję **Ustawienia zarządzania urządzeniami**, skonfiguruj następujące ustawienia profilu, a następnie wybierz pozycję **Zapisz**:

    - **Nadzorowane** — tryb zarządzania, w ramach którego następuje włączenie większej liczby opcji zarządzania i domyślne wyłączenie blokady aktywacji. Jeśli pole pozostanie puste, użytkownik będzie mieć ograniczone możliwości w zakresie zarządzania.

    - **Rejestracja zablokowana** — (wymaga zastosowania ustawienia Tryb zarządzania = Nadzorowane) wyłącza ustawienia systemu iOS, które umożliwiają usunięcie profilu zarządzania. W przypadku pozostawienia tego pola pustego istnieje możliwość usunięcia profilu zarządzania z poziomu menu Ustawienia. To ustawienie zostaje skonfigurowane podczas aktywacji i nie ma możliwości jego zmiany bez zresetowania urządzenia do ustawień fabrycznych.

    - **Zezwalaj na parowanie** — określa, czy urządzenia z systemem iOS można synchronizować z komputerami. W przypadku wybrania pozycji **Zezwalaj programowi Apple Configurator według certyfikatów** należy wybrać certyfikat w obszarze **Certyfikaty programu Apple Configurator**.

    - **Certyfikaty programu Apple Configurator** — w przypadku wyboru pozycji **Zezwalaj programowi Apple Configurator według certyfikatów** w obszarze **Zezwalaj na parowanie** należy wybrać certyfikat programu Apple Configurator do zaimportowania.

8. Wybierz pozycję **Ustawienia Asystenta ustawień**, skonfiguruj następujące ustawienia profilu, a następnie wybierz pozycję **Zapisz**:

    - **Nazwa działu** — jest wyświetlana, gdy użytkownik dotknie pozycji **Informacje o konfiguracji** podczas aktywacji.

    - **Telefon działu** — jest wyświetlany, gdy użytkownik kliknie podczas aktywacji przycisk Potrzebna pomoc.
    - **Opcje Asystenta ustawień** — te opcjonalne ustawienia mogą być później konfigurowane z poziomu menu **Ustawienia** systemu iOS.
        - **Kod dostępu** — wyświetla monit o podanie kodu dostępu podczas aktywacji. Zawsze należy wymagać kodu dostępu, chyba że urządzenie zostanie zabezpieczone lub dostęp do niego będzie kontrolowany w inny sposób (tj. tryb kiosku, który ogranicza możliwość użycia urządzenia do jednej aplikacji).
        - **Usługi lokalizacji** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący usługi podczas aktywacji
        - **Przywracanie** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit o kopię zapasową w programie iCloud podczas aktywacji
        - **Apple ID** — jeśli to ustawienie zostało włączone, system iOS wyświetla monit o podanie identyfikatora Apple ID, gdy usługa Intune będzie podejmowała próbę zainstalowania aplikacji bez tego identyfikatora. Identyfikator Apple ID jest wymagany do pobierania aplikacji ze sklepu iOS App Store, w tym aplikacji zainstalowanych przez usługę Intune.
        - **Warunki i postanowienia** — jeśli to ustawienie zostało włączone, Asystent ustawień monituje użytkowników o zaakceptowanie warunków i postanowień firmy Apple podczas aktywacji
        - **Touch ID** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji
        - **Apple Pay** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji
        - **Zoom** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji
        - **Siri** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji
        - **Dane diagnostyczne** — jeśli to ustawienie zostało włączone, Asystent ustawień wyświetla monit dotyczący tej usługi podczas aktywacji

9. Aby zapisać ustawienia profilu, wybierz pozycję **Utwórz** w bloku **Utwórz profil rejestracji**.

## <a name="assign-apple-dep-serial-numbers-to-your-mdm-server"></a>Przypisywanie numerów seryjnych programu DEP firmy Apple do serwera MDM
Numery seryjne urządzeń należy przypisać do serwera MDM usługi Intune w portalu internetowym programu DEP firmy Apple, aby umożliwić usłudze Intune zarządzanie tymi urządzeniami.

1. Przejdź do [portalu Device Enrollment Program](https://deploy.apple.com) (https://deploy.apple.com) i zaloguj się przy użyciu identyfikatora Apple ID swojej firmy.

2. Wybierz kolejno pozycje **Deployment Program** (Program wdrażania) &gt; **Device Enrollment Program** (Program rejestracji urządzeń) &gt; **Manage Devices** (Zarządzanie urządzeniami).

3. Określ sposób **wybierania urządzeń**, a następnie podaj informacje o urządzeniach i określ szczegóły według numeru seryjnego (**Serial Number**) urządzenia, numeru zamówienia (**Order Number**) lub przekaż plik CSV (**Upload CSV File**).

4. Wybierz pozycję **Assign to Server** (Przypisz do serwera), wybierz nazwę serwera &lt;nazwa_serwera&gt; określoną dla usługi Microsoft Intune, a następnie kliknij przycisk **OK**.

## <a name="synchronize-dep-managed-devices"></a>Synchronizowanie urządzeń zarządzanych w programie DEP
Teraz, gdy do usługi Intune zostało przypisane uprawnienie do zarządzania urządzeniami DEP, można zsynchronizować usługę Intune z usługą DEP, aby wyświetlić zarządzane urządzenia w portalu usługi Intune.

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku Intune witryny Azure Portal wybierz pozycję **Rejestracja urządzenia**, a następnie wybierz pozycję **Rejestracja Apple**.

3. W obszarze **Zarządzaj ustawieniami rejestracji programu DEP (Device Enrollment Program) firmy Apple** wybierz pozycję **Numery seryjne DEP**.

4. W bloku **Numery seryjne Apple DEP** wybierz przycisk **Synchronizuj**.

5. W bloku **Synchronizuj** wybierz pozycję **Żądaj synchronizacji**. Pasek postępu pokazuje, ile czasu minie przed ponownym przesłaniem żądania synchronizacji.

    Aby spełnić warunki ruchu programu DEP firmy Apple, usługa Intune nakłada następujące ograniczenia:
     -    Pełną synchronizację programu DEP można uruchamiać nie częściej niż co siedem dni. Podczas pełnej synchronizacji usługa Intune odświeża każdy numer seryjny Apple przypisany do usługi Intune, niezależnie od tego, czy numer seryjny był już wcześniej synchronizowany. W przypadku próby przeprowadzenia pełnej synchronizacji przed upływem siedmiu dni od poprzedniej pełnej synchronizacji usługa Intune odświeża tylko numery seryjne, które jeszcze nie zostały przypisane do usługi Intune.
     -    Każde żądanie synchronizacji ma przydzielone 10 minut na zakończenie. W tym czasie lub do momentu zakończenia żądania powodzeniem przycisk **synchronizacji** jest wyłączony.

>[!NOTE]
>Możesz także przypisać numery seryjne DEP do profilów z bloku **Numery seryjne Apple DEP**.

## <a name="assign-a-dep-profile-to-devices"></a>Przypisywanie profilu usługi DEP do urządzeń
Przed zarejestrowaniem urządzeń DEP zarządzanych przez usługę Intune należy przypisać do nich profil usługi DEP.

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku Intune witryny Azure Portal wybierz kolejno pozycje **Rejestracja urządzenia** > **Rejestracja Apple**, a następnie wybierz pozycję **Profile usługi DEP**.

3. Z listy **Profile rejestracji w usłudze DEP firmy Apple** wybierz profil, który ma zostać przypisany do urządzeń, a następnie wybierz pozycję **Przypisania urządzeń**

4. Wybierz pozycję **Przypisz**, a następnie wybierz urządzenia DEP, do których chcesz przypisać ten profil. Można filtrować, aby wyświetlać dostępne urządzenia DEP:
  - **nieprzypisane**
  - **dowolne**
  - **&lt;nazwa profilu usługi DEP&gt;**

  ![Zrzut ekranu przedstawiający przycisk Przypisz służący do przypisywania profilu usługi DEP w portalu usługi Intune](media/dep-profile-assignment.png)

5. Wybierz urządzenia, które chcesz przypisać. Pole wyboru nad kolumną pozwala na wybranie z listy maksymalnie 1000 urządzeń. Po wybraniu urządzeń kliknij przycisk **Przypisz**. Aby zarejestrować więcej niż 1000 urządzeń, powtarzaj czynności przypisania, aż profil usługi DEP zostanie przypisany do wszystkich urządzeń.

## <a name="distribute-devices-to-users"></a>Przekazywanie urządzeń użytkownikom

Urządzenia firmowe mogą zostać teraz przekazane użytkownikom. Po włączeniu urządzenia DEP z systemem iOS zostanie ono zarejestrowane na potrzeby zarządzania przez usługę Intune. Jeśli urządzenie zostało aktywowane i jest używane, profilu nie można zastosować, dopóki urządzenie nie zostanie zresetowane do ustawień fabrycznych.

### <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Jak użytkownicy instalują aplikację Portal firmy i używają jej na urządzeniach

Na urządzeniach skonfigurowanych z koligacją użytkownika można zainstalować aplikację Portal firmy i używać jej do pobierania aplikacji i zarządzania urządzeniami. Po otrzymaniu urządzeń użytkownicy muszą wykonać dodatkowe czynności, które zostały opisane poniżej, w celu ukończenia działania Asystenta ustawień i zainstalowania aplikacji Portal firmy.

### <a name="how-users-enroll-corporate-owned-ios-devices-with-user-affinity"></a>Jak użytkownicy rejestrują urządzenia firmowe z systemem iOS z koligacją użytkownika

1. Po włączeniu urządzenia użytkownicy są monitowani o ukończenie działania Asystenta ustawień. Podczas instalacji użytkownicy są monitowani o podanie swoich poświadczeń. Muszą oni korzystać z poświadczeń (tj. unikatowej kombinacji imienia i nazwiska lub nazwy UPN) skojarzonych z ich subskrypcją w usłudze Intune.

2. Podczas instalacji użytkownicy są monitowani o podanie identyfikatora Apple ID. Muszą podać identyfikator Apple ID, aby umożliwić zainstalowanie aplikacji Portal firmy na urządzeniu. Mogą także podać identyfikator Apple ID w menu ustawień systemu iOS po zakończeniu konfiguracji.

3. Po ukończeniu konfiguracji użytkownicy muszą zainstalować aplikację Portal firmy ze sklepu App Store.

4. Użytkownicy mogą się teraz zalogować do Portalu firmy przy użyciu nazwy UPN użytej podczas konfigurowania urządzenia.

5. Po zalogowaniu użytkownicy otrzymują monit o zarejestrowanie urządzenia. Pierwszym krokiem jest zidentyfikowanie urządzenia. Aplikacja wyświetla listę urządzeń z systemem iOS, które zostały już zarejestrowane przez firmę i przypisane do konta użytkownika w usłudze Intune. Użytkownicy powinni wybrać odpowiednie urządzenie. Jeśli to urządzenie nie zostało jeszcze zarejestrowane przez firmę, użytkownicy powinni wybrać pozycję „Nowe urządzenie”, aby kontynuować standardową procedurę rejestracji.

6. Na następnym ekranie użytkownicy potwierdzają numer seryjny nowego urządzenia. W tym celu użytkownicy wybierają wyświetlone łącze. Kliknięcie łącza uruchamia aplikację Ustawienia, która z kolei pozwala użytkownikom zweryfikować ich numer seryjny. Użytkownik musi następnie wprowadzić cztery ostatnie znaki numeru seryjnego do aplikacji Portal firmy.

   Ten krok umożliwia zweryfikowanie, że urządzenie zostało zarejestrowane przez firmę w usłudze Intune. Jeśli numer seryjny urządzenia nie jest zgodny, oznacza to, że użytkownik wybrał niewłaściwe urządzenie. Użytkownik musi powrócić do poprzedniego ekranu i wybrać inne urządzenie.

7. Po zweryfikowaniu numeru seryjnego aplikacja Portal firmy wykonuje przekierowanie do witryny internetowej Portalu firmy w celu sfinalizowania rejestracji. Następnie w witrynie pojawia się monit o powrót użytkownika do aplikacji.

Stanowi to zakończenie procesu rejestracji. Użytkownicy mogą od tego momentu używać tego urządzenia z pełnym zestawem funkcji.

