---
title: Dodawanie ustawień sieci VPN do urządzeń w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Do utworzenia połączenia z wirtualną siecią prywatną (VPN) w usłudze Microsoft Intune na urządzeniach z systemami Android, Android Enterprise, iOS, macOS lub Windows należy użyć ustawień wbudowanych.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5628ba39cafe38cc66827d69584d009c15326bd4
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72491751"
---
# <a name="create-vpn-profiles-to-connect-to-vpn-servers-in-intune"></a>Tworzenie profilów sieci VPN w celu nawiązania połączenia z serwerami sieci VPN w usłudze Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Wirtualne sieci prywatne (VPN) zapewniają użytkownikom bezpieczny dostęp zdalny do sieci organizacji. Do nawiązania połączenia z serwerem sieci VPN urządzenia używają profilu połączenia VPN. **Profile sieci VPN** w usłudze Microsoft Intune służą do przypisania ustawień sieci VPN do użytkowników i urządzeń w organizacji, tak aby łączenie z siecią organizacji było łatwe i bezpieczne.

Przyjmijmy na przykład, że chcesz skonfigurować na wszystkich urządzeniach z systemem iOS ustawienia wymagane do łączenia się z udziałem plików w sieci organizacji. Tworzysz profil sieci VPN, który zawiera te ustawienia. Następnie przypisujesz ten profil do wszystkich użytkowników, którzy mają urządzenia z systemem iOS. Użytkownicy widzą połączenie sieci VPN na liście dostępnych sieci i mogą łatwo nawiązać połączenie.

> [!NOTE]
> [Zasady niestandardowych konfiguracji usługi Intune](custom-settings-configure.md) umożliwiają tworzenie profilów sieci VPN dla następujących platform:
>
> * System Android 4 lub nowszy
> * Zarejestrowane urządzenia z systemem Windows 8.1 lub nowszym
> * System Windows Phone 8.1 lub nowszy
> * Zarejestrowane urządzenia z systemem Windows 10 Desktop
> * Windows 10 Mobile
> * Windows Holographic for Business

## <a name="vpn-connection-types"></a>Typy połączeń z siecią VPN

Możesz utworzyć profile sieci VPN, korzystając z następujących typów połączeń:

|Typ połączenia|Platforma|
|-|-|
|Automatyczny|Windows 10|
|Check Point Capsule VPN|— Android<br/>— Profile służbowe w systemie Android Enterprise<br/>— iOS<br/>— macOS<br/>— Windows 10<br/>— Windows 8.1<br/>— Windows Phone 8.1|
|Cisco AnyConnect|— Android<br/>— Profile służbowe w systemie Android Enterprise<br/>— Właściciel urządzenia z systemem Android Enterprise (w pełni zarządzanego)<br/>— iOS<br/>— macOS|
|Cisco (IPSec)|iOS|
|Citrix SSO|— Android<br/>— Profile służbowe w systemie Android Enterprise: Użyj [zasad konfigurowaniai aplikacji](../apps/app-configuration-policies-use-android.md)<br/>— iOS<br/>— Windows 10|
|Niestandardowa sieć VPN|— iOS<br/>— macOS|
|F5 Access|— Android<br/>— Profile służbowe w systemie Android Enterprise<br/>— Właściciel urządzenia z systemem Android Enterprise (w pełni zarządzanego)<br/>— iOS<br/>— macOS<br/>— Windows 10<br/>— Windows 8.1<br/>— Windows Phone 8.1|
|IKEv2| — iOS<br/>— Windows 10|
|L2TP|Windows 10|
|Palo Alto Networks GlobalProtect|— Profile służbowe w systemie Android Enterprise: Użyj [zasad konfigurowaniai aplikacji](../apps/app-configuration-policies-use-android.md)<br/>— iOS<br/>— Windows 10|
|PPTP|Windows 10|
|Pulse Secure|— Android<br/>— Profile służbowe w systemie Android Enterprise<br/>— Właściciel urządzenia z systemem Android Enterprise (w pełni zarządzanego)<br/>— iOS<br/>— macOS<br/>— Windows 10<br/>— Windows 8.1<br/>— Windows Phone 8.1|
|SonicWall Mobile Connect|— Android<br/>— Profile służbowe w systemie Android Enterprise<br/>— iOS<br/>— macOS<br/>— Windows 10<br/>— Windows 8.1<br/>— Windows Phone 8.1|
|Zscaler|— Profile służbowe w systemie Android Enterprise: Użyj [zasad konfigurowaniai aplikacji](../apps/app-configuration-policies-use-android.md)<br/>— iOS|

