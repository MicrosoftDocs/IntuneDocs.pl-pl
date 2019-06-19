---
title: Zarządzanie urządzeniami w rozwiązaniu Microsoft 365
description: Rozwiązanie Microsoft 365 Enterprise obejmuje usługę Microsoft Intune. Zobacz, jakie możliwości zarządzania urządzeniami i aplikacjami mobilnymi oferuje Twojej organizacji usługa Intune. Zapoznaj się z typowymi scenariuszami i wdróż rozwiązanie Microsoft 365 w swoim środowisku za pomocą usługi Intune.
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/12/2019
ms.topic: conceptual
audience: ITPro
ms.service: microsoft-intune
ms.technology: ''
ms.custom: intune
ms.assetid: 0649d310-43a7-4b01-85d2-da255d03e1da
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: d5614f0657175658c1a8442d650e16c8550c1ac1
ms.sourcegitcommit: 4b83697de8add3b90675c576202ef2ecb49d80b2
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 06/13/2019
ms.locfileid: "67043844"
---
# <a name="what-is-device-management"></a>Co to jest zarządzanie urządzeniami? 

Kluczowym zadaniem każdego administratora jest chronienie i zabezpieczanie danych i zasobów organizacji. To zadanie to *zarządzanie urządzeniami*. Użytkownicy mają wiele urządzeń, za pomocą których otwierają i udostępniają pliki osobiste, odwiedzają witryny internetowe oraz instalują aplikacje i gry. Ci sami użytkownicy są jednocześnie pracownikami, studentami lub uczniami. Chcą więc mieć na używanych urządzeniach dostęp do zasobów służbowych oraz szkolnych, takich jak wiadomości e-mail i program OneNote. Zarządzanie urządzeniami umożliwia organizacjom chronienie i zabezpieczanie zasobów i danych. 

Dzięki korzystaniu z usług dostawcy zarządzania urządzeniami organizacje mogą mieć pewność, że dostęp do należących do nich informacji uzyskują tylko autoryzowane osoby i urządzenia. Natomiast użytkownicy urządzeń mogą bez obaw uzyskiwać dostęp do danych służbowych na swoich telefonach, ponieważ wiedzą, że ich urządzenia spełniają wymagania zabezpieczeń organizacji. Z punktu widzenia organizacji można się zastanawiać: **w jaki sposób powinniśmy chronić nasze zasoby?**

Odpowiedzią jest usługa [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune). Usługa Intune umożliwia zarządzanie urządzeniami przenośnymi (MDM, mobile device management) oraz zarządzanie aplikacjami mobilnymi (MAM, mobile app management). Oto niektóre kluczowe zadania wszelkich rozwiązań MDM i MAM:

- Obsługa zróżnicowanego środowiska mobilnego oraz bezpieczne zarządzanie urządzeniami z systemami iOS, Android, Windows i macOS.
- Zapewnienie zgodności urządzeń i aplikacji z wymaganiami bezpieczeństwa organizacji.
- Tworzenie zasad pomagających zapewnić bezpieczeństwo danych organizacji na urządzeniach osobistych i należących do firmy.
- Używanie jednego, ujednoliconego rozwiązania dla środowiska mobilnego do egzekwowania tych zasad i ułatwiania zarządzania urządzeniami, aplikacjami, użytkownikami i grupami

Usługa Intune jest zawarta w rozwiązaniu Microsoft 365 i jest zintegrowana z usługą Azure Active Directory (Azure AD). Usługa Azure AD ułatwia kontrolowanie tego, kto i do czego ma dostęp.

## <a name="hello-intune"></a>Usługa Intune
Wiele organizacji, takich jak Microsoft, zabezpiecza dane własnościowe używane przez użytkowników na urządzeniach przenośnych osobistych i należących do firmy przy użyciu usługi Intune. Funkcje usługi Intune, takie jak zasady konfiguracji urządzeń i aplikacji, zasady aktualizacji oprogramowania oraz stany instalacji (wykresy, tabele i raporty), ułatwiają zabezpieczanie i monitorowanie dostępu do danych.

