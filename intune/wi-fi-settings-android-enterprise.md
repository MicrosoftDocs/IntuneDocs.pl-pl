---
title: Ustawienia sieci Wi-Fi dla urządzeń z systemem Android Enterprise oraz urządzeń kiosku — Microsoft Intune | Microsoft Docs
description: Tworzenie lub dodawanie profilu konfiguracji urządzeń w sieci Wi-Fi dla systemu Android dla firm i kiosku systemu Android. Zapoznaj się z różnymi ustawieniami, w tym dotyczącymi dodawania certyfikatów, wybierania typu protokołu EAP i wybierania metody uwierzytelniania w usłudze Microsoft Intune. W przypadku urządzeń kiosku należy także wprowadzić klucz wstępny sieci.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/16/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: d96bf5a4b0d9a8ce6aa7de0123a8bcc7e6db9692
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57566441"
---
# <a name="add-wi-fi-settings-for-devices-running-android-enterprise-and-android-kiosk-in-microsoft-intune"></a>Dodawanie ustawień sieci Wi-Fi dla urządzeń z systemem Android dla firm i kiosku systemu Android w usłudze Microsoft Intune

Można utworzyć profil z określonymi ustawieniami sieci Wi-Fi, a następnie wdrożyć ten profil na urządzeniach z systemem Android dla firm i urządzeniach kiosku systemu Android. Usługa Microsoft Intune oferuje wiele funkcji, w uwierzytelnianie do sieci, korzystanie z klucza wstępnego i inne.

