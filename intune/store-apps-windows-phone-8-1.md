---
title: Dodawanie aplikacji ze sklepu z aplikacjami dla systemu Windows Phone 8.1 do usługi Microsoft Intune
titleSuffix: ''
description: W tym temacie opisano jak dodawać aplikacje ze sklepu z aplikacjami dla systemu Windows Phone 8.1 do usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4a95e575-2c63-4bfc-b9c4-f0a132eef618
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 5892ffe0369ae7b43489c1ce5c327f88c0d857f3
ms.sourcegitcommit: 4e69a8664c289263490daa4c02bc6b81c33196e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2018
ms.locfileid: "53642527"
---
# <a name="add-windows-phone-81-store-apps-to-microsoft-intune"></a>Dodawanie aplikacji ze sklepu z aplikacjami dla systemu Windows Phone 8.1 do usługi Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Przed przypisaniem aplikacji do urządzenia lub grupy użytkowników należy najpierw dodać aplikację do usługi Microsoft Intune. 

## <a name="add-an-app-to-intune"></a>Dodawanie aplikacji do usługi Intune
Możesz dodawać aplikacje ze sklepu z aplikacjami dla systemu Windows Phone 8.1 do usługi Intune w witrynie Azure Portal, wykonując następujące czynności:

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**.  
    Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Aplikacje klienckie**.
4. W okienku obciążenia **Aplikacje klienckie** w obszarze **Zarządzanie** wybierz pozycję **Aplikacje**.
5. W okienku **Aplikacje** wybierz pozycję **Dodaj**.
6. W okienku **Dodaj aplikację** w obszarze **Typ aplikacji** wybierz pozycję **Windows Phone 8.1** i wybierz pozycję **Informacje o aplikacji**.
7. W okienku **Informacje o aplikacji** dodaj informacje dotyczące aplikacji. W zależności od wybranej aplikacji niektóre wartości w tym okienku mogą zostać wypełnione automatycznie:
    - **Nazwa**: Wprowadź nazwę aplikacji, która ma być wyświetlana w Portalu firmy. Upewnij się, że każda używana nazwa aplikacji jest unikatowa. Jeśli nazwa aplikacji będzie zduplikowana, użytkownicy zobaczą tylko jedną nazwę w Portalu firmy.
    - **Opis**: Wprowadź opis aplikacji. Ten opis jest wyświetlany użytkownikom Portalu firmy.
    - **Wydawca**: Wprowadź nazwę wydawcy aplikacji.
    - **Adres URL sklepu App Store**: Wpisz adres URL sklepu App Store dla aplikacji, którą chcesz utworzyć.
    - **Kategoria**: Opcjonalnie wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. Ułatwi to użytkownikom znajdowanie aplikacji podczas przeglądania Portalu firmy.
    - **Wyświetl jako polecaną aplikację w portalu firmy**: Wybierz tę opcję, aby wyświetlić pakiet aplikacji w dobrze widocznym miejscu na stronie głównej portalu firmy podczas przeglądania aplikacji przez użytkowników.
    - **Adres URL informacji**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Adres URL zasad ochrony prywatności**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje dotyczące zasad ochrony prywatności w tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Deweloper**: Opcjonalnie wprowadź nazwę dewelopera aplikacji.
    - **Właściciel**: Opcjonalnie wprowadź nazwę właściciela aplikacji, na przykład *Dział kadr*.
    - **Uwagi**: Opcjonalnie wprowadź wszelkie uwagi, które chcesz skojarzyć z tą aplikacją.
    - **Logo**: Opcjonalnie przekaż ikonę, która zostanie skojarzona z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
8. Wybierz przycisk **OK**.
9. Wybierz pozycję **Dodaj**.

Utworzona aplikacja będzie wyświetlana na liście aplikacji, z której można ją przypisać do wybranych grup.

## <a name="next-steps"></a>Następne kroki

- [Przypisywanie aplikacji do grup](apps-deploy.md)
