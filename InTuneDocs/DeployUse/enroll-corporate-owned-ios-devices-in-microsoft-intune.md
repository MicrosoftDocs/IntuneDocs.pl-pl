---
title: "Rejestrowanie urządzeń firmowych z systemem iOS | Microsoft Intune"
description: "Rejestrowanie urządzeń firmowych z systemem iOS przy użyciu programu Apple Device Enrollment Program (DEP) lub narzędzia Apple Configurator"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d81ef697518745b258598124d6e73899bdd76a0f
ms.openlocfilehash: 00d7e73154bb293fec48b74b6f6454d67e5ef378


---

# Rejestrowanie firmowych urządzeń z systemem iOS w usłudze Microsoft Intune
Usługa Microsoft Intune obsługuje rejestrowanie firmowych urządzeń z systemem iOS w ramach programu Device Enrollment Program (DEP) firmy Apple lub przy użyciu narzędzia [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) działającego na komputerze Mac.

**Wymaganie wstępne:** wymagany jest [certyfikat usługi Apple Push Notification Service](set-up-ios-and-mac-management-with-microsoft-intune.md).

Firmowe urządzenia z systemem iOS można zarejestrować na trzy sposoby: za pomocą narzędzia Apple Configurator, programu DEP lub Portalu firmy.

## Użycie narzędzia Apple Configurator

W celu zarejestrowania urządzeń z systemem iOS można wyeksportować firmowy profil wdrażania, a następnie połączyć te urządzenia przenośne z komputerem Mac, na którym działa program Apple Configurator. Program Apple Configurator obsługuje dwa rodzaje rejestracji:

- **Rejestracja przy użyciu Asystenta ustawień**: przywracanie ustawień fabrycznych urządzenia i przygotowanie do konfiguracji przez nowego użytkownika. Ta metoda wymaga od administratora podłączenia urządzenia z systemem iOS przez port USB do komputera Mac z programem [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) w celu wstępnego skonfigurowania rejestracji. Urządzenia są następnie dostarczane do ich użytkowników, którzy korzystają z procesu Asystenta ustawień. W ramach tego procesu następuje konfiguracja urządzenia z poświadczeniami firmy lub szkoły i ukończenie procesu rejestracji. Aby uzyskać więcej informacji, zobacz artykuł [Rejestracja urządzeń z systemem iOS w narzędziu Apple Configurator przy użyciu Asystenta ustawień](ios-setup-assistant-enrollment-in-microsoft-intune.md).

- **Rejestracja bezpośrednia**: tworzenie pliku zgodnego z programem Apple Configurator do użytku podczas przygotowywania urządzenia. Zarejestrowane urządzenie nie jest resetowane do ustawień fabrycznych, ale nie ma określonej przynależności do użytkownika. Ta metoda wymaga od administratora podłączenia urządzenia iOS przez port USB do komputera Mac z programem [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) w celu zarejestrowania urządzenia. Aby uzyskać więcej informacji, zobacz artykuł [Bezpośrednie rejestrowanie urządzeń z systemem iOS przy użyciu programu Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md).

## Użycie programu Device Enrollment Program (DEP)
Program DEP wdraża bezprzewodowo profil rejestracji na urządzeniach zakupionych w ramach tego programu. Gdy użytkownik uruchamia na urządzeniu Asystenta ustawień, jest ono rejestrowane w usłudze Intune.  Użytkownicy nie mogą wyrejestrowywać urządzeń zarejestrowanych w programie DEP. Aby uzyskać więcej informacji, zobacz artykuł [Rejestrowanie firmowych urządzeń z systemem iOS przy użyciu Device Enrollment Program](ios-device-enrollment-program-in-microsoft-intune.md).

## Korzystanie z Portalu firmy na urządzeniach zarejestrowanych w programie DEP lub przy użyciu narzędzia Apple Configurator

Na urządzeniach skonfigurowanych z koligacją użytkownika można zainstalować aplikację Portal firmy i używać jej do pobierania aplikacji i zarządzania urządzeniami. Po otrzymaniu urządzeń użytkownicy muszą wykonać kilka dodatkowych czynności w celu ukończenia działania Asystenta ustawień i zainstalowania aplikacji Portal firmy.

