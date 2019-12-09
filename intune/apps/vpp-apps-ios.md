---
title: Zarządzanie aplikacjami firmy Apple nabytymi w ramach zakupów zbiorczych
titleSuffix: Microsoft Intune
description: Informacje o synchronizowaniu aplikacji nabytych w ramach zakupów zbiorczych w sklepie App Store z aplikacjami dla systemu iOS i macOS z usługą Microsoft Intune oraz o zarządzaniu ich użyciem i jego śledzeniu.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
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
ms.openlocfilehash: eed0b8a74e69bc1552ae3e2badf485364ba37e94
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563821"
---
# <a name="how-to-manage-ios-and-macos-apps-purchased-through-apple-volume-purchase-program-with-microsoft-intune"></a>Jak w usłudze Microsoft Intune zarządzać aplikacjami dla systemów iOS i macOS, które zostały zakupione w ramach programu zakupów zbiorczych firmy Apple


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Firma Apple umożliwia zakup wielu licencji dla aplikacji, które mają być uruchamiane na urządzeniach firmowych z systemami iOS i macOS. Zakup wielu kopii ułatwia efektywne zarządzanie aplikacjami w firmie.

Usługa Microsoft Intune ułatwia zarządzanie wieloma kopiami aplikacji kupionych za pośrednictwem tego programu, ponieważ umożliwia:

- Raportowanie informacji o licencji ze sklepu z aplikacjami.
- Śledzenie liczby używanych licencji.
- Pomoc w zapobieganiu instalacji większej liczby kopii aplikacji niż posiadana.

Istnieją dwie metody przypisywania aplikacji nabytych w ramach zakupów zbiorczych:

## <a name="device-licensing"></a>Licencjonowanie na urządzenie

W przypadku przypisania aplikacji do urządzeń używana jest jedna licencja aplikacji, która pozostaje skojarzona z urządzeniem, do którego została przypisana.

W przypadku przypisania aplikacji nabytych w ramach zakupów zbiorczych do urządzeń użytkownik końcowy urządzenia nie musi podawać identyfikatora Apple ID, aby uzyskać dostęp do sklepu.

## <a name="user-licensing"></a>Licencjonowanie na użytkownika

W przypadku przypisania aplikacji do użytkownika używana jest jedna licencja aplikacji, która jest skojarzona z użytkownikiem. Aplikacja może być uruchamiana na maksymalnie 5 urządzeniach, które należą do użytkownika (limit urządzeń jest kontrolowany przez firmę Apple).

W przypadku przypisania aplikacji nabytych w ramach zakupów zbiorczych do użytkowników każdy użytkownik końcowy musi mieć prawidłowy i unikatowy identyfikator Apple ID, aby uzyskać dostęp do sklepu z aplikacjami.

Oprócz tego przy użyciu usługi Intune można także synchronizować książki kupione w sklepie programu Apple Volume Purchase Program (VPP) oraz zarządzać nimi i przypisywać je do urządzeń z systemem iOS. Aby uzyskać więcej informacji, zobacz [Jak zarządzać książkami elektronicznymi dla systemu iOS, które zostały zakupione w ramach programu zakupów zbiorczych](vpp-ebooks-ios.md).

## <a name="manage-volume-purchased-apps-for-ios-and-macos-devices"></a>Zarządzanie aplikacjami nabytymi w ramach zakupów zbiorczych na urządzeniach z systemem iOS i macOS

### <a name="supports-apple-volume-purchase-program-volume-purchased-apps"></a>Obsługuje aplikacje zakupione zbiorczo w ramach programu Apple Volume Purchase Program

