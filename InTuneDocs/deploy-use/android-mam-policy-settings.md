---
title: "Ustawienia zasad zarządzania aplikacjami mobilnymi systemu Android | Microsoft Intune"
description: "W tym temacie opisano ustawienia zasad zarządzania aplikacjami mobilnymi dla urządzeń z systemem Android."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5dbb702a-1df5-4637-95c9-77a5f0b1a0e3
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 13477a66ca8e89345334476445aae037ea8d9702
ms.openlocfilehash: 55bf3ebde7d1185aebdb874c46aae72d8e179d85


---

# <a name="android-mobile-app-management-policy-settings-in-microsoft-intune"></a>Ustawienia zasad zarządzania aplikacjami mobilnymi systemu Android w usłudze Microsoft Intune
Opisane w tym temacie ustawienia zasad można [skonfigurować](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) dla zasad zarządzania aplikacjami mobilnymi w bloku **Ustawienia** witryny Azure Portal.
Istnieją dwie kategorie ustawień zasad: relokacja danych i dostęp. W tym temacie termin *aplikacje zarządzane przez zasady* dotyczy aplikacji konfigurowanych przy użyciu zasad zarządzania aplikacjami mobilnymi.

##  <a name="data-relocation-settings"></a>Ustawienia relokacji danych

- **Nie zezwalaj na kopie zapasowe systemu Android:** Wybierz opcję **Tak**, aby wyłączyć tworzenie kopii zapasowych, lub opcję **Nie**, aby włączyć tworzenie kopii zapasowych danych firmy z aplikacji zarządzanych przez zasady.

  Wartość domyślna: **Tak**
- **Zezwalaj aplikacji na przesyłanie danych do innych aplikacji:** wybierz jedną z opcji, aby określić typy aplikacji, które mogą odbierać dane firmy z aplikacji zarządzanych przez zasady:
  -   **Aplikacje zarządzane przez zasady**: włącza przesyłanie danych tylko do aplikacji z zasadami MAM.
  -   **Wszystkie aplikacje**: włącza przesyłanie danych do wszystkich aplikacji.
  -   **Brak:** nie zezwala na przesyłanie danych do żadnej aplikacji.

 Wartość domyślna: **Aplikacje zarządzane przez zasady**.
- **Zezwalaj aplikacji na odbieranie danych z innych aplikacji:** określ aplikacje, które mogą przesyłać dane do aplikacji zarządzanych przez zasady:
  -   **Aplikacje zarządzane przez zasady**: włącza przesyłanie danych tylko z innych aplikacji zarządzanych przez zasady.
  -   **Wszystkie aplikacje**: włącza przesyłanie danych z wszystkich aplikacji.
  -   **Brak**: nie zezwala na przesyłanie danych z żadnej aplikacji.

  Wartość domyślna: **Wszystkie aplikacje**

-   **Nie zezwalaj na używanie polecenia Zapisz jako:** Wybierz pozycję **Tak**, aby zablokować używanie opcji Zapisz jako we wszystkich aplikacjach korzystających z tych zasad. Wybierz opcję **Nie**, jeśli chcesz włączyć używanie polecenia Zapisz jako.

  Wartość domyślna: **Tak**
- **Ogranicz wycinanie, kopiowanie i wklejanie w innych aplikacjach:** określ sytuacje, w których akcje wycinania, kopiowania i wklejania powinny być ograniczone. Wybierz spośród opcji:
  -   **Zablokowane:** nie zezwala na akcje wycinania, kopiowania i wklejania między aplikacjami zarządzanymi przez zasady.
  -   **Aplikacje zarządzane przez zasady:** włącza akcje wycinania, kopiowania i wklejania tylko między aplikacjami zarządzanymi przez zasady.
  -   **Aplikacje zarządzane przez zasady z funkcją wklejania**: włącza wycinanie i kopiowanie między aplikacjami zarządzanymi przez zasady. Włącza wklejanie w tej aplikacji danych wyciętych lub skopiowanych z dowolnych aplikacji.
  -   **Dowolna aplikacja**: nie ma ograniczeń dotyczących akcji wycinania, kopiowania i wklejania między dowolnymi aplikacjami.

  Wartość domyślna: **aplikacje zarządzane przez zasady z funkcją wklejania**
-   **Ogranicz zawartość sieci Web do wyświetlenia w programie Managed Browser:** wybierz opcję **tak**, aby ustalić, że wszystkie linki w aplikacji będą otwierane w programie Managed Browser.

  W przypadku urządzeń, które nie są zarejestrowane w usłudze Intune, linki w aplikacjach zarządzanych przez zasady będą otwierane tylko w aplikacji Managed Browser, jeśli użytkownika korzysta z zasad zarządzania aplikacjami mobilnymi.

  Jeśli używasz usługi Intune do zarządzania swoimi urządzeniami, zobacz [Zarządzanie dostępem do Internetu za pomocą zasad programu Managed Browser w usłudze Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).

  Wartość domyślna: **Tak**
- **Szyfruj dane aplikacji:** wybierz pozycję **Tak**, aby włączyć szyfrowanie. W przypadku włączenia tego ustawienia firma Microsoft zapewni szyfrowanie dla aplikacji, które są skojarzone z zasadami zarządzania aplikacjami mobilnymi. Dane są szyfrowane synchronicznie podczas zadań wejścia/wyjścia na plikach. Zawartość w pamięci urządzenia jest zawsze zaszyfrowana.
  >[!NOTE]
  >Metoda szyfrowania nie ma certyfikatu FIPS 140-2.

  Wartość domyślna: **Tak**

