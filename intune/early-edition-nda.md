---
title: Wczesna wersja
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ad49b983bd5dc72a3355cba5645192456a555e38
ms.sourcegitcommit: e8e8164586508f94704a09c2e27950fe6ff184c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321258"
---
# <a name="the-early-edition-for-microsoft-intune---july-2018"></a>Wczesna wersja usługi Microsoft Intune — lipiec 2018

> [!Note]
> Powiadomienie umowy o zachowaniu poufności: dla usługi Intune opracowywane są następujące zmiany. Te informacje są udostępniane pod rygorem umowy o zachowaniu poufności w bardzo ograniczonym zakresie. Nie wolno publikować żadnych tych informacji w mediach społecznościowych ani w publicznych witrynach internetowych, takich jak Twitter, UserVoice, Reddit itd. 

**Wczesna wersja** zawiera listę funkcji udostępnianych w ramach umowy o zachowaniu poufności, które zostaną wprowadzone w przyszłych wydaniach usługi Microsoft Intune. Te informacje są przekazywane w ograniczonym zakresie i mogą ulec zmianie. Nie publikuj tweetów, wpisów na platformie UserVoice ani w inny sposób nie udostępniaj tych informacji poza swoją firmą. Niektóre funkcje wymienione w tym miejscu mogą nie być wdrożone na czas i zostać opóźnione do przyszłych wersji. Inne funkcje są testowane w wersji pilotażowej, aby zapewnić przygotowanie ich do użytku przez klientów. W przypadku pytań lub wątpliwości skontaktuj się z osobą kontaktową ds. tej grupy produktów firmy Microsoft.

Ta strona jest okresowo aktualizowana. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Usługa Intune w witrynie Azure Portal

<!-- 1807 start -->

### <a name="more-sync-opportunities-in-the-company-portal-app-for-windows----2683177---"></a>Więcej możliwości synchronizacji w aplikacji Portal firmy dla systemu Windows <!-- 2683177 -->
Aplikacja Portal firmy dla systemu Windows dodaje akcję synchronizacji urządzeń do paska zadań systemu Windows i list szybkiego dostępu w menu Start. Kliknięcie tej akcji w dowolnej lokalizacji umożliwia szybkie zsynchronizowanie urządzeń i uzyskanie dostępu do zasobów firmy.  

### <a name="reset-device-passcodes-from-company-portal-app-for-windows-10----2101282---"></a>Resetowanie kodów dostępu urządzeń w aplikacji Portal firmy dla systemu Windows 10 <!-- 2101282 --> 
Twoi pracownicy będą wkrótce mogli resetować numer PIN lub kod dostępu dla swoich urządzeń bezpośrednio w aplikacji Portal firmy dla systemu Windows 10. Ta funkcja będzie dostępna na urządzeniach zdalnych i lokalnych zarządzanych przez usługę Intune, które obsługują resetowanie kodu dostępu. W zależności od rodzaju urządzenia żądanie wykonane dla urządzenia zdalnego spowoduje usunięcie bieżącego kodu dostępu urządzenia lub utworzenie tymczasowego kodu dostępu. Użytkownicy, którzy zażądają zresetowania dla urządzenia lokalnego, zostaną przekierowani do aplikacji Ustawienia urządzenia.  

### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows----2317227---"></a>Nowe środowisko przeglądania w aplikacji Portal firmy dla systemu Windows <!-- 2317227 -->  
Podczas przeglądania w poszukiwaniu aplikacji lub ich wyszukiwania w aplikacji Portal firmy dla systemu Windows możliwe będzie przełączanie się między istniejącym widokiem **Kafelki** a nowo dodanym widokiem **Szczegóły**. W nowym widoku wyświetlane są szczegółowe informacje dotyczące aplikacji, takie jak nazwa, wydawca, data publikacji i stan instalacji.  

