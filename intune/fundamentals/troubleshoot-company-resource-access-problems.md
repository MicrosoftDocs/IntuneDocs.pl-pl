---
title: Kody błędów i stanu w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zobacz listę błędów, kodów stanu, opisów i rozwiązań występujących podczas korzystania z urządzeń zarządzanych przez usługę MDM oraz podczas uzyskiwania dostępu do zasobów firmy, a także listę błędów występujących na urządzeniach z systemem iOS i błędów odpowiedzi OMA w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/20/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 40622ced-6029-4abf-873e-b51d2b51934c
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 17a8ebfcad2bcf485771f26184377aeb2c4bf4e1
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72509792"
---
# <a name="common-error-codes-and-descriptions-in-microsoft-intune"></a>Typowe kody błędów i opisy w usłudze Microsoft Intune

W tym artykule wymieniono typowe błędy, kody stanu, opisy i możliwe rozwiązania występujące podczas uzyskiwania dostępu do zasobów organizacji. Te informacje ułatwią rozwiązywanie problemów z dostępem podczas korzystania z usługi Microsoft Intune.

Jeśli potrzebujesz pomocy technicznej, zobacz [Uzyskiwanie pomocy technicznej dotyczącej usługi Microsoft Intune](../get-support.md).

## <a name="status-codes-for-mdm-managed-windows-devices"></a>Kody stanu dla urządzeń z systemem Windows zarządzanych przez usługę MDM

|Kod stanu|Komunikat o błędzie|Co należy zrobić|
|---------------|-----------------|--------------|
|10 (APP_CI_ENFORCEMENT_IN_PROGRESS)|Instalacja w toku||
|20 (APP_CI_ENFORCEMENT_IN_PROGRESS_WAITING_CONTENT)|Oczekiwanie na zawartość||
|30 (APP_CI_ENFORCEMENT_ERROR_RETRIEVING_CONTENT)|Pobieranie zawartości|Prawdopodobna przyczyna: stan zadania 30 wskazuje, że pobieranie aplikacji przez użytkownika nie powiodło się.<br /><br />Czym może to być spowodowane:<br /><br />Podczas pobierania aplikacji urządzenie utraciło połączenie z Internetem.<br /><br />Być może wygasł certyfikat wystawiony dla urządzenia w chwili rejestracji.<br /><br />Środki zaradcze:<br /><br />Uruchom aplet Aplikacje firmowe z Panelu sterowania na urządzeniu, aby upewnić się, że certyfikat urządzenia nie wygasł. Jeśli tak się stało, konieczna będzie ponowna rejestracja urządzenia.<br /><br />Upewnij się, że urządzenie jest połączone z Internetem, i spróbuj ponownie zażądać aplikacji.|
|40 (APP_CI_ENFORCEMENT_IN_PROGRESS_CONTENT_DOWNLOADED)|Pobieranie zawartości ukończone||
|50 (APP_CI_ENFORCEMENT_IN_PROGRESS_INSTALLING)|Instalacja w toku||
|60 (APP_CI_ENFORCEMENT_ERROR_INSTALLING)|Wystąpił błąd instalacji|Po pobraniu nie powiodła się instalacja aplikacji.<br /><br />Na urządzeniu nie ma certyfikatu podpisywania kodu użytego do podpisania aplikacji.<br /><br />Zależność struktury, od której jest zależna aplikacja, nie została zainstalowana na urządzeniu.<br /><br />Upewnij się, że certyfikat podpisywania kodu użyty do podpisania tej aplikacji jest na urządzeniu, i potwierdź u administratora, że taki certyfikat był przeznaczony dla wszystkich zarejestrowanych przez przedsiębiorstwo urządzeń z systemem Windows RT.<br /><br />W przypadku, gdy przyczyną niepowodzenia instalacji jest brakująca zależność struktury, administrator będzie musiał ponownie opublikować aplikację, pakując strukturę wraz z pakietem aplikacji.<br /><br />Pobrany pakiet aplikacji nie jest prawidłowym pakietem, może być uszkodzony lub może nie być zgodny z wersją systemu operacyjnego na urządzeniu.|
|70 (APP_CI_ENFORCEMENT_SUCCEEDED)|Powodzenie instalacji||
|80 (APP_CI_ENFORCEMENT_IN_PROGRESS)|Odinstalowywanie w toku||
|90 (APP_CI_ENFORCEMENT_ERROR)|Wystąpił błąd odinstalowywania||
|100 (APP_CI_ENFORCEMENT_SUCCEEDED)|Powodzenie odinstalowywania||
|110 (APP_CI_ENFORCEMENT_ERROR)|Niezgodność skrótu zawartości||
|120 (APP_CI_ENFORCEMENT_ERROR)|Klucz pobierania lokalnego/pobieranie lokalne nie jest włączone||
|130 (APP_CI_ENFORCEMENT_ERROR)|Niepowodzenie instalacji licencji MSADP||
|Brak stanu (APP_CI_ENFORCEMENT_UNKNOWN)|n/d|Stan jest aktualnie nieznany.|

## <a name="company-resource-access-common-errors"></a>Dostęp do zasobów firmy (typowe błędy)

