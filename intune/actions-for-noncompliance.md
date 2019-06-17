---
title: Komunikaty i akcje dotyczące braku zgodności w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Utwórz wiadomość e-mail z powiadomieniem, która zostanie wysłana do niezgodnych urządzeń. Dodaj akcje do wykonania po oznaczeniu urządzenia jako niezgodne, takie jak dodanie okresu prolongaty na zapewnienie zgodności lub utworzenie harmonogram w celu zablokowania dostępu, dopóki urządzenie nie będzie zgodne. Zrób to za pomocą usługi Microsoft Intune na platformie Azure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/01/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b799fd65a08646b46bf7fcce67bf4a09dc0413a6
ms.sourcegitcommit: cc5d757018d05fc03ac9ea3d30f563df9bfd61ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/10/2019
ms.locfileid: "66819914"
---
# <a name="automate-email-and-add-actions-for-noncompliant-devices-in-intune"></a>Automatyzowanie poczty e-mail i dodawanie akcji dla niezgodnych urządzeń w usłudze Intune

W przypadku urządzeń, które nie są zgodne z zasadami lub regułami zgodności, możesz dodać **Akcje w przypadku niezgodności**. Ta funkcja umożliwia skonfigurowanie uporządkowanej w czasie sekwencji akcji, takich jak wysyłanie wiadomości e-mail do użytkownika końcowego i nie tylko.

## <a name="overview"></a>Przegląd

Domyślnie po wykryciu przez usługę Intune urządzenia, które nie jest zgodne, usługa Intune natychmiast oznacza to urządzenie jako niezgodne. [Dostęp warunkowy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) usługi Azure Active Directory (AD) blokuje wtedy dane urządzenie. **Akcja w przypadku niezgodności** zapewnia także elastyczność w przypadku podejmowania decyzji o postępowaniu z urządzeniami niezgodnymi. Możesz na przykład zdecydować, aby nie blokować urządzenia natychmiast i przyznać użytkownikowi okres prolongaty, aby mógł zapewnić zgodność.

Istnieje kilka typów działań:

- **Wyślij wiadomość e-mail do użytkownika końcowego**: umożliwia dostosowanie powiadomienia e-mail przed wysłaniem go do użytkownika końcowego. Możesz dostosować adresatów, temat oraz treść wiadomości, w tym logo firmy oraz informacje kontaktowe.

    Ponadto usługa Intune dołącza do powiadomienia e-mail szczegółowe informacje dotyczące niezgodnych urządzeń.

- **Zdalne zablokowanie niezgodnego urządzenia**: w przypadku urządzeń, które nie są zgodne, możesz zastosować zdalną blokadę. Następnie wyświetlany jest monit, w którym użytkownik jest proszony o podanie numeru PIN lub hasła w celu odblokowania urządzenia. Więcej informacji na temat funkcji [zdalnego blokowania](device-remote-lock.md). 

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

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Zgodność urządzenia** > **Powiadomienia**.
3. Wybierz pozycję **Utwórz powiadomienie**. Wprowadź następujące informacje:

   - **Nazwa**
   - **Temat**
   - **Wiadomość**
   - **Nagłówek wiadomości e-mail — dołącz logo firmy**
   - **Stopka wiadomości e-mail — dołącz nazwę firmy**
   - **Stopka wiadomości e-mail — dołącz informacje kontaktowe**

   ![Przykład powiadomienia dotyczącego zgodności w usłudze Intune](./media/actionsfornoncompliance-1.PNG)

4. Gdy skończysz dodawać informacje, wybierz pozycję **Utwórz**. Szablon wiadomości z powiadomieniem jest gotowy do użytku. Logo przekazane w ramach znakowania Portalu firmy jest używane w szablonach wiadomości e-mail. Aby uzyskać więcej informacji na temat znakowania Portalu firmy, zobacz [Dostosowywanie znakowania tożsamości firmy](company-portal-app.md#company-identity-branding-customization).

> [!NOTE]
> Możesz również zmienić lub zaktualizować istniejący szablon powiadomienia, który został wcześniej utworzony.

## <a name="add-actions-for-noncompliance"></a>Dodawanie akcji w przypadku niezgodności

Podczas tworzenia zasad zgodności urządzeń usługa Intune automatycznie tworzy akcję w przypadku niezgodności. Jeśli dane urządzenie nie jest zgodne z zasadami zgodności, ta akcja oznacza je jako niezgodne. Możesz dostosować, jak długo urządzenie będzie oznaczone jako niezgodne. Tej akcji nie można usunąć.

Podczas tworzenia zasady zgodności lub aktualizowania istniejącej zasady można także dodać kolejną akcję. 

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) i wybierz pozycję **Zgodność urządzenia**.
2. Wybierz pozycję **Zasady**, wybierz jedną z zasad, a następnie wybierz pozycję **Właściwości**. 

    Nie masz jeszcze zasad? Utwórz zasady dla systemu [Android](compliance-policy-create-android.md), [iOS](compliance-policy-create-ios.md), [Windows](compliance-policy-create-windows.md) lub innej platformy.
  
    > [!NOTE]
    > W tym momencie urządzenia JAMF i urządzenia przeznaczone dla grup urządzeń nie mogą odbierać akcji dotyczących zgodności.

3. Wybierz pozycje **Akcje w przypadku niezgodności** > **Dodaj**.
4. Wybierz swoją **akcję**: 

    - **Wyślij wiadomość e-mail do użytkowników końcowych**: wyślij wiadomość e-mail do użytkownika, gdy urządzenie jest niezgodne. Ponadto: 
    
         - Wybierz wcześniej utworzony **szablon wiadomości**
         - Wprowadź dowolnych **dodatkowych adresatów** przez wybranie grup
    
    - **Zdalne zablokowanie niezgodnego urządzenia**: zablokuj urządzenie, gdy urządzenie jest niezgodne. Ta akcja wymusza wprowadzenie przez użytkownika numeru PIN lub hasła w celu odblokowania urządzenia. 
    
5. Skonfiguruj **Harmonogram**: wprowadź liczbę dni (od 0 do 365), jaka ma upłynąć od stwierdzenia niezgodności, w celu wyzwolenia akcji na urządzeniach użytkowników. Po tym okresie prolongaty można wymusić zasady dostępu warunkowego. Jeśli wprowadzisz **0** (zero) jako liczbę dni, dostęp warunkowy będzie obowiązywać **natychmiast**. Na przykład można natychmiastowo zablokować dostęp do zasobów firmowych, jeśli urządzenie jest niezgodne.

6. Po zakończeniu wybierz pozycję **Dodaj** > **OK**, aby zapisać zmiany.

## <a name="next-steps"></a>Następne kroki

[Monitorowanie zasad](compliance-policy-monitor.md).
