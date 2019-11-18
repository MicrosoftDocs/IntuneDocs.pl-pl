---
title: Konfigurowanie strony ze stanem rejestracji
titleSuffix: Microsoft Intune
description: Konfigurowanie strony powitalnej dla użytkowników rejestrujących urządzenia z systemem Windows 10.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/28/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: ericor
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5e453002493e95bd5147cca115075a17a6e7a298
ms.sourcegitcommit: 556b7ea2049014c9027f0e44affd3f301fab55fc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "73709320"
---
# <a name="set-up-an-enrollment-status-page"></a>Konfigurowanie strony ze stanem rejestracji
 
[!INCLUDE [azure_portal](../includes/azure_portal.md)]
 
Na stronie ze stanem rejestracji (ESP, Enrollment Status Page) są wyświetlane informacje o instalacji urządzeń z systemem Windows 10 (wersja 1803 lub nowsza) podczas początkowej rejestracji urządzenia. Przykład:
- podczas korzystania z rozwiązania [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/) 
- lub gdy urządzenie zarządzane zostanie uruchomione po raz pierwszy po zastosowaniu zasad strony ze stanem rejestracji. 

Strona ze stanem rejestracji pomaga użytkownikom zinterpretować stan urządzenia w trakcie konfigurowania. Możesz utworzyć wiele profilów strony ze stanem rejestracji i zastosować je do różnych grup zawierających użytkowników. Profile możesz ustawiać w następujących celach:
- Wyświetlanie postępu instalacji.
- Blokowanie użycia do zakończenia instalacji.
- Określanie czynności, które użytkownik może wykonać, jeśli konfigurowanie urządzenia nie powiedzie się.

Ponadto możesz ustawić kolejność priorytetu dla każdego profilu w celu obsłużenia konfliktu przypisań profilu do tego samego użytkownika.

> [!NOTE]
> Elementem docelowym strony ze stanem rejestracji może być tylko użytkownik należący do przypisanej grupy, a zasady są ustawiane na urządzeniu podczas rejestracji dla wszystkich użytkowników, którzy korzystają z urządzenia.  

## <a name="available-settings"></a>Dostępne ustawienia

 W celu dostosowania zachowania strony ze stanem rejestracji można skonfigurować następujące ustawienia:

<table>
<th align="left">Ustawienie<th align="left">Tak<th align="left">Nie
<tr><td>Pokaż postęp instalacji aplikacji i profilu<td>Strona ze stanem rejestracji jest wyświetlana.<td>Strona ze stanem rejestracji nie jest wyświetlana.
<tr><td>Zablokuj możliwość korzystania z urządzenia, dopóki nie zostaną zainstalowane wszystkie aplikacje i profile<td>W tej tabeli dostępne są ustawienia służące do dostosowywania zachowania strony ze stanem rejestracji w celu umożliwienia użytkownikowi rozwiązywania potencjalnych problemów z instalacją.
<td>Strona ze stanem rejestracji jest wyświetlana bez dodatkowych opcji w celu rozwiązywania problemów z błędami instalacji.
<tr><td>Zezwalaj użytkownikom na resetowanie urządzenia, jeśli wystąpi błąd instalacji<td>W przypadku błędu instalacji zostanie wyświetlony przycisk <b>Zresetuj urządzenie</b>.<td>W przypadku błędu instalacji nie zostanie wyświetlony przycisk <b>Zresetuj urządzenie</b>.
<tr><td>Zezwalaj użytkownikom na używanie urządzenia, jeśli wystąpi błąd instalacji<td>W przypadku błędu instalacji zostanie wyświetlony przycisk <b>Kontynuuj mimo to</b>.<td>W przypadku błędu instalacji nie zostanie wyświetlony przycisk <b>Kontynuuj mimo to</b>.
<tr><td>Pokaż błąd limitu czasu, jeśli instalacja trwa dłużej niż określona liczba minut<td colspan="2">Określ liczbę minut oczekiwania na ukończenie instalacji. Wprowadzona wartość domyślna wynosi 60 minut.
<tr><td>Pokaż niestandardowy komunikat po wystąpieniu błędu<td>Zostanie wyświetlone pole tekstowe, w którym można określić niestandardowy komunikat wyświetlany w przypadku wystąpienia błędu instalacji.<td>Komunikat domyślny jest następujący: <br><b>Instalacja przekroczyła limit czasu ustawiony przez organizację. Spróbuj ponownie lub skontaktuj się z pracownikiem pomocy technicznej IT, aby uzyskać pomoc.<b>
<tr><td>Zezwalaj użytkownikom na zbieranie dzienników o błędach instalacji<td>W przypadku wystąpienia błędu wyświetlany jest przycisk <b>Zbieraj dzienniki</b>. <br>Jeśli użytkownik kliknie ten przycisk, zostanie poproszony o wybranie lokalizacji, w której ma zostać zapisany plik dziennika <b>MDMDiagReport.cab</b><td>Przycisk <b>Zbieraj dzienniki</b> nie jest wyświetlany w przypadku wystąpienia błędu instalacji.
<tr><td>Blokuj użycie urządzenia do momentu zainstalowania wymaganych aplikacji, jeśli zostały przypisane do użytkownika/urządzenia<td colspan="2">Wybierz pozycję <b>Wszystkie</b> lub <b>Wybrane</b>. <br><br>Po kliknięciu pozycji <b>Wybrane</b> zostanie wyświetlony przycisk <b>Wybierz aplikacje</b> umożliwiający wybranie aplikacji, które muszą zostać zainstalowane przed włączeniem urządzenia.
</table>

