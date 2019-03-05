---
title: Ustawienia punktów odniesienia zabezpieczeń usługi Intune
titleSuffix: Microsoft Intune
description: Ustawienia punktów odniesienia zabezpieczeń systemu Windows obsługiwane przez usługę Intune
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/09/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a2dce0b743cd2944569e19a8106327f6735b1d6b
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57231710"
---
# <a name="windows-security-baseline-settings-for-intune"></a>Ustawienia punktów odniesienia zabezpieczeń usługi Intune  

Zapoznaj się z [ustawieniami punktu odniesienia systemu Windows](security-baselines.md) obsługiwanymi przez usługę Microsoft Intune.  

> [!NOTE]  
> Ustawienia punktu odniesienia zabezpieczeń systemu Windows są dostępne w wersji zapoznawczej. Podczas pracy w wersji zapoznawczej lista dostępnych ustawień oraz kolejność prezentowania tych ustawień zależy od tego, co jest dostępne w portalu.  
>  
> Po przeniesieniu ustawień punktu odniesienia poza wersję zapoznawczą ta zawartość zostanie zaktualizowana z użyciem listy ustawień punktu odniesienia zabezpieczeń obsługiwanych przez usługę Intune stosowanych poza wersją zapoznawczą.  

## <a name="above-lock"></a>Wyłączona blokada  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — AboveLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock) w dokumentacji systemu Windows.  

- **Blokuj wyświetlanie wyskakujących powiadomień**  
  To ustawienie zasad uniemożliwia wyświetlanie powiadomień aplikacji na ekranie blokady. Jeśli to ustawienie zasad zostanie włączone, na ekranie blokady nie będą wyświetlane powiadomienia aplikacji. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownicy będą mogli wybrać aplikacje, których powiadomienia są wyświetlane na ekranie blokady.
  - **Ustawienie domyślne**: Tak  

## <a name="app-runtime"></a>Środowisko uruchomieniowe aplikacji    
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — AppRuntime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-appruntime
) w dokumentacji systemu Windows.  

- **Konta Microsoft opcjonalne dla aplikacji ze Sklepu Windows**  
  To ustawienie zasad umożliwia kontrolowanie, czy konta Microsoft są opcjonalne dla aplikacji ze Sklepu Windows, które wymagają konta do zalogowania. Te zasady dotyczy tylko aplikacji ze Sklepu Windows, które je obsługują. Jeśli to ustawienie zasad zostanie włączone, aplikacje ze Sklepu Windows, które zwykle wymagają konta Microsoft do zalogowania się, umożliwią użytkownikom logowanie się za pomocą konta przedsiębiorstwa. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownicy będą musieli logować się przy użyciu konta Microsoft.  
  - **Ustawienie domyślne**: Enabled  

## <a name="application-management"></a>Zarządzanie aplikacjami   
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — ApplicationManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement) w dokumentacji systemu Windows.  

- **Blokuj DVR z gry (tylko dla komputerów stacjonarnych)**  
  Pozwala określić, czy nagrania i emisje z gier są dozwolone.
  - **Ustawienie domyślne**: Tak  

## <a name="auto-play"></a>Autoodtwarzanie   
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — Autoplay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-autoplay
) w dokumentacji systemu Windows.  

- **Domyślne zachowanie automatycznego uruchamiania funkcji autoodtwarzania**  
  To ustawienie ma wpływ na domyślne zachowanie poleceń Autorun. Polecenia Autorun są przechowywane w plikach autorun.inf i umożliwiają uruchamianie programów instalacyjnych lub innych procedur. Gdy jest ustawiona wartość *Włączone*, administratorzy mogą zmienić domyślne zachowanie automatycznego uruchamiania w urządzeniu z systemem Windows Vista lub nowszym. Możesz ustawić następujące zachowanie: a) całkowite wyłączenie poleceń autorun lub b) przywrócenie zachowania automatycznego wykonywania poleceń autorun z systemów starszych niż Windows Vista. Jeśli ustawisz wartość *Wyłączone* lub *Nie skonfigurowano*, w urządzeniach z systemem Windows Vista lub nowszym użytkownicy otrzymają monit o to, czy polecenia autorun mają być uruchamiane.
  - **Ustawienie domyślne**: Nie wykonuj  
  
- **Tryb autoodtwarzania**  
  To ustawienie zasad umożliwia wyłączenie funkcji autoodtwarzania. Autoodtwarzanie rozpoczyna odczyt z dysku zaraz po włożeniu nośnika do stacji. W rezultacie plik konfiguracji programów i muzyka na nośniku audio są uruchamiane natychmiast. W systemach starszych niż Windows XP z dodatkiem SP2 autoodtwarzanie jest domyślnie wyłączone w przypadku stacji dysków wymiennych, takich jak stacja dyskietek (ale nie stacja CD-ROM), i dysków sieciowych. Począwszy od systemu Windows XP z dodatkiem SP2, autoodtwarzanie jest też włączone dla dysków wymiennych, łącznie ze stacjami Zip i niektórymi urządzeniami pamięci masowej USB. Jeśli to ustawienie zasad zostanie włączone, autoodtwarzanie zostanie wyłączone dla stacji CD-ROM i stacji nośników wymiennych lub wyłączone dla wszystkich stacji. To ustawienie zasad powoduje wyłączenie autoodtwarzania dla dodatkowych typów dysków. To ustawienie nie służy do włączania autoodtwarzania dla dysków, dla których jest ono domyślnie wyłączone. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, autoodtwarzanie zostanie włączone. Uwaga: to ustawienie zasad jest dostępne w folderach konfiguracji komputera i konfiguracji użytkownika. Jeśli ustawienia zasad powodują konflikt, ustawienie zasad w konfiguracji komputera ma pierwszeństwo przed ustawieniem zasad w konfiguracji użytkownika.
  - **Ustawienie domyślne**: Wyłącz

- **Blokuj autoodtwarzanie w urządzeniach niezawierających woluminów**  
  To ustawienie zasad blokuje autoodtwarzanie w urządzeniach MTP, takich jak aparaty fotograficzne i telefony. Jeśli to ustawienie zasad zostanie włączone, autoodtwarzanie nie będzie dozwolone w urządzeniach MTP, takich jak aparaty fotograficzne i telefony. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, autoodtwarzanie zostanie włączone w urządzeniach niezawierających woluminów.
  - **Ustawienie domyślne**: Enabled  

## <a name="bitlocker"></a>Bitlocker    
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — Bitlocker](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bitlocker
) w dokumentacji systemu Windows.  

- **Zasady dysków wymiennych funkcji BitLocker**  
  To ustawienie zasad pozwala określić metodę i siłę szyfrowania. Wartości tych zasad określają siłę szyfrowania funkcji BitLocker. Przedsiębiorstwa mogą kontrolować poziom szyfrowania w celu zwiększenia bezpieczeństwa (szyfrowanie AES-256 jest silniejsze niż szyfrowanie AES-128). Jeśli to ustawienie zostanie włączone, będzie można skonfigurować algorytm szyfrowania i siłę klucza szyfrowania osobno dla stałych dysków danych, dysków systemu operacyjnego i wymiennych dysków danych. W przypadku dysków stałych i dysków systemu operacyjnego zalecamy użycie algorytmu XTS-AES. W przypadku dysków wymiennych użyj 128-bitowego lub 256-bitowego szyfrowania AES-CBC, jeśli dysk będzie używany w innych urządzeniach, które nie mają systemu Windows 10 w wersji 1511 lub nowszej. Metoda szyfrowania nie zmienia się, jeśli dysk jest już zaszyfrowany lub jeśli szyfrowanie jest w toku. W takich przypadkach to ustawienie zasad jest ignorowane.

    - **Wymagaj szyfrowania do zapisu**
      - **Ustawienie domyślne**: Tak  

    - **Metoda szyfrowania**
      - **Ustawienie domyślne**: 256-bitowe szyfrowanie AES CBC  

- **Zasady dysków stałych funkcji BitLocker**  
  To ustawienie zasad pozwala określić metodę i siłę szyfrowania. Wartości tych zasad określają siłę szyfrowania funkcji BitLocker. Przedsiębiorstwa mogą kontrolować poziom szyfrowania w celu zwiększenia bezpieczeństwa (szyfrowanie AES-256 jest silniejsze niż szyfrowanie AES-128). Jeśli to ustawienie zostanie włączone, będzie można skonfigurować algorytm szyfrowania i siłę klucza szyfrowania osobno dla stałych dysków danych, dysków systemu operacyjnego i wymiennych dysków danych. W przypadku dysków stałych i dysków systemu operacyjnego zalecamy użycie algorytmu XTS-AES. W przypadku dysków wymiennych użyj 128-bitowego lub 256-bitowego szyfrowania AES-CBC, jeśli dysk będzie używany w innych urządzeniach, które nie mają systemu Windows 10 w wersji 1511 lub nowszej. Metoda szyfrowania nie zmienia się, jeśli dysk jest już zaszyfrowany lub jeśli szyfrowanie jest w toku. W takich przypadkach to ustawienie zasad jest ignorowane.  
 
  - **Metoda szyfrowania**
    - **Ustawienie domyślne**: 256-bitowe szyfrowanie AES XTS  

- **Zasady dysków systemowych funkcji BitLocker**  
  To ustawienie zasad pozwala określić metodę i siłę szyfrowania. Wartości tych zasad określają siłę szyfrowania funkcji BitLocker. Przedsiębiorstwa mogą kontrolować poziom szyfrowania w celu zwiększenia bezpieczeństwa (szyfrowanie AES-256 jest silniejsze niż szyfrowanie AES-128). Jeśli to ustawienie zostanie włączone, będzie można skonfigurować algorytm szyfrowania i siłę klucza szyfrowania osobno dla stałych dysków danych, dysków systemu operacyjnego i wymiennych dysków danych. W przypadku dysków stałych i dysków systemu operacyjnego zalecamy użycie algorytmu XTS-AES. W przypadku dysków wymiennych użyj 128-bitowego lub 256-bitowego szyfrowania AES-CBC, jeśli dysk będzie używany w innych urządzeniach, które nie mają systemu Windows 10 w wersji 1511 lub nowszej. Metoda szyfrowania nie zmienia się, jeśli dysk jest już zaszyfrowany lub jeśli szyfrowanie jest w toku. W takich przypadkach to ustawienie zasad jest ignorowane.  

  - **Metoda szyfrowania**  
    - **Ustawienie domyślne**: 256-bitowe szyfrowanie AES XTS  

## <a name="browser"></a>Przeglądarka  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — przeglądarka](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser) w dokumentacji systemu Windows.  

- **Wymagaj filtra SmartScreen dla programu Microsoft Edge**  
  Program Microsoft Edge domyślnie używa filtra SmartScreen w usłudze Windows Defender, aby chronić użytkowników przed potencjalnym wyłudzeniem informacji i złośliwym oprogramowaniem. Ponadto domyślnie użytkownicy nie mogą wyłączyć filtra SmartScreen w usłudze Windows Defender. Włączenie tych zasad powoduje wyłączenie filtra SmartScreen w usłudze Windows Defender i uniemożliwia użytkownikom włączenie go. Nie konfiguruj tych zasad, aby umożliwić użytkownikom wybór, czy filtr SmartScreen w usłudze Windows Defender ma być włączony.  
  - **Ustawienie domyślne**: Tak  
  
- **Blokuj dostęp do złośliwych witryn**  
  Domyślnie program Microsoft Edge pozwala użytkownikom pomijać (ignorować) ostrzeżenia filtru SmartScreen w usłudze Windows Defender dotyczące potencjalnie złośliwych witryn, dzięki czemu mogą kontynuować korzystanie z witryny. Jednak za pomocą tych zasad można skonfigurować program Microsoft Edge, aby uniemożliwiał użytkownikom pomijanie ostrzeżeń i dalsze korzystanie z witryny.
  - **Ustawienie domyślne**: Tak  
  
- **Blokowanie pobierania niezweryfikowanych plików**  </br>
  Domyślnie program Microsoft Edge pozwala użytkownikom pomijać (ignorować) ostrzeżenia filtru SmartScreen w usłudze Windows Defender dotyczące potencjalnie złośliwych plików, dzięki czemu mogą kontynuować pobieranie niezweryfikowanych plików. Włączenie tych zasad uniemożliwia użytkownikom pomijanie ostrzeżeń, przez co nie mogą pobierać niezweryfikowanych plików.
  - **Ustawienie domyślne**: Tak  
  
- **Blokuj menedżera haseł**  </br>
  Domyślnie program Microsoft Edge automatycznie używa menedżera haseł, co pozwala użytkownikom zarządzać hasłami lokalnie. Wyłączenie tych zasad ogranicza używanie menedżera haseł przez program Microsoft Edge. Nie konfiguruj tych zasad, jeśli chcesz, aby użytkownicy mogli zapisywać hasła i zarządzać nimi lokalnie przy użyciu menedżera haseł.
  - **Ustawienie domyślne**: Tak  
  
- **Uniemożliwiaj przesłonięcia błędów certyfikatu**  </br>
  To ustawienie zasad uniemożliwia użytkownikowi ignorowanie błędów certyfikatu Secure Sockets Layer/Transport Layer Security (SSL/TLS), które przerywają przeglądanie (na przykład błędy z powodu wygaśnięcia, odwołania lub niezgodności nazwy) w programie Internet Explorer. Jeśli to ustawienie zasad zostanie włączone, użytkownik nie będzie mógł kontynuować przeglądania. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownik będzie mógł ignorować błędy certyfikatu i kontynuować przeglądanie.
  - **Ustawienie domyślne**: Tak  

## <a name="connectivity"></a>Łączność  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — łączność](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity) w dokumentacji systemu Windows.  

- **Blokuj pobieranie internetowe przez Kreatora publikacji internetowej i Kreatora zamawiania online**  
  To ustawienie zasad określa, czy system Windows ma pobierać listę dostawców dla Kreatora publikacji internetowej i Kreatora zamawiania online. Te kreatory pozwalają użytkownikom wybrać z listy firmę, która świadczy takie usługi jak magazyn online i drukowanie zdjęć. Domyślnie oprócz dostawców określonych w rejestrze w systemie Windows jest także wyświetlana lista dostawców pobrana z witryny internetowej systemu Windows. Włączenie tego ustawienia zasad spowoduje, że system Windows nie będzie pobierać listy dostawców i będą wyświetlani tylko dostawcy usług zapisywani w pamięci podręcznej w rejestrze lokalnym. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, lista dostawców zostanie pobrana po użyciu przez użytkownika Kreatora publikacji internetowej lub Kreatora zamawiania online. Więcej informacji, w tym szczegółowe informacje na temat określania dostawców usług w rejestrze, można znaleźć w dokumentacji Kreatora publikacji internetowej i Kreatora zamawiania online.  
  - **Ustawienie domyślne**: Enabled  

- **Blokuj pobieranie sterowników wydruku przez HTTP**  
  To ustawienie zasad określa, czy zezwalać temu klientowi na pobieranie pakietów sterowników wydruku przez HTTP. Aby skonfigurować drukowanie HTTP, należy pobrać przez HTTP sterowniki inne niż te, które były dostarczone z systemem. Uwaga: to ustawienie zasad nie blokuje klientowi możliwości drukowania za pomocą drukarek w intranecie lub Internecie przez HTTP. Uniemożliwia tylko pobieranie sterowników, które nie są już zainstalowane lokalnie. Jeśli to ustawienie zasad zostanie włączone, nie będzie można pobierać sterowników drukarek przez HTTP. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownicy będą mogli pobierać sterowniki drukarek przez HTTP.
  - **Ustawienie domyślne**: Enabled  

## <a name="credentials-delegation"></a>Delegowanie poświadczeń  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — CredentialsDelegation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsdelegation
) w dokumentacji systemu Windows.  

- **Delegowanie zdalnego hosta poświadczeń bez możliwości eksportowania**  
  Host zdalny umożliwia delegowanie poświadczeń, których nie można eksportować. Gdy używasz delegowania poświadczeń, urządzenia dostarczają do hosta zdalnego poświadczenia w wersji, którą można eksportować. Naraża to użytkowników na kradzież poświadczeń przed osoby atakujące na hoście zdalnym. Jeśli to ustawienie zasad zostanie włączone, host będzie obsługiwać tryb administratora z ograniczonym dostępem lub tryb zdalnej funkcji Credential Guard. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, tryb administratora z ograniczonym dostępem i tryb zdalnej funkcji Credential Guard nie będą obsługiwane. Użytkownik zawsze będzie musiał przekazywać poświadczenia do hosta.  

  - **Ustawienie domyślne**: Enabled  

## <a name="credentials-ui"></a>Interfejs użytkownika poświadczeń  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — CredentialsUI](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsui) w dokumentacji systemu Windows.  

- **Wyliczanie administratorów**    
  To ustawienie zasad określa, czy podczas próby podniesienia poziomu uruchomionej aplikacji przez użytkownika mają być wyświetlane konta administratorów. Domyślnie podczas próby podniesienia poziomu uruchomionej aplikacji przez użytkownika konta administratorów nie są wyświetlane. Jeśli to ustawienie zasad zostanie włączone, wszystkie konta administratorów lokalnych na komputerze będą wyświetlane, dzięki czemu użytkownik może wybrać jedno z nich i wprowadzić poprawne hasło. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy będą zawsze musieli wpisać nazwę użytkownika i hasło, aby podnieść poziom.  

  - **Ustawienie domyślne**: Wyłącz  

## <a name="data-protection"></a>Ochrona danych  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — DataProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection
) w dokumentacji systemu Windows.  

- **Blokuj bezpośredni dostęp do pamięci**   
  To ustawienie zasad umożliwia zablokowanie bezpośredniego dostępu do pamięci dla wszystkich podrzędnych portów PCI z możliwością podłączenia podczas pracy, dopóki użytkownik nie zaloguje się do systemu Windows. Po zalogowaniu się przez użytkownika system Windows wyliczy urządzenia PCI podłączone do portów PCI podłączenia hosta. Za każdym razem, gdy użytkownik zablokuje maszynę, bezpośredni dostęp do pamięci zostanie zablokowany na portach PCI z możliwością podłączenia podczas pracy bez urządzeń podrzędnych, dopóki użytkownik nie zaloguje się ponownie. Urządzenia, które były już wyliczone po odblokowaniu maszyny, będą w dalszym ciągu działać do czasu odłączenia. To ustawienie zasad jest wymuszane tylko wtedy, gdy jest włączone szyfrowanie funkcją BitLocker lub szyfrowanie urządzenia.
  
  - **Ustawienie domyślne**: Tak  

## <a name="device-guard"></a>Device Guard  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — DeviceGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceguard
) w dokumentacji systemu Windows.  

- **Credential Guard**  
  To ustawienie umożliwia użytkownikom włączenie funkcji Credential Guard z zabezpieczeniami opartymi na wirtualizacji, aby pomóc chronić poświadczenia przy następnym ponownym uruchomieniu.
  
  - **Ustawienie domyślne**: Włącz z blokadą UEFI 

- **Włącz zabezpieczenia oparte na wirtualizacji**  </br>
  Włącza zabezpieczenia oparte na wirtualizacji (VBS) podczas następnego rozruchu. Zabezpieczenia oparte na wirtualizacji używają funkcji Hypervisor systemu Windows, aby zapewniać obsługę usług zabezpieczeń.
  - **Ustawienie domyślne**: Tak  

<!-- not yet available 
- **Enable secure boot with DMA**  
  Among the commands that follow, you can choose settings for Secure Boot and Secure Boot with DMA. In most situations, we recommend that you choose Secure Boot. This option provides Secure Boot with as much protection as is supported by a given computer’s hardware. A computer with input/output memory management units (IOMMUs) will have Secure Boot with DMA protection. A computer without IOMMUs will simply have Secure Boot enabled. In contrast, with Secure Boot with DMA, the setting will enable Secure Boot—and VBS itself—only on a computer that supports DMA, that is, a computer with IOMMUs. With this setting, any computer without IOMMUs will not have VBS or HVCI protection, although it can still have WDAC enabled.
  
  - **Default**: Yes  
  -->
- **Uruchom ochronę systemu**  
  - **Ustawienie domyślne**: Enabled  

## <a name="device-installation"></a>Instalacja urządzenia  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — DeviceInstallation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation) w dokumentacji systemu Windows.  

- **Instalacja urządzeń sprzętowych według identyfikatorów urządzeń**  
  To ustawienie zasad umożliwia określenie listy identyfikatorów sprzętu Plug and Play i zgodnych identyfikatorów urządzeń, których nie można zainstalować w systemie Windows. To ustawienie zasad ma pierwszeństwo przed innymi ustawieniami zasad, które umożliwiają zainstalowanie urządzenia w systemie Windows. Jeśli to ustawienie zasad zostanie włączone, system Windows nie będzie mógł zainstalować urządzenia, którego identyfikator sprzętu lub zgodny identyfikator jest na utworzonej przez Ciebie liście. Jeśli włączysz to ustawienie zasad na serwerze usług pulpitu zdalnego, będzie ono wpływać na przekierowywanie określonych urządzeń z klienta usług pulpitu zdalnego na serwer usług pulpitu zdalnego. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, urządzenia będzie można instalować i aktualizować zgodnie z innymi ustawieniami zasad.
  - **Ustawienie domyślne**: Blokuj instalację urządzeń sprzętowych  
  
    - **Usuń zgodne urządzenia sprzętowe**  
      To ustawienie jest dostępne tylko wtedy, gdy ustawienie *Instalacja urządzeń sprzętowych według identyfikatorów urządzeń* ma wartość *Blokuj instalację urządzeń sprzętowych*.
      - **Ustawienie domyślne**: Tak
  
    - **Zablokowane identyfikatory urządzeń sprzętowych**  </br>
      To ustawienie jest dostępne tylko wtedy, gdy ustawienie *Instalacja urządzeń sprzętowych według identyfikatorów urządzeń* ma wartość *Blokuj instalację urządzeń sprzętowych*.
      - **Ustawienie domyślne**: Tak  
  
- **Instalacja urządzeń sprzętowych według klas konfiguracji**  
  To ustawienie zasad umożliwia określenie listy unikatowych identyfikatorów globalnych (GUID) klas konfiguracji urządzeń dla sterowników urządzeń, których nie można zainstalować w systemie Windows. To ustawienie zasad ma pierwszeństwo przed innymi ustawieniami zasad, które umożliwiają zainstalowanie urządzenia w systemie Windows. Jeśli to ustawienie zasad zostanie włączone, system Windows nie będzie mógł instalować ani aktualizować sterowników urządzeń, których identyfikatory GUID klas konfiguracji urządzeń są na utworzonej przez Ciebie liście. Jeśli włączysz to ustawienie zasad na serwerze usług pulpitu zdalnego, będzie ono wpływać na przekierowywanie określonych urządzeń z klienta usług pulpitu zdalnego na serwer usług pulpitu zdalnego. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, system Windows będzie mógł instalować i aktualizować urządzenia zgodnie z innymi ustawieniami zasad.
  - **Ustawienie domyślne**: Blokuj instalację urządzeń sprzętowych  
  
    - **Usuń zgodne urządzenia sprzętowe**  </br>
      To ustawienie jest dostępne tylko wtedy, gdy ustawienie *Instalacja urządzeń sprzętowych według klas konfiguracji* ma wartość *Blokuj instalację urządzeń sprzętowych*.
      - **Ustawienie domyślne**: *Brak konfiguracji domyślnej*  
  
    - **Zablokowane identyfikatory urządzeń sprzętowych**  </br>
      To ustawienie jest dostępne tylko wtedy, gdy ustawienie *Instalacja urządzeń sprzętowych według klas konfiguracji* ma wartość *Blokuj instalację urządzeń sprzętowych*.
      - **Ustawienie domyślne**: *Brak konfiguracji domyślnej*  

## <a name="device-lock"></a>Blokada urządzenia  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — DeviceLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock) w dokumentacji systemu Windows.  

- **Uniemożliwiaj używanie aparatu fotograficznego**  
  Wyłącza przełącznik aparatu na ekranie blokady w ustawieniach komputera i uniemożliwia wywoływanie aparatu na ekranie blokady. Domyślnie użytkownicy mogą włączyć wywoływanie dostępnego aparatu na ekranie blokady. Jeśli to ustawienie zostanie włączone, użytkownicy nie będą mogli włączyć ani wyłączyć dostępu do aparatu na ekranie blokady w ustawieniach komputera i nie będzie można wywołać aparatu na ekranie blokady.  
  - **Ustawienie domyślne**: Enabled  

