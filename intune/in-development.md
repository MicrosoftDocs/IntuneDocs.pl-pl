---
title: W trakcie opracowywania — Microsoft Intune
titleSuffix: ''
description: Funkcje usługi Microsoft Intune w trakcie opracowywania
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/29/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3645d07fe9a703f182e05bc9a7f9fbb93c413ddc
ms.sourcegitcommit: dfcf80a91792715404dc021c8684866c8b0a27e1
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2019
ms.locfileid: "65816239"
---
# <a name="in-development-for-microsoft-intune---may-2019"></a>Funkcje usługi Microsoft Intune w trakcie opracowywania — maj 2019 r.

Aby ułatwić Ci planowanie, na tej stronie udostępniamy listę aktualizacji interfejsu użytkownika i funkcji usługi Intune, które są obecnie opracowywane, a zostaną wydane w przyszłości. Ponadto:

- Jeśli przewidujemy, że przed wprowadzeniem zmiany będzie konieczne wykonanie określonych działań, opublikujemy również dodatkowy wpis w Centrum wiadomości usługi Office.
- Po wprowadzeniu funkcji w środowisku produkcyjnym — w wersji zapoznawczej lub ogólnie dostępnej — opis tej funkcji zostanie przeniesiony z tej strony na stronę [Co nowego](whats-new.md).
- Ta strona oraz strona [Co nowego](whats-new.md) są okresowo aktualizowane. Odwiedź ją ponownie, aby sprawdzić dodatkowe aktualizacje.
- Zobacz [harmonogram działania dla platformy M365](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS), aby poznać strategiczne cele i terminy.

> [!Note]
> Te elementy odzwierciedlają aktualne plany firmy Microsoft dotyczące funkcji usługi Intune, które zostaną wprowadzone w przyszłych wydaniach. Zarówno daty, jak i poszczególne funkcje mogą ulec zmianie. Nie wszystkie elementy będące w trakcie opracowywania zostały opisane na tej stronie.

**Kanał informacyjny RSS**: otrzymuj powiadomienie, gdy ta strona zostanie zaktualizowana przez skopiowanie i wklejenie następującego adresu URL w czytniku kanałów informacyjnych: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Usługa Intune w witrynie Azure Portal


<!-- 1905 start-->


### <a name="baseline-support-for-keyword-search-----3082036-----------"></a>Obsługa wyszukiwania punktów odniesienia według słów kluczowych  <!-- 3082036         -->
Podczas tworzenia lub edytowania profilu punktów odniesienia zabezpieczeń wkrótce będzie można używać *wyszukiwania* do filtrowania ustawień wyświetlanych w konsoli.   

### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api----3295288---"></a>Zbiorcze resetowanie i czyszczenie urządzeń za pomocą interfejsu API programu Graph <!-- 3295288 -->
Za pomocą interfejsu API programu Graph będzie można zbiorczo resetować i czyścić do 100 urządzeń.

<!-- 1904 start-->

### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Użytkownicy urządzeń mogą wyświetlać wszystkie zarządzane aplikacje, które zainstalowali lub próbowali zainstalować <!-- 2352913 -->
W aplikacji Portal firmy dla systemu Windows będzie dostępna lista wszystkich zarządzanych aplikacji (zarówno wymaganych, jak i dostępnych), które zainstalowano na urządzeniu użytkownika. Użytkownicy będą mogli wyświetlać aplikacje, które próbowano zainstalować lub które oczekują na instalację, wraz z bieżącym stanem. Jeśli organizacja nie określa aplikacji jako wymagane lub dostępne, użytkownicy zobaczą komunikat z informacją, że nie zainstalowano żadnych aplikacji firmowych. Użytkownicy będą również mogli sortować lub filtrować swoje aplikacje według stanu instalacji.

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Używanie „reguł stosowania” podczas tworzenia profili konfiguracji urządzeń z systemem Windows 10 <!-- 2549910 -->
Obecnie możesz tworzyć profile konfiguracji urządzeń z systemem Windows 10 (**Konfiguracja urządzeń** > **Profile** > **Utwórz profil** > **Windows 10** jako platforma). W przyszłości będzie możliwe również tworzenie **reguł stosowania**, aby profil był stosowany tylko do określonej edycji lub wersji. Możesz na przykład utworzyć profil włączający określone ustawienia funkcji BitLocker. Gdy dodasz ten profil, reguła stosowania umożliwi zastosowanie go tylko do urządzeń z systemem Windows 10 Enterprise.

Dotyczy: 
- System Windows 10 lub nowszy



## <a name="notices"></a>Uwagi

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Zobacz także
Aby dowiedzieć się więcej o najnowszych zmianach, zobacz [Co nowego w usłudze Microsoft Intune](whats-new.md).


