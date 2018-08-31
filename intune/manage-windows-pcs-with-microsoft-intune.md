---
title: Zarządzanie komputerami przy użyciu oprogramowania klienckiego
titlesuffix: Microsoft Intune
description: Zarządzaj komputerami z systemem Windows, instalując oprogramowanie klienckie usługi Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic-keep
ms.openlocfilehash: 5a248345a40cd7cfcff3883643562923f9535d3b
ms.sourcegitcommit: 40b1d82df99f09a75a17065cdd0e84d8038f460a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "41910634"
---
# <a name="manage-windows-pcs-as-computers-via-intune-software-client"></a>Zarządzanie komputerami z systemem Windows przy użyciu oprogramowania klienckiego usługi Intune

[!INCLUDE [classic-portal](includes/classic-portal.md)]

> [!NOTE]
> Możesz użyć usługi Microsoft Intune do zarządzania komputerami z systemem Windows albo [jako urządzeniami przenośnymi z wykorzystaniem zarządzania urządzeniami przenośnymi (MDM)](windows-enroll.md), albo jako komputerami z wykorzystaniem oprogramowania klienckiego usługi Intune zgodnie z poniższym opisem. Jednak firma Microsoft zaleca, aby klienci [używali rozwiązania MDM do zarządzania](windows-enroll.md) zawsze, gdy jest to możliwe.

Usługa Intune zapewnia organizacjom kompleksowe rozwiązanie do zarządzania urządzeniami przenośnymi. Usługa Intune może zarządzać komputerami z systemem Windows jako urządzeniami przenośnymi przy użyciu nowoczesnych funkcji zarządzania urządzeniami wbudowanych w systemie operacyjnym Windows 10. Aby spełnić wymagania organizacji związane z zarządzaniem, usługa Intune może również zarządzać komputerami z systemem Windows jako komputerami przy użyciu oprogramowania klienckiego usługi Intune. W tej metodzie zarządzania używa się funkcji tradycyjnego zarządzania komputerami ze starszej wersji systemu operacyjnego Windows.

Oprogramowanie klienckie usługi Intune jest najbardziej odpowiednie dla komputerów z systemem Windows z zainstalowanymi starszymi wersjami systemów operacyjnych, takimi jak Windows 7, którymi nie można zarządzać jako urządzeniami przenośnymi. Oprogramowanie klienckie usługi Intune używa takich funkcji zarządzania jak zasady grupy w celu zarządzania komputerami z chmury.

Usługa Intune obsługuje zarządzanie komputerami z systemem Windows jako komputerami przy użyciu oprogramowania klienckiego dla maksymalnie 7000 komputerów. W przypadku większych wdrożeń zarządzaj komputerami z systemem Windows 10 jako urządzeniami przenośnymi. Wszystkie wersje usługi Intune i aktualizacje systemu Windows 10 obejmują funkcje zarządzania oparte na architekturze zarządzania urządzeniami przenośnymi. Zdecydowanie zaleca się wdrożenie w organizacji urządzeń z systemem Windows 10 zarządzanych jako urządzenia przenośne.


