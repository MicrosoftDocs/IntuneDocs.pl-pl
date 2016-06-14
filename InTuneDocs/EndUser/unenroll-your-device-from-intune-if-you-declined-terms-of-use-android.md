---
# required metadata

title: Wyrejestrowywanie urządzenia z usługi Intune w przypadku odrzucenia warunków użytkowania | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4278f000-0258-4de5-93a1-195b48e5061e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Wyrejestrowywanie urządzenia z usługi Intune w przypadku odrzucenia warunków użytkowania

Najlepszym sposobem wyrejestrowania urządzenia z systemem Android jest zaakceptowanie warunków użytkowania, zalogowanie się w aplikacji Portal firmy, a następnie wyrejestrowanie zgodnie z [tymi instrukcjami](unenroll-your-device-from-intune-android.md). Jeśli jednak odrzucisz warunki użytkowania podczas próby zalogowania się w aplikacji Portal firmy, utracisz możliwość zalogowania się w aplikacji Portal firmy w przypadku ponownych prób w przyszłości, dlatego musisz wyrejestrować swoje urządzenie przy użyciu tych instrukcji umożliwiających „obejście” tego problemu.

Odinstalowanie aplikacji Portal firmy powoduje również wyrejestrowanie urządzenia z usługi Intune, co oznacza, że urządzenie nie może uzyskiwać dostępu do zasobów firmy.  Aby uzyskać więcej informacji o tym, co się stanie po wyrejestrowaniu, zobacz [Co się stanie w przypadku wyrejestrowania urządzenia z usługi Intune?](what-happens-if-you-unenroll-your-device-from-intune-android.md)..

Przed odinstalowaniem aplikacji Portal firmy musisz przejść do ustawienia **Administratorzy urządzenia** i wyłączyć **Portal firmy**. W zależności od posiadanego urządzenia z systemem Android poniższe kroki mogą się nieco różnić.

Aby wyrejestrować urządzenie z usługi Intune i odinstalować aplikację Portal firmy:

1.  Przejdź do pozycji **Ustawienia** &gt; **Zabezpieczenia&amp;Blokada ekranu** &gt; **Administratorzy urządzenia**..

    Wykonanie tego kroku powoduje natychmiastowe wyrejestrowanie urządzenia.

2.  Wyczyść pole wyboru obok pozycji **Portal firmy** lub wyłącz ją..

    Teraz możesz odinstalować aplikację Portal firmy.


### Zobacz także
[Korzystanie z urządzenia z systemem Android i usługi Intune](using-your-android-device-with-intune.md)

<!--HONumber=May16_HO1-->


