---
# required metadata

title: Wysyłanie dzienników danych diagnostycznych do administratora IT za pomocą poczty e-mail | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 85c868e7-8d63-480c-9770-4e99614a5c94

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: arnab
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Wysyłanie dzienników danych diagnostycznych do administratora IT za pomocą poczty e-mail

Jeśli na urządzeniu z systemem Android wystąpi błąd podczas pracy z aplikacjami firmowymi lub szkolnymi albo podczas pracy w aplikacji Portal firmy, możesz wysłać dzienniki danych diagnostycznych, aby pomóc administratorowi IT rozpoznać i usunąć błąd. Aby uwzględnić w dziennikach diagnostycznych wszystkie szczegóły, które ułatwią administratorowi IT ustalenie problemu, włącz ustawienie Pełne rejestrowanie.

Aby włączyć pełne rejestrowanie:

1.  Otwórz aplikację Portal firmy.

2.  Naciśnij kolejno pozycje **Menu** &gt; **Ustawienia**.

    > [!NOTE] 
    > Przycisk**Menu** może być przyciskiem programowym lub sprzętowym w zależności od posiadanego urządzenia z systemem Android.

3.  W obszarze **Dane diagnostyczne** naciśnij przycisk **Wyślij dane**.

    > [!NOTE]
    > **Tylko w przypadku korzystania z urządzeń z systemem Android 6.0 lub nowszym:** po naciśnięciu przycisku **Wyślij dane** zostanie wyświetlony komunikat **Zezwolić aplikacji Portal firmy na dostęp do zdjęć, multimediów i plików na Twoim urządzeniu?**. 

    Ten komunikat jest mylący, ponieważ **firma Microsoft nigdy nie próbuje uzyskać dostępu do zdjęć, multimediów ani plików na Twoim urządzeniu!** Tekst komunikatu pochodzi od firmy Google, a firma Microsoft nie może go zmienić.  Zezwalając na dostęp, umożliwiasz urządzeniu tylko zapisywanie dzienników danych na karcie SD urządzenia, co pozwala na przenoszenie tych dzienników przy użyciu kabla USB.

    Jeśli odmówisz dostępu, komunikat pojawi się ponownie przy kolejnym naciśnięciu przycisku **Wyślij dane**, ale możesz wyłączyć wyświetlanie komunikatów w przyszłości, zaznaczając pole wyboru **Nigdy nie pytaj ponownie**.  Jeśli później zdecydujesz zezwolić na dostęp, przejdź do pozycji **Ustawienia** &gt; **Aplikacje** &gt; **Portal firmy** &gt; **Uprawnienia** &gt; **Magazyn** i włącz uprawnienie.

4.  Postępuj zgodnie z monitami, aby wybrać aplikację poczty e-mail na potrzeby wysyłania dzienników do administratora IT. Aplikacja utworzy wstępnie zaadresowane wiadomości e-mail z dołączonymi wszystkimi dziennikami.


### Zobacz także
[Korzystanie z urządzenia z systemem Android i usługi Intune](using-your-android-device-with-intune.md)

<!--HONumber=Jun16_HO1-->


