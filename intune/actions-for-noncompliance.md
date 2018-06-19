---
title: Komunikaty i akcje dotyczące braku zgodności w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Utwórz wiadomość e-mail z powiadomieniem, która zostanie wysłana do niezgodnych urządzeń. Dodaj akcje do wykonania po oznaczeniu urządzenia jako niezgodne, takie jak dodanie okresu prolongaty na zapewnienie zgodności lub utworzenie harmonogram w celu zablokowania dostępu, dopóki urządzenie nie będzie zgodne. Zrób to za pomocą usługi Microsoft Intune na platformie Azure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8e8603ca59b46937b1529e710a8bc83aec5dd4d6
ms.sourcegitcommit: 4c18352d5b3b30080f7c7257fa63d852b1894850
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2018
ms.locfileid: "32017961"
---
# <a name="automate-email-and-add-actions-for-noncompliant-devices---intune"></a>Automatyzowanie poczty e-mail i dodawanie akcji dla niezgodnych urządzeń — Intune

Dostępna jest funkcja **Akcje w przypadku braku zgodności**, za pomocą której można skonfigurować uporządkowaną w czasie sekwencję akcji. Te akcje dotyczą urządzeń, które nie są zgodne z zasadami zgodności. 

## <a name="overview"></a>Przegląd
Domyślnie po wykryciu przez usługę Intune urządzenia, które nie jest zgodne, usługa Intune natychmiast oznacza to urządzenie jako niezgodne. [Dostęp warunkowy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) usługi Azure Active Directory (AD) blokuje wtedy dane urządzenie. **Akcje dotyczące niezgodności** zapewniają także elastyczność w przypadku podejmowania decyzji o postępowaniu z urządzeniami niezgodnymi. Możesz na przykład zdecydować, aby nie blokować urządzenia natychmiast i przyznać użytkownikowi okres prolongaty, aby mógł zapewnić zgodność.

Istnieją dwa rodzaje działań:

- **Powiadom użytkowników końcowych za pośrednictwem poczty e-mail**: dostosuj powiadomienie e-mail przed wysłaniem go do użytkownika końcowego. Możesz dostosować adresatów, temat oraz treść wiadomości, w tym logo firmy oraz informacje kontaktowe.

    Ponadto usługa Intune dołącza do powiadomienia e-mail szczegółowe informacje dotyczące niezgodnych urządzeń.

- **Oznacz urządzenie jako niezgodne**: utwórz harmonogram z liczbą dni, po których urządzenie zostanie oznaczone jako niezgodne. Akcję można skonfigurować tak, by następowała od razu, ale można również przyznać użytkownikowi okres prolongaty.

## <a name="before-you-begin"></a>Przed rozpoczęciem

- Aby skonfigurować akcje w przypadku niezgodności, musisz mieć co najmniej jedną zasadę zgodności urządzeń. Aby utworzyć zasady zgodności urządzeń, zapoznaj się z następującymi platformami:

  - [Android](compliance-policy-create-android.md)
  - [Android for Work](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows](compliance-policy-create-windows.md)

- W przypadku blokowania urządzeniom dostępu do zasobów firmowych przy użyciu zasad zgodności urządzeń musisz mieć skonfigurowany dostęp warunkowy usługi Azure AD. Aby uzyskać wskazówki, zobacz [Dostęp warunkowy w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

- Należy utworzyć szablon wiadomości z powiadomieniem. W przypadku wysyłania wiadomość e-mail do użytkowników ten szablon służy do tworzenia akcji dotyczących braku zgodności.

## <a name="create-a-notification-message-template"></a>Tworzenie szablonu wiadomości z powiadomieniem

1. Zaloguj się do [witryny Azure Portal](https://portal.azure.com) przy użyciu poświadczeń usługi Intune. 
2. Wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Zgodność urządzenia**, a następnie pozycję **Powiadomienia**. 
4. Wybierz pozycję **Utwórz powiadomienie**, a następnie wprowadź następujące informacje:

   - Nazwa
   - Temat
   - Wiadomość
   - Nagłówek wiadomości e-mail — dołącz logo firmy
   - Stopka wiadomości e-mail — dołącz nazwę firmy
   - Stopka wiadomości e-mail — dołącz informacje kontaktowe

   ![Przykład powiadomienia dotyczącego zgodności w usłudze Intune](./media/actionsfornoncompliance-1.PNG)

Gdy skończysz dodawać informacje, wybierz pozycję **Utwórz**. Szablon wiadomości z powiadomieniem jest gotowy do użytku.

> [!NOTE]
> Można również edytować wcześniej utworzony szablon powiadomienia.

## <a name="add-actions-for-noncompliance"></a>Dodawanie akcji w przypadku niezgodności

Domyślnie usługa Intune automatycznie tworzy akcję w przypadku niezgodności. Jeśli dane urządzenie nie jest zgodne z zasadami zgodności, ta akcja oznacza je jako niezgodne. Możesz dostosować, jak długo urządzenie będzie oznaczone jako niezgodne. Tej akcji nie można usunąć.

Akcję można dodać podczas tworzenia nowej zasady zgodności lub aktualizowania istniejącej zasady zgodności. 

1. W witrynie [Azure Portal](https://portal.azure.com) otwórz usługę **Microsoft Intune** i wybierz pozycję **Zgodność urządzenia**.
2. Wybierz pozycję **Zasady**, wybierz jedną z zasad, a następnie wybierz pozycję **Właściwości**. 

  Nie masz jeszcze zasad? Utwórz zasady dla systemu [Android](compliance-policy-create-android.md), [iOS](compliance-policy-create-ios.md), [Windows](compliance-policy-create-windows.md) lub innej platformy.
  
  > [!NOTE]
  > W tym momencie urządzenia JAMF i urządzenia przeznaczone dla grup urządzeń nie mogą odbierać akcji dotyczących zgodności.

3. Wybierz pozycję **Akcje w przypadku braku zgodności**, a następnie wybierz pozycję **Dodaj**, aby wprowadzić parametry akcji. Możesz wybrać wcześniej utworzony szablon wiadomości, dodać dodatkowych adresatów oraz zaktualizować harmonogram okresu prolongaty. W harmonogramie możesz wprowadzić liczbę dni (od 0 do 365), a następnie możesz wymusić zasady dostępu warunkowego. Jeśli jako liczbę dni wprowadzisz **0**, dostęp warunkowy **natychmiast** zablokuje dostęp do zasobów firmowych.

4. Po zakończeniu wybierz pozycję **Dodaj** > **OK**, aby zapisać zmiany.

## <a name="next-steps"></a>Następne kroki
Monitoruj aktywność zgodności urządzeń, uruchamiając raporty. Aby uzyskać wskazówki, zobacz [Monitorowanie zgodności urządzenia w usłudze Intune](device-compliance-monitor.md).
