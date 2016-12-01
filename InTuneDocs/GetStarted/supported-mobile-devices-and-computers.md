---
title: "Obsługiwane urządzenia przenośne i przeglądarki | Microsoft Intune"
description: "Urządzenia przenośne i komputery obsługiwane przez usługę Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aeeccfa4-0f14-447e-a3df-c8435c8a4bb2
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 149f3a3310907d131affeaad4bd372aa60be9206
ms.openlocfilehash: 80541567c535cfeb7fca3eda3c9143f4b11d7abb


---

# <a name="supported-mobile-devices-and-computers"></a>Obsługiwane urządzenia przenośne i komputery

Możesz zarejestrować następujące typy urządzeń, a następnie zarządzać nimi:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Zarejestrowanie urządzeń daje [te możliwości](/Intune/get-started/choose-how-to-manage-devices).

Komputerami z systemem Windows można też zarządzać przy użyciu oprogramowania klienckiego usługi Intune na komputery. Komputerowe oprogramowanie klienckie usługi Intune obsługuje system Windows 7 i nowsze, z wyjątkiem systemu Windows 10 Home. Zarządzanie komputerami przy użyciu oprogramowania klienckiego zapewnia [następujące możliwości](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

Klienci z pakietem Enterprise Management Suite mogą także użyć usługi Azure Active Directory (Azure AD), aby zarejestrować urządzenia z systemem Windows 10.

## <a name="microsoft-intune-supported-web-browsers"></a>Przeglądarki sieci Web obsługiwane przez usługę Microsoft Intune

Różne zadania administracyjne wymagają użycia jednej z następujących witryn administracyjnych sieci Web.

- [Portal usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Konsola administratora usługi Microsoft Intune](https://admin.manage.microsoft.com/)

> [!Note]
> Przeglądarka Microsoft Edge i przeglądarki dla urządzeń przenośnych nie są obsługiwane przez konsolę administracyjną, ponieważ nie obsługują technologii [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx). Konsola usługi Intune stopniowo odchodzi od technologii Silverlight. Docelowo wszystkie funkcje usługi Intune z zakresu zarządzania urządzeniami przenośnymi i aplikacjami zostaną [udostępnione w nowym portalu Microsoft Azure](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).

|Funkcja usługi Intune |Obsługiwane przeglądarki|
|---------|---------|
|Konsola administracyjna usługi Intune     |  Internet Explorer 10 lub nowsza wersja<br /><br />Google Chrome (wersje poprzedzające wersję 42)<br /><br />Mozilla Firefox z włączonym dodatkiem Silverlight<br /><br />**Uwaga:** przeglądarka Microsoft Edge i przeglądarki dla urządzeń przenośnych nie są obsługiwane w przypadku konsoli administracyjnej.                      
|Portal administracyjny usługi Office 365     |Wszystkie przeglądarki, w tym przeglądarki dla urządzeń przenośnych i zarządzane przeglądarki  |
|Witryna sieci Web Portal firmy     |**Urządzenia przenośne:** należy używać domyślnej przeglądarki sieci Web dla każdej z obsługiwanych platform   <br /><br />**Komputery z systemem Windows:** Internet Explorer 10 lub nowsza wersja albo Microsoft Edge<br /><br />**System Mac OS X 10.9 lub nowszy:** Apple Safari    |

> [!Note]
> Przeglądarka Microsoft Edge i przeglądarki dla urządzeń przenośnych nie są obsługiwane przez konsolę administracyjną, ponieważ nie obsługują technologii [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx). Konsola usługi Intune stopniowo odchodzi od technologii Silverlight. Docelowo wszystkie funkcje usługi Intune z zakresu zarządzania urządzeniami przenośnymi i aplikacjami zostaną [udostępnione w nowym portalu Microsoft Azure](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).

### <a name="office-365-portalhttpgomicrosoftcomfwlinkplinkid698854"></a>[Portal usługi Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)

**Administrator dzierżawy używa tego portalu do zarządzania subskrypcją**, co obejmuje wykonywanie następujących zadań, o ile jest to dozwolone przez rolę administratora:

- Zarządzanie kontami użytkowników w ramach subskrypcji i konfigurowanie synchronizacji katalogów z lokalnej usługi Active Directory.
- Zarządzanie grupami użytkowników zwanymi grupami zabezpieczeń.
- Przypisywanie użytkownikom licencji usługi Intune.
- Konfigurowanie nazwy domeny używanej w ramach subskrypcji. Nazwa domeny określa konto używane przez użytkowników do logowania.
- Zarządzanie informacjami dotyczącymi rozliczeń i zakupów w ramach subskrypcji, w tym liczbą posiadanych licencji lub ilością dostępnego miejsca w magazynie w chmurze.
- Znajdowanie linków umożliwiających wyświetlenie kondycji usługi Intune.
- Administrator dzierżawy może zalogować się do portalu usługi Office 365 w celu zarządzania subskrypcją, nawet jeśli nie ma przypisanej licencji na korzystanie z usługi Intune.
- Dowolny użytkownik, który ma licencję na korzystanie z usługi Intune, ale nie jest administratorem, może za pomocą tego portalu resetować hasło swojego konta i edytować swój profil.
- Aby użytkownik mógł uzyskać dostęp do portalu usługi Office 365, jego konto musi mieć stan logowania **Dozwolone**. Ten stan nie oznacza posiadania licencji na korzystanie z subskrypcji. Domyślnie wszystkie konta użytkowników mają stan **Dozwolone**.


### <a name="microsoft-intune-administrator-consolehttpsmanagemicrosoftcom"></a>[Konsola administratora usługi Microsoft Intune](https://manage.microsoft.com/)

**Administrator usługi korzysta z tego portalu do zarządzania typowymi operacjami**, które obejmują:

- Ustawianie zasad dla komputerów i urządzeń przenośnych.
- Przekazywanie i wdrażania oprogramowania, na przykład aktualizacji i aplikacji.
- Zarządzanie programem Endpoint Protection na komputerach.
- Wyświetlanie stanu urządzeń i uruchamianie raportów.
- Zaloguj się do tego portalu. Aby zalogować się do tego portalu, musisz mieć uprawnienia administratora usługi lub być administratorem dzierżawy z rolą administratora globalnego.


Do tego portalu mogą logować się tylko użytkownicy z uprawnieniami administratora usługi lub administratorzy dzierżawy z rolą administratora globalnego. Aby można było uzyskać dostęp do konsoli administracyjnej, konto musi mieć licencję na korzystanie z usługi Intune i stan logowania **Dozwolone**.



<!--HONumber=Nov16_HO4-->


