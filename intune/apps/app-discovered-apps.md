---
title: Odnalezione aplikacje
titleSuffix: Microsoft Intune
description: Zapoznaj się ze szczegółowymi informacjami o wykrytych aplikacjach znalezionych przez usługę Intune na urządzeniu.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 07dd262f-13e7-4cb2-9cc2-b755d1c276cf
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8519ad00024be43371cd118e3f37ae2fbc57898b
ms.sourcegitcommit: 25acfc88b366d2da71c37d354a0238e4f1168325
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2019
ms.locfileid: "72813364"
---
# <a name="intune-discovered-apps"></a>Aplikacje odnalezione przez usługę Intune

**Aplikacje odnalezione** przez usługę Intune to lista wykrytych aplikacji na urządzeniach zarejestrowanych w usłudze Intune w Twojej dzierżawie. Pełni ona rolę spisu oprogramowania dla dzierżawy. **Odnalezione aplikacje** to oddzielny raport niezależny od raportów dotyczących [instalacji aplikacji](apps-monitor.md). W przypadku urządzeń osobistych usługa Intune nigdy nie zbiera informacji o niezarządzanych aplikacjach. Na urządzeniach firmowych na potrzeby tego raportu zbierane są informacje o wszystkich aplikacjach — zarządzanych i niezarządzanych. Poniżej znajduje się tabela z mapowaniem oczekiwanego zachowania. Zwykle raport jest odświeżany co 7 dni od momentu rejestracji (nie jest to cotygodniowe odświeżanie dla całej dzierżawy). Jedynym wyjątkiem od tego okresu odświeżania są informacje o aplikacji gromadzone przez rozszerzenie do zarządzania usługi Intune dla aplikacji Win32, które są zbierane co 24 godziny.

## <a name="monitor-discovered-apps-with-intune"></a>Monitorowanie odnalezionych aplikacji za pomocą usługi Intune

Usługa Intune udostępnia zagregowaną listę aplikacji wykrytych na urządzeniach zarejestrowanych w usłudze Intune w Twojej dzierżawie.

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. W okienku **Intune** wybierz pozycję **Aplikacje klienckie** > **Odnalezione aplikacje**.

>[!NOTE]
>Listę odnalezionych aplikacji można wyeksportować do pliku CSV, wybierając pozycję **Eksportuj** w bloku **Odnalezione aplikacje**.
>
>W przypadku odnalezionych aplikacji Win32 obecnie nie jest dostępna liczba zagregowana. Ten typ danych można wyświetlać tylko dla poszczególnych urządzeń.

Usługa Intune udostępnia również listę odnalezionych aplikacji dla poszczególnych urządzeń w dzierżawie.

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. W okienku usługi Intune wybierz pozycje **Urządzenia** > **Wszystkie urządzenia**.
3. Wybierz urządzenie.
4. Aby wyświetlić wykryte aplikacje dla tego urządzenia, wybierz pozycję **Odnalezione aplikacje** w sekcji **Monitoruj**.

## <a name="details-of-discovered-apps"></a>Szczegóły odnalezionych aplikacji

Poniższa lista zawiera następujące informacje: typ platformy aplikacji, aplikacje monitorowane w przypadku urządzeń osobistych, aplikacje monitorowane na urządzeniach należących do firmy i cykl odświeżania. Aby uzyskać więcej informacji na temat typów aplikacji obsługiwanych przez usługę Intune, zobacz [Typy aplikacji w usłudze Microsoft Intune](apps-add.md#app-types-in-microsoft-intune).

| Platforma | Urządzenia osobiste | Urządzenia należące do firmy | Cykl odświeżania |
|------------------------------------------------------------------------|----------------------------------|--------------------------------------------------|---------------------------------------|
| Windows 10 (aplikacje Win32) UWAGA: [Wymaga rozszerzenia do zarządzania usługi Intune](intune-management-extension.md) na urządzeniu | Nie dotyczy | Wszystkie aplikacje Win32 znajdujące się na liście Dodaj/Usuń programy | Co 24 godziny od rejestracji urządzenia |
| Windows 10 (nowoczesne aplikacje) | Tylko zarządzane nowoczesne aplikacje | Wszystkie nowoczesne aplikacje zainstalowane na urządzeniu | Co 7 dni od rejestracji urządzenia |
| Windows 8.1 | Tylko aplikacje zarządzane | Tylko aplikacje zarządzane | Co 7 dni od rejestracji urządzenia |
| Windows Phone 8 | Tylko aplikacje zarządzane | Tylko aplikacje zarządzane | Co 7 dni od rejestracji urządzenia |
| Windows RT | Tylko aplikacje zarządzane | Tylko aplikacje zarządzane | Co 7 dni od rejestracji urządzenia |
| iOS | Tylko aplikacje zarządzane | Wszystkie aplikacje zainstalowane na urządzeniu | Co 7 dni od rejestracji urządzenia |
| macOS | Wszystkie aplikacje zainstalowane na urządzeniu | Wszystkie aplikacje zainstalowane na urządzeniu | Co 7 dni od rejestracji urządzenia |
| Android | Tylko aplikacje zarządzane | Wszystkie aplikacje zainstalowane na urządzeniu | Co 7 dni od rejestracji urządzenia |
| Android Enterprise | Tylko aplikacje zarządzane | Tylko aplikacje zainstalowane w profilu służbowym | Co 7 dni od rejestracji urządzenia |

> [!NOTE]
> Dołączone do usługi Azure AD hybrydowe urządzenia z systemem Windows 10, jak pokazano w obciążeniu zarządzania aplikacjami w programie Configuration Manager, aktualnie nie zbierają spisu aplikacji za pomocą rozszerzenia do zarządzania usługi Intune (IME) zgodnie z powyższym harmonogramem. Aby uniknąć tego problemu, obciążenie zarządzania aplikacjami w programie Configuration Manager należy przełączyć na usługę Intune w celu zainstalowania na urządzeniu rozszerzenia IME (rozszerzenie IME jest wymagane w przypadku spisu Win32 i wdrożenia środowiska PowerShell). Wszelkie zmiany i aktualizacje dotyczące tego zachowania są ogłaszane w sekcjach dotyczących [rozwiązań w trakcie opracowywania](../fundamentals/in-development.md) i/lub [nowości](../fundamentals/whats-new.md).

Liczba wykrytych aplikacji może być niezgodna z liczbą stanu instalacji aplikacji. Możliwe przyczyny niespójności to:

- Ukierunkowana zmiana zainstalowanej aplikacji zarządzanej może spowodować spadek liczby instalacji w bloku stanu, ale będzie nadal zgłaszana w wykrytych aplikacjach.
- Przeznaczenie tej samej aplikacji dla wielu wystąpień w dzierżawie spowoduje wygenerowanie różnych liczników z powodu potencjalnego nakładania się użytkowników lub urządzeń. W każdym wystąpieniu aplikacji będą liczeni nakładający się użytkownicy, ale odnalezione aplikacje będą mieć powielone liczby.
- Odnalezione aplikacje i stan aplikacji są zbierane w różnych przedziałach czasowych, które mogą spowodować rozbieżności liczby aplikacji.

## <a name="next-steps"></a>Następne kroki

- [Typy aplikacji w usłudze Microsoft Intune](apps-add.md#app-types-in-microsoft-intune)
- [Monitorowanie informacji o aplikacji i przypisań z użyciem usługi Microsoft Intune](apps-monitor.md)
