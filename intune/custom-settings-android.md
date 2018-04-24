---
title: Dodawanie ustawień niestandardowych dla urządzeń z systemem Android w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodawanie lub tworzenie profilu niestandardowego dla urządzeń z systemem Android w celu utworzenia profilu sieci Wi-Fi z kluczem wstępnym, utworzenia profilu sieci VPN dla aplikacji lub zezwalania na użycie bądź blokowanie aplikacji dla urządzeń z system Samsung Knox Standard w usłudze Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0195e138b59fae019fa2bc02aadf211257a65cac
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="custom-settings-for-android-devices---intune"></a>Ustawienia niestandardowe dla urządzeń z systemem Android — Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W przypadku profilów niestandardowych używane są ustawienia jednolitego identyfikatora zasobów Open Mobile Alliance (OMA-URI, Open Mobile Alliance Uniform Resource Identifier) w celu skonfigurowania różnych funkcji na urządzeniach z systemem Android. Te ustawienia są zwykle używane przez producentów urządzeń przenośnych w celu kontrolowania funkcji na urządzeniu.

Używając profilu niestandardowego, możesz skonfigurować lub przypisać następujące ustawienia systemu Android. Te ustawienia nie są wbudowane w zasady usługi Intune:

- [Tworzenie profilu sieci Wi-Fi z użyciem klucza wstępnego](/intune/wi-fi-profile-shared-key)
- [Tworzenie profilu sieci VPN dla aplikacji](/intune/android-pulse-secure-per-app-vpn)
- [Zezwalanie na użycie i blokowanie aplikacji na urządzeniach z systemem Samsung Knox Standard](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
> Przez ten typ profilu można skonfigurować tylko wymienione ustawienia. Urządzenia z systemem Android nie ujawniają pełnej listy ustawień identyfikatora OMA-URI, które można skonfigurować. Jeśli chcesz widzieć więcej ustawień, zagłosuj na więcej ustawień na [witrynie Intune Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas).

## <a name="custom-profile-settings-for-android-devices"></a>Niestandardowe ustawienia profilu dla urządzeń z systemem Android

1. Zaloguj się do [portalu Azure](https://portal.azure.com). 
2. Wybierz pozycję **Wszystkie usługi**, odfiltruj ciąg **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Utwórz profil niestandardowy przy użyciu platformy systemu Android. Aby poznać czynności, jakie należy wykonać, zobacz [Konfigurowanie niestandardowych ustawień urządzenia w usłudze Microsoft Intune](custom-settings-configure.md).
4. W obszarze **Niestandardowe ustawienia OMA-URI** wybierz pozycję **Dodaj**, a następnie pozycję **Dodaj wiersz**.
5. Wprowadź następujące właściwości:

   - **Nazwa** — wprowadź unikatową nazwę dla ustawienia identyfikatora OMA-URI, aby możne je było łatwo odnaleźć.
   - **Opis elementu** — wprowadź opis ułatwiający identyfikację ustawienia oraz zawierający inne ważne szczegóły.
   - **Typ danych** — wprowadź typ danych używany w przypadku tego ustawienia identyfikatora OMA-URI. Wybierz jedną z opcji: **Ciąg**, **Ciąg (XML)**, **Data i godzina**, **Liczba całkowita**, **Liczba zmiennoprzecinkowa** lub **Wartość logiczna**.
   - **OMA-URI** — wprowadź odpowiedni identyfikator OMA-URI.
   - **Wartość** — wprowadź wartość, którą chcesz skojarzyć z wprowadzonym identyfikatorem OMA-URI.

6. Wybierz przycisk **OK**, aby zapisać zmiany. W razie potrzeby kontynuuj dodawanie ustawień.

## <a name="next-steps"></a>Następne kroki

Po zakończeniu konfiguracji ustawień profil zostanie utworzony i wyświetlony na liście. Aby przypisać ten profil do grup, zobacz [Jak przypisywać profile urządzeń](device-profile-assign.md).
