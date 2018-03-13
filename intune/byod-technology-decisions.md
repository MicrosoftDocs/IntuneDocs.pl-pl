---
title: "Podejmowanie decyzji technologicznych dotyczących modelu „Przynieś własne urządzenie” (BYOD, Bring Your Own Device) za pomocą pakietu EMS"
description: "Podejmowanie kluczowych decyzji technologicznych dotyczących włączania modelu BYOD i ochrony danych firmowych za pomocą pakietu Microsoft Enterprise Mobility + Security."
keywords: 
author: dougeby
ms.author: pfetty
manager: angrobe
ms.date: 12/8/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.suite: ems
ms.openlocfilehash: 3ee642f5c2e30023043cec4bf5286999d4397e2d
ms.sourcegitcommit: 9cf05d3cb8099e4a238dae9b561920801ad5cdc6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2018
---
# <a name="technology-decisions-for-enabling-byod-with-microsoft-enterprise-mobility--security-ems"></a>Podejmowanie kluczowych decyzji technologicznych dotyczących włączania modelu BYOD za pomocą pakietu Microsoft Enterprise Mobility + Security

Podczas opracowywania strategii umożliwiającej pracownikom pracę zdalną z ich własnych urządzeń (BYOD), należy podjąć kluczowe decyzje w scenariuszach dotyczących włączania modelu BYOD i sposobu ochrony danych firmowych. Na szczęście pakiet EMS oferuje wszystkie możliwości wymagane w ramach zaawansowanego zestawu rozwiązań.  

W tym temacie zostanie omówiony prosty przypadek użycia dotyczący włączania dostępu w ramach modelu BYOD do firmowej poczty e-mail. Skupimy się na określeniu, czy konieczne jest zarządzanie całym urządzeniem, czy tylko aplikacjami — oba te wybory są całkowicie prawidłowe.

## <a name="assumptions"></a>Założenia
* Masz podstawową wiedzę na temat usługi Azure Active Directory i Microsoft Intune
* Twoje konta e-mail są hostowane w usłudze Exchange Online

## <a name="common-reasons-to-manage-the-device-mdm"></a>Typowe przyczyny zarządzania urządzeniem (zarządzanie urządzeniami przenośnymi)
Można łatwo zachęcić użytkowników do rejestrowania swoich urządzeń w systemie zarządzania urządzeniami, wdrażając zasady [dostępu warunkowego](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) w usłudze Exchange Online. Poniżej przedstawiono potencjalne przyczyny zarządzania urządzeniami osobistymi:

**Sieć Wi-Fi lub VPN** — jeśli użytkownicy potrzebują do pracy profilu łączności firmowej, może to zostać bezproblemowo skonfigurowane.

**Aplikacje** — jeśli użytkownicy potrzebują zestawu aplikacji, który ma zostać wypchnięty na ich urządzenia, może to zostać bezproblemowo zapewnione. Obejmuje to aplikacje, które mogą być wymagane ze względów bezpieczeństwa, takie jak aplikacja Mobile Threat Defense.

**Zgodność** — niektóre organizacje muszą zapewnić zgodność z przepisami lub innymi zasadami, które wymagają użycia określonych kontrolek zarządzania urządzeniami przenośnymi. Na przykład za pomocą zarządzania urządzeniami przenośnymi ma zostać wykonane szyfrowanie wszystkich danych na urządzeniu lub wygenerowanie raportu dotyczącego wszystkich aplikacji na urządzeniu.

## <a name="common-reasons-to-only-manage-the-apps-mam"></a>Typowe przyczyny zarządzania tylko aplikacjami (zarządzanie aplikacjami mobilnymi)
Zarządzanie aplikacjami mobilnymi bez zarządzania urządzeniami przenośnymi jest bardzo popularne w organizacjach, w których obsługiwany jest model BYOD. Można zachęcić użytkowników do uzyskiwania dostępu do poczty e-mail z poziomu aplikacji Outlook Mobile, która obsługuje ochronę usługi zarządzanie aplikacjami mobilnymi, wdrażając zasady dostępu warunkowego w usłudze Exchange Online. Poniżej przedstawiono potencjalne przyczyny zarządzania jedynie aplikacjami na urządzeniach osobistych:

**Środowisko użytkownika** — rejestracja w usłudze zarządzania urządzeniami przenośnymi obejmuje wiele monitów ostrzegawczych (wymuszanych przez platformę), co często skutkuje podjęciem przez użytkownika decyzji o tym, aby nie uzyskiwać dostępu do swojej poczty e-mail na urządzeniu osobistym. W usłudze zarządzania aplikacjami mobilnymi użytkownikom wyświetlanych jest znacznie mniej monitów — jest to tylko jedno okienko wyskakujące z informacją o tym, że ma miejsce ochrona usługi zarządzania aplikacjami mobilnymi.

