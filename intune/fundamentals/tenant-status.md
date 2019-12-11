---
title: Strona Stan dzierżawy w usłudze Microsoft Intune
titleSuffix: Microsoft Intune
description: Strona Stan dzierżawy w usłudze Intune do wyświetlania ważnych szczegółów dzierżawy bez konieczności opuszczania portalu usługi Intune
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.assetid: 7954a686-25dc-4fce-b395-324816f46d3b
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c79f24d44ad0aed78ed0ae6fce0873a080b2904d
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72504850"
---
# <a name="use-the-intune-tenant-status-page"></a>Korzystanie ze strony Stan dzierżawy w usłudze Intune
Strona Stan dzierżawy usługi Microsoft Intune pełni funkcję centrum, które udostępnia aktualne, ważne informacje o dzierżawie. Szczegółowe informacje obejmują dostępność i użycie licencji, stan łącznika oraz ważne komunikaty dotyczące usługi Intune.  

Aby wyświetlić pulpit nawigacyjny, zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973), a następnie wybierz pozycję **Stan dzierżawy**.  *Stan dzierżawy* zostanie wyświetlony w obszarze **Pomoc i obsługa techniczna**.  

Strona jest podzielona na trzy karty:

## <a name="tenant-details"></a>Szczegóły dzierżawy
Obszar Szczegóły dzierżawy zapewnia natychmiastowy dostęp do informacji na temat dzierżawy. Możesz wyświetlić takie informacje, jak na przykład nazwa dzierżawy i jej lokalizacja, urząd zarządzania urządzeniami przenośnymi oraz numer wydania usługi dzierżawy. Numer wydania usługi to link, który prowadzi do artykułu *Co nowego w usłudze Intune* w witrynie Microsoft Docs. Artykuł *Co nowego* zawiera informacje o najnowszych funkcjach i aktualizacjach w usłudze Intune.  

Na tej karcie znajdziesz również podstawowe informacje na temat dostępnych licencji oraz tego, ile z nich zostało przypisanych do użytkowników. Licencje dla urządzeń nie są wyświetlane.

## <a name="connector-status"></a>Stan łącznika
Stan łączników to centralna lokalizacja służąca do wyświetlania stanu wszystkich dostępnych łączników dla usługi Intune.  

Łączniki to:
- **Skonfigurowane połączenia z zewnętrznymi usługami**. Na przykład z usługą *Apple Volume Purchase Program* lub *Windows Autopilot*.  Stan tego typu łącznika jest określany na podstawie czasu ostatniej pomyślnej synchronizacji.
- **Certyfikaty lub poświadczenia, które są wymagane do połączenia z niezarządzaną usługą zewnętrzną**, na przykład certyfikaty *Apple Push Notification Service* (APNS). Stan tego typu łącznika jest określany na podstawie znacznika czasu wygaśnięcia certyfikatu lub poświadczenia.  

Po otwarciu karty *Stan łącznika* wszystkie łączniki w złej kondycji zostaną wyświetlone na początku listy. Poniżej wymienione są łączniki z ostrzeżeniami, a następnie łączniki w dobrej kondycji. Łączniki, których jeszcze nie skonfigurowano, znajdują się na końcu jako *niewłączone*.

Jeśli jest więcej niż jeden łącznik dowolnego typu, stan łącznika to podsumowanie stanu wszystkich takich samych łączników. Najgorsza kondycja łącznika jest używana jako kondycja całej grupy.  

**Stan łącznika:**
- **Zła kondycja:**
  - Certyfikat lub poświadczenie wygasło
  - Ostatnia synchronizacja została przeprowadzona co najmniej trzy dni temu
- **Ostrzeżenie:**
  - Certyfikat lub poświadczenie wygaśnie w ciągu siedmiu dni
  - Ostatnia synchronizacja została przeprowadzona co najmniej jeden dzień temu
- **Dobra kondycja:**
  - Certyfikat lub poświadczenie nie wygaśnie w ciągu następnych siedmiu dni
  - Ostania synchronizacja została przeprowadzona mniej niż jeden dzień temu  

Po wybraniu łącznika na liście w portalu zostanie wyświetlona strona portalu odpowiadająca temu łącznikowi. Na stronie łączników można przejrzeć stan wcześniej skonfigurowanych łączników lub wybrać opcje w celu dodania lub utworzenia nowego łącznika wybranego typu.

