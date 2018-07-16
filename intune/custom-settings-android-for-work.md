---
title: Niestandardowe ustawienia profilu dla profili służbowych systemu Android z użyciem usługi Intune
titlesuffix: Microsoft Intune
description: Informacje na temat tworzenia niestandardowych ustawień profilu dla urządzeń z profilami służbowymi systemu Android z użyciem usługi Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/12/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 109c50acf194598017aa507a0979ad3b9298de9e
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905295"
---
# <a name="create-intune-custom-profile-settings-for-android-work-profile-devices"></a>Tworzenie niestandardowych ustawień profilu dla urządzeń z profilami służbowymi systemu Android z użyciem usługi Intune

Niestandardowe zasady konfiguracji profilu służbowego systemu Android w usłudze Intune umożliwiają przypisanie ustawień OMA-URI, których można użyć do sterowania funkcjami w urządzeniach z profilami służbowymi systemu Android. Są to ustawienia standardowe używane przez wielu producentów urządzeń przenośnych do sterowania funkcjami urządzeń.

Ta funkcja ma umożliwić przypisanie ustawień systemu Android, których nie można skonfigurować przy użyciu zasad usługi Intune. Obecnie usługa Intune obsługuje tylko ograniczoną liczbę zasad niestandardowych systemu Android. Zobacz przykłady w tym artykule, aby dowiedzieć się, które zasady możesz skonfigurować.

## <a name="create-a-custom-profile"></a>Tworzenie profilu niestandardowego

1. Aby rozpocząć pracę, postępuj zgodnie z instrukcjami w artykule [Jak skonfigurować niestandardowe ustawienia urządzenia](custom-settings-configure.md). Dla ustawienia **Platforma** wybierz pozycję **Android enterprise**, a dla ustawienia **Typ profilu** wybierz pozycję **Niestandardowy**.
2. W bloku **Niestandardowe ustawienia OMA-URI** kliknij przycisk **Dodaj**, aby dodać nowe ustawienie.
3. W bloku **Dodaj wiersz** skonfiguruj następujące opcje:
    - **Nazwa** — wprowadź unikatową nazwę niestandardowych ustawień profilu służbowego systemu Android, która pomoże je zidentyfikować w witrynie Azure Portal.
    - **Opis** — podaj opis zawierający omówienie zasad niestandardowych systemu Android oraz inne istotne informacje ułatwiające ich wyszukanie.
    - **OMA-URI** — wprowadź identyfikator OMA-URI, dla którego chcesz podać ustawienie.
    - **Typ danych** — wybierz typ danych, przy pomocy których określisz to ustawienie OMA-URI. Wybierz jedną z opcji: **Ciąg**, **Ciąg (plik XML)**, **Data i godzina**, **Liczba całkowita**, **Liczba zmiennoprzecinkowa**, **Wartość logiczna** lub **Base64 (plik)**.
    - **Wartość** — określ wartość, która będzie skojarzona z określonym wcześniej identyfikatorem OMA-URI. Metoda wprowadzania tej wartości będzie się różnić w zależności od wybranego typu danych. Na przykład, jeśli została wybrana opcja **Data i godzina**, wartość należy wybrać z użyciem selektora daty.
4. Po zakończeniu wybierz przycisk OK, aby powrócić do bloku **Niestandardowe ustawienia OMA-URI**, a następnie dodaj więcej ustawień, lub wybierz pozycję **Utwórz**, aby utworzyć profil niestandardowy.


## <a name="example"></a>Przykład

W tym przykładzie zostanie utworzony profil niestandardowy, którego można użyć w celu ograniczenia możliwości wykonywania akcji kopiowania i wklejania danych między aplikacjami służbowymi i osobistymi w urządzeniach z profilami służbowymi systemu Android.

1. Procedura opisana w tym artykule pozwala utworzyć dla urządzeń z profilami służbowymi systemu Android profil niestandardowy przy użyciu następujących wartości:
    - **Nazwa** — wprowadź nazwę „Blokowanie kopiowania i wklejania” lub dowolną inną nazwę.
    - **Opis** — wpisz opis o treści „Blokuje kopiowanie/wklejanie danych między aplikacjami służbowymi i osobistymi” lub dowolny inny opis.
    - **OMA-URI** — wpisz wartość **./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste**.
    - **Typ danych** — wybierz opcję **Wartość logiczna**, aby wskazać, że OMA-URI ma wartość **Prawda** lub **Fałsz**.
    - **Wartość** — wybierz wartość **Prawda**.
2. Po wykonaniu tych czynności uzyskasz ustawienie podobne do przedstawionego na zrzucie ekranu.
![Blokowanie kopiowania i wklejania dla profilu służbowego systemu Android.](./media/custom-policy-afw-copy-paste.png)
3. Po przypisaniu profilu niestandardowego do zarządzanych urządzeń z profilami służbowymi systemu Android kopiowanie i wklejanie danych między aplikacjami z profilu służbowego i osobistego zostanie zablokowane.