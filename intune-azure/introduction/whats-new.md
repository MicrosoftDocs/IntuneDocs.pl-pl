---
title: "Co nowego w wersji zapoznawczej usługi Microsoft Intune"
titleSuffix: Intune Azure preview
description: "Dowiedz się, co nowego w wersji zapoznawczej usługi Intune platformy Azure"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/17/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 671d862c8d9a98e02f33d96cf6ceba712e740dec
ms.openlocfilehash: 586bdab54ee60ba8d620857ab3506aa27622d17a
ms.lasthandoff: 03/17/2017

---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>Co nowego w wersji zapoznawczej usługi Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

W miarę rozwoju wersji zapoznawczej i dodawania kolejnych funkcji będziemy Cię o nich tutaj powiadamiać.

> [!Note]
> Stopniowo wprowadzamy zmiany wymienione na tej stronie wersji zapoznawczej portalu Azure. Jednak zmiany mogą nie być dostępne od razu ze względu na sposób aktualizacji usługi Intune.  Zanim nowe funkcje staną się dostępne, niektóre składniki usługi muszą zostać zaktualizowane sekwencyjnie. Szukaj tych zmian w miarę ich sukcesywnego wdrażania w tym miesiącu.

## <a name="march-2017"></a>Marzec 2017

### <a name="support-for-ios-lost-mode---431695--"></a>Obsługa trybu utraty w systemie iOS<!--431695-->

Dla urządzeń z systemem iOS w wersji 9.3 i późniejszych w usłudze Intune dodano obsługę **trybu utraty**. Teraz możesz zablokować urządzenie, aby uniemożliwić jego użycie w jakikolwiek sposób, oraz wyświetlić komunikat i numer telefonu kontaktowego na ekranie blokady urządzenia.

Użytkownik końcowy nie będzie mógł odblokować urządzenia aż do chwili, gdy administrator wyłączy tryb utraty. Po włączeniu trybu utraty można skorzystać z akcji **Zlokalizuj urządzenie**, aby wyświetlić w konsoli usługi Intune lokalizację geograficzną urządzenia na mapie.

Urządzenie musi być urządzeniem z systemem iOS, należącym do firmy, zarejestrowanym w usłudze DEP i objętym trybem nadzorowanym.

Aby uzyskać więcej informacji, zobacz artykuł [Co to jest zarządzanie urządzeniami w usłudze Microsoft Intune?](/intune-azure/manage-devices/what-is)

### <a name="improvements-to-device-actions-report---677150--"></a>Ulepszenia w zakresie raportu dotyczącego akcji związanych z urządzeniami <!--677150-->

Wprowadziliśmy ulepszenia w zakresie raportu dotyczącego akcji związanych z urządzeniami w celu zwiększenia wydajności. Ponadto raport można teraz filtrować według stanu. Można na przykład filtrować raport w taki sposób, aby wyświetlić tylko te akcje związane z urządzeniem, które zostały zakończone.

### <a name="actions-for-non-compliance---730266--"></a>Akcje w przypadku niezgodności <!--730266-->

**Akcje w przypadku niezgodności** to nowa funkcja zasad zgodności, która umożliwia podejmowanie akcji na urządzeniach, które są niezgodne. Możesz określić jedną lub wiele akcji oraz przedział czasu, w którym te akcje muszą zostać wykonane. Na przykład możesz za pomocą poczty e-mail powiadomić użytkowników niezgodnych urządzeń, gdy tylko ich urządzenia staną się niezgodne, lub za pośrednictwem dostępu warunkowego zablokować niezgodnym urządzeniom dostęp do zasobów firmowych po 3-dniowym okresie karencji.

### <a name="custom-app-categories---748805--"></a>Niestandardowe kategorie aplikacji <!--748805-->

Możesz teraz tworzyć, edytować i przypisywać kategorie dla aplikacji dodawanych do usługi Intune. Obecnie kategorie można określać tylko w języku angielskim.
Zobacz [Jak dodać aplikację do usługi Intune](/intune-azure/manage-apps/add-apps).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>Przypisywanie aplikacji biznesowych do użytkowników z wyrejestrowanymi urządzeniami <!--748823-->

Użytkownikom można teraz przypisywać aplikacje biznesowe ze sklepu niezależnie od tego, czy ich urządzenia są zarejestrowane w usłudze Intune. Jeśli urządzenie użytkownika nie jest zarejestrowane w usłudze Intune, w celu jej zainstalowania użytkownik musi przejść do witryny sieci Web Portal firmy zamiast do aplikacji Portal firmy.

