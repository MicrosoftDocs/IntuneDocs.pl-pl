---
title: "Rejestrowanie urządzenia z systemem iOS w usłudze Intune | Microsoft Docs"
description: "Opis sposobu rejestrowania urządzenia z systemem iOS w usłudze Intune"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 09/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope: User help
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 975344e5eb773a2bff3a04d11e4e63d167b30b29
ms.sourcegitcommit: 2d67df51af66ec859587b66a6ce3965461601c29
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2017
---
# <a name="enroll-your-ios-device-in-intune"></a>Rejestrowanie urządzenia z systemem iOS w usłudze Intune

Jeśli firma lub szkoła używa usługi Microsoft Intune, możesz zarejestrować urządzenie z systemem iOS, aby uzyskać dostęp do poczty e-mail, plików i innych zasobów firmy. Po zarejestrowaniu urządzeń dział IT może zarządzać zasobami służbowymi i zabezpieczać je, a użytkownicy mogą korzystać z preferowanych urządzeń podczas wykonywania pracy. Aby uzyskać więcej informacji o rejestracji, zobacz [Co się dzieje w przypadku zainstalowania aplikacji Portal firmy i zarejestrowania urządzenia w usłudze Intune?](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)

> [!VIDEO https://channel9.msdn.com/Series/IntuneEnrollment/iOS-Enrollment/player]

> [!NOTE]
> Jeśli próbujesz uzyskać dostęp do firmowej poczty e-mail w aplikacji Mail, prawdopodobnie został wyświetlony monit o objęcie urządzenia zarządzaniem w celu jego zabezpieczenia. Aby uzyskać dostęp do poczty e-mail i innych zasobów firmy na swoim urządzeniu z systemem iOS, postępuj zgodnie z poniższymi instrukcjami.

**Przed rozpoczęciem:**

- Po rozpoczęciu wykonywania czynności upewnij się, że rejestracja została zakończona. Wstrzymywanie przez okres dłuższy niż kilka minut zwykle zatrzymuje proces i będzie wymagać ponownego rozpoczęcia.
- Jeśli rejestracja nie powiedzie się z jakiegoś powodu, musisz powrócić do aplikacji Portal firmy, aby spróbować ponownie.
- Upewnij się, że działa sieć Wi-Fi. W przeciwnym razie rejestracja zakończy się niepowodzeniem.
- Jeśli program Safari jest zablokowany na urządzeniu, odblokuj go. Przeglądarka Safari jest używana w procesie rejestracji urządzenia.


**Aby zarejestrować urządzenie z systemem iOS:**

1.  Wykonaj czynności opisane w artykule [Instalowanie aplikacji Portal firmy usługi Intune i logowanie się do niej](install-and-sign-in-to-the-intune-company-portal-app-ios.md).

2. Na stronie **Konfiguracja dostępu do zasobów firmy** naciśnij przycisk **Rozpocznij**.

    ![ios-enroll-comp-access-setup-begin](./media/ios-enroll-1a-comp-access-setup.png)

3. Na ekranie **Dlaczego warto zarejestrować urządzenie?** przeczytaj, co możesz zrobić po zarejestrowaniu urządzenia, a następnie naciśnij pozycję **Kontynuuj**.

    ![ios-enroll-why-enroll](./media/ios-enroll-1b-why-enroll.png)

  > [!NOTE]
  > Żółte trójkąty nie oznaczają wystąpienia błędu. Te ikony wskazują, że do zakończenia procesu rejestracji pozostało do wykonania kilka czynności.

4. Przejrzyj listę rzeczy, które administrator IT może zobaczyć na Twoim zarejestrowanym urządzeniu i których nie może zobaczyć, a następnie naciśnij pozycję **Kontynuuj**.

    ![ios-enroll-what-it-can-see](./media/ios-enroll-1c-we-care-privacy.png)

5.  Na ekranie **Co teraz** przeczytaj, co będzie się działo podczas rejestrowania, a następnie naciśnij pozycję **Zarejestruj**.

    ![ios-enroll-what-comes-next](./media/ios-enroll-1d-what-comes-next.png)

6.  Na ekranie **Instalacja profilu** naciśnij pozycję **Zainstaluj** i wprowadź hasło, jeśli zostanie wyświetlony monit.

    ![ios-enroll-install-profile](./media/ios-enroll-2-mgt-profile-install.png)

7.  Naciśnij przycisk **Zainstaluj**.

    ![ios-enroll-tap-install](./media/ios-enroll-3-mgt-profile-install-2.png)    

8.  Naciśnij pozycję **Zainstaluj**, aby potwierdzić, że ostrzeżenia zostały przeczytane.

    ![ios-enroll-tap-install-after-warning](./media/ios-enroll-4-warning.png)

9.  Naciśnij pozycję **Zaufanie**.

    ![ios-enroll-tap-trust](./media/ios-enroll-5-trust.png)

10.  Gdy ekran zmieni się, aby pokazać, że instalacja profilu została zakończona, naciśnij przycisk **Gotowe**.

    ![ios-enroll-tap-done](./media/ios-enroll-6-done.png)

    Na ekranie zostanie wyświetlony komunikat „Rejestrowanie urządzenia”.

11.  Gdy zostanie wyświetlony komunikat z pytaniem o otwarcie strony portalu firmy, naciśnij przycisk **Otwórz**.

    ![ios-enroll-open-comp-portal](./media/ios-enroll-7-open-cp.png)

12. Na ekranie **Konfigurowanie dostępu do zasobów firmy** naciśnij przycisk **Kontynuuj**. Ten ekran pokazuje inne wymagania, które mogą być konieczne do zrealizowania w celu zapewnienia zgodności urządzenia, np. ustawienie hasła. Postępuj zgodnie z wyświetlanymi instrukcjami aż do spełnienia wszystkich wymogów zgodności. Po zakończeniu nastąpi powrót do ekranu Konfiguracja dostępu do zasobów firmy. Naciśnij przycisk **Kontynuuj**.

    ![ios-enroll-comp-access-tap-continue](./media/ios-enroll-8-comp-access-setup-compliance.png)

13. Naciśnij pozycję **Gotowe**.

    ![ios-enroll-tap-done](./media/ios-enroll-9-comp-access-setup-complete.png)

Urządzenie zostanie zarejestrowane w usłudze Intune. Użytkownik zostanie przeniesiony z powrotem do aplikacji Portal firmy.

> [!Note]
> Pozostało kilka kroków do zakończenia rejestracji urządzenia. Dowiedz się więcej o [rejestrowaniu urządzenia przy użyciu zarządzania kosztami telekomunikacyjnymi](enroll-your-device-with-telecom-expense-management-ios.md). Jeśli organizacja korzysta z programu Device Enrollment Program firmy Apple, dowiedz się więcej [tutaj](enroll-your-device-dep-ios.md).

Nadal potrzebujesz pomocy? Skontaktuj się z administratorem IT. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](http://portal.manage.microsoft.com).
