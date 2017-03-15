---
title: "Dodawanie identyfikatorów IMEI do usługi Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące dodawania identyfikatorów firmy (numerów IMEI) do usługi Microsoft Intune. "
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: d8cb15d1b8c1c100f15084e43d2c3c4633fd64b5
ms.openlocfilehash: f12d538b1f4cd327b893d234f2b558185cdd9d85
ms.lasthandoff: 03/09/2017

---

# <a name="add-corporate-identifiers"></a>Dodawanie identyfikatorów firmy

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Do identyfikowania urządzeń firmy można utworzyć listę numerów IMEI (International Mobile Equipment Identity). Urządzenia te mogą być zarejestrowane lub nie, a ich stan ma wartość „Zarejestrowane” lub „Nie kontaktowano się”. „Nie kontaktowano się” oznacza, że urządzenie nie zostało nigdy zaewidencjonowane w usłudze Intune.

Aby utworzyć listę, utwórz listę wartości rozdzielonych przecinkami (.csv) zawierającą dwie kolumny, bez nagłówka. Dodaj identyfikator IMEI w lewej kolumnie i szczegółowe informacje w prawej kolumnie. Obecnie maksymalna liczba wierszy na liście wynosi 500.

W edytorze tekstu lista .csv wygląda następująco:

01 234567 890123, szczegóły urządzenia</br>
02 234567 890123, szczegóły urządzenia

**Aby dodać listę .csv identyfikatorów firmy**

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku Intune wybierz kolejno pozycje **Zarejestruj urządzenia** i **Identyfikatory urządzenia firmy**.

3. Jeśli importujesz plik z nowymi szczegółami, które zastąpią istniejące, wybierz opcję **Zastąp szczegóły istniejących identyfikatorów**, aby nowe szczegóły zastąpiły istniejące.

4. Przejdź do pliku CSV IMEI i wybierz przycisk **Dodaj**.

> [!IMPORTANT]
> Niektóre urządzenia z systemem Android mają wiele numerów IMEI. Usługa Intune rejestruje w spisie po jednym numerze IMEI na urządzenie. Jeśli zostanie zaimportowany numer IMEI inny niż numer zarejestrowany w spisie usługi Intune, urządzenie zostanie zaklasyfikowane jako urządzenie osobiste, a nie należące do firmy. Zaimportowanie wielu numerów IMEI urządzenia spowoduje, że dla numerów niezarejestrowanych w spisie będzie wyświetlany stan rejestracji **Nieznany**.

**Aby usunąć listę .csv identyfikatorów firmy**

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku Intune wybierz kolejno pozycje **Zarejestruj urządzenia** i **Identyfikatory urządzenia firmy**.

3. Wybierz przycisk **Usuń**.

