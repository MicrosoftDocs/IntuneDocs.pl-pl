---
title: Wczesna wersja
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d6a06326fbb60d910aef0411fc666b82a5f22078
ms.sourcegitcommit: 401cedcd7acc6cb3a6f18d4679bdadb0e0cdf443
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/28/2018
---
# <a name="the-early-edition-for-microsoft-intune---april-2018"></a>Wersja wczesna usługi Microsoft Intune — kwiecień 2018

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

<!-- 1804 start -->




### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Dodatki dla ustawień opcji zabezpieczeń urządzenia lokalnego <!-- 1403702 -->
Będzie można skonfigurować dodatkowe ustawienia opcji zabezpieczeń urządzenia lokalnego dla urządzeń z systemem Windows 10. Dodatkowe ustawienia będą dostępne w następujących obszarach: klient sieci Microsoft, serwer sieci Microsoft, dostęp do sieci i zabezpieczenia oraz logowanie interakcyjne. Te ustawienia można znaleźć w kategorii Endpoint Protection podczas tworzenia zasad konfiguracji urządzeń z systemem Windows 10.

### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>Wymagana instalacja zasad, aplikacji oraz profilów certyfikatów i sieciowych <!-- 1553555 -->
Administratorzy będą mogli zablokować dostęp użytkowników końcowych do pulpitu systemu Windows 10 RS4 do momentu zainstalowania zasad, aplikacji oraz profilów certyfikatów i sieciowych przez usługę Intune podczas aprowizowania urządzeń z rozwiązaniem AutoPilot.

### <a name="rules-for-removing-devices----1609459---"></a>Reguły usuwania urządzeń <!-- 1609459 -->
Będą dostępne nowe reguły umożliwiające automatyczne usuwanie urządzeń, które nie zostały zaewidencjonowane przez ustawioną liczbę dni. Aby wyświetlić nową regułę, przejdź do okienka **Intune**, wybierz pozycję **Urządzenia**, a następnie pozycję **Reguły usuwania urządzeń**.

### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Blokowanie aplikacji i środowisk konsumenckich na urządzeniach z rozwiązaniem AutoPilot w systemie Windows 10 Enterprise RS4<!-- 1621980 -->
Będzie można zablokować instalację aplikacji i środowisk konsumenckich na urządzeniach z systemem Windows 10 Enterprise RS4 i rozwiązaniem AutoPilot. Aby wyświetlić tę funkcję, przejdź do pozycji **Intune** > **Rejestrowanie urządzenia** > **Rejestrowanie systemu Windows** > **Profile AutoPilot systemu Windows** > **Utwórz nowy** > **Ustawienia rejestracji**. 


<!-- 1803 start -->

#### <a name="multiple-exchange-connector-support----2070451---"></a>Obsługa wielu programów Exchange Connector <!-- 2070451 -->

Nie będzie już ograniczenia do jednego programu Microsoft Intune Exchange Connector na dzierżawę. Usługa Intune będzie obsługiwać wiele programów Microsoft Intune Exchange Connector, dzięki czemu możliwe będzie skonfigurowanie dostępu warunkowego w usłudze Intune przy użyciu wielu lokalnych organizacji programu Exchange.

Dzięki lokalnemu łącznikowi programu Exchange w usłudze Intune możesz zarządzać dostępem urządzeń do lokalnych skrzynek pocztowych programu Exchange na podstawie tego, czy urządzenie jest zarejestrowane w usłudze Intune i jest zgodne z zasadami zgodności urządzeń usługi Intune. Aby skonfigurować łącznik, pobierz lokalny łącznik programu Exchange z witryny Azure Portal i zainstaluj go na serwerze w organizacji programu Exchange. Na pulpicie nawigacyjnym usługi Microsoft Intune wybierz pozycję **Dostęp lokalny**, a następnie w obszarze **Konfiguracja** wybierz pozycję **Łącznik Exchange ActiveSync**. Pobierz lokalny łącznik programu Exchange i zainstaluj go na serwerze w organizacji programu Exchange. Ponieważ nie ma już ograniczenia do jednego łącznika programu Exchange na dzierżawę, jeśli masz dodatkowe organizacje programu Exchange, możesz wykonać te same czynności, aby pobrać i zainstalować łącznik dla każdej dodatkowej organizacji programu Exchange.

### <a name="support-coming-for-new-cisco-anyconnect-client-for-ios----1333708---"></a>Nadchodząca obsługa klienta oprogramowania Cisco AnyConnect dla systemu iOS <!-- 1333708 -->

Nowe profile sieci VPN utworzone dla oprogramowania Cisco AnyConnect będą działały z wersją oprogramowania Cisco AnyConnect 4.0.7x i wyższymi. Istniejące profile sieci VPN oprogramowania Cisco AnyConnect dla systemu iOS zostaną oznaczone etykietą **Cisco Legacy AnyConnect** i będą nadal działały z oprogramowaniem AnyConnect 4.0.5x, jak ma to miejsce obecnie.

