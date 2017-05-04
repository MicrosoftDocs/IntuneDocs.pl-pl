---
title: "Zarządzanie blokadą aktywacji systemu iOS na urządzeniach | Microsoft Docs"
description: "Usługa Microsoft Intune ułatwia zarządzanie blokadą aktywacji systemu iOS — funkcją aplikacji Znajdź mój iPhone dla urządzeń z systemem iOS 7.1 lub nowszym."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb49e926-15c4-4f01-b6eb-cee6f7ee1984
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 742fac9c401c24bfc0f2500a238c41fa00c47fd3
ms.lasthandoff: 04/24/2017


---

# <a name="help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune"></a>Ochrona urządzeń z systemem iOS przez obejście blokady aktywacji w usłudze Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Usługa Microsoft Intune ułatwia zarządzanie blokadą aktywacji systemu iOS — funkcją aplikacji Znajdź mój iPhone dla urządzeń z systemem iOS 8.0 lub nowszym. Blokada aktywacji jest włączana automatycznie w przypadku otwarcia przez użytkownika aplikacji Znajdź mój iPhone na urządzeniu. Jeśli ta funkcja została włączona, należy podać identyfikator Apple ID i hasło użytkownika, aby można było wykonać następujące czynności: 

-   Wyłączenie aplikacji Znajdź mój iPhone

-   Wymazanie urządzenia

-   Ponowne uaktywnienie urządzenia

## <a name="how-activation-lock-affects-you"></a>Wpływ blokady aktywacji na Twoje działania
Blokada aktywacji pomaga w zabezpieczaniu urządzeń z systemem iOS i zwiększa szanse na odzyskanie urządzenia w razie jego zgubienia lub kradzieży, jednak może ona powodować problemy dla administratora systemu informatycznego. Na przykład:

-   Użytkownik konfiguruje blokadę aktywacji na urządzeniu. Następnie użytkownik odchodzi z firmy i zwraca urządzenie. Bez identyfikatora Apple ID i hasła użytkownika nie ma możliwości ponownego uaktywnienia urządzenia.

-   Potrzebny jest raport ze wszystkimi urządzeniami, na których włączono blokadę aktywacji.

-   Podczas odświeżania urządzenia w organizacji chcesz ponownie przypisać niektóre urządzenia do innego działu. Możesz przypisywać ponownie tylko urządzenia, na których nie włączono blokady aktywacji.

Aby pomóc w rozwiązaniu tych problemów, firma Apple wprowadziła obejście blokady aktywacji w systemie iOS 7.1. Dzięki temu można usunąć blokadę aktywacji z nadzorowanych urządzeń bez identyfikatora Apple ID i hasła użytkownika. Nadzorowane urządzenie może wygenerować unikatowy kod obejścia blokady aktywacji, który jest przechowywany na serwerze aktywacji firmy Apple.

> [!TIP]
> Tryb nadzorowany dla urządzeń z systemem iOS umożliwia zablokowanie urządzenia za pomocą programu Apple Configurator w celu ograniczenia funkcji urządzenia do określonych celów biznesowych. Tryb nadzorowany jest przeznaczony praktycznie tylko dla urządzeń należących do firm.

