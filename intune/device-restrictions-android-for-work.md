---
title: Ograniczenia urządzeń korzystających z profili służbowych systemu Android w usłudze Microsoft Intune — Azure | Microsoft Docs
description: W urządzeniach z profilami systemu Android Enterprise możesz ograniczyć część ustawień, w tym kopiowanie i wklejanie, pokazywanie powiadomień, uprawnienia aplikacji, udostępnianie danych, długość hasła, błędy logowania, używanie odcisku palca do odblokowywania, ponowne używanie haseł oraz włączanie udostępniania kontaktów służbowych za pomocą technologii Bluetooth.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/2/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: f0270818a03c68afd24e32d86a9c1f847e2f2ee2
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52181993"
---
# <a name="work-device-restriction-settings-in-intune"></a>Ustawienia ograniczeń urządzenia służbowego w usłudze Intune

W tym artykule opisano ustawienia ograniczeń urządzenia, które można skonfigurować w usłudze Microsoft Intune dla urządzeń z profilami systemu Android Enterprise.

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="work-profile-settings"></a>Ustawienia profilu służbowego

### <a name="general-settings"></a>Ustawienia ogólne

- **Kopiuj i wklejaj między profilem służbowym a osobistym**: steruje kopiowaniem i wklejaniem między aplikacjami służbowymi i osobistymi. Wybierz pozycję **Blokuj**, aby włączyć blokowanie. Wybierz pozycję **Nieskonfigurowane**, aby wyłączyć blokowanie.
- **Udostępnianie danych między profilami służbowym i osobistym**: określ, czy aplikacje w profilu służbowym mogą udostępniać dane aplikacjom w profilu osobistym. To ustawienie określa akcje udostępniania w ramach aplikacji, takie jak opcja **Udostępnij…** w przeglądarce Chrome. To ustawienie nie ma zastosowania do zachowania schowka w zakresie kopiowania/wklejania. W odróżnieniu od [ustawień zasad ochrony aplikacji](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) ustawieniami ograniczeń urządzenia zarządza się w portalu usługi Intune i używa partycji profilu służbowego systemu Android do izolowania zarządzanych aplikacji. Wybierz spośród opcji:
  - **Domyślne ograniczenia udostępniania**: domyślne zachowanie urządzenia w zakresie udostępniania, które różni się w zależności od wersji systemu Android. Udostępnianie danych z profilu osobistego w profilu służbowym jest domyślnie dozwolone. Udostępnianie danych z profilu służbowego w profilu osobistym jest domyślnie zablokowane. To ustawienie zapobiega udostępnianiu danych z profilu służbowego w profilu osobistym. Firma Google nie blokuje udostępniania z profilu osobistego do profilu służbowego na urządzeniach z systemem w wersji 6.0 lub nowszej.
  - **Aplikacje w profilu służbowym mogą obsługiwać żądania udostępnienia z profilu osobistego**: umożliwia włączenie wbudowanej funkcji systemu Android pozwalającej na udostępnianie danych z profilu osobistego w profilu służbowym. Gdy ta opcja jest włączona, żądanie udostępnienia z aplikacji w profilu osobistym umożliwi udostępnianie danych aplikacjom w profilu służbowym. Jest to domyślne ustawienie w przypadku urządzeń z systemem Android w wersji wcześniejszej niż 6.0.
  - **Zezwalaj na udostępnianie przez granice**: umożliwia udostępnianie przez granicę profilu służbowego w obu kierunkach. Po wybraniu tego ustawienia aplikacje w profilu służbowym mogą udostępniać dane niewskazanym aplikacjom w profilu osobistym. To ustawienie pozwala zarządzanym aplikacjom z profilu służbowego udostępniać dane aplikacjom w niezarządzanym obszarze urządzenia. Dlatego należy go używać ostrożnie.

