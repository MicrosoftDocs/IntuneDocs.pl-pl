---
title: Sprawdzanie poprawności ustawień zasad ochrony aplikacji
titleSuffix: Microsoft Intune
description: Dowiedz się, jak przetestować poprawną konfigurację i działanie zasad ochrony aplikacji w usłudze Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/15/2019
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.topic: conceptual
ms.technology: ''
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 455f717e0e8ca4337cfef8693d5b71a0902b103f
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72499225"
---
# <a name="how-to-validate-your-app-protection-policy-setup-in-microsoft-intune"></a>Sposób sprawdzania poprawności ustawień zasad ochrony aplikacji w usłudze Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Sprawdzanie poprawnej konfiguracji i działania zasad ochrony aplikacji. Te wskazówki dotyczą zasad ochrony aplikacji w portalu Azure Portal.

## <a name="checking-for-symptoms"></a>Sprawdzanie pod kątem objawów
Zgłaszanie problemów przez użytkowników jest mało prawdopodobne, ponieważ ochrona aplikacji to narzędzie ochrony danych. W przypadku problemu z konfiguracją ochrony aplikacji użytkownik będzie mieć nieograniczony dostęp, taki jaki miałby bez stosowania ochrony aplikacji, i nie będzie świadomy wystąpienia problemu. Z tego powodu zaleca się przeprowadzenie walidacji konfiguracji ochrony aplikacji przez pilotażowe wdrożenie zasad ochrony aplikacji dla małej grupy użytkowników, którzy celowo przetestują ograniczenia związane z ochroną aplikacji.

## <a name="what-to-check"></a>Co należy sprawdzić

Jeśli wyniki testów pokazują, że zachowanie zasad ochrony aplikacji nie funkcjonuje w oczekiwany sposób, sprawdź następujące kwestie:

- Czy użytkownicy mają licencje na ochronę aplikacji?
- Czy użytkownicy mają licencje usługi O365?
- Czy stan każdej aplikacji użytkowników objętej ochroną aplikacji jest zgodny z oczekiwaniami? Możliwe stany aplikacji to **Zaewidencjonowano** i **Nie zaewidencjonowano**.

### <a name="user-app-protection-status"></a>Stan ochrony aplikacji użytkownika
1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Wybierz kolejno pozycje **Aplikacje klienckie** >  **Stan ochrony aplikacji**, a następnie wybierz kafelek **Przypisani użytkownicy**. 
4. Na stronie **Zgłaszanie aplikacji** wybierz pozycję **Wybierz użytkownika**, aby wyświetlić listę użytkowników i grup. 
5. Na liście wyszukaj i wybierz użytkownika, a następnie wybierz pozycję **Wybierz użytkownika**. W górnej części strony **Zgłaszanie aplikacji** widoczna jest informacja, czy użytkownik ma licencję na ochronę aplikacji. Możesz również zobaczyć, czy użytkownik ma licencję usługi O365, i sprawdzić stan aplikacji dla wszystkich urządzeń użytkownika.

## <a name="what-to-do"></a>Co należy zrobić
Poniżej przedstawiono akcje do wykonania na podstawie stanu użytkownika:

- Jeśli użytkownik nie ma licencji na ochronę aplikacji, przypisz [licencję usługi Intune](../fundamentals/licenses.md) do użytkownika.
- Jeśli użytkownik nie ma licencji usługi O365, uzyskaj [licencję](../fundamentals/licenses.md) dla użytkownika.
- Jeśli aplikacja użytkownika ma stan **Niezaewidencjonowane**, sprawdź, czy [zasady ochrony aplikacji](app-protection-policies-validate.md) zostały poprawnie skonfigurowane dla tej aplikacji.
- Upewnij się, że te warunki są stosowane do wszystkich użytkowników, do których mają być stosowane [zasady ochrony aplikacji](app-protection-policies-monitor.md).

## <a name="see-also"></a>Zobacz także

- [Co to są zasady ochrony aplikacji w usłudze Intune?](app-protection-policies.md)
- [Licencje, które obejmują usługę Intune](../fundamentals/licenses.md)
- [Przypisanie użytkownikom licencji umożliwiających rejestrowanie urządzeń w usłudze Intune](../fundamentals/licenses-assign.md)
- [Sposób sprawdzania poprawności ustawień zasad ochrony aplikacji](app-protection-policies-validate.md)
- [Monitorowanie zasad ochrony aplikacji](app-protection-policies-monitor.md)

