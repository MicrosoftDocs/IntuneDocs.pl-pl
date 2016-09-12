---
title: "Synchronizacja usługi Active Directory i dodawanie użytkowników do usługi Intune | Microsoft Intune"
description: "Opisuje synchronizowanie lokalnych użytkowników z usługą Azure AD i udzielanie uprawnień administratora dla subskrypcji usługi Intune"
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 08/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0c1e08cc49d75303f6793894e3c8a040f6e7a8b1
ms.openlocfilehash: a2ed4b1e025437cca6de4a15b3800daa2c9a212b


---


# Synchronizacja usługi Active Directory i dodawanie użytkowników do usługi Intune
Istnieje możliwość skonfigurowania synchronizacji katalogów w celu zaimportowania kont użytkowników z lokalnej usługi Active Directory do usługi Microsoft Azure Active Directory (Azure AD). Połączenie lokalnej usługi Active Directory z wszystkimi usługami opartymi na usłudze Azure Active Directory znacznie ułatwia zarządzanie tożsamościami użytkowników. Można także skonfigurować funkcje logowania jednokrotnego, aby znacznie ułatwić uwierzytelnianie użytkowników.

Ponadto w przypadku korzystania z wielu usług za pomocą tej samej [dzierżawy usługi Azure AD](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant) zsynchronizowane konta użytkowników są dostępne dla wszystkich usług w chmurze, które współużytkują tę samą subskrypcję dzierżawy usługi Azure AD.

## Synchronizowanie lokalnych użytkowników z usługą Azure AD
Jedynym narzędziem potrzebnym do synchronizowania kont użytkowników z usługą Azure AD jest [Kreator Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594). Kreator Azure AD Connect zapewnia uproszczoną obsługę i przewodnik łączenia lokalnej infrastruktury tożsamości z chmurą.  Określ topologię i potrzeby (jeden lub wiele katalogów, synchronizacja haseł lub federacja), a kreator wdroży i skonfiguruje wszystkie elementy wymagane do uruchomienia połączenia. Dotyczy to następujących składników: usług synchronizacji, Usług federacyjne Active Directory (AD FS) i modułu Azure AD PowerShell.

> [!TIP]
> Kreator Azure AD Connect obejmuje funkcje, które były wcześniej dostępne w narzędziach Dirsync i Azure AD Sync. Dowiedz się więcej na temat [integracji katalogów](http://technet.microsoft.com/library/jj573653.aspx). Aby poznać zalety synchronizowania kont użytkowników z katalogu lokalnego do usługi Azure AD, zobacz [Podobieństwa między usługami Active Directory i Azure AD](http://technet.microsoft.com/library/dn518177.aspx).

## Udzielanie uprawnień administratora
Po dodaniu użytkowników do subskrypcji usługi Intune zalecane jest przyznanie [poświadczeń administracyjnych](administrative-accounts-websites-perms.md) kilku kontom użytkowników. Konsola, której należy użyć do przypisania poświadczeń administracyjnych, zależy od typu administratora, który chcesz przypisać:

-   **Administrator dzierżawy**: użyj narzędzia **[!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)]**, aby przypisać ten typ administratora umożliwiający zarządzanie subskrypcją, w tym rozliczeniami, magazynem w chmurze oraz użytkownikami, którzy mogą korzystać z usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

-   **Administrator usługi**: użyj narzędzia **[!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]**, aby przypisać ten typ administratora umożliwiający wykonywanie codziennych zadań, w tym zarządzanie urządzeniami przenośnymi lub komputerami, wdrażanie zasad lub oprogramowania i uruchamianie raportów.


### Następne kroki
Gratulacje! Krok 3 *przewodnika Szybki start dotyczącego usługi Intune* został ukończony.

>[!div class="step-by-step"]

>[&larr;**Ustawienia domeny**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Zarządzanie licencjami usługi Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  



<!--HONumber=Aug16_HO5-->


