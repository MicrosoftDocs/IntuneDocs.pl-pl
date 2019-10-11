---
title: Tworzenie profilu urządzenia z systemem iOS lub macOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodaj lub utwórz profil urządzenia z systemem iOS lub macOS, a następnie skonfiguruj ustawienia funkcji AirPrint, układu ekranu głównego, powiadomień aplikacji, urządzenia udostępnionego, logowania jednokrotnego i filtru zawartości internetowej w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 83328652c366eea6e1a3cbb81ea4979d8844a96b
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71724194"
---
# <a name="add-ios-or-macos-device-feature-settings-in-intune"></a>Dodawanie ustawień funkcji urządzenia z systemem iOS lub macOS w usłudze Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Usługa Intune oferuje wiele funkcji i ustawień, które pomagają administratorom kontrolować urządzenia z systemami iOS i macOS. Administratorzy mogą na przykład:

- Zezwalać użytkownikom na dostęp do drukarek AirPrint w sieci
- Dodawać aplikacje i foldery do ekranu głównego, w tym dodawać nowe strony
- Wybierać, czy i jak będą wyświetlane powiadomienia w aplikacji
- Konfigurować ekran blokady, aby pokazywać komunikat lub tag zasobu, szczególnie w przypadku urządzeń udostępnionych
- Oferować użytkownikom bezpieczne środowisko logowania jednokrotnego w celu udostępniania poświadczeń między aplikacjami
- Filtrować witryny internetowe, które używają języka dla dorosłych, oraz zezwalać na określone witryny internetowe lub je blokować

„Profile konfiguracji” są używane w usłudze Intune do tworzenia i dostosowywania tych ustawień na potrzeby organizacji. Po dodaniu tych funkcji w profilu można następnie wypychać lub wdrażać profil na urządzeniach z systemem iOS i macOS w organizacji.

Ten artykuł opisuje różne możliwe do skonfigurowania funkcje, a także pokazuje, jak utworzyć profil konfiguracji urządzenia. Zawiera on również listę wszystkich dostępnych ustawień dla urządzeń z systemem [iOS](ios-device-features-settings.md) i [macOS](macos-device-features-settings.md).

## <a name="airprint"></a>Funkcja AirPrint

AirPrint to funkcja firmy Apple, która umożliwia urządzeniom drukowanie plików za pośrednictwem sieci bezprzewodowej. W usłudze Intune możesz dodać do urządzeń informacje o funkcji AirPrint.

