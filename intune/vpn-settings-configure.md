---
title: "Jak konfigurować ustawienia sieci VPN w usłudze Intune"
titleSuffix: Azure portal
description: "Informacje dotyczące konfigurowania ustawień sieci VPN na zarządzanych urządzeniach przy użyciu usługi Intune."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 699fa64bc0f720b18c1376e39b85eccd9018bbaf
ms.sourcegitcommit: e9f9fccccef691333143b7523d1b325ee7d1915a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2017
---
# <a name="how-to-configure-vpn-settings-in-microsoft-intune"></a>Jak skonfigurować ustawienia sieci VPN w usłudze Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Wirtualne sieci prywatne (VPN) zapewniają użytkownikom bezpieczny dostęp zdalny do sieci firmowej. Do nawiązania połączenia z serwerem sieci VPN urządzenia używają profilu połączenia VPN. Za pomocą opcji w obszarze **Profile sieci VPN** w usłudze Microsoft Intune możesz przypisywać ustawienia sieci VPN do użytkowników i urządzeń w organizacji tak, aby łączenie z siecią było łatwe i bezpieczne.

Na przykład możesz chcieć udostępnić wszystkim urządzeniom z systemem iOS ustawienia wymagane do połączenia z udziałem plików w sieci firmowej. W tym celu tworzysz profil sieci VPN zawierający ustawienia wymagane do połączenia z siecią firmową, a następnie przypisujesz go do wszystkich użytkowników mających urządzenia z systemem iOS. Użytkownicy będą widzieli połączenie VPN na liście dostępnych sieci i będą mogli łatwo nawiązać połączenie.

## <a name="vpn-connection-types"></a>Typy połączeń z siecią VPN

Możesz utworzyć profile sieci VPN, korzystając z następujących typów połączeń:

|Typ połączenia|Android<br>Program Android for Work|iOS|macOS|Windows Phone 8.1|Windows 8.1|Windows 10|
|-|-|-|-|-|-|-|
|Pulse Secure|Tak|Tak|Tak|Tak|Tak|Tak|
|Cisco (IPSec)|Nie|Tak|Nie|Nie|Nie|Nie|
|Citrix|Tak|Tak|Nie|Nie|Nie|Tak|
|F5 Edge Client|Tak|Tak|Tak|Tak|Tak|Tak|
|Dell SonicWALL Mobile Connect|Tak|Tak|Tak|Tak|Tak|Tak|
|Check Point Capsule VPN|Tak|Tak|Tak|Tak|Tak|Tak|
|Cisco AnyConnect|Tak|Tak|Tak|Nie|Nie|Nie|
|Automatyczny|Nie|Nie|Nie|Nie|Nie|Tak|
|IKEv2|Nie|Nie|Nie|Nie|Nie|Tak|
|L2TP|Nie|Nie|Nie|Nie|Nie|Tak|
|PPTP|Nie|Nie|Nie|Nie|Nie|Tak|
|Niestandardowy|Nie|Tak|Tak|Nie|Nie|Nie|


> [!IMPORTANT]
> Aby używanie profilów sieci VPN przypisanych do urządzenia było możliwe, należy zainstalować aplikację VPN odpowiednią do profilu. W artykule [Co to jest zarządzanie aplikacjami w usłudze Microsoft Intune?](app-management.md) znajdziesz informacje, które pomogą Ci przypisać aplikację przy użyciu usługi Intune.  

Zapoznaj się z artykułem [Create custom VPN profiles](custom-vpn-profiles-create.md) (Tworzenie niestandardowych profilów sieci VPN), aby dowiedzieć się, jak tworzyć niestandardowe profile sieci VPN z użyciem ustawień identyfikatora URI.     

## <a name="create-a-device-profile-containing-vpn-settings"></a>Tworzenie profilu urządzenia zawierającego ustawienia sieci VPN

1. Zaloguj się do portalu Azure Portal.
2. Wybierz kolejno opcje **Więcej usług** > **Monitorowanie i zarządzanie** > **Intune**.
3. W bloku **Intune** wybierz opcję **Konfiguracja urządzeń**.
2. W bloku **Konfiguracja urządzeń** wybierz kolejno pozycje **Zarządzaj** > **Profile**.
3. W bloku profilów wybierz pozycję **Utwórz profil**.
4. W bloku **Utwórz profil** uzupełnij pola **Nazwa** i **Opis** odnoszące się do profilu sieci VPN.
5. Z listy rozwijanej **Platforma** wybierz platformę urządzenia, do której chcesz zastosować ustawienia sieci VPN. Obecnie dla ustawień sieci VPN urządzenia można wybrać jedną z następujących platform:
    - **Android**
    - **Android for Work**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 lub nowszy**
    - **Windows 10 lub nowszy**
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Sieć VPN**.
7. Ustawienia, które można skonfigurować, różnią się w zależności od wybranej platformy. Szczegółowe informacje na temat ustawień każdej z platform podano w następujących tematach:
    - [Ustawienia systemu Android i programu Android for Work](vpn-settings-android.md)
    - [Ustawienia systemu iOS](vpn-settings-ios.md)
    - [macOS settings](vpn-settings-macos.md) (Ustawienia systemu macOS)
    - [Ustawienia systemu Windows Phone 8.1](vpn-settings-windows-phone-8-1.md)
    - [Windows 8.1 settings](vpn-settings-windows-8-1.md) (Ustawienia systemu Windows 8.1)
    - [Windows 10 settings](vpn-settings-windows-10.md) (Ustawienia systemu Windows 10)
8. Gdy skończysz, wróć do bloku **Utwórz profil** i wybierz pozycję **Utwórz**.

Profil zostanie utworzony i wyświetlony w bloku listy profilów.
Wskazówki umożliwiające przypisanie tego profilu do grup znajdują się w artykule [How to assign device profiles](device-profile-assign.md) (Sposoby przypisywania profilów urządzeń).


## <a name="methods-of-securing-vpn-profiles"></a>Metody zabezpieczania profilów sieci VPN

Profile sieci VPN mogą używać różnych typów połączeń i protokołów różnych producentów. Połączenia te są zwykle chronione przy użyciu jednej z dwóch metod.

### <a name="certificates"></a>Certyfikaty

Podczas tworzenia profilu sieci VPN wybierasz profil certyfikatu SCEP lub PKCS utworzony wcześniej w usłudze Intune. Jest on znany pod nazwą certyfikatu tożsamości. Jest on używany do uwierzytelniania względem profilu zaufanego certyfikatu (lub *certyfikatu głównego*), który został utworzony do określenia, czy urządzenie użytkownika może nawiązać połączenie. Zaufany certyfikat jest przypisywany do komputera przeprowadzającego uwierzytelnienie połączenia z siecią VPN — zazwyczaj jest to serwer sieci VPN.

Aby uzyskać więcej informacji o sposobie tworzenia i używania profilów certyfikatów w usłudze Intune, zobacz artykuł [How to configure certificates with Microsoft Intune](certificates-configure.md) (Konfigurowanie certyfikatów przy użyciu usługi Microsoft Intune).

### <a name="user-name-and-password"></a>Nazwa użytkownika i hasło

Użytkownik jest uwierzytelniany na serwerze sieci VPN przez podanie swojej nazwy użytkownika i hasła.
