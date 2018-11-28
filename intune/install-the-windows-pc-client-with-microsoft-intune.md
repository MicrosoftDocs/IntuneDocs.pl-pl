---
title: Instalowanie oprogramowania klienckiego komputera
description: Ten przewodnik ułatwia skonfigurowanie komputerów z systemem Windows jako zarządzanych przez oprogramowanie klienckie usługi Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
ms.date: 07/13/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.openlocfilehash: 9059ddb164dfa57ed76b57141aad89dbb716a09f
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52179088"
---
# <a name="install-the-intune-software-client-on-windows-pcs"></a>Instalowanie klienta oprogramowania usługi Intune na komputerach z systemem Windows

[!INCLUDE [classic-portal](includes/classic-portal.md)]

> [!NOTE]
> Możesz użyć usługi Microsoft Intune do zarządzania komputerami z systemem Windows albo [jako urządzeniami przenośnymi z wykorzystaniem zarządzania urządzeniami przenośnymi (MDM)](windows-enroll.md), albo jako komputerami z wykorzystaniem oprogramowania klienckiego usługi Intune zgodnie z poniższym opisem. Jednak firma Microsoft zaleca, aby klienci [używali rozwiązania MDM do zarządzania](windows-enroll.md) zawsze, gdy jest to możliwe.


Komputery z systemem Windows można zarejestrować, instalując oprogramowanie klienckie usługi Intune. Oprogramowanie klienckie usługi Intune można zainstalować na następujące sposoby:

- Przez administratora IT przy użyciu jednej z następujących metod: instalacja ręczna, zasady grupy lub instalacja dołączona na obrazie dysku

- Instalacja ręczna oprogramowania klienckiego przez użytkowników końcowych

Oprogramowanie klienckie usługi Intune zawiera minimalne składniki oprogramowania niezbędne do zarejestrowania komputera w zarządzaniu przy użyciu usługi Intune. Po zarejestrowaniu komputera oprogramowanie klienckie usługi Intune pobiera pełne oprogramowanie klienckie wymagane do zarządzania komputerami.

Powyższa seria pobrań zmniejsza wpływ na przepustowość sieci i skraca do minimum czas wymagany do rejestrowania początkowego komputera w usłudze Intune. Gwarantuje to również, że po ukończeniu drugiego pobierania klient ma najnowsze dostępne oprogramowanie.

Jedna licencja usługi Intune umożliwia zainstalowanie oprogramowania klienckiego usługi Intune na pięciu komputerach.

## <a name="download-the-intune-client-software"></a>Pobieranie oprogramowania klienckiego usługi Intune

Wszystkie metody z wyjątkiem sytuacji, w których użytkownicy samodzielnie instalują oprogramowanie klienckie usługi Intune, wymagają, aby administratorzy IT pobrali oprogramowanie, które następnie zostanie wdrożone u użytkowników końcowych.

