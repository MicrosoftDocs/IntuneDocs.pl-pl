---
title: Ustawienia zasad MAM systemu iOS | Microsoft Intune
description: "W tym temacie opisano ustawienia zasad zarządzania aplikacjami mobilnymi dla urządzeń z systemem iOS."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 673ff872-943c-4076-931c-0be90363aea9
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 126974152c638fc4bc69ef92b5fa79beeb0eed0c


---

#  <a name="ios-mobile-app-management-policy-settings"></a>Ustawienia zasad zarządzania aplikacjami mobilnymi systemu iOS
Opisane w tym temacie ustawienia zasad można [skonfigurować](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) dla zasad zarządzania aplikacjami mobilnymi w bloku **Ustawienia** witryny Azure Portal.

Istnieją dwie kategorie ustawień zasad: relokacja danych i dostęp. W tym temacie termin *aplikacje zarządzane przez zasady* dotyczy aplikacji konfigurowanych przy użyciu zasad zarządzania aplikacjami mobilnymi.

##  <a name="data-relocation-settings"></a>Ustawienia relokacji danych

- **Zapobiegaj tworzeniu kopii zapasowych w programach iTunes i iCloud:** wybierz pozycję **Tak**, aby wyłączyć tworzenie kopii zapasowych, lub pozycję **Nie**, aby zezwalać na tworzenie kopii zapasowych danych firmy za pomocą aplikacji zarządzanych przez zasady.

  Wartość domyślna: **Tak**.

- **Zezwalaj aplikacji na przesyłanie danych do innych aplikacji:** wybierz jedną z opcji, aby wskazać aplikacje, które mogą odbierać dane od aplikacji zarządzanych przez zasady:
  - **Aplikacje zarządzane przez zasady**: zezwalaj na przesyłanie danych tylko do aplikacji z zasadami MAM.
  - **Wszystkie aplikacje**: zezwalaj na przesyłanie danych do wszystkich aplikacji.
  - **Brak**: nie zezwalaj na przesyłanie danych do żadnych aplikacji, w tym również innych aplikacji zarządzanych przez zasady.

  Ponadto jeśli ta opcja zostanie ustawiona na wartość **Aplikacje zarządzane przez zasady** lub **Brak**, zostanie zablokowana funkcja systemu iOS 9, która umożliwia narzędziu Spotlight Search wyszukiwanie danych w ramach aplikacji.

  >[!NOTE]
  >To ustawienie nie kontroluje użycia funkcji Otwórz za pomocą na urządzeniach przenośnych. Aby zarządzać funkcją Otwórz za pomocą, zobacz [Zarządzanie przesyłaniem danych między aplikacjami systemu iOS za pomocą usługi Microsoft Intune](manage-data-transfer-between-ios-apps-with-microsoft-intune.md).

  Wartość domyślna: **Aplikacje zarządzane przez zasady**.

- **Zezwalaj aplikacji na odbieranie danych z innych aplikacji:** określ aplikacje, które mogą przesyłać dane do aplikacji zarządzanych przez zasady:
  -  **Aplikacje zarządzane przez zasady**: zezwalaj na przesyłanie danych tylko z innych aplikacji zarządzanych przez zasady.
  -  **Wszystkie aplikacje**: zezwalaj na przesyłanie danych z wszystkich aplikacji.
  -  **Brak**: nie zezwalaj na przesyłanie danych z żadnej aplikacji

  Wartość domyślna: **Wszystkie aplikacje**.

- **Nie zezwalaj na używanie polecenia Zapisz jako:** Wybierz pozycję **Tak**, aby zablokować używanie opcji Zapisz jako we wszystkich aplikacjach korzystających z tych zasad. Wybierz opcję **Nie**, jeśli chcesz zezwolić na używanie polecenia Zapisz jako.

  Wartość domyślna: **Tak**.