Na stronie **Aplikacje** zostanie wprowadzony widok **Zainstalowane**, w którym będą dostępne szczegóły dotyczące zakończonych i trwających instalacji aplikacji. Chcesz udostępnić opinię lub swoje przemyślenia dotyczące nowych zmian? Wyślij nam swoją opinię w aplikacji Portal firmy.

### <a name="improved-company-portal-app-experience-for-device-enrollment-manager-users----675800---"></a>Ulepszone środowisko aplikacji Portal firmy dla użytkowników menedżera rejestracji urządzeń <!-- 675800 -->
Gdy menedżer rejestracji urządzeń loguje się do aplikacji Portal firmy dla systemu Windows, w aplikacji będzie wyświetlane tylko bieżące, uruchomione urządzenie menedżera rejestracji urządzeń. To ulepszenie ograniczy występowanie przekroczeń limitu czasu, które wcześniej miały miejsce, gdy aplikacja podejmowała próbę załadowania wszystkich urządzeń zarejestrowanych w menedżerze rejestracji urządzeń.  

### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>Korzystanie z licencji programu VPP do wstępnego aprowizowania aplikacji Portal firmy podczas rejestracji w programie DEP <!-- 1608345 -->
Możliwe będzie używanie licencji urządzeń zakupionych w ramach programu VPP (Volume Purchase Program) do wstępnej aprowizacji aplikacji Portal firmy podczas rejestracji w programie DEP (Device Enrollment Program). W tym celu podczas tworzenia lub edytowania profilu rejestracji należy określić token programu VPP, który zostanie użyty do zainstalowania aplikacji Portal firmy. Upewnij się, że token nie wygasł, i że masz wystarczającą liczbę licencji dla aplikacji Portal firmy. W przypadkach, gdy token wygaśnie lub zabraknie dla niego licencji, usługa Intune wypchnie aplikację Portal firmy ze sklepu App Store (spowoduje to wyświetlenie monitu o podanie identyfikatora Apple ID).


### <a name="bulk-delete-devices-on-devices-blade----1793693---"></a>Zbiorcze usuwanie urządzeń w bloku urządzeń <!-- 1793693 -->
Możliwe będzie usunięcie wielu urządzeń naraz w bloku Urządzenia. Wybierz kolejno pozycje **Urządzenia** > **Wszystkie urządzenia** > wybierz urządzenia do usunięcia > **Usuń**. W przypadku urządzeń, których nie można usunąć, zostanie wyświetlony alert.

### <a name="new-wi-fi-device-configuration-profile-for-windows-10-and-later----1879077---"></a>Nowy profil konfiguracji urządzenia sieci Wi-Fi dla systemu Windows 10 i nowszych <!-- 1879077 -->
Obecnie profile sieci Wi-Fi można importować i eksportować przy użyciu plików XML. Teraz będzie można utworzyć profil konfiguracji urządzenia sieci Wi-Fi bezpośrednio w usłudze Intune, podobnie jak w przypadku niektórych innych platform.

Aby utworzyć profil, przejdź kolejno do pozycji **Konfiguracja urządzenia** > **Profile** > **Utwórz profil** > **System Windows 10 lub nowszy** > **Wi-Fi**. 

Dotyczy systemu Windows 10 lub nowszych.

###  <a name="windows-line-of-business-lob-apps-file-extensions----1884873---"></a>Rozszerzenia plików aplikacji biznesowych (LOB) dla systemu Windows <!-- 1884873 -->
Rozszerzenia plików aplikacji LOB dla systemu Windows obejmują teraz rozszerzenia *msi*, *appx*, *appxbundle*, *msix* i *msixbundle*. Aby dodać aplikację w usłudze Microsoft Intune, wybierz kolejno pozycje **Aplikacje mobilne** > **Aplikacje** > **Dodaj**. Zostanie wyświetlone okienko **Dodaj aplikację**, w którym możesz wybrać **Typ aplikacji**. Dla aplikacji LOB dla systemu Windows wybierz aplikację **Biznesowa** jako typ aplikacji, wybierz pozycję **Plik pakietu aplikacji**, a następnie wprowadź plik instalacyjny z odpowiednim rozszerzeniem.

### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Pakiet konfiguracji zaawansowanej ochrony przed zagrożeniami w usłudze Windows Defender jest automatycznie dodawany do profilu konfiguracji <!-- 2144658 -->
Obecnie w przypadku korzystania z [zaawansowanej ochrony przed zagrożeniami i dołączania](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile) urządzeń w usłudze Intune pobierasz pakiet konfiguracyjny i dodajesz go do swojego profilu konfiguracji. W ramach przyszłej aktualizacji usługa Intune automatycznie pobierze pakiet z usługi Windows Defender Security Center i doda go do Twojego profilu.

Dotyczy systemu Windows 10 lub nowszych.


### <a name="check-for-sccm-compliance----2192052---"></a>Sprawdzanie zgodności programu SCCM <!-- 2192052 -->
Przyszła aktualizacja będzie zawierać nowe ustawienie zgodności programu System Center Configuration Manager (SCCM) (**Zgodność urządzeń** > **Zasady** > **Tworzenie zasad**  > **System Windows 10**). Program SCCM wysyła sygnały zgodności do usługi Intune. Przy użyciu ustawienia usługi Intune można wymagać, aby wszystkie sygnały programu SCCM zwracały stan „zgodne”.

Na przykład można wymagać, aby na urządzeniach były zainstalowane wszystkie aktualizacje oprogramowania. W programie SCCM to wymaganie ma stan „Zainstalowano”. Jeśli jakiekolwiek programy na urządzeniu mają nieznany stan, to urządzenie będzie niezgodne w usłudze Intune.

Dotyczy: system Windows 10 lub nowszy

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Alerty dotyczące wygasającego tokenu VPP lub zbyt małej liczby licencji aplikacji Portal firmy <!-- 2237572 -->
Jeśli do wstępnej aprowizacji aplikacji Portal firmy podczas rejestracji programu DEP jest używany token programu Volume Purchase Program (VPP), usługa Intune powiadomi Cię, jeśli token VPP niedługo wygaśnie lub zaczyna brakować licencji aplikacji Portal firmy.

### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Wymagane potwierdzenie w celu usunięcia tokenu programu VPP, który jest używany do wstępnej aprowizacji aplikacji Portal firmy <!-- 2237634 -->
Wymagane będzie potwierdzenie w celu usunięcia tokenu programu Volume Purchase Program (VPP), jeśli jest on używany do wstępnej aprowizacji aplikacji Portal firmy podczas rejestracji programu DEP.


#### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Dodatkowe ustawienia zabezpieczeń dla Instalatora Windows <!-- 2282430 -->
Możliwe będzie zezwolenie użytkownikom na kontrolowanie instalacji aplikacji. Po włączeniu tej funkcji instalacje, które w przeciwnym razie mogły zostać zatrzymane z powodu naruszenia zabezpieczeń, będą kontynuowane. Możliwe będzie przekierowanie Instalatora Windows tak, aby używał podwyższonego poziomu uprawnień podczas instalowania dowolnego programu w systemie. Ponadto możliwe będzie indeksowanie elementów funkcji Windows Information Protection (WIP) oraz przechowywanie związanych z nimi metadanych w niezaszyfrowanej lokalizacji. Gdy zasady są wyłączone, elementy chronione przez funkcję WIP nie będą indeksowane i nie będą wyświetlane w wynikach w Cortanie ani Eksploratorze plików. Funkcje tych opcji będą domyślnie wyłączone. 


<!-- 1806 start -->


### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Klawiatury innych firm mogą zostać zablokowane przez ustawienia aplikacji w systemie iOS <!-- 1248481 -->
Na urządzeniach z systemem iOS administratorzy usługi Intune będą mogli zablokować możliwość korzystania z klawiatur innych firm podczas uzyskiwania dostępu do danych organizacji w aplikacjach chronionych przez zasady. Gdy zasady ochrony aplikacji są ustawione na blokowanie klawiatur innych firm, użytkownik urządzenia otrzyma komunikat podczas pierwszej próby interakcji z danymi firmowymi przy użyciu klawiatury innej firmy. Wszystkie opcje inne niż klawiatura macierzysta zostaną zablokowane, a użytkownicy urządzenia nie będą ich widzieć. Użytkownicy urządzenia zobaczą tylko raz komunikat w oknie dialogowym. 

