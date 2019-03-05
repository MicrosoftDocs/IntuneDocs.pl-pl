---
title: Tworzenie profilu urządzenia sieci VPN w usłudze Microsoft Intune na platformie Azure | Microsoft Docs
description: W przypadku urządzeń z systemem iOS można w usłudze Microsoft Intune wyświetlić typy połączenia wirtualnej sieci prywatnej (VPN), utworzyć profil urządzenia sieci VPN w witrynie Azure Portal i wyświetlić opcje zabezpieczania profilu sieci VPN za pomocą certyfikatów, czyli nazwę użytkownika i hasło.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/25/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0588d3e01994092ca48a8a3bb4844883f7a5b100
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57235348"
---
# <a name="create-vpn-profiles-in-intune"></a>Tworzenie profilów sieci VPN w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Wirtualne sieci prywatne (VPN) zapewniają użytkownikom bezpieczny dostęp zdalny do sieci firmowej. Do nawiązania połączenia z serwerem sieci VPN urządzenia używają profilu połączenia VPN. Za pomocą opcji w obszarze **Profile sieci VPN** w usłudze Microsoft Intune możesz przypisywać ustawienia sieci VPN do użytkowników i urządzeń w organizacji tak, aby łączenie z siecią było łatwe i bezpieczne.

Na przykład możesz chcieć udostępnić wszystkim urządzeniom z systemem iOS ustawienia wymagane do połączenia z udziałem plików w sieci firmowej. Istnieje możliwość utworzenia profilu sieci VPN zawierającego ustawienia łączenia z siecią firmową. Następnie można przypisać ten profil do wszystkich użytkowników, którzy mają urządzenia z systemem iOS. Użytkownicy widzą połączenie sieci VPN na liście dostępnych sieci i mogą łatwo nawiązać połączenie.

Zasady konfiguracji niestandardowych usługi Intune umożliwiają tworzenie profilów sieci VPN dla następujących platform:

* System Android 4 lub nowszy
* Zarejestrowane urządzenia z systemem Windows 8.1 lub nowszym
* System Windows Phone 8.1 lub nowszy
* Zarejestrowane urządzenia z systemem Windows 10 Desktop
* Windows 10 Mobile
* Windows Holographic for Business

## <a name="vpn-connection-types"></a>Typy połączeń z siecią VPN

Możesz utworzyć profile sieci VPN, korzystając z następujących typów połączeń:

|Typ połączenia|Android<br>Profile służbowe systemu Android|iOS|macOS|Windows Phone 8,1|Windows 8.1|Windows 10|
|-|-|-|-|-|-|-|
|Automatyczny|Nie|Nie|Nie|Nie|Nie|Tak|
|Check Point Capsule VPN|Tak|Tak|Tak|Tak|Tak|Tak|
|Cisco AnyConnect|Tak|Tak|Tak|Nie|Nie|Nie|
|SonicWall Mobile Connect|Tak|Tak|Tak|Tak|Tak|Tak|
|F5 Edge Client|Tak|Tak|Tak|Tak|Tak|Tak|
|Palo Alto Networks GlobalProtect|Nie|Tak|Nie|Nie|Nie|Tak|
|Pulse Secure|Tak|Tak|Tak|Tak|Tak|Tak|
|Cisco (IPSec)|Nie|Tak|Nie|Nie|Nie|Nie|
|Citrix|Tak (tylko Android)|Tak|Nie|Nie|Nie|Tak|
|IKEv2|Nie|Nie|Nie|Nie|Nie|Tak|
|L2TP|Nie|Nie|Nie|Nie|Nie|Tak|
|PPTP|Nie|Nie|Nie|Nie|Nie|Tak|
|Zscaler|Nie|Tak|Nie|Nie|Nie|Nie|
|Niestandardowa sieć VPN|Nie|Tak|Tak|Nie|Nie|Nie|

> [!IMPORTANT]
> Aby używanie profilów sieci VPN przypisanych do urządzenia było możliwe, należy zainstalować aplikację VPN odpowiednią do profilu. W artykule [Co to jest zarządzanie aplikacjami w usłudze Microsoft Intune?](app-management.md) znajdziesz informacje, które pomogą Ci przypisać aplikację przy użyciu usługi Intune.  