- **Ogranicz wycinanie, kopiowanie i wklejanie w innych aplikacjach:** określ sytuacje, w których akcje wycinania, kopiowania i wklejania powinny być ograniczone. Wybierz spośród opcji:
  -   **Zablokowane:** nie zezwalaj na akcje wycinania, kopiowania i wklejania między aplikacjami zarządzanymi przez zasady.
  -   **Aplikacje zarządzane przez zasady:** zezwalaj na akcje wycinania, kopiowania i wklejania tylko między aplikacjami zarządzanymi przez zasady.
  -   **Aplikacje zarządzane przez zasady z funkcją wklejania**: zezwalaj na wycinanie i kopiowanie między aplikacjami zarządzanymi przez zasady. Zezwalaj na wklejanie w tej aplikacji danych wyciętych lub skopiowanych z dowolnych aplikacji.
  - **Dowolna aplikacja**: nie ma ograniczeń dotyczących akcji wycinania, kopiowania i wklejania między dowolnymi aplikacjami.

  Wartość domyślna: **aplikacje zarządzane przez zasady z funkcją wklejania**.

- **Ogranicz zawartość sieci Web do wyświetlenia w programie Managed Browser:** jeśli to ustawienie jest włączone, wszystkie linki w aplikacji będą otwierane w programie Managed Browser.

  W przypadku urządzeń, które nie są zarejestrowane w usłudze Intune, linki sieci Web w aplikacjach zarządzanych przez zasady będą otwierane tylko w aplikacji Managed Browser.

  Jeśli używasz usługi Intune do zarządzania swoimi urządzeniami, zobacz [Zarządzanie dostępem do Internetu za pomocą zasad programu Managed Browser w usłudze Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).

  Wartość domyślna: **Tak**.

