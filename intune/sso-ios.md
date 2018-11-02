---
title: Dodawanie funkcji logowania jednokrotnego dla urządzeń z systemem iOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: W usłudze Microsoft Intune możesz utworzyć, skonfigurować, zezwolić lub włączyć używanie funkcji logowania jednokrotnego (SSO) zamiast hasła w celu uwierzytelniania w zasobach i danych Twojej organizacji dla urządzeń z systemem iOS. Aby korzystać z logowania jednokrotnego, utwórz profil konfiguracji urządzenia, a następnie wprowadź nazwę UPN, identyfikator urządzenia, swoje aplikacje i certyfikat na potrzeby uwierzytelniania użytkownika i urządzenia.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d1add113222c2aa7eaea10679c329e877b1a136f
ms.sourcegitcommit: 437eaf364c3b8a38d294397310c770ea4d8a8015
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2018
ms.locfileid: "49992013"
---
# <a name="use-single-sign-on-ios-device-in-microsoft-intune"></a>Używanie urządzenia z systemem iOS z logowaniem jednokrotnym w usłudze Microsoft Intune

Większość aplikacji biznesowych (LOB, Line of Business) wymaga pewnego poziomu uwierzytelniania użytkowników w celu obsługi zabezpieczeń. W wielu przypadkach to uwierzytelnianie oznacza to, że użytkownik musi wprowadzać te same poświadczenia wielokrotnie, co może być irytujące. Aby udoskonalić środowisko pracy użytkownika, deweloperzy mogą tworzyć aplikacje korzystające z logowania jednokrotnego (SSO), co pozwala ograniczyć częstotliwość wprowadzania poświadczeń przez użytkownika.

W tym artykule pokazano, jak włączyć funkcję logowania jednokrotnego dla urządzeń z systemem iOS przy użyciu profilu konfiguracji urządzenia w usłudze Microsoft Intune.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Upewnij się, że masz aplikację poszukującą magazynu poświadczeń użytkownika w ładunku logowania jednokrotnego na urządzeniu z systemem iOS.

## <a name="create-the-sso-profile"></a>Tworzenie profilu logowania jednokrotnego

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Podaj następujące ustawienia:

    - **Nazwa**: wprowadź nazwę profilu, na przykład `ios sso profile`.
    - **Opis**: wprowadź opis zawierający kluczowe terminy, ułatwiające znalezienie profilu na liście.
    - **Platforma**: wybierz pozycję **iOS**.
    - **Typ profilu**: wybierz pozycję **Funkcje urządzenia**.

4. Wybierz pozycję **Logowanie jednokrotne**.

    ![Okienko Logowanie jednokrotne](./media/sso-blade.png)

