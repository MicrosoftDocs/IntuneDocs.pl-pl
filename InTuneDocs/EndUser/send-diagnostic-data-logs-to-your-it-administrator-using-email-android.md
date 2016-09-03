---
title: "Wysyłanie dzienników danych diagnostycznych do administratora IT za pomocą poczty e-mail | Microsoft Intune"
description: 
keywords: 
author: staciebarker
manager: angrobe
ms.date: 05/31/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 85c868e7-8d63-480c-9770-4e99614a5c94
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d3a2daebdb781ce99aa103e7717ffa1b0297cb3a
ms.openlocfilehash: 7e90141f08cf029a005aad1ae0501fc1962eb958


---


# Wysyłanie dzienników danych diagnostycznych do administratora IT za pomocą poczty e-mail

Jeśli na urządzeniu z systemem Android wystąpi błąd podczas pracy z aplikacjami firmowymi lub szkolnymi albo podczas pracy w aplikacji Portal firmy, możesz wysłać dzienniki danych diagnostycznych, aby pomóc administratorowi IT rozpoznać i usunąć błąd. Aby uwzględnić w dziennikach diagnostycznych wszystkie szczegóły, które ułatwią administratorowi IT ustalenie problemu, włącz ustawienie Pełne rejestrowanie. Przeczytaj więcej na temat [pełnego rejestrowania](use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android.md).

Aby włączyć pełne rejestrowanie:

1.  Otwórz aplikację Portal firmy.

2.  Naciśnij kolejno pozycje **Menu** &gt; **Ustawienia**.

    > [!NOTE]
    > Przycisk **Menu** może być przyciskiem programowym lub sprzętowym, w zależności od posiadanego urządzenia z systemem Android.

3.  W obszarze **Dane diagnostyczne** naciśnij przycisk **Wyślij dane**.

    > [!NOTE]
    > **Tylko w przypadku korzystania z urządzeń z systemem Android 6.0 lub nowszym:** Po naciśnięciu przycisku **Wyślij dane** zostanie wyświetlony komunikat **Zezwolić aplikacji Portal firmy na dostęp do zdjęć, multimediów i plików na Twoim urządzeniu?**.

    Ten komunikat jest mylący, ponieważ **firma Microsoft nigdy nie próbuje uzyskać dostępu do zdjęć, multimediów ani plików na Twoim urządzeniu!** Tekst komunikatu pochodzi od firmy Google, a firma Microsoft nie może go zmienić.  Zezwalając na dostęp, umożliwiasz urządzeniu tylko zapisywanie dzienników danych na karcie SD urządzenia, co pozwala na przenoszenie tych dzienników przy użyciu kabla USB.

    Jeśli odmówisz dostępu, komunikat pojawi się ponownie przy kolejnym naciśnięciu przycisku **Wyślij dane**, ale możesz wyłączyć wyświetlanie komunikatów w przyszłości, zaznaczając pole wyboru **Nigdy nie pytaj ponownie**.  Jeśli później zdecydujesz zezwolić na dostęp, przejdź do pozycji **Ustawienia** &gt; **Aplikacje** &gt; **Portal firmy** &gt; **Uprawnienia** &gt; **Magazyn** i włącz uprawnienie.

4.  Postępuj zgodnie z monitami, aby wybrać aplikację poczty e-mail na potrzeby wysyłania dzienników do administratora IT. Aplikacja utworzy wstępnie zaadresowane wiadomości e-mail z dołączonymi wszystkimi dziennikami.


### Zobacz także
[Korzystanie z urządzenia z systemem Android i usługi Intune](using-your-android-device-with-intune.md)



<!--HONumber=Aug16_HO4-->


