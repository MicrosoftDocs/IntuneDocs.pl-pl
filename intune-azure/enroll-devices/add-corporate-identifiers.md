---
title: "Dodawanie identyfikatorów IMEI do usługi Intune | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące dodawania identyfikatorów firmy (numerów IMEI) do usługi Microsoft Intune. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: 8667f063de65fd5fa86149ac124b236a432eecef

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

**Aby usunąć listę .csv identyfikatorów firmy**

1. W witrynie Azure Portal wybierz pozycję **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.

2. W bloku Intune wybierz kolejno pozycje **Zarejestruj urządzenia** i **Identyfikatory urządzenia firmy**.

3. Wybierz przycisk **Usuń**.



<!--HONumber=Feb17_HO3-->


