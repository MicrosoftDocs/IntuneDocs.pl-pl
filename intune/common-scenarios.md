---
title: Typowe sposoby korzystania z usługi Microsoft Intune
description: Poznaj sześć najbardziej typowych zadań, którymi zarządzanie może ułatwić usługa Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1f37d4ff-b5a7-4a89-8884-a6184908b09c
ms.reviewer: dougeby
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e9cf1b9c7d950707c268fd509c184be7709f53e3
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="common-ways-to-use-microsoft-intune"></a>Typowe sposoby korzystania z usługi Microsoft Intune

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Przed zagłębieniem się w zadania implementacji ważne jest, aby zorganizować uczestników projektu rozwiązania typu Enterprise Mobility firmy wokół celów biznesowych firmy.  Jest to istotne zarówno w przypadku wdrażania od zera rozwiązania typu Enterprise Mobility, jak i migracji z innego produktu.  

Potrzeby dotyczące rozwiązań typu Enterprise Mobility dynamicznie ewoluują i podejście firmy Microsoft do zaspakajania tych potrzeb może czasami różnić się od innych rozwiązań na rynku. Najlepszym sposobem, aby zorganizować projekt wokół celów biznesowych jest określenie swoich celów w postaci scenariuszy, które mają być obsługiwane dla pracowników, partnerów i działu IT.  

Poniżej przedstawiono krótkie wprowadzenia do sześciu najbardziej typowych scenariuszy korzystających z usługi Intune, wraz z linkami do dodatkowych informacji na temat sposobu planowania i wdrażania każdego z nich.

