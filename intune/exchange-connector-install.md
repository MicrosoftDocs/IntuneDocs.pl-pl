---
title: Konfigurowanie lokalnego programu Exchange Connector usługi Microsoft Intune
titleSuffix: Microsoft Intune
description: Za pomocą lokalnego programu Exchange Connector możesz zarządzać dostępem urządzeń do skrzynek pocztowych programu Exchange na podstawie rejestracji w usłudze Intune oraz programu Exchange Active Sync (EAS).
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: demerson
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e236548002f2779377e7ac57443077d48869e1f9
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/23/2019
ms.locfileid: "66047700"
---
# <a name="set-up-the-intune-on-premises-exchange-connector-in-microsoft-intune"></a>Konfigurowanie lokalnego programu Exchange Connector w usłudze Microsoft Intune
Informacje przedstawione w tym artykule ułatwiają instalowanie i monitorowanie lokalnego łącznika programu Exchange Active Sync dla usługi Intune.  Po skonfigurowaniu współdziałania lokalnego programu Exchange Connector w usłudze Intune z [zasadami dostępu warunkowego można sterować dostępem do lokalnych skrzynek pocztowych programu Exchange](conditional-access-exchange-create.md). 

Gdy urządzenie podejmuje próbę uzyskania dostępu do lokalnego programu Exchange, łącznik programu Exchange mapuje rekordy Exchange Active Sync (EAS) w programie Exchange Server na rekordy usługi Intune. Pozwala to sprawdzić rejestrację urządzeń w usłudze Intune i zweryfikować zgodność z zasadami dotyczącymi urządzeń. Na podstawie zasad dostępu warunkowego dostęp jest przyznawany lub blokowany. Aby uzyskać więcej informacji, zobacz temat [Jakie są typowe sposoby korzystania z dostępu warunkowego przy użyciu usługi Intune?](conditional-access-intune-common-ways-use.md)

Usługa Intune obsługuje instalację wielu lokalnych programów Exchange Connector na subskrypcję. Jeśli masz więcej niż jedną lokalną organizację programu Exchange, możesz skonfigurować osobny łącznik dla każdej organizacji. Jednak w danej organizacji programu Exchange można zainstalować tylko jeden łącznik. 

Poniżej przedstawiono w zarysie procedurę konfigurowania połączenia, które umożliwia usłudze Intune komunikowanie się z lokalnym serwerem programu Exchange:

1. Pobranie lokalnego programu Exchange Connector dla usługi Intune z portalu usługi Intune.
2. Zainstalowanie i skonfigurowanie programu Exchange Connector na komputerze w lokalnej organizacji programu Exchange.
3. Sprawdzenie działania połączenia z serwerem Exchange.
4. Powtórz te czynności dla każdej organizacji programu Exchange, którą chcesz połączyć z usługą Intune.

## <a name="intune-on-premises-exchange-connector-requirements"></a>Wymagania dotyczące lokalnego programu Exchange Connector
Potrzebne jest konto z licencją usługi Intune, które umożliwia łącznikowi łączenie się z programem Exchange. To konto jest podawane podczas instalacji łącznika.  

Poniższa tabela zawiera listę wymagań dotyczących komputera, na którym ma być instalowany lokalny program Exchange Connector.  