- **Powiadomienia profilu służbowego przy zablokowanym urządzeniu**: pozwala określić, czy aplikacje z profilu służbowego mogą wyświetlać dane w powiadomieniach, gdy urządzenie jest zablokowane.
- **Domyślne uprawnienia aplikacji**: powoduje ustawienie domyślnych zasad uprawnień dla wszystkich aplikacji w profilu służbowym. Począwszy od systemu Android 6, użytkownik jest monitowany o udzielenie określonych uprawnień wymaganych przez aplikacje, gdy aplikacja jest uruchamiana. To ustawienie zasad pozwala określić, czy użytkownicy są monitowani o nadanie uprawnień wszystkim aplikacjom w profilu służbowym. Można na przykład przypisać aplikację do profilu służbowego, który wymaga dostępu do lokalizacji. Standardowo aplikacja monituje użytkownika o zatwierdzenie lub odrzucenie dostępu aplikacji do lokalizacji. Należy użyć tych zasad, aby automatycznie udzielić uprawnień bez wyświetlania monitu, automatycznie odmówić uprawnień bez wyświetlania monitu lub pozwolić użytkownikowi końcowemu zdecydować. Wybierz spośród opcji:
  - **Ustawienie domyślne urządzenia**
  - **Monit**
  - **Automatyczne udzielaj**
  - **Automatyczne odmawiaj**

    Zasad konfiguracji aplikacji można także użyć do nadania uprawnień dla poszczególnych aplikacji (**Aplikacje klienckie** > **Zasady konfiguracji aplikacji**).

- **Dodawanie i usuwanie kont**

   Uniemożliwia użytkownikom końcowym ręczne dodawanie i usuwanie kont w profilu służbowym.

   Na przykład w przypadku wdrożenia aplikacji Gmail w profilu służbowym systemu Android można uniemożliwić użytkownikom końcowym dodawanie i usuwanie kont w tym profilu służbowym.

- **Udostępnianie kontaktów za pośrednictwem połączenia Bluetooth**: umożliwia dostęp do kontaktów służbowych z innego urządzenia, takiego jak samochód, sparowanego za pomocą połączenia Bluetooth. Domyślnie to ustawienie nie jest skonfigurowane i kontakty służbowe nie są wyświetlane. Wybierz pozycję **Włącz**, aby zezwolić na udostępnianie i wyświetlić kontakty z profilu służbowego. To ustawienie dotyczy urządzeń z systemem Android w wersji 6.0 i nowszych oraz profilem służbowym. Włączenie tego ustawienia może umożliwić niektórym urządzeniom Bluetooth zapisanie w pamięci podręcznej kontaktów służbowych przy pierwszym połączeniu. Wyłączenie tych zasad po przeprowadzeniu początkowego parowania/synchronizacji może nie spowodować usunięcia kontaktów służbowych z urządzenia Bluetooth.

- **Przechwytywanie ekranu**: blokuje przechwytywanie ekranu na urządzeniu w profilu służbowym. Zapobiega również wyświetlaniu zawartości na urządzeniach wyświetlających, które nie mają zabezpieczonego wyjścia wideo.

- **Wyświetlanie identyfikatora rozmówcy dla kontaktu służbowego w profilu osobistym**: po włączeniu (bez konfigurowania) szczegóły rozmówcy dla kontaktu służbowego są wyświetlane w profilu osobistym. Po zablokowaniu numer rozmówcy dla kontaktu służbowego nie jest wyświetlany w profilu osobistym. Dotyczy systemu operacyjnego Android w wersji 6.0 i nowszych wersji.

- **Aparat fotograficzny**: blokuje aparat w urządzeniu w profilu służbowym. To ustawienie nie wpływa na aparat w profilu osobistym.

### <a name="work-profile-password"></a>Hasło profilu służbowego

