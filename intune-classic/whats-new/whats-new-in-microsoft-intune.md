---
title: Co nowego | Microsoft Docs
description: "Sprawdź, co nowego w tym miesiącu i poprzednich wersjach usługi Microsoft Intune"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 2e6452a066aa7eaeb295a3b531d83dc3b632bcf5
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---
# <a name="whats-new-in-microsoft-intune---april-2017"></a>Co nowego w usłudze Microsoft Intune — kwiecień 2017
Poznaj nowości w tej wersji usługi Microsoft Intune. Dowiedz się o nadchodzących zmianach, na które należy się przygotować, jak również uzyskaj informacje o poprzednich wersjach.

> [!Note]
> Wszystkie te funkcje będą również w przyszłości obsługiwane dla hybrydowych wdrożeń klientów (program Configuration Manager z usługą Intune). Aby uzyskać więcej informacji na temat nowych funkcji hybrydowych, odwiedź stronę [Co nowego w funkcjach hybrydowych](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nowe możliwości

### <a name="myapps-available-for-managed-browser---822308-822303--"></a>Usługa MyApps dostępna dla przeglądarki Managed Browser <!--822308, 822303-->

Usługa Microsoft MyApps ma teraz lepsze wsparcie w ramach przeglądarki Managed Browser. Użytkownicy przeglądarki Managed Browser, którzy nie są przeznaczeni do zarządzania, zostaną przeniesieni bezpośrednio do usługi MyApps, w której będą mogli uzyskać dostęp do aprowizowanych przez administratora aplikacji SaaS. Użytkownicy, którzy są przeznaczeni do zarządzania w usłudze Intune, nadal będą mogli uzyskiwać dostęp do usługi MyApps z wbudowanej zakładki przeglądarki Managed Browser.

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431-971473--"></a>Nowe ikony przeglądarki Managed Browser i aplikacji Portal firmy <!--918433, 918431, 971473-->

Przeglądarka Managed Browser otrzymuje zaktualizowane ikony aplikacji dla systemów Android i iOS. Nowa ikona będzie zawierać zaktualizowany identyfikator Intune, dzięki czemu będzie bardziej spójna z innymi aplikacjami w rozwiązaniu Enterprise Mobility + Security (EM+S). Nowa ikona programu Managed Browser jest widoczna na [stronie dotyczącej nowości w interfejsie użytkownika aplikacji usługi Intune](whats-new-in-intune-app-ui.md).

Portal firmy również otrzymuje zaktualizowane ikony aplikacji dla systemów Android, iOS i Windows, aby poprawić spójność z innymi aplikacjami w rozwiązaniu EM+S. Ikony te będą stopniowo wydawane na różnych platformach od kwietnia do końca maja.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Wskaźnik postępu logowania w aplikacji Portal firmy dla systemu Android <!--953374-->

Aktualizacja aplikacji Portal firmy dla systemu Android pokazuje wskaźnik postępu logowania, gdy użytkownik uruchomi lub wznowi działanie aplikacji. Wskaźnik przechodzi przez nowe stany, od „Trwa łączenie...” przez „Trwa logowanie...” do „Trwa sprawdzanie wymagań dotyczących bezpieczeństwa...”, zanim zezwoli użytkownikowi na dostęp do aplikacji. Nowe ekrany aplikacji Portal firmy dla systemu Android są widoczne na [stronie dotyczącej nowości w interfejsie użytkownika aplikacji usługi Intune](whats-new-in-intune-app-ui.md).

### <a name="block-apps-from-accessing-sharepoint-online----679339---"></a>Blokowanie dostępu aplikacji do usługi SharePoint Online <!-- 679339 -->

Teraz możesz tworzyć zasady dostępu warunkowego na podstawie aplikacji, aby blokować dostęp do usługi [SharePoint Online](/intune-classic/deploy-use/mam-ca-for-sharepoint-online) aplikacjom, do których nie zastosowano zasad ochrony aplikacji. W tym scenariuszu dostępu warunkowego na podstawie aplikacji można określić aplikacje, które mają mieć dostęp do usługi SharePoint Online, za pomocą portalu Azure.

### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>Obsługa logowania jednokrotnego z aplikacji Portal firmy dla systemu iOS do programu Outlook dla systemu iOS <!--834012-->
Użytkownicy nie muszą już logować się w aplikacji Outlook, jeśli zalogowali się na tym samym urządzeniu do aplikacji Portal firmy dla systemu iOS przy użyciu tego samego konta. Gdy użytkownicy uruchamiają aplikację Outlook, mogą wybrać swoje konto i zalogować się automatycznie. Ponadto pracujemy nad dodaniem tej funkcji do innych aplikacji firmy Microsoft.

### <a name="improved-status-messaging-in-the-company-portal-app-for-ios---744866--"></a>Ulepszono komunikaty o stanie w aplikacji Portal firmy dla systemu iOS <!--744866-->
Nowe, bardziej szczegółowe komunikaty o błędach będą teraz wyświetlane w aplikacji Portal firmy dla systemu iOS, aby zapewnić bardziej dostępne informacje o tym, co dzieje się na urządzeniach. Poprzednio te przypadki błędów były uwzględniane w ogólnym komunikacie o błędzie o tytule „Portal firmy jest tymczasowo niedostępny”. Ponadto, jeśli użytkownik uruchamia aplikację Portal firmy w systemie iOS, gdy nie ma połączenia internetowego, zobaczy teraz stały pasek stanu na stronie głównej z komunikatem „Brak połączenia internetowego”.

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Ulepszono stan instalacji aplikacji Portal firmy dla systemu Windows 10 <!--676495-->

Nowe ulepszenia instalacji aplikacji uruchomionych w aplikacji Portal firmy systemu Windows 10 obejmują:
-    Szybsze raportowanie postępu instalacji pakietów MSI
-    Szybsze raportowanie postępu instalacji nowoczesnych aplikacji na urządzeniach z Rocznicową aktualizacją systemu Windows 10 lub nowszą wersją
-    Nowy pasek postępu dla instalacji nowoczesnych aplikacji na urządzeniach z Rocznicową aktualizacją systemu Windows 10 lub nowszą wersją

Nowy pasek postępu jest zaprezentowany na [stronie dotyczącej nowości w interfejsie użytkownika aplikacji usługi Intune](whats-new-in-intune-app-ui.md).

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Rejestracja zbiorcza urządzeń z systemem Windows 10 <!-- 747607 -->

Teraz możesz dołączyć dużą liczbę urządzeń z systemem Windows 10 z aktualizacją dla twórców do usług Azure Active Directory i Intune za pomocą projektanta konfiguracji systemu Windows /intune-classic/deploy-use/bulk-enroll-windows) dla swojej dzierżawy usługi Azure AD, utworzyć pakiet aprowizacji dołączający urządzenia do Twojej dzierżawy usługi Azure AD za pomocą projektanta konfiguracji systemu Windows i zastosować pakiet do urządzeń będących własnością firmy, które chcesz zbiorczo zarejestrować i którymi chcesz zarządzać. Po zastosowaniu pakietu urządzenia dołączają do usługi Azure AD, rejestrują się w usłudze Intune i umożliwiają logowanie użytkownikom usługi Azure AD.  Użytkownicy usługi Azure AD są standardowymi użytkownikami tych urządzeń i otrzymują przypisane zasady oraz wymagane aplikacje. Scenariusze samoobsługowe i scenariusze użycia witryny internetowej Portal firmy nie są w tej chwili obsługiwane.

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

