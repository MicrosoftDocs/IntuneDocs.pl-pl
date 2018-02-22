---
title: "Akcje w przypadku niezgodności z usługą Intune"
titleSuffix: Intune on Azure
description: "Informacje dotyczące tworzenia akcji w przypadku niezgodności z usługą Intune"
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 01/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 573a8b000e63576f3dd3bae1b6e8e8c47733f6bf
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2018
---
# <a name="automate-actions-for-noncompliance"></a>Automatyzacja akcji w przypadku niezgodności

**Akcje dotyczące niezgodności** umożliwiają skonfigurowanie uporządkowanej w czasie sekwencji akcji, które są stosowane do urządzeń niespełniających kryteriów zasad zgodności. Domyślnie w przypadku wykrycia urządzenia, które nie spełnia kryteriów zasad zgodności, usługa Intune natychmiast oznacza je jako niezgodne, a następnie dostęp warunkowy w usłudze Azure AD blokuje to urządzenie. **Akcje dotyczące niezgodności** zapewniają większą elastyczność w przypadku podejmowania decyzji o postępowaniu z urządzeniami niezgodnymi. Na przykład można zdecydować, aby nie blokować urządzenia natychmiast, a następnie przyznać użytkownikowi okres prolongaty, aby mógł osiągnąć zgodność.

Istnieją dwa rodzaje działań:

-   **Powiadom użytkowników końcowych za pośrednictwem poczty e-mail**: możesz dostosować powiadomienie e-mail przed wysłaniem go do użytkownika końcowego. Usługa Intune umożliwia dostosowanie adresatów, tematu oraz treści wiadomości, w tym dołączenie logo firmy oraz informacji kontaktowych.

    Ponadto usługa Intune dołącza do powiadomienia e-mail szczegółowe informacje dotyczące niezgodnych urządzeń.

-   **Oznacz urządzenie jako niezgodne**: możesz określić harmonogram z liczbą dni, po których urządzenie zostanie oznaczone jako niezgodne. Akcję można skonfigurować tak, by następowała od razu, ale można również przyznać użytkownikowi okres prolongaty przeznaczony na doprowadzenie urządzenia do stanu zgodności z zasadami.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Aby skonfigurować akcję w przypadku urządzeń niezgodnych, musisz dysponować co najmniej jedną utworzoną zasadą zgodności urządzenia. 

- Dowiedz się, jak utworzyć zasady zgodności urządzeń dla następujących platform:

    -   [Android](compliance-policy-create-android.md)
    -   [Android for Work](compliance-policy-create-android-for-work.md)
    -   [iOS](compliance-policy-create-ios.md)
    -   [macOS](compliance-policy-create-mac-os.md)
    -   [Windows](compliance-policy-create-windows.md)

Podczas planowania użycia zasad zgodności urządzenia do blokowania dostępu urządzenie do zasobów firmowych musisz mieć skonfigurowany dostęp warunkowy do usługi Azure AD. 

- Dowiedz się, [jak skonfigurować dostęp warunkowy do EMS](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access).

Ponadto musisz utworzyć szablon wiadomości z powiadomieniem. Szablon wiadomości z powiadomieniem jest używany później przy wysyłaniu wiadomości e-mail do użytkowników podczas procesu tworzenia akcji w przypadku niezgodności.

### <a name="to-create-a-notification-message-template"></a>Aby utworzyć szablon wiadomości z powiadomieniem

1. Przejdź do [usługi Intune w witrynie Azure Portal](https://portal.azure.com) i zaloguj się przy użyciu swoich poświadczeń usługi Intune.
2. W menu po lewej stronie wybierz pozycję **Więcej usług**, a następnie w filtrze pola tekstowego wpisz **Intune**.
3. Wybierz pozycję **Intune**.
4. Wybierz pozycję **Zgodność urządzeń**, a następnie wybierz pozycję **Powiadomienia** w sekcji **Zarządzanie**.
5. Wybierz pozycję **Utwórz powiadomienie**, a następnie wprowadź następujące informacje:
    - Nazwa
    - Temat
    - Wiadomość
    - Nagłówek wiadomości e-mail — dołącz logo firmy
    - Stopka wiadomości e-mail — dołącz logo firmy
    - Stopka wiadomości e-mail — dołącz informacje kontaktowe

5. Wybierz pozycję **Utwórz powiadomienie**, a następnie wprowadź następujące informacje:

    a. Nazwa

    b. Temat

    c.  Wiadomość

    d. nagłówek wiadomości e-mail — dołącz logo firmy

    e. stopka wiadomości e-mail — dołącz nazwę firmy

    f. stopka wiadomości e-mail — dołącz informacje kontaktowe

![przykładowy szablon wiadomości z powiadomieniem](./media/actionsfornoncompliance-1.PNG)

Gdy skończysz dodawać informacje, wybierz pozycję **Utwórz**. Szablon wiadomości z powiadomieniem jest gotowy do użytku.

> [!NOTE]
> Można również edytować wcześniej utworzony szablon powiadomienia.

## <a name="to-create-actions-for-noncompliance"></a>Aby utworzyć akcje w przypadku niezgodności

> [!TIP]
> Domyślnie usługa Intune udostępnia jedną akcję wstępnie zdefiniowaną w sekcji Akcje w przypadku niezgodności. Akcja ta powoduje oznaczenie urządzenia jako niezgodnego w przypadku wykrycia, że nie spełnia ono kryteriów zasad zgodności urządzeń. Możesz dostosować okres po wykryciu, po upływie którego urządzenie zostanie oznaczone jako niezgodne. Tej akcji nie można usunąć.

Akcję można dodać podczas tworzenia nowej zasady zgodności urządzeń lub edytowania istniejącej zasady zgodności urządzeń.

1.  W obciążeniu usługi Intune z poziomu bloku **Zasady zgodności urządzeń** wybierz pozycję **Zasady** w sekcji **Zarządzanie**.

2.  Zaznacz zasady zgodności urządzeń, klikając je, a następnie wybierz pozycję **Właściwości** w sekcji **Zarządzanie**.

3.  Zostanie otwarty blok **Właściwości zasady zgodności urządzeń**; wybierz opcję **Akcje dotyczące niezgodności**.

4.  Zostanie otwarty blok **Akcje w przypadku niezgodności**; wybierz w nim polecenie **Dodaj** w celu określenia parametrów akcji. Możesz wybrać wcześniej utworzony szablon wiadomości, dodatkowych adresatów oraz harmonogram okresu prolongaty. W harmonogramie możesz określić liczbę dni (od 0 do 365), a następnie możesz wymusić zasady dostępu warunkowego. Wybranie wartości **0** dni oznacza, że funkcja dostępu warunkowego musi **natychmiast** zablokować dostęp do zasobów firmy, jeśli urządzenia nie są zgodne z zasadami zgodności urządzeń.

5.  Gdy skończysz dodawać informacje, wybierz pozycję **Dodaj**, a następnie przycisk **OK**.

## <a name="next-steps"></a>Następne kroki
Możesz monitorować aktywność zgodności urządzeń, uruchamiając raporty dostępne w bloku zgodności urządzeń. Szczegółowe informacje znajdują się w temacie [Monitorowanie zgodności urządzenia w usłudze Intune](device-compliance-monitor.md).
