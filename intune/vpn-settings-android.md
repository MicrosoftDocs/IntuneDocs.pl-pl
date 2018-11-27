---
title: Konfigurowanie ustawień sieci VPN dla urządzeń z systemem Android w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Podczas tworzenia profilu konfiguracji sieci VPN dla urządzeń z systemem Android i urządzeń z programem Android for Work wprowadź nazwę połączenia, adres IP lub nazwę FQDN serwera sieci VPN, wybierz sposób uwierzytelniania użytkowników przy użyciu serwera sieci VPN, a następnie wybierz typ połączenia Citrix, SonicWall, Check Point Capsule, Pulse Secure i Microsoft Edge.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 7/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: ac4b7821f132c92b247538e4ea6131f517da7698
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52187697"
---
# <a name="configure-vpn-settings-for-devices-running-android-in-intune"></a>Konfigurowanie ustawień sieci VPN dla urządzeń z systemem Android w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ten artykuł zawiera informacje dotyczące ustawień usługi Intune, za pomocą których można skonfigurować połączenia sieci VPN na urządzeniach z systemem Android.

Możesz skonfigurować ustawienia sieci VPN dla następujących platform:

- [Android](#android-vpn-settings)
- [Android for Work](#android-for-work-vpn-settings)

W zależności od wybranych ustawień niektórych wartości z poniższej listy nie będzie można skonfigurować.

## <a name="android-vpn-settings"></a>Ustawienia sieci VPN dla systemu Android

- **Nazwa połączenia**: umożliwia wprowadzenie nazwy połączenia. Użytkownicy końcowi widzą tę nazwę, przeglądając w urządzeniu listę dostępnych połączeń sieci VPN.
- **Adres IP lub nazwa FQDN** — podaj adres IP lub w pełni kwalifikowaną nazwę domeny (FQDN) serwera sieci VPN, z którym urządzenia nawiązują połączenie. Na przykład podaj adres **192.168.1.1** lub **vpn.contoso.com**.

  - **Metoda uwierzytelniania**: umożliwia wybór sposobu uwierzytelniania urządzeń na serwerze sieci VPN. Dostępne opcje:

    - **Certyfikaty**: wybierz istniejący profil certyfikatu SCEP lub PKCS na potrzeby uwierzytelniania połączenia. [Konfigurowanie certyfikatów](certificates-configure.md): zawiera procedurę tworzenia profilu certyfikatu.
    - **Nazwa użytkownika i hasło**: podczas logowania się do serwera sieci VPN użytkownicy są proszeni o wprowadzenie nazwy użytkownika i hasła.

- **Typ połączenia**: pozwala wybrać typ połączenia VPN. Dostępne opcje:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**
  - **Citrix**

- **Odcisk palca** (tylko dla Check Point Capsule VPN) — wprowadź ciąg znaków, na przykład **Kod odcisku palca firmy Contoso**, aby sprawdzić, czy serwer sieci VPN jest zaufany. Odcisk palca można wysłać do klienta, który będzie wówczas traktował każdy serwer przedstawiający ten sam odcisk palca podczas połączenia jako zaufany. Jeśli urządzenie nie ma żadnego odcisku palca, wyświetli użytkownikowi monit dotyczący zaufania serwerowi sieci VPN zawierający odcisk palca serwera. Użytkownik samodzielnie weryfikuje odcisk palca i wybiera pozycję Zaufane w celu nawiązania połączenia.
- **Podaj pary klucza i wartości dla atrybutów sieci VPN Citrix** (tylko dla dostawcy Citrix) — wprowadź pary klucza i wartości dostarczone przez dostawcę Citrix. Te wartości służą do konfigurowania właściwości połączenia sieci VPN.

## <a name="android-for-work-vpn-settings"></a>Ustawienia sieci VPN dla programu Android for Work

- **Nazwa połączenia**: umożliwia wprowadzenie nazwy połączenia. Użytkownicy końcowi widzą tę nazwę, przeglądając w urządzeniu listę dostępnych połączeń sieci VPN.
- **Adres IP lub nazwa FQDN** — podaj adres IP lub w pełni kwalifikowaną nazwę domeny (FQDN) serwera sieci VPN, z którym urządzenia nawiązują połączenie. Na przykład podaj adres **192.168.1.1** lub **vpn.contoso.com**.

  - **Metoda uwierzytelniania**: umożliwia wybór sposobu uwierzytelniania urządzeń na serwerze sieci VPN. Dostępne opcje:
  
    - **Certyfikaty**: wybierz istniejący profil certyfikatu SCEP lub PKCS na potrzeby uwierzytelniania połączenia. [Konfigurowanie certyfikatów](certificates-configure.md): zawiera procedurę tworzenia profilu certyfikatu.
    - **Nazwa użytkownika i hasło**: podczas logowania się do serwera sieci VPN użytkownicy są proszeni o wprowadzenie nazwy użytkownika i hasła.

- **Typ połączenia**: pozwala wybrać typ połączenia VPN. Dostępne opcje:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**

## <a name="next-steps"></a>Następne kroki
[Profile poczty e-mail w usłudze Intune](vpn-settings-configure.md)
