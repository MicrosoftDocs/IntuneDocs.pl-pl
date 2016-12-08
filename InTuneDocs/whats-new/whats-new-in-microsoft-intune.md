---
title: Co nowego | Microsoft Intune
description: "Sprawdź nowości w tym miesiącu i poprzednich wersjach usługi Microsoft Intune"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8ef3b7e4eec5a520c93fb3f70c8e5b6ee7d2c3aa
ms.openlocfilehash: e0b0c7eb3ddc07f05fc0c2e4caa6726ed052c9d8


---
# <a name="whats-new-in-microsoft-intune---november-2016"></a>Co nowego w usłudze Microsoft Intune — listopad 2016 r.
Poznaj nowości w tej wersji usługi Microsoft Intune. Dowiedz się o nadchodzących zmianach, na które należy się przygotować, jak również uzyskaj informacje o poprzednich wersjach.

> [!Note]
> Wszystkie te funkcje będą również w przyszłości obsługiwane dla hybrydowych wdrożeń klientów (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nowe możliwości

<!--### View App States for All Platforms in Real Time
App installation status is now shown in real-time in the console. When you previously deployed an app, you had to wait for a targeted device to report back before the app install status was displayed in the Intune console.

### Streamline iOS App Management for your End Users
Intune can now automatically take over management of the previously installed app and no end user action is required.

Previously, if the end user of an enrolled iOS device installed an app from the App Store before you deployed that same app with a deployment action of __Available__, then the end user had to:

1. Open the __Company Portal__.
2. Select the app.
3. Tap __Install__ to enable Intune to take over management of the app.-->

__Nowy Portal firmy w usłudze Microsoft Intune dostępny dla urządzeń z systemem Windows 10__ Firma Microsoft udostępniła nową [aplikację Portal firmy w usłudze Microsoft Intune dla urządzeń z systemem Windows 10](https://www.microsoft.com/store/apps/9wzdncrfj3pz). Ta aplikacja, korzystająca z nowego uniwersalnego formatu systemu Windows 10, będzie udostępniać użytkownikom zaktualizowane środowisko obsługi w aplikacji oraz zapewniać identyczne środowisko obsługi na wszystkich urządzeniach z systemem Windows 10 — komputerach osobistych i urządzeniach przenośnych — oferując ten sam zestaw funkcji, który jest dostępny dzisiaj.

Nowa aplikacja będzie również umożliwiać użytkownikom korzystanie z dodatkowych funkcji platformy, takich jak rejestracja jednokrotna (SSO) i uwierzytelnianie oparte na certyfikatach, na urządzeniach z systemem Windows 10. Aplikacja zostanie udostępniona jako uaktualnienie istniejących instalacji Portalu firmy w systemie Windows 8.1 i Portalu firmy w systemie Windows Phone 8.1 ze Sklepu Windows. Aby uzyskać szczegółowe informacje, przejdź do strony [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).

<!--### Support for Windows Store for Business Apps Being Deployed as Available
You can now deploy apps you synchronized from the Windows Store for Business (WSfB) with a deployment action of __Available__ or __Required__. After syncing WSfB apps into Intune, administrators will be able to target those apps as available installs to groups of users. End users will see the deployed WSfB apps as available for install in the Universal Company Portal, where they can choose whether they would like to acquire the apps.

### Conditional Access for MAM with SharePoint Online

You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint online.  You can get started in Intune mobile app management via the Azure portal. Look for the  Conditional Access section in the “Settings” blade which now includes the option for SharePoint online.-->

> [!IMPORTANT]

> __Aktualizacja usługi Intune i programu Android for Work__

> Można wdrożyć aplikacje systemu Android for Work z akcją __Wymagane__, ale jeśli grupy usługi Intune zostały zmigrowane do nowego środowiska grup usługi Azure AD, będzie można wdrożyć aplikacje tylko jako __Dostępne__.

### <a name="intune-app-sdk-for-cordova-plugin-now-supports-mam-without-enrollment"></a>Zestaw SDK aplikacji usługi Intune dla wtyczki Cordova obsługuje teraz funkcje zarządzania aplikacjami mobilnymi bez rejestracji
Deweloperzy aplikacji mogą teraz używać zestawu SDK aplikacji usługi Intune dla wtyczki Cordova, aby w swoich aplikacjach opartych na platformie Cordova dla systemów Android i iOS włączyć funkcje zarządzania aplikacjami mobilnymi bez rejestracji urządzeń. Zestaw SDK aplikacji usługi Intune dla wtyczki Cordova można znaleźć [tutaj](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam).

### <a name="intune-app-sdk-xamarin-component-now-supports-mam-without-enrollment"></a>Składnik Xamarin zestawu SDK aplikacji usługi Intune obsługuje teraz funkcje zarządzania aplikacjami mobilnymi bez rejestracji
Deweloperzy aplikacji mogą teraz używać składnika Xamarin zestawu SDK aplikacji usługi Intune, aby w swoich aplikacjach opartych na platformie Xamarin dla systemów Android i iOS włączyć funkcje zarządzania aplikacjami mobilnymi bez rejestracji urządzeń. Składnik Xamarin zestawu SDK aplikacji usługi Intune można znaleźć [tutaj](https://github.com/msintuneappsdk/intune-app-sdk-xamarin).

## <a name="notices"></a>Uwagi

### <a name="symantec-signing-certificate-no-longer-requires-signed-windows-phone-8-company-portal-for-upload"></a>Certyfikat podpisywania firmy Symantec nie wymaga już podpisanego cyfrowo Portalu firmy dla systemu Windows Phone 8 w celu przekazywania
Do przekazywania certyfikatu podpisywania firmy Symantec nie jest już wymagana podpisana cyfrowo aplikacja Portal firmy dla systemu Windows Phone 8. Certyfikat można przekazać niezależnie.

## <a name="deprecations"></a>Zakończenie obsługi

### <a name="support-for-the-windows-phone-8-company-portal"></a>Obsługa Portalu firmy dla systemu Windows Phone 8
Obsługa Portalu firmy dla systemu Windows Phone 8 została zakończona. Obsługa platform systemów Windows Phone 8 i WinRT została zakończona w październiku 2016 r. Obsługa Portalu firmy dla systemu Windows 8 została również zakończona w październiku 2016 r.


### <a name="see-also"></a>Zobacz także
* [Blog usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plan platformy w chmurze](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Poprzednie wersje usługi Intune](whats-new-archive.md)



<!--HONumber=Dec16_HO1-->


