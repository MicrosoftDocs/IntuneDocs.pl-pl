---
title: "Zarządzanie komputerami przy użyciu oprogramowania klienckiego | Microsoft Docs"
description: "Zarządzaj komputerami z systemem Windows, instalując oprogramowanie klienckie usługi Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 2e7062169ceb855f03a13d1afb4b4de41af593ac
ms.openlocfilehash: 10ba007095182c9cb07710656ba5f275e254d92e
ms.lasthandoff: 02/15/2017


---

# <a name="manage-windows-pcs-with-intune-pc-client-software"></a>Zarządzanie komputerami z systemem Windows przy użyciu komputerowego oprogramowania klienckiego usługi Intune
[Rejestrowanie komputerów z systemem Windows jako urządzeń przenośnych](set-up-windows-device-management-with-microsoft-intune.md) jest preferowaną metodą rejestrowania komputerów z systemem Windows w usłudze Intune, ale można też wybrać rejestrowanie komputerów z systemem Windows i zarządzanie nimi poprzez zainstalowanie oprogramowania klienckiego usługi Intune zgodnie z opisem w niniejszym temacie.

Usługa Intune zarządza komputerami z systemem Windows za pomocą zasad, podobnie jak robią to obiekty zasad grupy Usług domenowych Active Directory (AD DS) systemu Windows Server. Jeśli planujesz zarządzać komputerami przyłączonymi do domeny usługi Active Directory przy użyciu usługi Intune, [upewnij się, że zasady usługi Intune nie powodują konfliktów z obiektami zasad grupy](resolve-gpo-and-microsoft-intune-policy-conflicts.md) stosowanymi w organizacji. Więcej informacji na temat [obiektów zasad grupy](https://technet.microsoft.com/library/hh147307.aspx).

## <a name="policies-and-app-deployments-for-the-intune-software-client"></a>Zasady i wdrożenia aplikacji dla oprogramowania klienckiego usługi Intune

Oprogramowanie klienckie usługi Intune obsługuje [możliwości z zakresu zarządzania sprzyjające ochronie komputerów](policies-to-protect-windows-pcs-in-microsoft-intune.md), umożliwiając zarządzanie aktualizacjami oprogramowania, zaporą systemu Windows i programem Endpoint Protection. Komputery zarządzane przy użyciu oprogramowania klienckiego usługi Intune nie mogą być jednak celem innych zasad usługi Intune, w tym ustawień zasad systemu **Windows** specyficznych dla zarządzania urządzeniami przenośnymi. 

Korzystając z oprogramowania klienckiego usługi Intune do zarządzania komputerami z systemem Windows, można użyć tylko zasad wyświetlanych w obszarze **Zarządzanie komputerem**.

  ![Wybierz szablon dla nowej zasady dotyczącej komputera z systemem Windows](../media/select-template-for-pc-policy.png)

Szczegółowe opisy zasad, które możesz ustawiać, znajdują się w następujących artykułach:

- [Stosowanie zasad w celu ochrony komputerów z systemem Windows, na których działa oprogramowanie klienckie usługi Intune](https://docs.microsoft.com/intune/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)
- [Zapewnianie aktualności oprogramowania na komputerach z systemem Windows za pomocą aktualizacji w usłudze Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)
- [Ochrona komputerów z systemem Windows przy użyciu zasad Zapory systemu Windows w usłudze Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)
- [Zabezpieczanie komputerów z systemem Windows przy użyciu programu Endpoint Protection dla usługi Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

Ponadto podczas wdrażania aplikacji można użyć tylko Instalatora Windows (.exe i .msi).

  ![Wybierz platformę i lokalizację plików oprogramowania klienta](../media/select-platform-of-software-files-for-pc-agent.png)

> [!NOTE]
> Urządzeniami z systemem Windows 8.1 lub nowszym można zarządzać jako komputerami za pomocą oprogramowania klienckiego usługi Intune lub jako urządzeniami przenośnymi za pomocą funkcji zarządzania urządzeniami przenośnymi (MDM). Nie można używać obu metod jednocześnie, należy więc dobrze zastanowić się przed podjęciem decyzji o zarządzaniu komputerami przy użyciu oprogramowania klienckiego usługi Intune. Ten temat dotyczy tylko zarządzania urządzeniami jako komputerami przez uruchamianie oprogramowania klienckiego usługi Intune.

## <a name="requirements-for-intune-pc-client-management"></a>Wymagania dotyczące funkcji zarządzania komputerami przy użyciu klienta usługi Intune

**Sprzęt**: poniżej podano minimalne wymagania dotyczące sprzętu w przypadku instalowania oprogramowania klienckiego usługi Intune:

|Wymaganie|Więcej informacji|
|---------------|--------------------|
|Sieć|Klient wymaga komputera z połączeniem z Internetem.|
|Procesor i pamięć|Należy zapoznać się z wymaganiami dotyczącymi procesora i pamięci RAM dla systemu operacyjnego komputera.|
|Miejsce na dysku|200 MB dostępnego miejsca na dysku przed zainstalowaniem oprogramowania klienckiego.|

**Oprogramowanie**: poniżej podano wymagania dotyczące oprogramowania w przypadku instalowania oprogramowania klienckiego:

|Wymaganie|Więcej informacji|
|---------------|--------------------|
|System operacyjny | Urządzenie z systemem Windows Vista lub nowszym. </br></br>**Wersje Home Edition nie są obsługiwane.**|
|Uprawnienia administracyjne|Konto używane do instalacji oprogramowania klienckiego musi mieć uprawnienia administratora lokalnego na danym urządzeniu.|
|Instalator Windows w wersji 3.1|Na komputerze musi być dostępny Instalator Windows w wersji 3.1 lub nowszej.<br /><br />Aby wyświetlić wersję Instalatora Windows na komputerze:<br /><br />  Na komputerze kliknij prawym przyciskiem myszy pozycję **%windir%\System32\msiexec.exe**, a następnie kliknij polecenie **Właściwości**.<br /><br />Najnowszą wersję Instalatora Windows można pobrać ze strony [pakietów redystrybucyjnych Instalatora Windows](http://go.microsoft.com/fwlink/?LinkID=234258) w witrynie Microsoft Developer Network w sieci Web.|
|Usunięcie niezgodnego oprogramowania klienckiego|Przed zainstalowaniem oprogramowania klienckiego usługi Intune należy odinstalować wszelkie oprogramowanie klienckie programu Configuration Manager, Operations Manager, Operations Management Suite i Service Manager z tego komputera.|

## <a name="computer-management-capabilities-with-the-intune-client-software"></a>Funkcje zarządzania komputerami przy użyciu oprogramowania klienckiego usługi Intune

Po zainstalowaniu oprogramowania klienckiego usługi Intune dostępne są możliwości zarządzania takie jak: 

- [Zarządzanie aplikacjami](deploy-apps-in-microsoft-intune.md)

- [Monitorowanie w czasie rzeczywistym i program Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) — program Endpoint Protection to dokładnie to samo co Windows Defender. Program Endpoint Protection znajduje zastosowanie w systemach Windows 7 i Windows 8. W systemie Windows 10 i nowszych nazwa produktu została zmieniona na Windows Defender.

- [Zarządzanie ustawieniami Zapory systemu Windows](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md), spis sprzętu i oprogramowania, zdalne sterowanie (za pośrednictwem żądań pomocy zdalnej)

- [Ustawienia aktualizacji oprogramowania](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)

- Raportowanie ustawień zgodności

W konsoli administracyjnej usługi Intune niektóre sekcje, takie jak „Aktualizacje”, „Ochrona” i „Licencje”, pojawiają się tylko w przypadku urządzeń zarejestrowanych za pomocą oprogramowania klienckiego usługi Intune.

  ![Elementy konsoli administratora, które są widoczne tylko dla komputera klienta](../media/admin-console-settings-only-for-pc-agent.png)

Konsoli administracyjnej usługi Intune można także używać do wykonywania innych typowych zadań z zakresu zarządzania komputerami na komputerach z systemem Windows i zainstalowanym oprogramowaniem klienckim:

-   Wyświetlanie informacji ze spisu sprzętu i oprogramowania na potrzeby zarządzanych komputerów
-   Zdalne ponowne uruchamianie komputera
-   Wycofywanie komputera w celu odinstalowania oprogramowania klienckiego oraz usuwanie go z zarządzania przy użyciu usługi Intune
-   Łączenie użytkowników z określonymi komputerami zarządzanymi
-   Odpowiadanie na żądania pomocy zdalnej

Aby uzyskać więcej informacji o powyższych, zobacz [typowe zadania zarządzania komputerem](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).

## <a name="management-limitations-of-the-intune-client-software"></a>Ograniczenia oprogramowania klienckiego usługi Intune dotyczące zarządzania

Niektóre opcje zarządzania, których można użyć do zarządzania komputerami jako urządzeniami przenośnymi, nie mogą zostać użyte w przypadku komputerów zarządzanych przy użyciu oprogramowania klienckiego usługi Intune:

-   Pełne czyszczenie (selektywne czyszczenie jest dostępne)

-   Dostęp warunkowy

## <a name="help-with-troubleshooting"></a>Pomoc w zakresie rozwiązywania problemów

Agent oprogramowania klienckiego usługi Intune zwykle działa w tle bez konieczności interakcji z użytkownikami ani rozwiązywania problemów. W razie potrzeby rozwiązania problemów z zarządzaniem komputerami można sprawdzić dzienniki. Oprogramowanie klienckie usługi Intune wraz z odpowiednimi dziennikami znajduje się w katalogu %Program Files%\Microsoft\OnlineManagement.

Można również przejrzeć artykuł [Rozwiązywanie problemów z instalacją klientów w usłudze Microsoft Intune](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune) w celu zapoznania się z informacjami na temat potencjalnych problemów oraz ich rozwiązań i obejść.

