---
title: dołączanie pliku
description: dołączanie pliku
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: d907c5256469e86410c9916d117d3e322d43cfc3
ms.sourcegitcommit: 2614d1b08b8a78cd792aebd2ca9848f391df8550
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/11/2019
ms.locfileid: "67812509"
---
Te powiadomienia zawierają ważne informacje, które mogą ułatwić przygotowanie się na nadchodzące zmiany i nowe funkcje w usłudze Intune. 

### <a name="update-your-android-company-portal-app-to-the-latest-version---4536963--"></a>Aktualizacja aplikacji Portal firmy dla systemu Android do najnowszej wersji <!--4536963-->
W ramach usługi Intune okresowo wydawane są aktualizacje aplikacji Portal firmy dla systemu Android. W listopadzie 2018 roku opublikowaliśmy aktualizację portalu firmy, która uwzględnia przełącznik zaplecza, aby przygotować się do zmiany wprowadzonej przez firmę Google, która przechodzi ze swojej dotychczasowej platformy powiadomień do usługi Google Firebase Cloud Messaging (FCM). Po wycofaniu przez Google obecnej platformy powiadomień i przejściu do usługi FCM użytkownicy końcowi będą musieli zaktualizować swoją aplikację portalu firmy do wersji z listopada 2018 r. lub nowszej, aby zachować możliwość komunikowania się ze sklepem Google Play.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Nasza telemetria wskazuje, że masz urządzenia z aplikacją Portal firmy w wersji wcześniejszej niż 5.0.4269.0. Jeśli ta lub nowsza wersja aplikacji portalu firmy nie zostanie zainstalowana, akcje inicjowane na urządzeniu przez specjalistę IT, takie jak czyszczenie, resetowanie hasła, instalowanie dostępnych i wymaganych aplikacji oraz rejestrowanie certyfikatów mogą nie działać zgodnie z oczekiwaniami. Jeśli Twoje urządzenia są zarejestrowane w usłudze Intune za pomocą rozwiązania MDM, wersje aplikacji portalu firmy oraz użytkowników możesz wyświetlić, przechodząc do obszaru Aplikacje klienckie — Odnalezione aplikacje. Wybierając wcześniejsze wersje aplikacji Portal firmy, będzie można zobaczyć, którzy użytkownicy końcowi mają urządzenia z niezaktualizowaną wersją portalu firmy.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Poproś użytkowników końcowych urządzeń z systemem Android, które nie zostały zaktualizowane, aby zaktualizowali portal firmy za pośrednictwem sklepu Google Play. Powiadom dział pomocy technicznej w przypadku, gdy użytkownik nie ma wybranej opcji automatycznego aktualizowania aplikacji portalu firmy. Skorzystaj z linku w sekcji Dodatkowe informacje, aby dowiedzieć się więcej na temat platformy FCM i zmiany wprowadzanej przez firmę Google.

#### <a name="additional-information"></a>Dodatkowe informacje
https://firebase.google.com/docs/cloud-messaging/


### <a name="new-fullscreen-experience-coming-to-intune---4593669--"></a>Nowe funkcje obsługi pełnego ekranu w usłudze Intune <!--4593669-->
Usługa Intune w witrynie Azure Portal zyska zaktualizowany interfejs użytkownika funkcji tworzenia i edytowania danych. Nowy interfejs uprości istniejące przepływy pracy dzięki zastosowaniu formatu kreatorów w obrębie jednego bloku. Zmiana ta pozwoli pozbyć się natłoku widocznych jednocześnie bloków, a także wyeliminować konieczność przechodzenia do szczegółów bloków podczas zadań związanych z tworzeniem i edytowaniem informacji. Przepływy pracy dotyczące tworzenia zostaną ponadto zaktualizowane o funkcję przypisań (z wyjątkiem przypisywania aplikacji).

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Obsługa pełnego ekranu w usłudze Intune zostanie wprowadzona zarówno w witrynie portal.azure.com, jak i devicemanagement.microsoft.com w ciągu najbliższych kilku miesięcy. Aktualizacja interfejsu użytkownika nie będzie miała wpływu na działanie istniejących zasad i profilów, ale przepływ pracy ulegnie drobnym zmianom. Na przykład podczas tworzenia nowych zasad będzie można już na tym etapie ustawić niektóre przypisania, zamiast robić to później, już po utworzeniu zasad. Dodatkowe informacje o tym, jak te nowe funkcje będą wyglądać w konsoli (wraz ze zrzutami ekranu), znaleźć można we wpisie na blogu.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Co zrobić, aby przygotować się do tej zmiany?
Nie trzeba podejmować żadnych działań, ale w razie potrzeby można rozważyć zaktualizowanie wskazówek dla specjalistów IT. Naszą dokumentację będziemy aktualizować w miarę wdrażania nowych funkcji w kolejnych blokach usługi Intune w witrynie Azure Portal.

