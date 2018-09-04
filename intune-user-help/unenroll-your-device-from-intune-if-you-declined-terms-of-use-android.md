---
title: Usuwanie urządzenia z zarządzania w przypadku odrzucenia warunków użytkowania | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4278f000-0258-4de5-93a1-195b48e5061e
searchScope:
- User help
ROBOTS: ''
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 24aa876b7100f0f802ab3723cedf92a32bc7e9d7
ms.sourcegitcommit: 490365fb8b5405f323b4358fb1ec9dfdd9ff2d58
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/29/2018
ms.locfileid: "43149711"
---
# <a name="remove-your-device-from-management-if-you-declined-terms-of-use"></a>Usuwanie urządzenia z zarządzania w przypadku odrzucenia warunków użytkowania

Jeśli odrzucisz warunki użytkowania podczas próby zalogowania się w aplikacji Portal firmy, utracisz możliwość zalogowania się w aplikacji Portal firmy w przypadku ponownych prób w przyszłości, dlatego musisz usunąć swoje urządzenie z usługi Intune przy użyciu tych instrukcji umożliwiających „obejście” tego problemu.

Odinstalowanie aplikacji Portal firmy powoduje także usunięcie danego urządzenia z usługi Intune. Urządzenie nie będzie już mogło uzyskiwać dostępu do zasobów firmy. Aby uzyskać więcej informacji o tym, co się stanie po usunięciu urządzenia z zarządzania, zobacz [Co się stanie w przypadku wyrejestrowania urządzenia z usługi Intune?](what-happens-if-you-unenroll-your-device-from-intune-android.md).

Przed odinstalowaniem aplikacji Portal firmy musisz przejść do ustawienia **Administratorzy urządzenia** i wyłączyć **Portal firmy**. W zależności od posiadanego urządzenia z systemem Android poniższe kroki mogą się nieco różnić.

## <a name="removing-the-device-from-the-company-portal-app"></a>Usuwanie urządzenia przy użyciu aplikacji Portal firmy

Aby usunąć urządzenie z usługi Intune i odinstalować aplikację Portal firmy:

1.  Przejdź do pozycji **Ustawienia** &gt; **Zabezpieczenia &amp; Blokada ekranu** &gt; **Administratorzy urządzenia**.

    Wykonanie tego kroku powoduje natychmiastowe wyrejestrowanie urządzenia.

2.  Wyczyść pole wyboru obok pozycji **Portal firmy** lub wyłącz ją.

    Teraz możesz odinstalować aplikację Portal firmy.

## <a name="removing-data-collected-by-the-company-portal-app"></a>Usuwanie danych zebranych przez aplikację Portal firmy

Aby usunąć wszystkie dane przechowywane przez aplikację Portal firmy dla systemu Android z urządzenia:

  - Wyczyść dane aplikacji: przejdź do obszaru Aplikacje, a następnie kliknij aplikację i przycisk „Wyczyść dane”
  - Usuń folder „\storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal”


Nadal potrzebujesz pomocy? Skontaktuj się z działem pomocy technicznej Twojej firmy (sprawdź [witrynę internetową Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980), aby uzyskać informacje kontaktowe) lub napisz do <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having unenrolling my Android device&body=Describe the issue you're experiencing here.">zespołu ds. systemu Android w firmie Microsoft</a>.
