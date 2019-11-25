---
title: Konfigurowanie programu Microsoft Intune Exchange Connector
titleSuffix: Microsoft Intune
description: Za pomocą lokalnego programu Intune Exchange Connector możesz zarządzać dostępem urządzeń do skrzynek pocztowych programu Exchange na podstawie rejestracji w usłudze Intune oraz programu Exchange ActiveSync (EAS).
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: demerson
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 62db99fc2e47bdfa1a767db3bb2916649dedc074
ms.sourcegitcommit: 15e099a9a1e18296580bb345610aee7cc4acd126
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2019
ms.locfileid: "74164686"
---
# <a name="set-up-the-on-premises-intune-exchange-connector"></a>Konfigurowanie lokalnego programu Intune Exchange Connector
Aby ułatwić ochronę dostępu do programu Exchange, usługa Intune opiera się na składniku lokalnym znanym jako program Microsoft Intune Exchange. W niektórych lokalizacjach konsoli usługi Intune ten łącznik nosi również nazwę *Lokalny łącznik programu Exchange ActiveSync*. 

Informacje przedstawione w tym artykule ułatwiają instalowanie i monitorowanie programu Intune Exchange Connector. Możesz używać łącznika z [zasadami dostępu warunkowego](conditional-access-exchange-create.md) do dopuszczania lub blokowania dostępu do lokalnych skrzynek pocztowych programu Exchange. 

Łącznik jest instalowany i uruchamiany na sprzęcie lokalnym. Odnajduje on urządzenia łączące się z programem Exchange, co pozwala na przekazywanie informacji o urządzeniach do usługi Intune. Łącznik dopuszcza lub blokuje dostęp do urządzeń w zależności od tego, czy urządzenia zostały zarejestrowane i są zgodne. Ta komunikacja korzysta z protokołu HTTPS.

Gdy urządzenie podejmuje próbę uzyskania dostępu do lokalnego programu Exchange Server, łącznik programu Exchange mapuje rekordy Exchange ActiveSync (EAS) w programie Exchange Server na rekordy usługi Intune. Pozwala to na upewnienie się, że urządzenie zostało zarejestrowane w usłudze Intune i jest zgodne z zasadami dotyczącymi urządzenia. Na podstawie zasad dostępu warunkowego dostęp jest przyznawany lub blokowany. Aby uzyskać więcej informacji, zobacz temat [Jakie są typowe sposoby korzystania z dostępu warunkowego przy użyciu usługi Intune?](conditional-access-intune-common-ways-use.md)

Obydwie operacje — *odnajdywania* oraz *zezwalania i blokowania* są wykonywane przy użyciu standardowych poleceń cmdlet Exchange PowerShell. Te operacje korzystają z konta usługi wybranego podczas pierwszej instalacji programu Exchange Connector. 

Usługa Intune obsługuje instalację wielu lokalnych programów Intune Exchange Connector na subskrypcję. Jeśli masz więcej niż jedną lokalną organizację programu Exchange, możesz skonfigurować osobny łącznik dla każdej organizacji. Jednak w danej organizacji programu Exchange można zainstalować tylko jeden łącznik.  

Wykonaj poniższe ogólne kroki, aby skonfigurować połączenie, które umożliwi usłudze Intune komunikowanie się z lokalnym serwerem programu Exchange:

1. Pobranie lokalnego łącznika lokalnego z portalu usługi Intune.
2. Zainstalowanie i skonfigurowanie programu Exchange Connector na komputerze w lokalnej organizacji programu Exchange.
3. Sprawdzenie działania połączenia z serwerem Exchange.
4. Powtórz te czynności dla każdej organizacji programu Exchange, którą chcesz połączyć z usługą Intune.

## <a name="intune-exchange-connector-requirements"></a>Wymagania dotyczące programu Intune Exchange Connector

Do połączenia z programem Exchange potrzebne jest konto z licencją usługi Intune, którego może używać łącznik. To konto jest określane podczas instalowania łącznika.  

