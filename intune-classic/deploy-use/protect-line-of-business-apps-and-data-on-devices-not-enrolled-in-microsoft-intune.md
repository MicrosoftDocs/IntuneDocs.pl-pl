---
title: Ochrona aplikacji biznesowych na urządzeniach, które nie zostały zarejestrowane
description: W tym temacie opisano, jak można przygotować swoje niestandardowe aplikacje biznesowe, aby mogły stosować zasady zarządzania aplikacjami mobilnymi, co może pomóc w uniknięciu utraty danych.
keywords: ''
author: mattbriggs
ms.author: mabriggs
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 00219467-a62e-43b6-954b-3084f54c45ba
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0fbc7ae1937aff60e8e494df06ee2c30e2fe8855
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31020354"
---
# <a name="protect-line-of-business-apps-and-data-on-devices-that-are-not-enrolled-in-microsoft-intune"></a>Ochrona aplikacji biznesowych i danych na urządzeniach niezarejestrowanych w usłudze Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Zasady zarządzania aplikacjami mobilnymi (MAM, mobile application management) pomagają chronić dane firmy przez ograniczanie możliwości wykonywania akcji, które mogą spowodować wyciek danych firmy i narzucenie wymagań w zakresie dostępu do danych (np. kod PIN w aplikacji). Aby zastosować zasady zarządzania aplikacjami mobilnymi do aplikacji biznesowych systemu iOS lub Android, należy najpierw opakować aplikację przy użyciu narzędzia opakowującego dostępnego w usłudze Microsoft Intune. Opakowywanie aplikacji jest procesem stosowania warstwy zarządzania względem aplikacji mobilnej bez konieczności wprowadzania zmian w aplikacji i rozpowszechniania ich wśród użytkowników.  

W tym temacie objaśniono czynności wymagane do stosowania zasad zarządzania aplikacjami mobilnymi do aplikacji używanych przez użytkowników na **niezarządzanych urządzeniach należących do pracowników** i urządzeniach zarządzanych przez **rozwiązanie do zarządzania urządzeniami przenośnymi (MDM, mobile device management) oferowane przez inną firmę**.  Aby przygotować aplikacje biznesowe uruchamiane na **urządzeniach zarejestrowanych w ramach zarządzania urządzeniami przenośnymi w usłudze Intune**, zobacz [Wybieranie sposobu przygotowania aplikacji do zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](/intune/apps-prepare-mobile-application-management).


##  <a name="step-1-prepare-the-app"></a>Krok 1. Przygotowywanie aplikacji

Przed zastosowaniem zasad zarządzania aplikacjami mobilnymi do aplikacji należy najpierw opakować aplikację za pomocą narzędzia opakowującego w usłudze Microsoft Intune dla systemów [iOS](/intune/app-wrapper-prepare-ios) i [Android](/intune/app-wrapper-prepare-android) lub użyć [zestawu Intune App SDK](/intune/app-sdk) w celu ręcznego zintegrowania funkcji ochrony aplikacji usługi Intune.

Aby uzyskać więcej informacji na temat korzystania z narzędzia opakowującego aplikacje lub zestawu SDK aplikacji usługi Intune, zobacz temat [Wybieranie sposobu przygotowania aplikacji do zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](/intune/apps-prepare-mobile-application-management).

## <a name="step-2-add-the-app"></a>Krok 2. Dodawanie aplikacji

Aby skojarzyć aplikację biznesową z zasadami zarządzania aplikacjami mobilnymi, należy dodać szczegóły aplikacji do subskrypcji/dzierżawy usługi Intune, wykonując poniższe czynności:

