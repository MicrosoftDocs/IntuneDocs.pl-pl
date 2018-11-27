---
title: Ustawienia sieci Wi-Fi dla urządzeń z systemem Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodawanie lub tworzenie profilu konfiguracji sieci Wi-Fi przy użyciu ustawień sieci Wi-Fi dla urządzeń z systemem Windows 10 lub nowszym w usłudze Microsoft Intune. Można skonfigurować ustawienia podstawowe lub ustawienia na poziomie przedsiębiorstwa.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/8/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.reviewer: tycast
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 76d9efc969f68188d9752996267ff7a88363f76f
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52180820"
---
# <a name="add-wi-fi-settings-for-windows-10-and-later-devices-in-intune"></a>Dodawanie ustawień sieci Wi-Fi dla urządzeń z systemem Windows 10 lub nowszym w usłudze Intune

Profil z określonymi ustawieniami sieci Wi-Fi można utworzyć, a następnie wdrożyć na urządzeniach z systemem Windows 10 lub nowszym. Usługa Microsoft Intune oferuje wiele funkcji, w uwierzytelnianie do sieci, korzystanie z klucza wstępnego i inne.

W tym artykule opisano te ustawienia.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil urządzenia](device-profile-create.md).

## <a name="basic-profile"></a>Profil podstawowy

- **Typ sieci Wi-Fi**: wybierz pozycję **Podstawowa**. 

- **Nazwa sieci (SSID)**: identyfikator zestawu usług. Ta wartość to prawdziwa nazwa sieci bezprzewodowej, z którą łączą się urządzenia. Podczas wybierania połączenia użytkownicy widzą jednak tylko skonfigurowaną przez Ciebie **nazwę połączenia**.

- **Nazwa połączenia**: wprowadź przyjazną dla użytkownika nazwę tego połączenia sieci Wi-Fi. Wprowadzany tekst to nazwa, którą użytkownicy zobaczą podczas przeglądania dostępnych połączeń na swoim urządzeniu.

- **Połącz automatycznie, gdy jest w zasięgu**: po wybraniu pozycji **Tak** urządzenia będą łączyć się automatycznie, gdy znajdą się w zasięgu tej sieci. W przypadku wybrania pozycji **Nie** urządzenia nie łączą się automatycznie.

  - **Połącz z bardziej preferowaną siecią, jeśli jest dostępna**: jeśli urządzenia znajdują się w zakresie bardziej preferowanej sieci, wybór pozycji **Tak** spowoduje użycie preferowanej sieci. Wybierz pozycję **Nie**, aby w tym profilu konfiguracji używać sieci Wi-Fi.

    Na przykład tworzysz sieć Wi-Fi **ContosoCorp** i używasz sieci **ContosoCorp** w ramach tego profilu konfiguracji. W zakresie masz również sieć Wi-Fi **ContosoGuest**. Gdy urządzenia firmowe znajdą się w zakresie, chcesz, aby automatycznie łączyły się z siecią **ContosoCorp**. W tym scenariuszu ustaw właściwość **Połącz z bardziej preferowaną siecią, jeśli jest dostępna** na **Nie**.

  - **Połącz z tą siecią, nawet jeśli nie emituje identyfikatora SSID**: wybierz pozycję **Tak** dla profilu konfiguracji, aby automatycznie łączyć się z siecią, nawet gdy jest ukryta (tzn. jej identyfikator SSID nie jest emitowany publicznie). Wybierz pozycję **Nie**, jeśli nie chcesz, aby ten profil konfiguracji łączył się z siecią ukrytą.

- **Limit połączenia taryfowego**: administrator może wybrać sposób mierzenia ruchu sieciowego. Aplikacje mogą następnie dopasowywać swoje zachowanie względem ruchu sieciowego na podstawie tego ustawienia. Dostępne opcje:

  - **Bez ograniczeń**: wartość domyślna. Połączenie nie jest taryfowe i nie ma żadnych ograniczeń dotyczących ruchu.
  - **Stały**: użyj tej opcji, jeśli dla sieci skonfigurowano stały limit ruchu sieciowego. Po osiągnięciu tego limitu dostęp do sieci jest zabroniony.
  - **Zmienny**: użyj tej opcji, jeśli opłaty w przypadku ruchu sieciowego są naliczane za bajt (koszt na bajt).

