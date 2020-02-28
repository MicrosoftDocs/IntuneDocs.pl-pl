---
title: Ustawienia sieci Wi-Fi dla urządzeń z systemem Android Enterprise oraz urządzeń kiosku — Microsoft Intune | Microsoft Docs
description: Tworzenie lub dodawanie profilu konfiguracji urządzeń w sieci Wi-Fi dla systemu Android dla firm i kiosku systemu Android. Zapoznaj się z różnymi ustawieniami, w tym dotyczącymi dodawania certyfikatów, wybierania typu protokołu EAP i wybierania metody uwierzytelniania w usłudze Microsoft Intune. W przypadku urządzeń kiosku należy także wprowadzić klucz wstępny sieci.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: maholdaa
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: aef1747fdbb3118db82f6e99c2838632c8a9d369
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77512453"
---
# <a name="add-wi-fi-settings-for-android-enterprise-dedicated-and-fully-managed-devices-in-microsoft-intune"></a>Dodawanie ustawień sieci Wi-Fi dla dedykowanych i w pełni zarządzanych urządzeń z systemem Android Enterprise w usłudze Microsoft Intune

Możesz utworzyć profil z określonymi ustawieniami Wi-Fi, po czym wdrożyć go w urządzeniach z systemem Android w wersji Enterprise dedykowanych i w pełni zarządzanych. Usługa Microsoft Intune oferuje wiele funkcji, w uwierzytelnianie do sieci, korzystanie z klucza wstępnego i inne.

