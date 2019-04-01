---
title: W trakcie opracowywania — Microsoft Intune
titlesuffix: ''
description: Funkcje programu Microsoft Intune w trakcie opracowywania
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/04/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9c377a8558b1f318b4ddad735b6368a291e34516
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57756823"
---
# <a name="in-development-for-microsoft-intune---march-2019"></a>Podczas tworzenia usługi Microsoft Intune — marzec 2019 r

Aby pomóc w swojej gotowości i planowania, ta strona listy aktualizacji interfejsu użytkownika usługi Intune i funkcje są w fazie projektowania, ale nie została jeszcze ogólnie. Ponadto:

- Przewidujemy, należy podjąć działania przed zmianą, opublikujemy bezpłatnych wpis w Centrum wiadomości usługi Office.
- Gdy funkcja jest uruchamiana w środowisku produkcyjnym, albo w wersji zapoznawczej lub ogólnie dostępna, opis funkcji przeniesie wyłączone na tej stronie i na [co to jest nowa strona](whats-new.md).
- Na tej stronie i [co to jest nowa strona](whats-new.md) są okresowo aktualizowane. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.
- Zapoznaj się [plan M365](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) strategiczne cele do zrealizowania i osi czasu.

> [!Note]
> Te elementy odzwierciedlają bieżących oczekiwań firmy Microsoft o możliwościach usługi Intune zostaną dodane w przyszłych wydaniach. Daty i poszczególne funkcje mogą ulec zmianie. Nie wszystkie elementy w rozwoju ma opis funkcji na tej stronie.

