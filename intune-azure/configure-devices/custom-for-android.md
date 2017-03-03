---
title: "Ustawienia niestandardowe dla urządzeń z systemem Android w usłudze Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące ustawień, których można używać w niestandardowym profilu systemu Android."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: d6181b24d94bb151df036241d0a8b6b987f1483d
ms.lasthandoff: 02/18/2017


---

# <a name="custom-settings-for-android-devices-in-microsoft-intune"></a>Ustawienia niestandardowe dla urządzeń z systemem Android w usłudze Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Profil **Niestandardowy** systemu Android w usłudze Microsoft Intune umożliwia wdrożenie ustawień OMA-URI, których można użyć do sterowania funkcjami na urządzeniach z systemem Android. Są to ustawienia standardowe używane przez wielu producentów urządzeń przenośnych do sterowania funkcjami urządzeń.

Ta funkcja ma umożliwić wdrażanie ustawień systemu Android, których nie można skonfigurować przy użyciu zasad usługi Intune.

## <a name="custom-profile-settings-for-android-devices"></a>Niestandardowe ustawienia profilu dla urządzeń z systemem Android

1. Aby rozpocząć pracę, postępuj zgodnie z instrukcjami w artykule [How to configure custom device settings in Microsoft Intune](how-to-configure-custom-settings.md) (Jak skonfigurować niestandardowe ustawienia urządzenia w usłudze Microsoft Intune).
2. W bloku **Tworzenie profilu** wybierz pozycję **Ustawienia**, aby dodać co najmniej jedno ustawienie OMA-URI.
3. W bloku **Edytowanie wiersza** skonfiguruj następujące wartości dla każdego ustawienia:
    - **Nazwa** — wprowadź unikatową nazwę ustawienia OMA-URI, aby ułatwić jego identyfikację na liście ustawień.
    - **Opis** — podaj opis, który zawiera omówienie ustawienia oraz inne istotne informacje ułatwiające jego wyszukanie.
    - **Typ danych** — wybierz typ danych, przy pomocy których określisz to ustawienie OMA-URI. Wybierz jedną z opcji: **Ciąg**, **Ciąg (XML)**, **Data i godzina**, **Liczba całkowita**, **Liczba zmiennoprzecinkowa** lub **Wartość logiczna**.
    - **OMA-URI** — określ identyfikator OMA-URI, dla którego chcesz podać ustawienie.
    - **Wartość** — wprowadź wartość, którą chcesz skojarzyć z wprowadzonym identyfikatorem OMA-URI.
4. Gdy wszystko będzie gotowe, kliknij przycisk **OK**, a następnie, jeśli to konieczne, dodaj więcej ustawień.

