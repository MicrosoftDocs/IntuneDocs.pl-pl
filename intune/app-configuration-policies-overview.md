---
title: Zasady konfiguracji aplikacji usługi Microsoft Intune
titleSuffix: ''
description: Dowiedz się, jak używać zasad konfiguracji aplikacji na urządzeniach z systemem iOS lub Android w usłudze Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/08/2019
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
ms.openlocfilehash: 1e5ddf39a201f1a70f997e03f0b65706853adefa
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/15/2019
ms.locfileid: "67885115"
---
# <a name="app-configuration-policies-for-microsoft-intune"></a>Zasady konfiguracji aplikacji usługi Microsoft Intune

Zasady konfiguracji aplikacji w usłudze Microsoft Intune umożliwiają określenie ustawień konfiguracji dla aplikacji systemu iOS lub Android. Te ustawienia konfiguracji umożliwiają dostosowanie aplikacji przy użyciu standardowego podejścia do konfigurowania aplikacji i zarządzania nimi. Ustawienia zasad konfiguracji są stosowane, gdy aplikacja je wyszukuje (zazwyczaj podczas pierwszego uruchomienia).

Zasady konfiguracji aplikacji możesz przypisać do grupy użytkowników i urządzeń za pomocą kombinacji dołączania i wykluczania przypisań. Po dodaniu zasad konfiguracji aplikacji możesz ustawić przypisania zasad konfiguracji aplikacji. Po ustawieniu przypisań dla zasad możesz dołączać i wykluczać grupy użytkowników, dla których zasady będą stosowane. Po wybraniu dołączenia co najmniej jednej grupy możesz wybrać określone grupy do dołączenia lub wybrać wbudowane grupy. Wbudowane grupy to **Wszyscy użytkownicy**, **Wszystkie urządzenia** oraz **Wszyscy użytkownicy i wszystkie urządzenia**.

Ustawienie konfiguracji aplikacji może wymagać na przykład określenia następujących szczegółów:

- Niestandardowy numer portu
- Ustawienia języka
- Ustawienia zabezpieczeń
- Ustawienia oznaczeń marki, takich jak logo firmy

Jeśli zamiast tego użytkownicy mieliby sami wprowadzać te ustawienia, mogliby wprowadzić je nieprawidłowo, co mogłoby zwiększyć obciążenie działu pomocy technicznej i spowolnić wdrażanie nowych aplikacji.

Zasady konfiguracji aplikacji mogą pomóc w wyeliminowaniu problemów z konfigurowaniem aplikacji, umożliwiając przypisywanie ustawień konfiguracji do zasad, które są przypisywane do użytkowników, zanim uruchomią oni aplikację. Ustawienia są następnie określane automatycznie, a użytkownicy nie muszą podejmować żadnej akcji.

Ustawienia konfiguracji są używane za każdym razem, gdy aplikacja je wyszukuje. Zazwyczaj aplikacja wyszukuje ustawienia konfiguracji podczas pierwszego uruchomienia przez użytkownika.

Dostępne są dwie opcje używania konfiguracji aplikacji z usługą Intune:
- **Urządzenia zarządzane** — urządzenie jest zarządzane przez usługę Intune działającą jako dostawca rozwiązania do zarządzania urządzeniami przenośnymi (MDM).
- **Aplikacje zarządzane** — zarządzanie aplikacją odbywa się bez rejestracji urządzenia.

> [!NOTE]
> Jako administrator usługi Microsoft Intune masz możliwość kontrolowania kont użytkownika dodawanych do aplikacji pakietu Microsoft Office na urządzeniach zarządzanych. Istnieje możliwość ograniczenia dostępu tylko do dozwolonych kont użytkowników w organizacji oraz blokowania kont osobistych na zarejestrowanych urządzeniach. Aplikacje pomocnicze przetwarzają konfigurację aplikacji i usuwają oraz blokują niezatwierdzone konta.

## <a name="apps-that-support-app-configuration"></a>Aplikacje obsługujące konfigurację aplikacji

### <a name="managed-devices"></a>Urządzenia zarządzane
Można używać zasad konfiguracji aplikacji w przypadku aplikacji, które je obsługują. Aby można było używać konfiguracji aplikacji w usłudze Intune, aplikacje muszą być napisane tak, aby obsługiwały korzystanie z konfiguracji aplikacji w sposób zdefiniowany przez społeczność [AppConfig Community](https://www.appconfig.org/members). Aby uzyskać więcej informacji, skontaktuj się z dostawcą aplikacji.

### <a name="managed-apps"></a>Aplikacje zarządzane
Aplikacje biznesowe można przygotować, włączając do aplikacji zestaw SDK aplikacji usługi Intune lub opakowując opracowaną aplikację. Korzystając z zestawu SDK aplikacji usługi Intune, dostępnego dla systemów iOS i Android, możesz obsługiwać zasady konfiguracji ochrony aplikacji usługi Intune w swojej aplikacji. Położono w nim nacisk na minimalizację liczby zmian kodu wymaganych od dewelopera aplikacji. Aby uzyskać więcej informacji, zobacz [Omówienie zestawu SDK aplikacji usługi Intune](app-sdk.md).

## <a name="graph-api-support-for-app-configuration"></a>Obsługa interfejsu API programu Graph w konfiguracji aplikacji

W celu wykonywania zadań konfiguracji aplikacji można używać interfejsu API programu Graph. Aby uzyskać więcej informacji, zobacz [Graph API Reference MAM Targeted Config](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create) (Dokumentacja interfejsu API programu Graph — konfiguracja podlegająca zarządzaniu aplikacjami mobilnymi).

## <a name="next-steps"></a>Następne kroki

### <a name="managed-devices"></a>Urządzenia zarządzane

- Dowiedz się, jak używać konfiguracji aplikacji na urządzeniach z systemem iOS.  Zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem iOS](app-configuration-policies-use-ios.md).
- Dowiedz się, jak używać konfiguracji aplikacji na urządzeniach z systemem Android.  Zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem Android](app-configuration-policies-use-android.md).

### <a name="managed-apps"></a>Aplikacje zarządzane

- Dowiedz się, jak używać konfiguracji aplikacji z zarządzanymi aplikacjami. Zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych aplikacji bez rejestracji urządzeń](app-configuration-policies-managed-app.md).
