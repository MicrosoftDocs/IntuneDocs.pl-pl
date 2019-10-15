---
title: Omówienie cyklu życia rozwiązania MDM w usłudze Microsoft Intune
description: Dowiedz się, jak usługa Intune ułatwia zarządzanie urządzeniami w całym ich cyklu życia — od rejestracji poprzez konfigurację aż po ewentualne wycofanie.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/04/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: 414476389a36cdfafd9169d449ea11adf6e68efd
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71726300"
---
# <a name="overview-of-the-microsoft-intune-mobile-device-management-mdm-lifecycle"></a>Omówienie cyklu życia zarządzania urządzeniami przenośnymi (MDM) w usłudze Microsoft Intune

[!INCLUDE [both-portals](../../intune-classic/includes/note-for-both-portals.md)]

Wszystkie urządzenia, którymi zarządzasz, mają *cykl życia*. Usługa Intune pomaga zarządzać tym cyklem życia od rejestracji przez konfigurację i ochronę aż po wycofanie urządzenia, gdy nie jest już potrzebne.

![Cykl życia urządzenia](./media/device-lifecycle/device-lifecycle.png "Cykl życia urządzenia usługi Intune")

## <a name="enroll"></a>Zarejestruj
Współczesne strategie zarządzania urządzeniami przenośnymi muszą uwzględniać różne telefony, tablety i komputery (z systemami iOS, Android, Windows i Mac OS X). Aby móc zarządzać urządzeniem, co często zdarza się w przypadku urządzeń będących własnością firmy, pierwszym krokiem jest [skonfigurowanie rejestracji urządzenia](../enrollment/device-enrollment.md). Komputerami z systemem Windows można też zarządzać przez zarejestrowanie ich w usłudze Intune (zarządzanie urządzeniami przenośnymi, MDM) lub [zainstalowanie oprogramowania klienckiego usługi Intune](../manage-windows-pcs-with-microsoft-intune.md).

## <a name="configure"></a>Konfiguracja
Zarejestrowanie urządzeń jest tylko pierwszym krokiem. Aby móc korzystać z oferty usługi Intune i zapewnić, że urządzenia są bezpieczne i zgodne ze standardami firmy, można wybierać z szerokiej gamy zasad. Pozwalają one na skonfigurowanie niemal każdego aspektu działania zarządzanych urządzeń. Dotyczy to na przykład tego, czy użytkownicy powinni mieć hasła na urządzeniach, na których znajdują się dane firmowe. Można tego wymagać. Czy masz firmową sieć Wi-Fi? Możesz ją skonfigurować automatycznie. Poniżej przedstawiono typy dostępnych opcji konfiguracji:

- [**Konfiguracja urządzeń**](../configuration/device-profiles.md). Zasady te pozwalają skonfigurować funkcje i możliwości urządzeń, którymi zarządzasz. Można na przykład wymagać używania hasła na telefonach z systemem Windows Phone lub uniemożliwić korzystanie z aparatu na urządzeniach iPhone.
- [**Dostęp do zasobów firmy**](../configuration/device-profiles.md). Jeśli umożliwisz użytkownikom dostęp do ich pracy na ich osobistych urządzeniach, może stać się to źródłem trudności. Na przykład jak zapewnić, aby wszystkie urządzenia, które wymagają dostępu do firmowej poczty e-mail, były skonfigurowane prawidłowo? Jak zapewnić użytkownikom dostęp do sieci firmowej za pomocą połączenia sieci VPN bez znajomości złożonych ustawień? Usługa Intune może pomóc zmniejszyć to obciążenie poprzez automatyczne konfigurowanie urządzeń, którymi zarządzasz, w sposób umożliwiający im dostęp do wspólnych zasobów firmy.
- [**Zasady zarządzania komputerem z systemem Windows (przy użyciu oprogramowania klienckiego usługi Intune)** ](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md). Rejestrowanie komputerów z systemem Windows za pomocą usługi Intune daje najwięcej możliwości zarządzania urządzeniami, jednak usługa Intune w dalszym ciągu obsługuje zarządzanie komputerami z systemem Windows przy użyciu oprogramowania klienckiego usługi Intune. Jeśli potrzebujesz informacji na temat niektórych zadań, które można wykonywać z użyciem komputerów, zacznij tutaj.

## <a name="protect"></a>Ochrona
We współczesnym świecie IT ochrona urządzeń przed nieautoryzowanym dostępem jest jednym z najważniejszych zadań, jakie wykonujesz. Usługa Intune — obok elementów w kroku **Konfiguracja** cyklu życia urządzenia — zapewnia dodatkowe możliwości ochrony zarządzanych urządzeń przed nieautoryzowanym dostępem lub złośliwymi atakami:
- [**Uwierzytelnianie wieloskładnikowe**](../enrollment/multi-factor-authentication.md). Dodanie dodatkowej warstwy uwierzytelniania do logowania użytkowników może sprawić, że urządzenia będą jeszcze bardziej bezpieczne. Wiele urządzeń obsługuje uwierzytelnianie wieloskładnikowe, które wymaga drugiego poziomu uwierzytelniania, takiego jak rozmowa telefoniczna lub wiadomości SMS, zanim użytkownicy będą mogli uzyskać dostęp.
- [**Ustawienia funkcji Windows Hello dla firm**](../protect/windows-hello.md). Funkcja Windows Hello dla firm stanowi alternatywną metodę logowania jednokrotnego pozwalającą użytkownikom na korzystanie z *gestu* — np. użycia odcisku palca lub funkcji Windows Hello — w celu logowania się bez hasła.
- [**Zasady ochrony komputerów z systemem Windows (przy użyciu oprogramowania klienckiego usługi Intune)** ](../policies-to-protect-windows-pcs-in-microsoft-intune.md). W przypadku zarządzania komputerami z systemem Windows przy użyciu oprogramowania klienckiego usługi Intune dostępne są zasady umożliwiające kontrolowanie ustawień programu Endpoint Protection, kontrolowanie aktualizacji oprogramowania i zapory systemu Windows na komputerach, którymi zarządzasz.

## <a name="retire"></a>Wycofaj
Gdy dojdzie do utraty lub kradzieży urządzenia, zajdzie potrzeba jego wymiany lub użytkownik przejdzie na inne stanowisko, zazwyczaj jest to czas na [wycofanie lub wyczyszczenie](../remote-actions/device-management.md) urządzenia. Istnieją różne sposoby, które umożliwiają realizację tego zadania — w tym zresetowanie urządzenia, usunięcie go z zarządzania i wyczyszczenie danych firmowych na nim.

## <a name="next-steps"></a>Następne kroki

- Dowiedz się więcej na temat [zarządzania urządzeniami w usłudze Microsoft Intune](../remote-actions/device-management.md)