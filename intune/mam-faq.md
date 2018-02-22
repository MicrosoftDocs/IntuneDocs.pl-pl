---
title: "Często zadawane pytania dotyczące zarządzania aplikacjami mobilnymi (MAM) i ochrony aplikacji"
description: "Ten artykuł zawiera odpowiedzi na niektóre często zadawane pytania dotyczące zarządzania aplikacjami mobilnymi (MAM) usługi Intune i ochrony jej aplikacji."
keywords: 
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 02/06/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 149def73-9d08-494b-97b7-4ba1572f0623
ms.reviewer: erikre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 23ab21e21ff2ffd471523f8132acffd7545358f0
ms.sourcegitcommit: 9bd6278d129fa29f184b2d850138f8f65f3674ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/09/2018
---
# <a name="frequently-asked-questions-about-mam-and-app-protection"></a>Często zadawane pytania dotyczące zarządzania aplikacjami mobilnymi (MAM) i ochrony aplikacji

Ten artykuł zawiera odpowiedzi na niektóre często zadawane pytania dotyczące zarządzania aplikacjami mobilnymi (MAM) usługi Intune i ochrony aplikacji usługi Intune.

## <a name="mam-basics"></a>Zarządzanie aplikacjami mobilnymi — podstawowe informacje


**Co to jest MAM?** [Zarządzanie aplikacjami mobilnymi (MAM) usługi Intune](/intune/app-lifecycle) obejmuje zestaw funkcji zarządzania usługi Intune, które umożliwiają publikowanie, wypychanie, konfigurowanie, zabezpieczanie, monitorowanie i aktualizowanie aplikacji mobilnych dla użytkowników.

**Jakie są zalety ochrony aplikacji MAM?** Zarządzanie aplikacjami mobilnymi pozwala chronić dane organizacji w obrębie aplikacji. MAM bez rejestracji (MAM-WE) umożliwia zarządzanie aplikacją służbową, która zawiera dane poufne, z prawie każdego urządzenia — w tym z urządzenia osobistego w scenariuszach BYOD (przynieś własne urządzenie). Zarządzanie aplikacjami mobilnymi usługi Intune można stosować do wielu aplikacji użytkowych, takich jak aplikacje pakietu Microsoft Office. Zobacz oficjalną listę [aplikacji zarządzanych przez usługę Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) dostępnych do użytku publicznego.

**Jakie konfiguracje urządzeń obsługuje zarządzanie aplikacjami mobilnymi?** Zarządzanie aplikacjami mobilnymi usługi Intune obsługuje dwie konfiguracje:
- **Intune MDM + MAM**: administratorzy IT mogą zarządzać aplikacjami korzystającymi z zasad zarządzania aplikacjami mobilnymi i ochrony aplikacji tylko na urządzeniach zarejestrowanych w usłudze zarządzania urządzeniami mobilnymi (MDM) usługi Intune. Aby zarządzać aplikacjami przy użyciu konfiguracji MDM + MAM, klienci powinni używać konsoli usługi Intune w portalu Azure pod adresem https://portal.azure.com.

- **MAM bez rejestracji urządzeń**: Zarządzanie aplikacjami mobilnymi bez rejestracji urządzeń (MAM-WE) umożliwia administratorom IT zarządzanie aplikacjami za pomocą zasad zarządzania aplikacjami mobilnymi i ochrony aplikacji na urządzeniach, które nie zostały zarejestrowane w usłudze Intune MDM. Oznacza to, że aplikacjami można zarządzać przy użyciu usługi Intune na urządzeniach zarejestrowanych u dostawców EMM innych firm. Aby zarządzać aplikacjami przy użyciu konfiguracji MAM-WE, klienci powinni używać konsoli usługi Intune w portalu Azure, korzystając z adresu http://portal.azure.com. Aplikacjami można również zarządzać przy użyciu usługi Intune na urządzeniach zarejestrowanych u dostawców usługi Enterprise Mobility Management (EMM) innych firm lub w ogóle niezarejestrowanych w usłudze MDM.


## <a name="app-protection-policies"></a>Zasady ochrony aplikacji

**Co to są zasady ochrony aplikacji**? Zasady ochrony aplikacji to reguły, które mogą zagwarantować, że dane organizacji pozostaną bezpieczne lub nie zostaną pobrane z zarządzanej aplikacji. Zasady mogą być regułą, która jest wymuszana w przypadku próby uzyskania dostępu do danych firmowych lub ich przeniesienia przez użytkownika albo zestawem akcji, które są zabronione lub monitorowane, gdy użytkownik korzysta z aplikacji.

