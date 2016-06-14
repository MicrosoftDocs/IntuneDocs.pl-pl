---
# required metadata

title: Rejestracja urządzeń z systemem iOS przy użyciu Asystenta ustawień w usłudze Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 46e5b027-4280-4809-b45f-651a6ab6d0cd

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Rejestracja urządzeń z systemem iOS w narzędziu Apple Configurator przy użyciu Asystenta ustawień
Usługa Intune obsługuje rejestrowanie firmowych urządzeń z systemem iOS przy użyciu narzędzia [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) działającego na komputerze Mac. Ten proces powoduje przywrócenie ustawień fabrycznych urządzenia i przygotowuje je do uruchomienia Asystenta ustawień przez nowego użytkownika urządzenia ze wstępnie zainstalowanymi zasadami firmy.


## Rejestrowanie urządzeń z systemem iOS przy użyciu Asystenta ustawień w usłudze Microsoft Intune
Za pomocą programu Apple Configurator można zresetować urządzenia z systemem iOS do ustawień fabrycznych i przygotować je do skonfigurowania przez nowego użytkownika.  Ta metoda wymaga podłączenia urządzenia z systemem iOS do komputera Mac przy użyciu połączenia USB w celu skonfigurowania rejestracji firmowej. Przyjęto założenie, że używany jest program Apple Configurator 2.0. Większość scenariuszy wymaga, aby zasady zastosowane w urządzeniu z systemem iOS uwzględniały *koligację użytkownika*, co umożliwia korzystanie z aplikacji Portal firmy usługi Intune.

