---
title: "Zalety zestawu SDK aplikacji usługi Intune | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd9f05e7-26e6-45e0-8d38-67d8232b1cae
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 952cfa4f23f8ba080ce53f6785baceb8a0a367c6
ms.openlocfilehash: ce8fa172c68fed7a1398cd5b1263ac970b87559b


---

# Omówienie zestawu SDK aplikacji usługi Intune
Zestaw SDK aplikacji usługi Intune jest dostępny na platformach iOS i Android. Udostępnia on funkcje zarządzania aplikacjami mobilnymi umożliwiające zarządzanie nimi za pomocą usługi Microsoft Intune. Ponadto staramy się zmniejszyć liczbę zmian w kodzie wymaganych od dewelopera. Większość funkcji zestawu SDK możesz włączyć bez zmiany zachowania aplikacji. W przypadku rozszerzonego środowiska użytkownika końcowego i administratora IT możesz użyć naszych interfejsów API, aby dostosować zachowanie aplikacji dla funkcji, które wymagają współdziałania ze strony aplikacji. Po aktywowaniu aplikacji administratorzy IT mogą wdrożyć zasady w zarządzanych aplikacjach usługi Intune i skorzystać z tych funkcji do ochrony danych firmowych.

## Standardowe funkcje

### Kontrolowanie możliwości przenoszenia dokumentów firmowych przez użytkowników
Administratorzy IT mogą kontrolować przenoszenie plików dokumentów firmowych w aplikacjach zarządzanych przez usługę Intune. Na przykład mogą wdrożyć zasady, które wyłączają w aplikacjach do obsługi kopii zapasowych możliwość tworzenia kopii zapasowych danych firmowych w chmurze.

### Konfigurowanie ograniczeń schowka
Administratorzy IT mogą skonfigurować działanie schowka w aplikacjach zarządzanych przez usługę Intune. Na przykład mogą wdrożyć zasady, tak aby użytkownicy końcowi nie mogli użyć funkcji wycinania/kopiowania do schowka w aplikacji zarządzanej przez usługę Intune i wkleić danych do aplikacji niezarządzanej.

### Konfigurowanie ograniczeń przechwytywania ekranu
Administratorzy IT mogą uniemożliwić użytkownikom przechwytywanie ekranu, jeśli jest wyświetlana aplikacja zarządzana przez usługę Intune. Zastosowanie tego ograniczenia zapobiega przechwytywaniu i publikowaniu poufnej zawartości firmowej. Ta funkcja jest dostępna tylko na urządzeniach z systemem Android.

### Wymuszanie szyfrowania zapisywanych danych
Administratorzy IT mogą wymusić zasady, które powodują szyfrowanie danych zapisywanych na urządzeniu przez aplikację.

### Zdalne czyszczenie danych firmowych
Administratorzy IT mogą zdalnie wyczyścić dane firmowe z aplikacji zarządzanej przez usługę Intune, gdy urządzenie jest wyrejestrowywane z usługi Microsoft Intune. Ta funkcja jest oparta na tożsamości i usuwa tylko pliki, które są powiązane z tożsamością firmową użytkownika końcowego. Funkcja wymaga w tym celu współdziałania ze strony aplikacji. Aplikacja może określić tożsamość, dla której powinno zostać wykonane czyszczenie, na podstawie ustawień użytkownika. Jeśli te określone ustawienia użytkownika są niedostępne w aplikacji, domyślne zachowanie to wyczyszczenie katalogu aplikacji i powiadomienie użytkownika końcowego, że dostęp do zasobów firmy został usunięty.

### Wymuszanie użycia programu Managed Browser
Administratorzy IT mogą wymusić użycie programu Managed Browser przy otwieraniu linków z aplikacji zarządzanych przez usługę Intune. Użycie programu Managed Browser zarządzanego przez usługę Intune ułatwia zapewnienie, że linki w wiadomościach e-mail (w ramach klienta poczty e-mail zarządzanego przez usługę Intune) pozostają w domenie aplikacji zarządzanych przez usługę Intune.

### Wymuszanie zasad numeru PIN
Administratorzy IT mogą wymusić zasady numeru PIN przy uruchamianiu aplikacji zarządzanej przez usługę Intune. Te zasady ułatwiają zapewnienie, że użytkownicy końcowi z urządzeniami zarejestrowanymi w usłudze Microsoft Intune są tymi samymi osobami, które uruchamiają aplikacje. Gdy użytkownicy końcowi skonfigurują swoje numery PIN, zestaw SDK aplikacji usługi Intune używa usługi Azure Active Directory do zweryfikowania poświadczeń użytkowników końcowych względem poświadczeń użytych do zarejestrowania urządzenia.

