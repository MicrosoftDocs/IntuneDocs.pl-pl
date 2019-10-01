---
title: Użycie programu OEMConfig do obsługi urządzeń z systemem Android Enterprise w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Użyj Microsoft Intune, aby zarządzać urządzeniami z systemem Android Enterprise i korzystać z nich przy użyciu programu OEMConfig. Zobacz wszystkie kroki, w tym omówienie, zobacz Wymagania wstępne, Utwórz profil konfiguracji w usłudze Intune i Zobacz listę obsługiwanych aplikacji OEMConfig.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c3108364850641cd85abf6b97a2b981735f59895
ms.sourcegitcommit: 8934b1abec96e18cee15a77107d37551766f7666
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2019
ms.locfileid: "71303906"
---
# <a name="use-and-manage-android-enterprise-devices-with-oemconfig-in-microsoft-intune"></a>Korzystanie z urządzeń z systemem Android Enterprise i zarządzanie nimi za pomocą OEMConfig w Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W Microsoft Intune można używać OEMConfig do dodawania, tworzenia i dostosowywania ustawień specyficznych dla producenta OEM dla urządzeń z systemem Android Enterprise. OEMConfig jest zazwyczaj używany do konfigurowania ustawień, które nie są wbudowane w usłudze Intune. Różni producenci oryginalnego sprzętu (OEM) zawierają różne ustawienia. Dostępne ustawienia zależą od tego, co zawiera producent OEM w aplikacji OEMConfig.

Ta funkcja ma zastosowanie do:  

- Android Enterprise

W tym artykule opisano OEMConfig, przedstawiono wymagania wstępne, przedstawiono sposób tworzenia profilu konfiguracji oraz listę obsługiwanych aplikacji OEMConfig w usłudze Intune.

## <a name="overview"></a>Przegląd

