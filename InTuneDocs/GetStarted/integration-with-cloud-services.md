---
title: "Integracja usługi Intune z usługami w chmurze firmy Microsoft | Microsoft Intune"
description: "Integracja usługi Intune z usługami i produktami w chmurze firmy Microsoft i innymi produktami firmy Microsoft"
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 49675811-08a3-408f-810b-89552ff404bd
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6d1c7c670341692d4ea0c823e4a9a96746b83067
ms.openlocfilehash: 83020d347a4bc036778d830f5189e68e7f8d85da


---

# Integracja usługi Intune z usługami w chmurze i produktami firmy Microsoft

Przed skonfigurowaniem usługi [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] przejrzyj ten temat i inne wymagania wymienione w artykule [Co należy wiedzieć przed rozpoczęciem korzystania z usługi Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md).
##Integracja z innymi usługami w chmurze firmy Microsoft


[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] jest taka sama jak w przypadku innych usług w chmurze firmy Microsoft. Gdy subskrybujesz wiele usług w chmurze za pomocą jednego konta, korzystają one z tej samej infrastruktury usługi Microsoft Azure AD i są dzierżawcami tej usługi. Usługa Azure AD zapewnia podstawowe funkcje zarządzania katalogami i tożsamościami dla usług firmy Microsoft w chmurze.

Więcej informacji o [administrowaniu usługą Azure AD](http://technet.microsoft.com/library/hh967611.aspx) zawiera biblioteka TechNet.

## Integracja z innymi produktami firmy Microsoft
Usługa [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] może działać jako autonomiczna usługa w chmurze lub może być zintegrowana z innymi produktami. Obecnie usługa [!INCLUDE[cmshort](../includes/cmshort_md.md)] obsługuje bezpośrednią integrację tylko z programem [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

Integracja usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] z programem [!INCLUDE[cmshort](../includes/cmshort_md.md)] ma charakter trwały i wymaga ustawienia urzędu zarządzania urządzeniami przenośnymi z poziomu konsoli programu [!INCLUDE[cmshort](../includes/cmshort_md.md)], a nie za pomocą narzędzia [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)]. Po ustawieniu urzędu zarządzania urządzeniami przenośnymi nie można zmienić ani wycofać tej konfiguracji.

Jeśli korzystasz z usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] i programu [!INCLUDE[cmshort](../includes/cmshort_md.md)], nie używaj narzędzia [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] do zarządzania usługą [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] — zamiast tego użyj konsoli usługi [!INCLUDE[cmshort](../includes/cmshort_md.md)]. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] nadal używa magazynu w chmurze Azure do przechowywania oprogramowania wdrażanego na urządzeniach zarządzanych za pomocą usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

Aby uzyskać więcej informacji, zobacz [Zarządzanie urządzeniami przenośnymi za pomocą programu Configuration Manager i usługi Microsoft Intune](http://msdn.microsoft.com/library/2c6bd0e5-d436-41c8-bf38-30152d76be10) w dokumentacji programu [!INCLUDE[cm5short](../includes/cm5short_md.md)] z dodatkiem SP1.

### Zobacz także
[Co należy wiedzieć przed rozpoczęciem korzystania z usługi Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Aug16_HO4-->


