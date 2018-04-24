---
title: Dodawanie aplikacji biznesowych dla systemu Windows do usługi Microsoft Intune
titlesuffix: ''
description: Dowiedz się, jak dodawać aplikacje biznesowe (LOB) dla systemu Windows do usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: aa11c29a50006053b6e9b52516a595683d6f4cfd
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-windows-line-of-business-lob-apps-to-microsoft-intune"></a>Jak dodawać aplikacje biznesowe (LOB) dla systemu Windows do usługi Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Aplikacja biznesowa (LOB) to aplikacja dodawana za pomocą pliku instalacyjnego aplikacji. Aplikacje tego typu są zwykle pisane w firmie. W poniższych krokach przedstawiono wskazówki ułatwiające dodawanie aplikacji biznesowych dla systemu Windows do usługi Microsoft Intune.

## <a name="step-1---specify-the-software-setup-file"></a>Krok 1. Określanie lokalizacji pliku konfiguracji oprogramowania

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Aplikacje mobilne**.
4. W obciążeniu **Aplikacje mobilne** wybierz kolejno pozycje **Zarządzaj** > **Aplikacje**.
5. Wybierz pozycję **Dodaj** powyżej listy aplikacji.
6. W okienku **Dodaj aplikację** wybierz pozycję **Aplikacja biznesowa**.

## <a name="step-2---configure-the-app-package-file"></a>Krok 2. Konfigurowanie pliku pakietu aplikacji

1. W okienku **Dodaj aplikację** wybierz plik **Pakiet aplikacji**.
2. W okienku pliku **Pakiet aplikacji** kliknij przycisk przeglądania i wybierz plik instalacyjny systemu Windows Phone z rozszerzeniem **.msi**, **.appx** lub **.appxbundle**.
3. Gdy skończysz, wybierz przycisk **OK**.


## <a name="step-3---configure-app-information"></a>Krok 3. Konfigurowanie informacji o aplikacji

1. W okienku **Dodaj aplikację** wybierz plik **Pakiet aplikacji**.
2. W okienku **Informacje o aplikacji** skonfiguruj poniższe informacje (niektóre wartości w okienku mogą zostać wypełnione automatycznie):
    - **Nazwa** — wprowadź nazwę aplikacji wyświetlaną w portalu firmy. Upewnij się, że wszystkie używane nazwy aplikacji są unikatowe. Jeśli dana nazwa aplikacji występuje dwa razy, użytkownicy Portalu firmy będą widzieć tylko jedną z aplikacji o tej nazwie.
    - **Opis** — wprowadź opis aplikacji. Opis jest wyświetlany użytkownikom Portalu firmy.
    - **Wydawca** — wprowadź nazwę wydawcy aplikacji.
    - **Ignoruj wersję aplikacji** — ustaw opcję na **Tak**, jeśli aplikacja jest automatycznie aktualizowania przez dewelopera aplikacji.
    - **Kategoria** — wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. Kategoryzacja aplikacji ułatwi użytkownikom znajdowanie aplikacji podczas przeglądania Portalu firmy.
    - **Wyświetl jako polecaną aplikację w portalu firmy** — wyróżnij aplikację na stronie głównej portalu firmy dla użytkowników przeglądających aplikacje.
    - **Adres URL informacji** — opcjonalnie wprowadź adres URL witryny internetowej zawierającej informacje o aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Adres URL zasad ochrony prywatności** — opcjonalnie wprowadź adres URL witryny internetowej zawierającej informacje o zasadach ochrony prywatności mających zastosowanie do aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Argumenty wiersza polecenia** — opcjonalnie wprowadź argumenty wiersza polecenia, które mają zostać zastosowane do pliku .msi po jego uruchomieniu, np. **/q**.
    - **Deweloper** — opcjonalnie wprowadź nazwę dewelopera aplikacji.
    - **Właściciel** — opcjonalnie wprowadź nazwę właściciela aplikacji, na przykład **Dział kadr**.
    - **Uwagi** — wprowadź wszelkie uwagi, które chcesz skojarzyć z aplikacją.
    - **Logo** — przekaż ikonę, która zostanie skojarzona z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
3. Gdy skończysz, wybierz przycisk **OK**.

## <a name="step-4---finish-up"></a>Krok 4. Zakończenie

1. W okienku **Dodaj aplikację** sprawdź poprawność skonfigurowanych informacji dotyczących aplikacji.
2. Wybierz pozycję **Dodaj**, aby przekazać aplikację do usługi Intune.

## <a name="step-5---update-a-line-of-business-app"></a>Krok 5. Aktualizacja aplikacji biznesowej

[!INCLUDE [shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

## <a name="configuring-a-self-updating-mobile-msi-app-to-ignore-the-version-check-process"></a>Konfigurowanie mobilnej aplikacji MSI korzystającej z samoaktualizacji w celu ignorowania procesu sprawdzania wersji

Znaną mobilną aplikację MSI, która korzysta z samoaktualizacji, można skonfigurować tak, aby ignorowała proces sprawdzania wersji. Niektóre aplikacje oparte na instalatorze MSI są automatycznie aktualizowane przez dewelopera aplikacji. W przypadku tych automatycznie aktualizowanych aplikacji MSI możesz skonfigurować ustawienie **Ignoruj wersję aplikacji** w bloku **Informacje o aplikacji**. Gdy to ustawienie zostanie przełączone na wartość **Tak**, usługa Microsoft Intune nie będzie wymuszać wersji aplikacji zainstalowanej na kliencie systemu Windows. Ta możliwość jest przydatna, aby uniknąć sytuacji wyścigu. Sytuacja wyścigu może wystąpić na przykład wtedy, gdy aplikacja jest automatycznie aktualizowana przez dewelopera, a równocześnie jest aktualizowana przez usługę Intune. Obie aktualizacje mogą próbować wymusić na kliencie systemu Windows daną wersję aplikacji, co może powodować konflikt.

## <a name="next-steps"></a>Następne kroki

- Utworzona aplikacja jest wyświetlana na liście aplikacji. Teraz można przypisać ją do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).

- Dowiedz się więcej o sposobach, w jakie możesz monitorować właściwości i przypisania Twojej aplikacji. Aby uzyskać więcej informacji, zobacz [Monitorowanie informacji o aplikacji i przypisań](apps-monitor.md).

- Dowiedz się więcej o kontekście swojej aplikacji w usłudze Intune. Aby uzyskać więcej informacji, zobacz [Przegląd cyklów życia urządzeń i aplikacji](introduction-device-app-lifecycles.md)