> [!NOTE]
> Ta zmiana dotyczy tylko systemu iOS; w przypadku systemów Android i macOS oraz programu Android for Work nadal będzie dostępna tylko jedna opcja oprogramowania Cisco AnyConnect.

#### <a name="more-information"></a>Więcej informacji

Aby włączyć obsługę nowej aplikacji, musisz utworzyć nowy profil sieci VPN oprogramowania Cisco AnyConnect dla systemu iOS, ponieważ nowa aplikacja Cisco AnyConnect oraz aplikacja Cisco Legacy AnyConnect to oddzielne aplikacje. Jeśli zarządzasz klientem oprogramowania AnyConnect w danym środowisku, musisz wdrożyć także nową aplikację Cisco AnyConnect. Aby wykonać uaktualnienie musisz także usunąć profil sieci VPN oprogramowania Cisco Legacy AnyConnect oraz aplikację Cisco Legacy AnyConnect.

W początkowym wydaniu integracja kontroli dostępu do sieci (NAC) nie będzie działać w przypadku nowego klienta oprogramowania AnyConnect. Wraz z firmą Cisco pracujemy nad umożliwieniem integracji NAC w przyszłym wydaniu usługi Intune.

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Możliwość wdrożenia wymaganych aplikacji biznesowych (LOB) dla wszystkich użytkowników urządzeń z systemem Windows 10 Desktop <!-- 1627835 RS4 -->
Klienci będą mogli wdrażać wymagane aplikacje biznesowe systemu Windows 10 oraz instalować je w kontekstach urządzeń. Umożliwi to udostępnienie tych aplikacji wszystkim użytkownikom urządzenia. Dotyczy to tylko urządzeń z systemem Windows 10 Desktop.

### <a name="company-portal-enrollment-improved----1874230--"></a>Ulepszona rejestracja za pomocą aplikacji Portal firmy <!-- 1874230-->
Użytkownicy rejestrujący urządzenia za pomocą aplikacji Portal firmy w systemie Windows 10 w wersji 1703 i wyższej będą mogli wykonać pierwszy krok rejestracji bez wychodzenia z aplikacji.

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Aktualizowanie środowiska Pomoc i opinie w aplikacji Portal firmy dla systemu Android <!--1631531 -->

Zaktualizujemy środowisko Pomoc i opinie w aplikacji Portal firmy dla systemu Android, aby było zgodne z najlepszymi rozwiązaniami dla aplikacji systemu Android. W ciągu kilku następnych miesięcy wprowadzimy aktualizację aplikacji Portal firmy dla systemu Android dzielącą element menu **Pomoc i opinie** na oddzielne elementy **Pomoc** i **Prześlij opinię**. Strona **Pomoc** będzie zawierała sekcję **Często zadawane pytania** oraz przycisk **Pomoc techniczna pocztą e-mail**, który umożliwi użytkownikom końcowym przekazanie dzienników firmie Microsoft i wysłanie wiadomości e-mail do pomocy technicznej firmy wraz z opisem problemu. Funkcja **Prześlij opinię** przeprowadzi użytkownika przez standardowy proces przesyłania opinii, podczas którego użytkownik będzie mógł wybrać opcje takie jak „Coś mi się podoba”, „Coś mi się nie podoba”, „Mam pomysł”.


<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Zasady usługi App Protection <!-- 679615 -->
Zasady usługi Intune App Protection umożliwiają tworzenie globalnych, domyślnych zasad, które pozwalają na szybkie włączenie ochrony dla wszystkich użytkowników w całej dzierżawie.

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Witryny internetowe usługi Azure Active Directory mogą wymagać aplikacji Intune Managed Browser i obsługiwać rejestrację jednokrotną w aplikacji Managed Browser (publiczna wersja zapoznawcza) <!-- 710595 -->   
Korzystając z usługi Azure Active Directory (Azure AD), można ograniczyć dostęp do witryn internetowych na urządzeniach przenośnych tylko do aplikacji Intune Managed Browser. W aplikacji Managed Browser dane witryn internetowych będą bezpieczne i odseparowane od osobistych danych użytkowników końcowych. Ponadto w przypadku witryn chronionych przez usługę Azure AD aplikacja Managed Browser będzie obsługiwać funkcje logowania jednokrotnego. Zarejestrowanie się w aplikacji Managed Browser lub korzystanie z aplikacji Managed Browser na urządzeniu z inną aplikacją zarządzaną przez usługę Intune umożliwia aplikacji Managed Browser dostęp do witryn firmowych chronionych przez usługę Azure AD bez konieczności wprowadzania poświadczeń użytkownika. Ta funkcja ma zastosowanie do witryn takich jak Outlook Web Access (OWA) i SharePoint Online, a także innych witryn firmowych, takich jak zasoby intranetowe dostępne za pośrednictwem serwera proxy aplikacji platformy Azure.




## <a name="notices"></a>Uwagi

Aktualnie nie ma aktywnych powiadomień.


### <a name="see-also"></a>Zobacz też
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).


