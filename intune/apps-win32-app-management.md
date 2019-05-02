---
title: Dodawanie i przypisywanie aplikacji Win32 do usługi Microsoft Intune
titleSuffix: ''
description: Dowiedz się, jak dodawać i przypisywać aplikacje Win32 oraz zarządzać nimi w usłudze Microsoft Intune. Ten temat zawiera omówienie możliwości dostarczania aplikacji Win32 i zarządzania nimi w usłudze Intune, a także informacje dotyczące rozwiązywania problemów z aplikacjami Win32.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/15/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: efdc196b-38f3-4678-ae16-cdec4303f8d2
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8c2cac99ba45ccd91629e6db32d91735d90d706e
ms.sourcegitcommit: 6d6f43d69462f7f8fadc421c4ba566dc6ec20c36
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62426157"
---
# <a name="intune-standalone---win32-app-management"></a>Autonomiczna usługa Intune — zarządzanie aplikacjami Win32

[Autonomiczna usługa Intune](mdm-authority-set.md) daje teraz większe możliwości zarządzania aplikacjami Win32. O ile klienci połączeni z chmurą mogą zarządzać aplikacjami Win32 za pomocą programu Configuration Manager, klienci korzystający tylko z usługi Intune będą mieć większe możliwości zarządzania aplikacjami biznesowymi Win32. Ten temat zawiera omówienie funkcji zarządzania aplikacjami Win32 w usłudze Intune i informacje dotyczące rozwiązywania problemów.

> [!NOTE]
> Ta możliwość zarządzania aplikacjami obsługuje 32-bitowe i 64-bitowe architektury systemów operacyjnych dla aplikacji systemu Windows.

## <a name="prerequisites"></a>Wymagania wstępne

Aby skorzystać z funkcji zarządzania aplikacjami Win32, upewnij się, że spełnione są następujące kryteria:

- System Windows 10 w wersji 1607 lub nowszej (wersje Enterprise, Pro i Education)
- Klient z systemem Windows 10 musi być: 
    - Urządzenia muszą zostać dołączone do usługi Azure AD i automatycznie zarejestrowane. Rozszerzenie do zarządzania usługi Intune obsługuje urządzenia dołączone do usługi Azure AD, urządzenia dołączone do domeny hybrydowej oraz urządzenia zarejestrowane w ramach zasad grupowych. 
    > [!NOTE]
    > W przypadku scenariusza rejestrowania w ramach zasad grupowych użytkownik końcowy korzysta z konta użytkownika lokalnego w celu dołączenia do usługi AAD urządzenia z systemem Windows 10. Użytkownik musi zalogować się do urządzenia przy użyciu konta użytkownika usługi AAD i zarejestrować się w usłudze Intune. Usługa Intune zainstaluje rozszerzenie do zarządzania usługi Intune na urządzeniu, jeśli skrypt programu PowerShell lub aplikacja Win32 jest przeznaczona dla użytkownika lub urządzenia.
- Rozmiar aplikacji systemu Windows jest ograniczony do 8 GB na aplikację.

## <a name="prepare-the-win32-app-content-for-upload"></a>Przygotowanie zawartości aplikacji Win32 do przekazania

