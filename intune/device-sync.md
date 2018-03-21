---
title: "Synchronizacja urządzeń w usłudze Microsoft Intune — Azure | Micrososft Docs"
description: "Synchronizowanie urządzeń zarejestrowanych lub zarządzanych w usłudze Microsoft Intune w celu pobrania najnowszych zasad i akcji. Obejmuje kroki synchronizowania przy użyciu witryny Azure Portal i zawiera listę kodów błędów z możliwością ponowienia próby."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d2d13ce2ed06549a6cd09fd766a0072b15fcd067
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/08/2018
---
# <a name="sync-devices-to-get-the-latest-policies-and-actions---intune"></a>Synchronizacja urządzeń w celu pobrania najnowszych zasad i akcji — usługa Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akcja urządzenia **Synchronizacja** wymusza natychmiastowe zameldowanie się wybranego urządzenia w usłudze Intune. Zameldowane urządzenie natychmiast odbiera wszelkie przypisane do niego oczekujące akcje lub zasady. Ta funkcja ułatwia natychmiastowe weryfikowanie przypisanych zasad i rozwiązywanie dotyczących ich problemów bez konieczności czekania na następne zaplanowane zameldowanie.

## <a name="supported-platforms"></a>Obsługiwane platformy

- Windows
- Windows Phone
- iOS
- macOS
- Android

## <a name="sync-a-device"></a>Synchronizowanie urządzenia

1. Zaloguj się do witryny [Azure Portal](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**. 
3. W obszarze **Intune** wybierz pozycję **Urządzenia**, a następnie wybierz pozycję **Wszystkie urządzenia**.
4. Z listy zarządzanych przez Ciebie urządzeń wybierz urządzenie, wybierz pozycję **...Więcej**, a następnie wybierz akcję **Synchronizuj**.
5. Kliknij przycisk **Tak**, aby potwierdzić.


## <a name="retryable-error-codes"></a>Kody błędów z możliwością ponowienia próby

Gdy administrator uruchamia akcję **Synchronizuj** urządzenia, aplikacje systemu iOS i Android, których działanie zakończyło się niepowodzeniem i które wywołały kod błędu z możliwością ponowienia próby, będą nadal dostępne dla urządzenia. Jednak w przypadku aplikacji, które wywołały kod błędu bez możliwości ponowienia próby, udostępnienie ich dla urządzenia nastąpi dopiero po 7 dniach.


| Kod błędu  | Sugerowany opis | Z możliwością ponowienia próby |
|---|---|---|
| 2016330898 | Wystąpił nieznany błąd. | Nie |
| 2016330897 | Przekroczono limit czasu połączenia z usługą Intune. Zresetuj połączenie. | Tak |
| 2016330896 | Utracono połączenie z Internetem. Zresetuj połączenie. | Tak |
| 2016330895 | Utracono połączenie z Internetem. Zresetuj połączenie. | Tak |
| 2016330894 | Utracono połączenie z Internetem. Zresetuj połączenie. | Tak |
| 2016330893 | Utracono połączenie z Internetem. Zresetuj połączenie. | Tak|
| 2016330892 | Roaming międzynarodowy jest wyłączony. | Nie|
| 2016330891 | Nie można uzyskać dostępu do połączenia danych komórkowych na tym urządzeniu podczas prowadzenia rozmowy telefonicznej. Poczekaj na zakończenie rozmowy telefonicznej. | Tak|
| 2016330890 | Sieć komórkowa dla tego urządzenia. W tym momencie nie można użyć tych urządzeń. | Nie|
| 2016330889 | Nawiązanie bezpiecznego połączenia nie powiodło się. Zresetuj połączenie. | Tak|
| 2016330888 | Ocena relacji zaufania serwera nie powiodła się. | Nie|

## <a name="next-step"></a>Następny krok

Wybierz pozycję **Akcje urządzeń**, aby zobaczyć stan akcji synchronizacji. 
