---
title: "Możliwości komputerowego klienta oprogramowania usługi Intune | Microsoft Docs"
description: "Dowiedz się więcej o możliwościach usługi Intune podczas zarządzania komputerami z systemem Windows przy użyciu klienta oprogramowania usługi Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f268cf29461447306d0f5c3ca06d541d9a03a49d
ms.openlocfilehash: 36a20feed1756ea8dde2230db81099b6c5f8c7f6


---

# <a name="windows-pc-management-capabilities-when-you-use-the-intune-software-client"></a>Możliwości w zakresie zarządzania komputerem z systemem Windows w przypadku użycia klienta oprogramowania usługi Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

W większości przypadków będziesz rejestrować urządzenia w usłudze Microsoft Intune, co zapewnia większe możliwości. Możesz jednak także zarządzać komputerami, korzystając z klienta oprogramowania usługi Intune, który zapewnia następujące funkcje:

-   **[Zarządzanie aktualizacjami oprogramowania](/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)** — aktualizowanie komputerów i zarządzanie harmonogramem stosowania aktualizacji.

-   **[Zasady Zapory systemu Windows](/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)** — zapewnianie, że żaden komputer używany w firmie nie ma nieaktywnej ani nieprawidłowo skonfigurowanej Zapory systemu Windows.

-   **[Ochrona przed złośliwym oprogramowaniem](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)** — usługa Intune obejmuje program Endpoint Protection, który pomaga chronić komputery przed złośliwym oprogramowaniem.

-   **[Pomoc zdalna](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#request-and-provide-remote-assistance-to-windows-pcs-that-use-the-intune-client-software )** — usługa Intune umożliwia użytkownikom kontaktowanie się z pracownikami działu pomocy technicznej IT, którzy mogą udzielić im pomocy przy użyciu funkcji pulpitu zdalnego dostępnej w usłudze Intune (wymagane jest oprogramowanie TeamViewer).

-   **[Zarządzanie licencjami na oprogramowanie](/intune/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)** — śledzenie liczby dostępnych licencji na oprogramowanie oraz liczby dostępnych licencji będących w użyciu.
-   **[Wdrażanie aplikacji](/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)** — wdrażanie oprogramowania na zarządzanych komputerach. Niektóre funkcje zarządzania aplikacjami są niedostępne, jeśli zarządzasz komputerami za pomocą klienta oprogramowania.


Usługa Intune obsługuje instalację klienta oprogramowania na maksymalnie 7000 urządzeń z systemem Windows.

## <a name="operating-system-requirements"></a>Wymagania dotyczące systemu operacyjnego
Usługa Intune może zarządzać komputerami z następującymi wersjami systemu Windows (32- i 64-bitowymi):


-   **Windows Vista** — wersje Business, Enterprise i Ultimate

-   **Windows 7** — wersje Pro, Enterprise i Ultimate (bez dodatku Service Pack lub z dodatkiem SP1)

-   **Windows 8** — wersje Pro i Enterprise

-   **Windows 8.1** — wersje Pro i Enterprise

- **Windows 10** — wersje Pro, Education i Enterprise


## <a name="minimum-hardware-requirements"></a>Minimalne wymagania sprzętowe
Poniżej podano minimalne wymagania sprzętowe w przypadku instalowania klienta oprogramowania usługi Intune:

|Wymaganie|Szczegóły|
|---------------|--------------------|
|Sieć|Klient wymaga komputera z połączeniem z Internetem.|
|Procesor i pamięć|Należy zapoznać się z wymaganiami dotyczącymi procesora i pamięci RAM dla systemu operacyjnego komputera.|
|Miejsce na dysku|200 MB dostępnego miejsca na dysku przed zainstalowaniem oprogramowania klienckiego.|

## <a name="further-requirements"></a>Dodatkowe wymagania
Poniżej podano wymagania programowe w przypadku instalowania klienta oprogramowania usługi Intune:

|Wymaganie|Szczegóły|
|---------------|--------------------|
|Uprawnienia administracyjne|Konto używane do instalacji oprogramowania klienckiego musi mieć uprawnienia administratora lokalnego na danym komputerze.|
|Instalator Windows w wersji 3.1|Na komputerze musi być dostępny Instalator Windows w wersji 3.1 lub nowszej.|
|Usunięcie niezgodnego oprogramowania klienckiego|Przed zainstalowaniem komputerowego oprogramowania klienckiego usługi Intune należy odinstalować następujące oprogramowanie klienckie z danego komputera:<br /><br />- Wszelkie wersje programu Configuration Manager<br />- Wszelkie wersje programu Microsoft Systems Management Server (SMS)|

### <a name="see-also"></a>Zobacz także
[Możliwości zarządzania zarejestrowanymi urządzeniami w usłudze Microsoft Intune](./mobile-device-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Dec16_HO3-->


