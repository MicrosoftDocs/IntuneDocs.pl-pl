---
title: Komunikaty aplikacji Portal firmy, które mogą być wyświetlane na urządzeniach użytkowników
titleSuffix: Microsoft Intune
description: Wyjaśnienie różnych komunikatów, które użytkownicy końcowi mogą zobaczyć w aplikacji Portal firmy.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/09/2017
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3df993aa-48c5-4799-b68d-c85fe4f7b02c
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 57467d3d073666c1c22ac0a412f68a258d5b3d75
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "73414070"
---
# <a name="help-end-users-understand-company-portal-app-messages"></a>Pomaganie użytkownikom końcowym w zrozumieniu komunikatów aplikacji Portal firmy

> [!NOTE]
> Poniższe informacje dotyczą tylko urządzeń z systemem Android 6.0 lub nowszym oraz iOS 10 lub nowszym.

Wyjaśnienie różnych komunikatów, które użytkownicy końcowi mogą zobaczyć w aplikacji Portal firmy. Te komunikaty aplikacji są często wyświetlane na różnych etapach procesu rejestracji. Dowiedz się, gdzie są wyświetlane te komunikaty, co oznaczają i co się stanie, jeśli użytkownik nie zezwoli na dostęp. Dowiedz się również, jak najlepiej wyjaśnić znaczenie tych komunikatów użytkownikom.

- __Zezwolić aplikacji Portal firmy na połączenia telefoniczne i zarządzanie nimi?__
- __Zezwolić aplikacji Portal firmy na dostęp do zdjęć, multimediów i plików na Twoim urządzeniu?__

> [!NOTE]
> Danych zebranych przez naszą usługę nie sprzedajemy z jakiegokolwiek powodu żadnym osobom trzecim.

## <a name="allow-company-portal-to-make-and-manage-phone-calls"></a>Zezwolić aplikacji Portal firmy na połączenia telefoniczne i zarządzanie nimi?

### <a name="where-it-appears"></a>Gdzie jest dostępny

Komunikat **Zezwolić aplikacji Portal firmy na połączenia telefoniczne i zarządzanie nimi?** jest wyświetlany, gdy użytkownicy wybiorą opcję **Zarejestruj** w aplikacji Portal firmy podczas rejestracji urządzenia.

### <a name="what-it-means"></a>Znaczenie

Akceptując ten monit, użytkownicy zezwalają na przesłanie numeru telefonu i numerów IMEI do usługi Intune. Pojawią się one w konsoli administracyjnej na stronie __Sprzęt__.

> [!NOTE]
> **Aplikacja Portal firmy nigdy nie wykonuje połączeń telefonicznych ani nimi nie zarządza.** Tekst komunikatu jest kontrolowany przez firmę Google i nie można go zmienić.

Aby wyświetlić stronę **Sprzęt**, należy wybrać pozycję **Grupy** > **Wszystkie urządzenia przenośne** > **Urządzenia**. Wybierz urządzenie użytkownika, a następnie wybierz pozycje **Wyświetl właściwości** > **Sprzęt**.

### <a name="what-happens-if-users-deny-access"></a>Co się stanie, gdy użytkownik nie zezwoli na dostęp

Użytkownicy, którzy wybiorą opcję odmowy dostępu, mogą nadal korzystać z aplikacji Portal firmy i zarejestrować swoje urządzenie. Pola numeru telefonu i numeru IMEI urządzenia pozostaną jednak puste na stronie __Sprzęt__ w konsoli administracyjnej. Podczas drugiego logowania użytkownika do aplikacji Portal firmy po odmowie dostępu w komunikacie zostanie wyświetlone pole wyboru **Nigdy nie pytaj ponownie**. Jego zaznaczenie spowoduje, że komunikat przestanie być wyświetlany.

Jeśli użytkownik zezwoli na dostęp, lecz potem anuluje zezwolenie, komunikat zostanie wyświetlony podczas następnego logowania użytkownika do aplikacji Portal firmy po rejestracji.

Jeśli później użytkownik zdecyduje się zezwolić na dostęp, może wybrać pozycję **Ustawienia** > **Aplikacje** > **Portal firmy** > **Uprawnienia** > **Telefon** i włączyć dostęp.

### <a name="how-to-explain-this-to-your-users"></a>Jak wyjaśnić to użytkownikom

