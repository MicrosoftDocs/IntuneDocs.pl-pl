---
title: Ustawienia kiosku dla systemu Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Skonfiguruj urządzenia z systemem Windows 10 (lub nowszym) jako kioski z pojedynczą aplikacją oraz z wieloma aplikacjami, dostosuj menu Start, dodaj aplikacje i pasek zadań oraz skonfiguruj przeglądarkę internetową w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/13/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 78b47decc297c58feadb7cd507a3ff09070d46d4
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57565744"
---
# <a name="windows-10-and-later-device-settings-to-run-as-a-kiosk-in-intune"></a>Ustawienia urządzenia z systemem Windows 10 lub nowszym, które ma działać jako kiosk w usłudze Intune

Urządzenia z systemem Windows 10 lub nowszym można skonfigurować tak, aby były uruchamiane w trybie kiosku z jedną aplikacją lub wieloma aplikacjami.

W tym artykule wymieniono i opisano różne ustawienia, którymi można sterować na urządzeniach z systemem Windows 10 i nowszym. W ramach rozwiązania do zarządzania urządzeniami przenośnymi (MDM) użyj tych ustawień, aby skonfigurować urządzenia z systemem Windows 10 lub nowszym do uruchamiania w trybie kiosku.

Jako administrator usługi Intune możesz tworzyć i przypisywać te ustawienia do urządzeń.

