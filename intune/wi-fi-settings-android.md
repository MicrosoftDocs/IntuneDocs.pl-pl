---
title: Konfigurowanie ustawień sieci Wi-Fi dla urządzeń z systemem Android w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Tworzenie lub dodawanie profilu konfiguracji urządzeń w sieci Wi-Fi dla systemu Android. Zapoznaj się z różnymi ustawieniami, w tym dotyczącymi dodawania certyfikatów, wybierania typu protokołu EAP i wybierania metody uwierzytelniania w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/06/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1d341aeace950f62ae699aa7760a65c0fd2f74fa
ms.sourcegitcommit: b78793ccbef2a644a759ca3110ea73e7ed6ceb8f
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2019
ms.locfileid: "69550050"
---
# <a name="add-wi-fi-settings-for-devices-running-android-in-microsoft-intune"></a>Dodawanie ustawień sieci Wi-Fi dla urządzeń z systemem Android w usłudze Microsoft Intune

Można utworzyć profil z określonymi ustawieniami sieci Wi-Fi, a następnie wdrożyć ten profil na urządzeniach z systemem Android. Usługa Microsoft Intune oferuje wiele funkcji, w tym uwierzytelnianie do sieci, dodawanie klucza wstępnego lub protokołu SCEP i inne.

Te ustawienia sieci Wi-Fi są podzielone na dwie kategorie: ustawienia podstawowe i ustawienia na poziomie przedsiębiorstwa.

W tym artykule opisano te ustawienia.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil urządzenia](device-profile-create.md).

## <a name="basic"></a>Podstawowe

- **Typ sieci Wi-Fi**: wybierz pozycję **Podstawowa**.
- **SSID**: wprowadź **Identyfikator zestawu usług**, który jest rzeczywistą nazwą sieci bezprzewodowej, z którą urządzenia nawiązują połączenie. Jednak przy wyborze połączenia użytkownicy widzą tylko **nazwę sieci** utworzoną wcześniej.
- **Połącz automatycznie**: wybierz pozycję **Włącz**, aby automatycznie łączyć się z tą siecią, gdy urządzenie jest w zasięgu. Wybierz pozycję **Wyłącz**, aby zapobiec automatycznemu łączeniu się przez urządzenia.
- **Ukryta sieć**: wybierz pozycję **Włącz**, aby ukrywać tę sieć na liście dostępnych sieci w urządzeniu. Identyfikator SSID nie jest rozgłaszany. Wybierz pozycję **Wyłącz**, aby wyświetlać tę sieć na liście dostępnych sieci w urządzeniu.

## <a name="enterprise"></a>Enterprise

