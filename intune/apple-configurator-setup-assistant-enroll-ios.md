---
title: "Rejestracja urządzeń z systemem iOS przy użyciu programu Apple Configurator i Asystenta ustawień"
titleSuffix: Intune on Azure
description: "Informacje dotyczące rejestrowania firmowych urządzeń z systemem iOS przy użyciu programu Apple Configurator i Asystenta ustawień."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1d74fbcebfe89bbafc545d11dd6316cb602db8ee
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2017
---
# <a name="enroll-ios-devices-with-apple-configurator"></a>Rejestrowanie urządzeń z systemem iOS przy użyciu programu Apple Configurator

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Usługa Intune obsługuje rejestrowanie firmowych urządzeń z systemem iOS przy użyciu narzędzia [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) działającego na komputerze Mac. Rejestrowanie przy użyciu narzędzia Apple Configurator wymaga, aby poszczególne urządzenia z systemem iOS zostały podłączone do komputera Mac za pośrednictwem portu USB w celu skonfigurowania rejestracji firmowej. Urządzenia można zarejestrować w usłudze Intune przy użyciu narzędzia Apple Configurator na dwa sposoby:
- **Rejestracja z użyciem Asystenta ustawień** — przywraca ustawienia fabryczne urządzenia i przygotowuje je do uruchomienia Asystenta ustawień, a także instaluje zasady firmy dla nowego użytkownika urządzenia. Większość scenariuszy wymaga, aby zasady zastosowane w urządzeniu z systemem iOS uwzględniały koligację użytkownika, co umożliwia korzystanie z aplikacji Portal firmy usługi Intune.
- **Rejestracja bezpośrednia** — nie powoduje przywrócenia ustawień fabrycznych urządzenia i powoduje zarejestrowanie urządzenia przy użyciu wstępnie zdefiniowanych zasad. Ta metoda służy do rejestrowania urządzeń **bez koligacji użytkownika**.

>[!NOTE]
>Tej metody rejestracji nie można używać z metodą korzystającą z [menedżera rejestracji urządzeń](device-enrollment-manager-enroll.md).

Inne metody rejestracji urządzeń z systemem iOS zostały opisane w temacie [Choose how to enroll iOS devices in Intune](enrollment-method-choose-ios.md) (Wybieranie sposobu rejestrowania urządzeń z systemem iOS w usłudze Intune).

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem konfigurowania rejestracji urządzeń z systemem iOS należy spełnić następujące wymagania wstępne:

