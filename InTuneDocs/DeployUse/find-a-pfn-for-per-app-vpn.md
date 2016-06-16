---
# required metadata

title: Znajdowanie nazwy rodziny pakietów (PFN) dla sieci VPN dla aplikacji | Microsoft Intune
description:
keywords:
author: nbigman
manager: [ALIAS]
ms.date: 05/10/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 74643d1d-4fd9-4cff-ac79-1a42281d2f76

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: tycast
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Znajdowanie nazwy rodziny pakietów (PFN) dla konfiguracji sieci VPN dla aplikacji

Istnieją dwa sposoby znajdowania nazwy PFN w celu skonfigurowania sieci VPN dla aplikacji.

## Znajdowanie nazwy PFN dla aplikacji zainstalowanej na komputerze z systemem Windows 10 

Jeśli pracujesz z aplikacją, która jest już zainstalowana na komputerze z systemem Windows 10, możesz uzyskać nazwę PFN przy użyciu polecenia cmdlet programu PowerShell [Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx).

Polecenie Get-AppxPackage ma następującą składnię:

` Parameter Set: __AllParameterSets`
` Get-AppxPackage [[-Name] <String> ] [[-Publisher] <String> ] [-AllUsers] [-User <String> ] [ <CommonParameters>]`

> Uwaga: aby uzyskać nazwę PFN, należy uruchomić program PowerShell jak administrator.

Aby na przykład uzyskać informacje dotyczące wszystkich uniwersalnych aplikacji zainstalowanych na komputerze, należy użyć polecenia `Get-AppxPackage`.

Aby uzyskać informacje dotyczące aplikacji, której nazwa lub jej część jest znana, należy użyć polecenia `Get-AppxPackage *<app_name>`. Należy zwrócić uwagę na użycie symbolu wieloznacznego, który jest przydatny szczególnie w wypadku, gdy nie masz pewności, jaka jest pełna nazwa aplikacji. Aby na przykład uzyskać informacje dotyczące programu OneNote, należy użyć polecenia `Get-AppxPackage *OneNote`.


Oto informacje pobrane dla programu OneNote:

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

1.  Przejdź do strony https://www.microsoft.com/pl-pl/store/apps
2.  Wprowadź nazwę aplikacji na pasku wyszukiwania. W naszym przykładzie wyszukaj aplikację OneNote.
3.  Kliknij link do aplikacji. Należy zauważyć, że docelowy adres URL zawiera serię liter na końcu. W naszym przykładzie adres URL może wyglądać następująco:
`https://www.microsoft.com/en-us/store/apps/onenote/9wzdncrfhvjl`
4.  Na innej karcie wklej adres URL `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/<app id>/applockerdata`, zastępując składnik `<app id>` identyfikatorem aplikacji uzyskanym z adresu https://www.microsoft.com/pl-pl/store/apps — serią liter na końcu adresu URL w kroku 3. W naszym przykładzie (aplikacja OneNote) należy wkleić: `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/9wzdncrfhvjl/applockerdata`.

W przeglądarce Edge wyświetlane są żądane informacje. W programie Internet Explorer należy kliknąć polecenie **Otwórz**, aby wyświetlić informacje. Wartość PFN jest podana w pierwszym wierszu. Oto jak wyglądają wyniki w naszym przykładzie:
 

`{`
`  "packageFamilyName": "Microsoft.Office.OneNote_8wekyb3d8bbwe",`
`  "packageIdentityName": "Microsoft.Office.OneNote",`
`  "windowsPhoneLegacyId": "ca05b3ab-f157-450c-8c49-a1f127f5e71d",`
`  "publisherCertificateName": "CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US"`
`}`



<!--HONumber=Jun16_HO1-->


