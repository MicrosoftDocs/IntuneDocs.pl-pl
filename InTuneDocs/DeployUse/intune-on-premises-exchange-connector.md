---
# required metadata

title: Instalowanie łącznika Microsoft Intune Exchange Connector dla lokalnej instalacji programu Exchange | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 41ff4212-a6f5-4374-8731-631f7560cff1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Instalowanie lokalnego łącznika Intune Exchange Connector


Aby skonfigurować połączenie, które umożliwia usłudze Microsoft Intune komunikację z serwerem Exchange hostującym skrzynki pocztowe urządzeń przenośnych, musisz pobrać i skonfigurować narzędzie On-Premises Connector w konsoli administracyjnej usługi Intune.

## Wymagania dotyczące łącznika On-Premises Connector
Poniższa tabela zawiera listę wymagań dotyczących komputera, na którym ma być instalowany lokalny łącznik Exchange Connector.

|Wymaganie|Więcej informacji|
|---------------|--------------------|
|Systemy operacyjne|Usługa Intune obsługuje lokalny łącznik Exchange Connector na komputerach z dowolną wersją systemu Windows Server 2008 SP2 (64 bity), Windows Server 2008 R2, Windows Server 2012 lub Windows Server 2012 R2.<br /><br />Łącznik nie jest obsługiwany w żadnej instalacji Server Core.|
|Wersja programu Microsoft Exchange|Lokalny łącznik On-Premises Connector wymaga programu Microsoft Exchange 2010 z dodatkiem SP1 lub nowszej wersji.|
|Urząd zarządzania urządzeniami przenośnymi| [Konfigurowanie usługi Intune jako urzędu zarządzania urządzeniami przenośnymi](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority).|
|Sprzęt|Komputer, na którym jest instalowany łącznik, wymaga co najmniej procesora CPU 1,6 GHz z 2 GB pamięci RAM oraz 10 GB wolnego miejsca na dysku.|
|Synchronizacja z usługą Active Directory|Zanim będzie możliwe połączenie usługi Intune z programem Exchange Server przy użyciu dowolnego z łączników, należy [skonfigurować synchronizację usługi Active Directory](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3), aby zapewnić synchronizację lokalnych użytkowników i grup zabezpieczeń z wystąpieniem usługi Azure Active Directory.|
|Dodatkowe oprogramowanie|Na komputerze, który będzie hostem łącznika, musi być zainstalowana pełna instalacja platformy Microsoft .NET Framework 4 i programu Windows PowerShell 2.0.|
|Sieć|Komputer, na którym ma być instalowany łącznik, musi należeć do domeny, która ma relację zaufania z domeną hostującą program Exchange Server.<br /><br />Komputer wymaga zastosowania konfiguracji umożliwiającej mu dostęp do usługi Intune za pośrednictwem zapór i serwerów proxy przez porty 80 i 443. Domeny używane przez usługę Intune obejmują manage.microsoft.com, &#42;manage.microsoft.com i &#42;.manage.microsoft.com.|
|Hostowany program Exchange — skonfigurowany i uruchomiony|Aby uzyskać więcej informacji, zobacz temat [Exchange Server 2016](https://technet.microsoft.com/library/mt170645.aspx). |
|Konfigurowanie usługi Intune jako urzędu zarządzania urządzeniami przenośnymi|[Konfigurowanie usługi Intune jako urzędu zarządzania urządzeniami przenośnymi](get-ready-to-enroll-devices-in-microsoft-intune.md#BKMK_Set_MDM_Authority)|

### Wymagania poleceń cmdlet programu Exchange

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

## Aby pobrać pakiet instalacyjny lokalnego łącznika On-Premises Exchange Connector

1. W obsługiwanym systemie operacyjnym dla lokalnego łącznika Exchange Connector otwórz [konsolę administracyjną Microsoft Intune](http://manage.microsoft.com) (http://manage.microsoft.com) przy użyciu konta użytkownika, który jest administratorem dzierżawy programu Exchange z licencją do korzystania z serwera Exchange Server.
![Otwórz konfigurację połączenia z programem Exchange.](../media/ExchangeConnector.gif)

2.  W okienku skrótów obszaru roboczego wybierz opcję **ADMINISTRACJA**.

3.  W okienku nawigacji w obszarze **Zarządzanie urządzeniami przenośnymi** rozwiń pozycję **Microsoft Exchange**, a następnie wybierz polecenie **Skonfiguruj połączenie z programem Exchange**.

4.  Na stronie **Konfigurowanie połączenia z programem Exchange** wybierz polecenie **Pobierz program On-Premises Connector**.

5.  Program On-Premises Exchange Connector znajduje się w skompresowanym folderze (pliku zip), który można otworzyć lub zapisać. W oknie dialogowym **Pobieranie pliku** wybierz polecenie **Zapisz**, aby zapisać skompresowany folder w bezpiecznej lokalizacji.

> [!IMPORTANT]
> Nie zmieniaj nazwy ani nie przenoś plików w folderze programu On-Premises Exchange Connector. Przeniesienie lub zmiana nazwy zawartości folderu spowoduje przerwanie instalacji.

## Instalowanie i konfigurowanie lokalnego łącznika Intune Exchange Connector
Wykonaj następujące kroki, aby zainstalować łącznik On-Premises Exchange Connector usługi Intune. Łącznik On-Premises Exchange Connector można zainstalować tylko raz dla danej subskrypcji usługi Intune i tylko na jednym komputerze. Próba skonfigurowania dodatkowego łącznika On-Premises Exchange Connector spowoduje zastąpienie oryginalnego połączenia nowym.

1.  W obsługiwanym systemie operacyjnym dla łącznika lokalnego wyodrębnij pliki z archiwum **Exchange_Connector_Setup.zip** w bezpiecznej lokalizacji.

2.  Po wyodrębnieniu plików otwórz wyodrębniony folder i kliknij dwukrotnie plik **Exchange_Connector_Setup.exe**, aby zainstalować łącznik On-Premises Exchange Connector.

    > [!IMPORTANT]
    > Jeśli folder docelowy nie jest bezpieczną lokalizacją, usuń plik certyfikatu **WindowsIntune.accountcert** po zainstalowaniu łącznika On-Premises Connector.

3.  W polu **Serwer Exchange** wybierz typ środowiska serwera Exchange: **Lokalny serwer Microsoft Exchange** lub **Hostowany serwer Microsoft Exchange**..

  ![Wybierz typ serwera Exchange Server](../media/IntuneSA1dconfigureExchConnector.png)

  W przypadku lokalnego serwera Exchange podaj nazwę lub w pełni kwalifikowaną nazwę domeny serwera Exchange, który hostuje rolę **serwera Dostęp klienta**.

  W przypadku hostowanego serwera Exchange podaj adres serwera Exchange. Aby określić adres URL hostowanego serwera Exchange:

      1.  Otwórz aplikację Outlook Web App for Office 365.

      2.  Wybierz ikonę „?” w lewym górnym rogu i wybierz pozycję **Informacje**.

      3.  Znajdź wartość **Zewnętrzny serwer protokołu POP** .

      4.  Wybierz pozycję **Serwer proxy**, aby określić ustawienia serwera proxy dla hostowanego serwera Exchange.
        1.  Wybierz opcję **Użyj serwera proxy podczas synchronizacji informacji o urządzeniu przenośnym**.

        2.  W polach **Nazwa serwera proxy** i **Numer portu** podaj wartości, które mają być używane na potrzeby dostępu do serwera.

        3.  Jeśli dostęp do serwera proxy wymaga podania poświadczeń użytkownika, wybierz pozycję Użyj poświadczeń do nawiązania połączenia z serwerem proxy i podaj wartości w polach **Domena\nazwa_użytkownika** oraz **Hasło**..

        4.  Wybierz przycisk **OK**..

5.  Podaj poświadczenia, **Nazwę użytkownika (domena\nazwa_użytkownika)** i **Hasło** wymagane do nawiązania połączenia z serwerem Exchange.

6.  Podaj poświadczenia administracyjne, które są niezbędne do wysyłania powiadomień do skrzynek pocztowych użytkowników w programie Exchange. Te powiadomienia można konfigurować za pomocą zasad dostępu warunkowego przy użyciu usługi Intune.

    Upewnij się, że usługa wykrywania automatycznego i usługi sieci Web programu Exchange są skonfigurowane na serwerze dostępu klienta programu Exchange. Aby uzyskać więcej informacji na ten temat, zapoznaj się z artykułem na temat [serwera dostępu klienta](https://technet.microsoft.com/library/dd298114.aspx).

7.  W polu **Hasło** podaj hasło dla tego konta, aby umożliwić usłudze Intune dostęp do serwera Exchange.

8. Wybierz polecenie **Połącz**.

    Konfigurowanie połączenia może zająć kilka minut.

Podczas konfigurowania program Exchange Connector zapisuje ustawienia serwera proxy, aby umożliwić dostęp do Internetu. Jeśli ustawienia serwera proxy zostaną zmienione, musisz skonfigurować ponownie program Exchange Connector w celu zastosowania zaktualizowanych ustawień serwera proxy dla programu Exchange Connector.

Po skonfigurowaniu połączenia przez program Exchange Connector urządzenia przenośne skojarzone z użytkownikami i zarządzane przez program Exchange Connector zostaną automatycznie zsynchronizowane i dodane do programu Exchange Connector. Wykonanie synchronizacji może zająć trochę czasu.

> [!NOTE]
> Jeśli po zainstalowaniu łącznika On-Premises Exchange Connector połączenie z programem Exchange zostanie usunięte, musisz odinstalować łącznik On-Premises Exchange Connector z komputera, na którym został zainstalowany.

## Weryfikacja połączenia z programem Exchange

Po pomyślnym skonfigurowaniu programu Exchange Connector można wyświetlić stan połączenia oraz ostatniej pomyślnej próby synchronizacji. W [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) wybierz obszar roboczy **ADMINISTRACJA** i w sekcji **Zarządzanie urządzeniami przenośnymi** wybierz pozycję **Microsoft Exchange**, a następnie sprawdź, czy podane szczegółowe informacje są wyświetlane w polu **Informacje o połączeniu z programem Exchange**.


Możesz również sprawdzić godzinę i datę ostatniej pomyślnej próby synchronizacji.


<!--HONumber=May16_HO1-->