W środowisku administracyjnym w witrynie Azure Portal będzie używana już zapowiadana nowa funkcja grupowania i określania celu. W przypadku migrowania istniejącej dzierżawy do nowego środowiska grupowania nastąpi również migracja do nowego środowiska administracyjnego w wersji zapoznawczej w dzierżawie. Jeśli przed zakończeniem migrowania dzierżawy chcesz przetestować lub poznać dowolną nową funkcję, utwórz nowe konto wersji próbnej usługi Intune lub zapoznaj się z [nową dokumentacją](/intune/whats-new).

> [!Note]
> W przypadku wersji zapoznawczej portalu Azure firma Microsoft jest w trakcie wdrażania aktualizacji przewidzianych w tym miesiącu. Jednak zmiany mogą nie być dostępne od razu ze względu na sposób wdrażania usługi Intune.  Zanim nowe funkcje staną się dostępne, niektóre składniki usługi muszą zostać zaktualizowane sekwencyjnie. Szukaj zmian w wersji zapoznawczej portalu Azure w miarę ich wdrażania w tym miesiącu. Aby uzyskać pełną listę zmian, zobacz artykuł [Co nowego w wersji zapoznawczej usługi Microsoft Intune](/intune/whats-new).

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Zastąpienie ról administracyjnych w witrynie Azure Portal

