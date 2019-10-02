---
title: Synchronizowanie urządzeń za pomocą usługi Microsoft Intune — Azure | Microsoft Docs
description: Synchronizuj urządzenia zarejestrowane lub zarządzane w usłudze Microsoft Intune w celu pobierania najnowszych zasad i akcji. Obejmuje kroki synchronizowania przy użyciu witryny Azure Portal i zawiera listę kodów błędów z możliwością ponowienia próby.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 173d3e4729b3d620167180fb17fcee6c618604eb
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728419"
---
# <a name="sync-devices-to-get-the-latest-policies-and-actions-with-intune"></a>Synchronizacja urządzeń w celu pobierania najnowszych zasad i akcji przy użyciu usługi Intune


Akcja urządzenia **Synchronizacja** wymusza natychmiastowe zaewidencjonowanie wybranego urządzenia w usłudze Intune. Zaewidencjonowane urządzenie natychmiast odbiera wszelkie przypisane do niego oczekujące akcje lub zasady. Ta funkcja ułatwia natychmiastowe weryfikowanie przypisanych zasad i rozwiązywanie dotyczących ich problemów bez konieczności czekania na następne zaplanowane zameldowanie.

## <a name="supported-platforms"></a>Obsługiwane platformy

- Windows
- Windows Phone
- iOS
- macOS
- Android

## <a name="sync-a-device"></a>Synchronizowanie urządzenia

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973). 
3. W usłudze **Intune** wybierz pozycję **Urządzenia** > **Wszystkie urządzenia**.
4. Z listy zarządzanych urządzeń wybierz urządzenie, aby otworzyć jego okienko *Omówienie*, a następnie wybierz pozycję **Synchronizuj**.
5. Wybierz pozycję **Tak**, aby potwierdzić.

Aby zobaczyć stan akcji synchronizacji, wybierz kolejno pozycje **Urządzenia**  >  **Akcje urządzenia**.

Standardowe częstotliwości zaewidencjonowania zasad usługi Intune można znaleźć w temacie [Czasy cyklu odświeżania](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

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
 
