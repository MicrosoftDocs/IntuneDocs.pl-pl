---
title: Opis usługi Microsoft Intune
description: Microsoft Intune jest usługą opartą na chmurze, która ułatwia zarządzanie urządzeniami z systemami Windows, iOS, Mac OS X, Android i Windows Mobile.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 40fa5a2e-6c0f-4150-9740-d5ddc0cdbda0
ms.reviewer: cacamp
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6fef68e137010448fbb32bb6e621566f309581a3
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="microsoft-intune-service-description"></a>Opis usługi Microsoft Intune

Usługa Intune to oparta na chmurze usługa zarządzania mobilnością w przedsiębiorstwie (EMM, enterprise mobility management) ułatwiająca pracownikom utrzymanie produktywności przy jednoczesnej ochronie danych firmowych. Usługa Intune umożliwia:
* zarządzanie urządzeniami przenośnymi używanymi przez pracowników do uzyskiwania dostępu do danych firmowych,
* zarządzanie aplikacjami mobilnymi używanymi przez pracowników,
* chronienie danych firmowych poprzez kontrolowanie sposobu, w jaki pracownicy uzyskują do nich dostęp i udostępniają je,
* zapewnienie zgodności urządzeń i aplikacji z wymaganiami firmy dotyczącymi bezpieczeństwa.

Usługa Intune jest ściśle zintegrowana z usługą Azure Active Directory (Azure AD), co umożliwia kontrolowanie tożsamości i dostępu, a także z usługą Azure Information Protection na potrzeby ochrony danych. Można ją także zintegrować z programem System Center Configuration Manager, aby rozszerzyć możliwości zarządzania.

