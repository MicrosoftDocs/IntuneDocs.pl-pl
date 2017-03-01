---
title: "Jak skonfigurować certyfikaty z użyciem usługi Intune"
titleSuffix: Intune Azure preview
description: "Usługa Intune Azure w wersji zapoznawczej: Dowiedz się, jak tworzyć i przypisywać certyfikaty, które pozwolą zabezpieczyć sieci Wi-Fi i VPN oraz inne połączenia, korzystając z usługi Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 364534ad788466f8b268b4091decee5326b94163
ms.lasthandoff: 02/16/2017


---

# <a name="how-to-configure-certificates-in-microsoft-intune"></a>Jak skonfigurować certyfikaty z użyciem usługi Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Po zapewnieniu użytkownikom dostępu do zasobów firmowych za pośrednictwem sieci VPN, sieci Wi-Fi lub profilów poczty e-mail możesz zabezpieczyć dostęp przy użyciu certyfikatu zainstalowanego na urządzeniu każdego użytkownika. Podstawowy przepływ pracy zakłada wykonanie następujących czynności:

1. Upewnij się, że dysponujesz odpowiednią infrastrukturą certyfikatów. Możesz użyć [certyfikatów protokołu SCEP](configure-certificate-infrastructure-for-scep.md) i [certyfikatów protokołu PKCS](configure-certificate-infrastructure-for-pfx.md).
2. Zainstaluj certyfikat główny lub certyfikat pośredniego urzędu certyfikacji (CA) na każdym urządzeniu, aby urządzenia rozpoznawały urząd certyfikacji jako wiarygodny. W tym celu należy utworzyć i przypisać **profil zaufanego certyfikatu**. Po przypisaniu tego profilu urządzenia zarządzane przy użyciu usługi Intune zażądają certyfikatu głównego i otrzymają go. Należy utworzyć oddzielny profil dla każdej platformy. Profile zaufanego certyfikatu są dostępne dla następujących platform:
    - System iOS 8.0 i nowsze
    - System macOS 10.9 i nowsze
    - System Android 4.0 i nowsze<!--Android for Work --->
    - Windows 8.1 i nowsze
    - System Windows Phone 8.1 lub nowszy
    - System Windows 10 lub nowszy
3. Utwórz profile certyfikatów, aby mieć pewność, że poszczególne urządzenia żądają certyfikatu w celu jego użycia do uwierzytelniania dostępu do poczty e-mail, sieci VPN i sieci Wi-Fi. Dla urządzeń korzystających z następujących platform można tworzyć i wdrażać profile certyfikatów protokołów **PKCS** i **SCEP**:
    - System iOS 8.0 i nowsze
    - Android 4.0 i nowsze
    - Program Android for Work
    - System Windows 10 (Desktop i Mobile) i nowsze

    Na urządzeniach korzystających z następujących platform można używać wyłącznie profilów certyfikatów protokołu SCEP:

-     System macOS 10.9 i nowsze
-     System Windows Phone 8.1 lub nowszy

Dla każdej platformy urządzenia należy utworzyć oddzielny profil. Po utworzeniu certyfikatu należy go skojarzyć z utworzonym profilem zaufanego certyfikatu głównego.

### <a name="further-considerations"></a>Dodatkowe uwagi

- Jeśli nie masz urzędu certyfikacji przedsiębiorstwa, musisz go utworzyć.
- Jeśli na podstawie platform urządzeń zdecydujesz się na użycie uproszczonego protokołu rejestrowania certyfikatów (SCEP), musisz również skonfigurować serwer usługi rejestracji urządzeń sieciowych (NDES).
- Niezależnie od tego, czy zamierzasz używać profilów certyfikatów protokołu SCEP czy PKCS, musisz pobrać i skonfigurować łącznik certyfikatów usługi Microsoft Intune.

## <a name="before-you-start"></a>Przed rozpoczęciem


### <a name="if-you-want-to-use-scep-certificates"></a>Korzystanie z certyfikatów protokołu SCEP

Spełnij niezbędne wymagania wstępne opisane w części [Infrastruktura certyfikatów dla profilu SCEP](/intune-azure/configure-devices/configure-certificate-infrastructure-for-scep).

