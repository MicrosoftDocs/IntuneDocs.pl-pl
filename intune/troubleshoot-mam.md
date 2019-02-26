---
title: Rozwiązywanie problemów związanych z zarządzaniem aplikacjami mobilnymi
titlesuffix: Microsoft Intune
description: W tym temacie przedstawiono kilka wskazówek dotyczących rozwiązywania problemów związanych z wdrożeniami dostępu warunkowego.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/21/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ae8113a603ae4c091005f7c82045708f7e9e3e97
ms.sourcegitcommit: 8943848d47d5d5d6e44c74d414c34c5e3457862b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/22/2019
ms.locfileid: "56655395"
---
# <a name="troubleshoot-mobile-application-management"></a>Rozwiązywanie problemów związanych z zarządzaniem aplikacjami mobilnymi

Ten temat zawiera rozwiązania typowych problemów, które wystąpiły podczas zarządzania aplikacjami mobilnymi usługi Intune.

Jeśli te informacje nie pomogą rozwiązać problemu, zobacz [How to get support for Microsoft Intune](get-support.md) (Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune), aby znaleźć więcej sposobów uzyskania pomocy.

## <a name="common-it-administrator-issues"></a>Typowe problemy administratora IT

Są to typowe problemy, które administrator IT może napotkać podczas korzystania z zasad ochrony aplikacji usługi Intune.