|  Wymaganie  |   Więcej informacji     |
|---------------|------------------------|
|  Systemy operacyjne        | Usługa Intune obsługuje lokalny program Exchange Connector na komputerach z dowolną wersją systemu Windows Server 2008 z dodatkiem SP2 (64-bitową), Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2 i Windows Server 2016.<br /><br />Program Connector nie jest obsługiwany w żadnej instalacji Server Core.  |
| Microsoft Exchange          | Lokalne łączniki wymagają programu Microsoft Exchange 2010 z dodatkiem SP3 lub jego nowszej wersji albo starszej wersji środowiska usługi Exchange Online w wersji dedykowanej. Aby ustalić, czy środowisko usługi Exchange Online w wersji dedykowanej zawiera <strong>nową</strong> czy <strong>starszą</strong> konfigurację, skontaktuj się z menedżerem ds. klientów. |
| Urząd zarządzania urządzeniami przenośnymi           | [Konfigurowanie usługi Intune jako urzędu zarządzania urządzeniami przenośnymi](mdm-authority-set.md). |
| Sprzęt              | Komputer, na którym jest instalowany łącznik, wymaga co najmniej procesora CPU 1,6 GHz z 2 GB pamięci RAM oraz 10 GB wolnego miejsca na dysku. |
|  Synchronizacja z usługą Active Directory             | Zanim będzie możliwe połączenie usługi Intune z programem Exchange Server przy użyciu programu Connector, należy [skonfigurować synchronizację usługi Active Directory](users-add.md), aby zapewnić synchronizację lokalnych użytkowników i grup zabezpieczeń z wystąpieniem usługi Azure Active Directory. |
| Dodatkowe oprogramowanie         | Na komputerze, który będzie hostem łącznika, musi być wdrożona pełna instalacja platformy Microsoft .NET Framework 4.5 i programu Windows PowerShell 2.0. |
| Sieć               | Komputer, na którym ma być instalowany łącznik, musi należeć do domeny, która ma relację zaufania z domeną hostującą program Exchange Server.<br /><br />Komputer wymaga zastosowania konfiguracji umożliwiającej mu dostęp do usługi Intune za pośrednictwem zapór i serwerów proxy przez porty 80 i 443. Domeny używane przez usługę Intune obejmują manage.microsoft.com, &#42;manage.microsoft.com i &#42;.manage.microsoft.com. |

### <a name="exchange-cmdlet-requirements"></a>Wymagania poleceń cmdlet programu Exchange

Utwórz konto użytkownika usługi Active Directory, które będzie używane przez lokalny program Exchange Connector. Konto musi mieć uprawnienia do uruchamiania następujących wymaganych poleceń cmdlet programu Exchange w środowisku Windows PowerShell:


 -   Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 -   Get-CasMailbox, Set-CasMailbox
 -   Get-ActiveSyncMailboxPolicy, Set-ActiveSyncMailboxPolicy, New-ActiveSyncMailboxPolicy, Remove-ActiveSyncMailboxPolicy
 -   Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 -   Get-ActiveSyncDeviceStatistics
 -   Get-ActiveSyncDevice
 -   Get-ExchangeServer
 -   Get-ActiveSyncDeviceClass
 -   Get-Recipient
 -   Clear-ActiveSyncDevice, Remove-ActiveSyncDevice
 -   Set-ADServerSettings
 -   Get-Command

## <a name="download-the-on-premises-exchange-connector-software-installation-package"></a>Pobieranie pakietu instalacyjnego lokalnego programu Exchange Connector

