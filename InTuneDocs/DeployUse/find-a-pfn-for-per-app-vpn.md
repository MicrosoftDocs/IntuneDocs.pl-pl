---
title: "Znajdowanie nazwy rodziny pakietów (PFN) dla sieci VPN dla aplikacji | Microsoft Intune"
description: "Znajdź nazwę PFN w celu skonfigurowania sieci VPN dla aplikacji."
keywords: 
author: nbigman
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 74643d1d-4fd9-4cff-ac79-1a42281d2f76
ms.reviewer: tycast
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7b16c19c95384655e170c199597dd6bd31afb90d
ms.openlocfilehash: 026bb4c8bf90bbe1af93513df46f0ec21f82509b


---

# Znajdowanie nazwy rodziny pakietów (PFN) w celu konfiguracji sieci VPN dla aplikacji

Istnieją dwa sposoby znajdowania nazwy PFN w celu skonfigurowania sieci VPN dla aplikacji.

## Znajdowanie nazwy PFN dla aplikacji zainstalowanej na komputerze z systemem Windows 10

Jeśli pracujesz z aplikacją, która jest już zainstalowana na komputerze z systemem Windows 10, możesz uzyskać nazwę PFN przy użyciu polecenia cmdlet programu PowerShell [Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx).

Polecenie Get-AppxPackage ma następującą składnię:

` Parameter Set: __AllParameterSets`
` Get-AppxPackage [[-Name] <String> ] [[-Publisher] <String> ] [-AllUsers] [-User <String> ] [ <CommonParameters>]`

> Uwaga: w celu uzyskania nazwy PFN może być konieczne uruchomienie programu PowerShell jako administrator.

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



## Znajdowanie nazwy PFN, jeśli aplikacja nie jest zainstalowana na komputerze

1.  Przejdź do strony https://www.microsoft.com/en-us/store/apps
2.  Wprowadź nazwę aplikacji na pasku wyszukiwania. W tym przykładzie wyszukaj aplikację OneNote.
3.  Kliknij link do aplikacji. Zwróć uwagę, że docelowy adres URL zawiera serię liter na końcu. W tym przykładzie adres URL wygląda następująco:
`https://www.microsoft.com/en-us/store/apps/onenote/9wzdncrfhvjl`
4.  Na innej karcie wklej adres URL `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/<app id>/applockerdata`, zastępując wartość `<app id>` identyfikatorem aplikacji uzyskanym ze strony https://www.microsoft.com/en-us/store/apps — serią liter na końcu adresu URL w kroku 3. W tym przykładzie (aplikacja OneNote) należy wkleić: `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/9wzdncrfhvjl/applockerdata`.

W programie Edge zostaną wyświetlone odpowiednie informacje. W programie Internet Explorer kliknij pozycję **Otwórz**, aby wyświetlić informacje. Wartość PFN jest podana w pierwszym wierszu. Oto jak wyglądają wyniki w tym przykładzie:


`{`
`  "packageFamilyName": "Microsoft.Office.OneNote_8wekyb3d8bbwe",`
`  "packageIdentityName": "Microsoft.Office.OneNote",`
`  "windowsPhoneLegacyId": "ca05b3ab-f157-450c-8c49-a1f127f5e71d",`
`  "publisherCertificateName": "CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US"`
`}`



<!--HONumber=Aug16_HO1-->


