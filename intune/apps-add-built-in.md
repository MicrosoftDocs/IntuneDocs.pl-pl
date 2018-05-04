---
title: Dodawanie wbudowanych aplikacji do urządzeń przenośnych za pomocą usługi Microsoft Intune
titlesuffix: ''
description: Dowiedz się, jak przy użyciu usługi Intune możesz łatwiej instalować wbudowane aplikacje na urządzeniach przenośnych.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0ec8de66-5a0f-4c8d-afbf-c2becc7d6eec
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 54eb50a47b28d04fc32662098c4ee521ae63589e
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
---
# <a name="add-built-in-apps-to-microsoft-intune"></a>Dodawanie wbudowanych aplikacji do usługi Microsoft Intune

Aplikacja typu *wbudowanego* ułatwia przypisanie nadzorowanych zarządzanych aplikacji, takich jak aplikacje usługi Office 365, do urządzeń z systemem iOS i Android. Do tego typu aplikacji możesz przypisać określone aplikacje, takie jak Excel, OneDrive, Outlook, Skype i inne. Po dodaniu aplikacji typ aplikacji zostanie wyświetlony jako *Wbudowana aplikacja systemu iOS* lub *Wbudowana aplikacja systemu Android*. Za pomocą typu wbudowanej aplikacji możesz wybrać, które z tych aplikacji mają być opublikowane dla użytkowników urządzenia.

We wcześniejszych wersjach konsoli usługi Intune usługa Intune udostępniała kilka domyślnych zarządzanych aplikacji usługi Office 365, takich jak Outlook i OneDrive. Typy aplikacji dla tych zarządzanych aplikacji zostały oznaczone jako *Zarządzana aplikacja w sklepie dla systemu iOS* lub *Zarządzana aplikacja dla systemu Android*. Zamiast korzystania z tych typów aplikacji firma Microsoft zaleca użycie typu aplikacji wbudowanej. Korzystanie z typu aplikacji wbudowanej pozwala na uzyskanie większej elastyczności podczas edytowania i usuwania aplikacji usługi Office 365.

>[!NOTE]
>Domyślne aplikacje usługi Office 365 oznaczone jako *Zarządzana w sklepie dla systemu iOS* i *Zarządzana aplikacja dla systemu Android* zostaną usunięte z listy aplikacji po usunięciu wszystkich przypisań.

## <a name="add-a-built-in-app"></a>Dodawanie aplikacji wbudowanej

Aby dodać aplikację wbudowaną do dostępnych dla Ciebie aplikacji w usłudze Microsoft Intune, wykonaj następujące czynności:
1. Zaloguj się do witryny Azure Portal.
2. Aby wyświetlić okienko usługi Microsoft Intune, wybierz pozycje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W okienku **Intune** wybierz pozycję **Aplikacje mobilne**.
4. W okienku **Aplikacje mobilne** w obszarze **Zarządzaj** wybierz pozycję **Aplikacje**.
5. Wybierz pozycję **Dodaj**.
6. W okienku aplikacji **Dodaj** z listy **Typ aplikacji** wybierz pozycję **Aplikacja wbudowana**.
7. Wybierz pozycję **Wybierz aplikację**.
8. W okienku **Aplikacja wbudowana** wybierz aplikacje, które chcesz dołączyć.
9. W okienku **Dodaj aplikację** wybierz pozycję **Dodaj**.


## <a name="configure-app-information"></a>Konfigurowanie informacji o aplikacji

Możesz zmodyfikować informacje o wbudowanej aplikacji. Te informacje pomagają zidentyfikować aplikację w usłudze Intune i ułatwiają użytkownikom odnalezienie aplikacji w portalu firmy.
1. W okienku **Aplikacje mobilne — aplikacje** wybierz wbudowaną aplikację, którą chcesz zmodyfikować.  
    Zostanie wyświetlone okienko dla wbudowanej aplikacji.
2. W obszarze **Zarządzaj** wybierz opcję **Właściwości**.
3. Aby zmodyfikować informacje o wbudowanej aplikacji, wybierz opcję **Konfiguruj**.
4. W okienku **Informacje o aplikacji** możesz zmodyfikować następujące informacje:
    - **Nazwa**: wprowadź nazwę wbudowanej aplikacji taką, jaka jest wyświetlana w Portalu firmy. Upewnij się, że wszystkie używane nazwy są unikatowe. Jeśli dana nazwa aplikacji występuje dwa razy, użytkownicy Portalu firmy będą widzieć tylko jedną z aplikacji o tej nazwie.
    - **Opis**: wprowadź opis aplikacji. 
    - **Wydawca**: wprowadź nazwę wydawcy aplikacji.
    - **Kategoria**: opcjonalnie wybierz przynajmniej jedną z kategorii wbudowanych aplikacji. Ustawienie tej opcji ułatwi użytkownikom znajdowanie aplikacji podczas przeglądania Portalu firmy.
    - **Wyświetl jako polecaną aplikację w portalu firmy**: wyróżnij aplikację na stronie głównej portalu firmy dla użytkowników przeglądających aplikacje.
    - **Adres URL informacji**: opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Adres URL zasad ochrony prywatności**: opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o zasadach ochrony prywatności mających zastosowanie do tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Deweloper**: opcjonalnie wprowadź nazwę dewelopera aplikacji.
    - **Właściciel**: opcjonalnie wprowadź nazwę właściciela aplikacji (na przykład *Dział kadr*).
    - **Uwagi**: wprowadź wszelkie uwagi, które chcesz skojarzyć z tą aplikacją.
    - **Przekaż ikonę**: przekaż ikonę, która jest wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
4. Wybierz przycisk **OK**.
5. W okienku **Właściwości** wybierz pozycję **Zapisz**.

## <a name="next-steps"></a>Następne kroki

- Teraz można przypisać aplikacje do wybranych grup. Aby uzyskać więcej informacji, zobacz temat [Przypisywanie aplikacji do grup](apps-deploy.md).
