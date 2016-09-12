---
title: "Określanie numerów IMEI | Microsoft Intune"
description: "Usługa Microsoft Intune umożliwia administratorom importowanie numerów IMEI dla platform urządzeń przenośnych w celu ułatwienia identyfikacji firmowych urządzeń przenośnych"
keywords: 
author: NathBarn
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
ms.sourcegitcommit: e9cbf5858cc4e860b540f421b6d463b8e7a429cf
ms.openlocfilehash: 4e2092182dbda4523c19afeabc34aa0166962c40


---

# Określanie urządzeń należących do firmy z międzynarodowymi numerami identyfikującymi urządzenia przenośne (IMEI, International Mobile Equipment Identity)
Usługa Microsoft Intune umożliwia administratorom importowanie międzynarodowych numerów identyfikujących urządzenia przenośne (IMEI) dla platform urządzeń przenośnych, które mają numery IMEI, co ułatwia identyfikację firmowych urządzeń przenośnych. Po zarejestrowaniu w usłudze Intune urządzenia z zaimportowanymi numerami IMEI można przeglądać w obszarze **Grupy** > **Przegląd** > **Wszystkie urządzenia**. Na listach w obszarze **Grupa urządzeń** urządzenia z zaimportowanymi numerami IMEI są wyświetlane jako **Firmowe** w kolumnie **Własność**.

1. W [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) wybierz kolejno pozycje **Grupy** &gt; **Wszystkie urządzenia** &gt; **Wszystkie wstępnie zarejestrowane urządzenia należące do firmy** &gt; **Według numeru IMEI (wszystkie platformy)**, a następnie wybierz pozycję **Dodaj urządzenia**. Urządzenia można dodać na dwa sposoby:

    -   **Przekaż plik CSV zawierający numery seryjne** — utwórz listę wartości oddzielanych przecinkami (plik csv) w dwóch kolumnach bez nagłówka ograniczoną do 5000 urządzeń lub 5 MB na plik CSV.

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
3.  W okienku **Przegląd urządzeń** możesz potwierdzić, które numery IMEI urządzenia są importowane. Możesz również wybrać, czy zastąpić wartość pola **Szczegóły** dla ponownie importowanych numerów IMEI. Możesz usunąć zaznaczenie pola wyboru **Zastąp**, aby zachować bieżące szczegóły. Wybierz przycisk **Zakończ**, aby zaimportować numery IMEI.
4.  Numery IMEI i opisy są dodawane do listy **Według numeru IMEI (wszystkie platformy)**.

Podczas rejestrowania urządzenia z tym numerem IMEI — przeważnie gdy użytkownik instaluje aplikację Portal firmy i kończy proces rejestracji — urządzenie zostanie oznaczone jako należące do firmy i będzie wyświetlane jako zarejestrowane w grupie **Urządzenia IMEI**.



<!--HONumber=Jul16_HO4-->