Użyj narzędzia [Microsoft Win32 Content Prep Tool](https://go.microsoft.com/fwlink/?linkid=2065730), aby przetworzyć wstępnie aplikacje klasyczne systemu Windows (Win32). Narzędzie konwertuje pliki instalacyjne aplikacji do formatu *intunewin*. Narzędzie wykrywa także niektóre atrybuty wymagane przez usługę Intune na potrzeby określenia stanu instalacji aplikacji. Po użyciu tego narzędzia względem folderu instalatora aplikacji będzie można utworzyć aplikację Win32 w konsoli usługi Intune.

> [!IMPORTANT]
> Narzędzie [Microsoft Win32 Content Prep Tool](https://go.microsoft.com/fwlink/?linkid=2065730) pakuje wszystkie pliki i podfoldery do pliku ZIP podczas tworzenia pliku *intunewin*. Pamiętaj, aby narzędzie Microsoft Win32 Content Prep Tool było umieszczone oddzielnie od plików instalatora i folderów, tak aby nie dołączać plików narzędzia lub innych zbędnych plików do pliku *intunewin*.

Narzędzie [Microsoft Win32 Content Prep Tool](https://go.microsoft.com/fwlink/?linkid=2065730) możesz pobrać z witryny GitHub jako plik ZIP. Plik ZIP zawiera folder o nazwie **Microsoft-Win32-Content-Prep-Tool-master**. Folder zawiera narzędzie do przygotowywania, licencję, plik readme i informacje o wersji. 

### <a name="process-flow-to-create-intunewin-file"></a>Przepływ procesu tworzenia pliku intunewin

   ![Przepływ procesu tworzenia pliku intunewin](./media/prepare-win32-app.svg)

### <a name="run-the-microsoft-win32-content-prep-tool"></a>Uruchamianie narzędzia Microsoft Win32 Content Prep Tool

Jeśli uruchamiasz plik `IntuneWinAppUtil.exe` w oknie polecenia bez parametrów, w narzędziu będą wyświetlane informacje krok po kroku dotyczące wprowadzania wymaganych parametrów. Możesz również dodać parametry do polecenia na podstawie znajdujących się poniżej dostępnych parametrów wiersza polecenia.

### <a name="available-command-line-parameters"></a>Dostępne parametry wiersza polecenia 

|    **Parametr wiersza polecenia**    |    **Opis**    |
|:------------------------------:|:----------------------------------------------------------:|
|    `-h`     |    Pomoc    |
|    `-c <setup_folder>`     |    Folder dla wszystkich plików instalacji. Wszystkie pliki w tym folderze zostaną skompresowane do pliku *intunewin*.    |
|   ` -s <setup_file>`     |    Plik instalacji (taki jak *setup.exe* lub *setup.msi*).    |
|    `-o <output_folder>`     |    Folder wyjściowy dla wygenerowanego pliku *intunewin*.    |
|    `-q`       |    Tryb cichy    |

### <a name="example-commands"></a>Przykładowe polecenia

|    **Przykładowe polecenie**    |    **Opis**    |
|:-----------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|    `IntuneWinAppUtil -h`    |    To polecenie wyświetla informacje o użyciu narzędzia.    |
|    `IntuneWinAppUtil -c c:\testapp\v1.0 -s c:\testapp\v1.0\setup.exe -o c:\testappoutput\v1.0 -q`    |    To polecenie umożliwia wygenerowanie pliku `.intunewin` z określonego folderu źródłowego i pliku instalacji. W przypadku pliku instalacji MSI to narzędzie pobierze informacje wymagane dla usługi Intune. Jeśli określono parametr `-q`, polecenie zostanie uruchomione w trybie cichym, a jeśli plik wyjściowy już istnieje, to zostanie zastąpiony. Ponadto jeśli folder wyjściowy nie istnieje, to zostanie automatycznie utworzony.    |

Podczas generowania pliku *intunewin* wszystkie pliki, które będą przywoływane, należy umieścić w podfolderze lub w folderze instalacyjnym. Następnie należy użyć ścieżki względnej, aby odwołać się do określonego pliku, którego potrzebujesz. Przykład:

**Źródłowy folder instalacji:** *c:\testapp\v1.0*<br>
**Plik licencji:** *c:\testapp\v1.0\licenses\license.txt*

Odwołaj się do pliku *license.txt* przy użyciu ścieżki względnej *licenses\license.txt*.

## <a name="create-assign-and-monitor-a-win32-app"></a>Tworzenie, przypisywanie i monitorowanie aplikacji Win32

Podobnie jak w przypadku aplikacji biznesowych, możesz dodać aplikację Win32 do usługi Microsoft Intune. Aplikacje tego typu są zwykle pisane we własnym zakresie lub przez inną firmę. 

### <a name="process-flow-to-add-a-win32-app-to-intune"></a>Przepływ procesu dodawania aplikacji Win32 do usługi Intune

   ![Przepływ procesu dodawania aplikacji Win32 do usługi Intune](./media/add-win32-app.svg)

### <a name="add-a-win32-app-to-intune"></a>Dodawanie aplikacji Win32 do usługi Intune

W poniższych krokach przedstawiono wskazówki ułatwiające dodanie aplikacji systemu Windows do usługi Microsoft Intune.

### <a name="step-1-specify-the-software-setup-file"></a>Krok 1. Określanie pliku konfiguracji oprogramowania

1.  Zaloguj się do [portalu Azure](https://portal.azure.com/).
2.  Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3.  W okienku **Intune** wybierz pozycję **Aplikacje klienckie** > **Aplikacje** > **Dodaj**.
4.  W okienku aplikacji **Dodawanie** wybierz z listy rozwijanej pozycję **Aplikacja systemu Windows (Win32)**.

    ![Zrzut ekranu przedstawiający blok dodawania aplikacji — pole listy rozwijanej dodawania typu](./media/apps-win32-app-01.png)

### <a name="step-2-upload-the-app-package-file"></a>Krok 2: Przekazywanie pliku pakietu aplikacji

1.  W okienku **Dodawanie aplikacji** wybierz pozycję **Dodaj plik pakietu**, aby wybrać plik. Zostanie wyświetlone okienko Plik pakietu aplikacji.

    ![Zrzut ekranu przedstawiający blok pliku pakietu aplikacji](./media/apps-win32-app-02.png)

2.  W okienku **Plik pakietu aplikacji** wybierz przycisk przeglądania. Następnie wybierz plik instalacyjny systemu Windows z rozszerzeniem *intunewin*.

    > [!IMPORTANT]
    > Upewnij się, że używasz najnowszej wersji narzędzia Microsoft Win32 Content Prep Tool. Jeśli nie użyjesz najnowszej wersji, zostanie wyświetlone ostrzeżenie z informacją, że aplikacja została spakowana przy użyciu starszej wersji narzędzia Microsoft Win32 Content Prep Tool. 

3.  Po zakończeniu wybierz przycisk **OK**.

### <a name="step-3-configure-app-information"></a>Krok 3: Konfigurowanie informacji o aplikacji

1.  Aby skonfigurować aplikację, w okienku **Dodaj aplikację** wybierz pozycję **Informacje o aplikacji**.
2.  W okienku **Informacje o aplikacji** skonfiguruj następujące informacje. Niektóre wartości w tym okienku mogą zostać wypełnione automatycznie.
    - **Nazwa**: wprowadź nazwę aplikacji wyświetlaną w portalu firmy. Jeśli dana nazwa aplikacji występuje dwa razy, obie aplikacje będą wyświetlane w portalu firmy.
    - **Opis**: Wprowadź opis aplikacji. Opis będzie widoczny w portalu firmy.
    - **Wydawca**: Wprowadź nazwę wydawcy aplikacji.
    - **Kategoria**: wybierz co najmniej jedną kategorię aplikacji — wbudowaną lub utworzoną samodzielnie. Kategorie ułatwiają użytkownikom znajdowanie aplikacji podczas przeglądania portalu firmy.
    - **Wyświetl jako polecaną aplikację w Portalu firmy**: Wyróżnij aplikację na stronie głównej Portalu firmy dla użytkowników przeglądających aplikacje.
    - **Adres URL informacji**: opcjonalnie wprowadź adres URL witryny internetowej zawierającej informacje o aplikacji. Adres URL będzie widoczny w portalu firmy.
    - **Adres URL zasad ochrony prywatności**: opcjonalnie wprowadź adres URL witryny internetowej zawierającej informacje dotyczące zasad ochrony prywatności w aplikacji. Adres URL będzie widoczny w portalu firmy.
    - **Deweloper**: opcjonalnie wprowadź nazwę dewelopera aplikacji.
    - **Właściciel**: opcjonalnie wprowadź nazwę właściciela aplikacji. Przykładem może być **Dział kadr**.
    - **Uwagi**: wprowadź wszelkie uwagi, które chcesz skojarzyć z tą aplikacją.
    - **Logo**: przekaż ikonę skojarzoną z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania portalu firmy.
3.  Po zakończeniu wybierz przycisk **OK**.

### <a name="step-4-configure-app-installation-details"></a>Krok 4. Konfigurowanie szczegółów instalacji aplikacji
1.  W okienku **Dodawanie aplikacji** wybierz pozycję **Program**, aby skonfigurować polecenia instalacji i usuwania aplikacji.
2.  Dodaj pełny wiersz polecenia instalacji, który umożliwia zainstalowanie aplikacji. 

    Na przykład jeśli nazwa pliku aplikacji to **MyApp123**, dodaj następujące polecenie:<br>
    `msiexec /p “MyApp123.msp”`<p>
    Jeśli dodatkowo aplikacja to `ApplicationName.exe`, polecenie będzie nazwą aplikacji z następującymi po niej argumentami polecenia (przełącznikami) obsługiwanymi przez pakiet. <br>Przykład:<br>
    `ApplicationName.exe /quite`<br>
    W powyższym poleceniu pakiet `ApplicaitonName.exe` obsługuje argument polecenia `/quite`.<p> Aby uzyskać konkretne argumenty obsługiwane przez pakiet aplikacji, skontaktuj się z dostawcą aplikacji.

3.  Dodaj pełny wiersz polecenia dezinstalacji, który umożliwia odinstalowanie aplikacji na podstawie identyfikatora GUID aplikacji. 

    Na przykład: `msiexec /x “{12345A67-89B0-1234-5678-000001000000}”`

    > [!NOTE]
    > Możesz skonfigurować aplikację Win32, aby została zainstalowana w kontekście **Użytkownik** lub **System**. Kontekst **Użytkownik** odwołuje się tylko do danego użytkownika. Kontekst **System** odwołuje się do wszystkich użytkowników urządzenia z systemem Windows 10.
    >
    > Użytkownicy końcowi nie muszą być zalogowani na urządzeniu, aby instalować aplikacje Win32.

4.  Po zakończeniu wybierz przycisk **OK**.

### <a name="step-5-configure-app-requirements"></a>Krok 5. Konfigurowanie wymagań aplikacji

1.  W okienku **Dodawanie aplikacji** wybierz pozycję **Wymagania**, aby skonfigurować wymagania, które urządzenia muszą spełniać, aby można było zainstalować aplikację.
2.  W okienku **Dodawanie reguły wymagania** skonfiguruj następujące informacje. Niektóre wartości w tym okienku mogą zostać wypełnione automatycznie.
    - **Architektura systemu operacyjnego**: wybierz architekturę wymaganą do zainstalowania aplikacji.
    - **Minimalna wersja systemu operacyjnego**: wybierz minimalną wersję systemu operacyjnego wymaganą do zainstalowania aplikacji.
    - **Wymagane miejsce na dysku (MB)**: opcjonalnie określ ilość wolnego miejsca na dysku systemowym wymaganego do zainstalowania aplikacji.
    - **Wymagana pamięć fizyczna (MB)**: opcjonalnie określ ilość pamięci fizycznej (RAM) wymaganej do zainstalowania aplikacji.
    - **Wymagana minimalna liczba procesorów logicznych**: opcjonalnie określ minimalną liczbę procesorów logicznych wymaganą do zainstalowania aplikacji.
    - **Wymagana minimalna szybkość procesora (MHz)**: opcjonalnie określ minimalną szybkość procesora wymaganą do zainstalowania aplikacji.

3. Kliknij pozycję **Dodaj**, aby wyświetlić blok **Dodawanie reguły wymagania** i skonfigurować dodatkowe reguły wymagań. Wybierz pozycję **Typ wymagania**, aby wybrać typ reguły, który będzie używany do określenia sposobu weryfikacji wymagania. Reguły wymagań mogą opierać się na informacji o systemie plików, wartościach rejestru lub skryptach programu PowerShell. 
    - **Plik**: Po wybraniu **pliku** jako **typu wymagania** reguła wymagania musi wykryć plik lub folder, datę, wersję lub rozmiar. 
        - **Ścieżka** — pełna ścieżka folderu zawierającego plik lub folder do wykrycia.
        - **Plik lub folder** — plik lub folder do wykrycia.
        - **Właściwość** — wybierz typ reguły używanej do weryfikowania obecności aplikacji.
        - **Skojarzone z aplikacją 32-bitową na klientach 64-bitowych** — wybierz opcję **Tak**, aby rozwijać wszystkie zmienne środowiskowe ścieżki w kontekście 32-bitowym na klientach 64-bitowych. Wybierz opcję **Nie** (domyślną), aby rozwijać wszystkie zmienne ścieżki w kontekście 64-bitowym na klientach 64-bitowych. Klienci 32-bitowi będą zawsze używać kontekstu 32-bitowego.
    - **Rejestr**: Po wybraniu **rejestru** jako **typu wymagania** reguła wymagania musi wykryć ustawienie rejestru na podstawie wartości, ciągu, liczby całkowitej lub wersji.
        - **Ścieżka klucza** — pełna ścieżka wpisu rejestru zawierającego wartość do wykrycia.
        - **Nazwa wartości** — nazwa wartości rejestru do wykrycia. Jeśli ta wartość jest pusta, wykrywanie będzie wykonywane za pomocą klucza. (Domyślna) wartość klucza będzie służyć jako wartość wykrywania, jeśli metoda wykrywania jest inna niż obecność pliku lub folderu.
        - **Wymaganie klucza rejestru** — wybierz typ porównania klucza rejestru używany do określenia sposobu weryfikacji reguły wymagania.
        - **Skojarzone z aplikacją 32-bitową na klientach 64-bitowych** — wybierz opcję **Tak**, aby przeszukiwać rejestr 32-bitowy na klientach 64-bitowych. Wybierz opcję **Nie** (domyślną), aby przeszukiwać rejestr 64-bitowy na klientach 64-bitowych. Klienci 32-bitowi zawsze przeszukują 32-bitowy rejestr.
    - **Skrypt**: Wybierz **skrypt** jako **typ wymagania**, gdy nie możesz utworzyć reguły wymagania na podstawie pliku, rejestru lub jakiejkolwiek innej metody dostępnej w konsoli usługi Intune.
        - **Plik skryptu** — jeśli w przypadku reguły wymagania opartej na skrypcie programu PowerShell kod zakończenia to 0, strumień STDOUT zostanie wykryty z bardziej szczegółowymi informacjami. Na przykład możemy wykryć strumień STDOUT jako liczbę całkowitą o wartości 1.
        - **Uruchom skrypt jako proces 32-bitowy na klientach 64-bitowych**: wybierz pozycję **Tak**, aby uruchamiać skrypt w procesie 32-bitowym na klientach 64-bitowych. Wybierz pozycję **Nie** (ustawienie domyślne), aby uruchamiać skrypt w procesie 64-bitowym na klientach 64-bitowych. Klienci 32-bitowi uruchamiają skrypt w procesie 32-bitowym.
        - **Uruchom ten skrypt, korzystając z poświadczeń użytych do logowania**: Wybierz pozycję **Tak**, aby uruchomić skrypt przy użyciu poświadczeń zalogowanego urządzenia**.
        - **Wymuszaj sprawdzanie podpisu skryptu** — wybierz opcję **Tak**, aby zweryfikować, że skrypt jest podpisany przez zaufanego wydawcę, co umożliwi uruchamianie skryptu bez wyświetlania ostrzeżeń ani monitów. Skrypt będzie uruchamiany bez blokowania. Wybierz opcję **Nie** (domyślną), aby uruchamiać skrypt z potwierdzeniem przez użytkownika końcowego i bez weryfikacji podpisu.
        - **Wybierz typ danych wyjściowych**: Wybierz typ danych używany podczas określania dopasowania reguły wymagania.
4.  Po zakończeniu wybierz przycisk **OK**.

### <a name="step-6-configure-app-detection-rules"></a>Krok 6. Konfigurowanie reguł wykrywania aplikacji

1.  W okienku **Dodawanie aplikacji** wybierz pozycję **Reguły wykrywania**, aby skonfigurować reguły wykrywania obecności aplikacji.
2.  W polu **Format reguł** wybierz sposób wykrywania obecności aplikacji. Reguły wykrywania obecności aplikacji możesz skonfigurować ręcznie lub przy użyciu niestandardowego skryptu. Musisz wybrać co najmniej jedną regułę wykrywania. 

    > [!NOTE]
    > W okienku **Reguły wykrywania** możesz dodać wiele reguł. Wykrycie aplikacji wymaga spełnienia **wszystkich** reguł.

    - **Ręcznie skonfiguruj reguły wykrywania** — możesz wybrać jeden z następujących typów reguły:
        1.  **MSI** — weryfikacja oparta na sprawdzeniu wersji pliku MSI. Tę opcję można dodać tylko raz. Po wybraniu reguły tego typu są dostępne dwa ustawienia:
            - **Kod produktu MSI** — dodaj prawidłowy kod produktu MSI dla aplikacji.
            - **Sprawdzenie wersji produktu MSI** — wybierz opcję **Tak**, aby zweryfikować wersję produktu MSI w dodatku do kodu produktu MSI.
        2.  **Plik** — weryfikacja oparta na wykryciu pliku lub folderu, dacie, wersji lub rozmiarze.
            - **Ścieżka** — pełna ścieżka folderu zawierającego plik lub folder do wykrycia.
            - **Plik lub folder** — plik lub folder do wykrycia.
            - **Metoda wykrywania** — wybierz typ metody wykrywania używanej do weryfikowania obecności aplikacji.
            - **Skojarzone z aplikacją 32-bitową na klientach 64-bitowych** — wybierz opcję **Tak**, aby rozwijać wszystkie zmienne środowiskowe ścieżki w kontekście 32-bitowym na klientach 64-bitowych. Wybierz opcję **Nie** (domyślną), aby rozwijać wszystkie zmienne ścieżki w kontekście 64-bitowym na klientach 64-bitowych. Klienci 32-bitowi będą zawsze używać kontekstu 32-bitowego.
            
            **Przykłady wykrywania opartego na plikach**
            1.  Sprawdzenie obecności pliku.
         
                ![Zrzut ekranu okienka Reguła wykrywania — obecność pliku](./media/apps-win32-app-03.png)
        
            2.  Sprawdzenie obecności folderu.
         
                ![Zrzut ekranu okienka Reguła wykrywania — obecność folderu](./media/apps-win32-app-04.png)
        
        3. **Rejestr** — weryfikacja na podstawie wartości, ciągu, liczby całkowitej lub wersji.
            - **Ścieżka klucza** — pełna ścieżka wpisu rejestru zawierającego wartość do wykrycia.
            - **Nazwa wartości** — nazwa wartości rejestru do wykrycia. Jeśli ta wartość jest pusta, wykrywanie będzie wykonywane za pomocą klucza. (Domyślna) wartość klucza będzie służyć jako wartość wykrywania, jeśli metoda wykrywania jest inna niż obecność pliku lub folderu.
            - **Metoda wykrywania** — wybierz typ metody wykrywania używanej do weryfikowania obecności aplikacji.
            - **Skojarzone z aplikacją 32-bitową na klientach 64-bitowych** — wybierz opcję **Tak**, aby przeszukiwać rejestr 32-bitowy na klientach 64-bitowych. Wybierz opcję **Nie** (domyślną), aby przeszukiwać rejestr 64-bitowy na klientach 64-bitowych. Klienci 32-bitowi zawsze przeszukują 32-bitowy rejestr.
            
            **Przykłady wykrywania opartego na rejestrze**
            1.  Sprawdzenie obecności klucza rejestru.
            
                ![Zrzut ekranu okienka Reguła wykrywania — obecność klucza rejestru](./media/apps-win32-app-05.png)    
            
            2.  Sprawdź, czy wartość rejestru istnieje.
        
                ![Zrzut okienka Reguła wykrywania — obecność wartości rejestru](./media/apps-win32-app-06.png)    
        
            3.  Sprawdzenie równości dla ciągu wartości rejestru.
        
                ![Zrzut okienka Reguła wykrywania — równość ciągu wartości rejestru](./media/apps-win32-app-07.png)    
     
    - **Użyj niestandardowego skryptu wykrywania** — określ skrypt programu PowerShell, który będzie używany do wykrywania aplikacji. 
    
        1.  **Plik skryptu** — wybierz skrypt programu PowerShell, który wykryje obecność aplikacji na kliencie. Aplikacja zostanie wykryta, gdy skrypt zwróci wartość 0 jako kod zakończenia i zapisze wartość ciągu do strumienia STDOUT.

        2.  **Uruchom skrypt jako proces 32-bitowy na klientach 64-bitowych**: wybierz pozycję **Tak**, aby uruchamiać skrypt w procesie 32-bitowym na klientach 64-bitowych. Wybierz pozycję **Nie** (ustawienie domyślne), aby uruchamiać skrypt w procesie 64-bitowym na klientach 64-bitowych. Klienci 32-bitowi uruchamiają skrypt w procesie 32-bitowym.

        3.  **Wymuszaj sprawdzanie podpisu skryptu** — wybierz opcję **Tak**, aby zweryfikować, że skrypt jest podpisany przez zaufanego wydawcę, co umożliwi uruchamianie skryptu bez wyświetlania ostrzeżeń ani monitów. Skrypt będzie uruchamiany bez blokowania. Wybierz opcję **Nie** (domyślną), aby uruchamiać skrypt z potwierdzeniem przez użytkownika końcowego i bez weryfikacji podpisu.
    
            Agent usługi Intune sprawdza wyniki ze skryptu. Odczytuje wartości zapisane przez skrypt do strumienia wyjścia standardowego (STDOUT) i standardowego strumienia błędów (STDERR) oraz kod zakończenia. Jeśli skrypt zwróci wartość różną od zera, jego wykonanie zakończy się niepowodzeniem, a stan wykrywania aplikacji będzie wskazywać, że nie jest zainstalowana. Jeśli kod zakończenia ma wartość zero, a strumień STDOUT zawiera dane, stan wykrywania aplikacji to Zainstalowano. 

            > [!NOTE]
            > Jeśli kod zakończenia skryptu to 0, oznacza to pomyślne wykonanie skryptu. Drugi kanał wyjściowy wskazuje wykrycie aplikacji — dane w strumieniu STDOUT oznaczają, że aplikacja została wykryta na kliencie. Nie szukamy konkretnego ciągu w strumieniu STDOUT.

        4.  Po dodaniu reguł wybierz polecenie **Dodaj** > **OK**.

### <a name="step-7-configure-app-return-codes"></a>Krok 7. Konfigurowanie kodów powrotnych aplikacji

1.  W okienku **Dodawanie aplikacji** wybierz pozycję **Kody powrotne**, aby dodać kody powrotne używane do określenia zachowania ponowienia instalacji aplikacji lub zachowania po instalacji. Pozycje kodów powrotnych są dodawane domyślnie podczas tworzenia aplikacji. Istnieje jednak możliwość dodania kolejnych kodów powrotnych lub zmiany istniejących kodów powrotnych. 
2.  W okienku **Kody powrotne** dodaj kolejne kody powrotne lub zmodyfikuj istniejące kody powrotne.
    - **Niepowodzenie** — wartość zwracana, która wskazuje błąd instalacji aplikacji.
    - **Ponowny rozruch sprzętowy** — kod powrotny ponownego uruchomienia sprzętowego nie zezwala na zainstalowanie następnej aplikacji Win32 na kliencie bez ponownego uruchomienia. 
    - **Ponowny rozruch systemowy** — kod powrotny ponownego uruchomienia systemowego umożliwia zainstalowanie następnej aplikacji Win32 bez ponownego uruchomienia klienta. Ponowne uruchomienie jest niezbędne do ukończenia instalacji bieżącej aplikacji.
    - **Ponów** — w przypadku kodu powrotnego ponowienia agent spróbuje zainstalować aplikację trzy razy. Między próbami agent będzie czekać 5 minut. 
    - **Powodzenie** — wartość zwracana, która wskazuje pomyślne zainstalowanie aplikacji.
3.  Wybierz pozycję **OK** po dodaniu lub zmodyfikowaniu listy kodów powrotnych.

### <a name="step-8-add-the-app"></a>Krok 8. Dodawanie aplikacji

1.  W okienku **Dodaj aplikację** sprawdź poprawność skonfigurowanych informacji.
2.  Wybierz pozycję **Dodaj**, aby przekazać aplikację do usługi Intune.

### <a name="step-9-assign-the-app"></a>Krok 9. Przypisywanie aplikacji

1.  W okienku aplikacji wybierz pozycję **Przypisania**.
2.  Wybierz pozycję **Dodaj grupę**, aby otworzyć okienko **Dodawanie grupy** powiązane z aplikacją.
3.  Dla określonej aplikacji wybierz **typ przypisania**:
    - **Dostępne dla zarejestrowanych urządzeń**: użytkownicy instalują aplikację z aplikacji Portal firmy lub witryny internetowej Portal firmy.
    - **Wymagane**: aplikacja jest instalowana na urządzeniach w wybranych grupach.
    - **Odinstalowywanie**: aplikacja jest odinstalowywana z urządzeń w wybranych grupach.
4.  Wybierz pozycję **Objęte grupy** i przypisz grupy, które będą używać aplikacji.
5.  W okienku **Przypisywanie** wybierz przycisk **OK**, aby ukończyć wybieranie uwzględnionych grup.
6.  Jeśli chcesz wykluczyć wszystkie grupy użytkowników z objęcia wpływem tego przypisania aplikacji, wybierz pozycję **Wykluczenie grup**.
7.  W okienku **Dodawanie grupy** wybierz przycisk **OK**.
8.  W okienku **Przypisania** aplikacji wybierz pozycję **Zapisz**.

W tym momencie wykonywanie kroków dodawania aplikacji Win32 do usługi Intune zostało zakończone. Aby uzyskać informacje dotyczące przypisywania i monitorowania aplikacji, zobacz [Przypisywanie aplikacji do grup w usłudze Microsoft Intune](https://docs.microsoft.com/intune/apps-deploy) i [Monitorowanie informacji o aplikacji i przypisań z użyciem usługi Microsoft Intune](https://docs.microsoft.com/intune/apps-monitor).

## <a name="app-dependencies"></a>Zależności aplikacji

Zależności aplikacji to aplikacje, które należy zainstalować przed zainstalowaniem aplikacji Win32. Możesz wymagać, aby inne aplikacje były instalowane jako zależności. W szczególności na urządzeniu muszą zostać zainstalowane aplikacje zależne przed zainstalowaniem aplikacji Win32. Maksymalnie można użyć 100 zależności, co obejmuje zależności wszystkich dołączonych zależności, a także samą aplikację. Zależności aplikacji Win32 możesz dodać tylko po dodaniu i przekazaniu aplikacji Win32 do usługi Intune. Po dodaniu aplikacji Win32 zostanie wyświetlona opcja **Zależności** w bloku aplikacji Win32. 

> [!NOTE]
> Funkcja zależności aplikacji będzie dostępna dopiero wtedy, gdy agent zarządzania usługi Intune zostanie uaktualniony do wersji 1904 (nowszej niż 1.18.120.0), co może nastąpić tydzień lub dwa tygodnie po uaktualnieniu usługi do wersji 1904.

Podczas dodawania zależności aplikacji możesz przeprowadzić wyszukiwanie na podstawie nazwy aplikacji i wydawcy. Ponadto możesz sortować dodane zależności na podstawie nazwy aplikacji i wydawcy. Wcześniej dodanych zależności aplikacji nie można wybrać na liście dodanych zależności aplikacji. 

Możesz wybrać, czy poszczególne aplikacje zależne mają być instalowane automatycznie. Domyślnie opcja **Instaluj automatycznie** jest ustawiona na wartość **Tak** dla każdej zależności. W przypadku automatycznego instalowania aplikacji zależnej, nawet jeśli nie jest przeznaczona dla użytkownika lub urządzenia, usługa Intune zainstaluje tę aplikację na urządzeniu w celu spełnienia zależności przed zainstalowaniem aplikacji Win32. Ważne jest, aby pamiętać, że dla danej zależności mogą istnieć cykliczne zależności podrzędne, z których każda zostanie zainstalowana przed zainstalowaniem zależności głównej. Ponadto instalacja zależności nie spełnia polecenia instalacji na danym poziomie zależności.

Aby dodać zależność aplikacji do aplikacji Win32, wykonaj następujące kroki:

1. W usłudze Intune wybierz pozycję **Aplikacje klienckie** > **Aplikacje**, aby wyświetlić listę dodanych aplikacji klienckich. 
2. Wybierz dodaną aplikację **Aplikacja systemu Windows (Win32)**. 
3. Wybierz pozycję **Zależności**, aby dodać aplikacje zależne, które należy zainstalować przed zainstalowaniem aplikacji Win32. 
4. Kliknij pozycję **Dodaj**, aby dodać zależność aplikacji.
5. Po dodaniu aplikacji zależnych kliknij pozycję **Wybierz**.
6. Zdecyduj, czy aplikacje zależne mają być automatycznie instalowane, wybierając pozycję **Tak** lub **Nie** w polu **Instaluj automatycznie**.
7. Kliknij polecenie **Zapisz**.

Użytkownikowi końcowemu zostaną wyświetlone wyskakujące powiadomienia systemu Windows wskazujące, że aplikacje zależne są pobierane i instalowane jako część procesu instalacji aplikacji Win32. Ponadto gdy aplikacja zależna nie jest zainstalowana, użytkownikowi końcowemu będzie często wyświetlane jedno z następujących powiadomień:
- Instalacja co najmniej jednej aplikacji zależnej nie powiodła się
- Wymagania aplikacji dla co najmniej jednej aplikacji zależnej nie zostały spełnione
- Dla co najmniej jednej aplikacji zależnej oczekiwane jest ponowne uruchomienie urządzenia

Jeśli zdecydujesz, że nie ma mieć miejsca **automatyczna instalacja** zależności, próba instalacji aplikacji Win32 nie zostanie podjęta. Ponadto w ramach raportowania aplikacji zostanie wyświetlone, że zależność została oznaczona jako `failed`. Zostanie także podana przyczyna niepowodzenia. Niepowodzenie instalacji zależności można wyświetlić, klikając błąd (lub ostrzeżenie) w [szczegółowych informacjach dotyczących instalacji](troubleshoot-app-install.md#win32-app-installation-troubleshooting) aplikacji Win32. 

Poszczególne zależności będą stosować się do logiki ponawiania aplikacji Win32 usługi Intune (trzykrotna próba instalacji po oczekiwaniu przez pięć minut) i globalnego harmonogramu ponownej oceny. Ponadto zależności mają zastosowanie tylko w momencie instalowania aplikacji Win32 na urządzeniu. Zależności nie mają zastosowania w przypadku odinstalowywania aplikacji Win32. Aby usunąć zależność, należy kliknąć wielokropek (trzy kropki) po lewej stronie aplikacji zależnej znajdujący się na końcu wiersza na liście zależności. 

## <a name="delivery-optimization"></a>Optymalizacja dostarczania

Klienci z systemem Windows 10 w wersji 1709 i nowszej będą pobierać zawartość aplikacji Win32 w usłudze Intune przy użyciu składnika Optymalizacja dostarczania na kliencie z systemem Windows 10. Optymalizacja dostarczania udostępnia funkcję Sieć równorzędna, która jest włączana domyślnie. Optymalizację dostarczania można skonfigurować przy użyciu zasad grupy oraz za pośrednictwem konfiguracji urządzeń w usłudze Intune. Aby uzyskać więcej informacji, zobacz [Delivery Optimization for Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) (Optymalizacja dostarczania w systemie Windows 10). 

## <a name="install-required-and-available-apps-on-devices"></a>Instalowanie wymaganych i dostępnych aplikacji na urządzeniach

Użytkownik końcowy nie będzie widzieć wyskakujących powiadomień systemu Windows dotyczących instalacji wymaganych i dostępnych aplikacji. Na poniższym obrazie przedstawiono przykładowe wyskakujące powiadomienie z informacją o tym, że instalacja aplikacji nie zostanie zakończona do momentu ponownego uruchomienia urządzenia. 

![Zrzut ekranu z wyskakującymi powiadomieniami systemu Windows dla instalacji aplikacji](./media/apps-win32-app-08.png)    

Poniższy obraz przedstawia powiadomienie użytkownika końcowego o wprowadzeniu zmian na urządzeniu.

![Zrzut ekranu powiadamiający użytkownika o tym, że są wprowadzane zmiany aplikacji](./media/apps-win32-app-09.png)    

## <a name="toast-notifications-for-win32-apps"></a>Wyskakujące powiadomienia dla aplikacji Win32 
W razie potrzeby można pominąć wyświetlanie wyskakujących powiadomień dla użytkownika końcowego podczas przypisywania aplikacji. W usłudze Intune wybierz kolejno pozycje **Aplikacje klienckie** > **Aplikacje** > wybierz aplikację > **Przypisania** > **Uwzględnij grupy**. 

> [!NOTE]
> Aplikacje Win32 zainstalowane za pomocą rozszerzenia do zarządzania usługi Intune nie zostaną odinstalowane na wyrejestrowanych urządzeniach. Administratorzy mogą korzystać z wykluczania przypisania, aby nie oferować aplikacji Win32 na urządzeniach BYOD.

## <a name="troubleshoot-win32-app-issues"></a>Rozwiązywanie problemów z aplikacjami Win32
Typowa lokalizacja dzienników agenta na maszynie klienta to `C:\ProgramData\Microsoft\IntuneManagementExtension\Logs`. Do wyświetlenia plików dziennika możesz użyć programu `CMTrace.exe`. Plik *CMTrace.exe* można pobrać ze strony [narzędzi klienta programu Configuration Manager](https://docs.microsoft.com/sccm/core/support/tools). 

![Zrzut ekranu przedstawiający dzienniki klienta na maszynie klienta](./media/apps-win32-app-10.png)    

> [!IMPORTANT]
> Aby umożliwić prawidłową instalację i wykonywanie aplikacji LOB dla systemu Win32, ustawienia ochrony przed złośliwym oprogramowaniem powinny wykluczać następujące katalogi ze skanowania:<p>
> **Na maszynach klienckich z architekturą x64**:<br>
> *C:\Program Files (x86)\Microsoft Intune Management Extension\Content*<br>
> *C:\windows\IMECache*
>  
> **Na maszynach klienckich z architekturą x86**:<br>
> *C:\Program Files\Microsoft Intune Management Extension\Content*<br>
> *C:\windows\IMECache*

Aby uzyskać więcej informacji na temat rozwiązywania problemów z aplikacjami Win32, zobacz [Rozwiązywanie problemów z instalacją aplikacji Win32](troubleshoot-app-install.md#win32-app-installation-troubleshooting).

### <a name="troubleshooting-areas-to-consider"></a>Obszary rozwiązywania problemów do uwzględnienia
- Sprawdź ustawienie celu, aby upewnić się, że agent jest zainstalowany na urządzeniu — aplikacja Win32 przeznaczona dla grupy lub skrypt programu PowerShell przeznaczony dla grupy spowoduje utworzenie zasad instalacji agenta dla grupy zabezpieczeń.
- Sprawdź wersję systemu operacyjnego — system Windows 10 1607 lub nowszy.  
- Sprawdź jednostkę SKU systemu Windows 10 — system Windows 10 S lub system Windows z włączonym trybem S nie obsługują instalacji za pomocą pliku MSI.

## <a name="next-steps"></a>Następne kroki

- Aby uzyskać więcej informacji na temat dodawania aplikacji do usługi Intune, zobacz [Dodawanie aplikacji w usłudze Microsoft Intune](apps-add.md).
