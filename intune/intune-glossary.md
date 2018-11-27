---
title: Słownik usługi Microsoft Intune
titleSuffix: Microsoft Intune
description: Zapoznaj się z terminologią dotyczącą usługi Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 07/28/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bd7b5613-ee9f-4dc3-990c-ab4c1d40720d
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: bfab6f5f9c3b083ebcb0cee8820149fed7ce5c94
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52188071"
---
# <a name="microsoft-intune-glossary"></a>Słownik usługi Microsoft Intune
Poznaj definicje typowych terminów używanych w usłudze Microsoft Intune.

## <a name="a"></a>A

|||
|-|-|
|Przypisanie aplikacji|Umożliwia użytkownikom [znajdowanie, pobieranie i instalowanie](/intune/app-management) potrzebnych im aplikacji. Ta funkcja była wcześniej znana jako *wdrażanie aplikacji*.|
|Profil konfiguracji aplikacji <br/><br/>Zasady konfiguracji aplikacji|Dostępne dla aplikacji mobilnych z konfiguracjami specyficznymi dla dostawcy. Konfiguruje aplikację dla systemu [iOS](/intune/app-configuration-policies-use-ios) lub [Android](/intune/app-configuration-policies-use-android) przy użyciu konkretnych ustawień, zanim zostanie ona uruchomiona.|
|Monitorowanie aplikacji|Umożliwia [sprawdzenie ostatniego stanu i przejrzenie działań](/intune/apps-monitor) związanych z przypisaniem aplikacji.|
|Zadanie usuwania danych w ramach ochrony aplikacji|[Usuwa dane aplikacji](/intune/app-protection-policies) z urządzenia użytkownika.|
|Zasady ochrony aplikacji|Dostępne dla aplikacji mobilnych integrujących się z technologią pakietu Enterprise Mobility + Security (EMS). Zapewnia, że aplikacje użytkownika są zgodne z [zasadami ochrony danych firmy](/intune/app-protection-policies).|
|Zestaw SDK aplikacji|[Zestaw SDK aplikacji usługi Microsoft Intune](/intune/app-sdk) umożliwia dodawanie funkcji do aplikacji utworzonych we własnym zakresie, co pozwala na zarządzanie tymi aplikacjami za pośrednictwem zasad ochrony aplikacji usługi Intune.|
|Akcja odinstalowania aplikacji|Umożliwia [odinstalowanie aplikacji](/intune/apps-deploy) z urządzeń użytkownika.|
|Narzędzie opakowujące aplikacje|[Aplikacja wiersza polecenia](/intune/apps-prepare-mobile-application-management) tworząca warstwę opakowującą aplikację biznesową, która z kolei umożliwia zarządzanie aplikacją za pośrednictwem zasad ochrony aplikacji.|
|Akcja przypisania|Wybór dokonywany podczas [wdrażania aplikacji](/intune/apps-deploy). Można zdecydować, czy instalacja danej aplikacji będzie obowiązkowa (wymagana) czy opcjonalna (dostępna), lub odinstalować tę aplikację.|
|Dostępna instalacja|Po wdrożeniu aplikacji za pomocą tej akcji aplikacja jest wyświetlana w portalu firmy, a użytkownicy mogą [zainstalować ją na żądanie](/intune/apps-deploy).|
|Portal Azure|Nowa konsola usługi Intune. [Dowiedz się więcej](/intune/what-is-intune).|

## <a name="b"></a>B

|||
|-|-|
|„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)|[„Przynieś własne urządzenie”](/intune/device-enrollment). Użytkownicy mogą instalować aplikację Portal firmy usługi Intune na urządzeniach, a następnie rejestrować je, aby uzyskać dostęp do zasobów firmy, takich jak poczta e-mail, aplikacje firmowe, dane firmowe i pomoc techniczna.|

## <a name="c"></a>C

