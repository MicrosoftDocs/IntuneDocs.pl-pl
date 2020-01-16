---
title: Konfigurowanie ustawień sieci VPN na urządzeniach z systemem Windows Phone 8.1 w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodawanie lub Tworzenie profilu konfiguracji sieci VPN przy użyciu ustawień konfiguracji wirtualnej sieci prywatnej (VPN), w tym szczegółów połączenia oraz ustawień serwera proxy w celu uwzględnienia adresu IP lub nazwy FQDN i portu TCP w Microsoft Intune na urządzeniach z systemem Windows Phone 8,1.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/19/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 70f33fe132eb6c3dbf91c5dc313369d75f4f3e24
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207030"
---
# <a name="add-vpn-settings-on-windows-phone-81-devices-in-microsoft-intune"></a>Dodawanie ustawień sieci VPN na urządzeniach z systemem Windows Phone 8.1 w usłudze Microsoft Intune



Ten artykuł zawiera informacje dotyczące ustawień usługi Intune, których można użyć do konfigurowania połączeń sieci VPN na urządzeniach z systemem Windows Phone 8.1. 

W zależności od wybranych ustawień niektórych wartości z poniższej listy nie będzie można skonfigurować.

>[!IMPORTANT]
>Profile sieci VPN Windows Phone 8,1 są również stosowane do urządzeń z systemem Windows 10.

## <a name="base-vpn-settings"></a>Podstawowe ustawienia sieci VPN

- **Zastosuj wszystkie ustawienia tylko do systemu Windows Phone 8.1** — to ustawienie można skonfigurować w portalu klasycznym usługi Intune. W centrum administracyjnym programu Microsoft Endpoint Manager nie można zmienić tego ustawienia. Jeśli jest ono ustawione na wartość **Skonfigurowane**, wszystkie ustawienia zostaną zastosowane tylko do urządzeń z systemem Windows Phone 8.1. Jeśli jest ono ustawione na wartość **Nieskonfigurowane**, te ustawienia zostaną również zastosowane do urządzeń z systemem Windows 10 Mobile.
- **Nazwa połączenia**: Wprowadź nazwę dla połączenia. Użytkownicy widzą tę nazwę, przeglądając na urządzeniu listę dostępnych połączeń sieci VPN.
- **Metoda uwierzytelniania**: Umożliwia wybór sposobu uwierzytelniania urządzeń na serwerze sieci VPN:
  - **Certyfikaty**: W obszarze **Certyfikat uwierzytelniania** można wybrać profil certyfikatu protokołu SCEP lub PKCS, który został wcześniej utworzony do uwierzytelniania połączenia. Aby uzyskać więcej informacji o profilach certyfikatów, zobacz temat dotyczący [konfigurowania certyfikatów](../protect/certificates-configure.md).
  - **Nazwa użytkownika i hasło**: Użytkownicy końcowi muszą podać nazwę użytkownika i hasło, aby zalogować się do serwera sieci VPN.
- **Serwery**: Dodaj jeden lub więcej serwerów sieci VPN, z którymi urządzenia się łączą.
  - **Dodaj**: Otwiera blok **Dodaj wiersz**, w którym można określić następujące informacje:
    - **Opis**: Umożliwia określenie opisowej nazwy serwera, na przykład **Serwer sieci VPN firmy Contoso**.
    - **Adres IP lub nazwa FQDN**: Podaj adres IP lub w pełni kwalifikowaną nazwę domeny (FQDN) serwera sieci VPN, z którym mają się łączyć urządzenia. Przykłady: **192.168.1.1**, **vpn.contoso.com**.
    - **Serwer domyślny**: Określa ten serwer jako serwer domyślny używany przez urządzenia do nawiązania połączenia. Upewnij się, że tylko jeden serwer jest ustawiony jako domyślny.
  - **Importuj**: Przejdź do pliku zawierającego rozdzielaną przecinkami listę serwerów w formacie: opis, adres IP lub nazwa FQDN, serwer domyślny. Wybierz pozycję **OK**, aby zaimportować te serwery do listy **Serwery**.
  - **Eksportuj**: Eksportuje listę serwerów do pliku CSV (plik wartości rozdzielanych przecinkami).