**Jakie są przykłady zasad ochrony aplikacji?** Zobacz tematy [Android app protection policy settings](app-protection-policy-settings-android.md) (Ustawienia zasad ochrony aplikacji systemu Android) i [iOS app protection policy settings](app-protection-policy-settings-ios.md) (Ustawienia zasad ochrony aplikacji systemu iOS), aby uzyskać szczegółowe informacje dotyczące poszczególnych ustawień zasad ochrony aplikacji.

## <a name="apps-you-can-manage-with-app-protection-policies"></a>Aplikacje, którymi można zarządzać za pomocą zasad ochrony aplikacji

**Którymi aplikacjami można zarządzać przy użyciu zasad ochrony aplikacji?** Każdą aplikacją zintegrowaną z zestawem [Intune App SDK](/intune/app-sdk) lub opakowaną za pomocą [Narzędzia opakowującego aplikacje usługi Intune](/intune/apps-prepare-mobile-application-management) można zarządzać przy użyciu zasad ochrony aplikacji usługi Intune. Zobacz oficjalną listę [aplikacji zarządzanych przez usługę Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) dostępnych do użytku publicznego.

**Jakie są podstawowe wymagania dotyczące użycia zasad ochrony aplikacji w aplikacji zarządzanej przez usługę Intune?**
- Użytkownik końcowy musi mieć konto usługi Azure Active Directory (AAD). Zobacz temat [Dodawanie użytkowników i przyznawanie uprawnień administracyjnych do usługi Intune](/intune/users-permissions-add), aby dowiedzieć się, jak utworzyć użytkowników usługi Intune w usłudze Azure Active Directory.

- Użytkownik końcowy musi mieć licencję usługi Microsoft Intune przypisaną do swojego konta usługi Azure Active Directory. Zobacz temat [Zarządzanie licencjami usługi Intune](/intune/licenses-assign), aby dowiedzieć się, jak przypisać licencje usługi Intune użytkownikom końcowym.