Więcej informacji o blokadzie aktywacji można znaleźć [tutaj](https://support.apple.com/en-us/HT201365).

## <a name="how-intune-helps-you-manage-activation-lock"></a>Jak usługa Intune pomaga w zarządzaniu blokadą aktywacji
Usługa Intune może wysłać żądanie dotyczące stanu blokady aktywacji na nadzorowanych urządzeniach z systemem iOS 8.0 lub nowszym. Tylko w przypadku urządzeń nadzorowanych usługa Intune może pobrać kod obejścia blokady aktywacji i wystawić go bezpośrednio na urządzeniu. Jeśli zawartość urządzenia została wyczyszczona, możesz bezpośrednio uzyskać dostęp do urządzenia, używając pustej nazwy użytkownika i kodu jako hasła.

**Wiąże się to z następującymi korzyściami dla firmy**:

-   Użytkownik może korzystać z zabezpieczeń oferowanych przez aplikację Znajdź mój iPhone.

-   Możesz umożliwić użytkownikom normalną pracę, wiedząc, że w razie konieczności zmiany przeznaczenia urządzenia można je wycofać lub odblokować.

## <a name="before-you-start"></a>Przed rozpoczęciem

Aby obejść blokadę aktywacji na urządzeniach, trzeba ją najpierw włączyć. Wykonaj następujące czynności:

1. Zapoznaj się z informacjami w temacie [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies), aby utworzyć [zasady konfiguracji urządzenia](/intune/deploy-use/ios-policy-settings-in-microsoft-intune) z systemem iOS.
2. W sekcji **Rejestracja** na stronie ustawień skonfiguruj ustawienie **Zezwalaj na blokadę aktywacji, gdy urządzenie jest w trybie nadzorowanym** na wartość **Tak**.
3. Zapisz zasady, a następnie wdróż je na urządzeniach, na których chcesz zarządzać obejściem blokady aktywacji.

## <a name="how-to-use-activation-lock-bypass-from-the-intune-admin-console"></a>Jak użyć obejścia blokady aktywacji z poziomu konsoli administracyjnej usługi Intune
> [!IMPORTANT]
> Po obejściu blokady aktywacji na urządzeniu zostanie automatycznie zastosowana nowa blokada aktywacji w przypadku otwarcia aplikacji Znajdź mój iPhone. Dlatego **musisz mieć fizyczny dostęp do urządzenia, aby móc wykonać tę procedurę**.

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) kliknij pozycje **Grupy** &gt; **Wszystkie urządzenia** &gt; **Wszystkie urządzenia należące do firmy**.

2.  Wybierz urządzenie, na którym chcesz obejść blokadę aktywacji. Wybierz pozycję **Obejście blokady aktywacji**.

3.  Przeczytaj komunikat ostrzegawczy. Wybierz przycisk **Tak**, aby kontynuować.

Stan żądania odblokowania można sprawdzić na stronie szczegółów urządzenia.

## <a name="how-to-see-which-devices-are-using-activation-lock"></a>Jak sprawdzić, które urządzenia korzystają z blokady aktywacji
Aby sprawdzić, które urządzenia korzystają z blokady aktywacji, użyj jednej z dwóch metod:

-   Uruchom polecenie **Raporty ze spisu urządzeń przenośnych**. Ten raport zawiera kolumny **Stan blokady aktywacji** i **Nadzorowane**, określające stan urządzeń. Kolumna **Nadzorowane** może mieć wartość **Tak** lub **Nie**, a kolumna **Stan blokady aktywacji** może mieć następujące wartości:

    -   Włączona z kodem obejścia

    -   Włączona bez kodu obejścia (urządzenie nie jest nadzorowane)

    -   Włączona bez kodu obejścia (urządzenie jest niedostępne)

    -   Niewłączona

    Pole **Stan blokady aktywacji** jest puste w przypadku urządzeń, które nie korzystają z systemu iOS 8.0 lub nowszego.

-   Wybierz urządzenie w widoku grup. Stan blokady aktywacji jest widoczny w okienku szczegółów urządzenia.

    Wybranie urządzenia w węźle **Wszystkie urządzenia należące do firmy** spowoduje włączenie blokady aktywacji na tym urządzeniu. Zostanie również wyświetlony kod obejścia. Za jego pomocą można ręcznie obejść blokadę aktywacji.

    > [!IMPORTANT]
    >Usługa Intune pobiera spis urządzeń dla funkcji blokady aktywacji co siedem dni. W związku z tym urządzenia mogą nie być natychmiast wyświetlane ze stanem blokady aktywacji w konsoli usługi Intune.


### <a name="see-also"></a>Zobacz także
[Wycofywanie urządzeń](retire-devices-from-microsoft-intune-management.md)
[Łatwiejsza ochrona urządzeń za pomocą funkcji zdalnego blokowania i resetowania kodu dostępu](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)

