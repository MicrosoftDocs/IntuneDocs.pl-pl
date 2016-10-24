---
title: Wersja wczesna | Microsoft Intune
description: 
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 10/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a5c4b0f15456a9f24c95954d669a17c63f96a459
ms.openlocfilehash: 273016d4fe114bbe60e9cebc06e89584c8f91f0b


---

# Wkrótce w usłudze Microsoft Intune — październik
**Wersja wczesna** zawiera listę funkcji, które zostaną wprowadzone w przyszłych wersjach usługi Microsoft Intune. Te informacje są przekazywane pod rygorem umowy NDA w bardzo ograniczonym zakresie i mogą ulec zmianie. Niektóre funkcje wymienione w tym miejscu mogą nie być wdrożone na czas i zostać opóźnione do przyszłych wersji. Inne funkcje są testowane w wersji pilotażowej, aby zapewnić przygotowanie ich do użytku przez klientów. W przypadku pytań lub wątpliwości skontaktuj się ze swoim partnerem ds. usługi Intune/PM.

Ta strona jest okresowo aktualizowana. Odwiedź ją ponownie, aby sprawdzić informacje na temat nadchodzących aktualizacji.

Dla usługi Intune opracowywane są następujące zmiany. Wszystkie te funkcje będą również w przyszłości obsługiwane dla hybrydowych wdrożeń klientów (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

### Zarządzanie drukowaniem z aplikacji zarządzanych przy użyciu zasad zarządzania aplikacjami mobilnymi
Możesz teraz uniemożliwić drukowanie firmowych danych z aplikacji, dla których obowiązują zasady zarządzania aplikacjami mobilnymi. To ustawienie jest dostępne w [Portalu Azure](..deployuse/create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) i jest obsługiwane zarówno przez urządzenia z systemem [iOS](..deployuse/ios-mam-policy-settings), jak i z systemem [Android](..deployuse/android-mam-policy-settings).
<!--TFS 1014328-->

### Nowy Portal firmy w usłudze Microsoft Intune dostępny dla urządzeń z systemem Windows 10
Firma Microsoft udostępnia nowy Portal firmy w usłudze Microsoft Intune dla urządzeń z systemem Windows 10. Ta aplikacja, korzystająca z nowego uniwersalnego formatu systemu Windows 10, będzie udostępniać użytkownikom zaktualizowane środowisko obsługi w aplikacji oraz zapewniać identyczne środowisko obsługi na wszystkich urządzeniach z systemem Windows 10 — komputerach osobistych i urządzeniach przenośnych — oferując ten sam zestaw funkcji, który jest dostępny dzisiaj.

Nowa aplikacja będzie również umożliwiać użytkownikom korzystanie z dodatkowych funkcji platformy, takich jak rejestracja jednokrotna (SSO) i uwierzytelnianie oparte na certyfikatach, na urządzeniach z systemem Windows 10. Aplikacja zostanie udostępniona jako uaktualnienie istniejących instalacji Portalu firmy w systemie Windows 8.1 i Portalu firmy w systemie Windows Phone 8.1 ze Sklepu Windows.
<!--TFS 1016502-->

### Pomoc techniczna dla programu Android for Work

Usługa Intune jest teraz częścią [programu Android for Work](https://enterprise.google.com/android/partners/). Firma Microsoft rozpocznie w tym miesiącu świadczenie pomocy technicznej dla funkcji programu Android for Work za pośrednictwem usługi Intune.

[Przeczytaj ogłoszenie firmy Microsoft dotyczące pomocy technicznej dla programu Android for Work w ramach usługi Intune](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

<!---This month, some newly provisioned Intune tenants will start seeing the Android for Work features. We will announce later when existing tenants will begin to see this feature.--->
<!--TFS 1043303-->

### Zgodność środowiska Android Samsung KNOX z usługą Intune

Niektóre modele telefonu Samsung Galaxy Ace nie mogą być zarządzane przez usługę Intune jako urządzenia Samsung KNOX. Zamiast tego po zarejestrowaniu tych urządzeń w usłudze Intune będą one zarządzane jako standardowe urządzenia z systemem Android.
Numery modeli, których dotyczy to zagadnienie:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

Ani Ty ani użytkownicy końcowi nie musicie wykonywać żadnych dalszych czynności.
Aby uzyskać więcej informacji, odwiedź witrynę sieci Web [Samsung KNOX](https://www.samsungknox.com).

<!--TFS 1173566 iX blurb provided by Barry; requires PM signoff

### Multi-factor authentication for Android and iOS enrollment

In addition to Windows 8.1 and later, administrators can now enable multi-factor authentication for Android and iOS devices in the Microsoft Intune Enrollment application. -->    

### Aplikacja Portal firmy dla systemu Windows 8 jest przestarzała; pomoc techniczna dla platform Windows Phone 8 i Windows RT zostanie wkrótce wycofana
Począwszy od października 2016 roku z usługi Microsoft Intune zostanie wycofana pomoc techniczna dla aplikacji Portal firmy systemu Windows 8. Z usługi Microsoft Intune zostanie również wycofana pomoc techniczna dla platform Windows Phone 8 i Windows RT. W rezultacie nie będzie można zarejestrować ani zaktualizować żadnych urządzeń z systemem Windows Phone 8 lub Windows RT.

Można będzie nadal zarządzać urządzeniami z systemami Windows Phone 8, Windows RT i Windows 8, które są już zarejestrowane. Zaktualizuj urządzenia z systemami Windows 8 i Windows Phone 8 do systemów Windows 8.1 i Windows Phone 8.1 oraz skorzystaj z odpowiedniej aplikacji Portal firmy dla systemu Windows 8.1 lub Windows Phone 8.1, aby kontynuować bez zakłóceń dystrybucję aplikacji na tych urządzeniach.

Począwszy od listopada 2016 roku firma Microsoft wycofa pomoc techniczną dla aplikacji Portal firmy systemu Windows Phone 8.
<!--TFS 1255391-->

### Dostęp warunkowy do zarządzania aplikacjami mobilnymi
Możesz teraz tworzyć zasady dostępu warunkowego, aby blokować dostęp niezarządzanych aplikacji mobilnych do usług [Exchange Online](..deployuse/restrict-access-to-exchange-online-with-microsoft-intune.md) i [SharePoint Online](..deployuse/restrict-access-to-sharepoint-online-with-microsoft-intune.md). Możesz blokować wbudowanych klientów poczty i aplikacje, dla których nie włączono zarządzania aplikacjami mobilnymi przy użyciu zestawu SDK aplikacji usługi Intune.  Można to zrobić przez utworzenie zasady dostępu warunkowego i określenie aplikacji, które mogą uzyskiwać dostęp do usług Exchange Online i SharePoint Online za pośrednictwem Portalu Azure.
<!--TFS 1317673-->

<!--TFS 1318014; awaiting approval in notes as to whether to proceed

### "Default" policy is deprecated

To minimize unintentionally assigned profiles, Intune is removing support for the "default" Corporate Device Enrollment profile for Apple Device Enrollment Program (DEP) device serial numbers in the new Azure console. Serial numbers synchronized from an Apple DEP account will initially have no Corporate Device Enrollment profile assigned.  A profile must be assigned manually after synchronization. This change will apply to the new console only. Until the existing Admin console is retired, no change will take place.
-->

<!--TFS 1318023; awaiting approval in notes as to whether to proceed

### Deprecation of row-by-row iOS Details review for iOS device CSV uploads

In order to streamline uploading IMEI numbers for Corporate devices and Apple serial numbers for Configurator enrollment, Intune is removing the row by row review of hardware identifiers already found in the system. This review allows the IT Pro to accept associated Details from the CSV to overwrite the existing details for a hardware identifier already in the system. The review will be replaced by a single option to automatically overwrite Details for all hardware identifiers or ignore new details for existing identifiers. This change will apply to the new console only. Until the existing Admin console is retired, no change will take place.
-->

### Integracja usługi Lookout w celu ochrony urządzeń z systemem iOS
W październiku firma Microsoft wprowadzi integrację z rozwiązaniem firmy Lookout do ochrony urządzeń przenośnych w celu zabezpieczenia urządzeń przenośnych z systemem iOS dzięki wykrywaniu złośliwego oprogramowania, ryzykownych aplikacji i innych zagrożeń na urządzeniach. Rozwiązanie firmy Lookout pomaga w określeniu poziomu zagrożenia, który można skonfigurować. W usłudze Intune można utworzyć regułę zasad zgodności w celu określania zgodności urządzeń na podstawie oceny ryzyka uzyskanej z rozwiązania firmy Lookout. Za pomocą zasad dostępu warunkowego można umożliwić lub zablokować dostęp do zasobów firmy w zależności od stanu zgodności danego urządzenia.

W przypadku użytkowników końcowych korzystających z niezgodnych urządzeń z systemem iOS zostanie wyświetlony monit o przeprowadzenie rejestracji. Aby uzyskać dostęp do zasobów firmy, użytkownicy będą musieli zainstalować aplikację Lookout for Work na swoich urządzeniach, uaktywnić ją i podjąć środki zaradcze dotyczące zagrożeń raportowanych przez aplikację Lookout for Work.
<!--TFS 1319493-->

### Zestaw SDK aplikacji usługi Intune i narzędzie opakowujące aplikacje dla systemu Android
Możesz włączyć stosowanie zasad zarządzania aplikacjami mobilnymi usługi Intune w używanych aplikacjach przy użyciu narzędzia opakowującego aplikacje usługi Intune lub zestawu SDK aplikacji usługi Intune. Nowe aktualizacje dla narzędzia opakowującego aplikacje i zestawu SDK obejmują:

* Pomoc techniczną dla systemu Android N
* Pomoc techniczną dotyczącą zasad zarządzania aplikacjami mobilnymi usługi Intune bez konieczności rejestrowania urządzeń
* Pomoc techniczną dla aplikacji systemu Android opartych na platformie Xamarin

Zarządzanie aplikacjami mobilnymi można przetestować bez rejestrowania urządzeń i pomocy technicznej platformy Xamarin w publicznej wersji zapoznawczej narzędzia opakowującego aplikacje systemu Android pod adresem: [https://github.com/msintuneappsdk/intune-app-wrapper-android-preview](https://github.com/msintuneappsdk/intune-app-wrapper-android-preview)
<!--TFS 1319511; please create new TFS entry for WN text associated with this TFS item-->

<!--TFS 1319613; no iX review on PM text blurb

### Private preview customers using MAM Conditional Access will have their policies reset

Due to changes in the policy structure for Conditional Access for Mobile App Management, any existing policies that were set by customers through the private preview will be removed. Customers will need to set new policies once the change is made. The timing will coincide with the October service update.
-->

### Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new-in-microsoft-intune.md).



<!--HONumber=Oct16_HO1-->


