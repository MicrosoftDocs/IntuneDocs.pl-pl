---
title: W trakcie opracowywania — Microsoft Intune
titleSuffix: ''
description: Funkcje usługi Microsoft Intune w trakcie opracowywania
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/29/2019
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
ms.openlocfilehash: 7bba992c79f69a126f0199d9cdac52779910ff38
ms.sourcegitcommit: 068c4e4bc6e6d778ece4a83d000128c4d2b732db
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 04/29/2019
ms.locfileid: "64910325"
---
# <a name="in-development-for-microsoft-intune---may-2019"></a>Funkcje usługi Microsoft Intune w trakcie opracowywania — maj 2019 r.

Aby ułatwić Ci planowanie, na tej stronie udostępniamy listę aktualizacji interfejsu użytkownika i funkcji usługi Intune, które są obecnie opracowywane, a zostaną wydane w przyszłości. Ponadto:

- Jeśli przewidujemy, że przed wprowadzeniem zmiany będzie konieczne wykonanie określonych działań, opublikujemy również dodatkowy wpis w Centrum wiadomości usługi Office.
- Po wprowadzeniu funkcji w środowisku produkcyjnym — w wersji zapoznawczej lub ogólnie dostępnej — opis tej funkcji zostanie przeniesiony z tej strony na stronę [Co nowego](whats-new.md).
- Ta strona oraz strona [Co nowego](whats-new.md) są okresowo aktualizowane. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.
- Zobacz [harmonogram działania dla platformy M365](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS), aby poznać strategiczne cele i terminy.

> [!Note]
> Te elementy odzwierciedlają aktualne plany firmy Microsoft dotyczące funkcji usługi Intune, które zostaną wprowadzone w przyszłych wydaniach. Zarówno daty, jak i poszczególne funkcje mogą ulec zmianie. Nie wszystkie elementy będące w trakcie opracowywania zostały opisane na tej stronie.

**Kanał informacyjny RSS**: otrzymuj powiadomienie, gdy ta strona zostanie zaktualizowana przez skopiowanie i wklejenie następującego adresu URL w czytniku kanałów informacyjnych: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Usługa Intune w witrynie Azure Portal


<!-- 1905 start-->


### <a name="deleting-a-device-in-the-apple-portal-will-be-reflected-in-the-intune-portal---2489996---"></a>Usunięcie urządzenia w portalu firmy Apple zostanie odzwierciedlone w portalu usługi Intune <!--2489996 -->
Jeśli urządzenie zostanie usunięte z portalu usługi Device Enrollment Program firmy Apple lub portalu Apple Business Manager, to zostanie też automatycznie usunięte z usługi Intune podczas następnej synchronizacji.

### <a name="baseline-support-for-keyword-search-----3082036-----------"></a>Obsługa wyszukiwania punktów odniesienia według słów kluczowych  <!-- 3082036         -->
Podczas tworzenia lub edytowania profilu punktów odniesienia zabezpieczeń wkrótce będzie można używać *wyszukiwania* do filtrowania ustawień wyświetlanych w konsoli.   

### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api----3295288---"></a>Zbiorcze resetowanie i czyszczenie urządzeń za pomocą interfejsu API programu Graph <!-- 3295288 -->
Za pomocą interfejsu API programu Graph będzie można zbiorczo resetować i czyścić do 100 urządzeń.

### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>Sprawdzanie mikroukładu modułu TPM w zasadach zgodności urządzeń z systemem Windows 10 <!-- 3617671 -->
Wiele urządzeń z systemem Windows 10 lub nowszym zawiera mikroukład modułu TPM (Trusted Platform Module). Ta aktualizacja obejmuje nowe ustawienie zgodności, które sprawdza wersję mikroukładu modułu TPM na urządzeniu. 

