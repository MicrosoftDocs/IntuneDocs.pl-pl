---
title: Wycofanie komputera z systemem Windows
titlesuffix: Microsoft Intune
description: Jak wycofać komputer z systemem Windows zarządzany przez usługę Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: archived
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 5c916182-d99c-44c5-a779-3f596f261c40
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0bafdfd4d688ccbbd547c41e0495af19f0b691e4
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57461111"
---
# <a name="retire-a-windows-pc"></a>Wycofanie komputera z systemem Windows

[!INCLUDE [classic-portal](includes/classic-portal.md)]

Wykonaj następujące kroki, aby wycofać komputery z systemem Windows, które są zarządzane jako komputery przy użyciu oprogramowania klienckiego usługi Intune. Wycofanie komputera spowoduje usunięcie go z zarządzania przy użyciu usługi Intune. Przy użyciu usługi Intune nie można wyczyścić komputera, aby przywrócić jego ustawienia fabryczne.

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz pozycję **Grupy** &gt; **Wszystkie urządzenia** (lub inną grupę zawierającą komputer, który chcesz wycofać).

2.  Wybierz urządzenia do wycofania, a następnie wybierz pozycję **Wycofaj/wyczyść**.

Aby ponownie zarejestrować komputer w usłudze Intune, ponownie zainstaluj klienta oprogramowania na komputerze, korzystając z informacji przedstawionych w temacie [Instalowanie klienta komputera z systemem Windows przy użyciu usługi Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).

Jeśli komputer nie może nawiązać połączenia z usługą Intune, w obszarze roboczym **Pulpit nawigacyjny** zostanie wyświetlony komunikat.

W przypadku wycofywania komputera:

-   Komputer jest usuwany z zarządzania i spisu w usłudze Intune, a skojarzona z nim licencja jest udostępniana do ponownego użycia. Polecenie Wycofaj/wyczyść usuwa oprogramowanie klienckie usługi Intune, ale nie usuwa aplikacji ani danych z komputera. Wycofanie nie powoduje wykonania pełnego czyszczenia danych na komputerze.

-   Jego stan nie jest już wyświetlany w konsoli usługi Intune.

-   Usługa Intune usuwa klienta oprogramowania z komputera. Jeśli komputer jest połączony z usługą Intune, klient oprogramowania zostanie usunięty po kolejnym nawiązaniu połączenia.

-   Program Microsoft Intune Endpoint Protection jest usuwany z komputera. Jeśli na komputerze zainstalowano inną aplikację ochrony punktu końcowego, która jest wyłączona, można ją ponownie włączyć po usunięciu programu Microsoft Intune Endpoint Protection, aby upewnić się, że komputer jest chroniony.

-   Wszystkie zasady są usuwane z komputera, a wartości ustawione przez zasady są zmieniane.

-   Komputer nie będzie już otrzymywać aktualizacji oprogramowania ani aktualizacji definicji złośliwego oprogramowania z usługi Intune.

-   W zależności od konfiguracji wycofane komputery mogą nadal otrzymywać aktualizacje w ramach usług Windows Server Update Services, Windows Update lub Microsoft Update.

    > [!IMPORTANT]
    > Jeśli oprogramowanie klienckie zostało zainstalowany przy użyciu obiektu zasad grupy, przed usunięciem tego oprogramowania należy usunąć obiekt zasad grupy, aby zapobiec ponownej instalacji oprogramowania.

    Jeśli odinstalowanie klienta nie powiedzie się, zapoznaj się z sekcją [Rozwiązywanie problemów z programem Endpoint Protection](/intune/troubleshoot-endpoint-protection-in-microsoft-intune), aby uzyskać dalszą pomoc.

### <a name="see-also"></a>Zobacz także

[Typowe zadania związane z zarządzaniem komputerem z systemem Windows za pomocą klienta oprogramowania usługi Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)
