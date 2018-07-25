---
title: Synchronizacja urządzeń w usłudze Microsoft Intune — Azure | Micrososft Docs
description: Synchronizuj urządzenia zarejestrowane lub zarządzane w usłudze Microsoft Intune w celu pobierania najnowszych zasad i akcji. Obejmuje kroki synchronizowania przy użyciu witryny Azure Portal i zawiera listę kodów błędów z możliwością ponowienia próby.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 30b4cf585edd7153ee01710ce8c572593056454f
ms.sourcegitcommit: f5998019bbb4769fb50a7ea9bf424199516eb9ee
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/18/2018
ms.locfileid: "39117875"
---
# <a name="sync-devices-to-get-the-latest-policies-and-actions-with-intune"></a>Synchronizacja urządzeń w celu pobierania najnowszych zasad i akcji przy użyciu usługi Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Akcja urządzenia **Synchronizacja** wymusza natychmiastowe zaewidencjonowanie wybranego urządzenia w usłudze Intune. Zaewidencjonowane urządzenie natychmiast odbiera wszelkie przypisane do niego oczekujące akcje lub zasady. Ta funkcja ułatwia natychmiastowe weryfikowanie przypisanych zasad i rozwiązywanie dotyczących ich problemów bez konieczności czekania na następne zaplanowane zameldowanie.

## <a name="supported-platforms"></a>Obsługiwane platformy

- Windows
- Windows Phone
- iOS
- macOS
- Android

## <a name="sync-a-device"></a>Synchronizowanie urządzenia

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**. 
3. W usłudze **Intune** wybierz pozycję **Urządzenia** > **Wszystkie urządzenia**.
4. Z listy zarządzanych urządzeń wybierz urządzenie, wybierz pozycję **Więcej**, a następnie wybierz opcję **Synchronizuj**.
5. Wybierz pozycję **Tak**, aby potwierdzić.

Aby zobaczyć stan akcji synchronizacji, wybierz kolejno pozycje **Urządzenia**  >  **Akcje urządzenia**.

## <a name="retryable-error-codes"></a>Kody błędów z możliwością ponowienia próby

Gdy administrator uruchomi akcję urządzenia **Synchronizuj**, aplikacje systemu iOS i Android, których działanie zakończyło się niepowodzeniem i które zwróciły kod błędu z możliwością ponowienia próby, będą nadal dostępne dla urządzenia. Jednak w przypadku aplikacji, które zwróciły kod błędu bez możliwości ponowienia próby, należy poczekać siedem dni, zanim staną się dostępne dla urządzenia.


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

## <a name="next-steps"></a>Następne kroki

Możesz [sprawdzić szczegóły](device-inventory.md) urządzenia.
 
