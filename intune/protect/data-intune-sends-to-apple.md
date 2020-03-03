---
title: Dane wysyłane przez usługę Intune do Apple
titleSuffix: Microsoft Intune
description: Lista danych, które usługa Intune wysyła do firmy Apple.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: b204a956-18ec-11e8-accf-0ed5f89f718b
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0c550fba45e5e6b16e49e7103fde40de1e08ba55
ms.sourcegitcommit: 47c9af81c385c7e893fe5a85eb79cf08e69e6831
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/25/2020
ms.locfileid: "77576481"
---
# <a name="data-intune-sends-to-apple"></a>Dane wysyłane przez usługę Intune do Apple

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Gdy dowolne z następujących usług Apple są włączone na urządzeniu, usługa Microsoft Intune nawiązuje połączenie z firmą Apple i udostępnia informacje o użytkowniku i o urządzeniu firmie Apple: 

- [Program Device Enrollment Program (DEP) firmy Apple](../enrollment/device-enrollment-program-enroll-ios.md)
- [Certyfikat wypychania MDM (APNS) firmy Apple](../enrollment/apple-mdm-push-certificate-get.md)
- [Usługa Apple School Manager (ASM) firmy Apple](https://docs.microsoft.com/schooldatasync/apple-school-manager-integration-with-intune-for-education-and-school-data-sync)
- [Program Volume Purchase Program (VPP) firmy Apple](../apps/vpp-apps-ios.md)

Zanim usługa Microsoft Intune będzie mogła nawiązać połączenie, musisz utworzyć konto Apple dla każdej z usług Apple.

Poniższa tabela zawiera dane wysyłane przez usługę Microsoft Intune z urządzenia do włączonych usług Apple. 

| Usługa | Dane wysyłane do firmy Apple | Sposób użycia |
|---|---| ---|
| [APNS](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token, PushMagic | Jeśli serwer zaakceptuje urządzenie, urządzenie udostępni serwerowi token powiadomienia push urządzenia. Serwer powinien używać tego tokenu do wysyłania komunikatów push do urządzenia. Ten komunikat zaewidencjonowania zawiera również ciąg PushMagic. Serwer musi zapamiętać ten ciąg i uwzględnić go we wszystkich komunikatach push, które wysyła do urządzenia. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token serwera | Token powiadomienia push urządzenia używany do uwierzytelniania usługi Apple. |
| ASM/DEP | server_name | Możliwa do zidentyfikowania nazwa serwera MDM. |
| ASM/DEP | server_uuid | Identyfikator serwera generowany przez system. |
| ASM/DEP | admin_id | Identyfikator Apple osoby, która wygenerowała bieżące tokeny będące w użyciu. |
| ASM/DEP | org_name | Nazwa organizacji. |
| ASM/DEP | org_email | Adres e-mail organizacji. |
| ASM/DEP | org_phone | Numer telefonu organizacji. |
| ASM/DEP | org_address | Adres organizacji. |
| ASM/DEP | org_id | Identyfikator DEP klienta. Ten klucz jest dostępny tylko dla protokołu w wersji 3 lub nowszego. |
| ASM/DEP | serial_number | Numer seryjny urządzenia (ciąg). |
| ASM/DEP | model | Nazwa modelu (ciąg). |
| ASM/DEP | description | Opis urządzenia (ciąg). |
| ASM/DEP | asset_tag | Znacznik zasobu urządzenia (ciąg). |
| ASM/DEP | profile_status | Stan instalacji profilu. Możliwe wartości: **pusty**, **przypisany**, **wypchnięty** lub **usunięty**. |
| ASM/DEP | profile_uuid | Unikatowy identyfikator przypisanego profilu. |
| ASM/DEP | device_assigned_by | Adres e-mail osoby, która przypisała urządzenie. |
| ASM/DEP | os | System operacyjny urządzenia: iOS/iPadOS, OSX lub tvOS. Ten klucz jest prawidłowy w protokole serwera X w wersji 2 lub nowszej. |
| ASM/DEP | device_family | Rodzina produktów firmy Apple urządzenia: iPad, iPhone, iPod, Mac lub AppleTV. Ten klucz jest prawidłowy w protokole serwera X w wersji 2 lub nowszej. |
| ASM/DEP | profile_name | Ciąg. Zrozumiała dla człowieka nazwa profilu. |
| ASM/DEP | support_phone_number | Opcjonalny. Ciąg. Numer telefonu pomocy technicznej dla organizacji. |
| ASM/DEP | support_email_address | Opcjonalny. Ciąg. Adres e-mail pomocy technicznej dla organizacji. Ten klucz jest prawidłowy w protokole serwera X w wersji 2 lub nowszej. |
| ASM/DEP | działu, | Opcjonalny. Ciąg. Zdefiniowana przez użytkownika nazwa działu lub lokalizacji. |
| ASM/DEP | devices | Tablica ciągów zawierająca numery seryjne urządzeń. (Może być pusta). |
| VPP | Identyfikator GUID dla identyfikatora UserId usługi Intune | Identyfikator GUID generowany przez usługę Intune. |
| VPP | Zarządzana nazwa UPN AppleId | Identyfikator AppleID, który został określony przez administratora podczas konfigurowania połączenia tokenu VPP z firmą Apple. |
| VPP | Numer seryjny | Numer seryjny urządzenia zarządzanego. |

Aby zaprzestać korzystania z usług Apple w usłudze Microsoft Intune i usunąć dane, musisz zarówno wyłączyć token Apple usługi Microsoft Intune, jak i usunąć swoje konto Apple. Zobacz informacje o koncie Apple, aby dowiedzieć się, jak zarządzać kontem.


