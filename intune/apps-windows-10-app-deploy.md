---
title: Wdrażanie aplikacji systemu Windows 10 w usłudze Microsoft Intune
titlesuffix: ''
description: Dowiedz się więcej na temat scenariuszy dotyczących aplikacji systemu Windows 10 dostępnych w usłudze Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/31/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: abebfb5e-054b-435a-903d-d1c31767bcf2
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7508f2c2eca06ceacf203103ab2cad53abc39a65
ms.sourcegitcommit: 2d1e89fa5fa721e79648e41fde147a035e7b047d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/31/2018
ms.locfileid: "43347436"
---
# <a name="windows-10-app-deployment-using-microsoft-intune"></a>Wdrażanie aplikacji systemu Windows 10 w usłudze Microsoft Intune 

Obecnie usługa Microsoft Intune obsługuje różne typy aplikacji i scenariusze wdrażania na urządzeniach z systemem Windows 10. Po dodaniu aplikacji do usługi Microsoft Intune należy ją przypisać do użytkowników i urządzeń. Poniżej znajdziesz więcej szczegółowych informacji na temat obsługiwanych scenariuszy w systemie Windows 10. Dodatkowo przedstawiono istotne informacje, o których należy pamiętać podczas wdrażania aplikacji w systemie Windows. 

Aplikacje obsługiwane na urządzeniach z systemem Windows 10 to aplikacje biznesowe i aplikacje dostępne w sklepie Microsoft dla Firm.