> [!IMPORTANT]
> Aby używanie profilów sieci VPN przypisanych do urządzenia było możliwe, należy zainstalować aplikację VPN odpowiednią do profilu. W artykule [Co to jest zarządzanie aplikacjami w usłudze Microsoft Intune?](../apps/app-management.md) znajdziesz informacje, które pomogą Ci przypisać aplikację przy użyciu usługi Intune.  

Zapoznaj się z artykułem [Create a profile with custom settings (Tworzenie profilu za pomocą ustawień niestandardowych)](custom-settings-configure.md), aby dowiedzieć się, jak tworzyć niestandardowe profile sieci VPN za pomocą ustawień identyfikatora URI.

## <a name="create-a-device-profile"></a>Tworzenie profilu urządzenia

1. W usłudze [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) wybierz kolejno pozycje **Konfiguracja urządzenia** > **Profile** > **Utwórz profil**.
2. Wprowadź następujące właściwości:

    - **Nazwa**: Wprowadź opisową nazwę profilu. Nadaj nazwę profilom, aby można było je później łatwo rozpoznać. For example, a good profile name is **VPN profile for entire company**.
    - **Opis**: Wprowadź opis profilu. To ustawienie jest opcjonalne, ale zalecane.
    - **Platforma**: Wybierz platformę urządzeń. Dostępne opcje:

      - **Android**
      - **Android Enterprise** > **Tylko właściciel urządzenia**
      - **Android Enterprise** > **Tylko profil służbowy**
      - **iOS/iPadOS**
      - **macOS**
      - **Windows Phone 8.1**
      - **Windows 8.1 lub nowszy**
      - **Windows 10 lub nowszy**

    - **Typ profilu**: Wybierz pozycję **Sieć VPN**.

3. Ustawienia, które można skonfigurować, różnią się w zależności od wybranej platformy. Szczegółowe ustawienia dla poszczególnych platform można znaleźć w następujących artykułach:

    - [Ustawienia systemu Android](vpn-settings-android.md)
    - [Ustawienia systemu Android Enterprise](vpn-settings-android-enterprise.md)
    - [Ustawienia systemu iOS/iPadOS](vpn-settings-ios.md)
    - [macOS settings](vpn-settings-macos.md) (Ustawienia systemu macOS)
    - [Ustawienia systemu Windows Phone 8.1](vpn-settings-windows-phone-8-1.md)
    - [Windows 8.1 settings](vpn-settings-windows-8-1.md) (Ustawienia systemu Windows 8.1)
    - [Ustawienia systemu Windows 10](vpn-settings-windows-10.md) (w tym systemu Windows Holographic for Business)

4. Gdy wszystko będzie gotowe, **utwórz** profil.

Profil zostanie utworzony i wyświetlony na liście profilów. Aby przypisać ten profil do grup, zobacz [przypisywanie profilów urządzeń](device-profile-assign.md).

## <a name="secure-your-vpn-profiles"></a>Zabezpieczanie profilów sieci VPN

Profile sieci VPN mogą używać różnych typów połączeń i protokołów różnych producentów. Te połączenia są zwykle zabezpieczone za pomocą poniższych metod.

### <a name="certificates"></a>Certyfikaty

Podczas tworzenia profilu sieci VPN wybierasz profil certyfikatu SCEP lub PKCS utworzony wcześniej w usłudze Intune. Ten profil jest znany pod nazwą certyfikatu tożsamości. Jest on używany do uwierzytelniania względem profilu zaufanego certyfikatu (lub *certyfikatu głównego*), który został utworzony, aby umożliwić urządzeniu użytkownika nawiązanie połączenia. Zaufany certyfikat jest przypisywany do komputera przeprowadzającego uwierzytelnienie połączenia z siecią VPN — zazwyczaj jest to serwer sieci VPN.

Aby uzyskać więcej informacji o sposobie tworzenia i używania profilów certyfikatów w usłudze Intune, zobacz artykuł [How to configure certificates with Microsoft Intune](../protect/certificates-configure.md) (Konfigurowanie certyfikatów przy użyciu usługi Microsoft Intune).

### <a name="user-name-and-password"></a>Nazwa użytkownika i hasło

Użytkownik jest uwierzytelniany na serwerze sieci VPN przez podanie swojej nazwy użytkownika i hasła.

## <a name="next-steps"></a>Następne kroki

Utworzony profil nie wykonuje jeszcze żadnych czynności. Następnie [przypisz profil](device-profile-assign.md) do urządzeń.

Możesz również tworzyć i używać sieci VPN dla poszczególnych aplikacji na urządzeniach z systemem [Android](android-pulse-secure-per-app-vpn.md) i [iOS](vpn-setting-configure-per-app.md).
