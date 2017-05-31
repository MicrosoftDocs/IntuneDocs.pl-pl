---
title: "Zasady zapory dla komputerów z systemem Windows | Microsoft Docs"
description: "Usługa Intune może pomóc w zabezpieczaniu komputerów zarządzanych za pomocą klienta usługi Intune na wiele sposobów, łącznie z konfigurowaniem ustawień Zapory systemu Windows."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9549c072-ac3d-4d14-a931-a2eda8846217
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: d96fd3cf4d8963f1e79ef4ed27c1b826c8893b5f
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune"></a>Ochrona komputerów z systemem Windows przy użyciu zasad Zapory systemu Windows w usłudze Microsoft Intune
Usługa Microsoft Intune może pomóc w zabezpieczaniu komputerów zarządzanych za pomocą klienta usługi Intune na wiele sposobów. Jednym z nich jest udostępnienie zasad, które umożliwiają skonfigurowanie ustawień Zapory systemu Windows na komputerach.

Jeśli klient usługi Intune na komputery z systemem Windows nie został jeszcze zainstalowany na komputerach, zobacz [Instalowanie klienta komputera z systemem Windows przy użyciu usługi Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).

W poniższych sekcjach znajdują się informacje ułatwiające konfigurowanie, wdrażanie i monitorowanie zasad Zapory systemu Windows na komputerach z systemem Windows.

## <a name="use-intune-policies-to-manage-windows-firewall"></a>Zarządzanie Zaporą systemu Windows przy użyciu zasad usługi Intune
Zasady Zapory systemu Windows umożliwiają tworzenie i wdrażanie ustawień sterujących zachowaniem Zapory systemu Windows na zarządzanych komputerach. Te ustawienia nie umożliwiają zarządzania niestandardowymi wyjątkami Zapory systemu Windows i nie mają wpływu na zapory innych firm.