#### <a name="additional-information"></a>Dodatkowe informacje 
https://aka.ms/intune_fullscreen

### <a name="plan-for-change-intune-moving-to-support-ios-11-and-higher-in-september----4665342--"></a>Planowanie zmian: W usłudze Intune nastąpi przejście do obsługi systemu iOS 11 i nowszych wersji we wrześniu <!-- 4665342-->
Oczekujemy, że we wrześniu firma Apple wyda system iOS 13. Rejestracja w usłudze Intune, aplikacja Portal firmy oraz program Managed Browser zostaną przeniesione do obsługi systemu iOS 11 i jego nowszych wersji wkrótce po wydaniu systemu iOS 13.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Pod warunkiem, że aplikacje mobilne usługi Office 365 będą obsługiwane w systemie iOS 11.0 lub nowszym, może nie mieć to wpływu na Ciebie; Twój system operacyjny lub urządzenia zostały już prawdopodobnie uaktualnione. Jednak jeśli masz dowolne z wymienionych poniżej urządzeń lub chcesz zarejestrować dowolne z tych urządzeń, pamiętaj, że poniższe urządzenia nie obsługują systemów operacyjnych nowszych niż iOS 10. Następujące urządzenia trzeba będzie uaktualnić tak, aby obsługiwały system iOS 11 lub nowszy:

- iPhone 5
- iPhone 5c
- iPad (4. generacja)

Od lipca urządzenia zarejestrowane w usłudze MDM z systemem iOS 10 i aplikacją Portal firmy będą otrzymywać monit o uaktualnienie systemu operacyjnego lub urządzenia. Jeśli używasz zasad ochrony aplikacji (APP, Application Protection Policies), możesz również zdefiniować ustawienie dostępu „Wymagaj minimalnej wersji systemu operacyjnego iOS (tylko ostrzeżenie)”.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Co należy zrobić, aby przygotować się do tej zmiany?
Sprawdź raporty usługi Intune, aby zobaczyć, na które urządzenia lub użytkowników może to mieć wpływ. Przejdź do pozycji **Urządzenia** > **Wszystkie urządzenia** i filtruj zawartość według systemu operacyjnego. Możesz dodać dodatkowe kolumny, które ułatwiają określenie, kto w organizacji ma urządzenia z systemem iOS 10. Poproś użytkowników końcowych, aby do września uaktualnili urządzenia do obsługiwanej wersji systemu operacyjnego.

### <a name="plan-for-change-support-for-version-811-and-higher-of-intune-app-sdk-for-ios----3586942--"></a>Planowanie zmian: Obsługa wersji 8.1.1 i nowszych zestawu SDK aplikacji usługi Intune dla systemu iOS <!-- 3586942-->
Od września 2019 r. usługa Intune zostanie przeniesiona do obsługi aplikacji dla systemu iOS przy użyciu zestawu Intune App SDK w wersji 8.1.1 i nowszych. Aplikacje skompilowane za pomocą zestawu SDK w wersjach starszych niż 8.1.1 nie będą już obsługiwane. Ta zmiana będzie obowiązywać od wydania przez firmę Apple systemu iOS 13, co jest oczekiwane w okolicy września i zostało ogłoszone w artykule MC181399.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Dzięki integracji zestawu SDK aplikacji usługi Intune lub narzędzia opakowującego aplikacje można chronić dane firmowe z niezatwierdzonych aplikacji i od niezatwierdzonych użytkowników za pomocą szyfrowania danych. Zestaw SDK aplikacji usługi Intune dla systemu iOS będzie domyślnie używać 256-bitowych kluczy szyfrowania po włączeniu szyfrowania przy użyciu zasad rozwiązania Intune App Protection (APP) w usłudze Intune. Po tej zmianie wszystkie aplikacje systemu iOS w wersjach zestawu SDK wcześniejszych niż 8.1.1, które używają 128-bitowych kluczy szyfrowania, nie będą już mogły udostępniać danych aplikacjom zintegrowanym za pomocą zestawu SDK 8.1.1 lub kluczy 256-bitowych. Wszystkie aplikacje dla systemu iOS będą musiały mieć zestaw SDK w wersji 8.1.1 lub nowszej, aby umożliwić udostępnianie chronionych danych.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Co zrobić, aby przygotować się do tej zmiany?
Sprawdź aplikacje firmy Microsoft, innych firm i biznesowe (LOB). Upewnij się, że wszystkie Twoje aplikacje chronione za pomocą zasad ochrony aplikacji usługi Intune korzystają z zestawu SDK w wersji 8.1.1 lub nowszej.

