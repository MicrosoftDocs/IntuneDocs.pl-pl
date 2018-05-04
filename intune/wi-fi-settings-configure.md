---
title: Jak skonfigurować ustawienia sieci Wi-Fi w usłudze Intune
titleSuffix: Microsoft Intune
description: Informacje dotyczące konfigurowania ustawień sieci Wi-Fi na zarządzanych urządzeniach przy użyciu usługi Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fb4d9fc6f0f0609062c408fd85921c1f86bd7303
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-configure-wi-fi-settings-in-microsoft-intune"></a>Jak skonfigurować ustawienia sieci Wi-Fi w usłudze Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Aby przypisać ustawienia sieci bezprzewodowej dla użytkowników i urządzeń w Twojej organizacji, użyj profili sieci Wi-Fi usługi Microsoft Intune. W przypadku przypisania profilu sieci Wi-Fi użytkownicy mają dostęp do firmowej sieci Wi-Fi bez konieczności samodzielnego konfigurowania połączenia.

Załóżmy, że zainstalowano nową sieć Wi-Fi o nazwie Sieć Wi-Fi firmy Contoso i że chcesz skonfigurować wszystkie urządzenia z systemem iOS do łączenia się z tą siecią. Oto proces:

1. Utwórz profil sieci Wi-Fi zawierający ustawienia wymagane do łączenia się z siecią bezprzewodową Sieć Wi-Fi firmy Contoso.
2. Przypisz profil do grupy obejmującej wszystkich użytkowników urządzeń z systemem iOS.
3. Użytkownicy znajdują nową sieć Wi-Fi firmy Contoso na liście sieci bezprzewodowych w urządzeniu i mogą się łatwo z nią łączyć.

## <a name="supported-device-platforms"></a>Obsługiwane platformy urządzeń

Profile sieci Wi-Fi obsługują następujące platformy urządzeń:

- System Android 4 lub nowszy
- Program Android for Work
- System iOS 8.0 i nowsze
- macOS (Mac OS X 10.11 lub nowszy)

Na urządzeniach z systemem Windows 8.1, Windows 10, Windows 10 Mobile lub Windows Holographic for Business możesz zaimportować konfigurację sieci Wi-Fi, która została wcześniej wyeksportowana z innego urządzenia.

Skorzystaj z informacji zawartych w tym temacie, aby uzyskać podstawową wiedzę z zakresu konfigurowania profilów sieci Wi-Fi, a następnie zapoznaj się z tematami dotyczącymi poszczególnych platform, aby dowiedzieć się więcej o charakterystyce urządzeń.

## <a name="create-a-device-profile-containing-wi-fi-settings"></a>Tworzenie profilu urządzenia zawierającego ustawienia sieci Wi-Fi

1. Zaloguj się do portalu [Azure Portal](https://portal.azure.com).
2. Wybierz pozycje **Wszystkie usługi** > **Intune**. Usługa Intune znajduje się w sekcji **Monitorowanie i zarządzanie**.
3. W okienku **Intune** wybierz pozycję **Konfiguracja urządzeń**.
2. W okienku **Konfiguracja urządzeń** w sekcji **Zarządzanie** wybierz pozycję **Profile**.
3. W okienku profilów wybierz pozycję **Utwórz profil**.
4. W okienku **Utwórz profil** uzupełnij pola **Nazwa** i **Opis** odnoszące się do profilu sieci Wi-Fi.
5. Z listy rozwijanej **Platforma** wybierz platformę urządzenia, do której chcesz zastosować ustawienia sieci Wi-Fi. Obecnie dla ustawień sieci Wi-Fi można wybrać jedną z następujących platform:
    - **Android**
    - **Android for Work**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 lub nowszy**
    - **Windows 10 lub nowszy**

   > [!IMPORTANT]
   > Jeśli tworzysz profil dla urządzeń z systemem Windows 10, w tym Windows Holographic for Business, musisz wybrać platformę **Windows 8.1 i nowsze**. Platforma **Windows 10 i nowsze** nie zawiera typu profilu sieci Wi-Fi. 

6. Dla urządzeń firmy Apple lub urządzeń z systemem Android na liście rozwijanej **Typ sieci Wi-Fi** wybierz pozycję **Podstawowa** lub **Enterprise**. Możesz użyć opcji **Podstawowa**, aby dostarczyć podstawowe funkcje, takie jak nazwa sieci i identyfikator SSID. Opcja **Firmowa** umożliwia dostarczenie bardziej zaawansowanych informacji, takich jak protokół uwierzytelniania rozszerzonego (EAP), o ile jest używany przez sieć Wi-Fi. 

   Profil **Importowanie sieci Wi-Fi** (dla systemu Windows 8.1 i nowszego) pozwala zaimportować ustawienia sieci Wi-Fi jako plik XML wyeksportowany wcześniej z innego urządzenia.
1. Ustawienia, które można skonfigurować, różnią się w zależności od wybranej platformy. Szczegółowe informacje na temat ustawień każdej z platform podano w następujących tematach:
    - [Ustawienia systemu Android i programu Android for Work](wi-fi-settings-android.md)
    - [Ustawienia systemu iOS](wi-fi-settings-ios.md)
    - [macOS settings](wi-fi-settings-macos.md) (Ustawienia systemu macOS)
    - [Ustawienia systemu Windows 8.1 i nowszego](wi-fi-settings-import-windows-8-1.md) (w tym systemu Windows Holographic for Business)
1. Gdy skończysz, wróć do okienka **Tworzenie profilu**, a następnie wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony w okienku z listą profilów.

## <a name="next-steps"></a>Następne kroki

Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](device-profile-assign.md) (Sposoby przypisywania profilów urządzeń).
