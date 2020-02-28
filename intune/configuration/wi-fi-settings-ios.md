---
title: Konfigurowanie ustawień sieci Wi-Fi dla urządzeń z systemem iOS/iPadOS w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Tworzenie lub dodawanie profilu konfiguracji urządzeń z systemem iOS/iPadOS. Zapoznaj się z różnymi ustawieniami, w tym dotyczącymi dodawania certyfikatów, wybierania typu protokołu EAP i wybierania metody uwierzytelniania w usłudze Microsoft Intune.
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
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 68685428ac94dfe08306858774eaf98fb079e66c
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77512317"
---
# <a name="add-wi-fi-settings-for-ios-and-ipados-devices-in-microsoft-intune"></a>Dodawanie ustawień sieci Wi-Fi dla urządzeń z systemem iOS i iPadOS w usłudze Microsoft Intune

Można utworzyć profil z określonymi ustawieniami sieci Wi-Fi, a następnie wdrożyć ten profil na urządzeniach z systemem iOS/iPadOS. Usługa Microsoft Intune oferuje wiele funkcji, w tym uwierzytelnianie do sieci, dodawanie certyfikatu PKCS lub SCEP i inne.

Te ustawienia sieci Wi-Fi są podzielone na dwie kategorie: ustawienia podstawowe i ustawienia na poziomie przedsiębiorstwa.

W tym artykule opisano te ustawienia.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil urządzenia](../device-profile-create.md).

> [!NOTE]
> Te ustawienia są dostępne dla wszystkich typów rejestracji. Aby uzyskać więcej informacji na temat typów rejestracji, zobacz [Rejestracja systemu iOS/iPadOS](../enrollment/ios-enroll.md).

## <a name="basic-profiles"></a>Profile podstawowe

- **Typ sieci Wi-Fi**: Wybierz pozycję **Podstawowe**.
- **Nazwa sieci**: wprowadź nazwę połączenia sieci Wi-Fi. Ta wartość to nazwa, którą użytkownicy zobaczą podczas przeglądania listy dostępnych połączeń na swoich urządzeniach.
- **SSID**: identyfikator zestawu usług (ang. **service set identifier**). Ta właściwość to prawdziwa nazwa sieci bezprzewodowej, z którą łączą się urządzenia. Jednak przy wyborze połączenia użytkownicy widzą tylko nazwę sieci utworzoną wcześniej.
- **Połącz automatycznie**: wybierz pozycję **Włącz**, aby automatycznie łączyć się z tą siecią, gdy urządzenie jest w zasięgu. Wybierz pozycję **Wyłącz**, aby zapobiec automatycznemu łączeniu się przez urządzenia.
- **Sieć ukryta**: Wybierz pozycję **Włącz**, jeśli nie jest rozgłaszany identyfikator SSID sieci. Wybierz pozycję **Wyłącz**, jeśli identyfikator SSID sieci jest rozgłaszany i widoczny.
- **Typ zabezpieczeń**: wybierz protokół zabezpieczeń do uwierzytelniania sieci Wi-Fi. Dostępne opcje:

  - **Otwarte (brak uwierzytelniania)** : z tej opcji można korzystać tylko w sytuacji, gdy sieć jest niezabezpieczona.
  - **WPA/WPA2-Personal**: wprowadź hasło w polu **Klucz wstępny**. Podczas ustawiania lub konfigurowania sieci organizacji jest również konfigurowane hasło lub klucz sieciowy. Wprowadź to hasło lub klucz sieciowy dla wartości klucza wstępnego.
  - **Szyfrowanie danych**

- **Ustawienia serwera proxy**: Dostępne opcje:
  - **Brak**: nie są konfigurowane żadne ustawienia serwera proxy.
  - **Ręczne**: wprowadź **adres serwera proxy** jako adres IP oraz jego **numer portu**.
  - **Automatyczne**: Użyj pliku do skonfigurowania serwera proxy. Wprowadź **adres URL serwera proxy** (np. `http://proxy.contoso.com`), który zawiera plik konfiguracji.

## <a name="enterprise-profiles"></a>Profile przedsiębiorstwa

