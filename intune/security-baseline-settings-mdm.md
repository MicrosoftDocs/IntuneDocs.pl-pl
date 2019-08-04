---
title: Ustawienia punktów odniesienia zabezpieczeń usługi Intune dla systemu Windows 10
titleSuffix: Microsoft Intune
description: Przejrzyj wartości domyślne i dostępne ustawienia, które znajdują się w linii bazowej zabezpieczeń systemu Windows MDM dla urządzeń z systemem Windows 10 zarządzanych za pomocą usługi Intune.
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/25/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5565ce7a355136a749d79b52e4830af91684440a
ms.sourcegitcommit: 864fdf995c2b41f104a98a7e2665088c2864774f
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 07/31/2019
ms.locfileid: "68680039"
---
# <a name="mdm-security-baseline-settings-for-intune"></a>Ustawienia punktów odniesienia zabezpieczeń oprogramowania MDM dla usługi Intune  

Wyświetl ustawienia linii bazowej zabezpieczeń MDM obsługiwane przez Microsoft Intune dla urządzeń z systemem Windows 10 lub nowszym. Wartości domyślne dla ustawień w tej linii bazowej reprezentują zalecaną konfigurację dla odpowiednich urządzeń i mogą nie być zgodne z wartościami domyślnymi linii bazowej z innych linii bazowych zabezpieczeń.  

Najnowsza wersja linii bazowej to **linia bazowa zabezpieczeń MDM dla 2019 maja**  

Aby dowiedzieć się więcej o zmianach w najnowszej wersji tego planu bazowego z poprzedniej wersji, zobacz [co zmieniono w nowym szablonie](#whats-changed-in-the-new-template).  

> [!NOTE]  
> W czerwcu 2019 linia bazowa zabezpieczeń MDM (wersja zapoznawcza) została zastąpiona przez wydanie *linii bazowej zabezpieczeń mdm 2019 dla* programu, która jest ogólnie dostępna (nie w wersji zapoznawczej). Profile, które zostały utworzone przed udostępnieniem *linii bazowej zabezpieczeń MDM dla 2019 maja* , nie zostaną zaktualizowane w celu odzwierciedlenia ustawień i wartości, które znajdują się w linii bazowej zabezpieczeń MDM dla maja 2019 wersji.  Chociaż nie można tworzyć nowych profilów opartych na szablonie wersji zapoznawczej, można edytować i nadal używać wcześniej utworzonych profilów, które są oparte na szablonie wersji zapoznawczej.   
  
Aby dowiedzieć się więcej o korzystaniu z linii bazowych zabezpieczeń w usłudze Intune, zobacz [Korzystanie z linii bazowych zabezpieczeń](security-baselines.md).  


   
## <a name="above-lock"></a>Wyłączona blokada  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — AboveLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock) w dokumentacji systemu Windows.  

- **Blokuj wyświetlanie wyskakujących powiadomień**  
  To ustawienie zasad uniemożliwia wyświetlanie powiadomień aplikacji na ekranie blokady. Jeśli to ustawienie zasad zostanie włączone, na ekranie blokady nie będą wyświetlane powiadomienia aplikacji. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownicy będą mogli wybrać aplikacje, których powiadomienia są wyświetlane na ekranie blokady.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067101)  

  **Domyślne**: Tak  

- **Aktywuj aplikacje na zablokowanym ekranie**  

  **Domyślne**: wyłączone

## <a name="app-runtime"></a>Środowisko uruchomieniowe aplikacji    
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — AppRuntime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-appruntime
) w dokumentacji systemu Windows.  

- **Konta Microsoft opcjonalne dla aplikacji ze Sklepu Windows**  
  To ustawienie zasad umożliwia kontrolowanie, czy konta Microsoft są opcjonalne dla aplikacji ze Sklepu Windows, które wymagają konta do zalogowania. Te zasady dotyczy tylko aplikacji ze Sklepu Windows, które je obsługują. Jeśli to ustawienie zasad zostanie włączone, aplikacje ze Sklepu Windows, które zwykle wymagają konta Microsoft do zalogowania się, umożliwią użytkownikom logowanie się za pomocą konta przedsiębiorstwa. Jeśli to ustawienie zasad jest wyłączone lub nieskonfigurowane, użytkownicy muszą logować się przy użyciu konta Microsoft.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067104)  
  
  **Domyślne**: włączone  

## <a name="application-management"></a>Zarządzanie aplikacjami   
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — ApplicationManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement) w dokumentacji systemu Windows.  

- **Blokuj kontrolę użytkownika nad instalacjami**  
  To ustawienie zasad umożliwia użytkownikom zmianę opcji instalacji, które zwykle są dostępne tylko dla administratorów systemu. Jeśli włączysz to ustawienie zasad, niektóre funkcje zabezpieczeń Instalator Windows są pomijane. Zezwala na ukończenie instalacji, które w przeciwnym razie zostałyby zatrzymane ze względu na naruszenie zabezpieczeń. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, funkcje zabezpieczeń Instalator Windows uniemożliwiają użytkownikom zmianę opcji instalacji zwykle zarezerwowanych dla administratorów systemu, takich jak określenie katalogu, do którego pliki są zainstalowane. Jeśli Instalator Windows wykryje, że pakiet instalacyjny zezwolił użytkownikowi na zmianę opcji chronionej, zatrzyma instalację i wyświetli komunikat. Te funkcje zabezpieczeń działają tylko wtedy, gdy program instalacyjny jest uruchomiony w kontekście zabezpieczeń uprzywilejowanych, w którym ma dostęp do katalogów zabronionych dla użytkownika. To ustawienie zasad jest przeznaczone dla mniej restrykcyjnych środowisk. Może służyć do obejścia błędów w programie instalacyjnym, który uniemożliwia instalację oprogramowania.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067060)  

  **Domyślne**: Tak

- **Blokuj instalacje aplikacji MSI z podniesionymi uprawnieniami**  
  To ustawienie zasad zezwala Instalatorowi Windows na użycie podniesionych uprawnień podczas instalowania dowolnego programu w systemie.  
  - *Włączenie tego ustawienia zasad*spowoduje, że uprawnienia zostaną rozszerzone na wszystkie programy. Te uprawnienia są zwykle zastrzeżone dla programów przypisanych do użytkownika (oferowanych na pulpicie), przypisanych do komputera (instalowanych automatycznie) f lub dostępnych w aplecie Dodaj lub usuń programy w panelu sterowania. To ustawienie profilu umożliwia użytkownikom instalowanie programów, które wymagają dostępu do katalogów, do których użytkownik może nie mieć uprawnień do wyświetlania lub zmieniania, w tym katalogów na komputerach z wysoce ograniczonymi uprawnieniami.
  - *Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane*, system zastosuje uprawnienia bieżącego użytkownika podczas instalowania programów niedystrybuowanych lub oferowanych przez administratora systemu. Uwaga: to ustawienie zasad jest dostępne w folderach Konfiguracja komputera i Konfiguracja użytkownika. Aby to ustawienie zasad zaczęło obowiązywać, należy włączyć je w obu folderach. Uwaga: Użytkownicy z wykwalifikowanymi użytkownikami mogą korzystać z uprawnień tych ustawień zasad, aby zmienić ich uprawnienia i uzyskać stały dostęp do ograniczonych plików i folderów. Należy pamiętać, że nie ma gwarancji, że wersja konfiguracji użytkownika tego ustawienia zasad nie jest bezpieczna.  
  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067134)    

  **Domyślne**: Tak

- **Blokuj DVR z gry (tylko dla komputerów stacjonarnych)**  
  Pozwala określić, czy nagrania i emisje z gier są dozwolone.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067056)  
  
  **Domyślne**: Tak  

## <a name="auto-play"></a>Autoodtwarzanie   
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — Autoplay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-autoplay) w dokumentacji systemu Windows.  

- **Domyślne zachowanie automatycznego uruchamiania funkcji autoodtwarzania**  
  To ustawienie ma wpływ na domyślne zachowanie poleceń Autorun. Polecenia Autorun są przechowywane w plikach autorun.inf i umożliwiają uruchamianie programów instalacyjnych lub innych procedur. Gdy jest ustawiona wartość *Włączone*, administratorzy mogą zmienić domyślne zachowanie automatycznego uruchamiania w urządzeniu z systemem Windows Vista lub nowszym. Możesz ustawić następujące zachowanie: a) całkowite wyłączenie poleceń autorun lub b) przywrócenie zachowania automatycznego wykonywania poleceń autorun z systemów starszych niż Windows Vista. Jeśli ustawisz wartość *Wyłączone* lub *Nie skonfigurowano*, w urządzeniach z systemem Windows Vista lub nowszym użytkownicy otrzymają monit o to, czy polecenia autorun mają być uruchamiane.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067133)       
  
  **Domyślne**: Nie wykonuj  
  
- **Tryb autoodtwarzania**  
  To ustawienie zasad umożliwia wyłączenie funkcji autoodtwarzania. Autoodtwarzanie rozpoczyna odczyt z dysku zaraz po włożeniu nośnika do stacji. W rezultacie plik konfiguracji programów i muzyka na nośniku audio są uruchamiane natychmiast. W systemach starszych niż Windows XP z dodatkiem SP2 autoodtwarzanie jest domyślnie wyłączone w przypadku stacji dysków wymiennych, takich jak stacja dyskietek (ale nie stacja CD-ROM), i dysków sieciowych. Począwszy od systemu Windows XP z dodatkiem SP2, autoodtwarzanie jest też włączone dla dysków wymiennych, łącznie ze stacjami Zip i niektórymi urządzeniami pamięci masowej USB. Jeśli to ustawienie zasad zostanie włączone, autoodtwarzanie zostanie wyłączone dla stacji CD-ROM i stacji nośników wymiennych lub wyłączone dla wszystkich stacji. To ustawienie zasad powoduje wyłączenie autoodtwarzania dla dodatkowych typów dysków. To ustawienie nie służy do włączania autoodtwarzania dla dysków, dla których jest ono domyślnie wyłączone. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, autoodtwarzanie zostanie włączone. Uwaga: to ustawienie zasad jest dostępne w folderach Konfiguracja komputera i Konfiguracja użytkownika. Jeśli ustawienia zasad powodują konflikt, ustawienie zasad w konfiguracji komputera ma pierwszeństwo przed ustawieniem zasad w konfiguracji użytkownika.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2066793)  
  
  **Domyślne**: wyłączone

- **Blokuj autoodtwarzanie w urządzeniach niezawierających woluminów**  
  To ustawienie zasad blokuje autoodtwarzanie w urządzeniach MTP, takich jak aparaty fotograficzne i telefony. Jeśli to ustawienie zasad zostanie włączone, autoodtwarzanie nie będzie dozwolone w urządzeniach MTP, takich jak aparaty fotograficzne i telefony. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, autoodtwarzanie zostanie włączone w urządzeniach niezawierających woluminów.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067106)    
  
  **Domyślne**: włączone  

## <a name="bitlocker"></a>Bitlocker    
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — Bitlocker](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bitlocker
) w dokumentacji systemu Windows.  

- **Zasady dysków wymiennych funkcji BitLocker**  
  To ustawienie zasad pozwala określić metodę i siłę szyfrowania. Wartości tych zasad określają siłę szyfrowania funkcji BitLocker. Przedsiębiorstwa mogą kontrolować poziom szyfrowania w celu zwiększenia bezpieczeństwa (szyfrowanie AES-256 jest silniejsze niż szyfrowanie AES-128). Jeśli to ustawienie zostanie włączone, będzie można skonfigurować algorytm szyfrowania i siłę klucza szyfrowania osobno dla stałych dysków danych, dysków systemu operacyjnego i wymiennych dysków danych. W przypadku dysków stałych i dysków systemu operacyjnego zalecamy użycie algorytmu XTS-AES. W przypadku dysków wymiennych użyj 128-bitowego lub 256-bitowego szyfrowania AES-CBC, jeśli dysk jest używany w innych urządzeniach, które nie mają systemu Windows 10 w wersji 1511 lub nowszej. Metoda szyfrowania nie zmienia się, jeśli dysk jest już zaszyfrowany lub jeśli szyfrowanie jest w toku. W takich przypadkach to ustawienie zasad jest ignorowane.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067140) 

  W przypadku zasad dysków wymiennych funkcji BitLocker skonfiguruj następujące ustawienie:

  - **Wymagaj szyfrowania do zapisu**  
    **Domyślne**: Tak  
  

## <a name="browser"></a>Przeglądarka  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — przeglądarka](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser) w dokumentacji systemu Windows.  

- **Wymagaj filtra SmartScreen dla programu Microsoft Edge**  
  Program Microsoft Edge domyślnie używa filtra SmartScreen w usłudze Windows Defender, aby chronić użytkowników przed potencjalnym wyłudzeniem informacji i złośliwym oprogramowaniem. Ponadto domyślnie użytkownicy nie mogą wyłączyć filtra SmartScreen w usłudze Windows Defender. Włączenie tych zasad powoduje wyłączenie filtra SmartScreen w usłudze Windows Defender i uniemożliwia użytkownikom włączenie go. Nie konfiguruj tych zasad, aby umożliwić użytkownikom wybór, czy filtr SmartScreen w usłudze Windows Defender ma być włączony.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067029)   
  
  **Domyślne**: Tak  
  
- **Blokuj dostęp do złośliwych witryn**  
  Domyślnie program Microsoft Edge pozwala użytkownikom pomijać (ignorować) ostrzeżenia filtru SmartScreen w usłudze Windows Defender dotyczące potencjalnie złośliwych witryn, dzięki czemu mogą kontynuować korzystanie z witryny. Jednak za pomocą tych zasad można skonfigurować program Microsoft Edge, aby uniemożliwiał użytkownikom pomijanie ostrzeżeń i dalsze korzystanie z witryny.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067040)   
  
  **Domyślne**: Tak  
  
- **Blokowanie pobierania niezweryfikowanych plików**  
  Domyślnie program Microsoft Edge pozwala użytkownikom pomijać (ignorować) ostrzeżenia filtru SmartScreen w usłudze Windows Defender dotyczące potencjalnie złośliwych plików, dzięki czemu mogą kontynuować pobieranie niezweryfikowanych plików. Włączenie tych zasad uniemożliwia użytkownikom pomijanie ostrzeżeń, przez co nie mogą pobierać niezweryfikowanych plików.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067023)  
  
  **Domyślne**: Tak  
  
- **Blokuj menedżera haseł**  
  Domyślnie program Microsoft Edge automatycznie używa menedżera haseł, co pozwala użytkownikom zarządzać hasłami lokalnie. Wyłączenie tych zasad ogranicza używanie menedżera haseł przez program Microsoft Edge. Nie konfiguruj tych zasad, jeśli chcesz, aby użytkownicy mogli zapisywać hasła i zarządzać nimi lokalnie przy użyciu menedżera haseł.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067128)  
  
  **Domyślne**: Tak  
  
- **Uniemożliwiaj przesłonięcia błędów certyfikatu**  
  To ustawienie zasad uniemożliwia użytkownikowi ignorowanie błędów certyfikatu Secure Sockets Layer/Transport Layer Security (SSL/TLS), które przerywają przeglądanie (na przykład błędy z powodu wygaśnięcia, odwołania lub niezgodności nazwy) w programie Internet Explorer. Jeśli to ustawienie zasad zostanie włączone, użytkownik nie będzie mógł kontynuować przeglądania. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownik będzie mógł ignorować błędy certyfikatu i kontynuować przeglądanie.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067126)  
  
  **Domyślne**: Tak  

## <a name="connectivity"></a>Łączność  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — łączność](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity) w dokumentacji systemu Windows.  

- **Blokuj pobieranie internetowe przez Kreatora publikacji internetowej i Kreatora zamawiania online**  
  To ustawienie zasad określa, czy system Windows ma pobierać listę dostawców dla Kreatora publikacji internetowej i Kreatora zamawiania online. Te kreatory pozwalają użytkownikom wybrać z listy firmę, która świadczy takie usługi jak magazyn online i drukowanie zdjęć. Domyślnie oprócz dostawców określonych w rejestrze w systemie Windows jest także wyświetlana lista dostawców pobrana z witryny internetowej systemu Windows. Włączenie tego ustawienia zasad spowoduje, że system Windows nie będzie pobierać listy dostawców i będą wyświetlani tylko dostawcy usług zapisywani w pamięci podręcznej w rejestrze lokalnym. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, lista dostawców zostanie pobrana po użyciu przez użytkownika Kreatora publikacji internetowej lub Kreatora zamawiania online. Więcej informacji, w tym szczegółowe informacje na temat określania dostawców usług w rejestrze, można znaleźć w dokumentacji Kreatora publikacji internetowej i Kreatora zamawiania online.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067136)  
  
  **Domyślne**: włączone  

- **Blokuj pobieranie sterowników wydruku przez HTTP**  
  To ustawienie zasad określa, czy zezwalać temu klientowi na pobieranie pakietów sterowników wydruku przez HTTP. Aby skonfigurować drukowanie HTTP, należy pobrać przez HTTP sterowniki inne niż te, które były dostarczone z systemem. Uwaga: to ustawienie zasad nie blokuje klientowi możliwości drukowania za pomocą drukarek w intranecie lub Internecie przez HTTP. Uniemożliwia tylko pobieranie sterowników, które nie są już zainstalowane lokalnie. Jeśli to ustawienie zasad zostanie włączone, nie będzie można pobierać sterowników drukarek przez HTTP. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownicy będą mogli pobierać sterowniki drukarek przez HTTP.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067141)  
  
  **Domyślne**: włączone  

## <a name="credentials-delegation"></a>Delegowanie poświadczeń  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — CredentialsDelegation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsdelegation
) w dokumentacji systemu Windows.  

- **Delegowanie zdalnego hosta poświadczeń bez możliwości eksportowania**  
  Host zdalny umożliwia delegowanie poświadczeń, których nie można eksportować. W przypadku korzystania z delegowania poświadczeń urządzenia dostarczają możliwą do wyeksportowania wersję poświadczeń do hosta zdalnego, co wystawia użytkowników na ryzyko kradzieży poświadczeń przez osoby atakujące ten host zdalny. Jeśli to ustawienie zasad zostanie włączone, host będzie obsługiwać tryb administratora z ograniczonym dostępem lub tryb zdalnej funkcji Credential Guard. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, tryb administratora z ograniczonym dostępem i tryb zdalnej funkcji Credential Guard nie będą obsługiwane. Użytkownik zawsze będzie musiał przekazywać poświadczenia do hosta.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067103)   
  
  **Domyślne**: włączone  

## <a name="credentials-ui"></a>Interfejs użytkownika poświadczeń  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — CredentialsUI](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsui) w dokumentacji systemu Windows.  

- **Wyliczanie administratorów** To ustawienie zasad określa, czy podczas próby podniesienia poziomu uruchomionej aplikacji przez użytkownika mają być wyświetlane konta administratorów. Domyślnie podczas próby podniesienia poziomu uruchomionej aplikacji przez użytkownika konta administratorów nie są wyświetlane. Jeśli to ustawienie zasad jest włączone, wszystkie konta administratorów lokalnych na komputerze są wyświetlane, dzięki czemu użytkownik może wybrać jedno z nich i wprowadzić poprawne hasło. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy będą zawsze musieli wpisać nazwę użytkownika i hasło, aby podnieść poziom.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067021)

  
  **Domyślne**: wyłączone  

## <a name="data-protection"></a>Ochrona danych  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — DataProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection
) w dokumentacji systemu Windows.  

- **Blokuj bezpośredni dostęp do pamięci**  
  To ustawienie zasad umożliwia zablokowanie bezpośredniego dostępu do pamięci dla wszystkich podrzędnych portów PCI z możliwością podłączenia podczas pracy, dopóki użytkownik nie zaloguje się do systemu Windows. Po zalogowaniu się przez użytkownika system Windows wyliczy urządzenia PCI podłączone do portów PCI podłączenia hosta. Za każdym razem, gdy użytkownik zablokuje maszynę, bezpośredni dostęp do pamięci zostaje zablokowany na portach PCI z możliwością podłączenia podczas pracy bez urządzeń podrzędnych, dopóki użytkownik nie zaloguje się ponownie. Urządzenia, które były już wyliczone po odblokowaniu maszyny, będą w dalszym ciągu działać do czasu odłączenia. To ustawienie zasad jest wymuszane tylko wtedy, gdy jest włączone szyfrowanie funkcją BitLocker lub szyfrowanie urządzenia.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067031)     
  
  **Domyślne**: Tak  

## <a name="device-guard"></a>Device Guard  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — DeviceGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceguard
) w dokumentacji systemu Windows.  

- **Credential Guard**  
  To ustawienie umożliwia użytkownikom włączenie funkcji Credential Guard z zabezpieczeniami opartymi na wirtualizacji, aby pomóc chronić poświadczenia przy następnym ponownym uruchomieniu.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067044)
   
  **Domyślne**: Włącz z blokadą UEFI 

- **Włącz zabezpieczenia oparte na wirtualizacji**   
  Włącza zabezpieczenia oparte na wirtualizacji (VBS) podczas następnego rozruchu. Zabezpieczenia oparte na wirtualizacji używają funkcji Hypervisor systemu Windows, aby zapewniać obsługę usług zabezpieczeń.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067066)  
  
  **Domyślne**: Tak  


- **Uruchom ochronę systemu**    
  **Domyślne**: włączone  

## <a name="device-installation"></a>Instalacja urządzenia  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — DeviceInstallation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation) w dokumentacji systemu Windows.  

- **Instalacja urządzeń sprzętowych według identyfikatorów urządzeń**  
  To ustawienie zasad umożliwia określenie listy identyfikatorów sprzętu Plug and Play i zgodnych identyfikatorów urządzeń, których nie można zainstalować w systemie Windows. To ustawienie zasad ma pierwszeństwo przed innymi ustawieniami zasad, które umożliwiają zainstalowanie urządzenia w systemie Windows. Jeśli to ustawienie zasad zostanie włączone, system Windows nie będzie mógł zainstalować urządzenia, którego identyfikator sprzętu lub zgodny identyfikator jest na utworzonej przez Ciebie liście. Jeśli włączysz to ustawienie zasad na serwerze usług pulpitu zdalnego, będzie ono wpływać na przekierowywanie określonych urządzeń z klienta usług pulpitu zdalnego na serwer usług pulpitu zdalnego. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, urządzenia będą mogły zostać zainstalowane i zaktualizowane zgodnie z innymi ustawieniami zasad.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2066794)  
  
  **Domyślne**: blokuj instalację urządzeń sprzętowych  

  W przypadku wybrania pozycji *Blokuj instalację urządzeń sprzętowych* są dostępne następujące ustawienia.

  - **Usuń zgodne urządzenia sprzętowe**   
    To ustawienie jest dostępne tylko wtedy, gdy ustawienie *Instalacja urządzeń sprzętowych według identyfikatorów urządzeń* ma wartość *Blokuj instalację urządzeń sprzętowych*.
    
    **Domyślne**: Tak

  - **Zablokowane identyfikatory urządzeń sprzętowych**  
    To ustawienie jest dostępne tylko wtedy, gdy ustawienie *Instalacja urządzeń sprzętowych według identyfikatorów urządzeń* ma wartość *Blokuj instalację urządzeń sprzętowych*.
    
    **Domyślne**: Tak  
  
- **Instalacja urządzeń sprzętowych według klas konfiguracji**  
  To ustawienie zasad umożliwia określenie listy unikatowych identyfikatorów globalnych (GUID) klas konfiguracji urządzeń dla sterowników urządzeń, których nie można zainstalować w systemie Windows. To ustawienie zasad ma pierwszeństwo przed innymi ustawieniami zasad, które umożliwiają zainstalowanie urządzenia w systemie Windows. Jeśli to ustawienie zasad zostanie włączone, system Windows nie będzie mógł instalować ani aktualizować sterowników urządzeń, których identyfikatory GUID klas konfiguracji urządzeń są na utworzonej przez Ciebie liście. Jeśli włączysz to ustawienie zasad na serwerze usług pulpitu zdalnego, będzie ono wpływać na przekierowywanie określonych urządzeń z klienta usług pulpitu zdalnego na serwer usług pulpitu zdalnego. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, system Windows będzie mógł instalować i aktualizować urządzenia zgodnie z innymi ustawieniami zasad.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067048)  
  
  **Domyślne**: blokuj instalację urządzeń sprzętowych  

  W przypadku wybrania pozycji *Blokuj instalację urządzeń sprzętowych* są dostępne następujące ustawienia.
  - **Usuń zgodne urządzenia sprzętowe**    
    To ustawienie jest dostępne tylko wtedy, gdy ustawienie *Instalacja urządzeń sprzętowych według klas konfiguracji* ma wartość *Blokuj instalację urządzeń sprzętowych*.  

    **Domyślne:** : *brak konfiguracji domyślnej*  

  - **Zablokowane identyfikatory urządzeń sprzętowych**  
    To ustawienie jest dostępne tylko wtedy, gdy ustawienie *Instalacja urządzeń sprzętowych według klas konfiguracji* ma wartość *Blokuj instalację urządzeń sprzętowych*.
    
    **Domyślne:** : *brak konfiguracji domyślnej*  

## <a name="device-lock"></a>Blokada urządzenia  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — DeviceLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock) w dokumentacji systemu Windows.  

- **Uniemożliwiaj używanie aparatu fotograficznego**  
  Wyłącza przełącznik aparatu na ekranie blokady w ustawieniach komputera i uniemożliwia wywoływanie aparatu na ekranie blokady. Domyślnie użytkownicy mogą włączyć wywoływanie dostępnego aparatu na ekranie blokady. Jeśli to ustawienie zostanie włączone, użytkownicy nie będą mogli włączyć ani wyłączyć dostępu do aparatu na ekranie blokady w ustawieniach komputera i nie będzie można wywołać aparatu na ekranie blokady.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067052)
  
  **Domyślne**: włączone  

- **Wymagaj hasła**  
  Określa, czy blokada urządzenia jest włączona.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067049)  
  
  **Domyślne**: Tak  
  
  Jeśli pozycja *Wymagaj hasła* została ustawiona na *Tak*, są dostępne następujące ustawienia.

  - **Minimalna liczba zestawów znaków hasła**  
    Liczba typów elementów (dużych i małych liter, liczb oraz znaków interpunkcyjnych) wymaganych do uznania hasła lub numeru PIN za silne. Numer PIN wymusza następujące zachowanie na komputerach stacjonarnych i urządzeniach przenośnych: 1 — Tylko cyfry 2 — Cyfry i małe litery są wymagane 3 — Cyfry, małe i wielkie litery są wymagane. Nie jest obsługiwane przez klasyczne konta Microsoft i konta domen. 4 — Cyfry, małe i wielkie litery oraz znaki specjalne są wymagane. Nieobsługiwane w wersji klasycznej. Wartość domyślna to 1.  
    [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067055)  
    
    **Domyślne**: 3  

  - **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia**  
    Liczba dozwolonych błędów uwierzytelniania przed wyczyszczeniem urządzenia. Wartość 0 powoduje wyłączenie funkcji czyszczenia urządzenia.  
    [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067030)  
      
    **Domyślne**: 10  

  - **Dni do wygaśnięcia hasła**  
    Ustawienie zasad maksymalnego wieku hasła określa, jak długo (w dniach) można używać hasła, zanim system będzie wymagać od użytkownika zmiany hasła. Możesz ustawić, aby hasła wygasały po pewnej liczbie dni (od 1 do 999), lub aby nigdy nie wygasały (ustawienie 0 dni). Jeśli maksymalny wiek hasła wynosi od 1 do 999 dni, minimalny wiek hasła musi być mniejszy niż maksymalny wiek hasła. Jeśli maksymalny wiek hasła jest równy 0, minimalny wiek hasła może być dowolną wartością od 0 do 998 dni.  
    [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067028)  
    
    **Domyślne**: 60  

  - **Wymagany typ hasła**  
    Określa wymagany typ numeru PIN lub hasła.  
    [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067027)  
    
    **Domyślne**: Alfanumeryczne  

  - **Minimalna długość hasła**  
    Ustawienie zasad minimalnej długości hasła określa najmniejszą dozwoloną liczbę znaków hasła konta użytkownika. Możesz ustawić wartość z zakresu od 1 do 14 znaków lub określić, że hasło nie jest wymagane, przez ustawienie wartości 0 znaków.  
    [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067024)  
    
    **Domyślne**: 8  

  - **Blokuj proste hasła**  
    Określa, czy dozwolone są numery PIN i hasła, takie jak „1111” lub „1234”. W wersji klasycznej steruje również użyciem haseł obrazkowych.  
    [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067127) 
    
    **Domyślne**: Tak  
      *Ustawienie Tak uniemożliwia używanie prostych haseł.* 

  - **Zapobiegaj ponownemu używaniu poprzednich haseł**  
    Określa, ile haseł, których nie można użyć, ma być przechowywanych w historii. Wartość zawiera bieżące hasło użytkownika. Na przykład ustawienie *1* powoduje, że użytkownik nie może ponownie użyć swojego bieżącego hasła podczas wybierania nowego hasła. Ustawienie *5* oznacza, że użytkownik nie może ustawić nowego hasła na bieżące hasło ani na dowolne z czterech poprzednich haseł.  
    [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2066795)  
    
    **Domyślne**: 24  

- **Blokuj pokaz slajdów**  
  Wyłącza ustawienia pokazu slajdów na ekranie blokady w ustawieniach komputera i uniemożliwia odtwarzanie pokazu slajdów na ekranie blokady. Domyślnie użytkownicy mogą włączyć pokaz slajdów, który będzie uruchamiany po zablokowaniu maszyny. Jeśli to ustawienie zostanie włączone, użytkownicy nie mogą modyfikować ustawień pokazu slajdów w ustawieniach komputera i nie można uruchomić żadnego pokazu slajdów.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067105) 
  
  **Domyślne**: włączone  
  *Ustawienie Włączone uniemożliwia uruchamianie pokazów slajdów.* 

- **Minimalny wiek hasła w dniach**  
  Ustawienie zasad minimalnego wieku hasła określa czas (w dniach), przez który trzeba używać hasła, zanim będzie możliwa zmiana hasła. Możesz ustawić wartość z zakresu od 1 do 998 dni lub umożliwić zmianę hasła od razu przez ustawienie 0 dni. Minimalny wiek hasła musi być mniejszy niż maksymalny wiek hasła, chyba że maksymalny wiek hasła jest równy 0, co oznacza, że hasła nigdy nie wygasają. Jeśli maksymalny wiek hasła jest równy 0, minimalny wiek hasła może być dowolną wartością od 0 do 998.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067022) 
  
  **Domyślne**: 1  

## <a name="dma-guard"></a>DMA Guard  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — DmaGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard) w dokumentacji systemu Windows.
- **Wyliczanie urządzeń zewnętrznych niezgodnych z ochroną DMA jądra**  
  Te zasady mają na celu zapewnienie dodatkowych zabezpieczeń przed zewnętrznymi urządzeniami z obsługą DMA. Zapewniają one lepszą kontrolę nad wyliczaniem zewnętrznych urządzeń obsługujących technologię DMA, które są niezgodne z ponownym mapowaniem/izolacją pamięci urządzenia przy użyciu technologii DMA. Te zasady są stosowane tylko wtedy, gdy ochrona DMA jądra jest obsługiwana i włączana przez systemowe oprogramowanie układowe. Ochrona przed jądrem jest funkcją platformy, która nie może być kontrolowana za pośrednictwem zasad ani przez użytkownika końcowego. Musi ona być obsługiwana przez system w momencie produkcji. Aby sprawdzić, czy system obsługuje ochronę przed jądrem DMA, sprawdź pole jądra ochrony DMA na stronie Podsumowanie programu MSINFO32. exe.  
  [Dowiedz się więcej](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard#dmaguard-deviceenumerationpolicy)

  **Domyślne**: Blokuj wszystko   

## <a name="event-log-service"></a>Usługa dziennika zdarzeń  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — EventLogService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-eventlogservice) w dokumentacji systemu Windows.  

- **Maksymalny rozmiar pliku dziennika zabezpieczeń w KB**  
  To ustawienie zasad określa maksymalny rozmiar pliku dziennika w kilobajtach. Jeśli to ustawienie zasad zostanie włączone, będzie można skonfigurować maksymalny rozmiar pliku dziennika od 1 megabajta (1024 kilobajtów) do 2 terabajtów (2147483647 kilobajtów) w kilobajtowych przyrostach. Jeśli to ustawienie zasad jest wyłączone lub nieskonfigurowane, jako maksymalny rozmiar pliku dziennika jest ustawiona lokalnie skonfigurowana wartość. Tę wartość może zmienić administrator lokalny w oknie dialogowym Właściwości dziennika — wartość domyślna to 20 megabajtów.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067042)  
  
   **Domyślne**: 196608  

- **Maksymalny rozmiar pliku dziennika systemu w KB**  
  To ustawienie zasad określa maksymalny rozmiar pliku dziennika w kilobajtach. Jeśli to ustawienie zasad zostanie włączone, będzie można skonfigurować maksymalny rozmiar pliku dziennika od 1 megabajta (1024 kilobajtów) do 2 terabajtów (2147483647 kilobajtów) w kilobajtowych przyrostach. Jeśli to ustawienie zasad jest wyłączone lub nieskonfigurowane, jako maksymalny rozmiar pliku dziennika jest ustawiona lokalnie skonfigurowana wartość. Tę wartość może zmienić administrator lokalny w oknie dialogowym Właściwości dziennika — wartość domyślna to 20 megabajtów.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2066798)  
  
  **Domyślne**: 32768  

- **Maksymalny rozmiar pliku dziennika aplikacji w KB**  
  To ustawienie zasad określa maksymalny rozmiar pliku dziennika w kilobajtach. Jeśli to ustawienie zasad zostanie włączone, będzie można skonfigurować maksymalny rozmiar pliku dziennika od 1 megabajta (1024 kilobajtów) do 2 terabajtów (2147483647 kilobajtów) w kilobajtowych przyrostach. Jeśli to ustawienie zasad jest wyłączone lub nieskonfigurowane, jako maksymalny rozmiar pliku dziennika jest ustawiona lokalnie skonfigurowana wartość. Tę wartość może zmienić administrator lokalny w oknie dialogowym Właściwości dziennika — wartość domyślna to 20 megabajtów.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067125)  
  
  **Domyślne**: 32768  

## <a name="experience"></a>Środowisko użytkownika  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — środowisko](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience) w dokumentacji systemu Windows.  

- **Blokuj funkcję W centrum uwagi Windows**  
  Umożliwia administratorom IT wyłączenie wszystkich funkcji W centrum uwagi Windows — W centrum uwagi Windows na ekranie blokady, porad dotyczących systemu Windows, funkcji firmy Microsoft dla konsumentów i innych powiązanych funkcji.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067037)  
  
  **Domyślne**: Tak  

  Jeśli pozycja *Blokuj funkcję W centrum uwagi Windows* została ustawiona na *Tak*, są dostępne następujące ustawienia.
  
  - **Blokuj sugestie innych firm w funkcji W centrum uwagi Windows**  
    Określa, czy zezwalać na sugestie dotyczące aplikacji i zawartości pochodzące od innych wydawców oprogramowania w funkcjach W centrum uwagi Windows, takich jak W centrum uwagi na ekranie blokady, sugerowane aplikacje w menu Start i porady dotyczące systemu Windows. Użytkownicy mogą nadal otrzymywać sugestie dotyczące funkcji, aplikacji i usług firmy Microsoft.  
    [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067045)  
      
    **Domyślne**: Tak  
  - **Blokuj funkcje dla konsumentów**  
    Umożliwia administratorom IT włączanie funkcji przeznaczonych zwykle tylko dla konsumentów, takich jak sugestie w menu Start, powiadomienia dotyczące członkostwa, instalacja aplikacji po uruchomieniu środowiska OOBE i kafelki przekierowania.  
    [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067054)  
     
    **Domyślne**: Tak  

## <a name="exploit-guard"></a>Exploit Guard  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — ExploitGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-exploitguard) w dokumentacji systemu Windows.  

- **Plik XML ochrony przed programami wykorzystującymi luki w zabezpieczeniach**  
  Umożliwia administratorowi IT wypchnięcie konfiguracji reprezentującej środki zaradcze dla żądanego systemu i żądanej aplikacji do wszystkich urządzeń w organizacji. Konfiguracja jest reprezentowana przez kod XML. Ochrona przed programami wykorzystującymi luki w zabezpieczeniach pomaga chronić urządzenia przed złośliwym oprogramowaniem, które rozpowszechnia się i infekuje za pomocą programów wykorzystujących luki w zabezpieczeniach. Aby utworzyć zestaw środków zaradczych (nazywanych konfiguracją), użyj aplikacji zabezpieczeń systemu Windows lub programu PowerShell. Możesz następnie wyeksportować tę konfigurację w pliku XML i udostępnić ją w wielu maszynach w sieci, aby wszystkie z nich korzystały z tego samego zestawu ustawień ograniczania ryzyka. Możesz też przekonwertować i zaimportować istniejący plik XML konfiguracji EMET do pliku XML konfiguracji ochrony.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067035)  
  
  **Domyślne**: *Podano przykładowy plik XML* 
 
## <a name="file-explorer"></a>Eksplorator plików  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — FileExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-fileexplorer) w dokumentacji systemu Windows.  

- **Blokuj zapobieganie wykonywaniu danych**  
  Wyłączenie zapobiegania wykonywaniu danych umożliwia niektórym starszym aplikacjom wtyczek działanie bez zamykania Eksploratora.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067043)  
  
  **Domyślne**: wyłączone  
   
- **Blokuj zakończenie sterty w przypadku uszkodzenia**  
  Wyłączenie zakończenia sterty w przypadku uszkodzenia umożliwia niektórym starszym aplikacjom wtyczek działanie bez natychmiastowego zamykania Eksploratora, mimo że Eksplorator może nadal nieoczekiwane zakończyć działanie później.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067107)  
  
  **Domyślne**: wyłączone  
    

## <a name="internet-explorer"></a>Internet Explorer  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — InternetExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-internetexplorer) w dokumentacji systemu Windows.  

- **Aktualizacje paska stanu za pomocą skryptu w strefie z ograniczeniami programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie tym, czy skrypt może aktualizować pasek stanu w obrębie strefy. 
  - *Jeśli to ustawienie zasad zostanie włączone*, skrypt będzie mógł aktualizować pasek stanu.
  - *Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane*, skrypt nie będzie mógł aktualizować paska stanu.  

  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067074)  

  **Domyślne**: wyłączone

- **Przeciąganie i upuszczanie lub kopiowanie i wklejanie plików w strefie internetowej w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie tym, czy użytkownicy będą mogli przeciągać pliki lub kopiować i wklejać pliki ze źródła w strefie. Jeśli to ustawienie zasad zostanie włączone, użytkownicy będą mogli automatycznie przeciągać pliki lub kopiować i wklejać pliki z tej strefy. Jeśli w polu listy rozwijanej zostanie wybrana wartość Monit, użytkownicy będą proszeni o wybranie, czy przeciągać lub kopiować pliki z tej strefy. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli przeciągać plików ani kopiować i wklejać plików z tej strefy. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy będą mogli automatycznie przeciągać pliki lub kopiować i wklejać pliki z tej strefy.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067076)  

  **Domyślne**: Wyłącz

- **Składniki uzależnione od platformy .NET Framework w strefie z ograniczeniami w programie Internet Explorer**    
  To ustawienie zasad umożliwia zarządzanie tym, czy składniki .NET Framework, które nie są podpisane przy użyciu technologii Authenticode, mogą być wykonywane w programie Internet Explorer. Do tych składników należą zarządzane kontrolki przywoływane z tagu obiektu oraz zarządzane pliki wykonywalne przywoływane z linku. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer będzie wykonywał niepodpisane składniki zarządzane. Jeśli w polu listy rozwijanej wybierzesz wartość Monituj, program Internet Explorer będzie prosił użytkownika o określenie, czy może wykonywać niepodpisane składniki zarządzane. Jeśli to ustawienie zasad zostanie wyłączone, program Internet Explorer nie będzie wykonywał niepodpisanych składników zarządzanych. Jeśli to ustawienie zasad nie zostanie skonfigurowane, program Internet Explorer nie będzie wykonywać niepodpisanych składników zarządzanych.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067077)

  **Domyślne**: Wyłącz


- **Strefa Komputer lokalny w programie Internet Explorer nie uruchamia oprogramowania chroniącego przed złośliwym oprogramowaniem względem kontrolek ActiveX**  
  To ustawienie zasad określa, czy program Internet Explorer uruchamia programy chroniące przed złośliwym oprogramowaniem względem kontrolek ActiveX w celu sprawdzenia, czy można bezpiecznie ładować je na stronach. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer nie będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Jeśli to ustawienie zasad zostanie wyłączone, program Internet Explorer zawsze będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Jeśli to ustawienie zasad nie zostanie skonfigurowane, program Internet Explorer nie będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Użytkownicy mogą włączać i wyłączać to zachowanie przy użyciu ustawień zabezpieczeń programu Internet Explorer.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067152)

  **Domyślne**: wyłączone

- **Dostęp strefy internetowej w programie Internet Explorer do źródeł danych**  
  To ustawienie zasad umożliwia zarządzanie tym, czy program Internet Explorer może uzyskiwać dostęp do danych z innej strefy zabezpieczeń przy użyciu programu Microsoft XML Parser (MSXML) lub ActiveX Data Objects (ADO). Jeśli to ustawienie zasad zostanie włączone, użytkownicy będą mogli załadować stronę w strefie używającej programu MSXML lub ADO w celu uzyskania dostępu do danych z innej witryny w strefie. Jeśli w polu listy rozwijanej zostanie wybrana pozycja Monituj, użytkownicy będą proszeni o wybranie, czy zezwolić na załadowanie strony w strefie używającej programu MSXML lub ADO w celu uzyskania dostępu do danych z innej witryny w strefie. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli załadować strony w strefie używającej programu MSXML lub ADO w celu uzyskania dostępu do danych z innej witryny w strefie. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy nie będą mogli załadować strony w strefie używającej programu MSXML lub ADO w celu uzyskania dostępu do danych z innej witryny w strefie.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067078)  
  
  **Domyślne**: Wyłącz  
  
- **Przeciąganie zawartości z innych domen w systemie Windows w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia ustawianie opcji przeciągania zawartości z między domenami, gdy źródło i lokalizacja docelowa znajdują się w tym samym oknie. Jeśli to ustawienie zasad zostanie włączone i klikniesz pozycję Włącz, użytkownicy będą mogli przeciągać zawartość między domenami, gdy źródło i lokalizacja docelowa znajdują się w tym samym oknie. Użytkownicy nie mogą zmieniać tego ustawienia. Jeśli to ustawienie zasad zostanie włączone i klikniesz pozycję Wyłącz, użytkownicy nie będą mogli przeciągać zawartości między domenami, gdy źródło i lokalizacja docelowa znajdują się w tym samym oknie. Użytkownicy nie mogą zmieniać tego ustawienia w oknie dialogowym Opcje internetowe. W programie Internet Explorer 10, jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownicy nie będą mogli przeciągać zawartości między domenami, gdy źródło i lokalizacja docelowa znajdują się w tym samym oknie. Użytkownicy mogą zmieniać to ustawienie w oknie dialogowym Opcje internetowe. W programie Internet Explorer 9 lub starszym, jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownicy będą mogli przeciągać zawartość między domenami, gdy źródło i lokalizacja docelowa znajdują się w tym samym oknie. Użytkownicy nie mogą zmieniać tego ustawienia w oknie dialogowym Opcje internetowe.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067079)  
  
  **Domyślne**: wyłączone
  
- **Ostrzeżenie o niezgodności adresu certyfikatu programu Internet Explorer**  
  To ustawienie zasad umożliwia włączenie ostrzeżenia o zabezpieczeniach dotyczącego niezgodności adresu certyfikatu. Gdy to ustawienie zasad zostanie włączone, użytkownik otrzyma ostrzeżenie podczas odwiedzania witryn bezpiecznego protokołu HTTP (HTTPS), które przedstawiają certyfikaty wystawione dla adresu innej witryny. To ostrzeżenie pomaga zapobiegać atakom metodą fałszowania. Jeśli to ustawienie zasad zostanie włączone, ostrzeżenie o niezgodności adresu certyfikatu będzie zawsze wyświetlane. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownik będzie mógł wybrać, czy ostrzeżenie o niezgodności adresu certyfikatu ma być wyświetlane (na stronie Zaawansowane w internetowym panelu sterowania).  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067153)  
  
  **Domyślne**: włączone 
  
- **Mniej uprzywilejowane witryny w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad pozwala określić, czy witryny internetowe z mniej uprzywilejowanych stref, takie jak witryny internetowe, mogą prowadzić do tej strefy. Jeśli to ustawienie zasad zostanie włączone, witryny z mniej uprzywilejowanych stref będą mogły otwierać nowe okna w tej strefie. Strefa zabezpieczeń będzie działać bez dodatkowej warstwy zabezpieczeń, które są udostępniane przez funkcję zabezpieczeń do ochrony z poziomu podniesienia uprawnień strefy. Jeśli w polu listy rozwijanej wybierzesz wartość Monituj, użytkownik otrzyma ostrzeżenie o potencjalnie ryzykownej nawigacji. Jeśli to ustawienie zasad zostanie wyłączone, potencjalnie szkodliwa nawigacja będzie blokowana. Funkcja zabezpieczeń programu Internet Explorer jest włączona w tej strefie zgodnie z ustawieniem kontroli funkcji ochrony z poziomu podniesienia uprawnień strefy. Jeśli to ustawienie zasad nie zostanie skonfigurowane, potencjalnie szkodliwe nawigacje będą blokowane. Funkcja zabezpieczeń programu Internet Explorer jest włączona w tej strefie zgodnie z ustawieniem kontroli funkcji ochrony z poziomu podniesienia uprawnień strefy.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067148)  
  
  **Domyślne**: Wyłącz  
  
- **Automatyczny monit o pobieranie plików w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad określa, czy użytkownicy otrzymują monit o pobieranie plików niezainicjowane przez użytkownika. Niezależnie od tego ustawienia u użytkowników będą wyświetlane okna dialogowe pobierania plików w przypadku pobierania zainicjowanego przez użytkownika. Jeśli to ustawienie zostanie włączone, u użytkowników będzie wyświetlane okno dialogowe pobierania plików w przypadku prób automatycznego pobrania. Jeśli to ustawienie jest wyłączone lub nieskonfigurowane, próby pobrania plików, które nie są inicjowane przez użytkownika, są blokowane, a użytkownicy widzą pasek powiadomień zamiast okna dialogowego pobierania plików. Użytkownicy będą mogli kliknąć pasek powiadomień, aby zezwolić na pobranie plików.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067150)  
  
  **Domyślne**: wyłączone
  
- **Składniki uzależnione od platformy .NET Framework w strefie internetowej w programie Internet Explorer**  
  To ustawienie zasad umożliwia określenie, czy składniki .NET Framework niepodpisane przy użyciu technologii Authenticode mogą być wykonywane w programie Internet Explorer. Do tych składników należą zarządzane kontrolki przywoływane z tagu obiektu oraz zarządzane pliki wykonywalne przywoływane z linku. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer będzie wykonywał niepodpisane składniki zarządzane. Jeśli w polu listy rozwijanej wybierzesz wartość Monituj, program Internet Explorer będzie prosił użytkownika o określenie, czy może wykonywać niepodpisane składniki zarządzane. Jeśli to ustawienie zasad zostanie wyłączone, program Internet Explorer nie będzie wykonywał niepodpisanych składników zarządzanych. Jeśli to ustawienie zasad nie zostanie skonfigurowane, program Internet Explorer będzie wykonywał niepodpisane składniki zarządzane.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067073)  
  
  **Domyślne**: Wyłącz 
  
- **Strefa internetowa w programie Internet Explorer zezwala na używanie kontrolek ActiveX TDC tylko przez zatwierdzone domeny**  
  To ustawienie zasad określa, czy użytkownik może uruchamiać kontrolkę ActiveX TDC w witrynach internetowych. Jeśli to ustawienie zasad zostanie włączone, kontrolka ActiveX TDC nie będzie uruchamiana z witryn internetowych w tej strefie. Jeśli to ustawienie zasad zostanie wyłączone, kontrolka ActiveX TDC będzie uruchamiana ze wszystkich witryn w tej strefie.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067151)
  
  **Domyślne**: włączone 
  
- **Okna inicjowane przez skrypty w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie ograniczeniami dotyczącymi okien podręcznych oraz okien zawierających paski tytułu i stanu inicjowanych przez skrypty. Jeśli to ustawienie zasad zostanie włączone, zabezpieczenia Ograniczenia systemu Windows nie będą stosowane w tej strefie. Strefa zabezpieczeń będzie działać bez dodatkowej warstwy zabezpieczeń udostępnianej przez tę funkcję. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie możliwe uruchamianie potencjalnie szkodliwych akcji zawartych w oknach podręcznych oraz oknach zawierających paski tytułu i stanu inicjowanych przez skrypty. Ta funkcja zabezpieczeń programu Internet Explorer jest włączona w tej strefie zgodnie z ustawieniem sterowania funkcją Ograniczenia zabezpieczeń okien inicjowanych przez skrypty dla procesu. Jeśli to ustawienie zasad nie zostanie skonfigurowane, nie będzie możliwe uruchamianie potencjalnie szkodliwych akcji zawartych w oknach podręcznych oraz oknach zawierających paski tytułu i stanu inicjowanych przez skrypty. Ta funkcja zabezpieczeń programu Internet Explorer jest włączona w tej strefie zgodnie z ustawieniem sterowania funkcją Ograniczenia zabezpieczeń okien inicjowanych przez skrypty dla procesu.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067075)  
  
  **Domyślne**: wyłączone 
  
- **Strefa internetowa w programie Internet Explorer obejmuje ścieżkę lokalną podczas przekazywania plików do serwera**  
  To ustawienie zasad określa, czy informacje o ścieżce lokalnej zostaną wysłane, gdy użytkownik będzie przekazywał plik za pomocą formularza HTML. Jeśli informacje o ścieżce lokalnej będą wysyłane, niektóre informacje mogą zostać przypadkowo ujawnione serwerowi. Na przykład pliki wysłane z komputera użytkownika mogą zawierać nazwę użytkownika jako część ścieżki. Jeśli to ustawienie zasad zostanie włączone, informacje o ścieżce będą wysyłane, gdy użytkownik będzie przekazywał plik za pomocą formularza HTML. Jeśli to ustawienie zasad zostanie wyłączone, informacje o ścieżce będą usuwane, gdy użytkownik będzie przekazywał plik za pomocą formularza HTML. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł wybrać, czy informacje o ścieżce będą wysyłane podczas przekazywania pliku za pomocą formularza HTML. Domyślnie informacje o ścieżce są wysyłane.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067072)  
  
  **Domyślne**: wyłączone 
  
- **Wyłączanie procesów w rozszerzonym trybie chronionym programu Internet Explorer**  
  To ustawienie zasad określa, czy program Internet Explorer 11 korzysta z procesów 64-bitowych (większe bezpieczeństwo) czy procesów 32-bitowych (większa zgodność) w rozszerzonym trybie chronionym w 64-bitowych wersjach systemu Windows. Ważne: niektóre kontrolki ActiveX i paski narzędzi mogą być niedostępne, gdy są używane procesy 64-bitowe. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer 11 będzie używać 64-bitowych procesów kart w rozszerzonym trybie chronionym w 64-bitowych wersjach systemu Windows. Jeśli to ustawienie zasad zostanie wyłączone, program Internet Explorer 11 będzie używać 32-bitowych procesów kart w rozszerzonym trybie chronionym w 64-bitowych wersjach systemu Windows. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy będą mogli włączyć lub wyłączyć tę funkcję w ustawieniach programu Internet Explorer. Ta funkcja jest domyślnie wyłączona.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067149)  
  
  **Domyślne**: włączone 
  
- **Ignorowanie błędów certyfikatów programu Internet Explorer**  
  To ustawienie zasad uniemożliwia użytkownikowi ignorowanie błędów certyfikatu Secure Sockets Layer/Transport Layer Security (SSL/TLS), które przerywają przeglądanie (na przykład błędy z powodu wygaśnięcia, odwołania lub niezgodności nazwy) w programie Internet Explorer. Jeśli to ustawienie zasad zostanie włączone, użytkownik nie będzie mógł kontynuować przeglądania. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownik będzie mógł ignorować błędy certyfikatu i kontynuować przeglądanie.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067071)  
  
  **Domyślne**: wyłączone 
  
- **Ładowanie stref internetowych plików XAML w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie ładowaniem plików XAML (Extensible Application Markup Language). XAML to oparty na składni XML język znaczników deklaratywnych, który jest często służy do tworzenia zaawansowanych interfejsów użytkownika i grafik korzystających z programu Windows Presentation Foundation. Jeśli to ustawienie zasad zostanie włączone i w polu listy rozwijanej zostanie ustawiona wartość Włącz, pliki XAML będą automatycznie ładowane w programie Internet Explorer. Użytkownik nie może zmienić tego zachowania. Jeśli ustawisz w polu listy rozwijanej wartość Monituj, użytkownik będzie monitowany o załadowanie plików XAML. Jeśli to ustawienie zasad zostanie wyłączone, pliki XAML nie będą ładowane w programie Internet Explorer. Użytkownik nie może zmienić tego zachowania. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł wybrać, czy załadować pliki XAML w programie Internet Explorer.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067147)  
  
  **Domyślne**: Wyłącz 
  
- **Automatyczny monit o pobieranie plików w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad określa, czy użytkownicy otrzymują monit o pobieranie plików niezainicjowane przez użytkownika. Niezależnie od tego ustawienia u użytkowników będą wyświetlane okna dialogowe pobierania plików w przypadku pobierania zainicjowanego przez użytkownika. Jeśli to ustawienie zostanie włączone, u użytkowników będzie wyświetlane okno dialogowe pobierania plików w przypadku prób automatycznego pobrania. Jeśli to ustawienie jest wyłączone lub nieskonfigurowane, próby pobrania plików, które nie są inicjowane przez użytkownika, są blokowane, a użytkownicy widzą pasek powiadomień zamiast okna dialogowego pobierania plików. Użytkownicy będą mogli kliknąć pasek powiadomień, aby zezwolić na pobranie plików.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067117)  
  
  **Domyślne**: wyłączone  
  
- **Ostrzeżenie o zabezpieczeniach strefy z ograniczeniami dla potencjalnie niebezpiecznych plików w programie Internet Explorer**  
  To ustawienie zasad określa, czy komunikat „Otwieranie pliku — ostrzeżenie o zabezpieczeniach” pojawia się, gdy użytkownik próbuje otworzyć pliki wykonywalne lub inne potencjalnie niebezpieczne pliki (na przykład z udziału plików w intranecie za pomocą Eksploratora plików). Jeśli to ustawienie zasad zostanie włączone i w polu listy rozwijanej zostanie ustawiona wartość Włącz, te pliki będą otwierane bez ostrzeżenia o zabezpieczeniach. Jeśli w polu listy rozwijanej ustawisz wartość Monituj, przed otwarciem plików pojawi się ostrzeżenie o zabezpieczeniach. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można otworzyć tych plików. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł skonfigurować sposób obsługi tych plików przez komputer. Domyślnie te pliki są zablokowane w strefie z ograniczeniami, włączone w strefie intranetu i komputera lokalnego oraz mają ustawione monitowanie w strefie Internetu i zaufanej strefie.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2066797)  
  
  **Domyślne**: Wyłącz  
  
- **Filtrowanie skryptów między witrynami w strefie internetowej programu Internet Explorer**  
  Te zasady określają, czy filtr skryptów między witrynami (XSS) będzie wykrywał i blokował wprowadzanie skryptu między witrynami w witrynach internetowych w tej strefie. Jeśli to ustawienie zasad zostanie włączone, filtr XSS zostanie włączony dla witryn w tej strefie i filtr XSS będzie próbować zablokować wprowadzanie skryptów między witrynami. Jeśli to ustawienie zasad zostanie wyłączone, filtr XSS zostanie wyłączony dla witryn w tej strefie i program Internet Explorer będzie zezwalać na wprowadzanie skryptów między witrynami.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067053) 
  
  **Domyślne**: włączone 
  
- **Powrót do protokołu SSL3 w programie Internet Explorer**  
  To ustawienie zasad umożliwia zablokowanie niezabezpieczonego powrotu do protokołu SSL 3.0. Jeśli te zasady zostaną włączone, program Internet Explorer będzie podejmować próby połączenia z witrynami za pomocą protokołu SSL 3.0 lub starszego w przypadku niepowodzenia połączenia za pomocą protokołu TLS 1.0 lub nowszego. Zalecamy, aby nie zezwalać na niezabezpieczony powrót w celu zapobieżenia atakowi typu man-in-the-middle. Te zasady nie mają wpływu na to, które protokoły zabezpieczeń są włączone. Jeśli te zasady są wyłączone, są używane ustawienia domyślne systemu.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067118)  
  
  **Domyślne**: Żadne witryny  

- **Obsługa szyfrowania w programie Internet Explorer**  
  To ustawienie zasad umożliwia wyłączenie obsługi Transport Layer Security (TLS) 1,0, TLS 1,1, TLS 1,2, SSL (SSL) 2,0 lub SSL 3,0 w przeglądarce. Protokoły TLS i SSL są protokołami chroniącymi komunikację między przeglądarką a serwerem docelowym. Gdy przeglądarka próbuje skonfigurować chronioną komunikację z serwerem docelowym, przeglądarka i serwer negocjują protokół i wersję do użycia. Przeglądarka i serwer próbują dopasować listę obsługiwanych protokołów i wersji, a następnie wybrać najbardziej preferowane dopasowanie. Jeśli to ustawienie zasad zostanie włączone, przeglądarka negocjuje lub nie negocjuje tunelu szyfrowania przy użyciu metod szyfrowania wybranych z listy rozwijanej. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownik będzie mógł wybrać metodę szyfrowania obsługiwaną przez przeglądarkę.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067057)

  **Wartość domyślna**: 2 elementy: TLS v 1.1 i TLS v 1.2  
  *Wybierz strzałkę w dół, aby wyświetlić opcje, które można wybrać dla tego ustawienia.*
  
- **Blokada filtra SmartScreen w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad określa, czy filtr SmartScreen skanuje strony w tej strefie pod kątem złośliwej zawartości. Jeśli to ustawienie zasad zostanie włączone, filtr SmartScreen będzie skanować strony w tej strefie pod kątem złośliwej zawartości. Jeśli to ustawienie zasad zostanie wyłączone, filtr SmartScreen nie będzie skanować stron w tej strefie pod kątem złośliwej zawartości. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł wybrać, czy filtr SmartScreen ma skanować strony w tej strefie pod kątem złośliwej zawartości. Uwaga: w programie Internet Explorer 7 to ustawienie zasad określa, czy filtr wyłudzania informacji skanuje strony w tej strefie pod kątem złośliwej zawartości.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067059)  
  
  **Domyślne**: włączone 
  
- **Uruchamianie aplikacje i plików w elementach iFrame w strefie z ograniczeniami programu Internet Explorer**  
  To ustawienie zasad umożliwia określenie, czy można uruchamiać aplikacje i pobierać pliki z odwołania IFRAME w kodzie HTML stron w tej strefie. Jeśli to ustawienie zasad zostanie włączone, użytkownicy będą mogli uruchamiać aplikacje i pobierać pliki z elementów IFRAME na stronach w tej strefie bez interwencji użytkownika. Jeśli w polu listy rozwijanej ustawisz wartość Monituj, użytkownicy będą proszeni o wybranie, czy uruchamiać aplikacje i pobierać pliki z elementów IFRAME na stronach w tej strefie. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli uruchamiać aplikacji i pobierać plików z elementów IFRAME na stronach w tej strefie. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy nie będą mogli uruchamiać aplikacji i pobierać plików z elementów IFRAME na stronach w tej strefie.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067061)  
  
  **Domyślne**: Wyłącz 
  
- **Program Internet Explorer pomija ostrzeżenia filtra SmartScreen dotyczące nietypowych plików**  
  To ustawienie zasad określa, czy użytkownik może pomijać ostrzeżenia filtra SmartScreen. Filtr SmartScreen wysyła do użytkownika ostrzeżenia o plikach wykonywalnych, których użytkownicy programu Internet Explorer nie pobierają często z Internetu. Jeśli to ustawienie zasad zostanie włączone, ostrzeżenia filtra SmartScreen będą blokować użytkownika. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownik będzie mógł pomijać ostrzeżenia filtra SmartScreen.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067068)  
  
  **Domyślne**: wyłączone  
  
- **Blokowanie okien podręcznych w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad pozwala określić, czy mają być wyświetlane niechciane okna podręczne. Okna podręczne otwierane, gdy użytkownik końcowy kliknie link, nie są blokowane. Jeśli to ustawienie zasad zostanie włączone, większość niechcianych okien podręcznych nie będzie wyświetlana. Jeśli to ustawienie zasad zostanie wyłączone, wyświetlanie okien podręcznych nie będzie blokowane. Jeśli to ustawienie zasad nie zostanie skonfigurowane, większość niechcianych okien podręcznych nie będzie wyświetlana.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067069)  
  
  **Domyślne**: Włącz  
  
- **Spójna obsługa protokołu MIME przez procesy programu Internet Explorer**  
  Program Internet Explorer zawiera dynamiczne zachowania elementów binarnych: składniki, które hermetyzują określone funkcje dla elementów HTML, z którymi są połączone. To ustawienie zasad określa, czy ustawienie ograniczenia zabezpieczeń zachowania elementów binarnych jest zablokowane czy dozwolone. Jeśli to ustawienie zasad zostanie włączone, zachowania elementów binarnych będą zablokowane w procesach Eksploratora plików i programu Internet Explorer. Jeśli to ustawienie zasad zostanie wyłączone, zachowania elementów binarnych będą dozwolone w procesach Eksploratora plików i programu Internet Explorer. Jeśli to ustawienie zasad nie zostanie skonfigurowane, zachowania elementów binarnych będą zablokowane w procesach Eksploratora plików i programu Internet Explorer.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067144)  
  
  **Domyślne**: włączone  
  
- **Uprawnienia języka Java w strefie z ograniczeniami programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie uprawnieniami dotyczącymi apletów Java. Jeśli to ustawienie zasad zostanie włączone, będzie można wybierać opcje z listy rozwijanej. Ustawienie Niestandardowe umożliwia kontrolowanie ustawień uprawnień pojedynczo. Ustawienie Niski poziom zabezpieczeń umożliwia apletom wykonywanie wszystkich operacji. Ustawienie Średni poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy (obszarze pamięci, poza którym program nie może wykonywać wywołań) oraz udostępnia funkcje, takie jak obszar na pliki tymczasowe (bezpieczny obszar magazynu na komputerze klienckim) i kontrolowane przez użytkownika operacje we/wy na plikach. Ustawienie Wysoki poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy. Wyłącz język Java, aby uniemożliwić uruchamianie jakichkolwiek apletów. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można uruchamiać apletów Java. Jeśli to ustawienie zasad nie zostanie skonfigurowane, aplety Java będą wyłączone.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067132)  
  
  **Domyślne**: Wyłącz Java  
    
  
- **Kontrolki ActiveX programu Internet Explorer w trybie chronionym**  
  To ustawienie zasad uniemożliwia uruchamianie kontrolek ActiveX w trybie chronionym, gdy jest włączony rozszerzony tryb chroniony. Jeśli użytkownik ma zainstalowaną kontrolkę ActiveX, która nie jest zgodna z rozszerzonym trybem chronionym, a witryna internetowa próbuje ją załadować, program Internet Explorer powiadamia użytkownika i umożliwia uruchomienie witryny w standardowym trybie chronionym. To ustawienie zasad powoduje wyłączenie tego powiadomienia i wymuszenie działania wszystkich witryn w rozszerzonym trybie chronionym. Rozszerzony tryb chroniony zapewnia dodatkową ochronę przed złośliwymi witrynami internetowymi dzięki użyciu 64-bitowych procesów w 64-bitowych wersjach systemu Windows. Na komputerach z systemem w wersji co najmniej Windows 8 rozszerzony tryb chroniony ogranicza także lokalizacje, z których program Internet Explorer może czytać w rejestrze i w systemie plików. Gdy rozszerzony tryb chroniony jest włączony i użytkownik napotyka witrynę, która próbuje załadować kontrolkę ActiveX niezgodną z rozszerzonym trybem chronionym, program Internet Explorer powiadamia użytkownika i umożliwia wyłączenie rozszerzonego trybu chronionego dla tej witryny. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer nie umożliwi użytkownikowi wyłączenia rozszerzonego trybu chronionego. Wszystkie witryny trybu chronionego będą uruchamiane w rozszerzonym trybie chronionym. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, program Internet Explorer będzie powiadamiać użytkowników i umożliwi uruchamianie witryn z niezgodnymi kontrolkami ActiveX w standardowym trybie chronionym.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067145)  
  
  **Domyślne**: wyłączone  
  
- **Ładowanie stref z ograniczeniami plików XAML w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie ładowaniem plików XAML (Extensible Application Markup Language). XAML to oparty na składni XML język znaczników deklaratywnych, który jest często służy do tworzenia zaawansowanych interfejsów użytkownika i grafik korzystających z programu Windows Presentation Foundation. Jeśli to ustawienie zasad zostanie włączone i w polu listy rozwijanej zostanie ustawiona wartość Włącz, pliki XAML będą automatycznie ładowane w programie Internet Explorer. Użytkownik nie może zmienić tego zachowania. Jeśli ustawisz w polu listy rozwijanej wartość Monituj, użytkownik będzie monitowany o załadowanie plików XAML. Jeśli to ustawienie zasad zostanie wyłączone, pliki XAML nie będą ładowane w programie Internet Explorer. Użytkownik nie może zmienić tego zachowania. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł wybrać, czy załadować pliki XAML w programie Internet Explorer.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067070)  
  
  **Domyślne**: Wyłącz  
  
- **Ograniczenia zabezpieczeń okien ze skryptem w procesach programu Internet Explorer**  
  Program Internet Explorer umożliwia skryptom programowe otwieranie różnego rodzaju okien oraz zmienianie ich rozmiaru i położenia. Funkcja zabezpieczeń dotycząca ograniczeń okien ogranicza okna podręczne i uniemożliwia skryptom wyświetlanie okien, w których pasek tytułu i stanu nie są widoczne dla użytkownika lub zaciemniają paski tytułu i stanu innych okien. Jeśli to ustawienie zasad zostanie włączone, okna inicjowane przez skrypty będą ograniczone dla wszystkich procesów. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, okna inicjowane przez skrypty nie będą ograniczone.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067146)  
  
  **Domyślne**: włączone   
  
- **Uruchamianie wtyczek i kontrolek ActiveX w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad pozwala określić, czy wtyczki i kontrolki ActiveX mogą być uruchamiane na stronach z określonej strefy. Jeśli to ustawienie zasad zostanie włączone, kontrolki i wtyczki będą uruchamiane bez interwencji użytkownika. Jeśli w polu listy rozwijanej wybierzesz wartość Monituj, użytkownicy będą proszeni o wybranie, czy zezwalać na uruchamianie kontrolek i wtyczek. Jeśli to ustawienie zasad zostanie wyłączone, kontrolki i wtyczki nie będą uruchamiane. Jeśli to ustawienie zasad nie zostanie skonfigurowane, kontrolki i wtyczki nie będą uruchamiane.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067114) 
  
  **Domyślne**: Wyłącz  
  
- **Używanie w skryptach kontrolek ActiveX oznaczonych jako bezpieczne dla skryptów w strefie z ograniczeniami programu Internet Explorer**  
  To ustawienie zasad pozwala określić, czy kontrolka ActiveX oznaczona jako bezpieczna dla skryptów może wchodzić w interakcję ze skryptem. Jeśli to ustawienie zasad zostanie włączone, interakcja ze skryptem może występować automatycznie bez interwencji użytkownika. Jeśli w polu listy rozwijanej wybierzesz wartość Monituj, użytkownicy będą proszeni o wybranie, czy zezwalać na interakcję ze skryptem. Jeśli to ustawienie zasad zostanie wyłączone, interakcja ze skryptem nie będzie możliwa. Jeśli to ustawienie zasad nie zostanie skonfigurowane, interakcja ze skryptem nie będzie możliwa.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067062)  
  
  **Domyślne**: Wyłącz  
  
- **Opcje logowania w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie ustawieniami opcji logowania. Jeśli to ustawienie zasad zostanie włączone, będzie można wybierać poniższe opcje logowania. 
  - *Anonimowe* — użyj logowania anonimowego, aby wyłączyć uwierzytelnianie HTTP i używać konta gościa tylko dla protokołu CIFS (Common Internet File System). 
  - *Monituj* — użyj monitowania o podanie nazwy użytkownika i hasła, aby wysyłać zapytania do użytkowników dotyczące identyfikatorów użytkowników i haseł. Po wysłaniu zapytania do użytkownika można używać tych wartości dyskretnie w pozostałej części sesji. 
  - *Zaloguj automatycznie tylko w strefie intranetu* — użyj tej opcji, aby wysyłać do użytkowników zapytania dotyczące identyfikatorów użytkowników i haseł w innych strefach. Po wysłaniu zapytania do użytkownika można używać tych wartości dyskretnie w pozostałej części sesji. 
  - *Zaloguj automatycznie przy użyciu bieżącej nazwy użytkownika i hasła* —użyj tej opcji, aby spróbować zalogować się przy użyciu odpowiedzi na żądanie systemu Windows NT (opcja znana również jako uwierzytelnianie NTLM). Jeśli serwer obsługuje odpowiedź na żądanie systemu Windows NT, podczas logowania są używane nazwa użytkownika i hasło sieci użytkownika. Jeśli odpowiedź na żądanie systemu Windows NT nie jest obsługiwana przez serwer, użytkownik zostanie poproszony o podanie nazwy użytkownika i hasła. 

  Jeśli to ustawienie zasad zostanie wyłączone, zostanie ustawione *automatyczne logowanie tylko w strefie intranetu*. Jeśli to ustawienie zasad nie zostanie skonfigurowane, zostanie ustawione *monitowanie* o podanie nazwy użytkownika i hasła.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067110)  
  
  **Domyślne**: Anonimowe  
  
- **Zaufana strefa w programie Internet Explorer inicjuje i umieszcza w skryptach kontrolki ActiveX, które nie są oznaczone jako bezpieczne**  
  To ustawienie zasad umożliwia zarządzanie kontrolkami ActiveX, które nie są oznaczone jako bezpieczne. Jeśli to ustawienie zasad zostanie włączone, kontrolki ActiveX będą uruchamiane i ładowane z parametrami oraz będą wykonywane ich skrypty bez konieczności ustawiania poziomu bezpieczeństwa obiektów dla niezaufanych danych lub skryptów. To ustawienie nie jest zalecane poza strefami bezpiecznymi i administrowanymi. To ustawienie umożliwia inicjowanie i wykonywanie skryptów zarówno bezpiecznych, jak i niebezpiecznych kontrolek, z jednoczesnym ignorowaniem opcji Wykonaj skrypty kontrolek ActiveX zaznaczone jako bezpieczne. Jeśli to ustawienie zasad zostanie włączone i w polu listy rozwijanej zostanie wybrana pozycja Monituj, użytkownicy będą pytani, czy zezwolić na ładowanie kontrolek z parametrami lub inicjowanych przez skrypty. Jeśli to ustawienie zasad zostanie wyłączone, kontrolki ActiveX, które nie mogą stać się bezpieczne, nie będą ładowane z parametrami ani nie będą wykonywane ich skrypty. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy będą pytani, czy zezwolić na ładowanie kontrolek z parametrami lub inicjowanych przez skrypty.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067137)  
  
  **Domyślne**: Wyłącz  
  
- **Sprawdzanie odwołania certyfikatów serwera w programie Internet Explorer**  
  To ustawienie zasad pozwala określić, czy program Internet Explorer będzie sprawdzać stan odwołania certyfikatów serwerów. Certyfikaty są odwoływane w przypadku naruszenia zabezpieczeń lub gdy nie są już prawidłowe. To ustawienie chroni użytkowników przed przesłaniem danych poufnych do fałszywej lub niezabezpieczonej witryny. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer będzie sprawdzać, czy certyfikaty serwerów zostały odwołane. Jeśli to ustawienie zasad zostanie wyłączone, program Internet Explorer nie będzie sprawdzać, czy certyfikaty serwerów zostały odwołane. Jeśli to ustawienie zasad nie zostanie skonfigurowane, program Internet Explorer nie będzie sprawdzać, czy certyfikaty serwerów zostały odwołane.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067046)  
  
  **Domyślne**: włączone 
  
- **Mniej uprzywilejowane witryny w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad pozwala określić, czy witryny internetowe z mniej uprzywilejowanych stref, takie jak witryny z ograniczeniami, mogą prowadzić do tej strefy. Jeśli to ustawienie zasad zostanie włączone, witryny z mniej uprzywilejowanych stref będą mogły otwierać nowe okna w tej strefie. Strefa zabezpieczeń będzie działać bez dodatkowej warstwy zabezpieczeń, które są udostępniane przez funkcję zabezpieczeń do ochrony z poziomu podniesienia uprawnień strefy. Jeśli w polu listy rozwijanej wybierzesz wartość Monituj, użytkownik otrzyma ostrzeżenie o potencjalnie ryzykownej nawigacji. Jeśli to ustawienie zasad zostanie wyłączone, potencjalnie szkodliwe nawigacje będą blokowane. Funkcja zabezpieczeń programu Internet Explorer jest włączona w tej strefie zgodnie z ustawieniem kontroli funkcji ochrony z poziomu podniesienia uprawnień strefy. Jeśli to ustawienie zasad nie zostanie skonfigurowane, witryny z mniej uprzywilejowanych stref będą mogły otwierać nowe okna w tej strefie.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067109)  
  
  **Domyślne**: Wyłącz  
  
- **Pobieranie plików w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad pozwala określić, czy pobieranie plików ze strefy jest dozwolone. Ta opcja jest określana przez strefę strony z linkiem pobierania, a nie przez strefę, z której plik jest dostarczany. Jeśli to ustawienie zasad zostanie włączone, będzie można pobierać pliki ze strefy. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można pobierać plików ze strefy. Jeśli to ustawienie zasad nie zostanie skonfigurowane, nie będzie można pobierać plików ze strefy.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067038)  
  
  **Domyślne**: Wyłącz  
  
- **Strefa internetowa w programie Internet Explorer uruchamia składniki uzależnione od platformy .NET Framework podpisane przy użyciu technologii Authenticode**  
  To ustawienie zasad umożliwia zarządzanie tym, czy składniki .NET Framework podpisane przy użyciu technologii Authenticode mogą być wykonywane w programie Internet Explorer. Do tych składników należą zarządzane kontrolki przywoływane z tagu obiektu oraz zarządzane pliki wykonywalne przywoływane z linku. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer będzie wykonywał podpisane składniki zarządzane. Jeśli w polu listy rozwijanej wybierzesz wartość Monituj, program Internet Explorer będzie prosił użytkownika o określenie, czy może wykonywać podpisane składniki zarządzane. Jeśli to ustawienie zasad zostanie wyłączone, program Internet Explorer nie będzie wykonywał podpisanych składników zarządzanych. Jeśli to ustawienie zasad nie zostanie skonfigurowane, program Internet Explorer nie będzie wykonywał podpisanych składników zarządzanych.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067033)  
  
  **Domyślne**: Wyłącz  
  
- **Program Internet Explorer uniemożliwia instalację kontrolek ActiveX przez poszczególnych użytkowników**  
  To ustawienie zasad umożliwia blokowanie instalacji kontrolek ActiveX przeprowadzanych przez poszczególnych użytkowników. Jeśli to ustawienie zasad zostanie włączone, poszczególni użytkownicy nie będą mogli instalować kontrolek ActiveX. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, poszczególni użytkownicy będą mogli instalować kontrolki ActiveX.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067058)  
  
  **Domyślne**: włączone  
  
- **Program Internet Explorer uniemożliwia zarządzanie filtrem SmartScreen**  
  To ustawienie zasad uniemożliwia użytkownikowi zarządzanie filtrem SmartScreen i powoduje wyświetlenie ostrzeżenia o tym, że odwiedzana witryna jest znana z fałszywych prób zebrania informacji osobistych metodą wyłudzania informacji lub z hostowania złośliwego oprogramowania. W przypadku włączenia tego ustawienia zasad użytkownik nie otrzyma monitu o włączenie filtru SmartScreen. Wszystkie adresy witryn, których nie ma na liście dozwolonych filtru, są automatycznie wysyłane do firmy Microsoft bez monitowania użytkownika. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownik otrzyma monit o to, czy włączyć filtr SmartScreen podczas pierwszego uruchomienia.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067135)  
  
  **Domyślne**: Włącz  
  
- **Funkcja zabezpieczeń wykrywania protokołu MIME w procesach programu Internet Explorer**  
  To ustawienie zasad określa, czy wykrywanie protokołu MIME programu Internet Explorer uniemożliwi podwyższenie poziomu pliku danego typu do bardziej niebezpiecznego typu pliku. Jeśli to ustawienie zasad zostanie włączone, wykrywanie protokołu MIME nigdy nie będzie podwyższać poziomu pliku danego typu do bardziej niebezpiecznego typu pliku. Jeśli to ustawienie zasad zostanie wyłączone, procesy programu Internet Explorer będą zezwalać na podwyższanie poziomu pliku danego typu do bardziej niebezpiecznego typu pliku w ramach wykrywania protokołu MIME. Jeśli to ustawienie zasad nie zostanie skonfigurowane, wykrywanie protokołu MIME nigdy nie będzie podwyższać poziomu pliku danego typu do bardziej niebezpiecznego typu pliku.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067124)  
  
  **Domyślne**: włączone  
  
- **Pobieranie podpisanych kontrolek ActiveX w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie tym, czy użytkownicy mogą pobierać podpisane kontrolki ActiveX ze strony w strefie. Jeśli te zasady zostaną włączone, użytkownicy będą mogli pobierać podpisane kontrolki bez interwencji użytkownika. Jeśli wybierzesz w polu listy rozwijanej wartość Monituj, użytkownicy będą proszeni o wybranie, czy pobierać kontrolki podpisane przez niezaufanych wydawców. Kod podpisany przez zaufanych wydawców jest dyskretnie pobierany. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można pobierać podpisanych kontrolek. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy będą proszeni o wybranie, czy pobierać kontrolki podpisane przez niezaufanych wydawców. Kod podpisany przez zaufanych wydawców jest dyskretnie pobierany.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067120) 
  
  **Domyślne**: Wyłącz  
  
- **Autouzupełnianie w programie Internet Explorer**  
  Ta funkcja autouzupełniania zapamiętuje i sugeruje nazwy użytkowników i hasła w formularzach. Jeśli to ustawienie zostanie włączone, użytkownik nie będzie mógł zmienić ustawienia „Nazwy użytkowników i hasła w formularzach” lub „Monituj o zapisywanie haseł”. Funkcja autouzupełniania dla nazw użytkownika i haseł w formularzach zostanie włączona. Musisz zdecydować, czy wybrać ustawienie „Monituj o zapisywanie haseł”. Jeśli to ustawienie zostanie wyłączone, użytkownik nie będzie mógł zmienić ustawienia „Nazwy użytkowników i hasła w formularzach” lub „Monituj o zapisywanie haseł”. Funkcja autouzupełniania dla nazw użytkownika i haseł w formularzach zostanie wyłączona. Użytkownik nie będzie mógł też włączyć monitowania o zapisywanie haseł. Jeśli to ustawienie nie zostanie skonfigurowane, użytkownik będzie mógł włączyć autouzupełnianie dla nazw użytkowników i haseł w formularzach oraz monitowanie o zapisywanie haseł. Aby wyświetlić tę opcję, użytkownicy muszą otworzyć okno dialogowe Opcje internetowe, kliknąć kartę Zawartość i kliknąć przycisk Ustawienia.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067122)  
  
  **Domyślne**: wyłączone  
  
- **Zezwalanie na uruchamianie skryptu VBscript w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad pozwala określić, czy można uruchamiać skrypt VBScript na stronach w określonych strefach programu Internet Explorer. Dostępne opcje: 
  - *Włącz* — skrypt VBScript jest uruchamiany na stronach w określonych strefach bez interakcji. 
  - *Monituj* — pracownicy są monitowani o to, czy zezwalać na uruchamianie skryptu VBScript w strefie. 
  - *Wyłącz* — nie można uruchamiać skryptu VBScript w strefie. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, skrypt VBScript będzie uruchamiany bez interakcji w określonej strefie.    

  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067119)  
  
  **Domyślne**: Wyłącz  
  
- **Strefa z ograniczeniami w programie Internet Explorer zezwala na używanie kontrolek ActiveX TDC tylko przez zatwierdzone domeny**  
  To ustawienie zasad określa, czy użytkownik może uruchamiać kontrolkę ActiveX TDC w witrynach internetowych. Jeśli to ustawienie zasad zostanie włączone, kontrolka ActiveX TDC nie będzie uruchamiana z witryn internetowych w tej strefie. Jeśli to ustawienie zasad zostanie wyłączone, kontrolka ActiveX TDC będzie uruchamiana ze wszystkich witryn w tej strefie.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067032)  
  
  **Domyślne**: włączone  
  
- **Zaufana strefa w programie Internet Explorer nie uruchamia oprogramowania chroniącego przed złośliwym oprogramowaniem względem kontrolek ActiveX**  
  To ustawienie zasad określa, czy program Internet Explorer uruchamia programy chroniące przed złośliwym oprogramowaniem względem kontrolek ActiveX w celu sprawdzenia, czy można bezpiecznie ładować je na stronach. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer nie będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Jeśli to ustawienie zasad zostanie wyłączone, program Internet Explorer zawsze będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Jeśli to ustawienie zasad nie zostanie skonfigurowane, program Internet Explorer zawsze będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Użytkownicy mogą włączać i wyłączać to zachowanie przy użyciu ustawień zabezpieczeń programu Internet Explorer.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067115)  
  
  **Domyślne**: wyłączone 
  
- **Uprawnienia języka Java w strefie komputera lokalnego programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie uprawnieniami dotyczącymi apletów Java. Jeśli to ustawienie zasad zostanie włączone, będzie można wybierać opcje z listy rozwijanej. Ustawienie Niestandardowe umożliwia kontrolowanie ustawień uprawnień pojedynczo. Ustawienie Niski poziom zabezpieczeń umożliwia apletom wykonywanie wszystkich operacji. Ustawienie Średni poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy (obszarze pamięci, poza którym program nie może wykonywać wywołań) oraz udostępnia funkcje, takie jak obszar na pliki tymczasowe (bezpieczny obszar magazynu na komputerze klienckim) i kontrolowane przez użytkownika operacje we/wy na plikach. Ustawienie Wysoki poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy. Wyłącz język Java, aby uniemożliwić uruchamianie jakichkolwiek apletów. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można uruchamiać apletów Java. Jeśli to ustawienie zasad nie zostanie skonfigurowane, uprawnienia zostaną ustawione na Średni poziom zabezpieczeń.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067113)  
  
  **Domyślne**: Wyłącz Java 
  
- **Strefa intranetowa w programie Internet Explorer nie uruchamia oprogramowania chroniącego przed złośliwym oprogramowaniem względem kontrolek ActiveX**  
  To ustawienie zasad określa, czy program Internet Explorer uruchamia programy chroniące przed złośliwym oprogramowaniem względem kontrolek ActiveX w celu sprawdzenia, czy można bezpiecznie ładować je na stronach. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer nie będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Jeśli to ustawienie zasad zostanie wyłączone, program Internet Explorer zawsze będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Jeśli to ustawienie zasad nie zostanie skonfigurowane, program Internet Explorer nie będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Użytkownicy mogą włączać i wyłączać to zachowanie przy użyciu ustawień zabezpieczeń programu Internet Explorer.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067138)  
  
  **Domyślne**: wyłączone  

- **Skryptlety w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad pozwala określić, czy użytkownik może uruchamiać skryptlety. Jeśli to ustawienie zasad zostanie włączone, użytkownik będzie mógł uruchamiać skryptlety. Jeśli to ustawienie zasad zostanie wyłączone, użytkownik nie będzie mógł uruchamiać skryptletów. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł włączać lub wyłączać skryptlety.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067112)  
  
  **Domyślne**: wyłączone  
  
- **Pasek powiadomień procesów programu Internet Explorer**  
  To ustawienie zasad pozwala określić, czy pasek powiadomień ma być wyświetlany dla procesów programu Internet Explorer, gdy instalacja pliku lub kodu jest ograniczona. Domyślnie pasek powiadomień jest wyświetlany dla procesów programu Internet Explorer. Jeśli to ustawienie zasad jest włączone, pasek powiadomień jest wyświetlany dla procesów programu Internet Explorer. Jeśli to ustawienie zasad zostanie wyłączone, pasek powiadomień nie będzie wyświetlany dla procesów programu Internet Explorer. Jeśli to ustawienie zasad nie jest skonfigurowane, pasek powiadomień nie jest wyświetlany dla procesów programu Internet Explorer.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067139)  
  
  **Domyślne**: włączone  
  
- **Pobieranie podpisanych kontrolek ActiveX w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie tym, czy użytkownicy mogą pobierać podpisane kontrolki ActiveX ze strony w strefie. Jeśli te zasady zostaną włączone, użytkownicy będą mogli pobierać podpisane kontrolki bez interwencji użytkownika. Jeśli wybierzesz w polu listy rozwijanej wartość Monituj, użytkownicy będą proszeni o wybranie, czy pobierać kontrolki podpisane przez niezaufanych wydawców. Kod podpisany przez zaufanych wydawców jest dyskretnie pobierany. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można pobierać podpisanych kontrolek. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy będą proszeni o wybranie, czy pobierać kontrolki podpisane przez niezaufanych wydawców. Kod podpisany przez zaufanych wydawców jest dyskretnie pobierany.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067064)  
  
  **Domyślne**: Wyłącz  
  
- **Filtr SmartScreen w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad określa, czy filtr SmartScreen skanuje strony w tej strefie pod kątem złośliwej zawartości. Jeśli to ustawienie zasad zostanie włączone, filtr SmartScreen będzie skanować strony w tej strefie pod kątem złośliwej zawartości. Jeśli to ustawienie zasad zostanie wyłączone, filtr SmartScreen nie będzie skanować stron w tej strefie pod kątem złośliwej zawartości. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł wybrać, czy filtr SmartScreen ma skanować strony w tej strefie pod kątem złośliwej zawartości. Uwaga: w programie Internet Explorer 7 to ustawienie zasad określa, czy filtr wyłudzania informacji skanuje strony w tej strefie pod kątem złośliwej zawartości.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067034)  
  
  **Domyślne**: włączone  
  
- **Usuwanie przycisku Uruchom teraz dla nieaktualnych kontrolek ActiveX w programie Internet Explorer**  
  To ustawienie zasad pozwala ukryć przed użytkownikami przycisk „Uruchom teraz” oraz uniemożliwia uruchamianie określonych nieaktualnych kontrolek ActiveX w programie Internet Explorer. Jeśli to ustawienie zasad zostanie włączone, użytkownicy nie będą widzieć przycisku „Uruchom teraz” w komunikacie ostrzegawczym, który jest wyświetlany, gdy program Internet Explorer blokuje nieaktualną kontrolkę ActiveX. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownicy będą widzieć przycisk „Uruchom teraz” w komunikacie ostrzegawczym, który jest wyświetlany, gdy program Internet Explorer blokuje nieaktualną kontrolkę ActiveX. Kliknięcie tego przycisku pozwala użytkownikowi uruchomić raz nieaktualną kontrolkę ActiveX. Więcej informacji można znaleźć na stronie „Nieaktualne kontrolki ActiveX” w bibliotece TechNet programu Internet Explorer.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067123)  
  
  **Domyślne**: włączone 
  
- **Uruchamianie aplikacji i plików w elementach iframe w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad umożliwia określenie, czy można uruchamiać aplikacje i pobierać pliki z odwołania IFRAME w kodzie HTML stron w tej strefie. Jeśli to ustawienie zasad zostanie włączone, użytkownicy będą mogli uruchamiać aplikacje i pobierać pliki z elementów IFRAME na stronach w tej strefie bez interwencji użytkownika. Jeśli w polu listy rozwijanej ustawisz wartość Monituj, użytkownicy będą proszeni o wybranie, czy uruchamiać aplikacje i pobierać pliki z elementów IFRAME na stronach w tej strefie. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli uruchamiać aplikacji i pobierać plików z elementów IFRAME na stronach w tej strefie. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy będą proszeni o wybranie, czy uruchamiać aplikacje i pobierać pliki z elementów IFRAME na stronach w tej strefie.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067020)  
  
  **Domyślne**: Wyłącz 
  
- **Nawigacja w oknach i ramkach różnych domen w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia ustawianie opcji przeciągania zawartości między domenami, gdy źródło i lokalizacja docelowa znajdują się w różnych oknach. Jeśli to ustawienie zasad zostanie włączone i klikniesz pozycję Włącz, użytkownicy będą mogli przeciągać zawartość między domenami, gdy źródło i lokalizacja docelowa znajdują się w różnych oknach. Użytkownicy nie mogą zmieniać tego ustawienia. Jeśli to ustawienie zasad zostanie włączone i klikniesz pozycję Wyłącz, użytkownicy nie będą mogli przeciągać zawartości z jednej domeny do innej, gdy zarówno miejsce źródłowe, jak i docelowe będą w różnych oknach. Użytkownicy nie mogą zmieniać tego ustawienia. W programie Internet Explorer 10, jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownicy nie będą mogli przeciągać zawartości z jednej domeny do innej, gdy miejsce źródłowe i docelowe będą w różnych oknach. Użytkownicy mogą zmieniać to ustawienie w oknie dialogowym Opcje internetowe. W programie Internet Explorer 9 lub jego starszych wersjach, jeśli te zasady zostaną wyłączone lub nie zostaną skonfigurowane, użytkownicy będą mogli przeciągać zawartość z jednej domeny do innej, gdy miejsce źródłowe i docelowe będą w różnych oknach. Użytkownicy nie mogą zmieniać tego ustawienia.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067050)  
  
  **Domyślne**: Wyłącz  
  
- **Filtr SmartScreen w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad określa, czy filtr SmartScreen skanuje strony w tej strefie pod kątem złośliwej zawartości. Jeśli to ustawienie zasad zostanie włączone, filtr SmartScreen będzie skanować strony w tej strefie pod kątem złośliwej zawartości. Jeśli to ustawienie zasad zostanie wyłączone, filtr SmartScreen nie będzie skanować stron w tej strefie pod kątem złośliwej zawartości. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł wybrać, czy filtr SmartScreen ma skanować strony w tej strefie pod kątem złośliwej zawartości. Uwaga: w programie Internet Explorer 7 to ustawienie zasad określa, czy filtr wyłudzania informacji skanuje strony w tej strefie pod kątem złośliwej zawartości.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067047)  
  
  **Domyślne**: włączone  
  
- **Zablokowane uprawnienia języka Java w zaufanej strefie programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie uprawnieniami dotyczącymi apletów Java. Jeśli to ustawienie zasad zostanie włączone, będzie można wybierać opcje z listy rozwijanej. Ustawienie Niestandardowe umożliwia kontrolowanie ustawień uprawnień pojedynczo. Ustawienie Niski poziom zabezpieczeń umożliwia apletom wykonywanie wszystkich operacji. Ustawienie Średni poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy (obszarze pamięci, poza którym program nie może wykonywać wywołań) oraz udostępnia funkcje, takie jak obszar na pliki tymczasowe (bezpieczny obszar magazynu na komputerze klienckim) i kontrolowane przez użytkownika operacje we/wy na plikach. Ustawienie Wysoki poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy. Wyłącz język Java, aby uniemożliwić uruchamianie jakichkolwiek apletów. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można uruchamiać apletów Java. Jeśli to ustawienie zasad nie zostanie skonfigurowane, aplety Java będą wyłączone.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067142)  
  
  
  **Domyślne**: Wyłącz Java 
  
- **Sprawdzanie podpisów pobranych programów w programie Internet Explorer**  
  To ustawienie zasad pozwala określić, czy program Internet Explorer ma sprawdzać podpisy cyfrowe (identyfikujące wydawcę podpisanego oprogramowania i sprawdzające, czy został on zmodyfikowany lub naruszony) w komputerach użytkowników przed pobraniem programów wykonywalnych. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer będzie sprawdzać podpisy cyfrowe programów wykonywalnych i wyświetlać ich tożsamości przed pobraniem do komputerów użytkowników. Jeśli to ustawienie zasad zostanie wyłączone, program Internet Explorer nie będzie sprawdzać podpisów cyfrowych programów wykonywalnych ani wyświetlać ich tożsamości przed pobraniem do komputerów użytkowników. Jeśli te zasady nie zostaną skonfigurowane, program Internet Explorer nie będzie sprawdzać podpisów cyfrowych programów wykonywalnych ani wyświetlać ich tożsamości przed pobraniem do komputerów użytkowników.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067051)  
  
  **Domyślne**: włączone  
  
- **Wykonywanie skryptów kontrolek przeglądarki internetowej w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad określa, czy strona może kontrolować osadzone kontrolki WebBrowser za pomocą skryptu. Jeśli to ustawienie zasad zostanie włączone, dostęp skryptów do kontrolki WebBrowser będzie dozwolony. Jeśli to ustawienie zasad zostanie wyłączone, dostęp skryptów do kontrolki WebBrowser nie będzie dozwolony. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł włączyć lub wyłączyć dostęp skryptów do kontrolki WebBrowser. Domyślnie dostęp skryptów do kontrolki WebBrowser jest dozwolony tylko w strefach Komputer lokalny i Intranet.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067098)  
  
  **Domyślne**: wyłączone  
  
- **Filtrowanie skryptów między witrynami w strefie z ograniczeniami w programie Internet Explorer**  
  Te zasady określają, czy filtr skryptów między witrynami (XSS) będzie wykrywał i blokował wprowadzanie skryptu między witrynami w witrynach internetowych w tej strefie. Jeśli to ustawienie zasad zostanie włączone, filtr XSS zostanie włączony dla witryn w tej strefie i filtr XSS będzie próbować zablokować wprowadzanie skryptów między witrynami. Jeśli to ustawienie zasad zostanie wyłączone, filtr XSS zostanie wyłączony dla witryn w tej strefie i program Internet Explorer będzie zezwalać na wprowadzanie skryptów między witrynami.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067178)  
  
  **Domyślne**: włączone  
  
- **Zachowanie danych binarnych i skryptów w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie dynamicznym zachowaniem danych binarnych i skryptów: składników, które hermetyzują określone funkcji dla elementów kodu HTML, do których zostały dołączone. Jeśli to ustawienie zasad zostanie włączone, zachowania danych binarnych i skryptów będą dostępne. Jeśli w polu listy rozwijanej wybierzesz pozycję Zatwierdzone przez administratora, dostępne będą tylko zachowania zatwierdzone przez administratora w ramach zasad ograniczenia zabezpieczeń zachowań danych binarnych. Jeśli to ustawienie zasad zostanie wyłączone, zachowania danych binarnych i skryptów nie będą dostępne, o ile aplikacje nie mają zaimplementowanego niestandardowego menedżera zabezpieczeń. Jeśli to ustawienie zasad nie zostanie skonfigurowane, zachowania danych binarnych i skryptów nie będą dostępne, o ile aplikacje nie mają zaimplementowanego niestandardowego menedżera zabezpieczeń.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067224)  
  
  **Domyślne**: Wyłącz  
  
- **Sprawdzanie ustawień zabezpieczeń programu Internet Explorer**  
  To ustawienie zasad powoduje wyłączenie funkcji sprawdzania ustawień zabezpieczeń, która sprawdza ustawienia zabezpieczeń programu Internet Explorer, aby określić, kiedy ustawienia stanowią zagrożenie dla programu Internet Explorer. Jeśli to ustawienie zasad zostanie włączone, funkcja zostanie wyłączona. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, funkcja zostanie włączona.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067182)  
  
  **Domyślne**: włączone  
  
- **Ostrzeżenie o zabezpieczeniach strefy internetowej dla potencjalnie niebezpiecznych plików w programie Internet Explorer**  
  To ustawienie zasad określa, czy komunikat „Otwieranie pliku — ostrzeżenie o zabezpieczeniach” pojawia się, gdy użytkownik próbuje otworzyć pliki wykonywalne lub inne potencjalnie niebezpieczne pliki (na przykład z udziału plików w intranecie za pomocą Eksploratora plików). Jeśli to ustawienie zasad zostanie włączone i w polu listy rozwijanej zostanie ustawiona wartość Włącz, te pliki będą otwierane bez ostrzeżenia o zabezpieczeniach. Jeśli w polu listy rozwijanej ustawisz wartość Monituj, przed otwarciem plików pojawi się ostrzeżenie o zabezpieczeniach. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można otworzyć tych plików. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł skonfigurować sposób obsługi tych plików przez komputer. Domyślnie te pliki są zablokowane w strefie z ograniczeniami, włączone w strefie intranetu i komputera lokalnego oraz mają ustawione monitowanie w strefie Internetu i zaufanej strefie.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067204)  
  
  **Domyślne**: Monituj  
  
- **Uprawnienia języka Java w strefie intranetowej programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie uprawnieniami dotyczącymi apletów Java. Jeśli to ustawienie zasad zostanie włączone, będzie można wybierać opcje z listy rozwijanej. Ustawienie Niestandardowe umożliwia kontrolowanie ustawień uprawnień pojedynczo. Ustawienie Niski poziom zabezpieczeń umożliwia apletom wykonywanie wszystkich operacji. Ustawienie Średni poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy (obszarze pamięci, poza którym program nie może wykonywać wywołań) oraz udostępnia funkcje, takie jak obszar na pliki tymczasowe (bezpieczny obszar magazynu na komputerze klienckim) i kontrolowane przez użytkownika operacje we/wy na plikach. Ustawienie Wysoki poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy. Wyłącz język Java, aby uniemożliwić uruchamianie jakichkolwiek apletów. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można uruchamiać apletów Java. Jeśli to ustawienie zasad nie zostanie skonfigurowane, uprawnienia zostaną ustawione na Średni poziom zabezpieczeń.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067206)  
  
  **Domyślne**: Wysoki poziom zabezpieczeń 
  
- **Blokowanie nieaktualnych kontrolek ActiveX w programie Internet Explorer**   
  To ustawienie zasad określa, czy program Internet Explorer ma blokować nieaktualne kontrolki ActiveX. Nieaktualne kontrolki ActiveX nigdy nie są blokowane w strefie intranetowej. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer przestanie blokować nieaktualne kontrolki ActiveX. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, program Internet Explorer będzie nadal blokować określone nieaktualne kontrolki ActiveX. Więcej informacji można znaleźć na stronie „Nieaktualne kontrolki ActiveX” w bibliotece TechNet programu Internet Explorer.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067203)  
  
  **Domyślne**: włączone  
  
- **Blokowanie okien podręcznych w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad pozwala określić, czy mają być wyświetlane niechciane okna podręczne. Okna podręczne otwierane, gdy użytkownik końcowy kliknie link, nie są blokowane. Jeśli to ustawienie zasad zostanie włączone, większość niechcianych okien podręcznych nie będzie wyświetlana. Jeśli to ustawienie zasad zostanie wyłączone, wyświetlanie okien podręcznych nie będzie blokowane. Jeśli to ustawienie zasad nie zostanie skonfigurowane, większość niechcianych okien podręcznych nie będzie wyświetlana.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067180)  
  
  **Domyślne**: Włącz  
  
- **Ograniczenia zabezpieczeń protokołu MK w procesach programu Internet Explorer**  
  Ustawienie zasad ograniczeń zabezpieczeń protokołu MK uniemożliwia korzystanie z protokołu MK, zmniejszając w ten sposób obszar powierzchni ataku. Korzystanie z zasobów obsługiwanych przez protokół MK nie będzie możliwe. Jeśli to ustawienie zasad zostanie włączone, protokół MK będzie zabroniony dla Eksploratora plików i przeglądarki Internet Explorer, a korzystanie z zasobów obsługiwanych przez protokół MK nie będzie możliwe. Jeśli to ustawienie zasad zostanie wyłączone, aplikacje będą mogły używać interfejsu API protokołu MK. Zasoby obsługiwane przez protokół MK będą działały w przypadku procesów Eksploratora plików i przeglądarki Internet Explorer. Jeśli to ustawienie zasad nie zostanie skonfigurowane, protokół MK będzie zabroniony dla Eksploratora plików i przeglądarki Internet Explorer, a korzystanie z zasobów obsługiwanych przez protokół MK nie będzie możliwe.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067179)  
  
  **Domyślne**: włączone  
  
- **Uprawnienia języka Java w strefie zaufanej programu Internet Explorer**   
  To ustawienie zasad umożliwia zarządzanie uprawnieniami dotyczącymi apletów Java. Jeśli to ustawienie zasad zostanie włączone, będzie można wybierać opcje z listy rozwijanej. Ustawienie Niestandardowe umożliwia kontrolowanie ustawień uprawnień pojedynczo. Ustawienie Niski poziom zabezpieczeń umożliwia apletom wykonywanie wszystkich operacji. Ustawienie Średni poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy (obszarze pamięci, poza którym program nie może wykonywać wywołań) oraz udostępnia funkcje, takie jak obszar na pliki tymczasowe (bezpieczny obszar magazynu na komputerze klienckim) i kontrolowane przez użytkownika operacje we/wy na plikach. Ustawienie Wysoki poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy. Wyłącz język Java, aby uniemożliwić uruchamianie jakichkolwiek apletów. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można uruchamiać apletów Java. Jeśli to ustawienie zasad nie zostanie skonfigurowane, zostaną ustawione uprawnienia Niski poziom zabezpieczeń.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067200)  
  
  **Domyślne**: Wysoki poziom zabezpieczeń  
  
- **Wykonywanie skryptów apletów Java w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie dostępnością apletów dla skryptów w strefie. Jeśli to ustawienie zasad zostanie włączone, skrypty będą mogły automatycznie uzyskiwać dostęp do apletów bez interwencji użytkownika. Jeśli w polu listy rozwijanej wybierzesz wartość Monit, użytkownicy będą proszeni o wybranie, czy zezwalać skryptom na dostęp do apletów. Jeśli to ustawienie zasad zostanie wyłączone, skrypty nie będą mogły uzyskiwać dostępu do apletów. Jeśli to ustawienie zasad nie zostanie skonfigurowane, skrypty nie będą mogły uzyskiwać dostępu do apletów.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067202)  
  
  **Domyślne**: Wyłącz  
  
- **Zablokowane uprawnienia języka Java w strefie z ograniczeniami w programie Internet Explorer**   
  To ustawienie zasad umożliwia zarządzanie uprawnieniami dotyczącymi apletów Java. Jeśli to ustawienie zasad zostanie włączone, będzie można wybierać opcje z listy rozwijanej. Ustawienie Niestandardowe umożliwia kontrolowanie ustawień uprawnień pojedynczo. Ustawienie Niski poziom zabezpieczeń umożliwia apletom wykonywanie wszystkich operacji. Ustawienie Średni poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy (obszarze pamięci, poza którym program nie może wykonywać wywołań) oraz udostępnia funkcje, takie jak obszar na pliki tymczasowe (bezpieczny obszar magazynu na komputerze klienckim) i kontrolowane przez użytkownika operacje we/wy na plikach. Ustawienie Wysoki poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy. Wyłącz język Java, aby uniemożliwić uruchamianie jakichkolwiek apletów. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można uruchamiać apletów Java. Jeśli to ustawienie zasad nie zostanie skonfigurowane, aplety Java będą wyłączone.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067181)  
  
  **Domyślne**: Wyłącz Java 
  
- **Strefa internetowa w programie Internet Explorer zezwala na używanie kontrolek ActiveX tylko przez zatwierdzone domeny**   
  To ustawienie zasad określa, czy użytkownik będzie proszony o wyrażenie zgody na uruchamianie kontrolek ActiveX w witrynach internetowych innych niż witryna internetowa, która zainstalowała kontrolkę ActiveX. Jeśli to ustawienie zasad zostanie włączone, użytkownik będzie proszony o wyrażenie zgody na uruchamianie kontrolek ActiveX z witryn internetowych w tej strefie. Użytkownik może zezwolić na uruchamianie kontrolki z bieżącej witryny lub ze wszystkich witryn. Jeśli to ustawienie zasad zostanie wyłączone, w poszczególnych witrynach nie będzie wyświetlany monit kontrolki ActiveX i będzie można uruchamiać kontrolki ActiveX ze wszystkich witryn w tej strefie.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067091)  
  
  **Domyślne**: włączone  
  
- **Program Internet Explorer zawiera wszystkie ścieżki sieciowe**  
  Program Internet Explorer zawiera wszystkie ścieżki sieciowe.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067090)  
  
  **Domyślne**: wyłączone 
  
- **Tryb chroniony w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad umożliwia włączenie trybu chronionego. Tryb chroniony ułatwia ochronę programu Internet Explorer przed wykorzystywaniem luk w zabezpieczeniach, zmniejszając liczbę lokalizacji, w których program Internet Explorer może zapisywać w rejestrze i w systemie plików. Jeśli to ustawienie zasad zostanie włączone, tryb chroniony będzie włączony. Użytkownik nie będzie mógł wyłączyć trybu chronionego. Jeśli to ustawienie zasad zostanie wyłączone, tryb chroniony będzie wyłączony. Użytkownik nie będzie mógł włączyć trybu chronionego. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł włączać i wyłączać tryb chroniony.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067171)  
  
  **Domyślne**: Włącz 
  
- **Strefa internetowa w programie Internet Explorer pozwala inicjować i wykonywać skrypty kontrolek ActiveX, które nie są oznaczone jako bezpieczne**  
  To ustawienie zasad umożliwia zarządzanie kontrolkami ActiveX, które nie są oznaczone jako bezpieczne. Jeśli to ustawienie zasad zostanie włączone, kontrolki ActiveX będą uruchamiane i ładowane z parametrami oraz będą wykonywane ich skrypty bez konieczności ustawiania poziomu bezpieczeństwa obiektów dla niezaufanych danych lub skryptów. To ustawienie nie jest zalecane poza strefami bezpiecznymi i administrowanymi. To ustawienie umożliwia inicjowanie i wykonywanie skryptów zarówno bezpiecznych, jak i niebezpiecznych kontrolek, z jednoczesnym ignorowaniem opcji Wykonaj skrypty kontrolek ActiveX zaznaczone jako bezpieczne. Jeśli to ustawienie zasad zostanie włączone i w polu listy rozwijanej zostanie wybrana pozycja Monituj, użytkownicy będą pytani, czy zezwolić na ładowanie kontrolek z parametrami lub inicjowanych przez skrypty. Jeśli to ustawienie zasad zostanie wyłączone, kontrolki ActiveX, które nie mogą stać się bezpieczne, nie będą ładowane z parametrami ani nie będą wykonywane ich skrypty. Jeśli to ustawienie zasad nie zostanie skonfigurowane, kontrolki ActiveX, które nie mogą stać się bezpieczne, nie będą ładowane z parametrami ani nie będą wykonywane ich skrypty.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067170)  
  
  **Domyślne**: Wyłącz 
  
- **Zablokowany filtr SmartScreen w strefie z ograniczeniami w programie Internet Explorer**   
  To ustawienie zasad określa, czy filtr SmartScreen skanuje strony w tej strefie pod kątem złośliwej zawartości. Jeśli to ustawienie zasad zostanie włączone, filtr SmartScreen będzie skanować strony w tej strefie pod kątem złośliwej zawartości. Jeśli to ustawienie zasad zostanie wyłączone, filtr SmartScreen nie będzie skanować stron w tej strefie pod kątem złośliwej zawartości. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł wybrać, czy filtr SmartScreen ma skanować strony w tej strefie pod kątem złośliwej zawartości. Uwaga: w programie Internet Explorer 7 to ustawienie zasad określa, czy filtr wyłudzania informacji skanuje strony w tej strefie pod kątem złośliwej zawartości.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067092)  
  
  **Domyślne**: włączone  
  
- **Wykrywanie awarii w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie funkcją wykrywania awarii Zarządzania dodatkami. Jeśli to ustawienie zasad zostanie włączone, awaria w programie Internet Explorer będzie powodowała zachowanie typowe dla systemu Windows XP Professional z dodatkiem Service Pack 1 lub starszego, to znaczy będzie wywoływać Raportowanie błędów systemu Windows. Wciąż będą obowiązywały wszystkie ustawienia zasad dla Raportowania błędów systemu Windows. Jeśli to ustawienie zasad jest wyłączone lub nieskonfigurowane, funkcja wykrywania awarii zarządzania dodatkami działa.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067094)  
  
  **Domyślne**: wyłączone  
  
- **Uprawnienia języka Java w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie uprawnieniami dotyczącymi apletów Java. Jeśli to ustawienie zasad zostanie włączone, będzie można wybierać opcje z listy rozwijanej. Ustawienie Niestandardowe umożliwia kontrolowanie ustawień uprawnień pojedynczo. Ustawienie Niski poziom zabezpieczeń umożliwia apletom wykonywanie wszystkich operacji. Ustawienie Średni poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy (obszarze pamięci, poza którym program nie może wykonywać wywołań) oraz udostępnia funkcje, takie jak obszar na pliki tymczasowe (bezpieczny obszar magazynu na komputerze klienckim) i kontrolowane przez użytkownika operacje we/wy na plikach. Ustawienie Wysoki poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy. Wyłącz język Java, aby uniemożliwić uruchamianie jakichkolwiek apletów. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można uruchamiać apletów Java. Jeśli to ustawienie zasad nie zostanie skonfigurowane, zostaną ustawione uprawnienia Wysoki poziom zabezpieczeń.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067174)  
  
  **Domyślne**: Wyłącz Java  
  
- **Aktywne wykonywanie skryptów w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie uruchamianiem kodu skryptu na stronach w strefie. Jeśli to ustawienie zasad zostanie włączone, będzie można uruchamiać kod skryptu na stronach w strefie. Jeśli w polu listy rozwijanej wybierzesz wartość Monit, użytkownicy będą proszeni o wybranie, czy zezwalać na uruchamianie kodu skryptu na stronach w strefie. Jeśli to ustawienie zasad zostanie wyłączone, uruchamianie kodu skryptu na stronach w strefie nie będzie możliwe. Jeśli to ustawienie zasad nie zostanie skonfigurowane, uruchamianie kodu skryptu na stronach w strefie nie będzie możliwe.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067172)  
  
  **Domyślne**: Wyłącz  
  
- **Opcje logowania w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie ustawieniami opcji logowania. Jeśli to ustawienie zasad zostanie włączone, będzie można wybierać poniższe opcje logowania. Użyj logowania anonimowego, aby wyłączyć uwierzytelnianie HTTP i używać konta gościa tylko dla protokołu CIFS (Common Internet File System). Monituj o podanie nazwy użytkownika i hasła, aby wysyłać zapytania do użytkowników dotyczące identyfikatorów użytkowników i haseł. Po wysłaniu zapytania do użytkownika można używać tych wartości dyskretnie w pozostałej części sesji. Zaloguj automatycznie tylko w strefie intranetu, aby wysyłać do użytkowników zapytania dotyczące identyfikatorów użytkowników i haseł w innych strefach. Po wysłaniu zapytania do użytkownika można używać tych wartości dyskretnie w pozostałej części sesji. Użyj automatycznego logowania przy użyciu bieżącej nazwy użytkownika i hasła, aby spróbować zalogować się przy użyciu odpowiedzi na żądanie systemu Windows NT (uwierzytelnianie NTLM). Jeśli serwer obsługuje odpowiedź na żądanie systemu Windows NT, podczas logowania są używane nazwa użytkownika i hasło sieci użytkownika. Jeśli odpowiedź na żądanie systemu Windows NT nie jest obsługiwana przez serwer, użytkownik zostanie poproszony o podanie nazwy użytkownika i hasła. Jeśli to ustawienie zasad zostanie wyłączone, zostanie ustawione automatyczne logowanie tylko w strefie intranetu. Jeśli to ustawienie zasad nie zostanie skonfigurowane, zostanie ustawione automatyczne logowanie tylko w strefie intranetu.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067194)  
  
  **Domyślne**: Monituj  
  
- **Zezwalanie na uruchamianie skryptu VBScript w strefie z ograniczeniami w programie Internet Explorer**   
  To ustawienie zasad pozwala określić, czy skrypt VBScript może być uruchamiany na stronach z określonej strefy w programie Internet Explorer. Jeśli w polu listy rozwijanej wybierzesz wartość Włącz, skrypt VBScript będzie można uruchamiać bez interwencji użytkownika. Jeśli w polu listy rozwijanej wybierzesz wartość Monit, użytkownicy będą proszeni o wybranie, czy zezwalać na uruchamianie skryptu VBScript. Jeśli w polu listy rozwijanej wybierzesz wartość Wyłącz, nie będzie można uruchamiać skryptu VBScript. Jeśli to ustawienie zasad nie zostanie skonfigurowane lub zostanie wyłączone, uruchamianie skryptu VBScript nie będzie możliwe.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067173)  
  
  **Domyślne**: Wyłącz  
  
- **Przeciąganie zawartości z innych domen między oknami w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad umożliwia ustawianie opcji przeciągania zawartości między domenami, gdy źródło i lokalizacja docelowa znajdują się w różnych oknach. Jeśli to ustawienie zasad zostanie włączone i klikniesz pozycję Włącz, użytkownicy będą mogli przeciągać zawartość między domenami, gdy źródło i lokalizacja docelowa znajdują się w różnych oknach. Użytkownicy nie mogą zmieniać tego ustawienia. Jeśli to ustawienie zasad zostanie włączone i klikniesz pozycję Wyłącz, użytkownicy nie będą mogli przeciągać zawartości z jednej domeny do innej, gdy zarówno miejsce źródłowe, jak i docelowe będą w różnych oknach. Użytkownicy nie mogą zmieniać tego ustawienia. W programie Internet Explorer 10, jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownicy nie będą mogli przeciągać zawartości z jednej domeny do innej, gdy miejsce źródłowe i docelowe będą w różnych oknach. Użytkownicy mogą zmieniać to ustawienie w oknie dialogowym Opcje internetowe. W programie Internet Explorer 9 lub jego starszych wersjach, jeśli te zasady zostaną wyłączone lub nie zostaną skonfigurowane, użytkownicy będą mogli przeciągać zawartość z jednej domeny do innej, gdy miejsce źródłowe i docelowe będą w różnych oknach. Użytkownicy nie mogą zmieniać tego ustawienia.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067093)  
  
  **Domyślne**: wyłączone 
  
- **Strefa intranetowa w programie Internet Explorer pozwala inicjować i wykonywać skrypty kontrolek ActiveX, które nie są oznaczone jako bezpieczne**  
  To ustawienie zasad umożliwia zarządzanie kontrolkami ActiveX, które nie są oznaczone jako bezpieczne. Jeśli to ustawienie zasad zostanie włączone, kontrolki ActiveX będą uruchamiane i ładowane z parametrami oraz będą wykonywane ich skrypty bez konieczności ustawiania poziomu bezpieczeństwa obiektów dla niezaufanych danych lub skryptów. To ustawienie nie jest zalecane poza strefami bezpiecznymi i administrowanymi. To ustawienie umożliwia inicjowanie i wykonywanie skryptów zarówno bezpiecznych, jak i niebezpiecznych kontrolek, z jednoczesnym ignorowaniem opcji Wykonaj skrypty kontrolek ActiveX zaznaczone jako bezpieczne. Jeśli to ustawienie zasad zostanie włączone i w polu listy rozwijanej zostanie wybrana pozycja Monituj, użytkownicy będą pytani, czy zezwolić na ładowanie kontrolek z parametrami lub inicjowanych przez skrypty. Jeśli to ustawienie zasad zostanie wyłączone, kontrolki ActiveX, które nie mogą stać się bezpieczne, nie będą ładowane z parametrami ani nie będą wykonywane ich skrypty. Jeśli to ustawienie zasad nie zostanie skonfigurowane, kontrolki ActiveX, które nie mogą stać się bezpieczne, nie będą ładowane z parametrami ani nie będą wykonywane ich skrypty.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067175)  
  
  **Domyślne**: Wyłącz 
  
- **Pobieranie załączników w programie Internet Explorer**  
  To ustawienie zasad uniemożliwia użytkownikowi pobieranie załączników (w postaci plików) ze źródła danych na komputer użytkownika. Jeśli to ustawienie zasad zostanie włączone, użytkownik nie będzie mógł ustawić pobierania załącznika przez aparat synchronizacji źródła danych za pośrednictwem strony właściwości źródła danych. Deweloper nie będzie mógł zmienić ustawienie pobierania za pośrednictwem interfejsów API źródła danych. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownik będzie mógł ustawić pobieranie załącznika przez aparat synchronizacji źródła danych za pośrednictwem strony właściwości źródła danych. Deweloper będzie mógł zmienić ustawienie pobierania za pośrednictwem interfejsów API źródła danych.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067245)  
  
  **Domyślne**: wyłączone  
  
- **Pobieranie niepodpisanych kontrolek ActiveX w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie tym, czy użytkownicy mogą pobierać niepodpisane kontrolki ActiveX ze strefy. Tego rodzaju kod jest potencjalnie szkodliwy, zwłaszcza gdy pochodzi z niezaufanej strefy. Jeśli to ustawienie zasad zostanie włączone, użytkownicy będą mogli uruchamiać niepodpisane kontrolki bez interwencji użytkownika. Jeśli w polu listy rozwijanej zostanie wybrana pozycja Monit, użytkownicy będą proszeni o wybranie, czy zezwalać na uruchamianie niepodpisanych kontrolek. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli uruchamiać niepodpisanych kontrolek. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy nie będą mogli uruchamiać niepodpisanych kontrolek.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067177)  
  
  **Domyślne**: Wyłącz  
  
- **Przeciąganie zawartości z innych domen w obrębie okien w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie tym, czy użytkownicy mogą pobierać niepodpisane kontrolki ActiveX ze strefy. Tego rodzaju kod jest potencjalnie szkodliwy, zwłaszcza gdy pochodzi z niezaufanej strefy. Jeśli to ustawienie zasad zostanie włączone, użytkownicy będą mogli uruchamiać niepodpisane kontrolki bez interwencji użytkownika. Jeśli w polu listy rozwijanej zostanie wybrana pozycja Monit, użytkownicy będą proszeni o wybranie, czy zezwalać na uruchamianie niepodpisanych kontrolek. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli uruchamiać niepodpisanych kontrolek. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy nie będą mogli uruchamiać niepodpisanych kontrolek.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067095)  
  
  **Domyślne**: wyłączone  
  
- **Procesy programu Internet Explorer ograniczają instalowanie kontrolek ActiveX**   
  To ustawienie zasad umożliwia aplikacjom hostującym kontrolkę przeglądarki internetowej blokowanie automatycznego monitowania o instalowanie kontrolek ActiveX. Jeśli to ustawienie zasad zostanie włączone, kontrolka przeglądarki internetowej będzie blokowała dla wszystkich procesów automatyczne monitowanie o instalowanie kontrolek ActiveX. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, kontrolka przeglądarki internetowej nie będzie blokowała dla wszystkich procesów automatycznego monitowania o instalowanie kontrolek ActiveX.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067250)  
  
  **Domyślne**: włączone  
  
- **Skryptlety strefy internetowej programu Internet Explorer**  
  To ustawienie zasad pozwala określić, czy użytkownik może uruchamiać skryptlety. Jeśli to ustawienie zasad zostanie włączone, użytkownik będzie mógł uruchamiać skryptlety. Jeśli to ustawienie zasad zostanie wyłączone, użytkownik nie będzie mógł uruchamiać skryptletów. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł włączać lub wyłączać skryptlety.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067176)  
  
  **Domyślne**: Wyłącz  
  
- **Przeciąganie i upuszczanie lub kopiowanie i wklejanie plików w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie tym, czy użytkownicy będą mogli przeciągać pliki lub kopiować i wklejać pliki ze źródła w strefie. Jeśli to ustawienie zasad zostanie włączone, użytkownicy będą mogli automatycznie przeciągać pliki lub kopiować i wklejać pliki z tej strefy. Jeśli w polu listy rozwijanej zostanie wybrana wartość Monit, użytkownicy będą proszeni o wybranie, czy przeciągać lub kopiować pliki z tej strefy. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli przeciągać plików ani kopiować i wklejać plików z tej strefy. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy będą proszeni o wybranie, czy przeciągać lub kopiować pliki z tej strefy.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067096)  
  
  **Domyślne**: Wyłącz  
  
- **Oprogramowanie przeglądarki Internet Explorer w przypadku nieprawidłowego podpisu**  
  To ustawienie zasad umożliwia zarządzanie tym, czy oprogramowanie, takie jak kontrolki ActiveX i funkcje pobierania plików, może być instalowane lub uruchamiane przez użytkownika, nawet jeśli podpis jest nieprawidłowy. Nieprawidłowy podpis może oznaczać, że ktoś naruszył plik. Jeśli to ustawienie zasad jest włączone, użytkownicy są monitowani o instalowanie lub uruchamianie plików z nieprawidłowym podpisem. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli uruchamiać ani instalować plików z nieprawidłowym podpisem. Jeśli te zasady nie zostaną skonfigurowane, użytkownicy będą mogli wybrać, czy pliki z nieprawidłowym podpisem mają być uruchamiane lub instalowane.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067201)
  
  **Domyślne**: wyłączone  
  
- **Kopiowanie i wklejanie za pomocą skryptu w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie tym, czy skrypty mogą wykonać operację schowka (na przykład wycięcie, skopiowanie i wklejenie) w określonym regionie. Jeśli to ustawienie zasad zostanie włączone, skrypt będzie mógł wykonać operację schowka. Jeśli w polu listy rozwijanej zostanie wybrana pozycja Monit, użytkownicy będą pytani, czy można wykonać operacje schowka. Jeśli to ustawienie zasad zostanie wyłączone, skrypt nie będzie mógł wykonać operacji schowka. Jeśli to ustawienie zasad nie zostanie skonfigurowane, skrypt nie będzie mógł wykonać operacji schowka.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067165)  
  
  **Domyślne**: Wyłącz  
  
- **Przeciąganie zawartości z innych domen między oknami w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia ustawianie opcji przeciągania zawartości między domenami, gdy źródło i lokalizacja docelowa znajdują się w różnych oknach. Jeśli to ustawienie zasad zostanie włączone i klikniesz pozycję Włącz, użytkownicy będą mogli przeciągać zawartość między domenami, gdy źródło i lokalizacja docelowa znajdują się w różnych oknach. Użytkownicy nie mogą zmieniać tego ustawienia. Jeśli to ustawienie zasad zostanie włączone i klikniesz pozycję Wyłącz, użytkownicy nie będą mogli przeciągać zawartości z jednej domeny do innej, gdy zarówno miejsce źródłowe, jak i docelowe będą w różnych oknach. Użytkownicy nie mogą zmieniać tego ustawienia. W programie Internet Explorer 10, jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownicy nie będą mogli przeciągać zawartości z jednej domeny do innej, gdy miejsce źródłowe i docelowe będą w różnych oknach. Użytkownicy mogą zmieniać to ustawienie w oknie dialogowym Opcje internetowe. W programie Internet Explorer 9 lub jego starszych wersjach, jeśli te zasady zostaną wyłączone lub nie zostaną skonfigurowane, użytkownicy będą mogli przeciągać zawartość z jednej domeny do innej, gdy miejsce źródłowe i docelowe będą w różnych oknach. Użytkownicy nie mogą zmieniać tego ustawienia.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067166)   

  **Domyślne**: wyłączone  
  
- **Użytkownicy programu Internet Explorer dodający witryny**  
  Uniemożliwia użytkownikom dodawanie i usuwanie witryn ze stref zabezpieczeń. Strefa zabezpieczeń to grupa witryn internetowych na tym samym poziomie zabezpieczeń. Włączenie tych zasad spowoduje wyłączenie ustawień zarządzania witrynami dla stref zabezpieczeń. (Aby zobaczyć ustawienia zarządzania witrynami dla stref zabezpieczeń, w oknie dialogowym Opcje internetowe kliknij kartę Zabezpieczenia, a następnie kliknij przycisk Witryny). Jeśli te zasady zostaną wyłączone lub nie zostaną skonfigurowane, użytkownicy będą mogli dodawać witryny internetowe do stref Zaufane witryny lub Witryny z ograniczeniami bądź je stamtąd usuwać, a także zmieniać ustawienia strefy Lokalny intranet. Te zasady uniemożliwiają użytkownikom zmianę ustawień zarządzania witrynami dla stref zabezpieczeń ustanowionych przez administratora. Uwaga: zasady „Wyłącz stronę Zabezpieczenia” (znajdujące się w katalogu \User Configuration\Administrative Templates\Windows Components\Internet Explorer\Internet Control Panel), które powodują usunięcie karty Zabezpieczenia z interfejsu, mają pierwszeństwo przed tymi zasadami. Jeśli zostaną włączone, omawiane tu zasady będą ignorowane. Zobacz też zasady „Strefy zabezpieczeń: używaj tylko ustawień komputera”.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067167)  
  
  **Domyślne**: wyłączone  
  
- **Okna inicjowane przez skrypty w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie ograniczeniami dotyczącymi okien podręcznych oraz okien zawierających paski tytułu i stanu inicjowanych przez skrypty. Jeśli to ustawienie zasad zostanie włączone, zabezpieczenia Ograniczenia systemu Windows nie będą stosowane w tej strefie. Strefa zabezpieczeń będzie działać bez dodatkowej warstwy zabezpieczeń udostępnianej przez tę funkcję. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie możliwe uruchamianie potencjalnie szkodliwych akcji zawartych w oknach podręcznych oraz oknach zawierających paski tytułu i stanu inicjowanych przez skrypty. Ta funkcja zabezpieczeń programu Internet Explorer jest włączona w tej strefie zgodnie z ustawieniem sterowania funkcją Ograniczenia zabezpieczeń okien inicjowanych przez skrypty dla procesu. Jeśli to ustawienie zasad nie zostanie skonfigurowane, nie będzie możliwe uruchamianie potencjalnie szkodliwych akcji zawartych w oknach podręcznych oraz oknach zawierających paski tytułu i stanu inicjowanych przez skrypty. Ta funkcja zabezpieczeń programu Internet Explorer jest włączona w tej strefie zgodnie z ustawieniem sterowania funkcją Ograniczenia zabezpieczeń okien inicjowanych przez skrypty dla procesu.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067088)  
  
  **Domyślne**: wyłączone  
  
- **Strefy zabezpieczeń programu Internet Explorer używają tylko ustawień komputera**  
  Stosuje informacje o strefie zabezpieczeń do wszystkich użytkowników tego samego komputera. Strefa zabezpieczeń to grupa witryn internetowych na tym samym poziomie zabezpieczeń. Jeśli te zasady zostaną włączone, zmiany wprowadzone przez użytkownika w strefie zabezpieczeń będą dotyczyły wszystkich użytkowników tego komputera. Jeśli te zasady zostaną wyłączone lub nie zostaną skonfigurowane, użytkownicy tego samego komputera będą mogli określać własne ustawienia stref zabezpieczeń. Te zasady mają zapewnić jednolite stosowanie ustawień stref zabezpieczeń na tym samym komputerze dla wszystkich użytkowników. Zobacz też zasady „Strefy zabezpieczeń: nie zezwalaj użytkownikom na zmianę zasad”.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067086)  
  
  **Domyślne**: włączone  
  
- **Zablokowane uprawnienia języka Java w strefie komputera lokalnego programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie uprawnieniami dotyczącymi apletów Java. Jeśli to ustawienie zasad zostanie włączone, będzie można wybierać opcje z listy rozwijanej. Ustawienie Niestandardowe umożliwia kontrolowanie ustawień uprawnień pojedynczo. Ustawienie Niski poziom zabezpieczeń umożliwia apletom wykonywanie wszystkich operacji. Ustawienie Średni poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy (obszarze pamięci, poza którym program nie może wykonywać wywołań) oraz udostępnia funkcje, takie jak obszar na pliki tymczasowe (bezpieczny obszar magazynu na komputerze klienckim) i kontrolowane przez użytkownika operacje we/wy na plikach. Ustawienie Wysoki poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy. Wyłącz język Java, aby uniemożliwić uruchamianie jakichkolwiek apletów. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można uruchamiać apletów Java. Jeśli to ustawienie zasad nie zostanie skonfigurowane, aplety Java będą wyłączone.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067253) 
  
  **Domyślne**: Wyłącz Java 
  
- **Strefa z ograniczeniami w programie Internet Explorer nie uruchamia oprogramowania chroniącego przed złośliwym oprogramowaniem względem kontrolek ActiveX**   
  To ustawienie zasad określa, czy program Internet Explorer uruchamia programy chroniące przed złośliwym oprogramowaniem względem kontrolek ActiveX w celu sprawdzenia, czy można bezpiecznie ładować je na stronach. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer nie będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Jeśli to ustawienie zasad zostanie wyłączone, program Internet Explorer zawsze będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Jeśli to ustawienie zasad nie zostanie skonfigurowane, program Internet Explorer zawsze będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Użytkownicy mogą włączać i wyłączać to zachowanie przy użyciu ustawień zabezpieczeń programu Internet Explorer.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067089)
  
  **Domyślne**: wyłączone  
  
- **Strefa z ograniczeniami w programie Internet Explorer uruchamia składniki uzależnione od platformy .NET Framework podpisane przy użyciu technologii Authenticode**  
  To ustawienie zasad umożliwia zarządzanie tym, czy składniki .NET Framework podpisane przy użyciu technologii Authenticode mogą być wykonywane w programie Internet Explorer. Do tych składników należą zarządzane kontrolki przywoływane z tagu obiektu oraz zarządzane pliki wykonywalne przywoływane z linku. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer będzie wykonywał podpisane składniki zarządzane. Jeśli w polu listy rozwijanej wybierzesz wartość Monituj, program Internet Explorer będzie prosił użytkownika o określenie, czy może wykonywać podpisane składniki zarządzane. Jeśli to ustawienie zasad zostanie wyłączone, program Internet Explorer nie będzie wykonywał podpisanych składników zarządzanych. Jeśli to ustawienie zasad nie zostanie skonfigurowane, program Internet Explorer nie będzie wykonywał podpisanych składników zarządzanych.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067169)  
  
  **Domyślne**: Wyłącz  
  
- **Dostęp strefy z ograniczeniami w programie Internet Explorer do źródeł danych**  
  To ustawienie zasad umożliwia zarządzanie tym, czy program Internet Explorer może uzyskiwać dostęp do danych z innej strefy zabezpieczeń przy użyciu programu Microsoft XML Parser (MSXML) lub ActiveX Data Objects (ADO). Jeśli to ustawienie zasad zostanie włączone, użytkownicy będą mogli załadować stronę w strefie używającej programu MSXML lub ADO w celu uzyskania dostępu do danych z innej witryny w strefie. Jeśli w polu listy rozwijanej zostanie wybrana pozycja Monituj, użytkownicy będą proszeni o wybranie, czy zezwolić na załadowanie strony w strefie używającej programu MSXML lub ADO w celu uzyskania dostępu do danych z innej witryny w strefie. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli załadować strony w strefie używającej programu MSXML lub ADO w celu uzyskania dostępu do danych z innej witryny w strefie. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy nie będą mogli załadować strony w strefie używającej programu MSXML lub ADO w celu uzyskania dostępu do danych z innej witryny w strefie.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067161)  
  
  **Domyślne**: Wyłącz 
  
- **Strefa internetowa w programie Internet Explorer nie uruchamia oprogramowania chroniącego przed złośliwym oprogramowaniem względem kontrolek ActiveX**  
  To ustawienie zasad określa, czy program Internet Explorer uruchamia programy chroniące przed złośliwym oprogramowaniem względem kontrolek ActiveX w celu sprawdzenia, czy można bezpiecznie ładować je na stronach. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer nie będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Jeśli to ustawienie zasad zostanie wyłączone, program Internet Explorer zawsze będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Jeśli to ustawienie zasad nie zostanie skonfigurowane, program Internet Explorer zawsze będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Użytkownicy mogą włączać i wyłączać to zachowanie przy użyciu ustawień zabezpieczeń programu Internet Explorer.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067162)  
  
  **Domyślne**: wyłączone  
  
- **Kopiowanie i wklejanie za pomocą skryptu w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie tym, czy skrypty mogą wykonać operację schowka (na przykład wycięcie, skopiowanie i wklejenie) w określonym regionie. Jeśli to ustawienie zasad zostanie włączone, skrypt będzie mógł wykonać operację schowka. Jeśli w polu listy rozwijanej zostanie wybrana pozycja Monit, użytkownicy będą pytani, czy można wykonać operacje schowka. Jeśli to ustawienie zasad zostanie wyłączone, skrypt nie będzie mógł wykonać operacji schowka. Jeśli to ustawienie zasad nie zostanie skonfigurowane, skrypt będzie mógł wykonać operację schowka.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067084)  
  
  **Domyślne**: Wyłącz  
  
- **Program Internet Explorer używa usługi instalatora ActiveX**  
  To ustawienie zasad pozwala określić sposób instalowania kontrolek ActiveX. Jeśli to ustawienie zasad zostanie włączone, kontrolki ActiveX będą instalowane tylko wtedy, gdy usługa instalatora kontrolek ActiveX jest obecna i została skonfigurowana tak, aby umożliwiać instalowanie kontrolek ActiveX. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, kontrolki ActiveX, w tym kontrolki użytkownika, będą instalowane za pośrednictwem standardowego procesu instalacji.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067163)
  
  **Domyślne**: włączone  
  
- **Ochrona procesów programu Internet Explorer przed podnoszeniem uprawnień strefy**  
  Program Internet Explorer stosuje ograniczenia na każdej otwieranej stronie internetowej. Ograniczenia są zależne od lokalizacji strony internetowej (Internet, intranet, strefa komputera lokalnego itd.). Na przykład strony internetowe na komputerze lokalnym mają najmniejsze ograniczenia zabezpieczeń i znajdują się w strefie Komputer lokalny, co sprawia, że strefa zabezpieczeń Komputer lokalny staje się głównym celem dla złośliwych użytkowników. Jeśli to ustawienie zasad zostanie włączone, dowolna strefa będzie mogła być chroniona przed podniesieniem uprawnień strefy dla wszystkich procesów. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, procesy inne niż związane z programem Internet Explorer lub wymienione na liście procesów nie otrzymają takiej ochrony.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067160)  
  
  **Domyślne**: włączone  
  
- **Pobieranie niepodpisanych kontrolek ActiveX w strefie internetowej programu Internet Explorer**   
  To ustawienie zasad umożliwia zarządzanie tym, czy użytkownicy mogą pobierać niepodpisane kontrolki ActiveX ze strefy. Tego rodzaju kod jest potencjalnie szkodliwy, zwłaszcza gdy pochodzi z niezaufanej strefy. Jeśli to ustawienie zasad zostanie włączone, użytkownicy będą mogli uruchamiać niepodpisane kontrolki bez interwencji użytkownika. Jeśli w polu listy rozwijanej zostanie wybrana pozycja Monit, użytkownicy będą proszeni o wybranie, czy zezwalać na uruchamianie niepodpisanych kontrolek. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli uruchamiać niepodpisanych kontrolek. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy nie będą mogli uruchamiać niepodpisanych kontrolek.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067325)
  
  **Domyślne**: Wyłącz  
  
- **Nawigacja w oknach i ramkach różnych domen w strefie internetowej programu Internet Explorer**   
  To ustawienie zasad umożliwia zarządzanie otwieraniem okien i ramek oraz uzyskiwaniem dostępu do aplikacji w różnych domenach. Jeśli to ustawienie zasad zostanie włączone, użytkownicy będą mogli otwierać okna i ramki z innych domen oraz uzyskiwać dostęp do aplikacji z innych domen. Jeśli w polu listy rozwijanej zostanie wybrana pozycja Monit, użytkownicy będą pytani, czy zezwolić oknom i ramkom na uzyskiwanie dostępu do aplikacji z innych domen. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli otwierać okien i ramek w celu uzyskania dostępu do aplikacji z różnych domen. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy będą mogli otwierać okna i ramki z innych domen oraz uzyskiwać dostęp do aplikacji z innych domen.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067083)  
  
  **Domyślne**: Wyłącz  
  
- **Aktualizacje paska stanu za pomocą skryptu w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad umożliwia określenie, czy skrypt może aktualizować pasek stanu w obrębie strefy. Jeśli to ustawienie zasad zostanie włączone, skrypty będą mogły aktualizować pasek stanu. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, skrypt nie będzie mógł aktualizować paska stanu.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067087)  
  
  **Domyślne**: wyłączone  
  
- **Strefa z ograniczeniami w programie Internet Explorer obejmuje ścieżkę lokalną podczas przekazywania plików do serwera**  
  To ustawienie zasad określa, czy informacje o ścieżce lokalnej będą wysyłane, gdy użytkownik będzie przekazywał plik za pomocą formularza HTML. Jeśli informacje o ścieżce lokalnej będą wysyłane, niektóre informacje mogą zostać przypadkowo ujawnione serwerowi. Na przykład pliki wysłane z komputera użytkownika mogą zawierać nazwę użytkownika jako część ścieżki. Jeśli to ustawienie zasad zostanie włączone, informacje o ścieżce będą wysyłane, gdy użytkownik będzie przekazywał plik za pomocą formularza HTML. Jeśli to ustawienie zasad zostanie wyłączone, informacje o ścieżce będą usuwane, gdy użytkownik będzie przekazywał plik za pomocą formularza HTML. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł wybrać, czy informacje o ścieżce będą wysyłane podczas przekazywania pliku za pomocą formularza HTML. Domyślnie informacje o ścieżce są wysyłane.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067085)  
  
  **Domyślne**: wyłączone  
  
- **Procesy programu Internet Explorer ograniczają pobieranie plików**   
  To ustawienie zasad umożliwia aplikacjom hostującym kontrolkę przeglądarki internetowej blokowanie automatycznego monitowania o pobieranie plików, które nie jest inicjowane przez użytkownika. Jeśli to ustawienie zasad zostanie włączone, kontrolka przeglądarki internetowej będzie blokowała dla wszystkich procesów automatyczne monitowanie o pobieranie plików, które nie jest inicjowane przez użytkownika. Jeśli to ustawienie zasad zostanie wyłączone, kontrolka przeglądarki internetowej nie będzie blokowała dla wszystkich procesów automatycznego monitowania o pobieranie plików, które nie jest inicjowane przez użytkownika.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067164)  
  
  **Domyślne**: włączone  
  
- **Strefa z ograniczeniami w programie Internet Explorer zezwala na używanie kontrolek ActiveX tylko przez zatwierdzone domeny**   
  To ustawienie zasad określa, czy użytkownik będzie proszony o wyrażenie zgody na uruchamianie kontrolek ActiveX w witrynach internetowych innych niż witryna internetowa, która zainstalowała kontrolkę ActiveX. Jeśli to ustawienie zasad zostanie włączone, użytkownik będzie proszony o wyrażenie zgody na uruchamianie kontrolek ActiveX z witryn internetowych w tej strefie. Użytkownik może zezwolić na uruchamianie kontrolki z bieżącej witryny lub ze wszystkich witryn. Jeśli to ustawienie zasad zostanie wyłączone, w poszczególnych witrynach nie będzie wyświetlany monit kontrolki ActiveX i będzie można uruchamiać kontrolki ActiveX ze wszystkich witryn w tej strefie.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067233)  
  
  **Domyślne**: włączone  
  
- **Strefa z ograniczeniami w programie Internet Explorer pozwala inicjować i wykonywać skrypty kontrolek ActiveX, które nie są oznaczone jako bezpieczne**  
  To ustawienie zasad umożliwia zarządzanie kontrolkami ActiveX, które nie są oznaczone jako bezpieczne. Jeśli to ustawienie zasad zostanie włączone, kontrolki ActiveX będą uruchamiane i ładowane z parametrami oraz będą wykonywane ich skrypty bez konieczności ustawiania poziomu bezpieczeństwa obiektów dla niezaufanych danych lub skryptów. To ustawienie nie jest zalecane poza strefami bezpiecznymi i administrowanymi. To ustawienie umożliwia inicjowanie i wykonywanie skryptów zarówno bezpiecznych, jak i niebezpiecznych kontrolek, z jednoczesnym ignorowaniem opcji Wykonaj skrypty kontrolek ActiveX zaznaczone jako bezpieczne. Jeśli to ustawienie zasad zostanie włączone i w polu listy rozwijanej zostanie wybrana pozycja Monituj, użytkownicy będą pytani, czy zezwolić na ładowanie kontrolek z parametrami lub inicjowanych przez skrypty. Jeśli to ustawienie zasad zostanie wyłączone, kontrolki ActiveX, które nie mogą stać się bezpieczne, nie będą ładowane z parametrami ani nie będą wykonywane ich skrypty. Jeśli to ustawienie zasad nie zostanie skonfigurowane, kontrolki ActiveX, które nie mogą stać się bezpieczne, nie będą ładowane z parametrami ani nie będą wykonywane ich skrypty.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067097)  
  
  **Domyślne**: Wyłącz  
  
- **Użytkownicy programu Internet Explorer zmieniający zasady**  
  Uniemożliwia użytkownikom zmianę ustawień strefy zabezpieczeń. Strefa zabezpieczeń to grupa witryn internetowych na tym samym poziomie zabezpieczeń. Jeśli te zasady zostaną włączone, przycisk Poziom niestandardowy i suwak poziomu zabezpieczeń na karcie Zabezpieczenia w oknie dialogowym Opcje internetowe będą wyłączone. Jeśli te zasady zostaną wyłączone lub nie zostaną skonfigurowane, użytkownicy będą mogli zmieniać ustawienia stref zabezpieczeń. Te zasady uniemożliwiają użytkownikom zmianę ustawień strefy zabezpieczeń ustanowionych przez administratora. Uwaga: zasady „Wyłącz stronę Zabezpieczenia” (znajdujące się w katalogu \User Configuration\Administrative Templates\Windows Components\Internet Explorer\Internet Control Panel), które powodują usunięcie karty Zabezpieczenia z programu Internet Explorer w Panelu sterowania, mają pierwszeństwo przed tymi zasadami. Jeśli zostaną włączone, omawiane tu zasady będą ignorowane. Zobacz też zasady „Strefy zabezpieczeń: używaj tylko ustawień komputera”.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067155)  
    
  **Domyślne**: wyłączone  
  
- **Tryb chroniony strefy z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia włączenie trybu chronionego. Tryb chroniony ułatwia ochronę programu Internet Explorer przed wykorzystywaniem luk w zabezpieczeniach, zmniejszając liczbę lokalizacji, w których program Internet Explorer może zapisywać w rejestrze i w systemie plików. Jeśli to ustawienie zasad zostanie włączone, tryb chroniony będzie włączony. Użytkownik nie będzie mógł wyłączyć trybu chronionego. Jeśli to ustawienie zasad zostanie wyłączone, tryb chroniony będzie wyłączony. Użytkownik nie będzie mógł włączyć trybu chronionego. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł włączać i wyłączać tryb chroniony.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067080)  
  
  **Domyślne**: Włącz  
  
- **Trwałość danych użytkownika w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie zachowywaniem informacji w historii przeglądarki, w ulubionych, w magazynie XML lub bezpośrednio na stronie internetowej zapisanej na dysku. Gdy użytkownik wróci na utrwaloną stronę, a ustawienie zasad zostało odpowiednio skonfigurowane, będzie można przywrócić stan strony. Jeśli to ustawienie zasad zostanie włączone, użytkownicy będą mogli zarządzać zachowywaniem informacji w historii przeglądarki, w ulubionych, w magazynie XML lub bezpośrednio na stronie internetowej zapisanej na dysku. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli zarządzać zachowywaniem informacji w historii przeglądarki, w ulubionych, w magazynie XML lub bezpośrednio na stronie internetowej zapisanej na dysku. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy będą mogli zarządzać zachowywaniem informacji w historii przeglądarki, w ulubionych, w magazynie XML lub bezpośrednio na stronie internetowej zapisanej na dysku.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067156)  
  
  **Domyślne**: wyłączone  
  
- **Wykonywanie skryptów kontrolek przeglądarki internetowej w strefie internetowej programu Internet Explorer**  
 
  To ustawienie zasad określa, czy strona może kontrolować osadzone kontrolki WebBrowser za pomocą skryptu. Jeśli to ustawienie zasad zostanie włączone, dostęp skryptów do kontrolki WebBrowser będzie dozwolony. Jeśli to ustawienie zasad zostanie wyłączone, dostęp skryptów do kontrolki WebBrowser nie będzie dozwolony. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł włączyć lub wyłączyć dostęp skryptów do kontrolki WebBrowser. Domyślnie dostęp skryptów do kontrolki WebBrowser jest dozwolony tylko w strefach Komputer lokalny i Intranet.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067157)  
  
  **Domyślne**: wyłączone  
  
- **Trwałość danych użytkownika w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie zachowywaniem informacji w historii przeglądarki, w ulubionych, w magazynie XML lub bezpośrednio na stronie internetowej zapisanej na dysku. Gdy użytkownik wróci na utrwaloną stronę, a ustawienie zasad zostało odpowiednio skonfigurowane, będzie można przywrócić stan strony. Jeśli to ustawienie zasad zostanie włączone, użytkownicy będą mogli zarządzać zachowywaniem informacji w historii przeglądarki, w ulubionych, w magazynie XML lub bezpośrednio na stronie internetowej zapisanej na dysku. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli zarządzać zachowywaniem informacji w historii przeglądarki, w ulubionych, w magazynie XML lub bezpośrednio na stronie internetowej zapisanej na dysku. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy nie będą mogli zarządzać zachowywaniem informacji w historii przeglądarki, w ulubionych, w magazynie XML lub bezpośrednio na stronie internetowej zapisanej na dysku.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067081)  
  
  **Domyślne**: wyłączone  
  
- **Zablokowane uprawnienia języka Java w strefie intranetowej programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie uprawnieniami dotyczącymi apletów Java. Jeśli to ustawienie zasad zostanie włączone, będzie można wybierać opcje z listy rozwijanej. Ustawienie Niestandardowe umożliwia kontrolowanie ustawień uprawnień pojedynczo. Ustawienie Niski poziom zabezpieczeń umożliwia apletom wykonywanie wszystkich operacji. Ustawienie Średni poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy (obszarze pamięci, poza którym program nie może wykonywać wywołań) oraz udostępnia funkcje, takie jak obszar na pliki tymczasowe (bezpieczny obszar magazynu na komputerze klienckim) i kontrolowane przez użytkownika operacje we/wy na plikach. Ustawienie Wysoki poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy. Wyłącz język Java, aby uniemożliwić uruchamianie jakichkolwiek apletów. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można uruchamiać apletów Java. Jeśli to ustawienie zasad nie zostanie skonfigurowane, aplety Java będą wyłączone.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067082)  
  
  **Domyślne**: Wyłącz Java  
  
- **Rozszerzony tryb chroniony programu Internet Explorer**  
  Rozszerzony tryb chroniony zapewnia dodatkową ochronę przed złośliwymi witrynami internetowymi dzięki użyciu 64-bitowych procesów w 64-bitowych wersjach systemu Windows. Na komputerach z systemem w wersji co najmniej Windows 8 rozszerzony tryb chroniony ogranicza także lokalizacje, z których program Internet Explorer może czytać w rejestrze i w systemie plików. Jeśli to ustawienie zasad jest włączone, rozszerzony tryb chroniony jest włączony. W każdej strefie, w której włączono tryb chroniony, będzie używany rozszerzony tryb chroniony. Użytkownicy nie będą mogli wyłączyć rozszerzonego trybu chronionego. Jeśli to ustawienie zasad jest wyłączone, rozszerzony tryb chroniony jest wyłączony. We wszystkich strefach z włączonym trybem chronionym będzie używana wersja trybu chronionego wprowadzona w programie Internet Explorer 7 dla systemu Windows Vista. Jeśli te zasady nie zostaną skonfigurowane, użytkownicy mogą włączać i wyłączać rozszerzony tryb chroniony na karcie Zaawansowane w oknie dialogowym Opcje internetowe.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067158)  
  
  **Domyślne**: włączone  
  
- **Program Internet Explorer pomija ostrzeżenia filtra SmartScreen**  
  To ustawienie zasad określa, czy użytkownik może pomijać ostrzeżenia filtra SmartScreen. Filtr SmartScreen wysyła do użytkownika ostrzeżenia o plikach wykonywalnych, których użytkownicy programu Internet Explorer nie pobierają często z Internetu. Jeśli to ustawienie zasad zostanie włączone, ostrzeżenia filtra SmartScreen będą blokować użytkownika. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownik będzie mógł pomijać ostrzeżenia filtra SmartScreen.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067159)  
  
  **Domyślne**: wyłączone  
  
- **Ustawienie Meta Refresh w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie tym, czy przeglądarka użytkownika może być przekierowywana do innej strony internetowej, gdy autor strony internetowej używa ustawienia (tagu) Meta Refresh w celu przekierowywania przeglądarek do innej strony internetowej. Jeśli to ustawienie zasad zostanie włączone, przeglądarka użytkownika, która ładuje stronę zawierającą aktywne ustawienie Meta Refresh, będzie mogła zostać przekierowana do innej strony internetowej. Jeśli to ustawienie zasad zostanie wyłączone, przeglądarka użytkownika, która ładuje stronę zawierającą aktywne ustawienie Meta Refresh, nie będzie mogła zostać przekierowana do innej strony internetowej. Jeśli to ustawienie zasad nie zostanie skonfigurowane, przeglądarka użytkownika, która ładuje stronę zawierającą aktywne ustawienie Meta Refresh, nie będzie mogła zostać przekierowana do innej strony internetowej.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067154)  
  
  **Domyślne**: wyłączone  
  
## <a name="local-policies-security-options"></a>Opcje zabezpieczeń zasad lokalnych
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — LocalPoliciesSecurityOptions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions) w dokumentacji systemu Windows. 

- **Ograniczaj dostęp anonimowy do nazwanych potoków i udziałów**  
  Po włączeniu to ustawienie zabezpieczeń ogranicza anonimowy dostęp do udziałów i potoków ustawień dla: (1) nazwanych potoków, do których można uzyskiwać dostęp anonimowo (2) udziałów, do których można uzyskiwać dostęp anonimowo.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067212)  
  
  **Domyślne**: Tak  
  
- **Minimalne zabezpieczenia sesji dla serwerów opartych ma technologii SSP NTLM**  
  To ustawienie zabezpieczeń pozwala serwerowi na wymaganie negocjacji szyfrowania 128-bitowego i/lub zabezpieczeń sesji NTLMv2. Te wartości są zależne od wartości ustawienia zabezpieczeń Poziom uwierzytelniania programu LAN Manager. Opcje to: Wymagaj zabezpieczeń sesji NTLMv2: Połączenie nie powiedzie się, jeśli nie zostanie wynegocjowana integralność komunikatów. Wymagaj szyfrowania 128-bitowego. Połączenie będzie nieudane, jeśli nie zostanie wynegocjowane silne szyfrowanie (128-bitowe).  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067246) 
  
  **Domyślne**: wymagaj protokołu NTLM V2 i szyfrowania 128-bitowego  
  
- **Liczba minut braku aktywności na ekranie blokady przed aktywowaniem wygaszacza ekranu**  
  System Windows wykryje nieaktywność sesji logowania, a gdy czas nieaktywności przekroczy limit nieaktywności, zostanie uruchomiony wygaszacz ekranu i nastąpi zablokowanie sesji.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067210)  
  
  **Domyślne**: 15
  
- **Wymagaj od klienta, aby zawsze podpisywał cyfrowo komunikację** To ustawienie zabezpieczeń określa, czy cały ruch w bezpiecznym kanale inicjowany przez element członkowski domeny musi być podpisany lub zaszyfrowany. Po dołączeniu komputera do domeny zostanie utworzone konto komputera. Następnie podczas uruchamiania systemu zostanie użyte hasło konta komputera, aby utworzyć bezpieczny kanał z kontrolerem dla jego domeny. Ten bezpieczny kanał służy do wykonywania operacji, takich jak uwierzytelnianie przekazywane NTLM, wyszukiwanie nazw/SID LSA i nie tylko. To ustawienie określa, czy cały ruch w bezpiecznym kanale inicjowany przez element członkowski domeny spełnia minimalne wymagania dotyczące zabezpieczeń. W szczególności określa, czy cały ruch w bezpiecznym kanale uruchomiony przez element członkowski domeny musi być podpisany lub zaszyfrowany. Jeśli te zasady zostaną włączone, bezpieczny kanał nie będzie tworzony, chyba że zostanie wynegocjowane podpisywanie lub szyfrowanie całego ruchu w bezpiecznym kanale. Jeśli te zasady zostaną wyłączone, szyfrowanie i podpisywanie całego ruchu w bezpiecznym kanale będzie negocjowane z kontrolerem domeny. W takim przypadku poziom podpisywania i szyfrowania będzie zależał od wersji kontrolera domeny i ustawień następujących dwóch zasad: Członek domeny: szyfruj cyfrowo dane bezpiecznego kanału — gdy to możliwe i Członek domeny: podpisuj cyfrowo dane bezpiecznego kanału — gdy to możliwe.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067187) 
  
  **Domyślne**: Tak
  
- **Poziom uwierzytelniania**  
  To ustawienie zabezpieczeń określa, który protokół uwierzytelniania typu żądanie/odpowiedź będzie używany podczas logowania do sieci. Ten wybór ma wpływ na poziom protokołu uwierzytelniania używanego przez klientów, poziom wynegocjowanych zabezpieczeń sesji i poziom uwierzytelniania akceptowany przez serwery w następujący sposób:  
  - *Wysyłaj odpowiedzi LM i NTLM* — klienci korzystają z uwierzytelniania LM oraz NTLM i nigdy nie używają zabezpieczeń sesji NTLMv2; kontrolery domeny akceptują uwierzytelnianie LM, NTLM i NTLMv2. 
  - *Wysyłaj odpowiedzi LM i NTLM — NTLMv2, jeśli zostaną wynegocjowane* — klienci korzystają z uwierzytelniania LM oraz NTLM i używają zabezpieczeń sesji NTLMv2, jeśli są one obsługiwane przez serwer; kontrolery domeny akceptują uwierzytelnianie LM, NTLM i NTLMv2. 
  - *Wysyłaj tylko odpowiedź NTLM:* — klienci korzystają tylko z uwierzytelniania NTLM i używają zabezpieczeń sesji NTLMv2, jeśli są one obsługiwane przez serwer; kontrolery domeny akceptują uwierzytelnianie LM, NTLM i NTLMv2. 
  - *Wysyłaj tylko odpowiedź NTLMv2* — klienci korzystają tylko z uwierzytelniania NTLMv2 i używają zabezpieczeń sesji NTLMv2, jeśli są one obsługiwane przez serwer; kontrolery domeny akceptują uwierzytelnianie LM, NTLM i NTLMv2. 
  - *Wysyłaj tylko odpowiedź NTLMv2. Odrzucaj odpowiedzi LM*: klienci korzystają tylko z uwierzytelniania NTLMv2 i używają zabezpieczeń sesji NTLMv2, jeśli są one obsługiwane przez serwer; kontrolery domeny odrzucają uwierzytelnianie LM (akceptują tylko uwierzytelnianie NTLM i NTLMv2). 
  - *Wysyłaj tylko odpowiedź NTLMv2. Odrzucaj odpowiedzi LM i NTLM* — klienci korzystają tylko z uwierzytelniania NTLMv2 i używają zabezpieczeń sesji NTLMv2, jeśli są one obsługiwane przez serwer; kontrolery domeny odrzucają uwierzytelnianie LM i NTLM (akceptują tylko uwierzytelnianie NTLMv2).  

  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067189)   
    
  **Domyślne**: wysyłaj tylko odpowiedź NTLMv2. Odrzucaj odpowiedzi LM i NTLM
  
- **Uniemożliwiaj klientom wysyłanie niezaszyfrowanych haseł do serwerów SMB innych firm**  
  Jeśli to ustawienie zabezpieczeń zostanie włączone, funkcja przekierowania bloku komunikatów serwera (SMB) będzie mogła wysyłać hasła w postaci zwykłego tekstu do serwerów SMB firm innych niż Microsoft, które nie obsługują szyfrowania haseł podczas uwierzytelniania. Wysyłanie niezaszyfrowanych haseł stanowi zagrożenie bezpieczeństwa.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067235)  
  
  **Domyślne**: Tak
  
- **Zawsze wymagaj serwera podpisującego cyfrowo komunikację**  
  To ustawienie zabezpieczeń określa, czy klient SMB próbuje negocjować podpisywanie pakietów SMB. Protokół bloku komunikatów serwera (SMB) stanowi podstawę do udostępniania plików i drukarek Microsoft oraz wielu innych operacji sieciowych, takich jak zdalne administrowanie systemem Windows. Aby zapobiegać atakom typu man-in-the-middle, które modyfikują pakiety SMB podczas przesyłania, protokół SMB obsługuje cyfrowe podpisywanie pakietów SMB. To ustawienie zasad określa, czy składnik klienta SMB próbuje negocjować podpisywanie pakietów SMB podczas łączenia z serwerem SMB. Jeśli to ustawienie zostanie włączone, klient sieci firmy Microsoft będzie żądał od serwera podpisania pakietów SMB podczas konfigurowania sesji. Jeśli podpisywanie pakietów zostało włączone na serwerze, jest negocjowane podpisywanie pakietów. Jeśli te zasady zostały wyłączone, klient SMB nigdy nie będzie negocjował podpisywania pakietów SMB.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067319)  
  
  **Domyślne**: Tak
  
- **Działanie monitu o podniesienie uprawnień administratora**  
  To ustawienie zasad steruje działaniem monitu o podniesienie uprawnień w przypadku administratorów. Dostępne są następujące opcje: 
  - *Podnieś bez monitowania* — umożliwia uprzywilejowanym kontom wykonanie operacji, która wymaga podniesienia uprawnień, bez konieczności wymagania zgody lub poświadczeń. Uwaga: tej opcji należy używać tylko w środowiskach z największymi ograniczeniami. 
  - *Monituj o podanie poświadczeń na bezpiecznym pulpicie* — jeśli operacja wymaga podniesienia uprawnień, na bezpiecznym pulpicie zostanie wyświetlony monit o wprowadzenie nazwy i hasła uprzywilejowanego użytkownika. Jeśli użytkownik wprowadzi prawidłowe poświadczenia, operacja będzie kontynuowana przy użyciu najwyższych dostępnych uprawnień użytkownika. 
  - *Monituj o zgodę na bezpiecznym pulpicie* — jeśli operacja wymaga podniesienia uprawnień, na bezpiecznym pulpicie zostanie wyświetlony monit o wybranie pozycji Zezwól lub Odmów. Jeśli użytkownik wybierze pozycję Zezwól, operacja będzie kontynuowana przy użyciu najwyższych dostępnych uprawnień użytkownika. 
  - *Monituj o poświadczenia* — jeśli operacja wymaga podniesienia uprawnień, zostanie wyświetlony monit o wprowadzenie nazwy i hasła użytkownika administracyjnego. Jeśli użytkownik wprowadzi prawidłowe poświadczenia, operacja będzie kontynuowana przy użyciu odpowiednich uprawnień. 
  - *Monituj o zgodę* — jeśli operacja wymaga podniesienia uprawnień, zostanie wyświetlony monit o wybranie pozycji Zezwól lub Odmów. Jeśli użytkownik wybierze pozycję Zezwól, operacja będzie kontynuowana przy użyciu najwyższych dostępnych uprawnień użytkownika.  
  - *Monituj o zgodę w przypadku plików binarnych z systemem innym niż Windows* — jeśli operacja dotycząca aplikacji firmy innej niż Microsoft wymaga podniesienia uprawnień, na bezpiecznym pulpicie zostanie wyświetlony monit o wybranie pozycji Zezwól lub Odmów. Jeśli użytkownik wybierze pozycję Zezwól, operacja będzie kontynuowana przy użyciu najwyższych dostępnych uprawnień użytkownika. 
  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067215)   
  
  **Domyślne**: monituj o zgodę na bezpiecznym pulpicie
  
- **Minimalne zabezpieczenia sesji dla klientów opartych na technologii SSP NTLM**  
  To ustawienie zabezpieczeń pozwala klientowi na wymaganie negocjacji szyfrowania 128-bitowego i/lub zabezpieczeń sesji NTLMv2. Te wartości są zależne od wartości ustawienia zabezpieczeń Poziom uwierzytelniania programu LAN Manager. Dostępne są następujące opcje:
  - *Wymagaj zabezpieczeń sesji NTLMv2* — połączenie nie powiedzie się, jeśli nie zostanie wynegocjowany protokół NTLMv2. 
  - *Wymagaj szyfrowania 128-bitowego* — połączenie nie powiedzie się, jeśli nie zostanie wynegocjowane silne szyfrowanie (128-bitowe).
  - *Wymagaj protokołu NTLMv2 i szyfrowania 128-bitowego*.  

  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067324)  

  **Domyślne**: wymagaj protokołu NTLM V2 i szyfrowania 128-bitowego
  
- **Zachowanie po wyjęciu karty inteligentnej**  
  To ustawienie zabezpieczeń określa, co się stanie, gdy karta inteligentna zalogowanego użytkownika zostanie usunięta z czytnika kart inteligentnych. Dostępne są następujące opcje:
  - *Brak akcji*. 
  - *Zablokuj stację roboczą* — stacja robocza jest blokowana po wyjęciu karty inteligentnej, dzięki czemu użytkownicy mogą opuścić obszar, zabierając ze sobą kartę inteligentną, i nadal utrzymywać chronioną sesję.
  - *Wymuszaj wylogowanie* — użytkownik jest automatycznie wylogowywany po wyjęciu karty inteligentnej.
  - *Rozłącz sesję pulpitu zdalnego* — usunięcie karty inteligentnej powoduje rozłączenie sesji bez wylogowywania użytkownika. Umożliwia to użytkownikowi włożenie karty inteligentnej i wznowienie sesji w późniejszym czasie lub na innym komputerze z czytnikiem kart inteligentnych bez konieczności ponownego logowania się. Jeśli sesja jest lokalna, te zasady działają tak samo, jak w przypadku opcji Zablokuj stację roboczą.
  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067331) 
    
  **Domyślne**: Zablokuj stację roboczą
  
- **Blokuj anonimowe wyliczanie kont SAM i udziałów**  
  To ustawienie zabezpieczeń określa, czy jest dozwolone anonimowe wyliczanie kont SAM i udziałów. System Windows pozwala użytkownikom anonimowym na wykonywanie pewnych działań, takich jak wyliczanie nazw kont domeny i udziałów sieciowych. Jest to wygodne, na przykład gdy administrator chce udzielić dostępu użytkownikom w zaufanej domenie, w której nie jest utrzymywane wzajemne zaufanie. Jeśli nie chcesz pozwolić na anonimowe wyliczanie kont SAM i udziałów, wybierz ustawienie *Tak* dla tych zasad.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067191)  
  
  **Domyślne**: Tak
  
- **Blokuj zdalne logowanie przy użyciu pustego hasła**  
  To ustawienie zabezpieczeń określa, czy konta lokalne, które nie są chronione hasłem, mogą być używane do logowania się z lokalizacji innych niż konsola fizycznego komputera. Jeśli to ustawienie zostanie włączone, konta lokalne, które nie są chronione hasłem, będą wymuszały logowanie się przy użyciu klawiatury komputera. 

  *Ostrzeżenie*: komputery, które nie znajdują się w fizycznie zabezpieczonych lokalizacjach, powinny zawsze wymuszać zasady silnych haseł dla wszystkich kont użytkowników lokalnych. W przeciwnym razie każda osoba mająca fizyczny dostęp do komputera będzie mogła zalogować się przy użyciu konta użytkownika, które nie ma hasła. Jest to szczególnie ważne w przypadku komputerów przenośnych. 

  Jeśli ta zasada zabezpieczeń zostanie zastosowana do grupy Wszyscy, nikt nie będzie mógł zalogować się za pośrednictwem usług pulpitu zdalnego. To ustawienie nie wpływa na logowanie z użyciem kont domeny. W przypadku aplikacji korzystających ze zdalnego logowania interakcyjnego istnieje możliwość obejścia tego ustawienia.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067219)  
  
  **Domyślne**: Tak
  
- **Działanie monitu o podniesienie uprawnień standardowego użytkownika**  
  To ustawienie zasad steruje działaniem monitu o podniesienie uprawnień w przypadku standardowych użytkowników. 
  - *Automatycznie odrzucaj żądania podniesienia uprawnień* — gdy operacja wymaga podniesienia uprawnień, zostanie wyświetlony komunikat o błędzie odmowy dostępu, który można skonfigurować. W przedsiębiorstwie, w którym komputery działają z uprawnieniami użytkowników standardowych, można wybrać to ustawienie, aby ograniczyć liczbę wezwań pomocy technicznej. 
  - *Monituj o podanie poświadczeń na bezpiecznym pulpicie* — jeśli operacja wymaga podniesienia uprawnień, na bezpiecznym pulpicie zostanie wyświetlony monit o wprowadzenie nazwy i hasła innego użytkownika. Jeśli użytkownik wprowadzi prawidłowe poświadczenia, operacja będzie kontynuowana przy użyciu odpowiednich uprawnień. 
  - *Monituj o poświadczenia* — jeśli operacja wymaga podniesienia uprawnień, zostanie wyświetlony monit o wprowadzenie nazwy i hasła użytkownika administracyjnego. Jeśli użytkownik wprowadzi prawidłowe poświadczenia, operacja będzie kontynuowana przy użyciu odpowiednich uprawnień.  

  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067183)  
  
  **Domyślne**: automatycznie odrzucaj żądania podniesienia uprawnień
  
- **Wymagaj trybu zatwierdzania przez administratora dla administratorów**  
  To ustawienie zasad kontroluje zachowanie wszystkich ustawień zasad funkcji Kontrola konta użytkownika (UAC) dla komputera. Jeśli to ustawienie zasad zostanie zmienione, należy uruchomić ponownie komputer. Dostępne są następujące opcje:   
  - *Nieskonfigurowane* — tryb zatwierdzania przez administratora i wszystkie powiązane ustawienia zasad funkcji Kontrola konta użytkownika będą wyłączone. Uwaga: jeśli to ustawienie zasad zostanie wyłączone, Centrum zabezpieczeń powiadomi Cię o pogorszeniu ogólnego stanu zabezpieczeń systemu operacyjnego. 
  - *Tak* — tryb zatwierdzania przez administratora zostanie włączony. Te zasady muszą być włączone, a powiązane z nimi ustawienia zasad funkcji Kontrola konta użytkownika muszą być odpowiednio ustawione, aby wbudowane konto administratora i wszystkich pozostałych użytkowników, którzy są członkami grupy Administratorzy, można było uruchamiać w trybie zatwierdzania przez administratora.  

  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067184)  
  
  **Domyślne**: Tak
  
- **Zapobiegaj anonimowemu wyliczaniu kont SAM**  
  To ustawienie zabezpieczeń określa, jakie dodatkowe uprawnienia są udzielane dla anonimowych połączeń z komputerem. System Windows pozwala użytkownikom anonimowym na wykonywanie pewnych działań, takich jak wyliczanie nazw kont domeny i udziałów sieciowych. Jest to wygodne, na przykład gdy administrator chce udzielić dostępu użytkownikom w zaufanej domenie, w której nie jest utrzymywane wzajemne zaufanie. Ta opcja zabezpieczeń umożliwia nakładanie dodatkowych ograniczeń na połączenia anonimowe w następujący sposób: 
  - *Tak* — nie zezwalaj na wyliczanie kont SAM. Ta opcja powoduje zamianę grupy Wszyscy na grupę Uwierzytelnieni użytkownicy w uprawnieniach zabezpieczeń dotyczących zasobów.
  - *Nieskonfigurowane* — brak dodatkowych ograniczeń. Polegaj na uprawnieniach domyślnych.  
  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067318)  

  **Domyślne**: Tak
  
- **Zezwalaj na zdalne połączenia z menedżerem kont zabezpieczeń**  
  To ustawienie zasad pozwala ograniczyć zdalne połączenia rpc z menedżerem kont zabezpieczeń. Jeśli nie zostanie wybrane, używany jest domyślny deskryptor zabezpieczeń.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067209)  
  
  **Domyślne**: *O:BAG:BAD:(A;;RC;;;BA)*

- **Używaj trybu zatwierdzania przez administratora**  
  To ustawienie zasad steruje zachowaniem trybu zatwierdzania przez administratora w przypadku wbudowanego konta administratora. Dostępne są następujące opcje: 
  - *Tak* — wbudowane konto administratora używa trybu zatwierdzania przez administratora. Domyślnie każda operacja, która wymaga podniesienia uprawnień, będzie monitowała użytkownika o zatwierdzenie operacji. 
  - *Nieskonfigurowane* — wbudowane konto administratora uruchamia wszystkie aplikacje z pełnymi uprawnieniami administracyjnymi. 

  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067186)  

  **Domyślne**: Tak
  
- **Zezwalaj na aplikacje dostępu do interfejsu użytkownika w bezpiecznych lokalizacjach**  
  To ustawienie zasad umożliwia zdecydowanie, czy programy z funkcją dostępności interfejsu użytkownika (UIAccess lub UIA, User Interface Accessibility) mogą automatycznie wyłączać bezpieczny pulpit na potrzeby monitowania o podniesienie uprawnień przez użytkownika standardowego. 
  - *Tak* — programy z automatyzacją interfejsu użytkownika, w tym Pomoc zdalna systemu Windows, będą automatycznie wyłączać bezpieczny pulpit w przypadku monitowania o podniesienie uprawnień. Jeśli nie wyłączysz ustawienia zasad „Kontrola konta użytkownika: przełącz na bezpieczny pulpit przy monitowaniu o podniesienie uprawnień”, monity będą wyświetlane na pulpicie użytkownika interakcyjnego, a nie na bezpiecznym pulpicie. 
  - *Nieskonfigurowane* — bezpieczny pulpit może zostać wyłączony tylko przez użytkownika pulpitu interakcyjnego lub przez wyłączenie ustawienia zasad „Kontrola konta użytkownika: przełącz na bezpieczny pulpit przy monitowaniu o podniesienie uprawnień”.  

  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067185)  

  **Domyślne**: Tak

- **Wykrywanie instalacji aplikacji i monitowanie o podniesienie uprawnień**  
  To ustawienie zasad steruje zachowaniem wykrywania instalacji aplikacji na komputerze. Dostępne są następujące opcje: 
  - *Włączone* — w przypadku wykrycia pakietu instalacyjnego aplikacji, który wymaga podwyższonego poziomu uprawnień, użytkownik jest monitowany o podanie nazwy użytkownika administracyjnego i hasła. Jeśli użytkownik wprowadzi prawidłowe poświadczenia, operacja będzie kontynuowana przy użyciu odpowiednich uprawnień. 
  - *Wyłączone* — pakiety instalacyjne aplikacji nie są wykrywane i monitowane o podniesienie poziomu uprawnień. W przedsiębiorstwach, które korzystają z pulpitów użytkowników standardowych i technologii instalacji delegowanej, takich jak instalacja oprogramowania zasad grupy lub Systems Management Server (SMS), to ustawienie zasad powinno zostać wyłączone. W tym przypadku wykrywanie instalatora nie jest konieczne.  
  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067208)  

  **Domyślne**: Tak
  
- **Zapobiegaj przechowywaniu wartości skrótu programu LAN Manager dla następnej zmiany hasła**  
  To ustawienie zabezpieczeń określa, czy przy następnej zmianie hasła będzie przechowywana wartość skrótu programu LAN Manager (LM) dla nowego hasła. Skrót programu LM jest stosunkowo słaby i podatny na atak w porównaniu do silniejszego kryptograficznie skrótu systemu Windows NT. Ponieważ skrót programu LM jest przechowywany na komputerze lokalnym w bazie danych zabezpieczeń, hasła mogą zostać złamane po zaatakowaniu bazy danych.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067213)  
  
  **Domyślne**: Tak

- **Wirtualizuj błędy zapisu w plikach i rejestrze w lokalizacjach poszczególnych użytkowników**  
  To ustawienie zasad kontroluje, czy błędy zapisu aplikacji są przekierowywane do zdefiniowanych lokalizacji rejestru i systemu plików. To ustawienie zasad ogranicza liczbę aplikacji uruchamianych w trybie administratora i zapisuje dane aplikacji w czasie wykonywania w katalogu *%ProgramFiles%* , *%Windir%* , *%Windir%\system32* lub *HKLM\Software*.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067321)  
  
  **Domyślne**: Tak

## <a name="ms-security-guide"></a>Przewodnik po zabezpieczeniach firmy MS  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — MSSecurityGuide](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mssecurityguide) w dokumentacji systemu Windows.  

- **Stosuj ograniczenia funkcji Kontrola konta użytkownika do kont lokalnych podczas logowania do sieci**  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067188)  

  **Domyślne**: włączone
  
- **Konfiguracja uruchamiania sterownika klienta SMB v1**  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067214) 
 
  **Domyślne**: wyłączony sterownik
  
- **Serwer SMB v1**  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067190)  

  **Domyślne**: wyłączone
  
- **Uwierzytelnianie szyfrowane**  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067193) 
 
  **Domyślne**: wyłączone
  
- **Ochrona przed zastąpieniem obsługi wyjątków strukturalnych**  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067217)  

  **Domyślne**: włączone
  
## <a name="mss-legacy"></a>Starsza wersja MSS  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — MSSLegacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-msslegacy) w dokumentacji systemu Windows.  

- **Poziom ochrony routingu źródła protokołu IP sieci**  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067220)  
  
  **Domyślne**: Najwyższa ochrona  
  
- **Sieć ignoruje żądania wydania nazwy NetBIOS z wyjątkiem żądań z serwerów WINS**  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067218)  
 
  **Domyślne**: włączone
  
- **Poziom ochrony routingu źródła protokołu IPv6 sieci**  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067216)  

  **Domyślne**: Najwyższa ochrona

- **Przekierowania protokołu ICMP sieci zastępują wygenerowane przez OSPF**  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067326)  

  **Domyślne**: wyłączone
  
## <a name="power"></a>Zasilanie  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — Power](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power) w dokumentacji systemu Windows.  

- **Wymagaj hasła przy wznawianiu, gdy urządzenie jest zasilane z sieci**  
  To ustawienie zasad określa, czy użytkownik ma być monitowany o podanie hasła podczas wznawiania działania systemu po trybie uśpienia. Jeśli to ustawienie zasad zostanie włączone lub nie zostanie skonfigurowane, użytkownik będzie monitowany o podanie hasła podczas wznawiania działania systemu po trybie uśpienia. Jeśli to ustawienie zasad zostanie wyłączone, użytkownik nie będzie monitowany o podanie hasła podczas wznawiania działania systemu po trybie uśpienia.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067221)  
  
  **Domyślne**: włączone
  
- **Stany wstrzymania podczas uśpienia, gdy urządzenie jest zasilane z baterii**  
  To ustawienie zasad określa, czy system Windows może używać stanów wstrzymania podczas przełączania komputera w stan uśpienia. Jeśli to ustawienie zasad zostanie włączone lub nie zostanie skonfigurowane, system Windows będzie używał stanów wstrzymania do przełączania komputera w stan uśpienia. Jeśli to ustawienie zasad zostanie wyłączone, stany wstrzymania (S1–S3) będą niedozwolone.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067195)  
  
  **Domyślne**: wyłączone
  
- **Stany wstrzymania podczas uśpienia, gdy urządzenie jest zasilane z sieci**  
  To ustawienie zasad określa, czy system Windows może używać stanów wstrzymania podczas przełączania komputera w stan uśpienia. Jeśli to ustawienie zasad zostanie włączone lub nie zostanie skonfigurowane, system Windows będzie używał stanów wstrzymania do przełączania komputera w stan uśpienia. Jeśli to ustawienie zasad zostanie wyłączone, stany wstrzymania (S1–S3) będą niedozwolone.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067196)  
  
  **Domyślne**: wyłączone
  
- **Wymagaj hasła przy wznawianiu, gdy urządzenie jest zasilane z baterii**  
  To ustawienie zasad określa, czy użytkownik ma być monitowany o podanie hasła podczas wznawiania działania systemu po trybie uśpienia. Jeśli to ustawienie zasad zostanie włączone lub nie zostanie skonfigurowane, użytkownik będzie monitowany o podanie hasła podczas wznawiania działania systemu po trybie uśpienia. Jeśli to ustawienie zasad zostanie wyłączone, użytkownik nie będzie monitowany o podanie hasła podczas wznawiania działania systemu po trybie uśpienia.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067322)  
  
  **Domyślne**: włączone

## <a name="remote-assistance"></a>Pomoc zdalna
- **Żądanie pomocy zdalnej**  
  To ustawienie zasad umożliwia włączenie lub wyłączenie pomocy zdalnej na żądanie na tym komputerze. 
  - *Włączenie tego ustawienia zasad*spowoduje, że użytkownicy na tym komputerze będą mogli korzystać z poczty e-mail lub transferu plików, aby poprosił kogoś o pomoc. Ponadto użytkownicy mogą używać programów do obsługi wiadomości błyskawicznych, aby zezwalać na połączenia z tym komputerem i można skonfigurować dodatkowe ustawienia pomocy zdalnej. 
  - *Jeśli to ustawienie zasad zostanie wyłączone*, użytkownicy na tym komputerze nie będą mogli korzystać z poczty e-mail ani transferu plików, aby poprosił kogoś o pomoc. Użytkownicy nie mogą również używać programów do obsługi wiadomości błyskawicznych, aby zezwalać na połączenia z tym komputerem. 
  - *Jeśli to ustawienie zasad nie zostanie skonfigurowane*, użytkownicy mogą włączać lub wyłączać samodzielną pomoc zdalną w oknie właściwości systemu w panelu sterowania. Użytkownicy mogą również konfigurować ustawienia pomocy zdalnej. 

  Jeśli włączysz to ustawienie zasad, masz dwa sposoby zezwalania pomocnikom na zapewnienie pomocy zdalnej: "Zezwalaj pomocnikom tylko na wyświetlanie komputera" lub "Zezwalaj pomocnikom na zdalne sterowanie komputerem". Ustawienie zasad "maksymalny czas biletu" określa limit czasu, przez który zaproszenie pomocy zdalnej utworzone przy użyciu poczty e-mail lub transferu plików może pozostać otwarte. Ustawienie "Wybierz metodę wysyłania zaproszeń e-mail" określa, który Standard poczty e-mail ma być używany do wysyłania zaproszeń pomocy zdalnej. W zależności od programu poczty e-mail można użyć standardu mailto (odbiorca zaproszenia za pośrednictwem linku internetowego) lub standardu SMAPI (Simple MAPI) (zaproszenie jest dołączone do wiadomości e-mail). To ustawienie zasad nie jest dostępne w systemie Windows Vista, ponieważ jedyna obsługiwana metoda to SMAPI. Jeśli to ustawienie zasad zostanie włączone, należy również włączyć odpowiednie wyjątki zapory, aby umożliwić komunikację zdalną.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067198)

  **Domyślne**: Wyłącz pomoc zdalną

  Po ustawieniu opcji *Włącz pomoc zdalną*skonfiguruj następujące ustawienia dodatkowe:  
  - **Uprawnienie do pomocy zdalnej**  
    **Domyślne**: Wyświetl  

  - **Maksymalna wartość czasu biletu**  
    **Domyślne**: *Nieskonfigurowane*  

  - **Maksymalny okres biletu**  
    **Wartość domyślna**: minuty    

  - **Metoda zaproszenia E-Mail**  
    **Domyślnie**: Simple MAPI

  
## <a name="remote-desktop-services"></a>Usługi pulpitu zdalnego  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — RemoteDesktopServices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotedesktopservices) w dokumentacji systemu Windows.  

- **Blokuj zapisywanie haseł**  
  Określa, czy hasła mogą być zapisywane w oknie Podłączanie pulpitu zdalnego na tym komputerze. Jeśli to ustawienie jest włączone, pole wyboru zapisywania haseł w oknie Podłączanie pulpitu zdalnego jest wyłączone, a użytkownicy nie będą mogli zapisywać haseł. Gdy użytkownik otwiera plik RDP za pomocą funkcji Podłączanie pulpitu zdalnego i zapisuje swoje ustawienia, wszystkie hasła, które wcześniej istniały w pliku RDP, są usuwane. Jeśli to ustawienie jest wyłączone lub nieskonfigurowane, użytkownik może zapisywać hasła za pomocą funkcji Podłączanie pulpitu zdalnego.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067301)  
  
   **Domyślne**: włączone
  
- **Bezpieczna komunikacja RPC**  
  Określa, czy serwer hosta sesji usług pulpitu zdalnego będzie wymagał bezpiecznej komunikacji RPC ze wszystkimi klientami, czy też będzie umożliwiał komunikację niezabezpieczoną. To ustawienie umożliwia poprawę zabezpieczeń komunikacji RPC z klientami, zezwalając tylko na żądania uwierzytelnione i szyfrowane. Jeśli stan zostanie ustawiony na Włączono, usługi pulpitu zdalnego będą akceptowały żądania od klientów RPC obsługujących bezpieczne żądania, a nie będą zezwalały na niezabezpieczoną komunikację z klientami niezaufanymi. Jeśli stan zostanie ustawiony na Wyłączono, usługi pulpitu zdalnego zawsze będą żądały zabezpieczeń dla całego ruchu RPC. Jednak niezabezpieczona komunikacja będzie dozwolona w przypadku klientów RPC, którzy nie odpowiadają na żądanie. Jeśli stan zostanie ustawiony na Nie skonfigurowano, niezabezpieczona komunikacja będzie dozwolona. Uwaga: interfejs usług RPC służy do administrowania usługami pulpitu zdalnego i ich konfigurowania.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067248)  
  
  **Domyślne**: włączone
  
- **Blokuj przekierowywanie dysków**  
  To ustawienie zasad określa, czy zapobiegać mapowaniu dysków klienta w ramach sesji usług pulpitu zdalnego (przekierowywaniu dysków). Domyślnie serwer hosta sesji usług pulpitu zdalnego automatycznie mapuje dyski klienta po podłączeniu. Zamapowane dyski są wyświetlane w drzewie folderów sesji w Eksploratorze plików lub na komputerze w formacie *\<litera_dysku>* na *\<nazwa_komputera>* . To ustawienie zasad umożliwia zmianę tego zachowania. Jeśli to ustawienie zasad zostanie włączone, przekierowywanie dysków klienta nie będzie dozwolone w ramach sesji usług pulpitu zdalnego, a przekierowywanie kopii plików ze Schowka nie będzie dozwolone na komputerach z systemami Windows Server 2003, Windows 8 i Windows XP. Jeśli to ustawienie zasad zostanie wyłączone, przekierowywanie dysków klienta będzie zawsze dozwolone. Ponadto przekierowywanie kopii plików ze Schowka będzie zawsze dozwolone, gdy będzie dozwolone przekierowywanie Schowka. Jeśli to ustawienie zasad nie zostanie skonfigurowane, przekierowywanie dysków klienta i przekierowywanie kopii plików ze Schowka nie będzie określane na poziomie zasad grupy.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067197)  
  
  **Domyślne**: włączone
  
- **Monit o podanie hasła podczas nawiązywania połączenia**  
  To ustawienie zasad określa, czy usługi pulpitu zdalnego zawsze będą wyświetlały klientowi monit o podanie hasła podczas nawiązywania połączenia. To ustawienie służy do wymuszania monitu o podanie hasła dla użytkowników, którzy logują się do usług pulpitu zdalnego, nawet wtedy, gdy podali już hasło w kliencie usługi Podłączanie pulpitu zdalnego. Domyślnie usługi pulpitu zdalnego umożliwiają użytkownikom automatyczne logowanie się po wprowadzeniu hasła w kliencie usługi Podłączanie pulpitu zdalnego. Jeśli to ustawienie zasad zostanie włączone, użytkownicy nie będą mogli automatycznie logować się do usług pulpitu zdalnego po podaniu haseł w kliencie usługi Podłączanie pulpitu zdalnego. Będą monitowani o podanie hasła w celu zalogowania. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy zawsze będą mogli automatycznie logować się do usług pulpitu zdalnego po podaniu haseł w kliencie usługi Podłączanie pulpitu zdalnego. Jeśli to ustawienie zasad nie zostanie skonfigurowane, automatyczne logowanie nie będzie określane na poziomie zasad grupy.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067328)  
  
  **Domyślne**: włączone
  
- **Poziom szyfrowania połączeń klienta usług pulpitu zdalnego**  
  Określa, czy do zabezpieczenia komunikacji między komputerami klienckimi a serwerami hosta sesji usług pulpitu zdalnego podczas połączeń za pomocą protokołu RDP (Remote Desktop Protocol) ma być wymagane użycie określonego poziomu szyfrowania. Te zasady mają zastosowanie tylko wtedy, gdy jest używane szyfrowanie natywne RDP. Jednak szyfrowanie natywne RDP (w przeciwieństwie do szyfrowania SSL) nie jest zalecane. Te zasady nie dotyczą szyfrowania SSL. Jeśli to ustawienie zasad zostanie włączone, cała komunikacja między klientami a serwerami hosta sesji usług pulpitu zdalnego podczas połączeń zdalnych będą musiały używać metody szyfrowania określonej w tym ustawieniu. Domyślnie poziom szyfrowania jest ustawiony na Wysoki. Dostępne są następujące metody szyfrowania:  
  - *Wysoki* — ustawienie Wysoki powoduje szyfrowanie danych wysyłanych od klienta do serwera i od serwera do klienta za pomocą silnego szyfrowania 128-bitowego. Tego poziomu szyfrowania należy używać w środowiskach zawierających tylko klientów 128-bitowych (na przykład klientów z uruchomioną funkcją Podłączanie pulpitu zdalnego). Klienci, którzy nie obsługują tego poziomu szyfrowania, nie będą mogli łączyć się z serwerami hosta sesji usług pulpitu zdalnego.  
  - *Zgodny z klientem* — ustawienie Zgodny z klientem powoduje szyfrowanie danych wysyłanych między klientem a serwerem z użyciem maksymalnej siły klucza obsługiwanej przez klienta. Tego poziomu szyfrowania należy używać w środowiskach zawierających klientów, którzy nie obsługują szyfrowania 128-bitowego.  
  - *Niski* — ustawienie Niski powoduje szyfrowanie tylko danych wysyłanych od klienta do serwera przy użyciu szyfrowania 56-bitowego.  
  
  Jeśli to ustawienie zostanie wyłączone lub nie zostanie skonfigurowane, poziom szyfrowania używany w przypadku zdalnych połączeń z serwerami hosta sesji usług pulpitu zdalnego nie będzie wymuszany za pomocą zasad grupy. Ważną zgodność ze standardem FIPS można skonfigurować za pomocą funkcji Kryptografia systemu. Algorytmów zgodnych ze standardem FIPS należy używać do szyfrowania, tworzenia skrótów i podpisywania ustawień w zasadach grupy (w obszarze Konfiguracja komputera\Ustawienia systemu Windows\Ustawienia zabezpieczeń\Zasady lokalne\Opcje zabezpieczeń). Ustawienie zgodne ze standardem FIPS powoduje szyfrowanie i odszyfrowywanie danych wysyłanych od klienta do serwera i od serwera do klienta za pomocą algorytmów szyfrowania Federal Information Processing Standard (FIPS) 140 przy użyciu modułów kryptograficznych firmy Microsoft. Tego poziomu szyfrowania należy używać, gdy komunikacja między klientami a serwerami hosta sesji usług pulpitu zdalnego wymaga najwyższego poziomu szyfrowania.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067222)  
  
  **Domyślne**: Wysoki
  
## <a name="remote-management"></a>Zdalne zarządzanie  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — RemoteManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotemanagement) w dokumentacji systemu Windows.  

- **Blokuj przechowywanie poświadczeń Uruchom jako**  
  Uwierzytelnianie podstawowe klienta.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067300)  
  
  **Domyślne**: włączone
  
- **Uwierzytelnianie podstawowe**  
  To ustawienie zasad umożliwia zarządzanie tym, czy usługa Windows Remote Management (WinRM) będzie akceptowała uwierzytelnianie podstawowe z klienta zdalnego. Jeśli to ustawienie zasad zostanie włączone, usługa WinRM będzie akceptowała uwierzytelnianie podstawowe z klienta zdalnego. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, usługa WinRM nie będzie akceptowała uwierzytelniania podstawowego z klienta zdalnego.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067223)  
  
  **Domyślne**: wyłączone
  
- **Blokuj uwierzytelnianie szyfrowane klienta**  
  To ustawienie zasad umożliwia zarządzanie tym, czy klient usługi Windows Remote Management (WinRM) będzie używał uwierzytelniania szyfrowanego. Jeśli to ustawienie zasad zostanie włączone, klient usługi WinRM nie będzie używał uwierzytelniania szyfrowanego. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, klient usługi WinRM będzie używał uwierzytelniania szyfrowanego.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067302)  
  
  **Domyślne**: włączone
  
- **Ruch niezaszyfrowany**  
  To ustawienie zasad umożliwia zarządzanie tym, czy usługa Windows Remote Management (WinRM) będzie wysyłała i odbierała niezaszyfrowane komunikaty za pośrednictwem sieci. Jeśli to ustawienie zasad zostanie włączone, klient usługi WinRM będzie wysyłał i odbierał niezaszyfrowane komunikaty za pośrednictwem sieci. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, klient usługi WinRM będzie wysyłał i odbierał tylko zaszyfrowane komunikaty za pośrednictwem sieci.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067226)  
  
  **Domyślne**: wyłączone
  
- **Niezaszyfrowany ruch klienta**  
  To ustawienie zasad umożliwia zarządzanie tym, czy klient usługi Windows Remote Management (WinRM) będzie wysyłał i odbierał niezaszyfrowane komunikaty za pośrednictwem sieci. Jeśli to ustawienie zasad zostanie włączone, klient usługi WinRM będzie wysyłał i odbierał niezaszyfrowane komunikaty za pośrednictwem sieci. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, klient usługi WinRM będzie wysyłał i odbierał tylko zaszyfrowane komunikaty za pośrednictwem sieci.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067304)  
  
  **Domyślne**: wyłączone
  
- **Uwierzytelnianie podstawowe klienta**  
  To ustawienie zasad umożliwia zarządzanie tym, czy klient usługi Windows Remote Management (WinRM) będzie używał uwierzytelniania podstawowego. Jeśli to ustawienie zasad zostanie włączone, klient usługi WinRM będzie używał uwierzytelniania podstawowego. Jeśli usługa WinRM zostanie skonfigurowana tak, aby używała transportu HTTP, nazwa użytkownika i hasło będą wysyłane przez sieć jako zwykły tekst. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, klient usługi WinRM nie będzie używał uwierzytelniania podstawowego.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067252)  
  
  **Domyślne**: wyłączone
  
## <a name="remote-procedure-call"></a>Zdalne wywoływanie procedur  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — RemoteProcedureCall](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remoteprocedurecall) w dokumentacji systemu Windows.  

- **Opcje nieuwierzytelnionego klienta RPC**  
  To ustawienie zasad określa, jak środowisko uruchomieniowe serwera RPC obsługuje nieuwierzytelnionych klientów RPC łączących się z serwerami RPC. To ustawienie zasad ma wpływ na wszystkie aplikacje RPC. W środowisku domeny tego ustawienia zasad należy używać ostrożnie, ponieważ może wpłynąć na wiele funkcji, łącznie z samym przetwarzaniem zasad grupy. Cofnięcie zmiany tego ustawienia zasad może wymagać ręcznego działania na każdej maszynie, której to dotyczy. Tego ustawienia zasad nigdy nie należy stosować do kontrolera domeny. Jeśli to ustawienie zasad zostanie wyłączone, środowisko uruchomieniowe serwera RPC będzie używać wartości „Uwierzytelnione” w kliencie systemu Windows i wartości „Brak” w wersjach systemu Windows Server, które obsługują to ustawienie zasad. Jeśli to ustawienie zasad nie zostanie skonfigurowane, pozostanie wyłączone. Środowisko uruchomieniowe serwera RPC zachowuje się tak, jakby było włączone z wartością „Uwierzytelnione” w kliencie systemu Windows i wartością „Brak” w jednostkach SKU serwera, które obsługują to ustawienie zasad. Jeśli to ustawienie zasad zostanie włączone, będzie nakazywać środowisku uruchomieniowemu serwera RPC ograniczanie nieuwierzytelnionych klientów RPC łączących się z serwerami RPC uruchomionymi na maszynie. Klient jest uznawany za uwierzytelnionego, jeśli używa nazwanego potoku do komunikacji z serwerem lub zabezpieczeń klienta RPC. Interfejsy RPC, które żądają, aby były dostępne dla nieuwierzytelnionych klientów, mogą być wykluczone z tego ograniczenia, w zależności od wybranej wartości tego ustawienia zasad.  
  - Ustawienie *Brak* zezwala wszystkim klientom RPC na łączenie się z serwerami RPC uruchomionymi na maszynie, na której zastosowano ustawienie zasad. 
  - Ustawienie *Uwierzytelnione* umożliwia tylko uwierzytelnionym klientom RPC (zgodnie z powyższą definicją) łączenie się z serwerami RPC uruchomionymi na maszynie, na której zastosowano ustawienie zasad. Wykluczenia są przyznawane interfejsom, które tego żądały. 
  - Ustawienie *Uwierzytelnione bez wyjątków* umożliwia tylko uwierzytelnionym klientom RPC (zgodnie z powyższą definicją) łączenie się z serwerami RPC uruchomionymi na maszynie, na której zastosowano ustawienie zasad. Wyjątki nie są dozwolone. Uwaga: to ustawienie zasad jest stosowane dopiero po ponownym uruchomieniu systemu.  

  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067225)  

  **Domyślne**: Uwierzytelnione

## <a name="search"></a>Wyszukaj 
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — wyszukiwanie](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-search) w dokumentacji systemu Windows.  

- **Wyłącz indeksowanie zaszyfrowanych elementów**  
  Zezwala lub nie zezwala na indeksowanie elementów. Ten przełącznik jest przeznaczony dla indeksatora programu Windows Search, który kontroluje, czy indeksuje on elementy, które są zaszyfrowane, takie jak pliki chronione przez funkcję Windows Information Protection (WIP). Gdy te zasady są włączone, elementy chronione przez funkcję WIP są indeksowane, a dotyczące ich metadane są przechowywane w lokalizacji niezaszyfrowanej. Metadane obejmują takie informacje, jak ścieżka do pliku i data modyfikacji. Gdy zasady są wyłączone, elementy chronione przez funkcję WIP nie są indeksowane i nie są wyświetlane w wynikach w Cortanie ani Eksploratorze plików. Jeśli na urządzeniu istnieje wiele plików multimedialnych chronionych przez funkcję WIP, może to także mieć wpływ na wydajność dla zdjęć i aplikacji Groove.  
  [Dowiedz się więcej]( https://go.microsoft.com/fwlink/?linkid=2067303)  
  
  **Domyślne**: Tak
  
## <a name="smart-screen"></a>SmartScreen  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — SmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen) w dokumentacji systemu Windows.  

- **Blokuj wykonywanie niezweryfikowanych plików**  
  Zablokuj użytkownikowi możliwość uruchamiania niezweryfikowanych plików. 
  - *Nieskonfigurowane* — pracownicy mogą ignorować ostrzeżenia filtru SmartScreen i uruchamiać złośliwe pliki. 
  - *Tak* — pracownicy nie mogą ignorować ostrzeżeń filtru SmartScreen i uruchamiać złośliwych plików.

  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067228)  
  
  **Domyślne**: Tak

- **Wymagaj filtra SmartScreen dla aplikacji i plików**  
  Umożliwia administratorom IT konfigurowanie filtru SmartScreen dla systemu Windows.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067168)  

  **Domyślne**: Tak
  
## <a name="system"></a>System  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — system](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system) w dokumentacji systemu Windows.  

- **Inicjowanie sterownika rozruchu systemu**  
  To ustawienie zasad pozwala określić, które sterowniki rozruchu są inicjowane na podstawie klasyfikacji określonej przez sterownik rozruchu wczesnej ochrony przed złośliwym kodem. Sterownik rozruchu wczesnej ochrony przed złośliwym kodem może zwrócić następujące klasyfikacje dla każdego sterownika rozruchu: 
  - *Dobry* — sterownik został podpisany i nie został naruszony.  
  - *Zły* — sterownik został zidentyfikowany jako złośliwy kod. Zalecamy, aby nie zezwalać na inicjowanie znanych nieprawidłowych sterowników. 
  - *Zły, ale wymagany do rozruchu* — sterownik został zidentyfikowany jako złośliwy kod, ale komputer nie może pomyślnie wykonać rozruchu bez załadowania tego sterownika. 
  - *Nieznany* — ten sterownik nie ma zaświadczenia aplikacji wykrywania złośliwego kodu i nie został sklasyfikowany przez sterownik rozruchu wczesnej ochrony przed złośliwym kodem.  

  Jeśli to ustawienie zasad zostanie włączone, można wybrać sterowniki rozruchu, które mają być inicjowane przy następnym uruchomieniu komputera. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, zostaną zainicjowane sterowniki rozruchu uznane za dobre, nieznane lub złe, ale wymagane do rozruchu, a inicjowanie sterowników uznanych za nieprawidłowe zostanie pominięte. Jeśli aplikacja wykrywania złośliwego kodu nie zawiera sterownika rozruchu wczesnej ochrony przed złośliwym kodem lub sterownik rozruchu wczesnej ochrony przed złośliwym kodem została wyłączona, to ustawienie nie obowiązuje i są inicjowane wszystkie sterowniki rozruchu.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067307)   
  
  **Domyślne**: dobry nieznany i zły krytyczny


## <a name="wi-fi"></a>Wi-Fi  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — Wifi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi) w dokumentacji systemu Windows.  

- **Blokuj udostępnianie Internetu**  
  Określa, czy udostępnianie Internetu jest obsługiwane przez urządzenie.   
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067327)   

  **Domyślne**: Tak  

- **Blokuj automatyczne połączenia z hotspotami Wi-Fi**  
  Zezwalaj lub nie zezwalaj na automatyczne połączenia urządzenia z hotspotami Wi-Fi.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067320)   

  **Domyślne**: Tak  
  
## <a name="windows-connection-manager"></a>Menedżer połączeń systemu Windows  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — WindowsConnectionManager](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsconnectionmanager) w dokumentacji systemu Windows.  

- **Blokuj połączenia z sieciami nienależącymi do domeny**  
  To ustawienie zasad uniemożliwia komputerom łączenie się z siecią opartą na domenie i siecią nienależącą do domeny w tym samym czasie. Jeśli to ustawienie zasad zostanie włączone, komputer będzie odpowiadać na próby automatycznego i ręcznego nawiązania połączenia sieciowego zależnie od następujących okoliczności: 
  - Próby automatycznego połączenia Gdy komputer jest już połączony z siecią opartą na domenie, wszystkie próby automatycznego połączenia z sieciami spoza domeny będą blokowane. Gdy komputer jest już połączony z siecią nienależącą do domeny, próby automatycznego połączenia z sieciami opartymi na domenie będą blokowane. 
  - Próby ręcznego połączenia Gdy komputer jest już połączony z siecią nienależącą do domeny lub siecią opartą na domenie przez nośnik inny niż Ethernet, a użytkownik próbuje utworzyć ręczne połączenie z dodatkową siecią niezgodnie z tym ustawieniem zasad, istniejące połączenie sieciowe zostanie zakończone i ręczne połączenie będzie dozwolone. Gdy komputer jest już połączony z siecią nienależącą do domeny lub siecią opartą na domenie przez protokół Ethernet, a użytkownik próbuje utworzyć ręczne połączenie z dodatkową siecią niezgodnie z tym ustawieniem zasad, istniejące połączenie Ethernet zostanie zachowane i próba ręcznego połączenia zostanie zablokowana.  

  Jeśli to ustawienie zasad nie zostanie skonfigurowane lub zostanie wyłączone, komputery będą mogły łączyć się jednocześnie z sieciami należącymi do domeny i nienależącymi do domeny.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067323)  

  **Domyślne**: włączone
  
## <a name="windows-defender"></a>Usługa Windows Defender  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) w dokumentacji systemu Windows.  

- **Skanuj przychodzące wiadomości e-mail**  
  Zezwala lub nie zezwala na skanowanie wiadomości e-mail.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067116)  
  
  **Domyślne**: Tak  

- **Uruchamianie typu procesów podrzędnych przez aplikacje pakietu Office**  
  Aplikacje pakietu Office nie będą mogły tworzyć procesów podrzędnych. Dotyczy to też programów Word, Excel, PowerPoint, OneNote i Access. Jest to typowe zachowanie złośliwego oprogramowania, szczególnie w przypadku ataków opartych na makrach, które polegają na próbie uruchomienia lub pobrania złośliwych plików wykonywalnych za pomocą aplikacji pakietu Office.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067121)  
  
  **Domyślne**: Blokuj
  
- **Typ zgody na przesyłanie przykładów usługi Defender**  
  Sprawdza poziom zgody użytkownika na wysyłanie danych w usłudze Windows Defender. Jeśli udzielono już wymaganej zgody, usługa Windows Defender prześle dane. W przeciwnym razie (jeśli użytkownik wybrał, aby nigdy nie wyświetlać pytania) przed wysłaniem danych zostanie uruchomiony interfejs użytkownika z pytaniem o zgodę użytkownika (jeśli zezwolono na element Defender/AllowCloudProtection).  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067131)  
  
  **Domyślne**: automatycznie wyślij bezpieczne próbki 
  
- **Interwał aktualizacji sygnatur (w godzinach)**  
  Interwał aktualizacji sygnatur usługi Defender (w godzinach)
  
  **Domyślne**: 4
  
- **Typ wykonywania pobranego ładunku skryptu**  
  Typ wykonywania pobranego ładunku skryptu usługi Defender
  
  **Domyślne**: Blokuj
  
- **Typ zapobiegania kradzieży poświadczeń**  
  Funkcja Windows Defender Credential Guard używa zabezpieczeń opartych na wirtualizacji do izolowania kluczy tajnych, aby tylko uprzywilejowane oprogramowanie systemowe mogło uzyskiwać do nich dostęp. Nieautoryzowany dostęp do tych kluczy tajnych może prowadzić do ataków przy użyciu skradzionych poświadczeń, takich jak „pass the hash” lub „pass the ticket”. Funkcja Windows Defender Credential Guard zapobiega atakom przez ochronę skrótów haseł NTLM, biletów uprawniających do przyznawania biletów protokołu Kerberos i poświadczeń przechowywanych przez aplikacje, takich jak poświadczenia domeny.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067065)  
  
  **Domyślne**: Włącz

- **Typ wykonywania zawartości wiadomości e-mail**  
  Ta reguła blokuje wykonywanie lub uruchamianie następujących typów plików z wiadomości e-mail w programie Microsoft Outlook lub poczcie internetowej (np. Gmail.com lub Outlook.com): pliki wykonywalne (takie jak exe, dll lub scr), pliki skryptów (takie jak plik ps programu PowerShell, plik vbs języka Visual Basic lub plik js języka JavaScript), pliki archiwum skryptów.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067063)  
  
  **Domyślne**: Blokuj

- **Uruchamianie programu Adobe Reader w procesie podrzędnym**  

  **Domyślne**: Włącz

- **Typ ochrony sieci**  
  Ta zasada umożliwia włączenie lub wyłączenie ochrony sieci (blokowanie/inspekcja) w funkcji Windows Defender Exploit Guard. Ochrona sieci w funkcji Windows Defender Exploit Guard chroni pracowników używających dowolnej aplikacji przed wyłudzeniem informacji, witrynami hostującymi programy wykorzystujące luki w zabezpieczeniach i złośliwą zawartością w Internecie. Obejmuje to blokadę połączeń w przeglądarkach innych firm z niebezpiecznymi witrynami. Typ wartości to liczba całkowita. Jeśli to ustawienie zostanie włączone, ochrona sieci zostanie włączona i pracownicy nie będą mogli jej wyłączyć. Jej zachowaniem można sterować przy użyciu następujących opcji: blokada i inspekcja. Jeśli te zasady są włączone z opcją „Blokada”, użytkownicy/aplikacje nie mogą łączyć się z niebezpiecznymi domenami. Ta aktywność jest widoczna w usłudze Windows Defender Security Center. Jeśli te zasady są włączone z opcją „Inspekcja”, użytkownicy/aplikacje mogą łączyć się z niebezpiecznymi domenami. Ta aktywność będzie jednak nadal widoczna w usłudze Windows Defender Security Center. Jeśli te zasady są wyłączone, użytkownicy/aplikacje mogą łączyć się z niebezpiecznymi domenami. Aktywność sieci nie będzie widoczna w usłudze Windows Defender Security Center. Jeśli te zasady nie zostaną skonfigurowane, blokada sieci będzie domyślnie wyłączona.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067102)  
  
  **Domyślne**: Włącz
  
- **Zaplanowany dzień skanowania w usłudze Defender**  
  Zaplanowany dzień skanowania w usłudze Defender.
  
  **Domyślne**: Codziennie
  
- **Ochrona w chmurze**  
  Aby najlepiej chronić komputer, usługa Windows Defender będzie wysyłać do firmy Microsoft informacje dotyczące wykrytych problemów. Firma Microsoft przeanalizuje te informacje, dowie się więcej na temat problemów wpływających na Ciebie i innych klientów oraz zaoferuje ulepszone rozwiązania.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067039)
  
  **Domyślne**: Tak  

- **Działanie dotyczące potencjalnie niechcianej aplikacji w usłudze Defender**  
  Funkcja ochrony przed potencjalnie niechcianymi aplikacjami w programie antywirusowym Windows Defender wykrywa i blokuje pobieranie potencjalnie niechcianych aplikacji oraz instalowanie w punktach końcowych w sieci. Te aplikacje nie są uważane za wirusy, złośliwe oprogramowanie ani innego typu zagrożenia, ale mogą wykonywać akcje w punktach końcowych, które niekorzystnie wpływają na wydajność lub sposób użycia. Potencjalnie niechcianymi aplikacjami mogą też być aplikacje o złej reputacji. Typowe zachowanie potencjalnie niechcianych aplikacji obejmuje: Różne rodzaje łączenia oprogramowania w pakiety Dodawanie reklam do przeglądarek internetowych Optymalizatory sterowników i rejestru, które wykrywają problemy i żądają płatności za naprawienie błędów, ale pozostają w punkcie końcowym i nie wprowadzają żadnych zmian ani optymalizacji (określane też jako „szkodliwe programy antywirusowe”). Takie aplikacje mogą narażać sieć na infekcję złośliwym oprogramowaniem, utrudniać identyfikowanie takich infekcji oraz wymagać poświęcania zasobów IT na oczyszczanie aplikacji.  
  [Dowiedz się więcej](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-puaprotection)    
  
  **Domyślne**: Blokuj  

- **Typ zaciemnionego kodu makra skryptu**  
  Złośliwe oprogramowanie i inne zagrożenia mogą próbować zaciemniać lub ukrywać złośliwy kod w niektórych plikach skryptów. Ta reguła uniemożliwia uruchamianie skryptów, które wydają się zaciemnione.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067026)  
  
  **Domyślne**: Blokuj
  
- **Skanuj dyski wymienne podczas pełnego skanowania**  
  Umożliwia usłudze Windows Defender skanowanie pod kątem złośliwego i niechcianego oprogramowania na dyskach wymiennych (na przykład dyski flash) podczas pełnego skanowania. Program antywirusowy Windows Defender skanuje wszystkie pliki na urządzeniach USB przed wykonaniem.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067036)  
  
  **Domyślne**: Tak  
  
- **Skanuj pliki archiwum**  
  Usługa Defender skanuje pliki archiwum.
  
  **Domyślne**: Tak
  
- **Monitorowanie zachowania**  
  Zezwala lub nie zezwala na działanie funkcji monitorowania zachowań Windows Defender. Osadzone w systemie Windows 10 czujniki zbierają i przetwarzają sygnały dotyczące zachowania z systemu operacyjnego i wysyłają te dane czujników do prywatnego izolowanego wystąpienia usługi Microsoft Defender ATP w chmurze.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067111)  
  
  **Domyślne**: Tak

- **Skanuj pliki otwierane z folderów sieciowych**  
  Jeśli pliki są tylko do odczytu, użytkownik nie będzie mógł usunąć wykrytego złośliwego oprogramowania.
  
  **Domyślne**: Tak

- **Niezaufany typ procesu USB**  
  Za pomocą tej reguły administratorzy mogą blokować uruchamianie niepodpisanych lub niezaufanych plików wykonywalnych z wymiennych dysków USB, w tym kart SD.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067100)  
  
  **Domyślne**: Blokuj
  
- **Typ wstrzykiwania innych procesów aplikacji pakietu Office**  
  Aplikacje pakietu Office, w tym programy Word, Excel, PowerPoint i OneNote, nie będą mogły wstrzykiwać kodu do innych procesów. Zazwyczaj jest to używane przez złośliwe oprogramowanie, aby uruchomić złośliwy kod w celu ukrycia aktywności przed aparatami skanowania antywirusowego.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067019)  
  
  **Domyślne**: Blokuj
  
- **Kod makr w pakiecie Office zezwala na typ importu elementów Win32**  
  Złośliwe oprogramowanie może używać kodu makra w plikach pakietu Office, aby importować i ładować biblioteki DLL Win32, za pomocą których można następnie wykonywać wywołania interfejsu API w celu dalszego zainfekowania systemu. Ta reguła próbuje zablokować pliki pakietu Office zawierające kod makra, który umożliwia importowanie bibliotek DLL Win32. Dotyczy to też programów Word, Excel, PowerPoint i OneNote.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067130)  
  
  **Domyślne**: Blokuj  
  
- **Poziom blokady chmury w usłudze Defender**  
  Poziom blokady chmury w usłudze Defender.
  
  **Domyślne**: nieskonfigurowane

- **Monitorowanie w czasie rzeczywistym**  
  Usługa Defender wymaga monitorowania w czasie rzeczywistym.
  
  **Domyślne**: Tak
 
- **Uruchamianie aplikacji komunikacyjnych pakietu Office w procesie podrzędnym**  

  **Domyślne**: Włącz

- **Tworzenie wykonywalnej zawartości lub typ uruchamiania aplikacji pakietu Office**  
  Ta reguła dotyczy typowego zachowania używanego przez podejrzane i złośliwe dodatki oraz skrypty (rozszerzenia), które powoduje tworzenie lub uruchamianie plików wykonywalnych. Jest to typowa technika złośliwego oprogramowania. Używanie rozszerzeń przez aplikacje pakietu Office jest zablokowane. Zazwyczaj te rozszerzenia używają hosta skryptów systemu Windows (pliki wsh), aby uruchamiać skrypty, które automatyzują określone zadania lub udostępniają dodatkowe funkcje utworzone przez użytkownika.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067108)  
  
  **Domyślne**: Blokuj

## <a name="windows-defender-firewall"></a>Zapora Windows Defender  
Aby uzyskać więcej informacji, zobacz [2.2.2 FW_PROFILE_TYPOE]( https://docs.microsoft.com/openspecs/windows_protocols/ms-fasp/7704e238-174d-4a5e-b809-5f3787dd8acc) w dokumentacji protokołów systemu Windows.  

- **Domena profilu zapory**  
  Określa profile, do których należy reguła: Domena, Prywatny, Publiczny. Ta wartość reprezentuje profil sieci, które zostały połączone z domeną.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2066796)  

  - **Połączenia przychodzące zablokowane**  
    **Domyślne**: Tak

  - **Połączenia wychodzące wymagane**  
    **Domyślne**: Tak 

  - **Powiadomienia przychodzące zablokowane**  
    **Domyślne**: Tak

  - **Zapora włączona**  
    **Domyślne**: Dozwolone

- **Publiczny profil zapory**  
  Określa profile, do których należy reguła: Domena, Prywatny, Publiczny. Ta wartość reprezentuje profil sieci publicznych. Te sieci są klasyfikowane jako publiczne przez administratorów na hoście serwera. Klasyfikacja odbywa się po pierwszym połączeniu hosta z siecią. Przeważnie takie sieci znajdują się na lotniskach, w kawiarniach i w innych miejscach, w których elementy równorzędne w sieci lub administrator sieci nie jest zaufany.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067143)  

  - **Połączenia przychodzące zablokowane**  
    **Domyślne**: Tak

  - **Połączenia wychodzące wymagane**  
    **Domyślne**: Tak 

  - **Powiadomienia przychodzące zablokowane**  
    **Domyślne**: Tak

  - **Zapora włączona**  
    **Domyślne**: Dozwolone

  - **Reguły zabezpieczeń połączeń niescalone z zasad grupy**  
    **Domyślne**: Tak

  - **Reguły zasad niescalone z zasad grupy**  
    **Domyślne**: Tak

- **Prywatny profil zapory**  
  Określa profile, do których należy reguła: Domena, Prywatny, Publiczny. Ta wartość reprezentuje profil sieci prywatnych.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067041)  

  - **Połączenia przychodzące zablokowane**  
    **Domyślne**: Tak

  - **Połączenia wychodzące wymagane**  
    **Domyślne**: Tak 

  - **Powiadomienia przychodzące zablokowane**  
    **Domyślne**: Tak

  - **Zapora włączona**  
    **Domyślne**: Dozwolone

## <a name="windows-hello-for-business"></a>Windows Hello for Business  
- **Wymagaj rozszerzonej ochrony przed fałszowaniem, jeśli jest dostępna**  
  Jeśli tak, urządzenia będą używać rozszerzonej ochrony przed fałszowaniem, jeśli jest dostępna. Jeśli nie, ochrona przed fałszowaniem zostanie zablokowana. Nieskonfigurowane, będą honorować konfiguracje wykonywane na kliencie.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067192)

  **Domyślne**: Tak

- **Skonfiguruj usługę Windows Hello dla firm**   
    Funkcja Windows Hello dla firm to alternatywna metoda logowania do systemu Windows przez zastępowanie haseł, kart inteligentnych i wirtualnych kart inteligentnych.  

  - W przypadku ustawienia *opcji tak*Włącz tę zasadę, a urządzenie zainicjuje funkcję Windows Hello dla firm.  
  - Jeśli ustawiono wartość *nie skonfigurowano*, linia bazowa nie ma wpływu na ustawienie zasad urządzenia. Oznacza to, że jeśli funkcja Windows Hello dla firm została wyłączona na urządzeniu, zostanie wyłączona. Jeśli jest włączona, pozostanie włączona. 

  Nie można wyłączyć usługi Windows Hello dla firm za jej podstawą. Można wyłączyć funkcję Windows Hello dla firm podczas konfigurowania [rejestracji systemu Windows](windows-hello.md)lub jako część profilu konfiguracji urządzenia na potrzeby [ochrony tożsamości](identity-protection-configure.md).  

  **Domyślne**: Tak

- **Wymagaj małych liter w numerze PIN**  
  W razie potrzeby numer PIN użytkownika musi zawierać co najmniej jedną małą literę.

  **Domyślne**: Dozwolone

- **Wymagaj znaków specjalnych w numerze PIN**  
  W razie potrzeby numer PIN użytkownika musi zawierać co najmniej jeden znak specjalny.

  **Domyślne**: Dozwolone

- **Minimalna długość numeru PIN**  
  Minimalna długość numeru PIN musi należeć do zakresu od 4 do 127.

  **Domyślne**: 6

- **Wymagaj wielkich liter w numerze PIN**  
  W razie potrzeby numer PIN użytkownika musi zawierać co najmniej jedną wielką literę.

  **Domyślne**: Dozwolone

## <a name="windows-ink-workspace"></a>Obszar roboczy funkcji Windows Ink  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — WindowsInkWorkspace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace) w dokumentacji systemu Windows.  

- **Obszar roboczy pisma odręcznego**  
  Określa, czy użytkownik może uzyskać dostęp do obszaru roboczego pisma odręcznego. 
  - *Wyłączone* — dostęp do obszaru roboczego pisma odręcznego jest wyłączony. Funkcja jest wyłączona.
  - *Włączone* — funkcja obszaru roboczego pisma odręcznego jest włączona, ale użytkownik nie może uzyskać dostępu do niej powyżej ekranu blokady.
  - *Nieskonfigurowane* — funkcja obszaru roboczego pisma odręcznego jest włączona, a użytkownik może używać jej powyżej ekranu blokady.  

  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067241)  

  **Domyślne**: włączone
 
## <a name="windows-powershell"></a>Windows PowerShell  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — WindowsPowerShell](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowspowershell) w dokumentacji systemu Windows.  

- **Rejestrowanie bloków skryptu w powłoce programu PowerShell**  
  To ustawienie zasad umożliwia rejestrowanie wszystkich danych wejściowych skryptu programu PowerShell w dzienniku zdarzeń Microsoft-Windows-PowerShell/Operational. Jeśli to ustawienie zasad zostanie włączone, program Windows PowerShell będzie rejestrować przetwarzanie poleceń, bloków skryptu, funkcji i skryptów wywoływanych interakcyjnie lub przy użyciu automatyzacji. Jeśli to ustawienie zasad zostanie wyłączone, rejestrowania danych wejściowych skryptu programu PowerShell zostanie wyłączone. Jeśli włączysz rejestrowanie wywołań bloków skryptu, program PowerShell dodatkowo będzie rejestrował zdarzenia w przypadku uruchomienia lub zatrzymania wywołania polecenia, bloku skryptu, funkcji lub skryptu. Włączenie rejestrowania wywołań generuje dużą liczbę dzienników zdarzeń. Uwaga: to ustawienie zasad istnieje w konfiguracji komputera i konfiguracji użytkownika w edytorze zasad grupy. Ustawienie zasad konfiguracji komputera ma pierwszeństwo przed ustawieniem zasad konfiguracji użytkownika.  
  [Dowiedz się więcej](https://go.microsoft.com/fwlink/?linkid=2067330)  

  **Domyślne**: włączone

## <a name="whats-changed-in-the-new-template"></a>Co zostało zmienione w nowym szablonie
*Linia bazowa zabezpieczeń MDM dla systemu 2019 może* mieć następujące zmiany w szablonie w *wersji* zapoznawczej.

### <a name="changes-to-the-baseline-settings"></a>Zmiany ustawień linii bazowej
Te ustawienia są:
- *Nowość* w tej najnowszej wersji linii bazowej.
- *Usunięte* z tej najnowszej wersji linii bazowej, ale były obecne w poprzedniej wersji.
- *Poprawiono* w inny sposób od tego, jak ustawienia pojawiły się w poprzedniej wersji. 

*[Nowy]* [**Powyżej blokady**](#above-lock):
- **Aktywuj aplikacje na zablokowanym ekranie**    

*[Nowe]* [**Zarządzanie aplikacjami**](#application-management): 
- **Blokuj kontrolę użytkownika nad instalacjami**  
- **Blokuj instalacje aplikacji MSI z podniesionymi uprawnieniami**  

*[Usunięto]* [**Funkcja BitLocker**](#bitlocker):  
- Zasada dysku wymiennego blokowania bitowego > **Metoda szyfrowania**
- **Zasady stałego dysku blokady bitowego** *(wszystkie ustawienia)*
- **Zasady dysku systemowego blokowania bitowego** *(wszystkie ustawienia)*

*[Nowe]* [**Łączność**](#connectivity):
- **Skonfiguruj bezpieczny dostęp do ścieżek UNC**

*[Nowe]* [**Device Guard**](#device-guard):
- **Zabezpieczenia oparte na wirtualizacji**


*[Nowy]* [**Ochrona DMA**](#dma-guard):
- **Wyliczanie urządzeń zewnętrznych niezgodnych z ochroną DMA jądra**  

*[Nowe]* [**Internet Explorer**](#internet-explorer):
- **Aktualizacje paska stanu za pomocą skryptu w strefie internetowej programu Explorer**
- **Przeciąganie i upuszczanie lub kopiowanie i wklejanie plików w strefie internetowej w programie Internet Explorer**  
- **Składniki uzależnione od platformy .NET Framework w strefie z ograniczeniami w programie Internet Explorer**  
- **Strefa Komputer lokalny w programie Internet Explorer nie uruchamia oprogramowania chroniącego przed złośliwym oprogramowaniem względem kontrolek ActiveX**
- **Obsługa szyfrowania w programie Internet Explorer**  

*[Poprawione]* [**Internet Explorer**](#internet-explorer):
- **Automatyczna Monituj o pobieranie plików w strefie internetowej programu Internet Explorer** > wartość domyślna jest teraz **wyłączona**. W wersji zapoznawczej ustawiono wartość włączone.

*[Nowe]* [**Pomoc zdalna**](#remote-assistance):  
- **Żądanie pomocy zdalnej** 
  - **Uprawnienie do pomocy zdalnej**
  - **Maksymalna wartość czasu biletu**  
  - **Maksymalny okres biletu**  
  - **Metoda zaproszenia E-Mail**


*[Nowe]* [**Windows Defender**](#windows-defender):
- **Uruchamianie programu Adobe Reader w procesie podrzędnym**  
- **Uruchamianie aplikacji komunikacyjnych pakietu Office w procesie podrzędnym** 

*[Nowe]* [**Zapora Windows Defender**](#windows-defender-firewall)
- **Domena profilu zapory**  
  - **Połączenia przychodzące zablokowane**  
  - **Połączenia wychodzące wymagane**  
  - **Powiadomienia przychodzące zablokowane**  
  - **Zapora włączona**  
- **Publiczny profil zapory**  
  - **Połączenia przychodzące zablokowane**  
  - **Połączenia wychodzące wymagane**  
  - **Powiadomienia przychodzące zablokowane**  
  - **Zapora włączona** 
  - **Reguły zabezpieczeń połączeń niescalone z zasad grupy**   
  - **Reguły zasad niescalone z zasad grupy**  
- **Prywatny profil zapory**  
  - **Połączenia przychodzące zablokowane**  
  - **Połączenia wychodzące wymagane**  
  - **Powiadomienia przychodzące zablokowane**  
  - **Zapora włączona**  

*[Nowe]* [**Windows Hello dla firm**](#windows-hello-for-business):  
- **Wymagaj rozszerzonej ochrony przed fałszowaniem, jeśli jest dostępna**  
- **Skonfiguruj usługę Windows Hello dla firm**  
- **Wymagaj małych liter w numerze PIN** 
- **Wymagaj znaków specjalnych w numerze PIN** 
- **Minimalna długość numeru PIN**  
- **Wymagaj wielkich liter w numerze PIN** 



<!-- The following settings were available in the Preview Baseline.   

   
## Above Lock  
For more information, see [Policy CSP - AboveLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock) in the Windows documentation.  

- **Block display of toast notifications**  
  This policy setting allows you to prevent app notifications from appearing on the lock screen. If you enable this policy setting, no app notifications are displayed on the lock screen. If you disable or don't configure this policy setting, users can choose which apps display notifications on the lock screen.
  
  **Default**: Yes  

## App Runtime    
For more information, see [Policy CSP - AppRuntime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-appruntime
) in the Windows documentation.  

- **Microsoft accounts optional for Windows Store apps**  
  This policy setting lets you control whether Microsoft accounts are optional for Windows Store apps that require an account to sign in. This policy only affects Windows Store apps that support it. If you enable this policy setting, Windows Store apps that typically require a Microsoft account to sign in will allow users to sign in with an enterprise account instead. If you disable or don't configure this policy setting, users must sign in with a Microsoft account.  
  
  **Default**: Enabled  

## Application Management   
For more information, see [Policy CSP - ApplicationManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement) in the Windows documentation.  

- **Block game DVR (desktop only)**  
  Configures whether recording and broadcasting of games is allowed.
  
  **Default**: Yes  

## Auto Play   
For more information, see [Policy CSP - Autoplay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-autoplay) in the Windows documentation.  

- **Auto play default auto run behavior**  
  This setting affects the default behavior for Autorun commands. Autorun commands are stored in autorun.inf files and can launch installation programs or other routines. When *Enabled*, Administrators can change the default autorun behavior on a device that runs Windows Vista or later. Behavior can be set to: a) completely disable autorun commands, or b) revert back to pre-Windows Vista behavior of automatically executing the autorun command. When set to *Disabled* or *Not Configured*, devices that run Windows Vista or later prompt the user as to whether an autorun command should run.
  
  **Default**: Do not execute  
  
- **Auto play mode**  
  This policy setting allows you to turn off the Autoplay feature. Autoplay begins reading from a drive as soon as you insert media in the drive. As a result, the setup file of programs and the music on audio media start immediately. Prior to Windows XP SP2, Autoplay is disabled by default on removable drives, such as the floppy disk drive (but not the CD-ROM drive), and on network drives. Starting with Windows XP SP2, Autoplay is enabled for removable drives as well, including Zip drives and some USB mass storage devices. If you enable this policy setting, Autoplay is disabled on CD-ROM and removable media drives, or disabled on all drives. This policy setting disables Autoplay on additional types of drives. You can't use this setting to enable Autoplay on drives on which it's disabled by default. If you disable or don't configure this policy setting, AutoPlay is enabled. Note: This policy setting appears in both the Computer Configuration and User Configuration folders. If the policy settings conflict, the policy setting in Computer Configuration takes precedence over the policy setting in User Configuration.
  
  **Default**: Disabled

- **Block auto play for non-volume devices**  
  This policy setting disallows AutoPlay for MTP devices like cameras or phones. If you enable this policy setting, AutoPlay isn't allowed for MTP devices like cameras or phones. If you disable or don't configure this policy setting, AutoPlay is enabled for non-volume devices.
  
  **Default**: Enabled  

## Bitlocker    
For more information, see [Policy CSP - Bitlocker](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bitlocker
) in the Windows documentation.  

- **Bit locker removable drive policy**  
  This policy setting is used to control the encryption method and cipher strength. The values of this policy determine the strength of the cipher that BitLocker uses for encryption. Enterprises may want to control the encryption level for increased security (AES-256 is stronger than AES-128). If you enable this setting, you'll be able to configure an encryption algorithm and key cipher strength for fixed data drives, operating system drives, and removable data drives individually. For fixed and operating system drives, we recommend that you use the XTS-AES algorithm. For removable drives, you should use AES-CBC 128-bit or AES-CBC 256-bit if the drive is used in other devices that aren't running Windows 10, version 1511 or later. Changing the encryption method has no effect if the drive is already encrypted or if encryption is in progress. In these cases, this policy setting is ignored.

  For Bit locker removable drive policy, configure the following settings:

    - **Require encryption for write access**  
      **Default**: Yes  
  
    - **Encryption method**  
      **Default**: AES 256bit CBC  

- **Bit locker fixed drive policy**  
  This policy setting is used to control the encryption method and cipher strength. The values of this policy determine the strength of the cipher that BitLocker uses for encryption. Enterprises may want to control the encryption level for increased security (AES-256 is stronger than AES-128). If you enable this setting, you can configure an encryption algorithm and key cipher strength for fixed data drives, operating system drives, and removable data drives individually. For fixed and operating system drives, we recommend that you use the XTS-AES algorithm. For removable drives, you should use AES-CBC 128-bit or AES-CBC 256-bit if the drive is used in other devices that aren't running Windows 10, version 1511 or later. Changing the encryption method has no effect if the drive is already encrypted or if encryption is in progress. In these cases, this policy setting is ignored.  
 
   For Bit locker fixed drive policy, configure the following settings: 
   - **Encryption method**
     **Default**: AES 256bit XTS  

- **Bit locker system drive policy**  
  This policy setting is used to control the encryption method and cipher strength. The values of this policy determine the strength of the cipher that BitLocker uses for encryption. Enterprises may want to control the encryption level for increased security (AES-256 is stronger than AES-128). If you enable this setting, you can configure an encryption algorithm and key cipher strength for fixed data drives, operating system drives, and removable data drives individually. For fixed and operating system drives, we recommend that you use the XTS-AES algorithm. For removable drives, you should use AES-CBC 128-bit or AES-CBC 256-bit if the drive is used in other devices that aren't running Windows 10, version 1511 or later. Changing the encryption method has no effect if the drive is already encrypted or if encryption is in progress. In these cases, this policy setting is ignored.  

   For Bit locker system drive policy, configure the following settings:
  - **Encryption method**  
    **Default**: AES 256bit XTS  

## Browser  
For more information, see [Policy CSP - Browser](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser) in the Windows documentation.  

- **Require SmartScreen for Microsoft Edge**  
  Microsoft Edge uses Windows Defender SmartScreen (turned on) to protect users from potential phishing scams and malicious software by default. Also, by default, users can't disable (turn off) Windows Defender SmartScreen. Enabling this policy turns off Windows Defender SmartScreen and prevent users from turning it on. Don’t configure this policy to let users choose to turn Windows defender SmartScreen on or off.  
  
  **Default**: Yes  
  
- **Block malicious site access**  
  By default, Microsoft Edge allows users to bypass (ignore) the Windows Defender SmartScreen warnings about potentially malicious sites, allowing them to continue to the site. With this policy though, you can configure Microsoft Edge to prevent users from bypassing the warnings, blocking them from continuing to the site.
  
  **Default**: Yes  
  
- **Block unverified file download**
  By default, Microsoft Edge allows users to bypass (ignore) the Windows Defender SmartScreen warnings about potentially malicious files, allowing them to continue downloading the unverified file(s). Enabling this policy prevents users from bypassing the warnings, blocking them from downloading of the unverified file(s).
  
  **Default**: Yes  
  
- **Block Password Manager**  
  By default, Microsoft Edge uses Password Manager automatically, allowing users to manager passwords locally. Disabling this policy restricts Microsoft Edge from using Password Manager. Don’t configure this policy if you want to let users choose to save and manage passwords locally using Password Manager.
  
  **Default**: Yes  
  
- **Prevent certificate error overrides**  
  This policy setting prevents the user from ignoring Secure Sockets Layer/Transport Layer Security (SSL/TLS) certificate errors that interrupt browsing (such as "expired", "revoked", or "name mismatch" errors) in Internet Explorer. If you enable this policy setting, the user can't continue browsing. If you disable or don't configure this policy setting, the user can choose to ignore certificate errors and continue browsing.
  
  **Default**: Yes  

## Connectivity  
For more information, see [Policy CSP - Connectivity](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity) in the Windows documentation.  

- **Block Internet download for web publishing and online ordering wizards**  
  This policy setting specifies whether Windows should download a list of providers for the web publishing and online ordering wizards. These wizards allow users to select from a list of companies that provide services such as online storage and photographic printing. By default, Windows displays providers downloaded from a Windows website in addition to providers specified in the registry. If you enable this policy setting, Windows doesn't download providers, and only the service providers that are cached in the local registry display. If you disable or don't configure this policy setting, a list of providers downloads when the user uses the web publishing or online ordering wizards. For more information that includes details on specifying service providers in the registry, see the documentation for the web publishing and online ordering wizards.  
  
  **Default**: Enabled  

- **Block downloading of print drivers over HTTP**  
  This policy setting specifies whether to allow this client to download print driver packages over HTTP. To set up HTTP printing, non-inbox drivers need to be downloaded over HTTP. Note: This policy setting doesn't prevent the client from printing to printers on the Intranet or the Internet over HTTP. It only prohibits downloading drivers that aren't already installed locally. If you enable this policy setting, print drivers can't be downloaded over HTTP. If you disable or don't configure this policy setting, users can download print drivers over HTTP.
  
  **Default**: Enabled  

## Credentials Delegation  
For more information, see [Policy CSP - CredentialsDelegation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsdelegation
) in the Windows documentation.  

- **Remote host delegation of non-exportable credentials**  
  Remote host allows delegation of non-exportable credentials. When using credential delegation, devices provide an exportable version of credentials to the remote host, which exposes users to the risk of credential theft from attackers on the remote host. If you enable this policy setting, the host supports Restricted Admin or Remote Credential Guard mode. If you disable or don't configure this policy setting, Restricted Administration and Remote Credential Guard mode aren't supported. User will always need to pass their credentials to the host.  

  
  **Default**: Enabled  

## Credentials UI  
For more information, see [Policy CSP - CredentialsUI](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsui) in the Windows documentation.  

- **Enumerate administrators** 
  This policy setting controls whether administrator accounts display when a user attempts to elevate a running application. By default, administrator accounts aren't displayed when the user attempts to elevate a running application. If you enable this policy setting, all local administrator accounts on the PC display so the user can choose one and enter the correct password. If you disable this policy setting, users will always be required to type a user name and password to elevate.  

  
  **Default**: Disabled  

## Data Protection  
For more information, see [Policy CSP - DataProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection
) in the Windows documentation.  

- **Block direct memory access**  
  This policy setting allows you to block direct memory access (DMA) for all hot pluggable PCI downstream ports until a user logs into Windows. Once a user logs in, Windows will enumerate the PCI devices connected to the host plug PCI ports. Every time the user locks the machine, DMA is blocked on hot plug PCI ports with no children devices until the user logs in again. Devices that were already enumerated when the machine was unlocked will continue to function until unplugged. This policy setting is only enforced when BitLocker or device encryption is enabled.
  
  
  **Default**: Yes  

## Device Guard  
For more information, see [Policy CSP - DeviceGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceguard
) in the Windows documentation.  

- **Credential Guard**  
  This setting lets users turn on Credential Guard with virtualization-based security to help protect credentials at next reboot.
   
  **Default**: Enable with UEFI lock 

- **Enable virtualization based security**   
  Turns on virtualization-based security (VBS) at the next reboot. Virtualization-based security uses the Windows Hypervisor to provide support for security services.
  
  **Default**: Yes  


- **Launch system guard**    
  **Default**: Enabled  

## Device Installation  
For more information, see [Policy CSP - DeviceInstallation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation) in the Windows documentation.  

- **Hardware device installation by device identifiers**  
  This policy setting allows you to specify a list of Plug and Play hardware IDs and compatible IDs for devices that Windows is prevented from installing. This policy setting takes precedence over any other policy setting that allows Windows to install a device. If you enable this policy setting, Windows is prevented from installing a device whose hardware ID or compatible ID appears in the list you create. If you enable this policy setting on a remote desktop server, the policy setting affects redirection of the specified devices from a remote desktop client to the remote desktop server. If you disable or don't configure this policy setting, devices can install and update as allowed or prevented by other policy settings.
  
  **Default**: Block hardware device installation  

    When *Block hardware device installation* is selected, the following settings are available.
  
    - **Remove matching hardware devices**   
    This setting is available only when *Hardware device installation by device identifiers* is set to *Block hardware device installation*.
      
      **Default**: Yes
  
    - **Hardware device identifiers that are blocked**  
       This setting is available only when *Hardware device installation by device identifiers* is set to *Block hardware device installation*.
      
      **Default**: Yes  
  
- **Hardware device installation by setup classes**  
  This policy setting allows you to specify a list of device setup class globally unique identifiers (GUIDs) for device drivers that Windows is prevented from installing. This policy setting takes precedence over any other policy setting that allows Windows to install a device. If you enable this policy setting, Windows is prevented from installing or updating device drivers whose device setup class GUIDs appear in the list you create. If you enable this policy setting on a remote desktop server, the policy setting affects redirection of the specified devices from a remote desktop client to the remote desktop server. If you disable or don't configure this policy setting, Windows can install and update devices as allowed or prevented by other policy settings.
  
  **Default**: Block hardware device installation  

    When *Block hardware device installation* is selected, the following settings are available.
    - **Remove matching hardware devices**    
    This setting is available only when *Hardware device installation by setup classes* is set to *Block hardware device installation*.  

      **Default**: *No default configuration*  
  
    - **Hardware device identifiers that are blocked**  
      This setting is available only when *Hardware device installation by setup classes* is set to *Block hardware device installation*.
      
      **Default**: *No default configuration*  

## Device Lock  
For more information, see [Policy CSP - DeviceLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock) in the Windows documentation.  

- **Prevent use of camera**  
  Disables the lock screen camera toggle switch in PC Settings and prevents a camera from being invoked on the lock screen. By default, users can enable invocation of an available camera on the lock screen. If you enable this setting, users will no longer be able to enable or disable lock screen camera access in PC Settings, and the camera can't be invoked on the lock screen. 
  
  **Default**: Enabled  

- **Require password**  
  Specifies whether device lock is enabled.
  
  **Default**: Yes  
  
    When *Require password* is set to *Yes*, the following settings are available.

    - **Password minimum character set count**  
      The number of complex element types (uppercase and lowercase letters, numbers, and punctuation) required for a strong PIN or password. PIN enforces the following behavior for desktop and mobile devices: 1 - Digits only 2 - Digits and lowercase letters are required 3 - Digits, lowercase letters, and uppercase letters are required. Not supported in desktop Microsoft accounts and domain accounts. 4 - Digits, lowercase letters, uppercase letters, and special characters are required. Not supported in desktop. The default value is 1. 
      
      **Default**: 3  
  
    - **Number of sign-in failures before wiping device**  
      The number of authentication failures allowed before the device is wiped. A value of 0 disables device wipe functionality.
        
      **Default**: 10  
  
    - **Password expiration (days)**  
      The Maximum password age policy setting determines how long (in days) that a password can be used before the system requires the user to change it. You can set passwords to expire after a number of days between 1 and 999, or you can specify that passwords never expire by setting the number of days to 0. If Maximum password age is between 1 and 999 days, the minimum password age must be less than the maximum password age. If Maximum password age is set to 0, Minimum password age can be any value between 0 and 998 days.
      
      **Default**: 60  
  
    - **Required password type**  
      Determines the type of PIN or password required.
      
      **Default**: Alphanumeric  
  
    - **Minimum password length**  
      The Minimum password length policy setting determines the least number of characters that can make up a password for a user account. You can set a value of between 1 and 14 characters, or you can establish that no password is required by setting the number of characters to 0.
      
      **Default**: 8  
  
    - **Block simple passwords**  
      Specifies whether PINs or passwords such as "1111" or "1234" are allowed. For the desktop, it also controls the use of picture passwords.
      
      **Default**: Yes  
        *A setting of Yes prevents use of simple passwords.* 

  - **Prevent reuse of previous passwords**  
    Specifies how many passwords can be stored in the history that can’t be used. The value includes the user's current password. For example, with a setting of *1* the user can't reuse their current password when choosing a new password. A setting of *5* means that a user can't set their new password to their current password or any of their previous four passwords.
    
    **Default**: 24  

- **Prevent slide show**  
  Disables the lock screen slide show settings in PC Settings and prevents a slide show from playing on the lock screen. By default, users can enable a slide show that will run after they lock the machine. If you enable this setting, users can't modify slide show settings in PC Settings, and no slide show can start.
  
    **Default**: Enabled  
    *A setting of Enabled prevents slide shows from running.* 

- **Password minimum age in days**  
  The Minimum password age policy setting determines the period of time (in days) that a password must be used before the user can change it. You can set a value between 1 and 998 days, or you can allow password changes immediately by setting the number of days to 0. The minimum password age must be less than the Maximum password age, unless the maximum password age is set to 0, indicating that passwords will never expire. If the maximum password age is set to 0, the minimum password age can be set to any value between 0 and 998.
  
    **Default**: 1  

## Event Log Service  
For more information, see [Policy CSP - EventLogService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-eventlogservice) in the Windows documentation.  

- **Security log maximum file size in KB**  
  This policy setting specifies the maximum size of the log file in kilobytes. If you enable this policy setting, you can configure the maximum log file size to be between 1 megabyte (1024 kilobytes) and 2 terabytes (2147483647 kilobytes) in kilobyte increments. If you disable or don't configure this policy setting, the maximum size of the log file is set to the locally configured value. This value can be changed by the local administrator using the Log Properties dialog and it defaults to 20 megabytes.
  
   **Default**: 196608  

- **System log maximum file size in KB**  
  This policy setting specifies the maximum size of the log file in kilobytes. If you enable this policy setting, you can configure the maximum log file size to be between 1 megabyte (1024 kilobytes) and 2 terabytes (2147483647 kilobytes) in kilobyte increments. If you disable or don't configure this policy setting, the maximum size of the log file is set to the locally configured value. This value can be changed by the local administrator using the Log Properties dialog and it defaults to 20 megabytes.
  
  **Default**: 32768  

- **Application log maximum file size in KB**  
  This policy setting specifies the maximum size of the log file in kilobytes. If you enable this policy setting, you can configure the maximum log file size to be between 1 megabyte (1024 kilobytes) and 2 terabytes (2147483647 kilobytes) in kilobyte increments. If you disable or don't configure this policy setting, the maximum size of the log file is set to the locally configured value. This value can be changed by the local administrator using the Log Properties dialog and it defaults to 20 megabytes.
  
  **Default**: 32768  

## Experience  
For more information, see [Policy CSP - Experience](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience) in the Windows documentation.  

- **Block Windows Spotlight**  
  Allows IT admins to turn off all Windows Spotlight Features - Window spotlight on lock screen, Windows Tips, Microsoft consumer features, and other related features.
  
  **Default**: Yes  

  When *Block Windows Spotlight* is set to *Yes*, the following settings are available.
  
  - **Block third-party suggestions in Windows Spotlight**  
    Specifies whether to allow app and content suggestions from third-party software publishers in Windows spotlight features like lock screen spotlight, suggested apps in the Start menu, and Windows tips. Users may still see suggestions for Microsoft features, apps, and services.
      
    **Default**: Yes  
   - **Block consumer specific features**  
      Allows IT admins to turn on experiences that are typically for consumers only, such as Start suggestions, Membership notifications, Post-OOBE app install, and redirect tiles.
      
     **Default**: Yes  


## Exploit Guard  
For more information, see [Policy CSP - ExploitGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-exploitguard) in the Windows documentation.  

- **Exploit protection XML**  
  Enables the IT admin to push out a configuration that represents the desired system and application mitigation options to all the devices in the organization. The configuration is represented by an XML. Exploit protection helps protect devices from malware that use exploits to spread and infect. You use the Windows Security app or PowerShell to create a set of mitigations (known as a configuration). You can then export this configuration as an XML file and share it with multiple machines on your network so they all have the same set of mitigation settings. You can also convert and import an existing EMET configuration XML file into an exploit protection configuration XML.
  
  **Default**: *Sample xml is provided* 
 
## File Explorer  
For more information, see [Policy CSP - FileExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-fileexplorer) in the Windows documentation.  

- **Block data execution prevention**  
  Disabling data execution prevention can allow certain legacy plug-in applications to function without terminating Explorer.
  
  **Default**: Disabled  
   
- **Block heap termination on corruption**  
  Disabling heap termination on corruption can allow certain legacy plug-in applications to function without terminating Explorer immediately, although Explorer may still terminate unexpectedly later.
  
  **Default**: Disabled  
    

## Internet Explorer  
For more information, see [Policy CSP - InternetExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-internetexplorer) in the Windows documentation.  


- **Internet Explorer internet zone access to data sources**  
  This policy setting allows you to manage whether Internet Explorer can access data from another security zone using the Microsoft XML Parser (MSXML) or ActiveX Data Objects (ADO). If you enable this policy setting, users can load a page in the zone that uses MSXML or ADO to access data from another site in the zone. If you select Prompt in the drop-down box, users are queried to choose whether to allow a page to load in the zone that uses MSXML or ADO to access data from another site in the zone. If you disable this policy setting, users can't load a page in the zone that uses MSXML or ADO to access data from another site in the zone. If you don't configure this policy setting, users can't load a page in the zone that uses MSXML or ADO to access data from another site in the zone.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone drag content from different domains within windows**  
  This policy setting allows you to set options for dragging content from one domain to a different domain when the source and destination are in the same window. If you enable this policy setting and click Enable, users can drag content from one domain to a different domain when the source and destination are in the same window. Users can't change this setting. If you enable this policy setting and click Disable, users can't drag content from one domain to a different domain when the source and destination are in the same window. Users can't change this setting in the Internet Options dialog. In Internet Explorer 10, if you disable this policy setting or don't configure it, users can't drag content from one domain to a different domain when the source and destination are in the same window. Users can change this setting in the Internet Options dialog. In Internet Explorer 9 and earlier versions, if you disable this policy setting or don't configure it, users can drag content from one domain to a different domain when the source and destination are in the same window. Users can't change this setting in the Internet Options dialog.
  
  **Default**: Disabled
  
- **Internet Explorer certificate address mismatch warning**  
  This policy setting allows you to turn on the certificate address mismatch security warning. When this policy setting is turned on, the user is warned when visiting Secure HTTP (HTTPS) websites that present certificates issued for a different website address. This warning helps prevent spoofing attacks. If you enable this policy setting, the certificate address mismatch warning always appears. If you disable or don't configure this policy setting, the user can choose whether the certificate address mismatch warning appears (by using the Advanced page in the Internet Control panel).
  
  **Default**: Enabled 
  
- **Internet Explorer restricted zone less privileged sites**  
  This policy setting allows you to manage whether Web sites from less privileged zones, such as Internet sites, can navigate into this zone. If you enable this policy setting, Web sites from less privileged zones can open new windows in, or navigate into, this zone. The security zone will run without the added layer of security that is provided by the Protection from Zone Elevation security feature. If you select Prompt in the drop-down box, a warning is issued to the user that potentially risky navigation is about to occur. If you disable this policy setting, possibly harmful navigation is prevented. The Internet Explorer security feature is on in this zone as set by Protection from Zone Elevation feature control. If you don't configure this policy setting, the possibly harmful navigations are prevented. The Internet Explorer security feature is on in this zone as set by Protection from Zone Elevation feature control.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone automatic prompt for file downloads**  
  This policy setting determines whether users are prompted for non user-initiated file downloads. Regardless of this setting, users will receive file download dialogs for user-initiated downloads. If you enable this setting, users will receive a file download dialog for automatic download attempts. If you disable or don't configure this setting, file downloads that aren't user-initiated are blocked, and users will see the Notification bar instead of the file download dialog. Users can then click the Notification bar to allow the file download prompt.
  
  **Default**: Disabled
  
- **Internet Explorer internet zone .NET Framework reliant components**  
  This policy setting allows you to manage whether .NET Framework components that aren't signed with Authenticode can be executed from Internet Explorer. These components include managed controls referenced from an object tag and managed executables referenced from a link. If you enable this policy setting, Internet Explorer will execute unsigned managed components. If you select Prompt in the drop-down box, Internet Explorer will prompt the user to determine whether to execute unsigned managed components. If you disable this policy setting, Internet Explorer won't execute unsigned managed components. If you don't configure this policy setting, Internet Explorer will execute unsigned managed components.
  
  **Default**: Disable 
  
- **Internet Explorer internet zone allow only approved domains to use tdc ActiveX controls**  
  This policy setting controls if the user can run the TDC ActiveX control on websites. If you enable this policy setting, the TDC ActiveX control won't run from websites in this zone. If you disable this policy setting, the TDC Active X control will run from all sites in this zone.
  
  **Default**: Enabled 
  
- **Internet Explorer restricted zone script initiated windows**  
  This policy setting allows you to manage restrictions on script-initiated pop-up windows and windows that include the title and status bars. If you enable this policy setting, Windows Restrictions security won't apply in this zone. The security zone runs without the added layer of security provided by this feature. If you disable this policy setting, the possible harmful actions contained in script-initiated pop-up windows and windows that include the title and status bars can't run. This Internet Explorer security feature is on in this zone as dictated by the Scripted Windows Security Restrictions feature control setting for the process. If you don't configure this policy setting, the possible harmful actions contained in script-initiated pop-up windows and windows that include the title and status bars can't run. This Internet Explorer security feature is on in this zone as dictated by the Scripted Windows Security Restrictions feature control setting for the process.
  
  **Default**: Disabled 
  
- **Internet Explorer internet zone include local path when uploading files to server**  
  This policy setting controls if local path information gets sent when the user is uploading a file via an HTML form. If the local path information is sent, some information may be unintentionally revealed to the server. For instance, files sent from the user's desktop may contain the user name as a part of the path. If you enable this policy setting, path information is sent when the user is uploading a file via an HTML form. If you disable this policy setting, path information is removed when the user is uploading a file via an HTML form. If you don't configure this policy setting, the user can choose whether path information gets sent when they upload a file via an HTML form. By default, path information is sent.
  
  **Default**: Disabled 
  
- **Internet Explorer disable processes in enhanced protected mode**  
  This policy setting determines whether Internet Explorer 11 uses 64-bit processes (for greater security) or 32-bit processes (for greater compatibility) when running in Enhanced Protected Mode on 64-bit versions of Windows. Important: Some ActiveX controls and toolbars may not be available when 64-bit processes are used. If you enable this policy setting, Internet Explorer 11 will use 64-bit tab processes when running in Enhanced Protected Mode on 64-bit versions of Windows. If you disable this policy setting, Internet Explorer 11 will use 32-bit tab processes when running in Enhanced Protected Mode on 64-bit versions of Windows. If you don't configure this policy setting, users can turn this feature on or off using Internet Explorer settings. This feature is turned off by default.
  
  **Default**: Enabled 
  
- **Internet Explorer ignore certificate errors**  
  This policy setting prevents the user from ignoring Secure Sockets Layer/Transport Layer Security (SSL/TLS) certificate errors that interrupt browsing (such as "expired", "revoked", or "name mismatch" errors) in Internet Explorer. If you enable this policy setting, the user can't continue browsing. If you disable or don't configure this policy setting, the user can choose to ignore certificate errors and continue browsing.
  
  **Default**: Disabled 
  
- **Internet Explorer internet zone loading of XAML files**  
  This policy setting allows you to manage the loading of Extensible Application Markup Language (XAML) files. XAML is an XML-based declarative markup language commonly used for creating rich user interfaces and graphics that take advantage of the Windows Presentation Foundation. If you enable this policy setting and set the drop-down box to Enable, XAML files are automatically loaded inside Internet Explorer. The user can't change this behavior. If you set the drop-down box to Prompt, the user is prompted for loading XAML files. If you disable this policy setting, XAML files aren't loaded inside Internet Explorer. The user can't change this behavior. If you don't configure this policy setting, the user can decide whether to load XAML files inside Internet Explorer.
  
  **Default**: Disable 
  
- **Internet Explorer internet zone automatic prompt for file downloads**  
  This policy setting determines whether users are prompted for non user-initiated file downloads. Regardless of this setting, users will receive file download dialogs for user-initiated downloads. If you enable this setting, users will receive a file download dialog for automatic download attempts. If you disable or don't configure this setting, file downloads that aren't user-initiated are blocked, and users will see the Notification bar instead of the file download dialog. Users can then click the Notification bar to allow the file download prompt.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone security warning for potentially unsafe files**  
  This policy setting controls if the "Open File - Security Warning" message appears when the user tries to open executable files or other potentially unsafe files (from an intranet file share by using File Explorer, for example). If you enable this policy setting and set the drop-down box to Enable, these files open without a security warning. If you set the drop-down box to Prompt, a security warning appears before the files open. If you disable this policy setting, these files don't open. If you don't configure this policy setting, the user can configure how the computer handles these files. By default, these files are blocked in the Restricted zone, enabled in the Intranet and Local Computer zones, and set to prompt in the Internet and Trusted zones.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone cross site scripting filter**  
  This policy controls if the Cross-Site Scripting (XSS) Filter will detect and prevent cross-site script injections into websites in this zone. If you enable this policy setting, the XSS Filter is turned on for sites in this zone, and the XSS Filter attempts to block cross-site script injections. If you disable this policy setting, the XSS Filter is turned off for sites in this zone, and Internet Explorer permits cross-site script injections.
  
  **Default**: Enabled 
  
- **Internet Explorer fallback to SSL3**  
  This policy setting allows you to block an insecure fallback to SSL 3.0. When this policy is enabled, Internet Explorer will attempt to connect to sites using SSL 3.0 or below when TLS 1.0 or greater fails. We recommend that you don't allow insecure fallback in order to prevent a man-in-the-middle attack. This policy doesn't affect which security protocols are enabled. If you disable this policy, system defaults are used.
  
  **Default**: No sites 
  
- **Internet Explorer locked down internet zone smart screen**  
  This policy setting controls whether SmartScreen Filter scans pages in this zone for malicious content. If you enable this policy setting, SmartScreen Filter scans pages in this zone for malicious content. If you disable this policy setting, SmartScreen Filter doesn't scan pages in this zone for malicious content. If you don't configure this policy setting, the user can choose whether SmartScreen Filter scans pages in this zone for malicious content. Note: In Internet Explorer 7, this policy setting controls whether Phishing Filter scans pages in this zone for malicious content.
  
  **Default**: Enabled 
  
- **Internet Explorer restricted zone launch applications and files in an iFrame**  
  This policy setting allows you to manage whether applications may be run and files may be downloaded from an IFRAME reference in the HTML of the pages in this zone. If you enable this policy setting, users can run applications and download files from IFRAMEs on the pages in this zone without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to run applications and download files from IFRAMEs on the pages in this zone. If you disable this policy setting, users are prevented from running applications and downloading files from IFRAMEs on the pages in this zone. If you don't configure this policy setting, users are prevented from running applications and downloading files from IFRAMEs on the pages in this zone.
  
  **Default**: Disable 
  
- **Internet Explorer bypass smart screen warnings about uncommon files**  
  This policy setting determines whether the user can bypass warnings from SmartScreen Filter. SmartScreen Filter warns the user about executable files that Internet Explorer users don't commonly download from the Internet. If you enable this policy setting, SmartScreen Filter warnings block the user. If you disable or don't configure this policy setting, the user can bypass SmartScreen Filter warnings.
  
  **Default**: Disabled  
  
- **Internet Explorer internet zone popup blocker**  
  This policy setting allows you to manage whether unwanted pop-up windows appear. Pop-up windows that are opened when the end user clicks a link aren't blocked. If you enable this policy setting, most unwanted pop-up windows are prevented from appearing. If you disable this policy setting, pop-up windows aren't prevented from appearing. If you don't configure this policy setting, most unwanted pop-up windows are prevented from appearing.
  
  **Default**: Enable  
  
- **Internet Explorer processes consistent MIME handling**  
  Internet Explorer contains dynamic binary behaviors: components that encapsulate specific functionality for the HTML elements to which they're attached. This policy setting controls whether the Binary Behavior Security Restriction setting is prevented or allowed. If you enable this policy setting, binary behaviors are prevented for the File Explorer and Internet Explorer processes. If you disable this policy setting, binary behaviors are allowed for the File Explorer and Internet Explorer processes. If you don't configure this policy setting, binary behaviors are prevented for the File Explorer and Internet Explorer processes.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, Java applets are disabled.
  
  **Default**: Disable java  
    
  
- **Internet Explorer Active X controls in protected mode**  
  This policy setting prevents ActiveX controls from running in Protected Mode when Enhanced Protected Mode is enabled. When a user has an ActiveX control installed that isn't compatible with Enhanced Protected Mode and a website attempts to load the control, Internet Explorer notifies the user and gives the option to run the website in regular Protected Mode. This policy setting disables this notification and forces all websites to run in Enhanced Protected Mode. Enhanced Protected Mode provides additional protection against malicious websites by using 64-bit processes on 64-bit versions of Windows. For computers running at least Windows 8, Enhanced Protected Mode also limits the locations Internet Explorer can read from in the registry and the file system. When Enhanced Protected Mode is enabled, and a user comes across a website that attempts to load an ActiveX control that isn't compatible with Enhanced Protected Mode, Internet Explorer notifies the user and gives the option to disable Enhanced Protected Mode for that particular website. If you enable this policy setting, Internet Explorer won't give the user the option to disable Enhanced Protected Mode. All Protected Mode websites will run in Enhanced Protected Mode. If you disable or don't configure this policy setting, Internet Explorer notifies users and provides an option to run websites with incompatible ActiveX controls in regular Protected Mode.  
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone loading of XAML files**  
  This policy setting allows you to manage the loading of Extensible Application Markup Language (XAML) files. XAML is an XML-based declarative markup language commonly used for creating rich user interfaces and graphics that take advantage of the Windows Presentation Foundation. If you enable this policy setting and set the drop-down box to Enable, XAML files are automatically loaded inside Internet Explorer. The user can't change this behavior. If you set the drop-down box to Prompt, the user is prompted for loading XAML files. If you disable this policy setting, XAML files aren't loaded inside Internet Explorer. The user can't change this behavior. If you don't configure this policy setting, the user can decide whether to load XAML files inside Internet Explorer.
  
  **Default**: Disable  
  
- **Internet Explorer processes scripted window security restrictions**  
  Internet Explorer allows scripts to programmatically open, resize, and reposition windows of various types. The Window Restrictions security feature restricts popup windows and prohibits scripts from displaying windows in which the title and status bars aren't visible to the user or obfuscate other Windows' title and status bars. If you enable this policy setting, scripted windows are restricted for all processes. If you disable or don't configure this policy setting, scripted windows aren't restricted.
  
  **Default**: Enabled   
  
- **Internet Explorer restricted zone run Active X controls and plugins**  
  This policy setting allows you to manage whether ActiveX controls and plug-ins can run on pages from the specified zone. If you enable this policy setting, controls and plug-ins can run without user intervention. If you selected Prompt in the drop-down box, users are asked to choose whether to allow the controls or plug-in to run. If you disable this policy setting, controls and plug-ins are prevented from running. If you don't configure this policy setting, controls and plug-ins are prevented from running.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone script Active X controls marked safe for scripting**  
  This policy setting allows you to manage whether an ActiveX control marked safe for scripting can interact with a script. If you enable this policy setting, script interaction can occur automatically without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to allow script interaction. If you disable this policy setting, script interaction is prevented from occurring. If you don't configure this policy setting, script interaction is prevented from occurring.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone logon options**  
  This policy setting allows you to manage settings for sign in options. If you enable this policy setting, you can choose from the following sign in options. 
  - *Anonymous*  - Use anonymous sign in to disable HTTP authentication and use the guest account only for the Common Internet File System (CIFS) protocol. 
  - *Prompt* - Use prompt for user name and password to query users for user IDs and passwords. After a user is queried, these values can be used silently for the rest of the session. 
  - *Automatic sign in only in Intranet zone* - Use this option to query users for user IDs and passwords in other zones. After a user is queried, these values can be used silently for the rest of the session. 
  - *Automatic sign in with current user name and password*- Use this option to attempt sign in using Windows NT Challenge Response (also known as NTLM authentication). If the server supports Windows NT Challenge Response, the sign in uses the user's network user name and password for sign in. If the server doesn't support Windows NT Challenge Response, the user is queried to provide the user name and password. 

  If you disable this policy setting, sign-in is set to *Automatic sign in only in Intranet zone*. If you don't configure this policy setting, sign-in is set to *Prompt* for username and password.
  
  **Default**: Anonymous  
  
- **Internet Explorer trusted zone initialize and script Active X controls not marked as safe**  
  This policy setting allows you to manage ActiveX controls not marked as safe. If you enable this policy setting, ActiveX controls run, loaded with parameters, and scripted without setting object safety for untrusted data or scripts. This setting isn't recommended, except for secure and administered zones. This setting causes both unsafe and safe controls to be initialized and scripted, ignoring the Script ActiveX controls marked safe for scripting option. If you enable this policy setting and select Prompt in the drop-down box, users are queried whether to allow the control to load with parameters or scripted. If you disable this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted. If you don't configure this policy setting, users are queried whether to allow the control to load with parameters or scripted.
  
  **Default**: Disable  
  
- **Internet Explorer check server certificate revocation**  
  This policy setting allows you to manage whether Internet Explorer will check revocation status of servers' certificates. Certificates are revoked when they are compromised or no longer valid, and this option protects users from submitting confidential data to a site that may be fraudulent or not secure. If you enable this policy setting, Internet Explorer will check to see if server certificates have been revoked. If you disable this policy setting, Internet Explorer won't check server certificates to see if they have been revoked. If you don't configure this policy setting, Internet Explorer won't check server certificates to see if they have been revoked.
  
  **Default**: Enabled 
  
- **Internet Explorer internet zone less privileged sites**  
  This policy setting allows you to manage whether Web sites from less privileged zones, such as Restricted Sites, can navigate into this zone. If you enable this policy setting, Web sites from less privileged zones can open new windows in, or navigate into, this zone. The security zone will run without the added layer of security that is provided by the Protection from Zone Elevation security feature. If you select Prompt in the drop-down box, a warning is issued to the user that potentially risky navigation is about to occur. If you disable this policy setting, the possibly harmful navigations are prevented. The Internet Explorer security feature is on in this zone as set by Protection from Zone Elevation feature control. If you don't configure this policy setting, Web sites from less privileged zones can open new windows in, or navigate into, this zone.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone file downloads**  
  This policy setting allows you to manage whether file downloads are permitted from the zone. This option gets determined by the zone of the page with the link causing the download, not the zone from which the file is delivered. If you enable this policy setting, files can be downloaded from the zone. If you disable this policy setting, files are prevented from being downloaded from the zone. If you don't configure this policy setting, files are prevented from being downloaded from the zone.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone run .NET Framework reliant components signed with Authenticode**  
  This policy setting allows you to manage whether .NET Framework components that are signed with Authenticode can be executed from Internet Explorer. These components include managed controls referenced from an object tag and managed executables referenced from a link. If you enable this policy setting, Internet Explorer will execute signed managed components. If you select Prompt in the drop-down box, Internet Explorer will prompt the user to determine whether to execute signed managed components. If you disable this policy setting, Internet Explorer won't execute signed managed components. If you don't configure this policy setting, Internet Explorer won't execute signed managed components.
  
  **Default**: Disable  
  
- **Internet Explorer prevent per user installation of Active X controls**  
  This policy setting allows you to prevent the installation of ActiveX controls on a per-user basis. If you enable this policy setting, ActiveX controls can't be installed on a per-user basis. If you disable or don't configure this policy setting, ActiveX controls can be installed on a per-user basis.
  
  **Default**: Enabled  
  
- **Internet Explorer prevent managing smart screen filter**  
  This policy setting prevents the user from managing SmartScreen Filter, which warns the user if the website they visit is known for fraudulent attempts to gather personal information through "phishing," or is known to host malware. If you enable this policy setting, the user isn't prompted to turn on SmartScreen Filter. All website addresses that aren't on the filters allow list are sent automatically to Microsoft without prompting the user. If you disable or don't configure this policy setting, the user gets prompted to decide whether to turn on SmartScreen Filter during the first-run experience.
  
  **Default**: Enable  
  
- **Internet Explorer processes MIME sniffing safety feature**  
  This policy setting determines whether Internet Explorer MIME sniffing will prevent promotion of a file of one type to a more dangerous file type. If you enable this policy setting, MIME sniffing will never promote a file of one type to a more dangerous file type. If you disable this policy setting, Internet Explorer processes will allow a MIME sniff promoting a file of one type to a more dangerous file type. If you don't configure this policy setting, MIME sniffing will never promote a file of one type to a more dangerous file type.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone download signed Active X controls**  
  This policy setting allows you to manage whether users may download signed ActiveX controls from a page in the zone. If you enable this policy, users can download signed controls without user intervention. If you select Prompt in the drop-down box, users are queried whether to download controls signed by publishers who aren't trusted. Code signed by trusted publishers is silently downloaded. If you disable the policy setting, signed controls can't download. If you don't configure this policy setting, users are queried whether to download controls signed by publishers who aren't trusted. Code signed by trusted publishers is silently downloaded.
  
  **Default**: Disable  
  
- **Internet Explorer auto complete**  
  This Auto-Complete feature can remember and suggest User names and passwords on Forms. If you enable this setting, the user can't change "User name and passwords on forms" or "prompt me to save passwords". The Auto Complete feature for User names and passwords on Forms is turned on. You have to decide whether to select "prompt me to save passwords". If you disable this setting the user can't change "User name and passwords on forms" or "prompt me to save passwords". The Auto Complete feature for User names and passwords on Forms is turned off. The user also can't opt to be prompted to save passwords. If you don't configure this setting, the user has the freedom of turning on Auto complete for User name and passwords on forms and the option of prompting to save passwords. To display this option, the users open the Internet Options dialog box, click the Contents Tab, and click the Settings button.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone allow VBscript to run**  
  This policy setting lets you decide whether VBScript can run on pages in specific Internet Explorer zones. Options include: 
  - *Enable* - VBScript runs on pages in specific zones, without any interaction. 
  - *Prompt* - Employees are prompted whether to allow VBScript to run in the zone. 
  - *Disable* - VBScript is prevented from running in the zone. If you disable or don’t configure this policy setting, VBScript runs without any interaction in the specified zone. 
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone allow only approved domains to use tdc Active X controls**  
  This policy setting controls if the user can run the TDC ActiveX control on websites. If you enable this policy setting, the TDC ActiveX control won't run from websites in this zone. If you disable this policy setting, the TDC Active X control will run from all sites in this zone.
  
  **Default**: Enabled  
  
- **Internet Explorer trusted zone don't run antimalware against Active X controls**  
  This policy setting determines whether Internet Explorer runs antimalware programs against ActiveX controls, to check if they're safe to load on pages. If you enable this policy setting, Internet Explorer won't check with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you disable this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you don't configure this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. Users can turn this behavior on or off, using Internet Explorer Security settings.
  
  **Default**: Disabled 
  
- **Internet Explorer local machine zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, the permission is set to Medium Safety.
  
  **Default**: Disable java 
  
- **Internet Explorer intranet zone do not run antimalware against Active X controls**
  This policy setting determines whether Internet Explorer runs antimalware programs against ActiveX controls, to check if they're safe to load on pages. If you enable this policy setting, Internet Explorer won't check with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you disable this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you don't configure this policy setting, Internet Explorer won't check with your antimalware program to see if it's safe to create an instance of the ActiveX control. Users can turn this behavior on or off, using Internet Explorer Security settings.
  
  **Default**: Disabled  

- **Internet Explorer restricted zone scriptlets**  
  This policy setting allows you to manage whether the user can run scriptlets. If you enable this policy setting, the user can run scriptlets. If you disable this policy setting, the user can't run scriptlets. If you don't configure this policy setting, the user can enable or disable scriptlets.
  
  **Default**: Disabled  
  
- **Internet Explorer processes notification bar**  
  This policy setting allows you to manage whether the Notification bar is displayed for Internet Explorer processes when file or code installs are restricted. By default, the Notification bar is displayed for Internet Explorer processes. If you enable this policy setting, the Notification bar displays for the Internet Explorer Processes. If you disable this policy setting, the Notification bar won't be displayed for Internet Explorer processes. If you don't configure this policy setting, the Notification bar doesn't display for Internet Explorer Processes.
  
  **Default**: Enabled  
  
- **Internet Explorer internet zone download signed ActiveX controls**  
  This policy setting allows you to manage whether users may download signed ActiveX controls from a page in the zone. If you enable this policy, users can download signed controls without user intervention. If you select Prompt in the drop-down box, users are queried whether to download controls signed by publishers who aren't trusted. Code signed by trusted publishers is silently downloaded. If you disable the policy setting, signed controls can't download. If you don't configure this policy setting, users are queried whether to download controls signed by publishers who aren't trusted. Code signed by trusted publishers is silently downloaded.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone smart screen**  
  This policy setting controls whether SmartScreen Filter scans pages in this zone for malicious content. If you enable this policy setting, SmartScreen Filter scans pages in this zone for malicious content. If you disable this policy setting, SmartScreen Filter doesn't scan pages in this zone for malicious content. If you don't configure this policy setting, the user can choose whether SmartScreen Filter scans pages in this zone for malicious content. Note: In Internet Explorer 7, this policy setting controls whether Phishing Filter scans pages in this zone for malicious content.
  
  **Default**: Enabled  
  
- **Internet Explorer remove run this time button for outdated Active X controls**  
  This policy setting allows you to stop users from seeing the "Run this time" button and from running specific outdated ActiveX controls in Internet Explorer. If you enable this policy setting, users won't see the "Run this time" button on the warning message that appears when Internet Explorer blocks an outdated ActiveX control. If you disable or don't configure this policy setting, users will see the "Run this time" button on the warning message that appears when Internet Explorer blocks an outdated ActiveX control. Clicking this button lets the user run the outdated ActiveX control once. For more information, see "Outdated ActiveX Controls" in the Internet Explorer TechNet library.
  
  **Default**: Enabled 
  
- **Internet Explorer internet zone launch applications and files in an iframe**  
  This policy setting allows you to manage whether applications may be run and files may be downloaded from an IFRAME reference in the HTML of the pages in this zone. If you enable this policy setting, users can run applications and download files from IFRAMEs on the pages in this zone without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to run applications and download files from IFRAMEs on the pages in this zone. If you disable this policy setting, users are prevented from running applications and downloading files from IFRAMEs on the pages in this zone. If you don't configure this policy setting, users are queried to choose whether to run applications and download files from IFRAMEs on the pages in this zone
  
  **Default**: Disable 
  
- **Internet Explorer restricted zone navigate windows and frames across different domains**  
  This policy setting allows you to set options for dragging content from one domain to a different domain when the source and destination are in different windows. If you enable this policy setting and click Enable, users can drag content from one domain to a different domain when the source and destination are in different windows. Users can't change this setting. If you enable this policy setting and click Disable, users can't drag content from one domain to a different domain when both the source and destination are in different windows. Users can't change this setting. In Internet Explorer 10, if you disable this policy setting or don't configure it, users can't drag content from one domain to a different domain when the source and destination are in different windows. Users can change this setting in the Internet Options dialog. In Internet Explorer 9 and earlier versions, if you disable this policy or don't configure it, users can drag content from one domain to a different domain when the source and destination are in different windows. Users can't change this setting.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone smart screen**  
  This policy setting controls whether SmartScreen Filter scans pages in this zone for malicious content. If you enable this policy setting, SmartScreen Filter scans pages in this zone for malicious content. If you disable this policy setting, SmartScreen Filter doesn't scan pages in this zone for malicious content. If you don't configure this policy setting, the user can choose whether SmartScreen Filter scans pages in this zone for malicious content. Note: In Internet Explorer 7, this policy setting controls whether Phishing Filter scans pages in this zone for malicious content.
  
  **Default**: Enabled  
  
- **Internet Explorer locked down trusted zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, Java applets are disabled.
  
  **Default**: Disable java 
  
- **Internet Explorer check signatures on downloaded programs**  
  This policy setting allows you to manage whether Internet Explorer checks for digital signatures (which identifies the publisher of signed software and verifies it hasn't been modified or tampered with) on user computers before downloading executable programs. If you enable this policy setting, Internet Explorer will check the digital signatures of executable programs and display their identities before downloading them to user computers. If you disable this policy setting, Internet Explorer won't check the digital signatures of executable programs or display their identities before downloading them to user computers. If you don't configure this policy, Internet Explorer won't check the digital signatures of executable programs or display their identities before downloading them to user computers.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone scripting of web browser controls**  
  This policy setting determines whether a page can control embedded WebBrowser controls via script. If you enable this policy setting, script access to the WebBrowser control is allowed. If you disable this policy setting, script access to the WebBrowser control isn't allowed. If you don't configure this policy setting, the user can enable or disable script access to the WebBrowser control. By default, script access to the WebBrowser control is allowed only in the Local Machine and Intranet zones.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone cross site scripting filter**  
  This policy controls if the Cross-Site Scripting (XSS) Filter will detect and prevent cross-site script injections into websites in this zone. If you enable this policy setting, the XSS Filter is turned on for sites in this zone, and the XSS Filter attempts to block cross-site script injections. If you disable this policy setting, the XSS Filter is turned off for sites in this zone, and Internet Explorer permits cross-site script injections.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone binary and script behaviors**  
  This policy setting allows you to manage dynamic binary and script behaviors: components that encapsulate specific functionality for HTML elements to which they were attached. If you enable this policy setting, binary and script behaviors are available. If you select Administrator approved in the drop-down box, only behaviors listed in the Admin-approved Behaviors under Binary Behaviors Security Restriction policy are available. If you disable this policy setting, binary and script behaviors aren't available unless applications have implemented a custom security manager. If you don't configure this policy setting, binary and script behaviors aren't available unless applications have implemented a custom security manager.
  
  **Default**: Disable  
  
- **Internet Explorer security settings check**  
  This policy setting turns off the Security Settings Check feature, which checks Internet Explorer security settings to determine when the settings put Internet Explorer at risk. If you enable this policy setting, the feature is turned off. If you disable or don't configure this policy setting, the feature is turned on.
  
  **Default**: Enabled  
  
- **Internet Explorer internet zone security warning for potentially unsafe files**  
  This policy setting controls if the "Open File - Security Warning" message appears when the user tries to open executable files or other potentially unsafe files (from an intranet file share by using File Explorer, for example). If you enable this policy setting and set the drop-down box to Enable, these files open without a security warning. If you set the drop-down box to Prompt, a security warning appears before the files open. If you disable this policy setting, these files don't open. If you don't configure this policy setting, the user can configure how the computer handles these files. By default, these files are blocked in the Restricted zone, enabled in the Intranet and Local Computer zones, and set to prompt in the Internet and Trusted zones.
  
  **Default**: Prompt  
  
- **Internet Explorer intranet zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, the permission is set to Medium Safety.
  
  **Default**: High safety 
  
- **Internet Explorer block outdated Active X controls**  
  This policy setting determines whether Internet Explorer blocks specific outdated ActiveX controls. Outdated ActiveX controls are never blocked in the Intranet Zone. If you enable this policy setting, Internet Explorer stops blocking outdated ActiveX controls. If you disable or don't configure this policy setting, Internet Explorer continues to block specific outdated ActiveX controls. For more information, see "Outdated ActiveX Controls" in the Internet Explorer TechNet library.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone popup blocker**  
  This policy setting allows you to manage whether unwanted pop-up windows appear. Pop-up windows that are opened when the end user clicks a link aren't blocked. If you enable this policy setting, most unwanted pop-up windows are prevented from appearing. If you disable this policy setting, pop-up windows aren't prevented from appearing. If you don't configure this policy setting, most unwanted pop-up windows are prevented from appearing.
  
  **Default**: Enable  
  
- **Internet Explorer processes MK protocol security restriction**  
  The MK Protocol Security Restriction policy setting reduces attack surface area by preventing the MK protocol. Resources hosted on the MK protocol will fail. If you enable this policy setting, the MK Protocol is prevented for File Explorer and Internet Explorer, and resources hosted on the MK protocol will fail. If you disable this policy setting, applications can use the MK protocol API. Resources hosted on the MK protocol will work for the File Explorer and Internet Explorer processes. If you don't configure this policy setting, the MK Protocol is prevented for File Explorer and Internet Explorer, and resources hosted on the MK protocol will fail.
  
  **Default**: Enabled  
  
- **Internet Explorer trusted zone java permissions**   
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, the permission is set to Low Safety.
  
  **Default**: High safety  
  
- **Internet Explorer restricted zone scripting of java applets**  
  This policy setting allows you to manage whether applets are exposed to scripts within the zone. If you enable this policy setting, scripts can access applets automatically without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to allow scripts to access applets. If you disable this policy setting, scripts are prevented from accessing applets. If you don't configure this policy setting, scripts are prevented from accessing applets.
  
  **Default**: Disable  
  
- **Internet Explorer locked down restricted zone java permissions**   
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, Java applets are disabled.
  
  **Default**: Disable java 
  
- **Internet Explorer internet zone allow only approved domains to use ActiveX controls**   
  This policy setting controls if the user is prompted to allow ActiveX controls to run on websites other than the website that installed the ActiveX control. If you enable this policy setting, the user is prompted before ActiveX controls can run from websites in this zone. The user can choose to allow the control to run from the current site or from all sites. If you disable this policy setting, the user doesn't see the per-site ActiveX prompt, and ActiveX controls can run from all sites in this zone.
  
  **Default**: Enabled  
  
- **Internet Explorer include all network paths**  
  Internet Explorer include all network paths
  
  **Default**: Disabled 
  
- **Internet Explorer internet zone protected mode**  
  This policy setting allows you to turn on Protected Mode. Protected Mode helps protect Internet Explorer from exploited vulnerabilities by reducing the locations that Internet Explorer can write to in the registry and the file system. If you enable this policy setting, Protected Mode is turned on. The user can't turn off Protected Mode. If you disable this policy setting, Protected Mode is turned off. The user can't turn on Protected Mode. If you don't configure this policy setting, the user can turn on or turn off Protected Mode.
  
  **Default**: Enable 
  
- **Internet Explorer internet zone initialize and script Active X controls not marked as safe**  
  This policy setting allows you to manage ActiveX controls not marked as safe. If you enable this policy setting, ActiveX controls run, loaded with parameters, and scripted without setting object safety for untrusted data or scripts. This setting isn't recommended, except for secure and administered zones. This setting causes both unsafe and safe controls to be initialized and scripted, ignoring the Script ActiveX controls marked safe for scripting option. If you enable this policy setting and select Prompt in the drop-down box, users are queried whether to allow the control to load with parameters or scripted. If you disable this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted. If you don't configure this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted.
  
  **Default**: Disable 
  
- **Internet Explorer locked down restricted zone smart screen**   
  This policy setting controls whether SmartScreen Filter scans pages in this zone for malicious content. If you enable this policy setting, SmartScreen Filter scans pages in this zone for malicious content. If you disable this policy setting, SmartScreen Filter doesn't scan pages in this zone for malicious content. If you don't configure this policy setting, the user can choose whether SmartScreen Filter scans pages in this zone for malicious content. Note: In Internet Explorer 7, this policy setting controls whether Phishing Filter scans pages in this zone for malicious content.
  
  **Default**: Enabled  
  
- **Internet Explorer crash detection**  
  This policy setting allows you to manage the crash detection feature of add-on Management. If you enable this policy setting, a crash in Internet Explorer will exhibit behavior found in Windows XP Professional Service Pack 1 and earlier, namely to invoke Windows Error Reporting. All policy settings for Windows Error Reporting continue to apply. If you disable or don't configure this policy setting, the crash detection feature for add-on management is functional.
  
  **Default**: Disabled  
  
- **Internet Explorer internet zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, the permission is set to High Safety.
  
  **Default**: Disable java  
  
- **Internet Explorer restricted zone active scripting**  
  This policy setting allows you to manage whether script code on pages in the zone is run. If you enable this policy setting, script code on pages in the zone can run automatically. If you select Prompt in the drop-down box, users are queried to choose whether to allow script code on pages in the zone to run. If you disable this policy setting, script code on pages in the zone is prevented from running. If you don't configure this policy setting, script code on pages in the zone is prevented from running.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone logon options**  
  This policy setting allows you to manage settings for sign in options. If you enable this policy setting, you can choose from the following sign in options. Anonymous log on to disable HTTP authentication and use the guest account only for the Common Internet File System (CIFS) protocol. Prompt for user name and password to query users for user IDs and passwords. After a user is queried, these values can be used silently for the remainder of the session. Automatic log on only in Intranet zone to query users for user IDs and passwords in other zones. After a user is queried, these values can be used silently for the rest of the session. Automatic sign in with current user name and password to attempt log on using Windows NT Challenge Response (also known as NTLM authentication). If the server supports Windows NT Challenge Response, the sign in uses the user's network user name and password for log on. If the server doesn't support Windows NT Challenge Response, the user is queried to provide the user name and password. If you disable this policy setting, sign in is set to Automatic log on only in Intranet zone. If you don't configure this policy setting, sign in is set to Automatic sign in only in Intranet zone.
  
  **Default**: Prompt  
  
- **Internet Explorer restricted zone allow vbscript to run**  
  This policy setting allows you to manage whether VBScript can be run on pages from the specified zone in Internet Explorer. If you selected Enable in the drop-down box, VBScript can run without user intervention. If you selected Prompt in the drop-down box, users are asked to choose whether to allow VBScript to run. If you selected Disable in the drop-down box, VBScript is prevented from running. If you don't configure or disable this policy setting, VBScript is prevented from running.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone drag content from different domains across windows**  
  This policy setting allows you to set options for dragging content from one domain to a different domain when the source and destination are in different windows. If you enable this policy setting and click Enable, users can drag content from one domain to a different domain when the source and destination are in different windows. Users can't change this setting. If you enable this policy setting and click Disable, users can't drag content from one domain to a different domain when both the source and destination are in different windows. Users can't change this setting. In Internet Explorer 10, if you disable this policy setting or don't configure it, users can't drag content from one domain to a different domain when the source and destination are in different windows. Users can change this setting in the Internet Options dialog. In Internet Explorer 9 and earlier versions, if you disable this policy or don't configure it, users can drag content from one domain to a different domain when the source and destination are in different windows. Users can't change this setting.
  
  **Default**: Disabled 
  
- **Internet Explorer intranet zone initialize and script Active X controls not marked as safe**  
  This policy setting allows you to manage ActiveX controls not marked as safe. If you enable this policy setting, ActiveX controls run, loaded with parameters, and scripted without setting object safety for untrusted data or scripts. This setting isn't recommended, except for secure and administered zones. This setting causes both unsafe and safe controls to be initialized and scripted, ignoring the Script ActiveX controls marked safe for scripting option. If you enable this policy setting and select Prompt in the drop-down box, users are queried whether to allow the control to load with parameters or scripted. If you disable this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted. If you don't configure this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted.
  
  **Default**: Disable 
  
- **Internet Explorer download enclosures**  
  This policy setting prevents the user from having enclosures (file attachments) downloaded from a feed to the user's computer. If you enable this policy setting, the user can't set the Feed Sync Engine to download an enclosure through the Feed property page. A developer can't change the download setting through the Feed APIs. If you disable or don't configure this policy setting, the user can set the Feed Sync Engine to download an enclosure through the Feed property page. A developer can change the download setting through the Feed APIs.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone download unsigned Active X controls**   
  This policy setting allows you to manage whether users may download unsigned ActiveX controls from the zone. Such code is potentially harmful, especially when coming from an untrusted zone. If you enable this policy setting, users can run unsigned controls without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to allow the unsigned control to run. If you disable this policy setting, users can't run unsigned controls. If you don't configure this policy setting, users can't run unsigned controls.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone drag content from different domains within windows**  
  This policy setting allows you to manage whether users may download unsigned ActiveX controls from the zone. Such code is potentially harmful, especially when coming from an untrusted zone. If you enable this policy setting, users can run unsigned controls without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to allow the unsigned control to run. If you disable this policy setting, users can't run unsigned controls. If you don't configure this policy setting, users can't run unsigned controls.
  
  **Default**: Disabled  
  
- **Internet Explorer processes restrict Active X install**   
  This policy setting enables applications hosting the Web Browser Control to block automatic prompting of ActiveX control installation. If you enable this policy setting, the Web Browser Control will block automatic prompting of ActiveX control installation for all processes. If you disable or don't configure this policy setting, the Web Browser Control won't block automatic prompting of ActiveX control installation for all processes.
  
  **Default**: Enabled  
  
- **Internet Explorer internet zone scriptlets**
  This policy setting allows you to manage whether the user can run scriptlets. If you enable this policy setting, the user can run scriptlets. If you disable this policy setting, the user can't run scriptlets. If you don't configure this policy setting, the user can enable or disable scriptlets.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone drag and drop or copy and paste files**  
  This policy setting allows you to manage whether users can drag files or copy and paste files from a source within the zone. If you enable this policy setting, users can drag files or copy and paste files from this zone automatically. If you select Prompt in the drop-down box, users are queried to choose whether to drag or copy files from this zone. If you disable this policy setting, users are prevented from dragging files or copying and pasting files from this zone. If you don't configure this policy setting, users are queried to choose whether to drag or copy files from this zone.
  
  **Default**: Disable  
  
- **Internet Explorer software when signature is invalid**   
  This policy setting allows you to manage whether software, such as ActiveX controls and file downloads, can be installed or run by the user even though the signature is invalid. An invalid signature might indicate that someone has tampered with the file. If you enable this policy setting, users are prompted to install or run files with an invalid signature. If you disable this policy setting, users can't run or install files with an invalid signature. If you don't configure this policy, users can choose to run or install files with an invalid signature.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone copy and paste via script**   
  This policy setting allows you to manage whether scripts can perform a clipboard operation (for example, cut, copy, and paste) in a specified region. If you enable this policy setting, a script can perform a clipboard operation. If you select Prompt in the drop-down box, users are queried as to whether to perform clipboard operations. If you disable this policy setting, a script can't perform a clipboard operation. If you don't configure this policy setting, a script can't perform a clipboard operation.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone drag content from different domains across windows**  
  This policy setting allows you to set options for dragging content from one domain to a different domain when the source and destination are in different windows. If you enable this policy setting and click Enable, users can drag content from one domain to a different domain when the source and destination are in different windows. Users can't change this setting. If you enable this policy setting and click Disable, users can't drag content from one domain to a different domain when both the source and destination are in different windows. Users can't change this setting. In Internet Explorer 10, if you disable this policy setting or don't configure it, users can't drag content from one domain to a different domain when the source and destination are in different windows. Users can change this setting in the Internet Options dialog. In Internet Explorer 9 and earlier versions, if you disable this policy or don't configure it, users can drag content from one domain to a different domain when the source and destination are in different windows. Users can't change this setting.   
  **Default**: Disabled  
  
- **Internet Explorer users adding sites**  
  Prevents users from adding or removing sites from security zones. A security zone is a group of Web sites with the same security level. If you enable this policy, the site management settings for security zones are disabled. (To see the site management settings for security zones, in the Internet Options dialog box, click the Security tab, and then click the Sites button.) If you disable this policy or don't configure it, users can add Web sites to or remove sites from the Trusted Sites and Restricted Sites zones, and alter settings for the Local Intranet zone. This policy prevents users from changing site management settings for security zones established by the administrator. Note: The "Disable the Security page" policy (located in \User Configuration\Administrative Templates\Windows Components\Internet Explorer\Internet Control Panel), which removes the Security tab from the interface, takes precedence over this policy. If it's enabled, this policy is ignored. Also, see the "Security zones: Use only machine settings" policy.
  
  **Default**: Disabled  
  
- **Internet Explorer internet zone script initiated windows**  
  This policy setting allows you to manage restrictions on script-initiated pop-up windows and windows that include the title and status bars. If you enable this policy setting, Windows Restrictions security won't apply in this zone. The security zone runs without the added layer of security provided by this feature. If you disable this policy setting, the possible harmful actions contained in script-initiated pop-up windows and windows that include the title and status bars can't run. This Internet Explorer security feature is on in this zone as dictated by the Scripted Windows Security Restrictions feature control setting for the process. If you don't configure this policy setting, the possible harmful actions contained in script-initiated pop-up windows and windows that include the title and status bars can't run. This Internet Explorer security feature is on in this zone as dictated by the Scripted Windows Security Restrictions feature control setting for the process.
  
  **Default**: Disabled  
  
- **Internet Explorer security zones use only machine settings**  
  Applies security zone information to all users of the same computer. A security zone is a group of Web sites with the same security level. If you enable this policy, changes that the user makes to a security zone will apply to all users of that computer. If you disable this policy or don't configure it, users of the same computer can establish their own security zone settings. Use this policy to ensure that security zone settings apply uniformly to the same computer and don't vary from user to user. Also, see the "Security zones: don't allow users to change policies" policy.
  
  **Default**: Enabled  
  
- **Internet Explorer locked down local machine zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, Java applets are disabled
  
  **Default**: Disable java 
  
- **Internet Explorer restricted zone do not run antimalware against Active X controls**   
  This policy setting determines whether Internet Explorer runs antimalware programs against ActiveX controls, to check if they're safe to load on pages. If you enable this policy setting, Internet Explorer won't check with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you disable this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you don't configure this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. Users can turn this behavior on or off, using Internet Explorer Security settings.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone run .NET Framework reliant components signed with authenticode**  
  This policy setting allows you to manage whether .NET Framework components that are signed with Authenticode can be executed from Internet Explorer. These components include managed controls referenced from an object tag and managed executables referenced from a link. If you enable this policy setting, Internet Explorer will execute signed managed components. If you select Prompt in the drop-down box, Internet Explorer will prompt the user to determine whether to execute signed managed components. If you disable this policy setting, Internet Explorer won't execute signed managed components. If you don't configure this policy setting, Internet Explorer won't execute signed managed components.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone access to data sources**  
  This policy setting allows you to manage whether Internet Explorer can access data from another security zone using the Microsoft XML Parser (MSXML) or ActiveX Data Objects (ADO). If you enable this policy setting, users can load a page in the zone that uses MSXML or ADO to access data from another site in the zone. If you select Prompt in the drop-down box, users are queried to choose whether to allow a page to load in the zone that uses MSXML or ADO to access data from another site in the zone. If you disable this policy setting, users can't load a page in the zone that uses MSXML or ADO to access data from another site in the zone. If you don't configure this policy setting, users can't load a page in the zone that uses MSXML or ADO to access data from another site in the zone.
  
  **Default**: Disable 
  
- **Internet Explorer internet zone don't run antimalware against ActiveX controls**   
  This policy setting determines whether Internet Explorer runs antimalware programs against ActiveX controls, to check if they're safe to load on pages. If you enable this policy setting, Internet Explorer won't check with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you disable this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you don't configure this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. Users can turn this behavior on or off, using Internet Explorer Security settings.
  
  **Default**: Disabled  
  
- **Internet Explorer internet zone copy and paste via script**  
  This policy setting allows you to manage whether scripts can perform a clipboard operation (for example, cut, copy, and paste) in a specified region. If you enable this policy setting, a script can perform a clipboard operation. If you select Prompt in the drop-down box, users are queried as to whether to perform clipboard operations. If you disable this policy setting, a script can't perform a clipboard operation. If you don't configure this policy setting, a script can perform a clipboard operation.
  
  **Default**: Disable  
  
- **Internet Explorer use Active X installer service**   
  This policy setting allows you to specify how ActiveX controls are installed. If you enable this policy setting, ActiveX controls are installed only if the ActiveX Installer Service is present and has been configured to allow the installation of ActiveX controls. If you disable or don't configure this policy setting, ActiveX controls, including per-user controls, are installed through the standard installation process.
  
  **Default**: Enabled  
  
- **Internet Explorer processes protection from zone elevation**  
  Internet Explorer places restrictions on each Web page it opens. The restrictions are dependent upon the location of the Web page (Internet, Intranet, Local Machine zone, and so on). For example, Web pages on the local computer have the fewest security restrictions and are in the Local Machine zone, making the Local Machine security zone a prime target for malicious users. If you enable this policy setting, any zone can be protected from zone elevation for all processes. If you disable or don't configure this policy setting, processes other than Internet Explorer or those listed in the Process List receive no such protection.
  
  **Default**: Enabled  
  
- **Internet Explorer internet zone download unsigned ActiveX controls**   
  This policy setting allows you to manage whether users may download unsigned ActiveX controls from the zone. Such code is potentially harmful, especially when coming from an untrusted zone. If you enable this policy setting, users can run unsigned controls without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to allow the unsigned control to run. If you disable this policy setting, users can't run unsigned controls. If you don't configure this policy setting, users can't run unsigned controls.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone navigate windows and frames across different domains**   
  This policy setting allows you to manage the opening of windows and frames and access of applications across different domains. If you enable this policy setting, users can open windows and frames from other domains and access applications from other domains. If you select Prompt in the drop-down box, users are queried whether to allow windows and frames to access applications from other domains. If you disable this policy setting, users can't open windows and frames to access applications from different domains. If you don't configure this policy setting, users can open windows and frames from other domains and access applications from other domains.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone updates to status bar via script**  
  This policy setting allows you to manage whether a script can update the status bar within the zone. If you enable this policy setting, scripts can update the status bar. If you disable or don't configure this policy setting, script isn't allowed to update the status bar.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone include local path when uploading files to server**  
  This policy setting controls if local path information is sent when the user is uploading a file via an HTML form. If the local path information is sent, some information may be unintentionally revealed to the server. For instance, files sent from the user's desktop may contain the user name as a part of the path. If you enable this policy setting, path information is sent when the user is uploading a file via an HTML form. If you disable this policy setting, path information is removed when the user is uploading a file via an HTML form. If you don't configure this policy setting, the user can choose whether path information is sent when they are uploading a file via an HTML form. By default, path information is sent.
  
  **Default**: Disabled  
  
- **Internet Explorer processes restrict file download**   
  This policy setting enables applications hosting the Web Browser Control to block automatic prompting of file downloads that aren't user initiated. If you enable this policy setting, the Web Browser Control will block automatic prompting of file downloads that aren't user initiated for all processes. If you disable this policy setting, the Web Browser Control won't block automatic prompting of file downloads that aren't user initiated for all processes.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone allow only approved domains to use Active X controls**   
  This policy setting controls if the user is prompted to allow ActiveX controls to run on websites other than the website that installed the ActiveX control. If you enable this policy setting, the user is prompted before ActiveX controls can run from websites in this zone. The user can choose to allow the control to run from the current site or from all sites. If you disable this policy setting, the user doesn't see the per-site ActiveX prompt, and ActiveX controls can run from all sites in this zone.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone initialize and script Active X controls not marked as safe**  
  This policy setting allows you to manage ActiveX controls not marked as safe. If you enable this policy setting, ActiveX controls run, loaded with parameters, and scripted without setting object safety for untrusted data or scripts. This setting isn't recommended, except for secure and administered zones. This setting causes both unsafe and safe controls to be initialized and scripted, ignoring the Script ActiveX controls marked safe for scripting option. If you enable this policy setting and select Prompt in the drop-down box, users are queried whether to allow the control to load with parameters or scripted. If you disable this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted. If you don't configure this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted.
  
  **Default**: Disable  
  
- **Internet Explorer users changing policies**  
    Prevents users from changing security zone settings. A security zone is a group of Web sites with the same security level. If you enable this policy, the Custom Level button and security-level slider on the Security tab in the Internet Options dialog box are disabled. If you disable this policy or don't configure it, users can change the settings for security zones. This policy prevents users from changing security zone settings established by the administrator. Note: The "Disable the Security page" policy (located in \User Configuration\Administrative Templates\Windows Components\Internet Explorer\Internet Control Panel), which removes the Security tab from Internet Explorer in Control Panel, takes precedence over this policy. If it's enabled, this policy is ignored. Also, see the "Security zones: Use only machine settings" policy.
    
  **Default**: Disabled  
  
- **Internet Explorer restricted zone protected mode**  
  This policy setting allows you to turn on Protected Mode. Protected Mode helps protect Internet Explorer from exploited vulnerabilities by reducing the locations that Internet Explorer can write to in the registry and the file system. If you enable this policy setting, Protected Mode is turned on. The user can't turn off Protected Mode. If you disable this policy setting, Protected Mode is turned off. The user can't turn on Protected Mode. If you don't configure this policy setting, the user can turn on or turn off Protected Mode.
  
  **Default**: Enable  
  
- **Internet Explorer internet zone user data persistence**  
  This policy setting allows you to manage the preservation of information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk. When a user returns to a persisted page, the state of the page can be restored if this policy setting is appropriately configured. If you enable this policy setting, users can preserve information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk. If you disable this policy setting, users can't preserve information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk. If you don't configure this policy setting, users can preserve information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk.
  
  **Default**: Disabled  
  
- **Internet Explorer internet zone scripting of web browser controls**  
 
  This policy setting determines whether a page can control embedded WebBrowser controls via script. If you enable this policy setting, script access to the WebBrowser control is allowed. If you disable this policy setting, script access to the WebBrowser control isn't allowed. If you don't configure this policy setting, the user can enable or disable script access to the WebBrowser control. By default, script access to the WebBrowser control is allowed only in the Local Machine and Intranet zones.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone user data persistence**  
    This policy setting allows you to manage the preservation of information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk. When a user returns to a persisted page, the state of the page can be restored if this policy setting is appropriately configured. If you enable this policy setting, users can preserve information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk. If you disable this policy setting, users can't preserve information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk. If you don't configure this policy setting, users can't preserve information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk.  
  
  **Default**: Disabled  
  
- **Internet Explorer locked down intranet zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, Java applets are disabled.
  
  **Default**: Disable java  
  
- **Internet Explorer enhanced protected mode**  
  Enhanced Protected Mode provides additional protection against malicious websites by using 64-bit processes on 64-bit versions of Windows. For computers running at least Windows 8, Enhanced Protected Mode also limits the locations Internet Explorer can read from in the registry and the file system. If you enable this policy setting, Enhanced Protected Mode is turned on. Any zone that has Protected Mode enabled will use Enhanced Protected Mode. Users won't be able to disable Enhanced Protected Mode. If you disable this policy setting, Enhanced Protected Mode is turned off. Any zone that has Protected Mode enabled will use the version of Protected Mode introduced in Internet Explorer 7 for Windows Vista. If you don't configure this policy, users can turn on or turn off Enhanced Protected Mode on the Advanced tab of the Internet Options dialog.
  
  **Default**: Enabled  
  
- **Internet Explorer bypass smart screen warnings**  
  This policy setting determines whether the user can bypass warnings from SmartScreen Filter. SmartScreen Filter warns the user about executable files that Internet Explorer users don't commonly download from the Internet. If you enable this policy setting, SmartScreen Filter warnings block the user. If you disable or don't configure this policy setting, the user can bypass SmartScreen Filter warnings.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone meta refresh**  
  This policy setting allows you to manage whether a user's browser can be redirected to another Web page if the author of the Web page uses the Meta Refresh setting (tag) to redirect browsers to another Web page. If you enable this policy setting, a user's browser that loads a page containing an active Meta Refresh setting can be redirected to another Web page. If you disable this policy setting, a user's browser that loads a page containing an active Meta Refresh setting can't be redirected to another Web page. If you don't configure this policy setting, a user's browser that loads a page containing an active Meta Refresh setting can't be redirected to another Web page.
  
  **Default**: Disabled  
  
## Local Policies Security Options
For more information, see [Policy CSP - LocalPoliciesSecurityOptions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions) in the Windows documentation. 

- **Restrict anonymous access to named pipes and shares**  
  When enabled, this security setting restricts anonymous access to shares and pipes to the settings for: (1) Named pipes that can be accessed anonymously (2) Shares that can be accessed anonymously
  
  **Default**: Yes  
  
- **Minimum session security for NTLM SSP based servers**  
  This security setting allows a server to require the negotiation of 128-bit encryption and/or NTLMv2 session security. These values are dependent on the LAN Manager Authentication Level security setting value. The options are: Require NTLMv2 session security: The connection will fail if message integrity isn't negotiated. Require 128-bit encryption. The connection will fail if strong encryption (128-bit) isn't negotiated.
  
  **Default**: Require NTLM V2 and 128 bit encryption  
  
- **Minutes of lock screen inactivity until screen saver activates**  
  Windows notices inactivity of a logon session, and if the amount of inactive time exceeds the inactivity limit, then the screen saver will run, locking the session.
  
  **Default**: 15
  
- **Require client to always digitally sign communications** 
  This security setting determines whether all secure channel traffic initiated by the domain member must be signed or encrypted. When a computer joins a domain, a computer account is created. After that, when the system starts, it uses the computer account password to create a secure channel with a domain controller for its domain. This secure channel is used to perform operations such as NTLM pass through authentication, LSA SID/name Lookup and more. This setting determines if all secure channel traffic initiated by the domain member meets minimum security requirements. Specifically it determines whether all secure channel traffic started by the domain member must be signed or encrypted. If this policy is enabled, then the secure channel won't be established unless either signing or encryption of all secure channel traffic is negotiated. If this policy is disabled, then encryption and signing of all secure channel traffic is negotiated with the Domain Controller in which case the level of signing and encryption depends on the version of the Domain Controller and the settings of the following two policies: Domain member: Digitally encrypt secure channel data (when possible) Domain member: Digitally sign secure channel data (when possible)
  
  **Default**: Yes
  
- **Authentication level**  
  This security setting determines which challenge/response authentication protocol is used for network logons. This choice affects the level of authentication protocol used by clients, the level of session security negotiated, and the level of authentication accepted by servers as follows:  
  - *Send LM and NTLM responses*: Clients use LM and NTLM authentication and never use NTLMv2 session security; domain controllers accept LM, NTLM, and NTLMv2 authentication. 
  - *Send LM and NTLM - NTLMv2 if negotiated*: Clients use LM and NTLM authentication and use NTLMv2 session security if the server supports it; domain controllers accept LM, NTLM, and NTLMv2 authentication. 
  - *Send NTLM response only*: Clients use NTLM authentication only and use NTLMv2 session security if the server supports it; domain controllers accept LM, NTLM, and NTLMv2 authentication. 
  - *Send NTLMv2 response only*: Clients use NTLMv2 authentication only and use NTLMv2 session security if the server supports it; domain controllers accept LM, NTLM, and NTLMv2 authentication. 
  - *Send NTLMv2 response only. Refuse LM*: Clients use NTLMv2 authentication only and use NTLMv2 session security if the server supports it; domain controllers refuse LM (accept only NTLM and NTLMv2 authentication). 
  - *Send NTLMv2 response only. Refuse LM and NTLM*: Clients use NTLMv2 authentication only and use NTLMv2 session security if the server supports it; domain controllers refuse LM and NTLM (accept only NTLMv2 authentication). 
    
  **Default**: Send NTLMv2 response only. Refuse LM and NTLM
  
- **Prevent clients from sending unencrypted passwords to third party SMB servers**  
  If this security setting is enabled, the Server Message Block (SMB) redirector can send plaintext passwords to non-Microsoft SMB servers that don't support password encryption during authentication. Sending unencrypted passwords is a security risk.
  
  **Default**: Yes
  
- **Disable server digitally signing communications always**  
  This security setting determines whether the SMB client attempts to negotiate SMB packet signing. The server message block (SMB) protocol provides the basis for Microsoft file and print sharing and many other networking operations, such as remote Windows administration. To prevent man-in-the-middle attacks that modify SMB packets in transit, the SMB protocol supports the digital signing of SMB packets. This policy setting determines whether the SMB client component attempts to negotiate SMB packet signing when it connects to an SMB server. If this setting is enabled, the Microsoft network client will ask the server to perform SMB packet signing upon session setup. If packet signing has been enabled on the server, packet signing is negotiated. If this policy is disabled, the SMB client will never negotiate SMB packet signing.
  
  **Default**: Yes
  
- **Administrator elevation prompt behavior**  
  This policy setting controls the behavior of the elevation prompt for administrators. The options are: 
    - *Elevate without prompting*: Allows privileged accounts to perform an operation that requires elevation without requiring consent or credentials. Note: Use this option only in the most constrained environments. 
    - *Prompt for credentials on the secure desktop*: When an operation requires elevation of privilege, the user is prompted on the secure desktop to enter a privileged user name and password. If the user enters valid credentials, the operation continues with the user's highest available privilege. 
    - *Prompt for consent on the secure desktop*: When an operation requires elevation of privilege, the user is prompted on the secure desktop to select either Permit or Deny. If the user selects Permit, the operation continues with the user's highest available privilege. 
    - *Prompt for credentials*: When an operation requires elevation of privilege, the user is prompted to enter an administrative user name and password. If the user enters valid credentials, the operation continues with the applicable privilege. 
    - *Prompt for consent*: When an operation requires elevation of privilege, the user is prompted to select either Permit or Deny. If the user selects Permit, the operation continues with the user's highest available privilege.  
    - *Prompt for consent for non-Windows binaries*: When an operation for a non-Microsoft application requires elevation of privilege, the user is prompted on the secure desktop to select either Permit or Deny. If the user selects Permit, the operation continues with the user's highest available privilege.   
  
  **Default**: Prompt for consent on the secure desktop
  
- **Minimum session security for NTLM SSP based clients**  
  This security setting allows a client to require the negotiation of 128-bit encryption and/or NTLMv2 session security. These values are dependent on the LAN Manager Authentication Level security setting value. The options are:
  - Require NTLMv2 session security: The connection will fail if NTLMv2 protocol isn't negotiated. 
  - *Require 128-bit encryption*: The connection will fail if strong encryption (128-bit) isn't negotiated.
  - *Require NTLMv2 and 128-bit encryption*. 

  **Default**: Require NTLM V2 128 encryption
  
- **Smart card removal behavior**  
    This security setting determines what happens when the smart card for a logged-on user is removed from the smart card reader. The options are:
     - *No action*. 
     - *Lock Workstation* - The workstation is locked when the smart card is removed, allowing users to leave the area, take their smart card with them, and still maintain a protected session.
     - *Force Logoff* - the user is automatically logged off when the smart card is removed.
     - *Disconnect Remote Desktop session* - Removal of the smart card disconnects the session without logging the user off. This allows the user to insert the smart card and resume the session later, or at another smart card reader-equipped computer, without having to log on again. If the session is local, this policy functions identically to Lock Workstation.   
    
  **Default**: Lock workstation
  
- **Block anonymous enumeration of SAM accounts and shares**  
  This security setting determines whether to allow anonymous enumeration of SAM accounts and shares. Windows allows anonymous users to perform certain activities, such as enumerating the names of domain accounts and network shares. This is convenient, for example, when an administrator wants to grant access to users in a trusted domain that doesn't maintain a reciprocal trust. If you don't want to allow anonymous enumeration of SAM accounts and shares, then set this policy to *Yes*.
  
  **Default**: Yes
  
- **Block remote logon with blank password**  
  This security setting determines whether local accounts that aren't password protected can be used to log on from locations other than the physical computer console. If enabled, local accounts that aren't password protected must use the computer's keyboard to log on. 

  *Warning*: Computers that aren't in physically secure locations should always enforce strong password policies for all local user accounts. Otherwise, anyone with physical access to the computer can log on by using a user account that doesn't have a password. This is especially important for portable computers. 

  If you apply this security policy to the Everyone group, no one can log on through Remote Desktop Services. This setting doesn't affect logons that use domain accounts. It's possible for applications that use remote interactive logons to bypass this setting.
  
  **Default**: Yes
  
- **Standard user elevation prompt behavior**  
  This policy setting controls the behavior of the elevation prompt for standard users. 
  - *Automatically deny elevation requests*: When an operation requires elevation of privilege, a configurable access denied error message is displayed. An enterprise that is running desktops as standard user may choose this setting to reduce help desk calls. 
  - *Prompt for credentials on the secure desktop*: When an operation requires elevation of privilege, the user is prompted on the secure desktop to enter a different user name and password. If the user enters valid credentials, the operation continues with the applicable privilege. 
  - *Prompt for credentials*: When an operation requires elevation of privilege, the user is prompted to enter an administrative user name and password. If the user enters valid credentials, the operation continues with the applicable privilege.  
  
  **Default**: Automatically deny elevation requests
  
- **Require admin approval mode for administrators**  
  This policy setting controls the behavior of all User Account Control (UAC) policy settings for the computer. If you change this policy setting, you must restart your computer. The options are:   
  - *Not configured*: Admin Approval Mode and all related UAC policy settings are disabled. Note: If this policy setting is disabled, the Security Center notifies you that the overall security of the operating system has been reduced. 
  - *Yes*: Admin Approval Mode is enabled. This policy must be enabled and related UAC policy settings must be set appropriately to allow the built-in Administrator account and all other users who are members of the Administrators group to run in Admin Approval Mode.  
  
  **Default**: Yes
  
- **Prevent anonymous enumeration of SAM accounts**  
  This security setting determines what additional permissions are granted for anonymous connections to the computer. Windows allows anonymous users to perform certain activities, such as enumerating the names of domain accounts and network shares. This is convenient, for example, when an administrator wants to grant access to users in a trusted domain that doesn't maintain a reciprocal trust. This security option allows additional restrictions to be placed on anonymous connections as follows: 
  - *Yes*: Don't allow enumeration of SAM accounts. This option replaces Everyone with Authenticated Users in the security permissions for resources.
  - *Not configured*: No additional restrictions. Rely on default permissions.  
  
  **Default**: Yes
  
- **Allow remote calls to security accounts manager**  
  This policy setting allows you to restrict remote rpc connections to SAM. If not selected, the default security descriptor is used.
  
  **Default**: *O:BAG:BAD:(A;;RC;;;BA)*

- **Use admin approval mode**  
  This policy setting controls the behavior of Admin Approval Mode for the built-in Administrator account. The options are: 
  - *Yes*: The built-in Administrator account uses Admin Approval Mode. By default, any operation that requires elevation of privilege will prompt the user to approve the operation. 
  - *Not Configured*: The built-in Administrator account runs all applications with full administrative privilege.  

  **Default**: Yes
  
- **Allow UI access applications for secure locations**  
  This policy setting controls whether User Interface Accessibility (UIAccess or UIA) programs can automatically disable the secure desktop for elevation prompts used by a standard user. 
  - *Yes*: UIA programs, including Windows Remote Assistance, automatically disable the secure desktop for elevation prompts. If you don't disable the "User Account Control: Switch to the secure desktop when prompting for elevation" policy setting, the prompts appear on the interactive user's desktop instead of the secure desktop. 
  - *Not Configured*: The secure desktop can be disabled only by the user of the interactive desktop or by disabling the "User Account Control: Switch to the secure desktop when prompting for elevation" policy setting.  

  **Default**: Yes

- **Detect application installations and prompt for elevation**  
  This policy setting controls the behavior of application installation detection for the computer. The options are: 
  - *Enabled*: When an application installation package is detected that requires elevation of privilege, the user is prompted to enter an administrative user name and password. If the user enters valid credentials, the operation continues with the applicable privilege. 
  - *Disabled*: Application installation packages aren't detected and prompted for elevation. Enterprises that are running standard user desktops and use delegated installation technologies such as Group Policy Software Installation or Systems Management Server (SMS) should disable this policy setting. In this case, installer detection is unnecessary.  
  
  **Default**: Yes
  
- **Prevent storing LAN manager hash value on next password change**  
  This security setting determines if, at the next password change, the LAN Manager (LM) hash value for the new password is stored. The LM hash is relatively weak and prone to attack, as compared with the cryptographically stronger Windows NT hash. Since the LM hash is stored on the local computer in the security database the passwords can be compromised if the security database is attacked.
  
  **Default**: Yes

- **Virtualize file and registry write failures to per user locations**  
  This policy setting controls whether application write failures are redirected to defined registry and file system locations. This policy setting mitigates applications that run as administrator and write run-time application data to *%ProgramFiles%*, *%Windir%*, *%Windir%\system32*, or *HKLM\Software*.
  
  **Default**: Yes

## MS Security Guide  
For more information, see [Policy CSP - MSSecurityGuide](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mssecurityguide) in the Windows documentation.  

- **Apply UAC restrictions to local accounts on network logon**  
  **Default**: Enabled
  
- **SMB v1 client driver start configuration**  
  **Default**: Disabled driver
  
- **SMB v1 server**  
  **Default**: Disabled
  
- **Digest authentication**  
  **Default**: Disabled
  
- **Structured exception handling overwrite protection**  
  **Default**: Enabled
  
## MSS Legacy  
For more information, see [Policy CSP - MSSLegacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-msslegacy) in the Windows documentation.  

- **Network IP source routing protection level**  
  **Default**: Highest protection  
  
- **Network ignore NetBIOS name release requests except from WINS servers**  
  **Default**: Enabled
  
- **Network IPv6 source routing protection level**  
  **Default**: Highest protection

- **Network ICMP redirects override OSPF generated**  
  **Default**: Disabled
  
## Power  
For more information, see [Policy CSP - Power](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power) in the Windows documentation.  

- **Require password on wake while plugged in**  
  This policy setting specifies if the user is prompted for a password when the system resumes from sleep. If you enable or don't configure this policy setting, the user is prompted for a password when the system resumes from sleep. If you disable this policy setting, the user isn't prompted for a password when the system resumes from sleep.
  
  **Default**: Enabled
  
- **Standby states when sleeping while on battery**  
  This policy setting manages if Windows can use standby states when putting the computer in a sleep state. If you enable or don't configure this policy setting, Windows uses standby states to put the computer in a sleep state. If you disable this policy setting, standby states (S1-S3) aren't allowed.
  
  **Default**: Disabled
  
- **Standby states when sleeping while plugged in**  
  This policy setting manages if Windows can use standby states when putting the computer in a sleep state. If you enable or don't configure this policy setting, Windows uses standby states to put the computer in a sleep state. If you disable this policy setting, standby states (S1-S3) aren't allowed.
  
  **Default**: Disabled
  
- **Require password on wake while on battery**  
  This policy setting specifies if the user is prompted for a password when the system resumes from sleep. If you enable or don't configure this policy setting, the user is prompted for a password when the system resumes from sleep. If you disable this policy setting, the user isn't prompted for a password when the system resumes from sleep.
  
  **Default**: Enabled
  
## Remote Desktop Services  
For more information, see [Policy CSP - RemoteDesktopServices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotedesktopservices) in the Windows documentation.  

- **Block password saving**  
  Controls whether passwords can be saved on this computer from Remote Desktop Connection. If you enable this setting the password saving checkbox in Remote Desktop Connection is disabled and users won't be able to save passwords. When a user opens an RDP file using Remote Desktop Connection and saves their settings, any password that previously existed in the RDP file are deleted. If you disable this setting or leave it not configured, the user can save passwords using Remote Desktop Connection.
  
   **Default**: Enabled
  
- **Secure RPC communication**  
  Specifies whether a Remote Desktop Session Host server requires secure RPC communication with all clients or allows unsecured communication. You can use this setting to strengthen the security of RPC communication with clients by allowing only authenticated and encrypted requests. If the status is set to Enabled, Remote Desktop Services accepts requests from RPC clients that support secure requests, and doesn't allow unsecured communication with untrusted clients. If the status is set to Disabled, Remote Desktop Services always requests security for all RPC traffic. However, unsecured communication is allowed for RPC clients that don't respond to the request. If the status is set to Not Configured, unsecured communication is allowed. Note: The RPC interface is used for administering and configuring Remote Desktop Services.
  
  **Default**: Enabled
  
- **Block drive redirection**  
  This policy setting specifies whether to prevent the mapping of client drives in a Remote Desktop Services session (drive redirection). By default, an RD Session Host server maps client drives automatically upon connection. Mapped drives appear in the session folder tree in File Explorer or Computer in the format *\<driveletter>* on *\<computername>*. You can use this policy setting to override this behavior. If you enable this policy setting, client drive redirection isn't allowed in Remote Desktop Services sessions, and Clipboard file copy redirection isn't allowed on computers running Windows Server 2003, Windows 8, and Windows XP. If you disable this policy setting, client drive redirection is always allowed. Also, Clipboard file copy redirection is always allowed if Clipboard redirection is allowed. If you don't configure this policy setting, client drive redirection and Clipboard file copy redirection aren't specified at the Group Policy level.
  
  **Default**: Enabled
  
- **Prompt for password upon connection**  
  This policy setting specifies whether Remote Desktop Services always prompts the client for a password upon connection. You can use this setting to enforce a password prompt for users logging on to Remote Desktop Services, even if they already provided the password in the Remote Desktop Connection client. By default, Remote Desktop Services allows users to automatically log on by entering a password in the Remote Desktop Connection client. If you enable this policy setting, users can't automatically log on to Remote Desktop Services by supplying their passwords in the Remote Desktop Connection client. they're prompted for a password to log on. If you disable this policy setting, users can always log on to Remote Desktop Services automatically by supplying their passwords in the Remote Desktop Connection client. If you don't configure this policy setting, automatic logon isn't specified at the Group Policy level. 
  
  **Default**: Enabled
  
- **Remote desktop services client connection encryption level**  
  Specifies whether to require the use of a specific encryption level to secure communications between client computers and RD Session Host servers during Remote Desktop Protocol (RDP) connections. This policy only applies when you're using native RDP encryption. However, native RDP encryption (as opposed to SSL encryption) isn't recommended. This policy doesn't apply to SSL encryption. If you enable this policy setting, all communications between clients and RD Session Host servers during remote connections must use the encryption method specified in this setting. By default, the encryption level is set to High. The following encryption methods are available:  
  - *High*: The High setting encrypts data sent from the client to the server and from the server to the client by using strong 128-bit encryption. Use this encryption level in environments that contain only 128-bit clients (for example, clients that run Remote Desktop Connection). Clients that don't support this encryption level can't connect to RD Session Host servers.  
  - *Client Compatible*: The Client Compatible setting encrypts data sent between the client and the server at the maximum key strength supported by the client. Use this encryption level in environments that include clients that don't support 128-bit encryption.  
  - *Low*: The Low setting encrypts only data sent from the client to the server by using 56-bit encryption.  
  
  If you disable or don't configure this setting, the encryption level to be used for remote connections to RD Session Host servers isn't enforced through Group Policy. Important FIPS compliance can be configured through the System cryptography. Use FIPS-compliant algorithms for encryption, hashing, and signing settings in Group Policy (under Computer Configuration\Windows Settings\Security Settings\Local Policies\Security Options.) The FIPS-compliant setting encrypts and decrypts data sent from the client to the server and from the server to the client, with the Federal Information Processing Standard (FIPS) 140 encryption algorithms, by using Microsoft cryptographic modules. Use this encryption level when communications between clients and RD Session Host servers requires the highest level of encryption.
  
  **Default**: High
  
## Remote Management  
For more information, see [Policy CSP - RemoteManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotemanagement) in the Windows documentation.  

- **Block storing run as credentials**  
  Client basic authentication
  
  **Default**: Enabled
  
- **Basic authentication**  
  This policy setting allows you to manage whether the Windows Remote Management (WinRM) service accepts Basic authentication from a remote client. If you enable this policy setting, the WinRM service accepts Basic authentication from a remote client. If you disable or don't configure this policy setting, the WinRM service doesn't accept Basic authentication from a remote client.
  
  **Default**: Disabled
  
- **Block client digest authentication**  
  This policy setting allows you to manage whether the Windows Remote Management (WinRM) client uses Digest authentication. If you enable this policy setting, the WinRM client doesn't use Digest authentication. If you disable or don't configure this policy setting, the WinRM client uses Digest authentication.
  
  **Default**: Enabled
  
- **Unencrypted traffic**  
  This policy setting allows you to manage whether the Windows Remote Management (WinRM) service sends and receives unencrypted messages over the network. If you enable this policy setting, the WinRM client sends and receives unencrypted messages over the network. If you disable or don't configure this policy setting, the WinRM client sends or receives only encrypted messages over the network.  
  
  **Default**: Disabled
  
- **Client unencrypted traffic**  
  This policy setting allows you to manage whether the Windows Remote Management (WinRM) client sends and receives unencrypted messages over the network. If you enable this policy setting, the WinRM client sends and receives unencrypted messages over the network. If you disable or don't configure this policy setting, the WinRM client sends or receives only encrypted messages over the network.
  
  **Default**: Disabled
  
- **Client basic authentication**  
  This policy setting allows you to manage whether the Windows Remote Management (WinRM) client uses Basic authentication. If you enable this policy setting, the WinRM client uses Basic authentication. If WinRM is configured to use HTTP transport, the user name and password are sent over the network as clear text. If you disable or don't configure this policy setting, the WinRM client doesn't use Basic authentication.
  
  **Default**: Disabled
  

## Remote Procedure Call  
For more information, see [Policy CSP - RemoteProcedureCall](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remoteprocedurecall) in the Windows documentation.  

- **RPC unauthenticated client options**  
  This policy setting controls how the RPC server runtime handles unauthenticated RPC clients connecting to RPC servers. This policy setting impacts all RPC applications. In a domain environment, use this policy setting with caution as it can impact a wide range of functionality including group policy processing itself. Reverting a change to this policy setting can require manual intervention on each affected machine. This policy setting should never be applied to a domain controller. If you disable this policy setting, the RPC server runtime uses the value of "Authenticated" on Windows Client, and the value of "None" on Windows Server versions that support this policy setting. If you don't configure this policy setting, it remains disabled. The RPC server runtime behaves as though it was enabled with the value of "Authenticated" used for Windows Client and the value of "None" used for Server SKUs that support this policy setting. If you enable this policy setting, it directs the RPC server runtime to restrict unauthenticated RPC clients connecting to RPC servers running on a machine. A client is considered an authenticated client if it uses a named pipe to communicate with the server or if it uses RPC Security. RPC Interfaces that have specifically requested to be accessible by unauthenticated clients may be exempt from this restriction, depending on the selected value for this policy setting.  
  - *None* allows all RPC clients to connect to RPC Servers running on the machine on which the policy setting is applied. 
  - *Authenticated* allows only authenticated RPC Clients (per the definition above) to connect to RPC Servers running on the machine on which the policy setting is applied. Exemptions are granted to interfaces that have requested them. 
  - *Authenticated without exceptions* allows only authenticated RPC Clients (per the definition above) to connect to RPC Servers running on the machine on which the policy setting is applied. No exceptions are allowed. Note: This policy setting won't be applied until the system is rebooted.  

  **Default**: Authenticated

## Search 
For more information, see [Policy CSP - Search](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-search) in the Windows documentation.  

- **Disable indexing encrypted items**  
  Allows or disallows the indexing of items. This switch is for the Windows Search Indexer, which controls whether it will index items that are encrypted, such as the Windows Information Protection (WIP) protected files. When the policy is enabled, WIP protected items are indexed and the metadata about them are stored in an unencrypted location. The metadata includes things like file path and date modified. When the policy is disabled, the WIP protected items aren't indexed and don't show up in the results in Cortana or file explorer. There may also be a performance impact on photos and Groove apps if there are many WIP protected media files on the device.
  
**Default**: Yes
  
## Smart Screen  
For more information, see [Policy CSP - SmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen) in the Windows documentation.  

- **Block execution of unverified files**  
  Block user from running unverified files. 
  - *Not Configured* - Employees can ignore SmartScreen warnings and run malicious files. 
  - *Yes* – Employees can't ignore SmartScreen warnings and run malicious files.

  **Default**: Yes

- **Require SmartScreen for apps and files**  
  Allows IT Admins to configure SmartScreen for Windows.

  **Default**: Yes
  
## System  
For more information, see [Policy CSP - System](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system) in the Windows documentation.  

- **System boot start driver initialization**  
  This policy setting allows you to specify which boot-start drivers are initialized based on a classification determined by an Early Launch Antimalware boot-start driver. The Early Launch Antimalware boot-start driver can return the following classifications for each boot-start driver: 
  - *Good*: The driver has been signed and hasn't been tampered with.  
  - *Bad* - The driver has been identified as malware. We recommend that you don't allow known bad drivers to be initialized. 
  - *Bad, but required for boot*: The driver has been identified as malware, but the computer can't successfully boot without loading this driver. 
  - *Unknown* - This driver hasn't been attested to by your malware detection application and hasn't been classified by the Early Launch Antimalware boot-start driver.  

  If you enable this policy setting, you can choose which boot-start drivers to initialize the next time the computer is started. If you disable or don't configure this policy setting, the boot start drivers determined to be Good, Unknown, or Bad but Boot Critical are initialized and the initialization of drivers determined to be Bad is skipped. If your malware detection application doesn't include an Early Launch Antimalware boot-start driver or if your Early Launch Antimalware boot-start driver has been disabled, this setting has no effect and all boot-start drivers are initialized.  
  
  **Default**: Good unknown and bad critical


## Wi-Fi  
For more information, see [Policy CSP - Wifi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi) in the Windows documentation.  

- **Block Internet sharing**  
  Specifies whether internet sharing is possible on the device.  

  **Default**: Yes  

- **Block Automatically connecting to Wi-Fi hotspots**  
  Allow or disallow the device to automatically connect to Wi-Fi hotspots.  

  **Default**: Yes  
  
## Windows Connection Manager  
For more information, see [Policy CSP - WindowsConnectionManager](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsconnectionmanager) in the Windows documentation.  

- **Block connection to non-domain networks**  
  This policy setting prevents computers from connecting to both a domain-based network and a non-domain based network at the same time. If this policy setting is enabled, the computer responds to automatic and manual network connection attempts based on the following circumstances: 
  - Automatic connection attempts When the computer is already connected to a domain-based network, all automatic connection attempts to non-domain networks are blocked. When the computer is already connected to a non-domain based network, automatic connection attempts to domain-based networks are blocked. 
  - Manual connection attempts When the computer is already connected to either a non-domain based network or a domain-based network over media other than Ethernet, and a user attempts to create a manual connection to an additional network in violation of this policy setting, the existing network connection disconnects and the manual connection is allowed. When the computer is already connected to either a non-domain based network or a domain-based network over Ethernet, and a user attempts to create a manual connection to an additional network in violation of this policy setting, the existing Ethernet connection is maintained and the manual connection attempt is blocked.  

  If this policy setting isn't configured or is disabled, computers are allowed to connect simultaneously to both domain and non-domain networks.  

  **Default**: Enabled
  
## Windows Defender  
For more information, see [Policy CSP - Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) in the Windows documentation.  

- **Scan incoming mail messages**  
  Allows or disallows scanning of email.
  
  **Default**: Yes  

- **Office apps launch child process type**  
  Office apps won't be allowed to create child processes. This includes Word, Excel, PowerPoint, OneNote, and Access. This is a typical malware behavior, especially for macro-based attacks that attempt to use Office apps to launch or download malicious executables.
  
  **Default**: Block
  
- **Defender sample submission consent type**  
  Checks for the user consent level in Windows Defender to send data. If the required consent has already been granted, Windows Defender submits them. If not, (and if the user has specified never to ask), the UI is launched to ask for user consent (when Defender/AllowCloudProtection is allowed) before sending data.
  
  **Default**: Send safe samples automatically 
  
- **Signature update interval (in hours)**  
  Defender signature update interval in hours
  
  **Default**: 4
  
- **Script downloaded payload execution type**  
  Defender script downloaded payload execution type
  
  **Default**: Block
  
- **Prevent credential stealing type**  
  Windows Defender Credential Guard uses virtualization-based security to isolate secrets so that only privileged system software can access them. Unauthorized access to these secrets can lead to credential theft attacks, such as Pass-the-Hash or Pass-The-Ticket. Windows Defender Credential Guard prevents these attacks by protecting NTLM password hashes, Kerberos Ticket Granting Tickets, and credentials stored by applications as domain credentials.
  
  **Default**: Enable

- **Email content execution type**  
  This rule blocks the following file types from being run or launched from an email seen in either Microsoft Outlook or webmail (such as Gmail.com or Outlook.com): Executable files (such as .exe, .dll, or .scr) Script files (such as a PowerShell .ps, VisualBasic .vbs, or JavaScript .js file) Script archive files.
  
  **Default**: Block
  
- **Network protection type**  
  This policy allows you to turn on network protection (block/audit) or off in Windows Defender Exploit Guard. Network protection is a feature of Windows Defender Exploit Guard that protects employees using any app from accessing phishing scams, exploit-hosting sites, and malicious content on the Internet. This includes preventing third-party browsers from connecting to dangerous sites. Value type is integer. If you enable this setting, network protection is turned on and employees can't turn it off. Its behavior can be controlled by the following options: Block and Audit. If you enable this policy with the "Block" option, users and apps are blocked from connecting to dangerous domains. You can see this activity in Windows Defender Security Center. If you enable this policy with the "Audit" option, users/apps won't be blocked from connecting to dangerous domains. However, you'll still see this activity in Windows Defender Security Center. If you disable this policy, users/apps won't be blocked from connecting to dangerous domains. You'll not see any network activity in Windows Defender Security Center. If you don't configure this policy, network blocking is disabled by default.
  
  **Default**: Enable
  
- **Defender schedule scan day**  
  Defender schedule scan day.
  
  **Default**: Everyday
  
- **Cloud-delivered protection**  
  To best protect your PC, Windows Defender will send information to Microsoft about any problems it finds. Microsoft will analyze that information, learn more about problems affecting you and other customers, and offer improved solutions.
  
  **Default**:  Yes  

- **Defender potentially unwanted app action**  
  The potentially unwanted application (PUA) protection feature in Windows Defender Antivirus can identify and block PUAs from downloading and installing on endpoints in your network. These applications aren't considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use. PUA can also refer to applications that are considered to have a poor reputation. Typical PUA behavior includes: Various types of software bundling Ad injection into web browsers Driver and registry optimizers that detect issues, request payment to fix the errors, but remain on the endpoint and make no changes or optimizations (also known as "rogue antivirus" programs). These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.  
  
  **Default**: Block  

- **Script obfuscated macro code type**  
  Malware and other threats can attempt to obfuscate or hide their malicious code in some script files. This rule prevents scripts that appear to be obfuscated from running.
  
  **Default**: Block
  
- **Scan removable drives during a full scan**  
  Allows Windows Defender to scan for malicious and unwanted software in removable drives (for example, flash drives) during a full scan. Windows Defender Antivirus scans all files on USB devices before execution.
  
  **Default**: Yes  
  
- **Scan archive files**  
  Defender scan archive files.
  
  **Default**: Yes
  
- **Behavior monitoring**  
  Allows or disallows Windows Defender Behavior Monitoring functionality.Embedded in Windows 10, these sensors collect and process behavioral signals from the operating system and sends this sensor data to your private, isolated, cloud instance of Microsoft Defender ATP.
  
  **Default**: Yes

- **Scan files opened from network folders**  
  If files are read-only, user won't be able to remove any detected malware.
  
  **Default**: Yes

- **Untrusted USB process type**  
  With this rule, admins can prevent unsigned or untrusted executable files from running from USB removable drives, including SD cards.
  
  **Default**: Block
  
- **Office apps other process injection type**  
  Office apps, including Word, Excel, PowerPoint, and OneNote, won't be able to inject code into other processes. This is typically used by malware to run malicious code in an attempt to hide the activity from antivirus scanning engines.
  
  **Default**:  Block
  
- **Office macro code allow Win32 imports type**  
  Malware can use macro code in Office files to import and load Win32 DLLs, which can then be used to make API calls to allow further infection throughout the system. This rule attempts to block Office files that contain macro code that is capable of importing Win32 DLLs. This includes Word, Excel, PowerPoint, and OneNote.
  
  **Default**: Block  
  
- **Defender cloud block level**  
  Defender cloud block level.
  
  **Default**: Not Configured

- **Real-time monitoring**  
  Defender requires real-time monitoring.
  
  **Default**: Yes
  
- **Office apps executable content creation or launch type**  
  This rule targets typical behaviors used by suspicious and malicious add-ons and scripts (extensions) that create or launch executable files. This is a typical malware technique. Extensions are blocked from being used by Office apps. Typically these extensions use the Windows Scripting Host (.wsh files) to run scripts that automate certain tasks or provide user-created add-on features
  
  **Default**: Block

## Windows Ink Workspace  
For more information, see [Policy CSP - WindowsInkWorkspace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace) in the Windows documentation.  

- **Ink Workspace**  
  Specifies whether to allow the user to access the ink workspace. 
  - *Disabled* - access to ink workspace is disabled. The feature is turned off.
  - *Enabled* - The Ink Workspace feature is turned on, but the user can't access it above the lock screen.
  - *Not Configured* - The Ink Workspace feature is turned on, and the user can use it above the lock screen.  

  **Default**: Enabled
 
## Windows PowerShell  
For more information, see [Policy CSP - WindowsPowerShell](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowspowershell) in the Windows documentation.  

- **Power shell shell script block logging**  
  This policy setting enables logging of all PowerShell script input to the Microsoft-Windows-PowerShell/Operational event log. If you enable this policy setting, Windows PowerShell will log the processing of commands, script blocks, functions, and scripts - whether invoked interactively, or through automation. If you disable this policy setting, logging of PowerShell script input is disabled. If you enable the Script Block Invocation Logging, PowerShell additionally logs events when invocation of a command, script block, function, or script starts or stops. Enabling Invocation Logging generates a high volume of event logs. Note: This policy setting exists under both Computer Configuration and User Configuration in the Group Policy Editor. The Computer Configuration policy setting takes precedence over the User Configuration policy setting.
  
  **Default**: Enabled
 

End of PReview baseilne list  -->
