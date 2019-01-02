---
title: Zarządzanie aplikacjami dla systemu iOS nabytymi w ramach zakupów zbiorczych w usłudze Microsoft Intune
titlesuffix: ''
description: Informacje o synchronizowaniu aplikacji nabytych w ramach zakupów zbiorczych w sklepie z aplikacjami dla systemu iOS z usługą Microsoft Intune oraz o zarządzaniu ich użyciem i jego śledzeniu.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: b2ec10ec1174e5e689802d2c4f17a21de8312a15
ms.sourcegitcommit: a0db74934433226e28ffdf5d92930dafd2feceae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/12/2018
ms.locfileid: "53305968"
---
# <a name="how-to-manage-ios-apps-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Jak w usłudze Microsoft Intune zarządzać aplikacjami dla systemu iOS, które zostały zakupione w ramach programu zakupów zbiorczych


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Sklep z aplikacjami systemu iOS umożliwia zakup wielu licencji dla aplikacji, które mają być uruchamiane w firmie. Zakup wielu kopii ułatwia efektywne zarządzanie aplikacjami w firmie.

Usługa Microsoft Intune ułatwia zarządzanie wieloma kopiami aplikacji kupionych za pośrednictwem tego programu, ponieważ umożliwia:

- Raportowanie informacji o licencji ze sklepu z aplikacjami.
- Śledzenie liczby używanych licencji.
- Pomoc w zapobieganiu instalacji większej liczby kopii aplikacji niż posiadana.

Istnieją dwie metody przypisywania aplikacji nabytych w ramach zakupów zbiorczych:

### <a name="device-licensing"></a>Licencjonowanie na urządzenie

W przypadku przypisania aplikacji do urządzeń używana jest jedna licencja aplikacji, która pozostaje skojarzona z urządzeniem, do którego została przypisana.

W przypadku przypisania aplikacji nabytych w ramach zakupów zbiorczych do urządzeń użytkownik końcowy urządzenia nie musi podawać identyfikatora Apple ID, aby uzyskać dostęp do sklepu.

### <a name="user-licensing"></a>Licencjonowanie na użytkownika

W przypadku przypisania aplikacji do użytkownika używana jest jedna licencja aplikacji, która jest skojarzona z użytkownikiem. Aplikacja może być uruchamiana na wielu urządzeniach, które należą do użytkownika (z limitem kontrolowanym przez firmę Apple).

W przypadku przypisania aplikacji nabytych w ramach zakupów zbiorczych do użytkowników każdy użytkownik końcowy musi mieć prawidłowy i unikatowy identyfikator Apple ID, aby uzyskać dostęp do sklepu z aplikacjami.

Oprócz tego możesz także synchronizować książki kupione w sklepie programu Apple Volume Purchase Program (VPP) oraz zarządzać nimi i przypisywać je przy użyciu usługi Intune. Aby uzyskać więcej informacji, zobacz [Jak zarządzać książkami elektronicznymi dla systemu iOS, które zostały zakupione w ramach programu zakupów zbiorczych](vpp-ebooks-ios.md).

## <a name="manage-volume-purchased-apps-for-ios-devices"></a>Zarządzanie zbiorczo zakupionymi aplikacjami dla urządzeń z systemem iOS

### <a name="supports-apple-volume-purchase-program-volume-purchased-apps-for-ios-devices"></a>Obsługuje aplikacje dla urządzeń z systemem iOS zbiorczo zakupione w ramach programu Apple Volume Purchase Program

