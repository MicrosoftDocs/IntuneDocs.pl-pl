---
title: "Możliwości zarządzania komputerami z systemem Windows | Microsoft Intune"
description: "Dowiedz się więcej o możliwościach usługi Intune podczas zarządzania komputerami z systemem Windows przy użyciu oprogramowania klienckiego usługi Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6716a3d1fb53dc3de0189f637d5664d0a2023d05
ms.openlocfilehash: b2e5b04df846db1a0076da7db63a5906fbd25558


---

# Możliwości zarządzania komputerami z systemem Windows (za pomocą komputerowego klienta usługi Microsoft Intune)
W większości przypadków będziesz rejestrować urządzenia w usłudze Microsoft Intune, co zapewnia dostęp do szerszego zestawu możliwości niż w przypadku komputerowego klienta usługi Intune. Jednak możesz również zarządzać komputerami, korzystając z komputerowego klienta usługi Intune, który zapewnia następujące funkcje:

-   **Zarządzanie aktualizacjami oprogramowania** — aktualizowanie komputerów i zarządzanie harmonogramem stosowania aktualizacji.

-   **Zasady Zapory systemu Windows** — zapewnianie, że żaden komputer używany przez firmę nie ma nieaktywnej ani nieprawidłowo skonfigurowanej Zapory systemu Windows.

-   **Ochrona przed złośliwym oprogramowaniem** — usługa Intune obejmuje program Endpoint Protection, który pomaga chronić komputery przed złośliwym oprogramowaniem.

-   **Pomoc zdalna** — usługa Intune umożliwia użytkownikom kontaktowanie się z pracownikami działu pomocy technicznej IT, którzy mogą udzielać im pomocy przy użyciu funkcji pulpitu zdalnego dostępnej w usłudze Intune <!--- (requires TeamViewer software)--->.

-   **Zarządzanie licencjami na oprogramowanie** — śledzenie liczby dostępnych licencji na oprogramowanie oraz liczby dostępnych licencji będących w użyciu.
-   **Wdrażanie aplikacji** — wdrażanie oprogramowania na zarządzanych komputerach. Niektóre funkcje zarządzania aplikacjami są niedostępne, jeśli zarządzasz komputerami za pomocą oprogramowania klienckiego.


Usługa Intune obsługuje instalowanie oprogramowania klienckiego na maksymalnie 7000 urządzeń z systemem Windows.

## Wymagania dotyczące systemu operacyjnego
Usługa Intune może zarządzać komputerami z następującymi wersjami systemu Windows (x86 i x64):


-   **Windows Vista** — wersje Business, Enterprise i Ultimate.

-   **Windows 7** — wersje Pro, Enterprise i Ultimate (bez dodatku Service Pack lub z dodatkiem SP1).

-   **Windows 8** — wersje Pro i Enterprise.

-   **Windows 8.1** — wersje Pro i Enterprise.

- **Windows 10** — wersje Home, Pro, Education i Enterprise.


## Minimalne wymagania sprzętowe
Poniżej podano minimalne wymagania dotyczące sprzętu w przypadku instalowania komputerowego klienta usługi Intune:

|Wymaganie|Szczegóły|
|---------------|--------------------|
|Sieć|Klient wymaga komputera z połączeniem z Internetem.|
|Procesor i pamięć|Należy zapoznać się z wymaganiami dotyczącymi procesora i pamięci RAM dla systemu operacyjnego komputera.|
|Miejsce na dysku|200 MB dostępnego miejsca na dysku przed zainstalowaniem oprogramowania klienckiego.|

## Dodatkowe wymagania
Poniżej podano wymagania dotyczące oprogramowania w przypadku instalowania komputerowego klienta usługi Intune:

|Wymaganie|Szczegóły|
|---------------|--------------------|
|Uprawnienia administracyjne|Konto używane do instalacji oprogramowania klienckiego musi mieć uprawnienia administratora lokalnego na danym komputerze.|
|Instalator Windows w wersji 3.1|Na komputerze musi być zainstalowany Instalator Windows w wersji 3.1 lub nowszej.|
|Usunięcie niezgodnego oprogramowania klienckiego|Przed zainstalowaniem komputerowego oprogramowania klienckiego usługi Intune należy odinstalować następujące oprogramowanie klienckie z danego komputera:<br /><br />- Wszelkie wersje programu Configuration Manager<br />- Wszelkie wersje programu Microsoft Systems Management Server (SMS)|

### Zobacz także
[Możliwości zarządzania urządzeniami przenośnymi w usłudze Microsoft Intune](./mobile-device-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