### <a name="if-you-want-to-use-pkcs-certificates"></a>Korzystanie z certyfikatów protokołu PKCS

Spełnij niezbędne wymagania wstępne opisane w części [Infrastruktura certyfikatów dla profilu PKCS](/intune-azure/configure-devices/configure-certificate-infrastructure-for-pfx).

## <a name="task-1-export-the-trusted-root-ca-certificate"></a>Zadanie 1 — Eksportowanie certyfikatu zaufanego głównego urzędu certyfikacji
Wyeksportuj certyfikat zaufanego głównego urzędu certyfikacji w formacie pliku **.cer** z wystawiającego urzędu certyfikacji lub dowolnego urządzenia traktującego wystawiający urząd certyfikacji jako zaufany. Nie należy eksportować klucza prywatnego.

Ten certyfikat zostanie zaimportowany podczas konfigurowania profilu zaufanego certyfikatu.

## <a name="task-2-create-trusted-certificate-profiles"></a>Zadanie 2 — Tworzenie profilów zaufanych certyfikatów
Aby móc utworzyć profil certyfikatu protokołu SCEP lub PKCS, należy utworzyć profil zaufanego certyfikatu. Dla każdej platformy urządzenia wymagany jest profil zaufanego certyfikatu oraz profil SCEP lub PKCS.

### <a name="to-create-a-trusted-certificate-profile"></a>Aby utworzyć profil zaufanego certyfikatu

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno pozycje **Więcej usług** > **Inne** > **Intune**.
3. W bloku **Intune** wybierz pozycję **Konfiguruj urządzenia**.
2. W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
3. W bloku profilów wybierz pozycję **Utwórz profil**.
4. W bloku **Utwórz profil** uzupełnij pola **Nazwa** i **Opis** odnoszące się do profilu zaufanego certyfikatu.
5. Z listy rozwijanej **Platforma** wybierz platformę urządzenia dla danego zaufanego certyfikatu. Obecnie dla ustawień ograniczeń dotyczących urządzeń można wybrać jedną z następujących platform:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 lub nowszy**
    - **Windows 10 lub nowszy**
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Zaufany certyfikat**.
7. Przejdź do lokalizacji certyfikatu zapisanego w zadaniu 1, a następnie kliknij przycisk **OK**.
8. Dotyczy wyłącznie urządzeń z systemem Windows 8.1 i Windows 10: wybierz dla zaufanego certyfikatu **magazyn docelowy** spośród wymienionych poniżej:
    - **Magazyn certyfikatów komputera — główny**
    - **Magazyn certyfikatów komputera — pośredni**
    - **Magazyn certyfikatów użytkownika — pośredni**
8. Gdy skończysz, wybierz opcję **OK**, wróć do bloku **Utwórz profil** i wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony w bloku listy profilów.
Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](how-to-assign-device-profiles.md) (Sposoby przypisywania profilów urządzeń).


> [!Note]
> Na urządzeniach z systemem Android zostanie wyświetlone powiadomienie o przeprowadzeniu instalacji zaufanego certyfikatu przez osobę trzecią.

## <a name="task-3-create-scep-or-pkcs-certificate-profiles"></a>Zadanie 3 — Tworzenie profilów certyfikatów protokołu SCEP lub PKCS
Po utworzeniu profilu zaufanego certyfikatu należy utworzyć profile certyfikatów protokołu SCEP lub PKCS dla wszystkich platform, które będą używane. Podczas tworzenia profilu certyfikatu protokołu SCEP należy wskazać profil zaufanego certyfikatu dla danej platformy. W ten sposób oba profile certyfikatów zostaną połączone, niemniej jednak każdy profil należy przypisać osobno.

### <a name="to-create-an-scep-certificate-profile"></a>Aby utworzyć profil certyfikatu protokołu SCEP

