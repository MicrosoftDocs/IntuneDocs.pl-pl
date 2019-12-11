---
title: Wyświetlanie profilów urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Wyświetlanie szczegółów profilu konfiguracji urządzenia w usłudze Microsoft Intune i zarządzanie nimi oraz wyświetlanie graficznego wykresu liczby urządzeń przypisanych do profilu i urządzeń z przypisanymi lub wdrożonymi profilami. Możesz też rozwiązywać problemy z profilami, które mają ustawienia powodujące konflikt.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9deaed87-fb4b-4689-ba88-067bc61686d7
ms.reviewer: karthib
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 85ba34cfec8ebe78d2574034967bd7ed76f3304e
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "74059546"
---
# <a name="monitor-device-profiles-in-microsoft-intune"></a>Monitorowanie profilów urządzeń w usłudze Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Usługa Intune oferuje funkcje, które ułatwiają monitorowanie profilów konfiguracji urządzenia i zarządzanie nimi. Można na przykład sprawdzić stan profilu, sprawdzić, które urządzenia zostały przypisane, a następnie zaktualizować właściwości profilu.

## <a name="view-existing-profiles"></a>Wyświetlanie istniejących profilów

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia** > **Profile konfiguracji**.

Zostanie wyświetlona lista wszystkich istniejących profilów ze szczegółami, takimi jak platforma i informacje o tym, czy profil został przypisany do urządzeń.

## <a name="view-details-on-a-profile"></a>Wyświetlanie szczegółów profilu

Po utworzeniu profilu urządzenia usługa Intune udostępnia wykresy graficzne. Te wykresy zawierają stan profilu, taki jak pomyślne przypisanie do urządzeń lub wyświetlanie konfliktu w tym profilu.

1. Wybierz istniejący profil. Na przykład wybierz profil systemu macOS.
2. Wybierz kartę **Omówienie**.

    Górny wykres graficzny przedstawia liczbę urządzeń przypisanych do profilu urządzenia. Na przykład jeśli profil urządzenia konfiguracji dotyczy urządzeń z systemem macOS, wykres zawiera liczbę urządzeń z systemem iOS.

    Zawiera on również liczbę urządzeń dla innych platform, które zostały przypisane do tego samego profilu urządzenia. Na przykład przedstawia liczbę urządzeń z systemem innym niż macOS.

    ![Wyświetlanie liczby urządzeń przypisanych do profilu urządzenia](./media/device-profile-monitor/device-configuration-profile-graphical-chart.png)

    Dolny wykres graficzny przedstawia liczbę użytkowników przypisanych do profilu urządzenia. Na przykład jeśli profil urządzenia konfiguracji dotyczy użytkowników systemu macOS, wykres zawiera liczbę użytkowników systemu iOS.

3. Wybierz okrąg na górnym wykresie graficznym. Zostanie otwarte okno **Stan urządzenia**.

    Zawiera ono listę urządzeń przypisanych do tego profilu oraz informację o tym, czy profil został pomyślnie wdrożony. Należy również zauważyć, że są wyświetlane tylko urządzenia dla określonej platformy (na przykład macOS).

    Zamknij okno **Stan urządzenia**.

4. Wybierz okrąg na dolnym wykresie graficznym. Zostanie otwarte okno **Stan użytkownika**. 

    Zawiera ono listę użytkowników przypisanych do tego profilu oraz informację o tym, czy profil został pomyślnie wdrożony. Należy również zauważyć, że są wyświetlani tylko użytkownicy określonej platformy (na przykład macOS).

    Zamknij okno **Stan użytkownika**.

5. Na liście **Profile** wybierz określony profil. Możesz również zmienić istniejące właściwości:
    - **Właściwości**: zmień nazwę lub zaktualizuj dowolne istniejące ustawienia.
    - **Przypisania**: dołącz lub wyklucz urządzenia, których mają dotyczyć zasady. Wybierz pozycję **Wybrane grupy**, aby wybrać określone grupy.
    - **Stan urządzenia**: Zawiera ono listę urządzeń przypisanych do tego profilu oraz informację o tym, czy profil został pomyślnie wdrożony. Można wybrać określone urządzenie, aby uzyskać więcej szczegółów, na przykład listę zainstalowanych aplikacji.
    - **Stan użytkownika**: Wyświetla listę nazw użytkowników z urządzeniami, na które wpływa ten profil, oraz informację o tym, czy profil został pomyślnie wdrożony. Można wybrać określonego użytkownika, aby uzyskać więcej szczegółów.
    - **Stan ustawień**: filtruje dane wyjściowe, pokazując poszczególne ustawienia w profilu i informację o tym, czy ustawienie zostało pomyślnie zastosowane.

