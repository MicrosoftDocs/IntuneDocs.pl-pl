---
title: Wczesna wersja
description: 
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/24/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d7c2ec47a163c16de91d3004a6204c1c00feb801
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/23/2018
---
# <a name="the-early-edition-for-microsoft-intune---february-2018"></a>Wczesna wersja usługi Microsoft Intune — luty 2018

**Wczesna wersja** zawiera listę funkcji, które zostaną wprowadzone w przyszłych wersjach usługi Microsoft Intune. Te informacje są przekazywane w ograniczonym zakresie i mogą ulec zmianie. Nie należy udostępniać tych informacji poza firmą. Niektóre funkcje wymienione w tym miejscu mogą nie być wdrożone na czas i zostać opóźnione do przyszłych wersji. Inne funkcje są testowane w wersji pilotażowej, aby zapewnić przygotowanie ich do użytku przez klientów. W przypadku pytań lub wątpliwości skontaktuj się z osobą kontaktową ds. tej grupy produktów firmy Microsoft.

Ta strona jest okresowo aktualizowana. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.

> [!Note]
>Dla usługi Intune opracowywane są następujące zmiany. Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->

## <a name="intune-in-the-azure-portal"></a>Usługa Intune w witrynie Azure Portal


<!-- 1802 start -->

### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Nowy wykres trendu niepowodzeń rejestracji i tabela z przyczynami niepowodzeń <!-- 1471783 -->

Na stronie przeglądu rejestracji będzie można wyświetlić trend niepowodzeń rejestracji i pięć najczęstszych przyczyn niepowodzeń. Klikając wykres lub tabelę, będzie można przejść do szczegółów, aby znaleźć porady dotyczące rozwiązywania problemów i sugestie dotyczące korygowania.

### <a name="prevent-end-users-from-adding-or-removing-accounts-in-the-work-profile----1728700---"></a>Uniemożliwianie użytkownikom końcowym dodawania i usuwania kont w profilu służbowym <!-- 1728700 -->    
Podczas wdrażania aplikacji usługi Gmail w profilu programu Android for Work będzie można uniemożliwić użytkownikom końcowym dodawanie i usuwanie kont w profilu służbowym przy użyciu ustawienia **Dodawanie i usuwanie kont** w profilu ograniczeń programu Android for Work.

### <a name="app-protection-policies-----679615---"></a>Zasady usługi App Protection <!-- 679615 -->
Zasady usługi Intune App Protection umożliwiają tworzenie globalnych, domyślnych zasad, które pozwalają na szybkie włączenie ochrony dla wszystkich użytkowników w całej dzierżawie.

### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Obsługa usługi Intune dla wielu kont usług Apple DEP/Apple School Manager <!-- 747685 -->

Usługa Intune będzie obsługiwać rejestrowanie urządzeń z maksymalnie 100 różnych kont usług Apple Device Enrollment Program (DEP) i Apple School Manager. Każdy przekazany token może być zarządzany oddzielnie w odniesieniu do profilów rejestracji i urządzeń. Do przekazanych tokenów usług DEP/School Manager mogą być automatycznie przypisywane różne profile rejestracji. W przypadku przekazania wielu tokenów usługi School Manager jednorazowo można udostępnić aplikacji Microsoft School Data Sync tylko jeden token.

Po przeprowadzeniu migracji interfejsy API programu Graph w wersji beta i opublikowane skrypty do zarządzania usługami Apple DEP lub ASM za pośrednictwem programu Graph nie będą już działać. Nowe interfejsy API programu Graph w wersji beta znajdują się w fazie projektowania i zostaną wydane po zakończeniu migracji.

### <a name="windows-defender-health-status-and-threat-status-reports---854704---"></a>Raporty dotyczące stanu zagrożenia i stanu kondycji programu Windows Defender <!--854704 -->

Zrozumienie stanu i kondycji programu Windows Defender ma kluczowe znaczenie w zarządzaniu komputerami z systemem Windows.  Usługa Intune doda nowe raporty i akcje do stanu i kondycji agenta programu Windows Defender. Za pomocą zbiorczego raportu stanu w obciążeniu Zgodność urządzenia będzie można zobaczyć urządzenia, dla których trzeba wykonać jedną z następujących czynności:

- Aktualizacja sygnatur
- Ponowne uruchomienie
- Ręczna interwencja
- Pełne skanowanie
- Inne stany agentów, które wymagają interwencji

W niektórych przypadkach mogą zostać wykonane zdalne akcje korygowania, takie jak wyzwolenie aktualizacji sygnatur.  Raport wskazuje także liczbę komputerów osobistych, których stan jest zgłaszany jako **Czysty**.