|||
|-|-|
|Profil certyfikatu|Ten typ zasad służy do [uzyskiwania bezpiecznego dostępu do zasobów firmowych](/intune/certificates-configure) przy użyciu certyfikatów podczas korzystania z sieci Wi-Fi, poczty e-mail lub profilów sieci VPN.|
|COD|[Urządzenia należące do firmy](/intune/device-enrollment) można rejestrować na różne sposoby, w zależności od potrzeb organizacji i typów zarządzanych urządzeń.|
|Portal firmy|Aplikacja lub witryna internetowa, która zapewnia użytkownikom [dostęp do firmowych danych i aplikacji](/intune/company-portal-customize).|
|Zasady zgodności|Zapewniają, że urządzenia [są zgodne z określonymi regułami](/intune/device-compliance), takimi jak wymaganie użycia numeru PIN w celu uzyskania dostępu do urządzenia lub szyfrowanie danych przechowywanych w urządzeniu.|
|Zgodne i niezgodne aplikacje|Te ustawienia są częścią [profilu ograniczeń urządzenia](/intune/device-restrictions-configure) i pozwalają zdefiniować listę aplikacji, które mogą lub nie mogą być uruchamiane przez użytkowników. Usługa Intune informuje następnie za pomocą. raportów o zainstalowaniu bądź uruchomieniu niezgodnych aplikacji. W przypadku niektórych platform usługa Intune może również zablokować instalację niezgodnych aplikacji.|
|Dostęp warunkowy|[Zezwala na dostęp do firmowej poczty e-mail, usługi Office 365 i innych usług](/intune/conditional-access) tylko za pomocą urządzeń zgodnych z ustawionymi przez Ciebie regułami.|
|Zasady niestandardowe|[Zasad tych należy użyć](/intune/custom-settings-configure) w sytuacji, gdy ogólne zasady konfiguracji nie zawierają wbudowanego ustawiania, które spełnia określone potrzeby. Za pomocą zasad niestandardowych możesz na przykład utworzyć ustawienie przy użyciu innych metod, takich jak program Apple Configurator lub identyfikator URI OMA.|

## <a name="d"></a>D

|||
|-|-|
|wdrażania|Czynność wysyłania aplikacji lub zasad na zarządzane urządzenie lub do zarządzanego użytkownika. Ta czynność jest teraz określana jako *przypisanie*.|
|Menedżer rejestracji urządzeń|Organizacje mogą używać usługi Intune do zarządzania dużą liczbą urządzeń przenośnych za pomocą jednego konta użytkownika. Konto [menedżera rejestracji urządzeń](/intune/device-enrollment-program-enroll-ios) jest specjalnym kontem usługi Intune umożliwiającym zarejestrowanie do 1000 urządzeń.|
|Profile urządzeń|[Profile](/intune/device-profile-create), które pozwalają skonfigurować szeroki zakres zabezpieczeń, funkcji i ustawień dostępu na urządzeniach zarządzanych przez użytkownika.|

## <a name="e"></a>E

