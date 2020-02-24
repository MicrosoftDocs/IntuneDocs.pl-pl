---
title: Zasady konfiguracji aplikacji usługi Microsoft Intune
titleSuffix: ''
description: Dowiedz się, jak używać zasad konfiguracji aplikacji na urządzeniach z systemem iOS, iPadOS lub Android w usłudze Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/06/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a2cf53b26c1617ca7fc493c837e57823c23781bc
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2020
ms.locfileid: "77414858"
---
# <a name="app-configuration-policies-for-microsoft-intune"></a>Zasady konfiguracji aplikacji usługi Microsoft Intune

Zasady konfiguracji aplikacji mogą pomóc w wyeliminowaniu problemów z konfigurowaniem aplikacji, umożliwiając przypisanie ustawień konfiguracji do zasad, które są przypisywane do użytkowników końcowych, zanim uruchomią oni aplikację. Ustawienia są następnie dostarczane automatycznie podczas konfigurowania aplikacji na urządzeniach użytkowników końcowych, a użytkownicy końcowi nie muszą podejmować żadnego działania. Ustawienia konfiguracji są unikatowe dla każdej aplikacji. 

Zasady konfiguracji aplikacji można utworzyć i używać ich w celu dostarczania ustawień konfiguracji dla aplikacji systemu iOS, iPadOS lub Android. Te ustawienia konfiguracji umożliwiają dostosowanie aplikacji przy użyciu zasad konfigurowania aplikacji i zarządzania nią. Ustawienia zasad konfiguracji są stosowane, gdy aplikacja sprawdza te ustawienia (zazwyczaj podczas pierwszego uruchomienia aplikacji). 

Ustawienie konfiguracji aplikacji może wymagać na przykład określenia następujących szczegółów:

- Niestandardowy numer portu
- Ustawienia języka
- Ustawienia zabezpieczeń
- Ustawienia oznaczeń marki, takich jak logo firmy

Gdyby te ustawienia mieli wprowadzać użytkownicy końcowi, mogliby to zrobić nieprawidłowo. Zasady konfiguracji aplikacji mogą pomóc zapewnić spójność w całym przedsiębiorstwie i ograniczyć liczbę zgłoszeń do pomocy technicznej od użytkowników końcowych próbujących samodzielnie skonfigurować ustawienia. Dzięki użyciu zasad konfiguracji aplikacji wdrażanie nowych aplikacji może być łatwiejsze i szybsze.

O dostępnych parametrach konfiguracji ostatecznie decydują deweloperzy aplikacji. Aby sprawdzić, czy aplikacja obsługuje konfigurację i jakie konfiguracje są dostępne, należy zapoznać się z dokumentacją dostawcy aplikacji. W przypadku niektórych aplikacji usługa Intune wypełni dostępne ustawienia konfiguracji. 

