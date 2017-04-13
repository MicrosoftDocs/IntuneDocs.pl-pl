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
translationtype: Human Translation
ms.sourcegitcommit: 4ebd74c77145464574a1fed878ec4dbc2eb3c271
ms.openlocfilehash: 7bb8168c442a3340e8c185f1908acd9be15cab05
ms.lasthandoff: 04/05/2017

---

# <a name="add-corporate-identifiers"></a>Dodawanie identyfikatorów firmy

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Jako administrator IT możesz utworzyć i zaimportować plik z wartościami rozdzielanymi przecinkami (CSV) zawierający listę numerów IMEI (International Mobile Equipment Identity) służących do identyfikowania urządzeń firmowych. Każdy numer IMEI może zawierać szczegółowe informacje określone na liście do celów administracyjnych.

Gdy przekazujesz numery seryjne firmowych urządzeń z systemem iOS, muszą one być sparowane z profilem rejestracji w firmie. Urządzenia należy wówczas zarejestrować przy użyciu programu Device Enrollment Program (DEP) firmy Apple lub narzędzia Apple Configurator, aby były wyświetlane jako należące do firmy. 

## <a name="create-a-csv-file"></a>Tworzenie pliku CSV
Aby utworzyć listę, utwórz listę wartości rozdzielonych przecinkami (.csv) zawierającą dwie kolumny, bez nagłówka. Dodaj identyfikator IMEI w lewej kolumnie i szczegółowe informacje w prawej kolumnie. Informacje szczegółowe mogą zawierać maksymalnie 128 znaków. Aktualne ograniczenie wynosi 500 wierszy w pliku CSV.

**Przekaż plik csv zawierający numery seryjne** — utwórz listę wartości rozdzielanych przecinkami (csv) w dwóch kolumnach bez nagłówka i ogranicz listę do 5000 urządzeń lub 5 MB na plik csv.

|||
|-|-|
|&lt;IMEI 1&gt;|&lt;Szczegóły urządzenia 1&gt;|
|&lt;IMEI 2&gt;|&lt;Szczegóły urządzenia 2&gt;|

    This .csv file when viewed in a text editor appears as:

    ```
    01 234567 890123,device details
    02 234567 890123,device details
    ```

**Aby dodać listę .csv identyfikatorów firmy**

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku Intune wybierz kolejno pozycje **Zarejestruj urządzenia** i **Identyfikatory urządzenia firmy**.

3. Jeśli importujesz plik z nowymi szczegółami, które zastąpią istniejące, wybierz opcję **Zastąp szczegóły istniejących identyfikatorów**, aby nowe szczegóły zastąpiły istniejące.

4. Przejdź do pliku CSV IMEI i wybierz przycisk **Dodaj**.

> [!IMPORTANT]
> Niektóre urządzenia z systemem Android mają wiele numerów IMEI. Usługa Intune rejestruje w spisie po jednym numerze IMEI na urządzenie. Jeśli zostanie zaimportowany numer IMEI inny niż numer zarejestrowany w spisie usługi Intune, urządzenie zostanie zaklasyfikowane jako urządzenie osobiste, a nie należące do firmy. Zaimportowanie wielu numerów IMEI urządzenia spowoduje, że dla numerów niezarejestrowanych w spisie będzie wyświetlany stan rejestracji **Nieznany**.

Po zaimportowaniu te urządzenia mogą być zarejestrowane lub nie, a ich stan ma wartość **Zarejestrowane** lub **Nie kontaktowano się**. Wartość **Nie kontaktowano się** oznacza, że z urządzeniem nigdy nie nawiązano połączenia w usłudze Intune.

## <a name="delete-a-csv-list"></a>Usuwanie listy CSV

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku Intune wybierz kolejno pozycje **Zarejestruj urządzenia** i **Identyfikatory urządzenia firmy**.

3. Wybierz przycisk **Usuń**.

Szczegółowe specyfikacje dotyczące identyfikatorów IMEI (International Mobile Equipment Identifier) można znaleźć w portalu [3GPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).