### <a name="new-compliance-reports---846671--"></a>Nowe raporty dotyczące zgodności <!--846671-->

Można teraz korzystać z raportów zgodności, które dostarczają informacje na temat stanu zgodności urządzeń w Twojej firmie i pozwalają na szybkie rozwiązywanie problemów ze zgodnością napotykanych przez użytkowników. Możliwe jest wyświetlanie informacji dotyczących następujących kwestii:

- ogólny stan zgodności urządzeń,
- stan zgodności poszczególnych ustawień,
- stan zgodności poszczególnych zasad.

Raportów można także użyć do przechodzenia do informacji szczegółowych dotyczących poszczególnych urządzeń, aby wyświetlić konkretne ustawienia i zasady, które mają wpływ na to urządzenie.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Bezpośredni dostęp do scenariuszy rejestracji firmy Apple <!--951869-->

Na kontach usługi Intune utworzonych po styczniu 2017 roku włączono bezpośredni dostęp do scenariuszy rejestracji firmy Apple przy użyciu obciążenia Rejestruj urządzenia w portalu Azure w wersji zapoznawczej. Wcześniej podgląd rejestracji firmy Apple był dostępny tylko z poziomu linków w klasycznym portalu Intune. Konta usługi Intune utworzone przed styczniem 2017 będą wymagać przeprowadzenia jednorazowej migracji, zanim funkcje te będą dostępne w systemie Azure. Harmonogram migracji nie został jeszcze ogłoszony, ale szczegółowe informacje zostaną udostępnione najszybciej, jak będzie to możliwe. Zdecydowanie zalecamy utworzenie konta w wersji próbnej w celu przetestowania nowego środowiska pracy w przypadku, gdy istniejące konto nie ma dostępu do podglądu.


## <a name="february-2017"></a>Luty 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Możliwość ograniczenia rejestracji urządzeń przenośnych <!--747600, 795782-->
Usługa Intune dodaje nowe ograniczenia rejestracji, które pozwalają kontrolować, które platformy urządzeń przenośnych mogą być rejestrowane. Usługa Intune dzieli platformy urządzeń przenośnych na iOS, macOS, Android, Windows i Windows Mobile.

* Ograniczanie rejestracji urządzeń przenośnych nie ogranicza rejestracji klientów komputerów stacjonarnych.  
* Tylko w przypadku systemu iOS i Android istnieje dodatkowa opcja blokowania rejestracji urządzeń, które są własnością osobistą.

Intune oznacza wszystkie nowe urządzenia jako osobiste, chyba że administrator IT oznaczy je jako własność firmową, zgodnie z opisem [w tym artykule](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).