1. W witrynie Azure Portal wybierz obciążenie **Konfiguruj urządzenia**.
2. W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
3. W bloku profilów wybierz pozycję **Utwórz profil**.
4. W bloku **Utwórz profil** uzupełnij pola **Nazwa** i **Opis** odnoszące się do profilu certyfikatu protokołu SCEP.
5. Z listy rozwijanej **Platforma** wybierz platformę urządzenia dla danego certyfikatu protokołu SCEP. Obecnie dla ustawień ograniczeń dotyczących urządzeń można wybrać jedną z następujących platform:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 lub nowszy**
    - **Windows 10 lub nowszy**
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Certyfikat SCEP**.
7. W bloku **Certyfikat SCEP** skonfiguruj następujące ustawienia:
    - **Okres ważności certyfikatu** — jeśli dla urzędu wystawiającego certyfikaty uruchomiono polecenie **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**, które dopuszcza niestandardowy okres ważności, możesz określić czas pozostały do wygaśnięcia certyfikatu.<br>Możesz podać wartość niższą niż okres ważności danego szablonu certyfikatu, ale nie wyższą. Jeśli na przykład okres ważności certyfikatu w szablonie certyfikatu wynosi dwa lata, możesz określić wartość jednego roku, ale nie pięciu lat. Wartość musi być też niższa niż pozostały okres ważności certyfikatu urzędu wystawiającego certyfikaty. 
    - **Dostawca magazynu kluczy (KSP)** (Windows Phone 8.1, Windows 8.1, Windows 10) — określ miejsce przechowywania klucza certyfikatu. Można wybrać jedną z następujących opcji:
        - **Zarejestruj u dostawcy magazynu kluczy modułu Trusted Platform Module (TPM), w przeciwnym razie u dostawcy magazynu kluczy oprogramowania**
        - **Zarejestruj u dostawcy magazynu kluczy modułu Trusted Platform Module (TPM), w przeciwnym razie niepowodzenie**
        - **Zarejestruj w usłudze Passport, w przeciwnym razie niepowodzenie (system Windows 10 i nowsze)**
        - **Zarejestruj u dostawcy magazynu kluczy oprogramowania**
    - **Format nazwy podmiotu** — wybierz z listy sposób automatycznego tworzenia przez usługę Intune nazwy podmiotu w żądaniu certyfikatu. Jeśli certyfikat przeznaczony jest dla użytkownika, możesz również uwzględnić w nazwie podmiotu adres e-mail tego użytkownika. Wybierz spośród opcji:
        - **Nieskonfigurowany**
        - **Nazwa pospolita**
        - **Nazwa pospolita obejmująca adres e-mail**
        - **Nazwa pospolita jako adres e-mail**
    - **Nazwa alternatywna podmiotu** — wybierz z listy sposób automatycznego tworzenia przez usługę Intune wartości nazwy alternatywnej podmiotu w żądaniu certyfikatu. Jeśli na przykład jako typ certyfikatu został wybrany typ użytkownika, w alternatywnej nazwie podmiotu można uwzględnić główną nazwę użytkownika (nazwę UPN). Jeśli certyfikat klienta będzie używany do uwierzytelniania go wobec serwera zasad sieciowych, dla alternatywnej nazwy podmiotu musisz ustawić nazwę UPN. 
    - **Użycie klucza** — określ opcje użycia klucza certyfikatu. Można wybrać następujące opcje: 
        - **Szyfrowanie klucza** — zezwalaj na wymianę kluczy tylko wtedy, gdy klucz jest zaszyfrowany. 
        - **Podpis cyfrowy** — zezwalaj na wymianę kluczy tylko wtedy, gdy klucz jest chroniony przy użyciu podpisu cyfrowego. 
    - **Rozmiar klucza (bity)** —wybierz liczbę bitów zawartych w kluczu. 
    - **Algorytm skrótu** (Android, Windows Phone 8.1, Windows 8.1, Windows 10) — wybierz jeden z dostępnych typów algorytmu wyznaczania wartości skrótu do użycia z tym certyfikatem. Wybierz najwyższy poziom zabezpieczeń obsługiwany przez podłączane urządzenia. 
    - **Certyfikat główny** — wybierz profil certyfikatu głównego urzędu certyfikacji, który został uprzednio skonfigurowany i przypisany do użytkownika lub urządzenia. Ten certyfikat urzędu certyfikacji musi być certyfikatem głównym urzędu certyfikacji wystawiającego certyfikat skonfigurowany w ramach danego profilu certyfikatu. 
    - **Rozszerzone użycie klucza** — kliknij pozycję **Dodaj**, aby dodać wartości w zależności od celu certyfikatu. W większości przypadków będzie wymagane wprowadzenie wartości **Uwierzytelnianie klienta** dla certyfikatu, aby zapewnić użytkownikom lub urządzeniom możliwość uwierzytelnienia na serwerze. Można jednak dodać również inne użycia klucza, zgodnie z potrzebami. 
    - **Ustawienia rejestracji**
        - **Próg odnawiania (%)** — określ wartość procentową pozostałego okresu ważności certyfikatu, przy której urządzenie ma żądać jego odnowienia.
        - **Adresy URL serwerów SCEP** — określ co najmniej jeden adres URL dla serwerów usługi NDES, które będą wystawiać certyfikaty za pośrednictwem protokołu SCEP. 
