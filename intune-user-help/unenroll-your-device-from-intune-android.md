---
title: Jak usunąć urządzenie z systemem Android z usługi Intune | Microsoft Docs
description: Usuwanie urządzenia z systemem Android z Portalu firmy usługi Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
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
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0a472e4d8c3ef7b922f02b4d2407362ba738486c
ms.sourcegitcommit: 1494ff4b33c13a87f20e0f3315da79a3567db96e
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 09/20/2019
ms.locfileid: "71167533"
---
# <a name="unenroll-your-android-device-from-management"></a>Wyrejestrowanie urządzenia z systemem Android z zarządzania  

Usunięcie zarejestrowanego urządzenia z systemem Android spowoduje, że nie będzie ono już zarządzane przez organizację. W tym artykule opisano sposób usuwania urządzenia z aplikacji Portal firmy. Po usunięciu urządzenia:  

* Urządzenie traci dostęp do chronionych danych i zasobów organizacji.
* Urządzenie nie jest już wyświetlane w aplikacji Portal firmy.
* Nie można instalować aplikacji z poziomu Portalu firmy.
* Wszystkie ustawienia w urządzeniu zmienione podczas dodawania go (np. wyłączenie aparatu lub wymaganie hasła o określonej długości) nie mają już zastosowania.  

> [!NOTE]
> Nie można wyrejestrować ani usunąć urządzenia należącego do firmy z aplikacji Microsoft Intune. Urządzenie zostało zarejestrowane podczas początkowej konfiguracji urządzenia i musi zostać zarejestrowane w celu uzyskania dostępu do zasobów organizacji.  

1. W aplikacji Portal firmy przejdź do prawego górnego rogu, a następnie naciśnij pionowy symbol wielokropka. Zostanie otwarte menu akcji.

   ![Zrzut ekranu przedstawiający aplikację Portal firmy dla systemu Android z otwartym menu akcji w prawym górnym rogu. Nowa opcja „usuń portal firmy” jest dostępna jako trzecia opcja poniżej opcji „mój profil” i „ustawienia”, powyżej pozycji „warunki i postanowienia”, „pomoc i opinie” oraz „informacje”.](./media/android_remove_cp_menu_action_after_1705.png)

2. Naciśnij pozycję **Usuń Portal firmy**.  

3. Zostanie wyświetlony komunikat z informacjami o tym, co się stanie po wyrejestrowaniu urządzenia. Naciśnij przycisk **OK**, aby potwierdzić, że chcesz usunąć urządzenie z aplikacji Portal firmy.

   ![Zrzut ekranu przedstawiający potwierdzenie, które jest dostępne po wybraniu w menu akcji nowej opcji „Usuń Portal firmy”.](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <a name="remove-data-collected-by-the-company-portal-app"></a>Usuwanie danych zebranych przez aplikację Portal firmy  

Aby usunąć wszystkie dane przechowywane przez aplikację Portal firmy dla systemu Android z urządzenia:

- Wyczyść dane aplikacji, naciskając pozycję **Aplikacje** > **[*nazwa aplikacji*]**  > **Wyczyść dane**.
- Usuń następujący folder: \storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal.

## <a name="uninstall-the-company-portal-app"></a>Odinstalowywanie aplikacji Portal firmy

Portal firmy to aplikacja do zarządzania urządzeniami. Nie można jej odinstalować do momentu wyrejestrowania urządzenia z zarządzania. Po wykonaniu tej czynności naciśnij i przytrzymaj ikonę aplikacji Portal firmy do momentu wyświetlenia pozycji **Odinstaluj**. Naciśnij pozycję **Odinstaluj**, aby usunąć aplikację z urządzenia.  

Alternatywnie naciśnij kolejno pozycje **Ustawienia** > **Aplikacje** > **Portal firmy** > **Odinstaluj**.  

### <a name="remove-the-company-portal-app-as-a-device-administrator"></a>Usuwanie aplikacji Portal firmy przez administratora urządzenia

W ostateczności możesz odinstalować tę aplikację z urządzenia, jako administrator urządzenia.  

Jeśli masz urządzenie należące do firmy, Twoja organizacja może wymagać, aby aplikacja Portal firmy działała na urządzeniu przez cały czas. Jeśli odinstalujesz tę aplikację, to do czasu jej ponownej instalacji możesz utracić dostęp do chronionych zasobów firmy, takich jak wiadomości e-mail, aplikacje i ustawienia sieci Wi-Fi lub VPN. Aby uzyskać więcej informacji na temat instalowania, aktualizowania lub usuwania wymaganych aplikacji, zobacz [Dodawanie aplikacji do usługi Microsoft Intune](https://docs.microsoft.com/intune/apps-add.md#apps-that-are-added-automatically-by-intune).  

Poniżej opisano, jak administrator urządzenia może wyłączyć aplikację Portal firmy. Rzeczywiste nazwy poszczególnych ustawień mogą być inne na Twoim urządzeniu z systemem Android.  

**Opcja 1**.  

1. Wybierz kolejno pozycje **Ustawienia** > **Zabezpieczenia** > **Dodatkowe ustawienia zabezpieczeń** > **Administratorzy urządzenia**.  
2. Usuń zaznaczenie opcji **Portal firmy**.  

**Opcja 2**:

1. Wybierz kolejno pozycje **Ustawienia** > **Blokada ekranu i zabezpieczenia** > **Inne ustawienia zabezpieczeń** > **Aplikacje administratora urządzenia**.
2. Usuń zaznaczenie opcji **Portal firmy**.

Nadal potrzebujesz pomocy? Skontaktuj się z pomocą techniczną Twojej firmy. Informacje kontaktowe są dostępne w [witrynie sieci Web Portal firmy](https://go.microsoft.com/fwlink/?linkid=2010980).
