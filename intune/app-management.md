---
title: Co to jest zarządzanie aplikacjami w usłudze Microsoft Intune?
titlesuffix: ''
description: Poznaj podstawy zarządzania aplikacjami w usłudze Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/20/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure; get-started
ms.openlocfilehash: 9529560fca1fcd30fc479c0eac8bd7bc967fa952
ms.sourcegitcommit: 23adbc50191f68c4b66ea845a044da19c659ac84
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2018
ms.locfileid: "45562854"
---
# <a name="what-is-microsoft-intune-app-management"></a>Co to jest zarządzanie aplikacjami w usłudze Microsoft Intune?


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Jako administrator informatyczny możesz używać usługi Microsoft Intune do zarządzania aplikacjami klienckimi używanymi przez pracowników firmy. Ta funkcja jest dodatkiem do funkcji zarządzania urządzeniami oraz ochrony danych. Jednym z priorytetów administratora jest zapewnienie, że użytkownicy końcowi mają dostęp do aplikacji, których potrzebują do pracy. Osiągnięcie tego celu może być trudne, ponieważ:
- Istnieje szeroka gama platform urządzeń i typów aplikacji.
- Konieczne może okazać się zarządzanie aplikacjami zarówno na urządzeniach firmowych, jak i na osobistych urządzeniach użytkowników.
- Musisz mieć pewność, że sieć i dane pozostaną bezpieczne.

Dodatkowo możesz przypisywać aplikacje na urządzeniach niezarejestrowanych w usłudze Intune i zarządzać nimi.

Usługa Intune oferuje szeroką gamę możliwości, które pomogą Ci uzyskać dostęp do potrzebnych aplikacji na urządzeniach, na których chcesz je uruchamiać. Poniższa tabela zawiera podsumowanie możliwości dotyczących zarządzania aplikacjami: 

## <a name="app-management-capabilities-by-platform"></a>Możliwości zarządzania aplikacjami według platformy

|  | Android | iOS | macOS | Windows 10 | Windows Phone 8,1 |
|-------------------------------------------------------------------------------------|---------|-----|-------|------------|-------------------|
| Dodawanie aplikacji i przypisywanie ich do urządzeń i użytkowników | Tak | Tak | Tak | Tak | Tak |
| Przypisywanie aplikacji do urządzeń, które nie zostały zarejestrowane za pomocą usługi Intune | Tak | Tak | Nie | Nie | Nie |
| Użycie zasad konfiguracji aplikacji do sterowania zachowaniem aplikacji podczas uruchamiania | Nie | Tak | Nie | Nie | Nie |
| Użycie zasad aprowizowania aplikacji mobilnych do odnowienia wygasłych aplikacji | Nie | Tak | Nie | Nie | Nie |
| Ochrona danych firmy w aplikacjach z zasadami ochrony aplikacji | Tak | Tak | Nie | Nie1 | Nie |
| Usuwanie jedynie danych firmowych z zainstalowanej aplikacji (Selektywne czyszczenie aplikacji) | Tak | Tak | Nie | Tak | Tak |
| Monitorowanie przypisań aplikacji | Tak | Tak | Tak | Tak | Tak |
| Przypisywanie i śledzenie aplikacji nabytych w ramach zakupów zbiorczych w sklepie z aplikacjami | Nie | Nie | Nie | Tak | Nie |
| Obowiązkowe instalowanie aplikacji na urządzeniach (wymagane)2 | Tak | Tak | Tak | Tak | Tak |
| Opcjonalna instalacja na urządzeniach z Portalu firmy (dostępna instalacja) | Tak | Tak | Tak | Tak | Tak |
| Instalowanie skrótu do aplikacji w Internecie (link internetowy) | Tak | Tak | Tak | Tak | Tak |
| Aplikacje wewnętrzne (biznesowe) | Tak | Tak | Tak | Tak | Nie |
| Aplikacje ze sklepu | Tak | Tak | Nie | Tak | Tak |
| Aktualizowanie aplikacji | Tak | Tak | Nie | Tak | Tak |

