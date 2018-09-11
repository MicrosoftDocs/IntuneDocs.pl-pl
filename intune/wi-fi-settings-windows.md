---
title: Ustawienia sieci Wi-Fi dla urządzeń z systemem Windows 10 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodawanie lub tworzenie profilu konfiguracji sieci Wi-Fi przy użyciu ustawień sieci Wi-Fi dla urządzeń z systemem Windows 10 lub nowszym w usłudze Microsoft Intune. Można skonfigurować ustawienia podstawowe lub ustawienia na poziomie przedsiębiorstwa.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/30/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.reviewer: tycast
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e15a7b034c9277fcd960e8c704f4318f0f5c1da2
ms.sourcegitcommit: e814cfbbefe818be3254ef6f859a7bf5f5b99123
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/31/2018
ms.locfileid: "43329651"
---
# <a name="wi-fi-settings-for-windows-10-and-later-devices-in-intune"></a>Ustawienia sieci Wi-Fi dla urządzeń z systemem Windows 10 lub nowszym w usłudze Microsoft Intune

Ustawienia sieci Wi-Fi są używane w profilu konfiguracji, który ma zastosowanie w przypadku urządzeń z systemem Windows 10 lub nowszym. Dostępne opcje:

- Podstawowe
- Enterprise

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil urządzenia](device-profile-create.md).

## <a name="settings-for-basic-and-enterprise-profiles"></a>Ustawienia dla profilu podstawowego i przedsiębiorstwa

- **Nazwa sieci (SSID)**: identyfikator zestawu usług. Ta wartość to prawdziwa nazwa sieci bezprzewodowej, z którą łączą się urządzenia. Podczas wybierania połączenia użytkownicy widzą jednak tylko skonfigurowaną przez Ciebie **nazwę połączenia**.
- **Nazwa połączenia**: wprowadź przyjazną dla użytkownika nazwę tego połączenia sieci Wi-Fi. Wprowadzany tekst to nazwa, którą użytkownicy zobaczą podczas przeglądania dostępnych połączeń na swoim urządzeniu.
- **Połącz automatycznie, gdy jest w zasięgu**: po wybraniu pozycji **Tak** urządzenia będą łączyć się automatycznie, gdy znajdą się w zasięgu tej sieci. W przypadku wybrania pozycji **Nie** urządzenia nie łączą się automatycznie.
  - **Połącz z bardziej preferowaną siecią, jeśli jest dostępna**: jeśli urządzenia znajdują się w zakresie bardziej preferowanej sieci, wybór pozycji **Tak** spowoduje użycie preferowanej sieci. Wybierz pozycję **Nie**, aby w tym profilu konfiguracji używać sieci Wi-Fi.

    Na przykład tworzysz sieć Wi-Fi **ContosoCorp** i używasz sieci **ContosoCorp** w ramach tego profilu konfiguracji. W zakresie masz również sieć Wi-Fi **ContosoGuest**. Gdy urządzenia firmowe znajdą się w zakresie, chcesz, aby automatycznie łączyły się z siecią **ContosoCorp**. W tym scenariuszu ustaw właściwość **Połącz z bardziej preferowaną siecią, jeśli jest dostępna** na **Nie**.

  - **Połącz z tą siecią, nawet jeśli nie emituje identyfikatora SSID**: wybierz pozycję **Tak** dla profilu konfiguracji, aby automatycznie łączyć się z siecią, nawet gdy jest ukryta (tzn. jej identyfikator SSID nie jest emitowany publicznie). Wybierz pozycję **Nie**, jeśli nie chcesz, aby ten profil konfiguracji łączył się z siecią ukrytą.

- **Ustawienia serwera proxy firmy**: wybierz sposób użycia ustawień serwera proxy w organizacji. Dostępne opcje:
  - **Brak**: nie są konfigurowane żadne ustawienia serwera proxy.
  - **Skonfiguruj ręcznie**: wprowadź **adres IP serwera proxy** i jego **numer portu**.
  - **Skonfiguruj ręcznie**: wprowadź adres URL wskazujący skrypt automatycznej konfiguracji serwera proxy (PAC). Na przykład wprowadź `http://proxy.contoso.com/proxy.pac`.

## <a name="settings-for-basic-profiles-only"></a>Ustawienia tylko dla profilów podstawowych

- **Typ zabezpieczeń sieci bezprzewodowej**: wprowadź protokół zabezpieczeń używany do uwierzytelniania urządzeń w sieci. Dostępne opcje to:
  - **Otwórz (bez uwierzytelniania)**: tej opcji można używać tylko, jeśli sieć jest niezabezpieczona.
  - **WPA/WPA2-Personal**

## <a name="settings-for-enterprise-profiles-only"></a>Ustawienia tylko dla profilów przedsiębiorstwa

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

- **Wymuszanie zgodności profilu Wi-Fi ze standardem FIPS**: wybierz pozycję **Tak** podczas weryfikacji pod kątem zgodności ze standardem FIPS 140-2. Ten standard jest wymagany dla wszystkich federalnych instytucji rządowych USA używających systemów zabezpieczeń opartych na kryptografii do ochrony przechowywanych w postaci cyfrowej poufnych, ale nie utajnionych informacji. Wybierz pozycję **Nie**, aby nie przestrzegać zgodności ze standardem FIPS.

## <a name="use-an-imported-settings-file"></a>Używanie zaimportowanego pliku ustawień

W przypadku wszystkich ustawień niedostępnych w usłudze Intune można wyeksportować ustawienia sieci Wi-Fi z innego urządzenia Windows. Ten eksport spowoduje utworzenie pliku XML z wszystkimi ustawieniami. Następnie należy zaimportować ten plik do usługi Intune i używać go jako profilu sieci Wi-Fi. Zobacz [Eksportowanie i importowanie ustawień sieci Wi-Fi dla urządzeń z systemem Windows](wi-fi-settings-import-windows-8-1.md).

## <a name="next-steps"></a>Następne kroki
[Konfigurowanie ustawień sieci Wi-Fi w usłudze Intune](wi-fi-settings-configure.md)
