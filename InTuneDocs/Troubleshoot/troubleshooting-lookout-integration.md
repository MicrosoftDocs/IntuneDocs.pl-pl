---
title: "Rozwiązywanie problemów dotyczących integracji z aplikacją Lookout | Microsoft Intune"
description: "W tym temacie opisano rozwiązywanie często występujących problemów dotyczących integracji z aplikacją Lookout"
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbe0b5f4-b8bc-49f3-85a9-51fb2f226fca
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9bf5764d1e1bd73fd62e5033b2309fc8d5a912e4
ms.openlocfilehash: aa29f702803d657f783ff0dfc6ea66981484c569


---

# <a name="troubleshoot-lookout-integration-with-intune"></a>Rozwiązywanie problemów dotyczących integracji aplikacji Lookout z usługą Intune
W tym temacie opisano niektóre typowe problemy, które mogą występować w konfiguracji aplikacji Lookout MTP (Mobile Threat Protection).
## <a name="troubleshoot-login-errors"></a>Rozwiązywanie problemów związanych w błędami logowania
### <a name="403-errors"></a>Błędy 403
Błąd 403 może zostać wyświetlony po zalogowaniu się do [konsoli Lookout MTP](https://aad.lookout.com):  **nie masz autoryzacji dostępu do usługi**  Może się to zdarzyć, gdy podana nazwa użytkownika nie jest elementem członkowskim grupy usługi Azure Active Directory (Azure AD) skonfigurowanej do uzyskiwania dostępu do aplikacji Lookout MTP.

Konfiguracja aplikacji Lookout MTP zezwala na dostęp do tej aplikacji tylko użytkownikom ze skonfigurowanej grupy usługi Azure AD. Jeśli nie masz pewności, która grupa ma skonfigurowany dostęp do aplikacji Lookout MTP, skontaktuj się z pomocą techniczną aplikacji Lookout.

Kontakt z pomocą techniczną aplikacji Lookout jest możliwy przy użyciu następujących metod:

* Poczta e-mail: enterprisesupport@lookout.com
* Zaloguj się do [konsoli MTP](http://aad.lookout.com) i przejdź do modułu **Pomoc techniczna**.
* Przejdź do strony:  https://enterprise.support.lookout.com/hc/en-us/requests i utwórz żądanie pomocy technicznej.

### <a name="unable-to-sign-in"></a>Nie można się zalogować
Poniższy błąd może się pojawić w sytuacji, gdy użytkownik będący administratorem globalnym usługi Azure AD nie zaakceptował początkowej konfiguracji aplikacji Lookout.

![zrzut ekranu przedstawiający ekran logowania do aplikacji Lookout z wyświetlonym błędem logowania](../media/mtp/lookout-mtp-consent-not-accepted-error.png)

Aby rozwiązać ten problem, użytkownik będący administratorem globalnym musi się zalogować na stronie https://aad.lookout.com/les?action=consent i zaakceptować monit o zainicjowanie konfiguracji. Bardziej szczegółowe informacje podano w temacie [Konfigurowanie subskrypcji przy użyciu aplikacji Lookout MTP](set-up-your-subscription-with-lookout-mtp.md)

## <a name="troubleshoot-device-status-issues"></a>Rozwiązywanie problemów ze stanem urządzenia

### <a name="device-not-showing-up-in-the-lookout-mtp-console-device-list"></a>Urządzenie nie jest wyświetlane na liście urządzeń w konsoli Lookout MTP

Taki problem może wystąpić w jednej z następujących sytuacji:
* Gdy użytkownik będący właścicielem urządzenia nie należy do **grupy rejestracji** określonej w **konsoli Lookout MTP**.  W module **System** przejdź do karty **Łącznik usługi Intune** i spójrz na ustawienia **Zarządzanie rejestracją**.  Powinna zostać wyświetlona co najmniej jedna grupa usługi Azure AD skonfigurowana na potrzeby rejestracji.  Sprawdź, czy użytkownik będący właścicielem brakującego urządzenia należy do jednej z określonych grup usługi Azure AD.  Po dodaniu nowego użytkownika do grupy rejestracji czas potrzebny do wyświetlenia urządzenia w module **Urządzenia** konsoli Lookout MTP może wynosić nawet tyle, co skonfigurowany interwał sondowania (wartość domyślna to 5 minut).

* Jeśli urządzenie jest nieobsługiwane przez aplikację Lookout MTP.  Urządzenia nieobsługiwane będą wyświetlane w sekcji **Zarządzane urządzenia** ustawień łącznika w konsoli Lookout MTP.

### <a name="device-continues-to-be-reported-as-pending"></a>Urządzenie ciągle jest raportowane jako **oczekujące**

Jeśli urządzenie jest wyświetlone ze stanem **Oczekujące**, oznacza to, że użytkownik nie otworzył aplikacji Lookout for Work i nie nacisnął przycisku **Aktywuj**. Aby uzyskać szczegółowe informacje dotyczące aktywacji urządzeń za pomocą aplikacji Lookout for Work, przeczytaj następujący temat:

[Pojawia się monit o zainstalowanie aplikacji Lookout for Work na urządzeniu z systemem Android ](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

### <a name="in-the-lookout-mtp-console-a-device-is-showing-as-active-but-does-not-have-a-device-id"></a>W konsoli Lookout MTP urządzenie jest wyświetlane jako aktywne, ale nie ma identyfikatora urządzenia.  
Oznacza to, że użytkownik będący właścicielem urządzenia nie należy do grupy rejestracji określonej w konsoli Lookout MTP.   Urządzenie może przejść do tego stanu w sytuacji, gdy użytkownik będący właścicielem urządzenia został usunięty z grupy rejestracji lub gdy grupa rejestracji, do której należy użytkownik, została usunięta.

W module **System** w konsoli Lookout MTP przejdź do karty **Łącznik usługi Intune** i przejrzyj **ustawienia rejestracji**.  Powinna zostać wyświetlona co najmniej jedna grupa usługi Azure AD skonfigurowana na potrzeby rejestracji.  Sprawdź, czy użytkownik będący właścicielem urządzenia należy do jednej z określonych grup usługi Azure AD.  

Gdy urządzenie jest w tym stanie, aplikacja Lookout będzie stale powiadamiać użytkownika o wszelkich wykrytych zagrożeniach, ale nie będzie wysyłać żadnych informacji o zagrożeniach do usługi Intune.

### <a name="device-shows-disconnected-state"></a>Urządzenie jest wyświetlane ze stanem rozłączenia

Stan rozłączenia oznacza, że urządzenie nie komunikowało się z aplikacją Lookout MTP przez wstępnie skonfigurowany przedział czasu (jego wartość domyślna to 30 dni, a wartość minimalna — 7 dni). Oznacza to, że na urządzeniu nie jest zainstalowana aplikacja Portal firmy lub aplikacja Lookout for Work lub że aplikacje te zostały odinstalowane. Ponowne zainstalowanie tych aplikacji powinno umożliwić rozwiązanie problemu. Gdy użytkownik otworzy aplikację Lookout for Work i ją aktywuje, urządzenie dokona ponownej synchronizacji z aplikacją Lookout MTP i usługą Intune.    

### <a name="forcing-a-resync-on-the-device"></a>Wymuszanie ponownej synchronizacji na urządzeniu
W module **Urządzenia** konsoli Lookout MTP administrator może wybrać urządzenie i zdecydować o jego usunięciu.   Gdy następnym razem właściciel urządzenia otworzy aplikację Lookout for Work i naciśnie pozycję **Aktywuj**, stan urządzenia zostanie w pełni ponownie zsynchronizowany.

### <a name="the-owner-of-the-device-is-no-longer-using-this-device"></a>Właściciel urządzenia przestał z niego korzystać
Należy wyczyścić urządzenie i poprosić nowego użytkownika o rejestrację.  W [konsoli administratora usługi Intune](https://manage.microsoft.com) wybierz urządzenie, kliknij je prawym przyciskiem myszy, a następnie wybierz polecenie **Wycofaj/wyczyść**, aby usunąć to urządzenie z zarządzania. Po wycofaniu urządzenia możesz je usunąć.

![zrzut ekranu przestawiający moduł Urządzenia w konsoli administratora usługi Intune z wyświetloną opcją Wycofaj/wyczyść](../media/mtp/mtp-retire-device-intune-console.png)

Możesz również przejść do modułu **Urządzenia** w konsoli Lookout MTP i wybrać pozycję **Usuń**.  

O ile nowy użytkownik należy do jednej z grup rejestracji określonych w konsoli Lookout MTP, urządzenie będzie wyświetlane po powiązaniu go przez usługę Azure AD z nowym użytkownikiem.

## <a name="compliance-remediation-workflows"></a>Przepływy pracy korygowania i zgodności
[Pojawia się monit o zainstalowanie aplikacji Lookout for Work na urządzeniu z systemem Android]( http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

[Należy rozwiązać problem związany z zagrożeniem wykrytym przez aplikację Lookout for Work na urządzeniu z systemem Android ](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)


### <a name="see-also"></a>Zobacz także
[Konfigurowanie subskrypcji przy użyciu aplikacji Lookout MTP](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-your-subscription-with-lookout-mtp)



<!--HONumber=Nov16_HO2-->