Poniższa tabela zawiera listę wymagań dotyczących komputera, na którym ma być instalowany program Intune Exchange Connector.  

|  Wymaganie  |   Więcej informacji     |
|---------------|------------------------|
|  Systemy operacyjne        | Usługa Intune obsługuje program Intune Exchange Connector na komputerach z dowolną wersją systemu Windows Server 2008 z dodatkiem SP2 (64-bitową), Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2 i Windows Server 2016.<br /><br />Program Connector nie jest obsługiwany w żadnej instalacji Server Core.  |
| Microsoft Exchange          | Lokalne łączniki wymagają programu Microsoft Exchange 2010 z dodatkiem SP3 lub jego nowszej wersji albo starszej wersji środowiska usługi Exchange Online w wersji dedykowanej. Aby ustalić, czy środowisko usługi Exchange Online w wersji dedykowanej zawiera *nową* czy *starszą* konfigurację, skontaktuj się z menedżerem ds. klientów. |
| Urząd zarządzania urządzeniami przenośnymi           | [Konfigurowanie usługi Intune jako urzędu zarządzania urządzeniami przenośnymi](../fundamentals/mdm-authority-set.md). |
| Sprzęt              | Komputer, na którym jest instalowany łącznik, wymaga co najmniej procesora CPU 1,6 GHz z 2 GB pamięci RAM oraz 10 GB wolnego miejsca na dysku. |
|  Synchronizacja z usługą Active Directory             | Przed użyciem łącznika do łączenia usługi Intune z serwerem Exchange Server [skonfiguruj synchronizację z usługą Active Directory](../fundamentals/users-add.md). Lokalnych użytkowników i grupy zabezpieczeń należy zsynchronizować z wystąpieniem usługi Azure Active Directory. |
| Dodatkowe oprogramowanie         | Na komputerze, który będzie hostem łącznika, musi zostać w pełni zainstalowana platforma Microsoft .NET Framework 4.5 i program Windows PowerShell 2.0. |
| Sieć               | Komputer, na którym ma być instalowany łącznik, musi należeć do domeny, która ma relację zaufania z domeną hostującą program Exchange Server.<br /><br />Komputer należy skonfigurować tak, aby zezwolić mu dostęp do usługi Intune za pośrednictwem zapór i serwerów proxy przez porty 80 i 443. Usługa Intune używa następujących domen: <br> - manage.microsoft.com <br> - \*manage.microsoft.com<br> - \*.manage.microsoft.com <br><br> Program Intune Exchange Connector komunikuje się z następującymi usługami: <br> - Usługa Intune: port 443 protokołu HTTPS <br> -Serwer dostępu klienta programu Exchange (CAS): port 443 usługi WinRM<br> - Adres URL wykrywania automatycznego programu Exchange 443<br> - Usługi Exchange Web Services (EWS) 443  |

### <a name="exchange-cmdlet-requirements"></a>Wymagania poleceń cmdlet programu Exchange

Utwórz konto użytkownika usługi Active Directory do użycia przez program Intune Exchange Connector. Konto musi mieć uprawnienia do uruchamiania następujących poleceń cmdlet programu Exchange w środowisku Windows PowerShell:  

- `Get-ActiveSyncOrganizationSettings`, `Set-ActiveSyncOrganizationSettings`
- `Get-CasMailbox`, `Set-CasMailbox`
- `Get-ActiveSyncMailboxPolicy`, `Set-ActiveSyncMailboxPolicy`, `New-ActiveSyncMailboxPolicy`, `Remove-ActiveSyncMailboxPolicy`
- `Get-ActiveSyncDeviceAccessRule`, `Set-ActiveSyncDeviceAccessRule`, `New-ActiveSyncDeviceAccessRule`, `Remove-ActiveSyncDeviceAccessRule`
- `Get-ActiveSyncDeviceStatistics`
- `Get-ActiveSyncDevice`
- `Get-ExchangeServer`
- `Get-ActiveSyncDeviceClass`
- `Get-Recipient`
- `Clear-ActiveSyncDevice`, `Remove-ActiveSyncDevice`
- `Set-ADServerSettings`
- `Get-Command`

