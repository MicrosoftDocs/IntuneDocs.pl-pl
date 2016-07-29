---
title: "Typowe sposoby korzystania z usługi Intune | Microsoft Intune"
description: "Wyświetla sześć najbardziej typowych zadań, które usługa Intune wykonuje za użytkowników"
keywords: 
author: jeffgilb
manager: arob98
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f37d4ff-b5a7-4a89-8884-a6184908b09c
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 376e6c1ae229187ab8ec73390f091f1d534365dd
ms.openlocfilehash: 3defa4b8f78e854532d32c66a17f0ed18d36cec7


---

# Typowe sposoby korzystania z usługi Intune

Przed zagłębieniem się w zadania implementacji ważne jest, aby zorganizować uczestników projektu rozwiązania typu Enterprise Mobility firmy wokół celów biznesowych firmy.  Jest to istotne zarówno w przypadku wdrażania od zera rozwiązania typu Enterprise Mobility, jak i migracji z innego produktu.  Potrzeby dotyczące rozwiązań typu Enterprise Mobility dynamicznie ewoluują i podejścia firmy Microsoft do zaspakajania tych potrzeb mogą czasami różnić się od innych rozwiązań na rynku.  Najlepszym sposobem, aby zorganizować projekt wokół celów biznesowych jest określenie, co chcesz osiągnąć, w postaci scenariuszy, które mają być obsługiwane dla pracowników, partnerów i informatyków.  Poniżej przedstawiono krótkie wprowadzenia do sześciu najbardziej typowych scenariuszy korzystających z usługi Intune, wraz z linkami do dodatkowych informacji na temat sposobu planowania i wdrażania każdego z nich.

