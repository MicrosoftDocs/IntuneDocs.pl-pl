---
title: Użycie programu OEMConfig do obsługi urządzeń z systemem Android Enterprise w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Używanie usługi Microsoft Intune do zarządzania urządzeniami z systemem Android Enterprise i korzystania z nich za pomocą aplikacji OEMConfig. Zapoznaj się ze wszystkimi krokami, w tym z omówieniem, zobacz wymagania wstępne, utwórz profil konfiguracji w usłudze Intune i zobacz listę obsługiwanych aplikacji OEMConfig.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/02/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1bc811bcac80f8321284ece8d3860efc7164a270
ms.sourcegitcommit: a25f556aa9df4fcd9fdacccd12c9029bc6c5fe20
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/03/2020
ms.locfileid: "78256326"
---
# <a name="use-and-manage-android-enterprise-devices-with-oemconfig-in-microsoft-intune"></a>Korzystanie z urządzeń z systemem Android Enterprise i zarządzanie nimi za pomocą aplikacji OEMConfig w usłudze Microsoft Intune

W usłudze Microsoft Intune można używać aplikacji OEMConfig, aby dodawać, tworzyć i dostosowywać ustawienia specyficzne dla producenta OEM dla urządzeń z systemem Android Enterprise. Aplikacja OEMConfig jest zazwyczaj używana do konfigurowania ustawień, które nie są wbudowane w usłudze Intune. Różni producenci oryginalnego sprzętu (OEM, original equipment manufacturer) uwzględniają różne ustawienia. Dostępne ustawienia zależą od tego, co producent OEM uwzględni w swojej aplikacji OEMConfig.

Ta funkcja ma zastosowanie do:  

- Android Enterprise

W tym artykule opisano standard OEMConfig, wymieniono wymagania wstępne, przedstawiono sposób tworzenia profilu konfiguracji oraz zawarto listę aplikacji OEMConfig obsługiwanych w usłudze Intune.

## <a name="overview"></a>Omówienie

