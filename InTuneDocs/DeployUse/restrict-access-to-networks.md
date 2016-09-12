---
title: "Ograniczanie dostępu do sieci na platformie Cisco ISE | Microsoft Intune"
description: "Użyj platformy Cisco ISE razem z usługą Intune, aby urządzenia musiały być zarejestrowane w usłudze Intune i zgodne z zasadami, zanim będą mogły uzyskać dostęp do sieci Wi-Fi i VPN kontrolowanych przez platformę Cisco ISE."
keywords: 
author: nbigman
manager: angrobe
ms.date: 06/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5631bac3-921d-438e-a320-d9061d88726c
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 40194f4359d0889806e080a4855b8e1934b667f9
ms.openlocfilehash: 9d6b7198e3c2e30898a8ec83785c7f3b777eda5f


---

# Korzystanie z platformy Cisco ISE razem z usługą Intune
Integracja usługi Intune z platformą Cisco ISE (Identity Services Engine) umożliwia tworzenie zasad sieciowych w środowisku platformy ISE przy użyciu rejestracji urządzeń i stanu ich zgodności w usłudze Intune. Te zasady mogą służyć do zagwarantowania, że dostęp do sieci firmowej jest ograniczony do urządzeń, które są zarządzane przez usługę Intune i zgodne z zasadami usługi Intune.

## Kroki konfiguracji

Aby włączyć tę integrację, nie trzeba wykonywać żadnej konfiguracji w dzierżawie usługi Intune. Będzie konieczne udostępnienie uprawnień serwerowi platformy Cisco ISE, aby miał dostęp do dzierżawy usługi Intune. Gdy zostanie to zrobione, pozostała konfiguracja zostanie wykonana na serwerze Cisco ISE. Ten artykuł zawiera instrukcje dotyczące zapewniania serwerowi platformy ISE uprawnień dostępu do danej dzierżawy usługi Intune.

### Krok 1. Zarządzanie certyfikatami
1. W konsoli usługi Azure Active Directory (Azure AD) wyeksportuj certyfikat.

#### Internet Explorer 11


   a. Uruchom program Internet Explorer jako administrator i zaloguj się do konsoli usługi Azure AD.

   b. Wybierz ikonę blokady na pasku adresu i wybierz polecenie **Wyświetl certyfikaty**.

   c. Na karcie **Szczegóły** właściwości certyfikatu wybierz pozycję **Kopiuj do pliku**.

   d. Na stronie powitalnej **Kreatora eksportu certyfikatów** wybierz polecenie **Dalej**.

   e. Na stronie **Format pliku eksportu** pozostaw domyślną wartość domyślną **Certyfikat X.509 szyfrowany binarnie algorytmem DER (.CER)**, a następnie wybierz polecenie **Dalej**.  

   f. Na stronie **Plik do eksportu** wybierz pozycję **Przeglądaj**, wskaż lokalizację, w której ma zostać zapisany plik, a następnie podaj nazwę pliku. Chociaż wydaje się, że wybierasz plik do wyeksportowania, w rzeczywistości nadajesz nazwę plikowi, w którym zostanie zapisany wyeksportowany certyfikat. Wybierz pozycje **Dalej** &gt; **Zakończ**.

#### Safari

 a. Zaloguj się do konsoli usługi Azure AD.

b. Wybierz ikonę blokady &gt; **Więcej informacji o**.

   c. Wybierz pozycje **Wyświetl certyfikat** &gt; **Szczegóły**.

   d. Wybierz certyfikat, a następnie wybierz pozycję **Eksportuj**.  

> [!IMPORTANT]
>
> Sprawdź datę wygaśnięcia certyfikatu, ponieważ po jej upłynięciu trzeba będzie wyeksportować i zaimportować nowy certyfikat.


2. Z poziomu konsoli ISE zaimportuj certyfikat usługi Intune (wyeksportowany plik) do magazynu **zaufanych certyfikatów**.


### Uzyskiwanie certyfikatu z podpisem własnym ze środowiska ISE 

1.  W konsoli ISE przejdź do pozycji **Administracja** > **Certyfikaty** > **Certyfikaty systemowe** > **Generuj certyfikat z podpisem własnym**.  
2.       Wyeksportuj certyfikat z podpisem własnym.
3. W edytorze tekstu edytuj wyeksportowany certyfikat:
 - Usuń ** -----BEGIN CERTIFICATE-----**
 - Usuń ** -----END CERTIFICATE-----**
 
Upewnij się, że cały tekst jest jednym wierszu


### Krok 2. Tworzenie aplikacji dla środowiska ISE w dzierżawie usługi Azure AD
1. W konsoli usługi Azure AD wybierz pozycję **Aplikacje** > **Dodawanie aplikacji** > **Dodaj aplikację opracowywaną przez moją organizację**.
2. Określ nazwę i adres URL aplikacji. Może to być adres URL witryny internetowej firmy.
3. Pobierz manifest aplikacji (plik JSON).
4. Edytuj plik JSON manifestu. W ustawieniu o nazwie **keyCredentials** podaj edytowany tekst certyfikatu z kroku 1 jako wartość ustawienia.
5. Zapisz plik bez zmieniania jego nazwy.
6. Udostępnij aplikacji uprawnienia do programu Microsoft Graph i interfejsu API usługi Microsoft Intune.

 a. W przypadku programu Microsoft Graph wybierz następujące uprawnienia:
    - **Uprawnienia aplikacji**: Odczytuj dane katalogu
    - **Delegowane uprawnienia**:
        - Uzyskuj dostęp do danych użytkowników w dowolnym czasie
        - Loguj użytkowników

 b. W przypadku interfejsu API usługi Microsoft Intune w obszarze **Uprawnienia aplikacji** wybierz pozycję **Pobieraj stan i zgodność urządzenia z usługi Intune**.

