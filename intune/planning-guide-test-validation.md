---
title: Testowanie i sprawdzanie poprawności usługi Intune
titlesuffix: Microsoft Intune
description: Jak testować i weryfikować oparte tylko na chmurze rozwiązanie usługi Intune w danym środowisku.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 10/31/2017
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4f82ee0c-4bd6-4623-9b10-9249d316ccf5
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4974dc3e86b26434cb633bd58e524d290573ecd0
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57237558"
---
# <a name="intune-testing-and-validation"></a>Testowanie i sprawdzanie poprawności usługi Intune

Podczas testowania implementacji usługi Microsoft Intune uwzględnij weryfikację funkcjonalną i weryfikację przypadku użycia. Sprawdzanie poprawności funkcjonalnej polega na testowaniu poszczególnych składników i konfiguracji w celu ustalenia, czy działają one poprawnie. Weryfikacja przypadku użycia polega na sprawdzeniu, czy scenariusze obejmujące serię zadań działają zgodnie z oczekiwaniami. 

Zalecamy uwzględnienie w fazie testowania pracowników wsparcia/pomocy technicznej w celu utworzenia dokumentacji z pomocą techniczną i ułatwienia pracownikom uzyskiwania wsparcia/pomocy technicznej dotyczącej obsługi produktu. Jeśli składnik lub scenariusz nie działa w oparciu o przypadki użycia, upewnij się, że udokumentowano niezbędne zmiany i podano przyczynę dokonanych zmian.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Zalecamy udokumentowanie następujących informacji:

-   **Kryteria testowania:** identyfikują testy porównawcze, względem których będą przeprowadzane pomiary.

-   **Składniki projektu:** muszą istnieć w co najmniej jednym kryterium testowania.

Jeśli składnika projektu nie ma w żadnym kryterium testowania zgodnym z wymaganiem lub scenariuszem, zdecyduj, czy składnik projektu jest wymagany. Dodatkowo upewnij się, że masz następujące elementy:

-   **Konta:** konta testowe z licencjami pakietu EMS i usługi Office 365, aby można było przetestować wszystkie scenariusze przypadków użycia.

-   **Urządzenia:** urządzenia testowe, które mogą być czyszczone lub na których możliwe jest przywrócenie ustawień fabrycznych.

-   **Składniki integracji:** wszystkie składniki integracji (łącznik certyfikatów, łącznik Service To Service Connector usługi Intune dla hostowanego programu Exchange i łącznik usługi Intune dla lokalnego programu Exchange) powinny być zainstalowane i skonfigurowane zgodnie z potrzebami.

Aby przezwyciężyć nieprzewidziane trudności, konieczne może być wprowadzenie zmian w projekcie. Dodatkowo wszystkie zmiany projektu powinny być w pełni udokumentowane wraz z podaniem przyczyn wprowadzenia poszczególnych zmian. Oto przykład zmiany:

<blockquote>Okazuje się, że nie są spełnione wymagania dotyczące usługi rejestracji urządzeń sieciowych (NDES), a jednocześnie istnieje możliwość takiego skonfigurowania profilów sieci VPN i Wi-Fi za pomocą głównego urzędu certyfikacji, że spełnią one takie same wymagania bez konieczności implementowania usługi NDES.</blockquote>

Podczas testowania i walidacji mogą pojawić się wyzwania lub problemy wymagające zastosowania pomocy technicznej lub wyspecjalizowanych procedur rozwiązywania problemów. Zalecamy korzystanie z pomocy za pośrednictwem kanałów pomocy technicznej firmy Microsoft.

-   [Dowiedz się, jak uzyskać pomoc techniczną dla usługi Intune](get-support.md)

-   [Kontakt z telefoniczną asystowaną pomocą techniczną dla usługi Microsoft Intune](get-support.md)

## <a name="functional-validation-testing"></a>Testowanie poprawności funkcjonalnej

Sprawdzanie poprawności funkcjonalnej polega na testowaniu poszczególnych składników i konfiguracji w celu ustalenia, czy działają one poprawnie. Przykładowe testowanie poprawności opisano w poniższej tabeli.

![Sekcja 9 tabela 1](./media/section-9-image-1-table.PNG)

## <a name="use-case-validation-testing"></a>Testowanie poprawności przypadku użycia

Należy przeprowadzić testy poprawności przypadku użycia w celu potwierdzenia, że scenariusze są kompletne i funkcjonalne. Istnieją dwa typy scenariuszy przypadków użycia: dotyczą one administratora IT i użytkownika końcowego.

### <a name="it-admin"></a>Administrator IT

Należy przeprowadzić testy poprawności administratora IT w celu zweryfikowania funkcjonowania działań administracyjnych wykonywanych względem urządzenia lub użytkownika. Poniżej znajduje się przykład scenariusza pełnej walidacji typu administratora IT.

![Sekcja 9 tabela 2](./media/section-9-image-2-table.PNG)

### <a name="end-user"></a>Użytkownik końcowy

Należy przeprowadzić testy poprawności użytkownika końcowego w celu potwierdzenia, że środowisko pracy użytkownika końcowego jest zgodne z oczekiwaniami i jest prawidłowo prezentowane w całej komunikacji użytkownika. Ważne jest, aby sprawdzić, czy środowisko pracy użytkownika końcowego jest poprawne. Jeśli walidacja jest niemożliwa, może to prowadzić do obniżenia współczynnika wdrażania i zwiększenia liczby zgłoszeń do działu pomocy technicznej.

![Sekcja 9 tabela 3](./media/section-9-image-3-table.PNG)

## <a name="next-steps"></a>Następne kroki

Po przetestowaniu i zweryfikowaniu scenariuszy przypadków funkcjonalnych i użytkownika usługi Intune możesz rozpocząć [wdrożenie produkcyjne usługi Intune](planning-guide-rollout-plan.md).

Zobacz [dodatkowe zasoby](planning-guide-resources.md), które zawierają więcej szablonów planowania i informacji na temat planowania.
