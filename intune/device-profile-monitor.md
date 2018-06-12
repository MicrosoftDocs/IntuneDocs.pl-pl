---
title: Wyświetlanie profilów urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Wyświetlanie szczegółów profilu konfiguracji urządzenia w usłudze Microsoft Intune i zarządzanie nimi oraz wyświetlanie graficznego wykresu liczby urządzeń przypisanych do profilu i urządzeń z przypisanymi lub wdrożonymi profilami.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9deaed87-fb4b-4689-ba88-067bc61686d7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bffb6832200379fca0221d8718afdebe06163980
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34744792"
---
# <a name="monitor-device-profiles-in-microsoft-intune"></a>Monitorowanie profilów urządzeń w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Usługa Intune w witrynie Azure Portal oferuje funkcje, które ułatwiają monitorowanie profilów konfiguracji urządzenia i zarządzanie nimi. Można na przykład sprawdzić stan profilu, sprawdzić, które urządzenia zostały przypisane, a następnie zaktualizować właściwości profilu.

## <a name="view-existing-profiles"></a>Wyświetlanie istniejących profilów

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Konfiguracja urządzeń** > **Profile**.

Zostanie wyświetlona lista wszystkich istniejących profilów ze szczegółami, takimi jak platforma i informacje o tym, czy profil został przypisany do urządzeń.

## <a name="view-details-on-a-profile"></a>Wyświetlanie szczegółów profilu

Po utworzeniu profilu urządzenia usługa Intune udostępnia wykresy graficzne. Te wykresy zawierają stan profilu, taki jak pomyślne przypisanie do urządzeń lub wyświetlanie konfliktu w tym profilu.

1. Wybierz istniejący profil. Na przykład wybierz profil systemu macOS.
2. Wybierz kartę **Omówienie**.

    Górny wykres graficzny przedstawia liczbę urządzeń przypisanych do określonego profilu urządzenia. Na przykład jeśli profil urządzenia konfiguracji dotyczy urządzeń z systemem macOS, wykres zawiera liczbę urządzeń z systemem iOS.

    Zawiera on również liczbę urządzeń dla innych platform, które zostały przypisane do tego samego profilu urządzenia. Na przykład przedstawia liczbę urządzeń z systemem innym niż macOS.

    ![Wyświetlanie liczby urządzeń przypisanych do profilu urządzenia](./media/device-configuration-profile-graphical-chart.png)

    Dolny wykres graficzny przedstawia liczbę użytkowników przypisanych do określonego profilu urządzenia. Na przykład jeśli profil urządzenia konfiguracji dotyczy użytkowników systemu macOS, wykres zawiera liczbę użytkowników systemu iOS.

3. Wybierz okrąg na górnym wykresie graficznym. Zostanie otwarte okno **Stan urządzenia**.

    Zawiera ono listę urządzeń przypisanych do tego profilu oraz informację o tym, czy profil został pomyślnie wdrożony. Należy również zauważyć, że są wyświetlane tylko urządzenia dla określonej platformy (na przykład macOS).

    Zamknij okno **Stan urządzenia**.

4. Wybierz okrąg na dolnym wykresie graficznym. Zostanie otwarte okno **Stan użytkownika**. 

    Zawiera ono listę użytkowników przypisanych do tego profilu oraz informację o tym, czy profil został pomyślnie wdrożony. Należy również zauważyć, że są wyświetlani tylko użytkownicy określonej platformy (na przykład macOS).

    Zamknij okno **Stan użytkownika**.

5. Na liście **Profile** wybierz określony profil. Możesz również zmienić istniejące właściwości:
  - **Właściwości**: zmień nazwę lub zaktualizuj dowolne istniejące ustawienia.
  - **Przypisania**: dołącz lub wyklucz urządzenia, których mają dotyczyć zasady. Wybierz pozycję **Wybrane grupy**, aby wybrać określone grupy.
  - **Stan urządzenia**: lista urządzeń przypisanych do tego profilu oraz informacja o tym, czy profil został pomyślnie wdrożony. Można wybrać określone urządzenie, aby uzyskać więcej szczegółów, na przykład listę zainstalowanych aplikacji.
  - **Stan użytkownika**: wyświetla listę nazw użytkowników z urządzeniami, które wpływa ten profil, oraz informację o tym, czy profil został pomyślnie wdrożony. Można wybrać określonego użytkownika, aby uzyskać więcej szczegółów.
  - **Stan ustawień**: filtruje dane wyjściowe, pokazując poszczególne ustawienia w profilu i informację o tym, czy ustawienie zostało pomyślnie zastosowane.

## <a name="next-steps"></a>Następne kroki
[Przypisywanie profilów użytkowników i urządzeń](device-profile-assign.md)  
[Typowe problemy dotyczące profilów urządzeń i sposoby ich rozwiązania](device-profile-troubleshoot.md)