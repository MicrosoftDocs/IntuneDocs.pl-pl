---
title: "Zapobieganie wyciekom danych na urządzeniach niezarządzanych"
description: "Zezwalaj na dostęp do danych firmowych na urządzeniach i chroń dane przed wyciekami."
keywords: "ochrona danych zapobieganie wyciekom na urządzeniach O365 Office 365"
author: arob98
manager: angrobe
ms.date: 09/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b1512c3a-3bbd-4111-a0df-c874a0a335df
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3ae8702c51df1c3c2b8e6dd2a79bf4599e6b7677
ms.sourcegitcommit: 29ee35da2864b25f4432d2423b285014c77040af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2017
---
# <a name="prevent-data-leaks-on-non-managed-devices"></a>Zapobieganie wyciekom danych na urządzeniach niezarządzanych

Jeśli zezwolisz na dostęp do firmowych danych hostowanych przez usługi Office 365, możesz kontrolować sposób, w jaki użytkownicy udostępniają i zapisują dane, bez ryzyka zamierzonych lub przypadkowych wycieków. Usługa Microsoft Intune dostarcza zasady ochrony aplikacji, które ustawia się w celu zabezpieczenia danych firmowych na urządzeniach będących własnością użytkowników. Urządzenia nie muszą być zarejestrowane w usłudze Intune. 

Zasady ochrony aplikacji ustawione przy użyciu usługi Intune również działają na urządzeniach zarządzanych za pomocą rozwiązania do zarządzania urządzeniami z systemem innym niż Microsoft. Dane osobowe na urządzeniach pozostają nienaruszone; jedynie dane firmowe są zarządzane przez dział IT. 

W celu ochrony danych firmowych można ustawić zasady ochrony aplikacji dla aplikacji mobilnych pakietu Office na urządzeniach z systemem Windows, iOS lub Android. Zasady te pozwalają na ustawienie zasad takich jak oparty na aplikacji numer PIN czy szyfrowanie danych firmowych lub bardziej zaawansowanych ustawień mających na celu ograniczenie sposobu, w jaki użytkownicy używają funkcji Wytnij, Kopiuj, Wklej oraz Zapisz jako między aplikacjami zarządzanymi i niezarządzanymi. Można także zdalnie wyczyścić dane firmowe bez konieczności rejestrowania urządzeń przez użytkowników. 

Zasady ochrony aplikacji usługi Intune są niezależne od zarządzania urządzeniami. Zasady ochrony aplikacji umożliwiają zarządzanie aplikacjami mobilnymi pakietu Office na urządzeniach niezarządzanych i zarządzanych przez usługę Intune, a także urządzeniach zarządzanych przez rozwiązania do zarządzania urządzeniami przenośnymi innych firm niż Microsoft. 

## <a name="before-you-begin"></a>Przed rozpoczęciem

Gdy zostaną spełnione następujące wymagania, można użyć poniższego planu działania:
* Firma jest gotowa do bezpiecznego przejścia do chmury.
* Firma korzysta z usług Office 365 Exchange Online, SharePoint Online i OneDrive dla Firm lub Yammer.
* Firma ma licencje dla rozwiązań Microsoft 365, Enterprise Mobility + Security (EMS) lub Azure Information Protection.
* Firma zezwala użytkownikom na dostęp do danych firmowych z urządzeń należących do firmy lub osobistych urządzeń z systemem Windows, iOS lub Android. 
* Firma nie chce wymagać rejestracji urządzeń osobistych w usłudze zarządzania urządzeniami. 

## <a name="action-plan"></a>Plan działania

Dla urządzeń z systemem iOS lub Android: 

1. Dowiedz się, [jak działają zasady ochrony aplikacji](app-protection-policy.md).
2. Dowiedz się, [jak utworzyć i wdrożyć zasady ochrony aplikacji](app-protection-policies.md) dla aplikacji mobilnych pakietu Office. 
3. [Monitoruj zasady ochrony aplikacji](app-protection-policies-monitor.md), które tworzysz i wdrażasz. 

Dla urządzeń z systemem Windows 10: 

1. Dowiedz się, [jak działa rozwiązanie Windows Information Protection (WIP)](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip). 
2. Przygotuj się do skonfigurowania [zasad ochrony aplikacji dla systemu Windows 10](app-protection-policies-configure-windows-10.md).
3. [Utwórz i wdróż zasad ochrony aplikacji w rozwiązaniu WIP za pomocą usługi Intune](windows-information-protection-policy-create.md).

## <a name="what-to-tell-employees-and-students"></a>Co powiedzieć pracownikom i uczniom

Zgodnie z potrzebami udostępnij poniższe linki, aby dostarczyć dodatkowe informacje: 
* [Czego można oczekiwać, gdy aplikacja systemu iOS jest zarządzana przy użyciu zasad ochrony aplikacji](app-protection-enabled-apps-ios.md)
* [Czego można oczekiwać, gdy aplikacja dla systemu Android jest zarządzana przy użyciu zasad ochrony aplikacji](app-protection-enabled-apps-android.md) 

## <a name="next-steps"></a>Następne kroki

Potrzebujesz pomocy dotyczącej włączenia tego lub innych scenariuszy EMS bądź usługi Office 365? Jeśli masz co najmniej 150 licencji usługi Microsoft 365, pakietu Enterprise Mobility + Security lub usługi Azure Active Directory Premium, wykorzystaj [możliwości rozwiązania FastTrack](https://docs.microsoft.com/enterprise-mobility-security/solutions/enterprise-mobility-fasttrack-program). 