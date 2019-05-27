---
title: Używanie usługi Intune do korygowania luk w zabezpieczeniach znalezionych przez usługę Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender — Azure | Microsoft Docs
description: Zobacz, jak zarządzać zadaniami zabezpieczeń przy użyciu funkcji zarządzania zagrożeniami i lukami w zabezpieczeniach, która wchodzi w skład usługi Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender, z poziomu konsoli usługi Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/17/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f6f6f319b5c38f290f3cdb6d4a04528f3b227212
ms.sourcegitcommit: f8bbd9bac2016a77f36461bec260f716e2155b4a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/16/2019
ms.locfileid: "65733395"
---
# <a name="use-intune-to-remediate-vulnerabilities-identified-by-microsoft-defender-atp"></a>Używanie usługi Intune do korygowania luk w zabezpieczeniach znalezionych przez usługę Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender  

Po zintegrowaniu usługi Intune z usługą Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender można korzystać z zalet funkcji zarządzania zagrożeniami i lukami w zabezpieczeniach usługi Zaawansowana ochrona przed zagrożeniami i używać usługi Intune do korygowania słabości punktów końcowych wykrytych przez funkcję zarządzania zagrożeniami i lukami w zabezpieczeniach. Integracja ta oferuje podejście oparte na ryzyku, które można zastosować w procesie odnajdywania luk w zabezpieczeniach i nadawania im priorytetów w celu skrócenia czasu reakcji dotyczącego korygowania w środowisku.  

[Zarządzanie zagrożeniami i lukami w zabezpieczeniach](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/next-gen-threat-and-vuln-mgt) jest częścią usługi [Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection).  

## <a name="how-integration-works"></a>Jak działa integracja  

Po połączeniu usługi Intune z Zaawansowaną ochroną przed zagrożeniami w usłudze Microsoft Defender usługa Zaawansowana ochrona przed zagrożeniami odbiera szczegóły zagrożeń i luk w zabezpieczeniach z urządzeń zarządzanych.  

W konsoli usługi Windows Defender Security Center administratorzy zabezpieczeń Zaawansowanej ochrony przed zagrożeniami mogą przeglądać dane dotyczące luk w zabezpieczeniach punktów końcowych. Administratorzy mogą następnie za pomocą jednego kliknięcia utworzyć zadania zabezpieczeń, które będą oflagowywać urządzenia narażone na ryzyko jako przeznaczone do skorygowania. Zadania zabezpieczeń są od razu przekazywane do konsoli usługi Intune, w której administratorzy usługi Intune mogą je przeglądać. Zadanie zabezpieczeń identyfikuje typ luki w zabezpieczeniach, priorytet, stan i czynności umożliwiające jej skorygowanie. Administrator usługi Intune wybiera opcję zaakceptowania lub odrzucenia zadania.  

Po zaakceptowaniu zadania administrator usługi Intune koryguje lukę w zabezpieczeniach za pośrednictwem usługi Intune, korzystając z wytycznych przedstawionych w ramach zadania zabezpieczenia.  

Typowe akcje w przypadku korygowania to:  
- **Blokowanie** uruchamiania przez aplikację.  
- **Wdrażanie** aktualizacji systemu operacyjnego w celu wyeliminowania luki w zabezpieczeniach.  
- **Modyfikowanie** wartości rejestru.  
- **Wyłączanie** lub **włączanie** konfiguracji, która wpływa na lukę w zabezpieczeniach.  
- Opcja **Wymaga uwagi** powiadamia administratora o zagrożeniu, gdy nie ma odpowiednich rekomendacji do wyświetlenia.  

Przykładowy przepływ pracy:  
- Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender odnajduje lukę w zabezpieczeniach aplikacji o nazwie Contoso Media Player w wersji 4. Administrator tworzy zadanie zabezpieczeń w celu zaktualizowania tej aplikacji. Contoso Media Player to niezarządzana aplikacja, która została wdrożona przy użyciu usługi Intune.  

  To zadanie zabezpieczeń jest wyświetlane w konsoli usługi Intune ze stanem Oczekujące:  
  ![Wyświetlanie listy zadań zabezpieczeń w konsoli usługi Intune](./media/atp-manage-vulnerabilities/temp-security-tasks.png)
 
- Administrator usługi Intune wybiera zadanie zabezpieczeń, aby wyświetlić szczegółowe informacje o zadaniu.  Następnie administrator wybiera pozycję **Zaakceptuj**, która służy do aktualizowania stanu w usłudze Intune i Zaawansowanej ochronie przed zagrożeniami na *Zaakceptowano*.  
  ![Akceptowanie lub odrzucanie zadania zabezpieczeń](./media/atp-manage-vulnerabilities/temp-accept-task.png) 
 
- Następnie administrator koryguje zadanie w oparciu o podane wskazówki.  Wskazówki różnią się w zależności od wymaganego typu korygowania. Jeśli wskazówki dotyczące korygowania są dostępne, obejmują linki, które otwierają okienka właściwe w przypadku konfiguracji w usłudze Intune. 

  Ponieważ odtwarzacz multimedialny w tym przykładzie nie jest aplikacją zarządzaną, usługa Intune może zaoferować tylko instrukcje tekstowe. Jeśli aplikacja byłaby zarządzana, usługa Intune mogłaby podać instrukcje dotyczące pobierania zaktualizowanej wersji i udostępnić link umożliwiający otwieranie wdrożenia dla aplikacji, tak aby zaktualizowane pliki można było dodać do wdrożenia. 

