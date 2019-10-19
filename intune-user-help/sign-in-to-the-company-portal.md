---
title: Jak zalogować się do aplikacji Portal firmy | Microsoft Docs
description: Dowiedz się, jak zalogować się do aplikacji Portal firmy na wielu platformach.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 09/18/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: cfd214bc-f072-4808-af2e-a3cbf7af9bca
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 68a44027c14e0a52d72fc032a6ab42413fa8df96
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72508304"
---
# <a name="sign-in-to-company-portal"></a>Zaloguj się do Portal firmy  

Istnieją trzy sposoby logowania się do aplikacji Portal firmy:

* Logowanie przy użyciu służbowego adresu e-mail i hasła.  
* Logowanie przy użyciu uwierzytelniania opartego na certyfikatach.  
* Logowanie z innego urządzenia.    


## <a name="sign-in-with-your-email-address-and-password"></a>Logowanie przy użyciu adresu e-mail i hasła
Poniższe kroki pokazują zrzuty ekranu z Portal firmy dla systemu iOS.  

1. Otwórz aplikację na urządzeniu i naciśnij pozycję **Zaloguj się**.  

   [![Example zrzut ekranu strony logowania Portal firmy. ](/intune-user-help/media/intune-ios-cp-signin-1908.png)](/intune-user-help/media/intune-ios-cp-signin-lightbox-1908.png#lightbox)  


2. Wprowadź swoje **Konto służbowe** i naciśnij przycisk **Dalej**.

   ![Na jednym ekranie użytkownik otrzymuje zwykle monit o podanie samego adresu e-mail, a nie adresu e-mail i hasła.](/intune-user-help/media/cp_ios_aad_signin_after_1804_002.png)

3. Wprowadź hasło, a następnie naciśnij przycisk **Zaloguj się**.

   ![Monit o podanie hasła wyświetla się po zaakceptowaniu podanego adresu e-mail.](/intune-user-help/media/cp_ios_aad_signin_after_1804_003.png)

4. Aplikacja sprawdzi Twoje poświadczenia. Po wykonaniu tych czynności możesz uzyskać dostęp do zasobów organizacji i zainstalować dostępne aplikacje.  

   ![Po przeprowadzeniu procesu uwierzytelniania w aplikacji Portal firmy następuje logowanie, którego postęp jest widoczny na pasku ładowania.](/intune-user-help/media/cp_ios_aad_signin_after_1804_004.png)

## <a name="sign-in-with-certificate-based-authentication"></a>Logowanie przy użyciu uwierzytelniania opartego na certyfikatach

1. Otwórz aplikację Portal firmy na urządzeniu.  

2. Wprowadź swoje **konto służbowe**.  

3. Wybierz link **Zaloguj się przy użyciu certyfikatu**.  

4. Wybierz pozycję **Kontynuuj**, aby używać certyfikatu.  

## <a name="sign-in-from-another-device"></a>Logowanie z innego urządzenia

Jeśli firma używa kart inteligentnych do uzyskiwania dostępu do komputerów, prawdopodobnie trzeba będzie uwierzytelnić się, logując się z innego urządzenia.  

1. Otwórz aplikację Portal firmy na urządzeniu. Upewnij się, że jest to urządzenie, za pomocą którego będziesz uzyskiwać dostęp do zasobów służbowych.       

1. Wybierz pozycję **Zaloguj się za pomocą innego urządzenia**.  

   ![Strona logowania do Portalu firmy wyświetla monit o wprowadzenie adresu e-mail.  Widoczny jest przycisk „Dalej” oraz link „Zaloguj się za pomocą innego urządzenia”. Zawiera również link do strony „Nie możesz uzyskać dostępu do konta?” Link u dołu pozwala uzyskać dostęp do informacji dotyczących polityki prywatności firmy Microsoft oraz sposobu korzystania przez nią z plików cookie.](/intune-user-help/media/cp_ios_aad_signin_after_1804_005.png)

2. Zobaczysz unikatowy, jednorazowy kod pozwalający zalogować się do aplikacji Portal firmy. Skopiuj kod.

   ![Zgodnie z instrukcjami po uzyskaniu unikatowego kodu dostępu należy na komputerze służbowym przejść na stronę https://microsoft.com/devicelogin, a następnie zalogować się, korzystając z kodu.](/intune-user-help/media/cp_ios_aad_signin_after_1804_006.png)

3. Na innym urządzeniu (używanym do uwierzytelniania) Otwórz przeglądarkę i przejdź do [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin). Wprowadź lub wklej kod.  

   ![Zrzut ekranu przedstawiający przeglądarkę użytkownika na komputerze służbowym zamiast aplikacji Portal firmy. Na stronie „Logowanie do urządzenia” zostanie wyświetlony monit o podanie kodu odebranego w aplikacji Portal firmy.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

4. Wybierz pozycję __Kontynuuj__ , aby zezwolić Portal firmy na logowanie się na urządzeniu służbowym.   

   ![Użytkownik wprowadził w odpowiednim polu swój unikatowy kod, a w witrynie „Logowanie do urządzenia” został wyświetlony monit o potwierdzenie, że aplikacja Portal firmy usługi Intune jest właściwą aplikacją, która ma otrzymać autoryzację do logowania.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

5. Po zweryfikowaniu kodu możesz zamknąć okno.  

   ![Strona potwierdzenia stwierdzająca, że użytkownik zalogował się do aplikacji Portal firmy na urządzeniu i że można już zamknąć tę stronę.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

6. Aplikacja Portal firmy loguje Cię na urządzeniu służbowym.  

   ![Po przeprowadzeniu procesu uwierzytelniania w aplikacji Portal firmy następuje logowanie, którego przebieg sygnalizuje pasek ładowania.](/intune-user-help/media/cp_ios_aad_signin_after_1804_007.png)

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).  
