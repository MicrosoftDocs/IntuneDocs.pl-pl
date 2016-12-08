---
title: Wersja wczesna | Microsoft Intune
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6dd584397451d38be86fa0780efff435ffb9b2af
ms.openlocfilehash: d70ebf87bc930f853741ddc0d572d2174c636dac


---

# <a name="the-early-edition-for-microsoft-intune---december"></a>Wersja wczesna usługi Microsoft Intune — grudzień

**Wersja wczesna** zawiera listę funkcji, które zostaną wprowadzone w przyszłych wersjach usługi Microsoft Intune. Te informacje są przekazywane pod rygorem umowy NDA w bardzo ograniczonym zakresie i mogą ulec zmianie. Niektóre funkcje wymienione w tym miejscu mogą nie być wdrożone na czas i zostać opóźnione do przyszłych wersji. Inne funkcje są testowane w wersji pilotażowej, aby zapewnić przygotowanie ich do użytku przez klientów. W przypadku pytań lub wątpliwości skontaktuj się ze swoim partnerem ds. usługi Intune/PM.

Ta strona jest okresowo aktualizowana. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.

Dla usługi Intune opracowywane są następujące zmiany. Wszystkie te funkcje będą również w przyszłości obsługiwane dla hybrydowych wdrożeń klientów (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

<!--736542-->
## <a name="public-preview-of-the-new-intune-admin-experience-on-azure"></a>Publiczna wersja zapoznawcza nowego środowiska administracyjnego usługi Intune na platformie Azure

Na początku roku 2017 r. będziemy migrować nasze pełne środowisko administracyjne na platformę Azure, co umożliwi zaawansowane i zintegrowane zarządzanie podstawowymi przepływami pracy EMS na nowoczesnej platformie usług, którą można rozszerzyć za pomocą interfejsów API programu Graph.

Publiczna wersja zapoznawcza nowego środowiska administracyjnego będzie widoczna w nowych dzierżawach w wersji próbnej w witrynie Azure Portal w tym miesiącu. W wersji zapoznawczej możliwości istniejącej konsoli usługi Intune i spójność z nią będą udostępniane w sposób iteracyjny.

W środowisku administracyjnym w witrynie Azure Portal będzie używana już zapowiadana nowa funkcja grupowania i określania celu. W przypadku migrowania istniejącej dzierżawy do nowego środowiska grupowania nastąpi również migracja do nowego środowiska administracyjnego w wersji zapoznawczej w dzierżawie. Jeśli przed zakończeniem migrowania dzierżawy chcesz przetestować lub poznać dowolną nową funkcję, utwórz nowe konto wersji próbnej usługi Intune lub zapoznaj się z nową dokumentacją.

Jeśli masz pytania dotyczące osi czasu migracji dzierżawy, skontaktuj się z zespołem ds. migracji pod adresem [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integracja zarządzania kosztami telekomunikacyjnymi w publicznej wersji zapoznawczej witryny Azure Portal<!--747605-->
Obecnie rozpoczynamy pracę nad wersją zapoznawczą integracji z usługami zarządzania kosztami telekomunikacyjnymi innych firm w witrynie Azure Portal. Usługa Intune może być używana do wymuszania limitów użycia danych w kraju i w roamingu. Te operacje integracji rozpoczynamy od współpracy z firmą [Saaswedo](http://www.saaswedo.com).

## <a name="new-capabilities"></a>Nowe możliwości

### <a name="multi-factor-authentication-across-all-platforms---747590--"></a>Usługa Multi-Factor Authentication na wszystkich platformach <!--747590-->
Teraz można wymusić użycie usługi Multi-Factor Authentication (MFA) przez wybraną grupę użytkowników podczas rejestracji urządzeń z systemem iOS, Android, Windows 8.1+ lub Windows Phone 8.1+ w portalu zarządzania Azure. W tym celu należy skonfigurować usługę MFA w aplikacji rejestracji w usłudze Microsoft Intune w usłudze Azure Active Directory.

### <a name="conditional-access-for-mam-with-sharepoint-online---vso-679339--"></a>Dostęp warunkowy do zarządzania aplikacjami mobilnymi przy użyciu usługi SharePoint Online <!--VSO 679339-->
Można zablokować dostęp aplikacji nieobsługiwanych przez zasady zarządzania aplikacjami mobilnymi usługi Intune do usługi SharePoint Online.  Pracę z funkcją zarządzania aplikacjami mobilnymi w usłudze Intune można rozpocząć w witrynie Azure Portal. Wyszukaj sekcję __Dostęp warunkowy__ zawierającą opcję dla usługi SharePoint Online w bloku __Ustawienia__. Ta funkcja zostanie udostępniona oddzielnie od pozostałej części wersji usługi.

### <a name="ability-to-restrict-intune-mobile-device-enrollment"></a>Możliwość ograniczenia rejestracji urządzeń przenośnych Intune
Usługa Intune dodaje nowe ograniczenia rejestracji, które pozwalają kontrolować, które platformy urządzeń przenośnych mogą być rejestrowane. Usługa Intune dzieli platformy urządzeń przenośnych na iOS, macOS, Android, Windows i Windows Mobile. 
* Platformy macOS i Windows 8.1 lub nowsze mogą mieć ograniczoną możliwość rejestrowania jako platformy urządzeń przenośnych. 
* Ograniczanie rejestracji urządzeń przenośnych nie ogranicza rejestracji agenta komputerowego. 
* Tylko platforma iOS ma dodatkową opcję blokowania rejestracji urządzeń, które są własnością osobistą. Intune oznacza wszystkie nowe urządzenia jako osobiste, chyba że administrator IT oznaczy je jako własność firmową, zgodnie z opisem [w tym artykule](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).


## <a name="notices"></a>Uwagi

### <a name="multi-factor-authentication-on-enrollment-moving-to-the-azure-portal---vso-750545--"></a>Użycie usługi Multi-Factor Authentication podczas rejestracji przeniesione do witryny Azure Portal <!--VSO 750545-->
Wcześniej w celu ustawienia usługi MFA na potrzeby rejestracji w usłudze Intune administratorzy musieli przejść do konsoli usług Intune lub konsoli programu Configuration Manager (wydania starsze niż 1610). Dzięki zaktualizowanej funkcji teraz należy zalogować się do witryny [Microsoft Azure Portal](https://manage.windowsazure.com) przy użyciu poświadczeń usługi Intune i skonfigurować ustawienia usługi MFA za pośrednictwem usługi Azure AD. Więcej informacji na ten temat można znaleźć [tutaj](https://aka.ms/mfa_ad).

### <a name="company-portal-app-for-android-now-available-in-china---vso-658093--"></a>Aplikacja Portal firmy dla systemu Android jest teraz dostępna w Chinach <!--VSO 658093-->
Obecnie publikujemy aplikację Portal firmy dla systemu Android możliwą do pobierania na terenie Chin. Z powodu braku sklepu Google Play w Chinach aplikacje dla urządzeń z systemem Android należy uzyskiwać z chińskich platform handlowych oferujących aplikacje. Aplikacja Portal firmy dla systemu Android będzie dostępna do pobrania na platformach 360, Tencent, Xiaomi, Wandoujia i Huawei. 

Aplikacja Portal firmy dla systemu Android używa usług Google Play do komunikowania się z usługą Microsoft Intune. Ponieważ usługi Google Play nie są jeszcze dostępne w Chinach, wykonanie dowolnego z wymienionych poniżej zadań może potrwać do 8 godzin. 

|Konsola administracyjna usługi Intune| Aplikacja Portal firmy w usłudze Intune dla systemu Android |Witryna aplikacji Portal firmy w usłudze Intune|   
|---|---|---|
|Pełne czyszczenie danych| Usuwanie urządzenia zdalnego| Usuwanie urządzenia (lokalnego i zdalnego)|
|Selektywne czyszczenie danych| Resetowanie urządzenia| Resetowanie urządzenia|
|Wdrażanie nowych lub zaktualizowanych aplikacji| Instalowanie dostępnych aplikacji biznesowych| Resetowanie kodu dostępu urządzenia|
|Zdalne blokowanie|||
|Resetowanie kodu dostępu|||

## <a name="deprecations"></a>Zakończenie obsługi

### <a name="removal-of-exchange-online-mobile-inbox-policies---770687--"></a>Usuwanie zasad mobilnej skrzynki odbiorczej usługi Exchange Online <!--770687-->
Od grudnia administratorzy nie będą już mogli wyświetlać ani konfigurować zasad dotyczących mobilnych skrzynek pocztowych usługi Exchange Online (EAS) w konsoli usługi Intune. Ta zmiana zostanie wdrożona we wszystkich dzierżawach usługi Intune w grudniu i styczniu. Wszystkie istniejące skonfigurowane zasady pozostaną niezmienione; w przypadku konfigurowania nowych zasad trzeba będzie korzystać z powłoki zarządzania serwerem Exchange. Więcej informacji można znaleźć [tutaj](https://technet.microsoft.com/en-us/library/bb123783%28v=exchg.150%29.aspx).

### <a name="intune-av-player-image-viewer-and-pdf-viewer-apps-are-no-longer-supported-on-android---747553--"></a>Aplikacje Intune AV Player, Image Viewer i PDF Viewer nie są już obsługiwane w systemie Android <!--747553-->
Od połowy grudnia 2016 r. użytkownicy nie będą już mogli korzystać z aplikacji Intune AV Player, Image Viewer i PDF Viewer. Te aplikacje zostały zastąpione przez aplikację Azure Information Protection. Więcej informacji na temat aplikacji Azure Information Protection można znaleźć [tutaj](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq).

### <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new-in-microsoft-intune.md).



<!--HONumber=Nov16_HO5-->