- **Typ sieci Wi-Fi**: wybierz pozycję **Przedsiębiorstwo**.
- **SSID**: identyfikator zestawu usług (ang. **service set identifier**). Ta właściwość to prawdziwa nazwa sieci bezprzewodowej, z którą łączą się urządzenia. Jednak przy wyborze połączenia użytkownicy widzą tylko nazwę sieci utworzoną wcześniej.
- **Połącz automatycznie**: wybierz pozycję **Włącz**, aby automatycznie łączyć się z tą siecią, gdy urządzenie jest w zasięgu. Wybierz pozycję **Wyłącz**, aby zapobiec automatycznemu łączeniu się przez urządzenia.
- **Sieć ukryta**: wybierz pozycję **Włącz**, aby ukrywać tę sieć na liście dostępnych sieci w urządzeniu. Identyfikator SSID nie jest rozgłaszany. Wybierz pozycję **Wyłącz**, aby wyświetlać tę sieć na liście dostępnych sieci w urządzeniu.

- **Typ protokołu EAP**: wybierz typ protokołu uwierzytelniania rozszerzonego (EAP) używany do uwierzytelniania zabezpieczonych połączeń bezprzewodowych. Dostępne opcje:

  - **EAP-FAST**: wprowadź **ustawienia PAC (Protected Access Credential)** . Ta opcja używa poświadczeń dostępu chronionego do utworzenia uwierzytelnionego tunelu między klientem i serwerem uwierzytelniania. Dostępne opcje:
    - **Nie używaj (PAC)**
    - **Użyj (PAC)** : jeśli plik PAC istnieje, użyj go.
    - **Użyj pliku PAC i aprowizuj go**: tworzenie i dodawanie pliku PAC do urządzeń.
    - **Użyj pliku PAC i aprowizuj go anonimowo**: tworzenie i dodawanie pliku PAC do urządzeń bez uwierzytelniania na serwerze.

  - **EAP-SIM**

  - **EAP-TLS**: Wprowadź też następujące ustawienia:

    - **Zaufanie serwera** - **Nazwy serwerów certyfikatów**: **dodaj** co najmniej jedną nazwę pospolitą używaną w certyfikatach wystawionych przez zaufany urząd certyfikacji do serwerów dostępu do sieci bezprzewodowej. Na przykład dodaj element `mywirelessserver.contoso.com` lub `mywirelessserver`. W przypadku wprowadzania tych informacji można pominąć dynamiczne okno dialogowe zaufania pokazywane na urządzeniach użytkowników nawiązujących połączenie z siecią Wi-Fi.
    - **Certyfikat główny weryfikacji serwera**: wybierz istniejący profil zaufanego certyfikatu głównego. Ten certyfikat pozwala klientowi ufać certyfikatowi serwera dostępu do sieci bezprzewodowej.

    - **Uwierzytelnianie klienta**: wybierz **metodę uwierzytelniania**. Dostępne opcje:

      - **Poświadczenie pochodne**: Użyj certyfikatu pochodzącego z karty inteligentnej użytkownika. Jeśli nie skonfigurowano wystawcy poświadczeń pochodnych, usługa Intune wyświetli monit o dodanie go. Aby uzyskać więcej informacji, zobacz [Korzystanie z poświadczeń pochodnych w usłudze Microsoft Intune](../protect/derived-credentials.md).

      - **Certyfikaty**: wybierz profil certyfikatu klienta protokołu SCEP lub PKCS, który również został wdrożony w urządzeniu. Ten certyfikat to tożsamość przesyłana przez urządzenie do serwera w celu uwierzytelnienia połączenia.

    - **Prywatność tożsamości (tożsamość zewnętrzna)** : wprowadź tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość, taką jak `anonymous`. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.

  - **EAP-TTLS**: Wprowadź też następujące ustawienia:

    - **Zaufanie serwera** - **Nazwy serwerów certyfikatów**: **dodaj** co najmniej jedną nazwę pospolitą używaną w certyfikatach wystawionych przez zaufany urząd certyfikacji do serwerów dostępu do sieci bezprzewodowej. Na przykład dodaj element `mywirelessserver.contoso.com` lub `mywirelessserver`. W przypadku wprowadzania tych informacji można pominąć dynamiczne okno dialogowe zaufania pokazywane na urządzeniach użytkowników nawiązujących połączenie z siecią Wi-Fi.
    - **Certyfikat główny weryfikacji serwera**: wybierz istniejący profil zaufanego certyfikatu głównego. Ten certyfikat pozwala klientowi ufać certyfikatowi serwera dostępu do sieci bezprzewodowej.

    - **Uwierzytelnianie klienta**: wybierz **metodę uwierzytelniania**. Dostępne opcje:

      - **Poświadczenie pochodne**: Użyj certyfikatu pochodzącego z karty inteligentnej użytkownika. Jeśli nie skonfigurowano wystawcy poświadczeń pochodnych, usługa Intune wyświetli monit o dodanie go. Aby uzyskać więcej informacji, zobacz [Korzystanie z poświadczeń pochodnych w usłudze Microsoft Intune](../protect/derived-credentials.md).

      - **Nazwa użytkownika i hasło**: monituj użytkownika o nazwę użytkownika i hasło w celu uwierzytelnienia połączenia. Wprowadź też następujące ustawienia:
        - **Metoda bez protokołu EAP (tożsamość wewnętrzna)** : wybierz sposób uwierzytelniania połączenia. Pamiętaj, aby wybrać ten sam protokół, który został skonfigurowany w sieci Wi-Fi.

          Dostępne opcje: **Hasło nieszyfrowane (PAP)** , **Protokół uwierzytelniania typu Challenge Handshake (CHAP)** , **Microsoft CHAP (MS-CHAP)** i **Microsoft CHAP wersja 2 (MS-CHAP v2)**

      - **Certyfikaty**: wybierz profil certyfikatu klienta protokołu SCEP lub PKCS, który również został wdrożony w urządzeniu. Ten certyfikat to tożsamość przesyłana przez urządzenie do serwera w celu uwierzytelnienia połączenia.

      - **Prywatność tożsamości (tożsamość zewnętrzna)** : wprowadź tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość, taką jak `anonymous`. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.

  - **LEAP**

  - **PEAP**: Wprowadź też następujące ustawienia:

    - **Zaufanie serwera** - **Nazwy serwerów certyfikatów**: **dodaj** co najmniej jedną nazwę pospolitą używaną w certyfikatach wystawionych przez zaufany urząd certyfikacji do serwerów dostępu do sieci bezprzewodowej. Na przykład dodaj element `mywirelessserver.contoso.com` lub `mywirelessserver`. W przypadku wprowadzania tych informacji można pominąć dynamiczne okno dialogowe zaufania pokazywane na urządzeniach użytkowników nawiązujących połączenie z siecią Wi-Fi.
    - **Certyfikat główny weryfikacji serwera**: wybierz istniejący profil zaufanego certyfikatu głównego. Ten certyfikat pozwala klientowi ufać certyfikatowi serwera dostępu do sieci bezprzewodowej.

    - **Uwierzytelnianie klienta**: wybierz **metodę uwierzytelniania**. Dostępne opcje:

      - **Poświadczenie pochodne**: Użyj certyfikatu pochodzącego z karty inteligentnej użytkownika. Jeśli nie skonfigurowano wystawcy poświadczeń pochodnych, usługa Intune wyświetli monit o dodanie go. Aby uzyskać więcej informacji, zobacz [Korzystanie z poświadczeń pochodnych w usłudze Microsoft Intune](../protect/derived-credentials.md).

      - **Nazwa użytkownika i hasło**: monituj użytkownika o nazwę użytkownika i hasło w celu uwierzytelnienia połączenia. 

      - **Certyfikaty**: wybierz profil certyfikatu klienta protokołu SCEP lub PKCS, który również został wdrożony w urządzeniu. Ten certyfikat to tożsamość przesyłana przez urządzenie do serwera w celu uwierzytelnienia połączenia.

      - **Prywatność tożsamości (tożsamość zewnętrzna)** : wprowadź tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość, taką jak `anonymous`. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.

- **Ustawienia serwera proxy**: Dostępne opcje:
  - **Brak**: nie są konfigurowane żadne ustawienia serwera proxy.
  - **Ręczne**: wprowadź **adres serwera proxy** jako adres IP oraz jego **numer portu**.
  - **Automatyczne**: Użyj pliku do skonfigurowania serwera proxy. Wprowadź **adres URL serwera proxy** (np. `http://proxy.contoso.com`), który zawiera plik konfiguracji.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje żadnych czynności. Następnie [przypisz ten profil](device-profile-assign.md) i [monitoruj jego stan](device-profile-monitor.md).

Konfigurowanie ustawień sieci Wi-Fi na urządzeniach z systemami [Android](wi-fi-settings-android.md), [Android Enterprise](wi-fi-settings-android-enterprise.md), [macOS](wi-fi-settings-macos.md) i [Windows 10](wi-fi-settings-windows.md).
