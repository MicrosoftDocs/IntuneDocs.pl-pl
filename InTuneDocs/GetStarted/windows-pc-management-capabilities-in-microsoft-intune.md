---
title: "Możliwości komputerowego klienta oprogramowania usługi Intune | Microsoft Intune"
description: "Dowiedz się więcej o możliwościach usługi Intune podczas zarządzania komputerami z systemem Windows przy użyciu klienta oprogramowania usługi Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 12d75bc67fd61a2e807eed2543f21b756a65a900
ms.openlocfilehash: 3066ef98c0a1df6fc0ae455860635e7c12f82c4f


---

# Możliwości z zakresu zarządzania z użyciem komputera z systemem Windows w przypadku użycia klienta oprogramowania usługi Intune
W większości przypadków będziesz rejestrować urządzenia w usłudze Microsoft Intune, co zapewnia większe możliwości. Możesz jednak także zarządzać komputerami, korzystając z klienta oprogramowania usługi Intune, który zapewnia następujące funkcje:

-   **Zarządzanie aktualizacjami oprogramowania** — aktualizowanie komputerów i zarządzanie harmonogramem stosowania aktualizacji.

-   **Zasady Zapory systemu Windows** — zapewnianie, że żaden komputer używany w firmie nie ma nieaktywnej ani nieprawidłowo skonfigurowanej Zapory systemu Windows.

-   **Ochrona przed złośliwym oprogramowaniem** — usługa Intune obejmuje program Endpoint Protection, który pomaga chronić komputery przed złośliwym oprogramowaniem.

-   **Pomoc zdalna** — usługa Intune umożliwia użytkownikom kontaktowanie się z pracownikami działu pomocy technicznej IT, którzy mogą udzielić im pomocy przy użyciu funkcji pulpitu zdalnego dostępnej w usłudze Intune (wymagane jest oprogramowanie TeamViewer).

-   **Zarządzanie licencjami na oprogramowanie** — śledź liczbę dostępnych licencji na oprogramowanie oraz liczbę dostępnych licencji będących w użyciu.
-   **Wdrażanie aplikacji** — wdrażanie oprogramowania na zarządzanych komputerach. Niektóre funkcje zarządzania aplikacjami są niedostępne, jeśli zarządzasz komputerami za pomocą klienta oprogramowania.


Usługa Intune obsługuje instalację klienta oprogramowania na maksymalnie 7000 urządzeń z systemem Windows.

## Wymagania dotyczące systemu operacyjnego
Usługa Intune może zarządzać komputerami z następującymi wersjami systemu Windows (32- i 64-bitowymi):


-   **Windows Vista** — wersje Business, Enterprise i Ultimate

-   **Windows 7** — wersje Pro, Enterprise i Ultimate (bez dodatku Service Pack lub z dodatkiem SP1)

-   **Windows 8** — wersje Pro i Enterprise

-   **Windows 8.1** — wersje Pro i Enterprise

- **Windows 10** — wersje Pro, Education i Enterprise


## Minimalne wymagania sprzętowe
Poniżej podano minimalne wymagania sprzętowe w przypadku instalowania klienta oprogramowania usługi Intune:

|Wymaganie|Szczegóły|
|---------------|--------------------|
|Sieć|Klient wymaga komputera z połączeniem z Internetem.|
|Procesor i pamięć|Należy zapoznać się z wymaganiami dotyczącymi procesora i pamięci RAM dla systemu operacyjnego komputera.|
|Miejsce na dysku|200 MB dostępnego miejsca na dysku przed zainstalowaniem oprogramowania klienckiego.|

## Dodatkowe wymagania
Poniżej podano wymagania programowe w przypadku instalowania klienta oprogramowania usługi Intune:

|Wymaganie|Szczegóły|
|---------------|--------------------|
|Uprawnienia administracyjne|Konto używane do instalacji oprogramowania klienckiego musi mieć uprawnienia administratora lokalnego na danym komputerze.|
|Instalator Windows w wersji 3.1|Na komputerze musi być dostępny Instalator Windows w wersji 3.1 lub nowszej.|
|Usunięcie niezgodnego oprogramowania klienckiego|Przed zainstalowaniem komputerowego oprogramowania klienckiego usługi Intune należy odinstalować następujące oprogramowanie klienckie z danego komputera:<br /><br />- Wszelkie wersje programu Configuration Manager<br />- Wszelkie wersje programu Microsoft Systems Management Server (SMS)|

### Zobacz także
[Możliwości zarządzania zarejestrowanymi urządzeniami w usłudze Microsoft Intune](./mobile-device-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Aug16_HO4-->