## <a name="download-the-installation-package"></a>Pobieranie pakietu instalacyjnego

Na serwerze z systemem Windows, który może obsługiwać program Intune Exchange Connector:

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).  Użyj konta, które jest kontem administratora na lokalnym serwerze programu Exchange i ma licencję na korzystanie z programu Exchange Server.

2. Wybierz pozycję **Administracja dzierżawą** > **Dostęp do programu Exchange**.  

3. W obszarze **Instalacja** wybierz pozycję **Lokalny łącznik Exchange ActiveSync**, a następnie wybierz pozycję **Dodaj**.

4. Na stronie **Dodawanie łącznika** wybierz pozycję **Pobierz łącznik lokalny**. Program Intune Exchange Connector znajduje się w skompresowanym folderze (pliku zip), który można otworzyć lub zapisać. W oknie dialogowym **Pobieranie pliku** wybierz pozycję **Zapisz**, aby zapisać skompresowany folder w bezpiecznej lokalizacji.

## <a name="install-and-configure-the-intune-exchange-connector"></a>Instalowanie i konfigurowanie programu Intune Exchange Connector

Wykonaj następujące kroki, aby zainstalować program Intune Exchange Connector. Jeśli masz wiele organizacji programu Exchange, powtórz te kroki dla każdego łącznika programu Exchange, który chcesz skonfigurować.

1. W obsługiwanym systemie operacyjnym programu Intune Exchange Connector wyodrębnij pliki z archiwum **Exchange_Connector_Setup.zip** w bezpiecznej lokalizacji.
   > [!IMPORTANT]
   > Nie zmieniaj nazw ani nie przenoś plików znajdujących się w folderze *Exchange_Connector_Setup*. Te zmiany spowodują, że instalacja łącznika nie powiedzie się.

2. Po wyodrębnieniu plików otwórz wyodrębniony folder i kliknij dwukrotnie plik **Exchange_Connector_Setup.exe**, aby zainstalować łącznik.

   > [!IMPORTANT]
   > Jeśli folder docelowy jest bezpieczną lokalizacją, usuń plik certyfikatu *MicrosoftIntune.accountcert* po zakończeniu instalacji łączników lokalnych.

3. W oknie dialogowym **Microsoft Intune Exchange Connector** wybierz opcję **Lokalny program Microsoft Exchange Server** lub **Hostowany program Microsoft Exchange Server**.

   ![Obraz przedstawiający miejsce, w którym należy wybrać typ serwera Exchange Server](./media/exchange-connector-install/intune-sa-exchange-connector-config.png)

   W przypadku lokalnego serwera Exchange podaj nazwę lub w pełni kwalifikowaną nazwę domeny serwera Exchange, który hostuje rolę **serwera Dostęp klienta**.

   W przypadku hostowanego serwera Exchange podaj adres serwera Exchange. Aby określić adres URL hostowanego serwera Exchange:

   1. Otwórz program Outlook dla Office 365.

   2. Wybierz ikonę **?** w lewym górnym rogu, a następnie wybierz pozycję **Informacje**.

   3. Znajdź wartość **Zewnętrzny serwer protokołu POP** .

   4. Wybierz pozycję **Serwer proxy**, aby określić ustawienia serwera proxy dla hostowanego serwera Exchange.

       1. Wybierz opcję **Użyj serwera proxy podczas synchronizacji informacji o urządzeniu przenośnym**.

       1. W polach **Nazwa serwera proxy** i **Numer portu** podaj wartości, które mają być używane na potrzeby dostępu do serwera.

       1. Jeśli do uzyskania dostępu do serwera proxy są wymagane poświadczenia użytkownika, wybierz pozycję **Użyj poświadczeń do nawiązania połączenia z serwerem proxy**. i podaj wartości w polach **Domena\nazwa_użytkownika** i **Hasło**.

       1. Wybierz przycisk **OK**.