> [!Note]
> Minimalna wymagana wersja systemu Windows 10 umożliwiająca wdrażanie aplikacji w kontekście urządzenia to aktualizacja z [23 maja 2018 r. — KB4100403 (kompilacja systemu operacyjnego 17134.81)](https://support.microsoft.com/en-us/help/4100403/windows-10-update-kb4100403).

## <a name="windows-10-line-of-business-apps"></a>Aplikacje biznesowe dla systemu Windows 10

Aplikacje biznesowe dla systemu Windows 10 są podpisywane i przesyłane do konsoli administratora w usłudze Intune i mogą obejmować zarówno nowoczesne aplikacje, takie jak aplikacje platformy uniwersalnej systemu Windows oraz pakiety aplikacji systemu Windows (AppX), jak i aplikacje Win 32, takie jak proste pliki pakietu instalatora Microsoft (MSI). Aktualizacje aplikacji biznesowych muszą być każdorazowo ręcznie przekazywane i wdrażane przez administratora. Wdrażane aktualizacje są automatycznie instalowane na urządzeniach użytkowników końcowych, na których zainstalowano aplikację, bez udziału użytkownika. Użytkownik nie ma kontroli nad aktualizacjami. 

## <a name="microsoft-store-for-business-apps"></a>Aplikacje ze Sklepu Microsoft dla Firm

Aplikacje ze sklepu Microsoft dla Firm to nowoczesne aplikacje zakupione w portalu administratora w sklepie Microsoft dla Firm, które następnie są synchronizowane z usługą Microsoft Intune w celu zarządzania nimi. Aplikacje mogą być **licencjonowane w trybie online** lub **licencjonowane w trybie offline**. Aktualizacje aplikacji ze sklepu Microsoft dla firm są zarządzane bezpośrednio przez sklep Microsoft Store, bez konieczności wykonywania dodatkowych czynności przez administratora. Administrator może również uniemożliwić aktualizacje określonych aplikacji przy użyciu niestandardowego identyfikatora URI. Aby uzyskać więcej informacji, zobacz [Enterprise app management — Prevent app from automatic updates (Zarządzanie aplikacjami dla przedsiębiorstw — zapobieganie automatycznym aktualizacjom aplikacji)](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management#prevent-app-from-automatic-updates). Użytkownik końcowy może również wyłączyć aktualizowanie wszystkich aplikacji ze sklepu Microsoft dla Firm na urządzeniu. 

## <a name="installing-apps-on-windows-10-devices"></a>Instalowanie aplikacji na urządzeniach z systemem Windows 10
W zależności od typu aplikacji aplikację można zainstalować na urządzeniu z systemem Windows 10, korzystając z jednego z dwóch sposobów:

- **Kontekst użytkownika**: po wdrożeniu aplikacji w kontekście użytkownika zarządzana aplikacja zostanie zainstalowana na urządzeniu tego użytkownika, gdy zaloguje się on na urządzeniu. Należy pamiętać, że instalacja aplikacji nie powiedzie się, jeśli użytkownik nie zaloguje się na urządzeniu. 
    - Nowoczesne aplikacje biznesowe i aplikacje ze sklepu Microsoft dla Firm (zarówno w trybie online, jak i offline) mogą być wdrażane w kontekście użytkownika i będą obsługiwały zarówno wymaganą, jak i dostępną intencję.
- **Kontekst urządzenia**: po wdrożeniu aplikacji w kontekście urządzenia zarządzana aplikacja zostanie zainstalowana bezpośrednio na urządzeniu przez usługę Intune.
    - Tylko nowoczesne aplikacje biznesowe oraz aplikacje ze sklepu Microsoft dla Firm licencjonowane online mogą być wdrażane w kontekście urządzenia i będą obsługiwały wyłącznie wymaganą intencję.

> [!Note]
> Wdrażanie pakietów MSI za pośrednictwem funkcji MDM w kontekście urządzenia nie jest jeszcze obsługiwane na urządzeniach z systemem Windows 10.

Po wdrożeniu aplikacji w kontekście urządzenia instalacja zakończy się powodzeniem pod warunkiem, że wskazane urządzenie obsługuje kontekst urządzenia. Ponadto wdrażanie w kontekście urządzenia podlega następującym warunkom:
- Jeśli aplikacja jest wdrażana w kontekście urządzenia i wskazany jest użytkownik, instalacja zakończy się niepowodzeniem, a w konsoli administratora zostanie wyświetlony następujący stan i komunikat o błędzie:
    - Stan: Niepowodzenie.
    - Błąd: Dla użytkownika nie można przeprowadzić instalacji z kontekstu urządzenia.
- Jeśli aplikacja jest wdrożona w kontekście urządzenia, ale wskazane jest urządzenie, które nie obsługuje kontekstu urządzenia, instalacja zakończy się niepowodzeniem, a w konsoli administratora zostanie wyświetlony następujący stan i komunikat o błędzie:
    - Stan: Niepowodzenie.
    - Błąd: Ta platforma nie obsługuje instalacji w kontekście urządzenia. 

> [!Note]
> Po zapisaniu przypisania aplikacji w konkretnym wdrożeniu nie można zmienić kontekstu dla tego przypisania. Wyjątkiem są nowoczesne aplikacje. W przypadku nowoczesnych aplikacji można zmienić kontekst z kontekstu użytkownika na kontekst urządzenia. 

Jeśli występuje konflikt zasad w przypadku jednego użytkownika/urządzenia, używane będą następujące priorytety zasad:
- Zasady kontekstu urządzenia mają wyższy priorytet niż zasady kontekstu użytkownika. 
- Zasady instalacji mają wyższy priorytet niż zasady dezinstalacji.

Aby uzyskać więcej informacji na temat przypisywania aplikacji w usłudze Microsoft Intune, zobacz [Przypisywanie aplikacji do grup przy użyciu usługi Microsoft Intune](apps-deploy.md) i [Dołączanie i wykluczanie przypisań aplikacji w usłudze Microsoft Intune](apps-inc-exl-assignments.md). Aby uzyskać więcej informacji na temat typów aplikacji w usłudze Intune, zobacz [Dodawanie aplikacji w usłudze Microsoft Intune](apps-add.md).

## <a name="next-steps"></a>Następne kroki

- Aby dowiedzieć się więcej na temat przypisywania aplikacji do grup, zobacz temat [Przypisywanie aplikacji do grup przy użyciu usługi Microsoft Intune](apps-deploy.md).
- Aby dowiedzieć się więcej na temat monitorowania przypisań aplikacji, zobacz [Jak monitorować aplikacje](apps-monitor.md).
