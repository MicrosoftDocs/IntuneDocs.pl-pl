---
title: Konfigurowanie ustawień sieci VPN na urządzeniach z systemem macOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodawanie lub Tworzenie profilu konfiguracji wirtualnej sieci prywatnej (VPN), w tym szczegółów połączenia, tunelowanie podzielone, niestandardowe ustawienia sieci VPN z identyfikatorami, pary kluczy i wartości, ustawienia serwera proxy ze skryptem konfiguracji, adresem IP lub nazwą FQDN i portem TCP w Microsoft Intune na urządzeniach z systemem macOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/09/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 044b35b34a9a5b01537e82dcfddca74a284ebdcc
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72491011"
---
# <a name="add-vpn-settings-on-macos-devices-in-microsoft-intune"></a>Konfigurowanie ustawień sieci VPN na urządzeniach z systemem macOS w usłudze Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Ten artykuł zawiera informacje dotyczące ustawień usługi Intune, których można użyć do konfigurowania połączeń sieci VPN na urządzeniach z systemem macOS.

W zależności od wybranych ustawień niektórych wartości z poniższej listy nie będzie można skonfigurować.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia](vpn-settings-configure.md).

> [!NOTE]
> Te ustawienia są dostępne dla wszystkich typów rejestracji. Aby uzyskać więcej informacji na temat typów rejestracji, zobacz [Rejestrowanie macOS](../enrollment/macos-enroll.md).

## <a name="base-vpn-settings"></a>Podstawowe ustawienia sieci VPN

**Nazwa połączenia**: umożliwia wprowadzenie nazwy połączenia. Użytkownicy końcowi widzą tę nazwę, przeglądając w urządzeniu listę dostępnych połączeń sieci VPN.
- **Adres IP lub nazwa FQDN**: umożliwia podanie adresu IP lub w pełni kwalifikowanej nazwy domeny serwera sieci VPN, z którym urządzenia się łączą. Przykłady: **192.168.1.1**, **vpn.contoso.com**.
- **Metoda uwierzytelniania**: umożliwia wybór sposobu uwierzytelniania urządzeń na serwerze sieci VPN:
  - **Certyfikaty**: w obszarze **Certyfikat uwierzytelniania** można wybrać profil certyfikatu protokołu SCEP lub PKCS, który został wcześniej utworzony do uwierzytelniania połączenia. Aby uzyskać więcej informacji o profilach certyfikatów, zobacz temat dotyczący [konfigurowania certyfikatów](../protect/certificates-configure.md).
  - **Nazwa użytkownika i hasło**: użytkownicy końcowi muszą podać nazwę użytkownika i hasło, aby zalogować się do serwera sieci VPN.
- **Typ połączenia**: umożliwia wybór typu połączenia sieci VPN z poniższej listy dostawców:
  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**
  - **Niestandardowa sieć VPN**
- **Podziel tunelowanie**: wybierz ustawienie **Włącz** lub **Wyłącz**. Ta opcja pozwala urządzeniom decydować, z którego połączenia skorzystać, w zależności od ruchu. Na przykład użytkownik w hotelu używa połączenia sieci VPN, aby uzyskać dostęp do plików roboczych, ale podczas zwykłego przeglądania Internetu skorzysta ze standardowej sieci hotelowej.

<!--- **Per-app VPN** - Select this option if you want to associate this VPN connection with an iOS or macOS app so that the connection will be opened when the app is run. You can associate the VPN profile with an app when you assign the software. For more information, see [How to assign and monitor apps](../apps/apps-deploy.md). --->

## <a name="custom-vpn-settings"></a>Niestandardowe ustawienia sieci VPN

W przypadku wybrania opcji **Niestandardowa sieć VPN** skonfiguruj następujące ustawienia dodatkowe:

- **Identyfikator sieci VPN**: Wprowadź identyfikator używanej aplikacji sieci VPN. Ten identyfikator jest dostarczany przez dostawcę sieci VPN.
- **Podaj pary klucza i wartości dla atrybutów niestandardowej sieci VPN**: dodaj lub zaimportuj **klucze** i **wartości**, aby dostosować połączenie sieci VPN. Te wartości są zwykle dostarczane przez dostawcę sieci VPN.

## <a name="proxy-settings"></a>Ustawienia serwera proxy

- **Skrypt konfiguracji automatycznej**: umożliwia skonfigurowanie serwera proxy przy użyciu pliku. Wprowadź **Adres URL serwera proxy**, który zawiera plik konfiguracji. Na przykład wprowadź `http://proxy.contoso.com`.
- **Adres**: wprowadź adres serwera proxy (jako adres IP).
- **Numer portu**: podaj numer portu skojarzony z serwerem proxy.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. W dalszej części [przypiszesz profil](device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).

Konfigurowanie ustawień sieci VPN na urządzeniach z [systemem Android](vpn-settings-android.md), [Android Enterprise](vpn-settings-android-enterprise.md), [iOS](vpn-settings-ios.md)i [Windows 10](vpn-settings-windows-10.md) .
