---
title: "Informacje o wersji dla usługi Microsoft Intune | Microsoft Docs"
description: "Informacje o wersji usługi Intune"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: db9479b2-582d-4a1a-9fbc-fbfc6c680e6f
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f0e027d1c63435084c434c591fed7bb71b5c07f2
ms.openlocfilehash: 8369cc039ac1c4c24b29927a96360cd872f8e9bc
ms.lasthandoff: 03/08/2017


---

# <a name="release-notes-for-microsoft-intune"></a>Informacje o wersji dla usługi Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Usługa Microsoft Intune to zintegrowane, oparte na chmurze rozwiązanie do zarządzania klientami, które oferuje narzędzia, raporty i licencje uaktualnienia do najnowszej wersji systemu Windows. Pomaga również aktualizować i zabezpieczać komputery. Ponadto usługa Intune umożliwia zarządzanie urządzeniami przenośnymi w sieci za pomocą programu Exchange ActiveSync lub bezpośrednio za pomocą usługi Intune. W poniższych informacjach o wersji opisano ważne informacje i znane problemy związane z usługą Microsoft Intune.

<!-- 3-6-17: customer asked if this is still current; Stacie asked Chris Baldwin about it. Chris said it's a Samsung issue, but that he hasn't heard any reports about it for months, so he suggested that I share that with the customer and remove this item from the release notes. I'm only going to comment it out in case it resurfaces.
## Android users can’t send email when conditional access for Exchange Online is implemented

**Issue:** Users running Samsung Android 5.1.1 and later on their devices can't send email when conditional access for Exchange Online has been set up. Samsung acknowledges that the issue is in its built-in email client in Android 5.1.1 and later, and is investigating a fix.

**Workaround 1:** Advise users to use the Outlook app for Android.

**Workaround 2:** To let affected users send email, you can follow these steps:

1. Put each affected user in a security group in the “exempted groups” section of the conditional access policy for Exchange Online.
2. Let the user temporarily sync email on the built-in email client.
3. Remove the affected user from the exempted group, and confirm that the user can now send email.

Microsoft will continue to work closely with Samsung on a fix or additional workarounds.
-->


## <a name="changing-resource-access-profiles-between-groups-for-ios-and-android-might-fail"></a>Zmienianie profilów dostępu do zasobów między grupami dla systemu iOS i Android może zakończyć się niepowodzeniem
**Problem:** Podczas zmiany profilów dostępu do zasobów poczty e-mail lub prostego protokołu rejestrowania certyfikatów (SCEP) między grupami może wystąpić konflikt profilów i niepowodzenie operacji. Załóżmy na przykład, że masz istniejący profil poczty e-mail przeznaczony dla grupy A wskazujący lokalny serwer programu Exchange. Następnie utworzysz nowy profil poczty e-mail przeznaczony dla grupy B wskazujący usługę Exchange Online. Gdy przeniesiesz użytkowników z grupy A do grupy B, urządzenia zachowają profil poczty e-mail korzystający z lokalnego serwera programu Exchange i spróbują zainstalować profil poczty e-mail korzystający z usługi Exchange Online przeznaczony dla grupy B.

Na tym etapie wystąpi jedna z następujących sytuacji: 
* Jeśli profile poczty e-mail A i B są identyczne, urządzenie odrzuci profil B poczty e-mail, ponieważ profil B poczty e-mail zawiera już profil A poczty e-mail.
* Jeśli profil A poczty e-mail różni się od profilu B poczty e-mail, jak wspomniano w przykładzie, na urządzeniu będą istnieć dwa profile poczty e-mail.

> [!NOTE]
> Nazwa hosta i atrybut używany dla nazwy użytkownika jest sprawdzany w celu odróżnienia od siebie profilów poczty e-mail.

W obu przypadkach profil dostępu do zasobów (profil poczty e-mail) nie został usunięty z urządzenia, aby zapobiec przypadkowemu usunięciu dostępu do poczty e-mail użytkownika lub certyfikatu protokołu SCEP klienta.

**Obejście:** brak.

## <a name="when-you-enroll-a-windows-81-device-that-must-authenticate-to-a-proxy-server-the-enrollment-process-fails-with-no-visible-cause"></a>Podczas rejestrowania urządzenia z systemem Windows 8.1, które musi uwierzytelniać się na serwerze proxy, proces rejestracji kończy się niepowodzeniem bez widocznej przyczyny
**Problem:** podczas rejestrowania urządzenia z systemem Windows 8.1, gdy to urządzenie musi uwierzytelniać się na serwerze proxy podczas procesu rejestracji, rejestracja kończy się niepowodzeniem, jeśli urządzenie nie ma poświadczeń serwera proxy w pamięci podręcznej. Jeśli poświadczenia serwera proxy nie znajdują się w pamięci podręcznej urządzenia, proces rejestracji musi czekać, aż użytkownik je wprowadzi. Jednak monit o poświadczenia serwera proxy nie pojawia się w trakcie procesu rejestracji. Powoduje to, że proces rejestracji nie może się uwierzytelnić na serwerze proxy. Użytkownik nie otrzymuje żadnej widocznej informacji o tym błędzie.

