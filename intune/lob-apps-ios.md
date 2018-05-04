---
title: Dodawanie do usługi Microsoft Intune aplikacji biznesowych dla systemu iOS
titlesuffix: ''
description: Dowiedz się, jak dodawać aplikacje biznesowe dla systemu iOS do usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 099101e8-4b22-40ac-ba19-82ba5c71944c
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fcbdf0a61b7b001dc7d3b1d620df7a88bb44e2ca
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
---
# <a name="add-an-ios-line-of-business-app-to-microsoft-intune"></a>Dodawanie do usługi Microsoft Intune aplikacji biznesowych dla systemu iOS

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Informacje przedstawione w tym artykule ułatwiają dodawanie aplikacji biznesowych (LOB, line-of-business) dla systemu iOS do usługi Microsoft Intune.

>[!NOTE]
>Użytkownicy urządzeń z systemem iOS mogą usuwać niektóre wbudowane aplikacje dla systemu iOS, takie jak Stocks i Maps. Nie można użyć usługi Intune do ponownego wdrożenia tych aplikacji. Jeśli użytkownicy usunęli te aplikacje, muszą przejść do sklepu z aplikacjami i ponownie ręcznie je zainstalować.

## <a name="step-1-specify-the-software-setup-file"></a>Krok 1. Określanie lokalizacji pliku konfiguracji oprogramowania

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Aplikacje mobilne**.
4. W obciążeniu **Aplikacje mobilne** wybierz kolejno pozycje **Zarządzaj** > **Aplikacje**.
5. Wybierz pozycję **Dodaj** powyżej listy aplikacji.
6. W okienku **Dodaj aplikację** wybierz opcję **Aplikacja biznesowa**.

## <a name="step-2-configure-the-app-package-file"></a>Krok 2. Konfigurowanie pliku pakietu aplikacji

1. W okienku **Dodaj aplikację** wybierz opcję **Plik pakietu aplikacji**.
2. W okienku **Plik pakietu aplikacji** wybierz przycisk przeglądania. Następnie wybierz plik instalacyjny systemu iOS z rozszerzeniem **.ipa**.
3. Po zakończeniu wybierz opcję **OK**.


## <a name="step-3-configure-app-information"></a>Krok 3: Konfigurowanie informacji o aplikacji

1. W okienku **Dodaj aplikację** wybierz opcję **Informacje o aplikacji**.
2. W okienku **Informacje o aplikacji** dodaj szczegóły swojej aplikacji. W zależności od wybranej aplikacji niektóre wartości w tym okienku mogą zostać wypełnione automatycznie.
    - **Nazwa**: wprowadź nazwę aplikacji wyświetlaną w portalu firmy. Upewnij się, że wszystkie używane nazwy aplikacji są unikatowe. Jeśli dana nazwa aplikacji występuje dwa razy, w portalu firmy będzie widoczna tylko jedna aplikacja o tej nazwie.
    - **Opis**: wprowadź opis aplikacji. Opis jest widoczny w portalu firmy.
    - **Wydawca**: wprowadź nazwę wydawcy aplikacji.
    - **Minimalna wersja systemu operacyjnego**: wybierz z listy minimalną wersję systemu operacyjnego, w którym można zainstalować aplikację. W przypadku przypisania aplikacji do urządzenia z wcześniejszą wersją systemu operacyjnego instalacja nie będzie możliwa.
    - **Ignoruj wersję aplikacji**: nadaj tej opcji wartość **Tak**, jeśli deweloper aplikacji automatycznie aktualizuje aplikację.
    - **Kategoria**: wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. Kategorie ułatwiają użytkownikom znajdowanie aplikacji podczas przeglądania portalu firmy.
    - **Wyświetl jako polecaną aplikację w portalu firmy**: wyróżnij aplikację na stronie głównej portalu firmy dla użytkowników przeglądających aplikacje.
    - **Adres URL informacji**: opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o aplikacji. Adres URL będzie widoczny w portalu firmy.
    - **Adres URL zasad ochrony prywatności**: opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o zasadach ochrony prywatności mających zastosowanie do tej aplikacji. Adres URL będzie widoczny w portalu firmy.
    - **Deweloper**: opcjonalnie wprowadź nazwę dewelopera aplikacji.
    - **Właściciel**: opcjonalnie wprowadź nazwę właściciela aplikacji. Przykładem może być **Dział kadr**.
    - **Uwagi**: wprowadź wszelkie uwagi, które chcesz skojarzyć z tą aplikacją.
    - **Logo**: przekaż ikonę, która zostanie skojarzona z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania witryny Portal firmy.
3. Po zakończeniu wybierz opcję **OK**.

## <a name="step-4-finish-up"></a>Krok 4. Zakończenie

1. W okienku **Dodaj aplikację** sprawdź poprawność szczegółów aplikacji.
2. Wybierz opcję **Dodaj**, aby przekazać aplikację do usługi Intune.

Utworzona przez Ciebie aplikacja jest widoczna na liście aplikacji. Korzystając z listy, możesz przypisywać aplikacje do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).

## <a name="step-5-update-a-line-of-business-app"></a>Krok 5. Aktualizacja aplikacji biznesowej

[!INCLUDE [shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

> [!NOTE]
> Aby usługa Intune mogła wdrożyć nowy plik IPA na urządzeniu, należy zwiększyć numer w ciągu znaków `CFBundleVersion` w pliku Info.plist w pakiecie IPA.

## <a name="next-steps"></a>Następne kroki

- Utworzona przez Ciebie aplikacja zostanie wyświetlona na liście aplikacji. Teraz możesz przypisać ją do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).

- Dowiedz się więcej o sposobach, w jakie możesz monitorować właściwości i przypisania Twojej aplikacji. Zobacz temat [Monitorowanie informacji o aplikacji i przypisań](apps-monitor.md).

- Dowiedz się więcej o kontekście swojej aplikacji w usłudze Intune. Zobacz temat [Przegląd cykli życia urządzeń i aplikacji](introduction-device-app-lifecycles.md).