- **Wymagaj hasła**  
  Określa, czy blokada urządzenia jest włączona.
  - **Ustawienie domyślne**: Tak  
  
  - **Minimalna liczba zestawów znaków hasła**  
    Liczba typów elementów (dużych i małych liter, liczb oraz znaków interpunkcyjnych) wymaganych do uznania hasła lub numeru PIN za silne. Numer PIN wymusza na następujące zachowanie w komputerze i urządzeniach przenośnych: 1 — Tylko cyfry 2 — Cyfry i małe litery są wymagane 3 — Cyfry, małe i wielkie litery są wymagane. Nie jest obsługiwane przez klasyczne konta Microsoft i konta domen. 4 — Cyfry, małe i wielkie litery oraz znaki specjalne są wymagane. Nieobsługiwane w wersji klasycznej. Wartość domyślna to 1. 
    - **Ustawienie domyślne**: 3  
  
  - **Liczba logowań zakończonych niepowodzeniem przed wyczyszczeniem urządzenia**  
    Liczba dozwolonych błędów uwierzytelniania przed wyczyszczeniem urządzenia. Wartość 0 powoduje wyłączenie funkcji czyszczenia urządzenia.
    - **Ustawienie domyślne**: 10  
  
  - **Dni do wygaśnięcia hasła**  
    Ustawienie zasad maksymalnego wieku hasła określa czas (w dniach), przez który można używać hasła, zanim system będzie wymagać od użytkownika zmiany hasła. Możesz ustawić, aby hasła wygasały po pewnej liczbie dni (od 1 do 999), lub aby nigdy nie wygasały (ustawienie 0 dni). Jeśli maksymalny wiek hasła wynosi od 1 do 999 dni, minimalny wiek hasła musi być mniejszy niż maksymalny wiek hasła. Jeśli maksymalny wiek hasła jest równy 0, minimalny wiek hasła może być dowolną wartością od 0 do 998 dni.
    - **Ustawienie domyślne**: 60  
  
  - **Wymagany typ hasła**  
    Określa wymagany typ numeru PIN lub hasła.
    - **Ustawienie domyślne**: Alfanumeryczne  
  
  - **Minimalna długość hasła**  
    Ustawienie zasad minimalnej długości hasła określa najmniejszą dozwoloną liczbę znaków hasła konta użytkownika. Możesz ustawić wartość z zakresu od 1 do 14 znaków lub określić, że hasło nie jest wymagane, przez ustawienie wartości 0 znaków.
    - **Ustawienie domyślne**: 8  
  
  - **Blokuj proste hasła**  
    Określa, czy dozwolone są numery PIN i hasła, takie jak „1111” lub „1234”. W wersji klasycznej steruje również użyciem haseł obrazkowych.
    - **Ustawienie domyślne**: Tak  
       *Ustawienie Tak uniemożliwia używanie prostych haseł.* 

  - **Zapobiegaj ponownemu używaniu poprzednich haseł**  
    Określa, ile haseł, których nie można użyć, ma być przechowywanych w historii. Wartość zawiera bieżące hasło użytkownika. Oznacza to, że w przypadku ustawienia 1 użytkownik nie może ponownie użyć bieżącego hasła podczas wybierania nowego hasła, natomiast ustawienie *5* oznacza, że użytkownik nie może jako nowego hasła ustawić bieżącego hasła ani poprzednich czterech haseł.
    - **Ustawienie domyślne**: 24  

- **Blokuj pokaz slajdów**  
  Wyłącza ustawienia pokazu slajdów na ekranie blokady w ustawieniach komputera i uniemożliwia odtwarzanie pokazu slajdów na ekranie blokady. Domyślnie użytkownicy mogą włączyć pokaz slajdów, który będzie uruchamiany po zablokowaniu maszyny. Jeśli to ustawienie zostanie włączone, użytkownicy nie będą już mogli modyfikować ustawień pokazu slajdów w ustawieniach komputera i nigdy nie zostanie uruchomiony żaden pokaz slajdów.
  - **Ustawienie domyślne**: Enabled  
    *Ustawienie Włączone uniemożliwia uruchamianie pokazów slajdów.* 

- **Minimalny wiek hasła w dniach**  
  Ustawienie zasad minimalnego wieku hasła określa czas (w dniach), przez który trzeba używać hasła, zanim będzie możliwa zmiana hasła. Możesz ustawić wartość z zakresu od 1 do 998 dni lub umożliwić zmianę hasła od razu przez ustawienie 0 dni. Minimalny wiek hasła musi być mniejszy niż maksymalny wiek hasła, chyba że maksymalny wiek hasła jest równy 0, co oznacza, że hasła nigdy nie wygasają. Jeśli maksymalny wiek hasła jest równy 0, minimalny wiek hasła może być dowolną wartością od 0 do 998.
  - **Ustawienie domyślne**: 1  

## <a name="event-log-service"></a>Usługa dziennika zdarzeń  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — EventLogService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-eventlogservice) w dokumentacji systemu Windows.  

- **Maksymalny rozmiar pliku dziennika zabezpieczeń w KB**  
  To ustawienie zasad określa maksymalny rozmiar pliku dziennika w kilobajtach. Jeśli to ustawienie zasad zostanie włączone, będzie można skonfigurować maksymalny rozmiar pliku dziennika od 1 megabajta (1024 kilobajtów) do 2 terabajtów (2147483647 kilobajtów) w kilobajtowych przyrostach. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, jako maksymalny rozmiar pliku dziennika zostanie ustawiona lokalnie skonfigurowana wartość. Tę wartość może zmienić administrator lokalny w oknie dialogowym Właściwości dziennika — wartość domyślna to 20 megabajtów.
  - **Ustawienie domyślne**: 196608  

- **Maksymalny rozmiar pliku dziennika systemu w KB**  
  To ustawienie zasad określa maksymalny rozmiar pliku dziennika w kilobajtach. Jeśli to ustawienie zasad zostanie włączone, będzie można skonfigurować maksymalny rozmiar pliku dziennika od 1 megabajta (1024 kilobajtów) do 2 terabajtów (2147483647 kilobajtów) w kilobajtowych przyrostach. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, jako maksymalny rozmiar pliku dziennika zostanie ustawiona lokalnie skonfigurowana wartość. Tę wartość może zmienić administrator lokalny w oknie dialogowym Właściwości dziennika — wartość domyślna to 20 megabajtów.
  - **Ustawienie domyślne**: 32768  

- **Maksymalny rozmiar pliku dziennika aplikacji w KB**  
  To ustawienie zasad określa maksymalny rozmiar pliku dziennika w kilobajtach. Jeśli to ustawienie zasad zostanie włączone, będzie można skonfigurować maksymalny rozmiar pliku dziennika od 1 megabajta (1024 kilobajtów) do 2 terabajtów (2147483647 kilobajtów) w kilobajtowych przyrostach. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, jako maksymalny rozmiar pliku dziennika zostanie ustawiona lokalnie skonfigurowana wartość. Tę wartość może zmienić administrator lokalny w oknie dialogowym Właściwości dziennika — wartość domyślna to 20 megabajtów.
  - **Ustawienie domyślne**: 32768  

## <a name="experience"></a>Środowisko użytkownika  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — środowisko](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience) w dokumentacji systemu Windows.  

- **Blokuj funkcję W centrum uwagi Windows**  
  Umożliwia administratorom IT wyłączenie wszystkich funkcji W centrum uwagi Windows — W centrum uwagi Windows na ekranie blokady, porad dotyczących systemu Windows, funkcji firmy Microsoft dla konsumentów i innych powiązanych funkcji.
  - **Ustawienie domyślne**: Tak  
  
  - **Blokuj sugestie innych firm w funkcji W centrum uwagi Windows**  
    Określa, czy zezwalać na sugestie dotyczące aplikacji i zawartości pochodzące od innych wydawców oprogramowania w funkcjach W centrum uwagi Windows, takich jak W centrum uwagi na ekranie blokady, sugerowane aplikacje w menu Start i porady dotyczące systemu Windows. Użytkownicy mogą nadal otrzymywać sugestie dotyczące funkcji, aplikacji i usług firmy Microsoft.
     - **Ustawienie domyślne**: Tak  
  - **Blokuj funkcje dla konsumentów**  
    Umożliwia administratorom IT włączanie funkcji przeznaczonych zwykle tylko dla konsumentów, takich jak sugestie w menu Start, powiadomienia dotyczące członkostwa, instalacja aplikacji po uruchomieniu środowiska OOBE i kafelki przekierowania.
    - **Ustawienie domyślne**: Tak  


## <a name="exploit-guard"></a>Exploit Guard  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — ExploitGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-exploitguard) w dokumentacji systemu Windows.  

- **Plik XML ochrony przed programami wykorzystującymi luki w zabezpieczeniach**  
  Umożliwia administratorowi IT wypchnięcie konfiguracji reprezentującej środki zaradcze dla żądanego systemu i żądanej aplikacji do wszystkich urządzeń w organizacji. Konfiguracja jest reprezentowana przez kod XML. Ochrona przed programami wykorzystującymi luki w zabezpieczeniach pomaga chronić urządzenia przed złośliwym oprogramowaniem, które rozpowszechnia się i infekuje za pomocą programów wykorzystujących luki w zabezpieczeniach. Aby utworzyć zestaw środków zaradczych (nazywanych konfiguracją), użyj aplikacji zabezpieczeń systemu Windows lub programu PowerShell. Możesz następnie wyeksportować tę konfigurację w pliku XML i udostępnić ją w wielu maszynach w sieci, aby wszystkie z nich korzystały z tego samego zestawu ustawień ograniczania ryzyka. Możesz też przekonwertować i zaimportować istniejący plik XML konfiguracji EMET do pliku XML konfiguracji ochrony.
  - **Ustawienie domyślne**: *Podano przykładowy plik XML* 
 
## <a name="file-explorer"></a>Eksplorator plików  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — FileExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-fileexplorer) w dokumentacji systemu Windows.  

- **Blokuj zapobieganie wykonywaniu danych**  
  Wyłączenie zapobiegania wykonywaniu danych umożliwia niektórym starszym aplikacjom wtyczek działanie bez zamykania Eksploratora.
  - **Ustawienie domyślne**: Wyłącz  
   
- **Blokuj zakończenie sterty w przypadku uszkodzenia**  
  Wyłączenie zakończenia sterty w przypadku uszkodzenia umożliwia niektórym starszym aplikacjom wtyczek działanie bez natychmiastowego zamykania Eksploratora, mimo że Eksplorator może nadal nieoczekiwane zakończyć działanie później.
  - **Ustawienie domyślne**: Wyłącz  
    

## <a name="internet-explorer"></a>Internet Explorer  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — InternetExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-internetexplorer) w dokumentacji systemu Windows.  
<!-- not yet available 
- **Scan incoming mail messages**  
  Allows or disallows scanning of email.
  - **Default**: Disabled  
  
- **Office apps launch child process type**  
  Office apps will not be allowed to create child processes. This includes Word, Excel, PowerPoint, OneNote, and Access. This is a typical malware behavior, especially for macro-based attacks that attempt to use Office apps to launch or download malicious executables.
  - **Default**: Disable  
  
- **Defender sample submission consent type**  
  Checks for the user consent level in Windows Defender to send data. If the required consent has already been granted, Windows Defender submits them. If not (and if the user has specified never to ask), the UI is launched to ask for user consent (when Defender/AllowCloudProtection is allowed) before sending data.
  - **Default**: Disable  
  
- **Signature update interval (in hours)**  
  Defender signature update interval in hours
  - **Default**: Disabled  
 -->
- **Dostęp strefy internetowej w programie Internet Explorer do źródeł danych**  
  To ustawienie zasad umożliwia zarządzanie tym, czy program Internet Explorer może uzyskiwać dostęp do danych z innej strefy zabezpieczeń przy użyciu programu Microsoft XML Parser (MSXML) lub ActiveX Data Objects (ADO). Jeśli to ustawienie zasad zostanie włączone, użytkownicy będą mogli załadować stronę w strefie używającej programu MSXML lub ADO w celu uzyskania dostępu do danych z innej witryny w strefie. Jeśli w polu listy rozwijanej zostanie wybrana pozycja Monituj, użytkownicy będą proszeni o wybranie, czy zezwolić na załadowanie strony w strefie używającej programu MSXML lub ADO w celu uzyskania dostępu do danych z innej witryny w strefie. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli załadować strony w strefie używającej programu MSXML lub ADO w celu uzyskania dostępu do danych z innej witryny w strefie. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy nie będą mogli załadować strony w strefie używającej programu MSXML lub ADO w celu uzyskania dostępu do danych z innej witryny w strefie.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Przeciąganie zawartości z innych domen w systemie Windows w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia ustawianie opcji przeciągania zawartości z między domenami, gdy źródło i lokalizacja docelowa znajdują się w tym samym oknie. Jeśli to ustawienie zasad zostanie włączone i klikniesz pozycję Włącz, użytkownicy będą mogli przeciągać zawartość między domenami, gdy źródło i lokalizacja docelowa znajdują się w tym samym oknie. Użytkownicy nie mogą zmieniać tego ustawienia. Jeśli to ustawienie zasad zostanie włączone i klikniesz pozycję Wyłącz, użytkownicy nie będą mogli przeciągać zawartość między domenami, gdy źródło i lokalizacja docelowa znajdują się w tym samym oknie. Użytkownicy nie mogą zmieniać tego ustawienia w oknie dialogowym Opcje internetowe. W programie Internet Explorer 10, jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownicy nie będą mogli przeciągać zawartości między domenami, gdy źródło i lokalizacja docelowa znajdują się w tym samym oknie. Użytkownicy mogą zmieniać to ustawienie w oknie dialogowym Opcje internetowe. W programie Internet Explorer 9 lub starszym, jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownicy nie będą mogli przeciągać zawartości między domenami, gdy źródło i lokalizacja docelowa znajdują się w tym samym oknie. Użytkownicy nie mogą zmieniać tego ustawienia w oknie dialogowym Opcje internetowe.
  - **Ustawienie domyślne**: Wyłącz
  
- **Ostrzeżenie o niezgodności adresu certyfikatu programu Internet Explorer**  
  To ustawienie zasad umożliwia włączenie ostrzeżenia o zabezpieczeniach dotyczącego niezgodności adresu certyfikatu. Gdy to ustawienie zasad zostanie włączone, użytkownik otrzyma ostrzeżenie podczas odwiedzania witryn bezpiecznego protokołu HTTP (HTTPS), które przedstawiają certyfikaty wystawione dla adresu innej witryny. To ostrzeżenie pomaga zapobiegać atakom metodą fałszowania. Jeśli to ustawienie zasad zostanie włączone, ostrzeżenie o niezgodności adresu certyfikatu będzie zawsze wyświetlane. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownik będzie mógł wybrać, czy ostrzeżenie o niezgodności adresu certyfikatu ma być wyświetlane (na stronie Zaawansowane w internetowym panelu sterowania).
  - **Ustawienie domyślne**: Enabled 
  
- **Mniej uprzywilejowane witryny w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad pozwala określić, czy witryny internetowe z mniej uprzywilejowanych stref, takie jak witryny internetowe, mogą prowadzić do tej strefy. Jeśli to ustawienie zasad zostanie włączone, witryny z mniej uprzywilejowanych stref będą mogły otwierać nowe okna w tej strefie. Strefa zabezpieczeń będzie działać bez dodatkowej warstwy zabezpieczeń, które są udostępniane przez funkcję zabezpieczeń do ochrony z poziomu podniesienia uprawnień strefy. Jeśli w polu listy rozwijanej wybierzesz wartość Monituj, użytkownik otrzyma ostrzeżenie o potencjalnie ryzykownej nawigacji. Jeśli to ustawienie zasad zostanie wyłączone, potencjalnie szkodliwe nawigacje będą blokowane. Funkcja zabezpieczeń programu Internet Explorer będzie włączona w tej strefie zgodnie z ustawieniem kontroli funkcji ochrony z poziomu podniesienia uprawnień strefy. Jeśli to ustawienie zasad nie zostanie skonfigurowane, potencjalnie szkodliwe nawigacje będą blokowane. Funkcja zabezpieczeń programu Internet Explorer będzie włączona w tej strefie zgodnie z ustawieniem kontroli funkcji ochrony z poziomu podniesienia uprawnień strefy.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Automatyczny monit o pobieranie plików w strefie z ograniczeniami w programie Internet Explorer**  </br>
  To ustawienie zasad określa, czy użytkownicy otrzymują monit o pobieranie plików niezainicjowane przez użytkownika. Niezależnie od tego ustawienia u użytkowników będą wyświetlane okna dialogowe pobierania plików w przypadku pobierania zainicjowanego przez użytkownika. Jeśli to ustawienie zostanie włączone, u użytkowników będzie wyświetlane okno dialogowe pobierania plików w przypadku prób automatycznego pobrania. Jeśli to ustawienie zostanie wyłączone lub nie zostanie skonfigurowane, próby pobrania plików, które nie są inicjowane przez użytkownika, będą blokowane, a użytkownicy będą widzieć pasek powiadomień zamiast okna dialogowego pobierania plików. Użytkownicy będą mogli kliknąć pasek powiadomień, aby zezwolić na pobranie plików.
  - **Ustawienie domyślne**: Wyłącz
  
- **Składniki uzależnione od platformy .NET Framework w strefie internetowej w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie tym, czy składniki .NET Framework, które nie są podpisane przy użyciu technologii Authenticode, mogą być wykonywane w programie Internet Explorer. Do tych składników należą zarządzane kontrolki przywoływane z tagu obiektu oraz zarządzane pliki wykonywalne przywoływane z linku. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer będzie wykonywał niepodpisane składniki zarządzane. Jeśli w polu listy rozwijanej wybierzesz wartość Monituj, program Internet Explorer będzie prosił użytkownika o określenie, czy może wykonywać niepodpisane składniki zarządzane. Jeśli to ustawienie zasad zostanie wyłączone, program Internet Explorer nie będzie wykonywał niepodpisanych składników zarządzanych. Jeśli to ustawienie zasad nie zostanie skonfigurowane, program Internet Explorer będzie wykonywał niepodpisane składniki zarządzane.
  - **Ustawienie domyślne**: Wyłącz 
  
- **Strefa internetowa w programie Internet Explorer zezwala na używanie kontrolek ActiveX TDC tylko przez zatwierdzone domeny**  </br>
  To ustawienie zasad określa, czy użytkownik może uruchomić kontrolkę ActiveX TDC w witrynach internetowych. Jeśli to ustawienie zasad zostanie włączone, kontrolka ActiveX TDC nie będzie uruchamiana z witryn internetowych w tej strefie. Jeśli to ustawienie zasad zostanie wyłączone, kontrolka ActiveX TDC będzie uruchamiana ze wszystkich witryn w tej strefie.
  - **Ustawienie domyślne**: Enabled 
  
- **Okna inicjowane przez skrypty w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie ograniczeniami dotyczącymi okien podręcznych oraz okien zawierających paski tytułu i stanu inicjowanych przez skrypty. Jeśli to ustawienie zasad zostanie włączone, zabezpieczenia Ograniczenia systemu Windows nie będą stosowane w tej strefie. Strefa zabezpieczeń będzie działać bez dodatkowej warstwy zabezpieczeń udostępnianej przez tę funkcję. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie możliwe uruchamianie potencjalnie szkodliwych akcji zawartych w oknach podręcznych oraz oknach zawierających paski tytułu i stanu inicjowanych przez skrypty. Ta funkcja zabezpieczeń programu Internet Explorer będzie włączona w tej strefie zgodnie z ustawieniem sterowania funkcją Ograniczenia zabezpieczeń okien inicjowanych przez skrypty dla procesu. Jeśli to ustawienie zasad nie zostanie skonfigurowane, nie będzie możliwe uruchamianie potencjalnie szkodliwych akcji zawartych w oknach podręcznych oraz oknach zawierających paski tytułu i stanu inicjowanych przez skrypty. Ta funkcja zabezpieczeń programu Internet Explorer będzie włączona w tej strefie zgodnie z ustawieniem sterowania funkcją Ograniczenia zabezpieczeń okien inicjowanych przez skrypty dla procesu.
  - **Ustawienie domyślne**: Wyłącz 
  
- **Strefa internetowa w programie Internet Explorer obejmuje ścieżkę lokalną podczas przekazywania plików do serwera**  </br>
  To ustawienie zasad określa, czy informacje o ścieżce lokalnej będą wysyłane, gdy użytkownik będzie przekazywał plik za pomocą formularza HTML. Jeśli informacje o ścieżce lokalnej będą wysyłane, niektóre informacje mogą zostać przypadkowo ujawnione serwerowi. Na przykład pliki wysłane z komputera użytkownika mogą zawierać nazwę użytkownika jako część ścieżki. Jeśli to ustawienie zasad zostanie włączone, informacje o ścieżce będą wysyłane, gdy użytkownik będzie przekazywał plik za pomocą formularza HTML. Jeśli to ustawienie zasad zostanie wyłączone, informacje o ścieżce będą usuwane, gdy użytkownik będzie przekazywał plik za pomocą formularza HTML. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł wybrać, czy informacje o ścieżce będą wysyłane podczas przekazywania pliku za pomocą formularza HTML. Domyślnie informacje o ścieżce są wysyłane.
  - **Ustawienie domyślne**: Wyłącz 
  
- **Wyłączanie procesów w rozszerzonym trybie chronionym programu Internet Explorer**  
  To ustawienie zasad określa, czy program Internet Explorer 11 korzysta z procesów 64-bitowych (większe bezpieczeństwo) czy procesów 32-bitowych (większa zgodność) w rozszerzonym trybie chronionym w 64-bitowych wersjach systemu Windows. Ważne: Niektóre kontrolki ActiveX i paski narzędzi mogą być niedostępne, gdy są używane procesy 64-bitowe. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer 11 będzie używać 64-bitowych procesów kart w rozszerzonym trybie chronionym w 64-bitowych wersjach systemu Windows. Jeśli to ustawienie zasad zostanie wyłączone, program Internet Explorer 11 będzie używać 32-bitowych procesów kart w rozszerzonym trybie chronionym w 64-bitowych wersjach systemu Windows. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy będą mogli włączyć lub wyłączyć tę funkcję w ustawieniach programu Internet Explorer. Ta funkcja jest domyślnie wyłączona.
  - **Ustawienie domyślne**: Enabled 
  
- **Ignorowanie błędów certyfikatów programu Internet Explorer**  </br>
  To ustawienie zasad uniemożliwia użytkownikowi ignorowanie błędów certyfikatu Secure Sockets Layer/Transport Layer Security (SSL/TLS), które przerywają przeglądanie (na przykład błędy z powodu wygaśnięcia, odwołania lub niezgodności nazwy) w programie Internet Explorer. Jeśli to ustawienie zasad zostanie włączone, użytkownik nie będzie mógł kontynuować przeglądania. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownik będzie mógł ignorować błędy certyfikatu i kontynuować przeglądanie.
  - **Ustawienie domyślne**: Wyłącz 
  
- **Ładowanie stref internetowych plików XAML w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie ładowaniem plików XAML (Extensible Application Markup Language). XAML to oparty na składni XML język znaczników deklaratywnych, który jest często służy do tworzenia zaawansowanych interfejsów użytkownika i grafik korzystających z programu Windows Presentation Foundation. Jeśli to ustawienie zasad zostanie włączone i w polu listy rozwijanej zostanie ustawiona wartość Włącz, pliki XAML będą automatycznie ładowane w programie Internet Explorer. Użytkownik nie może zmienić tego zachowania. Jeśli ustawisz w polu listy rozwijanej wartość Monituj, użytkownik będzie monitowany o załadowanie plików XAML. Jeśli to ustawienie zasad zostanie wyłączone, pliki XAML nie będą ładowane w programie Internet Explorer. Użytkownik nie może zmienić tego zachowania. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł wybrać, czy załadować pliki XAML w programie Internet Explorer.
  - **Ustawienie domyślne**: Wyłącz 
  
- **Automatyczny monit o pobieranie plików w strefie internetowej programu Internet Explorer**  </br>
  To ustawienie zasad określa, czy użytkownicy otrzymują monit o pobieranie plików niezainicjowane przez użytkownika. Niezależnie od tego ustawienia u użytkowników będą wyświetlane okna dialogowe pobierania plików w przypadku pobierania zainicjowanego przez użytkownika. Jeśli to ustawienie zostanie włączone, u użytkowników będzie wyświetlane okno dialogowe pobierania plików w przypadku prób automatycznego pobrania. Jeśli to ustawienie zostanie wyłączone lub nie zostanie skonfigurowane, próby pobrania plików, które nie są inicjowane przez użytkownika, będą blokowane, a użytkownicy będą widzieć pasek powiadomień zamiast okna dialogowego pobierania plików. Użytkownicy będą mogli kliknąć pasek powiadomień, aby zezwolić na pobranie plików.
  - **Ustawienie domyślne**: Enabled  
  
- **Ostrzeżenie o zabezpieczeniach strefy z ograniczeniami dla potencjalnie niebezpiecznych plików w programie Internet Explorer**  
  To ustawienie zasad określa, czy komunikat „Otwieranie pliku — ostrzeżenie o zabezpieczeniach” pojawia się, gdy użytkownik próbuje otworzyć pliki wykonywalne lub inne potencjalnie niebezpieczne pliki (na przykład z udziału plików w intranecie za pomocą Eksploratora plików). Jeśli to ustawienie zasad zostanie włączone i w polu listy rozwijanej zostanie ustawiona wartość Włącz, te pliki będą otwierane bez ostrzeżenia o zabezpieczeniach. Jeśli w polu listy rozwijanej ustawisz wartość Monituj, przed otwarciem plików pojawi się ostrzeżenie o zabezpieczeniach. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można otworzyć tych plików. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł skonfigurować sposób obsługi tych plików przez komputer. Domyślnie te pliki są zablokowane w strefie z ograniczeniami, włączone w strefie intranetu i komputera lokalnego oraz mają ustawione monitowanie w strefie Internetu i zaufanej strefie.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Filtrowanie skryptów między witrynami w strefie internetowej programu Internet Explorer**  
  Te zasady określają, czy filtr skryptów między witrynami (XSS) będzie wykrywał i blokował wprowadzanie skryptu między witrynami w witrynach internetowych w tej strefie. Jeśli to ustawienie zasad zostanie włączone, filtr XSS zostanie włączony dla witryn w tej strefie i filtr XSS będzie próbować zablokować wprowadzanie skryptów między witrynami. Jeśli to ustawienie zasad zostanie wyłączone, filtr XSS zostanie wyłączony dla witryn w tej strefie i program Internet Explorer będzie zezwalać na wprowadzanie skryptów między witrynami.
  - **Ustawienie domyślne**: Enabled 
  