8. Gdy skończysz, wróć do bloku **Utwórz profil** i wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony w bloku listy profilów.

Postępuj zgodnie z instrukcjami na stronie konfiguracji profilu, aby skonfigurować ustawienia profilu certyfikatu SCEP.
>[!Note]
> Dotyczy wyłącznie urządzeń z systemem iOS: w obszarze Format nazwy podmiotu wybierz opcję Niestandardowy, aby wprowadzić niestandardowy format nazwy podmiotu.
> Aktualnie są obsługiwane dwie zmienne dla formatu niestandardowego: **Nazwa pospolita (CN)** i **Adres e-mail (E)**. Przy użyciu kombinacji tych zmiennych i statycznych ciągów można utworzyć niestandardowy format nazwy podmiotu, na przykład taki: **CN={{NazwaUżytkownika}},E={{AdresEmail}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US**. W tym przykładzie utworzono format nazwy podmiotu, w którym oprócz zmiennych CN i E użyto ciągów zmiennych Organizational Unit, Organization, Location, State, i Country. [W tym temacie](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) omówiono funkcję **CertStrToName** i obsługiwane przez nią ciągi.


### <a name="to-create-a-pkcs-certificate-profile"></a>Aby utworzyć profil certyfikatu PKCS

W witrynie Azure Portal wybierz obciążenie **Konfiguruj urządzenia**.
2. W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
3. W bloku profilów kliknij pozycję **Utwórz profil**.
4. W bloku **Utwórz profil** uzupełnij pola **Nazwa** i **Opis** odnoszące się do profilu certyfikatu protokołu PKCS.
5. Z listy rozwijanej **Platforma** wybierz odpowiednią platformę urządzenia dla danego certyfikatu protokołu PKCS:
    - **Android**
    - **iOS**
    - **Windows 10 lub nowszy**
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Certyfikat PKCS**.
7. W bloku **Certyfikat PKCS** skonfiguruj następujące ustawienia:
    - **Próg odnawiania (%)** — określ wartość procentową pozostałego okresu ważności certyfikatu, przy której urządzenie ma żądać jego odnowienia.
    - **Okres ważności certyfikatu** — jeśli dla urzędu wystawiającego certyfikaty uruchomiono polecenie **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**, które dopuszcza niestandardowy okres ważności, możesz określić czas pozostały do wygaśnięcia certyfikatu.<br>Możesz podać wartość niższą niż okres ważności danego szablonu certyfikatu, ale nie wyższą. Jeśli na przykład okres ważności certyfikatu w szablonie certyfikatu wynosi dwa lata, możesz określić wartość jednego roku, ale nie pięciu lat. Wartość musi być też niższa niż pozostały okres ważności certyfikatu urzędu wystawiającego certyfikaty.
    - **Dostawca magazynu kluczy (KSP)** (Windows 10) -
    - **Urząd certyfikacji** -
    - **Nazwa urzędu certyfikacji** -
    - **Nazwa szablonu certyfikatu** — wprowadź nazwę szablonu certyfikatu, do którego użycia skonfigurowano usługę rejestracji urządzeń sieciowych i który dodano do urzędu wystawiającego certyfikaty.
    Upewnij się, że nazwa ta dokładnie pokrywa się z nazwą jednego z szablonów certyfikatów wymienionych w rejestrze serwera z uruchomioną usługą rejestracji urządzeń sieciowych. Zwróć uwagę, aby podać nazwę szablonu certyfikatu, a nie nazwę wyświetlaną szablonu certyfikatu. 
    Aby znaleźć nazwy szablonów certyfikatów, przejdź do następującego klucza: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP. Szablony certyfikatów są w nim wyświetlane jako wartości kluczy **EncryptionTemplate**, **GeneralPurposeTemplate**i **SignatureTemplate**. Dla wszystkich trzech szablonów certyfikatów domyślna wartość to IPSECIntermediateOffline, mapująca się na nazwę wyświetlaną szablonu **IPSec (żądanie offline)**. 
    - **Format nazwy podmiotu** — wybierz z listy sposób automatycznego tworzenia przez usługę Intune nazwy podmiotu w żądaniu certyfikatu. Jeśli certyfikat przeznaczony jest dla użytkownika, możesz również uwzględnić w nazwie podmiotu adres e-mail tego użytkownika. Wybierz spośród opcji:
        - **Nieskonfigurowany**
        - **Nazwa pospolita**
        - **Nazwa pospolita obejmująca adres e-mail**
        - **Nazwa pospolita jako adres e-mail**
    - **Nazwa alternatywna podmiotu** — wybierz z listy sposób automatycznego tworzenia przez usługę Intune wartości nazwy alternatywnej podmiotu w żądaniu certyfikatu. Jeśli na przykład jako typ certyfikatu został wybrany typ użytkownika, w alternatywnej nazwie podmiotu można uwzględnić główną nazwę użytkownika (nazwę UPN). Jeśli certyfikat klienta będzie używany do uwierzytelniania go wobec serwera zasad sieciowych, dla alternatywnej nazwy podmiotu musisz ustawić nazwę UPN.
    - **Rozszerzone użycie klucza** (Android) — kliknij pozycję **Dodaj**, aby dodać wartości w zależności od celu certyfikatu. W większości przypadków będzie wymagane wprowadzenie wartości **Uwierzytelnianie klienta** dla certyfikatu, aby zapewnić użytkownikom lub urządzeniom możliwość uwierzytelnienia na serwerze. Można jednak dodać również inne użycia klucza, zgodnie z potrzebami. 
    - **Certyfikat główny** (Android) — wybierz profil certyfikatu głównego urzędu certyfikacji, który został uprzednio skonfigurowany i przypisany do użytkownika lub urządzenia. Ten certyfikat urzędu certyfikacji musi być certyfikatem głównym urzędu certyfikacji wystawiającego certyfikat skonfigurowany w ramach danego profilu certyfikatu.
8. Gdy skończysz, wróć do bloku **Utwórz profil** i wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony w bloku listy profilów.

## <a name="task-4-assign-certificate-profiles"></a>Zadanie 4: Wdrażanie profilów certyfikatów

Przed przypisaniem profilów certyfikatów do grup należy wziąć pod uwagę następujące kwestie:

- Podczas przypisywania profilów certyfikatów do grup na urządzeniu jest instalowany plik certyfikatu z profilu certyfikatu zaufanego urzędu certyfikacji. Profil certyfikatu protokołu SCEP lub PKCS jest używany przez urządzenie do tworzenia żądania certyfikatu.
- Profile certyfikatów mogą być instalowane wyłącznie na urządzeniach z platformą użytą podczas tworzenia profilu.
- Profile certyfikatów można również wdrażać dla kolekcji użytkowników lub kolekcji urządzeń.
- Aby opublikować certyfikaty dla urządzenia jak najszybciej po jego rejestracji, należy wdrożyć profil certyfikatu w grupie użytkowników, a nie w grupie urządzeń. W przypadku wdrożenia w grupie urządzeń wymagana jest pełna rejestracja urządzenia przed otrzymaniem przez nie zasad.
- Mimo że każdy profil należy wdrożyć osobno, konieczne jest również wdrożenie profilu zaufanego certyfikatu głównego urzędu certyfikacji oraz profilu protokołu SCEP lub PKCS. W przeciwnym razie zasady certyfikatu protokołu SCEP lub PKCS nie będą działać.

## <a name="next-steps"></a>Następne kroki
Ogólne informacje dotyczące sposobu przypisywania profilów urządzeń znajdują się w temacie [How to assign device profiles](how-to-assign-device-profiles.md) (Jak przypisywać profile urządzeń).