Aby uzyskać listę ustawień, jakie można skonfigurować w usłudze Intune, patrz [AirPrint w systemie iOS](ios-device-features-settings.md#airprint) oraz [AirPrint w systemie macOS](macos-device-features-settings.md#airprint).

Więcej informacji na temat funkcji AirPrint można znaleźć w sekcji [Informacje o funkcji AirPrint](https://support.apple.com/HT201311) w witrynie internetowej firmy Apple.

Dotyczy:

- System iOS 7.0 i nowsze
- System iPadOS 13.0 i nowsze
- System macOS 10.10 i nowsze

## <a name="app-notifications"></a>Powiadomienia aplikacji

Wybierz sposób odbierania powiadomień przez aplikacje na urządzeniach z systemem iOS i urządzeniach iPad. W usłudze Intune możesz na przykład wysyłać powiadomienia aplikacji tak, aby były wyświetlane w centrum powiadomień, na ekranie blokady lub odtwarzały dźwięk.

Aby zapoznać się z listą ustawień, jakie można skonfigurować w usłudze Intune, patrz [Powiadomienia aplikacji w systemie iOS](ios-device-features-settings.md#app-notifications).

Więcej informacji na temat tej funkcji można znaleźć w sekcji [Powiadomienia](https://developer.apple.com/notifications/) w witrynie internetowej firmy Apple.

Dotyczy:

- System iOS 9.3 i nowsze
- System iPadOS 13.0 i nowsze

## <a name="associated-domains"></a>Powiązane domeny

Skojarzone domeny umożliwiają utworzenie relacji pomiędzy domenami, np. `contoso.com`, a aplikacjami. Ta funkcja pozwala:

- Udostępniać dane i oraz poświadczenia pomiędzy aplikacjami i witrynami w organizacji.
- Korzystać z funkcji aplikacji opartych na witrynie internetowej firmy, takich jak rozszerzenie aplikacji do rejestracji jednokrotnej, łącza uniwersalne czy autowypełnianie haseł.

  Możesz utworzyć powiązaną domenę, aby zezwolić funkcji autowypełniania hasła na rekomendowanie poświadczeń, na przykład hasła, w witrynach powiązanych z Twoją aplikacją.

Aby uzyskać listę ustawień, jakie można skonfigurować w usłudze Intune, patrz [Powiązane domeny w systemie macOS](macos-device-features-settings.md#associated-domains).

Więcej informacji na temat tej funkcji można znaleźć w artykule [Setting Up an App’s Associated Domains](https://developer.apple.com/documentation/security/password_autofill/setting_up_an_app_s_associated_domains) (Konfigurowanie domen powiązanych aplikacji) w witrynie internetowej firmy Apple.

Dotyczy:

- System macOS 10.15 i nowsze

## <a name="home-screen-layout"></a>Układ ekranu głównego

Te ustawienia umożliwiają konfigurowanie układu aplikacji i folderów w obszarze dokowania i na ekranie głównym urządzeń z systemem iOS i iPadOS. Można:

- Użyj ustawień **Dock**, aby dodać do ekranu aplikacje lub foldery. W panelu dok urządzenia możesz na przykład wyświetlić przeglądarkę Safari i aplikację poczty e-mail.
- Dodaj **strony**, które mają być wyświetlane na ekranie głównym, oraz aplikacje, które mają być wyświetlane na każdej ze stron. Możesz na przykład dodać stronę **Contoso** i dodać do niej aplikację Ustawienia.

Aby poznać listę ustawień, jakie można skonfigurować w usłudze Intune, patrz [Układ ekranu głównego w systemie iOS](ios-device-features-settings.md#home-screen-layout).

Dotyczy:

- System iOS 9.3 i nowsze
- System iPadOS 13.0 i nowsze

## <a name="lock-screen-message"></a>Komunikat na ekranie blokady

Te ustawienia pozwalają wyświetlać niestandardowe komunikaty lub tekst w oknie logowania i na ekranie blokady. Możesz na przykład wprowadzić komunikat „W razie zgubienia zwróć do” oraz wyświetlić informacje dotyczące tagu zasobu.

Aby poznać listę ustawień, jakie można skonfigurować w usłudze Intune, patrz [Ustawienia komunikatów na ekranie blokady w systemie iOS](ios-device-features-settings.md#lock-screen-message).

Więcej informacji na temat komunikatu na ekranie blokady można znaleźć na stronie [Komunikat na ekranie blokady](https://developer.apple.com/documentation/devicemanagement/lockscreenmessage) w witrynie internetowej firmy Apple.

Dotyczy:

- System iOS 9.3 i nowsze
- System iPadOS 13.0 i nowsze

## <a name="login-items"></a>Elementy logowania

Ta funkcja pozwala wybrać, które aplikacje, niestandardowych aplikacje, pliki i foldery zostaną otwarte, gdy użytkownicy zalogują się na swoich urządzeniach. 

Aby poznać listę ustawień, jakie można skonfigurować w usłudze Intune, patrz [Elementy logowania w systemie macOS](macos-device-features-settings.md#login-items).

Dotyczy:

- System macOS 10.13 i nowsze

## <a name="login-window"></a>Okno logowania

Kontrolowanie wyglądu ekranu logowania i funkcji dostępnych dla użytkowników przed zalogowaniem się. Możesz na przykład dodać baner z niestandardowym komunikatem, wybrać, czy będzie wyświetlany przycisk uśpienia itp.

Aby poznać listę ustawień, jakie można skonfigurować w usłudze Intune, patrz [Okno logowania w systemie macOS](macos-device-features-settings.md#login-window).

Dotyczy:

- System macOS 10.7 i nowsze

## <a name="single-sign-on"></a>Logowanie jednokrotne

Większość aplikacji biznesowych (LOB, Line of Business) wymaga pewnego poziomu uwierzytelniania użytkowników w celu obsługi zabezpieczeń. W wielu przypadkach uwierzytelnianie wymaga od użytkownika wielokrotnego wprowadzenia tych samych poświadczeń. Aby ulepszyć środowisko użytkownika, deweloperzy mogą tworzyć aplikacje korzystające z logowania jednokrotnego. Użycie logowania jednokrotnego zmniejsza liczbę operacji wprowadzania poświadczeń przez użytkownika.

Aby korzystać z logowania jednokrotnego, upewnij się, że masz:

- Aplikację poszukującą magazynu poświadczeń użytkownika w logowaniu jednokrotnym na urządzeniu.
- Usługa Intune musi być skonfigurowana na potrzeby logowania jednokrotnego dla urządzeń z systemem iOS.

![Okienko Logowanie jednokrotne](./media/device-features-configure/sso-blade.png)

Aby poznać listę ustawień, jakie można skonfigurować w usłudze Intune, patrz [Rejestracja jednokrotna w systemie iOS](ios-device-features-settings.md#single-sign-on).

Dotyczy:

- System iOS 7.0 i nowsze
- System iPadOS 13.0 i nowsze

## <a name="single-sign-on-app-extension"></a>Rozszerzenie aplikacji — rejestracja jednokrotna

Te ustawienia konfigurują rozszerzenie aplikacji umożliwiające rejestrację jednokrotną (SSO) na urządzeniach z systemem iOS, iPadOS i macOS. Większość aplikacji biznesowych (LOB) i witryn organizacji wymaga pewnego poziomu bezpiecznego uwierzytelniania użytkowników. W wielu przypadkach uwierzytelnianie wymaga od użytkowników wielokrotnego wprowadzania tych samych poświadczeń. Referencja jednokrotna daje użytkownikom dostęp do aplikacji i witryn internetowych po jednorazowym wprowadzeniu poświadczeń. Po zalogowaniu użytkownicy mają automatyczny dostęp do aplikacji i witryn internetowych, ale mogą również w tym celu używać funkcji Face ID lub Touch ID albo kodu dostępu Apple.

Użyj tych ustawień w usłudze Intune, aby skonfigurować wbudowane rozszerzenie protokołu Kerberos firmy Apple lub skonfigurować rozszerzenie aplikacji SSO utworzone przez Twoją organizację. Rozszerzenie aplikacji SSO obsługuje uwierzytelnianie użytkowników. Te ustawienia służą do konfigurowania rozszerzeń aplikacji SSO z poświadczeniami, opracowanych pod kątem przepływów uwierzytelniania typu wyzwanie-odpowiedź. Istnieje możliwość wyboru pomiędzy dostarczonym przez firmę Apple rozszerzeniem poświadczeń dostosowanym do protokołu Kerberos a ogólnym rozszerzeniem poświadczeń.

Aby poznać listę ustawień, jakie można skonfigurować w usłudze Intune, patrz [Rozszerzenie aplikacji SSO w systemie iOS](ios-device-features-settings.md#single-sign-on-app-extension) oraz [Rozszerzenie aplikacji SSO w systemie macOS](macos-device-features-settings.md#single-sign-on-app-extension).

Aby uzyskać więcej informacji na temat tworzenia rozszerzenia aplikacji SSO, obejrzyj materiał [Extensible Enterprise SSO](https://developer.apple.com/videos/play/tech-talks/301) w witrynie internetowej Apple.

> [!NOTE]
> Funkcja **rozszerzenia aplikacji SSO** różni się od funkcji **rejestracji jednokrotnej**:
>
> - Ustawienia **rozszerzenia aplikacji SSO** mają zastosowanie w systemie iPadOS 13.0 (i nowszych) oraz systemie iOS 13.0 (i nowszych). Ustawienia funkcji **rejestracji jednokrotnej** mają zastosowanie w systemie iPadOS 13.0 (i nowszych) oraz systemie iOS 7.0 (i nowszych).
> - **Rozszerzenie aplikacji SSO** obsługuje uwierzytelnianie w systemie operacyjnym. W przypadku funkcji **rejestracji jednokrotnej** uwierzytelnianie obsługuje konkretna aplikacja.
> - Korzystając z **rozszerzenia aplikacji SSO**, użytkownicy logują się do aplikacji i witryn internetowych automatycznie. Alternatywnie mogą też użyć funkcji Face ID lub Touch ID albo kodu PIN lub hasła firmy Apple. Korzystając z funkcji **rejestracji jednokrotnej**, użytkownicy logują się do aplikacji i witryn internetowych przy użyciu innej aplikacji.
>
>    **Rozszerzenie aplikacji SSO** korzysta w celu uwierzytelniania z systemu operacyjnego Apple. Może więc zapewnić lepsze środowisko użytkownika końcowego.
>
> - Z perspektywy dewelopera **rozszerzenie aplikacji SSO** może używać dowolnego typu uwierzytelniania SSO poświadczeń. W przypadku **rejestracji jednokrotnej** można korzystać wyłącznie z uwierzytelniania SSO za pomocą protokołu Kerberos.  

Dotyczy:

- System iOS 13.0 i nowsze
- System iPadOS 13.0 i nowsze
- System macOS 10.15 i nowsze

## <a name="wallpaper"></a>Tapeta

Dodaj niestandardowy obrazu PNG, JPG lub JPEG na urządzeniach nadzorowanych z systemem iOS. Na przykład możesz dodać za pomocą usługi Intune logo firmy do ekranu blokady na urządzeniach.

Aby poznać listę ustawień, jakie można skonfigurować w usłudze Intune, patrz [Tapeta w systemie iOS](ios-device-features-settings.md#wallpaper).

Dotyczy:

- iOS
- System iPadOS 13.0 i nowsze

## <a name="web-content-filter"></a>Filtr zawartości sieci Web

Te ustawienia mogą korzystać z wbudowanego algorytmu autofiltrowania firmy Apple w celu oceniania stron sieci Web oraz blokowania zawartości dla dorosłych oraz wulgarnego języka. Można również utworzyć listę linków sieci Web z ograniczeniami oraz bez ograniczeń. Na przykład możesz zezwolić wyłącznie na otwieranie witryn sieci Web `contoso`.

Aby poznać listę ustawień, jakie można skonfigurować w usłudze Intune, patrz [Filtr zawartości sieci Web dla systemu iOS](ios-device-features-settings.md#web-content-filter).

Dotyczy:

- System iOS 7.0 i nowsze
- System iPadOS 13.0 i nowsze

## <a name="create-a-device-profile"></a>Tworzenie profilu urządzenia

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Wprowadź następujące właściwości:

    - **Nazwa**: wprowadź opisową nazwę zasad. Nadaj nazwę zasadom, aby można było je później łatwo rozpoznać. Na przykład dobrą nazwą zasad jest **macOS: Konfiguruje ekran logowania**.
    - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: Wybierz platformę urządzeń. Dostępne opcje:  
        - **iOS/iPadOS**
        - **macOS**
    - **Typ profilu**: wybierz pozycję **Funkcje urządzenia**.

4. Ustawienia, które można skonfigurować, różnią się w zależności od wybranej platformy. Wybierz platformę dla ustawień szczegółowych:

    - [iOS/iPadOS](ios-device-features-settings.md)
    - [macOS](macos-device-features-settings.md)

5. Po zakończeniu wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany.

Profil zostanie utworzony i wyświetlony na liście profilów. Pamiętaj, aby [przypisać profil](device-profile-assign.md) i [monitorować jego stan](device-profile-monitor.md).

## <a name="next-steps"></a>Następne kroki

Po utworzeniu profil jest gotowy do przypisania. W dalszej części [przypiszesz profil](device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).

Wyświetl wszystkie ustawienia funkcji urządzenia dla urządzeń z systemem [iOS](ios-device-features-settings.md) i [macOS](macos-device-features-settings.md).
