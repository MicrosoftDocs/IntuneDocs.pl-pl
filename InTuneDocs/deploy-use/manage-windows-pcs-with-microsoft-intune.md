---
title: "Zarządzanie komputerami przy użyciu oprogramowania klienckiego | Microsoft Docs"
description: "Zarządzaj komputerami z systemem Windows, instalując oprogramowanie klienckie usługi Intune."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 08/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3d2f3a7233ea7a5127baf5a08be1ccb41f717244
ms.openlocfilehash: 4344251ede6d8cc338d84782d224d87fd78d5bd8


---

# <a name="manage-windows-pcs-with-intune-pc-client-software"></a>Zarządzanie komputerami z systemem Windows przy użyciu komputerowego oprogramowania klienckiego usługi Intune
Zamiast [rejestrować komputery z systemem Windows jako urządzenia przenośne](set-up-windows-device-management-with-microsoft-intune.md) możesz je rejestrować i zarządzać nimi poprzez zainstalowanie oprogramowania klienckiego usługi Intune.

Usługa Intune zarządza komputerami z systemem Windows za pomocą zasad, podobnie jak robią to obiekty zasad grupy Usług domenowych Active Directory (AD DS) systemu Windows Server. Jeśli planujesz zarządzać komputerami przyłączonymi do domeny usługi Active Directory przy użyciu usługi Intune, [upewnij się, że zasady usługi Intune nie powodują konfliktów z obiektami zasad grupy](resolve-gpo-and-microsoft-intune-policy-conflicts.md) stosowanymi w organizacji.

Oprogramowanie klienckie usługi Intune obsługuje [możliwości z zakresu zarządzania sprzyjające ochronie komputerów](policies-to-protect-windows-pcs-in-microsoft-intune.md), umożliwiając zarządzanie aktualizacjami oprogramowania, zaporą systemu Windows i programem Endpoint Protection. Komputery zarządzane przy użyciu oprogramowania klienckiego usługi Intune nie mogą być jednak celem innych zasad usługi Intune, w tym ustawień zasad systemu **Windows** specyficznych dla zarządzania urządzeniami przenośnymi.

> [!NOTE]
> Urządzeniami z systemem Windows 8.1 lub nowszym można zarządzać jako komputerami za pomocą klienta usługi Intune lub jako urządzeniami przenośnymi za pomocą funkcji zarządzania urządzeniami przenośnymi (MDM). Nie można równocześnie używać obu tych metod. Ten temat dotyczy tylko zarządzania urządzeniami jako komputerami przez uruchamianie oprogramowania klienckiego usługi Intune.

## <a name="requirements-for-intune-pc-client-management"></a>Wymagania dotyczące funkcji zarządzania komputerami przy użyciu klienta usługi Intune

**Sprzęt**: Poniżej podano minimalne wymagania dotyczące sprzętu w przypadku instalowania klienta usługi Intune:

|Wymaganie|Więcej informacji|
|---------------|--------------------|
|Sieć|Klient wymaga komputera z połączeniem z Internetem.|
|Procesor i pamięć|Należy zapoznać się z wymaganiami dotyczącymi procesora i pamięci RAM dla systemu operacyjnego komputera.|
|Miejsce na dysku|200 MB dostępnego miejsca na dysku przed zainstalowaniem oprogramowania klienckiego.|

**Oprogramowanie**: Poniżej podano wymagania dotyczące oprogramowania w przypadku instalowania klienta:

|Wymaganie|Więcej informacji|
|---------------|--------------------|
|System operacyjny | Urządzenie z systemem Windows Vista lub nowszym. Wersje Home Edition nie są obsługiwane.|
|Uprawnienia administracyjne|Konto używane do instalacji oprogramowania klienckiego musi mieć uprawnienia administratora lokalnego na danym urządzeniu.|
|Instalator Windows w wersji 3.1|Na komputerze musi być dostępny Instalator Windows w wersji 3.1 lub nowszej.<br /><br />Aby wyświetlić wersję Instalatora Windows na komputerze:<br /><br />  Na komputerze kliknij prawym przyciskiem myszy pozycję **%windir%\System32\msiexec.exe**, a następnie kliknij polecenie **Właściwości**.<br /><br />Najnowszą wersję Instalatora Windows można pobrać ze strony [pakietów redystrybucyjnych Instalatora Windows](http://go.microsoft.com/fwlink/?LinkID=234258) w witrynie Microsoft Developer Network w sieci Web.|
|Usunięcie niezgodnego oprogramowania klienckiego|Przed zainstalowaniem oprogramowania klienckiego usługi Intune należy odinstalować wszelkie oprogramowanie klienckie programu Configuration Manager, Operations Manager, Operations Management Suite i Service Manager z tego komputera.|

## <a name="computer-management-with-the-intune-computer-client"></a>Zarządzanie komputerami przy użyciu usługi klienta komputera z usługą Intune
Po zainstalowaniu oprogramowania klienckiego usługi Intune dostępne są możliwości zarządzania takie jak: 

- [Zarządzanie aplikacjami](deploy-apps-in-microsoft-intune.md)

- [Monitorowanie w czasie rzeczywistym i program Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)

- [Zarządzanie ustawieniami Zapory systemu Windows](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md), spis sprzętu i oprogramowania, zdalne sterowanie (za pośrednictwem żądań pomocy zdalnej)

- [Ustawienia aktualizacji oprogramowania](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)

- Raportowanie ustawień zgodności

Niektóre opcje zarządzania dostępne dla komputerów zarządzanych jako urządzenia przenośne są niedostępne dla komputerów zarządzanych przez oprogramowanie klienckie. Dotyczy to następujących opcji zarządzania:

-   Pełne czyszczenie (selektywne czyszczenie jest dostępne)

-   Dostęp warunkowy

-   Zasady systemu Windows inne niż zasady **zarządzania komputerem**

  ![Szablon zasad dla komputerów z systemem Windows](../media/pc_policy_template.png)

Oprócz akcji agenta klienta usługi Intune wykonywanych lokalnie na poszczególnych komputerach, można użyć konsoli administratora usługi Intune do wykonywania innych [typowych zadań zarządzania komputerami](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) na komputerach z systemem Windows z zainstalowanym klientem. Te zadania obejmują:

-   Wyświetlanie informacji ze spisu sprzętu i oprogramowania na potrzeby zarządzanych komputerów

-   Zdalne ponowne uruchamianie komputera

-   Wycofywanie komputera w celu odinstalowania oprogramowania klienckiego oraz usuwanie go z zarządzania przy użyciu usługi Intune

-   Łączenie użytkowników z określonymi komputerami zarządzanymi

-   Odpowiadanie na żądania pomocy zdalnej

Agent klienta usługi Intune zwykle działa w tle bez konieczności interakcji z użytkownikami ani rozwiązywania problemów. Jeśli jednak potrzebujesz pomocy w rozwiązywaniu problemów z zarządzaniem komputerami, możesz skorzystać z kilku [dostępnych zasobów umożliwiających ich rozwiązanie](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune).



<!--HONumber=Dec16_HO3-->


