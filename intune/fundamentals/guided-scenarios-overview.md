---
title: Scenariusze z przewodnikiem — omówienie
titleSuffix: Microsoft Intune
description: Dowiedz się więcej na temat scenariuszy z przewodnikiem usługi Intune dostępnych w portalu zarządzania urządzeniami platformy Microsoft 365.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 460cabead711e6fa4559bcec39e556448cdf2237
ms.sourcegitcommit: 2c8a41ee95a3fde150667a377770e51b621ead65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "73635365"
---
# <a name="intune-guided-scenarios-overview"></a>Scenariusze z przewodnikiem dotyczące usługi Intune — omówienie 

Scenariusz z przewodnikiem przedstawia serię dostosowanych kroków, które należy wykonać w jednym konkretnym przypadku użycia. Typowe scenariusze są opisane na podstawie na roli, jaką w Twojej organizacji odgrywa administrator, użytkownik lub urządzenie. Te role zwykle wymagają starannego zsynchronizowania profilów, ustawień, aplikacji i opcji zabezpieczeń, aby zapewnić jak najlepsze środowisko użytkownika i skuteczne zabezpieczenia.    

Jeśli nie znasz wszystkich kroków i zasobów potrzebnych do wdrożenia konkretnego scenariusza usługi Intune, możesz zacząć od skorzystania ze scenariusza z przewodnikiem. Scenariusz z przewodnikiem automatycznie łączy zasady, aplikacje, przypisania i inne konfiguracje zarządzania. Ponadto scenariusze z przewodnikiem celowo pomijają niektóre nietypowe opcje, które nie dotyczą danego scenariusza. 

Scenariusze z przewodnikiem nie są odrębnym obszarem zarządzania, różniącym się od normalnych przepływów pracy usługi Intune. Te przepływy pracy mają być używane w połączeniu z istniejącymi przepływami pracy usługi Intune w zakresie profilów, aplikacji i zasad. Po zakończeniu pracy ze scenariuszem z przewodnikiem całe dalsze zarządzanie scenariuszem musi odbywać się w istniejących menu zasad, aplikacji i profilów. Scenariusz z przewodnikiem nie zapisuje typu zasobu „scenariusz z przewodnikiem” ani nie śledzi zmian wprowadzanych w zasobach w przyszłości. Każdy zasób utworzony w ramach scenariusza z przewodnikiem pojawi się w odpowiednim obciążeniu. Wszystkie opcje, nawet te pominięte w scenariuszu z przewodnikiem, mogą być edytowane w istniejących menu.  

## <a name="types-of-guided-scenarios"></a>Typy scenariuszy z przewodnikiem 

Dla ułatwienia wszystkie scenariusze z przewodnikiem pomijają skomplikowane funkcje ustawiania zakresu, takie jak tagi zakresu <link>, grupy wykluczenia i przypisania grup wirtualnych <link>. Wszystkie zasoby utworzone w ramach scenariusza z przewodnikiem dziedziczą każdy tag zakresu administratora, który wykonuje scenariusz. Niektóre scenariusze oferują pewien poziom dostosowania w zakresie popularnych ustawień, aby obejmować kilka powiązanych sytuacji. Te scenariusze obsługują przypisanie grup wyłącznie do grup dołączania. W przypadku innych scenariuszy z przewodnikiem cały scenariusz gwarantuje jedno spójne środowisko, wynikające z braku dostosowywania, oraz automatycznie generuje nową grupę, która otrzyma wszystkie przypisania. Po zakończeniu scenariusza z przewodnikiem możesz bezpośrednio zastosować bardziej zaawansowane przypisania, używając istniejących obciążeń zasad, aplikacji i profilów.  

Następujące scenariusze są dostępne z przewodnikiem: 
- Wdrażanie przeglądarki Microsoft Edge dla urządzeń przenośnych 
- Korzystanie z komputera zarządzanego w chmurze
- Bezpieczne korzystanie z pakietu Microsoft Office na urządzeniach przenośnych 

## <a name="guided-scenario-functionality"></a>Funkcje scenariusza z przewodnikiem 

Scenariusze z przewodnikiem oferują określone funkcje. Poniżej wyjaśniono szczegółowo, co można, a czego nie można robić podczas korzystania ze scenariusza z przewodnikiem.

### <a name="launching"></a>Uruchamianie  