4. W polach **Nazwa użytkownika (domena\nazwa_użytkownika)** i **Hasło** podaj poświadczenia, aby połączyć się z serwerem programu Exchange. Wskazane konto musi mieć licencję umożliwiającą korzystanie z usługi Intune. 

5. Podaj poświadczenia, aby wysyłać powiadomienia do skrzynek pocztowych użytkownika programu Exchange Server. Ten użytkownik może być przeznaczony jedynie do obsługi powiadomień. Użytkownik powiadomień potrzebuje skrzynki pocztowej programu Exchange, aby móc wysyłać powiadomienia pocztą e-mail. Powiadomienia te można skonfigurować, używając zasad dostępu warunkowego w usłudze Intune.  

   Upewnij się, że usługa wykrywania automatycznego i usługi internetowe programu Exchange zostały skonfigurowane na serwerze dostępu klienta programu Exchange. Aby uzyskać więcej informacji na ten temat, zapoznaj się z artykułem [Client Access server](https://technet.microsoft.com/library/dd298114.aspx) (Serwer dostępu klienta).

6. W polu **Hasło** podaj hasło dla tego konta, aby umożliwić usłudze Intune dostęp do serwera programu Exchange.

   > [!NOTE]
   > Konto używane do logowania do dzierżawy musi odpowiadać co najmniej administratorowi usługi Intune. Bez tego konta administratora wystąpi następujący błąd połączenia „Serwer zdalny zwrócił błąd: (400) nieprawidłowe żądanie”.

7. Wybierz polecenie **Połącz**.

   > [!NOTE]
   > Konfigurowanie połączenia może potrwać kilka minut.

Podczas konfigurowania program Exchange Connector zapisuje ustawienia serwera proxy, aby umożliwić dostęp do Internetu. Jeśli ustawienia serwera proxy zostaną zmienione, skonfiguruj ponownie program Exchange Connector w celu zastosowania zaktualizowanych ustawień serwera proxy dla programu Exchange Connector.

Po skonfigurowaniu połączenia w programie Exchange Connector urządzenia przenośne skojarzone z użytkownikami zarządzanymi przez program Exchange zostaną automatycznie zsynchronizowane i dodane do programu Exchange Connector. Ukończenie synchronizacji może zająć pewien czas.

> [!NOTE]
> W przypadku zainstalowania programu Intune Exchange Connector i późniejszego usunięcia połączenia z programem Exchange należy odinstalować łącznik z komputera, na którym został zainstalowany.

## <a name="install-connectors-for-multiple-exchange-organizations"></a>Instalowanie łączników dla wielu organizacji programu Exchange

Usługa Intune obsługuje wiele lokalnych programów Intune Exchange Connector na subskrypcję. W przypadku dzierżawy z wieloma organizacjami programu Exchange można skonfigurować tylko jeden łącznik dla każdej organizacji programu Exchange. 

Aby zainstalować łączniki w celu nawiązania połączenia z wieloma organizacjami programu Exchange, należy jeden raz pobrać folder zip. Użyj tego samego pobranego pliku dla każdego instalowanego łącznika. Dla każdego dodatkowego łącznika wykonaj czynności opisane w poprzedniej sekcji, aby wyodrębnić i uruchomić program instalacyjny na serwerze w organizacji programu Exchange.

Każda organizacja programu Exchange, która nawiązuje połączenie z usługą Intune, obsługuje wysoką dostępność, monitorowanie i synchronizację ręczną. Funkcje te opisano w poniższych sekcjach.

## <a name="on-premises-intune-exchange-connector-high-availability-support"></a>Obsługa wysokiej dostępności lokalnego programu Intune Exchange Connector  

W przypadku łącznika lokalnego wysoka dostępność oznacza, że jeśli serwer dostępu klienta Exchange używany przez łącznik stanie się niedostępny, łącznik może zostać przełączony do innego serwera dostępu klienta dla danej organizacji programu Exchange. Sam program Exchange Connector nie obsługuje wysokiej dostępności. W przypadku niepowodzenia łącznika nie następuje automatyczne przełączenie w tryb failover. Musisz [zainstalować nowy łącznik](#reinstall-the-intune-exchange-connector), aby zastąpić łącznik, którego działanie zakończyło się niepowodzeniem.

Aby przełączyć się w tryb failover, łącznik używa określonego serwera dostępu klienta do utworzenia udanego połączenia z programem Exchange. Następnie odnajduje on dodatkowe serwery dostępu klienta dla tej organizacji programu Exchange. Takie odnajdowanie umożliwia łącznikowi przełączenie się w tryb failover na innym serwerze dostępu klienta (jeśli jest dostępny) do momentu przywrócenia dostępności podstawowego serwera dostępu klienta.

Domyślnie odnajdywanie dodatkowych serwerów dostępu klienta jest włączone. Jeśli musisz wyłączyć tryb failover:

1. Na serwerze, na którym został zainstalowany program Exchange Connector, przejdź do folderu **%*ProgramData*%\Microsoft\Windows Intune Exchange Connector**.

2. Za pomocą edytora tekstów otwórz plik **OnPremisesExchangeConnectorServiceConfiguration.xml**.

3. Zmień wartość **\<IsCasFailoverEnabled>*true*\</IsCasFailoverEnabled>** na **\<IsCasFailoverEnabled>*false*\</IsCasFailoverEnabled>** .

## <a name="performance-tune-the-exchange-connector-optional"></a>Dostrajanie wydajności programu Exchange Connector (opcjonalnie)

Jeśli program Exchange ActiveSync obsługuje co najmniej 5000 urządzeń, możesz skonfigurować opcjonalne ustawienie poprawiające wydajność łącznika. Aby zwiększyć wydajność, możesz włączyć w programie Exchange możliwość korzystania z wielu wystąpień obszarów uruchamiania poleceń programu PowerShell.

Przed wprowadzeniem tej zmiany upewnij się, że konto używane do uruchamiania łącznika programu Exchange nie jest używane do innych zadań zarządzania programem Exchange. Konto programu Exchange ma ograniczoną liczbę obszarów uruchamiania, a łącznik używa większości z nich.

Dostrajanie wydajności nie jest odpowiednie w przypadku łączników, które działają na starszym lub wolniejszym sprzęcie.

Aby zwiększyć wydajność programu Exchange Connector:

1. Na serwerze, na którym zainstalowano łącznik, otwórz katalog instalacyjny łączników.  Jego domyślna lokalizacja to *C:\ProgramData\Microsoft\Windows Intune Exchange Connector*.

2. Otwórz plik *OnPremisesExchangeConnectorServiceConfiguration.xml* do edycji.

3. Znajdź właściwość **EnableParallelCommandSupport** i ustaw dla niej wartość **true**:

   \<EnableParallelCommandSupport>true\</EnableParallelCommandSupport>

4. Zapisz plik, a następnie uruchom ponownie usługę Microsoft Intune Exchange Connector.

## <a name="reinstall-the-intune-exchange-connector"></a>Ponowne instalowanie programu Intune Exchange Connector

Może być konieczne ponowne zainstalowanie programu Intune Exchange Connector. Ponieważ tylko jeden łącznik może połączyć się z każdą organizacją programu Exchange, jeśli zainstalujesz drugi łącznik dla organizacji, nowy łącznik zastąpi pierwotny łącznik.

1. Aby zainstalować nowy łącznik, wykonaj czynności opisane w sekcji [Instalowanie i konfigurowanie programu Exchange Connector](#install-and-configure-the-intune-exchange-connector).

2. Po wyświetleniu monitu wybierz pozycję **Zastąp**, aby zainstalować nowy łącznik.
   ![Ostrzeżenie konfiguracyjne dotyczące zastąpienia łącznika](./media/exchange-connector-install/prompt-to-replace.png)

3. Wykonaj kroki opisane w sekcji [Instalowanie i konfigurowanie programu Intune Exchange Connector](#install-and-configure-the-intune-exchange-connector) i ponownie zaloguj się do usługi Intune.

4. W końcowym oknie wybierz pozycję **Zamknij**, aby zakończyć instalację.
   ![Kończenie instalacji](./media/exchange-connector-install/successful-reinstall.png)

## <a name="monitor-an-exchange-connector"></a>Monitorowanie programu Exchange Connector

Po pomyślnym skonfigurowaniu programu Exchange Connector można wyświetlić stan połączeń oraz ostatniej pomyślnej próby synchronizacji.

Aby zweryfikować połączenie programu Exchange Connector:

1. Na pulpicie nawigacyjnym usługi Intune wybierz pozycję **Dostęp do programu Exchange**.

2. Wybierz pozycję **Dostęp do lokalnego programu Exchange**, aby sprawdzić stan połączenia dla każdego łącznika programu Exchange.

Możesz również sprawdzić godzinę i datę ostatniej pomyślnej próby synchronizacji.

Począwszy od wersji 1710 usługi Intune, można korzystać z [pakietu administracyjnego programu System Center Operations Manager dla programu Exchange Connector oraz usługi Intune](https://www.microsoft.com/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True). Pakiet administracyjny oferuje różne sposoby monitorowania programu Exchange Connector w przypadku konieczności rozwiązywania problemów.

## <a name="manually-force-a-quick-sync-or-full-sync"></a>Ręczne wymuszanie szybkiej synchronizacji lub pełnej synchronizacji

Program Intune Exchange Connector regularnie i automatycznie synchronizuje rekordy protokołu EAS i urządzeń usługi Intune. W przypadku zmiany stanu zgodności urządzenia automatyczny proces synchronizacji regularnie zaktualizuje rekordy tak, aby dostęp urządzenia został odpowiednio umożliwiony lub zablokowany.

- **Szybka synchronizacja** jest przeprowadzana regularnie kilka razy dziennie. Podczas szybkiej synchronizacji są pobierane informacje o urządzeniach związane z użytkownikami z licencją usługi Intune i lokalnym programu Exchange korzystającymi z dostępu warunkowego, które uległy zmianie od ostatniej synchronizacji.

- **Pełna synchronizacja** jest domyślnie przeprowadzana raz dziennie. Podczas pełnej synchronizacji są pobierane informacje o urządzeniach związane ze wszystkimi użytkownikami z licencją usługi Intune i lokalnym programem Exchange korzystającymi z dostępu warunkowego. Pełna synchronizacja polega również na pobieraniu informacji o serwerze programu Exchange i zapewnianiu, że konfiguracja, którą usługa Intune określiła w witrynie Azure Portal, została zaktualizowana na serwerze programu Exchange.

Aby wymusić uruchomienie synchronizacji przez łącznik, można użyć opcji **Szybka synchronizacja** lub **Pełna synchronizacja** na pulpicie nawigacyjnym usługi Intune:

   1. Na pulpicie nawigacyjnym usługi Intune wybierz pozycję **Dostęp do programu Exchange**.

   2. Wybierz pozycję **Dostęp do lokalnego programu Exchange**.

   3. Wybierz łącznik do zsynchronizowania, a następnie wybierz pozycję **Szybka synchronizacja** lub **Pełna synchronizacja**.

## <a name="next-steps"></a>Następne kroki

Utwórz [zasady dostępu warunkowego dla lokalnych serwerów programu Exchange](conditional-access-exchange-create.md).
