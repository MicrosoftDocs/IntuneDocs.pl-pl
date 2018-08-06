---
title: Ustawienia kiosku dla systemu Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Możesz skonfigurować urządzenia z systemem Windows 10 (lub nowszym) jako kioski z pojedynczą aplikacją oraz z wieloma aplikacjami, dostosowując menu Start, dodając aplikacje i pasek zadań oraz konfigurując przeglądarkę internetową. Możesz również skonfigurować urządzenia platformy Windows Holographic for Business jako kioski z wieloma aplikacjami w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 7/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6f10e7bb7a2e7c5e1d0e8b27517a62454e8bd630
ms.sourcegitcommit: e8e8164586508f94704a09c2e27950fe6ff184c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321805"
---
# <a name="kiosk-settings-for-windows-10-and-later-in-intune"></a>Ustawienia kiosku dla systemu Windows 10 (i nowszych) w usłudze Intune

Profile kiosku służą do konfigurowania urządzeń z systemem Windows 10 tak, aby uruchamiały jedną lub wiele aplikacji. W przypadku tworzenia profilu kiosku należy również wybrać opcje wyświetlania lub niewyświetlania menu Start, instalowania przeglądarki internetowej i nie tylko.

## <a name="kiosk-settings"></a>Ustawienia kiosku

1. Wybierz pozycję **Dodaj**, aby utworzyć środowisko kiosku.
2. Wprowadź **nazwę konfiguracji kiosku** dla swojego kiosku. Ta nazwa identyfikuje grupę aplikacji, układ tych aplikacji w menu Start oraz użytkowników przypisanych do danej konfiguracji kiosku.
3. Wybierz pozycję **Tryb kiosku**. **Tryb kiosku** wskazuje typ trybu kiosku obsługiwany przez zasady. Dostępne opcje:

    - **Nieskonfigurowane** (domyślne): te zasady nie umożliwiają korzystania z trybu kiosku.
    - **Kiosk z pojedynczą aplikacją w trybie pełnoekranowym**: profil umożliwia uruchamianie urządzenia w ramach pojedynczego konta użytkownika i blokowanie go jako jednej aplikacji platformy uniwersalnej systemu Windows (platformy UWP). Gdy użytkownik zaloguje się, jest uruchamiana konkretna aplikacja. Ten tryb uniemożliwia także użytkownikowi otwieranie nowych aplikacji oraz zmianę uruchomionej aplikacji.
    - **Kiosk z wieloma aplikacjami**: profil umożliwia urządzeniu uruchamianie wielu aplikacji platformy uniwersalnej systemu Windows (platformy UWP) lub aplikacji Win32. Można także przypisywać różne aplikacje do różnych kont użytkowników. Tylko dodane aplikacje są dostępne dla użytkowników. Korzyści z kiosku z wieloma aplikacjami (czyli urządzenia o stałym przeznaczeniu) polegają na udostępnieniu użytkownikom łatwego do poznania środowiska, w którym są dostępne tylko potrzebne im aplikacje. Aplikacje, których użytkownicy nie potrzebują, są usuwane z widoku.

#### <a name="single-full-screen-app-kiosks"></a>Kioski z pojedynczą aplikacją w trybie pełnoekranowym
Podaj następujące ustawienia:

