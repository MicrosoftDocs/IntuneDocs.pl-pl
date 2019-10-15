---
title: Często zadawane pytania dotyczące zarządzania aplikacjami mobilnymi (MAM) i ochrony aplikacji
description: Ten artykuł zawiera odpowiedzi na niektóre często zadawane pytania dotyczące zarządzania aplikacjami mobilnymi (MAM) usługi Intune i ochrony jej aplikacji.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/09/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 149def73-9d08-494b-97b7-4ba1572f0623
ms.reviewer: erikre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1e77d303b3f9100c688b64feae6ca330d515df1b
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71724688"
---
# <a name="frequently-asked-questions-about-mam-and-app-protection"></a>Często zadawane pytania dotyczące zarządzania aplikacjami mobilnymi (MAM) i ochrony aplikacji

Ten artykuł zawiera odpowiedzi na niektóre często zadawane pytania dotyczące zarządzania aplikacjami mobilnymi (MAM) usługi Intune i ochrony aplikacji usługi Intune.

## <a name="mam-basics"></a>Zarządzanie aplikacjami mobilnymi — podstawowe informacje

**Co to jest MAM?**<br></br>
[Zarządzanie aplikacjami mobilnymi (MAM) usługi Intune](app-lifecycle.md) obejmuje zestaw funkcji zarządzania usługi Intune, które umożliwiają publikowanie, wypychanie, konfigurowanie, zabezpieczanie, monitorowanie i aktualizowanie aplikacji mobilnych dla użytkowników.

**Jakie są zalety ochrony aplikacji MAM?**<br></br>
Zarządzanie aplikacjami mobilnymi pozwala chronić dane organizacji w obrębie aplikacji. MAM bez rejestracji (MAM-WE) umożliwia zarządzanie aplikacją służbową, która zawiera dane poufne, z prawie każdego urządzenia — w tym z urządzenia osobistego w scenariuszach BYOD (przynieś własne urządzenie). Zarządzanie aplikacjami mobilnymi usługi Intune można stosować do wielu aplikacji użytkowych, takich jak aplikacje pakietu Microsoft Office. Zobacz oficjalną listę [aplikacji zarządzanych przez usługę Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) dostępnych do użytku publicznego.

**Jakie konfiguracje urządzeń obsługuje zarządzanie aplikacjami mobilnymi?**<br></br>
Zarządzanie aplikacjami mobilnymi usługi Intune obsługuje dwie konfiguracje:
- **Zarządzanie urządzeniami przenośnymi i zarządzanie aplikacjami mobilnymi w usłudze Intune**: Administratorzy IT mogą zarządzać aplikacjami korzystającymi z zasad zarządzania aplikacjami mobilnymi i ochrony aplikacji tylko na urządzeniach zarejestrowanych w usłudze zarządzania urządzeniami przenośnymi (MDM) usługi Intune. Aby zarządzać aplikacjami przy użyciu konfiguracji MDM + MAM, klienci powinni używać konsoli usługi Intune w witrynie Azure Portal pod adresem https://portal.azure.com.

