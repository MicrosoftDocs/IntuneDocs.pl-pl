---
title: Dodawanie aplikacji ze sklepu Microsoft Store do usługi Microsoft Intune
titleSuffix: ''
description: Informacje o dodawaniu aplikacji ze sklepu Microsoft Store (Windows Store) do usługi Microsoft Intune.
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
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8743af2a05f6daebca5e1394ba5b7b8f13fcf7e3
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2020
ms.locfileid: "76754919"
---
# <a name="add-microsoft-store-apps-to-microsoft-intune"></a>Dodawanie aplikacji ze sklepu Microsoft Store do usługi Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Aby móc przypisywać, monitorować, konfigurować lub zabezpieczać aplikacje, trzeba je najpierw dodać do usługi Intune. 

## <a name="add-an-app-to-intune"></a>Dodawanie aplikacji do usługi Intune
Możesz dodać aplikację ze sklepu Microsoft Store do usługi Intune, wykonując następujące czynności:

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**.
3. W okienku **Wybierz typ aplikacji** w obszarze dostępnych typów **Aplikacja ze sklepu** wybierz pozycję **Aplikacja ze Sklepu Windows**.
4. Kliknij pozycję **Wybierz**. Zostaną wyświetlone kroki **dodawania aplikacji**.
5. Aby skonfigurować **informacje o aplikacji** dotyczące aplikacji ze sklepu Windows, przejdź do [sklepu Google Play](https://www.microsoft.com/store/apps) i wyszukaj aplikację, którą chcesz wdrożyć. Wyświetl stronę aplikacji i zanotuj jej szczegóły. 
6. Na stronie **Informacje o aplikacji** dodaj szczegóły aplikacji:
    - **Nazwa**: wprowadź nazwę aplikacji, która ma być wyświetlana w Portalu firmy. Upewnij się, że każda używana nazwa aplikacji jest unikatowa. Jeśli nazwa aplikacji będzie zduplikowana, użytkownicy zobaczą tylko jedną nazwę w Portalu firmy.
    - **Opis**: Wprowadź opis aplikacji. Ten opis jest wyświetlany użytkownikom Portalu firmy.
    - **Wydawca**: Wprowadź nazwę wydawcy aplikacji.
    - **Adres URL sklepu App Store**: wpisz adres URL sklepu App Store dla aplikacji, którą chcesz utworzyć. Adres URL można znaleźć, wyszukując żądaną aplikację w sklepie [Microsoft Store](https://www.microsoft.com/store/apps). Użyj adresu URL z paska adresu przeglądarki.
    - **Kategoria**: opcjonalnie wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. Ułatwi to użytkownikom znajdowanie aplikacji podczas przeglądania Portalu firmy.
    - **Pokaż jako polecaną aplikację w Portalu firmy**: wybierz tę opcję, aby wyświetlić pakiet aplikacji w dobrze widocznym miejscu na stronie głównej portalu firmy podczas przeglądania aplikacji przez użytkowników.
    - **Adres URL informacji**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Adres URL zasad ochrony prywatności**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje dotyczące zasad ochrony prywatności w tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Deweloper**: opcjonalnie wprowadź nazwę dewelopera aplikacji.
    - **Właściciel**: opcjonalnie wprowadź nazwę właściciela aplikacji, na przykład *Dział kadr*.
    - **Uwagi**: opcjonalnie wprowadź wszelkie uwagi, które chcesz skojarzyć z tą aplikacją.
    - **Logo**: opcjonalnie przekaż ikonę, która zostanie skojarzona z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
7. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Tagi zakresu**.
8. Kliknij pozycję **Wybierz tagi zakresu**, aby opcjonalnie dodać tagi zakresu dla aplikacji. Aby uzyskać więcej informacji, zobacz temat [Używanie kontroli dostępu opartej na rolach i tagów zakresu w rozproszonej infrastrukturze informatycznej](~/fundamentals/scope-tags.md).
9. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Przypisania**.
10. Wybierz przypisania grupy dla aplikacji. Aby uzyskać więcej informacji, zobacz temat [Dodawanie grup w celu organizowania użytkowników i urządzeń](~/fundamentals/groups-add.md). 
11. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Recenzja i tworzenie**. Przejrzyj wartości i ustawienia wprowadzone dla aplikacji.
12. Gdy skończysz, kliknij pozycję **Utwórz**, aby dodać aplikację do usługi Intune.

Zostanie wyświetlony blok **Omówienie** dotyczący utworzonej aplikacji.

Utworzona aplikacja będzie wyświetlana na liście aplikacji, z której można ją przypisać do wybranych grup.

> [!IMPORTANT]
> Aplikacje ze sklepu Microsoft Store można przypisać tylko do grup z typem przypisania **Dostępne dla zarejestrowanych urządzeń** (użytkownicy instalują aplikację z aplikacji Portal firmy lub witryny internetowej).

## <a name="next-steps"></a>Następne kroki
- [Przypisywanie aplikacji do grup](apps-deploy.md)
