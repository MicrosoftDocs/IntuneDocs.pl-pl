---
title: Co nowego | Microsoft Docs
description: "Sprawdź, co nowego w tym miesiącu i poprzednich wersjach usługi Microsoft Intune"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 62dcb40ad5a7921c514a9d41da14b991e39f3bcd
ms.openlocfilehash: b3cf8d8f60482be2d4d903d1b2c00c1a3a392b73
ms.lasthandoff: 04/20/2017


---
# <a name="whats-new-in-microsoft-intune---april-2017"></a>Co nowego w usłudze Microsoft Intune — kwiecień 2017
Poznaj nowości w tej wersji usługi Microsoft Intune. Dowiedz się o nadchodzących zmianach, na które należy się przygotować, jak również uzyskaj informacje o poprzednich wersjach.

> [!Note]
> Wszystkie te funkcje będą również w przyszłości obsługiwane dla hybrydowych wdrożeń klientów (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nowe możliwości

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Ulepszone środowisko logowania w aplikacjach Portalu firmy dla wszystkich platform <!--User Story 1132123-->

Firma Microsoft ulepsza środowisko logowania aplikacji Portalu firmy w usłudze Intune dla systemu Android, iOS i Windows. Nowe środowisko użytkownika zostanie udostępnione automatycznie na wszystkich platformach aplikacji Portal firmy, gdy zmiana ta zostanie wprowadzona w usłudze Azure AD. Ponadto użytkownicy mogą teraz logować się do Portalu firmy za pomocą innego urządzenia, korzystając z wygenerowanego kodu jednorazowego. Ta opcja jest szczególnie przydatna w sytuacji, gdy niezbędne jest zalogowanie się bez użycia poświadczeń.

Zrzuty ekranu przedstawiające poprzednie środowisko logowania, nowe środowisko logowania z poświadczeniami oraz nowe środowisko logowania za pomocą innego urządzenia można znaleźć na stronie [Co nowego w interfejsie aplikacji](whats-new-in-intune-app-ui.md).

### <a name="myapps-available-for-managed-browser---822308-822303--"></a>Usługa MyApps dostępna dla przeglądarki Managed Browser <!--822308, 822303-->

Usługa Microsoft MyApps ma teraz lepsze wsparcie w ramach przeglądarki Managed Browser. Użytkownicy przeglądarki Managed Browser, którzy nie są przeznaczeni do zarządzania, zostaną przeniesieni bezpośrednio do usługi MyApps, w której będą mogli uzyskać dostęp do aprowizowanych przez administratora aplikacji SaaS. Użytkownicy, którzy są przeznaczeni do zarządzania w usłudze Intune, nadal będą mogli uzyskiwać dostęp do usługi MyApps z wbudowanej zakładki przeglądarki Managed Browser.

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431-971473--"></a>Nowe ikony przeglądarki Managed Browser i aplikacji Portal firmy <!--918433, 918431, 971473-->

Przeglądarka Managed Browser otrzymuje zaktualizowane ikony aplikacji dla systemów Android i iOS. Nowa ikona będzie zawierać zaktualizowany identyfikator Intune, dzięki czemu będzie bardziej spójna z innymi aplikacjami w rozwiązaniu Enterprise Mobility + Security (EM+S). Nowa ikona programu Managed Browser jest widoczna na [stronie dotyczącej nowości w interfejsie użytkownika aplikacji usługi Intune](whats-new-in-intune-app-ui.md).

Portal firmy również otrzymuje zaktualizowane ikony aplikacji dla systemów Android, iOS i Windows, aby poprawić spójność z innymi aplikacjami w rozwiązaniu EM+S. Ikony te będą stopniowo wydawane na różnych platformach od kwietnia do końca maja.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Wskaźnik postępu logowania w aplikacji Portal firmy dla systemu Android <!--953374-->

Aktualizacja aplikacji Portal firmy dla systemu Android pokazuje wskaźnik postępu logowania, gdy użytkownik uruchomi lub wznowi działanie aplikacji. Wskaźnik przechodzi przez nowe stany, od „Trwa łączenie...” przez „Trwa logowanie...” do „Trwa sprawdzanie wymagań dotyczących bezpieczeństwa...”, zanim zezwoli użytkownikowi na dostęp do aplikacji. Nowe ekrany aplikacji Portal firmy dla systemu Android są widoczne na [stronie dotyczącej nowości w interfejsie użytkownika aplikacji usługi Intune](whats-new-in-intune-app-ui.md).

### <a name="block-apps-from-accessing-sharepoint-online----679339---"></a>Blokowanie dostępu aplikacji do usługi SharePoint Online <!-- 679339 -->

Teraz możesz tworzyć zasady dostępu warunkowego na podstawie aplikacji, aby blokować dostęp do usługi [SharePoint Online](/InTune/deploy-use/mam-ca-for-sharepoint-online) aplikacjom, do których nie zastosowano zasad ochrony aplikacji. W tym scenariuszu dostępu warunkowego na podstawie aplikacji można określić aplikacje, które mają mieć dostęp do usługi SharePoint Online, za pomocą portalu Azure.

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Rejestracja zbiorcza urządzeń z systemem Windows 10 <!-- 747607 -->

Teraz możesz łączyć dużą liczbę urządzeń z aktualizacją systemu Windows 10 dla twórców z usługami Azure Active Directory oraz Intune, korzystając z aplikacji Windows Configuration Designer (WCD). Aby włączyć [zbiorcze rejestrowanie w usłudze MDM](/intune/deploy-use/bulk-enroll-windows) dla dzierżawy usługi Azure AD, utwórz pakiet aprowizacyjny, który dołącza urządzenia do dzierżawy usługi Azure AD, przy użyciu aplikacji Windows Configuration Designer, i zastosuj pakiet do firmowych urządzeń, które chcesz zarejestrować i którymi chcesz zarządzać w sposób zbiorczy. Po zastosowaniu pakietu urządzenia dołączają do usługi Azure AD, rejestrują się w usłudze Intune i umożliwiają logowanie użytkownikom usługi Azure AD.  Użytkownicy usługi Azure AD są standardowymi użytkownikami tych urządzeń i otrzymują przypisane zasady oraz wymagane aplikacje. Scenariusze samoobsługowe i scenariusze użycia witryny internetowej Portal firmy nie są w tej chwili obsługiwane.

## <a name="notices"></a>Uwagi

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Bezpośredni dostęp do scenariuszy rejestracji firmy Apple <!--951869-->

Na kontach usługi Intune utworzonych po styczniu 2017 roku włączono bezpośredni dostęp do scenariuszy rejestracji firmy Apple przy użyciu obciążenia Rejestruj urządzenia w portalu Azure w wersji zapoznawczej. Wcześniej podgląd rejestracji firmy Apple był dostępny tylko z poziomu linków w klasycznym portalu Intune. Konta usługi Intune utworzone przed styczniem 2017 będą wymagać przeprowadzenia jednorazowej migracji, zanim funkcje te będą dostępne w systemie Azure. Harmonogram migracji nie został jeszcze ogłoszony, ale szczegółowe informacje zostaną udostępnione najszybciej, jak będzie to możliwe. Zdecydowanie zalecamy utworzenie konta w wersji próbnej w celu przetestowania nowego środowiska pracy w przypadku, gdy istniejące konto nie ma dostępu do podglądu.

### <a name="whats-coming-for-appx-in-intune-on-azure----1000270---"></a>Elementy dostępne wkrótce dla pakietu AppX w usłudze Intune na platformie Azure <!-- 1000270 -->

W ramach migracji do usługi Intune na platformie Azure wprowadzamy następujące zmiany w pakiecie AppX:

1. Dodanie nowego typu aplikacji pakietu AppX w klasycznej konsoli usługi Intune, który można wdrożyć tylko do urządzeń zarejestrowanych w usłudze MDM.
2. Zmiana przeznaczenia istniejącego typu aplikacji pakietu AppX celem nakierowania wyłącznie na komputery zarządzanie za pośrednictwem komputerowego agenta usługi Intune.
3. Skonwertowanie wszystkich istniejących pakietów AppX do pakietów AppX usługi MDM w ramach migracji.

#### <a name="how-does-this-affect-me"></a>Jak to wpłynie na mnie?

Zmiany nie wpływają na żadne istniejące wdrożenia w urządzeniach zarządzanych za pośrednictwem komputerowego agenta usługi Intune. Niemniej po migracji nie będzie można wdrażać tych migrowanych pakietów AppX na żadnych nowych urządzeniach zarządzanych za pośrednictwem komputerowego agenta usługi Intune, które nie zostały wcześniej ustawione jako urządzenia docelowe.

#### <a name="what-action-do-i-need-to-take"></a>Jakie działania muszę podjąć?

Po migracji należy ponownie przekazać pakiet AppX jako komputerowy pakiet AppX, jeśli chcesz przeprowadzać nowe wdrożenia na komputerach. Aby dowiedzieć się więcej, zobacz [Appx changes in Intune on Azure](https://aka.ms/appxchange) (Zmiany w pakietach AppX w usłudze Intune na platformie Azure) na blogu zespołu pomocy technicznej usługi Intune.  


## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Nowości w publicznej wersji zapoznawczej środowiska administracyjnego usługi Intune na platformie Azure <!--736542-->

Na początku roku 2017 r. będziemy migrować nasze pełne środowisko administracyjne na platformę Azure, co umożliwi zaawansowane i zintegrowane zarządzanie podstawowymi przepływami pracy EMS na nowoczesnej platformie usług, którą można rozszerzyć za pomocą interfejsów API programu Graph.

Publiczna wersja zapoznawcza nowego środowiska administracyjnego będzie widoczna w nowych dzierżawach w wersji próbnej w witrynie Azure Portal w tym miesiącu. W wersji zapoznawczej możliwości istniejącej konsoli usługi Intune i spójność z nią będą udostępniane w sposób iteracyjny.

W środowisku administracyjnym w witrynie Azure Portal będzie używana już zapowiadana nowa funkcja grupowania i określania celu. W przypadku migrowania istniejącej dzierżawy do nowego środowiska grupowania nastąpi również migracja do nowego środowiska administracyjnego w wersji zapoznawczej w dzierżawie. Jeśli przed zakończeniem migrowania dzierżawy chcesz przetestować lub poznać dowolną nową funkcję, utwórz nowe konto wersji próbnej usługi Intune lub zapoznaj się z [nową dokumentacją](/intune-azure/introduction/whats-new).

> [!Note]
> W przypadku wersji zapoznawczej portalu Azure firma Microsoft jest w trakcie wdrażania aktualizacji przewidzianych w tym miesiącu. Jednak zmiany mogą nie być dostępne od razu ze względu na sposób wdrażania usługi Intune.  Zanim nowe funkcje staną się dostępne, niektóre składniki usługi muszą zostać zaktualizowane sekwencyjnie. Szukaj zmian w wersji zapoznawczej portalu Azure w miarę ich wdrażania w tym miesiącu. Aby uzyskać pełną listę zmian, zobacz artykuł [Co nowego w wersji zapoznawczej usługi Microsoft Intune](/intune-azure/introduction/whats-new).

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Zastąpienie ról administracyjnych w witrynie Azure Portal

Istniejące role administracyjne zarządzania aplikacjami mobilnymi (MAM) (współautor, właściciel, tylko do odczytu) używane w portalu klasycznym Intune (Silverlight) są zastępowane pełnym zestawem nowych kontroli administracyjnych opartych na rolach (RBAC) w witrynie Intune Azure Portal. Po migracji do witryny Azure Portal należy ponownie przypisać administratorów do nowych ról administracyjnych. Aby uzyskać więcej informacji na temat kontroli dostępu opartej na rolach (RBAC) i nowych ról, zobacz [Kontrola dostępu oparta na rolach w usłudze Microsoft Intune](/intune-azure/access-control/role-based-access-control).


## <a name="whats-coming"></a>Wkrótce

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Firma Apple będzie wymagać aktualizacji mechanizmu Application Transport Security <!--748318-->

Firma Apple ogłosiła, że począwszy od wiosny 2017 roku będzie egzekwować pewne wymagania dotyczące mechanizmu Application Transport Security (ATS). Mechanizm ATS służy do wymuszania mocniejszych zabezpieczeń całej komunikacji aplikacji za pośrednictwem protokołu HTTPS. Ta zmiana wpływa na klientów usługi Intune korzystających z aplikacji Portalu firmy w systemie iOS. Zapoznaj się z naszym [blogiem pomocy technicznej usługi Intune](https://aka.ms/compportalats), aby uzyskać więcej szczegółów.

### <a name="see-also"></a>Zobacz także
* [Blog usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plan platformy w chmurze](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Co nowego w wersji zapoznawczej na platformie Azure](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Co nowego w interfejsie użytkownika aplikacji Portal firmy](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Archiwum nowości](whats-new-archive.md)

