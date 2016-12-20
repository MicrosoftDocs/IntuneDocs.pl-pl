---
title: "Weryfikowanie konfiguracji zarządzania aplikacjami mobilnymi | Dokumentacja firmy Microsoft"
description: "W tym temacie opisano sposób sprawdzania i weryfikowania, czy zasady zarządzania aplikacjami mobilnymi są poprawnie skonfigurowane i działają zgodnie z oczekiwaniami."
keywords: 
author: andredm7
ms.author: andredm
manager: angerobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 41d82597-e13e-4c3e-9151-e71392236ca0
ms.reviewer: joglocke
translationtype: Human Translation
ms.sourcegitcommit: d6ff74f0b46baf384dbdedf13ad75538dd33a089
ms.openlocfilehash: 080d8f4fd4b6e1b53df860f4319b1c199d504c06


---

# <a name="validating-your-mobile-application-management-setup"></a>Weryfikowanie konfiguracji zarządzania aplikacjami mobilnymi

Ten temat zawiera informacje dotyczące sprawdzania występowania problemów po skonfigurowaniu zarządzania aplikacjami mobilnymi (MAM). Te wskazówki dotyczą zasad zarządzania aplikacjami mobilnymi w witrynie Azure Portal.

### <a name="checking-for-symptoms"></a>Sprawdzanie pod kątem objawów
Zgłaszanie problemów przez użytkowników nie jest prawdopodobne, ponieważ MAM to narzędzie ochrony danych. W przypadku problemu z konfiguracją zarządzania aplikacjami mobilnymi użytkownik będzie miał nieograniczony dostęp, taki jaki miałby bez stosowania funkcji MAM, i nie będzie świadomy, że wystąpił problem. Z tego powodu zaleca się zweryfikowanie konfiguracji zarządzania aplikacjami mobilnymi przez wprowadzenie ich pilotażowo dla małej grupy użytkowników, którzy będą mogli celowo przetestować ograniczenia MAM.


### <a name="what-to-check"></a>Co należy sprawdzić

Jeśli testowanie pokazuje, że zachowanie zasad zarządzania aplikacjami mobilnymi nie jest zgodne z przewidywanym, zaleca się sprawdzenie następujących kwestii:

- Czy użytkownicy mają licencje do zarządzania aplikacjami mobilnymi?
- Czy użytkownicy mają licencje usługi O365?
- Stan każdej z aplikacji zarządzania aplikacjami mobilnymi użytkowników. Możliwe stany aplikacji to **Zaewidencjonowano** i **Nie zaewidencjonowano**.

#### <a name="user-mam-status"></a>Stan zarządzania aplikacjami mobilnymi użytkownika
1. W witrynie Azure Portal wybierz pozycję **Zarządzanie aplikacjami mobilnymi w usłudze Intune** > **Ustawienia** > **Zarządzanie aplikacjami** > **Wszystkie ustawienia** > **Raportowanie aplikacji według użytkownika** > **Użytkownicy**.

2. Wybierz użytkownika z listy lub wyszukaj i wybierz użytkownika, a następnie wybierz pozycję **Wybierz użytkownika**. W górnej części kolumny **Raportowanie aplikacji** zobaczysz, czy użytkownik ma licencję do zarządzania aplikacjami mobilnymi. Poniżej zobaczysz, czy użytkownik ma licencję usługi O365 i sprawdzisz stan aplikacji dla wszystkich urządzeń użytkownika.

![Stan aplikacji dla zarządzania aplikacjami mobilnymi](..\media\ts-mam-user-apps.png)

### <a name="what-to-do"></a>Co należy zrobić
Poniżej przedstawiono akcje do wykonania na podstawie stanu użytkownika:

- Jeśli użytkownik nie ma licencji do zarządzania aplikacjami mobilnymi, przypisz licencję usługi Intune do użytkownika zgodnie z opisem w temacie [Zarządzanie licencjami usługi Intune](..\get-started\start-with-a-paid-subscription-to-microsoft-intune.md).
- Jeśli użytkownik nie ma licencji usługi O365, uzyskaj licencję dla użytkownika.
- Jeśli aplikacja użytkownika jest wyświetlana jako **Nie zaewidencjonowano**, sprawdź, czy poprawnie skonfigurowano zasady zarządzania aplikacjami mobilnymi dla tej aplikacji.
- Upewnij się, że te warunki są stosowane dla wszystkich użytkowników, do których mają być stosowane zasady zarządzania aplikacjami mobilnymi.

### <a name="see-also"></a>Zobacz także
[Przygotowywanie się do konfigurowania zasad zarządzania aplikacjami mobilnymi przy użyciu usługi Microsoft Intune](..\deploy-use\get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

[Ochrona danych aplikacji przy użyciu zasad zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](..\deploy-use\protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


