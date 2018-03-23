---
title: Przypisywanie licencji usługi Microsoft Intune
description: Przypisanie użytkownikom licencji umożliwiających rejestrowanie w usłudze Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 67d12c748c5f4daabcb64eff7a154455b39a57d0
ms.sourcegitcommit: 820f950d1fc80b1eb5db1b0cf77f44d92a969951
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2018
---
# <a name="assign-licenses-to-users-so-they-can-enroll-devices-in-intune"></a>Przypisanie użytkownikom licencji umożliwiających rejestrowanie urządzeń w usłudze Intune

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Bez względu na to, czy zamierzasz ręcznie dodać użytkowników, czy też przeprowadzić synchronizację lokalnej usługi Active Directory, zanim użytkownicy będą mogli rejestrować swoje urządzenia w usłudze Intune, musisz najpierw przypisać do każdego z użytkowników licencję usługi Intune. Aby uzyskać listę licencji, zobacz [Licencje, które obejmują usługę Intune](licenses.md).

## <a name="assign-an-intune-license-in-the-office-365-admin-center"></a>Przypisywanie licencji usługi Intune w Centrum administracyjnym usługi Office 365

[Portal usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) umożliwia ręczne dodawanie użytkowników w chmurze oraz przypisywanie licencji zarówno do kont użytkowników w chmurze, jak i kont synchronizowanych z lokalnej usługi Active Directory do usługi Azure AD.

1.  Zaloguj się do [portalu usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) przy użyciu poświadczeń administratora dzierżawy, a następnie wybierz pozycję **Użytkownicy** > **Aktywni użytkownicy**.

2.  Wybierz konto użytkownika, do którego chcesz przypisać licencję użytkownika usługi Intune, a następnie wybierz kolejno pozycje **Licencje produktów** > **Edytuj**.

3.  Przełącz wartość opcji **Intune** lub **Enterprise Mobility + Security** na **Wł.** i wybierz opcję **Zapisz**.

  ![Zrzut ekranu przedstawiający sekcję Licencje produktów w portalu usługi Office 365.](./media/office-assign-license.png)

4. Konto użytkownika ma teraz uprawnienia wymagane do korzystania z usługi i rejestrowania urządzeń w systemie zarządzania.

> [!NOTE]
> Użytkownicy będą wyświetlani w konsoli administratora dopiero po zarejestrowaniu przez nich urządzenia. Ponadto możesz wybrać grupę użytkowników do jednoczesnej edycji, a następnie wybrać opcję dodania lub zastąpienia licencji dla wszystkich wybranych użytkowników.

## <a name="use-school-data-sync-to-assign-licenses-to-users-in-intune-for-education"></a>Używanie narzędzia School Data Sync w celu przypisywania licencji do użytkowników w usłudze Intune for Education
Jeśli reprezentujesz instytucję edukacyjną, możesz użyć narzędzia School Data Sync (SDS), aby przypisać licencje usługi Intune for Education do synchronizowanych użytkowników. Wystarczy zaznaczyć pole wyboru Intune for Education podczas konfigurowania profilu SDS.  

![Zrzut ekranu przedstawiający ustawienie profilu SDS](./media/i4e-sds-profile-setup-setting.png)

Po przypisaniu licencji Intune for Education upewnij się, że przypisano również licencję Intune A Direct.

![Zrzut ekranu przedstawiający konfigurację licencji produktu](./media/i4e-set-licenses.png)

Aby dowiedzieć się więcej na temat narzędzia SDS, zobacz [omówienie narzędzia School Data Sync](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91).

## <a name="how-user-and-device-licenses-affect-access-to-services"></a>W jaki sposób licencje użytkownika i urządzeń wpływają na dostęp do usług
* Każdy **użytkownik**, który ma przypisaną licencję na oprogramowanie, może uzyskać dostęp i korzystać z usług online i powiązanego oprogramowania (łącznie z oprogramowaniem System Center) do zarządzania aplikacjami maksymalnie na 15 urządzeniach.
* Na każdym **urządzeniu**, które ma przypisaną licencję na oprogramowanie, dowolna liczba użytkowników może uzyskać dostęp i korzystać z usług online i powiązanego oprogramowania (łącznie z oprogramowaniem System Center).
* Jeśli urządzenie jest używane przez więcej niż jednego użytkownika, każde z nich wymaga licencji na oprogramowanie lub wszyscy użytkownicy wymagają licencji użytkownika na oprogramowanie.

## <a name="understanding-the-type-of-licenses-you-have-purchased"></a>Opis typu zakupionych licencji

Sposób zakupu usługi Intune określa informacje o subskrypcji:

- Jeśli usługa Intune została zakupiona w ramach umowy Enterprise Agreement, informacje o subskrypcji można znaleźć w portalu licencji zbiorczych, w obszarze **Subskrypcje**.
- Jeśli usługę Intune zakupiono za pośrednictwem dostawcy rozwiązań w chmurze, skontaktuj się z odsprzedawcą.
- Jeśli usługę Intune zakupiono przy użyciu numeru karty kredytowej lub faktury, licencje będą oparte na użytkownikach.




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