Zasady OEMConfig to specjalny typ zasad konfiguracji urządzeń podobnych do [zasad konfiguracji aplikacji](../apps/app-configuration-policies-overview.md). OEMConfig to standard zdefiniowany przez firmę Google, który używa konfiguracji aplikacji w systemie Android w celu wysyłania ustawień urządzenia do aplikacji tworzonych przez producentów OEM (czyli producentów oryginalnego sprzętu). Standard ten umożliwia producentom OEM i dostawcom rozwiązań zarządzania mobilnością w przedsiębiorstwie (EMM, Enterprise Mobility Management) tworzenie i obsługiwanie funkcji specyficznych dla producenta OEM w ustandaryzowany sposób. [Dowiedz się więcej o standardzie OEMConfig](https://blog.google/products/android-enterprise/oemconfig-supports-enterprise-device-features/).

Historycznie, dostawcy rozwiązań EMM, takich jak usługa Intune, ręcznie opracowywali obsługę funkcji specyficznych dla producenta OEM po wprowadzeniu danego rozwiązania przez producenta OEM. To podejście powodowało duplikowanie wysiłków i wolne wdrażanie.

Za pomocą standardu OEMConfig producent OEM tworzy schemat definiujący funkcje zarządzania specyficzne dla producenta OEM. Producent OEM osadza schemat w aplikacji, a następnie przekazuje tę aplikację do sklepu Google Play. Rozwiązanie EMM odczytuje schemat z aplikacji i uwidacznia go w konsoli administratora rozwiązania EMM. Konsola umożliwia administratorom usługi Intune konfigurowanie ustawień w schemacie.

Aplikacja OEMConfig, po zainstalowaniu na urządzeniu, używa ustawień skonfigurowanych w konsoli administratora rozwiązania EMM w celu zarządzania urządzeniem. Ustawienia urządzenia są obsługiwane przez aplikację OEMConfig zamiast przez agenta MDM skompilowanego przez rozwiązanie EMM.

Gdy producent OEM dodaje i poprawia funkcje zarządzania, aktualizuje również aplikację w sklepie Google Play. Jako administrator otrzymujesz te nowe funkcje i aktualizacje (w tym poprawki) bez konieczności czekania na to, aż rozwiązanie EMM uwzględni te aktualizacje.

> [!TIP]
> Standardu OEMConfig można używać tylko w przypadku urządzeń, które obsługują tę funkcję i mają odpowiednią aplikację OEMConfig. Aby uzyskać szczegółowe informacje, skontaktuj się z producentem OEM.

## <a name="before-you-begin"></a>Przed rozpoczęciem

W przypadku korzystania z aplikacji OEMConfig należy pamiętać o następujących kwestiach:

- Usługa Intune uwidacznia schemat aplikacji OEMConfig, aby można go było skonfigurować. Usługa Intune nie weryfikuje ani nie zmienia schematu dostarczonego przez aplikację. Jeśli więc schemat jest nieprawidłowy lub zawiera niedokładne dane, te dane są nadal wysyłane do urządzeń. Jeśli znajdziesz problem mający swoje źródło w schemacie, skontaktuj się z producentem OEM, aby uzyskać wskazówki.
- Usługa Intune nie ma wpływu na zawartość schematu aplikacji ani go nie kontroluje. Usługa Intune nie ma na przykład żadnej kontroli nad ciągami, językiem, dozwolonymi akcjami i tak dalej. Zalecamy skontaktowanie się z producentem OEM w celu uzyskania dokładniejszych informacji na temat zarządzania jego urządzeniami za pomocą aplikacji OEMConfig.
- W dowolnym momencie producenci OEM mogą zaktualizować obsługiwane funkcje i schematy i przekazać nową aplikację do sklepu Google Play. Usługa Intune zawsze synchronizuje najnowszą wersję aplikacji OEMConfig ze sklepu Google Play. Usługa Intune nie zachowuje starszych wersji schematu ani aplikacji. W przypadku wystąpienia konfliktu wersji zalecamy skontaktowanie się z producentem OEM w celu uzyskania dalszych informacji.
- Do urządzenia należy przypisać jeden profil OEMConfig. Jeśli do tego samego urządzenia zostanie przypisanych wiele profilów, urządzenie może zachowywać się niespójnie. Model OEMConfig obsługuje tylko jeden zestaw zasad na urządzenie.

## <a name="prerequisites"></a>Wymagania wstępne

Aby móc korzystać ze standardu OEMConfig na urządzeniach, upewnij się, że spełniono następujące wymagania:

- Urządzenie z systemem Android Enterprise zostało zarejestrowane w usłudze Intune.
- Aplikacja OEMConfig opracowana przez producenta OEM została przekazana do sklepu Google Play. Jeśli aplikacji nie ma w sklepie Google Play, skontaktuj się z producentem OEM, aby uzyskać więcej informacji.
- Administrator usługi Intune ma uprawnienia kontroli dostępu opartej na rolach (RBAC) dla **aplikacji mobilnych** i **konfiguracji urządzeń** oraz uprawnienie odczytu w programie **Android for Work**. Te uprawnienia są wymagane, ponieważ profile OEMConfig używają konfiguracji aplikacji zarządzanych w celu zarządzania konfiguracjami urządzeń.

## <a name="prepare-the-oemconfig-app"></a>Przygotowywanie aplikacji OEMConfig

Upewnij się, że urządzenie obsługuje aplikację OEMConfig, że odpowiednia aplikacja OEMConfig została dodana do usługi Intune i że aplikacja została zainstalowana na urządzeniu. Aby uzyskać te informacje, skontaktuj się z producentem OEM.

> [!TIP] 
> Aplikacja OEMConfig jest specyficzna dla producenta OEM. Na przykład aplikacja OEMConfig firmy Sony zainstalowana na urządzeniu firmy Zebra Technologies nie wykonuje żadnych działań.

1. Pobierz aplikację OEMConfig z zarządzanego sklepu Google Play. Kroki procedury znajdziesz w artykule [Dodawanie zarządzanych aplikacji ze sklepu Google Play do urządzeń z systemem Android Enterprise z usługą Intune](../apps/apps-add-android-for-work.md).
2. Niektórzy producenci OEM mogą dostarczać urządzenia ze wstępnie zainstalowaną aplikacją OEMConfig. Jeśli aplikacja nie jest wstępnie zainstalowana, użyj usługi Intune, aby [dodać i wdrożyć aplikację na urządzeniach](../apps/apps-deploy.md).

## <a name="create-an-oemconfig-profile"></a>Tworzenie profilu OEMConfig

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia** > **Profile konfiguracji** > **Utwórz profil**.
3. Wprowadź następujące właściwości:

    - **Platforma**: Wybierz pozycję **Android Enterprise**.
    - **Typ profilu**: Wybierz pozycję **OEMConfig**.

4. Wybierz przycisk **Utwórz**.
5. W obszarze **Podstawy** wprowadź następujące właściwości:

    - **Nazwa**: Wprowadź opisową nazwę nowego profilu.
    - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Aplikacja OEMConfig**: Wybierz pozycję **Wybierz aplikację OEMConfig**.

6. W obszarze **Skojarzona aplikacja** wybierz istniejącą, dodaną wcześniej aplikację OEMConfig, a następnie wybierz pozycję **Wybierz**. Upewnij się, że wybierasz poprawną aplikację OEMConfig dla urządzeń, do których przypisujesz zasady.

    Jeśli nie widzisz żadnych aplikacji na liście, skonfiguruj zarządzany sklep Google Play i pobierz aplikacje z zarządzanego sklepu Google Play. Kroki procedury znajdziesz w artykule [Dodawanie zarządzanych aplikacji ze sklepu Google Play do urządzeń z systemem Android Enterprise z usługą Intune](../apps/apps-add-android-for-work.md).

    > [!IMPORTANT]
    > Jeśli aplikacja OEMConfig została dodana i zsynchronizowana ze sklepem Google Play, ale nie jest widoczna na liście **Skojarzona aplikacja**, może być konieczne skontaktowanie się z zespołem usługi Intune w celu dołączenia tej aplikacji. Zobacz [Dodawanie nowej aplikacji](#supported-oemconfig-apps) (w tym artykule).

7. Wybierz pozycję **Dalej**.
8. W obszarze **Konfiguruj ustawienia** wybierz pozycję **Projektant konfiguracji** lub **Edytor JSON**:

    > [!TIP]
    > Zapoznaj się z dokumentacją producenta OEM, aby upewnić się, że właściwości są konfigurowane poprawnie. Te właściwości aplikacji są dołączane przez producenta OEM, a nie przez usługę Intune. Usługa Intune zapewnia minimalną weryfikację właściwości lub wprowadzanych wartości. Jeśli na przykład wprowadzisz wartość `abcd` jako numeru portu, profil zostanie zapisany w takiej postaci, w jakiej jest, i wdrożony na urządzeniach ze skonfigurowanymi przez Ciebie wartościami. Upewnij się, że wprowadzasz odpowiednie informacje.

    - **Projektant konfiguracji**: Po wybraniu tej opcji właściwości dostępne w schemacie aplikacji są wyświetlane na potrzeby konfiguracji.

      - Menu kontekstowe w projektancie konfiguracji wskazują, że jest dostępnych więcej opcji. Na przykład menu kontekstowe może pozwalać na dodawanie, usuwanie i zmienianie kolejności ustawień. Te opcje są dołączane przez producenta OEM. Zapoznaj się z dokumentacją aplikacji producenta OEM, aby dowiedzieć się, jak przy użyciu tych opcji tworzyć profile.

      - Wiele ustawień ma wartości domyślne dostarczone przez producenta OEM. Aby sprawdzić, czy jest dostępna wartość domyślna, umieść kursor na ikonie informacji obok ustawienia. Etykietka narzędzia pokaże wartości domyślne dla tego ustawienia (jeśli są dostępne) i więcej szczegółów dostarczonych przez producenta OEM.

      - Kliknięcie pozycji **Wyczyść** powoduje usunięcie ustawienia z profilu. Jeśli ustawienie nie znajduje się w profilu, jego wartość na urządzeniu nie ulegnie zmianie po zastosowaniu profilu.

      - Jeśli utworzysz pusty (nieskonfigurowany) pakiet w projektancie konfiguracji, zostanie on usunięty po przełączeniu się do edytora JSON.

    - **Edytor JSON**: Po wybraniu tej opcji zostanie otwarty edytor JSON z szablonem dla całego schematu konfiguracji osadzonego w aplikacji. W edytorze dostosuj szablon za pomocą wartości dla różnych ustawień. Jeśli zmienisz wartości przy użyciu **projektanta konfiguracji**, edytor JSON zastąpi szablon wartościami z projektanta konfiguracji.

      - W przypadku aktualizowania istniejącego profilu edytor JSON pokazuje ustawienia, które zostały ostatnio zapisane z profilem.

      - Schematy OEMConfig mogą być duże i złożone. Jeśli wolisz aktualizować te ustawienia przy użyciu innego edytora, wybierz przycisk **Pobierz szablon JSON**. Użyj wybranego edytora, aby dodać do szablonu wartości konfiguracji. Następnie skopiuj i wklej zaktualizowany plik JSON we właściwości **Edytor JSON**.

      - Za pomocą edytora JSON możesz utworzyć kopię zapasową konfiguracji. Po skonfigurowaniu ustawień użyj tej funkcji, aby pobrać ustawienia JSON ze swoimi wartościami. Skopiuj i wklej kod JSON do pliku i zapisz go. Teraz masz plik kopii zapasowej.

    Wszystkie zmiany wprowadzone w projektancie konfiguracji są również automatycznie wprowadzane w edytorze JSON. Podobnie wszelkie zmiany wprowadzone w edytorze JSON są automatycznie wprowadzane w projektancie konfiguracji. Jeśli dane wejściowe zawierają nieprawidłowe wartości, nie można przełączyć się między projektantem konfiguracji i edytorem JSON, dopóki problemy nie zostaną rozwiązane.

9. Wybierz pozycję **Dalej**.
10. W obszarze **Tagi zakresu** (opcjonalnie) przypisz tag, aby filtrować profil do określonych grup IT, takich jak `US-NC IT Team` lub `JohnGlenn_ITDepartment`. Aby uzyskać więcej informacji na temat tagów zakresu, zobacz [Używanie kontroli RBAC i tagów zakresu w rozproszonej strukturze informatycznej](../fundamentals/scope-tags.md).

    Wybierz pozycję **Dalej**.

11. W obszarze **Przypisania** wybierz użytkowników lub grupy, które otrzymają Twój profil. Do każdego urządzenia przypisz jeden profil. Model OEMConfig obsługuje tylko jeden zestaw zasad na urządzenie.

    Aby uzyskać więcej informacji na temat przypisywania profilów, zobacz [Przypisywanie profilów użytkowników i urządzeń](device-profile-assign.md).

    Wybierz pozycję **Dalej**.

12. W obszarze **Przeglądanie + tworzenie** przejrzyj ustawienia. Po wybraniu pozycji **Utwórz** zmiany zostaną zapisane, a profil przypisany. Zasady są również wyświetlane na liście profilów.

Następnym razem, gdy urządzenie będzie sprawdzać aktualizacje konfiguracji, skonfigurowane przez Ciebie ustawienia specyficzne dla producenta OEM zostaną zastosowane do aplikacji OEMConfig.

> [!NOTE]
> Standard OEMConfig obecnie nie obejmuje raportowania stanu. Dlatego domyślnie profile pokazują stan **Oczekujące**.

## <a name="supported-oemconfig-apps"></a>Obsługiwane aplikacje OEMConfig

W porównaniu ze standardowymi aplikacjami, aplikacje OEMConfig rozszerzają uprawnienia konfiguracji zarządzanych przyznane przez firmę Google w celu obsługiwania bardziej złożonych schematów. Usługa Intune obsługuje obecnie następujące aplikacje OEMConfig:

-----------------

| OEM | Identyfikator pakietu | Dokumentacja OEM (jeśli jest dostępna) |
| --- | --- | ---|
| Samsung | com.samsung.android.knox.kpu | [Przewodnik administratora wtyczki usługi Knox](https://docs.samsungknox.com/knox-service-plugin/admin-guide/index.htm) |
| Zebra Technologies | com.zebra.oemconfig.common | [Omówienie aplikacji OEMConfig firmy Zebra](http://techdocs.zebra.com/oemconfig ) |
| Datalogic | com.datalogic.oemconfig | [Dokumentacja użytkownika dotycząca aplikacji OEMConfig firmy Datalogic](https://datalogic.github.io/oemconfig/) |
| Honeywell | com.honeywell.oemconfig |  |
| Kyocera | jp.kyocera.enterprisedeviceconfig |  |
| Spectralink — Kody kreskowe | com.spectralink.barcode.service |  |
| Spectralink — Przyciski | com.spectralink.buttons |  |
| Spectralink — Urządzenie | com.spectralink.slnkdevicesettings  |  |
| Spectralink — Rejestrowanie | com.spectralink.slnklogger |  |
| Spectralink — VQO | com.spectralink.slnkvqo |  |
| Seuic | com.seuic.seuicoemconfig | |
| Unitech Electronics | com.unitech.oemconfig | |

-----------------

Jeśli aplikacja OEMConfig istnieje dla Twojego urządzenia, ale nie znajduje się w powyższej tabeli lub nie jest wyświetlana w konsoli usługi Intune, napisz wiadomość e-mail na adres `IntuneOEMConfig@microsoft.com`.

> [!NOTE]
> Aplikacje OEMConfig muszą zostać dołączone do usługi Intune, zanim będzie można je konfigurować za pomocą profilów OEMConfig. Gdy aplikacja będzie już obsługiwana, nie musisz kontaktować się z firmą Microsoft w celu skonfigurowania jej w dzierżawie. Po prostu postępuj zgodnie z instrukcjami na tej stronie.
>
> Jeśli aplikacja OEMConfig działa niepoprawnie, skontaktuj się z jej deweloperami. Usługa Intune nie odpowiada za problemy techniczne związane z poszczególnymi aplikacjami OEMConfig.

## <a name="next-steps"></a>Następne kroki

[Monitorowanie stanu profilu](device-profile-monitor.md).
