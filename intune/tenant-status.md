---
title: Strona Stan dzierżawy w usłudze Microsoft Intune
titleSuffix: Microsoft Intune
description: Strona Stan dzierżawy w usłudze Intune do wyświetlania ważnych szczegółów dzierżawy bez konieczności opuszczania portalu usługi Intune
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/09/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 98b3180bc90c7b54213781ddf8b6668918b22dd3
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/10/2019
ms.locfileid: "54205028"
---
# <a name="intune-tenant-status-page"></a>Strona Stan dzierżawy w usłudze Intune
Strona Stan dzierżawy to centralna lokalizacja, zapewniająca bieżący dostęp do ważnych informacji dotyczących Twojej dzierżawy, dostępności i użycia licencji, stanu łączników oraz ważnych komunikatów na temat usługi Intune.  

Aby wyświetlić ten pulpit nawigacyjny, w witrynie Azure Portal przejdź do pozycji **Intune > Stan dzierżawy**.  Stan dzierżawy zostanie wyświetlony w obszarze **Pomoc i obsługa techniczna**.  

Strona jest podzielona na cztery obszary:

## <a name="tenant-details"></a>Szczegóły dzierżawy
Obszar Szczegóły dzierżawy zapewnia natychmiastowy dostęp do informacji na temat dzierżawy. Możesz wyświetlić takie informacje, jak na przykład nazwa dzierżawy i jej lokalizacja, urząd zarządzania urządzeniami przenośnymi oraz numer wydania usługi dzierżawy. Numer wydania usługi dzierżawy to link, który otwiera artykuł *Co nowego w usłudze Intune* w dokumentacji firmy Microsoft, gdzie możesz zapoznać się z najnowszymi funkcjami i aktualizacjami usługi Microsoft Intune.  

Ta sekcja udostępnia również podstawowe informacje na temat dostępnych licencji oraz tego, ile z nich jest przypisanych do użytkowników. Licencje dla urządzeń nie są wyświetlane.

## <a name="connector-status"></a>Stan łącznika
Stan łączników to centralna lokalizacja służąca do wyświetlania stanu wszystkich dostępnych łączników dla usługi Intune.  

Łączniki to:
- **Skonfigurowane połączenia z zewnętrznymi usługami**. Na przykład z usługą *Apple Volume Purchase Program* lub *Windows Autopilot*.  Stan tego typu łącznika jest określany na podstawie czasu ostatniej pomyślnej synchronizacji.
- **Certyfikaty lub poświadczenia, które są wymagane do połączenia z niezarządzaną usługą zewnętrzną**, na przykład certyfikaty *Apple Push Notification Service* (APNS). Stan tego typu łącznika jest określany na podstawie znacznika czasu wygaśnięcia certyfikatu lub poświadczenia.  

Domyślnie wyświetlanych jest tylko pięć łączników. Możesz wybrać opcję **Zobacz wszystkie łączniki**, aby rozwinąć tę listę i wyświetlić wszystkie dostępne łączniki, w tym te, które nie zostały skonfigurowane do użycia.  

Jeśli jest więcej niż jeden łącznik dowolnego typu, stan łącznika to podsumowanie stanu wszystkich takich samych łączników. Najgorsza kondycja łącznika jest używana jako kondycja całej grupy.  

Łączniki w złej kondycji są zawsze wyświetlane na początku listy. Poniżej wymienione są łączniki z ostrzeżeniami, a następnie łączniki w dobrej kondycji. Łączniki, których jeszcze nie skonfigurowano, znajdują się na końcu.

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

Po wybraniu łącznika na liście w portalu zostanie wyświetlona strona tworzenia lub konfigurowania tego łącznika.  Na przykład po wybraniu łącznika **Data ważności VPP** otwiera się strona **Tokeny programu Volume Purchase Program systemu iOS**, na której można wyświetlić więcej informacji na temat tego łącznika. Możesz utworzyć nową konfigurację lub edytować istniejącą i rozwiązywać problemy w niej występujące.  

