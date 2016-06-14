---
# required metadata

title: Ustawienia zasad MAM systemu iOS | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 673ff872-943c-4076-931c-0be90363aea9

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

#  Ustawienia zasad zarządzania aplikacjami mobilnymi systemu iOS
Opisane poniżej ustawienia zasad można [skonfigurować](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) dla zasad zarządzania aplikacjami mobilnymi w bloku **Ustawienia** portalu Azure.

Istnieją dwie kategorie ustawień zasad, Relokacja danych i Dostęp:

##  Ustawienia relokacji danych
Termin **Aplikacje zarządzane przez zasady** dotyczy aplikacji konfigurowanych przy użyciu zasad zarządzania aplikacjami mobilnymi.

- **Zapobiegaj tworzeniu kopii zapasowych w programach iTunes i iCloud:**
  Wybierz opcję **Tak**, aby wyłączyć, lub **Nie**, aby zezwalać na tworzenie kopii zapasowych danych firmy w aplikacjach zarządzanych przez zasady.

  **Wartość domyślna = Tak**

- **Zezwalaj aplikacji na przesyłanie danych do innych aplikacji:** wybierz jedną z opcji, aby wskazać aplikacje, które mogą odbierać dane z aplikacji zarządzanych przez zasady:
  - **Aplikacje zarządzane przez zasady**: zezwalaj na przesyłanie danych tylko do aplikacji z zasadami MAM.
  - **Wszystkie aplikacje**: zezwalaj na przesyłanie danych do wszystkich aplikacji
  - **Brak**: nie zezwalaj na przesyłanie danych do żadnych aplikacji, w tym również innych aplikacji zarządzanych przez zasady.

  Ponadto jeśli ta opcja zostanie ustawiona na wartość **Aplikacje zarządzane przez zasady** lub **Brak**, zostanie zablokowana funkcja systemu iOS 9, która umożliwia narzędziu Spotlight Search wyszukiwanie danych w ramach aplikacji.

  **Wartość domyślna = Aplikacje zarządzane przez zasady**

- **Zezwalaj aplikacji na odbieranie danych z innych aplikacji:** określ aplikacje, które mogą przesyłać dane do aplikacji zarządzanych przez zasady:
  -  **Aplikacje zarządzane przez zasady**: zezwalaj na przesyłanie danych tylko z innych aplikacji zarządzanych przez zasady.
  -  **Wszystkie aplikacje**: zezwalaj na przesyłanie danych z wszystkich aplikacji.
  -  **Brak**: nie zezwalaj na przesyłanie danych z żadnej aplikacji

  **Wartość domyślna = Wszystkie aplikacje**

- **Nie zezwalaj na używanie polecenia „Zapisz jako”:**
  Wybierz opcję **Tak** , aby zablokować używanie polecenia Zapisz jako we wszystkich aplikacjach korzystających z tych zasad. Wybierz opcję **Nie**, jeśli chcesz zezwolić na używanie polecenia Zapisz jako.

  **Wartość domyślna = Tak**

- **Ogranicz wycinanie, kopiowanie i wklejanie w innych aplikacjach:**
Określ sytuacje, w których operacje wycinania, kopiowania i wklejania powinny być ograniczone. Wybierz spośród opcji:
  -   **Zablokowane:** nie zezwalaj na operacje wycinania, kopiowania i wklejania między aplikacjami zarządzanymi przez zasady.
  -   **Aplikacje zarządzane przez zasady:** zezwalaj na operacje wycinania, kopiowania i wklejania tylko między aplikacjami zarządzanymi przez zasady.
  -   **Aplikacje zarządzane przez zasady z funkcją wklejania**: zezwalaj na wycinanie i kopiowanie między aplikacjami zarządzanymi przez zasady. Zezwalaj na wklejanie w tej aplikacji danych wyciętych lub skopiowanych z dowolnych aplikacji.
  - **Dowolna aplikacja**: brak ograniczeń operacji wycinania, kopiowania i wklejania między dowolnymi aplikacjami.

  **Wartość domyślna = Aplikacje zarządzane przez zasady z funkcją wklejania**

- **Ogranicz zawartość sieci Web do wyświetlenia w programie Managed Browser:** jeśli to ustawienie zostanie włączone, wszystkie linki w aplikacji będą otwierane w programie Managed Browser.

  W przypadku urządzeń, które nie zostały zarejestrowane w usłudze Intune, linki sieci Web w aplikacjach zarządzanych przez zasady mogą być otwierane tylko w aplikacji Managed Browser korzystającej z zasad zarządzania aplikacjami mobilnymi.

  Jeśli używasz usługi Intune do zarządzania swoimi urządzeniami, zobacz [Zarządzanie dostępem do Internetu za pomocą zasad programu Managed Browser w usłudze Microsoft Intune](manage-internet-access-using-managed-browser-policies.md)..

    **Wartość domyślna = Tak**

