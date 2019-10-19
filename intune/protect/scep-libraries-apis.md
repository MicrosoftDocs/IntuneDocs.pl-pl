---
title: Interfejsy API umożliwiające dodawanie urzędów certyfikacji innych firm
titleSuffix: Microsoft Intune
description: Możesz dodać lub zintegrować rozwiązanie SCEP usługi GitHub dla urzędów certyfikacji innych firm w celu wydawania certyfikatów SCEP dla urządzeń w usłudze Microsoft Intune. To rozwiązanie obejmuje interfejsy API w językach Java i C#, które przeprowadzają walidację, przesyłają powiadomienia o powodzeniu i niepowodzeniu do usługi Intune oraz korzystają z fabryki gniazd protokołu SSL podczas komunikowania się z usługą Intune. Zobacz również omówienie czynności, które należy wykonać, aby przetestować konfigurację urzędu certyfikacji SCEP.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/06/2018
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: cadadcb8379d2de73b166d863c0b471747f5f6c7
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72504096"
---
# <a name="use-apis-to-add-third-party-cas-for-scep-to-intune"></a>Dodawanie urzędów certyfikacji innych firm dla protokołu SCEP do usługi Intune za pomocą interfejsów API

Usługa Microsoft Intune umożliwia dodawanie urzędów certyfikacji innych firm oraz korzystanie z certyfikatów wydawanych i walidowanych przez nie przy użyciu protokołu SCEP. Artykuł [Add third-party certification authority (Dodawanie urzędu certyfikacji innej firmy)](certificate-authority-add-scep-overview.md) zawiera omówienie tej funkcji oraz opisuje zadania administratora w usłudze Intune.

Również w ramach niektórych zadań dewelopera używana jest biblioteka typu open-source opublikowana przez firmę Microsoft w witrynie GitHub.com. Biblioteka zawiera interfejs API, który:

- Waliduje hasło protokołu SCEP dynamicznie generowane przez usługę Intune.
- Powiadamia usługę Intune o certyfikatach utworzonych na urządzeniach przesyłających żądania protokołu SCEP.

Za pomocą tego interfejsu API serwer SCEP innej firmy integruje się z rozwiązaniem do zarządzania protokołem SCEP usługi Itune na potrzeby zarządzania urządzeniami mobilnymi (MDM). Biblioteka odseparowuje takie aspekty jak uwierzytelnianie, lokalizacja serwera oraz interfejs API danych ODATA usługi Intune od użytkowników.

## <a name="scep-management-solution"></a>Rozwiązanie do zarządzania protokołem SCEP

![W jaki sposób protokół SCEP urzędu certyfikacji innej firmy integruje się z usługą Microsoft Intune](./media/scep-libraries-apis/scep-certificate-vendor-integration.png)

W usłudze Intune administratorzy mogą tworzyć profile protokołu SCEP, a następnie przypisywać je do urządzeń MDM. Profile protokołu SCEP zawierają między innymi następujące parametry:

- adres URL serwera SCEP,
- zaufany certyfikat główny urzędu certyfikacji,
- atrybuty certyfikatu i nie tylko.

Urządzenia zewidencjonowane w usłudze Intune są przypisywane do profilu SCEP i konfigurowane przy użyciu tych parametrów. W usłudze Intune jest tworzone dynamicznie generowane hasło wyzwania protokołu SCEP, które jest następnie przypisywane do urządzenia.

To wyzwanie zawiera:

- Dynamicznie wygenerowane hasło wyzwania
- Szczegóły dotyczące oczekiwanych parametrów w żądaniu podpisania certyfikatu (CSR), które urządzenie wysyła do serwera SCEP
- Czas wygaśnięcia wyzwania

Usługa Intune szyfruje informacje, podpisuje zaszyfrowany obiekt blob, a następnie umieszcza te dane w haśle wyzwania protokołu SCEP.

Urządzenia, które kontaktują się z serwerem SCEP w celu zażądania certyfikatu, podają to hasło wyzwania protokołu SCEP. Serwer SCEP wysyła żądanie CSR i zaszyfrowane hasło wyzwania SCEP do usługi Intune w celu wykonania walidacji.  Hasło wyzwania i żądanie CSR muszą przejść walidację, aby serwer SCEP wystawił certyfikat urządzenia. W trakcie walidacji wyzwania SCEP są sprawdzane następujące elementy:


