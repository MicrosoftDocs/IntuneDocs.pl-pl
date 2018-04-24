---
title: Jak dodawać aplikacje ze sklepu z aplikacjami dla systemu Android do usługi Microsoft Intune
titleSuffix: ''
description: Informacje o dodawaniu aplikacji ze sklepu z aplikacjami dla systemu Android do usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4433000a-23e9-4cad-a818-48c28eedc1f5
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ece6edee891b147ad2124b987239da6af8e1bc8d
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-android-store-apps-to-microsoft-intune"></a>Jak dodawać aplikacje ze sklepu z aplikacjami dla systemu Android do usługi Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Przed przypisaniem aplikacji do urządzenia lub grupy użytkowników należy najpierw dodać aplikację do usługi Microsoft Intune. Poniższe kroki umożliwiają dodanie aplikacji ze sklepu dla systemu Android do usługi Intune w portalu Azure.

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Aplikacje mobilne**.
4. W obciążeniu **Aplikacje mobilne** wybierz pozycję **Aplikacje** w sekcji **Zarządzaj**.
5. Wybierz pozycję **Dodaj** powyżej listy aplikacji.
6. W okienku **Dodaj aplikację** wybierz pozycję **Android** w obszarze dostępnych typów **aplikacji ze sklepu**.
7. Wybierz pozycję **Konfiguruj**, aby skonfigurować następujące informacje o aplikacji: w zależności od wybranej aplikacji niektóre wartości w tym okienku mogą zostać wypełnione automatycznie:
    - **Nazwa** — wprowadź nazwę aplikacji wyświetlaną w portalu firmy. Upewnij się, że wszystkie używane nazwy aplikacji są unikatowe. Jeśli dana nazwa aplikacji występuje dwa razy, użytkownicy Portalu firmy będą widzieć tylko jedną z aplikacji o tej nazwie.
    - **Opis** — wprowadź opis aplikacji. Ten opis będzie widoczny dla użytkowników w Portalu firmy.
    - **Wydawca** — wprowadź nazwę wydawcy aplikacji.
    - **Adres URL sklepu z aplikacjami** — wprowadź adres URL sklepu z aplikacjami dla aplikacji, którą chcesz utworzyć.
    - **Minimalna wersja systemu operacyjnego** — wybierz z listy minimalną wersję systemu operacyjnego, na którym można zainstalować aplikację. W przypadku przypisania aplikacji do urządzenia z wcześniejszą wersją systemu operacyjnego instalacja nie będzie możliwa.
    - **Kategoria** (opcjonalnie) — wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. Ułatwi to użytkownikom znajdowanie aplikacji podczas przeglądania Portalu firmy.
    - **Wyświetl jako polecaną aplikację w portalu firmy** — wyróżnij aplikację na stronie głównej portalu firmy dla użytkowników przeglądających aplikacje.
    - **Adres URL informacji** (opcjonalnie) — wprowadź adres URL witryny sieci Web zawierającej informacje o aplikacji. Adres będzie widoczny dla użytkowników w Portalu firmy.
    - **Adres URL zasad ochrony prywatności** — opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o ochronie prywatności dotyczące tej aplikacji. Adres będzie widoczny dla użytkowników w Portalu firmy.
    - **Deweloper** (opcjonalnie) — wprowadź nazwę dewelopera aplikacji.
    - **Właściciel** (opcjonalnie) — wprowadź nazwę właściciela aplikacji, na przykład **Dział kadr**.
    - **Uwagi** (opcjonalnie) — wprowadź wszelkie uwagi, które chcesz skojarzyć z aplikacją.
    - **Ikona** (opcjonalnie) — przekaż ikonę, która zostanie skojarzona z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
8. Kliknij przycisk **OK** po zakończeniu ustawiania informacji o aplikacji.
9. Kliknij przycisk **Dodaj**, aby dodać aplikację.

Utworzona aplikacja będzie wyświetlana na liście aplikacji, z której można ją przypisać do wybranych grup. 

## <a name="next-steps"></a>Następne kroki

- [Jak przypisać aplikacje do grup](apps-deploy.md)