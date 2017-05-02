---
title: "Zarządzanie aplikacjami dla systemu iOS nabytymi w ramach zakupów zbiorczych"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje o synchronizowaniu aplikacji zakupionych w ramach zakupów zbiorczych w sklepie z aplikacjami dla systemu iOS w usłudze Intune oraz o zarządzaniu ich użyciem i jego śledzeniu."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: a981b0253f56d66292ce77639faf4beba8832a9e
ms.openlocfilehash: 1c13d39b8b193c56439602a6e9d9a34e547aef81
ms.lasthandoff: 04/19/2017

---

# <a name="how-to-manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Jak zarządzać w usłudze Microsoft Intune aplikacjami dla systemu iOS, które zostały zakupione w ramach programu zakupów zbiorczych


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Sklep z aplikacjami systemu iOS umożliwia zakup wielu licencji dla aplikacji, które mają być uruchamiane w firmie. Dzięki temu można zmniejszyć koszty administracyjne śledzenia wielu zakupionych kopii aplikacji.

Usługa Microsoft Intune ułatwia zarządzanie aplikacjami zakupionymi za pośrednictwem tego programu przez zaimportowanie informacji o licencji ze sklepu z aplikacjami, śledzenie, ile licencji jest używanych, i zapobieganie instalacji większej liczby kopii aplikacji niż posiadana.

Dodatkowo możesz także synchronizować książki zakupione w sklepie programu zakupów zbiorczych Apple praz zarządzać nimi i przypisywać je przy użyciu usługi Intune, a także przypisywać je do użytkowników. Do zarządzania książkami służy obciążenie **Książki** w portalu usługi Intune. Procedury zarządzania książkami są takie same, jak używane do zarządzania aplikacjami.
Aby z nich korzystać, trzeba wcześniej przesłać token programu zakupów zbiorczych firmy Apple. Obecnie można przypisywać książki wyłącznie w ramach opcji instalacji **Wymagane**.
Aby możliwe było przypisanie książki do urządzenia, musi na nim być zainstalowana wbudowana aplikacja iBooks. Jeśli tak nie jest, użytkownik końcowy musi ponownie zainstalować aplikację w celu czytania książki. Obecnie nie jest możliwe przywracanie usuniętych wbudowanych aplikacji przy użyciu usługi Intune.


