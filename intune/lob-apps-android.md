---
title: Jak dodawać aplikacje biznesowe dla systemu Android do usługi Microsoft Intune
titlesuffix: ''
description: Dowiedz się, jak dodawać aplikacje biznesowe (LOB) dla systemu Android do usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 061d793c-c724-4cd9-9240-adb0cbda5661
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a5b09f855b6da65edf3c560725b339528f2bcfaa
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/22/2018
---
# <a name="how-to-add-android-line-of-business-lob-apps-to-microsoft-intune"></a>Jak dodawać aplikacje biznesowe dla systemu Android do usługi Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Aplikacja biznesowa (LOB) to aplikacja dodawana do usługi Intune za pomocą pliku instalacyjnego aplikacji. Aplikacje tego typu są zwykle pisane w firmie. Usługa Intune instaluje aplikację LOB na urządzeniu użytkownika. 

> [!Note]
> Aby uzyskać więcej informacji o aplikacjach biznesowych (LOB) ze sklepu Google Play dla firm, zobacz [Praca z aplikacją biznesową ze sklepu Google Play dla firm](apps-add-android-for-work.md?#working-with-a-line-of-business-app-from-the-google-play-for-work-store). 

## <a name="step-1---specify-the-software-setup-file"></a>Krok 1. Określanie lokalizacji pliku konfiguracji oprogramowania

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Aplikacje mobilne**.
4. W obciążeniu **Aplikacje mobilne** wybierz kolejno pozycje **Zarządzaj** > **Aplikacje**.
5. Wybierz pozycję **Dodaj** powyżej listy aplikacji.
6. W okienku **Dodaj aplikację** wybierz pozycję **Aplikacja biznesowa**.

## <a name="step-2---configure-the-app-package-file"></a>Krok 2. Konfigurowanie pliku pakietu aplikacji

1. W okienku **Dodaj aplikację** wybierz plik **Pakiet aplikacji**.
2. W okienku pliku **Pakiet aplikacji** kliknij przycisk przeglądania i wybierz plik instalacyjny systemu Android z rozszerzeniem **.apk**.
3. Gdy skończysz, wybierz przycisk **OK**.


## <a name="step-3---configure-app-information"></a>Krok 3. Konfigurowanie informacji o aplikacji

1. W okienku **Dodaj aplikację** wybierz plik **Pakiet aplikacji**.
2. W okienku **Informacje o aplikacji** dodaj szczegóły swojej aplikacji. W zależności od wybranej aplikacji niektóre wartości w tym okienku mogą zostać wypełnione automatycznie:
    - **Nazwa** — wprowadź nazwę aplikacji do wyświetlenia w Portalu firmy. Upewnij się, że wszystkie używane nazwy aplikacji są unikatowe. Jeśli dana nazwa aplikacji występuje dwa razy, użytkownicy Portalu firmy będą widzieć tylko jedną z aplikacji o tej nazwie.
    - **Opis** — wprowadź opis aplikacji, który ma być wyświetlany użytkownikom w Portalu firmy.
    - **Wydawca** — wprowadź nazwę wydawcy aplikacji.
    - **Minimalna wersja systemu operacyjnego** — wybierz z listy minimalną wersję systemu operacyjnego, na którym można zainstalować aplikację. W przypadku przypisania aplikacji do urządzenia z wcześniejszą wersją systemu operacyjnego instalacja nie będzie możliwa.
    - **Ignoruj wersję aplikacji** — ustaw opcję na **Tak**, jeśli aplikacja jest automatycznie aktualizowania przez dewelopera aplikacji.
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

1. W okienku **Dodaj aplikację** sprawdź informacje dotyczące aplikacji.
2. Wybierz pozycję **Dodaj**, aby przekazać aplikację do usługi Intune.

Utworzona aplikacja będzie wyświetlana na liście aplikacji, skąd można ją przypisać do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).

## <a name="step-5---update-a-line-of-business-app"></a>Krok 5. Aktualizacja aplikacji biznesowej

[!INCLUDE[shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

> [!Note]
> Aby usługa Intune mogła pomyślnie wdrożyć nowy plik APK na urządzeniu, należy zwiększyć numer w ciągu znaków android:versionCode w pliku AndroidManifest.xml w pakiecie APK.

## <a name="next-steps"></a>Następne kroki

- Utworzona aplikacja jest wyświetlana na liście aplikacji. Teraz można przypisać ją do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).

- Dowiedz się więcej o sposobach, w jakie możesz monitorować właściwości i przypisania Twojej aplikacji. Aby uzyskać więcej informacji, zobacz [Monitorowanie informacji o aplikacji i przypisań](apps-monitor.md).

- Dowiedz się więcej o kontekście swojej aplikacji w usłudze Intune. Aby uzyskać więcej informacji, zobacz [Przegląd cyklów życia urządzeń i aplikacji](introduction-device-app-lifecycles.md)
