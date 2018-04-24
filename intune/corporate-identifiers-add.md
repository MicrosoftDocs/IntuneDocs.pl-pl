---
title: Dodawanie identyfikatorów firmy do usługi Intune
titlesuffix: Microsoft Intune
description: Informacje dotyczące dodawania identyfikatorów urządzeń firmowych (metody rejestracji, numerów IMEI i numerów seryjnych) do usługi Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d9557c5f962390a9893109bc6f5175b1e709f7cd
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="identify-devices-as-corporate-owned"></a>Określanie urządzeń jako firmowe

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Jako administrator usługi Intune możesz określić urządzenia jako należące do firmy, aby doprecyzować zarządzanie i identyfikację. Usługa Intune może wykonywać dodatkowe zadania zarządzania i zbierać dodatkowe informacje, takie jak pełny numer telefonu i spis aplikacji z urządzeń należących do firmy. Można również ustawić ograniczenia urządzenia, aby zablokować rejestrację przez urządzenia, które nie należą do firmy.

Podczas rejestracji usługa Intune automatycznie przypisuje stan „należące do firmy” do urządzeń spełniających następujące warunki:

- Zarejestrowano je przy użyciu konta [menedżera rejestracji urządzeń](device-enrollment-manager-enroll.md) (wszystkie platformy)
- Zarejestrowano je przy użyciu programu [Device Enrollment Program](device-enrollment-program-enroll-ios.md) firmy Apple lub przy użyciu narzędzi [Apple School Manager](apple-school-manager-set-up-ios.md) albo [Apple Configurator](apple-configurator-enroll-ios.md) (tylko system iOS)
- [Zidentyfikowano je jako należące do firmy przed zarejestrowaniem](#identify-corporate-owned-devices-with-imei-or-serial-number) przy użyciu międzynarodowego identyfikatora urządzenia przenośnego (IMEI) (wszystkie platformy z numerami IMEI) lub numeru seryjnego (system iOS i Android)
- Zarejestrowano je w usłudze Azure Active Directory lub pakiecie Enterprise Mobility + Security jako urządzenie z systemem Windows 10 Enterprise
- Na [liście właściwości urządzenia](#change-device-ownership) ustawiono je jako firmowe

Po zarejestrowaniu można [zmieniać ustawienie własności](#change-device-ownership) z **Osobiste** na **Firmowe**.

## <a name="identify-corporate-owned-devices-with-imei-or-serial-number"></a>Identyfikowanie urządzeń należących do firmy przy użyciu numeru IMEI lub numeru seryjnego

Jako administrator usługi Intune możesz utworzyć i zaimportować plik z wartościami rozdzielanymi przecinkami (CSV) zawierający listę numerów IMEI lub numerów seryjnych. Usługa Intune używa tych identyfikatorów, aby określić własność urządzeń jako firmowe podczas ich rejestracji. Numery IMEI możesz deklarować dla wszystkich obsługiwanych platform. Numery seryjne można zadeklarować tylko dla urządzeń z systemem iOS, macOS i Android. Każdy numer IMEI lub numer seryjny może zawierać szczegółowe informacje określone na liście do celów administracyjnych.

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

[Dowiedz się, jak znaleźć numer seryjny urządzenia marki Apple](https://support.apple.com/HT204308).<br>
[Dowiedz się, jak znaleźć numer seryjny urządzenia z systemem Android](https://support.google.com/store/answer/3333000).

## <a name="add-corporate-identifiers"></a>Dodawanie identyfikatorów firmy
Aby utworzyć listę, utwórz listę wartości rozdzielonych przecinkami (.csv) zawierającą dwie kolumny, bez nagłówka. Dodaj identyfikatory IMEI lub numery seryjne w lewej kolumnie i szczegółowe informacje w prawej kolumnie. W jednym pliku csv można zaimportować tylko jeden typ identyfikatora: numer IMEI lub numer seryjny. Długość szczegółowych informacji nie może przekraczać 128 znaków. Są one przeznaczone tylko do użytku administracyjnego. Szczegóły nie są wyświetlane na urządzeniu. Aktualne ograniczenie wynosi 5000 wierszy na plik csv.

**Przekaż plik csv zawierający numery seryjne** — utwórz listę wartości rozdzielanych przecinkami (csv) w dwóch kolumnach bez nagłówka i ogranicz listę do 5000 urządzeń lub 5 MB na plik csv.

|||
|-|-|
|&lt;Identyfikator 1&gt;|&lt;Szczegóły urządzenia 1&gt;|
|&lt;Identyfikator 2&gt;|&lt;Szczegóły urządzenia 2&gt;|

Ten plik CSV wyświetlony w edytorze tekstu wygląda następująco:

```
01234567890123,device details
02234567890123,device details
```

> [!IMPORTANT]
> Niektóre urządzenia z systemem Android mają wiele numerów IMEI. Usługa Intune odczytuje tylko jeden numer IMEI dla każdego zarejestrowanego urządzenia. Jeśli zaimportujesz numer IMEI inny niż numer zarejestrowany w spisie usługi Intune, urządzenie będzie zaklasyfikowane jako urządzenie osobiste, a nie należące do firmy. Zaimportowanie wielu numerów IMEI urządzenia spowoduje, że dla numerów niezarejestrowanych w spisie wyświetlany będzie stan rejestracji **Nieznany**.<br>
>Należy również zauważyć, że nie ma gwarancji, iż numery seryjne systemu Android są unikatowe albo że istnieją. Aby ustalić, czy numer seryjny jest niezawodnym identyfikatorem urządzenia, skontaktuj się z dostawcą urządzenia.
>Numery seryjne zgłaszane przez urządzenie do usługi Intune mogą być niezgodne z identyfikatorami wyświetlanymi w menu Ustawienia/Informacje o systemie Android na urządzeniu. Sprawdź typ numeru seryjnego podanego przez producenta urządzenia.

### <a name="add-a-csv-list-of-corporate-identifiers"></a>Dodawanie listy CSV identyfikatorów firmy

1. W obszarze usługi [Intune w witrynie Azure Portal](https://portal.azure.com) wybierz kolejno pozycje **Rejestrowanie urządzenia** > **Identyfikatory urządzeń firmowych**, a następnie kliknij przycisk **Dodaj**.

   ![Obszar roboczy identyfikatorów urządzeń firmowych z wyróżnionym przyciskiem Dodaj](./media/add-corp-id.png)

2. W bloku **Dodawanie identyfikatorów** określ typ identyfikatora: **IMEI** lub **Numer seryjny**. Możesz określić, czy poprzednio zaimportowane numery powinny **zastąpić szczegóły istniejących identyfikatorów**.

3. Kliknij ikonę folderu i określ ścieżkę do listy, którą chcesz zaimportować. Przejdź do pliku csv i wybierz przycisk **Dodaj**. Aby zobaczyć nowe identyfikatory urządzeń, możesz kliknąć pozycję **Odśwież**.

Importowane urządzenia nie są zawsze zarejestrowane. Urządzenia mogą mieć stan **Zarejestrowane** lub **Nie kontaktowano się**. Wartość **Nie kontaktowano się** oznacza, że z urządzeniem nigdy nie nawiązano połączenia w usłudze Intune.

### <a name="delete-corporate-identifiers"></a>Usuwanie identyfikatorów firmy

1. W obszarze usługi [Intune w witrynie Azure Portal](https://portal.azure.com) wybierz kolejno pozycje **Rejestrowanie urządzenia** > **Identyfikatory urządzeń firmowych**.
2. Wybierz identyfikatory urządzeń do usunięcia, a następnie wybierz pozycję **Usuń**.
3. Potwierdzenie usunięcia.

Usunięcie identyfikatora firmy zarejestrowanego urządzenia nie zmienia własności tego urządzenia. Aby zmienić własność urządzenia, przejdź do pozycji **Urządzenia**, wybierz urządzenie, wybierz pozycję **Właściwości** i zmień ustawienie **Własność urządzenia**.

### <a name="imei-specifications"></a>Specyfikacje IMEI
Szczegółowe specyfikacje dotyczące identyfikatorów IMEI (International Mobile Equipment Identifier) można znaleźć w portalu [3GPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).

## <a name="change-device-ownership"></a>Zmienianie własności urządzeń

We właściwościach urządzeń jest wyświetlana **Własność** dla rekordów każdego urządzenia w usłudze Intune. Jako administrator możesz określić urządzenia jako **Osobiste** lub **Firmowe**.

**Aby zmienić własność urządzeń:**
1. W usłudze [Intune w witrynie Azure Portal](https://portal.azure.com) przejdź do pozycji **Urządzenia** i wybierz urządzenie.
2. Wybierz pozycję **Właściwości**.
3. Określ **Własność urządzeń** jako **Osobiste** lub **Firmowe**.

   ![Właściwości urządzenia z opcjami Kategoria urządzenia i Własność urządzeń](./media/device-properties.png)