### <a name="require-non-biometric-passcode-on-app-launch-and-timeout----1506985---"></a>Wymaganie niebiometrycznego kodu dostępu podczas uruchamiania aplikacji i po upłynięciu limitu czasu <!-- 1506985 -->

Wymagając niebiometrycznego kodu dostępu podczas uruchamiania aplikacji i po upłynięciu limitu czasu określonego przez administratora, usługa Intune zapewnia lepsze zabezpieczenia dla aplikacji z obsługą funkcji zarządzania aplikacjami mobilnymi (MAM) poprzez ograniczenie użycia identyfikacji biometrycznej na potrzeby dostępu do danych firmowych. Ustawienia będą miały wpływ na użytkowników, którzy korzystają z funkcji Touch ID (iOS), Face ID (iOS), Android Biometric lub innych przyszłych metod uwierzytelniania biometrycznego w celu uzyskiwania dostępu do swoich aplikacji z obsługą zasad ochrony aplikacji/funkcji MAM. Ustawienia te umożliwią administratorom usługi Intune uzyskanie większej kontroli nad dostępem użytkowników, eliminując przypadki, gdy urządzenie z wieloma odciskami palców lub innymi biometrycznymi metodami dostępu może ujawnić dane firmowe niewłaściwemu użytkownikowi. W witrynie Azure Portal otwórz usługę **Microsoft Intune**. Wybierz pozycję **Aplikacje mobilne** > **Zasady ochrony aplikacji** > **Dodaj zasadę** > **Ustawienia**. Znajdź sekcję **Dostęp** dla konkretnych ustawień.

### <a name="office-365-pro-plus-language-packs----1833450---"></a>Pakiety językowe usługi Office 365 Pro Plus <!-- 1833450 -->
Jako administrator usługi Intune możesz wdrożyć dodatkowe języki dla aplikacji pakietu Office 365 Pro Plus zarządzanych przez usługę Intune. Lista dostępnych języków uwzględnia **Typ** pakietu językowego (podstawowy, częściowy i weryfikujący). W witrynie Azure Portal wybierz pozycję **Microsoft Intune** > **Aplikacje mobilne** > **Aplikacje** > **Dodaj**. Na liście **Typ aplikacji** w bloku **Dodaj aplikację** wybierz pozycję **Windows 10** w obszarze **Pakiet Office 365**. Wybierz pozycję **Języki** w bloku **Ustawienia pakietu aplikacji**.

### <a name="preview-a-new-user-experience-update-for-the-company-portal-website---2000968---"></a>Wersja zapoznawcza nowego środowiska użytkownika witryny internetowej Portal firmy <!--2000968 -->
Na podstawie opinii klientów dodajemy nowe funkcje do witryny internetowej Portal firmy/katalogu aplikacji systemu iOS. Na urządzeniach z systemami Android, iOS i Windows zobaczysz znaczące ulepszenia istniejących funkcji i poprawę użyteczności. Obszary witryny — takie jak szczegółowe informacje o urządzeniu, opinie i pomoc techniczna oraz przegląd urządzenia — zyskają nowy, nowoczesny i dynamiczny wygląd. Ponadto wprowadziliśmy następujące zmiany:

- Usprawnione przepływy pracy na wszystkich platformach urządzeń
- Ulepszone przepływy identyfikacji i rejestracji urządzeń
- Bardziej pomocne komunikaty o błędach
- Bardziej przyjazny język, mniej technicznego żargonu
- Możliwość udostępniania bezpośrednich linków do aplikacji
- Zwiększona wydajność dużych wykazów aplikacji
- Zwiększona dostępność dla wszystkich użytkowników

