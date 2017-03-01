---
title: "Co to jest zarządzanie aplikacjami | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: z tego tematu nauczysz się podstaw zarządzania aplikacjami w usłudze Microsoft Intune"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: d3be47257556e8bfa331cebf68baa43524690d1a
ms.lasthandoff: 02/16/2017


---

# <a name="what-is-microsoft-intune-app-management"></a>Co to jest zarządzanie aplikacjami w usłudze Microsoft Intune?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Do Twoich obowiązków jako administratora IT prawdopodobnie będzie należało zapewnienie użytkownikom końcowym dostępu do aplikacji, które są im niezbędne do pracy. Może to być trudne, ponieważ:
- Istnieje szeroka gama platform urządzeń i typów aplikacji.
- Może okazać się konieczne zarządzanie aplikacjami nie tylko na urządzeniach firmy, ale także na własnych urządzeniach użytkowników.
- Oprócz tego musisz zapewnić bezpieczeństwo sieci i danych. 

Na dodatek możesz też przypisywać aplikacje na urządzeniach niezarejestrowanych w usłudze Intune i zarządzać nimi.

Usługa Intune oferuje szeroką gamę możliwości, które pomogą Ci uzyskać dostęp do potrzebnych aplikacji na wybranych urządzeniach.

## <a name="app-management-capabilities-by-platform"></a>Możliwości zarządzania aplikacjami według platformy

||||||
|-|-|-|-|-|
|&nbsp; |Android|iOS|Windows Phone 8.1|Windows 10|
|Dodawanie aplikacji i przypisywanie ich do urządzeń i użytkowników|Tak|Tak|Tak|Tak|
|Przypisywanie aplikacji do urządzeń, które nie zostały zarejestrowane za pomocą usługi Intune|Tak|Tak|Nie|Nie|
|Użycie zasad konfiguracji aplikacji do sterowania zachowaniem aplikacji podczas uruchamiania|Nie|Tak|Nie|Nie|
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

<sup>1</sup> Rozważ zastosowanie funkcji [Windows Information Protection](/intune-azure/configure-devices/how-to-configure-windows-information-protection) do ochrony aplikacji na urządzeniach z systemem Windows 10.

<sup>2</sup>Dotyczy urządzeń zarządzanych tylko przez usługę Intune.


## <a name="how-to-get-started"></a>Wprowadzenie

Większość elementów powiązanych z aplikacjami można znaleźć w obciążeniu **Aplikacje mobilne**, do którego dostęp można uzyskać w następujący sposób:

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Zarządzaj aplikacjami**.

    ![Obciążenie Aplikacje mobilne](./media/apps-workload.png)

### <a name="manage"></a>Zarządzanie programem Endpoint Protection usługi
- **Aplikacje** — to miejsce, w którym będziesz dodawać, przypisywać i monitorować większość swoich aplikacji. 
    - [Dodawanie aplikacji](add-apps.md)
    - [Przypisywanie aplikacji](deploy-apps.md)
    - [Monitorowanie aplikacji](monitor-apps.md)
- **Licencjonowane aplikacje** — przeglądanie, wdrażanie i monitorowanie aplikacji nabytych w ramach zakupów zbiorczych w sklepach z aplikacjami.
    - [Aplikacje nabyte w ramach zakupów zbiorczych w Sklepie Windows dla firm](wsfb-apps.md)
- **Zasady konfigurowania aplikacji** — zasady konfiguracji aplikacji umożliwiają określanie ustawień, które mogą być wymagane, gdy użytkownik uruchamia aplikację. Aby uzyskać szczegółowe informacje, zobacz:
    - [Zasady konfigurowania aplikacji](app-configuration-policies.md)
- **Zasady ochrony aplikacji** — umożliwia skojarzenie ustawień z aplikacją w taki sposób, aby umożliwić ochronę używanych przez nią danych firmy. Na przykład można ograniczyć możliwości komunikowania się aplikacji z innymi aplikacjami lub wymagać od użytkownika wprowadzania numeru PIN umożliwiającego dostęp do aplikacji firmowej.
    - [Zasady ochrony aplikacji](app-protection-policies.md)
- **Selektywne czyszczenie aplikacji** — usunięcie tylko danych firmowych z wybranego urządzenia.
    - [Selektywne czyszczenie danych](app-selective-wipe.md)

### <a name="monitor"></a>Monitor
- **Wykryte aplikacje** — pokazuje wszystkie aplikacje, które zostały przypisane przez usługę Intune i zainstalowane na urządzeniu.
- **Stan instalacji aplikacji** — pokazuje stan utworzonego przez Ciebie przypisania aplikacji.
- **Stan użytkownika ochrony aplikacji** — pokazuje stan zasad ochrony aplikacji dla wybranego przez Ciebie użytkownika.

Aby uzyskać szczegółowe informacje, zobacz sekcję [Monitorowanie aplikacji](monitor-apps.md)

### <a name="setup"></a>Setup
<!--- **iOS VPP Tokens**
    - [iOS volume-purchased apps](ios-vpp-apps.md) --->
- **Sklep Windows dla firm** — skonfiguruj integrację ze Sklepem Windows dla firm. Po wykonaniu tej czynności można zsynchronizować zakupione aplikacje z usługą Intune, przypisywać je i śledzić wykorzystanie licencji. 
    - [Aplikacje nabyte w ramach zakupów zbiorczych w Sklepie Windows dla firm](wsfb-apps.md)
- **Znakowanie portalu firmy** — dostosowywanie portalu firmy w celu nadania mu logo Twojej firmy. 
    - [Konfiguracja portalu firmy](company-portal-app.md)

