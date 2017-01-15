---
title: Aplikacje dla systemu iOS z zasadami MAM | Microsoft Docs
description: "W tym temacie opisano to, czego można oczekiwać, gdy aplikacja dla systemu iOS jest zarządzana przy użyciu zasad zarządzania aplikacjami mobilnymi."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b068da7685792757825a4bc0d555e28ee0168cb1
ms.openlocfilehash: f5a26d3d5ed060571892d91637dc12cae08f1a69


---

# <a name="what-to-expect-when-your-ios-app-is-managed-by-mam-policies"></a>Oczekiwany przebieg zarządzania aplikacją systemu iOS przez zasady zarządzania aplikacjami mobilnymi

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

 W tym temacie opisano środowisko użytkownika aplikacji z zasadami zarządzania aplikacjami mobilnymi (MAM). Zasady MAM są stosowane tylko wtedy, gdy aplikacje są używane do celów służbowych, czyli na przykład podczas korzystania z aplikacji przy użyciu konta służbowego lub uzyskiwania dostępu do plików przechowywanych w lokalizacji firmowej w usłudze OneDrive.

##  <a name="access-apps"></a>Dostęp do aplikacji

Jeśli urządzenie **nie jest zarejestrowane w usłudze Intune**, użytkownik zostanie poproszony o ponowne uruchomienie aplikacji przy jej pierwszym użyciu.  Ponowne uruchomienie jest wymagane, aby do aplikacji można było zastosować zasady MAM. 

<!--- The following screenshot from the Skype app illustrates this restart request: --->


<!---  ![Screenshot of the iOS device showing PIN prompt](../media/appmanagement/iOS_AppPINPrompt.png) --->

Na urządzeniach, które są **zarejestrowane do celów zarządzania w usłudze Intune**, użytkownik zobaczy komunikat, że jego aplikacja jest teraz zarządzana:

![Zrzut ekranu urządzenia z systemem iOS przedstawiający komunikat, że aplikacja jest teraz zarządzana przez firmę, oraz monit o podanie numeru PIN](../media/appmanagement/ios-managed-devices-pin-prompt.png)

##  <a name="use-apps-with-multi-identity-support"></a>Korzystanie z aplikacji z obsługą wielu tożsamości

Zasady MAM są stosowane tylko w kontekście służbowym. W związku z tym aplikacja może zachowywać się inaczej w zależności od tego, czy jest używana w kontekście służbowym czy osobistym.

 Na przykład podczas uzyskiwania dostępu do danych służbowych użytkownik zobaczy monit o podanie numeru PIN. W przypadku **aplikacji Outlook** użytkownik musi podać numer PIN podczas uruchamiania aplikacji. Korzystając z **aplikacji OneDrive**, użytkownik jest monitowany o numer PIN przy podawaniu konta służbowego.  W przypadku aplikacji Microsoft **Word**, **PowerPoint** i **Excel** numer PIN trzeba podać w celu uzyskania dostępu do dokumentów przechowywanych w lokalizacji firmowej w usłudze OneDrive dla Firm.

##  <a name="manage-user-accounts-on-the-device"></a>Zarządzanie kontami użytkowników na urządzeniu

Usługa Intune obsługuje wdrażanie zasad MAM tylko na jednym koncie użytkownika dla każdego urządzenia.

* W zależności od używanej aplikacji drugi użytkownik może być blokowany na urządzeniu. Jednak we wszystkich przypadkach zasady dotyczą tylko pierwszego użytkownika, który pobierze zasady MAM.
  * Programy **Microsoft Word**, **Excel** i **PowerPoint** nie blokują drugiego konta użytkownika, ale zasady MAM nie są stosowane do tego konta.  

  * W przypadku aplikacji **OneDrive** i **Outlook** można używać tylko jednego konta służbowego. Nie możesz dodawać wielu kont służbowych dla tych aplikacji. Możesz natomiast usunąć użytkownika na urządzeniu i dodać innego użytkownika.

* Jeśli urządzenie ma wiele istniejących kont użytkowników przed wdrożeniem zasad MAM, pierwsze konto, na którym wdrożono zasady MAM, jest zarządzane według zasad MAM usługi Intune.


Zapoznaj się z przykładowym scenariuszem poniżej, aby lepiej zrozumieć zasady obsługi wielu kont użytkowników.

Użytkownik A pracuje dla dwóch firm — **Firmy X** i **Firmy Y**. Użytkownik A ma konto służbowe dla każdej firmy, a obaj użytkownicy wdrażają zasady MAM za pomocą usługi Intune. **Firma X** wdraża zasady zarządzania aplikacjami mobilnymi **przed** **Firmą Y**. Zasady MAM zostaną zastosowane na koncie skojarzonym z **Firmą X**, ale nie na koncie skojarzonym z Firmą Y. Jeśli chcesz, aby konto użytkownika skojarzone z Firmą Y było zarządzane według zasad MAM, musisz usunąć konto użytkownika skojarzone z Firmą X.

### <a name="add-a-second-account"></a>Dodawanie drugiego konta

Jeśli korzystasz z urządzenia z systemem iOS, podczas próby dodania drugiego konta służbowego na tym urządzeniu może zostać wyświetlony komunikat o blokadzie. Konta zostaną wyświetlone, umożliwiając wybranie konta do usunięcia.

![Zrzut ekranu okna dialogowego z komunikatem o blokadzie i opcjami Tak i Nie](../media/AppManagement/iOS_SwitchUser.PNG)
## <a name="next-steps"></a>Następne kroki
[Oczekiwany przebieg zarządzania aplikacją systemu Android przez zasady zarządzania aplikacjami mobilnymi](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
### <a name="see-also"></a>Zobacz także
[Tworzenie i wdrażanie zasad zarządzania aplikacjami mobilnymi przy użyciu usługi Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO3-->


