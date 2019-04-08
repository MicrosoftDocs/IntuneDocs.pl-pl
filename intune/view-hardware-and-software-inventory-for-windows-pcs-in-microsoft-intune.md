---
title: Wyświetlanie spisu sprzętu i oprogramowania dla komputerów z systemem Windows
titleSuffix: Microsoft Intune
description: Jak wyświetlić informacje o sprzęcie i oprogramowaniu komputerów z systemem Windows zarządzanych jako komputery osobiste za pomocą oprogramowania klienckiego usługi Intune.
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
ms.assetid: 3c10f4c9-520b-4864-92fc-a45a9f640ad4
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1de4783d9d6e151f616406cc6a2f80406f58e408
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2019
ms.locfileid: "58798572"
---
# <a name="view-hardware-and-software-inventory-for-windows-pcs"></a>Wyświetlanie spisu sprzętu i oprogramowania dla komputerów z systemem Windows

[!INCLUDE [classic-portal](includes/classic-portal.md)]

Usługa Intune zbiera szczegółowe informacje dotyczące sprzętu i oprogramowania komputerów zarządzanych jako komputery osobiste za pomocą oprogramowania klienckiego usługi Intune. Poniżej opisano kroki procedur:

-   Tworzenie raportu zawierającego informacje na temat możliwości sprzętowych zarządzanych komputerów osobistych.

-   Tworzenie raportu zawierającego listę oprogramowania zainstalowanego na każdym komputerze osobistym.

-   Odświeżanie spisu komputerów osobistych w celu upewnienia się, że raport zawiera aktualne dane.

## <a name="to-display-information-about-pcs-you-manage"></a>Aby wyświetlić informacje o zarządzanych przez Ciebie komputerach osobistych

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz kolejno pozycje **Raporty** &gt; **Raporty ze spisu komputerów**.

2.  Na stronie **Utwórz nowy raport** zaakceptuj wartości domyślne lub dostosuj je, aby filtrować wyniki zwracane w raporcie. Możesz na przykład wybrać opcję wyświetlania w raporcie tylko komputerów osobistych z systemem Windows 8.1.

3.  Wybierz pozycję **Wyświetl raport**, aby otworzyć nowe okno **Raport o spisie komputerów**.

    Raport można sortować według dowolnej kolumny, na przykład **Nazwa**, **Typ obudowy** lub **Producent** , wybierając jej nagłówek.

## <a name="to-display-software-installed-on-pcs-you-manage"></a>Aby wyświetlić oprogramowanie zainstalowane na zarządzanych przez Ciebie komputerach osobistych

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz kolejno pozycje **Raporty** &gt; **Wykryte raporty oprogramowania**.

2.  Na stronie **Utwórz nowy raport** zaakceptuj wartości domyślne lub dostosuj je, aby filtrować wyniki zwracane w raporcie. Na przykład możesz określić, że w raporcie będzie wyświetlane tylko oprogramowanie opublikowane przez firmę Microsoft.

3.  Wybierz pozycję **Wyświetl raport**, aby otworzyć nowe okno **Raport z wykrytego oprogramowania**.

    Raport można sortować według dowolnej kolumny, na przykład **Nazwa**, **Wydawca** lub **Kategoria**, wybierając jej nagłówek. Możesz rozwinąć aktualizacje na liście w celu wyświetlenia większej liczby szczegółów (takich jak komputery osobiste, na których zainstalowano aktualizacje), wybierając strzałkę kierunkową obok elementu listy.

## <a name="to-refresh-computer-inventory-to-ensure-it-is-current"></a>Aby odświeżyć spis komputerów w celu upewnienia się, że jest on aktualny

1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com/) wybierz kolejno pozycje **Grupy** &gt; **Wszystkie urządzenia** (lub inną grupę zawierającą komputer osobisty, dla którego chcesz odświeżyć spis).

2.  Wybierz komputer osobisty lub naciśnij i przytrzymaj klawisz **Ctrl**, aby wybrać wiele komputerów.

3.  Na pasku zadań wybierz kolejno pozycje **Zadania zdalne** &gt; **Odśwież zapasy**.

4.  Aby wyświetlić stan zadania, wybierz pozycję **Zadania zdalne** w prawym dolnym rogu strony.

    W oknie dialogowym **Stan zadania** są wyświetlane bieżące zadania zdalne, stan zadania, nazwa urządzenia i wszelkie zgłoszone błędy. Okno zawiera również link do informacji dotyczących rozwiązywania problemów.

### <a name="see-also"></a>Zobacz także

[Typowe zadania związane z zarządzaniem komputerem z systemem Windows za pomocą klienta oprogramowania usługi Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)