## <a name="turn-on-default-enrollment-status-page-for-all-users"></a>Włączanie domyślnej strony ze stanem rejestracji dla wszystkich użytkowników

Aby włączyć stronę ze stanem rejestracji, wykonaj poniższe kroki.
 
1. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja w systemie Windows** > **Strona stanu rejestracji**.
2. W bloku **Strona ze stanem rejestracji** wybierz pozycje **Domyślne** > **Ustawienia**.
3. Aby **wyświetlić postęp instalacji aplikacji i profilu**, wybierz pozycję **Tak**.
4. Wybierz inne ustawienia, które chcesz włączyć, a następnie wybierz pozycję **Zapisz**.

## <a name="create-enrollment-status-page-profile-and-assign-to-a-group"></a>Tworzenie profilu strony ze stanem rejestracji i przypisywanie do grupy

1. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja w systemie Windows** > **Strona stanu rejestracji** > **Utwórz profil**.
2. Podaj **nazwę** i **opis**.
3. Wybierz pozycję **Utwórz**.
4. Wybierz nowy profil z listy **Strona ze stanem rejestracji**.
5. Wybierz pozycje **Przypisania** > **Wybierz grupy** > wybierz grupy, które mają być ujęte w tym profilu > **Wybierz** > **Zapisz**.
6. Wybierz pozycje **Ustawienia** > wybierz ustawienia, które chcesz zastosować do tego profilu > **Zapisz**.

## <a name="set-the-enrollment-status-page-priority"></a>Ustawianie priorytetu strony ze stanem rejestracji

Użytkownik może należeć do wielu grup i mieć wiele profilów stron ze stanem rejestracji. Aby obsłużyć takie konflikty, możesz ustawić priorytety dla każdego profilu. Jeśli dana osoba ma więcej niż jeden profil strony ze stanem rejestracji, podczas rejestracji do rejestrowanego urządzenia zostanie zastosowany tylko profil o najwyższym priorytecie.

1. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja w systemie Windows** > **Strona stanu rejestracji**.
2. Zatrzymaj wskaźnik myszy nad profilem na liście.
3. Używając trzech pionowych punktów, przeciągnij profil do żądanej pozycji na liście.

## <a name="block-access-to-a-device-until-a-specific-application-is-installed"></a>Blokowanie dostępu do urządzenia do momentu zainstalowania określonej aplikacji

Zanim użytkownik będzie mógł uzyskiwać dostęp do pulpitu, można określić aplikacje, które należy zainstalować.

1. W [centrum administracyjnym programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) wybierz pozycję **Rejestrowanie urządzenia** > **Rejestracja w systemie Windows** > **Strona stanu rejestracji**.
2. Wybierz profil > **Ustawienia**.
3. Wybierz pozycję **Tak** dla opcji **Pokaż postęp aplikacji i profilu**.
4. Wybierz pozycję **Tak** dla opcji **Blokuj użycie urządzenia do momentu zainstalowania wszystkich aplikacji i profilów**.
5. Wybierz pozycję **Wybrane** dla opcji **Blokuj użycie urządzenia do momentu zainstalowania wymaganych aplikacji, jeśli zostały przypisane do użytkownika/urządzenia**.
6. Wybierz pozycję **Wybierz aplikacje** > wybierz aplikacje > **Wybierz** > **Zapisz**.

