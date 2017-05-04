---
title: "Tworzenie zasad zgodności usługi Skycure Mobile Threat Defense | Dokumentacja firmy Microsoft"
description: "Utwórz zasady zgodności usługi Skycure Mobile Threat Defense w klasycznej konsoli usługi Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 56ff1728-1119-4e8a-aae6-ed5c7fafa052
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e10453155343bb7fd91a4fd3874d393ef78d0b1a
ms.openlocfilehash: c28ba63136c1037c8c8191e9a7f46fa9a4823b4e
ms.lasthandoff: 04/25/2017


---

# <a name="create-skycure-mobile-threat-defense-compliance-policy"></a>Tworzenie zasad zgodności usługi Skycure Mobile Threat Defense

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Usługa Intune z usługą Skycure Mobile Threat Defense umożliwia wykrywanie zagrożeń na urządzeniach przenośnych i ocenę ryzyka na tych urządzeniach. Można utworzyć regułę zasad zgodności usługi Intune, która ocenia ryzyko w celu określenia, czy urządzenie jest zgodne. Następnie można użyć zasad dostępu warunkowego, aby zablokować dostęp do usług w oparciu o zgodność urządzenia.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Wymagania wstępne dotyczące zasad zgodności z ochroną urządzeń przed zagrożeniami w programie Skycure:

-   [Konfiguracja integracji z programem Skycure w usłudze Intune](https://docs.microsoft.com/intune/deploy-use/setup-the-skycure-integration-with-Intune)

-   [Włączenie połączenia programu Skycure w usłudze Intune](https://docs.microsoft.com/intune/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

W ramach procesu konfiguracji usługi Skycure Mobile Threat Defense w konsoli Skycure zostały utworzone zasady, które klasyfikują zagrożenia jako wysokie, średnie i niskie. Teraz w zasadach zgodności usługi Intune trzeba ustawić maksymalny dozwolony poziom zagrożenia.

## <a name="to-create-skycure-compliance-policy"></a>Aby utworzyć zasady zgodności programu Skycure

1.  Przejdź do [klasycznej konsoli usługi Intune](https://manage.microsoft.com/) i wprowadź swoje poświadczenia.

2.  Wybierz opcję **Zasady** &gt; **Zasady zgodności**. Możesz użyć istniejących zasad zgodności lub utworzyć nowe.

3.  Wybierz pozycję **Dodaj** &gt; **Kondycja urządzenia**, a następnie włącz opcję **Ochrona urządzenia przed zagrożeniami**.

4.  Wybierz pozycję **Maksymalny dozwolony poziom zagrożenia**:

    a.  **Brak (zabezpieczone)** — to ustawienie zapewnia najwyższy poziom zabezpieczeń. Urządzenie, na którym są obecne jakiekolwiek zagrożenia, nie może uzyskiwać dostępu do zasobów firmy. Jeśli zostaną znalezione jakiekolwiek zagrożenia, urządzenie zostanie ocenione jako niezgodne.

    b.  **Niski**: urządzenie jest zgodne, jeśli są obecne tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.

    c.  **Średni**: urządzenie jest zgodne, jeśli znalezione na nim zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia zagrożeń wysokiego poziomu urządzenie zostanie określone jako niezgodne.

    d.  **Wysoki**: to ustawienie zapewnia najniższy poziom zabezpieczeń. Zezwala na wszystkie poziomy zagrożenia i wykorzystuje usługę ochrony urządzeń przenośnych przed zagrożeniami w programie Skycure tylko do celów raportowania.

> [!IMPORTANT]
> W przypadku tworzenia zasad dostępu warunkowego dla usługi Office 365 lub innych usług ta ocena zgodności jest oceniana i dostęp niezgodnych urządzeń do tych usług pozostanie zablokowany do momentu usunięcia zagrożenia.

## <a name="span-idmonitor-device-threats-classanchorspan-idnext-steps-classanchorspan-idtoc477360344-classanchorspanspanspannext-steps"></a><span id="monitor-device-threats" class="anchor"><span id="next-steps" class="anchor"><span id="_Toc477360344" class="anchor"></span></span></span>Następne kroki

-   Utwórz zasady dostępu warunkowego dla:

    -   [Exchange Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
    -   [Lokalna instalacja programu Exchange](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
    -   [SharePoint Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)
    -   [Skype dla firm Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)
    -   [Dynamics CRM](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)