- **Powrót do protokołu SSL3 w programie Internet Explorer**  
  To ustawienie zasad umożliwia zablokowanie niezabezpieczonego powrotu do protokołu SSL 3.0. Jeśli te zasady zostaną włączone, program Internet Explorer będzie podejmować próby połączenia z witrynami za pomocą protokołu SSL 3.0 lub starszego w przypadku niepowodzenia połączenia za pomocą protokołu TLS 1.0 lub nowszego. Zalecamy, aby nie zezwalać na niezabezpieczony powrót w celu zapobieżenia atakowi typu man-in-the-middle. Te zasady nie mają wpływu na to, które protokoły zabezpieczeń są włączone. Jeśli te zasady zostaną wyłączone, będą używane ustawienia domyślne systemu.
  - **Ustawienie domyślne**: Żadne witryny 
  
- **Blokada filtra SmartScreen w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad określa, czy filtr SmartScreen skanuje strony w tej strefie pod kątem złośliwej zawartości. Jeśli to ustawienie zasad zostanie włączone, filtr SmartScreen będzie skanować strony w tej strefie pod kątem złośliwej zawartości. Jeśli to ustawienie zasad zostanie wyłączone, filtr SmartScreen nie będzie skanować stron w tej strefie pod kątem złośliwej zawartości. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł wybrać, czy filtr SmartScreen ma skanować strony w tej strefie pod kątem złośliwej zawartości. Uwaga: W programie Internet Explorer 7 to ustawienie zasad określa, czy filtr wyłudzania informacji skanuje strony w tej strefie pod kątem złośliwej zawartości.
  - **Ustawienie domyślne**: Enabled 
  
- **Uruchamianie aplikacje i plików w elementach iFrame w strefie z ograniczeniami programu Internet Explorer**  
  To ustawienie zasad umożliwia określenie, czy można uruchamiać aplikacje i pobierać pliki z odwołania IFRAME w kodzie HTML stron w tej strefie. Jeśli to ustawienie zasad zostanie włączone, użytkownicy będą mogli uruchamiać aplikacje i pobierać pliki z elementów IFRAME na stronach w tej strefie bez interwencji użytkownika. Jeśli w polu listy rozwijanej ustawisz wartość Monituj, użytkownicy będą proszeni o wybranie, czy uruchamiać aplikacje i pobierać pliki z elementów IFRAME na stronach w tej strefie. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli uruchamiać aplikacji i pobierać plików z elementów IFRAME na stronach w tej strefie. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy nie będą mogli uruchamiać aplikacji i pobierać plików z elementów IFRAME na stronach w tej strefie.
  - **Ustawienie domyślne**: Wyłącz 
  
- **Pomijanie ostrzeżeń filtra SmartScreen o nietypowych plikach w programie Internet Explorer** To ustawienie zasad określa, czy użytkownik może pomijać ostrzeżenia filtra SmartScreen. Filtr SmartScreen wysyła do użytkownika ostrzeżenia o plikach wykonywalnych, których użytkownicy programu Internet Explorer nie pobierają często z Internetu. Jeśli to ustawienie zasad zostanie włączone, ostrzeżenia filtra SmartScreen będą blokować użytkownika. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownik będzie mógł pomijać ostrzeżenia filtra SmartScreen.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Blokowanie okien podręcznych w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad pozwala określić, czy mają być wyświetlane niechciane okna podręczne. Okna podręczne otwierane, gdy użytkownik końcowy kliknie link, nie są blokowane. Jeśli to ustawienie zasad zostanie włączone, większość niechcianych okien podręcznych nie będzie wyświetlana. Jeśli to ustawienie zasad zostanie wyłączone, wyświetlanie okien podręcznych nie będzie blokowane. Jeśli to ustawienie zasad nie zostanie skonfigurowane, większość niechcianych okien podręcznych nie będzie wyświetlana.
  - **Ustawienie domyślne**: Włącz  
  
- **Spójna obsługa protokołu MIME przez procesy programu Internet Explorer**  
  Program Internet Explorer zawiera dynamiczne zachowania elementów binarnych: składniki, które hermetyzują określone funkcje dla elementów HTML, z którymi są połączone. To ustawienie zasad określa, czy ustawienie ograniczenia zabezpieczeń zachowania elementów binarnych jest zablokowane czy dozwolone. Jeśli to ustawienie zasad zostanie włączone, zachowania elementów binarnych będą zablokowane w procesach Eksploratora plików i programu Internet Explorer. Jeśli to ustawienie zasad zostanie wyłączone, zachowania elementów binarnych będą dozwolone w procesach Eksploratora plików i programu Internet Explorer. Jeśli to ustawienie zasad nie zostanie skonfigurowane, zachowania elementów binarnych będą zablokowane w procesach Eksploratora plików i programu Internet Explorer.
  - **Ustawienie domyślne**: Enabled  
  
- **Uprawnienia środowiska Java w strefie z ograniczeniami programu Internet Explorer** To ustawienie zasad umożliwia zarządzanie uprawnieniami dotyczącymi apletów Java. Jeśli to ustawienie zasad zostanie włączone, będzie można wybierać opcje z listy rozwijanej. Ustawienie Niestandardowe umożliwia kontrolowanie ustawień uprawnień pojedynczo. Ustawienie Niski poziom zabezpieczeń umożliwia apletom wykonywanie wszystkich operacji. Ustawienie Średni poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy (obszarze pamięci, poza którym program nie może wykonywać wywołań) oraz udostępnia funkcje, takie jak obszar na pliki tymczasowe (bezpieczny obszar magazynu na komputerze klienckim) i kontrolowane przez użytkownika operacje we/wy na plikach. Ustawienie Wysoki poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy. Wyłącz język Java, aby uniemożliwić uruchamianie jakichkolwiek apletów. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można uruchamiać apletów Java. Jeśli to ustawienie zasad nie zostanie skonfigurowane, aplety Java będą wyłączone.
  - **Ustawienie domyślne**: Wyłącz Java  
    
  
- **Kontrolki ActiveX programu Internet Explorer w trybie chronionym**  
  To ustawienie zasad uniemożliwia uruchamianie kontrolek ActiveX w trybie chronionym, gdy jest włączony rozszerzony tryb chroniony. Jeśli użytkownik ma zainstalowaną kontrolkę ActiveX, która nie jest zgodna z rozszerzonym trybem chronionym, i witryna internetowa próbuje ją załadować, program Internet Explorer powiadamia użytkownika i umożliwia uruchomienie witryny w standardowym trybie chronionym. To ustawienie zasad powoduje wyłączenie tego powiadomienia i wymuszenie działania wszystkich witryn w rozszerzonym trybie chronionym. Rozszerzony tryb chroniony zapewnia dodatkową ochronę przed złośliwymi witrynami internetowymi dzięki użyciu 64-bitowych procesów w 64-bitowych wersjach systemu Windows. Na komputerach z systemem w wersji co najmniej Windows 8 rozszerzony tryb chroniony ogranicza także lokalizacje, z których program Internet Explorer może czytać w rejestrze i w systemie plików. Gdy rozszerzony tryb chroniony jest włączony i użytkownik napotyka witrynę, która próbuje załadować kontrolkę ActiveX niezgodną z rozszerzonym trybem chronionym, program Internet Explorer powiadamia użytkownika i umożliwia wyłączenie rozszerzonego trybu chronionego dla tej witryny. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer nie umożliwi użytkownikowi wyłączenia rozszerzonego trybu chronionego. Wszystkie witryny trybu chronionego będą uruchamiane w rozszerzonym trybie chronionym. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, program Internet Explorer będzie powiadamiać użytkowników i umożliwi uruchamianie witryn z niezgodnymi kontrolkami ActiveX w standardowym trybie chronionym. Jest to zachowanie domyślne.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Ładowanie stref z ograniczeniami plików XAML w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie ładowaniem plików XAML (Extensible Application Markup Language). XAML to oparty na składni XML język znaczników deklaratywnych, który jest często służy do tworzenia zaawansowanych interfejsów użytkownika i grafik korzystających z programu Windows Presentation Foundation. Jeśli to ustawienie zasad zostanie włączone i w polu listy rozwijanej zostanie ustawiona wartość Włącz, pliki XAML będą automatycznie ładowane w programie Internet Explorer. Użytkownik nie może zmienić tego zachowania. Jeśli ustawisz w polu listy rozwijanej wartość Monituj, użytkownik będzie monitowany o załadowanie plików XAML. Jeśli to ustawienie zasad zostanie wyłączone, pliki XAML nie będą ładowane w programie Internet Explorer. Użytkownik nie może zmienić tego zachowania. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł wybrać, czy załadować pliki XAML w programie Internet Explorer.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Ograniczenia zabezpieczeń okien ze skryptem w procesach programu Internet Explorer**  
  Program Internet Explorer umożliwia skryptom programowe otwieranie różnego rodzaju okien oraz zmienianie ich rozmiaru i położenia. Funkcja zabezpieczeń dotycząca ograniczeń okien ogranicza okna podręczne i uniemożliwia skryptom wyświetlanie okien, w których pasek tytułu i stanu nie są widoczne dla użytkownika lub zaciemniają paski tytułu i stanu innych okien. Jeśli to ustawienie zasad zostanie włączone, okna inicjowane przez skrypty będą ograniczone dla wszystkich procesów. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, okna inicjowane przez skrypty nie będą ograniczone.
  - **Ustawienie domyślne**: Enabled   
  
- **Uruchamianie wtyczek i kontrolek ActiveX w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad pozwala określić, czy wtyczki i kontrolki ActiveX mogą być uruchamiane na stronach z określonej strefy. Jeśli to ustawienie zasad zostanie włączone, kontrolki i wtyczki będą uruchamiane bez interwencji użytkownika. Jeśli w polu listy rozwijanej wybierzesz wartość Monituj, użytkownicy będą proszeni o wybranie, czy zezwalać na uruchamianie kontrolek i wtyczek. Jeśli to ustawienie zasad zostanie wyłączone, kontrolki i wtyczki nie będą uruchamiane. Jeśli to ustawienie zasad nie zostanie skonfigurowane, kontrolki i wtyczki nie będą uruchamiane.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Używanie w skryptach kontrolek ActiveX oznaczonych jako bezpieczne dla skryptów w strefie z ograniczeniami programu Internet Explorer**  
  To ustawienie zasad pozwala określić, czy kontrolka ActiveX oznaczona jako bezpieczna dla skryptów może wchodzić w interakcję ze skryptem. Jeśli to ustawienie zasad zostanie włączone, interakcja ze skryptem może występować automatycznie bez interwencji użytkownika. Jeśli w polu listy rozwijanej wybierzesz wartość Monituj, użytkownicy będą proszeni o wybranie, czy zezwalać na interakcję ze skryptem. Jeśli to ustawienie zasad zostanie wyłączone, interakcja ze skryptem nie będzie możliwa. Jeśli to ustawienie zasad nie zostanie skonfigurowane, interakcja ze skryptem nie będzie możliwa.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Opcje logowania w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie ustawieniami opcji logowania. Jeśli to ustawienie zasad zostanie włączone, będzie można wybierać poniższe opcje logowania. Użyj logowania anonimowego, aby wyłączyć uwierzytelnianie HTTP i używać konta gościa tylko dla protokołu CIFS (Common Internet File System). Monituj o podanie nazwy użytkownika i hasła, aby wysyłać zapytania do użytkowników dotyczące identyfikatorów użytkowników i haseł. Po wysłaniu zapytania do użytkownika można używać tych wartości dyskretnie w pozostałej części sesji. Zaloguj automatycznie tylko w strefie intranetu, aby wysyłać do użytkowników zapytania dotyczące identyfikatorów użytkowników i haseł w innych strefach. Po wysłaniu zapytania do użytkownika można używać tych wartości dyskretnie w pozostałej części sesji. Użyj automatycznego logowania przy użyciu bieżącej nazwy użytkownika i hasła, aby spróbować zalogować się przy użyciu odpowiedzi na żądanie systemu Windows NT (uwierzytelnianie NTLM). Jeśli odpowiedź na żądanie systemu Windows NT jest obsługiwana przez serwer, podczas logowania są używane nazwa użytkownika i hasło sieci użytkownika. Jeśli odpowiedź na żądanie systemu Windows NT nie jest obsługiwana przez serwer, użytkownik zostanie poproszony o podanie nazwy użytkownika i hasła. Jeśli to ustawienie zasad zostanie wyłączone, zostanie ustawione automatyczne logowanie tylko w strefie intranetu. Jeśli to ustawienie zasad nie zostanie skonfigurowane, zostanie ustawione monitowanie o podanie nazwy użytkownika i hasła.
  - **Ustawienie domyślne**: Anonimowy  
  
- **Zaufana strefa w programie Internet Explorer inicjuje i umieszcza w skryptach kontrolki ActiveX, które nie są oznaczone jako bezpieczne**  
  To ustawienie zasad umożliwia zarządzanie kontrolkami ActiveX, które nie są oznaczone jako bezpieczne. Jeśli to ustawienie zasad zostanie włączone, kontrolki ActiveX będą uruchamiane i ładowane z parametrami oraz będą wykonywane ich skrypty bez konieczności ustawiania poziomu bezpieczeństwa obiektów dla niezaufanych danych lub skryptów. To ustawienie nie jest zalecane poza strefami bezpiecznymi i administrowanymi. To ustawienie umożliwia inicjowanie i wykonywanie skryptów zarówno bezpiecznych, jak i niebezpiecznych kontrolek, z jednoczesnym ignorowaniem opcji Wykonaj skrypty kontrolek ActiveX zaznaczone jako bezpieczne. Jeśli to ustawienie zasad zostanie włączone i w polu listy rozwijanej zostanie wybrana pozycja Monituj, użytkownicy będą pytani, czy zezwolić na ładowanie kontrolek z parametrami lub inicjowanych przez skrypty. Jeśli to ustawienie zasad zostanie wyłączone, kontrolki ActiveX, które nie mogą stać się bezpieczne, nie będą ładowane z parametrami ani nie będą wykonywane ich skrypty. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy będą pytani, czy zezwolić na ładowanie kontrolek z parametrami lub inicjowanych przez skrypty.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Sprawdzanie odwołania certyfikatów serwera w programie Internet Explorer**  
  To ustawienie zasad pozwala określić, czy program Internet Explorer będzie sprawdzać stan odwołania certyfikatów serwerów. Certyfikaty są odwoływane w przypadku naruszenia zabezpieczeń lub gdy nie są już prawidłowe. To ustawienie chroni użytkowników przed przesłaniem danych poufnych do fałszywej lub niezabezpieczonej witryny. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer będzie sprawdzać, czy certyfikaty serwerów zostały odwołane. Jeśli to ustawienie zasad zostanie wyłączone, program Internet Explorer nie będzie sprawdzać, czy certyfikaty serwerów zostały odwołane. Jeśli to ustawienie zasad nie zostanie skonfigurowane, program Internet Explorer nie będzie sprawdzać, czy certyfikaty serwerów zostały odwołane.
  - **Ustawienie domyślne**: Enabled 
  
- **Mniej uprzywilejowane witryny w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad pozwala określić, czy witryny internetowe z mniej uprzywilejowanych stref, takie jak witryny z ograniczeniami, mogą prowadzić do tej strefy. Jeśli to ustawienie zasad zostanie włączone, witryny z mniej uprzywilejowanych stref będą mogły otwierać nowe okna w tej strefie. Strefa zabezpieczeń będzie działać bez dodatkowej warstwy zabezpieczeń, które są udostępniane przez funkcję zabezpieczeń do ochrony z poziomu podniesienia uprawnień strefy. Jeśli w polu listy rozwijanej wybierzesz wartość Monituj, użytkownik otrzyma ostrzeżenie o potencjalnie ryzykownej nawigacji. Jeśli to ustawienie zasad zostanie wyłączone, potencjalnie szkodliwe nawigacje będą blokowane. Funkcja zabezpieczeń programu Internet Explorer będzie włączona w tej strefie zgodnie z ustawieniem kontroli funkcji ochrony z poziomu podniesienia uprawnień strefy. Jeśli to ustawienie zasad nie zostanie skonfigurowane, witryny z mniej uprzywilejowanych stref będą mogły otwierać nowe okna w tej strefie.
  - **Ustawienie domyślne**: Wyłącz  

- **Pobieranie plików w strefie z ograniczeniami w programie Internet Explorer**  </br>
  To ustawienie zasad pozwala określić, czy pobieranie plików ze strefy jest dozwolone. Ta opcja jest określana przez strefę strony z linkiem pobierania, a nie przez strefę, z której plik jest dostarczany. Jeśli to ustawienie zasad zostanie włączone, będzie można pobierać pliki ze strefy. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można pobierać plików ze strefy. Jeśli to ustawienie zasad nie zostanie skonfigurowane, nie będzie można pobierać plików ze strefy.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Strefa internetowa w programie Internet Explorer uruchamia składniki uzależnione od platformy .NET Framework podpisane przy użyciu technologii Authenticode**  
  To ustawienie zasad umożliwia zarządzanie tym, czy składniki .NET Framework podpisane przy użyciu technologii Authenticode mogą być wykonywane w programie Internet Explorer. Do tych składników należą zarządzane kontrolki przywoływane z tagu obiektu oraz zarządzane pliki wykonywalne przywoływane z linku. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer będzie wykonywał podpisane składniki zarządzane. Jeśli w polu listy rozwijanej wybierzesz wartość Monituj, program Internet Explorer będzie prosił użytkownika o określenie, czy może wykonywać podpisane składniki zarządzane. Jeśli to ustawienie zasad zostanie wyłączone, program Internet Explorer nie będzie wykonywał podpisanych składników zarządzanych. Jeśli to ustawienie zasad nie zostanie skonfigurowane, program Internet Explorer nie będzie wykonywał podpisanych składników zarządzanych.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Program Internet Explorer uniemożliwia instalację kontrolek ActiveX przez poszczególnych użytkowników**  </br>
  To ustawienie zasad umożliwia blokowanie instalacji kontrolek ActiveX przeprowadzanych przez poszczególnych użytkowników. Jeśli to ustawienie zasad zostanie włączone, poszczególni użytkownicy nie będą mogli instalować kontrolek ActiveX. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, poszczególni użytkownicy będą mogli instalować kontrolki ActiveX.
  - **Ustawienie domyślne**: Enabled  
  
- **Program Internet Explorer uniemożliwia zarządzanie filtrem SmartScreen**  </br>
  To ustawienie zasad uniemożliwia użytkownikowi zarządzanie filtrem SmartScreen i powoduje wyświetlenie ostrzeżenia o tym, że odwiedzana witryna jest znana z fałszywych prób zebrania informacji osobistych metodą wyłudzania informacji lub z hostowania złośliwego oprogramowania. W przypadku włączenia tego ustawienia zasad użytkownik nie otrzyma monitu o włączenie filtru SmartScreen. Wszystkie adresy witryn, których nie ma na liście dozwolonych filtru, są automatycznie wysyłane do firmy Microsoft bez monitowania użytkownika. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownik otrzyma monit o to, czy włączyć filtr SmartScreen podczas pierwszego uruchomienia.
  - **Ustawienie domyślne**: Włącz  
  
- **Funkcja zabezpieczeń wykrywania protokołu MIME w procesach programu Internet Explorer**  
  To ustawienie zasad określa, czy wykrywanie protokołu MIME programu Internet Explorer uniemożliwi podwyższenie poziomu pliku danego typu do bardziej niebezpiecznego typu pliku. Jeśli to ustawienie zasad zostanie włączone, wykrywanie protokołu MIME nigdy nie będzie podwyższać poziomu pliku danego typu do bardziej niebezpiecznego typu pliku. Jeśli to ustawienie zasad zostanie wyłączone, procesy programu Internet Explorer będą zezwalać na podwyższanie poziomu pliku danego typu do bardziej niebezpiecznego typu pliku w ramach wykrywania protokołu MIME. Jeśli to ustawienie zasad nie zostanie skonfigurowane, wykrywanie protokołu MIME nigdy nie będzie podwyższać poziomu pliku danego typu do bardziej niebezpiecznego typu pliku.
  - **Ustawienie domyślne**: Enabled  
  
- **Pobieranie podpisanych kontrolek ActiveX w strefie z ograniczeniami w programie Internet Explorer**  </br>
  To ustawienie zasad umożliwia zarządzanie tym, czy użytkownicy mogą pobierać podpisane kontrolki ActiveX ze strony w strefie. Jeśli te zasady zostaną włączone, użytkownicy będą mogli pobierać podpisane kontrolki bez interwencji użytkownika. Jeśli wybierzesz w polu listy rozwijanej wartość Monituj, użytkownicy będą proszeni o wybranie, czy pobierać kontrolki podpisane przez niezaufanych wydawców. Kod podpisany przez zaufanych wydawców jest dyskretnie pobierany. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można pobierać podpisanych kontrolek. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy będą proszeni o wybranie, czy pobierać kontrolki podpisane przez niezaufanych wydawców. Kod podpisany przez zaufanych wydawców jest dyskretnie pobierany.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Autouzupełnianie w programie Internet Explorer**  </br>
  Ta funkcja autouzupełniania zapamiętuje i sugeruje nazwy użytkowników i hasła w formularzach. Jeśli to ustawienie zostanie włączone, użytkownik nie będzie mógł zmienić ustawienia „Nazwy użytkowników i hasła w formularzach” lub „Monituj o zapisywanie haseł”. Funkcja autouzupełniania dla nazw użytkowników i haseł w formularzach zostanie włączona. Musisz zdecydować, czy wybrać ustawienie „Monituj o zapisywanie haseł”. Jeśli to ustawienie zostanie wyłączone, użytkownik nie będzie mógł zmienić ustawienia „Nazwy użytkowników i hasła w formularzach” lub „Monituj o zapisywanie haseł”. Funkcja autouzupełniania dla nazw użytkownika i haseł w formularzach zostanie wyłączona. Użytkownik może też ustawić monitowanie o zapisywanie haseł. Jeśli to ustawienie nie zostanie skonfigurowane, użytkownik będzie mógł włączyć autouzupełnianie dla nazw użytkowników i haseł w formularzach oraz monitowanie o zapisywanie haseł. Aby wyświetlić tę opcję, użytkownicy muszą otworzyć okno dialogowe Opcje internetowe, kliknąć kartę Zawartość i kliknąć przycisk Ustawienia.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Zezwalanie na uruchamianie skryptu VBscript w strefie internetowej programu Internet Explorer**  </br>
  To ustawienie zasad pozwala określić, czy można uruchamiać skrypt VBScript na stronach w określonych strefach programu Internet Explorer. Jeśli to ustawienie zasad zostanie włączone (ustawienie domyślne), będzie trzeba również wybrać jedną z następujących pozycji w polu Opcje: Włącz. Skrypt VBScript jest uruchamiany na stronach w określonych strefach bez interakcji. Monituj. Pracownicy są monitowani o to, czy zezwalać na uruchamianie skryptu VBScript w strefie. Wyłącz. Nie można uruchamiać skryptu VBScript w strefie. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, skrypt VBScript będzie uruchamiany bez interakcji w określonej strefie
  - **Ustawienie domyślne**: Wyłącz  
  
- **Strefa z ograniczeniami w programie Internet Explorer zezwala na używanie kontrolek ActiveX TDC tylko przez zatwierdzone domeny**  </br>
  To ustawienie zasad określa, czy użytkownik może uruchomić kontrolkę ActiveX TDC w witrynach internetowych. Jeśli to ustawienie zasad zostanie włączone, kontrolka ActiveX TDC nie będzie uruchamiana z witryn internetowych w tej strefie. Jeśli to ustawienie zasad zostanie wyłączone, kontrolka ActiveX TDC będzie uruchamiana ze wszystkich witryn w tej strefie.
  - **Ustawienie domyślne**: Enabled  
  
- **Zaufana strefa w programie Internet Explorer nie uruchamia oprogramowania chroniącego przed złośliwym oprogramowaniem względem kontrolek ActiveX**   </br>
  To ustawienie zasad określa, czy program Internet Explorer uruchamia programy chroniące przed złośliwym oprogramowaniem względem kontrolek ActiveX w celu sprawdzenia, czy można bezpiecznie ładować je na stronach. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer nie będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Jeśli to ustawienie zasad zostanie wyłączone, program Internet Explorer zawsze będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Jeśli to ustawienie zasad nie zostanie skonfigurowane, program Internet Explorer zawsze będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Użytkownicy mogą włączać i wyłączać to zachowanie przy użyciu ustawień zabezpieczeń programu Internet Explorer.
  - **Ustawienie domyślne**: Wyłącz 
  
- **Uprawnienia języka Java w strefie komputera lokalnego programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie uprawnieniami dotyczącymi apletów Java. Jeśli to ustawienie zasad zostanie włączone, będzie można wybierać opcje z listy rozwijanej. Ustawienie Niestandardowe umożliwia kontrolowanie ustawień uprawnień pojedynczo. Ustawienie Niski poziom zabezpieczeń umożliwia apletom wykonywanie wszystkich operacji. Ustawienie Średni poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy (obszarze pamięci, poza którym program nie może wykonywać wywołań) oraz udostępnia funkcje, takie jak obszar na pliki tymczasowe (bezpieczny obszar magazynu na komputerze klienckim) i kontrolowane przez użytkownika operacje we/wy na plikach. Ustawienie Wysoki poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy. Wyłącz język Java, aby uniemożliwić uruchamianie jakichkolwiek apletów. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można uruchamiać apletów Java. Jeśli to ustawienie zasad nie zostanie skonfigurowane, zostaną ustawione uprawnienia na Średni poziom zabezpieczeń.
  - **Ustawienie domyślne**: Wyłącz Java 
  