Wiele licencji dla aplikacji systemu iOS można kupić za pośrednictwem programu [Apple Volume Purchase Program for Business](https://www.apple.com/business/vpp/) lub [Apple Volume Purchase Program for Education](https://volume.itunes.apple.com/us/store). Ten proces obejmuje skonfigurowanie konta programu VPP firmy Apple w witrynie sieci Web firmy Apple i przekazanie tokenu VPP firmy Apple do usługi Intune.  Następnie można zsynchronizować dane zakupu zbiorczego z usługą Intune i śledzić użycie aplikacji nabytych w ramach zakupu zbiorczego.

### <a name="supports-business-to-business-volume-purchased-apps-for-ios-devices"></a>Obsługuje zbiorczo zakupione aplikacje firma-firma dla urządzeń z systemem iOS

Ponadto deweloperzy innych firm mogą również prywatnie dystrybuować aplikacje do autoryzowanych członków programu Volume Purchase Program for Business określonych w usłudze iTunes Connect. Ci członkowie programu VPP for Business mogą zalogować się do sklepu Volume Purchase Program App Store i zakupić ich aplikacje. Aplikacje programu VPP for Business zakupione przez użytkownika końcowego zsynchronizują się z ich dzierżawami usługi Intune.

## <a name="before-you-start"></a>Przed rozpoczęciem
Przed rozpoczęciem należy uzyskać token VPP od firmy Apple i przekazać go do konta usługi Intune. Ponadto należy zapoznać się z następującymi kwestiami:

* Z kontem usługi Intune można skojarzyć wiele tokenów VPP.
* Jeśli poprzednio korzystano z tokenu VPP w ramach innego produktu, należy wygenerować nowy, aby korzystać z usługi Intune.
* Każdy token jest ważny przez jeden rok.
* Domyślnie usługa Intune przeprowadza synchronizację z usługą Apple VPP dwa razy dziennie. W dowolnym momencie można uruchomić ręczną synchronizację.
* Przed rozpoczęciem korzystania z programu VPP firmy Apple przy użyciu usługi Intune należy usunąć wszystkie istniejące konta usługi VPP utworzone przy użyciu innych dostawców zarządzania urządzeniami przenośnymi. Usługa Intune nie synchronizuje tych kont użytkowników z usługą Intune ze względów bezpieczeństwa. Usługa Intune synchronizuje tylko dane z usługi VPP firmy Apple, która została utworzona przez usługę Intune.
* Usługa Intune obsługuje dodawanie maksymalnie 256 tokenów usługi VPP.
* Program Device Enrollment Profile (DEP) firmy Apple automatyzuje rejestrację zarządzania urządzeniami przenośnymi (MDM). Przy użyciu programu DEP możesz skonfigurować urządzenia w przedsiębiorstwie bez dotykania ich. Możesz zarejestrować się w programie DEP przy użyciu tego samego konta agenta programu co dla programu VPP firmy Apple. Identyfikator programu Apple Deployment Program jest unikatowy dla programów wymienionych w witrynie internetowej [Programy wdrożenia](https://deploy.apple.com) i nie można go używać do logowania się do usług firmy Apple, takich jak sklep iTunes.
* Jeśli aplikacje VPP zostały przypisane do użytkowników lub urządzeń (z koligacją użytkowników) za pomocą modelu licencjonowania użytkowników, każdy użytkownik usługi Intune musi zostać skojarzony z unikatowym identyfikatorem Apple ID lub adresem e-mail, aby mógł zaakceptować warunki i postanowienia firmy Apple na swoim urządzeniu.
* Podczas konfigurowania urządzenia dla nowego użytkownika usługi Intune skonfiguruj je przy użyciu unikatowego identyfikatora Apple ID lub adresu e-mail tego użytkownika. Identyfikator Apple ID lub adres e-mail stanowią z użytkownikiem usługi Intune unikatową parę i mogą być używane na maksymalnie pięciu urządzeniach.
* W danym momencie token VPP może być używany tylko w ramach jednego konta usługi Intune. Nie używaj tego samego tokenu VPP dla wielu dzierżaw usługi Intune.

>[!IMPORTANT]
>Po zaimportowaniu tokenu VPP do usługi Intune nie należy importować tego samego tokenu do żadnego innego rozwiązania do zarządzania urządzeniami. Może to spowodować utratę przypisania licencji i rekordów użytkowników.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Aby uzyskać i przekazać token usługi VPP firmy Apple

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3.  W okienku **Intune** wybierz pozycję **Aplikacje klienckie** > **Tokeny programu VPP systemu iOS** w obszarze **Konfiguracja**.
4.  W okienku z listą tokenów programu VPP wybierz pozycję **Utwórz**.
5. W okienku **Utwórz token programu VPP** określ następujące informacje:
    - **Plik tokenu programu VPP** — jeśli nie jesteś jeszcze zarejestrowanym członkiem programu Volume Purchase Program for Business lub Volume Purchase Program for Education, zarejestruj się. Po zarejestrowaniu się pobierz token VPP firmy Apple dla swojego konta i wybierz go tutaj.
    - **Identyfikator firmy Apple** — wprowadź identyfikator firmy Apple dla konta skojarzonego z programem zakupów zbiorczych.
    - **Kraj/region** — wybierz sklep krajowy programu VPP.  Usługa Intune synchronizuje aplikacje VPP z określonego krajowego sklepu umożliwiającego korzystanie z programu zakupów zbiorczych zgodnie ze wszystkimi ustawieniami regionalnymi.
        > [!WARNING]  
        > Zmiana kraju spowoduje zaktualizowanie metadanych aplikacji i adresu URL sklepu przy następnej synchronizacji z usługą firmy Apple w przypadku aplikacji utworzonych za pomocą tego tokenu. Jeśli aplikacja nie istnieje w nowym sklepie krajowym, nie zostanie zaktualizowana.

    - **Typ konta programu VPP** — wybierz opcję **Biznes** lub **Edukacja**.
    - **Aktualizacje automatyczne aplikacji** — wybierz pozycję **Wł.** lub **Wył.**, aby włączyć aktualizacje automatyczne. Po włączeniu usługa Intune wykrywa aktualizacje aplikacji VPP w sklepie z aplikacjami i automatycznie wypycha je do urządzenia po jego zaewidencjonowaniu. Automatyczne aktualizacje aplikacji dla aplikacji VPP firmy Apple będą automatycznie aktualizować tylko aplikacje wdrażane za pomocą intencji instalacji **Wymagana**. W przypadku aplikacji wdrożonych za pomocą intencji instalacji **Dostępna** automatyczna aktualizacja generuje dla Ciebie (administratora) powiadomienie o dostępności nowej wersji aplikacji. Użytkownik musi kliknąć przycisk Zainstaluj, aby zainstalować nowszą wersję aplikacji. Ponadto użytkownik zobaczy aplikację jako nie zainstalowaną w witrynie Portal firmy, nawet jeśli jest zainstalowana wcześniejsza wersja aplikacji. W takim przypadku użytkownik może ponownie zainstalować aplikację.
    
        > [!NOTE]
        > Automatyczne aktualizacje aplikacji działają zarówno w przypadku aplikacji licencjonowanych dla urządzenia, jak i użytkownika dla systemu iOS w wersji 11.0 i nowszej.
6. Gdy wszystko będzie gotowe, wybierz pozycję **Utwórz**.

Token zostanie wyświetlony na liście w okienku tokenów.

Dane przechowywane przez firmę Apple można w dowolnym momencie zsynchronizować z usługą Intune, wybierając pozycję **Synchronizuj teraz**.

## <a name="to-assign-a-volume-purchased-app"></a>Wdrażanie aplikacji nabytej w ramach programu zakupów zbiorczych

1.  W okienku **Intune** wybierz pozycję **Aplikacje klienckie** > **Aplikacje** w obszarze **Zarządzanie**.
2.  W okienku z listą aplikacji wybierz aplikację, którą chcesz przypisać, a następnie wybierz pozycję **Przypisania**.
3.  W okienku ***Nazwa aplikacji*** - **Przypisania** wybierz pozycję **Dodaj grupy**, a następnie w okienku **Dodawanie grup** wybierz pozycję **Typ przypisania** i wybierz grupy użytkowników lub urządzeń usługi Azure AD, do których chcesz przypisać aplikację.
5.  Dla każdej wybranej grupy wybierz następujące ustawienia:
    - **Typ** — wybierz, czy aplikacja będzie **dostępna** (użytkownicy końcowi mogą instalować aplikację z Portalu firmy), czy **wymagana** (aplikacja zostanie automatycznie pobrana i zainstalowana na urządzeniach użytkowników końcowych).
    - **Typ licencji** — wybierz **Licencjonowanie na użytkownika** lub **Licencjonowanie na urządzenie**.
6.  Gdy wszystko będzie gotowe, wybierz pozycję **Zapisz**.


>[!NOTE]
>Wyświetlona lista aplikacji jest skojarzona z tokenem. Jeśli dana aplikacja jest skojarzona z wieloma tokenami VPP, zostanie ona wyświetlona wiele razy (po jednym razie dla każdego tokenu).

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

## <a name="revoking-app-licenses-and-deleting-tokens"></a>Odwoływanie licencji aplikacji i usuwanie tokenów 

Można odwołać wszystkie skojarzone licencje aplikacji licencje aplikacji systemu iOS w ramach programu Volume Purchase Program (VPP) na podstawie danego urządzenia, użytkownika lub aplikacji. Możesz powiadomić użytkowników, że aplikacja nie jest już do nich przypisana. Odwołanie licencji aplikacji nie spowoduje odinstalowania powiązanych aplikacji VPP z urządzenia. Aby odinstalować aplikację VPP i odzyskać licencję aplikacji przypisaną do użytkownika lub urządzenia, musisz zmienić akcję przypisywania na **Odinstaluj**. Gdy usuniesz aplikację przypisaną do użytkownika, usługa Intune odzyska licencję użytkownika lub urządzenia i odinstaluje aplikację z urządzenia. Liczba odzyskanych licencji zostanie odzwierciedlona w węźle **Licencjonowane aplikacje** w obciążeniu **Aplikacje** usługi Intune. Po odinstalowaniu aplikacji VPP i odzyskaniu licencji aplikacji można przypisać tę licencję do innego użytkownika lub urządzenia. 

>[!NOTE]
>Kiedy pracownik opuści firmę i przestanie być członkiem jakiejkolwiek grupy w usłudze AAD, usługa Intune pobierze wszystkie przypisane do użytkowników licencje aplikacji VPP dla systemu iOS.

<!-- 820879 -->  
Istnieje możliwość usunięcia tokenu programu Volume Purchasing Program (VPP) systemu iOS przy użyciu konsoli. Może to być konieczne w przypadku występowania zduplikowanych wystąpień tokenu programu VPP. Usunięcie tokenu spowoduje również usunięcie wszelkich skojarzonych aplikacji oraz przypisania. Jednak usunięcie tokenu nie spowoduje odwołania licencji aplikacji ani odinstalowania aplikacji. 

>[!NOTE]
>Usługa Intune nie można odwołać licencji aplikacji, jeśli token zostanie usunięty. 

<!-- 820870 -->  
Aby odwołać licencję wszystkich aplikacji programu VPP dla danego tokenu programu VPP, należy najpierw odwołać wszystkie licencje aplikacji skojarzone z tokenem, a następnie usunąć token.

## <a name="renewing-app-licenses"></a>Odnawianie licencji aplikacji

Token VPP firmy Apple można odnowić, pobierając nowy token z portalu programu Apple Volume Purchase Program i aktualizując istniejący token w usłudze Intune.

## <a name="deleting-an-ios-vpp-app"></a>Usuwanie aplikacji programu VPP systemu iOS

Obecnie nie można usunąć aplikacji programu VPP systemu iOS z usługi Microsoft Intune.

## <a name="additional-information"></a>Dodatkowe informacje

Gdy użytkownik mający kwalifikujące się urządzenie spróbuje zainstalować aplikację VPP na urządzeniu po raz pierwszy, zostanie poproszony o dołączenie do programu Apple Volume Purchase Program. Jest to konieczne, aby instalacja aplikacji mogła być kontynuowana. Zaproszenie do dołączenia do programu Apple Volume Purchase program wymaga, aby użytkownik był w stanie używać aplikacji iTunes na urządzeniu z systemem iOS. Jeśli ustawiono zasady wyłączające aplikację sklepu iTunes, oparte na użytkowniku licencje na aplikacje VPP nie działają. Rozwiązanie polega na zezwoleniu na działanie aplikacji iTunes poprzez usunięcie zasad lub na zastosowaniu licencji opartych na urządzeniach.

Firma Apple zapewnia bezpośrednią pomoc dotyczącą tworzenia i odnawiania tokenów programu VPP. Aby uzyskać więcej informacji, zobacz artykuł [Dystrybucja zawartości wśród użytkowników za pośrednictwem programu zakupów grupowych (VPP)](https://go.microsoft.com/fwlink/?linkid=2014661) jako część dokumentacji firmy Apple. 

Jeśli w portalu usługi Intune jest wskazana pozycja **Przypisane do zewnętrznego MDM**, wówczas Ty (administrator) musisz usunąć token VPP MDM od innej firmy przed użyciem tokenu VPP w usłudze Intune.

## <a name="frequently-asked-questions"></a>Często zadawane pytania

#### <a name="how-long-does-the-portal-take-to-update-the-license-count-once-an-app-is-installed-or-removed-from-the-device"></a>Jak długo trwa aktualizowanie liczby licencji w portalu po zainstalowaniu aplikacji na urządzeniu lub usunięciu jej z urządzenia?
Licencja powinna zostać zaktualizowana w ciągu kilku godzin po zainstalowaniu lub odinstalowaniu aplikacji. Należy pamiętać, że jeśli użytkownik końcowy usunie aplikację z urządzenia, licencja będzie nadal przypisana do tego użytkownika lub urządzenia.

#### <a name="is-it-possible-to-oversubscribe-an-app-and-if-so-in-what-circumstance"></a>Czy możliwe jest nadsubskrybowanie aplikacji, a jeśli tak, to w jakich okolicznościach?
Tak. Administrator usługi Intune może nadsubskrybować aplikację. Może to mieć na przykład miejsce, jeśli administrator zakupi 100 licencji dla aplikacji XYZ, a następnie przeznaczy aplikację dla grupy zawierającej 500 elementów członkowskich. Licencja zostanie przypisana do pierwszych 100 elementów członkowskich (użytkowników lub urządzeń), a dla pozostałych przypisanie licencji zakończy się niepowodzeniem.

#### <a name="i-understand-intune-automatically-syncs-app-licenses-each-day-with-apple-is-that-correct"></a>Czy to prawda, że usługa Intune każdego dnia automatycznie synchronizuje licencje z firmą Apple?
Usługa Intune przeprowadza synchronizację licencji aplikacji z firmą Apple dwa razy dziennie.

## <a name="next-steps"></a>Następne kroki

Informacje przydatne do monitorowania przypisań aplikacji znajdują się w artykule [How to monitor apps](apps-monitor.md) (Jak monitorować aplikacje).
