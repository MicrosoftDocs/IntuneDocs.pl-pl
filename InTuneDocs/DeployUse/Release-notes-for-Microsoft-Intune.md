---
title: "Informacje o wersji dla usługi Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: db9479b2-582d-4a1a-9fbc-fbfc6c680e6f
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: 1906f14568484ebbf23ac7c4350964fb2d5d508f


---

# Informacje o wersji dla usługi Microsoft Intune
Usługa Microsoft Intune to zintegrowane, oparte na chmurze rozwiązanie do zarządzania klientami, które oferuje narzędzia, raporty i licencje uaktualnienia do najnowszej wersji systemu Windows, a także pomaga zapewnić aktualizacje i bezpieczeństwo komputerów. Ponadto usługa Intune umożliwia zarządzanie urządzeniami przenośnymi w sieci za pomocą programu Exchange ActiveSync lub bezpośrednio za pomocą usługi Intune. W poniższych informacjach o wersji opisano ważne informacje i znane problemy związane z usługą Microsoft Intune.


## Użytkownicy systemu Android nie mogą wysyłać wiadomości e-mail, gdy jest wdrożony dostęp warunkowy dla usługi Exchange Online.

Użytkownicy urządzeń firmy Samsung z systemem Android 5.1.1 i nowszym nie mogą wysyłać wiadomości e-mail, gdy jest skonfigurowany dostęp warunkowych dla usługi Exchange Online. Firma Samsung potwierdza, że ten problem występuje w przypadku wbudowanego klienta poczty e-mail w systemie Android 5.1.1 i nowszym i pracuje obecnie nad poprawką.

**Obejście 1.** Poinstruuj użytkowników końcowych, aby korzystali z aplikacji Outlook dla systemu Android.

**Obejście 2.** Aby umożliwić wysyłanie wiadomości przez użytkowników, których dotyczy problem, możesz wykonać następujące kroki:

1. Dodaj użytkownika, którego dotyczy problem, do grupy zabezpieczeń w sekcji „wykluczone grupy” w zasadach dostępu warunkowego dla usługi Exchange Online.
2. Zezwól użytkownikowi na tymczasowe synchronizowanie przy użyciu wbudowanego klienta poczty e-mail.
3. Usuń użytkownika, którego dotyczy problem, z wykluczonej grupy i upewnij się, że użytkownik może teraz wysyłać wiadomości e-mail.

Firma Microsoft będzie kontynuować ścisłą współpracę z firmą Samsung w celu opracowania poprawki lub dodatkowych obejść.



## Zmienianie profilów dostępu do zasobów między grupami dla systemu iOS i Android może zakończyć się niepowodzeniem
**Problem:** Podczas zmiany profilów dostępu do zasobów poczty e-mail lub prostego protokołu rejestrowania certyfikatów (SCEP) między grupami może wystąpić konflikt profilów i niepowodzenie operacji. Załóżmy na przykład, że masz istniejący profil poczty e-mail wskazujący lokalny serwer programu Exchange, przeznaczony dla grupy A, a następnie utworzysz nowy profil poczty e-mail wskazujący usługę Exchange Online, przeznaczony dla grupy B. W przypadku przeniesienia użytkowników z grupy A do grupy B urządzenia zachowają profil poczty e-mail korzystający z lokalnego serwera programu Exchange i spróbują zainstalować profil poczty e-mail korzystający z usługi Exchange Online przeznaczony dla grupy B.

Na tym etapie wystąpi jedna z następujących sytuacji: 
* Jeśli profile poczty e-mail A i B są identyczne, urządzenie odrzuci profil B poczty e-mail, ponieważ profil B poczty e-mail zawiera już profil A poczty e-mail.
* Jeśli profil A poczty e-mail różni się od profilu B poczty e-mail, jak wspomniano w powyższym przykładzie, na urządzeniu będą istnieć dwa profile poczty e-mail.

**Uwaga:** Nazwa hosta i atrybut używany dla nazwy użytkownika jest sprawdzany w celu odróżnienia od siebie profilów poczty e-mail.

W obu przypadkach opisanych powyżej profil dostępu do zasobów (profil poczty e-mail) nie został usunięty z urządzenia w celu zapobiegnięcia przypadkowemu usunięciu dostępu do poczty e-mail użytkownika lub certyfikatu protokołu SCEP klienta.

**Obejście:** brak.