Zapoznaj się z artykułem [Create a profile with custom settings (Tworzenie profilu za pomocą ustawień niestandardowych)](custom-settings-configure.md), aby dowiedzieć się, jak tworzyć niestandardowe profile sieci VPN za pomocą ustawień identyfikatora URI.

## <a name="create-a-device-profile-containing-vpn-settings"></a>Tworzenie profilu urządzenia zawierającego ustawienia sieci VPN

1. Zaloguj się do [portalu Azure](https://portal.azure.com).
2. Wybierz opcję **Wszystkie usługi**, odfiltruj usługę **Intune**, a następnie wybierz pozycję **Microsoft Intune**.
3. Wybierz pozycję **Konfiguracja urządzeń** > **Profile** > **Utwórz profil**.
4. Podaj wartości **Nazwa** i **Opis** dla profilu sieci VPN.
5. Z listy rozwijanej **Platforma** wybierz platformę urządzenia, do której chcesz zastosować ustawienia sieci VPN. Obecnie dla ustawień sieci VPN urządzenia można wybrać jedną z następujących platform:
   - **Android**
   - **Android enterprise**
   - **iOS**
   - **macOS**
   - **Windows Phone 8.1**
   - **Windows 8.1 lub nowszy**
   - **Windows 10 lub nowszy**
6. Z listy rozwijanej **Typ profilu** wybierz pozycję **Sieć VPN**.
7. Ustawienia, które można skonfigurować, różnią się w zależności od wybranej platformy. Szczegółowe informacje na temat ustawień każdej z platform podano w następujących tematach:
   - [Ustawienia systemu Android i profilu służbowego w systemie Android](vpn-settings-android.md)
   - [Ustawienia systemu iOS](vpn-settings-ios.md)
   - [macOS settings](vpn-settings-macos.md) (Ustawienia systemu macOS)
   - [Ustawienia systemu Windows Phone 8.1](vpn-settings-windows-phone-8-1.md)
   - [Windows 8.1 settings](vpn-settings-windows-8-1.md) (Ustawienia systemu Windows 8.1)
   - [Ustawienia systemu Windows 10](vpn-settings-windows-10.md) (w tym systemu Windows Holographic for Business)
8. Gdy wszystko będzie gotowe, **utwórz** profil.

Profil zostanie utworzony i wyświetlony na liście profilów. Aby przypisać ten profil do grup, zobacz [przypisywanie profilów urządzeń](device-profile-assign.md).

## <a name="methods-of-securing-vpn-profiles"></a>Metody zabezpieczania profilów sieci VPN

Profile sieci VPN mogą używać różnych typów połączeń i protokołów różnych producentów. Połączenia te są zwykle chronione przy użyciu jednej z dwóch metod.

### <a name="certificates"></a>Certyfikaty

Podczas tworzenia profilu sieci VPN wybierasz profil certyfikatu SCEP lub PKCS utworzony wcześniej w usłudze Intune. Ten profil jest znany pod nazwą certyfikatu tożsamości. Jest on używany do uwierzytelniania względem profilu zaufanego certyfikatu (lub *certyfikatu głównego*), który został utworzony, aby umożliwić urządzeniu użytkownika nawiązanie połączenia. Zaufany certyfikat jest przypisywany do komputera przeprowadzającego uwierzytelnienie połączenia z siecią VPN — zazwyczaj jest to serwer sieci VPN.

Aby uzyskać więcej informacji o sposobie tworzenia i używania profilów certyfikatów w usłudze Intune, zobacz artykuł [How to configure certificates with Microsoft Intune](certificates-configure.md) (Konfigurowanie certyfikatów przy użyciu usługi Microsoft Intune).

### <a name="user-name-and-password"></a>Nazwa użytkownika i hasło

Użytkownik jest uwierzytelniany na serwerze sieci VPN przez podanie swojej nazwy użytkownika i hasła.
