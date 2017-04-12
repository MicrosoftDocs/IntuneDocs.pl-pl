---
title: "Wyrejestrowywanie urządzenia w przypadku odrzucenia warunków użytkowania | Dokumentacja firmy Microsoft"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4278f000-0258-4de5-93a1-195b48e5061e
searchScope:
- User help
ROBOTS: 
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: 1ba0dab35e0da6cfe744314a4935221a206fcea7
ms.openlocfilehash: b99ce8b30e25960e09e39b81f0f58aa09af2affa
ms.lasthandoff: 03/13/2017


---


# <a name="unenroll-your-device-if-you-declined-terms-of-use"></a>Wyrejestrowywanie urządzenia w przypadku odrzucenia warunków użytkowania

Najlepszym sposobem wyrejestrowania urządzenia z systemem Android jest zaakceptowanie warunków użytkowania, zalogowanie się w aplikacji Portal firmy, a następnie wyrejestrowanie zgodnie z [tymi instrukcjami](unenroll-your-device-from-intune-android.md). Jeśli jednak odrzucisz warunki użytkowania podczas próby zalogowania się w aplikacji Portal firmy, utracisz możliwość zalogowania się w aplikacji Portal firmy w przypadku ponownych prób w przyszłości, dlatego musisz wyrejestrować swoje urządzenie przy użyciu tych instrukcji umożliwiających „obejście” tego problemu.

Odinstalowanie aplikacji Portal firmy powoduje także wyrejestrowanie danego urządzenia z usługi Intune. Urządzenie nie będzie już mogło uzyskiwać dostępu do zasobów firmy. Aby uzyskać więcej informacji o tym, co się stanie po wyrejestrowaniu, zobacz [Co się stanie w przypadku wyrejestrowania urządzenia z usługi Intune?](what-happens-if-you-unenroll-your-device-from-intune-android.md).

Przed odinstalowaniem aplikacji Portal firmy musisz przejść do ustawienia **Administratorzy urządzenia** i wyłączyć **Portal firmy**. W zależności od posiadanego urządzenia z systemem Android poniższe kroki mogą się nieco różnić.

Aby wyrejestrować urządzenie z usługi Intune i odinstalować aplikację Portal firmy:

1.  Przejdź do pozycji **Ustawienia** &gt; **Zabezpieczenia &amp; Blokada ekranu** &gt; **Administratorzy urządzenia**.

    Wykonanie tego kroku powoduje natychmiastowe wyrejestrowanie urządzenia.

2.  Wyczyść pole wyboru obok pozycji **Portal firmy** lub wyłącz ją.

    Teraz możesz odinstalować aplikację Portal firmy.

Nadal potrzebujesz pomocy? Skontaktuj się z administratorem IT (sprawdź [witrynę sieci Web Portal firmy](http://portal.manage.microsoft.com), aby uzyskać informacje kontaktowe) lub napisz do <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having unenrolling my Android device&body=Describe the issue you're experiencing here.">zespołu ds. systemu Android firmy Microsoft</a>.

