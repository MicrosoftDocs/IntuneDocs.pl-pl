---
title: Co nowego | Microsoft Docs
description: "Sprawdź nowości w tym miesiącu i poprzednich wersjach usługi Microsoft Intune"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3ab53e40f4b7ea67733127f445005ecb77a404f7
ms.openlocfilehash: 37031eed6efa48ff52ec37a942fa77af414f78fe


---
# <a name="whats-new-in-microsoft-intune---january-2017"></a>Co nowego w usłudze Microsoft Intune — styczeń 2017 r.
Poznaj nowości w tej wersji usługi Microsoft Intune. Dowiedz się o nadchodzących zmianach, na które należy się przygotować, jak również uzyskaj informacje o poprzednich wersjach.

> [!Note]
> Wszystkie te funkcje będą również w przyszłości obsługiwane dla hybrydowych wdrożeń klientów (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nowe możliwości

<!--### Actions for non-compliance <!--730266
_Actions for non-compliance_ is a new feature of compliance policies that lets you take action on devices that are out of compliance. You can specify single or multiple actions and specify the time period at which those actions must occur. For example, you can notify users of non-compliant devices immediately after the devices become non-compliant through email, or you can block non-compliant devices from accessing corporate resources after a 3-day grace period via Conditional Access.-->

### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>Raporty w konsoli dotyczące zarządzania aplikacjami mobilnymi bez rejestracji <!--677961-->
Dodano nowe raporty ochrony aplikacji dla zarówno zarejestrowanych, jak i niezarejestrowanych urządzeń. Dowiedz się więcej na temat [monitorowania zasad zarządzania aplikacjami mobilnymi](https://docs.microsoft.com/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune).

<!--### Conditional access for MAM with SharePoint Online <!--679339
You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint Online.  You can get started using Intune mobile app management in the Azure portal. Look for the __Conditional Access__ section in the __Settings__ blade which will include the option for SharePoint Online. This feature will ship separately from the rest of the service release. <!--Find out more about this new feature [here](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online).-->

### <a name="android-711-support---694397--"></a>Obsługa systemu Android 7.1.1 <!--694397-->
Usługa Intune teraz w pełni obsługuje system Android 7.1.1 i zarządza nim.

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them---unknown--"></a>Rozwiązywanie problemów związanych z brakiem aktywności urządzeń z systemem iOS lub z brakiem możliwości komunikacji pomiędzy nimi a konsolą administracyjną <!--unknown-->
Gdy urządzenia użytkowników utracą połączenie z usługą Intune, można wykonać w odniesieniu do nich nowe kroki mające na celu rozwiązanie problemów w celu przywrócenia dostępu do zasobów firmy. Zobacz temat [Urządzenia są nieaktywne lub nie jest możliwe nawiązanie łączności między nimi a konsolą administracyjną](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="notices"></a>Uwagi

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Przyjmowanie wartości domyślnej zarządzania urządzeniami stacjonarnymi z systemem Windows za pomocą ustawień systemu Windows <!--663050-->
Domyślne zachowanie w przypadku rejestrowania komputerów z systemem Windows 10 ulega zmianie. W przypadku nowych rejestracji będzie stosowana typowa procedura rejestracji agenta MDM, a nie agenta komputerowego.

Na witrynie sieci Web Portal firmy użytkownikom komputerów stacjonarnych z systemem Windows 10 zostaną udostępnione instrukcje dotyczące rejestrowania, które przeprowadzą ich przez proces dodawania komputerów stacjonarnych z systemem Windows 10 jako urządzeń przenośnych. Nie będzie to miało wpływu na obecnie zarejestrowane komputery, a organizacja nadal będzie mogła zarządzać komputerami stacjonarnymi z systemem Windows 10 przy użyciu agenta komputerowego, [jeśli zechcesz](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

<!--### Company Portal for iOS links open inside the app <!--665954
Links inside of the Company Portal app for iOS, including those to documentation and apps, will open directly in the Company Portal app using an in-app view of Safari. This update will ship separately from the service update in January.-->

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Ulepszona obsługa selektywnego czyszczenia danych przez zarządzanie aplikacjami mobilnymi <!--581242-->
Użytkownicy końcowi otrzymają dodatkowe wskazówki dotyczące odzyskiwania dostępu do danych służbowych w przypadku automatycznego usunięcia tych danych spowodowanego przez zasadę „Interwał offline przed wyczyszczeniem danych aplikacji”.<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="modernizing-the-company-portal-website---753980--"></a>Modernizowanie witryny sieci Web Portal firmy <!--753980-->
Od lutego witryna sieci Web Portal firmy będzie obsługiwać aplikacje przeznaczone dla użytkowników, którzy nie mają zarządzanych urządzeń. Witryna sieci Web zostanie zmieniona tak, aby wyglądała jak witryny innych produktów i usług firmy Microsoft, przy użyciu nowego schematu kontrastujących kolorów, ilustracji dynamicznych i menu typu „hamburger” ![menu „hamburger” witryny sieci Web Portal firmy](../media/CP_hamburger_menu.png) oraz będzie zawierać szczegółowe dane kontaktowe działu pomocy technicznej i informacje o istniejących urządzeniach zarządzanych. Układ strony docelowej zostanie zmieniony tak, aby wyróżnić aplikacje dostępne dla użytkowników, a aplikacje polecane i ostatnio zaktualizowane zostaną oznaczone symbolem karuzeli. Obraz poprzedniej i nowej wersji witryny są dostępne w temacie [What's new in the Company Portal UI page](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui#January_2017) (Co nowego na stronie interfejsu użytkownika aplikacji Portal firmy).

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

<!--### Progress bar when launching the Company Portal on iOS <!--665978
The Company Portal for iOS is introducing a progress bar on the launch screen to provide the user with information about the loading processes that occur. There will be a phased rollout of the progress bar to replace the spinner. This means that some of your users will see the new progress bar while others will continue to see the spinner.-->

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Nowości w publicznej wersji zapoznawczej środowiska administracyjnego usługi Intune na platformie Azure <!--736542-->

Na początku roku 2017 r. będziemy migrować nasze pełne środowisko administracyjne na platformę Azure, co umożliwi zaawansowane i zintegrowane zarządzanie podstawowymi przepływami pracy EMS na nowoczesnej platformie usług, którą można rozszerzyć za pomocą interfejsów API programu Graph.

Publiczna wersja zapoznawcza nowego środowiska administracyjnego będzie widoczna w nowych dzierżawach w wersji próbnej w witrynie Azure Portal w tym miesiącu. W wersji zapoznawczej możliwości istniejącej konsoli usługi Intune i spójność z nią będą udostępniane w sposób iteracyjny.

W środowisku administracyjnym w witrynie Azure Portal będzie używana już zapowiadana nowa funkcja grupowania i określania celu. W przypadku migrowania istniejącej dzierżawy do nowego środowiska grupowania nastąpi również migracja do nowego środowiska administracyjnego w wersji zapoznawczej w dzierżawie. Jeśli przed zakończeniem migrowania dzierżawy chcesz przetestować lub poznać dowolną nową funkcję, utwórz nowe konto wersji próbnej usługi Intune lub zapoznaj się z [nową dokumentacją](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).

Jeśli masz pytania dotyczące osi czasu migracji dzierżawy, skontaktuj się z zespołem ds. migracji pod adresem [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

Informacje na temat nowości w wersji zapoznawczej usługi Intune na platformie Azure znajdziesz [tutaj](https://docs.microsoft.com/intune-azure/introduction/whats-new).

### <a name="see-also"></a>Zobacz także
* [Blog usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plan platformy w chmurze](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Co nowego w wersji zapoznawczej na platformie Azure](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Co nowego w interfejsie użytkownika aplikacji Portal firmy](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Archiwum nowości](whats-new-archive.md)



<!--HONumber=Jan17_HO4-->


