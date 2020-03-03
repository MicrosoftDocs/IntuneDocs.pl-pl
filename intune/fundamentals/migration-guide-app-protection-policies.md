---
title: Konfigurowanie zasad ochrony aplikacji podczas migracji
titleSuffix: Microsoft Intune
description: W tym artykule przedstawiono niezbędne instrukcje dotyczące konfigurowania zasad ochrony aplikacji podczas migracji do usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/09/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 183a1dc7083aa9b427df225297fb7c393939220f
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77515054"
---
# <a name="configure-app-protection-policies-optional"></a>Konfigurowanie zasad ochrony aplikacji (opcjonalnie)


Zasady ochrony aplikacji umożliwiają:
* Szyfrowanie aplikacji
* Definiowanie numeru PIN podczas uzyskiwania dostępu do aplikacji
* Blokowanie aplikacji działających na urządzeniach ze złamanymi ograniczeniami lub z odblokowanym dostępem, a także działających bez wielu innych zabezpieczeń.

W przypadku zgubienia lub kradzieży telefonu użytkownika można zdalnie i selektywnie wymazać dane firmowe, pozostawiając niezmienione dane osobiste.

Zasady ochrony aplikacji pozwalają stosować zabezpieczenia na poziomie aplikacji i nie wymagają rejestracji urządzeń. Zasad można używać zarówno w przypadku urządzeń zarejestrowanych, jak i niezarejestrowanych w usłudze Intune. Ponadto można je stosować względem urządzeń zarejestrowanych w usługach MDM innych dostawców.

## <a name="app-protection-policies-with-lob-apps"></a>Zasady ochrony aplikacji biznesowych

Działanie zasad ochrony aplikacji mobilnych można także rozszerzyć na aplikacje biznesowe, korzystając z zestawu [Microsoft Intune App SDK](../developer/app-sdk-get-started.md) lub narzędzia opakowującego aplikacje usługi Microsoft Intune. Materiały te są dostępne zarówno dla platformy iOS/iPadOS, jak i Android. Aby uzyskać więcej informacji, zobacz temat [Narzędzie opakowujące aplikacje dla systemu iOS](../developer/app-wrapper-prepare-ios.md) i [Narzędzie opakowujące aplikacje dla systemu Android](./../developer/app-wrapper-prepare-android.md). Zobacz też temat [Przygotowanie aplikacji biznesowych pod kątem zasad ochrony aplikacji](../developer/apps-prepare-mobile-application-management.md).

## <a name="how-do-app-protection-policies-help-during-migration"></a>Jak zasady ochrony aplikacji mogą pomóc podczas migracji?

Podczas migracji należy usunąć urządzenia u starego dostawcy usług MDM i zarejestrować je w usłudze Intune. Proces ten należy zaplanować, zachęcając użytkowników końcowych do opuszczenia starego dostawcy usług MDM i natychmiastowego zarejestrowania się w usłudze Intune. Jednak może okazać się, że niektórzy użytkownicy zwlekają z ukończeniem procesu rejestracji, a ich urządzenia nie są zarządzane przez żadnego dostawcę usług MDM.

W tym czasie może nastąpić wzrost narażenia organizacji na kradzież urządzeń i — jeśli nie wyłączono dostępu do zasobów firmy — może dojść do utraty danych firmowych. Natomiast zablokowanie dostępu do zasobów firmy może prowadzić do spadku wydajności użytkowników.

Usługa Intune może zapewnić ochronę danych firmowych podczas migracji. Pozostają one bezpieczne nawet w przypadku braku zarządzania na poziomie urządzenia.

Po wyłączeniu dostępu warunkowego u starego dostawcy usług MDM użytkownicy mogą utrzymać swoją produktywność, gdy będą wprowadzani do usługi Intune.

## <a name="task-list-for-app-protection-policies"></a>Lista zadań dotyczących zasad ochrony aplikacji

- [Tworzenie i przypisywanie zasad ochrony aplikacji](~/apps/app-protection-policies.md)

## <a name="next-steps"></a>Następne kroki

[Specjalne zagadnienia dotyczące migracji](migration-guide-considerations.md)
