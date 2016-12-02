---
title: "Włączanie reguły ochrony urządzenia w zasadach zgodności | Microsoft Intune"
description: "Włącz regułę ochrony przed zagrożeniami mobilnymi w zasadach zgodności urządzenia."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 686321a1c19acb9a3a7e262822b11304d07adb40
ms.openlocfilehash: 3e6aef013ae8764d9b031e880c333e184191feb4


---

# <a name="enable-device-threat-protection-rule-in-the-compliance-policy"></a>Włączanie reguły ochrony urządzenia przed zagrożeniami w zasadach zgodności
Usługa Intune z aplikacją Lookout do ochrony urządzeń przenośnych przed zagrożeniami umożliwia wykrywanie zagrożeń mobilnych i ocenę ryzyka na urządzeniu. Można utworzyć regułę zasad zgodności, aby uwzględnić ocenę ryzyka w celu określenia, czy urządzenie jest zgodne. Następnie można użyć zasad dostępu warunkowego, aby zezwolić na dostęp lub zablokować dostęp do programów Exchange, SharePoint i innych usług w oparciu o zgodność urządzenia.

Aby wykrywanie zagrożeń dotyczących urządzeń w usłudze Lookout miało wpływ na zasady zgodności dla urządzenia:

* Reguła **Ochrona urządzeń przed zagrożeniami** musi być włączona w zasadach zgodności.

* Na stronie **Stan usługi Lookout** w **konsoli administratora usługi Intune** musi być wyświetlana wartość **Aktywna**. Aby uzyskać bardziej szczegółowe informacje oraz instrukcje dotyczące sposobu aktywacji integracji z usługą Lookout, zobacz [Enable Lookout MTP connection in Intune](enable-lookout-mtp-connection-in-intune.md) (Włączanie połączenia z usługą Lookout MTP w usłudze Intune).


Przed utworzeniem reguły ochrony urządzenia przed zagrożeniami w zasadach zgodności zaleca się [skonfigurowanie subskrypcji przy użyciu usługi ochrony urządzeń przed zagrożeniami w usłudze Lookout](set-up-your-subscription-with-lookout-mtp.md), [włączenie połączenia z usługą Lookout w usłudze Intune](enable-lookout-mtp-connection-in-intune.md) i [skonfigurowanie aplikacji Lookout for Work](configure-and-deploy-lookout-for-work-apps.md). Reguła zgodności jest wymuszana tylko po przeprowadzeniu konfiguracji.

Aby włączyć regułę ochrony urządzenia przed zagrożeniami, można użyć istniejących zasad zgodności lub utworzyć nowe.

W ramach procesu konfiguracji ochrony urządzeń przed zagrożeniami w usłudze Lookout w [konsoli usługi Lookout](https://aad.lookout.com) zostały utworzone zasady, które klasyfikują zagrożenia na poziomie wysokim, średnim i niskim. W zasadach zgodności usługi Intune poziom zagrożenia będzie używany do ustawiania maksymalnego dozwolonego poziomu zagrożenia.

Na stronie **Zasady zgodności** w **konsoli administratora usługi Intune** przejdź do obszaru **Kondycja urządzenia** i włącz regułę **Ochrona urządzeń przed zagrożeniami** za pomocą opcji przełączania. Następnie wybierz maksymalny dozwolony poziom zagrożenia, który będzie miał jedną z następujących wartości:
* **Brak (zabezpieczone)**: to ustawienie zapewnia najwyższy poziom zabezpieczeń.  Oznacza to, że urządzenie nie może mieć żadnych zagrożeń.  Jeśli zostaną znalezione zagrożenia dowolnego poziomu, urządzenie zostanie ocenione jako niezgodne.  
* **Niski**: urządzenie jest oceniane jako zgodne, jeśli istnieją tylko zagrożenia niskiego poziomu. Jakiekolwiek zagrożenia wyższego poziomu spowodują, że urządzenie będzie miało status urządzenia niezgodnego.
* **Średni**: urządzenie jest oceniane jako zgodne, jeśli dotyczące go zagrożenia są na poziomie niskim lub średnim. W przypadku wykrycia zagrożeń wysokiego poziomu urządzenie zostanie określone jako niezgodne.
* **Wysoki**: to ustawienie zapewnia najniższy poziom zabezpieczeń. Zasadniczo to ustawienie zezwala na wszystkie poziomy zagrożeń i może być przydatne tylko wtedy, jeśli jest używane jedynie na potrzeby raportowania.

![zrzut ekranu przedstawiający ustawienie reguły ochrony urządzenia przed zagrożeniami w ](../media/mtp/mtp-compliance-policy-rule.png)

![zrzut ekranu przedstawiający opcję poziomu zagrożeń dla ustawienia reguły ochrony urządzeń przed zagrożeniami](../media/mtp/mtp-compliance-policy-setting.png)

W przypadku tworzenia zasad dostępu warunkowego dla usługi Office 365 i innych usług powyższa ocena zgodności jest brana pod uwagę i dostęp niezgodnych urządzeń do zasobów firmy pozostanie zablokowany do momentu usunięcia zagrożenia.

Stan zgodności urządzenia można zobaczyć na stronie **Wszystkie urządzenia**w **konsoli administratora usługi Intune**.

![zrzut ekranu przedstawiający stronę urządzeń w konsoli administracyjnej usługi Intune z wyświetlonym stanem zgodności urządzenia](../media/mtp/mtp-device-status-intune-console.png)

## <a name="next-steps"></a>Następne kroki
* Tworzenie zasad dostępu warunkowego
  * [Usługa Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [Lokalna instalacja programu Exchange](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [Skype dla firm Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Nov16_HO5-->


