---
title: Komunikaty i akcje dotyczące braku zgodności w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Utwórz wiadomość e-mail z powiadomieniem, która zostanie wysłana do niezgodnych urządzeń. Dodaj akcje do wykonania po oznaczeniu urządzenia jako niezgodne, takie jak dodanie okresu prolongaty na zapewnienie zgodności lub utworzenie harmonogram w celu zablokowania dostępu, dopóki urządzenie nie będzie zgodne. Zrób to za pomocą usługi Microsoft Intune na platformie Azure.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/08/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 50478ecb615cf39bba0a205cb06f83e47728e366
ms.sourcegitcommit: 8f56220e7cafc5bc43135940575a9acb5afde730
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/09/2020
ms.locfileid: "75827840"
---
# <a name="automate-email-and-add-actions-for-noncompliant-devices-in-intune"></a>Automatyzowanie poczty e-mail i dodawanie akcji dla niezgodnych urządzeń w usłudze Intune

W przypadku urządzeń, które nie są zgodne z zasadami lub regułami zgodności, możesz dodać **Akcje w przypadku niezgodności**. Ta funkcja umożliwia skonfigurowanie uporządkowanej w czasie sekwencji akcji, takich jak wysyłanie wiadomości e-mail do użytkownika końcowego i nie tylko.

## <a name="overview"></a>Omówienie

Domyślnie po wykryciu przez usługę Intune urządzenia, które nie jest zgodne, usługa Intune natychmiast oznacza to urządzenie jako niezgodne. [Dostęp warunkowy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) usługi Azure Active Directory (AD) blokuje wtedy dane urządzenie. **Akcja w przypadku niezgodności** zapewnia także elastyczność w przypadku podejmowania decyzji o postępowaniu z urządzeniami niezgodnymi. Możesz na przykład zdecydować, aby nie blokować urządzenia natychmiast i przyznać użytkownikowi okres prolongaty, aby mógł zapewnić zgodność.

Istnieje kilka typów działań:

- **Wyślij wiadomość e-mail do użytkownika końcowego**: umożliwia dostosowanie powiadomienia e-mail przed wysłaniem go do użytkownika końcowego. Możesz dostosować adresatów, temat oraz treść wiadomości, w tym logo firmy oraz informacje kontaktowe.

    Ponadto usługa Intune dołącza do powiadomienia e-mail szczegółowe informacje dotyczące niezgodnych urządzeń.

- **Zdalne zablokowanie niezgodnego urządzenia**: w przypadku urządzeń, które nie są zgodne, możesz zastosować zdalną blokadę. Następnie wyświetlany jest monit, w którym użytkownik jest proszony o podanie numeru PIN lub hasła w celu odblokowania urządzenia. Więcej informacji na temat funkcji [zdalnego blokowania](../remote-actions/device-remote-lock.md).

- **Oznacz urządzenie jako niezgodne**: utwórz harmonogram z liczbą dni, po których urządzenie zostanie oznaczone jako niezgodne. Akcję można skonfigurować tak, by następowała od razu, ale można również przyznać użytkownikowi okres prolongaty.

W tym artykule wyjaśniono, jak:

- Utworzyć szablon powiadomień wiadomości
- Utworzyć akcję w przypadku niezgodności, np. wysłanie wiadomości e-mail lub zdalne zablokowanie urządzenia


## <a name="before-you-begin"></a>Przed rozpoczęciem

- Aby skonfigurować akcje w przypadku niezgodności, musisz mieć co najmniej jedną zasadę zgodności urządzeń. Aby utworzyć zasady zgodności urządzeń, zapoznaj się z następującymi platformami:

  - [Android](compliance-policy-create-android.md)
  - [Profile służbowe systemu Android](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows](compliance-policy-create-windows.md)

- W przypadku blokowania urządzeniom dostępu do zasobów firmowych przy użyciu zasad zgodności urządzeń musisz mieć skonfigurowany dostęp warunkowy usługi Azure AD. Aby uzyskać wskazówki, zobacz artykuł [Dostęp warunkowy w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) lub [Typowe sposoby korzystania z dostępu warunkowego przy użyciu usługi Intune](conditional-access-intune-common-ways-use.md).

## <a name="create-a-notification-message-template"></a>Tworzenie szablonu wiadomości z powiadomieniem

Aby wysyłać wiadomości e-mail do użytkowników, należy utworzyć szablon wiadomości z powiadomieniem. Gdy urządzenie jest niezgodne, szczegółowe informacje wprowadzone w szablonie są wyświetlane w wiadomości e-mail wysyłanej do użytkowników.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz kolejno pozycje **Urządzenia** > **Zasady zgodności** > **Powiadomienia** > **Utwórz powiadomienie**.
3. W obszarze *Podstawy* podaj następujące informacje:

   - **Nazwa**
   - **Temat**
   - **Wiadomość**