- **Pomijaj sieć VPN w firmowej sieci Wi-Fi**: Włącz tę opcję, aby określić, że połączenia z siecią VPN nie będą używane, jeśli urządzenie jest połączone z firmową siecią Wi-Fi.
- **Pomijaj sieć VPN w domowej sieci Wi-Fi**: Włącz tę opcję, aby określić, że połączenie z siecią VPN nie będzie używane, jeśli urządzenie jest połączone z domową siecią Wi-Fi.

- **Typ połączenia**: Umożliwia wybór typu połączenia sieci VPN z poniższej listy dostawców:
  - **Check Point Capsule VPN**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**

- **Grupa lub domena logowania** (tylko SonicWall Mobile Connect): Określ nazwę grupy lub domeny logowania, z którą chcesz nawiązać połączenie.
- **Rola** (tylko Pulse Secure): Określ nazwę roli użytkownika, która ma dostęp do tego połączenia. Rola użytkownika definiuje ustawienia osobiste i opcje oraz włączenie lub wyłączenie określonych funkcji dostępu.
- **Obszar** (tylko Pulse Secure): Określ nazwę obszaru uwierzytelniania, który ma być używany. Obszar uwierzytelniania to grupa zasobów uwierzytelniania używana przez typ połączenia Pulse Secure.

- **Lista wyszukiwania sufiksów DNS**: **Dodaj** co najmniej jeden sufiks DNS. Wszystkie wprowadzone sufiksy DNS są wyszukiwane podczas łączenia z witryną internetową za pomocą nazwy skróconej. Na przykład określ sufiksy usługi DNS **domena1.contoso.com** i **domena2.contoso.com**, a następnie otwórz adres URL `http://mywebsite`, aby przeszukać adresy URL `http://mywebsite.domain1.contoso.com` i `http://mywebsite.domain2.contoso.com`.

- **Niestandardowy kod XML**: Podaj niestandardowe polecenia XML do konfiguracji połączenia z siecią VPN.

  **Przykład rozwiązania Pulse Secure**:

  ```xml
  <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
  ```

  **Przykład rozwiązania CheckPoint Mobile VPN**:

  ```xml
  <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
  ```

  **Przykład rozwiązania SonicWall Mobile Connect**:

  ```xml
  <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
  ```

  **Przykład rozwiązania F5 Edge Client**:

  ```xml
  <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
  ```

  Więcej informacji na temat pisania niestandardowych poleceń XML zawiera dokumentacja sieci VPN dostarczana przez producenta.

- **Podziel tunelowanie**: Wybierz ustawienie **Włącz** lub **Wyłącz**. Ta opcja pozwala urządzeniom decydować, z którego połączenia skorzystać, w zależności od ruchu. Na przykład użytkownik w hotelu używa połączenia sieci VPN, aby uzyskać dostęp do plików roboczych, ale podczas zwykłego przeglądania Internetu skorzysta ze standardowej sieci hotelowej.

## <a name="proxy-settings"></a>Ustawienia serwera proxy

- **Automatycznie wykrywaj ustawienia proxy**: Jeśli serwer sieci VPN wymaga połączenia przez serwer proxy, określ, czy chcesz, aby urządzenia automatycznie wykrywały ustawienia połączenia.
- **Skrypt konfiguracji automatycznej**: Użyj pliku do skonfigurowania serwera proxy. Podaj **adres URL serwera proxy**, np. `http://proxy.contoso.com`, który zawiera plik konfiguracji.
- **Użyj serwera proxy**: Włącz tę opcję, jeśli chcesz ręcznie wprowadzić ustawienia serwera proxy.
  - **Adres**: Wprowadź adres serwera proxy (jako adres IP).
  - **Numer portu**: Wprowadź numer portu skojarzony z serwerem proxy.
- **Pomijaj serwer proxy dla adresów lokalnych**: Zaznacz tę opcję, jeśli serwer sieci VPN wymaga połączenia przez serwer proxy, ale nie chcesz, aby serwer proxy był używany dla adresów lokalnych.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. W dalszej części [przypiszesz profil](device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).

Skonfiguruj ustawienia sieci VPN na [Android](vpn-settings-android.md), [Android Enterprise](vpn-settings-android-enterprise.md), [macOS](vpn-settings-macos.md)i [urządzeń z systemem Windows 10](vpn-settings-windows-10.md).
