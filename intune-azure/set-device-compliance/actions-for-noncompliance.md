---
title: "Akcje w przypadku niezgodności"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące tworzenia zasad dla urządzeń niezgodnych"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d0e0c4b-a562-44f3-82a4-80eb688d4733
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: deea78dcea9ade031441bf12b388a862235a8e9c
ms.openlocfilehash: 16da087e741e335144266c838c0a91050bd7d520
ms.lasthandoff: 03/15/2017


---

# <a name="create-actions-for-non-compliance"></a>Tworzenie akcji w przypadku niezgodności

Opcja **Akcje dotyczące niezgodności** pozwala na skonfigurowanie uporządkowanej w czasie sekwencji akcji, które są stosowane do urządzeń pozostających w stanie niezgodności. Można na przykład powiadomić użytkowników niezgodnych urządzeń za pośrednictwem poczty e-mail lub zablokować dostęp tych urządzeń do zasobów firmowych przy użyciu dostępu warunkowego.

## <a name="use-case-scenario"></a>Scenariusz przypadków użycia

Gdy urządzenie jest raportowane jako niezgodne przez zasady zgodności urządzenia usługi Intune, funkcja dostępu warunkowego natychmiast domyślnie blokuje to urządzenie, a użytkownik otrzymuje wiadomość e-mail z instrukcjami dotyczącymi zgodności. Opcja **Akcje dotyczące niezgodności** zapewnia większą elastyczność w przypadku podejmowania decyzji o postępowaniu z urządzeniami niezgodnymi. Na przykład można zdecydować, aby nie blokować urządzenia natychmiast, a następnie przyznać użytkownikowi okres prolongaty, aby mógł osiągnąć zgodność.

Istnieją dwa rodzaje działań:

-   Powiadomienie użytkownika za pośrednictwem poczty e-mail

-   Zablokowanie dostępu do zasobów firmy przy użyciu funkcji dostępu warunkowego

## <a name="notify-the-user-via-email"></a>Powiadomienie użytkownika za pośrednictwem poczty e-mail

Można wybrać spośród domyślnych wstępnie utworzonych szablonów wiadomości e-mail lub utworzyć w pełni dostosowane powiadomienie e-mail. Firma Microsoft dostarcza dostosowanych tematów, treści wiadomości, w tym logo firmy, informacji kontaktowych i informacji o dodatkowych adresatach.

## <a name="block-corporate-resource-access-through-conditional-access"></a>Zablokowanie dostępu do zasobów firmy przy użyciu funkcji dostępu warunkowego

W harmonogramie można określić liczbę dni, w ciągu których dostęp urządzenia do zasobów firmy powinien zostać zablokowany. Może to nastąpić od razu, ale można również przyznać użytkownikowi okres prolongaty przeznaczony na doprowadzenie urządzeń do stanu zgodności z zasadami.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Aby skonfigurować akcję w przypadku urządzeń niezgodnych, musisz dysponować co najmniej jedną utworzoną zasadą zgodności urządzenia.

-   Dowiedz się, jak utworzyć zasadę zgodności urządzenia dla systemów operacyjnych:

    -   [Android](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android)

    -   [Android for Work](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android-for-work)

    -   [iOS](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-ios)

    -   [Windows](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-windows)

Podczas planowania użycia zasad zgodności urządzenia do blokowania dostępu urządzenie do zasobów firmowych musisz mieć skonfigurowany dostęp warunkowy do EMS.

- Dowiedz się, [jak skonfigurować dostęp warunkowy do EMS](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access).

Ponadto musisz utworzyć szablon wiadomości z powiadomieniem. Szablon wiadomości z powiadomieniem jest używany później przy wysyłaniu wiadomości e-mail do użytkowników podczas procesu tworzenia akcji w przypadku niezgodności.

### <a name="to-add-a-notification-message-template"></a>Aby dodać szablon wiadomości z powiadomieniem

W bloku **Zasady zgodności urządzeń**:

1.  W obszarze **Zarządzaj** wybierz opcję **Powiadomienia**, co spowoduje otwarcie bloku szablonów wiadomości z powiadomieniem.

    ![Jak dodać szablon powiadomienia](../media/afnc-1.png)