- **Strefa intranetowa w programie Internet Explorer nie uruchamia oprogramowania chroniącego przed złośliwym oprogramowaniem względem kontrolek ActiveX**  </br>
  To ustawienie zasad określa, czy program Internet Explorer uruchamia programy chroniące przed złośliwym oprogramowaniem względem kontrolek ActiveX w celu sprawdzenia, czy można bezpiecznie ładować je na stronach. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer nie będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Jeśli to ustawienie zasad zostanie wyłączone, program Internet Explorer zawsze będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Jeśli to ustawienie zasad nie zostanie skonfigurowane, program Internet Explorer nie będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Użytkownicy mogą włączać i wyłączać to zachowanie przy użyciu ustawień zabezpieczeń programu Internet Explorer.
  - **Ustawienie domyślne**: Wyłącz  

- **Skryptlety w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad pozwala określić, czy użytkownik może uruchamiać skryptlety. Jeśli to ustawienie zasad zostanie włączone, użytkownik będzie mógł uruchamiać skryptlety. Jeśli to ustawienie zasad zostanie wyłączone, użytkownik nie będzie mógł uruchamiać skryptletów. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł włączać lub wyłączać skryptlety.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Pasek powiadomień procesów programu Internet Explorer**  </br>  
  To ustawienie zasad pozwala określić, czy pasek powiadomień ma być wyświetlany dla procesów programu Internet Explorer, gdy instalacja pliku lub kodu jest ograniczona. Domyślnie pasek powiadomień jest wyświetlany dla procesów programu Internet Explorer. Jeśli to ustawienie zasad zostanie włączone, pasek powiadomień będzie wyświetlany dla procesów programu Internet Explorer. Jeśli to ustawienie zasad zostanie wyłączone, pasek powiadomień nie będzie wyświetlany dla procesów programu Internet Explorer. Jeśli to ustawienie zasad nie zostanie skonfigurowane, pasek powiadomień będzie wyświetlany dla procesów programu Internet Explorer.
  - **Ustawienie domyślne**: Enabled  
  
- **Pobieranie podpisanych kontrolek ActiveX w strefie internetowej programu Internet Explorer**  </br>
  To ustawienie zasad umożliwia zarządzanie tym, czy użytkownicy mogą pobierać podpisane kontrolki ActiveX ze strony w strefie. Jeśli te zasady zostaną włączone, użytkownicy będą mogli pobierać podpisane kontrolki bez interwencji użytkownika. Jeśli wybierzesz w polu listy rozwijanej wartość Monituj, użytkownicy będą proszeni o wybranie, czy pobierać kontrolki podpisane przez niezaufanych wydawców. Kod podpisany przez zaufanych wydawców jest dyskretnie pobierany. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można pobierać podpisanych kontrolek. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy będą proszeni o wybranie, czy pobierać kontrolki podpisane przez niezaufanych wydawców. Kod podpisany przez zaufanych wydawców jest dyskretnie pobierany.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Filtr SmartScreen w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad określa, czy filtr SmartScreen skanuje strony w tej strefie pod kątem złośliwej zawartości. Jeśli to ustawienie zasad zostanie włączone, filtr SmartScreen będzie skanować strony w tej strefie pod kątem złośliwej zawartości. Jeśli to ustawienie zasad zostanie wyłączone, filtr SmartScreen nie będzie skanować stron w tej strefie pod kątem złośliwej zawartości. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł wybrać, czy filtr SmartScreen ma skanować strony w tej strefie pod kątem złośliwej zawartości. Uwaga: W programie Internet Explorer 7 to ustawienie zasad określa, czy filtr wyłudzania informacji skanuje strony w tej strefie pod kątem złośliwej zawartości.
  - **Ustawienie domyślne**: Enabled  
  
- **Usuwanie przycisku Uruchom teraz dla nieaktualnych kontrolek ActiveX w programie Internet Explorer**  </br>
  To ustawienie zasad pozwala ukryć przed użytkownikami przycisk „Uruchom teraz” oraz uniemożliwia uruchamianie określonych nieaktualnych kontrolek ActiveX w programie Internet Explorer. Jeśli to ustawienie zasad zostanie włączone, użytkownicy nie będą widzieć przycisku „Uruchom teraz” w komunikacie ostrzegawczym, który jest wyświetlany, gdy program Internet Explorer blokuje nieaktualną kontrolkę ActiveX. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownicy będą widzieć przycisk „Uruchom teraz” w komunikacie ostrzegawczym, który jest wyświetlany, gdy program Internet Explorer blokuje nieaktualną kontrolkę ActiveX. Kliknięcie tego przycisku pozwala użytkownikowi uruchomić raz nieaktualną kontrolkę ActiveX. Więcej informacji można znaleźć na stronie „Nieaktualne kontrolki ActiveX” w bibliotece TechNet programu Internet Explorer.
  - **Ustawienie domyślne**: Enabled 
  
- **Uruchamianie aplikacji i plików w elementach iframe w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad umożliwia określenie, czy można uruchamiać aplikacje i pobierać pliki z odwołania IFRAME w kodzie HTML stron w tej strefie. Jeśli to ustawienie zasad zostanie włączone, użytkownicy będą mogli uruchamiać aplikacje i pobierać pliki z elementów IFRAME na stronach w tej strefie bez interwencji użytkownika. Jeśli w polu listy rozwijanej ustawisz wartość Monituj, użytkownicy będą proszeni o wybranie, czy uruchamiać aplikacje i pobierać pliki z elementów IFRAME na stronach w tej strefie. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli uruchamiać aplikacji i pobierać plików z elementów IFRAME na stronach w tej strefie. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy będą proszeni o wybranie, czy uruchamiać aplikacje i pobierać pliki z elementów IFRAME na stronach w tej strefie
  - **Ustawienie domyślne**: Wyłącz 
  
- **Nawigacja w oknach i ramkach różnych domen w strefie z ograniczeniami w programie Internet Explorer**  </br>
  To ustawienie zasad umożliwia ustawianie opcji przeciągania zawartości między domenami, gdy źródło i lokalizacja docelowa znajdują się w różnych oknach. Jeśli to ustawienie zasad zostanie włączone i klikniesz pozycję Włącz, użytkownicy będą mogli przeciągać zawartość między domenami, gdy źródło i lokalizacja docelowa znajdują się w różnych oknach. Użytkownicy nie mogą zmieniać tego ustawienia. Jeśli to ustawienie zasad zostanie włączone i klikniesz pozycję Wyłącz, użytkownicy nie będą mogli przeciągać zawartości z jednej domeny do innej, gdy zarówno miejsce źródłowe, jak i docelowe będą w różnych oknach. Użytkownicy nie mogą zmieniać tego ustawienia. W programie Internet Explorer 10, jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownicy nie będą mogli przeciągać zawartości z jednej domeny do innej, gdy miejsce źródłowe i docelowe będą w różnych oknach. Użytkownicy mogą zmieniać to ustawienie w oknie dialogowym Opcje internetowe. W programie Internet Explorer 9 lub jego starszych wersjach, jeśli te zasady zostaną wyłączone lub nie zostaną skonfigurowane, użytkownicy będą mogli przeciągać zawartość z jednej domeny do innej, gdy miejsce źródłowe i docelowe będą w różnych oknach. Użytkownicy nie mogą zmieniać tego ustawienia.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Filtr SmartScreen w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad określa, czy filtr SmartScreen skanuje strony w tej strefie pod kątem złośliwej zawartości. Jeśli to ustawienie zasad zostanie włączone, filtr SmartScreen będzie skanować strony w tej strefie pod kątem złośliwej zawartości. Jeśli to ustawienie zasad zostanie wyłączone, filtr SmartScreen nie będzie skanować stron w tej strefie pod kątem złośliwej zawartości. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł wybrać, czy filtr SmartScreen ma skanować strony w tej strefie pod kątem złośliwej zawartości. Uwaga: W programie Internet Explorer 7 to ustawienie zasad określa, czy filtr wyłudzania informacji skanuje strony w tej strefie pod kątem złośliwej zawartości.
  - **Ustawienie domyślne**: Enabled  
  
- **Zablokowane uprawnienia języka Java w zaufanej strefie programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie uprawnieniami dotyczącymi apletów Java. Jeśli to ustawienie zasad zostanie włączone, będzie można wybierać opcje z listy rozwijanej. Ustawienie Niestandardowe umożliwia kontrolowanie ustawień uprawnień pojedynczo. Ustawienie Niski poziom zabezpieczeń umożliwia apletom wykonywanie wszystkich operacji. Ustawienie Średni poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy (obszarze pamięci, poza którym program nie może wykonywać wywołań) oraz udostępnia funkcje, takie jak obszar na pliki tymczasowe (bezpieczny obszar magazynu na komputerze klienckim) i kontrolowane przez użytkownika operacje we/wy na plikach. Ustawienie Wysoki poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy. Wyłącz język Java, aby uniemożliwić uruchamianie jakichkolwiek apletów. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można uruchamiać apletów Java. Jeśli to ustawienie zasad nie zostanie skonfigurowane, aplety Java będą wyłączone.
  - **Ustawienie domyślne**: Wyłącz Java 
  
- **Sprawdzanie podpisów pobranych programów w programie Internet Explorer**  
  To ustawienie zasad pozwala określić, czy program Internet Explorer ma sprawdzać podpisy cyfrowe (identyfikujące wydawcę podpisanego oprogramowania i sprawdzające, czy został on zmodyfikowany lub naruszony) w komputerach użytkowników przed pobraniem programów wykonywalnych. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer będzie sprawdzać podpisy cyfrowe programów wykonywalnych i wyświetlać ich tożsamości przed pobraniem do komputerów użytkowników. Jeśli to ustawienie zasad zostanie wyłączone, program Internet Explorer nie będzie sprawdzać podpisy cyfrowe programów wykonywalnych ani wyświetlać ich tożsamości przed pobraniem do komputerów użytkowników. Jeśli te zasady nie zostaną skonfigurowane, program Internet Explorer nie będzie sprawdzać podpisy cyfrowe programów wykonywalnych ani wyświetlać ich tożsamości przed pobraniem do komputerów użytkowników.
  - **Ustawienie domyślne**: Enabled  
  
- **Wykonywanie skryptów kontrolek przeglądarki internetowej w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad określa, czy strona może kontrolować osadzone kontrolki WebBrowser za pomocą skryptu. Jeśli to ustawienie zasad zostanie włączone, dostęp skryptów do kontrolki WebBrowser będzie dozwolony. Jeśli to ustawienie zasad zostanie wyłączone, dostęp skryptów do kontrolki WebBrowser nie będzie dozwolony. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł włączyć lub wyłączyć dostęp skryptów do kontrolki WebBrowser. Domyślnie dostęp skryptów do kontrolki WebBrowser jest dozwolony tylko w strefach Komputer lokalny i Intranet.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Filtrowanie skryptów między witrynami w strefie z ograniczeniami w programie Internet Explorer**  
  Te zasady określają, czy filtr skryptów między witrynami (XSS) będzie wykrywał i blokował wprowadzanie skryptu między witrynami w witrynach internetowych w tej strefie. Jeśli to ustawienie zasad zostanie włączone, filtr XSS zostanie włączony dla witryn w tej strefie i filtr XSS będzie próbować zablokować wprowadzanie skryptów między witrynami. Jeśli to ustawienie zasad zostanie wyłączone, filtr XSS zostanie wyłączony dla witryn w tej strefie i program Internet Explorer będzie zezwalać na wprowadzanie skryptów między witrynami.
  - **Ustawienie domyślne**: Enabled  
  
- **Zachowanie danych binarnych i skryptów w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie dynamicznym zachowaniem danych binarnych i skryptów: składników, które hermetyzują określone funkcji dla elementów kodu HTML, do których zostały dołączone. Jeśli to ustawienie zasad zostanie włączone, zachowania danych binarnych i skryptów będą dostępne. Jeśli w polu listy rozwijanej wybierzesz pozycję Zatwierdzone przez administratora, dostępne będą tylko zachowania zatwierdzone przez administratora w ramach zasad ograniczenia zabezpieczeń zachowań danych binarnych. Jeśli to ustawienie zasad zostanie wyłączone, zachowania danych binarnych i skryptów nie będą dostępne, o ile aplikacje nie mają zaimplementowanego niestandardowego menedżera zabezpieczeń. Jeśli to ustawienie zasad nie zostanie skonfigurowane, zachowania danych binarnych i skryptów nie będą dostępne, o ile aplikacje nie mają zaimplementowanego niestandardowego menedżera zabezpieczeń.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Sprawdzanie ustawień zabezpieczeń programu Internet Explorer**  </br>
  To ustawienie zasad powoduje wyłączenie funkcji sprawdzania ustawień zabezpieczeń, która sprawdza ustawienia zabezpieczeń programu Internet Explorer, aby określić, kiedy ustawienia stanowią zagrożenie dla programu Internet Explorer. Jeśli to ustawienie zasad zostanie włączone, funkcja zostanie wyłączona. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, funkcja zostanie włączona.
  - **Ustawienie domyślne**: Enabled  
  
- **Ostrzeżenie o zabezpieczeniach strefy internetowej dla potencjalnie niebezpiecznych plików w programie Internet Explorer**  
  To ustawienie zasad określa, czy komunikat „Otwieranie pliku — ostrzeżenie o zabezpieczeniach” pojawia się, gdy użytkownik próbuje otworzyć pliki wykonywalne lub inne potencjalnie niebezpieczne pliki (na przykład z udziału plików w intranecie za pomocą Eksploratora plików). Jeśli to ustawienie zasad zostanie włączone i w polu listy rozwijanej zostanie ustawiona wartość Włącz, te pliki będą otwierane bez ostrzeżenia o zabezpieczeniach. Jeśli w polu listy rozwijanej ustawisz wartość Monituj, przed otwarciem plików pojawi się ostrzeżenie o zabezpieczeniach. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można otworzyć tych plików. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł skonfigurować sposób obsługi tych plików przez komputer. Domyślnie te pliki są zablokowane w strefie z ograniczeniami, włączone w strefie intranetu i komputera lokalnego oraz mają ustawione monitowanie w strefie Internetu i zaufanej strefie.
  - **Ustawienie domyślne**: Monit  
  
- **Uprawnienia języka Java w strefie intranetowej programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie uprawnieniami dotyczącymi apletów Java. Jeśli to ustawienie zasad zostanie włączone, będzie można wybierać opcje z listy rozwijanej. Ustawienie Niestandardowe umożliwia kontrolowanie ustawień uprawnień pojedynczo. Ustawienie Niski poziom zabezpieczeń umożliwia apletom wykonywanie wszystkich operacji. Ustawienie Średni poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy (obszarze pamięci, poza którym program nie może wykonywać wywołań) oraz udostępnia funkcje, takie jak obszar na pliki tymczasowe (bezpieczny obszar magazynu na komputerze klienckim) i kontrolowane przez użytkownika operacje we/wy na plikach. Ustawienie Wysoki poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy. Wyłącz język Java, aby uniemożliwić uruchamianie jakichkolwiek apletów. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można uruchamiać apletów Java. Jeśli to ustawienie zasad nie zostanie skonfigurowane, zostaną ustawione uprawnienia na Średni poziom zabezpieczeń.
  - **Ustawienie domyślne**: Wysoki poziom zabezpieczeń 
  
- **Blokowanie nieaktualnych kontrolek ActiveX w programie Internet Explorer**  </br>
  To ustawienie zasad określa, czy program Internet Explorer ma blokować nieaktualne kontrolki ActiveX. Nieaktualne kontrolki ActiveX nigdy nie są blokowane w strefie intranetowej. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer przestanie blokować nieaktualne kontrolki ActiveX. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, program Internet Explorer będzie nadal blokować określone nieaktualne kontrolki ActiveX. Więcej informacji można znaleźć na stronie „Nieaktualne kontrolki ActiveX” w bibliotece TechNet programu Internet Explorer.
  - **Ustawienie domyślne**: Enabled  
  
- **Blokowanie okien podręcznych w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad pozwala określić, czy mają być wyświetlane niechciane okna podręczne. Okna podręczne otwierane, gdy użytkownik końcowy kliknie link, nie są blokowane. Jeśli to ustawienie zasad zostanie włączone, większość niechcianych okien podręcznych nie będzie wyświetlana. Jeśli to ustawienie zasad zostanie wyłączone, wyświetlanie okien podręcznych nie będzie blokowane. Jeśli to ustawienie zasad nie zostanie skonfigurowane, większość niechcianych okien podręcznych nie będzie wyświetlana.
  - **Ustawienie domyślne**: Włącz  
  
- **Ograniczenia zabezpieczeń protokołu MK w procesach programu Internet Explorer**  
  Ustawienie zasad ograniczeń zabezpieczeń protokołu MK uniemożliwia korzystanie z protokołu MK, zmniejszając w ten sposób obszar powierzchni ataku. Korzystanie z zasobów obsługiwanych przez protokół MK nie będzie możliwe. Jeśli to ustawienie zasad zostanie włączone, protokół MK będzie zabroniony dla Eksploratora plików i przeglądarki Internet Explorer, a korzystanie z zasobów obsługiwanych przez protokół MK nie będzie możliwe. Jeśli to ustawienie zasad zostanie wyłączone, aplikacje będą mogły używać interfejsu API protokołu MK. Zasoby obsługiwane przez protokół MK będą działały w przypadku procesów Eksploratora plików i przeglądarki Internet Explorer. Jeśli to ustawienie zasad nie zostanie skonfigurowane, protokół MK będzie zabroniony dla Eksploratora plików i przeglądarki Internet Explorer, a korzystanie z zasobów obsługiwanych przez protokół MK nie będzie możliwe.
  - **Ustawienie domyślne**: Enabled  
  
- **Uprawnienia języka Java w strefie zaufanej programu Internet Explorer**  </br>
  To ustawienie zasad umożliwia zarządzanie uprawnieniami dotyczącymi apletów Java. Jeśli to ustawienie zasad zostanie włączone, będzie można wybierać opcje z listy rozwijanej. Ustawienie Niestandardowe umożliwia kontrolowanie ustawień uprawnień pojedynczo. Ustawienie Niski poziom zabezpieczeń umożliwia apletom wykonywanie wszystkich operacji. Ustawienie Średni poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy (obszarze pamięci, poza którym program nie może wykonywać wywołań) oraz udostępnia funkcje, takie jak obszar na pliki tymczasowe (bezpieczny obszar magazynu na komputerze klienckim) i kontrolowane przez użytkownika operacje we/wy na plikach. Ustawienie Wysoki poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy. Wyłącz język Java, aby uniemożliwić uruchamianie jakichkolwiek apletów. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można uruchamiać apletów Java. Jeśli to ustawienie zasad nie zostanie skonfigurowane, zostaną ustawione uprawnienia Niski poziom zabezpieczeń.
  - **Ustawienie domyślne**: Wysoki poziom zabezpieczeń  
  
- **Wykonywanie skryptów apletów Java w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie dostępnością apletów dla skryptów w strefie. Jeśli to ustawienie zasad zostanie włączone, skrypty będą mogły automatycznie uzyskiwać dostęp do apletów bez interwencji użytkownika. Jeśli w polu listy rozwijanej wybierzesz wartość Monit, użytkownicy będą proszeni o wybranie, czy zezwalać skryptom na dostęp do apletów. Jeśli to ustawienie zasad zostanie wyłączone, skrypty nie będą mogły uzyskiwać dostępu do apletów. Jeśli to ustawienie zasad nie zostanie skonfigurowane, skrypty nie będą mogły uzyskiwać dostępu do apletów.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Zablokowane uprawnienia języka Java w strefie z ograniczeniami w programie Internet Explorer**  </br>
  To ustawienie zasad umożliwia zarządzanie uprawnieniami dotyczącymi apletów Java. Jeśli to ustawienie zasad zostanie włączone, będzie można wybierać opcje z listy rozwijanej. Ustawienie Niestandardowe umożliwia kontrolowanie ustawień uprawnień pojedynczo. Ustawienie Niski poziom zabezpieczeń umożliwia apletom wykonywanie wszystkich operacji. Ustawienie Średni poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy (obszarze pamięci, poza którym program nie może wykonywać wywołań) oraz udostępnia funkcje, takie jak obszar na pliki tymczasowe (bezpieczny obszar magazynu na komputerze klienckim) i kontrolowane przez użytkownika operacje we/wy na plikach. Ustawienie Wysoki poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy. Wyłącz język Java, aby uniemożliwić uruchamianie jakichkolwiek apletów. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można uruchamiać apletów Java. Jeśli to ustawienie zasad nie zostanie skonfigurowane, aplety Java będą wyłączone.
  - **Ustawienie domyślne**: Wyłącz Java 
  
- **Strefa internetowa w programie Internet Explorer zezwala na używanie kontrolek ActiveX tylko przez zatwierdzone domeny**  </br>
  To ustawienie zasad określa, czy użytkownik będzie proszony o wyrażenie zgody na uruchamianie kontrolek ActiveX w witrynach internetowych innych niż witryna internetowa, która zainstalowała kontrolkę ActiveX. Jeśli to ustawienie zasad zostanie włączone, użytkownik będzie proszony o wyrażenie zgody na uruchamianie kontrolek ActiveX z witryn internetowych w tej strefie. Użytkownik może zezwolić na uruchamianie kontrolki z bieżącej witryny lub ze wszystkich witryn. Jeśli to ustawienie zasad zostanie wyłączone, w poszczególnych witrynach nie będzie wyświetlany monit kontrolki ActiveX i będzie można uruchamiać kontrolki ActiveX ze wszystkich witryn w tej strefie.
  - **Ustawienie domyślne**: Enabled  
  
- **Program Internet Explorer zawiera wszystkie ścieżki sieciowe**  
  Program Internet Explorer zawiera wszystkie ścieżki sieciowe
  - **Ustawienie domyślne**: Wyłącz 
  
- **Tryb chroniony w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad umożliwia włączenie trybu chronionego. Tryb chroniony ułatwia ochronę programu Internet Explorer przed wykorzystywaniem luk w zabezpieczeniach, zmniejszając liczbę lokalizacji, w których program Internet Explorer może zapisywać w rejestrze i w systemie plików. Jeśli to ustawienie zasad zostanie włączone, tryb chroniony będzie włączony. Użytkownik nie będzie mógł wyłączyć trybu chronionego. Jeśli to ustawienie zasad zostanie wyłączone, tryb chroniony będzie wyłączony. Użytkownik nie będzie mógł włączyć trybu chronionego. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł włączać i wyłączać tryb chroniony.
  - **Ustawienie domyślne**: Włącz 
  
- **Strefa internetowa w programie Internet Explorer pozwala inicjować i wykonywać skrypty kontrolek ActiveX, które nie są oznaczone jako bezpieczne**  
  To ustawienie zasad umożliwia zarządzanie kontrolkami ActiveX, które nie są oznaczone jako bezpieczne. Jeśli to ustawienie zasad zostanie włączone, kontrolki ActiveX będą uruchamiane i ładowane z parametrami oraz będą wykonywane ich skrypty bez konieczności ustawiania poziomu bezpieczeństwa obiektów dla niezaufanych danych lub skryptów. To ustawienie nie jest zalecane poza strefami bezpiecznymi i administrowanymi. To ustawienie umożliwia inicjowanie i wykonywanie skryptów zarówno bezpiecznych, jak i niebezpiecznych kontrolek, z jednoczesnym ignorowaniem opcji Wykonaj skrypty kontrolek ActiveX zaznaczone jako bezpieczne. Jeśli to ustawienie zasad zostanie włączone i w polu listy rozwijanej zostanie wybrana pozycja Monituj, użytkownicy będą pytani, czy zezwolić na ładowanie kontrolek z parametrami lub inicjowanych przez skrypty. Jeśli to ustawienie zasad zostanie wyłączone, kontrolki ActiveX, które nie mogą stać się bezpieczne, nie będą ładowane z parametrami ani nie będą wykonywane ich skrypty. Jeśli to ustawienie zasad nie zostanie skonfigurowane, kontrolki ActiveX, które nie mogą stać się bezpieczne, nie będą ładowane z parametrami ani nie będą wykonywane ich skrypty.
  - **Ustawienie domyślne**: Wyłącz 
  
- **Zablokowany filtr SmartScreen w strefie z ograniczeniami w programie Internet Explorer**  </br>
  To ustawienie zasad określa, czy filtr SmartScreen skanuje strony w tej strefie pod kątem złośliwej zawartości. Jeśli to ustawienie zasad zostanie włączone, filtr SmartScreen będzie skanować strony w tej strefie pod kątem złośliwej zawartości. Jeśli to ustawienie zasad zostanie wyłączone, filtr SmartScreen nie będzie skanować stron w tej strefie pod kątem złośliwej zawartości. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł wybrać, czy filtr SmartScreen ma skanować strony w tej strefie pod kątem złośliwej zawartości. Uwaga: W programie Internet Explorer 7 to ustawienie zasad określa, czy filtr wyłudzania informacji skanuje strony w tej strefie pod kątem złośliwej zawartości.
  - **Ustawienie domyślne**: Enabled  
  