- **Wyłącz synchronizację kontaktów:** wybierz pozycję **Tak**, aby uniemożliwić synchronizowanie informacji kontaktowych z aplikacją natywnej książki adresowej na urządzeniu. W przypadku wybrania pozycji **Nie** aplikacja zapisze dane kontaktowe w aplikacji natywnej książki adresowej na urządzeniu.

  Wykonanie selektywnego czyszczenia w celu usunięcia danych firmy powoduje usunięcie kontaktów zsynchronizowanych bezpośrednio między aplikacją i natywną książką adresową. Nie można wyczyścić wszystkich kontaktów zsynchronizowanych między natywną książką adresową i innym źródłem zewnętrznym. Obecnie dotyczy to tylko aplikacji Microsoft Outlook.

  Wartość domyślna: **Tak**
- **Wyłącz drukowanie:** wybierz pozycję **Tak**, aby uniemożliwić drukowanie danych firmowych z poziomu aplikacji skojarzonych z zasadami zarządzania aplikacjami mobilnymi.

  Wartość domyślna: **Tak**

##  <a name="access-settings"></a>Ustawienia dostępu

- **Wymagaj numeru PIN w celu udzielenia dostępu:** wybierz pozycję **Tak**, aby wymagać numeru PIN do korzystania z aplikacji zarządzanych przez zasady. Użytkownik zostanie poproszony o skonfigurowanie tego numeru przy pierwszym uruchomieniu aplikacji w kontekście pracy.

 Wartość domyślna: **Tak**

 -  **Zezwalaj na prosty numer PIN**: określ, czy użytkownicy mogą używać prostych sekwencji numeru PIN, takich jak 1234 lub 1111. Wartość domyślna: **Tak**.
 - **Długość numeru PIN:** określ minimalną liczbę cyfr numeru PIN. Wartość domyślna: **4**.
 - **Liczba prób przed zresetowaniem numeru PIN:** określ liczbę prób wprowadzenia numeru PIN, po której użytkownik musi zresetować ten numer. To ustawienie nie ma wartości domyślnej.
 - **Wymagaj odcisku palca zamiast numeru PIN (system Android 6.0 i nowsze):** wybierz opcję **Tak**, aby wymagać potwierdzenia tożsamości odciskiem palca zamiast numerem PIN w celu uzyskania dostępu do aplikacji.
 Na urządzeniach z systemem Android możesz zezwolić użytkownikom na identyfikację za pomocą linii papilarnych zamiast identyfikacji przy użyciu numeru PIN. Gdy użytkownik podejmie próbę uzyskania dostępu do aplikacji przy użyciu konta służbowego, otrzyma monit o potwierdzenie tożsamości odciskiem palca, a nie numerem PIN.
 - **Wymagaj poświadczeń firmowych w celu udzielenia dostępu:** wybierz pozycję **Tak**, aby wymagać poświadczeń firmowych zamiast identyfikacji za pomocą numeru PIN lub linii papilarnych w celu uzyskania dostępu do aplikacji. Wybranie ustawienia **Tak** zastępuje wymagania dotyczące numeru PIN lub funkcji Touch ID. Użytkownik zostanie poproszony o podanie swoich poświadczeń firmowych. Wartość domyślna: **Nie**.


- **Blokuj uruchamianie aplikacji zarządzanych na urządzeniach, na których zdjęto zabezpieczenia systemu lub uzyskano dostęp do konta root:** wybierz pozycję **Tak**, aby blokować uruchamianie aplikacji na urządzeniach, na których zdjęto zabezpieczenia systemu lub uzyskano dostęp do konta root. Użytkownik będzie mógł korzystać z aplikacji do zadań osobistych, ale będzie musiał używać innego urządzenia do pracy.

  Wartość domyślna: **Tak**
- **Ponownie sprawdź wymagania dostępu po (w minutach)**
  -   **Limit czasu:** określ czas (w minutach) przed ponownym sprawdzeniem wymagań dostępu do aplikacji.
  -   **Okres karencji w trybie offline:** jeśli urządzenie znajduje się w trybie offline, określ czas (w minutach) przed ponownym sprawdzeniem wymagań dostępu do aplikacji.

  Wartości domyślne: limit czasu — **30** minut, okres karencji w trybie offline — **720** minut

-   **Interwał offline przed wyczyszczeniem danych aplikacji (w dniach):** wyczyść dane firmowe w przypadku, gdy urządzenie znajdowało się w trybie offline przez wybrany okres.  W bloku ustawień zasad możesz określić liczbę dni, przez które urządzenie może pozostawać w trybie offline przed usunięciem z niego danych firmowych.

    >[!TIP]
    >Wprowadzenie wartości **0** spowoduje wyłączenie tego ustawienia.

  Wartość domyślna: **90** dni
- **Zablokuj przechwytywanie ekranu i asystenta systemu Android (system Android 6 Marshmallow lub nowszy):** wybierz pozycję **Tak**, aby zablokować przechwytywanie ekranu i możliwości **asystenta systemu Android** podczas korzystania z tej aplikacji.



<!--HONumber=Nov16_HO2-->


