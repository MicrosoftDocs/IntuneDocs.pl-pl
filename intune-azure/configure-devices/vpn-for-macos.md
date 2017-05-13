---
title: "Ustawienia sieci VPN dla urządzeń z systemem macOS w usłudze Intune | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące ustawień usługi Intune służących do konfigurowania połączeń sieci VPN na urządzeniach z systemem macOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d203a70d-37df-4195-85f7-ad5ef14ac2a1
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: a9748a0ad6b9bbe10e36ba133ba74edb6aa6e09a
ms.openlocfilehash: 76fdf944a21a7dfcd300ef71d12954e4f61831f5
ms.contentlocale: pl-pl
ms.lasthandoff: 05/05/2017


---

# <a name="vpn-settings-for-macos-devices-in-microsoft-intune"></a>Ustawienia sieci VPN dla urządzeń z systemem macOS w usłudze Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

W zależności od wybranych ustawień niektórych wartości z poniższej listy nie będzie można skonfigurować.

## <a name="base-vpn-settings"></a>**Podstawowe ustawienia sieci VPN**

**Nazwa połączenia** — umożliwia wprowadzenie nazwy połączenia. Użytkownicy zobaczą tę nazwę, przeglądając na urządzeniu listę dostępnych połączeń sieci VPN.
- **Adres IP lub nazwa FQDN** — umożliwia podanie adresu IP lub w pełni kwalifikowanej nazwy domeny serwera sieci VPN, z którym urządzenia będą się łączyć. Przykłady: **192.168.1.1**, **vpn.contoso.com**.
- **Metoda uwierzytelniania** — umożliwia wybór sposobu uwierzytelniania urządzeń na serwerze sieci VPN:
    - **Certyfikaty** — w obszarze **Certyfikat uwierzytelniania** można wybrać profil certyfikatu protokołu SCEP lub PKCS, który został wcześniej utworzony do uwierzytelniania połączenia. Aby uzyskać więcej szczegółowych informacji o profilach certyfikatów, zobacz artykuł [Konfigurowanie certyfikatów](how-to-configure-certificates.md).
    - **Nazwa użytkownika i hasło** — użytkownicy końcowi muszą podać nazwę użytkownika i hasło, aby zalogować się do serwera sieci VPN.
- **Typ połączenia** — umożliwia wybór typu połączenia sieci VPN z poniższej listy dostawców:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Niestandardowa sieć VPN**
- **Podziel tunelowanie** - wybierz ustawienie **Włącz** lub **Wyłącz**. Ta opcja pozwala urządzeniom decydować, z którego połączenia skorzystać, w zależności od ruchu. Na przykład użytkownik w hotelu użyje połączenia sieci VPN, aby uzyskać dostęp do plików roboczych, ale podczas zwykłego przeglądania Internetu skorzysta ze standardowej sieci hotelowej.

<!--- **Per-app VPN** - Select this option if you want to associate this VPN connection with an iOS or macOS app so that the connection will be opened when the app is run. You can associate the VPN profile with an app when you assign the software. For more information, see [How to assign and monitor apps](../manage-apps/deploy-apps.md). --->

## <a name="custom-vpn-settings"></a>Niestandardowe ustawienia sieci VPN

W przypadku wybrania opcji **Niestandardowa sieć VPN** skonfiguruj następujące ustawienia dodatkowe:

- **Identyfikator sieci VPN** To jest identyfikator używanej aplikacji sieci VPN dostarczony przez dostawcę sieci VPN.
- **Podaj pary klucza i wartości dla atrybutów niestandardowej sieci VPN** Dodaj lub importuj **Klucze** i **Wartości**, aby dostosować połączenie VPN. Te wartości również są zwykle dostarczane przez dostawcę sieci VPN.


## <a name="proxy-settings"></a>Ustawienia serwera proxy

- **Skrypt konfiguracji automatycznej** — umożliwia skonfigurowanie serwera proxy przy użyciu pliku. W polu **Adres URL serwera proxy** wprowadź adres URL (na przykład **http://proxy.contoso.com**), który zawiera plik konfiguracji.
- **Adres** — wprowadź adres serwera proxy (jako adres IP).
- **Numer portu** — wprowadź numer portu skojarzony z serwerem proxy.

