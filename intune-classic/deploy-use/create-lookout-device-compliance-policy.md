---
title: "Włączanie reguły ochrony urządzenia | Microsoft Docs"
description: "Włącz regułę ochrony przed zagrożeniami mobilnymi w zasadach zgodności urządzenia."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 67913bfcbca3cef52e309ad86bfe722db6e16895
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="create-lookout-device-compliance-policy-in-intune"></a>Tworzenie zasad zgodności urządzeń z rozwiązaniem Lookout w usłudze Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Usługa Intune z usługą Lookout Mobile Threat Defense umożliwia wykrywanie zagrożeń na urządzeniach przenośnych i ocenę ryzyka na tych urządzeniach. Można utworzyć regułę zasad zgodności, która ocenia ryzyko w celu określenia, czy urządzenie jest zgodne. Następnie można użyć zasad dostępu warunkowego, aby zablokować dostęp do usług w oparciu o zgodność urządzenia.

Wymagania wstępne dotyczące zasad zgodności z usługą Lookout Mobile Threat Defense:

- [Skonfigurowanie subskrypcji usługi Lookout Mobile Threat Defense](setup-your-lookout-mtd-subscription.md)
- [Włączenie połączenia usługi Lookout w usłudze Intune](enable-lookout-mtd-connection.md)
- [Skonfigurowanie i wdrożenie aplikacji Lookout for Work](configure-deploy-lookout-for-work-app.md)

W ramach procesu konfiguracji usługi Lookout Mobile Threat Defense w [konsoli usługi Lookout](https://aad.lookout.com) zostały utworzone zasady, które klasyfikują zagrożenia jako wysokie, średnie i niskie. W zasadach zgodności usługi Intune można ustawić maksymalny dozwolony poziom zagrożenia.

1. W [konsoli administratora usługi Intune](https://manage.microsoft.com) przejdź do strony **Zasady zgodności**. Możesz użyć istniejących zasad zgodności lub utworzyć nowe. Przejdź do pozycji **Kondycja urządzenia** i włącz opcję **Ochrona urządzenia przed zagrożeniami**.
  ![zrzut ekranu przedstawiający ustawienie reguły ochrony urządzenia przed zagrożeniami w ](../media/mtp/mtp-compliance-policy-rule.png)

2. Wybierz pozycję **Maksymalny dozwolony poziom zagrożenia**:
  * **Brak (zabezpieczone)** — to ustawienie zapewnia najwyższy poziom zabezpieczeń.  Urządzenie, na którym są obecne jakiekolwiek zagrożenia, nie może uzyskiwać dostępu do zasobów firmy.  Jeśli zostaną znalezione jakiekolwiek zagrożenia, urządzenie zostanie ocenione jako niezgodne.  
  * **Niski**: urządzenie jest zgodne, jeśli są obecne tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.
  * **Średni**: urządzenie jest zgodne, jeśli znalezione na nim zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia zagrożeń wysokiego poziomu urządzenie zostanie określone jako niezgodne.
  * **Wysoki**: to ustawienie zapewnia najniższy poziom zabezpieczeń. Zezwala na wszystkie poziomy zagrożenia, a usługa Lookout do ochrony urządzeń przenośnych przed zagrożeniami jest używana tylko do celów raportowania.

![zrzut ekranu przedstawiający opcję poziomu zagrożeń dla ustawienia reguły ochrony urządzeń przed zagrożeniami](../media/mtp/mtp-compliance-policy-setting.png)

W przypadku tworzenia zasad dostępu warunkowego dla usługi Office 365 lub innych usług ta ocena zgodności jest oceniana i dostęp niezgodnych urządzeń do tych usług pozostanie zablokowany do momentu usunięcia zagrożenia.

## <a name="monitor-device-threats"></a>Monitorowanie zagrożeń dotyczących urządzeń
Aby wyświetlić stan zgodności urządzenia, przejdź do [konsoli administratora usługi Intune](https://manage.microsoft.com) i wyświetl pozycję **Wszystkie urządzenia**.

![zrzut ekranu przedstawiający stronę urządzeń w konsoli administracyjnej usługi Intune z wyświetlonym stanem zgodności urządzenia](../media/mtp/mtp-device-status-intune-console.png)

## <a name="next-steps"></a>Następne kroki
* Tworzenie zasad dostępu warunkowego
  * [Usługa Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [Lokalna instalacja programu Exchange](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [Skype dla firm Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)

