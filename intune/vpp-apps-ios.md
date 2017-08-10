---
title: "Zarządzanie aplikacjami dla systemu iOS nabytymi w ramach zakupów zbiorczych"
titleSuffix: Intune on Azure
description: "Informacje o synchronizowaniu aplikacji kupionych w ramach zakupów zbiorczych w sklepie z aplikacjami dla systemu iOS z usługą Intune oraz o zarządzaniu ich użyciem i jego śledzeniu."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 433cec8e0bc2012090e680e0a28a9a77d7b13a38
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2017
---
# <a name="how-to-manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Jak zarządzać w usłudze Microsoft Intune aplikacjami dla systemu iOS, które zostały zakupione w ramach programu zakupów zbiorczych


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Sklep z aplikacjami systemu iOS umożliwia zakup wielu licencji dla aplikacji, które mają być uruchamiane w firmie. Zakup wielu kopii aplikacji pozwala zmniejszyć koszty administracyjne śledzenia wielu kupionych kopii aplikacji.

Usługa Microsoft Intune ułatwia zarządzanie aplikacjami kupionymi za pośrednictwem tego programu, ponieważ umożliwia:

- Importowanie informacji o licencji ze sklepu z aplikacjami
- Śledzenie liczby używanych licencji
- Zapobieganie instalacji większej liczby kopii aplikacji niż posiadana

Istnieją dwie metody przypisywania aplikacji nabytych w ramach zakupów zbiorczych:

### <a name="device-licensing"></a>Licencjonowanie na urządzenie

W przypadku przypisania aplikacji do urządzeń używana jest jedna licencja aplikacji, która pozostaje skojarzona z urządzeniem, do którego została przypisana.
W przypadku przypisania aplikacji nabytych w ramach zakupów zbiorczych do urządzeń użytkownik końcowy urządzenia nie musi podawać identyfikatora Apple ID, aby uzyskać dostęp do sklepu. 

### <a name="user-licensing"></a>Licencjonowanie na użytkownika

W przypadku przypisania aplikacji do użytkowników używana jest jedna licencja aplikacji, która jest skojarzona z użytkownikiem. Aplikacja może być uruchamiana na wielu urządzeniach, które należą do użytkownika.
W przypadku przypisania aplikacji nabytych w ramach zakupów zbiorczych do użytkowników każdy użytkownik końcowy musi mieć prawidłowy identyfikator Apple ID, aby uzyskać dostęp do sklepu z aplikacjami.


Oprócz tego możesz także synchronizować książki kupione w sklepie programu Apple Volume Purchase Program oraz zarządzać nimi i przypisywać je przy użyciu usługi Intune. Do zarządzania książkami służy obciążenie **Książki** w portalu usługi Intune. Procedury zarządzania książkami są takie same, jak używane do zarządzania aplikacjami.
Przed rozpoczęciem działania trzeba przekazać token programu Apple Volume Purchase Program. Obecnie można przypisywać książki wyłącznie w ramach opcji instalacji **Wymagane**.
Aby możliwe było przypisanie książki do urządzenia, musi na nim być zainstalowana wbudowana aplikacja iBooks. Jeśli tak nie jest, użytkownik końcowy musi ponownie zainstalować aplikację w celu czytania książki. Obecnie nie jest możliwe przywracanie usuniętych wbudowanych aplikacji przy użyciu usługi Intune.


