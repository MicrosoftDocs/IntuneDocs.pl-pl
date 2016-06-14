---
# required metadata

title: Bezpośrednia rejestracja urządzeń z systemem iOS w usłudze Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a692b90c-72ae-47d1-ba9c-67a2e2576cc2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Bezpośrednie rejestrowanie urządzeń z systemem iOS przy użyciu programu Apple Configurator
Usługa Intune obsługuje rejestrowanie firmowych urządzeń z systemem iOS przy użyciu narzędzia [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) działającego na komputerze Mac. Ten proces nie powoduje przywrócenia ustawień fabrycznych urządzenia i powoduje zarejestrowanie urządzenia przy użyciu wstępnie zdefiniowanych zasad. Ta metoda jest przeznaczona dla urządzeń, których przynależność do użytkowników została ustawiona na wartość **Brak koligacji użytkownika** i wymaga podłączenia urządzenia z systemem iOS do komputera Mac przy użyciu połączenia USB w celu skonfigurowania rejestracji firmowej. Aplikacja Portal firmy nie jest obsługiwana w przypadku urządzeń, które zostały zarejestrowane bezpośrednio. W tych wskazówkach przyjęto założenie, że używany jest program Apple Configurator 2.0 na komputerze Mac.

1.  **Tworzenie profilów dla urządzeń**
    Profil rejestracji urządzeń określa ustawienia stosowane do urządzeń. Jeśli jeszcze tego nie zrobiono, utwórz profil rejestracji dla urządzeń z systemem iOS rejestrowanych przy użyciu programu Apple Configurator.

    #### Aby utworzyć profil

    1.  W [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) wybierz kolejno pozycje **Zasady** &gt; **Rejestracja urządzeń firmowych**, a następnie kliknij pozycję **Dodaj**.

        ![Tworzenie strony profilu rejestracji urządzenia](../media/pol-sa-corp-enroll.png)

    2.  Wprowadź szczegóły profilów urządzeń:

        -   **Nazwa** — nazwa profilu rejestracji urządzeń. Niewidoczne dla użytkowników.

        -   **Opis** — opis profilu rejestracji urządzeń. Niewidoczne dla użytkowników.

        -   **Przynależność do użytkownika** — określa sposób rejestracji urządzeń. W celu bezpośredniej rejestracji wybierz pozycję **Brak koligacji użytkownika**..

        -   **Wstępne przypisanie do grupy urządzeń** — wszystkie urządzenia, dla których ten profil zostanie wdrożony, będą początkowo należeć do tej grupy. Po rejestracji można ponownie przypisać urządzenia.

    3.  Kliknij przycisk **Zapisz profil** , aby dodać profil.

2.  **Dodawanie urządzeń z systemem iOS do rejestracji przy użyciu Asystenta ustawień**
    W [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) wybierz kolejno pozycje **Grupy** &gt; **Wszystkie urządzenia** &gt; **Wszystkie urządzenia zarejestrowane wstępnie należące do firmy** &gt; **Według numeru seryjnego systemu iOS**, a następnie kliknij pozycję **Dodaj urządzenia**.

    ![Asystent ustawień systemu iOS](../media/pol-SA-enroll-iOS-SetupAssistant.png)

      Urządzenia można dodać na dwa sposoby:

    -   **Przekaż plik CSV zawierający numery seryjne** — utwórz listę wartości oddzielanych przecinkami (plik csv) w dwóch kolumnach bez nagłówka ograniczoną do 5000 urządzeń lub 5 MB na plik CSV.

        |||
        |-|-|
        |&lt;Numer seryjny 1&gt;|&lt;Szczegóły urządzenia 1&gt;|
        |&lt;Numer seryjny 2&gt;|&lt;Szczegóły urządzenia 2&gt;|
        Ten plik CSV wyświetlony w edytorze tekstu wygląda następująco:

        ```
        0000000,PO 1234
        111111111,PO 1234
        ```

    -   **Ręcznie dodaj szczegóły urządzeń** — wprowadź numer seryjny i szczegóły maksymalnie pięciu urządzeń, a następnie kliknij przycisk **Dalej**..

    > [!NOTE]
    > Jeśli w przyszłości konieczne okaże się usunięcie urządzeń należących do firmy z zakresu zarządzania usługi Intune, należy usunąć numer seryjny urządzenia z usługi Intune w grupie **Urządzenia należące do firmy**, aby wyłączyć rejestrację urządzenia.  Jeśli usługa Intune przeprowadza procedurę odzyskiwania po awarii w przedziale czasowym zbliżonym do momentu usuwania numerów seryjnych, należy sprawdzić, czy w tej grupie znajdują się wyłącznie numery seryjne aktywnych urządzeń.