W tym artykule opisano te ustawienia. Więcej informacji na temat funkcji sieci Wi-Fi w usłudze Microsoft Intune można znaleźć w artykule [Używanie sieci Wi-Fi na urządzeniach](wi-fi-settings-configure.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil urządzenia](wi-fi-settings-configure.md#create-a-device-profile).

## <a name="device-owner-only"></a>Tylko właściciel urządzenia

Wybierz tę opcję, jeśli wdrażasz na dedykowanym lub w pełni zarządzanym urządzeniu z systemem Android Enterprise.  Dedykowane i w pełni zarządzane urządzenia z systemem Android Enterprise obecnie obsługują wdrażanie certyfikatów protokołu SCEP, ale nie PKCS.

### <a name="basic"></a>Podstawowy

- **Typ sieci Wi-Fi**: Wybierz pozycję **Podstawowe**.
- **Nazwa sieci**: wprowadź nazwę połączenia sieci Wi-Fi. Użytkownicy końcowi widzą tę nazwę, przeglądając w urządzeniu listę dostępnych połączeń sieci Wi-Fi. Na przykład wprowadź nazwę **Contoso WiFi**.
- **SSID**: wprowadź **identyfikator zestawu usług** będący prawdziwą nazwą sieci bezprzewodowej, z którą łączą się urządzenia. Jednak przy wyborze połączenia użytkownicy widzą tylko **nazwę sieci** utworzoną wcześniej.
- **Sieć ukryta**: wybierz pozycję **Włącz**, aby ukrywać tę sieć na liście dostępnych sieci w urządzeniu. Identyfikator SSID nie jest rozgłaszany. Wybierz pozycję **Wyłącz**, aby wyświetlać tę sieć na liście dostępnych sieci w urządzeniu.
- **Typ sieci Wi-Fi**: wybierz protokół zabezpieczeń do uwierzytelniania sieci Wi-Fi. Dostępne opcje:

  - **Otwarte (brak uwierzytelniania)** : z tej opcji można korzystać tylko w sytuacji, gdy sieć jest niezabezpieczona.
  - **Wstępnie udostępniony klucz WEP**: wprowadź hasło w polu **Klucz wstępny**. Podczas ustawiania lub konfigurowania sieci organizacji jest również konfigurowane hasło lub klucz sieciowy. Wprowadź to hasło lub klucz sieciowy dla wartości klucza wstępnego.
  - **Wstępnie udostępniony klucz WPA**: wprowadź hasło w polu **Klucz wstępny**. Podczas ustawiania lub konfigurowania sieci organizacji jest również konfigurowane hasło lub klucz sieciowy. Wprowadź to hasło lub klucz sieciowy dla wartości klucza wstępnego.

### <a name="enterprise"></a>Enterprise

- **Typ sieci Wi-Fi**: wybierz pozycję **Przedsiębiorstwo**.
- **SSID**: wprowadź **identyfikator zestawu usług** będący prawdziwą nazwą sieci bezprzewodowej, z którą łączą się urządzenia. Jednak przy wyborze połączenia użytkownicy widzą tylko **nazwę sieci** utworzoną wcześniej.
- **Sieć ukryta**: wybierz pozycję **Włącz**, aby ukrywać tę sieć na liście dostępnych sieci w urządzeniu. Identyfikator SSID nie jest rozgłaszany. Wybierz pozycję **Wyłącz**, aby wyświetlać tę sieć na liście dostępnych sieci w urządzeniu.
- **Typ protokołu EAP**: wybierz typ protokołu uwierzytelniania rozszerzonego (EAP) używany do uwierzytelniania zabezpieczonych połączeń bezprzewodowych. Dostępne opcje:

  - **EAP-TLS**: Wprowadź też następujące ustawienia:

    - **Zaufanie serwera** - **Certyfikat główny weryfikacji serwera**: wybierz istniejący profil zaufanego certyfikatu głównego. Gdy klient łączy się z siecią, ten certyfikat jest przedstawiany na serwerze i uwierzytelnia połączenie.

    - **Uwierzytelnienie klienta** - **Certyfikat klienta na potrzeby uwierzytelniania klienta (certyfikat tożsamości)** : wybierz profil certyfikatu klienta protokołu SCEP, który również został wdrożony w urządzeniu. Ten certyfikat to tożsamość przesyłana przez urządzenie do serwera w celu uwierzytelnienia połączenia.

    - **Prywatność tożsamości (tożsamość zewnętrzna)** : wprowadź tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość, taką jak `anonymous`. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.

  - **EAP-TTLS**: Wprowadź też następujące ustawienia:

    - **Zaufanie serwera** - **Certyfikat główny weryfikacji serwera**: wybierz istniejący profil zaufanego certyfikatu głównego. Gdy klient łączy się z siecią, ten certyfikat jest przedstawiany na serwerze i uwierzytelnia połączenie.

    - **Uwierzytelnianie klienta**: Wybierz **metodę uwierzytelniania**. Dostępne opcje:

      - **Nazwa użytkownika i hasło**: monituj użytkownika o nazwę użytkownika i hasło w celu uwierzytelnienia połączenia. Wprowadź też następujące ustawienia:
        - **Metoda bez protokołu EAP (tożsamość wewnętrzna)** : wybierz sposób uwierzytelniania połączenia. Pamiętaj, aby wybrać ten sam protokół, który został skonfigurowany w sieci Wi-Fi. Dostępne opcje:

          - **Hasło nieszyfrowane (PAP)**
          - **Microsoft CHAP (MS-CHAP)**
          - **Microsoft CHAP wersja 2 (MS-CHAP v2)**

      - **Certyfikaty**: wybierz profil certyfikatu klienta protokołu SCEP, który również został wdrożony w urządzeniu. Ten certyfikat to tożsamość przesyłana przez urządzenie do serwera w celu uwierzytelnienia połączenia.

      - **Prywatność tożsamości (tożsamość zewnętrzna)** : wprowadź tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość, taką jak `anonymous`. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.

  - **PEAP**: Wprowadź też następujące ustawienia:

    - **Zaufanie serwera** - **Certyfikat główny weryfikacji serwera**: wybierz istniejący profil zaufanego certyfikatu głównego. Gdy klient łączy się z siecią, ten certyfikat jest przedstawiany na serwerze i uwierzytelnia połączenie.

    - **Uwierzytelnianie klienta**: Wybierz **metodę uwierzytelniania**. Dostępne opcje:

      - **Nazwa użytkownika i hasło**: monituj użytkownika o nazwę użytkownika i hasło w celu uwierzytelnienia połączenia. Wprowadź też następujące ustawienia:
        - **Metoda uwierzytelniania inna niż EAP (tożsamość wewnętrzna)** : wybierz sposób uwierzytelniania połączenia. Pamiętaj, aby wybrać ten sam protokół, który został skonfigurowany w sieci Wi-Fi. Dostępne opcje:

          - **Brak**
          - **Microsoft CHAP wersja 2 (MS-CHAP v2)**

      - **Certyfikaty**: wybierz profil certyfikatu klienta protokołu SCEP, który również został wdrożony w urządzeniu. Ten certyfikat to tożsamość przesyłana przez urządzenie do serwera w celu uwierzytelnienia połączenia.

      - **Prywatność tożsamości (tożsamość zewnętrzna)** : wprowadź tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość, taką jak `anonymous`. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.

## <a name="work-profile-only"></a>Tylko profil służbowy

### <a name="basic"></a>Podstawowy

- **Typ sieci Wi-Fi**: Wybierz pozycję **Podstawowe**.
- **SSID**: wprowadź **identyfikator zestawu usług** będący prawdziwą nazwą sieci bezprzewodowej, z którą łączą się urządzenia. Jednak przy wyborze połączenia użytkownicy widzą tylko **nazwę sieci** utworzoną wcześniej.
- **Sieć ukryta**: wybierz pozycję **Włącz**, aby ukrywać tę sieć na liście dostępnych sieci w urządzeniu. Identyfikator SSID nie jest rozgłaszany. Wybierz pozycję **Wyłącz**, aby wyświetlać tę sieć na liście dostępnych sieci w urządzeniu.

### <a name="enterprise"></a>Enterprise

- **Typ sieci Wi-Fi**: wybierz pozycję **Przedsiębiorstwo**.
- **SSID**: wprowadź **identyfikator zestawu usług** będący prawdziwą nazwą sieci bezprzewodowej, z którą łączą się urządzenia. Jednak przy wyborze połączenia użytkownicy widzą tylko **nazwę sieci** utworzoną wcześniej.
- **Sieć ukryta**: wybierz pozycję **Włącz**, aby ukrywać tę sieć na liście dostępnych sieci w urządzeniu. Identyfikator SSID nie jest rozgłaszany. Wybierz pozycję **Wyłącz**, aby wyświetlać tę sieć na liście dostępnych sieci w urządzeniu.
- **Typ protokołu EAP**: wybierz typ protokołu uwierzytelniania rozszerzonego (EAP) używany do uwierzytelniania zabezpieczonych połączeń bezprzewodowych. Dostępne opcje:

  - **EAP-TLS**: Wprowadź też następujące ustawienia:

    - **Zaufanie serwera** - **Certyfikat główny weryfikacji serwera**: wybierz istniejący profil zaufanego certyfikatu głównego. Gdy klient łączy się z siecią, ten certyfikat jest przedstawiany na serwerze i uwierzytelnia połączenie.

    - **Uwierzytelnienie klienta** - **Certyfikat klienta na potrzeby uwierzytelniania klienta (certyfikat tożsamości)** : wybierz profil certyfikatu klienta protokołu SCEP lub PKCS, który również został wdrożony w urządzeniu. Ten certyfikat to tożsamość przesyłana przez urządzenie do serwera w celu uwierzytelnienia połączenia.

    - **Prywatność tożsamości (tożsamość zewnętrzna)** : wprowadź tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość, taką jak `anonymous`. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.

  - **EAP-TTLS**: Wprowadź też następujące ustawienia:

    - **Zaufanie serwera** - **Certyfikat główny weryfikacji serwera**: wybierz istniejący profil zaufanego certyfikatu głównego. Gdy klient łączy się z siecią, ten certyfikat jest przedstawiany na serwerze i uwierzytelnia połączenie.

    - **Uwierzytelnianie klienta**: Wybierz **metodę uwierzytelniania**. Dostępne opcje:

      - **Nazwa użytkownika i hasło**: monituj użytkownika o nazwę użytkownika i hasło w celu uwierzytelnienia połączenia. Wprowadź też następujące ustawienia:
        - **Metoda bez protokołu EAP (tożsamość wewnętrzna)** : wybierz sposób uwierzytelniania połączenia. Pamiętaj, aby wybrać ten sam protokół, który został skonfigurowany w sieci Wi-Fi. Dostępne opcje:

          - **Hasło nieszyfrowane (PAP)**
          - **Microsoft CHAP (MS-CHAP)**
          - **Microsoft CHAP wersja 2 (MS-CHAP v2)**

      - **Certyfikaty**: wybierz profil certyfikatu klienta protokołu SCEP lub PKCS, który również został wdrożony w urządzeniu. Ten certyfikat to tożsamość przesyłana przez urządzenie do serwera w celu uwierzytelnienia połączenia.

      - **Prywatność tożsamości (tożsamość zewnętrzna)** : wprowadź tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość, taką jak `anonymous`. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.

  - **PEAP**: Wprowadź też następujące ustawienia:

    - **Zaufanie serwera** - **Certyfikat główny weryfikacji serwera**: wybierz istniejący profil zaufanego certyfikatu głównego. Gdy klient łączy się z siecią, ten certyfikat jest przedstawiany na serwerze i uwierzytelnia połączenie.

    - **Uwierzytelnianie klienta**: Wybierz **metodę uwierzytelniania**. Dostępne opcje:

      - **Nazwa użytkownika i hasło**: monituj użytkownika o nazwę użytkownika i hasło w celu uwierzytelnienia połączenia. Wprowadź też następujące ustawienia:
        - **Metoda uwierzytelniania inna niż EAP (tożsamość wewnętrzna)** : wybierz sposób uwierzytelniania połączenia. Pamiętaj, aby wybrać ten sam protokół, który został skonfigurowany w sieci Wi-Fi. Dostępne opcje:

          - **Brak**
          - **Microsoft CHAP wersja 2 (MS-CHAP v2)**

      - **Certyfikaty**: wybierz profil certyfikatu klienta protokołu SCEP lub PKCS, który również został wdrożony w urządzeniu. Ten certyfikat to tożsamość przesyłana przez urządzenie do serwera w celu uwierzytelnienia połączenia.

      - **Prywatność tożsamości (tożsamość zewnętrzna)** : wprowadź tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość, taką jak `anonymous`. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje żadnych czynności. Następnie [przypiszesz ten profil](device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).

Możesz również utworzyć profile sieci Wi-Fi dla urządzeń z systemami [Android](wi-fi-settings-android.md), [iOS/iPadOS](wi-fi-settings-ios.md), [macOS](wi-fi-settings-macos.md), [Windows 10](wi-fi-settings-windows.md) i [Windows 8.1](wi-fi-settings-import-windows-8-1.md).
