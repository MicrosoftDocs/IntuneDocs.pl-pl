---
title: "Zarządzanie licencjami usługi Intune przy użyciu programu PowerShell | Microsoft Docs"
description: "Zarządzanie licencjami usługi Intune przy użyciu programu PowerShell"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2d31c80-c32c-4315-8271-1b0cf9a1f78a
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ad13897fe7bbe4fe13167bb4ce7f558b436a7a90
ms.openlocfilehash: dd71cc8f0d1fc5802f7f24e5f275089ffa24a1c5
ms.lasthandoff: 02/15/2017


---

# <a name="manage-intune-licenses-using-powershell"></a>Zarządzanie licencjami usługi Intune przy użyciu programu PowerShell

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ten temat zawiera informacje dla administratorów dotyczące zarządzania licencjami użytkownika usługi Intune za pomocą programu PowerShell.

Zanim użytkownicy będą mogli się zalogować w celu korzystania z usługi Intune i rejestrowania urządzeń w systemie zarządzania, należy przypisać każdemu użytkownikowi licencję do swojej subskrypcji usługi Intune, zgodnie z opisem w artykule [Zarządzanie licencjami usługi Intune](start-with-a-paid-subscription-to-microsoft-intune-step-4.md). Niektórzy użytkownicy w organizacjach korzystających z pakietu Microsoft Enterprise Mobility + Security mogą jednak wymagać tylko usługi Azure Active Directory Premium lub usługi Intune w pakiecie EMS. Można przypisać jedną usługę lub podzestaw usług przy użyciu [poleceń cmdlet środowiska PowerShell usługi Azure Active Directory](https://msdn.microsoft.com/library/jj151815.aspx).

Aby selektywnie przypisywać licencje użytkowników dla usług pakietu EMS, należy otworzyć program PowerShell jako administrator na komputerze, na którym zainstalowano [moduł usługi Azure Active Directory dla programu Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule). Program PowerShell można zainstalować na komputerze lokalnym lub serwerze usług ADFS.

Należy utworzyć nową definicję jednostki SKU licencji, która ma zastosowanie tylko do planów żądanej usługi. Aby to zrobić, należy wyłączyć plany, które nie powinny być stosowane. Na przykład można utworzyć definicję jednostki SKU licencji, która nie powoduje przypisania licencji usługi Intune. Aby wyświetlić listę dostępnych usług, wpisz:

    (Get-MsolAccountSku | Where {$\_.SkuPartNumber -eq "EMS"}).ServiceStatus

Aby wykluczyć plan usługi Intune, można uruchomić poniższe polecenie. Można użyć tej samej metody do rozszerzenia całej grupy zabezpieczeń lub skorzystać z bardziej szczegółowych filtrów.

**Przykład 1** Utworzenie nowego użytkownika w wierszu polecenia i przypisanie licencji pakietu EMS bez włączania składnika Intune licencji:

    Connect-MsolService

    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS


Weryfikacja:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

**Przykład 2** Wyłączenie składnika Intune licencji pakietu EMS dla użytkownika, do którego przypisano już licencję:

    Connect-MsolService

    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -RemoveLicenses IAPProdPartnerTest:EMS

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS

Weryfikacja:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com" .Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)

### <a name="next-steps"></a>Następne kroki
Gratulacje! Krok 4 *przewodnika Szybki start dotyczącego usługi Intune* został ukończony.
>[!div class="step-by-step"]

>[&larr; **Synchronizuj użytkowników z Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Organizuj użytkowników i urządzenia** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)  