- **Typ sieci Wi-Fi**: wybierz pozycję **Przedsiębiorstwo**.
- **SSID**: wprowadź **Identyfikator zestawu usług**, który jest rzeczywistą nazwą sieci bezprzewodowej, z którą urządzenia nawiązują połączenie. Jednak przy wyborze połączenia użytkownicy widzą tylko **nazwę sieci** utworzoną wcześniej.
- **Połącz automatycznie**: wybierz pozycję **Włącz**, aby automatycznie łączyć się z tą siecią, gdy urządzenie jest w zasięgu. Wybierz pozycję **Wyłącz**, aby zapobiec automatycznemu łączeniu się przez urządzenia.
- **Ukryta sieć**: wybierz pozycję **Włącz**, aby ukrywać tę sieć na liście dostępnych sieci w urządzeniu. Identyfikator SSID nie jest rozgłaszany. Wybierz pozycję **Wyłącz**, aby wyświetlać tę sieć na liście dostępnych sieci w urządzeniu.
- **Typ protokołu EAP**: wybierz typ protokołu uwierzytelniania rozszerzonego (EAP) używany do uwierzytelniania zabezpieczonych połączeń bezprzewodowych. Dostępne opcje: 

  - **EAP-TLS**: wprowadź też następujące ustawienia:

    - **Zaufanie serwera** - **certyfikat główny na potrzeby walidacji serwera**: wybierz istniejący profil zaufanego certyfikatu głównego. Ten certyfikat jest prezentowany serwerowi, gdy klient łączy się z siecią. Uwierzytelnia połączenie.

    - **Uwierzytelnianie klienta** - **certyfikat klienta na potrzeby uwierzytelniania klienta (certyfikat tożsamości)** : wybierz profil certyfikatu protokołu SCEP lub standardów PKCS, który również został wdrożony do urządzenia. Ten certyfikat to tożsamość przesyłana przez urządzenie do serwera w celu uwierzytelnienia połączenia.

    - **Prywatność tożsamości (tożsamość zewnętrzna)** : wprowadź tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość, taką jak `anonymous`. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.

  - **EAP-TTLS**: wprowadź też następujące ustawienia:

    - **Zaufanie serwera** - **certyfikat główny na potrzeby walidacji serwera**: wybierz istniejący profil zaufanego certyfikatu głównego. Ten certyfikat jest prezentowany serwerowi, gdy klient łączy się z siecią. Uwierzytelnia połączenie.

    - **Uwierzytelnianie klienta**: wybierz **metodę uwierzytelniania**. Dostępne opcje:

      - **Nazwa użytkownika i hasło**: monituj użytkownika o nazwę użytkownika i hasło w celu uwierzytelnienia połączenia. Wprowadź też następujące ustawienia:
        - **Metoda inna niż EAP (tożsamość wewnętrzna)** : wybierz sposób uwierzytelniania połączenia. Pamiętaj, aby wybrać ten sam protokół, który został skonfigurowany w sieci Wi-Fi. Dostępne opcje:

          - **Hasło nieszyfrowane (PAP)**
          - **Protokół uwierzytelniania typu Challenge Handshake (CHAP)**
          - **Microsoft CHAP (MS-CHAP)**
          - **Microsoft CHAP wersja 2 (MS-CHAP v2)**

      - **Certyfikaty**: wybierz profil certyfikatu klienta protokołu SCEP lub standardów PKCS, który również został wdrożony w urządzeniu. Ten certyfikat to tożsamość przesyłana przez urządzenie do serwera w celu uwierzytelnienia połączenia.

      - **Prywatność tożsamości (tożsamość zewnętrzna)** : wprowadź tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość, taką jak `anonymous`. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.

  - **PEAP**: wprowadź też następujące ustawienia:

    - **Zaufanie serwera** - **certyfikat główny na potrzeby walidacji serwera**: wybierz istniejący profil zaufanego certyfikatu głównego. Ten certyfikat jest prezentowany serwerowi, gdy klient łączy się z siecią. Uwierzytelnia połączenie.

    - **Uwierzytelnianie klienta**: wybierz **metodę uwierzytelniania**. Dostępne opcje:

      - **Nazwa użytkownika i hasło**: monituj użytkownika o nazwę użytkownika i hasło w celu uwierzytelnienia połączenia. Wprowadź też następujące ustawienia:
        - **Metoda uwierzytelniania inna niż EAP (tożsamość wewnętrzna)** : wybierz sposób uwierzytelniania połączenia. Pamiętaj, aby wybrać ten sam protokół, który został skonfigurowany w sieci Wi-Fi. Dostępne opcje:

          - **Brak**
          - **Microsoft CHAP wersja 2 (MS-CHAP v2)**

      - **Certyfikaty**: wybierz profil certyfikatu klienta protokołu SCEP lub standardów PKCS, który również został wdrożony w urządzeniu. Ten certyfikat to tożsamość przesyłana przez urządzenie do serwera w celu uwierzytelnienia połączenia.

      - **Prywatność tożsamości (tożsamość zewnętrzna)** : wprowadź tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość, taką jak `anonymous`. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje żadnych czynności. Następnie [przypisz ten profil](device-profile-assign.md).

## <a name="more-resources"></a>Dodatkowe zasoby

- [Omówienie ustawień sieci Wi-Fi](wi-fi-settings-configure.md), w tym informacje na temat innych platform.

- Używasz urządzeń z systemem Android dla firm lub urządzeń kiosku systemu Android? Jeśli tak, zapoznaj się z [ustawieniami sieci Wi-Fi dla urządzeń z systemem Android Enterprise i urządzeń dedykowanych](wi-fi-settings-android-enterprise.md).
