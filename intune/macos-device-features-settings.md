---
title: Ustawienia funkcji urządzeń z systemem macOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z ustawieniami umożliwiającymi konfigurowanie urządzeń z systemem macOS pod kątem obsługi funkcji AirPrint i dostosowywanie okna logowania w celu wyświetlania lub ukrywania przycisków zasilania w usłudze Microsoft Intune. Zapoznaj się również z krokami wymaganymi do pobrania ustawień adresu IP, ścieżki i portu serwera funkcji AirPrint w sieci. Te ustawienia zastosowane w profilu konfiguracji urządzenia umożliwiają skonfigurowanie funkcji urządzeń z systemem macOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/23/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1826498b3bfa2191900d7574f79051af8f758558
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 05/23/2019
ms.locfileid: "66041697"
---
# <a name="macos-device-feature-settings-in-intune"></a>Ustawienia funkcji urządzenia z systemem macOS w usłudze Intune

Ustawienia wbudowane w usługę Intune umożliwiają dostosowanie funkcji na urządzeniach z systemem macOS. Ten artykuł zawiera listę tych ustawień i opisy zadań poszczególnych ustawień. Przedstawiono w nim również listę czynności wymaganych do uzyskania adresu IP, ścieżki i portu drukarek AirPrint przy użyciu aplikacji Terminal (emulatora).

Ta funkcja ma zastosowanie do:

- macOS

Ustawienia te są częścią rozwiązania do zarządzania urządzeniami mobilnymi (MDM) i umożliwiają m.in. tworzenie banera, wybieranie sposobu logowania użytkowników i dodawanie serwera funkcji AirPrint.

Te ustawienia są dodawane do profilu konfiguracji urządzenia w usłudze Intune, a następnie przypisywane lub wdrażane na urządzeniach z systemem macOS.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia sieci macOS](device-features-configure.md).

## <a name="airprint"></a>Funkcja AirPrint

- **Adres IP**: podaj adres IPv4 lub IPv6 drukarki. Jeśli do identyfikowania drukarek używasz nazw hostów, możesz uzyskać adres IP, wysyłając polecenie ping do drukarki w aplikacji Terminal. Dalsze szczegółowe informacje można znaleźć w sekcji [Uzyskiwanie adresu IP i ścieżki](#get-the-ip-address-and-path) (w tym artykule).
- **Ścieżka**: wprowadź ścieżkę drukarki. W przypadku drukarek w sieci ścieżka to zazwyczaj `ipp/print`. Dalsze szczegółowe informacje można znaleźć w sekcji [Uzyskiwanie adresu IP i ścieżki](#get-the-ip-address-and-path) (w tym artykule).
- **Port** (system iOS 11.0 i nowsze): podaj port nasłuchiwania miejsca docelowego funkcji AirPrint. Jeśli ta właściwość pozostanie pusta, funkcja AirPrint będzie używać portu domyślnego.
- **TLS** (system iOS 11.0 i nowsze): wybierz pozycję **Włącz**, aby zabezpieczyć połączenia funkcji AirPrint przy użyciu protokołu Transport Layer Security (TLS).

**Dodaj** serwer funkcji AirPrint. Można dodać wiele serwerów z funkcją AirPrint.

- **Importuj** (opcjonalnie): można również **zaimportować** plik rozdzielany przecinkami (CSV) zawierający listę drukarek z funkcją AirPrint. Po dodaniu drukarek z funkcją AirPrint w usłudze Intune można również **wyeksportować** tę listę.

Wybierz przycisk **OK**, aby zapisać ustawienia.

### <a name="get-the-ip-address-and-path"></a>Uzyskiwanie adresu IP i ścieżki

Aby dodać serwery funkcji AirPrinter, potrzebujesz adresu IP drukarki, ścieżki zasobu i portu. Poniższe kroki przedstawiają sposób uzyskiwania tych informacji.

1. Na komputerze Mac podłączonym do tej samej sieci lokalnej (podsieci) co drukarki AirPrint otwórz **Terminal** (z folderu **/Applications/Utilities**).
2. W aplikacji Terminal wpisz `ippfind`, a następnie wybierz klawisz Enter.

    Zanotuj informacje o drukarce. Zwrócone informacje mogą wyglądać podobnie do następujących: `ipp://myprinter.local.:631/ipp/port1`. Pierwsza część to nazwa drukarki. Ostatnia część (`ipp/port1`) to ścieżka zasobu.

3. W terminalu wpisz `ping myprinter.local`, a następnie wybierz klawisz Enter.

   Zanotuj adres IP. Zwrócone informacje mogą wyglądać podobnie do następujących: `PING myprinter.local (10.50.25.21)`.

4. Użyj wartości adresu IP i ścieżki zasobu. W tym przykładzie adres IP to `10.50.25.21`, a ścieżka zasobu to `/ipp/port1`.

## <a name="login-window"></a>Okno logowania

### <a name="window-layout"></a>Układ okna

- **Pokaż dodatkowe informacje na pasku menu**: jeśli obszar czasu na pasku menu jest zaznaczony, wybranie opcji **Zezwalaj** powoduje wyświetlenie nazwy hosta i wersji systemu macOS. W przypadku wybrania opcji **Nie skonfigurowano** (ustawienie domyślne) informacje te nie są wyświetlane na pasku menu.
- **Baner**: wprowadź komunikat, który ma być wyświetlany na ekranie logowania urządzenia. Na przykład możesz wprowadzić komunikat powitalny, informacje o swojej organizacji lub informacje o rzeczach zgubionych i znalezionych.
- **Wybierz format logowania**: wybierz sposób logowania się użytkowników do urządzenia. Dostępne opcje:
  - **Monituj o nazwę użytkownika i hasło** (ustawienie domyślne): użytkownik musi wprowadzić nazwę użytkownika i hasło.
  - **Wyświetl listę wszystkich użytkowników i monituj o podanie hasła**: użytkownik musi wybrać swoją nazwę użytkownika z listy, a następnie wprowadzić hasło. Należy również skonfigurować poniższe ustawienia:

    - **Użytkownicy lokalni**: w przypadku wybrania opcji **Ukryj** konta użytkowników lokalnych, np. konto standardowe i konto administratora, nie są wyświetlane na liście użytkowników. Widoczne są tylko konta sieciowe i konta użytkowników systemu. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) powoduje wyświetlenie kont użytkowników lokalnych na liście użytkowników.
    - **Konta mobilne**: w przypadku wybrania opcji **Ukryj** konta mobilne nie są wyświetlane na liście użytkowników. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) powoduje wyświetlenie kont mobilnych na liście użytkowników. Niektóre konta mobilne mogą być widoczne jako użytkownicy sieciowi.
    - **Użytkownicy sieciowi**: wybranie opcji **Pokaż** powoduje wyświetlenie nazw użytkowników sieciowych na liście użytkowników. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) powoduje, że konta użytkowników sieciowych nie są wyświetlane.
    - **Administratorzy**: wybranie opcji **Ukryj** powoduje, że konta administratorów nie są wyświetlane na liście użytkowników. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) powoduje wyświetlenie kont administratorów na liście użytkowników.
    - **Inni użytkownicy**: wybranie opcji **Pokaż** powoduje wyświetlenie nazw użytkowników z kategorii **Inni...** na liście użytkowników. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) powoduje, że konta innych użytkowników nie są wyświetlane.

