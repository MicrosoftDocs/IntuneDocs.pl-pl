---
title: "Co nowego w wersji zapoznawczej usługi Microsoft Intune | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: sprawdź nowości w wersji zapoznawczej Intune Azure"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/02/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e405363f9d0a89b1589b01d18ee8d2861b07ec60
ms.openlocfilehash: 70007f5501fba37964a0a54807c0e0f565510a74


---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>Co nowego w wersji zapoznawczej usługi Microsoft Intune


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


W miarę rozwoju wersji zapoznawczej i dodawania kolejnych funkcji będziemy Cię o nich tutaj powiadamiać.

<!--## February 2017-->

<!--### Custom app categories <!--748805
You can now create, edit, and assign categories for apps you add to Intune. Currently, categories can only be specified in English.
See [How to add an app to Intune](/intune-azure/manage-apps/add-apps).-->

<!--### Display device categories <!--814654
You can now view the device category as a column in the device list. You can also edit the category from the properties section of the device properties blade.-->

## <a name="january-2017"></a>Styczeń 2017

### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--"></a>Przypisywanie aplikacji biznesowych niezależnie od tego, czy urządzenia są zarejestrowane <!--748823-->
Możesz teraz przypisywać użytkownikom aplikacje biznesowe ze sklepu niezależnie od tego, czy ich urządzenia są zarejestrowane w usłudze Intune. Jeśli urządzenie użytkownika nie jest zarejestrowane w usłudze Intune, aby ją zainstalować, użytkownik musi przejść do witryny sieci Web Portal firmy, a nie do aplikacji Portal firmy. Zobacz [Co to jest zarządzanie aplikacjami](/intune-azure/manage-apps/what-is-app-management).

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Rozwiązywanie problemów związanych z brakiem aktywności urządzeń z systemem iOS lub z brakiem możliwości komunikacji pomiędzy nimi a konsolą administracyjną
Gdy urządzenia użytkowników utracą połączenie z usługą Intune, można wykonać w odniesieniu do nich nowe kroki mające na celu rozwiązanie problemów w celu przywrócenia dostępu do zasobów firmy. Zobacz temat [Urządzenia są nieaktywne lub nie jest możliwe nawiązanie łączności między nimi a konsolą administracyjną](/intune-azure/enroll-devices/troubleshoot-device-enrollment#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="december-2016-initial-release"></a>Grudzień 2016 (wersja początkowa)

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integracja zarządzania kosztami telekomunikacyjnymi w publicznej wersji zapoznawczej witryny Azure Portal<!--747605-->
Obecnie rozpoczynamy pracę nad wersją zapoznawczą integracji z usługami zarządzania kosztami telekomunikacyjnymi innych firm w witrynie Azure Portal. Usługa Intune może być używana do wymuszania limitów użycia danych w kraju i w roamingu. Te operacje integracji rozpoczynamy od współpracy z firmą [Saaswedo](http://www.saaswedo.com). Aby włączyć tę funkcję w dzierżawie w wersji próbnej, [skontaktuj się z pomocą techniczną firmy Microsoft](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

- Wdrażanie aplikacji ze sklepu na urządzeniach z systemami iOS, Android i Windows i zarządzanie nimi
- Wdrażanie aplikacji biznesowych (LOB, line of business) na urządzeniach z systemami iOS, Android i Windows i zarządzanie nimi
- Wdrażanie aplikacji kupionych w ramach zakupów zbiorczych na urządzeniach z systemami iOS, Android i Windows i zarządzanie nimi
- Wdrażanie aplikacji sieci Web na urządzeniach z systemami iOS, Android i Windows i zarządzanie nimi
- Profile konfiguracji aplikacji zarządzanych w systemie iOS
- Konfigurowanie zasad ochrony aplikacji i wdrażanie aplikacji biznesowych na urządzeniach niezarejestrowanych w usłudze Intune
- Profile sieci VPN, sieci VPN dla aplikacji, sieci Wi-Fi, poczta e-mail i profile certyfikatów
- Zasady zgodności
- Dostęp warunkowy do usługi Azure AD
- Dostęp warunkowy do lokalnego programu Exchange
- Rejestrowanie urządzeń
- Kontrola dostępu oparta na rolach

## <a name="deprecated-features-in-the-azure-portal"></a>Funkcje przestarzałe w portalu Azure

### <a name="support-for-row-by-row-review-of-hardware-identifiers"></a>Obsługa przeglądu wiersz po wierszu identyfikatorów sprzętu
Portal Azure nie obsługuje przeglądu wiersz po wierszu identyfikatorów sprzętu dla numerów IMEI i numerów seryjnych firmy Apple. W klasycznej konsoli usługi Intune można zaimportować szczegółowe informacje z pliku CSV i zastąpić nimi istniejące szczegółowe informacje dotyczące indywidualnych identyfikatorów sprzętu. Portal Azure udostępnia pojedynczą, zoptymalizowaną opcję, która automatycznie zastępuje szczegóły dotyczące wszystkich identyfikatorów sprzętu lub ignoruje nowe szczegóły dotyczące istniejących identyfikatorów.

#### <a name="how-this-affects-you"></a>Jaki to ma wpływ na Ciebie
W portalu Azure nie będziesz mieć możliwości ustalenia wiersz po wierszu, które urządzenia z numerem InternationaI Mobile Equipment (IMEI) należy zaktualizować. W klasycznej konsoli usługi Intune ta funkcja będzie nadal obsługiwana.

#### <a name="how-to-get-ready-for-this-change"></a>Jak przygotować się do tej zmiany
Ponieważ informujemy o tym z wyprzedzeniem, to jeśli ta zmiana dotyczy Ciebie, masz możliwość zwrócenia na nią uwagi administratorom. Ta zmiana zbiega się z przeniesieniem do portalu Azure przewidywanym w pierwszej połowie 2017 roku.


### <a name="support-for-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Obsługa domyślnych profilów rejestracji urządzeń firmowych usługi Apple DEP
Portal Azure nie obsługuje „domyślnego” profilu rejestracji urządzeń firmowych w odniesieniu do numerów seryjnych urządzeń programu Apple DEP (Device Enrollment Program) Ta dostępna w klasycznej konsoli usługi Intune funkcja przestaje być obsługiwana, aby zapobiec przypadkowo przypisanym profilom. W portalu Azure numery seryjne synchronizowane z kontem usługi Apple DEP nie będą początkowo miały przypisanego profilu rejestracji urządzeń firmowych.

#### <a name="how-this-affects-you"></a>Jaki to ma wpływ na Ciebie
W portalu Azure nie będziesz mieć możliwości ustawienia domyślnych zasad profilu wszystkich urządzeń firmy Apple. W klasycznej konsoli usługi Intune ta funkcja będzie nadal obsługiwana.

#### <a name="how-to-get-ready-for-this-change"></a>Jak przygotować się do tej zmiany
Ponieważ informujemy o tym z wyprzedzeniem, to jeśli ta zmiana dotyczy Ciebie, masz możliwość zwrócenia na nią uwagi administratorom. Ta zmiana zbiega się z przeniesieniem do portalu Azure przewidywanym w pierwszej połowie 2017 roku.



<!--HONumber=Feb17_HO1-->


