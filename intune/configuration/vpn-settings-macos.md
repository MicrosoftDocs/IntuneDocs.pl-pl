---
title: Konfigurowanie ustawień sieci VPN na urządzeniach z systemem macOS w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Dodawanie lub tworzenie profilu konfiguracji wirtualnej sieci prywatnej (VPN), w tym szczegółów połączenia, tunelowanie podzielone, niestandardowe ustawienia sieci VPN z identyfikatorem, pary klucz i wartość, ustawienia serwera proxy ze skryptem konfiguracji, adresem IP lub nazwą FQDN i portem TCP w usłudze Microsoft Intune na urządzeniach z systemem macOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b20a7eca6f71d46380f9fcdb1674226cc54a104f
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77510783"
---
# <a name="add-vpn-settings-on-macos-devices-in-microsoft-intune"></a>Konfigurowanie ustawień sieci VPN na urządzeniach z systemem macOS w usłudze Microsoft Intune



Ten artykuł zawiera informacje dotyczące ustawień usługi Intune, których można użyć do konfigurowania połączeń sieci VPN na urządzeniach z systemem macOS.

W zależności od wybranych ustawień niektórych wartości z poniższej listy nie będzie można skonfigurować.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia](vpn-settings-configure.md).

> [!NOTE]
> Te ustawienia są dostępne dla wszystkich typów rejestracji. Aby uzyskać więcej informacji na temat typów rejestracji, zobacz [Rejestracja urządzeń z systemem macOS](../enrollment/macos-enroll.md).

## <a name="base-vpn-settings"></a>Podstawowe ustawienia sieci VPN

**Nazwa połączenia**: Wprowadź nazwę dla połączenia. Użytkownicy końcowi widzą tę nazwę, przeglądając w urządzeniu listę dostępnych połączeń sieci VPN.
- **Adres IP lub nazwa FQDN**: Podaj adres IP lub w pełni kwalifikowaną nazwę domeny (FQDN) serwera sieci VPN, z którym mają się łączyć urządzenia. Przykłady: **192.168.1.1**, **vpn.contoso.com**.
- **Metoda uwierzytelniania**: Umożliwia wybór sposobu uwierzytelniania urządzeń na serwerze sieci VPN:
  - **Certyfikaty**: W obszarze **Certyfikat uwierzytelniania** można wybrać profil certyfikatu protokołu SCEP lub PKCS, który został wcześniej utworzony do uwierzytelniania połączenia. Aby uzyskać więcej informacji o profilach certyfikatów, zobacz temat dotyczący [konfigurowania certyfikatów](../protect/certificates-configure.md).
  - **Nazwa użytkownika i hasło**: Użytkownicy końcowi muszą podać nazwę użytkownika i hasło, aby zalogować się do serwera sieci VPN.
- **Typ połączenia**: Umożliwia wybór typu połączenia sieci VPN z poniższej listy dostawców:
  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**
  - **Niestandardowa sieć VPN**
- **Podziel tunelowanie**: Wybierz ustawienie **Włącz** lub **Wyłącz**. Ta opcja pozwala urządzeniom decydować, z którego połączenia skorzystać, w zależności od ruchu. Na przykład użytkownik w hotelu używa połączenia sieci VPN, aby uzyskać dostęp do plików roboczych, ale podczas zwykłego przeglądania Internetu skorzysta ze standardowej sieci hotelowej.

<!--- **Per-app VPN** - Select this option if you want to associate this VPN connection with an iOS/iPadOS or macOS app so that the connection will be opened when the app is run. You can associate the VPN profile with an app when you assign the software. For more information, see [How to assign and monitor apps](../apps/apps-deploy.md). --->

## <a name="custom-vpn-settings"></a>Niestandardowe ustawienia sieci VPN

W przypadku wybrania opcji **Niestandardowa sieć VPN** skonfiguruj następujące ustawienia dodatkowe:

- **Identyfikator sieci VPN**: Wprowadź identyfikator używanej aplikacji sieci VPN. Ten identyfikator jest dostarczany przez dostawcę sieci VPN.
- **Podaj pary klucza i wartości dla atrybutów niestandardowej sieci VPN**: Dodaj lub zaimportuj **klucze** i **wartości**, aby dostosować połączenie swojej sieci VPN. Te wartości są zwykle dostarczane przez dostawcę sieci VPN.

## <a name="proxy-settings"></a>Ustawienia serwera proxy

- **Skrypt konfiguracji automatycznej**: Użyj pliku do skonfigurowania serwera proxy. Wprowadź **Adres URL serwera proxy**, który zawiera plik konfiguracji. Na przykład wprowadź `http://proxy.contoso.com`.
- **Adres**: Wprowadź adres serwera proxy (jako adres IP).
- **Numer portu**: Wprowadź numer portu skojarzony z serwerem proxy.

## <a name="next-steps"></a>Następne kroki

Profil został utworzony, ale nie wykonuje jeszcze żadnych czynności. W dalszej części [przypiszesz profil](device-profile-assign.md) i będziesz [monitorować jego stan](device-profile-monitor.md).

Konfigurowanie ustawień sieci VPN na urządzeniach z systemami [Android](vpn-settings-android.md), [Android Enterprise](vpn-settings-android-enterprise.md), [iOS/iPadOS](vpn-settings-ios.md) i [Windows 10](vpn-settings-windows-10.md).
