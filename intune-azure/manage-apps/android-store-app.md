---
title: "Dodawanie aplikacji ze sklepu z aplikacjami dla systemu Android do usługi Intune | Wersja zapoznawcza usługi Intune Azure | Dokumentacja firmy Microsoft"
description: "Wersja zapoznawcza usługi Intune Azure: informacje o dodawaniu aplikacji ze sklepu z aplikacjami dla systemu Android do usługi Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4433000a-23e9-4cad-a818-48c28eedc1f5
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 01e5bfeb98aee9314fa04679cc27c8aba0e18fb0
ms.openlocfilehash: ac3a901c4ecb900cb728c8dda04943071669f063

---

# <a name="how-to-add-android-store-apps-to-intune"></a>Jak dodać aplikacje ze sklepu z aplikacjami dla systemu Android do usługi Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku usługi Intune wybierz opcję **Zarządzaj aplikacjami**.
4. W obciążeniu **Aplikacje mobilne** wybierz kolejno pozycje **Zarządzaj** > **Aplikacje**.
5. Wybierz pozycję **Dodaj** powyżej listy aplikacji.
6. W bloku **Dodaj aplikację** wybierz pozycję **Informacje o aplikacji**.
7. W bloku **Edytuj aplikację** skonfiguruj następujące informacje. Gdy wszystko będzie gotowe, kliknij pozycję **Dodaj**. W zależności od wybranej aplikacji niektóre wartości w tym bloku mogą zostać wypełnione automatycznie:
    - **Nazwa aplikacji** — wprowadź nazwę aplikacji, która będzie wyświetlana w Portalu firmy. Upewnij się, że wszystkie używane nazwy aplikacji są unikatowe. Jeśli dana nazwa aplikacji występuje dwa razy, użytkownicy Portalu firmy będą widzieć tylko jedną z aplikacji o tej nazwie.
    - **Opis aplikacji** — wprowadź opis aplikacji. Ta informacja będzie widoczna dla użytkowników w Portalu firmy.
    - **Wydawca** — wprowadź nazwę wydawcy aplikacji.
    - **Adres URL sklepu z aplikacjami** — wprowadź adres URL sklepu z aplikacjami dla aplikacji, którą chcesz utworzyć.
    - **Minimalna wersja systemu operacyjnego** — wybierz z listy minimalną wersję systemu operacyjnego, na którym można zainstalować aplikację. W przypadku przypisania aplikacji do urządzenia z wcześniejszą wersją systemu operacyjnego instalacja nie będzie możliwa.
    - **Kategoria (opcjonalnie)** — wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. Ułatwi to użytkownikom znajdowanie aplikacji podczas przeglądania Portalu firmy.
    - **Wyświetl jako polecaną aplikację w portalu firmy** — wyróżnij aplikację na stronie głównej portalu firmy dla użytkowników przeglądających aplikacje.
    - **Adres URL informacji** — opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o aplikacji. Adres będzie widoczny dla użytkowników w Portalu firmy.
    - **Adres URL zasad ochrony prywatności** — opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o zasadach ochrony prywatności mających zastosowanie do aplikacji. Adres będzie widoczny dla użytkowników w Portalu firmy.
    - **Deweloper** — opcjonalnie wprowadź nazwę dewelopera aplikacji.
    - **Właściciel** — opcjonalnie wprowadź nazwę właściciela aplikacji, na przykład **Dział kadr**.
    - **Uwagi** — wprowadź wszelkie uwagi, które chcesz skojarzyć z aplikacją.
    - **Przekaż ikonę** — przekaż ikonę, która zostanie skojarzona z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
8. Gdy wszystko będzie gotowe, w bloku **Dodaj aplikację** wybierz pozycję **Zapisz**.

Utworzona aplikacja będzie wyświetlana na liście aplikacji, skąd można ją przypisać do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](/intune-azure/manage-apps/deploy-apps) (Jak przypisać aplikacje do grupy).


<!--HONumber=Feb17_HO1-->


