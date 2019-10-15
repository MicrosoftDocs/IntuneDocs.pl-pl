---
title: Korzyści z zestawu SDK aplikacji usługi Intune
titleSuffix: Microsoft Intune
description: Zestaw SDK aplikacji usługi Intune jest dostępny na platformach iOS i Android. Udostępnia on funkcje zarządzania aplikacjami mobilnymi za pomocą usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/15/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: cd9f05e7-26e6-45e0-8d38-67d8232b1cae
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 580e9f51532a5606ca8955abc5bf3b3fa3a63713
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71733702"
---
# <a name="microsoft-intune-app-sdk-overview"></a>Omówienie zestawu SDK aplikacji usługi Microsoft Intune
Korzystając z zestawu SDK aplikacji usługi Intune dostępnego dla systemów iOS i Android, możesz obsługiwać [zasady ochrony aplikacji](../apps/app-protection-policy.md) usługi Intune w swojej aplikacji. Po zastosowaniu zasad ochrony do aplikacji można zarządzać nią w usłudze Intune i będzie ona rozpoznawana przez usługę Intune jako zarządzana aplikacja. Zestaw SDK kładzie nacisk na minimalizację liczby zmian kodu wymaganych od dewelopera aplikacji. Większość funkcji zestawu SDK możesz włączyć bez zmiany zachowania aplikacji. W przypadku rozszerzonego środowiska użytkownika końcowego i administratora IT możesz użyć interfejsów API zestawu SDK, aby dostosować zachowanie aplikacji pod kątem obsługi funkcji, które wymagają współdziałania ze strony aplikacji.

Gdy włączysz obsługę zasad ochrony aplikacji usługi Intune w swojej aplikacji, administratorzy IT będą mogli wdrażać te zasady w celu ochrony danych firmowych w aplikacji.

## <a name="app-protection-features"></a>Funkcje ochrony aplikacji

Poniżej przedstawiono przykłady funkcji ochrony aplikacji usługi Intune, które można włączyć za pomocą zestawu SDK.

### <a name="control-users-ability-to-move-corporate-files"></a>Kontrolowanie możliwości przenoszenia plików firmowych przez użytkowników
Administratorzy IT mogą określać, gdzie można przenosić dane służbowe w aplikacji. Na przykład mogą wdrożyć zasady, które wyłączą w aplikacji możliwość tworzenia kopii zapasowych danych firmowych w chmurze.

### <a name="configure-clipboard-restrictions"></a>Konfigurowanie ograniczeń schowka
Administratorzy IT mogą skonfigurować działanie schowka w aplikacjach zarządzanych przez usługę Intune. Na przykład mogą wdrożyć zasady powodujące, że użytkownicy końcowi nie będą mogli wycinać lub kopiować danych z aplikacji i wklejać ich w niezarządzanej aplikacji osobistej.

### <a name="enforce-encryption-on-saved-data"></a>Wymuszanie szyfrowania zapisywanych danych
Administratorzy IT mogą wymusić zasady, które powodują szyfrowanie danych zapisywanych na urządzeniu przez aplikację.

### <a name="remotely-wipe-corporate-data"></a>Zdalne czyszczenie danych firmowych
Administratorzy IT mogą zdalnie czyścić dane firmowe z aplikacji zarządzanej przez usługę Intune. Ta funkcja jest oparta na tożsamości i usuwa tylko pliki, które są skojarzone z tożsamością firmową użytkownika końcowego. Funkcja wymaga w tym celu współdziałania ze strony aplikacji. Aplikacja może określić tożsamość, dla której powinno zostać wykonane czyszczenie, na podstawie ustawień użytkownika. Jeśli te określone ustawienia użytkownika są niedostępne w aplikacji, domyślne zachowanie to wyczyszczenie katalogu aplikacji i powiadomienie użytkownika końcowego, że dostęp został usunięty.

### <a name="enforce-the-use-of-a-managed-browser"></a>Wymuszanie użycia programu Managed Browser
Administratorzy IT mogą wymusić otwieranie linków sieci Web w danej aplikacji za pomocą [aplikacji Intune Managed Browser](../apps/app-configuration-managed-browser.md). Ta funkcja gwarantuje, że linki wyświetlane w środowisku firmowym są przechowywane w domenie aplikacji zarządzanych przez usługę Intune.

### <a name="enforce-a-pin-policy"></a>Wymuszanie zasad numeru PIN
Administratorzy IT mogą wymagać od użytkowników końcowych wprowadzania numeru PIN przed uzyskaniem dostępu do danych firmowych w aplikacji. Gwarantuje to, że osoba korzystająca z aplikacji jest tą samą osobą, która początkowo zalogowała się przy użyciu swojego konta służbowego. Gdy użytkownicy końcowi skonfigurują swoje numery PIN, zestaw SDK aplikacji usługi Intune będzie używać usługi Azure Active Directory do weryfikowania poświadczeń użytkowników końcowych względem zarejestrowanego konta usługi Intune.

