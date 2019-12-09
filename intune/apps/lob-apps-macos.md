---
title: Jak dodawać aplikacje biznesowe systemu macOS do usługi Microsoft Intune
titleSuffix: ''
description: Dowiedz się, jak dodawać aplikacje biznesowe (LOB) systemu macOS do usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
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
ms.openlocfilehash: 81a084528fdc500bf9b6de0ca5fa847c2e0b3797
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563927"
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
    
    - `IntuneAppUtil -h`<br>
    To polecenie wyświetla informacje o użyciu narzędzia.
    
    - `IntuneAppUtil -c <source_file> -o <output_file> [-v]`<br>
    To polecenie opakowuje plik aplikacji LOB *PKG* do pliku *INTUNEMAC*.
    
    - `IntuneAppUtil -r <filename.intunemac> [-v]`<br>
    To polecenie wyodrębnia wykryte parametry i wersję utworzonego pliku *INTUNEMAC*.

## <a name="step-1---specify-the-software-setup-file"></a>Krok 1. Określanie lokalizacji pliku konfiguracji oprogramowania

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz kolejno pozycje **Aplikacje** > **Wszystkie aplikacje** > **Dodaj**.
3. W okienku **Dodaj aplikację** wybierz opcję **Aplikacja biznesowa** jako **Typ aplikacji**.

## <a name="step-2---configure-the-app-package-file"></a>Krok 2. Konfigurowanie pliku pakietu aplikacji

1. W okienku **Dodaj aplikację** wybierz plik **Pakiet aplikacji**.
2. W okienku **Plik pakietu aplikacji** wybierz przycisk przeglądania, a następnie wybierz plik instalacji systemu macOS z rozszerzeniem *INTUNEMAC*.
3. Gdy skończysz, wybierz przycisk **OK**.


## <a name="step-3---configure-app-information"></a>Krok 3. Konfigurowanie informacji o aplikacji

1. W okienku **Dodaj aplikację** wybierz pozycję **Informacje o aplikacji**.
2. W okienku **Informacje o aplikacji** dodaj szczegóły swojej aplikacji. W zależności od wybranej aplikacji niektóre wartości w tym okienku mogą zostać wypełnione automatycznie:
    - **Nazwa** — wprowadź nazwę aplikacji do wyświetlenia w Portalu firmy. Upewnij się, że wszystkie używane nazwy aplikacji są unikatowe. Jeśli dana nazwa aplikacji występuje dwa razy, użytkownicy Portalu firmy będą widzieć tylko jedną z aplikacji o tej nazwie.
    - **Opis** — wprowadź opis aplikacji, który ma być wyświetlany użytkownikom w Portalu firmy.
    - **Wydawca** — wprowadź nazwę wydawcy aplikacji.
    - **Minimalna wersja systemu operacyjnego** — wybierz z listy minimalną wersję systemu operacyjnego, na którym można zainstalować aplikację. W przypadku przypisania aplikacji do urządzenia z wcześniejszą wersją systemu operacyjnego instalacja nie będzie możliwa.
    - **Kategoria** — wybierz co najmniej jedną wbudowaną lub utworzoną przez siebie kategorię aplikacji. Ułatwi to użytkownikom znajdowanie aplikacji podczas przeglądania Portalu firmy.
    - **Wyświetl jako polecaną aplikację w portalu firmy** — wyróżnij aplikację na stronie głównej portalu firmy dla użytkowników przeglądających aplikacje.
    - **Adres URL informacji** — opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Adres URL zasad ochrony prywatności** — opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o zasadach ochrony prywatności mających zastosowanie do aplikacji. Adres będzie widoczny dla użytkowników Portalu firmy.
    - **Deweloper** — opcjonalnie wprowadź nazwę dewelopera aplikacji.
    - **Właściciel** — opcjonalnie wprowadź nazwę właściciela aplikacji, na przykład **Dział kadr**.
    - **Uwagi** — wprowadź wszelkie uwagi, które chcesz skojarzyć z aplikacją.
    - **Logo** — przekaż ikonę, która zostanie skojarzona z aplikacją. Jest ona wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
3. Gdy skończysz, wybierz przycisk **OK**.

## <a name="step-4---finish-up"></a>Krok 4. Zakończenie

1. W okienku **Dodaj aplikację** sprawdź poprawność szczegółów aplikacji.
2. Wybierz pozycję **Dodaj**, aby przekazać aplikację do usługi Intune.

Utworzona aplikacja pojawi się na liście aplikacji, skąd można ją przypisać do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).

> [!NOTE]
> Jeśli plik *PKG* zawiera wiele aplikacji lub instalatorów aplikacji, usługa Microsoft Intune będzie zgłaszać tylko, że *aplikacja* została pomyślnie zainstalowana po wykryciu wszystkich aplikacji zainstalowanych na urządzeniu.

## <a name="step-5---update-a-line-of-business-app"></a>Krok 5. Aktualizacja aplikacji biznesowej

[!INCLUDE [shared-proc-lob-updateapp](../includes/shared-proc-lob-updateapp.md)]

> [!NOTE]
> Aby usługa Intune mogła pomyślnie wdrożyć nowy plik *PKG* na urządzeniu, należy zwiększyć numer w ciągu znaków `version` i `CFBundleVersion` w pliku *packageinfo* w pakiecie *PKG*.

## <a name="next-steps"></a>Następne kroki

- Utworzona aplikacja jest wyświetlana na liście aplikacji. Teraz można przypisać ją do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).

- Dowiedz się więcej o sposobach, w jakie możesz monitorować właściwości i przypisania Twojej aplikacji. Aby uzyskać więcej informacji, zobacz [Monitorowanie informacji o aplikacji i przypisań](apps-monitor.md).

- Dowiedz się więcej o kontekście swojej aplikacji w usłudze Intune. Aby uzyskać więcej informacji, zobacz [Przegląd cyklów życia urządzeń i aplikacji](../fundamentals/device-lifecycle.md)