### <a name="view-all-actions-on-managed-devices---677150--"></a>Wyświetlanie wszystkich akcji na urządzeniach zarządzanych <!--677150-->
Nowy raport __Akcje urządzenia__ pokazuje, kto wykonał akcje zdalne, takie jak przywrócenie stanu fabrycznego na urządzeniach, a ponadto wyświetla stan takich akcji. Zobacz [Co to jest zarządzanie urządzeniami?](https://docs.microsoft.com/intune-azure/manage-devices/what-is).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Urządzenia niezarządzane mają dostęp do przypisanych aplikacji <!--664691-->
W ramach zmian wyglądu witryny internetowej Portal firmy użytkownicy systemów iOS i Android będą mogli instalować na swoich urządzeniach niezarządzanych aplikacje przypisane im jako „dostępne bez rejestracji”. Przy użyciu poświadczeń usługi Intune użytkownicy mogą zalogować się do witryny internetowej Portal firmy i wyświetlić listę przypisanych im aplikacji. Pakiety aplikacji oznaczonych jako „dostępne bez rejestracji” są udostępniane do pobrania za pośrednictwem witryny internetowej Portal firmy. Ta zmiana nie ma wpływu na aplikacje, które wymagają rejestracji na potrzeby instalacji, ponieważ użytkownicy, którzy zechcą zainstalować te aplikacje, zobaczą monit o zarejestrowanie ich urządzenia.

### <a name="custom-app-categories---748805--"></a>Niestandardowe kategorie aplikacji <!--748805-->
Możesz teraz tworzyć, edytować i przypisywać kategorie dla aplikacji dodawanych do usługi Intune. Obecnie kategorie można określać tylko w języku angielskim.
Zobacz [Jak dodać aplikację do usługi Intune](/intune-azure/manage-apps/add-apps).

### <a name="display-device-categories---814654--"></a>Wyświetlanie kategorii urządzeń <!--814654-->
Kategorię urządzenia można teraz wyświetlić jako kolumnę na liście urządzeń. Można także edytować kategorię z poziomu sekcji właściwości w bloku właściwości urządzenia. Zobacz [Jak dodać aplikację do usługi Intune](/intune-azure/manage-apps/add-apps).

### <a name="configure-windows-update-for-business-settings---776716--"></a>Konfigurowanie ustawień usługi Windows Update dla firm<!--776716-->

Windows jako usługa to nowy sposób udostępniania aktualizacji dla systemu Windows 10. Począwszy od systemu Windows 10, wszystkie nowe funkcjonalne i jakościowe aktualizacje będą obejmować zawartość wszystkich poprzednich aktualizacji. Oznacza to, że po zainstalowaniu najnowszej aktualizacji masz pewność, iż urządzenia systemu Windows 10 są całkowicie aktualne. W odróżnieniu od wcześniejszych wersji systemu Windows teraz musisz zainstalować całą aktualizację, a nie tylko jej część.

Za pomocą usługi Windows Update dla firm można uprościć zarządzanie aktualizacjami, dzięki czemu nie trzeba zatwierdzać poszczególnych aktualizacji dla grup urządzeń. Nadal możesz zarządzać ryzykiem w swoich środowiskach, konfigurując strategię wdrażania aktualizacji, dzięki czemu usługa Windows Update zagwarantuje zainstalowanie aktualizacji w odpowiednim czasie. Usługa Microsoft Intune zapewnia możliwość konfigurowania ustawień aktualizacji na urządzeniach oraz odroczenia instalacji aktualizacji. Usługa Intune nie przechowuje aktualizacji, a jedynie przypisanie zasad aktualizacji. W celu aktualizacji urządzenia uzyskują dostęp bezpośrednio do witryny Windows Update. Użyj usługi Intune do konfigurowania **pierścieni aktualizacji systemu Windows 10** i zarządzania nimi. Pierścień aktualizacji zawiera grupę ustawień, które konfigurują, kiedy i w jaki sposób aktualizacje systemu Windows 10 mają zostać zainstalowane. Aby uzyskać szczegółowe informacje, zobacz sekcję [Konfigurowanie ustawień usługi Windows Update dla firm](/intune-azure/configure-devices/how-to-configure-windows-update-for-business).

## <a name="january-2017"></a>Styczeń 2017

### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--"></a>Przypisywanie aplikacji biznesowych niezależnie od tego, czy urządzenia są zarejestrowane <!--748823-->
Możesz teraz przypisywać użytkownikom aplikacje biznesowe ze sklepu niezależnie od tego, czy ich urządzenia są zarejestrowane w usłudze Intune. Jeśli urządzenie użytkownika nie jest zarejestrowane w usłudze Intune, aby ją zainstalować, użytkownik musi przejść do witryny sieci Web Portal firmy, a nie do aplikacji Portal firmy. Zobacz [Co to jest zarządzanie aplikacjami](/intune-azure/manage-apps/what-is-app-management).

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Rozwiązywanie problemów związanych z brakiem aktywności urządzeń z systemem iOS lub z brakiem możliwości komunikacji pomiędzy nimi a konsolą administracyjną
Gdy urządzenia użytkowników utracą połączenie z usługą Intune, można wykonać w odniesieniu do nich nowe kroki mające na celu rozwiązanie problemów w celu przywrócenia dostępu do zasobów firmy. Zobacz temat [Urządzenia są nieaktywne lub nie jest możliwe nawiązanie łączności między nimi a konsolą administracyjną](/intune-azure/enroll-devices/troubleshoot-device-enrollment#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="december-2016-initial-release"></a>Grudzień 2016 (wersja początkowa)

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integracja zarządzania kosztami telekomunikacyjnymi w publicznej wersji zapoznawczej witryny Azure Portal<!--747605-->
Obecnie rozpoczynamy pracę nad wersją zapoznawczą integracji z usługami zarządzania kosztami telekomunikacyjnymi innych firm w witrynie Azure Portal. Usługa Intune może być używana do wymuszania limitów użycia danych w kraju i w roamingu. Te operacje integracji rozpoczynamy od współpracy z firmą [Saaswedo](http://www.saaswedo.com). Aby włączyć tę funkcję w dzierżawie w wersji próbnej, [skontaktuj się z pomocą techniczną firmy Microsoft](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

- Wdrażanie aplikacji ze sklepu na urządzeniach z systemami iOS, Android i Windows i zarządzanie nimi
- Wdrażanie aplikacji biznesowych (LOB, line of business) na urządzeniach z systemami iOS, Android i Windows i zarządzanie nimi
- Wdrażanie aplikacji kupionych w ramach zakupów zbiorczych na urządzeniach z systemami iOS, Android i Windows i zarządzanie nimi
- Wdrażanie aplikacji sieci Web na urządzeniach z systemami iOS, Android i Windows i zarządzanie nimi
- Profile konfiguracji aplikacji zarządzanych w systemie iOS
- Konfigurowanie zasad ochrony aplikacji i wdrażanie aplikacji biznesowych na urządzeniach niezarejestrowanych w usłudze Intune
- Profile sieci VPN, sieci VPN dla aplikacji, sieci Wi-Fi, poczta e-mail i profile certyfikatów
- Zasady zgodności
- Dostęp warunkowy do usługi Azure AD
- Dostęp warunkowy do lokalnego programu Exchange
- Rejestrowanie urządzeń
- Kontrola dostępu oparta na rolach

## <a name="deprecated-features-in-the-azure-portal"></a>Funkcje przestarzałe w portalu Azure

### <a name="support-for-row-by-row-review-of-hardware-identifiers"></a>Obsługa przeglądu wiersz po wierszu identyfikatorów sprzętu
Portal Azure nie obsługuje przeglądu wiersz po wierszu identyfikatorów sprzętu dla numerów IMEI i numerów seryjnych firmy Apple. W klasycznej konsoli usługi Intune można zaimportować szczegółowe informacje z pliku CSV i zastąpić nimi istniejące szczegółowe informacje dotyczące indywidualnych identyfikatorów sprzętu. Portal Azure udostępnia pojedynczą, zoptymalizowaną opcję, która automatycznie zastępuje szczegóły dotyczące wszystkich identyfikatorów sprzętu lub ignoruje nowe szczegóły dotyczące istniejących identyfikatorów.

#### <a name="how-this-affects-you"></a>Jaki to ma wpływ na Ciebie
W portalu Azure nie będziesz mieć możliwości ustalenia wiersz po wierszu, które urządzenia z numerem InternationaI Mobile Equipment (IMEI) należy zaktualizować. W klasycznej konsoli usługi Intune ta funkcja będzie nadal obsługiwana.

#### <a name="how-to-get-ready-for-this-change"></a>Jak przygotować się do tej zmiany
Ponieważ informujemy o tym z wyprzedzeniem, to jeśli ta zmiana dotyczy Ciebie, masz możliwość zwrócenia na nią uwagi administratorom. Ta zmiana zbiega się z przeniesieniem do portalu Azure przewidywanym w pierwszej połowie 2017 roku.


### <a name="support-for-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Obsługa domyślnych profilów rejestracji urządzeń firmowych usługi Apple DEP
Portal Azure nie obsługuje „domyślnego” profilu rejestracji urządzeń firmowych w odniesieniu do numerów seryjnych urządzeń programu Apple DEP (Device Enrollment Program) Ta dostępna w klasycznej konsoli usługi Intune funkcja przestaje być obsługiwana, aby zapobiec przypadkowo przypisanym profilom. W portalu Azure numery seryjne synchronizowane z kontem usługi Apple DEP nie będą początkowo miały przypisanego profilu rejestracji urządzeń firmowych.

#### <a name="how-this-affects-you"></a>Jaki to ma wpływ na Ciebie
W portalu Azure nie będziesz mieć możliwości ustawienia domyślnych zasad profilu wszystkich urządzeń firmy Apple. W klasycznej konsoli usługi Intune ta funkcja będzie nadal obsługiwana.

#### <a name="how-to-get-ready-for-this-change"></a>Jak przygotować się do tej zmiany
Ponieważ informujemy o tym z wyprzedzeniem, to jeśli ta zmiana dotyczy Ciebie, masz możliwość zwrócenia na nią uwagi administratorom. Ta zmiana zbiega się z przeniesieniem do portalu Azure przewidywanym w pierwszej połowie 2017 roku.

