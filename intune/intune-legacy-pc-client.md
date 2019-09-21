---
title: Starszy klient usługi Intune i usługa Intune na platformie Azure
description: Uwagi dotyczące korzystania z usługi Intune na platformie Azure do zarządzania urządzeniami z systemem Windows w organizacji.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/15/2018
ms.topic: archived
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: f3891ce150ea740baa3ba18591139c66d78d9d00
ms.sourcegitcommit: 1494ff4b33c13a87f20e0f3315da79a3567db96e
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 09/20/2019
ms.locfileid: "71166374"
---
# <a name="intune-on-azure-console-and-legacy-intune-pc-client"></a>Usługa Intune w konsoli platformy Azure i starszej wersji klienta usługi Intune

Usługa Intune korzysta z architektury usługi aplikacji SaaS bazujących na platformie Azure. Platforma Azure oferuje znaczne ulepszenia dotyczące skali, pojemności i wydajności. Zapewnia to również rozszerzone środowisko administratora usługi Intune i zoptymalizowane przepływy pracy w portalu Azure. 

W przypadku korzystania z usługi Intune na platformie Azure do zarządzania urządzeniami z systemem Windows w organizacji należy wziąć pod uwagę następujące kwestie:

## <a name="manage-windows-10-devices-by-using-mdm"></a>Zarządzanie urządzeniami z systemem Windows 10 za pomocą funkcji zarządzania urządzeniami mobilnymi (MDM)

Firma Microsoft zaleca użycie [funkcji zarządzania urządzeniami mobilnymi (MDM) do zarządzania urządzeniami z systemem Windows 10](device-restrictions-windows-10.md), zamiast korzystania ze starszej wersji klienta usługi Intune. Możliwość zarządzania systemem Windows 10 za pomocą funkcji zarządzania urządzeniami mobilnymi jest dostępna w usłudze Intune w portalu Azure. Funkcja zarządzania urządzeniami mobilnymi z systemem Windows 10 udostępnia wiele nowych możliwości zarządzania i zabezpieczeń, które nie są dostępne przy użyciu starszej wersji klienta usługi Intune.

## <a name="legacy-pc-client-features-are-only-available-in-the-silverlight-console"></a>Funkcje starszej wersji klienta są dostępne tylko w konsoli programu Silverlight

Przepływy pracy zarządzania za pomocą klienta usługi Intune używają [Konsoli administracyjnej usługi Intune opartej na technologii Silverlight ](https://manage.microsoft.com/), co powoduje następujące konsekwencje:

- Do wszystkich niegrupowych zadań zarządzania za pomocą klienta usługi Intune należy użyć konsoli programu Silverlight.
- W przypadku zarządzania grupami należy użyć [usługi Intune w portalu Azure](https://portal.azure.com/). To wymaganie wynika z faktu, że usługa Intune używa teraz grup usługi Azure Active Directory zamiast starszych grup usługi Intune. 

Ze względu na przełączenie do grup usługi Azure Active Directory filtrowanie „na podstawie grupy” w widokach pulpitu nawigacyjnego konsoli Silverlight nieznacznie się zmieniło. Aby użyć filtru w interfejsie użytkownika zaktualizowanej wersji programu Silverlight, wykonaj następujące kroki:

1. Wybierz widok.
2. W polu **Filtry** wprowadź nazwę grupy, według której chcesz filtrować, a następnie naciśnij klawisz Enter. Spowoduje to włączenie filtru widoku listy, który wyświetla urządzenia z tej określonej grupy.

   ![Filtry — dane wejściowe listy rozwijanej bez zaznaczenia](media/intune-legacy-pc-client/image01.png)


## <a name="continue-to-manage-windows-7-by-using-intune-pc-client"></a>Zarządzanie systemem Windows 7 w dalszym ciągu przy użyciu klienta usługi Intune

W przypadku systemu Windows 7, który nie podlega zarządzaniu przy użyciu funkcji zarządzania urządzeniami mobilnymi, firma Microsoft będzie kontynuować obsługę istniejących funkcji klienta usługi Intune tylko w konsoli programu Silverlight. Należy rozważyć migrację do funkcji zarządzania urządzeniami mobilnymi podczas uaktualniania do systemu Windows 10.

## <a name="mdm-capabilities"></a>Możliwości zarządzania urządzeniami mobilnymi

Aby uzyskać szczegółowe porównanie możliwości klienta i funkcji zarządzania urządzeniami mobilnymi, zobacz temat [Porównanie zarządzania komputerami z systemem Windows jako komputerami i jako urządzeniami mobilnymi](pc-management-comparison.md). Aktualizacje funkcji zarządzania urządzeniami mobilnymi będą udostępniać nowe funkcje zarządzania w odniesieniu do urządzeń z systemem Windows 10 zarejestrowanych w funkcji MDM, w tym opcje oceny aplikacji Win 32. Zobacz sekcję [Co nowego](whats-new.md), aby uzyskać informacje na temat najnowszych dodatków do usługi.

## <a name="switch-from-pc-client-to-mdm"></a>Przejście z klienta do funkcji zarządzania urządzeniami mobilnymi

Aby przełączyć się z zarządzania urządzeniami z systemem Windows 10 za pomocą klienta usługi Intune na zarządzanie za pomocą funkcji MDM, wykonaj następujące kroki:

1. W konsoli programu Silverlight wykonaj **Selektywne czyszczenie**, aby wyrejestrować urządzenia z klienta.
  ![Okno podręczne ostrzeżeń z wybranym przyciskiem radiowym "selektywne czyszczenie urządzenia"](media/intune-legacy-pc-client/image02.png)
2. Zarejestruj ponownie urządzenie przy użyciu [funkcji zarządzania urządzeniami mobilnymi (i/lub dołączenia do usługi Azure AD)](windows-enroll.md).

## <a name="next-steps"></a>Następne kroki
[Rejestrowanie urządzeń z systemem Windows](windows-enroll.md)
