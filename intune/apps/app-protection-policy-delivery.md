---
title: Omówienie dostarczania zasad ochrony aplikacji i jego harmonogramu
titleSuffix: Microsoft Intune
description: Poznaj różne okna wdrażania zasad ochrony aplikacji, aby dowiedzieć się, kiedy powinny pojawić się zmiany na urządzeniach użytkowników końcowych.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ec111319-7e02-434f-946b-88647726bf1a
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: b9f9b6734dc5a5af320519a5f65442f01d21d66f
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940236"
---
# <a name="understand-app-protection-policy-delivery-timing"></a>Omówienie harmonogramu dostarczania zasad ochrony aplikacji

Poznaj różne okna wdrażania zasad ochrony aplikacji, aby dowiedzieć się, kiedy powinny pojawić się zmiany na urządzeniach użytkowników końcowych.

## <a name="delivery-timing-summary"></a>Podsumowanie harmonogramu dostarczania

Dostarczanie zasad ochrony aplikacji jest zależne od stanu licencji i rejestracji usługi Intune dla użytkowników.  

|    Stan użytkownika    |    Zachowanie ochrony aplikacji     |    Interwał ponawiania prób (patrz uwaga)    |    Dlaczego tak się dzieje?    |
|-----------------------------------------------------|-------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
|    Nie dołączono dzierżawy    |    Poczekaj do następnego interwału ponawiania prób.  Ochrona aplikacji nie jest aktywna dla użytkownika.    |    24 godziny    |    Występuje, gdy nie skonfigurowano dzierżawy dla usługi Intune.    |
|    Użytkownik nie ma licencji     |    Poczekaj do następnego interwału ponawiania prób.  Ochrona aplikacji nie jest aktywna dla użytkownika.     |    12 godzin — jednak w przypadku urządzeń z systemem Android ten interwał wymaga zestawu SDK aplikacji usługi Intune w wersji 5.6.0 lub nowszej. W przeciwnym razie w przypadku urządzeń z systemem Android ten interwał będzie wynosił 24 godziny.   |    Występuje, gdy użytkownik ma nie licencję na usługę Intune.    |
|    Użytkownik nie ma przypisanych zasad ochrony aplikacji    |    Poczekaj do następnego interwału ponawiania prób.  Ochrona aplikacji nie jest aktywna dla użytkownika.    |    12 godzin        |    Występuje, gdy nie przypisano ustawień aplikacji dla użytkownika.    |
|    Użytkownik został pomyślnie zarejestrowany w zarządzaniu aplikacjami mobilnymi w usłudze Intune    |    Ochrona aplikacji jest stosowana na ustawienia zasad.    Aktualizacje są wykonywane zgodnie z interwałem ponawiania prób    |    Usługa Intune jest definiowana w oparciu o obciążenie użytkownikami.    Zazwyczaj 30 minut.     |    Występuje, gdy użytkownik został pomyślnie zarejestrowany w konfiguracji usługi Intune dla zarządzania aplikacjami mobilnymi.    |

> [!NOTE]
> Interwały ponawiania prób mogą wymagać aktywnego użycia aplikacji, co świadczy o tym, że aplikacja została uruchomiona i użyta.  Jeśli interwał ponawiania prób wynosi 24 godziny, a użytkownik zwleka 48 godzin z uruchomieniem aplikacji, klient ochrony aplikacji spróbuje ponowić próbę po 48 godzinach.

## <a name="handling-network-connectivity-issues"></a>Rozwiązywanie problemów z połączeniem sieciowym

Jeśli rejestracja użytkownika kończy się niepowodzeniem z powodu problemów z połączeniami sieciowymi, używany jest przyspieszony interwał ponowień prób.  Klient ochrony aplikacji będzie ponawiał próby w coraz dłuższych odstępach czasu, aż interwał osiągnie 60 minut lub zostanie pomyślnie nawiązane połączenie.  Klient będzie następnie kontynuował ponawianie prób co 60 minut do czasu pomyślnego nawiązania połączenia. Następnie klient powróci do standardowego interwału ponawiania prób na podstawie stanu użytkownika.

## <a name="next-steps"></a>Następne kroki

[Przypisanie użytkownikom licencji umożliwiających rejestrowanie urządzeń w usłudze Intune](../fundamentals/licenses-assign.md)
