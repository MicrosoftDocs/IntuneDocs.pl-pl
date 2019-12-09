---
title: Co to jest zarządzanie aplikacjami w usłudze Microsoft Intune?
titleSuffix: ''
description: Dowiedz się więcej o możliwościach zarządzania aplikacjami klienckimi według platformy w usłudze Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 09b4cfad0490f35a85e4c72b937b2ba5c0472030
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/27/2019
ms.locfileid: "74564361"
---
# <a name="what-is-microsoft-intune-app-management"></a>Co to jest zarządzanie aplikacjami w usłudze Microsoft Intune?


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Jako administrator informatyczny możesz używać usługi Microsoft Intune do zarządzania aplikacjami klienckimi używanymi przez pracowników firmy. Ta funkcja jest dodatkiem do funkcji zarządzania urządzeniami oraz ochrony danych. Jednym z priorytetów administratora jest zapewnienie, że użytkownicy końcowi mają dostęp do aplikacji, których potrzebują do pracy. Osiągnięcie tego celu może być trudne, ponieważ:
- Istnieje szeroka gama platform urządzeń i typów aplikacji.
- Konieczne może okazać się zarządzanie aplikacjami zarówno na urządzeniach firmowych, jak i na osobistych urządzeniach użytkowników.
- Musisz mieć pewność, że sieć i dane pozostaną bezpieczne.

Dodatkowo możesz przypisywać aplikacje na urządzeniach niezarejestrowanych w usłudze Intune i zarządzać nimi.

## <a name="mobile-application-management-mam-basics"></a>Podstawowe informacje dotyczące zarządzania aplikacjami mobilnymi (MAM)

[Zarządzanie aplikacjami mobilnymi (MAM) usługi Intune](app-lifecycle.md) obejmuje zestaw funkcji zarządzania usługi Intune, które umożliwiają publikowanie, wypychanie, konfigurowanie, zabezpieczanie, monitorowanie i aktualizowanie aplikacji mobilnych dla użytkowników.

