---
title: "Ustawienia zasad zarządzania aplikacjami mobilnymi systemu Android | Microsoft Docs"
description: "W tym temacie opisano ustawienia zasad zarządzania aplikacjami mobilnymi dla urządzeń z systemem Android."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5dbb702a-1df5-4637-95c9-77a5f0b1a0e3
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 33febef8787887401960592d95356347f6917681
ms.openlocfilehash: 017c316ce102b71b3ef9552d8fe69181b79473de
ms.contentlocale: pl-pl
ms.lasthandoff: 05/04/2017


---

# <a name="android-app-protection-policy-settings-in-microsoft-intune"></a>Ustawienia zasad ochrony aplikacji systemu Android w usłudze Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Opisane w tym temacie ustawienia zasad aplikacji można [skonfigurować](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) w bloku **Ustawienia** w witrynie Azure Portal.
Istnieją dwie kategorie ustawień zasad: relokacja danych i dostęp. W tym temacie termin _**aplikacje zarządzane przez zasady**_ dotyczy aplikacji skonfigurowanych przy użyciu zasad ochrony aplikacji.

##  <a name="data-relocation-settings"></a>Ustawienia relokacji danych

| Ustawienie | Sposób użycia | Wartości domyślne |
|------|------|------|
| **Blokuj kopie zapasowe systemu Android** | Wybierz opcję **Tak**, aby uniemożliwić tej aplikacji tworzenie kopii zapasowych danych służbowych w [usłudze kopii zapasowych systemu Android](https://developer.android.com/google/backup/index.html). Wybierz opcję **Nie**, aby umożliwić tej aplikacji tworzenie kopii zapasowych danych służbowych.| Tak |
| **Zezwalaj aplikacji na przesyłanie danych do innych aplikacji** | Określ, które aplikacje mogą odbierać dane z tej aplikacji: <ul><li> **Aplikacje zarządzane przez zasady**: zezwalaj na przesyłanie danych tylko do innych aplikacji zarządzanych przez zasady.</li> <li>**Wszystkie aplikacje**: zezwalaj na przesyłanie danych do wszystkich aplikacji. </li> <li>**Brak**: nie zezwalaj na przesyłanie danych do żadnych aplikacji, w tym również innych aplikacji zarządzanych przez zasady.</li></ul> <p>Istnieją pewne aplikacje i usługi, w przypadku których usługa Intune może zezwolić na przesyłanie danych do tych aplikacji i usług. Sekcja [Wyjątki w transferze danych](#Data-transfer-exemptions) zawiera pełną listę aplikacji i usług.| Wszystkie aplikacje |
| **Zezwalaj aplikacji na odbieranie danych z innych aplikacji** | Określ, jakie aplikacje mogą przesyłać dane do tej aplikacji: <ul><li>**Aplikacje zarządzane przez zasady**: zezwalaj na przesyłanie danych tylko z innych aplikacji zarządzanych przez zasady.</li><li>**Wszystkie aplikacje**: zezwalaj na przesyłanie danych z wszystkich aplikacji.</li><li>**Brak**: nie zezwalaj na przesyłanie danych z żadnych aplikacji, w tym również innych aplikacji zarządzanych przez zasady. </li></ul> <p>Istnieją pewne aplikacje i usługi, w przypadku których usługa Intune może zezwolić na przesyłanie danych z tych aplikacji i usług. Sekcja [Wyjątki w transferze danych](#Data-transfer-exemptions) zawiera pełną listę aplikacji i usług. | Wszystkie aplikacje |
| **Nie zezwalaj na używanie polecenia „Zapisz jako”** | Wybierz opcję **Tak**, aby wyłączyć używanie opcji Zapisz jako w tej aplikacji. Wybierz opcję **Nie**, jeśli chcesz zezwolić na używanie polecenia Zapisz jako. <p><br>**Wybierz, w których usługach magazynu można zapisywać dane firmowe** <br>Użytkownicy będą mogli zapisywać dane w wybranych usługach (OneDrive dla Firm, SharePoint i Magazyn lokalny). Wszystkie pozostałe usługi będą zablokowane.</p> | Nie <br><br> Wybrano 0 |
| **Ogranicz wycinanie, kopiowanie i wklejanie w innych aplikacjach** | Określ, kiedy można używać akcji wycinania, kopiowania i wklejania w tej aplikacji. Wybierz spośród opcji: <ul><li>**Zablokowane**: nie zezwalaj na akcje wycinania, kopiowania i wklejania między tą aplikacją i dowolną inną aplikacją.</li><li>**Aplikacje zarządzane przez zasady**: zezwalaj na akcje wycinania, kopiowania i wklejania między tą aplikacją i innymi aplikacjami zarządzanymi przez zasady.</li><li>**Aplikacje zarządzane przez zasady z funkcją wklejania**: zezwalaj na wycinanie i kopiowanie między tą aplikacją i innymi aplikacjami zarządzanymi przez zasady. Zezwalaj na wklejanie w tej aplikacji danych z dowolnych aplikacji.</li><li>**Dowolna aplikacja**: brak ograniczeń wycinania, kopiowania i wklejania do i z tej aplikacji. | Dowolna aplikacja |
|**Ogranicz zawartość sieci Web do wyświetlenia w programie Managed Browser** | Wybierz opcję **Tak**, aby wymusić otwieranie linków sieci Web w danej aplikacji za pomocą aplikacji Managed Browser. <br><br> W przypadku urządzeń, które nie zostały zarejestrowane w usłudze Intune, linki sieci Web w aplikacjach zarządzanych przez zasady będą otwierane tylko w aplikacji Managed Browser. <br><br> Jeśli używasz usługi Intune do zarządzania swoimi urządzeniami, zobacz [Zarządzanie dostępem do Internetu za pomocą zasad programu Managed Browser w usłudze Microsoft Intune](manage-internet-access-using-managed-browser-policies.md). | Nie |
| **Szyfruj dane aplikacji** | Wybierz opcję **Tak**, aby włączyć szyfrowanie danych służbowych w tej aplikacji. Usługa Intune bezpiecznie szyfruje dane aplikacji przy użyciu schematu 128-bitowego szyfrowania AES i OpenSSL z systemem Android Keystore. Dane są szyfrowane synchronicznie podczas zadań wejścia/wyjścia na plikach. Zawartość w pamięci urządzenia jest zawsze zaszyfrowana. <br><br> Metoda szyfrowania **nie** ma certyfikatu FIPS 140-2.  | Tak |
| **Wyłącz synchronizację kontaktów** | Wybierz opcję **Tak**, aby uniemożliwić aplikacji zapisywanie danych w natywnej aplikacji Kontakty na urządzeniu. Jeśli wybierzesz opcję **Nie**, aplikacja będzie mogła zapisywać dane w natywnej aplikacji Kontakty na urządzeniu. <br><br>Gdy jest wykonywane selektywne czyszczenie danych w celu usunięcia danych służbowych z aplikacji, kontakty zsynchronizowane bezpośrednio z aplikacji do natywnej aplikacji Kontakty są usuwane. Nie można wyczyścić wszystkich kontaktów zsynchronizowanych z natywnej książki adresowej do innego źródła zewnętrznego. Obecnie dotyczy to tylko aplikacji Microsoft Outlook. | Nie |
| **Wyłącz drukowanie** | Wybierz opcję **Tak**, aby uniemożliwić aplikacji drukowanie danych służbowych. | Nie |

  >[!NOTE]
  >Metoda szyfrowania dla ustawienia **Szyfruj dane aplikacji** **nie** ma certyfikatu FIPS 140-2.


  ## <a name="data-transfer-exemptions"></a>Wyjątki w transferze danych

  Istnieją pewne aplikacje i usługi platform, w przypadku których zasady ochrony aplikacji usługi Intune mogą zezwolić na przesyłanie danych z tych aplikacji i usług oraz do nich. Na przykład wszystkie aplikacje obsługujące usługę Intune w systemie Android muszą mieć możliwość przesyłania danych z i do funkcji Zamiana tekstu na mowę Google, aby tekst z ekranu urządzenia przenośnego mógł być odczytywany na głos. Ta lista może ulec zmianom i odzwierciedla usługi oraz aplikacje uważane za przydatne w kwestii bezpieczeństwa wydajności.

  ### <a name="full-exemptions"></a>Pełna lista wyjątków

  Te aplikacje i usługi mogą przesyłać dane z aplikacji zarządzanych przez usługę Intune i do nich bez ograniczeń.

  |Nazwa aplikacji/usługi | Opis |
  | ------ | ---- |
  | com.android.phone | Natywna aplikacja telefoniczna
  | com.android.vending | Sklep Google Play |
  | com.android.documentsui | Android Document Picker|
  | com.google.android.webview | Składnik [WebView](https://developer.android.com/reference/android/webkit/WebView.html), który jest niezbędny dla wielu aplikacji np. Outlook. |
  | com.android.webview |Składnik [WebView](https://developer.android.com/reference/android/webkit/WebView.html), który jest niezbędny dla wielu aplikacji np. Outlook.|
  | com.google.android.tts | Zamiana tekstu na mowę Google |
  | com.android.providers.settings | Ustawienia systemu Android |
  | com.azure.authenticator | Aplikacja Azure Authenticator, która jest niezbędna do pomyślnego uwierzytelniania w wielu scenariuszach. |
  | com.microsoft.windowsintune.companyportal | Intune Portal firmy|

  ### <a name="conditional-exemptions"></a>Wyjątki warunkowe
  Te aplikacje i usługi mogą przesyłać dane z aplikacji zarządzanych przez usługę Intune i do nich pod pewnymi warunkami.

  |Nazwa aplikacji/usługi | Opis | Warunek wyjątku|
  | ------ | ---- | --- |
  | com.android.chrome | Przeglądarka Google Chrome | Przeglądarka Chrome jest używana w niektórych składnikach WebView w systemie Android 7.0+ i nigdy nie jest ukryta. Przepływ danych z aplikacji i do niej jest jednak zawsze ograniczony.
  | com.skype.raider | Skype | Aplikacja Skype jest dozwolona tylko w przypadku niektórych akcji, których wynikiem jest nawiązanie połączenia telefonicznego. |
  | com.android.providers.media | Dostawca zawartości multimedialnej systemu Android | Dostawca zawartości multimedialnej jest dozwolony tylko w przypadku akcji wybierania dzwonka. |
  | com.google.android.gms; com.google.android.gsf | Pakiety usług Google Play | Ta pakiety są dozwolone tylko w przypadku akcji usługi Google Cloud Messaging takich jak powiadomienia wypychane. |



##  <a name="access-settings"></a>Ustawienia dostępu

| Ustawienie | Sposób użycia | Wartości domyślne |
|------|------|------|
| **Wymagaj numeru PIN w celu udzielenia dostępu** | Wybierz opcję **Tak**, aby wymagać numeru PIN do korzystania z tej aplikacji. Użytkownik zostanie poproszony o skonfigurowanie tego numeru PIN przy pierwszym uruchomieniu aplikacji w kontekście służbowym. Wartość domyślna: **Tak**.<br><br> Skonfiguruj następujące ustawienia dotyczące siły numeru PIN: <ul><li>**Liczba prób przed zresetowaniem numeru PIN**: określ liczbę prób wprowadzenia numeru PIN, po której użytkownik musi go zresetować. Wartość domyślna: **5**.</li><li> **Zezwalaj na prosty numer PIN**: wybierz opcję **Tak**, aby zezwolić użytkownikom na stosowanie prostych sekwencji numeru PIN, takich jak 1234 lub 1111. Wybierz opcję **Nie**, aby uniemożliwić im stosowanie prostych sekwencji. Wartość domyślna: **Tak**. </li><li> **Długość numeru PIN**: określ minimalną liczbę cyfr w sekwencji numeru PIN. Wartość domyślna: **4**. </li><li> **Zezwalaj na odcisk palca zamiast numeru PIN (Android 6.0 i nowsze)**: wybierz opcję **Tak**, aby zezwolić użytkownikowi na dostęp do aplikacji za pomocą [uwierzytelniania odciskiem palca](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) zamiast numerem PIN. Wartość domyślna: **Tak**.</li></ul> Na urządzeniach z systemem Android można zezwolić użytkownikowi na potwierdzenie tożsamości za pomocą [uwierzytelniania odciskiem palca w systemie Android](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) zamiast numerem PIN. Gdy użytkownik spróbuje skorzystać z tej aplikacji za pomocą konta służbowego, otrzyma monit o potwierdzenie tożsamości odciskiem palca, a nie numerem PIN. </li></ul>| Wymagaj numeru PIN: tak <br><br> Liczba prób przed zresetowaniem numeru PIN: 5 <br><br> Zezwalaj na prosty numer PIN: tak <br><br> Długość numeru PIN: 4 <br><br> Zezwalaj na odcisk palca: tak |
| **Wymagaj poświadczeń firmowych w celu udzielenia dostępu** | Wybierz opcję **Tak**, aby wymagać od użytkownika logowania się za pomocą konta służbowego zamiast numeru PIN w celu uzyskania dostępu do aplikacji. Wybranie opcji **Tak** przesłania wymagania dotyczące numeru PIN lub funkcji Touch ID.  | Nie |
| **Blokuj uruchamianie aplikacji zarządzanych na urządzeniach, na których zdjęto zabezpieczenia systemu lub uzyskano dostęp do konta root** |Wybierz opcję **Tak**, aby uniemożliwić tej aplikacji działanie na urządzeniach, na których zdjęto zabezpieczenia systemu lub uzyskano dostęp do konta root. Użytkownik nadal będzie mógł wykonywać zadania osobiste za pomocą tej aplikacji, ale będzie musiał korzystać z innego urządzenia w celu uzyskania dostępu do danych służbowych w tej aplikacji. | Tak |
| **Ponownie sprawdź wymagania dostępu po (w minutach)** | Skonfiguruj następujące ustawienia: <ul><li>**Limit czasu**: jest to liczba minut przed ponownym sprawdzeniem wymagań dostępu (zdefiniowanych wcześniej w tych zasadach). Na przykład administrator włącza numer PIN w zasadach, a użytkownik otwiera aplikację MAM i musi wprowadzić numer PIN. Gdyby to ustawienie było używane, użytkownik nie musiałby wprowadzać numeru PIN w żadnej aplikacji MAM przez następne **30 minut** (wartość domyślna).</li><li>**Okres karencji w trybie offline:** jest to liczba minut, przez jaką aplikacja MAM może działać w trybie offline. Określ czas (w minutach) do ponownego sprawdzenia wymagań dostępu dla aplikacji. Wartość domyślna: **720** minut (12 godzin). Po tym czasie aplikacja będzie wymagać uwierzytelnienia użytkownika w usłudze AAD, co pozwoli na kontynuowanie jej działania.</li></ul>| Limit czasu: 30 <br><br> W trybie offline: 720 |
| **Interwał offline przed wyczyszczeniem danych aplikacji (w dniach)** | Po tej liczbie dni pracy w trybie offline (zdefiniowanej przez administratora) aplikacja sama przeprowadzi selektywne czyszczenie. To selektywne czyszczenie jest takie samo jak to, które może zostać zainicjowanie przez administratora w przepływie pracy czyszczenia zarządzania aplikacjami mobilnymi. <br><br> | 90 dni |
| **Zablokuj przechwytywanie ekranu i asystenta systemu Android (Android 6.0 i nowsze)** | Wybierz opcję **Tak**, aby zablokować funkcję przechwytywania ekranu i możliwości **asystenta systemu Android** na urządzeniu podczas korzystania z tej aplikacji. Wybranie opcji **Tak** spowoduje również rozmycie obrazu podglądu przełącznika aplikacji podczas korzystania z tej aplikacji przy użyciu konta służbowego. | Nie |
| **Wyłącz numer PIN aplikacji, gdy zarządzany jest numer PIN urządzenia** | Wybierz opcję **Tak**, aby wyłączyć numer PIN aplikacji, gdy na zarejestrowanym urządzeniu zostanie wykryta blokada urządzenia. | Nie |
