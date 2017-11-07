---
title: "Przypisywanie licencji usługi Intune"
description: "Przypisywanie licencji do użytkowników dla subskrypcji usługi Intune"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ff32d7dffa933ff79220773bd5216b039620db44
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2017
---
# <a name="assign-intune-licenses-to-your-user-accounts"></a>Przypisywanie licencji usługi Intune do kont użytkowników

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Bez względu na to, czy zamierzasz ręcznie dodać użytkowników, czy też przeprowadzić synchronizację lokalnej usługi Active Directory, zanim użytkownicy będą mogli rejestrować swoje urządzenia w usłudze Intune, musisz najpierw przypisać do każdego z użytkowników licencję usługi Intune.

## <a name="assign-an-intune-license-in-the-office-365-admin-center"></a>Przypisywanie licencji usługi Intune w Centrum administracyjnym usługi Office 365

[Portal usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) umożliwia ręczne dodawanie użytkowników w chmurze oraz przypisywanie licencji zarówno do kont użytkowników w chmurze, jak i kont synchronizowanych z lokalnej usługi Active Directory do usługi Azure AD.

1.  Zaloguj się do [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) przy użyciu poświadczeń administratora dzierżawy, a następnie wybierz pozycję **Użytkownicy** > **Aktywni użytkownicy**.

2.  Wybierz konto użytkownika, do którego chcesz przypisać licencję użytkownika usługi Intune, a następnie wybierz kolejno pozycje **Licencje produktów** > **Edytuj**.

3.  Przełącz wartość opcji **Intune** lub **Enterprise Mobility + Security** na **Wł.** i wybierz opcję **Zapisz**.

  ![Obraz przypisywania licencji produktu w portalu usługi Office 365.](./media/office-assign-license.png)

4. Konto użytkownika ma teraz uprawnienia wymagane do korzystania z usługi i rejestrowania urządzeń w systemie zarządzania.

> [!NOTE]
> Użytkownicy będą wyświetlani w konsoli administratora dopiero po zarejestrowaniu przez nich urządzenia. Ponadto możesz wybrać grupę użytkowników do jednoczesnej edycji, a następnie wybrać opcję dodania lub zastąpienia licencji dla wszystkich wybranych użytkowników.

## <a name="use-school-data-sync-to-assign-licenses-to-users-in-intune-for-education"></a>Używanie narzędzia School Data Sync w celu przypisywania licencji do użytkowników w usłudze Intune for Education
Jeśli reprezentujesz instytucję edukacyjną, możesz użyć narzędzia School Data Sync (SDS), aby przypisać licencje usługi Intune for Education do synchronizowanych użytkowników. Wystarczy zaznaczyć pole wyboru Intune for Education podczas konfigurowania profilu SDS.  

![Obraz ustawienia profilu SDS](./media/i4e-sds-profile-setup-setting.png)

Po przypisaniu licencji Intune for Education upewnij się, że przypisano również licencję Intune A Direct.

![Obraz przedstawiający konfigurację licencji produktu](./media/i4e-set-licenses.png)

Aby dowiedzieć się więcej na temat narzędzia SDS, zobacz [omówienie narzędzia School Data Sync](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91?ui=en-US&rs=en-US&ad=US).

## <a name="how-user-and-device-licenses-affect-access-to-services"></a>W jaki sposób licencje użytkownika i urządzeń wpływają na dostęp do usług
* Każdy **użytkownik**, który ma przypisaną licencję na oprogramowanie, może uzyskać dostęp i korzystać z usług online i powiązanego oprogramowania (łącznie z oprogramowaniem System Center) do zarządzania aplikacjami maksymalnie na 15 urządzeniach.
* Na każdym **urządzeniu**, które ma przypisaną licencję na oprogramowanie, dowolna liczba użytkowników może uzyskać dostęp i korzystać z usług online i powiązanego oprogramowania (łącznie z oprogramowaniem System Center).
* Jeśli urządzenie jest używane przez więcej niż jednego użytkownika, każde z nich wymaga licencji na oprogramowanie lub wszyscy użytkownicy wymagają licencji użytkownika na oprogramowanie.

## <a name="use-powershell-to-selectively-manage-ems-user-licenses"></a>Selektywne zarządzanie licencjami użytkowników pakietu EMS przy użyciu programu PowerShell
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

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -LicenseOptions $CustomEMS

Weryfikacja:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)
