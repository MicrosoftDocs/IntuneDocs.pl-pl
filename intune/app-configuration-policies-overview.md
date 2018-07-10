---
title: Zasady konfiguracji aplikacji usługi Microsoft Intune
titlesuffix: ''
description: Dowiedz się, jak używać zasad konfiguracji aplikacji na urządzeniach z systemem iOS lub Android w usłudze Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 06/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6c04d2d8fa2e302c4d11760d3660a0a67e8b3695
ms.sourcegitcommit: b47fad133ef8ef1eb65484463431c6c53f6a638a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/11/2018
ms.locfileid: "35291550"
---
# <a name="app-configuration-policies-for-microsoft-intune"></a>Zasady konfiguracji aplikacji usługi Microsoft Intune

Zasady konfiguracji aplikacji w usłudze Microsoft Intune umożliwiają określenie ustawień konfiguracji dla aplikacji systemu iOS lub Android. Dzięki tym ustawieniom konfiguracji aplikację można dostosować. Zasad konfiguracji nie można przypisywać bezpośrednio do użytkowników i urządzeń. Zamiast tego należy skojarzyć je z aplikacją, a następnie przypisać tę aplikację. Ustawienia zasad konfiguracji są stosowane, gdy aplikacja je wyszukuje (zazwyczaj podczas pierwszego uruchomienia).

Zasady konfiguracji aplikacji możesz przypisać do grupy użytkowników i urządzeń za pomocą kombinacji dołączania i wykluczania przypisań. Po dodaniu zasad konfiguracji aplikacji możesz ustawić przypisania zasad konfiguracji aplikacji. Po ustawieniu przypisań dla zasad możesz dołączać i wykluczać grupy użytkowników, dla których zasady będą stosowane. Po wybraniu dołączenia co najmniej jednej grupy możesz wybrać określone grupy do dołączenia lub wybrać wbudowane grupy. Wbudowane grupy to **Wszyscy użytkownicy**, **Wszystkie urządzenia** oraz **Wszyscy użytkownicy i wszystkie urządzenia**.

Aplikacja może wymagać na przykład określenia następujących szczegółów:

- Niestandardowy numer portu
- Ustawienia języka
- Ustawienia zabezpieczeń
- Ustawienia oznaczeń marki, takich jak logo firmy

Nieprawidłowe określenie tych ustawień przez użytkowników może zwiększyć obciążenie działu pomocy technicznej i spowolnić wdrażanie technologii nowych aplikacji.

Zasady konfiguracji aplikacji mogą pomóc wyeliminować te problemy, umożliwiając przypisanie tych ustawień do użytkowników w zasadach, zanim uruchomią oni aplikację. Ustawienia są następnie określane automatycznie, a użytkownicy nie muszą podejmować żadnej akcji.

Ustawienia konfiguracji są używane za każdym razem, gdy aplikacja je wyszukuje. Zazwyczaj aplikacja wyszukuje ustawienia konfiguracji podczas pierwszego uruchomienia przez użytkownika.

Dostępne są dwie opcje używania konfiguracji aplikacji z usługą Intune:
 - **Urządzenia zarządzane** — urządzenie jest zarządzane przez usługę Intune działającą jako dostawca rozwiązania do zarządzania urządzeniami przenośnymi (MDM).
 - **Aplikacje zarządzane** — zarządzanie aplikacją odbywa się bez rejestracji urządzenia.

## <a name="apps-that-support-app-configuration"></a>Aplikacje obsługujące konfigurację aplikacji

Można używać zasad konfiguracji aplikacji w przypadku aplikacji, które je obsługują. Aby można było używać konfiguracji aplikacji w usłudze Intune, aplikacje muszą być napisane tak, aby obsługiwały korzystanie z konfiguracji aplikacji. Aby uzyskać więcej informacji, skontaktuj się z dostawcą aplikacji.

Aplikacje biznesowe można przygotować, włączając do aplikacji zestaw SDK aplikacji usługi Intune lub opakowując opracowaną aplikację. Korzystając z zestawu SDK aplikacji usługi Intune, dostępnego dla systemów iOS i Android, możesz obsługiwać zasady konfiguracji aplikacji usługi Intune w swojej aplikacji. Położono w nim nacisk na minimalizację liczby zmian kodu wymaganych od dewelopera aplikacji. Aby uzyskać więcej informacji, zobacz [Omówienie zestawu SDK aplikacji usługi Intune](app-sdk.md).

## <a name="graph-api-support-for-app-configuration"></a>Obsługa interfejsu API programu Graph w konfiguracji aplikacji

W celu wykonywania zadań konfiguracji aplikacji można używać interfejsu API programu Graph. Aby uzyskać więcej informacji, zobacz [Graph API Reference MAM Targeted Config](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create) (Dokumentacja interfejsu API programu Graph — konfiguracja podlegająca zarządzaniu aplikacjami mobilnymi).

## <a name="next-steps"></a>Następne kroki

### <a name="managed-devices"></a>Urządzenia zarządzane

 - Dowiedz się, jak używać konfiguracji aplikacji na urządzeniach z systemem iOS.  Zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem iOS](app-configuration-policies-use-ios.md).
 - Dowiedz się, jak używać konfiguracji aplikacji na urządzeniach z systemem Android.  Zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem Android](app-configuration-policies-use-android.md).

### <a name="managed-apps"></a>Aplikacje zarządzane

 - Dowiedz się, jak używać konfiguracji aplikacji z zarządzanymi aplikacjami. Zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych aplikacji bez rejestracji urządzeń](app-configuration-policies-managed-app.md).
