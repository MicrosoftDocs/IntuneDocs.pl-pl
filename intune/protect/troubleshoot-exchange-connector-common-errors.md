---
title: Rozwiązywanie typowych błędów dla programu Intune Exchange Connector
titleSuffix: Microsoft Intune
description: Rozwiązywanie problemów i rozwiązywanie typowych błędów dla Microsoft Intune Exchange Connector lokalnych
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/02/2019
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
ms.openlocfilehash: b30a7e843850d6918abc2e76f84397a1f197516f
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72508863"
---
# <a name="resolve-common-errors-for-the-intune-exchange-connector"></a>Rozwiązywanie typowych błędów dla programu Intune Exchange Connector

Ten artykuł może pomóc administratorowi usługi Intune w rozwiązaniu określonych błędów i komunikatów dotyczących działania programu Intune Exchange Connector.  

## <a name="configuration-failed-and-returned-error-code-0x0000001"></a>Konfiguracja nie powiodła się i zwróciło kod błędu 0x0000001

**Problem**:  
Podczas próby skonfigurowania Microsoft Intune Exchange Connector zostanie wyświetlony następujący komunikat o błędzie:

```
   The Microsoft Intune Exchange Connector cannot connect to the Microsoft Exchange server.  
   The following Microsoft Exchange Server address could not be reached <Exchange server Name FQDN>  
   Verify that the FQDN of the exchange server address and credentials that you entered is correct and the server is running. The Microsoft Intune Exchange Connector does not support Exchange server arrays.  
   Error code: 0x0000001  
```

Ten problem może wystąpić, jeśli ustawienia internetowego serwera proxy są błędnie skonfigurowane.

**Rozwiązanie**:  
Konfigurowanie ustawień serwera proxy:
1. Skontaktuj się z administratorem sieci lokalnej, aby upewnić się, że ustawienia serwera proxy zostały skonfigurowane prawidłowo. 
2. Użyj polecenia **netsh WinHTTP** , aby skonfigurować serwer proxy i dodać wymaganą listę wykluczeń. Przykład:  

   ```
   Netsh winhttp set proxy proxy-server="http=proxy.corp.domain.com" bypass-list"34*.*;134.132.*.*;10.*.*;localhost;*.corp.domain.com;*.staging.domain.com"
   ```

## <a name="configuration-failed-and-returned-error-code-0x000000b"></a>Konfiguracja nie powiodła się i zwróciło kod błędu 0x000000b   

**Problem**:  
Podczas próby skonfigurowania Microsoft Intune Exchange Connector zostanie wyświetlony następujący komunikat o błędzie:  

```
   The Microsoft Intune Exchange Connector experienced an error:  
   CertEnroll::CX509PrivateKey::Create: The system cannot find the file specified. 0x80070002 (WIN32: 2  
   ERROR_FILE_NOT_FOUND  
   Error code: 0x000000b  
```
Ten problem może wystąpić, jeśli konto użyte do zalogowania się w usłudze Intune nie jest kontem administratora globalnego usługi Intune.

**Rozwiązanie**:  
Zaloguj się do usługi Intune przy użyciu konta będącego administratorem globalnym lub Dodaj konto do globalnej grupy administratorów. Aby uzyskać więcej informacji, zobacz [Kontrola administracji opartej na rolach (RBAC) przy użyciu usługi Microsoft Intune](../fundamentals/role-based-access-control.md).

## <a name="configuration-failed-and-returned-error-code-0x0000006"></a>Konfiguracja nie powiodła się i zwróciło kod błędu 0x0000006

**Problem**:  
Podczas próby skonfigurowania Microsoft Intune Exchange Connector zostanie wyświetlony następujący komunikat o błędzie:  

```  
   The Microsoft Intune Exchange Connector cannot connect to Microsoft Intune  
   Verify that you are connected to the Internet, check the Microsoft Intune Service Status, and try to connect again.  
   Error code: 0x00000006  
```  
Ten błąd może wystąpić, jeśli serwer proxy jest używany do łączenia się z Internetem i blokuje ruch do usługi Intune. Aby określić, czy serwer proxy jest używany, przejdź do **Panelu sterowania** , > **Opcje internetowe**, wybierz kartę **połączenie** , a następnie kliknij przycisk **Ustawienia sieci LAN**.

