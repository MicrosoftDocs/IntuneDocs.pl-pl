---
title: Ustawienia filtru zawartości internetowej dla urządzeń z systemem iOS w usłudze Microsoft Intune
titlesuffix: ''
description: Informacje na temat ustawień, których można użyć w celu umożliwienia i zablokowania dostępu do witryn internetowych z urządzeń z systemem iOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1c8eb121b3db52f0fdfc30d7d8dff7ef0f7bf97b
ms.sourcegitcommit: f21287c66dd5559688f08bd98b6c976a0dea055d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/31/2018
ms.locfileid: "34456354"
---
# <a name="web-content-filter-settings-for-ios-devices"></a>Ustawienia filtru zawartości sieci Web dla urządzeń z systemem iOS

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W tym artykule opisano ustawienia usługi Microsoft Intune, które pozwalają sterować dostępem do adresów URL w przeglądarce na urządzeniach z systemem iOS.

Istnieją dwie metody konfigurowania adresów URL:

- **Konfiguruj adresy URL** — użyj wbudowanego filtru internetowego firmy Apple, który wyszukuje język dla dorosłych, czyli przekleństwa i słowa o charakterze seksualnym. Ta funkcja dokonuje oceny każdej strony sieci Web podczas jej ładowania i podejmuje próbę identyfikacji i zablokowania nieodpowiedniej zawartości. Możesz także skonfigurować adresy URL, które nie są sprawdzane przez filtr, lub adresy URL, które są blokowane niezależnie od ustawień filtru.

- **Tylko określone witryny sieci Web** (dotyczy wyłącznie przeglądarki Safari) — te adresy URL są dodawane do zakładek przeglądarki Safari. Użytkownik jest uprawniony **wyłącznie** do odwiedzania tych witryn sieci Web i nie ma możliwości dostępu do żadnych innych witryn. Użyj tej opcji tylko wtedy, gdy znasz dokładną listę adresów URL, do których użytkownicy mogą uzyskiwać dostęp.
Jeśli nie dodasz żadnych adresów URL, użytkownicy końcowi nie będą mogli uzyskać dostępu do żadnych witryn internetowych z wyjątkiem witryn microsoft.com, microsoft.net i apple.com.

## <a name="get-started"></a>Wprowadzenie

1. Na stronie Funkcje urządzenia wybierz pozycję **Filtr zawartości sieci Web (tylko w trybie nadzorowanym)**.
2. Na stronie **Filtr zawartości sieci Web** wybierz **Typ filtru**, który chcesz skonfigurować:
    - **Nieskonfigurowane** — filtrowanie nie ma miejsca.
    - **Konfiguruj adresy URL**
    - **Tylko określone witryny sieci Web**
3. Następnie, w zależności od typu używanego filtru, skorzystaj z jednej z poniższych procedur:


## <a name="configure-urls"></a>Konfiguruj adresy URL

1. Na stronie **Filtr zawartości sieci Web** wybierz zgodnie z potrzebami jedno z następujących ustawień:
   - **Dozwolone adresy URL** — na stronie **Dozwolone adresy URL** wprowadź kolejno adresy URL, których odwiedzanie ma być możliwe (z pominięciem filtru internetowego firmy Apple), naciskając klawisz Enter po każdym z nich.
     > [!NOTE]
     > Wybrane adresy URL to adresy, które nie mają być obiektem filtru internetowego firmy Apple. Te adresy URL nie reprezentują listy jednych dozwolonych witryn internetowych. Jeśli chcesz tak zrobić, użyj pozycji **Tylko określone witryny internetowe**.

   - **Zablokowane adresy URL** — na stronie **Zablokowane adresy URL** wprowadź kolejno adresy URL, dostęp do których ma zostać zablokowany (niezależnie od ustawień filtru internetowego firmy Apple), naciskając klawisz Enter po każdym z nich.
2. Po zakończeniu kliknij przycisk **OK**.


## <a name="specific-websites-only"></a>Tylko określone witryny sieci Web

1. W okienku **Filtr zawartości sieci Web** skonfiguruj następujące ustawienia dla każdej dozwolonej witryny internetowej:
    - **Adres URL** — wprowadź adres URL dozwolonej witryny internetowej, na przykład **http://www.contoso.com**.
    - **Ścieżka do zakładki** — wpisz ścieżkę do lokalizacji, w której chcesz przechowywać zakładkę, na przykład **/Contoso/Business Apps**. Jeśli nie dodasz ścieżki, zakładka zostanie dodana do domyślnego folderu zakładek na urządzeniu.
    - **Tytuł** — wprowadź opisowy tytuł zakładki.
2. Po wprowadzeniu niezbędnych informacji dla każdej z witryn sieci Web kliknij przycisk **Dodaj**.
3. Po zakończeniu kliknij przycisk **OK**.

> [!IMPORTANT]
> Poniższe adresy URL są automatycznie uznawane za dozwolone przez usługę Intune.
> - <www.microsoft.com>
> - <www.microsoft.net>
> - <www.apple.com>

## <a name="finish-up"></a>Zakończenie

Wybierz przycisk **OK**, aby powrócić do okienka **Utwórz profil**, a następnie wybierz pozycję **Utwórz**.

## <a name="next-steps"></a>Następne kroki

Teraz można przypisać profil urządzenia do wybranych grup. Aby uzyskać szczegółowe informacje, zobacz [Przypisywanie profilów urządzeń](device-profile-assign.md).
