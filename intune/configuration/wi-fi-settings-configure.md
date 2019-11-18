---
title: Tworzenie profilu sieci Wi-Fi dla urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z krokami tworzenia profilu konfiguracji urządzeń sieci Wi-Fi w usłudze Microsoft Intune. Twórz profile dla systemu Android, systemu Android dla firm, kiosku systemu Android, systemów iOS, macOS i Windows 10 i nowszych oraz platformy Windows Holographic for Business. Te profile umożliwiają tworzenie połączenia sieci Wi-Fi na potrzeby korzystania z certyfikatów, wybierania typu protokołu EAP i metody uwierzytelniania, włączania serwer proxy i wykonywania innych czynności.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: tycast
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 589fc32db22de02f70ba78f79ebb413a31e92f1d
ms.sourcegitcommit: 1a7f04c80548e035be82308d2618492f6542d3c0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/07/2019
ms.locfileid: "73754863"
---
# <a name="add-and-use-wi-fi-settings-on-your-devices-in-microsoft-intune"></a>Dodawanie i używanie ustawień sieci Wi-Fi dla urządzeń w usłudze Microsoft Intune

Sieć Wi-Fi to sieć bezprzewodowa, która jest używana przez wiele urządzeń przenośnych w celu uzyskania dostępu do sieci. Usługa Microsoft Intune obejmuje wbudowane ustawienia sieci Wi-Fi, które można wdrażać do użytkowników i urządzeń w organizacji. Ta grupa ustawień jest nazywana „profilem” i można ją przypisywać do różnych użytkowników i grup. Po przypisaniu użytkownicy uzyskują dostęp do sieci Wi-Fi organizacji bez konieczności samodzielnego konfigurowania.

Załóżmy, że instalujesz nową sieć Wi-Fi o nazwie Sieć Wi-Fi firmy Contoso. Następnie chcesz skonfigurować wszystkie urządzenia z systemem iOS tak, aby łączyły się z tą siecią. Oto proces:

1. Utwórz profil sieci Wi-Fi zawierający ustawienia potrzebne do łączenia się z siecią bezprzewodową Sieć Wi-Fi firmy Contoso.
2. Przypisz profil do grupy uwzględniającej wszystkich użytkowników urządzeń z systemem iOS.
3. Użytkownicy znajdują nową sieć Wi-Fi firmy Contoso na liście sieci bezprzewodowych w urządzeniu. Mogą następnie połączyć się z siecią przy użyciu wybranej metody uwierzytelniania.

W tym artykule znajduje się lista czynności wymaganych do utworzenia profilu sieci Wi-Fi. Zawiera on również linki, które opisują różne ustawienia poszczególnych platform.

## <a name="supported-device-platforms"></a>Obsługiwane platformy urządzeń

Profile sieci Wi-Fi obsługują następujące platformy urządzeń:

- System Android 4 lub nowszy
- System Android dla firm i kiosk systemu Android
- System iOS 8.0 i nowsze
- System macOS X 10.11 i nowsze
- System Windows 10 lub nowsze, system Windows 10 Mobile i platforma Windows Holographic for Business

> [!NOTE]
> Na urządzeniach z systemem Windows 8.1 można zaimportować konfigurację sieci Wi-Fi, która została wcześniej wyeksportowana z innego urządzenia.

## <a name="create-a-device-profile"></a>Tworzenie profilu urządzenia

1. Zaloguj się do [centrum administracyjnego programu Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Wybierz pozycję **Urządzenia** > **Profile konfiguracji** > **Utwórz profil**.
3. Wprowadź następujące właściwości:

    - **Nazwa**: Wprowadź opisową nazwę profilu. Nadaj nazwę profilom, aby można było je później łatwo rozpoznać. Na przykład dobra nazwa profilu to **Profil sieci Wi-Fi dla całej firmy**.
    - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: Wybierz platformę urządzeń. Dostępne opcje:

      - **Android**
      - **Android Enterprise**
      - **iOS/iPadOS**
      - **macOS**
      - **Windows 8.1 lub nowszy**
      - **Windows 10 lub nowszy**

    - **Typ profilu**: Wybierz pozycję **Sieć Wi-Fi**.

      > [!TIP]
      >
      > - W przypadku urządzeń z systemem **Android Enterprise** działających jako urządzenie dedykowanie (kiosk) można kolejno wybrać pozycje **Tylko właściciel urządzenia** > **Sieć Wi-Fi**.
      > - W przypadku **systemu Windows 8.1 i nowszych** można wybrać pozycję **Importowanie sieci Wi-Fi**. Ta opcja pozwala zaimportować ustawienia sieci Wi-Fi jako plik XML wyeksportowany wcześniej z innego urządzenia.

4. Niektóre ustawienia sieci Wi-Fi są inne dla każdej platformy. Aby wyświetlić ustawienia dla określonej platformy, wybierz platformę:

    - [Android](wi-fi-settings-android.md)
    - [Android Enterprise](wi-fi-settings-android-enterprise.md), w tym urządzenia dedykowane
    - [iOS/iPadOS](wi-fi-settings-ios.md)
    - [macOS](wi-fi-settings-macos.md)
    - [Windows 10 lub nowszy](wi-fi-settings-windows.md)
    - [Windows 8.1 lub nowszy](wi-fi-settings-import-windows-8-1.md), w tym platforma Windows Holographic for Business

5. Gdy wszystko będzie gotowe, wybierz pozycję **Utwórz profil** > **Utwórz**.

Profil zostanie utworzony i wyświetlony na liście profilów (**Konfiguracja urządzenia** > **Profile**).

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje żadnych czynności. Następnie [przypiszesz ten profil](device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).
