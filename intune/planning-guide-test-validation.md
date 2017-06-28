---
title: "Testowanie i sprawdzanie poprawności usługi Intune"
description: "Ten artykuł zawiera wszystkie szczegółowe informacje, które należy wziąć pod uwagę podczas testowania i sprawdzania poprawności opartego tylko na chmurze rozwiązania Intune w środowisku."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4f82ee0c-4bd6-4623-9b10-9249d316ccf5
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 4ea2974c4724564cd8f9972fdb238b06d1b100e6
ms.contentlocale: pl-pl
ms.lasthandoff: 06/08/2017


---

# <a name="intune-testing-and-validation"></a>Testowanie i sprawdzanie poprawności usługi Intune

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Faza testowania powinna być przeprowadzana podczas fazy implementacji i po niej. Wymagane będzie posiadanie testowych kont, grup i urządzeń w celu przeprowadzenia testowania wszystkich wymaganych i zidentyfikowanych wcześniej scenariuszy dotyczących pracownika IT (administrator) i końcowego użytkownika (przypadek użycia).

Zaleca się ujęcie w fazie testowania pracowników wsparcia/pomocy technicznej w celu utworzenia dokumentacji z pomocą techniczną i ułatwienia pracownikom wsparcia/pomocy technicznej obsługi produktu. Jeśli składnik lub scenariusz nie działa w oparciu o przypadki użycia, upewnij się, że udokumentowano niezbędne zmiany i podano przyczynę dokonanych zmian.

## <a name="before-you-begin"></a>Przed rozpoczęciem

Zaleca się udokumentowanie następujących elementów:

-   **Kryteria testowania:** identyfikują testy porównawcze, względem których będą przeprowadzane pomiary.

-   **Składniki projektu:** muszą istnieć w co najmniej jednym kryterium testowania.

Jeśli składnika projektu nie ma w żadnym kryterium testowania zgodnym z wymaganiem lub scenariuszem, zdecyduj, czy składnik projektu jest wymagany. Dodatkowo upewnij się, że masz następujące elementy:

-   **Konta:** konta używane do testowania powinny być kontami testowymi z licencjami pakietu EMS i usługi Office 365, aby można było przetestować wszystkie scenariusze przypadków użycia.

-   **Urządzenia:** urządzenia używane na tym etapie powinny być urządzeniami testowymi, które potencjalnie mogą zostać wyczyszczone lub przywrócone do domyślnych ustawień fabrycznych.

-   **Składniki integracji:** wszystkie składniki integracji (łącznik certyfikatów, łącznik Service To Service Connector usługi Intune dla hostowanego programu Exchange i lokalny łącznik Intune Exchange Connector) powinny być zainstalowane i skonfigurowane, jeśli jest to konieczne.

Aby przezwyciężyć nieprzewidziane trudności, może być wymagane wprowadzenie zmian w projekcie. Dodatkowo wszystkie zmiany projektu powinny być w pełni udokumentowane wraz z podaniem przyczyn wprowadzenia poszczególnych zmian. Oto przykład zmiany:

-   Może się okazać, że nie są spełnione wymagania dotyczące usługi rejestracji urządzeń sieciowych (NDES), a jednocześnie istnieje możliwość takiego skonfigurowania profilów sieci VPN i Wi-Fi za pomocą głównego urzędu certyfikacji, że spełniają one takie same wymagania bez konieczności implementowania usługi NDES.

Podczas testowania i sprawdzania poprawności mogą pojawić się wyzwania lub problemy wymagające zastosowania pomocy technicznej lub wyspecjalizowanych procedur rozwiązywania problemów. Zaleca się skorzystanie z pomocy za pośrednictwem kanałów pomocy technicznej firmy Microsoft.

-   [Dowiedz się, jak uzyskać pomoc techniczną dla usługi Intune](/intune-classic/troubleshoot/how-to-get-support-for-microsoft-intune)

-   [Ogólne porady dotyczące rozwiązywania problemów w usłudze Microsoft Intune](/intune-classic/troubleshoot/general-troubleshooting-tips-for-microsoft-intune)

-   [Dowiedz się, jak uzyskać pomoc techniczną dotyczącą usługi Microsoft Intune](/intune-classic/troubleshoot/how-to-get-support-for-microsoft-intune)

-   [Kontakt z telefoniczną asystowaną pomocą techniczną dla usługi Microsoft Intune](/intune-classic/troubleshoot/contact-assisted-phone-support-for-microsoft-intune)

## <a name="functional-validation-testing"></a>Testowanie poprawności funkcjonalnej

Sprawdzanie poprawności funkcjonalnej polega na testowaniu poszczególnych składników i konfiguracji w celu ustalenia, czy działają one poprawnie. Przykładowe testowanie poprawności opisano w poniższej tabeli.

![Sekcja 9 tabela 1](./media/section-9-image-1-table.PNG)

## <a name="use-case-validation-testing"></a>Testowanie poprawności przypadku użycia

Testowanie poprawności przypadku użycia powinno być przeprowadzane w celu potwierdzenia, że scenariusze są kompletne i funkcjonalne. Istnieją dwa typy scenariuszy przypadków użycia: administratora IT i użytkownika końcowego.

### <a name="it-admin"></a>Administrator IT

Testowanie poprawności typu administratora IT powinno być przeprowadzane w celu sprawdzenia poprawności funkcjonowania akcji administracyjnej wykonywanej względem urządzenia lub użytkownika. Poniżej znajduje się przykład scenariusza pełnego sprawdzania poprawności typu administratora IT.

![Sekcja 9 tabela 2](./media/section-9-image-2-table.PNG)

### <a name="end-user"></a>Użytkownik końcowy

Testowanie poprawności typu użytkownika końcowego powinno być przeprowadzane w celu potwierdzenia, że środowisko użytkownika końcowego jest zgodne z oczekiwaniami i jest prawidłowo prezentowane w całej komunikacji użytkownika. Sprawdzenie poprawności środowiska użytkownika końcowego jest ważne, ponieważ nieprzeprowadzenie tego sprawdzania może prowadzić do obniżenia współczynnika wdrażania i zwiększenia liczby zgłoszeń do działu pomocy technicznej.

![Sekcja 9 tabela 3](./media/section-9-image-3-table.PNG)

## <a name="next-steps"></a>Następne kroki

Po przetestowaniu i sprawdzeniu poprawności scenariuszy przypadków funkcjonalnych i użytkownika usługi Intune możesz rozpocząć wdrożenie produkcyjne usługi Intune. Aby uzyskać więcej informacji, zobacz artykuł [Additional resources](planning-guide-resources.md) (Dodatkowe zasoby).

