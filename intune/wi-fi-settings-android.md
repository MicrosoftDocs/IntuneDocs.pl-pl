---
title: "Ustawienia sieci Wi-Fi dla urządzeń z systemem Android w usłudze Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: poznaj ustawienia usługi Intune, których można użyć do konfigurowania połączeń Wi-Fi na urządzeniach z systemem Android."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 103e17a4-2993-4359-b340-73e2acf4cf7d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 0dd0b8c4e4cf6733c20282817cba99d8379ef24e
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="wi-fi-settings-for-android-devices-in-microsoft-intune"></a>Ustawienia sieci Wi-Fi dla urządzeń z systemem Android w usłudze Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Ustawienia sieci Wi-Fi dla profilu podstawowego i firmowego

- **Nazwa sieci** — wprowadź nazwę połączenia sieci Wi-Fi. Jest to nazwa, którą użytkownicy zobaczą podczas przeglądania listy dostępnych połączeń na swoich urządzeniach.
- **Identyfikator SSID** — identyfikator zestawu usług. Jest to prawdziwa nazwa sieci bezprzewodowej, z którą będą łączyć się urządzenia. Jednak przy wyborze połączenia użytkownicy widzą tylko nazwę sieciową utworzoną wcześniej.
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
|**Nazwy serwera certyfikatów**|Określ jedną lub więcej nazw pospolitych używanych w certyfikatach wystawionych przez zaufany urząd certyfikacji (CA). Jeśli te informacje zostaną podane, można pominąć dynamiczne okno dialogowe zaufania wyświetlane na urządzeniach użytkowników końcowych próbujących nawiązać połączenie z siecią Wi-Fi.|Jako typ protokołu EAP wybrano wartość **EAP-TLS** lub **EAP-TTLS**|
|**Certyfikat główny weryfikacji serwera**|Wybierz profil zaufanych certyfikatów głównych używany do uwierzytelniania połączenia. |Jako typ protokołu EAP wybrano wartość **EAP-TLS**, **EAP-TTLS** lub **PEAP**|
|**Prywatność tożsamości (tożsamość zewnętrzna)**|Podaj tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.|Jako typ protokołu EAP wybrano wartość **PEAP**|


#### <a name="client-authentication"></a>Uwierzytelnianie klienta


|Nazwa ustawienia|Więcej informacji|Zastosowania|
|----------|--------------|----------|
|**Certyfikat klienta na potrzeby uwierzytelniania klienta (certyfikat tożsamości)**|Wybierz profil certyfikatu SCEP lub PKCS używany do uwierzytelniania połączenia.|Jako typ protokołu EAP wybrano wartość **EAP-TLS**|
|**Metoda uwierzytelniania**|Wybierz metodę uwierzytelniania dla połączenia:<br>- **Certyfikaty**, aby wybrać certyfikat klienta dla protokołu SCEP lub PKCS, który jest certyfikatem tożsamości przesłanym do serwera.<br><br>- **Nazwa użytkownika i hasło**, aby określić inną metodę uwierzytelniania. <br><br>W przypadku wybrania opcji **Nazwa użytkownika i hasło** należy skonfigurować ustawienia:<br><br>-  **Metoda inna niż EAP (tożsamość wewnętrzna)**, a następnie wybrać sposób uwierzytelniania połączenia:<br>- **Brak**<br>- **Hasło nieszyfrowane (PAP)**<br>- **Protokół uwierzytelniania typu Challenge Handshake (CHAP)**<br>- **Microsoft CHAP (MS-CHAP)**<br>- **Microsoft CHAP wersja 2 (MS-CHAP v2)**<br>Dostępne opcje zależą od wybranego typu protokołu EAP.<br><br>**i**<br><br>- **Prywatność tożsamości (tożsamość zewnętrzna)** — podaj tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.|Jako typ protokołu EAP wybrano wartość **EAP-TTLS** lub **PEAP**|