To ustawienie jest opisane w artykule [Ustawienia zasad zgodności urządzeń z systemem Windows 10 lub nowszym](compliance-policy-create-windows.md#device-security).

Dotyczy: system Windows 10 lub nowszy

### <a name="intune-management-extension-powershell-scripts-----3734186------"></a>Skrypty programu PowerShell rozszerzające zarządzanie w ramach usługi Intune  <!-- 3734186    -->
Skrypty programu PowerShell będzie można skonfigurować do uruchamiania z uprawnieniami administratora na urządzeniu. Aby uzyskać więcej informacji, zobacz [Używanie skryptów programu PowerShell na urządzeniach z systemem Windows 10 w usłudze Intune](intune-management-extension.md).

### <a name="prevent-end-users-from-modifying-their-personal-hotspot-and-disable-siri-server-logging-on-ios-supervised-devices----4097904----"></a>Uniemożliwianie użytkownikom końcowym modyfikowania ich osobistego hotspotu i wyłączenia rejestrowania serwera Siri na nadzorowanych urządzeniach z systemem iOS <!-- 4097904  --> 
Dla urządzenia z systemem iOS można utworzyć profil ograniczeń urządzenia (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > **iOS** dla platformy > **Ograniczenia urządzenia** dla typu profilu). Ta aktualizacja obejmuje nowe ustawienia, które można skonfigurować:

- Osobisty hotspot
- Rejestrowanie serwera Siri

Aby zobaczyć bieżące ustawienia, przejdź do artykułu [Ustawienia urządzeń z systemem iOS umożliwiające działanie funkcji lub ich ograniczanie](device-restrictions-ios.md). 

Dotyczy: system iOS 12.2 i nowsze

### <a name="new-classroom-app-device-restriction-settings-for-dep-enrolled-macos-devices----4097905----"></a>Nowe ustawienia ograniczeń urządzeń w aplikacji Klasa dotyczące urządzeń z systemem macOS zarejestrowanych w usłudze DEP <!-- 4097905  --> 
Na urządzeniach z systemem macOS można utworzyć profile konfiguracji urządzenia (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > **macOS** dla platformy > **Ograniczenia urządzenia** dla typu profilu). Ta aktualizacja obejmuje nowe ustawienia aplikacji Klasa dla urządzeń zarejestrowanych w usłudze DEP oraz opcję wyłączenia biblioteki zdjęć iCloud.

Aby zobaczyć bieżące ustawienia, przejdź do artykułu [Ustawienia urządzeń z systemem macOS umożliwiające działanie funkcji lub ich ograniczanie przy użyciu usługi Intune](device-restrictions-macos.md).

Dotyczy: system macOS 10.14.4 i nowsze

### <a name="android-enterprise-app-management----4459905-idready---"></a>Zarządzanie aplikacjami w usłudze Android Enterprise <!-- 4459905 idready -->
Aby ułatwić administratorom IT konfigurowanie i używanie zarządzania w usłudze Android Enterprise, cztery typowe aplikacje związane z usługą Android Enterprise zostaną automatycznie dodane do konsoli administracyjnej usługi Intune. Są to następujące cztery aplikacje w usłudze Android Enterprise:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)**  — używana w scenariuszach w pełni zarządzanych za pomocą Android Enterprise.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)**  — pomaga zalogować się do kont w przypadku używania weryfikacji dwuskładnikowej.
- **[Intune — Portal firmy](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)**  — używana w przypadku scenariuszy obejmujących zasady ochrony aplikacji i profil służbowy Android Enterprise.
- [Zarządzany ekran główny](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise) — używana w scenariuszach z użyciem Android Enterprise dla urządzeń dedykowanych/działających w trybie kiosku.

