---
# required metadata

title: Rozwiązywanie konfliktów obiektów zasad grupy i zasad usługi Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e76af5b7-e933-442c-a9d3-3b42c5f5868b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Rozwiązywanie konfliktów obiektów zasad grupy i zasad usługi Microsoft Intune
Usługa Intune używa zasad, które ułatwiają zarządzanie ustawieniami na zarządzanych komputerach. Na przykład możesz użyć zasad, aby kontrolować ustawienia Zapory systemu Windows na komputerach. Duża liczba ustawień usługi Intune jest podobnych do ustawień zasad grupy systemu Windows. Jednak czasami te metody mogą wchodzić ze sobą w konflikt.

Gdy wystąpi konflikt, zasady grupy na poziomie domeny mają pierwszeństwo przed zasadami usługi Intune, chyba że komputer nie może zalogować się do domeny. W takim przypadku na komputerze klienckim są stosowane zasady usługi Intune.

## Co zrobić, jeśli używasz zasad grupy
Sprawdź, czy jakiekolwiek zasady, które stosujesz, nie są zarządzane przez zasady grupy. Aby uniknąć konfliktów, możesz wykonać jedno lub wiele z następujących działań:

-   Przed zainstalowaniem klienta usługi Intune przenieś komputery do jednostki organizacyjnej usługi Active Directory, dla której nie zastosowano ustawień zasad grupy. Możesz również zablokować dziedziczenie zasad grupy dla jednostek organizacyjnych, które zawierają komputery zarejestrowane usłudze Intune i dla których nie chcesz stosować ustawień zasad grupy.

-   Użyj filtru WMI lub filtru zabezpieczeń, aby ograniczyć obiekty zasad grupy tylko do komputerów, które nie są zarządzane przez usługę Intune. Odpowiednie informacje i przykłady zawiera sekcja [Jak filtrować istniejące obiekty zasad grupy w celu uniknięcia konfliktów z zasadami usługi Microsoft Intune](resolve-gpo-and-microsoft-intune-policy-conflicts.md#BKMK_Filter) poniżej.

-   Wyłącz lub usuń obiekty zasad grupy, które powodują konflikt z zasadami usługi Intune.

Aby uzyskać więcej informacji na temat usługi Active Directory i zasad grupy systemu Windows, zapoznaj się z dokumentacją systemu Windows Server.

## Jak filtrować istniejące obiekty zasad grupy w celu uniknięcia konfliktów z zasadami usługi Intune
Jeśli zidentyfikowano obiekty zasad grupy, których ustawienia powodują konflikt z zasadami usługi Intune, możesz użyć dowolnej z następujących metod filtrowania do ograniczenia tych obiektów zasad grupy tylko do komputerów, które nie są zarządzane przez usługę Intune.

### Używanie filtrów WMI
Filtry WMI umożliwiają selektywne stosowanie obiektów zasad grupy dla komputerów, które spełniają warunki zapytania. Aby zastosować filtr WMI, wdróż wystąpienie klasy WMI na wszystkich komputerach w przedsiębiorstwie przed zarejestrowaniem jakiegokolwiek komputera w usłudze Intune.

#### Stosowanie filtrów WMI dla obiektu zasad grupy

1.  Utwórz plik obiektu zarządzania, kopiując i wklejając następujący kod do pliku tekstowego, a następnie zapisując go w wybranej lokalizacji pod nazwą **WIT.mof**. Ten plik zawiera wystąpienie klasy WMI do wdrożenia na komputerach, które chcesz zarejestrować w usłudze Intune.

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

2.  Wdróż plik za pomocą skryptu uruchomieniowego lub zasad grupy. Poniżej podano polecenie wdrożenia dla skryptu uruchomieniowego. Wystąpienie klasy WMI należy wdrożyć przed zarejestrowaniem komputerów klienckich w usłudze Intune.

    **C:/Windows/System32/Wbem/MOFCOMP &lt;ścieżka do pliku MOF&gt;\wit.mof**

3.  Uruchom dowolne z poniższych poleceń, aby utworzyć filtry WMI w zależności od tego, czy obiekt zasad grupy do filtrowania ma być stosowany dla komputerów zarządzanych przy użyciu usługi Intune, czy komputerów niezarządzanych przy użyciu usługi Intune.

    -   Dla obiektów zasad grupy, które mają być stosowane dla komputerów niezarządzanych przy użyciu usługi Intune, użyj następującego polecenia:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=0
        ```

    -   Dla obiektów zasad grupy, które mają być stosowane dla komputerów zarządzanych przy użyciu usługi Intune, użyj następującego polecenia:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=1
        ```

4.  Zmodyfikuj obiekt zasad grupy w konsoli zarządzania zasadami grupy, aby zastosować filtr WMI utworzony w poprzednim kroku.

    -   Dla obiektów zasad grupy do stosowania tylko dla komputerów, które mają być zarządzane przy użyciu usługi Intune, zastosuj filtr **WindowsIntunePolicyEnabled=1**..

    -   Dla obiektów zasad grupy do stosowania tylko dla komputerów, które nie mają być zarządzane przy użyciu usługi Intune, zastosuj filtr **WindowsIntunePolicyEnabled=0**.

Aby uzyskać więcej informacji dotyczących sposobu stosowania filtrów WMI w zasadach grupy, zapoznaj się z wpisem w blogu [Filtrowanie zabezpieczeń, filtrowanie WMI i określanie elementów docelowych w preferencjach zasad grupy](http://go.microsoft.com/fwlink/?LinkId=177883).

### Używanie filtrów grupy zabezpieczeń
Zasady grupy umożliwiają zastosowanie obiektów zasad grupy tylko dla grup zabezpieczeń, które są określone w obszarze **Filtrowanie zabezpieczeń** w konsoli zarządzania zasadami grupy dla wybranego obiektu zasad grupy. Domyślnie obiekty zasad grupy są stosowane dla grupy **Użytkownicy uwierzytelnieni**.

-   W przystawce **Użytkownicy i komputery usługi Active Directory** utwórz nową grupę zabezpieczeń zawierającą konta komputerów i użytkowników, które nie mają być zarządzane za pomocą usługi Intune. Możesz ją nazwać na przykład **Nie w usłudze Intune**.

-   W konsoli zarządzania zasadami grupy na karcie **Delegowanie** wybranego obiektu zasad grupy kliknij prawym przyciskiem myszy nową grupę zabezpieczeń, aby delegować odpowiednie uprawnienia **Odczyt** i **Stosowanie zasad grupy** do użytkowników i komputerów w grupie zabezpieczeń. (Uprawnienia**Stosowanie zasad grupy** są dostępne w oknie dialogowym **Zaawansowane** ).

-   Zastosuj nowy filtr grupy zabezpieczeń dla wybranego obiektu zasad grupy i usuń domyślny filtr **Użytkownicy uwierzytelnieni** .

Nową grupę zabezpieczeń należy aktualizować zgodnie ze zmianami rejestracji w usłudze Intune.

### Zobacz także
[Zarządzanie komputerami z systemem Windows przy użyciu usługi Microsoft Intune](manage-windows-pcs-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


