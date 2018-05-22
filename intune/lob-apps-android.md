---
title: Dodawanie aplikacji biznesowych dla systemu Android do usługi Microsoft Intune
titlesuffix: ''
description: Dowiedz się, jak dodawać aplikacje biznesowe dla systemu Android do usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 061d793c-c724-4cd9-9240-adb0cbda5661
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 22470356c921eea17e4d2b3d57f796fe51568ee1
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
---
# <a name="add-an-android-line-of-business-app-to-microsoft-intune"></a>Dodawanie aplikacji biznesowych dla systemu Android do usługi Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Aplikacja biznesowa (LOB) to aplikacja dodawana do usługi Intune za pomocą pliku instalacyjnego aplikacji. Aplikacja tego typu jest zwykle pisana w firmie. Usługa Intune instaluje aplikację LOB na urządzeniu użytkownika. 

> [!Note]
> Aby uzyskać więcej informacji o aplikacjach LOB ze sklepu Google Play dla firm, zobacz [Praca z aplikacją biznesową ze sklepu Google Play dla firm](apps-add-android-for-work.md?#working-with-a-line-of-business-app-from-the-google-play-for-work-store). 

## <a name="step-1-specify-the-software-setup-file"></a>Krok 1. Określanie lokalizacji pliku konfiguracji oprogramowania

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz pozycję **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Aplikacje mobilne**.
4. W obciążeniu **Aplikacje mobilne** wybierz kolejno pozycje **Zarządzaj** > **Aplikacje**.
5. Wybierz pozycję **Dodaj** powyżej listy aplikacji.
6. W okienku **Dodaj aplikację** wybierz opcję **Aplikacja biznesowa**.

## <a name="step-2-configure-the-app-package-file"></a>Krok 2. Konfigurowanie pliku pakietu aplikacji

1. W okienku **Dodaj aplikację** wybierz pozycję **Plik pakietu aplikacji**.
2. W okienku **Plik pakietu aplikacji** wybierz przycisk przeglądania. Następnie wybierz plik instalacyjny systemu Android z rozszerzeniem **APK**.
3. Po zakończeniu wybierz przycisk **OK**.


## <a name="step-3-configure-app-information"></a>Krok 3. Konfigurowanie informacji o aplikacji

1. W okienku **Dodaj aplikację** wybierz pozycję **Informacje o aplikacji**.
2. W okienku **Informacje o aplikacji** dodaj szczegóły swojej aplikacji. W zależności od wybranej aplikacji niektóre wartości w tym okienku mogą zostać wypełnione automatycznie.
    - **Nazwa**: wprowadź nazwę aplikacji wyświetlaną w portalu firmy. Upewnij się, że wszystkie używane nazwy aplikacji są unikatowe. Jeśli dana nazwa aplikacji występuje dwa razy, w portalu firmy będzie widoczna tylko jedna aplikacja o tej nazwie.
    - **Opis**: wprowadź opis aplikacji. Opis będzie widoczny w portalu firmy.
    - **Wydawca**: wprowadź nazwę wydawcy aplikacji.
    - **Minimalna wersja systemu operacyjnego**: wybierz z listy minimalną wersję systemu operacyjnego, w którym można zainstalować aplikację. W przypadku przypisania aplikacji do urządzenia z wcześniejszą wersją systemu operacyjnego instalacja nie będzie możliwa.
    - **Ignoruj wersję aplikacji**: wybierz wartość **Tak**, jeśli deweloper aplikacji automatycznie aktualizuje aplikację.
    - **Kategoria**: wybierz co najmniej jedną wbudowaną kategorię aplikacji lub kategorię utworzoną przez siebie. Kategorie ułatwiają użytkownikom znajdowanie aplikacji podczas przeglądania portalu firmy.
    - **Wyświetl jako polecaną aplikację w portalu firmy**: wyróżnij aplikację na stronie głównej portalu firmy dla użytkowników przeglądających aplikacje.
    - **Adres URL informacji**: opcjonalnie wprowadź adres URL witryny internetowej zawierającej informacje o tej aplikacji. Adres URL będzie widoczny w portalu firmy.
    - **Adres URL zasad ochrony prywatności**: opcjonalnie wprowadź adres URL witryny internetowej zawierającej informacje o zasadach ochrony prywatności w tej aplikacji. Adres URL będzie widoczny w portalu firmy.
    - **Deweloper**: opcjonalnie wprowadź nazwę dewelopera aplikacji.
    - **Właściciel**: opcjonalnie wprowadź nazwę właściciela aplikacji. Przykładem może być **Dział kadr**.
    - **Uwagi**: wprowadź wszelkie uwagi, które chcesz skojarzyć z tą aplikacją.
    - **Logo**: przekaż ikonę, która zostanie skojarzona z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
3. Po zakończeniu wybierz przycisk **OK**.

## <a name="step-4-finish-up"></a>Krok 4. Zakończenie

1. W okienku **Dodaj aplikację** sprawdź, czy szczegóły aplikacji są prawidłowe.
2. Wybierz pozycję **Dodaj**, aby przekazać aplikację do usługi Intune.

Utworzona przez Ciebie aplikacja jest teraz widoczna na liście aplikacji. Korzystając z listy, możesz przypisywać aplikację do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).

## <a name="step-5-update-a-line-of-business-app"></a>Krok 5. Aktualizacja aplikacji biznesowej

[!INCLUDE [shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

> [!Note]
> Aby usługa Intune mogła pomyślnie wdrożyć nowy plik APK na urządzeniu, należy zwiększyć numer w ciągu znaków `android:versionCode` w pliku AndroidManifest.xml w pakiecie APK.

## <a name="next-steps"></a>Następne kroki

- Utworzona przez Ciebie aplikacja jest wyświetlana na liście aplikacji. Teraz możesz ją przypisać do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).

- Dowiedz się więcej o sposobach, w jakie możesz monitorować właściwości i przypisania Twojej aplikacji. Zobacz [Monitorowanie informacji o aplikacji i przypisań](apps-monitor.md).

- Dowiedz się więcej o kontekście swojej aplikacji w usłudze Intune. Zobacz temat [Przegląd cyklów życia urządzeń i aplikacji](introduction-device-app-lifecycles.md).
