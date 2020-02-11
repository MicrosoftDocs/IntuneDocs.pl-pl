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
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5f6682cb-5fcd-4018-b7f7-71768ad3152e
ms.reviewer: kerimh
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: dfa93bb758447c872d172ded7706fd7507a42f11
ms.sourcegitcommit: c7c6be3833d9a63d43f31d598b555b49b33cf5cb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "76966287"
---
# <a name="us-government-endpoints-for-microsoft-intune"></a>Punkty końcowe dla instytucji rządowych USA w usłudze Microsoft Intune

Ta strona zawiera listę punktów końcowych dla instytucji rządowych USA wymaganych na potrzeby ustawień serwera proxy we wdrożeniach usługi Intune.

Aby zarządzać urządzeniami za zaporami i serwerami proxy, należy włączyć komunikację na potrzeby usługi Intune.

- Serwer proxy musi obsługiwać zarówno protokół **HTTP (80)** , jak i **HTTPS (443)** , ponieważ klienci usługi Intune używają obu tych protokołów.
- W celu wykonywania pewnych zadań (takich jak pobieranie aktualizacji oprogramowania) usługa Intune wymaga nieautoryzowanego dostępu serwera proxy do witryny manage.microsoft.com

Można modyfikować ustawienia serwera proxy na poszczególnych komputerach klienckich. Można również zmieniać ustawienia dla wszystkich komputerów klienckich znajdujących się za określonym serwerem proxy za pomocą ustawień zasad grupy.

Zarządzane urządzenia wymagają zastosowania takiej konfiguracji, aby grupa **Wszyscy użytkownicy** miała dostęp do usług za pośrednictwem zapór.

Aby uzyskać więcej informacji na temat automatycznego rejestrowania i rejestracji urządzeń w systemie Windows 10 dla klientów w instytucjach rządowych USA, zobacz artykuł [Konfigurowanie rejestracji dla urządzeń z systemem Windows](../enrollment/windows-enroll.md#windows-10-auto-enrollment-and-device-registration).

Poniższe tabele zawierają listę portów i usług, do których uzyskuje dostęp klient usługi Intune:

|**Punkt końcowy**|**Adres IP**|
|---------------------|-----------|
|*.manage.microsoft.us | 52.243.26.209 <br> 52.247.173.11 <br> 52.227.183.12 <br>52.227.180.205 <br> 52.227.178.107 <br> 13.72.185.168 <br> 52.227.173.179 <br> 52.227.175.242 <br> 13.72.39.209 <br> 52.243.26.209 <br> 52.247.173.11 |
| enterpriseregistration.microsoftonline.us | 13.72.188.239 <br> 13.72.55.179 |

## <a name="us-government-customer-designated-endpoints"></a>Wyznaczone przez klientów punkty końcowe dla instytucji rządowych USA:
- Azure portal: https:\//portal.azure.us/ 
- Office 365: https:\//portal.office365.us/ 
- Intune — Portal firmy: https:\//portal.manage.microsoft.us/ 

## <a name="partner-service-endpoints-that-intune-depends-on"></a>Punkty końcowe usług partnerskich, od których zależy usługa Intune:
- Usługa AAD Sync: https:\//syncservice.gov.us.microsoftonline.com/DirectoryService.svc
- Evo STS: https:\//login.microsoftonline.us
- Directory Proxy: https:\//directoryproxy.microsoftazure.us/DirectoryProxy.svc
- AAD Graph: https:\//directory.microsoftazure.us oraz https:\//graph.microsoftazure.us
- MS Graph: https:\//graph.microsoft.us
- ADRS: https:\//enterpriseregistration.microsoftonline.us

## <a name="windows-push-notification-services"></a>Usługi powiadomień WNS
W przypadku urządzeń zarządzanych przez usługę Intune przy użyciu rozwiązania do zarządzania urządzeniami mobilnymi (MDM) usługi WNS są wymagane do wykonywania akcji dla urządzeń i innych natychmiastowych działań. Aby uzyskać więcej informacji, zobacz [Enterprise Firewall and Proxy Configurations to Support WNS Traffic (Konfiguracje zapory przedsiębiorstwa i serwera proxy pod kątem obsługi ruchu usług WNS)](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)

## <a name="apple-device-network-information"></a>Informacje o sieci urządzeń firmy Apple

|**Sposób użycia**|**Nazwa hosta (adres IP/podsieć)**|**Protokół**|**Port**|
|------------|-----------|------------|-----------|
|Pobieranie i wyświetlanie zawartości z serwerów firmy Apple|itunes.apple.com<br>\*.itunes.apple.com<br>\*.mzstatic.com<br>\*.phobos.apple.com<br>\*.phobos.itunes-apple.com.akadns.net|HTTP|80|
|Komunikacja z serwerami usługi APNS|#-courier.push.apple.com<br>„#” jest liczbą losową z zakresu od 0 do 50.|TCP|5223 i 443|
|Różne funkcje, w tym dostęp do Internetu, sklepu iTunes, sklepu z aplikacjami systemu macOS, usługi iCloud, obsługi komunikatów itp.|phobos.apple.com<br>ocsp.apple.com<br>ax.itunes.apple.com<br>ax.itunes.apple.com.edgesuite.net|HTTP/HTTPS|80 lub 443|

Aby uzyskać więcej informacji, zobacz:

- [Porty TCP i UDP używane przez produkty Apple](https://support.apple.com/HT202944)
- [Informacje o połączeniach z serwerami systemów macOS i iOS oraz aplikacji iTunes oraz o procesach aplikacji iTunes działających w tle](https://support.apple.com/HT201999)
- [Jeśli urządzenia klienckie z systemem macOS lub iOS nie otrzymują powiadomień w trybie push Apple](https://support.apple.com/HT203609)

## <a name="next-steps"></a>Następne kroki
[Punkty końcowe sieci dla usługi Microsoft Intune](intune-endpoints.md)