W tym artykule opisano te ustawienia. Więcej informacji na temat funkcji sieci Wi-Fi w usłudze Microsoft Intune można znaleźć w artykule [Używanie sieci Wi-Fi na urządzeniach](wi-fi-settings-configure.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil urządzenia](wi-fi-settings-configure.md#create-a-device-profile).

## <a name="device-owner-only---kiosk"></a>Tylko właściciel urządzenia — kiosk

Wybierz tę opcję w przypadku używania urządzenia z systemem Android dla firm jako kiosku.

- **Nazwa sieci**: wprowadź nazwę połączenia sieci Wi-Fi. Ta wartość to nazwa, którą użytkownicy zobaczą podczas przeglądania listy dostępnych połączeń na swoich urządzeniach.
- **Identyfikator SSID**: identyfikator zestawu usług (ang. **service set identifier**). To ustawienie to prawdziwa nazwa sieci bezprzewodowej, z którą łączą się urządzenia. Jednak przy wyborze połączenia użytkownicy widzą tylko **nazwę sieci** utworzoną wcześniej.
- **Połącz automatycznie**: wybierz pozycję **Włącz**, aby automatycznie łączyć się z tą siecią, gdy urządzenie jest w zasięgu. Wybierz pozycję **Wyłącz**, aby zapobiec automatycznemu łączeniu się przez urządzenia.
- **Ukryta sieć**: wybierz pozycję **Włącz**, aby ukrywać tę sieć na liście dostępnych sieci w urządzeniu. Identyfikator SSID nie jest rozgłaszany. Wybierz pozycję **Wyłącz**, aby wyświetlać tę sieć na liście dostępnych sieci w urządzeniu.
- **Typ sieci Wi-Fi**: wybierz protokół zabezpieczeń do uwierzytelniania sieci Wi-Fi. Dostępne opcje:

  - **Otwórz (bez uwierzytelniania)**: tej opcji można używać tylko, jeśli sieć jest niezabezpieczona.
  - **Klucz wstępny protokołu WEP**: wprowadź hasło w polu **Klucz wstępny**. Podczas ustawiania lub konfigurowania sieci organizacji jest również konfigurowane hasło lub klucz sieciowy. Wprowadź to hasło lub klucz sieciowy dla wartości klucza wstępnego.
  - **Klucz wstępny funkcji WPA**: wprowadź hasło w polu **Klucz wstępny**. Podczas ustawiania lub konfigurowania sieci organizacji jest również konfigurowane hasło lub klucz sieciowy. Wprowadź to hasło lub klucz sieciowy dla wartości klucza wstępnego.

Wybierz przycisk **OK**, aby zapisać zmiany.

## <a name="work-profile-only"></a>Tylko profil służbowy

### <a name="basic-settings"></a>Ustawienia podstawowe

- **Typ sieci Wi-Fi**: wybierz pozycję **Podstawowa**.
- **Identyfikator SSID**: identyfikator zestawu usług (ang. **service set identifier**). To ustawienie to prawdziwa nazwa sieci bezprzewodowej, z którą łączą się urządzenia.
- **Połącz automatycznie**: wybierz pozycję **Włącz**, aby automatycznie łączyć się z tą siecią, gdy urządzenie jest w zasięgu. Wybierz pozycję **Wyłącz**, aby zapobiec automatycznemu łączeniu się przez urządzenia.
- **Ukryta sieć**: wybierz pozycję **Włącz**, aby ukrywać tę sieć na liście dostępnych sieci w urządzeniu. Identyfikator SSID nie jest rozgłaszany. Wybierz pozycję **Wyłącz**, aby wyświetlać tę sieć na liście dostępnych sieci w urządzeniu.

## <a name="enterprise-profile"></a>Profil przedsiębiorstwa

- **Typ sieci Wi-Fi**: wybierz pozycję **Przedsiębiorstwo**.
- **Identyfikator SSID**: identyfikator zestawu usług (ang. **service set identifier**). To ustawienie to prawdziwa nazwa sieci bezprzewodowej, z którą łączą się urządzenia.
- **Połącz automatycznie**: wybierz pozycję **Włącz**, aby automatycznie łączyć się z tą siecią, gdy urządzenie jest w zasięgu. Wybierz pozycję **Wyłącz**, aby zapobiec automatycznemu łączeniu się przez urządzenia.
- **Ukryta sieć**: wybierz pozycję **Włącz**, aby ukrywać tę sieć na liście dostępnych sieci w urządzeniu. Identyfikator SSID nie jest rozgłaszany. Wybierz pozycję **Wyłącz**, aby wyświetlać tę sieć na liście dostępnych sieci w urządzeniu.
- **Typ protokołu EAP**: wybierz typ protokołu uwierzytelniania rozszerzonego (EAP) używany do uwierzytelniania zabezpieczonych połączeń bezprzewodowych. Dostępne opcje: 

  - **EAP-TLS**: wprowadź też następujące ustawienia:

    - **Zaufanie serwera** - **certyfikat główny na potrzeby walidacji serwera**: wybierz istniejący profil zaufanego certyfikatu głównego. Gdy klient łączy się z siecią, ten certyfikat jest przedstawiany na serwerze i uwierzytelnia połączenie.

      Wybierz przycisk **OK**, aby zapisać zmiany.

    - **Uwierzytelnianie klienta** - **certyfikat klienta na potrzeby uwierzytelniania klienta (certyfikat tożsamości)**: wybierz profil certyfikatu protokołu SCEP lub standardów PKCS, który również został wdrożony do urządzenia. Ten certyfikat to tożsamość przesyłana przez urządzenie do serwera w celu uwierzytelnienia połączenia.

      Wybierz przycisk **OK**, aby zapisać zmiany.

  - **EAP-TTLS**: wprowadź też następujące ustawienia:

    - **Zaufanie serwera** - **certyfikat główny na potrzeby walidacji serwera**: wybierz istniejący profil zaufanego certyfikatu głównego. Gdy klient łączy się z siecią, ten certyfikat jest przedstawiany na serwerze i uwierzytelnia połączenie.

      Wybierz przycisk **OK**, aby zapisać zmiany.

    - **Uwierzytelnianie klienta**: wybierz **metodę uwierzytelniania**. Dostępne opcje:

      - **Nazwa użytkownika i hasło**: monituj użytkownika o nazwę użytkownika i hasło w celu uwierzytelnienia połączenia. Wprowadź też następujące ustawienia:
        - **Metoda inna niż EAP (tożsamość wewnętrzna)**: wybierz sposób uwierzytelniania połączenia. Pamiętaj, aby wybrać ten sam protokół, który został skonfigurowany w sieci Wi-Fi.

          Dostępne opcje: **Hasło nieszyfrowane (PAP)**, **Protokół uwierzytelniania typu Challenge Handshake (CHAP)**, **Microsoft CHAP (MS-CHAP)** i **Microsoft CHAP wersja 2 (MS-CHAP v2)**

      - **Certyfikaty**: wybierz profil certyfikatu klienta protokołu SCEP lub standardów PKCS, który również został wdrożony w urządzeniu. Ten certyfikat to tożsamość przesyłana przez urządzenie do serwera w celu uwierzytelnienia połączenia.

        Wybierz przycisk **OK**, aby zapisać zmiany.

      - **Prywatność tożsamości (tożsamość zewnętrzna)**: wprowadź tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość, taką jak `anonymous`. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.

  - **PEAP**: wprowadź też następujące ustawienia:

    - **Zaufanie serwera** - **certyfikat główny na potrzeby walidacji serwera**: wybierz istniejący profil zaufanego certyfikatu głównego. Gdy klient łączy się z siecią, ten certyfikat jest przedstawiany na serwerze i uwierzytelnia połączenie.

      Wybierz przycisk **OK**, aby zapisać zmiany.

    - **Uwierzytelnianie klienta**: wybierz **metodę uwierzytelniania**. Dostępne opcje:

      - **Nazwa użytkownika i hasło**: monituj użytkownika o nazwę użytkownika i hasło w celu uwierzytelnienia połączenia. Wprowadź też następujące ustawienia:
        - **Metoda uwierzytelniania inna niż EAP (tożsamość wewnętrzna)**: wybierz sposób uwierzytelniania połączenia. Pamiętaj, aby wybrać ten sam protokół, który został skonfigurowany w sieci Wi-Fi.

          Dostępne opcje: **Brak** lub **Microsoft CHAP wersja 2 (MS-CHAP v2)**

      - **Certyfikaty**: wybierz profil certyfikatu klienta protokołu SCEP lub standardów PKCS, który również został wdrożony w urządzeniu. Ten certyfikat to tożsamość przesyłana przez urządzenie do serwera w celu uwierzytelnienia połączenia.

        Wybierz przycisk **OK**, aby zapisać zmiany.

      - **Prywatność tożsamości (tożsamość zewnętrzna)**: wprowadź tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość, taką jak `anonymous`. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.

Wybierz kolejno pozycje **OK** > **Utwórz**, aby zapisać zmiany. Profil zostanie utworzony i wyświetlony na liście profilów.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje żadnych czynności. Następnie [przypiszesz ten profil](device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).

Możesz również utworzyć profile sieci Wi-Fi dla urządzeń z systemami [Android](wi-fi-settings-android.md), [iOS](wi-fi-settings-ios.md), [macOS](wi-fi-settings-macos.md), [Windows 10](wi-fi-settings-windows.md) i [Windows 8.1](wi-fi-settings-import-windows-8-1.md).
