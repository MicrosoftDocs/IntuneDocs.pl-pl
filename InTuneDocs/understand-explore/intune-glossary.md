---
title: "Słownik usługi Intune | Microsoft Docs"
description: "Zapoznaj się z terminologią dotyczącą usługi Microsoft Intune"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/17/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 86d00901-fac7-4471-aac2-f1d13a4879b6
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 6b99854e17e00a0dd0f91fa82fd1b79d1dfe5663
ms.openlocfilehash: ea5407c284f5408774ee5934ad6151bccfd7e6d1
ms.lasthandoff: 02/18/2017


---

# <a name="microsoft-intune-glossary"></a>Słownik usługi Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="a"></a>A

|||
|-|-|
|Zestaw SDK aplikacji|[Zestaw SDK aplikacji usługi Microsoft Intune](/intune/develop/intune-app-sdk) pozwala dodawać funkcje do aplikacji utworzonych we własnym zakresie umożliwiające zarządzanie tymi aplikacjami za pośrednictwem zasad zarządzania aplikacjami mobilnymi usługi Intune.|
|Narzędzie opakowujące aplikacje|[Aplikacja wiersza polecenia](/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune) tworząca otokę aplikacji biznesowej, która następnie umożliwia zarządzanie aplikacją za pośrednictwem zasad zarządzania aplikacjami mobilnymi usługi Intune.|
|Dostępna instalacja|Po wdrożeniu aplikacji za pomocą tej akcji aplikacja jest wyświetlana w portalu firmy i użytkownicy mogą [zainstalować ją na żądanie](/intune/deploy-use/deploy-apps).|
|Portal Azure|Nowa konsola usługi Intune, która zostanie wkrótce wprowadzona. Obecnie za pomocą portalu Azure możesz tworzyć [zasady zarządzania aplikacjami mobilnymi usługi Intune](/intune/deploy-use/azure-portal-for-microsoft-intune-mam-policies) dla urządzeń.|

## <a name="b"></a>B
|||
|-|-|
|„Przynieś własne urządzenie” (BYOD, Bring Your Own Device)|[„Przynieś własne urządzenie”](/intune/get-started/choose-how-to-enroll-devices1). Użytkownicy mogą instalować aplikację Portal firmy usługi Intune na urządzeniach, a następnie rejestrować je, aby uzyskać dostęp do zasobów firmy, takich jak poczta e-mail, aplikacje firmowe, dane firmowe i pomoc techniczna.|

