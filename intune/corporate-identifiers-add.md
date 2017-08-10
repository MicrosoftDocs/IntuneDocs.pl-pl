---
title: "Dodawanie identyfikatorów IMEI do usługi Intune"
titleSuffix: Intune on Azure
description: "Informacje dotyczące dodawania identyfikatorów urządzeń firmowych (numerów IMEI) do usługi Microsoft Intune. \""
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6b38bf2da70537d07a050fa21be9a2a3062ca84b
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2017
---
# <a name="add-corporate-identifiers"></a>Dodawanie identyfikatorów firmy

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Jako administrator usługi Intune możesz utworzyć i zaimportować plik z wartościami rozdzielanymi przecinkami (CSV) zawierający listę numerów IMEI (International Mobile Equipment Identity) lub numerów seryjnych. Usługa Intune używa tych identyfikatorów, aby określić własność urządzeń jako firmowe. Numery IMEI możesz deklarować dla wszystkich obsługiwanych platform. Numery seryjne można zadeklarować tylko dla urządzeń z systemem iOS i Android. Każdy numer IMEI lub numer seryjny może zawierać szczegółowe informacje określone na liście do celów administracyjnych.

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

[Dowiedz się, jak znaleźć numer seryjny urządzenia marki Apple](https://support.apple.com/HT204308).<br>
[Dowiedz się, jak znaleźć numer seryjny urządzenia z systemem Android](https://support.google.com/store/answer/3333000).

## <a name="add-corporate-identifiers"></a>Dodawanie identyfikatorów firmy
Aby utworzyć listę, utwórz listę wartości rozdzielonych przecinkami (.csv) zawierającą dwie kolumny, bez nagłówka. Dodaj identyfikatory IMEI lub numery seryjne w lewej kolumnie i szczegółowe informacje w prawej kolumnie. W jednym pliku csv można zaimportować tylko jeden typ identyfikatora: numer IMEI lub numer seryjny. Długość szczegółowych informacji nie może przekraczać 128 znaków. Są one przeznaczone tylko do użytku administracyjnego. Szczegóły nie są wyświetlane na urządzeniu. Aktualne ograniczenie wynosi 500 wierszy w pliku CSV.

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


**Aby dodać listę .csv identyfikatorów firmy**

1. W portalu Intune wybierz kolejno opcje **Rejestrowanie urządzenia** > **Ograniczenia rejestracji**, wybierz opcję **Identyfikatory urządzeń firmowych**, a następnie kliknij przycisk **Dodaj**.

 ![Zrzut ekranu obszaru roboczego identyfikatorów urządzeń firmowych z wyróżnionym przyciskiem Dodaj.](./media/add-corp-id.png)

2. W bloku **Dodawanie identyfikatorów** określ typ identyfikatora: **IMEI** lub **Numer seryjny**. Możesz określić, czy poprzednio zaimportowane numery powinny **zastąpić szczegóły istniejących identyfikatorów**.

3. Kliknij ikonę folderu i określ ścieżkę do listy, którą chcesz zaimportować. Przejdź do pliku csv i wybierz przycisk **Dodaj**. Aby zobaczyć nowe identyfikatory urządzeń, możesz kliknąć pozycję **Odśwież**.

Importowane urządzenia nie są zawsze zarejestrowane. Urządzenia mogą mieć stan **Zarejestrowane** lub **Nie kontaktowano się**. Wartość **Nie kontaktowano się** oznacza, że z urządzeniem nigdy nie nawiązano połączenia w usłudze Intune.

## <a name="delete-corporate-identifiers"></a>Usuwanie identyfikatorów firmy

1. W portalu Intune wybierz kolejno opcje **Rejestrowanie urządzenia** > **Ograniczenia rejestracji**, następnie opcję **Identyfikatory urządzeń firmowych** i przycisk **Usuń**.

3. W bloku **Usuń identyfikatory** przewiń do pliku .csv identyfikatorów urządzeń, aby je usunąć, a następnie kliknij przycisk **Usuń**.

## <a name="imei-specifications"></a>Specyfikacje IMEI
Szczegółowe specyfikacje dotyczące identyfikatorów IMEI (International Mobile Equipment Identifier) można znaleźć w portalu [3GPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).