## <a name="enrollment-status-page-tracking-information"></a>Informacje śledzenia strony ze stanem rejestracji

Strona ze stanem rejestracji śledzi informacje o trzech fazach: przygotowywanie urządzenia, konfiguracja urządzenia i konfiguracja konta.

### <a name="device-preparation"></a>Przygotowywanie urządzenia

W przypadku przygotowywania urządzenia na stronie ze stanem rejestracji są śledzone następujące informacje:
- zaświadczenia klucza modułu TPM (Trusted Platform Module) (jeśli jest to wymagane),
- postęp w dołączaniu do usługi Azure Active Directory,
- rejestrowanie w usłudze Intune,
- instalowanie rozszerzeń do zarządzania usługi Intune.

### <a name="device-setup"></a>Konfiguracja urządzenia

Na stronie ze stanem rejestracji są śledzone następujące elementy konfiguracji urządzenia (jeśli są przypisane do wszystkich urządzeń lub do grupy urządzeń, której członkiem jest rejestrowane urządzenie):
- Zasady zabezpieczeń
  - Jeden dostawca usług konfiguracji (CSP) dla wszystkich rejestracji.
  - Faktyczni dostawcy usług konfiguracji skonfigurowani za pomocą usługi Intune nie są śledzeni w tym miejscu.
- Aplikacje
  - Biznesowe aplikacje MSI na maszynę.
  - Aplikacje magazynu biznesowego z kontekstem instalacji = urządzenie.
  - Aplikacje magazynu offline i biznesowego z kontekstem instalacji = urządzenie.
  - Aplikacje systemu Win32 (tylko system Windows 10 w wersji 1903 lub nowszej) 
- Profile połączeń
  - Profile sieci VPN lub Wi-Fi przypisane do **wszystkich urządzeń** lub grupy urządzeń, do której należy rejestrowane urządzenie, ale tylko w przypadku urządzeń rozwiązania Autopilot
- Profile certyfikatów przypisane do **wszystkich urządzeń** lub grupy urządzeń, do której należy rejestrowane urządzenie, ale tylko w przypadku urządzeń rozwiązania Autopilot

### <a name="account-setup"></a>Konfigurowanie kont
W przypadku konfiguracji konta strona ze stanem rejestracji śledzi następujące elementy, jeśli są one przypisane do bieżącego zalogowanego użytkownika:
- Zasady zabezpieczeń
  - Jeden dostawca usług konfiguracji dla wszystkich rejestracji.
  - Faktyczni dostawcy usług konfiguracji skonfigurowani za pomocą usługi Intune nie są śledzeni w tym miejscu.
- Aplikacje
  - Aplikacje biznesowe MSI na użytkownika, które są przypisane do wszystkich urządzeń, wszystkich użytkowników lub grupy użytkowników, której członkiem jest użytkownik rejestrujący urządzenie.
  - Aplikacje biznesowe MSI na maszynę, które są przypisane do wszystkich użytkowników lub grupy użytkowników, której członkiem jest użytkownik rejestrujący urządzenie.
  - Aplikacje magazynu biznesowego, aplikacje magazynu online i aplikacje magazynu offline przypisane do dowolnego z następujących obiektów:
    - Wszystkie urządzenia
    - Wszyscy użytkownicy
    - Grupa użytkowników, w której użytkownik rejestrujący urządzenie jest członkiem z kontekstem instalacji ustawionym na wartość Użytkownik.
  - Aplikacje systemu Win32 (tylko system Windows 10 w wersji 1903 lub nowszej) 
- Profile połączeń
  - Profile sieci VPN lub Wi-Fi, które są przypisane do wszystkich użytkowników lub grupy użytkowników, której członkiem jest użytkownik rejestrujący urządzenie.
- Certyfikaty
  - Profile certyfikatów, które są przypisane do wszystkich użytkowników lub grupy użytkowników, której członkiem jest użytkownik rejestrujący urządzenie.

### <a name="troubleshooting"></a>Rozwiązywanie problemów
Najczęściej zadawane pytania dotyczące rozwiązywania problemów.

