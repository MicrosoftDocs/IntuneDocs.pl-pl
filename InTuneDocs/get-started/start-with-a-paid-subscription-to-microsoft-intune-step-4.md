---
title: "Zarządzanie licencjami usługi Intune | Microsoft Docs"
description: "Przypisywanie licencji do użytkowników dla subskrypcji usługi Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 68cdc77de1fa77b4fed6a1f37850b5427fb2b121


---

# <a name="manage-intune-licenses"></a>Zarządzanie licencjami usługi Intune
Zanim użytkownicy będą mogli logować się i korzystać z usługi Intune lub rejestrować urządzenia w celu zarządzania nimi, należy najpierw przypisać każdemu użytkownikowi licencję na subskrypcję usługi Intune, używając [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854).

Niektórzy użytkownicy w organizacjach korzystających z pakietu Microsoft Enterprise Mobility + Security (EMS) mogą wymagać tylko usługi Azure Active Directory — wersja Premium lub usługi Intune w pakiecie EMS. Można przypisać jedną usługę lub podzestaw usług przy użyciu [poleceń cmdlet środowiska PowerShell usługi Azure Active Directory](https://msdn.microsoft.com/library/jj151815.aspx). Aby uzyskać więcej informacji, zobacz [Zarządzanie licencjami usługi Intune przy użyciu programu PowerShell](start-with-a-paid-subscription-to-microsoft-intune-step-4-posh.md).

## <a name="how-intune-licenses-are-assigned"></a>Przypisywanie licencji usługi Intune
Gdy konta użytkowników są synchronizowane z lokalnej usługi Active Directory lub ręcznie dodawane do subskrypcji usług w chmurze za pośrednictwem [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854), licencja usługi Intune nie jest automatycznie przypisywana do nich. Zamiast tego administrator dzierżawy usługi Intune musi później edytować konto użytkownika w portalu usługi Office 365 w celu przypisania licencji do użytkownika.

Jeśli subskrypcja współużytkuje usługę Azure AD z innymi usługami w chmurze skojarzonymi z Twoją subskrypcją, masz również dostęp do użytkowników dodanych do tych usług. Ci użytkownicy nie mają licencji usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], dopóki licencja nie zostanie przypisana do każdego z nich.

> [!TIP]
> Jeśli opcja przypisywania lub odwoływania licencji usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] jest wyłączona, subskrypcja może obejmować opcje licencjonowania zbiorowego, na przykład opcje dostępne podczas korzystania z pakietu [Enterprise Mobility Suite + Security](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx). Informacje dotyczące przypisywania lub odwoływania licencji zawiera dokumentacja opcji licencjonowania.

## <a name="assign-an-intune-user-license"></a>Przypisywanie licencji użytkownika usługi Intune

[Portal usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) umożliwia ręczne dodawanie użytkowników w chmurze oraz przypisywanie licencji do kont użytkowników w chmurze i kont synchronizowanych z lokalnej usługi Active Directory do usługi Azure AD.

1.  Zaloguj się do [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) przy użyciu poświadczeń administratora dzierżawy, a następnie wybierz pozycję **Osoby** > **Wszyscy użytkownicy**.

2.  Wybierz konto użytkownika, do którego chcesz przypisać licencję użytkownika usługi Intune, a następnie wybierz pozycję **Microsoft Intune** (wersja autonomiczna) lub **Enterprise Mobility Suite**.

3.  Konto użytkownika ma teraz wymagane uprawnienia do korzystania z usługi i rejestrowania urządzeń w systemie zarządzania.

> [!NOTE]
> Użytkownicy będą wyświetlani w konsoli po zarejestrowaniu urządzenia.

### <a name="use-powershell-to-selectively-manage-ems-user-licenses"></a>Selektywne zarządzanie licencjami użytkowników pakietu EMS przy użyciu programu PowerShell
Niektórzy użytkownicy w organizacjach korzystających z pakietu Microsoft Enterprise Mobility + Security (EMS) mogą potrzebować tylko usługi Azure Active Directory — wersja Premium lub usługi Intune w pakiecie EMS. Można przypisać jedną usługę lub podzestaw usług przy użyciu [poleceń cmdlet środowiska PowerShell usługi Azure Active Directory](https://msdn.microsoft.com/library/jj151815.aspx).

Aby selektywnie przypisywać licencje użytkowników dla usług pakietu EMS, należy otworzyć program PowerShell jako administrator na komputerze, na którym zainstalowano [moduł usługi Azure Active Directory dla programu Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule). Program PowerShell można zainstalować na komputerze lokalnym lub serwerze usług ADFS.

Należy utworzyć nową definicję jednostki SKU licencji, która ma zastosowanie tylko do planów żądanej usługi. Aby to zrobić, należy wyłączyć plany, które nie powinny być stosowane. Na przykład można utworzyć definicję jednostki SKU licencji, która nie powoduje przypisania licencji usługi Intune. Aby wyświetlić listę dostępnych usług, wpisz:

    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus

Aby wykluczyć plan usługi Intune, można uruchomić poniższe polecenie. Można użyć tej samej metody do rozszerzenia całej grupy zabezpieczeń lub skorzystać z bardziej szczegółowych filtrów.

**Przykład 1**<br>
Utworzenie nowego użytkownika w wierszu polecenia i przypisanie licencji pakietu EMS bez włączania składnika Intune licencji:

    Connect-MsolService

    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS


Weryfikacja:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

**Przykład 2**<br>
Wyłączenie składnika Intune licencji pakietu EMS dla użytkownika, do którego przypisano już licencję:

    Connect-MsolService

    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -RemoveLicenses IAPProdPartnerTest:EMS

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS

Weryfikacja:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com" .Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)

>[!div class="step-by-step"]

>[&larr; **Synchronizuj użytkowników z Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Organizuj użytkowników i urządzenia** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)  



<!--HONumber=Dec16_HO2-->