>[!NOTE]
>Czy chcesz wiedzieć, jak dział IT firmy Microsoft używa usługi Intune, aby umożliwić pracownikom Microsoft dostęp do zasobów firmowych na ich urządzeniach przenośnych z zachowaniem ochrony danych firmowych? [Przeczytaj tę techniczną analizę przypadku](https://www.microsoft.com/itshowcase/Article/Content/588), aby zobaczyć szczegółowo, w jaki sposób dział IT firmy Microsoft używa usługi Intune i innych usług do zarządzania tożsamościami, urządzeniami, aplikacjami i danymi.  

## Zabezpieczanie lokalnej poczty e-mail i danych na potrzeby bezpiecznego uzyskiwania dostępu przez urządzenia przenośne
Większość strategii rozwiązań typu Enterprise Mobility zaczyna się od planu umożliwienia pracownikom z urządzeniami przenośnymi bezpiecznego dostępu do poczty e-mail przez Internet. W wielu organizacjach lokalne dane i serwery aplikacji, takie jak Microsoft Exchange, są nadal hostowane w sieci firmowej. Usługa Intune i pakiet Enterprise Mobility Suite (EMS) oferują unikatowe rozwiązanie zintegrowanego dostępu warunkowego dla serwera Exchange, które gwarantuje, że żadne aplikacje mobilne nie będą mogły uzyskać dostępu do poczty e-mail, dopóki urządzenie nie zostanie zarejestrowane w usłudze Intune, a wszystko bez wdrażania innego komputera bramy na granicy sieci firmowej.

Poza pocztą e-mail usługa Intune obsługuje umożliwianie dostępu do aplikacji mobilnych, które wymagają bezpiecznego dostępu do danych lokalnych, takich jak serwer aplikacji biznesowych.  Zazwyczaj jest to wykonywane przy użyciu zarządzanych przez usługę Intune certyfikatów kontroli dostępu w połączeniu ze standardową bramą sieci VPN lub serwerem proxy w sieci obwodowej, takim jak serwer proxy aplikacji usługi Azure AD.  W takich przypadkach jedynym sposobem na uzyskanie dostępu do danych firmowych jest rejestracja urządzenia w systemie zarządzania.  Po zarejestrowaniu system zarządzania zapewnia, że urządzenia uzyskujące dostęp do firmowych danych są zgodne z zasadami.  Ponadto można użyć narzędzia opakowującego aplikacje usługi Intune, aby pomóc w zamknięciu udostępnianych danych wewnątrz aplikacji biznesowej, aby nie mogła przekazywać danych firmowych do aplikacji lub usług konsumenckich.

<!-- Learn more about how to plan and deploy Intune to help secure on-premises email and data. -->

## Zabezpieczanie poczty e-mail i danych usługi Office 365 na potrzeby bezpiecznego uzyskiwania dostępu przez urządzenia przenośne
Ochrona danych firmowych w usłudze Office 365 (wiadomości e-mail, dokumentów, wiadomości błyskawicznych, kontaktów) jest łatwa dla Ciebie i bezproblemowa dla Twoich użytkowników. Usługa Intune i pakiet Enterprise Mobility Suite oferują unikalne rozwiązanie zintegrowanego dostępu warunkowego, które zapewnia, że żadni użytkownicy, aplikacje ani urządzenie nie będą mogły uzyskać dostępu do danych usługi Office 365, chyba że spełniają wymagania zgodności w firmie (wykonano uwierzytelnianie wieloskładnikowe, zarejestrowano w usłudze Intune, używane są aplikacje zarządzane, obsługiwana wersja systemu operacyjnego, numer PIN urządzenia, profil użytkownika niskiego ryzyka itp.). Aplikacje mobilne dla pakietu Office w odpowiednich sklepach z aplikacjami są gotowe do współpracy z zasadami zawierania danych, które można skonfigurować za pomocą usługi Intune. Pozwala to zapobiec udostępnianiu danych aplikacjom (np. natywnym aplikacjom poczty e-mail) i lokalizacjom przechowywania (np. Dropbox), które nie są zarządzane przez dział IT.  Ta funkcja jest wbudowana w usługę Office 365 i pakiet EMS.  Nie musisz wdrażać dodatkowej infrastruktury, aby zyskać tę wartość.

Powszechną praktyką wdrażania usługi Office 365 jest wymaganie zarejestrowania urządzeń w systemie zarządzania, jeśli wymagają one pełnego zainicjowania obsługi przy użyciu konfiguracji firmowych aplikacji/certyfikatów/sieci Wi-Fi/VPN, co ma często miejsce w przypadku firmowych urządzeń.  Jeśli jednak użytkownik po prostu musi uzyskiwać dostęp do firmowej poczty e-mail i dokumentów, jak to często bywa w przypadku urządzeń należących do użytkownika, wówczas musi on korzystać z aplikacji mobilnych dla pakietu Office (do których zastosowano zasady zawierania danych) i może pominąć rejestrowanie samego urządzenia.  W obu przypadkach dane usługi Office 365 będą chronione przez zasady, które zostały zdefiniowane.

<!-- Learn more about how to plan and deploy Intune to help secure Office 365 email and data. -->

## Oferowanie programu „Przynieś własne urządzenie" (BYOD, bring your own device) wszystkim pracownikom
Popularność strategii BYOD wśród organizacji stale rośnie, ponieważ oznacza ona zmniejszenie wydatków na sprzęt i zwiększa możliwości pracy mobilnej dla pracowników. W dzisiejszych czasach niemal każdy pracownik ma telefon osobisty, a więc po co wkładać mu drugi do kieszeni? Głównym wyzwaniem było zawsze przekonanie pracowników do rejestrowania urządzeń osobistych w systemie zarządzania, ponieważ obawiają się oni o to, co dział IT będzie mógł zobaczyć i zrobić z ich urządzeniem.  

Jeśli rejestracja urządzenia nie jest wygodną opcją, usługa Intune oferuje alternatywne podejście BYOD, umożliwiające po prostu zarządzanie aplikacjami, które zawierają dane firmowe.  Usługa Intune chroni dane firmowe, nawet jeśli dana aplikacja uzyskuje dostęp zarówno do danych firmowych, jak i osobistych, ponieważ tak się dzieje w przypadku aplikacji mobilnych dla pakietu Office.  Jako administrator możesz wymagać od użytkowników uzyskiwania dostępu do usługi Office 365 z aplikacji mobilnych dla pakietu Office oraz skonfigurowania aplikacji z zasadami zapewniającymi ochronę danych (szyfrowane, chronione numerem PIN itd.).  Te zasady zapobiegają utracie danych do niezarządzanych aplikacji i lokalizacji magazynu — wewnątrz lub na zewnątrz tych aplikacji.  Na przykład zasady uniemożliwią użytkownikowi kopiowanie tekstu z profilu firmowej poczty e-mail do profilu poczty e-mail klienta indywidualnego, nawet jeśli oba profile są skonfigurowane w programie Outlook Mobile.  Podobne konfiguracje można wdrożyć dla innych usług i aplikacji wymaganych przez użytkowników infrastruktury BYOD („Przynieś własne urządzenie”).

<!-- Learn more about how to plan and deploy Intune to support BYOD.-->

## Wydawanie firmowych telefonów pracownikom przetwarzającym informacje
Obecnie większość pracowników przetwarzających informacje korzysta z technologii mobilnych, przez co wydajność pracy na urządzeniach przenośnych staje się niezbędna dla utrzymania konkurencyjności.  Pracownicy ci potrzebują bezproblemowego dostępu do wszystkich aplikacji i danych firmowych, w dowolnym miejscu i czasie.  Należy się upewnić, że dane firmowe są bezpieczne, a koszty administracyjne niskie.  

Usługa Intune oferuje rozwiązania udostępniania i zarządzania zbiorczego zintegrowane z głównymi platformami zarządzania urządzeniami firmowymi na rynku, w tym programem Device Enrollment Program firmy Apple i platformą zabezpieczeń urządzeń przenośnych Samsung KNOX.  Scentralizowane tworzenie konfiguracji urządzeń za pomocą usługi Intune sprawia, że inicjowanie obsługi firmowych urządzeń może być wysoce zautomatyzowane.  

Wyobraź sobie: wręczasz pracownikowi nieotwarte pudełko z telefonem iPhone. Pracownik go włącza i zostaje przeprowadzony przez firmowy przepływ konfiguracji, podczas którego musi się uwierzytelnić. Telefon iPhone zostaje bezproblemowo skonfigurowany z zasadami zabezpieczeń (szyfrowanie dysków twardych, numer PIN urządzenia itd.), profilami poczty e-mail/sieci Wi-Fi/sieci VPN/certyfikatów i podstawowym zestawem aplikacji. Następnie pracownik uruchamia aplikację Portal firmy w usłudze Intune, aby uzyskać dostęp do opcjonalnych aplikacji firmowych, które są dla niego dostępne.

<!-- Learn more about how to plan and deploy Intune to support corporate owned devices. -->

## Wydawanie wspólnych tabletów do ograniczonego użytku pracownikom wykonującym zadania
Pracownicy wykonujący zadania w coraz większym stopniu korzystają z technologii mobilnych.  Na przykład wspólne tablety są teraz powszechnie wydawane pracownikom sklepów sieci detalicznych.  Czy to używane do obsługi transakcji sprzedaży, czy do natychmiastowego sprawdzenia zapasów, tablety pomagają stworzyć doskonałe interakcje z klientami.  W tym przypadku krytyczne znaczenie ma uproszczenie środowiska użytkownika.  Z tego powodu tablety są zazwyczaj przekazywane pracownikom w trybie ograniczonym, w którym pracownik może korzystać wyłącznie z jednej aplikacji biznesowej.  Usługa Intune umożliwia zbiorczą obsługę administracyjną, zabezpieczanie i centralne zarządzanie tymi wspólnymi tabletami, które można skonfigurować do pracy w trybie ograniczonym.

<!-- Learn more about how to plan and deploy Intune to support shared tablets. -->

## Umożliwianie pracownikom bezpiecznego dostępu do usługi Office 365 z niezarządzanego kiosku publicznego
Czasami pracownicy muszą używać urządzeń, aplikacji lub przeglądarek, którymi nie można zarządzać, takich jak komputery publiczne na targach czy w hotelach. Czy zezwalać pracownikom na dostęp do firmowej poczty e-mail z takich urządzeń, aplikacji lub przeglądarek? Dzięki usłudze Intune i pakietowi Enterprise Mobility Suite <!--you have choices. The--> Można po prostu odpowiedzieć „nie”, ograniczając dostęp do poczty e-mail tylko do urządzeń zarządzanych przez organizację.  <!-- Alternatively, you can choose to allow limited access to these untrusted computers by requiring multi-factor authentication and only allowing browser access (Outlook Web Access) in a mode where files cannot be downloaded (e.g. email attachments).-->  Daje to pewność, że silnie uwierzytelniony pracownik nie pozostawi przypadkowo danych firmowych na niezaufanym komputerze.

<!-- Learn more about how to plan and deploy Intune to support kiosks. -->



<!--HONumber=Jul16_HO3-->