|Kod stanu|Szesnastkowy kod błędu|Komunikat o błędzie|
|---------------|--------------------------|-----------------|
|-2016281101|0x87D1FDF3|Nie znaleziono żądania zasad żądania połączeń oprogramowania MDM|
|-2016281102|0x87D1FDF2|Nie znaleziono adresu URL usługi rejestrowania urządzeń sieciowych|
|-2016281103|0x87D1FDF1|Nie znaleziono informacji o certyfikacie zasad żądania połączeń oprogramowania MDM|
|-2016281104|0x87D1FDF0|Nie znaleziono informacji o certyfikacie elementu konfiguracji oprogramowania MDM|
|-2016281105|0x87D1FDEF|Nie można ocenić reguły|
|-2016281106|0x87D1FDEE|Nie dotyczy, ponieważ utracono podczas rozwiązywania konfliktów|
|-2016281107|0x87D1FDED|Nieobsługiwane źródło wykrywania ustawień|
|-2016281108|0x87D1FDEC|W elemencie konfiguracji nie znaleziono przywoływanego ustawienia|
|-2016281109|0x87D1FDEB|Konwersja typu danych nie powiodła się|
|-2016281110|0x87D1FDEA|Nieprawidłowy parametr ustawienia CIM|
|-2016281111|0x87D1FDE9|Nie dotyczy tego urządzenia|
|-2016281112|0x87D1FDE8|Korygowanie nie powiodło się|
|-2016330905|0x87D13B67|Stan aplikacji jest nieznany|
|-2016330906|0x87D13B66|Aplikacja jest zarządzana, ale została usunięta przez użytkownika|
|-2016330907|0x87D13B65|Urządzenie korzysta z kodu realizacji|
|-2016330908|0x87D13B64|Instalacja aplikacji nie powiodła się|
|-2016330909|0x87D13B63|Użytkownik odrzucił ofertę zaktualizowania aplikacji|
|-2016330910|0x87D13B62|Użytkownik odrzucił ofertę zainstalowania aplikacji|
|-2016330911|0x87D13B61|Użytkownik zainstalował aplikację, zanim możliwe było zainstalowanie aplikacji zarządzanej|
|-2016330912|0x87D13B60|Zaplanowano zainstalowanie tej aplikacji, ale sfinalizowanie transakcji wymaga kodu realizacji|
|-2016341109|0x87D1138B|Urządzenie z systemem iOS zwróciło błąd|
|-2016341110|0x87D1138A|Urządzenie z systemem iOS odrzuciło polecenie z powodu niepoprawnego formatu|
|-2016341111|0x87D11389|Urządzenie z systemem iOS zwróciło nieoczekiwany stan bezczynności|
|-2016341112|0x87D11388|Urządzenie z systemem iOS jest aktualnie zajęte|

## <a name="errors-returned-by-ios-devices"></a>Błędy zwrócone przez urządzenia z systemem iOS

### <a name="company-portal-errors"></a>Błędy aplikacji Portal firmy

|Tekst błędu w aplikacji Portal firmy|Kod stanu HTTP|Dodatkowe informacje o błędzie|
|---|---|---|
|__Wewnętrzny błąd serwera__ <br>Prawdopodobnie nie udało się nawiązać połączenia z powodu wewnętrznego błędu serwera. Spróbuj ponownie, a jeśli problem będzie się powtarzać, skontaktuj się z administratorem IT.|Błąd 500|Przyczyną tego błędu jest prawdopodobnie problem z usługą Intune. Problem powinien zostać rozwiązany po stronie usługi Intune. Prawdopodobnie nie jest on spowodowany problemami po stronie klienta.|
|__Tymczasowo niedostępne__ <br>Prawdopodobnie nie udało się nawiązać połączenia, ponieważ usługa jest tymczasowo niedostępna. Spróbuj ponownie, a jeśli problem będzie się powtarzać, skontaktuj się z administratorem IT.|Błąd 503|Błąd jest prawdopodobnie spowodowany tymczasowym problemem z usługą Intune, np. trwającymi pracami konserwacyjnymi. Problem powinien zostać rozwiązany po stronie usługi Intune. Prawdopodobnie nie jest on spowodowany problemami po stronie klienta.|
|__Nie można połączyć się z serwerem__ <br>Prawdopodobnie nie udało się nawiązać połączenia. Spróbuj ponownie, a jeśli problem będzie się powtarzać, skontaktuj się z administratorem IT.|Błąd nie jest powiązany z kodem stanu HTTP.|Nie udało się nawiązać bezpiecznego połączenia z serwerem, prawdopodobnie na skutek problemu z protokołem SSL i używanymi certyfikatami. Ten problem może wynikać z braku zgodności konfiguracji klienta z wymaganiami firmy Apple dotyczącymi funkcji App Transport Security (ATS).|
|__Wystąpiły problemy__ <br>Nie udało się załadować klienta Portal firmy. Spróbuj ponownie, a jeśli problem będzie się powtarzać, skontaktuj się z administratorem IT.|Błąd 400|Ten błąd zostanie wyświetlony w przypadku wystąpienia dowolnego błędu o trzycyfrowym kodzie stanu zaczynającym się od cyfry 4, dla którego nie jest dostępny bardziej szczegółowy komunikat o błędzie. Jest to błąd po stronie klienta, który występuje w aplikacji Portal firmy w systemie iOS.|
|__Nie można połączyć się z serwerem__ <br>Prawdopodobnie nie udało się nawiązać połączenia. Spróbuj ponownie, a jeśli problem będzie się powtarzać, skontaktuj się z administratorem IT.|Błąd 500|Ten błąd zostanie wyświetlony w przypadku wystąpienia dowolnego błędu o trzycyfrowym kodzie stanu zaczynającym się od cyfry 5, dla którego nie jest dostępny bardziej szczegółowy komunikat o błędzie. Jest to błąd po stronie usługi, który występuje w usłudze Intune.|

