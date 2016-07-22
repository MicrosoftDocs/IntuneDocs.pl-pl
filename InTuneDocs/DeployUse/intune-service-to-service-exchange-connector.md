---
# required metadata

title: Konfigurowanie łącznika Microsoft Intune Exchange Connector dla hostowanej instalacji programu Exchange | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Konfigurowanie łącznika Intune Service to Service dla programu Exchange Online

Dzięki tym informacjom można połączyć usługę Microsoft Intune i usługę Exchange Online hostowaną przez usługi Office 365.

## Wymagania dotyczące łącznika Service To Service Connector
Łącznik **Service To Service Connector** obsługuje tylko hostowany program Exchange i nie ma wymagań dotyczących infrastruktury lokalnej.

|Wymaganie|Więcej informacji|
|---------------|--------------------|
|Hostowany program Exchange — skonfigurowany i uruchomiony|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Urząd zarządzania urządzeniami przenośnymi| [Ustawianie usługi Microsoft Intune jako urzędu zarządzania urządzeniami przenośnymi](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority)|
|Wersja programu Microsoft Exchange|Należy mieć subskrypcję usługi Office 365 z dzierżawą programu Exchange Server w wersji 2013 lub nowszej. Jeśli jest dostępna dzierżawa programu Exchange Server w wersji 2013 lub nowszej, łącznik obsługuje program Exchange Server 2010 w tym samym środowisku.|
|Synchronizacja z usługą Active Directory|Zanim będzie możliwe użycie łącznika Intune Connector, należy [skonfigurować synchronizację z usługą Active Directory](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3), aby zapewnić synchronizację lokalnych użytkowników i grup zabezpieczeń z wystąpieniem usługi Azure Active Directory.|

### Wymagania poleceń cmdlet programu Exchange

Ponadto musisz utworzyć konto użytkownika usługi Exchange Online, które będzie używane przez program Exchange Connector usługi Intune. Konto musi mieć uprawnienia do użycia konsoli administracyjnej usługi Intune oraz do uruchamiania poniższych wymaganych poleceń cmdlet programu Exchange w środowisku Windows PowerShell:

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## Konfigurowanie łącznika Service To Service Connector

1. Otwórz [konsolę administracyjną usługi Microsoft Intune](http://manage.microsoft.com) przy użyciu konta użytkownika z prawami administratora programu Exchange i uprawnieniami do użycia [powyższych](#exchange-cmdlet-requirements) poleceń cmdlet. Usługa Microsoft Intune używa adresu e-mail aktualnie zalogowanego użytkownika, aby skonfigurować połączenie.

2.  W okienku skrótów obszaru roboczego wybierz pozycję **ADMINISTRACJA**, a następnie przejdź do pozycji **Zarządzanie urządzeniami przenośnymi** > **Microsoft Exchange** > **Skonfiguruj połączenie programu Exchange**.
![Strona konfiguracji łącznika Service To Service Connector](../media/intunesa5cservicetoserviceconnector.png)

3.  Na stronie **Konfigurowanie połączenia z programem Exchange** wybierz polecenie **Skonfiguruj łącznik Service To Service Connector**.


Łącznik Service To Service Connector będzie automatycznie konfigurował i synchronizował hostowane środowisko programu Exchange.

## Weryfikacja połączenia z programem Exchange

Po pomyślnym skonfigurowaniu programu Exchange Connector w konsoli administracyjnej usługi Intune wybierz obszar roboczy **ADMINISTRACJA** i przejdź do sekcji **Zarządzanie urządzeniami przenośnymi** > **Microsoft Exchange**, a następnie sprawdź, czy podane szczegółowe informacje są wyświetlane w polu **Informacje o połączeniu z programem Exchange**..

Możesz również sprawdzić godzinę i datę ostatniej pomyślnej próby synchronizacji.


<!--HONumber=May16_HO1-->