- **Wykrywanie awarii w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie funkcją wykrywania awarii Zarządzania dodatkami. Jeśli to ustawienie zasad zostanie włączone, awaria w programie Internet Explorer będzie powodowała zachowanie typowe dla systemu Windows XP Professional z dodatkiem Service Pack 1 lub starszego, to znaczy będzie wywoływać Raportowanie błędów systemu Windows. Wciąż będą obowiązywały wszystkie ustawienia zasad dla Raportowania błędów systemu Windows. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, funkcja wykrywania awarii zarządzania dodatkami będzie działała.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Uprawnienia języka Java w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie uprawnieniami dotyczącymi apletów Java. Jeśli to ustawienie zasad zostanie włączone, będzie można wybierać opcje z listy rozwijanej. Ustawienie Niestandardowe umożliwia kontrolowanie ustawień uprawnień pojedynczo. Ustawienie Niski poziom zabezpieczeń umożliwia apletom wykonywanie wszystkich operacji. Ustawienie Średni poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy (obszarze pamięci, poza którym program nie może wykonywać wywołań) oraz udostępnia funkcje, takie jak obszar na pliki tymczasowe (bezpieczny obszar magazynu na komputerze klienckim) i kontrolowane przez użytkownika operacje we/wy na plikach. Ustawienie Wysoki poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy. Wyłącz język Java, aby uniemożliwić uruchamianie jakichkolwiek apletów. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można uruchamiać apletów Java. Jeśli to ustawienie zasad nie zostanie skonfigurowane, zostaną ustawione uprawnienia Wysoki poziom zabezpieczeń.
  - **Ustawienie domyślne**: Wyłącz Java  
  
- **Aktywne wykonywanie skryptów w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie uruchamianiem kodu skryptu na stronach w strefie. Jeśli to ustawienie zasad zostanie włączone, będzie można uruchamiać kod skryptu na stronach w strefie. Jeśli w polu listy rozwijanej wybierzesz wartość Monit, użytkownicy będą proszeni o wybranie, czy zezwalać na uruchamianie kodu skryptu na stronach w strefie. Jeśli to ustawienie zasad zostanie wyłączone, uruchamianie kodu skryptu na stronach w strefie nie będzie możliwe. Jeśli to ustawienie zasad nie zostanie skonfigurowane, uruchamianie kodu skryptu na stronach w strefie nie będzie możliwe.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Opcje logowania w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie ustawieniami opcji logowania. Jeśli to ustawienie zasad zostanie włączone, będzie można wybierać poniższe opcje logowania. Użyj logowania anonimowego, aby wyłączyć uwierzytelnianie HTTP i używać konta gościa tylko dla protokołu CIFS (Common Internet File System). Monituj o podanie nazwy użytkownika i hasła, aby wysyłać zapytania do użytkowników dotyczące identyfikatorów użytkowników i haseł. Po wysłaniu zapytania do użytkownika można używać tych wartości dyskretnie w pozostałej części sesji. Zaloguj automatycznie tylko w strefie intranetu, aby wysyłać do użytkowników zapytania dotyczące identyfikatorów użytkowników i haseł w innych strefach. Po wysłaniu zapytania do użytkownika można używać tych wartości dyskretnie w pozostałej części sesji. Użyj automatycznego logowania przy użyciu bieżącej nazwy użytkownika i hasła, aby spróbować zalogować się przy użyciu odpowiedzi na żądanie systemu Windows NT (uwierzytelnianie NTLM). Jeśli odpowiedź na żądanie systemu Windows NT jest obsługiwana przez serwer, podczas logowania są używane nazwa użytkownika i hasło sieci użytkownika. Jeśli odpowiedź na żądanie systemu Windows NT nie jest obsługiwana przez serwer, użytkownik zostanie poproszony o podanie nazwy użytkownika i hasła. Jeśli to ustawienie zasad zostanie wyłączone, zostanie ustawione automatyczne logowanie tylko w strefie intranetu. Jeśli to ustawienie zasad nie zostanie skonfigurowane, zostanie ustawione automatyczne logowanie tylko w strefie intranetu.
  - **Ustawienie domyślne**: Monit  
  
- **Zezwalanie na uruchamianie skryptu VBScript w strefie z ograniczeniami w programie Internet Explorer**  </br>  
  To ustawienie zasad pozwala określić, czy skrypt VBScript może być uruchamiany na stronach z określonej strefy w programie Internet Explorer. Jeśli w polu listy rozwijanej wybierzesz wartość Włącz, skrypt VBScript będzie można uruchamiać bez interwencji użytkownika. Jeśli w polu listy rozwijanej wybierzesz wartość Monit, użytkownicy będą proszeni o wybranie, czy zezwalać na uruchamianie skryptu VBScript. Jeśli w polu listy rozwijanej wybierzesz wartość Wyłącz, nie będzie można uruchamiać skryptu VBScript. Jeśli to ustawienie zasad nie zostanie skonfigurowane lub zostanie wyłączone, uruchamianie skryptu VBScript nie będzie możliwe.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Przeciąganie zawartości z innych domen między oknami w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad umożliwia ustawianie opcji przeciągania zawartości między domenami, gdy źródło i lokalizacja docelowa znajdują się w różnych oknach. Jeśli to ustawienie zasad zostanie włączone i klikniesz pozycję Włącz, użytkownicy będą mogli przeciągać zawartość między domenami, gdy źródło i lokalizacja docelowa znajdują się w różnych oknach. Użytkownicy nie mogą zmieniać tego ustawienia. Jeśli to ustawienie zasad zostanie włączone i klikniesz pozycję Wyłącz, użytkownicy nie będą mogli przeciągać zawartości z jednej domeny do innej, gdy zarówno miejsce źródłowe, jak i docelowe będą w różnych oknach. Użytkownicy nie mogą zmieniać tego ustawienia. W programie Internet Explorer 10, jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownicy nie będą mogli przeciągać zawartości z jednej domeny do innej, gdy miejsce źródłowe i docelowe będą w różnych oknach. Użytkownicy mogą zmieniać to ustawienie w oknie dialogowym Opcje internetowe. W programie Internet Explorer 9 lub jego starszych wersjach, jeśli te zasady zostaną wyłączone lub nie zostaną skonfigurowane, użytkownicy będą mogli przeciągać zawartość z jednej domeny do innej, gdy miejsce źródłowe i docelowe będą w różnych oknach. Użytkownicy nie mogą zmieniać tego ustawienia.
  - **Ustawienie domyślne**: Wyłącz 
  
- **Strefa intranetowa w programie Internet Explorer pozwala inicjować i wykonywać skrypty kontrolek ActiveX, które nie są oznaczone jako bezpieczne**  
  To ustawienie zasad umożliwia zarządzanie kontrolkami ActiveX, które nie są oznaczone jako bezpieczne. Jeśli to ustawienie zasad zostanie włączone, kontrolki ActiveX będą uruchamiane i ładowane z parametrami oraz będą wykonywane ich skrypty bez konieczności ustawiania poziomu bezpieczeństwa obiektów dla niezaufanych danych lub skryptów. To ustawienie nie jest zalecane poza strefami bezpiecznymi i administrowanymi. To ustawienie umożliwia inicjowanie i wykonywanie skryptów zarówno bezpiecznych, jak i niebezpiecznych kontrolek, z jednoczesnym ignorowaniem opcji Wykonaj skrypty kontrolek ActiveX zaznaczone jako bezpieczne. Jeśli to ustawienie zasad zostanie włączone i w polu listy rozwijanej zostanie wybrana pozycja Monituj, użytkownicy będą pytani, czy zezwolić na ładowanie kontrolek z parametrami lub inicjowanych przez skrypty. Jeśli to ustawienie zasad zostanie wyłączone, kontrolki ActiveX, które nie mogą stać się bezpieczne, nie będą ładowane z parametrami ani nie będą wykonywane ich skrypty. Jeśli to ustawienie zasad nie zostanie skonfigurowane, kontrolki ActiveX, które nie mogą stać się bezpieczne, nie będą ładowane z parametrami ani nie będą wykonywane ich skrypty.
  - **Ustawienie domyślne**: Wyłącz 
  
- **Pobieranie załączników w programie Internet Explorer**  
  To ustawienie zasad uniemożliwia użytkownikowi pobieranie załączników (w postaci plików) ze źródła danych na komputer użytkownika. Jeśli to ustawienie zasad zostanie włączone, użytkownik nie będzie mógł ustawić pobierania załącznika przez aparat synchronizacji źródła danych za pośrednictwem strony właściwości źródła danych. Deweloper nie będzie mógł zmienić ustawienia pobierania za pośrednictwem interfejsów API źródła danych. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownik będzie mógł ustawić pobieranie załącznika przez aparat synchronizacji źródła danych za pośrednictwem strony właściwości źródła danych. Deweloper będzie mógł zmienić ustawienie pobierania za pośrednictwem interfejsów API źródła danych.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Pobieranie niepodpisanych kontrolek ActiveX w strefie z ograniczeniami w programie Internet Explorer**  </br>
  To ustawienie zasad umożliwia zarządzanie tym, czy użytkownicy mogą pobierać niepodpisane kontrolki ActiveX ze strefy. Tego rodzaju kod jest potencjalnie szkodliwy, zwłaszcza gdy pochodzi z niezaufanej strefy. Jeśli to ustawienie zasad zostanie włączone, użytkownicy będą mogli uruchamiać niepodpisane kontrolki bez interwencji użytkownika. Jeśli w polu listy rozwijanej zostanie wybrana pozycja Monit, użytkownicy będą proszeni o wybranie, czy zezwalać na uruchamianie niepodpisanych kontrolek. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli uruchamiać niepodpisanych kontrolek. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy nie będą mogli uruchamiać niepodpisanych kontrolek.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Przeciąganie zawartości z innych domen w obrębie okien w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie tym, czy użytkownicy mogą pobierać niepodpisane kontrolki ActiveX ze strefy. Tego rodzaju kod jest potencjalnie szkodliwy, zwłaszcza gdy pochodzi z niezaufanej strefy. Jeśli to ustawienie zasad zostanie włączone, użytkownicy będą mogli uruchamiać niepodpisane kontrolki bez interwencji użytkownika. Jeśli w polu listy rozwijanej zostanie wybrana pozycja Monit, użytkownicy będą proszeni o wybranie, czy zezwalać na uruchamianie niepodpisanych kontrolek. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli uruchamiać niepodpisanych kontrolek. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy nie będą mogli uruchamiać niepodpisanych kontrolek.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Procesy programu Internet Explorer ograniczają instalowanie kontrolek ActiveX**  </br>
  To ustawienie zasad umożliwia aplikacjom hostującym kontrolkę przeglądarki internetowej blokowanie automatycznego monitowania o instalowanie kontrolek ActiveX. Jeśli to ustawienie zasad zostanie włączone, kontrolka przeglądarki internetowej będzie blokowała dla wszystkich procesów automatyczne monitowanie o instalowanie kontrolek ActiveX. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, kontrolka przeglądarki internetowej nie będzie blokowała dla wszystkich procesów automatycznego monitowania o instalowanie kontrolek ActiveX.
  - **Ustawienie domyślne**: Enabled  
  
- **Skryptlety strefy internetowej programu Internet Explorer** To ustawienie zasad pozwala określić, czy użytkownik może uruchamiać skryptlety. Jeśli to ustawienie zasad zostanie włączone, użytkownik będzie mógł uruchamiać skryptlety. Jeśli to ustawienie zasad zostanie wyłączone, użytkownik nie będzie mógł uruchamiać skryptletów. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł włączać lub wyłączać skryptlety.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Przeciąganie i upuszczanie lub kopiowanie i wklejanie plików w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie tym, czy użytkownicy będą mogli przeciągać pliki lub kopiować i wklejać pliki ze źródła w strefie. Jeśli to ustawienie zasad zostanie włączone, użytkownicy będą mogli automatycznie przeciągać pliki lub kopiować i wklejać pliki z tej strefy. Jeśli w polu listy rozwijanej zostanie wybrana wartość Monit, użytkownicy będą proszeni o wybranie, czy przeciągać lub kopiować pliki z tej strefy. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli przeciągać plików ani kopiować i wklejać plików z tej strefy. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy będą proszeni o wybranie, czy przeciągać lub kopiować pliki z tej strefy.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Oprogramowanie przeglądarki Internet Explorer w przypadku nieprawidłowego podpisu** </br>
  To ustawienie zasad umożliwia zarządzanie tym, czy oprogramowanie, takie jak kontrolki ActiveX i funkcje pobierania plików, może być instalowane lub uruchamiane przez użytkownika, nawet jeśli podpis jest nieprawidłowy. Nieprawidłowy podpis może oznaczać, że ktoś naruszył plik. Jeśli to ustawienie zasad zostanie włączone, użytkownicy będą monitowani o instalowanie lub uruchamianie plików z nieprawidłowym podpisem. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli uruchamiać ani instalować plików z nieprawidłowym podpisem. Jeśli te zasady nie zostaną skonfigurowane, użytkownicy będą mogli wybrać, czy pliki z nieprawidłowym podpisem mają być uruchamiane lub instalowane.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Kopiowanie i wklejanie za pomocą skryptu w strefie z ograniczeniami w programie Internet Explorer** </br> To ustawienie zasad umożliwia zarządzanie tym, czy skrypty mogą wykonać operację schowka (na przykład wycięcie, skopiowanie i wklejenie) w określonym regionie. Jeśli to ustawienie zasad zostanie włączone, skrypt będzie mógł wykonać operację schowka. Jeśli w polu listy rozwijanej zostanie wybrana pozycja Monit, użytkownicy będą pytani, czy można wykonać operacje schowka. Jeśli to ustawienie zasad zostanie wyłączone, skrypt nie będzie mógł wykonać operacji schowka. Jeśli to ustawienie zasad nie zostanie skonfigurowane, skrypt nie będzie mógł wykonać operacji schowka.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Przeciąganie zawartości z innych domen między oknami w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia ustawianie opcji przeciągania zawartości między domenami, gdy źródło i lokalizacja docelowa znajdują się w różnych oknach. Jeśli to ustawienie zasad zostanie włączone i klikniesz pozycję Włącz, użytkownicy będą mogli przeciągać zawartość między domenami, gdy źródło i lokalizacja docelowa znajdują się w różnych oknach. Użytkownicy nie mogą zmieniać tego ustawienia. Jeśli to ustawienie zasad zostanie włączone i klikniesz pozycję Wyłącz, użytkownicy nie będą mogli przeciągać zawartości z jednej domeny do innej, gdy zarówno miejsce źródłowe, jak i docelowe będą w różnych oknach. Użytkownicy nie mogą zmieniać tego ustawienia. W programie Internet Explorer 10, jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownicy nie będą mogli przeciągać zawartości z jednej domeny do innej, gdy miejsce źródłowe i docelowe będą w różnych oknach. Użytkownicy mogą zmieniać to ustawienie w oknie dialogowym Opcje internetowe. W programie Internet Explorer 9 lub jego starszych wersjach, jeśli te zasady zostaną wyłączone lub nie zostaną skonfigurowane, użytkownicy będą mogli przeciągać zawartość z jednej domeny do innej, gdy miejsce źródłowe i docelowe będą w różnych oknach. Użytkownicy nie mogą zmieniać tego ustawienia.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Użytkownicy programu Internet Explorer dodający witryny**  
  Uniemożliwia użytkownikom dodawanie i usuwanie witryn ze stref zabezpieczeń. Strefa zabezpieczeń to grupa witryn internetowych na tym samym poziomie zabezpieczeń. Włączenie tych zasad spowoduje wyłączenie ustawień zarządzania witrynami dla stref zabezpieczeń. (Aby zobaczyć ustawienia zarządzania witrynami dla stref zabezpieczeń, w oknie dialogowym Opcje internetowe kliknij kartę Zabezpieczenia, a następnie kliknij przycisk Witryny). Jeśli te zasady zostaną wyłączone lub nie zostaną skonfigurowane, użytkownicy będą mogli dodawać witryny internetowe do stref Zaufane witryny lub Witryny z ograniczeniami bądź je stamtąd usuwać, a także zmieniać ustawienia strefy Lokalny intranet. Te zasady uniemożliwiają użytkownikom zmianę ustawień zarządzania witrynami dla stref zabezpieczeń ustanowionych przez administratora. Uwaga: Zasady „Wyłącz stronę Zabezpieczenia” (znajdujące się w katalogu \User Configuration\Administrative Templates\Windows Components\Internet Explorer\Internet Control Panel), które powodują usunięcie karty Zabezpieczenia z interfejsu, mają pierwszeństwo przed tymi zasadami. Jeśli zostaną włączone, omawiane tu zasady będą ignorowane. Zobacz też zasady „Strefy zabezpieczeń: Używaj tylko ustawień komputera”.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Okna inicjowane przez skrypty w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie ograniczeniami dotyczącymi okien podręcznych oraz okien zawierających paski tytułu i stanu inicjowanych przez skrypty. Jeśli to ustawienie zasad zostanie włączone, zabezpieczenia Ograniczenia systemu Windows nie będą stosowane w tej strefie. Strefa zabezpieczeń będzie działać bez dodatkowej warstwy zabezpieczeń udostępnianej przez tę funkcję. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie możliwe uruchamianie potencjalnie szkodliwych akcji zawartych w oknach podręcznych oraz oknach zawierających paski tytułu i stanu inicjowanych przez skrypty. Ta funkcja zabezpieczeń programu Internet Explorer będzie włączona w tej strefie zgodnie z ustawieniem sterowania funkcją Ograniczenia zabezpieczeń okien inicjowanych przez skrypty dla procesu. Jeśli to ustawienie zasad nie zostanie skonfigurowane, nie będzie możliwe uruchamianie potencjalnie szkodliwych akcji zawartych w oknach podręcznych oraz oknach zawierających paski tytułu i stanu inicjowanych przez skrypty. Ta funkcja zabezpieczeń programu Internet Explorer będzie włączona w tej strefie zgodnie z ustawieniem sterowania funkcją Ograniczenia zabezpieczeń okien inicjowanych przez skrypty dla procesu.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Strefy zabezpieczeń programu Internet Explorer używają tylko ustawień komputera**  
  Stosuje informacje o strefie zabezpieczeń do wszystkich użytkowników tego samego komputera. Strefa zabezpieczeń to grupa witryn internetowych na tym samym poziomie zabezpieczeń. Jeśli te zasady zostaną włączone, zmiany wprowadzone przez użytkownika w strefie zabezpieczeń będą dotyczyły wszystkich użytkowników tego komputera. Jeśli te zasady zostaną wyłączone lub nie zostaną skonfigurowane, użytkownicy tego samego komputera będą mogli określać własne ustawienia stref zabezpieczeń. Te zasady mają zapewnić jednolite stosowanie ustawień stref zabezpieczeń na tym samym komputerze dla wszystkich użytkowników. Zobacz też zasady „Strefy zabezpieczeń: Nie zezwalaj użytkownikom na zmienianie zasad”.
  - **Ustawienie domyślne**: Enabled  
  
- **Zablokowane uprawnienia języka Java w strefie komputera lokalnego programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie uprawnieniami dotyczącymi apletów Java. Jeśli to ustawienie zasad zostanie włączone, będzie można wybierać opcje z listy rozwijanej. Ustawienie Niestandardowe umożliwia kontrolowanie ustawień uprawnień pojedynczo. Ustawienie Niski poziom zabezpieczeń umożliwia apletom wykonywanie wszystkich operacji. Ustawienie Średni poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy (obszarze pamięci, poza którym program nie może wykonywać wywołań) oraz udostępnia funkcje, takie jak obszar na pliki tymczasowe (bezpieczny obszar magazynu na komputerze klienckim) i kontrolowane przez użytkownika operacje we/wy na plikach. Ustawienie Wysoki poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy. Wyłącz język Java, aby uniemożliwić uruchamianie jakichkolwiek apletów. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można uruchamiać apletów Java. Jeśli to ustawienie zasad nie zostanie skonfigurowane, aplety Java będą wyłączone
  - **Ustawienie domyślne**: Wyłącz Java 
  
- **Strefa z ograniczeniami w programie Internet Explorer nie uruchamia oprogramowania chroniącego przed złośliwym oprogramowaniem względem kontrolek ActiveX**  </br>
  To ustawienie zasad określa, czy program Internet Explorer uruchamia programy chroniące przed złośliwym oprogramowaniem względem kontrolek ActiveX w celu sprawdzenia, czy można bezpiecznie ładować je na stronach. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer nie będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Jeśli to ustawienie zasad zostanie wyłączone, program Internet Explorer zawsze będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Jeśli to ustawienie zasad nie zostanie skonfigurowane, program Internet Explorer zawsze będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Użytkownicy mogą włączać i wyłączać to zachowanie przy użyciu ustawień zabezpieczeń programu Internet Explorer.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Strefa z ograniczeniami w programie Internet Explorer uruchamia składniki uzależnione od platformy .NET Framework podpisane przy użyciu technologii Authenticode**  
  To ustawienie zasad umożliwia zarządzanie tym, czy składniki .NET Framework podpisane przy użyciu technologii Authenticode mogą być wykonywane w programie Internet Explorer. Do tych składników należą zarządzane kontrolki przywoływane z tagu obiektu oraz zarządzane pliki wykonywalne przywoływane z linku. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer będzie wykonywał podpisane składniki zarządzane. Jeśli w polu listy rozwijanej wybierzesz wartość Monituj, program Internet Explorer będzie prosił użytkownika o określenie, czy może wykonywać podpisane składniki zarządzane. Jeśli to ustawienie zasad zostanie wyłączone, program Internet Explorer nie będzie wykonywał podpisanych składników zarządzanych. Jeśli to ustawienie zasad nie zostanie skonfigurowane, program Internet Explorer nie będzie wykonywał podpisanych składników zarządzanych.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Dostęp strefy z ograniczeniami w programie Internet Explorer do źródeł danych**  
  To ustawienie zasad umożliwia zarządzanie tym, czy program Internet Explorer może uzyskiwać dostęp do danych z innej strefy zabezpieczeń przy użyciu programu Microsoft XML Parser (MSXML) lub ActiveX Data Objects (ADO). Jeśli to ustawienie zasad zostanie włączone, użytkownicy będą mogli załadować stronę w strefie używającej programu MSXML lub ADO w celu uzyskania dostępu do danych z innej witryny w strefie. Jeśli w polu listy rozwijanej zostanie wybrana pozycja Monituj, użytkownicy będą proszeni o wybranie, czy zezwolić na załadowanie strony w strefie używającej programu MSXML lub ADO w celu uzyskania dostępu do danych z innej witryny w strefie. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli załadować strony w strefie używającej programu MSXML lub ADO w celu uzyskania dostępu do danych z innej witryny w strefie. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy nie będą mogli załadować strony w strefie używającej programu MSXML lub ADO w celu uzyskania dostępu do danych z innej witryny w strefie.
  - **Ustawienie domyślne**: Wyłącz 
  
- **Strefa internetowa w programie Internet Explorer nie uruchamia oprogramowania chroniącego przed złośliwym oprogramowaniem względem kontrolek ActiveX**  </br>
  To ustawienie zasad określa, czy program Internet Explorer uruchamia programy chroniące przed złośliwym oprogramowaniem względem kontrolek ActiveX w celu sprawdzenia, czy można bezpiecznie ładować je na stronach. Jeśli to ustawienie zasad zostanie włączone, program Internet Explorer nie będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Jeśli to ustawienie zasad zostanie wyłączone, program Internet Explorer zawsze będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Jeśli to ustawienie zasad nie zostanie skonfigurowane, program Internet Explorer zawsze będzie sprawdzał za pomocą programu chroniącego przed złośliwym oprogramowaniem, czy utworzenie wystąpienia kontrolki ActiveX jest bezpieczne. Użytkownicy mogą włączać i wyłączać to zachowanie przy użyciu ustawień zabezpieczeń programu Internet Explorer.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Kopiowanie i wklejanie za pomocą skryptu w strefie internetowej programu Internet Explorer** </br> To ustawienie zasad umożliwia zarządzanie tym, czy skrypty mogą wykonać operację schowka (na przykład wycięcie, skopiowanie i wklejenie) w określonym regionie. Jeśli to ustawienie zasad zostanie włączone, skrypt będzie mógł wykonać operację schowka. Jeśli w polu listy rozwijanej zostanie wybrana pozycja Monit, użytkownicy będą pytani, czy można wykonać operacje schowka. Jeśli to ustawienie zasad zostanie wyłączone, skrypt nie będzie mógł wykonać operacji schowka. Jeśli to ustawienie zasad nie zostanie skonfigurowane, skrypt będzie mógł wykonać operację schowka.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Program Internet Explorer używa usługi instalatora ActiveX**  </br>
  To ustawienie zasad pozwala określić sposób instalowania kontrolek ActiveX. Jeśli to ustawienie zasad zostanie włączone, kontrolki ActiveX będą instalowane tylko wtedy, gdy usługa instalatora kontrolek ActiveX jest obecna i została skonfigurowana tak, aby umożliwiać instalowanie kontrolek ActiveX. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, kontrolki ActiveX, w tym kontrolki użytkownika, będą instalowane za pośrednictwem standardowego procesu instalacji.
  - **Ustawienie domyślne**: Enabled  
  
- **Ochrona procesów programu Internet Explorer przed podnoszeniem uprawnień strefy**  
  Program Internet Explorer stosuje ograniczenia na każdej otwieranej stronie internetowej. Ograniczenia są zależne od lokalizacji strony internetowej (Internet, intranet, strefa komputera lokalnego itd.). Na przykład strony internetowe na komputerze lokalnym mają najmniejsze ograniczenia zabezpieczeń i znajdują się w strefie Komputer lokalny, co sprawia, że strefa zabezpieczeń Komputer lokalny staje się głównym celem dla złośliwych użytkowników. Jeśli to ustawienie zasad zostanie włączone, dowolna strefa będzie mogła być chroniona przed podniesieniem uprawnień strefy dla wszystkich procesów. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, procesy inne niż związane z programem Internet Explorer lub wymienione na liście procesów nie otrzymają takiej ochrony.
  - **Ustawienie domyślne**: Enabled  
  