Na przykład po wybraniu łącznika **Data ważności VPP** jest otwierana strona **Tokeny programu Volume Purchase Program systemu iOS**, na której można wyświetlić więcej informacji na temat tego łącznika. Możesz również utworzyć nową konfigurację lub edytować istniejącą i rozwiązywać problemy w niej występujące.

## <a name="service-health-dashboard"></a>Pulpit nawigacyjny kondycji usługi  
Na pulpicie nawigacyjnym kondycji usługi można wyświetlić szczegółowe informacje o *zdarzeniach związanych z usługą*, które mają wpływ na dzierżawę, a także *wiadomości dotyczące usługi Intune*, w tym informacje o aktualizacjach i planowanych zmianach.

### <a name="intune-service-health"></a>Kondycja usługi Intune
Wyświetlaj szczegóły aktywnych zdarzeń i ostrzeżenia bez konieczności przechodzenia do pulpitu nawigacyjnego Microsoft 365 Service Health lub Centrum wiadomości, które są zlokalizowane w [Centrum administracyjnym usługi Microsoft 365](https://admin.microsoft.com). Są wyświetlane tylko zdarzenia mające wpływ na dzierżawę.  

Po wybraniu zdarzenia szczegóły zdarzenia są przedstawiane bezpośrednio na stronie Stan dzierżawy. Aby wyświetlić wcześniejsze ostrzeżenia i zdarzenia, wybierz pozycję **Zobacz wcześniejsze zdarzenia/ostrzeżenia**. Zostanie otwarte Centrum administracyjne usługi Microsoft 365, gdzie możesz wyświetlać ostrzeżenia i zdarzenia dotyczące dzierżawy z ostatnich 30 dni.  

Aby wyświetlać informacje na temat *kondycji usługi Intune*, Twoje konto musi mieć rolę**Administrator globalny** lub **Administrator usługi** w usłudze Azure Active Directory lub w Centrum administracyjnym usługi Microsoft 365. Aby przypisać te uprawnienia, zaloguj się do [Centrum administracyjnego usługi Microsoft 365](https://admin.microsoft.com) z uprawnieniami administratora globalnego. Wybierz kolejno pozycje **Użytkownicy > Aktywni użytkownicy**, a następnie wybierz konto, które wymaga dostępu. Wybierz opcję **Edytuj** w obszarze Role, wybierz rolę *Administrator usługi* lub *Administrator globalny*, a następnie wybierz polecenie **Zapisz**, aby przypisać uprawnienia.  

Preferencje dotyczące komunikacji dla funkcji Kondycja usługi Intune możesz skonfigurować wyłącznie za pośrednictwem Centrum administracyjnego usługi Microsoft 365.

### <a name="intune-news"></a>Wiadomości w usłudze Intune  
Wyświetlaj komunikaty informacyjne od zespołu usługi Intune bez konieczności przechodzenia do Centrum wiadomości usługi Office. Znajdziesz tu wiadomości na temat zmian wprowadzonych ostatnio w usłudze Intune lub takich, które niedługo zostaną wprowadzone w Twojej dzierżawie.  

Domyślnie jest wyświetlanych 10 ostatnich i aktywnych wiadomości. Aby wyświetlić starsze wiadomości, wybierz polecenie **Zobacz wcześniejsze wiadomości**, aby otworzyć *Centrum wiadomości* w portalu Centrum administracyjne usługi Microsoft 365.  

Aby wyświetlić informacje na temat funkcji Wiadomości w usłudze Intune, musisz mieć rolę **Administrator globalny** lub **Administrator usługi** w usłudze Azure Active Directory lub mieć przypisaną rolę **czytelnika Centrum wiadomości** w portalu Centrum administracyjne usługi Microsoft 365.  Aby przypisać to uprawnienie, zaloguj się do [Centrum administracyjnego usługi Microsoft 365](https://admin.microsoft.com) z uprawnieniami administratora. Wybierz kolejno pozycje **Użytkownicy > Aktywni użytkownicy**, a następnie wybierz konto, które wymaga dostępu. Wybierz opcję **Edytuj** w polu *Role*, wybierz opcję *Administrator komunikacji w usłudze Teams*, a następnie **Zapisz** zmiany, aby przypisać uprawnienia.  

Preferencje dotyczące komunikacji dla funkcji Wiadomości w usłudze Intune możesz skonfigurować wyłącznie za pośrednictwem Centrum administracyjnego usługi Microsoft 365.