- **Szyfruj dane aplikacji:** w przypadku aplikacji, które zostały skojarzone z zasadami zarządzania aplikacjami mobilnymi usługi Intune, dane są szyfrowane, gdy nie są używane, za pomocą funkcji szyfrowania na poziomie urządzenia udostępnianej przez system operacyjny. Jeśli jest wymagany numer PIN, dane są szyfrowane zgodnie z ustawieniami zasad zarządzania aplikacjami mobilnymi. Zgodnie z dokumentacją firmy Apple [moduły używane przez system iOS 7 mają certyfikaty FIPS 140-2](http://support.apple.com/en-us/HT202739).

  W ustawieniach zasad można określić wartości szyfrowania numeru PIN. Wartości te określają, kiedy dane są szyfrowane. Dostępne są następujące opcje:
  -   **Gdy urządzenie jest zablokowane:** wszystkie dane aplikacji skojarzonych z tymi zasadami są szyfrowane, gdy urządzenie jest zablokowane.
  -   **Gdy urządzenie jest zablokowane (oprócz otwartych plików):** wszystkie dane aplikacji skojarzonych z tymi zasadami są szyfrowane, gdy urządzenie jest zablokowane, za wyjątkiem danych w plikach obecnie otwartych w aplikacji.
  -   **Po ponownym uruchomieniu urządzenia:** wszystkie dane aplikacji skojarzonych z tymi zasadami są szyfrowane po ponownym uruchomieniu urządzenia, do momentu odblokowania urządzenia po raz pierwszy.
  -   **Użyj ustawień urządzenia:** dane aplikacji są szyfrowane na podstawie ustawień domyślnych urządzenia.
  Po włączeniu tego ustawienia użytkownik musi skonfigurować i stosować numer PIN, aby uzyskać dostęp do urządzenia.  Jeśli nie skonfigurowano numeru PIN, aplikacje nie będą otwierane, a użytkownik otrzyma monit o ustawienie numeru PIN z następującym komunikatem: „Firma wymaga włączenia numeru PIN urządzenia w celu uzyskania dostępu do tej aplikacji”.

  Wartość domyślna: nie wybrano opcji szyfrowania.
- **Wyłącz synchronizację kontaktów:** wybierz pozycję **Tak**, aby uniemożliwić synchronizowanie informacji kontaktowych z aplikacją natywnej książki adresowej na urządzeniu. W przypadku wybrania pozycji **Nie** aplikacja zapisze dane kontaktowe w aplikacji natywnej książki adresowej na urządzeniu.

  Wykonanie selektywnego czyszczenia w celu usunięcia danych firmy powoduje usunięcie kontaktów zsynchronizowanych bezpośrednio z aplikacji do natywnej książki adresowej. Nie można wyczyścić wszystkich kontaktów zsynchronizowanych z natywnej książki adresowej do innego źródła zewnętrznego. Obecnie dotyczy to tylko aplikacji Microsoft Outlook.

  Wartość domyślna: **Tak**.

- **Wyłącz drukowanie:** wybierz pozycję **Tak**, aby uniemożliwić drukowanie danych firmowych z poziomu aplikacji skojarzonych z zasadami zarządzania aplikacjami mobilnymi.

    Wartość domyślna: **Tak**.

##  <a name="access-settings"></a>Ustawienia dostępu

- **Wymagaj numeru PIN w celu udzielenia dostępu:** wybierz pozycję **Tak**, aby wymagać numeru PIN do korzystania z aplikacji zarządzanych przez zasady. Użytkownik zostanie poproszony o skonfigurowanie tego numeru przy pierwszym uruchomieniu aplikacji w kontekście pracy.

  Wartość domyślna: **Tak**.
    -  **Zezwalaj na prosty numer PIN**: określ, czy użytkownicy mogą używać prostych sekwencji numeru PIN, takich jak 1234 lub 1111. Wartość domyślna: **Tak**.
    - **Długość numeru PIN:** określ minimalną liczbę cyfr numeru PIN. Wartość domyślna: **4**.
    - **Liczba prób przed zresetowaniem numeru PIN:** określ liczbę prób wprowadzenia numeru PIN, po której użytkownik musi zresetować ten numer. To ustawienie nie ma wartości domyślnej.

- **Wymagaj odcisku palca zamiast numeru PIN (system iOS 8.0 i nowsze):** wybierz opcję **Tak**, aby wymagać potwierdzenia tożsamości odciskiem palca zamiast numerem PIN w celu uzyskania dostępu do aplikacji.
Na urządzeniach z systemem iOS możesz zezwolić użytkownikom na identyfikację za pomocą odcisku palca zamiast identyfikacji przy użyciu numeru PIN. Gdy użytkownik podejmie próbę uzyskania dostępu do aplikacji przy użyciu konta służbowego, otrzyma monit o potwierdzenie tożsamości odciskiem palca, a nie numerem PIN.

  Wartość domyślna: **Tak**.
- **Wymagaj poświadczeń firmowych w celu udzielenia dostępu:** wybierz pozycję **Tak**, aby wymagać poświadczeń firmowych zamiast numeru PIN w celu uzyskania dostępu do aplikacji. Wybranie opcji **Tak** przesłania wymagania dotyczące numeru PIN lub funkcji Touch ID. Użytkownik zostanie poproszony o podanie swoich poświadczeń firmowych.

  Wartość domyślna: **Nie**.
- **Blokuj uruchamianie aplikacji zarządzanych na urządzeniach, na których zdjęto zabezpieczenia systemu lub uzyskano dostęp do konta root:** wybierz pozycję **Tak**, aby blokować uruchamianie aplikacji na urządzeniach, na których zdjęto zabezpieczenia systemu lub uzyskano dostęp do konta root. Użytkownik będzie mógł korzystać z aplikacji do zadań osobistych, ale będzie musiał używać innego urządzenia do pracy.

  Wartość domyślna: **Tak**.
- **Ponownie sprawdź wymagania dostępu po (w minutach)**
  -   **Limit czasu:** określ czas (w minutach) przed ponownym sprawdzeniem wymagań dostępu do aplikacji.
  -   **Okres karencji w trybie offline:** jeśli urządzenie znajduje się w trybie offline, określ czas (w minutach) przed ponownym sprawdzeniem wymagań dostępu do aplikacji.

  Wartości domyślne: limit czasu — **30** minut, okres karencji w trybie offline — **720** minut.
- **Interwał offline przed wyczyszczeniem danych aplikacji (w dniach):** możesz wyczyścić dane firmowe w przypadku, gdy urządzenie znajdowało się w trybie offline przez wybrany okres. W bloku ustawień zasad możesz określić liczbę dni, przez które urządzenie może pozostawać w trybie offline przed usunięciem z niego danych firmowych.

  >[!TIP]
  >Wprowadzenie wartości **0** spowoduje wyłączenie tego ustawienia.

  Wartość domyślna: **90** dni.



<!--HONumber=Dec16_HO2-->


