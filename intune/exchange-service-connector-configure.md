---
title: Łącznik Intune Exchange dla usługi Exchange Online | Microsoft Intune
description: Połączenie usługi Intune z programem Exchange usługi Office 365 umożliwia obsługę funkcji zarządzanie urządzeniami przenośnymi usługi Exchange ActiveSync.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 9845ed1b809b611975c07c6c8335acd237d845c0
ms.sourcegitcommit: bee072b61cf8a1b8ad8d736b5f5aa9bc526e07ec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/02/2019
ms.locfileid: "53816705"
---
# <a name="configure-the-exchange-service-connector-for-intune-and-exchange-online"></a>Konfiguracja łącznika usługi Exchange dla programów Intune i Exchange Online
W tym artykule opisano, jak połączyć usługę Microsoft Intune z usługą Exchange Online lub nową usługą Exchange Online w wersji dedykowanej. Aby ustalić, czy środowisko usługi Exchange Online w wersji dedykowanej jest w wersji **nowej**, czy **starszej**, skontaktuj się z menedżerem ds. klientów.

Za pomocą łącznika **Service to Service Connector** można zarządzać programem Exchange ActiveSync (EAS) i urządzeniami zarządzanymi przez usługę Intune z poziomu jednej konsoli administracyjnej.  Łącznik nie jest wymagany do włączenia dostępu warunkowego dla usługi Exchange Online.

## <a name="service-to-service-connector-requirements"></a>Wymagania dotyczące łącznika Service To Service Connector
Łącznik **Service To Service Connector** obsługuje tylko usługę Exchange Online lub usługę Exchange Online w wersji dedykowanej i nie ma wymagań dotyczących infrastruktury lokalnej. 


|              Wymaganie               |                                                                                                            Więcej informacji                                                                                                            |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Usługa Exchange Online — skonfigurowana i uruchomiona |                                                                                 [Usługa Exchange Online](https://technet.microsoft.com/library/jj200580.aspx)                                                                                 |
|   Urząd zarządzania urządzeniami przenośnymi   |                                                       [Ustawianie usługi Microsoft Intune jako urzędu zarządzania urządzeniami przenośnymi](mdm-authority-set.md)                                                       |
|       Wersja programu Microsoft Exchange       |                                                                                      Usługa Exchange Online lub nowa usługa Exchange Online w wersji dedykowanej                                                                                      |
|    Synchronizacja z usługą Active Directory    | Zanim będzie możliwe użycie łącznika Intune Connector, należy [skonfigurować synchronizację z usługą Active Directory](/intune/users-add), aby zapewnić synchronizację lokalnych użytkowników i grup zabezpieczeń z wystąpieniem usługi Azure Active Directory. |

### <a name="exchange-cmdlet-requirements"></a>Wymagania poleceń cmdlet programu Exchange

Musisz też utworzyć konto użytkownika usługi Exchange Online, którego będzie używać łącznik usługi Intune Exchange. Konto musi mieć uprawnienia do uruchamiania następujących wymaganych poleceń cmdlet programu Exchange w środowisku Windows PowerShell:

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## <a name="set-up-the-service-to-service-connector"></a>Konfigurowanie łącznika Service To Service Connector

1. Zaloguj się w witrynie [Azure Portal](https://portal.azure.com) przy użyciu konta użytkownika z prawami administratora programu Exchange, uprawnieniami do użycia [opisanych wcześniej](#exchange-cmdlet-requirements) poleceń cmdlet, ważną licencją usługi Intune i rolą administratora globalnego. Usługa Microsoft Intune używa adresu e-mail aktualnie zalogowanego użytkownika, aby skonfigurować połączenie.

2. W menu po lewej stronie wybierz pozycję **Wszystkie usługi**, a następnie w filtrze pola tekstowego wpisz **Intune**.

3. Wybierz opcję **Intune**, aby otworzyć pulpit nawigacyjny usługi Microsoft Intune. Wybierz opcję **Dostęp warunkowy**, a następnie w obszarze **Instalator** wybierz **Łącznik usługi Exchange**.

4.  Na stronie **Dostęp warunkowy — łącznik usługi Exchange** wybierz pozycję **Skonfiguruj łącznik Service to Service**. 
   
     ![Obraz przedstawiający wybór linku Skonfiguruj łącznik Service to Service](media/exchange_service_connector.png)

Łącznik Service To Service Connector automatycznie konfiguruje i synchronizuje środowisko usługi Exchange Online lub nowej usługi Exchange Online w wersji dedykowanej.

## <a name="validate-your-exchange-connection"></a>Weryfikacja połączenia z programem Exchange

Po pomyślnym skonfigurowaniu łącznika Exchange Service to Service sprawdź poprawność informacji o serwerze łącznika programu Exchange na stronie **Dostęp warunkowy — łącznik usługi Exchange**.

Możesz również sprawdzić **Stan połączenia** oraz godzinę i datę ostatniej pomyślnej próby synchronizacji.

 