---
title: Konfigurowanie logowania jednokrotnego w usłudze Microsoft Intune dla urządzeń z systemem iOS
titlesuffix: ''
description: Dowiedz się, jak konfigurować logowanie jednokrotne w usłudze Microsoft Intune dla urządzeń z systemem iOS.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f19320df9a9728cdd77e608fc0ad219272a731f
ms.sourcegitcommit: e6319ff186d969da34bd19c9730ba003d6cce353
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/20/2018
---
# <a name="configure-microsoft-intune-for-ios-device-single-sign-on"></a>Konfigurowanie logowania jednokrotnego w usłudze Microsoft Intune dla urządzeń z systemem iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Większość aplikacji biznesowych (LOB, Line of Business) wymaga pewnego poziomu uwierzytelniania użytkowników w celu obsługi zabezpieczeń. W wielu przypadkach oznacza to, że użytkownik musi wprowadzać te same poświadczenia wielokrotnie, co może być irytujące. Aby udoskonalić środowisko pracy użytkownika, deweloperzy mogą tworzyć aplikacje korzystające z logowania jednokrotnego, co pozwala ograniczyć częstotliwość wprowadzania poświadczeń przez użytkownika.

Aby skorzystać z logowania jednokrotnego dla urządzeń z systemem iOS, konieczne jest spełnienie następujących wymagań:

- Należy utworzyć aplikację poszukującą magazynu poświadczeń użytkownika w ładunku logowania jednokrotnego na urządzeniu z systemem iOS.
- Usługa Intune musi być skonfigurowana na potrzeby logowania jednokrotnego dla urządzeń z systemem iOS.

## <a name="to-configure-intune-for-ios-device-single-sign-on"></a>Konfigurowanie logowania jednokrotnego w usłudze Intune dla urządzeń z systemem iOS


1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Konfiguracja urządzeń**.
4. W okienku **Konfiguracja urządzeń** w sekcji **Zarządzanie** wybierz pozycję **Profile**.
5. W okienku profilów wybierz pozycję **Utwórz profil**.
6. Podaj nazwę i opis, a następnie skonfiguruj następujące ustawienia:
   - **Platforma**: wybierz pozycję **iOS**.
   - **Typ profilu**: wybierz pozycję **Funkcje urządzenia**.
7. W okienku **Funkcje urządzenia** wybierz pozycję **Logowanie jednokrotne**.

   ![Okienko Logowanie jednokrotne](./media/sso-blade.png)

8. Skorzystaj z poniższej tabeli podsumowania, która ułatwia wypełnianie pól w okienku **Logowanie jednokrotne**. Więcej informacji zawierają sekcje pod tabelą.

   |Pole  |Uwagi|
   |---------|---------|
   |**Atrybut nazwy użytkownika z usługi AAD**|Atrybut sprawdzany przez usługę Intune dla każdego użytkownika w usłudze AAD i umożliwiający wypełnienie odpowiednich pól (na przykład nazwy UPN) przed wygenerowaniem ładunku XML instalowanego na urządzeniu.|
   |**Obszar**|Część adresu URL stanowiąca domenę.|
   |**Przedrostki adresów URL, które będą korzystały z logowania jednokrotnego**|Wszystkie adresy URL w organizacji, które wymagają uwierzytelniania za pomocą logowania jednokrotnego użytkownika|
   |**Aplikacje, które będą korzystały z logowania jednokrotnego**|Aplikacje na urządzeniach użytkownika końcowego korzystające z ładunku logowania jednokrotnego.|
   |**Certyfikat odnowienia poświadczeń**|W przypadku używania certyfikatów w celu uwierzytelniania wybierz certyfikat SCEP lub PFX wdrożony na potrzeby użytkownika jako certyfikat uwierzytelniania.|

W poniższych sekcjach znajduje się więcej informacji o poszczególnych polach dotyczących logowania jednokrotnego.

### <a name="username-attribute-from-aad-and-realm"></a>Atrybut nazwy użytkownika z usługi AAD i obszaru

- Jeśli dla tego pola wybrano wartość **Główna nazwa użytkownika**, jest ona analizowana w następujący sposób:

   ![Atrybut nazwy użytkownika](media/User-name-attribute.png)

   Istnieje również możliwość zastąpienia obszaru tekstem wpisywany w polu **Obszar**.

   Na przykład firma Contoso może mieć kilka podregionów, takich jak Europa, Azja i Ameryka Północna. Wymagane może być, aby użytkownicy tej firmy w Azji używali ładunku logowania jednokrotnego, natomiast aplikacja wymaga nazwy UPN w postaci *username@asia.contoso.com*. Jeśli w takim przypadku zostanie wybrana wartość **Główna nazwa użytkownika**, domyślnie obszar dla każdego użytkownika zostanie pobrany z usługi AAD i może on mieć po prostu wartość *contoso.com*. Dla użytkowników w Azji można zatem specjalnie utworzyć ten ładunek i zastąpić go wartością *asia.contoso.com*. Teraz nazwa UPN użytkownika końcowego będzie miała wartość *username@asia.contoso.com* zamiast *username@contoso.com*.

