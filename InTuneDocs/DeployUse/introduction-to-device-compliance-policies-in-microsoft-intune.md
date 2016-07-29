---
title: "Zasady zgodności urządzeń | Microsoft Intune"
description: "W tym temacie opisano istotne pojęcia związane z tym, czym są zasady zgodności urządzeń i jak działają."
keywords: 
author: karthikaraman
manager: jeffgilb
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0775107a-6662-41c8-9404-be14bbb599f3
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c72c8e1a764af73ba4d421ca6637ee91ab7bca0a
ms.openlocfilehash: f34ff402ae1012a471219647e94bc1f5225a6f07


---

# Zasady zgodności urządzeń w usłudze Microsoft Intune
## Czym jest zasada zgodności?
Aby chronić dane firmy, należy się upewnić, że urządzenia używane do uzyskiwania dostępu do aplikacji oraz danych firmowych spełniają pewne reguły, takie jak wymaganie użycia numeru PIN w celu uzyskania dostępu do urządzenia oraz szyfrowanie danych przechowywanych na urządzeniu. Zestaw takich reguł jest nazywany zasadami zgodności.

## Jak używać zasad zgodności?
Zasad zgodności można używać z zasadami dostępu warunkowego, aby zezwolić na dostęp do poczty e-mail i innych usług tylko tym urządzeniom, które spełniają reguły zasad zgodności. Aby zrozumieć, jak dwa zbiory zasad mogą być używane razem, przeczytaj artykuł [Ograniczanie dostępu do usługi poczty e-mail i usługi O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).

Zasady zgodności mogą być również stosowane niezależnie od dostępu warunkowego. Jeśli używane są niezależnie, urządzenia docelowe są oceniane, po czym generowany jest raport z ich stanem zgodności. Na przykład może być potrzebny raport z liczbą urządzeń, które nie są szyfrowane, lub urządzeń, na których zdjęto zabezpieczenia systemu albo uzyskano dostęp do konta root. Jednak w przypadku użycia niezależnego nie istnieją żadne domyślne ograniczenia dostępu do zasobów firmowych.

Zasady zgodności wdraża się dla użytkowników. Gdy zasady zgodności są wdrażane dla użytkownika, sprawdzana jest zgodność urządzeń użytkownika.

W poniższej tabeli przedstawiono typy urządzeń obsługiwanych przez zasady zgodności oraz sposób postępowania z niezgodnymi ustawieniami w przypadku, gdy zasady są używane w celu zapewnienia dostępu warunkowego.

--------------

|Ustawienie zasad| Windows 8.1 i nowsze| System Windows Phone 8.1 lub nowszy| System iOS 6.0 lub nowszy|Android 4.0 i nowsze<br/>KNOX Samsung  Standard 4.0 i nowsze|
|-----|----|----|----|
|**Konfiguracja kodu PIN lub hasła** |Skorygowane|Skorygowane|Skorygowane|Kwarantanna|
|**Szyfrowanie urządzenia**|Brak|Skorygowane|Skorygowane (przez ustawienie kodu PIN)|Kwarantanna|
|**Urządzenia, na których zdjęto zabezpieczenia systemu lub uzyskano dostęp do konta administratora**|Brak|Brak|Poddane kwarantannie (to nie jest ustawienie)|Poddane kwarantannie (to nie jest ustawienie)|
|**Profil e-mail**|Brak|Brak|Kwarantanna|Brak|
|**Minimalna wersja systemu operacyjnego**|Kwarantanna|Poddane kwarantannie|Poddane kwarantannie|Kwarantanna|
|**Maksymalna wersja systemu operacyjnego**|Kwarantanna| Poddane kwarantannie| Poddane kwarantannie| Kwarantanna|
|**Zaświadczanie o kondycji systemu Windows**|System Windows 10 i Windows 10 Mobile zostały poddane kwarantannie.<br /><br />Ustawienie nie ma zastosowania do systemu Windows 8.1|Brak|Brak|Brak|
--------------
**Skorygowane** = zgodność jest wymuszana przez system operacyjny urządzenia (na przykład system wymusza na użytkowniku ustawienie kodu PIN).  Nigdy nie występuje niezgodność tego ustawienia.

**Poddane kwarantannie** = system operacyjny urządzenia nie wymusza zgodności (na przykład urządzenie z systemem Android nie zmusza użytkownika do szyfrowania urządzenia). Gdy urządzenia nie są zgodne, zostaną wykonane następujące akcje:

-   Urządzenie zostanie zablokowane, jeśli użytkownik podlega zasadom dostępu warunkowego.

-   Portal firmy powiadomi użytkownika o wszelkich problemach ze zgodnością.

## Następne kroki
[Tworzenie zasad zgodności urządzenia](create-a-device-compliance-policy-in-microsoft-intune.md)

[Wdrażanie i monitorowanie zasad zgodności urządzenia](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### Zobacz także
[Ograniczanie dostępu do usługi poczty e-mail i usługi O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