- **Wymagaj hasła profilu służbowego**: ma zastosowanie do systemu Android 7.0 lub nowszego z włączonym profilem służbowym. Zdefiniuj zasady kodu dostępu, które będą mieć zastosowanie wyłącznie do aplikacji w profilu służbowym. Domyślnie użytkownik końcowy może używać dwóch różnych kodów PIN lub wybrać opcję połączenia zdefiniowanych kodów PIN w celu uzyskania kodu PIN o większej sile.
- **Minimalna długość hasła**: określ minimalną liczbę znaków, które musi zawierać hasło użytkownika (**4**-**16**).
- **Maksymalna liczba minut braku aktywności przed zablokowaniem profilu służbowego**: określ, po jakim czasie następuje zablokowanie profilu służbowego. Użytkownik musi następnie wprowadzić swoje poświadczenia, aby odzyskać dostęp.
- **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia**: określ, ile razy może zostać podane nieprawidłowe hasło, zanim profil służbowy zostanie wyczyszczony z urządzenia.
- **Wygaśnięcie hasła (dni)**: określ liczbę dni, po których użytkownik końcowy musi zmienić hasło (**1**-**255**).
- **Wymagany typ hasła**: wybierz typ hasła, które musi zostać ustawione na urządzeniu. Wybierz spośród opcji:
  - **Ustawienie domyślne urządzenia**
  - **Zabezpieczenia biometryczne na niskim poziomie**
  - **Wymagane**
  - **Co najmniej numeryczne**
  - **Złożona wartość liczbowa**: powtarzające się lub kolejne cyfry, np. „1111” lub „1234”, są niedozwolone
  - **Co najmniej alfabetyczne**
  - **Co najmniej alfanumeryczne**
  - **Co najmniej alfanumeryczne z symbolami**
- **Zapobiegaj ponownemu użyciu starych haseł**: wprowadź liczbę nowych haseł, których należy użyć, zanim będzie możliwe ponowne użycie starego hasła (**1**-**24**).
- **Odblokowywanie za pomocą odcisku palca**: uniemożliwia użytkownikowi końcowemu użycie skanera linii papilarnych w celu odblokowania urządzenia
- **Blokada Smart Lock i inni agenci zaufania**: umożliwia sterowanie funkcją Smart Lock na zgodnych urządzeniach. Ta funkcja telefonu, znana również jako funkcja agentów zaufania, umożliwia wyłączenie lub obejście hasła profilu służbowego, jeśli urządzenie jest w zaufanej lokalizacji. Na przykład można obejść hasło profilu służbowego, gdy urządzenie jest połączone z konkretnym urządzeniem Bluetooth lub znajduje się w pobliżu tagu NFC. Za pomocą tego ustawienia można uniemożliwić użytkownikom konfigurowanie funkcji Smart Lock.

## <a name="device-password"></a>Hasło urządzenia

- **Minimalna długość hasła**: określ minimalną liczbę znaków, które musi zawierać hasło użytkownika (**4**-**14**).
- **Maksymalna liczba minut braku aktywności przed zablokowaniem ekranu**: określ, po jakim czasie braku aktywności następuje automatyczne zablokowanie urządzenia
- **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia**: określ, ile razy może zostać podane nieprawidłowe hasło, zanim zostaną wyczyszczone wszystkie dane z urządzenia
- **Wygaśnięcie hasła (dni)**: określ liczbę dni, po których użytkownik końcowy musi zmienić hasło (**1**-**255**)
- **Wymagany typ hasła**: wybierz typ hasła, które musi zostać ustawione na urządzeniu. Wybierz spośród opcji:
  - **Ustawienie domyślne urządzenia**
  - **Zabezpieczenia biometryczne na niskim poziomie**
  - **Wymagane**
  - **Co najmniej numeryczne**
  - **Złożona wartość liczbowa**: powtarzające się lub kolejne cyfry, np. „1111” lub „1234”, są niedozwolone
  - **Co najmniej alfabetyczne**
  - **Co najmniej alfanumeryczne**
  - **Co najmniej alfanumeryczne z symbolami**
