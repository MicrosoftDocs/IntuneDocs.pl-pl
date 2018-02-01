---
title: "Jak dodawać aplikacje ze sklepu z aplikacjami dla systemu iOS do usługi Intune | Microsoft Docs"
titlesuffix: Azure portal
description: "Informacje o dodawaniu aplikacji ze sklepu z aplikacjami dla systemu iOS do usługi Intune."
keywords: Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e013b5c995274365978ee0c2ba2f45bfeef54baa
ms.sourcegitcommit: b982f9d50da4f958fb0c48c56ba46c8ef71500c4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2018
---
# <a name="how-to-add-ios-store-apps-to-microsoft-intune"></a>Jak dodawać aplikacje ze sklepu z aplikacjami dla systemu iOS do usługi Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Informacje przedstawione w tym temacie ułatwiają dodawanie aplikacji ze sklepu dla systemu w usłudze Intune.

>[!NOTE]
>Użytkownicy urządzeń z systemem iOS mogą usuwać niektóre wbudowane aplikacje dla systemu iOS, takie jak Stocks i Maps, ale nie można użyć usługi Intune do ponownego wdrożenia tych aplikacji. Jeśli użytkownicy końcowi usuwają te aplikacje, muszą przejść do sklepu z aplikacjami i ręcznie zainstalować je ponownie.

## <a name="before-you-start"></a>Przed rozpoczęciem

Przy użyciu tej metody można przypisywać tylko aplikacje dostępne bezpłatnie w sklepie z aplikacjami. Jeśli chcesz przy użyciu usługi Intune przypisać aplikacje płatne, rozważ skorzystanie z [programu zakupów zbiorczych dla systemu iOS](vpp-apps-ios.md).

>[!NOTE]
>Do pracy z usługą Microsoft Intune zalecane są przeglądarki Chrome i Edge.

## <a name="step-1---search-for-the-app-in-the-store"></a>Krok 1 — Wyszukiwanie aplikacji w sklepie

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Zarządzaj aplikacjami**.
4. W obciążeniu **Aplikacje mobilne** wybierz kolejno pozycje **Zarządzaj** > Aplikacje.
5. Wybierz pozycję **Dodaj** powyżej listy aplikacji.
6. W bloku **Dodaj aplikację** wybierz pozycję **Wyszukaj w sklepie App Store**.
7. W bloku **Sklep Apple App Store** wybierz ustawienia regionalne dla kraju sklepu App Store.
8. Wpisz nazwę (lub jej część) w polu wyszukiwania. Usługa Intune wyszuka nazwę w sklepie i powróci do listy wyników spełniających kryterium.
9. Wybierz aplikację z listy, a następnie kliknij przycisk **OK**.

## <a name="step-2---configure-app-information"></a>Krok 2 — Konfigurowanie informacji o aplikacji

1. W bloku **Dodaj aplikację** wybierz pozycję **Informacje o aplikacji**.
2. W bloku **Edytuj aplikację** skonfiguruj informacje o aplikacji. Gdy wszystko będzie gotowe, kliknij pozycję **Dodaj**. W zależności od wybranej aplikacji niektóre wartości w tym bloku mogą zostać wypełnione automatycznie:
- **Nazwa** — wpisz nazwę aplikacji do wyświetlenia w portalu firmy. Upewnij się, że wszystkie używane nazwy aplikacji są unikatowe. Jeśli dana nazwa aplikacji występuje dwa razy, portal firmy wyświetla użytkownikom tylko jedną z aplikacji o tej nazwie.
- **Opis** — wpisz opis aplikacji, który ma być wyświetlany użytkownikom w portalu firmy.
- **Wydawca** — wpisz nazwę wydawcy aplikacji.
- **Adres URL sklepu z aplikacjami** — wpisz adres URL sklepu z aplikacjami dla aplikacji, którą chcesz utworzyć.
- **Kraj/region sklepu** — wybierz ustawienia regionalne dla kraju sklepu App Store.
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
3. Gdy wszystko będzie gotowe, w bloku **Dodawanie aplikacji** wybierz przycisk **OK**.

Utworzona aplikacja będzie wyświetlana na liście aplikacji, skąd można ją przypisać do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).
