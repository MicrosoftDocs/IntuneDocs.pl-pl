---
title: "Zasady zgodności urządzeń | Microsoft Docs"
description: "W tym temacie opisano, czym są zasady zgodności urządzeń i jak działają."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0775107a-6662-41c8-9404-be14bbb599f3
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 7b91e52d72704b6beb79a1b35bb1a24ebb340a4b


---

# <a name="device-compliance-policies-in-microsoft-intune"></a>Zasady zgodności urządzeń w usłudze Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="what-is-a-compliance-policy"></a>Czym jest zasada zgodności?
Aby pomóc chronić dane firmy, należy się upewnić, że urządzenia używane do uzyskiwania dostępu do aplikacji oraz danych firmowych spełniają pewne reguły. Te reguły mogą obejmować wymaganie użycia numeru PIN w celu uzyskania dostępu do urządzeń oraz szyfrowanie danych przechowywanych na urządzeniach. Zestaw takich reguł jest nazywany zasadami zgodności.

## <a name="how-should-i-use-compliance-policies"></a>Jak używać zasad zgodności?
Zasad zgodności można używać z zasadami dostępu warunkowego, aby zezwolić na dostęp do poczty e-mail i innych usług tylko tym urządzeniom, które spełniają reguły zasad zgodności. Aby dowiedzieć się, jak dwa zbiory zasad mogą być używane razem, przeczytaj artykuł [Ograniczanie dostępu do usługi poczty e-mail i usługi O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).

Zasady zgodności mogą być również stosowane niezależnie od dostępu warunkowego. Jeśli zasady zgodności są stosowane niezależnie, urządzenia docelowe są oceniane, po czym generowany jest raport z ich stanem zgodności. Na przykład może być potrzebny raport z liczbą urządzeń, które nie są szyfrowane, lub urządzeń, na których zdjęto zabezpieczenia systemu albo uzyskano dostęp do konta root. Ale jeśli zasady zgodności są stosowane niezależnie, to nie istnieją żadne domyślne ograniczenia dostępu do zasobów firmowych.

Zasady zgodności wdraża się dla użytkowników. Gdy zasady zgodności są wdrażane dla użytkownika, sprawdzana jest zgodność urządzeń użytkownika.
Aby uzyskać informacje o tym, ile czasu potrzeba na otrzymanie zasad przez urządzenia przenośne po wdrożeniu tych zasad, zobacz [Zarządzanie ustawieniami i funkcjami urządzeń](https://docs.microsoft.com/en-us/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#frequently-asked-questions-about-intune-policies).

Poniższa tabela zawiera listę typów urządzeń, które są obsługiwane przez zasady zgodności. W tabeli opisano też sposób postępowania z niezgodnymi ustawieniami w przypadku, gdy zasady zgodności są używane wraz z zasadami dostępu warunkowego.

-----------------------------

|Ustawienie zasad| Windows 8.1 i nowsze| System Windows Phone 8.1 lub nowszy| System iOS 8.0 i nowsze|Android 4.0 i nowsze<br/>Samsung Knox Standard 4.0 i nowsze|
|-----|----|----|----|----|
|**Konfiguracja kodu PIN lub hasła** |Skorygowane|Skorygowane|Skorygowane|Poddane kwarantannie|
|**Szyfrowanie urządzenia**|Nie dotyczy|Skorygowane|Skorygowane (przez ustawienie kodu PIN)|Poddane kwarantannie|
|**Urządzenie ze złamanymi ograniczeniami lub z odblokowanym dostępem**|Nie dotyczy|Nie dotyczy|Poddane kwarantannie (to nie jest ustawienie)|Poddane kwarantannie (to nie jest ustawienie)|
|**Profil e-mail**|Nie dotyczy|Nie dotyczy|Poddane kwarantannie|Nie dotyczy|
|**Minimalna wersja systemu operacyjnego**|Poddane kwarantannie|Poddane kwarantannie|Poddane kwarantannie|Poddane kwarantannie|
|**Maksymalna wersja systemu operacyjnego**|Poddane kwarantannie|Poddane kwarantannie|Poddane kwarantannie|Poddane kwarantannie|
|**Zaświadczanie o kondycji systemu Windows**|Poddane kwarantannie: Windows 10 i Windows 10 Mobile<br /><br />Nie dotyczy: Windows 8.1|Nie dotyczy|Nie dotyczy|Nie dotyczy|

------------------------------

**Skorygowane** — system operacyjny urządzenia wymusza zgodność. (Na przykład użytkownik jest zmuszony do ustawienia kodu PIN).

**Poddane kwarantannie** — system operacyjny urządzenia nie wymusza zgodności. (Na przykład urządzenie z systemem Android nie zmusza użytkownika do szyfrowania urządzenia). Gdy urządzenia nie są zgodne, zostaną wykonane następujące akcje:

-   Urządzenie zostanie zablokowane, jeśli użytkownik podlega zasadom dostępu warunkowego.

-   Portal firmy powiadomi użytkownika o wszelkich problemach ze zgodnością.

## <a name="next-steps"></a>Następne kroki
[Tworzenie zasad zgodności urządzenia](create-a-device-compliance-policy-in-microsoft-intune.md)

[Wdrażanie i monitorowanie zasad zgodności urządzenia](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### <a name="see-also"></a>Zobacz też
[Ograniczanie dostępu do usługi poczty e-mail i usługi O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