> [!NOTE]
> W zarządzanym sklepie Google Play aplikacje obsługujące konfigurację będą oznaczone jako takie:
> 
> ![Zrzut ekranu przedstawiający skonfigurowaną aplikację](./media/app-configuration-policies-overview/configured-app.png)
>
> W przypadku korzystania z typu rejestracji Urządzenia zarządzane dla urządzeń z systemem Android będą widoczne tylko aplikacje z [zarządzanego sklepu Google Play](https://play.google.com/work), a nie ze [sklepu Google Play](https://play.google.com/store/apps). Zarządzany sklep Google Play, znany również jako program Android for Work (AfW) i rozwiązanie Android Enterprise, to aplikacje w profilu służbowym, które zawierają wersje aplikacji obsługujące konfigurację aplikacji.

Zasady konfiguracji aplikacji możesz przypisać do grupy użytkowników końcowych i urządzeń za pomocą kombinacji [dołączania i wykluczania przypisań](apps-inc-exl-assignments.md). Po dodaniu zasad konfiguracji aplikacji możesz ustawić przypisania zasad konfiguracji aplikacji. Po ustawieniu przypisań dla zasad możesz dołączać i wykluczać [grupy](../fundamentals/groups-add.md) użytkowników końcowych, dla których zasady będą stosowane. Po wybraniu dołączenia co najmniej jednej grupy możesz wybrać określone grupy do dołączenia lub wybrać wbudowane grupy. Wbudowane grupy to **Wszyscy użytkownicy**, **Wszystkie urządzenia** oraz **Wszyscy użytkownicy i wszystkie urządzenia**.

Dostępne są dwie opcje używania zasad konfiguracji aplikacji z usługą Intune:
- **Urządzenia zarządzane** — urządzenie jest zarządzane przez usługę Intune działającą jako dostawca rozwiązania do zarządzania urządzeniami przenośnymi (MDM). Aplikacja musi być zaprojektowana tak, aby obsługiwała konfigurację aplikacji.
- **Aplikacje zarządzane** — aplikacja opracowana pod kątem integracji zestawu SDK aplikacji usługi Intune. Jest to nazywane zarządzaniem aplikacjami mobilnymi bez rejestracji (mechanizm [MAM-WE](app-management.md#mobile-application-management-mam-basics)). Możesz również opakować aplikację, aby zaimplementować i obsługiwać zestaw SDK aplikacji usługi Intune. Aby uzyskać więcej informacji na temat opakowywania aplikacji, zobacz [Przygotowanie aplikacji biznesowych pod kątem zasad ochrony aplikacji](../developer/apps-prepare-mobile-application-management.md).

    > [!NOTE]
    > Aplikacje zarządzane przez usługę Intune będą wykonywać ewidencjonowanie z interwałem 30 minut dla stanu zasad konfiguracji aplikacji usługi Intune w przypadku wdrożenia w połączeniu z zasadami Intune App Protection. Jeśli zasady Intune App Protection nie są przypisane do użytkownika, interwał ewidencjonowania zasad konfiguracji aplikacji usługi Intune jest ustawiony na 720 minut.

## <a name="apps-that-support-app-configuration"></a>Aplikacje obsługujące konfigurację aplikacji

### <a name="managed-devices"></a>Urządzenia zarządzane
Zasad konfiguracji aplikacji można używać w przypadku aplikacji, które je obsługują. Aby można było używać konfiguracji aplikacji w usłudze Intune, aplikacje muszą być napisane w sposób umożliwiający korzystanie z konfiguracji aplikacji zdefiniowanych przez system operacyjny. Aby uzyskać szczegółowe informacje o obsługiwanych kluczach konfiguracji aplikacji, skontaktuj się z dostawcą aplikacji.

### <a name="managed-apps"></a>Aplikacje zarządzane
Aplikacje biznesowe można przygotować, włączając do aplikacji [zestaw SDK aplikacji usługi Intune](../developer/app-sdk.md) lub opakowując opracowaną aplikację przy użyciu [narzędzia opakowującego aplikacje usługi Intune](../developer/apps-prepare-mobile-application-management.md). Zestaw SDK aplikacji usługi Intune kładzie nacisk na minimalizację liczby zmian kodu wymaganych od dewelopera aplikacji. Aby uzyskać więcej informacji, zobacz [Omówienie zestawu SDK aplikacji usługi Intune](../developer/app-sdk.md). Aby zapoznać się z porównaniem zestawu SDK aplikacji usługi Intune i narzędzia opakowującego aplikacje usługi Intune, zobacz [Przygotowanie aplikacji biznesowych pod kątem zasad ochrony aplikacji](../developer/apps-prepare-mobile-application-management.md#feature-comparison).

Wybór opcji **Aplikacje zarządzane** jako **Typ rejestracji urządzenia** odnosi się do aplikacji konfigurowanych za pomocą zasad konfiguracji usługi Intune na urządzeniu niezarejestrowanym w rozwiązaniu do zarządzania urządzeniami, natomiast wybór opcji **Urządzenia zarządzane** odnosi się do aplikacji wdrażanych za pośrednictwem kanału zarządzania urządzeniami przenośnymi, a tym samym zarządzanych przez usługę Intune. Wybierz odpowiednią opcję na podstawie tych opisów. 

![Typ rejestracji urządzenia](./media/app-configuration-policies-overview/device-enrollment-type.png)

> [!NOTE]
> W przypadku aplikacji z obsługą wielu tożsamości, takich jak program Microsoft Outlook, można wziąć pod uwagę preferencje użytkownika. Na przykład priorytetowa skrzynka odbiorcza będzie uwzględniać ustawienie użytkownika i nie będzie zmieniać konfiguracji. Inne parametry pozwalają określić, czy użytkownik może zmienić ustawienie. Aby uzyskać więcej informacji, zobacz temat [Deploying Outlook for iOS/iPadOS and Android app configuration settings](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune) (Wdrażanie ustawień konfiguracji aplikacji Outlook dla systemów iOS, iPadOS i Android).

## <a name="validate-the-applied-app-configuration-policy"></a>Weryfikowanie zastosowanych zasad konfiguracji aplikacji

Zasady konfiguracji aplikacji można zweryfikować przy użyciu następujących trzech metod:

   1. Na urządzeniu. Czy aplikacja docelowa wykazuje zachowanie zastosowane w zasadach konfiguracji aplikacji?
   2. Za pomocą dzienników diagnostycznych (zobacz sekcję Dzienniki diagnostyczne poniżej).
   3. W portalu usługi Intune. Odpowiedni stan można sprawdzić w sekcji **Monitorowanie** zasad:

      ![Pierwszy zrzut ekranu przedstawiający stan instalacji urządzenia](./media/app-configuration-policies-overview/device-install-status-1.png)

      ![Drugi zrzut ekranu przedstawiający stan instalacji urządzenia](./media/app-configuration-policies-overview/device-install-status-2.png)

      Ponadto w obszarze **Intune** -> **Urządzenia** -> **Wszystkie urządzenia** po lewej stronie ekranu można wybrać opcję **Konfiguracja aplikacji** , aby wyświetlić wszystkie przypisane zasady i ich stan:

      ![Zrzut ekranu przedstawiający konfigurację aplikacji](./media/app-configuration-policies-overview/app-configuration.png)

## <a name="diagnostic-logs"></a>Dzienniki diagnostyczne

### <a name="ios-configuration-on-unmanaged-devices"></a>Konfiguracja systemu iOS na urządzeniach niezarządzanych

Konfigurację systemu iOS/iPadOS można zweryfikować za pomocą **dziennika diagnostycznego usługi Intune** na urządzeniach niezarządzanych w celu skonfigurowania aplikacji zarządzanych. Oprócz poniższych kroków można uzyskać dostęp do dzienników zarządzanych aplikacji przy użyciu przeglądarki Microsoft Edge. Więcej informacji — zobacz [Używanie przeglądarki Microsoft Edge w systemie iOS/iPadOS do uzyskiwania dostępu do dzienników aplikacji zarządzanych](~/apps/manage-microsoft-edge.md#use-microsoft-edge-on-ios-to-access-managed-app-logs).

1. Jeśli przeglądarka **Microsoft Edge** nie została jeszcze zainstalowana na urządzeniu, pobierz ją ze sklepu App Store i zainstaluj. Aby uzyskać więcej informacji, zobacz [Chronione aplikacje w usłudze Microsoft Intune](apps-supported-intune-apps.md).
2. Uruchom przeglądarkę **Microsoft Edge** i wybierz pozycję **about** > **intunehelp** na pasku nawigacyjnym.
3. Kliknij pozycję **Rozpocznij**.
4. Kliknij pozycję **Udostępnij dzienniki**.
5. Użyj wybranej aplikacji poczty, aby wysłać do siebie dziennik i umożliwić przeglądanie go na komputerze. 
6. Przejrzyj plik **IntuneMAMDiagnostics.txt** w przeglądarce plików tekstowych.
7. Wyszukaj ciąg `ApplicationConfiguration`. Wyniki będą wyglądać podobnie do następujących:

    ``` JSON
        {
            (
                {
                    Name = "com.microsoft.intune.mam.managedbrowser.BlockListURLs";
                    Value = "https://www.aol.com";
                },
                {
                    Name = "com.microsoft.intune.mam.managedbrowser.bookmarks";
                    Value = "Outlook Web|https://outlook.office.com||Bing|https://www.bing.com";
                }
            );
        },
        {
            ApplicationConfiguration =             
            (
                {
                Name = IntuneMAMUPN;
                Value = "CMARScrubbedM:13c45c42712a47a1739577e5c92b5bc86c3b44fd9a27aeec3f32857f69ddef79cbb988a92f8241af6df8b3ced7d5ce06e2d23c33639ddc2ca8ad8d9947385f8a";
                },
                {
                Name = "com.microsoft.outlook.Mail.NotificationsEnabled";
                Value = false;
                }
            );
        }
    ```

Szczegóły konfiguracji aplikacji powinny być zgodne z zasadami konfiguracji aplikacji skonfigurowanymi w dzierżawie. 

![Docelowa konfiguracja aplikacji](./media/app-configuration-policies-overview/targeted-app-configuration-3.png)

### <a name="ios-configuration-on-managed-devices"></a>Konfiguracja systemu iOS na urządzeniach zarządzanych

Konfigurację systemu iOS/iPadOS można zweryfikować za pomocą **dziennika diagnostycznego usługi Intune** na urządzeniach zarządzanych w celu skonfigurowania aplikacji zarządzanych.

1. Jeśli przeglądarka **Microsoft Edge** nie została jeszcze zainstalowana na urządzeniu, pobierz ją ze sklepu App Store i zainstaluj. Aby uzyskać więcej informacji, zobacz [Chronione aplikacje w usłudze Microsoft Intune](apps-supported-intune-apps.md).
2. Uruchom przeglądarkę **Microsoft Edge** i wybierz pozycję **about** > **intunehelp** na pasku nawigacyjnym.
3. Kliknij pozycję **Rozpocznij**.
4. Kliknij pozycję **Udostępnij dzienniki**.
5. Użyj wybranej aplikacji poczty, aby wysłać do siebie dziennik i umożliwić przeglądanie go na komputerze. 
6. Przejrzyj plik **IntuneMAMDiagnostics.txt** w przeglądarce plików tekstowych.
7. Wyszukaj ciąg `AppConfig`. Wyniki powinny być zgodne z zasadami konfiguracji aplikacji skonfigurowanymi w dzierżawie.

### <a name="android-configuration-on-managed-devices"></a>Konfiguracja systemu Android na urządzeniach zarządzanych

Konfigurację systemu iOS/iPadOS można zweryfikować za pomocą **dziennika diagnostycznego usługi Intune** na urządzeniach zarządzanych w celu skonfigurowania aplikacji zarządzanych.

Aby zbierać dzienniki z urządzenia z systemem Android, Ty lub użytkownik końcowy musicie pobrać dzienniki z urządzenia za pośrednictwem połączenia USB (lub odpowiednika narzędzia **Eksplorator plików** na urządzeniu). Oto kroki do wykonania:

1. Podłącz urządzenie z systemem Android do komputera za pomocą kabla USB.
2. Na komputerze wyszukaj katalog o nazwie odpowiadającej nazwie urządzenia. W tym katalogu znajdź folder `Android Device\Phone\Android\data\com.microsoft.windowsintune.companyportal`.
3. W folderze `com.microsoft.windowsintune.companyportal` otwórz folder Files i otwórz element `OMADMLog_0`.
3. Wyszukaj folder `AppConfigHelper`, aby znaleźć komunikaty powiązane z konfiguracją aplikacji. Wyniki będą wyglądać podobnie do następującego bloku danych:

    `2019-06-17T20:09:29.1970000       INFO   AppConfigHelper     10888  02256  Returning app config JSON [{"ApplicationConfiguration":[{"Name":"com.microsoft.intune.mam.managedbrowser.BlockListURLs","Value":"https:\/\/www.aol.com"},{"Name":"com.microsoft.intune.mam.managedbrowser.bookmarks","Value":"Outlook Web|https:\/\/outlook.office.com||Bing|https:\/\/www.bing.com"},{"Name":"com.microsoft.intune.mam.managedbrowser.homepage","Value":"https:\/\/www.arstechnica.com"}]},{"ApplicationConfiguration":[{"Name":"IntuneMAMUPN","Value":"AdeleV@M365x935807.OnMicrosoft.com"},{"Name":"com.microsoft.outlook.Mail.NotificationsEnabled","Value":"false"},{"Name":"com.microsoft.outlook.Mail.NotificationsEnabled.UserChangeAllowed","Value":"false"}]}] for user User-875363642`
    
## <a name="graph-api-support-for-app-configuration"></a>Obsługa interfejsu API programu Graph w konfiguracji aplikacji

W celu wykonania zadań konfiguracji aplikacji można używać interfejsu API programu Graph. Aby uzyskać więcej informacji, zobacz [Graph API Reference MAM Targeted Config](https://docs.microsoft.com/graph/api/resources/intune-shared-targetedmanagedappconfiguration?view=graph-rest-beta) (Dokumentacja interfejsu API programu Graph — konfiguracja podlegająca zarządzaniu aplikacjami mobilnymi). Aby uzyskać więcej informacji na temat usługi Intune i programu Graph, zobacz artykuł [Praca z usługą Intune w programie Microsoft Graph](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-beta).

## <a name="troubleshooting"></a>Rozwiązywanie problemów

### <a name="using-logs-to-show-a-configuration-parameter"></a>Korzystanie z dzienników w celu wyświetlenia parametru konfiguracji
Jeśli w dziennikach jest wyświetlany parametr konfiguracji, który został potwierdzony do zastosowania, ale wydaje się nie działać, być może występuje problem z implementacją konfiguracji przez dewelopera aplikacji. Skontaktowanie się najpierw z tym deweloperem aplikacji lub sprawdzenie jego bazy wiedzy często pozwala uniknąć konieczności przesyłania zgłoszenia do działu pomocy technicznej firmy Microsoft. Jeśli problem jest związany ze sposobem obsługi konfiguracji w aplikacji, będzie musiał zostać rozwiązany w przyszłej zaktualizowanej wersji tej aplikacji.

## <a name="next-steps"></a>Następne kroki

### <a name="managed-devices"></a>Urządzenia zarządzane

- Dowiedz się, jak używać konfiguracji aplikacji na urządzeniach z systemem iOS/iPadOS.  Zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem iOS/iPadOS](app-configuration-policies-use-ios.md).
- Dowiedz się, jak używać konfiguracji aplikacji na urządzeniach z systemem Android.  Zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem Android](app-configuration-policies-use-android.md).

### <a name="managed-apps"></a>Aplikacje zarządzane

- Dowiedz się, jak używać konfiguracji aplikacji z zarządzanymi aplikacjami. Zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych aplikacji bez rejestracji urządzeń](app-configuration-policies-managed-app.md).
