---
title: "Ustawienia sieci VPN dla urządzeń z systemem Android w usłudze Intune"
titleSuffix: Intune Azure preview
description: "Wersja zapoznawcza usługi Intune Azure: informacje dotyczące ustawień usługi Intune służących do konfigurowania połączeń sieci VPN na urządzeniach z systemem Android."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16c056ca-320e-4107-ad03-a0cf96c28885
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 8c8690b191c7358c8fd60c241177aca1372a8f54
ms.contentlocale: pl-pl
ms.lasthandoff: 05/23/2017


---

# <a name="vpn-settings-for-android-devices-in-microsoft-intune"></a>Ustawienia sieci VPN dla urządzeń z systemem Android w usłudze Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

W zależności od wybranych ustawień niektórych wartości z poniższej listy nie będzie można skonfigurować.

**Nazwa połączenia** — umożliwia wprowadzenie nazwy połączenia. Użytkownicy zobaczą tę nazwę, przeglądając na urządzeniu listę dostępnych połączeń sieci VPN.
- **Adres IP lub nazwa FQDN** — umożliwia podanie adresu IP lub w pełni kwalifikowanej nazwy domeny serwera sieci VPN, z którym urządzenia będą się łączyć. Przykłady: **192.168.1.1**, **vpn.contoso.com**.
- **Metoda uwierzytelniania** — umożliwia wybór sposobu uwierzytelniania urządzeń na serwerze sieci VPN:
    - **Certyfikaty** — umożliwia wybór profilu certyfikatu protokołu SCEP lub PKCS, który został wcześniej utworzony do uwierzytelniania połączenia. Aby uzyskać więcej szczegółowych informacji o profilach certyfikatów, zobacz artykuł [Konfigurowanie certyfikatów](certificates-configure.md).
    - **Nazwa użytkownika i hasło** — użytkownicy końcowi muszą podać nazwę użytkownika i hasło, aby zalogować się do serwera sieci VPN.
- **Typ połączenia** — umożliwia wybór typu połączenia sieci VPN z poniższej listy dostawców:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Citrix**

- **Odcisk palca** (tylko dla Check Point Capsule VPN) — określ ciąg znaków, na przykład „kod odcisku palca firmy Contoso”, który będzie używany do sprawdzenia, czy serwer sieci VPN jest zaufany. Odcisk palca można wysłać do klienta, który będzie wówczas traktował każdy serwer przedstawiający ten sam odcisk palca podczas połączenia jako zaufany. Jeśli urządzenie nie otrzymało jeszcze odcisku palca, zostanie wyświetlony monit dotyczący zaufania do serwera sieci VPN, z którym jest nawiązywane połączenie, zawierający odcisk palca (użytkownik samodzielnie weryfikuje odcisk palca i wybiera opcję zaufania, aby nawiązać połączenie).
- **Podaj pary klucza i wartości dla atrybutów sieci VPN Citrix** (tylko dla Citrix) — wprowadź pary klucza i wartości dostarczone przez dostawcę Citrix, aby skonfigurować właściwości połączenia sieci VPN.

