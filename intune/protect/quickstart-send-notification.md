---
title: Szybki start — wysyłanie powiadomień do niezgodnych urządzeń
titleSuffix: Microsoft Intune
description: W tym przewodniku Szybki start użyjesz usługi Microsoft Intune w celu wysyłania powiadomień e-mail do niezgodnych urządzeń.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/21/2019
ms.topic: quickstart
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a1b89f2d-7937-46bb-926b-b05f6fa9c749
ms.reviewer: jinyoon
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6d89cfcafd5452b990509e0fa6fd431a614ee5c1
ms.sourcegitcommit: a7b479c84b3af5b85528db676594bdb3a1ff6ec6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/22/2019
ms.locfileid: "74410254"
---
# <a name="quickstart-send-notifications-to-noncompliant-devices"></a>Szybki start: Wysyłanie powiadomień do niezgodnych urządzeń

W tym przewodniku Szybki start użyjesz usługi Microsoft Intune w celu wysyłania powiadomień e-mail do pracowników, którzy mają niezgodne urządzenia.

Domyślnie po wykryciu przez usługę Intune urządzenia, które nie jest zgodne, usługa Intune natychmiast oznacza to urządzenie jako niezgodne. [Dostęp warunkowy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) usługi Azure Active Directory (Azure AD) blokuje wtedy dane urządzenie. Gdy urządzenie jest niezgodne, usługa Intune umożliwia dodanie akcji dotyczących niezgodności, co zapewnia elastyczność podejmowania decyzji. Możesz na przykład przez zablokowaniem niezgodnych urządzeń wyznaczyć użytkownikom okres prolongaty, w trakcie którego będą mieli czas na zapewnienie zgodności urządzenia.

Jedną z akcji, którą można wykonać, gdy urządzenie nie spełnia warunków zgodności, jest wysłanie wiadomości e-mail do użytkownika urządzenia. Powiadomienie e-mail można dostosować przed wysłaniem. Możesz dostosować adresatów, temat oraz treść wiadomości, w tym logo firmy oraz informacje kontaktowe. Ponadto usługa Intune dołącza do powiadomienia e-mail szczegółowe informacje dotyczące niezgodnych urządzeń.

