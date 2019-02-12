---
title: Dodawanie aplikacji internetowych do usługi Microsoft Intune
titleSuffix: ''
description: Dowiedz się więcej na temat dodawania aplikacji internetowych (aplikacji typu klient-serwer) do usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0698a6b3010ad2177d4f593bf4d75ea2ff6a31dc
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55839206"
---
# <a name="add-web-apps-to-microsoft-intune"></a>Dodawanie aplikacji internetowych do usługi Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Usługa Intune obsługuje różne typy aplikacji, w tym aplikacje internetowe. Aplikacja internetowa to aplikacja typu klient/serwer. Serwer udostępnia aplikację internetową, która obejmuje interfejs użytkownika, zawartość i funkcje. Ponadto nowoczesne internetowe platformy hostingowe często oferują zabezpieczenia, równoważenie obciążenia i inne korzyści. Aplikacja internetowa jest obsługiwana oddzielnie w Internecie. Usługa Microsoft Intune umożliwia wskazanie tego typu aplikacji. Można także przypisać grupy użytkowników, które będą mogły uzyskiwać dostęp do takiej aplikacji. 

Aby można było zarządzać aplikacją oraz przypisywać ją do użytkowników, należy dodać ją do usługi Intune. Usługa Intune tworzy skrót do aplikacji internetowej na ekranie głównym urządzenia użytkownika.

> [!Note]
> Aplikacje internetowe nie są obsługiwane na urządzeniach z profilami służbowymi systemu Android i systemem macOS.

## <a name="add-a-web-app-to-intune"></a>Dodawanie aplikacji internetowej do usługi Intune
Aby dodać aplikację do usługi Intune jako skrót do aplikacji w Internecie, wykonaj następujące czynności:

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**.  
    Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Aplikacje klienckie**.
4. W okienku obciążenia **Aplikacje klienckie** w obszarze **Zarządzanie** wybierz pozycję **Aplikacje**.
5. W okienku **Aplikacje** wybierz pozycję **Dodaj**.
6. W okienku **Dodaj aplikację** wybierz typ **Link internetowy** z listy rozwijanej **Typ aplikacji**.
7. Wybierz pozycję **Konfiguruj**.
8. W okienku **Informacje o aplikacji** dodaj następujące informacje:
    - **Nazwa**:  wprowadź nazwę aplikacji, która ma być wyświetlana w Portalu firmy. 
    
        > [!NOTE]
        > Jeśli po wdrożeniu i zainstalowaniu aplikacji zmienisz jej nazwę za pośrednictwem witryny Azure Portal usługi Intune, nie będzie można już więcej oddziaływać na tę aplikację przy użyciu poleceń.
    
    - **Opis**: Wprowadź opis aplikacji. Ten opis jest wyświetlany użytkownikom Portalu firmy.
    - **Wydawca**: wprowadź nazwę wydawcy tej aplikacji.
    - **Adres URL aplikacji**: wprowadź adres URL witryny hostującej aplikację, którą chcesz przypisać.
    - **Kategoria**: opcjonalnie wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. Ułatwi to użytkownikom znajdowanie aplikacji podczas przeglądania Portalu firmy.
    - **Wyświetl jako polecaną aplikację w Portalu firmy**: wybierz tę opcję, aby wyświetlić pakiet aplikacji w dobrze widocznym miejscu na stronie głównej portalu firmy podczas przeglądania aplikacji przez użytkowników.
    - **Wymagaj zarządzanej przeglądarki do otworzenia tego linku**: wybierz tę opcję, aby przypisać do użytkowników link do witryny lub aplikacji internetowej, który będą mogli otworzyć w przeglądarce Intune Managed Browser. Ten program musi być zainstalowany na urządzeniu.
    - **Logo**: Przekaż ikonę, która zostanie skojarzona z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
9. Wybierz przycisk **OK**.
10. W okienku **Dodaj aplikację** wybierz pozycję **Dodaj**.

> [!Note]
> Użytkownicy muszą dodać widżet usługi Intune do ekranu głównego, aby móc wyświetlać aplikacje internetowe przypisane do urządzeń z systemem Android.
>
> Obecnie wdrożenie aplikacji internetowych usługi Intune na urządzeniach z systemem iOS jest skojarzone z profilem zarządzania i nie można usunąć go ręcznie. Typ wdrożenia można zmienić na **Odinstaluj** w portalu usługi Intune. Po wykonaniu tej czynności będzie można automatycznie usuwać aplikację internetową. Jednak w przypadku usunięcia wdrożenia przed zmianą intencji przypisywania aplikacji na **Odinstaluj** aplikacja internetowa zostanie trwale umieszczona na urządzeniu do momentu wyrejestrowania go z usługi Intune.

## <a name="next-steps"></a>Następne kroki

Utworzona aplikacja będzie wyświetlana na liście aplikacji, z której można ją przypisać do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [Assign apps to groups (Przypisywanie aplikacji do grup)](apps-deploy.md). 
