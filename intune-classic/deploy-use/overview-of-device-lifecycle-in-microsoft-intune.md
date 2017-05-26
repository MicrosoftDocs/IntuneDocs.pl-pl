---
title: "Przegląd cyklu życia rozwiązania do zarządzania urządzeniami przenośnymi | Microsoft Docs"
description: "Dowiedz się, jak usługa Intune ułatwia zarządzanie urządzeniami w całym ich cyklu życia — od rejestracji poprzez konfigurację aż po ewentualne wycofanie."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f6051fa7-133f-4712-86a5-e5f5bc5ab3c7
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b7a066c1387a97d6100be0e6ab22d78222bf2a30
ms.openlocfilehash: 3311ba5081c4b04d72fdeb1f9a558ffc2e1b02fc
ms.lasthandoff: 02/21/2017


---

# <a name="overview-of-the-mobile-device-management-mdm-lifecycle"></a>Przegląd cyklu życia zarządzania urządzeniami przenośnymi

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Wszystkie urządzenia, którymi zarządzasz, mają tak zwany *cykl życia*. Usługa Intune pomaga zarządzać tym cyklem życia od rejestracji przez konfigurację i ochronę aż po wycofanie urządzenia, gdy nie jest już potrzebne:

![Cykl życia urządzenia](./media/device-lifecycle.png "Cykl życia urządzenia usługi Intune")

## <a name="enroll"></a>Zarejestruj
Współczesne strategie zarządzania urządzeniami przenośnymi muszą uwzględniać różne telefony, tablety i komputery (z systemami iOS, Android, Windows i Mac OS X). Aby móc zarządzać urządzeniem, co często zdarza się w przypadku urządzeń będących własnością firmy, pierwszym krokiem jest [skonfigurowanie rejestracji urządzenia](enroll-devices-in-microsoft-intune.md). Komputerami z systemem Windows można też zarządzać przez zarejestrowanie ich w usłudze Intune (zarządzanie urządzeniami przenośnymi, MDM) lub [zainstalowanie oprogramowania klienckiego usługi Intune](manage-windows-pcs-with-microsoft-intune.md).

## <a name="configure"></a>Konfiguracja
Zarejestrowanie urządzeń jest tylko pierwszym krokiem. Aby móc korzystać z oferty usługi Intune i zapewnić, że urządzenia są bezpieczne i zgodne ze standardami firmy, można wybierać z szerokiej gamy zasad. Pozwalają one na skonfigurowanie niemal każdego aspektu działania zarządzanych urządzeń. Dotyczy to na przykład tego, czy użytkownicy powinni mieć hasła na urządzeniach, na których znajdują się dane firmowe. Można tego wymagać. Czy masz firmową sieć Wi-Fi? Możesz ją skonfigurować automatycznie. Poniżej przedstawiono typy dostępnych opcji konfiguracji:

- [**Zasady konfiguracji**](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md). Zasady te pozwalają skonfigurować funkcje i możliwości urządzeń, którymi zarządzasz. Można na przykład wymagać używania hasła na telefonach z systemem Windows Phone lub uniemożliwić korzystanie z aparatu na urządzeniach iPhone.
- [**Zasady dostępu do zasobów firmy**](enable-access-to-company-resources-with-microsoft-intune.md). Jeśli umożliwisz użytkownikom dostęp do ich pracy na ich osobistych urządzeniach, może stać się to źródłem trudności. Na przykład jak zapewnić, aby wszystkie urządzenia, które wymagają dostępu do firmowej poczty e-mail, były skonfigurowane prawidłowo? Jak zapewnić użytkownikom dostęp do sieci firmowej za pomocą połączenia sieci VPN bez znajomości złożonych ustawień? Usługa Intune może pomóc zmniejszyć to obciążenie poprzez automatyczne konfigurowanie urządzeń, którymi zarządzasz, w sposób umożliwiający im dostęp do wspólnych zasobów firmy.
- [**Zasady zarządzania komputerem z systemem Windows (przy użyciu oprogramowania klienckiego usługi Intune)**](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md). Rejestrowanie komputerów z systemem Windows za pomocą usługi Intune daje najwięcej możliwości zarządzania urządzeniami, jednak usługa Intune w dalszym ciągu obsługuje zarządzanie komputerami z systemem Windows przy użyciu oprogramowania klienckiego usługi Intune. Jeśli potrzebujesz informacji na temat niektórych zadań, które można wykonywać z użyciem komputerów, zacznij tutaj.

## <a name="protect"></a>Ochrona
We współczesnym świecie IT ochrona urządzeń przed nieautoryzowanym dostępem jest jednym z najważniejszych zadań, jakie będziesz wykonywać. Usługa Intune — obok elementów w kroku **Konfiguracja** cyklu życia urządzenia — zapewnia dodatkowe możliwości ochrony zarządzanych urządzeń przed nieautoryzowanym dostępem lub złośliwymi atakami:
- [**Uwierzytelnianie wieloskładnikowe**](protect-your-devices-with-microsoft-intune.md). Dodanie dodatkowej warstwy uwierzytelniania do logowania użytkowników może sprawić, że urządzenia będą jeszcze bardziej bezpieczne. Wiele urządzeń obsługuje uwierzytelnianie wieloskładnikowe, które wymaga drugiego poziomu uwierzytelniania, takiego jak rozmowa telefoniczna lub wiadomości SMS, zanim użytkownicy będą mogli uzyskać dostęp.
- [**Ustawienia usługi Microsoft Passport**](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md). Microsoft Passport stanowi alternatywną metodę logowania jednokrotnego pozwalającą użytkownikom na korzystanie z *gestu*, takiego jak odcisk palca, lub z funkcji Windows Hello w celu logowania się bez użycia hasła.
- [**Zasady ochrony komputerów z systemem Windows (przy użyciu oprogramowania klienckiego usługi Intune)**](policies-to-protect-windows-pcs-in-microsoft-intune.md). W przypadku zarządzania komputerami z systemem Windows przy użyciu oprogramowania klienckiego usługi Intune dostępne są zasady umożliwiające kontrolowanie ustawień programu Endpoint Protection, kontrolowanie aktualizacji oprogramowania i zapory systemu Windows na komputerach, którymi zarządzasz.

## <a name="retire"></a>Wycofaj
Gdy dojdzie do utraty lub kradzieży urządzenia, zajdzie potrzeba jego wymiany lub użytkownik przejdzie na inne stanowisko, zazwyczaj jest to czas na [wycofanie lub wyczyszczenie](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) urządzenia. Istnieją różne sposoby, które umożliwiają realizację tego zadania — w tym zresetowanie urządzenia, usunięcie go z zarządzania i wyczyszczenie danych firmowych na nim.
