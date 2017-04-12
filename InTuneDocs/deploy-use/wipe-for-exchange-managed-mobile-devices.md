---
title: "Czyszczenie urządzeń przenośnych zarządzanych przez program Exchange | Microsoft Docs"
description: "Usługa Microsoft Intune umożliwia czyszczenie lub resetowanie urządzeń przenośnych zarządzanych przy użyciu programu Exchange ActiveSync (EAS) za pomocą programu Intune Exchange Connector."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e116b620-1e12-4b5c-9905-2f7acf2ae530
ms.reviewer: lancecra
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 5f8da4e28f3b680d7b5b42c1c54fac4c9c43fbe2
ms.lasthandoff: 12/10/2016


---


# <a name="wipe-for-exchange-managed-mobile-devices"></a>Wipe for Program Exchange-managed mobile devices

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Usługa Microsoft Intune umożliwia czyszczenie lub resetowanie urządzeń przenośnych zarządzanych przy użyciu programu Exchange ActiveSync (EAS) za pomocą programu Intune Exchange Connector. W poniższej tabeli opisano możliwości czyszczenia dostępne za pośrednictwem programu Exchange ActiveSync:

|Typ czyszczenia|Windows 8.1 i Windows RT 8.1|iOS|Android|
|----------------|----------------------------------|--------------|-------------------|-------|-----------|
|Pełne czyszczenie danych|Usuwa konto e-mail i buforowaną pocztę e-mail.|XResetowanie do ustawień fabrycznych.|Resetowanie do ustawień fabrycznych.|
|Czyszczenie selektywne/poczta e-mail|Usuwa konto e-mail.|Nieobsługiwane.|Nieobsługiwane.|
|Czyszczenie selektywne/zasady|Wymuszanie zasad zostaje wyłączone, lecz ustawienia nie są zmieniane|XWymuszanie zasad zostaje wyłączone, lecz ustawienia nie są zmieniane.|Wymuszanie zasad zostaje wyłączone, ale ustawienia nie są zmieniane.|

