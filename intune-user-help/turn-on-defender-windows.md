---
title: Włączanie usługi Windows Defender | Microsoft Docs
description: Dowiedz się, jak włączyć usługę Windows Defender, aby uzyskać dostęp do zasobów firmy.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 11/08/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d16dd2de-3ed5-474f-a04b-36dcd350162c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: shburbid
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 9190282edb8d356d7d43a634d10991a4b4c19c16
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31018502"
---
# <a name="turn-on-windows-defender-to-access-company-resources"></a>Włączanie usługi Windows Defender w celu uzyskiwania dostępu do zasobów firmy

Administrator Twojego konta służbowego chce mieć pewność, że urządzenia uzyskujące dostęp do jego zasobów są zabezpieczone. Istnieje kilka sposobów wykorzystania w tym celu usługi [Windows Defender](https://www.microsoft.com/safety/pc-security/windows-defender.aspx) — wbudowanej ochrony systemu Windows przed złośliwym oprogramowaniem.

Istnieje parę ustawień, które być może musisz zmienić w Twoim systemie Windows Defender, aby rozwiązać problemy dotyczące dostępu. Te kroki mogą wymagać przejścia do różnych miejsc na Twoim komputerze.

## <a name="turn-on-windows-defender"></a>Włączanie usługi Windows Defender

1. W menu **Start** otwórz **Panel sterowania**.
2. Otwórz **Narzędzia administracyjne** > **Edytuj zasady grupy**. Spowoduje to otwarcie **Edytora lokalnych zasad grupy** w nowym oknie.
3. Otwórz kolejno pozycje **Konfiguracja komputera** > **Szablony administracyjne** > **Składniki systemu Windows** > **Windows Defender Antivirus**. Ustawienie **Wyłącz Program antywirusowy Windows Defender** znajduje się poniżej folderów innych ustawień. 
4. Otwórz ustawienie **Wyłącz Program antywirusowy Windows Defender** i upewnij się, że jest ustawione na wartość **Wyłączone** lub **Nieskonfigurowane**.

## <a name="turn-on-real-time-protection"></a>Włączanie ochrony w czasie rzeczywistym

Upewnij się, że ochrona w czasie rzeczywistym jest włączona, przechodząc do menu **Start** i wyszukując pozycję **Windows Defender Security Center**. Wybierz pozycję **Ustawienia ochrony przed wirusami i zagrożeniami** i upewnij się, że opcje **Ochrona w czasie rzeczywistym** i **Ochrona świadczona w chmurze** są przełączone do pozycji **Włącz**. Jeśli te opcje nie pojawiają się, wykonaj następujące czynności, aby je włączyć:

1. W menu **Start** otwórz **Panel sterowania**.
2. Otwórz **Narzędzia administracyjne** > **Edytuj zasady grupy**. Spowoduje to otwarcie **Edytora lokalnych zasad grupy** w nowym oknie.
3. Otwórz kolejno pozycje **Konfiguracja komputera** > **Szablony administracyjne** > **Składniki systemu Windows** > **Windows Defender Security Center** > **Ochrona przed wirusami i zagrożeniami**.
4. Otwórz ustawienie **Ochrona przed wirusami i zagrożeniami** i ustaw je na pozycję **Wyłączone**.

## <a name="update-your-antivirus-definitions"></a>Aktualizowanie definicji antywirusowych

Upewnij się, że definicje antywirusowe są aktualne, przechodząc do menu **Start** i wyszukując pozycję **Windows Defender Security Center**. Wybierz pozycje **Aktualizacje ochrony** i **Sprawdź aktualizacje**, aby upewnić się, że urządzenie ma bieżącą ochronę przed wirusami. Jeśli ta opcja nie jest wyświetlana, postępuj zgodnie z instrukcjami w sekcji [Włączanie ochrony w czasie rzeczywistym](turn-on-defender-windows.md#turn-on-real-time-protection)

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://portal.manage.microsoft.com#HelpDeskDialog).