Aktualizacja jest obecnie w wersji zapoznawczej. Możesz zarejestrować się, aby dołączyć do wersji zapoznawczej w http://aka.ms/webcpflighting


<!-- 1805 start -->

### <a name="require-non-biometric-passcode-on-cold-app-launch-and-timeout----1506985---"></a>Wymaganie niebiometrycznego kodu dostępu podczas zimnego uruchamiania aplikacji i po upłynięciu limitu czasu <!-- 1506985 --> 

Wymagając niebiometrycznego kodu dostępu podczas zimnego uruchamiania aplikacji i po upłynięciu limitu czasu określonego przez administratora, usługa Intune zapewnia lepsze zabezpieczenia dla aplikacji z obsługą funkcji zarządzania aplikacjami mobilnymi (MAM) poprzez ograniczenie użycia identyfikacji biometrycznej na potrzeby dostępu do danych firmowych. Ustawienia będą miały wpływ na użytkowników, którzy korzystają z funkcji Touch ID (iOS), Face ID (iOS), Android Biometric lub innych przyszłych metod uwierzytelniania biometrycznego w celu uzyskiwania dostępu do swoich aplikacji z obsługą zasad ochrony aplikacji/funkcji MAM. Ustawienia te umożliwią administratorom usługi Intune uzyskanie większej kontroli nad dostępem użytkowników, eliminując przypadki, gdy urządzenie z wieloma odciskami palców lub innymi biometrycznymi metodami dostępu może ujawnić dane firmowe niewłaściwemu użytkownikowi. W witrynie Azure Portal otwórz usługę **Microsoft Intune**. Wybierz pozycję **Aplikacje mobilne** > **Zasady ochrony aplikacji** > **Dodaj zasadę** > **Ustawienia**. Znajdź sekcję **Dostęp** dla konkretnych ustawień.


<!-- 1803 start -->

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Możliwość wdrożenia wymaganych aplikacji biznesowych (LOB) dla wszystkich użytkowników urządzeń z systemem Windows 10 Desktop <!-- 1627835 RS4 -->
Klienci będą mogli wdrażać wymagane aplikacje biznesowe systemu Windows 10 oraz instalować je w kontekstach urządzeń. Umożliwi to udostępnienie tych aplikacji wszystkim użytkownikom urządzenia. Dotyczy to tylko urządzeń z systemem Windows 10 Desktop.

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Aktualizowanie środowiska Pomoc i opinie w aplikacji Portal firmy dla systemu Android <!--1631531 -->

Środowisko Pomoc i opinie w aplikacji Portal firmy dla systemu Android zostanie zaktualizowane, aby było zgodne z najlepszymi rozwiązaniami dla aplikacji systemu Android. W ciągu kilku następnych miesięcy aplikacja Portal firmy dla systemu Android zostanie zaktualizowana, aby podzielić element menu **Pomoc i opinie** na oddzielne elementy **Pomoc** i **Prześlij opinię**. Strona **Pomoc** będzie zawierała sekcję **Często zadawane pytania** oraz przycisk **Pomoc techniczna pocztą e-mail**, który umożliwi użytkownikom końcowym przekazanie dzienników firmie Microsoft i wysłanie wiadomości e-mail do pomocy technicznej firmy wraz z opisem problemu. Funkcja **Prześlij opinię** przeprowadzi użytkownika przez standardowy proces przesyłania opinii, podczas którego użytkownik będzie mógł wybrać opcje takie jak „Coś mi się podoba”, „Coś mi się nie podoba”, „Mam pomysł”.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Zasady usługi App Protection <!-- 679615 -->
Zasady usługi Intune App Protection umożliwiają tworzenie globalnych, domyślnych zasad, które pozwalają na szybkie włączenie ochrony dla wszystkich użytkowników w całej dzierżawie.

<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Uwagi

Aktualnie nie ma aktywnych powiadomień.

### <a name="see-also"></a>Zobacz też
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).