### <a name="login-screen-power-settings"></a>Ustawienia zasilania ekranu logowania

- **Przycisk Wyłącz**: wybranie opcji **Ukryj** powoduje ukrycie przycisku wyłączania na ekranie logowania. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) powoduje wyświetlenie przycisku wyłączania.
- **Przycisk Uruchom ponownie**: wybranie opcji **Ukryj** powoduje ukrycie przycisku ponownego uruchamiania na ekranie logowania. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) powoduje wyświetlenie przycisku ponownego uruchamiania.
- **Przycisk Uśpij**: wybranie opcji **Ukryj** powoduje ukrycie przycisku usypiania na ekranie logowania. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) powoduje wyświetlenie przycisku usypiania.

### <a name="other"></a>Inne

- **Wyłącz logowanie użytkownika z konsoli**: wybranie opcji **Wyłącz** powoduje ukrycie wiersza polecenia systemu macOS używanego do logowania. W przypadku typowych użytkowników należy wybrać opcję **Wyłącz**. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) umożliwia zaawansowanym użytkownikom zalogowanie się przy użyciu wiersza polecenia systemu macOS. Aby przejść do trybu konsoli, użytkownicy muszą wprowadzić ciąg `>console` w polu Nazwa użytkownika, a następnie uwierzytelnić się w oknie konsoli.

### <a name="apple-menu"></a>Menu Apple

Za pomocą następujących ustawień można konfigurować zakres czynności dostępnych dla użytkowników zalogowanych do swoich urządzeń.

- **Wyłącz polecenie Wyłącz**: wybranie opcji **Wyłącz** uniemożliwia zalogowanym użytkownikom wybranie opcji **Zamknij**. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) pozwala użytkownikom wybierać polecenie **Zamknij** w menu na urządzeniu.
- **Wyłącz polecenie Uruchom ponownie**: wybranie opcji **Wyłącz** uniemożliwia zalogowanym użytkownikom wybranie opcji **Uruchom ponownie**. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) pozwala użytkownikom wybierać polecenie **Uruchom ponownie** w menu na urządzeniu.
- **Wyłącz polecenie Wyłącz zasilanie**: wybranie opcji **Wyłącz** uniemożliwia zalogowanym użytkownikom wybranie opcji **Wyłącz zasilanie**. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) pozwala użytkownikom wybierać polecenie **Wyłącz zasilanie** w menu na urządzeniu.
- **Wyłącz polecenie Wyloguj** (system macOS 10.13 i nowsze): wybranie opcji **Wyłącz** uniemożliwia zalogowanym użytkownikom wybranie opcji **Wyloguj**. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) pozwala użytkownikom wybierać polecenie **Wyloguj** w menu na urządzeniu.
- **Wyłącz pozycję Zablokuj ekran** (system macOS 10.13 i nowsze): wybranie opcji **Wyłącz** uniemożliwia zalogowanym użytkownikom wybranie opcji **Zablokuj ekran**. Wybranie opcji **Nie skonfigurowano** (ustawienie domyślne) pozwala użytkownikom wybierać polecenie **Zablokuj ekran** w menu na urządzeniu.

Wybierz przycisk **OK**, aby zapisać ustawienia.

## <a name="next-steps"></a>Następne kroki

- Wyświetl wszystkie ustawienia urządzeń z systemem [iOS](ios-device-features-settings.md).
- [Przypisz ten profil](device-profile-assign.md) do swoich grup i [monitoruj jego stan](device-profile-monitor.md).