1. W obsługiwanym systemie operacyjnym Windows Server dla lokalnego programu Exchange Connector otwórz witrynę [Azure Portal](https://portal.azure.com) i zaloguj się przy użyciu konta użytkownika, który jest administratorem lokalnego serwera programu Exchange i ma licencję na korzystanie z programu Exchange Server.

2. Wybierz pozycję **Intune** > **Dostęp do programu Exchange**  

3. W obszarze **Instalacja** wybierz pozycję **Lokalny łącznik Exchange ActiveSync**, a następnie wybierz pozycję **Dodaj**.

4. Na stronie **Dodawanie łącznika** wybierz pozycję **Pobierz łącznik lokalny**. Lokalny program Exchange Connector znajduje się w skompresowanym folderze (pliku zip), który można otworzyć lub zapisać. W oknie dialogowym **Pobieranie pliku** wybierz polecenie **Zapisz**, aby zapisać skompresowany folder w bezpiecznej lokalizacji.

    > [!IMPORTANT]
    > Nie zmieniaj nazwy ani nie przenoś plików znajdujących się w folderze lokalnego programu Exchange Connector. Przeniesienie lub zmiana nazwy zawartości folderu spowoduje niepowodzenie instalacji programu Exchange Connector.

## <a name="install-and-configure-the-intune-on-premises-exchange-connector"></a>Instalowanie i konfigurowanie lokalnego programu Exchange Connector w usłudze Intune
Wykonaj następujące kroki, aby zainstalować lokalny program Exchange Connector usługi Intune. Jeśli masz wiele organizacji programu Exchange, powtórz te kroki dla każdego dodatkowego łącznika programu Exchange, który chcesz skonfigurować.

1. W obsługiwanym systemie operacyjnym lokalnego programu Exchange Connector wyodrębnij pliki z archiwum **Exchange_Connector_Setup.zip** w bezpiecznej lokalizacji.

2. Po wyodrębnieniu plików otwórz utworzony folder i kliknij dwukrotnie plik **Exchange_Connector_Setup.exe**, aby zainstalować lokalny program Exchange Connector.

   > [!IMPORTANT]
   > Jeśli folder docelowy nie znajduje się w bezpiecznej lokalizacji, należy usunąć plik certyfikatu **WindowsIntune.accountcert** po zakończeniu instalacji łączników lokalnych.

3. W oknie dialogowym **Microsoft Intune Exchange Connector** wybierz opcję **Lokalny program Microsoft Exchange Server** lub **Hostowany program Microsoft Exchange Server**.

   ![Obraz przedstawiający miejsce, w którym należy wybrać typ serwera Exchange Server](./media/intune-sa-exchange-connector-config.png)

   W przypadku lokalnego serwera Exchange podaj nazwę lub w pełni kwalifikowaną nazwę domeny serwera Exchange, który hostuje rolę **serwera Dostęp klienta**.

   W przypadku hostowanego serwera Exchange podaj adres serwera Exchange. Aby określić adres URL hostowanego serwera Exchange:

   1. W Internecie otwórz program Outlook dla usługi Office 365.

   2. Wybierz ikonę **?** w lewym górnym rogu, a następnie wybierz polecenie **Informacje**.

   3. Znajdź wartość **Zewnętrzny serwer protokołu POP** .

   4. Wybierz pozycję **Serwer proxy**, aby określić ustawienia serwera proxy dla hostowanego serwera Exchange.
       1. Wybierz opcję **Użyj serwera proxy podczas synchronizacji informacji o urządzeniu przenośnym**.

       2. W polach **Nazwa serwera proxy** i **Numer portu** podaj wartości, które mają być używane na potrzeby dostępu do serwera.

       3. Jeśli dostęp do serwera proxy wymaga podania poświadczeń użytkownika, wybierz pozycję **Użyj poświadczeń do nawiązania połączenia z serwerem proxy**. i podaj wartości w polach **Domena\nazwa_użytkownika** i **Hasło**.

       4. Wybierz przycisk **OK**.

4. W polach **Nazwa użytkownika (domena\nazwa_użytkownika)** i **Hasło** podaj poświadczenia wymagane do nawiązania połączenia z serwerem Exchange. Wskazane konto musi mieć licencję umożliwiającą korzystanie z usługi Intune. 

5. Podaj poświadczenia, które są niezbędne do wysyłania powiadomień do skrzynek pocztowych użytkowników programie Exchange Server. Ten użytkownik może być przeznaczony jedynie do obsługi powiadomień. Użytkownik powiadomień potrzebuje skrzynki pocztowej programu Exchange, aby móc wysyłać powiadomienia pocztą e-mail. Powiadomienia te można skonfigurować za pomocą zasad dostępu warunkowego w usłudze Intune.  

       Ensure that the Autodiscover service and Exchange Web Services are configured on the Exchange Client Access Server. For more information, see [Client Access server](https://technet.microsoft.com/library/dd298114.aspx).

6. W polu **Hasło** podaj hasło dla tego konta, aby umożliwić usłudze Intune dostęp do serwera Exchange.

7. Wybierz polecenie **Połącz**.

   > [!NOTE]
   > Konfigurowanie połączenia może potrwać kilka minut.

Podczas konfigurowania program Exchange Connector zapisuje ustawienia serwera proxy, aby umożliwić dostęp do Internetu. Jeśli ustawienia serwera proxy zostaną zmienione, trzeba będzie skonfigurować ponownie program Exchange Connector w celu zastosowania zaktualizowanych ustawień serwera proxy dla programu Exchange Connector.

Po skonfigurowaniu połączenia w programie Exchange Connector urządzenia przenośne skojarzone z użytkownikami i zarządzane przez program Exchange zostaną automatycznie zsynchronizowane i dodane do programu Exchange Connector. Wykonanie synchronizacji może zająć trochę czasu.

> [!NOTE]
> Jeśli po zainstalowaniu lokalnego programu Exchange Connector połączenie z programem Exchange zostanie usunięte, musisz odinstalować lokalny program Exchange Connector z komputera, na którym został zainstalowany.



## <a name="install-connectors-for-multiple-exchange-organizations"></a>Instalowanie łączników dla wielu organizacji programu Exchange
Usługa Intune obsługuje wiele lokalnych łączników programu Exchange na subskrypcję. W przypadku dzierżawy z wieloma organizacjami programu Exchange można skonfigurować jeden łącznik dla każdej organizacji programu Exchange. 

W przypadku instalacji łączników umożliwiających łączenie się z wieloma organizacjami programu Exchange pobierz folder zip jeden raz i użyj go dla każdego instalowanego łącznika. Dla każdego dodatkowego łącznika wykonaj czynności opisane w poprzedniej sekcji, aby wyodrębnić i uruchomić program instalacyjny na serwerze w organizacji programu Exchange.

Wysoka dostępność, monitorowanie i funkcje ręcznej synchronizacji opisane w poniższych sekcjach są obsługiwane dla każdej organizacji programu Exchange połączonej z usługą Intune.

## <a name="on-premises-exchange-connector-high-availability-support"></a>Obsługa wysokiej dostępności łącznika lokalnego programu Exchange 
Wysoka dostępność lokalnego programu Exchange Connector oznacza, że jeśli serwer dostępu klienta Exchange używany przez łącznik stanie się niedostępny, nastąpi przełączenie do innego serwera dostępu klienta dla tej organizacji programu Exchange. Sam program Exchange Connector nie obsługuje wysokiej dostępności. W przypadku awarii łącznika nie nastąpi automatyczne przełączenie do trybu failover. Należy [zainstalować nowy łącznik](#reinstall-the-on-premises-exchange-connector). 

Aby zapewnić tryb failover, po nawiązaniu połączenia z programem Exchange za pomocą wskazanego serwera dostępu klienta łącznik wykrywa dodatkowe serwery dostępu klienta dla tej organizacji programu Exchange. Umożliwia to łącznikowi przełączenie się do trybu failover na innym serwerze dostępu klienta (jeśli jest dostępny). Inny serwer jest używany do momentu przywrócenia dostępności podstawowego serwera dostępu klienta. Domyślnie odnajdywanie dodatkowych serwerów dostępu klienta jest włączone. Tryb failover można wyłączyć, korzystając z następującej procedury:  
1. Na serwerze, na którym jest zainstalowany program Exchange Connector, przejdź do folderu %*ProgramData*%\Microsoft\Windows Intune Exchange Connector. 
2. Za pomocą edytora tekstów otwórz plik **OnPremisesExchangeConnectorServiceConfiguration.xml**.
3. Zastąp ciąg &lt;IsCasFailoverEnabled&gt;**true**&lt;/IsCasFailoverEnabled&gt; ciągiem &lt;IsCasFailoverEnabled&gt;**false**&lt;/IsCasFailoverEnabled&gt;, aby wyłączyć tę funkcję.    
 

## <a name="reinstall-the-on-premises-exchange-connector"></a>Ponowne instalowanie lokalnego programu Exchange Connector
Może być konieczne ponowne zainstalowanie łącznika programu Exchange. Ponieważ do łączenia się z daną organizacją programu Exchange można używać jednego łącznika, jeśli zainstalujesz drugi łącznik, zastąpi on pierwotny łącznik.

1. Aby rozpocząć instalację nowego łącznika, postępuj zgodnie z procedurą [Instalowanie i konfigurowanie lokalnego programu Exchange Connector w usłudze Intune](#install-and-configure-the-intune-on-premises-exchange-connector). 
2. Po wyświetleniu monitu wybierz pozycję **Zastąp**, aby zainstalować nowy łącznik.  
   ![Monit konfiguracyjny o zastąpienie łącznika](./media/exchange-connector-install/prompt-to-replace.png)

3. Kolejne czynności wykonaj zgodnie z powyższą procedurą i ponownie zaloguj się do usługi Intune.
4. Na ostatnim ekranie wybierz pozycję **Zamknij**, aby zakończyć instalację.  
   ![Kończenie instalacji](./media/exchange-connector-install/successful-reinstall.png)
 

## <a name="monitor-the-exchange-connector-activity"></a>Monitorowanie działania łącznika programu Exchange

Po pomyślnym skonfigurowaniu programu Exchange Connector można wyświetlić stan połączeń oraz ostatniej pomyślnej próby synchronizacji. Aby zweryfikować połączenie programu Exchange Connector:

1. Na pulpicie nawigacyjnym usługi Intune wybierz pozycję **Dostęp do programu Exchange**.
2. Wybierz pozycję **Dostęp do lokalnego programu Exchange**, aby sprawdzić stan połączenia dla każdego łącznika programu Exchange.

Możesz również sprawdzić godzinę i datę ostatniej pomyślnej próby synchronizacji.
--> 

### <a name="system-center-operations-manager-management-pack"></a>Pakiet administracyjny programu System Center Operations Manager

Począwszy od wersji 1710 usługi Intune, można korzystać z [pakietu administracyjnego programu Operations Manager dla łącznika programu Exchange oraz usługi Intune](https://www.microsoft.com/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True). Pakiet administracyjny udostępnia różne sposoby monitorowania łącznika programu Exchange w przypadku konieczności rozwiązywania problemów.

## <a name="manually-force-a-quick-sync-or-full-sync"></a>Ręczne wymuszanie szybkiej synchronizacji lub pełnej synchronizacji
Lokalny program Exchange Connect regularnie i automatycznie synchronizuje rekordy protokołu EAS i urządzeń usługi Intune. W przypadku zmiany stanu zgodności urządzenia automatyczny proces synchronizacji regularnie zaktualizuje rekordy tak, aby dostęp urządzenia został odpowiednio umożliwiony lub zablokowany.

   - **Szybka synchronizacja** jest przeprowadzana regularnie kilka razy dziennie. Podczas szybkiej synchronizacji są pobierane informacje o urządzeniach związane z użytkownikami z licencją usługi Intune i dostępem warunkowym lokalnego programu Exchange, które uległy zmianie od ostatniej synchronizacji.

   - **Pełna synchronizacja** jest domyślnie przeprowadzana raz dziennie. Podczas pełnej synchronizacji są pobierane informacje o urządzeniach związane ze wszystkimi użytkownikami z licencją usługi Intune i dostępem warunkowym lokalnego programu Exchange. Pełna synchronizacja polega również na pobieraniu informacji o serwerze programu Exchange i zapewnianiu, że konfiguracja określona przez usługę Intune w witrynie Azure Portal została zaktualizowana na serwerze programu Exchange. 


Aby wymusić uruchomienie synchronizacji przez łącznik, można użyć opcji **Szybka synchronizacja** lub **Pełna synchronizacja** na pulpicie nawigacyjnym usługi Intune i wykonać następujące kroki:

   1. Na pulpicie nawigacyjnym usługi Intune wybierz pozycję **Dostęp do programu Exchange**.
   2. Wybierz pozycję **Dostęp do lokalnego programu Exchange**.
   3. Wybierz łącznik do zsynchronizowania, a następnie wybierz pozycję **Szybka synchronizacja** lub **Pełna synchronizacja**.

## <a name="next-steps"></a>Następne kroki
[Tworzenie zasad dostępu warunkowego dla lokalnego programu Exchange](conditional-access-exchange-create.md)
