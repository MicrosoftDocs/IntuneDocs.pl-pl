---
title: Wersja wczesna | Microsoft Docs
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 18d47678b0fbdbd98502f2d3b469b202b567b2e7
ms.openlocfilehash: 3c7edc236878232c6f4c0ae993733c967946e765


---

# <a name="the-early-edition-for-microsoft-intune---january"></a>Wersja wczesna usługi Microsoft Intune — styczeń

**Wersja wczesna** zawiera listę funkcji, które zostaną wprowadzone w przyszłych wersjach usługi Microsoft Intune. Te informacje są przekazywane pod rygorem umowy NDA w bardzo ograniczonym zakresie i mogą ulec zmianie. Niektóre funkcje wymienione w tym miejscu mogą nie być wdrożone na czas i zostać opóźnione do przyszłych wersji. Inne funkcje są testowane w wersji pilotażowej, aby zapewnić przygotowanie ich do użytku przez klientów. W przypadku pytań lub wątpliwości skontaktuj się ze swoim partnerem ds. usługi Intune/PM.

Ta strona jest okresowo aktualizowana. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.

> [!Note]
> Dla usługi Intune opracowywane są następujące zmiany. Wszystkie te funkcje będą również w przyszłości obsługiwane dla hybrydowych wdrożeń klientów (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nowe możliwości

### <a name="actions-for-non-compliance---730266--"></a>Akcje w przypadku niezgodności <!--730266-->
_Akcje w przypadku niezgodności_ to nowa funkcja zasad zgodności, która umożliwia podejmowanie akcji na urządzeniach, które są niezgodne. Możesz określić jedną lub wiele akcji oraz przedział czasu, w którym te akcje muszą zostać wykonane. Na przykład możesz za pomocą poczty e-mail powiadomić użytkowników niezgodnych urządzeń, gdy tylko ich urządzenia staną się niezgodne, lub za pośrednictwem dostępu warunkowego zablokować niezgodnym urządzeniom dostęp do zasobów firmowych po 3-dniowym okresie karencji.

### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>Raporty w konsoli dotyczące zarządzania aplikacjami mobilnymi bez rejestracji <!--677961-->
Dodano nowe raporty ochrony aplikacji dla zarówno zarejestrowanych, jak i niezarejestrowanych urządzeń. Dowiedz się więcej na temat [monitorowania zasad zarządzania aplikacjami mobilnymi](https://docs.microsoft.com/en-us/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune).

### <a name="conditional-access-for-mam-with-sharepoint-online---679339--"></a>Dostęp warunkowy do zarządzania aplikacjami mobilnymi przy użyciu usługi SharePoint Online <!--679339-->
Można zablokować dostęp aplikacji nieobsługiwanych przez zasady zarządzania aplikacjami mobilnymi usługi Intune do usługi SharePoint Online.  Pracę z funkcją zarządzania aplikacjami mobilnymi w usłudze Intune można rozpocząć w witrynie Azure Portal. Wyszukaj sekcję __Dostęp warunkowy__ zawierającą opcję dla usługi SharePoint Online w bloku __Ustawienia__. Ta funkcja zostanie udostępniona oddzielnie od pozostałej części wersji usługi. <!--Find out more about this new feature [here](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online).-->

### <a name="android-711-support---694397--"></a>Obsługa systemu Android 7.1.1 <!--694397-->
Usługa Intune teraz w pełni obsługuje system Android 7.1.1 i zarządza nim.

## <a name="notices"></a>Uwagi

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Przyjmowanie wartości domyślnej zarządzania urządzeniami stacjonarnymi z systemem Windows za pomocą ustawień systemu Windows <!--663050-->
Domyślne zachowanie w przypadku rejestrowania komputerów z systemem Windows 10 ulega zmianie. W przypadku nowych rejestracji będzie stosowana typowa procedura rejestracji agenta MDM, a nie agenta komputerowego.

Na witrynie sieci Web Portal firmy użytkownikom komputerów stacjonarnych z systemem Windows 10 zostaną udostępnione instrukcje dotyczące rejestrowania, które przeprowadzą ich przez proces dodawania komputerów stacjonarnych z systemem Windows 10 jako urządzeń przenośnych. Nie będzie to miało wpływu na obecnie zarejestrowane komputery, a organizacja nadal będzie mogła zarządzać komputerami stacjonarnymi z systemem Windows 10 przy użyciu agenta komputerowego, [jeśli zechcesz](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Linki w aplikacji Portal dla systemu iOS są otwierane wewnątrz aplikacji <!--665954-->
Linki w aplikacji Portal firmy dla systemu iOS, w tym linki do dokumentacji i aplikacji, będą otwierane bezpośrednio w aplikacji Portal firmy przy użyciu widoku przeglądarki Safari w aplikacji. Ta aktualizacja zostanie udostępniona oddzielnie od aktualizacji usługi w styczniu.

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Ulepszona obsługa selektywnego czyszczenia danych przez zarządzanie aplikacjami mobilnymi <!--581242-->
Użytkownicy końcowi otrzymają dodatkowe wskazówki dotyczące odzyskiwania dostępu do danych służbowych w przypadku automatycznego usunięcia tych danych spowodowanego przez zasadę „Interwał offline przed wyczyszczeniem danych aplikacji”.<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="new-documentation-for-app-protection-policies---583398--"></a>Nowa dokumentacja dla zasad ochrony aplikacji <!--583398-->
Zaktualizowaliśmy dokumentację dla administratorów i deweloperów aplikacji, którzy chcą włączyć zasady ochrony aplikacji (znane jako zasady zarządzania aplikacjami mobilnymi) w swoich aplikacjach dla systemów iOS i Android przy użyciu narzędzia opakowującego aplikacje usługi Intune lub zestawu SDK aplikacji usługi Intune.

Zaktualizowano następujące artykuły:

* [Wybieranie sposobu przygotowania aplikacji do zarządzania aplikacjami mobilnymi w usłudze Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
* [Przygotowanie aplikacji systemu iOS do zarządzania aplikacjami mobilnymi za pomocą narzędzia opakowującego aplikacje w usłudze Intune](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
* [Wprowadzenie do zestawu SDK aplikacji usługi Microsoft Intune](https://docs.microsoft.com/intune/develop/intune-app-sdk-get-started)
* [Przewodnik dewelopera po zestawie SDK aplikacji usługi Intune dla systemu iOS](https://docs.microsoft.com/intune/develop/intune-app-sdk-ios)

Następujące artykuły są nowościami w bibliotece dokumentacji:

* [Wtyczka Cordova zestawu SDK aplikacji usługi Intune](https://docs.microsoft.com/intune/develop/intune-app-sdk-cordova)
* [Składnik Xamarin zestawu SDK aplikacji usługi Intune](https://docs.microsoft.com/intune/develop/intune-app-sdk-xamarin)

### <a name="progress-bar-when-launching-the-company-portal-on-ios---665978--"></a>Pasek postępu podczas uruchamiania aplikacji Portal firmy w systemie iOS <!--665978-->
W aplikacji Portal firmy dla systemu iOS wprowadzono pasek postępu na ekranie uruchamiania, aby przedstawić użytkownikowi informacje na temat procesów ładowania. Pasek postępu będzie wdrażany etapowo i zastąpi pokrętło. To oznacza, że niektórzy użytkownicy będą widzieć nowy pasek postępu, podczas gdy inni będą nadal widzieć pokrętło.

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Publiczna wersja zapoznawcza nowego środowiska administracyjnego usługi Intune na platformie Azure <!--736542-->

Na początku roku 2017 r. będziemy migrować nasze pełne środowisko administracyjne na platformę Azure, co umożliwi zaawansowane i zintegrowane zarządzanie podstawowymi przepływami pracy EMS na nowoczesnej platformie usług, którą można rozszerzyć za pomocą interfejsów API programu Graph.

Publiczna wersja zapoznawcza nowego środowiska administracyjnego będzie widoczna w nowych dzierżawach w wersji próbnej w witrynie Azure Portal w tym miesiącu. W wersji zapoznawczej możliwości istniejącej konsoli usługi Intune i spójność z nią będą udostępniane w sposób iteracyjny.

W środowisku administracyjnym w witrynie Azure Portal będzie używana już zapowiadana nowa funkcja grupowania i określania celu. W przypadku migrowania istniejącej dzierżawy do nowego środowiska grupowania nastąpi również migracja do nowego środowiska administracyjnego w wersji zapoznawczej w dzierżawie. Jeśli przed zakończeniem migrowania dzierżawy chcesz przetestować lub poznać dowolną nową funkcję, utwórz nowe konto wersji próbnej usługi Intune lub zapoznaj się z [nową dokumentacją](https://docs.microsoft.com/en-us/intune-azure/introduction/what-is-microsoft-intune).

Jeśli masz pytania dotyczące osi czasu migracji dzierżawy, skontaktuj się z zespołem ds. migracji pod adresem [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

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



<!--HONumber=Dec16_HO4-->