- **Pobieranie niepodpisanych kontrolek ActiveX w strefie internetowej programu Internet Explorer**  </br>
  To ustawienie zasad umożliwia zarządzanie tym, czy użytkownicy mogą pobierać niepodpisane kontrolki ActiveX ze strefy. Tego rodzaju kod jest potencjalnie szkodliwy, zwłaszcza gdy pochodzi z niezaufanej strefy. Jeśli to ustawienie zasad zostanie włączone, użytkownicy będą mogli uruchamiać niepodpisane kontrolki bez interwencji użytkownika. Jeśli w polu listy rozwijanej zostanie wybrana pozycja Monit, użytkownicy będą proszeni o wybranie, czy zezwalać na uruchamianie niepodpisanych kontrolek. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli uruchamiać niepodpisanych kontrolek. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy nie będą mogli uruchamiać niepodpisanych kontrolek.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Nawigacja w oknach i ramkach różnych domen w strefie internetowej programu Internet Explorer**  </br>
  To ustawienie zasad umożliwia zarządzanie otwieraniem okien i ramek oraz uzyskiwaniem dostępu do aplikacji w różnych domenach. Jeśli to ustawienie zasad zostanie włączone, użytkownicy będą mogli otwierać okna i ramki z innych domen oraz uzyskiwać dostęp do aplikacji z innych domen. Jeśli w polu listy rozwijanej zostanie wybrana pozycja Monit, użytkownicy będą pytani, czy zezwolić oknom i ramkom na uzyskiwanie dostępu do aplikacji z innych domen. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli otwierać okien i ramek w celu uzyskania dostępu do aplikacji z różnych domen. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy będą mogli otwierać okna i ramki z innych domen oraz uzyskiwać dostęp do aplikacji z innych domen.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Aktualizacje paska stanu za pomocą skryptu w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie tym, czy skrypt może aktualizować pasek stanu w obrębie strefy. Jeśli to ustawienie zasad zostanie włączone, skrypt będzie mógł aktualizować pasek stanu. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, skrypt nie będzie mógł aktualizować paska stanu.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Strefa z ograniczeniami w programie Internet Explorer obejmuje ścieżkę lokalną podczas przekazywania plików do serwera**  </br> To ustawienie zasad określa, czy informacje o ścieżce lokalnej będą wysyłane, gdy użytkownik będzie przekazywał plik za pomocą formularza HTML. Jeśli informacje o ścieżce lokalnej będą wysyłane, niektóre informacje mogą zostać przypadkowo ujawnione serwerowi. Na przykład pliki wysłane z komputera użytkownika mogą zawierać nazwę użytkownika jako część ścieżki. Jeśli to ustawienie zasad zostanie włączone, informacje o ścieżce będą wysyłane, gdy użytkownik będzie przekazywał plik za pomocą formularza HTML. Jeśli to ustawienie zasad zostanie wyłączone, informacje o ścieżce będą usuwane, gdy użytkownik będzie przekazywał plik za pomocą formularza HTML. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł wybrać, czy informacje o ścieżce będą wysyłane podczas przekazywania pliku za pomocą formularza HTML. Domyślnie informacje o ścieżce są wysyłane.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Procesy programu Internet Explorer ograniczają pobieranie plików**  </br> To ustawienie zasad umożliwia aplikacjom hostującym kontrolkę przeglądarki internetowej blokowanie automatycznego monitowania o pobieranie plików, które nie jest inicjowane przez użytkownika. Jeśli to ustawienie zasad zostanie włączone, kontrolka przeglądarki internetowej będzie blokowała dla wszystkich procesów automatyczne monitowanie o pobieranie plików, które nie jest inicjowane przez użytkownika. Jeśli to ustawienie zasad zostanie wyłączone, kontrolka przeglądarki internetowej nie będzie blokowała dla wszystkich procesów automatycznego monitowania o pobieranie plików, które nie jest inicjowane przez użytkownika.
  - **Ustawienie domyślne**: Enabled  
  
- **Strefa z ograniczeniami w programie Internet Explorer zezwala na używanie kontrolek ActiveX tylko przez zatwierdzone domeny**  </br>
  To ustawienie zasad określa, czy użytkownik będzie proszony o wyrażenie zgody na uruchamianie kontrolek ActiveX w witrynach internetowych innych niż witryna internetowa, która zainstalowała kontrolkę ActiveX. Jeśli to ustawienie zasad zostanie włączone, użytkownik będzie proszony o wyrażenie zgody na uruchamianie kontrolek ActiveX z witryn internetowych w tej strefie. Użytkownik może zezwolić na uruchamianie kontrolki z bieżącej witryny lub ze wszystkich witryn. Jeśli to ustawienie zasad zostanie wyłączone, w poszczególnych witrynach nie będzie wyświetlany monit kontrolki ActiveX i będzie można uruchamiać kontrolki ActiveX ze wszystkich witryn w tej strefie.
  - **Ustawienie domyślne**: Enabled  
  
- **Strefa z ograniczeniami w programie Internet Explorer pozwala inicjować i wykonywać skrypty kontrolek ActiveX, które nie są oznaczone jako bezpieczne**  
  To ustawienie zasad umożliwia zarządzanie kontrolkami ActiveX, które nie są oznaczone jako bezpieczne. Jeśli to ustawienie zasad zostanie włączone, kontrolki ActiveX będą uruchamiane i ładowane z parametrami oraz będą wykonywane ich skrypty bez konieczności ustawiania poziomu bezpieczeństwa obiektów dla niezaufanych danych lub skryptów. To ustawienie nie jest zalecane poza strefami bezpiecznymi i administrowanymi. To ustawienie umożliwia inicjowanie i wykonywanie skryptów zarówno bezpiecznych, jak i niebezpiecznych kontrolek, z jednoczesnym ignorowaniem opcji Wykonaj skrypty kontrolek ActiveX zaznaczone jako bezpieczne. Jeśli to ustawienie zasad zostanie włączone i w polu listy rozwijanej zostanie wybrana pozycja Monituj, użytkownicy będą pytani, czy zezwolić na ładowanie kontrolek z parametrami lub inicjowanych przez skrypty. Jeśli to ustawienie zasad zostanie wyłączone, kontrolki ActiveX, które nie mogą stać się bezpieczne, nie będą ładowane z parametrami ani nie będą wykonywane ich skrypty. Jeśli to ustawienie zasad nie zostanie skonfigurowane, kontrolki ActiveX, które nie mogą stać się bezpieczne, nie będą ładowane z parametrami ani nie będą wykonywane ich skrypty.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Użytkownicy programu Internet Explorer zmieniający zasady**  
    Uniemożliwia użytkownikom zmianę ustawień strefy zabezpieczeń. Strefa zabezpieczeń to grupa witryn internetowych na tym samym poziomie zabezpieczeń. Jeśli te zasady zostaną włączone, przycisk Poziom niestandardowy i suwak poziomu zabezpieczeń na karcie Zabezpieczenia w oknie dialogowym Opcje internetowe będą wyłączone. Jeśli te zasady zostaną wyłączone lub nie zostaną skonfigurowane, użytkownicy będą mogli zmieniać ustawienia stref zabezpieczeń. Te zasady uniemożliwiają użytkownikom zmianę ustawień strefy zabezpieczeń ustanowionych przez administratora. Uwaga: Zasady „Wyłącz stronę Zabezpieczenia” (znajdujące się w katalogu \User Configuration\Administrative Templates\Windows Components\Internet Explorer\Internet Control Panel), które powodują usunięcie karty Zabezpieczenia z programu Internet Explorer w Panelu sterowania, mają pierwszeństwo przed tymi zasadami. Jeśli zostaną włączone, omawiane tu zasady będą ignorowane. Zobacz też zasady „Strefy zabezpieczeń: Używaj tylko ustawień komputera”.
    - **Ustawienie domyślne**: Wyłącz  
  
- **Tryb chroniony strefy z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia włączenie trybu chronionego. Tryb chroniony ułatwia ochronę programu Internet Explorer przed wykorzystywaniem luk w zabezpieczeniach, zmniejszając liczbę lokalizacji, w których program Internet Explorer może zapisywać w rejestrze i w systemie plików. Jeśli to ustawienie zasad zostanie włączone, tryb chroniony będzie włączony. Użytkownik nie będzie mógł wyłączyć trybu chronionego. Jeśli to ustawienie zasad zostanie wyłączone, tryb chroniony będzie wyłączony. Użytkownik nie będzie mógł włączyć trybu chronionego. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł włączać i wyłączać tryb chroniony.
  - **Ustawienie domyślne**: Włącz  
  
- **Trwałość danych użytkownika w strefie internetowej programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie zachowywaniem informacji w historii przeglądarki, w ulubionych, w magazynie XML lub bezpośrednio na stronie internetowej zapisanej na dysku. Gdy użytkownik wróci na utrwaloną stronę, a ustawienie zasad zostało odpowiednio skonfigurowane, będzie można przywrócić stan strony. Jeśli to ustawienie zasad zostanie włączone, użytkownicy będą mogli zarządzać zachowywaniem informacji w historii przeglądarki, w ulubionych, w magazynie XML lub bezpośrednio na stronie internetowej zapisanej na dysku. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli zarządzać zachowywaniem informacji w historii przeglądarki, w ulubionych, w magazynie XML lub bezpośrednio na stronie internetowej zapisanej na dysku. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy będą mogli zarządzać zachowywaniem informacji w historii przeglądarki, w ulubionych, w magazynie XML lub bezpośrednio na stronie internetowej zapisanej na dysku.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Wykonywanie skryptów kontrolek przeglądarki internetowej w strefie internetowej programu Internet Explorer**  
 
  To ustawienie zasad określa, czy strona może kontrolować osadzone kontrolki WebBrowser za pomocą skryptu. Jeśli to ustawienie zasad zostanie włączone, dostęp skryptów do kontrolki WebBrowser będzie dozwolony. Jeśli to ustawienie zasad zostanie wyłączone, dostęp skryptów do kontrolki WebBrowser nie będzie dozwolony. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownik będzie mógł włączyć lub wyłączyć dostęp skryptów do kontrolki WebBrowser. Domyślnie dostęp skryptów do kontrolki WebBrowser jest dozwolony tylko w strefach Komputer lokalny i Intranet.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Trwałość danych użytkownika w strefie z ograniczeniami w programie Internet Explorer**  
    To ustawienie zasad umożliwia zarządzanie zachowywaniem informacji w historii przeglądarki, w ulubionych, w magazynie XML lub bezpośrednio na stronie internetowej zapisanej na dysku. Gdy użytkownik wróci na utrwaloną stronę, a ustawienie zasad zostało odpowiednio skonfigurowane, będzie można przywrócić stan strony. Jeśli to ustawienie zasad zostanie włączone, użytkownicy będą mogli zarządzać zachowywaniem informacji w historii przeglądarki, w ulubionych, w magazynie XML lub bezpośrednio na stronie internetowej zapisanej na dysku. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy nie będą mogli zarządzać zachowywaniem informacji w historii przeglądarki, w ulubionych, w magazynie XML lub bezpośrednio na stronie internetowej zapisanej na dysku. Jeśli to ustawienie zasad nie zostanie skonfigurowane, użytkownicy nie będą mogli zarządzać ochroną informacji w historii przeglądarki, w ulubionych, w magazynie XML lub bezpośrednio na stronie internetowej zapisanej na dysku.  
  - **Ustawienie domyślne**: Wyłącz  
  
- **Zablokowane uprawnienia języka Java w strefie intranetowej programu Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie uprawnieniami dotyczącymi apletów Java. Jeśli to ustawienie zasad zostanie włączone, będzie można wybierać opcje z listy rozwijanej. Ustawienie Niestandardowe umożliwia kontrolowanie ustawień uprawnień pojedynczo. Ustawienie Niski poziom zabezpieczeń umożliwia apletom wykonywanie wszystkich operacji. Ustawienie Średni poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy (obszarze pamięci, poza którym program nie może wykonywać wywołań) oraz udostępnia funkcje, takie jak obszar na pliki tymczasowe (bezpieczny obszar magazynu na komputerze klienckim) i kontrolowane przez użytkownika operacje we/wy na plikach. Ustawienie Wysoki poziom zabezpieczeń umożliwia uruchamianie apletów w ich piaskownicy. Wyłącz język Java, aby uniemożliwić uruchamianie jakichkolwiek apletów. Jeśli to ustawienie zasad zostanie wyłączone, nie będzie można uruchamiać apletów Java. Jeśli to ustawienie zasad nie zostanie skonfigurowane, aplety Java będą wyłączone.
  - **Ustawienie domyślne**: Wyłącz Java  
  
- **Rozszerzony tryb chroniony programu Internet Explorer**  
  Rozszerzony tryb chroniony zapewnia dodatkową ochronę przed złośliwymi witrynami internetowymi dzięki użyciu 64-bitowych procesów w 64-bitowych wersjach systemu Windows. Na komputerach z systemem w wersji co najmniej Windows 8 rozszerzony tryb chroniony ogranicza także lokalizacje, z których program Internet Explorer może czytać w rejestrze i w systemie plików. Jeśli to ustawienie zasad zostanie włączone, rozszerzony tryb chroniony będzie włączony. W każdej strefie, w której włączono tryb chroniony, będzie używany rozszerzony tryb chroniony. Użytkownicy nie będą mogli wyłączyć rozszerzonego trybu chronionego. Jeśli to ustawienie zasad zostanie wyłączone, rozszerzony tryb chroniony będzie wyłączony. We wszystkich strefach z włączonym trybem chronionym będzie używana wersja trybu chronionego wprowadzona w programie Internet Explorer 7 dla systemu Windows Vista. Jeśli te zasady nie zostaną skonfigurowane, użytkownicy będą mogli włączać i wyłączać rozszerzony tryb chroniony na karcie Zaawansowane w oknie dialogowym Opcje internetowe.
  - **Ustawienie domyślne**: Enabled  
  
- **Program Internet Explorer pomija ostrzeżenia filtra SmartScreen**  
  To ustawienie zasad określa, czy użytkownik może pomijać ostrzeżenia filtra SmartScreen. Filtr SmartScreen wysyła do użytkownika ostrzeżenia o plikach wykonywalnych, których użytkownicy programu Internet Explorer nie pobierają często z Internetu. Jeśli to ustawienie zasad zostanie włączone, ostrzeżenia filtra SmartScreen będą blokować użytkownika. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, użytkownik będzie mógł pomijać ostrzeżenia filtra SmartScreen.
  - **Ustawienie domyślne**: Wyłącz  
  
- **Ustawienie Meta Refresh w strefie z ograniczeniami w programie Internet Explorer**  
  To ustawienie zasad umożliwia zarządzanie tym, czy przeglądarka użytkownika może być przekierowywana do innej strony internetowej, gdy autor strony internetowej używa ustawienia (tagu) Meta Refresh w celu przekierowywania przeglądarek do innej strony internetowej. Jeśli to ustawienie zasad zostanie włączone, przeglądarka użytkownika, która ładuje stronę zawierającą aktywne ustawienie Meta Refresh, będzie mogła zostać przekierowana do innej strony internetowej. Jeśli to ustawienie zasad zostanie wyłączone, przeglądarka użytkownika, która ładuje stronę zawierającą aktywne ustawienie Meta Refresh, nie będzie mogła zostać przekierowana do innej strony internetowej. Jeśli to ustawienie zasad nie zostanie skonfigurowane, przeglądarka użytkownika, która ładuje stronę zawierającą aktywne ustawienie Meta Refresh, nie będzie mogła zostać przekierowana do innej strony internetowej.
  - **Ustawienie domyślne**: Wyłącz  
  
## <a name="local-policies-security-options"></a>Opcje zabezpieczeń zasad lokalnych
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — LocalPoliciesSecurityOptions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions) w dokumentacji systemu Windows. 

- **Ograniczaj dostęp anonimowy do nazwanych potoków i udziałów**  
  Po włączeniu tego ustawienia zabezpieczeń dostęp anonimowy do udziałów i potoków będzie ograniczany w przypadku ustawień: (1) Nazwanych potoków, do których można uzyskiwać dostęp anonimowo (2) Udziałów, do których można uzyskiwać dostęp anonimowo
  - **Ustawienie domyślne**: Tak  
  
- **Minimalne zabezpieczenia sesji dla serwerów opartych ma technologii SSP NTLM**  
  To ustawienie zabezpieczeń pozwala serwerowi na wymaganie negocjacji szyfrowania 128-bitowego i/lub zabezpieczeń sesji NTLMv2. Te wartości są zależne od wartości ustawienia zabezpieczeń Poziom uwierzytelniania programu LAN Manager. Dostępne opcje to: Wymagaj zabezpieczeń sesji NTLMv2: Połączenie będzie nieudane, jeśli nie zostanie wynegocjowana integralność komunikatu. Wymagaj szyfrowania 128-bitowego. Połączenie będzie nieudane, jeśli nie zostanie wynegocjowane silne szyfrowanie (128-bitowe).
  - **Ustawienie domyślne**: Wymagaj protokołu NTLM V2 i szyfrowania 128-bitowego  
  
- **Liczba minut braku aktywności na ekranie blokady przed aktywowaniem wygaszacza ekranu**  
  System Windows wykryje nieaktywność sesji logowania, a gdy czas nieaktywności przekroczy limit nieaktywności, zostanie uruchomiony wygaszacz ekranu i nastąpi zablokowanie sesji.
  - **Ustawienie domyślne**: 15
  
- **Wymagaj od klienta, aby zawsze podpisywał cyfrowo komunikację** To ustawienie zabezpieczeń określa, czy cały ruch w bezpiecznym kanale inicjowany przez element członkowski domeny musi być podpisany lub zaszyfrowany. Po dołączeniu komputera do domeny zostanie utworzone konto komputera. Następnie podczas uruchamiania systemu zostanie użyte hasło konta komputera, aby utworzyć bezpieczny kanał z kontrolerem dla jego domeny. Ten bezpieczny kanał służy do wykonywania operacji, takich jak uwierzytelnianie przekazywane NTLM, wyszukiwanie nazw/SID LSA itp. To ustawienie określa, czy cały ruch w bezpiecznym kanale inicjowany przez element członkowski domeny spełnia minimalne wymagania dotyczące zabezpieczeń. W szczególności określa, czy cały ruch w bezpiecznym kanale inicjowany przez element członkowski domeny musi być podpisany lub zaszyfrowany. Jeśli te zasady zostaną włączone, bezpieczny kanał nie będzie tworzony, chyba że zostanie wynegocjowane podpisywanie lub szyfrowanie całego ruchu w bezpiecznym kanale. Jeśli te zasady zostaną wyłączone, szyfrowanie i podpisywanie całego ruchu w bezpiecznym kanale będzie negocjowane z kontrolerem domeny. W takim przypadku poziom podpisywania i szyfrowania będzie zależał od wersji kontrolera domeny i ustawień następujących dwóch zasad: Element członkowski domeny: szyfruj cyfrowo dane bezpiecznego kanału — gdy to możliwe Element członkowski domeny: podpisuj cyfrowo dane bezpiecznego kanału — gdy to możliwe
  - **Ustawienie domyślne**: Tak
  
- **Poziom uwierzytelniania**  
  To ustawienie zabezpieczeń określa, który protokół uwierzytelniania typu żądanie/odpowiedź będzie używany podczas logowania do sieci. Ten wybór ma wpływ na poziom protokołu uwierzytelniania używanego przez klientów, poziom wynegocjowanych zabezpieczeń sesji i poziom uwierzytelniania akceptowany przez serwery w następujący sposób: Wysyłaj odpowiedzi LM i NTLM: Klienci korzystają z uwierzytelniania LM oraz NTLM i nigdy nie używają zabezpieczeń sesji NTLMv2; kontrolery domeny akceptują uwierzytelnianie LM, NTLM i NTLMv2. Wysyłaj odpowiedzi LM i NTLM — używaj zabezpieczeń sesji NTLMv2, jeśli zostaną wynegocjowane: Klienci korzystają z uwierzytelniania LM oraz NTLM i używają zabezpieczeń sesji NTLMv2, jeśli są one obsługiwane przez serwer; kontrolery domeny akceptują uwierzytelnianie LM, NTLM i NTLMv2. Wysyłaj tylko odpowiedź NTLM: Klienci korzystają tylko z uwierzytelniania NTLM i używają zabezpieczeń sesji NTLMv2, jeśli są one obsługiwane przez serwer; kontrolery domeny akceptują uwierzytelnianie LM, NTLM i NTLMv2. Wysyłaj tylko odpowiedź NTLMv2: Klienci korzystają tylko z uwierzytelniania NTLMv2 i używają zabezpieczeń sesji NTLMv2, jeśli są one obsługiwane przez serwer; kontrolery domeny akceptują uwierzytelnianie LM, NTLM i NTLMv2. Wysyłaj tylko odpowiedź NTLMv2/odrzucaj odpowiedź LM: Klienci korzystają tylko z uwierzytelniania NTLMv2 i używają zabezpieczeń sesji NTLMv2, jeśli są one obsługiwane przez serwer; kontrolery domeny odrzucają uwierzytelnianie LM (akceptują tylko uwierzytelnianie NTLM i NTLMv2). Wysyłaj tylko odpowiedź NTLMv2/odrzucaj odpowiedzi LM i NTLM: Klienci korzystają tylko z uwierzytelniania NTLMv2 i używają zabezpieczeń sesji NTLMv2, jeśli są one obsługiwane przez serwer; kontrolery domeny odrzucają uwierzytelnianie LM i NTLM (akceptują tylko uwierzytelnianie NTLMv2).
  - **Ustawienie domyślne**: Wysyłaj tylko odpowiedź NTLMv2. Odrzucaj odpowiedzi LM i NTLM
  
- **Uniemożliwiaj klientom wysyłanie niezaszyfrowanych haseł do serwerów SMB innych firm**  
  Jeśli to ustawienie zabezpieczeń zostanie włączone, funkcja przekierowania bloku komunikatów serwera (SMB) będzie mogła wysyłać hasła w postaci zwykłego tekstu do serwerów SMB firm innych niż Microsoft, które nie obsługują szyfrowania haseł podczas uwierzytelniania. Wysyłanie niezaszyfrowanych haseł stanowi zagrożenie bezpieczeństwa.
  - **Ustawienie domyślne**: Tak
  
- **Zawsze wyłączaj serwer podpisujący cyfrowo komunikację**  
  To ustawienie zabezpieczeń określa, czy klient SMB próbuje negocjować podpisywanie pakietów SMB. Protokół bloku komunikatów serwera (SMB) stanowi podstawę do udostępniania plików i drukarek Microsoft oraz wielu innych operacji sieciowych, takich jak zdalne administrowanie systemem Windows. Aby zapobiegać atakom typu man-in-the-middle, które modyfikują pakiety SMB podczas przesyłania, protokół SMB obsługuje cyfrowe podpisywanie pakietów SMB. To ustawienie zasad określa, czy składnik klienta SMB próbuje negocjować podpisywanie pakietów SMB podczas łączenia z serwerem SMB. Jeśli to ustawienie zostanie włączone, klient sieci firmy Microsoft będzie żądał od serwera podpisania pakietów SMB podczas konfigurowania sesji. Jeśli podpisywanie pakietów zostało włączone na serwerze, będzie ono negocjowane. Jeśli te zasady zostały wyłączone, klient SMB nigdy nie będzie negocjował podpisywania pakietów SMB.
  - **Ustawienie domyślne**: Tak
  
- **Działanie monitu o podniesienie uprawnień administratora**  
  To ustawienie zasad steruje działaniem monitu o podniesienie uprawnień w przypadku administratorów. Dostępne opcje to: 0 — Podnieś bez monitowania: Umożliwia uprzywilejowanym kontom wykonanie operacji, która wymaga podniesienia uprawnień, bez konieczności wymagania zgody lub poświadczeń. Uwaga: Tej opcji należy używać tylko w środowiskach z największymi ograniczeniami. 1 — Monituj o podanie poświadczeń na bezpiecznym pulpicie: Jeśli operacja wymaga podniesienia uprawnień, na bezpiecznym pulpicie zostanie wyświetlony monit o wprowadzenie nazwy i hasła uprzywilejowanego użytkownika. Jeśli użytkownik wprowadzi prawidłowe poświadczenia, operacja będzie kontynuowana przy użyciu najwyższych dostępnych uprawnień użytkownika. 2 — Monituj o zgodę na bezpiecznym pulpicie: Jeśli operacja wymaga podniesienia uprawnień, na bezpiecznym pulpicie zostanie wyświetlony monit o wybranie pozycji Zezwól lub Odmów. Jeśli użytkownik wybierze pozycję Zezwól, operacja będzie kontynuowana przy użyciu najwyższych dostępnych uprawnień użytkownika. 3 — Monituj o poświadczenia: Jeśli operacja wymaga podniesienia uprawnień, zostanie wyświetlony monit o wprowadzenie nazwy i hasła użytkownika administracyjnego. Jeśli użytkownik wprowadzi prawidłowe poświadczenia, operacja będzie kontynuowana przy użyciu odpowiednich uprawnień. 4 — Monituj o zgodę: Jeśli operacja wymaga podniesienia uprawnień, zostanie wyświetlony monit o wybranie pozycji Zezwól lub Odmów. Jeśli użytkownik wybierze pozycję Zezwól, operacja będzie kontynuowana przy użyciu najwyższych dostępnych uprawnień użytkownika. 5 — Monituj o zgodę w przypadku plików binarnych z systemem innym niż Windows: (Ustawienie domyślne) Jeśli operacja dotycząca aplikacji firmy innej niż Microsoft wymaga podniesienia uprawnień, na bezpiecznym pulpicie zostanie wyświetlony monit o wybranie pozycji Zezwól lub Odmów. Jeśli użytkownik wybierze pozycję Zezwól, operacja będzie kontynuowana przy użyciu najwyższych dostępnych uprawnień użytkownika
  - **Ustawienie domyślne**: Monituj o zgodę na bezpiecznym pulpicie
  