## <a name="c"></a>C
|||
|-|-|
|Profil certyfikatu|Ten typ zasad służy do [uzyskiwania bezpiecznego dostępu do zasobów firmowych](/intune/deploy-use/secure-resource-access-with-certificate-profiles) przy użyciu certyfikatów podczas korzystania z sieci Wi-Fi, poczty e-mail lub profilów sieci VPN.|
|Miejsce do magazynowania w chmurze|Miejsce, w którym [są przechowywane](/intune/deploy-use/add-apps#cloud-storage-space) aplikacje lub dane dotyczące tworzonych przez Ciebie aplikacji.|
|COD|[Urządzenia należące do firmy](/intune/get-started/choose-how-to-enroll-devices1) można rejestrować na różne sposoby, w zależności od potrzeb organizacji i typów zarządzanych urządzeń.|
|Portal firmy|Aplikacja lub witryna internetowa, która zapewnia użytkownikom [dostęp do firmowych danych i aplikacji](/intune/get-started/microsoft-intune-company-portal).|
|Zasady zgodności|Należy się upewnić, że urządzenia używane do uzyskiwania dostępu do aplikacji oraz danych firmowych [są zgodne z pewnymi regułami](/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune), takimi jak wymaganie użycia numeru PIN w celu uzyskania dostępu do urządzenia oraz szyfrowanie danych przechowywanych na urządzeniu.|
|Zgodne i niezgodne aplikacje|Te ustawienia będące częścią [ogólnych zasad konfiguracji](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) pozwalają zdefiniować listę aplikacji, które mogą bądź nie mogą być uruchamiane przez użytkowników. Następnie usługa Intune będzie Cię informować za pośrednictwem raportów o zainstalowaniu bądź uruchomieniu niezgodnych aplikacji. W przypadku niektórych platform usługa Intune może również zablokować instalację niezgodnych aplikacji.|
|Dostęp warunkowy|[Zezwala na dostęp do firmowej poczty e-mail, usługi Office 365 i innych usług](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) tylko za pomocą urządzeń zgodnych z ustawionymi przez Ciebie regułami.|
|Zasady niestandardowe|[Zasad tych należy użyć](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) w sytuacji, gdy ogólne zasady konfiguracji nie zawierają wbudowanego ustawiania, które spełnia określone potrzeby. Za pomocą zasad niestandardowych możesz na przykład utworzyć ustawienie przy użyciu innych metod, takich jak program Apple Configurator lub identyfikator URI OMA.|

## <a name="d"></a>D
|||
|-|-|
|wdrażania|Czynność wysyłania aplikacji lub zasad na zarządzane urządzenie lub do zarządzanego użytkownika.|
|Akcja wdrożenia|Wybór, którego dokonujesz podczas [wdrażania aplikacji](/intune/deploy-use/deploy-apps-in-microsoft-intune). Możesz zdecydować, aby instalacja danej aplikacji była obowiązkowa bądź opcjonalna lub możesz odinstalować tę aplikację.|
|Menedżer rejestracji urządzeń|Organizacje mogą używać usługi Intune do zarządzania dużą liczbą urządzeń przenośnych za pomocą jednego konta użytkownika. Konto [menedżera rejestracji urządzeń](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) jest specjalnym kontem usługi Intune umożliwiającym rejestrację maksymalnie do 1000 urządzeń.|
|Mapowanie grupy urządzeń|Ułatwia [automatyczne dodawanie urządzeń do grup](/intune/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune) na podstawie kategorii urządzenia (np. „Osobiste” lub „Dział sprzedaży”), która może zostać przypisana do urządzenia przez Ciebie lub użytkownika końcowego.|

## <a name="e"></a>E
|||
|-|-|
|Profil e-mail|Za pomocą tych zasad można skonfigurować [ustawienia dostępu do poczty e-mail](/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) dla określonych klientów poczty e-mail na urządzeniach przenośnych, co pozwala zminimalizować liczbę czynności konfiguracyjnych, które musi wykonać użytkownik końcowy.|
|EMS|Rozwiązanie Microsoft Enterprise Mobility + Security (dawniej pakiet Enterprise Mobility Suite) zapewnia ochronę danych firmowych, zezwalając jednocześnie użytkownikom na [dostęp do potrzebnych aplikacji i zawartości](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility).|
|Użytkownik końcowy|[Użytkownicy końcowi urządzeń, takich jak telefony i komputery](/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune) zarządzani za pomocą usługi Intune.|
|Zarejestruj|Usługa Microsoft Intune używa [rejestracji](/intune/deploy-use/enroll-devices-in-microsoft-intune), która umożliwia zarządzanie urządzeniami i zezwala na nich na dostęp do zasobów.|

## <a name="f"></a>F
|||
|-|-|
|FastTrack|[Usługa firmy Microsoft](https://technet.microsoft.com/library/mt228265.aspx) dla użytkowników usługi Intune ze 150 licencjami w uprawniającym planie. W ramach tej usługi specjaliści firmy Microsoft będą współpracować z Tobą, aby ułatwić szybkie i łatwe rozpoczęcie korzystania z usługi Intune.|

## <a name="g"></a>G
|||
|-|-|
|Grupy|Grupy pozwalają [logicznie zbierać razem użytkowników lub urządzenia](/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune). Możesz na przykład utworzyć grupę wszystkich komputerów z systemem Windows. Następnie możesz wdrażać do tych grup aplikacje i zasady.|

## <a name="h"></a>H
|||
|-|-|
|Hybrydowe|Konfiguracja, w ramach której możesz zarządzać urządzeniami zarejestrowanymi w usłudze Intune [za pomocą konsoli programu System Center Configuration Manager](/intune/get-started/integration-with-cloud-services).|

## <a name="i"></a>I
|||
|-|-|
|Konsola administracyjna Intune|Bieżąca konsola, której używasz do wykonywania większości operacji usługi Intune w zakresie zarządzania.|
|Oprogramowanie klienckie usługi Intune|Alternatywny sposób [zarządzania niektórymi komputerami z systemem Windows](/intune/deploy-use/manage-windows-pcs-with-microsoft-intune). Zobacz [Wybieranie metody zarządzania urządzeniami](/intune/get-started/choose-how-to-manage-devices), aby uzyskać pomoc przy wyborze metody.|
|Wydawcy oprogramowania usługi Intune|Narzędzie, za pomocą którego [definiujesz aplikacje, które chcesz wdrożyć, i przekazujesz te aplikacje do magazynu w chmurze](/intune/deploy-use/add-apps).|
|Stan zapasów|Służy do wyświetlania [sprzętu i zainstalowanego oprogramowania](/intune/deploy-use/understand-your-devices-with-inventory-in-microsoft-intune) urządzeń, którymi zarządzasz.|

## <a name="k"></a>K
|||
|-|-|
|Tryb kiosku|Tryb ten pozwala blokować urządzenia. Jest on konfigurowany w ramach [ogólnych zasad konfiguracji](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies). Możesz na przykład skonfigurować urządzenie sieci sprzedaży, aby zezwalać na nim na uruchomienie tylko jednej aplikacji.|

## <a name="m"></a>M
|||
|-|-|
|Managed Browser|[Aplikacja służąca do przeglądania sieci Web](/intune/deploy-use/manage-internet-access-using-managed-browser-policies), którą można wdrożyć w organizacji za pomocą usługi Microsoft Intune. Zasady programu Managed Browser umożliwiają skonfigurowanie listy dozwolonych lub zablokowanych witryn sieci Web ograniczającej zakres witryn, które użytkownicy programu Managed Browser mogą odwiedzać.|
|Zarządzanie aplikacjami mobilnymi|[Zarządzanie aplikacjami mobilnymi (MAM, mobile application management)](/intune/deploy-use/overview-of-app-lifecycle-in-microsoft-intune) pozwala publikować, wypychać, konfigurować, zabezpieczać, monitorować i aktualizować aplikacje mobilne dla użytkowników.
|Zarządzanie urządzeniami przenośnymi|[Zarządzanie urządzeniami przenośnymi (MDM, mobile device management)](/intune/deploy-use/overview-of-device-lifecycle-in-microsoft-intune) pozwala rejestrować urządzenia w usłudze Intune w sposób umożliwiający inicjowanie ich obsługi administracyjnej, konfigurowanie i monitorowanie tych urządzeń oraz wykonywanie na nich akcji.
|Urząd zarządzania urządzeniami przenośnymi|[Urząd MDM](/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune) definiuje usługę zarządzania z uprawnieniami do zarządzania zestawem urządzeń. Opcje przeznaczone dla urzędu zarządzania urządzeniami przenośnymi obejmują samą usługę Intune oraz program Configuration Manager z usługą Intune.|
|Zasady inicjowania obsługi administracyjnej aplikacji mobilnych|Zasady systemu iOS ułatwiające zagwarantowanie, że [profile inicjowania obsługi administracyjnej](/intune/deploy-use/ios-mobile-app-provisioning-profiles) wdrażanych aplikacji systemu iOS nie wygasają.|
|Zasady konfiguracji aplikacji mobilnych|Zasady systemu iOS służące do [określania ustawień dla zgodnych aplikacji systemu iOS](/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune) podczas ich uruchamiania, na przykład do podawania im nazwy firmy lub adresu serwera.|

## <a name="o"></a>O
|||
|-|-|
|Protokół OMA-DM|Zarządzanie urządzeniami Open Mobile Alliance (Open Mobile Alliance Device Management). Będący standardem branżowym protokół zarządzania urządzeniami używany przez wielu producentów sprzętu w celu umożliwienia sterowania funkcjami urządzeń przenośnych i komputerów.|
|Identyfikator URI OMA|Jednolity identyfikator zasobów Open Mobile Alliance (Open Mobile Alliance Uniform Resource Identifier). Identyfikatory te identyfikują poszczególne ustawienia urządzeń zgodne ze standardem OMA-DM. Niektóre z nich można używać w [zasadach niestandardowych usługi Intune](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies), gdy nie ma wbudowanego ustawienia spełniającego określone potrzeby.|

## <a name="p"></a>P
|||
|-|-|
|Zasady|[Pakiet informacji](/intune/deploy-use/microsoft-intune-policy-reference) wysyłany z usługi Intune na urządzenie. Możesz na przykład wdrożyć na urządzeniu ustawienia zabezpieczeń lub informacje dotyczące zgodności urządzenia.|
|Resetowanie kodu dostępu|Funkcja usługi Intune pozwalająca wymuszać na użytkownikach końcowych [resetowanie kodów dostępu](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune) na obsługiwanych urządzeniach.|

## <a name="r"></a>R
|||
|-|-|
|Zdalne blokowanie|Funkcja usługi Intune pozwalająca [blokować obsługiwane urządzenia](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune), nawet jeśli nie masz fizycznego dostępu do urządzenia.|
|Reports|Usługa Intune oferuje wiele różnych [wbudowanych raportów](/intune/deploy-use/understand-microsoft-intune-operations-by-using-reports), które podają informacje o zarządzanych urządzeniach.|
|Wymagana instalacja|Gdy wdrożysz aplikację za pomocą tej akcji, zostanie ona zainstalowana na urządzeniu [bez interwencji użytkownika](/intune/deploy-use/deploy-apps) (w przypadku niektórych platform może być jednak konieczne zaakceptowanie instalacji przez użytkownika końcowego).|
|Wymagania|[Operacja wdrażania aplikacji](/en-us/intune/deploy-use/add-apps) pozwalająca wybrać wymagania, które muszą zostać spełnione na urządzeniu, zanim aplikacja zostanie zainstalowana. Możesz na przykład określić wersję systemu operacyjnego iOS, która musi być zainstalowana, zanim aplikacja zostanie zainstalowana.|

## <a name="s"></a>S
|||
|-|-|
|Selektywne czyszczenie danych|[Selektywne czyszczenie danych](/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune) powoduje usunięcie z urządzenia tylko danych firmowych, w tym danych zarządzania aplikacjami mobilnymi (jeśli ma to zastosowanie), ustawień i profilów poczty e-mail. Selektywne czyszczenie danych nie powoduje usunięcia osobistych danych użytkownika z urządzenia.|
|Subskrypcja|Zawarta umowa, która umożliwia dostęp do dzierżawy usługi Intune.|

## <a name="t"></a>T
|||
|-|-|
|TeamViewer|Aplikacja innej firmy współdziałająca z usługą Intune, aby udostępnić [funkcje pomocy zdalnej](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#request-and-provide-remote-assistance-for-windows-pcs) dla komputerów z systemem Windows zarządzanych za pomocą oprogramowania klienckiego usługi Intune.|
|Dzierżawca|Pojedyncze wystąpienie usługi Intune, do której można uzyskać dostęp dzięki subskrypcji.|
|Warunki i postanowienia|Typ wdrażanych do użytkowników zasad zawierających informacje, które użytkownicy muszą [przeczytać i zaakceptować](/intune/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune), zanim będą mogli za pomocą Portalu firmy zarejestrować swoje urządzenia i uzyskać dostęp do swojej pracy.|

## <a name="v"></a>V
|||
|-|-|
|Aplikacje nabyte w ramach zakupów zbiorczych|Niektóre sklepy z aplikacjami umożliwiają zakup wielu licencji dla aplikacji, które mają być uruchamiane w firmie. Usługa Intune ułatwia zarządzanie aplikacjami [zakupionymi za pośrednictwem takiego programu](/intune/deploy-use/manage-volume-purchased-apps-in-microsoft-intune) przez zaimportowanie informacji o licencji ze sklepu z aplikacjami, śledzenie, ile licencji jest używanych, i zapobieganie instalacji większej liczby kopii aplikacji niż posiadana.|
|Profil sieci VPN|Zasady wdrażające [ustawienia sieci VPN](/intune/deploy-use/vpn-connections-in-microsoft-intune) na urządzeniach, którymi zarządzasz. Zasady te pozwalają zminimalizować wszelkie czynności konfiguracyjne, które muszą wykonywać użytkownicy końcowi.|

## <a name="w"></a>W
|||
|-|-|
|Profil sieci Wi-Fi|Zasady wdrażające [ustawienia sieci bezprzewodowej](/intune/deploy-use/wi-fi-connections-in-microsoft-intune) na urządzenia, aby pozwolić użytkownikom na łączenie się z siecią firmową bez znajomości czy konfigurowania jakichkolwiek ustawień.

