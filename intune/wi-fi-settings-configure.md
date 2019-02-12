---
title: Tworzenie profilu sieci Wi-Fi dla urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zapoznaj się z krokami tworzenia profilu konfiguracji urządzeń sieci Wi-Fi w usłudze Microsoft Intune. Twórz profile dla systemu Android, systemu Android dla firm, kiosku systemu Android, systemów iOS, macOS i Windows 10 i nowszych oraz platformy Windows Holographic for Business. Te profile umożliwiają tworzenie połączenia sieci Wi-Fi na potrzeby korzystania z certyfikatów, wybierania typu protokołu EAP i metody uwierzytelniania, włączania serwer proxy i wykonywania innych czynności.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/16/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c780f68d3c332cec899250ea4a0ee85745247b37
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55842443"
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
- macOS (Mac OS X 10.11 lub nowszy)
- System Windows 10 lub nowsze, system Windows 10 Mobile i platforma Windows Holographic for Business

> [!NOTE]
> Na urządzeniach z systemem Windows 8.1 można zaimportować konfigurację sieci Wi-Fi, która została wcześniej wyeksportowana z innego urządzenia.

## <a name="create-a-device-profile"></a>Tworzenie profilu urządzenia

1. W witrynie [Azure Portal](https://portal.azure.com) wybierz pozycję **Wszystkie usługi** > wpisz nazwę usługi **Intune** w filtrze, a następnie wybierz pozycję **Microsoft Intune**. 
2. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
3. Wprowadź **nazwę** i **opis** profilu sieci Wi-Fi.
4. Z listy rozwijanej **Platforma** wybierz platformę urządzenia, do której mają zostać zastosowane ustawienia sieci Wi-Fi. Dostępne opcje:

    - **Android**
    - **Android enterprise**
    - **iOS**
    - **macOS**
    - **Windows 8.1 lub nowszy**
    - **Windows 10 lub nowszy**

5. W polu **Typ profilu** wybierz pozycję **Sieć Wi-Fi**.

    - W przypadku urządzeń z **systemem Android dla firm** działających jako kiosk można kolejno wybrać pozycje **Tylko właściciel urządzenia** > **Sieć Wi-Fi**.
    - W przypadku **systemu Windows 8.1 i nowszych** można wybrać pozycję **Importowanie sieci Wi-Fi**. Ta opcja pozwala zaimportować ustawienia sieci Wi-Fi jako plik XML wyeksportowany wcześniej z innego urządzenia.

6. Niektóre ustawienia sieci Wi-Fi są inne dla każdej platformy. Aby wyświetlić ustawienia dla określonej platformy, wybierz pozycję:

    - [Android](wi-fi-settings-android.md)
    - [System Android dla firm i kiosk systemu Android](wi-fi-settings-android-enterprise.md)
    - [iOS](wi-fi-settings-ios.md)
    - [macOS](wi-fi-settings-macos.md)
    - [Windows 10 lub nowszy](wi-fi-settings-windows.md)
    - [Windows 8.1 lub nowszy](wi-fi-settings-import-windows-8-1.md), w tym platforma Windows Holographic for Business

    Większość platform ma ustawienia typu **Podstawowe** i **Przedsiębiorstwo**. Opcja **Podstawowe** udostępnia funkcje, takie jak nazwa sieci i identyfikator SSID. Opcja **Przedsiębiorstwo** umożliwia podawanie bardziej zaawansowanych informacji, takich jak protokół uwierzytelniania rozszerzonego (EAP).

7. Po zakończeniu dodawania ustawień sieci Wi-Fi wybierz pozycję **Utwórz profil** > **Utwórz**, aby dodać profil konfiguracji. Profil zostanie utworzony i wyświetlony na liście profilów (**Konfiguracja urządzenia** > **Profile**).

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje żadnych czynności. Następnie [przypiszesz ten profil](device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).
