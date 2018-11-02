---
title: Dodawanie ustawień niestandardowych do urządzeń z systemem Android w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodawanie lub tworzenie profilu niestandardowego dla urządzeń z systemem Android w celu utworzenia profilu sieci Wi-Fi z kluczem wstępnym, utworzenia profilu sieci VPN dla aplikacji lub zezwalania na użycie bądź blokowanie aplikacji dla urządzeń z system Samsung Knox Standard w usłudze Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f9e98575c92d403d51708f7403109bea2184176e
ms.sourcegitcommit: c969b596ec0fec227484c50f210ba4e159e2e533
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2018
ms.locfileid: "49983129"
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

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Podaj następujące ustawienia:

    - **Nazwa**: wprowadź nazwę profilu, na przykład `android custom profile`.
    - **Opis:** wprowadź opis profilu.
    - **Platforma**: wybierz system **Android**.
    - **Typ profilu**: wybierz pozycję **Niestandardowy**.

4. W obszarze **Niestandardowe ustawienia OMA-URI** wybierz pozycję **Dodaj**. Podaj następujące ustawienia:

    - **Nazwa**: wprowadź unikatową nazwę dla ustawienia identyfikatora OMA-URI, aby możne je było łatwo odnaleźć.
    - **Opis elementu**: wprowadź opis ułatwiający identyfikację ustawienia oraz zawierający inne ważne szczegóły.
    - **OMA-URI**: wprowadź identyfikator OMA-URI, którego chcesz używać jako ustawienia.
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

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. Teraz należy [przypisać profil](device-profile-assign.md).

Zobacz jak [utworzyć profil na urządzeniach z systemem Android Enterprise](custom-settings-android-for-work.md).
