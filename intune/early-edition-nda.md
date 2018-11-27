---
title: Wczesna wersja
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: fbe8cc0fc3e835ee5807dfbe56ea1aa3c728547e
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52184730"
---
# <a name="the-early-edition-for-microsoft-intune---november-2018"></a>Wczesna wersja usługi Microsoft Intune — listopad 2018

> [!Note]
> Powiadomienie dotyczące umowy o zachowaniu poufności: dla usługi Intune opracowywane są następujące zmiany. Te informacje są udostępniane pod rygorem umowy o zachowaniu poufności w bardzo ograniczonym zakresie. Nie wolno publikować żadnych tych informacji w mediach społecznościowych ani w publicznych witrynach internetowych, takich jak Twitter, UserVoice, Reddit itd. 

**Wczesna wersja** zawiera listę funkcji udostępnianych w ramach umowy o zachowaniu poufności, które zostaną wprowadzone w przyszłych wydaniach usługi Microsoft Intune. Te informacje są przekazywane w ograniczonym zakresie i mogą ulec zmianie. Nie publikuj tweetów, wpisów na platformie UserVoice ani w inny sposób nie udostępniaj tych informacji poza swoją firmą. Niektóre funkcje wymienione w tym miejscu mogą nie być wdrożone na czas i zostać opóźnione do przyszłych wersji. Inne funkcje są testowane w wersji pilotażowej, aby zapewnić przygotowanie ich do użytku przez klientów. W przypadku pytań lub wątpliwości skontaktuj się z osobą kontaktową ds. tej grupy produktów firmy Microsoft.

Ta strona jest okresowo aktualizowana. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Usługa Intune w witrynie Azure Portal

<!-- 1811 start -->

### <a name="uninstalling-apps-on-corporate-owned-supervised-ios-devices----1281677---"></a>Odinstalowywanie aplikacji na nadzorowanych urządzeniach z systemem iOS należących do firmy <!-- 1281677 -->
Będzie można usunąć dowolną aplikację na nadzorowanych urządzeniach z systemem iOS należących do firmy. Dowolną aplikację można usunąć, określając jako cel grupę użytkowników lub urządzeń za pomocą typu przypisania **Odinstaluj**. W przypadku osobistych lub nienadzorowanych urządzeń z systemem iOS będzie można w dalszym ciągu usunąć tylko aplikacje zainstalowane przy użyciu usługi Intune.

### <a name="track-installation-of-office-proplus---2620217--"></a>Śledzenie instalacji pakietu Office ProPlus <!--2620217-->
Będzie można śledzić postęp instalacji pakietu [Office ProPlus](apps-add-office365.md) przy użyciu [strony stanu rejestracji](windows-enrollment-status.md).

### <a name="macos-device-enrollment-program-support-for-apple-school-manager-accounts---3006133--"></a>Obsługa programu Device Enrollment Program dla systemu macOS w przypadku kont usługi Apple School Manager <!--3006133-->
Usługa Intune będzie obsługiwać program Device Enrollment Program dla urządzeń z systemem macOS w przypadku kont usługi Apple School Manager.

### <a name="temporarily-pause-kiosk-mode-on-android-devices-to-make-changes----3041935---"></a>Tymczasowe wstrzymanie trybu kiosku na urządzeniach z systemem Android w celu wprowadzenia zmian <!-- 3041935 -->
W przypadku urządzeń z systemem Android pracujących w trybie kiosku z wieloma aplikacjami administrator IT może potrzebować wprowadzić zmiany na urządzeniu. Nowe ustawienie dla kiosku z wieloma aplikacjami pozwoli administratorowi IT na tymczasowe wstrzymanie trybu kiosku za pomocą numeru PIN i uzyskanie dostępu do całego urządzenia.
Aby wyświetlić bieżące ustawienia kiosku, zobacz [Ustawienia kiosku dla systemu Android](android-kiosk-settings.md).

### <a name="set-custom-background-in-managed-home-screen-app-----3041945---"></a>Ustawianie niestandardowego tła w aplikacji Managed Home Screen <!-- 3041945 -->
Dodamy ustawienie, które umożliwia dostosowanie wyglądu tła aplikacji Managed Home Screen na urządzeniach z rozwiązaniem Android Enterprise pracujących w trybie kiosku z wieloma aplikacjami.  Aby skonfigurować **adres URL niestandardowego tła**, przejdź do usługi Intune za pomocą pozycji Konfiguracja urządzenia w witrynie Azure Portal. Wybierz bieżący profil konfiguracji urządzenia lub utwórz nowy profil, aby edytować ustawienia kiosku.

