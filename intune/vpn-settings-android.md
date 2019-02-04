---
title: Konfigurowanie ustawień sieci VPN dla urządzeń z systemem Android w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Podczas tworzenia profilu konfiguracji sieci VPN dla urządzeń z systemem Android i urządzeń z programem Android for Work wprowadź nazwę połączenia, adres IP lub nazwę FQDN serwera sieci VPN, wybierz sposób uwierzytelniania użytkowników przy użyciu serwera sieci VPN, a następnie wybierz typ połączenia Citrix, SonicWall, Check Point Capsule, Pulse Secure i Microsoft Edge.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 5e442ae550d138d532f7a2d8e829c623d09f240a
ms.sourcegitcommit: 9739a9aab032ebb2c4b52ccfb454a9e0f78b2ee4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54751165"
---
# <a name="configure-vpn-settings-for-devices-running-android-in-intune"></a>Konfigurowanie ustawień sieci VPN dla urządzeń z systemem Android w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ten artykuł zawiera informacje dotyczące ustawień usługi Intune, za pomocą których można skonfigurować połączenia sieci VPN na urządzeniach z systemem Android.

Możesz skonfigurować ustawienia sieci VPN dla następujących platform:

- [Android](#android-vpn-settings)
- [Android enterprise](#android-enterprise-vpn-settings)

W zależności od wybranych ustawień niektórych wartości z poniższej listy nie będzie można skonfigurować.

## <a name="android-vpn-settings"></a>Ustawienia sieci VPN dla systemu Android

- **Nazwa połączenia**: Wprowadź nazwę dla połączenia. Użytkownicy końcowi widzą tę nazwę, przeglądając w urządzeniu listę dostępnych połączeń sieci VPN.
- **Adres IP lub nazwa FQDN**: wprowadź adres IP lub w pełni kwalifikowaną nazwę domeny (FQDN) serwera sieci VPN, z którym urządzenia nawiązują połączenie. Na przykład podaj adres **192.168.1.1** lub **vpn.contoso.com**.

  - **Metoda uwierzytelniania**: wybierz sposób uwierzytelniania urządzeń na serwerze sieci VPN. Dostępne opcje:

    - **Certyfikaty**: wybierz istniejący profil certyfikatu SCEP lub PKCS na potrzeby uwierzytelniania połączenia. [Konfigurowanie certyfikatów](certificates-configure.md): zawiera procedurę tworzenia profilu certyfikatu.
    - **Nazwa użytkownika i hasło**: podczas logowania się do serwera sieci VPN użytkownicy są proszeni o wprowadzenie nazwy użytkownika i hasła.

- **Typ połączenia**: wybierz typ połączenia sieci VPN. Dostępne opcje:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**
  - **Citrix**

- **Odcisk palca** (tylko funkcja Check Point Capsule VPN): wprowadź ciąg znaków, na przykład **Kod odcisku palca firmy Contoso**, aby sprawdzić, czy serwer sieci VPN jest zaufany. Odcisk palca można wysłać do klienta, który będzie wówczas traktował każdy serwer przedstawiający ten sam odcisk palca podczas połączenia jako zaufany. Jeśli urządzenie nie ma żadnego odcisku palca, wyświetli użytkownikowi monit dotyczący zaufania serwerowi sieci VPN zawierający odcisk palca serwera. Użytkownik samodzielnie weryfikuje odcisk palca i wybiera pozycję Zaufane w celu nawiązania połączenia.
- **Wprowadź pary kluczy i wartości dla atrybutów sieci VPN Citrix** (tylko Citrix): wprowadź pary kluczy i wartości udostępnione przez firmę Citrix. Te wartości służą do konfigurowania właściwości połączenia sieci VPN.

## <a name="android-enterprise-vpn-settings"></a>Ustawienia sieci VPN systemu Android Enterprise

- **Nazwa połączenia**: Wprowadź nazwę dla połączenia. Użytkownicy końcowi widzą tę nazwę, przeglądając w urządzeniu listę dostępnych połączeń sieci VPN.
- **Adres IP lub nazwa FQDN**: wprowadź adres IP lub w pełni kwalifikowaną nazwę domeny (FQDN) serwera sieci VPN, z którym urządzenia nawiązują połączenie. Na przykład podaj adres **192.168.1.1** lub **vpn.contoso.com**.

  - **Metoda uwierzytelniania**: wybierz sposób uwierzytelniania urządzeń na serwerze sieci VPN. Dostępne opcje:
  
    - **Certyfikaty**: wybierz istniejący profil certyfikatu SCEP lub PKCS na potrzeby uwierzytelniania połączenia. [Konfigurowanie certyfikatów](certificates-configure.md): zawiera procedurę tworzenia profilu certyfikatu.
    - **Nazwa użytkownika i hasło**: podczas logowania się do serwera sieci VPN użytkownicy są proszeni o wprowadzenie nazwy użytkownika i hasła.

- **Typ połączenia**: wybierz typ połączenia sieci VPN. Dostępne opcje:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Access**
  - **Pulse Secure**

## <a name="next-steps"></a>Następne kroki
[Profile poczty e-mail w usłudze Intune](vpn-settings-configure.md)