- **Minimalne zabezpieczenia sesji dla klientów opartych na technologii SSP NTLM**  
  To ustawienie zabezpieczeń pozwala klientowi na wymaganie negocjacji szyfrowania 128-bitowego i/lub zabezpieczeń sesji NTLMv2. Te wartości są zależne od wartości ustawienia zabezpieczeń Poziom uwierzytelniania programu LAN Manager. Dostępne opcje to: Wymagaj zabezpieczeń sesji NTLMv2: Połączenie będzie nieudane, jeśli nie zostanie wynegocjowany protokół NTLMv2. Wymagaj szyfrowania 128-bitowego: Połączenie będzie nieudane, jeśli nie zostanie wynegocjowane silne szyfrowanie (128-bitowe).
  - **Ustawienie domyślne**: Wymagaj protokołu NTLM V2 i szyfrowania 128-bitowego
  
- **Zachowanie po wyjęciu karty inteligentnej**  
  To ustawienie zabezpieczeń określa, co się stanie, gdy karta inteligentna zalogowanego użytkownika zostanie usunięta z czytnika kart inteligentnych. Dostępne opcje to: Brak akcji Zablokuj stację roboczą Wymuś wylogowanie Rozłącz, gdy istnieje sesja usług pulpitu zdalnego Jeśli w oknie dialogowym Właściwości dla tych zasad zostanie kliknięta pozycja Zablokuj stację roboczą, po wyjęciu karty inteligentnej stacja robocza zostanie zablokowana, umożliwiając użytkownikom opuszczenie miejsca, zabranie karty inteligentnej ze sobą i zachowanie sesji chronionej. Jeśli w oknie dialogowym Właściwości dla tych zasad zostanie kliknięta pozycja Wymuś wylogowanie, po wyjęciu karty inteligentnej użytkownik zostanie automatycznie wylogowany. Jeśli zostanie kliknięta pozycja Rozłącz, gdy istnieje sesja usług pulpitu zdalnego, usunięcie karty inteligentnej spowoduje rozłączenie sesji bez wylogowywania użytkownika. Umożliwia to użytkownikowi włożenie karty inteligentnej i wznowienie sesji w późniejszym czasie lub na innym komputerze z czytnikiem kart inteligentnych bez konieczności ponownego logowania się. Jeśli sesja jest lokalna, te zasady działają tak samo, jak w przypadku opcji Zablokuj stację roboczą.
  - **Ustawienie domyślne**: Zablokuj stację roboczą
  
- **Blokuj anonimowe wyliczanie kont SAM i udziałów**  
  To ustawienie zabezpieczeń określa, czy jest dozwolone anonimowe wyliczanie kont SAM i udziałów. System Windows pozwala użytkownikom anonimowym na wykonywanie pewnych działań, takich jak wyliczanie nazw kont domeny i udziałów sieciowych. Jest to wygodne, na przykład gdy administrator chce udzielić dostępu użytkownikom w zaufanej domenie, w której nie jest utrzymywane wzajemne zaufanie. Jeśli nie chcesz pozwolić na anonimowe wyliczanie kont SAM i udziałów, włącz te zasady.
  - **Ustawienie domyślne**: Tak
  
- **Blokuj zdalne logowanie przy użyciu pustego hasła**  
  To ustawienie zabezpieczeń określa, czy konta lokalne, które nie są chronione hasłem, mogą być używane do logowania się z lokalizacji innych niż konsola fizycznego komputera. Jeśli to ustawienie zostanie włączone, konta lokalne, które nie są chronione hasłem, będą umożliwiały tylko logowanie się przy użyciu klawiatury komputera. Ostrzeżenie: Komputery, które nie znajdują się w fizycznie zabezpieczonych lokalizacjach, powinny zawsze wymuszać zasady silnych haseł dla wszystkich kont użytkowników lokalnych. W przeciwnym razie każda osoba mająca fizyczny dostęp do komputera będzie mogła zalogować się przy użyciu konta użytkownika, które nie ma hasła. Jest to szczególnie ważne w przypadku komputerów przenośnych. Jeśli ta zasada zabezpieczeń zostanie zastosowana do grupy Wszyscy, nikt nie będzie mógł zalogować się za pośrednictwem usług pulpitu zdalnego. To ustawienie nie wpływa na logowanie z użyciem kont domeny. W przypadku aplikacji korzystających ze zdalnego logowania interakcyjnego istnieje możliwość obejścia tego ustawienia.
  - **Ustawienie domyślne**: Tak
  
- **Działanie monitu o podniesienie uprawnień standardowego użytkownika**  
  To ustawienie zasad steruje działaniem monitu o podniesienie uprawnień w przypadku standardowych użytkowników. 0 — Automatycznie odrzucaj żądania podniesienia uprawnień: Gdy operacja wymaga podniesienia uprawnień, zostanie wyświetlony komunikat o błędzie odmowy dostępu, który można skonfigurować. W przedsiębiorstwie, w którym komputery działają z uprawnieniami użytkowników standardowych, można wybrać to ustawienie, aby ograniczyć liczbę wezwań pomocy technicznej. 1 — Monituj o podanie poświadczeń na bezpiecznym pulpicie: Jeśli operacja wymaga podniesienia uprawnień, na bezpiecznym pulpicie zostanie wyświetlony monit o wprowadzenie nazwy i hasła innego użytkownika. Jeśli użytkownik wprowadzi prawidłowe poświadczenia, operacja będzie kontynuowana przy użyciu odpowiednich uprawnień. 3 (Ustawienie domyślne) — Monituj o poświadczenia: Jeśli operacja wymaga podniesienia uprawnień, zostanie wyświetlony monit o wprowadzenie nazwy i hasła użytkownika administracyjnego. Jeśli użytkownik wprowadzi prawidłowe poświadczenia, operacja będzie kontynuowana przy użyciu odpowiednich uprawnień.
  - **Ustawienie domyślne**: Automatycznie odrzucaj żądania podniesienia uprawnień
  
- **Wymagaj trybu zatwierdzania przez administratora dla administratorów**  
  To ustawienie zasad kontroluje zachowanie wszystkich ustawień zasad funkcji Kontrola konta użytkownika (UAC) dla komputera. Jeśli to ustawienie zasad zostanie zmienione, należy uruchomić ponownie komputer. Dostępne opcje to: 0 — Wyłączone: Tryb zatwierdzania przez administratora i wszystkie powiązane ustawienia zasad funkcji Kontrola konta użytkownika będą wyłączone. Uwaga: Jeśli to ustawienie zasad zostanie wyłączone, Centrum zabezpieczeń powiadomi Cię o pogorszeniu ogólnego stanu zabezpieczeń systemu operacyjnego. 1 — Włączone: (Ustawienie domyślne) Tryb zatwierdzania przez administratora będzie włączony. Te zasady muszą być włączone, a powiązane z nimi ustawienia zasad funkcji Kontrola konta użytkownika muszą być także odpowiednio ustawione, aby wbudowane konto administratora i wszystkich pozostałych użytkowników, którzy są członkami grupy Administratorzy, można było uruchamiać w trybie zatwierdzania przez administratora.
  - **Ustawienie domyślne**: Tak
  
- **Zapobiegaj anonimowemu wyliczaniu kont SAM**  
  To ustawienie zabezpieczeń określa, jakie dodatkowe uprawnienia będą udzielane dla anonimowych połączeń z komputerem. System Windows pozwala użytkownikom anonimowym na wykonywanie pewnych działań, takich jak wyliczanie nazw kont domeny i udziałów sieciowych. Jest to wygodne, na przykład gdy administrator chce udzielić dostępu użytkownikom w zaufanej domenie, w której nie jest utrzymywane wzajemne zaufanie. Ta opcja zabezpieczeń umożliwia nakładanie dodatkowych ograniczeń na połączenia anonimowe w następujący sposób: Włączone: Nie zezwalaj na wyliczanie kont SAM. Ta opcja powoduje zamianę grupy Wszyscy na grupę Uwierzytelnieni użytkownicy w uprawnieniach zabezpieczeń dotyczących zasobów. Disabled: Brak dodatkowych ograniczeń. Polegaj na uprawnieniach domyślnych. Domyślnie na stacjach roboczych: Włączone. Domyślnie na serwerze: Włączone.
  - **Ustawienie domyślne**: Tak
  
- **Zezwalaj na zdalne połączenia z menedżerem kont zabezpieczeń**  
  To ustawienie zasad pozwala ograniczyć zdalne połączenia rpc z menedżerem kont zabezpieczeń. Jeśli nie zostanie wybrane, będzie używany domyślny deskryptor zabezpieczeń.
  - **Ustawienie domyślne**: *O:BAG:BAD:(A;;RC;;;BA)*

- **Używaj trybu zatwierdzania przez administratora**  
  To ustawienie zasad steruje zachowaniem trybu zatwierdzania przez administratora w przypadku wbudowanego konta administratora. Dostępne opcje to: • Włączone: Wbudowane konto administratora używa trybu zatwierdzania przez administratora. Domyślnie każda operacja, która wymaga podniesienia uprawnień, będzie monitowała użytkownika o zatwierdzenie operacji. • Wyłączone: (Ustawienie domyślne) Wbudowane konto administratora uruchamia wszystkie aplikacje z pełnymi uprawnieniami administracyjnymi.
  - **Ustawienie domyślne**: Tak
  
- **Zezwalaj na aplikacje dostępu do interfejsu użytkownika w bezpiecznych lokalizacjach**  
  To ustawienie zasad umożliwia zdecydowanie, czy programy z funkcją dostępności interfejsu użytkownika (UIAccess lub UIA, User Interface Accessibility) mogą automatycznie wyłączać bezpieczny pulpit na potrzeby monitowania o podniesienie uprawnień przez użytkownika standardowego. Włączone: Programy z funkcją UIA, w tym Pomoc zdalna systemu Windows, będą automatycznie wyłączać bezpieczny pulpit w przypadku monitowania o podniesienie uprawnień. Jeśli ustawienie zasad „Kontrola konta użytkownika: przełącz na bezpieczny pulpit przy monitowaniu o podniesienie uprawnień” nie zostanie wyłączone, monity będą wyświetlane na pulpicie użytkownika interakcyjnego, a nie na bezpiecznym pulpicie. Disabled: (Ustawienie domyślne) Bezpieczny pulpit może zostać wyłączony tylko przez użytkownika pulpitu interakcyjnego lub przez wyłączenie ustawienia zasad „Kontrola konta użytkownika: przełącz na bezpieczny pulpit przy monitowaniu o podniesienie uprawnień”.
  - **Ustawienie domyślne**: Tak

- **Wykrywanie instalacji aplikacji i monitowanie o podniesienie uprawnień**  
  To ustawienie zasad steruje zachowaniem wykrywania instalacji aplikacji na komputerze. Dostępne opcje to: Włączone: (Ustawienie domyślne) W przypadku wykrycia pakietu instalacyjnego aplikacji, który wymaga podwyższonego poziomu uprawnień, użytkownik jest monitowany o podanie nazwy użytkownika administracyjnego i hasła. Jeśli użytkownik wprowadzi prawidłowe poświadczenia, operacja będzie kontynuowana przy użyciu odpowiednich uprawnień. Disabled: Pakiety instalacyjne aplikacji nie są wykrywane i monitowane o podniesienie poziomu uprawnień. W przedsiębiorstwach, które korzystają z pulpitów użytkowników standardowych i technologii instalacji delegowanej, takich jak instalacja oprogramowania zasad grupy lub Systems Management Server (SMS), to ustawienie zasad powinno zostać wyłączone. W tym przypadku wykrywanie instalatora nie jest konieczne.
  - **Ustawienie domyślne**: Tak
  
- **Zapobiegaj przechowywaniu wartości skrótu programu LAN Manager dla następnej zmiany hasła**  
  To ustawienie zabezpieczeń określa, czy przy następnej zmianie hasła będzie przechowywana wartość skrótu programu LAN Manager (LM) dla nowego hasła. Skrót programu LM jest stosunkowo słaby i podatny na atak w porównaniu do silniejszego kryptograficznie skrótu systemu Windows NT. Ponieważ skrót programu LM jest przechowywany na komputerze lokalnym w bazie danych zabezpieczeń, hasła mogą zostać złamane po zaatakowaniu bazy danych.
  - **Ustawienie domyślne**: Tak

- **Wirtualizuj błędy zapisu w plikach i rejestrze w lokalizacjach poszczególnych użytkowników**  
  To ustawienie zasad kontroluje, czy błędy zapisu aplikacji są przekierowywane do zdefiniowanych lokalizacji rejestru i systemu plików. To ustawienie zasad ogranicza liczbę aplikacji uruchamianych w trybie administratora i zapisuje dane aplikacji w czasie wykonywania w katalogu %ProgramFiles%, %Windir%, %Windir%\system32 lub HKLM\Software.
  - **Ustawienie domyślne**: Tak

## <a name="ms-security-guide"></a>Przewodnik po zabezpieczeniach firmy MS  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — MSSecurityGuide](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mssecurityguide) w dokumentacji systemu Windows.  

- **Stosuj ograniczenia funkcji Kontrola konta użytkownika do kont lokalnych podczas logowania do sieci**  
    - **Ustawienie domyślne**: Enabled
  
- **Konfiguracja uruchamiania sterownika klienta SMB v1**  
  - **Ustawienie domyślne**: Sterownik wyłączony
  
- **Serwer SMB v1**  
  - **Ustawienie domyślne**: Wyłącz
  
- **Uwierzytelnianie szyfrowane**  
  - **Ustawienie domyślne**: Wyłącz
  
- **Ochrona przed zastąpieniem obsługi wyjątków strukturalnych**  
  - **Ustawienie domyślne**: Enabled
  
## <a name="mss-legacy"></a>Starsza wersja MSS  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — MSSLegacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-msslegacy) w dokumentacji systemu Windows.  

- **Poziom ochrony routingu źródła protokołu IP sieci**  
  - **Ustawienie domyślne**: Najwyższa ochrona 
  
- **Sieć ignoruje żądania wydania nazwy NetBIOS z wyjątkiem żądań z serwerów WINS**  
  - **Ustawienie domyślne**: Enabled
  
- **Poziom ochrony routingu źródła protokołu IPv6 sieci**  
  - **Ustawienie domyślne**: Najwyższa ochrona

- **Przekierowania protokołu ICMP sieci zastępują wygenerowane przez OSPF**  
  - **Ustawienie domyślne**: Wyłącz
  
## <a name="power"></a>Zasilanie  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — Power](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power) w dokumentacji systemu Windows.  

- **Wymagaj hasła przy wznawianiu, gdy urządzenie jest zasilane z sieci**  
  To ustawienie zasad określa, czy użytkownik ma być monitowany o podanie hasła podczas wznawiania działania systemu po trybie uśpienia. Jeśli to ustawienie zasad zostanie włączone lub nie zostanie skonfigurowane, użytkownik będzie monitowany o podanie hasła podczas wznawiania działania systemu po trybie uśpienia. Jeśli to ustawienie zasad zostanie wyłączone, użytkownik nie będzie monitowany o podanie hasła podczas wznawiania działania systemu po trybie uśpienia.
  - **Ustawienie domyślne**: Enabled
  
- **Stany wstrzymania podczas uśpienia, gdy urządzenie jest zasilane z baterii**  
  To ustawienie zasad określa, czy system Windows może używać stanów wstrzymania podczas przełączania komputera w stan uśpienia. Jeśli to ustawienie zasad zostanie włączone lub nie zostanie skonfigurowane, system Windows będzie używał stanów wstrzymania do przełączania komputera w stan uśpienia. Jeśli to ustawienie zasad zostanie wyłączone, stany wstrzymania (S1–S3) będą niedozwolone.
  - **Ustawienie domyślne**: Wyłącz
  
- **Stany wstrzymania podczas uśpienia, gdy urządzenie jest zasilane z sieci**  
  To ustawienie zasad określa, czy system Windows może używać stanów wstrzymania podczas przełączania komputera w stan uśpienia. Jeśli to ustawienie zasad zostanie włączone lub nie zostanie skonfigurowane, system Windows będzie używał stanów wstrzymania do przełączania komputera w stan uśpienia. Jeśli to ustawienie zasad zostanie wyłączone, stany wstrzymania (S1–S3) będą niedozwolone.
  - **Ustawienie domyślne**: Wyłącz
  
- **Wymagaj hasła przy wznawianiu, gdy urządzenie jest zasilane z baterii**  
  To ustawienie zasad określa, czy użytkownik ma być monitowany o podanie hasła podczas wznawiania działania systemu po trybie uśpienia. Jeśli to ustawienie zasad zostanie włączone lub nie zostanie skonfigurowane, użytkownik będzie monitowany o podanie hasła podczas wznawiania działania systemu po trybie uśpienia. Jeśli to ustawienie zasad zostanie wyłączone, użytkownik nie będzie monitowany o podanie hasła podczas wznawiania działania systemu po trybie uśpienia.
  - **Ustawienie domyślne**: Enabled
  
## <a name="remote-desktop-services"></a>Usługi pulpitu zdalnego  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — RemoteDesktopServices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotedesktopservices) w dokumentacji systemu Windows.  

- **Blokuj zapisywanie haseł**  
  Określa, czy hasła mogą być zapisywane w oknie Podłączanie pulpitu zdalnego na tym komputerze. Jeśli to ustawienie zostanie włączone, pole wyboru zapisywania haseł w oknie Podłączanie pulpitu zdalnego będzie wyłączone, a użytkownicy nie będą już mogli zapisywać haseł. Gdy użytkownik otworzy plik RDP za pomocą funkcji Podłączanie pulpitu zdalnego i zapisze swoje ustawienia, wszystkie hasła, które wcześniej istniały w pliku RDP, zostaną usunięte. Jeśli to ustawienie zostanie wyłączone lub nie zostanie skonfigurowane, użytkownik będzie mógł zapisywać hasła za pomocą funkcji Podłączanie pulpitu zdalnego.
  - **Ustawienie domyślne**: Enabled
  
- **Bezpieczna komunikacja RPC**  
  Określa, czy serwer hosta sesji usług pulpitu zdalnego będzie wymagał bezpiecznej komunikacji RPC ze wszystkimi klientami, czy też będzie umożliwiał komunikację niezabezpieczoną. To ustawienie umożliwia poprawę zabezpieczeń komunikacji RPC z klientami, zezwalając tylko na żądania uwierzytelnione i szyfrowane. Jeśli stan zostanie ustawiony na Włączono, usługi pulpitu zdalnego będą akceptowały żądania od klientów RPC obsługujących bezpieczne żądania, a nie będą zezwalały na niezabezpieczoną komunikację z klientami niezaufanymi. Jeśli stan zostanie ustawiony na Wyłączono, usługi pulpitu zdalnego zawsze będą żądały zabezpieczeń dla całego ruchu RPC. Jednak niezabezpieczona komunikacja będzie dozwolona w przypadku klientów RPC, którzy nie odpowiadają na żądanie. Jeśli stan zostanie ustawiony na Nie skonfigurowano, niezabezpieczona komunikacja będzie dozwolona. Uwaga: Interfejs usług RPC służy do administrowania usługami pulpitu zdalnego i ich konfigurowania.
  - **Ustawienie domyślne**: Enabled
  
- **Blokuj przekierowywanie dysków**  
  To ustawienie zasad określa, czy zapobiegać mapowaniu dysków klienta w ramach sesji usług pulpitu zdalnego (przekierowywaniu dysków). Domyślnie serwer hosta sesji usług pulpitu zdalnego automatycznie mapuje dyski klienta po podłączeniu. Zamapowane dyski są wyświetlane w drzewie folderów sesji w Eksploratorze plików lub na komputerze w formacie *\<litera_dysku>* na *\<nazwa_komputera>*. To ustawienie zasad umożliwia zmianę tego zachowania. Jeśli to ustawienie zasad zostanie włączone, przekierowywanie dysków klienta nie będzie dozwolone w ramach sesji usług pulpitu zdalnego, a przekierowywanie kopii plików ze Schowka nie będzie dozwolone na komputerach z systemami Windows Server 2003, Windows 8 i Windows XP. Jeśli to ustawienie zasad zostanie wyłączone, przekierowywanie dysków klienta będzie zawsze dozwolone. Ponadto przekierowywanie kopii plików ze Schowka będzie zawsze dozwolone, gdy będzie dozwolone przekierowywanie Schowka. Jeśli to ustawienie zasad nie zostanie skonfigurowane, przekierowywanie dysków klienta i przekierowywanie kopii plików ze Schowka nie będzie określane na poziomie zasad grupy.
  - **Ustawienie domyślne**: Enabled
  
- **Monit o podanie hasła podczas nawiązywania połączenia**  
  To ustawienie zasad określa, czy usługi pulpitu zdalnego zawsze będą wyświetlały klientowi monit o podanie hasła podczas nawiązywania połączenia. To ustawienie służy do wymuszania monitu o podanie hasła dla użytkowników, którzy logują się do usług pulpitu zdalnego, nawet wtedy, gdy podali już hasło w kliencie usługi Podłączanie pulpitu zdalnego. Domyślnie usługi pulpitu zdalnego umożliwiają użytkownikom automatyczne logowanie się po wprowadzeniu hasła w kliencie usługi Podłączanie pulpitu zdalnego. Jeśli to ustawienie zasad zostanie włączone, użytkownicy nie będą mogli automatycznie logować się do usług pulpitu zdalnego po podaniu haseł w kliencie usługi Podłączanie pulpitu zdalnego. Będą monitowani o podanie hasła w celu zalogowania. Jeśli to ustawienie zasad zostanie wyłączone, użytkownicy zawsze będą mogli automatycznie logować się do usług pulpitu zdalnego po podaniu haseł w kliencie usługi Podłączanie pulpitu zdalnego. Jeśli to ustawienie zasad nie zostanie skonfigurowane, automatyczne logowanie nie będzie określane na poziomie zasad grupy. 
  - **Ustawienie domyślne**: Enabled
  
- **Poziom szyfrowania połączeń klienta usług pulpitu zdalnego**  
  Określa, czy do zabezpieczenia komunikacji między komputerami klienckimi a serwerami hosta sesji usług pulpitu zdalnego podczas połączeń za pomocą protokołu RDP (Remote Desktop Protocol) ma być wymagane użycie określonego poziomu szyfrowania. Te zasady mają zastosowanie tylko wtedy, gdy jest używane szyfrowanie natywne RDP. Jednak szyfrowanie natywne RDP (w przeciwieństwie do szyfrowania SSL) nie jest zalecane. Te zasady nie dotyczą szyfrowania SSL. Jeśli to ustawienie zasad zostanie włączone, cała komunikacja między klientami a serwerami hosta sesji usług pulpitu zdalnego podczas połączeń zdalnych będą musiały używać metody szyfrowania określonej w tym ustawieniu. Domyślnie poziom szyfrowania jest ustawiony na Wysoki. Dostępne są następujące metody szyfrowania:  
  - *Wysoki*: Ustawienie Wysoki powoduje szyfrowanie danych wysyłanych od klienta do serwera i od serwera do klienta za pomocą silnego szyfrowania 128-bitowego. Tego poziomu szyfrowania należy używać w środowiskach zawierających tylko klientów 128-bitowych (na przykład klientów z uruchomioną funkcją Podłączanie pulpitu zdalnego). Klienci, którzy nie obsługują tego poziomu szyfrowania, nie będą mogli łączyć się z serwerami hosta sesji usług pulpitu zdalnego.  
  - *Zgodny z klientem*: Ustawienie Zgodny z klientem powoduje szyfrowanie danych wysyłanych między klientem a serwerem z użyciem maksymalnej siły klucza obsługiwanej przez klienta. Tego poziomu szyfrowania należy używać w środowiskach zawierających klientów, którzy nie obsługują szyfrowania 128-bitowego.  
  - *Niski*: Ustawienie Niski powoduje szyfrowanie tylko danych wysyłanych od klienta do serwera przy użyciu szyfrowania 56-bitowego.  
  
  Jeśli to ustawienie zostanie wyłączone lub nie zostanie skonfigurowane, poziom szyfrowania używany w przypadku zdalnych połączeń z serwerami hosta sesji usług pulpitu zdalnego nie będzie wymuszany za pomocą zasad grupy. Ważną zgodność ze standardem FIPS można skonfigurować za pomocą funkcji Kryptografia systemu. Algorytmów zgodnych ze standardem FIPS należy używać do szyfrowania, tworzenia skrótów i podpisywania ustawień w zasadach grupy (w obszarze Konfiguracja komputera\Ustawienia systemu Windows\Ustawienia zabezpieczeń\Zasady lokalne\Opcje zabezpieczeń). Ustawienie zgodne ze standardem FIPS powoduje szyfrowanie i odszyfrowywanie danych wysyłanych od klienta do serwera i od serwera do klienta za pomocą algorytmów szyfrowania Federal Information Processing Standard (FIPS) 140 przy użyciu modułów kryptograficznych firmy Microsoft. Tego poziomu szyfrowania należy używać, gdy komunikacja między klientami a serwerami hosta sesji usług pulpitu zdalnego wymaga najwyższego poziomu szyfrowania.
  - **Ustawienie domyślne**: Wysoki
  
## <a name="remote-management"></a>Zdalne zarządzanie  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — RemoteManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotemanagement) w dokumentacji systemu Windows.  

- **Blokuj przechowywanie poświadczeń Uruchom jako**  
  Uwierzytelnianie podstawowe klienta
  - **Ustawienie domyślne**: Enabled
  
- **Uwierzytelnianie podstawowe**  
  To ustawienie zasad umożliwia zarządzanie tym, czy usługa Windows Remote Management (WinRM) będzie akceptowała uwierzytelnianie podstawowe z klienta zdalnego. Jeśli to ustawienie zasad zostanie włączone, usługa WinRM będzie akceptowała uwierzytelnianie podstawowe z klienta zdalnego. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, usługa WinRM nie będzie akceptowała uwierzytelniania podstawowego z klienta zdalnego.
  - **Ustawienie domyślne**: Wyłącz
  
