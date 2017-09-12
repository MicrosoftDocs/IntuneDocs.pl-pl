---
title: "Co to jest zarządzanie aplikacjami"
titlesuffix: Azure portal
description: "Z tego tematu nauczysz się podstaw zarządzania aplikacjami w usłudze Microsoft Intune"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 616589e02ba3c499e73431889f5a849a16538f90
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2017
---
# <a name="what-is-microsoft-intune-app-management"></a>Co to jest zarządzanie aplikacjami w usłudze Microsoft Intune?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Do Twoich obowiązków jako administratora IT należy zapewnienie użytkownikom końcowym dostępu do aplikacji, które są im niezbędne do pracy. Może to być trudne, ponieważ:
- Istnieje szeroka gama platform urządzeń i typów aplikacji.
- Może okazać się konieczne zarządzanie aplikacjami na urządzeniach firmy i na własnych urządzeniach użytkowników.
- Musisz mieć pewność, że sieć i dane pozostaną bezpieczne.

Na dodatek możesz też przypisywać aplikacje na urządzeniach niezarejestrowanych w usłudze Intune i zarządzać nimi.

Usługa Intune oferuje szeroką gamę możliwości, które pomogą Ci uzyskać dostęp do potrzebnych aplikacji na wybranych urządzeniach.

## <a name="app-management-capabilities-by-platform"></a>Możliwości zarządzania aplikacjami według platformy

||||||
|-|-|-|-|-|
|&nbsp; |Android|iOS|Windows Phone 8.1|Windows 10|
|Dodawanie aplikacji i przypisywanie ich do urządzeń i użytkowników|Tak|Tak|Tak|Tak|
|Przypisywanie aplikacji do urządzeń, które nie zostały zarejestrowane za pomocą usługi Intune|Tak|Tak|Nie|Nie|
|Użycie zasad konfiguracji aplikacji do sterowania zachowaniem aplikacji podczas uruchamiania|Nie|Tak|Nie|Nie|
|Użycie zasad aprowizowania aplikacji mobilnych do odnowienia wygasłych aplikacji|Nie|Tak|Nie|Nie|
|Ochrona danych firmy w aplikacjach z zasadami ochrony aplikacji|Tak|Tak|Nie|Nie<sup>1</sup>|
|Usuwanie jedynie danych firmowych z zainstalowanej aplikacji (Selektywne czyszczenie aplikacji)|Tak|Tak|Tak|Tak|
|Monitorowanie przypisań aplikacji|Tak|Tak|Tak|Tak|
|Przypisywanie i śledzenie aplikacji nabytych w ramach zakupów zbiorczych w sklepie z aplikacjami|Nie|Nie|Nie|Tak|
|Obowiązkowe instalowanie aplikacji na urządzeniach (wymagane)<sup>2</sup>|Tak|Tak|Tak|Tak|
|Opcjonalna instalacja na urządzeniach z portalu firmy (dostępna instalacja)|Tak|Tak|Tak|Tak|
|Instalowanie skrótu do aplikacji w sieci Web (składnik Web Clip)|Tak|Tak|Tak|Tak|
|Aplikacje wewnętrzne (biznesowe)|Tak|Tak|Nie|Nie|
|Aplikacje ze sklepu|Tak|Tak|Tak|Tak|
|Aktualizowanie aplikacji|Tak|Tak|Tak|Tak|

<sup>1</sup> Rozważ zastosowanie funkcji [Windows Information Protection](windows-information-protection-configure.md) do ochrony aplikacji na urządzeniach z systemem Windows 10.

<sup>2</sup>Dotyczy urządzeń zarządzanych tylko przez usługę Intune.

## <a name="how-to-get-started"></a>Wprowadzenie

Większość elementów powiązanych z aplikacjami można znaleźć w obciążeniu **Aplikacje mobilne**, do którego dostęp można uzyskać w następujący sposób:

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz pozycję **Aplikacje mobilne**.

    ![Obciążenie Aplikacje mobilne](./media/apps-workload.png)

### <a name="manage"></a>Zarządzanie programem Endpoint Protection usługi
- **Aplikacje** — ten węzeł to miejsce, w którym będziesz dodawać, przypisywać i monitorować większość swoich aplikacji.
    - [Dodawanie aplikacji](apps-add.md)
    - [Przypisywanie aplikacji](apps-deploy.md)
    - [Monitorowanie aplikacji](apps-monitor.md)
- **Zasady konfigurowania aplikacji** — zasady konfigurowania aplikacji umożliwiają określanie ustawień, które mogą być wymagane, gdy użytkownik uruchamia aplikację.
    - [Zasady konfiguracji aplikacji systemu iOS](app-configuration-policies-use-ios.md)
    - [Zasady konfiguracji aplikacji systemu Android](app-configuration-policies-use-android.md)
- **Zasady ochrony aplikacji** — umożliwia skojarzenie ustawień z aplikacją w taki sposób, aby umożliwić ochronę używanych przez nią danych firmy. Na przykład można ograniczyć możliwości komunikowania się aplikacji z innymi aplikacjami lub wymagać od użytkownika wprowadzania numeru PIN umożliwiającego dostęp do aplikacji firmowej.
    - [Zasady ochrony aplikacji](app-protection-policies.md)
- **Selektywne czyszczenie aplikacji** — usunięcie tylko danych firmowych z wybranego urządzenia.
    - [Selektywne czyszczenie danych](apps-selective-wipe.md)
- **Profile aprowizacji systemu iOS** — aplikacje dla systemu iOS obejmują profil aprowizowania i kod podpisany przy użyciu certyfikatu. Po wygaśnięciu certyfikatu aplikacji nie będzie można już uruchomić. Usługa Intune udostępnia narzędzia umożliwiające aktywne przypisywanie nowych zasad profilu aprowizowania do urządzeń, na których znajdują się aplikacje bliskie wygaśnięcia.
    - [Profile aprowizowania aplikacji dla systemu iOS](app-provisioning-profile-ios.md)

### <a name="monitor"></a>Monitor
- **Licencjonowane aplikacje** — przeglądanie, przypisywanie i monitorowanie aplikacji nabytych w ramach zakupów zbiorczych w sklepach z aplikacjami.
    - [Aplikacje nabyte w ramach zakupów zbiorczych w Sklepie Microsoft dla Firm](windows-store-for-business.md)
- **Wykryte aplikacje** — pokazuje wszystkie aplikacje, które zostały przypisane przez usługę Intune i zainstalowane na urządzeniu.
- **Stan instalacji aplikacji** — pokazuje stan utworzonego przez Ciebie przypisania aplikacji.
- **Stan ochrony aplikacji** — pokazuje stan zasad ochrony aplikacji dla wybranego użytkownika.

Aby uzyskać szczegółowe informacje, zobacz sekcję [Monitorowanie aplikacji](apps-monitor.md)

### <a name="setup"></a>Setup
<!--- **iOS VPP Tokens**
    - [iOS volume-purchased apps](vpp-apps-ios.md) --->
- **Sklep Microsoft dla Firm** — umożliwia skonfigurowanie integracji ze Sklepem Microsoft dla Firm. Po wykonaniu tej czynności można zsynchronizować zakupione aplikacje z usługą Intune, przypisywać je i śledzić wykorzystanie licencji.
    - [Aplikacje nabyte w ramach zakupów zbiorczych w Sklepie Microsoft dla Firm](windows-store-for-business.md)
- **Znakowanie portalu firmy** — dostosowywanie portalu firmy w celu nadania mu logo Twojej firmy.
    - [Konfiguracja portalu firmy](company-portal-app.md)
