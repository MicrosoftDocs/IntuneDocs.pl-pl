---
title: Tworzenie zasad zgodności urządzeń usługi MTD w usłudze Microsoft Intune
titleSuffix: Microsoft Intune
description: Utwórz zasady zgodności urządzeń usługi Intune wykorzystujące poziomy zagrożeń partnera MTD w celu określenia, czy urządzenie przenośne może uzyskiwać dostęp do zasobów firmy.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/20/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5d12254f-ffab-4792-b19c-ab37f5e02f35
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 504c77fb56918cf97312e70f50b38356f9f7efef
ms.sourcegitcommit: a7b479c84b3af5b85528db676594bdb3a1ff6ec6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/22/2019
ms.locfileid: "74409693"
---
# <a name="create-mobile-threat-defense-mtd-device-compliance-policy-with-intune"></a>Tworzenie zasad zgodności urządzeń usługi Mobile Threat Defense (MTD) za pomocą usługi Intune

Usługa Intune w połączeniu z usługą MTD pomaga wykrywać zagrożenia i oceniać ryzyko na urządzeniach przenośnych. Można utworzyć regułę zasad zgodności urządzeń w usłudze Intune, która ocenia ryzyko w celu określenia, czy urządzenie jest zgodne. Następnie można użyć [zasad dostępu warunkowego](create-conditional-access-intune.md), aby zablokować dostęp do usług w oparciu o zgodność urządzenia.

> [!NOTE]
> Niniejsze informacje dotyczą wszystkich partnerów usługi Mobile Threat Defense.

## <a name="before-you-begin"></a>Przed rozpoczęciem

W ramach procesu konfiguracji usługi MTD w konsoli tej usługi zostały utworzone zasady, które klasyfikują zagrożenia jako wysokie, średnie i niskie. Teraz w zasadach zgodności urządzeń w usłudze Intune trzeba ustawić odpowiedni poziom dla usługi MTD.

Wymagania wstępne dotyczące zasad zgodności urządzeń i usługi MTD:

- Skonfigurowanie integracji z usługą MTD w usłudze Intune

## <a name="to-create-an-mtd-device-compliance-policy"></a>Aby utworzyć zasady zgodności urządzenia usługi MTD

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz pozycję **Urządzenie** > **Zasady zgodności** > **Utwórz zasady**.

3. Podaj wartości w polach **Nazwa** i **Opis** dla zasad zgodności urządzenia, wybierz pozycję **Platforma**, a następnie wybierz pozycję **Konfiguruj** w sekcji **Ustawienia**.

4. W okienku **Zasady zgodności** wybierz pozycję **Kondycja urządzenia**.

5. W okienku **Kondycja urządzenia** wybierz poziom zagrożeń mobilnych z listy rozwijanej dla opcji **Wymagaj od urządzenia, aby jego poziom zagrożenia był niższy lub równy poziomowi zagrożenia urządzenia**.

   - **Zabezpieczone**: Ten poziom jest najbardziej bezpieczny. Urządzenie, na którym są obecne jakiekolwiek zagrożenia, nie może uzyskiwać dostępu do zasobów firmy. Jeśli zostaną znalezione jakiekolwiek zagrożenia, urządzenie zostanie ocenione jako niezgodne.

   - **Niski**: urządzenie jest zgodne, jeśli są obecne tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.

   - **Średni**: urządzenie jest zgodne, jeśli znalezione na nim zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia zagrożeń wysokiego poziomu urządzenie zostanie określone jako niezgodne.

   - **Wysoki**: ten poziom jest najmniej bezpieczny. Zezwala na wszystkie poziomy zagrożenia i wykorzystuje usługę Mobile Threat Defense w programie Skycure tylko do celów raportowania. Na urządzeniach musi znajdować się aplikacja MTD, w której to ustawienie zostało aktywowane.

6. Dwukrotnie wybierz przycisk **OK**, a następnie wybierz pozycję **Utwórz**, aby utworzyć zasady.

> [!IMPORTANT]
> W przypadku tworzenia zasad dostępu warunkowego dla usługi Office 365 lub innych usług ta ocena zgodności urządzeń jest oceniana i dostęp niezgodnych urządzeń do tych zasobów firmowych jest blokowany do momentu usunięcia zagrożenia na urządzeniu.

## <a name="to-assign-an-mtd-device-compliance-policy"></a>Aby przypisać zasady zgodności urządzenia usługi MTD

Aby przypisać zasady zgodności urządzenia do użytkowników:

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz pozycję **Urządzenie** > **Zasady zgodności**.

3. Wybierz zasady, które chcesz przypisać użytkownikom, a następnie wybierz pozycję **Przypisania**. Skorzystaj z dostępnych opcji, aby *uwzględnić* i *wykluczyć* grupy, które mają otrzymać te zasady.  

4. Wybierz przycisk Zapisz, aby ukończyć przypisywanie. Po zapisaniu przypisania zasady są wdrażane dla wybranych użytkowników i ich urządzenia są oceniane pod kątem zgodności.

## <a name="next-steps"></a>Następne kroki

[Włączanie rozwiązania MTD w usłudze Intune](mtd-connector-enable.md)
