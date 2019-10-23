---
title: Wdrażanie aplikacji systemu Windows 10 przy użyciu usługi Microsoft Intune
titleSuffix: ''
description: Dowiedz się więcej na temat scenariuszy wdrażania aplikacji systemu Windows 10 dostępnych w usłudze Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: abebfb5e-054b-435a-903d-d1c31767bcf2
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c8ce24081eae1808d3db0c5078026b306fd209d5
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72507240"
---
# <a name="windows-10-app-deployment-by-using-microsoft-intune"></a>Wdrażanie aplikacji systemu Windows 10 przy użyciu usługi Microsoft Intune 

Usługa Microsoft Intune obsługuje różne typy aplikacji i scenariusze wdrażania na urządzeniach z systemem Windows 10. Po dodaniu aplikacji do usługi Microsoft Intune należy ją przypisać do użytkowników i urządzeń. Ten artykuł zawiera szczegółowe informacje o obsługiwanych scenariuszach systemu Windows 10, a także o kluczowych kwestiach, które należy rozważyć podczas wdrażania aplikacji w systemie Windows. 

Aplikacje obsługiwane na urządzeniach z systemem Windows 10 to aplikacje biznesowe i aplikacje dostępne w sklepie Microsoft dla Firm. Rozszerzenia plików aplikacji dla systemu Windows to msi, appx i appxbundle.  