- **Zarządzanie aplikacjami mobilnymi bez rejestracji urządzenia**: zarządzanie aplikacjami mobilnymi bez rejestracji urządzeń (MAM-WE) umożliwia administratorom IT zarządzanie aplikacjami za pomocą zasad zarządzania aplikacjami mobilnymi i ochrony aplikacji na urządzeniach, które nie zostały zarejestrowane w usłudze Intune MDM. Oznacza to, że aplikacjami można zarządzać przy użyciu usługi Intune na urządzeniach zarejestrowanych u dostawców EMM innych firm. Aby zarządzać aplikacjami przy użyciu konfiguracji MAM-WE, klienci powinni używać konsoli usługi Intune w witrynie Azure Portal pod adresem [https://portal.azure.com](https://portal.azure.com). Aplikacjami można również zarządzać przy użyciu usługi Intune na urządzeniach zarejestrowanych u dostawców usługi Enterprise Mobility Management (EMM) innych firm lub w ogóle niezarejestrowanych w usłudze MDM.


## <a name="app-protection-policies"></a>Zasady ochrony aplikacji

**Co to są zasady ochrony aplikacji?**<br></br>
Zasady ochrony aplikacji to reguły, które mogą zagwarantować, że dane organizacji pozostaną bezpieczne lub nie zostaną pobrane z zarządzanej aplikacji. Zasady mogą być regułą, która jest wymuszana w przypadku próby uzyskania dostępu do danych firmowych lub ich przeniesienia przez użytkownika albo zestawem akcji, które są zabronione lub monitorowane, gdy użytkownik korzysta z aplikacji.

**Jakie są przykłady zasad ochrony aplikacji?**<br></br>
Zobacz tematy [Android app protection policy settings](app-protection-policy-settings-android.md) (Ustawienia zasad ochrony aplikacji systemu Android) i [iOS app protection policy settings](app-protection-policy-settings-ios.md) (Ustawienia zasad ochrony aplikacji systemu iOS), aby uzyskać szczegółowe informacje dotyczące poszczególnych ustawień zasad ochrony aplikacji.

**Czy istnieje możliwość stosowania zarówno zasad MAM, jak i usługi MDM dla tego samego użytkownika, w tym samym czasie i na różnych urządzeniach? Na przykład w przypadku, gdy użytkownik powinien być w stanie uzyskać dostęp do zasobów służbowych z własnej maszyny objętej zarządzaniem aplikacjami mobilnymi, ale również może przyjść do pracy i korzystać z urządzenia zarządzanego przez usługę Intune MDM. Czy istnieją jakieś zastrzeżenia do tego pomysłu?**<br></br>
Jeśli zasady zarządzania aplikacjami mobilnymi są stosowane do użytkownika bez ustawiania stanu urządzenia, te zasady będą działać dla użytkownika zarówno w przypadku użycia własnych urządzeń (BYOD), jak i urządzeń zarządzanych przez usługę Intune. Można także zastosować zasady zarządzania aplikacjami mobilnymi w oparciu o stan zarządzany. W tym celu podczas tworzenia zasad ochrony aplikacji dla pozycji Dotyczy wszystkich typów aplikacji należy wybrać opcję Nie. Następnie należy wykonać jedną z następujących czynności:
- Zastosowanie mniej rygorystycznych zasad zarządzania aplikacjami mobilnymi do urządzeń zarządzanych przez usługę Intune oraz bardziej rygorystycznych zasad zarządzania aplikacjami mobilnymi do urządzeń niezarejestrowanych w usłudze MDM.
- Zastosowanie zasad zarządzania aplikacjami mobilnymi tylko do niezarejestrowanych urządzeń.

Aby uzyskać więcej informacji, zobacz [Monitorowanie zasad ochrony aplikacji](app-protection-policies-monitor.md).

## <a name="apps-you-can-manage-with-app-protection-policies"></a>Aplikacje, którymi można zarządzać za pomocą zasad ochrony aplikacji

**Którymi aplikacjami można zarządzać przy użyciu zasad ochrony aplikacji?**<br></br>
Każdą aplikacją zintegrowaną z zestawem [Intune App SDK](../developer/app-sdk.md) lub opakowaną za pomocą [Narzędzia opakowującego aplikacje usługi Intune](../developer/apps-prepare-mobile-application-management.md) można zarządzać przy użyciu zasad ochrony aplikacji usługi Intune. Zobacz oficjalną listę [aplikacji zarządzanych przez usługę Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) dostępnych do użytku publicznego.

**Jakie są podstawowe wymagania dotyczące użycia zasad ochrony aplikacji w aplikacji zarządzanej przez usługę Intune?**

- Użytkownik końcowy musi mieć konto usługi Azure Active Directory (AAD). Zobacz temat [Dodawanie użytkowników i przyznawanie uprawnień administracyjnych do usługi Intune](../fundamentals/users-add.md), aby dowiedzieć się, jak utworzyć użytkowników usługi Intune w usłudze Azure Active Directory.

- Użytkownik końcowy musi mieć licencję usługi Microsoft Intune przypisaną do swojego konta usługi Azure Active Directory. Zobacz temat [Zarządzanie licencjami usługi Intune](../fundamentals/licenses-assign.md), aby dowiedzieć się, jak przypisać licencje usługi Intune użytkownikom końcowym.

- Użytkownik końcowy musi należeć do grupy zabezpieczeń objętej zasadami ochrony aplikacji. Te same zasady ochrony aplikacji muszą obejmować określoną używaną aplikację. Zasady ochrony aplikacji można tworzyć i wdrażać w konsoli usługi Intune w [portalu Azure](https://portal.azure.com). Grupy zabezpieczeń można obecnie tworzyć w [centrum administracyjnym platformy Microsoft 365](https://admin.microsoft.com).

- Użytkownik końcowy musi zalogować się do aplikacji przy użyciu konta usługi AAD.

**Co zrobić, jeśli chcę włączyć usługę Intune App Protection dla aplikacji, która nie korzysta z obsługiwanej platformy programistycznej?**

Zespół programistyczny zajmujący się zestawem Intune SDK aktywnie przeprowadza testy i zapewnia obsługę aplikacji z natywnych platform Android, iOS (Obj-C, Swift), Xamarin, Xamarin.Forms i Cordova. Niektórym klientom udało się zintegrować zestaw Intune SDK z innymi platformami (takimi jak React Native i NativeScript), ale nie udostępniamy deweloperom żadnych wskazówek ani wtyczek dotyczących nieobsługiwanych przez nas platform.

**Czy zestaw SDK rozwiązania App Policy Protection usługi Intune obsługuje bibliotekę Microsoft Authentication Library (MSAL) lub konta społecznościowe?**<br></br>
Zestaw Intune APP SDK rozwiązania używa niektórych zaawansowanych możliwości biblioteki ADAL dla zestawu SDK zarówno w wersjach własnych, jak i innych firm. W efekcie biblioteka MSAL nie działa dobrze w przypadku wielu naszych podstawowych scenariuszy, takich jak uwierzytelnianie w usłudze Intune App Protection i uruchamianie warunkowe. Biorąc pod uwagę, że zgodnie z ogólnymi wytycznymi nasz zespół ds. tożsamości zaleca przejście na bibliotekę MSAL dla wszystkich aplikacji pakietu Microsoft Office, zestaw SDK usługi Intune będzie musiał w końcu ją obsługiwać — obecnie nie ma jednak konkretnego planu.

**Jakie są dodatkowe wymagania dotyczące korzystania z [aplikacji mobilnej Outlook](https://products.office.com/outlook)?**

- Użytkownik końcowy musi mieć na urządzeniu aplikację mobilną Outlook.

- Użytkownik końcowy musi mieć skrzynkę pocztową usługi [Office 365 Exchange Online](https://products.office.com/exchange/exchange-online) oraz licencję powiązaną z kontem usługi Azure Active Directory.

  >[!NOTE]
  > Aplikacja mobilna Outlook aktualnie obsługuje tylko usługę Intune App Protection dla usługi Microsoft Exchange Online oraz [program Exchange Server z nowoczesnym uwierzytelnianiem hybrydowym](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx), a nie obsługuje programu Exchange w ramach usługi Office 365 Dedicated.

**Jakie są dodatkowe wymagania dotyczące korzystania z aplikacji [Word, Excel i PowerPoint](https://products.office.com/business/office)?**

- Użytkownik końcowy musi mieć licencję usługi [Office 365 Business lub Enterprise](https://products.office.com/business/compare-more-office-365-for-business-plans) przypisaną do swojego konta usługi Azure Active Directory. Subskrypcja musi obejmować aplikacje pakietu Office na urządzeniach przenośnych i może uwzględniać konto magazynu w chmurze w ramach usługi [OneDrive dla Firm](https://onedrive.live.com/about/business/). Licencje usługi Office 365 można przypisać w [centrum administracyjnym platformy Microsoft 365](https://admin.microsoft.com), wykonując te [instrukcje](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

- Użytkownik końcowy musi mieć zarządzaną lokalizację skonfigurowaną przy użyciu funkcji szczegółowego zapisywania jako — w ramach ustawienia „Nie zezwalaj na używanie polecenia Zapisz jako” w zasadach ochrony aplikacji. Przykładowo — jeśli zarządzana lokalizacja to OneDrive, aplikację [OneDrive](https://onedrive.live.com/about/) należy skonfigurować w aplikacji Word, Excel lub PowerPoint użytkownika końcowego.

- Jeśli zarządzana lokalizacja to OneDrive, aplikacja musi być objęta zasadami ochrony aplikacji wdrożonymi dla użytkownika końcowego.

  >[!NOTE]
  > Aplikacje mobilne pakietu Office obsługują obecnie tylko usługę SharePoint Online, a nie lokalny program SharePoint.

**Dlaczego w pakiecie Office jest wymagana zarządzana lokalizacja (np. OneDrive)?**<br></br>
Usługa Intune oznacza wszystkie dane w aplikacji jako „firmowe” lub „osobiste”. Dane są uznawane za „firmowe”, jeśli pochodzą z lokalizacji firmowej. W przypadku aplikacji pakietu Office usługa Intune uznaje za lokalizacje firmowe: adres e-mail (Exchange) lub magazyn w chmurze (aplikacja OneDrive z kontem usługi OneDrive dla Firm).

**Jakie są dodatkowe wymagania dotyczące korzystania z usługi Skype dla firm?**<br></br>
Zobacz wymagania licencyjne usługi [Skype dla firm](https://products.office.com/skype-for-business/it-pros). Dla konfiguracji hybrydowych i lokalnych usługi Skype dla firm zobacz odpowiednio artykuły [Hybrid Modern Auth for SfB and Exchange goes GA](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Hybrid-Modern-Auth-for-SfB-and-Exchange-goes-GA/ba-p/134756) (Nowoczesne uwierzytelnianie hybrydowe dla usługi Skype dla firm i programu Exchange jest ogólnie dostępne) lub [Modern Auth for SfB OnPrem with AAD](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Modern-Auth-for-SfB-OnPrem-with-AAD/ba-p/180910) (Nowoczesne uwierzytelnianie dla lokalnej usługi Skype dla firm za pomocą usługi AAD).

## <a name="app-protection-features"></a>Funkcje ochrony aplikacji

**Co to jest obsługa wielu tożsamości?**<br></br>
Obsługa wielu tożsamości polega na tym, że zestaw SDK aplikacji usługi Intune może przypisywać zasady ochrony aplikacji tylko do konta służbowego zarejestrowanego w aplikacji. Jeśli w aplikacji zostanie zarejestrowane konto osobiste , dane pozostaną bez zmian.

**Jaki jest cel obsługi wielu tożsamości?**<br></br>
Dzięki obsłudze wielu tożsamości zarówno aplikacje dla odbiorców „firmowych”, jak i konsumentów (tj. aplikacje pakietu Office) mogą być wprowadzane na rynek z funkcjami ochrony aplikacji usługi Intune dla kont „firmowych”.

**Jak wygląda obsługa wielu tożsamości w programie Outlook?**<br></br>
Ze względu na to, że w programie Outlook widok osobistych i „firmowych” wiadomości e-mail jest połączony, aplikacja Outlook monituje o numer PIN usługi Intune podczas uruchamiania.

**Co to jest numer PIN aplikacji usługi Intune?**<br></br>
Osobisty numer identyfikacyjny (PIN) jest kodem dostępu służącym do weryfikacji, czy właściwy użytkownik uzyskuje dostęp do danych organizacji w aplikacji.

- **Kiedy jest wyświetlany monit o wprowadzenie numeru PIN?**<br></br> Monit o podanie numeru PIN aplikacji użytkownika jest wyświetlany w usłudze Intune tylko wtedy, gdy użytkownik chce uzyskać dostęp do danych „firmowych”. W aplikacjach z obsługą wielu tożsamości, np. Word, Excel lub PowerPoint, monit o wprowadzenie numeru PIN jest wyświetlany, gdy użytkownik próbuje otworzyć dokument lub plik „firmowy”. W aplikacjach z obsługą jednej tożsamości, np. aplikacjach biznesowych zarządzanych przy użyciu Narzędzia opakowującego aplikacje dostępnego w usłudze Intune, monit o podanie numeru PIN wyświetla się podczas uruchamiania, ponieważ zestaw Intune App SDK wie, że środowisko użytkownika w aplikacji jest zawsze „firmowe”.

- **Jak często użytkownik będzie otrzymywać monit o podanie numeru PIN usługi Intune?**<br></br> Administrator IT może zdefiniować ustawienie zasad ochrony aplikacji usługi Intune „Ponownie sprawdź wymagania dostępu po (w minutach)” w konsoli administracyjnej usługi Intune. To ustawienie określa czas, po którym na urządzeniu są sprawdzane wymagania dotyczące dostępu i ponownie jest wyświetlany ekran numeru PIN aplikacji. Jednak wpływ na częstotliwość monitowania użytkownika mają następujące ważne informacje o numerze PIN: 

  - **Numer PIN jest udostępniany w aplikacjach tego samego wydawcy w celu zwiększenia użyteczności:** w systemie iOS numer PIN danej aplikacji jest udostępniany we wszystkich aplikacjach **tego samego wydawcy aplikacji**. W systemie Android numer PIN danej aplikacji jest współużytkowany przez wszystkie aplikacje.
  - **Zachowanie „Ponownie sprawdź wymagania dostępu po (w minutach)” po ponownym uruchomieniu urządzenia:** funkcja „Czasomierz numeru PIN” śledzi liczbę minut braku aktywności, które określają, kiedy należy ponownie wyświetlić numer PIN aplikacji usługi Intune. W systemie iOS na czasomierz numeru PIN nie ma wpływu ponowne uruchomienie urządzenia. W związku z tym ponowne uruchomienie urządzenia nie ma wpływu na liczbę minut, przez które użytkownik jest nieaktywny w aplikacji systemu iOS objętej zasadami numeru PIN usługi Intune. W systemie Android czasomierz numeru PIN jest resetowany przy ponownym uruchomieniu urządzenia. W efekcie aplikacje systemu Android z zasadami numeru PIN usługi Intune prawdopodobnie wyświetlą zapytanie o numer PIN aplikacji niezależnie od wartości ustawienia „Ponownie sprawdź wymagania dostępu po (w minutach)” **po ponownym uruchomieniu urządzenia**.  
  - **Ciągłe działanie czasomierza skojarzonego z numerem PIN:** gdy numer PIN zostanie wprowadzony w celu uzyskania dostępu do aplikacji (aplikacji A) i aplikacja zostanie wyłączona z pierwszego planu (głównego fokusu wprowadzania) na urządzeniu, czasomierz numeru PIN zostanie zresetowany dla tego numeru PIN. Monit dla użytkownika o podanie numeru PIN nie będzie wyświetlany w żadnej aplikacji (aplikacji B), która współużytkuje ten numer PIN, ponieważ czasomierz został zresetowany. Monit pojawi się znowu po ponownym osiągnięciu odpowiedniej wartości ustawienia „Ponownie sprawdź wymagania dostępu po (w minutach)”.

W przypadku urządzeń z systemem iOS, nawet jeśli numer PIN jest współużytkowany pomiędzy aplikacjami od różnych dostawców, zostanie ponownie wyświetlony monit, jeśli ponownie osiągnięto wartość **Sprawdź ponownie wymagania dostępu po (minuty)** dla aplikacji, która nie jest głównym elementem fokusu wprowadzania danych. Przykładowo użytkownik ma aplikację _A_ od wydawcy _X_ oraz aplikację _B_ od wydawcy _Y_; obie aplikacje współdzielą ten sam numer PIN. Użytkownik skupia się na aplikacji _A_ (na pierwszym planie), a aplikacja _B_ jest zminimalizowana. Po osiągnięciu wartości **Sprawdź ponownie wymagania dostępu po (minuty)** i przełączeniu się przez użytkownika na aplikację _B_ będzie wymagany numer PIN.

  >[!NOTE] 
  > Aby częściej sprawdzać wymagania dostępu użytkownika (tj. monit o podanie numeru PIN), szczególnie w przypadku często używanej aplikacji, zaleca się zmniejszenie wartości ustawienia „Ponownie sprawdź wymagania dostępu po (w minutach)”. 
      
- **Jak numer PIN usługi Intune działa z numerami PIN wbudowanej aplikacji dla programu Outlook i OneDrive?**<br></br>
Numer PIN usługi Intune działa na podstawie czasomierza bazującego na braku aktywności, znany również jako wartość „Ponownie sprawdź wymagania dostępu po (w minutach)”. W efekcie monity o numer PIN usługi Intune są wyświetlane niezależnie od monitów o numer PIN wbudowanej aplikacji dla programu Outlook i OneDrive, które często są domyślnie powiązane z uruchomieniem aplikacji. Jeśli użytkownik jednocześnie otrzymuje obydwa monity o numer PIN, oczekiwane zachowanie powinno określać, że numer PIN usługi Intune ma pierwszeństwo. 

- **Czy numer PIN jest bezpieczny?**<br></br> Dzięki numerowi PIN tylko właściwy użytkownik uzyskuje dostęp do danych organizacji w aplikacji. W związku z tym przed ustawieniem lub zresetowaniem numeru PIN aplikacji usługi Intune użytkownik końcowy musi zalogować się przy użyciu swojego konta służbowego lub szkolnego. To uwierzytelnianie jest obsługiwane przez usługę Azure Active Directory za pośrednictwem zabezpieczonej wymiany tokenów i nie jest niewidoczne dla zestawu SDK aplikacji usługi Intune. Z punktu widzenia zabezpieczeń najlepszym sposobem na ochronę danych służbowych jest ich zaszyfrowanie. Szyfrowanie nie jest powiązane z numerem PIN aplikacji, ale stanowi jej zasady ochrony aplikacji.

- **Jak usługa Intune chroni numer PIN przed atakami siłowymi?**<br></br> W ramach zasad numeru PIN aplikacji administrator IT może ustawić maksymalną liczbę prób uwierzytelniania numeru PIN przez użytkownika przed zablokowaniem aplikacji. Po wykonaniu pewnej liczby prób zestaw SDK aplikacji usługi Intune może wyczyścić dane „firmowe” z aplikacji.
  
- **Dlaczego konieczne jest dwukrotne ustawienie kodu PIN dla aplikacji tego samego wydawcy?**<br></br> Zarządzanie aplikacjami mobilnymi (w systemie iOS) umożliwia obecnie korzystanie z numeru PIN na poziomie aplikacji ze znakami alfanumerycznymi i specjalnymi („kod dostępu”). Wymaga to udziału aplikacji (np.WXP, Outlook, Managed Browser, Yammer) w celu zintegrowania zestawu Intune App SDK dla systemu iOS. Bez tego ustawienia kodu dostępu nie są prawidłowo wymuszane w aplikacjach docelowych. Ta funkcja została dołączona do zestawu SDK usługi Intune dla systemu iOS w wersji 7.1.12. <br><br> Aby zapewnić jej obsługę i zgodność z poprzednimi wersjami zestawu SDK usługi Intune dla systemu iOS, wszystkie kody PIN (numeryczne lub kody dostępu) w wersji 7.1.12 oraz nowszych są obsługiwane niezależnie od numerycznego kodu PIN w poprzednich wersjach zestawu SDK. W związku z tym jeśli na urządzeniu znajdują się aplikacje z zestawem SDK usługi Intune dla systemu iOS w wersji wcześniejszej niż 7.1.12 oraz późniejszej niż 7.1.12 tego samego wydawcy, konieczne będzie skonfigurowanie dwóch kodów PIN. <br><br> Po uwzględnieniu powyższych warunków oba kody PIN (po jednym dla każdej aplikacji) nie są ze sobą w żaden sposób powiązane, tj. muszą być zgodne z zasadami ochrony aplikacji, które mają do niej zastosowanie. W efekcie użytkownik może skonfigurować dwa razy ten sam kod PIN *tylko* w przypadku, gdy aplikacje A i B są objęte tymi samymi zasadami (w zakresie kodu PIN). <br><br> Takie rozwiązanie jest charakterystyczne dla numeru PIN w aplikacjach systemu iOS, które są uruchamiane przy użyciu funkcji zarządzania aplikacjami mobilnymi usługi Intune. Z czasem, gdy aplikacje przyjmują nowsze wersje zestawu SDK usługi INTUNE dla systemu iOS, konieczność dwukrotnego ustawiania kodu PIN dla aplikacji tego samego wydawcy nie stanowi takiego problemu. Poniżej przedstawiono przykład.

  >[!NOTE]
  > Na przykład jeśli aplikacja A została utworzona przy użyciu wersji wcześniejszej niż 7.1.12, a aplikacja B tego samego wydawcy została utworzona za pomocą wersji 7.1.12 lub nowszej, użytkownik końcowy będzie musiał skonfigurować numery PIN oddzielnie dla aplikacji A i B, jeśli obie są zainstalowane na urządzeniu z systemem iOS. <br><br> Jeśli na urządzeniu jest zainstalowana aplikacja C, która zawiera zestaw SDK w wersji 7.1.9, będzie ona korzystać z tego samego kodu PIN, co aplikacja A. <br><br> Aplikacja D skompilowana przy użyciu wersji 7.1.14 będzie mieć ten sam kod PIN, co aplikacja B. <br><br> Jeśli na urządzeniu są zainstalowane tylko aplikacje A i C, trzeba ustawić jeden kod PIN. Ta sama zasada ma zastosowanie, jeśli na urządzeniu są zainstalowane tylko aplikacje B i D.

**Jak to wygląda w przypadku szyfrowania?**<br></br>
Administratorzy IT mogą wdrażać zasady ochrony aplikacji, które wymagają szyfrowania danych aplikacji. W ramach zasad administrator IT może również określić, kiedy zawartość będzie szyfrowana.

- **Jak usługa Intune szyfruje dane?**<br></br> Zobacz tematy [Android app protection policy settings](app-protection-policy-settings-android.md) (Ustawienia zasad ochrony aplikacji systemu Android) i [iOS app protection policy settings](app-protection-policy-settings-ios.md) (Ustawienia zasad ochrony aplikacji systemu iOS), aby uzyskać szczegółowe informacje dotyczące ustawień zasad ochrony aplikacji dotyczących szyfrowania.

- **Co zostaje zaszyfrowane?**<br></br> Szyfrowane są tylko dane oznaczone jako „firmowe” zgodnie z zasadami ochrony aplikacji administratora IT. Dane są uznawane za „firmowe”, jeśli pochodzą z lokalizacji firmowej. W przypadku aplikacji pakietu Office usługa Intune uznaje za lokalizacje firmowe: adres e-mail (Exchange) lub magazyn w chmurze (aplikacja OneDrive z kontem usługi OneDrive dla Firm). W przypadku aplikacji biznesowych zarządzanych przy użyciu Narzędzia opakowującego aplikacje dostępnego w usłudze Intune wszystkie dane aplikacji uznaje się za „firmowe”.

**Jak usługa Intune czyści dane zdalnie?**<br></br>
Usługa Intune umożliwia czyszczenie danych aplikacji na trzy różne sposoby: pełne czyszczenie urządzenia, selektywne czyszczenie pod kątem zarządzania urządzeniami przenośnymi oraz selektywne czyszczenie pod kątem zarządzania aplikacjami mobilnymi. Aby uzyskać więcej informacji o zdalnym czyszczeniu w usłudze MDM, zobacz [Usuwanie urządzeń za pomocą czyszczenia lub wycofywania](../remote-actions/devices-wipe.md). Aby dowiedzieć się więcej o czyszczeniu selektywnym za pomocą usługi MAM, zobacz sekcję [Akcja Wycofaj](../remote-actions/devices-wipe.md#retire) i temat [Jak czyścić z aplikacji tylko dane firmowe](apps-selective-wipe.md).

- **Co to jest czyszczenie?**<br></br> [Czyszczenie](../remote-actions/devices-wipe.md) usuwa wszystkie dane użytkownika i ustawienia z **urządzenia** przez przywrócenie jego domyślnych ustawień fabrycznych. Urządzenie jest usuwane z usługi Intune.
  >[!NOTE]
  > Czyszczenie może odbyć się tylko na urządzeniach zarejestrowanych w usłudze zarządzania urządzeniami przenośnymi (MDM) usługi Intune.

- **Co to jest selektywne czyszczenie pod kątem zarządzania urządzeniami przenośnymi?**<br></br> Aby przeczytać o usuwaniu danych firmowych, zobacz temat [Usuwanie urządzeń — wycofywanie](../remote-actions/devices-wipe.md#retire).

- **Co to jest selektywne czyszczenie pod kątem zarządzania aplikacjami mobilnymi?**<br></br> Selektywne czyszczenie pod kątem zarządzania aplikacjami mobilnymi po prostu usuwa dane aplikacji firmowych z aplikacji. Żądanie jest inicjowane z użyciem usługi Intune w ramach witryny Azure Portal. Aby dowiedzieć się, jak zainicjować żądanie czyszczenia, zobacz temat [Jak czyścić z aplikacji usługi Intune tylko dane firmowe](apps-selective-wipe.md).

- **Jak szybko odbywa się selektywne czyszczenie danych pod kątem zarządzania aplikacjami mobilnymi?**<br></br> Jeśli użytkownik używa aplikacji po zainicjowaniu selektywnego czyszczenia danych, zestaw SDK aplikacji usługi Intune sprawdza co 30 minut, czy wysłano żądanie selektywnego czyszczenia danych w ramach usługi Intune MAM. Sprawdzenie takie odbywa się również, gdy użytkownik uruchamia aplikację po raz pierwszy i loguje się przy użyciu swojego konta służbowego lub szkolnego.

**Dlaczego usługi lokalne nie są obsługiwane w aplikacjach chronionych przy użyciu usługi Intune?**<br></br>
Ochrona aplikacji usługi Intune zależy od zgodności tożsamości użytkownika między aplikacją i zestawem SDK aplikacji usługi Intune. Można to zagwarantować tylko przez nowoczesne uwierzytelnianie. Istnieją scenariusze, w których aplikacje mogą działać w konfiguracji lokalnej, ale nie są one ani zgodne, ani gwarantowane.

**Czy istnieje bezpieczny sposób na otwieranie linków sieci Web z zarządzanych aplikacji?**<br></br>
Tak! Administrator IT może wdrożyć i ustawić zasady ochrony aplikacji dla [aplikacji Intune Managed Browser](../apps/app-configuration-managed-browser.md), przeglądarki sieci Web opracowanej przez Microsoft Intune, którą można łatwo zarządzać za pomocą usługi Intune. Administrator IT może wymagać, aby wszystkie linki internetowe w aplikacjach zarządzanych przez usługę Intune były otwierane przy użyciu aplikacji Managed Browser.

## <a name="app-experience-on-android"></a>Środowisko aplikacji w systemie Android

**Dlaczego do obsługi ochrony aplikacji usługi Intune na urządzeniach z systemem Android jest wymagana aplikacja Portal firmy?**<br></br>
Większość funkcji ochrony aplikacji jest wbudowanych w aplikacji Portal firmy. Rejestracja urządzeń _nie jest konieczna_, mimo że aplikacja Portal firmy jest zawsze wymagana. W przypadku konfiguracji MAM-WE użytkownik końcowy po prostu musi mieć zainstalowaną na urządzeniu aplikację Portal firmy.

**W jaki sposób wiele ustawień dostępu zasad ochrony aplikacji usługi Intune skonfigurowanych dla tego samego zestawu aplikacji i użytkowników działa w systemie Android?**<br></br>
Zasady ochrony aplikacji usługi Intune dla dostępu będą stosowane w określonej kolejności na urządzeniach użytkowników końcowych, kiedy będą próbowali uzyskać dostęp do aplikacji docelowej ze swojego konta firmowego. Ogólnie rzecz biorąc, pierwszeństwo ma blokada, następnie ostrzeżenie z możliwością odrzucenia. Na przykład jeśli ma zastosowanie do określonego użytkownika/aplikacji, ustawienie minimalnej wersji poprawki zabezpieczeń systemu Android, które ostrzega użytkownika o konieczności uaktualnienia poprawki, zostanie zastosowane po ustawieniu minimalnej wersji poprawki zabezpieczeń systemu Android, które blokuje dostęp użytkownika. Dlatego w scenariuszu, w którym administrator IT skonfigurował minimalną wersję poprawki zabezpieczeń systemu Android na 2018-03-01 i minimalną wersję poprawki zabezpieczeń systemu Android (tylko ostrzeżenie) na 2018-02-01, a urządzenie próbujące uzyskać dostęp do aplikacji ma wersję poprawki 2018-01-01, użytkownik końcowy zostałby zablokowany na podstawie bardziej restrykcyjnego ustawienia minimalnej wersji poprawki systemu Android, które powoduje zablokowanie dostępu. 

Podczas pracy z różnymi typami ustawień pierwszeństwo ma wymaganie dotyczące wersji aplikacji, a następnie wymaganie dotyczące wersji systemu operacyjnego Android i wymaganie dotyczące wersji poprawki zabezpieczeń systemu Android. Następnie sprawdzane są ostrzeżenia dla wszystkich typów ustawień w tej samej kolejności.

**Dzięki zasadom ochrony aplikacji usługi Intune administratorzy mogą wymagać, aby urządzenia użytkowników końcowych przechodziły pomyślnie testy zaświadczeń rozwiązania SafetyNet firmy Google dla urządzeń z systemem Android. Jak często nowy wynik zaświadczania SafetyNet jest wysyłany do usługi?** <br><br> Nowe określenia usługi Google Play będą zgłaszane do administratora IT w odstępach czasu określonych przez usługę Intune. Częstotliwość wywołań usługi jest ograniczana ze względu na obciążenie, dlatego ta wartość jest przechowywana wewnętrznie i nie można jej konfigurować. Wszelkie akcje skonfigurowane przez administratora IT względem ustawienia zaświadczeń rozwiązania SafetyNet firmy Google będą podejmowane na podstawie ostatniego wyniku zgłoszonego do usługi Intune w czasie warunkowego uruchamiania. W przypadku braku danych dostęp będzie udzielany w zależności od tego, czy zakończyły się niepowodzeniem jakieś inne sprawdzania uruchomienia warunkowego. „Komunikacja dwukierunkowa” usługi Google Play mająca na celu określenie wyników zaświadczania rozpocznie się na zapleczu i będzie monitować użytkownika asynchronicznie, jeśli urządzenie ulegnie awarii. Jeśli dane są przestarzałe, dostęp zostanie zablokowany lub udzielony w zależności od ostatniego zgłoszonego wyniku. Podobnie jak w poprzednim przypadku „komunikacja dwukierunkowa” usługi Google Play mająca na celu określenie wyników zaświadczania rozpocznie się i będzie monitować użytkownika asynchronicznie, jeśli urządzenie ulegnie awarii.

**Dzięki zasadom ochrony aplikacji usługi Intune administratorzy mogą wymagać, aby urządzenia użytkowników końcowych wysyłały sygnały za pomocą interfejsu API Verify Apps firmy Google dla urządzeń z systemem Android. W jaki sposób użytkownicy końcowi mogą włączyć skanowanie aplikacji, aby z tego powodu nie został im zablokowany dostęp?**<br><br> Instrukcje wykonania tego zadania różnią się nieznacznie między urządzeniami. Ogólnie należy przejść do sklepu Google Play i kliknąć pozycję **Moje gry i aplikacje**. Następnie kliknięcie wyniku ostatniego skanowania aplikacji spowoduje wyświetlenie menu Play Protect. Upewnij się, że włączono przełącznik **Skanuj urządzenie pod kątem zagrożeń**.

**Co w rzeczywistości sprawdza interfejs API zaświadczania SafetyNet firmy Google na urządzeniach z systemem Android? Jaka jest różnica między możliwymi do skonfigurowania wartościami opcji „Sprawdź podstawową integralność” i „Sprawdź podstawową integralność i certyfikowane urządzenia”?** <br><br>
Usługa Intune wykorzystuje interfejsy API SafetyNet usługi Google Play Protect do dodania sprawdzeń dotyczących wykrywania rootingu dla urządzeń niezarejestrowanych. Firma Google opracowała ten zestaw interfejsów API dla aplikacji systemu Android i obsługuje go w celu stwierdzenia, czy aplikacje nie są uruchamiane na urządzeniach z odblokowanym dostępem. Ten zestaw został na przykład wprowadzony w aplikacji Android Pay. Ponieważ firma Google nie udostępnia publicznie wszystkich informacji dotyczących procesów zachodzących podczas wykrywania rootingu, oczekujemy, że te interfejsy API wykrywają użytkowników, którzy odblokowali dostęp do konta root na swoich urządzeniach. Dostęp tych użytkowników można następnie zablokować lub wyczyścić ich konta firmowe z aplikacji obsługujących zasady. Opcja „Sprawdź podstawową integralność” informuje o ogólnej integralności urządzenia. W przypadku urządzeń z odblokowanym dostępem do konta root, emulatorów, urządzeń wirtualnych i urządzeń z oznakami naruszenia podstawowa integralność kończy się niepowodzeniem. Opcja „Sprawdź podstawową integralność i certyfikowane urządzenia” informuje o zgodności urządzenia z usługami Google. Tylko sprawdzanie niemodyfikowanych urządzeń, które były certyfikowane przez firmę Google, może zakończyć się powodzeniem. Sprawdzanie zakończy się niepowodzeniem w przypadku następujących urządzeń:

- Urządzenia, w przypadku których test podstawowej integralności kończy się niepowodzeniem
- Urządzenia z odblokowanym programem rozruchowym
- Urządzenia z niestandardowym obrazem systemu/pamięcią ROM
- Urządzenia, w przypadku których producent nie zwrócił się do firmy Google o przeprowadzenie procesu certyfikacji, lub urządzenia, które takiej certyfikacji nie przeszły 
- Urządzenia z obrazem systemu skompilowanym bezpośrednio na podstawie plików źródłowych programu Android Open Source
- Urządzenia z obrazem systemu w wersji beta lub deweloperskiej wersji zapoznawczej

Aby poznać szczegóły techniczne, zobacz [dokumentację firmy Google dotyczącą zaświadczania SafetyNet](https://developer.android.com/training/safetynet/attestation).

**Podczas tworzenia zasad ochrony aplikacji usługi Intune dla urządzeń z systemem Android w sekcji Uruchamianie warunkowe istnieją dwa podobne testy. Czy należy wybrać ustawienie „Zaświadczanie urządzeń SafetyNet”, czy „Urządzenia, w przypadku których wykonano jailbreak lub zapewniono dostęp do konta root”?** <br><br>
Sprawdzania wykonywane przez interfejs API SafetyNet usługi Google Play Protect wymagają, aby użytkownik końcowy był w trybie online co najmniej przez czas wykonywania „komunikacji dwukierunkowej” podczas określania wyników zaświadczania. Jeśli użytkownik końcowy jest w trybie offline, administrator IT może nadal oczekiwać, że wynik będzie egzekwowany dzięki ustawieniu „Urządzenia, w przypadku których wykonano jailbreak lub zapewniono dostęp do konta root”. Jak już wspomniano, jeśli użytkownik końcowy będzie zbyt długo w trybie offline, zacznie obowiązywać opcja „Okres karencji w trybie offline”. Po osiągnięciu wartości czasomierza zostanie zablokowany dostęp do wszystkich danych służbowych do czasu uzyskania dostępu do sieci. Włączenie obu tych ustawień umożliwia utrzymanie w dobrej kondycji urządzeń użytkowników w rozwiązaniu warstwowym, co jest szczególnie ważne, kiedy użytkownicy końcowi uzyskują dostęp do danych służbowych za pomocą urządzeń przenośnych. 

**Ustawienia zasad ochrony aplikacji korzystających z interfejsów API usługi Google Play Protect wymagają działających usług Google Play. Co zrobić, jeśli usługi Google Play nie są dozwolone w lokalizacji, w której może znajdować się użytkownik końcowy?**<br><br>
Zarówno ustawienie „Zaświadczanie urządzeń SafetyNet”, jak i ustawienie „Skanowanie aplikacji pod kątem zagrożeń” do poprawnego działania wymagają określonej przez firmę Google wersji usług Google Play. Ponieważ te ustawienia dotyczą zabezpieczeń, to po ich włączeniu użytkownik końcowy zostanie zablokowany, jeśli nie będzie miał odpowiedniej wersji usług Google Play lub nie będzie miał do nich dostępu. 

## <a name="app-experience-on-ios"></a>Środowisko aplikacji w systemie iOS
**Co się dzieje po dodaniu lub usunięciu odcisku palca lub twarzy na moim urządzeniu?**<br></br>
Zasady ochrony aplikacji w usłudze Intune umożliwiają ograniczenie dostępu do aplikacji tylko do użytkowników mających licencję usługi Intune. Jednym ze sposobów kontrolowania dostępu do aplikacji jest wymaganie korzystania z funkcji Touch ID lub Face ID firmy Apple na obsługiwanych urządzeniach. Usługa Intune implementuje zachowanie, w którym po jakiejkolwiek zmianie w bazie danych biometrycznych urządzenia usługa monituje użytkownika o podanie numeru PIN przy najbliższym osiągnięciu wartości limitu czasu bezczynności. Zmiany w danych biometrycznych obejmują dodawanie i usuwanie odcisku palca lub twarzy. Jeśli użytkownik usługi Intune nie ma ustawionego numer PIN, zostanie poprowadzony przez procedurę konfigurowania numeru PIN usługi Intune.

Intencją tego zachowania jest zapewnienie utrzymywania bezpieczeństwa i ochrony danych organizacji w aplikacji na poziomie aplikacji. Ta funkcja jest dostępna tylko dla systemów iOS i wymaga udziału aplikacji, w których zintegrowany jest zestaw SDK zasad ochrony aplikacji usługi Intune dla systemu iOS w wersji 9.0.1 lub nowszej. Integracja zestawu SDK jest konieczna, aby można było wymusić to zachowanie w aplikacjach docelowych. Ta integracja jest przeprowadzana w sposób ciągły i zależy od zespołów zajmujących się określonymi aplikacjami. Dotyczy to między innymi aplikacji WXP, Outlook, Managed Browser i Yammer.
  
**Mogę otwierać dane służbowe lub szkolne w aplikacjach niezarządzanych przy użyciu rozszerzenia udostępniania systemu iOS, nawet wtedy, gdy zasady transferu danych mają wartość „tylko aplikacje zarządzane” lub „brak aplikacji”. Czy nie powoduje to wycieku danych?**<br></br>
Zasady ochrony aplikacji usługi Intune nie mogą kontrolować rozszerzenia udostępniania systemu iOS bez zarządzania danym urządzeniem. W związku z tym usługa Intune _**szyfruje dane „firmowe” przed ich udostępnieniem poza aplikację**_ . Aby to sprawdzić, spróbuj otworzyć plik „firmowy” poza zarządzaną aplikacją. Plik powinien być zaszyfrowany i jego otwarcie poza zarządzaną aplikacją nie powinno być możliwe.

**W jaki sposób wiele ustawień dostępu zasad ochrony aplikacji usługi Intune skonfigurowanych dla tego samego zestawu aplikacji i użytkowników działa w systemie iOS?**<br></br>
Zasady ochrony aplikacji usługi Intune dla dostępu będą stosowane w określonej kolejności na urządzeniach użytkowników końcowych, kiedy będą próbowali uzyskać dostęp do aplikacji docelowej ze swojego konta firmowego. Ogólnie rzecz biorąc, pierwszeństwo miałoby czyszczenie, następnie blokada, a następnie ostrzeżenie z możliwością odrzucenia. Na przykład jeśli ma zastosowanie do określonego użytkownika/aplikacji, ustawienie minimalnej wersji systemu operacyjnego iOS, które ostrzega użytkownika o konieczności uaktualnienia wersji systemu iOS, zostanie zastosowane po ustawieniu minimalnej wersji systemu operacyjnego iOS, które blokuje dostęp użytkownika. Dlatego w scenariuszu, w którym administrator IT skonfigurował minimalną wersję systemu operacyjnego iOS na 11.0.0.0 i minimalną wersję systemu operacyjnego iOS (tylko ostrzeżenie) na 11.1.0.0, a urządzenie próbujące uzyskać dostęp do aplikacji ma system operacyjny iOS 10, użytkownik końcowy zostałby zablokowany na podstawie bardziej restrykcyjnego ustawienia minimalnej wersji systemu operacyjnego iOS, które powoduje zablokowanie dostępu.

Podczas pracy z różnymi typami ustawień pierwszeństwo ma wymaganie dotyczące wersji zestawu SDK aplikacji usługi Intune, następnie wymaganie dotyczące wersji aplikacji, a potem wymaganie dotyczące wersji systemu operacyjnego iOS. Następnie sprawdzane są ostrzeżenia dla wszystkich typów ustawień w tej samej kolejności. Zaleca się, aby wymaganie dotyczące wersji zestawu SDK aplikacji usługi Intune było konfigurowane tylko na podstawie wskazówek od zespołu produktu usługi Intune dla podstawowych scenariuszy blokowania.


## <a name="see-also"></a>Zobacz także
- [Implementowanie własnego planu dotyczącego usługi Intune](../fundamentals/planning-guide-onboarding.md)
- [Testowanie i sprawdzanie poprawności w usłudze Intune](../fundamentals/planning-guide-test-validation.md)
- [Ustawienia zasad zarządzania aplikacjami mobilnymi systemu Android w usłudze Microsoft Intune](../apps/app-protection-policy-settings-android.md)
- [Ustawienia zasad zarządzania aplikacjami mobilnymi systemu iOS](../apps/app-protection-policy-settings-ios.md)
- [Zasady ochrony aplikacji — odświeżanie zasad](../apps/app-protection-policy-delivery.md)
- [Weryfikowanie zasad ochrony aplikacji](../apps/app-protection-policy-delivery.md)
- [Dodawanie zasad konfiguracji aplikacji dla zarządzanych aplikacji bez rejestracji urządzeń](../apps/app-configuration-policies-managed-app.md)
- [Jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](../fundamentals/get-support.md)