7. Wybierz pozycję **Wyświetl punkty końcowe** i skopiuj następujące wartości do użycia podczas konfigurowania ustawień platformy ISE:

|Wartość w portalu usługi Azure AD|Odpowiednie pole w portalu platformy ISE|
|-------------------|---------------------------------|
|Punkt końcowy interfejsu API Microsoft Azure AD Graph|Auto Discovery URL (Adres URL autowykrywania)|
|Punkt końcowy tokenu OAuth 2.0|Token Issuing URL (Adres URL wystawiania tokenów)|
|Aktualizowanie kodu przy użyciu identyfikatora klienta|Identyfikator klienta|


### Krok 3. Konfigurowanie ustawień platformy ISE
W konsoli administracyjnej platformy ISE podaj wartości tych ustawień:
  - **Server Type (Typ serwera)**: Mobile Device Manager
  - **Authentication type (Typ uwierzytelniania)**: OAuth – Client Credentials (OAuth — poświadczenia klienta)
  - **Auto Discovery (Autowykrywanie)**: Yes (Tak)
  - **Auto Discover URL (Adres URL autowykrywania)**: *wprowadź wartość z kroku 1*
  - **Client ID (Identyfikator klienta)**: *wprowadź wartość z kroku 1*
  - **Token issuing URL (Adres URL wystawiania tokenów)**: *wprowadź wartość z kroku 1*



## Informacje współużytkowane przez dzierżawę usługi Intune i serwer Cisco ISE
Ta tabela zawiera informacje współużytkowane przez dzierżawę usługi Intune i serwer Cisco ISE dla urządzeń zarządzanych przez usługę Intune.

|Właściwość|  Opis|
|---------------|------------------------------------------------------------|
|complianceState|Wartość true lub false (ciąg) wskazująca, czy urządzenie jest zgodne, czy niezgodne.|
|isManaged|Wartość true lub false wskazująca, czy klient jest zarządzany przez usługę Intune, czy nie.|
|macAddress|Adres MAC urządzenia.|
|serialNumber|Numer seryjny urządzenia. Dotyczy tylko urządzeń z systemem iOS.|
|imei|Numer IMEI (15 cyfr dziesiętnych: 14 cyfr i cyfra kontrolna) lub numer IMEISV (16 cyfr) zawiera informacje o pochodzeniu, modelu i numerze seryjnym urządzenia. Struktura tych numerów jest określona w specyfikacji 3GPP TS 23.003. Dotyczy to tylko urządzeń z kartami SIM.|
|udid|Unikatowy identyfikator urządzenia będący sekwencją 40 liter i cyfr. Jest on specyficzny dla urządzeń z systemem iOS.|
|meid|Identyfikator sprzętu przenośnego będący globalnie unikatowym numerem identyfikującym fizyczny element sprzętu przenośnego stacji sieci CDMA. Format liczbowy jest zdefiniowany w raporcie 3GPP2 S. R0048. W praktyce może być uznawany za numer IMEI, ale z cyframi szesnastkowymi. Numer MEID ma długość 56 bitów (14 cyfr szesnastkowych). Składa się z trzech pól, w tym 8-bitowego kodu regionu (RR), 24-bitowego kodu producenta i 24-bitowego numeru seryjnego przypisanego przez producenta.|
|osVersion|Wersja systemu operacyjnego urządzenia.
|model|Model urządzenia.
|manufacturer|Producent urządzenia.
|azureDeviceId|Identyfikator urządzenia po dołączeniu go w miejscu pracy za pomocą usługi Azure AD. Pusty identyfikator GUID dla urządzeń, które nie są dołączone.|
|lastContactTimeUtc|Data i godzina ostatniego zaewidencjonowania urządzenia w usłudze zarządzania usługi Intune.


## Środowisko użytkownika

Gdy użytkownik próbuje uzyskać dostęp do zasobów przy użyciu niezarejestrowanego urządzenia, otrzymuje monit o rejestrację podobny do pokazanego poniżej:

![Przykład monitu o rejestrację](../media/cisco-ise-user-iphone.png)

Jeśli użytkownik zdecyduje się na rejestrację, zostanie przekierowany do procesu rejestracji w usłudze Intune. Obsługa rejestracji użytkownika w usłudze Intune zostało opisane w tych tematach:

- [Rejestrowanie urządzenia z systemem Android w usłudze Intune](/intune/enduser/enroll-your-device-in-Intune-android)</br>
- [Rejestrowanie urządzenia z systemem iOS w usłudze Intune](/intune/enduser/enroll-your-device-in-intune-ios)</br>
- [Rejestrowanie urządzenia z systemem Mac OS X w usłudze Intune](/intune/enduser/enroll-your-device-in-intune-mac-os-x)</br>
- [Rejestrowanie urządzenia z systemem Windows w usłudze Intune](/intune/enduser/enroll-your-device-in-intune-windows)</br>

Istnieje również [dostępny do pobrania zestaw instrukcji dotyczących rejestracji](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a), za pomocą którego można utworzyć dostosowane wskazówki na potrzeby środowiska użytkowników.


### Zobacz także

[Cisco Identity Services Engine Administrator Guide, wersja 2.1](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html#task_820C9C2A1A6647E995CA5AAB01E1CDEF)



<!--HONumber=Sep16_HO1-->