| Problem | Opis | Rozwiązanie |
| -- | -- | -- |
| Zasady nie są stosowane w przypadku programu Skype dla firm | Zasady ochrony aplikacji bez rejestracji urządzenia wprowadzone w witrynie Azure Portal nie są stosowane do aplikacji Skype dla firm na urządzeniach z systemem iOS i Android. | Skonfiguruj aplikację Skype dla firm do korzystania z nowoczesnego uwierzytelniania.  Postępuj zgodnie z instrukcjami podanymi w temacie [Zapewnianie dzierżawcy możliwości nowoczesnego uwierzytelniania](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx), aby skonfigurować nowoczesne uwierzytelnianie dla aplikacji Skype. |
| Zasady aplikacji pakietu Office nie są stosowane | Zasady ochrony aplikacji nie są stosowane do żadnej [obsługiwanej aplikacji pakietu Office](https://www.microsoft.com/cloud-platform/microsoft-intune-partners) dla jakiegokolwiek użytkownika. | Potwierdź, że użytkownik ma licencję na usługę Intune oraz że aplikacje pakietu Office są objęte wdrożonymi zasadami ochrony aplikacji. Zastosowanie nowo wdrożonych zasad ochrony aplikacji może potrwać do 8 godzin. |
| Administrator nie może skonfigurować zasad ochrony aplikacji w witrynie Azure Portal | Użytkownik będący administratorem IT nie może skonfigurować zasad ochrony aplikacji w portalu Azure Portal. | Następujące role użytkownika mają dostęp do portalu Azure Portal: <ul><li>Administrator globalny, którego można skonfigurować w [portalu usługi Office](https://portal.office.com/)</li><li>Właściciel, którego można skonfigurować w [portalu Azure](https://portal.azure.com/).</li><li>Współautor, którego można skonfigurować w [portalu Azure](https://portal.azure.com/).</li></ul> W celu uzyskania pomocy podczas konfigurowania tych ról zapoznaj się z tematem [Kontrola dostępu na podstawie ról (kontrola RBAC) w usłudze Microsoft Intune](role-based-access-control.md).|
|W raportach zasad ochrony aplikacji brakuje kont użytkowników | W raportach konsoli administratora nie są widoczne konta użytkowników, dla których niedawno wdrożono zasady ochrony aplikacji. | W przypadku użytkownika niedawno objętego zasadami ochrony aplikacji wyświetlenie informacji na jego temat w raportach może nastąpić po upływie nawet 24 godzin. |
| Zmiany zasad nie działają | Zastosowanie zmian i aktualizacji zasad ochrony aplikacji może potrwać nawet 8 godzin. | Jeśli to konieczne, użytkownik końcowy może wylogować się z aplikacji i zalogować się do niej ponownie, aby wymusić synchronizację z usługą. |
| Zasady ochrony aplikacji nie działają z programem DEP | Zasady ochrony aplikacji nie są stosowane do urządzeń korzystających z programu DEP firmy Apple. | Upewnij się, że używasz koligacji użytkownika na potrzeby programu Device Enrollment Program (DEP) firmy Apple. Koligacja użytkownika jest wymagana dla każdej aplikacji, która wymaga uwierzytelniania użytkownika w ramach programu DEP. <br><br>Artykuł [Automatyczne rejestrowanie urządzeń z systemem iOS w ramach programu Device Enrollment Program firmy Apple](device-enrollment-program-enroll-ios.md) zawiera dalsze informacje na temat rejestracji w ramach programu DEP dla systemu iOS.|
| Zasady transferu danych nie działają w systemie iOS | Zasady **Zezwalaj aplikacji na transfer danych do innych aplikacji** i **Zezwalaj aplikacji na odbieranie danych z innych aplikacji** nie zarządzają pomyślnie transferem danych w systemie iOS. | Zobacz temat [Jak zarządzać przesyłaniem danych między aplikacjami systemu iOS w usłudze Microsoft Intune](data-transfer-between-apps-manage-ios.md). |

## <a name="common-end-user-issues"></a>Typowe problemy użytkowników końcowych

Typowe problemy użytkowników końcowych są podzielone na następujące kategorie:

* **Scenariusze normalnego użycia**: użytkownik końcowy może napotkać te scenariusze w aplikacjach korzystających z zasad ochrony aplikacji usługi Intune. To nie są faktyczne problemy, ale mogą być uważane za usterki lub błędy.

* **Okna dialogowe normalnego użycia**: są to okna dialogowe użycia, które użytkownik końcowy może zobaczyć w aplikacjach korzystających z zasad ochrony aplikacji usługi Intune. Te komunikaty i okna dialogowe **nie** wskazują błędu ani usterki.

* **Okna dialogowe błędów i komunikaty o błędach**: są to okna dialogowe błędów i komunikaty o błędach, które użytkownik końcowy może zobaczyć w aplikacjach korzystających z zasad ochrony aplikacji usługi Intune. Często oznaczają one błąd popełniony przez administratora IT lub usterkę w ochronie aplikacji usługi Intune.

### <a name="normal-usage-scenarios"></a>Scenariusze normalnego użycia

Platforma | Scenariusz | Objaśnienie |
---| --- | --- |
iOS | Użytkownik końcowy może otwierać dane służbowe w aplikacjach niezarządzanych przy użyciu rozszerzenia udostępniania systemu iOS nawet wtedy, gdy zasady transferu danych mają wartość **Tylko aplikacje zarządzane** lub **Brak aplikacji**. Czy te dane nie wyciekają? | Zasady ochrony aplikacji usługi Intune nie mogą kontrolować rozszerzenia udostępniania systemu iOS bez zarządzania tym urządzeniem. W związku z tym **usługa Intune szyfruje dane „firmowe” przed ich udostępnieniem poza aplikację**. Aby to sprawdzić, spróbuj otworzyć plik „firmowy” poza aplikacją zarządzaną. Plik powinien być zaszyfrowany, a jego otworzenie poza aplikacją zarządzaną powinno być niemożliwe.
Android | Dlaczego użytkownik końcowy **musi instalować aplikację Portal firmy** nawet wtedy, gdy używam ochrony aplikacji zarządzania aplikacjami mobilnymi bez rejestracji urządzeń?  | W systemie Android wiele funkcji ochrony aplikacji jest wbudowanych w aplikację Portal firmy. **Rejestracja urządzeń nie jest konieczna, mimo że aplikacja Portal firmy jest zawsze wymagana**. Aby korzystać z ochrony aplikacji bez rejestracji, użytkownik końcowy po prostu musi mieć zainstalowaną aplikację Portal firmy na urządzeniu.

### <a name="normal-usage-dialogs"></a>Okna dialogowe normalnego użycia

Platforma | Komunikat lub okno dialogowe | Objaśnienie |
--- | --- | --- |
iOS, Android | **Logowanie**: Twoja organizacja musi zarządzać tą aplikacją, aby chronić swoje dane. Aby wykonać tę akcję, zaloguj się za pomocą konta służbowego. | Użytkownik końcowy musi zalogować się przy użyciu swojego konta służbowego w celu korzystania z tej aplikacji, co wymaga zasad ochrony aplikacji. Aby zasady były stosowane, użytkownik musi uwierzytelnić się w usłudze Azure Active Directory.
iOS, Android |**Wymagane ponowne uruchomienie**: Twoja organizacja chroni teraz dane w tej aplikacji. Aby kontynuować, musisz ponownie uruchomić aplikację. | Aplikacja właśnie uzyskała zasady ochrony aplikacji usługi Intune i musi zostać ponownie uruchomiona, aby je zastosować.
iOS, Android |**Niedozwolona akcja**: Twoja organizacja pozwala na otwieranie tylko danych służbowych w tej aplikacji. | Administrator IT ustawił pozycję **Zezwalaj aplikacji na odbieranie danych z innych aplikacji** na wartość **Tylko aplikacje zarządzane**. W związku z tym użytkownik końcowy może transferować dane do tej aplikacji jedynie z innych aplikacji korzystających z zasad ochrony aplikacji.
iOS, Android |**Niedozwolona akcja**: Twoja organizacja pozwala na przesyłanie jej danych tylko do innych zarządzanych aplikacji. | Administrator IT ustawił pozycję **Zezwalaj aplikacji na transfer danych do innych aplikacji** na wartość **Tylko aplikacje zarządzane**. W związku z tym użytkownik końcowy może transferować dane z tej aplikacji jedynie do innych aplikacji korzystających z zasad ochrony aplikacji.
iOS, Android |**Alert dotyczący czyszczenia**: Twoja organizacja usunęła swoje dane skojarzone z tą aplikacją. Aby kontynuować, uruchom ponownie aplikację. | Administrator IT zainicjował czyszczenie aplikacji za pomocą ochrony aplikacji usługi Intune.
Android | **Aplikacja Portal firmy jest wymagana**: aby w tej aplikacji korzystać z konta służbowego, musisz zainstalować aplikację Portal firmy dla usługi Intune. Kliknij pozycję „Przejdź do sklepu”, aby kontynuować. | W systemie Android wiele funkcji ochrony aplikacji jest wbudowanych w aplikację Portal firmy. **Rejestracja urządzeń nie jest konieczna, mimo że aplikacja Portal firmy jest zawsze wymagana**. Aby korzystać z ochrony aplikacji bez rejestracji, użytkownik końcowy po prostu musi mieć zainstalowaną aplikację Portal firmy na urządzeniu.

### <a name="error-messages-and-dialogs-on-ios"></a>Okna dialogowe błędów i komunikaty o błędach w systemie iOS

Okno dialogowe błędu lub komunikat o błędzie | Przyczyna | Korekty |
-- | --- | --- |
**Nie skonfigurowano aplikacji**: możliwość korzystania z tej aplikacji nie została skonfigurowana w Twoim przypadku. Skontaktuj się z administratorem IT, aby uzyskać pomoc. | Nie można wykryć zasad ochrony wymaganych dla tej aplikacji. |Upewnij się, zasady ochrony aplikacji systemu iOS są wdrożone w grupie zabezpieczeń użytkownika i obejmują tę aplikację.
**Intune Managed Browser — Zapraszamy**: ta aplikacja działa najlepiej, gdy jest zarządzana przez usługę Microsoft Intune. Możesz przeglądać sieć Web za pomocą tej aplikacji, a jeśli jest ona zarządzana przez usługę Microsoft Intune, uzyskasz dostęp do dodatkowych funkcji ochrony danych. | Nie można wykryć zasad ochrony wymaganych dla aplikacji Intune Managed Browser. <br><br>Użytkownik nadal może korzystać z tej aplikacji do przeglądania sieci Web, ale nie jest ona zarządzana przez usługę Intune. | Upewnij się, zasady ochrony aplikacji systemu iOS są wdrożone w grupie zabezpieczeń użytkownika i obejmują aplikację Intune Managed Browser.
**Logowanie nie powiodło się**: nie możemy Cię zalogować w tej chwili. Spróbuj ponownie później. | Nie można zarejestrować użytkownika przy użyciu usługi MAM po dokonaniu próby logowania z użyciem konta służbowego. | Upewnij się, zasady ochrony aplikacji systemu iOS są wdrożone w grupie zabezpieczeń użytkownika i obejmują tę aplikację.
**Nie skonfigurowano konta**: Twoja organizacja nie skonfigurowała na Twoim koncie dostępu do danych służbowych. Skontaktuj się z administratorem działu IT w celu uzyskania pomocy. | Konto użytkownika nie ma licencji Intune A Direct. | Upewnij się, że konto użytkownika ma przypisaną licencję usługi Intune w [portalu pakietu Office](https://portal.office.com).
**Niezgodne urządzenie**: nie można użyć tej aplikacji, ponieważ używasz urządzenia z usuniętymi ograniczeniami. Skontaktuj się z administratorem IT, aby uzyskać pomoc. | Usługa Intune wykryła, że użytkownik korzysta z urządzenia ze zdjętymi zabezpieczeniami systemu. | Przywróć ustawienia fabryczne urządzenia. Postępuj zgodnie z [tymi instrukcjami](https://support.apple.com/HT201274) z witryny pomocy technicznej firmy Apple.
**Wymagane jest połączenie z Internetem**: aby zweryfikować, czy możesz używać tej aplikacji, musisz mieć połączenie z Internetem. | Urządzenie nie jest połączone z Internetem. | Połącz urządzenie z siecią Wi-Fi lub siecią transmisji danych.
**Nieznany błąd**: spróbuj ponownie uruchomić tę aplikację. Jeśli ten problem będzie nadal występować, skontaktuj się z administratorem działu IT w celu uzyskania pomocy. | Wystąpił nieznany błąd. | Poczekaj chwilę i spróbuj ponownie. Jeśli błąd będzie nadal występować, utwórz [bilet pomocy technicznej](get-support.md#create-an-online-support-ticket) w usłudze Intune.
**Uzyskiwanie dostępu do danych organizacji**: podane konto służbowe nie ma dostępu do tej aplikacji. Może być konieczne zalogowanie się przy użyciu innego konta. Skontaktuj się z administratorem IT, aby uzyskać pomoc. | Usługa Intune wykryła, że użytkownik próbował zalogować się przy użyciu drugiego konta służbowego, które różni się od konta zarejestrowanego w oprogramowaniu do zarządzania aplikacjami mobilnymi (MAM) dla tego urządzenia. Oprogramowanie MAM może zarządzać jednocześnie tylko jednym kontem służbowym na danym urządzeniu. | Zaloguj się przy użyciu konta, którego nazwa użytkownika jest wstępnie wypełniona na ekranie logowania. <br> <br> Ewentualnie zaloguj się przy użyciu nowego konta służbowego i usuń istniejące konto zarejestrowane w oprogramowaniu MAM.
**Problem z połączeniem**: wystąpił nieoczekiwany problem z połączeniem. Sprawdź połączenie i spróbuj ponownie.  |  Nieoczekiwany błąd. | Poczekaj chwilę i spróbuj ponownie. Jeśli błąd będzie nadal występować, utwórz [bilet pomocy technicznej](get-support.md#create-an-online-support-ticket) w usłudze Intune.
**Alert**: nie można już używać tej aplikacji. Aby uzyskać więcej informacji, skontaktuj się z administratorem działu IT. | Nie można zweryfikować certyfikatu aplikacji. | Upewnij się, że używana wersja aplikacji jest aktualna. <br><br> Zainstaluj aplikację ponownie.
**Błąd**: ta aplikacja napotkała problem i musi zostać zamknięta. Jeśli ten błąd będzie się powtarzać, skontaktuj się z administratorem działu IT. | Nie można odczytać numeru PIN aplikacji MAM z pęku kluczy systemu Apple iOS. | Uruchom urządzenie ponownie. Upewnij się, że używana wersja aplikacji jest aktualna. <br><br> Zainstaluj aplikację ponownie.

### <a name="error-messages-and-dialogs-on-android"></a>Okna dialogowe błędów i komunikaty o błędach w systemie Android

Okno dialogowe/komunikat o błędzie | Przyczyna | Korekty |
-- | --- | --- |
**Nie skonfigurowano aplikacji**: możliwość korzystania z tej aplikacji nie została skonfigurowana w Twoim przypadku. Skontaktuj się z administratorem IT, aby uzyskać pomoc. | Nie można wykryć zasad ochrony wymaganych dla tej aplikacji. |Upewnij się, że zasady ochrony aplikacji systemu Android są wdrożone w grupie zabezpieczeń użytkownika i obejmują tę aplikację.
**Uruchomienie aplikacji nie powiodło się**: wystąpił problem podczas uruchamiania aplikacji. Spróbuj zaktualizować aplikację lub aplikację Portal firmy usługi Intune. Jeśli potrzebujesz pomocy, skontaktuj się z administratorem IT. | Usługa Intune wykryła prawidłowe zasady ochrony dla tej aplikacji, ale podczas inicjowania oprogramowania MAM występuje awaria aplikacji. | Upewnij się, że używana wersja aplikacji jest aktualna. <br><br> Upewnij się, że aplikacja Portal firmy usługi Intune jest zainstalowana na urządzeniu i jest aktualna. <br><br> Jeśli błąd będzie się powtarzać, wyślij dzienniki do usługi Intune przy użyciu aplikacji Portal firmy lub utwórz [bilet pomocy technicznej](get-support.md#create-an-online-support-ticket).
**Nie znaleziono aplikacji**: na tym urządzeniu nie ma żadnych aplikacji, którym organizacja zezwala na otwieranie tej zawartości. Skontaktuj się z administratorem IT, aby uzyskać pomoc. | Użytkownik próbował otworzyć dane służbowe za pomocą innej aplikacji, ale usługa Intune nie można odnaleźć żadnych innych zarządzanych aplikacji, które mają zezwolenie na otwieranie tych danych. | Upewnij się, zasady ochrony aplikacji systemu Android są wdrożone w zabezpieczeniach użytkownika i obejmują co najmniej jedną inną aplikację z obsługą zarządzania aplikacjami mobilnymi (MAM), przy użyciu której można otworzyć te dane.
**Logowanie nie powiodło się**: spróbuj zalogować się ponownie. Jeśli problem będzie się powtarzać, skontaktuj się z administratorem IT w celu uzyskania pomocy. | Nie można uwierzytelnić konta, przy użyciu którego użytkownik próbował się zalogować. | Upewnij się, że użytkownik loguje się przy użyciu konta służbowego, które jest już zarejestrowane w usłudze Intune MAM (pierwszego konta służbowego, przy użyciu którego wykonano pomyślne logowanie w tej aplikacji). <br><br> Wyczyść dane aplikacji. <br><br> Upewnij się, że używana wersja aplikacji jest aktualna. <br><br> Upewnij się, że wersja aplikacji Portal firmy jest aktualna.
**Wymagane jest połączenie z Internetem**: aby zweryfikować, czy możesz używać tej aplikacji, musisz mieć połączenie z Internetem. | Urządzenie nie jest połączone z Internetem. | Połącz urządzenie z siecią Wi-Fi lub siecią transmisji danych.
**Niezgodne urządzenie**: nie można korzystać z tej aplikacji, ponieważ używane przez Ciebie urządzenie ma dostęp do konta root. Skontaktuj się z administratorem IT, aby uzyskać pomoc. | Usługa Intune wykryła, że użytkownik korzysta z urządzenia z odblokowanym dostępem. | Przywróć ustawienia fabryczne urządzenia.
**Nie skonfigurowano konta**: ta aplikacja musi być zarządzana przez usługę Microsoft Intune, ale Twoje konto nie zostało skonfigurowane. Skontaktuj się z administratorem IT, aby uzyskać pomoc. | Konto użytkownika nie ma licencji Intune A Direct. | Upewnij się, że konto użytkownika ma przypisaną licencję usługi Intune w [portalu pakietu Office](https://portal.office.com).
**Nie można zarejestrować aplikacji**: ta aplikacja musi być zarządzana przez usługę Microsoft Intune, ale w tej chwili nie udało nam się jej zarejestrować. Skontaktuj się z administratorem IT, aby uzyskać pomoc. | Nie można automatycznie zarejestrować aplikacji przy użyciu usługi zarządzania aplikacjami mobilnymi, gdy wymagane są zasady ochrony aplikacji. | Wyczyść dane aplikacji. <br><br> Wyślij dzienniki do usługi Intune za pomocą aplikacji Portal firmy lub utwórz bilet pomocy technicznej. Aby uzyskać więcej informacji, zobacz [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](get-support.md).

## <a name="next-steps"></a>Następne kroki

- [Weryfikowanie konfiguracji zarządzania aplikacjami mobilnymi](app-protection-policies-validate.md)
- Aby uzyskać dodatkowe informacje dotyczące rozwiązywania problemów z usługą Intune, zobacz [Korzystanie z portalu rozwiązywania problemów, aby pomóc użytkownikom w firmie](help-desk-operators.md). 
- Dowiedz się więcej o wszelkich znanych problemach w usłudze Microsoft Intune. Aby uzyskać więcej informacji, zobacz [Znane problemy w usłudze Microsoft Intune](known-issues.md).
- Potrzebujesz dodatkowej pomocy? Zobacz [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](get-support.md).
