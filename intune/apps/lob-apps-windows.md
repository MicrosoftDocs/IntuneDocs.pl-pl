---
title: Dodawanie aplikacji biznesowych dla systemu Windows do usługi Microsoft Intune
titleSuffix: ''
description: Dowiedz się, jak dodać aplikację biznesową (LOB) dla systemu Windows przy użyciu usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/29/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3d9b579e944827e511700073f0b3348b5ef20adc
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71724701"
---
# <a name="add-a-windows-line-of-business-app-to-microsoft-intune"></a>Dodawanie aplikacji biznesowych dla systemu Windows do usługi Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Aplikacja biznesowa (LOB) to aplikacja dodawana za pomocą pliku instalacyjnego aplikacji. Aplikacja tego typu jest zwykle pisana w firmie. W poniższych krokach przedstawiono wskazówki ułatwiające dodawanie aplikacji biznesowych dla systemu Windows do usługi Microsoft Intune.

## <a name="step-1-specify-the-software-setup-file"></a>Krok 1. Określanie pliku konfiguracji oprogramowania

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. W okienku **Intune** wybierz pozycję **Aplikacje klienckie**.
4. W obciążeniu **Aplikacje klienckie** wybierz kolejno pozycje **Zarządzanie** > **Aplikacje**.
5. Wybierz pozycję **Dodaj** powyżej listy aplikacji.
6. W okienku **Dodaj aplikację** wybierz opcję **Aplikacja biznesowa**.

## <a name="step-2-configure-the-app-package-file"></a>Krok 2: Konfigurowanie pliku pakietu aplikacji

1. W okienku **Dodaj aplikację** wybierz pozycję **Plik pakietu aplikacji**.
2. W okienku **Plik pakietu aplikacji** wybierz przycisk przeglądania. Następnie wybierz plik instalacyjny systemu Windows z rozszerzeniem **msi**, **appx** lub **appxbundle**.

    > [!NOTE]
    > Rozszerzenia plików aplikacji dla systemu Windows to **msi**, **appx**, **appxbundle**, **msix** i **msixbundle**.  

1. Po zakończeniu wybierz przycisk **OK**.


## <a name="step-3-configure-app-information"></a>Krok 3: Konfigurowanie informacji o aplikacji