## <a name="manage-volume-purchased-apps-for-ios-devices"></a>Zarządzanie zbiorczo zakupionymi aplikacjami dla urządzeń z systemem iOS
Wiele licencji dla aplikacji z systemem iOS można zakupić za pośrednictwem programu [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) lub [Apple Volume Purchase Program for Education](http://volume.itunes.apple.com/us/store). Obejmuje to skonfigurowanie konta VPP w witrynie sieci Web firmy Apple i przekazanie tokenu VPP firmy Apple do usługi Intune.  Następnie można zsynchronizować dane zakupu zbiorczego z usługą Intune i śledzić użycie aplikacji nabytych w ramach zakupu zbiorczego.

## <a name="before-you-start"></a>Przed rozpoczęciem
Przed rozpoczęciem należy uzyskać token VPP od firmy Apple i przekazać go do konta usługi Intune. Ponadto należy zrozumieć następujące kwestie:

* Z kontem usługi Intune można skojarzyć wiele tokenów programów zakupionych w ramach zakupów zbiorczych.
* Jeśli poprzednio korzystano z tokenu VPP w ramach innego produktu, należy wygenerować nowy, aby korzystać z usługi Intune.
* Każdy token jest ważny przez jeden rok.
* Domyślnie usługa Intune przeprowadza synchronizację z usługą Apple VPP dwa razy dziennie. W dowolnym momencie można uruchomić ręczną synchronizację.
* Po zaimportowaniu tokenu VPP do usługi Intune nie należy importować tego samego tokenu do żadnego innego rozwiązania do zarządzania urządzeniami. Może to spowodować utratę przypisania licencji i rekordów użytkowników.
* Przed rozpoczęciem korzystania z programu VPP dla systemu iOS przy użyciu usługi Intune należy usunąć wszystkie istniejące konta usługi VPP utworzone przy użyciu innych dostawców zarządzania urządzeniami przenośnymi. Usługa Intune nie będzie synchronizować tych kont użytkowników z usługą Intune ze względów bezpieczeństwa. Usługa Intune będzie tylko synchronizować dane z usługi VPP firmy Apple, która została utworzona przez usługę Intune.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Aby uzyskać i przekazać token usługi VPP firmy Apple

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno pozycje **Więcej usług** > **Inne** > **Intune**.
3. W bloku **Intune** wybierz opcję **Zarządzaj aplikacjami**.
1.  W obciążeniu **Zarządzaj aplikacjami** wybierz kolejno pozycje **Konfiguracja** > **Tokeny programu VPP dla systemu iOS**.
2.  W bloku listy tokenów programu VPP kliknij pozycję **Dodaj**.
3.  W bloku Nowy token programu VPP określ następujące informacje:
    - **Plik tokenu programu VPP** — jeśli nie jesteś jeszcze zarejestrowanym członkiem programu zakupów zbiorczych dla firm lub dla instytucji oświatowych, zarejestruj się. Po zarejestrowaniu się pobierz token VPP firmy Apple dla swojego konta i wybierz go tutaj.
    - **Identyfikator firmy Apple** — wprowadź identyfikator firmy Apple dla konta skojarzonego z programem zakupów zbiorczych.
    - **Typ konta programu VPP** — wybierz opcję **Biznes** lub **Edukacja**.
4. Gdy wszystko będzie gotowe, kliknij pozycję **Przekaż**.

Token zostanie wyświetlony na liście w bloku tokenów.


Dane przechowywane przez firmę Apple można w dowolnym momencie zsynchronizować z usługą Intune, wybierając pozycję **Synchronizuj teraz**.

## <a name="to-assign-a-volume-purchased-app"></a>Wdrażanie aplikacji nabytej w ramach programu zakupów zbiorczych

1. W obciążeniu **Zarządzaj aplikacjami** wybierz kolejno pozycje **Zarządzaj** > **Licencjonowane aplikacje**.
2. W bloku listy aplikacji wybierz aplikację, którą chcesz przypisać, a następnie wybierz kolejno opcje „**...**” > **Przypisz grupy**.
3. W bloku <*nazwa aplikacji*> — **Przypisane grupy** wybierz kolejno pozycje **Zarządzaj** > **Przypisane grupy**.
4. Wybierz pozycję **Przypisz grupy**, a następnie w bloku **Wybierz grupy** wybierz grupy użytkowników lub urządzeń usługi Azure AD, do których chcesz przypisać aplikację.
Musisz wybrać akcję przypisania **Wymagane**. Ponadto przypisania do grup urządzeń są dostępne dla nowych dzierżaw utworzonych po styczniu 2017 r. Jeśli Twoja dzierżawa została utworzona wcześniej i nie masz możliwości przypisania aplikacji usługi VPP do grup urządzeń, skontaktuj się z pomocą techniczną usługi Intune.
5. Gdy wszystko będzie gotowe, wybierz pozycję **Zapisz**.

Informacje przydatne do monitorowania przypisań aplikacji znajdują się w artykule [How to monitor apps](monitor-apps.md) (Jak monitorować aplikacje).

## <a name="further-information"></a>Dodatkowe informacje

Podczas przypisywania aplikacji jako instalacji **wymaganej** licencja jest używana przez każdego użytkownika, który instaluje aplikację.

Aby odzyskać licencję, należy zmienić akcję przypisywania na **Odinstaluj**. Licencja zostanie odzyskana po odinstalowaniu aplikacji.

Gdy użytkownik mający kwalifikujące się urządzenie spróbuje zainstalować aplikację VPP po raz pierwszy, zostanie poproszony o dołączenie do programu zakupów zbiorczych firmy Apple. Jest to konieczne, aby instalacja aplikacji mogła być kontynuowana.

W przypadku wdrażania aplikacji VPP jako elementu o właściwości Dostępne zawartość aplikacji oraz licencja są wdrażane bezpośrednio ze sklepu z aplikacjami.

