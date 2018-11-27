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
ms.openlocfilehash: 080205e601b857d4765eb6b97eeeeeb8f4e6fc1b
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52187161"
---
# <a name="use-scope-tags-to-filter-policies"></a>Używanie tagów zakresu do filtrowania zasad

Tagi zakresu umożliwiają filtrowanie zasad za pomocą tagów niestandardowych, które samodzielnie tworzysz.

Na przykład utwórz tag zakresu o nazwie „Dział inżynieryjny” i przypisz go do profilów konfiguracji związanych z działem inżynieryjnym. Przypisz ten sam znacznik do roli „Administratorzy inżynieryjni”. Będą oni widzieli tylko zasady z tagiem „Dział inżynieryjny”.

## <a name="to-create-a-scope-tag"></a>Aby utworzyć tag zakresu

Wybierz pozycję **Role** > **Zakres (tagi)** > **Utwórz**.

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Aby dodać tag zakresu do profilu konfiguracji

Wybierz pozycję **Konfiguracja urządzenia** > **Profile** > wybierz profil > **Właściwości** > **Zakres (tagi)**.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Aby przypisać tag zakresu do roli

Wybierz pozycję **Role** > **Wszystkie role** > **Menedżer zasad i profilów** > **Przypisania** > **Zakres (tagi)**.

## <a name="next-steps"></a>Następne kroki

Zarządzanie własnymi [rolami](role-based-access-control.md) i [profilami](device-profile-assign.md).

