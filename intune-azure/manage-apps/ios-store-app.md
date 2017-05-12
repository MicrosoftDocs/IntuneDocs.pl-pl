---
title: "Jak dodawać aplikacje ze sklepu z aplikacjami dla systemu iOS do usługi Intune | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje o dodawaniu aplikacji ze sklepu z aplikacjami dla systemu iOS do usługi Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 011f33d1d8569a079f73baaca6ba2a665131691d
ms.contentlocale: pl-pl
ms.lasthandoff: 05/10/2017

---

# <a name="how-to-add-ios-store-apps-to-microsoft-intune"></a>Jak dodawać aplikacje ze sklepu z aplikacjami dla systemu iOS do usługi Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="before-you-start"></a>Przed rozpoczęciem

Przy użyciu tej metody można przypisywać tylko aplikacje dostępne bezpłatnie w sklepie z aplikacjami. Jeśli chcesz przy użyciu usługi Intune przypisać aplikacje płatne, rozważ skorzystanie z [programu zakupów zbiorczych dla systemu iOS](ios-vpp-apps.md).


## <a name="step-1---search-for-the-app-in-the-store"></a>Krok 1 — Wyszukiwanie aplikacji w sklepie

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Zarządzaj aplikacjami**.
4. W obciążeniu **Aplikacje mobilne** wybierz kolejno pozycje **Zarządzaj** > Aplikacje.
5. Wybierz pozycję **Dodaj** powyżej listy aplikacji.
6. W bloku **Dodaj aplikację** wybierz pozycję **Wyszukaj w sklepie App Store**.
7. W bloku **Sklep App Store** wprowadź nazwę (lub jej część) w polu wyszukiwania. Usługa Intune wyszuka nazwę w sklepie i powróci do listy wyników spełniających kryterium.
8. Wybierz aplikację z listy, a następnie kliknij przycisk **OK**.

## <a name="step-2---configure-app-information"></a>Krok 2 — Konfigurowanie informacji o aplikacji

1. W bloku **Dodaj aplikację** wybierz pozycję **Informacje o aplikacji**.
2. W bloku **Edytuj aplikację** skonfiguruj następujące informacje. Gdy wszystko będzie gotowe, kliknij pozycję **Dodaj**. W zależności od wybranej aplikacji niektóre wartości w tym bloku mogą zostać wypełnione automatycznie:
- **Nazwa aplikacji** — wprowadź nazwę aplikacji, która będzie wyświetlana w Portalu firmy. Upewnij się, że wszystkie używane nazwy aplikacji są unikatowe. Jeśli dana nazwa aplikacji występuje dwa razy, użytkownicy Portalu firmy będą widzieć tylko jedną z aplikacji o tej nazwie.
    - **Opis aplikacji** — wprowadź opis aplikacji. Ta informacja będzie widoczna dla użytkowników w Portalu firmy.
- **Wydawca** — wprowadź nazwę wydawcy aplikacji.
- **Adres URL sklepu z aplikacjami** — wprowadź adres URL sklepu z aplikacjami dla aplikacji, którą chcesz utworzyć.
- **Minimalna wersja systemu operacyjnego** — wybierz z listy minimalną wersję systemu operacyjnego, na którym można zainstalować aplikację. W przypadku przypisania aplikacji do urządzenia z wcześniejszą wersją systemu operacyjnego instalacja nie będzie możliwa.
- **Kategoria** (opcjonalnie). Wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. Ułatwi to użytkownikom znajdowanie aplikacji podczas przeglądania Portalu firmy.
- **Wyświetl jako polecaną aplikację w portalu firmy** — wyróżnij aplikację na stronie głównej portalu firmy dla użytkowników przeglądających aplikacje.
- **Adres URL informacji** — opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o aplikacji. Adres będzie widoczny dla użytkowników w Portalu firmy.
- **Adres URL zasad ochrony prywatności** — opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o zasadach ochrony prywatności mających zastosowanie do aplikacji. Adres będzie widoczny dla użytkowników w Portalu firmy.
- **Deweloper** — opcjonalnie wprowadź nazwę dewelopera aplikacji.
- **Właściciel** — opcjonalnie wprowadź nazwę właściciela aplikacji, na przykład **Dział kadr**.
- **Uwagi** — wprowadź wszelkie uwagi, które chcesz skojarzyć z aplikacją.
- **Przekaż ikonę** — przekaż ikonę, która zostanie skojarzona z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
3. Gdy wszystko będzie gotowe, w bloku **Dodaj aplikację** wybierz pozycję **Zapisz**.

Utworzona aplikacja będzie wyświetlana na liście aplikacji, skąd można ją przypisać do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](deploy-apps.md) (Jak przypisać aplikacje do grupy).