**Wymagania wstępne**
* Fizyczny dostęp do urządzeń z systemem iOS — urządzenia muszą być w stanie nieskonfigurowanym (resetowanie do ustawień fabrycznych) bez ochrony hasłem
* Numery seryjne — [w jaki sposób uzyskać numer seryjny systemu iOS](https://support.apple.com/en-us/HT204308)
* Kable połączenia USB
* Komputer Mac z programem [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)


1.  **Utwórz grupę urządzeń przenośnych** (opcjonalnie)
    Jeśli w firmie grupy urządzeń przenośnych są wymagane w celu ułatwienia zarządzania urządzeniami, utwórz te grupy. [Używanie grup do zarządzania użytkownikami i urządzeniami w usłudze Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

2.  **Tworzenie profilów dla urządzeń**
    Profil rejestracji urządzeń określa ustawienia stosowane do grupy urządzeń. Jeśli jeszcze tego nie zrobiono, utwórz profil rejestracji dla urządzeń z systemem iOS rejestrowanych przy użyciu programu Apple Configurator.

    ###### Aby utworzyć profil

    1.  W [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) wybierz kolejno pozycje **Zasady** &gt; **Urządzenia należące do firmy**, a następnie kliknij pozycję **Dodaj**.

    ![Tworzenie profilu rejestracji urządzenia](../media/pol-sa-corp-enroll.png)

    2.  Wprowadź szczegóły profilów urządzeń:

        -   **Nazwa** — nazwa profilu rejestracji urządzeń. (niewidoczny dla użytkowników)

        -   **Opis** — opis profilu rejestracji urządzeń. (niewidoczny dla użytkowników)

        -   **Szczegóły rejestracji** — określa sposób rejestracji urządzeń.

            -   **Monituj o koligację użytkownika** — podczas początkowej konfiguracji można określić przynależność urządzenia z systemem iOS do użytkownika i zezwolić na dostęp tego urządzenia do danych firmowych i poczty e-mail jako ten użytkownik. W przypadku większości scenariuszy Asystenta ustawień użyj trybu **Monituj o koligację użytkownika**..
            W tym trybie jest obsługiwanych kilka scenariuszy:

                -   **Urządzenie osobiste należące do firmy** — model „Wybierz własne urządzenie” (CYOD, Choose Your Own Device). Scenariusz podobny do stosowania prywatnych lub osobistych urządzeń, ale administrator ma określone uprawnienia, w tym uprawnienia do administrowania urządzeniem oraz czyszczenia, resetowania i wyrejestrowywania urządzenia. Użytkownik urządzenia może instalować aplikacje i ma większość pozostałych uprawnień do korzystania z urządzenia, oprócz zablokowanych zgodnie z zasadami zarządzania.

                -   **Konto menedżera rejestracji urządzeń** — urządzenie jest rejestrowane przy użyciu specjalnego konta administratora usługi Intune. Można nim zarządzać jak kontem prywatnym, ale tylko użytkownik, który zna poświadczenia menedżera rejestracji można instalować aplikacje i administrować urządzeniem oraz czyścić, resetować i wyrejestrowywać urządzenie. Informacje dotyczące rejestrowania urządzenia udostępnianego wielu użytkownikom za pomocą wspólnego konta można znaleźć w temacie [Rejestrowanie urządzeń należących do firmy przy użyciu menedżera rejestracji urządzeń w usłudze Microsoft Intune](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)..

            -   **Bez koligacji użytkownika** — urządzenie nie przynależy do żadnego użytkownika. Tego typu przynależności należy użyć w przypadku urządzeń wykonujących zadania bez uzyskiwania dostępu do danych użytkowników lokalnych. Aplikacje wymagające przynależności do użytkownika są wyłączone lub nie będą działać.

        -   **Wstępne przypisanie do grupy urządzeń** — wszystkie urządzenia, dla których ten profil zostanie wdrożony, będą początkowo należeć do tej grupy. Po rejestracji można ponownie przypisać urządzenia.

          -  **Device Enrollment Program** — program Device Enrollment Program (DEP) firmy Apple nie może być używany z rejestracją z wykorzystaniem Asystenta ustawień. Upewnij się, że przełącznik jest **wyłączony**..

    3.  Kliknij przycisk **Zapisz profil** , aby dodać profil.

3.  **Dodawanie urządzenia z systemem iOS do rejestracji przy użyciu Asystenta ustawień**
    W [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) wybierz kolejno pozycje **Grupy** &gt; **Wszystkie urządzenia** &gt; **Wszystkie urządzenia należące do firmy** &gt; **Wszystkie urządzenia**, a następnie kliknij pozycję **Dodaj urządzenia**. Urządzenia można dodać na dwa sposoby:

    ![Okno dialogowe dodawania urządzeń](../media/pol-SA-enroll-iOS-SetupAssistant.png)

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

    -   **Ręcznie dodaj szczegóły urządzeń** — wprowadź numery seryjne i szczegóły maksymalnie pięciu urządzeń.

    > [!NOTE]
    > Jeśli w przyszłości konieczne okaże się usunięcie urządzeń należących do firmy z zakresu zarządzania usługi Intune, konieczne może być usunięcie numeru seryjnego urządzenia z usługi Intune w grupie **Urządzenia należące do firmy**, aby wyłączyć rejestrację urządzenia.  Jeśli usługa Intune przeprowadza procedurę odzyskiwania po awarii w przedziale czasowym zbliżonym do momentu usuwania numerów seryjnych, należy sprawdzić, czy w tej grupie znajdują się wyłącznie numery seryjne aktywnych urządzeń.

    Następnie kliknij przycisk **Dalej**..

4.  **Wybieranie urządzeń do zarejestrowania**
    Potwierdź urządzenia przeznaczone do zarejestrowania. Nie można zaimportować numerów seryjnych, które są już zarejestrowane lub zostały zarejestrowane w inny sposób. Kliknij przycisk **Dalej** , aby kontynuować.

5.  **Przypisywanie profilu**
    Z listy dostępnych profilów wybierz profil, który ma zostać przypisany do dodanych urządzeń, sprawdź informacje w obszarze **Szczegóły profilu rejestracji**(Zarządzanie serwerami), a następnie kliknij pozycję **Zakończ**. Ręcznie dodane urządzenia można przypisać do dowolnego profilu rejestracji.

6.  **Eksportowanie profilu do wdrożenia na urządzeniach z systemem iOS**
    W [konsoli administracyjnej usługi Microsoft Intune](http://manage.microsoft.com) przejdź do pozycji **Zasady** &gt; **Rejestracja urządzeń firmowych** i wybierz profil urządzeń, który ma być wdrażany na urządzeniach przenośnych. Kliknij przycisk **Eksportuj...**. na pasku zadań. Skopiuj i zapisz adres w polu **Adres URL profilu**. Możesz przekazać go później przy użyciu narzędzia Apple Configurator, aby określić profil usługi Intune używany przez urządzenia z systemem iOS.
    Aby umożliwić obsługę programu Apple Configurator 2, należy edytować adres URL profilu 2.0. Zastąp
    ```
    https://manage.microsoft.com/EnrollmentServer/Discovery.svc/iOS/ESProxy?id=
    ```
    z programem

    ```
    https://appleconfigurator2.manage.microsoft.com/MDMServiceConfig?id=
    ```

   Możesz przekazać ten adres URL profilu do programu Apple DEP za pomocą narzędzia Apple Configurator, aby zdefiniować profil usługi Intune używany przez urządzenia z systemem iOS, używając poniższej procedury.

    > [!NOTE]
    > Adres URL profilu rejestracji jest ważny przez dwa tygodnie od momentu jego wyeksportowania. Po dwóch tygodniach należy wyeksportować nowy adres URL profilu rejestracji, aby zarejestrować urządzenia z systemem iOS przy użyciu Asystenta ustawień.

7.  **Przygotowywanie urządzenia przy użyciu programu Apple Configurator**
    Urządzenia z systemem iOS są podłączane do komputera Mac i rejestrowane w usłudze zarządzania urządzeniami przenośnymi.

    1.  Na komputerze Mac otwórz narzędzie **Apple Configurator 2**. Na pasku menu kliknij pozycję **Apple Configurator 2**, a następnie kliknij pozycję **Preferencje**..

         > [!WARNING]
         > Podczas procesu rejestracji urządzenia zostaną zresetowane do konfiguracji fabrycznych. Jako najlepsze rozwiązanie zalecane jest zresetowania urządzenia i włączenie go. Jako najlepsze rozwiązanie zalecane jest również, aby podczas podłączania na urządzeniach był wyświetlany ekran **powitania**.

    2. W okienku preferencji wybierz pozycję **Serwery** i kliknij symbol „+” pod lewym okienkiem, aby uruchomić Kreatora serwera MDM. Kliknij przycisk **Dalej**..

    3. Wprowadź **nazwę** i **adres URL rejestracji** dla serwera MDM z kroku 6 powyżej. W polu adresu URL rejestracji wprowadź adres URL profilu rejestracji wyeksportowany z usługi Intune. Kliknij przycisk **Dalej**..  

       Jeśli zostanie wyświetlone ostrzeżenie o wymaganiach dotyczących profilu zaufanego dla Apple TV, możesz bezpiecznie anulować opcję **Zaufany profil**, klikając szary symbol „X”. Możesz również bezpiecznie pominąć wszelkie ostrzeżenia dotyczące certyfikatu zakotwiczenia. Aby kontynuować, klikaj przycisk **Dalej**, aż do ukończenia pracy kreatora.

    4.  W okienku **Serwery** kliknij pozycję „Edytuj” obok profilu nowego serwera. Upewnij się, że adres URL rejestracji dokładnie odpowiada adresowi URL wyeksportowanemu z usługi Intune. Jeśli adresy różnią się, wprowadź ponownie oryginalny adres URL i **zapisz** profil rejestracji wyeksportowany z usługi Intune.

    5.  Podłącz urządzenia przenośne z systemem iOS do komputera Apple przy użyciu adaptera USB.

        > [!WARNING]
        > Podczas procesu rejestracji urządzenia zostaną zresetowane do konfiguracji fabrycznych. Jako najlepsze rozwiązanie zalecane jest zresetowania urządzenia i włączenie go. Jako najlepsze rozwiązanie zalecane jest również, aby podczas uruchamiania Asystenta ustawień był wyświetlany ekran **powitania**.

    6.  Kliknij przycisk **Prepare**(Przygotuj). W okienku **Prepare iOS Device** (Przygotowywanie urządzenia z systemem iOS) wybierz pozycję **Manual** (Ręcznie), a następnie kliknij przycisk **Next** (Dalej)..

    7. W okienku **Enroll in MDM Server** (Rejestrowanie na serwerze MDM) wybierz nazwę utworzonego serwera, a następnie kliknij przycisk **Next** (Dalej)..

    8. W okienku **Supervise Devices** (Nadzorowanie urządzeń) wybierz poziom nadzoru, a następnie kliknij przycisk **Next** (Dalej)..

    9. W okienku **Create an Organization** (Tworzenie organizacji) wybierz wartość w polu **Organization** (Organizacja) lub utwórz nową organizację, a następnie kliknij przycisk **Next** (Dalej)..

    10. W okienku **Configure iOS Setup Assistant** (Konfigurowanie Asystenta ustawień systemu iOS) wybierz wyświetlone czynności, a następnie kliknij pozycję **Prepare** (Przygotuj). Jeśli zostanie wyświetlony monit, uwierzytelnij się w celu zaktualizowania ustawień zaufania.  

    11. Po zakończeniu przygotowywania urządzenia z systemem iOS można odłączyć kabel USB.  

8.  **Dystrybuowanie urządzeń**
    Urządzenia są teraz gotowe do rejestracji w firmie. Wyłącz urządzenia i przekaż je użytkownikom. Po włączeniu urządzenia zostanie uruchomiony Asystent ustawień.



### Zobacz także
[Przygotowanie do rejestracji urządzeń](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


