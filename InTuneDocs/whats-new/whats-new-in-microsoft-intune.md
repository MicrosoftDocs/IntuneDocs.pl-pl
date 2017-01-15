---
title: Co nowego | Microsoft Docs
description: "Sprawdź nowości w tym miesiącu i poprzednich wersjach usługi Microsoft Intune"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1d9ebc7fd727b80091625ed5256ae634323a9257
ms.openlocfilehash: f7e71d20923e113b533668a7b5aef688de196182


---
# <a name="whats-new-in-microsoft-intune---december-2016"></a>Co nowego w usłudze Microsoft Intune — grudzień 2016 r.
Poznaj nowości w tej wersji usługi Microsoft Intune. Dowiedz się o nadchodzących zmianach, na które należy się przygotować, jak również uzyskaj informacje o poprzednich wersjach.

> [!Note]
> Wszystkie te funkcje będą również w przyszłości obsługiwane dla hybrydowych wdrożeń klientów (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure--736542--"></a>Publiczna wersja zapoznawcza nowego środowiska administracyjnego usługi Intune na platformie Azure<!--736542-->
Na początku roku 2017 przeprowadzimy migrację pełnego środowiska administracyjnego na platformę Azure, co umożliwi zaawansowane i zintegrowane zarządzanie podstawowymi przepływami pracy EMS na nowoczesnej platformie usług, którą można rozszerzać za pomocą interfejsów API programu Graph. W związku z planami udostępnienia tego portalu wszystkim dzierżawcom usługi Intune z przyjemnością informujemy, że rozpoczynamy udostępnianie podglądu nowego środowiska administracyjnego jeszcze w tym miesiącu, aby wybrać dzierżawców.

W środowisku administracyjnym w witrynie Azure Portal będzie używana już zapowiadana nowa funkcja grupowania i określania celu. W przypadku migrowania istniejącej dzierżawy do nowego środowiska grupowania nastąpi również migracja do nowego środowiska administracyjnego w wersji zapoznawczej w dzierżawie. W międzyczasie możesz zapoznać się z naszą ofertą dotyczącą usługi Microsoft Intune w witrynie Azure Portal, korzystając z [nowej dokumentacji](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).

Jeśli masz pytania dotyczące osi czasu migracji dzierżawy, skontaktuj się z zespołem ds. migracji pod adresem [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integracja zarządzania kosztami telekomunikacyjnymi w publicznej wersji zapoznawczej witryny Azure Portal<!--747605-->
Obecnie rozpoczynamy pracę nad wersją zapoznawczą integracji z usługami zarządzania kosztami telekomunikacyjnymi innych firm w witrynie Azure Portal. Usługa Intune może być używana do wymuszania limitów użycia danych w kraju i w roamingu. Te operacje integracji rozpoczynamy od współpracy z firmą [Saaswedo](http://www.saaswedo.com). Aby włączyć tę funkcję w dzierżawie w wersji próbnej, [skontaktuj się z pomocą techniczną firmy Microsoft](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

## <a name="new-capabilities"></a>Nowe możliwości

### <a name="multi-factor-authentication-across-all-platforms---747590--"></a>Usługa Multi-Factor Authentication na wszystkich platformach <!--747590-->
Teraz można wymusić użycie usługi Multi-Factor Authentication (MFA) przez wybraną grupę użytkowników podczas rejestracji urządzeń z systemem iOS, Android, Windows 8.1+ lub Windows Phone 8.1+ w portalu zarządzania Azure. W tym celu należy skonfigurować usługę MFA w aplikacji rejestracji w usłudze Microsoft Intune w usłudze Azure Active Directory.

### <a name="ability-to-restrict-mobile-device-enrollment--747596--"></a>Możliwość ograniczenia rejestracji urządzeń przenośnych<!--747596-->
Usługa Intune dodaje nowe ograniczenia rejestracji, które pozwalają kontrolować, które platformy urządzeń przenośnych mogą być rejestrowane. Usługa Intune dzieli platformy urządzeń przenośnych na iOS, macOS, Android, Windows i Windows Mobile.
* Ograniczanie rejestracji urządzeń przenośnych nie ogranicza rejestracji klientów komputerów stacjonarnych.
* Tylko platforma iOS ma dodatkową opcję blokowania rejestracji urządzeń, które są własnością osobistą.

Intune oznacza wszystkie nowe urządzenia jako osobiste, chyba że administrator IT oznaczy je jako własność firmową, zgodnie z opisem [w tym artykule](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).


## <a name="notices"></a>Uwagi

### <a name="multi-factor-authentication-on-enrollment-moving-to-the-azure-portal---vso-750545--"></a>Użycie usługi Multi-Factor Authentication podczas rejestracji przeniesione do witryny Azure Portal <!--VSO 750545-->
Wcześniej w celu skonfigurowania usługi MFA na potrzeby rejestracji w usłudze Intune administratorzy musieli przejść do konsoli usług Intune lub konsoli programu Configuration Manager (wersje wydane przed październikiem 2016). Dzięki zaktualizowanej funkcji teraz należy zalogować się do witryny [Microsoft Azure Portal](https://manage.windowsazure.com) przy użyciu poświadczeń usługi Intune i skonfigurować ustawienia usługi MFA za pośrednictwem usługi Azure AD. Więcej informacji na ten temat można znaleźć [tutaj](https://aka.ms/mfa_ad).

### <a name="company-portal-app-for-android-now-available-in-china--vso-658093--"></a>Aplikacja Portal firmy dla systemu Android jest teraz dostępna w Chinach <!--VSO 658093-->
Obecnie publikujemy aplikację Portal firmy dla systemu Android możliwą do pobierania na terenie Chin. Z powodu braku sklepu Google Play w Chinach aplikacje dla urządzeń z systemem Android należy uzyskiwać z chińskich platform handlowych oferujących aplikacje. Aplikacja Portal firmy dla systemu Android będzie dostępna do pobrania w następujących sklepach:
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

Aplikacja Portal firmy dla systemu Android używa usług Google Play do komunikowania się z usługą Microsoft Intune. Ponieważ usługi Google Play nie są jeszcze dostępne w Chinach, wykonanie dowolnego z wymienionych poniżej zadań może potrwać do 8 godzin. 

|Konsola administracyjna usługi Intune| Aplikacja Portal firmy w usłudze Intune dla systemu Android |Witryna aplikacji Portal firmy w usłudze Intune|   
|---|---|---|
|Pełne czyszczenie danych| Usuwanie urządzenia zdalnego| Usuwanie urządzenia (lokalnego i zdalnego)|
|Selektywne czyszczenie danych| Resetowanie urządzenia| Resetowanie urządzenia|
|Wdrażanie nowych lub zaktualizowanych aplikacji| Instalowanie dostępnych aplikacji biznesowych| Resetowanie kodu dostępu urządzenia|
|Zdalne blokowanie|||
|Resetowanie kodu dostępu|||

## <a name="deprecations"></a>Zakończenie obsługi

### <a name="firefox-to-no-longer-support-silverlight--vso-tba--"></a>Przeglądarka Firefox nie obsługuje już programu Silverlight<!--VSO TBA-->
Mozilla rezygnuje z obsługi technologii Silverlight w wersji 52 [przeglądarki Firefox](https://www.mozilla.org/firefox), począwszy od marca 2017 r. W związku z tym nie będzie można zalogować się do istniejącej konsoli usługi Intune za pomocą przeglądarki Firefox w wersjach nowszych niż 51. W celu uzyskania dostępu do konsoli administracyjnej zaleca się korzystanie z programu Internet Explorer 10 i 11 lub [wersji przeglądarki Firefox niższej niż 52](https://ftp.mozilla.org/pub/firefox/releases/). Przejście usługi Intune do witryny Azure Portal umożliwi obsługę wielu [nowoczesnych przeglądarek](https://docs.microsoft.com/en-us/azure/azure-preview-portal-supported-browsers-devices) bez konieczności korzystania z technologii Silverlight.

### <a name="removal-of-exchange-online-mobile-inbox-policies---770687--"></a>Usuwanie zasad mobilnej skrzynki odbiorczej usługi Exchange Online <!--770687-->
Od grudnia administratorzy nie będą już mogli wyświetlać ani konfigurować zasad dotyczących mobilnych skrzynek pocztowych usługi Exchange Online (EAS) w konsoli usługi Intune. Ta zmiana zostanie wdrożona we wszystkich dzierżawach usługi Intune w grudniu i styczniu. Wszystkie istniejące skonfigurowane zasady pozostaną niezmienione; w przypadku konfigurowania nowych zasad trzeba będzie korzystać z powłoki zarządzania serwerem Exchange. Więcej informacji można znaleźć [tutaj](https://technet.microsoft.com/en-us/library/bb123783%28v=exchg.150%29.aspx).

### <a name="intune-av-player-image-viewer-and-pdf-viewer-apps-are-no-longer-supported-on-android---747553--"></a>Aplikacje Intune AV Player, Image Viewer i PDF Viewer nie są już obsługiwane w systemie Android <!--747553-->
Od połowy grudnia 2016 r. użytkownicy nie będą już mogli korzystać z aplikacji Intune AV Player, Image Viewer i PDF Viewer. Te aplikacje zostały zastąpione przez aplikację Azure Information Protection. Więcej informacji na temat aplikacji Azure Information Protection można znaleźć [tutaj](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq).

### <a name="see-also"></a>Zobacz także
* [Blog usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plan platformy w chmurze](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Archiwum nowości](whats-new-archive.md)



<!--HONumber=Dec16_HO4-->