### <a name="enable-virtual-home-button-on-android-enterprise-kiosk-devices-----3042021---"></a>Dostępność wirtualnego przycisku strony głównej na urządzeniach z rozwiązaniem Android Enterprise pracujących w trybie kiosku <!-- 3042021 -->
Nowe ustawienie umożliwi użytkownikom przełączanie się między aplikacją Managed Home Screen a innymi przypisanymi aplikacjami na urządzeniu kiosku z wieloma aplikacjami przez naciśnięcie przycisku programowego. To ustawienie jest szczególnie przydatne w sytuacjach, gdy aplikacja kiosku nie reaguje odpowiednio na przycisk „wstecz”. To ustawienie będzie można skonfigurować dla pojedynczych urządzeń z systemem Android należących do firmy. Aby włączyć lub wyłączyć **wirtualny przycisk strony głównej**, przejdź do usługi Intune za pomocą pozycji Konfiguracja urządzenia w witrynie Azure Portal. Wybierz bieżący profil konfiguracji urządzenia lub utwórz nowy profil, aby edytować ustawienia kiosku.

### <a name="app-protection-policy-assignment-save-and-apply----3104570---"></a>Zapisywanie i stosowanie przypisania zasad ochrony aplikacji <!-- 3104570 -->
Będziesz mieć lepszą kontrolę nad przypisaniami zasad ochrony aplikacji. Po zapisaniu i zastosowaniu przypisań zasad ochrony aplikacji będą one dotyczyć bezpośrednio tylko wybranych użytkowników.

