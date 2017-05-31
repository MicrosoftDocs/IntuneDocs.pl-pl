---
title: "Dodawanie identyfikatorów IMEI do usługi Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące dodawania identyfikatorów firmy (numerów IMEI) do usługi Microsoft Intune. "
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 25414cd42159d1c3e09b80d236ccb12f0df5662a
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017

---

# <a name="add-corporate-identifiers"></a>Dodawanie identyfikatorów firmy

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Jako administrator IT możesz utworzyć i zaimportować plik z wartościami rozdzielanymi przecinkami (CSV) zawierający listę numerów IMEI (International Mobile Equipment Identity) służących do identyfikowania urządzeń firmowych. Każdy numer IMEI może zawierać szczegółowe informacje określone na liście do celów administracyjnych.

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

## <a name="add-corporate-identifiers"></a>Dodawanie identyfikatorów firmy
Aby utworzyć listę, utwórz listę wartości rozdzielonych przecinkami (.csv) zawierającą dwie kolumny, bez nagłówka. Dodaj identyfikator IMEI w lewej kolumnie i szczegółowe informacje w prawej kolumnie. Długość szczegółowych informacji nie może przekraczać 128 znaków. Są one przeznaczone tylko do użytku administracyjnego. Szczegóły nie są wyświetlane na urządzeniu. Aktualne ograniczenie wynosi 500 wierszy w pliku CSV.

**Przekaż plik csv zawierający numery seryjne** — utwórz listę wartości rozdzielanych przecinkami (csv) w dwóch kolumnach bez nagłówka i ogranicz listę do 5000 urządzeń lub 5 MB na plik csv. 

|||
|-|-|
|&lt;IMEI 1&gt;|&lt;Szczegóły urządzenia 1&gt;|
|&lt;IMEI 2&gt;|&lt;Szczegóły urządzenia 2&gt;|

Ten plik CSV wyświetlony w edytorze tekstu wygląda następująco:

```
01234567890123,device details
02234567890123,device details
```


> [!IMPORTANT]
> Niektóre urządzenia z systemem Android mają wiele numerów IMEI. Usługa Intune rejestruje w spisie po jednym numerze IMEI na urządzenie. Jeśli zostanie zaimportowany numer IMEI inny niż numer zarejestrowany w spisie usługi Intune, urządzenie zostanie zaklasyfikowane jako urządzenie osobiste, a nie należące do firmy. Zaimportowanie wielu numerów IMEI urządzenia spowoduje, że dla numerów niezarejestrowanych w spisie będzie wyświetlany stan rejestracji **Nieznany**.

**Aby dodać listę .csv identyfikatorów firmy**

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku Intune wybierz kolejno opcje **Rejestracja urządzeń** > **Ograniczenia rejestracji**, wybierz opcję **Identyfikatory urządzeń firmowych**, a następnie kliknij przycisk **Dodaj**.

3. W bloku **Dodaj identyfikatory** określ typ identyfikatora **IMEI**. Możesz określić, czy poprzednio zaimportowane numery powinny **zastąpić szczegóły istniejących identyfikatorów**.  

4. Kliknij ikonę folderu i określ ścieżkę do listy, którą chcesz zaimportować. Przejdź do pliku CSV IMEI i wybierz przycisk **Dodaj**.

Po zaimportowaniu te urządzenia mogą być zarejestrowane lub nie, a ich stan ma wartość **Zarejestrowane** lub **Nie kontaktowano się**. Wartość **Nie kontaktowano się** oznacza, że z urządzeniem nigdy nie nawiązano połączenia w usłudze Intune.

## <a name="delete--corporate-identifiers"></a>Usuwanie identyfikatorów firmy

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku Intune wybierz kolejno opcje **Rejestracja urządzeń** > **Ograniczenia rejestracji**, następnie opcję **Identyfikatory urządzeń firmowych** i przycisk **Usuń**.

3. W bloku **Usuń identyfikatory** przewiń do pliku .csv identyfikatorów urządzeń, aby je usunąć, a następnie kliknij przycisk **Usuń**.

## <a name="imei-specifications"></a>Specyfikacje IMEI
Szczegółowe specyfikacje dotyczące identyfikatorów IMEI (International Mobile Equipment Identifier) można znaleźć w portalu [3GPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).