- **Blokuj uwierzytelnianie szyfrowane klienta**  
  To ustawienie zasad umożliwia zarządzanie tym, czy klient usługi Windows Remote Management (WinRM) będzie używał uwierzytelniania szyfrowanego. Jeśli to ustawienie zasad zostanie włączone, klient usługi WinRM nie będzie używał uwierzytelniania szyfrowanego. Jeśli to ustawienie zostanie wyłączone lub nie zostanie skonfigurowane, klient usługi WinRM będzie używał uwierzytelniania szyfrowanego.
  - **Ustawienie domyślne**: Enabled
  
- **Ruch niezaszyfrowany**  
  To ustawienie zasad umożliwia zarządzanie tym, czy usługa Windows Remote Management (WinRM) będzie wysyłała i odbierała niezaszyfrowane komunikaty za pośrednictwem sieci. Jeśli to ustawienie zasad zostanie włączone, klient usługi WinRM będzie wysyłał i odbierał niezaszyfrowane komunikaty za pośrednictwem sieci. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, klient usługi WinRM będzie wysyłał i odbierał tylko zaszyfrowane komunikaty za pośrednictwem sieci.  
  - **Ustawienie domyślne**: Wyłącz
  
- **Niezaszyfrowany ruch klienta**  
  To ustawienie zasad umożliwia zarządzanie tym, czy klient usługi Windows Remote Management (WinRM) będzie wysyłał i odbierał niezaszyfrowane komunikaty za pośrednictwem sieci. Jeśli to ustawienie zasad zostanie włączone, klient usługi WinRM będzie wysyłał i odbierał niezaszyfrowane komunikaty za pośrednictwem sieci. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, klient usługi WinRM będzie wysyłał i odbierał tylko zaszyfrowane komunikaty za pośrednictwem sieci.
  - **Ustawienie domyślne**: Wyłącz
  
- **Uwierzytelnianie podstawowe klienta**  
  To ustawienie zasad umożliwia zarządzanie tym, czy klient usługi Windows Remote Management (WinRM) będzie używał uwierzytelniania podstawowego. Jeśli to ustawienie zasad zostanie włączone, klient usługi WinRM będzie używał uwierzytelniania podstawowego. Jeśli usługa WinRM zostanie skonfigurowana tak, aby używała transportu HTTP, nazwa użytkownika i hasło będą wysyłane przez sieć jako zwykły tekst. Jeśli to ustawienie zostanie wyłączone lub nie zostanie skonfigurowane, klient usługi WinRM nie będzie używał uwierzytelniania podstawowego.
  - **Ustawienie domyślne**: Wyłącz
  

## <a name="remote-procedure-call"></a>Zdalne wywoływanie procedur  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — RemoteProcedureCall](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remoteprocedurecall) w dokumentacji systemu Windows.  

- **Opcje nieuwierzytelnionego klienta RPC**  
  To ustawienie zasad określa, jak środowisko uruchomieniowe serwera RPC obsługuje nieuwierzytelnionych klientów RPC łączących się z serwerami RPC. To ustawienie zasad ma wpływ na wszystkie aplikacje RPC. W środowisku domeny tego ustawienia zasad należy używać ostrożnie, ponieważ może wpłynąć na wiele funkcji, łącznie z samym przetwarzaniem zasad grupy. Cofnięcie zmiany tego ustawienia zasad może wymagać ręcznego działania na każdej maszynie, której to dotyczy. Tego ustawienia zasad nigdy nie należy stosować do kontrolera domeny. Jeśli to ustawienie zasad zostanie wyłączone, środowisko uruchomieniowe serwera RPC będzie używać wartości „Uwierzytelnione” w kliencie systemu Windows i wartości „Brak” w wersjach systemu Windows Server, które obsługują to ustawienie zasad. Jeśli to ustawienie zasad nie zostanie skonfigurowane, pozostanie wyłączone. Środowisko uruchomieniowe serwera RPC będzie zachowywać się tak, jakby było włączone z wartością „Uwierzytelnione” w kliencie systemu Windows i wartością „Brak” w jednostkach SKU serwera, które obsługują to ustawienie zasad. Jeśli to ustawienie zasad zostanie włączone, będzie nakazywać środowisku uruchomieniowemu serwera RPC ograniczanie nieuwierzytelnionych klientów RPC łączących się z serwerami RPC uruchomionymi na maszynie. Klient będzie uznany za uwierzytelnionego, jeśli będzie używać nazwanego potoku do komunikacji z serwerem lub zabezpieczeń klienta RPC. Interfejsy RPC, które żądają, aby były dostępne dla nieuwierzytelnionych klientów, mogą być wykluczone z tego ograniczenia, w zależności od wybranej wartości tego ustawienia zasad.  
  - Ustawienie *Brak* zezwala wszystkim klientom RPC na łączenie się z serwerami RPC uruchomionymi na maszynie, na której zastosowano ustawienie zasad. 
  - Ustawienie *Uwierzytelnione* umożliwia tylko uwierzytelnionym klientom RPC (zgodnie z powyższą definicją) łączenie się z serwerami RPC uruchomionymi na maszynie, na której zastosowano ustawienie zasad. Wykluczenia są przyznawane interfejsom, które tego żądały. 
  - Ustawienie *Uwierzytelnione bez wyjątków* umożliwia tylko uwierzytelnionym klientom RPC (zgodnie z powyższą definicją) łączenie się z serwerami RPC uruchomionymi na maszynie, na której zastosowano ustawienie zasad. Wyjątki nie są dozwolone. Uwaga: to ustawienie zasad jest stosowane dopiero po ponownym uruchomieniu systemu.  

  - **Ustawienie domyślne**: Uwierzytelnione

## <a name="search"></a>Wyszukaj 
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — wyszukiwanie](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-search) w dokumentacji systemu Windows.  

- **Wyłącz indeksowanie zaszyfrowanych elementów**  
  Zezwala lub nie zezwala na indeksowanie elementów. Ten przełącznik jest przeznaczony dla indeksatora programu Windows Search, który kontroluje, czy indeksuje on elementy, które są zaszyfrowane, takie jak pliki chronione przez funkcję Windows Information Protection (WIP). Gdy te zasady są włączone, elementy chronione przez funkcję WIP są indeksowane, a dotyczące ich metadane są przechowywane w lokalizacji niezaszyfrowanej. Metadane obejmują takie informacje, jak ścieżka do pliku i data modyfikacji. Gdy zasady są wyłączone, elementy chronione przez funkcję WIP nie są indeksowane i nie są wyświetlane w wynikach w Cortanie ani Eksploratorze plików. Jeśli na urządzeniu istnieje wiele plików multimedialnych chronionych przez funkcję WIP, może to także mieć wpływ na wydajność dla zdjęć i aplikacji Groove.
  - **Ustawienie domyślne**: Tak
  
## <a name="smart-screen"></a>SmartScreen  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — SmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen) w dokumentacji systemu Windows.  

- **Blokuj wykonywanie niezweryfikowanych plików**  
  Zablokuj użytkownikowi możliwość uruchamiania niezweryfikowanych plików. 0 — pracownicy mogą ignorować ostrzeżenia filtru SmartScreen i uruchamiać złośliwe pliki. 1 — pracownicy nie mogą ignorować ostrzeżenia filtru SmartScreen i uruchamiać złośliwe pliki.
  - **Ustawienie domyślne**: Tak

- **Blokowanie pobierania niezweryfikowanych plików**  
  Domyślnie program Microsoft Edge pozwala użytkownikom pomijać (ignorować) ostrzeżenia filtru SmartScreen w usłudze Windows Defender dotyczące potencjalnie złośliwych plików, dzięki czemu mogą kontynuować pobieranie niezweryfikowanych plików. Włączenie tych zasad uniemożliwia użytkownikom pomijanie ostrzeżeń, przez co nie mogą pobierać niezweryfikowanych plików.
  - **Ustawienie domyślne**: Tak
  
- **Wymagaj filtra SmartScreen dla aplikacji i plików**  
  Umożliwia administratorom IT konfigurowanie filtru SmartScreen dla systemu Windows.
  - **Ustawienie domyślne**: Tak
  
## <a name="system"></a>System  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — system](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system) w dokumentacji systemu Windows.  

- **Inicjowanie sterownika rozruchu systemu**  
  To ustawienie zasad pozwala określić, które sterowniki rozruchu są inicjowane na podstawie klasyfikacji określonej przez sterownik rozruchu wczesnej ochrony przed złośliwym kodem. Sterownik rozruchu wczesnej ochrony przed złośliwym kodem może zwrócić następujące klasyfikacje dla każdego sterownika rozruchu: — Dobry: sterownik został podpisany i nie został naruszony.  
  - *Zły* — sterownik został zidentyfikowany jako złośliwy kod. Zaleca się, aby nie zezwalać na inicjowanie znanych nieprawidłowych sterowników. — Zły, ale wymagany do rozruchu: sterownik został zidentyfikowany jako złośliwy kod, ale komputer nie może pomyślnie wykonać rozruchu bez załadowania tego sterownika. 
  - *Nieznany* — ten sterownik ma nie zaświadczenia aplikacji wykrywania złośliwego kodu i nie został sklasyfikowany przez sterownik rozruchu wczesnej ochrony przed złośliwym kodem.  

  Jeśli to ustawienie zasad zostanie włączone, będzie można wybrać sterowniki rozruchu, które mają być inicjowane przy następnym uruchomieniu komputera. Jeśli to ustawienie zasad zostanie wyłączone lub nie zostanie skonfigurowane, zostaną zainicjowane sterowniki rozruchu uznane za dobre, nieznane lub złe, ale wymagane do rozruchu, a inicjowanie sterowników uznanych za nieprawidłowe zostanie pominięte. Jeśli aplikacja wykrywania złośliwego kodu nie zawiera sterownika rozruchu wczesnej ochrony przed złośliwym kodem lub sterownik rozruchu wczesnej ochrony przed złośliwym kodem została wyłączona, to ustawienie nie obowiązuje i są inicjowane wszystkie sterowniki rozruchu.  
  - **Ustawienie domyślne**: Dobry nieznany i zły krytyczny

## <a name="wi-fi"></a>Wi-Fi  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — Wifi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi) w dokumentacji systemu Windows.  

- **Wi-Fi**  
  Określa, czy udostępnianie Internetu jest obsługiwane przez urządzenie.
  - **Ustawienie domyślne**: Tak  

- **Blokuj automatyczne połączenia z hotspotami Wi-Fi**  
  Zezwalaj lub nie zezwalaj na automatyczne połączenia urządzenia z hotspotami Wi-Fi.  
  - **Ustawienie domyślne**: Tak  
  
## <a name="windows-connection-manager"></a>Menedżer połączeń systemu Windows  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — WindowsConnectionManager](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsconnectionmanager) w dokumentacji systemu Windows.  

- **Blokuj połączenia z sieciami nienależącymi do domeny**  
  To ustawienie zasad uniemożliwia komputerom łączenie się z siecią opartą na domenie i siecią nienależącą do domeny w tym samym czasie. Jeśli to ustawienie zasad zostanie włączone, komputer będzie odpowiadać na próby automatycznego i ręcznego nawiązania połączenia sieciowego zależnie od następujących okoliczności: 
  - Próby automatycznego połączenia Gdy komputer jest już połączony z siecią opartą na domenie, wszystkie próby automatycznego połączenia z sieciami spoza domeny będą blokowane. Gdy komputer jest już połączony z siecią nienależącą do domeny, próby automatycznego połączenia z sieciami opartymi na domenie będą blokowane. 
  - Próby ręcznego połączenia Gdy komputer jest już połączony z siecią nienależącą do domeny lub siecią opartą na domenie przez nośnik inny niż Ethernet, a użytkownik próbuje utworzyć ręczne połączenie z dodatkową siecią niezgodnie z tym ustawieniem zasad, istniejące połączenie sieciowe zostanie zakończone i ręczne połączenie będzie dozwolone. Gdy komputer jest już połączony z siecią nienależącą do domeny lub siecią opartą na domenie przez protokół Ethernet, a użytkownik próbuje utworzyć ręczne połączenie z dodatkową siecią niezgodnie z tym ustawieniem zasad, istniejące połączenie Ethernet zostanie zachowane i próba ręcznego połączenia zostanie zablokowana.  

  Jeśli to ustawienie zasad nie zostanie skonfigurowane lub zostanie wyłączone, komputery będą mogły łączyć się jednocześnie z sieciami należącymi do domeny i nienależącymi do domeny.
  - **Ustawienie domyślne**: Enabled
  
## <a name="windows-defender"></a>Usługa Windows Defender  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) w dokumentacji systemu Windows.  

- **Skanuj przychodzące wiadomości e-mail**  
  Zezwala lub nie zezwala na skanowanie wiadomości e-mail.
  - **Ustawienie domyślne**: Tak  

- **Uruchamianie typu procesów podrzędnych przez aplikacje pakietu Office**  
  Aplikacje pakietu Office nie będą mogły tworzyć procesów podrzędnych. Dotyczy to też programów Word, Excel, PowerPoint, OneNote i Access. Jest to typowe zachowanie złośliwego oprogramowania, szczególnie w przypadku ataków opartych na makrach, które polegają na próbie uruchomienia lub pobrania złośliwych plików wykonywalnych za pomocą aplikacji pakietu Office.
  - **Ustawienie domyślne**: Zablokowanie
  
- **Typ zgody na przesyłanie przykładów usługi Defender**  
  Sprawdza poziom zgody użytkownika na wysyłanie danych w usłudze Windows Defender. Jeśli udzielono już wymaganej zgody, usługa Windows Defender prześle dane. W przeciwnym razie (jeśli użytkownik wybrał, aby nigdy nie wyświetlać pytania) przed wysłaniem danych zostanie uruchomiony interfejs użytkownika z pytaniem o zgodę użytkownika (jeśli zezwolono na element Defender/AllowCloudProtection).
  - **Ustawienie domyślne**: Automatycznie wyślij bezpieczne próbki 
  
- **Interwał aktualizacji sygnatur (w godzinach)**  
  Interwał aktualizacji sygnatur usługi Defender (w godzinach)
  - **Ustawienie domyślne**: 4
  
- **Typ wykonywania pobranego ładunku skryptu**  
  Typ wykonywania pobranego ładunku skryptu usługi Defender
  - **Ustawienie domyślne**: Zablokowanie
  
- **Typ zapobiegania kradzieży poświadczeń**  
  Funkcja Windows Defender Credential Guard używa zabezpieczeń opartych na wirtualizacji do izolowania kluczy tajnych, aby tylko uprzywilejowane oprogramowanie systemowe mogło uzyskiwać do nich dostęp. Nieautoryzowany dostęp do tych kluczy tajnych może prowadzić do ataków przy użyciu skradzionych poświadczeń, takich jak „pass the hash” lub „pass the ticket”. Funkcja Windows Defender Credential Guard zapobiega atakom przez ochronę skrótów haseł NTLM, biletów uprawniających do przyznawania biletów protokołu Kerberos i poświadczeń przechowywanych przez aplikacje, takich jak poświadczenia domeny.
  - **Ustawienie domyślne**: Włącz

- **Typ wykonywania zawartości wiadomości e-mail**  
  Ta reguła blokuje możliwość uruchamiania następujących typów plików z wiadomości e-mail w programie Microsoft Outlook lub poczcie internetowej (np. Gmail.com lub Outlook.com): Pliki wykonywalne (takie jak exe, dll lub scr), pliki skryptów (takie jak pliki ps programu PowerShell, pliki vbs języka Visual Basic lub pliki js języka JavaScript) i pliki archiwum skryptów.
  - **Ustawienie domyślne**: Zablokowanie
  
- **Typ ochrony sieci**  
  Ta zasada umożliwia włączenie lub wyłączenie ochrony sieci (blokowanie/inspekcja) w funkcji Windows Defender Exploit Guard. Ochrona sieci w funkcji Windows Defender Exploit Guard chroni pracowników używających dowolnej aplikacji przed wyłudzeniem informacji, witrynami hostującymi programy wykorzystujące luki w zabezpieczeniach i złośliwą zawartością w Internecie. Obejmuje to blokadę połączeń w przeglądarkach innych firm z niebezpiecznymi witrynami. Typ wartości to liczba całkowita. Jeśli to ustawienie zostanie włączone, ochrona sieci zostanie włączona i pracownicy nie będą mogli jej wyłączyć. Jej zachowaniem można sterować przy użyciu następujących opcji: Blokada i inspekcja. Jeśli te zasady zostaną włączone z opcją „Blokada”, użytkownicy/aplikacje nie będą mogły łączyć się z niebezpiecznymi domenami. Ta aktywność będzie widoczna w usłudze Windows Defender Security Center. Jeśli te zasady zostaną włączone z opcją „Inspekcja”, użytkownicy/aplikacje będą mogły łączyć się z niebezpiecznymi domenami. Ta aktywność będzie jednak nadal widoczna w usłudze Windows Defender Security Center. Jeśli te zasady zostaną wyłączone, użytkownicy/aplikacje będą mogły łączyć się z niebezpiecznymi domenami. Aktywność sieci nie będzie widoczna w usłudze Windows Defender Security Center. Jeśli te zasady nie zostaną skonfigurowane, blokada sieci zostanie domyślnie wyłączona.
  - **Ustawienie domyślne**: Włącz
  
- **Zaplanowany dzień skanowania w usłudze Defender**  
  Zaplanowany dzień skanowania w usłudze Defender.
  - **Ustawienie domyślne**: Codzienne
  
- **Ochrona w chmurze**  
  Aby najlepiej chronić komputer, usługa Windows Defender będzie wysyłać do firmy Microsoft informacje dotyczące wykrytych problemów. Firma Microsoft przeanalizuje te informacje, dowie się więcej na temat problemów wpływających na Ciebie i innych klientów oraz zaoferuje ulepszone rozwiązania.
  - **Ustawienie domyślne**:  Tak  

- **Działanie dotyczące potencjalnie niechcianej aplikacji w usłudze Defender**  
  Funkcja ochrony przed potencjalnie niechcianymi aplikacjami w programie antywirusowym Windows Defender wykrywa i blokuje pobieranie potencjalnie niechcianych aplikacji oraz instalowanie w punktach końcowych w sieci. Te aplikacje nie są uważane za wirusy, złośliwe oprogramowanie ani innego typu zagrożenia, ale mogą wykonywać akcje w punktach końcowych, które niekorzystnie wpływają na wydajność lub sposób użycia. Potencjalnie niechcianymi aplikacjami mogą też być aplikacje o złej reputacji. Typowe zachowanie potencjalnie niechcianej aplikacji obejmuje: Różne typy oprogramowania tworzące pakiety dodawania reklam do przeglądarek internetowych Optymalizatory sterowników i rejestru, które wykrywają problemy, żądają płatności za usunięcie błędów, ale pozostają w punkcie końcowym i nie wprowadzają zmian ani optymalizacji (nazywane też nieautoryzowanymi programami antywirusowymi) Te aplikacje mogą zwiększyć ryzyko zainfekowania sieci przez złośliwe oprogramowanie, utrudnić wykrywanie infekcji złośliwym oprogramowaniem i marnować zasoby IT na czyszczenie aplikacji.  
  - **Ustawienie domyślne**: Zablokowanie  

- **Typ zaciemnionego kodu makra skryptu**  
  Złośliwe oprogramowanie i inne zagrożenia mogą próbować zaciemniać lub ukrywać złośliwy kod w niektórych plikach skryptów. Ta reguła uniemożliwia uruchamianie skryptów, które wydają się zaciemnione.
  - **Ustawienie domyślne**: Zablokowanie
  
- **Skanuj dyski wymienne podczas pełnego skanowania**  
  Umożliwia usłudze Windows Defender skanowanie pod kątem złośliwego i niechcianego oprogramowania na dyskach wymiennych (na przykład dyski flash) podczas pełnego skanowania. Program antywirusowy Windows Defender skanuje wszystkie pliki na urządzeniach USB przed wykonaniem.
  - **Ustawienie domyślne**: Tak  
  
- **Skanuj pliki archiwum**  
  Usługa Defender skanuje pliki archiwum.
  - **Ustawienie domyślne**: Tak
  
- **Monitorowanie zachowania**  
  Zezwala lub nie zezwala na działanie funkcji monitorowania zachowania usługi Windows Defender. Te czujniki osadzone w systemie Windows 10 zbierają i przetwarzają sygnały dotyczące zachowania z systemu operacyjnego i wysyła te dane czujników do prywatnego izolowanego wystąpienia usługi Windows Defender ATP w chmurze.
  - **Ustawienie domyślne**: Tak

- **Skanuj pliki otwierane z folderów sieciowych**  
  Jeśli pliki są tylko do odczytu, użytkownik nie będzie mógł usunąć wykrytego złośliwego oprogramowania.
  - **Ustawienie domyślne**: Tak

- **Niezaufany typ procesu USB**  
  Za pomocą tej reguły administratorzy mogą blokować uruchamianie niepodpisanych lub niezaufanych plików wykonywalnych z wymiennych dysków USB, w tym kart SD.
  - **Ustawienie domyślne**: Zablokowanie
  
- **Typ wstrzykiwania innych procesów aplikacji pakietu Office**  
  Aplikacje pakietu Office, w tym programy Word, Excel, PowerPoint i OneNote, nie będą mogły wstrzykiwać kodu do innych procesów. Zazwyczaj jest to używane przez złośliwe oprogramowanie, aby uruchomić złośliwy kod w celu ukrycia aktywności przed aparatami skanowania antywirusowego.
  - **Ustawienie domyślne**:  Zablokowanie
  
- **Kod makr w pakiecie Office zezwala na typ importu elementów Win32**  
  Złośliwe oprogramowanie może używać kodu makra w plikach pakietu Office, aby importować i ładować biblioteki DLL Win32, za pomocą których można następnie wykonywać wywołania interfejsu API w celu dalszego zainfekowania systemu. Ta reguła próbuje zablokować pliki pakietu Office zawierające kod makra, który umożliwia importowanie bibliotek DLL Win32. Dotyczy to też programów Word, Excel, PowerPoint i OneNote.
  - **Ustawienie domyślne**: Zablokowanie  
  
- **Poziom blokady chmury w usłudze Defender**  
  Poziom blokady chmury w usłudze Defender.
  - **Ustawienie domyślne**: Nieskonfigurowane

- **Monitorowanie w czasie rzeczywistym**  
  Usługa Defender wymaga monitorowania w czasie rzeczywistym.
  - **Ustawienie domyślne**: Tak
  
- **Tworzenie wykonywalnej zawartości lub typ uruchamiania aplikacji pakietu Office**  
  Ta reguła dotyczy typowego zachowania używanego przez podejrzane i złośliwe dodatki oraz skrypty (rozszerzenia), które powoduje tworzenie lub uruchamianie plików wykonywalnych. Jest to typowa technika złośliwego oprogramowania. Używanie rozszerzeń przez aplikacje pakietu Office zostanie zablokowane. Zazwyczaj te rozszerzenia używają hosta skryptów systemu Windows (pliki wsh), aby uruchamiać skrypty, które automatyzują określone zadania lub udostępniają dodatkowe funkcje utworzone przez użytkownika
  - **Ustawienie domyślne**: Zablokowanie

## <a name="windows-ink-workspace"></a>Obszar roboczy funkcji Windows Ink  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — WindowsInkWorkspace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace) w dokumentacji systemu Windows.  

- **Obszar roboczy pisma odręcznego**  
  Określa, czy użytkownik może uzyskać dostęp do obszaru roboczego pisma odręcznego. 0 — dostęp do obszaru roboczego pisma odręcznego jest wyłączony. Funkcja jest wyłączona. 1 — obszar roboczy pisma odręcznego jest włączony (funkcja jest włączona), ale użytkownik nie może uzyskać dostępu do niego powyżej ekranu blokady. 2 (domyślnie) — obszar roboczy pisma odręcznego jest włączony (funkcja jest włączona), a użytkownik może używać jej powyżej ekranu blokady.
  - **Ustawienie domyślne**: Enabled
 
## <a name="windows-powershell"></a>Windows PowerShell  
Więcej informacji można znaleźć na stronie [Dostawca usługi konfiguracji zasad — WindowsPowerShell](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowspowershell) w dokumentacji systemu Windows.  

- **Rejestrowanie bloków skryptu w powłoce programu PowerShell**  
  To ustawienie zasad umożliwia rejestrowanie wszystkich danych wejściowych skryptu programu PowerShell w dzienniku zdarzeń Microsoft-Windows-PowerShell/Operational. Jeśli to ustawienie zasad zostanie włączone, program Windows PowerShell będzie rejestrować przetwarzanie poleceń, bloków skryptu, funkcji i skryptów wywoływanych interakcyjnie lub przy użyciu automatyzacji. Jeśli to ustawienie zasad zostanie wyłączone, rejestrowania danych wejściowych skryptu programu PowerShell zostanie wyłączone. Jeśli włączysz rejestrowanie wywołań bloków skryptu, program PowerShell dodatkowo będzie rejestrował zdarzenia w przypadku uruchomienia lub zatrzymania wywołania polecenia, bloku skryptu, funkcji lub skryptu. Włączenie rejestrowania wywołań generuje dużą liczbę dzienników zdarzeń. Uwaga: to ustawienie zasad istnieje w konfiguracji komputera i konfiguracji użytkownika w edytorze zasad grupy. Ustawienie zasad konfiguracji komputera ma pierwszeństwo przed ustawieniem zasad konfiguracji użytkownika.
  - **Ustawienie domyślne**: Enabled
 
