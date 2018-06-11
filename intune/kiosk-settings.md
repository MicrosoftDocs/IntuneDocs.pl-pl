---
title: Ustawienia kiosku dla systemu Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Informacje na temat ustawień usługi Microsoft Intune służących do kontrolowania ustawień i funkcjonalności na urządzeniach z systemem Windows 10.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 5/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 897ff48253961d6e1aa83bf36113c362d4548fbf
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34745178"
---
# <a name="kiosk-settings-for-windows-10-and-later-in-intune"></a>Ustawienia kiosku dla systemu Windows 10 (i nowszych) w usłudze Intune

Profile kiosku mogą służyć do konfigurowania urządzeń z systemem Windows 10 tak, aby uruchamiały jedną lub wiele aplikacji. W przypadku konfigurowania profilu kiosku należy również wybrać opcję wyświetlania menu Start lub rezygnacji z niego, instalowania przeglądarki sieciowej i inne opcje.

## <a name="kiosk-settings"></a>Ustawienia kiosku

1. Wybierz pozycję **Dodaj**, aby utworzyć środowisko kiosku.
2. Wprowadź **nazwę konfiguracji kiosku** dla swojego kiosku. Ta nazwa identyfikuje grupę aplikacji, układ tych aplikacji w menu Start oraz użytkowników przypisanych do danej konfiguracji kiosku.
3. Wybierz pozycję **Tryb kiosku**. **Tryb kiosku** wskazuje typ trybu kiosku obsługiwany przez zasady. Dostępne opcje:

  - **Nieskonfigurowane** (domyślne): zasady nie umożliwiają korzystania z trybu kiosku.
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

  - **Pokaż przycisk Strona główna**: pokazywanie (**Wymagaj**) lub ukrywanie (**Nieskonfigurowany**) przycisku Strona główna przeglądarki kiosku. Domyślnie ten przycisk nie jest konfigurowany.

  - **Pokaż przycisk nawigacji**: pokazywanie (**Wymagaj**) lub ukrywanie (**Nieskonfigurowany**) przycisków Dalej i Wstecz. Domyślnie przyciski nawigacji nie są konfigurowane.

  - **Odśwież przeglądarkę, gdy użytkownik przekracza limit czasu bezczynności**: wprowadź czas bezczynności sesji (w minutach), po którym przeglądarka kiosku jest uruchamiana od nowa. Wartość to liczba całkowita z przedziału od 1 do 1440 minut. Domyślnie to pole pozostaje puste, co oznacza, że nie ma limitu czasu bezczynności.

  - **Zablokowane witryny internetowe**: lista adresów URL zablokowanych witryn internetowych (z obsługą symboli wieloznacznych). Użyj tego ustawienia, aby uniemożliwić otwieranie określonych witryn w przeglądarce. Możesz również **zaimportować** plik CSV zawierający listę. Inna opcja to utworzenie pliku CSV (**Eksportuj**) zawierającego dodawane witryny.

  - **Wyjątki witryn internetowych**: lista wyjątków adresów URL zablokowanych witryn internetowych (z obsługą symboli wieloznacznych). Użyj tego ustawienia, aby zezwolić przeglądarce na otwieranie określonych witryn. Te wyjątki są podzestawem zablokowanych adresów URL. Jeśli adres URL znajduje się na liście zablokowanych witryn internetowych i na liście wyjątków witryn internetowych, wyjątek zostanie uwzględniony.

    Możesz również **zaimportować** plik CSV zawierający listę. Inna opcja to utworzenie pliku CSV (**Eksportuj**) zawierającego dodawane witryny.

2. Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="next-steps"></a>Następne kroki
[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).