3.  **Wybieranie urządzeń do zarejestrowania**
    Potwierdź urządzenia przeznaczone do zarejestrowania. Nie można zaimportować numerów seryjnych, które są już zarejestrowane lub zostały zarejestrowane w inny sposób. Kliknij przycisk **Dalej** , aby kontynuować.

4.  **Przypisywanie profilu**
    Z listy dostępnych profilów wybierz profil, który ma zostać przypisany do dodanych urządzeń, sprawdź informacje w obszarze **Szczegóły profilu rejestracji**(Zarządzanie serwerami), a następnie kliknij pozycję **Zakończ**. Ręcznie dodane urządzenia można przypisać do dowolnego profilu rejestracji.

5.  **Wybieranie profilu do wdrożenia na urządzeniach z systemem iOS**
    W [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) przejdź do pozycji **Zasady** &gt; **Rejestracja urządzeń firmowych** i wybierz profil urządzeń, który ma być wdrażany na urządzeniach przenośnych. Ten profil powinien być taki sam jak profil przypisany do wdrożenia w poprzednim kroku. Kliknij przycisk **Eksportuj...**. na pasku zadań. Kliknij pozycję **Pobierz profil** i zapisz pobrany plik mobileconfig.

6.  **Transferowanie pliku**
    Skopiuj pobrany plik mobileconfig na komputer Mac.
    > [!NOTE]
    > Adres URL profilu rejestracji jest ważny przez dwa tygodnie od momentu jego wyeksportowania. Po dwóch tygodniach należy wyeksportować nowy adres URL profilu rejestracji, aby zarejestrować urządzenia z systemem iOS przy użyciu Asystenta ustawień.
7.  **Przygotowywanie urządzenia przy użyciu programu Apple Configurator**
    Urządzenia z systemem iOS są podłączane do komputera Mac i rejestrowane w usłudze zarządzania urządzeniami przenośnymi.

    1.  Na komputerze Mac otwórz program **Apple Configurator 2.0**.

    2.  Podłącz urządzenia z systemem iOS do komputera Mac przy użyciu kabla USB. Zamknij aplikacje **Photos** (Zdjęcia), **iTunes** i inne aplikacje otwarte na urządzeniu po jego wykryciu.

    3.  W programie Apple Configurator kliknij raz podłączone urządzenie z systemem iOS, a następnie kliknij pozycję **Add** (Dodaj). Opcje, które można dodać do urządzenia, są wyświetlane na liście rozwijanej. Kliknij pozycję **Profiles** (Profile). .

    4.  Użyj selektora plików do wybrania pliku mobileconfig wyeksportowanego za pomocą usługi Intune, a następnie kliknij przycisk **Add** (Dodaj). Profil zostanie dodany do urządzenia.  Jeśli urządzenie jest **nienadzorowane**, instalacja będzie wymagać akceptacji na urządzeniu.

8.  **Instalowanie profilu**
    Wszystko jest gotowe do zainstalowania profilu na urządzeniu z systemem iOS. Na urządzeniu musi zostać zakończona praca Asystenta ustawień i musi być one gotowe do użycia.  Jeśli rejestracja wiąże się z wdrożeniami aplikacji, urządzenie powinno mieć ustawiony identyfikator firmy Apple, ponieważ wdrożenia aplikacji będą wymagać posiadania identyfikatora Apple ID powiązanego ze sklepem App Store.

    ###### Kończenie akceptacji profilu dla nienadzorowanych urządzeń z systemem iOS

    1.  Odblokuj urządzenie z systemem iOS.

    2.  W oknie dialogowym **Instalowanie profilu** dla pozycji **Profil zarządzania** naciśnij pozycję **Zainstaluj**..

    3.  Podaj **kod dostępu urządzenia** lub **identyfikator Apple ID**, jeśli jest to wymagane.

    4.  Zaakceptuj **ostrzeżenie** i naciśnij pozycję **Zainstaluj**..

    5.  Zaakceptuj **ostrzeżenie zdalne** i naciśnij pozycję **Ufaj**..

    6.  Wyświetlenie okna dialogowego **Profil został zainstalowany** oznacza, że profil został **zainstalowany**. Kliknij pozycję **Gotowe**..

9. **Weryfikowanie profilu**
    Na urządzeniu z systemem iOS kliknij pozycję **Ustawienia**, kliknij kolejno pozycje **Ogólne** &gt; **Zarządzanie urządzeniami** &gt; **Profil zarządzania** &gt; i potwierdź, że instalacja profilu znajduje się na liście, a następnie sprawdź ograniczenia zasad systemu iOS oraz zainstalowane aplikacje. Wyświetlenie ograniczeń zasad i aplikacji na urządzeniu może potrwać do 10 minut.

10. **Dystrybuowanie urządzeń**
    Urządzenie z systemem iOS jest teraz zarejestrowane w usłudze Intune i zarządzane przez tę usługę.


### Zobacz także
[Przygotowanie do rejestracji urządzeń](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


