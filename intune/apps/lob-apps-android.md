---
title: Dodawanie aplikacji biznesowych dla systemu Android do usługi Microsoft Intune
description: Dowiedz się, jak dodać aplikację biznesową (LOB) dla systemu Android do usługi Microsoft Intune.
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
ms.assetid: 061d793c-c724-4cd9-9240-adb0cbda5661
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cd3736a08f09fcb5ee953626c63e336ca7f9af81
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755208"
---
# <a name="add-an-android-line-of-business-app-to-microsoft-intune"></a>Dodawanie aplikacji biznesowych dla systemu Android do usługi Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Aplikacja biznesowa (LOB) to aplikacja dodawana do usługi Intune za pomocą pliku instalacyjnego aplikacji. Aplikacja tego typu jest zwykle pisana w firmie. Usługa Intune instaluje aplikację LOB na urządzeniu użytkownika. 

> [!Note]
> Więcej informacji na temat aplikacji biznesowych (LOB) i konsoli dla deweloperów Google Play znajdziesz w temacie [Managed Google Play private (LOB) app publishing using the Google Developer Console](apps-add-android-for-work.md?#managed-google-play-private-lob-app-publishing-using-the-google-developer-console) (Publikowanie prywatnych aplikacji (LOB) zarządzanych ze sklepu Google Play przy użyciu konsoli dla deweloperów Google). 

> [!Note]
> W przypadku urządzeń z systemem Android dla pracowników patrz [Add Managed Google Play apps to Android Enterprise devices with Intune](apps-add-android-for-work.md) (Dodawanie aplikacji zarządzanych ze sklepu Google Play na urządzeniach firmowych z systemem Android za pomocą usługi Intune). 

## <a name="select-the-app-type"></a>Wybieranie typu aplikacji

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**.
3. W okienku **Wybierz typ aplikacji** w obszarze typów aplikacji **Inne** wybierz pozycję **Aplikacja biznesowa**.
4. Kliknij pozycję **Wybierz**. Zostaną wyświetlone kroki **dodawania aplikacji**.

## <a name="step-1---app-information"></a>Krok 1. Informacje o aplikacji

### <a name="select-the-app-package-file"></a>Wybieranie pliku pakietu aplikacji

1. W okienku **Dodawanie aplikacji** kliknij pozycję **Wybierz plik pakietu aplikacji**. 
2. W okienku **Plik pakietu aplikacji** wybierz przycisk przeglądania. Następnie wybierz plik instalacyjny systemu Android z rozszerzeniem **APK**.
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

## <a name="step-5-update-a-line-of-business-app"></a>Krok 5. Aktualizowanie aplikacji biznesowej

[!INCLUDE [shared-proc-lob-updateapp](../includes/shared-proc-lob-updateapp.md)]

Jeśli na urządzeniu z systemem Android jest włączona opcja **Sprawdzaj aplikacje ze źródeł zewnętrznych**, przed zainstalowaniem aktualizacji zostanie wyświetlony odpowiedni komunikat. W przeciwnym razie aktualizacja zostanie zainstalowana automatycznie.

> [!Note]
> Aby usługa Intune mogła pomyślnie wdrożyć nowy plik APK na urządzeniu, należy zwiększyć numer w ciągu znaków `android:versionCode` w pliku AndroidManifest.xml w pakiecie APK.

## <a name="next-steps"></a>Następne kroki

- Utworzona przez Ciebie aplikacja jest wyświetlana na liście aplikacji. Teraz możesz ją przypisać do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).

- Dowiedz się więcej o sposobach, w jakie możesz monitorować właściwości i przypisania Twojej aplikacji. Zobacz [Monitorowanie informacji o aplikacji i przypisań](apps-monitor.md).

- Dowiedz się więcej o kontekście swojej aplikacji w usłudze Intune. Zobacz temat [Przegląd cyklów życia urządzeń i aplikacji](../fundamentals/device-lifecycle.md).
