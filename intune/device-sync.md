---
title: "Synchronizacja urządzeń w usłudze Intune"
titlesuffix: Azure portal
description: "Dowiedz się, jak synchronizować urządzenia w usłudze Intune, aby pobrać najnowsze zasady i akcje."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7d48b81e6df912815d9ef843b4588f8c1076a8a7
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/23/2018
---
# <a name="sync-devices-with-intune-to-get-the-latest-policies-and-actions"></a>Synchronizacja urządzeń w usłudze Intune w celu pobrania najnowszych zasad i akcji


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Akcja urządzenia **Synchronizacja** wymusza natychmiastowe zaewidencjonowanie wybranego urządzenia w usłudze Intune. Zaewidencjonowane urządzenie natychmiast odbiera wszelkie przypisane do niego oczekujące akcje lub zasady.  Ta akcja ułatwia natychmiastowe weryfikowanie przypisanych zasad i rozwiązywanie dotyczących ich problemów bez konieczności czekania na następne zaplanowane ewidencjonowanie.

## <a name="supported-platforms"></a>Obsługiwane platformy

- Windows
- Windows Phone
- iOS
- macOS
- Android

## <a name="how-to-sync-a-device"></a>Jak zsynchronizować urządzenie

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie + zarządzanie**.
3. W bloku **Intune** wybierz opcję **Urządzenia**.
4. W bloku **Urządzenia** wybierz pozycję **Wszystkie urządzenia**.
5. Z listy zarządzanych przez Ciebie urządzeń wybierz urządzenie, wybierz pozycję **...Więcej**, a następnie wybierz akcję zdalną **Synchronizuj**.
7. Kliknij przycisk **Tak**, aby potwierdzić akcję.


## <a name="retriable-error-codes"></a>Kody błędów z możliwością ponowienia próby

Gdy administrator uruchamia akcję **Synchronizuj** urządzenia, aplikacje systemu iOS i Android, których działanie zakończyło się niepowodzeniem, ale które wywołały kod błędu z możliwością ponowienia próby, będą dostępne dla urządzenia. Jednak w przypadku aplikacji, które wywołały kod błędu bez możliwości ponowienia próby, udostępnienie ich dla urządzenia będzie możliwe dopiero po 7 dniach.


| Kod błędu  | Sugerowany opis                                                                                                                  | Z możliwością ponowienia próby |
|-------------|----------------------------------------------------------------------------------------------------------------------------------------|-----------|
| 2016330898 | Wystąpił nieznany błąd.                                                                                                             | Nie        |
| 2016330897 | Przekroczono limit czasu połączenia z usługą Intune. Zresetuj połączenie.                                                                             | Tak       |
| 2016330896 | Utracono połączenie z Internetem. Zresetuj połączenie.                                                                            | Tak       |
| 2016330895 | Utracono połączenie z Internetem. Zresetuj połączenie.                                                                            | Tak       |
| 2016330894 | Utracono połączenie z Internetem. Zresetuj połączenie.                                                                            | Tak       |
| 2016330893 | Utracono połączenie z Internetem. Zresetuj połączenie.                                                                            | Tak       |
| 2016330892 | Roaming międzynarodowy jest wyłączony.                                                                                                     | Nie        |
| 2016330891 | Nie można uzyskać dostępu do połączenia danych komórkowych na tym urządzeniu podczas prowadzenia rozmowy telefonicznej. Poczekaj na zakończenie rozmowy telefonicznej. | Tak       |
| 2016330890 | Sieć komórkowa dla tego urządzenia. W tym momencie nie można użyć tych urządzeń.                                                   | Nie        |
| 2016330889 | Nawiązanie bezpiecznego połączenia nie powiodło się. Zresetuj połączenie.                                                                                   | Tak       |
| 2016330888 | Ocena relacji zaufania serwera nie powiodła się.                                                                                                | Nie        |

## <a name="next-steps"></a>Następne kroki

Wybierz pozycję **Akcje urządzeń**, aby zobaczyć stan akcji synchronizacji. 
