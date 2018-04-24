---
title: Jak dodawać aplikacje sieci Web do usługi Microsoft Intune
titleSuffix: ''
description: Informacje o dodawaniu aplikacji internetowych do usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 45253e061039198aee4aa49b2bf879a1b9929e35
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Jak dodawać aplikacje sieci Web do usługi Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Usługa Intune obsługuje różne typy aplikacji, w tym aplikacje sieci Web. Aplikacja internetowa to aplikacja typu klient/serwer. Serwer udostępnia aplikację internetową, która obejmuje interfejs użytkownika, zawartość i funkcje. Ponadto nowoczesne internetowe platformy hostingowe często oferują zabezpieczenia, równoważenie obciążenia i inne korzyści. Aplikacja internetowa jest obsługiwana oddzielnie w Internecie. Usługa Microsoft Intune umożliwia wskazanie tego typu aplikacji. Można także przypisać grupy użytkowników, które będą mogły uzyskiwać dostęp do takiej aplikacji. 

Aby można było zarządzać aplikacją oraz przypisywać ją do użytkowników, należy dodać ją do usługi Intune. Usługa Intune tworzy skrót do aplikacji internetowej na ekranie głównym urządzenia użytkownika.

> [!Note]
> Aplikacje internetowe nie są obsługiwane na urządzeniach z programem Android for Work i systemem macOS.

Wykonaj poniższe kroki, aby dodać aplikację do usługi Intune jako skrót do aplikacji w sieci Web:

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Microsoft Intune** wybierz pozycję **Aplikacje mobilne**.
4. W okienku **Aplikacje mobilne** wybierz pozycję **Aplikacje**.
5. Wybierz pozycję **Dodaj** powyżej listy aplikacji. Zostanie wyświetlone okienko **Dodaj aplikację**.
6. W okienku **Dodaj aplikację** wybierz typ **Link internetowy** z listy rozwijanej **Typ aplikacji**.
7. Wybierz opcję **Konfiguruj**, aby wyświetlić okienko **Informacje o aplikacji**.
8. W okienku **Informacje o aplikacji** dodaj następujące informacje:
    - **Nazwa** — wprowadź nazwę aplikacji, która ma być wyświetlana w portalu firmy.
    - **Opis** — wprowadź opis aplikacji. Będzie on widoczny dla użytkowników w portalu firmy.
    - **Wydawca** — wprowadź nazwę wydawcy tej aplikacji.
    - **Adres URL aplikacji** — wprowadź adres URL witryny hostującej aplikację, którą chcesz przypisać.
    - **Kategoria (opcjonalnie)** — wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. Ułatwi to użytkownikom znajdowanie aplikacji podczas przeglądania portalu firmy.
    - **Wyświetl jako polecaną aplikację w portalu firmy** — wyróżnij aplikację na stronie głównej portalu firmy dla użytkowników przeglądających aplikacje.
    - **Wymagaj zarządzanej przeglądarki do otworzenia tego linku** — użytkownicy będą mogli otworzyć link przypisany do witryny lub przypisaną do nich aplikację sieci Web w przeglądarce zarządzanej przez usługę Intune. Ten program musi być zainstalowany na urządzeniu.
    - **Logo** — przekaż logo skojarzone z aplikacją. Jest to logo, które będzie wyświetlane razem z nazwą aplikacji podczas przeglądania portalu firmy.
9. Po zakończeniu w okienku **Dodaj informacje** wybierz pozycję **OK**.
10. Następnie w okienku **Dodaj aplikację** wybierz pozycję **Dodaj**.

> [!Note]
> Użytkownicy muszą dodać widżet usługi Intune do ekranu głównego, aby móc wyświetlać aplikacje internetowe przypisane do urządzeń z systemem Android.

## <a name="next-steps"></a>Następne kroki

- Utworzona aplikacja będzie wyświetlana na liście aplikacji, z której można ją przypisać do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).