**Jak użytkownicy rejestrują urządzenia firmowe z systemem iOS z koligacją użytkownika**
1. Po włączeniu urządzenia użytkownicy są monitowani o ukończenie działania Asystenta ustawień. Podczas instalacji użytkownicy są monitowani o podanie swoich poświadczeń. Muszą oni korzystać z poświadczeń (tj. unikatowej kombinacji imienia i nazwiska lub nazwy UPN) skojarzonych z ich subskrypcją w usłudze Intune.

2. Podczas instalacji użytkownicy są monitowani o podanie identyfikatora Apple ID. Muszą podać identyfikator Apple ID, aby umożliwić zainstalowanie aplikacji Portal firmy na urządzeniu. Mogą także podać identyfikator z menu ustawień systemu iOS po zakończeniu konfiguracji.

3. Po ukończeniu konfiguracji na urządzeniu iOS trzeba zainstalować aplikację Portal firmy ze sklepu App Store.

4. Użytkownik może się teraz zalogować do Portalu firmy przy użyciu nazwy UPN użytej podczas konfigurowania urządzenia.

5. Po zalogowaniu użytkownik jest monitowany o zarejestrowanie urządzenia. Pierwszym krokiem jest zidentyfikowanie urządzenia. Aplikacja wyświetla listę urządzeń z systemem iOS, które zostały już zarejestrowane przez firmę i przypisane do konta użytkownika w usłudze Intune. Użytkownicy powinni wybrać odpowiednie urządzenie.

  Jeśli to urządzenie nie zostało jeszcze zarejestrowane przez firmę, użytkownicy powinni wybrać pozycję **nowe urządzenie**, aby kontynuować standardową procedurę rejestracji.

6. Na następnym ekranie użytkownik musi potwierdzić numer seryjny nowego urządzenia. Użytkownik może nacisnąć link **potwierdź numer seryjny**, aby uruchomić aplikację Ustawienia w celu zweryfikowania numeru seryjnego. Użytkownik musi następnie wprowadzić cztery ostatnie znaki numeru seryjnego do aplikacji Portal firmy.

  Ten krok umożliwia zweryfikowanie, że urządzenie zostało zarejestrowane przez firmę w usłudze Intune. Jeśli numer seryjny urządzenia nie jest zgodny, oznacza to, że wybrano niewłaściwe urządzenie. Użytkownik powinien wrócić do poprzedniego ekranu i wybrać inne urządzenie.

7. Po zweryfikowaniu numeru seryjnego aplikacja Portal firmy wykonuje przekierowanie do witryny internetowej Portalu firmy w celu sfinalizowania rejestracji. Następnie w witrynie pojawia się monit o powrót użytkownika do aplikacji.

8. Rejestracja jest teraz ukończona. Użytkownik może teraz używać tego urządzenia z pełnym zestawem funkcji.

### Informacje dotyczące zarządzanych urządzeń należących do firmy bez koligacji użytkownika

Urządzenia skonfigurowane bez koligacji użytkownika nie obsługują Portalu firmy i nie powinny mieć zainstalowanej tej aplikacji. Portal firmy jest przeznaczony dla użytkowników, którzy mają poświadczenia firmowe i wymagają dostępu do spersonalizowanych zasobów firmowych (np. poczta e-mail). Urządzenia zarejestrowane bez koligacji użytkownika nie są przeznaczone do logowania określonego użytkownika. Urządzenia rejestrowane bez koligacji użytkownika są zazwyczaj stosowane w kioskach lub punktach sprzedaży (POS) albo jako narzędzia udostępnione.

Jeśli koligacja użytkownika jest wymagana, przed zarejestrowaniem urządzenia należy sprawdzić, czy w profilu rejestracji urządzenia wybrano opcję **Koligacja użytkownika**. Aby zmienić stan koligacji urządzenia, należy wycofać urządzenie i zarejestrować je ponownie.



### Zobacz także
[Przygotowanie do rejestracji urządzeń w usłudze Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Sep16_HO1-->


