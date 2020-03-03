---
title: Dodawanie aplikacji biznesowych dla systemu Windows do usługi Microsoft Intune
titleSuffix: ''
description: Dowiedz się, jak dodać aplikację biznesową (LOB) dla systemu Windows przy użyciu usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/21/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ceb4d2354ca073cf05f526df7638aebf8f16d5b7
ms.sourcegitcommit: 5881979c45fc973cba382413eaa193d369b8dcf6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/24/2020
ms.locfileid: "77569493"
---
# <a name="add-a-windows-line-of-business-app-to-microsoft-intune"></a>Dodawanie aplikacji biznesowych dla systemu Windows do usługi Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Aplikacja biznesowa (LOB) to aplikacja dodawana za pomocą pliku instalacyjnego aplikacji. Aplikacja tego typu jest zwykle pisana w firmie. W poniższych krokach przedstawiono wskazówki ułatwiające dodawanie aplikacji biznesowych dla systemu Windows do usługi Microsoft Intune.

> [!IMPORTANT]
> Podczas wdrażania aplikacji Win32 przy użyciu pliku instalacyjnego z rozszerzeniem MSI (umieszczonej w pliku INTUNEWIN przy użyciu narzędzia do konwersji plików) rozważ użycie [rozszerzenia do zarządzania usługi Intune](../apps/intune-management-extension.md). Jeśli podczas rejestracji rozwiązania Autopilot pomieszasz instalacje aplikacji Win32 i aplikacji biznesowych, instalacja aplikacji może zakończyć się niepowodzeniem.  

## <a name="select-the-app-type"></a>Wybieranie typu aplikacji

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**.
3. W okienku **Wybierz typ aplikacji** w obszarze typów aplikacji **Inne** wybierz pozycję **Aplikacja biznesowa**.
4. Kliknij pozycję **Wybierz**. Zostaną wyświetlone kroki **dodawania aplikacji**.

## <a name="step-1---app-information"></a>Krok 1. Informacje o aplikacji

### <a name="select-the-app-package-file"></a>Wybieranie pliku pakietu aplikacji

1. W okienku **Dodawanie aplikacji** kliknij pozycję **Wybierz plik pakietu aplikacji**. 
2. W okienku **Plik pakietu aplikacji** wybierz przycisk przeglądania. Następnie wybierz plik instalacyjny systemu Windows z rozszerzeniem **msi**, **appx** lub **appxbundle**.
   Zostaną wyświetlone szczegóły aplikacji.

    > [!NOTE]
    > Rozszerzenia plików aplikacji dla systemu Windows to **msi**, **appx**, **appxbundle**, **msix** i **msixbundle**.  

3. Po zakończeniu wybierz przycisk **OK** w okienku **Plik pakietu aplikacji**, aby dodać aplikację.

### <a name="set-app-information"></a>Ustawianie informacje o aplikacji

1. Na stronie **Informacje o aplikacji** dodaj szczegóły aplikacji. W zależności od wybranej aplikacji niektóre wartości w tym okienku mogą zostać wypełnione automatycznie.
    - **Nazwa**: wprowadź nazwę aplikacji wyświetlaną w portalu firmy. Upewnij się, że wszystkie używane nazwy aplikacji są unikatowe. Jeśli dana nazwa aplikacji występuje dwa razy, w portalu firmy będzie widoczna tylko jedna aplikacja o tej nazwie.
    - **Opis**: wprowadź opis aplikacji. Opis będzie widoczny w portalu firmy.
    - **Wydawca**: Wprowadź nazwę wydawcy aplikacji.
    - **Minimalna wersja systemu operacyjnego**: wybierz z listy minimalną wersję systemu operacyjnego, w którym można zainstalować aplikację. W przypadku przypisania aplikacji do urządzenia z wcześniejszą wersją systemu operacyjnego instalacja nie będzie możliwa.
    - **Kategoria**: wybierz co najmniej jedną kategorię aplikacji — wbudowaną lub utworzoną samodzielnie. Kategorie ułatwiają użytkownikom znajdowanie aplikacji podczas przeglądania portalu firmy.
    - **Pokaż jako polecaną aplikację w Portalu firmy**: Wyróżnij aplikację na stronie głównej Portalu firmy dla użytkowników przeglądających aplikacje.
    - **Adres URL informacji**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o tej aplikacji. Adres URL będzie widoczny w portalu firmy.
    - **Adres URL zasad ochrony prywatności**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje dotyczące zasad ochrony prywatności w tej aplikacji. Adres URL będzie widoczny w portalu firmy.
    - **Deweloper**: opcjonalnie wprowadź nazwę dewelopera aplikacji.
    - **Właściciel**: opcjonalnie wprowadź nazwę właściciela aplikacji. Przykładem może być **Dział kadr**.
    - **Uwagi**: wprowadź wszelkie uwagi, które chcesz skojarzyć z tą aplikacją.
    - **Logo**: przekaż ikonę skojarzoną z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
2. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Tagi zakresu**.

## <a name="step-2---select-scope-tags-optional"></a>Krok 2. Wybieranie tagów zakresu (opcjonalnie)
Za pomocą tagów zakresu można określić, kto będzie mógł wyświetlać informacje o aplikacji klienckiej w usłudze Intune. Więcej informacji o tagach zakresu zawiera artykuł [Używanie kontroli dostępu opartej na rolach i tagów zakresu w rozproszonej infrastrukturze informatycznej](../fundamentals/scope-tags.md).

1. Kliknij pozycję **Wybierz tagi zakresu**, aby opcjonalnie dodać tagi zakresu dla aplikacji. 
2. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Przypisania**.

## <a name="step-3---assignments"></a>Krok 3. Przypisania

1. Wybierz przypisania grupy **Wymagane**, **Dostępne dla zarejestrowanych urządzeń** lub **Odinstaluj** dla aplikacji. Aby uzyskać więcej informacji, zobacz temat [Dodawanie grup w celu organizowania użytkowników i urządzeń](~/fundamentals/groups-add.md) i [Przypisywanie aplikacji do grup przy użyciu usługi Microsoft Intune](apps-deploy.md).
2. Kliknij przycisk **Dalej**, aby wyświetlić stronę **Recenzja i tworzenie**. 

## <a name="step-4---review--create"></a>Krok 4. Przegląd + tworzenie

1. Przejrzyj wartości i ustawienia wprowadzone dla aplikacji.
2. Gdy skończysz, kliknij pozycję **Utwórz**, aby dodać aplikację do usługi Intune.

    Zostanie wyświetlony blok **Omówienie** dotyczący aplikacji biznesowej.

Utworzona przez Ciebie aplikacja jest teraz widoczna na liście aplikacji. Korzystając z listy, możesz przypisywać aplikacje do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).

## <a name="update-a-line-of-business-app"></a>Aktualizowanie aplikacji biznesowej

[!INCLUDE [shared-proc-lob-updateapp](../includes/shared-proc-lob-updateapp.md)]

   > [!NOTE]
   > Aby usługa Intune mogła pomyślnie wdrożyć nowy plik APPX na urządzeniu, należy zwiększyć numer w ciągu znaków `Version` w pliku AppxManifest.xml w pakiecie APPX.

## <a name="configure-a-self-updating-mobile-msi-app-to-ignore-the-version-check-process"></a>Konfigurowanie mobilnej aplikacji MSI korzystającej z samoaktualizacji w celu ignorowania procesu sprawdzania wersji

Znaną mobilną aplikację MSI, która korzysta z samoaktualizacji, można skonfigurować tak, aby ignorowała proces sprawdzania wersji.

Niektóre aplikacje oparte na instalatorze MSI są automatycznie aktualizowane przez dewelopera aplikacji lub z wykorzystaniem innej metody aktualizacji. W przypadku tych automatycznie aktualizowanych aplikacji MSI możesz skonfigurować ustawienie **Ignoruj wersję aplikacji** w okienku **Informacje o aplikacji**. Gdy przełączysz to ustawienie na wartość **Tak**, usługa Microsoft Intune nie będzie wymuszać wersji aplikacji zainstalowanej na kliencie systemu Windows.

Ta możliwość jest przydatna, aby uniknąć sytuacji wyścigu. Na przykład sytuacja wyścigu może wystąpić, gdy aplikacja jest automatycznie aktualizowana przez dewelopera aplikacji i aktualizowana przez usługę Intune. Obie aktualizacje mogą próbować wymusić na kliencie systemu Windows daną wersję aplikacji, co spowoduje konflikt.

## <a name="next-steps"></a>Następne kroki

- Utworzona przez Ciebie aplikacja jest wyświetlana na liście aplikacji. Teraz możesz ją przypisać do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).

- Dowiedz się więcej o sposobach, w jakie możesz monitorować właściwości i przypisania Twojej aplikacji. Zobacz [Monitorowanie informacji o aplikacji i przypisań](apps-monitor.md).

- Dowiedz się więcej o kontekście swojej aplikacji w usłudze Intune. Zobacz temat [Przegląd cyklu życia aplikacji w usłudze Microsoft Intune](app-lifecycle.md).

- Dowiedz się więcej o aplikacjach Win32. Zobacz temat [Zarządzanie aplikacjami Win32](~/apps/apps-win32-app-management.md).