2.  Wybierz polecenie **Dodaj**, a następnie uzupełnij następujące informacje:

    a.  Opis

    b.  Z

    c.  Temat

    d.  Wiadomość

    e.  Nagłówek wiadomości e-mail — dołącz logo firmy

    f.  Stopka wiadomości e-mail — dołącz logo firmy

    g.  Stopka wiadomości e-mail — dołącz informacje kontaktowe

     ![Szablon wiadomości z powiadomieniem](../media/afnc-2.png)

Po zakończeniu dodawania informacji kliknij przycisk **Utwórz**. Szablon wiadomości z powiadomieniem jest gotowy do użytku.

> [!NOTE] 
> Można również edytować wcześniej utworzony szablon powiadomienia.

## <a name="to-create-actions-for-non-compliance"></a>Aby utworzyć akcje w przypadku niezgodności

Akcję można dodać w momencie tworzenia nowej zasady zgodności urządzeń lub też edytując istniejącą zasadę zgodności urządzeń.

1.  W bloku **Zasady zgodności urządzeń** w obszarze **Zarządzanie** wybierz opcję **Zasady**.

2.  Wybierz zasadę zgodności urządzeń, klikając ją.

    ![Zasady zgodności](../media/afnc-3.png)

3.  Zostanie otwarty blok **Właściwości zasady zgodności urządzeń**; wybierz opcję **Akcje dotyczące niezgodności**.

4.  Zostanie otwarty blok akcji dotyczących niezgodności; wybierz w nim polecenie **Dodaj** w celu określenia parametrów akcji.

    ![Akcje w przypadku niezgodności](../media/afnc-4.png)

W przypadku niezgodności dostępne są następujące akcje:

-   **Wymuszenie zasady dostępu warunkowego**

-   **Wysłanie wiadomości e-mail do użytkownika końcowego**

### <a name="enforce-conditional-access-policy"></a>Wymuszenie zasady dostępu warunkowego

Aby dodać tę akcję w przypadku braku zgodności:

1.  W bloku **Akcje dotyczące niezgodności** wybierz opcję **Dodaj**.

2.  W bloku **Parametry akcji** wybierz opcję **Wymuszanie zasady dostępu warunkowego** z listy rozwijanej Akcja.

3.  W obszarze **Harmonogram** możesz określić liczbę dni (od 0 do 255) obowiązywania zasady dostępu warunkowego. Wybranie wartości **0** dni oznacza, że funkcja dostępu warunkowego musi **natychmiast** zablokować dostęp do zasobów firmy, jeśli urządzenia nie są zgodne z zasadami zgodności urządzeń.

    ![Planowanie akcji w przypadku niezgodności](../media/afnc-5.png)

4.  Wybierz kolejno przyciski **Dodaj** i **OK** w bloku **Akcje**.

5.  W bloku **Właściwości zasady zgodności urządzeń** wybierz przycisk **Zapisz**.

### <a name="send-e-mail-to-end-user"></a>Wysyłanie wiadomości e-mail do użytkownika końcowego

Przy wysyłaniu wiadomości do użytkowników niezgodnych można użyć szablonu wiadomości e-mail. Te wiadomości e-mail pomogą w uzyskaniu zgodności urządzenia w całej organizacji.

Aby dodać tę akcję w przypadku braku zgodności:

1.  W bloku **Akcje dotyczące niezgodności** wybierz opcję **Dodaj**.

2.  W bloku **Parametry akcji** wybierz opcję **Wysyłanie wiadomości e-mail do użytkownika końcowego** z listy rozwijanej Akcja.

3.  Wybierz uprzednio utworzony szablon wiadomości, klikając opcję **Szablon wiadomości**. Po wyświetleniu zawartości szablonu wiadomości możesz nacisnąć przycisk **Wybierz**.

    ![Szablon wiadomości](../media/afnc-6.png)

> [!NOTE] 
> Szablon wiadomości można wyświetlić, ale nie można go edytować. Jeśli chcesz edytować szablon wiadomości, musisz powrócić do bloku **Powiadomienia**.

1.  W obszarze **Harmonogram** wprowadź liczbę dni od stwierdzenia niezgodności, po upłynięciu których wiadomość e-mail powinna zostać przesłana do użytkowników. W przypadku podania wartości **0** dni wiadomość e-mail zostanie wysłana **natychmiast**.

2.  Wybierz kolejno przyciski **Dodaj** i **OK** w bloku **Akcje**.

3.  W bloku **Właściwości zasady zgodności urządzeń** wybierz przycisk **Zapisz**.