|||
|-|-|
|Profil e-mail|Za pomocą tych zasad można skonfigurować [ustawienia dostępu do poczty e-mail](/intune/email-settings-configure) na urządzeniach mobilnych, co pozwala zminimalizować liczbę czynności konfiguracyjnych, które musi wykonać użytkownik końcowy.|
|EMS|Rozwiązanie Microsoft Enterprise Mobility + Security (dawniej pakiet Enterprise Mobility Suite) zapewnia ochronę danych firmowych, zezwalając jednocześnie użytkownikom na [dostęp do potrzebnych aplikacji i zawartości](https://www.microsoft.com/cloud-platform/enterprise-mobility).|
|Użytkownik końcowy|[Użytkownicy końcowi urządzeń, takich jak telefony i komputery](/intune/end-user-educate) zarządzani za pomocą usługi Intune.|
|Zarejestruj|Usługa Microsoft Intune używa [rejestracji](/intune/device-enrollment), która umożliwia zarządzanie urządzeniami i zezwala na nich na dostęp do zasobów.|

## <a name="f"></a>F

|||
|-|-|
|FastTrack|[Usługa firmy Microsoft](https://technet.microsoft.com/library/mt228265.aspx) dla użytkowników usługi Intune ze 150 licencjami w uprawniającym planie. W ramach tej usługi specjaliści firmy Microsoft będą współpracować z użytkownikiem, aby ułatwić szybkie rozpoczęcie korzystania z usługi Intune.|

## <a name="g"></a>G

|||
|-|-|
|Grupy|Grupy pozwalają [logicznie zbierać razem użytkowników lub urządzenia](/intune/groups-get-started). Możesz na przykład utworzyć grupę wszystkich komputerów z systemem Windows. Następnie można przypisać aplikacje i profile do tych grup.|

## <a name="h"></a>H

|||
|-|-|
|Hybrydowe|Konfiguracja, w ramach której możesz zarządzać urządzeniami zarejestrowanymi w usłudze Intune za pomocą konsoli programu System Center Configuration Manager.|

## <a name="i"></a>I

|||
|-|-|
|Witryna Azure Portal|Witryna Azure Portal używana do wykonywania większości działań administracyjnych w usłudze Intune.|
|Oprogramowanie klienckie usługi Intune|Alternatywny sposób [zarządzania niektórymi komputerami z systemem Windows](/intune-classic/get-started/choose-how-to-manage-devices) w celu uzyskania pomocy przy wyborze metody.|
|Wydawcy oprogramowania usługi Intune|Narzędzie, za pomocą którego [definiujesz aplikacje, które chcesz wdrożyć, i przekazujesz te aplikacje do magazynu w chmurze](/intune-classic/deploy-use/add-apps).|
|Stan zapasów|Służy do wyświetlania [sprzętu i zainstalowanego oprogramowania](/intune/device-inventory) urządzeń, którymi zarządzasz.|

## <a name="k"></a>K

|||
|-|-|
|Tryb kiosku|Tryb ten pozwala blokować urządzenia. Jest on konfigurowany w [profilu ograniczeń urządzenia](/intune/device-restrictions-configure). Można na przykład skonfigurować urządzenie sieci sprzedaży, aby zezwalać na nim na uruchomienie tylko niektórych aplikacji.|

## <a name="m"></a>M

|||
|-|-|
|Managed Browser|[Aplikacja służąca do przeglądania sieci Web](/intune/app-configuration-managed-browser), którą można przypisać w organizacji za pomocą usługi Microsoft Intune. Zasady programu Managed Browser umożliwiają skonfigurowanie listy dozwolonych lub zablokowanych witryn sieci Web ograniczającej zakres witryn, które użytkownicy programu Managed Browser mogą odwiedzać.|
|Urząd zarządzania urządzeniami przenośnymi|[Urząd MDM](/intune/mdm-authority-set) definiuje usługę zarządzania z uprawnieniami do zarządzania zestawem urządzeń. Opcje przeznaczone dla urzędu zarządzania urządzeniami przenośnymi obejmują samą usługę Intune oraz program Configuration Manager z usługą Intune.|
|Zasady konfiguracji aplikacji mobilnych|Dostępne dla aplikacji mobilnych z konfiguracjami specyficznymi dla dostawcy. Na przykład zasady dotyczące systemu [iOS](/intune/app-configuration-policies-use-ios) lub [Android](/intune/app-configuration-policies-use-android), które służą do określania ustawień dla zgodnych aplikacji podczas ich uruchamiania (np. nazwa firmy lub adres serwera).|
|Zasady inicjowania obsługi administracyjnej aplikacji mobilnych|Zasady dotyczące systemu iOS, które ułatwiają zapewnienie, że [profile aprowizacji](/intune/app-provisioning-profile-ios) wdrażanych aplikacji dla systemu iOS nie wygasną.|
|Zarządzanie aplikacjami mobilnymi|[Zarządzanie aplikacjami mobilnymi (MAM, mobile application management)](/intune/app-lifecycle) pozwala publikować, wypychać, konfigurować, zabezpieczać, monitorować i aktualizować aplikacje mobilne dla użytkowników.
|Zarządzanie urządzeniami przenośnymi|[Zarządzanie urządzeniami mobilnymi (MDM)](/intune/device-lifecycle) pozwala rejestrować urządzenia w usłudze Intune w sposób umożliwiający ich aprowizowanie, konfigurowanie, monitorowanie i zarządzanie nimi.



## <a name="o"></a>O

|||
|-|-|
|Protokół OMA-DM|Zarządzanie urządzeniami Open Mobile Alliance (Open Mobile Alliance Device Management). Będący standardem branżowym protokół zarządzania urządzeniami używany przez wielu producentów sprzętu w celu umożliwienia sterowania funkcjami urządzeń przenośnych i komputerów.|
|Identyfikator URI OMA|Jednolity identyfikator zasobów Open Mobile Alliance (Open Mobile Alliance Uniform Resource Identifier). Te elementy identyfikują poszczególne ustawienia urządzeń zgodne ze standardem OMA-DM. Z tych ustawień można korzystać w [niestandardowych profilach usługi Intune](/intune/custom-settings-configure), gdy nie ma wbudowanego ustawienia spełniającego określone potrzeby.|

## <a name="p"></a>P

|||
|-|-|
|Resetowanie kodu dostępu|Funkcja usługi Intune pozwalająca wymuszać na użytkownikach końcowych [resetowanie kodów dostępu](/intune/device-passcode-reset) na obsługiwanych urządzeniach.|

## <a name="r"></a>R

|||
|-|-|
|Zdalne blokowanie|Funkcja usługi Intune pozwalająca [blokować obsługiwane urządzenia](/intune/device-remote-lock), nawet bez fizycznego dostępu do nich.|
|Wymagana instalacja|Po przypisaniu aplikacji za pomocą tej akcji do ukończenia instalacji nie jest wymagana [interwencja użytkownika](/intune/apps-deploy). (Na niektórych platformach niezbędne może być zaakceptowanie instalacji przez użytkownika końcowego).|


## <a name="s"></a>S

|||
|-|-|
|Selektywne czyszczenie danych|[Selektywne czyszczenie danych](/intune/device-company-data-remove) powoduje usunięcie z urządzenia tylko danych firmowych, dla których mają zastosowanie zasady ochrony aplikacji, w tym ustawień i profilów poczty e-mail. Selektywne czyszczenie danych nie powoduje usunięcia osobistych danych użytkownika z urządzenia.|
|Pobieranie lokalne|Akcja instalowania aplikacji biznesowych bez uzyskiwania dostępu do nich ze sklepu z aplikacjami.|
|Subskrypcja|Zawarta umowa, która umożliwia dostęp do dzierżawy usługi Intune.|

## <a name="t"></a>T

|||
|-|-|
|TeamViewer|Aplikacja innej firmy współdziałająca z usługą Intune w celu udostępnienia [funkcji pomocy zdalnej](/intune/device-profile-android-teamviewer) na urządzeniu z systemem Android zarządzanym w usłudze Intune.|
|Dzierżawca|Pojedyncze wystąpienie usługi Intune, do której można uzyskać dostęp dzięki subskrypcji.|
|Warunki i postanowienia|Typ przypisywanych do użytkowników zasad zawierających informacje, które użytkownicy muszą [przeczytać i zaakceptować](/intune/terms-and-conditions-create), zanim będą mogli za pomocą Portalu firmy zarejestrować swoje urządzenia i uzyskać dostęp do swojej pracy.|

## <a name="v"></a>V

|||
|-|-|
|Aplikacje i książki kupione w ramach zakupów zbiorczych|Niektóre sklepy z aplikacjami umożliwiają zakup wielu licencji aplikacji lub książek, które mają być wykorzystywane w firmie. Usługa Intune ułatwia zarządzanie aplikacjami i książkami [kupionymi za pośrednictwem takiego programu](/intune/vpp-apps). Można zaimportować informacje o licencjach z dowolnego sklepu z aplikacjami, śledzić liczbę wykorzystanych licencji oraz uniemożliwić użytkownikom instalowanie większej liczby kopii aplikacji, niż jest dla nich dostępna.|
|Profil sieci VPN|Zasady przypisujące [ustawienia sieci VPN](/intune/vpn-settings-configure) do urządzeń zarządzanych przez użytkownika. Zasady te pozwalają zminimalizować wszelkie czynności konfiguracyjne wymagane od użytkowników końcowych.|

## <a name="w"></a>W

|               |                                                                                                                                                                                                 |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Profil sieci Wi-Fi | Zasady przypisujące [ustawienia sieci bezprzewodowej](/intune/wi-fi-settings-configure) do urządzeń, aby umożliwić użytkownikom łączenie się z siecią firmową bez znajomości lub konfigurowania jakichkolwiek ustawień. |