<sup>1</sup> Rozważ zastosowanie funkcji [Windows Information Protection](windows-information-protection-configure.md) do ochrony aplikacji na urządzeniach z systemem Windows 10.

<sup>2</sup>Dotyczy urządzeń zarządzanych tylko przez usługę Intune.

## <a name="get-started"></a>Wprowadzenie

Większość informacji powiązanych z aplikacjami można znaleźć w obciążeniu **Aplikacje klienckie**, do którego dostęp można uzyskać w następujący sposób:

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**.  
    Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Microsoft Intune** wybierz pozycję **Aplikacje klienckie**.

    ![Okienko obciążenia Aplikacje klienckie](./media/apps-workload.png)

W następnych czterech sekcjach opisano opcje dostępne w okienku **Aplikacje klienckie**.

### <a name="manage"></a>Zarządzanie programem Endpoint Protection usługi
- **Aplikacje**: wybierz tę opcję, aby dodawać, wyświetlać, przypisywać i monitorować aplikacje używane przez pracowników. Aby uzyskać więcej informacji, zobacz:
    - [Dodawanie aplikacji](apps-add.md).
    - [Przypisywanie aplikacji](apps-deploy.md).
    - [Monitorowanie aplikacji](apps-monitor.md).
- **Zasady konfiguracji aplikacji mobilnych**: wybierz tę opcję, aby określać wartości ustawień, które mogą być wymagane, jeśli użytkownik uruchamia aplikację. Aby uzyskać więcej informacji, zobacz:
    - [Zasady konfiguracji aplikacji usługi Intune](app-configuration-policies-overview.md).
        - [Zasady konfiguracji aplikacji systemu iOS](app-configuration-policies-use-ios.md).
        - [Zasady konfiguracji aplikacji systemu Android](app-configuration-policies-use-android.md).
- **Zasady ochrony aplikacji**: wybierz tę opcję, aby skojarzyć ustawienia z aplikacją i ułatwić ochronę używanych przez nią danych firmy. Można na przykład ograniczyć możliwości komunikowania się aplikacji z innymi aplikacjami lub wymagać od użytkownika wprowadzania numeru PIN umożliwiającego dostęp do aplikacji firmowej. Aby uzyskać więcej informacji, zobacz:
    - [Zasady ochrony aplikacji](app-protection-policies.md).
- **Selektywne czyszczenie aplikacji**: wybierz tę opcję, aby usunąć tylko dane firmowe z wybranego urządzenia użytkownika. Aby uzyskać więcej informacji, zobacz:
    - [Selektywne czyszczenie aplikacji](apps-selective-wipe.md).
- **Profile aprowizacji aplikacji systemu iOS**: aplikacje dla systemu iOS obejmują profil aprowizowania i kod podpisany przy użyciu certyfikatu. Po wygaśnięciu certyfikatu aplikacji nie będzie można już uruchomić. Usługa Intune udostępnia narzędzia umożliwiające aktywne przypisywanie nowych zasad profilu aprowizowania do urządzeń, na których znajdują się aplikacje bliskie wygaśnięcia. Aby uzyskać więcej informacji, zobacz:
    - [Profile aprowizowania aplikacji dla systemu iOS](app-provisioning-profile-ios.md).

Aby uzyskać więcej informacji na temat tej sekcji, zobacz [Zarządzanie aplikacjami](app-management.md).

### <a name="monitor"></a>Monitor
- **Licencje aplikacji**: przeglądanie, przypisywanie i monitorowanie aplikacji nabytych w ramach zakupów zbiorczych w sklepach z aplikacjami. Aby uzyskać więcej informacji, zobacz:
    - [Aplikacje dla systemu iOS zakupione w ramach programu zakupów zbiorczych (VPP)](vpp-apps-ios.md).
    - [Aplikacje nabyte w ramach zakupów zbiorczych w sklepie Microsoft Store dla Firm](windows-store-for-business.md).
