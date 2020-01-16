---
title: Dodawanie ustawień niestandardowych do urządzeń z systemem Android w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodawanie lub tworzenie profilu niestandardowego dla urządzeń z systemem Android w celu utworzenia profilu sieci Wi-Fi z kluczem wstępnym, utworzenia profilu sieci VPN dla aplikacji lub zezwalania na użycie bądź blokowanie aplikacji dla urządzeń z system Samsung Knox Standard w usłudze Microsoft Intune
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
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8137a806598facd540781702b1c2c359e89d6bda
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206792"
---
# <a name="use-custom-settings-for-android-devices-in-microsoft-intune"></a>Używanie ustawień niestandardowych dla urządzeń z systemem Android w usłudze Microsoft Intune

Za pomocą usługi Microsoft Intune można dodawać lub tworzyć ustawienia niestandardowe dla urządzeń z systemem Android przy użyciu „profilu niestandardowego”. Profile niestandardowe to funkcja w usłudze Intune. Służą one do dodawania ustawień i funkcji urządzeń, które nie są wbudowane w usłudze Intune.

W przypadku profilów niestandardowych systemu Android używane są ustawienia jednolitego identyfikatora zasobów Open Mobile Alliance (OMA-URI, Open Mobile Alliance Uniform Resource Identifier) w celu skonfigurowania różnych funkcji na urządzeniach z systemem Android. Te ustawienia są zwykle używane przez producentów urządzeń przenośnych w celu kontrolowania tych funkcji.

Używając profilu niestandardowego, możesz skonfigurować lub przypisać następujące ustawienia systemu Android. Następujące ustawienia nie są wbudowane w usłudze Intune:

- [Tworzenie profilu sieci Wi-Fi z użyciem klucza wstępnego](/intune/wi-fi-profile-shared-key)
- [Tworzenie profilu sieci VPN dla aplikacji](/intune/android-pulse-secure-per-app-vpn)
- [Zezwalanie na użycie i blokowanie aplikacji na urządzeniach z systemem Samsung Knox Standard](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
> Za pomocą profilu niestandardowego można skonfigurować tylko wymienione ustawienia. Urządzenia z systemem Android nie ujawniają pełnej listy ustawień identyfikatora OMA-URI, które można skonfigurować. Jeśli chcesz widzieć więcej ustawień, zagłosuj na więcej ustawień na [witrynie Intune Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas).

W tym artykule pokazano, jak utworzyć profil niestandardowy dla urządzeń z systemem Android.

## <a name="create-the-profile"></a>Tworzenie profilu

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia** > **Profile konfiguracji** > **Utwórz profil**.
3. Podaj następujące ustawienia:

    - **Nazwa**: Wprowadź opisową nazwę profilu. Nadaj nazwę profilom, aby można było je później łatwo rozpoznać. Na przykład dobrą nazwą profilu jest niestandardowego **profilu systemu Android**.
    - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: — wybierz opcję **Android**.
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

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. W dalszej części [przypiszesz profil](../device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).

Utwórz profil niestandardowy [na urządzeniach z systemem Android Enterprise](custom-settings-android-for-work.md).