Wiele osób korzysta z wielu różnych urządzeń, na których używane są różne platformy. Na przykład pracownik może używać komputera Surface Pro do pracy i urządzenia przenośnego z systemem Android do spraw osobistych. Typowe jest też uzyskiwanie dostępu do zasobów organizacji, takich jak programy Microsoft Outlook i SharePoint, przy użyciu tych wielu urządzeń.

Za pomocą usługi Intune można zarządzać wieloma urządzeniami na osobę i różnymi platformami działającymi na poszczególnych urządzeniach, w tym systemami iOS, macOS, Android i Windows. W usłudze Intune zasady i ustawienia są podzielone według platformy urządzeń. Dzięki temu można łatwo wyświetlać urządzenia korzystające z określonej platformy i nimi zarządzać.

**[Typowe scenariusze](https://docs.microsoft.com/intune/common-scenarios)** to świetny zasób pozwalający przekonać się, jak usługa Intune obsługuje typowe zagadnienia związane z pracą z urządzeniami przenośnymi. Oto czego dotyczą te scenariusze:  
- Ochrona poczty e-mail obsługiwanej przy użyciu lokalnego programu Exchange
- Bezpieczne uzyskiwanie dostępu do usługi Office 365
- Uzyskiwanie dostępu do zasobów organizacji za pomocą urządzeń osobistych

## <a name="integration-with-secure-and-protect-services"></a>Integracja z usługami zabezpieczania i ochrony
Kluczowym zadaniem dowolnego rozwiązania do zarządzania urządzeniami jest zapewnienie zabezpieczeń i ochrony. Usługa Intune jest doskonale zintegrowana z innymi usługami na potrzeby realizacji tego zadania. Przykład:

- Rozwiązanie **Microsoft 365** to kluczowy składnik upraszczania typowych zadań informatycznych. W centrum administracyjnym platformy Microsoft 365 możesz tworzyć użytkowników i zarządzać grupami. Możesz także uzyskać dostęp do innych usług, takich jak Intune, Azure AD i nie tylko. 

  W rozwiązaniu Microsoft 365 można na przykład utworzyć grupę urządzeń z systemem iOS. Następnie przy użyciu usługi Intune można wypychać do tej grupy urządzeń z systemem iOS zasady dotyczące funkcji systemu iOS, takich jak między innymi dostęp do sklepu z aplikacjami, używanie funkcji AirDrop, tworzenie kopii zapasowych w usłudze iCloud i korzystanie z filtru internetowego firmy Apple.

- Program **Windows Defender** zawiera wiele funkcji zabezpieczeń ułatwiających chronienie urządzeń z systemem Windows 10. Używanie usługi Intune i programu Windows Defender w połączeniu umożliwia na przykład: 

    - Wyszukiwanie podejrzanych działań w plikach i aplikacjach na urządzeniach przenośnych za pomocą [filtru Windows Defender SmartScreen](https://docs.microsoft.com/intune/endpoint-protection-windows-10). 
    - Zapobieganie naruszeniom zabezpieczeń na urządzeniach przenośnych za pomocą [zaawansowanej ochrony przed zagrożeniami w usłudze Windows Defender](https://docs.microsoft.com/intune/advanced-threat-protection). Ograniczanie skutków naruszenia zabezpieczeń przez zablokowanie dostępu użytkownika do zasobów firmowych.

- **Dostęp warunkowy** to funkcja usługi Azure Active Directory, która jest bardzo dobrze zintegrowana z usługą Intune. Za pomocą [dostępu warunkowego](https://docs.microsoft.com/intune/conditional-access) można zadbać o to, aby dostęp do poczty e-mail, programu SharePoint i innych aplikacji miały tylko zgodne urządzenia. 

## <a name="choose-the-device-management-solution-thats-right-for-you"></a>Wybieranie odpowiedniego rozwiązania do zarządzania urządzeniami

Istnieje kilka różnych metod zarządzania urządzeniami. Po pierwsze można zarządzać różnymi aspektami urządzeń przy użyciu funkcji wbudowanych w usługę Intune. Takie podejście nazywane jest **zarządzaniem urządzeniami mobilnymi (MDM)** . W takim przypadku użytkownicy „rejestrują” urządzenia i komunikują się z usługą Intune przy użyciu certyfikatów. Administrator IT może między innymi wypychać aplikacje na urządzenia, ograniczać urządzenia do określonego systemu operacyjnego i blokować urządzenia osobiste. Jeśli jakieś urządzenie zostanie kiedykolwiek zgubione lub skradzione, może on też usunąć z niego wszystkie dane. 

W przypadku drugiej metody zarządza się aplikacjami na urządzeniach. To podejście nazywane jest **zarządzaniem aplikacjami mobilnymi (MAM)** . W tym przypadku użytkownicy mogą uzyskiwać dostęp do zasobów organizacji za pomocą urządzeń osobistych. Podczas otwierania aplikacji, takich jak poczta e-mail lub program SharePoint, użytkownicy są monitowani o dodatkowe uwierzytelnienie. Jeśli jakieś urządzenie zostanie kiedykolwiek zgubione lub skradzione, można usunąć z niego wszystkie dane organizacji. 

Można również używać połączenia metod [MDM i MAM](https://docs.microsoft.com/intune/byod-technology-decisions).

Po skonfigurowaniu usługi Intune wybiera się też opcję zarządzania urządzeniami wyłącznie w witrynie Azure Portal lub zarządzania urządzeniami za pomocą połączenia usługi Intune i rozwiązania Microsoft 365. Na stronie [Migrating mobile device management to Intune in the Azure portal (Migracja zarządzania urządzeniami mobilnymi do usługi Intune za pomocą witryny Azure Portal)](https://www.microsoft.com/itshowcase/Article/Content/1042/Migrating-mobile-device-management-to-Intune-in-the-Azure-portal) przedstawiono analizę przypadku działu informatycznego firmy Microsoft. Z tej analizy przypadku dowiesz się, jak dział informatyczny firmy Microsoft wprowadzić nowoczesne podejście do zarządzania urządzeniami, i poznasz wnioski z tej sytuacji.

## <a name="simplify-it-tasks-using-the-device-management-dashboard"></a>Upraszczanie zadań informatycznych za pomocą pulpitu nawigacyjnego zarządzania urządzeniami

[Pulpit nawigacyjny zarządzania urządzeniami](https://devicemanagement.portal.azure.com/) to pojedyncze miejsce do zarządzania urządzeniami przenośnymi i realizowania związanych z nimi zadań. Ten pulpit nawigacyjny zawiera usługi służące do zarządzania urządzeniami, w tym Intune i Azure Active Directory, a także do zarządzania aplikacjami klienckimi. 

Oto zadania, które można realizować na pulpicie nawigacyjnym zarządzania urządzeniami:

- [Rejestrowanie urządzeń](https://docs.microsoft.com/intune/device-enrollment)
- [Ustawianie zgodności urządzenia](https://docs.microsoft.com/intune/device-compliance-get-started)
- [Zarządzanie urządzeniami](https://docs.microsoft.com/intune/device-management)
- [Zarządzanie aplikacjami](https://docs.microsoft.com/intune/app-management)  
- [Książki elektroniczne dla systemu iOS](https://docs.microsoft.com/intune/vpp-ebooks-ios)  
- [Instalowanie lokalnego łącznika programu Exchange](https://docs.microsoft.com/intune/exchange-connector-install)  
- [Zarządzanie rolami](https://docs.microsoft.com/intune/role-based-access-control)  
- Zarządzanie aktualizacjami oprogramowania
  - [Zarządzanie aktualizacjami systemu Windows 10](https://docs.microsoft.com/intune/windows-update-for-business-configure)  
  - [Zarządzanie aktualizacjami systemu iOS](https://docs.microsoft.com/intune/software-updates-ios)  
- [Azure Active Directory](https://docs.microsoft.com/azure/active-directory)  
- [Zarządzanie użytkownikami](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory)
- [Zarządzanie grupami i członkami](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups)
- [Rozwiązywanie problemów](https://docs.microsoft.com/intune/help-desk-operators)

## <a name="next-step"></a>Następny krok
Gdy wszystko będzie gotowe do rozpoczęcia pracy z rozwiązaniem MDM lub MAM, skorzystaj z dalszych instrukcji konfigurowania usługi Intune, rejestrowania urządzeń i tworzenia zasad. Artykuł [Mobile device management for Microsoft 365 (Zarządzanie urządzeniami mobilnymi w rozwiązaniu Microsoft 365)](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure) również stanowi świetne źródło informacji.