Wszystkie scenariusze z przewodnikiem są dostępne w **[portalu Zarządzanie urządzeniami](https://devicemanagement.microsoft.com)**  > **Rozwiązywanie problemów + Pomoc** > **Scenariusze z przewodnikiem**. 

Scenariusz z przewodnikiem rozpoczyna się od wprowadzenia, w którym wyjaśniany jest cel scenariusza i wszelkie wymagania wstępne, które należy spełnić, aby ukończyć konfigurację. W tym momencie sprawdzane są Twoje uprawnienia administratora, aby upewnić się, że masz wszystkie uprawnienia konieczne do ukończenia tego scenariusza.  

Jeśli wszystkie wymagania wstępne są spełnione, w scenariuszu zaproponowane zostaną odpowiednie ustawienia. Scenariusze z przewodnikiem wymagają podania danych wejściowych wyłącznie dla minimalnej liczby ustawień i ukrywają rzadko stosowane lub zaawansowane ustawienia, jeśli nie są potrzebne, lub pokazują je w określonych okolicznościach. Każdy scenariusz z przewodnikiem zawiera linki do dokumentacji, w której zawarte są dodatkowe informacje. 

Po wprowadzeniu wszystkich obowiązkowych ustawień w scenariuszu z przewodnikiem zostanie przedstawione podsumowanie wprowadzonych ustawień oraz zasoby wymagane przez scenariusz. W tym momencie nic nie jest jeszcze zapisywane, o ile nie zostało to wyraźnie odnotowane.

Następnym krokiem jest wdrożenie scenariusza. Wdrożenie scenariusza powoduje utworzenie i zapisanie wszystkich niezbędnych zasobów i wybranych ustawień. Czas potrzebny na ukończenie wdrożenia różni się w zależności od scenariusza. Po zakończeniu wdrożenia w scenariuszu z przewodnikiem przedstawiana jest lista utworzonych zasobów z linkami do widoku zarządzania każdego zasobu, normalnego obciążenia zasobu i dokumentacji. 

> [!IMPORTANT]
> Lista przedstawiana na końcu scenariusza z przewodnikiem nie jest zapisywana i można ją wyświetlać wyłącznie, gdy scenariusz z przewodnikiem jest otwarty.  
Jeśli podczas wdrażania scenariusza wystąpi błąd, wszystkie zmiany zostaną wycofane. 

### <a name="editing"></a>Edytowanie 

Scenariuszy z przewodnikiem nie można używać do edytowania istniejących zasobów. Wszystkie utworzone zasoby, grupy i przypisania muszą być edytowane przy użyciu istniejących obciążeń.

### <a name="monitoring"></a>Monitorowanie 

Scenariuszy z przewodnikiem nie można używać do monitorowania istniejących zasobów, z wyjątkiem początkowego procesu tworzenia. Wszystkie utworzone zasoby, grupy i przypisania muszą być monitorowane przy użyciu istniejących obciążeń. 

### <a name="retiring"></a>Wycofywanie 

Scenariuszy z przewodnikiem nie można używać do wycofywania istniejących zasobów, z wyjątkiem automatycznego czyszczenia w przypadku wystąpienia błędu w trakcie początkowego wdrożenia. Wszystkie utworzone zasoby, grupy i przypisania muszą być wycofywane przy użyciu istniejących obciążeń. 

### <a name="updating"></a>Aktualizowanie

Wraz z rozwojem technologii scenariusze z przewodnikiem w usłudze Intune mogą być od czasu do czasu aktualizowane, aby usprawnić środowisko użytkownika oraz poprawić bezpieczeństwo i inne aspekty scenariuszy. Ta aktualizacja będzie miała wpływ wyłącznie na nowe wdrożenia utworzone w scenariuszach z przewodnikiem. Usługa Intune nie zaktualizuje zasobów wygenerowanych wcześniej przy użyciu scenariusza z przewodnikiem w celu dostosowania ich do najlepszych rozwiązań lub zaleceń.  

## <a name="next-steps"></a>Następne kroki

Aby szybko rozpocząć pracę z usługą Microsoft Intune, zapoznaj się ze scenariuszami z przewodnikiem usługi Intune. Jeśli jesteś nowym użytkownikiem usługi Intune, utwórz dzierżawę usługi Intune, wykonując czynności opisane w [przewodniku Szybki start bezpłatnej wersji próbnej](free-trial-sign-up.md).