Raport szczegółowy dla każdej kategorii stanu zawiera listę poszczególnych komputerów osobistych, które wymagają uwagi, lub takich, których stan jest zgłaszany jako **Czysty**.

### <a name="protocol-exceptions-for-applications---1035509-eeready--"></a>Wyjątki protokołu dla aplikacji <!--1035509 eeready-->

W zasadach transferu danych funkcji zarządzania aplikacjami mobilnymi (MAM, Mobile Application Management) w usłudze Intune będzie można tworzyć wyjątki, aby umożliwiać korzystanie z określonych aplikacji niezarządzanych. Takie aplikacje muszą być uznane za zaufane przez dział IT. Poza utworzonymi wyjątkami transfer danych nadal będzie ograniczony do aplikacji, które są zarządzane przez usługę Intune, gdy zasady transferu danych mają ustawienie **Tylko aplikacje zarządzane**. Ograniczenia można tworzyć za pomocą protokołów (system iOS) lub pakietów (system Android).

Na przykład można dodać pakiet Webex jako wyjątek do zasad transferu danych MAM. Pozwoli to na otwieranie linków Webex w wiadomości e-mail zarządzanego programu Outlook bezpośrednio w aplikacji Webex. Transfer danych będzie w dalszym ciągu ograniczony w innych aplikacjach niezarządzanych.

### <a name="customize-your-company-portal-themes-with-hex-codes---1049561-eeready--"></a>Dostosowywanie motywów aplikacji Portal firmy za pomocą kodów szesnastkowych <!--1049561 eeready-->

