---
title: "Przypisywanie aplikacji do grup | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
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
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 638ad0d87c19c9e40e96b42d18e5c4342f40a156
ms.lasthandoff: 02/16/2017

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