Aby dowiedzieć się więcej o zarządzaniu urządzeniami i aplikacjami oraz o ochronie danych firmowych za pomocą usługi Intune, zobacz [Dokumentacja usługi Intune](https://docs.microsoft.com/intune/).

## <a name="30-day-free-trial"></a>30-dniowa bezpłatna wersja próbna
Możesz rozpocząć korzystanie z usługi Intune w ramach 30-dniowej bezpłatnej wersji próbnej, która zawiera 100 licencji użytkowników. Aby rozpocząć korzystanie z bezpłatnej wersji próbnej, [odwiedź stronę rejestracji w usłudze Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20). Jeśli Twoja organizacja ma umowę Enterprise Agreement lub równoważną umowę licencjonowania zbiorowego, skontaktuj się z przedstawicielem firmy Microsoft, aby skonfigurować bezpłatną wersję próbną.

> [!NOTE]
> Jeśli Twoja organizacja ma konto służbowe usług Microsoft Online Services i zamierzasz kontynuować tę subskrypcję usługi Intune w środowisku produkcyjnym po zakończeniu okresu próbnego, wybierz opcję **Zaloguj** na tej stronie i uwierzytelnij się przy użyciu konta administratora globalnego Twojej organizacji. Ta akcja zagwarantuje, że wersja próbna usługi Intune zostanie połączona z istniejącym kontem służbowym.

<!--- For a list of settings that you can set up on mobile devices, see:

-   [Enrolled device management capabilities of Microsoft Intune](introduction-intune.md)

-   [Hybrid mobile device management (MDM) with System Center Configuration Manager and Microsoft Intune](/sccm/mdm/understand/hybrid-mobile-device-management)

For more about System Center Configuration Manager, see [Documentation  for System Center Configuration Manager](/sccm/index).--->
## <a name="intune-onboarding-benefit"></a>Asysta przy przejściu do usługi Intune
Firma Microsoft oferuje dla usługi Intune asystę przy dołączaniu w przypadku zakupu kwalifikujących się usług z odpowiednimi planami. Asysta umożliwia zdalną współpracę ze specjalistami firmy Microsoft w celu przygotowania środowiska usługi Intune. Aby uzyskać więcej informacji na temat asysty przy dołączaniu, zobacz [Opis asysty przy dołączaniu do usługi Microsoft Intune](http://go.microsoft.com/fwlink/?LinkId=619281).


## <a name="learn-how-intune-service-updates-affect-you"></a>Omówienie skutków aktualizacji usługi Intune

Ponieważ ekosystem zarządzania urządzeniami przenośnymi często się zmienia wraz z aktualizacjami systemu operacyjnego i nowymi wersjami aplikacji mobilnych, firma Microsoft regularnie aktualizuje usługę Intune. Istnieją trzy sposoby, aby dowiedzieć się o zmianach w usłudze Intune:

- [Co nowego w usłudze Microsoft Intune](whats-new.md). Ten temat jest aktualizowany wraz z comiesięczną lub cotygodniową aktualizacją usługi, na przykład po pojawieniu się nowej wersji aplikacji Portal firmy.

- Ponadto informacje o ważnych aktualizacjach usługi są ogłaszane w Centrum wiadomości [portalu zarządzania usługi Office 365](https://portal.office.com/Admin/Default.aspx). Jeśli zainstalujesz towarzyszącą [aplikację mobilną Office 365 Admin](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a), możesz otrzymywać powiadomienia na urządzeniu przenośnym. Dowiedz się więcej na temat sposobu pracy z [Centrum wiadomości usługi Office 365](https://support.office.com/client/results?Shownav=true&ns=O365ENTADMIN&version=15&ver=15&HelpID=O365E_MCManageUpdates).

    Kilka przydatnych wskazówek:

    - Komunikaty w Centrum wiadomości usługi Office 365 są kierowane do konkretnej grupy docelowej. To oznacza, że jeśli Twoja firma nie korzysta z oferty usługi Intune for EDU, to nie prześlemy jej komunikatów na temat usługi Intune for EDU.

    - Komunikaty wygasają. Na przykład powiadomienie o aktualizacji usługi z linkiem do strony „Co nowego” prawdopodobnie wygaśnie przed następnym powiadomieniem o aktualizacji usługi. W przeciwnym razie powstałaby długa lista starszych wpisów, które mogłyby nie być już istotne.

    - Aplikacja mobilna Office 365 Admin umożliwia przeszukiwanie wszystkich komunikatów i przekazywanie dalej powiadomienia, które chcesz udostępnić współpracownikom ze swojej organizacji.

    - W obszarze Edycja preferencji Centrum wiadomości zostanie dodany przełącznik dla usługi **Intune**, aby umożliwić wyświetlanie tych komunikatów w ramach subskrypcji usługi Intune. Jeśli widzisz opcję Zarządzanie urządzeniami mobilnymi w usłudze Office 365, jest to usługa inna niż Intune.

- Ponadto używamy dwóch blogów do przekazywania komunikatów na temat usług EMS i najlepszych rozwiązań pomocy technicznej usługi Intune:

    - [Blog dotyczący pakietu Enterprise Mobility + Security](https://blogs.technet.microsoft.com/enterprisemobility/)

    - [Blog dotyczący pomocy technicznej usługi Intune](https://blogs.technet.microsoft.com/intunesupport/)

>[!Note]
>Kondycję usługi Intune możesz monitorować w [portalu zarządzania usługi Office 365](https://portal.office.com/Admin/Default.aspx). Wybierz pozycję **Kondycja usługi** w lewym okienku. Można również użyć [aplikacji mobilnej Office 365 Admin](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a), aby wyświetlić informacje o kondycji usługi.

## <a name="types-of-notices-microsoft-provides-about-the-intune-service"></a>Oto typy powiadomień dotyczących usługi Intune udostępniane przez firmę Microsoft

Aby pomóc Ci zaplanować działania związane ze zmianami w usłudze, powiadomimy Cię co najmniej 7–90 dni przed uaktualnieniem usługi, w zależności od wpływu zmiany. Te aktualizacje mogą obejmować następujące typy zmian:

- Zmiany w środowisku użytkownika końcowego, które warto udostępnić pracownikom działu pomocy technicznej lub użytkownikom końcowym. Zwykle powiadamiamy o tych zmianach z wyprzedzeniem od 7 do 30 dni i zapisujemy je na stronie [Co nowego w interfejsie użytkownika aplikacji usługi Intune](whats-new-app-ui.md). Poprawki, takie jak błędy pisowni, zwykle nie są uwzględniane w dokumentacji. Jednak zmiana w środowisku użytkownika końcowego podczas rejestracji jest na tyle znacząca dla interfejsu użytkownika, że zarówno wysyłamy komunikat do klientów w Centrum wiadomości usługi Office 365, jak i dodajemy link do strony Co nowego w interfejsie użytkownika aplikacji usługi Intune, aby powiadomić o wprowadzanych zmianach i dać Ci czas na ocenę i aktualizację wskazówek dla użytkowników końcowych przed wdrożeniem zmian w środowisku produkcyjnym.

- Zmiany wymagające działań z Twojej strony są określane jako **Planowanie zmian** i zwykle powiadamiamy o nich z 30-dniowym wyprzedzeniem. W Centrum wiadomości usługi Office 365 istnieje nawet kategoria Planowanie zmian. Gdy znamy dokładną datę wdrożenia zmiany w środowisku produkcyjnym, umieszczamy datę **Wykonać do** z wizualizacją kolejki i wykrzyknikiem.

- W przypadku zakończenia obsługi zwykle powiadamiamy z 90-dniowym wyprzedzeniem. Na przykład, gdy przestajemy obsługiwać daną wersję programu IE, staramy się powiadomić o tym z 90-dniowym wyprzedzeniem. Proces ten komplikuje się jednak, gdy o zakończeniu obsługi informuje inna firma. Na przykład, gdy producent przeglądarki informuje, że jej najnowsza wersja nie będzie już obsługiwać programu Silverlight, powiadamiamy klientów o zakończeniu obsługi tej przeglądarki, aczkolwiek z wyprzedzeniem krótszym niż 90 dni.

- W przypadku wycofania usługi Intune użytkownicy zostaną powiadomieni z wyprzedzeniem 12 miesięcy.

Ponadto w rzadkich przypadkach, gdy musisz wykonać jakieś kroki po danym zdarzeniu, aby przywrócić normalne działanie usługi, lub gdy konieczne jest wprowadzenie znaczącej zmiany, którą w oparciu o informacje uzyskane od klientów uznajemy za zmianę mogącą zakłócać pracę, wysyłamy wiadomość e-mail do administratorów usługi. Jest to zależne od Twoich ustawień [preferencji komunikacji usługi Office 365](https://support.office.com/article/Change-your-contact-preferences-for-communications-from-Microsoft-6f70de1b-a64d-4498-bfbd-be8c83a9c0fc) oraz tego, czy został podany prawidłowy (najlepiej służbowy) adres e-mail.  


<!--- ## Choose the management solution that’s right for you
You can set up Intune in several ways to manage and help protect your company's mobile devices and computers (referred to as **devices** in this article).

- **Intune stand-alone configuration.** Use the web-based admin console in Intune to manage devices in your organization. Intune can be used without any on-premises IT infrastructure. If you use Intune with Active Directory Domain Services, you can use domain user accounts that you manage with Domain Services with Intune.

- **Intune with System Center Configuration Manager.** Use the Configuration Manager management console to manage computers and mobile devices in your enterprise. This configuration can help you to manage all your organization’s devices through a single console, the Configuration Manager Admin Console. Configuration Manager supports large numbers of mobile devices, servers, and computers. For more about Configuration Manager, see [Hybrid mobile device management (MDM) with System Center Configuration Manager and Microsoft Intune](/sccm/mdm/understand/hybrid-mobile-device-management). For more help deciding which approach is right for you, see [Choose between Microsoft Intune standalone and hybrid mobile device management with Configuration Manager](/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management).--->

## <a name="language-support"></a>Obsługa języków
Usługa Intune działa w witrynie Azure Portal, która obsługuje następujące języki: chiński (uproszczony), chiński (tradycyjny), czeski, holenderski, angielski, niemiecki, węgierski, włoski, japoński, portugalski (Brazylia), portugalski (Portugalia), rosyjski, hiszpański, francuski, koreański, polski, szwedzki i turecki.

Konsola administracyjna usługi Intune oraz mobilne środowiska użytkownika obsługują język duński, grecki, fiński, norweski i rumuński, a także wszystkie języki obsługiwane przez witrynę Azure Portal.

<!--- ## Learn more about Intune
Use these resources to learn more about Intune:

- The [Microsoft Intune Trust Center](https://www.microsoft.com/server-cloud/products/intune-trust-center/) provides information about the security, privacy, and compliance practices of Intune, and it describes some of Intune's certifications.

- [Enrolled device management capabilities of Microsoft Intune](introduction-intune.md)--->
