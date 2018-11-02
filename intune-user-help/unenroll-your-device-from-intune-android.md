---
title: Jak usunąć urządzenie z systemem Android z usługi Intune | Microsoft Docs
description: Opis sposobu wyrejestrowania urządzenia z systemem Android z usługi Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f40aab26-7613-48cc-a74e-de83df9465a4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: d932005c955afed7f16e9766b559b77b2cd43182
ms.sourcegitcommit: 604b29c480b24270b5debc3e5f3141c8149ee6ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2018
ms.locfileid: "49959489"
---
# <a name="unenroll-your-android-device-from-management"></a>Wyrejestrowanie urządzenia z systemem Android z zarządzania  

Usunięcie zarejestrowanego urządzenia z systemem Android spowoduje, że nie będzie ono już zarządzane przez organizację. W tym artykule opisano sposób usuwania urządzenia z aplikacji Portal firmy. Po usunięciu urządzenia:  

* Urządzenie traci dostęp do chronionych danych i zasobów organizacji.
* Urządzenie nie jest już wyświetlane w aplikacji Portal firmy.
* Nie można instalować aplikacji z poziomu Portalu firmy.
* Wszystkie ustawienia w urządzeniu zmienione podczas dodawania go (np. wyłączenie aparatu lub wymaganie hasła o określonej długości) nie mają już zastosowania.  

1. W aplikacji Portal firmy przejdź do prawego górnego rogu, a następnie naciśnij pionowy symbol wielokropka. Zostanie otwarte menu akcji.

   ![Obraz aplikacji Portal firmy dla systemu Android z otwartym menu akcji w prawym górnym rogu. Nowa opcja „usuń portal firmy” jest dostępna jako trzecia opcja poniżej opcji „mój profil” i „ustawienia”, powyżej pozycji „warunki i postanowienia”, „pomoc i opinie” oraz „informacje”.](./media/android_remove_cp_menu_action_after_1705.png)

2. Naciśnij pozycję **Usuń Portal firmy**.  

3. Zostanie wyświetlony komunikat z informacjami o tym, co się stanie po wyrejestrowaniu urządzenia. Naciśnij przycisk **OK**, aby potwierdzić, że chcesz usunąć urządzenie z aplikacji Portal firmy.

   ![Obraz okna dialogowego potwierdzenia, które jest dostępne po wybraniu w menu akcji nowej opcji „usuń portal firmy”. Okno dialogowe informuje użytkownika, że „po usunięciu portalu firmy urządzenie przestanie być zarządzane przez dział pomocy technicznej Twojej firmy, a dostęp do firmowych danych, aplikacji i poczty e-mail może zostać utracony”. Następnie użytkownik jest proszony o potwierdzenie za pomocą przycisku „Tak”, że chce usunąć aplikację Portal firmy.](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <a name="removing-data-collected-by-the-company-portal-app"></a>Usuwanie danych zebranych przez aplikację Portal firmy  

Aby usunąć wszystkie dane przechowywane przez aplikację Portal firmy dla systemu Android z urządzenia:

-   Wyczyść dane aplikacji: przejdź do obszaru Aplikacje, a następnie kliknij aplikację i przycisk „Wyczyść dane”
-   Usuń folder „\storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal”

## <a name="uninstall-the-company-portal-app"></a>Odinstalowywanie aplikacji Portal firmy  
Portal firmy to aplikacja do zarządzania urządzeniami, więc nie można jej odinstalować do momentu [wyrejestrowania urządzenia z zarządzania](unenroll-your-device-from-intune-android.md#unenroll-your-android-device-from-management). Po wykonaniu tej czynności naciśnij i przytrzymaj ikonę aplikacji Portal firmy do momentu wyświetlenia pozycji **Odinstaluj**. Naciśnij pozycję **Odinstaluj**, aby usunąć aplikację z urządzenia.  

Alternatywnie naciśnij kolejno pozycje **Ustawienia** > **Aplikacje** > **Portal firmy** > **Odinstaluj**.  

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie internetowej Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).
