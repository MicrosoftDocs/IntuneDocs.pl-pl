---
title: Ustawienia kiosku dla systemu Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Skonfiguruj urządzenia z systemem Windows 10 (lub nowszym) jako kioski z pojedynczą aplikacją oraz z wieloma aplikacjami, dostosuj menu Start, dodaj aplikacje i pasek zadań oraz skonfiguruj przeglądarkę internetową. Możesz również skonfigurować urządzenia platformy Windows Holographic for Business jako kioski z wieloma aplikacjami w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.openlocfilehash: 353c18affa41e56501a76bf695f95cbe95796e99
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203471"
---
# <a name="windows-10-and-later-device-settings-to-run-as-a-dedicated-kiosk-using-intune"></a>Ustawienia urządzenia z systemem Windows 10 (lub nowszym), które ma działać jako dedykowany kiosk przy użyciu usługi Intune

Na urządzeniach z systemem Windows 10 możesz użyć usługi Intune, aby uruchamiać urządzenia jako kiosk — czasami jest to nazywane urządzeniem dedykowanym. Urządzenie w trybie kiosku może uruchamiać jedną aplikację lub wiele aplikacji. Możesz wyświetlić i dostosować menu Start, dodać różne aplikacje, w tym aplikacje Win32, dodać określoną stronę główną do przeglądarki internetowej i wykonywać inne czynności. 

W tym artykule wymieniono i opisano różne ustawienia, którymi można sterować na urządzeniach z systemem Windows 10 i nowszym. W ramach rozwiązania do zarządzania urządzeniami przenośnymi (MDM) użyj tych ustawień, aby skonfigurować urządzenia z systemem Windows 10 do uruchamiania w trybie kiosku.

Usługa Intune obsługuje jeden profil kiosku na urządzenie. Jeśli potrzebujesz wielu profilów kiosku w jednym urządzeniu, możesz użyć [niestandardowego identyfikatora OMA-URI](custom-settings-windows-10.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia](device-profile-create.md).

## <a name="kiosk-settings"></a>Ustawienia kiosku

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi** > wpisz nazwę usługi **Intune** w filtrze > wybierz pozycję **Microsoft Intune**.
2. Wybierz kolejno pozycje **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Wprowadź następujące właściwości:

   - **Nazwa**: Wprowadź opisową nazwę nowego profilu.
   - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
   - **Platforma**: Wybierz pozycję **Windows 10 i nowsze**
   - **Typ profilu**: Wybierz pozycję **Kiosk**

4. Wybierz **tryb kiosku**. **Tryb kiosku** wskazuje typ trybu kiosku obsługiwany przez zasady. Dostępne opcje:

    - **Nieskonfigurowane** (wartość domyślna): Te zasady nie umożliwiają korzystania z trybu kiosku.
    - **Kiosk z pojedynczą aplikacją w trybie pełnoekranowym**: Urządzenie działa jako jedno konto użytkownika i blokuje je do pojedynczej aplikacji ze Sklepu. Gdy użytkownik zaloguje się, jest uruchamiana konkretna aplikacja. Ten tryb uniemożliwia także użytkownikowi otwieranie nowych aplikacji oraz zmianę uruchomionej aplikacji.
    - **Kiosk z wieloma aplikacjami**: W urządzeniu działa wiele aplikacji ze Sklepu, aplikacji Win32 lub aplikacji skrzynki odbiorczej systemu Windows dzięki użyciu identyfikatora modelu użytkownika aplikacji (AUMID). Tylko dodane aplikacje są dostępne w urządzeniu.

        Korzyści z kiosku z wieloma aplikacjami (czyli urządzenia o stałym przeznaczeniu) polegają na udostępnieniu użytkownikom łatwego do poznania środowiska, w którym są dostępne tylko potrzebne im aplikacje. Aplikacje, których użytkownicy nie potrzebują, są usuwane z widoku.

## <a name="single-full-screen-app-kiosks"></a>Kioski z pojedynczą aplikacją w trybie pełnoekranowym
W przypadku wybrania trybu kiosku z pojedynczą aplikacją wprowadź następujące ustawienia:

