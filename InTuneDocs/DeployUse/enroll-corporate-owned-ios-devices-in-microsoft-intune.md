---
title: "Rejestrowanie urządzeń firmowych z systemem iOS | Microsoft Intune"
description: "Rejestrowanie urządzeń firmowych z systemem iOS przy użyciu programu Apple Device Enrollment Program (DEP) lub programu Apple Configurator"
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
ms.sourcegitcommit: 9b7b8f6e5182e228458f5ea75e804a638f1e2a2b
ms.openlocfilehash: ca05e94e72269c11db24b667f1d113c794cd8b23


---

# Rejestrowanie firmowych urządzeń z systemem iOS w usłudze Microsoft Intune
Usługa Microsoft Intune obsługuje rejestrowanie firmowych urządzeń z systemem iOS w ramach programu Device Enrollment Program (DEP) firmy Apple lub przy użyciu programu [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) działającego na komputerze Mac.

**Wymaganie wstępne:** [certyfikat usługi Apple Push Notification Service](set-up-ios-and-mac-management-with-microsoft-intune.md)

Firmowe urządzenia z systemem iOS można zarejestrować na trzy sposoby:

-   **Apple Configurator** — urządzenia z systemem iOS można zarejestrować, eksportując profil rejestracji w firmie, a następnie łącząc te urządzenia przenośne z programem Apple Configurator działającym na komputerze Mac. Program Apple Configurator obsługuje dwa rodzaje rejestracji:

    - **Rejestracja przy użyciu asystenta ustawień** — resetuje urządzenie do ustawień fabrycznych i przygotowuje je do konfiguracji przez nowego użytkownika urządzenia. Ta metoda wymaga od administratora podłączenia do komputera Mac z programem [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) urządzenia z systemem iOS za pośrednictwem portu USB w celu wstępnego skonfigurowania rejestracji. Następnie urządzenia są dostarczane do użytkowników, którzy uruchamiają proces Asystenta ustawień, konfigurują urządzenie za pomocą służbowych poświadczeń użytkownika i kończą proces rejestracji. [Rejestracja urządzeń z systemem iOS przy użyciu narzędzia Apple Configurator i Asystenta ustawień](ios-setup-assistant-enrollment-in-microsoft-intune.md)

    - **Rejestracja bezpośrednia** — tworzy plik zgodny z programem Apple Configurator do użytku podczas przygotowywania urządzenia. Zarejestrowane urządzenie nie jest resetowane do ustawień fabrycznych, ale nie ma określonej przynależności do użytkownika. Ta metoda wymaga od administratora podłączenia do komputera Mac z programem [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) urządzenia z systemem iOS za pośrednictwem portu USB w celu zarejestrowania urządzenia. [Rejestrowanie urządzeń z systemem iOS przy użyciu bezpośredniej rejestracji w programie Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md)

-   **Device Enrollment Program (DEP)** — wdraża profil rejestracji bez udziału użytkownika w urządzeniach zakupionych w programie Device Enrollment Program firmy Apple. Gdy użytkownik uruchomi Asystenta ustawień na urządzeniu, urządzenie zostanie zarejestrowane w usłudze Intune.  Urządzenia zarejestrowane w programie DEP nie mogą zostać wyrejestrowane przez użytkowników. [Rejestrowanie urządzeń z systemem iOS biorących udział w programie Device Enrollment Program](ios-device-enrollment-program-in-microsoft-intune.md)

## Korzystanie z portalu firmy na urządzeniach zarejestrowanych w programie DEP lub przy użyciu programu Apple Configurator

Urządzenia skonfigurowane z koligacją użytkownika mogą instalować i uruchamiać aplikację Portal firmy w celu pobierania aplikacji i zarządzania urządzeniami. Gdy użytkownicy otrzymają urządzenia, muszą wykonać kilka dodatkowych czynności w celu ukończenia działania Asystenta ustawień i zainstalowania aplikacji Portal firmy.

