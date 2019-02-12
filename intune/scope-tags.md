---
title: Filtrowanie zasad przy użyciu tagów zakresu w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Tagi zakresu umożliwiają filtrowanie profilów konfiguracji dla określonych ról.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9441f1c69e3d445d6174521ad2c9ef5c7a6db2be
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55835541"
---
# <a name="use-scope-tags-to-filter-policies"></a>Używanie tagów zakresu do filtrowania zasad

Tagi zakresu umożliwiają filtrowanie zasad za pomocą tagów niestandardowych, które samodzielnie tworzysz. Tagi zakresu można zastosować do ról i aplikacji.

Na przykład utwórz tag zakresu o nazwie „Dział inżynieryjny” i przypisz go do profilów konfiguracji związanych z działem inżynieryjnym. Przypisz ten sam znacznik do roli „Administratorzy inżynieryjni”. Będą oni widzieli tylko zasady z tagiem „Dział inżynieryjny”.

## <a name="to-create-a-scope-tag"></a>Aby utworzyć tag zakresu

Wybierz pozycję **Role** > **Zakres (tagi)** > **Utwórz**.

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Aby dodać tag zakresu do profilu konfiguracji

Wybierz pozycję **Konfiguracja urządzenia** > **Profile** > wybierz profil > **Właściwości** > **Zakres (tagi)**.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Aby przypisać tag zakresu do roli

Wybierz pozycję **Role** > **Wszystkie role** > **Menedżer zasad i profilów** > **Przypisania** > **Zakres (tagi)**.

## <a name="to-assign-a-scope-tag-to-an-app"></a>Aby przypisać tag zakresu do aplikacji

Wybierz pozycję **Aplikacje klienckie** > **Aplikacje** > wybierz aplikację > **Właściwości** > **Zakres (tagi)** > **Dodaj** > wybierz tagi > **Wybierz** > **OK** > **Zapisz**.


## <a name="next-steps"></a>Następne kroki

Zarządzanie własnymi [rolami](role-based-access-control.md) i [profilami](device-profile-assign.md).

