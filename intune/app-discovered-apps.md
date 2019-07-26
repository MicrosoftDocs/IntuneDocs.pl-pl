---
title: Odnalezione aplikacje
titleSuffix: Microsoft Intune
description: Zapoznaj się ze szczegółowymi informacjami o wykrytych aplikacjach znalezionych przez usługę Intune na urządzeniu.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 07dd262f-13e7-4cb2-9cc2-b755d1c276cf
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1827375dc1905b5c881f743777a73340f0215e0c
ms.sourcegitcommit: 8023ba7d42e61bd37305c69f52a649cf83bf72e2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/23/2019
ms.locfileid: "68388516"
---
# <a name="intune-discovered-apps"></a>Aplikacje odnalezione przez usługę Intune

**Aplikacje odnalezione** przez usługę Intune to lista wykrytych aplikacji na urządzeniach zarejestrowanych w usłudze Intune w Twojej dzierżawie. Pełni ona rolę spisu oprogramowania dla dzierżawy. **Odnalezione aplikacje** to oddzielny raport niezależny od raportów dotyczących [instalacji aplikacji](apps-monitor.md). W przypadku urządzeń osobistych usługa Intune nigdy nie zbiera informacji o niezarządzanych aplikacjach. Na urządzeniach firmowych na potrzeby tego raportu zbierane są informacje o wszystkich aplikacjach — zarządzanych i niezarządzanych. Poniżej znajduje się tabela z mapowaniem oczekiwanego zachowania. Zwykle raport jest odświeżany co 7 dni od momentu rejestracji (nie jest to cotygodniowe odświeżanie dla całej dzierżawy). Jedynym wyjątkiem od tego okresu odświeżania są informacje o aplikacji gromadzone przez rozszerzenie do zarządzania usługi Intune dla aplikacji Win32, które są zbierane co 24 godziny.

## <a name="monitor-discovered-apps-with-intune"></a>Monitorowanie odnalezionych aplikacji za pomocą usługi Intune

Usługa Intune udostępnia listę wykrytych aplikacji na urządzeniach zarejestrowanych w usłudze Intune w Twojej dzierżawie.

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. W okienku **Intune** wybierz pozycję **Aplikacje klienckie** > **Odnalezione aplikacje**.

>[!NOTE]
>Listę odnalezionych aplikacji można wyeksportować do pliku CSV, wybierając pozycję **Eksportuj** w bloku **Odnalezione aplikacje**.

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

Liczba wykrytych aplikacji może być niezgodna z liczbą stanu instalacji aplikacji. Możliwe przyczyny niespójności to:
- Ukierunkowana zmiana zainstalowanej aplikacji zarządzanej może spowodować spadek liczby instalacji w bloku stanu, ale będzie nadal zgłaszana w wykrytych aplikacjach.
- Przeznaczenie tej samej aplikacji dla wielu wystąpień w dzierżawie spowoduje wygenerowanie różnych liczników z powodu potencjalnego nakładania się użytkowników lub urządzeń. W każdym wystąpieniu aplikacji będą liczeni nakładający się użytkownicy, ale odnalezione aplikacje będą mieć powielone liczby.
- Odnalezione aplikacje i stan aplikacji są zbierane w różnych przedziałach czasowych, które mogą spowodować rozbieżności liczby aplikacji.

## <a name="next-steps"></a>Następne kroki

- [Typy aplikacji w usłudze Microsoft Intune](apps-add.md#app-types-in-microsoft-intune)
- [Monitorowanie informacji o aplikacji i przypisań z użyciem usługi Microsoft Intune](apps-monitor.md)
