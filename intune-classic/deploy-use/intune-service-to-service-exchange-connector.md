---
title: "Program Exchange Connector dla usługi Exchange Online | Microsoft Docs"
description: "Połączenie usługi Intune z programem Exchange usługi Office 365 umożliwia obsługę funkcji zarządzanie urządzeniami przenośnymi usługi Exchange ActiveSync."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 4b73767f585cfa6283c7fb0601e7061efe42c606
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="configure-the-intune-service-to-service-connector-for-exchange-online"></a>Konfigurowanie łącznika Intune Service to Service Connector dla programu Exchange Online

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Dzięki tym informacjom można połączyć usługę Microsoft Intune i usługę Exchange Online lub nową usługę Exchange Online w wersji dedykowanej. Aby ustalić, czy środowisko usługi Exchange Online w wersji dedykowanej jest w wersji **nowej**, czy **starszej**, skontaktuj się z menedżerem ds. klientów. Usługa Intune obsługuje tylko jedno połączenie programu Exchange Connector dowolnego typu na subskrypcję.

## <a name="service-to-service-connector-requirements"></a>Wymagania dotyczące łącznika Service To Service Connector
Łącznik **Service To Service Connector** obsługuje tylko usługę Exchange Online lub usługę Exchange Online w wersji dedykowanej i nie ma wymagań dotyczących infrastruktury lokalnej.

|Wymaganie|Więcej informacji|
|---------------|--------------------|
|Usługa Exchange Online — skonfigurowana i uruchomiona|[Usługa Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Urząd zarządzania urządzeniami przenośnymi| [Ustawianie usługi Microsoft Intune jako urzędu zarządzania urządzeniami przenośnymi](prerequisites-for-enrollment.md#step-2-set-mdm-authority)|
|Wersja programu Microsoft Exchange|Usługa Exchange Online lub nowa usługa Exchange Online w wersji dedykowanej|
|Synchronizacja z usługą Active Directory|Zanim będzie możliwe użycie łącznika Intune Connector, należy [skonfigurować synchronizację z usługą Active Directory](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3), aby zapewnić synchronizację lokalnych użytkowników i grup zabezpieczeń z wystąpieniem usługi Azure Active Directory.|

### <a name="exchange-cmdlet-requirements"></a>Wymagania poleceń cmdlet programu Exchange

Ponadto musisz utworzyć konto użytkownika usługi Exchange Online, które będzie używane przez program Exchange Connector usługi Intune. Konto musi mieć uprawnienia do użycia konsoli administracyjnej usługi Intune oraz do uruchamiania następujących wymaganych poleceń cmdlet programu Exchange w środowisku Windows PowerShell:

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## <a name="set-up-the-service-to-service-connector"></a>Konfigurowanie łącznika Service To Service Connector

1. Otwórz [konsolę administracyjną usługi Microsoft Intune](https://manage.microsoft.com) przy użyciu konta użytkownika z prawami administratora programu Exchange i uprawnieniami do użycia [opisanych wcześniej](#exchange-cmdlet-requirements) poleceń cmdlet. Usługa Microsoft Intune używa adresu e-mail aktualnie zalogowanego użytkownika, aby skonfigurować połączenie.

2.  W okienku skrótów obszaru roboczego wybierz pozycje **ADMINISTRACJA**>**Zarządzanie urządzeniami przenośnymi** > **Microsoft Exchange** > **Skonfiguruj połączenie programu Exchange**.
![Strona konfiguracji łącznika Service To Service Connector](../media/intunesa5cservicetoserviceconnector.png)

3.  Na stronie **Konfigurowanie połączenia z programem Exchange** wybierz polecenie **Skonfiguruj łącznik Service To Service Connector**.


Łącznik Service To Service Connector automatycznie konfiguruje i synchronizuje środowisko usługi Exchange Online lub nowej usługi Exchange Online w wersji dedykowanej.

## <a name="validate-your-exchange-connection"></a>Weryfikacja połączenia z programem Exchange

Po pomyślnym skonfigurowaniu programu Exchange Connector przejdź do [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com). Wybierz pozycje **Administracja**> **Zarządzania urządzeniami przenośnymi** > **Microsoft Exchange**. Następnie sprawdź, czy podane szczegółowe informacje są wyświetlane w polu **Informacje o połączeniu z programem Exchange**.

Możesz również sprawdzić godzinę i datę ostatniej pomyślnej próby synchronizacji.

