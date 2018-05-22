---
title: Dodawanie aplikacji ze sklepu z aplikacjami dla systemu iOS do usługi Microsoft Intune
titlesuffix: ''
description: Informacje o dodawaniu aplikacji ze sklepu z aplikacjami dla systemu iOS do usługi Microsoft Intune.
keywords: Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ac96c66dd6f09a7bd7a1b1c8c37f2f0eda24828c
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="add-ios-store-apps-to-microsoft-intune"></a>Dodawanie aplikacji ze sklepu z aplikacjami dla systemu iOS do usługi Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Informacje przedstawione w tym artykule ułatwiają dodawanie aplikacji ze sklepu dla systemu iOS w usłudze Microsoft Intune. Aplikacje ze sklepu dla systemu iOS to aplikacje instalowane przez usługę Intune na urządzeniu użytkownika. Użytkownik jest pracownikiem firmy. Aplikacje ze sklepu dla systemu iOS są aktualizowane automatycznie.

>[!NOTE]
>Chociaż użytkownicy urządzeń z systemem iOS mogą usunąć niektóre wbudowane aplikacje dla systemu iOS, takie jak Stocks i Maps, jednak nie mogą użyć usługi Intune do ponownego wdrożenia tych aplikacji. Jeśli użytkownicy usunęli te aplikacje, muszą przejść do sklepu App Store i ponownie zainstalować je ręcznie.

## <a name="before-you-start"></a>Przed rozpoczęciem

Przy użyciu tej metody można przypisywać tylko aplikacje dostępne bezpłatnie w sklepie App Store. Jeśli chcesz przy użyciu usługi Intune przypisać aplikacje płatne, rozważ skorzystanie z [programu zakupów zbiorczych dla systemu iOS](vpp-apps-ios.md).

>[!NOTE]
>Jeśli pracujesz, korzystając z usługi Microsoft Intune, firma Microsoft zaleca używanie przeglądarki Microsoft Edge lub Google Chrome.

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**.  
    Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Aplikacje mobilne**.
4. W okienku obciążenia **Aplikacje mobilne** w obszarze **Zarządzaj** wybierz pozycję **Aplikacje**.
5. W okienku **Aplikacje** wybierz pozycję **Dodaj**.
6. Na liście **Typ aplikacji** w obszarze typów **aplikacji ze sklepu** wybierz opcję **iOS**.
7. Wybierz opcję **Wyszukaj w sklepie App Store**.
8. W okienku **Wyszukaj w sklepie App Store** wybierz ustawienia regionalne dla kraju sklepu App Store.
9. W polu **Wyszukaj** wpisz nazwę aplikacji (lub jej część).  
    Usługa Intune wyszuka nazwę w sklepie i zwróci listę wyników spełniających kryterium.
10. Na liście wyników zaznacz odpowiednią aplikację, a następnie użyj opcji **Wybierz**.
11. Aby skonfigurować aplikację, w okienku **Dodaj aplikację** wybierz pozycję **Informacje o aplikacji**.
12. W okienku **Informacje o aplikacji** dodaj informacje dotyczące aplikacji. W zależności od wybranej aplikacji niektóre wartości w tym okienku mogą zostać wypełnione automatycznie:
    - **Nazwa**: wprowadź nazwę aplikacji, która ma być wyświetlana w Portalu firmy. Upewnij się, że każda używana nazwa aplikacji jest unikatowa. Jeśli nazwa aplikacji będzie zduplikowana, użytkownicy zobaczą tylko jedną nazwę w Portalu firmy.
    - **Opis**: wprowadź opis aplikacji. Ten opis jest wyświetlany użytkownikom Portalu firmy.
    - **Wydawca**: wprowadź nazwę wydawcy aplikacji.
    - **Adres URL sklepu z aplikacjami**: wpisz adres URL sklepu z aplikacjami dla aplikacji, którą chcesz utworzyć.
    - **Minimalna wersja systemu operacyjnego**: wybierz z listy najwcześniejszą wersję systemu operacyjnego, w której można zainstalować aplikację. W przypadku przypisania aplikacji do urządzenia z wcześniejszą wersją systemu operacyjnego instalacja nie będzie możliwa.
    - **Odpowiedni typ urządzenia**: wybierz z listy urządzenia, z których korzysta aplikacja.
    - **Kategoria**: opcjonalnie wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. Ułatwi to użytkownikom znajdowanie aplikacji podczas przeglądania Portalu firmy.
    - **Wyświetl jako polecaną aplikację w Portalu firmy**: wybierz tę opcję, aby wyświetlić pakiet aplikacji na stronie głównej portalu firmy podczas przeglądania aplikacji przez użytkowników.
    - **Adres URL informacji**: opcjonalnie wprowadź adres URL witryny internetowej zawierającej informacje o tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Adres URL zasad ochrony prywatności**: opcjonalnie wprowadź adres URL witryny internetowej zawierającej informacje o zasadach ochrony prywatności w tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Deweloper**: opcjonalnie wprowadź nazwę dewelopera aplikacji. To pole jest widoczne tylko dla administratorów i nie jest widoczne dla użytkowników.
    - **Właściciel**: opcjonalnie wprowadź nazwę właściciela aplikacji, na przykład *Dział kadr*. To pole jest widoczne tylko dla administratorów i nie jest widoczne dla użytkowników.
    - **Uwagi**: opcjonalnie wprowadź wszelkie uwagi, które chcesz skojarzyć z tą aplikacją. To pole jest widoczne tylko dla administratora i nie będzie wyświetlane użytkownikom końcowym.
    - **Logo**: opcjonalnie przekaż ikonę, która zostanie skojarzona z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
13. Wybierz przycisk **OK**.
14. Wybierz pozycję **Dodaj**.

Utworzona aplikacja będzie wyświetlana na liście aplikacji, z której można ją przypisać do wybranych grup.

## <a name="next-steps"></a>Następne kroki

- [Przypisywanie aplikacji do grup](apps-deploy.md)
