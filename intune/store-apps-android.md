---
title: Dodawanie aplikacji ze sklepu z aplikacjami dla systemu Android do usługi Microsoft Intune
titleSuffix: ''
description: Informacje o dodawaniu aplikacji ze sklepu z aplikacjami dla systemu Android do usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4433000a-23e9-4cad-a818-48c28eedc1f5
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f62cb3a99a9cfd328cc041f095b0980eacc99852
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="add-android-store-apps-to-microsoft-intune"></a>Dodawanie aplikacji ze sklepu z aplikacjami dla systemu Android do usługi Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Przed przypisaniem aplikacji do urządzenia lub grupy użytkowników należy najpierw dodać aplikację do usługi Microsoft Intune. Możesz dodawać aplikacje ze sklepu dla systemu Android do usługi Intune w witrynie Azure Portal, wykonując następujące czynności:

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**.  
    Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
1. W okienku **Intune** wybierz pozycję **Aplikacje mobilne**.
2. W okienku obciążenia **Aplikacje mobilne** w obszarze **Zarządzaj** wybierz pozycję **Aplikacje**.
3. Wybierz pozycję **Dodaj**.
4. W okienku **Dodaj aplikację** wybierz pozycję **Android** w obszarze dostępnych typów **aplikacji ze sklepu**.
5. Aby skonfigurować informacje o aplikacji, wybierz pozycję **Konfiguruj**, a następnie podaj następujące informacje.  
    W zależności od wybranej aplikacji niektóre wartości mogą zostać wypełnione automatycznie.
    - **Nazwa**: wprowadź nazwę aplikacji, która ma być wyświetlana w Portalu firmy. Upewnij się, że każda używana nazwa aplikacji jest unikatowa. Jeśli nazwa aplikacji będzie zduplikowana, użytkownicy zobaczą tylko jedną nazwę w Portalu firmy.
    - **Opis**: wprowadź opis aplikacji. Ten opis jest wyświetlany użytkownikom Portalu firmy.
    - **Wydawca**: wprowadź nazwę wydawcy aplikacji.
    - **Adres URL sklepu z aplikacjami**: wprowadź adres URL sklepu z aplikacjami dla aplikacji, którą chcesz utworzyć.
    - **Minimalna wersja systemu operacyjnego**: wybierz z listy najwcześniejszą wersję systemu operacyjnego, w której można zainstalować aplikację. W przypadku przypisania aplikacji do urządzenia z wcześniejszą wersją systemu operacyjnego instalacja nie będzie możliwa.
    - **Kategoria**: opcjonalnie wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. Ułatwi to użytkownikom znajdowanie aplikacji podczas przeglądania Portalu firmy.
    - **Wyświetl jako polecaną aplikację w Portalu firmy**: wybierz tę opcję, aby wyświetlić pakiet aplikacji na stronie głównej portalu firmy podczas przeglądania aplikacji przez użytkowników.
    - **Adres URL informacji**: opcjonalnie wprowadź adres URL witryny internetowej zawierającej informacje o tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Adres URL zasad ochrony prywatności**: opcjonalnie wprowadź adres URL witryny internetowej zawierającej informacje o zasadach ochrony prywatności w tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Deweloper**: opcjonalnie wprowadź nazwę dewelopera aplikacji.
    - **Właściciel**: opcjonalnie wprowadź nazwę właściciela aplikacji, na przykład *Dział kadr*.
    - **Uwagi**: opcjonalnie wprowadź wszelkie uwagi, które chcesz skojarzyć z tą aplikacją.
    - **Logo**: opcjonalnie przekaż ikonę, która zostanie skojarzona z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
1. Wybierz przycisk **OK**.
2. Wybierz pozycję **Dodaj**.

Utworzona aplikacja będzie wyświetlana na liście aplikacji, z której można ją przypisać do wybranych grup. 

## <a name="next-steps"></a>Następne kroki

- [Przypisywanie aplikacji do grup](apps-deploy.md)