## Podczas rejestrowania urządzenia z systemem Windows 8.1, które musi uwierzytelniać się na serwerze proxy, proces rejestracji kończy się niepowodzeniem bez widocznego wskazania przyczyny
**Problem:** podczas rejestrowania urządzenia z systemem Windows 8.1, gdy to urządzenie musi uwierzytelniać się na serwerze proxy podczas procesu rejestracji, rejestracja kończy się niepowodzeniem, jeśli urządzenie nie ma poświadczeń serwera proxy w pamięci podręcznej. Jeśli poświadczenia serwera proxy nie znajdują się w pamięci podręcznej urządzenia, proces rejestracji musi czekać, aż użytkownik je wprowadzi. Jednak monit o poświadczenia serwera proxy nie jest wyświetlany podczas procesu rejestracji. W związku z tym, proces rejestracji nie może uwierzytelnić się na serwerze proxy, a użytkownik nie otrzymuje żadnej informacji o tym niepowodzeniu.

**Obejście:** na urządzeniach z systemem Windows 8.1, które muszą rejestrować się w sieci wymagającej korzystania z uwierzytelnionego serwera proxy, skonfiguruj i zapisz poświadczenia serwera proxy przed zarejestrowaniem urządzenia. Aby skonfigurować i zapisać poświadczenia na urządzeniu z systemem Windows 8.1:

1.  Na urządzeniu z systemem Windows 8.1 otwórz program **Internet Explorer**.

2.  Po wyświetleniu monitu o poświadczenia serwera proxy wprowadź poświadczenia, a następnie wybierz opcję **Zapamiętaj moje poświadczenia**.

3.  Zarejestruj urządzenie.

## Urządzeń z systemem Windows Phone 8.1 nie można zarejestrować w usłudze Microsoft Intune, gdy jest włączone uwierzytelnianie urządzenia w usługach AD FS
**Problem:** rejestracja urządzenia z systemem Windows Phone 8.1 nie powiedzie się, jeśli opcjonalne ustawienie uwierzytelniania urządzenia jest włączone w ramach globalnych zasad uwierzytelniania w Usługach federacyjnych Active Directory (AD FS, Active Directory Federated Services).

**Obejście:** wyłącz uwierzytelnianie urządzeń na serwerze usług AD FS, usuwając zaznaczenie pola wyboru **Włącz uwierzytelnianie urządzeń** w obszarze **Edytuj globalne zasady uwierzytelniania**. Aby uzyskać więcej informacji, zobacz [Konfigurowanie zasad uwierzytelniania](http://technet.microsoft.com/library/dn486781.aspx).


## Aplikacja Microsoft Intune App Wrapping Tool dla systemu Android nie ma wbudowanej funkcji odinstalowywania
**Problem:** **narzędzie firmy Microsoft opakowujące aplikacje dla systemu Android** nie ma wbudowanej funkcji odinstalowywania narzędzia.

**Obejście:** przejdź do lokalizacji, w której zainstalowano narzędzie, a następnie usuń katalog. Domyślna lokalizacja instalacji: **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**. Aby uzyskać więcej informacji o narzędziu do opakowywania aplikacji, zobacz [Przygotowanie aplikacji systemu Android do zarządzania za pomocą narzędzia opakowującego aplikacje](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool).

## Pomoc zdalna jest niedostępna na komputerach z systemem Windows 8 i Windows 8.1
**Problem:** w tej wersji funkcja pomocy zdalnej nie jest dostępna na komputerach z systemem Windows 8 lub Windows 8.1.

**Obejście:** brak.

## Powiadomienia o alertach dla automatycznie dodawanych odbiorców mogą nie działać
**Problem:** jeśli odbiorca jest automatycznie dodawany do powiadomień o alertach, czasem może nie otrzymać powiadomienia.

**Obejście:** aby upewnić się, że odbiorcy będą otrzymywać powiadomienia o wiadomościach, należy ręcznie dodawać odbiorców do powiadomień o alertach.

## Obsługa języków w portalu Azure w wersji zapoznawczej
Portal Azure w wersji zapoznawczej jest zbudowany na nowej platformie i obsługuje następujące języki: chiński (uproszczony), chiński (tradycyjny), czeski, holenderski, angielski, niemiecki, węgierski, włoski, japoński, portugalski (Brazylia), portugalski (Portugalia), rosyjski, hiszpański, francuski, koreański, polski, szwedzki i turecki.

Konsola administracyjna usługi Intune oraz mobilne środowiska użytkownika obsługują język duński, grecki, fiński i rumuński, a także wszystkie języki obsługiwane przez portal Azure w wersji zapoznawczej.



<!--HONumber=Jun16_HO4-->


