---
title: "Zasady zapory dla komputerów z systemem Windows | Microsoft Intune"
description: "Usługa Intune może pomóc w zabezpieczaniu komputerów zarządzanych za pomocą klienta usługi Intune na wiele sposobów, łącznie z konfigurowaniem ustawień Zapory systemu Windows."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9549c072-ac3d-4d14-a931-a2eda8846217
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6716a3d1fb53dc3de0189f637d5664d0a2023d05
ms.openlocfilehash: 20970051e0be6cd1b700691ec87ecdd4c536a0c6


---

# Ochrona komputerów z systemem Windows przy użyciu zasad Zapory systemu Windows w usłudze Microsoft Intune
Usługa Microsoft Intune może pomóc w zabezpieczaniu komputerów z systemem Windows zarządzanych za pomocą klienta usługi Intune na wiele sposobów, łącznie z użyciem zasad, które pozwalają skonfigurować ustawienia Zapory systemu Windows na komputerach.

Jeśli klient usługi Intune na komputery z systemem Windows nie został jeszcze zainstalowany na komputerach, zobacz [Instalowanie klienta komputera z systemem Windows przy użyciu usługi Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).

W poniższych sekcjach znajdują się informacje ułatwiające konfigurowanie, wdrażanie i monitorowanie zasad Zapory systemu Windows na komputerach z systemem Windows.

## Zarządzanie Zaporą systemu Windows przy użyciu zasad usługi Intune
Zasady Zapory systemu Windows umożliwiają tworzenie i wdrażanie ustawień sterujących zachowaniem Zapory systemu Windows na zarządzanych komputerach. Te ustawienia nie umożliwiają zarządzania niestandardowymi wyjątkami Zapory systemu Windows i nie mają wpływu na zapory innych firm.

