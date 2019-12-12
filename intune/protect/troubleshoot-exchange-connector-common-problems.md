---
title: Rozwiązywanie typowych problemów z programem Intune Exchange Connector
titleSuffix: Microsoft Intune
description: Rozwiązywanie problemów i rozwiązywanie typowych problemów dotyczących lokalnego łącznika programu Exchange Microsoft Intune.
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/26/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: de365312a7d293527c3c83fbbd84ab55de41d530
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "74547670"
---
# <a name="resolve-common-problems-with-the-intune-exchange-connector"></a>Rozwiązywanie typowych problemów z programem Intune Exchange Connector
 
Ten artykuł może pomóc administratorowi usługi Intune rozwiązać typowe problemy związane z działaniem programu Intune Exchange Connector.

Przed rozpoczęciem rozwiązywania problemów przejrzyj temat [Rozwiązywanie problemów z lokalnym programem Exchange Connector usługi Intune,](troubleshoot-exchange-connector.md) Aby uzyskać podstawowe informacje o łączniku. Przejrzyj również typowe problemy związane z konfiguracją łącznika.

## <a name="an-exchange-activesync-device-isnt-discovered-from-exchange"></a>Urządzenie z programem Exchange ActiveSync nie jest wykrywane za pomocą programu Exchange

Jeśli urządzenie Exchange ActiveSync nie zostanie wykryte z programu Exchange, [Monitoruj działanie programu Exchange Connector](exchange-connector-install.md#on-premises-intune-exchange-connector-high-availability-support) , aby sprawdzić, czy program Exchange Connector jest synchronizowany z serwerem Exchange. Jeśli nie nastąpiła żadna synchronizacja od momentu przyłączenia urządzenia, Zbierz dzienniki synchronizacji i Dołącz je do żądania obsługi. Jeśli pełna synchronizacja lub szybka synchronizacja zakończyła się pomyślnie od momentu przyłączenia urządzenia, sprawdź następujące problemy:

- Upewnij się, że użytkownicy mają licencję usługi Intune. W przeciwnym razie program Exchange Connector nie odnajdzie swoich urządzeń.

- Jeśli podstawowy adres SMTP użytkownika różni się od głównej nazwy użytkownika (UPN) w usłudze Azure Active Directory (Azure AD), program Exchange Connector nie wykryje żadnych urządzeń dla tego użytkownika. Popraw podstawowy adres SMTP w celu rozwiązania problemu.

- Jeśli w środowisku znajdują się serwery skrzynek pocztowych zarówno programu Exchange 2010, jak i programu Exchange 2013, zalecamy skierowanie programu Exchange Connector do serwera CAS programu Exchange 2013. Jeśli program Exchange Connector jest skonfigurowany pod kątem komunikowania się z serwerem CAS programu Exchange 2010, nie odnajdzie żadnych urządzeń użytkowników programu Exchange 2013.

- W przypadku środowisk usługi Exchange Online w wersji dedykowanej należy wskazać program Exchange Connector do urzędów certyfikacji programu Exchange 2013 (a nie urzędów certyfikacji programu Exchange 2010) w środowisku dedykowanym podczas początkowej konfiguracji. Łącznik będzie komunikować się tylko z urzędami certyfikacji programu Exchange 2013 podczas wykonywania poleceń cmdlet programu PowerShell.

## <a name="problems-with-the-notification-email-message"></a>Problemy z wiadomością e-mail z powiadomieniem

Aby zapewnić obsługę dostępu warunkowego dla lokalnych skrzynek pocztowych na urządzeniach, na których nie jest uruchomiony system Android Knox, upewnij się, że rejestracja w usłudze Intune rozpoczyna się od wiadomości e-mail "Rozpocznij teraz" wysyłanej przez program Intune Exchange Connector. Uruchomienie rejestracji z poziomu komunikatu zapewnia, że urządzenie otrzymuje unikatowy ActiveSyncID na wszystkich platformach (Exchange, Azure AD, Intune).

Użytkownik może nie otrzymać wiadomości e-mail z powiadomieniem, ponieważ:

- Konto powiadomień zostało nieprawidłowo skonfigurowane.
- Nie można przeprowadzić wykrywania automatycznego dla konta powiadomień.
- Żądanie wysłania wiadomości e-mail przez usługi programu Exchange Web Services (EWS) nie powiodło się.

Zapoznaj się z następującymi sekcjami, aby rozwiązać problemy z powiadomieniami e-mail.

### <a name="check-the-notification-account-that-retrieves-autodiscover-settings"></a>Sprawdź konto powiadomień, które pobiera ustawienia wykrywania automatycznego

1. Upewnij się, że usługa wykrywania automatycznego i usługi EWS zostały skonfigurowane w usługach dostępu klienta programu Exchange. Aby uzyskać więcej informacji, zobacz [usługi dostępu klienta](https://docs.microsoft.com/Exchange/architecture/client-access/client-access) i [Usługa wykrywania automatycznego w programie Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/autodiscover?view=exchserver-2019).

2. Sprawdź, czy konto powiadomienia spełnia następujące wymagania:

   - Konto ma aktywną skrzynkę pocztową hostowaną na serwerze lokalnym programu Exchange.

   - Nazwa UPN konta jest zgodna z adresem SMTP.

3. Element wykrywania automatycznego wymaga serwera DNS z rekordem DNS dla **Autodiscover.SMTPdomain.com** (na przykład Autodiscover.contoso.com), który wskazuje serwer dostępu klienta programu Exchange. Aby sprawdzić rekord, określ nazwę FQDN zamiast *Autodiscover.SMTPdomain.com* i wykonaj następujące kroki:

   1. W wierszu polecenia wpisz polecenie *nslookup*.

   2. Wprowadź *Autodiscover.SMTPdomain.com*. Dane wyjściowe powinny wyglądać podobnie jak na poniższym obrazie: ![nslookup wyniki](./media/troubleshoot-exchange-connector-common-problems/nslookup-results.png
      )

   Usługę wykrywania automatycznego można testować również z Internetu w https://testconnectivity.microsoft.com. Lub przetestuj ją z domeny lokalnej za pomocą narzędzia Microsoft Connectivity Analyzer. Aby uzyskać więcej informacji, zobacz [Narzędzie Analizator łączności Microsoft](https://docs.microsoft.com/previous-versions/office/exchange-remote-connectivity/jj851141(v=exchg.80)).


### <a name="check-autodiscovery"></a>Sprawdź Autowykrywanie

W przypadku niepowodzenia wykrywania awaryjnego spróbuj wykonać następujące czynności:

1. [Skonfiguruj prawidłowy rekord DNS wykrywania automatycznego](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/mt473798(v=exchg.150)).

2. Twarde kodowanie adresu URL EWS w pliku konfiguracji łącznika usługi Intune Exchange:

   1. Określ adres URL EWS. Domyślny adres URL EWS dla programu Exchange to `https://<mailServerFQDN>/ews/exchange.asmx`, ale adres URL może się różnić. Skontaktuj się z administratorem programu Exchange, aby zweryfikować prawidłowy adres URL dla danego środowiska.

   2. Edytuj plik *OnPremisesExchangeConnectorServiceConfiguration.xml*. Domyślnie plik znajduje się w *%ProgramData%\Microsoft\Windows Intune Exchange Connector* na komputerze, na którym jest uruchomiony program Exchange Connector. Otwórz plik w edytorze tekstów, a następnie zmień następujący wiersz, aby odzwierciedlić adres URL EWS środowiska: `<ExchangeWebServiceURL> https://<YourExchangeHOST>/EWS/Exchange.asmx</ExchangeWebServiceURL>`

3. Zapisz plik, a następnie uruchom ponownie komputer lub usługę Microsoft Intune Exchange Connector.

>[!NOTE]
> W tej konfiguracji łącznik usługi Intune Exchange przestaje używać wykrywania, a zamiast tego nawiązuje połączenie bezpośrednio z adresem URL EWS.

## <a name="next-steps"></a>Następne kroki

Aby uzyskać pomoc dotyczącą określonych błędów, spróbuj [rozwiązać typowe błędy dla programu Intune Exchange Connector](troubleshoot-exchange-connector-common-errors.md).

Aby uzyskać pomoc techniczną lub uzyskać dostęp do pomocy społeczności usługi Intune:

- Zobacz [Uzyskaj pomoc techniczną](../fundamentals/get-support.md) , aby skorzystać z konsoli usługi Intune w celu rozwiązania problemu lub otwarcia zgłoszenia do pomocy technicznej w firmie Microsoft.
- Opublikuj swój problem na [forach Microsoft Intune](https://social.technet.microsoft.com/Forums/home?forum=microsoftintuneprod).