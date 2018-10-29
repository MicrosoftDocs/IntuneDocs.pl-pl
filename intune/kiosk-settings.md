---
title: Ustawienia kiosku dla systemu Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Możesz skonfigurować urządzenia z systemem Windows 10 (lub nowszym) jako kioski z pojedynczą aplikacją oraz z wieloma aplikacjami, dostosowując menu Start, dodając aplikacje i pasek zadań oraz konfigurując przeglądarkę internetową. Możesz również skonfigurować urządzenia platformy Windows Holographic for Business jako kioski z wieloma aplikacjami w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 59e2ab4635c8488b99781ac123aacd0854967dc8
ms.sourcegitcommit: c3ac9e5f6240223cb5dfed8b44c7425066d6ea86
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2018
ms.locfileid: "49380035"
---
# <a name="kiosk-settings-for-windows-10-and-later-in-intune"></a>Ustawienia kiosku dla systemu Windows 10 (i nowszych) w usłudze Intune

W urządzeniach z systemem Windows 10 można używać usługi Intune do uruchamiania tych urządzeń jako kiosku. Kiosk może uruchamiać jedną aplikację lub wiele aplikacji. Można również wyświetlić i dostosowywać menu Start, dodawać różne aplikacje, w tym aplikacje Win32, dodawać określoną stronę główną do przeglądarki internetowej i wykonywać inne czynności. 

Kroki opisane w tym artykule umożliwiają utworzenie kiosku z jedną aplikacją lub kiosku z wieloma aplikacjami w usłudze Intune.

Usługa Intune obsługuje jeden profil kiosku na urządzenie. Jeśli potrzebujesz wielu profilów kiosku w jednym urządzeniu, możesz użyć [niestandardowego identyfikatora OMA-URI](custom-settings-windows-10.md).

## <a name="kiosk-settings"></a>Ustawienia kiosku

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, wpisz nazwę usługi **Intune** w filtrze, a następnie wybierz pozycję **Microsoft Intune**.
2. Wybierz kolejno pozycje **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Wprowadź następujące właściwości:

   - **Nazwa**: wprowadź opisową nazwę nowego profilu.
   - **Opis:** wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
   - **Platforma**: wybierz pozycję **Windows 10 i nowsze**
   - **Typ profilu**: wybierz pozycję **Kiosk (wersja zapoznawcza)**

4. Wybierz **tryb kiosku**. **Tryb kiosku** wskazuje typ trybu kiosku obsługiwany przez zasady. Dostępne opcje:

    - **Nieskonfigurowane** (domyślne): te zasady nie umożliwiają korzystania z trybu kiosku.
    - **Kiosk z pojedynczą aplikacją w trybie pełnoekranowym**: urządzenie działa jako jedno konto użytkownika i blokuje je do pojedynczej aplikacji sklepu. Gdy użytkownik zaloguje się, jest uruchamiana konkretna aplikacja. Ten tryb uniemożliwia także użytkownikowi otwieranie nowych aplikacji oraz zmianę uruchomionej aplikacji.
    - **Kiosk z wieloma aplikacjami**: w urządzeniu działa wiele aplikacji ze sklepu, aplikacji Win32 lub aplikacji skrzynki odbiorczej systemu Windows dzięki użyciu identyfikatora modelu użytkownika aplikacji (AUMID). Tylko dodane aplikacje są dostępne w urządzeniu.

        Korzyści z kiosku z wieloma aplikacjami (czyli urządzenia o stałym przeznaczeniu) polegają na udostępnieniu użytkownikom łatwego do poznania środowiska, w którym są dostępne tylko potrzebne im aplikacje. Aplikacje, których użytkownicy nie potrzebują, są usuwane z widoku.

## <a name="single-full-screen-app-kiosks"></a>Kioski z pojedynczą aplikacją w trybie pełnoekranowym
W przypadku wybrania trybu kiosku z pojedynczą aplikacją wprowadź następujące ustawienia:

