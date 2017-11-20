---
title: "Konfigurowanie łącznika Exchange dla lokalnego programu EAS w usłudze Intune"
titleSuffix: Azure portal
description: "Użycie łącznika w celu umożliwienia komunikacji między usługą Intune a lokalnym serwerem Exchange"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c7947c9d047c6f206f9f93c389d418379fe8267a
ms.sourcegitcommit: 5279a0bb8c5aef79aa57aa247ad95888ffe5a12b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/08/2017
---
# <a name="set-up-the-intune-on-premises-exchange-connector-in-microsoft-intune-azure"></a>Konfigurowanie lokalnego programu Exchange Connector w usłudze Microsoft Intune Azure

Lokalne środowiska serwera Exchange mogą używać programu On-premises Exchange Connector w celu zarządzania dostępem urządzeń do skrzynek pocztowych Exchange w oparciu o to, czy urządzenia są zarejestrowane w usłudze Intune i spełniają zasady zgodności w usłudze Intune. Program On-premises Exchange Connector odpowiada także za odnajdywanie urządzeń mobilnych łączących się z lokalnymi serwerami programu Exchange poprzez synchronizowanie istniejącego rekordu programu Exchange Active Sync (EAS) z usługą Intune.

> [!IMPORTANT]
> Usługa Intune obsługuje tylko jedno połączenie programu On-premises Exchange Connector dowolnego typu w ramach jednej subskrypcji.

Aby skonfigurować połączenie, które umożliwi usłudze Microsoft Intune komunikowanie się z lokalnym serwerem Exchange, konieczne jest wykonanie następujących czynności:

1.  Pobranie programu On-premises Exchange Connector dla usługi Intune z witryny Azure Portal.
2.  Zainstalowanie i skonfigurowanie programu On-premises Exchange Connector dla usługi Intune.
3.  Sprawdzenie działania połączenia z serwerem Exchange.

## <a name="on-premises-exchange-connector-requirements"></a>Wymagania dotyczące programu On-premises Exchange Connector
Poniższa tabela zawiera listę wymagań dotyczących komputera, na którym ma być instalowany program On-premises Exchange Connector.

