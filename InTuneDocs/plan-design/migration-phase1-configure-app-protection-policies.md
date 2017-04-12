---
title: "Konfigurowanie zasad ochrony aplikacji podczas migracji do usługi Intune | Microsoft Docs"
description: "Celem tego artykułu jest przedstawienie niezbędnych instrukcji dotyczących konfigurowania zasad ochrony aplikacji podczas migracji do usługi Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: 35543604ed68393e859517e32f5186247be001df
ms.lasthandoff: 03/27/2017


---

# <a name="phase-1-configure-app-protection-policies-optional"></a>Faza 1: Konfiguracja zasad ochrony aplikacji (opcjonalnie)

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Zasady ochrony aplikacji pozwalają szyfrować aplikacje, definiować numer PIN umożliwiający uzyskanie dostępu do aplikacji oraz blokować uruchamianie aplikacji na urządzeniach ze złamanymi zabezpieczeniami lub odblokowanym dostępem do konta root. Oprócz tego udostępniają wiele innych mechanizmów ochrony. W przypadku zgubienia lub kradzieży telefonu użytkownika można za pomocą zasad ochrony aplikacji mobilnych zdalnie i selektywnie wymazać dane firmowe, pozostawiając niezmienione dane osobiste.

Zasady ochrony aplikacji pozwalają stosować zabezpieczenia na poziomie aplikacji i nie wymagają rejestracji urządzeń. Można ich używać zarówno w przypadku urządzeń zarejestrowanych, jak i niezarejestrowanych w usłudze Intune. Ponadto można je stosować z urządzeniami zarejestrowanymi w usługach MDM innych dostawców.

## <a name="app-protection-policies-with-lob-apps"></a>Zasady ochrony aplikacji biznesowych

Działanie zasad ochrony aplikacji mobilnych można także rozszerzyć na aplikacje biznesowe (LOB), korzystając z dostępnych zarówno dla platformy [iOS](https://www.microsoft.com/en-us/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True), jak i [Android](https://www.microsoft.com/en-us/download/details.aspx?id=47267) [zestawu SDK aplikacji usługi Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management) lub narzędzia opakowującego aplikacje usługi Microsoft Intune.

## <a name="how-do-app-protection-policies-help-during-migration"></a>Jak zasady ochrony aplikacji mogą pomóc podczas migracji?

Migracja wymaga usunięcia urządzeń u starego dostawcy usług MDM i ich zarejestrowania w usłudze Intune. Proces ten należy zaplanować, zachęcając użytkowników końcowych do opuszczenia starego dostawcy usług MDM i natychmiastowego zarejestrowania się w usłudze Intune. Jednak może okazać się, że niektórzy użytkownicy zwlekają z ukończeniem procesu rejestracji, a ich urządzenia nie są zarządzane przez żadnego dostawcę usług MDM.

W tym czasie może nastąpić wzrost narażenia organizacji na kradzież urządzeń i — jeśli nie wyłączono dostępu do zasobów firmy — utratę danych firmowych. Z kolei zablokowanie dostępu do zasobów firmy może prowadzić do spadku wydajności pracy użytkowników.

Usługa Intune może zapewnić ochronę danych firmowych podczas migracji. Pozostają one bezpieczne nawet w przypadku braku zarządzania na poziomie urządzenia.

Po wyłączeniu dostępu warunkowego u starego dostawcy usług MDM użytkownicy mogą utrzymać swoją produktywność, gdy będą wprowadzani do usługi Intune.

## <a name="task-list-for-app-protection-policies"></a>Lista zadań dotyczących zasad ochrony aplikacji

-   Zadanie 1. Dowiedz się, [jak się przygotować do konfigurowania zasad ochrony aplikacji mobilnych](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)

-   Zadanie 2. Dowiedz się, [jak utworzyć i wdrożyć zasady ochrony aplikacji mobilnych](https://docs.microsoft.com/en-us/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)

## <a name="next-steps"></a>Następne kroki 

[Faza 1: Specjalne zagadnienia dotyczące migracji](https://docs.microsoft.com/intune/plan-design/migration-phase1-special-migration-considerations)

