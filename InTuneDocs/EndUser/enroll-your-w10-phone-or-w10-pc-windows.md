---
title: "Rejestrowanie urządzenia z systemem Windows 10 w usłudze Intune | Microsoft Intune"
description: "Opis sposobu rejestrowania urządzenia przenośnego lub stacjonarnego z systemem Windows 10 w usłudze Intune"
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 36250832-c6fd-4e8d-b681-de735023ebc3
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9e0321b23bbbaaa16c28c23e56b5fbcaee0d3c24
ms.openlocfilehash: 75f19a1c613b2d018e0cb89862f15aa4be2bc138


---


# Rejestrowanie urządzenia z systemem Windows 10 Mobile lub Windows 10 Desktop w usłudze Intune

Jeśli firma lub szkoła używa usługi Microsoft Intune, możesz zarejestrować urządzenia, aby uzyskać dostęp do poczty e-mail, plików i innych zasobów firmy. Rejestracja urządzenia umożliwia organizacji ochronę danych firmowych. Aby uzyskać więcej informacji o rejestracji, zobacz [Co się dzieje w przypadku zainstalowania aplikacji Portal firmy i zarejestrowania urządzenia w usłudze Intune?](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows.md) i [Lista rzeczy, jakie administrator IT może zobaczyć na Twoim urządzeniu i jakich nie może](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md).


Aby zarejestrować urządzenie z systemem Windows 10 Mobile lub Windows 10 Desktop:

1.  Przejdź do pozycji **Ustawienia** systemu Windows i naciśnij pozycję **Konta**.

    ![Ustawienia systemu Windows](./media/w10-enroll-rs1-settings-accounts.png)

2.  Przyjrzyj się obu ekranom i zastanów się, który z nich przypomina zawartość ekranu urządzenia. Wykonaj kroki odnoszące się do ekranu przypominającego ekran urządzenia.

    Jeśli widzisz ten ekran, postępuj zgodnie z instrukcjami opisanymi w artykule [Czynności w przypadku wyświetlenia ekranu Dostęp do zasobów służbowych](#steps-to-follow-if-you-see-access-work-or-school).

    ![Połącz z miejscem pracy lub szkołą](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    Jeśli widzisz ten ekran, postępuj zgodnie z instrukcjami opisanymi w artykule [Czynności w przypadku wyświetlenia ekranu Konto użytkownika](#steps-to-follow-if-you-see-your-account).

    ![Twoje konto](./media/w10-enroll-2-accounts-your-account.png)

## Czynności w przypadku wyświetlenia ekranu Dostęp do zasobów służbowych

1.  Naciśnij opcję **Uzyskaj dostęp do miejsca pracy lub nauki**, a następnie naciśnij opcję **Połącz**.

    ![Wybierz pozycję Konto służbowe](./media/w10-enroll-rs1-connect-to-work-or-school.png)

2.  Wprowadź służbowy adres e-mail, a następnie naciśnij przycisk **Dalej**.

    ![Wprowadź dane konta służbowego](./media/w10-enroll-rs1-set-up-work-or-school-account.png)

3. Zaloguj się do usługi Intune przy użyciu konta służbowego.

    ![Dodaj konto służbowe](./media/w10-enroll-rs1-enter-your-credentials.png)

    Pojawi się komunikat informujący o tym, że firma lub szkoła rejestruje urządzenie.

4. Po wyświetleniu strony **Wszystko jest gotowe!** wybierz opcję **Zamknij**. To wszystko.

  ![Po wyświetleniu ekranu „Wszystko jest gotowe!” wybierz opcję Zamknij](./media/w10-enroll-rs1-youre-all-set.png)

5. Jeśli chcesz się upewnić, że połączenie jest prawidłowo skonfigurowane, wróć do obszaru **Ustawienia** i sprawdź, czy konto służbowe znajduje się na liście.

    ![Sprawdź, czy połączenie zostało poprawnie skonfigurowane](./media/w10-enroll-rs1-validate-successful-enrollment.png)

Jeśli powyższe kroki zostały wykonane, ale nadal nie można uzyskać dostępu do służbowego konta e-mail i plików, wykonaj czynności opisane w części [Rozwiązywanie problemów w przypadku wyświetlenia ekranu Dostęp do zasobów służbowych](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).


## Czynności w przypadku wyświetlenia ekranu Konto użytkownika

1.  Przejdź do pozycji **Ustawienia** systemu Windows, a następnie naciśnij pozycję **Konta**.

    ![Przejdź do pozycji Ustawienia i Konta](./media/W10-enroll-1-settings-accounts.png)

2.  Naciśnij pozycję **Twoje konto**.

    ![Naciśnij pozycję Twoje konto](./media/W10-enroll-2-accounts-your-account.png)

3.  Naciśnij pozycję **Dodaj konto służbowe**.

    ![Naciśnij pozycję Dodaj konto służbowe](./media/w10-enroll-3-add-work-school-acct.png)

4.  Zaloguj się przy użyciu poświadczeń konta służbowego.

    ![sign-in](./media/W10-enroll-4-sign-in.png)

Jeśli poprzednie kroki zostały wykonane, ale nadal nie można uzyskać dostępu do służbowego adresu e-mail, plików lub innych danych, wykonaj instrukcje opisane w części [Rozwiązywanie problemów w przypadku wyświetlenia ekranu Konto użytkownika](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-your-account).

Zalecane jest również zainstalowanie aplikacji Portal firmy, dzięki której możesz łatwo znaleźć i uzyskać aplikacje firmowe związane z Tobą i Twoim stanowiskiem. W zależności od tego, jak usługa Intune została skonfigurowana w firmie, aplikacja Portal firmy może zostać zainstalowana w ramach procesu rejestracji.

Aby sprawdzić, czy masz tę aplikację, poszukaj nazwy **Portal firmy** na liście aplikacji. Jeśli lista nie zawiera aplikacji Portal firmy, wykonaj następujące kroki, aby ją zainstalować.

1.  Naciśnij kolejno pozycje **Start** &gt; **Sklep**.

2.  Naciśnij pozycję **Wyszukaj** i wpisz **portal firmy**.

3.  Na liście wyników naciśnij kolejno pozycje **Portal firmy** &gt; **Zainstaluj**.

4.  Naciśnij pozycję **Zainstaluj** lub **Bezpłatne**. Wyświetlana opcja zależy od konfiguracji aplikacji w firmie.

Nadal potrzebujesz pomocy? Skontaktuj się z administratorem IT. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](http://portal.manage.microsoft.com).





<!--HONumber=Oct16_HO1-->


