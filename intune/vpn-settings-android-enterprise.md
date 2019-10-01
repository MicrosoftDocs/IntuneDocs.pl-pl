---
title: Konfigurowanie ustawień sieci VPN dla urządzeń z systemem Android Enterprise w usłudze Microsoft Intune — Azure | Microsoft Docs
description: Zobacz wszystkie ustawienia, aby utworzyć połączenia sieci VPN na urządzeniach z systemem Android Enterprise w Microsoft Intune. Wprowadź nazwę połączenia, adres IP lub nazwę FQDN serwera sieci VPN, wybierz sposób uwierzytelniania użytkowników, a następnie wybierz Citrix, SonicWall, Check Point kapsułka i Pulse bezpieczne typy połączeń.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/06/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: eff546c619f6314508c475a98bc29c3f8bc8181b
ms.sourcegitcommit: b78793ccbef2a644a759ca3110ea73e7ed6ceb8f
ms.translationtype: MTE75
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2019
ms.locfileid: "71302818"
---
# <a name="android-enterprise-device-settings-to-configure-vpn-in-intune"></a>Ustawienia urządzenia z systemem Android w celu skonfigurowania sieci VPN w usłudze Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

W tym artykule wyszczególniono i opisano różne ustawienia połączenia VPN, którymi można zarządzać na urządzeniach z systemem Android Enterprise. W ramach rozwiązania do zarządzania urządzeniami przenośnymi (MDM) Użyj tych ustawień, aby utworzyć połączenie sieci VPN, wybierz sposób uwierzytelniania sieci VPN, wybierz typ serwera sieci VPN i inne.

Jako administrator usługi Intune możesz utworzyć i przypisać ustawienia sieci VPN do urządzeń z systemem Android Enterprise. 

Aby dowiedzieć się więcej o profilach sieci VPN w usłudze Intune, zobacz [Profile sieci VPN](vpn-settings-configure.md).

## <a name="before-you-begin"></a>Przed rozpoczęciem

[Utwórz profil konfiguracji urządzenia](vpn-settings-configure.md#create-a-device-profile)i wybierz pozycję **Android Enterprise**.

## <a name="device-owner-only"></a>Tylko właściciel urządzenia

- **Nazwa połączenia**: umożliwia wprowadzenie nazwy połączenia. Użytkownicy końcowi widzą tę nazwę, przeglądając w urządzeniu listę dostępnych połączeń sieci VPN. Na przykład wprowadź `Contoso VPN`.
- **Adres IP lub nazwa FQDN** — podaj adres IP lub w pełni kwalifikowaną nazwę domeny (FQDN) serwera sieci VPN, z którym urządzenia nawiązują połączenie. Na przykład podaj adres **192.168.1.1** lub **vpn.contoso.com**.

  - **Metoda uwierzytelniania**: umożliwia wybór sposobu uwierzytelniania urządzeń na serwerze sieci VPN. Dostępne opcje:
  
    - **Certyfikaty**: wybierz istniejący profil certyfikatu SCEP lub PKCS na potrzeby uwierzytelniania połączenia. [Konfigurowanie certyfikatów](certificates-configure.md): zawiera procedurę tworzenia profilu certyfikatu.
    - **Nazwa użytkownika i hasło**: podczas logowania na serwerze VPN użytkownicy końcowi są proszeni o podanie nazwy użytkownika i hasła.

- **Typ połączenia**: pozwala wybrać typ połączenia VPN. Dostępne opcje:

  - **Cisco AnyConnect**
  - **F5 Access**
  - **Pulse Secure**

## <a name="work-profile-only"></a>Tylko profil służbowy

- **Nazwa połączenia**: umożliwia wprowadzenie nazwy połączenia. Użytkownicy końcowi widzą tę nazwę, przeglądając w urządzeniu listę dostępnych połączeń sieci VPN. Na przykład wprowadź `Contoso VPN`.
- **Adres IP lub nazwa FQDN** — podaj adres IP lub w pełni kwalifikowaną nazwę domeny (FQDN) serwera sieci VPN, z którym urządzenia nawiązują połączenie. Na przykład podaj adres **192.168.1.1** lub **vpn.contoso.com**.

  - **Metoda uwierzytelniania**: umożliwia wybór sposobu uwierzytelniania urządzeń na serwerze sieci VPN. Dostępne opcje:
  
    - **Certyfikaty**: wybierz istniejący profil certyfikatu SCEP lub PKCS na potrzeby uwierzytelniania połączenia. [Konfigurowanie certyfikatów](certificates-configure.md): zawiera procedurę tworzenia profilu certyfikatu.
    - **Nazwa użytkownika i hasło**: podczas logowania na serwerze VPN użytkownicy końcowi są proszeni o podanie nazwy użytkownika i hasła.

- **Typ połączenia**: pozwala wybrać typ połączenia VPN. Dostępne opcje:

  - **Cisco AnyConnect**
  - **F5 Access**
  - **Pulse Secure**
  - **SonicWall Mobile Connect**
  - **Check Point Capsule VPN**

## <a name="next-steps"></a>Następne kroki

[Przypisywanie profilu](device-profile-assign.md) i [monitorowanie jego stanu](device-profile-monitor.md).

Można również tworzyć profile sieci VPN dla urządzeń z [systemami](vpn-settings-ios.md) [Android](vpn-settings-android.md), iOS, [macOS](vpn-settings-macos.md), [Windows 10 i nowszych](vpn-settings-windows-10.md), [Windows 8.1](vpn-settings-windows-8-1.md)i [Windows Phone 8,1](vpn-settings-windows-phone-8-1.md) .