Zarządzanie aplikacjami mobilnymi umożliwia zarządzanie danymi organizacji oraz ich ochronę w ramach aplikacji. **Zarządzanie aplikacjami mobilnymi bez rejestracji** (MAM-WE) umożliwia zarządzanie aplikacją służbową, która zawiera dane poufne, z prawie każdego [urządzenia](app-management.md#app-management-capabilities-by-platform) — w tym z urządzenia osobistego w scenariuszach **BYOD** (przynieś własne urządzenie). Zarządzanie aplikacjami mobilnymi usługi Intune można stosować do wielu aplikacji użytkowych, takich jak aplikacje pakietu Microsoft Office. Zobacz oficjalną listę [aplikacji chronionych przez usługę Microsoft Intune](apps-supported-intune-apps.md) dostępnych do użytku publicznego.

Zarządzanie aplikacjami mobilnymi usługi Intune obsługuje dwie konfiguracje:
- **Zarządzanie urządzeniami przenośnymi i zarządzanie aplikacjami mobilnymi w usłudze Intune**: Administratorzy IT mogą zarządzać aplikacjami korzystającymi z zasad zarządzania aplikacjami mobilnymi i ochrony aplikacji tylko na urządzeniach zarejestrowanych w usłudze zarządzania urządzeniami przenośnymi (MDM) usługi Intune. Aby zarządzać aplikacjami przy użyciu konfiguracji MDM + MAM, klienci powinni używać konsoli usługi Intune w witrynie Azure Portal pod adresem https://portal.azure.com.
- **Zarządzanie aplikacjami mobilnymi bez rejestracji urządzenia**: zarządzanie aplikacjami mobilnymi bez rejestracji urządzeń (MAM-WE) umożliwia administratorom IT zarządzanie aplikacjami za pomocą zasad zarządzania aplikacjami mobilnymi i ochrony aplikacji na urządzeniach, które nie zostały zarejestrowane w usłudze Intune MDM. Oznacza to, że aplikacjami można zarządzać przy użyciu usługi Intune na urządzeniach zarejestrowanych u dostawców EMM innych firm. Aby zarządzać aplikacjami przy użyciu konfiguracji MAM-WE, klienci powinni używać konsoli usługi Intune w witrynie Azure Portal pod adresem https://portal.azure.com. Aplikacjami można również zarządzać przy użyciu usługi Intune na urządzeniach zarejestrowanych u dostawców usługi Enterprise Mobility Management (EMM) innych firm lub w ogóle niezarejestrowanych w usłudze MDM. Aby uzyskać więcej informacji dotyczących modelu BYOD i pakietu EMS firmy Microsoft, zobacz [Podejmowanie kluczowych decyzji technologicznych dotyczących włączania modelu BYOD za pomocą pakietu Microsoft Enterprise Mobility + Security](../fundamentals/byod-technology-decisions.md).

## <a name="app-management-capabilities-by-platform"></a>Możliwości zarządzania aplikacjami według platformy

Usługa Intune oferuje szeroką gamę możliwości, które pomogą Ci uzyskać dostęp do potrzebnych aplikacji na urządzeniach, na których chcesz je uruchamiać. Poniższa tabela zawiera podsumowanie możliwości dotyczących zarządzania aplikacjami.

|  | Android/Android Enterprise | iOS | macOS | Windows 10 | Windows Phone 8,1 |
|-------------------------------------------------------------------------------------|---------|-----|-------|------------|-------------------|
| Dodawanie aplikacji i przypisywanie ich do urządzeń i użytkowników | Tak | Tak | Tak | Tak | Tak |
| Przypisywanie aplikacji do urządzeń, które nie zostały zarejestrowane za pomocą usługi Intune | Tak | Tak | Nie | Nie | Nie |
| Użycie zasad konfiguracji aplikacji do sterowania zachowaniem aplikacji podczas uruchamiania | Tak | Tak | Nie | Nie | Nie |
| Użycie zasad aprowizowania aplikacji mobilnych do odnowienia wygasłych aplikacji | Nie | Tak | Nie | Nie | Nie |
| Ochrona danych firmy w aplikacjach z zasadami ochrony aplikacji | Tak | Tak | Nie | Nie <sup>1</sup> | Nie |
| Usuwanie jedynie danych firmowych z zainstalowanej aplikacji (Selektywne czyszczenie aplikacji) | Tak | Tak | Nie | Tak | Tak |
| Monitorowanie przypisań aplikacji | Tak | Tak | Tak | Tak | Tak |
| Przypisywanie i śledzenie aplikacji nabytych w ramach zakupów zbiorczych w sklepie z aplikacjami | Nie | Nie | Nie | Tak | Nie |
| Obowiązkowe instalowanie aplikacji na urządzeniach (wymagane) <sup>2</sup> | Tak | Tak | Tak | Tak | Tak |
| Opcjonalna instalacja na urządzeniach z Portalu firmy (dostępna instalacja) | Tak <sup>3</sup> | Tak | Tak | Tak | Tak |
| Instalowanie skrótu do aplikacji w Internecie (link internetowy) | Tak <sup>4</sup> | Tak | Tak | Tak | Tak |
| Aplikacje wewnętrzne (biznesowe) | Tak | Tak | Tak | Tak | Nie |
| Aplikacje ze sklepu | Tak | Tak | Nie | Tak | Tak |
| Aktualizowanie aplikacji | Tak | Tak | Nie | Tak | Tak |

<sup>1</sup> Rozważ zastosowanie funkcji [Windows Information Protection](../protect/windows-information-protection-configure.md) do ochrony aplikacji na urządzeniach z systemem Windows 10.<br>
<sup>2</sup>Dotyczy urządzeń zarządzanych tylko przez usługę Intune.<br>
<sup>3</sup> Usługa Intune obsługuje dostępne aplikacje z zarządzanego sklepu Google Play na urządzeniach z systemem Android Enterprise.<br>
<sup>4</sup> Usługa Intune nie umożliwia instalacji skrótu do aplikacji jako linku sieci Web na standardowych urządzeniach z systemem Android Enterprise. Oferowana jest jednak obsługa linku sieci Web dla [dedykowanych urządzeń z wieloma aplikacjami z systemem Android Enterprise](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings). 


## <a name="get-started"></a>Wprowadzenie

Większość informacji powiązanych z aplikacjami można znaleźć w obciążeniu **Aplikacje**, do którego dostęp można uzyskać w następujący sposób:

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Wybierz pozycję **Aplikacje**.

    ![Okienko obciążenia Aplikacje](./media/app-management/apps-workload.png)

W następnych czterech sekcjach opisano opcje dostępne w okienku **Aplikacje**.

### <a name="manage"></a>Zarządzanie programem Endpoint Protection usługi
- **Aplikacje**: wybierz tę opcję, aby dodawać, wyświetlać, przypisywać i monitorować aplikacje używane przez pracowników. Aby uzyskać więcej informacji, zobacz:
  - [Dodawanie aplikacji](apps-add.md).
  - [Przypisywanie aplikacji](apps-deploy.md).
  - [Monitorowanie aplikacji](apps-monitor.md).
- **Zasady konfigurowania aplikacji**: wybierz tę opcję, aby określać wartości ustawień, które mogą być wymagane, jeśli użytkownik uruchamia aplikację. Aby uzyskać więcej informacji, zobacz:
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
- **Odnalezione aplikacje**: wyświetlanie aplikacji, które zostały przypisane przez usługę Intune lub zainstalowane na urządzeniu. Aby uzyskać więcej informacji, zobacz [Intune discovered apps](app-discovered-apps.md) (Aplikacje odnalezione przez usługę Intune).
- **Stan instalacji aplikacji**: wyświetlanie stanu utworzonego przez siebie przypisania aplikacji. Aby uzyskać więcej informacji, zobacz [Monitorowanie informacji o aplikacji i przypisań z użyciem usługi Microsoft Intune](apps-monitor.md#device-and-user-status-graphs).
- **Stan ochrony aplikacji**: wyświetlanie stanu zasad ochrony aplikacji dla wybranego użytkownika.
- **Dzienniki inspekcji**: wyświetlanie działań wszystkich administratorów IT związanych z aplikacją usługi Intune.

Aby uzyskać więcej informacji na temat tej sekcji, zobacz [Monitorowanie aplikacji](apps-monitor.md).

### <a name="set-up"></a>Konfiguruj
- **Tokeny programu VPP dla systemu iOS**: stosowanie i wyświetlanie licencji Volume Purchase Program (VPP) dla systemu iOS. Aby uzyskać więcej informacji, zobacz:
  - [Aplikacje systemu iOS nabyte w ramach zakupów zbiorczych](vpp-apps-ios.md)
- **Certyfikat przedsiębiorstwa systemu Windows**: stosowanie lub wyświetlanie stanu certyfikatu podpisywania kodu używanego do dystrybuowania aplikacji biznesowych na zarządzanych urządzeniach z systemem Windows.
- **Certyfikat firmy Symantec systemu Windows**: stosowanie lub wyświetlanie stanu certyfikatu podpisywania kodu firmy Symantec potrzebnego do rozpowszechniania plików appx XAP i WP8.x na urządzeniach z systemem Windows 10 Mobile.
- **Microsoft Store dla Firm**: konfigurowanie integracji ze sklepem Microsoft Store dla Firm. Po wykonaniu tej czynności można synchronizować zakupione aplikacje z usługą Intune, przypisywać je i śledzić użycie licencji. Aby uzyskać więcej informacji, zobacz:
  - [Aplikacje nabyte w ramach zakupów zbiorczych w sklepie Microsoft Store dla Firm](windows-store-for-business.md).
- **Klucze ładowania bezpośredniego systemu Windows**: dodawanie klucza ładowania bezpośredniego systemu Windows, który może służyć do bezpośredniej instalacji aplikacji na urządzeniach bez konieczności publikowania aplikacji i pobierania jej ze sklepu Windows Store. Aby uzyskać więcej informacji, zobacz:
  - [Ładowanie bezpośrednie aplikacji systemu Windows](app-sideload-windows.md).
- **Znakowanie Portalu firmy**: dostosowywanie Portalu firmy w celu nadania mu logo Twojej firmy. Aby uzyskać więcej informacji, zobacz:
  - [Konfiguracja portalu firmy](company-portal-app.md).
- **Kategorie aplikacji**: dodawanie, przypinanie i usuwanie nazw kategorii aplikacji.
- **Profil służbowy systemu Android**: zatwierdzanie i synchronizowanie aplikacji zatwierdzonych dla przedsiębiorstwa. Aby uzyskać więcej informacji, zobacz:
  - [Aplikacje profilu służbowego systemu Android](apps-add-android-for-work.md).

### <a name="help-and-support"></a>Pomoc i obsługa techniczna
- **Pomoc i obsługa techniczna**: rozwiązywanie problemów, wnioskowanie o pomoc techniczną lub wyświetlanie stanu usługi Intune. Aby uzyskać więcej informacji, zobacz:
  - [Rozwiązywanie problemów](../fundamentals/help-desk-operators.md).

## <a name="next-steps"></a>Następne kroki

- [Dodawanie aplikacji do usługi Microsoft Intune](apps-add.md)