- **Identyfikator aplikacji platformy uniwersalnej systemu Windows (UWP)**: wprowadź **identyfikator modelu użytkownika aplikacji (AUMID)** aplikacji kiosku. Możesz również wybrać istniejącą aplikację zarządzaną, którą dodano za pomocą usługi [Mobile Apps](apps-add.md).

    Zobacz [Find the Application User Model ID of an installed app (Znajdowanie identyfikatora modelu użytkownika aplikacji zainstalowanej aplikacji)](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

- **Typ konta użytkownika**: opcje:

  - **Logowanie automatyczne**: w przypadku kiosków w miejscach publicznych z włączonym automatycznym logowaniem należy użyć użytkownika z najniższymi uprawnieniami (na przykład lokalnego standardowego konta użytkownika). Aby skonfigurować konto usługi Azure Active Directory (AD) pod kątem trybu kiosku, użyj formatu `AzureAD\user@contoso.com`.
  - **Konto użytkownika lokalnego**: wprowadź lokalne (na urządzeniu) konto użytkownika lub dane logowania konta usługi Azure AD skojarzonego z aplikacją kiosku. W przypadku kont przyłączonych do domeny usługi Azure AD podaj konto w formacie `domain\username@tenant.org`.

#### <a name="multi-app-kiosks"></a>Kioski z wieloma aplikacjami
Aplikacje w tym trybie są dostępne w menu Start. Te aplikacje to jedyne aplikacje, które użytkownik może otwierać. 

[Kioski z wieloma aplikacjami](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configure-a-kiosk-in-microsoft-intune) korzystają z konfiguracji kiosku zawierającej listę dozwolonych aplikacji i inne ustawienia.

Podaj następujące ustawienia:

- **Dodaj aplikację systemu Win32**: aplikacja systemu Win32 to tradycyjna aplikacja klasyczna. Wprowadź wartości pól **Nazwa aplikacji** i **Identyfikator**. **Identyfikator** to w pełni kwalifikowana nazwa ścieżki pliku wykonywalnego określona względem urządzenia.
- **Dodaj aplikacje zarządzane**: wybierz istniejącą aplikację zarządzaną, którą dodano za pomocą usługi [Mobile Apps w usłudze Intune](apps-add.md).
- **Dodaj aplikację według identyfikatora AUMID**: wprowadź [identyfikator AUMID aplikacji](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (aplikacje platformy UWP).
- **Pasek zadań**: wybierz wartość **Włącz**, aby wyświetlać pasek zadań, lub wartość **Nieskonfigurowany**, aby go ukryć na kiosku.
- **Układ menu Start**: określ plik XML, który opisuje sposób wyświetlania aplikacji w menu Start, w tym ich kolejność. Artykuł [Customize and export Start layout (Dostosowywanie i eksportowanie układu menu Start)](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) zawiera wskazówki i przykładowy kod XML.

  Artykuł [Create a Windows 10 kiosk that runs multiple apps (Tworzenie kiosku z systemem Windows 10 obsługującego wiele aplikacji)](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file) zawiera więcej szczegółowych informacji na temat używania i tworzenia plików XML.

- **Typ konta użytkownika**: dodaj co najmniej jedno konto użytkownika, które może używać dodanych aplikacji. Po zalogowaniu przy użyciu konta będą dostępne tylko aplikacje określone w konfiguracji. Może być to konto lokalne na urządzeniu lub dane logowania konta usługi Azure AD skojarzonego z aplikacją kiosku.

    W przypadku kiosków w miejscach publicznych z włączonym automatycznym logowaniem należy użyć typu użytkownika z najniższymi uprawnieniami (na przykład lokalnego standardowego konta użytkownika). Aby skonfigurować konto usługi Azure Active Directory (AD) pod kątem trybu kiosku, użyj formatu `domain\user@tenant.com`.

## <a name="kiosk-web-browser-settings"></a>Ustawienia przeglądarki internetowej kiosku

Te ustawienia umożliwiają kontrolowanie aplikacji przeglądarki internetowej działającej w obrębie kiosku. Upewnij się, że aplikacja przeglądarki internetowej została wdrożona na urządzeniach kiosku przy użyciu usługi [Mobile Apps](apps-add.md).

1. Podaj następujące ustawienia:

    - **Adres URL domyślnej strony głównej**: wprowadź domyślny adres URL otwierany po otwarciu lub ponownym uruchomieniu przeglądarki kiosku.

    - **Przycisk Strona główna**: pokazywanie (**Zezwalaj**) lub ukrywanie (**Nieskonfigurowany**) przycisku Strona główna przeglądarki kiosku. Domyślnie ten przycisk nie jest konfigurowany.

    - **Przycisk nawigacji**: pokazywanie (**Zezwalaj**) lub ukrywanie (**Nieskonfigurowany**) przycisków Dalej i Wstecz. Domyślnie przyciski nawigacji nie są konfigurowane.

    - **Przycisk Zakończ sesję**: pokazywanie (**Zezwalaj**), lub ukrywanie (**Nieskonfigurowany**) przycisku kończenia sesji. Jeśli przycisk jest wyświetlany, po wybraniu go przez użytkownika w aplikacji pojawia się monit o zakończenie sesji. Po potwierdzeniu przeglądarka czyści wszystkie dane przeglądania (pliki cookies, pamięć podręczną i tak dalej) i powraca do domyślnego adresu URL. Domyślnie ten przycisk nie jest konfigurowany. 

    - **Odśwież przeglądarkę, gdy użytkownik przekracza limit czasu bezczynności**: wprowadź czas bezczynności sesji (w minutach), po którym przeglądarka kiosku jest uruchamiana od nowa. Wartość to liczba całkowita z przedziału od 1 do 1440 minut. Domyślnie to pole pozostaje puste, co oznacza, że nie ma limitu czasu bezczynności.

    - **Zablokowane witryny internetowe**: lista adresów URL zablokowanych witryn internetowych (z obsługą symboli wieloznacznych). Użyj tego ustawienia, aby uniemożliwić otwieranie określonych witryn w przeglądarce. Możesz również **zaimportować** plik CSV zawierający listę. Inna opcja to utworzenie pliku CSV (**Eksportuj**) zawierającego dodawane witryny.

    - **Wyjątki witryn internetowych**: lista wyjątków adresów URL zablokowanych witryn internetowych (z obsługą symboli wieloznacznych). Użyj tego ustawienia, aby zezwolić przeglądarce na otwieranie określonych witryn. Te wyjątki są podzestawem zablokowanych adresów URL. Jeśli adres URL znajduje się na liście zablokowanych witryn internetowych i na liście wyjątków witryn internetowych, wyjątek zostanie uwzględniony.

    Możesz również **zaimportować** plik CSV zawierający listę. Inna opcja to utworzenie pliku CSV (**Eksportuj**) zawierającego dodawane witryny.

2. Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

Urządzenia platformy Windows Holographic for Business można skonfigurować tak, aby były uruchamiane w trybie kiosku z jedną aplikacją lub wieloma aplikacjami. 

#### <a name="single-full-screen-app-kiosks"></a>Kioski z pojedynczą aplikacją w trybie pełnoekranowym
Podaj następujące ustawienia:

- **Identyfikator aplikacji platformy uniwersalnej systemu Windows (UWP)**: wprowadź **identyfikator modelu użytkownika aplikacji (AUMID)** aplikacji kiosku. Możesz również wybrać istniejącą aplikację zarządzaną, którą dodano za pomocą usługi [Mobile Apps](apps-add.md).

    Zobacz [Znajdowanie identyfikatora modelu użytkownika aplikacji zainstalowanej aplikacji](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

- **Typ konta użytkownika**: wybierz **Konto użytkownika lokalnego**, aby wprowadzić konto użytkownika lokalnego (na urządzenie) lub konto Microsoft skojarzone z aplikacją kiosku. Konta użytkowników typu **Logowanie automatyczne** nie są obsługiwane na platformie Windows Holographic for Business.

#### <a name="multi-app-kiosks"></a>Kioski z wieloma aplikacjami
Aplikacje w tym trybie są dostępne w menu Start. Te aplikacje to jedyne aplikacje, które użytkownik może otwierać.

Podaj następujące ustawienia:

- **Dodaj aplikacje zarządzane**: wybierz istniejącą aplikację zarządzaną, którą dodano za pomocą usługi [Mobile Apps w usłudze Intune](apps-add.md).
- **Dodaj aplikację według identyfikatora AUMID**: wprowadź [identyfikator AUMID aplikacji](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (aplikacje platformy UWP).
- **Układ menu Start**: określ plik XML, który opisuje sposób wyświetlania aplikacji w menu Start, w tym ich kolejność. Artykuł [Customize and export Start layout (Dostosowywanie i eksportowanie układu menu Start)](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-for-hololens) zawiera wskazówki i oraz plik XML przygotowany dla urządzeń platformy Windows Holographic for Business.
- **Typ konta użytkownika**: dodaj co najmniej jedno konto użytkownika, które może używać dodanych aplikacji. Obsługiwane opcje obejmują: 
  - **Gość HaloLens**: konto gościa, które nie wymaga żadnych poświadczeń użytkownika ani uwierzytelniania, zgodnie z opisem w sekcji [Shared PC mode concepts (Pojęcia związane z trybem komputera udostępnionego)](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).
  - **Użytkownicy usługi Azure AD**: wymaga poświadczeń użytkownika w celu zalogowania się na urządzeniu. Użyj formatu `domain\user@tenant.com`.
  - **Konta użytkownika lokalnego**: wymaga poświadczeń użytkownika w celu zalogowania się na urządzeniu. 

Po zalogowaniu przy użyciu konta będą dostępne tylko aplikacje określone w konfiguracji.

## <a name="next-steps"></a>Następne kroki
[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).
