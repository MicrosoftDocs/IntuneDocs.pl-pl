---
title: Program Exchange Connector dla lokalnego programu EAS
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: użycie narzędzia Connector w celu umożliwienia komunikacji między konsolą administracyjną usługi Intune a lokalnym serwerem programu Exchange na potrzeby funkcji zarządzania urządzeniami przenośnymi programu Exchange ActiveSync"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 317b88e289fce216916dfa4ec3890ba7c9559c16
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="install-the-intune-on-premises-exchange-connector-in-microsoft-intune-azure-preview"></a>Instalowanie programu Intune On-premises Exchange Connector w wersji zapoznawczej usługi Microsoft Intune Azure

[!INCLUDE[azure_preview](./includes/azure_preview.md)]


Aby skonfigurować połączenie, które umożliwia usłudze Microsoft Intune komunikację z serwerem Exchange hostującym skrzynki pocztowe używane na urządzeniach przenośnych, musisz pobrać i skonfigurować narzędzie On-Premises Exchange Connector za pomocą konsoli administracyjnej usługi Intune. W ramach jednej subskrypcji usługa Intune obsługuje tylko jedno połączenie programu Exchange Connector dowolnego typu.

## <a name="on-premises-exchange-connector-requirements"></a>Wymagania dotyczące programu On-premises Exchange Connector
Poniższa tabela zawiera listę wymagań dotyczących komputera, na którym ma być instalowany program On-premises Exchange Connector.

|Wymaganie|Więcej informacji|
|---------------|--------------------|
|Systemy operacyjne|Usługa Intune obsługuje program On-premises Exchange Connector na komputerach z dowolną wersją systemu Windows Server 2008 SP2 (64-bitową), Windows Server 2008 R2, Windows Server 2012 i Windows Server 2012 R2.<br /><br />Program Connector nie jest obsługiwany w żadnej instalacji Server Core.|
|Microsoft Exchange|Lokalne łączniki wymagają programu Microsoft Exchange 2010 z dodatkiem SP1 lub jego nowszej wersji albo starszej wersji środowiska usługi Exchange Online w wersji dedykowanej. Aby ustalić, czy środowisko usługi Exchange Online w wersji dedykowanej zawiera **nową** czy **starszą** konfigurację, skontaktuj się z menedżerem ds. klientów.|
|Urząd zarządzania urządzeniami przenośnymi| [Konfigurowanie usługi Intune jako urzędu zarządzania urządzeniami przenośnymi](https://docs.microsoft.com/intune-classic/deploy-use/prerequisites-for-enrollment#step-2-mdm-authority-set).|
|Sprzęt|Komputer, na którym jest instalowany łącznik, wymaga co najmniej procesora CPU 1,6 GHz z 2 GB pamięci RAM oraz 10 GB wolnego miejsca na dysku.|
|Synchronizacja z usługą Active Directory|Zanim będzie możliwe połączenie usługi Intune z programem Exchange Server przy użyciu programu Connector, należy [skonfigurować synchronizację usługi Active Directory](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3), aby zapewnić synchronizację lokalnych użytkowników i grup zabezpieczeń z wystąpieniem usługi Azure Active Directory.|
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

1. W obsługiwanym systemie operacyjnym Windows Server dla lokalnego programu Exchange Connector otwórz [witrynę Azure Portal](http://portal.azure.com) przy użyciu konta użytkownika, który jest administratorem dzierżawy programu Exchange i ma licencję na korzystanie z serwera programu Exchange.

2.  Wybierz obciążenie **Dostęp warunkowy**.
3.  Wybierz obciążenie **Dostęp warunkowy** w portalu Azure Portal, aby otworzyć blok **lokalny**.

4. W sekcji **Instalacja** wybierz pozycję **Lokalny łącznik Exchange ActiveSync** i wybierz polecenie **Pobierz łącznik lokalny**.

4.  Program On-Premises Exchange Connector znajduje się w skompresowanym folderze (pliku zip), który można otworzyć lub zapisać. W oknie dialogowym **Pobieranie pliku** wybierz polecenie **Zapisz**, aby zapisać skompresowany folder w bezpiecznej lokalizacji.

> [!IMPORTANT]
> Nie zmieniaj nazwy ani nie przenoś plików znajdujących się w folderze programu On-Premises Exchange Connector. Przeniesienie lub zmiana nazwy zawartości folderu spowoduje niepowodzenie instalacji.

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

Konfigurowanie połączenia może potrwać kilka minut.

Podczas konfigurowania program Exchange Connector zapisuje ustawienia serwera proxy, aby umożliwić dostęp do Internetu. Jeśli ustawienia serwera proxy zostaną zmienione, będzie trzeba skonfigurować ponownie program Exchange Connector w celu zastosowania zaktualizowanych ustawień serwera proxy dla programu Exchange Connector.

Po skonfigurowaniu połączenia w programie Exchange Connector urządzenia przenośne skojarzone z użytkownikami i zarządzane przez program Exchange Connector zostaną automatycznie zsynchronizowane i dodane do programu Exchange Connector. Wykonanie synchronizacji może zająć trochę czasu.

> [!NOTE]
> Jeśli po zainstalowaniu łącznika On-Premises Exchange Connector połączenie z programem Exchange zostanie usunięte, musisz odinstalować łącznik On-Premises Exchange Connector z komputera, na którym został zainstalowany.

## <a name="validate-the-exchange-connection"></a>Weryfikacja połączenia z programem Exchange

Po pomyślnym skonfigurowaniu programu Exchange Connector można wyświetlić stan połączenia oraz ostatniej pomyślnej próby synchronizacji. W witrynie [Azure Portal](http://portal.azure.com) wybierz obciążenie **Intune** > **Dostęp warunkowy**. W obszarze **Instalacja** wybierz lokalny łącznik **Exchange on-premises connector** i sprawdź, czy jest on wyświetlany jako aktywny.

Możesz również sprawdzić godzinę i datę ostatniej pomyślnej próby synchronizacji.

## <a name="next-steps"></a>Następne kroki
[Tworzenie zasad dostępu warunkowego dla lokalnego programu Exchange](conditional-access-exchange-create.md)