- **Odnalezione aplikacje**: wyświetlanie wszystkich aplikacji, które zostały przypisane przez usługę Intune i zainstalowane na urządzeniu. Aby uzyskać więcej informacji, zobacz [Monitorowanie informacji o aplikacji i przypisań z użyciem usługi Microsoft Intune](apps-monitor.md#device-and-user-status-graphs).
- **Stan instalacji aplikacji**: wyświetlanie stanu utworzonego przez siebie przypisania aplikacji. Aby uzyskać więcej informacji, zobacz [Monitorowanie informacji o aplikacji i przypisań z użyciem usługi Microsoft Intune](apps-monitor.md#device-and-user-status-graphs).
- **Stan ochrony aplikacji**: wyświetlanie stanu zasad ochrony aplikacji dla wybranego użytkownika.
- **Dzienniki inspekcji**: wyświetlanie działań wszystkich administratorów IT związane z aplikacją usługi Intune.

Aby uzyskać więcej informacji na temat tej sekcji, zobacz [Monitorowanie aplikacji](apps-monitor.md).

### <a name="set-up"></a>Konfigurowanie
- **Tokeny programu VPP dla systemu iOS**: stosowanie i wyświetlanie licencji Volume Purchase Program (VPP) dla systemu iOS. Aby uzyskać więcej informacji, zobacz:
    - [Aplikacje systemu iOS nabyte w ramach zakupów zbiorczych](vpp-apps-ios.md)
- **Certyfikat przedsiębiorstwa systemu Windows**: stosowanie lub wyświetlanie stanu certyfikatu podpisywania kodu używanego do dystrybuowania aplikacji biznesowych na zarządzanych urządzeniach z systemem Windows.
- **Certyfikat firmy Symantec systemu Windows**: stosowanie lub wyświetlanie stanu certyfikatu podpisywania kodu firmy Symantec potrzebnego do rozpowszechniania plików appx XAP i WP8.x na urządzeniach z systemem Windows 10 Mobile.
- **Microsoft Store dla Firm**: konfigurowanie integracji ze sklepem Microsoft Store dla Firm. Po wykonaniu tej czynności można synchronizować zakupione aplikacje z usługą Intune, przypisywać je i śledzić użycie licencji. Aby uzyskać więcej informacji, zobacz:
    - [Aplikacje nabyte w ramach zakupów zbiorczych w sklepie Microsoft Store dla Firm](windows-store-for-business.md).
- **Klucze ładowania bezpośredniego systemu Windows**: dodawanie klucza ładowania bezpośredniego systemu Windows, który może służyć do bezpośredniej instalacji aplikacji na urządzeniach bez konieczności publikowania aplikacji i pobierania jej ze Sklepu Windows. Aby uzyskać więcej informacji, zobacz:
    - [Ładowanie bezpośrednie aplikacji systemu Windows](app-sideload-windows.md).
- **Znakowanie portalu firmy**: dostosowywanie portalu firmy w celu nadania mu logo Twojej firmy. Aby uzyskać więcej informacji, zobacz:
    - [Konfiguracja portalu firmy](company-portal-app.md).
- **Kategorie aplikacji**: dodawanie, przypinanie i usuwanie nazw kategorii aplikacji.
- **Profil służbowy systemu Android**: zatwierdzanie i synchronizowanie aplikacji zatwierdzonych dla przedsiębiorstwa. Aby uzyskać więcej informacji, zobacz:
    - [Aplikacje profilu służbowego systemu Android](apps-add-android-for-work.md).

### <a name="help-and-support"></a>Pomoc i obsługa techniczna
- **Pomoc i obsługa techniczna**: rozwiązywanie problemów, wnioskowanie o pomoc techniczną lub wyświetlanie stanu usługi Intune. Aby uzyskać więcej informacji, zobacz:
    - [Rozwiązywanie problemów](help-desk-operators.md).

## <a name="next-steps"></a>Następne kroki

- [Dodawanie aplikacji do usługi Microsoft Intune](apps-add.md)