- podpis zaszyfrowanego obiektu blob,
- data wygaśnięcia żądania,
- aktualne przypisanie profilu do urządzenia,
- zgodność właściwości certyfikatu w żądaniu CSR przesłanym przez urządzenie z oczekiwanymi wartościami.

Rozwiązanie do zarządzania protokołem SCEP zawiera również funkcję raportowania. Administrator może uzyskać informacje na temat stanu wdrożenia profilu protokołu SCEP i certyfikatów wystawionych dla urządzenia.

## <a name="integrate-with-intune"></a>Integracja z usługą Intune

Kod dla biblioteki umożliwiający integrację z funkcją SCEP usługi Intune można pobrać z [repozytorium GitHub Microsoft/Intune-Resource-Access](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation).

Integrowanie biblioteki z produktami obejmuje następujące czynności. Te czynności wymagają znajomości sposobu korzystania z repozytoriów GitHub oraz tworzenia rozwiązań i projektów w usłudze Visual Studio.

1. Zarejestruj się w celu otrzymywania powiadomień z repozytorium.
2. Sklonuj lub pobierz repozytorium.
3. Przejdź do odpowiedniej implementacji biblioteki w folderze `\src\CsrValidation` (https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation).
4. Skompiluj bibliotekę, korzystając z instrukcji w pliku README.
5. Dołącz bibliotekę do projektu, który kompiluje serwer SCEP.
6. Wykonaj następujące zadania na serwerze SCEP:

    - Zezwól administratorowi na konfigurowanie [identyfikatora aplikacji platformy Azure, klucza aplikacji platformy Azure i identyfikatora dzierżawy](#onboard-scep-server-in-azure) (w tym artykule), z których korzysta biblioteka w celu uwierzytelniania. Administratorzy powinni mieć możliwość aktualizowania klucza aplikacji platformy Azure.
    - Określ żądania protokołu SCEP, które zawierają hasło SCEP wygenerowane przez usługę Intune.
    - Użyj biblioteki **interfejsu API walidacji żądania**, aby zwalidować hasła SCEP wygenerowane przez usługę Intune.
    - Użyj interfejsów API powiadomień biblioteki, aby powiadamiać usługę Intune o certyfikatach, które zostały wydane dla żądań protokołu SCEP zawierających hasła SCEP wygenerowane przez usługę Intune. Powiadamiaj również usługę Intune o błędach podczas przetwarzania żądań protokołu SCEP.
    - Upewnij się, że serwer rejestruje w dziennikach informacje wystarczające rozwiązywanie problemów przez administratorów.

7. Wykonaj [test integracji](#integration-testing) (w tym artykule) i rozwiąż ewentualne problemy.
8. Poinformuj klienta na piśmie:

    - W jaki sposób należy dołączyć serwer SCEP w witrynie Azure Portal.
    - Jak uzyskać identyfikator aplikacji platformy Azure i klucz aplikacji platformy Azure wymagane do skonfigurowania biblioteki.

### <a name="onboard-scep-server-in-azure"></a>Dołączanie serwera SCEP na platformie Azure

Aby przeprowadzić uwierzytelnienie w usłudze Intune, serwer SCEP musi mieć identyfikator aplikacji platformy Azure, klucz aplikacji platformy Azure oraz identyfikator dzierżawy. Serwer SCEP musi mieć również uprawnienia dostępu do interfejsu API usługi Intune.

Aby uzyskać te dane, administrator serwera musi zalogować się w witrynie Azure Portal, zarejestrować aplikację, zezwolić aplikacji na **walidację żądań usługi Microsoft Intune API\SCEP**, utworzyć klucz aplikacji i pobrać identyfikator aplikacji, klucz aplikacji oraz identyfikator dzierżawy.

Aby uzyskać wskazówki dotyczące rejestrowania aplikacji i uzyskiwania identyfikatorów i klucza, zobacz [Use portal to create an AAD application and service principal to access resources (Tworzenie aplikacji usługi AAD oraz jednostki usługi w portalu w celu uzyskiwania dostępu do zasobów)](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal).

### <a name="java-library-api"></a>Interfejs API biblioteki w języku Java

Biblioteka w języku Java jest wdrażana jako projekt Maven, który po kompilacji pobiera wszystkie zależności. Interfejs API jest wdrażany w przestrzeni nazw `com.microsoft.intune.scepvalidation` za pomocą klasy `IntuneScepServiceClient`.

#### <a name="intunescepserviceclient-class"></a>Klasa IntuneScepServiceClient

Klasa `IntuneScepServiceClient` zawiera metody używane przez usługę SCEP do walidowania haseł protokołu SCEP, powiadamiania usługi Intune o tworzonych certyfikatach i uzyskiwania listy błędów.

##### <a name="intunescepserviceclient-constructor"></a>Konstruktor IntuneScepServiceClient

Podpis:

```java
IntuneScepServiceClient(
    Properties configProperties)
```

Opis:

Inicjuje i konfiguruje obiekt `IntuneScepServiceClient`.

Parametry:

    - configProperties Obiekt właściwości zawierający informacje na temat konfiguracji klienta

Konfiguracja musi zawierać następujące właściwości:

    - AAD_APP_ID="Identyfikator aplikacji platformy Azure uzyskany podczas procesu dołączania"
    - AAD_APP_KEY="Klucz aplikacji platformy Azure uzyskany podczas procesu dołączania"
    - TENANT="Identyfikator dzierżawy uzyskany podczas procesu dołączania"
    - PROVIDER_NAME_AND_VERSION="Informacje użyte to zidentyfikowania produktu i jego wersji"
    
Jeśli rozwiązanie wymaga serwera proxy z uwierzytelnianiem lub bez uwierzytelniania, można dodać następujące właściwości:

    - PROXY_HOST="Host serwera proxy."
    - PROXY_PORT="Port, na którym nasłuchuje serwer proxy."
    - PROXY_USER="Nazwa użytkownika, której należy użyć, jeśli serwer proxy korzysta z uwierzytelniania podstawowego."
    - PROXY_PASS="Hasło, którego należy użyć, jeśli serwer proxy korzysta z uwierzytelniania podstawowego."

Wyjątki:

    - IllegalArgumentException Zgłaszany, jeśli konstruktor jest wykonywany bez odpowiedniego obiektu właściwości.

> [!IMPORTANT]
> Najlepiej zainicjować wystąpienie tej klasy i użyć go do przetworzenia wielu żądań protokołu SCEP. Dzięki temu obciążenie jest mniejsze, ponieważ tokeny uwierzytelniania i informacje na temat lokalizacji usługi są umieszczane w pamięci podręcznej.

**Uwagi dotyczące zabezpieczeń**  
Osoba wdrażająca serwer SCEP musi chronić dane wprowadzone we właściwościach konfiguracji utrwalonych w magazynie przed naruszeniem lub ujawnieniem. Zaleca się używanie odpowiednich list kontroli dostępu i szyfrowania w celu zabezpieczenia informacji.

##### <a name="validaterequest-method"></a>Metoda ValidateRequest

Podpis:

```java
void ValidateRequest(
    String transactionId,
    String certificateRequest)
```

Opis:

Waliduje żądanie certyfikatu SCEP.

Parametry:

    - transactionId         Identyfikator transakcji SCEP
    - certificateRequest    Żądanie certyfikatu PKCS #10 szyfrowane kodem DER kodowane metodą Base64 jako ciąg

Wyjątki:

    - IllegalArgumentException      Zgłaszany w przypadku wywołania za pomocą nieprawidłowego parametru
    - IntuneScepServiceException    Zgłaszany, jeśli żądanie certyfikatu nie jest prawidłowe
    - Exception                     Zgłaszany, jeśli wystąpi nieoczekiwany błąd

> [!IMPORTANT]
> Wyjątki zgłoszone przez tę metodę powinny być rejestrowane przez serwer. Należy pamiętać, że właściwości `IntuneScepServiceException` zawierają szczegółowe informacje dotyczące powodu niepowodzenia walidacji żądania certyfikatu.

**Uwagi dotyczące zabezpieczeń**  

- Jeśli ta metoda zgłasza wyjątek, serwer SCEP **nie może** wystawić certyfikatu klientowi.
- Niepowodzenia walidacji żądania certyfikatu SCEP mogą wskazywać na problem z infrastrukturą usługi Intune. Mogą również wskazywać na próbę uzyskania certyfikatu przez osobę niepowołaną.

##### <a name="sendsuccessnotification-method"></a>Metoda SendSuccessNotification

Podpis:

```java
void SendSuccessNotification(
    String transactionId,
    String certificateRequest,
    String certThumbprint,
    String certSerialNumber,
    String certExpirationDate,
    String certIssuingAuthority)
```

Opis:

Powiadamia usługę Intune, że certyfikat został utworzony w ramach przetwarzania żądania protokołu SCEP.

Parametry:

    - transactionId           Identyfikator transakcji SCEP
    - certificateRequest    Żądanie certyfikatu PKCS #10 szyfrowane kodem DER kodowane metodą Base64 jako ciąg
    - certThumprint           Odcisk palca aprowizowanego certyfikatu
    - certSerialNumber        Numer seryjny aprowizowanego certyfikatu
    - .certExpirationDate      Data wygaśnięcia aprowizowanego certyfikatu Ciąg daty i czasu powinien być w formacie internetowego czasu UTC (RRRR-MM-DDThh:mm:ss.sssTZD) zgodnie z normą ISO 8601.
    - certIssuingAuthority    Nazwa urzędu, który wystawił certyfikat

Wyjątki:

    - IllegalArgumentException      Zgłaszany w przypadku wywołania za pomocą nieprawidłowego parametru
    - IntuneScepServiceException    Zgłaszany, jeśli żądanie certyfikatu nie jest prawidłowe
    - Exception                     Zgłaszany, jeśli wystąpi nieoczekiwany błąd

> [!IMPORTANT]
> Wyjątki zgłoszone przez tę metodę powinny być rejestrowane przez serwer. Należy pamiętać, że właściwości `IntuneScepServiceException` zawierają szczegółowe informacje dotyczące powodu niepowodzenia walidacji żądania certyfikatu.

**Uwagi dotyczące zabezpieczeń**

- Jeśli ta metoda zgłasza wyjątek, serwer SCEP **nie może** wystawić certyfikatu klientowi.
- Niepowodzenia walidacji żądania certyfikatu SCEP mogą wskazywać na problem z infrastrukturą usługi Intune. Mogą również wskazywać na próbę uzyskania certyfikatu przez osobę niepowołaną.

##### <a name="sendfailurenotification-method"></a>Metoda SendFailureNotification

Podpis:

```java
void SendFailureNotification(
    String transactionId,
    String certificateRequest,
    long  hResult,
    String errorDescription)
```

Opis:

Powiadamia usługę Intune, że wystąpił błąd podczas przetwarzania żądania protokołu SCEP. Ta metoda nie powinna być wywoływana w przypadku wyjątków zgłaszanych przez metody tej klasy.

Parametry:

    - transactionId         Identyfikator transakcji SCEP
    - certificateRequest    Żądanie certyfikatu PKCS #10 szyfrowane kodem DER kodowane metodą Base64 jako ciąg
    - hResult               Kod błędu Win32 najlepiej opisujący błąd, który wystąpił. Zobacz [Kody błędów Win32](https://msdn.microsoft.com/library/cc231199.aspx)
    - errorDescription      Opis błędu, który wystąpił

Wyjątki:

    - IllegalArgumentException      Zgłaszany w przypadku wywołania za pomocą nieprawidłowego parametru
    - IntuneScepServiceException    Zgłaszany, jeśli żądanie certyfikatu nie jest prawidłowe
    - Exception                     Zgłaszany, jeśli wystąpi nieoczekiwany błąd

> [!IMPORTANT]
> Wyjątki zgłoszone przez tę metodę powinny być rejestrowane przez serwer. Należy pamiętać, że właściwości `IntuneScepServiceException` zawierają szczegółowe informacje dotyczące powodu niepowodzenia walidacji żądania certyfikatu.

**Uwagi dotyczące zabezpieczeń**

- Jeśli ta metoda zgłasza wyjątek, serwer SCEP **nie może** wystawić certyfikatu klientowi.
- Niepowodzenia walidacji żądania certyfikatu SCEP mogą wskazywać na problem z infrastrukturą usługi Intune. Mogą również wskazywać na próbę uzyskania certyfikatu przez osobę niepowołaną.

##### <a name="setsslsocketfactory-method"></a>Metoda SetSslSocketFactory

Podpis:

```java
void SetSslSocketFactory(
    SSLSocketFactory factory)
```

Opis:

Użyj tej metody, aby poinformować klienta, że musi użyć określonej (a nie domyślnej) fabryki gniazd protokołu SSL podczas komunikowania się z usługą Intune.

Parametry:

    - factory    Fabryka gniazd protokołu SSL, której klient powinien użyć w przypadku żądań protokołu HTTPS

Wyjątki:

    - IllegalArgumentException    Zgłaszany, jeśli wywołany za pomocą nieprawidłowego parametru

> [!NOTE]
> Jeśli fabryka gniazd protokołu SSL jest wymagana, musi być skonfigurowana przez wykonaniem innych metod tej klasy.

## <a name="integration-testing"></a>Testowanie integracji

Walidacja i sprawdzenie, że rozwiązanie jest prawidłowo zintegrowane z usługą Intune jest bezwzględnie konieczne. Poniższej znajduje się lista odpowiednich czynności:

1. Skonfiguruj [konto wersji próbnej usługi Intune](../fundamentals/account-sign-up.md).
2. Dołącz [serwer SCEP w witrynie Azure Portal](#onboard-scep-server-in-azure) (w tym artykule).
3. [Skonfiguruj serwer SCEP](certificates-scep-configure.md) przy użyciu identyfikatorów i klucza utworzonych podczas dołączania serwera SCEP.
4. [Zarejestruj urządzenia](../enrollment/device-enrollment.md) w celu przetestowania scenariuszy wymienionych w [macierzy testowania scenariuszy](https://github.com/Microsoft/Intune-Resource-Access/blob/develop/src/CsrValidation/doc/TestMatrix.csv).
5. [Utwórz profil zaufanego certyfikatu głównego](certificates-scep-configure.md) w celu przetestowania urzędu certyfikacji.
6. Utwórz profile protokołu SCEP w celu przetestowania scenariuszy wymienionych w [macierzy testowania scenariuszy](https://github.com/Microsoft/Intune-Resource-Access/blob/develop/src/CsrValidation/doc/TestMatrix.csv).
7. [Przypisz profile](../configuration/device-profile-assign.md) użytkownikom, którzy zarejestrowali urządzenia.
8. Poczekaj, aż urządzenia zsynchronizują się z usługą Intune. Możesz też ręcznie [zsynchronizować urządzenia](../remote-actions/device-sync.md).
9. Upewnij się, że zaufany certyfikat główny i profile SCEP [są wdrożone na urządzeniach](../configuration/device-profile-monitor.md).
10. Upewnij się, że zaufany certyfikat główny jest zainstalowany na wszystkich urządzeniach.
11. Upewnij się, że certyfikaty SCEP dla przypisanych profilów są zainstalowane na wszystkich urządzeniach.
12. Upewnij się, że właściwości zainstalowanych certyfikatów odpowiadają właściwościom skonfigurowanym w profilu protokołu SCEP.
13. Upewnij się, że wystawione certyfikaty są wymienione w konsoli usługi Intune.

## <a name="see-also"></a>Zobacz także

- [Add 3rd party CA overview (Dodawanie urzędu certyfikacji innej firmy — omówienie)](certificate-authority-add-scep-overview.md)
- [Setup Intune](../fundamentals/setup-steps.md) (Konfigurowanie usługi Intune)
- [Rejestrowanie urządzeń](../enrollment/device-enrollment.md)
- [Tworzenie profilu certyfikatu protokołu SCEP](certificates-profile-scep.md) (w tym scenariuszu nie jest używany instalator NDES Server\Connector firmy Microsoft)
