---
title: "Rozwiązywanie problemów dotyczących integracji z aplikacją Lookout | Microsoft Docs"
description: "W tym temacie opisano rozwiązywanie często występujących problemów dotyczących integracji z aplikacją Lookout"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbe0b5f4-b8bc-49f3-85a9-51fb2f226fca
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 80e96003c584c67cb6b0289a7e2ed1ff3a833c2c
ms.openlocfilehash: 076fbc5e2c73a7c6d5a17130f477a840c3c4ed19


---

# <a name="troubleshoot-lookout-integration-with-intune"></a>Rozwiązywanie problemów dotyczących integracji aplikacji Lookout z usługą Intune
W tym temacie opisano niektóre typowe problemy, które mogą występować w konfiguracji aplikacji Lookout MTP (Mobile Threat Protection).

**Błędy logowania**

## <a name="403-errors"></a>Błędy 403
Podczas logowania się do [konsoli Lookout MTP](https://aad.lookout.com) jest wyświetlany błąd 403: **nie masz autoryzacji dostępu do usługi**. Może się to zdarzyć, gdy podana nazwa użytkownika nie jest członkiem grupy usługi Azure Active Directory (AD) skonfigurowanej do uzyskiwania dostępu do aplikacji Lookout MTP.

Aplikacja Lookout MTP umożliwia dostęp do usługi tylko użytkownikom w skonfigurowanej grupie Azure AD. Aby sprawdzić, która grupa ma skonfigurowany dostęp do aplikacji Lookout MTP, skontaktuj się z pomocą techniczną aplikacji Lookout:

* Poczta e-mail: enterprisesupport@lookout.com
* Zaloguj się do [konsoli MTP](http://aad.lookout.com) i przejdź do modułu **Pomoc techniczna**.
* Przejdź do strony:  https://enterprise.support.lookout.com/hc/en-us/requests i utwórz żądanie pomocy technicznej.

## <a name="unable-to-sign-in"></a>Nie można się zalogować
Poniższy błąd występuje w sytuacji, gdy użytkownik będący administratorem globalnym usługi Azure AD nie zaakceptował początkowej konfiguracji aplikacji Lookout.

![zrzut ekranu przedstawiający ekran logowania do aplikacji Lookout z wyświetlonym błędem logowania](../media/mtp/lookout-mtp-consent-not-accepted-error.png)

Aby rozwiązać ten problem, użytkownik będący administratorem globalnym musi się zalogować na stronie https://aad.lookout.com/les?action=consent i zaakceptować monit o zainicjowanie konfiguracji. Bardziej szczegółowe informacje podano w temacie [Konfigurowanie subskrypcji przy użyciu aplikacji Lookout MTP](../deploy-use/set-up-your-subscription-with-lookout-mtp.md)

**Problemy ze stanem urządzenia**

## <a name="device-missing-from-lookout-device-list"></a>Brak urządzenia na liście urządzeń w aplikacji Lookout

Taki problem może wystąpić w jednej z następujących sytuacji:
* Użytkownik urządzenia nie należy do **grupy rejestracji** określonej w **konsoli Lookout MTP**.  W [konsoli Lookout](http://aad.lookout.com) wybierz pozycję **System** > **Łącznik usługi Intune** > **Zarządzanie rejestracją**.  Przejrzyj grupy usługi Azure AD skonfigurowane na potrzeby rejestracji i sprawdź, czy użytkownik urządzenia należy do jednej z grup usługi Azure AD.  Po dodaniu użytkownika do grupy rejestracji czas potrzebny do wyświetlenia urządzenia w module **Urządzenia** konsoli Lookout MTP może wynosić nawet tyle, co skonfigurowany interwał sondowania (wartość domyślna to 5 minut).
* Jeśli urządzenie jest nieobsługiwane przez aplikację Lookout MTP.  Urządzenia nieobsługiwane będą wyświetlane w sekcji **Zarządzane urządzenia** ustawień łącznika w konsoli Lookout MTP.

### <a name="device-reported-as-pending"></a>Urządzenie jest zgłaszane jako **Oczekujące**

Urządzenie jest wyświetlane ze stanem **Oczekujące**, jeśli użytkownik końcowy nie otworzył aplikacji Lookout for Work i nie nacisnął przycisku **Aktywuj**. Dodatkowe szczegóły dotyczące aktywacji urządzenia przy użyciu aplikacji Lookout for Work zawierają tematy [Pojawia się monit o zainstalowanie aplikacji Lookout for Work na urządzeniu z systemem Android](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android) oraz [Pojawia się monit o zainstalowanie aplikacji Lookout for Work na urządzeniu z systemem iOS](https://docs.microsoft.com/en-us/intune/enduser/you-are-prompted-to-install-lookout-for-work-ios)

## <a name="device-whos-active-but-has-no-device-id"></a>Urządzenie jest aktywne, ale nie ma identyfikatora urządzenia
Jeśli aktywne urządzenie nie ma identyfikatora urządzenia w konsoli Lookout MTP, użytkownik urządzenia nie znajduje się w grupie rejestracji. Urządzenie może przejść do tego stanu w sytuacji, gdy użytkownik urządzenia został usunięty z grupy rejestracji lub gdy grupa rejestracji została usunięta.

W [konsoli Lookout](http://aad.lookout.com) wybierz pozycję **System** > **Łącznik usługi Intune** > **Rejestracja** i przejrzyj ustawienia.  Przejrzyj grupy usługi Azure AD i sprawdź, czy użytkownik urządzenia należy do jednej z grup usługi Azure AD.

Gdy urządzenie jest w tym stanie, aplikacja Lookout będzie stale powiadamiać użytkownika o wszelkich wykrytych zagrożeniach, ale nie będzie wysyłać żadnych informacji o zagrożeniach do usługi Intune.

## <a name="device-reported-as-disconnected"></a>Urządzenie jest zgłaszane jako **Rozłączone**

Stan **Rozłączone** oznacza, że urządzenie nie zostało zsynchronizowane z aplikacją Lookout MTP w skonfigurowanym interwale (domyślnie jest to 30 dni, a minimalny interwał to 7 dni). Brak aplikacji Portal firmy lub Lookout for Work na urządzeniu. Ponowne zainstalowanie tych aplikacji powinno umożliwić rozwiązanie problemu. Gdy użytkownik otworzy aplikację Lookout for Work i ją aktywuje, urządzenie dokona ponownej synchronizacji z aplikacją Lookout MTP i usługą Intune.    

### <a name="forcing-a-device-sync"></a>Wymuszanie synchronizacji urządzenia
W module **Urządzenia** konsoli Lookout MTP administrator może wybrać urządzenie i zdecydować o jego usunięciu.   Gdy następnym razem właściciel urządzenia otworzy aplikację Lookout for Work i naciśnie pozycję **Aktywuj**, stan urządzenia zostanie w pełni ponownie zsynchronizowany.

## <a name="device-has-a-new-user"></a>Urządzenie ma nowego użytkownika
Należy wyczyścić urządzenie i poprosić nowego użytkownika o rejestrację.  W [konsoli administratora usługi Intune](https://manage.microsoft.com) wybierz urządzenie, kliknij je prawym przyciskiem myszy, a następnie wybierz polecenie **Wycofaj/wyczyść**, aby usunąć to urządzenie z zarządzania. Po wycofaniu urządzenia możesz je usunąć.

![zrzut ekranu przestawiający moduł Urządzenia w konsoli administratora usługi Intune z wyświetloną opcją Wycofaj/wyczyść](../media/mtp/mtp-retire-device-intune-console.png)

Możesz również przejść do modułu **Urządzenia** w [konsoli Lookout](http://aad.lookout.com) i wybrać pozycję **Usuń**.  

Jeśli nowy użytkownik należy do grupy rejestracji Lookout MTP, urządzenie będzie wyświetlane po skojarzeniu go przez usługę Azure AD z nowym użytkownikiem.

## <a name="compliance-remediation-workflows"></a>Przepływy pracy korygowania i zgodności
- [Pojawia się monit o zainstalowanie aplikacji Lookout for Work na urządzeniu z systemem Android]( http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)
- [Należy rozwiązać problem związany z zagrożeniem wykrytym przez aplikację Lookout for Work na urządzeniu z systemem Android](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)
- [Należy rozwiązać problem związany z zagrożeniem wykrytym przez aplikację Lookout for Work na urządzeniu z systemem iOS](https://docs.microsoft.com/en-us/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-ios)


### <a name="see-also"></a>Zobacz także
[Konfigurowanie subskrypcji przy użyciu aplikacji Lookout MTP](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-your-subscription-with-lookout-mtp)



<!--HONumber=Dec16_HO4-->


