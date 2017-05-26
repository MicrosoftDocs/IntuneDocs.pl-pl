---
title: "Bezpośrednia rejestracja urządzeń z systemem iOS | Microsoft Docs"
description: "Użyj narzędzia Apple Configurator, aby bezpośrednio zarejestrować firmowe urządzenia z systemem iOS za pomocą wstępnie zdefiniowanych zasad poprzez połączenie USB z komputerem Mac."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a692b90c-72ae-47d1-ba9c-67a2e2576cc2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: ee0320db2c4a1a977326f62fcd20597fa39aba24
ms.lasthandoff: 04/24/2017


---

# <a name="directly-enroll-ios-devices-by-using-apple-configurator"></a>Bezpośrednie rejestrowanie urządzeń z systemem iOS przy użyciu programu Apple Configurator

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Usługa Intune obsługuje rejestrowanie firmowych urządzeń z systemem iOS przy użyciu narzędzia [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) działającego na komputerze Mac. Ten proces nie powoduje przywrócenia ustawień fabrycznych urządzenia i powoduje zarejestrowanie urządzenia przy użyciu wstępnie zdefiniowanych zasad. Ta metoda jest przeznaczona dla urządzeń, których przynależność do użytkowników została ustawiona na wartość **Brak koligacji użytkownika** i wymaga podłączenia urządzenia z systemem iOS do komputera Mac przy użyciu połączenia USB w celu skonfigurowania rejestracji firmowej.

W przypadku bezpośredniego rejestrowania urządzeń z systemem iOS możesz zarejestrować urządzenie bez uzyskiwania jego numeru seryjnego. Możesz też nazwać urządzenie w celach identyfikacyjnych, zanim usługa Intune przechwyci nazwę urządzenia podczas rejestracji. Aplikacja Portal firmy nie jest obsługiwana w przypadku urządzeń, które zostały zarejestrowane bezpośrednio. W tych wskazówkach przyjęto założenie, że używany jest program Apple Configurator 2.0 na komputerze Mac.

>[!NOTE]
>Tej metody rejestracji nie można używać z metodą korzystającą z [menedżera rejestracji urządzeń](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).

1.  Jeśli jeszcze tego nie zrobiono, utwórz profil rejestracji dla urządzeń z systemem iOS rejestrowanych przy użyciu programu Apple Configurator. Profil rejestracji urządzeń określa ustawienia stosowane do urządzeń.

    1.  W [konsoli administracyjnej usługi Microsoft Intune](https://manage.microsoft.com) wybierz pozycję **Zasady** &gt; **Rejestracja urządzeń firmowych**, a następnie wybierz pozycję **Dodaj**.

        ![Tworzenie strony profilu rejestracji urządzenia](../media/pol-sa-corp-enroll.png)

    2.  Wprowadź szczegóły profilów urządzeń:

        -   **Nazwa**: nazwa profilu rejestracji urządzeń. Niewidoczne dla użytkowników.

        -   **Opis**: opis profilu rejestracji urządzeń. Niewidoczne dla użytkowników.

        -   **Przynależność do użytkownika**: określa sposób rejestracji urządzeń. W celu bezpośredniej rejestracji wybierz pozycję **Brak koligacji użytkownika**.

        -   **Wstępne przypisanie do grupy urządzeń**: wszystkie urządzenia, które mają ten profil, będą początkowo należeć do tej grupy. Po rejestracji można ponownie przypisać urządzenia.

            [!INCLUDE[groups deprecated](../includes/group-deprecation.md)]

    3.  Wybierz pozycję **Zapisz profil**, aby dodać profil.

5.  Eksportowanie profilu jako pliku mobileconfig do wdrożenia na urządzeniach z systemem iOS:

    1.   Wybierz utworzony profil urządzenia.

    2.   Na pasku zadań kliknij przycisk **Eksportuj**.

    3.   Wybierz pozycję **Pobierz profil** i zapisz pobrany plik mobileconfig.

6.  Przetransferuj plik, kopiując pobrany plik mobileconfig na komputer Mac.
    > [!NOTE]
    > Adres URL profilu rejestracji jest ważny przez dwa tygodnie od momentu jego wyeksportowania. Po dwóch tygodniach należy wyeksportować nowy adres URL profilu rejestracji, aby zarejestrować urządzenia z systemem iOS przy użyciu Asystenta ustawień.

7.  Przygotuj urządzenie przy użyciu programu Apple Configurator. Urządzenia z systemem iOS są podłączane do komputera Mac i rejestrowane w usłudze zarządzania urządzeniami przenośnymi.

    1.  Na komputerze Mac otwórz narzędzie **Apple Configurator 2.0**.

    2.  Podłącz urządzenia z systemem iOS do komputera Mac przy użyciu kabla USB. Zamknij aplikacje **Photos** (Zdjęcia), **iTunes** i inne aplikacje otwarte na urządzeniu po jego wykryciu.

    3.  W programie Apple Configurator wybierz podłączone urządzenie z systemem iOS, a następnie wybierz przycisk **Add** (Dodaj). Opcje, które można dodać do urządzenia, są wyświetlane na liście rozwijanej. Wybierz pozycję **Profiles** (Profile).

    4.  Użyj selektora plików w celu wybrania pliku mobileconfig wyeksportowanego za pomocą usługi Intune, a następnie wybierz pozycję **Add** (Dodaj). Profil zostanie dodany do urządzenia.  Jeśli urządzenie jest **nienadzorowane**, instalacja będzie wymagać akceptacji na urządzeniu.

8.  Wszystko jest gotowe do zainstalowania profilu na urządzeniu z systemem iOS. Na urządzeniu musi zostać zakończona praca Asystenta ustawień i musi być one gotowe do użycia. Jeśli rejestracja wiąże się z wdrożeniami aplikacji, urządzenie powinno mieć ustawiony identyfikator firmy Apple, ponieważ wdrożenia aplikacji będą wymagać posiadania identyfikatora Apple ID powiązanego ze sklepem App Store.

    1.  Odblokuj urządzenie z systemem iOS.

    2.  W oknie dialogowym **Instalacja profilu** dla pola **Profil zarządzania** wybierz pozycję **Zainstaluj**.

    3.  Podaj **kod dostępu urządzenia** lub **identyfikator Apple ID**, jeśli jest to wymagane.

    4.  Zaakceptuj **ostrzeżenie** i wybierz pozycję **Zainstaluj**.

    5.  Zaakceptuj **ostrzeżenie zdalne** i wybierz pozycję **Ufaj**.

    6.  Wyświetlenie okna dialogowego **Profil został zainstalowany** oznacza, że profil został **zainstalowany**. Wybierz pozycję **Gotowe**.

9.  Na urządzeniu z systemem iOS otwórz pozycję **Ustawienia** i przejdź do pozycji **Ogólne** &gt; **Zarządzanie urządzeniem** &gt; **Profil zarządzania**. Upewnij się, że instalacja profilu jest wymieniona na liście, a następnie sprawdź ograniczenia zasad systemu iOS i zainstalowane aplikacje. Wyświetlenie ograniczeń zasad i aplikacji na urządzeniu może potrwać do 10 minut.

10.  Rozdystrybuuj urządzenia. Urządzenie z systemem iOS jest teraz zarejestrowane w usłudze Intune i zarządzane przez tę usługę.
