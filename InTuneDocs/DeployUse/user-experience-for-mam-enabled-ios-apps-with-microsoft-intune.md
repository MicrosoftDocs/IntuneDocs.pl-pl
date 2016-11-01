---
title: Aplikacje dla systemu iOS z zasadami MAM | Microsoft Intune
description: "W tym temacie opisano to, czego można oczekiwać, gdy aplikacja dla systemu iOS jest zarządzana przy użyciu zasad zarządzania aplikacjami mobilnymi."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 389daf0ed39fa2cd4b2e5d6e52cbd6809a568c9e
ms.openlocfilehash: 3f9d9c7cafcdac0db21e5ba35f713fe630c65b99


---

# Oczekiwany przebieg zarządzania aplikacją systemu iOS przez zasady zarządzania aplikacjami mobilnymi
 W tym temacie opisano środowisko użytkownika aplikacji z zasadami MAM. Zasady zarządzania aplikacjami mobilnymi (MAM, mobile application management) są stosowane tylko wtedy, gdy aplikacje są używane służbowo, czyli na przykład podczas korzystania z aplikacji przy użyciu konta służbowego lub uzyskiwania dostępu do plików przechowywanych w lokalizacji służbowej w usłudze OneDrive.
##  Uzyskiwanie dostępu do aplikacji

Jeśli urządzenie **nie jest zarejestrowane w usłudze Intune**, użytkownik końcowy będzie musiał uruchomić ponownie aplikację po jej pierwszym uruchomieniu.  Ponowne uruchomienie jest wymagane, aby do aplikacji można było zastosować zasady MAM. Poniższy zrzut ekranu przedstawia tę sytuację w aplikacji Skype:


![zrzut ekranu z monitem o podanie kodu PIN na urządzeniu z systemem iOS](../media/appmanagement/iOS_AppPINPrompt.png)

W przypadku urządzeń, które są **zarejestrowane w celu zarządzania w usłudze Intune**, użytkownik końcowy zobaczy komunikat, że jego aplikacja jest teraz zarządzana:

![zrzut ekranu urządzenia z systemem iOS przedstawiający komunikat dotyczący zarządzania przez firmę i monit o podanie kodu PIN](../media/appmanagement/ios-managed-devices-pin-prompt.png)

##  Korzystanie z aplikacji z obsługą wielu tożsamości

Zasady MAM są stosowane tylko podczas służbowego używania aplikacji, więc w zależności od trybu działania (służbowego lub osobistego) aplikacja może zachowywać się różnie.  

W przypadku aplikacji, które obsługują wiele tożsamości, usługa Intune stosuje zasady MAM tylko, jeśli użytkownik korzysta z aplikacji służbowo.  Na przykład podczas uzyskiwania dostępu do danych służbowych użytkownik zobaczy monit o podanie kodu PIN.  W przypadku **aplikacji Outlook** użytkownik końcowy musi podać kod PIN podczas uruchamiania aplikacji. W przypadku **aplikacji OneDrive** trzeba to zrobić po wybraniu konta służbowego.  W przypadku aplikacji Microsoft **Word**, **PowerPoint* i **Excel** kod PIN trzeba podać w celu uzyskania dostępu do dokumentów przechowywanych w lokalizacji firmowej w usłudze OneDrive dla Firm.
##  Zarządzanie kontami użytkowników na urządzeniu

Usługa Intune obsługuje wdrażanie zasad MAM na koncie tylko jednego użytkownika dla każdego urządzenia.

* W zależności od używanej aplikacji drugi użytkownik może być blokowany na urządzeniu. Jednak we wszystkich przypadkach zasady dotyczą tylko pierwszego użytkownika, który pobierze zasady MAM.
  * Programy **Microsoft Word**, **Excel** i **PowerPoint** nie blokują drugiego konta użytkownika, ale zasady MAM nie są stosowane do tego konta.  

  * W przypadku **aplikacji OneDrive i Outlook** możesz używać tylko jednego konta służbowego.  Dodawanie większej liczby kont służbowych w tych aplikacjach jest zablokowane.  Możesz natomiast usunąć użytkownika na urządzeniu i dodać innego użytkownika.

* Jeśli urządzenie ma wiele istniejących kont użytkowników przed wdrożeniem zasad MAM, pierwsze konto, na którym wdrożono zasady MAM, jest zarządzane przez zasady MAM usługi Intune.


Zapoznaj się z przykładowym scenariuszem poniżej, aby lepiej zrozumieć zasady traktowania wielu kont użytkowników.

Użytkownik A pracuje dla dwóch firm — **Firmy X** i **Firmy Y**. Użytkownik A ma konto służbowe dla każdej firmy, a obaj użytkownicy wdrażają zasady MAM za pomocą usługi Intune. **Firma X** wdraża zasady zarządzania aplikacjami mobilnymi **przed** **Firmą Y**. Zasady MAM zostaną zastosowane na koncie skojarzonym z **Firmą X**, ale nie na koncie skojarzonym z Firmą Y. Jeśli chcesz, aby konto użytkownika skojarzone z Firmą Y było zarządzane przez zasady MAM, musisz usunąć konto użytkownika skojarzone z Firmą X.
### Dodawanie drugiego konta

Jeśli korzystasz z urządzenia z systemem iOS, podczas próby dodania drugiego konta służbowego na tym samym urządzeniu może zostać wyświetlony komunikat o blokadzie.  Konta zostaną wyświetlone, umożliwiając wybranie konta do usunięcia.

![Zrzut ekranu okna dialogowego z komunikatem o blokadzie i opcjami Tak i Nie](../media/AppManagement/iOS_SwitchUser.PNG)
## Następne kroki
[Oczekiwany przebieg zarządzania aplikacją systemu Android przez zasady zarządzania aplikacjami mobilnymi](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
### Zobacz także
[Tworzenie i wdrażanie zasad zarządzania aplikacjami mobilnymi przy użyciu usługi Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


