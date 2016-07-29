---
title: "Wyrejestrowywanie urządzenia z usługi Intune w przypadku odrzucenia warunków użytkowania | Microsoft Intune"
description: "Zawiera opis sposobu wyrejestrowania urządzenia z systemem Android z usługi Intune, jeśli odrzucono warunki użytkowania i nie można zalogować się do aplikacji Portal firmy"
keywords: 
author: staciebarker
manager: arob98
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4278f000-0258-4de5-93a1-195b48e5061e
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 376e6c1ae229187ab8ec73390f091f1d534365dd
ms.openlocfilehash: 06e2fa597e9e4143d17e817daee7eeac8eb46bf7


---


# Wyrejestrowywanie urządzenia z usługi Intune w przypadku odrzucenia warunków użytkowania

Najlepszym sposobem wyrejestrowania urządzenia z systemem Android jest zaakceptowanie warunków użytkowania, zalogowanie się w aplikacji Portal firmy, a następnie wyrejestrowanie zgodnie z [tymi instrukcjami](unenroll-your-device-from-intune-android.md). Jeśli jednak odrzucisz warunki użytkowania podczas próby zalogowania się w aplikacji Portal firmy, utracisz możliwość zalogowania się w aplikacji Portal firmy w przypadku ponownych prób w przyszłości, dlatego musisz wyrejestrować swoje urządzenie przy użyciu tych instrukcji umożliwiających „obejście” tego problemu.

Odinstalowanie aplikacji Portal firmy powoduje również wyrejestrowanie urządzenia z usługi Intune, co oznacza, że urządzenie nie może uzyskiwać dostępu do zasobów firmy.  Aby uzyskać więcej informacji o tym, co się stanie po wyrejestrowaniu, zobacz [Co się stanie w przypadku wyrejestrowania urządzenia z usługi Intune?](what-happens-if-you-unenroll-your-device-from-intune-android.md).

Przed odinstalowaniem aplikacji Portal firmy musisz przejść do ustawienia **Administratorzy urządzenia** i wyłączyć **Portal firmy**. W zależności od posiadanego urządzenia z systemem Android poniższe kroki mogą się nieco różnić.

Aby wyrejestrować urządzenie z usługi Intune i odinstalować aplikację Portal firmy:

1.  Przejdź do pozycji **Ustawienia** &gt; **Zabezpieczenia &amp; Blokada ekranu** &gt; **Administratorzy urządzenia**.

    Wykonanie tego kroku powoduje natychmiastowe wyrejestrowanie urządzenia.

2.  Wyczyść pole wyboru obok pozycji **Portal firmy** lub wyłącz ją.

    Teraz możesz odinstalować aplikację Portal firmy.

Nadal potrzebujesz pomocy? Skontaktuj się z administratorem IT (sprawdź [witrynę sieci Web Portal firmy](http://portal.manage.microsoft.com), aby uzyskać informacje kontaktowe) lub napisz do zespołu ds. systemu Android firmy Microsoft: wintunedroidfbk@microsoft.com.


### Zobacz także
[Korzystanie z urządzenia z systemem Android i usługi Intune](using-your-android-device-with-intune.md)


<!--HONumber=Jul16_HO3-->


