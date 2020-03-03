---
title: Dodawanie aplikacji ze sklepu z aplikacjami dla systemu iOS do usługi Microsoft Intune
titleSuffix: ''
description: Informacje o dodawaniu aplikacji ze sklepu z aplikacjami dla systemu iOS do usługi Microsoft Intune. Przy użyciu tej metody można przypisywać aplikacje, które są dostępne bezpłatnie w sklepie App Store.
keywords: Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/22/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f2baf60fed2c6010e5ae0784cda166ac4fabfd57
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77511739"
---
# <a name="add-ios-store-apps-to-microsoft-intune"></a>Dodawanie aplikacji ze sklepu z aplikacjami dla systemu iOS do usługi Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Informacje przedstawione w tym artykule ułatwiają dodawanie aplikacji ze sklepu dla systemu iOS w usłudze Microsoft Intune. Aplikacje ze sklepu dla systemu iOS to aplikacje instalowane przez usługę Intune na urządzeniu użytkownika. Użytkownik jest pracownikiem firmy. Aplikacje ze sklepu dla systemu iOS są aktualizowane automatycznie.

>[!NOTE]
>Chociaż użytkownicy urządzeń z systemem iOS/iPadOS mogą usunąć niektóre wbudowane aplikacje dla systemu iOS/iPadOS, takie jak Stocks i Maps, jednak nie mogą użyć usługi Intune do ponownego wdrożenia tych aplikacji. Jeśli użytkownicy usunęli te aplikacje, muszą przejść do sklepu App Store i ponownie zainstalować je ręcznie.

## <a name="before-you-start"></a>Przed rozpoczęciem

Przy użyciu tej metody można przypisywać tylko aplikacje dostępne bezpłatnie w sklepie App Store. Jeśli chcesz przy użyciu usługi Intune przypisać aplikacje płatne, rozważ skorzystanie z [programu zakupów zbiorczych dla systemu iOS/iPadOS](vpp-apps-ios.md).

>[!NOTE]
>Jeśli pracujesz, korzystając z usługi Microsoft Intune, firma Microsoft zaleca używanie przeglądarki Microsoft Edge lub Google Chrome.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**.
3. W okienku **Wybierz typ aplikacji** w obszarze dostępnych typów **Aplikacja ze sklepu** wybierz pozycję **Aplikacja ze sklepu dla systemu iOS**.
4. Kliknij pozycję **Wybierz**.<br>
   Zostaną wyświetlone kroki **dodawania aplikacji**.
5. Wybierz opcję **Wyszukaj w sklepie App Store**.
6. W okienku **Wyszukaj w sklepie App Store** wybierz ustawienia regionalne dla kraju/regionu sklepu App Store.
7. W polu **Wyszukaj** wpisz nazwę aplikacji (lub jej część).  
    Usługa Intune wyszuka nazwę w sklepie i zwróci listę wyników spełniających kryterium.
8. Na liście wyników zaznacz odpowiednią aplikację, a następnie użyj opcji **Wybierz**.<br>

   Strona **informacji o aplikacji** zostanie wyświetlona w okienku **Dodawanie aplikacji**. Gdy będzie to możliwe, informacje o aplikacji zostaną dodane na podstawie wybranej aplikacji ze sklepu.

9. Na stronie **Informacje o aplikacji** dodaj szczegóły aplikacji. W zależności od wybranej aplikacji niektóre wartości w tym okienku mogą zostać wypełnione automatycznie:
    - **Nazwa**: wprowadź nazwę aplikacji, która ma być wyświetlana w Portalu firmy. Upewnij się, że każda używana nazwa aplikacji jest unikatowa. Jeśli nazwa aplikacji będzie zduplikowana, użytkownicy zobaczą tylko jedną nazwę w Portalu firmy.
    - **Opis**: Wprowadź opis aplikacji. Ten opis jest wyświetlany użytkownikom Portalu firmy.
    - **Wydawca**: Wprowadź nazwę wydawcy aplikacji.
    - **Adres URL sklepu App Store**: Wpisz adres URL sklepu App Store dla aplikacji, którą chcesz utworzyć.
    - **Minimalna wersja systemu operacyjnego**: wybierz z listy najwcześniejszą wersję systemu operacyjnego, w której można zainstalować aplikację. W przypadku przypisania aplikacji do urządzenia z wcześniejszą wersją systemu operacyjnego instalacja nie będzie możliwa.
    - **Odpowiedni typ urządzenia**: Wybierz z listy urządzenia, z których korzysta aplikacja.
    - **Kategoria**: opcjonalnie wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. Ułatwi to użytkownikom znajdowanie aplikacji podczas przeglądania Portalu firmy.
    - **Pokaż jako polecaną aplikację w Portalu firmy**: wybierz tę opcję, aby wyświetlić pakiet aplikacji w dobrze widocznym miejscu na stronie głównej portalu firmy podczas przeglądania aplikacji przez użytkowników.
    - **Adres URL informacji**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Adres URL zasad ochrony prywatności**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje dotyczące zasad ochrony prywatności w tej aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Deweloper**: Opcjonalnie wprowadź nazwę dewelopera aplikacji. To pole jest widoczne tylko dla administratorów i nie jest widoczne dla użytkowników.
    - **Właściciel**: Opcjonalnie wprowadź nazwę właściciela aplikacji, na przykład *Dział kadr*. To pole jest widoczne tylko dla administratorów i nie jest widoczne dla użytkowników.
    - **Uwagi**: Opcjonalnie wprowadź wszelkie uwagi, które chcesz skojarzyć z tą aplikacją. To pole jest widoczne tylko dla administratora i nie będzie wyświetlane użytkownikom końcowym.
    - **Logo**: opcjonalnie przekaż ikonę, która zostanie skojarzona z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
10. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Tagi zakresu**.
11. Kliknij pozycję **Wybierz tagi zakresu**, aby opcjonalnie dodać tagi zakresu dla aplikacji. Aby uzyskać więcej informacji, zobacz temat [Używanie kontroli dostępu opartej na rolach i tagów zakresu w rozproszonej infrastrukturze informatycznej](~/fundamentals/scope-tags.md).
12. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Przypisania**.
13. Wybierz przypisania grupy dla aplikacji. Aby uzyskać więcej informacji, zobacz temat [Dodawanie grup w celu organizowania użytkowników i urządzeń](~/fundamentals/groups-add.md). 
14. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Recenzja i tworzenie**. Przejrzyj wartości i ustawienia wprowadzone dla aplikacji.
15. Gdy skończysz, kliknij pozycję **Utwórz**, aby dodać aplikację do usługi Intune.

Zostanie wyświetlony blok **Omówienie** dotyczący utworzonej aplikacji.

## <a name="next-steps"></a>Następne kroki

- [Przypisywanie aplikacji do grup](apps-deploy.md)