5. Podaj następujące ustawienia: 

    - **Atrybut nazwy użytkownika z usługi AAD**: usługa Intune szuka tego atrybutu dla każdego użytkownika w usłudze Azure AD. Następnie usługa Intune wypełnia odpowiednie pole (na przykład nazwę UPN) przed wygenerowaniem ładunku XML instalowanego na urządzeniu. Dostępne opcje:
    
        - **Główna nazwa użytkownika**: nazwa UPN jest analizowana w następujący sposób:

            ![Atrybut nazwy użytkownika](media/User-name-attribute.png)

            Można również zastąpić obszar tekstem wpisywanym w polu tekstowym **Obszar**.

            Na przykład firma Contoso może mieć kilka podregionów, takich jak Europa, Azja i Ameryka Północna. Wymagane może być, aby użytkownicy tej firmy w Azji używali ładunku logowania jednokrotnego, natomiast aplikacja wymaga nazwy UPN w formacie `username@asia.contoso.com`. Jeśli w takim przypadku zostanie wybrana wartość **Główna nazwa użytkownika**, domyślnie obszar dla każdego użytkownika zostanie pobrany z usługi Azure AD i może on mieć wartość *contoso.com*. Dla użytkowników w Azji można zatem specjalnie utworzyć ten ładunek i zastąpić go wartością *asia.contoso.com*. Teraz nazwa UPN użytkownika końcowego będzie miała wartość username@asia.contoso.com zamiast username@contoso.com.

        - **Identyfikator urządzenia usługi Intune**: usługa Intune automatycznie wybiera identyfikator urządzenia usługi Intune. 

            Domyślnie dla aplikacji wymagany jest tylko identyfikator urządzenia. Jeśli natomiast aplikacja korzysta z obszaru *oraz* z identyfikatora urządzenia, możesz wpisać obszar w polu tekstowym **Obszar**.

            > [!NOTE]
            > Domyślnie nie wpisuj żadnej wartości w polu Obszar, jeśli używasz identyfikatora urządzenia.

    - **Obszar**: część adresu URL stanowiąca domenę.
    
    - **Przedrostki adresów URL, które będą korzystały z logowania jednokrotnego**: **dodaj** wszystkie adresy URL w organizacji, które wymagają uwierzytelniania za pomocą logowania jednokrotnego użytkownika. 

        Kiedy na przykład użytkownik nawiązuje połączenie z dowolną z tych witryn, urządzenie z systemem iOS używa poświadczeń logowania jednokrotnego. Użytkownik nie musi wprowadzać żadnych dodatkowych poświadczeń. Jeśli jednak włączone jest uwierzytelnianie wieloskładnikowe, użytkownicy muszą wykonać drugie uwierzytelnianie.

        > [!NOTE]
        > Te adresy URL muszą być poprawnie sformatowanymi nazwami FQDN. Firma Apple wymaga, aby adresy URL miały format `http://<yourURL.domain>`.

        Wzorce dopasowań adresów URL muszą rozpoczynać się od ciągu `http://` lub `https://`. Wykonywane jest proste dopasowanie ciągu, które wykaże, że prefiks adresu URL `http://www.contoso.com/` jest niezgodny z ciągiem `http://www.contoso.com:80/`. W przypadku systemów iOS 10.0 lub nowszych można jednak użyć pojedynczego symbolu wieloznacznego \*, aby wprowadzić wszystkie zgodne wartości. Na przykład wzorzec `http://*.contoso.com/` jest zgodny zarówno z adresem URL `http://store.contoso.com/`, jak i `http://www.contoso.com`.

        Wzorce `http://.com` i `https://.com` są zgodne odpowiednio ze wszystkimi adresami URL HTTP i HTTPS.
    
    - **Aplikacje, które będą korzystały z logowania jednokrotnego**: **dodaj** aplikacje na urządzeniach użytkowników końcowych, które mogą używać logowania jednokrotnego. 

        Tablica `AppIdentifierMatches` musi zawierać ciągi zgodne z identyfikatorami pakietu aplikacji. Te ciągi mogą być dokładnymi dopasowaniami (przykład: `com.contoso.myapp`) lub możesz wprowadzić dopasowanie prefiksu w ramach identyfikatora pakietu za pomocą symbolu wieloznacznego \*. Symbol wieloznaczny musi występować po znaku kropki (.) i może zostać użyty tylko raz — na końcu ciągu (przykład: `com.contoso.*`). Jeśli symbol wieloznaczny zostanie użyty, to dowolna aplikacja o identyfikatorze pakietu rozpoczynającym się od prefiksu uzyskuje dostęp do konta.

        Użyj pola **Nazwa aplikacji**, aby wprowadzić przyjazną nazwę, która ułatwia rozpoznanie identyfikatora pakietu.
    
    - **Certyfikat odnowy poświadczeń**: w przypadku używania certyfikatów w celu uwierzytelniania (nie haseł) wybierz certyfikat SCEP lub PFX wdrożony na potrzeby użytkownika jako certyfikat uwierzytelniania. Zazwyczaj jest to ten sam certyfikat, który został wdrożony dla użytkownika na potrzeby innych profilów, takich jak profil sieci VPN lub Wi-Fi bądź profil poczty e-mail.

6. Wybierz pozycję **OK** > **OK** > **Utwórz**, aby zapisać zmiany i utworzyć profil. Po utworzeniu profil będzie widoczny na liście **Konfiguracja urządzenia — profile**. 

## <a name="next-steps"></a>Następne kroki

Aby uzyskać dodatkowe informacje o konfiguracji funkcji urządzeń, zobacz [Jak skonfigurować ustawienia funkcji urządzeń w usłudze Microsoft Intune](device-features-configure.md).

[Przypisanie tego profilu](device-profile-assign.md) do urządzeń z systemem iOS.
