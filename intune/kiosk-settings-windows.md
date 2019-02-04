---
title: Ustawienia kiosku dla systemu Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Skonfiguruj urządzenia z systemem Windows 10 (lub nowszym) jako kioski z pojedynczą aplikacją oraz z wieloma aplikacjami, dostosuj menu Start, dodaj aplikacje i pasek zadań oraz skonfiguruj przeglądarkę internetową w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.openlocfilehash: 61cb1a3c9de10020381d62a2a7795d5ff728db22
ms.sourcegitcommit: 6f2f2fa70f4e47fa5ad2f3c536ba7116e1bd1d05
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "55199425"
---
# <a name="windows-10-and-later-device-settings-to-run-as-a-kiosk-in-intune"></a>Ustawienia urządzenia z systemem Windows 10 lub nowszym, które ma działać jako kiosk w usłudze Intune

Urządzenia z systemem Windows 10 lub nowszym można skonfigurować tak, aby były uruchamiane w trybie kiosku z jedną aplikacją lub wieloma aplikacjami.

W tym artykule wymieniono i opisano różne ustawienia, którymi można sterować na urządzeniach z systemem Windows 10 i nowszym. W ramach rozwiązania do zarządzania urządzeniami przenośnymi (MDM) użyj tych ustawień, aby skonfigurować urządzenia z systemem Windows 10 lub nowszym do uruchamiania w trybie kiosku.

Jako administrator usługi Intune możesz tworzyć i przypisywać te ustawienia do urządzeń.

Aby dowiedzieć się więcej na temat funkcji kiosku systemu Windows w usłudze Intune, zobacz temat dotyczący [konfigurowania ustawień kiosku](kiosk-settings.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil](kiosk-settings.md#create-the-profile).

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

  - **Adres URL domyślnej strony głównej **: Wprowadź domyślny adres URL pokazywany po otwarciu przeglądarki kiosku lub ponownym uruchomieniu przeglądarki. Na przykład wprowadź adres `http://bing.com` lub `http://www.contoso.com`.

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

  - **Adres URL domyślnej strony głównej **: Wprowadź domyślny adres URL pokazywany po otwarciu przeglądarki kiosku lub ponownym uruchomieniu przeglądarki. Na przykład wprowadź adres `http://bing.com` lub `http://www.contoso.com`.

  - **Przycisk Strona główna**: **Pokaż** lub **Ukryj** przycisk Strona główna przeglądarki kiosku. Domyślnie ten przycisk nie jest wyświetlany.

  - **Przyciski nawigacyjne**: **Pokaż** lub **Ukryj** przyciski przechodzenia dalej i wstecz. Domyślnie przyciski nawigacyjne nie są wyświetlane.

  - **Przycisk zakończenia sesji**: **Pokaż** lub **Ukryj** przycisk zakończenia sesji. Jeśli przycisk jest wyświetlany, po wybraniu go przez użytkownika w aplikacji pojawia się monit o zakończenie sesji. Po potwierdzeniu przeglądarka czyści wszystkie dane przeglądania (pliki cookies, pamięć podręczną itd.), a następnie otwiera domyślny adres URL. Domyślnie ten przycisk nie jest wyświetlany.

  - **Odśwież przeglądarkę po czasie bezczynności**: Wprowadź czas bezczynności (1–1440 minut), po którym przeglądarka kiosku jest uruchamiana od nowa. Czas bezczynności to liczba minut od ostatniej interakcji użytkownika. Domyślnie ta wartość pozostaje pusta, co oznacza, że nie ma limitu czasu bezczynności.

  - **Dozwolone witryny internetowe**: To ustawienie umożliwia zezwolenie na otwieranie określonych witryn internetowych. Mówiąc inaczej, ta funkcja umożliwia ograniczenie lub uniemożliwienie użycia witryn internetowych w urządzeniu. Można na przykład zezwolić na otwieranie wszystkich witryn internetowych w lokalizacji `contoso.com*`. Domyślnie wszystkie witryny internetowe są dozwolone.

    Aby zezwolić na określone witryny internetowe, przekaż plik CSV zawierający listę dozwolonych witryn internetowych. Jeśli nie dodasz pliku CSV, wszystkie witryny internetowe będą dozwolone.

  Wybierz przycisk **OK**, aby zapisać zmiany.

- **Użyj alternatywnego układu ekranu startowego**: Wybierz pozycję **Tak**, aby wprowadzić plik XML, który opisuje sposób wyświetlania aplikacji w menu Start, w tym ich kolejność. Użyj tej opcji, jeśli potrzebujesz większej liczby dostosowań w menu Start. Artykuł [Customize and export Start layout (Dostosowywanie i eksportowanie układu menu Start)](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) zawiera wskazówki i przykładowy kod XML.

- **Pasek zadań systemu Windows**: Wybierz opcję **pokazywania** lub **ukrywania** paska zadań. Domyślnie pasek zadań nie jest wyświetlany. Ikony, takich jak ikona sieci Wi-Fi, są wyświetlane, ale użytkownicy końcowi nie mogą zmieniać ich ustawień.

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).

Można również utworzyć profile kiosku dla urządzeń z systemem [Android](device-restrictions-android.md#kiosk), [Android Enterprise](device-restrictions-android-for-work.md#kiosk-settings) oraz [Windows Holographic for Business](kiosk-settings-holographic.md).
