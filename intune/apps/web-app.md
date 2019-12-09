---
title: Dodawanie aplikacji internetowych do usługi Microsoft Intune
titleSuffix: ''
description: Dowiedz się więcej na temat dodawania aplikacji internetowych (aplikacji typu klient-serwer) do usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 68e2e768067a88b8ae58adeb38c17d90ac995a30
ms.sourcegitcommit: b752acefec077c719e169e665c955adb944e85c6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74781230"
---
# <a name="add-web-apps-to-microsoft-intune"></a>Dodawanie aplikacji internetowych do usługi Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Usługa Intune obsługuje różne typy aplikacji, w tym aplikacje internetowe. Aplikacja internetowa to aplikacja typu klient/serwer. Serwer udostępnia aplikację internetową, która obejmuje interfejs użytkownika, zawartość i funkcje. Ponadto nowoczesne internetowe platformy hostingowe często oferują zabezpieczenia, równoważenie obciążenia i inne korzyści. Aplikacja internetowa jest obsługiwana oddzielnie w Internecie. Usługa Microsoft Intune umożliwia wskazanie tego typu aplikacji. Można także przypisać grupy użytkowników, które będą mogły uzyskiwać dostęp do takiej aplikacji. 

Aby można było zarządzać aplikacją oraz przypisywać ją do użytkowników, należy dodać ją do usługi Intune. 

Usługa Intune tworzy skrót do aplikacji internetowej na urządzeniu użytkownika. W przypadku urządzeń z systemem iOS skrót do aplikacji internetowej jest dodawany do ekranu głównego. W przypadku urządzeń administratora z systemem Android skrót do aplikacji internetowej jest dodawany do widżetu Portal firmy usługi Intune, a widżet musi zostać przypięty ręcznie przez użytkownika. W przypadku urządzeń z systemem Windows skrót do aplikacji internetowej jest umieszczany w menu Start.

> [!Note]
> Aby można było uruchamiać aplikacje internetowe, na urządzeniu użytkownika musi być zainstalowana przeglądarka. 

> [!Note]
> Informacje dotyczące urządzeń z systemem Android Enterprise znajdują się w sekcji [Linki sieci Web z zarządzanego sklepu Google Play](apps-add-android-for-work.md#managed-google-play-web-links)

## <a name="add-a-web-app-to-intune"></a>Dodawanie aplikacji internetowej do usługi Intune
Aby dodać aplikację do usługi Intune jako skrót do aplikacji w Internecie, wykonaj następujące czynności:

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz kolejno pozycje **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**.
3. W okienku **Dodaj aplikację** wybierz typ **Link internetowy** z listy rozwijanej **Typ aplikacji**.
4. Wybierz pozycję **Konfiguruj**.
5. W okienku **Informacje o aplikacji** dodaj następujące informacje:
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
6. Wybierz przycisk **OK**.
7. W okienku **Dodaj aplikację** wybierz pozycję **Dodaj**.

> [!Note]
> Obecnie wdrożenie aplikacji internetowych usługi Intune na urządzeniach z systemem iOS jest skojarzone z profilem zarządzania i nie można usunąć go ręcznie. Typ wdrożenia można zmienić na **Odinstaluj** w portalu usługi Intune. Po wykonaniu tej czynności będzie można automatycznie usuwać aplikację internetową. Jednak w przypadku usunięcia wdrożenia przed zmianą intencji przypisywania aplikacji na **Odinstaluj** aplikacja internetowa zostanie trwale umieszczona na urządzeniu do momentu wyrejestrowania go z usługi Intune.

Użytkownicy końcowi mogą uruchamiać aplikacje internetowe bezpośrednio z poziomu aplikacji Portal firmy systemu Windows, wybierając aplikację internetową, a następnie wybierając opcję **Otwórz w przeglądarce**. Opublikowany internetowy adres URL zostanie otwarty bezpośrednio w przeglądarce. 

## <a name="next-steps"></a>Następne kroki

Utworzona aplikacja będzie wyświetlana na liście aplikacji, z której można ją przypisać do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [Assign apps to groups (Przypisywanie aplikacji do grup)](apps-deploy.md). 