> [!NOTE]
> Jeśli określone ustawienie na komputerze jest zarządzane zarówno przez zasady grupy, jak i zasady usługi Microsoft Intune, ustawienie skonfigurowane w ramach zasad grupy ma pierwszeństwo przed ustawieniem skonfigurowanym w ramach zasad usługi Microsoft Intune. Aby uzyskać informacje dotyczące zapobiegania konfliktom występującym między zasadami usługi Intune i zasadami grupy, zobacz [Rozwiązywanie konfliktów obiektów zasad grupy i zasad usługi Microsoft Intune](resolve-gpo-and-microsoft-intune-policy-conflicts.md).
>
> Jeśli chcesz wdrożyć ustawienia Zapory systemu Windows na komputerach z systemem Windows Vista, musisz najpierw zainstalować na nich [poprawkę KB971800](http://support2.microsoft.com/kb/971800).

> [!IMPORTANT]
> Aby móc zarządzać Zaporą systemu Windows za pomocą usługi Intune, na zarządzanych komputerach muszą być włączone następujące dwie usługi:
>
> -   Zapora systemu Windows
> -   Agent zasad IPsec

## <a name="configure-a-windows-firewall-policy"></a>Konfiguracja zasad Zapory systemu Windows

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz kolejno pozycje **Zasady** &gt; **Dodaj zasady**.

2.  Skonfiguruj i wdroż zasady **ustawień Zapory systemu Windows** . Możesz użyć zalecanych ustawień lub dostosować je. Aby uzyskać więcej informacji dotyczących sposobu tworzenia i wdrażania zasad, zobacz [Typowe zadania związane z zarządzaniem komputerem z systemem Windows za pomocą klienta komputerowego usługi Microsoft Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).

    W poniższej sekcji przedstawiono ustawienia możliwe do skonfigurowania w ramach zasad oraz ich wartości domyślne, które zostaną użyte, jeśli zrezygnujesz z dostosowania zasad.

Po wdrożeniu zasad Zapory systemu Windows można wyświetlić ich stan w obszarze roboczym **Zasady** na stronie **Wszystkie zasady**.

## <a name="specify-policy-settings-for-windows-firewall"></a>Określanie ustawień zasad Zapory systemu Windows

### <a name="turn-on-windows-firewall"></a>Włącz Zaporę systemu Windows

Te ustawienia zasad umożliwiają użycie Zapory systemu Windows na zarządzanych komputerach, które są:
- Połączone z domeną (np. w miejscu pracy)
- Połączone z (zaufaną) siecią prywatną (np. siecią domową)
- Połączone z niezaufaną siecią publiczną (np. w kawiarni)

Wartością domyślną dla każdego z tych ustawień jest **Tak**. Jest to najbezpieczniejsze ustawienie.



### <a name="block-all-incoming-connections-including-those-in-the-list-of-allowed-programs"></a>Blokuj wszystkie połączenia przychodzące łącznie z programami znajdującymi się na liście dozwolonych programów

Te ustawienia zasad konfigurują użycie Zapory systemu Windows w celu blokowania przychodzącego ruchu sieciowego na zarządzanych komputerach, które są:
- Połączone z domeną (np. w miejscu pracy)
- Połączone z (zaufaną) siecią prywatną (np. siecią domową)
- Połączone z niezaufaną siecią publiczną (np. w kawiarni)

Wartością domyślną dla każdego z tych ustawień jest **Tak**. Jest to najbezpieczniejsze ustawienie.

> [!IMPORTANT]
> Jeśli środowisko obejmuje zarządzane komputery z systemem Windows Vista bez zainstalowanych dodatków Service Pack, należy zainstalować aktualizację skojarzoną z [artykułem 971800](http://go.microsoft.com/fwlink/?LinkId=188405) w bazie wiedzy Microsoft Knowledge Base albo wyłączyć ustawienia zasad **Blokuj wszystkie połączenia przychodzące** w ramach zasad wdrożonych na tych komputerach.

### <a name="notify-the-user-when-windows-firewall-blocks-a-new-program"></a>Powiadamiaj użytkownika, gdy Zapora systemu Windows zablokuje nowy program

Te ustawienia zasad ustalają, czy użytkownik komputera otrzyma powiadomienie, gdy Zapora systemu Windows zablokuje przychodzący ruch sieciowy na zarządzanych komputerach:
- Połączone z domeną (np. w miejscu pracy)
- Połączone z (zaufaną) siecią prywatną (np. siecią domową)
- Połączone z niezaufaną siecią publiczną (np. w kawiarni)

Wartością domyślną dla każdego z tych ustawień jest **Tak**.


### <a name="configure-predefined-exceptions"></a>Konfigurowanie wstępnie zdefiniowanych wyjątków

Możesz skonfigurować wyjątki, które zezwalają na przesyłanie konkretnych rodzajów ruchu sieciowego przez zaporę, niezależnie od wartości skonfigurowanych wcześniej. Żadne z tych ustawień nie są domyślnie skonfigurowane.

|Nazwa ustawienia|Szczegóły|
|------------------|--------------------|
|**BranchCache — Pobieranie zawartości**<br>(system Windows 7 lub nowszy)|Umożliwia klientom usługi BranchCache korzystanie z protokołu HTTP do pobierania od innych klientów usługi BranchCache zawartości w trybie rozproszonym oraz zawartości z hostowanej pamięci podręcznej w trybie hostowanej pamięci podręcznej. To ustawienie powoduje użycie protokołu HTTP.|
|**BranchCache — Klient hostowanej pamięci podręcznej**<br>(system Windows 7 lub nowszy)|Umożliwia klientom usługi BranchCache używanie hostowanej pamięci podręcznej. To ustawienie powoduje użycie protokołu HTTPS.|
|**BranchCache — Serwer hostowanej pamięci podręcznej**|Umożliwia klientom usługi BranchCache używanie hostowanej pamięci podręcznej w celu komunikowania się z innymi klientami. To ustawienie powoduje użycie protokołu HTTPS.|
|**BranchCache — Odnajdywanie węzłów równorzędnych**<br>(system Windows 7 lub nowszy)|Umożliwia klientom usługi BranchCache używanie protokołu WS Discovery (Web Services Dynamic Discovery) do sprawdzania dostępności zawartości w podsieci lokalnej.|
|**Buforowanie równorzędne BITS**|Umożliwia klientom użycie usługi inteligentnego transferu w tle (BITS) w celu znajdowania plików przechowywanych w pamięci podręcznej usługi inteligentnego transferu w tle i udostępniania ich klientom w tej samej podsieci. To ustawienie powoduje użycie interfejsu Web Services on Devices (interfejsu WSDAPI) i zdalnego wywołania procedury (RPC).|
|**Połączenie z projektorem sieciowym**|Umożliwia użytkownikom nawiązywanie połączeń z projektorami za pośrednictwem sieci przewodowej lub bezprzewodowej w celu wyświetlenia prezentacji. To ustawienie powoduje użycie interfejsu WSDAPI.|
|**Podstawowe operacje sieciowe**|Umożliwia klientom korzystanie z protokołów IPv4 i IPv6 w celu nawiązywania połączeń z zasobami sieciowymi.|
|**Koordynator transakcji rozproszonych**|Umożliwia zarządzanym komputerom koordynowanie transakcji, które aktualizują zasoby z chronionymi transakcjami, takie jak bazy danych, kolejki komunikatów i systemy plików.|
|**Udostępnianie plików i drukarek**|Umożliwia użytkownikom udostępnianie lokalnych plików i drukarek innym użytkownikom w sieci. To ustawienie powoduje użycie systemu NetBIOS, rozpoznawania nazw multiemisji połączenia lokalnego (LLMNR), protokołu bloku komunikatów serwera (SMB) i zdalnego wywołania procedury (RPC).|
|**Grupa domowa**<br>(system Windows 7 lub nowszy)|Umożliwia zarządzanym komputerom działanie w sieci Grupa domowa.|
|**Usługa iSCSI**|Umożliwia zarządzanym komputerom nawiązywanie połączeń z serwerami i urządzeniami usługi iSCSI.|
|**Usługa zarządzania kluczami**|Umożliwia wyliczenie komputerów na potrzeby sprawdzania zgodności licencji w środowiskach przedsiębiorstw.|
|**Urządzenia Media Center Extender**|Umożliwia urządzeniom Media Center Extender komunikowanie się z komputerami, na których działa program Windows Media Center. To ustawienie powoduje użycie protokołu SSDP (Simple Service Discovery Protocol) i qWave.|
|**Usługa Netlogon**|Umożliwia skonfigurowanie kanału zabezpieczeń między klientami domeny a kontrolerem domeny w celu uwierzytelniania użytkowników i usług. To ustawienie powoduje użycie usługi RPC.|
|**Odnajdywanie sieci**|Umożliwia skonfigurowanie, czy komputery mogą odnajdywać inne urządzenia i czy mogą być przez nie odnajdywane w sieci. Ta funkcja korzysta z hosta odnajdywania funkcji i usług publikacji, architektury UPnP, protokołu SSDP, protokołu NetBIOS i rozpoznawania nazw LLMNR.|
|**Dzienniki wydajności i alerty**|Umożliwia zdalne zarządzanie usługą dzienników wydajności i alertów. To ustawienie powoduje użycie usługi RPC.|
|**Administracja zdalna**|Umożliwia zdalne administrowanie komputerem.|
|**Pomoc zdalna**|Umożliwia użytkownikom zarządzanych komputerów wysyłanie żądań o pomoc zdalną do innych użytkowników w sieci. To ustawienie powoduje użycie protokołów sieciowych SSDP, PNRP (Peer Name Resolution Protocol), Teredo oraz UPnP.|
|**Pulpit zdalny**|Umożliwia dostęp do innych komputerów za pomocą pulpitu zdalnego.|
|**Zdalne zarządzanie dziennikiem zdarzeń**|Umożliwia zdalne wyświetlanie dzienników zdarzeń klienta i zarządzanie nimi. To ustawienie powoduje użycie potoków nazwanych i usługi RPC.|
|**Zdalne zarządzanie zaplanowanymi zadaniami**|Umożliwia zdalne zarządzanie usługą planowania zadań. To ustawienie powoduje użycie usługi RPC.|
|**Zdalne zarządzanie usługami**|Umożliwia zdalne zarządzanie usługami lokalnymi na klientach. To ustawienie powoduje użycie potoków nazwanych i usługi RPC.|
|**Zdalne zarządzanie woluminami**|Umożliwia zdalne sprzętowe i programowe zarządzanie woluminami dyskowymi. To ustawienie powoduje użycie usługi RPC.|
|**Routing i dostęp zdalny**|Umożliwia komputerom obsługiwanie połączeń przychodzących VPN i dostępu zdalnego.|
|**Protokół SSTP**|Umożliwia zarządzanym komputerom obsługiwanie połączeń przychodzących VPN przy użyciu protokołu SSTP (Secure Socket Tunneling Protocol). To ustawienie powoduje użycie protokołu HTTPS.|
|**Usługa SNMP Trap**|Umożliwia zarządzanym komputerom odbieranie ruchu w ramach usługi Simple Network Management Protocol (SNMP) Trap.|
|**Architektura UPnP**|Umożliwia skonfigurowanie usługi Architektura UPnP na komputerach w celu umożliwienia im odnajdywania i używania certyfikowanych urządzeń UPnP.|
|**Usługa rejestracji nazw komputerów w funkcji Współpraca w systemie Windows**|Umożliwia komputerom wyszukiwanie innych komputerów i komunikowanie się z nimi przy użyciu protokołów SSDP i PNRP.|
|**Windows Media Player**|Umożliwia użytkownikom odbieranie multimediów strumieniowych za pośrednictwem protokołu UDP (User Datagram Protocol).|
|**Usługa udostępniania w sieci programu Windows Media Player**|Umożliwia użytkownikom udostępnianie multimediów przez sieć. To ustawienie powoduje użycie usług SSDP, qWave oraz protokołów sieciowych UPnP.|
|**Usługa udostępniania w sieci programu Windows Media Player (Internet)**<br>(system Windows 7 lub nowszy)|Umożliwia użytkownikom udostępnianie multimediów domowych przez Internet.|
|**Obszar spotkań w systemie Windows**|Umożliwia użytkownikom współpracę przez sieć w celu udostępniania dokumentów, programów i pulpitów. To ustawienie korzysta z usługi replikacji rozproszonego systemu plików (DFS) i funkcji P2P.|
|**Funkcja Podstawa współpracy w sieci równorzędnej systemu Windows**|Umożliwia konfigurowanie różnych programów i technologii działających w sieciach równorzędnych. To ustawienie powoduje użycie usług SSDP i PNRP.|
|**Zdalne zarządzanie systemem Windows (tryb zgodności)**|Umożliwia zdalne zarządzanie komputerami za pomocą usługi WS-Management, czyli opartego na usługach sieci Web protokołu do zdalnego zarządzania systemami operacyjnymi i urządzeniami.|
|**Zdalne zarządzanie systemem Windows**<br>(system Windows 8 lub nowszy).|Umożliwia zdalne zarządzanie komputerami za pomocą usługi WS-Management, czyli opartego na usługach sieci Web protokołu do zdalnego zarządzania systemami operacyjnymi i urządzeniami.|
|**Windows Virtual PC**<br>(system Windows 7 lub nowszy)|Umożliwia maszynom wirtualnym komunikowanie się z innymi komputerami.|
|**Bezprzewodowe urządzenia przenośne**|Umożliwia transferowanie multimediów z kamery sieciowej lub urządzenia multimedialnego do zarządzanych komputerów przy użyciu protokołu transferu multimediów (MTP). To ustawienie powoduje użycie usługi SSDP i protokołów sieciowych UPnP.|

### <a name="see-also"></a>Zobacz także
[Zasady ochrony komputerów z systemem Windows](policies-to-protect-windows-pcs-in-microsoft-intune.md)

