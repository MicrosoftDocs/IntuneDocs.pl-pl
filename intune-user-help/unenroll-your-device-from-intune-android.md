---
title: Jak usunąć urządzenie z systemem Android z usługi Intune | Microsoft Docs
description: Usuwanie urządzenia z systemem Android z Portalu firmy usługi Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/04/2019
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
ms.openlocfilehash: 75b26e178badbaa7905199eb91490134d2b72ba9
ms.sourcegitcommit: 61ed365f7f8826451c41bcab5e19bef97b5a3c72
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/05/2019
ms.locfileid: "54057342"
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
Portal firmy to aplikacja do zarządzania urządzeniami. Nie można jej odinstalować do momentu [wyrejestrowania urządzenia z zarządzania](unenroll-your-device-from-intune-android.md#unenroll-your-android-device-from-management). Po wykonaniu tej czynności naciśnij i przytrzymaj ikonę aplikacji Portal firmy do momentu wyświetlenia pozycji **Odinstaluj**. Naciśnij pozycję **Odinstaluj**, aby usunąć aplikację z urządzenia.  

Alternatywnie naciśnij kolejno pozycje **Ustawienia** > **Aplikacje** > **Portal firmy** > **Odinstaluj**.  

### <a name="remove-company-portal-app-as-device-administrator"></a>Usuwanie aplikacji Portal firmy przez administratora urządzenia  
W ostateczności możesz odinstalować tę aplikację z urządzenia, usuwając ją jako administrator urządzenia.  

Jeśli masz urządzenie należące do firmy, Twoja organizacja może wymagać, aby aplikacja Portal firmy działała na urządzeniu przez cały czas. Jeśli odinstalujesz tę aplikację, to do czasu jej ponownej instalacji możesz utracić dostęp do chronionych zasobów firmy, takich jak wiadomości e-mail, aplikacje i ustawienia sieci WiFi lub VPN. Aby uzyskać więcej informacji na temat instalowania, aktualizowania lub usuwania wymaganych aplikacji, zobacz [Dodawanie aplikacji do usługi Microsoft Intune](https://docs.microsoft.com/intune/apps-add#apps-that-are-added-automatically-by-intune).  

Wykonaj poniższe kroki, aby wyłączyć aplikację Portal firmy jako administrator urządzenia. Rzeczywiste nazwy poszczególnych ustawień mogą być inne na Twoim urządzeniu z systemem Android.  

**Instrukcje dla systemu Android, opcja 1**:  
1. Wybierz kolejno pozycje **Ustawienia** > **Zabezpieczenia** > **Dodatkowe ustawienia zabezpieczeń** > **Administratorzy urządzenia**.  
2. Usuń zaznaczenie opcji **Portal firmy**.  

**Instrukcje dla systemu Android, opcja 2**:  
1. Wybierz kolejno pozycje **Ustawienia** > **Blokada ekranu i zabezpieczenia** > **Inne ustawienia zabezpieczeń** > **Aplikacje administratora urządzenia**.  
2. Usuń zaznaczenie opcji **Portal firmy**.    

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie internetowej Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).