## <a name="intune-service-health"></a>Kondycja usługi Intune  
Możesz wyświetlać szczegóły aktywnych zdarzeń i ostrzeżenia bez konieczności przechodzenia do pulpitu nawigacyjnego usługi Microsoft 365 Service Health lub Centrum wiadomości, które są zlokalizowane w Centrum administracyjnym usługi Microsoft 365 pod adresem https://portal.office.com. Wyświetlane są wyłącznie te zdarzenia, które miały wpływ na Twoją dzierżawę.  

Po wybraniu zdarzenia szczegóły zdarzenia są przedstawiane bezpośrednio na stronie Stan dzierżawy. Aby wyświetlić wcześniejsze ostrzeżenia i zdarzenia, wybierz pozycję **Zobacz wcześniejsze zdarzenia/ostrzeżenia**. Zostanie otwarte Centrum administracyjne usługi Microsoft 365, gdzie możesz wyświetlać ostrzeżenia i zdarzenia dotyczące dzierżawy z ostatnich 30 dni.  

Aby wyświetlać informacje na temat *kondycji usługi Intune*, Twoje konto musi mieć rolę**Administrator globalny** lub **Administrator usługi** w usłudze Azure Active Directory lub w portalu administracyjnym usługi Office. Aby przypisać te uprawnienia, zaloguj się do [Centrum administracyjnego usługi Microsoft 365](https://portal.officeppe.com/AdminPortal/Home#/homepage) z uprawnieniami administratora globalnego. Wybierz kolejno pozycje **Użytkownicy > Aktywni użytkownicy**, a następnie wybierz konto, które wymaga dostępu. Wybierz opcję **Edytuj** w obszarze Role, wybierz rolę *Administrator usługi* lub *Administrator globalny*, a następnie wybierz polecenie **Zapisz**, aby przypisać uprawnienia.  

Preferencje dotyczące komunikacji dla funkcji Kondycja usługi Intune możesz skonfigurować wyłącznie za pośrednictwem Centrum administracyjnego usługi Microsoft 365.

## <a name="intune-news"></a>Wiadomości w usłudze Intune  
Wyświetlaj komunikaty informacyjne od zespołu usługi Intune bez konieczności przechodzenia do Centrum wiadomości usługi Office. Znajdziesz tu wiadomości na temat zmian wprowadzonych ostatnio w usłudze Intune lub takich, które niedługo zostaną wprowadzone w Twojej dzierżawie.  

Domyślnie wyświetlanych jest ostatnich 10 aktywnych wiadomości. Aby wyświetlić starsze wiadomości, wybierz polecenie **Zobacz wcześniejsze wiadomości**, aby otworzyć *Centrum wiadomości* w portalu Centrum administracyjne usługi Microsoft 365.  

Aby wyświetlić informacje na temat funkcji Wiadomości w usłudze Intune, musisz mieć rolę **Administrator globalny** lub **Administrator usługi** w usłudze Azure Active Directory lub mieć przypisaną rolę **czytelnika Centrum wiadomości** w portalu administracyjnym pakietu Office.  Aby przypisać to uprawnienie, zaloguj się do [Centrum administracyjnego usługi Microsoft 365](https://portal.officeppe.com/AdminPortal/Home#/homepage) z uprawnieniami administratora. Wybierz kolejno pozycje **Użytkownicy > Aktywni użytkownicy**, a następnie wybierz konto, które wymaga dostępu. Wybierz opcję **Edytuj** w polu *Role*, wybierz opcję *Administrator komunikacji w usłudze Teams*, a następnie **Zapisz** zmiany, aby przypisać uprawnienia.  

Preferencje dotyczące komunikacji dla funkcji Wiadomości w usłudze Intune możesz skonfigurować wyłącznie za pośrednictwem Centrum administracyjnego usługi Microsoft 365.
