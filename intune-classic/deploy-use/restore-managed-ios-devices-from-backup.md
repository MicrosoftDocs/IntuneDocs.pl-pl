---
title: Przywracanie urządzeń z systemem iOS zarządzanych przez usługę Intune z kopii zapasowej
description: Udostępnij użytkownikom końcowym wskazówki na temat ponownej rejestracji ich urządzeń po przywróceniu z kopii zapasowej.
keywords: przywracanie, zarządzanie, iOS
author: lenewsad
ms.author: lanewsad
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a19e5612-8805-4bd7-a86a-b734bde293ae
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2c2a35a7faa022ab2b9b095d4a08075e1c338c70
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="restore-intune-managed-ios-devices-from-backup"></a>Przywracanie urządzeń z systemem iOS zarządzanych przez usługę Intune z kopii zapasowej

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Będą się zdarzać przypadki, gdy Ty lub Twoi użytkownicy będą musieli przywrócić urządzenie z systemem iOS, np. gdy użytkownik otrzyma nowe urządzenie. W tym temacie opisano dodatkowe kroki, które mogą być konieczne w celu ustawienia zarządzania w usłudze Intune po przywróceniu urządzenia.

## <a name="restoring-backups-onto-the-same-device"></a>Przywracanie kopii zapasowych na tym samym urządzeniu

Jeśli kopia zapasowa zostanie przywrócona na tym samym urządzeniu, stan rejestracji na tym urządzeniu również zostanie przywrócony. Nie są wymagane dodatkowe działania.

## <a name="restoring-backups-onto-different-devices"></a>Przywracanie kopii zapasowych na różnych urządzeniach

Jeśli kopia zapasowa jest przywracana na innym urządzeniu, stan rejestracji nie zostanie automatycznie przywrócony na nowym urządzeniu. Użytkownicy muszą wykonać standardowe kroki rejestracji w aplikacji Portal firmy w wersji 2.1.22 lub nowszej, aby [zarejestrować swoje urządzenie z systemem iOS w usłudze Intune](/intune-user-help/enroll-your-device-in-intune-ios).

> [!NOTE]
> Jeśli użytkownicy końcowi zostaną objęci zasadami dostępu warunkowego, nie będą mogli uzyskać dostępu do firmowej poczty e-mail do czasu ponownej rejestracji.

> [!TIP]
> Przykładowa informacja dla użytkowników może być następująca: Aby zarejestrować nowe urządzenie, upewnij się, że aplikacja Portal firmy jest w wersji 2.1.22 lub nowszej. Aby sprawdzić wersję, otwórz aplikację Portal firmy, naciśnij przycisk Menu w prawym górnym rogu, a następnie naciśnij pozycję Informacje. Jeśli masz starszą wersję, zamknij aplikację Portal firmy i otwórz sklep App Store. Naciśnij przycisk Aktualizacje w prawym dolnym rogu, a następnie naciśnij przycisk Aktualizuj obok pozycji Portal firmy na liście. Po zakończeniu aktualizacji uruchom aplikację Portal firmy i [zarejestruj swoje urządzenie z systemem iOS w usłudze Intune](/intune-user-help/enroll-your-device-in-intune-ios).

## <a name="resolving-known-issues-with-restores"></a>Rozpoznawanie znanych problemów związanych z przywracaniem

Jeśli użytkownicy mają zainstalowany Portal firmy w wersji 2.1.21 lub starszej, mogą wystąpić trudności podczas przywracania ich urządzenia i uruchamiania aplikacji Portal firmy. Podjęcie odpowiednich kroków może rozwiązać ewentualne problemy użytkownika.

### <a name="for-users-who-will-only-use-their-new-device"></a>Dla użytkowników korzystających wyłącznie z nowego urządzenia
Uruchom aplikację Portal firmy i wyrejestruj urządzenie, wybierając kafelek bieżącego urządzenia i naciskając przycisk __Usuń__. Po usunięciu urządzenia wykonaj standardową procedurę rejestracji w celu [zarejestrowania urządzenia z systemem iOS w usłudze Intune](/intune-user-help/enroll-your-device-in-intune-ios).

### <a name="for-users-who-will-use-both-their-old-and-new-devices"></a>Dla użytkowników korzystających zarówno ze starego, jak i nowego urządzenia
Wyczyść pliki cookie w przeglądarce Safari, naciskając kolejno pozycje __Ustawienia__ > __Safari__ > __Wyczyść historię i dane witryny sieci Web__. Po wyczyszczeniu odinstaluj i ponownie zainstaluj aplikację Portal firmy, a następnie wykonaj standardową procedurę rejestracji, aby [zarejestrować urządzenie z systemem iOS w usłudze Intune](/intune-user-help/enroll-your-device-in-intune-ios).