1. W okienku **Dodaj aplikację** wybierz pozycję **Informacje o aplikacji**.
2. W okienku **Informacje o aplikacji** skonfiguruj następujące informacje. Niektóre wartości w tym okienku mogą zostać wypełnione automatycznie.
    - **Nazwa**: wprowadź nazwę aplikacji wyświetlaną w portalu firmy. Upewnij się, że wszystkie używane nazwy aplikacji są unikatowe. Jeśli dana nazwa aplikacji występuje dwa razy, w portalu firmy będzie widoczna tylko jedna aplikacja o tej nazwie.
    - **Opis**: Wprowadź opis aplikacji. Opis będzie widoczny w portalu firmy.
    - **Wydawca**: Wprowadź nazwę wydawcy aplikacji.
    - **Ignoruj wersję aplikacji**: wybierz wartość **Tak**, jeśli deweloper aplikacji automatycznie aktualizuje aplikację. Ta opcja dotyczy wyłącznie aplikacji mobilnych msi.
    - **Kategoria**: wybierz co najmniej jedną kategorię aplikacji — wbudowaną lub utworzoną samodzielnie. Kategorie ułatwiają użytkownikom znajdowanie aplikacji podczas przeglądania portalu firmy.
    - **Wyświetl jako polecaną aplikację w Portalu firmy**: Wyróżnij aplikację na stronie głównej Portalu firmy dla użytkowników przeglądających aplikacje.
    - **Adres URL informacji**: opcjonalnie wprowadź adres URL witryny internetowej zawierającej informacje o aplikacji. Adres URL będzie widoczny w portalu firmy.
    - **Adres URL zasad ochrony prywatności**: opcjonalnie wprowadź adres URL witryny internetowej zawierającej informacje dotyczące zasad ochrony prywatności w aplikacji. Adres URL będzie widoczny w portalu firmy.
    - **Argumenty wiersza polecenia**: opcjonalnie wprowadź argumenty wiersza polecenia, które chcesz zastosować do pliku msi po jego uruchomieniu.  Na przykład: **/q**. Nie dołączaj polecenia ani argumentów programu msiexec, takich jak **/i** lub **/x**, ponieważ są one używane automatycznie. Aby uzyskać więcej informacji, zobacz [Opcje wiersza polecenia](https://docs.microsoft.com/windows/desktop/Msi/command-line-options). Jeśli plik .MSI wymaga dodatkowych opcji wiersza polecenia, należy rozważyć użycie funkcji [Zarządzanie aplikacjami Win32](app-management.md).
    - **Deweloper**: opcjonalnie wprowadź nazwę dewelopera aplikacji.
    - **Właściciel**: opcjonalnie wprowadź nazwę właściciela aplikacji. Przykładem może być **Dział kadr**.
    - **Uwagi**: wprowadź wszelkie uwagi, które chcesz skojarzyć z tą aplikacją.
    - **Logo**: przekaż ikonę skojarzoną z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania portalu firmy.
3. Po zakończeniu wybierz przycisk **OK**.

## <a name="step-4-finish-up"></a>Krok 4. Zakończenie

1. W okienku **Dodaj aplikację** sprawdź poprawność skonfigurowanych informacji.
2. Wybierz pozycję **Dodaj**, aby przekazać aplikację do usługi Intune.

## <a name="step-5-update-a-line-of-business-app"></a>Krok 5. Aktualizowanie aplikacji biznesowej

[!INCLUDE [shared-proc-lob-updateapp](../includes/shared-proc-lob-updateapp.md)]

   > [!NOTE]
   > Aby usługa Intune mogła pomyślnie wdrożyć nowy plik APPX na urządzeniu, należy zwiększyć numer w ciągu znaków `Version` w pliku AppxManifest.xml w pakiecie APPX.
    
## <a name="configure-a-self-updating-mobile-msi-app-to-ignore-the-version-check-process"></a>Konfigurowanie mobilnej aplikacji MSI korzystającej z samoaktualizacji w celu ignorowania procesu sprawdzania wersji

Znaną mobilną aplikację MSI, która korzysta z samoaktualizacji, można skonfigurować tak, aby ignorowała proces sprawdzania wersji. 

Niektóre aplikacje oparte na instalatorze MSI są automatycznie aktualizowane przez dewelopera aplikacji. W przypadku tych automatycznie aktualizowanych aplikacji MSI możesz skonfigurować ustawienie **Ignoruj wersję aplikacji** w okienku **Informacje o aplikacji**. Gdy przełączysz to ustawienie na wartość **Tak**, usługa Microsoft Intune nie będzie wymuszać wersji aplikacji zainstalowanej na kliencie systemu Windows. 

Ta możliwość jest przydatna, aby uniknąć sytuacji wyścigu. Na przykład sytuacja wyścigu może wystąpić, gdy aplikacja jest automatycznie aktualizowana przez dewelopera aplikacji i aktualizowana przez usługę Intune. Obie aktualizacje mogą próbować wymusić na kliencie systemu Windows daną wersję aplikacji, co spowoduje konflikt.

## <a name="next-steps"></a>Następne kroki

- Utworzona przez Ciebie aplikacja jest wyświetlana na liście aplikacji. Teraz możesz ją przypisać do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).

- Dowiedz się więcej o sposobach, w jakie możesz monitorować właściwości i przypisania Twojej aplikacji. Zobacz [Monitorowanie informacji o aplikacji i przypisań](apps-monitor.md).

- Dowiedz się więcej o kontekście swojej aplikacji w usłudze Intune. Zobacz temat [Przegląd cyklu życia aplikacji w usłudze Microsoft Intune](app-lifecycle.md).