Odeślij użytkowników do sekcji [Rejestrowanie urządzenia z systemem Android w usłudze Intune](/intune-user-help/enroll-device-android-company-portal), aby umożliwić im uzyskanie szczegółowych informacji.

## <a name="allow-company-portal-to-access-your-contacts"></a>Zezwolić aplikacji Portal firmy na dostęp do Twoich kontaktów?

### <a name="where-it-appears"></a>Gdzie jest dostępny

Komunikat **Zezwolić aplikacji Portal firmy na dostęp do Twoich kontaktów?** jest wyświetlany, gdy użytkownik wybierze opcję **Zarejestruj** w aplikacji Portal firmy podczas rejestracji urządzenia.

### <a name="what-it-means"></a>Znaczenie

Akceptując ten monit, użytkownicy zezwalają usłudze Intune na utworzenie konta służbowego i zarządzanie tożsamością usługi Azure Active Directory, która jest zarejestrowana dla użytkownika na tym urządzeniu.

> [!NOTE]
> **Firma Microsoft nigdy nie uzyskuje dostępu do Twoich kontaktów!** Tekst komunikatu jest kontrolowany przez firmę Google i nie można go zmienić.

### <a name="what-happens-if-users-deny-access"></a>Co się stanie, gdy użytkownik nie zezwoli na dostęp

Jeśli użytkownik nie zezwoli na dostęp, jego urządzenie nie zostanie zarejestrowane w usłudze Intune i nie będzie można nim zarządzać. Podczas drugiego logowania użytkownika do aplikacji Portal firmy po odmowie dostępu w komunikacie zostanie wyświetlone pole wyboru **Nigdy nie pytaj ponownie**. Jego zaznaczenie spowoduje, że komunikat przestanie być wyświetlany.

Jeśli użytkownik zezwoli na dostęp, lecz potem anuluje zezwolenie, komunikat zostanie wyświetlony podczas następnego logowania użytkownika do aplikacji Portal firmy po rejestracji.

Jeśli później użytkownik zdecyduje się zezwolić na dostęp, może wybrać pozycję **Ustawienia** > **Aplikacje** > **Portal firmy** > **Uprawnienia** > **Telefon** i włączyć dostęp.

### <a name="how-to-explain-this-to-your-users"></a>Jak wyjaśnić to użytkownikom

Odeślij użytkowników do sekcji [Rejestrowanie urządzenia z systemem Android w usłudze Intune](/intune-user-help/enroll-device-android-company-portal), aby umożliwić im uzyskanie szczegółowych informacji.  

## <a name="allow-company-portal-to-access-photos-media-and-files-on-your-device"></a>Zezwolić aplikacji Portal firmy na dostęp do zdjęć, multimediów i plików na Twoim urządzeniu?

### <a name="where-it-appears"></a>Gdzie jest dostępny

Komunikat **Zezwolić aplikacji Portal firmy na dostęp do zdjęć, multimediów i plików na Twoim urządzeniu?** jest wyświetlany, gdy użytkownik wybierze opcję **Wyślij dane**, aby wysłać dzienniki do administratora IT.

### <a name="what-it-means"></a>Znaczenie

Akceptując ten monit, użytkownicy zezwalają swoim urządzeniom na zapisywanie dzienników danych na karcie SD urządzenia. To umożliwia też przenoszenie tych dzienników za pośrednictwem kabla USB.   

> [!NOTE]
> **Aplikacja Portal firmy nigdy nie uzyskuje dostępu do zdjęć, multimediów ani plików użytkownika.** Tekst komunikatu jest kontrolowany przez firmę Google i nie można go zmienić.

### <a name="what-happens-if-users-deny-access"></a>Co się stanie, gdy użytkownik nie zezwoli na dostęp

Jeśli użytkownik nie zezwoli na dostęp, nadal może wysyłać dzienniki danych za pośrednictwem poczty e-mail, ale dzienniki nie będą kopiowane na kartę SD urządzenia.

Podczas drugiego logowania użytkownika do aplikacji Portal firmy po odmowie dostępu w komunikacie zostanie wyświetlone pole wyboru **Nigdy nie pytaj ponownie**. Jego zaznaczenie spowoduje, że komunikat nigdy nie zostanie wyświetlony ponownie. Jeśli użytkownik zezwoli na dostęp, lecz potem anuluje zezwolenie, komunikat zostanie wyświetlony podczas następnej próby wysłania dzienników przez użytkownika. Jeśli jednak później użytkownik zdecyduje się zezwolić na dostęp, może wybrać pozycję **Ustawienia** > **Aplikacje** > **Portal firmy** > **Uprawnienia** > **Pamięć** i włączyć uprawnienie.