- **Zapobiegaj ponownemu użyciu starych haseł**: wprowadź liczbę nowych haseł, których należy użyć, zanim będzie możliwe ponowne użycie starego hasła (**1**-**24**).
- **Odblokowywanie za pomocą odcisku palca**: uniemożliwia użytkownikowi końcowemu użycie skanera linii papilarnych w celu odblokowania urządzenia
- **Blokada Smart Lock i inni agenci zaufania**: umożliwia sterowanie funkcją Smart Lock na zgodnych urządzeniach. Ta funkcja telefonu, znana również jako funkcja agentów zaufania, umożliwia wyłączenie lub obejście hasła ekranu blokady urządzenia, jeśli urządzenie jest w zaufanej lokalizacji. Na przykład można obejść hasło profilu służbowego, gdy urządzenie jest połączone z konkretnym urządzeniem Bluetooth lub znajduje się w pobliżu tagu NFC. Za pomocą tego ustawienia można uniemożliwić użytkownikom konfigurowanie funkcji Smart Lock.

## <a name="system-security"></a>Zabezpieczenia systemu

- **Skanowanie aplikacji pod kątem zagrożeń**: wymuszaj włączenie ustawienia **Weryfikuj aplikacje** w profilach służbowych i osobistych.

   > [!Note]
   > To ustawienie działa tylko w przypadku urządzeń z systemem Android O lub nowszym.

## <a name="connectivity"></a>Łączność

- **Zawsze włączona sieć VPN**: wybierz pozycję **Włącz**, aby ustawić klienta sieci VPN tak, aby automatycznie łączył się i przywracał połączenie z siecią VPN. Zawsze włączone połączenia sieci VPN pozostają aktywne lub natychmiast łączą się, gdy użytkownik zablokuje urządzenie, urządzenie uruchomi się ponownie lub zmieni się sieć bezprzewodowa. 

  Wybierz pozycję **Nieskonfigurowane**, aby wyłączyć zawsze włączoną sieć VPN dla wszystkich klientów sieci VPN. 

  > [!IMPORTANT]
  > Należy pamiętać, aby dla jednego urządzenia wdrożyć tylko jedne zasady zawsze włączonej sieci VPN. Wdrażanie wielu zasad zawsze włączonej sieci VPN dla jednego urządzenia nie jest obsługiwane.

- **Klient sieci VPN**: wybierz klienta sieci VPN, który obsługuje opcję Zawsze włączone. Dostępne opcje:
  - Cisco AnyConnect
  - F5 Access
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Niestandardowy
    - **Identyfikator pakietu**: wprowadź identyfikator pakietu aplikacji w sklepie Google Play. Jeśli na przykład adresem URL aplikacji w sklepie Play jest `https://play.google.com/store/details?id=com.contosovpn.android.prod`, to identyfikatorem pakietu jest `com.contosovpn.android.prod`.

    > [!IMPORTANT]
    >  - Wybrany klient sieci VPN musi być zainstalowany na urządzeniu i musi obsługiwać sieć VPN dla aplikacji w profilach służbowych. W przeciwnym razie wystąpi błąd. 
    >  - Należy zatwierdzić aplikację klienta sieci VPN w **zarządzanymi sklepie Google Play**, zsynchronizować aplikację z usługą Intune i wdrożyć aplikację na urządzeniu. Po wykonaniu tej czynności aplikacja jest zainstalowana w profilu służbowym użytkownika.
    >  - Istnieją znane problemy podczas korzystania z sieci VPN dla aplikacji z programem F5 Access dla systemu Android 3.0.3. Aby uzyskać więcej informacji, zobacz [opublikowane przez firmę F5 informacje o wersji programu F5 Access dla systemu Android 3.0.3](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-3.html#relnotes_known_issues_f5_access_android).

- **Tryb blokady**: wybierz pozycję **Włącz**, aby wymusić korzystanie z tunelu sieci VPN przez cały ruch sieciowy. Jeśli nie nawiązano połączenia z siecią VPN, urządzenie nie będzie mieć dostępu do sieci.

  Wybierz pozycję **Nieskonfigurowane**, aby zezwolić ruchowi na przepływ przez tunel VPN lub sieć komórkową.

## <a name="next-step"></a>Następny krok

[Przypisywanie profilów](device-profile-assign.md) do użytkowników i urządzeń.