- **Typ zabezpieczeń sieci bezprzewodowej**: wprowadź protokół zabezpieczeń używany do uwierzytelniania urządzeń w sieci. Dostępne opcje to:
  - **Otwórz (bez uwierzytelniania)**: tej opcji można używać tylko, jeśli sieć jest niezabezpieczona.
  - **WPA/WPA2-Personal**: opcja zapewniająca większe bezpieczeństwo, która jest często używana w przypadku łączności Wi-Fi. Aby uzyskać lepsze zabezpieczenia, możesz także wprowadzić hasło w postaci klucza wstępnego lub klucz sieci. 

    - **Klucz wstępny** (PSK): opcjonalnie. Wyświetlana po wybraniu typu zabezpieczeń **WPA/WPA2-Personal**. Podczas ustawiania lub konfigurowania sieci organizacji jest również konfigurowane hasło lub klucz sieciowy. Wprowadź to hasło lub klucz sieciowy dla wartości klucza wstępnego. Wprowadź ciąg zawierający od 8 do 64 znaków. Jeśli hasło lub klucz sieci ma 64 znaki, wprowadź znaki szesnastkowe.
    
      > [!NOTE]
      > Jeśli zapiszesz profil Wi-Fi, wprowadzona wartość klucza wstępnego nie zostanie wyświetlona z przyczyn bezpieczeństwa. Znak wodny klucza wstępnego nadal będzie wyświetlany jako **Nieskonfigurowany**, mimo że klucz wstępny jest zapisany w profilu. Aby zmienić klucz wstępny, wprowadź nowy klucz i zapisz profil. Jeśli zapiszesz klucz wstępny, edytujesz zasadę i zostawisz pole klucza wstępnego puste, to nadal używany będzie istniejący klucz wstępny.

- **Ustawienia serwera proxy firmy**: wybierz sposób użycia ustawień serwera proxy w organizacji. Dostępne opcje:
  - **Brak**: nie są konfigurowane żadne ustawienia serwera proxy.
  - **Skonfiguruj ręcznie**: wprowadź **adres IP serwera proxy** i jego **numer portu**.
  - **Skonfiguruj automatycznie**: wprowadź adres URL wskazujący skrypt automatycznej konfiguracji serwera proxy (PAC). Na przykład wprowadź `http://proxy.contoso.com/proxy.pac`.

Wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany. Profil zostanie utworzony i wyświetlony na liście profilów.

## <a name="enterprise-profile"></a>Profil przedsiębiorstwa

- **Typ sieci Wi-Fi**: wybierz pozycję **Przedsiębiorstwo**. 

- **Nazwa sieci (SSID)**: identyfikator zestawu usług. Ta wartość to prawdziwa nazwa sieci bezprzewodowej, z którą łączą się urządzenia. Podczas wybierania połączenia użytkownicy widzą jednak tylko skonfigurowaną przez Ciebie **nazwę połączenia**.

- **Nazwa połączenia**: wprowadź przyjazną dla użytkownika nazwę tego połączenia sieci Wi-Fi. Wprowadzany tekst to nazwa, którą użytkownicy zobaczą podczas przeglądania dostępnych połączeń na swoim urządzeniu.

- **Połącz automatycznie, gdy jest w zasięgu**: po wybraniu pozycji **Tak** urządzenia będą łączyć się automatycznie, gdy znajdą się w zasięgu tej sieci. W przypadku wybrania pozycji **Nie** urządzenia nie łączą się automatycznie.
  - **Połącz z bardziej preferowaną siecią, jeśli jest dostępna**: jeśli urządzenia znajdują się w zakresie bardziej preferowanej sieci, wybór pozycji **Tak** spowoduje użycie preferowanej sieci. Wybierz pozycję **Nie**, aby w tym profilu konfiguracji używać sieci Wi-Fi.

    Na przykład tworzysz sieć Wi-Fi **ContosoCorp** i używasz sieci **ContosoCorp** w ramach tego profilu konfiguracji. W zakresie masz również sieć Wi-Fi **ContosoGuest**. Gdy urządzenia firmowe znajdą się w zakresie, chcesz, aby automatycznie łączyły się z siecią **ContosoCorp**. W tym scenariuszu ustaw właściwość **Połącz z bardziej preferowaną siecią, jeśli jest dostępna** na **Nie**.

  - **Połącz z tą siecią, nawet jeśli nie emituje identyfikatora SSID**: wybierz pozycję **Tak** dla profilu konfiguracji, aby automatycznie łączyć się z siecią, nawet gdy jest ukryta (tzn. jej identyfikator SSID nie jest emitowany publicznie). Wybierz pozycję **Nie**, jeśli nie chcesz, aby ten profil konfiguracji łączył się z siecią ukrytą.

