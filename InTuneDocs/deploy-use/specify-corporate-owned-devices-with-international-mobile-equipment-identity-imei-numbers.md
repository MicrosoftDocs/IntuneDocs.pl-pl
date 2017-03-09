---
title: "Określanie numerów IMEI | Microsoft Docs"
description: "Usługa Microsoft Intune umożliwia administratorom importowanie numerów IMEI dla platform urządzeń przenośnych w celu ułatwienia identyfikacji firmowych urządzeń przenośnych"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 51f9d7bad6a1411ff68fa94c62421e2c0a43ab5a
ms.openlocfilehash: 97bedfdd2d756ae79350496f54076c16ada64def
ms.lasthandoff: 02/25/2017


---

# <a name="specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers"></a>Określanie urządzeń należących do firmy z międzynarodowymi numerami identyfikującymi urządzenia przenośne (IMEI, International Mobile Equipment Identity)

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Usługa Microsoft Intune umożliwia administratorom importowanie międzynarodowych numerów identyfikujących urządzenia przenośne (IMEI) dla platform urządzeń przenośnych za pomocą numerów IMEI, co ułatwia identyfikację firmowych urządzeń przenośnych. Po zarejestrowaniu urządzeń w usłudze Intune w obszarze **Grupy** > **Przegląd** > **Wszystkie urządzenia** zobaczysz urządzenia z zaimportowanymi numerami IMEI. W obszarze **Grupa urządzeń** widoczne są urządzenia z zaimportowanymi numerami IMEI wyświetlanymi jako **Firmowe** w kolumnie **Własność**.

1. W [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) wybierz kolejno pozycje **Grupy** &gt; **Wszystkie urządzenia** &gt; **Wszystkie wstępnie zarejestrowane urządzenia należące do firmy** &gt; **Według numeru IMEI (wszystkie platformy)**, a następnie wybierz polecenie **Dodaj urządzenia**. Urządzenia można dodać na dwa sposoby:

    -   **Przekaż plik csv zawierający numery seryjne** — utwórz listę wartości rozdzielanych przecinkami (csv) w dwóch kolumnach bez nagłówka i ogranicz listę do 5000 urządzeń lub 5 MB na plik csv.

        |||
        |-|-|
        |&lt;IMEI 1&gt;|&lt;Szczegóły urządzenia 1&gt;|
        |&lt;IMEI 2&gt;|&lt;Szczegóły urządzenia 2&gt;|
        Ten plik CSV wyświetlony w edytorze tekstu wygląda następująco:

        ```
        AABBBBBBCCCCCCD,PO 1234
        AABBBBBBCCCCCCE,PO 1234
        ```

    -   **Ręcznie dodaj szczegóły urządzeń** — wprowadź numery IMEI i szczegóły maksymalnie 15 urządzeń.

   Pole *Szczegóły* jest przeznaczone do użytku administracyjnego. Możesz określić szczegóły, aby pomóc w zidentyfikowaniu urządzenia na liście należących do firmy urządzeń wymienionych według identyfikatora sprzętu. Te informacje nie są wysyłane do urządzenia, ale będą wyświetlane w konsoli usługi Intune.

2.   Wybierz pozycję **Next** (Dalej).
3.  W okienku **Przegląd urządzeń** możesz potwierdzić zaimportowane numery IMEI urządzenia. Możesz również wybrać, czy zastąpić wartość pola **Szczegóły** dla ponownie importowanych numerów IMEI. Możesz usunąć zaznaczenie pola **Zastąp**, aby zachować bieżące szczegóły. Wybierz przycisk **Zakończ**, aby zaimportować numery IMEI.
4.  Zaimportowane numery IMEI i opisy są dodawane do listy **Według numeru IMEI (wszystkie platformy)**.

> [!IMPORTANT]
> W przypadku importowania numerów IMEI dla urządzeń z systemem Android należy pamiętać, że niektóre urządzenia z systemem Android mogą mieć wiele numerów IMEI. Jeśli zostanie zaimportowany numer IMEI inny niż numer zgłoszony przez urządzenie w usłudze IMEI, urządzenie zostanie zaklasyfikowane jako urządzenie osobiste, a nie należące do firmy.

Podczas rejestrowania urządzenia z numerem IMEI w usłudze Intune — zwykle gdy użytkownik instaluje aplikację Portal firmy i kończy proces rejestracji — urządzenie zostanie oznaczone jako należące do firmy i będzie wyświetlane jako zarejestrowane w grupie **Urządzenia IMEI**.

>[!NOTE]
> Jeśli w najbliższej przyszłości dana organizacja zostanie poddana migracji do nowej witryny Azure Portal, ta funkcja ulegnie zmianie. W istniejącej konsoli administratora usługi Intune administratorzy mogą akceptować szczegóły z przekazanego pliku CSV i zastępować istniejące dane poszczególnych identyfikatorów sprzętu. W nowej wersji witryny Azure Portal będzie można automatycznie zastąpić szczegóły wszystkich identyfikatorów sprzętu lub zignorować wszystkie nowe szczegóły istniejących identyfikatorów.