- W przypadku wybrania wartości **Identyfikator urządzenia** usługa Intune automatycznie wybiera identyfikator urządzenia usługi Intune.

   Domyślnie dla aplikacji wymagany jest tylko identyfikator urządzenia. Jeśli natomiast aplikacja korzysta z obszaru oprócz identyfikatora urządzenia, możesz wpisać obszar w polu tekstowym **Obszar**.

   > [!NOTE]
   > Domyślnie nie wpisuj żadnej wartości w polu Obszar, jeśli używasz identyfikatora urządzenia.

### <a name="url-prefixes-that-will-use-single-sign-on"></a>Przedrostki adresów URL, które będą korzystały z logowania jednokrotnego

Wpisz w tym miejscu wszystkie adresy URL w organizacji, które wymagają uwierzytelniania użytkownika.

Na przykład gdy użytkownik nawiązuje połączenie z dowolną z tych witryn, urządzenie z systemem iOS używa poświadczeń logowania jednokrotnego i użytkownik nie musi wprowadzać żadnych dodatkowych poświadczeń. Jeśli jednak włączone jest uwierzytelnianie wieloskładnikowe, użytkownicy muszą wykonać drugie uwierzytelnianie.

> [!NOTE]
> Te adresy URL muszą być poprawnie sformatowanymi nazwami FQDN. Firma Apple wymaga, aby miały one postać `http://<yourURL.domain>`

Wzorce dopasowań adresów URL muszą rozpoczynać się od ciągu `http://` lub `https://`. Wykonywane jest proste dopasowanie ciągu, które wykaże, że prefiks adresu URL `http://www.contoso.com/` jest niezgodny z ciągiem `http://www.contoso.com:80/`. W przypadku systemów iOS 9.0 lub nowszych można jednak użyć pojedynczego symbolu wieloznacznego \*, aby określić wszystkie zgodne wartości. Na przykład wzorzec `http://*.contoso.com/` jest zgodny zarówno z adresem URL `http://store.contoso.com/`, jak i `http://www.contoso.com`.
Wzorce `http://.com` i `https://.com` są zgodne odpowiednio ze wszystkimi adresami URL HTTP i HTTPS.

### <a name="apps-that-will-use-single-sign-on"></a>Aplikacje, które będą korzystały z logowania jednokrotnego

Wskazuje aplikacje na urządzeniu użytkownika końcowego, które mogą korzystać z ładunku logowania jednokrotnego.

Tablica `AppIdentifierMatches` musi zawierać ciągi zgodne z identyfikatorami pakietu aplikacji. Te ciągi mogą być dokładnymi dopasowaniami (przykład: `com.contoso.myapp`) lub mogą określać dopasowanie prefiksu w ramach identyfikatora pakietu za pomocą symbolu wieloznacznego \*. Symbol wieloznaczny musi występować po znaku kropki (.) i może zostać użyty tylko raz — na końcu ciągu (przykład: `com.contoso.*`). Jeśli symbol wieloznaczny zostanie użyty, to dowolna aplikacja o identyfikatorze pakietu rozpoczynającym się od prefiksu uzyskuje dostęp do konta.

Pole **Nazwa aplikacji** służy do dodawania przyjaznej nazwy, która ułatwia identyfikowanie identyfikatora pakietu.

### <a name="credential-renewal-certificate"></a>Certyfikat odnowienia poświadczeń

W przypadku uwierzytelniania użytkowników końcowych za pomocą certyfikatów, a nie haseł, użyj tego pola w celu wybrania certyfikatu SCEP lub PFX wdrożonego dla użytkownika jako certyfikat uwierzytelniania. Zazwyczaj jest to ten sam certyfikat, który został wdrożony dla użytkownika na potrzeby innych profilów, takich jak profil sieci VPN lub Wi-Fi bądź profil poczty e-mail.

## <a name="next-steps"></a>Następne kroki

Aby uzyskać dodatkowe informacje o konfiguracji funkcji urządzeń, zobacz [Jak skonfigurować ustawienia funkcji urządzeń w usłudze Microsoft Intune](device-features-configure.md).
