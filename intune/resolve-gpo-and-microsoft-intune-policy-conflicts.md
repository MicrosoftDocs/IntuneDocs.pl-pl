---
title: Rozwiązywanie konfliktów obiektów zasad grupy i zasad usługi Intune
titleSuffix: Microsoft Intune
description: Dowiedz się, jak rozwiązywać konflikty między zasadami grupy i zasadami konfiguracji usługi Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: archived
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e76af5b7-e933-442c-a9d3-3b42c5f5868b
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8ebae39c529571c5f926debcf64b46d6399d770f
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2019
ms.locfileid: "67547953"
---
# <a name="resolve-group-policy-objects-gpo-and-microsoft-intune-policy-conflicts"></a>Rozwiązywanie konfliktów obiektów zasad grupy i zasad usługi Microsoft Intune

[!INCLUDE [classic-portal](includes/classic-portal.md)]

> [!NOTE]
> Informacje w tym temacie dotyczą tylko komputerów z systemem Windows, które są zarządzane jako komputery osobiste przy użyciu oprogramowania klienckiego usługi Intune.

Usługa Intune używa zasad, które ułatwiają zarządzanie ustawieniami na komputerach z systemem Windows. Na przykład możesz użyć zasad, aby kontrolować ustawienia Zapory systemu Windows na komputerach. Wiele ustawień usługi Intune jest podobnych do ustawień konfigurowanych za pomocą zasad grupy systemu Windows. Jednak czasami te dwie metody mogą wchodzić ze sobą w konflikt.

W przypadku wystąpienia konfliktu zasady grupy na poziomie domeny mają pierwszeństwo przed zasadami usługi Intune, chyba że komputer nie może zalogować się do domeny. W takim przypadku na komputerze klienckim są stosowane zasady usługi Intune.

## <a name="what-to-do-if-you-are-using-group-policy"></a>Co zrobić, jeśli używasz zasad grupy
Upewnij się, że zasady, które stosujesz, nie są zarządzane przez zasady grupy. Aby uniknąć konfliktów, możesz użyć jednej lub wielu z następujących metod:

- Przed zainstalowaniem klienta usługi Intune przenieś komputery do jednostki organizacyjnej usługi Active Directory, dla której nie zastosowano ustawień zasad grupy. Możesz również zablokować dziedziczenie zasad grupy dla jednostek organizacyjnych, które zawierają komputery zarejestrowane w usłudze Intune i dla których nie chcesz stosować ustawień zasad grupy.

- Użyj filtru grup zabezpieczeń, aby ograniczyć obiekty zasad grupy tylko do komputerów, które nie są zarządzane przez usługę Intune.

- Wyłącz lub usuń obiekty zasad grupy, które powodują konflikt z zasadami usługi Intune.

Aby uzyskać więcej informacji na temat usługi Active Directory i zasad grupy systemu Windows, zapoznaj się z dokumentacją systemu Windows Server.

## <a name="how-to-filter-existing-gpos-to-avoid-conflicts-with-intune-policy"></a>Jak filtrować istniejące obiekty zasad grupy w celu uniknięcia konfliktów z zasadami usługi Intune
Jeśli zidentyfikowano obiekty zasad grupy, których ustawienia powodują konflikt z zasadami usługi Intune, możesz użyć filtrów grup zabezpieczeń do ograniczenia tych obiektów zasad grupy tylko do komputerów, które nie są zarządzane przez usługę Intune.

<!--- ### Use WMI filters
WMI filters selectively apply GPOs to computers that satisfy the conditions of a query. To apply a WMI filter, deploy a WMI class instance to all PCs in the enterprise before you enroll any PCs in the Intune service.

#### To apply WMI filters to a GPO

1. Create a management object file by copying and pasting the following into a text file, and then saving it to a convenient location as **WIT.mof**. The file contains the WMI class instance that you deploy to PCs that you want to enroll in the Intune service.

    ```
    //Beginning of MOF file.
    #pragma classflags("forceupdate")
    #pragma namespace ("\\\\.\\Root")
    instance of __Namespace
    {
       Name = "WindowsIntune";
    };

    #pragma namespace ("\\\\.\\Root\\WindowsIntune")
    [
       Description("This class defines Microsoft Intune common properties")
    ]
    class WindowsIntune_ManagedNode
    {
       [ read, Description("This defines whether Microsoft Intune Policy is enabled"): DisableOverride ToSubClass ]
       boolean WindowsIntunePolicyEnabled;
       [ read, key, Description("This property defines the version." "Example: 1.0"): ToSubClass ]
       string Version;
    };

    instance of WindowsIntune_ManagedNode
    {
       Version = "1.0";
       WindowsIntunePolicyEnabled = 1;
    };
    ```

2. Use either a startup script or Group Policy to deploy the file. The following is the deployment command for the startup script. The WMI class instance must be deployed before you enroll client PCs in the Intune service.

    **C:/Windows/System32/Wbem/MOFCOMP &lt;path to MOF file&gt;\wit.mof**

3. Run either of the following commands to create the WMI filters, depending on whether the GPO you want to filter applies to PCs that are managed by using Intune or to PCs that are not managed by using Intune.

    - For GPOs that apply to PCs that are not managed by using Intune, use the following:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=0
        ```

    - For GPOs that apply to PCs that are managed by Intune, use the following:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=1
        ```

4. Edit the GPO in the Group Policy Management console to apply the WMI filter that you created in the previous step.

    - For GPOs that should apply only to PCs that you want to manage by using Intune, apply the filter **WindowsIntunePolicyEnabled=1**.

    - For GPOs that should apply only to PCs that you do not want to manage by using Intune, apply the filter **WindowsIntunePolicyEnabled=0**.

For more information about how to apply WMI filters in Group Policy, see the blog post [Security Filtering, WMI Filtering, and Item-level Targeting in Group Policy Preferences](http://go.microsoft.com/fwlink/?LinkId=177883). --->


Możesz zastosować obiekty zasad grupy tylko do grup zabezpieczeń, które są określone w obszarze **Filtrowanie zabezpieczeń** w konsoli zarządzania zasadami grupy dla wybranego obiektu zasad grupy. Domyślnie obiekty zasad grupy są stosowane dla grupy *Użytkownicy uwierzytelnieni*.

- W przystawce **Użytkownicy i komputery usługi Active Directory** utwórz nową grupę zabezpieczeń zawierającą konta komputerów i użytkowników, które nie mają być zarządzane przez usługę Intune. Możesz nazwać tę grupę na przykład *Nie w usłudze Microsoft Intune*.

- W konsoli zarządzania zasadami grupy na karcie **Delegowanie** wybranego obiektu zasad grupy kliknij prawym przyciskiem myszy nową grupę zabezpieczeń, aby delegować odpowiednie uprawnienia **Odczyt** i **Stosowanie zasad grupy** do użytkowników i komputerów w grupie zabezpieczeń. (Uprawnienia**Stosowanie zasad grupy** są dostępne w oknie dialogowym **Zaawansowane** ).

- Zastosuj nowy filtr grupy zabezpieczeń dla wybranego obiektu zasad grupy i usuń domyślny filtr **Użytkownicy uwierzytelnieni** .

Nową grupę zabezpieczeń należy aktualizować zgodnie ze zmianami rejestracji w usłudze Intune.

### <a name="see-also"></a>Zobacz także
[Zarządzanie komputerami osobistymi z systemem Windows przy użyciu usługi Microsoft Intune](manage-windows-pcs-with-microsoft-intune.md)
