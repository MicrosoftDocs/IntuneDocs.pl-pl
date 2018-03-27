---
title: Uwagi dotyczące zarządzania urządzeniami z systemem Windows przy użyciu usługi Intune na platformie Azure
description: Uwagi dotyczące korzystania z usługi Intune na platformie Azure do zarządzania urządzeniami z systemem Windows w organizacji.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/14/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 71effb587bfb82ecae18afda67b05fffd2127052
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2018
---
# <a name="intune-on-azure-console-and-legacy-intune-pc-client"></a>Usługa Intune w konsoli platformy Azure i starszej wersji klienta usługi Intune

Usługa Intune została niedawno przeniesiona do architektury usługi aplikacji SaaS bazujących na platformie Azure. Platforma Azure oferuje znaczne ulepszenia dotyczące skali, pojemności i wydajności. To przeniesienie oferuje również rozszerzone środowisko administratora usługi Intune i zoptymalizowane przepływy pracy w portalu Azure. 

W przypadku korzystania z usługi Intune na platformie Azure do zarządzania urządzeniami z systemem Windows w organizacji należy wziąć pod uwagę następujące kwestie:

## <a name="legacy-pc-client-features-are-only-available-in-the-silverlight-console"></a>Funkcje starszej wersji klienta są dostępne tylko w konsoli programu Silverlight

Przepływy pracy zarządzania za pomocą klienta usługi Intune używają [Konsoli administracyjnej usługi Intune opartej na technologii Silverlight ](https://manage.microsoft.com/), co powoduje następujące konsekwencje:

- Do wszystkich niegrupowych zadań zarządzania za pomocą klienta usługi Intune należy użyć konsoli programu Silverlight.
- W przypadku zarządzania grupami należy użyć [usługi Intune w portalu Azure](https://portal.azure.com/). To wymaganie wynika z faktu, że usługa Intune używa teraz grup usługi Azure Active Directory zamiast starszych grup usługi Intune. 

Ze względu na przełączenie do grup usługi Azure Active Directory filtrowanie „na podstawie grupy” w widokach pulpitu nawigacyjnego konsoli Silverlight nieznacznie się zmieniło. Aby użyć filtru w interfejsie użytkownika zaktualizowanej wersji programu Silverlight, wykonaj następujące kroki:

1. Wybierz widok.
2. W polu **Filtry** wprowadź nazwę grupy, według której chcesz filtrować, a następnie naciśnij klawisz Enter. Spowoduje to włączenie filtru widoku listy, który wyświetla urządzenia z tej określonej grupy.

   ![](media/intune_on_azure/image01.png)

## <a name="manage-windows-10-devices-by-using-mdm"></a>Zarządzanie urządzeniami z systemem Windows 10 za pomocą funkcji zarządzania urządzeniami mobilnymi (MDM)

Firma Microsoft zaleca użycie [funkcji zarządzania urządzeniami mobilnymi (MDM) do zarządzania urządzeniami z systemem Windows 10](https://docs.microsoft.com/intune/device-restrictions-windows-10), zamiast korzystania ze starszej wersji klienta usługi Intune. Możliwość zarządzania systemem Windows 10 za pomocą funkcji zarządzania urządzeniami mobilnymi jest dostępna w usłudze Intune w portalu Azure. Funkcja zarządzania urządzeniami mobilnymi z systemem Windows 10 udostępnia wiele nowych możliwości zarządzania i zabezpieczeń, które nie są dostępne przy użyciu starszej wersji klienta usługi Intune.

## <a name="continue-to-manage-windows-7-by-using-intune-pc-client"></a>Zarządzanie systemem Windows 7 w dalszym ciągu przy użyciu klienta usługi Intune

W przypadku systemu Windows 7, który nie podlega zarządzaniu przy użyciu funkcji zarządzania urządzeniami mobilnymi, firma Microsoft będzie kontynuować obsługę istniejących funkcji klienta usługi Intune tylko w konsoli programu Silverlight. Należy rozważyć migrację do funkcji zarządzania urządzeniami mobilnymi podczas uaktualniania do systemu Windows 10.

## <a name="mdm-capabilities"></a>Możliwości zarządzania urządzeniami mobilnymi

Aby uzyskać szczegółowe porównanie możliwości klienta i funkcji zarządzania urządzeniami mobilnymi, zobacz temat [Porównanie zarządzania komputerami z systemem Windows jako komputerami i jako urządzeniami mobilnymi](https://docs.microsoft.com/intune-classic/deploy-use/pc-management-comparison). Aktualizacje funkcji zarządzania urządzeniami mobilnymi będą udostępniać nowe funkcje zarządzania w odniesieniu do urządzeń z systemem Windows 10 zarejestrowanych w funkcji MDM, w tym opcje oceny aplikacji Win 32. Zobacz sekcję [Co nowego](https://docs.microsoft.com/intune/whats-new), aby uzyskać informacje na temat najnowszych dodatków do usługi.

## <a name="switch-from-pc-client-to-mdm"></a>Przejście z klienta do funkcji zarządzania urządzeniami mobilnymi

Aby przełączyć się z zarządzania urządzeniami z systemem Windows 10 za pomocą klienta usługi Intune na zarządzanie za pomocą funkcji MDM, wykonaj następujące kroki:

1. W konsoli programu Silverlight wykonaj **Selektywne czyszczenie**, aby wyrejestrować urządzenia z klienta.
  ![](media/intune_on_azure/image02.png)
2. Zarejestruj ponownie urządzenie przy użyciu [funkcji zarządzania urządzeniami mobilnymi (i/lub dołączenia do usługi Azure AD)](https://docs.microsoft.com/intune/windows-enroll). 

## <a name="next-steps"></a>Następne kroki
[Rejestrowanie urządzeń z systemem Windows](https://docs.microsoft.com/intune/windows-enroll)

 