> [!NOTE]
> Jeśli określone ustawienie na komputerze jest zarządzane zarówno przez zasady grupy, jak i zasady usługi Microsoft Intune, ustawienie skonfigurowane w ramach zasad grupy ma pierwszeństwo przed ustawieniem skonfigurowanym w ramach zasad usługi Microsoft Intune. Aby uzyskać informacje dotyczące zapobiegania konfliktom występującym między zasadami usługi Intune i zasadami grupy, zobacz [Rozwiązywanie konfliktów obiektów zasad grupy i zasad usługi Microsoft Intune](resolve-gpo-and-microsoft-intune-policy-conflicts.md).
>
> Jeśli chcesz wdrożyć ustawienia Zapory systemu Windows na komputerach z systemem Windows Vista, musisz najpierw zainstalować na nich [poprawkę KB971800](http://support2.microsoft.com/kb/971800) .

> [!IMPORTANT]
> Aby móc zarządzać Zaporą systemu Windows za pomocą usługi Intune, na zarządzanych komputerach muszą być włączone następujące dwie usługi:
>
> -   Zapora systemu Windows
> -   Agent zasad IPsec

## Konfiguracja zasad Zapory systemu Windows

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz kolejno pozycje **Zasady** &gt; **Dodaj zasady**.

2.  Skonfiguruj i wdroż zasady **ustawień Zapory systemu Windows** . Możesz skorzystać z zalecanych ustawień lub dostosować je. Aby uzyskać więcej informacji dotyczących sposobu tworzenia i wdrażania zasad, zobacz [Typowe zadania związane z zarządzaniem komputerem z systemem Windows za pomocą klienta komputerowego usługi Microsoft Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).

    W poniższej sekcji przedstawiono ustawienia możliwe do skonfigurowania w ramach zasad oraz ich wartości domyślne, które zostaną użyte, jeśli zrezygnujesz z dostosowania zasad.

Po wdrożeniu zasad Zapory systemu Windows można wyświetlić ich stan w obszarze roboczym **Zasady** na stronie **Wszystkie zasady**.

## Ustawienia zasad Zapory systemu Windows

### Włącz Zaporę systemu Windows

Te ustawienia zasad umożliwiają użycie Zapory systemu Windows na zarządzanych komputerach podłączonych do domeny (np. w miejscu pracy) lub pracujących w (zaufanej) sieci prywatnej (np. sieci domowej) albo w niezaufanej sieci publicznej (np. w kawiarni). Wartością domyślną dla każdego z tych ustawień jest **Tak**. Jest to najbezpieczniejsze ustawienie. 



### Blokuj wszystkie połączenia przychodzące łącznie z programami znajdującymi się na liście dozwolonych programów

Te ustawienia zasad konfigurują użycie Zapory systemu Windows w celu blokowania przychodzącego ruchu sieciowego na zarządzanych komputerach podłączonych do domeny (np. w miejscu pracy) lub pracujących w (zaufanej) sieci prywatnej (np. sieci domowej) albo w niezaufanej sieci publicznej (np. w kawiarni). Wartością domyślną dla każdego z tych ustawień jest **Tak**. Jest to najbezpieczniejsze ustawienie. 

> [!IMPORTANT]
> Jeśli środowisko obejmuje zarządzane komputery z systemem Windows Vista bez zainstalowanych dodatków Service Pack, należy zainstalować aktualizację skojarzoną z [artykułem 971800](http://go.microsoft.com/fwlink/?LinkId=188405) w bazie wiedzy Microsoft Knowledge Base albo wyłączyć ustawienia **Blokuj wszystkie połączenia przychodzące** w ramach zasad wdrożonych na tych komputerach.

### Powiadamiaj użytkownika, gdy Zapora systemu Windows zablokuje nowy program

Te ustawienia zasad ustalają, czy użytkownik komputera otrzyma powiadomienie, gdy Zapora systemu Windows zablokuje przychodzący ruch sieciowy na zarządzanych komputerach podłączonych do domeny (np. w miejscu pracy) lub pracujących w (zaufanej) sieci prywatnej (np. sieci domowej) albo w niezaufanej sieci publicznej (np. w kawiarni). Wartością domyślną dla każdego z tych ustawień jest **Tak**.


### Wstępnie zdefiniowane wyjątki

Po skonfigurowaniu powyższych wartości podstawowych możesz skonfigurować wyjątki, które zezwalają na przesyłanie konkretnego ruchu sieciowego przez zaporę, niezależnie od wartości skonfigurowanych powyżej. Domyślnie nie są skonfigurowane żadne z tych ustawień.

|Nazwa ustawienia|Szczegóły|
|------------------|--------------------|
|**BranchCache — Pobieranie zawartości**<br>(system Windows 7 lub nowszy)|Umożliwia klientom usługi BranchCache korzystanie z protokołu HTTP do pobierania od siebie nawzajem zawartości w trybie rozproszonym oraz zawartości z hostowanej pamięci podręcznej w trybie hostowanej pamięci podręcznej. To ustawienie powoduje użycie protokołu HTTP.|
|**BranchCache — Klient hostowanej pamięci podręcznej**<br>(system Windows 7 lub nowszy)|Umożliwia klientom usługi BranchCache używanie hostowanej pamięci podręcznej. To ustawienie powoduje użycie protokołu HTTPS.|
|**BranchCache — Serwer hostowanej pamięci podręcznej**|Umożliwia klientom usługi BranchCache używanie hostowanej pamięci podręcznej w celu komunikowania się z innymi klientami. To ustawienie powoduje użycie protokołu HTTPS.|
|**BranchCache — Odnajdywanie węzłów równorzędnych**<br>(system Windows 7 lub nowszy)|Umożliwia klientom usługi BranchCache używanie protokołu WS Discovery do sprawdzania dostępności zawartości w podsieci lokalnej.|
|**Buforowanie równorzędne BITS**|Umożliwia klientom użycie usługi inteligentnego transferu w tle (BITS) w celu znajdowania plików przechowywanych w pamięci podręcznej usługi inteligentnego transferu w tle i udostępniania ich klientom w tej samej podsieci. To ustawienie powoduje użycie interfejsu WSDAPI i usługi RPC.|
|**Połączenie z projektorem sieciowym**|Umożliwia użytkownikom nawiązywanie połączeń z projektorami za pośrednictwem sieci przewodowej lub bezprzewodowej w celu wyświetlenia prezentacji. To ustawienie powoduje użycie interfejsu WSDAPI.|
|**Podstawowe operacje sieciowe**|Umożliwia klientom korzystanie z protokołów IPv4 i IPv6 w celu nawiązywania połączeń z zasobami sieciowymi.|
|**Koordynator transakcji rozproszonych**|Umożliwia zarządzanym komputerom koordynowanie transakcji, które aktualizują zasoby z chronionymi transakcjami, takie jak bazy danych, kolejki komunikatów i systemy plików.|
|**Udostępnianie plików i drukarek**|Umożliwia użytkownikom udostępnianie lokalnych plików i drukarek innym użytkownikom w sieci. To ustawienie korzysta z systemu NetBIOS, rozpoznawania LLMNR, bloków SMB i usługi RPC.|
|**Grupa domowa**<br>(system Windows 7 lub nowszy)|Umożliwia zarządzanym komputerom działanie w sieci Grupy domowej.|
|**Usługa iSCSI**|Umożliwia zarządzanym komputerom nawiązywanie połączeń z serwerami i urządzeniami usługi iSCSI.|
|**Usługa zarządzania kluczami**|Umożliwia wyliczenie komputerów na potrzeby sprawdzania zgodności licencji w środowiskach przedsiębiorstw.|
|**Urządzenia Media Center Extender**|Umożliwia urządzeniom Media Center Extender komunikowanie się z komputerami, na których działa program Windows Media Center. To ustawienie powoduje użycie usług SSDP i qWave.|
|**Usługa Netlogon**|Umożliwia skonfigurowanie kanału zabezpieczeń między klientami domeny a kontrolerem domeny w celu uwierzytelniania użytkowników i usług. To ustawienie powoduje użycie usługi RPC.|
|**Odnajdywanie sieci**|Umożliwia skonfigurowanie, czy komputery mogą odnajdywać inne urządzenia i czy mogą być przez nie odnajdywane w sieci. Ta funkcja korzysta z hosta odnajdywania funkcji i usług publikacji, architektury UPnP, protokołu SSDP, protokołu NetBIOS i rozpoznawania nazw LLMNR.|
|**Dzienniki wydajności i alerty**|Umożliwia zdalne zarządzanie usługą dzienników wydajności i alertów. To ustawienie powoduje użycie usługi RPC.|
|**Administracja zdalna**|Umożliwia zdalne administrowanie komputerem.|
|**Pomoc zdalna**|Umożliwia użytkownikom zarządzanych komputerów wysyłanie żądań o pomoc zdalną do innych użytkowników w sieci. To ustawienie powoduje użycie usług SSDP, PNRP, Teredo oraz protokołów sieciowych UPnP.|
|**Pulpit zdalny**|Umożliwia dostęp do innych komputerów za pomocą pulpitu zdalnego.|
|**Zdalne zarządzanie dziennikiem zdarzeń**|Umożliwia zdalne wyświetlanie dzienników zdarzeń klienta i zarządzanie nimi. To ustawienie powoduje użycie potoków nazwanych i usługi RPC.|
|**Zdalne zarządzanie zaplanowanymi zadaniami**|Umożliwia zdalne zarządzanie usługą planowania zadań. To ustawienie powoduje użycie usługi RPC.|
|**Zdalne zarządzanie usługami**|Umożliwia zdalne zarządzanie usługami lokalnymi na klientach. To ustawienie powoduje użycie potoków nazwanych i usługi RPC.|
|**Zdalne zarządzanie woluminami**|Umożliwia zdalne sprzętowe i programowe zarządzanie woluminami dyskowymi. To ustawienie powoduje użycie usługi RPC.|
|**Routing i dostęp zdalny**|Umożliwia komputerom obsługiwanie połączeń przychodzących VPN i dostępu zdalnego.|
|**Protokół SSTP**|Umożliwia zarządzanym komputerom obsługiwanie połączeń przychodzących VPN, które używają protokołu SSTP (Secure Socket Tunneling Protocol). To ustawienie powoduje użycie protokołu HTTPS.|
|**Usługa SNMP Trap**|Umożliwia zarządzanym komputerom odbieranie ruchu w ramach usługi SNMP Trap.|
|**Architektura UPnP**|Umożliwia skonfigurowanie usługi Architektura UPnP na komputerach w celu umożliwienia im odnajdywania i używania certyfikowanych urządzeń UPnP.|
|**Usługa rejestracji nazw komputerów w funkcji Współpraca w systemie Windows**|Umożliwia komputerom wyszukiwanie innych komputerów za pomocą protokołu rozpoznawania nazw równorzędnych (PNRP, Peer Name Resolution Protocol) i komunikowanie się z nimi. To ustawienie powoduje użycie usług SSDP i PNRP.|
|**Windows Media Player**|Umożliwia użytkownikom odbieranie multimediów strumieniowych za pośrednictwem protokołu UDP.|
|**Usługa udostępniania w sieci programu Windows Media Player**|Umożliwia użytkownikom udostępnianie multimediów przez sieć. To ustawienie powoduje użycie usług SSDP, qWave oraz protokołów sieciowych UPnP.|
|**Usługa udostępniania w sieci programu Windows Media Player (Internet)**<br>(system Windows 7 lub nowszy)|Umożliwia użytkownikom udostępnianie multimediów domowych przez Internet.|
|**Obszar spotkań w systemie Windows**|Umożliwia użytkownikom współpracę przez sieć w celu udostępniania dokumentów, programów lub pulpitu. To ustawienie powoduje użycie narzędzi DFSR i P2P.|
|**Funkcja Podstawa współpracy w sieci równorzędnej systemu Windows**|Umożliwia konfigurowanie różnych programów i technologii działających w sieciach równorzędnych. To ustawienie powoduje użycie usług SSDP i PNRP.|
|**Zdalne zarządzanie systemem Windows (tryb zgodności)**|Umożliwia zdalne zarządzanie komputerami za pomocą usługi WS-Management, czyli opartego na usługach sieci Web protokołu do zdalnego zarządzania systemami operacyjnymi i urządzeniami.|
|**Zdalne zarządzanie systemem Windows**<br>(system Windows 8 lub nowszy).|Umożliwia zdalne zarządzanie komputerami za pomocą usługi WS-Management, czyli opartego na usługach sieci Web protokołu do zdalnego zarządzania systemami operacyjnymi i urządzeniami.|
|**Windows Virtual PC**<br>(system Windows 7 lub nowszy)|Umożliwia maszynom wirtualnym komunikowanie się z innymi komputerami.|
|**Bezprzewodowe urządzenia przenośne**|Umożliwia transferowanie multimediów z kamery sieciowej lub urządzenia multimedialnego do zarządzanych komputerów za pośrednictwem protokołu transferu multimediów (MTP). To ustawienie powoduje użycie usługi SSDP i protokołów sieciowych UPnP.|

### Zobacz także
[Zasady ochrony komputerów z systemem Windows](policies-to-protect-windows-pcs-in-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


