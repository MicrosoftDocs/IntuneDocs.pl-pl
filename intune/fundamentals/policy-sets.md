---
title: Zestawy zasad
titleSuffix: Microsoft Intune
description: Zestawy zasad umożliwiają grupowanie kolekcji obiektów zarządzania w usłudze Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: craigma
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 48bfe727615f5165fc70ed2e08f98f01203dc895
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514833"
---
# <a name="use-policy-sets-to-group-collections-of-management-objects"></a>Zestawy zasad umożliwiają grupowanie kolekcji obiektów zarządzania

Zestawy zasad umożliwiają tworzenie pakietu odwołań do już istniejących jednostek zarządzania, które muszą być identyfikowane, kierowane i monitorowane jako pojedyncza jednostka koncepcyjna. Zestaw zasad to możliwa do przypisania kolekcja aplikacji, zasad i innych utworzonych obiektów zarządzania. Dzięki utworzeniu zestawu zasad możliwe jest wybranie wielu różnych obiektów jednocześnie i przypisanie ich z jednego miejsca. Jeśli w organizacji zajdą jakieś zmiany, będzie można ponownie przejrzeć zestaw zasad w celu dodania lub usunięcia obiektów i przypisań. Zestawu zasad można używać do kojarzenia i przypisywania istniejących obiektów, takich jak aplikacje, zasady i sieci VPN, w postaci pojedynczego pakietu. 