### <a name="service-errors"></a>Błędy usługi

|Kod stanu|Szesnastkowy kod błędu|Komunikat o błędzie|
|---------------|--------------------------|-----------------|
|-2016299111|0x87D1B799|Błąd wewnętrzny|
|-2016299112|0x87D1B798|Błąd wewnętrzny|
|-2016300111|0x87D1B3B1|36001: (błąd wewnętrzny)|
|-2016300112|0x87D1B3B0|36000: Skonfigurowano już transmisję w sieci komórkowej|
|-2016301110|0x87D1AFCA|35002: Wiele czcionek w jednym ładunku|
|-2016301111|0x87D1AFC9|35001: Nie można zainstalować czcionek|
|-2016301112|0x87D1AFC8|35000: Nieprawidłowe dane czcionek|
|-2016302109|0x87D1ABE3|34003: Nieprawidłowa nazwa główna protokołu Kerberos|
|-2016302110|0x87D1ABE2|34002: Brak nazwy głównej protokołu Kerberos|
|-2016302111|0x87D1ABE1|34001: Nieprawidłowy wzorzec dopasowywania adresów URL|
|-2016302112|0x87D1ABE0|34000: Nieprawidłowy wzorzec dopasowywania identyfikatorów aplikacji|
|-2016304112|0x87D1A410|32000: Zbyt wiele aplikacji|
|-2016305111|0x87D1A029|31001: Nie można zastosować ustawień|
|-2016305112|0x87D1A028|31000: Nie można zastosować poświadczeń|
|-2016306111|0x87D19C41|30001: Upłynął limit czasu|
|-2016306112|0x87D19C40|30000: Uwierzytelnianie nie powiodło się|
|-2016307109|0x87D1985B|29003: Nieodpowiednie dane certyfikatu|
|-2016307110|0x87D1985A|29002:|
|-2016307111|0x87D19859|29001:|
|-2016307112|0x87D19858|29000: Urządzenie nie jest nadzorowane|
|-2016308110|0x87D19472|28002: Nie można ustawić tapety|
|-2016308111|0x87D19471|28001: Nieodpowiedni obraz tapety|
|-2016308112|0x87D19470|28000: Nieznany element|
|-2016310111|0x87D18CA1|26001: Szyfrowanie na poziomie plików nie jest obsługiwane|
|-2016310112|0x87D18CA0|26000: Szyfrowanie na poziomie bloków nie jest obsługiwane|
|-2016311110|0x87D188BA|25002: Nie można usunąć|
|-2016311111|0x87D188B9|25001: Nie można zainstalować|
|-2016311112|0x87D188B8|25000: Nieodpowiedni profil|
|-2016312109|0x87D184D3|24003: Nieodpowiedni profil ostateczny|
|-2016312110|0x87D184D2|24002: Nieodpowiednia tożsamość ładunku|
|-2016312111|0x87D184D1|24001: Nie można podpisać słownika atrybutów|
|-2016312112|0x87D184D0|24000: Nie można utworzyć słownika atrybutów|
|-2016313110|0x87D180EA|23002: Nieprawidłowy certyfikat serwera|
|-2016313111|0x87D180E9|23001: Nieodpowiednia odpowiedź serwera|
|-2016313112|0x87D180E8|23000: Nieodpowiednia tożsamość|
|-2016314099|0x87D17D0D|22013: Nieprawidłowa odpowiedź operacji PKIOperation|
|-2016314100|0x87D17D0C|22012: Nie można zapisać certyfikatu CACertificate|
|-2016314101|0x87D17D0B|22011: Nie można wygenerować żądania CSR|
|-2016314102|0x87D17D0A|22010: Nie można zapisać tożsamości tymczasowej|
|-2016314103|0x87D17D09|22009: Nie można utworzyć tożsamości tymczasowej|
|-2016314104|0x87D17D08|22008: Nie można utworzyć tożsamości|
|-2016314105|0x87D17D07|22007: Nieprawidłowy certyfikat z podpisem|
|-2016314106|0x87D17D06|22006: Niewystarczające dane CACaps|
|-2016314107|0x87D17D05|22005: Błąd sieci|
|-2016314108|0x87D17D04|22004: Nieobsługiwana konfiguracja certyfikatów|
|-2016314109|0x87D17D03|22003: Nieprawidłowa odpowiedź RAResponse|
|-2016314110|0x87D17D02|22002: Nieprawidłowa odpowiedź CAResponse|
|-2016314111|0x87D17D01|22001: Nie można wygenerować pary kluczy|
|-2016314112|0x87D17D00|22000: Nieprawidłowe użycie klucza|
|-2016315105|0x87D1791F|21007: Nie można zweryfikować konta|
|-2016315106|0x87D1791E|21006: Nie można odszyfrować certyfikatu|
|-2016315107|0x87D1791D|21005: Konto nie jest unikatowe (profil poczty e-mail już istnieje na urządzeniu)|
|-2016315108|0x87D1791C|21004: Nie można utworzyć konta|
|-2016315109|0x87D1791B|21003: Brak nazwy hosta|
|-2016315110|0x87D1791A|21002: Nie można zachować zgodności z zasadami szyfrowania pochodzącymi z serwera|
|-2016315111|0x87D17919|21001: Nie można zachować zgodności z zasadami pochodzącymi z serwera|
|-2016315112|0x87D17918|21000: Nie można pobrać zasad z serwera|
|-2016316110|0x87D17532|20002: Konto nie jest unikatowe|
|-2016316111|0x87D17531|20001: Brak nazwy hosta|
|-2016316112|0x87D17530|20000: Nie można utworzyć konta|
|-2016317110|0x87D1714A|19002: Konto nie jest unikatowe|
|-2016317111|0x87D17149|19001: Brak nazwy hosta|
|-2016317112|0x87D17148|19000: Nie można utworzyć konta|
|-2016318110|0x87D16D62|18002: Nieprawidłowe poświadczenia|
|-2016318111|0x87D16D61|18001: Host jest nieosiągalny|
|-2016318112|0x87D16D60|18000: Nieznany błąd|
|-2016319110|0x87D1697A|17002: Konto nie jest unikatowe|
|-2016319111|0x87D16979|17001: Brak nazwy hosta|
|-2016319112|0x87D16978|17000: Nie można utworzyć konta|
|-2016320110|0x87D16592|16002: Konto nie jest unikatowe|
|-2016320111|0x87D16591|16001: Brak nazwy hosta|
|-2016320112|0x87D16590|16000: Nie można utworzyć subskrypcji|
|-2016321109|0x87D161AB|15003: Nieprawidłowy certyfikat|
|-2016321110|0x87D161AA|15002: Nie można zablokować konfiguracji sieciowej|
|-2016321111|0x87D161A9|15001: Nie można usunąć sieci VPN|
|-2016321112|0x87D161A8|15000: Nie można zainstalować sieci VPN|
|-2016322110|0x87D15DC2|14002: Istnieje już konfiguracja chmury|
|-2016322111|0x87D15DC1|14001: Urządzenie zablokowane|
|-2016322112|0x87D15DC0|14000: Nieprawidłowe pole|
|-2016323107|0x87D159DD|13005: Nie można skonfigurować serwera proxy|
|-2016323108|0x87D159DC|13004: Nie można skonfigurować protokołu EAP|
|-2016323109|0x87D159DB|13003: Nie można utworzyć konfiguracji sieci WiFi|
|-2016323110|0x87D159DA|13002: Wymagane jest hasło|
|-2016323111|0x87D159D9|13001: Wymagana jest nazwa użytkownika|
|-2016323112|0x87D159D8|13000: Nie można zainstalować|
|-2016324070|0x87D1561A|12042: Nieznany kod ustawień regionalnych|
|-2016324071|0x87D15619|12041: Nieznany kod języka|
|-2016324072|0x87D15618|12040: Jest wymagana nazwa logowania sklepu iTunes|
|-2016324073|0x87D15617|12039: (nieużywane)|
|-2016324074|0x87D15616|12038: Aplikacja nie jest zarządzana|
|-2016324075|0x87D15615|12037: Nieprawidłowy kod realizacji|
|-2016324076|0x87D15614|12036: Nie można usunąć aplikacji w bieżącym stanie|
|-2016324077|0x87D15613|12035: Nie można kupić aplikacji|
|-2016324078|0x87D15612|12034: Adres URL nie jest typu HTTPS|
|-2016324079|0x87D15611|12033: Nieprawidłowy manifest|
|-2016324080|0x87D15610|12032: Zbyt wiele aplikacji w manifeście|
|-2016324081|0x87D1560F|12031: Wyłączono instalację aplikacji|
|-2016324082|0x87D1560E|12030: Nieprawidłowy adres URL|
|-2016324083|0x87D1560D|12029: Aplikacja nie jest zarządzana|
|-2016324084|0x87D1560C|12028: Bez oczekiwania na realizację|
|-2016324085|0x87D1560B|12027: To nie jest aplikacja|
|-2016324086|0x87D1560A|12026: Aplikację dodano już do kolejki|
|-2016324087|0x87D15609|12025: Aplikację już zainstalowano|
|-2016324088|0x87D15608|12024: Nie można zweryfikować manifestu aplikacji|
|-2016324089|0x87D15607|12023: Nie można zweryfikować identyfikatora aplikacji|
|-2016324090|0x87D15606|12022: Nieprawidłowy temat|
|-2016324091|0x87D15605|12021: Nieprawidłowy typ żądania|
|-2016324092|0x87D15604|12020: Brak autoryzacji na serwerze|
|-2016324093|0x87D15603|12019: Nie można skopiować klucza tajnego depozytu|
|-2016324094|0x87D15602|12018: Nie można skopiować danych zbioru kluczy depozytu|
|-2016324095|0x87D15601|12017: Nie można utworzyć zbioru kluczy depozytu|
|-2016324096|0x87D15600|12016: Brak tożsamości|
|-2016324097|0x87D155FF|12015: Nie można uzyskać tokenu wypychania|
|-2016324098|0x87D155FE|12014: Profil informacyjny nie jest zarządzany|
|-2016324099|0x87D155FD|12013: Profil nie jest zarządzany|
|-2016324100|0x87D155FC|12012: Niezgodność dotycząca zamiany MDM|
|-2016324101|0x87D155FB|12011: Nieprawidłowa konfiguracja usługi MDM|
|-2016324102|0x87D155FA|12010: Wewnętrzny błąd niespójności|
|-2016324103|0x87D155F9|12009: Nieprawidłowy profil zastępczy|
|-2016324104|0x87D155F8|12008: Źle sformułowane żądanie|
|-2016324105|0x87D155F7|12007: Brak autoryzacji|
|-2016324106|0x87D155F6|12006: Odmowa przekierowania|
|-2016324107|0x87D155F5|12005: Nie można odnaleźć certyfikatu|
|-2016324108|0x87D155F4|12004: Nieprawidłowy certyfikat wypychania|
|-2016324109|0x87D155F3|12003: Nieprawidłowa odpowiedź na test|
|-2016324110|0x87D155F2|12002: Nie można zaewidencjonować|
|-2016324111|0x87D155F1|12001: Wiele wystąpień usługi MDM|
|-2016324112|0x87D155F0|12000: Nieprawidłowe prawa dostępu|
|-2016325111|0x87D15209|11001: Zainstalowano już niestandardowy element APN|
|-2016325112|0x87D15208|11000: Nie można zainstalować elementu APN|
|-2016326111|0x87D14E21|10001: Nieprawidłowy podpisujący|
|-2016326112|0x87D14E20|10000: Nie można zainstalować elementów domyślnych|
|-2016327106|0x87D14A3E|9006: Certyfikat nie jest tożsamością|
|-2016327107|0x87D14A3D|9005: Certyfikat jest źle sformułowany|
|-2016327108|0x87D14A3C|9004: Nie można zapisać certyfikatu głównego|
|-2016327109|0x87D14A3B|9003: Nie można zapisać danych WAPI|
|-2016327110|0x87D14A3A|9002: Nie można zapisać certyfikatu|
|-2016327111|0x87D14A39|9001: Zbyt wiele certyfikatów w ładunku|
|-2016327112|0x87D14A38|9000: Nieprawidłowe hasło|
|-2016328112|0x87D14650|8000: Nie można zainstalować składnika Web Clip|
|-2016329105|0x87D1426F|7007: Konto SMTP jest błędnie skonfigurowane|
|-2016329106|0x87D1426E|7006: Konto POP jest błędnie skonfigurowane|
|-2016329107|0x87D1426D|7005: Konto IMAP jest błędnie skonfigurowane|
|-2016329108|0x87D1426C|7004: Certyfikat SMIME jest nieodpowiedni|
|-2016329109|0x87D1426B|7003: Nie można odnaleźć certyfikatu SMIME|
|-2016329110|0x87D1426A|7002: W trakcie weryfikacji wystąpił nieznany błąd|
|-2016329111|0x87D14269|7001: Nieprawidłowe poświadczenia|
|-2016329112|0x87D14268|7000: Host jest nieosiągalny|
|-2016330110|0x87D13E82|6002: Nie można utworzyć zapytania|
|-2016330111|0x87D13E81|6001: Pusty ciąg|
|-2016330112|0x87D13E80|6000: Błąd systemu łańcucha kluczy|
|-2016331097|0x87D13AA7|5015: Nie można ustawić okresu prolongaty|
|-2016331098|0x87D13AA6|5014: Nie można ustawić kodu dostępu|
|-2016331099|0x87D13AA5|5013: nie można wyczyścić kodu dostępu|
|-2016331100|0x87D13AA4|5012: (nieużywane)|
|-2016331101||5011: Nieodpowiedni kod dostępu|
|-2016331102||5010: Urządzenie zablokowane|
|-2016331103|0x87D13AA4|5009: (nieużywane)|
|-2016331104|0x87D13AA0|5008: Kod dostępu jest zbyt nowy|
|-2016331105|0x87D13A9F|5007: Kod dostępu wygasł|
|-2016331106|0x87D13AA3|5006: Kod dostępu musi zawierać znaki alfanumeryczne|
|-2016331107|0x87D13A9D|5005: Kod dostępu musi zawierać cyfrę|
|-2016331108|0x87D13A9C|5004: Kod dostępu zawiera znaki w porządku rosnącym/malejącym|
|-2016331109|0x87D13A9B|5003: Kod dostępu zawiera powtarzające się znaki|
|-2016331110|0x87D13A9A|5002: Zbyt mało znaków złożonych|
|-2016331111|0x87D13A99|5001: Zbyt mało znaków unikatowych|
|-2016331112|0x87D13A98|5000: Kod dostępu jest za krótki|
|-2016332093|0x87D136C3|4019: Wiele ładunków blokad aplikacji|
|-2016332094|0x87D136C2|4018: Wiele ładunków APN lub transmisji w sieci komórkowej|
|-2016332095|0x87D136C1|4017: Wiele ładunków globalnych HTTPProxy|
|-2016332096|0x87D136C0|4016: (błąd wewnętrzny)|
|-2016332097|0x87D136BF|4015: Profil zastępczy nie zawiera żadnych ładunków MDM|
|-2016332098|0x87D136BE|4014: Brak dostępnej tożsamości urządzenia|
|-2016332099|0x87D136BD|4013: Aktualizacja nie powiodła się|
|-2016332100|0x87D136BC|4012: Profil nie nadaje się do zaktualizowania|
|-2016332101|0x87D136BB|4011: Profil ostateczny nie jest profilem konfiguracji|
|-2016332102|0x87D136BA|4010: Profil zaktualizowany nie ma tego samego identyfikatora|
|-2016332103|0x87D136B9|4009: Urządzenie zablokowane|
|-2016332104|0x87D136B8|4008: Niezgodność certyfikatów|
|-2016332105|0x87D136B7|4007: Nierozpoznany format pliku|
|-2016332106|0x87D136B6|4006: Data usunięcia profilu przypada w przeszłości|
|-2016332107|0x87D136B5|4005: Kod dostępu nie spełnia warunków|
|-2016332108|0x87D136B4|4004: Użytkownik anulował instalację|
|-2016332109|0x87D136B3|4003: Profilu nie dodano do kolejki w celu zainstalowania|
|-2016332110|0x87D136B2|4002: Zduplikowany identyfikator UUID|
|-2016332111|0x87D136B1|4001: Niepowodzenie instalacji|
|-2016332112|0x87D136B0|4000: Nie można przeanalizować profilu|
|-2016333111|0x87D132C9|3001: Wykryto niespójne porównanie wartości (błąd wewnętrzny)|
|-2016333112|0x87D132C8|3000: Wykryto niespójne ograniczenie (błąd wewnętrzny)|
|-2016334108|0x87D12EE4|2004: Nieobsługiwana wartość pola|
|-2016334109|0x87D12EE3|2003: Nieodpowiedni typ danych w polu|
|-2016334110|0x87D12EE2|2002: Brak pola wymaganego|
|-2016334111|0x87D12EE1|2001: Nieobsługiwana wersja ładunku|
|-2016334112|0x87D12EE0|2000: Źle sformułowany ładunek|
|-2016335102|0x87D12B02|1010: Nieobsługiwana wartość pola|
|-2016335103|0x87D12B01|1009: Niepowodzenie instalacji profilu|
|-2016335104|0x87D12B00|1008: Identyfikatory ładunków nie są unikatowe|
|-2016335105|0x87D12AFF|1007: Identyfikatory UUID nie są unikatowe|
|-2016335106|0x87D12AFE|1006: Nie można odszyfrować|
|-2016335107|0x87D12AFD|1005: Pusty profil|
|-2016335108|0x87D12AFC|1004: Błędny podpis|
|-2016335109|0x87D12AFB|1003: Nieodpowiedni typ danych w polu|
|-2016335110|0x87D12AFA|1002: Brak pola wymaganego|
|-2016335111|0x87D12AF9|1001: Nieobsługiwana wersja profilu|
|-2016335112|0x87D12AF8|1000: Źle sformułowany profil|

