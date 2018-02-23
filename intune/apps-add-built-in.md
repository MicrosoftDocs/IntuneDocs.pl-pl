---
title: "Dodawanie wbudowanych aplikacji do urządzeń przenośnych za pomocą usługi Intune"
titlesuffix: Azure portal
description: "Dowiedz się, jak przy użyciu usługi Intune możesz łatwiej instalować wbudowane aplikacje na urządzeniach przenośnych."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/13/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0ec8de66-5a0f-4c8d-afbf-c2becc7d6eec
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d622f2cb8c6b3e8c9aace4e805108ccfa71eb4d2
ms.sourcegitcommit: 754fcc31155b28d6910bba45419c6be745f8793e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/14/2018
---
# <a name="how-to-add-built-in-apps-to-microsoft-intune"></a>Jak dodawać wbudowane aplikacje do usługi Microsoft Intune

Aplikacja typu **wbudowanego** ułatwia przypisanie nadzorowanych zarządzanych aplikacji, takich jak aplikacje usługi Office 365, do urządzeń z systemem iOS i Android. Do tego typu aplikacji możesz przypisać określone aplikacje, takie jak Excel, OneDrive, Outlook, Skype i inne. Po dodaniu aplikacji zobaczysz typ aplikacji jako **Wbudowana aplikacja systemu iOS** lub **Wbudowana aplikacja systemu Android**. Za pomocą typu wbudowanej aplikacji możesz wybrać, które z tych określonych aplikacji mają być opublikowane dla użytkowników urządzenia.

 We wcześniejszych wersjach konsoli usługi Intune usługa Intune udostępniała kilka domyślnych zarządzanych aplikacji usługi Office 365, takich jak Outlook i OneDrive. Typ aplikacji dla tych zarządzanych aplikacji został oznaczony jako „Zarządzana aplikacja w sklepie dla systemu iOS” lub „Zarządzana aplikacja dla systemu Android”. Zaleca się używanie wbudowanego typu aplikacji zamiast typu „Zarządzana aplikacja w sklepie dla systemu iOS” lub „Zarządzana aplikacja dla systemu Android”. Wbudowany typ aplikacji zapewnia dodatkową elastyczność na potrzeby edytowania i usuwania aplikacji usługi Office 365.

>[!NOTE]
>Domyślne aplikacje usługi Office 365 oznaczone jako „Zarządzana w sklepie dla systemu iOS” i „Zarządzana aplikacja dla systemu Android” zostaną usunięte z listy aplikacji, gdy zostaną usunięte wszystkie przypisania.

## <a name="add-built-in-app"></a>Dodawanie wbudowanej aplikacji

Poniższe kroki umożliwiają dodanie wbudowanej aplikacji do dostępnych dla Ciebie aplikacji w usłudze Microsoft Intune.
1.  Zaloguj się do portalu Azure Portal.
2.  Wyświetl blok usługi Microsoft Intune, wybierając pozycje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3.  W bloku **Intune** wybierz pozycję **Aplikacje mobilne**.
4.  W bloku **Aplikacje mobilne** wybierz pozycję **Aplikacje** w grupie **Zarządzaj**.
5.  Wybierz pozycję **Dodaj**, aby dodać nową aplikację.
6.  W bloku aplikacji **Dodaj** wybierz pozycję **Wbudowana aplikacja** z listy **Typ aplikacji**.
7.  Kliknij pozycję **Wybierz aplikację**, aby wybrać wbudowane aplikacje do dołączenia.
8.  W bloku Wbudowana aplikacja wybierz aplikacje do dołączenia.
9.  W bloku **Dodaj aplikację** kliknij przycisk **Dodaj**, aby dołączyć aplikacje.


## <a name="configure-app-information"></a>Konfigurowanie informacji o aplikacji

Możesz zmodyfikować informacje o wbudowanej aplikacji. Te informacje pomagają zidentyfikować aplikację w usłudze Intune, a także ułatwiają użytkownikom odnalezienie aplikacji w aplikacji Portal firmy.
1.  W bloku **Aplikacje mobilne — aplikacje** wybierz wbudowaną aplikację, którą chcesz zmodyfikować. Zostanie wyświetlony blok dla wbudowanej aplikacji.
2.  Wybierz opcję **Właściwości** z grupy **Zarządzaj**.
3.  Wybierz opcję **Konfiguruj**, aby zmodyfikować informacje o wbudowanej aplikacji.
4.  W bloku **Informacje o aplikacji** możesz zmodyfikować następujące informacje:
    -   **Nazwa** — wprowadź nazwę wbudowanej aplikacji taką, jaka jest wyświetlana w Portalu firmy. Upewnij się, że wszystkie używane nazwy są unikatowe. Jeśli dana nazwa aplikacji występuje dwa razy, użytkownicy Portalu firmy będą widzieć tylko jedną z aplikacji o tej nazwie.
    -   **Opis** — wprowadź opis aplikacji. 
    -   **Wydawca** — wprowadź nazwę wydawcy aplikacji.
    -   **Kategoria** — opcjonalnie wybierz przynajmniej jedną z kategorii wbudowanych aplikacji. Ustawienie tej opcji ułatwi użytkownikom znajdowanie aplikacji podczas przeglądania Portalu firmy.
    -   **Wyświetl jako polecaną aplikację w portalu firmy** — wyróżnij aplikację na stronie głównej portalu firmy dla użytkowników przeglądających aplikacje.
    -   **Adres URL informacji** — opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    -   **Adres URL zasad ochrony prywatności** — opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o zasadach ochrony prywatności mających zastosowanie do aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    -   **Deweloper** — opcjonalnie wprowadź nazwę dewelopera aplikacji.
    -   **Właściciel** — opcjonalnie wprowadź nazwę właściciela aplikacji, na przykład Dział kadr.
    -   **Uwagi** — wprowadź wszelkie uwagi, które chcesz skojarzyć z aplikacją.
    -   **Przekaż ikonę** — przekaż ikonę, która jest wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
3.  Po zakończeniu w bloku **Informacje o aplikacji** kliknij przycisk **OK**.
4.  Kliknij przycisk **Zapisz** w bloku **Właściwości**.

## <a name="next-steps"></a>Następne kroki

Teraz można przypisać aplikacje do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).
