---
title: Konfigurowanie ustawień sieci Wi-Fi dla urządzeń z systemem Android w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Tworzenie lub dodawanie profilu konfiguracji urządzeń w sieci Wi-Fi dla systemu Android. Zapoznaj się z różnymi ustawieniami, w tym dotyczącymi dodawania certyfikatów, wybierania typu protokołu EAP i wybierania metody uwierzytelniania w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e99b934597806ea8ee4fbc8d37f53e32cf5c9abf
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55842630"
---
# <a name="add-wi-fi-settings-for-devices-running-android-in-microsoft-intune"></a>Dodawanie ustawień sieci Wi-Fi dla urządzeń z systemem Android w usłudze Microsoft Intune

Można utworzyć profil z określonymi ustawieniami sieci Wi-Fi, a następnie wdrożyć ten profil na urządzeniach z systemem Android. Usługa Microsoft Intune oferuje wiele funkcji, w tym uwierzytelnianie do sieci, dodawanie klucza wstępnego lub protokołu SCEP i inne.

Te ustawienia sieci Wi-Fi są podzielone na dwie kategorie: ustawienia podstawowe i ustawienia na poziomie przedsiębiorstwa.

W tym artykule opisano te ustawienia.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil urządzenia](device-profile-create.md).

## <a name="basic-profile"></a>Profil podstawowy

- **Typ sieci Wi-Fi**: Wybierz pozycję **Podstawowe**.
- **SSID**: identyfikator zestawu usług (ang. **service set identifier**). To ustawienie to prawdziwa nazwa sieci bezprzewodowej, z którą łączą się urządzenia.
- **Połącz automatycznie**: wybierz pozycję **Włącz**, aby automatycznie łączyć się z tą siecią, gdy urządzenie jest w zasięgu. Wybierz pozycję **Wyłącz**, aby zapobiec automatycznemu łączeniu się przez urządzenia.
- **Sieć ukryta**: wybierz pozycję **Włącz**, aby ukrywać tę sieć na liście dostępnych sieci w urządzeniu. Identyfikator SSID nie jest rozgłaszany. Wybierz pozycję **Wyłącz**, aby wyświetlać tę sieć na liście dostępnych sieci w urządzeniu.

## <a name="enterprise-profile"></a>Profil przedsiębiorstwa

