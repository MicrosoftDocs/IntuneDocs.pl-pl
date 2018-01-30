---
title: "Rejestrowanie urządzenia z systemem Android w usłudze Intune | Microsoft Docs"
description: "Opis sposobu rejestrowania urządzenia z systemem Android w usłudze Intune"
keywords: 
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 10/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
searchScope:
- User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 89262f4fecba6aa8d76efd7fd5bbe415d9048204
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="enroll-your-android-device-in-intune"></a>Rejestrowanie urządzenia z systemem Android w usłudze Intune

Jeśli firma lub szkoła używa usługi Microsoft Intune, możesz zarejestrować urządzenie z systemem Android, aby uzyskać dostęp do poczty e-mail, plików i innych zasobów firmy. Po zarejestrowaniu urządzeń dział IT może zarządzać zasobami służbowymi i zabezpieczać je, a użytkownicy mogą korzystać z preferowanych urządzeń podczas wykonywania pracy. Aby uzyskać więcej informacji o rejestracji, zobacz [Co się stanie, jeśli zainstaluję aplikację Portal firmy i zarejestruję swoje urządzenie?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-android.md)

> [!VIDEO https://channel9.msdn.com/Series/IntuneEnrollment/Android-Enrollment/player]

Te instrukcje dotyczące rejestracji są przeznaczone dla urządzeń z systemem Android Samsung Knox i urządzeń z natywnym systemem Android. Samsung Knox to rodzaj zabezpieczenia dostępnego w niektórych urządzeniach firmy Samsung. Funkcja ta zapewnia dodatkową ochronę poza zabezpieczeniami dostępnymi w natywnym systemie Android. Aby sprawdzić, czy masz urządzenie z rozwiązaniem Samsung Knox, przejdź do pozycji **Ustawienia** > **Informacje o urządzeniu**. Jeśli na tej liście nie widzisz pozycji „Knox version” (Wersja systemu Knox), oznacza to, że masz urządzenie z natywnym systemem Android.

Przed zarejestrowaniem lub po nim może pojawić się monit o wybranie kategorii, która najlepiej opisuje Twój sposób korzystania z urządzenia. Dział pomocy technicznej Twojej firmy używa tej kategorii, aby pomóc sprawdzić aplikacje, do których masz dostęp.

**Aby zarejestrować urządzenie z systemem Android:**

1.  Zainstaluj bezpłatną aplikację Portal firmy usługi Intune ze sklepu [Google Play](http://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal).

2.  Otwórz aplikację Portal firmy.

3.  Na **ekranie powitalnym** Portalu firmy naciśnij przycisk **Zaloguj**, a następnie zaloguj się przy użyciu swojego konta służbowego.

    ![Ekran powitalny aplikacji Portal firmy dla systemu Android, która prosi użytkownika o zalogowanie się przy użyciu odpowiedniego konta służbowego. Warto wiedzieć, że konta Microsoft i inne konta osobiste nie są akceptowane.](./media/and-enroll-0-welcome-screen.png)   

4.  Jeśli dział pomocy technicznej Twojej firmy skonfigurował firmowe warunki i postanowienia, naciśnij przycisk **AKCEPTUJ**, aby zaakceptować postanowienia. Zawartość tego ekranu może różnić się nieco od poniższej ilustracji w zależności od używanej wersji systemu Android.

    ![android-company-portal-sign-in](./media/and-enroll-3-accept-terms.png)

5.  Zaloguj się w aplikacji Portal firmy, podając służbowe konto i hasło, a następnie naciśnij pozycję **Zaloguj**.

    ![android-company-portal-sign-in](./media/and-enroll-2-cp-sign-in.png)

6.  Na ekranie **Konfigurowanie dostępu do zasobów firmy** naciśnij pozycję **KONTYNUUJ**.

    ![Ekran konfigurowania dostępu do zasobów firmy](/intune/media/android_cp_enroll_01_1709_new.png)

    > [!NOTE]
    > Żółte trójkąty nie oznaczają wystąpienia błędu. Te ikony wskazują, że do zakończenia procesu rejestracji pozostało do wykonania kilka czynności.

7.  Przejrzyj listę rzeczy, które dział pomocy technicznej Twojej firmy może zobaczyć na Twoim urządzeniu i których nie może zobaczyć, a następnie naciśnij pozycję **KONTYNUUJ**.

    ![Ustawienia prywatności](/intune/media/android_cp_enroll_02_after_1710.png)

9.  Na ekranie **Co dalej?** przeczytaj, co będzie się działo podczas rejestrowania, a następnie naciśnij pozycję **ZAREJESTRUJ**.

    ![Ekran Co teraz](/intune/media/android_cp_enroll_03_after_1710.png)

10.  Wykonaj ten krok, jeśli używasz systemu Android w wersji 6.0 lub nowszej. W przeciwnym razie przejdź do następnego kroku.

    Jeśli dział pomocy technicznej Twojej firmy skonfigurował pewne zasady, mogą pojawić się następujące komunikaty:
    -   **Zezwolić aplikacji Portal firmy na połączenia telefoniczne i zarządzanie nimi?**

        ![android-company-portal-sign-in](./media/and-enroll-3a-allow-phone-access.png)

    Jeśli ten komunikat zostanie wyświetlony, naciśnij opcję **ZEZWALAJ**. Naciśnięcie pozycji ZEZWALAJ jest bezpieczne, ponieważ **firma Microsoft nigdy nie nawiązuje za Ciebie połączeń telefonicznych ani nie zarządza nimi**! Tekst komunikatu pochodzi od firmy Google, a firma Microsoft nie może go zmienić. Zezwolenie na dostęp oznacza, że umożliwisz tylko urządzeniu wysłanie międzynarodowego numeru identyfikacyjnego urządzenia przenośnego (IMEI) do usługi Intune. Numer IMEI to numer podobny do numeru seryjnego, który jednoznacznie identyfikuje urządzenie przenośne.

    Jeśli odmówisz dostępu, komunikat pojawi się ponownie przy kolejnym logowaniu do Portalu firmy, ale możesz wyłączyć wyświetlanie komunikatów w przyszłości, naciskając pole **Nigdy nie pytaj ponownie**. Jeśli później zdecydujesz zezwolić na dostęp, przejdź do pozycji **Ustawienia** &gt; **Aplikacje** &gt; **Portal firmy** &gt; **Uprawnienia** &gt; **Telefon** i włącz uprawnienie.

    -   **Zezwolić aplikacji Portal firmy na dostęp do Twoich kontaktów?**

        ![android-company-portal-sign-in](./media/and-enroll-3b-allow-contacts-access.png)

        Jeśli ten komunikat zostanie wyświetlony, naciśnij opcję **ZEZWALAJ**. Naciśnięcie pozycji ZEZWALAJ jest bezpieczne, ponieważ **firma Microsoft nigdy nie uzyskuje dostępu do Twoich kontaktów!** Tekst komunikatu pochodzi od firmy Google, a firma Microsoft nie może go zmienić. Jeśli zezwolisz na dostęp, aplikacja Portal firmy będzie mogła tylko utworzyć konto służbowe, korzystać z niego i zarządzać nim.

        Jeśli odmówisz dostępu, komunikat pojawi się ponownie przy kolejnym logowaniu do Portalu firmy, ale możesz wyłączyć wyświetlanie komunikatów w przyszłości, naciskając pole **Nigdy nie pytaj ponownie**. Jeśli później zdecydujesz zezwolić na dostęp, przejdź do pozycji **Ustawienia** &gt; **Aplikacje** &gt; **Portal firmy** &gt; **Uprawnienia** &gt; **Telefon** i włącz uprawnienie.

11.  Na ekranie **Aktywowanie administratora urządzenia** naciśnij przycisk **Aktywuj**.

    ![Ekran Aktywowanie administratora urządzenia](./media/and-enroll-5-activate.png)

    Do zarządzania urządzeniem Portal firmy wymaga roli administratora. Umożliwia ona administratorowi wyświetlenie niektórych informacji – na przykład o liczbie prób odblokowania ekranu — oraz podjęcie określonych działań.

    Należy pamiętać, że te działania są podejmowane w trosce o bezpieczeństwo. Dział pomocy technicznej Twojej firmy nie dokonuje próby naruszenia prywatności lub usunięcia informacji bez powodu, ale aby się upewnić, że dane firmowe są bezpieczne.

    Firma Microsoft nie kontroluje tego komunikatu i zdaje sobie sprawę, że jego brzmienie może się wydawać nieco drastyczne. Nie istnieje metoda wyświetlania w Portalu firmy wyłącznie ograniczeń i dostępu odpowiedniego dla Twojej organizacji. Wszystkie te elementy pojawiają się na tym ekranie jednocześnie. Jeśli masz pytania dotyczące sposobu używania aplikacji w Twojej organizacji, skontaktuj się z działem pomocy technicznej Twojej firmy, korzystając z informacji kontaktowych zawartych w [witrynie internetowej aplikacji Portal firmy](https://portal.manage.microsoft.com#HelpDeskDialog) w celu uzyskania dodatkowych informacji.

12.  Postępuj zgodnie z monitami o wprowadzenie numeru PIN lub hasła. Jeśli skonfigurowano już numer PIN lub hasło na tym urządzeniu, ten ekran nie będzie widoczny lub wymagane będzie wprowadzenie nowego numeru PIN lub hasła.

    ![Wprowadzanie numeru PIN lub hasła](./media/and-enroll-6-PIN-native.png)

13.  Jeśli korzystasz z urządzenia z systemem Samsung KNOX, naciśnij pozycję **Potwierdź**. Zostanie wyświetlony komunikat potwierdzający zarejestrowanie urządzenia. Jeśli korzystasz z urządzenia z natywnym systemem Android, zobaczysz poniższy ekran pokazujący, że urządzenie jest rejestrowane.

    ![Zasady ochrony prywatności systemu Samsung Knox](./media/and-enroll-7-knox-privacy-policy.png)

    Ten ekran pokazuje, że urządzenie jest rejestrowane.

    ![Ekran rejestracji urządzenia](./media/and-enroll-8-device-enrolling.png)

14. Po wyświetleniu ekranu **Konfiguracja dostępu do zasobów firmy** naciśnij przycisk **KONTYNUUJ**. Jeśli komunikat informuje o niezgodności urządzenia, wykonaj instrukcje rozwiązania problemu, a następnie naciśnij pozycję **KONTYNUUJ**.

    ![Urządzenie nie jest zgodne, ale jest zarejestrowane](/intune/media/android_cp_enroll_05_post_1709.png)

    ![Wyświetlane są problemy ze zgodnością urządzenia wymagające rozwiązania](/intune/media/android_cp_enroll_03_post_1709.png)

    Można dowiedzieć się więcej o problemach, naciskając je.

    ![Rozwinięte informacje o problemach ze zgodnością urządzeń](/intune/media/android_cp_enroll_04_post_1709.png)

    ![Ekran konfigurowania dostępu do zasobów firmy](./media/and-enroll-9d-comp-access-setup.png)  

15. Na ekranie **Zakończono konfigurowanie dostępu do zasobów firmy** naciśnij przycisk **GOTOWE**. Urządzenie jest teraz zarejestrowane.

    ![Ekran Konfigurowanie dostępu do zasobów firmy zostało zakończone](./media/and-enroll-10-comp-access-setup-complete.png)

Zanim spróbujesz zainstalować aplikacje firmowe, przejdź kolejno do pozycji **Ustawienia** &gt; **Zabezpieczenia** i włącz opcję **Nieznane źródła**. Jeśli nie włączysz tej opcji przed próbą zainstalowania aplikacji, zostanie wyświetlony następujący komunikat: „Zablokowano instalację. Ze względów bezpieczeństwa Twoje urządzenie zostało ustawione w celu blokowania instalacji aplikacji uzyskanych z nieznanych źródeł”. W oknie dialogowym komunikatu o błędzie możesz nacisnąć pozycję **Ustawienia**, aby przejść do opcji **Nieznane źródła**.

> [!Note]
> Jeśli Twoja organizacja korzysta z oprogramowania do zarządzania wydatkami telekomunikacyjnymi, musisz wykonać kilka dodatkowych czynności, zanim urządzenie zostanie w pełni zarejestrowane. Dowiedz się więcej [tutaj](enroll-your-device-with-telecom-expense-management-android.md).

Jeśli podczas próby zarejestrowania urządzenia w usłudze Intune wystąpi błąd, możesz [wysłać błędy rejestracji do działu pomocy technicznej Twojej firmy](send-enrollment-errors-to-your-it-admin-android.md).

Nadal potrzebujesz pomocy? Skontaktuj się z działem pomocy technicznej Twojej firmy (sprawdź [witrynę internetową Portal firmy](https://portal.manage.microsoft.com#HelpDeskDialog), aby uzyskać informacje kontaktowe) lub napisz do <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">zespołu ds. systemu Android w firmie Microsoft</a>.
