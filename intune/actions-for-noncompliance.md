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
ms.assetid: 6d0e0c4b-a562-44f3-82a4-80eb688d4733
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4e45f5d3836fc33851c650703f713c03204df792
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="automate-actions-for-noncompliance"></a>Automatyzacja akcji w przypadku niezgodności

**Akcje dotyczące niezgodności** umożliwiają skonfigurowanie uporządkowanej w czasie sekwencji akcji, które są stosowane do urządzeń niespełniających kryteriów zasad zgodności. Domyślnie w przypadku wykrycia urządzenia, które nie spełnia kryteriów zasad zgodności, usługa Intune natychmiast oznacza je jako niezgodne, a następnie dostęp warunkowy w usłudze Azure AD blokuje to urządzenie. **Akcje dotyczące niezgodności** zapewniają większą elastyczność w przypadku podejmowania decyzji o postępowaniu z urządzeniami niezgodnymi. Na przykład można zdecydować, aby nie blokować urządzenia natychmiast, a następnie przyznać użytkownikowi okres prolongaty, aby mógł osiągnąć zgodność.

Istnieją dwa rodzaje działań:

-   **Powiadom użytkowników końcowych za pośrednictwem poczty e-mail**: możesz dostosować powiadomienie e-mail przed wysłaniem go do użytkownika końcowego. Usługa Intune umożliwia dostosowanie adresatów, tematu oraz treści wiadomości, w tym dołączenie logo firmy oraz informacji kontaktowych.
-   **Oznacz urządzenie jako niezgodne**: możesz określić harmonogram z liczbą dni, po których urządzenie zostanie oznaczone jako niezgodne. Akcję można skonfigurować tak, by następowała od razu, ale można również przyznać użytkownikowi okres prolongaty przeznaczony na doprowadzenie urządzenia do stanu zgodności z zasadami.

## <a name="before-you-begin"></a>Przed rozpoczęciem

- Aby skonfigurować akcję w przypadku urządzeń niezgodnych, musisz dysponować co najmniej jedną utworzoną zasadą zgodności urządzenia. Dowiedz się, jak utworzyć zasady zgodności urządzeń dla następujących platform:

    -   [Android](compliance-policy-create-android.md)
    -   [Android for Work](compliance-policy-create-android-for-work.md)
    -   [iOS](compliance-policy-create-ios.md)
    -   [macOS](compliance-policy-create-mac-os.md)
    -   [Windows](compliance-policy-create-windows.md)

- Podczas planowania użycia zasad zgodności urządzenia do blokowania dostępu urządzenie do zasobów firmowych musisz mieć skonfigurowany dostęp warunkowy do usługi Azure AD. Dowiedz się, [jak skonfigurować dostęp warunkowy do EMS](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access).

- Musisz utworzyć szablon wiadomości z powiadomieniem. Szablon wiadomości z powiadomieniem jest używany później przy wysyłaniu wiadomości e-mail do użytkowników podczas procesu tworzenia akcji w przypadku niezgodności.

- Należy skonfigurować usługę Exchange Online do akceptowania wiadomości e-mail z  *IntuneNotificationService@microsoft.com* , aby umożliwić usłudze Intune wysłanie powiadomienia e-mail. Szczegółowe informacje znajdują się w artykule [Configure message delivery restrictions for a mailbox](https://technet.microsoft.com/library/bb397214(v=exchg.160).aspx) (Konfigurowanie ograniczeń dostarczania wiadomości dla skrzynki pocztowej).

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

   ![przykładowy szablon wiadomości z powiadomieniem](./media/actionsfornoncompliance-1.PNG)

Gdy skończysz dodawać informacje, wybierz pozycję **Utwórz**. Szablon wiadomości z powiadomieniem jest gotowy do użytku.

> [!NOTE] 
> Można również edytować wcześniej utworzony szablon powiadomienia.

## <a name="to-create-actions-for-non-compliance"></a>Aby utworzyć akcje w przypadku niezgodności

> [!TIP]
> Domyślnie usługa Intune udostępnia jedną akcję wstępnie zdefiniowaną w sekcji Akcje w przypadku niezgodności. Akcja ta powoduje oznaczenie urządzenia jako niezgodnego w przypadku wykrycia, że nie spełnia ono kryteriów zasad zgodności urządzeń. Możesz dostosować okres po wykryciu, po upływie którego urządzenie zostanie oznaczone jako niezgodne. Tej akcji nie można usunąć.

Akcję można dodać podczas tworzenia nowej zasady zgodności urządzeń lub edytowania istniejącej zasady zgodności urządzeń.

1.  W obciążeniu usługi Intune z poziomu bloku **Zasady zgodności urządzeń** wybierz pozycję **Zasady** w sekcji **Zarządzanie**.
2.  Zaznacz zasady zgodności urządzeń, klikając je, a następnie wybierz pozycję **Właściwości** w sekcji **Zarządzanie**.
3.  W bloku **właściwości zasad zgodności urządzeń** wybierz opcję **Akcje w przypadku niezgodności**.
4.  W bloku **Akcje w przypadku niezgodności** wybierz przycisk **Dodaj** w celu określenia parametrów akcji. Możesz wybrać wcześniej utworzony szablon wiadomości, dodatkowych adresatów oraz harmonogram okresu prolongaty. W harmonogramie możesz określić liczbę dni (od 0 do 365), a następnie możesz wymusić zasady dostępu warunkowego. W przypadku wybrania dla liczby dni wartości **0** funkcja dostępu warunkowego **natychmiast** blokuje dostęp do zasobów firmy, jeśli urządzenia są niezgodne z zasadami zgodności urządzeń.
5.  Gdy skończysz dodawać informacje, wybierz pozycję **Dodaj**, a następnie przycisk **OK**.

## <a name="next-steps"></a>Następne kroki
Możesz monitorować aktywność zgodności urządzeń, uruchamiając raporty dostępne w bloku zgodności urządzeń. Szczegółowe informacje znajdują się w temacie [Monitorowanie zgodności urządzenia w usłudze Intune](device-compliance-monitor.md).

