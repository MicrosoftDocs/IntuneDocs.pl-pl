---
title: Tworzenie zasad zgodności urządzeń usługi MTD w usłudze Microsoft Intune
titleSuffix: Microsoft Intune
description: Utwórz zasady zgodności urządzeń usługi Intune wykorzystujące poziomy zagrożeń partnera MTD w celu określenia, czy urządzenie przenośne może uzyskiwać dostęp do zasobów firmy.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5d12254f-ffab-4792-b19c-ab37f5e02f35
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2315136fe277f06f6dbb11c13139a9dc193ce6f7
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2019
ms.locfileid: "67549366"
---
# <a name="create-mobile-threat-defense-mtd-device-compliance-policy-with-intune"></a>Tworzenie zasad zgodności urządzeń usługi Mobile Threat Defense (MTD) za pomocą usługi Intune

> [!NOTE] 
> Niniejsze informacje dotyczą wszystkich partnerów usługi Mobile Threat Defense.

Usługa Intune w połączeniu z usługą MTD pomaga wykrywać zagrożenia i oceniać ryzyko na urządzeniach przenośnych. Można utworzyć regułę zasad zgodności urządzeń w usłudze Intune, która ocenia ryzyko w celu określenia, czy urządzenie jest zgodne. Następnie można użyć [zasad dostępu warunkowego](create-conditional-access-intune.md), aby zablokować dostęp do usług w oparciu o zgodność urządzenia.

## <a name="before-you-begin"></a>Przed rozpoczęciem

W ramach procesu konfiguracji usługi MTD w konsoli tej usługi zostały utworzone zasady, które klasyfikują zagrożenia jako wysokie, średnie i niskie. Teraz w zasadach zgodności urządzeń w usłudze Intune trzeba ustawić odpowiedni poziom dla usługi MTD.

Wymagania wstępne dotyczące zasad zgodności urządzeń i usługi MTD:

- Skonfigurowanie integracji z usługą MTD w usłudze Intune

## <a name="to-create-an-mtd-device-compliance-policy"></a>Aby utworzyć zasady zgodności urządzenia usługi MTD

1. Przejdź do witryny [Azure Portal](https://portal.azure.com/) i zaloguj się przy użyciu swoich poświadczeń usługi Intune.

2. Na stronie **Pulpit nawigacyjny platformy Azure** w menu po lewej stronie wybierz pozycję **Wszystkie usługi**, a następnie w filtrze pola tekstowego wpisz wartość **Intune**.

3. Wybierz pozycję **Intune**. Zostanie otwarty **Pulpit nawigacyjny Intune**.

4. Na stronie **Pulpit nawigacyjny usługi Intune** wybierz pozycję **Zgodność urządzeń**, a następnie wybierz pozycję **Zasady** w sekcji **Zarządzanie**.

5. Wybierz pozycję **Utwórz zasady**, wypełnij pola **Nazwa** i **Opis** dotyczące zgodności urządzeń, zaznacz pozycję **Platforma**, a następnie wybierz pozycję **Konfiguruj** w sekcji **Ustawienia**.

6. W okienku **Zasady zgodności** wybierz pozycję **Kondycja urządzenia**.

7. W okienku **Kondycja urządzenia** wybierz poziom zagrożeń mobilnych z listy rozwijanej w obszarze **Wymagaj od urządzenia, aby jego poziom zagrożenia był niższy lub równy poziomowi zagrożenia urządzenia**.

    a.  **Zabezpieczone**: Ten poziom jest najbardziej bezpieczny. Urządzenie, na którym są obecne jakiekolwiek zagrożenia, nie może uzyskiwać dostępu do zasobów firmy. Jeśli zostaną znalezione jakiekolwiek zagrożenia, urządzenie zostanie ocenione jako niezgodne.

    b.  **Niski**: urządzenie jest zgodne, jeśli są obecne tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.

    c.  **Średni**: urządzenie jest zgodne, jeśli znalezione na nim zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia zagrożeń wysokiego poziomu urządzenie zostanie określone jako niezgodne.

    d.  **Wysoki**: ten poziom jest najmniej bezpieczny. Zezwala na wszystkie poziomy zagrożenia i wykorzystuje usługę Mobile Threat Defense w programie Skycure tylko do celów raportowania. Na urządzeniach musi znajdować się aplikacja MTD, w której to ustawienie zostało aktywowane.

8. Kliknij przycisk **OK** dwa razy, a następnie wybierz pozycję **Utwórz**.

> [!IMPORTANT]
> W przypadku tworzenia zasad dostępu warunkowego dla usługi Office 365 lub innych usług ta ocena zgodności urządzeń jest oceniana i dostęp niezgodnych urządzeń do tych zasobów firmowych jest blokowany do momentu usunięcia zagrożenia na urządzeniu.

## <a name="to-assign-an-mtd-device-compliance-policy"></a>Aby przypisać zasady zgodności urządzenia usługi MTD

Aby przypisać użytkownikom zasady zgodności urządzeń, wybierz wcześniej skonfigurowane przez siebie zasady. Istniejące zasady znajdują się w okienku **Zgodność urządzeń — zasady**.

1. Wybierz zasady, które chcesz przypisać użytkownikom, a następnie wybierz pozycję **Przypisania**. Spowoduje to otwarcie okienka, w którym można wybrać **grupy zabezpieczeń usługi Azure Active Directory** i przypisać je do zasad.

2. Wybierz pozycję **Wybierz grupy do uwzględnienia**, aby otworzyć stronę, na której zostaną wyświetlone grupy zabezpieczeń usługi Azure AD.  Wybranie pozycji **Wybierz** powoduje wdrożenie zasad dla użytkowników.

    > [!NOTE] 
    > Zasady zostały zastosowane do użytkowników. Urządzenia, którymi posługują się użytkownicy objęci zasadami, zostaną ocenione pod kątem zgodności.

## <a name="next-steps"></a>Następne kroki

- [Włączanie rozwiązania MTD w usłudze Intune](mtd-connector-enable.md)
