---
title: Dodawanie aplikacji Win32 do usługi Microsoft Intune
titlesuffix: ''
description: Dowiedz się, jak dodawać i dostarczać aplikacje Win32 oraz zarządzać nimi w usłudze Microsoft Intune. Ten temat zawiera omówienie możliwości dostarczania aplikacji Win32 i zarządzania nimi w usłudze Intune, a także informacje dotyczące rozwiązywania problemów z aplikacjami Win32.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/29/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: efdc196b-38f3-4678-ae16-cdec4303f8d2
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: ba77c14e470ed75a87f44adcaf0ba9b98cd06438
ms.sourcegitcommit: e0d55bdda1a818ffe4cfc0ef0592833e22f65a89
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2019
ms.locfileid: "55290761"
---
# <a name="intune-standalone---win32-app-management"></a>Autonomiczna usługa Intune — zarządzanie aplikacjami Win32

Autonomiczna usługa Intune daje większe możliwości zarządzania aplikacjami Win32. O ile klienci połączeni z chmurą mogą zarządzać aplikacjami Win32 za pomocą programu Configuration Manager, klienci korzystający tylko z usługi Intune będą mieć większe możliwości zarządzania aplikacjami biznesowymi Win32. Ten temat zawiera omówienie funkcji zarządzania aplikacjami Win32 w usłudze Intune i informacje dotyczące rozwiązywania problemów.

## <a name="prerequisites"></a>Wymagania wstępne

- System Windows 10 w wersji 1607 lub nowszej (wersje Enterprise, Pro i Education)
- Klient z systemem Windows 10 musi być: 
    - Przyłączony do usługi Azure Active Directory (AAD) lub hybrydowej usługi Azure Active Directory
    - Zarejestrowany w usłudze Intune (zarządzany przez rozwiązanie MDM)
- Rozmiar aplikacji systemu Windows jest ograniczony do 8 GB na aplikację

## <a name="prepare-the-win32-app-content-for-upload"></a>Przygotowanie zawartości aplikacji Win32 do przekazania