### <a name="require-users-to-sign-in-with-a-work-or-school-account-for-app-access"></a>Wymaganie logowania się użytkowników za pomocą konta służbowego w celu uzyskania dostępu do aplikacji
Administratorzy IT mogą wymagać od użytkowników logowania się za pomocą konta służbowego w celu uzyskania dostępu do aplikacji. Zestaw SDK aplikacji usługi Intune używa usługi Azure Active Directory do udostępnienia funkcji logowania jednokrotnego, która umożliwia ponowne używanie poświadczeń podczas kolejnych logowań po ich jednokrotnym podaniu. Obsługiwane jest również uwierzytelnianie przy użyciu rozwiązań do zarządzania tożsamościami sfederowanych z usługą Azure Active Directory.

### <a name="check-device-health-and-compliance"></a>Sprawdzanie kondycji i zgodności urządzenia
Administratorzy IT mogą sprawdzać kondycję urządzenia i jego zgodność z zasadami usługi Intune przed udostępnieniem aplikacji użytkownikom końcowym. W systemie iOS te zasady sprawdzają, czy nie zostały zdjęte zabezpieczenia systemu. W systemie Android te zasady sprawdzają, czy na urządzeniu nie został odblokowany dostęp do konta root.

### <a name="support-multi-identity"></a>Obsługa wielu tożsamości
Obsługa wielu tożsamości to funkcja zestawu SDK, która umożliwia współistnienie kont zarządzanych przez zasady (firmowych) i niezarządzanych (osobistych) w jednej aplikacji.

Na przykład wielu użytkowników konfiguruje zarówno konto firmowe, jak i osobiste w aplikacjach mobilnych Outlook dla systemów iOS i Android. Gdy użytkownik uzyskuje dostęp do danych za pomocą konta firmowego, administrator IT musi mieć pewność, że zostaną zastosowane zasady ochrony aplikacji. Jednak gdy użytkownik uzyskuje dostęp do osobistego konta e-mail, dane powinny być poza kontrolą administratora IT. Zestaw SDK aplikacji usługi Intune osiąga to, stosując zasady ochrony aplikacji **tylko** do tożsamości firmowej w aplikacji.

Funkcja umożliwiająca stosowanie wielu tożsamości pomaga w rozwiązaniu problemów z ochroną danych, przed którymi stoją organizacje korzystające z aplikacji ze sklepu obsługujących konta osobiste i firmowe.
 
### <a name="app-protection-without-device-enrollment"></a>Ochrona aplikacji bez rejestracji urządzeń

>[!IMPORTANT]
>Ochrona aplikacji bez rejestracji urządzeń w usłudze Intune jest dostępna w narzędziach opakowujących aplikacje usługi Intune, zestawie SDK dla systemu Android, zestawie SDK dla systemu iOS oraz powiązaniach Xamarin dla zestawu SDK aplikacji Intune.

Wielu użytkowników korzystających z urządzeń osobistych chce uzyskiwać dostęp do danych firmowych bez rejestrowania swoich urządzeń osobistych za pomocą dostawcy zarządzania urządzeniami przenośnymi (MDM). Ponieważ rejestracja w rozwiązaniu MDM wymaga globalnej kontroli nad urządzeniem, użytkownicy często mają wątpliwości przed przekazaniem swojej firmie kontroli nad ich urządzeniami osobistymi.

Ochrona aplikacji bez rejestracji urządzeń umożliwia usłudze Microsoft Intune wdrożenie zasad ochrony aplikacji bezpośrednio w aplikacji, bez konieczności wdrażania zasad za pomocą kanału zarządzania urządzeniami.

### <a name="on-demand-application-vpn-connections-with-citrix-mvpn"></a>Połączenia sieci VPN na żądanie aplikacji z użyciem technologii Citrix mVPN 
Urządzeniami i aplikacjami można zarządzać przy użyciu kombinacji usług Citrix XenMobile MDX i Microsoft Intune. To połączenie oznacza, że można zarządzać aplikacjami za pomocą zasad ochrony aplikacji w usłudze Intune przy równoczesnym użyciu technologii mVPN firmy Citrix. Integracja z oprogramowaniem Citrix jest dostępna w przypadku zestawu SDK aplikacji usługi Intune dla systemów iOS i Android oraz narzędzia opakowującego aplikacje usługi Intune dla systemów iOS i Android (z flagą -citrix).
 
Aby dowiedzieć się więcej na temat rozwiązania Citrix MDX, zobacz [About the MDX Toolkit (Informacje o zestawie narzędzi MDX)](https://docs.citrix.com/en-us/mdx-toolkit/10/about-mdx-toolkit.html), [Citrix MDX app wrapper for iOS (Narzędzie opakowujące aplikacje Citrix MDX dla systemu iOS)](https://docs.citrix.com/en-us/mdx-toolkit/10/xmob-mdx-kit-app-wrap-ios.html) i [Citrix MDX app wrapper for Android (Narzędzie opakowujące aplikacje Citrix MDX dla systemu Android)](https://docs.citrix.com/en-us/mdx-toolkit/10/xmob-mdx-kit-app-wrap-android.html).

## <a name="next-steps"></a>Następne kroki

- [Wprowadzenie do zestawu SDK aplikacji usługi Microsoft Intune](app-sdk-get-started.md).