## <a name="view-conflicts"></a>Wyświetl konflikty

W lokalizacji **Urządzenia**  >  **Wszystkie urządzenia** są wyświetlane wszelkie ustawienia powodujące konflikt. Gdy występuje konflikt, są także wyświetlane wszystkie profile konfiguracji, które zawierają to ustawienie. Administratorzy mogą używać tej funkcji, aby rozwiązywać problemy i naprawiać rozbieżności z profilami.

1. W usłudze Intune wybierz pozycję **Urządzenia**  >  **Wszystkie urządzenia**, a następnie wybierz istniejące urządzenie z listy. Użytkownik końcowy może pobrać nazwę urządzenia z aplikacji Portal firmy.
2. Wybierz pozycję **Konfiguracja urządzenia**. Zostaną wyświetlone wszystkie zasady konfiguracji dotyczące urządzenia.
3. Wybierz zasady. Są tutaj wyświetlane wszystkie ustawienia w zasadach dotyczące urządzenia. Jeśli urządzenie ma stan **Konflikt**, zaznacz ten wiersz. W nowym oknie zostaną wyświetlone wszystkie profile i nazwy profili, które mają ustawienie powodujące konflikt.

Znasz już ustawienie powodujące konflikt i zasady zawierające to ustawienie, co powinno ułatwić rozwiązanie konfliktu. 

## <a name="device-firmware-configuration-interface-profile-reporting"></a>Raporty dotyczące profilu Device Firmware Configuration Interface

> [!WARNING]
> Trwa tworzenie monitorowania profilów DFCI. Gdy profil DFCI jest w publicznej wersji zapoznawczej, dane monitorowania mogą być niedostępne lub niekompletne.

Profile DFCI są raportowane dla poszczególnych ustawień, podobnie jak w przypadku innych profilów konfiguracji urządzeń. Niektóre ustawienia mogą nie mieć zastosowania w zależności od obsługi interfejsu DFCI przez producenta.

Przy użyciu ustawień profilu DFCI można zobaczyć następujące stany:

- **Zgodne**: Ten stan pokazuje, kiedy wartość ustawienia w profilu pasuje do ustawienia na urządzeniu. Ten stan może wystąpić w następujących scenariuszach:

  - Profil DFCI pomyślnie skonfigurował ustawienia w profilu.
  - Urządzenie nie ma funkcji sprzętowej kontrolowanej przez ustawienie, a ustawienie profilu jest **wyłączone**.
  - Interfejs UEFI nie zezwala profilowi DFCI na wyłączenie funkcji, a ustawienie profilu jest **włączone**.
  - Urządzenie nie może wyłączyć tej funkcji ze względu na brak odpowiedniego sprzętu, a ustawienie profilu jest **włączone**.

- **Nie dotyczy**: Ten stan pokazuje, kiedy wartość ustawienia w profilu jest **włączona**, ale nie można znaleźć pasującego ustawienia na urządzeniu. Ten stan może wystąpić, jeśli sprzęt urządzenia nie ma tej funkcji.

- **Niezgodne**: Ten stan pokazuje, kiedy wartość ustawienia w profilu nie pasuje do ustawienia na urządzeniu. Ten stan może wystąpić w następujących scenariuszach:

  - Interfejs UEFI nie zezwala profilowi DFCI na wyłączenie ustawienia, a ustawienie profilu jest **wyłączone**.
  - Urządzenie nie może wyłączyć tej funkcji ze względu na brak odpowiedniego sprzętu, a ustawienie profilu jest **wyłączone**.
  - Urządzenie nie ma najnowszej wersji oprogramowania układowego DFCI.
  - Profil DFCI został wyłączony przed zarejestrowaniem w usłudze Intune przy użyciu lokalnej kontrolki „niezgody na uczestnictwo” w menu interfejsu UEFI.
  - Urządzenie zostało zarejestrowane w usłudze Intune poza rejestracją w rozwiązaniu Autopilot.
  - Urządzenie nie zostało zarejestrowane w rozwiązaniu Autopilot przez dostawcę CSP firmy Microsoft lub zostało zarejestrowane bezpośrednio przez producenta OEM.

## <a name="next-steps"></a>Następne kroki

[Typowe pytania, problemy i rozwiązania dotyczące profilów urządzeń](device-profile-troubleshoot.md)  
[Rozwiązywanie problemów związanych z zasadami i profilami w usłudze Intune](troubleshoot-policies-in-microsoft-intune.md)
