---
title: Łącznik Symantec w usłudze Microsoft Intune
titleSuffix: Microsoft Intune
description: Dowiedz się więcej na temat integracji usługi Intune z programem Symantec Endpoint Protection Mobile w celu kontrolowania dostępu urządzeń przenośnych do zasobów firmy.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/09/2017
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: df4ce3f6-a093-432c-ab86-7a83865e389e
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: be8fbb0bd96891eb3af3157deddfc325ebc5f2b9
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72508925"
---
# <a name="symantec-endpoint-protection-mobile-connector"></a>Łącznik Symantec Endpoint Protection Mobile

Dostęp urządzeń przenośnych do zasobów firmy można kontrolować z użyciem dostępu warunkowego opartego na ocenie ryzyka przeprowadzanej przez produkt Symantec Endpoint Protection Mobile (SEP Mobile). Jest to rozwiązanie chroniące przed zagrożeniami bezpieczeństwa urządzenia przenośne zintegrowane z usługą Microsoft Intune. Ryzyko jest oceniane na podstawie danych telemetrycznych zebranych z urządzeń z uruchomioną usługą SEP Mobile. Są to na przykład:

- Ochrona fizyczna

- Ochrona sieciowa

- Ochrona aplikacji

- Ochrona przed lukami w zabezpieczeniach

Możesz włączyć ocenę ryzyka SEP Mobile za pomocą zasad zgodności urządzeń usługi Intune, a następnie używać zasad dostępu warunkowego do zezwalania na dostęp do zasobów firmy lub blokowania go w oparciu o wykryte zagrożenia.

## <a name="how-do-intune-and-sep-mobile-help-protect-your-company-resources"></a>W jaki sposób usługa Intune i program SEP Mobile ułatwiają ochronę zasobów firmy?

Aplikacja SEP Mobile dla systemu Android lub iOS przechwytuje dane telemetryczne z systemu plików, stosu sieci oraz urządzenia i aplikacji (wszędzie, gdzie są dostępne), a następnie wysyła je do usługi Symantec w chmurze w celu dokonania oceny ryzyka dotyczącego urządzenia pod kątem zagrożeń mobilnych.

Zasady zgodności urządzeń w usłudze Intune zawierają regułę dotyczącą programu SEP Mobile, która jest oparta na ocenie ryzyka SEP Mobile. Gdy ta reguła jest włączona, usługa Intune ocenia zgodność urządzenia z zasadami, które zostały włączone.

Jeśli okaże się, że urządzenie nie jest zgodne, może zostać zablokowany dostęp do zasobów, takich jak usługa Exchange Online lub SharePoint Online. Użytkownicy zablokowanych urządzeń otrzymają wskazówki z aplikacji SEP Mobile dotyczące rozwiązania problemu i odzyskania dostępu do zasobów firmy.

Usługa Intune obsługuje dwa tryby integracji z programem SEP Mobile:

- **Konfiguracja podstawowa**, który jest trybem tylko do odczytu, umożliwiającym widoczność programu SEP Mobile dla urządzeń w usłudze Intune.

- **Pełna integracja**, który umożliwia programowi SEP Mobile raportowanie do usługi Intune ryzyka urządzeń i szczegółowych informacji dotyczących incydentów zabezpieczeń.

## <a name="sample-scenarios"></a>Przykładowe scenariusze

Poniżej przedstawiono kilka typowych scenariuszy:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kontrola dostępu oparta na zagrożeniach ze strony złośliwych aplikacji

Po wykryciu na urządzeniach złośliwego oprogramowania możesz zablokować na nich następujące funkcje do czasu usunięcia zagrożenia:

- Łączenie z firmową pocztą e-mail

- Synchronizowanie plików firmowych za pomocą aplikacji OneDrive do pracy

- Uzyskiwanie dostępu do aplikacji firmowych

**Blokowanie po wykryciu złośliwych aplikacji:**

![Koncepcyjny obraz przedstawiający wykrycie złośliwych aplikacji](./media/skycure-mobile-threat-defense-connector/symantec-arch-1.png)

**Dostęp udzielany po skorygowaniu:**

![Obraz przedstawiający dostęp udzielany po skorygowaniu w następstwie wykrycia złośliwych aplikacji](./media/skycure-mobile-threat-defense-connector/symantec-arch-2.png)

### <a name="control-access-based-on-threat-to-network"></a>Kontrola dostępu oparta na zagrożeniu dla sieci

Wykrywanie w sieci zagrożeń, takich jak ataki typu **Man-in-the-middle**, i ochrona dostępu do sieci Wi-Fi w oparciu o ryzyko dotyczące urządzenia.

**Blokowanie dostępu do sieci za pośrednictwem sieci Wi-Fi:**

![Blokowanie dostępu do sieci za pośrednictwem sieci Wi-Fi](./media/skycure-mobile-threat-defense-connector/symantec-arch-3.png)

**Dostęp udzielany po skorygowaniu:**

![Dostęp udzielany po skorygowaniu](./media/skycure-mobile-threat-defense-connector/symantec-arch-4.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Kontrola dostępu do usługi SharePoint Online oparta na zagrożeniu dla sieci

Wykrywanie w sieci zagrożeń, takich jak ataki typu **Man-in-the-middle**, i blokowanie synchronizacji plików firmowych w oparciu o ryzyko dotyczące urządzenia.

**Blokowanie usługi SharePoint Online po wykryciu zagrożeń sieciowych:**

![Blokowanie usługi SharePoint Online po wykryciu zagrożeń sieciowych](./media/skycure-mobile-threat-defense-connector/symantec-arch-5.png)

**Dostęp udzielany po skorygowaniu:**

![Dostęp udzielany po skorygowaniu — przykład dla programu Sharepoint](./media/skycure-mobile-threat-defense-connector/symantec-arch-6.png)

## <a name="supported-platforms"></a>Obsługiwane platformy

- **Android 4.1 i nowsze**

- **iOS 8 i nowsze**

## <a name="pre-requisites"></a>Wymagania wstępne

- Azure Active Directory Premium

- Subskrypcja usługi Microsoft Intune

- Subskrypcja programu Symantec Endpoint Protection Mobile

Więcej informacji można znaleźć w [witrynie internetowej firmy Symantec](https://www.skycure.com/skycure-microsoft-integration/).

## <a name="next-steps"></a>Następne kroki

Poniżej przedstawiono kroki, które należy wykonać w celu zintegrowania usługi Intune z programem SEP Mobile:

- [Konfiguracja integracji z programem SEP Mobile w usłudze Intune](skycure-mtd-connector-integration.md)

- [Dodawanie i przypisywanie aplikacji SEP Mobile, aplikacji Microsoft Authenticator i zasad konfiguracji aplikacji systemu iOS](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Tworzenie zasad zgodności urządzeń w programie SEP Mobile przy użyciu usługi Intune](mtd-device-compliance-policy-create.md)

- [Włączanie łącznika MTD programu SEP Mobile w usłudze Intune](mtd-connector-enable.md)
