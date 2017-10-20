---
title: "Wdrażanie aplikacji"
description: "W tym temacie omówiono pojęcia, które należy zrozumieć przed rozpoczęciem wdrażania aplikacji w usłudze Intune."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ad5ea85c-aa2e-4110-a184-172cd0b8f270
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6e3761ad892ff17abdfb8b61516ef56b1fb8318d
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2017
---
# <a name="deploy-apps-with-microsoft-intune"></a>Wdrażanie aplikacji w usłudze Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

W tym temacie omówiono pojęcia, które należy zrozumieć przed rozpoczęciem wdrażania aplikacji w usłudze Microsoft Intune.


## <a name="app-deployment-actions"></a>Akcje wdrażania aplikacji
Podczas wdrażania aplikacji można wybrać jedną z następujących akcji wdrażania:

-   **Wymagana instalacja** — aplikacja jest instalowana na urządzeniu bez potrzeby interwencji użytkownika.

    > [!TIP]
    > W przypadku urządzeń z systemem iOS niebędących w trybie nadzorowanym oraz wszystkich urządzeń z systemem Android użytkownik musi zaakceptować ofertę aplikacji, zanim zostanie ona zainstalowana.
    >
    >  Jeśli użytkownik odinstaluje aplikację, która została wdrożona jako instalacja wymagana, usługa Intune automatycznie ponownie zainstaluje aplikację po następnym cyklu spisu, który ma miejsce zazwyczaj co siedem dni.

-   **Dostępna instalacja** — aplikacja jest wyświetlana w portalu firmy i użytkownicy mogą zainstalować ją na żądanie.

-   **Odinstaluj** — aplikacja zostanie odinstalowana z urządzenia.

-   **Nie dotyczy** — aplikacja nie jest wyświetlana w portalu firmy i nie jest instalowana na żadnych urządzeniach.

#### <a name="understand-which-deployment-actions-are-available-for-each-installer-type"></a>Opis akcji wdrażania dostępnych dla poszczególnych typów instalatora

|Typ instalatora|Wymagana instalacja|Dostępna instalacja|Odinstaluj|Nie dotyczy|
|------------------|--------------------|---------------------|-------------|------------------|
|Pakiet aplikacji systemu Windows (wdrożenie w grupie użytkowników)|Tak|Tak|Tak|Tak|
|Pakiet aplikacji systemu Windows (wdrożenie w grupie urządzeń)|Tak|Nie|Tak|Tak|
|Pakiet aplikacji dla urządzeń przenośnych (wdrożenie w grupie użytkowników)|Tak|Tak|Tak|Tak|
|Pakiet aplikacji dla urządzeń przenośnych (wdrożenie w grupie urządzeń)|Tak|Nie|Tak|Tak|
|Instalator systemu Windows (wdrożenie w grupie użytkowników)|Nie|Tak|Nie|Tak|
|Instalator systemu Windows (wdrożenie w grupie urządzeń)|Tak|Nie|Tak|Tak|
|Link zewnętrzny (wdrożenie w grupie użytkowników)|Nie|Tak|Nie|Tak|
|Link zewnętrzny (wdrożenie w grupie urządzeń)|Nie|Nie|Nie|Nie|
|Zarządzana aplikacja systemu iOS ze sklepu App Store (wdrożenie w grupie użytkowników)|Tak|Tak|Tak|Tak|
|Zarządzana aplikacja systemu iOS ze sklepu App Store (wdrożenie w grupie urządzeń)|Tak|Nie|Tak|Tak|
> [!TIP]
> Jeśli podczas wdrażania aplikacji wybierzesz zarówno grupę użytkowników, jak i grupę urządzeń, możesz wdrożyć aplikację jedynie przy użyciu ustawienia **Dostępna instalacja**.

## <a name="deployment-conflicts"></a>Konflikty wdrażania
W przypadku gdy urządzenie otrzymuje dwa wdrożenia z tą samą akcją wdrażania, stosowane są następujące reguły:

-   Wdrożenia w grupie urządzeń mają pierwszeństwo przed wdrożeniami w grupie użytkowników. Jednak jeśli ta sama aplikacja jest wdrożona dla grupy użytkowników przy użyciu akcji wdrażania **Dostępne** i wdrożona dla grupy urządzeń przy użyciu akcji wdrażania **Nie dotyczy**, aplikacja zostanie udostępniona w portalu firmy, aby użytkownicy mogli ją zainstalować.

-   Akcja instalacji ma pierwszeństwo przed akcją dezinstalacji.

-   Jeśli urządzenie otrzymuje zarówno wymaganą, jak i dostępną instalację, akcje zostają połączone. Innymi słowy użytkownik może zainstalować dostępną aplikację z portalu firmy przed rozpoczęciem instalacji wymaganej.


## <a name="next-steps"></a>Następne kroki

Dowiedz się, jak [wdrażać aplikacje w usłudze Microsoft Intune](deploy-apps-in-microsoft-intune.md).
