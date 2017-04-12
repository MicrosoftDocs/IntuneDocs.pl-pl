---
title: "Jak przypisać aplikacje do grup"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: po dodaniu aplikacji do usługi Intune należy przypisać ją do grup użytkowników lub urządzeń."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b372d4ee505ca39a4739069e5798918ecde134ea
ms.openlocfilehash: abf45b835d13ef5fe4acb769194542611448504e
ms.lasthandoff: 02/18/2017

---

# <a name="how-to-assign-apps-to-groups-with-microsoft-intune"></a>Jak przypisywać aplikacje do grup w usłudze Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Po dodaniu aplikacji do usługi Intune należy ją udostępnić użytkownikom i urządzeniom. W tym celu należy ją przypisać.

Aplikacje można przypisać do urządzeń niezależnie od tego, czy są zarządzane przez usługę Intune. Poniższa tabela pomoże zapoznać się z różnymi opcjami przypisywania aplikacji użytkownikom i urządzeniom:

||||
|-|-|-|-|
|&nbsp;|Urządzenia zarejestrowane w usłudze Intune|Urządzenia niezarejestrowane w usłudze Intune|
|Przypisz do użytkowników|Tak|Tak|
|Przypisz do urządzeń|Tak|Nie|
|Przypisz opakowane aplikacje lub aplikacje zawierające zestaw Intune SDK (dla zasad ochrony aplikacji)|Tak|Tak|
|Przypisz aplikacje jako dostępne|Tak|Tak|
|Przypisz aplikacje jako wymagane|Tak|Nie|
|Odinstaluj aplikacje|Tak|Tak|
|Użytkownicy końcowi instalują dostępne aplikacje z aplikacji Portal firmy|Tak|Nie|
|Użytkownicy końcowi instalują dostępne aplikacje z internetowego Portalu firmy|Tak|Tak|

> [!NOTE]
> Obecnie można przypisać aplikacje iOS i Android (zarówno biznesowe, jak i zakupione w sklepie) do urządzeń, które nie są zarejestrowane w usłudze Intune.

## <a name="changes-to-how-you-assign-apps-to-groups-in-the-intune-preview"></a>Zmiany metody przypisywania aplikacji do grup w wersji zapoznawczej usługi Intune

W wersji zapoznawczej usługi Intune Azure nie używa się już grup w usłudze Intune do przypisywania aplikacji; teraz używa się grup zabezpieczeń usługi Azure Active Directory (Azure AD). W związku z tym należy poznać pewne zmiany w sposobie, w jaki odbywają się przypisania aplikacji, szczególnie w przypadku przypisywania aplikacji do grup podrzędnych usługi Intune.
Najważniejszą rzeczą, na którą trzeba zwrócić uwagę jest to, że pojęcie grup podrzędnych nie istnieje w usłudze Azure AD. Jednak niektóre grupy mogą zawierać te same elementy członkowskie. W takim przypadku zachowanie klasycznej usługi Intune różni się od wersji zapoznawczej usługi Intune Azure. Zostało to przedstawione w poniższej tabeli:

||||||
|-|-|-|-|-|
|**Intune Classic (przed migracją dzierżawy)**|-|**Intune Azure (po zakończeniu migracji dzierżawy)**|-|**Więcej informacji**|
|**Opcja wdrażania grupy nadrzędnej**|**Opcja wdrażania grupy podrzędnej**|**Wynikowa opcja przypisania dla wspólnych elementów członkowskich poprzedniej grupy nadrzędnej i podrzędnej**|**Akcja wynikowej opcji przypisania dla elementów członkowskich grupy nadrzędnej**|-|    
|Dostępne|Wymagane|Wymagane i dostępne|Dostępne|Wymagane i dostępne oznacza, że aplikacje przypisane w razie potrzeby można także znaleźć w aplikacji Portal firmy.
|Nie dotyczy|Dostępne|Nie dotyczy|Nie dotyczy|Obejście problemu: usuń opcję wdrażania „Nie dotyczy” z grupy nadrzędnej usługi Intune.
|Wymagane|Dostępne|Wymagane i dostępne|Wymagane|-|
|Wymagane i dostępne<sup>1</sup>|Dostępne|Wymagane i dostępne|Wymagane i dostępne|-|    
|Wymagane|Nie dotyczy|Wymagane|Wymagane|-|    
|Wymagane i dostępne|Nie dotyczy|Wymagane i dostępne|Wymagane i dostępne|-|    
|Wymagane|Odinstaluj|Wymagane|Wymagane|-|    
|Wymagane i dostępne|Odinstaluj|Wymagane i dostępne|Wymagane i dostępne|-|
<sup>1</sup> Tylko dla zarządzanych aplikacji ze sklepu iOS w przypadku ich dodania do usługi Intune i wdrożenia jako Wymagane są automatycznie tworzone z opcjami Wymagane i Dostępne.

W celu uniknięcia konfliktów wdrożenia można wykonać następujące czynności:

1.    Jeśli aplikacje zostały wcześniej wdrożone do powiązanych grup nadrzędnych i podrzędnych usługi Intune, rozważ usunięcie tych wdrożeń przed rozpoczęciem migracji dzierżawy.
2.    Usuń grupy podrzędne z grup nadrzędnych i utwórz nową grupę zawierającą elementy członkowskie starej grupy podrzędnej. Następnie można utworzyć nowe wdrożenie aplikacji do tej grupy.
Uwagi: Jeśli poprzednią grupą nadrzędną była „Wszyscy użytkownicy”, należy utworzyć nową grupę dynamiczną, która nie obejmuje elementów członkowskich grupy podrzędnej.
Należy wprowadzić zmiany w grupach w portalu [Azure Portal](https://portal.azure.com/) dla grup użytkowników i urządzeń. [Klasyczny portal Azure](https://manage.windowsazure.com/) pozwala wprowadzać zmiany tylko w grupach użytkowników.


## <a name="how-to-assign-an-app"></a>Jak przypisać aplikację

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Zarządzaj aplikacjami**.
1. W obciążeniu **Zarządzaj aplikacjami** wybierz kolejno opcje **Zarządzaj** > **Aplikacje**.
2. W bloku listy aplikacji kliknij aplikację, którą chcesz przypisać.
3. W bloku <*nazwa aplikacji*> — **Przegląd** wybierz kolejno pozycje **Zarządzaj** > **Przypisania**.
4. Wybierz pozycję **Wybierz grupy**, a następnie w bloku **Wybierz grupy** wybierz grupy Azure AD, do których chcesz przypisać aplikację.
5. Dla każdej wybranej aplikacji wybierz **typ przypisania** dla aplikacji:
    - **Dostępne** — użytkownicy instalują aplikację z aplikacji Portal firmy lub witryny sieci Web.
    - **Nie dotyczy** — aplikacja nie jest instalowana ani wyświetlana w Portalu firmy.
    - **Wymagane** — aplikacja jest instalowana na urządzeniach w wybranych grupach.
    - **Odinstaluj** — aplikacja jest odinstalowywana z urządzeń w wybranych grupach.
    - **Dostępne z rejestracją lub bez** — przypisz tę aplikację do grup użytkowników, których urządzenia nie są zarejestrowane w usłudze Intune. Pomocna będzie tabela powyżej.
6. Gdy wszystko będzie gotowe, wybierz pozycję **Zapisz**.

Aplikacja jest teraz przypisana do wybranej grupy.

Informacje przydatne do monitorowania przypisań aplikacji znajdują się w artykule [How to monitor apps](monitor-apps.md) (Jak monitorować aplikacje).