- **Szyfruj dane aplikacji:** w przypadku aplikacji, które zostały skojarzone z zasadami zarządzania aplikacjami mobilnymi usługi [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], dane są szyfrowane, gdy nie są używane, za pomocą szyfrowania na poziomie urządzenia obsługiwanego przez system operacyjny. Jeśli numer PIN jest wymagany, dane są szyfrowane zgodnie z ustawieniami zasad zarządzania aplikacjami mobilnymi. Zgodnie z dokumentacją firmy Apple [moduły używane przez system iOS 7 mają certyfikaty FIPS 140-2](http://support.apple.com/en-us/HT202739).

  W ustawieniach zasad można określić wartości szyfrowania numeru PIN.  Wartości te określają, kiedy dane są szyfrowane. Dostępne opcje to:
  - **Gdy urządzenie jest zablokowane:** wszystkie dane aplikacji skojarzonych z tymi zasadami są szyfrowane, gdy urządzenie jest zablokowane.
  -   **Gdy urządzenie jest zablokowane (oprócz otwartych plików):** wszystkie dane aplikacji skojarzonych z tymi zasadami są szyfrowane, gdy urządzenie jest zablokowane, za wyjątkiem danych w plikach obecnie otwartych w aplikacji.
  -   **Po ponownym uruchomieniu urządzenia:** wszystkie dane aplikacji skojarzonych z tymi zasadami są szyfrowane po ponownym uruchomieniu urządzenia, do momentu odblokowania urządzenia po raz pierwszy.
  -   **Użyj ustawień urządzenia:** dane aplikacji są szyfrowane na podstawie ustawień domyślnych urządzenia.
  Po włączeniu tego ustawienia użytkownik końcowy musi skonfigurować i stosować numer PIN, aby uzyskać dostęp do urządzenia.  Jeśli nie skonfigurowano numeru PIN, aplikacje nie będą uruchamiane, a użytkownik końcowy otrzyma monit o ustawienie numeru PIN z następującym komunikatem: „Firma wymaga włączenia numeru PIN urządzenia w celu uzyskania dostępu do tej aplikacji”.

  **Wartość domyślna — Nie wybrano opcji szyfrowania.**
- **ContactSyncDisabled:** wybierz opcję **Tak**, aby uniemożliwić synchronizację informacji kontaktowych z aplikacją natywnej książki adresowej na urządzeniu. W przypadku wybrania opcji **Nie** aplikacja zapisuje dane kontaktowe w aplikacji natywnej książki adresowej urządzenia.

  Wykonanie selektywnego czyszczenia w celu usunięcia danych firmy powoduje usunięcie kontaktów zsynchronizowanych bezpośrednio z aplikacji do natywnej książki adresowej. Nie można wyczyścić wszystkich kontaktów zsynchronizowanych z natywnej książki adresowej do innego źródła zewnętrznego. Obecnie ta opcja ma zastosowanie tylko do aplikacji **Microsoft Outlook**.

  **Wartość domyślna = Tak**
##  Ustawienia zasad dostępu systemu iOS
Termin **Aplikacje zarządzane przez zasady** dotyczy aplikacji konfigurowanych przy użyciu zasad zarządzania aplikacjami mobilnymi.
- **Wymagaj prostego numeru PIN w celu udzielenia dostępu:** wybierz opcję **Tak**, aby wymagać numeru PIN do korzystania z aplikacji zarządzanej przy użyciu zasad. Użytkownik zostanie poproszony o skonfigurowanie tego numeru przy pierwszym uruchomieniu aplikacji w kontekście pracy.

  **Wartość domyślna = Tak**
- **Liczba prób przed zresetowaniem numeru PIN:** określ liczbę prób wprowadzenia numeru PIN, po której użytkownik musi zresetować ten numer.

  **To ustawienie nie ma wartości domyślnej**.
- **Wymagaj odcisku palca zamiast numeru PIN (system iOS 8.0 i nowsze):** wybierz opcję **Tak**, aby wymagać potwierdzenia tożsamości odciskiem palca zamiast numerem PIN w celu uzyskania dostępu do aplikacji.
Na urządzeniach z systemem iOS możesz zezwolić użytkownikom na identyfikację za pomocą odcisku palca zamiast identyfikacji przy użyciu numeru PIN. Gdy użytkownik końcowy podejmie próbę uzyskania dostępu do aplikacji przy użyciu konta służbowego, otrzyma monit o potwierdzenie tożsamości odciskiem palca, a nie numerem PIN.

  **Wartość domyślna = Tak**
- **Wymagaj poświadczeń firmowych w celu udzielenia dostępu:** wybierz opcję **Tak**, aby wymagać poświadczeń firmowych zamiast numeru PIN w celu uzyskania dostępu do aplikacji. **Wybranie opcji Tak przesłania wymaganie numeru PIN lub użycia funkcji Touch ID.** Użytkownik zostanie poproszony o podanie swoich poświadczeń firmowych.

  **Wartość domyślna = Nie**
- **Blokuj uruchamianie aplikacji zarządzanych na urządzeniach, na których zdjęto zabezpieczenia systemu lub uzyskano dostęp do konta root:** wybierz opcję **Tak**, aby blokować uruchamianie aplikacji na urządzeniach, na których zdjęto zabezpieczenia systemu lub uzyskano dostęp do konta root. Użytkownik będzie mógł korzystać z aplikacji do zadań osobistych, ale będzie musiał używać innego urządzenia do pracy.

  **Wartość domyślna = Tak**
- **Ponownie sprawdź wymagania dostępu po (w minutach)**|-   **Limit czasu:** czas (w minutach) przed ponownym sprawdzeniu wymagań dostępu dla aplikacji.
  -   **Okres karencji w trybie offline:** jeśli urządzenie znajduje się w trybie offline, określ czas (w minutach) przed ponownym sprawdzeniem wymagań dostępu do aplikacji.

  **Wartość domyślna = limit czasu 30 minut, okres karencji w trybie offline 720 minut**
  - **Interwał offline przed wyczyszczeniem danych aplikacji (w dniach):** możesz zdecydować się na wyczyszczenie danych firmowych w przypadku przebywania urządzenia w trybie offline przez wybrany okres.  W bloku ustawień zasad możesz określić liczbę dni, przez które urządzenie może pozostawać w trybie offline przed usunięciem z niego danych firmowych. **Wprowadzenie wartości 0 spowoduje wyłączenie tego ustawienia.**.

  **Wartość domyślna = 90 dni**


<!--HONumber=May16_HO1-->


