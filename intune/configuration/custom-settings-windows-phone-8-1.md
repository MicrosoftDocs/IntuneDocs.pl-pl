---
title: Dodawanie ustawień niestandardowych dla urządzeń z systemem Windows Phone 8.1 w usłudze Microsoft Intune — Azure | Microsoft Docs
titleSuffix: ''
description: Dodaj lub utwórz profil niestandardowy w celu użycia ustawień identyfikatora URI OMA dla urządzeń z systemem Windows Phone 8.1 w usłudze Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/18/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6ed1f43e7c7e6f0580cb22513a489fb32c30e5f6
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206758"
---
# <a name="use-custom-settings-for-windows-phone-81-devices-in-intune"></a>Używanie ustawień niestandardowych dla urządzeń z systemem Windows Phone 8.1 w usłudze Intune

Za pomocą usługi Microsoft Intune można dodawać lub tworzyć ustawienia niestandardowe dla urządzeń z systemem Windows Phone 8.1 przy użyciu „profili niestandardowych”. Profile niestandardowe to funkcja w usłudze Intune. Służą one do dodawania ustawień i funkcji urządzeń, które nie są wbudowane w usłudze Intune.

Profile niestandardowe systemu Windows Phone 8.1 używają ustawień jednolitego identyfikatora zasobów Open Mobile Alliance (OMA-URI, Open Mobile Alliance Uniform Resource Identifier) w celu skonfigurowania różnych funkcji. Te ustawienia są zwykle używane przez producentów urządzeń przenośnych w celu kontrolowania funkcji na urządzeniu. [Dokumentacja protokołu MDM w Windows Phone 8,1](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-phone/dn499787(v=technet.10)) zawiera listę ustawień.

W tym artykule pokazano, jak utworzyć profil niestandardowy dla urządzeń z systemem Windows Phone 8.1. 

## <a name="create-the-profile"></a>Tworzenie profilu

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia** > **Profile konfiguracji** > **Utwórz profil**.
3. Podaj następujące ustawienia:

    - **Nazwa**: Wprowadź opisową nazwę profilu. Nadaj nazwę profilom, aby można było je później łatwo rozpoznać. Na przykład dobrą nazwą profilu jest **profilu niestandardowego systemu Windows Phone**.
    - **Opis**: Wprowadź opis ułatwiający identyfikację ustawienia oraz zawierający inne ważne szczegóły.
    - **platformy**: Wybierz **Windows Phone 8,1**.
    - **Typ profilu**: Wybierz **niestandardowe**.

4. W obszarze **Niestandardowe ustawienia OMA-URI** wybierz pozycję **Dodaj**. Podaj następujące ustawienia:

    - **Nazwa**: Wprowadź unikatową nazwę dla ustawienia OMA-URI, aby ułatwić jego identyfikację na liście ustawień.
    - **Opis**: Wprowadź opis, który zawiera omówienie ustawienia oraz inne istotne informacje ułatwiające wyszukanie profilu.
    - **OMA-URI** (rozróżniana jest wielkość liter): Wprowadź identyfikator OMA-URI, którego chcesz używać jako ustawienia.
    - **Typ danych**: Wybierz typ danych używany w przypadku tego ustawienia identyfikatora OMA-URI. Dostępne opcje:

        - String
        - Ciąg (plik XML)
        - Data i godzina
        - Integer
        - Liczba zmiennoprzecinkowa
        - Boolean
        - Base64 (plik)

    - **Wartość**: Wprowadź wartość danych, którą chcesz skojarzyć z wprowadzonym identyfikatorem OMA-URI. Wartość zależy od wybranego typu danych. Jeśli na przykład wybrano opcję **Data i godzina**, wybierz wartość za pomocą selektora daty.

    Po dodaniu ustawień możesz wybrać pozycję **Eksportuj**. Wybranie pozycji **Eksportuj** spowoduje utworzenie listy wszystkich dodanych wartości w pliku wartości rozdzielanych przecinkami (CSV).

5. Wybierz przycisk **OK**, aby zapisać zmiany. W razie potrzeby kontynuuj dodawanie ustawień.
6. Po zakończeniu wybierz pozycję **OK** > **Utwórz**, aby utworzyć profil usługi Intune. Po utworzeniu profil będzie widoczny na liście **Urządzenia — profile konfiguracji**.

## <a name="example"></a>Przykład

W poniższym przykładzie Windows 8.1 urządzenia telefonii nie mogą zmieniać sieci komórkowych podczas podróży poza obszarem pokrycia operatora.

- **Nazwa**: Zezwalaj na roaming danych komórkowych
- **Opis**: Zezwalaj lub nie Zezwalaj na roaming danych komórkowych
- **OMA-URI** (z uwzględnieniem wielkości liter):./Vendor/MSFT/PolicyManager/My/Connectivity/AllowCellularDataRoaming
- **Typ danych**: Integer
- **Wartość**: 0

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. W dalszej części [przypiszesz profil](../device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).

Utwórz [profil niestandardowy na urządzeniach z systemem Windows 10](../custom-settings-windows-10.md).