- **Typ logowania użytkownika**: Dodane aplikacje działają jako wprowadzone konto użytkownika. Dostępne opcje:

  - **Logowanie automatyczne (system Windows 10 w wersji 1803 i nowszych)**: W przypadku kiosków w środowiskach publicznych, które nie wymagają logowania od użytkowników, podobnie jak dla konta gościa. To ustawienie używa [dostawcy usług kryptograficznych AssignedAccess](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Konto użytkownika lokalnego**: Wprowadź konto użytkownika lokalnego (w urządzeniu). Wprowadzone konto jest używane do logowania się do kiosku.

- **Typ aplikacji**: Wybierz pozycję **Aplikacja ze Sklepu**.

- **Aplikacja do uruchamiania w trybie kiosku**: Wybierz pozycję **Dodaj aplikację ze sklepu**, a następnie wybierz aplikację z listy.

    Lista nie zawiera żadnych aplikacji? Dodaj aplikacje, wykonując czynności opisane w temacie [Aplikacje klienckie](apps-add.md).

    Wybierz przycisk **OK**, aby zapisać zmiany.

- **Ustawienia przeglądarki kiosku**: Te ustawienia umożliwiają kontrolowanie aplikacji przeglądarki internetowej działającej w obrębie kiosku. Upewnij się, że [aplikacja przeglądarki kiosku](https://businessstore.microsoft.com/store/details/kiosk-browser/9NGB5S5XG2KP) została pobrana ze Sklepu, dodana do usługi Intune jako [aplikacja kliencka](apps-add.md), a następnie przypisana do urządzeń kiosku.

  Podaj następujące ustawienia:

  - **Adres URL domyślnej strony głównej** : Wprowadź domyślny adres URL pokazywany po otwarciu przeglądarki kiosku lub ponownym uruchomieniu przeglądarki. Na przykład wprowadź adres `http://bing.com` lub `http://www.contoso.com`.

  - **Przycisk Strona główna**: **Pokaż** lub **Ukryj** przycisk Strona główna przeglądarki kiosku. Domyślnie ten przycisk nie jest wyświetlany.

  - **Przyciski nawigacyjne**: **Pokaż** lub **Ukryj** przyciski przechodzenia dalej i wstecz. Domyślnie przyciski nawigacyjne nie są wyświetlane.

  - **Przycisk zakończenia sesji**: **Pokaż** lub **Ukryj** przycisk zakończenia sesji. Jeśli przycisk jest wyświetlany, po wybraniu go przez użytkownika w aplikacji pojawia się monit o zakończenie sesji. Po potwierdzeniu przeglądarka czyści wszystkie dane przeglądania (pliki cookies, pamięć podręczną itd.), a następnie otwiera domyślny adres URL. Domyślnie ten przycisk nie jest wyświetlany.

  - **Odśwież przeglądarkę po czasie bezczynności**: Wprowadź czas bezczynności (1–1440 minut), po którym przeglądarka kiosku jest uruchamiana od nowa. Czas bezczynności to liczba minut od ostatniej interakcji użytkownika. Domyślnie ta wartość pozostaje pusta, co oznacza, że nie ma limitu czasu bezczynności.

  - **Dozwolone witryny internetowe**: To ustawienie umożliwia zezwolenie na otwieranie określonych witryn internetowych. Mówiąc inaczej, ta funkcja umożliwia ograniczenie lub uniemożliwienie użycia witryn internetowych w urządzeniu. Można na przykład zezwolić na otwieranie wszystkich witryn internetowych w lokalizacji `http://contoso.com*`. Domyślnie wszystkie witryny internetowe są dozwolone.
 
      Aby zezwolić na określone witryny internetowe, przekaż plik zawierający listę dozwolonych witryn internetowych w oddzielnych wierszach. Jeśli nie dodasz pliku, wszystkie witryny internetowe będą dozwolone. Usługa Intune obsługuje znak * (gwiazdka) jako symbol wieloznaczny.

      Przykładowy plik powinien być podobny do poniższej listy:

      `http://bing.com`  
      `https://bing.com`  
      `http://contoso.com/*`  
      `https://contoso.com/*`  

  Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="multi-app-kiosks"></a>Kioski z wieloma aplikacjami

Aplikacje w tym trybie są dostępne w menu Start. Te aplikacje to jedyne aplikacje, które użytkownik może otwierać.

W przypadku wybrania trybu kiosku z wieloma aplikacjami wprowadź następujące ustawienia:

- **Określ urządzenia w trybie S z systemem Windows 10 jako docelowe**: Wybierz pozycję **Tak**, aby zezwolić na aplikacje ze sklepu i aplikacje AUMID (z wyłączeniem aplikacji systemu Win32) w profilu kiosku. Wybierz pozycję **Nie**, aby zezwolić na aplikacje ze sklepu, aplikacje systemu Win32 i aplikacje AUMID w profilu kiosku. Po wybraniu pozycji **Nie** ten profil kiosku nie będzie wdrażany na urządzeniach w trybie S.

- **Typ logowania użytkownika**: Dodane aplikacje działają jako wprowadzone konto użytkownika. Dostępne opcje:

  - **Logowanie automatyczne (system Windows 10 w wersji 1803 i nowszych)**: W przypadku kiosków w środowiskach publicznych, które nie wymagają logowania od użytkowników, podobnie jak dla konta gościa. To ustawienie używa [dostawcy usług kryptograficznych AssignedAccess](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Konto użytkownika lokalnego**: **Dodaj** konto użytkownika lokalnego (w urządzeniu). Wprowadzone konto jest używane do logowania się do kiosku.
  - **Użytkownik lub grupa usługi Azure AD (system Windows 10 w wersji 1803 lub nowszej)**: Wybierz pozycję **Dodaj**, aby wybrać użytkowników lub grupy usługi Azure AD z listy. Można wybrać wielu użytkowników lub wiele grup. Wybierz przycisk **Wybierz**, aby zapisać zmiany.
  - **Odwiedzający platformę HoloLens**: Konto gościa, które nie wymaga żadnych poświadczeń użytkownika ani uwierzytelniania, zgodnie z opisem w sekcji [Pojęcia związane z trybem komputera udostępnionego](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Aplikacje**: Dodaj aplikacje do uruchamiania w urządzeniu kiosku. Pamiętaj, że możesz dodać kilka aplikacji.

  - **Dodaj aplikację ze sklepu**: Dodaj aplikację ze sklepu Microsoft Store dla Firm. Jeśli lista nie zawiera żadnych aplikacji, możesz pobrać aplikacje i [dodać je do usługi Intune](store-apps-windows.md). Można na przykład dodać przeglądarkę kiosku, program Excel, program OneNote i inne.

  - **Dodaj aplikację systemu Win32**: Aplikacja systemu Win32 to tradycyjna aplikacja klasyczna, taka jak program Visual Studio Code lub Google Chrome. Wprowadź następujące właściwości:

    - **Nazwa aplikacji**: Element wymagany. Wprowadź nazwę aplikacji.
    - **Ścieżka lokalna**: Element wymagany. Wprowadź ścieżkę do pliku wykonywalnego, taką jak `C:\Program Files (x86)\Microsoft VS Code\Code.exe` lub `C:\Program Files (x86)\Google\Chrome\Application\chrome.exe`.
    - **Identyfikator modelu użytkownika aplikacji (AUMID)**: Wprowadź identyfikator modelu użytkownika aplikacji (AUMID) dla aplikacji systemu Win32. To ustawienie określa początkowy układ kafelka na pulpicie. Aby uzyskać ten identyfikator, zobacz [Znajdowanie identyfikatora modelu użytkownika aplikacji zainstalowanej aplikacji](https://docs.microsoft.com/powershell/module/startlayout/get-startapps?view=win10-ps).
    - **Rozmiar kafelka**: Element wymagany. Wybierz mały, średni, szeroki lub duży rozmiar kafelka aplikacji.
  
  - **Dodaj przy użyciu identyfikatora AUMID**: Użyj tej opcji, aby dodać aplikacje skrzynki odbiorczej systemu Windows, na przykład Notatnik lub Kalkulator. Wprowadź następujące właściwości: 

    - **Nazwa aplikacji**: Element wymagany. Wprowadź nazwę aplikacji.
    - **Identyfikator modelu użytkownika aplikacji (AUMID)**: Element wymagany. Wprowadź identyfikator modelu użytkownika aplikacji (AUMID) dla aplikacji systemu Windows. Aby uzyskać ten identyfikator, zobacz [Znajdowanie identyfikatora modelu użytkownika aplikacji zainstalowanej aplikacji](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).
    - **Rozmiar kafelka**: Element wymagany. Wybierz mały, średni, szeroki lub duży rozmiar kafelka aplikacji.

  > [!TIP]
  > Po dodaniu wszystkich aplikacji można zmienić kolejność ich wyświetlania, klikając i przeciągając aplikacje na liście.  

  Wybierz przycisk **OK**, aby zapisać zmiany.

- **Ustawienia przeglądarki kiosku**: Te ustawienia umożliwiają kontrolowanie aplikacji przeglądarki internetowej działającej w obrębie kiosku. Upewnij się, że aplikacja przeglądarki internetowej została wdrożona na urządzeniach kiosków przy użyciu usługi [Aplikacje klienckie](apps-add.md).

  Podaj następujące ustawienia:

  - **Adres URL domyślnej strony głównej** : Wprowadź domyślny adres URL pokazywany po otwarciu przeglądarki kiosku lub ponownym uruchomieniu przeglądarki. Na przykład wprowadź adres `http://bing.com` lub `http://www.contoso.com`.

  - **Przycisk Strona główna**: **Pokaż** lub **Ukryj** przycisk Strona główna przeglądarki kiosku. Domyślnie ten przycisk nie jest wyświetlany.

  - **Przyciski nawigacyjne**: **Pokaż** lub **Ukryj** przyciski przechodzenia dalej i wstecz. Domyślnie przyciski nawigacyjne nie są wyświetlane.

  - **Przycisk zakończenia sesji**: **Pokaż** lub **Ukryj** przycisk zakończenia sesji. Jeśli przycisk jest wyświetlany, po wybraniu go przez użytkownika w aplikacji pojawia się monit o zakończenie sesji. Po potwierdzeniu przeglądarka czyści wszystkie dane przeglądania (pliki cookies, pamięć podręczną itd.), a następnie otwiera domyślny adres URL. Domyślnie ten przycisk nie jest wyświetlany.

  - **Odśwież przeglądarkę po czasie bezczynności**: Wprowadź czas bezczynności (1–1440 minut), po którym przeglądarka kiosku jest uruchamiana od nowa. Czas bezczynności to liczba minut od ostatniej interakcji użytkownika. Domyślnie ta wartość pozostaje pusta, co oznacza, że nie ma limitu czasu bezczynności.

  - **Dozwolone witryny internetowe**: To ustawienie umożliwia zezwolenie na otwieranie określonych witryn internetowych. Mówiąc inaczej, ta funkcja umożliwia ograniczenie lub uniemożliwienie użycia witryn internetowych w urządzeniu. Można na przykład zezwolić na otwieranie wszystkich witryn internetowych w lokalizacji `contoso.com*`. Domyślnie wszystkie witryny internetowe są dozwolone.

    Aby zezwolić na określone witryny internetowe, przekaż plik CSV zawierający listę dozwolonych witryn internetowych. Jeśli nie dodasz pliku CSV, wszystkie witryny internetowe będą dozwolone.

  Wybierz przycisk **OK**, aby zapisać zmiany.

- **Użyj alternatywnego układu ekranu startowego**: Wybierz pozycję **Tak**, aby wprowadzić plik XML, który opisuje sposób wyświetlania aplikacji w menu Start, w tym ich kolejność. Użyj tej opcji, jeśli potrzebujesz większej liczby dostosowań w menu Start. Artykuł [Customize and export Start layout (Dostosowywanie i eksportowanie układu menu Start)](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) zawiera wskazówki i przykładowy kod XML.

- **Pasek zadań systemu Windows**: Wybierz opcję **pokazywania** lub **ukrywania** paska zadań. Domyślnie pasek zadań nie jest wyświetlany.

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

Urządzenia platformy Windows Holographic for Business można skonfigurować tak, aby były uruchamiane w trybie kiosku z jedną aplikacją lub wieloma aplikacjami. Niektóre funkcje nie są obsługiwane na platformie Windows Holographic for Business.

#### <a name="single-full-screen-app-kiosks"></a>Kioski z pojedynczą aplikacją w trybie pełnoekranowym
W przypadku wybrania trybu kiosku z pojedynczą aplikacją wprowadź następujące ustawienia:

- **Typ logowania użytkownika**: Wybierz pozycję **Konto użytkownika lokalnego**, aby wprowadzić konto użytkownika lokalnego (na urządzenie) lub konto Microsoft skojarzone z aplikacją kiosku. Konta użytkowników typu **Logowanie automatyczne** nie są obsługiwane na platformie Windows Holographic for Business.

- **Typ aplikacji**: Wybierz pozycję **Aplikacja ze Sklepu**.

- **Aplikacja do uruchamiania w trybie kiosku**: Wybierz pozycję **Dodaj aplikację ze sklepu**, a następnie wybierz aplikację z listy.

    Lista nie zawiera żadnych aplikacji? Dodaj aplikacje, wykonując czynności opisane w temacie [Aplikacje klienckie](apps-add.md).

    Wybierz przycisk **OK**, aby zapisać zmiany.

#### <a name="multi-app-kiosks"></a>Kioski z wieloma aplikacjami
Aplikacje w tym trybie są dostępne w menu Start. Te aplikacje to jedyne aplikacje, które użytkownik może otwierać. W przypadku wybrania trybu kiosku z wieloma aplikacjami wprowadź następujące ustawienia:

- **Określ urządzenia w trybie S z systemem Windows 10 jako docelowe**: Wybierz pozycję **Nie**. Tryb S nie jest obsługiwany na platformie Windows Holographic for Business.

- **Typ logowania użytkownika**: Dodaj co najmniej jedno konta użytkownika, które może używać dodanych aplikacji. Dostępne opcje: 

  - **Logowanie automatyczne**: Ta opcja nie jest obsługiwana na platformie Windows Holographic for Business.
  - **Konta użytkowników lokalnych**: **Dodaj** konto użytkownika lokalnego (w urządzeniu). Wprowadzone konto jest używane do logowania się do kiosku.
  - **Użytkownik lub grupa usługi Azure AD (system Windows 10 w wersji 1803 lub nowszej)**: Wymaga poświadczeń użytkownika w celu zalogowania się na urządzeniu. Wybierz pozycję **Dodaj**, aby wybrać użytkowników lub grupy usługi Azure AD z listy. Można wybrać wielu użytkowników lub wiele grup. Wybierz przycisk **Wybierz**, aby zapisać zmiany.
  - **Odwiedzający platformę HoloLens**: Konto gościa, które nie wymaga żadnych poświadczeń użytkownika ani uwierzytelniania, zgodnie z opisem w sekcji [Pojęcia związane z trybem komputera udostępnionego](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Aplikacje**: Dodaj aplikacje do uruchamiania w urządzeniu kiosku. Pamiętaj, że możesz dodać kilka aplikacji.

  - **Dodaj aplikacje ze Sklepu**: Wybierz istniejącą aplikację, którą dodano za pomocą funkcji [Aplikacje klienckie](apps-add.md). Jeśli lista nie zawiera żadnych aplikacji, możesz pobrać aplikacje i [dodać je do usługi Intune](store-apps-windows.md).
  - **Dodaj aplikację systemu Win32**: Ta opcja nie jest obsługiwana na platformie Windows Holographic for Business.
  - **Dodaj przy użyciu identyfikatora AUMID**: Użyj tej opcji, aby dodać aplikacje skrzynki odbiorczej systemu Windows. Wprowadź następujące właściwości: 

    - **Nazwa aplikacji**: Element wymagany. Wprowadź nazwę aplikacji.
    - **Identyfikator modelu użytkownika aplikacji (AUMID)**: Element wymagany. Wprowadź identyfikator modelu użytkownika aplikacji (AUMID) dla aplikacji systemu Windows. Aby uzyskać ten identyfikator, zobacz [Znajdowanie identyfikatora modelu użytkownika aplikacji zainstalowanej aplikacji](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).
    - **Rozmiar kafelka**: Element wymagany. Wybierz mały, średni, szeroki lub duży rozmiar kafelka aplikacji.

- **Ustawienia przeglądarki kiosku**: Ta opcja nie jest obsługiwana na platformie Windows Holographic for Business.

- **Użyj alternatywnego układu ekranu startowego**: Wybierz pozycję **Tak**, aby wprowadzić plik XML, który opisuje sposób wyświetlania aplikacji w menu Start, w tym ich kolejność. Użyj tej opcji, jeśli potrzebujesz większej liczby dostosowań w menu Start. Artykuł [Customize and export Start layout (Dostosowywanie i eksportowanie układu menu Start)](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-for-hololens) zawiera wskazówki i oraz plik XML przygotowany dla urządzeń platformy Windows Holographic for Business.

- **Pasek zadań systemu Windows**: Ta opcja nie jest obsługiwana na platformie Windows Holographic for Business.

## <a name="next-steps"></a>Następne kroki
[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).

Można również utworzyć profile kiosku dla urządzeń z systemem [Android](device-restrictions-android.md#kiosk) i [Android Enterprise](device-restrictions-android-for-work.md#kiosk-settings).