**Zgodność** — niektóre organizacje muszą zapewnić zgodność z zasadami, które na urządzeniach osobistych wymagają mniejszych możliwości zarządzania. Na przykład za pomocą usługi zarządzania aplikacjami mobilnymi możliwe jest jedynie usunięcie danych firmowych z aplikacji, w przeciwieństwie do usługi zarządzania urządzeniami przenośnymi, w której można usunąć wszystkie dane z urządzenia.

![Obraz przedstawiający zarządzanie urządzeniami i aplikacjami na urządzeniach przenośnych](./media/byod-app-device-mgmt.png)

Dowiedz się więcej o [cyklach życia zarządzania urządzeniami i aplikacjami](introduction-device-app-lifecycles.md).

## <a name="mdm-vs-mam-capability-comparison"></a>Porównanie możliwości usługi zarządzania urządzeniami przenośnymi i usługi zarządzania aplikacjami mobilnymi
Jak wcześniej wspomniano, dostęp warunkowy może zachęcić użytkownika do zarejestrowania swojego urządzenia lub użycia aplikacji zarządzanej, takiej jak Outlook Mobile. W obu przypadkach może mieć zastosowanie wiele innych warunków, w tym:

* Użytkownik, który próbuje uzyskać dostęp
* Czy lokalizacja jest zaufana, czy nie
*   Poziom ryzyka dotyczący logowania
* Platforma urządzeń

Wiele organizacji ma często określone zagrożenia, które ich dotyczą.  W poniższej tabeli wymieniono typowe zagadnienia i odpowiedzi na nie w przypadku usługi zarządzania urządzeniami przenośnymi i usługi zarządzania aplikacjami mobilnymi.

| Zagadnienie   |   ZARZĄDZANIE URZĄDZENIAMI PRZENOŚNYMI  |   ZARZĄDZANIE URZĄDZENIAMI PRZENOŚNYMI  |
|------------|--------|--------|
|Nieautoryzowany dostęp do danych | Wymaganie członkostwa w grupie | Wymaganie członkostwa w grupie |
|Nieautoryzowany dostęp do danych | Wymaganie rejestracji urządzenia | Wymaganie chronionej aplikacji |
|Nieautoryzowany dostęp do danych | Wymaganie określonej lokalizacji | Wymaganie określonej lokalizacji |
| | | |
|Zagrożone konto użytkownika| Wymaganie uwierzytelniania wieloskładnikowego | Wymaganie uwierzytelniania wieloskładnikowego|
|Zagrożone konto użytkownika | Blokowanie użytkowników o wysokim ryzyku | Blokowanie użytkowników o wysokim ryzyku |
|Zagrożone konto użytkownika | Numer PIN urządzenia | Numer PIN aplikacji |
| | | |
| Zagrożone urządzenie lub aplikacji | Wymaganie zgodnego urządzenia | Sprawdzanie zdjęcie zabezpieczeń systemu podczas uruchamiania aplikacji |
| Zagrożone urządzenie lub aplikacja | Szyfrowanie danych urządzenia | Szyfruj dane aplikacji |
| | | |
|Zgubione lub skradzione urządzenie | Usuwanie wszystkich danych urządzenia | Usuwanie wszystkich danych aplikacji|
| | | |
| Przypadkowe udostępnienie danych lub zapisanie w niezabezpieczonych lokalizacjach | Ograniczanie tworzenia kopii zapasowych danych urządzenia | Ograniczanie wycinania, kopiowania i wklejania|
| Przypadkowe udostępnienie danych lub zapisanie w niezabezpieczonych lokalizacjach | Ograniczanie zapisywania jako | Ograniczanie zapisywania jako |
|Przypadkowe udostępnienie danych lub zapisanie w niezabezpieczonych lokalizacjach | Wyłącz drukowanie | n/d|

## <a name="next-steps"></a>Następne kroki
Teraz należy podjąć decyzję o tym, czy model BYOD ma zostać włączony w organizacji, koncentrując swoje działania na zarządzaniu urządzeniami, zarządzaniu aplikacjami lub obu tych czynnościach. Wybór implementacji należy do Ciebie, ale możesz mieć pewność, że funkcje tożsamości i zabezpieczeń dostępne dzięki użyciu usługi Azure AD będą dostępne niezależnie od tego wyboru.

Użyj [Przewodnika planowania](planning-guide.md), aby ustalić szczegóły dotyczące następnego poziomu planowania.
