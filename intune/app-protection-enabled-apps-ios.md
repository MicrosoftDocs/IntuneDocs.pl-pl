---
title: "Aplikacje dla systemu iOS z zasadami ochrony aplikacji | Wersja zapoznawcza usługi Intune Azure"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: w tym temacie opisano, czego można oczekiwać, gdy aplikacja dla systemu iOS jest zarządzana przy użyciu zasad ochrony aplikacji."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 586d9440-3813-4dec-b865-8bd319befde0
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 5e172b940dfae32213c870b29f05f56573192704
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>Czego można oczekiwać, gdy aplikacja dla systemu iOS jest zarządzana przy użyciu zasad ochrony aplikacji
[!INCLUDE[azure_preview](./includes/azure_preview.md)]W tym temacie opisano środowisko użytkownika aplikacji z zasadami ochrony aplikacji. Zasady ochrony aplikacji są stosowane tylko wtedy, gdy aplikacje są używane służbowo, czyli na przykład podczas korzystania z aplikacji przy użyciu konta służbowego lub uzyskiwania dostępu do plików przechowywanych w lokalizacji służbowej w usłudze OneDrive.
##  <a name="accessing-apps"></a>Uzyskiwanie dostępu do aplikacji

Jeśli urządzenie **nie jest zarejestrowane w usłudze Intune**, użytkownik końcowy będzie musiał uruchomić ponownie aplikację po jej pierwszym uruchomieniu.  Aby do aplikacji można było zastosować zasady ochrony aplikacji, należy ponownie uruchomić urządzenie. Poniższy zrzut ekranu przedstawia tę sytuację w aplikacji Skype:


![zrzut ekranu z monitem o podanie kodu PIN na urządzeniu z systemem iOS](./media/ios-pin-prompt.png)

W przypadku urządzeń, które są **zarejestrowane w celu zarządzania w usłudze Intune**, użytkownik końcowy zobaczy komunikat, że jego aplikacja jest teraz zarządzana:

![zrzut ekranu urządzenia z systemem iOS przedstawiający komunikat dotyczący zarządzania przez firmę i monit o podanie kodu PIN](./media/ios-managed-devices-pin-prompt.png)

##  <a name="using-apps-with-multi-identity-support"></a>Korzystanie z aplikacji z obsługą wielu tożsamości

Zasady ochrony aplikacji są stosowane tylko podczas służbowego używania aplikacji, więc w zależności od trybu działania (służbowego lub osobistego) aplikacja może zachowywać się różnie.  

W przypadku aplikacji, które obsługują wiele tożsamości, usługa Intune stosuje zasady ochrony aplikacji tylko, jeśli użytkownik korzysta z aplikacji służbowo.  Na przykład podczas uzyskiwania dostępu do danych służbowych użytkownik zobaczy monit o podanie kodu PIN.  W przypadku **aplikacji Outlook** użytkownik końcowy musi podać kod PIN podczas uruchamiania aplikacji. W przypadku **aplikacji OneDrive** trzeba to zrobić po wybraniu konta służbowego.  W przypadku aplikacji Microsoft **Word**, **PowerPoint* i **Excel** kod PIN trzeba podać w celu uzyskania dostępu do dokumentów przechowywanych w lokalizacji firmowej w usłudze OneDrive dla Firm.
##  <a name="managing-user-accounts-on-the-device"></a>Zarządzanie kontami użytkowników na urządzeniu

Usługa Intune obsługuje wdrażanie zasad ochrony aplikacji na koncie tylko jednego użytkownika dla każdego urządzenia.

* W zależności od używanej aplikacji drugi użytkownik może być blokowany na urządzeniu. Jednak we wszystkich przypadkach zasady dotyczą tylko pierwszego użytkownika, który pobierze zasady ochrony aplikacji.
  * Programy **Microsoft Word**, **Excel** i **PowerPoint** nie blokują drugiego konta użytkownika, ale zasady ochrony aplikacji nie są stosowane do tego konta.  

  * W przypadku **aplikacji OneDrive i Outlook** możesz używać tylko jednego konta służbowego.  Dodawanie większej liczby kont służbowych w tych aplikacjach jest zablokowane.  Możesz natomiast usunąć użytkownika na urządzeniu i dodać innego użytkownika.

* Jeśli urządzenie ma wiele istniejących kont użytkowników przed wdrożeniem zasad ochrony aplikacji, pierwsze konto, na którym wdrożono zasady ochrony aplikacji, jest zarządzane przez zasady ochrony aplikacji usługi Intune.


Zapoznaj się z przykładowym scenariuszem poniżej, aby lepiej zrozumieć zasady traktowania wielu kont użytkowników.

Użytkownik A pracuje dla dwóch firm — **Firmy X** i **Firmy Y**. Użytkownik A ma konto służbowe dla każdej firmy, a obaj użytkownicy wdrażają zasady ochrony aplikacji za pomocą usługi Intune. **Firma X** wdraża zasady ochrony aplikacji **przed** **Firmą Y**. Zasady ochrony aplikacji zostaną zastosowane na koncie skojarzonym z **Firmą X**, ale nie na koncie skojarzonym z Firmą Y. Jeśli chcesz, aby konto użytkownika skojarzone z Firmą Y było zarządzane przez zasady ochrony aplikacji, musisz usunąć konto użytkownika skojarzone z Firmą X.
### <a name="adding-a-second-account"></a>Dodawanie drugiego konta

Jeśli korzystasz z urządzenia z systemem iOS, podczas próby dodania drugiego konta służbowego na tym samym urządzeniu może zostać wyświetlony komunikat o blokadzie.  Konta zostaną wyświetlone, umożliwiając wybranie konta do usunięcia.

![Zrzut ekranu okna dialogowego z komunikatem o blokadzie i opcjami Tak i Nie](./media/ios-switch-user.PNG)

## <a name="next-steps"></a>Następne kroki
[Czego można oczekiwać, gdy aplikacja dla systemu Android jest zarządzana przy użyciu zasad ochrony aplikacji](app-protection-enabled-apps-android.md)
### <a name="see-also"></a>Zobacz także
[Tworzenie i wdrażanie zasad ochrony aplikacji przy użyciu usługi Microsoft Intune](app-protection-policies.md)

