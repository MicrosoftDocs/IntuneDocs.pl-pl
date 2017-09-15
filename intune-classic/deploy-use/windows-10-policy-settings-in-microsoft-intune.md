---
title: Ustawienia zasad systemu Windows 10
description: "Ustawienia zasad wymienione w tym temacie ułatwiają konfigurowanie wbudowanych i niestandardowych ustawień dla zarejestrowanych urządzeń z systemem Windows 10 Desktop lub Windows 10 Mobile."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1f19b7e9d57350f90baca96562a99b2fde66f91a
ms.sourcegitcommit: 00352501833818a08479758ba1c9efdf7223e264
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2017
---
# <a name="intune-policy-settings-for-windows-10-devices-in-microsoft-intune"></a>Ustawienia zasad usługi Intune dla urządzeń z systemem Windows 10 w usłudze Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ten temat zawiera informacje ułatwiające zrozumienie ustawień zasad usługi Intune, których można użyć do zarządzania urządzeniami z systemem Windows 10. Z tym tematem zapoznawaj się wraz z procedurami w temacie [Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](/intune-classic/get-started/windows-pc-management-capabilities-in-microsoft-intune).

Można wybrać spośród dwóch typów zasad:

- **Zasady niestandardowe**: **zasady niestandardowe**  usługi Microsoft Intune dla systemów Windows 10 i Windows 10 Mobile umożliwiają wdrożenie ustawień OMA-URI (Open Mobile Alliance Uniform Resource Identifier), których można użyć do sterowania funkcjami na urządzeniach. System Windows 10 zapewnia dostęp do wielu ustawień dostawcy usług konfiguracji, np. [Dostawca usługi konfiguracji zasad](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
- **Ogólne zasady konfiguracji**: użyj tego typu zasad, aby wybrać ustawienia z wbudowanej listy dostarczonej z usługą Microsoft Intune.

## <a name="custom-policy-settings"></a>Ustawienia zasad niestandardowych

Podaj następujące ustawienia w przypadku zasad niestandardowych.

### <a name="general-settings"></a>Ustawienia ogólne

Wprowadź nazwę i opcjonalny opis zasad, aby ułatwić ich identyfikację w konsoli usługi Intune.

### <a name="oma-uri-settings"></a>Ustawienia OMA-URI

Dla każdego ustawienia OMA-URI, które chcesz dodać, wprowadź następujące informacje:

- **Nazwa ustawienia**: wprowadź unikatową nazwę dla ustawienia OMA-URI, aby ułatwić jego identyfikację na liście ustawień. Więcej informacji na temat ustawień identyfikatora URI można znaleźć w artykule [Dostawca usługi konfiguracji zasad](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
- **Opis ustawienia**: opcjonalnie wprowadź opis ustawienia.
- **Typ danych**: wybierz jeden z następujących typów danych:
    - **Ciąg**
    - **Ciąg (XML)**
    - **Data i godzina**
    - **Liczba całkowita**
    - **Liczba zmiennoprzecinkowa**
    - **Wartość logiczna**
- **OMA-URI (z uwzględnieniem wielkości liter)**: określ identyfikator OMA-URI, dla którego chcesz podać ustawienie.
- **Wartość**: określ wartość, która będzie kojarzona z określonym wcześniej identyfikatorem OMA-URI.

### <a name="example"></a>Przykład
Na poniższym zrzucie ekranu ustawienie **Connectivity/AllowVPNOverCellular** jest włączone. Pozwala to urządzeniu z systemem Windows 10 na otwarcie połączenia sieci VPN w sieci komórkowej.

> ![Przykład zasad niestandardowych zawierających ustawienia sieci VPN](./media/custom-policy-example.png)

### <a name="how-to-find-the-policies-you-can-configure"></a>Jak znaleźć zasady, które można skonfigurować

Pełna lista wszystkich dostawców usług konfiguracji (CSP) obsługiwanych w systemie Windows 10 jest przedstawiona w artykule [Configuration service provider reference](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) (Informacje dotyczące dostawcy usługi konfiguracji) w bibliotece dokumentacji systemu Windows.

Nie wszystkie ustawienia są zgodne ze wszystkimi wersjami systemu Windows 10. Table w temacie poświęconym systemowi Windows zawiera informacje o tym, które wersje są obsługiwane w przypadku każdego z dostawców usług konfiguracji.

Ponadto usługa Intune nie obsługuje wszystkich ustawień wymienionych w temacie. Aby dowiedzieć się, czy usługa Intune obsługuje dane ustawienie, otwórz temat dotyczący tego ustawienia. Na stronie każdego ustawienia znajdują się informacje dotyczące obsługiwanych operacji. Aby ustawienie mogło być używane z usługą Intune, musi obsługiwać operacje **Dodaj** lub **Zastąp**.

## <a name="general-configuration-policy-settings"></a>Ustawienia ogólnych zasad konfiguracji

**Ogólne zasady konfiguracji** usługi Microsoft Intune dla systemu Windows 10 umożliwiają konfigurowanie wbudowanych ustawień dla zarejestrowanych urządzeń z systemem Windows 10 Desktop lub Windows 10 Mobile.

### <a name="password"></a>Hasło

|Nazwa ustawienia|Informacje dodatkowe (jeśli są wymagane)|
|----------------|----------------------|
|**Wymagaj hasła w celu odblokowania urządzeń**|-|
|**Wymagany typ hasła**|Określa, czy hasło musi być wyłącznie numeryczne lub alfanumeryczne|
|**Wymagany typ hasła** - **Minimalna liczba zestawów znaków**| Określa, ile zestawów znaków musi być uwzględnionych w haśle (małe litery, wielkie litery, cyfry i symbole)|
|**Minimalna długość hasła**|Dotyczy tylko systemu Windows 10 Mobile|
|**Liczba dopuszczalnych nieudanych logowań przed wyczyszczeniem danych z urządzenia**.|W przypadku urządzeń z systemem Windows 10: jeśli na urządzeniu jest włączona funkcja BitLocker, zostanie ono przełączone do trybu odzyskiwania funkcji BitLocker po określonej liczbie nieudanych prób logowania. Jeśli na urządzeniu nie jest włączona funkcja BitLocker, to ustawienie nie będzie miało zastosowania.<br>Na urządzeniach z systemem Windows 10 Mobile: po określonej liczbie niepowodzeń logowania urządzenie zostanie wyczyszczone.|
|**Czas braku aktywności (w minutach) przed wyłączeniem ekranu**|Określa czas bezczynności urządzenia, po upływie którego ekran jest blokowany|
|**Dni do wygaśnięcia hasła**|Określa czas, po jakim hasło urządzenia musi zostać zmienione|
|**Pamiętaj historię haseł**|Określa, czy należy ograniczyć użytkownikowi możliwość tworzenia poprzednio używanych haseł|
|**Pamiętaj historię haseł** - **Zapobiegaj ponownemu używaniu poprzednich haseł**|Określa liczbę poprzednich haseł, które są zapamiętywane przez urządzenie|
|**Wymagaj hasła po przywróceniu urządzenia ze stanu bezczynności**|Określa, czy użytkownik musi wprowadzić hasło, aby odblokować urządzenie (tylko system Windows 10 Mobile)|

### <a name="encryption"></a>Szyfrowanie

|Nazwa ustawienia|Informacje dodatkowe (jeśli są wymagane)|
|----------------|----------------------|
|**Wymagaj szyfrowania na urządzeniu przenośnym**|Włącza szyfrowanie na urządzeniach docelowych<br>(Tylko Windows 10 Mobile)|

### <a name="system"></a>System

|Nazwa ustawienia|Informacje dodatkowe (jeśli są wymagane)|
|----------------|----------------------|
|**Zezwalaj na przechwytywanie ekranu**|Umożliwia użytkownikowi przechwytywanie ekranu urządzenia w formie obrazu (tylko system Windows 10 Mobile)|
|**Zezwalaj na ręczne wyrejestrowanie**|Umożliwia użytkownikowi ręczne usunięcie z urządzenia konta w miejscu pracy|
|**Zezwalaj na ręczną instalację certyfikatu głównego**|Dotyczy systemu Windows 10 Mobile|
|**Zezwalaj na wysyłanie danych diagnostycznych i danych dotyczących użycia do firmy Microsoft**|Możliwe wartości:<br><br>**Brak** — żadne dane nie są wysyłane do firmy Microsoft<br>**Podstawowe** — ograniczone informacje są wysyłane do firmy Microsoft<br>**Rozszerzone** — rozszerzone dane diagnostyczne są wysyłane do firmy Microsoft<br>**Pełne (zalecane)** — urządzenie wysyła te same dane, które są wysyłane w przypadku opcji **Rozszerzone**, oraz dodatkowe dane dotyczące stanu urządzenia|


### <a name="account-and-synchronization"></a>Konto i synchronizacja

|Nazwa ustawienia|Informacje dodatkowe (jeśli są wymagane)|
|----------------|----------------------|---------------------|
|**Zezwalaj na konto Microsoft**|Zezwala użytkownikowi na skojarzenie konta Microsoft z urządzeniem|
|**Zezwalaj na ręczne dodawanie kont innych niż konta Microsoft**|Zezwala użytkownikowi na dodanie na urządzeniu kont e-mail, które nie są skojarzone z kontem Microsoft|
|**Zezwalaj na synchronizację ustawień kont Microsoft**|Zezwala na synchronizację ustawień urządzenia i aplikacji, które są skojarzone z kontem Microsoft, między urządzeniami|

### <a name="microsoft-edge"></a>Microsoft Edge

|Nazwa ustawienia|Informacje dodatkowe (jeśli są wymagane)|
|----------------|----------------------|
|**Zezwalaj na używanie przeglądarki sieci Web**|Zezwala na korzystanie z przeglądarki Microsoft Edge na urządzeniu<br>(Tylko Windows 10 Mobile)|
|**Zezwalaj na sugestie dotyczące wyszukiwania na pasku adresu**|Umożliwia wyszukiwarce sugerowanie witryn podczas wpisywania fraz do wyszukania|
|**Zezwalaj na wysyłanie ruchu intranetowego do programu Internet Explorer**|Zezwala użytkownikom na otwieranie intranetowych witryn sieci Web w programie Internet Explorer<br>(Tylko Windows 10 Desktop)|
|**Zezwalaj na żądania Nie śledź**|Konfiguruje przeglądarkę Microsoft Edge, aby wysyłała nagłówki „Nie śledź” do witryn sieci Web odwiedzanych przez użytkowników|
|**Włącz filtr SmartScreen**||
|**Zezwalaj na wykonywanie aktywnych skryptów**|Zezwala na uruchamianie skryptów, takich jak skrypty JavaScript, w przeglądarce Edge|
|**Zezwalaj na wyskakujące okienka**|Dotyczy tylko systemu Windows 10 Desktop|
|**Zezwalaj na pliki cookie**||
|**Zezwalaj na automatyczne uzupełnianie**|Umożliwia użytkownikom zmianę ustawień autouzupełniania w przeglądarce<br>(Tylko Windows 10 Desktop)|
|**Zezwalaj na działanie menedżera haseł**|Włącza lub wyłącza funkcję menedżera haseł przeglądarki Microsoft Edge|
|**Lokalizacja listy witryn trybu przedsiębiorstwa**|Określa lokalizację listy witryn, które będą otwierane w trybie przedsiębiorstwa. Użytkownicy nie mogą edytować tej listy.<br>(Tylko Windows 10 Desktop)|

### <a name="apps"></a>Aplikacje

|Nazwa ustawienia|Informacje dodatkowe (jeśli są wymagane)|
|----------------|----------------------|---------------------|
|**Zezwalaj na korzystanie ze sklepu z aplikacjami**|Dotyczy tylko systemu Windows 10 Mobile|



### <a name="cellular"></a>Komórkowe

|Nazwa ustawienia|Informacje dodatkowe (jeśli są wymagane)|
|----------------|----------------------|---------------------|
|**Zezwala na roaming danych**|Umożliwia roaming między sieciami przy dostępie do danych|
|**Zezwalaj na połączenia VPN przez sieć komórkową**|Określa, czy urządzenie może uzyskiwać dostęp do połączeń sieci VPN w przypadku połączenia z siecią komórkową|
|**Zezwalaj na roaming połączeń VPN przez sieć komórkową**|Określa, czy urządzenie może uzyskiwać dostęp do połączeń sieci VPN w przypadku roamingu w sieci komórkowej|

### <a name="hardware"></a>Sprzęt

|Nazwa ustawienia|Informacje dodatkowe (jeśli są wymagane)|
|----------------|----------------------|
|**Zezwalaj na używanie aparatu**|-|
|**Zezwalaj na używanie magazynu wymiennego**|Określa, czy z urządzeniem można używać zewnętrznych urządzeń pamięci masowej, na przykład kart SD|
|**Zezwalaj na połączenia Wi-Fi**|Dotyczy tylko systemu Windows 10 Mobile|
|**Zezwalaj na udostępnianie Internetu**|Zezwala na udostępnianie połączenia internetowego na urządzeniu|
|**Zezwalaj na ręczną konfigurację sieci Wi-Fi**|Określa, czy użytkownik może konfigurować własne połączenia sieci Wi-Fi, czy używać tylko połączeń skonfigurowanych przez profil sieci Wi-Fi<br>(Tylko Windows 10 Mobile)|
|**Zezwalaj na automatyczne łączenie z bezpłatnymi punktami hotspot Wi-Fi**|Umożliwia urządzeniu automatyczne łączenie się z bezpłatnymi hotspotami Wi-Fi oraz automatyczne akceptowanie wszelkich warunków i postanowień związanych z połączeniem|
|**Zezwalaj na używanie funkcji geolokalizacji**|Określa, czy urządzenie może używać informacji z usług lokalizacyjnych|
|**Zezwalaj na komunikację NFC**|Zezwala urządzeniu na korzystanie z funkcji Near Field Communications|
|**Zezwalaj na połączenia Bluetooth**|-|
|**Zezwalaj na tryb wykrywania urządzeń Bluetooth**|Umożliwia wykrycie urządzenia przez inne urządzenia Bluetooth|
|**Zezwalaj na reklamy przez sieć Bluetooth**|Umożliwia urządzeniom odbieranie reklam przez sieć Bluetooth|
|**Zezwalaj na resetowanie telefonu**|Określa, czy użytkownik może resetować urządzenie do ustawień fabrycznych|
|**Zezwalaj na połączenie USB**|Określa, czy urządzenia mają dostęp do zewnętrznych urządzeń pamięci masowej przez połączenie USB|
|**Zezwalaj na tryb antykradzieżowy**|Pozwala określić, czy jest włączony tryb antykradzieżowy systemu Windows|

### <a name="features"></a>Funkcje

|Nazwa ustawienia|Informacje dodatkowe (jeśli są wymagane)|
|----------------|----------------------|---------------------|
|**Zezwalaj na kopiowanie i wklejanie**|Dotyczy tylko systemu Windows 10 Mobile|
|**Zezwalaj na nagrywanie głosu**|Dotyczy tylko systemu Windows 10 Mobile|
|**Zezwalaj na funkcję Cortana**|Włącza lub wyłącza asystenta głosowego Cortana|
|**Zezwalaj na powiadomienia w Centrum akcji**|Włącza lub wyłącza powiadomienia centrum akcji na ekranie blokady urządzenia<br>(Tylko Windows 10 Mobile)|

### <a name="windows-defender"></a>Usługa Windows Defender

Wszystkie ustawienia dotyczą wyłącznie systemu Windows 10 Desktop.

|Nazwa ustawienia|Informacje dodatkowe (jeśli są wymagane)|
|----------------|----------------------|---------------------|
|**Zezwalaj na monitorowanie w czasie rzeczywistym**|Włącza skanowanie w czasie rzeczywistym w poszukiwaniu złośliwego oprogramowania, programów szpiegujących i innego niepożądanego oprogramowania|
|**Zezwalaj na monitorowanie zachowania**|Umożliwia usłudze Defender sprawdzanie określonych wzorców podejrzanej aktywności na urządzeniach|
|**Włącz system inspekcji sieci**|System inspekcji sieci (NIS, Network Inspection System) ułatwia ochronę urządzenia przed atakami sieciowymi wykorzystującymi luki w zabezpieczeniach, używając sygnatur znanych luk w zabezpieczeniach z centrum programu Microsoft Endpoint Protection, co pomaga wykrywać i blokować złośliwy ruch|
|**Skanuj wszystkie pobrane pliki**|Określa, czy usługa Defender skanuje wszystkie pliki pobierane z Internetu|
|**Zezwalaj na skanowanie skryptów**|Umożliwia usłudze Defender skanowanie skryptów używanych przez program Internet Explorer|
|**Monitoruj działania plików i programów**|Zezwala usłudze Defender na monitorowanie działania plików i programów na urządzeniach|
|**Liczba dni śledzenia wykrytego złośliwego oprogramowania**|Umożliwia usłudze Defender kontynuowanie śledzenia wykrytego złośliwego oprogramowania przez podaną liczbę dni, co pozwala ręcznie sprawdzać urządzenia, które wcześniej zostały zainfekowane. Jeśli liczba dni zostanie ustawiona na **0**, złośliwe oprogramowanie pozostanie w folderze kwarantanny i nie będzie automatycznie usuwane. |
|**Zezwalaj na dostęp do interfejsu użytkownika klienta**|Określa, czy interfejs użytkownika programu Windows Defender jest ukryty dla użytkowników.<br>Jeśli to ustawienie zostanie zmienione, zmiany zostaną wprowadzone po następnym ponownym uruchomieniu komputera użytkownika.|
|**Zaplanuj codzienne szybkie skanowanie**|Umożliwia zaplanowanie szybkiego skanowania, które będzie odbywać się codziennie o wybranej porze|
|**Zaplanuj skanowanie systemu**|Umożliwia zaplanowanie pełnego lub szybkiego skanowania systemu wykonywanego regularnie w wybranym dniu o wybranej godzinie|
|**Ogranicz użycie procesora CPU podczas skanowania**|Pozwala ograniczyć moc procesora CPU, jakiej mogą używać procesy skanowania (od **1** do **100**).|
|**Skanuj pliki archiwum**|Zezwala usłudze Defender na skanowanie plików archiwów, na przykład plików zip i cab.|
|**Skanuj wiadomości e-mail**|Zezwala usłudze Defender na skanowanie wiadomości e-mail podczas ich dostarczania do urządzenia|
|**Skanuj dyski wymienne**|Umożliwia usłudze Defender skanowanie dysków wymiennych, na przykład dysków USB|
|**Skanuj zamapowane dyski sieciowe**|Umożliwia usłudze Defender skanowanie plików na zamapowanym dysku sieciowym.<br>Jeśli pliki na dysku są plikami tylko do odczytu, usługa Defender nie będzie mogła usunąć z nich wykrytego złośliwego oprogramowania.|
|**Skanuj pliki otwierane z udostępnionych folderów sieciowych**|Umożliwia usłudze Defender skanowanie plików na udostępnionych dyskach sieciowych (np. dyskach z dostępem za pośrednictwem ścieżki UNC).<br>Jeśli pliki na dysku są plikami tylko do odczytu, usługa Defender nie będzie mogła usunąć z nich wykrytego złośliwego oprogramowania.|
|**Interwał aktualizacji sygnatur**|Określa interwał, z jakim usługa Defender sprawdza dostępność nowych plików sygnatur.|
|**Zezwalaj na ochronę w chmurze**|Zezwala usłudze Microsoft Active Protection na odbieranie informacji o działaniu złośliwego oprogramowania z zarządzanych urządzeń lub blokuje tę możliwość. Te informacje służą ulepszaniu usługi w przyszłości.|
|**Pytaj użytkowników o przesyłane próbki**|Określa, czy do firmy Microsoft są automatycznie wysyłane pliki, które mogą wymagać dalszej analizy ze strony firmy Microsoft w celu określenia, czy są złośliwe|
|**Wykrywanie potencjalnie niechcianych aplikacji**|Chroni zarejestrowane urządzenia stacjonarne z systemem Windows przed uruchamianiem oprogramowania sklasyfikowanego przez program Windows Defender jako potencjalnie niechciane. Można chronić komputery przed uruchamianiem tych aplikacji lub używać trybu inspekcji, aby zgłaszać zdarzenia instalowania potencjalnie niechcianych aplikacji.|
|**Pliki i foldery do wykluczenia w trakcie skanowania lub używania ochrony w czasie rzeczywistym**|Dodaje do listy wykluczeń jeden lub więcej plików i folderów, na przykład **C:\ścieżka** lub **%ProgramFiles%\ścieżka\nazwa_pliku.exe**. Te pliki i foldery nie są uwzględniane podczas skanowania w czasie rzeczywistym ani zaplanowanego skanowania.|
|**Rozszerzenia plików, które mają zostać wykluczone podczas przeprowadzania skanowania lub stosowania ochrony w czasie rzeczywistym**|Dodaj do listy wykluczeń jedno lub więcej rozszerzeń plików, na przykład **jpg** lub **txt**. Żadne pliki z tymi rozszerzeniami nie są uwzględniane podczas skanowania w czasie rzeczywistym ani zaplanowanego skanowania.|
|**Procesy, które mają zostać wykluczone podczas przeprowadzania skanowania lub stosowania ochrony w czasie rzeczywistym**|Dodaje jeden lub więcej procesów typu **exe**, **com** lub **scr** do listy wykluczeń. Te procesy nie są uwzględniane podczas skanowania w czasie rzeczywistym ani zaplanowanego skanowania.|


### <a name="updates"></a>Updates

|Nazwa ustawienia|Informacje dodatkowe (jeśli są wymagane)|
|----------------|---------------|
|**Zezwalaj na aktualizacje automatyczne**|Zezwala na aktualizacje automatyczne. Skonfiguruj jedno z następujących ustawień kontrolowania zachowania aktualizacji:<br />**Powiadamiaj o pobieraniu**<br />**Instaluj automatycznie podczas konserwacji**<br />**Automatycznie instaluj i uruchamiaj ponownie podczas konserwacji**<br />**Automatycznie zainstaluj i uruchom ponownie w zaplanowanym czasie**: Należy pamiętać, że jeśli ta opcja jest wybrana, możesz również skonfigurować następujące ustawienia: **Pomiń powiadamianie użytkownika końcowego** i **Zdefiniuj dzień instalacji zaplanowanych aktualizacji**.<br>(Tylko Windows 10 Desktop)|
|**Zezwalaj na funkcje wersji wstępnej**|Umożliwia firmie Microsoft wdrażanie na urządzeniach z systemem Windows 10 ustawień i funkcji wersji wstępnej. Możesz zezwolić na instalowanie tylko ustawień lub wszystkich ustawień i funkcji wersji wstępnej.|

### <a name="see-also"></a>Zobacz także
[Zarządzanie ustawieniami i funkcjami na urządzeniach przy użyciu zasad usługi Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
