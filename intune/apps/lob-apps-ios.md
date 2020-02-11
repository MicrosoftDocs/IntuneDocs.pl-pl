---
title: Dodawanie do usługi Microsoft Intune aplikacji biznesowych dla systemu iOS
titleSuffix: ''
description: Dowiedz się, jak dodać aplikację biznesową (LOB) dla systemu iOS do usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/23/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 099101e8-4b22-40ac-ba19-82ba5c71944c
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0b7c0a7dfa4337983c12ada2d0f415c771bd0548
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755191"
---
# <a name="add-an-ios-line-of-business-app-to-microsoft-intune"></a>Dodawanie do usługi Microsoft Intune aplikacji biznesowych dla systemu iOS

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Informacje przedstawione w tym artykule ułatwiają dodawanie aplikacji biznesowych (LOB, line-of-business) dla systemu iOS do usługi Microsoft Intune. Aplikacja biznesowa (LOB) to aplikacja dodawana do usługi Intune za pomocą pliku instalacyjnego aplikacji IPA. Aplikacja tego typu jest zwykle pisana w firmie. Najpierw musisz dołączyć do programu dla deweloperów aplikacji systemu iOS dla przedsiębiorstw. Więcej informacji na ten temat znajdziesz w [witrynie firmy Apple](https://developer.apple.com/programs/ios/enterprise/).

>[!NOTE]
>Użytkownicy urządzeń z systemem iOS mogą usuwać niektóre wbudowane aplikacje dla systemu iOS, takie jak Stocks i Maps. Nie można użyć usługi Intune do ponownego wdrożenia tych aplikacji. Jeśli użytkownicy usunęli te aplikacje, muszą przejść do sklepu z aplikacjami i ponownie ręcznie je zainstalować.
>
>Aplikacje LOB systemu iOS mają maksymalny limit rozmiaru wynoszący 4 GB na aplikację.

## <a name="select-the-app-type"></a>Wybieranie typu aplikacji

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**.
3. W okienku **Wybierz typ aplikacji** w obszarze typów aplikacji **Inne** wybierz pozycję **Aplikacja biznesowa**.
4. Kliknij pozycję **Wybierz**. Zostaną wyświetlone kroki **dodawania aplikacji**.

## <a name="step-1---app-information"></a>Krok 1. Informacje o aplikacji

### <a name="select-the-app-package-file"></a>Wybieranie pliku pakietu aplikacji

1. W okienku **Dodawanie aplikacji** kliknij pozycję **Wybierz plik pakietu aplikacji**. 
2. W okienku **Plik pakietu aplikacji** wybierz przycisk przeglądania. Następnie wybierz plik instalacyjny systemu iOS z rozszerzeniem **IPA**.
   Zostaną wyświetlone szczegóły aplikacji.
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

> [!NOTE]
> 30 dni przed wygaśnięciem profilu aprowizowania dla aplikacji LOB systemu iOS otrzymasz odpowiednie powiadomienie.

## <a name="step-5-update-a-line-of-business-app"></a>Krok 5. Aktualizowanie aplikacji biznesowej

[!INCLUDE [shared-proc-lob-updateapp](../includes/shared-proc-lob-updateapp.md)]

Aktualizacja aplikacji biznesowej zostanie zainstalowana automatycznie.

> [!NOTE]
> Aby usługa Intune mogła wdrożyć nowy plik IPA na urządzeniu, należy zwiększyć numer w ciągu znaków `CFBundleVersion` w pliku Info.plist w pakiecie IPA.

## <a name="next-steps"></a>Następne kroki

- Utworzona przez Ciebie aplikacja jest wyświetlana na liście aplikacji. Teraz możesz ją przypisać do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).

- Dowiedz się więcej o sposobach, w jakie możesz monitorować właściwości i przypisania Twojej aplikacji. Zobacz [Monitorowanie informacji o aplikacji i przypisań](apps-monitor.md).

- Dowiedz się więcej o kontekście swojej aplikacji w usłudze Intune. Zobacz temat [Przegląd cyklów życia urządzeń i aplikacji](../fundamentals/device-lifecycle.md).
