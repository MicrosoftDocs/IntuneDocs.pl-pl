---
title: "Archiwum nowości | Microsoft Intune"
description: "Zarchiwizowane artykuły „Co nowego” dla usługi Microsoft Intune"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: aa8fe81b6a9f6b11bba9c15ede36d9df9cd2e0da
ms.openlocfilehash: 72a2f8026d1a67a3a49111daa9a7b8380b0cb088


---
# <a name="whats-new---archive"></a>Archiwum nowości

Ta strona stanowi archiwum niedawnych ogłoszeń opublikowanych w temacie [Co nowego w usłudze Microsoft Intune](whats-new-in-microsoft-intune.md).

## <a name="october-2016"></a>Październik 2016

### <a name="conditional-access-for-mobile-application-management"></a>Dostęp warunkowy do zarządzania aplikacjami mobilnymi
Będzie możliwe ograniczanie dostępu do usług Exchange Online w taki sposób, aby można go było uzyskać tylko z poziomu aplikacji obsługujących zasady zarządzania aplikacjami mobilnymi usługi Intune, takich jak Outlook. [Ta nowa funkcja](/intune/deploy-use/allow-policy-managed-apps-access-to-o365) doskonale współgra z zasadami zarządzania aplikacjami mobilnymi w usłudze Intune, ponieważ umożliwia blokowanie dostępu do wbudowanych klientów poczty lub innych aplikacji, które nie zostały skonfigurowane za pomocą tych zasad. Dzięki temu użytkownicy mogą korzystać z danych organizacji za pośrednictwem aplikacji, które mogą być chronione przy użyciu funkcji zarządzania aplikacjami mobilnymi w usłudze Intune. Pracę z zasadami zarządzania aplikacjami mobilnymi w usłudze Intune można rozpocząć, korzystając z portalu Azure. Wystarczy znaleźć w bloku „Ustawienia” nową sekcję dotyczącą dostępu warunkowego.

### <a name="conditional-access-for-windows-pcs"></a>Dostęp warunkowy dla komputerów z systemem Windows
Przy użyciu konsoli administracyjnej usługi Intune można teraz tworzyć zasady dostępu warunkowego, uniemożliwiając komputerom z systemem Windows dostęp do usług [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) i [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune). Zasady dostępu warunkowego można też tworzyć w celu blokowania dostępu do aplikacji klasycznych pakietu Office oraz aplikacji uniwersalnych.

### <a name="android-for-work-support"></a>Pomoc techniczna dla programu Android for Work

> [!IMPORTANT]

> Można wdrożyć aplikacje systemu Android for Work z akcją __Wymagane__, ale jeśli grupy usługi Intune zostały zmigrowane do nowego środowiska grup usługi Azure AD, będzie można wdrożyć aplikacje tylko jako __Dostępne__.

Usługa Intune jest teraz częścią programu Android for Work (AfW). W tym miesiącu rozpoczniemy wdrażanie obsługi funkcji programu AfW i będziemy kontynuować te działania w ciągu następnych kilku miesięcy. Należy pamiętać, że wdrożenie dostępnych aplikacji programu AfW korzysta z nowego środowiska grupowania i kierowania. Użytkownicy nowo aprowizowanych kont usługi Intune będą w stanie korzystać z tej funkcji po udostępnieniu im programu AfW.

<!--Existing Intune customers can use this feature in production once their tenant has been migrated. Existing customers are welcome to create a trial Intune account to plan for and test this feature until their tenant has been migrated. Any questions on grouping and targeting timelines, please contact our [migration team](mailto:intunegrps@microsoft.com).-->