1. W [portalu Azure](https://portal.azure.com/) przejdź do pozycji **Zarządzanie aplikacjami mobilnymi usługi Intune**  > **Ustawienia** i wybierz pozycję **Aplikacje biznesowe**.

   ![Zrzut ekranu przedstawiający blok ustawień z opcją dotyczącą aplikacji biznesowych](../media/mam-azure-portal-lob-on-settings.png)

2. W bloku **Aplikacje biznesowe** wybierz pozycję **Dodaj aplikację niestandardową**.

   ![Zrzut ekranu przedstawiający blok aplikacji biznesowych z umieszczonym u góry przyciskiem Dodaj aplikację niestandardową](../media/mam-azure-portal-add-lob-app-action.png)
3. Określ nazwę aplikacji, identyfikator pakietu w polu identyfikatora aplikacji oraz platformę (iOS lub Android).

   ![Zrzut ekranu przedstawiający blok dodawania aplikacji niestandardowej](../media/mam-azure-portal-add-app-details.png)

   Ten krok umożliwia tworzenie unikatowej listy aplikacji. Aplikacja będzie również wyświetlana na liście aplikacji docelowych zasad zarządzania aplikacjami mobilnymi dla dzierżawy zgodnie z opisem w następnym kroku.

## <a name="step-3-apply-mam-policies"></a>Krok 3. Stosowanie zasad zarządzania aplikacjami mobilnymi
Po przekazaniu metadanych aplikacji do usługi aplikacja będzie wyświetlana na liście aplikacji. Możesz teraz [utworzyć nowe zasady lub użyć istniejących zasad](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) i zastosować je do aplikacji biznesowej dodanej w kroku 2.

>[!IMPORTANT]
>Należy wskazać zasady zarządzania aplikacjami mobilnymi dla użytkowników, którzy będą używać opakowanej aplikacji.  Użytkownicy, dla których ta zasada nie zostanie wdrożona, nie będą mogli korzystać z aplikacji.


  ![Zrzut ekranu przedstawiający blok listy aplikacji docelowych z wyświetloną nową aplikacją biznesową](../media/mam-azure-portal-lob-on-targeted-app-list.png)
## <a name="step-4-distribute-the-app"></a>Krok 4. Rozpowszechnianie aplikacji
Aplikacje można wdrażać na urządzeniach użytkowników końcowych, stosując następujące metody:
* W przypadku urządzeń zarejestrowanych w rozwiązaniu MDM innej firmy można rozpowszechniać aplikacje za pośrednictwem tego rozwiązania MDM.
* W przypadku urządzeń, które nie są zarządzane przez żadne rozwiązanie MDM, wymagane jest rozwiązanie niestandardowe. Użytkownicy końcowi muszą pobrać i zainstalować aplikację na swoich urządzeniach.

## <a name="change-the-metadata"></a>Zmiana metadanych
Jeśli istnieje konieczność zmiany szczegółów aplikacji, takich jak nazwa aplikacji lub identyfikator pakietu, należy [usunąć aplikację](#remove-apps) i [dodać ją](#step-2-add-the-app) z nowymi metadanymi.

##  <a name="remove-apps"></a>Usuwanie aplikacji
Aplikację biznesową można usunąć z listy aplikacji. Spowoduje to usunięcie aplikacji z listy i usunięcie skojarzenia z zasadami zarządzania aplikacjami mobilnymi, ale aplikacja nie zostanie usunięta ani odinstalowana z urządzenia użytkownika.  

1. W [Portalu Azure](https://portal.azure.com/) przejdź do pozycji **Zarządzanie aplikacjami mobilnymi usługi Intune** > **Ustawienia**. W bloku **Ustawienia** wybierz pozycję **Biznesowe**, aby otworzyć listę istniejących aplikacji.  
2. Wybierz aplikację, którą chcesz usunąć, i wybierz menu **kontekstowe (…)**.

   ![Zrzut ekranu przedstawiający blok aplikacji biznesowych z ikoną wielokropka](../media/mam-azure-portal-lob-context-menu.png)
3. Wybierz pozycję **Usuń aplikację**, aby usunąć aplikację.

   ![Zrzut ekranu przedstawiający blok aplikacji biznesowych z opcją usunięcia aplikacji](../media/mam-azure-portal-delete-app.png)

   Spowoduje to usunięcie aplikacji z listy aplikacji biznesowych i listy aplikacji docelowych w zasadach zarządzania aplikacjami mobilnymi.
