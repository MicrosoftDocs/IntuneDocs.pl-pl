---
title: "Dodawanie aplikacji sieci Web do usługi Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje na temat dodawania aplikacji sieci Web do usługi Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: c2e54d3e57a4b02ba277b88cc672d5587c449281
ms.lasthandoff: 02/18/2017

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
    - **Adres URL aplikacji** — wprowadź adres URL witryny hostującej aplikację, którą chcesz wdrożyć.
    - **Nazwa aplikacji** — wprowadź nazwę aplikacji, która będzie wyświetlana w portalu firmy.
    - **Opis aplikacji** — wprowadź opis aplikacji. Będzie on widoczny dla użytkowników w portalu firmy.
    - **Wydawca** — wprowadź nazwę wydawcy tej aplikacji.
    - **Kategoria** (opcjonalnie) — wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. Ułatwi to użytkownikom znajdowanie aplikacji podczas przeglądania Portalu firmy.
    - **Wyświetl jako polecaną aplikację w portalu firmy** — wyróżnij aplikację na stronie głównej portalu firmy dla użytkowników przeglądających aplikacje.
    - **Wymagaj zarządzanej przeglądarki do otworzenia tego linku** — użytkownicy będą mogli otworzyć wdrożony link do witryny lub aplikacji sieci Web tylko w przeglądarce zarządzanej przez usługę Intune. Ten program musi być zainstalowany na urządzeniu.
    - **Przekaż ikonę** — przekaż ikonę, która zostanie skojarzona z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
8. Gdy wszystko będzie gotowe, w bloku **Dodaj aplikację** wybierz pozycję **Zapisz**.

Utworzona aplikacja będzie wyświetlana na liście aplikacji, skąd można ją przypisać do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](/intune-azure/manage-apps/deploy-apps) (Jak przypisać aplikacje do grupy).