- Po zakończeniu korygowania administrator usługi Intune otwiera zadanie zabezpieczeń i wybiera pozycję **Zakończ zadanie**.  Stan korygowania jest aktualizowany w usłudze Intune i Zaawansowanej ochronie przed zagrożeniami, gdzie administratorzy zabezpieczeń potwierdzają zmodyfikowany stan luki w zabezpieczeniach.  

## <a name="prerequisites"></a>Wymagania wstępne  

**Subskrypcje**:  
- Microsoft Intune  
- Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender ([utwórz konto bezpłatnej wersji próbnej](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-main-abovefoldlink)).  

**Konfiguracje usługi Intune dla Zaawansowanej ochrony przed zagrożeniami**:  
- Skonfigurowanie połączenia między usługami za pomocą Zaawansowanej ochrony przed zagrożeniami w usłudze Microsoft Defender.  
- Wdrożenie zasad zgodności urządzeń za pomocą profilu typu **Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender (Windows 10 Desktop)** na urządzeniach, dla których ryzyko będzie oceniane przy użyciu Zaawansowanej ochrony przed zagrożeniami.
  Aby uzyskać informacje dotyczące sposobu konfigurowania usługi Intune do pracy z Zaawansowaną ochrony przed zagrożeniami, zobacz [Wymuszanie zgodności dla Zaawansowanej ochrony przed zagrożeniami z dostępem warunkowym w usłudze Intune](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).  

## <a name="work-with-security-tasks"></a>Praca z zadaniami zabezpieczeń  

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) i przejdź do pozycji **Bezpieczeństwo urządzeń** > **Zadania zabezpieczeń**.  
2. Wybierz zadanie z listy, aby otworzyć okno zasobów z dodatkowymi szczegółami tego zadania zabezpieczeń.  
3. W wyświetlonym oknie zasobów zadania zabezpieczeń możesz wybrać dodatkowe linki:  
   - APLIKACJE ZARZĄDZANE — wyświetl aplikację podatną na zagrożenia. Jeśli luka w zabezpieczeniach dotyczy wielu aplikacji, zobaczysz odfiltrowaną listę aplikacji.  
   - URZĄDZENIA — wyświetl listę *urządzeń narażonych na zagrożenia*, z której można połączyć się z wpisem zawierającym szczegółowe informacje dotyczące luki w zabezpieczeniach na danym urządzeniu.  
   - OSOBA ŻĄDAJĄCA — użyj tego linku do wysłania wiadomości e-mail do administratora, który przesłał to zadanie zabezpieczeń.  
   - NOTATKI — przeczytaj niestandardowe wiadomości przesłane przez osobę żądającą po otwarciu zadania zabezpieczeń.  
4. Wybierz pozycję **Zaakceptuj** lub **Odrzuć**, aby wysłać powiadomienie dotyczące planowanej akcji do Zaawansowanej ochrony przed zagrożeniami. Po zaakceptowaniu lub odrzuceniu zadania można przesłać notatki, które zostaną wysłane do Zaawansowanej ochrony przed zagrożeniami.  

5. Po zaakceptowaniu zadania otwórz ponownie zadanie zabezpieczeń (jeśli zostało zamknięte), a następnie postępuj zgodnie ze szczegółowymi informacjami w obszarze KORYGOWANIE w celu skorygowania luki w zabezpieczeniach.  Instrukcje udostępniane przez Zaawansowaną ochronę przed zagrożeniami w szczegółach zadania zabezpieczeń zależą od uwzględnionej luki w zabezpieczeniach.  

   Jeśli jest to możliwe, instrukcje dotyczące korygowania zawierają linki, które otwierają odpowiednie obiekty konfiguracji w konsoli usługi Intune.  

6. Po zakończeniu czynności korygujących otwórz zadanie zabezpieczeń, a następnie wybierz pozycję **Zakończ zadanie**.  Ta akcja aktualizuje stan zadania zabezpieczeń w usłudze Intune i Zaawansowanej ochronie przed zagrożeniami.  

Po pomyślnym zakończeniu korygowania ocena narażenia na ryzyko może zostać obniżona w Zaawansowanej ochronie przed zagrożeniami w oparciu o nowe informacje ze skorygowanych urządzeń. 

## <a name="next-steps"></a>Następne kroki
Dowiedz się więcej o usługach Intune i [Zaawansowana ochrona przed zagrożeniami w usłudze Microsoft Defender](https://docs.microsoft.com/intune/advanced-threat-protection)  
Zapoznaj się z usługą [Mobile Threat Defense](https://docs.microsoft.com/intune/mobile-threat-defense) w usłudze Intune  
Zapoznaj się z [pulpitem nawigacyjnym funkcji zarządzania zagrożeniami i lukami w zabezpieczeniach](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/tvm-dashboard-insights) w Zaawansowanej ochronie przed zagrożeniami w usłudze Microsoft Defender
