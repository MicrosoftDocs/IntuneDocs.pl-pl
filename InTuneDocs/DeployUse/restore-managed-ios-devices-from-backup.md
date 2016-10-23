---
title: "Przywracanie urządzeń z systemem iOS zarządzanych przez usługę Intune z kopii zapasowej | Microsoft Intune"
description: "Udostępnij użytkownikom końcowym wskazówki na temat ponownej rejestracji ich urządzeń po przywróceniu z kopii zapasowej."
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 10/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a19e5612-8805-4bd7-a86a-b734bde293ae
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 612b0954a81de1ee8d4a1e96c7440239437dec14
ms.openlocfilehash: 5fc4423f8fd0c5829be5fe6c96949e126991e430


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



<!--HONumber=Oct16_HO2-->