- Dlaczego moje aplikacje nie zostały zainstalowane w fazie konfiguracji urządzenia podczas wdrażania rozwiązania Autopilot korzystającego ze strony ze stanem rejestracji?
  - Aby zapewnić pomyślną instalację aplikacji w fazie konfiguracji rozwiązania Autopilot, należy się upewnić, że: 
        1. Aplikacja została wybrana w celu blokowania dostępu na liście wybranych aplikacji
        2. Aplikacje są dodawane do tej samej grupy urządzeń usługi Azure AD, do której przypisano profil rozwiązania Autopilot. 

- Dlaczego strona ze stanem rejestracji jest wyświetlana dla wdrożeń innych niż rozwiązania Autopilot, na przykład gdy użytkownik loguje się po raz pierwszy na urządzeniu zarejestrowanym do współzarządzania programu Configuration Manager?  
  - Na stronie ze stanem rejestracji znajduje się lista stanów instalacji dla wszystkich metod rejestracji, w tym:
      - rozwiązania Autopilot;
      - współzarządzania programu Configuration Manager;
      - gdy nowy użytkownik loguje się po raz pierwszy na urządzeniu, do którego zastosowano zasady strony ze stanem rejestracji.

- Jak mogę wyłączyć stronę ze stanem rejestracji, jeśli została ona skonfigurowana na urządzeniu?
  - Zasady strony ze stanem rejestracji są ustawiane na urządzeniu podczas rejestracji. Aby wyłączyć stronę ze stanem rejestracji, należy wyłączyć sekcje strony ze stanem rejestracji użytkowników i urządzeń. Te sekcje można wyłączyć, tworząc niestandardowe ustawienia OMA-URI z następującymi konfiguracjami.

      Wyłączanie strony ze stanem rejestracji użytkowników:

      ```
      Name:  Disable User ESP (choose a name you desire)
      Description:  (enter a description)
      OMA-URI:  ./Vendor/MSFT/DMClient/Provider/MS DM Server/FirstSyncStatus/SkipUserStatusPage
      Data type:  Boolean
      Value:  True 
      ```
      Wyłączanie strony ze stanem rejestracji urządzeń:

      ```
      Name:  Disable Device ESP (choose a name you desire)
      Description:  (enter a description)
      OMA-URI:  ./Vendor/MSFT/DMClient/Provider/MS DM Server/FirstSyncStatus/SkipDeviceStatusPage
      Data type:  Boolean
      Value:  True 
      ```
- Jak można zbierać pliki dziennika?
  - Dostępne są dwa sposoby zbierania plików dzienników stron ze stanem rejestracji:
      - Włącz możliwość zbierania dzienników przez użytkowników w zasadach strony ze stanem rejestracji. Po przekroczeniu limitu czasu na stronie ze stanem rejestracji użytkownik końcowy może wybrać opcję **Zbieraj dzienniki**. Po włożeniu dysku USB można skopiować na niego pliki dzienników.
      - Otwórz wiersz polecenia, wprowadzając sekwencję klawiszy SHIFT-F10, a następnie wprowadź następujące polecenie wiersza polecenia w celu wygenerowania plików dziennika: 

      ```
      mdmdiagnosticstool.exe -area Autopilot -cab <pathToOutputCabFile>.cab 
      ```

