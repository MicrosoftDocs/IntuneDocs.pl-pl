---
title: "Ustawienia zasad zarządzania aplikacjami mobilnymi systemu Android | Microsoft Intune"
description: "W tym temacie opisano ustawienia zasad zarządzania aplikacjami mobilnymi dla urządzeń z systemem Android."
keywords: 
author: karthikaraman
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
ms.sourcegitcommit: 7313854dc9cee26412ed4759e570f0aecc5f156b
ms.openlocfilehash: e8b1ccca0c905ccdefd5c4a97b78561c6edb7908


---

# Ustawienia zasad zarządzania aplikacjami mobilnymi systemu Android w usłudze Microsoft Intune
Opisane poniżej ustawienia zasad można [skonfigurować](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) dla zasad zarządzania aplikacjami mobilnymi w bloku **Ustawienia** portalu Azure.
Istnieją dwie kategorie ustawień zasad, Relokacja danych i Dostęp:

##  Ustawienia relokacji danych
Termin **Aplikacje zarządzane przez zasady** dotyczy aplikacji konfigurowanych przy użyciu zasad zarządzania aplikacjami mobilnymi.
- **Nie zezwalaj na kopie zapasowe systemu Android:** Wybierz opcję **Tak**, aby wyłączyć tworzenie kopii zapasowych, lub opcję **Nie**, aby zezwalać na tworzenie kopii zapasowych danych firmy z aplikacji zarządzanych przez zasady.

  **Wartość domyślna = Tak**
- **Zezwalaj aplikacji na przesyłanie danych do innych aplikacji:** Wybierz jedną z opcji, aby określić aplikacje, które mogą odbierać dane firmy z aplikacji zarządzanych przez zasady:
  -   **Aplikacje zarządzane przez zasady:** zezwalaj na przesyłanie danych tylko do aplikacji mających zasady zarządzania aplikacjami mobilnymi
  -   **Wszystkie aplikacje**: zezwalaj na przesyłanie danych do wszystkich aplikacji
  -   **Brak:** nie zezwalaj na przesyłanie danych do żadnej aplikacji

  **Wartość domyślna = Aplikacje zarządzane przez zasady**
- **Zezwalaj aplikacji na odbieranie danych z innych aplikacji:** Określ aplikacje, które mogą przesyłać dane do aplikacji zarządzanych przez zasady:
  -   **Aplikacje zarządzane przez zasady:** Zezwalaj na przesyłanie danych tylko z innych aplikacji zarządzanych przez zasady
  -   **Wszystkie aplikacje:** Zezwalaj na przesyłanie danych z wszystkich aplikacji
  -   **Brak:** Nie zezwalaj na przesyłanie danych z żadnej aplikacji

      **Wartość domyślna = Wszystkie aplikacje**

-   **Nie zezwalaj na używanie polecenia Zapisz jako:** Wybierz opcję **Tak**, aby zablokować używanie polecenia Zapisz jako we wszystkich aplikacjach korzystających z tych zasad. Wybierz opcję **Nie**, jeśli chcesz zezwolić na używanie polecenia Zapisz jako.

  **Wartość domyślna = Tak**
- **Ogranicz wycinanie, kopiowanie i wklejanie w innych aplikacjach:** Określ sytuacje, w których operacje wycinania, kopiowania i wklejania powinny być ograniczone. Wybierz spośród opcji:
  -   **Zablokowane:** nie zezwalaj na operacje wycinania, kopiowania i wklejania między aplikacjami zarządzanymi przez zasady.
  -   **Aplikacje zarządzane przez zasady:** zezwalaj na operacje wycinania, kopiowania i wklejania tylko między aplikacjami zarządzanymi przez zasady.
  -   **Aplikacje zarządzane przez zasady z funkcją wklejania**: zezwalaj na wycinanie i kopiowanie między aplikacjami zarządzanymi przez zasady. Zezwalaj na wklejanie w tej aplikacji danych wyciętych lub skopiowanych z dowolnych aplikacji.
  -   **Dowolna aplikacja**: brak ograniczeń operacji wycinania, kopiowania i wklejania między dowolnymi aplikacjami.

    **Wartość domyślna = Aplikacje zarządzane przez zasady z funkcją wklejania**
-   **Ogranicz zawartość sieci Web do wyświetlenia w programie Managed Browser:** jeśli to ustawienie zostanie włączone, wszystkie linki w aplikacji będą otwierane w programie Managed Browser.

  W przypadku urządzeń, które nie są zarejestrowane w usłudze Intune, linki sieci Web w aplikacjach zarządzanych przez zasady będą otwierane tylko w aplikacji Managed Browser korzystającej z zasad zarządzania aplikacjami mobilnymi.

  Jeśli używasz usługi Intune do zarządzania swoimi urządzeniami, zobacz [Zarządzanie dostępem do Internetu za pomocą zasad programu Managed Browser w usłudze Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).

    **Wartość domyślna = Tak**
