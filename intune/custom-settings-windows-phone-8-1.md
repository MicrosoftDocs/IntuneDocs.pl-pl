---
title: Ustawienia niestandardowe w usłudze Microsoft Intune dla urządzeń z systemem Windows Phone 8.1
titleSuffix: ''
description: Dowiedz się więcej na temat ustawień, których można używać w niestandardowym profilu systemu Windows Phone 8.1.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 83c123f3752680dbc7faca76aa525a0f035831d7
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-windows-phone-81"></a>Niestandardowe ustawienia urządzeń w usłudze Microsoft Intune dla urządzeń z systemem Windows Phone 8.1

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Profil **niestandardowy** systemu Windows Phone 8.1 w usłudze Microsoft Intune umożliwia przypisanie ustawień OMA-URI, których można użyć do sterowania funkcjami na urządzeniach z systemem Windows Phone 8.1. Są to ustawienia standardowe używane przez wielu producentów urządzeń przenośnych do sterowania funkcjami urządzeń.

Ta funkcja ma umożliwić przypisanie ustawień, których nie można skonfigurować przy użyciu zasad usługi Intune.

## <a name="custom-policy-settings-for-windows-phone-81-devices"></a>Ustawienia zasad niestandardowych dla urządzeń z systemem Windows Phone 8.1

1. Aby rozpocząć pracę, postępuj zgodnie z instrukcjami w artykule [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) (Jak skonfigurować niestandardowe ustawienia urządzenia w usłudze Microsoft Intune).
2. W okienku **Niestandardowe ustawienia OMA-URI** wybierz pozycję **Dodaj**, aby dodać co najmniej jedno ustawienie OMA-URI.
3. W okienku **Dodawanie wiersza** skonfiguruj następujące wartości dla każdego ustawienia:
    - **Nazwa** — wprowadź unikatową nazwę ustawienia OMA-URI, aby ułatwić jego identyfikację na liście ustawień.
    - **Opis** — podaj opis, który zawiera omówienie ustawienia oraz inne istotne informacje ułatwiające jego wyszukanie.
    - **OMA-URI** — określ identyfikator OMA-URI, dla którego chcesz podać ustawienie.
    - **Typ danych** — wybierz typ danych, przy pomocy którego określisz to ustawienie OMA-URI. Wybierz jeden z następujących typów: **Ciąg**, **Ciąg (XML)**, **Data i godzina**, **Liczba całkowita**, **Liczba zmiennoprzecinkowa**, **Wartość logiczna** lub **Base64**.
    - **Wartość** — wprowadź wartość lub plik do skojarzenia z wprowadzonym identyfikatorem OMA-URI.

4. Gdy wszystko będzie gotowe, kliknij przycisk **OK**, a następnie, jeśli to konieczne, dodaj więcej ustawień.