[Przeczytaj ogłoszenie firmy Microsoft dotyczące pomocy technicznej dla programu Android for Work w ramach usługi Intune](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

Poniższe tematy dotyczące usługi Intune są nowe lub zostały zaktualizowane o informacje o programie Android for Work:

Dla specjalistów IT:
- [Konfigurowanie programu Android for Work](/intune/deploy-use/set-up-android-for-work)
<!--- [Nathan Bigman's resource access topics]()-->
- [Ograniczanie dostępu poczty e-mail do usługi Exchange Online i nowej usługi Exchange Online w wersji dedykowanej przy użyciu usługi Intune](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
- [Ograniczanie dostępu poczty e-mail do lokalnego programu Exchange i starszej wersji usługi Exchange Online w wersji dedykowanej przy użyciu usługi Intune](/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
- [Ustawienia zasad zgodności programu Android for Work](/intune/deploy-use/afw-compliance-policy-settings-in-microsoft-intune)
- [Jak wdrażać aplikacje programu Android for Work](/intune/deploy-use/android-for-work-apps)
- [Konfigurowanie aplikacji programu Android for Work przy użyciu zasad konfiguracji aplikacji mobilnych](/intune/deploy-use/afw-app-configuration-policy)
- [Ustawienia zasad programu Android for Work](/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)

Dla użytkowników końcowych:
- [Co się dzieje w przypadku tworzenia profilu służbowego](/intune/enduser/what-happens-when-you-create-a-work-profile-android)
- [Tworzenie profilu służbowego i rejestrowanie urządzenia w usłudze Intune](/intune/enduser/create-a-work-profile-and-enroll-your-device-in-intune-android)

### <a name="lookout-integration-to-protect-ios-devices"></a>Integracja usługi Lookout w celu ochrony urządzeń z systemem iOS
W październiku firma Microsoft wprowadzi integrację z rozwiązaniem firmy Lookout do ochrony urządzeń przenośnych w celu zabezpieczenia urządzeń przenośnych z systemem iOS dzięki wykrywaniu złośliwego oprogramowania, ryzykownych aplikacji i innych zagrożeń na urządzeniach. Rozwiązanie firmy Lookout pomaga w określeniu poziomu zagrożenia, który można skonfigurować. W usłudze Intune można utworzyć regułę zasad zgodności w celu określania zgodności urządzeń na podstawie oceny ryzyka uzyskanej z rozwiązania firmy Lookout. Za pomocą zasad dostępu warunkowego można umożliwić lub zablokować dostęp do zasobów firmy w zależności od stanu zgodności danego urządzenia.

W przypadku użytkowników końcowych korzystających z niezgodnych urządzeń z systemem iOS zostanie wyświetlony monit o przeprowadzenie rejestracji. Aby uzyskać dostęp do zasobów firmy, użytkownicy będą musieli zainstalować aplikację Lookout for Work na swoich urządzeniach, uaktywnić ją i podjąć środki zaradcze dotyczące zagrożeń raportowanych przez aplikację Lookout for Work. Dowiedz się, jak [skonfigurować i wdrożyć aplikację Lookout for Work](/intune/deploy-use/configure-and-deploy-lookout-for-work-apps).
<!--TFS 1319493-->

<!--### New Microsoft Intune Company Portal available for Windows 10 devices
Microsoft is releasing a new [Microsoft Intune Company Portal for Windows 10 devices](https://go.microsoft.com/fwlink/?linkid=830663). This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store.-->

### <a name="intune-app-wrapping-tool-for-android"></a>Narzędzie opakowujące aplikacje usługi Intune dla systemu Android
Przy użyciu narzędzia opakowującego aplikacje usługi Intune możesz włączyć stosowanie zasad zarządzania aplikacjami mobilnymi usługi Intune w używanych aplikacjach. Pomoc techniczna dotycząca zasad zarządzania aplikacjami mobilnymi usługi Intune bez konieczności rejestrowania urządzeń jest już dostępna.

### <a name="manage-printing-from-apps-managed-using-mam-policies"></a>Zarządzanie drukowaniem z aplikacji zarządzanych przy użyciu zasad zarządzania aplikacjami mobilnymi
Możesz teraz uniemożliwić drukowanie firmowych danych z aplikacji, dla których obowiązują zasady zarządzania aplikacjami mobilnymi. To ustawienie jest dostępne w [Portalu Azure](/Intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) i jest obsługiwane zarówno przez urządzenia z systemem [iOS](/Intune/deploy-use/ios-mam-policy-settings), jak i z systemem [Android](/Intune/deploy-use/android-mam-policy-settings).
<!--TFS 1014328-->

### <a name="support-for-fingerprints-on-android-devices"></a>Obsługa odcisków palców na urządzeniach z systemem Android
Zasady zarządzania aplikacjami mobilnymi systemu Android teraz umożliwiają użytkownikom uzyskanie dostępu do aplikacji za pomocą odcisku palca zamiast wpisywania kodu PIN. Zobacz to i inne [ustawienia zasad zarządzania aplikacjami mobilnymi systemu Android, klikając tutaj](/Intune/deploy-use/android-mam-policy-settings).

### <a name="notices"></a>Uwagi

__Zgodność systemów Android i Samsung KNOX z usługą Intune__ Niektóre modele telefonu Samsung Galaxy Ace nie mogą być zarządzane przez usługę Intune jako urządzenia Samsung KNOX. Zamiast tego po zarejestrowaniu tych urządzeń w usłudze Intune będą one zarządzane jako standardowe urządzenia z systemem Android.

Numery modeli, których dotyczy to zagadnienie:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

Ani Ty ani użytkownicy końcowi nie musicie wykonywać żadnych dalszych czynności. Aby uzyskać więcej informacji, odwiedź witrynę sieci Web [Samsung KNOX](https://www.samsungknox.com).

__Aplikacja Portal firmy dla systemu Windows 8 jest przestarzała; pomoc techniczna dla platform Windows Phone 8 i Windows RT zostanie wkrótce wycofana__ Począwszy od października 2016 r. usługa Microsoft Intune wstrzyma obsługę aplikacji Portal firmy dla systemu Windows 8. Z usługi Microsoft Intune zostanie również wycofana pomoc techniczna dla platform Windows Phone 8 i Windows RT. W rezultacie nie będzie można zarejestrować ani zaktualizować żadnych urządzeń z systemem Windows Phone 8 lub Windows RT.

Można będzie nadal zarządzać urządzeniami z systemami Windows Phone 8, Windows RT i Windows 8, które są już zarejestrowane. Zaktualizuj urządzenia z systemami Windows 8 i Windows Phone 8 do systemów Windows 8.1 i Windows Phone 8.1 oraz skorzystaj z odpowiedniej aplikacji Portal firmy dla systemu Windows 8.1 lub Windows Phone 8.1, aby kontynuować bez zakłóceń dystrybucję aplikacji na tych urządzeniach.

Począwszy od listopada 2016 roku firma Microsoft wycofa pomoc techniczną dla aplikacji Portal firmy systemu Windows Phone 8.
<!--TFS 1255391-->

### <a name="whats-coming"></a>Wkrótce

__Nowy Portal firmy w usłudze Microsoft Intune dostępny dla urządzeń z systemem Windows 10__ Firma Microsoft udostępnia nowy Portal firmy w usłudze Microsoft Intune dla urządzeń z systemem Windows 10. Ta aplikacja, korzystająca z nowego uniwersalnego formatu systemu Windows 10, będzie udostępniać użytkownikom zaktualizowane środowisko obsługi w aplikacji oraz zapewniać identyczne środowisko obsługi na wszystkich urządzeniach z systemem Windows 10 — komputerach osobistych i urządzeniach przenośnych — oferując ten sam zestaw funkcji, który jest dostępny dzisiaj.

Nowa aplikacja będzie również umożliwiać użytkownikom korzystanie z dodatkowych funkcji platformy, takich jak rejestracja jednokrotna (SSO) i uwierzytelnianie oparte na certyfikatach, na urządzeniach z systemem Windows 10. Aplikacja zostanie udostępniona jako uaktualnienie istniejących instalacji Portalu firmy w systemie Windows 8.1 i Portalu firmy w systemie Windows Phone 8.1 ze Sklepu Windows. Aby uzyskać szczegółowe informacje, przejdź do strony [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).
<!--TFS 1016502-->

## <a name="september-2016"></a>Wrzesień 2016
### <a name="new-features-announcements-and-information"></a>Nowe funkcje, anonsy i informacje
* [Dostęp warunkowy w systemie Windows](#windows-conditional-access)
* [Obsługa systemu iOS 10](#ios-10-support)
* [Narzędzie opakowujące aplikacje obsługuje zarządzanie aplikacjami mobilnymi bez rejestrowania urządzeń dla systemów Android i iOS](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [Rozpoczęte we wrześniu przejście grup usługi Intune do grup usługi Azure Active Directory](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Integracja aplikacji Lookout w celu ochrony urządzeń z systemem Android](#lookout-integration-to-protect-android-devices)
* [Aktualizacje aplikacji Portal firmy dla systemów Android, iOS i Windows](#company-portal-updates)
* [Słownik dotyczący usługi Intune](#intune-glossary)
* [Wkrótce](#whats-coming)

### <a name="windows-conditional-access"></a>Dostęp warunkowy w systemie Windows
Przy użyciu konsoli administracyjnej usługi Intune można teraz tworzyć zasady dostępu warunkowego, uniemożliwiając komputerom z systemem Windows dostęp do usług Exchange Online i SharePoint Online. Zasady dostępu warunkowego można też tworzyć w celu blokowania dostępu do aplikacji klasycznych pakietu Office oraz aplikacji uniwersalnych.

### <a name="ios-10-support"></a>Obsługa systemu iOS 10
Istniejące scenariusze dotyczące zarządzania urządzeniami przenośnymi i aplikacjami mobilnymi w usłudze Intune mają zastosowanie w systemie iOS 10. Aby uzyskać porady, zobacz [Blog zespołu pomocy technicznej usługi Intune](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/).

### <a name="app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios"></a>Narzędzie opakowujące aplikacje obsługuje zarządzanie aplikacjami mobilnymi bez rejestrowania urządzeń dla systemów Android i iOS
Narzędzie opakowujące aplikacje dostępne w ramach usługi Intune to narzędzie wiersza polecenia służące do obsługi aplikacji biznesowych do zarządzania aplikacjami mobilnymi w usłudze Intune dla systemów iOS i Android. Jest to najprostszy sposób uwzględnienia w swojej aplikacji zestawu SDK do zarządzania aplikacjami mobilnymi w usłudze Intune. Dzięki temu aplikacja może wymuszać stosowanie zasad zarządzania aplikacjami mobilnymi wdrożonych za pomocą usługi Intune. Za pomocą zasad zarządzania aplikacjami mobilnymi można:

1. Szyfrować dane aplikacji.
2. Wymagać wprowadzania numeru PIN podczas uruchamiania aplikacji przez pracownika przetwarzającego informacje.
3. Zezwalać aplikacji na przesyłanie danych tylko do innych aplikacji zarządzanych.
4. Uniemożliwić aplikacji tworzenie kopii zapasowej danych w systemie Android oraz usługach iTunes i iCloud.
5. Zezwalać na wycinanie, kopiowanie i wklejanie wyłącznie do oraz z innych aplikacji zarządzanych.

Publiczna wersja zapoznawcza zaktualizowanego narzędzia opakowującego aplikacje w usłudze Intune obsługuje teraz zarządzanie aplikacjami mobilnymi bez rejestrowania urządzeń w wewnętrznych aplikacjach biznesowych w systemach iOS i Android. To znaczy, że użytkownicy końcowi nie muszą rejestrować swoich urządzeń za pomocą usługi Intune w celu używania aplikacji biznesowych obsługujących zarządzanie aplikacjami mobilnymi.

Każdy może wypróbować publiczną wersję zapoznawczą i przeczytać pomocną dokumentację. Wystarczy skorzystać z materiałów udostępnionych na koncie msintuneappsdk w usłudze GitHub:

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Przed zainstalowaniem i użyciem wersji wstępnej narzędzia opakowującego aplikacje w usłudze Microsoft Intune dla systemów Android i iOS trzeba:

* Zapoznać się z postanowieniami licencyjnymi firmy Microsoft dotyczącymi wersji wstępnej narzędzia opakowującego aplikacje w usłudze Microsoft Intune dla systemów Android i iOS.
* Wydrukować i zachować kopię postanowień licencyjnych. Pobranie i używanie wersji wstępnej narzędzia opakowującego aplikacje w usłudze Microsoft Intune dla systemu Android jest równoznaczne z akceptacją postanowień licencyjnych. Jeśli użytkownik nie akceptuje niniejszych postanowień, nie może używać tego oprogramowania.
<!---TFS 1235607--->

### <a name="intune-groups-begin-transitioning-to-azure-active-directory-in-september"></a>Rozpoczęte we wrześniu przejście grup usługi Intune do grup usługi Azure Active Directory
W przypadku niektórych nowych kont usługi Intune będą używane grupy zabezpieczeń usługi Azure Active Directory, a nie grupy użytkowników usługi Intune. To, że praca odbywa się z grupami zabezpieczeń, jest sygnalizowane obecnością na stronie grup portalu Intune linku do portalu zarządzania Azure.

### <a name="lookout-integration-to-protect-android-devices"></a>Integracja aplikacji Lookout w celu ochrony urządzeń z systemem Android
Firma Microsoft przeprowadza integrację z rozwiązaniem firmy Lookout przeznaczonymi do ochrony urządzeń przenośnych w celu zabezpieczenia urządzeń przenośnych z systemem Android przez wykrywanie na urządzeniach złośliwego oprogramowania, ryzykownych aplikacji i innych zagrożeń. Rozwiązanie firmy Lookout pomaga w określeniu poziomu zagrożenia, który można skonfigurować. W usłudze Intune można utworzyć regułę zasad zgodności w celu określania zgodności urządzeń na podstawie oceny ryzyka uzyskanej z rozwiązania firmy Lookout. Za pomocą zasad dostępu warunkowego można umożliwić lub zablokować dostęp do zasobów firmy w zależności od stanu zgodności danego urządzenia.

W przypadku użytkowników końcowych korzystających z niezgodnych urządzeń zostanie wyświetlony monit o zarejestrowanie urządzeń. Aby uzyskać dostęp do zasobów firmy, użytkownicy będą musieli zainstalować aplikację Lookout for Work na urządzeniach z systemem Android, uaktywnić ją i podjąć środki zaradcze dotyczące zagrożeń zgłoszonych w aplikacji Lookout for Work. Aby uzyskać więcej informacji, zobacz [Ograniczanie dostępu do zasobów firmy oparte na ryzyku dotyczącym urządzeń, sieci i aplikacji](restrict-access-based-on-device-network-app-risk.md).


### <a name="company-portal-updates"></a>Aktualizacje Portalu firmy

__Android__

<p style="margin-left: 40px">**Dodanie obszaru „Powiadomienia” do Portalu firmy dla systemu Android**<br/>
<p style="margin-left: 40px">Na stronie głównej Portalu firmy dla systemu Android dodano nową ikonę Powiadomienia. Naciśnięcie tej ikony powoduje przejście na stronę Powiadomienia — przedstawia ona użytkownikowi końcowemu wszystkie elementy, które wymagają uwagi w aplikacji Portal firmy, takie jak brak zgodności urządzeń, aktualizacja rejestracji i aktywacja rejestracji. W aplikacji Portal firmy dla systemu iOS obszar powiadomień jest już dostępny. W wyniku wprowadzenia strony Powiadomienia nie będzie widoczna strona Konfigurowanie dostępu do zasobów firmy po uruchomieniu lub wznowieniu pracy w Portalu firmy, jeśli urządzenie zostało już zarejestrowane. W przypadku tworzenia własnych wskazówek dla użytkowników końcowych warto zaktualizować dokumentację, tak aby uwzględniała tę zmianę. Zaktualizowane zrzuty ekranu można znaleźć [tutaj](https://aka.ms/androidcpupdate).  

__iOS__
<p style="margin-left: 40px">**Zmiany w obsłudze aplikacji Portal firmy dla systemu iOS**<br/>
<p style="margin-left: 40px">Wszyscy użytkownicy aplikacji Portal firmy usługi Microsoft Intune dla systemu iOS muszą obecnie używać jej najnowszej wersji. Nowi użytkownicy mogą pobrać tylko najnowszą wersję, a bieżący użytkownicy muszą przeprowadzić aktualizację do najnowszej wersji. Najnowsza wersja aplikacji wymaga systemu iOS 8.0 lub nowszego, dlatego urządzenia ze starszymi wersjami systemu iOS nie mogą korzystać z portalu firmy ani rejestrować się do czasu ich zaktualizowania do systemu iOS 8.0 lub nowszego oraz zaktualizowania aplikacji Portal firmy do najnowszej wersji. Zarejestrowane urządzenia z wersjami systemu iOS poniżej 8.0 będą nadal zarządzane i wyświetlane w konsoli administracyjnej usługi Intune.
<!---TFS 1283165--->

<p style="margin-left: 40px">**Ulepszenia w sposobie uzyskiwania aplikacji przez użytkowników końcowych systemu iOS**<br/>
<p style="margin-left: 40px">Wprowadzono następujące zmiany w odniesieniu do kafelków aplikacji w aplikacji Portal firmy dla systemu iOS. Zmiany mają na celu umożliwienie przechodzenia do różnych widoków w obrębie jednej lokalizacji — witryny sieci Web Portal firmy — dla wszystkich swoich aplikacji. Ograniczenia firmy Apple uniemożliwiają wyświetlanie w aplikacji Portal firmy aplikacji biznesowych oraz zarządzanych ze sklepu z aplikacjami, w związku z czym użytkownicy muszą korzystać z różnych widoków, aby znaleźć wszystkie swoje aplikacje.

<p style="margin-left: 40px">Kafelek **Aplikacje firmowe** pozwalał poprzednio przejść do listy wszystkich aplikacji na karcie WSZYSTKIE w witrynie sieci Web Portal firmy. Jego działanie nie ulegnie zmianie. Nazwa kafelka została zmieniona na **Wszystkie aplikacje**.

<p style="margin-left: 40px">Kafelek **Inne aplikacje** pozwalał poprzednio przejść do widoku zawierającego wszystkie aplikacje, których wyświetlanie w aplikacji Portal firmy jest możliwe zgodnie z zasadami firmy Apple. Nazwa kafelka została zmieniona na **Polecane aplikacje**, a jego naciśnięcie spowoduje przejście na kartę POLECANE w witrynie sieci Web Portal firmy.

<p style="margin-left: 40px">Kafelek **Kategorie** pozwalał poprzednio przejść w ramach aplikacji Portal firmy do widoku zawierającego kategorie aplikacji. Nazwa kafelka nie uległa zmianie, ale jego naciśnięcie będzie teraz powodować przejście na kartę KATEGORIE w witrynie sieci Web Portal firmy. Zaktualizowane zrzuty ekranu można znaleźć [tutaj](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
  <!---TFS 1317133--->

<p style="margin-left: 40px">**Wyświetlanie monitu o instalację aplikacji Managed Browser dla systemu iOS, jeśli oprogramowanie IT Pro określiło taki wymóg dla aplikacji**<br/>
<p style="margin-left: 40px">Ustawienie składnika Web Clip w taki sposób, aby otwierał się tylko w zarządzanej przeglądarce w przypadku, gdy zarządzana przeglądarka nie została zainstalowana na urządzeniu, spowoduje, że aplikacja Portal firmy na urządzeniu wyświetli monit o zainstalowanie zarządzanej przeglądarki przed zainstalowaniem składnika Web Clip.
  <!---TFS 1228570--->

__Windows__
<p style="margin-left: 40px">**Dodanie przycisku wysyłania opinii do aplikacji Portal firmy dla systemu Windows Phone 8.1**<br/>
<p style="margin-left: 40px">Aplikacja Portal firmy dla systemu Windows Phone 8.1 umożliwia użytkownikom końcowym przesyłanie opinii o aplikacji przy użyciu nowego przycisku „wyślij opinię”. Aby znaleźć przycisk, użytkownicy muszą nacisnąć oznaczone wielokropkiem menu w prawej dolnej części ekranu aplikacji Portal firmy, a następnie nacisnąć pozycję **wyślij opinię**. Zebrane anonimowe opinie pomogą firmie Microsoft w ulepszaniu środowiska aplikacji Portal firmy dla użytkowników.
<!---TFS 1317806--->

### <a name="intune-glossarybr"></a>Słownik dotyczący usługi Intune</br>
Dodano nowy [temat w słowniku](https://docs.microsoft.com/intune/understand-explore/intune-glossary) do biblioteki, aby ułatwić zrozumienie niektórych pojęć używanych w produkcie Intune.

## <a name="august-2016"></a>Sierpień 2016
### <a name="app-management"></a>Zarządzanie aplikacjami
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

__Aplikacje ukrywane i wyświetlane dla systemu iOS 9.3__ Dla urządzeń z systemem iOS 9.3 lub nowszym w ogólnych zasadach konfiguracji systemu iOS można używać listy aplikacji ukrywanych i wyświetlanych, aby:
- Określić listę aplikacji, które będą ukryte dla użytkowników. Użytkownicy nie będą mogli wyświetlać ani uruchamiać tych aplikacji.
- Określić listę aplikacji, które użytkownicy mogą wyświetlać i uruchamiać. Użytkownicy nie będą mogli wyświetlać ani uruchamiać żadnych innych aplikacji.

Dla tych list można określić zarówno aplikacje wdrożone, jak i wbudowane aplikacje dla systemu iOS, takie jak Wiadomości i Notatki. Aby uzyskać więcej informacji, zobacz [Ustawienia zasad systemu iOS w usłudze Microsoft Intune]( https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune)
<!---TFS 1279009 checked--->
__Zasady aplikacji dozwolonych i zablokowanych dla urządzeń z systemem Samsung KNOX__ Dla urządzeń z systemem Samsung KNOX można teraz skonfigurować zasady niestandardowe umożliwiające utworzenie jednej z następujących list:
- Lista aplikacji, których uruchamianie na urządzeniu jest zablokowane. Nawet po zainstalowaniu aplikacji zdefiniowanej na liście zablokowanych nie będzie jej można uaktywnić na urządzeniu.
- Lista aplikacji, które użytkownicy urządzenia mogą instalować ze sklepu klepu Google Play. Nie będzie można instalować żadnych innych aplikacji ze sklepu.

Tych ustawień można używać tylko w przypadku urządzeń z systemem Samsung KNOX.
Aby uzyskać więcej informacji, zobacz [Użycie niestandardowych zasad do zezwalania na aplikacje i blokowania ich na urządzeniach z systemem Samsung KNOX]( custom-policy-to-allow-and-block-samsung-knox-apps.md).
<!---TFS 1311629 checked --->
__Nowe aplikacje zgodne z zasadami zarządzania aplikacjami mobilnymi__ Aplikacja usługi Yammer dla systemów [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) i [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) jest teraz zgodna z [zasadami zarządzania aplikacjami mobilnymi usługi Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), bez względu na to, czy urządzenie jest zarejestrowane.

Pełna lista aplikacji zgodnych z zasadami MAM jest dostępna w witrynie [partnerów aplikacji usługi Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners).
<!--- TFS 1252335 & 1252336 checked--->


<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

__Aplikacje Intune Viewer__ Wraz z wydaniem nowej aplikacji RMS sharing zostaną usunięte następujące aplikacje Intune Viewer, począwszy od sierpnia 2016 roku:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer dla systemu Android ze sklepu Google Play

Zalecamy, aby zamiast korzystania z aplikacji Intune Viewer używać nowej [aplikacji do zarządzania prawami (RMS sharing) dla systemu Android](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), co pozwala na wdrożenie jednej aplikacji zamiast trzech osobnych aplikacji w celu bezpiecznego przeglądania plików firmy na urządzeniach z systemem Android. Gdy aplikacja Intune Viewer nie będzie już obsługiwana, zostanie usunięta ze sklepu Google i nie będzie dostępna do użycia w przyszłości.

### <a name="device-management"></a>Zarządzanie urządzeniami
__Obsługa systemu Android 7.0__ Usługa Intune zapewnia obsługę „od dnia 0” nadchodzącego systemu operacyjnego Android 7.0 dla urządzeń przenośnych.
<!---TFS 1262053--->
### <a name="google-removal-of-remote-passcode-reset-capability-on-android-70-devices"></a>Usunięcie przez Google możliwości zdalnego resetowania kodu dostępu na urządzeniach z systemem Android 7.0
Google usuwa możliwość zdalnego resetowania kodu dostępu urządzeń z systemem Android 7.0 przez administratorów IT i użytkowników końcowych. Wcześniej administratorzy IT mogli zdalnie zresetować kod dostępu użytkownika, a użytkownicy końcowi mogli resetować swoje kody dostępu z witryny sieci Web Portalu firmy.



### <a name="company-portal-updates"></a>Aktualizacje Portalu firmy
__Witryna sieci Web Portal firmy__
- **Link opinii z Portalu firmy do firmy Microsoft** <br/>
Witryna sieci Web Portalu firmy udostępnia użytkownikom końcowym nowy link „Opinia” u dołu strony, który użytkownicy mogą wybrać, aby wysłać do firmy Microsoft opinię dotyczącą ich wizyty w witrynie. Zebrane, anonimowe opinie pomogą firmie Microsoft w ulepszaniu środowiska witryny sieci Web Portalu firmy dla użytkowników.
<!--- TFS 1313657 checked--->

__iOS__
- **Minimalna wersja systemu iOS dla przeglądarki Managed Browser została zaktualizowana do 8.0**<br/>
Aplikacja Microsoft Intune Managed Browser dla systemu iOS została zaktualizowana w celu obsługiwania urządzeń z systemem iOS 8.0 lub nowszym. Podczas gdy urządzenia z systemem iOS 7.1 wciąż mogą używać istniejącej aplikacji Managed Browser, należy zachęcać użytkowników do aktualizacji systemu iOS do wersji 8.0 lub nowszej, aby mogli w pełni skorzystać z najnowszych funkcji przeglądarki Managed Browser.  
<!---TFS 1313253 checked--->

### <a name="whats-coming"></a>Wkrótce
__Przejście grup usługi Intune do grup usługi Azure Active Directory rozpocznie się we wrześniu 2016 r.__ Usługa Intune wprowadza nową funkcjonalność zarządzania grupami, która używa grup zabezpieczeń usługi Azure Active Directory (AAD) jako grupy użytkowników i urządzeń w usłudze Intune. Te grupy będą używane do zarządzania grupami, wdrażania zasad i wdrażania profilów **po wprowadzeniu nowego portalu administracyjnego usługi Intune używającej platformy Azure**.

Nowe środowisko zlikwiduje konieczność duplikowania grup między usługami, **pozwoli na dostęp do nowych funkcji grup usługi Azure Active Directory — wersja Premium (AADP)** i zapewni możliwość rozszerzenia przy użyciu programów PowerShell i Graph. Ujednolici to również środowisko administrowania grupami w zarządzaniu mobilnością w przedsiębiorstwie.

W celu umożliwienia przejścia do grup zabezpieczeń środowisko **bieżącej konsoli administracyjnej** zostanie zmodyfikowane. **Te zmiany i sposób korzystania z grup zabezpieczeń usługi AAD zostaną zarejestrowane w dokumentacji usługi Intune**.

Nowi klienci usługi Intune zobaczą **zmiany grup zabezpieczeń przed bieżącymi dzierżawcami**.

Oprócz zmian w zarządzaniu grupami **zostaną wycofane następujące funkcje**:
- Wykluczanie członków lub grup podczas tworzenia nowej grupy
- Grupy **Użytkownicy niezgrupowani** i **Urządzenia niezgrupowane**
- **Zarządzanie grupami** w roli administratora usługi
- Niestandardowe alerty bazujące na grupach dla reguł powiadomień
- Przestawianie z grupami w raportach
<!--- TFS 1295329--->

__Dodanie obszaru „Powiadomienia” do Portalu firmy dla systemu Android__ We wrześniu udostępnimy aktualizację Portalu firmy dla systemu Android, która wprowadzi nową ikonę **Powiadomienia** na stronie głównej. Naciśnięcie tej ikony spowoduje przejście na stronę **Powiadomienia**, która przedstawia użytkownikowi końcowemu wszystkie elementy, które wymagają uwagi w aplikacji Portal firmy, takie jak brak zgodności urządzeń, aktualizacja rejestracji i aktywacja rejestracji. Jeśli używasz również aplikacji Portal firmy dla systemu iOS, powiadomienia masz już widoczne. Wraz z wprowadzeniem strony **Powiadomienia** nie będzie widoczna strona **Konfigurowanie dostępu do zasobów firmy** po uruchomieniu lub wznowieniu pracy w Portalu firmy dla systemu Android, jeśli urządzenie zostało już zarejestrowane. Wiemy, że wiele osób utworzyło wskazówki dla użytkowników końcowych i doceniają wcześniejsze powiadomienie, gdy wskazówki lub zrzuty ekranu mogą wymagać aktualizacji. Prosimy więc o takie zaktualizowanie dokumentacji, aby odzwierciedlała ona nadchodzące zmiany w środowisku. Zaktualizowane zrzuty ekranu można znaleźć tutaj: https://aka.ms/androidcpupdate.  

### <a name="service-deprecation"></a>Wycofywanie usług
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **Zmiany w obsłudze aplikacji Portal firmy dla systemu iOS**<br/>
We wrześniu wszyscy użytkownicy aplikacji Portal firmy usługi Microsoft Intune dla systemu iOS będą musieli używać jej najnowszej wersji. Nowi użytkownicy będą mogli pobrać tylko najnowszą wersję, a bieżący użytkownicy będą musieli przeprowadzić aktualizację do najnowszej wersji. Najnowsza wersja aplikacji wymaga systemu iOS 8.0 lub nowszego, dlatego urządzenia ze starszymi wersjami systemu iOS nie będą mogły korzystać z portalu firmy ani rejestrować się do czasu ich zaktualizowania do systemu iOS 8.0 lub nowszego oraz zaktualizowania aplikacji Portal firmy do najnowszej wersji. Zarejestrowane urządzenia z wersjami systemu iOS poniżej 8.0 będą nadal zarządzane i wyświetlane w konsoli administracyjnej usługi Intune.  

- **Minimalna wersja systemu iOS dla przeglądarki Managed Browser została zaktualizowana do 8.0**<br/>
W sierpniu dział usługi Intune opublikuje zaktualizowaną aplikację Microsoft Intune Managed Browser dla systemu iOS, która będzie obsługiwana tylko na urządzeniach z systemem iOS 8.0 lub nowszym. Podczas gdy urządzenia z systemem iOS 7.1 wciąż będą mogły używać istniejącej aplikacji Managed Browser, należy zachęcać użytkowników do aktualizacji systemu iOS do wersji 8.0 lub nowszej, aby mogli w pełni skorzystać z najnowszych funkcji przeglądarki Managed Browser.  
<!---TFS 1313253--->

- **Aplikacje Portal firmy dla systemu Windows 8 i Windows Phone 8 zostaną wycofane we wrześniu 2016 r.** <br/>
Począwszy od września 2016 roku w usłudze Microsoft Intune zakończy się obsługa aplikacji Portal firmy Microsoft Intune dla platform Windows Phone 8 i Windows 8. Zaktualizuj urządzenia do systemów Windows 8.1 i Windows Phone 8.1 oraz skorzystaj z odpowiedniej aplikacji Portal firmy dla systemu Windows 8.1 lub Windows Phone 8.1, aby kontynuować dystrybucję aplikacji na tych urządzeniach.
<!---TFS 1255391--->

<!--- - **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

    Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

    In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

    In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

    The preliminary timeline for this change is as follows:
    - In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
    - Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
    - Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

--->

## <a name="july-2016"></a>Lipiec 2016
### <a name="app-management"></a>Zarządzanie aplikacjami

__Poprawa aktualizowania profilu aprowizacji aplikacji__ Biznesowe aplikacje mobilne systemu Apple iOS są tworzone za pomocą dołączonego profilu aprowizacji, a ich kod jest podpisywany przy użyciu certyfikatu. Gdy aplikacja jest uruchamiana na urządzeniu z systemem iOS, system iOS potwierdza integralność aplikacji systemu iOS i wymusza zasady zdefiniowane przez profil aprowizacji.

Certyfikat podpisywania przedsiębiorstwa używany do podpisywania aplikacji jest zwykle ważny przez 3 lata. Profil aprowizacji wygasa jednak po 1 roku. Dzięki tej aktualizacji usługa Intune udostępnia narzędzia umożliwiające aktywne wdrażanie nowych zasad profilu aprowizacji na urządzeniach, na których znajdują się aplikacje bliskie wygaśnięcia, ale certyfikat jest nadal ważny. Aby uzyskać więcej informacji, zobacz [Use iOS mobile provisioning profile policies to keep your line of business apps up to date](/intune/deploy-use/ios-mobile-app-provisioning-profiles) (Używanie zasad profilów aprowizacji aplikacji mobilnych systemu iOS, aby zapewnić aktualność aplikacji).
<!--- TFS 1280247--->

__Dostępny jest zestaw SDK platformy Xamarin dla aplikacji Intune__ Składnik Xamarin zestawu SDK aplikacji Intune umożliwia włączenie funkcji zarządzania aplikacjami mobilnymi usługi Intune w aplikacjach mobilnych dla systemów iOS i Android skompilowanych za pomocą platformy Xamarin. Składnik można znaleźć w [sklepie Xamarin](https://components.xamarin.com/view/Microsoft.Intune.MAM) lub na [stronie Microsoft Intune Github](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

### <a name="device-management"></a>Zarządzanie urządzeniami
__Zwiększenie limitów rejestracji urządzeń__ Usługa Intune zwiększyła maksymalny limit rejestracji konfigurowalnych urządzeń z 5 do 15 urządzeń dla każdego użytkownika.
<!---TFS 1289896 --->

__Integracja programu TeamViewer dla komputerów z systemem Windows z uruchomionym oprogramowaniem klienckim usługi Intune__
 Integracja oprogramowania [TeamViewer](https://www.teamviewer.com) dla komputerów z systemem Windows z uruchomionym oprogramowaniem klienckim usługi Intune umożliwia ustanawianie sesji pomocy zdalnej dla komputerów z systemem Windows w celu wsparcia działu pomocy technicznej użytkowników końcowych. Dotyczy to systemów Windows 7, 8, 8.1 i Windows 10. Aby uzyskać więcej informacji, zobacz [Typowe zadania związane z zarządzaniem komputerem z systemem Windows za pomocą klienta komputerowego usługi Microsoft Intune](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

### <a name="company-portal-updates"></a>Aktualizacje Portalu firmy

__Witryna sieci Web Portal firmy__
- **Poprawione środowisko użytkownika końcowego podczas rejestrowania urządzeń z systemem Windows**<br/>
Jeśli korzystasz z dostępu warunkowego, procedury rejestracji systemów Windows 8.1, Windows 10 Desktop i Windows 10 Mobile zostały uproszczone w witrynie internetowej Portalu firmy. Użytkownicy zobaczą teraz osobne kroki „Rejestrowanie urządzeń” i „Workplace Join”, co ułatwi sprawdzenie stanu urządzenia i ukończenie procesu po błędzie narzędzia Workplace Join (WPJ). Oddzielne kroki powinny również uprościć proces rozwiązywania problemów dla administratorów IT. Wcześniej, gdy użytkownik końcowy próbował zarejestrować urządzenie i wszystkie kroki rejestracji kończyły się pomyślnie z wyjątkiem użycia narzędzia WPJ, zarejestrowane urządzenie nie było wyświetlane na liście urządzeń do zidentyfikowania przez użytkowników, co było mylące.

__Android__
- **Aplikacja Portal firmy dla systemu Android**<br/>
Jeśli użytkownicy końcowi systemu Android widzą komunikat o błędzie stwierdzający brak wymaganego certyfikatu na urządzeniu, mogą nacisnąć przycisk „Jak rozwiązać ten problem”, aby uzyskać [kroki](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) wymagane do zainstalowania brakującego certyfikatu. Jeśli użytkownicy wykonają podane kroki, ale wciąż widzą komunikat o braku certyfikatu, proszeni są o kontakt z administratorem IT i podanie tego [linku](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), który zawiera kroki umożliwiające administratorom IT usunięcie problemu z certyfikatem.

- **Ograniczenie instalacji aplikacji ładowanych bezpośrednio do zarejestrowanych urządzeń**<br/>
Na urządzeniach z systemem Android nie można już instalować aplikacji za pośrednictwem witryny internetowej Portalu firmy, chyba że zostały zarejestrowane w usłudze Intune przy użyciu aplikacji Portal firmy usługi Intune dla systemu Android.
<!---TFS 1299082--->

__iOS__
- **Zmiany w kontach menedżerów rejestracji urządzeń w aplikacji Portal firmy dla systemu iOS**<br/>
Aby zwiększyć wydajność i skalę, usługa Intune nie pokazuje już wszystkich urządzeń menedżerów rejestracji urządzeń (DEM) w okienku **Moje urządzenia** aplikacji Portal firmy dla systemu iOS. Wyświetlane jest tylko urządzenie lokalne, na którym uruchomiono aplikację, o ile zostało zarejestrowane przez aplikację Portal firmy.

Użytkownik menedżera rejestracji urządzeń może wykonywać działania na urządzeniu lokalnym, ale zdalne zarządzanie innymi zarejestrowanymi urządzeniami można przeprowadzać tylko z konsoli administracyjnej usługi Intune. Dodatkowo w usłudze Intune wycofano używanie kont menedżera rejestracji urządzeń z programem Device Enrollment Program firmy Apple i narzędziem Apple Configurator. Obie te metody rejestracji obsługują już rejestrację bez użytkowników dla współużytkowanych urządzeń z systemem iOS.

Kont menedżera rejestracji urządzeń należy używać tylko w przypadku braku dostępności rejestracji bez użytkowników dla współużytkowanych urządzeń. Więcej informacji zawiera temat [Rejestrowanie urządzeń należących do firmy przy użyciu menedżera rejestracji urządzeń w usłudze Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### <a name="change-of-names-for-windows-features"></a>Zmiana nazw funkcji systemu Windows
- Usługa [Microsoft Passport for Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) ma teraz nazwę **Windows Hello dla firm**.
- [Ochrona danych przedsiębiorstwa](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) ma teraz nazwę **Windows Information Protection**.

## <a name="june-2016"></a>Czerwiec 2016
### <a name="intune-service-health"></a>Kondycja usługi Intune
Informacje o kondycji usługi Intune zostały przeniesione do centralnej lokalizacji z innymi usługami firmy Microsoft. Teraz znajdziesz te informacje w portalu zarządzania usługą Office 365 w obszarze Kondycja usługi. Aby uzyskać więcej informacji, zobacz [ten wpis w blogu](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### <a name="app-management"></a>Zarządzanie aplikacjami
- **Ulepszone funkcje konfiguracji zasad dotyczących danych przedsiębiorstwa w systemie Windows 10.** Wprowadzono ulepszenia funkcji konfiguracji zasad ochrony danych przedsiębiorstwa w systemie Windows 10 dotyczące tworzenia reguł aplikacji, określania definicji granic sieci i innych ustawień ochrony danych przedsiębiorstwa. Aby dowiedzieć się więcej, zobacz [Tworzenie zasad ochrony danych w przedsiębiorstwie (EDP) przy użyciu usługi Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune).


### <a name="device-management"></a>Zarządzanie urządzeniami
- **Ustawienie zasad programu Windows Defender umożliwiające ochronę przed potencjalnie niechcianymi aplikacjami.** W programie Windows Defender dodano nowe ustawienie o nazwie **Wykrywanie potencjalnie niechcianych aplikacji** do ogólnych zasad konfiguracji systemu Windows 10 Desktop i Mobile. Przy użyciu tego ustawienia możesz chronić zarejestrowane komputery stacjonarne z systemem Windows przed uruchamianiem oprogramowania sklasyfikowanego przez program Windows Defender jako potencjalnie niechciane. Można chronić komputery przed uruchamianiem tych aplikacji lub używać trybu inspekcji, aby zgłaszać zdarzenia instalowania potencjalnie niechcianych aplikacji. Aby uzyskać więcej informacji, zobacz [Ustawienia zasad systemu Windows 10 w usłudze Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).
<!---TFS 1244478--->

### <a name="conditional-access"></a>Dostęp warunkowy
- **Zasady kontroli dostępu do sieci dla usługi Intune w produkcie Cisco ISE.**  Klienci korzystający z platformy Cisco Identity Service Engine (ISE) 2.1 i usługi Microsoft Intune mogą ustawić zasady kontroli dostępu do sieci w produkcie ISE.

    W przypadku korzystania z tych zasad urządzenia, które łączą się z siecią przy użyciu sieci WiFi lub VPN, muszą spełniać następujące warunki przed udzieleniem im dostępu:

    * być zarządzane przez usługę Intune,
    * być zgodne z wdrożonymi zasadami zgodności usługi Intune.

 Użytkownicy końcowi niezgodnych urządzeń będą otrzymywali monit o zarejestrowanie się i skorygowanie wszystkich problemów ze zgodnością w celu uzyskania dostępu.
- **Dostęp warunkowy dla przeglądarki.** Możliwe jest ustawienie zasad dostępu warunkowego dla usług [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) i [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune), aby można było do nich uzyskać dostęp tylko z obsługiwanych przeglądarek internetowych i zgodnych urządzeń z systemem iOS lub Android. Użytkownicy końcowi, którzy podejmą próbę zalogowania się do witryn usługi Outlook Web Access (OWA) lub usługi SharePoint przy użyciu urządzeń z systemami iOS i Android, zostaną poproszeni o zarejestrowanie swoich urządzeń w usłudze Intune oraz rozwiązanie wszelkich problemów z niezgodnością przed ukończeniem logowania.
<!---TFS 1175844--->

- **Usługa Dynamics CRM Online obsługuje dostęp warunkowy.** Można ustawić zasady dostępu warunkowego dla usługi [Dynamics CRM Online](/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune), co umożliwia dostęp do niej tylko przez zarządzane i zgodne urządzenia z systemem iOS lub Android. Użytkownicy końcowi, którzy podejmą próbę zalogowania się do aplikacji mobilnej Dynamics CRM w systemie iOS lub Android, zostaną poproszeni o rejestrację w usłudze Intune oraz rozwiązanie wszelkich problemów z niezgodnością przed ukończeniem logowania.
<!---TFS1295358--->

### <a name="intune-company-portal-updates"></a>Aktualizacje Portalu firmy w usłudze Intune

__Aplikacja Portal firmy dla systemu Android__

- Gdy administratorzy IT zastosują nowe zasady „Wymagaj, aby urządzenia nie zezwalały na instalowanie aplikacji z nieznanych źródeł (Android 4.0+)”, użytkownikom końcowym urządzeń z systemem Android 4.0 lub nowszym zostanie wyświetlony komunikat „Instalacja z nieznanych źródeł musi zostać wyłączona”. Użytkownicy będą musieli przejść do pozycji **Ustawienia** > **Zabezpieczenia** i wyłączyć opcję **Nieznane źródła**. Link w komunikacie dotyczącym zgodności pozwala użytkownikom uzyskać więcej [informacji](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) o komunikacie i o tym, dlaczego wymagane jest wyłączenie tego ustawienia.

- Gdy administratorzy IT zastosują nowe zasady „Wymagaj, aby urządzenia miały włączone skanowanie aplikacji pod kątem zagrożeń zabezpieczeń (Android 4.0+)”, użytkownikom końcowym urządzeń z systemem Android 4.0 lub nowszym zostanie wyświetlony komunikat „Skanuj urządzenie pod kątem zagrożeń zabezpieczeń”. Użytkownicy będą musieli przejść do pozycji **Ustawienia** > **Google** > **Zabezpieczenia** i włączyć opcję **Skanuj urządzenie pod kątem zagrożeń zabezpieczeń**. Link w komunikacie dotyczącym zgodności pozwala użytkownikom uzyskać więcej [informacji](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) o komunikacie i o tym, dlaczego wymagane jest włączenie tego ustawienia.

- Gdy administratorzy IT zastosują nowe zasady „Wymagaj, aby debugowanie USB było wyłączone (Android 4.2 +)”, użytkownikom końcowym urządzeń z systemem Android 4.2 lub nowszym zostanie wyświetlony komunikat „Debugowanie USB musi zostać wyłączone”. Użytkownicy będą musieli przejść do pozycji **Ustawienia** > **Opcje dewelopera** i wyłączyć opcję **Debugowanie USB**. Link w komunikacie dotyczącym zgodności pozwala użytkownikom uzyskać więcej [informacji](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) o komunikacie i o tym, dlaczego wymagane jest wyłączenie tego ustawienia.

- Gdy administratorzy IT zastosują nową zasadę „Minimalny poziom poprawki zabezpieczeń (Android 6.0+)”, użytkownikom końcowym z urządzeniami z systemem Android 6.0 lub nowszym będzie wyświetlany komunikat „To urządzenie nie spełnia wymagań dotyczących minimalnego poziomu poprawki zabezpieczeń systemu Android”. Użytkownicy będą musieli zainstalować wymaganą poprawkę zabezpieczeń. Link w komunikacie dotyczącym zgodności pozwala użytkownikom uzyskać [informacje](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) o sposobie instalowania wymaganej poprawki zabezpieczeń i zobaczyć, która poprawka zabezpieczeń jest aktualnie zainstalowana.

__Aplikacja Portal firmy dla systemu iOS__

- Podczas instalacji aplikacji biznesowych przez użytkowników końcowych wyświetlane jest teraz usprawnione środowisko instalacyjne aplikacji. Jeśli instalacja aplikacji trwa długo, użytkownicy mogą synchronizować swoje urządzenia ręcznie, co wymusza wznowienie procesu synchronizacji. Aby przejrzeć instrukcje dla użytkowników końcowych, zobacz [Ręczne synchronizowanie urządzenia z systemem iOS](/Intune/EndUser/sync-your-device-manually-ios).

- Aplikacja Portal firmy usługi Microsoft Intune dla systemu iOS została zaktualizowana do obsługi systemu iOS w wersji 8.0 i nowszych. Ta aktualizacja oznacza, że użytkownicy końcowi mogą instalować aplikację Portal firmy i rejestrować w usłudze Intune nowe urządzenia tylko wtedy, gdy urządzenie ma zainstalowany system iOS w wersji 8.0 lub nowszej. Użytkownicy, którzy mają wcześniej zarejestrowane urządzenia z nieobsługiwaną wersją systemu iOS, mogą nadal używać aplikacji Portal firmy, która znajduje się na urządzeniu.


## <a name="may-2016"></a>Maj 2016
Wszystkie te funkcje są również obsługiwane dla wdrożeń hybrydowych (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](https://technet.microsoft.com/en-us/library/mt718155.aspx).

### <a name="documentation"></a>Dokumentacja
Zapraszamy do skorzystania z wersji zapoznawczej witryny [docs.microsoft.com](https://docs.microsoft.com/en-us/intune)!
Jest to zupełnie nowa, nowoczesna platforma zawartości zaprojektowana z myślą o tym, aby ułatwić naszym klientom zrozumienie usługi Intune oraz korzystanie z niej.
Aby przeczytać o wszystkich nowych funkcjach, zobacz [Wprowadzenie do witryny docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/)

### <a name="intune-service-health"></a>Kondycja usługi Intune
Informacje o kondycji usługi Intune zostały przeniesione do centralnej lokalizacji z innymi usługami firmy Microsoft. Teraz znajdziesz te informacje w [portalu zarządzania usługą Office 365](https://portal.office.com/Admin/Default.aspx) w obszarze **Kondycja usługi**.
Aby uzyskać więcej informacji, zobacz [ten wpis w blogu](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).


### <a name="app-management"></a>Zarządzanie aplikacjami
- **Zestaw SDK zarządzania aplikacjami mobilnymi: obsługa konfiguracji długości numeru PIN.** Będzie możliwe określenie długości numeru PIN dla aplikacji w ramach zarządzania aplikacjami mobilnymi, podobnie jak w przypadku numeru PIN urządzenia. Użytkownicy końcowi będą musieli zachować zgodność z określonymi nowymi ograniczeniami. Będzie wyświetlany nieco zmodyfikowany ekran numeru PIN, umożliwiający wprowadzanie dłuższych numerów. Aby uzyskać szczegółowe informacje, zobacz [Ustawienia zasad zarządzania aplikacjami mobilnymi dla systemu Android](/intune/deploy-use/android-mam-policy-settings) i [Ustawienia zasad zarządzania aplikacjami mobilnymi dla systemu iOS](/intune/deploy-use/ios-mam-policy-settings).

- **Aplikacja Skype dla firm dla systemów iOS i Android.** Aplikację Skype dla firm można teraz wskazać jako objętą [zarządzaniem aplikacjami mobilnymi bez stosowania zasad rejestracji](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). Gdy użytkownicy zalogują się, zostaną zastosowane zasady zarządzania aplikacjami mobilnymi.

- **Nowe aplikacje dostępne do zarządzania przy użyciu zasad zarządzania aplikacjami mobilnymi.** Aplikacje Microsoft Word, Excel i PowerPoint dla systemu Android teraz mogą być skojarzone z zasadami zarządzania aplikacjami mobilnymi na urządzeniach, które nie są zarejestrowane w usłudze Intune. Pełna lista obsługiwanych aplikacji jest dostępna w galerii aplikacji mobilnych usługi Microsoft Intune na stronie [partnerów aplikacji usługi Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).


### <a name="company-portal-updates"></a>Aktualizacje Portalu firmy

#### <a name="android-company-portal-app"></a>Aplikacja Portal firmy dla systemu Android
- **Wyskakujące powiadomienia dla użytkownika końcowego**: użytkownicy końcowi będą teraz otrzymywać wyskakujące powiadomienia z aplikacji Portal firmy dla systemu Android, gdy będą rejestrować lub usuwać swoje urządzenia w Portalu firmy.

- **Zmiany w kontach menedżerów rejestracji urządzeń w aplikacji Portal firmy dla systemu Android.** W celu poprawy wydajności i skalowania usługa Intune nie pokazuje już wszystkich urządzeń menedżerów rejestracji urządzeń (DEM) w okienku Moje urządzenia w aplikacji Portal firmy dla systemu Android. Wyświetlane jest tylko urządzenie lokalne, na którym uruchomiono aplikację, o ile zostało zarejestrowane przez aplikację Portal firmy. Użytkownik menedżera rejestracji urządzeń może wykonywać działania na urządzeniu lokalnym, ale zdalne zarządzanie innymi zarejestrowanymi urządzeniami można przeprowadzać tylko z konsoli administracyjnej usługi Intune.

#### <a name="company-portal-website"></a>Witryna sieci Web Portal firmy
- **Witryna sieci Web Portal firmy: transparent identyfikacji urządzenia będzie zapewniać więcej informacji użytkownikom końcowym.** Użytkownicy końcowi mogą teraz łatwiej identyfikować urządzenie, które wybrali, gdy korzystają z witryny sieci Web Portal firmy. W przypadku wybrania niewłaściwego urządzenia użytkownik będzie mógł wybrać poprawne urządzenie, naciskając link **Naciśnij tutaj** na transparencie na stronie głównej.

### <a name="service-deprecation"></a>Wycofywanie usług
- **Aplikacje Intune Viewer.** Wraz z wydaniem nowej aplikacji RMS sharing zostaną usunięte następujące aplikacje Intune Viewer, począwszy od sierpnia 2016 roku:
    - Intune AV Viewer
    - Intune PDF Viewer
    - Intune Image Viewer dla systemu Android ze sklepu Google Play

  Zalecamy, aby zamiast korzystania z aplikacji Intune Viewer używać nowej aplikacji do zarządzania prawami (RMS sharing) dla systemu Android, co pozwala na wdrożenie jednej aplikacji zamiast trzech osobnych aplikacji w celu bezpiecznego przeglądania plików firmy na urządzeniach z systemem Android. Dowiedz się więcej na temat aplikacji RMS sharing (za pomocą linku do dokumentacji).

- **Usunięcie określania grup niestandardowych jako obiektów docelowych reguł powiadomień.**
Reguły powiadomień usługi Intune definiują, do kogo będą wysyłane alerty e-mail z usługi Intune. Obecnie można konfigurować reguły powiadomień w celu wysyłania wiadomości e-mail do wszystkich użytkowników urządzeń należących do utworzonej grupy urządzeń usługi Intune. Około 1 czerwca 2016 roku określanie grup utworzonych przez użytkownika jako docelowych przestanie być obsługiwane.

    Obecnie w celu skierowania reguły powiadomień do grupy utworzonej z konsoli administracyjnej usługi Microsoft Intune można wykonać następujące czynności:

    W obszarze roboczym **Administracja** kliknij pozycję **Reguły powiadomień** > **Utwórz nową regułę**.

    W drugim kroku Kreatora tworzenia reguł powiadomień wybierz grupy urządzeń, których będzie dotyczyć dana reguła. Ten krok („Wybierz grupy urządzeń”) jest usuwany z konsoli usługi Intune.

    Wstępny plan dla tej zmiany jest następujący:
    - W czerwcu 2016 roku nowi dzierżawcy nie będą widzieć drugiego kroku Kreatora tworzenia reguł powiadomień. Nie dotyczy to jednak istniejących dzierżawców.
    - W okolicach sierpnia 2016 roku niektórzy istniejący dzierżawcy nie będą widzieć kroku „Wybierz grupy urządzeń” w kreatorze.
    - Przewidujemy, że krok „Wybierz grupy urządzeń” w kreatorze przestanie być widoczny dla wszystkich dzierżawców w okolicach października 2016 roku.


- **Zmiany w obsłudze aplikacji Portal firmy dla systemu iOS**. W najbliższych miesiącach odbędzie się aktualizacja aplikacji Portal firmy usługi Microsoft Intune dla systemu iOS, która obejmie tylko urządzenia z systemem iOS 8.0 lub nowszym. Użytkownicy nie będą mogli rejestrować nowych urządzeń z wersjami starszymi niż iOS 8.0. Zarejestrowane urządzenia z wersjami starszymi niż iOS 8.0 nadal będą zarządzane i przez ograniczony czas będzie można nadal korzystać z aplikacji Portal firmy. Jednak w celu uzyskania dostępu do najnowszych wersji aplikacji Portal firmy urządzenia muszą mieć system iOS 8.0 lub późniejszą wersję. Zalecamy powiadomienie użytkowników, aby przeprowadzili aktualizację do wersji iOS 8.0 lub nowszej w celu pełnego korzystania z nowych funkcji usługi Intune.  


## <a name="april-2016"></a>Kwiecień 2016
Wszystkie te funkcje są również obsługiwane dla klientów hybrydowych (program Configuration Manager zintegrowany z usługą Intune).

### <a name="app-management"></a>Zarządzanie aplikacjami
- **Zgodność użytkownika funkcji zarządzania aplikacjami mobilnymi.**
Teraz można wyświetlić [stan](/intune/deploy-use/monitor-mobile-app-management-policies-with-Microsoft-Intune) zasad zarządzania aplikacjami dla dowolnego użytkownika w dzierżawie usługi Azure Active Directory (AAD). Obejmuje to następujące działania:
   - Urządzenia
   - Aplikacje na urządzeniu

   Wartości stanu:

   **Zaewidencjonowano**: wskazuje, że zasady zostały wdrożone dla użytkownika, aplikacja była stosowana w kontekście pracy i pomyślnie odebrała zasady.

    **Nie zaewidencjonowano**: wskazuje, że zasady zostały wdrożone dla użytkownika, ale aplikacja nie była stosowana w kontekście pracy od tego momentu.


- **Kontrolki zarządzania aplikacjami mobilnymi zapobiegające synchronizacji kontaktów programu Outlook (Android).**
Dostępne jest nowe ustawienie do [zarządzania aplikacjami mobilnymi](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) bez rejestracji urządzeń. To ustawienie umożliwia zapobieganie synchronizacji przez aplikację kontaktów z natywną książką adresową na urządzeniach z systemem Android. Po włączeniu tego ustawienia wybrane aplikacje nie będą w stanie zapisywać kontaktów w natywnej książce adresowej. Po wyłączeniu tego ustawienia wybrane aplikacje będą w stanie zapisywać kontakty w natywnej książce adresowej. Po [zdalnym wyczyszczeniu urządzenia lub aplikacji](/intune/deploy-use/wipe-managed-company-app-data-with-Microsoft-Intune) zostaną usunięte wszystkie kontakty zapisane wcześniej w natywnej książce adresowej. To nowe ustawienie jest obsługiwane początkowo przez aplikację Outlook na urządzeniach z systemem Android.

### <a name="device-management"></a>Zarządzanie urządzeniami
- **Identyfikacja numeru telefonu dla urządzeń należących do firmy.** Telefony skategoryzowane jako firmowe są teraz identyfikowane przez pełny numer telefonu na przykład przy uruchomieniu raportu inwentaryzacyjnego urządzenia przenośnego. Numery telefonów BYOD są nadal maskowane symbolami **** i wyświetlane są tylko 4 ostatnie cyfry.


### <a name="company-portal-updates"></a>Aktualizacje Portalu firmy
**Aplikacja Portal firmy dla systemu Android** Użytkownicy, którzy nie zarejestrowali urządzeń w usłudze Intune i którzy nie mają zainstalowanych poprawnych certyfikatów, nie będą w stanie zalogować się do aplikacji Portal firmy systemu Android i zobaczą komunikat „Nie możesz się zalogować, ponieważ urządzenie nie ma wymaganego certyfikatu”. Komunikat zawiera link „Rozwiązanie problemu”, którego naciśnięcie powoduje wyświetlenie instrukcji instalacji certyfikatu. Aby zobaczyć kroki, które użytkownicy końcowi powinni wykonać w celu rozwiązania problemu, zobacz [Brak wymaganego certyfikatu urządzenia](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing).

**Aplikacja Portal firmy dla systemu iOS** Dodano obsługę akcji „pociągnij, aby odświeżyć”, umożliwiającej odświeżenie zawartości ekranu głównego, w tym aplikacji, urządzeń i danych kontaktowych działu IT. Akcja „pociągnij, aby odświeżyć” nie sprawdza informacji dotyczących zgodności i zasad. Można to zrobić, wybierając kafelek bieżącego urządzenia i naciskając przycisk **Synchronizuj**.

**Aplikacja Portal firmy w systemie Windows 10 Mobile i Windows Phone 8.1** Podczas instalacji aplikacji biznesowych przez użytkowników końcowych wyświetlane jest teraz usprawnione środowisko instalacyjne aplikacji. Jeśli instalacja aplikacji trwa długo, użytkownicy mogą synchronizować swoje urządzenia ręcznie, co wymusza wznowienie procesu synchronizacji. Aby przejrzeć instrukcje dla użytkowników końcowych, zobacz [Ręczne synchronizowanie urządzenia w celu przyspieszenia instalacji aplikacji](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually).

**Witryna sieci Web Portal firmy** Gdy użytkownicy systemów Windows 10 Mobile i Windows Phone 8.1 instalują aplikacje biznesowe, wyświetlane są następujące nowe stany zapewniające więcej informacji na temat stanu instalacji:

* **Oczekiwanie na synchronizację urządzenia** — użytkownik nacisnął pozycję „Instaluj” i urządzenie próbuje przeprowadzić synchronizację z infrastrukturą usługi Intune. Synchronizacja jest wymagana w celu ukończenia instalacji. Komunikat „Oczekiwanie na synchronizację urządzenia” to również link, który użytkownicy mogą nacisnąć w celu wyświetlenia [instrukcji](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) ręcznej synchronizacji urządzenia z usługą Intune, jeśli proces synchronizacji trwa długo lub zablokował się.
* **Pobieranie** — trwa przetwarzanie żądania pobierania użytkownika; urządzenie pobiera i instaluje aplikację.

Przed dodaniem tych stanów użytkownicy nie mieli wystarczających informacji na temat sytuacji w przypadku długich instalacji, ponieważ wyświetlany był tylko stan „Instalowanie”, który mógł pozostawać na ekranie godzinami. Dodanie nowych stanów oznacza, że zamiast kontaktować się z działem pomocy technicznej, użytkownicy mogą nacisnąć link „Oczekiwanie na synchronizację urządzenia” i wykonać instrukcje, aby wymusić wznowienie procesu synchronizacji.



### <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new-in-microsoft-intune.md).



<!--HONumber=Nov16_HO3-->