> [!Note]
> Aby wdrożyć nowoczesne aplikacje, potrzeba co najmniej:
> - Dla systemu Windows 10 1803: [23 maja 2018 r. — KB4100403 (kompilacja systemu operacyjnego 17134.81)](https://support.microsoft.com/help/4100403/windows-10-update-kb4100403).
> - Dla systemu Windows 10 1709 [21 czerwca 2018 r. — KB4284822 (kompilacja systemu operacyjnego 16299.522)](https://support.microsoft.com/help/4284822).
>
> Tylko system Windows 10 w wersji 1803 i nowszej obsługuje instalowanie aplikacji, gdy nie ma skojarzonego użytkownika podstawowego.
>
> Wdrażanie aplikacji biznesowych nie jest obsługiwane na urządzeniach z systemem Windows 10 Home.

## <a name="windows-10-lob-apps"></a>Aplikacje biznesowe systemu Windows 10

Aplikacje biznesowe systemu Windows 10 można podpisywać i przekazywać do konsoli administracyjnej usługi Intune. Mogą one obejmować aplikacje nowoczesne, takie jak aplikacje platformy uniwersalnej systemu Windows oraz pakiety aplikacji systemu Windows (AppX), oraz aplikacje Win 32, takie jak proste pliki pakietu instalatora Microsoft (MSI). Administrator musi ręcznie przekazywać i wdrażać aktualizacje aplikacji biznesowych. Te aktualizacje są instalowane automatycznie na urządzeniach użytkowników, na których zainstalowano aplikację. Interwencja użytkownika nie jest wymagana, a użytkownik nie ma kontroli nad aktualizacjami. 

## <a name="microsoft-store-for-business-apps"></a>Aplikacje ze Sklepu Microsoft dla Firm

Aplikacje ze sklepu Microsoft Store dla Firm to nowoczesne aplikacje zakupione w portalu administratora w sklepie Microsoft Store dla Firm. Następnie są one synchronizowane z usługą Microsoft Intune w celu zarządzania nimi. Aplikacje mogą być licencjonowane w trybie online lub licencjonowane w trybie offline. Sklep Microsoft Store bezpośrednio zarządza aktualizacjami bez konieczności wykonywania dodatkowych czynności przez administratora. Administrator może również uniemożliwić aktualizacje określonych aplikacji przy użyciu niestandardowego identyfikatora URI. Aby uzyskać więcej informacji, zobacz [Enterprise app management — Prevent app from automatic updates (Zarządzanie aplikacjami dla przedsiębiorstw — zapobieganie automatycznym aktualizacjom aplikacji)](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management#prevent-app-from-automatic-updates). Użytkownik końcowy może również wyłączyć aktualizowanie wszystkich aplikacji ze sklepu Microsoft dla Firm na urządzeniu. 

### <a name="categorize-microsoft-store-for-business-apps"></a>Kategoryzowanie aplikacji ze sklepu Microsoft Store dla Firm 
Aby ustalić kategorie aplikacji ze sklepu Microsoft Store dla Firm, wykonaj następujące czynności: 

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Aplikacje klienckie** > **Aplikacje**. Wybierz aplikację ze sklepu Microsoft Store dla Firm. Następnie wybierz pozycję **Informacje o aplikacji** > **Kategoria**. 
3. Wybierz kategorię.

## <a name="install-apps-on-windows-10-devices"></a>Instalowanie aplikacji na urządzeniach z systemem Windows 10
W zależności od typu aplikacji można zainstalować ją na urządzeniu z systemem Windows 10, korzystając z jednego z dwóch sposobów:

- **Kontekst użytkownika**: Po wdrożeniu aplikacji w kontekście użytkownika zarządzana aplikacja zostanie zainstalowana na urządzeniu tego użytkownika, gdy zaloguje się on na urządzeniu. Należy pamiętać, że instalacja aplikacji nie powiedzie się, jeśli użytkownik nie zaloguje się na urządzeniu. 
  - Nowoczesne aplikacje biznesowe i aplikacje ze sklepu Microsoft Store dla Firm (zarówno w trybie online, jak i offline) mogą być wdrażane w kontekście użytkownika. Aplikacje te obsługują zarówno intencję wymaganą, jak i dostępną.
  - Aplikacje Win32 tworzone jako aplikacje typu Tryb użytkownika lub Tryb podwójny mogą być wdrażane w kontekście użytkownika i obsługują zarówno wymaganą, jak i dostępną intencję. 
- **Kontekst urządzenia**: Po wdrożeniu aplikacji w kontekście urządzenia zarządzana aplikacja jest instalowana bezpośrednio na urządzeniu przez usługę Intune.
  - Tylko nowoczesne aplikacje biznesowe oraz aplikacje ze sklepu Microsoft Store dla Firm licencjonowane offline mogą być wdrażane w kontekście urządzenia. Te aplikacje obsługują tylko intencję wymaganą.
  - Aplikacje Win32 tworzone jako aplikacje typu Tryb komputera lub Tryb podwójny mogą być wdrażane w kontekście użytkownika i obsługują tylko wymaganą intencję.

> [!NOTE]
> Dla aplikacji Win32 tworzonych jako aplikacje typu Tryb podwójny administrator musi dla wszystkich przypisań skojarzonych z tym wystąpieniem określić, czy aplikacja będzie działać jako aplikacja trybu użytkownika, czy aplikacja trybu komputera. Nie można zmienić kontekstu wdrożenia dla poszczególnych przypisań.  

Po wdrożeniu aplikacji w kontekście urządzenia instalacja zakończy się powodzeniem pod warunkiem, że wskazane urządzenie obsługuje kontekst urządzenia. Ponadto wdrażanie w kontekście urządzenia podlega następującym warunkom:
- Jeśli aplikacja jest wdrażana w kontekście urządzenia i przeznaczona dla użytkownika, instalacja nie powiedzie się. W konsoli administracyjnej jest wyświetlany następujący stan i błąd:
  - Stan: Niepowodzenie.
  - Błąd: Dla użytkownika nie można przeprowadzić instalacji z kontekstu urządzenia.
- Jeśli aplikacja jest wdrażana w kontekście urządzenia, ale jest przeznaczona dla urządzenia, które nie obsługuje kontekstu urządzenia, instalacja zakończy się niepowodzeniem. W konsoli administracyjnej jest wyświetlany następujący stan i błąd:
  - Stan: Niepowodzenie.
  - Błąd: Ta platforma nie obsługuje instalacji w kontekście urządzenia. 

> [!Note]
> Po zapisaniu przypisania aplikacji w konkretnym wdrożeniu nie można zmienić kontekstu tego przypisania. Wyjątkiem są nowoczesne aplikacje. W przypadku nowoczesnych aplikacji można zmienić kontekst z kontekstu użytkownika na kontekst urządzenia. 

Jeśli wystąpi konflikt zasad w przypadku pojedynczego użytkownika lub urządzenia, obowiązują następujące priorytety:
- Zasady kontekstu urządzenia mają wyższy priorytet niż zasady kontekstu użytkownika. 
- Zasady instalacji mają wyższy priorytet niż zasady dezinstalacji.

Aby uzyskać więcej informacji, zobacz [Dołączanie i wykluczanie przypisań aplikacji w usłudze Microsoft Intune](apps-inc-exl-assignments.md). Aby uzyskać więcej informacji na temat typów aplikacji w usłudze Intune, zobacz [Dodawanie aplikacji w usłudze Microsoft Intune](apps-add.md).

## <a name="next-steps"></a>Następne kroki

- [Przypisywanie aplikacji do grup przy użyciu usługi Microsoft Intune](apps-deploy.md)
- [Jak monitorować aplikacje](apps-monitor.md)
