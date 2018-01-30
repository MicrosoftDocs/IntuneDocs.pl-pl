---
title: "Optymalizacja zużycia energii uniemożliwia dostęp do poczty e-mail | Microsoft Docs"
description: "Dowiedz się, jak wyłączyć optymalizację zużycia energii dla systemu Android i upewnić się, że wiadomości e-mail są pobierane."
keywords: 
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 07/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ad713f18-40a9-421f-aa2b-f8c21028d57c
searchScope:
- User help
ROBOTS: 
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: d0e39bfc475909ba2f6b8d361ba31c734cace523
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/25/2018
---
# <a name="outlook-wont-sync-managed-email-when-battery-optimization-for-android-is-turned-on"></a>Program Outlook nie synchronizuje zarządzanych kont e-mail w przypadku włączenia funkcji optymalizacji baterii dla systemu Android

> [!IMPORTANT]
> Ta kwestia została udokumentowana w tym miejscu, ponieważ otrzymujemy rosnącą liczbę zgłoszeń klientów z nią związanych. Jeśli ten problem będzie nadal występował po wykonaniu tych kroków, skontaktuj się z [działem pomocy technicznej Twojej firmy](https://portal.manage.microsoft.com#HelpDeskDialog), aby uzyskać dodatkową pomoc.

Zarejestrowanie urządzenia w usłudze Intune pozwala uzyskać dostęp do zasobów firmy. Jednym z najbardziej typowych zasobów jest dostęp do poczty e-mail. Zaobserwowany problem z dostępem do poczty e-mail za pomocą programu Outlook na urządzeniach z systemem Android występuje w przypadku włączenia funkcji optymalizacji baterii. Optymalizacja baterii może zostać włączona automatycznie, aby pomóc w jak najdłuższym utrzymaniu zasilania urządzenia. Optymalizacja baterii jest w stanie częściowo pomóc w ten sposób, ponieważ próbuje zatrzymać automatyczne pobieranie wiadomości e-mail.

Zespół usługi Microsoft Intune aktywnie pracuje nad rozwiązaniem tego problemu. Jednym ze sposobów zapobieżenia przejściu urządzenia w tryb niskiego zużycia energii jest upewnienie się, że bateria utrzymuje poziom naładowania przekraczający 30%. Aby zapobiec wystąpieniu problemu w przypadku przejścia w tryb niskiego zużycia energii, usuń Portal firmy i program Outlook z listy aplikacji, na które mają wpływ ustawienia optymalizacji baterii i zużycia energii.

Na rynku jest wiele urządzeń z systemem Android wyprodukowanych przez wiele firm. Nie jesteśmy w stanie udokumentować dokładnych kroków, które należy wykonać dla każdego urządzenia. Przedstawione działania należy podjąć w ustawieniach systemu, ale także w ustawieniach specyficznych dla danego producenta. Przygotowaliśmy typowe przykłady rozwiązywania tego problemu w urządzeniach z systemem Android.

## <a name="unmodified-android-devices"></a>Niezmodyfikowane urządzenia z systemem Android

Wielu producentów wprowadza modyfikacje w swoich urządzeniach z systemem Android. Mogą one zmienić określone sposoby interakcji z urządzeniem, na przykład motywy i powiadomienia. Firma Google generalnie nie wprowadza modyfikacji tego typu w swoich telefonach. Na przykład na urządzeniu Google Pixel z systemem Android 7.0 lub nowszym należy wykonać następujące kroki, aby wyłączyć optymalizację zasilania dla tych aplikacji:

1. Otwórz obszar **Ustawienia**.
2. Dotknij pozycji **Bateria** > **Więcej** > **Optymalizacja baterii**.
3. Dotknij strzałki w dół, a następnie pozycji **Brak optymalizacji**.
4. Wybierz aplikacje Portal firmy i Outlook, po czym wyłącz optymalizację zasilania.

## <a name="samsung-devices"></a>Urządzenia firmy Samsung

W przypadku innych typów urządzeń z systemem Android, takich jak urządzenia Samsung z systemem Android 7.0 lub nowszym, należy wykonać inne działania w celu wyłączenia aplikacji Outlook i Portal firmy z działania funkcji optymalizacji baterii.

1. Otwórz obszar **Ustawienia**.
2. Dotknij pozycji **Menu (…)** > **Dostęp specjalny** > **Optymalizuj zużycie baterii**.
3. Wybierz z listy rozwijanej pozycję **Wszystkie aplikacje**.
4. **Wyłącz** przełączniki obok aplikacji Portal firmy i Outlook, aby wyłączyć optymalizację baterii.

Dodatkowo jeśli używasz urządzenia Samsung ze starszą wersją systemu Android, musisz wykonać poniższe kroki, aby wyłączyć te aplikacje z trybu oszczędzania energii.

1. Otwórz obszar **Ustawienia**.
2. Dotknij pozycji **Obsługa urządzenia** > **Bateria** > **Aplikacje niemonitorowane**.
3. Dotknij pozycji **Dodaj aplikacje**.
4. Wybierz aplikacje Portal firmy i Outlook, po czym dotknij pozycji **Gotowe**.

## <a name="oneplus-devices"></a>Urządzenia OnePlus

Przykładem innej metody wyszukiwania tych ustawień jest wykorzystanie funkcji przeszukiwania ustawień systemu. Na przykład na urządzeniu OnePlus 3 z systemem Android 7.1.1 wykonaj następujące działania: 

1. Otwórz obszar **Ustawienia systemu**. 
2. Dotknij przycisku **Wyszukaj**. Przycisk ten wygląda jak szkło powiększające i znajduje się w prawym górnym rogu ekranu. 
3. Wpisz **optymalizacja baterii** w polu wyszukiwania, a następnie wybierz opcję **Optymalizacja baterii** na wyświetlonym ekranie **Ustawienia**. 
4. Dotknij pozycji **Bateria** > **Optymalizacja baterii**.
5. Wybierz aplikacje Portal firmy i Outlook, po czym wybierz opcję **Nie optymalizuj**. Naciśnij pozycję **Gotowe**.

<!--On a OnePlus 5 device with Android 7.1.1, you would follow these steps to remove these apps from battery optimization:
1. Open **Settings**.
2. Tap **Battery** > **Battery optimization**.
3. Select the Company Portal and Outlook apps, then select **Don’t optimize**. Tap **Done**.-->

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://portal.manage.microsoft.com#HelpDeskDialog).
