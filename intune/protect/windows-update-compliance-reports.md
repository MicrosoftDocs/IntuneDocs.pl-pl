---
title: Użycie raportów rozwiązania Update Compliance dla aktualizacji systemu Windows w usłudze Microsoft Intune
titleSuffix: Microsoft Intune
description: Użyj rozwiązania Update Compliance pakietu OMS do wyświetlenia danych raportów dla aktualizacji systemu Windows wdrożonych za pomocą usługi Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/25/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0de98a0820e15a09c2b3724b216359580327259e
ms.sourcegitcommit: ce518a5dfe62c546a77f32ef372f36efbaad473f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2019
ms.locfileid: "74465727"
---
# <a name="intune-compliance-reports-for-updates"></a>Raporty zgodności usługi Intune dla aktualizacji

Jeśli użyto usługi Intune do wdrożenia aktualizacji systemu Windows na urządzeniach z systemem Windows 10, możesz wyświetlić szczegóły dotyczące zgodności aktualizacji za pomocą usługi Intune lub bezpłatnego rozwiązania o nazwie *Update Compliance*, które jest częścią pakietu Microsoft Operations Management Suite (OMS).

## <a name="use-intune"></a>Używanie usługi Intune

Aby przejrzeć raport zasad dotyczący stanu wdrożenia dla skonfigurowanych pierścieni aktualizacji systemu Windows 10:

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Wybierz pozycję **Urządzenia** > **Przegląd** > **Stan aktualizacji oprogramowania**. Zostaną wyświetlone ogólne informacje o stanie wszystkich przypisanych pierścieni aktualizacji.

3. Aby wyświetlić dodatkowe szczegóły, wybierz pozycję **Monitoruj**. Następnie w obszarze **Aktualizacje oprogramowania** wybierz pozycję **Stan wdrożenia według pierścienia aktualizacji** i wybierz pierścień wdrożenia do przejrzenia.

   W sekcji **Monitorowanie** wybierz jeden z następujących raportów, aby wyświetlić bardziej szczegółowe informacje o pierścieniu aktualizacji:

   - **Stan urządzenia** — Spowoduje to wyświetlenie stanu konfiguracji urządzenia. Aby uzyskać szczegółowe informacje, zobacz [Aktualizowanie obiektu deviceConfigurationDeviceStatus]( https://docs.microsoft.com/graph/api/intune-deviceconfig-deviceconfigurationdevicestatus-update?view=graph-rest-1.0).

   - **Stan użytkownika** — Spowoduje to wyświetlenie informacji o nazwie użytkownika, stanie i dacie ostatniego raportu. Aby uzyskać szczegółowe informacje, zobacz [Wyświetlanie listy obiektów deviceConfigurationUserStatus](https://docs.microsoft.com/graph/api/intune-deviceconfig-deviceconfigurationuserstatus-list?view=graph-rest-1.0).

   - **Stan aktualizacji użytkownika końcowego** — Spowoduje to wyświetlenie stanu aktualizacji urządzenia z systemem Windows. Aby uzyskać szczegółowe informacje, zobacz [Obiekt windowsUpdateState](https://docs.microsoft.com/graph/api/resources/intune-shared-windowsupdatestate?view=graph-rest-beta).

## <a name="use-update-compliance"></a>Używanie rozwiązania Update Compliance

Wdrożenia aktualizacji systemu Windows 10 można monitorować za pomocą rozwiązania [Update Compliance](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor) będącego częścią narzędzi Windows Analytics. Rozwiązanie Update Compliance jest oferowane za pośrednictwem witryny Azure Portal i jest dostępne bezpłatnie dla urządzeń spełniających jego [wymagania wstępne](https://docs.microsoft.com/windows/deployment/update/update-compliance-get-started#update-compliance-prerequisites).  

Dzięki temu rozwiązaniu można nadać komercyjny identyfikator dowolnemu urządzeniu z systemem Windows 10 zarządzanemu przez usługę Intune, dla którego chcesz otrzymywać raport zgodności aktualizacji.  

W usłudze Intune możesz użyć ustawień ścieżki OMA-URI dla niestandardowych zasad do skonfigurowania identyfikatora komercyjnego. Zobacz [Ustawienia zasad usługi Intune dla urządzeń z systemem Windows 10 w usłudze Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).  

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