Użyj narzędzia [Microsoft Win32 Content Prep Tool](https://go.microsoft.com/fwlink/?linkid=2065730), aby przetworzyć wstępnie aplikacje Win32. Narzędzie konwertuje pliki instalacyjne aplikacji do formatu *intunewin*. Narzędzie wykrywa także niektóre atrybuty wymagane przez usługę Intune na potrzeby określenia stanu instalacji aplikacji. Po użyciu tego narzędzia dla folderu instalatora aplikacji będzie można utworzyć aplikację Win32 w konsoli usługi Intune.

Narzędzie [Microsoft Win32 Content Prep Tool](https://go.microsoft.com/fwlink/?linkid=2065730) możesz pobrać z witryny GitHub.

### <a name="available-command-line-parameters"></a>Dostępne parametry wiersza polecenia 

|    **Parametr wiersza polecenia**    |    **Opis**    |
|:------------------------------:|:----------------------------------------------------------:|
|    `-h`     |    Pomoc    |
|    `-c <setup_folder>`     |    Folder instalacji dla wszystkich plików instalacji.    |
|   ` -s <setup_file>`     |    Plik instalacji (taki jak *setup.exe* lub *setup.msi*).    |
|    `-o <output_folder>`     |    Folder wyjściowy dla wygenerowanego pliku *intunewin*.    |
|    `-q`       |    Tryb cichy    |

### <a name="example-commands"></a>Przykładowe polecenia

|    **Przykładowe polecenie**    |    **Opis**    |
|:-----------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|    `IntuneWinAppUtil -h`    |    To polecenie wyświetla informacje o użyciu narzędzia.    |
|    `IntuneWinAppUtil -c <setup_folder> -s <source_setup_file> -o <output_folder> <-q>`    |    To polecenie umożliwia wygenerowanie pliku `.intunewin` z określonego folderu źródłowego i pliku instalacji. W przypadku pliku instalacji MSI to narzędzie pobierze informacje wymagane dla usługi Intune. Jeśli określono parametr `-q`, polecenie zostanie uruchomione w trybie cichym, a jeśli plik wyjściowy już istnieje, to zostanie zastąpiony. Ponadto jeśli folder wyjściowy nie istnieje, to zostanie automatycznie utworzony.    |

Podczas generowania pliku *intunewin* wszystkie pliki, które będą przywoływane, należy umieścić w podfolderze lub w folderze instalacyjnym. Następnie należy użyć ścieżki względnej, aby odwołać się do określonego pliku, którego potrzebujesz. Przykład:

**Źródłowy folder instalacji:** *c:\testapp\v1.0*<br>
**Plik licencji:** *c:\testapp\v1.0\licenses\license.txt*

Odwołaj się do pliku *license.txt* przy użyciu ścieżki względnej *licenses\license.txt*.

## <a name="create-assign-and-monitor-a-win32-app"></a>Tworzenie, przypisywanie i monitorowanie aplikacji Win32

Podobnie jak w przypadku aplikacji biznesowych, możesz dodać aplikację Win32 do usługi Microsoft Intune. Aplikacje tego typu są zwykle pisane we własnym zakresie lub przez inną firmę. W poniższych krokach przedstawiono wskazówki ułatwiające dodanie aplikacji systemu Windows do usługi Microsoft Intune.

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

### <a name="step-4-configure-app-installation-details"></a>Krok 4. Konfigurowanie szczegółów instalacji aplikacji
1.  W okienku **Dodawanie aplikacji** wybierz pozycję **Program**, aby skonfigurować polecenia instalacji i usuwania aplikacji.
2.  Dodaj pełny wiersz polecenia instalacji, który umożliwia zainstalowanie aplikacji. 

    Na przykład jeśli nazwa pliku aplikacji to **MyApp123**, dodaj następujące polecenie: `msiexec /i “MyApp123.msi”`

3.  Dodaj pełny wiersz polecenia dezinstalacji, który umożliwia odinstalowanie aplikacji na podstawie identyfikatora GUID aplikacji. 

    Na przykład: `msiexec /x “{12345A67-89B0-1234-5678-000001000000}”`

    > [!NOTE]
    > Możesz skonfigurować aplikację Win32, aby została zainstalowana w kontekście **Użytkownik** lub **System**. Kontekst **Użytkownik** odwołuje się tylko do danego użytkownika. Kontekst **System** odwołuje się do wszystkich użytkowników urządzenia z systemem Windows 10.
    >
    > Użytkownicy końcowi nie muszą być zalogowani na urządzeniu, aby instalować aplikacje Win32.

4.  Po zakończeniu wybierz przycisk **OK**.

### <a name="step-5-configure-app-requirements"></a>Krok 5. Konfigurowanie wymagań aplikacji

1.  W okienku **Dodawanie aplikacji** wybierz pozycję **Wymagania**, aby skonfigurować wymagania, które urządzenia muszą spełniać, aby można było zainstalować aplikację.
2.  W okienku **Wymagania** skonfiguruj następujące informacje. Niektóre wartości w tym okienku mogą zostać wypełnione automatycznie.
    - **Architektura systemu operacyjnego**: wybierz architekturę wymaganą do zainstalowania aplikacji.
    - **Minimalna wersja systemu operacyjnego**: wybierz minimalną wersję systemu operacyjnego wymaganą do zainstalowania aplikacji.
    - **Wymagane miejsce na dysku (MB)**: opcjonalnie określ ilość wolnego miejsca na dysku systemowym wymaganego do zainstalowania aplikacji.
    - **Wymagana pamięć fizyczna (MB)**: opcjonalnie określ ilość pamięci fizycznej (RAM) wymaganej do zainstalowania aplikacji.
    - **Wymagana minimalna liczba procesorów logicznych**: opcjonalnie określ minimalną liczbę procesorów logicznych wymaganą do zainstalowania aplikacji.
    - **Wymagana minimalna szybkość procesora (MHz)**: opcjonalnie określ minimalną szybkość procesora wymaganą do zainstalowania aplikacji.
3.  Po zakończeniu wybierz przycisk **OK**.

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

### <a name="step-7-configure-app-return-codes"></a>Krok 7. Konfigurowanie kodów powrotnych aplikacji

1.  W okienku **Dodawanie aplikacji** wybierz pozycję **Kody powrotne**, aby dodać kody powrotne używane do określenia zachowania ponowienia instalacji aplikacji lub zachowania po instalacji. Pozycje kodów powrotnych są dodawane domyślnie podczas tworzenia aplikacji. Istnieje jednak możliwość dodania kolejnych kodów powrotnych lub zmiany istniejących kodów powrotnych. 
2.  W okienku **Kody powrotne** dodaj kolejne kody powrotne lub zmodyfikuj istniejące kody powrotne.
    - **Niepowodzenie** — wartość zwracana, która wskazuje błąd instalacji aplikacji.
    - **Ponowny rozruch sprzętowy** — kod powrotny ponownego uruchomienia sprzętowego nie zezwala na zainstalowanie następnej aplikacji Win32 na kliencie bez ponownego uruchomienia. 
    - **Ponowny rozruch systemowy** — kod powrotny ponownego uruchomienia systemowego umożliwia zainstalowanie następnej aplikacji Win32 bez ponownego uruchomienia klienta. Ponowne uruchomienie jest niezbędne do ukończenia instalacji bieżącej aplikacji.
    - **Ponów** — w przypadku kodu powrotnego ponowienia agent spróbuje zainstalować aplikację trzy razy. Między próbami agent będzie czekać 5 minut. 
    - **Powodzenie** — wartość zwracana, która wskazuje pomyślne zainstalowanie aplikacji.
3.  Wybierz pozycję **OK** po dodaniu lub zmodyfikowaniu listy kodów powrotnych.

### <a name="step-8-add-the-app"></a>Krok 8. Dodawanie aplikacji

1.  W okienku **Dodaj aplikację** sprawdź poprawność skonfigurowanych informacji.
2.  Wybierz pozycję **Dodaj**, aby przekazać aplikację do usługi Intune.

### <a name="step-9-assign-the-app"></a>Krok 9. Przypisywanie aplikacji

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

## <a name="delivery-optimization"></a>Optymalizacja dostarczania

System Windows 10 RS3 i nowsi klienci będą pobierać zawartość aplikacji Win32 w usłudze Intune przy użyciu składnika Optymalizacja dostarczania w obrębie klienta systemu Windows 10. Optymalizacja dostarczania udostępnia funkcję Sieć równorzędna, która jest włączana domyślnie. Optymalizację dostarczania można skonfigurować przy użyciu zasad grupy, a w przyszłości oprogramowania MDM w usłudze Intune. Aby uzyskać więcej informacji, zobacz [Delivery Optimization for Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) (Optymalizacja dostarczania w systemie Windows 10). 

## <a name="install-required-and-available-apps-on-devices"></a>Instalowanie wymaganych i dostępnych aplikacji na urządzeniach

Użytkownik końcowy nie będzie widzieć wyskakujących powiadomień systemu Windows dotyczących instalacji wymaganych i dostępnych aplikacji. Na poniższym obrazie przedstawiono przykładowe wyskakujące powiadomienie z informacją o tym, że instalacja aplikacji nie zostanie zakończona do momentu ponownego uruchomienia urządzenia. 

![Zrzut ekranu z wyskakującymi powiadomieniami systemu Windows dla instalacji aplikacji](./media/apps-win32-app-08.png)    

Poniższy obraz przedstawia powiadomienie użytkownika końcowego o wprowadzeniu zmian na urządzeniu.

![Zrzut ekranu powiadamiający użytkownika o tym, że są wprowadzane zmiany aplikacji](./media/apps-win32-app-09.png)    

## <a name="toast-notifications-for-win32-apps"></a>Wyskakujące powiadomienia dla aplikacji Win32 
W razie potrzeby można pominąć wyświetlanie wyskakujących powiadomień dla użytkownika końcowego podczas przypisywania aplikacji. W usłudze Intune wybierz kolejno pozycje **Aplikacje klienckie** > **Aplikacje** > wybierz aplikację > **Przypisania** > **Uwzględnij grupy**. 

## <a name="troubleshoot-win32-app-issues"></a>Rozwiązywanie problemów z aplikacjami Win32
Typowa lokalizacja dzienników agenta na maszynie klienta to `C:\ProgramData\Microsoft\IntuneManagementExtension\Logs`. Do wyświetlenia plików dziennika możesz użyć programu `CMTrace.exe`. Program *CMTrace.exe* można pobrać ze strony [Narzędzia klienta SCCM](https://docs.microsoft.com/sccm/core/support/tools). 

![Zrzut ekranu przedstawiający dzienniki klienta na maszynie klienta](./media/apps-win32-app-10.png)    

### <a name="troubleshooting-areas-to-consider"></a>Obszary rozwiązywania problemów do uwzględnienia
- Sprawdź ustawienie celu, aby upewnić się, że agent jest zainstalowany na urządzeniu — aplikacja Win32 przeznaczona dla grupy lub skrypt programu PowerShell przeznaczony dla grupy spowoduje utworzenie zasad instalacji agenta dla grupy zabezpieczeń.
- Sprawdź wersję systemu operacyjnego — system Windows 10 1607 lub nowszy.  
- Sprawdź jednostkę SKU systemu Windows 10 — system Windows 10 S lub system Windows z włączonym trybem S nie obsługują instalacji za pomocą pliku MSI.

## <a name="next-steps"></a>Następne kroki

- Aby uzyskać więcej informacji na temat dodawania aplikacji do usługi Intune, zobacz [Dodawanie aplikacji w usłudze Microsoft Intune](apps-add.md).
