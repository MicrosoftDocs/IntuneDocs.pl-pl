---
title: "Znajdowanie nazwy rodziny pakietów (PFN) dla sieci VPN dla aplikacji | Microsoft Docs"
description: "Znajdź nazwę PFN w celu skonfigurowania sieci VPN dla aplikacji."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 74643d1d-4fd9-4cff-ac79-1a42281d2f76
ms.reviewer: tycast
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 0fd7d7e1e09f193479c6ad221c8ace7470942c5a
ms.lasthandoff: 04/14/2017


---

# <a name="find-a-package-family-name-pfn-for-per-app-vpn-configuration"></a>Znajdowanie nazwy rodziny pakietów (PFN) w celu konfiguracji sieci VPN dla aplikacji

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Istnieją dwa sposoby znajdowania nazwy PFN w celu skonfigurowania sieci VPN dla aplikacji.

## <a name="find-a-pfn-for-an-app-thats-installed-on-a-windows-10-computer"></a>Znajdowanie nazwy PFN dla aplikacji zainstalowanej na komputerze z systemem Windows 10

Jeśli pracujesz z aplikacją, która jest już zainstalowana na komputerze z systemem Windows 10, możesz uzyskać nazwę PFN przy użyciu polecenia cmdlet programu PowerShell [Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx).

Polecenie Get-AppxPackage ma następującą składnię:

` Parameter Set: __AllParameterSets`
` Get-AppxPackage [[-Name] <String> ] [[-Publisher] <String> ] [-AllUsers] [-User <String> ] [ <CommonParameters>]`

> [!NOTE]
W celu uzyskania nazwy PFN może być konieczne uruchomienie programu PowerShell jako administrator.

Aby na przykład uzyskać informacje dotyczące wszystkich aplikacji uniwersalnych zainstalowanych na komputerze, użyj polecenia `Get-AppxPackage`.

Aby uzyskać informacje dotyczące aplikacji, której nazwa lub część nazwy jest znana, użyj polecenia `Get-AppxPackage *<app_name>`. Zwróć uwagę na użycie symbolu wieloznacznego, który jest przydatny zwłaszcza wtedy, gdy nie masz pewności, jaka jest pełna nazwa aplikacji. Aby na przykład uzyskać informacje dotyczące programu OneNote, użyj polecenia `Get-AppxPackage *OneNote`.


Oto informacje uzyskane dla programu OneNote:

`Name                   : Microsoft.Office.OneNote`

`Publisher              : CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US`

`Architecture           : X64`

`ResourceId             :`

`Version                : 17.6769.57631.0`

`PackageFullName        : Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`InstallLocation        : C:\Program Files\WindowsApps`

`\Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`IsFramework            : False`

**`PackageFamilyName      : Microsoft.Office.OneNote_8wekyb3d8bbwe`**

`PublisherId            : 8wekyb3d8bbwe`



## <a name="find-a-pfn-if-the-app-is-not-installed-on-a-computer"></a>Znajdowanie nazwy PFN, jeśli aplikacja nie jest zainstalowana na komputerze

1.    Przejdź do strony https://www.microsoft.com/store/apps.
2.    Wprowadź nazwę aplikacji na pasku wyszukiwania. W tym przykładzie wyszukaj aplikację OneNote.
3.    Wybierz link do aplikacji. Zwróć uwagę, że adres URL zawiera serię liter na końcu. W tym przykładzie adres URL wygląda następująco: `https://www.microsoft.com/store/apps/onenote/9wzdncrfhvjl`.
4.    Wklej następujący adres URL w innej karcie `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/<app id>/applockerdata`. Zastąp ciąg `<app id>` identyfikatorem aplikacji uzyskanym ze strony https://www.microsoft.com/store/apps — serią liter na końcu adresu URL w kroku 3. W tym przykładzie (aplikacja OneNote) należy wkleić ciąg: `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/9wzdncrfhvjl/applockerdata`.

W programie Microsoft Edge zostaną wyświetlone odpowiednie informacje. W programie Internet Explorer kliknij pozycję **Otwórz**, aby wyświetlić informacje. Wartość PFN jest podana w pierwszym wierszu. Poniżej przedstawiono wyniki dla przykładu:


`{`
`  "packageFamilyName": "Microsoft.Office.OneNote_8wekyb3d8bbwe",`
`  "packageIdentityName": "Microsoft.Office.OneNote",`
`  "windowsPhoneLegacyId": "ca05b3ab-f157-450c-8c49-a1f127f5e71d",`
`  "publisherCertificateName": "CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US"`
`}`