Zasady OEMConfig są specjalnym typem zasad konfiguracji urządzeń podobnymi do [zasad konfiguracji aplikacji](app-configuration-policies-overview.md). OEMConfig jest standardem zdefiniowanym przez firmę Google, który wykorzystuje konfigurację aplikacji w systemie Android do wysyłania ustawień urządzenia do aplikacji tworzonych przez producentów OEM (producenci oryginalnego sprzętu). Standard ten umożliwia producentom OEM i EMMs (Enterprise Mobility Management) Tworzenie i obsługę funkcji specyficznych dla producenta OEM w ustandaryzowany sposób. [Dowiedz się więcej o OEMConfig](https://blog.google/products/android-enterprise/oemconfig-supports-enterprise-device-features/).

Historycznie, EMMs, na przykład usługa Intune, ręcznie Kompiluj obsługę funkcji specyficznych dla producenta OEM po wprowadzeniu ich przez producenta OEM. To podejście prowadzi do duplikowania wysiłków i wolnego przyjęcia.

W programie OEMConfig producent OEM tworzy schemat, który definiuje funkcje zarządzania specyficzne dla producenta OEM. Producent OEM osadza schemat w aplikacji, a następnie umieszcza tę aplikację na Google Play. Moduł EMM odczytuje schemat z aplikacji i uwidacznia schemat w konsoli administratora modułu EMM. W konsoli programu Administratorzy usługi Intune mogą konfigurować ustawienia w schemacie.

Gdy aplikacja OEMConfig jest instalowana na urządzeniu, używa ustawień skonfigurowanych w konsoli administratora modułu EMM do zarządzania urządzeniem. Ustawienia na urządzeniu są wykonywane przez aplikację OEMConfig zamiast agenta MDM utworzonego przez moduł EMM.

Gdy producent OEM dodaje i poprawi funkcje zarządzania, producent OEM aktualizuje również aplikację w Google Play. Jako administrator otrzymujesz te nowe funkcje i aktualizacje (w tym poprawki) bez czekania, aż program EMMs uwzględni te aktualizacje.

> [!TIP]
> OEMConfig można używać tylko z urządzeniami, które obsługują tę funkcję, i mają odpowiednią aplikację OEMConfig. Aby uzyskać szczegółowe informacje, skontaktuj się z producentem OEM.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Korzystając z OEMConfig, należy pamiętać o następujących informacjach:

- Usługa Intune udostępnia schemat aplikacji OEMConfig, dzięki czemu można go skonfigurować. Usługa Intune nie weryfikuje ani nie zmienia schematu dostarczonego przez aplikację. Dlatego jeśli schemat jest nieprawidłowy lub ma niedokładne dane, te dane są nadal wysyłane do urządzeń. Jeśli znajdziesz problem pochodzący ze schematu, skontaktuj się z producentem OEM, aby uzyskać wskazówki.
- Usługa Intune nie ma wpływu na zawartość schematu aplikacji ani nie kontroluje jej. Na przykład usługa Intune nie ma żadnej kontroli nad ciągami, językiem, dozwolonymi akcjami i tak dalej. Zalecamy skontaktowanie się z producentem OEM w celu uzyskania szczegółowych informacji i najlepszych rozwiązań związanych z zarządzaniem urządzeniami przy użyciu usługi OEMConfig.
- W dowolnym momencie producenci OEM mogą zaktualizować obsługiwane funkcje i schematy oraz przekazać nową aplikację do Google Play. Usługa Intune zawsze synchronizuje najnowszą wersję aplikacji OEMConfig z Google Play. Usługa Intune nie zachowuje starszych wersji schematu ani aplikacji. Jeśli wystąpią konflikty wersji, zalecamy skontaktowanie się z producentem OEM, aby uzyskać więcej informacji.
- Przypisz jeden profil OEMConfig do urządzenia. Jeśli do tego samego urządzenia jest przypisanych wiele profilów, może być widoczne zachowanie niespójne. Model OEMConfig obsługuje tylko pojedyncze zasady dla każdego urządzenia.

## <a name="prerequisites"></a>Wymagania wstępne

Aby korzystać z OEMConfig na urządzeniach, upewnij się, że masz następujące wymagania:

- Urządzenie z systemem Android Enterprise zarejestrowane w usłudze Intune.
- Aplikacja OEMConfig skompilowana przez producenta OEM i przekazana do Google Play. Jeśli nie jest on Google Play, skontaktuj się z producentem OEM, aby uzyskać więcej informacji.
- Administrator usługi Intune ma uprawnienia kontroli dostępu opartej na rolach (RBAC) dla **aplikacji mobilnych** i **DeviceConfigurations**. Te uprawnienia są wymagane, ponieważ profile OEMConfig używają konfiguracji aplikacji zarządzanych do zarządzania konfiguracjami urządzeń.

## <a name="prepare-the-oemconfig-app"></a>Przygotowywanie aplikacji OEMConfig

Upewnij się, że urządzenie obsługuje OEMConfig, poprawna aplikacja OEMConfig jest dodawana do usługi Intune, a aplikacja jest zainstalowana na urządzeniu. Aby uzyskać te informacje, skontaktuj się z producentem OEM.

> [!TIP] 
> Aplikacje OEMConfig są specyficzne dla producenta OEM. Na przykład aplikacja Sony OEMConfig zainstalowana na urządzeniu technologii zebry nie wykonuje żadnych działań.

1. Pobierz aplikację OEMConfig z zarządzanego Sklep Google Play. Kroki procedury znajdziesz w artykule [Dodawanie zarządzanych aplikacji ze sklepu Google Play do urządzeń z systemem Android Enterprise z usługą Intune](apps-add-android-for-work.md).
2. Niektórzy producenci OEM mogą dostarczać urządzenia ze wstępnie zainstalowaną aplikacją OEMConfig. Jeśli aplikacja nie jest wstępnie zainstalowana, Użyj usługi Intune, aby [dodać aplikację i wdrożyć ją na urządzeniach](apps-deploy.md).

## <a name="create-an-oemconfig-profile"></a>Tworzenie profilu OEMConfig

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz kolejno pozycje **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Wprowadź następujące właściwości:

    - **Nazwa**: wprowadź opisową nazwę nowego profilu.
    - **Opis:** wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: wybierz pozycję **Android Enterprise**.
    - **Typ profilu**: wybierz pozycję **OEMConfig**.

4. Wybierz pozycję **skojarzona aplikacja**, wybierz istniejącą aplikację OEMConfig, która została wcześniej dodana > **OK**. Upewnij się, że wybrano poprawną aplikację OEMConfig dla urządzeń, do których są przypisywane zasady.

    Jeśli nie widzisz żadnych aplikacji na liście, skonfiguruj zarządzane Google Play i Pobierz aplikacje z magazynu zarządzanych Google Play. Kroki procedury znajdziesz w artykule [Dodawanie zarządzanych aplikacji ze sklepu Google Play do urządzeń z systemem Android Enterprise z usługą Intune](apps-add-android-for-work.md).

    > [!IMPORTANT]
    > W przypadku dodania aplikacji OEMConfig i zsynchronizowania jej do Google Play, ale nie jest ona wyświetlana jako **skojarzona aplikacja**, może być konieczne skontaktowanie się z usługą Intune w celu dołączenia aplikacji. Zobacz [Dodawanie nowej aplikacji](#supported-oemconfig-apps) (w tym artykule).

5. W obszarze **Konfigurowanie ustawień za pomocą**programu wybierz opcję użycia **projektanta konfiguracji** lub **edytora JSON**:

    > [!TIP]
    > Zapoznaj się z dokumentacją producenta OEM, aby upewnić się, że są poprawnie skonfigurowane właściwości. Te właściwości aplikacji są dołączone przez producenta OEM, a nie do usługi Intune. Usługa Intune zapewnia minimalną weryfikację właściwości lub wprowadzaną wartość. Jeśli na przykład wprowadzisz wartość `abcd` dla numeru portu, profil zostanie zapisany jako-is i wdrożony na urządzeniach przy użyciu skonfigurowanych wartości. Upewnij się, że wprowadzono odpowiednie informacje.

    - **Projektant konfiguracji**: wybranie tej opcji powoduje wyświetlenie właściwości dostępnych w schemacie aplikacji.

      - Menu kontekstowe w projektancie konfiguracji wskazują, że są dostępne więcej opcji. Na przykład menu kontekstowe może pozwolić na dodawanie, usuwanie i zmienianie kolejności ustawień. Te opcje są dołączone przez producenta OEM. Zapoznaj się z dokumentacją aplikacji OEM, aby dowiedzieć się, jak te opcje powinny być używane do tworzenia profilów.

      - Wiele ustawień ma wartości domyślne dostarczone przez producenta OEM. Aby sprawdzić, czy jest dostępna wartość domyślna, umieść kursor na ikonie informacji obok ustawienia. Etykietka narzędzia pokazuje wartości domyślne dla tego ustawienia (jeśli dotyczy) i więcej szczegółów dostarczonych przez producenta OEM.

      - Kliknięcie przycisku **Wyczyść** powoduje usunięcie ustawienia z profilu. Jeśli ustawienie nie znajduje się w profilu, jego wartość na urządzeniu nie ulegnie zmianie, gdy profil zostanie zastosowany.
        
      - Jeśli utworzysz pusty (nieskonfigurowany) pakiet w projektancie konfiguracji, zostanie on usunięty podczas przełączania do edytora JSON.

    - **Edytor JSON**: po wybraniu tej opcji Edytor JSON zostanie otwarty z szablonem pełnego schematu konfiguracji osadzonego w aplikacji. W edytorze Dostosuj szablon o wartości dla różnych ustawień. Jeśli używasz **projektanta konfiguracji** do zmiany wartości, Edytor JSON zastępuje szablon wartościami z projektanta konfiguracji.
    
      - W przypadku aktualizowania istniejącego profilu Edytor JSON pokazuje ustawienia, które zostały ostatnio zapisane z profilem.

      - Schematy OEMConfig mogą być duże i złożone. Jeśli wolisz zaktualizować te ustawienia przy użyciu innego edytora, wybierz przycisk **Pobierz szablon JSON** . Użyj wybranego edytora, aby dodać do szablonu wartości konfiguracyjne. Następnie skopiuj i wklej zaktualizowany kod JSON we właściwości **Edytor JSON** .

      - Aby utworzyć kopię zapasową konfiguracji, można użyć edytora JSON. Po skonfigurowaniu ustawień użyj tej funkcji, aby pobrać ustawienia JSON z wartościami. Skopiuj i wklej kod JSON do pliku i Zapisz go. Teraz masz plik kopii zapasowej.

    Wszystkie zmiany wprowadzone w projektancie konfiguracji są również automatycznie wprowadzane w edytorze JSON. Podobnie wszelkie zmiany wprowadzone w edytorze JSON są automatycznie tworzone w programie Configuration Designer. Jeśli dane wejściowe zawierają nieprawidłowe wartości, nie można przełączać się między projektantem konfiguracji i edytorem JSON do momentu rozwiązania problemów.

6. Wybierz **przycisk OK** > **Dodaj** , aby zapisać zmiany. Zasady zostaną utworzone i wyświetlone na liście.

Pamiętaj, aby [przypisać profil](device-profile-assign.md) i [monitorować jego stan](device-profile-monitor.md).

 > [!NOTE]
 > Do każdego urządzenia przypisz jeden profil. Model OEMConfig obsługuje tylko jedną zasadę na urządzenie.

Przy następnym sprawdzaniu przez urządzenie aktualizacji konfiguracji ustawienia specyficzne dla producenta OEM zostaną zastosowane do aplikacji OEMConfig.

> [!NOTE]
> Standard OEMConfig nie obejmuje obecnie raportów o stanie. W związku z tym domyślnie profile są wyświetlane jako **oczekujące** .

## <a name="supported-oemconfig-apps"></a>Obsługiwane aplikacje OEMConfig

W porównaniu do standardowych aplikacji aplikacje OEMConfig rozszerzają uprawnienia do konfiguracji zarządzanych przyznane przez firmę Google, aby obsługiwały bardziej złożone schematy. Usługa Intune obsługuje obecnie następujące aplikacje OEMConfig:

-----------------

| OEM | Identyfikator pakietu | Dokumentacja OEM (jeśli jest dostępna) |
| --- | --- | ---|
| Samsunga | com. Samsung. Android. Knox. KPU | [Przewodnik administratora wtyczki usługi Knox](https://docs.samsungknox.com/knox-service-plugin/admin-guide/welcome.htm) |
| Technologie zebry | com. zebry. oemconfig. Common | [Zebry OEMConfig — Omówienie](http://techdocs.zebra.com/oemconfig ) |
| Logika Datalogic | com. Datalogic. oemconfig | [Dokumentacja użytkownika dotycząca usługi Datalogic OEMConfig](https://datalogic.github.io/oemconfig/) |
| Honeywell | com. Honeywell. oemconfig |  |

-----------------

Jeśli aplikacja OEMConfig istnieje dla urządzenia, ale nie znajduje się w powyższej tabeli lub nie jest wyświetlana w konsoli usługi Intune, Wyślij wiadomość e-mail `IntuneOEMConfig@microsoft.com`.

> [!NOTE]
> Aplikacje OEMConfig muszą być dołączone do usługi Intune, zanim będą mogły zostać skonfigurowane za pomocą profilów OEMConfig. Gdy aplikacja jest obsługiwana, nie musisz kontaktować się z firmą Microsoft, aby ją skonfigurować w dzierżawie. Po prostu postępuj zgodnie z instrukcjami na tej stronie.

## <a name="next-steps"></a>Następne kroki

- [Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).
