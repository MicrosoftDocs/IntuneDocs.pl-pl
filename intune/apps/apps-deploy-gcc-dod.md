---
title: Aplikacje dla środowisk GCC High i DoD
titleSuffix: Microsoft Intune
description: Dowiedz się więcej na temat aplikacji dla środowisk GCC High i DoD korzystających z usługi Microsoft Intune.
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
ms.assetid: 29329f86-1aa5-434f-9925-8dc28bf35348
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8a6c430ab15c40166e8c3afbccd6fcc7c2c5976d
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72507257"
---
# <a name="deploying-apps-using-intune-on-the-gcc-high-and-dod-environments"></a>Wdrażanie aplikacji przy użyciu usługi Intune w środowiskach GCC High i DoD 

Administratorzy dzierżaw mogą dystrybuować aplikacje dla swoich pracowników za pomocą usługi Microsoft Intune. Pracownik to osoba zatrudniona w firmie, czyli użytkownik aplikacji. Istnieje wiele typów aplikacji, które można wdrażać za pomocą usługi Intune w środowiskach GCC High i DoD. Jeśli administrator musi przekazać i rozpowszechnić aplikację systemu Windows przeznaczoną dla odbiorców w środowiskach GCC High i DoD, która została utworzona przez użytkownika, przez innych dostawców lub która została pobrana jako aplikacja offline z witryny [Microsoft Store dla Firm](https://businessstore.microsoft.com/store), administrator może rozpowszechnić ją jako [aplikację biznesową](apps-add.md#app-types-in-microsoft-intune).  

> [!NOTE]
> W środowiskach komercyjnych administrator dzierżawy może zsynchronizować usługę Store dla Firm z usługą Intune, jednak w środowiskach GCC High i DoD ta usługa jest niedostępna. W takiej sytuacji administratorzy muszą przeprowadzić wdrożenie aplikacji, przekazując ją bezpośrednio do usługi Intune.  

## <a name="add-line-of-business-apps-using-intune"></a>Dodawanie aplikacji biznesowych przy użyciu usługi Intune 

Aby dodać aplikację biznesową przeznaczoną dla środowiska GCC High lub DoD przy użyciu usługi Intune, możesz wykonać instrukcje dla [aplikacji biznesowych systemu Windows](lob-apps-windows.md). Jeśli chcesz, możesz najpierw wdrożyć aplikację Portal firmy z witryny Microsoft Store dla Firm. Jeśli zdecydujesz się na korzystanie z aplikacji Portal firmy, możesz ją ręcznie zainstalować i wdrożyć. Aby uzyskać więcej informacji, zobacz [Jak skonfigurować aplikację Portal firmy w usłudze Microsoft Intune](company-portal-app.md). 

## <a name="distribute-offline-apps-from-the-store-for-business-using-intune"></a>Dystrybuowanie aplikacji w trybie offline z witryny Store dla Firm przy użyciu usługi Intune  

Jeśli musisz [pobrać aplikację licencjonowaną w trybie offline](https://docs.microsoft.com/microsoft-store/distribute-offline-apps#download-an-offline-licensed-app) z witryny Microsoft Store dla Firm, wykonaj następujące kroki, aby pobrać aplikację: 

1. Zaloguj się do witryny [Store dla Firm](https://businessstore.microsoft.com/).
2. Wybierz pozycję **Zarządzaj** > **Ustawienia**.
3. W sekcji **Możliwości zakupów** ustaw opcję **Pokaż aplikacje offline** na **Wł.**

Jeśli podczas kupowania aplikacji będzie dostępna wersja offline aplikacji, będzie można wybrać zmianę typu licencji na licencję w trybie offline. Po uzyskaniu aplikacji można nią zarządzać, wybierając pozycję **Zarządzaj** > **Produkty i usługi** w witrynie [Store dla Firm](https://businessstore.microsoft.com/). Ponadto możesz pobrać aplikację wraz z jej zależnościami. Pobraną aplikację (oraz jej zależności) możesz następnie wdrożyć dla użytkowników za pomocą usługi Intune.  

## <a name="syncing-intune-to-the-store-for-business"></a>Synchronizowanie usługi Intune z witryną Store dla Firm 

W środowisku komercyjnym (nie dla instytucji rządowych) administrator może zsynchronizować usługę Intune z witryną Microsoft Store dla Firm. Ta funkcja nie jest dostępna w środowiskach dla instytucji rządowych. Aby uzyskać szczegółowe informacje o różnicach między usługą Intune w środowiskach komercyjnych i usługą Intune w środowiskach dla instytucji rządowych, zobacz [Enterprise Mobility + Security for US Government Service Description (Opis usługi Enterprise Mobility + Security dla instytucji rządowych w Stanach Zjednoczonych)](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-govt-service-description).  

Jeśli chcesz zsynchronizować usługę Intune z kontem witryny Store dla Firm, zobacz temat [Jak zarządzać aplikacjami zakupionymi w sklepie Microsoft Store dla Firm za pomocą usługi Microsoft Intune](windows-store-for-business.md).  

## <a name="compliance"></a>Zgodność 

Przejrzyj instrukcje dotyczące ochrony prywatności oraz zgodności aplikacji i porównaj je z wymaganiami dotyczącymi zgodności, bezpieczeństwa i prywatności Twojej organizacji przy ocenie właściwego użycia tych usług.   

## <a name="next-steps"></a>Następne kroki

Aby dowiedzieć się więcej na temat wdrażania i przypisywania aplikacji, zobacz temat [Przypisywanie aplikacji do grup przy użyciu usługi Microsoft Intune](apps-deploy.md).

 