Wcześniej administratorzy IT musieli ręcznie znajdować i zatwierdzać te aplikacje w [zarządzanym sklepie Google Play](https://play.google.com/store/apps) w ramach procesu konfigurowania. Ta zmiana eliminuje te wcześniej wykonywane ręcznie kroki, aby klienci mogli łatwiej i szybciej zacząć korzystać z zarządzania w ramach usługi Android Enterprise.

Administratorzy zobaczą te cztery aplikacje automatycznie dodane do listy aplikacji usługi Intune podczas pierwszego połączenia swojego dzierżawcy usługi Intune z zarządzanym sklepem Google Play. Aby uzyskać więcej informacji, zobacz [Łączenie konta usługi Intune z kontem zarządzanego sklepu Google Play](connect-intune-android-enterprise.md). W przypadku dzierżawców, dla których już nawiązano połączenie lub rozpoczęto korzystanie z usługi Android Enterprise, administratorzy nie muszą nic robić. Te cztery aplikacje automatycznie staną się widoczne w ciągu 7 dni od ukończenia wdrożenia usługi w maju 2019 r.

<!-- 1904 start-->

### <a name="advanced-settings-for-windows-defender-firewall----1311949---"></a>Zaawansowane ustawienia zapory Windows Defender <!-- 1311949 -->
Wkrótce będzie można zarządzać niestandardowymi regułami zapory usługi Windows Defender na komputerach klienckich za pomocą usługi Intune. Reguły te mogą określać zachowanie dotyczące ruchu przychodzącego i wychodzącego na poziomie aplikacji, adresów sieciowych i portów. 


### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Użytkownicy urządzeń mogą wyświetlać wszystkie zarządzane aplikacje, które zainstalowali lub próbowali zainstalować <!-- 2352913 -->
W aplikacji Portal firmy dla systemu Windows będzie dostępna lista wszystkich zarządzanych aplikacji (zarówno wymaganych, jak i dostępnych), które zainstalowano na urządzeniu użytkownika. Użytkownicy będą mogli wyświetlać aplikacje, które próbowano zainstalować lub które oczekują na instalację, wraz z bieżącym stanem. Jeśli organizacja nie określa aplikacji jako wymagane lub dostępne, użytkownicy zobaczą komunikat z informacją, że nie zainstalowano żadnych aplikacji firmowych. Użytkownicy będą również mogli sortować lub filtrować swoje aplikacje według stanu instalacji.

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Używanie „reguł stosowania” podczas tworzenia profili konfiguracji urządzeń z systemem Windows 10 <!-- 2549910 -->
Obecnie możesz tworzyć profile konfiguracji urządzeń z systemem Windows 10 (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > **Windows 10** jako platforma). W przyszłości będzie możliwe również tworzenie **reguł stosowania**, aby profil był stosowany tylko do określonej edycji lub wersji. Możesz na przykład utworzyć profil włączający określone ustawienia funkcji BitLocker. Gdy dodasz ten profil, reguła stosowania umożliwi zastosowanie go tylko do urządzeń z systemem Windows 10 Enterprise.

Dotyczy: 
- System Windows 10 lub nowszy

###  <a name="intune-security-tasks-for-defender-atp-in-public-preview----3208597---"></a>Zadania zabezpieczeń usługi Intune dotyczące zaawansowanej ochrony przed zagrożeniami usługi Defender (w publicznej wersji zapoznawczej) <!-- 3208597 -->
Wkrótce w usłudze Intune zostanie udostępniona publiczna wersja zapoznawcza zadań zabezpieczeń związanych z nowo przedstawioną funkcją zarządzania zagrożeniami i lukami w zabezpieczeniach usługi Microsoft Defender.  Dzięki tej integracji administratorzy zabezpieczeń zaawansowanej ochrony przed zagrożeniami w usłudze Windows Defender będą mogli bardziej efektywnie informować administratorów usługi Intune o zalecanych środkach zaradczych w odniesieniu do pojawiających się zagrożeń. Dodanie tych zadań zabezpieczeń umożliwia zastosowanie opartego na ryzyku podejścia do wykrywania, określania priorytetów i korygowania luk w zabezpieczeniach i błędów w konfiguracji punktów końcowych.

Aby dowiedzieć się więcej na temat zadań zabezpieczeń w usłudze Intune, zobacz wpis w blogu dotyczący [rozszerzania funkcji zarządzania zagrożeniami i lukami w zabezpieczeniach w ramach zaawansowanej ochrony przed zagrożeniami w usłudze Microsoft Defender za pomocą zadań zabezpieczeń w usłudze Intune](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Microsoft-Intune-security-tasks-extend-Microsoft-Defender-ATP-s/ba-p/369857). 

### <a name="windows-defender-advanced-threat-protection-baseline----3754134---"></a>Punkt odniesienia dla zaawansowanej ochrony przed zagrożeniami w usłudze Windows Defender <!-- 3754134 -->
Planujemy dodać nowy punkt odniesienia ułatwiający konfigurowanie ustawień zaawansowanej ochrony przed zagrożeniami w usłudze Windows Defender.



## <a name="notices"></a>Uwagi

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).


