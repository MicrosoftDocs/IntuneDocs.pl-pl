---
title: "Konfigurowanie zasad ochrony aplikacji podczas migracji do usługi Intune"
description: "W tym artykule przedstawiono niezbędne instrukcje dotyczące konfigurowania zasad ochrony aplikacji podczas migracji do usługi Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: c58ce51731b476cfca71851430297aff3edc5cd6
ms.sourcegitcommit: 388c5f59bc992375ac63968fd7330af5d84a1348
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2017
---
# <a name="configure-app-protection-policies-optional"></a>Konfigurowanie zasad ochrony aplikacji (opcjonalnie)


Zasady ochrony aplikacji umożliwiają:
* Szyfrowanie aplikacji
* Definiowanie numeru PIN podczas uzyskiwania dostępu do aplikacji
* Blokowanie aplikacji działających na urządzeniach ze złamanymi ograniczeniami lub z odblokowanym dostępem, a także działających bez wielu innych zabezpieczeń.

W przypadku zgubienia lub kradzieży telefonu użytkownika można zdalnie i selektywnie wymazać dane firmowe, pozostawiając niezmienione dane osobiste.

Zasady ochrony aplikacji pozwalają stosować zabezpieczenia na poziomie aplikacji i nie wymagają rejestracji urządzeń. Zasad można używać zarówno w przypadku urządzeń zarejestrowanych, jak i niezarejestrowanych w usłudze Intune. Ponadto można je stosować względem urządzeń zarejestrowanych w usługach MDM innych dostawców.

## <a name="app-protection-policies-with-lob-apps"></a>Zasady ochrony aplikacji biznesowych

Działanie zasad ochrony aplikacji mobilnych można także rozszerzyć na aplikacje biznesowe, korzystając z dostępnych zarówno dla platformy [iOS](https://www.microsoft.com/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True), jak i [Android](https://www.microsoft.com/download/details.aspx?id=47267), [zestawu SDK aplikacji usługi Microsoft Intune](app-sdk-get-started.md) lub narzędzia opakowującego aplikacje usługi Microsoft Intune.

## <a name="how-do-app-protection-policies-help-during-migration"></a>Jak zasady ochrony aplikacji mogą pomóc podczas migracji?

Podczas migracji należy usunąć urządzenia u starego dostawcy usług MDM i zarejestrować je w usłudze Intune. Proces ten należy zaplanować, zachęcając użytkowników końcowych do opuszczenia starego dostawcy usług MDM i natychmiastowego zarejestrowania się w usłudze Intune. Jednak może okazać się, że niektórzy użytkownicy zwlekają z ukończeniem procesu rejestracji, a ich urządzenia nie są zarządzane przez żadnego dostawcę usług MDM.

W tym czasie może nastąpić wzrost narażenia organizacji na kradzież urządzeń i — jeśli nie wyłączono dostępu do zasobów firmy — może dojść do utraty danych firmowych. Natomiast zablokowanie dostępu do zasobów firmy może prowadzić do spadku wydajności użytkowników.

Usługa Intune może zapewnić ochronę danych firmowych podczas migracji. Pozostają one bezpieczne nawet w przypadku braku zarządzania na poziomie urządzenia.

Po wyłączeniu dostępu warunkowego u starego dostawcy usług MDM użytkownicy mogą utrzymać swoją produktywność, gdy będą wprowadzani do usługi Intune.

## <a name="task-list-for-app-protection-policies"></a>Lista zadań dotyczących zasad ochrony aplikacji

1. [Tworzenie zasad ochrony aplikacji](app-protection-policies.md#create-an-app-protection-policy)
2. [Wdrażanie zasad](app-protection-policies.md#deploy-a-policy-to-users)


## <a name="next-steps"></a>Następne kroki

[Specjalne zagadnienia dotyczące migracji](migration-guide-considerations.md)