### Wymaganie wprowadzenia poświadczeń przed uruchomieniem aplikacji
Administratorzy IT mogą wymagać od użytkowników wprowadzenia poświadczeń przed uruchomieniem aplikacji zarządzanej przez usługę Intune. Zestaw SDK aplikacji usługi Intune używa usługi Azure Active Directory do udostępnienia funkcji logowania jednokrotnego, która umożliwia ponowne użycie poświadczeń podczas kolejnych logowań po ich jednokrotnym podaniu. Obsługiwane jest również uwierzytelnianie przy użyciu rozwiązań do zarządzania tożsamościami [sfederowanych z usługą Azure Active Directory](https://msdn.microsoft.com/library/azure/jj679342.aspx).

### Sprawdzanie kondycji i zgodności urządzenia
Administratorzy IT mogą sprawdzić kondycję urządzenia i jego zgodność z zasadami firmy przed udostępnieniem użytkownikom końcowym aplikacji zarządzanych przez usługę Intune. Na platformie iOS te zasady sprawdzają, czy nie zostały zdjęte zabezpieczenia systemu. Na platformie Android te zasady sprawdzają, czy na urządzeniu nie został odblokowany dostęp do konta root.

## Funkcje w wersji zapoznawczej
Zestaw SDK aplikacji usługi Microsoft Intune zawiera kilka funkcji w wersji zapoznawczej. Możesz rozpocząć integrowanie z interfejsami API w wersji zapoznawczej, lecz tylko do celów testowych. Zwróć uwagę, że te funkcje w wersji zapoznawczej raczej uzupełniają istniejące scenariusze, a nie zastępują ich.

### Obsługa wielu tożsamości w zestawie SDK aplikacji usługi Microsoft Intune
Obsługa wielu tożsamości to funkcja, która umożliwia współistnienie kont zarządzanych przez zasady (firmowych) i niezarządzanych (osobistych) w jednej aplikacji.

### Przykład scenariusza z wieloma tożsamościami
Wielu użytkowników konfiguruje zarówno konto firmowe, jak i osobiste w aplikacji Outlook w systemach iOS i Android. Gdy użytkownik uzyskuje dostęp do danych na koncie firmowym, administrator IT musi mieć pewność, że funkcja zarządzania zasadami MAM zostanie zastosowana. Jednak gdy użytkownik uzyskuje dostęp do osobistego konta e-mail, dane powinny być poza kontrolą administratora IT. Usługa Microsoft Intune osiąga to, wybierając w aplikacji zasady zarządzania tylko dla konta firmowego. Funkcja umożliwiająca stosowanie wielu tożsamości pomaga w rozwiązaniu problemów z ochroną danych, przed którymi stoją organizacje używające urządzeń i aplikacji obsługujących konta osobiste oraz firmowe.

### Jak obsługiwać wiele tożsamości
Interfejsy API w wersji zapoznawczej umożliwiają określenie głównej nazwy użytkownika (UPN) razem z określonymi operacjami, takimi jak operacje schowka i plików. Zestaw SDK aplikacji usługi Microsoft Intune używa nazwy UPN w celu dopasowania wywołania do głównej nazwy użytkownika użytej do zarejestrowania urządzenia w usłudze Microsoft Intune. Jeśli nazwy UPN są zgodne, wywołanie jest traktowane jako wywołanie „danych firmowych” i dane są chronione. Jeśli nazwy UPN nie są zgodne, wywołanie jest traktowane jako wywołanie „danych osobistych” i dane nie są chronione.

### Zarządzanie aplikacjami bez rejestracji urządzeń
Wielu użytkowników korzystających z urządzeń przenośnych chce przeglądać dane firmowe i pracować z nimi bez rejestrowania swoich urządzeń osobistych za pomocą produktu do zarządzania urządzeniami przenośnymi (MDM). Ponieważ rejestracja za pomocą rozwiązania MDM wymaga przejęcia całkowitej kontroli nad urządzeniem, użytkownicy niechętnie zezwalają na taką kontrolę osobistego urządzenia przez firmę.

Zarządzanie aplikacjami bez rejestracji urządzenia umożliwia usłudze Microsoft Intune wdrożenie zasad MAM w aplikacji bezpośrednio, bez konieczności korzystania z kanału rozwiązania MDM do wdrożenia zasad. Ponieważ kanał rozwiązania MDM nie jest potrzebny, rejestracja za pomocą rozwiązania MDM także nie jest potrzebna.




<!--HONumber=Sep16_HO2-->