- [Certyfikat wypychania MDM firmy Apple](apple-mdm-push-certificate-get.md)
- Fizyczny dostęp do urządzeń z systemem iOS
- Numery seryjne urządzeń (zobacz artykuł [Znajdowanie numeru seryjnego produktu firmy Apple](https://support.apple.com//HT204308))
- Kable połączenia USB
- Komputer Mac z programem [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)
- [Dodawanie numerów seryjnych programu Apple Configurator](apple-configurator-serial-numbers-add.md)

## <a name="setup-assistant-enrollment"></a>Rejestracja Asystenta ustawień

### <a name="create-an-apple-configurator-profile-for-devices"></a>Tworzenie profilu programu Apple Configurator dla urządzeń

Profil rejestracji urządzeń określa ustawienia stosowane do grupy urządzeń. Poniższe kroki pokazują, jak utworzyć profil rejestracji dla urządzeń z systemem iOS rejestrowanych przy użyciu programu Apple Configurator.

1. W portalu usługi Intune wybierz pozycję **Rejestracja urządzenia**, a następnie pozycję **Rejestracja Apple**.
2. W obszarze **Zarządzaj ustawieniami rejestracji programu Apple Configurator** wybierz pozycję **Profile programu AC**.
3. W bloku **Profile rejestracji programu Apple Configurator** wybierz pozycję **Utwórz**.
4. W bloku **Utwórz profil rejestracji** wprowadź nazwę i opis profilu.
5. Dla pozycji **Koligacja użytkownika** wskaż, czy urządzenia z tym profilem będą rejestrowane z koligacją użytkownika, czy bez niej.

   - **Zarejestruj z koligacją użytkownika** — podczas początkowej konfiguracji należy określić przynależność urządzenia do użytkownika, a następnie zezwolić na dostęp tego urządzenia do firmowych danych i poczty e-mail. Koligację użytkownika należy skonfigurować dla urządzeń zarządzanych, które należą do użytkowników i muszą korzystać z portalu firmy na potrzeby usług, takich jak instalowanie aplikacji.
   - **Zarejestruj bez koligacji użytkownika** — przynależność urządzenia do użytkownika nie jest określana. Tego typu przynależności należy użyć w przypadku urządzeń wykonujących zadania bez uzyskiwania dostępu do danych użytkowników lokalnych. Aplikacje wymagające koligacji użytkownika (w tym aplikacja Portal firmy używana do instalowania aplikacji biznesowych) nie będą działać.

6. Wybierz pozycję **Utwórz**, aby zapisać profil.

### <a name="add-apple-configurator-serial-numbers"></a>Dodawanie numerów seryjnych programu Apple Configurator

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

W krokach tych opisano dodawanie numerów seryjnych do usługi Intune w przypadku [rejestracji urządzeń firmowych z systemem iOS przy użyciu programu Apple Configurator i Asystenta ustawień](apple-configurator-setup-assistant-enroll-ios.md). Można dodawać numery seryjne pojedynczo lub załadować plik wartości rozdzielonych przecinkami (CSV) z numerami seryjnymi. Po dodaniu numerów seryjnych można do nich przypisać profil. Profil zawiera określone ustawienia zarządzania, które mają być zastosowane do urządzeń.

Inne metody rejestracji urządzeń z systemem iOS zostały opisane w temacie [Choose how to enroll iOS devices in Intune](enrollment-method-choose-ios.md) (Wybieranie sposobu rejestrowania urządzeń z systemem iOS w usłudze Intune).

**Aby dodać numery seryjne programu Apple Configurator do usługi Intune**

1. Utwórz listę wartości rozdzielonych przecinkami (.csv) zawierającą dwie kolumny, bez nagłówka. Dodaj identyfikator IMEI w lewej kolumnie i szczegółowe informacje w prawej kolumnie. Obecnie maksymalna liczba wierszy na liście wynosi 500. W edytorze tekstu lista .csv wygląda następująco:

    F7TLWCLBX196, szczegóły urządzenia</br>
    DLXQPCWVGHMJ,szczegóły urządzenia

2. W portalu Azure Portal wybierz pozycję **Zarejestruj urządzenia**, a następnie pozycję **Rejestracja Apple**.
3. W obszarze **Zarządzanie ustawieniami rejestracji programu Apple Configurator** wybierz pozycję **Numery seryjne programu Apple Configurator**.
4. W bloku **Numery seryjne programu Apple Configurator** wybierz przycisk **Dodaj**.
5. W bloku **Dodaj numery seryjne** wybierz profil do zastosowania do importowanych numerów seryjnych. Jeśli importujesz plik z nowymi szczegółami, które zastąpią istniejące, wybierz opcję Zastąp szczegóły istniejących identyfikatorów, aby nowe szczegóły zastąpiły istniejące.
6. Przejdź do pliku .csv numerów seryjnych i wybierz przycisk **Dodaj**.

### <a name="assign-a-profile-to-specific-serial-numbers"></a>Przypisywanie profilu do określonych numerów seryjnych

Usługa Intune umożliwia przypisywanie profilów z dwóch różnych miejsc w portalu Azure. Przypisywanie odbywa się według profilu programu Apple Configurator lub według urządzeń.

#### <a name="assign-by-devices"></a>Przypisywanie według urządzeń
1. W portalu usługi Intune wybierz pozycję **Rejestracja urządzenia**, a następnie pozycję **Rejestracja Apple**.
3. W bloku **Urządzenia programu Apple Configurator** wybierz numery seryjne, do których chcesz przypisać profil, a następnie wybierz pozycję **Przypisz profil**.
4. W bloku **Przypisz profil** wybierz profil, który chcesz przypisać, a następnie wybierz przycisk **Przypisz**.

#### <a name="assign-by-profiles"></a>Przypisywanie według profilów
1. W portalu usługi Intune wybierz pozycję **Rejestracja urządzenia**, a następnie pozycję **Rejestracja Apple**.
2. Wybierz **Profile programu AC**, a następnie wybierz profil, do którego chcesz przypisać numery seryjne.
3. W bloku o nazwie profilu wybierz kolejno pozycje **Numery seryjne** > **Przypisz**.
4. Wybierz numery seryjne, które chcesz przypisać do tego profilu, a następnie kliknij przycisk **Przypisz**.

### <a name="export-the-profile-to-ios-devices"></a>Eksportowanie profilu do urządzeń z systemem iOS
Po utworzeniu profilu i przypisaniu numerów seryjnych należy wyeksportować profil z usługi Intune jako adres URL lub jako plik w formacie opisanym poniżej. Następnie należy zaimportować go ręcznie do programu Apple Configurator zainstalowanego na komputerze Mac; po wykonaniu tej czynności program Apple Configurator wdroży go na urządzeniach.

1. W portalu usługi Intune wybierz blok **Profile rejestracji programu Apple Configurator**, a następnie wybierz profil przeznaczony do wyeksportowania.
2. W bloku odpowiedniego profilu zaznacz pozycję **Eksportuj profil**.
3. Skopiuj adres URL profilu do programu [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) po podłączeniu urządzenia z systemem iOS. Możesz przekazać go później przy użyciu narzędzia Apple Configurator, aby określić profil usługi Intune używany przez urządzenia z systemem iOS.

  Możesz przekazać ten adres URL profilu do usługi firmy Apple za pomocą narzędzia Apple Configurator, aby zdefiniować profil usługi Intune używany przez urządzenia z systemem iOS, używając poniższej procedury.
4. Przekaż ten adres URL profilu do usługi firmy Apple za pomocą narzędzia Apple Configurator, aby zdefiniować profil usługi Intune używany przez urządzenia z systemem iOS.
 1.  Na komputerze Mac otwórz narzędzie **Apple Configurator 2**. Na pasku menu wybierz pozycję **Apple Configurator 2**, a następnie wybierz pozycję **Preferences** (Preferencje).
  > [!WARNING]
  > Podczas procesu rejestracji urządzenia zostaną zresetowane do konfiguracji fabrycznych. Jako najlepsze rozwiązanie zalecane jest zresetowanie urządzenia i włączenie go. Zalecane jest również, aby podczas podłączania na urządzeniach był wyświetlany ekran **powitalny**.
  2. W okienku **preferencji** wybierz pozycję **Servers** (Serwery), a następnie wybierz symbol plusa (+), aby uruchomić kreatora serwera MDM. Wybierz pozycję **Next** (Dalej).
  3. Wprowadź **nazwę lub adres URL hosta** i **adres URL rejestracji** dla serwera MDM w obszarze rejestracji asystenta ustawień dla urządzeń z systemem iOS w usłudze Microsoft Intune. W polu adresu URL rejestracji wprowadź adres URL profilu rejestracji wyeksportowany z usługi Intune. Wybierz pozycję **Next** (Dalej).  

    Możesz bezpiecznie zignorować ostrzeżenie informujące, że adres URL serwera nie został zweryfikowany. Aby kontynuować, wybieraj pozycję **Next** (Dalej), aż do ukończenia pracy kreatora.
  4.  Podłącz urządzenia przenośne z systemem iOS do komputera Mac przy użyciu adaptera USB.
  > [!WARNING]
  > Podczas procesu rejestracji urządzenia zostaną zresetowane do konfiguracji fabrycznych. Jako najlepsze rozwiązanie zalecane jest zresetowanie urządzenia i włączenie go. Podczas uruchamiania Asystenta ustawień na urządzeniach powinien być wyświetlany ekran **powitalny**.
  5.  Wybierz pozycję **Prepare**(Przygotuj). W okienku **Prepare iOS Device** (Przygotowywanie urządzenia z systemem iOS) wybierz pozycję **Manual** (Ręcznie), a następnie wybierz pozycję **Next** (Dalej).
  6. W okienku **Enroll in MDM Server** (Rejestrowanie na serwerze MDM) wybierz utworzoną nazwę serwera, a następnie wybierz pozycję **Next** (Dalej).
  7. W okienku **Supervise Devices** (Nadzorowanie urządzeń) wybierz poziom nadzoru, a następnie wybierz pozycję **Next** (Dalej).
  8. W okienku **Create an Organization** (Tworzenie organizacji) wybierz pozycję **Organization** (Organizacja) lub utwórz nową organizację, a następnie wybierz pozycję **Next** (Dalej).
  9. W okienku **Configure iOS Setup Assistant** (Konfigurowanie Asystenta ustawień systemu iOS) wybierz czynności, które mają zostać wyświetlone użytkownikowi, a następnie wybierz pozycję **Prepare** (Przygotuj). Jeśli zostanie wyświetlony monit, uwierzytelnij się w celu zaktualizowania ustawień zaufania.  
  10. Po zakończeniu przygotowywania urządzenia z systemem iOS odłącz kabel USB.  
6.  **Rozdystrybuuj urządzenia**.
    Urządzenia są teraz gotowe do rejestracji w firmie. Wyłącz urządzenia i przekaż je użytkownikom. Po włączeniu urządzeń przez użytkowników zostanie uruchomiony Asystent ustawień.

## <a name="direct-enrollment"></a>Rejestracja bezpośrednia
W przypadku bezpośredniego rejestrowania urządzeń z systemem iOS przy użyciu programu Apple Configurator możesz zarejestrować urządzenie bez uzyskiwania jego numeru seryjnego. Możesz też nazwać urządzenie w celach identyfikacyjnych, zanim usługa Intune przechwyci nazwę urządzenia podczas rejestracji. Aplikacja Portal firmy nie jest obsługiwana w przypadku urządzeń, które zostały zarejestrowane bezpośrednio. W tych wskazówkach przyjęto założenie, że używany jest program Apple Configurator 2.0 na komputerze Mac.

1. W portalu usługi Intune wybierz kolejno pozycje **Rejestracja urządzenia** i **Rejestracja Apple**, a następnie **Profile programu AC**.
2. W bloku **Profile rejestracji programu Apple Configurator** wybierz pozycję **Utwórz**.
3. W bloku **Utwórz profil rejestracji** wprowadź nazwę i opis profilu.
4. Dla pozycji **Koligacja użytkownika** wybierz opcję **Zarejestruj bez koligacji użytkownika**, aby mieć pewność, że urządzenie nie jest powiązane z użytkownikiem. Tego typu przynależności należy użyć w przypadku urządzeń wykonujących zadania bez uzyskiwania dostępu do danych użytkowników lokalnych. Aplikacje wymagające koligacji użytkownika (w tym aplikacja Portal firmy używana do instalowania aplikacji biznesowych) nie będą działać.
5. Wybierz pozycję **Utwórz**, aby zapisać profil.

### <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>Eksportowanie profilu jako pliku .mobileconfig do urządzeń z systemem iOS

1. W bloku **Eksportuj profil** pobierz profil rejestracji do programu [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) w celu bezpośredniego wypchnięcia go jako profilu zarządzania do połączonego urządzenia z systemem iOS. Użycie tej metody nie powoduje zresetowania urządzenia do ustawień fabrycznych.
2. Przygotuj urządzenie z zainstalowanym programem Apple Configurator, wykonując kroki opisane poniżej.
  1. Na komputerze Mac otwórz program Apple Configurator 2.0.
  2. Podłącz urządzenia z systemem iOS do komputera Mac przy użyciu kabla USB. Zamknij aplikacje Photos (Zdjęcia), iTunes i inne aplikacje otwarte na urządzeniu po jego wykryciu.
  3. W programie Apple Configurator wybierz podłączone urządzenie z systemem iOS, a następnie wybierz przycisk **Add** (Dodaj). Opcje, które można dodać do urządzenia, są wyświetlane na liście rozwijanej. Wybierz pozycję **Profiles** (Profile).
  4. Użyj selektora plików w celu wybrania pliku mobileconfig wyeksportowanego za pomocą usługi Intune, a następnie wybierz pozycję **Add** (Dodaj). Profil zostanie dodany do urządzenia. Jeśli urządzenie jest nienadzorowane, instalacja będzie wymagać akceptacji na urządzeniu.
3. Wykonaj poniższe kroki w celu zainstalowania profilu na urządzeniu z systemem iOS. Na urządzeniu musi zostać zakończona praca Asystenta ustawień i musi być one gotowe do użycia. Jeśli rejestracja wiąże się z wdrożeniami aplikacji, urządzenie powinno mieć ustawiony identyfikator firmy Apple, ponieważ wdrożenia aplikacji będą wymagać posiadania identyfikatora Apple ID powiązanego ze sklepem App Store.
   1. Odblokuj urządzenie z systemem iOS.
   2. W oknie dialogowym **Zainstaluj profil** wybierz dla pozycji **Profil zarządzania** opcję **Zainstaluj**.
   3. W razie potrzeby podaj kod dostępu urządzenia lub identyfikator Apple ID.
   4. Zaakceptuj **ostrzeżenie** i wybierz pozycję **Zainstaluj**.
   5. Zaakceptuj **ostrzeżenie zdalne** i wybierz pozycję **Ufaj**.
   6. Wyświetlenie okna dialogowego **Profil został zainstalowany** oznacza, że profil został zainstalowany. Wybierz pozycję **Gotowe**.

    4. Na urządzeniu z systemem iOS otwórz pozycję **Ustawienia** i przejdź do pozycji **Ogólne** > **Zarządzanie urządzeniem** > **Profil zarządzania**. Upewnij się, że instalacja profilu jest wymieniona na liście, a następnie sprawdź ograniczenia zasad systemu iOS i zainstalowane aplikacje. Wyświetlenie ograniczeń zasad i aplikacji na urządzeniu może potrwać do 10 minut.

    5. Rozdystrybuuj urządzenia. Urządzenie z systemem iOS jest teraz zarejestrowane w usłudze Intune i zarządzane przez tę usługę.


## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Jak użytkownicy instalują aplikację Portal firmy i używają jej na urządzeniach

Na urządzeniach skonfigurowanych z koligacją użytkownika można zainstalować aplikację Portal firmy i używać jej do pobierania aplikacji i zarządzania urządzeniami. Po otrzymaniu urządzeń użytkownicy muszą wykonać dodatkowe czynności, które zostały opisane poniżej, w celu ukończenia działania Asystenta ustawień i zainstalowania aplikacji Portal firmy.