- Aplikacje LOB: Może być konieczne ponowne opublikowanie aplikacji zintegrowanych z zestawem SDK w wersji 8.1.1 lub nowszej. Zalecamy użycie najnowszej wersji zestawu SDK. Aby uzyskać informacje na temat przygotowywania aplikacji biznesowych do użycia zasad ochrony aplikacji, zobacz [Przygotowanie aplikacji biznesowych pod kątem zasad ochrony aplikacji](../apps-prepare-mobile-application-management.md).
- Aplikacje firmy Microsoft/innych firm: Upewnij się, że wdrażasz najnowszą wersję tych aplikacji dla użytkowników.

Należy również zaktualizować dokumentację lub wskazówki dla deweloperów (jeśli ma to zastosowanie), aby uwzględnić tę zmianę w ramach obsługi dla zestawu SDK.

#### <a name="additional-information"></a>Dodatkowe informacje
https://docs.microsoft.com/intune/apps-prepare-mobile-application-management

### <a name="plan-for-change-new-windows-updates-settings-in-intune----4464404---"></a>Planowanie zmian: Nowe ustawienia aktualizacji systemu Windows w usłudze Intune <!-- 4464404 -->
Od sierpniowego wydania usługi Intune lub wersji 1908 dodamy nowy obszar „Ustawienia terminu ostatecznego”, który można będzie skonfigurować zamiast ustawień obszaru „Zezwalaj użytkownikowi na ponowne uruchamianie (ponowne uruchamianie wymagające interwencji użytkownika)”. Ustawienia ponownego uruchomienia wymagającego interwencji użytkownika w interfejsie użytkownika planujemy wyłączyć w wersji 1909 lub aktualizacji z września. Do końca października ustawienia te zostaną całkowicie usunięte z konsoli. 

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?
Jeśli zarządzasz urządzeniami z systemem Windows 10 w swoim środowisku: 
- W aktualizacji usługi Intune z sierpnia lub wersji 1908 zobaczysz w konsoli nowe ustawienia terminu ostatecznego jako dodatek do starych ustawień ponownego uruchomienia wymagającego interwencji użytkownika.
- W przypadku skonfigurowania starych i nowych ustawień wartości ustawień terminu ostatecznego będą zastępować wartości ustawień ponownego uruchomienia wymagającego interwencji użytkownika.
- Ustawienia terminu ostatecznego zastąpią opcję „Zezwalaj użytkownikowi na ponowne uruchamianie (ponowne uruchamianie wymagające interwencji użytkownika)” w konsoli w aktualizacji 1910.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Co zrobić, aby przygotować się do tej zmiany?
Zacznij korzystać z ustawień terminu ostatecznego w wersji 1908, konfigurując ich żądane wartości. Po wykonaniu tej czynności będzie można ustawić wartość ustawienia ponownego uruchomienia wymagającego interwencji użytkownika na „Nieskonfigurowane”, aby przygotować się do jego usunięcia z konsoli w październiku.

W razie potrzeby zaktualizuj dokumentację i skrypty automatyzacji. 

Będziemy Cię informować na bieżąco, a przed usunięciem ustawień ponownego uruchomienia wymagającego interwencji użytkownika opublikujemy przypomnienie w Centrum wiadomości.
