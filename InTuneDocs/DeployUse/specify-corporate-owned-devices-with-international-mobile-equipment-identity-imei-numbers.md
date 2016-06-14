---
# required metadata

title: Określanie urządzeń należących do firmy z międzynarodowymi numerami identyfikującymi urządzenia przenośne (IMEI, International Mobile Equipment Identity) | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Określanie urządzeń należących do firmy z międzynarodowymi numerami identyfikującymi urządzenia przenośne (IMEI, International Mobile Equipment Identity)
Usługa Microsoft Intune umożliwia administratorom importowanie międzynarodowych numerów identyfikujących urządzenia przenośne (IMEI) dla platform urządzeń przenośnych, które mają numery IMEI, co ułatwia identyfikację firmowych urządzeń przenośnych. Zarejestrowane w usłudze Intune urządzenia z numerami IMEI oznaczone jako firmowe, co jest użyteczne w przypadku stosowania strategii innych niż względem urządzeń prywatnych.

1. W [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) przejdź kolejno do pozycji **Grupy** &gt; **Wszystkie urządzenia** &gt; **Wszystkie urządzenia zarejestrowane wstępnie należące do firmy** &gt; **Według numeru IMEI (wszystkie platformy)**, a następnie kliknij pozycję **Dodaj urządzenia**. Urządzenia można dodać na dwa sposoby:

    -   **Przekaż plik CSV zawierający numery seryjne** — utwórz listę wartości oddzielanych przecinkami (plik csv) w dwóch kolumnach bez nagłówka ograniczoną do 5000 urządzeń lub 5 MB na plik CSV.

        |||
        |-|-|
        |&lt;KOD IMEI 1&gt;|&lt;Szczegóły urządzenia 1&gt;|
        |&lt;KOD IMEI 2&gt;|&lt;Szczegóły urządzenia 2&gt;|
        Ten plik CSV wyświetlony w edytorze tekstu wygląda następująco:

        ```
        AA-BBBBBB-CCCCCC-D,PO 1234
        AA-BBBBBB-CCCCCC-E,PO 1234
        ```

    -   **Ręcznie dodaj szczegóły urządzeń** — wprowadź numery IMEI i szczegóły maksymalnie pięciu urządzeń.

   *Szczegóły* są przeznaczone do użytku administracyjnego, dzięki czemu można zidentyfikować numer IMEI skojarzony z urządzeniem. Te informacje nie są wysyłane do urządzenia, ale będą wyświetlane w konsoli usługi Intune.

2.   Kliknij przycisk **Dalej**..
3.  W okienku **Przegląd urządzeń** możesz potwierdzić, które numery IMEI urządzenia są importowane. Możesz również wybrać, czy zastąpić wartość pola **Szczegóły** dla ponownie importowanych numerów IMEI. Możesz usunąć zaznaczenie pola wyboru **Zastąp**, aby zachować bieżące szczegóły. Kliknij przycisk **Zakończ**, aby zaimportować numery IMEI.
4.  Numery IMEI i opisy są dodawane do listy **Według numeru IMEI (wszystkie platformy)**.

Podczas rejestrowania urządzenia z tym numerem IMEI — przeważnie gdy użytkownik instaluje aplikację Portal firmy i kończy proces rejestracji — urządzenie zostanie oznaczone jako należące do firmy i będzie wyświetlane jako zarejestrowane w grupie **Urządzenia IMEI**.


<!--HONumber=May16_HO1-->


