---
title: Dodawanie ustawień niestandardowych do urządzeń z systemem Android Enterprise w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodaj lub utwórz profil niestandardowy dla urządzeń z system Android Enterprise do tworzenia w usłudze Microsoft Intune
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
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1bd6e2d5ceebd23e87f464d15376594d1764c5b8
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206809"
---
# <a name="use-custom-settings-for-android-enterprise-devices-in-microsoft-intune"></a>Używanie ustawień niestandardowych dla urządzeń z systemem Android Enterprise w usłudze Microsoft Intune

Za pomocą usługi Microsoft Intune można dodawać lub tworzyć ustawienia niestandardowe dla urządzeń z profilem roboczym Android Enterprise przy użyciu „profilu niestandardowego”. Profile niestandardowe to funkcja w usłudze Intune. Służą one do dodawania ustawień i funkcji urządzeń, które nie są wbudowane w usłudze Intune.

Profile niestandardowe systemu Android Enterprise używają ustawień jednolitego identyfikatora zasobów Open Mobile Alliance (OMA-URI, Open Mobile Alliance Uniform Resource Identifier) w celu kontrolowania funkcji na urządzeniach z systemem Android Enterprise. Te ustawienia są zwykle używane przez producentów urządzeń przenośnych w celu kontrolowania tych funkcji.

Usługa Intune obsługuje następującą ograniczoną liczbę profilów niestandardowych przedsiębiorstwa z systemem Android:

- ./Vendor/MSFT/WiFi/Profile/SSID/Settings: [utworzyć profil sieci Wi-Fi z kluczem wstępnym](wi-fi-profile-shared-key.md) zawiera kilka przykładów.
- ./Vendor/MSFT/VPN/Profile/Name/PackageList: [tworzenia profilu sieci VPN dla aplikacji](android-pulse-secure-per-app-vpn.md) zawiera kilka przykładów.
- ./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste: Zobacz [przykład](#example) w tym artykule. To ustawienie jest również dostępne w interfejsie użytkownika. Więcej informacji — zobacz [Ustawienia urządzeń z systemem Android Enterprise w celu zezwolenia na funkcje lub ich ograniczenia przy użyciu usługi Intune](device-restrictions-android-for-work.md).

Jeśli potrzebujesz dodatkowych ustawień, zobacz [OEMConfig for Android Enterprise](android-oem-configuration-overview.md).

W tym artykule pokazano, jak utworzyć profil niestandardowy dla urządzeń z systemem Android Enterprise. Zawiera także przykład profilu niestandardowego, który blokuje kopiowanie i wklejanie.

## <a name="create-the-profile"></a>Tworzenie profilu

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia** > **Profile konfiguracji** > **Utwórz profil**.
3. Podaj następujące ustawienia:

    - **Nazwa**: Wprowadź opisową nazwę profilu. Nadaj nazwę profilom, aby można było je później łatwo rozpoznać. Na przykład dobrą nazwą profilu jest niestandardowego **profilu systemu Android w wersji Enterprise**.
    - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: Wybierz pozycję **Android Enterprise**.
    - **Typ profilu**: Wybierz **niestandardowe**.

4. W obszarze **Niestandardowe ustawienia OMA-URI** wybierz pozycję **Dodaj**. Podaj następujące ustawienia:

    - **Nazwa**: Wprowadź unikatową nazwę dla ustawienia identyfikatora OMA-URI, aby możne je było łatwo odnaleźć.
    - **Opis**: Wprowadź opis ułatwiający identyfikację ustawienia oraz zawierający inne ważne szczegóły.
    - **OMA-URI**: Wprowadź identyfikator OMA-URI, którego chcesz używać jako ustawienia.
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

W tym przykładzie utworzysz profil niestandardowy, który ogranicza możliwość wykonywania akcji kopiowania i wklejania między aplikacjami służbowymi i osobistymi na urządzeniach z systemem Android Enterprise.

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia** > **Profile konfiguracji** > **Utwórz profil**.
3. Podaj następujące ustawienia:

    - **Nazwa**: Wprowadź opisową nazwę profilu. Nadaj nazwę profilom, aby można było je później łatwo rozpoznać. Na przykład wprowadź **w systemie Android w bloku wklej opcję Kopiuj profil niestandardowy**.
    - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: Wybierz pozycję **Android Enterprise**.
    - **Typ profilu**: Wybierz **niestandardowe**.

4. W obszarze **Niestandardowe ustawienia OMA-URI** wybierz pozycję **Dodaj**. Podaj następujące ustawienia:

    - **Nazwa**: Wprowadź na przykład nazwę `Block copy and paste`.
    - **Opis**: Wprowadź na przykład nazwę `Blocks copy/paste between work and personal apps`.
    - **OMA-URI**: Wprowadź `./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste`.
    - **Typ danych**: Wybierz **wartość logiczną**, aby wartość identyfikatora OMA-URI była równa **True** lub **False**.
    - **Wartość**: Wybierz wartość **True**.

5. Po wprowadzeniu ustawień środowisko powinno wyglądać podobnie do przedstawionego na poniższym obrazie:

    ![Blokowanie kopiowania i wklejania dla profilu służbowego systemu Android.](./media/custom-settings-android-for-work/custom-policy-afw-copy-paste.png)

Po przypisaniu tego profilu do zarządzanych urządzeń z systemem Android Enterprise kopiowanie i wklejanie danych między aplikacjami z profilu służbowego i osobistego będzie zablokowane.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. W dalszej części [przypiszesz profil](../device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).

Utwórz profil niestandardowy [na urządzeniach z systemem Android](../custom-settings-android.md).
