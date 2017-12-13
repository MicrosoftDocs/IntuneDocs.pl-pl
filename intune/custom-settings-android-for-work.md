---
title: "Niestandardowe ustawienia profilu dla programu Android for Work z użyciem usługi Intune"
titlesuffix: Azure portal
description: "Informacje na temat tworzenia niestandardowych ustawień profilu dla urządzeń z programem Android for Work z użyciem usługi Intune."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f12d71b9477e3072b7952d3f9331ed0cefc33ac7
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/12/2017
---
# <a name="create-intune-custom-profile-settings-for-android-for-work-devices"></a>Tworzenie niestandardowych ustawień profilu dla urządzeń z programem Android for Work z użyciem usługi Intune

Niestandardowe zasady konfiguracji programu Android for Work w usłudze Intune umożliwiają przypisanie ustawień OMA-URI, których można użyć do sterowania funkcjami na urządzeniach z programem Android for Work. Są to ustawienia standardowe używane przez wielu producentów urządzeń przenośnych do sterowania funkcjami urządzeń.

Ta funkcja ma umożliwić przypisanie ustawień systemu Android, których nie można skonfigurować przy użyciu zasad usługi Intune. Obecnie usługa Intune obsługuje tylko ograniczoną liczbę zasad niestandardowych systemu Android. Zobacz przykłady w tym temacie, aby dowiedzieć się, które zasady możesz skonfigurować.

## <a name="create-a-custom-profile"></a>Tworzenie profilu niestandardowego

1. Aby rozpocząć pracę, postępuj zgodnie z instrukcjami w artykule [Jak skonfigurować niestandardowe ustawienia urządzenia](custom-settings-configure.md).
2. W bloku **Niestandardowe ustawienia OMA-URI** kliknij przycisk **Dodaj**, aby dodać nowe ustawienie.
3. W bloku **Dodaj wiersz** skonfiguruj następujące opcje:
    - **Nazwa** — wprowadź unikatową nazwę niestandardowych ustawień programu Android for Work, która pomoże je zidentyfikować w witrynie Azure Portal.
    - **Opis** — podaj opis zawierający omówienie zasad niestandardowych systemu Android oraz inne istotne informacje ułatwiające ich wyszukanie.
    - **OMA-URI** — wprowadź identyfikator OMA-URI, dla którego chcesz podać ustawienie.
    - **Typ danych** — wybierz typ danych, przy pomocy których określisz to ustawienie OMA-URI. Wybierz jedną z opcji: **Ciąg**, **Ciąg (plik XML)**, **Data i godzina**, **Liczba całkowita**, **Liczba zmiennoprzecinkowa**, **Wartość logiczna** lub **Base64 (plik)**.
    - **Wartość** — określ wartość, która będzie skojarzona z określonym wcześniej identyfikatorem OMA-URI. Metoda wprowadzania tej wartości będzie się różnić w zależności od wybranego typu danych. Na przykład, jeśli została wybrana opcja **Data i godzina**, wartość należy wybrać z użyciem selektora daty.
4. Po zakończeniu wybierz przycisk OK, aby powrócić do bloku **Niestandardowe ustawienia OMA-URI**, a następnie dodaj więcej ustawień, lub wybierz pozycję **Utwórz**, aby utworzyć profil niestandardowy.


## <a name="example"></a>Przykład

W tym przykładzie zostanie utworzony profil niestandardowy, którego można użyć w celu ograniczenia możliwości wykonywania akcji kopiowania i wklejania danych między aplikacjami służbowymi i osobistymi na zarządzanych urządzeniach z programem Android for Work.

1. Procedura opisana w tym temacie pozwala utworzyć dla urządzeń z programem Android for Work profil niestandardowy przy użyciu następujących wartości:
    - **Nazwa** — wprowadź nazwę „Blokowanie kopiowania i wklejania” lub dowolną inną nazwę.
    - **Opis** — wpisz opis o treści „Blokuje kopiowanie/wklejanie danych między aplikacjami służbowymi i osobistymi” lub dowolny inny opis.
    - **OMA-URI** — wpisz wartość **./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste**.
    - **Typ danych** — wybierz opcję **Wartość logiczna**, aby wskazać, że OMA-URI ma wartość **Prawda** lub **Fałsz**.
    - **Wartość** — wybierz wartość **Prawda**.
2. Po wykonaniu tych czynności uzyskasz ustawienie podobne do przedstawionego na zrzucie ekranu.
![Blokowanie kopiowania i wklejania dla programu Android for Work.](./media/custom-policy-afw-copy-paste.png)
3. Po przypisaniu profilu niestandardowego do zarządzanych urządzeń z programem Android for Work kopiowanie i wklejanie danych pomiędzy aplikacjami z profilu służbowego i osobistego zostanie zablokowane.