**Kanał informacyjny RSS**: otrzymuj powiadomienie, gdy ta strona zostanie zaktualizowana przez skopiowanie i wklejenie następującego adresu URL w czytniku kanałów informacyjnych: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`


<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Usługa Intune w witrynie Azure Portal


<!-- 1903 start-->

### <a name="encryption-report-----2351538---"></a>Raport szyfrowania  <!-- 2351538 -->
Będzie można użyć nowego raportu szyfrowania, aby wyświetlić szczegóły dotyczące stanu szyfrowania urządzenia. Szczegóły dostępne będzie zawierać wersja modułu TPM urządzenia, szyfrowanie gotowości i stan, raportowanie błędów i więcej.  

### <a name="access-bitlocker-recovery-keys-from-the-intune-portal-----2351547----"></a>Dostęp do kluczy odzyskiwania funkcji BitLocker z portalu usługi Intune  <!-- 2351547  -->
Dodajemy nowy punkt wejścia na urządzeniach, w którym można wyświetlić szczegółowe informacje z usługi Azure Active Directory (AAD) o identyfikator klucza funkcji BitLocker i klucze odzyskiwania funkcji BitLocker.

### <a name="scope-tags-for-app-configuration-policies---2371891---"></a>Tagi zakresu dla zasad konfiguracji aplikacji <!--2371891 -->
Będzie można dodać tag zakresu zasad konfiguracji aplikacji, tak, aby tylko osoby z rolami również przypisany ten tag zakresu mają dostęp do zasad konfiguracji aplikacji. Można tylko przeznaczone dla zasad konfiguracji aplikacji lub skojarzone z aplikacje przypisane do tego samego tagu zakresu.

### <a name="assign-autopilot-profiles-to-the-all-devices-virtual-group---2715522---"></a>Przypisywanie profilów rozwiązania Autopilot do wirtualnej grupy Wszystkie urządzenia <!--2715522 -->
Będzie można przypisać profile rozwiązania Autopilot do wirtualnej grupy wszystkich urządzeń. Aby to zrobić, wybierz pozycję **Rejestrowanie urządzeń** > **Rejestracja w systemie Windows** > **Profile wdrażania** > wybierz profil > **Przypisania** > w obszarze **Przypisz do** wybierz pozycję **Wszystkie urządzenia**. Aby uzyskać więcej informacji na temat profilów rozwiązania Autopilot, zobacz [Rejestrowanie urządzeń z systemem Windows przy użyciu rozwiązania Windows Autopilot](enrollment-autopilot.md).

### <a name="install-available-apps-using-the-company-portal-app-after-windows-bulk-enrollment----2751523----"></a>Instalowanie dostępnych aplikacji przy użyciu aplikacji Portal firmy po rejestracja zbiorcza Windows <!-- 2751523  -->
Urządzenia Windows, które są zarejestrowane w usłudze Intune przy użyciu [rejestracji zbiorczej Windows](windows-bulk-enroll.md) (udostępnianie pakietów) będą mogli Instalowanie dostępnych aplikacji przy użyciu aplikacji Portal firmy. Aby uzyskać więcej informacji na temat aplikacji Portal firmy, zobacz [ręcznie dodać Portal firmy systemu Windows 10](store-apps-company-portal-app.md) i [jak skonfigurować aplikację Portal firmy usługi Microsoft Intune](company-portal-app.md).

### <a name="scope-tags-for-ios-app-provisioning-profiles---2934430---"></a>Tagi zakresu dla profilów aprowizacji aplikacji dla systemu iOS <!--2934430 -->
Będzie można dodać tag zakresu do profilu aprowizacji aplikacji systemu iOS, aby tylko osoby z rolami również przypisany ten tag zakresu mają dostęp do profilu aprowizacji aplikacji dla systemu iOS. 

### <a name="office-deployment-tool-odt-xml-for-office-proplus-deployment----3192477----"></a>Narzędzie wdrażania Office (ODT) XML wdrażania pakietu Office ProPlus <!-- 3192477  -->
Będzie można udostępnić narzędzia wdrażania pakietu Office (ODT) XML, podczas tworzenia wystąpienia Office Pro Plus w konsoli administracyjnej usługi Intune. Dzięki temu będzie większa dostosowywalności istniejące opcje interfejsu użytkownika usługi Intune nie odpowiadają Twoim potrzebom. 

###  <a name="block-users-from-scanning-for-windows-updates-------3316758------"></a>Zablokuj użytkownikom możliwość skanowania w poszukiwaniu aktualizacji Windows    <!-- 3316758    -->
Dodajemy nowy Windows pierścień aktualizacji ustawień, których można używać, będzie Zablokuj użytkownikom możliwość skanowania w poszukiwaniu aktualizacji Windows. To ustawienie nie będzie dostępny z poziomu portalu, ale można skonfigurować przy użyciu interfejsu API programu Graph usługi Intune.

### <a name="windows-update-notifications-----3316782---"></a>Powiadomienia o aktualizacji Windows  <!-- 3316782 -->
Dodajemy obsługę konfiguracje pierścienia aktualizacji Windows, dzięki czemu będzie można skonfigurować powiadomienia Windows Update, które są widoczne dla użytkowników. To ustawienie nie będzie dostępny z poziomu portalu, ale można skonfigurować przy użyciu interfejsu API programu Graph usługi Intune.

### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users---3448635---"></a>Zmiany do rejestracji w aplikacji Portal firmy dla użytkowników urządzeń z systemem iOS 12 <!--3448635 -->  
Portal firmy dla systemu iOS zostanie zaktualizowany w ekrany rejestracji i kroki, aby wyrównać ze zmianami rejestracji MDM ogólnie dostępnych w systemie iOS firmy Apple 12.2. Zaktualizowano przepływ pracy będzie monitować użytkowników o:

- Zezwalaj na Safari do otwierania witryny internetowej Portal firmy (za pośrednictwem przeglądarki Safari) i Pobierz profil zarządzania przed powrotem do aplikacji Portal firmy. 
- Otwórz aplikację ustawienia w celu zainstalowania profilu zarządzania na urządzeniu.
- Wróć do aplikacji Portal firmy w celu ukończenia procesu rejestrowania.  

Aby uzyskać więcej informacji na temat jak można przygotować pod kątem tych zmian, zobacz [wpis społeczności technicznej firmy Microsoft](https://techcommunity.microsoft.com/). W międzyczasie, aby zapewnić obsługę systemu iOS na nowe rejestracje w aplikacji Portal firmy, Zaktualizowaliśmy kroki opisane w [rejestrowanie urządzenia z systemem iOS w usłudze Intune](https://docs.microsoft.com/en-us/intune/ios-enroll). Zmiany te dokumenty będą na żywo, po Apple wersje systemu iOS w wersji 12.2. 

### <a name="support-for-additional-connectors-on-the-tenant-status-page----3617202-------"></a>Obsługa dodatkowych łączników na stronie stanu dzierżawy <!-- 3617202     -->
Na stronie stanu dzierżawy będą wyświetlane informacje o dodatkowe łączniki, w tym stanie *zaawansowanej ochrony przed zagrożeniami programu Windows Defender* (ATP) i inne łączniki Mobile Threat Defense.

### <a name="granting-intune-read-only-access-to-some-azure-active-directory-roles----3637917---"></a>Udzielanie Intune przeczytaj dostęp tylko do niektórych ról usługi Azure Active Directory <!-- 3637917 -->
Firma Microsoft będzie udzielanie, read usługi Intune na dostęp tylko do następujących ról w usłudze Azure AD. Uprawnienia przyznane przy użyciu ról usługi Azure AD zastępują uprawnienia przyznane przy użyciu kontroli dostępu opartej na rolach usługi Intune (RBAC).

Przeczytaj tylko dostęp do danych inspekcji w usłudze Intune:

- Administrator zgodności
- Administrator do spraw zgodności danych

Przeczytaj tylko dostęp do wszystkich danych w usłudze Intune:

- Administrator zabezpieczeń
- Podmiot zabezpieczeń
- Czytelnik zabezpieczeń
- Czytnik globalne

### <a name="easier-access-to-diagnostic-settings------3804627-----"></a>Ułatwienia dostępu do ustawień diagnostycznych   <!-- 3804627   -->
Dodajemy nową opcję **dzienniki inspekcji** bloku w każdym w każdym obciążeniu dziennika inspekcji, w konsoli usługi Intune, które można użyć, aby otworzyć bezpośrednio *ustawień diagnostycznych* strony.

### <a name="create-and-use-device-configuration-profiles-on-android-zebra-devices-in-intune----3895244----"></a>Tworzenie i używanie profilów konfiguracji urządzeń na urządzeniach z systemem Android zebry w usłudze Intune <!-- 3895244  -->
Usługa Intune będzie obsługiwać konfigurowanie urządzeń dla systemu Android zebry. Ściślej mówiąc będziesz mieć możliwość: 

- Tworzenie profilu konfiguracji urządzenia, a następnie Zastosuj ustawienia do urządzeń dla systemu Android zebry przy użyciu profilów mobilności rozszerzenia (MX) generowany przez StageNow (**konfiguracji urządzenia** > **profile**  >  **Utwórz profil** > **Android** platformy).

Dotyczy:  
- Android

<!-- 1901 start -->

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----1672660----"></a>Wdrażanie aplikacji ze sklepu Microsoft Store dla Firm licencjonowanych w trybie online <!-- 1672660  -->
Będzie możliwe przypisywanie w kontekście urządzenia wymaganych, licencjonowanych w trybie online aplikacji ze sklepu Microsoft Store dla Firm. Wdrożona w ten sposób aplikacja ze sklepu Microsoft Store dla Firm będzie mogła być zainstalowana dla wszystkich użytkowników urządzenia. Dotyczy to tylko urządzeń stacjonarnych z systemem Windows 10 w wersji RS4 lub nowszej. Możliwość instalacji w kontekście urządzenia jest dostępna na stronie przypisywania aplikacji klienckich dla aplikacji MSFB licencjonowanych w trybie online.

## <a name="notices"></a>Uwagi

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).