### <a name="new-microsoft-edge-browser-settings-for-windows-10-and-later----3174639---"></a>Nowe ustawienia przeglądarki Microsoft Edge dla systemu Windows 10 i nowszych <!-- 3174639 -->
Zostanie dodane nowe ustawienie ułatwiające kontrolowanie przeglądarki Microsoft Edge na urządzeniach i zarządzanie nią. Aby uzyskać listę bieżących ustawień, zobacz [Ograniczenia urządzeń dla systemu Windows 10 (i nowszych)](device-restrictions-windows-10.md#microsoft-edge-browser).

### <a name="select-apps-tracked-on-the-enrollment-status-page---2531007---"></a>Wybieranie śledzonych aplikacji na stronie stanu rejestracji <!-- 2531007 -->
Będzie można wybrać śledzone aplikacje na stronie stanu rejestracji.

### <a name="intune-app-protection-policies-ui-update----3251427---"></a>Aktualizacja interfejsu użytkownika zasad ochrony aplikacji usługi Intune <!-- 3251427 -->

Zasady ochrony aplikacji usługi Intune pozwalają konfigurować różne ustawienia ochrony danych dla chronionych aplikacji usługi Intune, takich jak Microsoft Outlook i Word. Zmieniamy etykiety ustawień i przycisków, aby ułatwić ich zrozumienie. Kontrolki zostaną zmienione z kontrolek **tak**/**nie** na głównie kontrolki **blokuj**/**zezwalaj** i **wyłącz**/**włącz**, a etykiety zostaną także zaktualizowane, tak aby były bardziej zrozumiałe. Rozmieszczenie ustawień zostanie zmienione, dzięki czemu ustawienie i jego etykieta będą znajdować się obok siebie w kontrolce, umożliwiając lepszą nawigację. Ustawienia domyślne i liczba ustawień pozostaną takie same, lecz ta zmiana pozwoli użytkownikowi lepiej zrozumieć i wykorzystać ustawienia w celu stosowania wybranych zasad ochrony aplikacji, a także łatwiej nawigować po nich.



<!-- 1810 start -->

### <a name="use-microsoft-recommended-settings-with-security-baselines----2055484---"></a>Używanie ustawień zalecanych przez firmę Microsoft z punktami odniesienia zabezpieczeń <!-- 2055484 -->
Usługa Intune umożliwia integrację z innymi usługami koncentrującymi się na zabezpieczeniach, w tym z usługą Windows Defender ATP i usługą Office 365 ATP. Klienci pytają o typową strategię i spójny zestaw kompleksowych przepływów pracy zabezpieczeń w usługach Microsoft 365. Naszym celem jest dopasowanie strategii w celu utworzenia rozwiązań, które łączą operacje zabezpieczeń i typowe zadania administratora. W usłudze Intune staramy się osiągnąć ten cel, publikując zestaw „punktów odniesienia zabezpieczeń” zalecanych przez firmę Microsoft (**Intune** > **Punkty odniesienia zabezpieczeń**).  Administrator będzie mógł tworzyć zasady zabezpieczeń bezpośrednio z tych punktów odniesienia, a następnie wdrożyć je dla użytkowników. Można również dostosować rekomendacje dotyczące najlepszych rozwiązań do potrzeb swojej organizacji. Usługa Intune zapewnia, że urządzenia pozostają w zgodności z tymi punktami odniesienia, i powiadamia administratorów użytkowników lub urządzeń, które nie są zgodne.

### <a name="scope-tags-for-apps---1081941---"></a>Tagi zakresu dla aplikacji <!--1081941 -->
Będzie możliwe tworzenie tagów zakresu w celu ograniczenia dostępu do zasobów usługi Intune. Dodaj tag zakresu do przypisania roli, a następnie dodaj tag zakresu do profilu konfiguracji. Rola będzie miała wtedy dostęp tylko do zasobów z profilami konfiguracji ze zgodnymi tagami zakresu (lub bez tagów zakresu).
Aby utworzyć tag zakresu, wybierz pozycję **Role usługi Intune** > **Zakres (tagi)** > **Utwórz**.
Aby dodać tag zakresu do przypisania roli, wybierz pozycję **Role usługi Intune** > **Wszystkie role** > **Menedżer zasad i profilów** > **Przypisania** > **Zakres (tagi)**.
Aby dodać tag zakresu do profilu konfiguracji, wybierz pozycję **Konfiguracja urządzenia** > **Profile** > wybierz profil > **Właściwości** > **Zakres (tagi)**.

### <a name="tenant-health-dashboard----1124854---"></a>Pulpit nawigacyjny kondycji dzierżawy <!-- 1124854 -->
Na stronie Stan dzierżawy w usłudze Intune znajdziesz informacje o stanie dzierżawy w jednym miejscu. Strona jest podzielona na 4 sekcje:  
- **Szczegóły dzierżawy**: zawiera informacje takie jak urząd zarządzania urządzeniami przenośnymi, suma zarejestrowanych urządzeń w Twojej dzierżawie i liczba licencji. Ta sekcja zawiera także bieżącą wersję usługi dla Twojej dzierżawy.
- **Stan łącznika**: zawiera informacje dla skonfigurowanych łączników, takich jak program VPP firmy Apple, Sklep Windows dla Firm i łączniki certyfikatów. Na podstawie ich bieżącego stanu łączniki są oznaczane flagami *Dobra kondycja*, *Ostrzeżenie* lub *Zła kondycja*.
- **Kondycja usługi Intune**: zawiera aktywne zdarzenia lub awarie dotyczące Twojej dzierżawy. Informacje przedstawione w tej sekcji są pobierane bezpośrednio z Centrum wiadomości usługi Office ([https://portal.office.com](https://portal.office.com)).
- **Wiadomości w usłudze Intune**: zawiera aktywne wiadomości dla dzierżawy obejmujące takie elementy jak powiadomienia o tym, że dzierżawa otrzymała najnowsze funkcje usługi Intune. Informacje przedstawione w tej sekcji są pobierane bezpośrednio z Centrum wiadomości usługi Office ([https://portal.office.com](https://portal.office.com)).


### <a name="deployed-wip-policies-without-user-enrollment----1434452---"></a>Wdrożone zasady funkcji WIP bez rejestracji użytkownika <!-- 1434452 -->
Zasady funkcji Windows Information Protection (WIP) będzie można wdrożyć bez konieczności rejestracji urządzeń z systemem Windows 10 przez użytkowników zarządzania urządzeniami przenośnymi. Ta konfiguracja pozwala firmom na ochronę firmowych dokumentów na podstawie konfiguracji funkcji WIP, jednocześnie umożliwiając użytkownikom zarządzanie własnymi urządzeniami z systemem Windows. Gdy dokumenty są chronione za pomocą zasad funkcji WIP, chronione dane mogą być selektywnie czyszczone przez administratora usługi Intune. Wybierając użytkownika i urządzenie oraz wysyłając żądanie czyszczenia, wszystkie dane chronione za pomocą zasad funkcji WIP staną się bezużyteczne. Z usługi Intune w witrynie Azure Portal wybierz pozycję **Aplikacja mobilna** > **Selektywne czyszczenie aplikacji**.


<!-- 1809 start -->  

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Ustawienia zasad ochrony aplikacji dla danych internetowych <!-- 2662995 -->
Ustawienia zasad ochrony aplikacji dla zawartości internetowej na urządzeniach z systemami Android i iOS zostaną zaktualizowane w celu ulepszenia obsługi linków internetowych http i https, a także przesyłania danych za pośrednictwem linków uniwersalnych systemu iOS i linków między aplikacjami systemu Android.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Token VPP firmy Apple używany przez inne rozwiązanie MDM <!-- 1488946 -->
Usługa Intune wykryje i wyświetli szczegółowe informacje, jeśli token programu VPP (Volume Purchase Program) jest używany zarówno przez usługę Intune, jak i inne rozwiązanie MDM.

### <a name="ios-and-macos-version-numbers-and-build-numbers-are-available-in-compliance-policies----1892471---"></a>Numery wersji oraz numery kompilacji systemów iOS i macOS są dostępne w zasadach zgodności <!-- 1892471 -->
W polu **Zgodność urządzenia** > **Zgodność urządzenia** są wyświetlane wersje systemów operacyjnych iOS oraz macOS i można ich używać w zasadach zgodności. W ramach przyszłej aktualizacji konfigurowalny będzie także numer kompilacji dla obydwu platform.

Po wydaniu aktualizacji zabezpieczeń firma Apple zwykle pozostawia numer wersji bez zmian, lecz aktualizuje numer kompilacji. Na podstawie numeru kompilacji w zasadach zgodności można łatwo sprawdzić, czy została zainstalowana aktualizacja eliminująca luki w zabezpieczeniach.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Wycofane urządzenia na pulpicie nawigacyjnym zgodności urządzeń <!-- 1981119 -->
W ramach przyszłej aktualizacji wycofane urządzenia zostaną usunięte z pulpitu nawigacyjnego zgodności urządzeń. Spowoduje to zmianę liczb dotyczących zgodności.


### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Zmiana w procesie aktualizacji łączników lokalnych <!-- 2277554 -->
Na podstawie opinii klientów zmienimy sposób aktualizacji łączników lokalnych. Po początkowej instalacji łącznika lokalnego aktualizacje będą wykonywane automatycznie. Ta zmiana rozpocznie się od nowego łącznika certyfikatów PFX usługi Microsoft Intune, a następnie będzie wdrażana dla innych typów łączników lokalnych. 

<!-- 1807 start -->

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Sprawdzanie zgodności w programie Configuration Manager <!-- 2192052 -->
Przyszła aktualizacja będzie zawierać nowe ustawienie zgodności programu System Center Configuration Manager (**Zgodność urządzeń** > **Zasady** > **Tworzenie zasad** > **System Windows 10**). Program Configuration Manager wysyła sygnały zgodności do usługi Intune. Przy użyciu ustawienia usługi Intune można wymagać, aby wszystkie sygnały programu Configuration Manager zwracały stan „zgodne”.

Na przykład można wymagać, aby na urządzeniach były zainstalowane wszystkie aktualizacje oprogramowania. W programie Configuration Manager to wymaganie ma stan „Zainstalowano”. Jeśli jakiekolwiek programy na urządzeniu mają nieznany stan, to urządzenie będzie niezgodne w usłudze Intune.

Dotyczy: system Windows 10 lub nowszy

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Alerty dotyczące wygasającego tokenu VPP lub zbyt małej liczby licencji aplikacji Portal firmy <!-- 2237572 -->
Jeśli do wstępnej aprowizacji aplikacji Portal firmy podczas rejestracji programu DEP jest używany token programu Volume Purchase Program (VPP), usługa Intune powiadomi Cię, jeśli token VPP niedługo wygaśnie lub zaczyna brakować licencji aplikacji Portal firmy.



<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Uwagi

Aktualnie nie ma aktywnych powiadomień.

### <a name="see-also"></a>Zobacz też
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).



