---
title: "Tworzenie zasad zgodności urządzeń usługi Mobile Threat Defense za pomocą usługi Intune"
titlesuffix: Azure portal
description: "Tworzenie zasad zgodności urządzeń usługi Mobile Threat Defense w usłudze Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d12254f-ffab-4792-b19c-ab37f5e02f35
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2e9b1a3dc42a9c18d61fc9b55d5a7b71f00c3e29
ms.sourcegitcommit: d434dfab7ef7a6c4082d675717fa22d5581b4f51
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/19/2017
---
# <a name="create-mobile-threat-defense-mtd-device-compliance-policy-with-intune"></a>Tworzenie zasad zgodności urządzeń usługi Mobile Threat Defense (MTD) za pomocą usługi Intune

> [!NOTE] 
> Niniejszy temat dotyczy wszystkich partnerów narzędzi Mobile Threat Defense.

Usługa Intune w połączeniu z usługą MTD pomaga wykrywać zagrożenia i oceniać ryzyko na urządzeniach przenośnych. Można utworzyć regułę zasad zgodności urządzeń w usłudze Intune, która ocenia ryzyko w celu określenia, czy urządzenie jest zgodne. Następnie można użyć zasad dostępu warunkowego, aby zablokować dostęp do usług w oparciu o zgodność urządzenia.

## <a name="before-you-begin"></a>Przed rozpoczęciem

W ramach procesu konfiguracji usługi MTD w konsoli tej usługi zostały utworzone zasady, które klasyfikują zagrożenia jako wysokie, średnie i niskie. Teraz w zasadach zgodności urządzeń w usłudze Intune trzeba ustawić odpowiedni poziom dla usługi MTD.

Wymagania wstępne dotyczące zasad zgodności urządzeń i usługi MTD:

-   Skonfigurowanie integracji z usługą MTD w usłudze Intune

## <a name="to-create-a-mtd-device-compliance-policy"></a>Utworzenie zasad zgodności urządzeń usługi MTD

1.  Przejdź do witryny [Azure Portal](https://portal.azure.com/) i zaloguj się przy użyciu swoich poświadczeń usługi Intune.

2.  Na stronie **Pulpit nawigacyjny Azure** w menu po lewej stronie wybierz opcję **Więcej usług**, a następnie w filtrze pola tekstowego wpisz **Intune**.

3.  Wybierz pozycję **Intune**. Zostanie otwarty **Pulpit nawigacyjny Intune**.

4. Na stronie **Pulpit nawigacyjny usługi Intune** wybierz pozycję **Zgodność urządzeń**, a następnie wybierz pozycję **Zasady** w sekcji **Zarządzanie**.

5.  Wybierz pozycję **Utwórz zasady**, wypełnij pola **Nazwa** i **Opis** dotyczące zgodności urządzeń, zaznacz pozycję **Platforma**, a następnie wybierz pozycję **Konfiguruj** w sekcji **Ustawienia**.

6.  W bloku **Zasady zgodności** wybierz pozycję **Kondycja urządzenia**.

7.  W bloku **Kondycja urządzenia** wybierz poziom zagrożeń mobilnych z listy rozwijanej w obszarze **Wymagaj od urządzenia, aby jego poziom zagrożenia był niższy lub równy poziomowi zagrożeń mobilnych**.

    a.  **Zabezpieczone**: to ustawienie zapewnia najwyższy poziom zabezpieczeń. Urządzenie, na którym są obecne jakiekolwiek zagrożenia, nie może uzyskiwać dostępu do zasobów firmy. Jeśli zostaną znalezione jakiekolwiek zagrożenia, urządzenie zostanie ocenione jako niezgodne.

    b.  **Niski**: urządzenie jest zgodne, jeśli są obecne tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.

    c.  **Średni**: urządzenie jest zgodne, jeśli znalezione na nim zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia zagrożeń wysokiego poziomu urządzenie zostanie określone jako niezgodne.

    d.  **Wysoki**: to ustawienie zapewnia najniższy poziom zabezpieczeń. Zezwala na wszystkie poziomy zagrożenia i wykorzystuje usługę Mobile Threat Defense w programie Skycure tylko do celów raportowania. Na urządzeniach musi znajdować się aplikacja MTD, w której to ustawienie zostało aktywowane.

8.  Kliknij przycisk **OK** dwa razy, a następnie wybierz pozycję **Utwórz**.

> [!IMPORTANT]
> W przypadku tworzenia zasad dostępu warunkowego dla usługi Office 365 lub innych usług ta ocena zgodności urządzeń jest oceniana i dostęp niezgodnych urządzeń do tych zasobów firmowych pozostanie zablokowany do momentu usunięcia zagrożenia na urządzeniu.

## <a name="to-assign-a-mtd-device-compliance-policy"></a>Aby przypisać zasady zgodności urządzeń usługi MTD

Aby przypisać użytkownikom zasady zgodności urządzeń, wybierz wcześniej skonfigurowane przez siebie zasady. Istniejące zasady znajdują się w bloku **Zasady zgodności urządzeń**.

1. Wybierz zasady, które chcesz przypisać użytkownikom, a następnie wybierz pozycję **Przypisania**. Spowoduje to otwarcie bloku, w którym można wybrać **grupy zabezpieczeń usługi Azure Active Directory** i przypisać je do zasad.

2. Wybierz pozycję **Wybierz grupy**, aby otworzyć blok, w którym zostaną wyświetlone grupy zabezpieczeń usługi Azure AD.  Wybranie pozycji **Wybierz** powoduje wdrożenie zasad dla użytkowników.

    > [!NOTE] 
    > Zasady zostały zastosowane do użytkowników. Urządzenia, którymi posługują się użytkownicy objęci zasadami, zostaną ocenione pod kątem zgodności.

## <a name="next-steps"></a>Następne kroki

- [Włączanie rozwiązania MTD w usłudze Intune](mtd-connector-enable.md)