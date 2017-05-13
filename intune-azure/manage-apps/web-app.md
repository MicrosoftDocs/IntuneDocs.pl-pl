---
title: "Dodawanie aplikacji sieci Web do usługi Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje na temat dodawania aplikacji sieci Web do usługi Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: a9748a0ad6b9bbe10e36ba133ba74edb6aa6e09a
ms.openlocfilehash: 4b6e8d72085edc3de41b7dcdb4fe5b09f5561601
ms.contentlocale: pl-pl
ms.lasthandoff: 05/05/2017

---

# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Jak dodawać aplikacje sieci Web do usługi Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Zarządzaj aplikacjami**.
4. W obciążeniu **Aplikacje mobilne** wybierz kolejno pozycje **Zarządzaj** > **Aplikacje**.
5. Wybierz pozycję **Dodaj** powyżej listy aplikacji.
6. W bloku **Dodaj aplikację** wybierz pozycję **Informacje o aplikacji**.
7. W bloku **Edytuj aplikację** skonfiguruj następujące informacje. Po zakończeniu kliknij pozycję **Dodaj**:
    - **Adres URL aplikacji** — wprowadź adres URL witryny hostującej aplikację, którą chcesz przypisać.
    - **Nazwa aplikacji** — wprowadź nazwę aplikacji, która będzie wyświetlana w Portalu firmy.
    - **Opis aplikacji** — wprowadź opis aplikacji. Będzie on widoczny dla użytkowników w portalu firmy.
    - **Wydawca** — wprowadź nazwę wydawcy tej aplikacji.
    - **Kategoria** (opcjonalnie) — wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. Ułatwi to użytkownikom znajdowanie aplikacji podczas przeglądania Portalu firmy.
    - **Wyświetl jako polecaną aplikację w portalu firmy** — wyróżnij aplikację na stronie głównej portalu firmy dla użytkowników przeglądających aplikacje.
    - **Wymagaj zarządzanej przeglądarki do otworzenia tego linku** — użytkownicy będą mogli otworzyć link przypisany do witryny lub aplikacji sieci Web tylko w przeglądarce zarządzanej przez usługę Intune. Ten program musi być zainstalowany na urządzeniu.
    - **Przekaż ikonę** — przekaż ikonę, która zostanie skojarzona z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
8. Gdy wszystko będzie gotowe, w bloku **Dodaj aplikację** wybierz pozycję **Zapisz**.

Utworzona aplikacja będzie wyświetlana na liście aplikacji, skąd można ją przypisać do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](/intune-azure/manage-apps/deploy-apps) (Jak przypisać aplikacje do grupy).
