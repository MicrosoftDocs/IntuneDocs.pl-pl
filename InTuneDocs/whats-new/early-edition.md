---
title: Wersja wczesna | Microsoft Docs
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: d0b3a883bb307fb06cb8d16500798086f328314a
ms.openlocfilehash: eeebf8b6b3bc5c7c35386eb20c96097af1f6769c
ms.lasthandoff: 02/14/2017


---


# <a name="the-early-edition-for-microsoft-intune---february-2017"></a>Wersja wczesna usługi Microsoft Intune — luty 2017

**Wersja wczesna** zawiera listę funkcji, które zostaną wprowadzone w przyszłych wersjach usługi Microsoft Intune. Te informacje są przekazywane pod rygorem umowy NDA w bardzo ograniczonym zakresie i mogą ulec zmianie. Niektóre funkcje wymienione w tym miejscu mogą nie być wdrożone na czas i zostać opóźnione do przyszłych wersji. Inne funkcje są testowane w wersji pilotażowej, aby zapewnić przygotowanie ich do użytku przez klientów. W przypadku pytań lub wątpliwości skontaktuj się ze swoim partnerem ds. usługi Intune/PM.

Ta strona jest okresowo aktualizowana. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.

> [!Note]
> Dla usługi Intune opracowywane są następujące zmiany. Wszystkie te funkcje będą również w przyszłości obsługiwane dla hybrydowych wdrożeń klientów (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nowe możliwości

### <a name="modernizing-the-company-portal-website---753980--"></a>Modernizowanie witryny sieci Web Portal firmy <!--753980-->
Od lutego wygląd witryny internetowej Portal firmy zostanie zmieniony tak, aby wyglądał jak witryny innych produktów i usług firmy Microsoft, przy użyciu nowego schematu kontrastujących kolorów, ilustracji dynamicznych i menu typu „hamburger” ![Mały obraz menu typu „hamburger” dodanego w lewym górnym rogu witryny internetowej Portal firmy](./media/CP_hamburger_menu.png), które będzie zawierać szczegółowe dane kontaktowe działu pomocy technicznej i informacje o istniejących urządzeniach zarządzanych. Układ strony docelowej zostanie zmieniony tak, aby wyróżnić aplikacje dostępne dla użytkowników, a aplikacje polecane i ostatnio zaktualizowane zostaną oznaczone symbolem karuzeli. Obrazy przedstawiające poprzednią i nową wersję są dostępne na [stronie aktualizacji interfejsu użytkownika](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="new-guided-experience-for-windows-10-company-portal---713927--"></a>Nowe środowisko z przewodnikiem dla Portalu firmy systemu Windows 10 <!--713927-->
Od marca Portal firmy dla systemu Windows 10 będzie zawierać wskazówki przewodnika usługi Intune dla urządzeń, które nie zostały zidentyfikowane ani zarejestrowane. Nowe środowisko obejmuje instrukcje krok po kroku dostosowane do kompilacji systemu Windows 10 użytkownika, które ułatwiają mu wykonanie rejestracji usługi AAD (wymaganej w celu identyfikacji funkcji dostępu warunkowego) i rejestracji MDM (wymaganej dla funkcji zarządzania urządzeniami). Środowisko z przewodnikiem będzie dostępne na stronie głównej Portalu firmy i jest opcjonalne; użytkownicy mogą nadal używać aplikacji, jeśli nie wykonają rejestracji, ale mogą wystąpić ograniczenia funkcjonalności.

###

## <a name="notices"></a>Uwagi

### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>Migracja grup nie wymaga żadnych aktualizacji grup ani zasad dotyczących urządzeń z systemem iOS <!--898837-->
W przypadku każdej grupy urządzeń w usłudze Intune, które są wstępnie przypisane przy użyciu profilu Rejestracja urządzeń firmowych, w usłudze AAD zostanie utworzona odpowiednia dynamiczna grupa urządzeń przy użyciu nazwy profilu Rejestracja urządzeń firmowych podczas migracji do grup urządzeń w usłudze Azure Active Directory. Dzięki temu rejestrowane urządzenia będą automatycznie grupowane i będą uzyskiwać te same zasady oraz aplikacje co grupa oryginalna w usłudze Intune.

Kiedy rozpocznie się proces migracji dzierżawy w zakresie grupowania i określania wartości docelowej, usługa Intune automatycznie utworzy dynamiczną grupę usługi AAD, która będzie odpowiadała grupie usługi Intune określonej jako docelowa przez profil Rejestracja urządzeń firmowych. Jeśli administrator usługi Intune usunie docelową grupę usługi Intune, odpowiadająca jej dynamiczna grupa usługi AAD nie zostanie usunięta. Członkowie tej grupy i zapytanie dynamiczne zostaną wyczyszczone, ale sama grupa jako całość zostanie pozostawiona do czasu, aż administrator IT usunie ją za pomocą portalu usługi AAD.

Podobnie — jeśli administrator IT zmieni docelową grupę usługi Intune dla profilu Rejestracja urządzeń firmowych, usługa Intune utworzy nową grupę dynamiczną odzwierciedlającą nowe przypisanie profilu, ale nie spowoduje usunięcia grupy dynamicznej utworzonej dla starego przypisania.

### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Nowy adres serwera MDM dla urządzeń z systemem Windows <!--893007-->
Jeśli użytkownik wpisze ciąg __manage.microsoft.com__ jako adres serwera MDM (po wyświetleniu odpowiedniego monitu), próba zarejestrowania urządzenia z systemem Windows lub Windows Phone nie powiedzie się. Adres serwera MDM uległ zmianie z adresu __manage.microsoft.com__ na adres __enrollment.manage.microsoft.com__. Powiadom użytkownika, aby użył ciągu __enrollment.manage.microsoft.com__ jako adresu serwera MDM w przypadku wyświetlenia monitu podczas rejestrowania urządzenia z systemem Windows lub Windows Phone. Ta aktualizacja wymaga, aby każdy rekord CNAME, który znajduje się w systemie DNS i przekierowuje domenę __EnterpriseEnrollment.contoso.com__ do domeny __manage.microsoft.com__, został zastąpiony w systemie DNS rekordem CNAME, który przekierowuje domenę __EnterpriseEnrollment.contoso.com__ do domeny __EnterpriseEnrollment-s.manage.microsoft.com__. Aby uzyskać dodatkowe informacje o tej zmianie, odwiedź stronę [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange).

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nowe środowisko użytkownika aplikacji Portal firmy dla systemu Android <!--621622-->
Od marca aplikacja Portal firmy dla systemu Android będzie zgodna z [zaleceniami dotyczącymi projektowania materiałów](https://material.io/guidelines/material-design/introduction.html) w celu zapewnienia bardziej nowoczesnego wyglądu i działania. Udoskonalone środowisko użytkownika końcowego obejmuje między innymi następujące elementy:

* __Kolory__: nagłówkom kart można nadać kolory z palety kolorów niestandardowych.
* __Interfejs__: przyciski Polecane aplikacje i Wszystkie aplikacje na karcie Aplikacje zostały zaktualizowane. Przycisk Wyszukaj jest teraz przestawnym przyciskiem akcji.
* __Nawigacja__: na karcie Wszystkie aplikacje jest dostępny widok z kartami Polecane, Wszystkie i Kategorie w celu zapewnienia łatwiejszej nawigacji.
* __Usługa__: karty Moje urządzenia i Kontakt z działem IT są bardziej czytelne.

Obrazy przedstawiające poprzednią i nową wersję są dostępne na [stronie aktualizacji interfejsu użytkownika](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>Skojarzenie wielu narzędzi do zarządzania ze Sklepem Windows dla firm <!--926135-->
Wcześniej w przypadku wdrażania aplikacji ze Sklepu Windows dla firm za pomocą więcej niż jednego narzędzia do zarządzania można było skojarzyć ze Sklepem Windows dla firm tylko jedno z tych narzędzi. Teraz ze sklepem można skojarzyć wiele narzędzi do zarządzania (np. usługę Intune i program Configuration Manager). Aby uzyskać szczegółowe informacje, zobacz artykuł [Zarządzanie aplikacjami zakupionymi w Sklepie Windows dla firm za pomocą usługi Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune).

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Publiczna wersja zapoznawcza nowego środowiska administracyjnego usługi Intune na platformie Azure <!--736542-->

Na początku roku 2017 r. będziemy migrować nasze pełne środowisko administracyjne na platformę Azure, co umożliwi zaawansowane i zintegrowane zarządzanie podstawowymi przepływami pracy EMS na nowoczesnej platformie usług, którą można rozszerzyć za pomocą interfejsów API programu Graph.

Publiczna wersja zapoznawcza nowego środowiska administracyjnego będzie widoczna w nowych dzierżawach w wersji próbnej w witrynie Azure Portal w tym miesiącu. W wersji zapoznawczej możliwości istniejącej konsoli usługi Intune i spójność z nią będą udostępniane w sposób iteracyjny.

W środowisku administracyjnym w witrynie Azure Portal będzie używana już zapowiadana nowa funkcja grupowania i określania celu. W przypadku migrowania istniejącej dzierżawy do nowego środowiska grupowania nastąpi również migracja do nowego środowiska administracyjnego w wersji zapoznawczej w dzierżawie. Jeśli przed zakończeniem migrowania dzierżawy chcesz przetestować lub poznać dowolną nową funkcję, utwórz nowe konto wersji próbnej usługi Intune lub zapoznaj się z [nową dokumentacją](https://docs.microsoft.com/en-us/intune-azure/introduction/what-is-microsoft-intune).

Jeśli masz pytania dotyczące osi czasu migracji dzierżawy, skontaktuj się z zespołem ds. migracji pod adresem [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="february-2017"></a>Luty 2017

#### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Możliwość ograniczenia rejestracji urządzeń przenośnych <!--747600, 795782-->
Usługa Intune dodaje nowe ograniczenia rejestracji, które pozwalają kontrolować, które platformy urządzeń przenośnych mogą być rejestrowane. Usługa Intune dzieli platformy urządzeń przenośnych na iOS, macOS, Android, Windows i Windows Mobile.

* Ograniczanie rejestracji urządzeń przenośnych nie ogranicza rejestracji klientów komputerów stacjonarnych.  
* Tylko w przypadku systemu iOS i Android istnieje dodatkowa opcja blokowania rejestracji urządzeń, które są własnością osobistą.

Intune oznacza wszystkie nowe urządzenia jako osobiste, chyba że administrator IT oznaczy je jako własność firmową, zgodnie z opisem [w tym artykule](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).

#### <a name="view-all-actions-on-managed-devices---677150--"></a>Wyświetlanie wszystkich akcji na urządzeniach zarządzanych <!--677150-->
Nowy raport __Akcje urządzenia__ pokazuje, kto wykonał akcje zdalne, takie jak przywrócenie stanu fabrycznego na urządzeniach, a ponadto wyświetla stan takich akcji.

#### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Urządzenia niezarządzane mają dostęp do przypisanych aplikacji <!--664691-->
W ramach zmian wyglądu witryny internetowej Portal firmy użytkownicy systemów iOS i Android będą mogli instalować na swoich urządzeniach niezarządzanych aplikacje przypisane im jako „dostępne bez rejestracji”. Przy użyciu poświadczeń usługi Intune użytkownicy mogą zalogować się do witryny internetowej Portal firmy i wyświetlić listę przypisanych im aplikacji. Pakiety aplikacji oznaczonych jako „dostępne bez rejestracji” są udostępniane do pobrania za pośrednictwem witryny internetowej Portal firmy. Ta zmiana nie ma wpływu na aplikacje, które wymagają rejestracji na potrzeby instalacji, ponieważ użytkownicy, którzy zechcą zainstalować te aplikacje, zobaczą monit o zarejestrowanie ich urządzenia.

#### <a name="custom-app-categories---748805--"></a>Niestandardowe kategorie aplikacji <!--748805-->
Możesz teraz tworzyć, edytować i przypisywać kategorie dla aplikacji dodawanych do usługi Intune. Obecnie kategorie można określać tylko w języku angielskim.
Zobacz [Jak dodać aplikację do usługi Intune](/intune-azure/manage-apps/add-apps).

#### <a name="display-device-categories---814654--"></a>Wyświetlanie kategorii urządzeń <!--814654-->
Kategorię urządzenia można teraz wyświetlić jako kolumnę na liście urządzeń. Można także edytować kategorię z poziomu sekcji właściwości w bloku właściwości urządzenia.

### <a name="january-2017"></a>Styczeń 2017

#### <a name="custom-app-categories---748805--"></a>Niestandardowe kategorie aplikacji <!--748805-->
Możesz teraz tworzyć, edytować i przypisywać kategorie dla aplikacji dodawanych do usługi Intune. Obecnie kategorie można określać tylko w języku angielskim.

#### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748803--"></a>Przypisywanie aplikacji biznesowych niezależnie od tego, czy urządzenia są zarejestrowane <!--748803-->
Możesz teraz przypisywać użytkownikom aplikacje biznesowe ze sklepu niezależnie od tego, czy ich urządzenia są zarejestrowane w usłudze Intune. Jeśli urządzenie użytkownika nie jest zarejestrowane w usłudze Intune, aby ją zainstalować, użytkownik musi przejść do witryny sieci Web Portal firmy, a nie do aplikacji Portal firmy.

### <a name="december-2016"></a>Grudzień 2016

#### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integracja zarządzania kosztami telekomunikacyjnymi w publicznej wersji zapoznawczej witryny Azure Portal<!--747605-->
Obecnie rozpoczynamy pracę nad wersją zapoznawczą integracji z usługami zarządzania kosztami telekomunikacyjnymi innych firm w witrynie Azure Portal. Usługa Intune może być używana do wymuszania limitów użycia danych w kraju i w roamingu. Te operacje integracji rozpoczynamy od współpracy z firmą [Saaswedo](http://www.saaswedo.com). Aby włączyć tę funkcję w dzierżawie w wersji próbnej, [skontaktuj się z pomocą techniczną firmy Microsoft](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

### <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new-in-microsoft-intune.md).

