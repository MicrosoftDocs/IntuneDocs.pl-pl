---
title: Jak zalogować się do aplikacji Portal firmy | Microsoft Docs
description: Dowiedz się, jak zalogować się do aplikacji Portal firmy na wielu platformach.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: cfd214bc-f072-4808-af2e-a3cbf7af9bca
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 84f8e70d8321ca27d689d13472b69007a1d6c186
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31019232"
---
# <a name="how-do-i-sign-in-to-the-company-portal-app---user-story-1132123--"></a>Jak zalogować się do aplikacji Portal firmy? <!--User Story 1132123-->

Aplikacja Portal firmy służy do uzyskiwania dostępu do zasobów firmy, takich jak poczta e-mail i aplikacje biznesowe. Istnieją dwa główne sposoby logowania się do aplikacji Portal firmy:

* Logowanie za pomocą służbowego adresu e-mail i hasła
* Logowanie z innego urządzenia

Chociaż poniższe ilustracje przedstawiają system iOS, proces jest w zasadzie taki sam dla urządzeń z systemami Android i Windows.

## <a name="signing-in-with-your-email-address-and-password"></a>Logowanie się przy użyciu adresu e-mail i hasła

1. Otwórz aplikację Portal firmy na urządzeniu i naciśnij pozycję **Zaloguj się**.

   ![Strona logowania do Portalu firmy z ikoną osoby przed graficzną reprezentacją witryny sieci Web. Poniżej znajduje się tekst „Uzyskaj dostęp do zasobów firmy i zabezpiecz je” oraz przycisk „Zaloguj się”. Link u dołu pozwala uzyskać dostęp do informacji dotyczących polityki prywatności firmy Microsoft oraz sposobu korzystania przez nią z plików cookie.](/intune-user-help/media/cp_ios_aad_signin_after_1804_001.png)

   Nie masz aplikacji Portal firmy? Dowiedz się, jak ją pobrać i zainstalować w systemach [iOS](install-and-sign-in-to-the-intune-company-portal-app-ios.md) i [Android](install-the-company-portal-app-android.md).

2. Wprowadź swoje **Konto służbowe** i naciśnij przycisk **Dalej**.

   ![Na jednym ekranie użytkownik otrzymuje zwykle monit o podanie samego adresu e-mail, a nie adresu e-mail i hasła.](/intune-user-help/media/cp_ios_aad_signin_after_1804_002.png)

3. Wprowadź hasło, a następnie naciśnij przycisk **Zaloguj się**.

   ![Monit o podanie hasła wyświetla się po zaakceptowaniu podanego adresu e-mail.](/intune-user-help/media/cp_ios_aad_signin_after_1804_003.png)

4. Gdy aplikacja Portal firmy zaakceptuje Twoje dane logowania, zaloguje Cię i uzyskasz dostęp do zasobów firmy.   

   ![Po przeprowadzeniu procesu uwierzytelniania w aplikacji Portal firmy następuje logowanie, którego postęp sygnalizuje pasek ładowania.](/intune-user-help/media/cp_ios_aad_signin_after_1804_004.png)

## <a name="signing-in-with-certificate-based-authentication"></a>Logowanie przy użyciu uwierzytelniania opartego na certyfikatach

1.  Otwórz aplikację Portal firmy na urządzeniu.

2.  Wprowadź swoje **konto służbowe**.

3.  Wybierz link **Zaloguj się przy użyciu certyfikatu**.

4.  Wybierz pozycję **Kontynuuj**, aby używać certyfikatu.

## <a name="signing-in-from-another-device"></a>Logowanie z innego urządzenia

Jeśli nie używasz hasła do logowania się do zasobów Twojej firmy, do potwierdzania, że jesteś odpowiednią osobą z właściwymi poziomami dostępu, możesz używać innego urządzenia. Jeśli w Twojej firmie do uzyskiwania dostępu do komputerów używane są karty inteligentne, prawdopodobnie musisz zalogować się za pomocą innego urządzenia.

1. Zamiast wprowadzać adres e-mail, wybierz link **Zaloguj się za pomocą innego urządzenia** pod polem tekstowym adresu e-mail.

   ![Strona logowania do Portalu firmy wyświetli monit o wprowadzenie adresu e-mail.  Poniżej znajduje się przycisk „Dalej” oraz link „Zaloguj się z innego urządzenia”. Zawiera również link do strony „Nie możesz uzyskać dostępu do konta?” Link u dołu pozwala uzyskać dostęp do informacji dotyczących polityki prywatności firmy Microsoft oraz sposobu korzystania przez nią z plików cookie.](/intune-user-help/media/cp_ios_aad_signin_after_1804_005.png)

2. Zobaczysz unikatowy, jednorazowy kod pozwalający zalogować się do aplikacji Portal firmy.

   ![Zgodnie z instrukcjami po uzyskaniu unikatowego kodu dostępu należy na komputerze służbowym przejść na stronę https://microsoft.com/devicelogin, a następnie zalogować się, korzystając z kodu.](/intune-user-help/media/cp_ios_aad_signin_after_1804_006.png)

3. Otwórz przeglądarkę na innym urządzeniu i przejdź pod adres [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin) w celu wprowadzenia kodu.

   ![Zrzut ekranu przedstawiający przeglądarkę użytkownika na komputerze służbowym zamiast aplikacji Portal firmy. Na stronie „Logowanie do urządzenia” zostanie wyświetlony monit o podanie kodu odebranego w aplikacji Portal firmy.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

4. Gdy strona **Logowanie z urządzenia** zweryfikuje kod, wybierz pozycję __Kontynuuj__, aby zezwolić aplikacji Portal firmy na zalogowanie na Twoim innym urządzeniu.

   ![Użytkownik wprowadził w odpowiednim polu swój unikatowy kod, a w witrynie „Logowanie do urządzenia” został wyświetlony monit o potwierdzenie, że aplikacja Portal firmy usługi Intune jest właściwą aplikacją, która ma otrzymać autoryzację do logowania.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

5. Po zweryfikowaniu kodu możesz zamknąć okno.

   ![Strona potwierdzenia stwierdzająca, że użytkownik zalogował się do aplikacji Portal firmy na urządzeniu i że można już zamknąć tę stronę.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

6. Aplikacja Portal firmy na pierwotnym urządzeniu rozpocznie logowanie.

   ![Po przeprowadzeniu procesu uwierzytelniania w aplikacji Portal firmy następuje logowanie, którego przebieg sygnalizuje pasek ładowania.](/intune-user-help/media/cp_ios_aad_signin_after_1804_007.png)

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://portal.manage.microsoft.com#HelpDeskDialog).
