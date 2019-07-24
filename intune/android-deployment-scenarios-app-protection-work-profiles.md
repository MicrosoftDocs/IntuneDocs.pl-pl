---
title: Zasady ochrony aplikacji i profile służbowe systemu Android w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z różnicami oraz mocnymi i słabymi stronami procesu podejmowania decyzji o użyciu zasad ochrony aplikacji lub profilów służbowych na urządzeniach osobistych lub BYOD z systemem Android Enterprise w usłudze Microsoft Intune. Porównaj różnice i funkcje, które uzyskujesz dzięki zasadom ochrony aplikacji bez rejestracji (APP-WE) i profilom służbowym systemu Android Enterprise.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/13/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: d5814a4aac064394dbd0c7f5902dc3f62459ad1d
ms.sourcegitcommit: bd09decb754a832574d7f7375bad0186a22a15ab
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/19/2019
ms.locfileid: "68353808"
---
# <a name="application-protection-policies-and-work-profiles-on-android-enterprise-devices-in-intune"></a>Zasady ochrony aplikacji i profile służbowe na urządzeniach z systemem Android Enterprise w usłudze Intune

W wielu organizacjach administratorzy muszą chronić zasoby i dane na różnych urządzeniach. Jednym z wyzwań jest ochrona zasobów dla użytkowników z osobistymi urządzeniami z systemem Android Enterprise znanymi również jako BYOD (bring-your-own-device). Usługa Microsoft Intune obsługuje dwa scenariusze wdrażania dla systemu Android w przypadku urządzeń BYOD (bring-your-own-device):

- Zasady ochrony aplikacji bez rejestracji (APP-WE)
- Profile służbowe w systemie Android Enterprise

Scenariusze wdrażania zasad APP-WE i profilów służbowych systemu Android zawierają następujące kluczowe funkcje ważne dla środowisk BYOD:

1. **Ochrona i podział danych zarządzanych przez organizację**: oba rozwiązania chronią dane organizacji, wymuszając testy ochrony przed utratą danych (DLP) na danych zarządzanych przez organizację. Te środki ochronne zapobiegają przypadkowym wyciekom chronionych danych, jeśli na przykład użytkownik końcowy przypadkowo udostępni je w osobistej aplikacji lub na koncie. Gwarantują one również, że urządzenie uzyskujące dostęp do danych jest w dobrej kondycji, a jego zabezpieczenia nie zostały naruszone.

2. **Prywatność użytkownika końcowego**: Zasady APP-WE i profile służbowe systemu Android Enterprise oddzielają zawartość użytkowników końcowych na urządzeniu i dane zarządzane przez administratora zarządzania urządzeniami przenośnymi (MDM). W obydwu scenariuszach administratorzy IT wymuszają zasady, takie jak uwierzytelnianie tylko przy użyciu numeru PIN, w obrębie tożsamości lub aplikacji zarządzanych przez organizację. Administratorzy IT nie mogą odczytywać i usuwać danych posiadanych lub kontrolowanych przez użytkowników końcowych ani uzyskiwać dostępu do tych danych.

Wybór zasad APP-WE lub profilów służbowych systemu Android Enterprise do wdrożenia BYOD zależy od wymagań i potrzeb biznesowych. Celem tego artykułu jest przedstawienie wskazówek, które pomogą Ci w podjęciu decyzji.

## <a name="about-intune-app-protection-policies"></a>Informacje o zasadach ochrony aplikacji usługi Intune

Zasady ochrony aplikacji (APP) usługi Intune to zasady ochrony danych ukierunkowane na użytkowników. Zasady stosują ochronę przed utratą danych na poziomie aplikacji. Zasady ochrony aplikacji w usłudze Intune wymagają, aby deweloperzy aplikacji włączali funkcje zasad ochrony aplikacji w tworzonych aplikacjach.

Poszczególne aplikacje dla systemu Android są włączane na potrzeby zasad ochrony aplikacji na kilka sposobów:

1. **Natywnie zintegrowane w aplikacjach firmy Microsoft**: aplikacje pakietu Microsoft Office dla systemu Android oraz inne wybrane aplikacje firmy Microsoft mają wbudowane zasady ochrony aplikacji usługi Intune. Te aplikacje pakietu Office, takie jak Word, OneDrive, Outlook itd., do stosowania zasad nie wymagają kolejnych operacji dostosowywania. Użytkownicy końcowi mogą instalować te aplikacje bezpośrednio ze sklepu Google Play.

