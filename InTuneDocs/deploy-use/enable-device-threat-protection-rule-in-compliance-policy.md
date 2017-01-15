---
title: "Włączanie reguły ochrony urządzenia w zasadach zgodności | Microsoft Docs"
description: "Włącz regułę ochrony przed zagrożeniami mobilnymi w zasadach zgodności urządzenia."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 80e96003c584c67cb6b0289a7e2ed1ff3a833c2c
ms.openlocfilehash: 3dea6c35d5fc035a5aef6dda52543b64cd5ce177


---

# <a name="enable-device-threat-protection-rule-in-the-compliance-policy"></a>Włączanie reguły ochrony urządzenia przed zagrożeniami w zasadach zgodności

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Usługa Intune z usługą Lookout do ochrony przed zagrożeniami mobilnymi umożliwia wykrywanie zagrożeń na urządzeniach przenośnych i ocenę ryzyka na tych urządzeniach. Można utworzyć regułę zasad zgodności, która ocenia ryzyko w celu określenia, czy urządzenie jest zgodne. Następnie można użyć zasad dostępu warunkowego, aby zablokować dostęp do usług w oparciu o zgodność urządzenia.

Wymagania wstępne dotyczące zasad zgodności z ochroną urządzeń przed zagrożeniami w usłudze Lookout:

- [Skonfigurowanie subskrypcji ochrony urządzeń przed zagrożeniami w usłudze Lookout](set-up-your-subscription-with-lookout-mtp.md)
- [Włączenie połączenia usługi Lookout w usłudze Intune](enable-lookout-mtp-connection-in-intune.md)
- [Skonfigurowanie aplikacji Lookout for Work](configure-and-deploy-lookout-for-work-apps.md)

W ramach procesu konfiguracji ochrony urządzeń przed zagrożeniami w usłudze Lookout w [konsoli usługi Lookout](https://aad.lookout.com) zostały utworzone zasady, które klasyfikują zagrożenia jako wysokie, średnie i niskie. W zasadach zgodności usługi Intune można ustawić maksymalny dozwolony poziom zagrożenia.

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



<!--HONumber=Dec16_HO4-->


