---
title: Zarządzanie aplikacjami firmy Apple nabytymi w ramach zakupów zbiorczych
titleSuffix: Microsoft Intune
description: Informacje o synchronizowaniu aplikacji nabytych w ramach zakupów zbiorczych w sklepie App Store z aplikacjami dla systemu iOS i macOS z usługą Microsoft Intune oraz o zarządzaniu ich użyciem i jego śledzeniu.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d965ac35719d809ab922d28f76dec1754e9a4c6b
ms.sourcegitcommit: 9b29478f815e10c46c8030abe0146d601ce0e28c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2020
ms.locfileid: "77051630"
---
# <a name="how-to-manage-ios-and-macos-apps-purchased-through-apple-volume-purchase-program-with-microsoft-intune"></a>Jak w usłudze Microsoft Intune zarządzać aplikacjami dla systemów iOS i macOS, które zostały zakupione w ramach programu zakupów zbiorczych firmy Apple


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Firma Apple umożliwia zakupienie wielu licencji dla aplikacji, która ma być używana w organizacji na urządzeniach z systemem iOS i macOS przy użyciu programu [Apple Business Manager](https://business.apple.com/) lub [Apple School Manager](https://school.apple.com/). Następnie można zsynchronizować dane zakupu zbiorczego z usługą Intune i śledzić użycie aplikacji nabytych w ramach zakupu zbiorczego. Kupowanie licencji aplikacji pomaga wydajnie zarządzać aplikacjami w firmie i zachować własność i kontrolę nad zakupionymi aplikacjami. 

Usługa Microsoft Intune ułatwia zarządzanie aplikacjami kupionymi za pośrednictwem tego programu, ponieważ umożliwia:

- Synchronizowanie tokenów lokalizacji pobranych z programu Apple Business Manager.
- Śledzenie liczby licencji dostępnych i użytych w zakupionych aplikacjach.
- Pomoc przy instalowaniu aplikacji do liczby posiadanych licencji.

Oprócz tego przy użyciu usługi Intune można synchronizować książki kupione w programie Apple Business Manager oraz zarządzać nimi i przypisywać je do urządzeń z systemem iOS. Aby uzyskać więcej informacji, zobacz [Jak zarządzać książkami elektronicznymi dla systemu iOS, które zostały zakupione w ramach programu zakupów zbiorczych](vpp-ebooks-ios.md).

## <a name="what-are-location-tokens"></a>Co to są tokeny lokalizacji?
Tokeny lokalizacji są również nazywane tokenami programu Volume Purchase Program (VPP). Te tokeny służą do przypisywania licencji zakupionych w ramach programu Apple Business Manager i zarządzania nimi. Menedżerowie zawartości mogą kupować licencje i kojarzyć je z tokenami lokalizacji, do których mają uprawnienia w programie Apple Business Manager. Te tokeny lokalizacji są następnie pobierane z programu Apple Business Manager i przekazywane w usłudze Microsoft Intune. Usługa Microsoft Intune obsługuje przekazywanie wielu tokenów lokalizacji na dzierżawę. Każdy token jest ważny przez jeden rok.

## <a name="how-are-purchased-apps-licensed"></a>Jak odbywa się licencjonowanie zakupionych aplikacji?
Zakupione aplikacje można przypisać do grup przy użyciu dwóch typów licencji oferowanych przez firmę Apple dla urządzeń z systemem iOS i macOS.

|   | Licencjonowanie na urządzenie | Licencjonowanie na użytkownika |
|-----|------------------|----------------|
| **Logowanie w sklepie App Store** | Niewymagane. | Każdy użytkownik końcowy musi użyć unikatowego identyfikatora Apple ID, gdy zostanie wyświetlony monit o zalogowanie się w sklepie App Store. |
| **Konfiguracja urządzenia blokująca dostęp do sklepu App Store** | Aplikacje można instalować i aktualizować przy użyciu Portalu firmy. | Zaproszenie do dołączenia do programu Apple VPP wymaga dostępu do sklepu App Store. Jeśli ustawiono zasady wyłączające sklep App Store, licencjonowanie na użytkownika nie będzie działać w przypadku aplikacji programu VPP. |
| **Automatyczna aktualizacja aplikacji** | Zgodnie z konfiguracją zdefiniowaną przez administratora usługi Intune w ustawieniach tokenu VPP firmy Apple, w której **typ przypisania** aplikacji to **wymagana**. <br> <br> Jeśli **typ przypisania** to **dostępna dla zarejestrowanych urządzeń**, dostępne aktualizacje aplikacji można instalować z poziomu Portalu firmy. | Zgodnie z konfiguracją zdefiniowaną przez użytkownika końcowego w osobistych ustawieniach sklepu App Store. Brak możliwości zarządzania przez administratora usługi Intune. |
| **Rejestrowanie użytkownika** | Nieobsługiwane. | Obsługiwane przy użyciu zarządzanych identyfikatorów Apple ID. |
| **Książki** | Nieobsługiwane. | Obsługiwane. |
| **Licencje użyte** | 1 licencja na urządzenia. Licencja jest skojarzona z urządzeniem. | 1 licencja na maksymalnie 5 urządzeń przy użyciu tego samego osobistego identyfikatora Apple ID. Licencja jest skojarzona z użytkownikiem. <br> <br> Użytkownik końcowy skojarzony z osobistym identyfikatorem Apple ID i zarządzanym identyfikatorem Apple ID w usłudze Intune zużywa 2 licencje aplikacji.|
| **Migracja licencji** | Aplikacje można migrować w trybie dyskretnym z licencji na użytkownika do licencji na urządzenie. | Aplikacji nie można migrować z licencji na urządzenie do licencji na użytkownika. |

> [!NOTE]  
> Portal firmy nie wyświetla aplikacji licencjonowanych na urządzenie na urządzeniach rejestrowanych przez użytkowników, ponieważ na urządzeniach rejestrowanych przez użytkowników można instalować tylko aplikacje licencjonowane na użytkownika.

## <a name="what-app-types-are-supported"></a>Jak typy aplikacji są obsługiwane?
Możesz kupować i dystrybuować aplikacje publiczne oraz prywatne za pomocą programu Apple Business Manager.
- **Aplikacje ze Sklepu:** za pomocą programu Apple Business Manager menedżerowie zawartości mogą kupować bezpłatne i płatne aplikacje, które są dostępne w sklepie App Store.
- **Aplikacje niestandardowe:** Za pomocą programu Apple Business Manager menedżerowie zawartości mogą również kupować aplikacje niestandardowe udostępnione prywatnie w organizacji. Te aplikacje są dostosowywane do konkretnych potrzeb organizacji przez deweloperów, z którymi bezpośrednio współpracujesz. Dowiedz się więcej na temat sposobu [dystrybuowania aplikacji niestandardowych](https://developer.apple.com/business/custom-apps/).

## <a name="prerequisites"></a>Wymagania wstępne
- Konto programu [Apple Business Manager](https://business.apple.com/) lub [Apple School Manager](https://school.apple.com/) dla organizacji. 
- Licencje zakupionych aplikacji przypisane do co najmniej jednego tokenu lokalizacji. 
- Pobrane tokeny lokalizacji. 

> [!IMPORTANT]
> - Tokenu lokalizacji można używać tylko z jednym rozwiązaniem do zarządzania urządzeniami jednocześnie. Przed rozpoczęciem korzystania z zakupionych aplikacji przy użyciu usługi Intune należy odwołać i usunąć wszystkie istniejące tokeny lokalizacji utworzone przy użyciu innych dostawców zarządzania urządzeniami mobilnymi. 
> - W danym momencie token lokalizacji może być używany tylko w ramach jednej dzierżawy usługi Intune. Nie używaj tego samego tokenu dla wielu dzierżaw usługi Intune.
> - Domyślnie usługa Intune synchronizuje tokeny lokalizacji z firmą Apple dwa razy dziennie. Można jednak w dowolnym momencie zainicjować ręczną synchronizację w usłudze Intune.
> - Po zaimportowaniu tokenu lokalizacji do usługi Intune nie należy importować tego samego tokenu do żadnego innego rozwiązania do zarządzania urządzeniami. Może to spowodować utratę przypisania licencji i rekordów użytkowników.

## <a name="migrate-from-volume-purchase-program-vpp-to-apps-and-books"></a>Migrowanie z programu Volume Purchase Program (VPP) do aplikacji i książek
Jeśli Twoja organizacja nie była jeszcze migrowana do programu Apple Business Manager lub Apple School Manager, przed przystąpieniem do zarządzania zakupionymi aplikacjami w usłudze Intune zapoznaj się ze [wskazówkami firmy Apple dotyczącymi migracji do aplikacji i książek](https://support.apple.com/HT208257).

> [!IMPORTANT]
> - Aby zapewnić najlepsze środowisko migracji, należy migrować tylko jednego nabywcę programu VPP na lokalizację. Jeśli każdy nabywca jest migrowany do unikatowej lokalizacji, wszystkie licencje — przypisane i nieprzypisane — zostaną przeniesione do aplikacji i książek.
> - Nie usuwaj istniejącego starszego tokenu programu VPP w usłudze Intune ani aplikacji i przypisań skojarzonych z istniejącym starszym tokenem programu VPP w usłudze Intune. Te akcje będą wymagały ponownego utworzenia wszystkich przypisań aplikacji w usłudze Intune.

Migruj istniejącą zakupioną zawartość i tokeny programu VPP do aplikacji i książek w programie Apple Business Manager lub Apple School Manager w następujący sposób:

1. Zaproś nabywców programu VPP do dołączenia do organizacji i poinformuj każdego użytkownika o konieczności wybrania unikatowej lokalizacji. 
2. Przed kontynuowaniem upewnij się, że wszyscy nabywcy programu VPP w organizacji wykonali krok 1.
3. Sprawdź, czy wszystkie zakupione aplikacje i licencje zostały zmigrowane do aplikacji i książek w programie Apple Business Manager lub Apple School Manager.
4. Pobierz nowy token lokalizacji, przechodząc do pozycji **Apple Business (lub School) Manager** > **Settings (Ustawienia)**  > **Apps and Books (Aplikacje i książki)**  > **My Server Tokens (Moje tokeny serwera)** .
5. Zaktualizuj token lokalizacji w centrum administracyjnym programu Microsoft Endpoint Manager, przechodząc do pozycji **Administracja dzierżawą** > **Łączniki i tokeny** > **Tokeny VPP firmy Apple** i zsynchronizuj token.

## <a name="upload-an-apple-vpp-or-location-token"></a>Przekazywanie tokenu VPP firmy Apple lub tokenu lokalizacji

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Wybierz kolejno pozycje **Administracja dzierżawą** > **Łączniki i tokeny** > **Tokeny VPP firmy Apple**.
4. W okienku z listą tokenów programu VPP wybierz pozycję **Utwórz**.
5. W okienku **Utwórz token programu VPP** określ następujące informacje:
    - **Plik tokenu programu VPP** — jeśli jeszcze tego nie zrobiono, zarejestruj się w programie Apple Business Manager lub Apple School Manager. Po zarejestrowaniu się pobierz token VPP firmy Apple dla swojego konta i wybierz go tutaj.
    - **Identyfikator firmy Apple** — wprowadź zarządzany identyfikator Apple ID dla konta skojarzonego z przekazanym tokenem.
    - **Przejmij kontrolę nad tokenem z innego oprogramowania MDM** — ustawienie tej opcji na wartość **Tak** umożliwia ponowne przypisanie tokenu do usługi Intune z innego rozwiązania typu MDM.
    - **Nazwa tokenu** — pole administracyjne służące do ustawiania nazwy tokenu.    
    - **Kraj/region** — wybierz sklep krajowy/regionalny programu VPP.  Usługa Intune synchronizuje aplikacje VPP ze sklepu w danym kraju/regionie umożliwiającego korzystanie z programu zakupów zbiorczych zgodnie ze wszystkimi ustawieniami regionalnymi.
        > [!WARNING]  
        > Zmiana kraju/regionu spowoduje zaktualizowanie metadanych aplikacji i adresu URL sklepu App Store przy następnej synchronizacji z usługą firmy Apple w przypadku aplikacji utworzonych za pomocą tego tokenu. Jeśli aplikacja nie istnieje w nowym sklepie krajowym/regionalnym, nie zostanie zaktualizowana.

    - **Typ konta programu VPP** — wybierz opcję **Biznes** lub **Edukacja**.
    - **Aktualizacje automatyczne aplikacji** — wybierz pozycję **Wł.** lub **Wył.** , aby włączyć aktualizacje automatyczne. Po włączeniu usługa Intune wykrywa aktualizacje aplikacji VPP w sklepie z aplikacjami i automatycznie wypycha je do urządzenia po jego zaewidencjonowaniu. 
        
        > [!NOTE] 
        > Automatyczne aktualizacje aplikacji dla aplikacji VPP firmy Apple będą automatycznie aktualizować tylko aplikacje wdrażane za pomocą intencji instalacji **Wymagana**. W przypadku aplikacji wdrożonych za pomocą intencji instalacji **Dostępna** automatyczna aktualizacja generuje dla administratora IT komunikat o stanie informujący o dostępności nowej wersji aplikacji. Ten komunikat o stanie można wyświetlić, wybierając aplikację, a następnie pozycję Stan instalacji urządzenia i sprawdzając pozycję Szczegóły stanu.  

    - **Zezwalam firmie Microsoft na wysyłanie informacji o użytkowniku i urządzeniu do firmy Apple.** — Aby kontynuować, musisz wybrać pozycję **Zgadzam się**. Aby sprawdzić, jakie dane firma Microsoft wysyła do firmy Apple, zobacz temat [Dane wysyłane przez usługę Intune do firmy Apple](~/protect/data-intune-sends-to-apple.md).

6. Gdy wszystko będzie gotowe, wybierz pozycję **Utwórz**. Token zostanie wyświetlony na liście w okienku tokenów.

## <a name="synchronize-a-vpp-token"></a>Synchronizowanie tokenu programu VPP
Możesz synchronizować nazwy aplikacji, metadane i informacje o licencji dla zakupionych aplikacji w usłudze Intune, wybierając pozycję **Synchronizuj** dla wybranego tokenu.

## <a name="assign-a-volume-purchased-app"></a>Przypisywanie aplikacji nabytej w ramach programu zakupów zbiorczych

1. Wybierz pozycję **Aplikacje** > **Wszystkie aplikacje**.
2. W okienku z listą aplikacji wybierz aplikację, którą chcesz przypisać, a następnie wybierz pozycję **Przypisania**.
3. W okienku **Nazwa aplikacji** - **Przypisania** wybierz pozycję **Dodaj grupy**, a następnie w okienku **Dodawanie grup** wybierz pozycję **Typ przypisania** i wybierz grupy użytkowników lub urządzeń usługi Azure AD, do których chcesz przypisać aplikację.
5. Dla każdej wybranej grupy wybierz następujące ustawienia:
    - **Typ** — wybierz, czy aplikacja będzie **dostępna** (użytkownicy końcowi mogą instalować aplikację z Portalu firmy), czy **wymagana** (aplikacja zostanie automatycznie pobrana i zainstalowana na urządzeniach użytkowników końcowych).
    - **Typ licencji** — wybierz **Licencjonowanie na użytkownika** lub **Licencjonowanie na urządzenie**.
6. Gdy wszystko będzie gotowe, wybierz pozycję **Zapisz**.


>[!NOTE]
>Dostępna intencja wdrożenia nie jest obsługiwane w przypadku grup urządzeń, obsługiwane są tylko grupy użytkowników. Wyświetlona lista aplikacji jest skojarzona z tokenem. Jeśli dana aplikacja jest skojarzona z wieloma tokenami VPP, zostanie ona wyświetlona wiele razy (po jednym razie dla każdego tokenu).

> [!NOTE]  
> Usługa Intune (ani żadne inne rozwiązanie do zarządzania urządzeniami przenośnymi) w rzeczywistości nie instaluje aplikacji programu VPP. Zamiast tego usługa Intune nawiązuje połączenie z kontem programu VPP i informuje firmę Apple, które licencje aplikacji mają zostać przypisane do których urządzeń. Następnie rzeczywista instalacja jest obsługiwana przez firmę Apple i urządzenie.
> 
> [Apple MDM Protocol Reference (Dokumentacja protokołu MDM firmy Apple), strona 135](https://developer.apple.com/business/documentation/MDM-Protocol-Reference.pdf)

## <a name="end-user-prompts-for-vpp"></a>Monity dotyczące programu VPP dla użytkowników końcowych

Użytkownik końcowy otrzymuje monity dotyczące instalacji aplikacji programu VPP w wielu scenariuszach. W poniższej tabeli objaśniono każdą sytuację:

| # | Scenariusz                                | Zaproszenie do programu VPP firmy Apple                              | Monit dotyczący instalacji aplikacji | Monit o podanie identyfikatora Apple ID |
|---|--------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------|-----------------------------------|
| 1 | Model BYOD — licencja użytkownika (nie urządzenie rejestrowane przez użytkownika)                             | T                                                                                               | T                                           | T                                 |
| 2 | Firma — licencja użytkownika (urządzenie nienadzorowane)     | T                                                                                               | T                                           | T                                 |
| 3 | Firma — licencja użytkownika (urządzenie nadzorowane)         | T                                                                                               | N                                           | T                                 |
| 4 | Model BYOD — licencja urządzenia                           | N                                                                                               | T                                           | N                                 |
| 5 | Firma — licencja urządzenia (urządzenie nienadzorowane)                           | N                                                                                               | T                                           | N                                 |
| 6 | Firma — licencja urządzenia (urządzenie nadzorowane)                           | N                                                                                               | N                                           | N                                 |
| 7 | Tryb kiosku (urządzenie nadzorowane) — licencja urządzenia | N                                                                                               | N                                           | N                                 |
| 8 | Tryb kiosku (urządzenie nadzorowane) — licencja użytkownika   | --- | ---                                          | ---                                |

> [!Note]  
> Nie zaleca się przypisywania aplikacji programu VPP do urządzeń w trybie kiosku przy użyciu licencji użytkownika.

## <a name="revoking-app-licenses"></a>Odwoływanie licencji aplikacji

Można odwołać wszystkie skojarzone licencje aplikacji systemu iOS lub macOS programu Volume Purchase Program (VPP) na podstawie danego urządzenia, użytkownika lub aplikacji.  Istnieją jednak pewne różnice między platformami iOS i macOS. 

|   | iOS | macOS |
|-----|------------------|----------------|
| **Usuwanie przypisania aplikacji** | Gdy usuniesz aplikację przypisaną do użytkownika, usługa Intune odzyska licencję użytkownika lub urządzenia i odinstaluje aplikację z urządzenia. | Gdy usuniesz aplikację przypisaną do użytkownika, usługa Intune odzyska licencję użytkownika lub urządzenia. Aplikacja nie zostanie odinstalowana z urządzenia. |
| **Odwoływanie licencji aplikacji** | Odwoływanie licencji aplikacji polega na odzyskiwaniu licencji aplikacji od użytkownika lub urządzenia. Musisz zmienić przypisanie na **Odinstaluj**, aby usunąć aplikację z urządzenia. | Odwoływanie licencji aplikacji polega na odzyskiwaniu licencji aplikacji od użytkownika lub urządzenia. Aplikacja systemu macOS z odwołaną licencją pozostaje na urządzeniu i można jej używać, ale nie można jej zaktualizować do czasu ponownego przypisania licencji do użytkownika lub urządzenia. Zgodnie z zasadami firmy Apple takie aplikacje są usuwane po 30-dniowym okresie prolongaty. Firma Apple nie zapewnia jednak sposobu usunięcia takiej aplikacji za pomocą usługi Intune za pośrednictwem akcji odinstalowywania przypisania.

>[!NOTE]
> - Usługa Intune odzyskuje licencje aplikacji, kiedy pracownik opuści firmę i przestanie być członkiem grup usługi AAD.
> - W przypadku przypisywania nabytej aplikacji z intencją **Odinstalowywanie** usługa Intune odzyskuje licencję i odinstalowuje aplikację.
> - Licencje aplikacji nie są odzyskiwane po usunięciu urządzenia z zarządzania w usłudze Intune. 

## <a name="deleting-vpp-tokens"></a>Usuwanie tokenów programu VPP
<!-- 820879 -->  
Istnieje możliwość usunięcia tokenu programu Apple Volume Purchasing Program (VPP) przy użyciu konsoli. Może to być konieczne w przypadku występowania zduplikowanych wystąpień tokenu programu VPP. Usunięcie tokenu spowoduje również usunięcie wszelkich skojarzonych aplikacji oraz przypisania. Jednak usunięcie tokenu nie spowoduje odwołania licencji aplikacji ani odinstalowania aplikacji. 

>[!NOTE]
>Usługa Intune nie można odwołać licencji aplikacji, jeśli token zostanie usunięty. 

<!-- 820870 -->  
Aby odwołać licencję wszystkich aplikacji programu VPP dla danego tokenu programu VPP, należy najpierw odwołać wszystkie licencje aplikacji skojarzone z tokenem, a następnie usunąć token.

## <a name="renewing-app-licenses"></a>Odnawianie licencji aplikacji

Token VPP firmy Apple można odnowić, pobierając nowy token z portalu programu Apple Business Manager lub Apple School Manager i aktualizując istniejący token w usłudze Intune.

## <a name="deleting-a-vpp-app"></a>Usuwanie aplikacji VPP

Obecnie nie można usunąć aplikacji programu VPP systemu iOS z usługi Microsoft Intune.

## <a name="assigning-custom-role-permissions-for-vpp"></a>Przypisywanie uprawnień roli niestandardowej dla programu VPP

Dostęp do tokenów i aplikacji VPP firmy Apple można kontrolować niezależnie przy użyciu uprawnień przypisanych do niestandardowych ról administratorów w usłudze Intune.

* Aby umożliwić roli niestandardowej usługi Intune zarządzanie tokenami programu VPP firmy Apple, w obszarze **Aplikacje** > **Tokeny VPP firmy Apple** przypisz uprawnienia dla elementu **Aplikacje zarządzane**.
* Aby umożliwić roli niestandardowej usługi Intune zarządzanie aplikacjami kupionymi przy użyciu tokenów VPP systemu iOS, w obszarze **Aplikacje** > **Wszystkie aplikacje** przypisz uprawnienia dla elementu **Aplikacje mobilne**. 

## <a name="additional-information"></a>Dodatkowe informacje

Firma Apple zapewnia bezpośrednią pomoc dotyczącą tworzenia i odnawiania tokenów programu VPP. Aby uzyskać więcej informacji, zobacz artykuł [Dystrybucja zawartości wśród użytkowników za pośrednictwem programu zakupów grupowych (VPP)](https://go.microsoft.com/fwlink/?linkid=2014661) jako część dokumentacji firmy Apple. 

Jeśli w portalu usługi Intune jest wskazana pozycja **Przypisane do zewnętrznego MDM**, wówczas Ty (administrator) musisz usunąć token VPP MDM od innej firmy przed użyciem tokenu VPP w usłudze Intune.

## <a name="frequently-asked-questions"></a>Często zadawane pytania

### <a name="how-many-tokens-can-i-upload"></a>Ile tokenów mogę przekazać?
Możesz przekazać do 3000 tokenów w usłudze Intune.

### <a name="how-long-does-the-portal-take-to-update-the-license-count-once-an-app-is-installed-or-removed-from-the-device"></a>Jak długo trwa aktualizowanie liczby licencji w portalu po zainstalowaniu aplikacji na urządzeniu lub usunięciu jej z urządzenia?
Licencja powinna zostać zaktualizowana w ciągu kilku godzin po zainstalowaniu lub odinstalowaniu aplikacji. Należy pamiętać, że jeśli użytkownik końcowy usunie aplikację z urządzenia, licencja będzie nadal przypisana do tego użytkownika lub urządzenia.

### <a name="is-it-possible-to-oversubscribe-an-app-and-if-so-in-what-circumstance"></a>Czy możliwe jest nadsubskrybowanie aplikacji, a jeśli tak, to w jakich okolicznościach?
Tak. Administrator usługi Intune może nadsubskrybować aplikację. Może to mieć na przykład miejsce, jeśli administrator zakupi 100 licencji dla aplikacji XYZ, a następnie przeznaczy aplikację dla grupy zawierającej 500 elementów członkowskich. Licencja zostanie przypisana do pierwszych 100 elementów członkowskich (użytkowników lub urządzeń), a dla pozostałych przypisanie licencji zakończy się niepowodzeniem.


## <a name="next-steps"></a>Następne kroki

Informacje przydatne do monitorowania przypisań aplikacji znajdują się w artykule [How to monitor apps](apps-monitor.md) (Jak monitorować aplikacje).

Informacje przydatne do rozwiązywania problemów z aplikacjami znajdują się w artykule [Rozwiązywanie problemów z aplikacjami](~/apps/troubleshoot-app-install.md).
