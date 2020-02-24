---
title: Dodawanie wbudowanych aplikacji do urządzeń przenośnych za pomocą usługi Microsoft Intune
titleSuffix: ''
description: Dowiedz się, jak przy użyciu usługi Intune możesz łatwiej instalować wbudowane aplikacje na urządzeniach przenośnych.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/22/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0ec8de66-5a0f-4c8d-afbf-c2becc7d6eec
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 96cd4997029c15396db91e9866bbb387c20f1044
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2020
ms.locfileid: "77414445"
---
# <a name="add-built-in-apps-to-microsoft-intune"></a>Dodawanie wbudowanych aplikacji do usługi Microsoft Intune

Aplikacja typu *wbudowanego* ułatwia przypisanie nadzorowanych zarządzanych aplikacji, takich jak aplikacje usługi Office 365, do urządzeń z systemem iOS/iPadOS i Android. Do tego typu aplikacji możesz przypisać określone aplikacje, takie jak Excel, OneDrive, Outlook, Skype i inne. Po dodaniu aplikacji typ aplikacji zostanie wyświetlony jako *Wbudowana aplikacja systemu iOS* lub *Wbudowana aplikacja systemu Android*. Za pomocą typu wbudowanej aplikacji możesz wybrać, które z tych aplikacji mają być opublikowane dla użytkowników urządzenia.

We wcześniejszych wersjach konsoli usługi Intune usługa Intune udostępniała kilka domyślnych zarządzanych aplikacji usługi Office 365, takich jak Outlook i OneDrive. Typy aplikacji dla tych zarządzanych aplikacji zostały oznaczone jako *Zarządzana aplikacja w sklepie dla systemu iOS* lub *Zarządzana aplikacja dla systemu Android*. Zamiast korzystania z tych typów aplikacji firma Microsoft zaleca użycie typu aplikacji wbudowanej. Korzystanie z typu aplikacji wbudowanej pozwala na uzyskanie większej elastyczności podczas edytowania i usuwania aplikacji usługi Office 365.

>[!NOTE]
>Domyślne aplikacje usługi Office 365 oznaczone jako *Zarządzana w sklepie dla systemu iOS* i *Zarządzana aplikacja dla systemu Android* zostaną usunięte z listy aplikacji po usunięciu wszystkich przypisań.

## <a name="add-a-built-in-app"></a>Dodawanie aplikacji wbudowanej

Aby dodać aplikację wbudowaną do dostępnych dla Ciebie aplikacji w usłudze Microsoft Intune, wykonaj następujące czynności:
1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**.
3. W okienku **Wybierz typ aplikacji** w obszarze dostępnych typów **Aplikacja ze sklepu** wybierz pozycję **Aplikacja wbudowana**.
4. Kliknij pozycję **Wybierz**. Zostaną wyświetlone kroki **dodawania aplikacji**.
5. Na stronie **Wybierz aplikacje wbudowane** kliknij pozycję **Wybierz aplikację**, aby wybrać aplikacje, które chcesz uwzględnić.
6. Wybierz aplikacje wbudowane do uwzględnienia. 
7. Po wybraniu aplikacji kliknij pozycję **Wybierz** w okienku **Wybierz wbudowane aplikacje**.
8. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Tagi zakresu**.
9. Kliknij pozycję **Wybierz tagi zakresu**, aby opcjonalnie dodać tagi zakresu dla aplikacji. Aby uzyskać więcej informacji, zobacz temat [Używanie kontroli dostępu opartej na rolach i tagów zakresu w rozproszonej infrastrukturze informatycznej](~/fundamentals/scope-tags.md).
10. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Przypisania**.
11. Wybierz przypisania grupy dla aplikacji. Aby uzyskać więcej informacji, zobacz temat [Dodawanie grup w celu organizowania użytkowników i urządzeń](~/fundamentals/groups-add.md). 
12. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Recenzja i tworzenie**. Przejrzyj wartości i ustawienia wprowadzone dla aplikacji.
13. Gdy skończysz, kliknij pozycję **Utwórz**, aby dodać aplikację do usługi Intune.

    Zostanie wyświetlony blok **Omówienie** dotyczący utworzonej aplikacji.

## <a name="configure-app-information"></a>Konfigurowanie informacji o aplikacji

Możesz zmodyfikować informacje o wbudowanej aplikacji. Te informacje pomagają zidentyfikować aplikację w usłudze Intune i ułatwiają użytkownikom odnalezienie aplikacji w portalu firmy.
1. Wybierz kolejno pozycje **Aplikacje** > **Wszystkie aplikacje** i wybierz wbudowaną aplikację, którą chcesz zmodyfikować.  
   Zostanie wyświetlone okienko dla wbudowanej aplikacji.
2. Wybierz pozycję **Właściwości**.
3. Wybierz pozycję **Edytuj** obok pozycji **Informacje o aplikacji**.
4. W okienku **Informacje o aplikacji** możesz zmodyfikować następujące informacje:
    - **Nazwa**: wprowadź nazwę wbudowanej aplikacji taką, jaka jest wyświetlana w Portalu firmy. Upewnij się, że wszystkie używane nazwy są unikatowe. Jeśli dana nazwa aplikacji występuje dwa razy, użytkownicy Portalu firmy będą widzieć tylko jedną z aplikacji o tej nazwie.
    - **Opis**: Wprowadź opis aplikacji. 
    - **Wydawca**: Wprowadź nazwę wydawcy aplikacji.
    - **Kategoria**: opcjonalnie wybierz przynajmniej jedną z kategorii wbudowanych aplikacji. Ustawienie tej opcji ułatwi użytkownikom znajdowanie aplikacji podczas przeglądania Portalu firmy.
    - **Pokaż jako polecaną aplikację w Portalu firmy**: Wyróżnij aplikację na stronie głównej Portalu firmy dla użytkowników przeglądających aplikacje.
    - **Adres URL informacji**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Adres URL zasad ochrony prywatności**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje dotyczące zasad ochrony prywatności w tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Deweloper**: opcjonalnie wprowadź nazwę dewelopera aplikacji.
    - **Właściciel**: opcjonalnie wprowadź nazwę właściciela aplikacji (na przykład *Dział kadr*).
    - **Uwagi**: wprowadź wszelkie uwagi, które chcesz skojarzyć z tą aplikacją.
    - **Przekaż ikonę**: przekaż ikonę, która jest wyświetlana jako ikona aplikacji podczas przeglądania portalu firmy.
5. Kliknij pozycję **Przejrzyj i zapisz**, aby wyświetlić stronę **Przeglądanie + tworzenie**. Przejrzyj wartości i ustawienia wprowadzone dla aplikacji.
13. Gdy skończysz, kliknij pozycję **Zapisz**, aby zaktualizować aplikację w usłudze Intune.

    Zostanie wyświetlony blok **Omówienie** dotyczący utworzonej aplikacji.

## <a name="next-steps"></a>Następne kroki

- Teraz można przypisać aplikacje do wybranych grup. Aby uzyskać więcej informacji, zobacz temat [Przypisywanie aplikacji do grup](apps-deploy.md).