- Użytkownik końcowy musi należeć do grupy zabezpieczeń objętej zasadami ochrony aplikacji. Te same zasady ochrony aplikacji muszą obejmować określoną używaną aplikację. Zasady ochrony aplikacji można tworzyć i wdrażać w konsoli usługi Intune w [portalu Azure](http://portal.azure.com). Grupy zabezpieczeń można obecnie tworzyć w [portalu Office](http://portal.office.com).

- Użytkownik końcowy musi zalogować się do aplikacji przy użyciu konta usługi AAD.

**Jakie są dodatkowe wymagania dotyczące korzystania z [aplikacji mobilnej Outlook](https://products.office.com/outlook)?**

- Użytkownik końcowy musi mieć na urządzeniu aplikację mobilną Outlook.

- Użytkownik końcowy musi mieć skrzynkę pocztową usługi [Office 365 Exchange Online](https://products.office.com/exchange/exchange-online) oraz licencję powiązaną z kontem usługi Azure Active Directory.

  >[!NOTE]
  > Aplikacja mobilna Outlook obsługuje obecnie tylko usługę Microsoft Exchange Online i nie obsługuje lokalnej instalacji programu Exchange ani usługi Exchange dedykowanej dla usługi Office 365.

**Jakie są dodatkowe wymagania dotyczące korzystania z aplikacji [Word, Excel i PowerPoint](https://products.office.com/business/office)?**

- Użytkownik końcowy musi mieć licencję usługi [Office 365 Business lub Enterprise](https://products.office.com/business/compare-more-office-365-for-business-plans) przypisaną do swojego konta usługi Azure Active Directory. Subskrypcja musi obejmować aplikacje pakietu Office na urządzeniach przenośnych i może uwzględniać konto magazynu w chmurze w ramach usługi [OneDrive dla Firm](https://onedrive.live.com/about/business/). Licencje usługi Office 365 można przypisać w [portalu Office](http://portal.office.com), wykonując poniższe [instrukcje](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

- Użytkownik końcowy musi mieć zarządzaną lokalizację skonfigurowaną przy użyciu funkcji szczegółowego zapisywania jako — w ramach ustawienia „Nie zezwalaj na używanie polecenia Zapisz jako” w zasadach ochrony aplikacji. Przykładowo — jeśli zarządzana lokalizacja to OneDrive, aplikację [OneDrive](https://onedrive.live.com/about/) należy skonfigurować w aplikacji Word, Excel lub PowerPoint użytkownika końcowego.

- Jeśli zarządzana lokalizacja to OneDrive, aplikacja musi być objęta zasadami ochrony aplikacji wdrożonymi dla użytkownika końcowego.

  >[!NOTE]
  > Aplikacje mobilne pakietu Office obsługują obecnie tylko usługę SharePoint Online, a nie lokalny program SharePoint.

**Dlaczego w pakiecie Office jest wymagana zarządzana lokalizacja (np. OneDrive)?** Usługa Intune oznacza wszystkie dane w aplikacji jako „firmowe” lub „osobiste”. Dane są uznawane za „firmowe”, jeśli pochodzą z lokalizacji firmowej. W przypadku aplikacji pakietu Office usługa Intune uznaje za lokalizacje firmowe: adres e-mail (Exchange) lub magazyn w chmurze (aplikacja OneDrive z kontem usługi OneDrive dla Firm).

**Jakie są dodatkowe wymagania dotyczące korzystania z usługi Skype dla firm?** Zobacz wymagania licencyjne usługi [Skype dla firm](https://products.office.com/skype-for-business/it-pros).
  >[!NOTE]
  > Aplikacja mobilna Skype dla firm obsługuje obecnie tylko usługę Skype dla firm Online.

## <a name="app-protection-features"></a>Funkcje ochrony aplikacji

**Co to jest obsługa wielu tożsamości?** Obsługa wielu tożsamości polega na tym, że zestaw SDK aplikacji usługi Intune może przypisywać zasady ochrony aplikacji tylko do konta służbowego zarejestrowanego w aplikacji. Jeśli w aplikacji zostanie zarejestrowane konto osobiste , dane pozostaną bez zmian.

**Jaki jest cel obsługi wielu tożsamości?** Dzięki obsłudze wielu tożsamości zarówno aplikacje dla odbiorców „firmowych”, jak i konsumentów (tj. aplikacje pakietu Office) mogą być wprowadzane na rynek z funkcjami ochrony aplikacji usługi Intune dla kont „firmowych”.

**Jak wygląda obsługa wielu tożsamości w programie Outlook?** Ze względu na to, że w programie Outlook widok osobistych i „firmowych” wiadomości e-mail jest połączony, aplikacja Outlook monituje o numer PIN usługi Intune podczas uruchamiania.

**Co to jest numer PIN aplikacji usługi Intune?** Osobisty numer identyfikacyjny (PIN) jest kodem dostępu służącym do weryfikacji, czy właściwy użytkownik uzyskuje dostęp do danych organizacji w aplikacji.

- **Kiedy jest wyświetlany monit o wprowadzenie numeru PIN?** Monit o podanie numeru PIN aplikacji użytkownika jest wyświetlany w usłudze Intune tylko wtedy, gdy użytkownik chce uzyskać dostęp do danych „firmowych”. W aplikacjach z obsługą wielu tożsamości, np. Word, Excel lub PowerPoint, monit o wprowadzenie numeru PIN jest wyświetlany, gdy użytkownik próbuje otworzyć dokument lub plik „firmowy”. W aplikacjach z obsługą jednej tożsamości, np. aplikacjach biznesowych zarządzanych przy użyciu Narzędzia opakowującego aplikacje dostępnego w usłudze Intune, monit o podanie numeru PIN wyświetla się podczas uruchamiania, ponieważ zestaw Intune App SDK wie, że środowisko użytkownika w aplikacji jest zawsze „firmowe”.

- **Jak często użytkownik będzie otrzymywać monit o podanie numeru PIN usługi Intune?**
  Administrator IT może zdefiniować ustawienie zasad ochrony aplikacji usługi Intune „Ponownie sprawdź wymagania dostępu po (w minutach)” w konsoli administracyjnej usługi Intune. To ustawienie określa czas, po którym na urządzeniu są sprawdzane wymagania dotyczące dostępu i ponownie jest wyświetlany ekran numeru PIN aplikacji. Jednak wpływ na częstotliwość monitowania użytkownika mają następujące ważne informacje o numerze PIN: 

    - **Numer PIN jest współużytkowany przez aplikacje tego samego wydawcy, aby zwiększyć użyteczność:** w systemie iOS numer PIN danej aplikacji jest używany przez wszystkie aplikacje **tego samego wydawcy**. W systemie Android numer PIN danej aplikacji jest współużytkowany przez wszystkie aplikacje.
    - **Ciągłe działanie czasomierza skojarzonego z numerem PIN:** gdy zostanie wprowadzony numer PIN w celu uzyskania dostępu do aplikacji (aplikacji A) i aplikacja zostanie wyłączona z pierwszego planu (głównego fokusu wprowadzania) na urządzeniu, czasomierz numeru PIN zostanie zresetowany dla tego numeru PIN. Monit dla użytkownika o podanie numeru PIN nie będzie wyświetlany w żadnej aplikacji (aplikacji B), która współużytkuje ten numer PIN, ponieważ czasomierz został zresetowany. Monit pojawi się znowu po ponownym osiągnięciu odpowiedniej wartości ustawienia „Ponownie sprawdź wymagania dostępu po (w minutach)”. 

      >[!NOTE] 
      > Aby częściej sprawdzać wymagania dostępu użytkownika (tj. monit o podanie numeru PIN), szczególnie w przypadku często używanej aplikacji, zaleca się zmniejszenie wartości ustawienia „Ponownie sprawdź wymagania dostępu po (w minutach)”. 

- **Czy numer PIN jest bezpieczny?** Dzięki numerowi PIN tylko właściwy użytkownik uzyskuje dostęp do danych organizacji w aplikacji. W związku z tym przed ustawieniem lub zresetowaniem numeru PIN aplikacji usługi Intune użytkownik końcowy musi zalogować się przy użyciu swojego konta służbowego lub szkolnego. To uwierzytelnianie jest obsługiwane przez usługę Azure Active Directory za pośrednictwem zabezpieczonej wymiany tokenów i nie jest niewidoczne dla zestawu SDK aplikacji usługi Intune. Z punktu widzenia zabezpieczeń najlepszym sposobem na ochronę danych służbowych jest ich zaszyfrowanie. Szyfrowanie nie jest powiązane z numerem PIN aplikacji, ale stanowi jej zasady ochrony aplikacji.

- **Jak usługa Intune chroni numer PIN przed atakami siłowymi?** W ramach zasad numeru PIN aplikacji administrator IT może ustawić maksymalną liczbę prób uwierzytelniania numeru PIN przez użytkownika przed zablokowaniem aplikacji. Po wykonaniu pewnej liczby prób zestaw SDK aplikacji usługi Intune może wyczyścić dane „firmowe” z aplikacji.
  
- **Dlaczego konieczne jest dwukrotne ustawienie kodu PIN dla aplikacji tego samego wydawcy?**
  Zarządzanie aplikacjami mobilnymi (w systemie iOS) umożliwia obecnie korzystanie z numeru PIN na poziomie aplikacji ze znakami alfanumerycznymi i specjalnymi („kod dostępu”). Wymaga to udziału aplikacji (np.WXP, Outlook, Managed Browser, Yammer) w celu zintegrowania zestawu Intune App SDK dla systemu iOS. Bez tego ustawienia kodu dostępu nie są prawidłowo wymuszane w aplikacjach docelowych. Ta funkcja została dołączona do zestawu SDK usługi Intune dla systemu iOS w wersji 7.1.12. <br><br> Aby zapewnić jej obsługę i zgodność z poprzednimi wersjami zestawu SDK usługi Intune dla systemu iOS, wszystkie kody PIN (numeryczne lub kody dostępu) w wersji 7.1.12 oraz nowszych są obsługiwane niezależnie od numerycznego kodu PIN w poprzednich wersjach zestawu SDK. W związku z tym jeśli na urządzeniu znajdują się aplikacje z zestawem SDK usługi Intune dla systemu iOS w wersji wcześniejszej niż 7.1.12 oraz późniejszej niż 7.1.12 tego samego wydawcy, konieczne będzie skonfigurowanie dwóch kodów PIN. <br><br> Po uwzględnieniu powyższych warunków oba kody PIN (po jednym dla każdej aplikacji) nie są ze sobą w żaden sposób powiązane, tj. muszą być zgodne z zasadami ochrony aplikacji, które mają do niej zastosowanie. W efekcie użytkownik może skonfigurować dwa razy ten sam kod PIN *tylko* w przypadku, gdy aplikacje A i B są objęte tymi samymi zasadami (w zakresie kodu PIN). <br><br> Takie rozwiązanie jest charakterystyczne dla numeru PIN w aplikacjach systemu iOS, które są uruchamiane przy użyciu funkcji zarządzania aplikacjami mobilnymi usługi Intune. Z czasem, gdy aplikacje przyjmują nowsze wersje zestawu SDK usługi INTUNE dla systemu iOS, konieczność dwukrotnego ustawiania kodu PIN dla aplikacji tego samego wydawcy nie stanowi takiego problemu. Poniżej przedstawiono przykład.

  >[!NOTE]
  > Na przykład jeśli aplikacja A została utworzona przy użyciu wersji wcześniejszej niż 7.1.12, a aplikacja B tego samego wydawcy została utworzona za pomocą wersji 7.1.12 lub nowszej, użytkownik końcowy będzie musiał skonfigurować numery PIN oddzielnie dla aplikacji A i B, jeśli obie są zainstalowane na urządzeniu z systemem iOS. <br><br> Jeśli na urządzeniu jest zainstalowana aplikacja C, która zawiera zestaw SDK w wersji 7.1.9, będzie ona korzystać z tego samego kodu PIN, co aplikacja A. <br><br> Aplikacja D skompilowana przy użyciu wersji 7.1.14 będzie mieć ten sam kod PIN, co aplikacja B. <br><br> Jeśli na urządzeniu są zainstalowane tylko aplikacje A i C, trzeba ustawić jeden kod PIN. Ta sama zasada ma zastosowanie, jeśli na urządzeniu są zainstalowane tylko aplikacje B i D.

**Jak to wygląda w przypadku szyfrowania?** Administratorzy IT mogą wdrażać zasady ochrony aplikacji, które wymagają szyfrowania danych aplikacji. W ramach zasad administrator IT może również określić, kiedy zawartość będzie szyfrowana.

- **Jak usługa Intune szyfruje dane?** Zobacz tematy [Android app protection policy settings](app-protection-policy-settings-android.md) (Ustawienia zasad ochrony aplikacji systemu Android) i [iOS app protection policy settings](app-protection-policy-settings-ios.md) (Ustawienia zasad ochrony aplikacji systemu iOS), aby uzyskać szczegółowe informacje dotyczące ustawień zasad ochrony aplikacji dotyczących szyfrowania.

- **Co zostaje zaszyfrowane?** Szyfrowane są tylko dane oznaczone jako „firmowe” zgodnie z zasadami ochrony aplikacji administratora IT. Dane są uznawane za „firmowe”, jeśli pochodzą z lokalizacji firmowej. W przypadku aplikacji pakietu Office usługa Intune uznaje za lokalizacje firmowe: adres e-mail (Exchange) lub magazyn w chmurze (aplikacja OneDrive z kontem usługi OneDrive dla Firm). W przypadku aplikacji biznesowych zarządzanych przy użyciu Narzędzia opakowującego aplikacje dostępnego w usłudze Intune wszystkie dane aplikacji uznaje się za „firmowe”.

**Jak usługa Intune czyści dane zdalnie?** Usługa Intune umożliwia czyszczenie danych aplikacji na trzy różne sposoby: pełne czyszczenie urządzenia, selektywne czyszczenie pod kątem zarządzania urządzeniami przenośnymi oraz selektywne czyszczenie pod kątem zarządzania aplikacjami mobilnymi. Aby uzyskać więcej informacji o zdalnym czyszczeniu w usłudze MDM, zobacz temat [Usuwanie urządzeń za pomocą resetowania do ustawień fabrycznych lub usuwania danych firmy](devices-wipe.md#factory-reset). Aby dowiedzieć się więcej o czyszczeniu selektywnym za pomocą usługi MAM, zobacz sekcję [Usuwanie danych firmy](devices-wipe.md#remove-company-data) i temat [Jak czyścić z aplikacji tylko dane firmowe](apps-selective-wipe.md).

- **Co to jest resetowanie do ustawień fabrycznych** [Resetowanie do ustawień fabrycznych](devices-wipe.md) usuwa wszystkie dane użytkownika i ustawienia z **urządzenia** przez przywrócenie jego domyślnych ustawień fabrycznych. Urządzenie jest usuwane z usługi Intune.
  >[!NOTE]
  > Resetowanie do ustawień fabrycznych może odbyć się tylko na urządzeniach zarejestrowanych w usłudze zarządzania urządzeniami mobilnymi (MDM) usługi Intune.

- **Co to jest selektywne czyszczenie pod kątem zarządzania urządzeniami przenośnymi?** Aby przeczytać o usuwaniu danych firmowych, zobacz temat [Usuwanie urządzeń — Usuwanie danych firmy](devices-wipe.md#remove-company-data).

- **Co to jest selektywne czyszczenie pod kątem zarządzania aplikacjami mobilnymi?** Selektywne czyszczenie pod kątem zarządzania aplikacjami mobilnymi po prostu usuwa dane aplikacji firmowych z aplikacji. Żądanie jest inicjowane z użyciem usługi Intune w ramach witryny Azure Portal. Aby dowiedzieć się, jak zainicjować żądanie czyszczenia, zobacz temat [Jak czyścić z aplikacji usługi Intune tylko dane firmowe](apps-selective-wipe.md).

- **Jak szybko odbywa się selektywne czyszczenie danych pod kątem zarządzania aplikacjami mobilnymi?** Jeśli użytkownik używa aplikacji po zainicjowaniu selektywnego czyszczenia danych, zestaw SDK aplikacji usługi Intune sprawdza co 30 minut, czy wysłano żądanie selektywnego czyszczenia danych w ramach usługi Intune MAM. Sprawdzenie takie odbywa się również, gdy użytkownik uruchamia aplikację po raz pierwszy i loguje się przy użyciu swojego konta służbowego lub szkolnego.

**Dlaczego usługi lokalne nie są obsługiwane w aplikacjach chronionych przy użyciu usługi Intune?** Ochrona aplikacji usługi Intune zależy od zgodności tożsamości użytkownika między aplikacją i zestawem SDK aplikacji usługi Intune. Można to zagwarantować tylko przez nowoczesne uwierzytelnianie. Istnieją scenariusze, w których aplikacje mogą działać w konfiguracji lokalnej, ale nie są one ani zgodne, ani gwarantowane.

**Czy istnieje bezpieczny sposób na otwieranie linków sieci Web z zarządzanych aplikacji?** Tak! Administrator IT może wdrożyć i ustawić zasady ochrony aplikacji dla [aplikacji Intune Managed Browser](app-configuration-managed-browser.md), przeglądarki sieci Web opracowanej przez Microsoft Intune, którą można łatwo zarządzać za pomocą usługi Intune. Administrator IT może wymagać, aby wszystkie linki internetowe w aplikacjach zarządzanych przez usługę Intune były otwierane przy użyciu aplikacji Managed Browser.


## <a name="app-experience-on-android"></a>Środowisko aplikacji w systemie Android

**Dlaczego do obsługi ochrony aplikacji usługi Intune na urządzeniach z systemem Android jest wymagana aplikacja Portal firmy?** Większość funkcji ochrony aplikacji jest wbudowanych w aplikacji Portal firmy. Rejestracja urządzeń _nie jest konieczna_, mimo że aplikacja Portal firmy jest zawsze wymagana. W przypadku konfiguracji MAM-WE użytkownik końcowy po prostu musi mieć zainstalowaną na urządzeniu aplikację Portal firmy.

## <a name="app-experience-on-ios"></a>Środowisko aplikacji w systemie iOS

**Mogę otwierać dane służbowe lub szkolne w aplikacjach niezarządzanych przy użyciu rozszerzenia udostępniania systemu iOS, nawet wtedy, gdy zasady transferu danych mają wartość „tylko aplikacje zarządzane” lub „brak aplikacji”. Czy nie powoduje to wycieku danych?** Zasady ochrony aplikacji usługi Intune nie mogą kontrolować rozszerzenia udostępniania systemu iOS bez zarządzania danym urządzeniem. W związku z tym usługa Intune _**szyfruje dane „firmowe” przed ich udostępnieniem poza aplikację**_. Aby to sprawdzić, spróbuj otworzyć plik „firmowy” poza zarządzaną aplikacją. Plik powinien być zaszyfrowany i jego otwarcie poza zarządzaną aplikacją nie powinno być możliwe.

## <a name="see-also"></a>Zobacz też
- [Implementowanie własnego planu dotyczącego usługi Intune](planning-guide-onboarding.md)
- [Testowanie i sprawdzanie poprawności w usłudze Intune](planning-guide-test-validation.md)
- [Ustawienia zasad zarządzania aplikacjami mobilnymi systemu Android w usłudze Microsoft Intune](app-protection-policy-settings-android.md)
- [Ustawienia zasad zarządzania aplikacjami mobilnymi systemu iOS](app-protection-policy-settings-ios.md)
- [Weryfikowanie zasad ochrony aplikacji](app-protection-policies-validate.md)
- [Dodawanie zasad konfiguracji aplikacji dla zarządzanych aplikacji bez rejestracji urządzeń](app-configuration-policies-managed-app.md)
- [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](get-support.md)
