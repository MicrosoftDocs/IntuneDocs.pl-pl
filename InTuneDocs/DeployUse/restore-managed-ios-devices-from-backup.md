---
title: "Przywracanie urządzeń z systemem iOS zarządzanych przez usługę Intune z kopii zapasowej | Microsoft Intune"
description: "Udostępnij użytkownikom końcowym wskazówki na temat ponownej rejestracji ich urządzeń po przywróceniu z kopii zapasowej."
keywords: "przywracanie, zarządzanie, iOS"
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a19e5612-8805-4bd7-a86a-b734bde293ae
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e6bb539c87c4a13a490ba98c016d814bea5c7bbc
ms.openlocfilehash: 6395e50b3e4c06e7363acc136b5ed9eb2ef75abd


---

# Przywracanie urządzeń z systemem iOS zarządzanych przez usługę Intune z kopii zapasowej

Będą się zdarzać przypadki, gdy Ty lub Twoi użytkownicy będą musieli przywrócić urządzenie z systemem iOS, np. gdy użytkownik otrzyma nowe urządzenie. W tym temacie opisano dodatkowe kroki, które mogą być konieczne w celu ustawienia zarządzania w usłudze Intune po przywróceniu urządzenia.

## Przywracanie kopii zapasowych na tym samym urządzeniu

Jeśli kopia zapasowa zostanie przywrócona na tym samym urządzeniu, stan rejestracji na tym urządzeniu również zostanie przywrócony. Nie są wymagane dodatkowe działania.

## Przywracanie kopii zapasowych na różnych urządzeniach

Jeśli kopia zapasowa jest przywracana na innym urządzeniu, stan rejestracji nie zostanie automatycznie przywrócony na nowym urządzeniu. Użytkownicy muszą wykonać standardowe kroki rejestracji w aplikacji Portal firmy w wersji 2.1.22 lub nowszej, aby [zarejestrować swoje urządzenie z systemem iOS w usłudze Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).

> [!NOTE]
> Jeśli użytkownicy końcowi zostaną objęci zasadami dostępu warunkowego, nie będą mogli uzyskać dostępu do firmowej poczty e-mail do czasu ponownej rejestracji.

> [!TIP]
> Przykładowa informacja dla użytkowników może być następująca: Aby zarejestrować nowe urządzenie, upewnij się, że aplikacja Portal firmy jest w wersji 2.1.22 lub nowszej. Aby sprawdzić wersję, otwórz aplikację Portal firmy, naciśnij przycisk Menu w prawym górnym rogu, a następnie naciśnij pozycję Informacje. Jeśli masz starszą wersję, zamknij aplikację Portal firmy i otwórz sklep App Store. Naciśnij przycisk Aktualizacje w prawym dolnym rogu, a następnie naciśnij przycisk Aktualizuj obok pozycji Portal firmy na liście. Po zakończeniu aktualizacji uruchom aplikację Portal firmy i [zarejestruj swoje urządzenie z systemem iOS w usłudze Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).

## Rozpoznawanie znanych problemów związanych z przywracaniem

Jeśli użytkownicy mają zainstalowany Portal firmy w wersji 2.1.21 lub starszej, mogą wystąpić trudności podczas przywracania ich urządzenia i uruchamiania aplikacji Portal firmy. Podjęcie odpowiednich kroków może rozwiązać ewentualne problemy użytkownika.

### Dla użytkowników korzystających wyłącznie z nowego urządzenia
Uruchom aplikację Portal firmy i wyrejestruj urządzenie, wybierając kafelek bieżącego urządzenia i naciskając przycisk __Usuń__. Po usunięciu urządzenia wykonaj standardową procedurę rejestracji w celu [zarejestrowania urządzenia z systemem iOS w usłudze Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).

### Dla użytkowników korzystających zarówno ze starego, jak i nowego urządzenia
Wyczyść pliki cookie w przeglądarce Safari, naciskając kolejno pozycje __Ustawienia__ > __Safari__ > __Wyczyść historię i dane witryny sieci Web__. Po wyczyszczeniu odinstaluj i ponownie zainstaluj aplikację Portal firmy, a następnie wykonaj standardową procedurę rejestracji, aby [zarejestrować urządzenie z systemem iOS w usłudze Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).



<!--HONumber=Oct16_HO3-->


