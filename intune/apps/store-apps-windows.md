---
title: Dodawanie aplikacji ze sklepu Microsoft Store do usługi Microsoft Intune
titleSuffix: ''
description: Informacje o dodawaniu aplikacji ze sklepu Microsoft Store (Windows Store) do usługi Microsoft Intune.
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
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3c13d7960c0bb5c73908a0a574ab7d6c169d6460
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563436"
---
# <a name="add-microsoft-store-apps-to-microsoft-intune"></a>Dodawanie aplikacji ze sklepu Microsoft Store do usługi Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Aby móc przypisywać, monitorować, konfigurować lub zabezpieczać aplikacje, trzeba je najpierw dodać do usługi Intune. 

## <a name="add-an-app-to-intune"></a>Dodawanie aplikacji do usługi Intune
Możesz dodać aplikację ze sklepu Microsoft Store do usługi Intune, wykonując następujące czynności:

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**.
3. W okienku **Dodaj aplikację** w obszarze **Typ aplikacji** wybierz pozycję **Windows** i wybierz pozycję **Informacje o aplikacji**.
4. W okienku **Informacje o aplikacji** dodaj informacje dotyczące aplikacji. W zależności od wybranej aplikacji niektóre wartości w tym okienku mogą zostać wypełnione automatycznie:
    - **Nazwa**: wprowadź nazwę aplikacji, która ma być wyświetlana w Portalu firmy. Upewnij się, że każda używana nazwa aplikacji jest unikatowa. Jeśli nazwa aplikacji będzie zduplikowana, użytkownicy zobaczą tylko jedną nazwę w Portalu firmy.
    - **Opis**: Wprowadź opis aplikacji. Ten opis jest wyświetlany użytkownikom Portalu firmy.
    - **Wydawca**: Wprowadź nazwę wydawcy aplikacji.
    - **Adres URL sklepu App Store**: wpisz adres URL sklepu App Store dla aplikacji, którą chcesz utworzyć. Adres URL można znaleźć, wyszukując żądaną aplikację w sklepie [Microsoft Store](https://store.microsoft.com). Użyj adresu URL z paska adresu przeglądarki.
    - **Kategoria**: opcjonalnie wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. Ułatwi to użytkownikom znajdowanie aplikacji podczas przeglądania Portalu firmy.
    - **Wyświetl jako polecaną aplikację w Portalu firmy**: wybierz tę opcję, aby wyświetlić pakiet aplikacji w dobrze widocznym miejscu na stronie głównej portalu firmy podczas przeglądania aplikacji przez użytkowników.
    - **Adres URL informacji**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Adres URL zasad ochrony prywatności**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje dotyczące zasad ochrony prywatności w tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Deweloper**: opcjonalnie wprowadź nazwę dewelopera aplikacji.
    - **Właściciel**: opcjonalnie wprowadź nazwę właściciela aplikacji, na przykład *Dział kadr*.
    - **Uwagi**: opcjonalnie wprowadź wszelkie uwagi, które chcesz skojarzyć z tą aplikacją.
    - **Logo**: opcjonalnie przekaż ikonę, która zostanie skojarzona z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
5. Wybierz przycisk **OK**.
6. Wybierz pozycję **Dodaj**.

Utworzona aplikacja będzie wyświetlana na liście aplikacji, z której można ją przypisać do wybranych grup. Aplikacje ze sklepu Microsoft Store można przypisać tylko do grup z typem przypisania **Dostępne dla zarejestrowanych urządzeń** (użytkownicy instalują aplikację z aplikacji Portal firmy lub witryny internetowej).

## <a name="next-steps"></a>Następne kroki
- [Przypisywanie aplikacji do grup](apps-deploy.md)