2. **Integrowane w kompilacjach aplikacji przez deweloperów przy użyciu zestawu SDK usługi Intune**: deweloperzy aplikacji mogą integrować zestaw SDK usługi Intune w kodzie źródłowym i ponownie kompilować aplikacje tak, aby obsługiwały funkcje zasad ochrony aplikacji usługi Intune.

3. **Opakowane przy użyciu narzędzia opakowującego aplikacje usługi Intune**: niektórzy klienci kompilują aplikacje dla systemu Android (plik APK) bez dostępu do kodu źródłowego. Bez kodu źródłowego deweloper nie może przeprowadzić integracji z zestawem SDK usługi Intune. Bez zestawu SDK nie można włączyć zasad ochrony aplikacji dla aplikacji. Deweloper musi zmodyfikować lub ponownie zakodować aplikację, aby obsługiwała zasady ochrony aplikacji.

    Aby pomóc, usługa Intune oferuje **narzędzie opakowujące aplikacje** dla istniejących aplikacji systemu Android (plików APK), a następnie tworzy aplikację, która rozpoznaje zasady ochrony aplikacji.

    Aby uzyskać więcej informacji na temat tego narzędzia, zobacz [Przygotowanie aplikacji biznesowych pod kątem zasad ochrony aplikacji](apps-prepare-mobile-application-management.md).

