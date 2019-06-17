---
title: Punkty końcowe sieci w przypadku wdrożeń dla instytucji rządowych USA — Microsoft Intune
titleSuffix: ''
description: Zapoznaj się z punktami końcowymi usługi Intune dla instytucji rządowych USA.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: e4712c2958e2beee8853ad0d2620414d823da327
ms.sourcegitcommit: 6e07c35145f70b008cf170bae57143248a275b67
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/07/2019
ms.locfileid: "66804500"
---
# <a name="us-government-endpoints-for-microsoft-intune"></a>Punkty końcowe dla instytucji rządowych USA w usłudze Microsoft Intune

Ta strona zawiera listę punktów końcowych dla instytucji rządowych USA wymaganych na potrzeby ustawień serwera proxy we wdrożeniach usługi Intune.

Aby zarządzać urządzeniami za zaporami i serwerami proxy, należy włączyć komunikację na potrzeby usługi Intune.

- Serwer proxy musi obsługiwać zarówno protokół **HTTP (80)** , jak i **HTTPS (443)** , ponieważ klienci usługi Intune używają obu tych protokołów.
- W celu wykonywania pewnych zadań (takich jak pobieranie aktualizacji oprogramowania) usługa Intune wymaga nieautoryzowanego dostępu serwera proxy do witryny manage.microsoft.com

Można modyfikować ustawienia serwera proxy na poszczególnych komputerach klienckich. Można również zmieniać ustawienia dla wszystkich komputerów klienckich znajdujących się za określonym serwerem proxy za pomocą ustawień zasad grupy.

Zarządzane urządzenia wymagają zastosowania takiej konfiguracji, aby grupa **Wszyscy użytkownicy** miała dostęp do usług za pośrednictwem zapór.

Poniższe tabele zawierają listę portów i usług, do których uzyskuje dostęp klient usługi Intune:

|**Punkt końcowy**|**Adres IP**|
|---------------------|-----------|
|*.manage.microsoft.us | 52.243.26.209 <br> 52.247.173.11 <br> 52.227.183.12 <br>52.227.180.205 <br> 52.227.178.107 <br> 13.72.185.168 <br> 52.227.173.179 <br> 52.227.175.242 <br> 13.72.39.209 <br> 52.243.26.209 <br> 52.247.173.11 |
| enterpriseregistration.microsoftonline.us | 13.72.188.239 <br> 13.72.55.179 |

## <a name="us-government-customer-designated-endpoints"></a>Wyznaczone przez klientów punkty końcowe dla instytucji rządowych USA:
- Witryna Azure Portal: https://portal.azure.us/ 
- Usługa Office 365: https://portal.office365.us/ 
- Aplikacja Portal firmy w usłudze Intune: https://portal.manage.microsoft.us/ 

## <a name="partner-service-endpoints-that-intune-depends-on"></a>Punkty końcowe usług partnerskich, od których zależy usługa Intune:
- AAD Sync: https://syncservice.gov.us.microsoftonline.com/DirectoryService.svc
- Evo STS: https://login.microsoftonline.us
- Directory Proxy: https://directoryproxy.microsoftazure.us/DirectoryProxy.svc
- AAD Graph: https://directory.microsoftazure.us i https://graph.microsoftazure.us
- MS Graph: https://graph.microsoft.us
- ADRS: https://enterpriseregistration.microsoftonline.us