## <a name="oma-response-codes"></a>Kody odpowiedzi OMA

|Kod stanu|Szesnastkowy kod błędu|Komunikat o błędzie|
|---------------|--------------------------|-----------------|
|-2016344008|0x87D10838|(1404): odmowa dostępu do certyfikatu|
|-2016344009|0x87D10837|(1403): nie znaleziono certyfikatu|
|-2016344010|0x87D10836|DCMO(1402): operacja nie powiodła się|
|-2016344011|0x87D10835|DCMO(1401): użytkownik nie zaakceptował operacji po wyświetleniu monitu|
|-2016344012|0x87D10834|DCMO(1400): błąd klienta|
|-2016344108|0x87D107D4|DCMO(1204): możliwość urządzenia jest wyłączona, a użytkownik może ją ponownie włączyć|
|-2016344109|0x87D107D3|DCMO(1203): możliwość urządzenia jest wyłączona, a użytkownik nie może jej ponownie włączyć|
|-2016344110|0x87D107D2|DCMO(1202): operacja włączania została wykonana pomyślnie, ale możliwość urządzenia jest aktualnie odłączona|
|-2016344111|0xF3FB4D95|DCMO(1201): operacja włączania została wykonana pomyślnie, a możliwość urządzenia jest aktualnie dołączona|
|-2016344112|0x87D107D0|DCMO(1200): operacja została wykonana pomyślnie|
|-2016345595|0x87D10205|Syncml(517): odpowiedź na niepodzielne polecenie była zbyt duża, aby zmieścić ją w pojedynczym komunikacie.|
|-2016345596|0x87D10204|Syncml(516): polecenie znajdowało się wewnątrz niepodzielnego elementu, dla którego wystąpiło niepowodzenie. To polecenie nie zostało wycofane pomyślnie.|
|-2016345598|0x87D10202|Syncml(514): polecenie SyncML nie zostało zakończone pomyślnie, ponieważ operacja została już anulowana przed przetworzeniem polecenia.|
|-2016345599|0x87D10201|Syncml(513): odbiorca nie obsługuje lub odmawia obsługi określonej wersji protokołu synchronizacji SyncML użytej w komunikacie SyncML żądania.|
|-2016345600|0x87D10200|Syncml(512): podczas sesji synchronizacji wystąpił błąd aplikacji.|
|-2016345601|0x87D101FF|Syncml(511): podczas przetwarzania żądania wystąpił poważny błąd na serwerze.|
|-2016345602|0x87D101FE|Syncml(510): podczas przetwarzania żądania wystąpił błąd. Błąd jest związany z błędem w magazynie danych odbiorcy.|
|-2016345603|0x87D101FD|Syncml(509): zarezerwowany do użytku w przyszłości.|
|-2016345604|0x87D101FC|Syncml(508): wystąpił błąd wymagający odświeżenia bieżącego stanu synchronizacji klienta z serwerem.|
|-2016345605|0x87D101FB|Syncml(507): błąd spowodował niepowodzenie wszystkich poleceń SyncML w elemencie o typie niepodzielnym.|
|-2016345606|0x87D101FA|Syncml(506): podczas przetwarzania żądania wystąpił błąd aplikacji.|
|-2016345607|0x87D101F9|Syncml(505): odbiorca nie obsługuje lub odmawia obsługi określonej wersji schematu DTD SyncML użytego w komunikacie SyncML żądania.|
|-2016345608|=0x87D101F8|Syncml(504): odbiorca, który działa jako brama lub serwer proxy, nie otrzymał terminowo odpowiedzi od nadrzędnego odbiorcy określonego przez identyfikator URI (np. HTTP, FTP, LDAP) lub innego odbiorcy dodatkowego (np. DNS), do którego musiał uzyskać dostęp podczas próby wykonania żądania.|
|-2016345609|0x87D101F7|Syncml(503): odbiorca nie może obecnie obsłużyć żądania ze względu na tymczasowe przeciążenie lub konserwację odbiorcy.|
|-2016345610|0x87D101F6|Syncml(502): odbiorca podczas działania jako brama lub serwer proxy otrzymał nieprawidłową odpowiedź od nadrzędnego serwera, do którego uzyskiwał dostęp podczas próby wykonania żądania.|
|-2016345611|0x87D101F5|Syncml(501): odbiorca nie obsługuje polecenia wymaganego do wykonania żądania.|
|-2016345612|0x87D101F4|Syncml(500): odbiorca napotkał nieoczekiwany warunek, który uniemożliwił mu wykonanie żądania|
|-2016345684|0x87D101AC|Syncml(428): przenoszenie nie powiodło się|
|-2016345685|0x87D101AB|Syncml(427): nie można usunąć elementu nadrzędnego, ponieważ zawiera elementy podrzędne.|
|-2016345686|0x87D101AA|Syncml(426): nie zaakceptowano częściowego elementu.|
|-2016345687|0x87D101A9|Syncml(425): żądane polecenie nie powiodło się, ponieważ nadawca nie ma wystarczających uprawnień kontroli dostępu na odbiorcy.|
|-2016345688|0x87D101A8|Syncml(424): odebrano podzielony obiekt, ale rozmiar odebranego obiektu nie był zgodny z rozmiarem zadeklarowanym w pierwszym fragmencie.|
|-2016345689|0x87D101A7|Syncml(423): żądane polecenie nie powiodło się, ponieważ usunięty wstępnie element został wcześniej całkowicie usunięty na serwerze.|
|-2016345690|0x87D101A6|Syncml(422): żądane polecenie nie powiodło się na serwerze, ponieważ skrypt CGI w identyfikatorze LocURI był niepoprawnie uformowany.|
|-2016345691|0x87D101A5|Syncml(421): żądane polecenie nie powiodło się na serwerze, ponieważ określona gramatyka wyszukiwania jest nieznana.|
|-2016345692|0x87D101A4|Syncml(420): odbiorca nie ma więcej miejsca w magazynie dla pozostałych danych synchronizacji.|
|-2016345693|0x87D101A3|Syncml(419): żądanie klienta spowodowało powstanie konfliktu, który został rozwiązany przez określenie pierwszeństwa polecenia serwera.|
|-2016345694|0x87D101A2|Syncml(418): żądane polecenie Put lub Add nie powiodło się, ponieważ element docelowy już istnieje.|
|-2016345695|0x87D101A1|Syncml(417): żądanie nie powiodło się w tym momencie, a osoba tworząca powinna ponowić żądanie w późniejszym momencie.|
|-2016345696|0x87D101A0|Syncml(416): żądanie nie powiodło się, ponieważ określony w żądaniu rozmiar w bajtach był zbyt duży.|
|-2016345697|0x87D1019F|Syncml(415): nieobsługiwany typ lub format nośnika.|
|-2016345698|0x87D1019E|Syncml(414): żądane polecenie nie powiodło się, ponieważ identyfikator URI elementu docelowego jest zbyt długi i odbiorca nie może lub nie chce go przetworzyć.|
|-2016345699|0x87D1019D|Syncml(413): odbiorca odmawia wykonania żądanego polecenia, ponieważ żądany element jest zbyt duży, aby możliwe było jego przetworzenie przez odbiorcę.|
|-2016345700|0x87D1019C|Syncml(412): żądane polecenie nie powiodło się na odbiorcy, ponieważ było niekompletne lub niepoprawnie uformowane.|
|-2016345701|0x87D1019B|Syncml(411): żądanemu poleceniu musi towarzyszyć rozmiar w bajtach lub informacje o długości w typie elementu Meta.|
|-2016345702|0x87D1019A|Syncml(410): żądany element docelowy nie znajduje się już na odbiorcy i nie jest znany identyfikator URI przekazywania.|
|-2016345703|0x87D10199|Syncml(409): żądanie nie powiodło się ze względu na konflikt aktualizacji między wersjami danych klienta i serwera.|
|-2016345704|0x87D10198|Syncml(408): nie odebrano oczekiwanego komunikatu w wymaganym czasie.|
|-2016345705|0x87D10197|Syncml(407): żądane polecenie nie powiodło się, ponieważ przy jego uruchomieniu musi zostać określone właściwe uwierzytelnienie.|
|-2016345706|0x87D10196|Syncml(406): żądane polecenie nie powiodło się, ponieważ opcjonalna funkcja w żądaniu nie jest obsługiwana.|
|-2016345707|0x87D10195|Syncml(405): żądane polecenie nie jest dozwolone dla elementu docelowego.|
|-2016345708|0x87D10194|Syncml(404): nie znaleziono żądanego elementu docelowego.|
|-2016345709|0x87D10193|Syncml(403): żądane polecenie nie powiodło się, ale odbiorca zrozumiał to polecenie.|
|-2016345710|0x87D10192|Syncml(402): żądane polecenie nie powiodło się, ponieważ wymagana jest właściwa płatność.|
|-2016345711|0x87D10191|Syncml(401): żądane polecenie nie powiodło się, ponieważ obiekt żądający musi określić właściwe uwierzytelnienie.|
|-2016345712|0x87D10190|Syncml(400): nie można wykonać żądanego polecenia ze względu na nieprawidłowo uformowaną składnię w poleceniu.|
|-2016345807|0x87D10131|Syncml(305): dostęp do żądanego elementu docelowego należy uzyskać przy użyciu określonego identyfikatora URI serwera proxy.|
|-2016345808|0x87D10130|Syncml(304): Żądane polecenie SyncML nie zostało wykonane na elemencie docelowym.|
|-2016345809|0x87D1012F|Syncml(303): żądany element docelowy można znaleźć pod innym identyfikatorem URI.|
|-2016345810|0x87D1012E|Syncml(302): żądany element docelowy został tymczasowo przeniesiony pod inny identyfikator URI.|
|-2016345811|0x87D1012D|Syncml(301): żądany element docelowy ma nowy identyfikator URI.|
|-2016345812|0x87D1012C|Syncml(300): żądany element docelowy stanowi jedną z wielu alternatyw żądanego elementu docelowego.|
|-2016345896|0x87D100D8|Syncml(216): polecenie znajdowało się wewnątrz niepodzielnego elementu, dla którego wystąpił błąd. To polecenie zostało pomyślnie wycofane.|
|-2016345897|0x87D100D7|Syncml(215): polecenie nie zostało wykonane w wyniku interakcji z użytkownikiem, który nie zaakceptował wyboru.|
|-2016345898|0x87D100D6|Syncml(214): operacja została anulowana. Polecenie SyncML zostało wykonane pomyślnie, ale żadne kolejne polecenia nie będą przetwarzane w ramach sesji.|
|-2016345899|0x87D100D5|Syncml(213): podzielony element został zaakceptowany i zbuforowany|
|-2016345900|0x87D100D4|Syncml(212): uwierzytelnianie zostało zaakceptowane. Żadne inne uwierzytelnianie nie jest potrzebne w pozostałej części sesji synchronizacji. Tego kodu odpowiedzi można użyć tylko w odpowiedzi na żądanie, w którym podano poświadczenia.|
|-2016345901|0x87D100D3|Syncml(211): element nie został usunięty. Nie znaleziono żądanego elementu. Być może został usunięty wcześniej.|
|-2016345902|0x87D100D2|Syncml(210): usunięcie bez archiwizacji. Odpowiedź wskazuje, że żądane dane zostały pomyślnie usunięte, ale nie zostały zarchiwizowane przed usunięciem, ponieważ ta funkcja OPCJONALNA nie jest obsługiwana przez implementację.|
|-2016345903|0x87D100D1|Konflikt został rozwiązany za pomocą duplikatu. Odpowiedź wskazuje, że żądanie spowodowało konflikt aktualizacji, który został rozwiązany przez zduplikowanie danych klienta w bazie danych serwera. Odpowiedź zawiera docelowy identyfikator URI duplikatu w elemencie stanu. Dodatkowo w przypadku synchronizacji dwukierunkowej zostało zwrócone polecenie Add z definicją danych duplikatu.|
|-2016345904|0x87D100D0|Konflikt został rozwiązany przez zastosowanie polecenia klienta. Odpowiedź wskazuje, że wystąpił konflikt aktualizacji, który został rozwiązany przez nadanie pierwszeństwa poleceniu klienta.|
|-2016345905|0x87D100CF|Konflikt został rozwiązany przez scalenie. Odpowiedź wskazuje, że żądanie spowodowało wystąpienie konfliktu, który został rozwiązany przez scalenie wystąpień danych klienta i serwera. Odpowiedź zawiera docelowy i źródłowy adres URL w elemencie stanu. Dodatkowo zostało zwrócone polecenie Replace ze scalonymi danymi.|
|-2016345906|0x87D100CE|Odpowiedź wskazuje, że tylko część polecenia została wykonana. Jeśli pozostałą część polecenia można wykonać później, NALEŻY utworzyć kolejny odpowiedni kod stanu wykonania żądania po zakończeniu polecenia.|
|-2016345907|0x87D100CD|Źródło POWINNO zaktualizować swoją zawartość. Nadawca żądania otrzymał informację, że jego zawartość POWINNA zostać zsynchronizowana w celu pobrania aktualnej wersji.|
|-2016345908|0x87D100CC|Żądanie zostało wykonane pomyślnie, ale żadne dane nie zostały zwrócone. Kod odpowiedzi jest także zwracany w odpowiedzi na polecenie Get, jeśli element docelowy nie miał zawartości.|
|-2016345909|0x87D100CB|Odpowiedź nieautorytatywna. Odpowiedzi na żądanie udziela jednostka inna niż docelowa. Odpowiedź jest zwracana tylko wtedy, jeśli autorytatywny element docelowy odpowiedziałby na żądanie kodem odpowiedzi 200.|
|-2016345910|0x87D100CA|Zaakceptowano do przetwarzania. Żądanie uruchomienia zdalnego wykonania aplikacji lub poinformowania użytkownika albo aplikacji zostało wykonane pomyślnie.|
|-2016345911|0x87D100C9|Element żądania został dodany.|
|-2016345912|0x87D100C8|Polecenie SyncML zostało wykonane pomyślnie.|
|-2016346011|0x87D10065|Trwa wykonywanie określonego polecenia SyncML, ale polecenie nie zostało jeszcze zakończone.|

## <a name="next-steps"></a>Następne kroki

Skontaktuj się z pomocą techniczną firmy Microsoft, aby [uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](../get-support.md).