**Rozwiązanie**:  

- **Opcja 1** — usunięcie ustawień serwera proxy, aby umożliwić komputerowi łączenie się z Internetem bez przechodzenia przez serwer proxy.  

- **Opcja 2** — Konfigurowanie serwera proxy w celu umożliwienia komunikacji z usługą Intune, zgodnie z opisem w [wymaganiach programu Intune Exchange Connector](exchange-connector-install.md#intune-exchange-connector-requirements).



## <a name="event-7000-or-7041-microsoft-intune-exchange-connector-service-wont-start"></a>Zdarzenie 7000 lub 7041: nie można uruchomić usługi Microsoft Intune Exchange Connector

**Problem**:  
Nie można zarejestrować urządzenia z systemem iOS w usłudze Intune i wygenerowania jednego z następujących komunikatów o błędach:  

```  
   Log Name:      System
   Source:            Service Control Manager
   Date:               <time>
   Task Category: None
   Level:               Error
   Keywords:        Classic
   User:                N/A
   Computer:      <computer>
   Description:
   The Microsoft Intune Exchange Connector Service service failed to start because of the following error:  
   The service did not start because of a logon failure.
```  

```  
   Log Name:      System
   Source:            Service Control Manager
   Date:               <time>
   Event ID:          7041
   Task Category: None
   Level:               Error   
   Keywords:        Classic
   User:                N/A
   Computer:       <computer>
   Description:
   The WIEC service was unable to log on as .\WIEC_USER with the currently configured password because of the following error:
   Logon failure: the user has not been granted the requested logon type at this computer.
   Service: WIEC
   Domain and account: .\WIEC_USER
   This service account does not have the required user right "Log on as a service."  
```
Ten problem może wystąpić, jeśli konto **WIEC_User** nie ma prawa użytkownika **Logowanie jako usługa** do zasad lokalnych.

**Rozwiązanie**:  
Na komputerze z uruchomionym programem Intune Exchange Connector Przypisz uprawnienie **Zaloguj się jako użytkownik usługi** do konta usługi **WIEC_User** . Jeśli komputer jest węzłem w klastrze, upewnij się, że do konta usługi klastra na wszystkich węzłach w klastrze jest przypisane uprawnienie *Logowanie jako użytkownik usługi* .  

Aby przypisać użytkownikowi **Logowanie się jako użytkownik usługi** do konta usługi **WIEC_User** na komputerze, wykonaj następujące kroki:

1. Zaloguj się na komputerze jako administrator lub członek grupy Administratorzy.
2. Uruchom **secpol. msc** , aby otworzyć zasady zabezpieczeń lokalnych.
3. Przejdź do pozycji **Ustawienia zabezpieczeń** > **Zasady lokalne**, a następnie wybierz pozycję **Przypisywanie praw użytkownika**.
4. W prawym okienku kliknij dwukrotnie pozycję **Zaloguj się jako usługa**.
5. Wybierz pozycję **Dodaj użytkownika lub grupę**, Dodaj **WIEC_USER** do zasad, a następnie kliknij przycisk **OK** dwa razy.

Jeśli uprawnienie **Zaloguj się jako użytkownik usługi** zostało przypisane do **WIEC_User** ale zostało później usunięte, skontaktuj się z administratorem domeny, aby określić, czy ustawienie zasady grupy zastąpiło jego zastąpienie.  

## <a name="next-steps"></a>Następne kroki  

Następujący artykuł może pomóc w rozwiązaniu określonych błędów:
- [Rozwiązywanie typowych problemów dotyczących programu Intune Exchange Connector](troubleshoot-exchange-connector-common-problems.md). git 

Wyszukaj pomoc techniczną lub społeczność usługi Intune.
- Zobacz [Uzyskaj pomoc techniczną](../fundamentals/get-support.md) , aby korzystać z konsoli usługi Intune, aby pomóc w rozwiązywaniu problemu lub otworzyć przypadek pomocy technicznej w firmie Microsoft. 
- Opublikuj swój problem na [forach Microsoft Intune](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).  