1. W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) kliknij pozycję **Administracja** &gt;  **Pobieranie oprogramowania klienckiego**.

   ![Pobieranie klienta komputerowego usługi Intune](./media/https://docs.microsoft.com/intune/media/install-the-windows-pc-client/pc-sa-client-download.png)

2. Na stronie **Pobieranie oprogramowania klienckiego** kliknij przycisk **Pobieranie oprogramowania klienckiego**. Następnie zapisz pakiet **Microsoft_Intune_Setup.zip**, który zawiera oprogramowanie, w bezpiecznej lokalizacji w sieci.

   Pakiet instalacyjny oprogramowania klienckiego usługi Intune zawiera unikatowe i specyficzne informacje dotyczące Twojego konta, które są dostępne za pośrednictwem osadzonego certyfikatu. Jeśli nieautoryzowani użytkownicy uzyskają dostęp do pakietu instalacyjnego, mogą zarejestrować komputery na koncie reprezentowanym przez osadzony certyfikat tego pakietu i mogą uzyskać dostęp do zasobów firmy.

3. Wyodrębnij zawartość pakietu instalacyjnego w bezpiecznej lokalizacji w sieci.

    > [!IMPORTANT]
    > Nie zmieniaj nazwy wyodrębnionego pliku **ACCOUNTCERT** ani nie usuwaj go, ponieważ spowoduje to niepowodzenie instalacji oprogramowania klienckiego.

## <a name="deploy-the-client-software-manually"></a>Ręczne wdrażanie oprogramowania klienckiego

Na komputerach, na których ma zostać zainstalowane oprogramowanie klienckie, przejdź do folderu, w którym znajdują się jego pliki instalacyjne. Następnie uruchom plik **Microsoft_Intune_Setup.exe**, aby zainstalować oprogramowanie klienckie.

> [!NOTE]
> Stan instalacji można wyświetlić, zatrzymując wskaźnik myszy na ikonie na pasku zadań komputera klienckiego.

## <a name="deploy-the-client-software-by-using-group-policy"></a>Wdrażanie oprogramowania klienckiego za pomocą zasad grupy

1.  W folderze zawierającym pliki **Microsoft_Intune_Setup.exe** i **MicrosoftIntune.accountcert** uruchom następujące polecenie, aby wyodrębnić programy instalacyjne oparte na Instalatorze Windows dla komputerów 32-bitowych i 64-bitowych:

    ```
    Microsoft_Intune_Setup.exe/Extract <destination folder>
    ```

2.  Skopiuj pliki **Microsoft_Intune_x86.msi**, **Microsoft_Intune_x64.msi** i **MicrosoftIntune.accountcert** do lokalizacji sieciowej dostępnej dla wszystkich komputerów, na których ma zostać zainstalowane oprogramowanie klienckie.

    > [!IMPORTANT]
    > Nie należy rozdzielać plików ani zmieniać ich nazw, ponieważ spowoduje to niepowodzenie instalacji oprogramowania klienckiego.

3.  Wdróż oprogramowanie na komputerach w sieci za pomocą zasad grupy.

    Aby uzyskać więcej informacji o automatycznym wdrażaniu oprogramowania za pomocą zasad grupy, zapoznaj się z artykułem [Group Policy for Beginners](https://technet.microsoft.com/library/hh147307.aspx) (Zasady grupy dla początkujących użytkowników).

## <a name="deploy-the-client-software-as-part-of-an-image"></a>Wdrażanie oprogramowania klienckiego jako części obrazu
Oprogramowanie klienckie usługi Intune można wdrożyć na komputerach jako część obrazu systemu operacyjnego, postępując według następującej procedury:

1.  Skopiuj pliki instalacyjne klienta (**Microsoft_Intune_Setup.exe** i **MicrosoftIntune.accountcert**) do folderu **%Systemdrive%\Temp\Microsoft_Intune_Setup** na komputerze odniesienia.

2.  Utwórz wpis rejestru **WindowsIntuneEnrollPending**, dodając następujące polecenie do skryptu **SetupComplete.cmd** :

    ```
    %windir%\system32\reg.exe add HKEY_LOCAL_MACHINE\Software\Microsoft\Onlinemanagement\Deployment /v
    WindowsIntuneEnrollPending /t REG_DWORD /d 1
    ```

3.  Dodaj następujące polecenie do pliku **SetupComplete.cmd**, aby uruchomić pakiet rejestracyjny z argumentem wiersza polecenia /PrepareEnroll:

    ```
    %systemdrive%\temp\Microsoft_Intune_Setup\Microsoft_Intune_Setup.exe /PrepareEnroll
    ```
    > [!TIP]
    > Skrypt **SetupComplete.cmd** umożliwia Instalatorowi systemu Windows wprowadzenie modyfikacji systemu przed zalogowaniem się użytkownika. Argument wiersza polecenia **/PrepareEnroll** powoduje przygotowanie komputera docelowego do automatycznej rejestracji w usłudze Intune po zakończeniu działania Instalatora systemu Windows.

4.  Umieść skrypt **SetupComplete.cmd** w folderze **%Windir%\Setup\Scripts** na komputerze odniesienia.

5.  Przechwyć obraz komputera odniesienia, a następnie wdróż go na komputerach docelowych.

    Gdy komputer docelowy zostanie uruchomiony ponownie po ukończeniu działania Instalatora systemu Windows, nastąpi utworzenie klucza rejestru **WindowsIntuneEnrollPending** . Pakiet rejestracyjny sprawdza, czy komputer jest zarejestrowany. Jeśli komputer jest zarejestrowany, nie są wykonywane żadne dalsze działania. Jeśli komputer nie jest zarejestrowany, pakiet rejestracyjny tworzy zadanie automatycznej rejestracji w usłudze Microsoft Intune.

    Gdy zadanie automatycznej rejestracji jest uruchamiane w następnym zaplanowanym terminie, sprawdza istnienie wartości rejestru **WindowsIntuneEnrollPending** i próbuje zarejestrować komputer docelowy w usłudze Intune. Jeśli rejestracja nie powiedzie się z jakiegokolwiek powodu, próba rejestracji zostanie ponowiona przy następnym uruchomieniu zadania. Ponowne próby będą kontynuowane przez miesiąc.

    Zadanie automatycznej rejestracji w usłudze Intune, wartość rejestru **WindowsIntuneEnrollPending** i certyfikat konta zostaną usunięte z komputera docelowego po pomyślnej rejestracji lub po upływie miesiąca (w zależności od tego, co nastąpi wcześniej).

## <a name="instruct-users-to-self-enroll"></a>Instruowanie użytkowników odnośnie samodzielnej rejestracji

Użytkownicy instalują oprogramowanie klienckie usługi Intune, przechodząc do [witryny internetowej Portal firmy](https://portal.manage.microsoft.com). Konkretne informacje, które widzą użytkownicy w portalu sieci Web, różnią się w zależności od urzędu certyfikacji MDM oraz platformy lub wersji systemu operacyjnego komputera użytkownika.

Jeśli użytkownikom nie przypisano licencji usługi Intune lub nie ustawiono usługi Intune jako urzędu certyfikacji zarządzania urządzeniami przenośnymi organizacji, opcje rejestracji nie są widoczne dla użytkowników.

Jeśli użytkownikom przypisano licencję usługi Intune i ustawiono usługę Intune jako urząd certyfikacji zarządzania urządzeniami przenośnymi organizacji:

- Dla użytkowników komputerów z systemem Windows 7 lub Windows 8 jest wyświetlana TYLKO opcja rejestracji w usłudze Intune przez pobranie i zainstalowanie komputerowego oprogramowania klienckiego, które jest unikatowe dla organizacji.

- Dla użytkowników komputerów z systemem Windows 10 lub Windows 8.1 są wyświetlane dwie opcje rejestracji:

  -  **Zarejestruj komputer jako urządzenie przenośne**: użytkownicy wybierają przycisk **Dowiedz się, jak zarejestrować** i przechodzą do instrukcji dotyczących sposobu rejestracji komputera jako urządzenia przenośnego. Ten przycisk jest zawsze wyświetlany, ponieważ rejestracja w zarządzaniu urządzeniami przenośnymi jest uznawana za domyślną i preferowaną opcję rejestracji. Jednak opcja zarządzania urządzeniami przenośnymi nie została uwzględniona w tym temacie, który obejmuje tylko instalację oprogramowania klienckiego.
  - **Zarejestruj komputer przy użyciu oprogramowania klienckiego usługi Intune**: należy poinformować użytkowników, aby wybrali link **Kliknij tutaj, aby je pobrać**, który poprowadzi ich przez proces instalacji oprogramowania klienckiego.

Poniższa tabela zawiera podsumowanie opcji.

  ![Domyślne opcje rejestracji dla danej platformy](./media/install-the-windows-pc-client/default-enrollment-options-table.png)

Na poniższych zrzutach ekranu przedstawiono zawartość wyświetlaną dla użytkowników podczas rejestrowania urządzeń przy użyciu oprogramowania klienckiego.

Najpierw wyświetlany jest monit o zidentyfikowanie lub zarejestrowanie urządzeń przez użytkowników.

  ![identyfikowanie lub rejestrowanie urządzenia](./media/install-the-windows-pc-client/identify-device-or-enroll.png)

W celu zainstalowania komputerowego oprogramowania klienckiego przez użytkowników musisz poinformować ich, aby wybrali link **Kliknij tutaj , aby je pobrać**, który umożliwia użytkownikom pobranie komputerowego oprogramowania klienckiego i prowadzi ich przez proces instalacji. Przycisk **Dowiedz się, jak zarejestrować** powoduje przejście do dokumentacji dotyczącej sposobu rejestrowania za pomocą opcji rejestracji w zarządzaniu urządzeniami przenośnymi, która nie została uwzględniona w tej instrukcji oprogramowania klienckiego.

  ![wybieranie linku Kliknij tutaj, aby ją pobrać](./media/install-the-windows-pc-client/enroll-your-windows-device.png)

Po kliknięciu linku przez użytkowników jest wyświetlany przycisk **Pobierz oprogramowanie**, który należy wybrać, aby rozpocząć instalację komputerowego oprogramowania klienckiego.

  ![wybieranie przycisku Pobierz oprogramowanie](./media/install-the-windows-pc-client/download-pc-client-software.png)

Użytkownicy są proszeni o zalogowanie się za pomocą firmowych poświadczeń.

  ![Logowanie się przy użyciu poświadczeń](./media/install-the-windows-pc-client/sign-in-to-intune.png)

Użytkownicy przechodzą do strony powitalnej instalacji.

  ![Strona powitalna instalacji klienta komputerowego](./media/install-the-windows-pc-client/welcome-to-pc-agent-install-wizard.png)

Użytkownicy wybierają przycisk **Dalej**, po czym rozpoczyna się instalacja.

  ![Strona powitalna instalacji klienta komputerowego](./media/install-the-windows-pc-client/welcome-to-pc-agent-install-wizard.png)

Po zakończeniu instalacji użytkownicy wybierają przycisk **Zakończ**.

  ![Zakończenie instalacji klienta komputerowego](./media/install-the-windows-pc-client/completed-the-setup-wizard.png)

Jeśli użytkownicy podejmą próbę zarejestrowania komputera jako urządzenia przenośnego po zarejestrowaniu za pomocą komputerowego oprogramowania klienckiego usługi Intune, zostanie wyświetlony następujący ekran błędu.

  ![Ekran wyświetlany, jeśli komputer jest już zarejestrowany](./media/install-the-windows-pc-client/page-shown-if-pc-already-enrolled.png)

## <a name="monitor-and-validate-successful-client-deployment"></a>Monitorowanie i weryfikowanie pomyślnego wdrożenia klienta
Użyj jednej z poniższych procedur ułatwiających monitorowanie i weryfikowanie pomyślnego wdrożenia klienta.

### <a name="to-verify-the-installation-of-the-client-software-from-the-microsoft-intune-administrator-console"></a>Aby zweryfikować instalację oprogramowania klienckiego z poziomu konsoli administratora usługi Microsoft Intune

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) kliknij pozycję **Grupy** &gt; **Wszystkie urządzenia** &gt; **Wszystkie komputery**.

2.  Na liście znajdź komputery komunikujące się z usługą Intune, albo wyszukaj określony zarządzany komputer, wpisując jego nazwę (lub dowolną część nazwy) w polu **Wyszukaj urządzenia**.

3.  Sprawdź stan komputera w dolnym okienku konsoli. Usuń wszelkie błędy.

### <a name="to-create-a-computer-inventory-report-to-display-all-enrolled-computers"></a>Aby utworzyć raport ze spisu komputerów w celu wyświetlenia wszystkich zarejestrowanych komputerów

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) kliknij pozycje **Raporty** &gt; **Raporty ze spisu komputerów**.

2.  Na stronie **Tworzenie nowego raportu** pozostaw wartości domyślne we wszystkich polach (chyba że chcesz zastosować filtry), a następnie kliknij pozycję **Wyświetl raport**.

3.  W nowym oknie zostanie otwarta strona **Raport o spisie komputerów** zawierająca wszystkie komputery, które zostały pomyślnie zarejestrowane w usłudze Intune.

    > [!TIP]
    > Kliknij nagłówek dowolnej kolumny w raporcie, aby posortować listę według zawartości tej kolumny.

## <a name="uninstall-the-windows-client-software"></a>Odinstalowywanie oprogramowania klienckiego systemu Windows

Istnieją dwie metody wyrejestrowania oprogramowania klienckiego systemu Windows:

- Z konsoli administracyjnej usługi Intune (zalecana metoda)
- Z wiersza polecenia na komputerze klienckim

### <a name="unenroll-by-using-the-intune-admin-console"></a>Wyrejestrowanie przy użyciu konsoli administracyjnej usługi Intune

Aby wyrejestrować oprogramowanie klienckie za pomocą konsoli administracyjnej usługi Intune, przejdź kolejno do pozycji **Grupy** > **Wszystkie komputery** > **Urządzenia**. Kliknij klienta prawym przyciskiem myszy, a następnie wybierz pozycję **Wycofaj/Wyczyść**.

### <a name="unenroll-by-using-a-command-prompt-on-the-client"></a>Wyrejestrowanie przy użyciu wiersza polecenia na komputerze klienckim

W wierszu polecenia z podwyższonym poziomem uprawnień uruchom jedno z następujących poleceń.

**Metoda 1**:

    "C:\Program Files\Microsoft\OnlineManagement\Common\ProvisioningUtil.exe" /UninstallAgents /MicrosoftIntune

**Metoda 2** Należy pamiętać, że nie wszystkie agenty są zainstalowane we wszystkich jednostkach magazynowych systemu Windows:

    wmic product where name="Microsoft Endpoint Protection Management Components" call uninstall
    wmic product where name="Microsoft Intune Notification Service" call uninstall
    wmic product where name="System Center 2012 - Operations Manager Agent" call uninstall
    wmic product where name="Microsoft Online Management Policy Agent" call uninstall
    wmic product where name="Microsoft Policy Platform" call uninstall
    wmic product where name="Microsoft Security Client" call uninstall
    wmic product where name="Microsoft Online Management Client" call uninstall
    wmic product where name="Microsoft Online Management Client Service" call uninstall
    wmic product where name="Microsoft Easy Assist v2" call uninstall
    wmic product where name="Microsoft Intune Monitoring Agent" call uninstall
    wmic product where name="Windows Intune Endpoint Protection Agent" call uninstall
    wmic product where name="Windows Firewall Configuration Provider" call uninstall
    wmic product where name="Microsoft Intune Center" call uninstall
    wmic product where name="Microsoft Online Management Update Manager" call uninstall
    wmic product where name="Microsoft Online Management Agent Installer" call uninstall
    wmic product where name="Microsoft Intune" call uninstall
    wmic product where name="Windows Endpoint Protection Management Components" call uninstall
    wmic product where name="Windows Intune Notification Service" call uninstall
    wmic product where name="System Center 2012 - Operations Manager Agent" call uninstall
    wmic product where name="Windows Online Management Policy Agent" call uninstall
    wmic product where name="Windows Policy Platform" call uninstall
    wmic product where name="Windows Security Client" call uninstall
    wmic product where name="Windows Online Management Client" call uninstall
    wmic product where name="Windows Online Management Client Service" call uninstall
    wmic product where name="Windows Easy Assist v2" call uninstall
    wmic product where name="Windows Intune Monitoring Agent" call uninstall
    wmic product where name="Windows Intune Endpoint Protection Agent" call uninstall
    wmic product where name="Windows Firewall Configuration Provider" call uninstall
    wmic product where name="Windows Intune Center" call uninstall
    wmic product where name="Windows Online Management Update Manager" call uninstall
    wmic product where name="Windows Online Management Agent Installer" call uninstall
    wmic product where name="Windows Intune" call uninstall

> [!TIP]
> Wyrejestrowanie klienta pozostawi stary rekord po stronie serwera dla klienta, którego to dotyczy. Proces wyrejestrowania jest asynchroniczny i istnieje dziewięciu agentów do odinstalowania, więc operacja może potrwać do 30 minut.

### <a name="check-the-unenrollment-status"></a>Sprawdź stan wyrejestrowania

Sprawdź folder „%ProgramFiles%\Microsoft\OnlineManagement” i upewnij się, że po lewej stronie są wyświetlane tylko następujące katalogi:

- AgentInstaller
- Dzienniki
- Updates
- Wspólne

### <a name="remove-the-onlinemanagement-folder"></a>Usuń folder OnlineManagement

Operacja wyrejestrowania nie usuwa folderu OnlineManagement. Odczekaj 30 minut po odinstalowaniu, a następnie uruchom to polecenie. Jeśli zostanie ono uruchomione zbyt szybko, odinstalowanie może pozostać w nieznanym stanie. Aby usunąć folder, uruchom wiersz polecenia z podwyższonym poziomem uprawnień:

    "rd /s /q %ProgramFiles%\Microsoft\OnlineManagement".

### <a name="next-steps"></a>Następne kroki
[Zarządzanie urządzeniami przy użyciu usługi Microsoft Intune](device-management.md)
