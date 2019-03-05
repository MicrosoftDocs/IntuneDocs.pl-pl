---
title: Rozwiązywanie problemów z łącznikami programu Exchange Connector | Microsoft Intune
description: Rozwiązywanie problemów związanych z lokalnym łącznikiem Exchange Connector usługi Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/18/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a7e3c742-295b-40bb-9afa-17f243062500
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 89611dd197c968df43cac6006d3982fe5f1ec5c2
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57232645"
---
# <a name="troubleshoot-the-intune-on-premises-exchange-connector"></a>Rozwiązywanie problemów z lokalnym łącznikiem Exchange Connector usługi Intune

W tym artykule opisano, jak rozwiązywać problemy związane z lokalnym łącznikiem Exchange Connector usługi Intune.

## <a name="steps-for-checking-the-connector-configuration"></a>Kroki dotyczące sprawdzania konfiguracji łącznika 

Zapoznaj się z tematem [Konfiguracja lokalnego łącznika Exchange Connector usługi Intune](exchange-connector-install.md), aby upewnić się, że łącznik został skonfigurowany prawidłowo. Poniżej przedstawiono kilka typowych problemów. Po wprowadzeniu poprawek sprawdź, czy problem został rozwiązany.

 - W oknie dialogowym Microsoft Intune Exchange Connector upewnij się, że określono konto użytkownika, które ma odpowiednie uprawnienia do wykonywania [wymaganych poleceń cmdlet programu Exchange w środowisku Windows PowerShell](exchange-connector-install.md#exchange-cmdlet-requirements).
- Włącz powiadomienia i określ konto powiadomień.
 - Podczas konfigurowania programu Exchange Connector należy określić serwer dostępu klienta (CAS, Client Access Server) znajdujący się możliwie najbliżej serwera hostującego program Exchange Connector. Opóźnienie komunikacji między serwerem CAS i programem Exchange Connector może spowodować opóźnienia odnajdywania urządzeń, zwłaszcza w przypadku korzystania z usługi Exchange Online w warstwie Dedykowana.
 - Uzyskanie dostępu przez użytkownika z nowo zarejestrowanym urządzeniem może zostać opóźnione do momentu, aż program Exchange Connector zsynchronizuje się z serwerem CAS programu Exchange. Pełna synchronizacja jest wykonywana raz dziennie, a synchronizacja różnicowa (szybka) jest wykonywana kilka razy dziennie.  Aby zminimalizować opóźnienie, możesz [ręcznie wymusić szybką synchronizację lub pełną synchronizację](exchange-connector-install.md#manually-force-a-quick-sync-or-full-sync).
 
## <a name="exchange-activesync-device-not-discovered-from-exchange"></a>Urządzenie z programem Exchange ActiveSync nie zostało wykryte za pomocą programu Exchange
[Monitoruj działanie programu Exchange Connector](exchange-connector-install.md#on-premises-exchange-connector-high-availability-support), aby sprawdzić, czy program Exchange Connector jest synchronizowany z serwerem Exchange. Jeśli od czasu dołączenia urządzenia została pomyślnie wykonana pełna lub szybka synchronizacja, możesz sprawdzić, czy występują inne możliwe problemy, wymienione poniżej. Jeśli synchronizacja nie została wykonana, zbierz dzienniki synchronizacji i dołącz je do żądania pomocy technicznej.

 - Upewnij się, że użytkownicy mają licencję usługi Intune — jeśli nie, program Exchange Connector nie wykryje ich urządzeń.
 - Jeśli podstawowy adres SMTP użytkownika różni się od jego nazwy UPN w usłudze Azure Active Directory (Azure AD), program Exchange Connector nie wykryje żadnych urządzeń dla tego użytkownika. Popraw podstawowy adres SMTP w celu rozwiązania problemu.
 - Jeśli w środowisku znajdują się serwery skrzynek pocztowych zarówno programu Exchange 2010, jak i programu Exchange 2013, zalecamy skierowanie programu Exchange Connector do serwera CAS programu Exchange 2013. W przeciwnym razie, jeśli program Exchange Connector zostanie skonfigurowany do komunikowania się z serwerem CAS programu Exchange 2010, nie odnajdzie żadnych urządzeń użytkowników programu Exchange 2013. 
- W przypadku środowisk usługi Exchange Online w warstwie Dedykowana należy skierować program Exchange Connector do serwera CAS programu Exchange 2013 (a nie serwera CAS programu Exchange 2010) w środowisku dedykowanym podczas instalacji początkowej, ponieważ program Connector będzie komunikować się z tym serwerem CAS tylko podczas wykonywania poleceń cmdlet programu PowerShell.


## <a name="using-powershell-to-get-more-data-on-exchange-connector-issues"></a>Uzyskiwanie dodatkowych danych dotyczących problemów z programem Exchange Connector za pomocą programu Powershell
- Aby uzyskać listę wszystkich urządzeń przenośnych dla skrzynki pocztowej, użyj polecenia Get-ActiveSyncDeviceStatistics -mailbox mbx
- Aby uzyskać listę adresów SMTP dla skrzynki pocztowej, użyj polecenia Get-Mailbox -Identity user | select emailaddresses | fl
- Aby uzyskać szczegółowe informacje dotyczące stanu dostępu do urządzenia, użyj polecenia Get-CASMailbox <upn> | fl

### <a name="next-steps"></a>Następne kroki
Jeśli te informacje nie pomogą w rozwiązaniu problemu, możesz również [uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](get-support.md).