Jeśli nie masz subskrypcji usługi Intune, [utwórz konto bezpłatnej wersji próbnej](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Wymagania wstępne

W przypadku blokowania urządzeniom dostępu do zasobów firmowych przy użyciu zasad zgodności urządzeń musisz mieć skonfigurowany dostęp warunkowy usługi Azure AD. Ukończenie przewodnika Szybki start [Tworzenie zasad zgodności urządzenia](quickstart-set-password-length-android.md) oznacza, że używasz usługi Azure Active Directory. Aby uzyskać więcej informacji na temat usługi Azure AD, zobacz [Dostęp warunkowy w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) oraz [Typowe sposoby korzystania z dostępu warunkowego przy użyciu usługi Intune](../protect/conditional-access-intune-common-ways-use.md).

## <a name="sign-in-to-intune"></a>Logowanie się do usługi Intune

Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) jako [administrator globalny](../fundamentals/users-add.md#types-of-administrators) lub [administrator usługi Intune](../fundamentals/users-add.md#types-of-administrators). Jeśli utworzono subskrypcję wersji próbnej usługi Intune, konto, którego użyto do utworzenia subskrypcji, jest administratorem globalnym.

## <a name="create-a-notification-message-template"></a>Tworzenie szablonu wiadomości z powiadomieniem

Aby wysyłać wiadomości e-mail do użytkowników, należy utworzyć szablon wiadomości z powiadomieniem. Gdy urządzenie jest niezgodne, szczegółowe informacje wprowadzone w szablonie są wyświetlane w wiadomości e-mail wysyłanej do użytkowników.

1. W usłudze Intune wybierz pozycję **Urządzenia** > **Zasady zgodności** > **Powiadomienia** > **Utwórz powiadomienie**.
2. Wprowadź następujące informacje:

   - **Nazwa**: *Administrator firmy Contoso*
   - **Temat**: *Zgodność urządzeń*
   - **Wiadomość**: *Urządzenie obecnie nie spełnia wymogów zgodności w organizacji.*
   - **Nagłówek wiadomości e-mail — dołącz logo firmy**: Ustaw opcję **Włączone**, aby pokazać logo organizacji.
   - **Stopka wiadomości e-mail — dołącz nazwę firmy**: Ustaw opcję **Włączone**, aby pokazać nazwę organizacji.
   - **Stopka wiadomości e-mail — dołącz informacje kontaktowe**: Ustaw opcję **Włączone**, aby pokazać informacje kontaktowe firmy.

   ![Przykład powiadomienia dotyczącego zgodności w usłudze Intune](./media/quickstart-send-notification/quickstart-send-notification-01.png)

3. Wybierz pozycję **Dalej** i przejrzyj powiadomienie. Wybierz pozycję **Utwórz** i szablon wiadomości z powiadomieniem będzie gotowy do użytku.

   > [!NOTE]
   > Możesz również edytować wcześniej utworzony szablon powiadomienia.

Aby uzyskać szczegółowe informacje na temat ustawiania nazwy firmy, informacji kontaktowych firmy i logo firmy, zobacz następujące artykuły:

- [Informacje o firmie i zasady zachowania poufności informacji](../apps/company-portal-app.md#company-information-and-privacy-statement)
- [Informacje dotyczące pomocy technicznej](../apps/company-portal-app.md#support-information)
- [Dostosowywanie znakowania tożsamości firmy](../apps/company-portal-app.md#company-identity-branding-customization).

## <a name="add-a-noncompliance-policy"></a>Dodawanie zasad niezgodności

Podczas tworzenia zasad zgodności urządzeń usługa Intune automatycznie tworzy akcję w przypadku niezgodności. Następnie usługa Intune oznacza urządzenia jako niezgodne, gdy nie spełniają zasad zgodności. Możesz dostosować czas, przez jaki urządzenie będzie oznaczone jako niezgodne. Podczas tworzenia zasad zgodności lub aktualizowania istniejących zasad możesz także dodać kolejną akcję.

Poniższe kroki umożliwiają utworzenie zasad zgodności dla urządzeń z systemem Windows 10.

1. W usłudze Intune wybierz pozycję **Urządzenia** > **Zasady zgodności** > **Utwórz zasady**.

2. Wprowadź następujące informacje:

   - **Nazwa**: *Zgodność systemu Windows 10*
   - **Opis**: *Zasady zgodności systemu Windows 10*
   - **Platforma**: Windows 10 lub nowszym

3. Wybierz kolejno pozycje **Ustawienia** > **Zabezpieczenia systemu**, aby wyświetlić ustawienia dotyczące zabezpieczeń urządzenia.

4. Skonfiguruj następujące opcje:

   - W obszarze **Wymagaj hasła do odblokowania urządzeń przenośnych** wybierz pozycję **Wymagaj**. To ustawienie określa, czy użytkownicy mają wpisywać hasło przed uzyskaniem dostępu do informacji zapisanych na urządzeniu przenośnym.

   - Ustaw **minimalną długość hasła** na **6**. To ustawienie określa minimalną liczbę cyfr lub znaków hasła.

   ![Ustawienia zabezpieczeń systemu dla nowych zasad zgodności](./media/quickstart-send-notification/system-security-settings-01.png)

5. Kliknij kolejno pozycje **OK** > **OK** > **Utwórz**, aby utworzyć zasady zgodności.

6. Wybierz kolejno pozycje **Właściwości** > **Akcja dotycząca niezgodności** > **Dodaj**.

7. W polu listy rozwijanej **Akcja** sprawdź, czy wybrano pozycję **Wyślij wiadomość e-mail do użytkowników końcowych**.

8. Wybierz pozycję **Szablon wiadomości**, wybierz szablon utworzony we wcześniejszej części tego tematu, a następnie pozycję **Wybierz**, aby wybrać szablon wiadomości.

9. Wybierz kolejno pozycje **DODAJ** > **OK** > **Zapisz**, aby zapisać zmiany.

## <a name="assign-the-policy"></a>Przypisywanie zasad

Zasady zgodności można przypisać do konkretnej grupy użytkowników lub do wszystkich użytkowników. Gdy usługa Intune rozpozna niezgodne urządzenie, użytkownik jest powiadamiany, że musi zaktualizować urządzenie, aby spełniało zasady zgodności. Wykonaj poniższe kroki, aby przypisać zasady.

1. W usłudze Intune przejdź do pozycji **Urządzenia** > **Zasady zgodności** i wybierz utworzone wcześniej zasady **zgodności systemu Windows 10**.

2. Wybierz pozycję **Przypisania**.

3. W polu listy rozwijanej **Przypisz do** wybierz pozycję **Wszyscy użytkownicy**. Dzięki temu wybrani zostaną wszyscy użytkownicy. Każdy użytkownik mający urządzenie z systemem **Windows 10 lub nowszym**, które nie spełnia zasad zgodności, zostanie o tym powiadomiony.

    > [!NOTE]
    > Możesz dołączać lub wykluczać grupy podczas przypisywania zasad zgodności.

4. Kliknij polecenie **Zapisz**.

Jeśli zasady zostały pomyślnie utworzone i zapisane, pojawią się na liście **Zasady zgodności — zasady**. Zwróć uwagę, że opcja **Przypisane** na liście jest ustawiona na **Tak**.

## <a name="next-steps"></a>Następne kroki

W tym przewodniku Szybki start użyto usługi Intune do utworzenia i przypisania zasad zgodności dla urządzeń z systemem Windows 10 pracowników, które będą wymagać wprowadzenia hasła składającego się z co najmniej sześciu znaków. Aby uzyskać więcej informacji na temat tworzenia zasad zgodności dla urządzeń z systemem Windows, zobacz [Dodawanie zasad zgodności urządzeń z systemem Windows w usłudze Intune](compliance-policy-create-windows.md).

Aby zapoznać się z kolejnymi przewodnikami Szybki start dotyczącymi usługi Intune, przejdź do kolejnego przewodnika Szybki start.

> [!div class="nextstepaction"]
> [Szybki start: Dodawanie i przypisywanie aplikacji klienckiej](../apps/quickstart-add-assign-app.md)