- **Typ sieci Wi-Fi**: wybierz pozycję **Przedsiębiorstwo**.
- **SSID**: identyfikator zestawu usług (ang. **service set identifier**). To ustawienie to prawdziwa nazwa sieci bezprzewodowej, z którą łączą się urządzenia.
- **Połącz automatycznie**: wybierz pozycję **Włącz**, aby automatycznie łączyć się z tą siecią, gdy urządzenie jest w zasięgu. Wybierz pozycję **Wyłącz**, aby zapobiec automatycznemu łączeniu się przez urządzenia.
- **Sieć ukryta**: wybierz pozycję **Włącz**, aby ukrywać tę sieć na liście dostępnych sieci w urządzeniu. Identyfikator SSID nie jest rozgłaszany. Wybierz pozycję **Wyłącz**, aby wyświetlać tę sieć na liście dostępnych sieci w urządzeniu.
- **Typ protokołu EAP**: wybierz typ protokołu uwierzytelniania rozszerzonego (EAP) używany do uwierzytelniania zabezpieczonych połączeń bezprzewodowych. Dostępne opcje: 

  - **EAP-TLS**: Wprowadź też następujące ustawienia:

    - **Zaufanie serwera** - **Certyfikat główny weryfikacji serwera**: wybierz istniejący profil zaufanego certyfikatu głównego. Ten certyfikat jest przesyłany na serwer, gdy klient łączy się z siecią, i jest używany do uwierzytelniania połączenia.

      Wybierz przycisk **OK**, aby zapisać zmiany.

    - **Uwierzytelnienie klienta** - **Certyfikat klienta na potrzeby uwierzytelniania klienta (certyfikat tożsamości)**: wybierz profil certyfikatu klienta protokołu SCEP lub PKCS, który również został wdrożony w urządzeniu. Ten certyfikat to tożsamość przesyłana przez urządzenie do serwera w celu uwierzytelnienia połączenia.

      Wybierz przycisk **OK**, aby zapisać zmiany.

  - **EAP-TTLS**: Wprowadź też następujące ustawienia:

    - **Zaufanie serwera** - **Certyfikat główny weryfikacji serwera**: wybierz istniejący profil zaufanego certyfikatu głównego. Ten certyfikat jest przesyłany na serwer, gdy klient łączy się z siecią, i jest używany do uwierzytelniania połączenia.

      Wybierz przycisk **OK**, aby zapisać zmiany.

    - **Uwierzytelnianie klienta**: wybierz **metodę uwierzytelniania**. Dostępne opcje:

      - **Nazwa użytkownika i hasło**: monituj użytkownika o nazwę użytkownika i hasło w celu uwierzytelnienia połączenia. Wprowadź też następujące ustawienia:
        - **Metoda bez protokołu EAP (tożsamość wewnętrzna)**: wybierz sposób uwierzytelniania połączenia. Pamiętaj, aby wybrać ten sam protokół, który został skonfigurowany w sieci Wi-Fi.

          Dostępne opcje: **Hasło nieszyfrowane (PAP)**, **Protokół uwierzytelniania typu Challenge Handshake (CHAP)**, **Microsoft CHAP (MS-CHAP)** i **Microsoft CHAP wersja 2 (MS-CHAP v2)**

      - **Certyfikaty**: wybierz profil certyfikatu klienta protokołu SCEP lub PKCS, który również został wdrożony w urządzeniu. Ten certyfikat to tożsamość przesyłana przez urządzenie do serwera w celu uwierzytelnienia połączenia.

        Wybierz przycisk **OK**, aby zapisać zmiany.

      - **Prywatność tożsamości (tożsamość zewnętrzna)**: wprowadź tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość, taką jak `anonymous`. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.

  - **PEAP**: Wprowadź też następujące ustawienia:

    - **Zaufanie serwera** - **Certyfikat główny weryfikacji serwera**: wybierz istniejący profil zaufanego certyfikatu głównego. Ten certyfikat jest przesyłany na serwer, gdy klient łączy się z siecią, i jest używany do uwierzytelniania połączenia.

      Wybierz przycisk **OK**, aby zapisać zmiany.

    - **Uwierzytelnianie klienta**: wybierz **metodę uwierzytelniania**. Dostępne opcje:

      - **Nazwa użytkownika i hasło**: monituj użytkownika o nazwę użytkownika i hasło w celu uwierzytelnienia połączenia. Wprowadź też następujące ustawienia:
        - **Metoda uwierzytelniania inna niż EAP (tożsamość wewnętrzna)**: wybierz sposób uwierzytelniania połączenia. Pamiętaj, aby wybrać ten sam protokół, który został skonfigurowany w sieci Wi-Fi.

          Dostępne opcje: **Brak** lub **Microsoft CHAP Version 2 (MS-CHAP v2)**

      - **Certyfikaty**: wybierz profil certyfikatu klienta protokołu SCEP lub PKCS, który również został wdrożony w urządzeniu. Ten certyfikat to tożsamość przesyłana przez urządzenie do serwera w celu uwierzytelnienia połączenia.

        Wybierz przycisk **OK**, aby zapisać zmiany.

      - **Prywatność tożsamości (tożsamość zewnętrzna)**: wprowadź tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość, taką jak `anonymous`. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.

Wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany. Profil zostanie utworzony i wyświetlony na liście profilów.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje żadnych czynności. Następnie [przypisz ten profil](device-profile-assign.md).

## <a name="more-resources"></a>Dodatkowe zasoby

- [Omówienie ustawień sieci Wi-Fi](wi-fi-settings-configure.md), w tym informacje na temat innych platform.

- Używasz urządzeń z systemem Android dla firm lub urządzeń kiosku systemu Android? Jeśli tak, zapoznaj się z [ustawieniami sieci Wi-Fi dla urządzeń z systemem Android dla firm i kiosku systemu Android](wi-fi-settings-android-enterprise.md).