Wiele licencji dla aplikacji systemów iOS i macOS można kupić za pośrednictwem programu [Apple Volume Purchase Program for Business](https://www.apple.com/business/vpp/) lub [Apple Volume Purchase Program for Education](https://volume.itunes.apple.com/us/store). Ten proces obejmuje skonfigurowanie konta programu VPP firmy Apple w witrynie sieci Web firmy Apple i przekazanie tokenu VPP firmy Apple do usługi Intune.  Następnie można zsynchronizować dane zakupu zbiorczego z usługą Intune i śledzić użycie aplikacji nabytych w ramach zakupu zbiorczego.

### <a name="supports-business-to-business-volume-purchased-apps"></a>Obsługuje aplikacje kupione zbiorczo w ramach współpracy między firmami

Ponadto deweloperzy innych firm mogą również prywatnie dystrybuować aplikacje do autoryzowanych członków programu Volume Purchase Program for Business określonych w usłudze App Store Connect. Ci członkowie programu VPP for Business mogą zalogować się do sklepu Volume Purchase Program App Store i zakupić ich aplikacje. Aplikacje programu VPP for Business zakupione przez użytkownika końcowego zsynchronizują się z ich dzierżawami usługi Intune.

## <a name="before-you-start"></a>Przed rozpoczęciem
Przed rozpoczęciem należy uzyskać token VPP od firmy Apple i przekazać go do konta usługi Intune. Ponadto należy zapoznać się z następującymi kwestiami:

* Z kontem usługi Intune można skojarzyć wiele tokenów VPP.
* Jeśli poprzednio korzystano z tokenu VPP w ramach innego produktu, należy wygenerować nowy, aby korzystać z usługi Intune.
* Każdy token jest ważny przez jeden rok.
* Domyślnie usługa Intune przeprowadza synchronizację z usługą Apple VPP dwa razy dziennie. W dowolnym momencie można uruchomić ręczną synchronizację.
* Przed rozpoczęciem korzystania z programu VPP firmy Apple przy użyciu usługi Intune należy usunąć wszystkie istniejące konta usługi VPP utworzone przy użyciu innych dostawców zarządzania urządzeniami przenośnymi. Usługa Intune nie synchronizuje tych kont użytkowników z usługą Intune ze względów bezpieczeństwa. Usługa Intune synchronizuje tylko dane z usługi VPP firmy Apple, która została utworzona przez usługę Intune.
* Program Device Enrollment Profile (DEP) firmy Apple automatyzuje rejestrację zarządzania urządzeniami przenośnymi (MDM). Przy użyciu programu DEP możesz skonfigurować urządzenia w przedsiębiorstwie bez dotykania ich. Możesz zarejestrować się w programie DEP przy użyciu tego samego konta agenta programu co dla programu VPP firmy Apple. Identyfikator programu Apple Deployment Program jest unikatowy dla programów wymienionych w witrynie internetowej [Programy wdrożenia](https://deploy.apple.com) i nie można go używać do logowania się do usług firmy Apple, takich jak sklep iTunes.
* Jeśli aplikacje VPP zostały przypisane do użytkowników lub urządzeń (z koligacją użytkowników) za pomocą modelu licencjonowania użytkowników, każdy użytkownik usługi Intune musi zostać skojarzony z unikatowym identyfikatorem Apple ID lub adresem e-mail, aby mógł zaakceptować warunki i postanowienia firmy Apple na swoim urządzeniu.
* Podczas konfigurowania urządzenia dla nowego użytkownika usługi Intune skonfiguruj je przy użyciu unikatowego identyfikatora Apple ID lub adresu e-mail tego użytkownika. Identyfikator Apple ID lub adres e-mail stanowią z użytkownikiem usługi Intune unikatową parę i mogą być używane na maksymalnie pięciu urządzeniach.
* W danym momencie token VPP może być używany tylko w ramach jednego konta usługi Intune. Nie używaj tego samego tokenu VPP dla wielu dzierżaw usługi Intune.

>[!IMPORTANT]
>Po zaimportowaniu tokenu VPP do usługi Intune nie należy importować tego samego tokenu do żadnego innego rozwiązania do zarządzania urządzeniami. Może to spowodować utratę przypisania licencji i rekordów użytkowników.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Aby uzyskać i przekazać token usługi VPP firmy Apple

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Wybierz kolejno pozycje **Administracja dzierżawą** > **Łączniki i tokeny** > **Tokeny VPP firmy Apple**.
4. W okienku z listą tokenów programu VPP wybierz pozycję **Utwórz**.
5. W okienku **Utwórz token programu VPP** określ następujące informacje:
    - **Plik tokenu programu VPP** — jeśli nie jesteś jeszcze zarejestrowanym członkiem programu Volume Purchase Program for Business lub Volume Purchase Program for Education, zarejestruj się. Po zarejestrowaniu się pobierz token VPP firmy Apple dla swojego konta i wybierz go tutaj.
    - **Identyfikator firmy Apple** — wprowadź identyfikator firmy Apple dla konta skojarzonego z programem zakupów zbiorczych.
    - **Przejmij kontrolę nad tokenem z innego oprogramowania MDM** — ustawienie tej opcji na wartość **Tak** umożliwia ponowne przypisanie tokenu do usługi Intune z innego oprogramowania MDM.
    - **Nazwa tokenu** — pole administracyjne służące do ustawiania nazwy tokenu.    
    - **Kraj/region** — wybierz sklep krajowy/regionalny programu VPP.  Usługa Intune synchronizuje aplikacje VPP ze sklepu w danym kraju/regionie umożliwiającego korzystanie z programu zakupów zbiorczych zgodnie ze wszystkimi ustawieniami regionalnymi.
        > [!WARNING]  
        > Zmiana kraju/regionu spowoduje zaktualizowanie metadanych aplikacji i adresu URL sklepu przy następnej synchronizacji z usługą firmy Apple w przypadku aplikacji utworzonych za pomocą tego tokenu. Jeśli aplikacja nie istnieje w nowym sklepie krajowym/regionalnym, nie zostanie zaktualizowana.

    - **Typ konta programu VPP** — wybierz opcję **Biznes** lub **Edukacja**.
    - **Aktualizacje automatyczne aplikacji** — wybierz pozycję **Wł.** lub **Wył.** , aby włączyć aktualizacje automatyczne. Po włączeniu usługa Intune wykrywa aktualizacje aplikacji VPP w sklepie z aplikacjami i automatycznie wypycha je do urządzenia po jego zaewidencjonowaniu. Automatyczne aktualizacje aplikacji dla aplikacji VPP firmy Apple będą automatycznie aktualizować tylko aplikacje wdrażane za pomocą intencji instalacji **Wymagana**. W przypadku aplikacji wdrożonych za pomocą intencji instalacji **Dostępna** automatyczna aktualizacja generuje dla administratora IT komunikat o stanie informujący o dostępności nowej wersji aplikacji. Ten komunikat o stanie można wyświetlić, wybierając aplikację, a następnie pozycję Stan instalacji urządzenia i sprawdzając pozycję Szczegóły stanu. Ponadto użytkownik zobaczy aplikację jako nie zainstalowaną w witrynie Portal firmy, nawet jeśli jest zainstalowana wcześniejsza wersja aplikacji. W takim przypadku, aby zainstalować nowszą wersję aplikacji, użytkownik może ponownie zainstalować aplikację, klikając pozycję **Zainstaluj** na ekranie szczegółów aplikacji w aplikacji Portal firmy.

        > [!NOTE]
        > Automatyczne aktualizacje aplikacji działają zarówno w przypadku aplikacji licencjonowanych dla urządzenia, jak i użytkownika, dla systemu iOS w wersji 11.0 i nowszej lub macOS w wersji 10.12 i nowszej.

    - **Zezwalam firmie Microsoft na wysyłanie informacji o użytkowniku i urządzeniu do firmy Apple.** — Aby kontynuować, musisz wybrać pozycję **Zgadzam się**. Aby sprawdzić, jakie dane firma Microsoft wysyła do firmy Apple, zobacz temat [Dane wysyłane przez usługę Intune do firmy Apple](~/protect/data-intune-sends-to-apple.md).

6. Gdy wszystko będzie gotowe, wybierz pozycję **Utwórz**.

Token zostanie wyświetlony na liście w okienku tokenów.

Dane przechowywane przez firmę Apple można w dowolnym momencie zsynchronizować z usługą Intune, wybierając pozycję **Synchronizuj teraz**.

## <a name="to-assign-a-volume-purchased-app"></a>Wdrażanie aplikacji nabytej w ramach programu zakupów zbiorczych

1. Wybierz kolejno pozycje **Aplikacje** > **Wszystkie aplikacje**.
2. W okienku z listą aplikacji wybierz aplikację, którą chcesz przypisać, a następnie wybierz pozycję **Przypisania**.
3. W okienku ***Nazwa aplikacji*** - **Przypisania** wybierz pozycję **Dodaj grupy**, a następnie w okienku **Dodawanie grup** wybierz pozycję **Typ przypisania** i wybierz grupy użytkowników lub urządzeń usługi Azure AD, do których chcesz przypisać aplikację.
5. Dla każdej wybranej grupy wybierz następujące ustawienia:
    - **Typ** — wybierz, czy aplikacja będzie **dostępna** (użytkownicy końcowi mogą instalować aplikację z Portalu firmy), czy **wymagana** (aplikacja zostanie automatycznie pobrana i zainstalowana na urządzeniach użytkowników końcowych).
    - **Typ licencji** — wybierz **Licencjonowanie na użytkownika** lub **Licencjonowanie na urządzenie**.
6. Gdy wszystko będzie gotowe, wybierz pozycję **Zapisz**.


>[!NOTE]
>Dostępna intencja wdrożenia nie jest obsługiwane w przypadku grup urządzeń, obsługiwane są tylko grupy użytkowników. Wyświetlona lista aplikacji jest skojarzona z tokenem. Jeśli dana aplikacja jest skojarzona z wieloma tokenami VPP, zostanie ona wyświetlona wiele razy (po jednym razie dla każdego tokenu).

## <a name="end-user-prompts-for-vpp"></a>Monity dotyczące programu VPP dla użytkowników końcowych

Użytkownik końcowy otrzymuje monity dotyczące instalacji aplikacji programu VPP w wielu scenariuszach. W poniższej tabeli objaśniono każdą sytuację:

| # | Scenariusz                                | Zaproszenie do programu VPP firmy Apple                              | Monit dotyczący instalacji aplikacji | Monit o podanie identyfikatora Apple ID |
|---|--------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------|-----------------------------------|
| 1 | Model BYOD — licencja użytkownika                             | T                                                                                               | T                                           | T                                 |
| 2 | Firma — licencja użytkownika (urządzenie nienadzorowane)     | T                                                                                               | T                                           | T                                 |
| 3 | Firma — licencja użytkownika (urządzenie nadzorowane)         | T                                                                                               | N                                           | T                                 |
| 4 | Model BYOD — licencja urządzenia                           | N                                                                                               | T                                           | N                                 |
| 5 | Firma — licencja urządzenia (urządzenie nienadzorowane)                           | N                                                                                               | T                                           | N                                 |
| 6 | Firma — licencja urządzenia (urządzenie nadzorowane)                           | N                                                                                               | N                                           | N                                 |
| 7 | Tryb kiosku (urządzenie nadzorowane) — licencja urządzenia | N                                                                                               | N                                           | N                                 |
| 8 | Tryb kiosku (urządzenie nadzorowane) — licencja użytkownika   | --- | ---                                          | ---                                |

> [!Note]  
> Nie zaleca się przypisywania aplikacji programu VPP do urządzeń w trybie kiosku przy użyciu licencji użytkownika programu VPP.

## <a name="revoking-app-licenses"></a>Odwoływanie licencji aplikacji

Można odwołać wszystkie skojarzone licencje aplikacji systemu iOS lub macOS programu Volume Purchase Program (VPP) na podstawie danego urządzenia, użytkownika lub aplikacji.  Istnieją jednak pewne różnice między platformami iOS i macOS. 

### <a name="revoking-app-licenses-on-ios"></a>Odwoływanie licencji aplikacji w systemie iOS
Możesz powiadomić użytkowników, że aplikacja nie jest już do nich przypisana. Jednak odwołanie licencji aplikacji nie spowoduje odinstalowania powiązanej aplikacji VPP z urządzenia. Aby odinstalować aplikację VPP i odzyskać licencję aplikacji przypisaną do użytkownika lub urządzenia, musisz zmienić akcję przypisywania na **Odinstaluj**. Gdy usuniesz aplikację przypisaną do użytkownika, usługa Intune odzyska licencję użytkownika lub urządzenia i odinstaluje aplikację z urządzenia. Liczba odzyskanych licencji zostanie odzwierciedlona w węźle **Licencjonowane aplikacje** w obciążeniu **Aplikacje** usługi Intune. Po odinstalowaniu aplikacji VPP i odzyskaniu licencji można przypisać tę licencję do innego użytkownika lub urządzenia.


### <a name="revoking-app-licenses-on-macos"></a>Odwoływanie licencji aplikacji w systemie macOS
Odwołanie licencji aplikacji nie spowoduje odinstalowania aplikacji VPP z urządzenia. Gdy odwołasz licencję aplikacji przypisaną do użytkownika, usługa Intune odzyska licencję użytkownika lub urządzenia. Aplikacja systemu macOS z odwołaną licencją pozostaje na urządzeniu i można jej używać, ale nie można jej zaktualizować do czasu ponownego przypisania licencji do użytkownika lub urządzenia. Zgodnie z zasadami firmy Apple takie aplikacje są usuwane po 30-dniowym okresie prolongaty. Firma Apple nie zapewnia jednak sposobu usunięcia takiej aplikacji za pomocą usługi Intune przez kliknięcie przycisku **Odinstaluj**. Można jednak przypisać odzyskaną licencję aplikacji do innego użytkownika lub urządzenia.

>[!NOTE]
>Kiedy pracownik opuści firmę i przestanie być członkiem grupy w usłudze AAD, usługa Intune pobierze wszystkie przypisane do użytkownika licencje aplikacji VPP dla systemu iOS i macOS.

## <a name="deleting-vpp-tokens"></a>Usuwanie tokenów programu VPP
<!-- 820879 -->  
Istnieje możliwość usunięcia tokenu programu Apple Volume Purchasing Program (VPP) przy użyciu konsoli. Może to być konieczne w przypadku występowania zduplikowanych wystąpień tokenu programu VPP. Usunięcie tokenu spowoduje również usunięcie wszelkich skojarzonych aplikacji oraz przypisania. Jednak usunięcie tokenu nie spowoduje odwołania licencji aplikacji ani odinstalowania aplikacji. 

>[!NOTE]
>Usługa Intune nie można odwołać licencji aplikacji, jeśli token zostanie usunięty. 

<!-- 820870 -->  
Aby odwołać licencję wszystkich aplikacji programu VPP dla danego tokenu programu VPP, należy najpierw odwołać wszystkie licencje aplikacji skojarzone z tokenem, a następnie usunąć token.

## <a name="renewing-app-licenses"></a>Odnawianie licencji aplikacji

Token VPP firmy Apple można odnowić, pobierając nowy token z portalu programu Apple Volume Purchase Program i aktualizując istniejący token w usłudze Intune.

## <a name="deleting-a-vpp-app"></a>Usuwanie aplikacji VPP

Obecnie nie można usunąć aplikacji programu VPP systemu iOS z usługi Microsoft Intune.

## <a name="assigning-custom-role-permissions-for-vpp"></a>Przypisywanie uprawnień roli niestandardowej dla programu VPP

Dostęp do tokenów i aplikacji VPP firmy Apple można kontrolować niezależnie przy użyciu uprawnień przypisanych do niestandardowych ról administratorów w usłudze Intune.

* Aby umożliwić roli niestandardowej usługi Intune zarządzanie tokenami programu VPP firmy Apple, w obszarze **Aplikacje** > **Tokeny VPP firmy Apple** przypisz uprawnienia dla elementu **Aplikacje zarządzane**.
* Aby umożliwić roli niestandardowej usługi Intune zarządzanie aplikacjami kupionymi przy użyciu tokenów VPP systemu iOS, w obszarze **Aplikacje** > **Wszystkie aplikacje** przypisz uprawnienia dla elementu **Aplikacje mobilne**. 

## <a name="additional-information"></a>Dodatkowe informacje

Gdy użytkownik mający kwalifikujące się urządzenie spróbuje zainstalować aplikację VPP na urządzeniu po raz pierwszy, zostanie poproszony o dołączenie do programu Apple Volume Purchase Program. Jest to konieczne, aby instalacja aplikacji mogła być kontynuowana. Zaproszenie do dołączenia do programu Apple Volume Purchase program wymaga, aby użytkownik mógł używać aplikacji App Store na urządzeniu z systemem iOS lub macOS. Jeśli ustawiono zasady wyłączające aplikację sklepu App Store, oparte na użytkowniku licencje na aplikacje VPP nie będą działać. Aby rozwiązać ten problem, należy zezwolić na aplikację sklepu App Store przez usunięcie zasad lub zastosować licencje oparte na urządzeniach.

Firma Apple zapewnia bezpośrednią pomoc dotyczącą tworzenia i odnawiania tokenów programu VPP. Aby uzyskać więcej informacji, zobacz artykuł [Dystrybucja zawartości wśród użytkowników za pośrednictwem programu zakupów grupowych (VPP)](https://go.microsoft.com/fwlink/?linkid=2014661) jako część dokumentacji firmy Apple. 

Jeśli w portalu usługi Intune jest wskazana pozycja **Przypisane do zewnętrznego MDM**, wówczas Ty (administrator) musisz usunąć token VPP MDM od innej firmy przed użyciem tokenu VPP w usłudze Intune.

## <a name="frequently-asked-questions"></a>Często zadawane pytania

### <a name="how-long-does-the-portal-take-to-update-the-license-count-once-an-app-is-installed-or-removed-from-the-device"></a>Jak długo trwa aktualizowanie liczby licencji w portalu po zainstalowaniu aplikacji na urządzeniu lub usunięciu jej z urządzenia?
Licencja powinna zostać zaktualizowana w ciągu kilku godzin po zainstalowaniu lub odinstalowaniu aplikacji. Należy pamiętać, że jeśli użytkownik końcowy usunie aplikację z urządzenia, licencja będzie nadal przypisana do tego użytkownika lub urządzenia.

### <a name="is-it-possible-to-oversubscribe-an-app-and-if-so-in-what-circumstance"></a>Czy możliwe jest nadsubskrybowanie aplikacji, a jeśli tak, to w jakich okolicznościach?
Tak. Administrator usługi Intune może nadsubskrybować aplikację. Może to mieć na przykład miejsce, jeśli administrator zakupi 100 licencji dla aplikacji XYZ, a następnie przeznaczy aplikację dla grupy zawierającej 500 elementów członkowskich. Licencja zostanie przypisana do pierwszych 100 elementów członkowskich (użytkowników lub urządzeń), a dla pozostałych przypisanie licencji zakończy się niepowodzeniem.

### <a name="how-frequently-does-intune-sync-vpp-tokens-with-apple"></a>Jak często usługa Intune synchronizuje tokeny VPP z firmą Apple?
Usługa Intune synchronizuje tokeny VPP z firmą Apple dwa razy dziennie. Administrator usługi Intune może zainicjować synchronizację ręczną w obszarze **Aplikacje** > **Tokeny VPP firmy Apple**.

## <a name="next-steps"></a>Następne kroki

Informacje przydatne do monitorowania przypisań aplikacji znajdują się w artykule [How to monitor apps](apps-monitor.md) (Jak monitorować aplikacje).
