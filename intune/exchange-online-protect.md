---
title: Program Exchange bez zarządzania urządzeniami
titleSuffix: Microsoft Intune
description: Użyj usługi Microsoft Intune, aby zapewnić pracownikom dostęp do poczty e-mail usługi Office 365 Exchange Online bez potrzeby konfigurowaniem systemu zarządzania urządzeniami.
keywords: Dostęp do poczty e-mail w usłudze Office 365 Exchange
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/31/2017
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.topic: archived
ms.technology: ''
ms.assetid: 88a0d3b9-2622-403b-8374-1396afd8066e
ms.reviewer: pchacon
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5f61b7e755ea7bfe8d20c3db8c859f148dcf7704
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57460431"
---
# <a name="protect-office-365-exchange-online-without-requiring-device-management"></a>Ochrona usługi Office 365 Exchange Online bez konieczności zarządzania urządzeniami

Jeśli chcesz zapewnić pracownikom dostęp do służbowej poczty e-mail bez ponoszenia kosztów związanych z konfigurowaniem systemu zarządzania urządzeniami, możesz to zrobić. Możesz zapewnić dostęp do usługi Office 365 Exchange Online za pośrednictwem usługi Intune. Aby móc wykonać niezbędne kroki, upewnij się, że masz licencję na usługę Microsoft 365 lub usługi Azure Active Directory (Premium) i Intune. Pracownicy muszą posiadać [obsługiwane urządzenie z systemem iOS lub Android](supported-devices-browsers.md). 

Jeśli postanowisz skonfigurować system zarządzania urządzeniami, możesz to zrobić. Ten typ ochrony aplikacji działa niezależnie od zarządzania urządzeniami. 

## <a name="action-plan"></a>Plan działania

1. [Zapoznanie się z dostępem warunkowym](conditional-access.md). 
2. [Zapoznanie się z dostępem warunkowym opartym na aplikacji](app-based-conditional-access-intune.md).
3. [Skonfigurowanie zasad dostępu warunkowego opartego na aplikacji dla usługi Exchange Online](app-based-conditional-access-intune-create.md).
4. [Zablokowanie aplikacji, którymi nie można zarządzać](app-modern-authentication-block.md), a w szczególności aplikacji, które nie korzystają z biblioteki uwierzytelniania usługi Azure Active Directory (ADAL).
5. (Opcjonalnie) [Skonfigurowanie zasad dostępu warunkowego opartego na aplikacji dla usługi SharePoint Online](app-based-conditional-access-intune-create.md). Te zasady blokują dostęp do danych firmowych aplikacjom, którymi nie można zarządzać i których nie można zabezpieczyć. Te zasady ograniczają także dostęp za pośrednictwem programu SharePoint dla urządzeń przenośnych. 

## <a name="what-to-tell-employees-and-students"></a>Co powiedzieć pracownikom i uczniom

* Poproś pracowników oraz uczniów o pobranie i zainstalowanie programu Outlook lub Microsoft SharePoint dla systemu iOS ze sklepu App Store firmy Apple lub dla systemu Android ze sklepu Google Play. 
* Jeśli zablokujesz dostęp do aplikacji, które nie korzystają z nowoczesnego uwierzytelniania, powiadom pracowników i uczniów o tym ograniczeniu. 

## <a name="next-steps"></a>Następne kroki

Przy użyciu dostępu warunkowego opartego na aplikacji zwiększono bezpieczeństwo danych firmowych. W ramach kolejnych kroków możesz dowiedzieć się więcej o innych sposobach zwiększenia ochrony danych firmowych, takich jak: 

* Skonfigurowanie [dostępu warunkowego opartego na zgodności urządzeń, ryzyku urządzeń, lokalizacji i atrybutów użytkownika w usługach Active Directory i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).  
* Skonfigurowanie zasad ochrony aplikacji w celu ułatwienia ochrony danych firmowych przed zamierzonymi lub przypadkowymi przeciekami danych. 
* Ochrona danych firmowych poza siecią przy użyciu usługi Azure Information Protection. 

Potrzebujesz pomocy dotyczącej włączenia tego lub innych scenariuszy EMS bądź usługi Office 365? Jeśli masz co najmniej 150 licencji usługi Microsoft 365, pakietu Enterprise Mobility + Security lub usługi Azure Active Directory Premium, wykorzystaj [możliwości rozwiązania FastTrack](https://docs.microsoft.com/enterprise-mobility-security/solutions/enterprise-mobility-fasttrack-program). 