### <a name="known-issues"></a>Znane problemy
Poniżej przedstawiono znane problemy. 
- Wyłączenie profilu strony ze stanem rejestracji nie powoduje usunięcia z urządzeń zasad strony ze stanem rejestracji, a strona ze stanem rejestracji jest nadal wyświetlana, gdy użytkownicy logują się po raz pierwszy na urządzeniu. Zasady nie są usuwane, gdy profil strony ze stanem rejestracji jest wyłączany. Aby wyłączyć zasady strony ze stanem rejestracji, należy wdrożyć ustawienia OMA-URI. Zapoznaj się z powyższymi instrukcjami dotyczącymi wyłączania strony ze stanem rejestracji przy użyciu ustawień OMA-URI. 
- Oczekujące ponowne uruchomienie zawsze spowoduje przekroczenie limitu czasu. Przekroczenie limitu czasu występuje, ponieważ należy ponownie uruchomić urządzenie. Ponowne uruchomienie jest wymagane w celu zapewnienia czasu na ukończenie elementu śledzonego na stronie ze stanem rejestracji. Ponowne uruchomienie powoduje zamknięcie strony ze stanem rejestracji, a po ponownym uruchomieniu urządzenie nie zostaje wprowadzone podczas konfiguracji konta.  Należy rozważyć ustawienie niewymagania ponownego rozruchu po instalacji aplikacji. 
- Ponowne uruchomienie podczas konfigurowania powoduje wymuszenie wprowadzenia poświadczeń przez użytkownika przed przejściem do fazy konfiguracji konta. Poświadczenia użytkownika nie są zachowywane podczas ponownego uruchomienia. Użytkownik musi wprowadzić swoje poświadczenia, aby kontynuować wyświetlanie strony ze stanem rejestracji. 
- Podczas rejestracji konta służbowego w systemie Windows 10 w wersji niższej niż 1903 zawsze będzie występować przekroczenie limitu czasu. Strona ze stanem rejestracji czeka na zakończenie rejestracji w usłudze Azure AD. Ten problem został rozwiązany w systemie Windows 10 w wersji 1903 lub nowszej.  
- Wdrożenie hybrydowej usługi Azure AD przy użyciu rozwiązania Autopilot ze stroną ze stanem rejestracji trwa dłużej, niż limit czasu zdefiniowany w profilu strony ze stanem rejestracji. W przypadku wdrożeń hybrydowej usługi Azure AD przy użyciu rozwiązania Autopilot instalacja strony ze stanem rejestracji potrwa 40 minut dłużej, niż wartość ustawiona w profilu strony ze stanem rejestracji. To opóźnienie umożliwia utworzenie nowego rekordu urządzenia w usłudze Azure AD przy użyciu łącznika lokalnej usługi AD. 
- Nazwa użytkownika na stronie logowania systemu Windows nie jest wstępnie wypełniona w trybie rozwiązania Autopilot sterowanym przez użytkownika. W przypadku ponownego uruchomienia w fazie konfigurowania strony ze stanem rejestracji:
    - poświadczenia użytkownika nie są zachowywane;
    - użytkownik musi ponownie wprowadzić poświadczenia przed przejściem z fazy konfiguracji urządzenia do fazy konfiguracji konta;
- strona ze stanem rejestracji jest zablokowana przez długi czas lub faza „Identifying” (Identyfikowanie) nigdy nie zostaje ukończona. Usługa Intune oblicza zasady strony ze stanem rejestracji w fazie identyfikowania. Jeśli bieżący użytkownik nie ma przypisanej licencji usługi Intune, urządzenie może nigdy nie ukończyć przetwarzania zasad strony ze stanem rejestracji.  
- Skonfigurowanie rozwiązania Kontrola aplikacji usługi Windows Defender powoduje wyświetlenie monitu o ponowne uruchomienie podczas korzystania z rozwiązania Autopilot. Konfigurowanie aplikacji Windows Defender (AppLocker CSP) wymaga ponownego uruchomienia. Skonfigurowanie tych zasad może spowodować ponowne uruchomienie urządzenia podczas korzystania z rozwiązania Autopilot. Obecnie nie ma możliwości pominięcia lub odroczenia ponownego uruchomienia.
- Gdy zasady DeviceLock (https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock) są włączone w ramach profilu strony ze stanem rejestracji, proces OOBE lub logowanie automatyczne użytkownika do komputera może nieoczekiwanie zakończyć się niepowodzeniem z dwóch powodów.
  - Jeśli urządzenie nie zostało ponownie uruchomione przed zakończeniem fazy konfiguracji urządzenia strony ze stanem rejestracji, użytkownik może zostać poproszony o wprowadzenie poświadczeń usługi Azure AD. Ten monit jest wyświetlany zamiast pomyślnego logowania automatycznego powodującego wyświetlenie animacji pierwszego logowania użytkownika w systemie Windows.
  - Logowanie automatyczne nie powiedzie się, jeśli urządzenie zostało uruchomione ponownie po wprowadzeniu poświadczeń usługi Azure AD przez użytkownika, ale przed zakończeniem fazy konfiguracji urządzenia strony ze stanem rejestracji. Ten błąd występuje, ponieważ faza konfiguracji urządzenia strony ze stanem rejestracji nigdy nie została ukończona. Obejście polega na zresetowaniu urządzenia.

## <a name="next-steps"></a>Następne kroki
Po skonfigurowaniu strony rejestracji w systemie Windows dowiedz się, jak zarządzać urządzeniami z systemem Windows. Aby uzyskać więcej informacji, zobacz artykuł [Co to jest zarządzanie urządzeniami w usłudze Microsoft Intune?](../remote-actions/device-management.md)
