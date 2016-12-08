---
title: "Omówienie zestawu SDK aplikacji usługi Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ef1751bb-3a2f-4662-a922-38c076869eb3
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5eca6c925159287cbed2074f65c1d641d527faef
ms.openlocfilehash: 4cb153c601b83b113a22b2acf3da5200cdb70472


---

# <a name="overview-of-the-microsoft-intune-app-sdk"></a>Omówienie zestawu SDK aplikacji usługi Microsoft Intune
Zestaw SDK aplikacji usługi Intune jest dostępny na platformach iOS i Android. Udostępnia on funkcje zarządzania aplikacjami mobilnymi za pomocą usługi Microsoft Intune. Ponadto próbuje zmniejszyć liczbę zmian w kodzie, które musi wprowadzić deweloper.

Większość funkcji zestawu SDK możesz włączyć bez zmiany zachowania aplikacji. W przypadku rozszerzonego środowiska użytkownika końcowego i administratora IT możesz użyć naszych interfejsów API, aby dostosować zachowanie aplikacji dla funkcji, które wymagają współdziałania ze strony aplikacji.

Po aktywowaniu aplikacji administratorzy IT mogą wdrożyć zasady w zarządzanych aplikacjach usługi Intune i skorzystać z tych funkcji do ochrony danych firmowych.

# <a name="features"></a>Funkcje
## <a name="control-users-ability-to-move-corporate-documents"></a>Kontrolowanie możliwości przenoszenia dokumentów firmowych przez użytkowników
Administratorzy IT mogą kontrolować przenoszenie plików dokumentów firmowych w aplikacjach zarządzanych przez usługę Intune. Na przykład możesz wdrożyć zasady, które wyłączają w aplikacjach do obsługi kopii zapasowych plików możliwość tworzenia kopii zapasowych danych firmowych w chmurze.  

## <a name="configure-clipboard-restrictions"></a>Konfigurowanie ograniczeń schowka
Administratorzy IT mogą skonfigurować działanie schowka w aplikacjach zarządzanych przez usługę Intune. Na przykład mogą wdrożyć zasady, które spowodują, że użytkownicy końcowi nie będą mogli użyć funkcji wycinania lub kopiowania do schowka w aplikacji zarządzanej przez usługę Intune, by wkleić dane do niezarządzanej aplikacji.

## <a name="enforce-encryption-on-saved-data"></a>Wymuszanie szyfrowania zapisywanych danych
Administratorzy IT mogą wymusić zasady, które powodują szyfrowanie danych zapisywanych na urządzeniu przez aplikację.

## <a name="remotely-wipe-corporate-data"></a>Zdalne czyszczenie danych firmowych
Administratorzy IT mogą zdalnie wyczyścić dane firmowe z aplikacji zarządzanej przez usługę Intune, gdy urządzenie jest wyrejestrowywane z usługi Microsoft Intune. Ta funkcja jest oparta na tożsamości i usuwa tylko pliki powiązane z tożsamością firmową użytkownika końcowego. Funkcja wymaga w tym celu współdziałania ze strony aplikacji. Aplikacja może określić tożsamość, dla której powinno zostać wykonane czyszczenie, na podstawie ustawień użytkownika. Jeśli te określone ustawienia użytkownika są niedostępne w aplikacji, domyślne zachowanie to wyczyszczenie katalogu aplikacji i powiadomienie użytkownika końcowego, że dostęp do zasobów firmy został usunięty.

## <a name="enforce-the-use-of-a-managed-browser"></a>Wymuszanie użycia programu Managed Browser
Administratorzy IT mogą wymusić użycie zarządzanej przeglądarki przy otwieraniu przez użytkowników linków z aplikacji zarządzanych przez usługę Intune. Gdy użytkownicy końcowi korzystają z przeglądarki zarządzanej przez usługę Intune, można w ten sposób zapewnić, że linki, które pojawiają się w wiadomościach e-mail w kliencie poczty e-mail zarządzanym przez tę usługę Intune, pozostają w domenie zarządzanych przez nią aplikacji.

## <a name="enforce-a-pin-policy"></a>Wymuszanie zasad numeru PIN
Administratorzy IT mogą wymusić zasady numeru PIN przy uruchamianiu aplikacji zarządzanej przez usługę Intune. Te zasady ułatwiają zapewnienie, że użytkownicy końcowi z urządzeniami zarejestrowanymi w usłudze Microsoft Intune są tymi samymi osobami, które uruchamiają aplikacje. Gdy użytkownicy końcowi konfigurują swoje numery PIN, zestaw SDK aplikacji usługi Intune używa usługi Azure Active Directory do zweryfikowania ich poświadczeń względem poświadczeń użytych do zarejestrowania urządzenia.

## <a name="require-users-to-enter-credentials-before-they-can-start-apps"></a>Wymaganie wprowadzenia poświadczeń przed uruchomieniem aplikacji
Administratorzy IT mogą wymagać od użytkowników końcowych wprowadzenia poświadczeń przed uruchomieniem aplikacji zarządzanej przez usługę Intune. Zestaw SDK aplikacji usługi Intune korzysta z usługi Azure Active Directory w celu zapewnienia środowiska jednokrotnego logowania. Oznacza to, że raz wprowadzone poświadczenia są używane do późniejszego logowania. Zestaw SDK obsługuje również uwierzytelnianie przy użyciu rozwiązań do zarządzania tożsamościami, które są [sfederowane z usługą Azure Active Directory](/active-directory/active-directory-aadconnect-federation-compatibility).

## <a name="check-device-health-and-compliance"></a>Sprawdzanie kondycji i zgodności urządzenia
Administratorzy IT mogą sprawdzać kondycję urządzenia i jego zgodność z zasadami firmy przed udostępnieniem użytkownikom końcowym aplikacji zarządzanych przez usługę Intune. Na platformie iOS te zasady sprawdzają, czy nie zostały zdjęte zabezpieczenia systemu. Na platformie Android te zasady sprawdzają, czy na urządzeniu nie został odblokowany dostęp do konta root.  



<!--HONumber=Nov16_HO5-->