**Obejście:** na urządzeniach z systemem Windows 8.1, które muszą rejestrować się w sieci wymagającej korzystania z uwierzytelnionego serwera proxy, skonfiguruj i zapisz poświadczenia serwera proxy przed zarejestrowaniem urządzenia. Aby skonfigurować i zapisać poświadczenia na urządzeniu z systemem Windows 8.1:

1.  Na urządzeniu z systemem Windows 8.1 otwórz program Internet Explorer.
2.  Po wyświetleniu monitu o poświadczenia serwera proxy wprowadź poświadczenia, a następnie wybierz opcję **Zapamiętaj moje poświadczenia**.
3.  Zarejestruj urządzenie.

## <a name="windows-phone-81-devices-fail-to-enroll-with-microsoft-intune-when-device-authentication-is-enabled-in-ad-fs"></a>Urządzeń z systemem Windows Phone 8.1 nie można zarejestrować w usłudze Microsoft Intune, gdy jest włączone uwierzytelnianie urządzenia w usługach AD FS
**Problem:** rejestracja urządzenia z systemem Windows Phone 8.1 nie powiedzie się, jeśli opcjonalne ustawienie uwierzytelniania urządzenia jest włączone w ramach globalnych zasad uwierzytelniania w Usługach federacyjnych Active Directory (AD FS).

**Obejście:** wyłącz uwierzytelnianie urządzeń na serwerze usług AD FS, usuwając zaznaczenie pola wyboru **Włącz uwierzytelnianie urządzeń** w obszarze **Edytuj globalne zasady uwierzytelniania**. Aby uzyskać więcej informacji, zobacz [Konfigurowanie zasad uwierzytelniania](http://technet.microsoft.com/library/dn486781.aspx).


## <a name="microsoft-intune-app-wrapping-tool-for-android-has-no-built-in-uninstall-capability"></a>Aplikacja Microsoft Intune App Wrapping Tool dla systemu Android nie ma wbudowanej funkcji odinstalowywania
**Problem:** **narzędzie firmy Microsoft opakowujące aplikacje dla systemu Android** nie ma wbudowanej funkcji odinstalowywania narzędzia.

**Obejście:** przejdź do lokalizacji, w której zainstalowano narzędzie, a następnie usuń katalog. Domyślna lokalizacja instalacji: **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**. Aby uzyskać więcej informacji o narzędziu do opakowywania aplikacji, zobacz [Przygotowanie aplikacji systemu Android do zarządzania za pomocą narzędzia do opakowywania aplikacji](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool).

## <a name="remote-assistance-is-not-available-on-computers-that-run-windows-8-or-windows-81"></a>Pomoc zdalna jest niedostępna na komputerach z systemem Windows 8 i Windows 8.1
**Problem:** w tej wersji funkcja pomocy zdalnej nie jest dostępna na komputerach z systemem Windows 8 lub Windows 8.1.

**Obejście:** brak.

## <a name="alert-notifications-for-recipients-that-are-automatically-added-might-not-work"></a>Powiadomienia o alertach dla automatycznie dodawanych odbiorców mogą nie działać
**Problem:** jeśli odbiorcy są automatycznie dodawani do powiadomień o alertach, czasem mogą nie otrzymać powiadomienia.

**Obejście:** aby upewnić się, że odbiorcy będą otrzymywać powiadomienia o wiadomościach, należy ręcznie dodać odbiorców do powiadomień o alertach.

## <a name="language-support-in-the-azure-portal"></a>Obsługa języków w witrynie Azure Portal
Witryna Azure Portal obsługuje następujące języki: chiński (uproszczony), chiński (tradycyjny), czeski, holenderski, angielski, niemiecki, węgierski, włoski, japoński, portugalski (Brazylia), portugalski (Portugalia), rosyjski, hiszpański, francuski, koreański, polski, szwedzki i turecki.

Konsola administracyjna usługi Intune oraz mobilne środowiska użytkownika obsługują język duński, grecki, fiński, norweski i rumuński, a także wszystkie języki obsługiwane przez witrynę Azure Portal.

