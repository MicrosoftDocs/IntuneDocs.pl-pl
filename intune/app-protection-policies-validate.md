---
title: Sprawdzanie poprawności ustawień zasad ochrony aplikacji
titleSuffix: Microsoft Intune
description: Dowiedz się, jak przetestować poprawną konfigurację i działanie zasad ochrony aplikacji.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/13/2018
ms.prod: ''
ms.service: microsoft-intune
ms.topic: article
ms.technology: ''
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 3158d0531de4809bf654c030b8c1e0ef90185362
ms.sourcegitcommit: 8019bdd8117806c6a3a73a8c6d40af1a3def6d90
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2018
ms.locfileid: "53247071"
---
# <a name="how-to-validate-your-app-protection-policy-setup"></a>Sposób sprawdzania poprawności ustawień zasad ochrony aplikacji

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Sprawdzanie poprawnej konfiguracji i działania zasad ochrony aplikacji. Te wskazówki dotyczą zasad ochrony aplikacji w portalu Azure Portal.

### <a name="checking-for-symptoms"></a>Sprawdzanie pod kątem objawów
Zgłaszanie problemów przez użytkowników jest mało prawdopodobne, ponieważ ochrona aplikacji to narzędzie ochrony danych. W przypadku problemu z konfiguracją ochrony aplikacji użytkownik będzie mieć nieograniczony dostęp, taki jaki miałby bez stosowania ochrony aplikacji, i nie będzie świadomy wystąpienia problemu. Z tego powodu zaleca się przeprowadzenie walidacji konfiguracji ochrony aplikacji przez pilotażowe wdrożenie zasad ochrony aplikacji dla małej grupy użytkowników, którzy celowo przetestują ograniczenia związane z ochroną aplikacji.


### <a name="what-to-check"></a>Co należy sprawdzić

Jeśli wyniki testów pokazują, że zachowanie zasad ochrony aplikacji nie jest zgodne z oczekiwanym, sprawdź następujące kwestie:

- Czy użytkownicy mają licencje na ochronę aplikacji?
- Czy użytkownicy mają licencje usługi O365?
- Stan każdej aplikacji użytkowników objętej ochroną aplikacji. Możliwe stany aplikacji to **Zaewidencjonowano** i **Nie zaewidencjonowano**.

#### <a name="user-app-protection-status"></a>Stan ochrony aplikacji użytkownika
1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. Wybierz kolejno pozycje **Aplikacje klienckie** > **Monitorowanie** >  **Stan ochrony aplikacji**, a następnie wybierz kafelek **Przypisani użytkownicy**. 
4. Na stronie **Zgłaszanie aplikacji** wybierz pozycję **Wybierz użytkownika**, aby wyświetlić listę użytkowników i grup. 
5. Na liście wyszukaj i wybierz użytkownika, a następnie wybierz pozycję **Wybierz użytkownika**. W górnej części strony **Zgłaszanie aplikacji** widoczna jest informacja, czy użytkownik ma licencję na ochronę aplikacji. Możesz również zobaczyć, czy użytkownik ma licencję usługi O365, i sprawdzić stan aplikacji dla wszystkich urządzeń użytkownika.



### <a name="what-to-do"></a>Co należy zrobić
Poniżej przedstawiono akcje do wykonania na podstawie stanu użytkownika:

- Jeśli użytkownik nie ma licencji na ochronę aplikacji, przypisz licencję usługi Intune do użytkownika.
- Jeśli użytkownik nie ma licencji usługi O365, uzyskaj licencję dla użytkownika.
- Jeśli aplikacja użytkownika ma stan **Niezaewidencjonowane**, sprawdź, czy zasady ochrony aplikacji zostały poprawnie skonfigurowane dla tej aplikacji.
- Upewnij się, że te warunki są stosowane do wszystkich użytkowników, do których mają być stosowane zasady ochrony aplikacji.

### <a name="see-also"></a>Zobacz też

[Co to są zasady ochrony aplikacji w usłudze Intune?](app-protection-policies.md)
