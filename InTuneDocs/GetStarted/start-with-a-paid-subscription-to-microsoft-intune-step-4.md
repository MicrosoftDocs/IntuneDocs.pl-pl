---
# required metadata

title: Zarządzanie licencjami usługi Intune | Usługa Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Zarządzanie licencjami usługi Intune
Użytkownik musi mieć licencję na subskrypcję usługi Intune, aby móc zalogować się do usługi i korzystać z niej albo rejestrować swoje urządzenia w systemie zarządzania. Jeśli użytkownik ma licencję, należy do grupy użytkowników usługi [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)]. Do tej grupy należą wszyscy użytkownicy, którzy mają licencję do korzystania z subskrypcji. **Każda licencja użytkownika obsługuje rejestrację maksymalnie 5 urządzeń.**.

## Przypisywanie licencji usługi Intune
Gdy konta użytkowników są synchronizowane z lokalnej usługi Active Directory lub ręcznie dodawane do subskrypcji usług w chmurze za pośrednictwem portalu konta, licencja usługi Intune nie jest automatycznie przypisywana do nich. Zamiast tego administrator dzierżawy usługi Intune musi później edytować konto użytkownika w portalu konta w celu przypisania licencji do użytkownika.

Jeśli subskrypcja współużytkuje usługę Azure AD z innymi usługami w chmurze skojarzonymi z Twoją subskrypcją, masz również dostęp do użytkowników dodanych do tych usług. Ci użytkownicy nie mają licencji usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], dopóki licencja nie zostanie przypisana do każdego z nich.

> [!TIP]
> Jeśli opcja przypisywania lub odwoływania licencji usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] jest wyłączona, subskrypcja może obejmować opcje licencjonowania zbiorowego, na przykład opcje dostępne podczas korzystania z pakietu [Enterprise Mobility Suite](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx). Informacje dotyczące przypisywania lub odwoływania licencji zawiera dokumentacja opcji licencjonowania.

## Przypisywanie licencji użytkownika usługi Intune

**[!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)]** jest używany do ręcznego dodawania użytkowników w chmurze oraz przypisywania licencji do kont użytkowników w chmurze i kont synchronizowanych z lokalnej usługi Active Directory do usługi Azure AD.

1.  Zaloguj się do portalu konta usługi Intune przy użyciu poświadczeń administratora dzierżawy.

2.  Wybierz konto użytkownika, do którego chcesz przypisać licencję użytkownika usługi Intune, i zaznacz pole wyboru **Microsoft Intune** we właściwościach konta użytkownika.

3.  Konto użytkownika zostanie dodane do grupy użytkowników usługi Microsoft Intune uprawnionych do korzystania z usługi i rejestrowania urządzeń w systemie zarządzania.

### Selektywne zarządzanie licencjami użytkowników pakietu EMS przy użyciu programu PowerShell
Niektórzy użytkownicy w organizacjach korzystających z pakietu EMS (Enterprise Mobility Suite) firmy Microsoft mogą wymagać tylko usługi Azure Active Directory — wersja Premium lub usługi Intune w pakiecie EMS. Można przypisać jedną usługę lub podzestaw usług przy użyciu [poleceń cmdlet środowiska PowerShell usługi Azure Active Directory](https://msdn.microsoft.com/library/jj151815.aspx).. 

Aby selektywnie przypisywać licencje użytkowników dla usług pakietu EMS, należy otworzyć program PowerShell jako administrator na komputerze, na którym zainstalowano [moduł usługi Azure Active Directory dla programu Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule). Program PowerShell można zainstalować na komputerze lokalnym lub serwerze usług ADFS.

Należy utworzyć nową definicję jednostki SKU licencji, która ma zastosowanie tylko do planów żądanej usługi. Aby to zrobić, należy wyłączyć plany, które nie powinny być stosowane. Na przykład można utworzyć definicję jednostki SKU licencji, która nie powoduje przypisania licencji usługi Intune. Aby wyświetlić listę dostępnych usług, wpisz:
 
    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus 

Aby wykluczyć plan usługi Intune, można uruchomić poniższe polecenie. Można użyć tej samej metody do rozszerzenia całej grupy zabezpieczeń lub skorzystać z bardziej szczegółowych filtrów. 

**Przykład 1**
Utworzenie nowego użytkownika w wierszu polecenia i przypisanie licencji pakietu EMS bez włączania składnika Intune licencji:

    Connect-MsolService 
        
    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US
    
    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS 
    

Weryfikacja:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

**Przykład 2**
Wyłączenie składnika Intune licencji pakietu EMS dla użytkownika, do którego przypisano już licencję:

    Connect-MsolService 
    
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -RemoveLicenses IAPProdPartnerTest:EMS
    
    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS
 
Weryfikacja:
 
    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com" .Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)

### Następne kroki
Gratulacje! Krok 4 *przewodnika Szybki start dotyczącego usługi Intune* został ukończony..
>[!div class="step-by-step"]

>[&larr; **Synchronizowanie użytkowników z usługą Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Organizowanie użytkowników i urządzeń** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)  


<!--HONumber=May16_HO1-->


