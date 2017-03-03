---
title: "Jak skonfigurować ustawienia sieci Wi-Fi w usłudze Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące konfigurowania ustawień sieci Wi-Fi na zarządzanych urządzeniach przy użyciu usługi Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1fadb488-9c6c-43c1-ba23-8c69db633b96
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: aea6d9868d91260dd7a3a4c3b1426f12fcc9f47d
ms.lasthandoff: 02/18/2017


---

# <a name="how-to-configure-wi-fi-settings-in-microsoft-intune"></a>Jak skonfigurować ustawienia sieci Wi-Fi w usłudze Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Aby wdrożyć ustawienia sieci bezprzewodowej dla użytkowników i urządzeń w Twojej organizacji, użyj profilu sieci Wi-Fi usługi Microsoft Intune. W przypadku wdrożenia profilu sieci Wi-Fi użytkownicy mają dostęp do firmowej sieci Wi-Fi bez konieczności samodzielnego konfigurowania połączenia.

Załóżmy, że zainstalowano nową sieć Wi-Fi o nazwie Sieć Wi-Fi firmy Contoso i że chcesz skonfigurować wszystkie urządzenia z systemem iOS do łączenia się z tą siecią. Oto proces:

1. Utwórz profil sieci Wi-Fi zawierający ustawienia wymagane do łączenia się z siecią bezprzewodową Sieć Wi-Fi firmy Contoso.
2. Przypisz profil do grupy obejmującej wszystkich użytkowników urządzeń z systemem iOS.
3. Użytkownicy znajdują nową sieć Wi-Fi firmy Contoso na liście sieci bezprzewodowych w urządzeniu i mogą się łatwo z nią łączyć.

Profile sieci Wi-Fi obsługują następujące platformy urządzeń:

- System Android 4 lub nowszy
- System iOS 8.0 i nowsze
- macOS (Mac OS X 10.9 lub nowszy)

Na urządzeniach z systemem Windows 8.1, Windows 10 lub Windows 10 Mobile można zaimportować konfigurację sieci Wi-Fi, która została wcześniej wyeksportowana z innego urządzenia.

Skorzystaj z informacji zawartych w tym temacie, aby uzyskać podstawową wiedzę z zakresu konfigurowania profilów sieci Wi-Fi, a następnie zapoznaj się z tematami dotyczącymi poszczególnych platform, aby dowiedzieć się więcej o charakterystyce urządzeń.

## <a name="create-a-device-profile-containing-wi-fi-settings"></a>Tworzenie profilu urządzenia zawierającego ustawienia sieci Wi-Fi

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno pozycje **Więcej usług** > **Inne** > **Intune**.
3. W bloku **Intune** wybierz pozycję **Konfiguruj urządzenia**.
2. W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
3. W bloku profilów wybierz pozycję **Utwórz profil**.
4. W bloku **Utwórz profil** uzupełnij pola **Nazwa** i **Opis** odnoszące się do profilu sieci Wi-Fi.
5. Z listy rozwijanej **Platforma** wybierz platformę urządzenia, do której chcesz zastosować ustawienia sieci Wi-Fi. Obecnie dla ustawień sieci Wi-Fi można wybrać jedną z następujących platform:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows 8.1 lub nowszy (importuj profil)**
6. Z listy rozwijanej typu **profilu** wybierz pozycję **Podstawowa sieć Wi-Fi** lub **Firmowa sieć Wi-Fi**.
    >[!TIP]
    >Użyj opcji **Podstawowa sieć Wi-Fi**, aby dostarczyć podstawowe funkcje, takie jak nazwa sieci i identyfikator SSID. **Firmowa sieć Wi-Fi** umożliwia dostarczenie bardziej zaawansowanych informacji, takich jak protokół uwierzytelniania rozszerzonego (EAP) (o ile jest używany przez sieć Wi-Fi). **Importowanie sieci Wi-Fi** (dla systemu Windows 8.1 i Windows 10) pozwala zaimportować ustawienia sieci Wi-Fi jako plik XML wyeksportowany wcześniej z innego urządzenia.
7. Ustawienia, które można skonfigurować, różnią się w zależności od wybranej platformy. Szczegółowe informacje na temat ustawień każdej z platform podano w następujących tematach:
    - [Ustawienia systemu Android](wi-fi-for-android.md)
    - [Ustawienia systemu iOS](wi-fi-for-ios.md)
    - [macOS settings](wi-fi-for-macos.md) (Ustawienia systemu macOS)
    - [Ustawienia systemu Windows Phone 8.1](wi-fi-import-for-windows-8-1.md)
8. Gdy skończysz, wróć do bloku **Utwórz profil** i wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony w bloku listy profilów.
Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](how-to-assign-device-profiles.md) (Sposoby przypisywania profilów urządzeń).