4. W obszarze *Podstawy* skonfiguruj również następujące opcje dla powiadomienia (domyślnie są one *włączone*):

   - **Nagłówek wiadomości e-mail — dołącz logo firmy**
   - **Stopka wiadomości e-mail — dołącz nazwę firmy**
   - **Stopka wiadomości e-mail — dołącz informacje kontaktowe**

   Logo przekazane w ramach znakowania Portalu firmy jest używane w szablonach wiadomości e-mail. Aby uzyskać więcej informacji na temat znakowania Portalu firmy, zobacz [Dostosowywanie znakowania tożsamości firmy](../apps/company-portal-app.md#company-identity-branding-customization).

   ![Przykład powiadomienia dotyczącego zgodności w usłudze Intune](./media/actions-for-noncompliance/actionsfornoncompliance-1.PNG)

   Wybierz przycisk **Dalej**, aby kontynuować.

5. W obszarze **Przeglądanie + tworzenie** przejrzyj konfiguracje, aby upewnić się, że szablon wiadomości z powiadomieniem jest gotowy do użycia. Wybierz pozycję **Utwórz**, aby ukończyć tworzenie powiadomienia.

> [!NOTE]
> Możesz również wybrać istniejący, wcześniej utworzony szablon powiadomienia i **edytować** jego informacje w celu zaktualizowania szablonu.

## <a name="add-actions-for-noncompliance"></a>Dodawanie akcji w przypadku niezgodności

Podczas tworzenia zasad zgodności urządzeń usługa Intune automatycznie tworzy akcję w przypadku niezgodności. Jeśli dane urządzenie nie jest zgodne z zasadami zgodności, ta akcja oznacza je jako niezgodne. Możesz dostosować, jak długo urządzenie będzie oznaczone jako niezgodne. Tej akcji nie można usunąć.

Oprócz domyślnej akcji oznaczania urządzeń jako niezgodnych można dodać opcjonalne akcje podczas tworzenia zasad zgodności lub aktualizowania istniejących zasad.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz pozycję **Urządzenia** > **Zasady zgodności** > **Zasady**, wybierz jedne z zasad, a następnie wybierz pozycję **Właściwości**.

   Nie masz jeszcze zasad? Utwórz zasady dla systemu [Android](compliance-policy-create-android.md), [iOS](compliance-policy-create-ios.md), [Windows](compliance-policy-create-windows.md) lub innej platformy.

   > [!NOTE]
   > W tym momencie urządzenia JAMF i urządzenia przeznaczone dla grup urządzeń nie mogą odbierać akcji dotyczących zgodności.

3. Wybierz pozycje **Akcje w przypadku niezgodności** > **Dodaj**.

4. Wybierz swoją **akcję**:

   - **Wyślij wiadomość e-mail do użytkowników końcowych**: wyślij wiadomość e-mail do użytkownika, gdy urządzenie jest niezgodne. Ponadto:
     - Wybierz wcześniej utworzony **szablon wiadomości**
     - Wprowadź dowolnych **dodatkowych adresatów** przez wybranie grup

   - **Zdalne zablokowanie niezgodnego urządzenia**: zablokuj urządzenie, gdy urządzenie jest niezgodne. Ta akcja wymusza wprowadzenie przez użytkownika numeru PIN lub hasła w celu odblokowania urządzenia.

5. Skonfiguruj **Harmonogram**: wprowadź liczbę dni (od 0 do 365), jaka ma upłynąć od stwierdzenia niezgodności, w celu wyzwolenia akcji na urządzeniach użytkowników. Po tym okresie prolongaty można wymusić zasady [dostępu warunkowego](conditional-access-intune-common-ways-use.md). Jeśli wprowadzisz **0** (zero) jako liczbę dni, dostęp warunkowy będzie obowiązywać **natychmiast**. Jeśli na przykład urządzenie jest niezgodne, użyj dostępu warunkowego, aby natychmiast zablokować dostęp do poczty e-mail, programu SharePoint i innych zasobów organizacji.

   Podczas tworzenia zasad zgodności akcja **Oznacz urządzenie jako niezgodne** jest tworzona automatycznie i jest dla niej ustawiana wartość **0** dni (natychmiast). Z tą akcją urządzenie po zaewidencjonowaniu jest od razu oceniane jako niezgodne. W przypadku korzystania z dostępu warunkowego jest ono uruchamiane natychmiast. Jeśli chcesz zezwolić na okres prolongaty, zmień wartość pozycji **Harmonogram** dla akcji **Oznacz urządzenie jako niezgodne**.

   W zasadach zgodności warto również powiadomić użytkownika. Można dodać akcję **Wyślij wiadomość e-mail do użytkownika końcowego**. W przypadku tej akcji **Wyślij wiadomość e-mail** dla opcji **Harmonogram** ustaw wartość 2 dni. Jeśli urządzenie lub użytkownik końcowy nadal będą oceniani jako niezgodni w dniu 2, wiadomość e-mail zostanie wysłana w dniu 2. Jeśli chcesz ponownie wysłać wiadomość e-mail do użytkownika 5 dnia niezgodności, dodaj kolejną akcję i ustaw wartość opcji **Harmonogram** na 5 dni.

   Aby uzyskać więcej informacji na temat zgodności oraz wbudowanych akcji, zobacz [omówienie zgodności](device-compliance-get-started.md).

6. Po zakończeniu wybierz pozycję **Dodaj** > **OK**, aby zapisać zmiany.

## <a name="next-steps"></a>Następne kroki

[Monitorowanie zasad](compliance-policy-monitor.md).
