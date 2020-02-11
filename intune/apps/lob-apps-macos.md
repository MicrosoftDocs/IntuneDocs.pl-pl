---
title: Jak dodawać aplikacje biznesowe systemu macOS do usługi Microsoft Intune
titleSuffix: ''
description: Dowiedz się, jak dodawać aplikacje biznesowe (LOB) systemu macOS do usługi Microsoft Intune.
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
ms.assetid: ef8008ac-8b85-4bfc-86ac-1f9fcbd3db76
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c7aa6af751e5ab3e1e3cdff6b1d2e3d6693f65df
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755174"
---
# <a name="how-to-add-macos-line-of-business-lob-apps-to-microsoft-intune"></a>Jak dodawać aplikacje biznesowe (LOB) systemu macOS do usługi Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Informacje przedstawione w tym artykule ułatwiają dodawanie aplikacji biznesowych systemu macOS do usługi Microsoft Intune. Musisz pobrać narzędzie zewnętrzne, aby wstępnie przetworzyć pliki *PKG* przed przekazaniem pliku biznesowego do usługi Microsoft Intune. Przetwarzanie wstępne plików *PKG* należy przeprowadzić na urządzeniu z systemem macOS.

> [!NOTE]
> Począwszy od wersji macOS Catalina 10.15, przed dodaniem aplikacji do usługi Intune, upewnij się, że Twoje aplikacje biznesowe dla systemu macOS zostały notarializowane. Jeśli deweloperzy aplikacji biznesowych nie notarializują swoich aplikacji, aplikacje nie będą działać na urządzeniach użytkowników z systemem macOS. Aby uzyskać więcej informacji na temat sprawdzania, czy aplikacja została notarializowana, odwiedź stronę [Notarize your macOS apps to prepare for macOS Catalina (Notarializowanie aplikacji dla systemu macOS w celu przygotowania się do korzystania z systemu macOS Catalina)](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Notarizing-your-macOS-apps-to-prepare-for-macOS/ba-p/808579).

> [!NOTE]
> Użytkownicy urządzeń z systemem macOS mogą usuwać niektóre wbudowane aplikacje dla systemu macOS, takie jak Stocks i Maps, ale nie można użyć usługi Intune do ponownego wdrożenia tych aplikacji. Jeśli użytkownicy końcowi usuwają te aplikacje, muszą przejść do sklepu z aplikacjami i ręcznie zainstalować je ponownie.

## <a name="before-your-start"></a>Przed rozpoczęciem

Przed przekazaniem pliku biznesowego do usługi Microsoft Intune musisz pobrać narzędzie zewnętrzne, oznaczyć pobrane narzędzie jako plik wykonywalny i użyć go do wstępnego przetworzenia plików *PKG*. Przetwarzanie wstępne plików *PKG* należy przeprowadzić na urządzeniu z systemem macOS. Użyj w usłudze Intune narzędzia opakowującego aplikacje dla komputerów Mac, aby umożliwić zarządzanie aplikacjami dla komputerów Mac przez usługę Intune.

> [!IMPORTANT]
> Plik *PKG* należy podpisać przy użyciu certyfikatu „Instalator identyfikatora dewelopera” uzyskanego z konta dewelopera firmy Apple. Tylko pliki *PKG* mogą być używane do przekazywania aplikacji biznesowych systemu macOS do usługi Microsoft Intune. Konwersja innych formatów, na przykład *DMG* do *PKG*, nie jest obsługiwana.
>

1. Pobierz [narzędzie opakowujące aplikacje w usłudze Intune dla komputerów Mac](https://github.com/msintuneappsdk/intune-app-wrapping-tool-mac).

    > [!NOTE]
    > **Narzędzie opakowujące aplikacje w usłudze Intune dla komputerów Mac** musi działać na maszynie z systemem macOS. 

2. Oznacz pobrane narzędzie jako plik wykonywalny:
   - Uruchom aplikację terminalu.
   - Zmień katalog na lokalizację, w której znajduje się plik `IntuneAppUtil`.
   - Uruchom następujące polecenie, aby narzędzie było plikiem wykonywalnym:<br> 
       `chmod +x IntuneAppUtil`

3. Użyj polecenia `IntuneAppUtil` w obrębie **narzędzia opakowującego aplikacje w usłudze Intune dla komputerów Mac** w celu opakowania pliku aplikacji LOB *PKG* z poziomu pliku *INTUNEMAC*.<br>

    Przykładowe polecenia do użycia z narzędziem opakowującym aplikacje w usłudze Intune dla systemu macOS:
    > [!IMPORTANT]
    > Upewnij się, że argument `<source_file>` nie zawiera spacji, przed uruchomieniem poleceń `IntuneAppUtil`.

    - `IntuneAppUtil -h`<br>
    To polecenie wyświetla informacje o użyciu narzędzia.
    
    - `IntuneAppUtil -c <source_file> -o <output_file> [-v]`<br>
    To polecenie opakowuje plik aplikacji LOB *PKG* do pliku *INTUNEMAC*.
    
    - `IntuneAppUtil -r <filename.intunemac> [-v]`<br>
    To polecenie wyodrębnia wykryte parametry i wersję utworzonego pliku *INTUNEMAC*.

## <a name="select-the-app-type"></a>Wybieranie typu aplikacji

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**.
3. W okienku **Wybierz typ aplikacji** w obszarze typów aplikacji **Inne** wybierz pozycję **Aplikacja biznesowa**.
4. Kliknij pozycję **Wybierz**. Zostaną wyświetlone kroki **dodawania aplikacji**.

## <a name="step-1---app-information"></a>Krok 1. Informacje o aplikacji

### <a name="select-the-app-package-file"></a>Wybieranie pliku pakietu aplikacji

1. W okienku **Dodawanie aplikacji** kliknij pozycję **Wybierz plik pakietu aplikacji**. 
2. W okienku **Plik pakietu aplikacji** wybierz przycisk przeglądania. Następnie wybierz plik instalacyjny systemu macOS z rozszerzeniem *intunemac*.
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

Utworzona aplikacja pojawi się na liście aplikacji, skąd można ją przypisać do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).

> [!NOTE]
> Jeśli plik *PKG* zawiera wiele aplikacji lub instalatorów aplikacji, usługa Microsoft Intune będzie zgłaszać tylko, że *aplikacja* została pomyślnie zainstalowana po wykryciu wszystkich aplikacji zainstalowanych na urządzeniu.

## <a name="update-a-line-of-business-app"></a>Aktualizowanie aplikacji biznesowej

[!INCLUDE [shared-proc-lob-updateapp](../includes/shared-proc-lob-updateapp.md)]

> [!NOTE]
> Aby usługa Intune mogła pomyślnie wdrożyć nowy plik *PKG* na urządzeniu, należy zwiększyć numer w ciągu znaków `version` i `CFBundleVersion` w pliku *packageinfo* w pakiecie *PKG*.

## <a name="next-steps"></a>Następne kroki

- Utworzona aplikacja jest wyświetlana na liście aplikacji. Teraz można przypisać ją do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).

- Dowiedz się więcej o sposobach, w jakie możesz monitorować właściwości i przypisania Twojej aplikacji. Aby uzyskać więcej informacji, zobacz [Monitorowanie informacji o aplikacji i przypisań](apps-monitor.md).

- Dowiedz się więcej o kontekście swojej aplikacji w usłudze Intune. Aby uzyskać więcej informacji, zobacz [Przegląd cyklów życia urządzeń i aplikacji](../fundamentals/device-lifecycle.md)
