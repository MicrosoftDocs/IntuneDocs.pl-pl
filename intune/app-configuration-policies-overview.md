---
title: "Zasady konfiguracji aplikacji usługi Intune | Microsoft Docs"
titlesuffix: Azure portal
description: "Dowiedz się, jak używać zasad konfiguracji aplikacji usługi Intune."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 406d0faa1e03a41d20c1b584d2d37f9810ddbf32
ms.sourcegitcommit: ce35790090ebe768d5f75c108e8d5934fd19c8c7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/09/2017
---
# <a name="app-configuration-policies-for-intune"></a>Zasady konfiguracji aplikacji usługi Intune

Zasady konfiguracji aplikacji w usłudze Microsoft Intune umożliwiają określanie ustawień podczas uruchamiania aplikacji dla systemu iOS lub Android. Aplikacja może na przykład wymagać, aby użytkownicy określili:

- Niestandardowy numer portu
- Ustawienia języka
- Ustawienia zabezpieczeń
- Ustawienia oznaczeń marki, takich jak logo firmy

Nieprawidłowe określenie tych ustawień przez użytkowników może zwiększyć obciążenie działu pomocy technicznej i spowolnić wdrażanie technologii nowych aplikacji.

Zasady konfiguracji aplikacji mogą pomóc wyeliminować te problemy, umożliwiając przypisanie tych ustawień do użytkowników w zasadach, zanim uruchomią oni aplikację. Ustawienia są następnie określane automatycznie, a użytkownicy nie muszą podejmować żadnej akcji.

Tych zasad nie można przypisywać bezpośrednio do użytkowników i urządzeń. W zamian należy skojarzyć je z aplikacją, a następnie przypisać tę aplikację. Ustawienia zasad są stosowane zawsze, gdy aplikacja ich szuka (zazwyczaj podczas pierwszego uruchomienia).

Dostępne są dwie opcje używania konfiguracji aplikacji z usługą Intune:
 - **Zarządzane urządzenia**  
   Urządzenie jest zarządzane przez usługę Intune działającą jako dostawca rozwiązania do zarządzania urządzeniami przenośnymi (MDM).
 - **Zarządzane aplikacje**  
   Zarządzanie aplikacją odbywa się bez rejestracji urządzenia.

## <a name="apps-that-support-app-configuration"></a>Aplikacje obsługujące konfigurację aplikacji

Można używać zasad konfiguracji aplikacji w przypadku aplikacji, które je obsługują. Aby można było używać konfiguracji aplikacji w usłudze Intune, aplikacje muszą być napisane tak, aby obsługiwały korzystanie z konfiguracji aplikacji. Aby uzyskać więcej informacji, skontaktuj się z dostawcą aplikacji.

Aplikacje biznesowe można przygotować, włączając do aplikacji zestaw SDK aplikacji usługi Intune lub opakowując opracowaną aplikację. Korzystając z zestawu SDK aplikacji usługi Intune, dostępnego dla systemów iOS i Android, możesz obsługiwać zasady ochrony aplikacji usługi Intune w swojej aplikacji. Położono w nim nacisk na minimalizację liczby zmian kodu wymaganych od dewelopera aplikacji. Aby uzyskać więcej informacji, zobacz [Omówienie zestawu SDK aplikacji usługi Intune](app-sdk.md).

## <a name="graph-api-support-for-app-configuration"></a>Obsługa interfejsu API programu Graph w konfiguracji aplikacji

W celu wykonywania zadań konfiguracji aplikacji można używać interfejsu API programu Graph. Aby uzyskać więcej informacji, zobacz [Graph API Reference MAM Targeted Config](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create) (Dokumentacja interfejsu API programu Graph — konfiguracja podlegająca zarządzaniu aplikacjami mobilnymi).

## <a name="next-steps"></a>Następne kroki

### <a name="managed-devices"></a>Urządzenia zarządzane

 - Dowiedz się, jak używać konfiguracji aplikacji na urządzeniach z systemem iOS.  Zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem iOS](app-configuration-policies-use-ios.md).
 - Dowiedz się, jak używać konfiguracji aplikacji na urządzeniach z systemem Android.  Zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych urządzeń z systemem Android](app-configuration-policies-use-android.md).

### <a name="managed-apps"></a>Aplikacje zarządzane

 - Dowiedz się, jak używać konfiguracji aplikacji z zarządzanymi aplikacjami. Zobacz [Dodawanie zasad konfiguracji aplikacji dla zarządzanych aplikacji bez rejestracji urządzeń](app-configuration-policies-managed-app.md).