---
title: "Omówienie zestawu SDK aplikacji usługi Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ef1751bb-3a2f-4662-a922-38c076869eb3
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: 8a9dfe8224b4e0e441691043eaffea73c456b3ec


---

# Omówienie zestawu SDK aplikacji usługi Microsoft Intune
Zestaw SDK aplikacji usługi Intune jest dostępny na platformach iOS i Android. Udostępnia on funkcje zarządzania aplikacjami mobilnymi umożliwiające zarządzanie nimi za pomocą usługi Microsoft Intune. Ponadto staramy się zmniejszyć liczbę zmian w kodzie wymaganych od dewelopera. Większość funkcji zestawu SDK możesz włączyć bez zmiany zachowania aplikacji. W przypadku rozszerzonego środowiska użytkownika końcowego i administratora IT możesz użyć naszych interfejsów API, aby dostosować zachowanie aplikacji dla funkcji, które wymagają współdziałania ze strony aplikacji. 

Po aktywowaniu aplikacji administratorzy IT mogą wdrożyć zasady w zarządzanych aplikacjach usługi Intune i skorzystać z tych funkcji do ochrony danych firmowych.

# Funkcje
## Kontrolowanie możliwości przenoszenia dokumentów firmowych przez użytkowników
Administratorzy IT mogą kontrolować przenoszenie plików dokumentów firmowych w aplikacjach zarządzanych przez usługę Intune. Na przykład mogą wdrożyć zasady, które wyłączają w aplikacjach do obsługi kopii zapasowych możliwość tworzenia kopii zapasowych danych firmowych w chmurze.  

## Konfigurowanie ograniczeń schowka
Administratorzy IT mogą skonfigurować działanie schowka w aplikacjach zarządzanych przez usługę Intune. Na przykład mogą wdrożyć zasady, tak aby użytkownicy końcowi nie mogli użyć funkcji wycinania/kopiowania do schowka w aplikacji zarządzanej przez usługę Intune i wkleić danych do aplikacji niezarządzanej.

## Konfigurowanie ograniczeń przechwytywania ekranu
Administratorzy IT mogą uniemożliwić użytkownikom przechwytywanie ekranu, jeśli jest wyświetlana aplikacja zarządzana przez usługę Intune. Zastosowanie tego ograniczenia zapobiega przechwytywaniu i publikowaniu poufnej zawartości firmowej. Ta funkcja jest dostępna tylko na urządzeniach z systemem Android. 

## Wymuszanie szyfrowania zapisywanych danych
Administratorzy IT mogą wymusić zasady, które powodują szyfrowanie danych zapisywanych na urządzeniu przez aplikację.

## Zdalne czyszczenie danych firmowych
Administratorzy IT mogą zdalnie wyczyścić dane firmowe z aplikacji zarządzanej przez usługę Intune, gdy urządzenie jest wyrejestrowywane z usługi Microsoft Intune. Ta funkcja jest oparta na tożsamości i usuwa tylko pliki, które są powiązane z tożsamością firmową użytkownika końcowego. Funkcja wymaga w tym celu współdziałania ze strony aplikacji. Aplikacja może określić tożsamość, dla której powinno zostać wykonane czyszczenie, na podstawie ustawień użytkownika. Jeśli te określone ustawienia użytkownika są niedostępne w aplikacji, domyślne zachowanie to wyczyszczenie katalogu aplikacji i powiadomienie użytkownika końcowego, że dostęp do zasobów firmy został usunięty. 

## Wymuszanie użycia programu Managed Browser
Administratorzy IT mogą wymusić użycie programu Managed Browser przy otwieraniu linków z aplikacji zarządzanych przez usługę Intune. Użycie programu Managed Browser zarządzanego przez usługę Intune ułatwia zapewnienie, że linki w wiadomościach e-mail (w ramach klienta poczty e-mail zarządzanego przez usługę Intune) pozostają w domenie aplikacji zarządzanych przez usługę Intune.

## Wymuszanie zasad numeru PIN
Administratorzy IT mogą wymusić zasady numeru PIN przy uruchamianiu aplikacji zarządzanej przez usługę Intune. Te zasady ułatwiają zapewnienie, że użytkownicy końcowi z urządzeniami zarejestrowanymi w usłudze Microsoft Intune są tymi samymi osobami, które uruchamiają aplikacje. Gdy użytkownicy końcowi skonfigurują swoje numery PIN, zestaw SDK aplikacji usługi Intune używa usługi Azure Active Directory do zweryfikowania poświadczeń użytkowników końcowych wobec poświadczeń użytych do zarejestrowania urządzenia. 

## Wymaganie wprowadzenia poświadczeń przed uruchomieniem aplikacji
Administratorzy IT mogą wymagać od użytkowników wprowadzenia poświadczeń przed uruchomieniem aplikacji zarządzanej przez usługę Intune. Zestaw SDK aplikacji usługi Intune używa usługi Azure Active Directory do udostępnienia funkcji logowania jednokrotnego, która umożliwia ponowne użycie poświadczeń podczas kolejnych logowań po ich jednokrotnym podaniu. Obsługujemy również uwierzytelnianie rozwiązań do zarządzania tożsamościami [sfederowanych z usługą Azure Active Directory](https://msdn.microsoft.com/en-us/library/azure/jj679342.aspx). 

## Sprawdzanie kondycji i zgodności urządzenia
Administratorzy IT mogą sprawdzić kondycję urządzenia i jego zgodność z zasadami firmy przed udostępnieniem użytkownikom końcowym aplikacji zarządzanych przez usługę Intune. Na platformie iOS te zasady sprawdzają, czy nie zostały zdjęte zabezpieczenia systemu. Na platformie Android te zasady sprawdzają, czy na urządzeniu nie został odblokowany dostęp do konta root.  





<!--HONumber=Jun16_HO4-->