Istniejące role administracyjne zarządzania aplikacjami mobilnymi (MAM) (współautor, właściciel, tylko do odczytu) używane w portalu klasycznym Intune (Silverlight) są zastępowane pełnym zestawem nowych kontroli administracyjnych opartych na rolach (RBAC) w witrynie Intune Azure Portal. Po migracji do witryny Azure Portal należy ponownie przypisać administratorów do nowych ról administracyjnych. Aby uzyskać więcej informacji na temat kontroli dostępu opartej na rolach (RBAC) i nowych ról, zobacz [Kontrola dostępu oparta na rolach w usłudze Microsoft Intune](/intune/role-based-access-control).

## <a name="whats-coming"></a>Wkrótce

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Ulepszone środowisko logowania w aplikacjach Portalu firmy dla wszystkich platform <!--User Story 1132123-->

Informujemy o zmianie, która zostanie wprowadzona w ciągu następnych kilku miesięcy i ułatwi logowanie w aplikacjach Portal firmy w usłudze Intune dla systemów Android, iOS i Windows. Nowe środowisko użytkownika zostanie udostępnione automatycznie na wszystkich platformach aplikacji Portal firmy, gdy zmiana ta zostanie wprowadzona w usłudze Azure AD. Ponadto użytkownicy mogą teraz logować się do Portalu firmy za pomocą innego urządzenia, korzystając z wygenerowanego kodu jednorazowego. Ta opcja jest szczególnie przydatna w sytuacji, gdy niezbędne jest zalogowanie się bez użycia poświadczeń.

Zrzuty ekranu przedstawiające poprzednie środowisko logowania, nowe środowisko logowania z poświadczeniami oraz nowe środowisko logowania za pomocą innego urządzenia można znaleźć na stronie [Co nowego w interfejsie aplikacji](whats-new-in-intune-app-ui.md).

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Planowane zmiany: zmiany w usłudze Intune dotyczące witryny Intune Partner Portal <!-- 1050016 -->

Wraz z aktualizacją usługi w połowie maja 2017 r. strona Intune Partner zostanie usunięta z witryny manage.microsoft.com.  

Administratorzy partnerów nie będą już mogli wyświetlać strony Intune Partner ani podejmować na niej działań w imieniu swoich klientów. Zamiast tego konieczne będzie zalogowanie się w jednym z dwóch innych portali firmy Microsoft dla partnerów.

Logowanie się na zarządzane konta klientów będzie możliwe zarówno w [Centrum partnerskim firmy Microsoft](https://partnercenter.microsoft.com/), jak i w [Centrum administracyjnym dla partnerów usługi Microsoft Office 365](https://portal.office.com/). Aby kontynuować czynności partnerskie, należy korzystać z dowolnej z tych witryn do zarządzania klientami.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Firma Apple będzie wymagać aktualizacji mechanizmu Application Transport Security <!--748318-->

Firma Apple ogłosiła, że będzie egzekwować pewne wymagania dotyczące mechanizmu Application Transport Security (ATS). Mechanizm ATS służy do wymuszania mocniejszych zabezpieczeń całej komunikacji aplikacji za pośrednictwem protokołu HTTPS. Ta zmiana wpływa na klientów usługi Intune korzystających z aplikacji Portalu firmy w systemie iOS.

Udostępniliśmy wersję aplikacji Portal firmy dla systemu iOS przy użyciu programu Apple TestFlight, który wymusza nowe wymagania ATS. Jeśli chcesz ją wypróbować, aby sprawdzić swoją zgodność z ATS, wyślij na adres e-mail <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> wiadomość ze swoim imieniem i nazwiskiem, adresem e-mail i nazwą firmy. Zapoznaj się z naszym [blogiem pomocy technicznej usługi Intune](https://aka.ms/compportalats), aby uzyskać więcej szczegółów.

### <a name="see-also"></a>Zobacz także
* [Blog usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Plan platformy w chmurze](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Co nowego w wersji zapoznawczej na platformie Azure](https://docs.microsoft.com/intune/whats-new)
* [Co nowego w interfejsie użytkownika aplikacji Portal firmy](/intune-classic/whats-new/whats-new-in-company-portal-ui)
* [Archiwum nowości](whats-new-archive.md)

