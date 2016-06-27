---
# required metadata

title: Chronienie aplikacji biznesowych i danych na niezarejestrowanych urządzeniach | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 00219467-a62e-43b6-954b-3084f54c45ba

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: joglocke
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Chronienie aplikacji biznesowych i danych na niezarejestrowanych urządzeniach w usłudze Microsoft Intune

Zasady zarządzania aplikacjami mobilnymi (MAM) chronią dane firmy, ograniczając przenoszenie danych (na przykład kopiowanie i wklejanie) lub uniemożliwiając użytkownikom zapisywanie dokumentów firmy w lokalizacji prywatnej.   Aby zastosować zasady zarządzania aplikacjami mobilnymi do aplikacji biznesowych systemu iOS lub Android, należy najpierw opakować aplikację przy użyciu narzędzia opakowującego aplikacje dostępnego w usłudze Microsoft Intune.  Opakowywanie aplikacji jest procesem stosowania warstwy zarządzania do aplikacji mobilnej bez konieczności wprowadzania zmian w aplikacji.  Po opakowaniu aplikacji można stosować do niej zasady zarządzania aplikacjami mobilnymi i rozpowszechniać ją wśród użytkowników końcowych.  

W tym temacie objaśniono czynności wymagane do stosowania zasad zarządzania aplikacjami mobilnymi dla aplikacji używanych na **niezarządzanych urządzeniach należących do pracowników** i urządzeniach zarządzanych przez **rozwiązanie do zarządzania urządzeniami przenośnymi (MDM) oferowane przez inną firmę**.  Aby przygotować aplikacje biznesowe uruchamiane na **urządzeniach zarejestrowanych w usłudze Intune**, zobacz [Wybieranie sposobu przygotowania aplikacji do zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).
##  Krok 1. Przygotowywanie aplikacji
Aby można było zastosować zasady zarządzania aplikacjami mobilnymi do aplikacji, należy najpierw opakować aplikację przy użyciu narzędzia opakowującego aplikacje dostępnego w usłudze Microsoft Intune.  Plik do pobrania zawiera instrukcje dotyczące instalowania i używania narzędzia opakowującego aplikacje.  
>[!IMPORTANT]  
>Ta wersja narzędzia opakowującego aplikacje, obsługująca urządzenia niezarejestrowane w usłudze Intune, zostanie udostępniona w prywatnej wersji zapoznawczej w najbliższych tygodniach. Jeśli chcesz uczestniczyć w tym programie, wyślij wiadomość na adres msintuneappsdk@microsoft.com w celu uzyskania dodatkowych informacji.

## Krok 2. Dodawanie aplikacji

Aby skojarzyć aplikację biznesową z zasadami zarządzania aplikacjami mobilnymi, należy dodać szczegóły aplikacji do subskrypcji/dzierżawy usługi Intune, wykonując poniższe czynności:

1. W [portalu Azure](https://portal.azure.com/) przejdź do pozycji **Zarządzanie aplikacjami mobilnymi usługi Intune > Ustawienia** i wybierz pozycję **Aplikacje biznesowe**.

  ![Zrzut ekranu przedstawiający blok ustawień z opcją dotyczącą aplikacji biznesowych](../media/mam-azure-portal-lob-on-settings.png)

2. W bloku **Aplikacje biznesowe** wybierz pozycję **Dodaj aplikację niestandardową**.

  ![Zrzut ekranu przedstawiający blok aplikacji biznesowych z umieszczonym u góry przyciskiem Dodaj aplikację niestandardową](../media/mam-azure-portal-add-lob-app-action.png)
3.  Określ nazwę aplikacji, identyfikator pakietu w polu identyfikatora aplikacji oraz platformę (iOS lub Android).

  ![Zrzut ekranu przedstawiający blok dodawania aplikacji niestandardowej ](../media/mam-azure-portal-add-app-details.png) Ten krok ułatwia utworzenie unikatowego wpisu dotyczącego aplikacji.  Aplikacja będzie również wyświetlana na liście aplikacji docelowych dla zasad zarządzania aplikacjami mobilnymi dla dzierżawy zgodnie z opisem w następnym kroku.

## Krok 3. Stosowanie zasad zarządzania aplikacjami mobilnymi
Po przekazaniu metadanych aplikacji do usługi aplikacja będzie wyświetlana na liście aplikacji.  Możesz teraz [utworzyć nowe zasady lub użyć istniejących zasad](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) i zastosować je do aplikacji biznesowej dodanej w kroku 2.

>[!IMPORTANT]
>Należy wskazać zasady zarządzania aplikacjami mobilnymi dla użytkowników, którzy będą używać opakowanej aplikacji.  Użytkownicy, dla których ta zasada nie zostanie wdrożona, nie będą mogli korzystać z aplikacji.


  ![Zrzut ekranu przedstawiający blok listy aplikacji docelowych z wyświetloną nową aplikacją biznesową](../media/mam-azure-portal-lob-on-targeted-app-list.png)
## Krok 4. Rozpowszechnianie aplikacji
Aplikacje można wdrażać na urządzeniach użytkowników końcowych, stosując następujące metody:
* W przypadku urządzeń zarejestrowanych w rozwiązaniu MDM innej firmy można rozpowszechniać aplikacje za pośrednictwem tego rozwiązania MDM.
* W przypadku urządzeń, które nie są zarządzane przez rozwiązanie MDM, wymagane jest rozwiązanie niestandardowe. Użytkownicy końcowi muszą pobrać i zainstalować aplikację na swoich urządzeniach.

## Zmienianie metadanych
Aby zmienić szczegóły aplikacji, takie jak nazwa aplikacji lub identyfikator pakietu, należy [usunąć aplikację](#remove-apps) i [dodać ją](#add-the-app) z nowymi metadanymi.

##  Usuwanie aplikacji
Aplikację biznesową można usunąć z listy aplikacji.  Spowoduje to usunięcie aplikacji z listy i usunięcie skojarzenia z zasadami zarządzania aplikacjami mobilnymi, ale aplikacja nie zostanie usunięta ani odinstalowana z urządzenia użytkownika końcowego.  

1.  W [portalu Azure](https://portal.azure.com/) przejdź do pozycji **Zarządzanie aplikacjami mobilnymi usługi Intune > Ustawienia**.  W bloku **Ustawienia** wybierz pozycję **Biznesowe**, aby otworzyć listę istniejących aplikacji.  
2.  Wybierz aplikację, którą chcesz usunąć, i wybierz menu kontekstowe **(…)**.

  ![Zrzut ekranu przedstawiający blok aplikacji biznesowych z ikoną wielokropka](../media/mam-azure-portal-lob-context-menu.png)
3.  Wybierz pozycję **Usuń aplikację**, aby usunąć aplikację.

  ![Zrzut ekranu przedstawiający blok aplikacji biznesowych z opcją usunięcia aplikacji](../media/mam-azure-portal-delete-app.png)

  Spowoduje to usunięcie aplikacji z listy aplikacji biznesowych i listy aplikacji docelowych w zasadach zarządzania aplikacjami mobilnymi.


<!--HONumber=Jun16_HO2-->

