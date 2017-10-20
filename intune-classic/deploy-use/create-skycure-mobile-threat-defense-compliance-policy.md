---
title: "Tworzenie zasad zgodności usługi Skycure Mobile Threat Defense"
description: "Utwórz zasady zgodności usługi Skycure Mobile Threat Defense w portalu klasycznym usługi Intune."
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
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f601253c6ea905e86a2a417cfd37bdb03b1df48b
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2017
---
# <a name="create-skycure-mobile-threat-defense-compliance-policy"></a>Tworzenie zasad zgodności usługi Skycure Mobile Threat Defense

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Usługa Intune z usługą Skycure Mobile Threat Defense umożliwia wykrywanie zagrożeń na urządzeniach przenośnych i ocenę ryzyka na tych urządzeniach. Można utworzyć regułę zasad zgodności usługi Intune, która ocenia ryzyko w celu określenia, czy urządzenie jest zgodne. Następnie można użyć zasad dostępu warunkowego, aby zablokować dostęp do usług w oparciu o zgodność urządzenia.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Wymagania wstępne dotyczące zasad zgodności z ochroną urządzeń przed zagrożeniami w programie Skycure:

-   [Konfiguracja integracji z programem Skycure w usłudze Intune](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)

-   [Włączenie połączenia programu Skycure w usłudze Intune](/intune-classic/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

W ramach procesu konfiguracji usługi Skycure Mobile Threat Defense w konsoli Skycure zostały utworzone zasady, które klasyfikują zagrożenia jako wysokie, średnie i niskie. Teraz w zasadach zgodności usługi Intune trzeba ustawić maksymalny dozwolony poziom zagrożenia.

## <a name="to-create-skycure-compliance-policy"></a>Aby utworzyć zasady zgodności programu Skycure

1.  Przejdź do [portalu klasycznego usługi Intune](https://manage.microsoft.com/) i wprowadź swoje poświadczenia.

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

    -   [Exchange Online](/intune-classic/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
    -   [Lokalna instalacja programu Exchange](/intune-classic/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
    -   [SharePoint Online](/intune-classic/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)
    -   [Skype dla firm Online](/intune-classic/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)
    -   [Dynamics CRM](/intune-classic/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)