> [!NOTE]
> Urządzeniami z systemem Windows 8.1 lub nowszym można zarządzać jako komputerami przy użyciu oprogramowania klienckiego usługi Intune lub jako urządzeniami przenośnymi. Nie można używać obu tych metod na tym samym urządzeniu. Przed podjęciem decyzji o zarządzaniu komputerami przy użyciu oprogramowania klienckiego usługi Intune należy dobrze się zastanowić. Ten temat dotyczy tylko zarządzania urządzeniami jako komputerami przez uruchamianie oprogramowania klienckiego usługi Intune.

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
|System operacyjny | Urządzenie z systemem Windows 7 z dodatkiem SP1 oraz z systemem Windows 8.1 lub nowszym. </br></br>**Wersje Home Edition nie są obsługiwane.**|
|Uprawnienia administracyjne|Konto używane do instalacji oprogramowania klienckiego musi mieć uprawnienia administratora lokalnego na danym urządzeniu.|
|Instalator Windows w wersji 3.1|Na komputerze musi być dostępny Instalator Windows w wersji 3.1 lub nowszej.<br /><br />Aby wyświetlić wersję Instalatora Windows na komputerze:<br /><br />  Na komputerze kliknij prawym przyciskiem myszy pozycję **%windir%\System32\msiexec.exe**, a następnie kliknij polecenie **Właściwości**.<br /><br />Najnowszą wersję Instalatora Windows można pobrać ze strony [pakietów redystrybucyjnych Instalatora Windows](http://go.microsoft.com/fwlink/?LinkID=234258) w witrynie Microsoft Developer Network w sieci Web.|
|Usunięcie niezgodnego oprogramowania klienckiego|Przed zainstalowaniem oprogramowania klienckiego usługi Intune należy odinstalować wszelkie oprogramowanie klienckie programu Configuration Manager, Operations Manager i Service Manager z tego komputera.|

## <a name="deploying-the-intune-software-client"></a>Wdrażanie oprogramowania klienckiego usługi Intune
Jako administrator usługi Intune możesz udostępnić użytkownikom oprogramowanie klienckie usługi Intune na kilka sposobów. Aby uzyskać instrukcje, zobacz temat [Instalowanie klienta oprogramowania usługi Intune na komputerach z systemem Windows](install-the-windows-pc-client-with-microsoft-intune.md).

## <a name="computer-management-capabilities-with-the-intune-client-software"></a>Funkcje zarządzania komputerami przy użyciu oprogramowania klienckiego usługi Intune
W większości przypadków będziesz rejestrować urządzenia w usłudze Microsoft Intune, co zapewnia większe możliwości. Możesz jednak także zarządzać komputerami, korzystając z klienta oprogramowania usługi Intune, który zapewnia następujące funkcje:

-   **[Zarządzanie aktualizacjami oprogramowania](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)** — aktualizowanie komputerów i zarządzanie harmonogramem stosowania aktualizacji.

-   **[Zasady Zapory systemu Windows](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md)** — zapewnianie, że żaden komputer używany w firmie nie ma nieaktywnej ani nieprawidłowo skonfigurowanej Zapory systemu Windows.

-   **[Ochrona przed złośliwym oprogramowaniem](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)** — usługa Intune obejmuje program Endpoint Protection, który pomaga chronić komputery przed złośliwym oprogramowaniem.

-   **[Pomoc zdalna](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)** — usługa Intune umożliwia użytkownikom kontaktowanie się z pracownikami działu pomocy technicznej IT, którzy mogą udzielić im pomocy przy użyciu funkcji pulpitu zdalnego dostępnej w usłudze Intune (wymagane jest oprogramowanie TeamViewer).

-   **[Zarządzanie licencjami na oprogramowanie](manage-license-agreements-for-windows-pc-software-in-microsoft-intune.md)** — śledzenie liczby dostępnych licencji na oprogramowanie oraz liczby dostępnych licencji będących w użyciu.
-   **[Wdrażanie aplikacji](add-apps-for-windows-pcs-in-microsoft-intune.md)** — wdrażanie oprogramowania na zarządzanych komputerach. Niektóre funkcje zarządzania aplikacjami są niedostępne, jeśli zarządzasz komputerami za pomocą klienta oprogramowania.

<!-- - **Compliance settings reporting** -->

## <a name="policies-and-app-deployments-for-the-intune-software-client"></a>Zasady i wdrożenia aplikacji dla oprogramowania klienckiego usługi Intune

Oprogramowanie klienckie usługi Intune obsługuje [możliwości z zakresu zarządzania sprzyjające ochronie komputerów](policies-to-protect-windows-pcs-in-microsoft-intune.md), umożliwiając zarządzanie aktualizacjami oprogramowania, zaporą systemu Windows i programem Endpoint Protection. Komputery zarządzane przy użyciu oprogramowania klienckiego usługi Intune nie mogą być jednak celem innych zasad usługi Intune, w tym ustawień zasad systemu **Windows** specyficznych dla zarządzania urządzeniami przenośnymi.

Korzystając z oprogramowania klienckiego usługi Intune do zarządzania komputerami z systemem Windows, można użyć tylko zasad wyświetlanych w obszarze **Zarządzanie komputerem**.

Usługa Intune zarządza komputerami z systemem Windows za pomocą zasad. Jest to podobne do działania obiektów zasad grupy w usługach Active Directory Domain Services (AD DS) systemu Windows Server. Jeśli zarządzasz komputerami przyłączonymi do domeny usługi Active Directory przy użyciu usługi Intune, [upewnij się, że zasady usługi Intune nie powodują konfliktów z innymi obiektami zasad grupy](resolve-gpo-and-microsoft-intune-policy-conflicts.md) stosowanymi w organizacji. Aby dowiedzieć się więcej, zobacz temat [Group Policy for beginners](https://technet.microsoft.com/library/hh147307.aspx) (Zasady grupy dla początkujących).

  ![Wybierz szablon dla nowej zasady dotyczącej komputera z systemem Windows](media/select-template-for-pc-policy.png)

Podczas wdrażania aplikacji można używać tylko Instalatora Windows (.exe i .msi).

  ![Wybierz platformę i lokalizację plików oprogramowania klienta](media/select-platform-of-software-files-for-pc-agent.png)

## <a name="common-tasks-for-windows-pcs"></a>Typowe zadania dla komputerów z systemem Windows

Konsoli administracyjnej usługi Intune można używać do wykonywania innych typowych zadań z zakresu zarządzania komputerami na komputerach z systemem Windows i z zainstalowanym oprogramowaniem klienckim:
- [Upraszczanie zarządzania komputerami przy użyciu zasad](use-policies-to-simplify-windows-pc-management.md) — opis zasad **zarządzania komputerem** usługi Intune oraz lista ustawień programu Microsoft Intune Center.

- [Wyświetlanie spisu sprzętu i oprogramowania dla komputerów z systemem Windows](view-hardware-and-software-inventory-for-windows-pcs-in-microsoft-intune.md) — objaśnienie sposobu tworzenia raportu zawierającego listę informacji na temat możliwości sprzętowych komputerów oraz zainstalowanego na nich oprogramowania. Ponadto opis sposobu odświeżenia elementów komputera w celu zapewnienia jego aktualności.
- [Wycofanie komputera z systemem Windows](retire-a-windows-pc-with-microsoft-intune.md) — lista czynności prowadzących do wycofania komputera z systemem Windows i opis sytuacji po wycofaniu komputera.
- [Zarządzanie połączeniem użytkownik-urządzenie dla komputerów z systemem Windows](manage-user-device-linking-for-windows-pcs-with-microsoft-intune.md) — objaśnienie, kiedy i jak należy połączyć użytkownika z komputerem osobistym przed wdrożeniem oprogramowania dla użytkownika.
- [Żądanie i zapewnianie pomocy zdalnej dla komputerów z systemem Windows](request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune.md) — objaśnienie sposobu udzielania pomocy zdalnej użytkownikom komputerów Intune oraz opis warunków wstępnych i konfiguracji programu TeamViewer.

Aby uzyskać więcej informacji o powyższych, zobacz [typowe zadania zarządzania komputerem](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).

## <a name="management-limitations-of-the-intune-client-software"></a>Ograniczenia oprogramowania klienckiego usługi Intune dotyczące zarządzania

Niektóre opcje zarządzania, których można użyć do zarządzania komputerami jako urządzeniami przenośnymi, nie mogą zostać użyte w przypadku komputerów zarządzanych przy użyciu oprogramowania klienckiego usługi Intune:

-   Pełne czyszczenie (selektywne czyszczenie jest dostępne)
-   Dostęp warunkowy

Należy również pamiętać, że w konsoli administracyjnej usługi Intune niektóre sekcje, takie jak **Aktualizacje**, **Ochrona** i **Licencje**, pojawiają się tylko w przypadku urządzeń zarejestrowanych za pomocą oprogramowania klienckiego usługi Intune.

  ![Elementy konsoli administratora, które są widoczne tylko dla komputera klienta](media/admin-console-settings-only-for-pc-agent.png)

## <a name="help-with-troubleshooting"></a>Pomoc w zakresie rozwiązywania problemów

Agent oprogramowania klienckiego usługi Intune zwykle działa w tle bez konieczności interakcji z użytkownikami ani rozwiązywania problemów. W razie potrzeby rozwiązania problemów z zarządzaniem komputerami można sprawdzić dzienniki. Oprogramowanie klienckie usługi Intune wraz z odpowiednimi dziennikami znajduje się w katalogu %Program Files%\Microsoft\OnlineManagement.

Możesz również zapoznać się z [rejestracją urządzeń](device-enrollment.md), aby uzyskać więcej informacji na temat rejestrowania urządzeń w usłudze Microsoft Intune.