- **Szyfruj dane aplikacji:** Wybierz opcję **Tak**, aby włączyć szyfrowanie. W przypadku włączenia tego ustawienia dla aplikacji, które są skojarzone z zasadami zarządzania aplikacjami mobilnymi, szyfrowanie jest obsługiwane przez firmę Microsoft. Dane są szyfrowane synchronicznie podczas operacji wejścia/wyjścia na plikach. Zawartość w pamięci urządzenia zawsze jest zaszyfrowana.
  >[!NOTE]
  >Metoda szyfrowania nie ma certyfikatu FIPS 140-2

  **Wartość domyślna = Tak**

- **Wyłącz synchronizację kontaktów:** wybierz opcję **Tak**, aby uniemożliwić synchronizowanie informacji kontaktowych z aplikacją natywnej książki adresowej na urządzeniu. W przypadku wybrania opcji **Nie** aplikacja zapisuje dane kontaktowe w aplikacji natywnej książki adresowej urządzenia.<br/>Wykonanie selektywnego czyszczenia w celu usunięcia danych firmy powoduje usunięcie kontaktów zsynchronizowanych bezpośrednio z aplikacji do natywnej książki adresowej. Nie można wyczyścić wszystkich kontaktów zsynchronizowanych z natywnej książki adresowej do innego źródła zewnętrznego. Obecnie ta opcja ma zastosowanie tylko do aplikacji **Microsoft Outlook**.

  **Wartość domyślna = Tak**
- **Wyłącz drukowanie:** wybierz opcję **Tak**, aby uniemożliwić drukowanie danych firmowych z poziomu aplikacji skojarzonych z zasadami zarządzania aplikacjami mobilnymi.

  **Wartość domyślna — Tak**

##  Ustawienia zasad dostępu systemu Android
Termin **Aplikacje zarządzane przez zasady** dotyczy aplikacji skonfigurowanych przy użyciu zasad zarządzania aplikacjami mobilnymi.

- **Wymagaj numeru PIN w celu udzielenia dostępu:** wybierz pozycję **Tak**, aby wymagać numeru PIN do korzystania z aplikacji zarządzanych przez zasady. Użytkownik zostanie poproszony o skonfigurowanie tego numeru przy pierwszym uruchomieniu aplikacji w kontekście pracy.

 **Wartość domyślna = Tak**

 -  **Zezwalaj na prosty numer PIN**: określ, czy użytkownicy mogą używać prostych sekwencji numeru PIN, takich jak 1234 lub 1111. **Wartość domyślna: Tak**.
 - **Długość numeru PIN:** określ minimalną liczbę cyfr numeru PIN. **Wartość domyślna: 4**
 - **Liczba prób przed zresetowaniem numeru PIN:** określ liczbę prób wprowadzenia numeru PIN, po której użytkownik musi zresetować ten numer. **To ustawienie nie ma wartości domyślnej.**
- **Wymagaj poświadczeń firmowych w celu udzielenia dostępu:** wybierz opcję **Tak**, aby wymagać poświadczeń firmowych zamiast numeru PIN w celu uzyskania dostępu do aplikacji.  Wybranie opcji **Tak** przesłania wymagania dotyczące numeru PIN lub funkcji Touch ID.  Użytkownik zostanie poproszony o podanie swoich poświadczeń firmowych.

  **Wartość domyślna = Nie**
- **Blokuj uruchamianie aplikacji zarządzanych na urządzeniach, na których zdjęto zabezpieczenia systemu lub uzyskano dostęp do konta root:** wybierz opcję **Tak**, aby blokować uruchamianie aplikacji na urządzeniach, na których zdjęto zabezpieczenia systemu lub uzyskano dostęp do konta root. Użytkownik będzie mógł korzystać z aplikacji do zadań osobistych, ale będzie musiał używać innego urządzenia do pracy.

  **Wartość domyślna = Tak**
- **Ponownie sprawdź wymagania dostępu po (w minutach)**-   **Limit czasu:** Czas (w minutach) przed ponownym sprawdzeniem wymagań dostępu dla aplikacji.
  -   **Okres karencji w trybie offline:** jeśli urządzenie znajduje się w trybie offline, określ czas (w minutach) przed ponownym sprawdzeniem wymagań dostępu do aplikacji.

    **Wartości domyślne = limit czasu: 30 minut, okres karencji w trybie offline: 720 minut**

-   **Interwał offline przed wyczyszczeniem danych aplikacji (w dniach):** możesz zdecydować się na wyczyszczenie danych firmowych w przypadku przebywania urządzenia w trybie offline przez wybrany okres.  W bloku ustawień zasad możesz określić liczbę dni, przez które urządzenie może pozostawać w trybie offline przed usunięciem z niego danych firmowych. **Wskazówka:** wprowadzenie wartości 0 spowoduje wyłączenie tego ustawienia.

  **Wartość domyślna = 90 dni**
- **Zablokuj przechwytywanie ekranu i asystenta systemu Android (system Android 6 Marshmallow lub nowszy):** Wybierz opcję **Tak**, aby blokować przechwytywanie ekranu i funkcje **asystenta systemu Android** podczas korzystania z tej aplikacji.



<!--HONumber=Oct16_HO2-->