- **Limit połączenia taryfowego**: administrator może wybrać sposób mierzenia ruchu sieciowego. Aplikacje mogą następnie dopasowywać swoje zachowanie względem ruchu sieciowego na podstawie tego ustawienia. Dostępne opcje:

  - **Bez ograniczeń**: wartość domyślna. Połączenie nie jest taryfowe i nie ma żadnych ograniczeń dotyczących ruchu.
  - **Stały**: użyj tej opcji, jeśli dla sieci skonfigurowano stały limit ruchu sieciowego. Po osiągnięciu tego limitu dostęp do sieci jest zabroniony.
  - **Zmienny**: użyj tej opcji, jeśli opłaty w przypadku ruchu sieciowego są naliczane za bajt.

- **Logowanie jednokrotne**: umożliwia konfigurowanie logowania jednokrotnego, w ramach którego poświadczenia są udostępniane na potrzeby logowania do komputera i sieci Wi-Fi. Dostępne opcje to:
  - **Wyłącz**: wyłącza zachowanie logowania jednokrotnego. Użytkownik musi oddzielnie uwierzytelnić się w sieci.
  - **Włącz przed zalogowaniem użytkownika do urządzenia**: użycie logowania jednokrotnego w celu uwierzytelnienia w sieci przed rozpoczęciem procesu logowania.
  - **Włącz po zalogowaniu użytkownika do urządzenia**: użycie logowania jednokrotnego w celu uwierzytelnienia w sieci od razu po zakończeniu procesu logowania.
  - **Maksymalny czas uwierzytelniania przed upływem limitu czasu**: wprowadź maksymalną liczbę sekund oczekiwania przed uwierzytelnianiem w sieci z przedziału od 1 do 120 sekund.
  - **Zezwalaj systemowi Windows na monitowanie użytkownika o dodatkowe poświadczenia uwierzytelniania**: po wybraniu pozycji **Tak** system Windows będzie mógł monitować użytkownika o dodatkowe poświadczenia, jeśli wymaga tego metoda uwierzytelniania. Wybierz pozycję **Nie**, aby ukryć te monity.

- **Włącz buforowanie kluczy głównych parowania**: wybierz pozycję **Tak**, aby buforować klucze główne parowania używane w przypadku uwierzytelniania. Takie buforowanie pozwala zazwyczaj na szybsze ukończenie uwierzytelniania w sieci. Wybierz pozycję **Nie**, aby wymuszać uzgadnianie uwierzytelniania za każdym razem, gdy będziesz łączyć się z siecią Wi-Fi.

  - **Maksymalny czas przechowywania klucza głównego parowania w pamięci podręcznej**: wprowadź liczbę minut wskazującą, jak długo klucz główny parowania będzie przechowywany w pamięci podręcznej, z przedziału od 5 do 1440 minut.
  - **Maksymalna liczba kluczy głównych parowania przechowywanych w pamięci podręcznej**: wprowadź liczbę kluczy przechowywanych w pamięci podręcznej z przedziału od 1 do 255.

- **Włącz uwierzytelnianie wstępne**: uwierzytelnianie wstępne umożliwia profilowi uwierzytelnianie do wszystkich punktów dostępu do sieci w profilu. Podczas przechodzenia między punktami dostępu uwierzytelnianie wstępne powoduje, że połączenia z użytkownikiem lub urządzeniami są nawiązywane szybciej. Wybierz pozycję **Tak**, aby profil był uwierzytelniany do wszystkich punktów dostępu do danej sieci, które znajdują się w zakresie. Wybierz pozycję **Nie**, aby wymagać osobnego uwierzytelniania użytkownika lub urządzenia do każdego punktu dostępu.

  - **Maksymalna liczba prób uwierzytelniania wstępnego**: wprowadź liczbę prób uwierzytelniania wstępnego z przedziału od 1 do 16.