- **Typ logowania użytkownika**: dodane aplikacje działają jako wprowadzone konto użytkownika. Dostępne opcje:

  - **Logowanie automatyczne (system Windows 10 w wersji 1803 i nowszych)**: w przypadku kiosków w środowiskach publicznych, które nie wymagają logowania od użytkowników, podobnie jak dla konta gościa. To ustawienie używa [dostawcy usług kryptograficznych AssignedAccess](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Konto użytkownika lokalnego**: wprowadź konto użytkownika lokalnego (w urządzeniu). Wprowadzone konto jest używane do logowania się do kiosku.

- **Typ aplikacji**: wybierz pozycję **Aplikacja ze sklepu**.

- **Aplikacja do uruchamiania w trybie kiosku**: wybierz pozycję **Dodaj aplikację ze sklepu**, a następnie wybierz aplikację z listy.

    Lista nie zawiera żadnych aplikacji? Dodaj aplikacje, wykonując czynności opisane w temacie [Aplikacje klienckie](apps-add.md).

    Wybierz przycisk **OK**, aby zapisać zmiany.

- **Ustawienia przeglądarki kiosku**: te ustawienia umożliwiają kontrolowanie aplikacji przeglądarki internetowej działającej w obrębie kiosku. Upewnij się, że [aplikacja przeglądarki kiosku](https://businessstore.microsoft.com/store/details/kiosk-browser/9NGB5S5XG2KP) została pobrana ze sklepu, dodana do usługi Intune jako [aplikacja kliencka](apps-add.md), a następnie przypisana do urządzeń kiosku.

  Podaj następujące ustawienia:

  - **Adres URL domyślnej strony głównej**: wprowadź domyślny adres URL pokazywany po otwarciu przeglądarki kiosku lub ponownym uruchomieniu przeglądarki. Na przykład wprowadź adres `http://bing.com` lub `http://www.contoso.com`.

  - **Przycisk Strona główna**: **pokazywanie** lub **ukrywanie** przycisku Strona główna przeglądarki kiosku. Domyślnie ten przycisk nie jest wyświetlany.

  - **Przyciski nawigacyjne**: **pokazywanie** lub **ukrywanie** przycisków przechodzenia dalej i wstecz. Domyślnie przyciski nawigacyjne nie są wyświetlane.

  - **Przycisk Zakończ sesję**: **pokazywanie** lub **ukrywanie** przycisku kończenia sesji. Jeśli przycisk jest wyświetlany, po wybraniu go przez użytkownika w aplikacji pojawia się monit o zakończenie sesji. Po potwierdzeniu przeglądarka czyści wszystkie dane przeglądania (pliki cookies, pamięć podręczną itd.), a następnie otwiera domyślny adres URL. Domyślnie ten przycisk nie jest wyświetlany.

  - **Odśwież przeglądarkę po upływie czasu bezczynności**: wprowadź czas bezczynności (1–1440 minut), po którym przeglądarka kiosku jest uruchamiana od nowa. Czas bezczynności to liczba minut od ostatniej interakcji użytkownika. Domyślnie ta wartość pozostaje pusta, co oznacza, że nie ma limitu czasu bezczynności.

  - **Dozwolone witryny internetowe**: to ustawienie umożliwia zezwolenie na otwieranie określonych witryn internetowych. Mówiąc inaczej, ta funkcja umożliwia ograniczenie lub uniemożliwienie użycia witryn internetowych w urządzeniu. Można na przykład zezwolić na otwieranie wszystkich witryn internetowych w lokalizacji `http://contoso.com*`. Domyślnie wszystkie witryny internetowe są dozwolone.

    Aby zezwolić na określone witryny internetowe, przekaż plik CSV zawierający listę dozwolonych witryn internetowych. Jeśli nie dodasz pliku CSV, wszystkie witryny internetowe będą dozwolone. Usługa Intune obsługuje znak * (gwiazdka) jako symbol wieloznaczny.

  Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="multi-app-kiosks"></a>Kioski z wieloma aplikacjami

Aplikacje w tym trybie są dostępne w menu Start. Te aplikacje to jedyne aplikacje, które użytkownik może otwierać.

W przypadku wybrania trybu kiosku z wieloma aplikacjami wprowadź następujące ustawienia:

- **Określ urządzenia w trybie S z systemem Windows 10 S jako docelowe**: wybierz pozycję **Tak**, aby zezwolić na aplikacje ze sklepu i aplikacje AUMID (z wyłączeniem aplikacji systemu Win32) w profilu kiosku. Wybierz pozycję **Nie**, aby zezwolić na aplikacje ze sklepu, aplikacje systemu Win32 i aplikacje AUMID w profilu kiosku. Po wybraniu pozycji **Nie** ten profil kiosku nie będzie wdrażany na urządzeniach w trybie S.

- **Typ logowania użytkownika**: dodane aplikacje działają jako wprowadzone konto użytkownika. Dostępne opcje:

  - **Logowanie automatyczne (system Windows 10 w wersji 1803 i nowszych)**: w przypadku kiosków w środowiskach publicznych, które nie wymagają logowania od użytkowników, podobnie jak dla konta gościa. To ustawienie używa [dostawcy usług kryptograficznych AssignedAccess](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Konto użytkownika lokalnego**: **dodaj** konto użytkownika lokalnego (w urządzeniu). Wprowadzone konto jest używane do logowania się do kiosku.
  - **Użytkownik lub grupa usługi Azure AD (system Windows 10 w wersji 1803 i nowszych)**: wybierz pozycję **Dodaj**, aby wybrać użytkowników lub grupy usługi Azure AD z listy. Można wybrać wielu użytkowników lub wiele grup. Wybierz przycisk **Wybierz**, aby zapisać zmiany.
  - **Gość HaloLens**: konto gościa, które nie wymaga żadnych poświadczeń użytkownika ani uwierzytelniania, zgodnie z opisem w sekcji [Shared PC mode concepts (Pojęcia związane z trybem komputera udostępnionego)](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Aplikacje**: dodaj aplikacje do uruchamiania w urządzeniu kiosku. Pamiętaj, że możesz dodać kilka aplikacji.

  - **Dodaj aplikację ze sklepu**: dodaj aplikację ze Microsoft Store dla Firm. Jeśli lista nie zawiera żadnych aplikacji, możesz pobrać aplikacje i [dodać je do usługi Intune](store-apps-windows.md). Można na przykład dodać przeglądarkę kiosku, program Excel, program OneNote i inne.

  - **Dodaj aplikację systemu Win32**: aplikacja systemu Win32 to tradycyjna aplikacja klasyczna, taka jak program Visual Studio Code lub Google Chrome. Wprowadź następujące właściwości:

    - **Nazwa aplikacji**: wymagana. Wprowadź nazwę aplikacji.
    - **Ścieżka lokalna**: wymagana. Wprowadź ścieżkę do pliku wykonywalnego, taką jak `C:\Program Files (x86)\Microsoft VS Code\Code.exe` lub `C:\Program Files (x86)\Google\Chrome\Application\chrome.exe`.
    - **Identyfikator modelu użytkownika aplikacji (AUMID)**: opcjonalny. Wprowadź identyfikator modelu użytkownika aplikacji (AUMID) dla aplikacji systemu Win32. To ustawienie określa początkowy układ kafelka na pulpicie. Aby uzyskać ten identyfikator, zobacz [Znajdowanie identyfikatora modelu użytkownika aplikacji zainstalowanej aplikacji](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).
    - **Rozmiar kafelka**: wymagany. Wybierz mały, średni, szeroki lub duży rozmiar kafelka aplikacji.
  
  - **Dodaj według identyfikatora AUMID**: użyj tej opcji, aby dodać aplikacje skrzynki odbiorczej systemu Windows, na przykład Notatnik lub Kalkulator. Wprowadź następujące właściwości: 

    - **Nazwa aplikacji**: wymagana. Wprowadź nazwę aplikacji.
    - **Identyfikator modelu użytkownika aplikacji (AUMID)**: wymagany. Wprowadź identyfikator modelu użytkownika aplikacji (AUMID) dla aplikacji systemu Windows. Aby uzyskać ten identyfikator, zobacz [Znajdowanie identyfikatora modelu użytkownika aplikacji zainstalowanej aplikacji](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).
    - **Rozmiar kafelka**: wymagany. Wybierz mały, średni, szeroki lub duży rozmiar kafelka aplikacji.

  > [!TIP]
  > Po dodaniu wszystkich aplikacji można zmienić kolejność ich wyświetlania, klikając i przeciągając aplikacje na liście.  

  Wybierz przycisk **OK**, aby zapisać zmiany.

- **Ustawienia przeglądarki kiosku**: te ustawienia umożliwiają kontrolowanie aplikacji przeglądarki internetowej działającej w obrębie kiosku. Upewnij się, że aplikacja przeglądarki internetowej została wdrożona na urządzeniach kiosków przy użyciu usługi [Aplikacje klienckie](apps-add.md).

  Podaj następujące ustawienia:

  - **Adres URL domyślnej strony głównej**: wprowadź domyślny adres URL pokazywany po otwarciu przeglądarki kiosku lub ponownym uruchomieniu przeglądarki. Na przykład wprowadź adres `http://bing.com` lub `http://www.contoso.com`.

  - **Przycisk Strona główna**: **pokazywanie** lub **ukrywanie** przycisku Strona główna przeglądarki kiosku. Domyślnie ten przycisk nie jest wyświetlany.

  - **Przyciski nawigacyjne**: **pokazywanie** lub **ukrywanie** przycisków przechodzenia dalej i wstecz. Domyślnie przyciski nawigacyjne nie są wyświetlane.

  - **Przycisk Zakończ sesję**: **pokazywanie** lub **ukrywanie** przycisku kończenia sesji. Jeśli przycisk jest wyświetlany, po wybraniu go przez użytkownika w aplikacji pojawia się monit o zakończenie sesji. Po potwierdzeniu przeglądarka czyści wszystkie dane przeglądania (pliki cookies, pamięć podręczną itd.), a następnie otwiera domyślny adres URL. Domyślnie ten przycisk nie jest wyświetlany.

  - **Odśwież przeglądarkę po upływie czasu bezczynności**: wprowadź czas bezczynności (1–1440 minut), po którym przeglądarka kiosku jest uruchamiana od nowa. Czas bezczynności to liczba minut od ostatniej interakcji użytkownika. Domyślnie ta wartość pozostaje pusta, co oznacza, że nie ma limitu czasu bezczynności.

  - **Dozwolone witryny internetowe**: to ustawienie umożliwia zezwolenie na otwieranie określonych witryn internetowych. Mówiąc inaczej, ta funkcja umożliwia ograniczenie lub uniemożliwienie użycia witryn internetowych w urządzeniu. Można na przykład zezwolić na otwieranie wszystkich witryn internetowych w lokalizacji `contoso.com*`. Domyślnie wszystkie witryny internetowe są dozwolone.

    Aby zezwolić na określone witryny internetowe, przekaż plik CSV zawierający listę dozwolonych witryn internetowych. Jeśli nie dodasz pliku CSV, wszystkie witryny internetowe będą dozwolone.

  Wybierz przycisk **OK**, aby zapisać zmiany.

- **Użyj alternatywnego układ menu Start**: wybierz pozycję **Tak**, aby wprowadzić plik XML, który opisuje sposób wyświetlania aplikacji w menu Start, w tym ich kolejność. Użyj tej opcji, jeśli potrzebujesz większej liczby dostosowań w menu Start. Artykuł [Customize and export Start layout (Dostosowywanie i eksportowanie układu menu Start)](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) zawiera wskazówki i przykładowy kod XML.

- **Pasek zadań systemu Windows**: wybierz opcję **pokazywania** lub **ukrywania** paska zadań. Domyślnie pasek zadań nie jest wyświetlany.

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

Urządzenia platformy Windows Holographic for Business można skonfigurować tak, aby były uruchamiane w trybie kiosku z jedną aplikacją lub wieloma aplikacjami. Niektóre funkcje nie są obsługiwane na platformie Windows Holographic for Business.

#### <a name="single-full-screen-app-kiosks"></a>Kioski z pojedynczą aplikacją w trybie pełnoekranowym
W przypadku wybrania trybu kiosku z pojedynczą aplikacją wprowadź następujące ustawienia:

- **Typ logowania użytkownika**: wybierz pozycję **Konto użytkownika lokalnego**, aby wprowadzić konto użytkownika lokalnego (na urządzenie) lub konto Microsoft skojarzone z aplikacją kiosku. Konta użytkowników typu **Logowanie automatyczne** nie są obsługiwane na platformie Windows Holographic for Business.

- **Typ aplikacji**: wybierz pozycję **Aplikacja ze sklepu**.

- **Aplikacja do uruchamiania w trybie kiosku**: wybierz pozycję **Dodaj aplikację ze sklepu**, a następnie wybierz aplikację z listy.

    Lista nie zawiera żadnych aplikacji? Dodaj aplikacje, wykonując czynności opisane w temacie [Aplikacje klienckie](apps-add.md).

    Wybierz przycisk **OK**, aby zapisać zmiany.

#### <a name="multi-app-kiosks"></a>Kioski z wieloma aplikacjami
Aplikacje w tym trybie są dostępne w menu Start. Te aplikacje to jedyne aplikacje, które użytkownik może otwierać. W przypadku wybrania trybu kiosku z wieloma aplikacjami wprowadź następujące ustawienia:

- **Określ urządzenia w trybie S z systemem Windows 10 jako docelowe**: wybierz pozycję **Nie**. Tryb S nie jest obsługiwany na platformie Windows Holographic for Business.

- **Typ logowania użytkownika**: dodaj co najmniej jedno konto użytkownika, które może używać dodanych aplikacji. Dostępne opcje: 

  - **Logowanie automatyczne**: nie jest obsługiwane na platformie Windows Holographic for Business.
  - **Konta użytkownika lokalnego**: **dodaj** konto użytkownika lokalnego (w urządzeniu). Wprowadzone konto jest używane do logowania się do kiosku.
  - **Użytkownik lub grupa usługi Azure AD (system Windows 10 w wersji 1803 i nowszych)**: wymaga poświadczeń użytkownika do zalogowania na urządzeniu. Wybierz pozycję **Dodaj**, aby wybrać użytkowników lub grupy usługi Azure AD z listy. Można wybrać wielu użytkowników lub wiele grup. Wybierz przycisk **Wybierz**, aby zapisać zmiany.
  - **Gość HaloLens**: konto gościa, które nie wymaga żadnych poświadczeń użytkownika ani uwierzytelniania, zgodnie z opisem w sekcji [Shared PC mode concepts (Pojęcia związane z trybem komputera udostępnionego)](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Aplikacje**: dodaj aplikacje do uruchamiania w urządzeniu kiosku. Pamiętaj, że możesz dodać kilka aplikacji.

  - **Dodaj aplikacje ze sklepu**: wybierz istniejącą aplikację, którą dodano za pomocą usługi [Aplikacje klienckie](apps-add.md). Jeśli lista nie zawiera żadnych aplikacji, możesz pobrać aplikacje i [dodać je do usługi Intune](store-apps-windows.md).
  - **Dodaj aplikację systemu Win32**: opcja nieobsługiwana na platformie Windows Holographic for Business.
  - **Dodaj według identyfikatora AUMID**: użyj tej opcji, aby dodać aplikacje skrzynki odbiorczej systemu Windows. Wprowadź następujące właściwości: 

    - **Nazwa aplikacji**: wymagana. Wprowadź nazwę aplikacji.
    - **Identyfikator modelu użytkownika aplikacji (AUMID)**: wymagany. Wprowadź identyfikator modelu użytkownika aplikacji (AUMID) dla aplikacji systemu Windows. Aby uzyskać ten identyfikator, zobacz [Znajdowanie identyfikatora modelu użytkownika aplikacji zainstalowanej aplikacji](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).
    - **Rozmiar kafelka**: wymagany. Wybierz mały, średni, szeroki lub duży rozmiar kafelka aplikacji.

- **Ustawienia przeglądarki kiosku**: nie są obsługiwane na platformie Windows Holographic for Business.

- **Użyj alternatywnego układ menu Start**: wybierz pozycję **Tak**, aby wprowadzić plik XML, który opisuje sposób wyświetlania aplikacji w menu Start, w tym ich kolejność. Użyj tej opcji, jeśli potrzebujesz większej liczby dostosowań w menu Start. Artykuł [Customize and export Start layout (Dostosowywanie i eksportowanie układu menu Start)](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-for-hololens) zawiera wskazówki i oraz plik XML przygotowany dla urządzeń platformy Windows Holographic for Business.

- **Pasek zadań systemu Windows**: nie jest obsługiwany na platformie Windows Holographic for Business.



## <a name="next-steps"></a>Następne kroki
[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).