Aby dowiedzieć się więcej na temat funkcji kiosku systemu Windows w usłudze Intune, zobacz temat dotyczący [konfigurowania ustawień kiosku](kiosk-settings.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

- [Utwórz profil](kiosk-settings.md#create-the-profile).

- Tego profilu kiosku są bezpośrednio związane z profilu ograniczeń urządzenia możesz utworzyć przy użyciu [Microsoft Edge ustawienia kiosku](device-restrictions-windows-10.md#microsoft-edge-browser). Podsumowując:

  1. Tworzenie profilu kiosku do uruchomienia urządzenia w trybie kiosku.
  2. Tworzenie [profilu ograniczeń urządzenia](device-restrictions-windows-10.md#microsoft-edge-browser)i skonfiguruj określonych funkcji i ustawień w programie Microsoft Edge.

> [!IMPORTANT] 
> Pamiętaj przypisać ten profil kiosku do tych samych urządzeń jako swojej [profil Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser).

## <a name="single-full-screen-app-kiosks"></a>Kioski z pojedynczą aplikacją w trybie pełnoekranowym

Uruchamia tylko jednej aplikacji na urządzeniu.

- **Wybierz tryb kiosku**: Wybierz **pojedynczej aplikacji, kiosku pełnoekranowego**.

- **Typ logowania użytkownika**: dodane aplikacje działają jako wprowadzone konto użytkownika. Dostępne opcje:

  - **Logowanie automatyczne (system Windows 10 w wersji 1803 i nowszych)**: użyj go w przypadku kiosków w środowiskach publicznych, które nie wymagają logowania od użytkowników, podobnie jak dla konta gościa. To ustawienie używa [dostawcy usług kryptograficznych AssignedAccess](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Konto użytkownika lokalnego**: wprowadź konto użytkownika lokalnego (w urządzeniu). Konto, którego możesz wprowadzić loguje się na kiosku.

- **Typ aplikacji**: Wybierz typ aplikacji. Dostępne opcje:

  - **Dodaj przeglądarki Microsoft Edge**: Wybierz **przeglądarki Microsoft Edge**i wybierz polecenie **krawędzi typ trybu kiosku**:

    - **Znakowania cyfrowego/Interactive**: zostanie otwarty na pełnym ekranie adresu URL i zawiera tylko zawartość w tej witrynie sieci Web. [Konfigurowanie cyfrowego podpisuje](https://docs.microsoft.com/windows/configuration/setup-digital-signage) zawiera więcej informacji na temat tej funkcji.
    - **Publiczne przeglądania (InPrivate)**: działa z ograniczoną wersję wieloma kartami Microsoft Edge. Użytkownicy mogą przeglądać publicznie lub zakończyć ich sesji przeglądania.

    Aby uzyskać więcej informacji na temat tych opcji, zobacz [trybu kiosku wdrażanie przeglądarki Microsoft Edge](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

    > [!NOTE]
    > To ustawienie włącza przeglądarki Microsoft Edge na urządzeniu. Aby skonfigurować ustawienia specyficzne dla Microsoft Edge, należy utworzyć profil konfiguracji urządzeń (**konfiguracji urządzenia** > **profile** > **Utwórz profil**  >  **Systemu Windows 10** platformy > **ograniczenia dotyczące urządzeń** >  **przeglądarki Microsoft Edge**). [Przeglądarka Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser) wymieniono i opisano dostępne ustawienia.

    Wybierz przycisk **OK**, aby zapisać zmiany.

  - **Dodawanie przeglądarki kiosku**: Wybierz **ustawienia przeglądarki kiosku**. Te ustawienia umożliwiają kontrolowanie aplikacji przeglądarki internetowej działającej w obrębie kiosku. Upewnij się, że [aplikacja przeglądarki kiosku](https://businessstore.microsoft.com/store/details/kiosk-browser/9NGB5S5XG2KP) została pobrana ze Sklepu, dodana do usługi Intune jako [aplikacja kliencka](apps-add.md), a następnie przypisana do urządzeń kiosku.

    Podaj następujące ustawienia:

    - **Adres URL domyślnej strony głównej**: wprowadź domyślny adres URL pokazywany po otwarciu przeglądarki kiosku lub ponownym uruchomieniu przeglądarki. Na przykład wprowadź adres `http://bing.com` lub `http://www.contoso.com`.

    - **Przycisk Strona główna**: **pokazywanie** lub **ukrywanie** przycisku Strona główna przeglądarki kiosku. Domyślnie ten przycisk nie jest wyświetlany.

    - **Przyciski nawigacyjne**: **pokazywanie** lub **ukrywanie** przycisków przechodzenia dalej i wstecz. Domyślnie przyciski nawigacyjne nie są wyświetlane.

    - **Przycisk Zakończ sesję**: **pokazywanie** lub **ukrywanie** przycisku kończenia sesji. Jeśli przycisk jest wyświetlany, po wybraniu go przez użytkownika w aplikacji pojawia się monit o zakończenie sesji. Po potwierdzeniu przeglądarka czyści wszystkie dane przeglądania (pliki cookies, pamięć podręczną itd.), a następnie otwiera domyślny adres URL. Domyślnie ten przycisk nie jest wyświetlany.

    - **Odśwież przeglądarkę po upływie czasu bezczynności**: wprowadź czas bezczynności (1–1440 minut), po którym przeglądarka kiosku jest uruchamiana od nowa. Czas bezczynności to liczba minut od ostatniej interakcji użytkownika. Domyślnie ta wartość pozostaje pusta, co oznacza, że nie ma limitu czasu bezczynności.

    - **Dozwolone witryny internetowe**: to ustawienie umożliwia zezwolenie na otwieranie określonych witryn internetowych. Mówiąc inaczej, ta funkcja umożliwia ograniczenie lub uniemożliwienie użycia witryn internetowych w urządzeniu. Można na przykład zezwolić na otwieranie wszystkich witryn internetowych w lokalizacji `http://contoso.com*`. Domyślnie wszystkie witryny internetowe są dozwolone.

      Aby zezwolić na określone witryny internetowe, przekaż plik zawierający listę dozwolonych witryn internetowych w oddzielnych wierszach. Jeśli nie dodasz pliku, wszystkie witryny internetowe będą dozwolone. Usługa Intune obsługuje znak `*` (gwiazdka) jako symbol wieloznaczny.

      Przykładowy plik powinien być podobny do poniższej listy:

      `http://bing.com`  
      `https://bing.com`  
      `http://contoso.com/*`  
      `https://contoso.com/*`  

    Wybierz przycisk **OK**, aby zapisać zmiany.

  - **App Store Add**: Wybierz **dodanie aplikacji ze sklepu**, a następnie wybierz aplikację z listy.

    Lista nie zawiera żadnych aplikacji? Dodaj aplikacje, wykonując czynności opisane w temacie [Aplikacje klienckie](apps-add.md).

  Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="multi-app-kiosks"></a>Kioski z wieloma aplikacjami

Aplikacje w tym trybie są dostępne w menu Start. Te aplikacje to jedyne aplikacje, które użytkownik może otwierać. Jeśli aplikacja ma zależność od innej aplikacji, zarówno musi zawierać listę dozwolonych aplikacji. Na przykład Internet Explorer 64-bitowych zależny od programu Internet Explorer 32-bitowy, więc musisz zezwolić na "C:\Program Files\internet explorer\iexplore.exe" i "C:\Program Files (x86) \Internet". 

- **Wybierz tryb kiosku**: Wybierz **kiosk z wieloma aplikacjami**.

- **Określ urządzenia w trybie S z systemem Windows 10 jako docelowe**:
  - **Tak**: zezwala na aplikacje ze sklepu i aplikacje AUMID (z wyłączeniem aplikacji systemu Win32) w profilu kiosku.
  - **Nie**: zezwala na aplikacje ze sklepu, aplikacje systemu Win32 i aplikacje AUMID w profilu kiosku. Tego profilu kiosku nie są wdrażane na urządzeniach tryb S.

- **Typ logowania użytkownika**: dodane aplikacje działają jako wprowadzone konto użytkownika. Dostępne opcje:

  - **Logowanie automatyczne (system Windows 10 w wersji 1803 i nowszych)**: użyj go w przypadku kiosków w środowiskach publicznych, które nie wymagają logowania od użytkowników, podobnie jak dla konta gościa. To ustawienie używa [dostawcy usług kryptograficznych AssignedAccess](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Konto użytkownika lokalnego**: **dodaj** konto użytkownika lokalnego (w urządzeniu). Konto, którego możesz wprowadzić loguje się na kiosku.
  - **Użytkownik lub grupa usługi Azure AD (system Windows 10 w wersji 1803 i nowszych)**: wybierz pozycję **Dodaj** i wybierz użytkowników lub grupy usługi Azure AD z listy. Można wybrać wielu użytkowników lub wiele grup. Wybierz przycisk **Wybierz**, aby zapisać zmiany.
  - **Gość HaloLens**: konto gościa, które nie wymaga żadnych poświadczeń użytkownika ani uwierzytelniania, zgodnie z opisem w sekcji [Shared PC mode concepts (Pojęcia związane z trybem komputera udostępnionego)](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Przeglądarka i aplikacje**: dodaj aplikacje do uruchamiania w urządzeniu kiosku. Pamiętaj, że możesz dodać kilka aplikacji.

  - **Przeglądarki**

    - **Dodaj Microsoft Edge**: Microsoft Edge zostanie dodany do siatki aplikację i wszystkie aplikacje mogą być uruchamiane na tym kiosku. Wybierz **typ trybu kiosku Microsoft Edge**:

      - **Tryb normalny (pełnej wersji programu Microsoft Edge)**: uruchamia pełnej wersji programu Microsoft Edge z wszystkich funkcji przeglądania. Stan i dane użytkownika są zapisywane między sesjami.
      - **Publiczne przeglądania (InPrivate)**: z wersją wieloma kartami InPrivate przeglądarki Microsoft Edge z dopasowane środowisko dla kioski, które działają w trybie pełnoekranowym.

      Aby uzyskać więcej informacji na temat tych opcji, zobacz [trybu kiosku wdrażanie przeglądarki Microsoft Edge](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

      > [!NOTE]
      > To ustawienie włącza przeglądarki Microsoft Edge na urządzeniu. Aby skonfigurować ustawienia specyficzne dla Microsoft Edge, należy utworzyć profil konfiguracji urządzeń (**konfiguracji urządzenia** > **profile** > **Utwórz profil**  >  **Systemu Windows 10** platformy > **ograniczenia dotyczące urządzeń** >  **przeglądarki Microsoft Edge**). [Przeglądarka Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser) wymieniono i opisano dostępne ustawienia.

      Wybierz przycisk **OK**, aby zapisać zmiany.

    - **Dodaj przeglądarkę kiosku**: te ustawienia umożliwiają kontrolowanie aplikacji przeglądarki internetowej działającej w obrębie kiosku. Upewnij się, że aplikacja przeglądarki internetowej została wdrożona na urządzeniach kiosków przy użyciu usługi [Aplikacje klienckie](apps-add.md).

      Podaj następujące ustawienia:

      - **Adres URL domyślnej strony głównej**: wprowadź domyślny adres URL pokazywany po otwarciu przeglądarki kiosku lub ponownym uruchomieniu przeglądarki. Na przykład wprowadź adres `http://bing.com` lub `http://www.contoso.com`.

      - **Przycisk Strona główna**: **pokazywanie** lub **ukrywanie** przycisku Strona główna przeglądarki kiosku. Domyślnie ten przycisk nie jest wyświetlany.

      - **Przyciski nawigacyjne**: **pokazywanie** lub **ukrywanie** przycisków przechodzenia dalej i wstecz. Domyślnie przyciski nawigacyjne nie są wyświetlane.

      - **Przycisk Zakończ sesję**: **pokazywanie** lub **ukrywanie** przycisku kończenia sesji. Jeśli przycisk jest wyświetlany, po wybraniu go przez użytkownika w aplikacji pojawia się monit o zakończenie sesji. Po potwierdzeniu przeglądarka czyści wszystkie dane przeglądania (pliki cookies, pamięć podręczną itd.), a następnie otwiera domyślny adres URL. Domyślnie ten przycisk nie jest wyświetlany.

      - **Odśwież przeglądarkę po upływie czasu bezczynności**: wprowadź czas bezczynności (1–1440 minut), po którym przeglądarka kiosku jest uruchamiana od nowa. Czas bezczynności to liczba minut od ostatniej interakcji użytkownika. Domyślnie ta wartość pozostaje pusta, co oznacza, że nie ma limitu czasu bezczynności.

      - **Dozwolone witryny internetowe**: to ustawienie umożliwia zezwolenie na otwieranie określonych witryn internetowych. Mówiąc inaczej, ta funkcja umożliwia ograniczenie lub uniemożliwienie użycia witryn internetowych w urządzeniu. Można na przykład zezwolić na otwieranie wszystkich witryn internetowych w lokalizacji `contoso.com*`. Domyślnie wszystkie witryny internetowe są dozwolone.

        Aby zezwolić na określone witryny internetowe, przekaż plik CSV zawierający listę dozwolonych witryn internetowych. Jeśli nie dodasz pliku CSV, wszystkie witryny internetowe będą dozwolone.

      Wybierz przycisk **OK**, aby zapisać zmiany.

  - **Aplikacje**

    - **Dodaj aplikację ze sklepu**: dodaj aplikację ze Microsoft Store dla Firm. Jeśli lista nie zawiera żadnych aplikacji, możesz pobrać aplikacje i [dodać je do usługi Intune](store-apps-windows.md). Można na przykład dodać przeglądarkę kiosku, program Excel, program OneNote i inne.

      Wybierz przycisk **OK**, aby zapisać zmiany.

    - **Dodaj aplikację systemu Win32**: aplikacja systemu Win32 to tradycyjna aplikacja klasyczna, taka jak program Visual Studio Code lub Google Chrome. Wprowadź następujące właściwości:

      - **Nazwa aplikacji**: wymagana. Wprowadź nazwę aplikacji.
      - **Ścieżka lokalna**: wymagana. Wprowadź ścieżkę do pliku wykonywalnego, taką jak `C:\Program Files (x86)\Microsoft VS Code\Code.exe` lub `C:\Program Files (x86)\Google\Chrome\Application\chrome.exe`.
      - **Identyfikator modelu użytkownika aplikacji (AUMID)**: podaj identyfikator modelu użytkownika aplikacji (AUMID) dla aplikacji Win32. To ustawienie określa początkowy układ kafelka na pulpicie. Informacje na temat uzyskiwania tego identyfikatora zawiera artykuł [Get-StartApps](https://docs.microsoft.com/powershell/module/startlayout/get-startapps?view=win10-ps) (Polecenie Get-StartApps).

      Wybierz przycisk **OK**, aby zapisać zmiany.

    - **Dodaj według identyfikatora AUMID**: użyj tej opcji, aby dodać aplikacje skrzynki odbiorczej systemu Windows, na przykład Notatnik lub Kalkulator. Wprowadź następujące właściwości:

      - **Nazwa aplikacji**: wymagana. Wprowadź nazwę aplikacji.
      - **Identyfikator modelu użytkownika aplikacji (AUMID)**: wymagany. Wprowadź identyfikator modelu użytkownika aplikacji (AUMID) dla aplikacji systemu Windows. Aby uzyskać ten identyfikator, zobacz [Znajdowanie identyfikatora modelu użytkownika aplikacji zainstalowanej aplikacji](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

      Wybierz przycisk **OK**, aby zapisać zmiany.

    - **Rozmiar kafelka**: wymagany. Wybierz mały, średni, szeroki lub duży rozmiar kafelka aplikacji.

  > [!TIP]
  > Po dodaniu wszystkich aplikacji można zmienić kolejność ich wyświetlania, klikając i przeciągając aplikacje na liście.  

- **Użyj alternatywnego układ menu Start**: wybierz pozycję **Tak**, aby wprowadzić plik XML, który opisuje sposób wyświetlania aplikacji w menu Start, w tym ich kolejność. Użyj tej opcji, jeśli potrzebujesz większej liczby dostosowań w menu Start. Artykuł [Customize and export Start layout (Dostosowywanie i eksportowanie układu menu Start)](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) zawiera wskazówki i przykładowy kod XML.

- **Pasek zadań systemu Windows**: wybierz opcję **pokazywania** lub **ukrywania** paska zadań. Domyślnie pasek zadań nie jest wyświetlany. Ikony, takich jak ikona sieci Wi-Fi, są wyświetlane, ale użytkownicy końcowi nie mogą zmieniać ich ustawień.

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).

Można również utworzyć profile kiosku dla urządzeń z systemem [Android](device-restrictions-android.md#kiosk), [Android Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings) oraz [Windows Holographic for Business](kiosk-settings-holographic.md).
