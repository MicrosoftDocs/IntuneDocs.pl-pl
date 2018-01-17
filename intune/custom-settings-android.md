---
title: "Ustawienia niestandardowe dla urządzeń z systemem Android w usłudze Intune"
titleSuffix: Azure portal
description: "Informacje dotyczące ustawień, których można używać w niestandardowym profilu systemu Android."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 09/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3b1ccb3b0b7b2ce024ff6a09d7f9d8366896fb67
ms.sourcegitcommit: 5004b9564915712b41860df20324f39fac3dc27d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/03/2018
---
# <a name="custom-settings-for-android-devices-in-microsoft-intune"></a>Ustawienia niestandardowe dla urządzeń z systemem Android w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Profil **Niestandardowy** systemu Android w usłudze Microsoft Intune umożliwia przypisanie ustawień OMA-URI, których można użyć do sterowania funkcjami na urządzeniach z systemem Android. Są to ustawienia standardowe używane przez wielu producentów urządzeń przenośnych do sterowania funkcjami urządzeń.

Ta funkcja ma umożliwić przypisanie następujących ustawień systemu Android, których nie można skonfigurować przy użyciu zasad usługi Intune:

- [Tworzenie profilu sieci Wi-Fi z użyciem klucza wstępnego za pomocą niestandardowego profilu urządzenia usługi Microsoft Intune](/intune/wi-fi-profile-shared-key)
- [Korzystanie z niestandardowego profilu usługi Microsoft Intune w celu tworzenia profilu sieci VPN dla aplikacji dla urządzeń z systemem Android](/intune/android-pulse-secure-per-app-vpn)
- [Użycie niestandardowych zasad do zezwalania na aplikacje i blokowania ich na urządzeniach z systemem Samsung Knox Standard w usłudze Microsoft Intune](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
>Obecnie tylko ustawienia wymienione powyżej mogą być konfigurowane przez ten typ profilu. Urządzenia z systemem Android nie ujawniają pełnej listy ustawień OMA-URI, które można skonfigurować. Jeśli chcesz zobaczyć więcej dodanych ustawień, prześlij żądanie w [witrynie Intune Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas).

## <a name="custom-profile-settings-for-android-devices"></a>Niestandardowe ustawienia profilu dla urządzeń z systemem Android

1. Aby rozpocząć pracę, postępuj zgodnie z instrukcjami w artykule [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) (Jak skonfigurować niestandardowe ustawienia urządzenia w usłudze Microsoft Intune).
2. W bloku **Tworzenie profilu** wybierz pozycję **Ustawienia**, aby dodać co najmniej jedno ustawienie OMA-URI.
3. W bloku **Edytowanie wiersza** skonfiguruj następujące wartości dla każdego ustawienia:
    - **Nazwa** — wprowadź unikatową nazwę ustawienia OMA-URI, aby ułatwić jego identyfikację na liście ustawień.
    - **Opis** — podaj opis, który zawiera omówienie ustawienia oraz inne istotne informacje ułatwiające jego wyszukanie.
    - **Typ danych** — wybierz typ danych, przy pomocy których określisz to ustawienie OMA-URI. Wybierz jedną z opcji: **Ciąg**, **Ciąg (XML)**, **Data i godzina**, **Liczba całkowita**, **Liczba zmiennoprzecinkowa** lub **Wartość logiczna**.
    - **OMA-URI** — określ identyfikator OMA-URI, dla którego chcesz podać ustawienie.
    - **Wartość** — wprowadź wartość, którą chcesz skojarzyć z wprowadzonym identyfikatorem OMA-URI.
4. Gdy wszystko będzie gotowe, kliknij przycisk **OK**, a następnie, jeśli to konieczne, dodaj więcej ustawień.

## <a name="next-steps"></a>Następne kroki

Po zakończeniu konfiguracji ustawień profil zostanie utworzony i wyświetlony w bloku listy profilów. Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](device-profile-assign.md) (Sposoby przypisywania profilów urządzeń).




