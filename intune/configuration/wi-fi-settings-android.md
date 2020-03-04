---
title: Konfigurowanie ustawień sieci Wi-Fi dla urządzeń z systemem Android w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Tworzenie lub dodawanie profilu konfiguracji urządzeń w sieci Wi-Fi dla systemu Android. Zapoznaj się z różnymi ustawieniami, w tym dotyczącymi dodawania certyfikatów, wybierania typu protokołu EAP i wybierania metody uwierzytelniania w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/26/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: maholdaa
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 955d9931779752e8736435555db7f7aba777b430
ms.sourcegitcommit: 8b716db3c0fdbb7dff62497ec283902a5069a343
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/27/2020
ms.locfileid: "77652406"
---
# <a name="add-wi-fi-settings-for-devices-running-android-in-microsoft-intune"></a>Dodawanie ustawień sieci Wi-Fi dla urządzeń z systemem Android w usłudze Microsoft Intune

Można utworzyć profil z określonymi ustawieniami sieci Wi-Fi, a następnie wdrożyć ten profil na urządzeniach z systemem Android. Usługa Microsoft Intune oferuje wiele funkcji, w tym uwierzytelnianie do sieci, dodawanie klucza wstępnego lub protokołu SCEP i inne.

Te ustawienia sieci Wi-Fi są podzielone na dwie kategorie: ustawienia podstawowe i ustawienia na poziomie przedsiębiorstwa.

W tym artykule opisano te ustawienia.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil urządzenia](device-profile-create.md).

## <a name="basic"></a>Podstawowy

- **Typ sieci Wi-Fi**: Wybierz pozycję **Podstawowe**.
- **SSID**: wprowadź **identyfikator zestawu usług** będący prawdziwą nazwą sieci bezprzewodowej, z którą łączą się urządzenia. Jednak przy wyborze połączenia użytkownicy widzą tylko **nazwę sieci** utworzoną wcześniej.
- **Sieć ukryta**: wybierz pozycję **Włącz**, aby ukrywać tę sieć na liście dostępnych sieci w urządzeniu. Identyfikator SSID nie jest rozgłaszany. Wybierz pozycję **Wyłącz**, aby wyświetlać tę sieć na liście dostępnych sieci w urządzeniu.

## <a name="enterprise"></a>Enterprise

- **Typ sieci Wi-Fi**: wybierz pozycję **Przedsiębiorstwo**.
- **SSID**: wprowadź **identyfikator zestawu usług** będący prawdziwą nazwą sieci bezprzewodowej, z którą łączą się urządzenia. Jednak przy wyborze połączenia użytkownicy widzą tylko **nazwę sieci** utworzoną wcześniej.
- **Sieć ukryta**: wybierz pozycję **Włącz**, aby ukrywać tę sieć na liście dostępnych sieci w urządzeniu. Identyfikator SSID nie jest rozgłaszany. Wybierz pozycję **Wyłącz**, aby wyświetlać tę sieć na liście dostępnych sieci w urządzeniu.
- **Typ protokołu EAP**: wybierz typ protokołu uwierzytelniania rozszerzonego (EAP) używany do uwierzytelniania zabezpieczonych połączeń bezprzewodowych. Dostępne opcje:

  - **EAP-TLS**: Wprowadź też następujące ustawienia:

    - **Zaufanie serwera** - **Certyfikat główny weryfikacji serwera**: wybierz istniejący profil zaufanego certyfikatu głównego. Ten certyfikat jest przedstawiany na serwerze, gdy klient łączy się z siecią. Uwierzytelnia on połączenie.

    - **Uwierzytelnienie klienta** - **Certyfikat klienta na potrzeby uwierzytelniania klienta (certyfikat tożsamości)** : wybierz profil certyfikatu klienta protokołu SCEP lub PKCS, który również został wdrożony w urządzeniu. Ten certyfikat to tożsamość przesyłana przez urządzenie do serwera w celu uwierzytelnienia połączenia.

    - **Prywatność tożsamości (tożsamość zewnętrzna)** : wprowadź tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość, taką jak `anonymous`. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.

  - **EAP-TTLS**: Wprowadź też następujące ustawienia:

    - **Zaufanie serwera** - **Certyfikat główny weryfikacji serwera**: wybierz istniejący profil zaufanego certyfikatu głównego. Ten certyfikat jest przedstawiany na serwerze, gdy klient łączy się z siecią. Uwierzytelnia on połączenie.

    - **Uwierzytelnianie klienta**: Wybierz **metodę uwierzytelniania**. Dostępne opcje:

      - **Nazwa użytkownika i hasło**: monituj użytkownika o nazwę użytkownika i hasło w celu uwierzytelnienia połączenia. Wprowadź też następujące ustawienia:
        - **Metoda bez protokołu EAP (tożsamość wewnętrzna)** : wybierz sposób uwierzytelniania połączenia. Pamiętaj, aby wybrać ten sam protokół, który został skonfigurowany w sieci Wi-Fi. Dostępne opcje:

          - **Hasło nieszyfrowane (PAP)**
          - **Protokół uwierzytelniania typu Challenge Handshake (CHAP)**
          - **Microsoft CHAP (MS-CHAP)**
          - **Microsoft CHAP wersja 2 (MS-CHAP v2)**

      - **Certyfikaty**: wybierz profil certyfikatu klienta protokołu SCEP lub PKCS, który również został wdrożony w urządzeniu. Ten certyfikat to tożsamość przesyłana przez urządzenie do serwera w celu uwierzytelnienia połączenia.

      - **Prywatność tożsamości (tożsamość zewnętrzna)** : wprowadź tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość, taką jak `anonymous`. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.

  - **PEAP**: Wprowadź też następujące ustawienia:

    - **Zaufanie serwera** - **Certyfikat główny weryfikacji serwera**: wybierz istniejący profil zaufanego certyfikatu głównego. Ten certyfikat jest przedstawiany na serwerze, gdy klient łączy się z siecią. Uwierzytelnia on połączenie.

    - **Uwierzytelnianie klienta**: Wybierz **metodę uwierzytelniania**. Dostępne opcje:

      - **Nazwa użytkownika i hasło**: monituj użytkownika o nazwę użytkownika i hasło w celu uwierzytelnienia połączenia. Wprowadź też następujące ustawienia:
        - **Metoda uwierzytelniania inna niż EAP (tożsamość wewnętrzna)** : wybierz sposób uwierzytelniania połączenia. Pamiętaj, aby wybrać ten sam protokół, który został skonfigurowany w sieci Wi-Fi. Dostępne opcje:

          - **Brak**
          - **Microsoft CHAP wersja 2 (MS-CHAP v2)**

      - **Certyfikaty**: wybierz profil certyfikatu klienta protokołu SCEP lub PKCS, który również został wdrożony w urządzeniu. Ten certyfikat to tożsamość przesyłana przez urządzenie do serwera w celu uwierzytelnienia połączenia.

      - **Prywatność tożsamości (tożsamość zewnętrzna)** : wprowadź tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość, taką jak `anonymous`. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje żadnych czynności. Następnie [przypisz ten profil](device-profile-assign.md).

## <a name="more-resources"></a>Dodatkowe zasoby

- [Omówienie ustawień sieci Wi-Fi](wi-fi-settings-configure.md), w tym informacje na temat innych platform.

- Używasz urządzeń z systemem Android dla firm lub urządzeń kiosku systemu Android? Jeśli tak, zapoznaj się z [ustawieniami sieci Wi-Fi dla urządzeń z systemem Android Enterprise i urządzeń dedykowanych](wi-fi-settings-android-enterprise.md).
