---
title: "Rejestrowanie urządzenia z systemem Android w usłudze Intune | Microsoft Intune"
description: "Opis sposobu rejestrowania urządzenia z systemem Android w usłudze Intune"
keywords: 
author: barlan
ms.author: barlan
manager: angrobe
ms.date: 09/09/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7eefcefa5e1cd0f789c77bf020c256e449099273
ms.openlocfilehash: 5d7507d9c09867b5c302caba409f1a7347fae4b6


---


# Rejestrowanie urządzenia z systemem Android w usłudze Intune

Jeśli firma lub szkoła używa usługi Microsoft Intune, możesz zarejestrować urządzenie z systemem Android, aby uzyskać dostęp do poczty e-mail, plików i innych zasobów firmy. Po zarejestrowaniu urządzeń dział IT może zarządzać zasobami służbowymi i zabezpieczać je, a użytkownicy mogą korzystać z preferowanych urządzeń podczas wykonywania pracy. Aby uzyskać więcej informacji o rejestracji, zobacz [Co się stanie, jeśli zainstaluję aplikację Portal firmy i zarejestruję swoje urządzenie?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-android.md).

Te instrukcje dotyczące rejestracji są przeznaczone dla urządzeń z systemem Android Samsung Knox i „natywnych” urządzeń z systemem Android (innych niż Samsung Knox). Aby sprawdzić, czy masz urządzenie Samsung Knox, przejdź do pozycji **Ustawienia** &gt; **Informacje o urządzeniu**. Jeśli na tej liście nie widzisz pozycji „KNOX version” (Wersja systemu KNOX), oznacza to, że masz urządzenie z natywnym systemem Android.

Przed zarejestrowaniem lub po nim może pojawić się monit o wybranie kategorii, która najlepiej opisuje Twój sposób korzystania z urządzenia. Administrator IT używa tej kategorii, aby pomóc sprawdzić aplikacje, do których masz dostęp.

Jeśli podczas próby zarejestrowania urządzenia w usłudze Intune wystąpi błąd, możesz [wysłać błędy rejestracji do administratora IT](send-enrollment-errors-to-your-it-administrator-android.md).

**Aby zarejestrować urządzenie z systemem Android:**

1.  Zainstaluj bezpłatną aplikację Portal firmy usługi Intune ze sklepu [Google Play](http://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal).

2.  Otwórz aplikację Portal firmy usługi Microsoft Intune.

3.  Na **ekranie powitalnym** Portalu firmy naciśnij przycisk **Zaloguj**, a następnie zaloguj się przy użyciu swojego konta służbowego.

    ![android-company-portal-sign-in](./media/and-enroll-0-welcome-screen.png)   

4.  Jeśli administrator IT skonfigurował firmowe warunki i postanowienia, naciśnij przycisk **AKCEPTUJ**, aby zaakceptować postanowienia.

    ![android-company-portal-sign-in](./media/and-enroll-3-accept-terms.png)

5.  Zaloguj się w aplikacji Portal firmy, podając służbowe konto i hasło, a następnie naciśnij pozycję **Zaloguj**.

    ![android-company-portal-sign-in](./media/and-enroll-2-cp-sign-in.png)

6.  Na ekranie **Konfiguracja dostępu do zasobów firmy** naciśnij przycisk **ROZPOCZNIJ**.

    ![Ekran konfigurowania dostępu do zasobów firmy](./media/and-enroll-4a-comp-access-setup.png)

7.  Na ekranie **Dlaczego warto zarejestrować urządzenie?** przeczytaj, co możesz zrobić po zarejestrowaniu urządzenia, a następnie naciśnij pozycję **KONTYNUUJ**.

    ![Ekran „Dlaczego warto zarejestrować urządzenie?”](./media/and-enroll-4b-why-enroll.png)

8.  Przejrzyj listę rzeczy, które administrator IT może zobaczyć na Twoim urządzeniu i których nie może zobaczyć, a następnie naciśnij pozycję **KONTYNUUJ**.

    ![Ustawienia prywatności](./media/and-enroll-4c-we-care-privacy.png)

9.  Na ekranie **Co teraz** przeczytaj, co będzie się działo podczas rejestrowania, a następnie naciśnij przycisk **ZAREJESTRUJ**.

    ![Ekran Co teraz](./media/and-enroll-4d-what-comes-next.png)

10.  Wykonaj ten krok, jeśli używasz systemu Android w wersji 6.0 lub nowszej. W przeciwnym razie przejdź do następnego kroku.

    Jeśli administrator IT skonfigurował pewne zasady, mogą pojawić się następujące komunikaty:
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

12.  Postępuj zgodnie z monitami o wprowadzenie numeru PIN lub hasła. Jeśli skonfigurowano już numer PIN lub hasło na tym urządzeniu, ten ekran nie będzie widoczny lub wymagane będzie wprowadzenie nowego numeru PIN lub hasła.

    ![Wprowadzanie numeru PIN lub hasła](./media/and-enroll-6-PIN-native.png)

13.  Jeśli korzystasz z urządzenia z systemem Samsung KNOX, naciśnij pozycję **Potwierdź**. Zostanie wyświetlony komunikat potwierdzający zarejestrowanie urządzenia. Jeśli korzystasz z urządzenia z natywnym systemem Android, zobaczysz poniższy ekran pokazujący, że urządzenie jest rejestrowane.

    ![Zasady ochrony prywatności systemu Samsung KNOX](./media/and-enroll-7-knox-privacy-policy.png)

    Ten ekran pokazuje, że urządzenie jest rejestrowane.

    ![Ekran rejestracji urządzenia](./media/and-enroll-8-device-enrolling.png)

14. Po wyświetleniu ekranu **Konfiguracja dostępu do zasobów firmy** naciśnij przycisk **KONTYNUUJ**. Jeśli komunikat informuje o niezgodności urządzenia, wykonaj instrukcje rozwiązania problemu, a następnie naciśnij pozycję **KONTYNUUJ**.

    ![Ekran konfigurowania dostępu do zasobów firmy](./media/and-enroll-9-comp-access-setup.png)  

11. Na ekranie **Zakończono konfigurowanie dostępu do zasobów firmy** naciśnij przycisk **GOTOWE**. Urządzenie jest teraz zarejestrowane.

    ![Ekran Konfigurowanie dostępu do zasobów firmy zostało zakończone](./media/and-enroll-10-comp-access-setup-complete.png)

Zanim spróbujesz zainstalować aplikacje firmowe, przejdź kolejno do pozycji **Ustawienia** &gt; **Zabezpieczenia** i włącz opcję **Nieznane źródła**. Jeśli nie włączysz tej opcji przed próbą zainstalowania aplikacji, zostanie wyświetlony następujący komunikat: „Zablokowano instalację. Ze względów bezpieczeństwa Twoje urządzenie zostało ustawione w celu blokowania instalacji aplikacji uzyskanych z nieznanych źródeł”. W oknie dialogowym komunikatu o błędzie możesz nacisnąć pozycję **Ustawienia**, aby przejść do opcji **Nieznane źródła**.

Nadal potrzebujesz pomocy? Skontaktuj się z administratorem IT (sprawdź [witrynę sieci Web Portal firmy](http://portal.manage.microsoft.com), aby uzyskać informacje kontaktowe) lub napisz do zespołu ds. systemu Android firmy Microsoft: wintunedroidfbk@microsoft.com.



<!--HONumber=Oct16_HO2-->