## <a name="manage-volume-purchased-apps-for-ios-devices"></a>Zarządzanie zbiorczo zakupionymi aplikacjami dla urządzeń z systemem iOS
Wiele licencji dla aplikacji systemu iOS można kupić za pośrednictwem programu [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) lub [Apple Volume Purchase Program for Education](http://volume.itunes.apple.com/us/store). Ten proces obejmuje skonfigurowanie konta programu VPP firmy Apple w witrynie sieci Web firmy Apple i przekazanie tokenu VPP firmy Apple do usługi Intune.  Następnie można zsynchronizować dane zakupu zbiorczego z usługą Intune i śledzić użycie aplikacji nabytych w ramach zakupu zbiorczego.

## <a name="before-you-start"></a>Przed rozpoczęciem
Przed rozpoczęciem należy uzyskać token VPP od firmy Apple i przekazać go do konta usługi Intune. Ponadto należy zapoznać się z następującymi kwestiami:

* Z kontem usługi Intune można skojarzyć wiele tokenów programów zakupionych w ramach zakupów zbiorczych.
* Jeśli poprzednio korzystano z tokenu VPP w ramach innego produktu, należy wygenerować nowy, aby korzystać z usługi Intune.
* Każdy token jest ważny przez jeden rok.
* Domyślnie usługa Intune przeprowadza synchronizację z usługą Apple VPP dwa razy dziennie. W dowolnym momencie można uruchomić ręczną synchronizację.
* Po zaimportowaniu tokenu VPP do usługi Intune nie należy importować tego samego tokenu do żadnego innego rozwiązania do zarządzania urządzeniami. Może to spowodować utratę przypisania licencji i rekordów użytkowników.
* Przed rozpoczęciem korzystania z programu VPP dla systemu iOS przy użyciu usługi Intune należy usunąć wszystkie istniejące konta usługi VPP utworzone przy użyciu innych dostawców zarządzania urządzeniami przenośnymi. Usługa Intune nie synchronizuje tych kont użytkowników z usługą Intune ze względów bezpieczeństwa. Usługa Intune synchronizuje tylko dane z usługi VPP firmy Apple, która została utworzona przez usługę Intune.
* Usługa Intune obsługuje dodawanie maksymalnie 256 tokenów usługi VPP.
* W przypadku przypisania aplikacji kupionych w ramach zakupów zbiorczych do urządzenia zarejestrowanego przy użyciu profilu rejestracji urządzeń lub programu Apple Configurator działają tylko te aplikacje, które są docelowe dla określonych urządzeń. Nie można przypisać aplikacji kupionych zbiorczo użytkownikom urządzenia DEP, które nie ma żadnych koligacji użytkownika.
* W danym momencie token VPP może być używany tylko w ramach jednego konta usługi Intune. Nie używaj tego samego tokenu VPP dla wielu dzierżaw usługi Intune.
* Jeśli aplikacje VPP zostały przypisane do użytkowników lub urządzeń (z koligacją użytkowników) za pomocą modelu licencjonowania użytkowników, każdy użytkownik usługi Intune musi zostać skojarzony z unikatowym identyfikatorem Apple ID lub adresem e-mail, aby mógł zaakceptować warunki i postanowienia firmy Apple na swoim urządzeniu.
Podczas konfigurowania urządzenia dla nowego użytkownika usługi Intune skonfiguruj je przy użyciu unikatowego identyfikatora Apple ID lub adresu e-mail tego użytkownika. Identyfikator Apple ID lub adres e-mail i użytkownik usługi Intune stanowią unikatową parę i mogą być używane na maksymalnie 5 urządzeniach.


## <a name="to-get-and-upload-an-apple-vpp-token"></a>Aby uzyskać i przekazać token usługi VPP firmy Apple

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz pozycję **Aplikacje mobilne**.
1.  W obciążeniu **Aplikacje mobilne** wybierz kolejno pozycje **Konfiguracja** > **Tokeny programu VPP dla systemu iOS**.
2.  W bloku listy tokenów programu VPP kliknij pozycję **Dodaj**.
3.  W bloku **Nowy token programu VPP** określ następujące informacje:
    - **Plik tokenu programu VPP** — jeśli nie jesteś jeszcze zarejestrowanym członkiem programu Volume Purchase Program for Business lub Volume Purchase Program for Education, zarejestruj się. Po zarejestrowaniu się pobierz token VPP firmy Apple dla swojego konta i wybierz go tutaj.
    - **Identyfikator firmy Apple** — wprowadź identyfikator firmy Apple dla konta skojarzonego z programem zakupów zbiorczych.
    - **Typ konta programu VPP** — wybierz opcję **Biznes** lub **Edukacja**.
4. Gdy wszystko będzie gotowe, kliknij pozycję **Przekaż**.

Token zostanie wyświetlony na liście w bloku tokenów.


Dane przechowywane przez firmę Apple można w dowolnym momencie zsynchronizować z usługą Intune, wybierając pozycję **Synchronizuj teraz**.

> [!NOTE]
> Usługa Microsoft Intune synchronizuje informacje dotyczące tylko tych aplikacji, które są publicznie dostępne w sklepie iTunes. **Niestandardowe aplikacje B2B dla systemu iOS** nie są jeszcze obsługiwane. Jeśli scenariusz odwołuje się do takich aplikacji, informacji o nich nie można zsynchronizować.

## <a name="to-assign-a-volume-purchased-app"></a>Wdrażanie aplikacji nabytej w ramach programu zakupów zbiorczych

1.  W obciążeniu **Aplikacje mobilne** wybierz kolejno pozycje **Zarządzaj** > **Licencje aplikacji**.
2.  W bloku listy aplikacji wybierz aplikację, którą chcesz przypisać, a następnie wybierz kolejno opcje „**...**” > **Przypisz grupy**.
3.  W bloku *<app name>* - **Przypisania** wybierz kolejno pozycje **Zarządzaj** > **Przypisania**.
4.  Wybierz pozycję **Wybierz grupy**, a następnie w bloku **Wybieranie grup** wybierz grupy użytkowników lub urządzeń usługi Azure AD, do których chcesz przypisać aplikację.
5.  Dla każdej wybranej grupy wybierz następujące ustawienia:
    - **Typ** — wybierz, czy aplikacja będzie **dostępna** (użytkownicy końcowi mogą instalować aplikację z Portalu firmy), czy **wymagana** (urządzenia użytkowników końcowych automatycznie pobiorą i zainstalują aplikację).
W przypadku przypisywania aplikacji VPP jako elementu o właściwości **Dostępna** zawartość i licencja aplikacji są przypisywane bezpośrednio ze sklepu z aplikacjami.
    - **Typ licencji** — wybierz **Licencjonowanie na użytkownika** lub **Licencjonowanie na urządzenie**.
6.  Gdy wszystko będzie gotowe, wybierz pozycję **Zapisz**.


>[!NOTE]
>Wyświetlona lista aplikacji jest skojarzona z tokenem. Jeśli dana aplikacja jest skojarzona z wieloma tokenami VPP, zostanie ona wyświetlona wiele razy (po jednym razie dla każdego tokenu).

## <a name="further-information"></a>Dodatkowe informacje

Aby odzyskać licencję, należy zmienić akcję przypisywania na Odinstaluj. Licencja zostanie odzyskana po odinstalowaniu aplikacji.

Gdy użytkownik mający kwalifikujące się urządzenie spróbuje zainstalować aplikację VPP po raz pierwszy, zostanie poproszony o dołączenie do programu Apple Volume Purchase Program. Jest to konieczne, aby instalacja aplikacji mogła być kontynuowana. Zaproszenie do dołączenia do programu Apple Volume Purchase program wymaga, aby użytkownik był w stanie używać aplikacji iTunes na urządzeniu z systemem iOS. Jeśli ustawiono zasady wyłączające aplikację sklepu iTunes, oparte na użytkowniku licencje na aplikacje VPP nie działają. Rozwiązanie polega na zezwoleniu na działanie aplikacji iTunes poprzez usunięcie zasad lub na zastosowaniu licencji opartych na urządzeniach.



## <a name="next-steps"></a>Następne kroki

Informacje przydatne do monitorowania przypisań aplikacji znajdują się w artykule [How to monitor apps](apps-monitor.md) (Jak monitorować aplikacje).