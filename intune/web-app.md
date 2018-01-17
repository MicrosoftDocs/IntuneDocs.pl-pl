---
title: "Dodawanie aplikacji sieci Web do usługi Intune"
titleSuffix: Azure portal
description: "Informacje o dodawaniu aplikacji sieci Web do usługi Intune."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6da1441b16a43b5e22bedd9e87970f3388b11b9e
ms.sourcegitcommit: a3a744ea55f38a360ca9f788c77a5b3018d1add5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/30/2017
---
# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Jak dodawać aplikacje sieci Web do usługi Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Aby można było zarządzać aplikacją oraz przypisywać ją do użytkowników, należy dodać ją do usługi Intune. Usługa Intune obsługuje różne typy aplikacji, w tym aplikacje sieci Web.

> [!Note]
> Aplikacje sieci Web nie są obsługiwane na urządzeniach z programem Android for Work.

Wykonaj poniższe kroki, aby dodać aplikację do usługi Intune jako skrót do aplikacji w sieci Web:

1. Zaloguj się do portalu Azure Portal.
2. Korzystając z opcji **Więcej zasobów**, wyszukaj i wybierz pozycję **Intune**.
3. W bloku **Microsoft Intune** wybierz pozycję **Aplikacje mobilne**.
4. W bloku **Aplikacje mobilne** wybierz pozycję **Aplikacje**.
5. Wybierz pozycję **Dodaj** powyżej listy aplikacji. Zostanie wyświetlony blok **Dodaj aplikację**.
6. W bloku **Dodaj aplikację** wybierz typ **aplikacji sieci Web** z listy rozwijanej **Typ aplikacji**.
7. Wybierz opcję **Konfiguruj**, aby wyświetlić blok **Informacje o aplikacji**.
8. W bloku **Informacje o aplikacji** dodaj następujące informacje:
    - **Nazwa** — wprowadź nazwę aplikacji, która ma być wyświetlana w portalu firmy.
    - **Opis** — wprowadź opis aplikacji. Będzie on widoczny dla użytkowników w portalu firmy.
    - **Wydawca** — wprowadź nazwę wydawcy tej aplikacji.
    - **Adres URL aplikacji** — wprowadź adres URL witryny hostującej aplikację, którą chcesz przypisać.
    - **Kategoria (opcjonalnie)** — wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. Ułatwi to użytkownikom znajdowanie aplikacji podczas przeglądania portalu firmy.
    - **Wyświetl jako polecaną aplikację w portalu firmy** — wyróżnij aplikację na stronie głównej portalu firmy dla użytkowników przeglądających aplikacje.
    - **Wymagaj zarządzanej przeglądarki do otworzenia tego linku** — użytkownicy będą mogli otworzyć link przypisany do witryny lub przypisaną do nich aplikację sieci Web w przeglądarce zarządzanej przez usługę Intune. Ten program musi być zainstalowany na urządzeniu.
    - **Logo** — przekaż logo skojarzone z aplikacją. Jest to logo, które będzie wyświetlane razem z nazwą aplikacji podczas przeglądania portalu firmy.
9. Po zakończeniu w bloku **Dodaj informacje** wybierz pozycję **OK**.
10. Następnie w bloku **Dodaj aplikację** wybierz pozycję **Dodaj**.

Utworzona aplikacja będzie wyświetlana na liście aplikacji, z której można ją przypisać do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).