> [!IMPORTANT]
> Aby uzyskać listę znanych problemów związanych z zestawami zasad, zobacz [Znane problemy dotyczące zestawów zasad](~/fundamentals/policy-sets.md#policy-sets-known-issues).

Zestawy zasad nie zastępują istniejących koncepcji ani obiektów. Można nadal przypisywać poszczególne obiekty, a także odwoływać się do nich w ramach zestawu zasad. W konsekwencji wszystkie zmiany tych pojedynczych obiektów zostaną odzwierciedlone w zestawie zasad. 

Zestawów zasad można używać do wykonywania następujących czynności:

- Grupowanie obiektów, które muszą być przypisane razem
- Przypisywanie minimalnych wymagań dotyczących konfiguracji organizacji na wszystkich urządzeniach zarządzanych
- Przypisywanie często używanych lub odpowiednich aplikacji do wszystkich użytkowników

W zestawie zasad można uwzględnić następujące obiekty zarządzania:
- Aplikacje
- Zasady konfigurowania aplikacji
- Zasady ochrony aplikacji
- Profile konfiguracji urządzeń
- Zasady zgodności urządzeń
- Ograniczenia dotyczące typów urządzeń
- Profile wdrażania rozwiązania Windows Autopilot
- Strona ze stanem rejestracji

Kiedy tworzysz zestaw zasad, tworzysz pojedynczą jednostkę przypisania i zarządzasz skojarzeniami między różnymi obiektami. Zestaw zasad będzie więc odwołaniem do obiektów znajdujących się poza ta jednostką. Wszelkie zmiany w uwzględnionych obiektach wpłyną również na zestaw zasad. Po utworzeniu zestawu zasad możesz wielokrotnie wyświetlać i edytować jego obiekty i przydziały. 

> [!NOTE]
> Zestawy zasad obsługują ustawienia systemów Windows, Android, macOS i iOS/iPadOS oraz mogą być przypisywane między różnymi platformami.

## <a name="how-to-create-a-policy-set"></a>Jak utworzyć zestaw zasad

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz kolejno pozycje **Urządzenia** > **Zestawy zasad** > **Zestawy zasad** > **Utwórz**.
3. Na stronie **Podstawowe** dodaj następujące wartości:
    - **Nazwa zestawu zasad**  — podaj nazwę tego zestawu zasad.
    - **Opis** — opcjonalnie wprowadź opis zestawu zasad.
   <p>
   <img alt="Create policy set - Basics" src="~/fundamentals/media/policy-sets/policy-sets-01.png">

4. Kliknij przycisk **Dalej: Zarządzanie aplikacjami**.<br>
   Na stronie **Zarządzanie aplikacjami** możesz opcjonalnie dodać do zestawu zasad [aplikacje](~/apps/apps-add.md), [zasady konfiguracji aplikacji](~/apps/app-configuration-policies-overview.md) i [zasady ochrony aplikacji](~/apps/app-protection-policy.md). Aby uzyskać więcej informacji o zarządzaniu aplikacjami, zobacz [Co to jest zarządzanie aplikacjami w usłudze Microsoft Intune?](~/apps/app-management.md) 
5. Kliknij przycisk **Dalej: Zarządzanie urządzeniami**.<br>
   Strona **Zarządzanie urządzeniami** umożliwia dodawanie do zestawu zasad obiektów zarządzania urządzeniami, takich jak [profile konfiguracji urządzeń](~/configuration/device-profiles.md) i [zasady zgodności urządzeń](~/protect/device-compliance-get-started.md). Pamiętaj, aby uwzględnić wszystkie skojarzone obiekty, takie jak inne zasady, certyfikaty i profile punktów odniesienia zabezpieczeń.
6. Kliknij przycisk **Dalej: Rejestrowanie urządzenia**.<br>
   Strona **Rejestrowanie urządzenia** umożliwia dodawanie do zestawu zasad obiektów rejestracji urządzeń, takich jak [ograniczenia typu urządzeń](~/enrollment/enrollment-restrictions-set.md), [profile wdrażania rozwiązania Windows Autopilot](~/enrollment/enrollment-autopilot.md) i [profile stron stanu rejestracji](~/enrollment/windows-enrollment-status.md).
7. Kliknij przycisk **Dalej: Przypisania**.<br>
   Strona **Przypisania** umożliwia przypisanie zestawu zasad do użytkowników i urządzeń. Ważne jest, aby pamiętać, że zestaw zasad można przypisać do urządzenia bez względu na to, czy jest ono zarządzane przez usługę Intune.
8. Kliknij przycisk **Dalej: Przeglądanie + tworzenie**, aby przejrzeć wartości wprowadzone dla profilu.
9. Gdy skończysz, kliknij pozycję **Utwórz**, aby utworzyć zestaw zasad w usłudze Intune. 

## <a name="policy-sets-known-issues"></a>Znane problemy dotyczące zestawów zasad

Zestawy zasad wprowadzone w wersji 1910 mają następujące znane problemy.

- Jeśli podczas tworzenia zestawu zasad administrator z zakresem próbuje utworzyć zestaw zasad bez zaznaczenia jakichkolwiek tagów zakresu, to na stronie **Przeglądanie + tworzenie** sprawdzanie poprawności zakończy się niepowodzeniem, a na pasku stanu zostanie wyświetlony komunikat o błędzie. Administrator musi przełączyć się na inną stronę w procesie, a następnie wrócić do strony **Przeglądanie + tworzenie**. Spowoduje to włączenie opcji **Utwórz**.  
 
- Następujące typy aplikacji są obecnie obsługiwane przez zestawy zasad:
    - Aplikacja ze sklepu dla systemu iOS/iPadOS
    - Aplikacja biznesowa dla systemu iOS/iPadOS
    - Zarządzana aplikacja biznesowa dla systemu iOS/iPadOS
    - Aplikacja ze sklepu dla systemu Android
    - Aplikacja biznesowa dla systemu Android
    - Zarządzana aplikacja biznesowa dla systemu Android
    - Pakiet Office 365 ProPlus (Windows 10)
    - Link internetowy
    - Aplikacja wbudowana dla systemu iOS/iPadOS
    - Wbudowana aplikacja systemu Android

- Ustawianie przypisania zestawu zasad **Wszyscy użytkownicy** do **profilu rozwiązania Autopilot** nie jest obsługiwane.

- W przypadku zestawów zasad wykryto następujące problemy dotyczące ograniczeń rejestracji i strony ze stanem rejestracji:
    - Ograniczenia i strona ze stanem rejestracji nie obsługują przypisań grup wirtualnych.
    - Ograniczenia i strona ze stanem rejestracji nie obsługują ściśle przypisań grup wykluczeń. 
    - Ograniczenia i strona ze stanem rejestracji korzystają z mechanizmu rozwiązywania konfliktów opartego na priorytecie. Ograniczenia i strona ze stanem rejestracji mogą nie zostać zastosowane do tych samych użytkowników co pozostałe ładunki zestawu zasad, jeśli ograniczenia i strona ze stanem rejestracji są również objęte ograniczeniami o wyższym priorytecie.
    - Domyślne ograniczenia i strona ze stanem rejestracji nie mogą zostać dodane do zestawu zasad.

- Zestawy zasad są obsługiwane przez następujące typy zasad MAM: 
    - Ochrona aplikacji zarządzanych za pomocą funkcji MAM WIP (Windows) MDM 
    - Ochrona aplikacji zarządzanych za pomocą funkcji MAM w systemie iOS/iPadOS
    - Ochrona aplikacji zarządzanych za pomocą funkcji MAM w systemie Android
    - Konfiguracja aplikacji zarządzanych za pomocą funkcji MAM w systemie iOS/iPadOS
    - Konfiguracja aplikacji zarządzanych za pomocą funkcji MAM w systemie Android

- Zestawy zasad nie są obsługiwane przez następujące typy zasad MAM: 
    - Ochrona aplikacji zarządzanych za pomocą funkcji MAM WIP (Windows)

- Funkcja MAM przetwarza przypisania zestawu zasad jako bezpośrednie przypisania dla następujących typów zasad:
    - Ochrona aplikacji zarządzanych za pomocą funkcji MAM w systemie iOS/iPadOS
    - Ochrona aplikacji zarządzanych za pomocą funkcji MAM w systemie Android
    - Konfiguracja aplikacji zarządzanych za pomocą funkcji MAM w systemie iOS/iPadOS
    - Konfiguracja aplikacji zarządzanych za pomocą funkcji MAM w systemie Android

    Jeśli zasady zostaną dodane do zestawu zasad wdrożonego w grupie, ta grupa będzie wyświetlana jako bezpośrednio przypisana w obciążeniu, a nie jako „przypisana za pomocą zestawu zasad”. W związku z tym funkcja MAM nie przetwarza usunięć przypisań grup pochodzących z zestawów zasad.

- Funkcja MAM nie obsługuje wdrażania w grupach wirtualnych **Wszyscy użytkownicy** i **Wszystkie urządzenia** dla jakichkolwiek typów zasad.

## <a name="next-steps"></a>Następne kroki

- [Rejestrowanie urządzeń w usłudze Microsoft Intune](~/enrollment/index.yml).