Aby wyświetlić listę aplikacji z włączonymi zasadami ochrony aplikacji, zobacz [Aplikacje zarządzane z bogatym zestawem zasad ochrony aplikacji mobilnych](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

## <a name="deployment-scenarios"></a>Scenariusze wdrażania

W tej sekcji opisano ważne charakterystyki scenariuszy wdrażania zasad APP-WE i profilów służbowych systemu Android Enterprise.

### <a name="app-we"></a>APP-WE

Wdrożenie APP-WE (zasady ochrony aplikacji bez rejestracji) definiuje zasady dotyczące aplikacji, a nie urządzeń. W tym scenariuszu urządzenia zwykle nie są rejestrowane ani zarządzane przez urząd MDM, taki jak usługa Intune. Aby chronić aplikacje i dostęp do danych organizacji, administratorzy korzystają z aplikacji zarządzanych przez zasady APP i stosują zasady ochrony danych do tych aplikacji.

Ta funkcja ma zastosowanie do:

- System Android 4.4 i nowsze

> [!TIP]
> Aby uzyskać więcej informacji, zobacz [Co to są zasady ochrony aplikacji?](app-protection-policy.md)

Scenariusze APP-WE są przeznaczone dla użytkowników końcowych, którzy potrzebują niewielkiej ilości danych organizacyjnych na swoich urządzeniach i nie chcą rejestrować się w oprogramowaniu MDM. Jako administrator nadal musisz chronić dane. Te urządzenia nie są zarządzane. Dlatego typowe zadania i funkcje zarządzania urządzeniami przenośnymi, takie jak sieć Wi-Fi, sieć VPN urządzenia i zarządzanie certyfikatami, nie są częścią tego scenariusza wdrażania.

### <a name="android-enterprise-work-profiles"></a>Profile służbowe w systemie Android Enterprise

Profile służbowe to podstawowy scenariusz wdrażania systemu Android Enterprise i jedyny scenariusz przeznaczony dla przypadków użycia strategii BYOD. Profil służbowy to oddzielna partycja utworzona na poziomie systemu operacyjnego Android, która może być zarządzana przez usługę Intune.

Ta funkcja ma zastosowanie do:

- Urządzenia z systemem Android 5.0 lub nowszym i z usługami Google Mobile Services

Profil służbowy zawiera następujące funkcje:

- **Tradycyjna funkcjonalność oprogramowania MDM**: kluczowe możliwości oprogramowania MDM, takie jak zarządzanie cyklem życia aplikacji za pomocą zarządzanego sklepu Google Play, są dostępne w każdym scenariuszu dla systemu Android Enterprise. Zarządzany sklep Google Play zapewnia niezawodne środowisko służące do instalowania można instalować i aktualizować aplikacje bez interwencji użytkownika. Dział IT może również wypychać ustawienia konfiguracji aplikacji do aplikacji organizacyjnych. Użytkownicy końcowi nie muszą zezwalać na instalacje z nieznanych źródeł. Inne typowe działania oprogramowania MDM, takie jak wdrażanie certyfikatów, konfigurowanie sieci Wi-Fi/VPN i ustawianie kodów dostępu do urządzenia, są dostępne w przypadku profilów służbowych.

- **Ochrona przed utratą danych na granicy profilu służbowego**: Tak jak w przypadku zasad APP-WE, dział IT może wymuszać zasady ochrony danych. W przypadku profilu służbowego zasady DLP są wymuszane na poziomie profilu służbowego, a nie na poziomie aplikacji. Na przykład ochrona kopiowania/wklejania jest wymuszana przez ustawienia zasad ochrony aplikacji stosowane do aplikacji lub wymuszana przez profil służbowy. Jeśli aplikacja jest wdrażana w profilu służbowym, administratorzy mogą wstrzymać ochronę kopiowania/wklejania w profilu służbowym przez wyłączenie tych zasad na poziomie zasad ochrony aplikacji.

## <a name="tips-to-optimize-the-work-profile-experience"></a>Porady dotyczące optymalizowania środowiska profilu służbowego

### <a name="when-to-use-app-within-work-profiles"></a>Kiedy należy używać zasad ochrony aplikacji w ramach profilów służbowych

Zasady APP usługi Intune i profile służbowe to uzupełniające się technologie, których można używać razem lub osobno. Z punktu widzenia architektury obydwa rozwiązania wymuszają zasady w różnych warstwach — zasady ochrony aplikacji aplikacji w warstwie poszczególnych aplikacji, a profil służbowy w warstwie profilu. Wdrażanie aplikacji zarządzanych przy użyciu zasad ochrony aplikacji do aplikacji w profilu służbowym to prawidłowy i obsługiwany scenariusz. Opcja użycia zasad ochrony aplikacji, profilów służbowych lub ich kombinacji zależy od wymagań dotyczących ochrony przed utratą danych.

Profile służbowe i zasady ochrony aplikacji uzupełniają swoje ustawienia, zapewniając dodatkowe pokrycie, jeśli jeden profil nie spełnia wymagań dotyczących ochrony danych organizacji. Na przykład profile służbowe natywnie nie udostępniają środków kontroli w celu ograniczenia w aplikacji zapisywania w niezaufanej lokalizacji magazynu w chmurze. Zasady APP uwzględniają tę funkcję. Możesz zdecydować, że ochrona przed utratą danych oferowana wyłącznie w profilu służbowym jest wystarczająca, i zrezygnować z używania zasad ochrony aplikacji. Możesz również wymagać ochrony oferowanej przez połączenie tych dwóch funkcji.

### <a name="suppress-app-policy-for-work-profiles"></a>Pomijanie zasad ochrony aplikacji w przypadku profilów służbowych

Być może trzeba będzie obsługiwać poszczególnych użytkowników, którzy mają wiele urządzeń — urządzeń niezarządzanych w scenariuszu zasad APP-WE i urządzeń zarządzanych w przypadku profilów służbowych.

Na przykład wymagasz, aby użytkownicy końcowi wprowadzali numer PIN podczas otwierania aplikacji służbowej. W zależności od urządzenia funkcje numeru PIN są obsługiwane przez zasady ochrony aplikacji lub profil służbowy. W przypadku urządzeń APP-WE zachowanie wymagające podania numeru PIN do uruchomienia jest wymuszane przez zasady ochrony aplikacji. W przypadku urządzeń z profilem służbowym można używać numeru PIN urządzenia lub profilu służbowego wymuszanego przez system operacyjny. Aby korzystać z tego scenariusza, skonfiguruj ustawienia zasad ochrony aplikacji, tak aby nie były stosowane, *gdy* aplikacja będzie wdrażana w profilu służbowym. Jeśli nie skonfigurujesz ich w ten sposób, użytkownik końcowy zobaczy monit o podanie numeru PIN na urządzeniu, a następnie w warstwie zasad ochrony aplikacji.

### <a name="control-multi-identity-behavior-in-work-profiles"></a>Kontrolowanie zachowania obejmującego wiele tożsamości w profilu służbowym

Aplikacje pakietu Office, takie jak Outlook i OneDrive, mają zachowanie typu „wiele tożsamości”. W ramach jednego wystąpienia aplikacji użytkownik końcowy może dodawać połączenia do wielu różnych kont lub lokalizacji magazynu w chmurze. W aplikacji dane pobrane z tych lokalizacji mogą być obsługiwane oddzielne lub jako dane scalone. A użytkownik może przełączać kontekst między tożsamościami osobistymi (user@outlook.com) i tożsamościami organizacji (user@contoso.com).

W przypadku korzystania z profilów służbowych możesz wyłączyć to zachowanie obejmujące wiele tożsamości. Po jego wyłączeniu oznaczone wystąpienia aplikacji w profilu służbowym można konfigurować tylko przy użyciu tożsamości organizacji. Należy użyć ustawienia konfiguracji aplikacji Dozwolone konta, aby obsługiwać aplikacje pakietu Office dla systemu Android.

Aby uzyskać więcej informacji, zobacz temat [Deploy Outlook for iOS and Android app configuration settings](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune) (Wdrażanie ustawień konfiguracji aplikacji Outlook dla systemu iOS i Android).

## <a name="when-to-use-intune-app"></a>Kiedy należy używać zasad ochrony aplikacji usługi Intune

Istnieje kilka scenariuszy związanych z mobilnością w przedsiębiorstwie, w przypadku których użycie zasad ochrony aplikacji usługi Intune jest najlepszym rozwiązaniem.

### <a name="older-devices-running-android-44-51-are-being-used"></a>Używanie starszych urządzeń z systemem Android 4.4–5.1

Oficjalnie wszystkie urządzenia z systemem Android 5.0 lub nowszym i usługami Mobile Services Google obsługują profile służbowe i można nimi zarządzać w ten sposób. Jednak pewne urządzenia z systemami Android 5.0 i 5.1 od niektórych producentów OEM nie obsługują profilów służbowych.

Jeśli używasz wersji, które nie obsługują profilów służbowych, i chcesz zapewnić ochronę przed utratą danych organizacji na urządzeniach, musisz używać funkcji zasad ochrony aplikacji usługi Intune.

### <a name="no-mdm-no-enrollment-google-services-are-unavailable"></a>Brak oprogramowania MDM, brak rejestracji, usługi Google są niedostępne

Niektórzy klienci nie potrzebują funkcji zarządzania urządzeniami, w tym zarządzania profilami służbowymi, z różnych powodów:

- Przyczyny związane z przepisami prawnymi i odpowiedzialnością
- Zachowanie spójności środowiska użytkownika
- Środowisko urządzenia z systemem Android jest wysoce heterogeniczne
- Brak łączności z usługami Google, co jest wymagane do zarządzania profilami służbowymi.

Na przykład klienci w Chinach lub z użytkownikami w Chinach nie mogą używać zarządzania urządzeniami z systemem Android, ponieważ usługi Google są zablokowane. W takim przypadku należy użyć zasad ochrony aplikacji usługi Intune dla technologii DLP.

## <a name="summary"></a>Podsumowanie

Jeśli używasz usługi Intune, zasady APP-WE i profile służbowe systemu Android Enterprise są dostępne w programie BYOD dla systemu Android. Wybór zasad APP-WE lub profilów służbowych zależy od wymagań biznesowych i dotyczących użycia. Podsumowując: profilów służbowych należy używać, jeśli chcesz wykonywać działania oprogramowania MDM, takie jak wdrażanie certyfikatów, wypychanie aplikacji itd., na urządzeniach zarządzanych. Zasad APP-WE należy używać, jeśli nie chcesz lub nie możesz zarządzać urządzeniami i używasz aplikacji z obsługą zasad ochrony aplikacji usługi Intune.

## <a name="next-steps"></a>Następne kroki
[Rozpocznij korzystanie z zasad ochrony aplikacji](app-protection-policy.md) lub [zarejestruj swoje urządzenia](android-enroll.md).
