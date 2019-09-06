---
title: Zasady konfiguracji aplikacji usługi Microsoft Intune
titleSuffix: ''
description: Dowiedz się, jak używać zasad konfiguracji aplikacji na urządzeniach z systemem iOS lub Android w usłudze Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/28/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cda0453009855d96e7c13e170ba908479a0773ea
ms.sourcegitcommit: 513e805bbea8bf652c2901dfc5460e34946077df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/29/2019
ms.locfileid: "70160582"
---
# <a name="app-configuration-policies-for-microsoft-intune"></a>Zasady konfiguracji aplikacji usługi Microsoft Intune

Zasady konfiguracji aplikacji mogą pomóc w wyeliminowaniu problemów z konfigurowaniem aplikacji, umożliwiając przypisanie ustawień konfiguracji do zasad, które są przypisywane do użytkowników końcowych, zanim uruchomią oni aplikację. Ustawienia są następnie dostarczane automatycznie podczas konfigurowania aplikacji na urządzeniach użytkowników końcowych, a użytkownicy końcowi nie muszą podejmować żadnego działania. Ustawienia konfiguracji są unikatowe dla każdej aplikacji. 

Zasady konfiguracji aplikacji można utworzyć i używać ich w celu dostarczania ustawień konfiguracji dla aplikacji systemu iOS lub Android. Te ustawienia konfiguracji umożliwiają dostosowanie aplikacji przy użyciu [standardowego podejścia](https://www.appconfig.org/) do konfigurowania aplikacji i zarządzania nimi. Ustawienia zasad konfiguracji są stosowane, gdy aplikacja sprawdza te ustawienia (zazwyczaj podczas pierwszego uruchomienia aplikacji). 

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
> ![Zrzut ekranu przedstawiający skonfigurowaną aplikację](./media/app-configuration-policy-overview/configured-app.png)
>
> W przypadku korzystania z typu rejestracji Urządzenia zarządzane dla urządzeń z systemem Android będą widoczne tylko aplikacje z [zarządzanego sklepu Google Play](https://play.google.com/work), a nie ze [sklepu Google Play](https://play.google.com/store/apps). Zarządzany sklep Google Play, znany również jako program Android for Work (AfW) i rozwiązanie Android Enterprise, to aplikacje w profilu służbowym, które zawierają wersje aplikacji obsługujące konfigurację aplikacji.

Zasady konfiguracji aplikacji możesz przypisać do grupy użytkowników końcowych i urządzeń za pomocą kombinacji [dołączania i wykluczania przypisań](apps-inc-exl-assignments.md). Po dodaniu zasad konfiguracji aplikacji możesz ustawić przypisania zasad konfiguracji aplikacji. Po ustawieniu przypisań dla zasad możesz dołączać i wykluczać [grupy](groups-add.md) użytkowników końcowych, dla których zasady będą stosowane. Po wybraniu dołączenia co najmniej jednej grupy możesz wybrać określone grupy do dołączenia lub wybrać wbudowane grupy. Wbudowane grupy to **Wszyscy użytkownicy**, **Wszystkie urządzenia** oraz **Wszyscy użytkownicy i wszystkie urządzenia**.

Dostępne są dwie opcje używania zasad konfiguracji aplikacji z usługą Intune:
- **Urządzenia zarządzane** — urządzenie jest zarządzane przez usługę Intune działającą jako dostawca rozwiązania do zarządzania urządzeniami przenośnymi (MDM). Aplikacja musi być zaprojektowana tak, aby obsługiwała konfigurację aplikacji.
- **Aplikacje zarządzane** — aplikacja opracowana pod kątem integracji zestawu SDK aplikacji usługi Intune. Jest to nazywane zarządzaniem aplikacjami mobilnymi bez rejestracji (mechanizm [MAM-WE](app-management.md#mobile-application-management-mam-basics)). Możesz również opakować aplikację, aby zaimplementować i obsługiwać zestaw SDK aplikacji usługi Intune. Aby uzyskać więcej informacji na temat opakowywania aplikacji, zobacz [Przygotowanie aplikacji biznesowych pod kątem zasad ochrony aplikacji](apps-prepare-mobile-application-management.md).

    > [!NOTE]
    > Aplikacje zarządzane przez usługę Intune będą wykonywać ewidencjonowanie z interwałem 30 minut dla stanu zasad konfiguracji aplikacji usługi Intune w przypadku wdrożenia w połączeniu z zasadami Intune App Protection. Jeśli zasady Intune App Protection nie są przypisane do użytkownika, interwał ewidencjonowania zasad konfiguracji aplikacji usługi Intune jest ustawiony na 720 minut.

## <a name="apps-that-support-app-configuration"></a>Aplikacje obsługujące konfigurację aplikacji

### <a name="managed-devices"></a>Urządzenia zarządzane
Zasad konfiguracji aplikacji można używać w przypadku aplikacji, które je obsługują. Aby można było używać konfiguracji aplikacji w usłudze Intune, aplikacje muszą być napisane tak, aby obsługiwały korzystanie z konfiguracji aplikacji w sposób zdefiniowany przez społeczność [AppConfig Community](https://www.appconfig.org/members). Aby uzyskać więcej informacji, skontaktuj się z dostawcą aplikacji.

### <a name="managed-apps"></a>Aplikacje zarządzane
Aplikacje biznesowe można przygotować, włączając do aplikacji [zestaw SDK aplikacji usługi Intune](app-sdk.md) lub opakowując opracowaną aplikację przy użyciu [narzędzia opakowującego aplikacje usługi Intune](apps-prepare-mobile-application-management.md). Zestaw SDK aplikacji usługi Intune kładzie nacisk na minimalizację liczby zmian kodu wymaganych od dewelopera aplikacji. Aby uzyskać więcej informacji, zobacz [Omówienie zestawu SDK aplikacji usługi Intune](app-sdk.md). Aby zapoznać się z porównaniem zestawu SDK aplikacji usługi Intune i narzędzia opakowującego aplikacje usługi Intune, zobacz [Przygotowanie aplikacji biznesowych pod kątem zasad ochrony aplikacji](apps-prepare-mobile-application-management.md#feature-comparison).

Wybór opcji **Aplikacje zarządzane** jako **Typ rejestracji urządzenia** odnosi się do aplikacji konfigurowanych za pomocą zasad konfiguracji usługi Intune na urządzeniu niezarejestrowanym w rozwiązaniu do zarządzania urządzeniami, natomiast wybór opcji **Urządzenia zarządzane** odnosi się do aplikacji wdrażanych za pośrednictwem kanału zarządzania urządzeniami przenośnymi, a tym samym zarządzanych przez usługę Intune. Wybierz odpowiednią opcję na podstawie tych opisów. 

![Typ rejestracji urządzenia](./media/app-configuration-policy-overview/device-enrollment-type.png)

> [!NOTE]
> W przypadku aplikacji z obsługą wielu tożsamości, takich jak program Microsoft Outlook, można wziąć pod uwagę preferencje użytkownika. Na przykład priorytetowa skrzynka odbiorcza będzie uwzględniać ustawienie użytkownika i nie będzie zmieniać konfiguracji. Inne parametry pozwalają określić, czy użytkownik może zmienić ustawienie. Aby uzyskać więcej informacji, zobacz temat [Deploying Outlook for iOS and Android app configuration settings](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune) (Wdrażanie ustawień konfiguracji aplikacji Outlook dla systemu iOS i Android).

## <a name="validate-the-applied-app-configuration-policy"></a>Weryfikowanie zastosowanych zasad konfiguracji aplikacji

Zasady konfiguracji aplikacji można zweryfikować przy użyciu następujących trzech metod:

   1. Na urządzeniu. Czy aplikacja docelowa wykazuje zachowanie zastosowane w zasadach konfiguracji aplikacji?
   2. Za pomocą dzienników diagnostycznych (zobacz sekcję Dzienniki diagnostyczne poniżej).
   3. W portalu usługi Intune. Odpowiedni stan można sprawdzić w sekcji **Monitorowanie** zasad:

      ![Pierwszy zrzut ekranu przedstawiający stan instalacji urządzenia](./media/app-configuration-policy-overview/device-install-status-1.png)

      ![Drugi zrzut ekranu przedstawiający stan instalacji urządzenia](./media/app-configuration-policy-overview/device-install-status-2.png)

      Ponadto w obszarze **Intune** -> **Urządzenia** -> **Wszystkie urządzenia** po lewej stronie ekranu można wybrać opcję **Konfiguracja aplikacji** , aby wyświetlić wszystkie przypisane zasady i ich stan:

      ![Zrzut ekranu przedstawiający konfigurację aplikacji](./media/app-configuration-policy-overview/app-configuration.png)

## <a name="graph-api-support-for-app-configuration"></a>Obsługa interfejsu API programu Graph w konfiguracji aplikacji

W celu wykonania zadań konfiguracji aplikacji można używać interfejsu API programu Graph. Aby uzyskać więcej informacji, zobacz [Graph API Reference MAM Targeted Config](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create) (Dokumentacja interfejsu API programu Graph — konfiguracja podlegająca zarządzaniu aplikacjami mobilnymi).

## <a name="troubleshooting"></a>Rozwiązywanie problemów

### <a name="using-logs-to-show-a-configuration-parameter"></a>Korzystanie z dzienników w celu wyświetlenia parametru konfiguracji
Jeśli w dziennikach jest wyświetlany parametr konfiguracji, który został potwierdzony do zastosowania, ale wydaje się nie działać, być może występuje problem z implementacją konfiguracji przez dewelopera aplikacji. Skontaktowanie się najpierw z tym deweloperem aplikacji lub sprawdzenie jego bazy wiedzy często pozwala uniknąć konieczności przesyłania zgłoszenia do działu pomocy technicznej firmy Microsoft. Jeśli problem jest związany ze sposobem obsługi konfiguracji w aplikacji, będzie musiał zostać rozwiązany w przyszłej zaktualizowanej wersji tej aplikacji.

## <a name="next-steps"></a>Następne kroki

### <a name="managed-devices"></a>Urządzenia zarządzane

- Dowiedz się, jak używać konfiguracji aplikacji na urządzeniach z systemem iOS.  Zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem iOS](app-configuration-policies-use-ios.md).
- Dowiedz się, jak używać konfiguracji aplikacji na urządzeniach z systemem Android.  Zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem Android](app-configuration-policies-use-android.md).

### <a name="managed-apps"></a>Aplikacje zarządzane

- Dowiedz się, jak używać konfiguracji aplikacji z zarządzanymi aplikacjami. Zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych aplikacji bez rejestracji urządzeń](app-configuration-policies-managed-app.md).
