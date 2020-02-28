---
title: Konfigurowanie ustawień sieci VPN dla urządzeń z systemem Android Enterprise w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zobacz wszystkie ustawienia potrzebne do utworzenia połączeń sieci VPN na urządzeniach z systemem Android Enterprise w usłudze Microsoft Intune. Wprowadź nazwę połączenia, adres IP lub nazwę FQDN serwera sieci VPN, wybierz sposób uwierzytelniania użytkowników, a następnie wybierz typ połączenia Citrix, SonicWall, Check Point Capsule lub Pulse Secure.
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
ms.openlocfilehash: 81300651355e52f438ea2a314eeb1d0d48e3fcbc
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77510868"
---
# <a name="android-enterprise-device-settings-to-configure-vpn-in-intune"></a>Ustawienia urządzenia z systemem Android potrzebne do skonfigurowania sieci VPN w usłudze Intune

W tym artykule wyszczególniono i opisano różne ustawienia połączenia VPN, którymi można zarządzać na urządzeniach z systemem Android Enterprise. W ramach rozwiązania do zarządzania urządzeniami mobilnymi (MDM) użyj tych ustawień, aby utworzyć połączenie sieci VPN, wybrać sposób uwierzytelniania sieci VPN, wybrać typ serwera sieci VPN i inne parametry.

Jako administrator usługi Intune możesz tworzyć ustawienia sieci VPN i przypisywać je do urządzeń z rozwiązaniem Android Enterprise. 

Aby dowiedzieć się więcej o profilach sieci VPN w usłudze Intune, zobacz [Profile sieci VPN](vpn-settings-configure.md).

> [!NOTE]
> Aby skonfigurować zawsze włączoną sieć VPN, należy utworzyć profil sieci VPN, a także utworzyć profil [ograniczeń urządzenia](device-restrictions-android-for-work.md#connectivity) ze skonfigurowanym ustawieniem Zawsze włączona sieć VPN.

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia](vpn-settings-configure.md#create-a-device-profile) i wybierz pozycję **Android Enterprise**.

## <a name="device-owner-only"></a>Tylko właściciel urządzenia

- **Nazwa połączenia**: Wprowadź nazwę dla połączenia. Użytkownicy końcowi widzą tę nazwę, przeglądając w urządzeniu listę dostępnych połączeń sieci VPN. Na przykład wprowadź `Contoso VPN`.
- **Adres IP lub nazwa FQDN**: wprowadź adres IP lub w pełni kwalifikowaną nazwę domeny (FQDN) serwera sieci VPN, z którym urządzenia nawiązują połączenie. Na przykład podaj adres **192.168.1.1** lub **vpn.contoso.com**.

  - **Metoda uwierzytelniania**: wybierz sposób uwierzytelniania urządzeń na serwerze sieci VPN. Dostępne opcje:
  
    - **Certyfikaty**: wybierz istniejący profil certyfikatu SCEP lub PKCS na potrzeby uwierzytelniania połączenia. [Konfigurowanie certyfikatów](../protect/certificates-configure.md): zawiera procedurę tworzenia profilu certyfikatu.
    - **Nazwa użytkownika i hasło**: podczas logowania się do serwera sieci VPN użytkownicy są proszeni o wprowadzenie nazwy użytkownika i hasła.

- **Typ połączenia**: wybierz typ połączenia sieci VPN. Dostępne opcje:

  - **Cisco AnyConnect**
  - **F5 Access**
  - **Pulse Secure**

## <a name="work-profile-only"></a>Tylko profil służbowy

- **Nazwa połączenia**: Wprowadź nazwę dla połączenia. Użytkownicy końcowi widzą tę nazwę, przeglądając w urządzeniu listę dostępnych połączeń sieci VPN. Na przykład wprowadź `Contoso VPN`.
- **Adres IP lub nazwa FQDN**: wprowadź adres IP lub w pełni kwalifikowaną nazwę domeny (FQDN) serwera sieci VPN, z którym urządzenia nawiązują połączenie. Na przykład podaj adres **192.168.1.1** lub **vpn.contoso.com**.

  - **Metoda uwierzytelniania**: wybierz sposób uwierzytelniania urządzeń na serwerze sieci VPN. Dostępne opcje:
  
    - **Certyfikaty**: wybierz istniejący profil certyfikatu SCEP lub PKCS na potrzeby uwierzytelniania połączenia. [Konfigurowanie certyfikatów](../protect/certificates-configure.md): zawiera procedurę tworzenia profilu certyfikatu.
    - **Nazwa użytkownika i hasło**: podczas logowania się do serwera sieci VPN użytkownicy są proszeni o wprowadzenie nazwy użytkownika i hasła.

- **Typ połączenia**: wybierz typ połączenia sieci VPN. Dostępne opcje:

  - **Cisco AnyConnect**
  - **F5 Access**
  - **Pulse Secure**
  - **SonicWall Mobile Connect**
  - **Check Point Capsule VPN**

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).

Można również tworzyć profile sieci VPN dla urządzeń z systemem [Android](vpn-settings-android.md), [iOS/iPadOS](vpn-settings-ios.md), [macOS](vpn-settings-macos.md), [Windows 10 lub nowszym](vpn-settings-windows-10.md), [Windows 8.1](vpn-settings-windows-8-1.md) i [Windows Phone 8.1](vpn-settings-windows-phone-8-1.md).