>[!NOTE]
>Czy chcesz wiedzieć, jak dział IT firmy Microsoft używa usługi Intune, aby umożliwić pracownikom firmy Microsoft dostęp do zasobów firmowych na ich urządzeniach przenośnych z zachowaniem ochrony danych firmowych? [Przeczytaj tę techniczną analizę przypadku](https://www.microsoft.com/itshowcase/Article/Content/588), aby zobaczyć szczegółowo, w jaki sposób dział IT firmy Microsoft używa usługi Intune i innych usług do zarządzania tożsamościami, urządzeniami, aplikacjami i danymi.  

>[!IMPORTANT]
>Chcemy się upewnić, że urządzenia przenośne są aktualne w kontekście ostatnich ataków złośliwego oprogramowania „Trident” na urządzenia z systemem iOS. Dlatego opublikowaliśmy wpis na blogu — [Ensuring mobile devices are up-to-date using Microsoft Intune](https://blogs.technet.microsoft.com/enterprisemobility/2016/08/26/ensuring-mobile-devices-are-up-to-date-using-microsoft-intune/) (Zapewnianie aktualności urządzeń przenośnych za pomocą usługi Microsoft Intune). Zawiera on informacje dotyczące różnych sposobów zabezpieczania i zapewniania aktualności urządzeń przez usługę Intune.

## <a name="protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices"></a>Zabezpieczanie lokalnej poczty e-mail i danych na potrzeby bezpiecznego uzyskiwania dostępu przez urządzenia przenośne
Większość strategii rozwiązań typu Enterprise Mobility zaczyna się od planu umożliwienia pracownikom z urządzeniami przenośnymi bezpiecznego dostępu do poczty e-mail przez Internet. W wielu organizacjach lokalne dane i serwery aplikacji, takie jak Microsoft Exchange, są nadal hostowane w sieci firmowej.


Usługa Intune oraz pakiet Microsoft Enterprise Mobility + Security (EMS) oferują unikatowo zintegrowane [rozwiązanie dostępu warunkowego](conditional-access.md) ([portal klasyczny](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)) dla programu Exchange Server, dzięki któremu żadna aplikacja mobilna nie może uzyskać dostępu do poczty e-mail, dopóki urządzenie nie zostanie zarejestrowane w usłudze Intune. Wszystko to można zrobić bez wdrażania kolejnej maszyny bramy na granicy sieci firmowej.

Ponadto usługa Intune obsługuje umożliwianie dostępu do aplikacji mobilnych, które wymagają bezpiecznego dostępu do danych lokalnych, takich jak serwery aplikacji biznesowych. Zazwyczaj jest to wykonywane przy użyciu [zarządzanych przez usługę Intune certyfikatów](certificates-configure.md) kontroli dostępu ([portal klasyczny](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles)) w połączeniu ze standardową bramą sieci VPN lub serwerem proxy w sieci obwodowej, takim jak serwer proxy aplikacji usługi Microsoft Azure Active Directory. 

W takich przypadkach jedynym sposobem, aby uzyskać dostęp do danych firmowych, jest zarejestrowanie urządzenia w systemie zarządzania. Po zarejestrowaniu urządzeń system zarządzania zapewnia, że urządzenia są zgodne z zasadami, zanim będą mogły uzyskać dostęp do danych firmowych. Ponadto można użyć [narzędzia opakowującego aplikacje i zestawu SDK aplikacji](apps-prepare-mobile-application-management.md) usługi Intune, aby pomóc w zamknięciu udostępnianych danych wewnątrz aplikacji biznesowej w celu niedopuszczenia do przekazania danych firmowych do aplikacji lub usług konsumenckich.

<!-- Learn more about how to plan and deploy Intune to help secure on-premises email and data. -->


## <a name="protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices"></a>Zabezpieczanie poczty e-mail i danych usługi Office 365 na potrzeby bezpiecznego uzyskiwania dostępu przez urządzenia przenośne
Ochrona danych firmowych w usłudze Office 365 (wiadomości e-mail, dokumentów, wiadomości błyskawicznych, kontaktów) jest łatwa dla Ciebie i bezproblemowa dla Twoich użytkowników.


Usługa Intune i pakiet Microsoft Enterprise Mobility + Security oferują unikalne rozwiązanie zintegrowanego dostępu warunkowego, które zapewnia, że żadni użytkownicy, aplikacje ani urządzenia nie będą mogły uzyskać dostępu do danych usługi Office 365, chyba że spełniają wymagania zgodności w firmie (wykonano [uwierzytelnianie wieloskładnikowe](/intune-classic/deploy-use/multi-factor-authentication-azure-active-directory), zarejestrowano w usłudze Intune, używane są aplikacje zarządzane, obsługiwana wersja systemu operacyjnego, numer PIN urządzenia, profil użytkownika niskiego ryzyka itp.).


Aplikacje mobilne pakietu Office w odpowiednich sklepach z aplikacjami są gotowe do korzystania z zasad zawierania danych, które można skonfigurować za pośrednictwem usługi Intune. Pozwala to zapobiegać udostępnianiu danych aplikacjom (np. natywnym aplikacjom poczty e-mail) i lokalizacjom magazynu (np. programowi Dropbox), które nie są zarządzane przez dział IT. Ta funkcja jest wbudowana w usługę Office 365 i pakiet EMS. Nie musisz wdrażać dodatkowej infrastruktury, aby zyskać tę wartość.

Powszechną praktyką wdrażania usługi Office 365 jest wymaganie zarejestrowania urządzeń w systemie zarządzania, jeśli wymagają one pełnego skonfigurowania przy użyciu konfiguracji firmowych aplikacji, certyfikatów, sieci Wi-Fi i VPN, co jest typowym scenariuszem w przypadku urządzeń firmowych.  


Jeśli jednak użytkownik potrzebuje jedynie uzyskiwać dostęp do firmowej poczty e-mail i dokumentów, co ma często miejsce w przypadku urządzeń prywatnych, można zażądać od użytkownika korzystania z aplikacji mobilnych pakietu Office (do których zostały zastosowane [zasady ochrony aplikacji](app-protection-policies.md) ([portal klasyczny](/intune-classic/deploy-use/protect-apps-and-data-with-microsoft-intune)) i całkowicie pominąć rejestrację urządzenia.  



W obu przypadkach dane usługi Office 365 będą chronione przez zasady, które zostały zdefiniowane.

<!-- Learn more about how to plan and deploy Intune to help secure Office 365 email and data. -->


## <a name="offer-a-bring-your-own-device-program-to-all-employees"></a>Oferowanie programu „Przynieś własne urządzenie” (bring your own device) wszystkim pracownikom
Popularność strategii BYOD (bring your own device) wśród organizacji stale rośnie, ponieważ oznacza ona zmniejszenie wydatków na sprzęt i zwiększa możliwości pracy mobilnej dla pracowników. W dzisiejszych czasach niemal każdy pracownik ma telefon osobisty, a więc po co wkładać mu drugi do kieszeni? Głównym wyzwaniem było zawsze przekonanie pracowników do rejestrowania urządzeń osobistych w systemie zarządzania, ponieważ obawiają się oni o to, co dział IT będzie mógł zobaczyć i zrobić z ich urządzeniem.  

Jeśli rejestracja urządzenia nie jest wygodną opcją, usługa Intune oferuje alternatywne podejście BYOD, umożliwiające po prostu [zarządzanie aplikacjami, które zawierają dane firmowe](app-protection-policies.md) ([portal klasyczny](/intune-classic/deploy-use/protect-apps-and-data-with-microsoft-intune)). Usługa Intune chroni dane firmowe, nawet jeśli dana aplikacja uzyskuje dostęp zarówno do danych firmowych, jak i osobistych, ponieważ tak się dzieje w przypadku aplikacji mobilnych dla pakietu Office.  

Jako administrator możesz wymagać od użytkowników uzyskiwania dostępu do usługi Office 365 z aplikacji mobilnych dla pakietu Office oraz skonfigurowania aplikacji z zasadami zapewniającymi ochronę danych (np. szyfrowanie, ochrona przy użyciu numeru PIN itp.). Te zasady ochrony aplikacji zapobiegają utracie danych w aplikacjach niezarządzanych i lokalizacjach magazynowania — wewnątrz tych aplikacji lub poza nimi. Na przykład zasady uniemożliwiają użytkownikowi kopiowanie tekstu z profilu firmowej poczty e-mail do profilu poczty e-mail klienta indywidualnego, nawet jeśli oba profile są skonfigurowane w programie Outlook Mobile. Podobne konfiguracje można wdrożyć dla innych usług i aplikacji wymaganych przez użytkowników infrastruktury BYOD („Przynieś własne urządzenie”).

<!-- Learn more about how to plan and deploy Intune to support BYOD.-->

## <a name="issue-corporate-owned-phones-to-your-employees"></a>Wydawanie firmowych telefonów pracownikom
Obecnie wielu pracowników korzysta z technologii mobilnych, przez co wydajność pracy na urządzeniach przenośnych staje się niezbędna dla utrzymania konkurencyjności. Pracownicy ci potrzebują bezproblemowego dostępu do wszystkich aplikacji i danych firmowych, w dowolnym miejscu i czasie. Należy się upewnić, że dane firmowe są bezpieczne, a koszty administracyjne niskie.  

Usługa Intune oferuje [rozwiązania do zbiorczej obsługi administracyjnej i zarządzania](device-enrollment.md) ([portal klasyczny](/intune-classic/deploy-use/manage-corporate-owned-devices)) zintegrowane z głównymi platformami zarządzania urządzeniami firmowymi na rynku, w tym programem Device Enrollment Program firmy Apple i platformą zabezpieczeń urządzeń mobilnych Samsung Knox. Scentralizowane tworzenie konfiguracji urządzeń za pomocą usługi Intune sprawia, że inicjowanie obsługi firmowych urządzeń może być wysoce zautomatyzowane.  

Wyobraź sobie: wręczasz pracownikowi nieotwarte pudełko z telefonem iPhone. Pracownik go włącza i zostaje przeprowadzony przez firmowy przepływ konfiguracji, podczas którego musi się uwierzytelnić. Telefon iPhone jest bezproblemowo konfigurowany z użyciem [zasad zabezpieczeń](device-profiles.md) ([portal klasyczny](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)).

Następnie pracownik uruchamia aplikację Portal firmy w usłudze Intune, aby uzyskać dostęp do opcjonalnych aplikacji firmowych, które są dla niego dostępne.

<!-- Learn more about how to plan and deploy Intune to support corporate owned devices. -->

## <a name="issue-limited-use-shared-tablets-to-your-employees"></a>Wydawanie pracownikom tabletów udostępnionych do ograniczonego użytku
Pracownicy w coraz większym stopniu korzystają z technologii mobilnych. Na przykład wspólne tablety są teraz powszechnie używane przez pracowników sklepów sieci detalicznych.  Czy to używane do obsługi transakcji sprzedaży, czy do natychmiastowego sprawdzenia zapasów, tablety pomagają stworzyć doskonałe interakcje z klientami.

W tym przypadku krytyczne znaczenie ma uproszczenie środowiska użytkownika. Z tego powodu tablety są zazwyczaj przekazywane pracownikom w trybie ograniczonym, w którym pracownik może korzystać wyłącznie z jednej aplikacji biznesowej. Usługa Intune umożliwia zbiorczą obsługę administracyjną, zabezpieczanie i centralne zarządzanie tymi wspólnymi urządzeniami z systemem [iOS oraz Android](device-profiles.md) ([portal klasyczny](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)), które można skonfigurować do pracy w trybie ograniczonym.

<!-- Learn more about how to plan and deploy Intune to support shared tablets. -->

## <a name="enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk"></a>Umożliwianie pracownikom bezpiecznego dostępu do usługi Office 365 z niezarządzanego kiosku publicznego
Czasami pracownicy muszą używać urządzeń, aplikacji lub przeglądarek, którymi nie można zarządzać, takich jak komputery publiczne na targach czy w hotelach.

Czy zezwalać pracownikom na dostęp do firmowej poczty e-mail z takich urządzeń, aplikacji lub przeglądarek? Dzięki usłudze Intune i pakietowi Microsoft Enterprise Mobility + Security można po prostu odpowiedzieć „nie”, [ograniczając dostęp do poczty e-mail tylko do urządzeń zarządzanych przez organizację](conditional-access.md) ([portal klasyczny](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)). Daje to pewność, że silnie uwierzytelniony pracownik nie pozostawi przypadkowo danych firmowych na niezaufanym komputerze.
