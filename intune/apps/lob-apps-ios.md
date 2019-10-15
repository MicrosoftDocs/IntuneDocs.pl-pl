---
title: Dodawanie do usługi Microsoft Intune aplikacji biznesowych dla systemu iOS
titleSuffix: ''
description: Dowiedz się, jak dodać aplikację biznesową (LOB) dla systemu iOS do usługi Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/15/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 099101e8-4b22-40ac-ba19-82ba5c71944c
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 59cde9d38523c3683d56c54b66b563b7a95c49f9
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71724727"
---
# <a name="add-an-ios-line-of-business-app-to-microsoft-intune"></a>Dodawanie do usługi Microsoft Intune aplikacji biznesowych dla systemu iOS

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Informacje przedstawione w tym artykule ułatwiają dodawanie aplikacji biznesowych (LOB, line-of-business) dla systemu iOS do usługi Microsoft Intune. Aplikacja biznesowa (LOB) to aplikacja dodawana do usługi Intune za pomocą pliku instalacyjnego aplikacji IPA. Aplikacja tego typu jest zwykle pisana w firmie. Najpierw musisz dołączyć do programu dla deweloperów aplikacji systemu iOS dla przedsiębiorstw. Więcej informacji na ten temat znajdziesz w [witrynie firmy Apple](https://developer.apple.com/programs/ios/enterprise/).

>[!NOTE]
>Użytkownicy urządzeń z systemem iOS mogą usuwać niektóre wbudowane aplikacje dla systemu iOS, takie jak Stocks i Maps. Nie można użyć usługi Intune do ponownego wdrożenia tych aplikacji. Jeśli użytkownicy usunęli te aplikacje, muszą przejść do sklepu z aplikacjami i ponownie ręcznie je zainstalować.
>
>Aplikacje LOB systemu iOS mają maksymalny limit rozmiaru wynoszący 4 GB na aplikację.

## <a name="step-1-specify-the-software-setup-file"></a>Krok 1. Określanie pliku konfiguracji oprogramowania

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. W okienku **Intune** wybierz pozycję **Aplikacje klienckie**.
4. W obciążeniu **Aplikacje klienckie** wybierz kolejno pozycje **Zarządzanie** > **Aplikacje**.
5. Wybierz pozycję **Dodaj** powyżej listy aplikacji.
6. W okienku **Dodaj aplikację** wybierz opcję **Aplikacja biznesowa**.

## <a name="step-2-configure-the-app-package-file"></a>Krok 2: Konfigurowanie pliku pakietu aplikacji

1. W okienku **Dodaj aplikację** wybierz pozycję **Plik pakietu aplikacji**.
2. W okienku **Plik pakietu aplikacji** wybierz przycisk przeglądania. Następnie wybierz plik instalacyjny systemu iOS z rozszerzeniem **.ipa**.
3. Po zakończeniu wybierz przycisk **OK**.


## <a name="step-3-configure-app-information"></a>Krok 3: Konfigurowanie informacji o aplikacji

1. W okienku **Dodaj aplikację** wybierz pozycję **Informacje o aplikacji**.
2. W okienku **Informacje o aplikacji** dodaj szczegóły swojej aplikacji. W zależności od wybranej aplikacji niektóre wartości w tym okienku mogą zostać wypełnione automatycznie.
    - **Nazwa**: wprowadź nazwę aplikacji wyświetlaną w portalu firmy. Upewnij się, że wszystkie używane nazwy aplikacji są unikatowe. Jeśli dana nazwa aplikacji występuje dwa razy, w portalu firmy będzie widoczna tylko jedna aplikacja o tej nazwie.
    - **Opis**: Wprowadź opis aplikacji. Opis będzie widoczny w portalu firmy.
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

1. W okienku **Dodaj aplikację** sprawdź poprawność szczegółów aplikacji.
2. Wybierz opcję **Dodaj**, aby przekazać aplikację do usługi Intune.

Utworzona przez Ciebie aplikacja jest widoczna na liście aplikacji. Korzystając z listy, możesz przypisywać aplikacje do wybranych grup. Aby uzyskać pomoc, zobacz artykuł [How to assign apps to groups](apps-deploy.md) (Jak przypisać aplikacje do grupy).

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