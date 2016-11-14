---
title: Unenroll your device from Intune if you declined "Terms of Use" | Microsoft Intune
description: "Zawiera opis sposobu wyrejestrowania urządzenia z systemem Android z usługi Intune, jeśli odrzucono warunki użytkowania i nie można zalogować się do aplikacji Portal firmy"
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4278f000-0258-4de5-93a1-195b48e5061e
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0d32aa982cf9d45da36f71be5554f31375521e35
ms.openlocfilehash: 4f5088bc645fed0451885078f5ab0dcd04a33d81


---


# Wyrejestrowywanie urządzenia z usługi Intune w przypadku odrzucenia warunków użytkowania

Najlepszym sposobem wyrejestrowania urządzenia z systemem Android jest zaakceptowanie warunków użytkowania, zalogowanie się w aplikacji Portal firmy, a następnie wyrejestrowanie zgodnie z [tymi instrukcjami](unenroll-your-device-from-intune-android.md). Jeśli jednak odrzucisz warunki użytkowania podczas próby zalogowania się w aplikacji Portal firmy, utracisz możliwość zalogowania się w aplikacji Portal firmy w przypadku ponownych prób w przyszłości. W takiej sytuacji skorzystaj z tych instrukcji umożliwiających „obejście” tego problemu i wyrejestrowanie urządzenia.

Odinstalowanie aplikacji Portal firmy powoduje także wyrejestrowanie danego urządzenia z usługi Intune. Urządzenie nie będzie już mogło uzyskiwać dostępu do zasobów firmy. Aby uzyskać więcej informacji o tym, co się stanie po wyrejestrowaniu, zobacz [Co się stanie w przypadku wyrejestrowania urządzenia z usługi Intune?](what-happens-if-you-unenroll-your-device-from-intune-android.md).

Przed odinstalowaniem aplikacji Portal firmy musisz przejść do ustawienia **Administratorzy urządzenia** i wyłączyć **Portal firmy**. W zależności od posiadanego urządzenia z systemem Android poniższe kroki mogą się nieco różnić.

Aby wyrejestrować urządzenie z usługi Intune i odinstalować aplikację Portal firmy:

1.  Przejdź do pozycji **Ustawienia** &gt; **Zabezpieczenia &amp; Blokada ekranu** &gt; **Administratorzy urządzenia**.

    Wykonanie tego kroku powoduje natychmiastowe wyrejestrowanie urządzenia.

2.  Wyczyść pole wyboru obok pozycji **Portal firmy** lub wyłącz ją.

    Teraz możesz odinstalować aplikację Portal firmy.

Nadal potrzebujesz pomocy? Skontaktuj się z administratorem IT (sprawdź [witrynę sieci Web Portal firmy](http://portal.manage.microsoft.com), aby uzyskać informacje kontaktowe) lub napisz do zespołu ds. systemu Android firmy Microsoft: wintunedroidfbk@microsoft.com.



<!--HONumber=Oct16_HO2-->


