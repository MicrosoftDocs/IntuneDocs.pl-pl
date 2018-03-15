---
title: "Jak dodawać aplikacje ze sklepu z aplikacjami dla systemu iOS do usługi Microsoft Intune"
titlesuffix: 
description: "Informacje o dodawaniu aplikacji ze sklepu z aplikacjami dla systemu iOS do usługi Microsoft Intune."
keywords: Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/21/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b5315d683abfc38a7f42d2f322cc77c625270e3c
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2018
---
# <a name="how-to-add-ios-store-apps-to-microsoft-intune"></a>Jak dodawać aplikacje ze sklepu z aplikacjami dla systemu iOS do usługi Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Informacje przedstawione w tym artykule ułatwiają dodawanie aplikacji ze sklepu dla systemu iOS w usłudze Microsoft Intune. Aplikacje ze sklepu dla systemu iOS to aplikacje instalowane na urządzeniu użytkownika przy użyciu usługi Intune. Użytkownik jest pracownikiem firmy. Aplikacje ze sklepu dla systemu iOS są aktualizowane automatycznie. 

>[!NOTE]
>Użytkownicy urządzeń z systemem iOS mogą usuwać niektóre wbudowane aplikacje dla systemu iOS, takie jak Stocks i Maps, ale nie można użyć usługi Intune do ponownego wdrożenia tych aplikacji. Jeśli użytkownicy końcowi usunęli te aplikacje, muszą przejść do sklepu z aplikacjami i ręcznie zainstalować je ponownie.

## <a name="before-you-start"></a>Przed rozpoczęciem

Przy użyciu tej metody można przypisywać tylko aplikacje dostępne bezpłatnie w sklepie z aplikacjami. Jeśli chcesz przy użyciu usługi Intune przypisać aplikacje płatne, rozważ skorzystanie z [programu zakupów zbiorczych dla systemu iOS](vpp-apps-ios.md).

>[!NOTE]
>Do pracy z usługą Microsoft Intune zalecane są przeglądarki Chrome i Microsoft Edge.

## <a name="step-1---search-for-the-app-in-the-store"></a>Krok 1 — Wyszukiwanie aplikacji w sklepie

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W bloku **Intune** wybierz pozycję **Aplikacje mobilne**.
4. W obciążeniu **Aplikacje mobilne** wybierz pozycję **Aplikacje** w sekcji **Zarządzaj**.
5. Wybierz opcję **Dodaj** po prawej stronie okienka **Aplikacje**.
6. Na liście **Typ aplikacji** wybierz opcję **iOS** w obszarze dostępnych typów **aplikacji ze sklepu**.
6. Wybierz opcję **Wyszukaj w sklepie App Store**.
7. W bloku **Wyszukaj w sklepie App Store** wybierz ustawienia regionalne dla kraju sklepu App Store.
8. Wpisz nazwę (lub jej część) w polu wyszukiwania. Usługa Intune wyszuka nazwę w sklepie i powróci do listy wyników spełniających kryterium.
9. Wybierz aplikację z listy, a następnie kliknij przycisk **Wybierz**.

## <a name="step-2---configure-app-information"></a>Krok 2 — Konfigurowanie informacji o aplikacji

1. W bloku **Dodaj aplikację** wybierz pozycję **Informacje o aplikacji**, aby skonfigurować aplikację.
2. W bloku **Informacje o aplikacji** dodaj informacje dotyczące aplikacji. W zależności od wybranej aplikacji niektóre wartości w tym bloku mogą zostać wypełnione automatycznie:
- **Nazwa** — wpisz nazwę aplikacji do wyświetlenia w portalu firmy. Upewnij się, że wszystkie używane nazwy aplikacji są unikatowe. Jeśli dana nazwa aplikacji występuje dwa razy, portal firmy wyświetla użytkownikom tylko jedną z aplikacji o tej nazwie.
- **Opis** — wpisz opis aplikacji, który ma być wyświetlany użytkownikom w portalu firmy.
- **Wydawca** — wpisz nazwę wydawcy aplikacji.
- **Adres URL sklepu z aplikacjami** — wpisz adres URL sklepu z aplikacjami dla aplikacji, którą chcesz utworzyć.
- **Minimalna wersja systemu operacyjnego** — wybierz z listy minimalną wersję systemu operacyjnego, na którym można zainstalować aplikację. Aplikacja nie zostanie zainstalowana na urządzeniu ze starszą wersją systemu operacyjnego.
- **Odpowiedni typ urządzenia** — wybierz z listy urządzenia, z których korzysta aplikacja.
- **Kategoria** (opcjonalnie). Wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. Kategorie ułatwiają użytkownikom znajdowanie aplikacji podczas przeglądania portalu firmy.
- **Wyświetl jako polecaną aplikację w portalu firmy** — wyróżnij aplikację na stronie głównej portalu firmy dla użytkowników przeglądających aplikacje.
- **Adres URL informacji** — opcjonalnie wpisz adres URL witryny internetowej zawierającej informacje o aplikacji. Adres będzie widoczny dla użytkowników portalu firmy.
- **Adres URL zasad ochrony prywatności** — opcjonalnie wpisz adres URL witryny internetowej zawierającej informacje o zasadach ochrony prywatności mających zastosowanie do aplikacji. Adres będzie widoczny dla użytkowników portalu firmy.
- **Deweloper** — opcjonalnie wpisz nazwę dewelopera aplikacji. To pole jest widoczne tylko dla administratora i nie będzie wyświetlane użytkownikom końcowym.
- **Właściciel** — opcjonalnie wpisz nazwę właściciela aplikacji, na przykład **Dział kadr**.  To pole jest widoczne tylko dla administratora i nie będzie wyświetlane użytkownikom końcowym.
- **Uwagi** — wpisz wszelkie uwagi, które chcesz skojarzyć z aplikacją. To pole jest widoczne tylko dla administratora i nie będzie wyświetlane użytkownikom końcowym.
- **Logo** — przekaż ikonę, która zostanie skojarzona z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
3. Po zakończeniu w bloku **Informacje o aplikacji** kliknij przycisk **OK**.
4. Kliknij przycisk **Dodaj** w bloku **Dodawanie aplikacji**. 

Utworzona aplikacja będzie wyświetlana na liście aplikacji, skąd można ją przypisać do wybranych grup. 

## <a name="next-steps"></a>Następne kroki

- [Jak przypisać aplikacje do grup](apps-deploy.md)
