---
title: Dodawanie aplikacji biznesowych dla systemu Android do usługi Microsoft Intune
description: Dowiedz się, jak dodać aplikację biznesową (LOB) dla systemu Android do usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 061d793c-c724-4cd9-9240-adb0cbda5661
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 783079786d19c0a65d44af96f9a3be9e2e817fc0
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71724792"
---
# <a name="add-an-android-line-of-business-app-to-microsoft-intune"></a>Dodawanie aplikacji biznesowych dla systemu Android do usługi Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Aplikacja biznesowa (LOB) to aplikacja dodawana do usługi Intune za pomocą pliku instalacyjnego aplikacji. Aplikacja tego typu jest zwykle pisana w firmie. Usługa Intune instaluje aplikację LOB na urządzeniu użytkownika. 

> [!Note]
> Więcej informacji na temat aplikacji LOB i konsoli dla deweloperów Google Play znajdziesz w temacie [Publikowanie prywatnych aplikacji (LOB) zarządzanych ze sklepu Google Play przy użyciu konsoli dla deweloperów Google](apps-add-android-for-work.md?#managed-google-play-private-lob-app-publishing-using-the-google-developer-console). 

> [!Note]
> W przypadku urządzeń z systemem Android dla pracowników patrz [Dodawanie aplikacji zarządzanych ze sklepu Google Play na urządzeniach firmowych z systemem Android za pomocą usługi Intune](apps-add-android-for-work.md). 

## <a name="step-1-specify-the-software-setup-file"></a>Krok 1. Określanie pliku konfiguracji oprogramowania

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. W okienku **Intune** wybierz pozycję **Aplikacje klienckie**.
3. W obciążeniu **Aplikacje klienckie** wybierz kolejno pozycje **Zarządzanie** > **Aplikacje**.
4. Wybierz pozycję **Dodaj** powyżej listy aplikacji.
5. W okienku **Dodaj aplikację** wybierz opcję **Aplikacja biznesowa**.

## <a name="step-2-configure-the-app-package-file"></a>Krok 2: Konfigurowanie pliku pakietu aplikacji

1. W okienku **Dodaj aplikację** wybierz pozycję **Plik pakietu aplikacji**.
2. W okienku **Plik pakietu aplikacji** wybierz przycisk przeglądania. Następnie wybierz plik instalacyjny systemu Android z rozszerzeniem **APK**.
3. Po zakończeniu wybierz przycisk **OK**.

## <a name="step-3-configure-app-information"></a>Krok 3: Konfigurowanie informacji o aplikacji

1. W okienku **Dodaj aplikację** wybierz pozycję **Informacje o aplikacji**.
2. W okienku **Informacje o aplikacji** dodaj szczegóły swojej aplikacji. W zależności od wybranej aplikacji niektóre wartości w tym okienku mogą zostać wypełnione automatycznie.
    - **Nazwa**: wprowadź nazwę aplikacji wyświetlaną w portalu firmy. Upewnij się, że wszystkie używane nazwy aplikacji są unikatowe. Jeśli dana nazwa aplikacji występuje dwa razy, w portalu firmy będzie widoczna tylko jedna aplikacja o tej nazwie.
    - **Opis**: wprowadź opis aplikacji. Opis będzie widoczny w portalu firmy.
    - **Wydawca**: Wprowadź nazwę wydawcy aplikacji.
    - **Minimalna wersja systemu operacyjnego**: wybierz z listy minimalną wersję systemu operacyjnego, w którym można zainstalować aplikację. W przypadku przypisania aplikacji do urządzenia z wcześniejszą wersją systemu operacyjnego instalacja nie będzie możliwa.
    - **Kategoria**: wybierz co najmniej jedną kategorię aplikacji — wbudowaną lub utworzoną samodzielnie. Kategorie ułatwiają użytkownikom znajdowanie aplikacji podczas przeglądania portalu firmy.
    - **Wyświetl jako polecaną aplikację w Portalu firmy**: Wyróżnij aplikację na stronie głównej Portalu firmy dla użytkowników przeglądających aplikacje.
    - **Adres URL informacji**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje o tej aplikacji. Adres URL będzie widoczny w portalu firmy.
    - **Adres URL zasad ochrony prywatności**: Opcjonalnie wprowadź adres URL witryny sieci Web zawierającej informacje dotyczące zasad ochrony prywatności w tej aplikacji. Adres URL będzie widoczny w portalu firmy.
    - **Deweloper**: opcjonalnie wprowadź nazwę dewelopera aplikacji.
    - **Właściciel**: opcjonalnie wprowadź nazwę właściciela aplikacji. Przykładem może być **Dział kadr**.
    - **Uwagi**: wprowadź wszelkie uwagi, które chcesz skojarzyć z tą aplikacją.
    - **Logo**: przekaż ikonę skojarzoną z aplikacją. Będzie ona wyświetlana jako ikona aplikacji podczas przeglądania Portalu firmy.
3. Po zakończeniu wybierz przycisk **OK**.

## <a name="step-4-finish-up"></a>Krok 4. Zakończenie

1. W okienku **Dodaj aplikację** sprawdź, czy szczegóły aplikacji są prawidłowe.
2. Wybierz pozycję **Dodaj**, aby przekazać aplikację do usługi Intune.

Utworzona przez Ciebie aplikacja jest teraz widoczna na liście aplikacji. Korzystając z listy, możesz przypisywać aplikację do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).

## <a name="step-5-update-a-line-of-business-app"></a>Krok 5. Aktualizowanie aplikacji biznesowej

[!INCLUDE [shared-proc-lob-updateapp](../includes/shared-proc-lob-updateapp.md)]

Jeśli na urządzeniu z systemem Android jest włączona opcja **Sprawdzaj aplikacje ze źródeł zewnętrznych**, przed zainstalowaniem aktualizacji zostanie wyświetlony odpowiedni komunikat. W przeciwnym razie aktualizacja zostanie zainstalowana automatycznie.

> [!Note]
> Aby usługa Intune mogła pomyślnie wdrożyć nowy plik APK na urządzeniu, należy zwiększyć numer w ciągu znaków `android:versionCode` w pliku AndroidManifest.xml w pakiecie APK.

## <a name="next-steps"></a>Następne kroki

- Utworzona przez Ciebie aplikacja jest wyświetlana na liście aplikacji. Teraz możesz ją przypisać do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).

- Dowiedz się więcej o sposobach, w jakie możesz monitorować właściwości i przypisania Twojej aplikacji. Zobacz [Monitorowanie informacji o aplikacji i przypisań](apps-monitor.md).

- Dowiedz się więcej o kontekście swojej aplikacji w usłudze Intune. Zobacz temat [Przegląd cyklów życia urządzeń i aplikacji](../fundamentals/device-lifecycle.md).