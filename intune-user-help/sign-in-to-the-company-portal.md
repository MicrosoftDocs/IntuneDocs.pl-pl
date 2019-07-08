---
title: Jak zalogować się do aplikacji Portal firmy | Microsoft Docs
description: Dowiedz się, jak zalogować się do aplikacji Portal firmy na wielu platformach.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
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
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6bfd8496061b4b3aba2589b73c3e98bce94a5011
ms.sourcegitcommit: 7315fe72b7e55c5dcffc6d87f185f3c2cded9028
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 07/02/2019
ms.locfileid: "67528653"
---
# <a name="sign-in-to-company-portal"></a>Zaloguj się do portalu firmy  

Istnieją trzy sposoby, aby zalogować się do aplikacji Portal firmy:

* Logowanie przy użyciu służbowego adresu e-mail i hasła.  
* Logowanie przy użyciu uwierzytelniania opartego na certyfikatach.  
* Logowanie z innego urządzenia.    


## <a name="sign-in-with-your-email-address-and-password"></a>Logowanie przy użyciu adresu e-mail i hasła
Poniższe kroki pokazują zrzuty ekranu z aplikacji Portal firmy dla systemu iOS.  

1. Otwórz aplikację na urządzeniu i naciśnij pozycję **Sign In**.  

   ![Strona logowania do Portalu firmy z ikoną osoby przed graficzną reprezentacją witryny sieci Web. Poniżej znajduje się tekst „Uzyskuj dostęp do zasobów firmowych i zachowaj ich bezpieczeństwo” oraz przycisk „Zaloguj się”. Link u dołu pozwala uzyskać dostęp do informacji dotyczących polityki prywatności firmy Microsoft oraz sposobu korzystania przez nią z plików cookie.](/intune-user-help/media/cp_ios_aad_signin_after_1804_001.png)



2. Wprowadź swoje **Konto służbowe** i naciśnij przycisk **Dalej**.

   ![Na jednym ekranie użytkownik otrzymuje zwykle monit o podanie samego adresu e-mail, a nie adresu e-mail i hasła.](/intune-user-help/media/cp_ios_aad_signin_after_1804_002.png)

3. Wprowadź hasło, a następnie naciśnij przycisk **Zaloguj się**.

   ![Monit o podanie hasła wyświetla się po zaakceptowaniu podanego adresu e-mail.](/intune-user-help/media/cp_ios_aad_signin_after_1804_003.png)

4. Aplikacja będzie zweryfikować swoje poświadczenia. Po zakończeniu można uzyskać dostępu do zasobów organizacji i instalowanie dostępnych aplikacji.  

   ![Po przeprowadzeniu procesu uwierzytelniania w aplikacji Portal firmy następuje logowanie, którego postęp jest widoczny na pasku ładowania.](/intune-user-help/media/cp_ios_aad_signin_after_1804_004.png)

## <a name="sign-in-with-certificate-based-authentication"></a>Logowanie przy użyciu uwierzytelniania opartego na certyfikatach

1. Otwórz aplikację Portal firmy na urządzeniu.  

2. Wprowadź swoje **konto służbowe**.  

3. Wybierz link **Zaloguj się przy użyciu certyfikatu**.  

4. Wybierz pozycję **Kontynuuj**, aby używać certyfikatu.  

## <a name="sign-in-from-another-device"></a>Logowanie z innego urządzenia

Jeśli firma korzysta z kart inteligentnych, dostęp do komputerów, prawdopodobnie musisz uwierzytelnić, logując się za pomocą innego urządzenia.  

1. Otwórz aplikację Portal firmy na urządzeniu. Upewnij się, że to urządzenie, które będą używane do dostępu do zasobów roboczych.       

1. Wybierz **Zaloguj się za pomocą innego urządzenia**.  

   ![Strona logowania do Portalu firmy wyświetla monit o wprowadzenie adresu e-mail.  Widoczny jest przycisk „Dalej” oraz link „Zaloguj się za pomocą innego urządzenia”. Zawiera również link do strony „Nie możesz uzyskać dostępu do konta?” Link u dołu pozwala uzyskać dostęp do informacji dotyczących polityki prywatności firmy Microsoft oraz sposobu korzystania przez nią z plików cookie.](/intune-user-help/media/cp_ios_aad_signin_after_1804_005.png)

2. Zobaczysz unikatowy, jednorazowy kod pozwalający zalogować się do aplikacji Portal firmy. Skopiuj kod.

   ![Zgodnie z instrukcjami po uzyskaniu unikatowego kodu dostępu należy na komputerze służbowym przejść na stronę https://microsoft.com/devicelogin, a następnie zalogować się, korzystając z kodu.](/intune-user-help/media/cp_ios_aad_signin_after_1804_006.png)

3. Na innym urządzeniu (jedna za pomocą uwierzytelniania), otwórz przeglądarkę i przejdź do [ https://microsoft.com/devicelogin ](https://microsoft.com/devicelogin). Wpisz lub wklej ten kod.  

   ![Zrzut ekranu przedstawiający przeglądarkę użytkownika na komputerze służbowym zamiast aplikacji Portal firmy. Na stronie „Logowanie do urządzenia” zostanie wyświetlony monit o podanie kodu odebranego w aplikacji Portal firmy.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

4. Wybierz __Kontynuuj__ aby umożliwić aplikacji Portal firmy do logowania się na twoim urządzeniu pracy.   

   ![Użytkownik wprowadził w odpowiednim polu swój unikatowy kod, a w witrynie „Logowanie do urządzenia” został wyświetlony monit o potwierdzenie, że aplikacja Portal firmy usługi Intune jest właściwą aplikacją, która ma otrzymać autoryzację do logowania.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

5. Po zweryfikowaniu kodu możesz zamknąć okno.  

   ![Strona potwierdzenia stwierdzająca, że użytkownik zalogował się do aplikacji Portal firmy na urządzeniu i że można już zamknąć tę stronę.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

6. Aplikacja Portal firmy zaloguje Cię na twoim urządzeniu pracy.  

   ![Po przeprowadzeniu procesu uwierzytelniania w aplikacji Portal firmy następuje logowanie, którego przebieg sygnalizuje pasek ładowania.](/intune-user-help/media/cp_ios_aad_signin_after_1804_007.png)

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).  
