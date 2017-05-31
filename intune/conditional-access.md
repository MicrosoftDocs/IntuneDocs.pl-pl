---
title: "Co to jest dostęp warunkowy?"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: poznaj sposoby definiowania warunków, które muszą spełniać użytkownicy i urządzenia, aby uzyskać dostęp do zasobów firmy w wersji zapoznawczej programu Microsoft Intune Azure."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 8ab6d782460a857a0901abd9bd567365ee2e3f70
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="what-is-conditional-access"></a>Co to jest dostęp warunkowy?


[!INCLUDE[azure_preview](./includes/azure_preview.md)]


W tym temacie opisano funkcję dostępu warunkowego stosowaną w dodatku Enterprise Mobility + Security, a w dalszej kolejności możliwości dostępu warunkowego w usłudze Intune.

Dostęp warunkowy dodatku Enterprise Mobility + Security (EMS) używa możliwości usług Azure Active Directory Premium i Microsoft Intune, aby zapewnić kontrolę wymaganą w celu zabezpieczenia danych firmowych przy jednoczesnym zapewnieniu pracownikom środowiska umożliwiającego pracę z dowolnego urządzenia.

Przy użyciu dostępu warunkowego można określić warunki, które ograniczają dostęp do danych firmowych na podstawie lokalizacji, stanu urządzeń, stanu użytkownika i ważności aplikacji.

Z perspektywy urządzenia usługi Intune i Azure Active Directory działają razem w celu zapewnienia, że tylko zarządzane i zgodne urządzenia mają możliwość uzyskania dostępu do poczty e-mail i usług Office 365. Można na przykład w usłudze Azure Active Directory ustawić zasady zezwalające na dostęp do usług Office 365 tylko komputerom dołączonym do domeny lub urządzeniom przenośnym zarejestrowanym w aplikacji do zarządzania urządzeniami przenośnymi, takiej jak usługa Intune. Do ustawienia profilu zgodności urządzenia, który ocenia stan jego zgodności, można skorzystać z usługi Intune. Stan zgodności jest zgłaszany do usługi Azure Active Directory w celu zastosowania do wymuszania zasad w usłudze Azure Active Directory, gdy użytkownik próbuje uzyskać dostęp do zasobów firmy. Aby uzyskać informacje dotyczące zgodności urządzeń w usłudze Intune, zobacz artykuł [Co to jest zgodność urządzeń?](device-compliance.md).

Funkcję dostępu warunkowego dla aplikacji w chmurze, takich jak Exchange Online, można skonfigurować za pomocą usługi Azure Active Directory. Więcej informacji znajduje się w tym [artykule](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

## <a name="on-premises-conditional-access-in-intune"></a>Lokalny dostęp warunkowy w usłudze Intune

Funkcji dostępu warunkowego w usłudze Intune można użyć do zezwalania lub blokowania dostępu do **lokalnej instalacji programu Exchange** na podstawie zarządzania urządzeniami i ich rejestracji.

Ustawienia profilu zgodności urządzenia są używane do oceny jego zgodności. Funkcja dostępu warunkowego używa oceny do zezwalania na dostęp do lokalnego programu Exchange lub jego blokowania. Jeśli funkcja dostępu warunkowego jest stosowana w połączeniu z profilem zgodności urządzenia, tylko zgodne urządzenia będą miały dostęp do lokalnego programu Exchange. Dla celów bardziej szczegółowej kontroli można skonfigurować ustawienia zaawansowane funkcji dostępu warunkowego, takie jak umożliwianie lub blokowanie niektórych platform lub natychmiastowe blokowanie urządzeń, które nie są zarządzane przez usługę Intune.

Profil zgodności urządzenia i dostęp warunkowy są przypisane do użytkownika. Wszystkie urządzenia, których użytkownik używa do uzyskiwania dostępu do lokalnego programu, są sprawdzane pod kątem zgodności. Należy pamiętać, że użytkownik używający urządzenia musi mieć przypisany do niego profil, aby urządzenie mogło zostać ocenione pod kątem zgodności. Jeśli na urządzeniu nie wdrożono żadnych zasad zgodności dla użytkownika, będzie ono traktowane jako zgodne i nie będą stosowane żadne ograniczenia dostępu.

Jeśli urządzenia nie spełniają warunków, użytkownik jest przeprowadzany przez procedurę rejestracji urządzenia i rozwiązywania problemu powodującego jego niezgodność.

## <a name="next-steps"></a>Następne kroki

[Tworzenie zasad dostępu warunkowego do lokalnego programu Exchange](conditional-access-exchange-create.md)

[Konfigurowanie dostępu warunkowego w usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

