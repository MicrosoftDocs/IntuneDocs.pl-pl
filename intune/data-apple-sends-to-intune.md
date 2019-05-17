---
title: Dane wysyłane do usługi Intune przez firmę Apple
titleSuffix: Microsoft Intune
description: Lista danych, które firma Apple wysyła do usługi Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/19/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: cf27fdb8-f408-425c-9a7c-146de1534425
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4362983bbcdb78f82ce7b16f675c6f61fbefd1e1
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57396349"
---
# <a name="data-apple-sends-to-intune"></a>Dane wysyłane do usługi Intune przez firmę Apple

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Gdy dowolne z następujących usług Apple są włączone na urządzeniu, usługa Microsoft Intune nawiązuje połączenie z firmą Apple i udostępnia informacje o użytkowniku i urządzeniu:

- [Program Device Enrollment Program (DEP) firmy Apple](device-enrollment-program-enroll-ios.md)
- [Certyfikat wypychania MDM (APNs) firmy Apple](apple-mdm-push-certificate-get.md)
- [Usługa Apple School Manager (ASM) firmy Apple](https://docs.microsoft.com/schooldatasync/apple-school-manager-integration-with-intune-for-education-and-school-data-sync)
- [Program Volume Purchase Program (VPP) firmy Apple](vpp-apps-ios.md)

Zanim usługa Microsoft Intune będzie mogła nawiązać połączenie, musisz utworzyć konto Apple dla każdej z usług Apple.

W poniższej tabeli wymieniono dane, które urządzenie firmy Apple wysyła do usługi Intune. [Usługa Intune wysyła również dane do firmy Apple](data-intune-sends-to-apple.md). 

| Usługa | Wiadomość | Dane wysyłane do usługi Intune | Sposób użycia |
|:---:|:---:|:---:| ---|
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Uwierzytelnianie | MessageType | Typ komunikatu: uwierzytelnianie. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Uwierzytelnianie | Temat | Temat, który będzie nasłuchiwany przez urządzenie. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Uwierzytelnianie | MesUDID | Identyfikator UDID urządzeń. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Uwierzytelnianie | OSVersion | Wersja systemu operacyjnego urządzenia. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Uwierzytelnianie | BuildVersion | Wersja kompilacji urządzenia. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Uwierzytelnianie | ProductName | Nazwa produktu urządzenia. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Uwierzytelnianie | SerialNumber | Numer seryjny urządzenia. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Uwierzytelnianie | IMEI | Numer International Mobile Station Equipment urządzenia. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Uwierzytelnianie | MEID | Identyfikator sprzętu przenośnego urządzenia |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | Temat | Temat, który będzie nasłuchiwany przez urządzenie. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | Identyfikator UDID | Identyfikator UDID urządzenia. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | Token | Token wypychania dla urządzenia. Serwer powinien korzystać z tego zaktualizowanego tokenu w przypadku wysyłania powiadomień push do urządzenia. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | PushMagic | Ciąg magiczny musi być zawarty w komunikacie powiadomień push.  |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | UnlockToken | Obiekt BLOB może służyć do odblokowania urządzenia. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | AwaitingConfiguration | Jeśli ma wartość true, urządzenie oczekuje na polecenie MDM DeviceConfigured przed kontynuowaniem za pośrednictwem Asystenta ustawień.  |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Checkout | MessageType | Typ komunikatu: wyewidencjonowanie. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Checkout | Temat | Temat, który będzie nasłuchiwany przez urządzenie. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Checkout | Identyfikator UDID | Identyfikator UDID urządzenia |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Protokół MDM | Stan | Stan.  |
| [APNS](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Protokół MDM | Identyfikator UDID |Identyfikator UDID urządzenia.  |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Protokół MDM | CommandUUID | Identyfikator UUID polecenia, dla którego jest przeznaczona ta odpowiedź. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Protokół MDM | ErrorChain | Tablica słowników przedstawiająca łańcuch błędów, które wystąpiły.  |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token programu rejestracji | Numer seryjny | Numer seryjny urządzenia. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token programu rejestracji | model | Nazwa modelu urządzenia. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token programu rejestracji | Opis | Opis urządzenia. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token programu rejestracji | Kolor | Kolor urządzenia. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token programu rejestracji | Tag zasobu | Tag zasobu urządzenia. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token programu rejestracji | Stan profilu | Stan instalacji profilu. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token programu rejestracji | Identyfikator UUID profilu | Identyfikator UUID przypisanego profilu. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token programu rejestracji | Czasu przypisania profilu | Sygnatura czasowa w formacie ISO 8601 wskazująca, kiedy profil został przypisany do urządzenia. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token programu rejestracji | Czas wypychania profilu | Sygnatura czasowa w formacie ISO 8601 wskazująca, kiedy profil został wypchnięty do urządzenia.|
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token programu rejestracji | Data przypisania urządzenia | Sygnatura czasowa w formacie ISO 8601 wskazująca, kiedy urządzenie zostało zarejestrowane w programie Device Enrollment Program. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token programu rejestracji | Urządzenie przypisane przez | Adres e-mail osoby, która przypisała urządzenie. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token programu rejestracji | System operacyjny | System operacyjny urządzenia. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token programu rejestracji | Rodzina urządzeń | Rodzina produktów urządzenia firmy Apple. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | Identyfikator użytkownika firmy Apple | Identyfikator użytkownika generowany przez firmę Apple. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | opis aplikacji | Opis aplikacji VPP. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | ikona aplikacji | Adres URL ikony hostowanej przez firmę Apple dla aplikacji VPP. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | Identyfikator aplikacji | Identyfikator aplikacji firmy Apple nazywany również adamsId. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | nazwa aplikacji | Nazwa aplikacji VPP. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | assignedCount | Liczba przypisanych licencji dla aplikacji. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | availableCount | Liczba nieprzypisanych licencji dla aplikacji. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | bundleId | Element bundleId aplikacji. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | informacji o prawach autorskich, | Informacje o prawach autorskich aplikacji. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | CountryCode | Kod kraju programu VPP. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | deviceAssignable | Firma Apple zwraca wartość true, jeśli administrator może przypisać licencję urządzenia dla aplikacji. W przeciwnym razie zostaje zwrócona wartość false. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | facilitatorMemberId | Identyfikator elementu członkowskiego facylitatora konta VPP.  |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | gatunki | Gatunki aplikacji. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | Identyfikator GUID dla identyfikatora UserId usługi Intune | Identyfikator GUID wygenerowany przez usługę Intune. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | isIrrevocable | Firma Apple zwraca wartość true, jeśli nie można odwołać licencji. Jeśli można ją odwołać, zostaje zwrócona wartość false. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | Identyfikator licencji | Identyfikator wygenerowany przez firmę Apple do identyfikowania konkretnej licencji. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | Lokalizacja | Lokalizacja przechowywana w danych konfiguracji programu VPP firmy Apple. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | Zarządzana nazwa UPN AppleId | Adres e-mail AppleID dla użytkownika, administratora oraz elementu członkowskiego facylitatora. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | OrganizationId | Identyfikator organizacji przypisany przez firmę Apple. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | pricingParam | Typ kalkulacji cen firmy Apple dla aplikacji. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | productType | Typ produktu aplikacji VPP. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | retiredCount | Liczba wycofanych licencji dla aplikacji. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | totalCount | Całkowita liczba licencji zakupionych dla aplikacji. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | adres URL | Adres URL sklepu iTunes Store aplikacji.|
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP firmy Apple | Stan użytkownika | Stan użytkownika w programach VPP firmy Apple. |


Aby zaprzestać korzystania z usług Apple w usłudze Microsoft Intune i usunąć dane, musisz zarówno wyłączyć token Apple usługi Microsoft Intune, jak i usunąć swoje konto Apple. Zobacz informacje o koncie Apple, aby dowiedzieć się, jak zarządzać kontem.


