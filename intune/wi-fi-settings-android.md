---
title: Konfigurowanie ustawień sieci Wi-Fi dla urządzeń z systemem Android w usłudze Microsoft Intune
titleSuffix: ''
description: Informacje na temat konfiguracji ustawień sieci Wi-Fi w usłudze Intune dla urządzeń z systemem Android i programem Android for Work.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ee82da997a794bb2f65929a6fd9e0de0cc776a6e
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
ms.locfileid: "31831065"
---
# <a name="configure-wi-fi-settings-in-microsoft-intune-for-devices-running-android-and-android-for-work"></a>Konfigurowanie ustawień sieci Wi-Fi w usłudze Microsoft Intune dla urządzeń z systemem Android i programem Android for Work  

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W tym artykule opisano ustawienia sieci Wi-Fi, które można skonfigurować w usłudze Microsoft Intune dla urządzeń z systemem Android i programem Android for Work.

## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Ustawienia sieci Wi-Fi dla profilu podstawowego i firmowego

W przypadku urządzeń z systemem Android i programem Android for Work dostępne są następujące ustawienia sieci Wi-Fi:

- **Nazwa sieci** — wprowadź nazwę połączenia sieci Wi-Fi. Jest to nazwa, którą użytkownicy zobaczą podczas przeglądania listy dostępnych połączeń na swoich urządzeniach.
- **Identyfikator SSID** — identyfikator zestawu usług. Jest to prawdziwa nazwa sieci bezprzewodowej, z którą będą łączyć się urządzenia. Jednak przy wyborze połączenia użytkownicy widzą tylko nazwę sieci utworzoną wcześniej.
- **Połącz automatycznie** — sprawia, że urządzenie łączy się zawsze, gdy znajdzie się w zasięgu tej sieci.
- **Ukryta sieć** — uniemożliwia wyświetlanie tej sieci na liście dostępnych sieci na urządzeniu.


## <a name="wi-fi-settings-for-enterprise-profiles-only"></a>Ustawienia sieci Wi-Fi tylko dla profilów firmowych

- **Typ protokołu EAP** — wybierz typ protokołu uwierzytelniania rozszerzonego (EAP, Extensible Authentication Protocol) używany do uwierzytelniania zabezpieczonych połączeń bezprzewodowych:
    - **EAP-TLS**
    - **EAP-TTLS**
    - **PEAP**

### <a name="further-options-when-you-choose-an-eap-type"></a>Dalsze opcje w przypadku wybrania typu protokołu EAP

#### <a name="server-trust"></a>Zaufanie serwera



|Nazwa ustawienia|Więcej informacji|Zastosowania|
|-------------|---------------|-----------|
|**Nazwy serwera certyfikatów**|Określ jedną lub więcej nazw pospolitych używanych w certyfikatach wystawionych przez zaufany urząd certyfikacji (CA). Jeśli te informacje zostaną podane, można pominąć dynamiczne okno dialogowe zaufania wyświetlane na urządzeniach użytkowników próbujących nawiązać połączenie z siecią Wi-Fi.|Jako typ protokołu EAP wybrano wartość **EAP-TLS** lub **EAP-TTLS**|
|**Certyfikat główny weryfikacji serwera**|Wybierz profil zaufanych certyfikatów głównych używany do uwierzytelniania połączenia. |Jako typ protokołu EAP wybrano wartość **EAP-TLS**, **EAP-TTLS** lub **PEAP**|
|**Prywatność tożsamości (tożsamość zewnętrzna)**|Podaj tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.|Jako typ protokołu EAP wybrano wartość **PEAP**|


#### <a name="client-authentication"></a>Uwierzytelnianie klienta


|                                     Nazwa ustawienia                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       Więcej informacji                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                            Zastosowania                            |
|--------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------|
| <strong>Certyfikat klienta na potrzeby uwierzytelniania klienta (certyfikat tożsamości)</strong> |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       Wybierz profil certyfikatu SCEP lub PKCS używany do uwierzytelniania połączenia.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |              Jako typ protokołu EAP wybrano wartość <strong>EAP-TLS</strong>              |
|                        <strong>Metoda uwierzytelniania</strong>                        | Wybierz metodę uwierzytelniania dla połączenia:<br>- <strong>Certyfikaty</strong>, aby wybrać certyfikat klienta dla protokołu SCEP lub PKCS, który jest certyfikatem tożsamości przesłanym do serwera.<br><br>- <strong>Nazwa użytkownika i hasło</strong>, aby określić inną metodę uwierzytelniania. <br><br>W przypadku wybrania opcji <strong>Nazwa użytkownika i hasło</strong> należy skonfigurować ustawienia:<br><br>-  <strong>Metoda inna niż EAP (tożsamość wewnętrzna)</strong>, a następnie wybrać sposób uwierzytelniania połączenia:<br>- <strong>Brak</strong><br>- <strong>Hasło nieszyfrowane (PAP)</strong><br>- <strong>Protokół uwierzytelniania typu Challenge Handshake (CHAP)</strong><br>- <strong>Microsoft CHAP (MS-CHAP)</strong><br>- <strong>Microsoft CHAP wersja 2 (MS-CHAP v2)</strong><br>Dostępne opcje zależą od wybranego typu protokołu EAP.<br><br><strong>i</strong><br><br>- <strong>Prywatność tożsamości (tożsamość zewnętrzna)</strong> — podaj tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu. | Jako typ protokołu EAP wybrano wartość <strong>EAP-TTLS</strong> lub <strong>PEAP</strong> |

