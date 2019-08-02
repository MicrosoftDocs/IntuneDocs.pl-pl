---
title: Użycie raportów rozwiązania Update Compliance dla aktualizacji systemu Windows w usłudze Microsoft Intune
titleSuffix: Microsoft Intune
description: Użyj rozwiązania Update Compliance pakietu OMS do wyświetlenia danych raportów dla aktualizacji systemu Windows wdrożonych za pomocą usługi Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/12/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 09f3cafc16d8a08885731aa244a089367c6c0933
ms.sourcegitcommit: c715c93bb242f4fe44bbdf2fd585909854ed72b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/30/2019
ms.locfileid: "68660407"
---
# <a name="intune-compliance-reports-for-updates"></a>Raporty zgodności usługi Intune dla aktualizacji
Jeśli użyto usługi Intune do wdrożenia aktualizacji systemu Windows na urządzeniach z systemem Windows 10, możesz wyświetlić szczegóły dotyczące zgodności aktualizacji za pomocą usługi Intune lub bezpłatnego rozwiązania o nazwie *Update Compliance*, które jest częścią pakietu Microsoft Operations Management Suite (OMS).

## <a name="use-intune"></a>Używanie usługi Intune
Aby przejrzeć raport zasad dotyczący stanu wdrożenia dla skonfigurowanych pierścieni aktualizacji systemu Windows 10: 
1. Zaloguj się do [portalu Azure](https://portal.azure.com/).
2. Wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Aktualizacje oprogramowania** > **Przegląd**. Zostaną wyświetlone ogólne informacje o stanie wszystkich przypisanych pierścieni aktualizacji.
4. Otwórz jeden z następujących raportów:  

   **Dla wszystkich pierścieni wdrażania**:
   1. W obszarze **Aktualizacje oprogramowania** > **Pierścienie aktualizacji systemu Windows 10**
   2. W sekcji **Monitorowanie** wybierz pozycję **Stan wdrożenia według pierścienia aktualizacji**.  

   **Dla określonych pierścieni wdrażania**:  

   1. W obszarze **Aktualizacje oprogramowania** > **Pierścienie aktualizacji systemu Windows 10** wybierz pierścień wdrażania, który chcesz przejrzeć.  
   2. W sekcji **Monitorowanie** wybierz jeden z następujących raportów, aby wyświetlić bardziej szczegółowe informacje o pierścieniu aktualizacji:  
      - **Stan urządzenia**  
      - **Stan użytkownika**  

## <a name="use-update-compliance"></a>Używanie rozwiązania Update Compliance
Wdrożenia aktualizacji systemu Windows 10 można monitorować za pomocą rozwiązania [Update Compliance](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor) będącego częścią narzędzi Windows Analytics. Rozwiązanie Update Compliance jest oferowane za pośrednictwem witryny Azure Portal i jest dostępne bezpłatnie dla urządzeń spełniających jego [wymagania wstępne](https://docs.microsoft.com/windows/deployment/update/update-compliance-get-started#update-compliance-prerequisites).  

Dzięki temu rozwiązaniu można nadać komercyjny identyfikator dowolnemu urządzeniu z systemem Windows 10 zarządzanemu przez usługę Intune, dla którego chcesz otrzymywać raport zgodności aktualizacji.  

W konsoli usługi Intune możesz użyć ustawień ścieżki OMA-URI dla niestandardowych zasad do skonfigurowania komercyjnego identyfikatora. Szczegółowe informacje można znaleźć w artykule [Ustawienia zasad usługi Intune dla urządzeń z systemem Windows 10 w usłudze Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).  

Ścieżka OMA-URI (z rozróżnianiem wielkości liter) służąca do konfigurowania komercyjnego identyfikatora to *./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID*  

Na przykład można użyć następujących wartości w obszarze **Dodaj lub edytuj ustawienie OMA-URI**:
- **Nazwa ustawienia**: Identyfikator komercyjny programu Windows Analytics
- **Opis ustawienia**: Konfigurowanie identyfikatorów komercyjnych rozwiązań programu Windows Analytics
- **OMA-URI** (wielkość liter jest rozróżniana): *./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID*
- **Typ danych**: String
- **Wartość**: \<Użyj identyfikatora GUID wyświetlanego na karcie Telemetria systemu Windows w obszarze roboczym pakietu OMS>
 
> [!NOTE]  
> Aby uzyskać więcej informacji o programie MS DM, zobacz [Dostawca usługi konfiguracji (CSP) DMClient]( https://docs.microsoft.com/windows/client-management/mdm/dmclient-csp).

## <a name="next-steps"></a>Następne kroki
[Zarządzanie aktualizacjami oprogramowania w usłudze Intune](windows-update-for-business-configure.md)