Jak rejestrować urządzenia firmowe z systemem iOS z koligacją użytkownika
1. Gdy użytkownicy włączają urządzenia, są monitowani o ukończenie działania Asystenta ustawień. Podczas instalacji użytkownicy są monitowani o podanie swoich poświadczeń. Muszą oni korzystać z poświadczeń (tj. unikatowego imienia i nazwiska lub nazwy UPN) skojarzonych z ich subskrypcją w usłudze Intune.

2. Podczas instalacji użytkownicy są monitowani o podanie identyfikatora Apple ID. Należy podać identyfikator Apple ID, aby umożliwić zainstalowanie aplikacji Portal firmy na urządzeniu. Identyfikator Apple ID można również podać po ukończeniu instalacji, korzystając z menu ustawień systemu iOS.

3. Po ukończeniu instalacji urządzenie iOS musi zainstalować aplikację Portal firmy ze sklepu App Store, na przykład aplikację Portal firmy.

4. Użytkownik może teraz zalogować się do Portalu firmy przy użyciu nazwy UPN używanej podczas konfigurowania urządzenia.

5. Po zalogowaniu użytkownik jest monitowany o zarejestrowanie urządzenia. Pierwszym krokiem jest zidentyfikowanie urządzenia. Aplikacja wyświetla listę urządzeń z systemem iOS, które zostały już zarejestrowane przez firmę i przypisane do konta użytkownika końcowego w usłudze Intune. Wybierz odpowiednie urządzenie.

  Jeśli to urządzenie nie zostało jeszcze zarejestrowane przez firmę, wybierz pozycję „nowe urządzenie”, aby kontynuować standardową procedurę rejestracji.

6. Na następnym ekranie użytkownik musi potwierdzić numer seryjny nowego urządzenia. Użytkownik może nacisnąć link „potwierdź numer seryjny”, aby uruchomić aplikację Ustawienia w celu zweryfikowania numeru seryjnego. Użytkownik musi następnie wprowadzić 4 ostatnie znaki numeru seryjnego w aplikacji Portal firmy.

  Ten krok umożliwia zweryfikowanie, że urządzenie zostało zarejestrowane przez firmę w usłudze Intune. Jeśli numer seryjny urządzenia nie jest zgodny, oznacza to, że wybrano niewłaściwe urządzenie. Wróć do poprzedniego ekranu i wybierz inne urządzenie.

7. Po zweryfikowaniu numeru seryjnego aplikacja Portal firmy wykonuje przekierowanie do witryny Portalu firmy w sieci Web w celu sfinalizowania rejestracji, a następnie monituje użytkownika o powrót do aplikacji.

8. Rejestracja jest teraz ukończona. Możesz teraz używać tego urządzenia z pełnym zestawem funkcji.

### Informacje dotyczące zarządzanych urządzeń należących do firmy bez koligacji użytkownika

Urządzenia skonfigurowane bez koligacji użytkownika nie obsługują Portalu firmy i nie powinny instalować aplikacji. Portal firmy jest przeznaczony dla użytkowników, którzy mają poświadczenia firmowe i wymagają dostępu do spersonalizowanych zasobów firmowych (np. poczta e-mail). Urządzenia zarejestrowane bez koligacji użytkownika nie powinny być dedykowane do logowania określonego użytkownika. Urządzenia zarejestrowane bez koligacji użytkownika są zazwyczaj stosowane w kioskach lub punktach sprzedaży (POS) albo jako narzędzia udostępnione. Jeśli koligacja użytkownika jest wymagana, należy upewnić się, że dla profilu rejestracji urządzenia wybrano opcję Koligacja użytkownika przed zarejestrowaniem urządzenia. Aby zmienić stan koligacji urządzenia, należy wycofać i ponownie zarejestrować urządzenie.



### Zobacz także
[Przygotowanie do rejestracji urządzeń w usłudze Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Aug16_HO1-->


