---
title: "Dokąd została przeniesiona funkcja usługi Intune na platformie Azure?"
titleSuffix: Intune on Azure
description: "Ułatwia znajdowanie funkcji usługi Intune w konsoli platformy Azure."
keywords: 
author: dagerrit
ms.author: dagerrit
manager: angrobe
ms.date: 03/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 18e5ea572bde503600bc33a0b4401efed2e35d18
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2017
---
# <a name="where-did-my-intune-feature-go-in-azure"></a>Dokąd została przeniesiona funkcja usługi Intune na platformie Azure?
Przenosząc usługę Intune do witryny Azure Portal, skorzystaliśmy z okazji, aby uporządkować niektóre zadania w bardziej logiczny sposób. Jednak każde ulepszenie wymaga nauczenia się nowego porządku. Dlatego przygotowaliśmy ten przewodnik dla osób, które doskonale znają usługę Intune w konsoli klasycznej i zastanawiają się, jak zrobić coś w usłudze Intune na platformie Azure. Jeśli w tym artykule nie została uwzględniona funkcja, którą próbujesz znaleźć, pozostaw komentarz na końcu artykułu, abyśmy mogli go zaktualizować.
## <a name="quick-reference-guide"></a>Krótki przewodnik
|Funkcja |Ścieżka w konsoli klasycznej|Ścieżka w usłudze Intune na platformie Azure|
|------------|---------------|---------------|
|Device Enrollment Program (DEP) |Administracja > Zarządzanie urządzeniami przenośnymi > iOS i Mac OS X > Device Enrollment Program|[Rejestrowanie urządzenia > Rejestracja Apple > Token programu Enrollment Program](#where-did-apple-dep-go) |
|Device Enrollment Program (DEP)| Administracja > Zarządzanie urządzeniami przenośnymi > iOS i Mac OS X > Device Enrollment Program |[Rejestrowanie urządzenia > Rejestracja Apple > Numery seryjne programu Enrollment Program](#where-did-apple-dep-go) |
|Reguły rejestracji |Administracja > Zarządzanie urządzeniami przenośnymi > Reguły rejestracji|[Rejestrowanie urządzenia > Ograniczenia rejestracji](#where-did-enrollment-rules-go) |
|Grupy według numeru seryjnego systemu iOS |Grupy > Wszystkie urządzenia> Wstępnie zarejestrowane urządzenia należące do firmy > Według numeru seryjnego systemu iOS|[Rejestrowanie urządzenia > Rejestracja Apple > Numery seryjne programu Enrollment Program](#where-did-corporate-pre-enrolled-devices-go) |
|Grupy według numeru seryjnego systemu iOS |Grupy > Wszystkie urządzenia> Wstępnie zarejestrowane urządzenia należące do firmy > Według numeru seryjnego systemu iOS| [Rejestrowanie urządzenia > Rejestracja Apple > Numery seryjne AC](#where-did-corporate-pre-enrolled-devices-go)|
|Grupy według numeru IMEI (wszystkie platformy)| Grupy > Wszystkie urządzenia> Wstępnie zarejestrowane urządzenia należące do firmy > Według numeru IMEI (wszystkie platformy) | [Rejestrowanie urządzenia > Identyfikatory urządzeń firmowych](#by-imei-all-platforms)|
| Profil rejestracji urządzeń firmowych| Zasady > Rejestracja urządzeń firmowych | [Rejestrowanie urządzenia > Rejestracja Apple > Profile programu Enrollment Program](#where-did-corporate-pre-enrolled-devices-go) |
| Profil rejestracji urządzeń firmowych | Zasady > Rejestracja urządzeń firmowych | [Rejestrowanie urządzenia > Rejestracja Apple > Profile AC](#where-did-corporate-pre-enrolled-devices-go) |
| Program Android for Work | Administracja > Zarządzanie urządzeniami przenośnymi > Android for Work | Rejestrowanie urządzenia > Rejestracja w programie Android for Work |
| Warunki i postanowienia | Zasady > Warunki i postanowienia | Rejestrowanie urządzeń > Warunki i postanowienia |


## <a name="where-do-i-manage-groups"></a>Gdzie mogę zarządzać grupami?
Do zarządzania grupami w usłudze Intune na platformie Azure służy usługa [Azure Active Directory (AD)](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).

## <a name="where-did-enrollment-rules-go"></a>Dokąd zostały przeniesione reguły rejestracji?
W konsoli klasycznej można było określić reguły rejestracji urządzeń przenośnych oraz nowoczesnych urządzeń z systemem Windows i macOS w rozwiązaniu MDM:

![Ilustracja przedstawiająca klasyczne reguły rejestracji urządzeń przenośnych](./media/01-classic-rules.png)

Te reguły dotyczyły wszystkich bez wyjątku użytkowników na Twoim koncie usługi Intune. W witrynie Azure Portal te reguły są teraz widoczne w dwóch odrębnych typach zasad: ograniczeniach typów urządzeń i ograniczeniach limitu urządzeń:

![Ilustracja przedstawiająca ograniczenia rejestracji urządzeń przenośnych na platformie Azure](./media/02-azure-enroll-restrictions.png)

Domyślne ograniczenie limitu urządzeń odpowiada limitowi rejestracji urządzeń w konsoli klasycznej:

![Ilustracja przedstawiająca ograniczenia limitu urządzeń na platformie Azure](./media/03-azure-device-limit.png)

Domyślne ograniczenie typów urządzeń odpowiada ograniczeniom platformy w konsoli klasycznej:

![Ilustracja przedstawiająca ograniczenia typów urządzeń na platformie Azure](./media/04-azure-platform-restrictions.png)

Funkcją zezwalania lub blokowania urządzeń osobistych zarządza się teraz w ramach konfiguracji platformy ograniczenia typów urządzeń:

![Ilustracja przedstawiająca ustawienia blokowania urządzeń osobistych na platformie Azure](./media/05-azure-personal-block.png)

Nowe możliwości ograniczania zostaną dodane tylko do witryny Azure Portal.

## <a name="where-did-apple-dep-go"></a>Dokąd został przeniesiony program DEP firmy Apple?
W konsoli klasycznej można było skonfigurować usługę Intune tak, aby integrowała się z programem Device Enrollment Program firmy Apple, oraz ręcznie zażądać synchronizacji z usługą firmy Apple:

![Ilustracja przedstawiająca klasyczny token DEP](./media/06-classic-dep-token.png)

W witrynie Azure Portal program Device Enrollment Program firmy Apple konfiguruje się, wykonując te same czynności co w przypadku klasycznej usługi Intune:

![Ilustracja przedstawiająca token DEP na platformie Azure](./media/07-azure-dep-token.png)

Jednak opcja **synchronizacji** w konsoli klasycznej została przeniesiona do przepływu pracy zarządzania numerami seryjnymi, ponieważ tam będą wyświetlane wyniki synchronizacji ręcznej:

![Ilustracja przedstawiająca synchronizację programu DEP na platformie Azure](./media/08-azure-dep-sync.png)

## <a name="where-did-corporate-pre-enrolled-devices-go"></a>Dokąd zostały przeniesione urządzenia zarejestrowane wstępnie należące do firmy?
### <a name="by-ios-serial-number"></a>Według numeru seryjnego systemu iOS
W konsoli klasycznej możesz rejestrować urządzenia z systemem iOS za pomocą programu Device Enrollment Program (DEP) firmy Apple i za pomocą narzędzia Apple Configurator. Obie metody umożliwiają wstępne rejestrowanie urządzeń według numeru seryjnego i obejmują przypisywanie specjalnych profilów rejestracji urządzeń firmowych. Przypisaniem profilu rejestracji przed zarejestrowaniem można zarządzać za pomocą grupy urządzeń **Urządzenie zarejestrowane wstępnie należące do firmy według numeru seryjnego systemu iOS**:

![Ilustracja przedstawiająca klasyczne numery seryjne firmy Apple](./media/09-classic-apple-serials.png)

Na jednej liście znajdują się numery seryjne zarówno dla rejestracji w programie DEP firmy Apple, jak i dla rejestracji w narzędziu Configurator. Aby ograniczyć niezgodność przypisań profilów (profilu w programie DEP do numeru seryjnego w narzędziu AC i na odwrót), w witrynie Azure Portal podzieliliśmy numery seryjne na dwie listy:

**Numery seryjne w programie DEP**
![Ilustracja przedstawiająca numery seryjne w programie DEP na platformie Azure](./media/10-azure-dep-serials.png)

**Numery seryjne w narzędziu Apple Configurator**
![Ilustracja przedstawiająca numery seryjne w narzędziu Apple Configurator na platformie Azure](./media/11-azure-ac-serials.png)

### <a name="by-imei-all-platforms"></a>Według numeru IMEI (wszystkie platformy)

W konsoli klasycznej możesz wstępnie wyświetlić listę numerów IMEI urządzeń, aby oznaczyć je jako firmowe po zarejestrowaniu ich w usłudze Intune:

![Ilustracja przedstawiająca klasyczną listę numerów IMEI](./media/12-classic-corp-imei.png)

W konsoli platformy Azure musisz przekazać te same numery IMEI na listę identyfikatorów urządzeń firmowych za pomocą pliku zawierającego wartości rozdzielane przecinkami (CSV). Nowy portal nie będzie obsługiwał ręcznego wprowadzania numerów IMEI:

![Ilustracja przedstawiająca listę numerów IMEI na platformie Azure](./media/13-azure-corp-imei.png)

Usługa Intune w witrynie Azure Portal jest gotowa na przyszłe potrzeby związane z obsługą innych typów identyfikatorów oprócz IMEI, ale obecnie umożliwia wstępne wyświetlanie listy jedynie numerów IMEI.

## <a name="where-did-corporate-device-enrollment-profiles-go"></a>Dokąd zostały przeniesione profile rejestracji urządzeń firmowych?
Aby zarejestrować urządzenia iOS za pomocą programu Device Enrollment Program firmy Apple lub narzędzia Apple Configurator, musisz dostarczyć profil rejestracji urządzenia firmowego, który zostanie przypisany do urządzenia. W konsoli klasycznej funkcje tworzenia tych profilów i zarządzania nimi znajdują się na jednej liście:

![Ilustracja przedstawiająca klasyczne profile rejestracji urządzeń](./media/14-classic-corp-profiles.png)

Na tej liście znajdują się profile przeznaczone do użytku z programem Device Enrollment Program firmy Apple (**DEP wł.**) oraz profil przeznaczony wyłącznie do użytku z narzędziem Apple Configurator (**DEP wył.**).

Aby ułatwić rozróżnienie tych dwóch typów profilów i ograniczyć liczbę potencjalnie niedopasowanych przypisań (profilu w programie DEP do urządzeń w narzędziu Configurator i na odwrót), podzieliliśmy funkcje tworzenia profilów programu rejestracji (obsługujących program Device Enrollment Program firmy Apple i Apple School Manager) i profilów narzędzia Apple Configurator oraz zarządzania nimi:

**Profile programu DEP**
![Ilustracja przedstawiająca profile programu DEP na platformie Azure](./media/15-azure-dep-profiles.png)

**Profile narzędzia Apple Configurator**
![Ilustracja przedstawiająca profile narzędzia Apple Configurator na platformie Azure](./media/16-azure-ac-profiles.png)
