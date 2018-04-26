---
title: Aplikacje dla systemu iOS z zasadami ochrony aplikacji
titlesuffix: Microsoft Intune
description: Dowiedz się, czego oczekiwać od aplikacji systemu iOS zawierającej zasady ochrony.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 586d9440-3813-4dec-b865-8bd319befde0
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 172e99a38e3aef500fca8563079e3656e372089b
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
---
# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>Czego można oczekiwać, gdy aplikacja dla systemu iOS jest zarządzana przy użyciu zasad ochrony aplikacji

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Dowiedz się więcej o środowisku użytkownika aplikacji systemu iOS z zasadami ochrony aplikacji. Zasady ochrony aplikacji są stosowane wyłącznie podczas korzystania z aplikacji w kontekście służbowym. Na przykład w przypadku uzyskiwania dostępu do aplikacji przy użyciu konta służbowego lub w przypadku uzyskiwania dostępu do plików przechowywanych w firmowej lokalizacji w usłudze OneDrive.
##  <a name="accessing-apps"></a>Uzyskiwanie dostępu do aplikacji

Jeśli urządzenie **nie jest zarejestrowane w usłudze Intune**, użytkownik będzie musiał uruchomić ponownie aplikację po jej pierwszym uruchomieniu.  Aby do aplikacji można było zastosować zasady ochrony aplikacji, należy ponownie uruchomić urządzenie. Poniższy zrzut ekranu przedstawia tę sytuację w aplikacji Skype:


![zrzut ekranu z monitem o podanie kodu PIN na urządzeniu z systemem iOS](./media/ios-pin-prompt.png)

W przypadku urządzeń, które są **zarejestrowane w celu zarządzania w usłudze Intune**, użytkownik zobaczy komunikat, że jego aplikacja jest teraz zarządzana:

![zrzut ekranu urządzenia z systemem iOS przedstawiający komunikat dotyczący zarządzania przez firmę i monit o podanie kodu PIN](./media/ios-managed-devices-pin-prompt.png)

##  <a name="using-apps-with-multi-identity-support"></a>Korzystanie z aplikacji z obsługą wielu tożsamości

Zasady ochrony aplikacji mają zastosowanie tylko wtedy, gdy użytkownik próbuje uzyskać dostęp do danych służbowych.  Jeśli użytkownik uzyska dostęp do aplikacji w ramach użytku osobistego, można będzie zaobserwować inne zachowania. 

W przypadku aplikacji obsługujących wiele tożsamości usługa Intune stosuje zasady ochrony aplikacji tylko wtedy, gdy użytkownik uzyskuje dostęp do danych służbowych.  Na przykład może zostać wyświetlony monit o podanie kodu PIN.  W **aplikacji Outlook** monit jest wyświetlany tylko wtedy, gdy użytkownik uruchamia aplikację. W **aplikacji OneDrive** monit jest wyświetlany, gdy użytkownik wpisuje konto służbowe.  W programach Microsoft **Word**, **PowerPoint** i **Excel** monit jest wyświetlany, gdy użytkownik uzyskuje dostęp do firmowych dokumentów w usłudze OneDrive.
##  <a name="managing-user-accounts-on-the-device"></a>Zarządzanie kontami użytkowników na urządzeniu

Usługa Intune obsługuje wdrażanie zasad ochrony aplikacji na koncie tylko jednego użytkownika dla każdego urządzenia.

* W zależności od używanej aplikacji drugi użytkownik może być blokowany na urządzeniu. Jednak we wszystkich przypadkach zasady dotyczą tylko pierwszego użytkownika, który pobierze zasady ochrony aplikacji.
  * Programy **Microsoft Word**, **Excel** i **PowerPoint** nie będą blokować dostępu do dodatkowego konta użytkownika. Zasady ochrony aplikacji nie będą mieć jednak wpływu na konto użytkownika.

  * W przypadku **aplikacji OneDrive i Outlook** możesz używać tylko jednego konta służbowego.  Dodawanie większej liczby kont służbowych w tych aplikacjach jest zablokowane.  Jednak możesz usunąć użytkownika z urządzenia, a następnie dodać innego użytkownika do urządzenia.

* Urządzenie może mieć różne istniejące konta użytkowników przed wdrożeniem zasad ochrony aplikacji. W takim przypadku pierwsze konto, na którym zostaną wdrożone zasady ochrony aplikacji, będzie zarządzane przez zasady ochrony aplikacji usługi Intune.


Przeczytaj poniższy przykładowy scenariusz, aby dowiedzieć się, jak usługa Intune obsługuje wiele kont użytkowników.

Użytkownik A pracuje dla dwóch firm: **Firmy X** i **Firmy Y**. Użytkownik A ma konto służbowe dla każdej firmy, a obaj użytkownicy wdrażają zasady ochrony aplikacji za pomocą usługi Intune. **Firma X** wdraża zasady ochrony aplikacji **przed** **Firmą Y**. Zasady ochrony aplikacji zostaną zastosowane na koncie skojarzonym z **Firmą X**, ale nie na koncie skojarzonym z Firmą Y. Aby konto użytkownika skojarzone z Firmą Y było zarządzane przez zasady ochrony aplikacji, użytkownik A musi usunąć konto użytkownika skojarzone z Firmą X.
### <a name="adding-a-second-account"></a>Dodawanie drugiego konta

Jeśli korzystasz z urządzenia z systemem iOS, podczas próby dodania drugiego konta służbowego na tym samym urządzeniu może zostać wyświetlony komunikat o blokadzie.  Konta zostaną wyświetlone, umożliwiając wybranie konta do usunięcia.

![Zrzut ekranu okna dialogowego z komunikatem o blokadzie i opcjami Tak i Nie](./media/ios-switch-user.PNG)

## <a name="next-steps"></a>Następne kroki
[Czego można oczekiwać, gdy aplikacja systemu Android jest zarządzana przy użyciu zasad ochrony aplikacji](app-protection-enabled-apps-android.md)
### <a name="see-also"></a>Zobacz też
[Tworzenie i wdrażanie zasad ochrony aplikacji przy użyciu usługi Microsoft Intune](app-protection-policies.md)
