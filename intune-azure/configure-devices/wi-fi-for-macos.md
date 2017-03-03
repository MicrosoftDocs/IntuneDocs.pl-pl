---
title: "Ustawienia sieci Wi-Fi dla urządzeń z systemem macOS w usłudze Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące ustawień usługi Intune, których można użyć do konfigurowania połączeń sieci Wi-Fi na urządzeniach z systemem macOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 322a38d5-21f5-48ee-bc59-0a4f9da78d38
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: c287ce2c528610bbbb9c0df204eed9f492a32cc2
ms.lasthandoff: 02/18/2017


---

# <a name="wi-fi-settings-for-macos-devices-in-microsoft-intune"></a>Ustawienia sieci Wi-Fi dla urządzeń z systemem macOS w usłudze Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Ustawienia sieci Wi-Fi dla profilu podstawowego i firmowego

- **Nazwa sieci** — wprowadź nazwę połączenia sieci Wi-Fi. Jest to nazwa, którą użytkownicy zobaczą podczas przeglądania listy dostępnych połączeń na swoich urządzeniach.
- **Identyfikator SSID** — identyfikator zestawu usług. Jest to prawdziwa nazwa sieci bezprzewodowej, z którą będą łączyć się urządzenia. Jednak przy wyborze połączenia użytkownicy widzą tylko nazwę sieciową utworzoną wcześniej.
- **Połącz automatycznie** — sprawia, że urządzenie łączy się zawsze, gdy znajdzie się w zasięgu tej sieci.
- **Ukryta sieć** — uniemożliwia wyświetlanie tej sieci na liście dostępnych sieci na urządzeniu.
- **Ustawienia serwera proxy** — wybierz pozycję:
    - **Brak** — nie zostaną skonfigurowane żadne ustawienia serwera proxy.
    - **Ręczne** — uzupełnij pole **Adres serwera proxy** (jako adres IP) oraz wprowadź skojarzony z nim **numer portu**.
    - **Automatyczne** — użyj pliku do konfiguracji serwera proxy. W polu **Adres URL serwera proxy** wprowadź adres URL (na przykład **http://proxy.contoso.com**), który zawiera plik konfiguracji.

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
|**Nazwy serwera certyfikatów**|Określ jedną lub więcej nazw pospolitych używanych w certyfikatach wystawionych przez zaufany urząd certyfikacji (CA). Jeśli te informacje zostaną podane, można pominąć dynamiczne okno dialogowe zaufania wyświetlane na urządzeniach użytkowników końcowych próbujących nawiązać połączenie z siecią Wi-Fi.|Jako typ protokołu EAP wybrano wartość **EAP-TLS**, **EAP-TTLS** lub **PEAP**.|
|**Certyfikat główny weryfikacji serwera**|Wybierz profil zaufanych certyfikatów głównych używany do uwierzytelniania połączenia. |Jako typ protokołu EAP wybrano wartość **EAP-TLS**, **EAP-TTLS** lub **PEAP**|
|**Prywatność tożsamości (tożsamość zewnętrzna)**|Podaj tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.|Jako typ protokołu EAP wybrano wartość **PEAP**|


#### <a name="client-authentication"></a>Uwierzytelnianie klienta


|Nazwa ustawienia|Więcej informacji|Zastosowania|
|--------------|-------------|----------|
|**Certyfikat klienta na potrzeby uwierzytelniania klienta (certyfikat tożsamości)**|Wybierz profil certyfikatu SCEP lub PKCS używany do uwierzytelniania połączenia.|Jako typ protokołu EAP wybrano wartość **EAP-TLS**|
|**Metoda uwierzytelniania**|Wybierz metodę uwierzytelniania dla połączenia:<br>- **Certyfikaty**, aby wybrać certyfikat klienta dla protokołu SCEP lub PKCS, który jest certyfikatem tożsamości przesłanym do serwera.<br><br>- **Nazwa użytkownika i hasło**, aby określić inną metodę uwierzytelniania. <br><br>W przypadku wybrania opcji **Nazwa użytkownika i hasło** należy skonfigurować ustawienia:<br><br>-  **Metoda inna niż EAP (tożsamość wewnętrzna)**, a następnie wybrać sposób uwierzytelniania połączenia:<br>- **Brak**<br>- **Hasło nieszyfrowane (PAP)**<br>- **Protokół uwierzytelniania typu Challenge Handshake (CHAP)**<br>- **Microsoft CHAP (MS-CHAP)**<br>- **Microsoft CHAP wersja 2 (MS-CHAP v2)**<br>Dostępne opcje zależą od wybranego typu protokołu EAP.<br><br>**i**<br><br>- **Prywatność tożsamości (tożsamość zewnętrzna)** — podaj tekst, który będzie wysyłany w odpowiedzi na żądanie podania tożsamości zgłaszane przez protokół EAP. Ten tekst może mieć dowolną wartość. Podczas uwierzytelniania na początku wysyłana jest ta tożsamość anonimowa, a po niej — tożsamość rzeczywista, która jest wysyłana w bezpiecznym tunelu.|Jako typ protokołu EAP wybrano wartość **EAP-TTLS** lub **PEAP**|

