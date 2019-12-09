---
title: Dodawanie aplikacji ze sklepu z aplikacjami dla systemu Android do usługi Microsoft Intune
titleSuffix: ''
description: Dowiedz się, jak dodawać aplikacje dla systemu Android ze sklepu Google Play do usługi Microsoft Intune.
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
ms.assetid: 4433000a-23e9-4cad-a818-48c28eedc1f5
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ec800064d109cca42878c79ade6777de9b782015
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563500"
---
# <a name="add-android-store-apps-to-microsoft-intune"></a>Dodawanie aplikacji ze sklepu z aplikacjami dla systemu Android do usługi Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Przed przypisaniem aplikacji do urządzenia lub grupy użytkowników należy najpierw dodać aplikację do usługi Microsoft Intune. 

## <a name="add-an-app"></a>Dodawanie aplikacji

Możesz dodawać aplikacje ze sklepu dla systemu Android do usługi Intune w witrynie Azure Portal, wykonując następujące czynności:

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz kolejno pozycje **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**.
3. W okienku **Dodaj aplikację** wybierz pozycję **Android** w obszarze dostępnych typów **aplikacji ze sklepu**.
4. Aby skonfigurować informacje o aplikacji, wybierz pozycję **Konfiguruj**, a następnie podaj następujące informacje. W przypadku aplikacji systemu Android przejdź do [sklepu Google Play](https://play.google.com/store) i wyszukaj aplikację, którą chcesz wdrożyć. Wybierz aplikację, a następnie zanotuj szczegóły aplikacji. W zależności od wybranej aplikacji niektóre wartości mogą zostać wypełnione automatycznie.
    - **Nazwa**: wprowadź nazwę aplikacji, która ma być wyświetlana w Portalu firmy. Upewnij się, że każda używana nazwa aplikacji jest unikatowa. Jeśli nazwa aplikacji będzie zduplikowana, użytkownicy zobaczą tylko jedną nazwę w Portalu firmy.
    - **Opis**: Wprowadź opis aplikacji. Ten opis jest wyświetlany użytkownikom Portalu firmy.
    - **Wydawca**: Wprowadź nazwę wydawcy aplikacji.
    - **Adres URL sklepu App Store**: wprowadź adres URL sklepu z aplikacjami dla aplikacji, którą chcesz utworzyć.
    - **Minimalna wersja systemu operacyjnego**: wybierz z listy najwcześniejszą wersję systemu operacyjnego, w której można zainstalować aplikację. W przypadku przypisania aplikacji do urządzenia z wcześniejszą wersją systemu operacyjnego instalacja nie będzie możliwa.
    - **Kategoria**: opcjonalnie wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. Ułatwi to użytkownikom znajdowanie aplikacji podczas przeglądania Portalu firmy.
    - **Wyświetl jako polecaną aplikację w Portalu firmy**: wybierz tę opcję, aby wyświetlić pakiet aplikacji w dobrze widocznym miejscu na stronie głównej portalu firmy podczas przeglądania aplikacji przez użytkowników. Dotyczy do aplikacji wdrożonych z intencją dostępną.
    - **Adres URL informacji**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Adres URL zasad ochrony prywatności**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje dotyczące zasad ochrony prywatności w tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Deweloper**: opcjonalnie wprowadź nazwę dewelopera aplikacji.
    - **Właściciel**: opcjonalnie wprowadź nazwę właściciela aplikacji, na przykład *Dział kadr*.
    - **Uwagi**: opcjonalnie wprowadź wszelkie uwagi, które chcesz skojarzyć z tą aplikacją.
    - **Logo**: opcjonalnie przekaż ikonę, która zostanie skojarzona z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
5. Wybierz przycisk **OK**.
6. Wybierz pozycję **Dodaj**.

Utworzona aplikacja będzie wyświetlana na liście aplikacji, z której można ją przypisać do wybranych grup. 

## <a name="next-steps"></a>Następne kroki

- [Przypisywanie aplikacji do grup](apps-deploy.md)