|Wymaganie|Więcej informacji|
|---------------|--------------------|
|Systemy operacyjne|Usługa Intune obsługuje program On-premises Exchange Connector na komputerach z dowolną wersją systemu Windows Server 2008 SP2 (64-bitową), Windows Server 2008 R2, Windows Server 2012 i Windows Server 2012 R2.<br /><br />Program Connector nie jest obsługiwany w żadnej instalacji Server Core.|
|Microsoft Exchange|Lokalne łączniki wymagają programu Microsoft Exchange 2010 z dodatkiem SP1 lub jego nowszej wersji albo starszej wersji środowiska usługi Exchange Online w wersji dedykowanej. Aby ustalić, czy środowisko usługi Exchange Online w wersji dedykowanej zawiera **nową** czy **starszą** konfigurację, skontaktuj się z menedżerem ds. klientów.|
|Urząd zarządzania urządzeniami przenośnymi| [Konfigurowanie usługi Intune jako urzędu zarządzania urządzeniami przenośnymi](https://docs.microsoft.com/intune-classic/deploy-use/prerequisites-for-enrollment#step-2-mdm-authority-set).|
|Sprzęt|Komputer, na którym jest instalowany łącznik, wymaga co najmniej procesora CPU 1,6 GHz z 2 GB pamięci RAM oraz 10 GB wolnego miejsca na dysku.|users-add.md
|Synchronizacja z usługą Active Directory|Zanim będzie możliwe połączenie usługi Intune z programem Exchange Server przy użyciu programu Connector, należy [skonfigurować synchronizację usługi Active Directory](users-add.md), aby zapewnić synchronizację lokalnych użytkowników i grup zabezpieczeń z wystąpieniem usługi Azure Active Directory.|
|Dodatkowe oprogramowanie|Na komputerze, który będzie hostem łącznika, musi być wdrożona pełna instalacja platformy Microsoft .NET Framework 4.5 i programu Windows PowerShell 2.0.|
|Sieć|Komputer, na którym ma być instalowany łącznik, musi należeć do domeny, która ma relację zaufania z domeną hostującą program Exchange Server.<br /><br />Komputer wymaga zastosowania konfiguracji umożliwiającej mu dostęp do usługi Intune za pośrednictwem zapór i serwerów proxy przez porty 80 i 443. Domeny używane przez usługę Intune obejmują manage.microsoft.com, &#42;manage.microsoft.com i &#42;.manage.microsoft.com.|


### <a name="exchange-cmdlet-requirements"></a>Wymagania poleceń cmdlet programu Exchange

Musisz utworzyć konto użytkownika usługi Active Directory, które będzie używane przez program Exchange Connector usługi Intune. Konto musi mieć uprawnienia do uruchamiania następujących wymaganych poleceń cmdlet programu Exchange w środowisku Windows PowerShell:


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

## <a name="download-the-on-premises-exchange-connector-software-installation-package"></a>Pobieranie pakietu instalacyjnego programu On-premises Exchange Connector

1. W obsługiwanym systemie operacyjnym Windows Server dla lokalnego programu On-premises Exchange Connector otwórz [witrynę Azure Portal](http://portal.azure.com) przy użyciu konta użytkownika, który jest administratorem lokalnego serwera Exchange i ma licencję na korzystanie z programu Exchange Server.

2. W menu po lewej stronie wybierz pozycję **Więcej usług**, a następnie w filtrze pola tekstowego wpisz **Intune**.

3. Wybierz pozycję **Intune**, a po otwarciu pulpitu nawigacyjnego usługi Intune wybierz opcję **Dostęp lokalny**.

4. W bloku **Dostęp lokalny — łącznik Exchange ActiveSync** w sekcji **Konfiguracja** wybierz polecenie **Pobierz łącznik lokalny**.

5.  Program On-Premises Exchange Connector znajduje się w skompresowanym folderze (pliku zip), który można otworzyć lub zapisać. W oknie dialogowym **Pobieranie pliku** wybierz polecenie **Zapisz**, aby zapisać skompresowany folder w bezpiecznej lokalizacji.

    > [!IMPORTANT]
    > Nie zmieniaj nazwy ani nie przenoś plików znajdujących się w folderze programu On-premises Exchange Connector. Przeniesienie lub zmiana nazwy zawartości folderu spowoduje niepowodzenie instalacji łącznika programu Exchange.

## <a name="install-and-configure-the-intune-on-premises-exchange-connector"></a>Instalowanie i konfigurowanie programu Intune On-premises Exchange Connector
Wykonaj następujące kroki, aby zainstalować program Intune On-Premises Exchange Connector. Program On-Premises Exchange Connector można zainstalować tylko raz dla danej subskrypcji usługi Intune i tylko na jednym komputerze. Skonfigurowanie dodatkowego łącznika On-Premises Exchange Connector spowoduje zastąpienie oryginalnego połączenia nowym.

1.  W obsługiwanym systemie operacyjnym dla łącznika lokalnego wyodrębnij pliki z archiwum **Exchange_Connector_Setup.zip** w bezpiecznej lokalizacji.

2.  Po wyodrębnieniu plików otwórz utworzony folder i kliknij dwukrotnie plik **Exchange_Connector_Setup.exe**, aby zainstalować łącznik On-Premises Exchange Connector.

    > [!IMPORTANT]
    > Jeśli folder docelowy nie znajduje się w bezpiecznej lokalizacji, usuń plik certyfikatu **WindowsIntune.accountcert** po zainstalowaniu łącznika On-Premises Connector.

3.  W oknie dialogowym **Microsoft Intune Exchange Connector** wybierz opcję **Lokalny program Microsoft Exchange Server** lub **Hostowany program Microsoft Exchange Server**.

  ![Wybierz typ serwera Exchange Server](./media/intune-sa-exchange-connector-config.png)

  W przypadku lokalnego serwera Exchange podaj jego nazwę lub w pełni kwalifikowaną nazwę domeny serwera Exchange, który hostuje rolę **serwera dostępu klienta**.

  W przypadku hostowanego serwera Exchange podaj adres serwera Exchange. Aby określić adres URL hostowanego serwera Exchange:

    1. Otwórz aplikację Outlook Web App for Office 365.

    2. Wybierz ikonę **?** w lewym górnym rogu, a następnie wybierz polecenie **Informacje**.

    3. Znajdź wartość **Zewnętrzny serwer protokołu POP** .

    4. Wybierz pozycję **Serwer proxy**, aby określić ustawienia serwera proxy dla hostowanego serwera Exchange.
        1. Wybierz opcję **Użyj serwera proxy podczas synchronizacji informacji o urządzeniu przenośnym**.

        2. W polach **Nazwa serwera proxy** i **Numer portu** podaj wartości, które mają być używane na potrzeby dostępu do serwera.

        3. Jeśli dostęp do serwera proxy wymaga podania poświadczeń użytkownika, wybierz pozycję **Użyj poświadczeń do nawiązania połączenia z serwerem proxy**. i podaj wartości w polach **Domena\nazwa_użytkownika** i **Hasło**.

        4. Wybierz przycisk **OK**.

    5. W polach **Nazwa użytkownika (domena\nazwa_użytkownika)** i **Hasło** podaj poświadczenia wymagane do nawiązania połączenia z serwerem Exchange.

    6.  Podaj poświadczenia administracyjne, które są niezbędne do wysyłania powiadomień do skrzynek pocztowych użytkowników w programie Exchange Server. Powiadomienia te można skonfigurować za pomocą reguł dostępu warunkowego w usłudze Intune.

        Upewnij się, że usługa wykrywania automatycznego i usługi sieci Web programu Exchange są skonfigurowane na serwerze dostępu klienta programu Exchange. Aby uzyskać więcej informacji na ten temat, zapoznaj się z artykułem [Client Access server](https://technet.microsoft.com/library/dd298114.aspx) (Serwer dostępu klienta).

    7.  W polu **Hasło** podaj hasło dla tego konta, aby umożliwić usłudze Intune dostęp do serwera Exchange.

    8. Wybierz polecenie **Połącz**.

    > [!NOTE]
    > Konfigurowanie połączenia może potrwać kilka minut.

Podczas konfigurowania program Exchange Connector zapisuje ustawienia serwera proxy, aby umożliwić dostęp do Internetu. Jeśli ustawienia serwera proxy zostaną zmienione, będzie trzeba skonfigurować ponownie program Exchange Connector w celu zastosowania zaktualizowanych ustawień serwera proxy dla programu Exchange Connector.

Po skonfigurowaniu połączenia w programie Exchange Connector urządzenia przenośne skojarzone z użytkownikami i zarządzane przez program Exchange Connector zostaną automatycznie zsynchronizowane i dodane do programu Exchange Connector. Wykonanie synchronizacji może zająć trochę czasu.

> [!NOTE]
> Jeśli po zainstalowaniu łącznika On-Premises Exchange Connector połączenie z programem Exchange zostanie usunięte, musisz odinstalować łącznik On-Premises Exchange Connector z komputera, na którym został zainstalowany.

## <a name="monitor-the-exchange-connector-activity"></a>Monitorowanie działania łącznika programu Exchange

Po pomyślnym skonfigurowaniu programu Exchange Connector można wyświetlić stan połączenia oraz ostatniej pomyślnej próby synchronizacji. Aby dokonać weryfikacji łącznika programu Exchange:

1. Na pulpicie nawigacyjnym usługi Intune wybierz pozycję **Dostęp warunkowy**.
2. W obszarze **Zarządzaj** wybierz pozycję **Dostęp do lokalnego wystąpienia programu Exchange**, aby sprawdzić stan połączenia.

Możesz również sprawdzić godzinę i datę ostatniej pomyślnej próby synchronizacji.

### <a name="system-center-operations-manager-scom-management-pack"></a>Pakiet administracyjny programu System Center Operations Manager (SCOM)

Począwszy od wersji 1710 usługi Intune, można korzystać z [pakietu administracyjnego programu SCOM dla łącznika programu Exchange oraz usługi Intune](https://www.microsoft.com/en-us/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True). Zapewnia on różne sposoby monitorowania łącznika programu Exchange w przypadku konieczności rozwiązywania problemów.

## <a name="next-steps"></a>Następne kroki
[Tworzenie zasad dostępu warunkowego dla lokalnego programu Exchange](conditional-access-exchange-create.md)
