---
title: Co nowego | Microsoft Docs
description: "Sprawdź, co nowego w tym miesiącu i poprzednich wersjach usługi Microsoft Intune"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: a9336e3d230de962d2623dd627e45c6e9262a822
ms.openlocfilehash: cfe4a0bb802956278387ac2a39d5316482e09332
ms.lasthandoff: 03/01/2017


---
# <a name="whats-new-in-microsoft-intune---february-2017"></a>Co nowego w usłudze Microsoft Intune — luty 2017 r.
Poznaj nowości w tej wersji usługi Microsoft Intune. Dowiedz się o nadchodzących zmianach, na które należy się przygotować, jak również uzyskaj informacje o poprzednich wersjach.

> [!Note]
> Wszystkie te funkcje będą również w przyszłości obsługiwane dla hybrydowych wdrożeń klientów (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nowe możliwości

### <a name="modernizing-the-company-portal-website---753980--"></a>Modernizowanie witryny sieci Web Portal firmy <!--753980-->
Witryna internetowa Portal firmy będzie obsługiwać aplikacje przeznaczone dla użytkowników, którzy nie mają zarządzanych urządzeń. Witryna internetowa zostanie zmieniona tak, aby wyglądała jak witryny innych produktów i usług firmy Microsoft, przy użyciu nowego schematu kontrastujących kolorów, ilustracji dynamicznych i menu typu „hamburger” ![Mały obraz menu typu „hamburger” dodanego w lewym górnym rogu witryny internetowej Portal firmy,](./media/CP_hamburger_menu.png) które będzie zawierać szczegółowe dane kontaktowe działu pomocy technicznej i informacje o istniejących urządzeniach zarządzanych. Układ strony docelowej zostanie zmieniony tak, aby wyróżnić aplikacje dostępne dla użytkowników, a aplikacje polecane i ostatnio zaktualizowane zostaną oznaczone symbolem karuzeli. Obrazy przedstawiające poprzednią i nową wersję są dostępne na [stronie aktualizacji interfejsu użytkownika](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="new-guided-experience-for-windows-10-company-portal---713927--"></a>Nowe środowisko z przewodnikiem dla Portalu firmy systemu Windows 10 <!--713927-->
Od marca Portal firmy dla systemu Windows 10 będzie zawierać wskazówki przewodnika usługi Intune dla urządzeń, które nie zostały zidentyfikowane ani zarejestrowane. Nowe środowisko obejmuje instrukcje krok po kroku dostosowane do kompilacji systemu Windows 10 użytkownika, które ułatwiają mu wykonanie rejestracji usługi AAD (wymaganej w celu identyfikacji funkcji dostępu warunkowego) i rejestracji MDM (wymaganej dla funkcji zarządzania urządzeniami). Środowisko z przewodnikiem będzie dostępne na stronie głównej Portalu firmy i jest opcjonalne; użytkownicy mogą nadal używać aplikacji, jeśli nie wykonają rejestracji, ale mogą wystąpić ograniczenia funkcjonalności.

## <a name="notices"></a>Uwagi

### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>Migracja grup nie wymaga żadnych aktualizacji grup ani zasad dotyczących urządzeń z systemem iOS <!--898837-->
W przypadku każdej grupy urządzeń w usłudze Intune, które są wstępnie przypisane przy użyciu profilu Rejestracja urządzeń firmowych, w usłudze AAD zostanie utworzona odpowiednia dynamiczna grupa urządzeń przy użyciu nazwy profilu Rejestracja urządzeń firmowych podczas migracji do grup urządzeń w usłudze Azure Active Directory. Dzięki temu rejestrowane urządzenia będą automatycznie grupowane i będą uzyskiwać te same zasady oraz aplikacje co grupa oryginalna w usłudze Intune.

Kiedy rozpocznie się proces migracji dzierżawy w zakresie grupowania i określania wartości docelowej, usługa Intune automatycznie utworzy dynamiczną grupę usługi AAD, która będzie odpowiadała grupie usługi Intune określonej jako docelowa przez profil Rejestracja urządzeń firmowych. Jeśli administrator usługi Intune usunie docelową grupę usługi Intune, odpowiadająca jej dynamiczna grupa usługi AAD nie zostanie usunięta. Członkowie tej grupy i zapytanie dynamiczne zostaną wyczyszczone, ale sama grupa jako całość zostanie pozostawiona do czasu, aż administrator IT usunie ją za pomocą portalu usługi AAD.

Podobnie — jeśli administrator IT zmieni docelową grupę usługi Intune dla profilu Rejestracja urządzeń firmowych, usługa Intune utworzy nową grupę dynamiczną odzwierciedlającą nowe przypisanie profilu, ale nie spowoduje usunięcia grupy dynamicznej utworzonej dla starego przypisania.

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Przyjmowanie wartości domyślnej zarządzania urządzeniami stacjonarnymi z systemem Windows za pomocą ustawień systemu Windows <!--663050-->
Domyślne zachowanie w przypadku rejestrowania komputerów z systemem Windows 10 ulega zmianie. W przypadku nowych rejestracji będzie stosowana typowa procedura rejestracji agenta MDM, a nie agenta komputerowego. Na witrynie sieci Web Portal firmy użytkownikom komputerów stacjonarnych z systemem Windows 10 zostaną udostępnione instrukcje dotyczące rejestrowania, które przeprowadzą ich przez proces dodawania komputerów stacjonarnych z systemem Windows 10 jako urządzeń przenośnych. Nie będzie to miało wpływu na obecnie zarejestrowane komputery, a organizacja nadal będzie mogła zarządzać komputerami stacjonarnymi z systemem Windows 10 przy użyciu agenta komputerowego, [jeśli zechcesz](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Ulepszona obsługa selektywnego czyszczenia danych przez zarządzanie aplikacjami mobilnymi <!--581242-->
Użytkownicy końcowi otrzymają dodatkowe wskazówki dotyczące odzyskiwania dostępu do danych służbowych w przypadku automatycznego usunięcia tych danych spowodowanego przez zasadę „Interwał offline przed wyczyszczeniem danych aplikacji”.<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Linki w aplikacji Portal dla systemu iOS są otwierane wewnątrz aplikacji <!--665954-->
Linki w aplikacji Portal firmy dla systemu iOS, w tym linki do dokumentacji i aplikacji, będą otwierane bezpośrednio w aplikacji Portal firmy przy użyciu widoku przeglądarki Safari w aplikacji. Ta aktualizacja zostanie udostępniona oddzielnie od aktualizacji usługi w styczniu.

### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Nowy adres serwera MDM dla urządzeń z systemem Windows <!--893007-->
Jeśli użytkownik wpisze ciąg __manage.microsoft.com__ jako adres serwera MDM (po wyświetleniu odpowiedniego monitu), próba zarejestrowania urządzenia z systemem Windows lub Windows Phone nie powiedzie się. Adres serwera MDM uległ zmianie z adresu __manage.microsoft.com__ na adres __enrollment.manage.microsoft.com__. Powiadom użytkownika, aby użył ciągu __enrollment.manage.microsoft.com__ jako adresu serwera MDM w przypadku wyświetlenia monitu podczas rejestrowania urządzenia z systemem Windows lub Windows Phone. Nie są wymagane żadne zmiany w konfiguracji CNAME. Aby uzyskać dodatkowe informacje o tej zmianie, odwiedź stronę [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange).

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nowe środowisko użytkownika aplikacji Portal firmy dla systemu Android <!--621622-->
Od marca aplikacja Portal firmy dla systemu Android będzie zgodna z [zaleceniami dotyczącymi projektowania materiałów](https://material.io/guidelines/material-design/introduction.html) w celu zapewnienia bardziej nowoczesnego wyglądu i działania. Udoskonalone środowisko użytkownika końcowego obejmuje między innymi następujące elementy:

* __Kolory__: nagłówkom kart można nadać kolory z palety kolorów niestandardowych.
* __Interfejs__: przyciski Polecane aplikacje i Wszystkie aplikacje na karcie Aplikacje zostały zaktualizowane. Przycisk Wyszukaj jest teraz przestawnym przyciskiem akcji.
* __Nawigacja__: na karcie Wszystkie aplikacje jest dostępny widok z kartami Polecane, Wszystkie i Kategorie w celu zapewnienia łatwiejszej nawigacji.
* __Usługa__: karty Moje urządzenia i Kontakt z działem IT są bardziej czytelne.

Obrazy przedstawiające poprzednią i nową wersję są dostępne na [stronie aktualizacji interfejsu użytkownika](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>Skojarzenie wielu narzędzi do zarządzania ze Sklepem Windows dla firm <!--926135-->
Wcześniej w przypadku wdrażania aplikacji ze Sklepu Windows dla firm za pomocą więcej niż jednego narzędzia do zarządzania można było skojarzyć ze Sklepem Windows dla firm tylko jedno z tych narzędzi. Teraz ze sklepem można skojarzyć wiele narzędzi do zarządzania (np. usługę Intune i program Configuration Manager). Aby uzyskać szczegółowe informacje, zobacz artykuł [Zarządzanie aplikacjami zakupionymi w Sklepie Windows dla firm za pomocą usługi Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune).

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Nowości w publicznej wersji zapoznawczej środowiska administracyjnego usługi Intune na platformie Azure <!--736542-->

Na początku roku 2017 r. będziemy migrować nasze pełne środowisko administracyjne na platformę Azure, co umożliwi zaawansowane i zintegrowane zarządzanie podstawowymi przepływami pracy EMS na nowoczesnej platformie usług, którą można rozszerzyć za pomocą interfejsów API programu Graph.

Publiczna wersja zapoznawcza nowego środowiska administracyjnego będzie widoczna w nowych dzierżawach w wersji próbnej w witrynie Azure Portal w tym miesiącu. W wersji zapoznawczej możliwości istniejącej konsoli usługi Intune i spójność z nią będą udostępniane w sposób iteracyjny.

W środowisku administracyjnym w witrynie Azure Portal będzie używana już zapowiadana nowa funkcja grupowania i określania celu. W przypadku migrowania istniejącej dzierżawy do nowego środowiska grupowania nastąpi również migracja do nowego środowiska administracyjnego w wersji zapoznawczej w dzierżawie. Jeśli przed zakończeniem migrowania dzierżawy chcesz przetestować lub poznać dowolną nową funkcję, utwórz nowe konto wersji próbnej usługi Intune lub zapoznaj się z [nową dokumentacją](https://docs.microsoft.com/intune-azure/introduction/whats-new).

Jeśli masz pytania dotyczące osi czasu migracji dzierżawy, skontaktuj się z zespołem ds. migracji pod adresem [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

Informacje na temat nowości w wersji zapoznawczej usługi Intune na platformie Azure znajdziesz [tutaj](https://docs.microsoft.com/intune-azure/introduction/whats-new).

## <a name="whats-coming"></a>Wkrótce

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Firma Apple będzie wymagać aktualizacji mechanizmu Application Transport Security <!--748318-->

Firma Apple ogłosiła, że począwszy od wiosny 2017 roku będzie egzekwować pewne wymagania dotyczące mechanizmu Application Transport Security (ATS). Mechanizm ATS służy do wymuszania mocniejszych zabezpieczeń całej komunikacji aplikacji za pośrednictwem protokołu HTTPS. Ta zmiana wpływa na klientów usługi Intune korzystających z aplikacji Portalu firmy w systemie iOS. Zapoznaj się z naszym [blogiem pomocy technicznej usługi Intune](https://aka.ms/compportalats), aby uzyskać więcej szczegółów. 

### <a name="see-also"></a>Zobacz także
* [Blog usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plan platformy w chmurze](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Co nowego w wersji zapoznawczej na platformie Azure](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Co nowego w interfejsie użytkownika aplikacji Portal firmy](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Archiwum nowości](whats-new-archive.md)

