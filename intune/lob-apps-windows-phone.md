---
title: Dodawanie aplikacji biznesowych dla systemu Windows Phone do usługi Microsoft Intune
titlesuffix: ''
description: Dowiedz się, jak dodawać aplikacje biznesowe (LOB) dla systemu Windows Phone przy użyciu usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a097b7b2-d01d-454b-954c-da4f3cd0ae86
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 9fa39f212c9979a9986bba5537f0c9a2b5e01c8c
ms.sourcegitcommit: 4e69a8664c289263490daa4c02bc6b81c33196e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/20/2018
ms.locfileid: "53642646"
---
# <a name="add-a-windows-phone-line-of-business-app-to-microsoft-intune"></a>Dodawanie aplikacji biznesowych dla systemu Windows Phone do usługi Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Informacje przedstawione w tym artykule są przydatne podczas dodawania aplikacji biznesowych (LOB) dla systemu Windows Phone do usługi Microsoft Intune. Aplikacja LOB to aplikacja dodawana do usługi Intune za pomocą pliku instalacyjnego aplikacji. Aplikacja tego typu jest zwykle pisana w firmie. Usługa Intune instaluje aplikację LOB na urządzeniu użytkownika. 

## <a name="step-1-specify-the-software-setup-file"></a>Krok 1. Określanie pliku konfiguracji oprogramowania

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Aplikacje klienckie**.
4. W obciążeniu **Aplikacje klienckie** wybierz kolejno pozycje **Zarządzanie** > **Aplikacje**.
5. Wybierz pozycję **Dodaj** powyżej listy aplikacji.
6. W okienku **Dodaj aplikację** wybierz opcję **Aplikacja biznesowa**.

## <a name="step-2-configure-the-app-package-file"></a>Krok 2: Konfigurowanie pliku pakietu aplikacji

1. W okienku **Dodaj aplikację** wybierz pozycję **Plik pakietu aplikacji**.
2. W okienku **Plik pakietu aplikacji** wybierz przycisk przeglądania. Następnie wybierz plik instalacyjny systemu Windows Phone z rozszerzeniem **.xap**.
3. Po zakończeniu wybierz przycisk **OK**.


## <a name="step-3-configure-app-information"></a>Krok 3: Konfigurowanie informacji o aplikacji

1. W okienku **Dodaj aplikację** wybierz pozycję **Informacje o aplikacji**.
2. W okienku **Informacje o aplikacji** skonfiguruj informacje dotyczące aplikacji. W zależności od wybranej aplikacji niektóre wartości w tym okienku mogą zostać wypełnione automatycznie.
    - **Nazwa**: Wprowadź nazwę aplikacji wyświetlaną w portalu firmy. Upewnij się, że wszystkie używane nazwy aplikacji są unikatowe. Jeśli dana nazwa aplikacji występuje dwa razy, w portalu firmy będzie widoczna tylko jedna aplikacja o tej nazwie.
    - **Opis**: Wprowadź opis aplikacji. Opis będzie widoczny w portalu firmy.
    - **Wydawca**: Wprowadź nazwę wydawcy aplikacji.
    - **Kategoria**: Wybierz co najmniej jedną kategorię aplikacji — wbudowaną lub utworzoną samodzielnie. Kategorie ułatwiają użytkownikom znajdowanie aplikacji podczas przeglądania portalu firmy.
    - **Wyświetl jako polecaną aplikację w portalu firmy**: Wyróżnij aplikację na stronie głównej Portalu firmy dla użytkowników przeglądających aplikacje.
    - **Adres URL informacji**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o tej aplikacji. Adres URL będzie widoczny w portalu firmy.
    - **Adres URL zasad ochrony prywatności**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje dotyczące zasad ochrony prywatności w tej aplikacji. Adres URL będzie widoczny w portalu firmy.
    - **Deweloper**: Opcjonalnie wprowadź nazwę dewelopera aplikacji.
    - **Właściciel**: Opcjonalnie wprowadź nazwę właściciela aplikacji. Przykładem może być **Dział kadr**.
    - **Uwagi**: Wprowadź wszelkie uwagi, które chcesz skojarzyć z tą aplikacją.
    - **Logo**: Przekaż ikonę, która jest skojarzona z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
3. Po zakończeniu wybierz przycisk **OK**.

## <a name="step-4-finish-up"></a>Krok 4. Zakończenie

1. W okienku **Dodaj aplikację** sprawdź poprawność skonfigurowanych informacji.
2. Wybierz pozycję **Dodaj**, aby przekazać aplikację do usługi Intune.

## <a name="next-steps"></a>Następne kroki

- Utworzona przez Ciebie aplikacja jest wyświetlana na liście aplikacji. Teraz możesz ją przypisać do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).

- Dowiedz się więcej o sposobach, w jakie możesz monitorować właściwości i przypisania Twojej aplikacji. Zobacz [Monitorowanie informacji o aplikacji i przypisań](apps-monitor.md).

- Dowiedz się więcej o kontekście swojej aplikacji w usłudze Intune. Zobacz temat [Przegląd cyklów życia urządzeń i aplikacji](introduction-device-app-lifecycles.md).