Kolor motywów w aplikacjach Portal firmy będzie można dostosowywać przy użyciu kodów szesnastkowych. Po wprowadzeniu kodu szesnastkowego usługa Intune określi kolor tekstu, który zapewni najwyższy poziom kontrastu między tekstem a tłem, zgodnie ze [standardami WCAG 2.0](http://www.w3.org/TR/WCAG20). Podgląd koloru tekstu i logo firmy na tle wybranego koloru możesz wyświetlić, wybierając pozycję **Aplikacje mobilne** > **Portal firmy**. 

### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252---"></a>Nowe ustawienia funkcji Windows Defender Credential Guard dodane do ustawień programu Endpoint Protection <!--1102252 --> 

Nowe ustawienia funkcji [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) zostaną dodane do obszaru **Konfiguracja urządzenia** > **Profile** > **Endpoint Protection**. Zostaną dodane następujące ustawienia: 

- Poziom zabezpieczeń platformy: określ, czy poziom zabezpieczeń platformy zostanie włączony przy następnym ponownym uruchomieniu. Zabezpieczenia oparte na wirtualizacji wymagają bezpiecznego rozruchu. Opcjonalnie zabezpieczenia oparte na wirtualizacji można włączyć przy użyciu ochrony bezpośredniego dostępu do pamięci (DMA, direct memory access). Ochrona DMA wymaga obsługi sprzętowej i będzie można ją włączyć tylko na prawidłowo skonfigurowanych urządzeniach.
- Zabezpieczenia oparte na wirtualizacji: określ, czy zabezpieczenia oparte na wirtualizacji zostaną włączone przy następnym ponownym uruchomieniu. 
- Windows Defender Credential Guard: włącz funkcję Credential Guard z zabezpieczeniami opartymi na wirtualizacji, aby ułatwić zapewnienie ochrony poświadczeń, przy następnym ponownym uruchomieniu, gdy poziom zabezpieczeń platformy z bezpiecznym rozruchem i zabezpieczenia oparte na wirtualizacji są włączone. Dostępne opcje: **Wyłączone**, **Włączone z blokadą UEFI**, **Włączone bez blokady** i **Nieskonfigurowane**. 
  - Opcja „Wyłączone” zdalnie wyłącza funkcję Credential Guard, jeśli została ona wcześniej włączona za pomocą opcji „Włączone bez blokady”.

  - Opcja „Włączone z blokadą UEFI” zapewnia, że funkcji Credential Guard nie będzie można wyłączyć za pomocą klucza rejestru ani przy użyciu zasad grupy. Aby wyłączyć funkcję Credential Guard po użyciu tego ustawienia, należy ustawić zasady grupy na opcję „Wyłączone” i usunąć funkcję zabezpieczeń z każdego komputera, gdy użytkownik jest fizycznie przy komputerze, w celu wyczyszczenia konfiguracji utrwalonej w interfejsie UEFI. Dopóki konfiguracja interfejsu UEFI będzie utrwalona, funkcja Credential Guard pozostanie włączona.

  - Opcja „Włączone bez blokady” umożliwia zdalne wyłączenie funkcji Credential Guard za pomocą zasad grupy. Na urządzeniach, które korzystają z tego ustawienia, musi działać system Windows 10 (wersja 1511) lub nowszy.

  - Opcja „Nieskonfigurowane” pozostawia niezdefiniowane ustawienie zasad. Zasady grupy nie zapisują ustawienia zasad w rejestrze, więc nie ma ono wpływu na komputery ani użytkowników. Jeśli w rejestrze znajduje się bieżące ustawienie, nie zostanie ono zmodyfikowane.

### <a name="synchronize-and-deploy-sparsely-bundled-windows-store-for-business-apps---1222672---"></a>Synchronizowanie i wdrażanie aplikacji ze Sklepu Windows dla firm w pakiecie rozrzedzonym <!--1222672 -->
Aplikacje offline zakupione ze Sklepu Windows dla firm będą synchronizowane z portalem usługi Intune. Następnie można wdrożyć te aplikacje w grupach urządzeń lub w grupach użytkowników. Aplikacje offline są instalowane przez usługę Intune, a nie przez sklep.

### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Resetowanie haseł dla urządzeń z systemem Android O <!-- 1238299 -->
Będzie można resetować hasła zarejestrowanych urządzeń z systemem Android O. Po wysłaniu żądania „Resetuj hasło” do urządzenia z systemem Android O ustawi ono nowe hasło odblokowania urządzenia lub wezwanie zarządzanego profilu dla bieżącego użytkownika. Hasło lub wezwanie jest wysyłane w zależności od tego, czy urządzenie ma właściciela profilu, czy właściciela urządzenia, i zaczyna obowiązywać natychmiast.

### <a name="local-device-security-option-settings----1251887---"></a>Ustawienia opcji zabezpieczeń urządzenia lokalnego <!-- 1251887 -->
Na urządzeniach z systemem Windows 10 będzie można włączać ustawienia zabezpieczeń przy użyciu nowych ustawień opcji zabezpieczeń urządzenia lokalnego. Te ustawienia można znaleźć w kategorii Endpoint Protection podczas tworzenia zasad konfiguracji urządzeń z systemem Windows 10.

### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Nowe ustawienia drukarek dla profili edukacyjnych <!-- 1308900 -->

W przypadku profili edukacyjnych będą dostępne nowe ustawienia w kategorii **Drukarki**: **Drukarki**, **Drukarka domyślna**, **Dodaj nowe drukarki**. 

### <a name="new-privacy-settings-for-device-restrictions---1308926---"></a>Nowe ustawienia prywatności dla ograniczeń urządzenia <!--1308926 -->

Dla urządzeń będą dostępne dwa nowe ustawienia prywatności:

- **Publikuj działania użytkownika**: ustaw tę pozycję na wartość **Blokuj**, aby uniemożliwić udostępnianie środowisk i odnajdywanie ostatnio używanych zasobów w przełączniku zadań.

- **Tylko działania lokalne**: ustaw tę pozycję na wartość **Blokuj**, aby uniemożliwić udostępnianie środowisk i odnajdywanie ostatnio używanych zasobów w przełączniku zadań jedynie na podstawie działań lokalnych.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager----1352411---"></a>Obsługa rejestracji, które używają menedżera rejestracji urządzeń, w aplikacji Portal firmy dla systemu macOS <!-- 1352411 -->

Użytkownicy będą mogli używać menedżera rejestracji urządzeń podczas rejestrowania za pomocą aplikacji Portal firmy dla systemu macOS.

#### <a name="new-settings-for-the-edge-browser---1469166---"></a>Nowe ustawienia przeglądarki Edge <!--1469166 -->

Dla urządzeń z przeglądarką Microsoft Edge będą dostępne dwa nowe ustawienia: **Ścieżka do pliku ulubionych** i **Zmiany w ulubionych**. 

### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Dane zaszyfrowane przy użyciu funkcji Windows Information Protection (WIP) w wynikach wyszukiwania systemu Windows <!-- 1469193 -->

Nowe ustawienie w zasadach funkcji Windows Information Protection (WIP) umożliwia kontrolowanie, czy dane zaszyfrowane przy użyciu funkcji WIP będą uwzględniane w wynikach wyszukiwania systemu Windows.

### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>Obsługa aplikacji biznesowych dla systemu macOS <!-- 1473977 -->
Usługa Intune będzie umożliwiać instalowanie aplikacji biznesowych (LOB, line-of-business) dla systemu macOS. Aplikacje LOB to aplikacje, w przypadku których dostarczasz plik instalacyjny, a następnie instalujesz aplikację na urządzeniu przy użyciu usługi Intune. W ramach obsługi aplikacji LOB dla systemu macOS należy użyć dostępnego w usłudze Microsoft Intune narzędzia opakowującego aplikacje dla systemu macOS, aby wstępnie przetworzyć aplikacje LOB dla systemu macOS.

### <a name="configure-resource-account-settings-for-surface-hubs----1475674---"></a>Konfigurowanie ustawień kont zasobów dla urządzeń Surface Hub <!-- 1475674 -->

Ustawienia kont zasobów dla urządzeń Surface Hub będzie można konfigurować zdalnie.

Konto zasobu jest używane przez urządzenie Surface Hub do uwierzytelniania względem programu Skype/Exchange, co pozwala przyłączyć je do spotkania. Zaleca się utworzenie unikatowego konta zasobu, aby urządzenie Surface Hub było wyświetlane w ramach spotkania jako sala konferencyjna. Na przykład konto zasobu takie jak **Sala konferencyjna B41/6233**.

> [!NOTE]
> - Jeśli pozostawisz puste pola, spowoduje to zastąpienie atrybutów skonfigurowanych wcześniej na urządzeniu.
>
> - Właściwości konta zasobu mogą się dynamicznie zmieniać na urządzeniu Surface Hub. Jeśli na przykład rotacja hasła jest włączona. W związku z tym możliwe jest, że minie trochę czasu, zanim wartości w konsoli platformy Azure będą odzwierciedlać rzeczywiste wartości na urządzeniu. 
>
>   Aby poznać bieżącą konfigurację na urządzeniu Surface Hub, informacje o koncie zasobu mogą zostać uwzględnione w spisie sprzętu (który jest już wykonywany z 7-dniowym interwałem) lub jako właściwości tylko do odczytu. Aby poprawić dokładność danych po przeprowadzeniu akcji zdalnej, można pobrać stan parametrów natychmiast po wykonaniu akcji w celu zaktualizowania konta/parametrów na urządzeniu Surface Hub.

### <a name="ios-app-provisioning-configuration----1581650---"></a>Konfiguracja aprowizacji aplikacji systemu iOS <!-- 1581650 -->
Aby zapobiec wygaśnięciu aplikacji, będzie można przypisywać profile aprowizacji aplikacji systemu iOS przez uwzględnienie lub wykluczenie grup zabezpieczeń.

### <a name="new-windows-defender-exploit-guard-settings----631893---"></a>Nowe ustawienia funkcji Windows Defender Exploit Guard <!-- 631893 -->

Będzie dostępnych sześć nowych ustawień funkcji **Zmniejszenie obszaru ataków** oraz rozszerzone możliwości **Kontrolowany dostęp do folderów: Ochrona folderów**. Te ustawienia można znaleźć w obszarze: Konfiguracja urządzenia\Profile\
Utwórz profil\Endpoint Protection\Windows Defender Exploit Guard.

#### <a name="attack-surface-reduction"></a>Zmniejszenie obszaru ataków

|Nazwa ustawienia  |Opcje ustawienia  |Opis  |
|---------|---------|---------|
|Zaawansowana ochrona przed oprogramowaniem wymuszającym okup|Włączone, Inspekcja, Nieskonfigurowane|Użyj agresywnej ochrony przed oprogramowaniem wymuszającym okup.|
|Flaguj kradzież poświadczeń z podsystemu lokalnego uwierzytelniania zabezpieczeń systemu Windows|Włączone, Inspekcja, Nieskonfigurowane|Flaguj kradzież poświadczeń z podsystemu lokalnego uwierzytelniania zabezpieczeń systemu Windows (lsass.exe).|
|Tworzenie procesów za pomocą poleceń narzędzia PSExec i usługi WMI|Blokuj, Inspekcja, Nieskonfigurowane|Blokuj tworzenie procesów pochodzące z poleceń narzędzia PSExec i usługi WMI.|
|Niezaufane i niepodpisane procesy uruchamiane z dysku USB|Blokuj, Inspekcja, Nieskonfigurowane|Blokuj niezaufane i niepodpisane procesy uruchamiane z dysku USB.|
|Pliki wykonywalne, które nie spełniają kryteriów występowania, wieku lub listy zaufanych|Blokuj, Inspekcja, Nieskonfigurowane|Blokuj uruchamianie plików wykonywalnych, chyba że spełniają kryteria występowania, wieku lub listy zaufanych.|

#### <a name="controlled-folder-access"></a>Kontrolowany dostęp do folderów

|Nazwa ustawienia  |Opcje ustawienia  |Opis  |
|---------|---------|---------|
|Ochrona folderów (już zaimplementowano)|Nieskonfigurowane, Włączone, Tylko inspekcja (już zaimplementowano)<br><br> **Nowe**<br>Blokuj modyfikację dysku, Inspekcja modyfikacji dysku|
Chroń pliki i foldery przed nieautoryzowanymi zmianami przez nieprzyjazne aplikacje.<br><br>**Włącz**: zapobiegaj modyfikowaniu i usuwaniu plików w folderach chronionych oraz zapisywaniu danych w sektorach dysku przez niezaufane aplikacje.<br><br>
**Blokuj tylko modyfikowanie dysku**:<br>Blokuj zapisywanie danych w sektorach dysku przez niezaufane aplikacje. Niezaufane aplikacje nadal mogą modyfikować i usuwać pliki w folderach chronionych.

### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Nowe ustawienia funkcji Windows Defender Application Guard <!-- 1631890 -->

- **Włącz przyspieszanie grafiki**

Administratorzy będą mogli włączyć wirtualny procesor graficzny dla funkcji Windows Defender Application Guard. To ustawienie umożliwia procesorowi CPU przekazanie renderowania grafiki do procesora vGPU. Może to poprawić wydajność podczas pracy z witrynami internetowymi bogatymi w grafikę lub podczas oglądania filmu wideo znajdującego się w kontenerze.

- **SaveFilestoHost**

Administratorzy będą mogli włączyć przekazywanie plików z przeglądarki Microsoft Edge działającej w kontenerze do systemu plików hosta. Włączenie tej opcji pozwoli użytkownikom na pobieranie plików z przeglądarki Microsoft Edge w kontenerze do systemu plików hosta.

### <a name="see-enrollment-restrictions-per-user----1634444---"></a>Wyświetlanie ograniczeń rejestracji dla poszczególnych użytkowników <!-- 1634444 -->
W bloku rozwiązywania problemów będzie można zobaczyć ograniczenia rejestracji obowiązujące poszczególnych użytkowników.

### <a name="configuring-a-self-updating-mobile-msi-app----1740840---"></a>Konfigurowanie mobilnej aplikacji MSI korzystającej z samoaktualizacji <!-- 1740840 -->
Znaną mobilną aplikację MSI, która korzysta z samoaktualizacji, będzie można skonfigurować tak, aby ignorowała proces sprawdzania wersji. Ta możliwość jest przydatna, aby uniknąć sytuacji wyścigu. Może ona wystąpić na przykład wtedy, gdy aplikacja jest automatycznie aktualizowana przez dewelopera, a równocześnie jest aktualizowana przez usługę Intune. Obie aktualizacje mogą próbować wymusić na kliencie systemu Windows daną wersję aplikacji, co może powodować konflikt.

### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies---1704133---"></a>Dodatki do ustawień zabezpieczeń systemu dla zasad zgodności systemu Windows 10 lub nowszego <!--1704133 -->

Będą dostępne dodatki do ustawień zgodności systemu Windows 10, w tym możliwość wymagania zapory oraz programu antywirusowego Windows Defender.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Uwzględnianie i wykluczanie przypisania aplikacji na podstawie grup dla programu Android Enterprise <!-- 1813081 -->
Podczas przypisywania aplikacji i po wybraniu typu przypisania program Android Enterprise (wcześniej znany jako Android for Work) będzie obsługiwać funkcję wykluczania.


### <a name="related-sets-of-app-licenses-supported-in-intune----1864117---"></a>Powiązane zestawy licencji aplikacji obsługiwane w usłudze Intune <!-- 1864117 -->
Usługa Intune w witrynie Azure Portal będzie obsługiwać powiązane zestawy licencji aplikacji jako jeden element aplikacji w interfejsie użytkownika. Ponadto wszelkie aplikacje licencjonowane w trybie offline synchronizowane ze sklepem Microsoft Store dla Firm zostaną skonsolidowane w jeden wpis aplikacji i wszelkie szczegóły wdrożenia z indywidualnych pakietów zostaną migrowane do tego pojedynczego wpisu. Aby wyświetlić powiązane zestawy licencji aplikacji w witrynie Azure Portal, wybierz pozycję **Licencje aplikacji** w bloku **Aplikacje mobilne**.

<!-- the following are present prior to 1802 -->

### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625---"></a>Nowa opcja uwierzytelniania użytkownika na potrzeby rejestracji zbiorczej firmy Apple <!-- 747625 -->
Usługa Intune zapewni możliwość uwierzytelniania urządzeń przy użyciu aplikacji Portal firmy dla następujących metod rejestracji:

- Program Device Enrollment Program firmy Apple
- Apple School Manager
- Rejestracja programu Apple Configurator

Korzystając z opcji obejmującej Portal firmy, można wymusić uwierzytelnianie wieloskładnikowe usługi Azure Active Directory bez blokowania tych metod rejestracji.

W przypadku użycia opcji obejmującej Portal firmy usługa Intune pomija uwierzytelnianie użytkownika w Asystencie ustawień systemu iOS w celu rejestracji koligacji użytkownika. Oznacza to, że urządzenie zostaje początkowo zarejestrowane jako urządzenie bez użytkownika i dlatego nie otrzymuje konfiguracji ani zasad dotyczących grup użytkowników. Otrzymuje tylko konfiguracje i zasady dotyczące grup urządzeń. Jednak usługa Intune automatycznie zainstaluje aplikację Portal firmy na urządzeniu. Pierwszy użytkownik, który uruchomi aplikację Portal firmy i zaloguje się w niej, zostanie skojarzony z urządzeniem w usłudze Intune. Użytkownik otrzyma wówczas konfiguracje i zasady dotyczące grup użytkowników. Skojarzenia z użytkownikiem nie można zmienić bez ponownego wykonania rejestracji.

### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Obsługa usługi Intune dla wielu kont usług Apple DEP/Apple School Manager <!-- 747685 -->
Usługa Intune będzie obsługiwać rejestrowanie urządzeń z maksymalnie 100 różnych kont usług Apple Device Enrollment Program (DEP) i Apple School Manager. Każdy przekazany token może być zarządzany oddzielnie w odniesieniu do profilów rejestracji i urządzeń. Do przekazanych tokenów usług DEP/School Manager mogą być automatycznie przypisywane różne profile rejestracji. W przypadku przekazania wielu tokenów usługi School Manager jednorazowo można udostępnić aplikacji Microsoft School Data Sync tylko jeden token.

Po przeprowadzeniu migracji interfejsy API programu Graph w wersji beta i opublikowane skrypty do zarządzania usługami Apple DEP lub ASM za pośrednictwem programu Graph nie będą już działać. Nowe interfejsy API programu Graph w wersji beta znajdują się w fazie projektowania i zostaną wydane po zakończeniu migracji.

### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Określanie zasad zgodności dla urządzeń w grupach urządzeń<!--1307012 -->

Możesz określać zasady zgodności dla użytkowników w grupach użytkowników. Możesz także określać zasady zgodności dla urządzeń w grupach urządzeń.

### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Dane zaszyfrowane przy użyciu funkcji Windows Information Protection (WIP) w wynikach wyszukiwania systemu Windows <!-- 1469193 -->

Nowe ustawienie w zasadach funkcji Windows Information Protection (WIP) umożliwia kontrolowanie, czy dane zaszyfrowane przy użyciu funkcji WIP będą uwzględniane w wynikach wyszukiwania systemu Windows.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Drukowanie zdalne za pośrednictwem sieci zabezpieczonej <!-- 1709994  -->
Rozwiązania bezprzewodowego drukowania mobilnego PrinterOn umożliwią użytkownikom drukowanie zdalne z dowolnego miejsca i w dowolnym czasie za pośrednictwem sieci zabezpieczonej. Rozwiązania PrinterOn będą zintegrowane z zestawem Intune APP SDK dla systemów iOS i Android. Możliwe będzie określenie zasad ochrony aplikacji dla danej aplikacji przy użyciu bloku **Zasady ochrony aplikacji** usługi Intune w konsoli administratora. Użytkownicy końcowi będą mogli pobrać aplikację „PrinterOn for Microsoft” za pośrednictwem sklepu Play lub iTunes i używać jej w środowisku usługi Intune.



### <a name="microsoft-graph-api-for-intune---general-availability-----1833289---"></a>Interfejs API programu Microsoft Graph dla usługi Intune — ogólna dostępność <!-- 1833289 -->
Interfejsy API programu Microsoft Graph w usłudze Intune zapewnią programowy dostęp do danych i metod na potrzeby automatyzacji działań administracyjnych dla usługi Intune.  Dzięki **ogólnej dostępności** tych interfejsów API klienci, partnerzy i deweloperzy będą mogli używać interfejsów API do integracji z rozwiązaniami wewnętrznymi lub komercyjnymi, które są związane z obsługą usługi Intune bądź wymagają takiej obsługi, albo z innymi usługami firmy Microsoft dostępnymi za pośrednictwem programu Microsoft Graph.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Zasady usługi App Protection <!-- 679615 -->
Zasady usługi Intune App Protection umożliwiają tworzenie globalnych, domyślnych zasad, które pozwalają na szybkie włączenie ochrony dla wszystkich użytkowników w całej dzierżawie.

### <a name="new-ios-device-action------1244701---"></a>Nowa akcja dotycząca urządzenia z systemem iOS <!-- 1244701 -->
Można zamknąć nadzorowane urządzenia z systemem iOS 10.3. Ta akcja natychmiast wyłącza urządzenie bez ostrzeżenia dla użytkownika końcowego. Akcję **Wyłącz (tylko nadzorowane)** można znaleźć we właściwościach urządzenia po wybraniu urządzenia w obciążeniu **Urządzenie**.

### <a name="intune-provides-the-account-move-operation-----1573558-1579830---"></a>Usługa Intune obejmuje operację przenoszenia konta <!-- 1573558, 1579830 -->
Funkcja **Przenoszenie konta** migruje dzierżawę z jednej jednostki skalowania Azure (ASU) na inną. Funkcji **Przenoszenie konta** można użyć w obu scenariuszach inicjowanych przez klienta, kiedy klient dzwoni do zespołu pomocy technicznej usługi Intune z prośbą o przeniesienie, oraz w scenariuszu inicjowanym przez Microsoft, w którym firma Microsoft musi wprowadzić zmiany na zapleczu usługi. W trakcie **przenoszenia konta** dzierżawa działa w trybie tylko do odczytu (ROM). Operacje usług, takie jak rejestrowanie, zmiana nazwy urządzenia, aktualizowanie stanu zgodności, w okresie ROM zakończą się niepowodzeniem.

Ma to na celu wyeliminowanie pomyłek związanych z przypisaniem aplikacji do wielu grup o różnym przeznaczeniu.

Jeśli chcesz udostępnić aplikację w Portalu pracowników przetwarzających informacje i Portalu firmy przed wydaniem listopadowej wersji usługi, masz dwie opcje:

1. Usunięcie przypisania **Nie dotyczy** z grupy.
2. Utworzenie nowej grupy, która nie zawiera elementów członkowskich z przypisaniem **Wymagane i dostępne**, i przypisanie tej grupy jako **Nie dotyczy**.

Aby uzyskać więcej informacji, zobacz artykuł [How to assign apps to groups with Microsoft Intune](apps-deploy.md) (Jak przypisać aplikacje do grup w usłudze Microsoft Intune).

> [!Note]
> Po wydaniu nowej wersji nie będzie możliwe wyświetlanie ani modyfikowanie przypisań aplikacji w ramach zarządzania urządzeniami mobilnymi za pomocą konsoli klasycznej usługi Intune. Można jednak zarządzać przypisaniami aplikacji przy użyciu konsoli platformy Azure lub interfejsu API programu Intune Graph.

### <a name="configure-an-ios-app-pin----1586774---"></a>Konfigurowanie numeru PIN aplikacji dla systemu iOS <!-- 1586774 -->
Już wkrótce będzie można wymagać wprowadzenia numeru PIN dla aplikacji docelowych z systemem iOS. Wymaganie wprowadzenia numeru PIN i datę wygaśnięcia liczoną w dniach można skonfigurować za pośrednictwem witryny Azure Portal. W razie potrzeby będzie można narzucić wymaganie używania nowego numeru PIN w celu uzyskania dostępu do aplikacji dla systemu iOS. Ta funkcja będzie dostępna tylko dla aplikacji dla systemu iOS, dla których włączono ochronę aplikacji przy użyciu zestawu SDK aplikacji usługi Intune.

### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866--"></a>Aktualizacja środowiska użytkownika aplikacji Portal firmy dla systemu iOS <!--1412866-->

Niedługo wydamy dużą aktualizację środowiska użytkownika w aplikacji Portal firmy dla systemu iOS. Aktualizacja obejmie całkowicie nowy projekt wizualny, w tym zmodernizowany wygląd i działanie oraz większą użyteczność i dostępność. Cała obecna funkcjonalność aplikacji Portal firmy dla systemu iOS zostanie zachowana.

Za pośrednictwem programu Apple TestFlight oferujemy wersję wstępną zaktualizowanej aplikacji Portal firmy dla systemu iOS, aby umożliwić korzystanie z niej i przesyłanie opinii na jej temat. Zarejestruj się pod adresem https://aka.ms/intune_ios_cp_testflight, aby uzyskać dostęp do programu TestFlight. 

![wzbudzające ciekawość obrazy nowej aplikacji Portal firmy dla systemu iOS](./media/ios-cp-app-redesign-1801-teaser.png)

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Witryny internetowe usługi Azure Active Directory mogą wymagać aplikacji Intune Managed Browser i obsługiwać rejestrację jednokrotną w aplikacji Managed Browser (publiczna wersja zapoznawcza) <!-- 710595 -->   
Korzystając z usługi Azure Active Directory (Azure AD), można ograniczyć dostęp do witryn internetowych na urządzeniach przenośnych tylko do aplikacji Intune Managed Browser. W aplikacji Managed Browser dane witryn internetowych będą bezpieczne i odseparowane od osobistych danych użytkowników końcowych. Ponadto w przypadku witryn chronionych przez usługę Azure AD aplikacja Managed Browser będzie obsługiwać funkcje logowania jednokrotnego. Zarejestrowanie się w aplikacji Managed Browser lub korzystanie z aplikacji Managed Browser na urządzeniu z inną aplikacją zarządzaną przez usługę Intune umożliwia aplikacji Managed Browser dostęp do witryn firmowych chronionych przez usługę Azure AD bez konieczności wprowadzania poświadczeń użytkownika. Ta funkcja ma zastosowanie do witryn takich jak Outlook Web Access (OWA) i SharePoint Online, a także innych witryn firmowych, takich jak zasoby intranetowe dostępne za pośrednictwem serwera proxy aplikacji platformy Azure.

<!-- the following are present prior to 1709 -->
### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Narzędzia deweloperskie usług Intune App Protection i Citrix MDX <!-- 709185 -->
Urządzeniami i aplikacjami można zarządzać przy użyciu kombinacji usług Citrix XenMobile MDX i Microsoft Intune. Umożliwia ona zarządzanie aplikacjami za pomocą zasad usługi Intune App Protection przy równoczesnym wykorzystaniu technologii mVPN firmy Citrix.

Możesz odnaleźć repozytorium kodu, które zawiera narzędzie opakowujące aplikacje usługi Intune i zestawu Intune App SDK dla systemu iOS i Android zintegrowane z technologią mVPN Citrix MDX.

<!-- the following are present prior to 1711 -->

### <a name="redirecting-macos-users-to-the-new-company-portal-app---1380728--"></a>Przekierowywanie użytkowników systemu macOS do nowej aplikacji Portal firmy <!--1380728-->   
Gdy użytkownik końcowy zaloguje się do witryny internetowej Portal firmy, aby zarejestrować swoje urządzenie z systemem macOS, w celu ukończenia procesu zostanie przekierowany na stronę pobierania nowej aplikacji Portal firmy dla systemu macOS. Dotyczy to urządzeń z systemem macOS w wersji OS X El Capitan 10.11 lub nowszym. 

<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Obsługa aplikacji Intune Managed Browser dla systemu iOS i Android <!-- 1374196 -->
Od października 2017 r. aplikacja Intune Managed Browser w aplikacji dla systemu Android będzie obsługiwać tylko urządzenia z systemem Android 4.4 lub nowszym. Aplikacja Intune Managed Browser dla systemu iOS będzie obsługiwać wyłącznie urządzenia z systemem iOS 9.0 i nowszym. Wcześniejsze wersje systemu Android i iOS nadal mogą używać aplikacji Managed Browser, ale nie będą mogły instalować nowych wersji aplikacji i mogą nie być w stanie uzyskać dostępu do wszystkich możliwości aplikacji. Zachęcamy do zaktualizowania urządzeń do obsługiwanej wersji systemu operacyjnego.

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Ulepszony komunikat o błędzie, gdy użytkownik osiągnie maksymalną liczbę urządzeń, które można zarejestrować <!-- 1270370 -->
Zamiast ogólnego komunikatu o błędzie użytkownicy końcowi urządzeń z systemem Android zobaczą przyjazny komunikat o błędzie umożliwiający wykonanie akcji: „Zarejestrowano maksymalną liczbę urządzeń dozwoloną przez administratora IT. Usuń zarejestrowane urządzenie lub skontaktuj się z administratorem IT w celu uzyskania pomocy”.



## <a name="notices"></a>Uwagi

Aktualnie nie ma aktywnych powiadomień.



### <a name="see-also"></a>Zobacz też
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).


