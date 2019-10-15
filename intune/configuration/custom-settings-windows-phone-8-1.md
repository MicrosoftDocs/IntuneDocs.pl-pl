---
title: Dodawanie ustawień niestandardowych dla urządzeń z systemem Windows Phone 8.1 w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Dodaj lub utwórz profil niestandardowy w celu użycia ustawień identyfikatora URI OMA dla urządzeń z systemem Windows Phone 8.1 w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/25/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d6807caad60eb492324f37e0c406b44a4052589e
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71735015"
---
# <a name="use-custom-settings-for-windows-phone-81-devices-in-intune"></a>Używanie ustawień niestandardowych dla urządzeń z systemem Windows Phone 8.1 w usłudze Intune

Za pomocą usługi Microsoft Intune można dodawać lub tworzyć ustawienia niestandardowe dla urządzeń z systemem Windows Phone 8.1 przy użyciu „profili niestandardowych”. Profile niestandardowe to funkcja w usłudze Intune. Służą one do dodawania ustawień i funkcji urządzeń, które nie są wbudowane w usłudze Intune.

Profile niestandardowe systemu Windows Phone 8.1 używają ustawień jednolitego identyfikatora zasobów Open Mobile Alliance (OMA-URI, Open Mobile Alliance Uniform Resource Identifier) w celu skonfigurowania różnych funkcji. Te ustawienia są zwykle używane przez producentów urządzeń przenośnych w celu kontrolowania funkcji na urządzeniu. [Dokumentacja protokołu MDM w Windows Phone 8,1](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-phone/dn499787(v=technet.10)) zawiera listę ustawień.

W tym artykule pokazano, jak utworzyć profil niestandardowy dla urządzeń z systemem Windows Phone 8.1. 

## <a name="create-the-profile"></a>Tworzenie profilu

1. Zaloguj się do usługi [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Podaj następujące ustawienia:

    - **Nazwa**: wprowadź nazwę profilu, na przykład `windows phone custom profile`.
    - **Opis:** wprowadź opis profilu.
    - **Platforma**: wybierz system **Windows Phone 8.1**.
    - **Typ profilu**: wybierz pozycję **Niestandardowy**.

4. W obszarze **Niestandardowe ustawienia OMA-URI** wybierz pozycję **Dodaj**. Podaj następujące ustawienia:

    - **Nazwa**: wprowadź unikatową nazwę ustawienia OMA-URI, aby ułatwić jego identyfikację na liście ustawień.
    - **Opis**: wprowadź opis, który zawiera omówienie ustawienia oraz inne istotne informacje ułatwiające wyszukanie profilu.
    - **OMA-URI** (z uwzględnieniem wielkości liter): wprowadź identyfikator OMA-URI, którego chcesz użyć jako ustawienia.
    - **Typ danych**: wprowadź typ danych używany w przypadku tego ustawienia identyfikatora OMA-URI. Dostępne opcje:

        - String
        - Ciąg (plik XML)
        - Data i godzina
        - Integer
        - Liczba zmiennoprzecinkowa
        - Boolean
        - Base64 (plik)

    - **Wartość**: wprowadź wartość danych, którą chcesz skojarzyć z wprowadzonym identyfikatorem OMA-URI. Wartość zależy od wybranego typu danych. Jeśli na przykład wybrano opcję **Data i godzina**, wybierz wartość za pomocą selektora daty.

    Po dodaniu ustawień możesz wybrać pozycję **Eksportuj**. Wybranie pozycji **Eksportuj** spowoduje utworzenie listy wszystkich dodanych wartości w pliku wartości rozdzielanych przecinkami (CSV).

5. Wybierz przycisk **OK**, aby zapisać zmiany. W razie potrzeby kontynuuj dodawanie ustawień.
6. Po zakończeniu wybierz pozycję **OK** > **Utwórz**, aby utworzyć profil usługi Intune. Po utworzeniu profil będzie widoczny na liście **Konfiguracja urządzenia — profile**.

## <a name="example"></a>Przykład

W poniższym przykładzie Windows 8.1 urządzenia telefonii nie mogą zmieniać sieci komórkowych podczas podróży poza obszarem pokrycia operatora.

- **Nazwa**: Zezwalaj na roaming danych komórkowych
- **Opis**: Zezwalaj lub nie Zezwalaj na roaming danych komórkowych
- **OMA-URI** (z uwzględnieniem wielkości liter):./Vendor/MSFT/PolicyManager/my/Connectivity/AllowCellularDataRoaming
- **Typ danych**: liczba całkowita
- **Wartość**: 0

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. Teraz należy [przypisać profil](device-profile-assign.md).

Zobacz, jak utworzyć profil niestandardowy na [urządzeniach z systemem Windows 10](../custom-settings-windows-10.md).