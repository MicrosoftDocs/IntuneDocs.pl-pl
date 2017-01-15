---
title: "Rozwiązywanie problemów z programem Exchange Connector | Microsoft Docs"
description: "Rozwiązywanie problemów związanych z programem Intune Exchange Connector."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c5cb5465-fd8e-4524-83b9-ccdf3393b6dc
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 04c89b6dba34be4e3c49bfc907abe7a6240f3d51
ms.openlocfilehash: 4ada25264aee779f5b31708fdec4f44d19b2e7f7


---

# <a name="troubleshoot-the-exchange-connector"></a>Rozwiązywanie problemów z programem Exchange Connector

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

W tym temacie opisano sposób rozwiązywania problemów, które mogą być związane z programem Intune Exchange Connector.

## <a name="steps-for-checking-the-connector-configuration"></a>Kroki dotyczące sprawdzania konfiguracji programu Exchange Connector 

Sprawdź konfigurację programu Exchange Connector, a następnie zobacz, czy problem został rozwiązany.

- Upewnij się, że określono konto powiadomień w początkowej konfiguracji programu Exchange Connector.
- Konto programu Exchange Connector musi mieć odpowiednie uprawnienia do wykonania polecenia cmdlet programu PowerShell używanego przez program Exchange Connector.
- Podczas konfigurowania programu Exchange Connector należy określić serwer (CAS) znajdujący się możliwie najbliżej serwera hostującego program Exchange Connector. Opóźnienie komunikacji między serwerem CAS i programem Exchange Connector może spowodować opóźnienia odnajdywania urządzeń, zwłaszcza w przypadku korzystania z usługi O365 w wersji dedykowanej.
- Należy pamiętać, że istnieje opóźnienie czasowe między synchronizacjami programu Exchange Connector z serwerem CAS programu Exchange. Pełna synchronizacja jest wykonywana raz dziennie, a co około dwie godziny odbywa się synchronizacja różnicowa (szybka). Istnieje prawdopodobieństwo, że użytkownik z nowo zarejestrowanym urządzeniem doświadczy opóźnienia podczas uzyskiwania dostępu.
- 
## <a name="exchange-activesync-device-not-discovered-from-exchange"></a>Urządzenie z programem Exchange ActiveSync nie zostało wykryte za pomocą programu Exchange
Sprawdź, czy program Exchange Connector jest synchronizowany z serwerem Exchange. Aby to zrobić, zlokalizuj dzienniki pełnej synchronizacji lub synchronizacji różnicowej. Zobacz dzienniki programu Exchange Connector. Jeśli synchronizacja pełna lub różnicowa została pomyślnie ukończona od czasu dołączenia urządzenia, nie może być ona źródłem problemu. Jeśli synchronizacja nie została wykonana, zbierz dzienniki synchronizacji i dołącz je do żądania pomocy technicznej.

- Jeśli użytkownik nie ma licencji usługi Intune, program Exchange Connector nie wykryje urządzeń tego użytkownika.
- Jeśli podstawowy adres SMTP użytkownika różni się od jego nazwy UPN w usłudze AAD, program Exchange Connector nie wykryje żadnych urządzeń dla tego użytkownika usługi Intune/AAD. Popraw podstawowy adres SMTP.
- Jeśli serwer CAS, z którym komunikuje się program Exchange Connector podczas cyklu odnajdywania, jest serwerem CAS programu Exchange 2010, a masz serwery skrzynek pocztowych zarówno dla programu Exchange 2010, jak i 2013, program Exchange Connector nie odnajdzie żadnych urządzeń użytkowników korzystających z programu Exchange 2013. W celu rozwiązania tego problemu skonfiguruj program Exchange Connector, tak aby wskazywał serwer CAS programu Exchange 2013.  Chociaż ten problem dotyczy przede wszystkim topologii usługi O365 w wersji dedykowanej, również w innych topologiach jako najlepsze rozwiązanie zaleca się wskazanie serwera CAS programu Exchange 2013.
- W przypadku środowisk programu Exchange w wersji dedykowanej (usługi O365 w wersji dedykowanej) należy wskazać w programie Exchange Connector serwer CAS programu Exchange 2013 (nie Exchange 2010) w środowisku dedykowanym podczas instalacji początkowej, ponieważ będzie on komunikować się tylko z tym serwerem CAS podczas wykonywania poleceń cmdlet programu Powershell.


## <a name="using-powershell-to-get-more-data-on-exchange-connector-issues"></a>Uzyskiwanie dodatkowych danych dotyczących problemów z programem Exchange Connector za pomocą programu Powershell
- Aby uzyskać listę wszystkich urządzeń przenośnych dla skrzynki pocztowej, użyj polecenia Get-ActiveSyncDeviceStatistics -mailbox mbx
- Aby uzyskać listę adresów SMTP dla skrzynki pocztowej, użyj polecenia Get-Mailbox -Identity user | select emailaddresses | fl.
- Aby uzyskać szczegółowe informacje dotyczące stanu dostępu do urządzenia, użyj polecenia Get-CASMailbox <upn> | fl

### <a name="next-steps"></a>Następne kroki
Jeśli te informacje dotyczące rozwiązywania problemów nie pomogły, skontaktuj się z pomocą techniczną firmy Microsoft zgodnie z opisem w temacie [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune).



<!--HONumber=Dec16_HO5-->


