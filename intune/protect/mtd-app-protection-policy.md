---
title: Tworzenie zasad ochrony aplikacji usługi Mobile Threat Defense (MTD) za pomocą usługi Intune
titleSuffix: Microsoft Intune
description: Tworzenie zasad ochrony aplikacji usługi Mobile Threat Defense (MTD) za pomocą usługi Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 48dc7de86965741d8ed42bd5a5f29f72ae66d4f3
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "74188495"
---
# <a name="create-mobile-threat-defense-app-protection-policy-with-intune"></a>Tworzenie zasad ochrony aplikacji usługi Mobile Threat Defense za pomocą usługi Intune

Usługa Intune w połączeniu z usługą Mobile Threat Defense (MTD) pomaga wykrywać zagrożenia i oceniać ryzyko na urządzeniach przenośnych. Istnieje możliwość utworzenia zasad ochrony aplikacji usługi Intune, które oceniają ryzyko w celu określenia, czy urządzenie może uzyskać dostęp do danych firmowych.


> [!NOTE]
> Ten artykuł dotyczy wszystkich partnerów usługi Mobile Threat Defense, którzy obsługują zasady ochrony aplikacji:
>
> - Better Mobile (Android)
> - Zimperium (iOS)
> - Lookout for Work (Android, iOS)

## <a name="before-you-begin"></a>Przed rozpoczęciem

W ramach procesu konfiguracji usługi MTD w konsoli tej usługi zostały utworzone zasady, które klasyfikują zagrożenia jako wysokie, średnie i niskie. Teraz poziom usługi Mobile Threat Defense trzeba ustawić w zasadach ochrony aplikacji usługi Intune.

Wymagania wstępne dla zasad ochrony aplikacji za pomocą usługi MTD:

- Skonfiguruj integrację usługi MTD z usługą Intune. Bez tej integracji zasady ochrony aplikacji usługi MTD nie będą działać.

## <a name="to-create-an-mtd-app-protection-policy"></a>Tworzenie zasad ochrony aplikacji usługi MTD

Użyj procedury [tworzenia zasad ochrony aplikacji dla systemu iOS/iPadOS lub Android](../apps/app-protection-policies.md#app-protection-policies-for-iosipados-and-android-apps), a następnie użyj następujących informacji na stronach *Aplikacje*, *Uruchamianie warunkowe* i *Przypisania*:

- **Aplikacje**: wybierz aplikację dla partnera usługi Mobile Threat obrony, którego używasz.
- **Uruchamianie warunkowe**:  poniżej obszaru *Warunki urządzenia* użyj pola listy rozwijanej, aby wybrać **maksymalny dozwolony poziom zagrożenia urządzenia**.

  Opcje **wartości** poziomu zagrożenia:

  - **Zabezpieczone**: Ten poziom jest najbardziej bezpieczny. Urządzenie, na którym są obecne jakiekolwiek zagrożenia, nie może uzyskiwać dostępu do zasobów firmy. Jeśli zostaną znalezione jakiekolwiek zagrożenia, urządzenie zostanie ocenione jako niezgodne.
  - **Niski**: urządzenie jest zgodne, jeśli są obecne tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.
  - **Średni**: urządzenie jest zgodne, jeśli znalezione na nim zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia zagrożeń wysokiego poziomu urządzenie zostanie określone jako niezgodne.
  - **Wysoki**: ten poziom jest najmniej bezpieczny. Zezwala na wszystkie poziomy zagrożenia i używa usługi Mobile Threat Defense tylko do celów raportowania. Na urządzeniach musi znajdować się aplikacja MTD, w której to ustawienie zostało aktywowane.

  Opcje pola **Akcja**:

  - **Blokuj dostęp**
  - **Wyczyść dane**

- **Przypisania**: przypisz zasady do grup użytkowników.  Urządzenia używane przez członków grupy są oceniane pod kątem dostępu do danych firmowych za pomocą aplikacji docelowych przez funkcję ochrony aplikacji usługi Intune.


## <a name="next-steps"></a>Następne kroki  

- Dowiedz się więcej na temat [usługi Mobile Threat Defense](~/protect/mobile-threat-defense.md) w ramach usługi Microsoft Intune.
