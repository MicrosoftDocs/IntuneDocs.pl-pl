---
title: Ustawienia sieci Wi-Fi w usłudze Microsoft Intune dla urządzeń z systemem macOS
titleSuffix: ''
description: Informacje dotyczące ustawień usługi Intune, których można użyć do konfigurowania połączeń Wi-Fi na urządzeniach z systemem macOS.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6f0feb00949375cf65428d061af81813cfcd5249
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="wi-fi-settings-for-macos-devices-in-microsoft-intune"></a>Ustawienia sieci Wi-Fi dla urządzeń z systemem macOS w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W tym artykule opisano ustawienia sieci Wi-Fi, które można skonfigurować w usłudze Microsoft Intune dla urządzeń z systemem macOS.

## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Ustawienia sieci Wi-Fi dla profilu podstawowego i firmowego

- **Nazwa sieci** — wprowadź nazwę połączenia sieci Wi-Fi. Jest to nazwa, którą użytkownicy zobaczą podczas przeglądania listy dostępnych połączeń na swoich urządzeniach.
- **Identyfikator SSID** — identyfikator zestawu usług. Jest to prawdziwa nazwa sieci bezprzewodowej, z którą będą łączyć się urządzenia. Jednak przy wyborze połączenia użytkownicy widzą tylko nazwę sieci utworzoną wcześniej.
- **Połącz automatycznie** — sprawia, że urządzenie łączy się zawsze, gdy znajdzie się w zasięgu tej sieci.
- **Ukryta sieć** — uniemożliwia wyświetlanie tej sieci na liście dostępnych sieci na urządzeniu.
- **Ustawienia serwera proxy** — wybierz pozycję:
    - **Brak** — nie są konfigurowane żadne ustawienia serwera proxy.
    - **Ręczne** — uzupełnij pole **Adres serwera proxy** (jako adres IP) oraz wprowadź skojarzony z nim **numer portu**.
    - **Automatyczne** — użyj pliku do konfiguracji serwera proxy. Podaj **adres URL serwera proxy**, np. **http://proxy.contoso.com**, który zawiera plik konfiguracji.

## <a name="wi-fi-settings-for-basic-profiles-only"></a>Ustawienia sieci Wi-Fi tylko dla profilów podstawowych

- **Typ zabezpieczeń** — wybierz protokół zabezpieczeń do uwierzytelniania sieci Wi-Fi:
    - **Otwórz (bez uwierzytelniania)** — tej opcji można używać tylko, jeśli sieć jest niezabezpieczona.
    - **WPA/WPA2-Personal**
    - **Szyfrowanie danych**

## <a name="wi-fi-settings-for-enterprise-profiles-only"></a>Ustawienia sieci Wi-Fi tylko dla profilów firmowych

- **Typ protokołu EAP** — wybierz typ protokołu uwierzytelniania rozszerzonego (EAP, Extensible Authentication Protocol) używany do uwierzytelniania zabezpieczonych połączeń bezprzewodowych:
    - **EAP-FAST**
    - **EAP-SIM**
    - **EAP-TLS**
    - **EAP-TTLS**
    - **LEAP**
    - **PEAP**

### <a name="further-options-when-you-choose-an-eap-type"></a>Dalsze opcje w przypadku wybrania typu protokołu EAP


|Nazwa ustawienia|Więcej informacji|Zastosowania|
|--------------|-------------|----------|
|**Ustawienia PAC (Protected Access Credential)**|Wybierz tę wartość, aby ustanowić uwierzytelniony tunel między klientem i serwerem uwierzytelniania przy użyciu uwierzytelniania PAC. Wybierz jedną z opcji:<br>- **Użyj uwierzytelniania PAC** — zostanie użyty istniejący plik PAC, jeśli jest obecny.<br>- **Użyj i inicjuj obsługę PAC** — inicjuje obsługę pliku PAC dla urządzeń.<br>- **Użyj i inicjuj obsługę PAC anonimowo** — zainicjuj obsługę pliku PAC na urządzeniach i upewnij się, że plik PAC zostanie zainicjowany bez uwierzytelniania serwera.|Jako typ protokołu EAP wybrano wartość **EAP-FAST**|

#### <a name="server-trust"></a>Zaufanie serwera


|Nazwa ustawienia|Więcej informacji|Zastosowania|
|--------------|-------------|----------|
|**Nazwy serwera certyfikatów**|Określ jedną lub więcej nazw pospolitych używanych w certyfikatach wystawionych przez zaufany urząd certyfikacji (CA). Jeśli te informacje zostaną podane, można pominąć dynamiczne okno dialogowe zaufania wyświetlane na urządzeniach użytkowników próbujących nawiązać połączenie z siecią Wi-Fi.|Jako typ protokołu EAP wybrano wartość **EAP-TLS**, **EAP-TTLS** lub **PEAP**.|
|**Certyfikat główny weryfikacji serwera**|Wybierz profil zaufanych certyfikatów głównych używany do uwierzytelniania połączenia. |Jako typ protokołu EAP wybrano wartość **EAP-TLS**, **EAP-TTLS** lub **PEAP**|
|**Prywatność tożsamości (tożsamość zewnętrzna)**|Podaj tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.|Jako typ protokołu EAP wybrano wartość **PEAP**|


#### <a name="client-authentication"></a>Uwierzytelnianie klienta


|                                     Nazwa ustawienia                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       Więcej informacji                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                            Zastosowania                            |
|--------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------|
| <strong>Certyfikat klienta na potrzeby uwierzytelniania klienta (certyfikat tożsamości)</strong> |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       Wybierz profil certyfikatu SCEP lub PKCS używany do uwierzytelniania połączenia.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |              Jako typ protokołu EAP wybrano wartość <strong>EAP-TLS</strong>              |
|                        <strong>Metoda uwierzytelniania</strong>                        | Wybierz metodę uwierzytelniania dla połączenia:<br>- <strong>Certyfikaty</strong>, aby wybrać certyfikat klienta dla protokołu SCEP lub PKCS, który jest certyfikatem tożsamości przesłanym do serwera.<br><br>- <strong>Nazwa użytkownika i hasło</strong>, aby określić inną metodę uwierzytelniania. <br><br>W przypadku wybrania opcji <strong>Nazwa użytkownika i hasło</strong> należy skonfigurować ustawienia:<br><br>-  <strong>Metoda inna niż EAP (tożsamość wewnętrzna)</strong>, a następnie wybrać sposób uwierzytelniania połączenia:<br>- <strong>Brak</strong><br>- <strong>Hasło nieszyfrowane (PAP)</strong><br>- <strong>Protokół uwierzytelniania typu Challenge Handshake (CHAP)</strong><br>- <strong>Microsoft CHAP (MS-CHAP)</strong><br>- <strong>Microsoft CHAP wersja 2 (MS-CHAP v2)</strong><br>Dostępne opcje zależą od wybranego typu protokołu EAP.<br><br><strong>i</strong><br><br>- <strong>Prywatność tożsamości (tożsamość zewnętrzna)</strong> — podaj tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu. | Jako typ protokołu EAP wybrano wartość <strong>EAP-TTLS</strong> lub <strong>PEAP</strong> |

