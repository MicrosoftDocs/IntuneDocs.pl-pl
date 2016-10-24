---
title: Co nowego | Microsoft Intune
description: "Sprawdź nowości w tym miesiącu i poprzednich wersjach usługi Microsoft Intune"
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 10/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 503719953031bf5079b2bf5bc84a0497d708f79a
ms.openlocfilehash: 730809e0841a248b90f5fe157f2c6338bfd32b2d


---
# Co nowego w usłudze Microsoft Intune — październik 2016 r.
Poznaj nowości w tej wersji usługi Microsoft Intune. Dowiedz się o nadchodzących zmianach, na które należy się przygotować, jak również uzyskaj informacje o poprzednich wersjach.

Wszystkie te funkcje będą również w przyszłości obsługiwane dla hybrydowych wdrożeń klientów (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](https://technet.microsoft.com/library/mt718155.aspx).
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

## Co nowego

### Dostęp warunkowy do zarządzania aplikacjami mobilnymi
Będzie możliwe ograniczanie dostępu do usług Exchange Online w taki sposób, aby można go było uzyskać tylko z poziomu aplikacji obsługujących zasady zarządzania aplikacjami mobilnymi usługi Intune, takich jak Outlook. [Ta nowa funkcja](/intune/deploy-use/allow-policy-managed-apps-access-to-o365) doskonale współgra z zasadami zarządzania aplikacjami mobilnymi w usłudze Intune, ponieważ umożliwia blokowanie dostępu do wbudowanych klientów poczty lub innych aplikacji, które nie zostały skonfigurowane za pomocą tych zasad. Dzięki temu użytkownicy mogą korzystać z danych organizacji za pośrednictwem aplikacji, które mogą być chronione przy użyciu funkcji zarządzania aplikacjami mobilnymi w usłudze Intune. Pracę z zasadami zarządzania aplikacjami mobilnymi w usłudze Intune można rozpocząć, korzystając z portalu Azure. Wystarczy znaleźć w bloku „Ustawienia” nową sekcję dotyczącą dostępu warunkowego.

### Dostęp warunkowy dla komputerów z systemem Windows
Przy użyciu konsoli administracyjnej usługi Intune można teraz tworzyć zasady dostępu warunkowego, uniemożliwiając komputerom z systemem Windows dostęp do usług [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) i [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune). Zasady dostępu warunkowego można też tworzyć w celu blokowania dostępu do aplikacji klasycznych pakietu Office oraz aplikacji uniwersalnych.

### Pomoc techniczna dla programu Android for Work
Usługa Intune jest teraz częścią programu Android for Work. Firma Microsoft rozpocznie w tym miesiącu świadczenie pomocy technicznej dla funkcji programu Android for Work za pośrednictwem usługi Intune.
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

### Integracja usługi Lookout w celu ochrony urządzeń z systemem iOS
W październiku firma Microsoft wprowadzi integrację z rozwiązaniem firmy Lookout do ochrony urządzeń przenośnych w celu zabezpieczenia urządzeń przenośnych z systemem iOS dzięki wykrywaniu złośliwego oprogramowania, ryzykownych aplikacji i innych zagrożeń na urządzeniach. Rozwiązanie firmy Lookout pomaga w określeniu poziomu zagrożenia, który można skonfigurować. W usłudze Intune można utworzyć regułę zasad zgodności w celu określania zgodności urządzeń na podstawie oceny ryzyka uzyskanej z rozwiązania firmy Lookout. Za pomocą zasad dostępu warunkowego można umożliwić lub zablokować dostęp do zasobów firmy w zależności od stanu zgodności danego urządzenia.

W przypadku użytkowników końcowych korzystających z niezgodnych urządzeń z systemem iOS zostanie wyświetlony monit o przeprowadzenie rejestracji. Aby uzyskać dostęp do zasobów firmy, użytkownicy będą musieli zainstalować aplikację Lookout for Work na swoich urządzeniach, uaktywnić ją i podjąć środki zaradcze dotyczące zagrożeń raportowanych przez aplikację Lookout for Work. Dowiedz się, jak [skonfigurować i wdrożyć aplikację Lookout for Work](/intune/deploy-use/configure-and-deploy-lookout-for-work-apps).
<!--TFS 1319493-->

<!--### New Microsoft Intune Company Portal available for Windows 10 devices
Microsoft is releasing a new [Microsoft Intune Company Portal for Windows 10 devices](https://go.microsoft.com/fwlink/?linkid=830663). This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store.-->

### Narzędzie opakowujące aplikacje usługi Intune dla systemu Android
Przy użyciu narzędzia opakowującego aplikacje usługi Intune możesz włączyć stosowanie zasad zarządzania aplikacjami mobilnymi usługi Intune w używanych aplikacjach. Pomoc techniczna dotycząca zasad zarządzania aplikacjami mobilnymi usługi Intune bez konieczności rejestrowania urządzeń jest już dostępna.

### Zarządzanie drukowaniem z aplikacji zarządzanych przy użyciu zasad zarządzania aplikacjami mobilnymi
Możesz teraz uniemożliwić drukowanie firmowych danych z aplikacji, dla których obowiązują zasady zarządzania aplikacjami mobilnymi. To ustawienie jest dostępne w [Portalu Azure](/Intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) i jest obsługiwane zarówno przez urządzenia z systemem [iOS](/Intune/deploy-use/ios-mam-policy-settings), jak i z systemem [Android](/Intune/deploy-use/android-mam-policy-settings).
<!--TFS 1014328-->

## Uwagi

### Zgodność środowiska Android Samsung KNOX z usługą Intune
Niektóre modele telefonu Samsung Galaxy Ace nie mogą być zarządzane przez usługę Intune jako urządzenia Samsung KNOX. Zamiast tego po zarejestrowaniu tych urządzeń w usłudze Intune będą one zarządzane jako standardowe urządzenia z systemem Android.

Numery modeli, których dotyczy to zagadnienie:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

Ani Ty ani użytkownicy końcowi nie musicie wykonywać żadnych dalszych czynności. Aby uzyskać więcej informacji, odwiedź witrynę sieci Web [Samsung KNOX](https://www.samsungknox.com).

### Aplikacja Portal firmy dla systemu Windows 8 jest przestarzała; pomoc techniczna dla platform Windows Phone 8 i Windows RT zostanie wkrótce wycofana
Począwszy od października 2016 roku z usługi Microsoft Intune zostanie wycofana pomoc techniczna dla aplikacji Portal firmy systemu Windows 8. Z usługi Microsoft Intune zostanie również wycofana pomoc techniczna dla platform Windows Phone 8 i Windows RT. W rezultacie nie będzie można zarejestrować ani zaktualizować żadnych urządzeń z systemem Windows Phone 8 lub Windows RT.

Można będzie nadal zarządzać urządzeniami z systemami Windows Phone 8, Windows RT i Windows 8, które są już zarejestrowane. Zaktualizuj urządzenia z systemami Windows 8 i Windows Phone 8 do systemów Windows 8.1 i Windows Phone 8.1 oraz skorzystaj z odpowiedniej aplikacji Portal firmy dla systemu Windows 8.1 lub Windows Phone 8.1, aby kontynuować bez zakłóceń dystrybucję aplikacji na tych urządzeniach.

Począwszy od listopada 2016 roku firma Microsoft wycofa pomoc techniczną dla aplikacji Portal firmy systemu Windows Phone 8.
<!--TFS 1255391-->

## Wkrótce

### Nowy Portal firmy w usłudze Microsoft Intune dostępny dla urządzeń z systemem Windows 10
Firma Microsoft udostępnia nowy Portal firmy w usłudze Microsoft Intune dla urządzeń z systemem Windows 10. Ta aplikacja, korzystająca z nowego uniwersalnego formatu systemu Windows 10, będzie udostępniać użytkownikom zaktualizowane środowisko obsługi w aplikacji oraz zapewniać identyczne środowisko obsługi na wszystkich urządzeniach z systemem Windows 10 — komputerach osobistych i urządzeniach przenośnych — oferując ten sam zestaw funkcji, który jest dostępny dzisiaj.

Nowa aplikacja będzie również umożliwiać użytkownikom korzystanie z dodatkowych funkcji platformy, takich jak rejestracja jednokrotna (SSO) i uwierzytelnianie oparte na certyfikatach, na urządzeniach z systemem Windows 10. Aplikacja zostanie udostępniona jako uaktualnienie istniejących instalacji Portalu firmy w systemie Windows 8.1 i Portalu firmy w systemie Windows Phone 8.1 ze Sklepu Windows. Aby uzyskać szczegółowe informacje, przejdź do strony [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).
<!--TFS 1016502-->

### Zobacz także
* [Blog usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plan platformy w chmurze](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Poprzednie wersje usługi Intune](previous-intune-releases.md)



<!--HONumber=Oct16_HO3-->


