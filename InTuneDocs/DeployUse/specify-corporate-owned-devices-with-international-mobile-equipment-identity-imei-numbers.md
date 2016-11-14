---
title: "Określanie numerów IMEI | Microsoft Intune"
description: "Usługa Microsoft Intune umożliwia administratorom importowanie numerów IMEI dla platform urządzeń przenośnych w celu ułatwienia identyfikacji firmowych urządzeń przenośnych"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c6b01a5efc0f60622b95623fd91f192c267ff766
ms.openlocfilehash: 9bd2b4bb676e23712c0a668161b81c4e352bce87


---

# Określanie urządzeń należących do firmy z międzynarodowymi numerami identyfikującymi urządzenia przenośne (IMEI, International Mobile Equipment Identity)
Usługa Microsoft Intune umożliwia administratorom importowanie międzynarodowych numerów identyfikujących urządzenia przenośne (IMEI) dla platform urządzeń przenośnych za pomocą numerów IMEI, co ułatwia identyfikację firmowych urządzeń przenośnych. Po zarejestrowaniu urządzeń w usłudze Intune w obszarze **Grupy** > **Przegląd** > **Wszystkie urządzenia** zobaczysz urządzenia z zaimportowanymi numerami IMEI. W obszarze **Grupa urządzeń** widoczne są urządzenia z zaimportowanymi numerami IMEI wyświetlanymi jako **Firmowe** w kolumnie **Własność**.

1. W [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) wybierz kolejno pozycje **Grupy** &gt; **Wszystkie urządzenia** &gt; **Wszystkie wstępnie zarejestrowane urządzenia należące do firmy** &gt; **Według numeru IMEI (wszystkie platformy)**, a następnie wybierz polecenie **Dodaj urządzenia**. Urządzenia można dodać na dwa sposoby:

    -   **Przekaż plik csv zawierający numery seryjne** — utwórz listę wartości rozdzielanych przecinkami (csv) w dwóch kolumnach bez nagłówka i ogranicz listę do 5000 urządzeń lub 5 MB na plik csv.

        |||
        |-|-|
        |&lt;KOD IMEI 1&gt;|&lt;Szczegóły urządzenia 1&gt;|
        |&lt;KOD IMEI 2&gt;|&lt;Szczegóły urządzenia 2&gt;|
        Ten plik CSV wyświetlony w edytorze tekstu wygląda następująco:

        ```
        AABBBBBBCCCCCCD,PO 1234
        AABBBBBBCCCCCCE,PO 1234
        ```

    -   **Ręcznie dodaj szczegóły urządzeń** — wprowadź numery IMEI i szczegóły maksymalnie pięciu urządzeń.

   *Szczegóły* są przeznaczone do użytku administracyjnego, dzięki czemu można zidentyfikować numer IMEI skojarzony z urządzeniem. Te informacje nie są wysyłane do urządzenia, ale będą wyświetlane w konsoli usługi Intune.

2.   Wybierz pozycję **Next** (Dalej).
3.  W okienku **Przegląd urządzeń** możesz potwierdzić zaimportowane numery IMEI urządzenia. Możesz również wybrać, czy zastąpić wartość pola **Szczegóły** dla ponownie importowanych numerów IMEI. Możesz usunąć zaznaczenie pola **Zastąp**, aby zachować bieżące szczegóły. Wybierz przycisk **Zakończ**, aby zaimportować numery IMEI.
4.  Zaimportowane numery IMEI i opisy są dodawane do listy **Według numeru IMEI (wszystkie platformy)**.

Podczas rejestrowania urządzenia z numerem IMEI w usłudze Intune — zwykle gdy użytkownik instaluje aplikację Portal firmy i kończy proces rejestracji — urządzenie zostanie oznaczone jako należące do firmy i będzie wyświetlane jako zarejestrowane w grupie **Urządzenia IMEI**.



<!--HONumber=Oct16_HO3-->