### <a name="how-to-explain-this-to-your-users"></a>Jak wyjaśnić to użytkownikom

Odeślij użytkowników do sekcji [Wysyłanie dzienników do administratora IT pocztą e-mail](/intune-user-help/send-logs-to-your-it-admin-by-email-android). 

## <a name="your-company-support-needs-to-give-you-access-to-company-resources"></a>Dział pomocy technicznej firmy musi udzielić Ci dostępu do zasobów firmy

### <a name="where-it-appears"></a>Gdzie jest dostępny

Jeśli aplikacja Portal firmy nie została dodana do listy **Dozwolone aplikacje** lub **Aplikacje wykluczone**, a użytkownik spróbuje się zalogować, logowanie nie powiedzie się. Zostanie wyświetlony następujący komunikat:

> **Dział pomocy technicznej firmy musi udzielić Ci dostępu do zasobów firmy**  
> Firma używa zasad usługi Windows Information Protection do ochrony Twojego urządzenia. Dział pomocy technicznej firmy musi się upewnić, że aplikacja Portal firmy ma dostęp do tych zasobów.

### <a name="what-it-means"></a>Znaczenie

Dodaj Portal firmy do listy **Dozwolone aplikacje** lub **Aplikacje wykluczone** w zasadach ochrony aplikacji usługi Windows Information Protection (WIP). Aby uzyskać więcej informacji, zobacz [Tworzenie i wdrażanie zasad ochrony aplikacji w funkcji Windows Information Protection (WIP) za pomocą usługi Intune](../apps/windows-information-protection-policy-create.md).

## <a name="approve-a-ios-company-app-line-of-business-app-on-your-ios-device"></a>Zatwierdź aplikację firmową systemu iOS (aplikacja biznesowa) na urządzeniu z systemem iOS 

### <a name="where-it-appears"></a>Gdzie jest dostępny

Aplikacje systemu iOS opracowywane przez organizację, które nie są dostępne w sklepie App Store, domyślnie nie są traktowane przez urządzenie jako zaufane. Gdy zainstalujesz takie aplikacje przy użyciu aplikacji Portal firmy, a następnie uruchomisz aplikację, zostanie wyświetlony następujący komunikat:

![Komunikat aplikacji systemu iOS — niezaufany twórca programów firmowych](./media/end-user-company-portal-messages/end-user-company-portal-messages-01.png)

### <a name="what-it-means"></a>Znaczenie

Ten komunikat oznacza, że musisz zmodyfikować ustawienia urządzenia z systemem iOS w celu zatwierdzenia i zainstalowania aplikacji opracowanej przez firmę na urządzeniu z systemem iOS.

Gdy zainstalujesz takie aplikacje przy użyciu aplikacji Portal firmy, a następnie uruchomisz aplikację, wykonaj poniższe kroki w celu zatwierdzenia pobranej aplikacji:

1. Po uruchomieniu zainstalowanej aplikacji firmowej (aplikacji biznesowej) zobaczysz komunikat „Niezaufany twórca programów firmowych”. <br>
   Naciśnij przycisk **Anuluj**.
2. Przejdź do pozycji **Ustawienia** > **Ogólne** > **Zarządzanie urządzeniami**.

   ![Interfejs użytkownika urządzenia z systemem iOS — zarządzanie urządzeniami](./media/end-user-company-portal-messages/end-user-company-portal-messages-02.png)

3. Wybierz pozycję **Profil zarządzania** > **Aplikacja przedsiębiorstwa**.
4. Wybierz nazwę dewelopera.
5. Naciśnij klawisz **Ufaj deweloperowi _nazwa dewelopera_** .
6. Potwierdź aplikację, wybierając przycisk **Ufaj** w wyskakującym okienku z komunikatem dotyczącym instalacji aplikacji.

   ![Interfejs użytkownika urządzenia z systemem iOS — komunikat dotyczący zaufania w aplikacji](./media/end-user-company-portal-messages/end-user-company-portal-messages-03.png)

    Teraz uruchomienie aplikacji i korzystanie z niej powinno być możliwe.


## <a name="see-also"></a>Zobacz także
[Co powinni wiedzieć użytkownicy końcowi na temat korzystania z usługi Intune](end-user-educate.md)