- **Typ protokołu EAP**: wybierz typ protokołu uwierzytelniania rozszerzonego (EAP) na potrzeby uwierzytelniania zabezpieczonych połączeń bezprzewodowych. Dostępne opcje:

  - **EAP-SIM**
  - **EAP-TLS**
  - **EAP-TTLS**
  - **Chroniony protokół EAP** (PEAP)

    **Dodatkowe ustawienia EAP-TLS, EAP-TTLS i PEAP**:
    
    > [!NOTE]
    > Obecnie profile certyfikatów SCEP są obsługiwane tylko w przypadku korzystania z typu protokołu EAP. Profile certyfikatów PKCS nie są obsługiwane. Pamiętaj, aby za każdym razem, gdy użytkownik zostanie poproszony o wprowadzenie certyfikatu, wybierać certyfikat protokołu SCEP.

      - **Zaufanie serwera**  

        **Nazwy serwerów certyfikatów**: należy używać z następującymi typami protokołu EAP: **EAP-TLS**, **EAP-TTLS** lub **PEAP**. Wprowadź jedną lub więcej nazw pospolitych używanych w certyfikatach wystawionych przez zaufany urząd certyfikacji (CA). Jeśli te informacje zostaną wprowadzone, można pominąć dynamiczne okno dialogowe zaufania pokazywane na urządzeniach użytkowników próbujących nawiązać połączenie z siecią Wi-Fi.  

        **Certyfikat główny walidacji serwera**: należy używać z następującymi typami protokołu EAP: **EAP-TLS**, **EAP-TTLS** lub **PEAP**. Wybierz profil zaufanych certyfikatów głównych używany do uwierzytelniania połączenia.  

        **Prywatność tożsamości (tożsamość zewnętrzna)**: należy używać z typem protokołu EAP **PEAP**. Wprowadź tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.  

      - **Uwierzytelnianie klienta**

        **Certyfikat klienta na potrzeby uwierzytelniania klienta (certyfikat tożsamości)**: należy używać z typem protokołu EAP **EAP-TLS**. Wybierz profil certyfikatu używany do uwierzytelniania połączenia.

        **Metoda uwierzytelniania**: należy używać z typem protokołu EAP **EAP-TTLS**. Wybierz metodę uwierzytelniania dla połączenia:  

          - **Certyfikaty**: wybierz certyfikat klienta, który jest certyfikatem tożsamości przesłanym do serwera.
          - **Nazwa użytkownika i hasło**: wprowadź metodę **Metoda inna niż protokół EAP (tożsamość wewnętrzna)** na potrzeby uwierzytelniania. Dostępne opcje:

            - **Hasło nieszyfrowane (PAP)**
            - **Challenge Handshake (CHAP)**
            - **Microsoft CHAP (MS-CHAP)**
            - **Microsoft CHAP wersja 2 (MS-CHAP v2)**

        **Prywatność tożsamości (tożsamość zewnętrzna)**: należy używać z typem protokołu EAP **EAP-TTLS**. Wprowadź tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.

- **Ustawienia serwera proxy firmy**: wybierz sposób użycia ustawień serwera proxy w organizacji. Dostępne opcje:
  - **Brak**: nie są konfigurowane żadne ustawienia serwera proxy.
  - **Skonfiguruj ręcznie**: wprowadź **adres IP serwera proxy** i jego **numer portu**.
  - **Skonfiguruj ręcznie**: wprowadź adres URL wskazujący skrypt automatycznej konfiguracji serwera proxy (PAC). Na przykład wprowadź `http://proxy.contoso.com/proxy.pac`.

- **Wymuszanie zgodności profilu Wi-Fi ze standardem FIPS**: wybierz pozycję **Tak** podczas weryfikacji pod kątem zgodności ze standardem FIPS 140-2. Ten standard jest wymagany dla wszystkich federalnych instytucji rządowych USA używających systemów zabezpieczeń opartych na kryptografii do ochrony przechowywanych w postaci cyfrowej poufnych, ale nie utajnionych informacji. Wybierz pozycję **Nie**, aby nie przestrzegać zgodności ze standardem FIPS.

Wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany. Profil zostanie utworzony i wyświetlony na liście profilów.

## <a name="use-an-imported-settings-file"></a>Używanie zaimportowanego pliku ustawień

W przypadku wszystkich ustawień niedostępnych w usłudze Intune można wyeksportować ustawienia sieci Wi-Fi z innego urządzenia Windows. Ten eksport spowoduje utworzenie pliku XML z wszystkimi ustawieniami. Następnie należy zaimportować ten plik do usługi Intune i używać go jako profilu sieci Wi-Fi. Zobacz [Eksportowanie i importowanie ustawień sieci Wi-Fi dla urządzeń z systemem Windows](wi-fi-settings-import-windows-8-1.md).

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje żadnych czynności. Następnie [przypisz ten profil](device-profile-assign.md).

## <a name="more-resources"></a>Dodatkowe zasoby

- Zobacz ustawienia dostępne dla systemu [Windows 8.1](wi-fi-settings-import-windows-8-1.md).
- [Omówienie ustawień sieci Wi-Fi](wi-fi-settings-configure.md), w tym informacje na temat innych platform
